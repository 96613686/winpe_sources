# Microsoft.Crm.Reporting.ReportPublisher::UpgradeCustomReports

- ea: `0x4410`
- end: `0x45b7`
- name: `Microsoft.Crm.Reporting.ReportPublisher::UpgradeCustomReports`
- size: `423`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180`
- `0x450`
- `0x4410`
- `0x45c0`
- `0x4650`
- `0x4740`

## string_xrefs

- `0x44a2`: `customreportxml`

## pseudocode

```c

```

## disassembly

```asm
0x4410  ldstr    aMicrosoftCrmRe// "Microsoft.Crm.Reporting.Strings"
0x4415  ldtoken  Microsoft.Crm.Reporting.ReportServer
0x441a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x441f  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x4424  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x4429  stloc.0
0x442a  ldarg.1
0x442b  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x4430  stloc.1
0x4431  ldarg.0
0x4432  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Reporting.ReportPublisher::_context
0x4437  ldc.i4.1
0x4438  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.SystemUserContext::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, bool)
0x443d  stloc.2
0x443e  ldarg.0
0x443f  ldarg.1
0x4440  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection Microsoft.Crm.Reporting.ReportPublisher::GetCustomReports(int32 languageCode)
0x4445  stloc.3
0x4446  ldc.i4.1
0x4447  stloc.s  4
0x4449  ldloc.3
0x444a  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x444f  stloc.s  5
0x4451  br       loc_4589
0x4456  ldloc.s  5
0x4458  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x445d  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x4462  stloc.s  6
0x4464  ldarg.2
0x4465  brfalse.s loc_44A0
0x4467  ldarg.2
0x4468  ldloc.0
0x4469  ldstr    aSrsPublisingre// "SRS.PublisingReport"
0x446e  ldloc.1
0x446f  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string, class [mscorlib]System.Globalization.CultureInfo)
0x4474  ldstr    asc_B3EC// " "
0x4479  ldloc.s  6
0x447b  ldstr    aName_0// "name"
0x4480  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4485  castclass [mscorlib]System.String
0x448a  call     string [mscorlib]System.String::Concat(string, string, string)
0x448f  ldloc.s  4
0x4491  ldc.i4.s 0x64
0x4493  mul
0x4494  ldloc.3
0x4495  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x449a  div
0x449b  callvirt instance void Microsoft.Crm.Reporting.IProgressEventSource::RaiseProgressChanged(string text, int32 value)
0x44a0  ldloc.s  6
0x44a2  ldstr    aCustomreportxm// "customreportxml"
0x44a7  ldarg.0
0x44a8  ldloc.s  6
0x44aa  call     instance string Microsoft.Crm.Reporting.ReportPublisher::GetWizardXml(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity report)
0x44af  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x44b4  ldloc.s  6
0x44b6  ldstr    aSolutionid// "solutionid"
0x44bb  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x44c0  unbox.any [mscorlib]System.Guid
0x44c5  stloc.s  7
0x44c7  ldloc.s  7
0x44c9  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.Crm.Constants]Microsoft.Crm.SolutionConstants::ActiveSolutionId
0x44ce  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x44d3  brtrue.s loc_44D8
0x44d5  ldc.i4.3
0x44d6  br.s     loc_44D9
0x44d8  ldc.i4.0
0x44d9  stloc.s  8
0x44db  ldarg.0
0x44dc  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Reporting.ReportPublisher::_context
0x44e1  ldloc.s  8
0x44e3  ldloc.s  7
0x44e5  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.AutoSolutionOperationContextModifier::.ctor(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext, valuetype [Microsoft.Crm.Core]Microsoft.Crm.SolutionOperationContext, valuetype [mscorlib]System.Guid)
0x44ea  stloc.s  9
0x44ec  ldarg.3
0x44ed  brfalse.s loc_4505
0x44ef  ldarg.0
0x44f0  ldfld    class Microsoft.Crm.Reporting.IReportService Microsoft.Crm.Reporting.ReportPublisher::_provisioningReportService
0x44f5  ldloc.s  6
0x44f7  ldarg.0
0x44f8  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Reporting.ReportPublisher::_context
0x44fd  ldc.i4.0
0x44fe  callvirt instance void Microsoft.Crm.Reporting.IReportService::UpdateInternalFromTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool updateRelatedEntities)
0x4503  br.s     loc_4519
0x4505  ldarg.0
0x4506  ldfld    class Microsoft.Crm.Reporting.IReportService Microsoft.Crm.Reporting.ReportPublisher::_reportService
0x450b  ldloc.s  6
0x450d  ldarg.0
0x450e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext Microsoft.Crm.Reporting.ReportPublisher::_context
0x4513  ldc.i4.0
0x4514  callvirt instance void Microsoft.Crm.Reporting.IReportService::UpdateInternalFromTemplate(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context, bool updateRelatedEntities)
0x4519  leave.s  loc_4583
0x451b  stloc.s  0xA
0x451d  ldarg.0
0x451e  ldstr    aWarningCouldNo// "Warning: Could not upgrade report {0}: "...
0x4523  ldc.i4.2
0x4524  newarr   [mscorlib]System.Object
0x4529  dup
0x452a  ldc.i4.0
0x452b  ldloc.s  6
0x452d  ldstr    aName_0// "name"
0x4532  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4537  castclass [mscorlib]System.String
0x453c  stelem.ref
0x453d  dup
0x453e  ldc.i4.1
0x453f  ldloc.s  0xA
0x4541  stelem.ref
0x4542  callvirt instance void Microsoft.Crm.Reporting.ReportPublisher::LogWarningFormat(string format, object[] args)
0x4547  leave.s  loc_4583
0x4549  stloc.s  0xB
0x454b  ldarg.0
0x454c  ldstr    aWarningCouldNo// "Warning: Could not upgrade report {0}: "...
0x4551  ldc.i4.2
0x4552  newarr   [mscorlib]System.Object
0x4557  dup
0x4558  ldc.i4.0
0x4559  ldloc.s  6
0x455b  ldstr    aName_0// "name"
0x4560  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x4565  castclass [mscorlib]System.String
0x456a  stelem.ref
0x456b  dup
0x456c  ldc.i4.1
0x456d  ldloc.s  0xB
0x456f  stelem.ref
0x4570  callvirt instance void Microsoft.Crm.Reporting.ReportPublisher::LogWarningFormat(string format, object[] args)
0x4575  leave.s  loc_4583
0x4577  ldloc.s  9
0x4579  brfalse.s loc_4582
0x457b  ldloc.s  9
0x457d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4582  endfinally
0x4583  ldloc.s  4
0x4585  ldc.i4.1
0x4586  add
0x4587  stloc.s  4
0x4589  ldloc.s  5
0x458b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4590  brtrue   loc_4456
0x4595  leave.s  loc_45B6
0x4597  ldloc.s  5
0x4599  isinst   [mscorlib]System.IDisposable
0x459e  stloc.s  0xC
0x45a0  ldloc.s  0xC
0x45a2  brfalse.s loc_45AB
0x45a4  ldloc.s  0xC
0x45a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45ab  endfinally
0x45ac  ldloc.2
0x45ad  brfalse.s loc_45B5
0x45af  ldloc.2
0x45b0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45b5  endfinally
0x45b6  ret
```
