# Microsoft.Crm.CoverPages::GetCoverPageDirectory

- ea: `0x1b7f0`
- end: `0x1b856`
- name: `Microsoft.Crm.CoverPages::GetCoverPageDirectory`
- size: `102`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1b730`

## callees

- `0x1b7f0`

## string_xrefs

- `0x1b7f0`: `FaxCoverPageDirectory`
- `0x1b827`: `Microsoft\Windows NT\MSFax\Common Coverpages`
- `0x1b849`: `Documents\My Faxes\Common Coverpages`

## pseudocode

```c

```

## disassembly

```asm
0x1b7f0  ldstr    aFaxcoverpagedi// "FaxCoverPageDirectory"
0x1b7f5  ldnull
0x1b7f6  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string, object)
0x1b7fb  castclass [mscorlib]System.String
0x1b800  stloc.0
0x1b801  ldloc.0
0x1b802  brtrue.s loc_1B854
0x1b804  ldc.i4.5
0x1b805  ldc.i4.2
0x1b806  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32)
0x1b80b  stloc.1
0x1b80c  call     class [mscorlib]System.OperatingSystem [mscorlib]System.Environment::get_OSVersion()
0x1b811  callvirt instance class [mscorlib]System.Version [mscorlib]System.OperatingSystem::get_Version()
0x1b816  ldloc.1
0x1b817  call     bool [mscorlib]System.Version::op_GreaterThanOrEqual(class [mscorlib]System.Version, class [mscorlib]System.Version)
0x1b81c  brfalse.s loc_1B834
0x1b81e  ldc.i4.s 0x23
0x1b820  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x1b825  stloc.0
0x1b826  ldloc.0
0x1b827  ldstr    aMicrosoftWindo// "Microsoft\\Windows NT\\MSFax\\Common Co"...
0x1b82c  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1b831  stloc.0
0x1b832  br.s     loc_1B854
0x1b834  ldc.i4.s 0x23
0x1b836  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x1b83b  stloc.0
0x1b83c  ldloc.0
0x1b83d  call     class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.Directory::GetParent(string)
0x1b842  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x1b847  stloc.0
0x1b848  ldloc.0
0x1b849  ldstr    aDocumentsMyFax// "Documents\\My Faxes\\Common Coverpages"
0x1b84e  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1b853  stloc.0
0x1b854  ldloc.0
0x1b855  ret
```
