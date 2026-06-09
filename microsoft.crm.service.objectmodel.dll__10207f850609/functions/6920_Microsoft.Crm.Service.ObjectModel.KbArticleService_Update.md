# Microsoft.Crm.Service.ObjectModel.KbArticleService::Update

- ea: `0x6920`
- end: `0x6a8a`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleService::Update`
- size: `362`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x6920`
- `0x73c0`

## string_xrefs

- `0x6974`: `kbarticletemplateid`

## pseudocode

```c

```

## disassembly

```asm
0x6920  ldarg.1
0x6921  ldstr    aEntity// "entity"
0x6926  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x692b  ldarg.2
0x692c  ldstr    aContext// "context"
0x6931  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x6936  ldc.i4.1
0x6937  newarr   [mscorlib]System.String
0x693c  dup
0x693d  ldc.i4.0
0x693e  ldstr    aStatecode// "statecode"
0x6943  stelem.ref
0x6944  stloc.0
0x6945  ldnull
0x6946  stloc.1
0x6947  ldloca.s 2
0x6949  initobj  valuetype [mscorlib]System.Nullable`1<int32>
0x694f  ldarg.1
0x6950  ldstr    aStatecode// "statecode"
0x6955  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::IsAttributeNull(string)
0x695a  brtrue.s loc_6973
0x695c  ldloca.s 2
0x695e  ldarg.1
0x695f  ldstr    aStatecode// "statecode"
0x6964  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Item(string)
0x6969  unbox.any [mscorlib]System.Int32
0x696e  call     instance void valuetype [mscorlib]System.Nullable`1<int32>::.ctor(var<u1>)
0x6973  ldarg.1
0x6974  ldstr    aKbarticletempl// "kbarticletemplateid"
0x6979  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::ClearAttribute(string)
0x697e  ldarg.1
0x697f  ldstr    aLanguagecode// "languagecode"
0x6984  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::ClearAttribute(string)
0x6989  ldarg.2
0x698a  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x698f  stloc.s  4
0x6991  ldarg.0
0x6992  ldarg.1
0x6993  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_PrimaryKey()
0x6998  unbox.any [mscorlib]System.Guid
0x699d  ldloc.0
0x699e  ldarg.2
0x699f  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.KbArticleService::GetKbArticle(valuetype [mscorlib]System.Guid kbArticleId, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x69a4  stloc.1
0x69a5  leave.s  loc_69B3
0x69a7  ldloc.s  4
0x69a9  brfalse.s loc_69B2
0x69ab  ldloc.s  4
0x69ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69b2  endfinally
0x69b3  ldloca.s 2
0x69b5  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x69ba  brtrue.s loc_69BF
0x69bc  ldc.i4.1
0x69bd  br.s     loc_69DA
0x69bf  ldloc.2
0x69c0  stloc.s  5
0x69c2  ldc.i4.3
0x69c3  stloc.s  6
0x69c5  ldloca.s 5
0x69c7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::GetValueOrDefault()
0x69cc  ldloc.s  6
0x69ce  beq.s    loc_69D3
0x69d0  ldc.i4.0
0x69d1  br.s     loc_69DA
0x69d3  ldloca.s 5
0x69d5  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x69da  stloc.3
0x69db  ldloc.1
0x69dc  ldstr    aStatecode// "statecode"
0x69e1  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x69e6  unbox.any [mscorlib]System.Int32
0x69eb  ldc.i4.3
0x69ec  ceq
0x69ee  ldloc.3
0x69ef  and
0x69f0  brfalse  loc_6A81
0x69f5  ldc.i4.1
0x69f6  stloc.s  7
0x69f8  ldarg.1
0x69f9  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IAttributeInfoCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity::get_Attributes()
0x69fe  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x6a03  stloc.s  8
0x6a05  br.s     loc_6A48
0x6a07  ldloc.s  8
0x6a09  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x6a0e  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfo
0x6a13  stloc.s  9
0x6a15  ldloc.s  9
0x6a17  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Metadata()
0x6a1c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsPrimaryKey()
0x6a21  brtrue.s loc_6A48
0x6a23  ldloc.s  9
0x6a25  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Metadata()
0x6a2a  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsCustomField()
0x6a2f  brfalse.s loc_6A45
0x6a31  ldloc.s  9
0x6a33  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.AttributeInfoBase::get_Metadata()
0x6a38  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x6a3d  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x6a42  ldc.i4.7
0x6a43  beq.s    loc_6A48
0x6a45  ldc.i4.0
0x6a46  stloc.s  7
0x6a48  ldloc.s  8
0x6a4a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x6a4f  brtrue.s loc_6A07
0x6a51  leave.s  loc_6A68
0x6a53  ldloc.s  8
0x6a55  isinst   [mscorlib]System.IDisposable
0x6a5a  stloc.s  0xA
0x6a5c  ldloc.s  0xA
0x6a5e  brfalse.s loc_6A67
0x6a60  ldloc.s  0xA
0x6a62  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6a67  endfinally
0x6a68  ldloc.s  7
0x6a6a  brtrue.s loc_6A81
0x6a6c  ldc.i4   0x800404FE
0x6a71  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x6a76  ldc.i4   0x800404FE
0x6a7b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6a80  throw
0x6a81  ldarg.0
0x6a82  ldarg.1
0x6a83  ldarg.2
0x6a84  call     instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6a89  ret
```
