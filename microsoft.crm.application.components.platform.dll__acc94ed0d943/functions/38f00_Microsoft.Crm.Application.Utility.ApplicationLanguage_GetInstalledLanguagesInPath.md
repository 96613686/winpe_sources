# Microsoft.Crm.Application.Utility.ApplicationLanguage::GetInstalledLanguagesInPath

- ea: `0x38f00`
- end: `0x3903d`
- name: `Microsoft.Crm.Application.Utility.ApplicationLanguage::GetInstalledLanguagesInPath`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x38e90`

## callees

- `0x38f00`
- `0x47920`
- `0x47940`

## string_xrefs

- `0x38f26`: `path not specified.`
- `0x38f56`: `path not found : `

## pseudocode

```c

```

## disassembly

```asm
0x38f00  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::.ctor()
0x38f05  stloc.0
0x38f06  ldarg.0
0x38f07  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x38f0c  brfalse.s loc_38F33
0x38f0e  ldnull
0x38f0f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x38f14  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x38f19  ldstr    a0// "{0}"
0x38f1e  ldc.i4.1
0x38f1f  newarr   [mscorlib]System.Object
0x38f24  dup
0x38f25  ldc.i4.0
0x38f26  ldstr    aPathNotSpecifi// "path not specified."
0x38f2b  stelem.ref
0x38f2c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x38f31  ldloc.0
0x38f32  ret
0x38f33  ldnull
0x38f34  stloc.1
0x38f35  ldarg.0
0x38f36  call     string[] [mscorlib]System.IO.Directory::GetDirectories(string)
0x38f3b  stloc.1
0x38f3c  leave.s  loc_38F69
0x38f3e  pop
0x38f3f  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x38f44  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x38f49  ldstr    a0// "{0}"
0x38f4e  ldc.i4.1
0x38f4f  newarr   [mscorlib]System.Object
0x38f54  dup
0x38f55  ldc.i4.0
0x38f56  ldstr    aPathNotFound// "path not found : "
0x38f5b  ldarg.0
0x38f5c  call     string [mscorlib]System.String::Concat(string, string)
0x38f61  stelem.ref
0x38f62  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x38f67  leave.s  loc_38F69
0x38f69  ldloc.1
0x38f6a  brfalse  loc_3902C
0x38f6f  ldloc.1
0x38f70  stloc.2
0x38f71  ldc.i4.0
0x38f72  stloc.3
0x38f73  br       loc_39023
0x38f78  ldloc.2
0x38f79  ldloc.3
0x38f7a  ldelem.ref
0x38f7b  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x38f80  stloc.s  4
0x38f82  ldsfld   class [System]System.Text.RegularExpressions.Regex Microsoft.Crm.Application.Utility.ApplicationLanguage::ValidPathRegex
0x38f87  ldloc.s  4
0x38f89  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x38f8e  brfalse  loc_3901F
0x38f93  ldnull
0x38f94  stloc.s  5
0x38f96  ldloc.s  4
0x38f98  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x38f9d  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x38fa2  newobj   instance void [mscorlib]System.Globalization.CultureInfo::.ctor(int32)
0x38fa7  stloc.s  5
0x38fa9  ldloc.0
0x38faa  ldloc.s  5
0x38fac  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x38fb1  callvirt instance bool class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Contains(var<u1>)
0x38fb6  brtrue.s loc_38FC5
0x38fb8  ldloc.0
0x38fb9  ldloc.s  5
0x38fbb  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x38fc0  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::Add(var<u1>)
0x38fc5  leave.s  loc_3901F
0x38fc7  pop
0x38fc8  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x38fcd  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x38fd2  ldstr    a0// "{0}"
0x38fd7  ldc.i4.1
0x38fd8  newarr   [mscorlib]System.Object
0x38fdd  dup
0x38fde  ldc.i4.0
0x38fdf  ldstr    aSubdirectories// "Subdirectories are expected to be cultu"...
0x38fe4  ldloc.s  4
0x38fe6  call     string [mscorlib]System.String::Concat(string, string)
0x38feb  stelem.ref
0x38fec  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x38ff1  leave.s  loc_3901F
0x38ff3  pop
0x38ff4  call     valuetype [mscorlib]System.Guid Microsoft.Crm.Application.Utility.Util::get_TraceOrganizationId()
0x38ff9  call     valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory Microsoft.Crm.Application.Utility.Util::GetTraceCategory()
0x38ffe  ldstr    a0// "{0}"
0x39003  ldc.i4.1
0x39004  newarr   [mscorlib]System.Object
0x39009  dup
0x3900a  ldc.i4.0
0x3900b  ldstr    aSubdirectories_0// "Subdirectories are expected to be cultu"...
0x39010  ldloc.s  4
0x39012  call     string [mscorlib]System.String::Concat(string, string)
0x39017  stelem.ref
0x39018  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3901d  leave.s  loc_3901F
0x3901f  ldloc.3
0x39020  ldc.i4.1
0x39021  add
0x39022  stloc.3
0x39023  ldloc.3
0x39024  ldloc.2
0x39025  ldlen
0x39026  conv.i4
0x39027  blt      loc_38F78
0x3902c  ldloc.0
0x3902d  call     T0x2B000066
0x39032  call     T0x2B000069
0x39037  newobj   instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<int32>::.ctor(class [mscorlib]System.Collections.Generic.IList`1<var<u1>>)
0x3903c  ret
```
