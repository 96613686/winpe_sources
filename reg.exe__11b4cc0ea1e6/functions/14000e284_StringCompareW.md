# StringCompareW

- ea: `0x14000e284`
- end: `0x14000e2f2`
- name: `StringCompareW`
- size: `110`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000375c`
- `0x140003c48`
- `0x14000612c`
- `0x140006394`
- `0x140008788`
- `0x14000eae0`

## callees

- `0x14000e284`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e2d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e2d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e2e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e2e1`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000e2c9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000e2c9`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14000e2b0`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14000e2b0`

## pseudocode

```c
__int64 __fastcall StringCompareW(PCNZWCH lpString1, PCNZWCH lpString2, int a3, int a4)
{
  int cchCount2; // edi
  DWORD v7; // ebx
  LCID ThreadLocale; // eax

  if ( lpString1 && lpString2 )
  {
    cchCount2 = -1;
    if ( a4 )
      cchCount2 = a4;
    v7 = a3 == 1;
    ThreadLocale = GetThreadLocale();
    return (unsigned int)(CompareStringW(ThreadLocale, v7, lpString1, cchCount2, lpString2, cchCount2) - 2);
  }
  else
  {
    if ( !GetLastError() )
      SetLastError(0x57u);
    return 0;
  }
}

```

## disassembly

```asm
0x14000e284  push    rbx
0x14000e286  push    rbp
0x14000e287  push    rsi
0x14000e288  push    rdi
0x14000e289  sub     rsp, 38h
0x14000e28d  mov     rsi, rdx
0x14000e290  mov     rbp, rcx
0x14000e293  test    rcx, rcx
0x14000e296  jz      short loc_14000E2D4
0x14000e298  test    rdx, rdx
0x14000e29b  jz      short loc_14000E2D4
0x14000e29d  or      edi, 0FFFFFFFFh
0x14000e2a0  test    r9d, r9d
0x14000e2a3  cmovnz  edi, r9d
0x14000e2a7  xor     ebx, ebx
0x14000e2a9  cmp     r8d, 1
0x14000e2ad  setz    bl
0x14000e2b0  call    cs:__imp_GetThreadLocale
0x14000e2b6  mov     [rsp+58h+cchCount2], edi; cchCount2
0x14000e2ba  mov     r9d, edi; cchCount1
0x14000e2bd  mov     ecx, eax; Locale
0x14000e2bf  mov     [rsp+58h+lpString2], rsi; lpString2
0x14000e2c4  mov     r8, rbp; lpString1
0x14000e2c7  mov     edx, ebx; dwCmpFlags
0x14000e2c9  call    cs:__imp_CompareStringW
0x14000e2cf  sub     eax, 2
0x14000e2d2  jmp     short loc_14000E2E9
0x14000e2d4  call    cs:__imp_GetLastError
0x14000e2da  test    eax, eax
0x14000e2dc  jnz     short loc_14000E2E7
0x14000e2de  lea     ecx, [rax+57h]; dwErrCode
0x14000e2e1  call    cs:__imp_SetLastError
0x14000e2e7  xor     eax, eax
0x14000e2e9  add     rsp, 38h
0x14000e2ed  pop     rdi
0x14000e2ee  pop     rsi
0x14000e2ef  pop     rbp
0x14000e2f0  pop     rbx
0x14000e2f1  retn
```
