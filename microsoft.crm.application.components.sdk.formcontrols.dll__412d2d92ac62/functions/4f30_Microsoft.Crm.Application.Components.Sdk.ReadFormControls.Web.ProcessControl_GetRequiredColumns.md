# Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetRequiredColumns

- ea: `0x4f30`
- end: `0x4fb4`
- name: `Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetRequiredColumns`
- size: `132`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x4b60`
- `0x4f30`
- `0x4fc0`
- `0x57f0`

## string_xrefs

- `0x4fa8`: `processid`
- `0x4f9d`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x4f30  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x4f35  stloc.0
0x4f36  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetCurrentEntityId()
0x4f3b  stloc.1
0x4f3c  ldarg.0
0x4f3d  ldloc.1
0x4f3e  ldarg.1
0x4f3f  call     instance void Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::InitializeProcess(valuetype [mscorlib]System.Guid entityId, int32 entityTypeCode)
0x4f44  ldarg.0
0x4f45  ldfld    class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.WorkflowStep Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::Process
0x4f4a  brtrue.s loc_4F4E
0x4f4c  ldloc.0
0x4f4d  ret
0x4f4e  ldarg.0
0x4f4f  ldarg.1
0x4f50  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor> Microsoft.Crm.Application.Components.Sdk.ReadFormControls.Web.ProcessControl::GetRequiredControlDescriptors(int32 entityTypeCode)
0x4f55  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::GetEnumerator()
0x4f5a  stloc.2
0x4f5b  br.s     loc_4F7D
0x4f5d  ldloc.2
0x4f5e  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor>::get_Current()
0x4f63  stloc.3
0x4f64  ldloc.3
0x4f65  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x4f6a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4f6f  brtrue.s loc_4F7D
0x4f71  ldloc.0
0x4f72  ldloc.3
0x4f73  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ControlDescriptor::get_DataFieldName()
0x4f78  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4f7d  ldloc.2
0x4f7e  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4f83  brtrue.s loc_4F5D
0x4f85  leave.s  loc_4F91
0x4f87  ldloc.2
0x4f88  brfalse.s loc_4F90
0x4f8a  ldloc.2
0x4f8b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4f90  endfinally
0x4f91  ldloc.0
0x4f92  ldstr    aStageid// "stageid"
0x4f97  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4f9c  ldloc.0
0x4f9d  ldstr    aTraversedpath// "traversedpath"
0x4fa2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4fa7  ldloc.0
0x4fa8  ldstr    aProcessid// "processid"
0x4fad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x4fb2  ldloc.0
0x4fb3  ret
```
