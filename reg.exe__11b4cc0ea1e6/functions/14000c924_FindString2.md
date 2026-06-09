# FindString2

- ea: `0x14000c924`
- end: `0x14000c9ba`
- name: `FindString2`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400053e0`
- `0x140006394`
- `0x14000a0a0`
- `0x14000d010`

## callees

- `0x14000c924`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c99a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000c99a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c9a7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000c9a7`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x14000c984`
- `api-ms-win-core-libraryloader-l1-2-0!FindStringOrdinal` at `0x14000c984`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000c941`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000c94c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000c941`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x14000c94c`

## pseudocode

```c
__int64 __fastcall FindString2(const WCHAR *a1, const WCHAR *a2, __int64 a3, unsigned int a4)
{
  __int64 v4; // rsi
  unsigned int v7; // edi
  unsigned int v8; // eax
  int StringOrdinal; // eax
  DWORD v11; // ecx

  v4 = a4;
  if ( a1 && a2 )
  {
    v7 = lstrlenW(a1);
    v8 = lstrlenW(a2);
    if ( v8 )
    {
      if ( v7 )
      {
        if ( (unsigned int)v4 < v7 && v7 - (unsigned int)v4 >= v8 )
        {
          StringOrdinal = FindStringOrdinal(0x400000u, &a1[v4], -1, a2, -1, 1);
          if ( StringOrdinal != -1 )
            return (unsigned int)(v4 + StringOrdinal);
        }
      }
    }
    v11 = 1168;
    goto LABEL_12;
  }
  if ( !GetLastError() )
  {
    v11 = 87;
LABEL_12:
    SetLastError(v11);
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x14000c924  push    rbp
0x14000c926  push    rsi
0x14000c927  push    rdi
0x14000c928  push    r14
0x14000c92a  sub     rsp, 38h
0x14000c92e  mov     esi, r9d
0x14000c931  mov     rbp, rdx
0x14000c934  mov     r14, rcx
0x14000c937  test    rcx, rcx
0x14000c93a  jz      short loc_14000C99A
0x14000c93c  test    rdx, rdx
0x14000c93f  jz      short loc_14000C99A
0x14000c941  call    cs:__imp_lstrlenW
0x14000c947  mov     rcx, rbp; lpString
0x14000c94a  mov     edi, eax
0x14000c94c  call    cs:__imp_lstrlenW
0x14000c952  test    eax, eax
0x14000c954  jz      short loc_14000C993
0x14000c956  test    edi, edi
0x14000c958  jz      short loc_14000C993
0x14000c95a  cmp     esi, edi
0x14000c95c  jnb     short loc_14000C993
0x14000c95e  sub     edi, esi
0x14000c960  cmp     edi, eax
0x14000c962  jb      short loc_14000C993
0x14000c964  lea     rdx, [r14+rsi*2]; lpStringSource
0x14000c968  mov     [rsp+58h+bIgnoreCase], 1; bIgnoreCase
0x14000c970  mov     r9, rbp; lpStringValue
0x14000c973  mov     [rsp+58h+cchValue], 0FFFFFFFFh; cchValue
0x14000c97b  or      r8d, 0FFFFFFFFh; cchSource
0x14000c97f  mov     ecx, 400000h; dwFindStringOrdinalFlags
0x14000c984  call    cs:__imp_FindStringOrdinal
0x14000c98a  cmp     eax, 0FFFFFFFFh
0x14000c98d  jz      short loc_14000C993
0x14000c98f  add     eax, esi
0x14000c991  jmp     short loc_14000C9B0
0x14000c993  mov     ecx, 490h
0x14000c998  jmp     short loc_14000C9A7
0x14000c99a  call    cs:__imp_GetLastError
0x14000c9a0  test    eax, eax
0x14000c9a2  jnz     short loc_14000C9AD
0x14000c9a4  lea     ecx, [rax+57h]; dwErrCode
0x14000c9a7  call    cs:__imp_SetLastError
0x14000c9ad  or      eax, 0FFFFFFFFh
0x14000c9b0  add     rsp, 38h
0x14000c9b4  pop     r14
0x14000c9b6  pop     rdi
0x14000c9b7  pop     rsi
0x14000c9b8  pop     rbp
0x14000c9b9  retn
```
