# PreviewFile

- ea: `0x18000f0b8`
- end: `0x18000f254`
- name: `PreviewFile`
- size: `412`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000ed20`

## callees

- `0x180002280`
- `0x180003f98`
- `0x18000f004`
- `0x18000f0b8`
- `0x18000f388`
- `0x18000f41c`

## import_xrefs

- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000f1c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000f20b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000f1c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000f20b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f112`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18000f112`
- `GDI32!DeleteObject` at `0x18000f121`
- `GDI32!DeleteObject` at `0x18000f121`
- `USER32!SendMessageW` at `0x18000f103`
- `USER32!SendMessageW` at `0x18000f15d`
- `USER32!SendMessageW` at `0x18000f198`
- `USER32!SendMessageW` at `0x18000f1b5`
- `USER32!SendMessageW` at `0x18000f103`
- `USER32!SendMessageW` at `0x18000f15d`
- `USER32!SendMessageW` at `0x18000f198`
- `USER32!SendMessageW` at `0x18000f1b5`
- `USER32!ShowWindow` at `0x18000f0ee`
- `USER32!ShowWindow` at `0x18000f0ee`

## pseudocode

```c
__int64 __fastcall PreviewFile(__int64 a1, WCHAR *a2)
{
  HWND v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  const wchar_t *v8; // rax
  int v9; // ebx
  size_t v10; // rbp
  int v11; // eax
  unsigned int v12; // [rsp+20h] [rbp-38h]

  if ( !a1 )
    return 0;
  v4 = *(HWND *)(a1 + 96);
  if ( !v4 )
    return 0;
  *(_WORD *)(a1 + 128) = 0;
  ShowWindow(v4, 0);
  SendMessageW(*(HWND *)(a1 + 96), 0x804u, 0, 0);
  v5 = *(void **)(a1 + 120);
  if ( v5 )
    GlobalFree(v5);
  v6 = *(void **)(a1 + 112);
  if ( v6 )
    DeleteObject(v6);
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 112) = 0;
  PreviewPaint(a1);
  if ( a2 )
  {
    if ( !(unsigned int)SendMessageW(*(HWND *)(a1 + 96), 0x4FCu, 0, (LPARAM)a2) )
    {
      v8 = (const wchar_t *)NiceName(a2);
      StringCchCopyW((STRSAFE_LPWSTR)(a1 + 128), 0x80u, v8);
      if ( !(unsigned int)SendMessageW(*(HWND *)(a1 + 96), 0x4DBu, 0, (LPARAM)L"ms") )
      {
        v9 = SendMessageW(*(HWND *)(a1 + 96), 0x468u, 0, 0);
        if ( v9 > 0 )
        {
          v10 = 128LL - lstrlenW((LPCWSTR)(a1 + 128));
          v11 = lstrlenW((LPCWSTR)(a1 + 128));
          v12 = v9 / 0x3E8u % 0x3C;
          StringCchPrintfW((STRSAFE_LPWSTR)(a1 + 2 * (v11 + 64LL)), v10, L" (%02d:%02d)", v9 / 0xEA60u % 0x3C, v12);
        }
      }
    }
    PreviewSize(a1);
    PreviewPaint(a1);
  }
  return 1;
}

