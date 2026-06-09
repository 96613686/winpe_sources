# Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::.ctor

- ea: `0x990`
- end: `0x9a9`
- name: `Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::.ctor`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3300`

## callees

- `0x2310`

## string_xrefs

- `0x997`: `localConfigStore`

## pseudocode

```c

```

## disassembly

```asm
0x990  ldarg.0
0x991  call     instance void Microsoft.Crm.Sandbox.SandboxMarshalByRefObject::.ctor()
0x996  ldarg.1
0x997  ldstr    aLocalconfigsto// "localConfigStore"
0x99c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9a1  ldarg.0
0x9a2  ldarg.1
0x9a3  stfld    class [Microsoft.Crm.Sandbox]Microsoft.Crm.Sandbox.IInternalConfigStore Microsoft.Crm.Sandbox.LocalConfigStoreWrapper::_localConfigStore
0x9a8  ret
```
