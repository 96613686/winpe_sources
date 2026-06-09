# Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddDialogSystemFormProperties

- ea: `0x10a00`
- end: `0x10abb`
- name: `Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddDialogSystemFormProperties`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x102a0`

## callees

- `0x10d60`

## string_xrefs

- `0x10a59`: `formxmlmanaged`
- `0x10a17`: `formxml`
- `0x10a90`: `formxml`
- `0x10a64`: `componentState`

## pseudocode

```c

```

## disassembly

```asm
0x10a00  ldarg.0
0x10a01  ldstr    aSystemform_0// "SystemForm"
0x10a06  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x10a0b  dup
0x10a0c  ldstr    aFormidunique// "formidunique"
0x10a11  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a16  dup
0x10a17  ldstr    aFormxml_0// "formxml"
0x10a1c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a21  dup
0x10a22  ldstr    aType_0// "type"
0x10a27  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a2c  dup
0x10a2d  ldstr    aObjecttypecode_0// "objecttypecode"
0x10a32  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a37  dup
0x10a38  ldstr    aFormpresentati// "formpresentation"
0x10a3d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a42  dup
0x10a43  ldstr    aFormactivation// "formactivationstate"
0x10a48  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a4d  dup
0x10a4e  ldstr    aIsairmerged// "isairmerged"
0x10a53  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a58  dup
0x10a59  ldstr    aFormxmlmanaged// "formxmlmanaged"
0x10a5e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a63  dup
0x10a64  ldstr    aComponentstate// "componentState"
0x10a69  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a6e  dup
0x10a6f  ldstr    aObjecttypecode_0// "objecttypecode"
0x10a74  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a79  dup
0x10a7a  ldstr    aAncestorformid// "ancestorformid"
0x10a7f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a84  dup
0x10a85  ldstr    aType_0// "type"
0x10a8a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a8f  dup
0x10a90  ldstr    aFormxml_0// "formxml"
0x10a95  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10a9a  dup
0x10a9b  ldstr    aIsdefault// "isdefault"
0x10aa0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10aa5  dup
0x10aa6  ldstr    aPublishedon// "publishedon"
0x10aab  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x10ab0  ldstr    aDialogproperti// "DialogProperties"
0x10ab5  call     void Microsoft.Crm.Tools.ImportExportPublish.FirstPartyComponentPropertiesProvider::AddPropertiesForMetadata(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, string entity, class [mscorlib]System.Collections.Generic.List`1<string> ignoreColumnsList, string componentName)
0x10aba  ret
```
