# Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationResourceHelper

- ea: `0x9b10`
- end: `0x9b3c`
- name: `Microsoft.Crm.Tools.Admin.OrganizationOperation::get_OrganizationResourceHelper`
- size: `44`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x71e0`

## callees

- `0x99c0`
- `0x9b10`

## string_xrefs

- `0x9b1e`: `OrganizationSettings\OrganizationSettings.xml`

## pseudocode

```c

```

## disassembly

```asm
0x9b10  ldarg.0
0x9b11  ldfld    class [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.OrganizationResourceHelper Microsoft.Crm.Tools.Admin.OrganizationOperation::_OrganizationResourceHelper
0x9b16  brtrue.s loc_9B35
0x9b18  ldarg.0
0x9b19  call     instance string Microsoft.Crm.Tools.Admin.OrganizationOperation::get_SqlDirectory()
0x9b1e  ldstr    aOrganizationse// "OrganizationSettings\\OrganizationSetti"...
0x9b23  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x9b28  stloc.0
0x9b29  ldarg.0
0x9b2a  ldloc.0
0x9b2b  newobj   instance void [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.OrganizationResourceHelper::.ctor(string)
0x9b30  stfld    class [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.OrganizationResourceHelper Microsoft.Crm.Tools.Admin.OrganizationOperation::_OrganizationResourceHelper
0x9b35  ldarg.0
0x9b36  ldfld    class [Microsoft.Crm.Setup.Server.Utility]Microsoft.Crm.Setup.Server.Utility.OrganizationResourceHelper Microsoft.Crm.Tools.Admin.OrganizationOperation::_OrganizationResourceHelper
0x9b3b  ret
```
