# Microsoft.Crm.Application.Platform.EntityProxy::ClearProcessRelatedFields

- ea: `0x5d610`
- end: `0x5d665`
- name: `Microsoft.Crm.Application.Platform.EntityProxy::ClearProcessRelatedFields`
- size: `85`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x5da00`
- `0x5dba0`

## callees

- `0x5be20`
- `0x5be40`
- `0x5d610`

## string_xrefs

- `0x5d611`: `processid`
- `0x5d61e`: `processid`
- `0x5d64c`: `traversedpath`
- `0x5d659`: `traversedpath`

## pseudocode

```c

```

## disassembly

```asm
0x5d610  ldarg.0
0x5d611  ldstr    aProcessid// "processid"
0x5d616  call     instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5d61b  brfalse.s loc_5D632
0x5d61d  ldarg.0
0x5d61e  ldstr    aProcessid// "processid"
0x5d623  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x5d628  box      [mscorlib]System.Guid
0x5d62d  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x5d632  ldarg.0
0x5d633  ldstr    aStageid// "stageid"
0x5d638  call     instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5d63d  brfalse.s loc_5D64B
0x5d63f  ldarg.0
0x5d640  ldstr    aStageid// "stageid"
0x5d645  ldnull
0x5d646  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x5d64b  ldarg.0
0x5d64c  ldstr    aTraversedpath// "traversedpath"
0x5d651  call     instance object Microsoft.Crm.Application.Platform.EntityBase::get_Item(string name)
0x5d656  brfalse.s loc_5D664
0x5d658  ldarg.0
0x5d659  ldstr    aTraversedpath// "traversedpath"
0x5d65e  ldnull
0x5d65f  call     instance void Microsoft.Crm.Application.Platform.EntityBase::set_Item(string name, object value)
0x5d664  ret
```
