# Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::RemoveOrgName

- ea: `0x18990`
- end: `0x189f9`
- name: `Microsoft.Xrm.Sdk.Client.OrganizationServiceConfiguration::RemoveOrgName`
- size: `105`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18910`

## callees

- `0x18990`

## string_xrefs

- `0x18996`: `/xrmservices/`

## pseudocode

```c

```

## disassembly

```asm
0x18990  ldarg.0
0x18991  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x18996  ldstr    aXrmservices// "/xrmservices/"
0x1899b  ldc.i4.5
0x1899c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x189a1  brtrue.s loc_189F7
0x189a3  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x189a8  stloc.0
0x189a9  ldc.i4.2
0x189aa  stloc.1
0x189ab  br.s     loc_189C0
0x189ad  ldloc.0
0x189ae  ldarg.0
0x189af  callvirt instance string[] [System]System.Uri::get_Segments()
0x189b4  ldloc.1
0x189b5  ldelem.ref
0x189b6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x189bb  pop
0x189bc  ldloc.1
0x189bd  ldc.i4.1
0x189be  add
0x189bf  stloc.1
0x189c0  ldloc.1
0x189c1  ldarg.0
0x189c2  callvirt instance string[] [System]System.Uri::get_Segments()
0x189c7  ldlen
0x189c8  conv.i4
0x189c9  blt.s    loc_189AD
0x189cb  ldloc.0
0x189cc  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x189d1  ldc.i4.0
0x189d2  ble.s    loc_189F7
0x189d4  ldarg.0
0x189d5  ldc.i4.s 0xD
0x189d7  ldc.i4.1
0x189d8  callvirt instance string [System]System.Uri::GetComponents(valuetype [System]System.UriComponents, valuetype [System]System.UriFormat)
0x189dd  newobj   instance void [System]System.UriBuilder::.ctor(string)
0x189e2  dup
0x189e3  ldloc.0
0x189e4  callvirt instance string [mscorlib]System.Object::ToString()
0x189e9  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x189ee  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x189f3  starg.s  0
0x189f5  ldarg.0
0x189f6  ret
0x189f7  ldnull
0x189f8  ret
```
