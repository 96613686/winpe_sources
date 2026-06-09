# Microsoft.Crm.Common.InterfaceService::Get

- ea: `0x880`
- end: `0x8b4`
- name: `Microsoft.Crm.Common.InterfaceService::Get`
- size: `52`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x880`

## string_xrefs

- `0x890`: `Service of type [`

## pseudocode

```c

```

## disassembly

```asm
0x880  call     T0x2B000001
0x885  stloc.0
0x886  ldloc.0
0x887  box      mvar<u1>
0x88c  brfalse.s loc_890
0x88e  ldloc.0
0x88f  ret
0x890  ldstr    aServiceOfType// "Service of type ["
0x895  ldtoken  mvar<u1>
0x89a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x89f  callvirt instance string [mscorlib]System.Type::get_FullName()
0x8a4  ldstr    aWasNotDefined// "] was not defined"
0x8a9  call     string [mscorlib]System.String::Concat(string, string, string)
0x8ae  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8b3  throw
```