```

## disassembly

```asm
0x18000f0b8  push    rbx
0x18000f0ba  push    rbp
0x18000f0bb  push    rsi
0x18000f0bc  push    rdi
0x18000f0bd  push    r14
0x18000f0bf  sub     rsp, 30h
0x18000f0c3  mov     rbx, rdx
0x18000f0c6  mov     rsi, rcx
0x18000f0c9  test    rcx, rcx
0x18000f0cc  jz      loc_18000F247
0x18000f0d2  mov     rcx, [rcx+60h]; hWnd
0x18000f0d6  test    rcx, rcx
0x18000f0d9  jz      loc_18000F247
0x18000f0df  xor     eax, eax
0x18000f0e1  lea     r14, [rsi+80h]
0x18000f0e8  xor     edx, edx; nCmdShow
0x18000f0ea  mov     [r14], ax
0x18000f0ee  call    cs:__imp_ShowWindow
0x18000f0f4  mov     rcx, [rsi+60h]; hWnd
0x18000f0f8  xor     r9d, r9d; lParam
0x18000f0fb  xor     r8d, r8d; wParam
0x18000f0fe  mov     edx, 804h; Msg
0x18000f103  call    cs:__imp_SendMessageW
0x18000f109  mov     rcx, [rsi+78h]; hMem
0x18000f10d  test    rcx, rcx
0x18000f110  jz      short loc_18000F118
0x18000f112  call    cs:__imp_GlobalFree
0x18000f118  mov     rcx, [rsi+70h]; ho
0x18000f11c  test    rcx, rcx
0x18000f11f  jz      short loc_18000F127
0x18000f121  call    cs:__imp_DeleteObject
0x18000f127  mov     rcx, rsi
0x18000f12a  mov     qword ptr [rsi+78h], 0
0x18000f132  mov     qword ptr [rsi+70h], 0
0x18000f13a  call    PreviewPaint
0x18000f13f  test    rbx, rbx
0x18000f142  jnz     short loc_18000F14E
0x18000f144  mov     eax, 1
0x18000f149  jmp     loc_18000F249
0x18000f14e  mov     rcx, [rsi+60h]; hWnd
0x18000f152  mov     r9, rbx; lParam
0x18000f155  xor     r8d, r8d; wParam
0x18000f158  mov     edx, 4FCh; Msg
0x18000f15d  call    cs:__imp_SendMessageW
0x18000f163  test    eax, eax
0x18000f165  jnz     loc_18000F232
0x18000f16b  mov     rcx, rbx; lpsz
0x18000f16e  call    NiceName
0x18000f173  mov     ebp, 80h
0x18000f178  mov     r8, rax; pszSrc
0x18000f17b  mov     edx, ebp; cchDest
0x18000f17d  mov     rcx, r14; pszDest
0x18000f180  call    StringCchCopyW
0x18000f185  mov     rcx, [rsi+60h]; hWnd
0x18000f189  lea     r9, lParam; "ms"
0x18000f190  xor     r8d, r8d; wParam
0x18000f193  mov     edx, 4DBh; Msg
0x18000f198  call    cs:__imp_SendMessageW
0x18000f19e  test    eax, eax
0x18000f1a0  jnz     loc_18000F232
0x18000f1a6  mov     rcx, [rsi+60h]; hWnd
0x18000f1aa  xor     r9d, r9d; lParam
0x18000f1ad  xor     r8d, r8d; wParam
0x18000f1b0  mov     edx, 468h; Msg
0x18000f1b5  call    cs:__imp_SendMessageW
0x18000f1bb  mov     rbx, rax
0x18000f1be  test    eax, eax
0x18000f1c0  jle     short loc_18000F232
0x18000f1c2  mov     rcx, r14; lpString
0x18000f1c5  call    cs:__imp_lstrlenW
0x18000f1cb  movsxd  rcx, eax
0x18000f1ce  mov     eax, 10624DD3h
0x18000f1d3  mul     ebx
0x18000f1d5  sub     rbp, rcx
0x18000f1d8  mov     ecx, 88888889h
0x18000f1dd  mov     edi, edx
0x18000f1df  mov     eax, ecx
0x18000f1e1  shr     edi, 6
0x18000f1e4  mul     edi
0x18000f1e6  mov     eax, 45E7B273h
0x18000f1eb  shr     edx, 5
0x18000f1ee  imul    r8d, edx, 3Ch ; '<'
0x18000f1f2  mul     ebx
0x18000f1f4  mov     eax, ecx
0x18000f1f6  mov     rcx, r14; lpString
0x18000f1f9  mov     ebx, edx
0x18000f1fb  sub     edi, r8d
0x18000f1fe  shr     ebx, 0Eh
0x18000f201  mul     ebx
0x18000f203  shr     edx, 5
0x18000f206  imul    eax, edx, 3Ch ; '<'
0x18000f209  sub     ebx, eax
0x18000f20b  call    cs:__imp_lstrlenW
0x18000f211  mov     r9d, ebx
0x18000f214  mov     [rsp+58h+var_38], edi
0x18000f218  movsxd  rcx, eax
0x18000f21b  lea     r8, a02d02d; " (%02d:%02d)"
0x18000f222  add     rcx, 40h ; '@'
0x18000f226  mov     rdx, rbp; cchDest
0x18000f229  lea     rcx, [rsi+rcx*2]; pszDest
0x18000f22d  call    StringCchPrintfW
0x18000f232  mov     rcx, rsi
0x18000f235  call    PreviewSize
0x18000f23a  mov     rcx, rsi
0x18000f23d  call    PreviewPaint
0x18000f242  jmp     loc_18000F144
0x18000f247  xor     eax, eax
0x18000f249  add     rsp, 30h
0x18000f24d  pop     r14
0x18000f24f  pop     rdi
0x18000f250  pop     rsi
0x18000f251  pop     rbp
0x18000f252  pop     rbx
0x18000f253  retn
```
