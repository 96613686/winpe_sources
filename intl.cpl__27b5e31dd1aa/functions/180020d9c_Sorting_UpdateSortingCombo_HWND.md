# Sorting_UpdateSortingCombo(HWND__ *)

- ea: `0x180020d9c`
- end: `0x180020f39`
- name: `?Sorting_UpdateSortingCombo@@YAXPEAUHWND__@@@Z`
- size: `413`
- prototype: `void __fastcall(HWND)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180020cc0`

## callees

- `0x180020d9c`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180020e1e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180020ea4`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180020e1e`
- `api-ms-win-core-localization-l1-2-0!GetLocaleInfoW` at `0x180020ea4`
- `USER32!GetDlgItem` at `0x180020dc3`
- `USER32!GetDlgItem` at `0x180020dc3`
- `USER32!SendMessageW` at `0x180020dda`
- `USER32!SendMessageW` at `0x180020e38`
- `USER32!SendMessageW` at `0x180020e50`
- `USER32!SendMessageW` at `0x180020e64`
- `USER32!SendMessageW` at `0x180020ebe`
- `USER32!SendMessageW` at `0x180020ed5`
- `USER32!SendMessageW` at `0x180020eff`
- `USER32!SendMessageW` at `0x180020dda`
- `USER32!SendMessageW` at `0x180020e38`
- `USER32!SendMessageW` at `0x180020e50`
- `USER32!SendMessageW` at `0x180020e64`
- `USER32!SendMessageW` at `0x180020ebe`
- `USER32!SendMessageW` at `0x180020ed5`
- `USER32!SendMessageW` at `0x180020eff`

## pseudocode

```c
void __fastcall Sorting_UpdateSortingCombo(HWND a1)
{
  HWND DlgItem; // rbp
  unsigned __int16 v2; // di
  WPARAM v3; // rbx
  __int64 i; // rbx
  LPARAM v5; // rsi
  WPARAM v6; // r14
  WCHAR LCData[128]; // [rsp+20h] [rbp-148h] BYREF

  DlgItem = GetDlgItem(a1, 1120);
  SendMessageW(DlgItem, 0x14Bu, 0, 0);
  v2 = *(_WORD *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 16LL);
  if ( v2 == 1034 )
    v2 = 3082;
  if ( GetLocaleInfoW(v2, 0x1013u, LCData, 128) )
  {
    v3 = (int)SendMessageW(DlgItem, 0x143u, 0, (LPARAM)LCData);
    SendMessageW(DlgItem, 0x151u, v3, v2);
    SendMessageW(DlgItem, 0x14Eu, v3, 0);
  }
  for ( i = 0; (unsigned int)i < g_NumAltSorts; i = (unsigned int)(i + 1) )
  {
    v5 = g_AltSorts[i];
    if ( (_DWORD)v5 == 1034 && v2 == 3082 || (_WORD)v5 == v2 )
    {
      if ( GetLocaleInfoW(v5, 0x1013u, LCData, 128) )
      {
        v6 = (int)SendMessageW(DlgItem, 0x143u, 0, (LPARAM)LCData);
        SendMessageW(DlgItem, 0x151u, v6, v5);
        if ( (_DWORD)v5 == *(_DWORD *)(*((_QWORD *)g_localeInfo + UserLocaleIndex) + 16LL) )
          SendMessageW(DlgItem, 0x14Eu, v6, 0);
      }
    }
  }
}

```

## disassembly

