# Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddProviderIdentifiers

- ea: `0xaa50`
- end: `0xaaa0`
- name: `Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddProviderIdentifiers`
- size: `80`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0xa9b0`

## callees

- `0xaa50`
- `0xab40`

## pseudocode

```c

```

## disassembly

```asm
0xaa50  ldarg.1
0xaa51  ldstr    aExternalrelyin// "ExternalRelyingPartyPassiveIdentifier"
0xaa56  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xaa5b  isinst   [mscorlib]System.String
0xaa60  stloc.0
0xaa61  ldloc.0
0xaa62  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xaa67  brfalse.s loc_AA6A
0xaa69  ret
0xaa6a  ldloc.0
0xaa6b  ldc.i4.1
0xaa6c  newarr   [mscorlib]System.Char
0xaa71  dup
0xaa72  ldc.i4.0
0xaa73  ldc.i4.s 0x7C
0xaa75  stelem.i2
0xaa76  ldc.i4.1
0xaa77  callvirt instance string[] [mscorlib]System.String::Split(char[], valuetype [mscorlib]System.StringSplitOptions)
0xaa7c  stloc.1
0xaa7d  ldc.i4.0
0xaa7e  stloc.2
0xaa7f  br.s     loc_AA99
0xaa81  ldloc.1
0xaa82  ldloc.2
0xaa83  ldelem.ref
0xaa84  ldc.i4.0
0xaa85  ldloca.s 3
0xaa87  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0xaa8c  brfalse.s loc_AA95
0xaa8e  ldarg.0
0xaa8f  ldloc.3
0xaa90  call     void Microsoft.Crm.Authentication.Claims.CrmTokenAudienceProvider::AddAudienceUri(class [mscorlib]System.Collections.ObjectModel.Collection`1<class [System]System.Uri> audiences, class [System]System.Uri uri)
0xaa95  ldloc.2
0xaa96  ldc.i4.1
0xaa97  add
0xaa98  stloc.2
0xaa99  ldloc.2
0xaa9a  ldloc.1
0xaa9b  ldlen
0xaa9c  conv.i4
0xaa9d  blt.s    loc_AA81
0xaa9f  ret
```
