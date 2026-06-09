# Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::PreparePackage

- ea: `0x23450`
- end: `0x23584`
- name: `Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::PreparePackage`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x23590`

## callees

- `0x23410`
- `0x23450`
- `0x236c0`
- `0x23740`

## string_xrefs

- `0x234a1`: `SolutionPackageCache: Downloading solution package {0} from {1} to {2}.`
- `0x234d2`: `SolutionPackageCache: Extracting solution package {0} to {1}.`
- `0x23514`: `SolutionPackageCache: Solution package {0} is found in the cache: {1}.`
- `0x23532`: `*.dll`

## pseudocode

```c

```

## disassembly

```asm
0x23450  ldarg.0
0x23451  ldfld    object Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::_locker
0x23456  stloc.0
0x23457  ldc.i4.0
0x23458  stloc.1
0x23459  ldloc.0
0x2345a  ldloca.s 1
0x2345c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x23461  ldarg.1
0x23462  ldarg.2
0x23463  call     string Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::GenerateDirectoryKeyName(valuetype [mscorlib]System.Guid packageId, string packageUrl)
0x23468  stloc.2
0x23469  ldarg.0
0x2346a  ldfld    string Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::_cachePath
0x2346f  ldloc.2
0x23470  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x23475  stloc.3
0x23476  ldloc.3
0x23477  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x2347c  brtrue   loc_2350D
0x23481  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x23486  stloc.s  5
0x23488  ldarg.0
0x23489  ldfld    string Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::_cachePath
0x2348e  call     string [mscorlib]System.IO.Path::GetRandomFileName()
0x23493  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x23498  stloc.s  6
0x2349a  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x2349f  ldc.i4.s 0xA
0x234a1  ldstr    aSolutionpackag_5// "SolutionPackageCache: Downloading solut"...
0x234a6  ldc.i4.3
0x234a7  newarr   [mscorlib]System.Object
0x234ac  dup
0x234ad  ldc.i4.0
0x234ae  ldarg.1
0x234af  box      [mscorlib]System.Guid
0x234b4  stelem.ref
0x234b5  dup
0x234b6  ldc.i4.1
0x234b7  ldarg.2
0x234b8  stelem.ref
0x234b9  dup
0x234ba  ldc.i4.2
0x234bb  ldloc.s  6
0x234bd  stelem.ref
0x234be  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x234c3  ldarg.2
0x234c4  ldloc.s  6
0x234c6  call     void Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::DownloadPackageWithRetry(string url, string fileName)
0x234cb  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x234d0  ldc.i4.s 0xA
0x234d2  ldstr    aSolutionpackag_6// "SolutionPackageCache: Extracting soluti"...
0x234d7  ldc.i4.2
0x234d8  newarr   [mscorlib]System.Object
0x234dd  dup
0x234de  ldc.i4.0
0x234df  ldarg.1
0x234e0  box      [mscorlib]System.Guid
0x234e5  stelem.ref
0x234e6  dup
0x234e7  ldc.i4.1
0x234e8  ldloc.3
0x234e9  stelem.ref
0x234ea  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x234ef  ldloc.s  6
0x234f1  ldloc.3
0x234f2  call     void Microsoft.Crm.CrmLive.Provisioning.SolutionPackageCache::ExtractPackage(string packageFileName, string destinationPath)
0x234f7  leave.s  loc_23531
0x234f9  ldloc.s  6
0x234fb  call     void [mscorlib]System.IO.File::Delete(string)
0x23500  endfinally
0x23501  ldloc.s  5
0x23503  brfalse.s loc_2350C
0x23505  ldloc.s  5
0x23507  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2350c  endfinally
0x2350d  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x23512  ldc.i4.s 0xA
0x23514  ldstr    aSolutionpackag_7// "SolutionPackageCache: Solution package "...
0x23519  ldc.i4.2
0x2351a  newarr   [mscorlib]System.Object
0x2351f  dup
0x23520  ldc.i4.0
0x23521  ldarg.1
0x23522  box      [mscorlib]System.Guid
0x23527  stelem.ref
0x23528  dup
0x23529  ldc.i4.1
0x2352a  ldloc.3
0x2352b  stelem.ref
0x2352c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x23531  ldloc.3
0x23532  ldstr    aDll// "*.dll"
0x23537  ldc.i4.0
0x23538  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<string> [mscorlib]System.IO.Directory::EnumerateFiles(string, string, valuetype [mscorlib]System.IO.SearchOption)
0x2353d  call     T0x2B0000A2
0x23542  stloc.s  4
0x23544  ldloc.s  4
0x23546  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2354b  brfalse.s loc_23571
0x2354d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x23552  ldstr    aCouldNotFindPa// "Could not find package assembly in solu"...
0x23557  ldc.i4.1
0x23558  newarr   [mscorlib]System.Object
0x2355d  dup
0x2355e  ldc.i4.0
0x2355f  ldarg.1
0x23560  box      [mscorlib]System.Guid
0x23565  stelem.ref
0x23566  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x2356b  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x23570  throw
0x23571  ldloc.s  4
0x23573  stloc.s  7
0x23575  leave.s  loc_23581
0x23577  ldloc.1
0x23578  brfalse.s loc_23580
0x2357a  ldloc.0
0x2357b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x23580  endfinally
0x23581  ldloc.s  7
0x23583  ret
```
