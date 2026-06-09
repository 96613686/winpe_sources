# CGeneralPage::_OnHelp(void *,uint)

- ea: `0x180011f90`
- end: `0x180011fb5`
- name: `?_OnHelp@CGeneralPage@@EEAA_JPEAXI@Z`
- size: `37`
- prototype: `__int64(CGeneralPage *__hidden this, void *, unsigned int)`
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## import_xrefs

- `USER32!WinHelpW` at `0x180011fa5`
- `USER32!WinHelpW` at `0x180011fa5`

## string_xrefs

- `0x180011f9e`: `%windir%\help\mstask.hlp`

## pseudocode

```c
__int64 __fastcall CGeneralPage::_OnHelp(CGeneralPage *this, HWND a2, UINT a3)
{
  WinHelpW(a2, szMstaskHelp, a3, (ULONG_PTR)&s_aGeneralPageHelpIds);
  return 1;
}

```

## disassembly

```asm
0x180011f90  sub     rsp, 28h
0x180011f94  mov     rcx, rdx; hWndMain
0x180011f97  lea     r9, ?s_aGeneralPageHelpIds@@3PAKA; dwData
0x180011f9e  lea     rdx, szMstaskHelp; "%windir%\\help\\mstask.hlp"
0x180011fa5  call    cs:__imp_WinHelpW
0x180011fab  mov     eax, 1
0x180011fb0  add     rsp, 28h
0x180011fb4  retn
```
