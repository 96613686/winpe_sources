# BfsGetShareName

- ea: `0x1400077a4`
- end: `0x14000781c`
- name: `BfsGetShareName`
- size: `120`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140009d2c`

## callees

- `0x1400077a4`

## pseudocode

```c
__int64 __fastcall BfsGetShareName(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  unsigned __int16 v4; // cx
  __int64 v5; // r9
  unsigned __int16 v6; // ax
  unsigned __int16 v7; // dx

  v2 = *(_QWORD *)(a2 + 48);
  *(_OWORD *)a1 = 0;
  if ( v2 )
  {
    *(_QWORD *)(a1 + 8) = v2;
    v4 = *(_WORD *)(a2 + 40);
    *(_WORD *)a1 = v4;
    if ( v4 < 2u || (v4 -= 2, v5 = v2 + 2, *(_QWORD *)(a1 + 8) = v2 + 2, *(_WORD *)a1 = v4, v4 < 2u) )
    {
      v7 = v4;
    }
    else
    {
      v6 = v4;
      do
      {
        v7 = v6;
        if ( *(_WORD *)(v5 + 2LL * (unsigned __int16)((v6 >> 1) - 1)) != 92 )
          break;
        v4 -= 2;
        *(_WORD *)a1 = v4;
        v6 = v4;
        v7 = v4;
      }
      while ( v4 >= 2u );
    }
    *(_WORD *)(a1 + 2) = v7;
  }
  return a1;
}

```

## disassembly

```asm
0x1400077a4  mov     rax, [rdx+30h]
0x1400077a8  xorps   xmm0, xmm0
0x1400077ab  mov     r8, rcx
0x1400077ae  movups  xmmword ptr [rcx], xmm0
0x1400077b1  test    rax, rax
0x1400077b4  jz      short loc_140007818
0x1400077b6  mov     [rcx+8], rax
0x1400077ba  mov     r10w, 2
0x1400077bf  movzx   ecx, word ptr [rdx+28h]
0x1400077c3  mov     [r8], cx
0x1400077c7  cmp     cx, r10w
0x1400077cb  jb      short loc_140007810
0x1400077cd  sub     cx, r10w
0x1400077d1  lea     r9, [rax+2]
0x1400077d5  mov     [r8+8], r9
0x1400077d9  mov     [r8], cx
0x1400077dd  cmp     cx, r10w
0x1400077e1  jb      short loc_140007810
0x1400077e3  movzx   eax, cx
0x1400077e6  movzx   edx, ax
0x1400077e9  shr     ax, 1
0x1400077ec  dec     ax
0x1400077ef  movzx   eax, ax
0x1400077f2  cmp     word ptr [r9+rax*2], 5Ch ; '\'
0x1400077f8  jnz     short loc_140007813
0x1400077fa  sub     cx, r10w
0x1400077fe  mov     [r8], cx
0x140007802  movzx   eax, cx
0x140007805  movzx   edx, cx
0x140007808  cmp     cx, r10w
0x14000780c  jnb     short loc_1400077E6
0x14000780e  jmp     short loc_140007813
0x140007810  movzx   edx, cx
0x140007813  mov     [r8+2], dx
0x140007818  mov     rax, r8
0x14000781b  retn
```
