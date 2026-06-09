# Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::GetMailboxInfo

- ea: `0x50870`
- end: `0x50a00`
- name: `Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::GetMailboxInfo`
- size: `400`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x505c0`

## callees

- `0x50870`

## string_xrefs

- `0x508a1`: `incomingemaildeliverymethod`
- `0x50974`: `incomingemaildeliverymethod`
- `0x508b1`: `enabledforincomingemail`
- `0x5098b`: `enabledforincomingemail`
- `0x50891`: `lastsuccessfulsynccompletedon`
- `0x5095d`: `lastsuccessfulsynccompletedon`

## pseudocode

```c

```

## disassembly

```asm
0x50870  ldstr    aMailbox// "mailbox"
0x50875  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x5087a  stloc.0
0x5087b  ldloc.0
0x5087c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x50881  ldstr    aFolderhierarch// "folderhierarchy"
0x50886  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x5088b  ldloc.0
0x5088c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x50891  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0x50896  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x5089b  ldloc.0
0x5089c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x508a1  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x508a6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x508ab  ldloc.0
0x508ac  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x508b1  ldstr    aEnabledforinco// "enabledforincomingemail"
0x508b6  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumn(string)
0x508bb  ldloc.0
0x508bc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_Criteria()
0x508c1  ldstr    aMailboxid// "mailboxid"
0x508c6  ldc.i4.0
0x508c7  ldc.i4.1
0x508c8  newarr   [mscorlib]System.Object
0x508cd  dup
0x508ce  ldc.i4.0
0x508cf  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x508d4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultMailbox()
0x508d9  box      [mscorlib]System.Guid
0x508de  stelem.ref
0x508df  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.FilterExpression::AddCondition(string, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object[])
0x508e4  ldloc.0
0x508e5  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x508ea  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.ApplicationEntityCollection [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.DataSource::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x508ef  stloc.1
0x508f0  ldloc.1
0x508f1  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Count()
0x508f6  brtrue.s loc_50932
0x508f8  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x508fd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x50902  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x50907  ldstr    aNoMailboxInfor// "No mailbox information was found for th"...
0x5090c  ldc.i4.1
0x5090d  newarr   [mscorlib]System.Object
0x50912  dup
0x50913  ldc.i4.0
0x50914  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x50919  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultMailbox()
0x5091e  stloc.2
0x5091f  ldloca.s 2
0x50921  constrained. [mscorlib]System.Guid
0x50927  callvirt instance string [mscorlib]System.Object::ToString()
0x5092c  stelem.ref
0x5092d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x50932  ldloc.1
0x50933  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::GetEnumerator()
0x50938  stloc.3
0x50939  br.s     loc_5099F
0x5093b  ldloc.3
0x5093c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity>::get_Current()
0x50941  stloc.s  4
0x50943  ldarg.0
0x50944  ldloc.s  4
0x50946  ldstr    aFolderhierarch// "folderhierarchy"
0x5094b  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x50950  castclass [mscorlib]System.String
0x50955  stfld    string Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::folderHierarchy
0x5095a  ldarg.0
0x5095b  ldloc.s  4
0x5095d  ldstr    aLastsuccessful// "lastsuccessfulsynccompletedon"
0x50962  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x50967  unbox.any [mscorlib]System.DateTime
0x5096c  stfld    valuetype [mscorlib]System.DateTime Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::lastSuccessfulSyncCompletedOn
0x50971  ldarg.0
0x50972  ldloc.s  4
0x50974  ldstr    aIncomingemaild// "incomingemaildeliverymethod"
0x50979  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x5097e  unbox.any [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod
0x50983  stfld    valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.EmailDeliveryMethod Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::incomingEmailDeliveryMethod
0x50988  ldarg.0
0x50989  ldloc.s  4
0x5098b  ldstr    aEnabledforinco// "enabledforincomingemail"
0x50990  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x50995  unbox.any [mscorlib]System.Boolean
0x5099a  stfld    bool Microsoft.Crm.Web.Tools.FolderBasedTracking.FolderBasedTrackingPage::enabledForIncomingEmail
0x5099f  ldloc.3
0x509a0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x509a5  brtrue.s loc_5093B
0x509a7  leave.s  loc_509B3
0x509a9  ldloc.3
0x509aa  brfalse.s loc_509B2
0x509ac  ldloc.3
0x509ad  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x509b2  endfinally
0x509b3  leave.s  loc_509FF
0x509b5  stloc.s  5
0x509b7  ldloc.s  5
0x509b9  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x509be  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x509c3  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x509c8  ldstr    aExceptionWhile// "Exception while querying the mailbox fo"...
0x509cd  ldc.i4.2
0x509ce  newarr   [mscorlib]System.Object
0x509d3  dup
0x509d4  ldc.i4.0
0x509d5  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::get_Current()
0x509da  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_DefaultMailbox()
0x509df  stloc.2
0x509e0  ldloca.s 2
0x509e2  constrained. [mscorlib]System.Guid
0x509e8  callvirt instance string [mscorlib]System.Object::ToString()
0x509ed  stelem.ref
0x509ee  dup
0x509ef  ldc.i4.1
0x509f0  ldloc.s  5
0x509f2  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x509f7  stelem.ref
0x509f8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x509fd  leave.s  loc_509FF
0x509ff  ret
```
