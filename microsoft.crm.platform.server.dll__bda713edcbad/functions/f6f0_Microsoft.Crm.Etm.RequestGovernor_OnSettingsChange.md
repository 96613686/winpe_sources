# Microsoft.Crm.Etm.RequestGovernor::OnSettingsChange

- ea: `0xf6f0`
- end: `0xf7b9`
- name: `Microsoft.Crm.Etm.RequestGovernor::OnSettingsChange`
- size: `201`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callees

- `0xdcb0`
- `0xdcc0`
- `0xdcd0`
- `0xdce0`
- `0xdcf0`
- `0xdd00`
- `0xf3c0`
- `0xf6f0`
- `0xffd0`
- `0xffe0`
- `0xfff0`
- `0x10000`
- `0x10010`
- `0x10020`
- `0x10030`

## string_xrefs

- `0xf780`: `RequestGovernor detected a change in configuration.`
- `0xf7a2`: `Exception during re-initialize. ETM disabled. {0}`

## pseudocode

```c

```

## disassembly

```asm
0xf6f0  newobj   instance void Microsoft.Crm.Etm.EtmServerConfiguration::.ctor()
0xf6f5  stloc.0
0xf6f6  ldloc.0
0xf6f7  callvirt instance bool Microsoft.Crm.Etm.EtmServerConfiguration::get_Enabled()
0xf6fc  ldarg.0
0xf6fd  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf702  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_Enabled()
0xf707  bne.un.s loc_F76D
0xf709  ldloc.0
0xf70a  callvirt instance bool Microsoft.Crm.Etm.EtmServerConfiguration::get_ThrottlingEnabled()
0xf70f  ldarg.0
0xf710  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf715  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_ThrottlingEnabled()
0xf71a  bne.un.s loc_F76D
0xf71c  ldloc.0
0xf71d  callvirt instance bool Microsoft.Crm.Etm.EtmServerConfiguration::get_ServerThrottlingDisabled()
0xf722  ldarg.0
0xf723  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf728  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_ServerThrottlingDisabled()
0xf72d  bne.un.s loc_F76D
0xf72f  ldloc.0
0xf730  callvirt instance string Microsoft.Crm.Etm.EtmServerConfiguration::get_ProviderConfiguration()
0xf735  ldarg.0
0xf736  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf73b  callvirt instance string Microsoft.Crm.Etm.IConfiguration::get_ProviderConfiguration()
0xf740  call     bool [mscorlib]System.String::op_Inequality(string, string)
0xf745  brtrue.s loc_F76D
0xf747  ldloc.0
0xf748  callvirt instance int32 Microsoft.Crm.Etm.EtmServerConfiguration::get_AsyncCollectInterval()
0xf74d  ldarg.0
0xf74e  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf753  callvirt instance int32 Microsoft.Crm.Etm.IConfiguration::get_AsyncCollectInterval()
0xf758  bne.un.s loc_F76D
0xf75a  ldloc.0
0xf75b  callvirt instance bool Microsoft.Crm.Etm.EtmServerConfiguration::get_StatisticsUpdateEnabled()
0xf760  ldarg.0
0xf761  ldfld    class Microsoft.Crm.Etm.IConfiguration Microsoft.Crm.Etm.RequestGovernor::_configuration
0xf766  callvirt instance bool Microsoft.Crm.Etm.IConfiguration::get_StatisticsUpdateEnabled()
0xf76b  beq.s    loc_F792
0xf76d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xf772  ldc.i4.7
0xf773  ldstr    a0// "{0}"
0xf778  ldc.i4.1
0xf779  newarr   [mscorlib]System.Object
0xf77e  dup
0xf77f  ldc.i4.0
0xf780  ldstr    aRequestgoverno_3// "RequestGovernor detected a change in co"...
0xf785  stelem.ref
0xf786  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf78b  ldarg.0
0xf78c  ldloc.0
0xf78d  call     instance void Microsoft.Crm.Etm.RequestGovernor::Initialize(class Microsoft.Crm.Etm.IConfiguration configuration)
0xf792  leave.s  loc_F7B8
0xf794  stloc.1
0xf795  ldc.i4.0
0xf796  stsfld   bool Microsoft.Crm.Etm.RequestGovernor::_governorEnabled
0xf79b  ldloc.1
0xf79c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xf7a1  ldc.i4.7
0xf7a2  ldstr    aExceptionDurin// "Exception during re-initialize. ETM dis"...
0xf7a7  ldc.i4.1
0xf7a8  newarr   [mscorlib]System.Object
0xf7ad  dup
0xf7ae  ldc.i4.0
0xf7af  ldloc.1
0xf7b0  stelem.ref
0xf7b1  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf7b6  leave.s  loc_F7B8
0xf7b8  ret
```
