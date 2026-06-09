# Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities

- ea: `0x93b0`
- end: `0x93ca`
- name: `Microsoft.Xrm.Sdk.Query.LinkEntity::get_LinkEntities`
- size: `26`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x9450`
- `0x9cb0`
- `0xa560`
- `0x24c30`

## callees

- `0x93b0`

## pseudocode

```c

```

## disassembly

```asm
0x93b0  ldarg.0
0x93b1  ldfld    class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Query.LinkEntity::_linkEntities
0x93b6  brtrue.s loc_93C3
0x93b8  ldarg.0
0x93b9  newobj   instance void class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity>::.ctor()
0x93be  stfld    class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Query.LinkEntity::_linkEntities
0x93c3  ldarg.0
0x93c4  ldfld    class Microsoft.Xrm.Sdk.DataCollection`1<class Microsoft.Xrm.Sdk.Query.LinkEntity> Microsoft.Xrm.Sdk.Query.LinkEntity::_linkEntities
0x93c9  ret
```
