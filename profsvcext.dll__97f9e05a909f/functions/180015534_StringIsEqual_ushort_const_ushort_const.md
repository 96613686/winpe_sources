# StringIsEqual(ushort const *,ushort const *)

- ea: `0x180015534`
- end: `0x180015560`
- name: `?StringIsEqual@@YAHPEBG0@Z`
- size: `44`
- prototype: `_BOOL8 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180007468`
- `0x18001375c`
- `0x180016b68`
- `0x180019380`
- `0x180019af8`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001554b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001554b`

## pseudocode

```c
_BOOL8 __fastcall StringIsEqual(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  return CompareStringOrdinal(a1, -1, a2, -1, 1) == 2;
}

```

## disassembly

```asm
0x180015534  sub     rsp, 38h
0x180015538  or      eax, 0FFFFFFFFh
0x18001553b  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x180015543  mov     r8, rdx; lpString2
0x180015546  mov     r9d, eax; cchCount2
0x180015549  mov     edx, eax; cchCount1
0x18001554b  call    cs:__imp_CompareStringOrdinal
0x180015551  xor     ecx, ecx
0x180015553  cmp     eax, 2
0x180015556  setz    cl
0x180015559  mov     eax, ecx
0x18001555b  add     rsp, 38h
0x18001555f  retn
```
