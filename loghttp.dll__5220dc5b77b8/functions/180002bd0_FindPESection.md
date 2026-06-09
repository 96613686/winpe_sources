# _FindPESection

- ea: `0x180002bd0`
- end: `0x180002c13`
- name: `_FindPESection`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002c20`

## callees

- `0x180002bd0`

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
0x180002bd0  movsxd  r8, dword ptr [rcx+3Ch]
0x180002bd4  xor     r9d, r9d
0x180002bd7  add     r8, rcx
0x180002bda  movzx   eax, word ptr [r8+14h]
0x180002bdf  movzx   r10d, word ptr [r8+6]
0x180002be4  add     rax, 18h
0x180002be8  add     rax, r8
0x180002beb  test    r10d, r10d
0x180002bee  jz      short loc_180002C10
0x180002bf0  mov     r8d, [rax+0Ch]
0x180002bf4  cmp     rdx, r8
0x180002bf7  jb      short loc_180002C04
0x180002bf9  mov     ecx, [rax+8]
0x180002bfc  add     ecx, r8d
0x180002bff  cmp     rdx, rcx
0x180002c02  jb      short locret_180002C12
0x180002c04  inc     r9d
0x180002c07  add     rax, 28h ; '('
0x180002c0b  cmp     r9d, r10d
0x180002c0e  jb      short loc_180002BF0
0x180002c10  xor     eax, eax
0x180002c12  retn
```
