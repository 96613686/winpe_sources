# Microsoft.Crm.Metadata.CustomizationSecurityCache::.cctor

- ea: `0x5a960`
- end: `0x5aa45`
- name: `Microsoft.Crm.Metadata.CustomizationSecurityCache::.cctor`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x5a9fa`: `prvReadSqlEncryptionKey`
- `0x5a971`: `prvReadEntity`
- `0x5a991`: `prvReadAttribute`
- `0x5a9b2`: `prvReadRelationship`
- `0x5a9d6`: `prvReadOptionSet`
- `0x5a9f1`: `prvReadCustomization`
- `0x5aa1e`: `prvReadEntityKey`
- `0x5a989`: `prvCreateAttribute`
- `0x5a999`: `prvWriteAttribute`
- `0x5a9a1`: `prvDeleteAttribute`
- `0x5aa15`: `prvCreateEntityKey`
- `0x5aa27`: `prvDeleteEntityKey`
- `0x5a969`: `prvCreateEntity`
- `0x5a979`: `prvWriteEntity`
- `0x5a981`: `prvDeleteEntity`
- `0x5a9a9`: `prvCreateRelationship`
- `0x5a9df`: `prvWriteOptionSet`
- `0x5a9cd`: `prvCreateOptionSet`
- `0x5a9e8`: `prvDeleteOptionSet`
- `0x5a9c4`: `prvDeleteRelationship`
- `0x5a9bb`: `prvWriteRelationship`

## pseudocode

```c

```

## disassembly

```asm
0x5a960  ldc.i4.s 0x17
0x5a962  newarr   [mscorlib]System.String
0x5a967  dup
0x5a968  ldc.i4.0
0x5a969  ldstr    aPrvcreateentit_0// "prvCreateEntity"
0x5a96e  stelem.ref
0x5a96f  dup
0x5a970  ldc.i4.1
0x5a971  ldstr    aPrvreadentity// "prvReadEntity"
0x5a976  stelem.ref
0x5a977  dup
0x5a978  ldc.i4.2
0x5a979  ldstr    aPrvwriteentity// "prvWriteEntity"
0x5a97e  stelem.ref
0x5a97f  dup
0x5a980  ldc.i4.3
0x5a981  ldstr    aPrvdeleteentit_0// "prvDeleteEntity"
0x5a986  stelem.ref
0x5a987  dup
0x5a988  ldc.i4.4
0x5a989  ldstr    aPrvcreateattri// "prvCreateAttribute"
0x5a98e  stelem.ref
0x5a98f  dup
0x5a990  ldc.i4.5
0x5a991  ldstr    aPrvreadattribu// "prvReadAttribute"
0x5a996  stelem.ref
0x5a997  dup
0x5a998  ldc.i4.6
0x5a999  ldstr    aPrvwriteattrib// "prvWriteAttribute"
0x5a99e  stelem.ref
0x5a99f  dup
0x5a9a0  ldc.i4.7
0x5a9a1  ldstr    aPrvdeleteattri// "prvDeleteAttribute"
0x5a9a6  stelem.ref
0x5a9a7  dup
0x5a9a8  ldc.i4.8
0x5a9a9  ldstr    aPrvcreaterelat// "prvCreateRelationship"
0x5a9ae  stelem.ref
0x5a9af  dup
0x5a9b0  ldc.i4.s 9
0x5a9b2  ldstr    aPrvreadrelatio// "prvReadRelationship"
0x5a9b7  stelem.ref
0x5a9b8  dup
0x5a9b9  ldc.i4.s 0xA
0x5a9bb  ldstr    aPrvwriterelati// "prvWriteRelationship"
0x5a9c0  stelem.ref
0x5a9c1  dup
0x5a9c2  ldc.i4.s 0xB
0x5a9c4  ldstr    aPrvdeleterelat// "prvDeleteRelationship"
0x5a9c9  stelem.ref
0x5a9ca  dup
0x5a9cb  ldc.i4.s 0xC
0x5a9cd  ldstr    aPrvcreateoptio// "prvCreateOptionSet"
0x5a9d2  stelem.ref
0x5a9d3  dup
0x5a9d4  ldc.i4.s 0xD
0x5a9d6  ldstr    aPrvreadoptions// "prvReadOptionSet"
0x5a9db  stelem.ref
0x5a9dc  dup
0x5a9dd  ldc.i4.s 0xE
0x5a9df  ldstr    aPrvwriteoption// "prvWriteOptionSet"
0x5a9e4  stelem.ref
0x5a9e5  dup
0x5a9e6  ldc.i4.s 0xF
0x5a9e8  ldstr    aPrvdeleteoptio// "prvDeleteOptionSet"
0x5a9ed  stelem.ref
0x5a9ee  dup
0x5a9ef  ldc.i4.s 0x10
0x5a9f1  ldstr    aPrvreadcustomi// "prvReadCustomization"
0x5a9f6  stelem.ref
0x5a9f7  dup
0x5a9f8  ldc.i4.s 0x11
0x5a9fa  ldstr    aPrvreadsqlencr// "prvReadSqlEncryptionKey"
0x5a9ff  stelem.ref
0x5aa00  dup
0x5aa01  ldc.i4.s 0x12
0x5aa03  ldstr    aPrvrestoresqle// "prvRestoreSqlEncryptionKey"
0x5aa08  stelem.ref
0x5aa09  dup
0x5aa0a  ldc.i4.s 0x13
0x5aa0c  ldstr    aPrvchangesqlen// "prvChangeSqlEncryptionKey"
0x5aa11  stelem.ref
0x5aa12  dup
0x5aa13  ldc.i4.s 0x14
0x5aa15  ldstr    aPrvcreateentit// "prvCreateEntityKey"
0x5aa1a  stelem.ref
0x5aa1b  dup
0x5aa1c  ldc.i4.s 0x15
0x5aa1e  ldstr    aPrvreadentityk// "prvReadEntityKey"
0x5aa23  stelem.ref
0x5aa24  dup
0x5aa25  ldc.i4.s 0x16
0x5aa27  ldstr    aPrvdeleteentit// "prvDeleteEntityKey"
0x5aa2c  stelem.ref
0x5aa2d  stsfld   string[] Microsoft.Crm.Metadata.CustomizationSecurityCache::_customizationPrivilegeNames
0x5aa32  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid>::.ctor()
0x5aa37  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.Metadata.CustomizationSecurityCache::_customizationPrivileges
0x5aa3c  ldc.i4.0
0x5aa3d  volatile.
0x5aa3f  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool Microsoft.Crm.Metadata.CustomizationSecurityCache::_arePrivilegesLoaded
0x5aa44  ret
```
