# Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TraceErrorForSetOrganizationResources

- ea: `0x135d0`
- end: `0x136a9`
- name: `Microsoft.Crm.CrmLive.Services.ServiceInstanceService::TraceErrorForSetOrganizationResources`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x13350`

## callees

- `0x12790`
- `0x127b0`
- `0x127d0`
- `0x127f0`
- `0x12810`
- `0x12850`
- `0x135d0`

## string_xrefs

- `0x135da`: `SetOrganizationResources failed for Deprovision with the old service component -- could be ignored.`
- `0x135eb`: `Old ServiceComponentId: '{0}'\nNew ServiceComponentId: '{1}'\n`
- `0x13622`: `Id: '{0}'\nOrganizationId: '{1}'\nUserPuid: '{2}'\nServiceInstanceId: '{3}'\nServiceComponentId: '{4}'\nOld Status: '{5}'\nException: {6}\n`

## pseudocode

```c

```

## disassembly

```asm
0x135d0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x135d5  stloc.0
0x135d6  ldarg.3
0x135d7  brfalse.s loc_13610
0x135d9  ldloc.0
0x135da  ldstr    aSetorganizatio_1// "SetOrganizationResources failed for Dep"...
0x135df  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x135e4  pop
0x135e5  ldloc.0
0x135e6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x135eb  ldstr    aOldServicecomp// "Old ServiceComponentId: '{0}'\nNew Serv"...
0x135f0  ldc.i4.2
0x135f1  newarr   [mscorlib]System.Object
0x135f6  dup
0x135f7  ldc.i4.0
0x135f8  ldarg.2
0x135f9  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceComponentId()
0x135fe  stelem.ref
0x135ff  dup
0x13600  ldc.i4.1
0x13601  ldarg.3
0x13602  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceComponentId()
0x13607  stelem.ref
0x13608  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x1360d  pop
0x1360e  br.s     loc_1361C
0x13610  ldloc.0
0x13611  ldstr    aSetorganizatio_2// "SetOrganizationResources failed for Dep"...
0x13616  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1361b  pop
0x1361c  ldloc.0
0x1361d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13622  ldstr    aId0Organizatio// "Id: '{0}'\nOrganizationId: '{1}'\nUserP"...
0x13627  ldc.i4.7
0x13628  newarr   [mscorlib]System.Object
0x1362d  dup
0x1362e  ldc.i4.0
0x1362f  ldarg.1
0x13630  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_Id()
0x13635  box      [mscorlib]System.Guid
0x1363a  stelem.ref
0x1363b  dup
0x1363c  ldc.i4.1
0x1363d  ldarg.1
0x1363e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_OrganizationId()
0x13643  box      [mscorlib]System.Guid
0x13648  stelem.ref
0x13649  dup
0x1364a  ldc.i4.2
0x1364b  ldarg.1
0x1364c  callvirt instance class [Microsoft.Crm.Core.Extensions]Microsoft.Crm.CrmLive.Puid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_UserPuid()
0x13651  stelem.ref
0x13652  dup
0x13653  ldc.i4.3
0x13654  ldarg.1
0x13655  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceInstanceId()
0x1365a  stelem.ref
0x1365b  dup
0x1365c  ldc.i4.4
0x1365d  ldarg.1
0x1365e  callvirt instance string Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceComponentId()
0x13663  stelem.ref
0x13664  dup
0x13665  ldc.i4.5
0x13666  ldarg.2
0x13667  callvirt instance valuetype [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus Microsoft.Crm.CrmLive.Services.ServiceInstance::get_ServiceInstanceStatus()
0x1366c  box      [Microsoft.Crm.Core]Microsoft.Crm.Config.Wrapper.ServiceInstanceStatus
0x13671  stelem.ref
0x13672  dup
0x13673  ldc.i4.6
0x13674  ldarg.0
0x13675  callvirt instance string [mscorlib]System.Exception::get_Message()
0x1367a  stelem.ref
0x1367b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0x13680  pop
0x13681  ldloc.0
0x13682  ldarg.0
0x13683  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x13688  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x1368d  pop
0x1368e  ldnull
0x1368f  ldarg.1
0x13690  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.CrmLive.Services.ServiceInstance::get_OrganizationId()
0x13695  ldc.i4.s 0xF
0x13697  ldloc.0
0x13698  callvirt instance string [mscorlib]System.Object::ToString()
0x1369d  ldc.i4.0
0x1369e  newarr   [mscorlib]System.Object
0x136a3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x136a8  ret
```
