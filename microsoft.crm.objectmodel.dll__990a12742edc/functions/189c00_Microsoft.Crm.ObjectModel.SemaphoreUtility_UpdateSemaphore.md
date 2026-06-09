# Microsoft.Crm.ObjectModel.SemaphoreUtility::UpdateSemaphore

- ea: `0x189c00`
- end: `0x189d61`
- name: `Microsoft.Crm.ObjectModel.SemaphoreUtility::UpdateSemaphore`
- size: `353`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x189b80`

## callees

- `0x6d5c0`
- `0x189c00`

## string_xrefs

- `0x189c22`: `MaxSharepointThreadsperUser`
- `0x189c3e`: `MaxSharepointThreadsperUser`
- `0x189c6f`: `MaxSharepointThreadsperUser`
- `0x189c29`: `UpdateSemaphore`
- `0x189c69`: `UpdateSemaphore`
- `0x189ccb`: `UpdateSemaphore`
- `0x189d16`: `UpdateSemaphore`
- `0x189c2e`: `D:\a\1\s\src\Core\ObjectModel\Services\SharePoint\SemaphoreUtility.cs`
- `0x189cd0`: `D:\a\1\s\src\Core\ObjectModel\Services\SharePoint\SemaphoreUtility.cs`
- `0x189cc4`: `MaxSharepointThreads`
- `0x189ce1`: `MaxSharepointThreadsperOrganisation`
- `0x189d1c`: `MaxSharepointThreadsperOrganization`

## pseudocode

```c

