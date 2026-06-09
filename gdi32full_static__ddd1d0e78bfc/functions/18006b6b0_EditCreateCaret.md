# EditCreateCaret

- ea: `0x18006b6b0`
- end: `0x18006b7cf`
- name: `EditCreateCaret`
- size: `287`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callees

- `0x18001eb10`
- `0x180020880`
- `0x18006b6b0`

## import_xrefs

- `USER32!GetKeyboardLayout` at `0x18006b74b`
- `USER32!GetKeyboardLayout` at `0x18006b74b`
- `USER32!CreateCaret` at `0x18006b728`
- `USER32!CreateCaret` at `0x18006b728`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18006b759`
- `api-ms-win-core-localization-private-l1-1-0!NlsGetCacheUpdateCount` at `0x18006b759`

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
0x18006b6b0  push    rbx
0x18006b6b2  push    rbp
0x18006b6b3  push    rsi
0x18006b6b4  push    rdi
0x18006b6b5  push    r12
0x18006b6b7  push    r14
0x18006b6b9  sub     rsp, 38h
0x18006b6bd  mov     eax, [rsp+68h+arg_20]
0x18006b6c4  mov     esi, r9d
0x18006b6c7  mov     dword ptr [rcx+130h], 0
0x18006b6d1  mov     ebp, r8d
0x18006b6d4  mov     r14, rdx
0x18006b6d7  mov     rdi, rcx
0x18006b6da  test    eax, eax
0x18006b6dc  jz      short loc_18006B749
0x18006b6de  and     eax, 3FFh
0x18006b6e3  mov     r12d, 1
0x18006b6e9  sub     eax, r12d
0x18006b6ec  jz      loc_18006B77E
0x18006b6f2  sub     eax, 0Ch
0x18006b6f5  jz      loc_18006B77E
0x18006b6fb  sub     eax, 11h
0x18006b6fe  jz      short loc_18006B742
0x18006b700  sub     eax, 2
0x18006b703  jz      short loc_18006B77E
0x18006b705  cmp     eax, 9
0x18006b708  jz      short loc_18006B77E
0x18006b70a  cmp     cs:g_ulNlsUpdateCacheCount, 0FFFFFFFFh
0x18006b711  jz      short loc_18006B759
0x18006b713  cmp     cs:g_UserBidiLocale, 0
0x18006b71a  jnz     short loc_18006B77A
0x18006b71c  mov     rcx, [rdi+40h]; hWnd
0x18006b720  mov     r9d, esi; nHeight
0x18006b723  mov     r8d, ebp; nWidth
0x18006b726  xor     edx, edx; hBitmap
0x18006b728  call    cs:__imp_CreateCaret
0x18006b72f  nop     dword ptr [rax+rax+00h]
0x18006b734  add     rsp, 38h
0x18006b738  pop     r14
0x18006b73a  pop     r12
0x18006b73c  pop     rdi
0x18006b73d  pop     rsi
0x18006b73e  pop     rbp
0x18006b73f  pop     rbx
0x18006b740  retn
0x18006b742  mov     ebx, 2
0x18006b747  jmp     short loc_18006B782
0x18006b749  xor     ecx, ecx; idThread
0x18006b74b  call    cs:__imp_GetKeyboardLayout
0x18006b752  nop     dword ptr [rax+rax+00h]
0x18006b757  jmp     short loc_18006B6DE
0x18006b759  call    cs:__imp_NlsGetCacheUpdateCount
0x18006b760  nop     dword ptr [rax+rax+00h]
0x18006b765  cmp     eax, cs:g_ulNlsUpdateCacheCount
0x18006b76b  jz      short loc_18006B713
0x18006b76d  mov     cs:g_ulNlsUpdateCacheCount, eax
0x18006b773  call    ReadNLSScriptSettings
0x18006b778  jmp     short loc_18006B713
0x18006b77a  xor     ebx, ebx
0x18006b77c  jmp     short loc_18006B782
0x18006b77e  movzx   ebx, r12w
0x18006b782  mov     [rsp+68h+var_40], bx
0x18006b787  mov     r9d, esi
0x18006b78a  mov     r8d, ebp
0x18006b78d  mov     [rsp+68h+var_48], 0
0x18006b795  mov     rdx, r14
0x18006b798  mov     rcx, rdi
0x18006b79b  call    EditCreateCaretFromFont
0x18006b7a0  test    eax, eax
0x18006b7a2  jnz     short loc_18006B7C7
0x18006b7a4  mov     [rsp+68h+var_40], bx
0x18006b7a9  mov     r9d, esi
0x18006b7ac  mov     r8d, ebp
0x18006b7af  mov     [rsp+68h+var_48], r12d
0x18006b7b4  mov     rdx, r14
0x18006b7b7  mov     rcx, rdi
0x18006b7ba  call    EditCreateCaretFromFont
0x18006b7bf  test    eax, eax
0x18006b7c1  jz      loc_18006B71C
0x18006b7c7  mov     eax, r12d
0x18006b7ca  jmp     loc_18006B734
```
