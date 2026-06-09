# CSchedulePage::_OnHelp(void *,uint)

- ea: `0x180015540`
- end: `0x180015565`
- name: `?_OnHelp@CSchedulePage@@EEAA_JPEAXI@Z`
- size: `37`
- prototype: `__int64(CSchedulePage *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `USER32!WinHelpW` at `0x180015555`
- `USER32!WinHelpW` at `0x180015555`

## string_xrefs

- `0x18001554e`: `%windir%\help\mstask.hlp`

## pseudocode

```c
__int64 __fastcall CSchedulePage::_OnHelp(CSchedulePage *this, HWND a2, UINT a3)
{
  WinHelpW(a2, szMstaskHelp, a3, (ULONG_PTR)&s_aSchedulePageHelpIds);
  return 1;
}

```

## disassembly

```asm
0x180015540  sub     rsp, 28h
0x180015544  mov     rcx, rdx; hWndMain
0x180015547  lea     r9, ?s_aSchedulePageHelpIds@@3PAKA; dwData
0x18001554e  lea     rdx, szMstaskHelp; "%windir%\\help\\mstask.hlp"
0x180015555  call    cs:__imp_WinHelpW
0x18001555b  mov     eax, 1
0x180015560  add     rsp, 28h
0x180015564  retn
```
