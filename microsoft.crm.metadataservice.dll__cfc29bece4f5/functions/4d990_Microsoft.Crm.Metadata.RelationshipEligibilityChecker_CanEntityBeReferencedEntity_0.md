# Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencedEntity_0

- ea: `0x4d990`
- end: `0x4da47`
- name: `Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencedEntity_0`
- size: `183`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2f250`
- `0x4d940`

## callees

- `0x4d990`
- `0x4e220`
- `0x5a810`

## string_xrefs

- `0x4d9a1`: `prvReadRelationship`
- `0x4d9d5`: `issecurityintersect`

## pseudocode

```c

```

## disassembly

```asm
0x4d990  ldarg.2
0x4d991  ldstr    aContext// "context"
0x4d996  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x4d99b  ldarg.2
0x4d99c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x4d9a1  ldstr    aPrvreadrelatio// "prvReadRelationship"
0x4d9a6  ldarg.2
0x4d9a7  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Metadata.CustomizationSecurityCache::GetPrivilegeIdFromName(string privilegeName, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x4d9ac  ldarg.2
0x4d9ad  call     void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SecurityLibrary::CheckPrivilegeGlobalDepth(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x4d9b2  call     class [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::get_Instance()
0x4d9b7  ldarg.1
0x4d9b8  ldstr    aEntity_0// "Entity"
0x4d9bd  ldc.i4.7
0x4d9be  newarr   [mscorlib]System.String
0x4d9c3  dup
0x4d9c4  ldc.i4.0
0x4d9c5  ldstr    aEntityid// "entityid"
0x4d9ca  stelem.ref
0x4d9cb  dup
0x4d9cc  ldc.i4.1
0x4d9cd  ldstr    aIsintersect// "isintersect"
0x4d9d2  stelem.ref
0x4d9d3  dup
0x4d9d4  ldc.i4.2
0x4d9d5  ldstr    aIssecurityinte// "issecurityintersect"
0x4d9da  stelem.ref
0x4d9db  dup
0x4d9dc  ldc.i4.3
0x4d9dd  ldstr    aName// "name"
0x4d9e2  stelem.ref
0x4d9e3  dup
0x4d9e4  ldc.i4.4
0x4d9e5  ldstr    aObjecttypecode_0// "objecttypecode"
0x4d9ea  stelem.ref
0x4d9eb  dup
0x4d9ec  ldc.i4.5
0x4d9ed  ldstr    aIsshareableacr// "isshareableacrossorgs"
0x4d9f2  stelem.ref
0x4d9f3  dup
0x4d9f4  ldc.i4.6
0x4d9f5  ldstr    aCanbeprimaryen// "canbeprimaryentityinrelationship"
0x4d9fa  stelem.ref
0x4d9fb  ldarg.2
0x4d9fc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_SqlContext()
0x4da01  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity [Microsoft.Crm.MetadataHelper]Microsoft.Crm.Metadata.MetadataQueryHelper::RetrieveMetadataEntity(valuetype [mscorlib]System.Guid, string, string[], class [Microsoft.Crm.Core]Microsoft.Crm.ISqlExecutionContext)
0x4da06  stloc.0
0x4da07  ldc.i4.0
0x4da08  stloc.1
0x4da09  ldnull
0x4da0a  stloc.2
0x4da0b  ldarg.0
0x4da0c  ldloc.0
0x4da0d  ldarg.2
0x4da0e  ldloca.s 1
0x4da10  ldloca.s 2
0x4da12  call     instance bool Microsoft.Crm.Metadata.RelationshipEligibilityChecker::CanEntityBeReferencedEntity(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity possibleReferencedEntityData, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, [out] int32& errorCode, [out] string& exceptionMessage)
0x4da17  stloc.3
0x4da18  ldloc.3
0x4da19  brtrue.s loc_4DA45
0x4da1b  ldarg.2
0x4da1c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x4da21  ldc.i4.s 0x19
0x4da23  ldstr    aEntity0CannotB_0// "Entity {0} cannot be a referenced entit"...
0x4da28  ldc.i4.2
0x4da29  newarr   [mscorlib]System.Object
0x4da2e  dup
0x4da2f  ldc.i4.0
0x4da30  ldloc.0
0x4da31  ldstr    aName// "name"
0x4da36  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataBusinessEntity::get_Item(string)
0x4da3b  stelem.ref
0x4da3c  dup
0x4da3d  ldc.i4.1
0x4da3e  ldloc.2
0x4da3f  stelem.ref
0x4da40  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x4da45  ldloc.3
0x4da46  ret
```
