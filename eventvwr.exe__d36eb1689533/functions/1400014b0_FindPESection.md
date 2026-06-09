# _FindPESection

- ea: `0x1400014b0`
- end: `0x1400014f3`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001500`

## callees

- `0x1400014b0`

## pseudocode

```c
__int64 __fastcall FindPESection(__int64 a1, unsigned __int64 a2)
{
  unsigned int v2; // r9d
  __int64 v3; // r8
  unsigned int v4; // r10d
  __int64 result; // rax
  unsigned __int64 v6; // r8

  v2 = 0;
  v3 = a1 + *(int *)(a1 + 60);
  v4 = *(unsigned __int16 *)(v3 + 6);
  result = v3 + *(unsigned __int16 *)(v3 + 20) + 24LL;
  if ( !*(_WORD *)(v3 + 6) )
    return 0;
  while ( 1 )
  {
    v6 = *(unsigned int *)(result + 12);
    if ( a2 >= v6 && a2 < (unsigned int)(v6 + *(_DWORD *)(result + 8)) )
      break;
    ++v2;
    result += 40;
    if ( v2 >= v4 )
      return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400014b0  movsxd  r8, dword ptr [rcx+3Ch]
0x1400014b4  xor     r9d, r9d
0x1400014b7  add     r8, rcx
0x1400014ba  movzx   eax, word ptr [r8+14h]
0x1400014bf  movzx   r10d, word ptr [r8+6]
0x1400014c4  add     rax, 18h
0x1400014c8  add     rax, r8
0x1400014cb  test    r10d, r10d
0x1400014ce  jz      short loc_1400014F0
0x1400014d0  mov     r8d, [rax+0Ch]
0x1400014d4  cmp     rdx, r8
0x1400014d7  jb      short loc_1400014E4
0x1400014d9  mov     ecx, [rax+8]
0x1400014dc  add     ecx, r8d
0x1400014df  cmp     rdx, rcx
0x1400014e2  jb      short locret_1400014F2
0x1400014e4  inc     r9d
0x1400014e7  add     rax, 28h ; '('
0x1400014eb  cmp     r9d, r10d
0x1400014ee  jb      short loc_1400014D0
0x1400014f0  xor     eax, eax
0x1400014f2  retn
```
