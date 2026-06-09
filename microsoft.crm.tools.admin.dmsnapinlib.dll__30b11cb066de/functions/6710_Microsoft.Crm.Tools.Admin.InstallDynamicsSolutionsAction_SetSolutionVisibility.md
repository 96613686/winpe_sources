# Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::SetSolutionVisibility

- ea: `0x6710`
- end: `0x684d`
- name: `Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::SetSolutionVisibility`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x19400`

## callees

- `0x6710`
- `0x6850`
- `0x8630`

## string_xrefs

- `0x67d5`: `Failed to dispose importXml object correctly for solution {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x6710  ldsfld   string [mscorlib]System.String::Empty
0x6715  stloc.0
0x6716  ldarg.2
0x6717  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x671c  call     int32 [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::GetInstallConnectionTimeout()
0x6721  ldc.i4.0
0x6722  ldc.i4.0
0x6723  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection::.ctor(valuetype [mscorlib]System.Guid, int32, bool, valuetype [Microsoft.Crm.Core]Microsoft.Crm.ReadPriority)
0x6728  ldarg.2
0x6729  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x672e  call     class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.DllMethodActionsUtility::CreateExecutionContext(class [Microsoft.Crm.Core]Microsoft.Crm.CrmDbConnection, valuetype [mscorlib]System.Guid)
0x6733  stloc.1
0x6734  ldloc.1
0x6735  ldc.i4.0
0x6736  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnBeginRequest(bool)
0x673b  ldarg.0
0x673c  callvirt instance bool [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UsePackage()
0x6741  brfalse  loc_680B
0x6746  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x674b  stloc.2
0x674c  ldarg.0
0x674d  ldloc.1
0x674e  call     class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml>> [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.LangProvisioning.LanguageProvisioningUtility::GetImportXmlsForPackage(class [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6753  stloc.3
0x6754  ldloc.3
0x6755  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml>>::get_Keys()
0x675a  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x675f  stloc.s  4
0x6761  br.s     loc_6783
0x6763  ldloc.s  4
0x6765  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x676a  stloc.s  5
0x676c  ldloc.2
0x676d  ldstr    asc_1FB16// "'"
0x6772  ldloc.s  5
0x6774  ldstr    asc_1FB16// "'"
0x6779  call     string [mscorlib]System.String::Concat(string, string, string)
0x677e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x6783  ldloc.s  4
0x6785  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x678a  brtrue.s loc_6763
0x678c  leave.s  loc_679A
0x678e  ldloc.s  4
0x6790  brfalse.s loc_6799
0x6792  ldloc.s  4
0x6794  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6799  endfinally
0x679a  ldstr    asc_1FB1A// ","
0x679f  ldloc.2
0x67a0  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x67a5  stloc.0
0x67a6  leave.s  loc_6821
0x67a8  ldloc.3
0x67a9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml>>>::GetEnumerator()
0x67ae  stloc.s  6
0x67b0  br.s     loc_67F3
0x67b2  ldloc.s  6
0x67b4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml>>>::get_Current()
0x67b9  stloc.s  7
0x67bb  ldloca.s 7
0x67bd  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml>>::get_Value()
0x67c2  callvirt instance var<u1> class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml>::get_Item2()
0x67c7  callvirt instance void [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml::Dispose()
0x67cc  leave.s  loc_67F3
0x67ce  ldarg.2
0x67cf  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Tools.Admin.OrganizationInfo::get_OrganizationId()
0x67d4  ldc.i4.3
0x67d5  ldstr    aFailedToDispos// "Failed to dispose importXml object corr"...
0x67da  ldloca.s 7
0x67dc  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class [mscorlib]System.Tuple`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Tools.Core.ImportExportPublish]Microsoft.Crm.Tools.ImportExportPublish.ImportXml>>::get_Key()
0x67e1  call     string [mscorlib]System.String::Format(string, object)
0x67e6  ldc.i4.0
0x67e7  newarr   [mscorlib]System.Object
0x67ec  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x67f1  leave.s  loc_67F3
0x67f3  ldloc.s  6
0x67f5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x67fa  brtrue.s loc_67B2
0x67fc  leave.s  loc_680A
0x67fe  ldloc.s  6
0x6800  brfalse.s loc_6809
0x6802  ldloc.s  6
0x6804  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6809  endfinally
0x680a  endfinally
0x680b  ldstr    asc_1FB16// "'"
0x6810  ldarg.0
0x6811  callvirt instance string [Microsoft.Crm.Setup.Server.SolutionsUtility]Microsoft.Crm.Setup.Server.SolutionsUtility.SolutionInfo::get_UniqueName()
0x6816  ldstr    asc_1FB16// "'"
0x681b  call     string [mscorlib]System.String::Concat(string, string, string)
0x6820  stloc.0
0x6821  ldloc.0
0x6822  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x6827  brtrue.s loc_6831
0x6829  ldloc.0
0x682a  ldarg.1
0x682b  ldloc.1
0x682c  call     void Microsoft.Crm.Tools.Admin.InstallDynamicsSolutionsAction::SetSolutionVisibilityInternal(string solutionUniqueName, bool isHidden, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x6831  ldloc.1
0x6832  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnEndRequest()
0x6837  leave.s  loc_684C
0x6839  pop
0x683a  ldloc.1
0x683b  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::OnErrorRequest()
0x6840  rethrow
0x6842  ldloc.1
0x6843  brfalse.s loc_684B
0x6845  ldloc.1
0x6846  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x684b  endfinally
0x684c  ret
```
