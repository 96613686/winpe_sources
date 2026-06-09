# CSettingsPage::_OnHelp(void *,uint)

- ea: `0x180017650`
- end: `0x180017675`
- name: `?_OnHelp@CSettingsPage@@EEAA_JPEAXI@Z`
- size: `37`
- prototype: `__int64(CSettingsPage *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, service_task`

## import_xrefs

- `USER32!WinHelpW` at `0x180017665`
- `USER32!WinHelpW` at `0x180017665`

## string_xrefs

- `0x18001765e`: `%windir%\help\mstask.hlp`

## pseudocode

```c
__int64 __fastcall CSettingsPage::_OnHelp(CSettingsPage *this, HWND a2, UINT a3)
{
  WinHelpW(a2, szMstaskHelp, a3, (ULONG_PTR)&s_aSettingsPageHelpIds);
  return 1;
}

```

## disassembly

```asm
0x180017650  sub     rsp, 28h
0x180017654  mov     rcx, rdx; hWndMain
0x180017657  lea     r9, ?s_aSettingsPageHelpIds@@3PAKA; dwData
0x18001765e  lea     rdx, szMstaskHelp; "%windir%\\help\\mstask.hlp"
0x180017665  call    cs:__imp_WinHelpW
0x18001766b  mov     eax, 1
0x180017670  add     rsp, 28h
0x180017674  retn
```
