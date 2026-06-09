# TraverseHuffmanTree

- ea: `0x18000bb20`
- end: `0x18000bb55`
- name: `TraverseHuffmanTree`
- size: `53`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b2d0`
- `0x18000bb20`
- `0x18001ae0c`

## callees

- `0x18000bb20`

## pseudocode

```c
__int64 __fastcall TraverseHuffmanTree(int a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 result; // rax

  while ( 1 )
  {
    v4 = *(_QWORD *)(a2 + 8);
    if ( !v4 )
      break;
    result = TraverseHuffmanTree((unsigned int)++a1, v4);
    a2 = *(_QWORD *)(a2 + 16);
  }
  *(_DWORD *)(a2 + 8) = a1;
  return result;
}

```

## disassembly

```asm
0x18000bb20  mov     [rsp+arg_0], rbx
0x18000bb25  push    rdi
0x18000bb26  sub     rsp, 20h
0x18000bb2a  mov     rbx, rdx
0x18000bb2d  mov     edi, ecx
0x18000bb2f  mov     rdx, [rbx+8]
0x18000bb33  test    rdx, rdx
0x18000bb36  jnz     short loc_18000BB46
0x18000bb38  mov     [rbx+8], edi
0x18000bb3b  mov     rbx, [rsp+28h+arg_0]
0x18000bb40  add     rsp, 20h
0x18000bb44  pop     rdi
0x18000bb45  retn
0x18000bb46  inc     edi
0x18000bb48  mov     ecx, edi
0x18000bb4a  call    TraverseHuffmanTree
0x18000bb4f  mov     rbx, [rbx+10h]
0x18000bb53  jmp     short loc_18000BB2F
```
