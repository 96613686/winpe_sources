# Microsoft.Crm.Application.Forms.FormDescriptorLoader::DataSourceRetrieve

- ea: `0x317f0`
- end: `0x3188e`
- name: `Microsoft.Crm.Application.Forms.FormDescriptorLoader::DataSourceRetrieve`
- size: `158`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x31480`
- `0x31890`
- `0xa7ee0`

## callees

- `0x317f0`
- `0x31f50`
- `0x59740`

## string_xrefs

- `0x3180e`: `formxml`
- `0x3181e`: `componentstate`

## pseudocode

```c

```

## disassembly

```asm
0x317f0  ldnull
0x317f1  stloc.0
0x317f2  ldstr    aSystemform// "systemform"
0x317f7  ldarg.0
0x317f8  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Forms.FormDescriptorCacheKey::get_FormId()
0x317fd  ldc.i4.s 9
0x317ff  newarr   [mscorlib]System.String
0x31804  dup
0x31805  ldc.i4.0
0x31806  ldstr    aFormid// "formid"
0x3180b  stelem.ref
0x3180c  dup
0x3180d  ldc.i4.1
0x3180e  ldstr    aFormxml// "formxml"
0x31813  stelem.ref
0x31814  dup
0x31815  ldc.i4.2
0x31816  ldstr    aSolutionid_0// "solutionid"
0x3181b  stelem.ref
0x3181c  dup
0x3181d  ldc.i4.3
0x3181e  ldstr    aComponentstate// "componentstate"
0x31823  stelem.ref
0x31824  dup
0x31825  ldc.i4.4
0x31826  ldstr    aObjecttypecode// "objecttypecode"
0x3182b  stelem.ref
0x3182c  dup
0x3182d  ldc.i4.5
0x3182e  ldstr    aType// "type"
0x31833  stelem.ref
0x31834  dup
0x31835  ldc.i4.6
0x31836  ldstr    aVersionnumber// "versionnumber"
0x3183b  stelem.ref
0x3183c  dup
0x3183d  ldc.i4.7
0x3183e  ldstr    aFormpresentati// "formpresentation"
0x31843  stelem.ref
0x31844  dup
0x31845  ldc.i4.8
0x31846  ldstr    aFormactivation// "formactivationstate"
0x3184b  stelem.ref
0x3184c  ldc.i4.0
0x3184d  ldc.i4.1
0x3184e  ldarg.1
0x3184f  call     class Microsoft.Crm.Application.Platform.Entity Microsoft.Crm.Application.Platform.DataSource::Retrieve(string entityName, valuetype [mscorlib]System.Guid entityId, string[] columns, bool retrieveLatest, bool useSystemUserContext, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x31854  stloc.0
0x31855  leave.s  loc_3188A
0x31857  stloc.1
0x31858  ldloc.1
0x31859  callvirt instance int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmException::get_ErrorCode()
0x3185e  ldc.i4   0x80040217
0x31863  bne.un.s loc_31888
0x31865  ldloc.1
0x31866  ldstr    aTheGivenFormid_0// "The given formid :{0}: points to an inv"...
0x3186b  ldc.i4.1
0x3186c  newarr   [mscorlib]System.Object
0x31871  dup
0x31872  ldc.i4.0
0x31873  ldarg.0
0x31874  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Forms.FormDescriptorCacheKey::get_FormId()
0x31879  box      [mscorlib]System.Guid
0x3187e  stelem.ref
0x3187f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::Error(class [mscorlib]System.Exception, string, object[])
0x31884  ldnull
0x31885  stloc.2
0x31886  leave.s  loc_3188C
0x31888  rethrow
0x3188a  ldloc.0
0x3188b  ret
0x3188c  ldloc.2
0x3188d  ret
```
