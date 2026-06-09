# Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CalculateEndpoints

- ea: `0x161e0`
- end: `0x1629a`
- name: `Microsoft.Xrm.Sdk.Client.ServiceConfiguration`1::CalculateEndpoints`
- size: `186`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x161e0`
- `0x17670`
- `0x17690`
- `0x176b0`
- `0x176c0`

## pseudocode

```c

```

## disassembly

```asm
0x161e0  newobj   instance void Microsoft.Xrm.Sdk.Client.ServiceUrls::.ctor()
0x161e5  stloc.0
0x161e6  ldarg.0
0x161e7  newobj   instance void [System]System.UriBuilder::.ctor(class [System]System.Uri)
0x161ec  stloc.1
0x161ed  ldloc.1
0x161ee  callvirt instance string [System]System.UriBuilder::get_Host()
0x161f3  ldc.i4.1
0x161f4  newarr   [mscorlib]System.Char
0x161f9  dup
0x161fa  ldc.i4.0
0x161fb  ldc.i4.s 0x2E
0x161fd  stelem.i2
0x161fe  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x16203  stloc.2
0x16204  ldloc.2
0x16205  ldc.i4.0
0x16206  ldelem.ref
0x16207  ldstr    aS// "--s"
0x1620c  ldc.i4.5
0x1620d  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x16212  brfalse.s loc_1625B
0x16214  ldloc.0
0x16215  ldloc.1
0x16216  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x1621b  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceUrls::set_AlternateEndpoint(class [System]System.Uri value)
0x16220  ldloc.2
0x16221  ldc.i4.0
0x16222  ldloc.2
0x16223  ldc.i4.0
0x16224  ldelem.ref
0x16225  ldloc.2
0x16226  ldc.i4.0
0x16227  ldelem.ref
0x16228  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1622d  ldc.i4.3
0x1622e  sub
0x1622f  callvirt instance string [mscorlib]System.String::Remove(int32)
0x16234  stelem.ref
0x16235  ldloc.1
0x16236  ldstr    asc_2B914// "."
0x1623b  ldloc.2
0x1623c  call     string [mscorlib]System.String::Join(string, string[])
0x16241  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x16246  ldloc.0
0x16247  ldloc.1
0x16248  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x1624d  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceUrls::set_PrimaryEndpoint(class [System]System.Uri value)
0x16252  ldloc.0
0x16253  ldc.i4.1
0x16254  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceUrls::set_GeneratedFromAlternate(bool value)
0x16259  br.s     loc_16298
0x1625b  ldloc.0
0x1625c  ldloc.1
0x1625d  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x16262  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceUrls::set_PrimaryEndpoint(class [System]System.Uri value)
0x16267  ldloc.2
0x16268  ldc.i4.0
0x16269  ldelema  [mscorlib]System.String
0x1626e  dup
0x1626f  ldind.ref
0x16270  ldstr    aS// "--s"
0x16275  call     string [mscorlib]System.String::Concat(string, string)
0x1627a  stind.ref
0x1627b  ldloc.1
0x1627c  ldstr    asc_2B914// "."
0x16281  ldloc.2
0x16282  call     string [mscorlib]System.String::Join(string, string[])
0x16287  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x1628c  ldloc.0
0x1628d  ldloc.1
0x1628e  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x16293  callvirt instance void Microsoft.Xrm.Sdk.Client.ServiceUrls::set_AlternateEndpoint(class [System]System.Uri value)
0x16298  ldloc.0
0x16299  ret
```
