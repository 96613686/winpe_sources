# Microsoft.Crm.Service.ObjectModel.KbArticleService::SetState

- ea: `0x6b10`
- end: `0x6c04`
- name: `Microsoft.Crm.Service.ObjectModel.KbArticleService::SetState`
- size: `244`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x6b10`
- `0x6d60`
- `0x6e20`
- `0x7170`
- `0x7340`
- `0x73c0`

## string_xrefs

- `0x6b20`: `kbarticletemplateid`
- `0x6b28`: `articlexml`

## pseudocode

```c

```

## disassembly

```asm
0x6b10  ldc.i4.8
0x6b11  newarr   [mscorlib]System.String
0x6b16  dup
0x6b17  ldc.i4.0
0x6b18  ldstr    aStatecode// "statecode"
0x6b1d  stelem.ref
0x6b1e  dup
0x6b1f  ldc.i4.1
0x6b20  ldstr    aKbarticletempl// "kbarticletemplateid"
0x6b25  stelem.ref
0x6b26  dup
0x6b27  ldc.i4.2
0x6b28  ldstr    aArticlexml// "articlexml"
0x6b2d  stelem.ref
0x6b2e  dup
0x6b2f  ldc.i4.3
0x6b30  ldstr    aTitle// "title"
0x6b35  stelem.ref
0x6b36  dup
0x6b37  ldc.i4.4
0x6b38  ldstr    aNumber// "number"
0x6b3d  stelem.ref
0x6b3e  dup
0x6b3f  ldc.i4.5
0x6b40  ldstr    aKeywords// "keywords"
0x6b45  stelem.ref
0x6b46  dup
0x6b47  ldc.i4.6
0x6b48  ldstr    aSubjectid// "subjectid"
0x6b4d  stelem.ref
0x6b4e  dup
0x6b4f  ldc.i4.7
0x6b50  ldstr    aContent// "content"
0x6b55  stelem.ref
0x6b56  stloc.0
0x6b57  ldnull
0x6b58  stloc.1
0x6b59  ldarg.s  4
0x6b5b  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6b60  stloc.3
0x6b61  ldarg.0
0x6b62  ldarg.1
0x6b63  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x6b68  ldloc.0
0x6b69  ldarg.s  4
0x6b6b  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity Microsoft.Crm.Service.ObjectModel.KbArticleService::GetKbArticle(valuetype [mscorlib]System.Guid kbArticleId, string[] columns, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6b70  stloc.1
0x6b71  leave.s  loc_6B7D
0x6b73  ldloc.3
0x6b74  brfalse.s loc_6B7C
0x6b76  ldloc.3
0x6b77  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6b7c  endfinally
0x6b7d  ldloc.1
0x6b7e  ldstr    aStatecode// "statecode"
0x6b83  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x6b88  unbox.any [mscorlib]System.Int32
0x6b8d  stloc.2
0x6b8e  ldloc.2
0x6b8f  ldarg.2
0x6b90  bne.un.s loc_6B94
0x6b92  ldc.i4.1
0x6b93  ret
0x6b94  ldarg.2
0x6b95  ldc.i4.1
0x6b96  sub
0x6b97  switch   loc_6BAA, loc_6BB4, loc_6BE5
0x6ba8  br.s     loc_6BEF
0x6baa  ldarg.0
0x6bab  ldloc.1
0x6bac  ldarg.s  4
0x6bae  call     instance bool Microsoft.Crm.Service.ObjectModel.KbArticleService::Reject(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6bb3  ret
0x6bb4  ldloc.2
0x6bb5  ldc.i4.1
0x6bb6  bne.un.s loc_6BC2
0x6bb8  ldarg.0
0x6bb9  ldloc.1
0x6bba  ldarg.s  4
0x6bbc  call     instance bool Microsoft.Crm.Service.ObjectModel.KbArticleService::Submit(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6bc1  ret
0x6bc2  ldloc.2
0x6bc3  ldc.i4.3
0x6bc4  bne.un.s loc_6BD0
0x6bc6  ldarg.0
0x6bc7  ldloc.1
0x6bc8  ldarg.s  4
0x6bca  call     instance bool Microsoft.Crm.Service.ObjectModel.KbArticleService::UnPublish(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6bcf  ret
0x6bd0  ldc.i4   0x800404FB
0x6bd5  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x6bda  ldc.i4   0x800404FB
0x6bdf  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6be4  throw
0x6be5  ldarg.0
0x6be6  ldloc.1
0x6be7  ldarg.s  4
0x6be9  call     instance bool Microsoft.Crm.Service.ObjectModel.KbArticleService::Publish(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6bee  ret
0x6bef  ldc.i4   0x800404FB
0x6bf4  call     string [Microsoft.Crm.Constants]Microsoft.Crm.ErrorCodes::GetErrorMessage(int32)
0x6bf9  ldc.i4   0x800404FB
0x6bfe  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x6c03  throw
```
