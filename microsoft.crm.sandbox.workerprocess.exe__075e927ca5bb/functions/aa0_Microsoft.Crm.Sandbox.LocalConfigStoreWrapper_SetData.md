# Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::SetData

- ea: `0xaa0`
- end: `0xaed`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::SetData`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xaa0`

## string_xrefs

- `0xac2`: `PSS: Unhanlded Exception in LocalConfigStoreWrapper.SetData_Dictionary: {0}:{1}`

## pseudocode

```c

```

## disassembly

```asm
0xaa0  ldc.i4.1
0xaa1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0xaa6  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0xaab  ldarg.0
0xaac  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::_localConfigStore
0xab1  ldarg.1
0xab2  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore::SetData(class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]>)
0xab7  leave.s  loc_AEC
0xab9  stloc.0
0xaba  ldloc.0
0xabb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xac0  ldc.i4.s 0x1F
0xac2  ldstr    aPssUnhanldedEx_8// "PSS: Unhanlded Exception in LocalConfig"...
0xac7  ldc.i4.2
0xac8  newarr   [mscorlib]System.Object
0xacd  dup
0xace  ldc.i4.0
0xacf  ldloc.0
0xad0  callvirt instance string [mscorlib]System.Exception::get_Message()
0xad5  stelem.ref
0xad6  dup
0xad7  ldc.i4.1
0xad8  ldloc.0
0xad9  callvirt instance string [mscorlib]System.Object::ToString()
0xade  stelem.ref
0xadf  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xae4  rethrow
0xae6  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xaeb  endfinally
0xaec  ret
```
