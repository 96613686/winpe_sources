# StringCompareExW

- ea: `0x14000e228`
- end: `0x14000e27d`
- name: `StringCompareExW`
- size: `85`
- prototype: `__int64 __fastcall(PCNZWCH lpString1, PCNZWCH lpString2)`
- caller_count: `17`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140001e90`
- `0x140002290`
- `0x1400024a4`
- `0x140002940`
- `0x1400030b8`
- `0x140003c48`
- `0x14000406c`
- `0x140004354`
- `0x140004bbc`
- `0x140006a5c`
- `0x14000752c`
- `0x140008fe8`
- `0x140009ae4`
- `0x140009d40`
- `0x14000a0a0`
- `0x14000d204`
- `0x14000d5c4`

## callees

- `0x14000e228`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e263`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000e263`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e270`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000e270`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000e258`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x14000e258`

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
0x14000e228  sub     rsp, 38h
0x14000e22c  mov     eax, r9d
0x14000e22f  test    rcx, rcx
0x14000e232  jz      short loc_14000E263
0x14000e234  test    rdx, rdx
0x14000e237  jz      short loc_14000E263
0x14000e239  or      r9d, 0FFFFFFFFh
0x14000e23d  mov     r8, rcx; lpString1
0x14000e240  test    eax, eax
0x14000e242  cmovnz  r9d, eax; cchCount1
0x14000e246  mov     [rsp+38h+cchCount2], r9d; cchCount2
0x14000e24b  mov     [rsp+38h+lpString2], rdx; lpString2
0x14000e250  mov     edx, 1; dwCmpFlags
0x14000e255  lea     ecx, [rdx+7Eh]; Locale
0x14000e258  call    cs:__imp_CompareStringW
0x14000e25e  sub     eax, 2
0x14000e261  jmp     short loc_14000E278
0x14000e263  call    cs:__imp_GetLastError
0x14000e269  test    eax, eax
0x14000e26b  jnz     short loc_14000E276
0x14000e26d  lea     ecx, [rax+57h]; dwErrCode
0x14000e270  call    cs:__imp_SetLastError
0x14000e276  xor     eax, eax
0x14000e278  add     rsp, 38h
0x14000e27c  retn
```
