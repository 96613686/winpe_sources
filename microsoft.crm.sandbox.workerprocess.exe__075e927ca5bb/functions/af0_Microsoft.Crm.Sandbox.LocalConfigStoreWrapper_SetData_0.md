# Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::SetData_0

- ea: `0xaf0`
- end: `0xb3e`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::SetData_0`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xaf0`

## string_xrefs

- `0xb13`: `PSS: Unhanlded Exception in LocalConfigStoreWrapper.SetData: {0}:{1}`

## pseudocode

```c

```

## disassembly

```asm
0xaf0  ldc.i4.1
0xaf1  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0xaf6  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0xafb  ldarg.0
0xafc  ldfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::_localConfigStore
0xb01  ldarg.1
0xb02  ldarg.2
0xb03  callvirt instance void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore::SetData(string, unsigned int8[])
0xb08  leave.s  loc_B3D
0xb0a  stloc.0
0xb0b  ldloc.0
0xb0c  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xb11  ldc.i4.s 0x1F
0xb13  ldstr    aPssUnhanldedEx_9// "PSS: Unhanlded Exception in LocalConfig"...
0xb18  ldc.i4.2
0xb19  newarr   [mscorlib]System.Object
0xb1e  dup
0xb1f  ldc.i4.0
0xb20  ldloc.0
0xb21  callvirt instance string [mscorlib]System.Exception::get_Message()
0xb26  stelem.ref
0xb27  dup
0xb28  ldc.i4.1
0xb29  ldloc.0
0xb2a  callvirt instance string [mscorlib]System.Object::ToString()
0xb2f  stelem.ref
0xb30  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xb35  rethrow
0xb37  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xb3c  endfinally
0xb3d  ret
```
