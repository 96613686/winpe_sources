# LuafvPathGetFileNamePart_UStr

- ea: `0x140001a18`
- end: `0x140001ab5`
- name: `LuafvPathGetFileNamePart_UStr`
- size: `157`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140014a1c`

## callees

- `0x140001a18`

## pseudocode

```c
__int64 __fastcall LuafvPathGetFileNamePart_UStr(__int64 a1, unsigned __int16 *a2)
{
  __int64 v2; // r9
  unsigned int v3; // ebx
  unsigned __int64 v4; // r8
  unsigned __int64 v5; // r11
  unsigned __int16 v6; // dx
  __int16 v7; // ax
  __int64 result; // rax

  v2 = *((_QWORD *)a2 + 1);
  if ( v2 && (v3 = *a2, v3 >= 2) )
  {
    v4 = 0;
    v5 = (unsigned __int64)*a2 >> 1;
    while ( 1 )
    {
      if ( v4 >= v5 )
      {
        v6 = a2[1];
        goto LABEL_13;
      }
      if ( *(_WORD *)(v2 + 2 * (v5 - v4) - 2) == 92 )
        break;
      ++v4;
    }
    if ( v4 || (_WORD)v3 != a2[1] )
    {
      v7 = 2 * v4 - v3;
      LOWORD(v3) = 2 * v4;
      v6 = a2[1] + v7;
      v2 += 2 * (v5 - v4);
    }
    else
    {
      v6 = 0;
      LOWORD(v3) = 0;
      v2 = 0;
    }
  }
  else
  {
    v6 = 0;
    LOWORD(v3) = 0;
    v2 = 0;
  }
LABEL_13:
  *(_QWORD *)(a1 + 8) = v2;
  result = 0;
  *(_WORD *)a1 = v3;
  *(_WORD *)(a1 + 2) = v6;
  return result;
}

```

## disassembly

```asm
0x140001a18  mov     [rsp+arg_0], rbx
0x140001a1d  mov     r9, [rdx+8]
0x140001a21  mov     r10, rcx
0x140001a24  test    r9, r9
0x140001a27  jz      short loc_140001A90
0x140001a29  movzx   ebx, word ptr [rdx]
0x140001a2c  cmp     ebx, 2
0x140001a2f  jb      short loc_140001A90
0x140001a31  xor     r8d, r8d
0x140001a34  mov     r11d, ebx
0x140001a37  shr     r11, 1
0x140001a3a  cmp     r8, r11
0x140001a3d  jnb     short loc_140001A8A
0x140001a3f  mov     rax, r11
0x140001a42  sub     rax, r8
0x140001a45  cmp     word ptr [r9+rax*2-2], 5Ch ; '\'
0x140001a4c  jz      short loc_140001A53
0x140001a4e  inc     r8
0x140001a51  jmp     short loc_140001A3A
0x140001a53  test    r8, r8
0x140001a56  jnz     short loc_140001A67
0x140001a58  cmp     bx, [rdx+2]
0x140001a5c  jnz     short loc_140001A67
0x140001a5e  xor     edx, edx
0x140001a60  xor     ebx, ebx
0x140001a62  xor     r9d, r9d
0x140001a65  jmp     short loc_140001A85
0x140001a67  movzx   ecx, r8w
0x140001a6b  add     cx, cx
0x140001a6e  movzx   eax, cx
0x140001a71  sub     ax, bx
0x140001a74  movzx   ebx, cx
0x140001a77  add     ax, [rdx+2]
0x140001a7b  sub     r11, r8
0x140001a7e  movzx   edx, ax
0x140001a81  lea     r9, [r9+r11*2]
0x140001a85  mov     rcx, r10
0x140001a88  jmp     short loc_140001A9B
0x140001a8a  movzx   edx, word ptr [rdx+2]
0x140001a8e  jmp     short loc_140001A9B
0x140001a90  xor     eax, eax
0x140001a92  movzx   edx, ax
0x140001a95  movzx   ebx, ax
0x140001a98  xor     r9d, r9d
0x140001a9b  mov     eax, 8
0x140001aa0  mov     [rax+r10], r9
0x140001aa4  xor     eax, eax
0x140001aa6  mov     [rcx], bx
0x140001aa9  mov     [r10+2], dx
0x140001aae  mov     rbx, [rsp+arg_0]
0x140001ab3  retn
```
