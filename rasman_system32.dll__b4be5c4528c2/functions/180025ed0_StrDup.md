# StrDup

- ea: `0x180025ed0`
- end: `0x180025fa2`
- name: `StrDup`
- size: `210`
- prototype: `__int64 __fastcall(STRSAFE_LPCWSTR pszSrc)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180025480`
- `0x180026ac8`
- `0x180027074`

## callees

- `0x180025ed0`
- `0x180026058`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180025f80`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x180025f80`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180025f04`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x180025f04`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025eed`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180025eed`
- `rtutils!TracePrintfExA` at `0x180025f2d`
- `rtutils!TracePrintfExA` at `0x180025f71`
- `rtutils!TracePrintfExA` at `0x180025f2d`
- `rtutils!TracePrintfExA` at `0x180025f71`

## string_xrefs

- `0x180025f65`: `StrDup: StringCchCopyEx failed with error 0x%x`

## pseudocode

```c
wchar_t *__fastcall StrDup(STRSAFE_LPCWSTR pszSrc)
{
  wchar_t *v1; // rbx
  size_t v3; // rsi
  wchar_t *v4; // rax
  STRSAFE_LPWSTR *v5; // r9
  HRESULT v7; // eax
  size_t *v8; // [rsp+20h] [rbp-18h]

  v1 = 0;
  if ( !pszSrc )
    return v1;
  v3 = (unsigned int)(lstrlenW(pszSrc) + 1);
  v4 = (wchar_t *)GlobalAlloc(0x40u, 2 * v3);
  v1 = v4;
  if ( v4 )
  {
    v7 = StringCchCopyExW(v4, v3, pszSrc, v5, v8, 0x100u);
    if ( v7 < 0 )
    {
      if ( g_dwTraceId != -1 )
        TracePrintfExA(g_dwTraceId, 0xCu, "StrDup: StringCchCopyEx failed with error 0x%x", v7);
      GlobalFree(v1);
      return 0;
    }
    return v1;
  }
  if ( g_dwTraceId != -1 )
    TracePrintfExA(g_dwTraceId, 0xCu, "StrDup Malloc failed");
  return 0;
}

```

## disassembly

```asm
0x180025ed0  mov     [rsp+arg_0], rbx
0x180025ed5  mov     [rsp+arg_8], rsi
0x180025eda  push    rdi
0x180025edb  sub     rsp, 30h
0x180025edf  xor     ebx, ebx
0x180025ee1  mov     rdi, rcx
0x180025ee4  test    rcx, rcx
0x180025ee7  jz      loc_180025F8E
0x180025eed  call    cs:__imp_lstrlenW
0x180025ef4  nop     dword ptr [rax+rax+00h]
0x180025ef9  inc     eax
0x180025efb  lea     ecx, [rbx+40h]; uFlags
0x180025efe  mov     esi, eax
0x180025f00  lea     rdx, [rax+rax]; dwBytes
0x180025f04  call    cs:__imp_GlobalAlloc
0x180025f0b  nop     dword ptr [rax+rax+00h]
0x180025f10  mov     rbx, rax
0x180025f13  test    rax, rax
0x180025f16  jnz     short loc_180025F3D
0x180025f18  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025f1e  cmp     ecx, 0FFFFFFFFh
0x180025f21  jz      short loc_180025F39
0x180025f23  lea     r8, aStrdupMallocFa; "StrDup Malloc failed"
0x180025f2a  lea     edx, [rax+0Ch]; dwFlags
0x180025f2d  call    cs:__imp_TracePrintfExA
0x180025f34  nop     dword ptr [rax+rax+00h]
0x180025f39  xor     eax, eax
0x180025f3b  jmp     short loc_180025F91
0x180025f3d  mov     r8, rdi; pszSrc
0x180025f40  mov     [rsp+38h+dwFlags], 100h; dwFlags
0x180025f48  mov     rdx, rsi; cchDest
0x180025f4b  mov     rcx, rbx; pszDest
0x180025f4e  call    StringCchCopyExW
0x180025f53  test    eax, eax
0x180025f55  jns     short loc_180025F8E
0x180025f57  mov     ecx, cs:g_dwTraceId; dwTraceID
0x180025f5d  cmp     ecx, 0FFFFFFFFh
0x180025f60  jz      short loc_180025F7D
0x180025f62  mov     r9d, eax
0x180025f65  lea     r8, aStrdupStringcc; "StrDup: StringCchCopyEx failed with err"...
0x180025f6c  mov     edx, 0Ch; dwFlags
0x180025f71  call    cs:__imp_TracePrintfExA
0x180025f78  nop     dword ptr [rax+rax+00h]
0x180025f7d  mov     rcx, rbx; hMem
0x180025f80  call    cs:__imp_GlobalFree
0x180025f87  nop     dword ptr [rax+rax+00h]
0x180025f8c  xor     ebx, ebx
0x180025f8e  mov     rax, rbx
0x180025f91  mov     rbx, [rsp+38h+arg_0]
0x180025f96  mov     rsi, [rsp+38h+arg_8]
0x180025f9b  add     rsp, 30h
0x180025f9f  pop     rdi
0x180025fa0  retn
```
