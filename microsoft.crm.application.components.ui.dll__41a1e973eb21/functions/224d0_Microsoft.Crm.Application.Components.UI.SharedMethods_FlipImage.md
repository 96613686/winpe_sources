# Microsoft.Crm.Application.Components.UI.SharedMethods::FlipImage

- ea: `0x224d0`
- end: `0x225ed`
- name: `Microsoft.Crm.Application.Components.UI.SharedMethods::FlipImage`
- size: `285`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x101a0`
- `0x10990`
- `0x11d80`
- `0x196d0`
- `0x1c0f0`
- `0x29980`

## callees

- `0x224d0`

## pseudocode

```c

```

## disassembly

```asm
0x224d0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x224d5  stloc.0
0x224d6  ldstr    aScalex1// "scaleX(-1);"
0x224db  stloc.1
0x224dc  ldstr    aFliph// "FlipH();"
0x224e1  stloc.2
0x224e2  ldarg.0
0x224e3  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x224e8  ldstr    aH_0// "H"
0x224ed  call     bool [mscorlib]System.String::op_Equality(string, string)
0x224f2  brfalse.s loc_22502
0x224f4  ldstr    aScalex1// "scaleX(-1);"
0x224f9  stloc.1
0x224fa  ldstr    aFliph// "FlipH();"
0x224ff  stloc.2
0x22500  br.s     loc_22540
0x22502  ldarg.0
0x22503  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x22508  ldstr    aV// "V"
0x2250d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22512  brfalse.s loc_22522
0x22514  ldstr    aScaley1// "scaleY(-1);"
0x22519  stloc.1
0x2251a  ldstr    aFlipv// "FlipV();"
0x2251f  stloc.2
0x22520  br.s     loc_22540
0x22522  ldarg.0
0x22523  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x22528  ldstr    aHv// "HV"
0x2252d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x22532  brfalse.s loc_22540
0x22534  ldstr    aScale1// "scale(-1);"
0x22539  stloc.1
0x2253a  ldstr    aFliphFlipv// "FlipH() FlipV();"
0x2253f  stloc.2
0x22540  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x22545  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2254a  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x2254f  callvirt instance string [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_Browser()
0x22554  ldstr    aIe// "IE"
0x22559  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2255e  brfalse.s loc_2258C
0x22560  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x22565  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x2256a  callvirt instance class [System.Web]System.Web.HttpBrowserCapabilities [System.Web]System.Web.HttpRequest::get_Browser()
0x2256f  callvirt instance int32 [System.Web]System.Web.Configuration.HttpCapabilitiesBase::get_MajorVersion()
0x22574  ldc.i4.s 0xA
0x22576  blt.s    loc_2258C
0x22578  ldloc.0
0x22579  ldstr    aMsTransform// "-ms-transform:"
0x2257e  ldloc.1
0x2257f  call     string [mscorlib]System.String::Concat(string, string)
0x22584  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x22589  pop
0x2258a  br.s     loc_2259E
0x2258c  ldloc.0
0x2258d  ldstr    aFilter// "filter:"
0x22592  ldloc.2
0x22593  call     string [mscorlib]System.String::Concat(string, string)
0x22598  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x2259d  pop
0x2259e  ldloc.0
0x2259f  ldstr    aWebkitTransfor// "-webkit-transform:"
0x225a4  ldloc.1
0x225a5  call     string [mscorlib]System.String::Concat(string, string)
0x225aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x225af  pop
0x225b0  ldloc.0
0x225b1  ldstr    aMozTransform// "-moz-transform:"
0x225b6  ldloc.1
0x225b7  call     string [mscorlib]System.String::Concat(string, string)
0x225bc  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x225c1  pop
0x225c2  ldloc.0
0x225c3  ldstr    aOTransform// "-o-transform:"
0x225c8  ldloc.1
0x225c9  call     string [mscorlib]System.String::Concat(string, string)
0x225ce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x225d3  pop
0x225d4  ldloc.0
0x225d5  ldstr    aTransform// "transform:"
0x225da  ldloc.1
0x225db  call     string [mscorlib]System.String::Concat(string, string)
0x225e0  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x225e5  pop
0x225e6  ldloc.0
0x225e7  callvirt instance string [mscorlib]System.Object::ToString()
0x225ec  ret
```
