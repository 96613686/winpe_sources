# CStatusBar::SetStatusMessage(uint,ushort const *)

- ea: `0x180023340`
- end: `0x180023400`
- name: `?SetStatusMessage@CStatusBar@@QEAAXIPEBG@Z`
- size: `192`
- prototype: `void(CStatusBar *__hidden this, unsigned int, const unsigned __int16 *)`
- caller_count: `10`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x18000d920`
- `0x18000f694`
- `0x180011920`
- `0x180013108`
- `0x180013354`
- `0x1800159c4`
- `0x180017e40`
- `0x1800201c4`
- `0x180020a4c`
- `0x180026300`

## callees

- `0x180002240`
- `0x1800096c4`
- `0x180023340`
- `0x180023710`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002338d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18002338d`
- `USER32!UpdateWindow` at `0x1800233df`
- `USER32!UpdateWindow` at `0x1800233df`
- `USER32!SendMessageW` at `0x1800233be`
- `USER32!SendMessageW` at `0x1800233d5`
- `USER32!SendMessageW` at `0x1800233be`
- `USER32!SendMessageW` at `0x1800233d5`

## pseudocode

```c
void __fastcall CStatusBar::SetStatusMessage(HWND *this, UINT a2, const unsigned __int16 *a3)
{
  WCHAR Buffer[256]; // [rsp+20h] [rbp-A28h] BYREF
  unsigned __int16 v7[1024]; // [rsp+220h] [rbp-828h] BYREF

  if ( this )
  {
    if ( this[1] )
    {
      CStatusBar::_InitStatusBar((CStatusBar *)this);
      LoadStringW(g_hinst, a2, Buffer, 256);
      StringCchPrintfW(v7, 0x400u, Buffer, a3);
      SendMessageW(this[1], 0x40Bu, 0, (LPARAM)Buffer);
      SendMessageW(this[1], 0x411u, 0, (LPARAM)Buffer);
      UpdateWindow(this[1]);
    }
  }
}

```

## disassembly

```asm
0x180023340  test    rcx, rcx
0x180023343  jz      locret_1800233FF
0x180023349  push    rbx
0x18002334a  push    rsi
0x18002334b  push    rdi
0x18002334c  sub     rsp, 0A30h
0x180023353  mov     rax, cs:__security_cookie
0x18002335a  xor     rax, rsp
0x18002335d  mov     [rsp+0A48h+var_28], rax
0x180023365  cmp     qword ptr [rcx+8], 0
0x18002336a  mov     rsi, r8
0x18002336d  mov     edi, edx
0x18002336f  mov     rbx, rcx
0x180023372  jz      short loc_1800233E5
0x180023374  call    ?_InitStatusBar@CStatusBar@@IEAAJXZ; CStatusBar::_InitStatusBar(void)
0x180023379  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x180023380  lea     r8, [rsp+0A48h+Buffer]; lpBuffer
0x180023385  mov     r9d, 100h; cchBufferMax
0x18002338b  mov     edx, edi; uID
0x18002338d  call    cs:__imp_LoadStringW
0x180023393  mov     r9, rsi
0x180023396  lea     r8, [rsp+0A48h+Buffer]; unsigned __int16 *
0x18002339b  mov     edx, 400h; unsigned __int64
0x1800233a0  lea     rcx, [rsp+0A48h+var_828]; unsigned __int16 *
0x1800233a8  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800233ad  mov     rcx, [rbx+8]; hWnd
0x1800233b1  lea     r9, [rsp+0A48h+Buffer]; lParam
0x1800233b6  xor     r8d, r8d; wParam
0x1800233b9  mov     edx, 40Bh; Msg
0x1800233be  call    cs:__imp_SendMessageW
0x1800233c4  mov     rcx, [rbx+8]; hWnd
0x1800233c8  lea     r9, [rsp+0A48h+Buffer]; lParam
0x1800233cd  xor     r8d, r8d; wParam
0x1800233d0  mov     edx, 411h; Msg
0x1800233d5  call    cs:__imp_SendMessageW
0x1800233db  mov     rcx, [rbx+8]; hWnd
0x1800233df  call    cs:__imp_UpdateWindow
0x1800233e5  mov     rcx, [rsp+0A48h+var_28]
0x1800233ed  xor     rcx, rsp; StackCookie
0x1800233f0  call    __security_check_cookie
0x1800233f5  add     rsp, 0A30h
0x1800233fc  pop     rdi
0x1800233fd  pop     rsi
0x1800233fe  pop     rbx
0x1800233ff  retn
```
