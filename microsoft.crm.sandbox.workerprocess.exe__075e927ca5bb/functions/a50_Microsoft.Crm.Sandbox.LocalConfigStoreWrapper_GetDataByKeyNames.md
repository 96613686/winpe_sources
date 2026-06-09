# Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::GetDataByKeyNames

- ea: `0xa50`
- end: `0xa9f`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::GetDataByKeyNames`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa50`

## string_xrefs

- `0xa73`: `PSS: Unhanlded Exception in LocalConfigStoreWrapper.GetDataByKeyNames: {0}:{1}`

## pseudocode

```c

```

## disassembly

```asm
0xa50  ldc.i4.1
0xa51  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0xa56  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0xa5b  ldarg.0
0xa5c  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::_localConfigStore
0xa61  ldarg.1
0xa62  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, unsigned int8[]> [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore::GetDataByKeyNames(class [mscorlib]System.Collections.Generic.List`1<string>)
0xa67  stloc.0
0xa68  leave.s  loc_A9D
0xa6a  stloc.1
0xa6b  ldloc.1
0xa6c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xa71  ldc.i4.s 0x1F
0xa73  ldstr    aPssUnhanldedEx_7// "PSS: Unhanlded Exception in LocalConfig"...
0xa78  ldc.i4.2
0xa79  newarr   [mscorlib]System.Object
0xa7e  dup
0xa7f  ldc.i4.0
0xa80  ldloc.1
0xa81  callvirt instance string [mscorlib]System.Exception::get_Message()
0xa86  stelem.ref
0xa87  dup
0xa88  ldc.i4.1
0xa89  ldloc.1
0xa8a  callvirt instance string [mscorlib]System.Object::ToString()
0xa8f  stelem.ref
0xa90  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xa95  rethrow
0xa97  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xa9c  endfinally
0xa9d  ldloc.0
0xa9e  ret
```