```asm
0x180020d9c  push    rbx
0x180020d9e  push    rbp
0x180020d9f  push    rsi
0x180020da0  push    rdi
0x180020da1  push    r14
0x180020da3  push    r15
0x180020da5  sub     rsp, 138h
0x180020dac  mov     rax, cs:__security_cookie
0x180020db3  xor     rax, rsp
0x180020db6  mov     [rsp+168h+var_48], rax
0x180020dbe  mov     edx, 460h; nIDDlgItem
0x180020dc3  call    cs:__imp_GetDlgItem
0x180020dc9  xor     r9d, r9d; lParam
0x180020dcc  xor     r8d, r8d; wParam
0x180020dcf  mov     rcx, rax; hWnd
0x180020dd2  mov     edx, 14Bh; Msg
0x180020dd7  mov     rbp, rax
0x180020dda  call    cs:__imp_SendMessageW
0x180020de0  mov     edx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180020de6  mov     r14d, 40Ah
0x180020dec  mov     rcx, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180020df3  mov     r15d, 0C0Ah
0x180020df9  mov     rdx, [rcx+rdx*8]
0x180020dfd  movzx   edi, word ptr [rdx+10h]
0x180020e01  cmp     di, r14w
0x180020e05  jnz     short loc_180020E0B
0x180020e07  movzx   edi, r15w
0x180020e0b  movzx   ecx, di; Locale
0x180020e0e  lea     r8, [rsp+168h+LCData]; lpLCData
0x180020e13  mov     r9d, 80h; cchData
0x180020e19  mov     edx, 1013h; LCType
0x180020e1e  call    cs:__imp_GetLocaleInfoW
0x180020e24  test    eax, eax
0x180020e26  jz      short loc_180020E6A
0x180020e28  lea     r9, [rsp+168h+LCData]; lParam
0x180020e2d  xor     r8d, r8d; wParam
0x180020e30  mov     edx, 143h; Msg
0x180020e35  mov     rcx, rbp; hWnd
0x180020e38  call    cs:__imp_SendMessageW
0x180020e3e  movzx   r9d, di; lParam
0x180020e42  mov     edx, 151h; Msg
0x180020e47  movsxd  rbx, eax
0x180020e4a  mov     rcx, rbp; hWnd
0x180020e4d  mov     r8, rbx; wParam
0x180020e50  call    cs:__imp_SendMessageW
0x180020e56  xor     r9d, r9d; lParam
0x180020e59  mov     r8, rbx; wParam
0x180020e5c  mov     edx, 14Eh; Msg
0x180020e61  mov     rcx, rbp; hWnd
0x180020e64  call    cs:__imp_SendMessageW
0x180020e6a  xor     ebx, ebx
0x180020e6c  cmp     cs:?g_NumAltSorts@@3KA, ebx; ulong g_NumAltSorts
0x180020e72  jbe     loc_180020F19
0x180020e78  lea     rsi, ?g_AltSorts@@3PAKA; ulong near * g_AltSorts
0x180020e7f  mov     esi, [rsi+rbx*4]
0x180020e82  cmp     esi, r14d
0x180020e85  jnz     short loc_180020E8D
0x180020e87  cmp     di, r15w
0x180020e8b  jz      short loc_180020E92
0x180020e8d  cmp     si, di
0x180020e90  jnz     short loc_180020F0B
0x180020e92  mov     r9d, 80h; cchData
0x180020e98  lea     r8, [rsp+168h+LCData]; lpLCData
0x180020e9d  mov     edx, 1013h; LCType
0x180020ea2  mov     ecx, esi; Locale
0x180020ea4  call    cs:__imp_GetLocaleInfoW
0x180020eaa  test    eax, eax
0x180020eac  jz      short loc_180020F0B
0x180020eae  lea     r9, [rsp+168h+LCData]; lParam
0x180020eb3  xor     r8d, r8d; wParam
0x180020eb6  mov     edx, 143h; Msg
0x180020ebb  mov     rcx, rbp; hWnd
0x180020ebe  call    cs:__imp_SendMessageW
0x180020ec4  movsxd  r14, eax
0x180020ec7  mov     r9, rsi; lParam
0x180020eca  mov     r8, r14; wParam
0x180020ecd  mov     edx, 151h; Msg
0x180020ed2  mov     rcx, rbp; hWnd
0x180020ed5  call    cs:__imp_SendMessageW
0x180020edb  mov     ecx, cs:?UserLocaleIndex@@3KA; ulong UserLocaleIndex
0x180020ee1  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180020ee8  mov     rcx, [rax+rcx*8]
0x180020eec  cmp     esi, [rcx+10h]
0x180020eef  jnz     short loc_180020F05
0x180020ef1  xor     r9d, r9d; lParam
0x180020ef4  mov     r8, r14; wParam
0x180020ef7  mov     edx, 14Eh; Msg
0x180020efc  mov     rcx, rbp; hWnd
0x180020eff  call    cs:__imp_SendMessageW
0x180020f05  mov     r14d, 40Ah
0x180020f0b  inc     ebx
0x180020f0d  cmp     ebx, cs:?g_NumAltSorts@@3KA; ulong g_NumAltSorts
0x180020f13  jb      loc_180020E78
0x180020f19  mov     rcx, [rsp+168h+var_48]
0x180020f21  xor     rcx, rsp; StackCookie
0x180020f24  call    __security_check_cookie
0x180020f29  add     rsp, 138h
0x180020f30  pop     r15
0x180020f32  pop     r14
0x180020f34  pop     rdi
0x180020f35  pop     rsi
0x180020f36  pop     rbp
0x180020f37  pop     rbx
0x180020f38  retn
```
