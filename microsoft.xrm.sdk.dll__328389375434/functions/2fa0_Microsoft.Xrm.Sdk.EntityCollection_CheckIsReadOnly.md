# Microsoft.Xrm.Sdk.EntityCollection::CheckIsReadOnly

- ea: `0x2fa0`
- end: `0x2fb4`
- name: `Microsoft.Xrm.Sdk.EntityCollection::CheckIsReadOnly`
- size: `20`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2ea0`
- `0x2ec0`
- `0x2ee0`
- `0x2f00`
- `0x2f20`
- `0x2f40`
- `0x2f70`

## callees

- `0x2f80`
- `0x2fa0`

## string_xrefs

- `0x2fa8`: `The collection is read-only.`

## pseudocode

```c

```

## disassembly

```asm
0x2fa0  ldarg.0
0x2fa1  call     instance bool Microsoft.Xrm.Sdk.EntityCollection::get_IsReadOnly()
0x2fa6  brfalse.s loc_2FB3
0x2fa8  ldstr    aTheCollectionI// "The collection is read-only."
0x2fad  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2fb2  throw
0x2fb3  ret
```
