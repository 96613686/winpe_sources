# Microsoft.Crm.Sandbox.SandboxOrganizationService::Stop

- ea: `0x28e0`
- end: `0x2903`
- name: `Microsoft.Crm.Sandbox.SandboxOrganizationService::Stop`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x45f0`
- `0x4720`

## string_xrefs

- `0x28e7`: `SandboxOrganizationService.Stop`

## pseudocode

```c

```

## disassembly

```asm
0x28e0  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x28e5  ldc.i4.s 0x26
0x28e7  ldstr    aSandboxorganiz_15// "SandboxOrganizationService.Stop"
0x28ec  ldc.i4.0
0x28ed  newarr   [mscorlib]System.Object
0x28f2  call     void [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x28f7  call     class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<var<u1>> class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<class Microsoft.Crm.Sandbox.SandboxSdkClient>::get_Instance()
0x28fc  ldc.i4.1
0x28fd  callvirt instance void class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.SandboxSdkClientCache`1<class Microsoft.Crm.Sandbox.SandboxSdkClient>::set_Shutdown(bool)
0x2902  ret
```
