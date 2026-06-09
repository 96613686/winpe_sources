# Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::BuildLegacyAuthRequiredResponse

- ea: `0xf9f0`
- end: `0xfa7b`
- name: `Microsoft.Crm.Authentication.Claims.ResourceAccessErrorResponseHandler::BuildLegacyAuthRequiredResponse`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xf780`

## callees

- `0xf9f0`

## string_xrefs

- `0xfa03`: `redirect_uri`

## pseudocode

```c

```

## disassembly

```asm
0xf9f0  ldarg.0
0xf9f1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf9f6  ldstr    a01_1// "{0}={1}"
0xf9fb  ldc.i4.2
0xf9fc  newarr   [mscorlib]System.Object
0xfa01  dup
0xfa02  ldc.i4.0
0xfa03  ldstr    aRedirectUri// "redirect_uri"
0xfa08  stelem.ref
0xfa09  dup
0xfa0a  ldc.i4.1
0xfa0b  ldarg.1
0xfa0c  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0xfa11  stelem.ref
0xfa12  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xfa17  pop
0xfa18  call     class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::get_AzureActiveDirectoryFederationProvider()
0xfa1d  ldstr    aExternalrelyin// "ExternalRelyingPartyPassiveIdentifier"
0xfa22  call     object [Microsoft.Crm.Core]Microsoft.Crm.CrmAuthenticationContext::GetFederationProviderProperty(class [Microsoft.Crm.Core]Microsoft.Crm.Data.PropertyBag, string)
0xfa27  isinst   [mscorlib]System.String
0xfa2c  stloc.0
0xfa2d  ldloc.0
0xfa2e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0xfa33  brtrue.s loc_FA7A
0xfa35  ldarg.0
0xfa36  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xfa3b  ldstr    a01_2// ", {0}={1}"
0xfa40  ldc.i4.2
0xfa41  newarr   [mscorlib]System.Object
0xfa46  dup
0xfa47  ldc.i4.0
0xfa48  ldstr    aRealm// "realm"
0xfa4d  stelem.ref
0xfa4e  dup
0xfa4f  ldc.i4.1
0xfa50  ldloc.0
0xfa51  ldstr    aSpn// "spn:"
0xfa56  ldc.i4.5
0xfa57  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0xfa5c  brtrue.s loc_FA66
0xfa5e  ldloc.0
0xfa5f  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0xfa64  br.s     loc_FA73
0xfa66  ldloc.0
0xfa67  ldc.i4.0
0xfa68  ldc.i4.4
0xfa69  callvirt instance string [mscorlib]System.String::Remove(int32, int32)
0xfa6e  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::CrmUrlEncode(string)
0xfa73  stelem.ref
0xfa74  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(class [mscorlib]System.IFormatProvider, string, object[])
0xfa79  pop
0xfa7a  ret
```
