# Microsoft.Crm.CrmTraceSettings::LoadDeploymentSettings

- ea: `0x21310`
- end: `0x21421`
- name: `Microsoft.Crm.CrmTraceSettings::LoadDeploymentSettings`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x21000`

## callees

- `0xb10`
- `0x1110`
- `0x16f0`
- `0x1f80`
- `0x4640`
- `0x1be80`
- `0x20bd0`
- `0x20c10`
- `0x20c30`
- `0x20c50`
- `0x20cb0`
- `0x20ce0`
- `0x20cf0`
- `0x20dc0`
- `0x21310`
- `0x221b0`
- `0x340b0`

## string_xrefs

- `0x21388`: `TraceDirectory`
- `0x2131d`: `LocatorService.Instance`

## pseudocode

```c

```

## disassembly

```asm
0x21310  call     bool Microsoft.Crm.RegControl::IsInSandboxServerContext()
0x21315  brfalse.s loc_21318
0x21317  ret
0x21318  call     class Microsoft.Crm.LocatorService Microsoft.Crm.LocatorService::get_Instance()
0x2131d  ldstr    aLocatorservice_2// "LocatorService.Instance"
0x21322  call     void Microsoft.Crm.Exceptions::ThrowIfNull(object parameter, string name)
0x21327  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x2132c  ldc.i4.2
0x2132d  bne.un.s loc_21346
0x2132f  call     class Microsoft.Crm.IScaleGroupInfoProvider Microsoft.Crm.ScaleGroupInfoProvider::get_Instance()
0x21334  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.IScaleGroupInfoProvider::GetScaleGroupId()
0x21339  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2133e  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x21343  brfalse.s loc_21346
0x21345  ret
0x21346  newobj   instance void Microsoft.Crm.CrmTraceSettings::.ctor()
0x2134b  stloc.0
0x2134c  ldloc.0
0x2134d  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x21352  ldstr    aTraceenabled// "TraceEnabled"
0x21357  callvirt T0x2B00003D
0x2135c  brfalse.s loc_21361
0x2135e  ldc.i4.2
0x2135f  br.s     loc_21362
0x21361  ldc.i4.1
0x21362  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_IsTracingOff(valuetype TraceBool value)
0x21367  ldloc.0
0x21368  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2136d  ldstr    aTracecallstack// "TraceCallStack"
0x21372  callvirt T0x2B00003D
0x21377  brtrue.s loc_2137C
0x21379  ldc.i4.2
0x2137a  br.s     loc_2137D
0x2137c  ldc.i4.1
0x2137d  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TracingCallStack(valuetype TraceBool value)
0x21382  ldloc.0
0x21383  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x21388  ldstr    aTracedirectory// "TraceDirectory"
0x2138d  callvirt T0x2B00005B
0x21392  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceDirectory(string value)
0x21397  ldloc.0
0x21398  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x2139d  ldstr    aTracefilesize// "TraceFileSize"
0x213a2  callvirt T0x2B00003E
0x213a7  ldc.i4   0x100000
0x213ac  mul
0x213ad  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceFileSize(int32 value)
0x213b2  ldloc.0
0x213b3  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x213b8  ldstr    aTraceuseetwonl// "TraceUseEtwOnly"
0x213bd  call     valuetype Microsoft.Crm.SharedDatabase.ConfigSku Microsoft.Crm.BootstrapService::GetSku()
0x213c2  ldc.i4.2
0x213c3  ceq
0x213c5  callvirt T0x2B00004A
0x213ca  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_UseEtwTracingOnly(bool value)
0x213cf  call     class Microsoft.Crm.IDeploymentInfoProvider Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x213d4  ldstr    aTracecategorie// "TraceCategories"
0x213d9  callvirt T0x2B00005B
0x213de  stloc.1
0x213df  ldloc.1
0x213e0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x213e5  brfalse.s loc_213F0
0x213e7  ldloc.0
0x213e8  ldnull
0x213e9  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceCategoryLevels(class [mscorlib]System.Collections.Hashtable value)
0x213ee  br.s     loc_21414
0x213f0  ldloc.0
0x213f1  ldloc.1
0x213f2  call     class [mscorlib]System.Collections.Hashtable Microsoft.Crm.CrmTraceSettings::GenerateTraceCategories(string traceCategoriesUnsplit)
0x213f7  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceCategoryLevels(class [mscorlib]System.Collections.Hashtable value)
0x213fc  ldloc.0
0x213fd  callvirt instance class [mscorlib]System.Collections.Hashtable Microsoft.Crm.CrmTraceSettings::get_TraceCategoryLevels()
0x21402  brtrue.s loc_21414
0x21404  ldloc.0
0x21405  ldstr    aError_0// "*:Error"
0x2140a  call     class [mscorlib]System.Collections.Hashtable Microsoft.Crm.CrmTraceSettings::GenerateTraceCategories(string traceCategoriesUnsplit)
0x2140f  callvirt instance void Microsoft.Crm.CrmTraceSettings::set_TraceCategoryLevels(class [mscorlib]System.Collections.Hashtable value)
0x21414  ldsflda  class Microsoft.Crm.CrmTraceSettings Microsoft.Crm.CrmTraceSettings::_deploymentSettings
0x21419  ldloc.0
0x2141a  call     T0x2B00005E
0x2141f  pop
0x21420  ret
```
