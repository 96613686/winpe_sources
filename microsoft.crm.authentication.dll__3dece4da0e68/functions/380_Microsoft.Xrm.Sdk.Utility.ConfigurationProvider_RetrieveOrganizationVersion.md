# Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::RetrieveOrganizationVersion

- ea: `0x380`
- end: `0x409`
- name: `Microsoft.Xrm.Sdk.Utility.ConfigurationProvider::RetrieveOrganizationVersion`
- size: `137`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x330`
- `0x680`

## callees

- `0x380`

## pseudocode

```c

```

## disassembly

```asm
0x380  ldarg.2
0x381  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetContextInstance(valuetype [Microsoft.Crm.Core]Microsoft.Crm.LocatorServiceContext)
0x386  ldarg.1
0x387  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::GetOrganization(valuetype [mscorlib]System.Guid)
0x38c  stloc.0
0x38d  ldloc.0
0x38e  ldstr    aMajorversion// "MajorVersion"
0x393  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x398  brfalse.s loc_407
0x39a  ldloc.0
0x39b  ldstr    aMinorversion// "MinorVersion"
0x3a0  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x3a5  brfalse.s loc_407
0x3a7  ldloc.0
0x3a8  ldstr    aBuildnumber// "BuildNumber"
0x3ad  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x3b2  brfalse.s loc_407
0x3b4  ldloc.0
0x3b5  ldstr    aRevision// "Revision"
0x3ba  callvirt instance bool [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::Contains(string)
0x3bf  brfalse.s loc_407
0x3c1  ldloc.0
0x3c2  ldstr    aMajorversion// "MajorVersion"
0x3c7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3cc  unbox.any [mscorlib]System.Int32
0x3d1  ldloc.0
0x3d2  ldstr    aMinorversion// "MinorVersion"
0x3d7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3dc  unbox.any [mscorlib]System.Int32
0x3e1  ldloc.0
0x3e2  ldstr    aBuildnumber// "BuildNumber"
0x3e7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3ec  unbox.any [mscorlib]System.Int32
0x3f1  ldloc.0
0x3f2  ldstr    aRevision// "Revision"
0x3f7  callvirt instance object [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag::get_Item(string)
0x3fc  unbox.any [mscorlib]System.Int32
0x401  newobj   instance void [mscorlib]System.Version::.ctor(int32, int32, int32, int32)
0x406  ret
0x407  ldnull
0x408  ret
```
