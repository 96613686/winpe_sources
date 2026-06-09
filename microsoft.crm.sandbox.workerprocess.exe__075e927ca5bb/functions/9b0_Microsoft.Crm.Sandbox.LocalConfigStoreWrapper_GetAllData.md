# Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::GetAllData

- ea: `0x9b0`
- end: `0x9fe`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::GetAllData`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x9b0`

## string_xrefs

- `0x9d2`: `PSS: Unhanlded Exception in LocalConfigStoreWrapper.GetAllData: {0}:{1}`

## pseudocode

```c

```

## disassembly

```asm
0x9b0  ldc.i4.1
0x9b1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0x9b6  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0x9bb  ldarg.0
0x9bc  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::_localConfigStore
0x9c1  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore::GetAllData()
0x9c6  stloc.0
0x9c7  leave.s  loc_9FC
0x9c9  stloc.1
0x9ca  ldloc.1
0x9cb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x9d0  ldc.i4.s 0x1F
0x9d2  ldstr    aPssUnhanldedEx_5// "PSS: Unhanlded Exception in LocalConfig"...
0x9d7  ldc.i4.2
0x9d8  newarr   [mscorlib]System.Object
0x9dd  dup
0x9de  ldc.i4.0
0x9df  ldloc.1
0x9e0  callvirt instance string [mscorlib]System.Exception::get_Message()
0x9e5  stelem.ref
0x9e6  dup
0x9e7  ldc.i4.1
0x9e8  ldloc.1
0x9e9  callvirt instance string [mscorlib]System.Object::ToString()
0x9ee  stelem.ref
0x9ef  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9f4  rethrow
0x9f6  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0x9fb  endfinally
0x9fc  ldloc.0
0x9fd  ret
```
