# _dynamic_atexit_destructor_for__ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL__

- ea: `0x180010b70`
- end: `0x180010b7e`
- name: `_dynamic_atexit_destructor_for__ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010b77`

## pseudocode

```c
void dynamic_atexit_destructor_for__ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL__()
{
  SysFreeString(ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL);
}

```

## disassembly

```asm
0x180010b70  mov     rcx, cs:?GROUP_POLICY_HELP_URL@CLauncherMainTaskDialog@ux@@0VCComBSTR@ATL@@B; ATL::CComBSTR const ux::CLauncherMainTaskDialog::GROUP_POLICY_HELP_URL
0x180010b77  jmp     cs:__imp_SysFreeString
```
