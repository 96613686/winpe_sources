# Microsoft.Crm.Application.WebServices.WorkflowWebService::DeleteAttachmentStep

- ea: `0x7210`
- end: `0x72d8`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::DeleteAttachmentStep`
- size: `200`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x7210`

## pseudocode

```c

```

## disassembly

```asm
0x7210  ldstr    aAnnotation// "annotation"
0x7215  newobj   instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::.ctor(string)
0x721a  dup
0x721b  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x7220  ldstr    aObjecttypecode// "objecttypecode"
0x7225  ldc.i4.0
0x7226  ldc.i4   0x125F
0x722b  box      [mscorlib]System.Int32
0x7230  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x7235  dup
0x7236  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x723b  ldstr    aObjectid// "objectid"
0x7240  ldc.i4.0
0x7241  ldarg.1
0x7242  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x7247  box      [mscorlib]System.Guid
0x724c  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x7251  dup
0x7252  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression::get_Criteria()
0x7257  ldstr    aStepid_0// "stepid"
0x725c  ldc.i4.0
0x725d  ldarg.2
0x725e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ConditionOperator, object)
0x7263  dup
0x7264  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryBase::get_ColumnSet()
0x7269  ldstr    aAnnotationid// "annotationid"
0x726e  callvirt instance void [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.ColumnSetBase::AddColumn(string)
0x7273  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x7278  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x727d  stloc.0
0x727e  ldloc.0
0x727f  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x7284  ldc.i4.0
0x7285  bgt.s    loc_7289
0x7287  leave.s  loc_72D7
0x7289  ldloc.0
0x728a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x728f  stloc.1
0x7290  br.s     loc_72B8
0x7292  ldloc.1
0x7293  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x7298  stloc.2
0x7299  ldstr    aAnnotation// "annotation"
0x729e  ldloc.2
0x729f  ldstr    aAnnotationid// "annotationid"
0x72a4  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x72a9  unbox.any [mscorlib]System.Guid
0x72ae  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x72b3  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::Delete(string, valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x72b8  ldloc.1
0x72b9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x72be  brtrue.s loc_7292
0x72c0  leave.s  loc_72CC
0x72c2  ldloc.1
0x72c3  brfalse.s loc_72CB
0x72c5  ldloc.1
0x72c6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x72cb  endfinally
0x72cc  leave.s  loc_72D7
0x72ce  stloc.3
0x72cf  ldarg.0
0x72d0  ldloc.3
0x72d1  call     instance class [System.Web.Services]System.Web.Services.Protocols.SoapException [Microsoft.Crm.Core.Application.Components.WebServices.Core]Microsoft.Crm.Core.Application.WebServices.AppWebService::CreateSoapException(class [mscorlib]System.Exception)
0x72d6  throw
0x72d7  ret
```
