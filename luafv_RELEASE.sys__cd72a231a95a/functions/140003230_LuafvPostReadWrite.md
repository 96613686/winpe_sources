# LuafvPostReadWrite

- ea: `0x140003230`
- end: `0x140003282`
- name: `LuafvPostReadWrite`
- size: `82`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140003230`

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
0x140003230  mov     r9, [rdx+20h]
0x140003234  mov     r10, rcx
0x140003237  test    r9, r9
0x14000323a  jz      short loc_14000327F
0x14000323c  test    r8, r8
0x14000323f  jz      short loc_14000327F
0x140003241  mov     rdx, [r8+0F0h]
0x140003248  test    rdx, rdx
0x14000324b  jz      short loc_14000327F
0x14000324d  mov     eax, [r9+50h]
0x140003251  test    al, 2
0x140003253  jz      short loc_14000326F
0x140003255  mov     rax, [rcx+10h]
0x140003259  mov     ecx, [rax]
0x14000325b  test    cl, 2
0x14000325e  jnz     short loc_14000326F
0x140003260  cmp     dword ptr [r10+18h], 0
0x140003265  jl      short loc_14000326F
0x140003267  mov     rax, [rdx+68h]
0x14000326b  mov     [r9+68h], rax
0x14000326f  mov     rax, [rdx+28h]
0x140003273  mov     [r9+28h], rax
0x140003277  mov     rax, [rdx+30h]
0x14000327b  mov     [r9+30h], rax
0x14000327f  xor     eax, eax
0x140003281  retn
```
