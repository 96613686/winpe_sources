# Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddPrivilegeProperties

- ea: `0x10810`
- end: `0x10872`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddPrivilegeProperties`
- size: `98`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x102a0`

## callees

- `0x10dc0`

## string_xrefs

- `0x10811`: `Privilege`
- `0x10816`: `privilege`
- `0x10821`: `privilegerowid`
- `0x10852`: `PrivilegeObjectTypeCode`
- `0x10857`: `privilegeobjecttypecode`
- `0x10862`: `privilegeobjecttypecoderowid`

## pseudocode

```c

```

## disassembly

```asm
0x10810  ldarg.0
0x10811  ldstr    aPrivilege// "Privilege"
0x10816  ldstr    aPrivilege_0// "privilege"
0x1081b  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x10820  dup
0x10821  ldstr    aPrivilegerowid// "privilegerowid"
0x10826  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1082b  dup
0x1082c  ldstr    aIsdiabledwheni// "isdiabledwhenintegrated"
0x10831  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10836  dup
0x10837  ldstr    aCanbeentityref// "canbeentityreference"
0x1083c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10841  dup
0x10842  ldstr    aCanbeparentent// "canbeparententityreference"
0x10847  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1084c  call     void Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddPropertiesForMetadataForMetadata(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string metadataEntityName, string componentName, class [mscorlib]System.Collections.Generic.List`1<string> ignoreColumnsList)
0x10851  ldarg.0
0x10852  ldstr    aPrivilegeobjec// "PrivilegeObjectTypeCode"
0x10857  ldstr    aPrivilegeobjec_0// "privilegeobjecttypecode"
0x1085c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x10861  dup
0x10862  ldstr    aPrivilegeobjec_1// "privilegeobjecttypecoderowid"
0x10867  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x1086c  call     void Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddPropertiesForMetadataForMetadata(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string metadataEntityName, string componentName, class [mscorlib]System.Collections.Generic.List`1<string> ignoreColumnsList)
0x10871  ret
```
