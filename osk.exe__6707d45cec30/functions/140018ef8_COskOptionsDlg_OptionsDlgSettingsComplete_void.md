# COskOptionsDlg::OptionsDlgSettingsComplete(void)

- ea: `0x140018ef8`
- end: `0x140019027`
- name: `?OptionsDlgSettingsComplete@COskOptionsDlg@@AEAA_NXZ`
- size: `303`
- prototype: `bool __fastcall(COskOptionsDlg *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140018b38`

## callees

- `0x140018ef8`
- `0x140025d70`

## import_xrefs

- `USER32!LoadStringW` at `0x140018faf`
- `USER32!LoadStringW` at `0x140018fcc`
- `USER32!LoadStringW` at `0x140018faf`
- `USER32!LoadStringW` at `0x140018fcc`
- `USER32!MessageBoxW` at `0x140018fe5`
- `USER32!MessageBoxW` at `0x140018fe5`
- `USER32!SendDlgItemMessageW` at `0x140018f39`
- `USER32!SendDlgItemMessageW` at `0x140018f62`
- `USER32!SendDlgItemMessageW` at `0x140018f8b`
- `USER32!SendDlgItemMessageW` at `0x140018f39`
- `USER32!SendDlgItemMessageW` at `0x140018f62`
- `USER32!SendDlgItemMessageW` at `0x140018f8b`
- `USER32!SetFocus` at `0x140018ffc`
- `USER32!SetFocus` at `0x140018ffc`
- `USER32!GetDlgItem` at `0x140018ff3`
- `USER32!GetDlgItem` at `0x140018ff3`

## pseudocode

```c
char __fastcall COskOptionsDlg::OptionsDlgSettingsComplete(HWND *this)
{
  char v2; // bl
  HWND DlgItem; // rax
  WCHAR Buffer[256]; // [rsp+30h] [rbp-418h] BYREF
  WCHAR Text[256]; // [rsp+230h] [rbp-218h] BYREF

  v2 = 1;
  if ( SendDlgItemMessageW(*this, 5023, 0xF0u, 0, 0) != 1
    && SendDlgItemMessageW(*this, 5030, 0xF0u, 0, 0) != 1
    && SendDlgItemMessageW(*this, 5024, 0xF0u, 0, 0) != 1 )
  {
    LoadStringW(g_hInstance, 0x3E8u, Buffer, 256);
    LoadStringW(g_hInstance, 0x3F4u, Text, 256);
    MessageBoxW(*this, Text, Buffer, 0);
    DlgItem = GetDlgItem(*this, 5023);
    SetFocus(DlgItem);
    return 0;
  }
  return v2;
}

```

## disassembly

```asm
0x140018ef8  mov     [rsp+arg_8], rbx
0x140018efd  push    rdi
0x140018efe  sub     rsp, 440h
0x140018f05  mov     rax, cs:__security_cookie
0x140018f0c  xor     rax, rsp
0x140018f0f  mov     [rsp+448h+var_18], rax
0x140018f17  mov     rdi, rcx
0x140018f1a  mov     [rsp+448h+lParam], 0; lParam
0x140018f23  mov     rcx, [rcx]; hDlg
0x140018f26  xor     r9d, r9d; wParam
0x140018f29  mov     edx, 139Fh; nIDDlgItem
0x140018f2e  mov     r8d, 0F0h; Msg
0x140018f34  mov     ebx, 1
0x140018f39  call    cs:__imp_SendDlgItemMessageW
0x140018f3f  cmp     rax, rbx
0x140018f42  jz      loc_140019004
0x140018f48  mov     rcx, [rdi]; hDlg
0x140018f4b  xor     r9d, r9d; wParam
0x140018f4e  mov     edx, 13A6h; nIDDlgItem
0x140018f53  mov     [rsp+448h+lParam], 0; lParam
0x140018f5c  mov     r8d, 0F0h; Msg
0x140018f62  call    cs:__imp_SendDlgItemMessageW
0x140018f68  cmp     rax, rbx
0x140018f6b  jz      loc_140019004
0x140018f71  mov     rcx, [rdi]; hDlg
0x140018f74  xor     r9d, r9d; wParam
0x140018f77  mov     edx, 13A0h; nIDDlgItem
0x140018f7c  mov     [rsp+448h+lParam], 0; lParam
0x140018f85  mov     r8d, 0F0h; Msg
0x140018f8b  call    cs:__imp_SendDlgItemMessageW
0x140018f91  cmp     rax, rbx
0x140018f94  jz      short loc_140019004
0x140018f96  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x140018f9d  lea     r8, [rsp+448h+Buffer]; lpBuffer
0x140018fa2  mov     ebx, 100h
0x140018fa7  mov     edx, 3E8h; uID
0x140018fac  mov     r9d, ebx; cchBufferMax
0x140018faf  call    cs:__imp_LoadStringW
0x140018fb5  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; hInstance
0x140018fbc  lea     r8, [rsp+448h+Text]; lpBuffer
0x140018fc4  mov     r9d, ebx; cchBufferMax
0x140018fc7  mov     edx, 3F4h; uID
0x140018fcc  call    cs:__imp_LoadStringW
0x140018fd2  mov     rcx, [rdi]; hWnd
0x140018fd5  lea     r8, [rsp+448h+Buffer]; lpCaption
0x140018fda  xor     r9d, r9d; uType
0x140018fdd  lea     rdx, [rsp+448h+Text]; lpText
0x140018fe5  call    cs:__imp_MessageBoxW
0x140018feb  mov     rcx, [rdi]; hDlg
0x140018fee  mov     edx, 139Fh; nIDDlgItem
0x140018ff3  call    cs:__imp_GetDlgItem
0x140018ff9  mov     rcx, rax; hWnd
0x140018ffc  call    cs:__imp_SetFocus
0x140019002  xor     bl, bl
0x140019004  mov     al, bl
0x140019006  mov     rcx, [rsp+448h+var_18]
0x14001900e  xor     rcx, rsp; StackCookie
0x140019011  call    __security_check_cookie
0x140019016  mov     rbx, [rsp+448h+arg_8]
0x14001901e  add     rsp, 440h
0x140019025  pop     rdi
0x140019026  retn
```
