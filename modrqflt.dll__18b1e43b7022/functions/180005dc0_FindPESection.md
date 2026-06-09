# _FindPESection

- ea: `0x180005dc0`
- end: `0x180005e03`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e10`

## callees

- `0x180005dc0`

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
0x180005dc0  movsxd  r8, dword ptr [rcx+3Ch]
0x180005dc4  xor     r9d, r9d
0x180005dc7  add     r8, rcx
0x180005dca  movzx   eax, word ptr [r8+14h]
0x180005dcf  movzx   r10d, word ptr [r8+6]
0x180005dd4  add     rax, 18h
0x180005dd8  add     rax, r8
0x180005ddb  test    r10d, r10d
0x180005dde  jz      short loc_180005E00
0x180005de0  mov     r8d, [rax+0Ch]
0x180005de4  cmp     rdx, r8
0x180005de7  jb      short loc_180005DF4
0x180005de9  mov     ecx, [rax+8]
0x180005dec  add     ecx, r8d
0x180005def  cmp     rdx, rcx
0x180005df2  jb      short locret_180005E02
0x180005df4  inc     r9d
0x180005df7  add     rax, 28h ; '('
0x180005dfb  cmp     r9d, r10d
0x180005dfe  jb      short loc_180005DE0
0x180005e00  xor     eax, eax
0x180005e02  retn
```
