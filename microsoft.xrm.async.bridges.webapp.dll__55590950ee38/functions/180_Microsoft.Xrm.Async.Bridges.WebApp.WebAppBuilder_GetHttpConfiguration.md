# Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::GetHttpConfiguration

- ea: `0x180`
- end: `0x1f4`
- name: `Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::GetHttpConfiguration`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x130`

## callees

- `0x90`
- `0x180`
- `0x200`

## pseudocode

```c

```

## disassembly

```asm
0x180  newobj   instance void [System.Web.Http]System.Web.Http.HttpConfiguration::.ctor()
0x185  stloc.0
0x186  newobj   instance void Microsoft.Xrm.Async.Bridges.WebApp.InheritingDirectRouteProvider::.ctor()
0x18b  stloc.1
0x18c  ldloc.0
0x18d  ldloc.1
0x18e  call     void [System.Web.Http]System.Web.Http.HttpConfigurationExtensions::MapHttpAttributeRoutes(class [System.Web.Http]System.Web.Http.HttpConfiguration, class [System.Web.Http]System.Web.Http.Routing.IDirectRouteProvider)
0x193  ldarg.0
0x194  ldloc.0
0x195  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Formatters()
0x19a  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.JsonMediaTypeFormatter [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection::get_JsonFormatter()
0x19f  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings [System.Net.Http.Formatting]System.Net.Http.Formatting.BaseJsonMediaTypeFormatter::get_SerializerSettings()
0x1a4  callvirt instance void Microsoft.Xrm.Async.Bridges.WebApp.WebAppBuilder::ConfigureJsonSerializer(class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializerSettings serializerSettings)
0x1a9  ldloc.0
0x1aa  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Formatters()
0x1af  ldloc.0
0x1b0  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection [System.Web.Http]System.Web.Http.HttpConfiguration::get_Formatters()
0x1b5  callvirt instance class [System.Net.Http.Formatting]System.Net.Http.Formatting.XmlMediaTypeFormatter [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatterCollection::get_XmlFormatter()
0x1ba  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System.Net.Http.Formatting]System.Net.Http.Formatting.MediaTypeFormatter>::Remove(var<u1>)
0x1bf  pop
0x1c0  ldloc.0
0x1c1  ldarg.1
0x1c2  newobj   instance void [Autofac.Integration.WebApi]Autofac.Integration.WebApi.AutofacWebApiDependencyResolver::.ctor(class [Autofac]Autofac.ILifetimeScope)
0x1c7  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_DependencyResolver(class [System.Web.Http]System.Web.Http.Dependencies.IDependencyResolver)
0x1cc  ldarg.1
0x1cd  call     T0x2B000004
0x1d2  stloc.2
0x1d3  ldloc.2
0x1d4  callvirt instance valuetype [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.FromCommon.EnvironmentKind [Microsoft.Xrm.Async.Bridges]Microsoft.Xrm.Async.Bridges.FromCommon.EnvironmentConfig::get_Kind()
0x1d9  ldc.i4.2
0x1da  bne.un.s loc_1E5
0x1dc  ldloc.0
0x1dd  ldc.i4.3
0x1de  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_IncludeErrorDetailPolicy(valuetype [System.Web.Http]System.Web.Http.IncludeErrorDetailPolicy)
0x1e3  br.s     loc_1EC
0x1e5  ldloc.0
0x1e6  ldc.i4.2
0x1e7  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::set_IncludeErrorDetailPolicy(valuetype [System.Web.Http]System.Web.Http.IncludeErrorDetailPolicy)
0x1ec  ldloc.0
0x1ed  callvirt instance void [System.Web.Http]System.Web.Http.HttpConfiguration::EnsureInitialized()
0x1f2  ldloc.0
0x1f3  ret
```
