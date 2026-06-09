# Microsoft.Crm.BusinessEntities.BusinessProcessObject::HandleStateAndSecurityAttributes

- ea: `0x5ddd0`
- end: `0x5df06`
- name: `Microsoft.Crm.BusinessEntities.BusinessProcessObject::HandleStateAndSecurityAttributes`
- size: `310`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5c450`

## callees

- `0x51680`
- `0x51690`
- `0x5d550`
- `0x5ddd0`
- `0x5e290`
- `0x66ff0`

## string_xrefs

- `0x5dddd`: `IsInternalUpdate`
- `0x5ddef`: `IsInternalUpdate`

## pseudocode

```c

```

## disassembly

```asm
0x5ddd0  ldarg.s  4
0x5ddd2  ldc.i4.0
0x5ddd3  stind.i1
0x5ddd4  ldarg.3
0x5ddd5  ldc.i4.0
0x5ddd6  stind.i1
0x5ddd7  ldarg.2
0x5ddd8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5dddd  ldstr    aIsinternalupda// "IsInternalUpdate"
0x5dde2  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5dde7  brfalse.s loc_5DE00
0x5dde9  ldarg.2
0x5ddea  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5ddef  ldstr    aIsinternalupda// "IsInternalUpdate"
0x5ddf4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5ddf9  unbox.any [mscorlib]System.Boolean
0x5ddfe  br.s     loc_5DE01
0x5de00  ldc.i4.0
0x5de01  brfalse.s loc_5DE04
0x5de03  ret
0x5de04  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x5de09  ldstr    aIssetstate01// "IsSetState_{0}_{1}"
0x5de0e  ldc.i4.2
0x5de0f  newarr   [mscorlib]System.Object
0x5de14  dup
0x5de15  ldc.i4.0
0x5de16  ldarg.1
0x5de17  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5de1c  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_LogicalName()
0x5de21  stelem.ref
0x5de22  dup
0x5de23  ldc.i4.1
0x5de24  ldarg.1
0x5de25  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x5de2a  stelem.ref
0x5de2b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x5de30  stloc.0
0x5de31  ldarg.2
0x5de32  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5de37  ldloc.0
0x5de38  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5de3d  brfalse.s loc_5DE52
0x5de3f  ldarg.2
0x5de40  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5de45  ldloc.0
0x5de46  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::get_Item(void)
0x5de4b  unbox.any [mscorlib]System.Boolean
0x5de50  br.s     loc_5DE53
0x5de52  ldc.i4.0
0x5de53  brtrue.s loc_5DE9A
0x5de55  ldarg.1
0x5de56  ldarg.0
0x5de57  call     instance class Microsoft.Crm.Platform.Server.ISetStatePropertiesProvider Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_SetStatePropertiesProvider()
0x5de5c  callvirt instance string Microsoft.Crm.Platform.Server.ISetStatePropertiesProvider::get_StateAttributeName()
0x5de61  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x5de66  brtrue.s loc_5DE9A
0x5de68  ldarg.0
0x5de69  ldarg.1
0x5de6a  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0x5de6f  dup
0x5de70  ldarg.0
0x5de71  call     instance class Microsoft.Crm.Platform.Server.ISetStatePropertiesProvider Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_SetStatePropertiesProvider()
0x5de76  callvirt instance string Microsoft.Crm.Platform.Server.ISetStatePropertiesProvider::get_StateAttributeName()
0x5de7b  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x5de80  dup
0x5de81  ldarg.0
0x5de82  call     instance class Microsoft.Crm.Platform.Server.ISetStatePropertiesProvider Microsoft.Crm.BusinessEntities.BusinessProcessObject::get_SetStatePropertiesProvider()
0x5de87  callvirt instance string Microsoft.Crm.Platform.Server.ISetStatePropertiesProvider::get_StatusAttributeName()
0x5de8c  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x5de91  call     instance bool Microsoft.Crm.BusinessEntities.BusinessProcessObject::ClearAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [mscorlib]System.Collections.ObjectModel.Collection`1<string> attributes)
0x5de96  pop
0x5de97  ldarg.3
0x5de98  ldc.i4.1
0x5de99  stind.i1
0x5de9a  ldarg.2
0x5de9b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.Crm.BusinessEntities.ExecutionContext::get_InternalContextVariables()
0x5dea0  ldstr    aIscascadingass// "IsCascadingAssign"
0x5dea5  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::ContainsKey(var<u1>)
0x5deaa  brtrue.s loc_5DF05
0x5deac  ldarg.1
0x5dead  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Metadata()
0x5deb2  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsUnowned()
0x5deb7  brtrue.s loc_5DF05
0x5deb9  ldarg.1
0x5deba  ldstr    aOwnerid// "ownerid"
0x5debf  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x5dec4  brtrue.s loc_5DF05
0x5dec6  ldarg.1
0x5dec7  ldstr    aOwneridtype// "owneridtype"
0x5decc  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x5ded1  brtrue.s loc_5DF05
0x5ded3  ldarg.0
0x5ded4  ldarg.1
0x5ded5  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::.ctor()
0x5deda  dup
0x5dedb  ldstr    aOwnerid// "ownerid"
0x5dee0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x5dee5  dup
0x5dee6  ldstr    aOwneridtype// "owneridtype"
0x5deeb  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x5def0  dup
0x5def1  ldstr    aOwningbusiness// "owningbusinessunit"
0x5def6  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<string>::Add(var<u1>)
0x5defb  call     instance bool Microsoft.Crm.BusinessEntities.BusinessProcessObject::ClearAttributes(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [mscorlib]System.Collections.ObjectModel.Collection`1<string> attributes)
0x5df00  pop
0x5df01  ldarg.s  4
0x5df03  ldc.i4.1
0x5df04  stind.i1
0x5df05  ret
```
