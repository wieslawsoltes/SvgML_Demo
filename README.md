# SvgML Demo

SvgML adds support for embedding SVG images directly within Avalonia's inline XAML code.

## Install NuGet Package

https://www.nuget.org/packages/SvgML

```xml
<PackageReference Include="SvgML" Version="11.0.0-alpha.8" />
```

## svg xmlns

Remove any xmlns from svg xaml as they are not supported.

## Xaml

Add svg to xaml.

```xaml
<Window xmlns="https://github.com/avaloniaui"
        xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
        xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
        xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
        mc:Ignorable="d" d:DesignWidth="800" d:DesignHeight="450"
        x:Class="SvgML_Demo.MainWindow"
        Title="SvgML Demo">
  <Window.Styles>
    <Style Selector=":is(circle).animate">
      <Style.Animations>
        <Animation Duration="0:0:3" IterationCount="Infinite" PlaybackDirection="Alternate">
          <KeyFrame Cue="0%">
            <Setter Property="opacity" Value="0.0" />
          </KeyFrame>
          <KeyFrame Cue="100%">
            <Setter Property="opacity" Value="1.0" />
          </KeyFrame>
        </Animation>
      </Style.Animations>
    </Style>
  </Window.Styles>

  <svg viewBox="0 0 200 100">
    <defs>
      <linearGradient id="gradient" x1="0%" y1="0%" x2="0" y2="100%">
        <stop offset="0%" style="stop-color:skyblue;" />
        <stop offset="100%" style="stop-color:seagreen;" />
      </linearGradient>
    </defs>
    <rect x="0" y="0" width="100%" height="100%" fill="url(#gradient)" />
    <circle cx="50" cy="50" r="40" fill="black" Classes="animate" />
    <circle cx="150" cy="50" r="40" fill="black" opacity="0.3" />
  </svg>
</Window>
```
