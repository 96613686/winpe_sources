# Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::LoadFromFile

- ea: `0x14830`
- end: `0x148d4`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::LoadFromFile`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x148e0`

## callees

- `0x14780`
- `0x147b0`
- `0x14830`
- `0x14db0`
- `0x14dc0`

## string_xrefs

- `0x14831`: `filePath must be provided to load OnlinePackageDescriptor from file`
- `0x14843`: `Online Package Descriptor file {0} not found`
- `0x1485d`: `Parsing package descriptor {0}`
- `0x148a0`: `Error occurred while parsing online package descriptor file {0}: `

## pseudocode

```c

```

## disassembly

```asm
0x14830  ldarg.0
0x14831  ldstr    aFilepathMustBe_1// "filePath must be provided to load Onlin"...
0x14836  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1483b  ldarg.0
0x1483c  call     bool [mscorlib]System.IO.File::Exists(string)
0x14841  brtrue.s loc_1485D
0x14843  ldstr    aOnlinePackageD// "Online Package Descriptor file {0} not "...
0x14848  ldc.i4.1
0x14849  newarr   [mscorlib]System.Object
0x1484e  dup
0x1484f  ldc.i4.0
0x14850  ldarg.0
0x14851  stelem.ref
0x14852  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x14857  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1485c  throw
0x1485d  ldstr    aParsingPackage// "Parsing package descriptor {0}"
0x14862  ldc.i4.1
0x14863  newarr   [mscorlib]System.Object
0x14868  dup
0x14869  ldc.i4.0
0x1486a  ldarg.0
0x1486b  stelem.ref
0x1486c  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x14871  ldarg.0
0x14872  call     T0x2B000017
0x14877  stloc.0
0x14878  ldloc.0
0x14879  ldarg.0
0x1487a  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x1487f  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::set_PackagePath(string value)
0x14884  ldloc.0
0x14885  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::VerifyDescriptorConsistency()
0x1488a  ldarg.1
0x1488b  brfalse.s loc_1489B
0x1488d  ldloc.0
0x1488e  ldarg.1
0x1488f  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.OnlinePackageDescriptor::set_TokenMap(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap value)
0x14894  ldloc.0
0x14895  ldarg.1
0x14896  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::ReplaceTokenValues(class Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap tokenMap)
0x1489b  ldloc.0
0x1489c  stloc.1
0x1489d  leave.s  loc_148D2
0x1489f  stloc.2
0x148a0  ldstr    aErrorOccurredW_0// "Error occurred while parsing online pac"...
0x148a5  ldc.i4.2
0x148a6  newarr   [mscorlib]System.Object
0x148ab  dup
0x148ac  ldc.i4.0
0x148ad  ldarg.0
0x148ae  stelem.ref
0x148af  dup
0x148b0  ldc.i4.1
0x148b1  ldloc.2
0x148b2  callvirt instance string [mscorlib]System.Exception::get_Message()
0x148b7  stelem.ref
0x148b8  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x148bd  stloc.3
0x148be  ldloc.3
0x148bf  ldc.i4.0
0x148c0  newarr   [mscorlib]System.Object
0x148c5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x148ca  ldloc.3
0x148cb  ldloc.2
0x148cc  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, class [mscorlib]System.Exception)
0x148d1  throw
0x148d2  ldloc.1
0x148d3  ret
```
