# Microsoft.Crm.Asynchronous.DatabaseTuningManager::Initialize

- ea: `0x2090`
- end: `0x2187`
- name: `Microsoft.Crm.Asynchronous.DatabaseTuningManager::Initialize`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1f60`

## callees

- `0x2090`

## string_xrefs

- `0x209c`: `DTADirectory`
- `0x20aa`: `DTADirectory not found`
- `0x20bf`: `DTATemplate`
- `0x20cd`: `DTATemplate note found`

## pseudocode

```c

```

## disassembly

```asm
0x2090  ldarg.0
0x2091  ldarg.1
0x2092  stfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.DatabaseTuningManager::_organizationId
0x2097  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x209c  ldstr    aDtadirectory// "DTADirectory"
0x20a1  callvirt T0x2B000001
0x20a6  stloc.0
0x20a7  ldloc.0
0x20a8  brtrue.s loc_20BA
0x20aa  ldstr    aDtadirectoryNo// "DTADirectory not found"
0x20af  ldc.i4   0x80040216
0x20b4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x20b9  throw
0x20ba  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x20bf  ldstr    aDtatemplate// "DTATemplate"
0x20c4  callvirt T0x2B000001
0x20c9  stloc.1
0x20ca  ldloc.1
0x20cb  brtrue.s loc_20DD
0x20cd  ldstr    aDtatemplateNot// "DTATemplate note found"
0x20d2  ldc.i4   0x80040216
0x20d7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x20dc  throw
0x20dd  ldarg.0
0x20de  ldloc.0
0x20df  stfld    string Microsoft.Crm.Asynchronous.DatabaseTuningManager::_traceDirectory
0x20e4  ldarg.0
0x20e5  ldloc.1
0x20e6  stfld    string Microsoft.Crm.Asynchronous.DatabaseTuningManager::_dtaTemplateXml
0x20eb  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x20f0  ldstr    aDtatracedurati// "DTATraceDurationMinutes"
0x20f5  callvirt T0x2B000005
0x20fa  stloc.2
0x20fb  ldloca.s 2
0x20fd  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x2102  brtrue.s loc_210D
0x2104  ldarg.0
0x2105  ldc.i4.5
0x2106  stfld    int32 Microsoft.Crm.Asynchronous.DatabaseTuningManager::_traceDurationMinutes
0x210b  br.s     loc_211A
0x210d  ldarg.0
0x210e  ldloca.s 2
0x2110  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x2115  stfld    int32 Microsoft.Crm.Asynchronous.DatabaseTuningManager::_traceDurationMinutes
0x211a  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x211f  ldstr    aOrganization// "Organization"
0x2124  ldarg.0
0x2125  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.DatabaseTuningManager::_organizationId
0x212a  box      [mscorlib]System.Guid
0x212f  ldc.i4.2
0x2130  newarr   [mscorlib]System.String
0x2135  dup
0x2136  ldc.i4.0
0x2137  ldstr    aSqlservername// "SqlServerName"
0x213c  stelem.ref
0x213d  dup
0x213e  ldc.i4.1
0x213f  ldstr    aDatabasename// "DatabaseName"
0x2144  stelem.ref
0x2145  ldc.i4   0xA3
0x214a  ldstr    aInitialize// "Initialize"
0x214f  ldstr    aDDbsShDccm2110_2// "d:\\dbs\\sh\\dccm2\\1101_190851\\cmd\\5"...
0x2154  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::RetrieveById(string, object, string[], int32, string, string)
0x2159  stloc.3
0x215a  ldarg.0
0x215b  ldloc.3
0x215c  ldstr    aSqlservername// "SqlServerName"
0x2161  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x2166  castclass [mscorlib]System.String
0x216b  stfld    string Microsoft.Crm.Asynchronous.DatabaseTuningManager::_sqlServer
0x2170  ldarg.0
0x2171  ldloc.3
0x2172  ldstr    aDatabasename// "DatabaseName"
0x2177  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x217c  castclass [mscorlib]System.String
0x2181  stfld    string Microsoft.Crm.Asynchronous.DatabaseTuningManager::_databaseName
0x2186  ret
```
