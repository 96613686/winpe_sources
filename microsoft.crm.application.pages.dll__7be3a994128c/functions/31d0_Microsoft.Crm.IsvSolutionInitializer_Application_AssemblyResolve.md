# Microsoft.Crm.IsvSolutionInitializer::Application_AssemblyResolve

- ea: `0x31d0`
- end: `0x3415`
- name: `Microsoft.Crm.IsvSolutionInitializer::Application_AssemblyResolve`
- size: `581`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x31d0`

## string_xrefs

- `0x320e`: `Attempt to find assembly skipped due missing request information.`
- `0x3245`: `Attempted to find assembly {0} skipped path not being under ISV folder.`
- `0x32ee`: `Attempted to find assembly {0} skipped due to unknown search location {1}.`
- `0x333a`: `Attempt to find assembly {0} in {1} skipped due to missing directory.`
- `0x3394`: `Attempt to find assembly {0} in {1} skipped due to no matches.`
- `0x33c0`: `Attempt to find assembly {0} in {1} skipped due to multiple matches.`

## pseudocode

```c

```

## disassembly

```asm
0x31d0  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x31d5  brtrue.s loc_31EF
0x31d7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x31dc  ldc.i4.0
0x31dd  ldstr    aIsvsolutionini// "IsvSolutionInitializer: Assembly resolv"...
0x31e2  ldc.i4.0
0x31e3  newarr   [mscorlib]System.Object
0x31e8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x31ed  ldnull
0x31ee  ret
0x31ef  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x31f4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x31f9  brfalse.s loc_3208
0x31fb  ldarg.1
0x31fc  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x3201  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3206  brfalse.s loc_3220
0x3208  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x320d  ldc.i4.0
0x320e  ldstr    aAttemptToFindA// "Attempt to find assembly skipped due mi"...
0x3213  ldc.i4.0
0x3214  newarr   [mscorlib]System.Object
0x3219  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x321e  ldnull
0x321f  ret
0x3220  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3225  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x322a  callvirt instance string [System.Web]System.Web.HttpRequest::get_PhysicalPath()
0x322f  ldstr    aIsv// "isv"
0x3234  ldc.i4.5
0x3235  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x323a  stloc.0
0x323b  ldloc.0
0x323c  ldc.i4.0
0x323d  bge.s    loc_3272
0x323f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3244  ldc.i4.0
0x3245  ldstr    aAttemptedToFin// "Attempted to find assembly {0} skipped "...
0x324a  ldc.i4.2
0x324b  newarr   [mscorlib]System.Object
0x3250  dup
0x3251  ldc.i4.0
0x3252  ldarg.1
0x3253  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x3258  stelem.ref
0x3259  dup
0x325a  ldc.i4.1
0x325b  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3260  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x3265  callvirt instance string [System.Web]System.Web.HttpRequest::get_PhysicalPath()
0x326a  stelem.ref
0x326b  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3270  ldnull
0x3271  ret
0x3272  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x3277  callvirt instance string [mscorlib]System.AppDomain::get_BaseDirectory()
0x327c  ldstr    aIsv_0// "ISV"
0x3281  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x3286  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x328b  stloc.1
0x328c  call     class [mscorlib]System.AppDomain [mscorlib]System.AppDomain::get_CurrentDomain()
0x3291  callvirt instance string [mscorlib]System.AppDomain::get_BaseDirectory()
0x3296  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x329b  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x32a0  callvirt instance string [System.Web]System.Web.HttpRequest::get_PhysicalPath()
0x32a5  ldloc.0
0x32a6  callvirt instance string [mscorlib]System.String::Substring(int32)
0x32ab  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x32b0  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x32b5  stloc.2
0x32b6  br.s     loc_32BF
0x32b8  ldloc.2
0x32b9  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x32be  stloc.2
0x32bf  ldloc.2
0x32c0  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x32c5  brfalse.s loc_32E0
0x32c7  ldloc.1
0x32c8  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x32cd  ldloc.2
0x32ce  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x32d3  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x32d8  ldc.i4.5
0x32d9  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x32de  brfalse.s loc_32B8
0x32e0  ldloc.2
0x32e1  callvirt instance class [mscorlib]System.IO.DirectoryInfo [mscorlib]System.IO.DirectoryInfo::get_Parent()
0x32e6  brtrue.s loc_331B
0x32e8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x32ed  ldc.i4.0
0x32ee  ldstr    aAttemptedToFin_0// "Attempted to find assembly {0} skipped "...
0x32f3  ldc.i4.2
0x32f4  newarr   [mscorlib]System.Object
0x32f9  dup
0x32fa  ldc.i4.0
0x32fb  ldarg.1
0x32fc  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x3301  stelem.ref
0x3302  dup
0x3303  ldc.i4.1
0x3304  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x3309  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x330e  callvirt instance string [System.Web]System.Web.HttpRequest::get_PhysicalPath()
0x3313  stelem.ref
0x3314  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3319  ldnull
0x331a  ret
0x331b  ldloc.2
0x331c  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x3321  ldstr    aBin// "bin"
0x3326  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x332b  stloc.3
0x332c  ldloc.3
0x332d  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x3332  brtrue.s loc_3359
0x3334  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3339  ldc.i4.0
0x333a  ldstr    aAttemptToFindA_0// "Attempt to find assembly {0} in {1} ski"...
0x333f  ldc.i4.2
0x3340  newarr   [mscorlib]System.Object
0x3345  dup
0x3346  ldc.i4.0
0x3347  ldarg.1
0x3348  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x334d  stelem.ref
0x334e  dup
0x334f  ldc.i4.1
0x3350  ldloc.3
0x3351  stelem.ref
0x3352  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3357  ldnull
0x3358  ret
0x3359  ldloc.3
0x335a  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x335f  ldarg.1
0x3360  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x3365  newobj   instance void [mscorlib]System.Reflection.AssemblyName::.ctor(string)
0x336a  callvirt instance string [mscorlib]System.Reflection.AssemblyName::get_Name()
0x336f  ldstr    aDll// ".dll"
0x3374  call     string [mscorlib]System.IO.Path::ChangeExtension(string, string)
0x3379  stloc.s  4
0x337b  ldloc.s  4
0x337d  ldc.i4.0
0x337e  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string, valuetype [mscorlib]System.IO.SearchOption)
0x3383  stloc.s  5
0x3385  ldloc.s  5
0x3387  brfalse.s loc_338E
0x3389  ldloc.s  5
0x338b  ldlen
0x338c  brtrue.s loc_33B3
0x338e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3393  ldc.i4.0
0x3394  ldstr    aAttemptToFindA_1// "Attempt to find assembly {0} in {1} ski"...
0x3399  ldc.i4.2
0x339a  newarr   [mscorlib]System.Object
0x339f  dup
0x33a0  ldc.i4.0
0x33a1  ldarg.1
0x33a2  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x33a7  stelem.ref
0x33a8  dup
0x33a9  ldc.i4.1
0x33aa  ldloc.3
0x33ab  stelem.ref
0x33ac  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x33b1  ldnull
0x33b2  ret
0x33b3  ldloc.s  5
0x33b5  ldlen
0x33b6  conv.i4
0x33b7  ldc.i4.1
0x33b8  ble.s    loc_33DF
0x33ba  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33bf  ldc.i4.0
0x33c0  ldstr    aAttemptToFindA_2// "Attempt to find assembly {0} in {1} ski"...
0x33c5  ldc.i4.2
0x33c6  newarr   [mscorlib]System.Object
0x33cb  dup
0x33cc  ldc.i4.0
0x33cd  ldarg.1
0x33ce  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x33d3  stelem.ref
0x33d4  dup
0x33d5  ldc.i4.1
0x33d6  ldloc.3
0x33d7  stelem.ref
0x33d8  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x33dd  ldnull
0x33de  ret
0x33df  ldloc.s  5
0x33e1  ldc.i4.0
0x33e2  ldelem.ref
0x33e3  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x33e8  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::LoadFrom(string)
0x33ed  stloc.s  6
0x33ef  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x33f4  ldc.i4.0
0x33f5  ldstr    aIsvAssembly0Lo// "ISV assembly {0} loaded from {1}."
0x33fa  ldc.i4.2
0x33fb  newarr   [mscorlib]System.Object
0x3400  dup
0x3401  ldc.i4.0
0x3402  ldarg.1
0x3403  callvirt instance string [mscorlib]System.ResolveEventArgs::get_Name()
0x3408  stelem.ref
0x3409  dup
0x340a  ldc.i4.1
0x340b  ldloc.3
0x340c  stelem.ref
0x340d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x3412  ldloc.s  6
0x3414  ret
```
