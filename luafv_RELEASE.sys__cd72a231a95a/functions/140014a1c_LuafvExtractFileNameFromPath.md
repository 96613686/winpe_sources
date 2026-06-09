# LuafvExtractFileNameFromPath

- ea: `0x140014a1c`
- end: `0x140014a89`
- name: `LuafvExtractFileNameFromPath`
- size: `109`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140023cc4`

## callees

- `0x140001a18`
- `0x140014a1c`

## pseudocode

```c
__int64 __fastcall LuafvExtractFileNameFromPath(__int64 a1, __int64 a2)
{
  unsigned __int16 v2; // r8
  __int64 v4; // r9
  __int16 v5; // cx
  __int64 result; // rax

  v2 = *(_WORD *)a2;
  if ( *(_WORD *)a2 >= 2u )
  {
    v4 = *(_QWORD *)(a2 + 8) - 2LL;
    do
    {
      v5 = *(_WORD *)(v4 + 2 * ((unsigned __int64)v2 >> 1));
      if ( v5 != 92 && v5 != 47 && v5 )
        break;
      v2 -= 2;
      *(_WORD *)a2 = v2;
    }
    while ( v2 >= 2u );
  }
  result = LuafvPathGetFileNamePart_UStr(a1, (unsigned __int16 *)a2);
  if ( (int)result < 0 )
  {
    *(_QWORD *)(a1 + 8) = 0;
    *(_DWORD *)a1 = 0;
  }
  return result;
}

```

## disassembly

```asm
0x140014a1c  mov     [rsp+arg_0], rbx
0x140014a21  push    rdi
0x140014a22  sub     rsp, 20h
0x140014a26  movzx   r8d, word ptr [rdx]
0x140014a2a  xor     edi, edi
0x140014a2c  mov     rbx, rcx
0x140014a2f  lea     r10d, [rdi+2]
0x140014a33  cmp     r8w, r10w
0x140014a37  jb      short loc_140014A6B
0x140014a39  mov     r9, [rdx+8]
0x140014a3d  sub     r9, r10
0x140014a40  movzx   eax, r8w
0x140014a44  shr     rax, 1
0x140014a47  movzx   ecx, word ptr [r9+rax*2]
0x140014a4c  cmp     cx, 5Ch ; '\'
0x140014a50  jz      short loc_140014A5D
0x140014a52  cmp     cx, 2Fh ; '/'
0x140014a56  jz      short loc_140014A5D
0x140014a58  test    cx, cx
0x140014a5b  jnz     short loc_140014A6B
0x140014a5d  sub     r8w, r10w
0x140014a61  mov     [rdx], r8w
0x140014a65  cmp     r8w, r10w
0x140014a69  jnb     short loc_140014A40
0x140014a6b  mov     rcx, rbx
0x140014a6e  call    LuafvPathGetFileNamePart_UStr
0x140014a73  test    eax, eax
0x140014a75  jns     short loc_140014A7D
0x140014a77  mov     [rbx+8], rdi
0x140014a7b  mov     [rbx], edi
0x140014a7d  mov     rbx, [rsp+28h+arg_0]
0x140014a82  add     rsp, 20h
0x140014a86  pop     rdi
0x140014a87  retn
```
