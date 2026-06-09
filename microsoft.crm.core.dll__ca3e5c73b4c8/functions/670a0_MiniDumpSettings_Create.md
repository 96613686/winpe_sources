# MiniDumpSettings::Create

- ea: `0x670a0`
- end: `0x671de`
- name: `MiniDumpSettings::Create`
- size: `318`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d9f0`

## callees

- `0x1eaa0`
- `0x1f4b0`
- `0x1f510`
- `0x34780`
- `0x34790`
- `0x670a0`
- `0x67230`

## string_xrefs

- `0x670b9`: `TraceDirectory`
- `0x670e8`: `MiniDump: TraceDirectory setting not set or missing. Defaulting to temporary folder.`
- `0x670ff`: `MiniDumpCheckCommand`
- `0x67116`: `MiniDumpCommand`
- `0x6711b`: `%WINDIR%\system32\ntsd.exe`
- `0x6713f`: `MiniDump did not find the MiniDumpCommand file: {0}. Using dbgHelp to dump.`
- `0x6715e`: `-g -p {0} -pv -y srv**http://msdl.microsoft.com/download/symbols -c ".dump /mfh {1}; .detach; q"`

## pseudocode

```c

```

## disassembly

```asm
0x670a0  ldstr    aMinidumpdisabl// "MiniDumpDisabled"
0x670a5  ldc.i4.1
0x670a6  box      [mscorlib]System.Int32
0x670ab  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x670b0  unbox.any [mscorlib]System.Int32
0x670b5  ldc.i4.0
0x670b6  cgt.un
0x670b8  stloc.0
0x670b9  ldstr    aTracedirectory// "TraceDirectory"
0x670be  call     object Microsoft.Crm.RegistryCache::GetValue(string key)
0x670c3  castclass [mscorlib]System.String
0x670c8  stloc.1
0x670c9  ldloc.1
0x670ca  brfalse.s loc_670D4
0x670cc  ldloc.1
0x670cd  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x670d2  brtrue.s loc_670F9
0x670d4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x670d9  ldc.i4.s 0x14
0x670db  ldstr    a0// "{0}"
0x670e0  ldc.i4.1
0x670e1  newarr   [mscorlib]System.Object
0x670e6  dup
0x670e7  ldc.i4.0
0x670e8  ldstr    aMinidumpTraced// "MiniDump: TraceDirectory setting not se"...
0x670ed  stelem.ref
0x670ee  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x670f3  call     string [mscorlib]System.IO.Path::GetTempPath()
0x670f8  stloc.1
0x670f9  ldsfld   string [mscorlib]System.String::Empty
0x670fe  stloc.2
0x670ff  ldstr    aMinidumpcheckc// "MiniDumpCheckCommand"
0x67104  ldc.i4.0
0x67105  box      [mscorlib]System.Int32
0x6710a  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x6710f  unbox.any [mscorlib]System.Int32
0x67114  brfalse.s loc_67159
0x67116  ldstr    aMinidumpcomman// "MiniDumpCommand"
0x6711b  ldstr    aWindirSystem32// "%WINDIR%\\system32\\ntsd.exe"
0x67120  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x67125  castclass [mscorlib]System.String
0x6712a  call     string [mscorlib]System.Environment::ExpandEnvironmentVariables(string)
0x6712f  stloc.2
0x67130  ldloc.2
0x67131  call     bool [mscorlib]System.IO.File::Exists(string)
0x67136  brtrue.s loc_67159
0x67138  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x6713d  ldc.i4.s 0x14
0x6713f  ldstr    aMinidumpDidNot// "MiniDump did not find the MiniDumpComma"...
0x67144  ldc.i4.1
0x67145  newarr   [mscorlib]System.Object
0x6714a  dup
0x6714b  ldc.i4.0
0x6714c  ldloc.2
0x6714d  stelem.ref
0x6714e  call     void Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x67153  ldsfld   string [mscorlib]System.String::Empty
0x67158  stloc.2
0x67159  ldstr    aMinidumpargume// "MiniDumpArguments"
0x6715e  ldstr    aGP0PvYSrvHttpM// "-g -p {0} -pv -y srv**http://msdl.micro"...
0x67163  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x67168  castclass [mscorlib]System.String
0x6716d  stloc.3
0x6716e  ldstr    aMinidumpcondit// "MiniDumpConditions"
0x67173  ldstr    aNone// "None"
0x67178  call     object Microsoft.Crm.RegistryCache::GetValue(string key, object defaultValue)
0x6717d  castclass [mscorlib]System.String
0x67182  stloc.s  4
0x67184  ldtoken  Microsoft.Crm.MiniDumpReasons
0x67189  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6718e  ldloc.s  4
0x67190  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x67195  unbox.any Microsoft.Crm.MiniDumpReasons
0x6719a  stloc.s  5
0x6719c  ldloc.s  5
0x6719e  ldc.i4.8
0x6719f  or
0x671a0  stloc.s  5
0x671a2  ldloc.0
0x671a3  ldloc.1
0x671a4  ldloc.2
0x671a5  ldloc.3
0x671a6  ldloc.s  5
0x671a8  newobj   instance void MiniDumpSettings::.ctor(bool dumpDisabled, string dumpDirectory, string dumpCommand, string dumpArgumentsFormat, valuetype Microsoft.Crm.MiniDumpReasons conditions)
0x671ad  stloc.s  6
0x671af  leave.s  loc_671DB
0x671b1  stloc.s  7
0x671b3  ldloc.s  7
0x671b5  call     valuetype [mscorlib]System.Guid Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x671ba  ldc.i4.s 0x14
0x671bc  ldstr    aExceptionWhile_2// "Exception while loading mini-dump setti"...
0x671c1  ldc.i4.2
0x671c2  newarr   [mscorlib]System.Object
0x671c7  dup
0x671c8  ldc.i4.0
0x671c9  call     string [mscorlib]System.Environment::get_NewLine()
0x671ce  stelem.ref
0x671cf  dup
0x671d0  ldc.i4.1
0x671d1  ldloc.s  7
0x671d3  stelem.ref
0x671d4  call     void Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception ex, valuetype [mscorlib]System.Guid orgId, valuetype Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x671d9  rethrow
0x671db  ldloc.s  6
0x671dd  ret
```
