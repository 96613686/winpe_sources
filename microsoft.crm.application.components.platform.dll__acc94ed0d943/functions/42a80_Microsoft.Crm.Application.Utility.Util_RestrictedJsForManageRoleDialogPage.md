# Microsoft.Crm.Application.Utility.Util::RestrictedJsForManageRoleDialogPage

- ea: `0x42a80`
- end: `0x42ac9`
- name: `Microsoft.Crm.Application.Utility.Util::RestrictedJsForManageRoleDialogPage`
- size: `73`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x42a50`
- `0x42a80`

## string_xrefs

- `0x42a8f`: `/_static/_common/scripts/stage.js`
- `0x42aa5`: `/_static/_common/scripts/details.js`
- `0x42ab0`: `/_common/entityproperties/entitypropertiesutil.js.aspx`
- `0x42abb`: `/_common/entitiescustomizedhelp/entitiescustomizedhelp.js.aspx`

## pseudocode

```c

```

## disassembly

```asm
0x42a80  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x42a85  stloc.0
0x42a86  ldarg.0
0x42a87  call     bool Microsoft.Crm.Application.Utility.Util::IsManageRolePage(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context)
0x42a8c  brfalse.s loc_42AC7
0x42a8e  ldloc.0
0x42a8f  ldstr    aStaticCommonSc_4// "/_static/_common/scripts/stage.js"
0x42a94  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x42a99  ldloc.0
0x42a9a  ldstr    aStaticFormsAdd// "/_static/_forms/addrelated.js"
0x42a9f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x42aa4  ldloc.0
0x42aa5  ldstr    aStaticCommonSc_5// "/_static/_common/scripts/details.js"
0x42aaa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x42aaf  ldloc.0
0x42ab0  ldstr    aCommonEntitypr// "/_common/entityproperties/entitypropert"...
0x42ab5  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x42aba  ldloc.0
0x42abb  ldstr    aCommonEntities// "/_common/entitiescustomizedhelp/entitie"...
0x42ac0  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x42ac5  ldloc.0
0x42ac6  ret
0x42ac7  ldloc.0
0x42ac8  ret
```
