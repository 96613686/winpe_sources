# PerflibiIsEqualCounter

- ea: `0x1800014c0`
- end: `0x180001518`
- name: `PerflibiIsEqualCounter`
- size: `88`
- prototype: `bool __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180015e20`

## callees

- `0x1800014c0`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000150a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000150a`

## pseudocode

```c
bool __fastcall PerflibiIsEqualCounter(__int64 a1, __int64 a2)
{
  unsigned int v3; // eax

  if ( *(_DWORD *)(a1 + 24) != *(_DWORD *)(a2 + 24) )
    return 0;
  v3 = *(_DWORD *)(a2 + 20);
  if ( *(_DWORD *)(a1 + 20) <= 0x28u )
    return v3 <= 0x28;
  if ( v3 <= 0x28 || *(_DWORD *)(a1 + 28) != *(_DWORD *)(a2 + 28) )
    return 0;
  return CompareStringOrdinal((LPCWCH)(a1 + 40), -1, (LPCWCH)(a2 + 40), -1, 1) == 2;
}

```

## disassembly

```asm
0x1800014c0  sub     rsp, 38h
0x1800014c4  mov     eax, [rdx+18h]
0x1800014c7  cmp     [rcx+18h], eax
0x1800014ca  jz      short loc_1800014D3
0x1800014cc  xor     al, al
0x1800014ce  add     rsp, 38h
0x1800014d2  retn
0x1800014d3  cmp     dword ptr [rcx+14h], 28h ; '('
0x1800014d7  mov     eax, [rdx+14h]
0x1800014da  ja      short loc_1800014E5
0x1800014dc  cmp     eax, 28h ; '('
0x1800014df  ja      short loc_1800014CC
0x1800014e1  mov     al, 1
0x1800014e3  jmp     short loc_1800014CE
0x1800014e5  cmp     eax, 28h ; '('
0x1800014e8  jbe     short loc_1800014CC
0x1800014ea  mov     eax, [rdx+1Ch]
0x1800014ed  cmp     [rcx+1Ch], eax
0x1800014f0  jnz     short loc_1800014CC
0x1800014f2  lea     r8, [rdx+28h]; lpString2
0x1800014f6  mov     [rsp+38h+bIgnoreCase], 1; bIgnoreCase
0x1800014fe  mov     edx, 0FFFFFFFFh; cchCount1
0x180001503  add     rcx, 28h ; '('; lpString1
0x180001507  mov     r9d, edx; cchCount2
0x18000150a  call    cs:__imp_CompareStringOrdinal
0x180001510  cmp     eax, 2
0x180001513  setz    al
0x180001516  jmp     short loc_1800014CE
```
