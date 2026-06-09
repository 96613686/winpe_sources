# NgcUtils::AreStringsEqual(ushort const *,ushort const *)

- ea: `0x18001c724`
- end: `0x18001c74c`
- name: `?AreStringsEqual@NgcUtils@@YA_NPEBG0@Z`
- size: `40`
- prototype: `bool __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800110c4`
- `0x180015abc`
- `0x18001d954`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c73b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001c73b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall NgcUtils::AreStringsEqual(const WCHAR *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  return CompareStringOrdinal(this, -1, a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x18001c724  sub     rsp, 38h
0x18001c728  or      eax, 0FFFFFFFFh
0x18001c72b  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18001c733  mov     r8, rdx; lpString2
0x18001c736  mov     r9d, eax; cchCount2
0x18001c739  mov     edx, eax; cchCount1
0x18001c73b  call    cs:__imp_CompareStringOrdinal
0x18001c741  cmp     eax, 2
0x18001c744  setz    al
0x18001c747  add     rsp, 38h
0x18001c74b  retn
```
