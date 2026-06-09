# Microsoft.Crm.Metadata.AttributeService::ValidateAttributeRequiredLevelForUpdate

- ea: `0x22a10`
- end: `0x22af4`
- name: `Microsoft.Crm.Metadata.AttributeService::ValidateAttributeRequiredLevelForUpdate`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1ff00`

## callees

- `0x18490`
- `0x18570`
- `0x22a10`

## string_xrefs

- `0x22a63`: `Cannot update RequiredLevel of attribute {0} from SystemRequired`
- `0x22ac5`: `Cannot update RequiredLevel of attribute {0} to SystemRequired`

## pseudocode

```c

```

## disassembly

```asm
0x22a10  ldarg.0
0x22a11  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel> Microsoft.Crm.Metadata.AttributeInfo::get_RequiredLevel()
0x22a16  stloc.0
0x22a17  ldloca.s 0
0x22a19  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::get_HasValue()
0x22a1e  brfalse  loc_22AF3
0x22a23  ldnull
0x22a24  stloc.1
0x22a25  ldarg.0
0x22a26  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel> Microsoft.Crm.Metadata.AttributeInfo::get_RequiredLevel()
0x22a2b  stloc.0
0x22a2c  ldc.i4.1
0x22a2d  stloc.2
0x22a2e  ldloca.s 0
0x22a30  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::GetValueOrDefault()
0x22a35  ldloc.2
0x22a36  ceq
0x22a38  ldloca.s 0
0x22a3a  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::get_HasValue()
0x22a3f  and
0x22a40  brtrue.s loc_22A7F
0x22a42  ldarg.1
0x22a43  ldstr    aAttributerequi// "attributerequiredlevelid"
0x22a48  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22a4d  castclass [mscorlib]System.String
0x22a52  ldstr    aSystemrequired// "systemrequired"
0x22a57  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22a5c  brfalse.s loc_22A7F
0x22a5e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22a63  ldstr    aCannotUpdateRe// "Cannot update RequiredLevel of attribut"...
0x22a68  ldc.i4.1
0x22a69  newarr   [mscorlib]System.Object
0x22a6e  dup
0x22a6f  ldc.i4.0
0x22a70  ldarg.0
0x22a71  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x22a76  stelem.ref
0x22a77  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22a7c  stloc.1
0x22a7d  br.s     loc_22ADF
0x22a7f  ldarg.0
0x22a80  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel> Microsoft.Crm.Metadata.AttributeInfo::get_RequiredLevel()
0x22a85  stloc.0
0x22a86  ldc.i4.1
0x22a87  stloc.2
0x22a88  ldloca.s 0
0x22a8a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::GetValueOrDefault()
0x22a8f  ldloc.2
0x22a90  ceq
0x22a92  ldloca.s 0
0x22a94  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeRequiredLevel>::get_HasValue()
0x22a99  and
0x22a9a  brfalse.s loc_22ADF
0x22a9c  ldarg.1
0x22a9d  ldstr    aAttributerequi// "attributerequiredlevelid"
0x22aa2  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x22aa7  castclass [mscorlib]System.String
0x22aac  ldstr    aSystemrequired// "systemrequired"
0x22ab1  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x22ab6  brfalse.s loc_22ADF
0x22ab8  ldarg.2
0x22ab9  callvirt instance valuetype [Microsoft.Crm.Platform.Server]Microsoft.Crm.Platform.OperationContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_OperationContext()
0x22abe  brfalse.s loc_22ADF
0x22ac0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x22ac5  ldstr    aCannotUpdateRe_0// "Cannot update RequiredLevel of attribut"...
0x22aca  ldc.i4.1
0x22acb  newarr   [mscorlib]System.Object
0x22ad0  dup
0x22ad1  ldc.i4.0
0x22ad2  ldarg.0
0x22ad3  callvirt instance string Microsoft.Crm.Metadata.AttributeInfo::get_Name()
0x22ad8  stelem.ref
0x22ad9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x22ade  stloc.1
0x22adf  ldloc.1
0x22ae0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x22ae5  brtrue.s loc_22AF3
0x22ae7  ldloc.1
0x22ae8  ldc.i4   0x8004D293
0x22aed  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x22af2  throw
0x22af3  ret
```
