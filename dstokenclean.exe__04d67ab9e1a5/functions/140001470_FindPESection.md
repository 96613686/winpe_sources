# _FindPESection

- ea: `0x140001470`
- end: `0x1400014b3`
- name: `_FindPESection`
- size: `67`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400014c0`

## callees

- `0x140001470`

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
0x140001470  movsxd  r8, dword ptr [rcx+3Ch]
0x140001474  xor     r9d, r9d
0x140001477  add     r8, rcx
0x14000147a  movzx   eax, word ptr [r8+14h]
0x14000147f  movzx   r10d, word ptr [r8+6]
0x140001484  add     rax, 18h
0x140001488  add     rax, r8
0x14000148b  test    r10d, r10d
0x14000148e  jz      short loc_1400014B0
0x140001490  mov     r8d, [rax+0Ch]
0x140001494  cmp     rdx, r8
0x140001497  jb      short loc_1400014A4
0x140001499  mov     ecx, [rax+8]
0x14000149c  add     ecx, r8d
0x14000149f  cmp     rdx, rcx
0x1400014a2  jb      short locret_1400014B2
0x1400014a4  inc     r9d
0x1400014a7  add     rax, 28h ; '('
0x1400014ab  cmp     r9d, r10d
0x1400014ae  jb      short loc_140001490
0x1400014b0  xor     eax, eax
0x1400014b2  retn
```
