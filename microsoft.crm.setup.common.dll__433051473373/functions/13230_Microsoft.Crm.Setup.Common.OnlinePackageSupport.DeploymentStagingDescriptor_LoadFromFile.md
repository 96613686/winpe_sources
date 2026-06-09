# Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::LoadFromFile

- ea: `0x13230`
- end: `0x132f2`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::LoadFromFile`
- size: `194`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0x16310`

## callees

- `0x131f0`
- `0x13210`
- `0x13230`
- `0x13450`
- `0x14db0`

## string_xrefs

- `0x13231`: `filePath must be provided to load RollbackDescriptor from file`
- `0x13243`: `Installation Rollback Descriptor file {0} not found`
- `0x132d0`: `Error occurred while parsing rollback descriptor file {0}: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x13230  ldarg.0
0x13231  ldstr    aFilepathMustBe// "filePath must be provided to load Rollb"...
0x13236  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x1323b  ldarg.0
0x1323c  call     bool [mscorlib]System.IO.File::Exists(string)
0x13241  brtrue.s loc_1325D
0x13243  ldstr    aInstallationRo// "Installation Rollback Descriptor file {"...
0x13248  ldc.i4.1
0x13249  newarr   [mscorlib]System.Object
0x1324e  dup
0x1324f  ldc.i4.0
0x13250  ldarg.0
0x13251  stelem.ref
0x13252  call     string [Microsoft.Crm.Core]Microsoft.Crm.Core.Helpers.StringExtensions::FormatInvariant(string, object[])
0x13257  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1325c  throw
0x1325d  ldarg.0
0x1325e  call     T0x2B000013
0x13263  stloc.0
0x13264  ldloc.0
0x13265  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_FileSystemOperations()
0x1326a  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::GetEnumerator()
0x1326f  stloc.1
0x13270  br.s     loc_1327E
0x13272  ldloca.s 1
0x13274  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::get_Current()
0x13279  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation::VerifyDescriptorConsistency()
0x1327e  ldloca.s 1
0x13280  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>::MoveNext()
0x13285  brtrue.s loc_13272
0x13287  leave.s  loc_13297
0x13289  ldloca.s 1
0x1328b  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.FileSystemOperation>
0x13291  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13296  endfinally
0x13297  ldloc.0
0x13298  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation> Microsoft.Crm.Setup.Common.OnlinePackageSupport.DeploymentStagingDescriptor::get_RegistryOperations()
0x1329d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::GetEnumerator()
0x132a2  stloc.2
0x132a3  br.s     loc_132B1
0x132a5  ldloca.s 2
0x132a7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::get_Current()
0x132ac  callvirt instance void Microsoft.Crm.Setup.Common.OnlinePackageSupport.DescriptorElementBase::VerifyDescriptorConsistency()
0x132b1  ldloca.s 2
0x132b3  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>::MoveNext()
0x132b8  brtrue.s loc_132A5
0x132ba  leave.s  loc_132CA
0x132bc  ldloca.s 2
0x132be  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.Crm.Setup.Common.OnlinePackageSupport.RegistryOperation>
0x132c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x132c9  endfinally
0x132ca  ldloc.0
0x132cb  stloc.3
0x132cc  leave.s  loc_132F0
0x132ce  stloc.s  4
0x132d0  ldstr    aErrorOccurredW// "Error occurred while parsing rollback d"...
0x132d5  ldc.i4.2
0x132d6  newarr   [mscorlib]System.Object
0x132db  dup
0x132dc  ldc.i4.0
0x132dd  ldarg.0
0x132de  stelem.ref
0x132df  dup
0x132e0  ldc.i4.1
0x132e1  ldloc.s  4
0x132e3  callvirt instance string [mscorlib]System.Exception::get_Message()
0x132e8  stelem.ref
0x132e9  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteErrorFormat(string, object[])
0x132ee  rethrow
0x132f0  ldloc.3
0x132f1  ret
```
