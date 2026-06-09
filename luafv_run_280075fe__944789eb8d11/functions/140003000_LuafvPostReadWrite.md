# LuafvPostReadWrite

- ea: `0x140003000`
- end: `0x140003052`
- name: `LuafvPostReadWrite`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003000`

## pseudocode

```c
__int64 __fastcall LuafvPostReadWrite(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // r9
  _QWORD *v4; // rdx

  v3 = *(_QWORD *)(a2 + 32);
  if ( v3 )
  {
    if ( a3 )
    {
      v4 = *(_QWORD **)(a3 + 240);
      if ( v4 )
      {
        if ( (*(_DWORD *)(v3 + 80) & 2) != 0 && (**(_DWORD **)(a1 + 16) & 2) == 0 && *(int *)(a1 + 24) >= 0 )
          *(_QWORD *)(v3 + 104) = v4[13];
        *(_QWORD *)(v3 + 40) = v4[5];
        *(_QWORD *)(v3 + 48) = v4[6];
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140003000  mov     r9, [rdx+20h]
0x140003004  mov     r10, rcx
0x140003007  test    r9, r9
0x14000300a  jz      short loc_14000304F
0x14000300c  test    r8, r8
0x14000300f  jz      short loc_14000304F
0x140003011  mov     rdx, [r8+0F0h]
0x140003018  test    rdx, rdx
0x14000301b  jz      short loc_14000304F
0x14000301d  mov     eax, [r9+50h]
0x140003021  test    al, 2
0x140003023  jz      short loc_14000303F
0x140003025  mov     rax, [rcx+10h]
0x140003029  mov     ecx, [rax]
0x14000302b  test    cl, 2
0x14000302e  jnz     short loc_14000303F
0x140003030  cmp     dword ptr [r10+18h], 0
0x140003035  jl      short loc_14000303F
0x140003037  mov     rax, [rdx+68h]
0x14000303b  mov     [r9+68h], rax
0x14000303f  mov     rax, [rdx+28h]
0x140003043  mov     [r9+28h], rax
0x140003047  mov     rax, [rdx+30h]
0x14000304b  mov     [r9+30h], rax
0x14000304f  xor     eax, eax
0x140003051  retn
```
