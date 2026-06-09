# Microsoft.Crm.Application.FormFactorExtensionMethods::GetEntityDataUri

- ea: `0x1f310`
- end: `0x1f34d`
- name: `Microsoft.Crm.Application.FormFactorExtensionMethods::GetEntityDataUri`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1f310`
- `0x39f50`

## string_xrefs

- `0x1f324`: `/_forms/read/entitydata.aspx`
- `0x1f330`: `unknown FormFactor encountered in FormFactor.GetEntityDataUri : `

## pseudocode

```c

```

## disassembly

```asm
0x1f310  ldarg.0
0x1f311  ldc.i4.3
0x1f312  beq.s    loc_1F324
0x1f314  ldarg.0
0x1f315  ldc.i4.4
0x1f316  bne.un.s loc_1F330
0x1f318  ldstr    aFormsMobileref_1// "/_forms/mobilerefresh/entitydata.aspx"
0x1f31d  ldarg.1
0x1f31e  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1f323  ret
0x1f324  ldstr    aFormsReadEntit// "/_forms/read/entitydata.aspx"
0x1f329  ldarg.1
0x1f32a  call     class Microsoft.Crm.Application.Utility.CrmUri Microsoft.Crm.Application.Utility.CrmUri::Create(string uri, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x1f32f  ret
0x1f330  ldstr    aUnknownFormfac_1// "unknown FormFactor encountered in FormF"...
0x1f335  ldarga.s 0
0x1f337  constrained. Microsoft.Crm.Application.FormFactor
0x1f33d  callvirt instance string [mscorlib]System.Object::ToString()
0x1f342  call     string [mscorlib]System.String::Concat(string, string)
0x1f347  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x1f34c  throw
```
