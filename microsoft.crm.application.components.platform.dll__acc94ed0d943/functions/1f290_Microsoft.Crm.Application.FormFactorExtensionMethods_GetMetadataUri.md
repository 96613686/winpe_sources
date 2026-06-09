# Microsoft.Crm.Application.FormFactorExtensionMethods::GetMetadataUri

- ea: `0x1f290`
- end: `0x1f2cd`
- name: `Microsoft.Crm.Application.FormFactorExtensionMethods::GetMetadataUri`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1f290`
- `0x39f50`

## string_xrefs

- `0x1f2a4`: `/_forms/read/data.aspx`
- `0x1f2b0`: `unknown FormFactor encountered in FormFactor.GetMetadataUri : `

## pseudocode

```c

```

## disassembly

```asm
0x1f290  ldarg.0
0x1f291  ldc.i4.3
0x1f292  beq.s    loc_1F2A4
0x1f294  ldarg.0
0x1f295  ldc.i4.4
0x1f296  bne.un.s loc_1F2B0
0x1f298  ldstr    aFormsMobileref// "/_forms/mobilerefresh/data.aspx"
0x1f29d  ldarg.1
0x1f29e  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1f2a3  ret
0x1f2a4  ldstr    aFormsReadDataA// "/_forms/read/data.aspx"
0x1f2a9  ldarg.1
0x1f2aa  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1f2af  ret
0x1f2b0  ldstr    aUnknownFormfac// "unknown FormFactor encountered in FormF"...
0x1f2b5  ldarga.s 0
0x1f2b7  constrained. Microsoft.Crm.Application.FormFactor
0x1f2bd  callvirt instance string [mscorlib]System.Object::ToString()
0x1f2c2  call     string [mscorlib]System.String::Concat(string, string)
0x1f2c7  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1f2cc  throw
```
