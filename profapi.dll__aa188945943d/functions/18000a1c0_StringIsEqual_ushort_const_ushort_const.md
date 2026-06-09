# StringIsEqual(ushort const *,ushort const *)

- ea: `0x18000a1c0`
- end: `0x18000a1ed`
- name: `?StringIsEqual@@YAHPEBG0@Z`
- size: `45`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180009d10`
- `0x180009e70`
- `0x180009f90`
- `0x18000d620`
- `0x180016d14`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a1d8`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000a1d8`

## pseudocode

```c
_BOOL8 __fastcall StringIsEqual(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  return CompareStringOrdinal(a1, -1, a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x18000a1c0  sub     rsp, 38h
0x18000a1c4  mov     r9d, 0FFFFFFFFh; cchCount2
0x18000a1ca  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x18000a1d2  mov     r8, rdx; lpString2
0x18000a1d5  mov     edx, r9d; cchCount1
0x18000a1d8  call    cs:__imp_CompareStringOrdinal
0x18000a1de  xor     ecx, ecx
0x18000a1e0  cmp     eax, 2
0x18000a1e3  setz    cl
0x18000a1e6  mov     eax, ecx
0x18000a1e8  add     rsp, 38h
0x18000a1ec  retn
```
