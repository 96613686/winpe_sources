# StringCompareExW

- ea: `0x14000ee5c`
- end: `0x14000eec4`
- name: `StringCompareExW`
- size: `104`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001e90`
- `0x140002338`
- `0x14000263c`
- `0x140002a78`
- `0x1400031f4`
- `0x140003e34`
- `0x14000426c`
- `0x14000456c`
- `0x140004e84`
- `0x140006e6c`
- `0x14000799c`
- `0x14000957c`
- `0x14000a0e0`
- `0x14000a358`
- `0x14000a6d8`
- `0x14000dbb8`
- `0x14000e050`

## callees

- `0x14000ee5c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee9d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee9d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eeb0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000eeb0`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000ee8c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000ee8c`

## pseudocode

```c
__int64 __fastcall StringCompareExW(PCNZWCH lpString1, PCNZWCH lpString2, __int64 a3, int a4)
{
  int cchCount2; // r9d

  if ( lpString1 && lpString2 )
  {
    cchCount2 = -1;
    if ( a4 )
      cchCount2 = a4;
    return (unsigned int)(CompareStringW(0x7Fu, 1u, lpString1, cchCount2, lpString2, cchCount2) - 2);
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
0x14000ee5c  sub     rsp, 38h
0x14000ee60  mov     eax, r9d
0x14000ee63  test    rcx, rcx
0x14000ee66  jz      short loc_14000EE9D
0x14000ee68  test    rdx, rdx
0x14000ee6b  jz      short loc_14000EE9D
0x14000ee6d  or      r9d, 0FFFFFFFFh
0x14000ee71  mov     r8, rcx; lpString1
0x14000ee74  test    eax, eax
0x14000ee76  cmovnz  r9d, eax; cchCount1
0x14000ee7a  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x14000ee7f  mov     [rsp+38h+lpString2], rdx; lpString2
0x14000ee84  mov     edx, 1; dwCmpFlags
0x14000ee89  lea     ecx, [rdx+7Eh]; Locale
0x14000ee8c  call    cs:__imp_CompareStringW
0x14000ee93  nop     dword ptr [rax+rax+00h]
0x14000ee98  sub     eax, 2
0x14000ee9b  jmp     short loc_14000EEBE
0x14000ee9d  call    cs:__imp_GetLastError
0x14000eea4  nop     dword ptr [rax+rax+00h]
0x14000eea9  test    eax, eax
0x14000eeab  jnz     short loc_14000EEBC
0x14000eead  lea     ecx, [rax+57h]; dwErrCode
0x14000eeb0  call    cs:__imp_SetLastError
0x14000eeb7  nop     dword ptr [rax+rax+00h]
0x14000eebc  xor     eax, eax
0x14000eebe  add     rsp, 38h
0x14000eec2  retn
```
