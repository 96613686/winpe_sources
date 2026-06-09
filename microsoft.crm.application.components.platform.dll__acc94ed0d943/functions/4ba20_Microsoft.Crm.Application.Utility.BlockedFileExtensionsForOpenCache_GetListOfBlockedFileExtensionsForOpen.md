# Microsoft.Crm.Application.Utility.BlockedFileExtensionsForOpenCache::GetListOfBlockedFileExtensionsForOpen

- ea: `0x4ba20`
- end: `0x4baa5`
- name: `Microsoft.Crm.Application.Utility.BlockedFileExtensionsForOpenCache::GetListOfBlockedFileExtensionsForOpen`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x44640`

## callees

- `0x4ba20`

## string_xrefs

- `0x4ba2a`: `MSCRMListOfBlockedFileExtensionsForOpen`
- `0x4ba92`: `MSCRMListOfBlockedFileExtensionsForOpen`
- `0x4ba3d`: `BlockedFileExtensionsForOpen.txt`
- `0x4ba6c`: `Unable to read file :`

## pseudocode

```c

```

## disassembly

```asm
0x4ba20  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x4ba25  callvirt instance class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpContext::get_Cache()
0x4ba2a  ldstr    aMscrmlistofblo// "MSCRMListOfBlockedFileExtensionsForOpen"
0x4ba2f  callvirt instance object [System.Web]System.Web.Caching.Cache::get_Item(string)
0x4ba34  castclass string[]
0x4ba39  stloc.0
0x4ba3a  ldloc.0
0x4ba3b  brtrue.s loc_4BAA3
0x4ba3d  ldstr    aBlockedfileext// "BlockedFileExtensionsForOpen.txt"
0x4ba42  call     string [Microsoft.Crm]Microsoft.Crm.ApplicationFileManager::GetApplicationFilePath(string)
0x4ba47  stloc.1
0x4ba48  ldloc.1
0x4ba49  call     string [mscorlib]System.IO.File::ReadAllText(string)
0x4ba4e  stloc.2
0x4ba4f  ldloc.2
0x4ba50  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4ba55  brtrue.s loc_4BA69
0x4ba57  ldloc.2
0x4ba58  ldc.i4.1
0x4ba59  newarr   [mscorlib]System.Char
0x4ba5e  dup
0x4ba5f  ldc.i4.0
0x4ba60  ldc.i4.s 0x3B
0x4ba62  stelem.i2
0x4ba63  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x4ba68  stloc.0
0x4ba69  leave.s  loc_4BA7E
0x4ba6b  stloc.3
0x4ba6c  ldstr    aUnableToReadFi// "Unable to read file :"
0x4ba71  ldloc.1
0x4ba72  call     string [mscorlib]System.String::Concat(string, string)
0x4ba77  ldloc.3
0x4ba78  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x4ba7d  throw
0x4ba7e  ldloc.0
0x4ba7f  brtrue.s loc_4BA88
0x4ba81  ldc.i4.1
0x4ba82  newarr   [mscorlib]System.String
0x4ba87  stloc.0
0x4ba88  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x4ba8d  callvirt instance class [System.Web]System.Web.Caching.Cache [System.Web]System.Web.HttpContext::get_Cache()
0x4ba92  ldstr    aMscrmlistofblo// "MSCRMListOfBlockedFileExtensionsForOpen"
0x4ba97  ldloc.0
0x4ba98  ldloc.1
0x4ba99  newobj   instance void [System.Web]System.Web.Caching.CacheDependency::.ctor(string)
0x4ba9e  callvirt instance void [System.Web]System.Web.Caching.Cache::Insert(string, object, class [System.Web]System.Web.Caching.CacheDependency)
0x4baa3  ldloc.0
0x4baa4  ret
```
