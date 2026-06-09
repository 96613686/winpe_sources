# _dynamic_atexit_destructor_for__ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC__

- ea: `0x180010b50`
- end: `0x180010b5e`
- name: `_dynamic_atexit_destructor_for__ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC__`
- size: `14`
- prototype: `void()`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x180010b57`

## pseudocode

```c
void dynamic_atexit_destructor_for__ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC__()
{
  SysFreeString(ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC);
}

```

## disassembly

```asm
0x180010b50  mov     rcx, cs:?FIRMWARE_HELP_TOPIC@CLauncherErrorTaskDialog@ux@@0VCComBSTR@ATL@@B; ATL::CComBSTR const ux::CLauncherErrorTaskDialog::FIRMWARE_HELP_TOPIC
0x180010b57  jmp     cs:__imp_SysFreeString
```
