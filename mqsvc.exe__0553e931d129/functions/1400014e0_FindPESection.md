# _FindPESection

- ea: `0x1400014e0`
- end: `0x140001523`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140001530`

## callees

- `0x1400014e0`

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
0x1400014e0  movsxd  r8, dword ptr [rcx+3Ch]
0x1400014e4  xor     r9d, r9d
0x1400014e7  add     r8, rcx
0x1400014ea  movzx   eax, word ptr [r8+14h]
0x1400014ef  movzx   r10d, word ptr [r8+6]
0x1400014f4  add     rax, 18h
0x1400014f8  add     rax, r8
0x1400014fb  test    r10d, r10d
0x1400014fe  jz      short loc_140001520
0x140001500  mov     r8d, [rax+0Ch]
0x140001504  cmp     rdx, r8
0x140001507  jb      short loc_140001514
0x140001509  mov     ecx, [rax+8]
0x14000150c  add     ecx, r8d
0x14000150f  cmp     rdx, rcx
0x140001512  jb      short locret_140001522
0x140001514  inc     r9d
0x140001517  add     rax, 28h ; '('
0x14000151b  cmp     r9d, r10d
0x14000151e  jb      short loc_140001500
0x140001520  xor     eax, eax
0x140001522  retn
```
