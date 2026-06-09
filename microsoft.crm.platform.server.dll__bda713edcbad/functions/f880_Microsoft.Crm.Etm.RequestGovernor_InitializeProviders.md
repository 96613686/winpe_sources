# Microsoft.Crm.Etm.RequestGovernor::InitializeProviders

- ea: `0xf880`
- end: `0xfad8`
- name: `Microsoft.Crm.Etm.RequestGovernor::InitializeProviders`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf3c0`

## callees

- `0xdcd0`
- `0xdce0`
- `0xdcf0`
- `0xdd00`
- `0xdd40`
- `0xddd0`
- `0xded0`
- `0xdef0`
- `0xdf10`
- `0xdf50`
- `0xdf70`
- `0xe130`
- `0xe150`
- `0xf7c0`
- `0xf820`
- `0xf880`

## string_xrefs

- `0xf893`: `Configuration expected to be non-null`
- `0xfa5f`: `ETM background thread`

## pseudocode

```c

```

## disassembly

```asm
0xf880  ldsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf885  brfalse  loc_FAD7
0xf88a  ldarg.0
0xf88b  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf890  ldnull
0xf891  cgt.un
0xf893  ldstr    aConfigurationE// "Configuration expected to be non-null"
0xf898  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xf89d  ldarg.0
0xf89e  ldfld    class Microsoft.Crm.Etm.DataManager Microsoft.Crm.Etm.RequestGovernor::_dataManager
0xf8a3  ldnull
0xf8a4  cgt.un
0xf8a6  ldstr    aDataManagerExp// "Data Manager expected to be non-null"
0xf8ab  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0xf8b0  ldarg.0
0xf8b1  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf8b6  callvirt instance string Microsoft.Crm.Etm.IConfiguration::get_ProviderConfiguration()
0xf8bb  stloc.0
0xf8bc  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IDataCollector>::.ctor()
0xf8c1  stloc.1
0xf8c2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IThrottleProvider>::.ctor()
0xf8c7  stloc.2
0xf8c8  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IPerformanceDataCollector>::.ctor()
0xf8cd  stloc.3
0xf8ce  ldloc.0
0xf8cf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf8d4  brtrue   loc_FA15
0xf8d9  ldnull
0xf8da  stloc.s  4
0xf8dc  ldtoken  Microsoft.Crm.Etm.ProviderConfiguration
0xf8e1  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xf8e6  newobj   instance void [System.Xml]System.Xml.Serialization.XmlSerializer::.ctor(class [mscorlib]System.Type)
0xf8eb  stloc.s  5
0xf8ed  ldloc.0
0xf8ee  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0xf8f3  stloc.s  6
0xf8f5  ldloc.s  6
0xf8f7  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0xf8fc  stloc.s  7
0xf8fe  ldloc.s  5
0xf900  ldloc.s  7
0xf902  callvirt instance object [System.Xml]System.Xml.Serialization.XmlSerializer::Deserialize(class [System.Xml]System.Xml.XmlReader)
0xf907  castclass Microsoft.Crm.Etm.ProviderConfiguration
0xf90c  stloc.s  4
0xf90e  leave.s  loc_F928
0xf910  ldloc.s  7
0xf912  brfalse.s loc_F91B
0xf914  ldloc.s  7
0xf916  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf91b  endfinally
0xf91c  ldloc.s  6
0xf91e  brfalse.s loc_F927
0xf920  ldloc.s  6
0xf922  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xf927  endfinally
0xf928  ldloc.s  4
0xf92a  brfalse  loc_FA15
0xf92f  ldloc.s  4
0xf931  callvirt instance class Microsoft.Crm.Etm.DataCollectorConfiguration[] Microsoft.Crm.Etm.ProviderConfiguration::get_DataCollectionProviders()
0xf936  brfalse.s loc_F98C
0xf938  ldloc.s  4
0xf93a  callvirt instance class Microsoft.Crm.Etm.DataCollectorConfiguration[] Microsoft.Crm.Etm.ProviderConfiguration::get_DataCollectionProviders()
0xf93f  stloc.s  8
0xf941  ldc.i4.0
0xf942  stloc.s  9
0xf944  br.s     loc_F984
0xf946  ldloc.s  8
0xf948  ldloc.s  9
0xf94a  ldelem.ref
0xf94b  stloc.s  0xA
0xf94d  ldarg.0
0xf94e  ldloc.s  0xA
0xf950  callvirt instance string Microsoft.Crm.Etm.DataCollectorConfiguration::get_TypeName()
0xf955  call     T0x2B00001E
0xf95a  stloc.s  0xB
0xf95c  ldloc.s  0xB
0xf95e  ldarg.0
0xf95f  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf964  ldloc.s  0xA
0xf966  callvirt instance class Microsoft.Crm.Etm.ProviderSetting[] Microsoft.Crm.Etm.DataCollectorConfiguration::get_Settings()
0xf96b  ldarg.0
0xf96c  ldfld    class Microsoft.Crm.Etm.DataManager Microsoft.Crm.Etm.RequestGovernor::_dataManager
0xf971  callvirt instance void Microsoft.Crm.Etm.IDataCollector::Initialize(class Microsoft.Crm.Etm.IConfiguration configuration, class Microsoft.Crm.Etm.ProviderSetting[] settings, class Microsoft.Crm.Etm.IDataManager dataManager)
0xf976  ldloc.1
0xf977  ldloc.s  0xB
0xf979  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IDataCollector>::Add(var<u1>)
0xf97e  ldloc.s  9
0xf980  ldc.i4.1
0xf981  add
0xf982  stloc.s  9
0xf984  ldloc.s  9
0xf986  ldloc.s  8
0xf988  ldlen
0xf989  conv.i4
0xf98a  blt.s    loc_F946
0xf98c  ldloc.s  4
0xf98e  callvirt instance class Microsoft.Crm.Etm.PerformanceCollectorConfiguration[] Microsoft.Crm.Etm.ProviderConfiguration::get_PerformanceCollectionProviders()
0xf993  brfalse.s loc_F99E
0xf995  ldarg.0
0xf996  ldloc.s  4
0xf998  call     instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IPerformanceDataCollector> Microsoft.Crm.Etm.RequestGovernor::LoadPerformanceDataCollectors(class Microsoft.Crm.Etm.ProviderConfiguration providerConfiguration)
0xf99d  stloc.3
0xf99e  ldarg.0
0xf99f  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf9a4  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_ThrottlingEnabled()
0xf9a9  brfalse.s loc_FA15
0xf9ab  ldloc.s  4
0xf9ad  callvirt instance class Microsoft.Crm.Etm.ThrottleProviderConfiguration[] Microsoft.Crm.Etm.ProviderConfiguration::get_ThrottleProviders()
0xf9b2  brfalse.s loc_FA15
0xf9b4  ldarg.0
0xf9b5  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf9ba  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_ServerThrottlingDisabled()
0xf9bf  brtrue.s loc_FA15
0xf9c1  ldloc.s  4
0xf9c3  callvirt instance class Microsoft.Crm.Etm.ThrottleProviderConfiguration[] Microsoft.Crm.Etm.ProviderConfiguration::get_ThrottleProviders()
0xf9c8  stloc.s  0xC
0xf9ca  ldc.i4.0
0xf9cb  stloc.s  9
0xf9cd  br.s     loc_FA0D
0xf9cf  ldloc.s  0xC
0xf9d1  ldloc.s  9
0xf9d3  ldelem.ref
0xf9d4  stloc.s  0xD
0xf9d6  ldarg.0
0xf9d7  ldloc.s  0xD
0xf9d9  callvirt instance string Microsoft.Crm.Etm.ThrottleProviderConfiguration::get_TypeName()
0xf9de  call     T0x2B00001F
0xf9e3  stloc.s  0xE
0xf9e5  ldloc.s  0xE
0xf9e7  ldarg.0
0xf9e8  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf9ed  ldloc.s  0xD
0xf9ef  callvirt instance class Microsoft.Crm.Etm.ProviderSetting[] Microsoft.Crm.Etm.ThrottleProviderConfiguration::get_Settings()
0xf9f4  ldarg.0
0xf9f5  ldfld    class Microsoft.Crm.Etm.DataManager Microsoft.Crm.Etm.RequestGovernor::_dataManager
0xf9fa  callvirt instance void Microsoft.Crm.Etm.IThrottleProvider::Initialize(class Microsoft.Crm.Etm.IConfiguration configuration, class Microsoft.Crm.Etm.ProviderSetting[] settings, class Microsoft.Crm.Etm.IDataManager dataManager)
0xf9ff  ldloc.2
0xfa00  ldloc.s  0xE
0xfa02  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IThrottleProvider>::Add(var<u1>)
0xfa07  ldloc.s  9
0xfa09  ldc.i4.1
0xfa0a  add
0xfa0b  stloc.s  9
0xfa0d  ldloc.s  9
0xfa0f  ldloc.s  0xC
0xfa11  ldlen
0xfa12  conv.i4
0xfa13  blt.s    loc_F9CF
0xfa15  ldarg.0
0xfa16  ldloc.1
0xfa17  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IDataCollector> Microsoft.Crm.Etm.RequestGovernor::_dataCollectors
0xfa1c  ldarg.0
0xfa1d  ldloc.2
0xfa1e  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IThrottleProvider> Microsoft.Crm.Etm.RequestGovernor::_throttleProviders
0xfa23  ldarg.0
0xfa24  ldloc.3
0xfa25  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IPerformanceDataCollector> Microsoft.Crm.Etm.RequestGovernor::_performanceDataCollectors
0xfa2a  ldloc.1
0xfa2b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IDataCollector>::get_Count()
0xfa30  ldc.i4.0
0xfa31  ble.s    loc_FA88
0xfa33  ldarg.0
0xfa34  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xfa39  callvirt instance int32 Microsoft.Crm.Etm.IConfiguration::get_AsyncCollectInterval()
0xfa3e  dup
0xfa3f  ldc.i4.1
0xfa40  ldc.i4.s 0x3C
0xfa42  ldstr    aAsynccollectin// "AsyncCollectInterval"
0xfa47  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfOutOfRange(int32, int32, int32, string)
0xfa4c  conv.r8
0xfa4d  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0xfa52  stloc.s  0x10
0xfa54  ldloca.s 0x10
0xfa56  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0xfa5b  conv.i4
0xfa5c  stloc.s  0xF
0xfa5e  ldarg.0
0xfa5f  ldstr    aEtmBackgroundT// "ETM background thread"
0xfa64  ldloc.s  0xF
0xfa66  conv.r8
0xfa67  ldarg.0
0xfa68  ldftn    instance void Microsoft.Crm.Etm.RequestGovernor::OnTimerCallback(object sender, class [Microsoft.Crm.Core]Microsoft.Crm.Timers.ElapsedEventArgs e)
0xfa6e  newobj   instance void class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Core]Microsoft.Crm.Timers.ElapsedEventArgs>::.ctor(object, native int)
0xfa73  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer::.ctor(string, float64, class [mscorlib]System.EventHandler`1<class [Microsoft.Crm.Core]Microsoft.Crm.Timers.ElapsedEventArgs>)
0xfa78  stfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Etm.RequestGovernor::_backgroundCollectionTimer
0xfa7d  ldarg.0
0xfa7e  ldfld    class [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer Microsoft.Crm.Etm.RequestGovernor::_backgroundCollectionTimer
0xfa83  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.Timers.Timer::Start()
0xfa88  ldloc.3
0xfa89  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IPerformanceDataCollector>::get_Count()
0xfa8e  ldc.i4.0
0xfa8f  ble.s    loc_FA97
0xfa91  ldarg.0
0xfa92  call     instance void Microsoft.Crm.Etm.RequestGovernor::StartPerformanceMonitorThread()
0xfa97  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xfa9c  ldc.i4.7
0xfa9d  ldstr    aRequestgoverno_4// "RequestGovernor Initialized with {0} co"...
0xfaa2  ldc.i4.3
0xfaa3  newarr   [mscorlib]System.Object
0xfaa8  dup
0xfaa9  ldc.i4.0
0xfaaa  ldloc.1
0xfaab  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IDataCollector>::get_Count()
0xfab0  box      [mscorlib]System.Int32
0xfab5  stelem.ref
0xfab6  dup
0xfab7  ldc.i4.1
0xfab8  ldloc.2
0xfab9  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IThrottleProvider>::get_Count()
0xfabe  box      [mscorlib]System.Int32
0xfac3  stelem.ref
0xfac4  dup
0xfac5  ldc.i4.2
0xfac6  ldloc.3
0xfac7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Etm.IPerformanceDataCollector>::get_Count()
0xfacc  box      [mscorlib]System.Int32
0xfad1  stelem.ref
0xfad2  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xfad7  ret
```
