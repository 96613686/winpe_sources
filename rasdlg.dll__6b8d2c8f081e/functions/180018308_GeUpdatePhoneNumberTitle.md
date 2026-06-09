# GeUpdatePhoneNumberTitle

- ea: `0x180018308`
- end: `0x18001841a`
- name: `GeUpdatePhoneNumberTitle`
- size: `274`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180018184`

## callees

- `0x18000f380`
- `0x180018308`
- `0x18003c43c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180018378`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180018378`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800183dd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180018407`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800183dd`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180018407`
- `USER32!SetWindowTextW` at `0x1800183d4`
- `USER32!SetWindowTextW` at `0x1800183fe`
- `USER32!SetWindowTextW` at `0x1800183d4`
- `USER32!SetWindowTextW` at `0x1800183fe`
- `rtutils!TracePrintfExA` at `0x1800183c7`
- `rtutils!TracePrintfExA` at `0x1800183c7`

## string_xrefs

- `0x1800183bb`: `GeUpdatePhoneNumberTitle: StringCchPrintfEx failed. hr = 0x%x`

## pseudocode

```c
void __fastcall GeUpdatePhoneNumberTitle(__int64 a1, __int64 a2)
{
  wchar_t *pszFormat; // rbx
  __int64 v5; // rcx
  __int64 v6; // rax
  size_t v7; // r14
  wchar_t *v8; // rax
  WCHAR *v9; // rdi
  HRESULT v10; // eax
  const WCHAR *v11; // rax

  if ( *(_QWORD *)(a1 + 104) )
  {
    if ( a2 )
    {
      pszFormat = (wchar_t *)PszFromId(g_hinstDll, 0x11Cu);
      if ( !pszFormat )
        return;
      v5 = -1;
      v6 = -1;
      do
        ++v6;
      while ( *(_WORD *)(a2 + 2 * v6) );
      do
        ++v5;
      while ( pszFormat[v5] );
      v7 = (int)v5 + (int)v6;
      v8 = (wchar_t *)GlobalAlloc(0x40u, 2 * v7);
      v9 = v8;
      if ( v8 )
      {
        v10 = StringCchPrintfExW(v8, v7, 0, 0, 0x100u, pszFormat, a2);
        if ( v10 < 0 && g_dwTraceId != -1 )
          TracePrintfExA(g_dwTraceId, 0xCu, "GeUpdatePhoneNumberTitle: StringCchPrintfEx failed. hr = 0x%x", v10);
        SetWindowTextW(*(HWND *)(a1 + 104), v9);
        GlobalFree(v9);
      }
    }
    else
    {
      v11 = (const WCHAR *)PszFromId(g_hinstDll, 0x1CDu);
      pszFormat = (wchar_t *)v11;
      if ( !v11 )
        return;
      SetWindowTextW(*(HWND *)(a1 + 104), v11);
    }
    GlobalFree(pszFormat);
  }
}

```

## disassembly

```asm
0x180018308  push    rbx
0x18001830a  push    rbp
0x18001830b  push    rsi
0x18001830c  push    rdi
0x18001830d  push    r14
0x18001830f  push    r15
0x180018311  sub     rsp, 48h
0x180018315  xor     r15d, r15d
0x180018318  mov     rbp, rdx
0x18001831b  mov     rsi, rcx
0x18001831e  cmp     [rcx+68h], r15
0x180018322  jz      loc_18001840D
0x180018328  mov     rcx, cs:g_hinstDll; hInstance
0x18001832f  test    rdx, rdx
0x180018332  jz      loc_1800183E5
0x180018338  mov     edx, 11Ch; uID
0x18001833d  call    PszFromId
0x180018342  mov     rbx, rax
0x180018345  test    rax, rax
0x180018348  jz      loc_18001840D
0x18001834e  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180018352  mov     rax, rcx
0x180018355  inc     rax
0x180018358  cmp     [rbp+rax*2+0], r15w
0x18001835e  jnz     short loc_180018355
0x180018360  inc     rcx
0x180018363  cmp     [rbx+rcx*2], r15w
0x180018368  jnz     short loc_180018360
0x18001836a  add     eax, ecx
0x18001836c  mov     ecx, 40h ; '@'; uFlags
0x180018371  movsxd  r14, eax
0x180018374  lea     rdx, [r14+r14]; dwBytes
0x180018378  call    cs:__imp_GlobalAlloc
0x18001837e  mov     rdi, rax
0x180018381  test    rax, rax
0x180018384  jz      short loc_180018404
0x180018386  mov     [rsp+78h+var_48], rbp
0x18001838b  xor     r9d, r9d; pcchRemaining
0x18001838e  mov     [rsp+78h+pszFormat], rbx; pszFormat
0x180018393  xor     r8d, r8d; ppszDestEnd
0x180018396  mov     rdx, r14; cchDest
0x180018399  mov     [rsp+78h+dwFlags], 100h; dwFlags
0x1800183a1  mov     rcx, rax; pszDest
0x1800183a4  call    StringCchPrintfExW
0x1800183a9  test    eax, eax
0x1800183ab  jns     short loc_1800183CD
0x1800183ad  mov     ecx, cs:g_dwTraceId; dwTraceID
0x1800183b3  cmp     ecx, 0FFFFFFFFh
0x1800183b6  jz      short loc_1800183CD
0x1800183b8  mov     r9d, eax
0x1800183bb  lea     r8, aGeupdatephonen; "GeUpdatePhoneNumberTitle: StringCchPrin"...
0x1800183c2  mov     edx, 0Ch; dwFlags
0x1800183c7  call    cs:__imp_TracePrintfExA
0x1800183cd  mov     rcx, [rsi+68h]; hWnd
0x1800183d1  mov     rdx, rdi; lpString
0x1800183d4  call    cs:__imp_SetWindowTextW
0x1800183da  mov     rcx, rdi; hMem
0x1800183dd  call    cs:__imp_GlobalFree
0x1800183e3  jmp     short loc_180018404
0x1800183e5  mov     edx, 1CDh; uID
0x1800183ea  call    PszFromId
0x1800183ef  mov     rbx, rax
0x1800183f2  test    rax, rax
0x1800183f5  jz      short loc_18001840D
0x1800183f7  mov     rcx, [rsi+68h]; hWnd
0x1800183fb  mov     rdx, rax; lpString
0x1800183fe  call    cs:__imp_SetWindowTextW
0x180018404  mov     rcx, rbx; hMem
0x180018407  call    cs:__imp_GlobalFree
0x18001840d  add     rsp, 48h
0x180018411  pop     r15
0x180018413  pop     r14
0x180018415  pop     rdi
0x180018416  pop     rsi
0x180018417  pop     rbp
0x180018418  pop     rbx
0x180018419  retn
```
