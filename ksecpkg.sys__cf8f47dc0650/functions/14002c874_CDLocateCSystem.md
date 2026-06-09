# CDLocateCSystem

- ea: `0x14002c874`
- end: `0x14002c8a6`
- name: `CDLocateCSystem`
- size: `50`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x140025504`
- `0x1400263c0`
- `0x140026f70`
- `0x1400276c0`
- `0x1400291a0`
- `0x140029fe4`
- `0x14002a4d8`
- `0x14002bf1c`

## callees

- `0x14002c874`

## pseudocode

```c
__int64 __fastcall CDLocateCSystem(int a1, _QWORD *a2)
{
  int v2; // r8d
  unsigned __int64 v3; // rax

  v2 = cCSystems;
  while ( v2 )
  {
    v3 = (unsigned __int64)(unsigned int)--v2 << 7;
    if ( *(_DWORD *)((char *)&CSystems + v3) == a1 )
    {
      *a2 = (char *)&CSystems + v3;
      return 0;
    }
  }
  return 2148008769LL;
}

```

## disassembly

```asm
0x14002c874  mov     r8d, cs:cCSystems
0x14002c87b  test    r8d, r8d
0x14002c87e  jz      short loc_14002C8A0
0x14002c880  dec     r8d
0x14002c883  lea     r9, CSystems
0x14002c88a  mov     eax, r8d
0x14002c88d  shl     rax, 7
0x14002c891  add     r9, rax
0x14002c894  cmp     [r9], ecx
0x14002c897  jnz     short loc_14002C87B
0x14002c899  mov     [rdx], r9
0x14002c89c  xor     eax, eax
0x14002c89e  retn
0x14002c8a0  mov     eax, 80080341h
0x14002c8a5  retn
```
