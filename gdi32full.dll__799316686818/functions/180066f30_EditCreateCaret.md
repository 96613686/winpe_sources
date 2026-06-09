# EditCreateCaret

- ea: `0x180066f30`
- end: `0x180067034`
- name: `EditCreateCaret`
- size: `260`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x180013954`
- `0x18001de14`
- `0x180066f30`

## import_xrefs

- `USER32!GetKeyboardLayout` at `0x180066fbc`
- `USER32!GetKeyboardLayout` at `0x180066fbc`
- `USER32!CreateCaret` at `0x180066fa0`
- `USER32!CreateCaret` at `0x180066fa0`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180066fc4`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x180066fc4`

## pseudocode

```c
BOOL __fastcall EditCreateCaret(__int64 a1, HDC a2, int a3, int a4, int a5)
{
  unsigned __int16 KeyboardLayout; // ax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  unsigned __int16 v15; // bx
  int CacheUpdateCount; // eax

  KeyboardLayout = a5;
  *(_DWORD *)(a1 + 304) = 0;
  if ( !a5 )
    KeyboardLayout = (unsigned __int16)GetKeyboardLayout(0);
  v10 = (KeyboardLayout & 0x3FF) - 1;
  if ( !v10 )
    goto LABEL_15;
  v11 = v10 - 12;
  if ( !v11 )
    goto LABEL_15;
  v12 = v11 - 17;
  if ( !v12 )
  {
    v15 = 2;
    goto LABEL_16;
  }
  v13 = v12 - 2;
  if ( !v13 || v13 == 9 )
  {
LABEL_15:
    v15 = 1;
    goto LABEL_16;
  }
  if ( g_ulNlsUpdateCacheCount == -1 )
  {
    CacheUpdateCount = NlsGetCacheUpdateCount();
    if ( CacheUpdateCount != g_ulNlsUpdateCacheCount )
    {
      g_ulNlsUpdateCacheCount = CacheUpdateCount;
      ReadNLSScriptSettings();
    }
  }
  if ( !g_UserBidiLocale )
    return CreateCaret(*(HWND *)(a1 + 64), 0, a3, a4);
  v15 = 0;
LABEL_16:
  if ( !(unsigned int)EditCreateCaretFromFont(a1, a2, a3, a4, 0, v15)
    && !(unsigned int)EditCreateCaretFromFont(a1, a2, a3, a4, 1u, v15) )
  {
    return CreateCaret(*(HWND *)(a1 + 64), 0, a3, a4);
  }
  return 1;
}

```

## disassembly

```asm
0x180066f30  push    rbx
0x180066f32  push    rbp
0x180066f33  push    rsi
0x180066f34  push    rdi
0x180066f35  push    r12
0x180066f37  push    r14
0x180066f39  sub     rsp, 38h
0x180066f3d  mov     eax, [rsp+68h+arg_20]
0x180066f44  mov     esi, r9d
0x180066f47  mov     dword ptr [rcx+130h], 0
0x180066f51  mov     ebp, r8d
0x180066f54  mov     r14, rdx
0x180066f57  mov     rdi, rcx
0x180066f5a  test    eax, eax
0x180066f5c  jz      short loc_180066FBA
0x180066f5e  and     eax, 3FFh
0x180066f63  mov     r12d, 1
0x180066f69  sub     eax, r12d
0x180066f6c  jz      short loc_180066FE3
0x180066f6e  sub     eax, 0Ch
0x180066f71  jz      short loc_180066FE3
0x180066f73  sub     eax, 11h
0x180066f76  jz      short loc_180066FB3
0x180066f78  sub     eax, 2
0x180066f7b  jz      short loc_180066FE3
0x180066f7d  cmp     eax, 9
0x180066f80  jz      short loc_180066FE3
0x180066f82  cmp     cs:g_ulNlsUpdateCacheCount, 0FFFFFFFFh
0x180066f89  jz      short loc_180066FC4
0x180066f8b  cmp     cs:g_UserBidiLocale, 0
0x180066f92  jnz     short loc_180066FDF
0x180066f94  mov     rcx, [rdi+40h]; hWnd
0x180066f98  mov     r9d, esi; nHeight
0x180066f9b  mov     r8d, ebp; nWidth
0x180066f9e  xor     edx, edx; hBitmap
0x180066fa0  call    cs:__imp_CreateCaret
0x180066fa6  add     rsp, 38h
0x180066faa  pop     r14
0x180066fac  pop     r12
0x180066fae  pop     rdi
0x180066faf  pop     rsi
0x180066fb0  pop     rbp
0x180066fb1  pop     rbx
0x180066fb2  retn
0x180066fb3  mov     ebx, 2
0x180066fb8  jmp     short loc_180066FE7
0x180066fba  xor     ecx, ecx; idThread
0x180066fbc  call    cs:__imp_GetKeyboardLayout
0x180066fc2  jmp     short loc_180066F5E
0x180066fc4  call    cs:__imp_NlsGetCacheUpdateCount
0x180066fca  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x180066fd0  jz      short loc_180066F8B
0x180066fd2  mov     cs:g_ulNlsUpdateCacheCount, eax
0x180066fd8  call    ReadNLSScriptSettings
0x180066fdd  jmp     short loc_180066F8B
0x180066fdf  xor     ebx, ebx
0x180066fe1  jmp     short loc_180066FE7
0x180066fe3  movzx   ebx, r12w
0x180066fe7  mov     [rsp+68h+var_40], bx
0x180066fec  mov     r9d, esi
0x180066fef  mov     r8d, ebp
0x180066ff2  mov     [rsp+68h+var_48], 0
0x180066ffa  mov     rdx, r14
0x180066ffd  mov     rcx, rdi
0x180067000  call    EditCreateCaretFromFont
0x180067005  test    eax, eax
0x180067007  jnz     short loc_18006702C
0x180067009  mov     [rsp+68h+var_40], bx
0x18006700e  mov     r9d, esi
0x180067011  mov     r8d, ebp
0x180067014  mov     [rsp+68h+var_48], r12d
0x180067019  mov     rdx, r14
0x18006701c  mov     rcx, rdi
0x18006701f  call    EditCreateCaretFromFont
0x180067024  test    eax, eax
0x180067026  jz      loc_180066F94
0x18006702c  mov     eax, r12d
0x18006702f  jmp     loc_180066FA6
```
