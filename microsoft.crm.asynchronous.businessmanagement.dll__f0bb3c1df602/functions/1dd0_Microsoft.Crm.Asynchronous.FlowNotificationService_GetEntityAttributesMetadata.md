# Microsoft.Crm.Asynchronous.FlowNotificationService::GetEntityAttributesMetadata

- ea: `0x1dd0`
- end: `0x1e0e`
- name: `Microsoft.Crm.Asynchronous.FlowNotificationService::GetEntityAttributesMetadata`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1990`

## callees

- `0x990`
- `0x1dd0`

## pseudocode

```c

```

## disassembly

```asm
0x1dd0  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::.ctor()
0x1dd5  stloc.0
0x1dd6  ldarg.0
0x1dd7  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata[] [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.EntityMetadata::get_Attributes()
0x1ddc  stloc.1
0x1ddd  ldc.i4.0
0x1dde  stloc.2
0x1ddf  br.s     loc_1E06
0x1de1  ldloc.1
0x1de2  ldloc.2
0x1de3  ldelem.ref
0x1de4  stloc.3
0x1de5  ldloc.3
0x1de6  call     bool Microsoft.Crm.Asynchronous.AttributeMetadataExtensions::IsVisible(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata attributeMetadata)
0x1deb  brfalse.s loc_1E02
0x1ded  ldloc.3
0x1dee  isinst   [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.MultiSelectPicklistAttributeMetadata
0x1df3  brtrue.s loc_1E02
0x1df5  ldloc.0
0x1df6  ldloc.3
0x1df7  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata::get_LogicalName()
0x1dfc  ldloc.3
0x1dfd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Metadata.AttributeMetadata>::Add(var<u1>, !!T0)
0x1e02  ldloc.2
0x1e03  ldc.i4.1
0x1e04  add
0x1e05  stloc.2
0x1e06  ldloc.2
0x1e07  ldloc.1
0x1e08  ldlen
0x1e09  conv.i4
0x1e0a  blt.s    loc_1DE1
0x1e0c  ldloc.0
0x1e0d  ret
```
