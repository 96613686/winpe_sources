# StringCompareW

- ea: `0x14000eecc`
- end: `0x14000ef53`
- name: `StringCompareW`
- size: `135`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400038f8`
- `0x140003e34`
- `0x1400064b0`
- `0x14000672c`
- `0x140008cbc`
- `0x14000f78c`

## callees

- `0x14000eecc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ef28`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ef28`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ef3b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ef3b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000ef17`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000ef17`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14000eef8`
- `api-ms-win-core-localization-l1-2-0!GetThreadLocale` at `0x14000eef8`

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
0x14000eecc  push    rbx
0x14000eece  push    rbp
0x14000eecf  push    rsi
0x14000eed0  push    rdi
0x14000eed1  sub     rsp, 38h
0x14000eed5  mov     rsi, rdx
0x14000eed8  mov     rbp, rcx
0x14000eedb  test    rcx, rcx
0x14000eede  jz      short loc_14000EF28
0x14000eee0  test    rdx, rdx
0x14000eee3  jz      short loc_14000EF28
0x14000eee5  or      edi, 0FFFFFFFFh
0x14000eee8  test    r9d, r9d
0x14000eeeb  cmovnz  edi, r9d
0x14000eeef  xor     ebx, ebx
0x14000eef1  cmp     r8d, 1
0x14000eef5  setz    bl
0x14000eef8  call    cs:__imp_GetThreadLocale
0x14000eeff  nop     dword ptr [rax+rax+00h]
0x14000ef04  mov     [rsp+58h+cchCount2], edi; cchCount2
0x14000ef08  mov     r9d, edi; cchCount1
0x14000ef0b  mov     ecx, eax; Locale
0x14000ef0d  mov     [rsp+58h+lpString2], rsi; lpString2
0x14000ef12  mov     r8, rbp; lpString1
0x14000ef15  mov     edx, ebx; dwCmpFlags
0x14000ef17  call    cs:__imp_CompareStringW
0x14000ef1e  nop     dword ptr [rax+rax+00h]
0x14000ef23  sub     eax, 2
0x14000ef26  jmp     short loc_14000EF49
0x14000ef28  call    cs:__imp_GetLastError
0x14000ef2f  nop     dword ptr [rax+rax+00h]
0x14000ef34  test    eax, eax
0x14000ef36  jnz     short loc_14000EF47
0x14000ef38  lea     ecx, [rax+57h]; dwErrCode
0x14000ef3b  call    cs:__imp_SetLastError
0x14000ef42  nop     dword ptr [rax+rax+00h]
0x14000ef47  xor     eax, eax
0x14000ef49  add     rsp, 38h
0x14000ef4d  pop     rdi
0x14000ef4e  pop     rsi
0x14000ef4f  pop     rbp
0x14000ef50  pop     rbx
0x14000ef51  retn
```
