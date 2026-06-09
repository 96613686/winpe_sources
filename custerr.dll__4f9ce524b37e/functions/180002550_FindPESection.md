# _FindPESection

- ea: `0x180002550`
- end: `0x180002593`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025a0`

## callees

- `0x180002550`

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
0x180002550  movsxd  r8, dword ptr [rcx+3Ch]
0x180002554  xor     r9d, r9d
0x180002557  add     r8, rcx
0x18000255a  movzx   eax, word ptr [r8+14h]
0x18000255f  movzx   r10d, word ptr [r8+6]
0x180002564  add     rax, 18h
0x180002568  add     rax, r8
0x18000256b  test    r10d, r10d
0x18000256e  jz      short loc_180002590
0x180002570  mov     r8d, [rax+0Ch]
0x180002574  cmp     rdx, r8
0x180002577  jb      short loc_180002584
0x180002579  mov     ecx, [rax+8]
0x18000257c  add     ecx, r8d
0x18000257f  cmp     rdx, rcx
0x180002582  jb      short locret_180002592
0x180002584  inc     r9d
0x180002587  add     rax, 28h ; '('
0x18000258b  cmp     r9d, r10d
0x18000258e  jb      short loc_180002570
0x180002590  xor     eax, eax
0x180002592  retn
```
