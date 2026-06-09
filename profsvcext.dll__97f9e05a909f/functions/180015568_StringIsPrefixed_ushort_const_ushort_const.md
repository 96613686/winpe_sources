# StringIsPrefixed(ushort const *,ushort const *)

- ea: `0x180015568`
- end: `0x180015598`
- name: `?StringIsPrefixed@@YAHPEBG0@Z`
- size: `48`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007bd0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015583`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180015583`

## pseudocode

```c
_BOOL8 __fastcall StringIsPrefixed(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  return CompareStringOrdinal(a1, 4, L"\\\\?\\", 4, 1) == 2;
}

```

## disassembly

```asm
0x180015568  sub     rsp, 38h
0x18001556c  mov     edx, 4; cchCount1
0x180015571  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180015579  mov     r9d, edx; cchCount2
0x18001557c  lea     r8, asc_180023DF0; "\\\\?\\"
0x180015583  call    cs:__imp_CompareStringOrdinal
0x180015589  xor     ecx, ecx
0x18001558b  cmp     eax, 2
0x18001558e  setz    cl
0x180015591  mov     eax, ecx
0x180015593  add     rsp, 38h
0x180015597  retn
```
