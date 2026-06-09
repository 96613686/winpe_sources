# Microsoft.Crm.ObjectModel.AppModuleService::AddAppModuleComponentToAppModule

- ea: `0x94800`
- end: `0x94928`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::AddAppModuleComponentToAppModule`
- size: `296`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x910e0`
- `0x96f40`
- `0x97550`

## callees

- `0x94800`

## string_xrefs

- `0x9484e`: `componenttype`
- `0x94895`: `componenttype`
- `0x9480b`: `AppModuleComponent_BEGIN_{0}.AddAppModuleComponentToAppModule`
- `0x9482c`: `AppModuleService.AddAppModuleComponentToAppModule(): START.`
- `0x94877`: `AppModuleService.AddAppModuleComponentToAppModule(): Adding appModuleComponent [{0}:{1}] [{2}:{3}] [{4}:{5}].`
- `0x948d0`: `AppModuleService.AddAppModuleComponentToAppModule(): Added appModuleComponent [appModuleComponentId:{0}].`
- `0x948f3`: `AppModuleComponent_END_{0}.AddAppModuleComponentToAppModule`
- `0x94914`: `AppModuleService.AddAppModuleComponentToAppModule(): END.`

## pseudocode

```c

```

## disassembly

```asm
0x94800  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x94805  stloc.0
0x94806  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9480b  ldstr    aAppmodulecompo_6// "AppModuleComponent_BEGIN_{0}.AddAppModu"...
0x94810  ldc.i4.1
0x94811  newarr   [mscorlib]System.Object
0x94816  dup
0x94817  ldc.i4.0
0x94818  ldarg.0
0x94819  stelem.ref
0x9481a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9481f  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x94824  ldarg.3
0x94825  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x9482a  ldc.i4.s 0x47
0x9482c  ldstr    aAppmoduleservi_93// "AppModuleService.AddAppModuleComponentT"...
0x94831  ldc.i4.0
0x94832  newarr   [mscorlib]System.Object
0x94837  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9483c  ldarg.1
0x9483d  ldstr    aObjectid// "objectid"
0x94842  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x94847  unbox.any [mscorlib]System.Guid
0x9484c  stloc.1
0x9484d  ldarg.1
0x9484e  ldstr    aComponenttype// "componenttype"
0x94853  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x94858  unbox.any [mscorlib]System.Int32
0x9485d  stloc.2
0x9485e  ldarg.1
0x9485f  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x94864  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x94869  unbox.any [mscorlib]System.Guid
0x9486e  stloc.3
0x9486f  ldarg.3
0x94870  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x94875  ldc.i4.s 0x47
0x94877  ldstr    aAppmoduleservi_94// "AppModuleService.AddAppModuleComponentT"...
0x9487c  ldc.i4.6
0x9487d  newarr   [mscorlib]System.Object
0x94882  dup
0x94883  ldc.i4.0
0x94884  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x94889  stelem.ref
0x9488a  dup
0x9488b  ldc.i4.1
0x9488c  ldloc.3
0x9488d  box      [mscorlib]System.Guid
0x94892  stelem.ref
0x94893  dup
0x94894  ldc.i4.2
0x94895  ldstr    aComponenttype// "componenttype"
0x9489a  stelem.ref
0x9489b  dup
0x9489c  ldc.i4.3
0x9489d  ldloc.2
0x9489e  box      [mscorlib]System.Int32
0x948a3  stelem.ref
0x948a4  dup
0x948a5  ldc.i4.4
0x948a6  ldstr    aObjectid// "objectid"
0x948ab  stelem.ref
0x948ac  dup
0x948ad  ldc.i4.5
0x948ae  ldloc.1
0x948af  box      [mscorlib]System.Guid
0x948b4  stelem.ref
0x948b5  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x948ba  ldarg.2
0x948bb  ldarg.1
0x948bc  ldarg.3
0x948bd  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Create(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x948c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::get_Id()
0x948c7  stloc.0
0x948c8  ldarg.3
0x948c9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x948ce  ldc.i4.s 0x47
0x948d0  ldstr    aAppmoduleservi_95// "AppModuleService.AddAppModuleComponentT"...
0x948d5  ldc.i4.1
0x948d6  newarr   [mscorlib]System.Object
0x948db  dup
0x948dc  ldc.i4.0
0x948dd  ldloc.0
0x948de  box      [mscorlib]System.Guid
0x948e3  stelem.ref
0x948e4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x948e9  ldloc.0
0x948ea  stloc.s  4
0x948ec  leave.s  loc_94925
0x948ee  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x948f3  ldstr    aAppmodulecompo_7// "AppModuleComponent_END_{0}.AddAppModule"...
0x948f8  ldc.i4.1
0x948f9  newarr   [mscorlib]System.Object
0x948fe  dup
0x948ff  ldc.i4.0
0x94900  ldarg.0
0x94901  stelem.ref
0x94902  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x94907  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x9490c  ldarg.3
0x9490d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x94912  ldc.i4.s 0x47
0x94914  ldstr    aAppmoduleservi_96// "AppModuleService.AddAppModuleComponentT"...
0x94919  ldc.i4.0
0x9491a  newarr   [mscorlib]System.Object
0x9491f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x94924  endfinally
0x94925  ldloc.s  4
0x94927  ret
```
