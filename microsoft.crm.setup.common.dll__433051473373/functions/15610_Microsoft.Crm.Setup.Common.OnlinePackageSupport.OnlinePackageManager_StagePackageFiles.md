# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::StagePackageFiles

- ea: `0x15610`
- end: `0x156d8`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::StagePackageFiles`
- size: `200`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15340`

## callees

- `0x14710`
- `0x14730`
- `0x14770`
- `0x149c0`
- `0x14a00`
- `0x14d40`
- `0x15610`
- `0x156e0`
- `0x15720`

## string_xrefs

- `0x1561b`: `Expected to find at least one installPointElement`
- `0x15659`: `Processing InstallPoint {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15610  ldarg.1
0x15611  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint> Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_InstallationPoints()
0x15616  call     T0x2B000019
0x1561b  ldstr    aExpectedToFind// "Expected to find at least one installPo"...
0x15620  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x15625  ldstr    aStagingFilesFr// "---------- Staging files from {0} packa"...
0x1562a  ldc.i4.1
0x1562b  newarr   [mscorlib]System.Object
0x15630  dup
0x15631  ldc.i4.0
0x15632  ldarg.1
0x15633  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackage Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_Package()
0x15638  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::get_Name()
0x1563d  stelem.ref
0x1563e  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15643  ldarg.1
0x15644  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint> Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_InstallationPoints()
0x15649  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::GetEnumerator()
0x1564e  stloc.0
0x1564f  br.s     loc_156BE
0x15651  ldloca.s 0
0x15653  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::get_Current()
0x15658  stloc.1
0x15659  ldstr    aProcessingInst// "Processing InstallPoint {0}"
0x1565e  ldc.i4.1
0x1565f  newarr   [mscorlib]System.Object
0x15664  dup
0x15665  ldc.i4.0
0x15666  ldloc.1
0x15667  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::get_Name()
0x1566c  stelem.ref
0x1566d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x15672  ldarg.1
0x15673  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::get_PackagePath()
0x15678  ldloc.1
0x15679  callvirt instance class Microsoft.Crm.Setup.Common.OnlinePackageSupport.ZipFileDescriptor Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::get_ZipFileDescriptor()
0x1567e  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.NamedDescriptorElement::get_Name()
0x15683  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x15688  stloc.2
0x15689  ldloc.2
0x1568a  call     bool [mscorlib]System.IO.File::Exists(string)
0x1568f  ldstr    aZipFile0NotFou// "Zip file {0} not found"
0x15694  ldc.i4.1
0x15695  newarr   [mscorlib]System.Object
0x1569a  dup
0x1569b  ldc.i4.0
0x1569c  ldloc.2
0x1569d  stelem.ref
0x1569e  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x156a3  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x156a8  ldarg.0
0x156a9  ldloc.1
0x156aa  callvirt instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint::get_Location()
0x156af  call     instance string Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::GetStagingPathForInstallLocation(string installPointLocation)
0x156b4  stloc.3
0x156b5  ldarg.0
0x156b6  ldloc.2
0x156b7  ldloc.3
0x156b8  ldnull
0x156b9  call     instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageManager::ExtractZipContents(string zipFilePath, string targetFolder, class Microsoft.Crm.Setup.Common.OnlinePackageSupport.LockedFileHandler lockedFileHandler)
0x156be  ldloca.s 0
0x156c0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>::MoveNext()
0x156c5  brtrue.s loc_15651
0x156c7  leave.s  loc_156D7
0x156c9  ldloca.s 0
0x156cb  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.InstallationPoint>
0x156d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x156d6  endfinally
0x156d7  ret
```
