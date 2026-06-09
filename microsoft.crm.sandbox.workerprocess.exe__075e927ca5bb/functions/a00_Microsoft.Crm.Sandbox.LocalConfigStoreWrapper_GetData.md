# Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::GetData

- ea: `0xa00`
- end: `0xa4f`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::GetData`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa00`

## string_xrefs

- `0xa23`: `PSS: Unhanlded Exception in LocalConfigStoreWrapper.GetData: {0}:{1}`

## pseudocode

```c

```

## disassembly

```asm
0xa00  ldc.i4.1
0xa01  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0xa06  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0xa0b  ldarg.0
0xa0c  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::_localConfigStore
0xa11  ldarg.1
0xa12  callvirt instance unsigned int8[] [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore::GetData(string)
0xa17  stloc.0
0xa18  leave.s  loc_A4D
0xa1a  stloc.1
0xa1b  ldloc.1
0xa1c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xa21  ldc.i4.s 0x1F
0xa23  ldstr    aPssUnhanldedEx_6// "PSS: Unhanlded Exception in LocalConfig"...
0xa28  ldc.i4.2
0xa29  newarr   [mscorlib]System.Object
0xa2e  dup
0xa2f  ldc.i4.0
0xa30  ldloc.1
0xa31  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa36  stelem.ref
0xa37  dup
0xa38  ldc.i4.1
0xa39  ldloc.1
0xa3a  callvirt instance string [mscorlib]System.Object::ToString()
0xa3f  stelem.ref
0xa40  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa45  rethrow
0xa47  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xa4c  endfinally
0xa4d  ldloc.0
0xa4e  ret
```
