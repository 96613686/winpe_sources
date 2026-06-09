# Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::.ctor

- ea: `0x17a90`
- end: `0x17ace`
- name: `Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::.ctor`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## string_xrefs

- `0x17aa7`: `lqRemove`

## pseudocode

```c

```

## disassembly

```asm
0x17a90  ldarg.0
0x17a91  ldsfld   string [mscorlib]System.String::Empty
0x17a96  stfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::fetchXml
0x17a9b  ldarg.0
0x17a9c  ldstr    aLqadd// "lqAdd"
0x17aa1  stfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::listQueryAddAction
0x17aa6  ldarg.0
0x17aa7  ldstr    aLqremove// "lqRemove"
0x17aac  stfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::listQueryRemoveAction
0x17ab1  ldarg.0
0x17ab2  ldstr    aLqkeep// "lqKeep"
0x17ab7  stfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::listQueryKeepAction
0x17abc  ldarg.0
0x17abd  ldstr    aLqusequery// "lqUseQuery"
0x17ac2  stfld    string Microsoft.Crm.Common.Application.Pages.MA.QueryBuildPage::listQueryUseAction
0x17ac7  ldarg.0
0x17ac8  call     instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.DialogBase::.ctor()
0x17acd  ret
```
