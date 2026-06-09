# _PropVarCompareStrCmp(ushort const *,ushort const *,int)

- ea: `0x18004d184`
- end: `0x18004d212`
- name: `?_PropVarCompareStrCmp@@YAHPEBG0H@Z`
- size: `142`
- prototype: `__int64 __fastcall(LPCWCH lpString1, LPCWCH lpString2, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000f050`

## callees

- `0x18004d184`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004d1e3`
- `api-ms-win-core-string-l1-1-0!CompareStringEx` at `0x18004d1e3`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18004d20b`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x18004d200`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpCW` at `0x18004d1f5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpLogicalW` at `0x18004d1aa`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpW` at `0x18004d1b5`

## pseudocode

```c
int __fastcall _PropVarCompareStrCmp(LPCWCH lpString1, LPCWCH lpString2, char a3)
{
  if ( (a3 & 2) != 0 )
    return StrCmpW(lpString1, lpString2);
  if ( (a3 & 4) != 0 )
    return StrCmpCW(lpString1, lpString2);
  if ( (a3 & 8) != 0 )
    return StrCmpIW(lpString1, lpString2);
  if ( (a3 & 0x10) != 0 )
    return StrCmpICW(lpString1, lpString2);
  if ( (a3 & 0x20) != 0 )
    return CompareStringEx(0, 8u, lpString1, -1, lpString2, -1, 0, 0, 0) - 2;
  return StrCmpLogicalW(lpString1, lpString2);
}

```

## disassembly

```asm
0x18004d184  sub     rsp, 58h
0x18004d188  test    r8b, 2
0x18004d18c  jnz     short loc_18004D1B1
0x18004d18e  test    r8b, 4
0x18004d192  jnz     short loc_18004D1F1
0x18004d194  test    r8b, 8
0x18004d198  jnz     short loc_18004D1FC
0x18004d19a  test    r8b, 10h
0x18004d19e  jnz     short loc_18004D207
0x18004d1a0  test    r8b, 20h
0x18004d1a4  jnz     short loc_18004D1BC
0x18004d1a6  add     rsp, 58h
0x18004d1aa  jmp     cs:__imp_StrCmpLogicalW
0x18004d1b1  add     rsp, 58h
0x18004d1b5  jmp     cs:__imp_StrCmpW
0x18004d1bc  xor     eax, eax
0x18004d1be  or      r9d, 0FFFFFFFFh; cchCount1
0x18004d1c2  mov     [rsp+58h+lParam], rax; lParam
0x18004d1c7  mov     r8, rcx; lpString1
0x18004d1ca  mov     [rsp+58h+lpReserved], rax; lpReserved
0x18004d1cf  xor     ecx, ecx; lpLocaleName
0x18004d1d1  mov     [rsp+58h+lpVersionInformation], rax; lpVersionInformation
0x18004d1d6  mov     [rsp+58h+cchCount2], r9d; cchCount2
0x18004d1db  mov     [rsp+58h+lpString2], rdx; lpString2
0x18004d1e0  lea     edx, [rax+8]; dwCmpFlags
0x18004d1e3  call    cs:__imp_CompareStringEx
0x18004d1e9  sub     eax, 2
0x18004d1ec  add     rsp, 58h
0x18004d1f0  retn
0x18004d1f1  add     rsp, 58h
0x18004d1f5  jmp     cs:__imp_StrCmpCW
0x18004d1fc  add     rsp, 58h
0x18004d200  jmp     cs:__imp_StrCmpIW
0x18004d207  add     rsp, 58h
0x18004d20b  jmp     cs:__imp_StrCmpICW
```
