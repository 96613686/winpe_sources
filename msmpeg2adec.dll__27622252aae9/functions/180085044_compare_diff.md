# compare_diff

- ea: `0x180085044`
- end: `0x18008509b`
- name: `compare_diff`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180082a18`
- `0x180085dac`

## callees

- `0x180085044`

## pseudocode

```c
__int64 __fastcall compare_diff(__int64 a1, unsigned __int64 a2, __int64 a3, unsigned __int64 a4)
{
  unsigned int v6; // eax
  unsigned int v7; // ecx

  while ( a2 > a4 )
  {
    if ( *(_DWORD *)(a1 + 4 * a2 - 4) )
      return 1;
    --a2;
  }
  while ( a4 > a2 )
  {
    if ( *(_DWORD *)(a3 + 4 * a4 - 4) )
      return 0xFFFFFFFFLL;
    --a4;
  }
  if ( !a2 )
    return 0;
  while ( 1 )
  {
    v6 = *(_DWORD *)(a1 + 4 * a2 - 4);
    v7 = *(_DWORD *)(a3 + 4 * a2 - 4);
    if ( v7 != v6 )
      break;
    if ( !--a2 )
      return 0;
  }
  return v7 < v6 ? 1 : -1;
}

```

## disassembly

```asm
0x180085044  mov     r10, rcx
0x180085047  jmp     short loc_180085053
0x180085049  cmp     dword ptr [rcx+rdx*4-4], 0
0x18008504e  jnz     short loc_18008505A
0x180085050  dec     rdx
0x180085053  cmp     rdx, r9
0x180085056  ja      short loc_180085049
0x180085058  jmp     short loc_18008506C
0x18008505a  mov     eax, 1
0x18008505f  retn
0x180085061  cmp     dword ptr [r8+r9*4-4], 0
0x180085067  jnz     short loc_18008508E
0x180085069  dec     r9
0x18008506c  cmp     r9, rdx
0x18008506f  ja      short loc_180085061
0x180085071  test    rdx, rdx
0x180085074  jz      short loc_18008508A
0x180085076  mov     eax, [r10+rdx*4-4]
0x18008507b  mov     ecx, [r8+rdx*4-4]
0x180085080  cmp     ecx, eax
0x180085082  jnz     short loc_180085093
0x180085084  sub     rdx, 1
0x180085088  jnz     short loc_180085076
0x18008508a  xor     eax, eax
0x18008508c  retn
0x18008508e  or      eax, 0FFFFFFFFh
0x180085091  retn
0x180085093  sbb     eax, eax
0x180085095  and     eax, 2
0x180085098  dec     eax
0x18008509a  retn
```
