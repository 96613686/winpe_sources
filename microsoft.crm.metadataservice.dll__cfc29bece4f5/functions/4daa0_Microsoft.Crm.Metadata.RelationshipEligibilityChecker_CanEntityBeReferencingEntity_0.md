# Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencingEntity_0

- ea: `0x4daa0`
- end: `0x4db71`
- name: `Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencingEntity_0`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2f280`
- `0x4da50`

## callees

- `0x4daa0`
- `0x4dfe0`
- `0x5a810`

## string_xrefs

- `0x4dab1`: `prvReadRelationship`
- `0x4dae6`: `issecurityintersect`

## pseudocode

```c

```

## disassembly

```asm
0x4daa0  ldarg.2
0x4daa1  ldstr    aContext// "context"
0x4daa6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4daab  ldarg.2
0x4daac  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4dab1  ldstr    aPrvreadrelatio// "prvReadRelationship"
0x4dab6  ldarg.2
0x4dab7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4dabc  ldarg.2
0x4dabd  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4dac2  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x4dac7  ldarg.1
0x4dac8  ldstr    aEntity_0// "Entity"
0x4dacd  ldc.i4.s 0xA
0x4dacf  newarr   [mscorlib]System.String
0x4dad4  dup
0x4dad5  ldc.i4.0
0x4dad6  ldstr    aEntityid// "entityid"
0x4dadb  stelem.ref
0x4dadc  dup
0x4dadd  ldc.i4.1
0x4dade  ldstr    aIsintersect// "isintersect"
0x4dae3  stelem.ref
0x4dae4  dup
0x4dae5  ldc.i4.2
0x4dae6  ldstr    aIssecurityinte// "issecurityintersect"
0x4daeb  stelem.ref
0x4daec  dup
0x4daed  ldc.i4.3
0x4daee  ldstr    aName// "name"
0x4daf3  stelem.ref
0x4daf4  dup
0x4daf5  ldc.i4.4
0x4daf6  ldstr    aIscustomizable// "iscustomizable"
0x4dafb  stelem.ref
0x4dafc  dup
0x4dafd  ldc.i4.5
0x4dafe  ldstr    aIsmanaged// "ismanaged"
0x4db03  stelem.ref
0x4db04  dup
0x4db05  ldc.i4.6
0x4db06  ldstr    aObjecttypecode_0// "objecttypecode"
0x4db0b  stelem.ref
0x4db0c  dup
0x4db0d  ldc.i4.7
0x4db0e  ldstr    aIssolutionawar// "issolutionaware"
0x4db13  stelem.ref
0x4db14  dup
0x4db15  ldc.i4.8
0x4db16  ldstr    aCanberelateden// "canberelatedentityinrelationship"
0x4db1b  stelem.ref
0x4db1c  dup
0x4db1d  ldc.i4.s 9
0x4db1f  ldstr    aIsenabledforex// "isenabledforexternalchannels"
0x4db24  stelem.ref
0x4db25  ldarg.2
0x4db26  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4db2b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4db30  stloc.0
0x4db31  ldc.i4.0
0x4db32  stloc.1
0x4db33  ldnull
0x4db34  stloc.2
0x4db35  ldarg.0
0x4db36  ldloc.0
0x4db37  ldarg.2
0x4db38  ldloca.s 1
0x4db3a  ldloca.s 2
0x4db3c  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencingEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity possibleReferencingEntityData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] int32& errorCode, [out] string& exceptionMessage)
0x4db41  stloc.3
0x4db42  ldloc.3
0x4db43  brtrue.s loc_4DB6F
0x4db45  ldarg.2
0x4db46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4db4b  ldc.i4.s 0x19
0x4db4d  ldstr    aEntity0CannotB_1// "Entity {0} cannot be a referencing enti"...
0x4db52  ldc.i4.2
0x4db53  newarr   [mscorlib]System.Object
0x4db58  dup
0x4db59  ldc.i4.0
0x4db5a  ldloc.0
0x4db5b  ldstr    aName// "name"
0x4db60  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4db65  stelem.ref
0x4db66  dup
0x4db67  ldc.i4.1
0x4db68  ldloc.2
0x4db69  stelem.ref
0x4db6a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4db6f  ldloc.3
0x4db70  ret
```
