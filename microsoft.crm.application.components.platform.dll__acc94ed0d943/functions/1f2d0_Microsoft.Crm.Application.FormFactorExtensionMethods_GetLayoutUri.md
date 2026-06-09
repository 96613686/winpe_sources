# Microsoft.Crm.Application.FormFactorExtensionMethods::GetLayoutUri

- ea: `0x1f2d0`
- end: `0x1f30d`
- name: `Microsoft.Crm.Application.FormFactorExtensionMethods::GetLayoutUri`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1f2d0`
- `0x39f50`

## string_xrefs

- `0x1f2e4`: `/_forms/read/layout.aspx`
- `0x1f2f0`: `unknown FormFactor encountered in FormFactor.GetLayoutUri : `

## pseudocode

```c

```

## disassembly

```asm
0x1f2d0  ldarg.0
0x1f2d1  ldc.i4.3
0x1f2d2  beq.s    loc_1F2E4
0x1f2d4  ldarg.0
0x1f2d5  ldc.i4.4
0x1f2d6  bne.un.s loc_1F2F0
0x1f2d8  ldstr    aFormsMobileref_0// "/_forms/mobilerefresh/layout.aspx"
0x1f2dd  ldarg.1
0x1f2de  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1f2e3  ret
0x1f2e4  ldstr    aFormsReadLayou// "/_forms/read/layout.aspx"
0x1f2e9  ldarg.1
0x1f2ea  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1f2ef  ret
0x1f2f0  ldstr    aUnknownFormfac_0// "unknown FormFactor encountered in FormF"...
0x1f2f5  ldarga.s 0
0x1f2f7  constrained. Microsoft.Crm.Application.FormFactor
0x1f2fd  callvirt instance string [mscorlib]System.Object::ToString()
0x1f302  call     string [mscorlib]System.String::Concat(string, string)
0x1f307  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1f30c  throw
```
