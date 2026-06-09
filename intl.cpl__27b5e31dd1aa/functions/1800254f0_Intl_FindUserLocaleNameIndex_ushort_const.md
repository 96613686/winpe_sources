# Intl_FindUserLocaleNameIndex(ushort const *)

- ea: `0x1800254f0`
- end: `0x180025546`
- name: `?Intl_FindUserLocaleNameIndex@@YAKPEBG@Z`
- size: `86`
- prototype: `unsigned int __fastcall(LPCWCH lpString2)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18001ebc8`
- `0x180025480`
- `0x180025cac`

## callees

- `0x1800254f0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002552a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18002552a`

## pseudocode

```c
__int64 __fastcall Intl_FindUserLocaleNameIndex(LPCWCH lpString2)
{
  __int64 i; // rbx
  __int64 result; // rax

  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    result = g_dwLocaleCount;
    if ( (unsigned int)i >= g_dwLocaleCount )
      break;
    if ( CompareStringOrdinal(*(LPCWCH *)(*((_QWORD *)g_localeInfo + i) + 8LL), -1, lpString2, -1, 1) == 2 )
      return (unsigned int)i;
  }
  return result;
}

```

## disassembly

```asm
0x1800254f0  mov     [rsp+arg_0], rbx
0x1800254f5  push    rdi
0x1800254f6  sub     rsp, 30h
0x1800254fa  mov     rdi, rcx
0x1800254fd  xor     ebx, ebx
0x1800254ff  mov     eax, cs:?g_dwLocaleCount@@3KA; ulong g_dwLocaleCount
0x180025505  cmp     ebx, eax
0x180025507  jnb     short loc_18002553B
0x180025509  mov     rax, cs:?g_localeInfo@@3PEAPEAULocaleInfo@@EA; LocaleInfo * * g_localeInfo
0x180025510  or      r9d, 0FFFFFFFFh; cchCount2
0x180025514  mov     r8, rdi; lpString2
0x180025517  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18002551f  or      edx, r9d; cchCount1
0x180025522  mov     rcx, [rax+rbx*8]
0x180025526  mov     rcx, [rcx+8]; lpString1
0x18002552a  call    cs:__imp_CompareStringOrdinal
0x180025530  cmp     eax, 2
0x180025533  jz      short loc_180025539
0x180025535  inc     ebx
0x180025537  jmp     short loc_1800254FF
0x180025539  mov     eax, ebx
0x18002553b  mov     rbx, [rsp+38h+arg_0]
0x180025540  add     rsp, 30h
0x180025544  pop     rdi
0x180025545  retn
```
