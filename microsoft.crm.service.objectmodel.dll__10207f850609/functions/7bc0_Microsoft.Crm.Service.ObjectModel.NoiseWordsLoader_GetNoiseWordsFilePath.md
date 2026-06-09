# Microsoft.Crm.Service.ObjectModel.NoiseWordsLoader::GetNoiseWordsFilePath

- ea: `0x7bc0`
- end: `0x7c19`
- name: `Microsoft.Crm.Service.ObjectModel.NoiseWordsLoader::GetNoiseWordsFilePath`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x7b30`

## callees

- `0x7bc0`

## string_xrefs

- `0x7bc7`: `CRM_Client_InstallDir`

## pseudocode

```c

```

## disassembly

```asm
0x7bc0  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInClientContext()
0x7bc5  brfalse.s loc_7BE3
0x7bc7  ldstr    aCrmClientInsta// "CRM_Client_InstallDir"
0x7bcc  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x7bd1  castclass [mscorlib]System.String
0x7bd6  ldstr    aClientResWebHe// "Client\\res\\web\\help\\noisewords"
0x7bdb  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7be0  stloc.0
0x7be1  br.s     loc_7BF8
0x7be3  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x7be8  callvirt instance class [System.Web]System.Web.HttpServerUtility [System.Web]System.Web.HttpContext::get_Server()
0x7bed  ldstr    aHelpNoisewords// "/help/noisewords"
0x7bf2  callvirt instance string [System.Web]System.Web.HttpServerUtility::MapPath(string)
0x7bf7  stloc.0
0x7bf8  ldloc.0
0x7bf9  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x7bfe  brtrue.s loc_7C0B
0x7c00  ldstr    aNoiseWordsFile// "Noise words file cannot be found."
0x7c05  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x7c0a  throw
0x7c0b  ldloc.0
0x7c0c  ldarg.0
0x7c0d  ldarg.1
0x7c0e  call     instance string [Microsoft.Crm]Microsoft.Crm.NoiseWordsLoaderBase::GetNoiseWordsFileName(int32)
0x7c13  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x7c18  ret
```
