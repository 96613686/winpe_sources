# Microsoft.Crm.Sandbox.SandboxUtility::GetSpnIdentityString

- ea: `0x36a0`
- end: `0x3798`
- name: `Microsoft.Crm.Sandbox.SandboxUtility::GetSpnIdentityString`
- size: `248`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14a0`
- `0x14d0`
- `0x36a0`

## string_xrefs

- `0x371e`: `SandboxUtility.GetSpnIdentityString: registryKey: {0}`
- `0x375a`: `SandboxUtility.GetSpnIdentityString: REGISTRY OVERRIDE: registryKey: {0}: no SPN specified`
- `0x377e`: `SandboxUtility.GetSpnIdentityString: REGISTRY OVERRIDE: registryKey: {0}: SPN: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x36a0  ldarg.1
0x36a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x36a6  brfalse.s loc_36B6
0x36a8  ldstr    aHost// "HOST/"
0x36ad  ldarg.0
0x36ae  call     string [mscorlib]System.String::Concat(string, string)
0x36b3  stloc.0
0x36b4  br.s     loc_36C3
0x36b6  ldarg.1
0x36b7  ldstr    asc_C034// "/"
0x36bc  ldarg.0
0x36bd  call     string [mscorlib]System.String::Concat(string, string, string)
0x36c2  stloc.0
0x36c3  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x36c8  ldc.i4.s 0x21
0x36ca  ldstr    aSandboxutility_3// "SandboxUtility.GetSpnIdentityString: cl"...
0x36cf  ldc.i4.1
0x36d0  newarr   [mscorlib]System.Object
0x36d5  dup
0x36d6  ldc.i4.0
0x36d7  ldloc.0
0x36d8  stelem.ref
0x36d9  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x36de  ldc.i4.4
0x36df  newarr   [mscorlib]System.Object
0x36e4  dup
0x36e5  ldc.i4.0
0x36e6  ldc.i4.0
0x36e7  stloc.3
0x36e8  ldloca.s 3
0x36ea  constrained. Microsoft.Crm.Sandbox.SandboxPropertyPrefix
0x36f0  callvirt instance string [mscorlib]System.Object::ToString()
0x36f5  stelem.ref
0x36f6  dup
0x36f7  ldc.i4.1
0x36f8  ldc.i4.s 0xE
0x36fa  box      Microsoft.Crm.Sandbox.SandboxProperty
0x36ff  stelem.ref
0x3700  dup
0x3701  ldc.i4.2
0x3702  ldstr    asc_E186// "."
0x3707  stelem.ref
0x3708  dup
0x3709  ldc.i4.3
0x370a  ldarg.0
0x370b  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x3710  stelem.ref
0x3711  call     string [mscorlib]System.String::Concat(object[])
0x3716  stloc.1
0x3717  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x371c  ldc.i4.s 0x21
0x371e  ldstr    aSandboxutility_4// "SandboxUtility.GetSpnIdentityString: re"...
0x3723  ldc.i4.1
0x3724  newarr   [mscorlib]System.Object
0x3729  dup
0x372a  ldc.i4.0
0x372b  ldloc.1
0x372c  stelem.ref
0x372d  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceInfo(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3732  ldloc.1
0x3733  call     object [Microsoft.Crm.Core]Microsoft.Crm.RegistryCache::GetValue(string)
0x3738  stloc.2
0x3739  ldloc.2
0x373a  brfalse.s loc_3796
0x373c  ldloc.2
0x373d  isinst   [mscorlib]System.String
0x3742  brfalse.s loc_3796
0x3744  ldloc.2
0x3745  castclass [mscorlib]System.String
0x374a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x374f  brfalse.s loc_3770
0x3751  ldnull
0x3752  stloc.0
0x3753  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3758  ldc.i4.s 0x21
0x375a  ldstr    aSandboxutility_5// "SandboxUtility.GetSpnIdentityString: RE"...
0x375f  ldc.i4.1
0x3760  newarr   [mscorlib]System.Object
0x3765  dup
0x3766  ldc.i4.0
0x3767  ldloc.1
0x3768  stelem.ref
0x3769  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x376e  br.s     loc_3796
0x3770  ldloc.2
0x3771  castclass [mscorlib]System.String
0x3776  stloc.0
0x3777  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x377c  ldc.i4.s 0x21
0x377e  ldstr    aSandboxutility_6// "SandboxUtility.GetSpnIdentityString: RE"...
0x3783  ldc.i4.2
0x3784  newarr   [mscorlib]System.Object
0x3789  dup
0x378a  ldc.i4.0
0x378b  ldloc.1
0x378c  stelem.ref
0x378d  dup
0x378e  ldc.i4.1
0x378f  ldloc.0
0x3790  stelem.ref
0x3791  call     void Microsoft.Crm.Sandbox.SandboxTrace::TraceWarning(valuetype [mscorlib]System.Guid orgId, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory traceCategory, string format, object[] args)
0x3796  ldloc.0
0x3797  ret
```
