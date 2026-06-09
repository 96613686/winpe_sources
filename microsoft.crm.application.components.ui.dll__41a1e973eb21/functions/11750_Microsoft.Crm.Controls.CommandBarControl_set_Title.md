# Microsoft.Crm.Controls.CommandBarControl::set_Title

- ea: `0x11750`
- end: `0x117f9`
- name: `Microsoft.Crm.Controls.CommandBarControl::set_Title`
- size: `169`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf1e0`
- `0xf220`
- `0xf4a0`
- `0xf5f0`
- `0xfe00`
- `0x10640`
- `0x11bb0`

## callees

- `0x11750`

## pseudocode

```c

```

## disassembly

```asm
0x11750  ldarg.1
0x11751  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x11756  brfalse.s loc_1176B
0x11758  ldarg.0
0x11759  ldarg.1
0x1175a  stfld    string Microsoft.Crm.Controls.CommandBarControl::_title
0x1175f  ldarg.0
0x11760  ldsfld   string [mscorlib]System.String::Empty
0x11765  stfld    string Microsoft.Crm.Controls.CommandBarControl::_accessKey
0x1176a  ret
0x1176b  ldarg.1
0x1176c  ldc.i4.s 0x26
0x1176e  callvirt instance int32 [mscorlib]System.String::IndexOf(char)
0x11773  stloc.0
0x11774  ldloc.0
0x11775  ldc.i4.0
0x11776  blt.s    loc_117E6
0x11778  ldloc.0
0x11779  ldarg.1
0x1177a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1177f  ldc.i4.1
0x11780  sub
0x11781  bge.s    loc_117E6
0x11783  ldloc.0
0x11784  ldarg.1
0x11785  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1178a  ldc.i4.1
0x1178b  sub
0x1178c  bge.s    loc_117C2
0x1178e  ldarg.0
0x1178f  ldarg.1
0x11790  ldc.i4.0
0x11791  ldloc.0
0x11792  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x11797  ldarg.1
0x11798  ldloc.0
0x11799  ldc.i4.1
0x1179a  add
0x1179b  callvirt instance string [mscorlib]System.String::Substring(int32)
0x117a0  call     string [mscorlib]System.String::Concat(string, string)
0x117a5  stfld    string Microsoft.Crm.Controls.CommandBarControl::_title
0x117aa  ldarg.0
0x117ab  ldarg.1
0x117ac  ldloc.0
0x117ad  ldc.i4.1
0x117ae  add
0x117af  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x117b4  stloc.1
0x117b5  ldloca.s 1
0x117b7  call     instance string [mscorlib]System.Char::ToString()
0x117bc  stfld    string Microsoft.Crm.Controls.CommandBarControl::_accessKey
0x117c1  ret
0x117c2  ldc.i4.0
0x117c3  ldstr    aCannotBeTheLas// "& cannot be the last character of the t"...
0x117c8  ldarg.1
0x117c9  call     string [mscorlib]System.String::Concat(string, string)
0x117ce  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x117d3  ldarg.0
0x117d4  ldarg.1
0x117d5  stfld    string Microsoft.Crm.Controls.CommandBarControl::_title
0x117da  ldarg.0
0x117db  ldsfld   string [mscorlib]System.String::Empty
0x117e0  stfld    string Microsoft.Crm.Controls.CommandBarControl::_accessKey
0x117e5  ret
0x117e6  ldarg.0
0x117e7  ldarg.1
0x117e8  stfld    string Microsoft.Crm.Controls.CommandBarControl::_title
0x117ed  ldarg.0
0x117ee  ldsfld   string [mscorlib]System.String::Empty
0x117f3  stfld    string Microsoft.Crm.Controls.CommandBarControl::_accessKey
0x117f8  ret
```