```

## disassembly

```asm
0x189c00  ldarg.2
0x189c01  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x189c06  stloc.0
0x189c07  ldarg.2
0x189c08  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x189c0d  stloc.1
0x189c0e  ldarg.1
0x189c0f  ldloc.0
0x189c10  callvirt instance bool class [Microsoft.Crm]Microsoft.Crm.ThreadSafeDictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Threading.Semaphore>::ContainsKey(var<u1>)
0x189c15  brtrue   loc_189CA5
0x189c1a  ldc.i4.1
0x189c1b  stloc.2
0x189c1c  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x189c21  ldloc.1
0x189c22  ldstr    aMaxsharepointt_0// "MaxSharepointThreadsperUser"
0x189c27  ldc.i4.s 0x22
0x189c29  ldstr    aUpdatesemaphor_0// "UpdateSemaphore"
0x189c2e  ldstr    aDA1SSrcCoreObj_49// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x189c33  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x189c38  stloc.3
0x189c39  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x189c3e  ldstr    aMaxsharepointt_0// "MaxSharepointThreadsperUser"
0x189c43  callvirt T0x2B00012E
0x189c48  stloc.s  4
0x189c4a  ldloca.s 4
0x189c4c  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x189c51  brfalse.s loc_189C5B
0x189c53  ldloca.s 4
0x189c55  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x189c5a  stloc.2
0x189c5b  ldloc.3
0x189c5c  brfalse.s loc_189C65
0x189c5e  ldloc.3
0x189c5f  unbox.any [mscorlib]System.Int32
0x189c64  stloc.2
0x189c65  ldarg.3
0x189c66  ldloc.2
0x189c67  mul
0x189c68  stloc.2
0x189c69  ldstr    aUpdatesemaphor_0// "UpdateSemaphore"
0x189c6e  ldarg.2
0x189c6f  ldstr    aMaxsharepointt_0// "MaxSharepointThreadsperUser"
0x189c74  ldloca.s 2
0x189c76  call     instance string [mscorlib]System.Int32::ToString()
0x189c7b  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogInformation(string EventName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string EventParamsKey, string EventParamsValue)
0x189c80  ldc.i4.0
0x189c81  ldloc.2
0x189c82  newobj   instance void [System]System.Threading.Semaphore::.ctor(int32, int32)
0x189c87  stloc.s  5
0x189c89  ldloc.s  5
0x189c8b  ldloc.2
0x189c8c  callvirt instance int32 [System]System.Threading.Semaphore::Release(int32)
0x189c91  pop
0x189c92  ldarg.1
0x189c93  ldloc.0
0x189c94  ldloc.s  5
0x189c96  callvirt instance void class [Microsoft.Crm]Microsoft.Crm.ThreadSafeDictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Threading.Semaphore>::Add(var<u1>, !!T0)
0x189c9b  ldloc.s  5
0x189c9d  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x189ca2  pop
0x189ca3  br.s     loc_189CB2
0x189ca5  ldarg.1
0x189ca6  ldloc.0
0x189ca7  callvirt instance var<u1> class [Microsoft.Crm]Microsoft.Crm.ThreadSafeDictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Threading.Semaphore>::get_Item(void)
0x189cac  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x189cb1  pop
0x189cb2  ldarg.0
0x189cb3  ldloc.1
0x189cb4  callvirt instance bool class [Microsoft.Crm]Microsoft.Crm.ThreadSafeDictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Threading.Semaphore>::ContainsKey(var<u1>)
0x189cb9  brtrue   loc_189D53
0x189cbe  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationSettingsProvider::get_Instance()
0x189cc3  ldloc.1
0x189cc4  ldstr    aMaxsharepointt_1// "MaxSharepointThreads"
0x189cc9  ldc.i4.s 0x3C
0x189ccb  ldstr    aUpdatesemaphor_0// "UpdateSemaphore"
0x189cd0  ldstr    aDA1SSrcCoreObj_49// "D:\\a\\1\\s\\src\\Core\\ObjectModel\\Se"...
0x189cd5  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationSettingsProvider::GetOrganizationSetting(valuetype [mscorlib]System.Guid, string, int32, string, string)
0x189cda  stloc.s  6
0x189cdc  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x189ce1  ldstr    aMaxsharepointt_2// "MaxSharepointThreadsperOrganisation"
0x189ce6  callvirt T0x2B00012E
0x189ceb  stloc.s  7
0x189ced  ldc.i4.s 0xA
0x189cef  stloc.s  8
0x189cf1  ldloca.s 7
0x189cf3  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x189cf8  brfalse.s loc_189D03
0x189cfa  ldloca.s 7
0x189cfc  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x189d01  stloc.s  8
0x189d03  ldloc.s  6
0x189d05  brfalse.s loc_189D10
0x189d07  ldloc.s  6
0x189d09  unbox.any [mscorlib]System.Int32
0x189d0e  stloc.s  8
0x189d10  ldarg.3
0x189d11  ldloc.s  8
0x189d13  mul
0x189d14  stloc.s  8
0x189d16  ldstr    aUpdatesemaphor_0// "UpdateSemaphore"
0x189d1b  ldarg.2
0x189d1c  ldstr    aMaxsharepointt_3// "MaxSharepointThreadsperOrganization"
0x189d21  ldloca.s 8
0x189d23  call     instance string [mscorlib]System.Int32::ToString()
0x189d28  call     void Microsoft.Crm.ObjectModel.SharePointTelemetryHelper::LogInformation(string EventName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string EventParamsKey, string EventParamsValue)
0x189d2d  ldc.i4.0
0x189d2e  ldloc.s  8
0x189d30  newobj   instance void [System]System.Threading.Semaphore::.ctor(int32, int32)
0x189d35  stloc.s  9
0x189d37  ldloc.s  9
0x189d39  ldloc.s  8
0x189d3b  callvirt instance int32 [System]System.Threading.Semaphore::Release(int32)
0x189d40  pop
0x189d41  ldarg.0
0x189d42  ldloc.1
0x189d43  ldloc.s  9
0x189d45  callvirt instance void class [Microsoft.Crm]Microsoft.Crm.ThreadSafeDictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Threading.Semaphore>::Add(var<u1>, !!T0)
0x189d4a  ldloc.s  9
0x189d4c  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x189d51  pop
0x189d52  ret
0x189d53  ldarg.0
0x189d54  ldloc.1
0x189d55  callvirt instance var<u1> class [Microsoft.Crm]Microsoft.Crm.ThreadSafeDictionary`2<valuetype [mscorlib]System.Guid, class [System]System.Threading.Semaphore>::get_Item(void)
0x189d5a  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x189d5f  pop
0x189d60  ret
```
