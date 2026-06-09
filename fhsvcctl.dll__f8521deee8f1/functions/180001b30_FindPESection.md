# _FindPESection

- ea: `0x180001b30`
- end: `0x180001b73`
- name: `_FindPESection`
- size: `67`
- prototype: `__int64 __fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001b80`

## callees

- `0x180001b30`

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
0x180001b30  movsxd  r8, dword ptr [rcx+3Ch]
0x180001b34  xor     r9d, r9d
0x180001b37  add     r8, rcx
0x180001b3a  movzx   eax, word ptr [r8+14h]
0x180001b3f  movzx   r10d, word ptr [r8+6]
0x180001b44  add     rax, 18h
0x180001b48  add     rax, r8
0x180001b4b  test    r10d, r10d
0x180001b4e  jz      short loc_180001B70
0x180001b50  mov     r8d, [rax+0Ch]
0x180001b54  cmp     rdx, r8
0x180001b57  jb      short loc_180001B64
0x180001b59  mov     ecx, [rax+8]
0x180001b5c  add     ecx, r8d
0x180001b5f  cmp     rdx, rcx
0x180001b62  jb      short locret_180001B72
0x180001b64  inc     r9d
0x180001b67  add     rax, 28h ; '('
0x180001b6b  cmp     r9d, r10d
0x180001b6e  jb      short loc_180001B50
0x180001b70  xor     eax, eax
0x180001b72  retn
```
