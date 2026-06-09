# NgcUtils::AreStringsEqual(ushort const *,ushort const *)

- ea: `0x180015000`
- end: `0x180015028`
- name: `?AreStringsEqual@NgcUtils@@YA_NPEBG0@Z`
- size: `40`
- prototype: `bool(NgcUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180014588`
- `0x180019424`
- `0x18001c708`
- `0x18001d9e4`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015017`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015017`

## pseudocode

```c
bool __fastcall NgcUtils::AreStringsEqual(const WCHAR *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  return CompareStringOrdinal(this, -1, a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180015000  sub     rsp, 38h
0x180015004  or      eax, 0FFFFFFFFh
0x180015007  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18001500f  mov     r8, rdx; lpString2
0x180015012  mov     r9d, eax; cchCount2
0x180015015  mov     edx, eax; cchCount1
0x180015017  call    cs:__imp_CompareStringOrdinal
0x18001501d  cmp     eax, 2
0x180015020  setz    al
0x180015023  add     rsp, 38h
0x180015027  retn
```
