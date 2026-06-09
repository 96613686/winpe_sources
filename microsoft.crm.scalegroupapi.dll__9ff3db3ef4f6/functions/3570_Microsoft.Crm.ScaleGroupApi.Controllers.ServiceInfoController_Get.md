# Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::Get

- ea: `0x3570`
- end: `0x35b2`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::Get`
- size: `66`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x16d0`
- `0x16f0`
- `0x1710`
- `0x1720`

## pseudocode

```c

```

## disassembly

```asm
0x3570  newobj   instance void Microsoft.Crm.ScaleGroupApi.Models.SGServiceInfo::.ctor()
0x3575  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x357a  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x357f  stloc.0
0x3580  dup
0x3581  ldloc.0
0x3582  call     class [System]System.Diagnostics.FileVersionInfo [System]System.Diagnostics.FileVersionInfo::GetVersionInfo(string)
0x3587  callvirt instance string [System]System.Diagnostics.FileVersionInfo::get_ProductVersion()
0x358c  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGServiceInfo::set_BuildVersion(string value)
0x3591  dup
0x3592  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.Models.SGController[]> Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::_controllerList
0x3597  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.Models.SGController[]>::get_Value()
0x359c  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGServiceInfo::set_Controllers(class Microsoft.Crm.ScaleGroupApi.Models.SGController[] value)
0x35a1  dup
0x35a2  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.Models.SGModel[]> Microsoft.Crm.ScaleGroupApi.Controllers.ServiceInfoController::_modelList
0x35a7  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.Models.SGModel[]>::get_Value()
0x35ac  callvirt instance void Microsoft.Crm.ScaleGroupApi.Models.SGServiceInfo::set_Models(class Microsoft.Crm.ScaleGroupApi.Models.SGModel[] value)
0x35b1  ret
```
