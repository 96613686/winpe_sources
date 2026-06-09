# CopyPutBool(x,x,x,x)

- ea: `0x10032097`
- end: `0x100320df`
- name: `_CopyPutBool@16`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1002c918`
- `0x1002cee0`

## callees

- `0x10031f11`
- `0x10031fd9`
- `0x10032097`

## pseudocode

```c
int __fastcall CopyPutBool(int a1, int a2, int a3, unsigned __int8 a4)
{
  int CopyBufferNode; // eax

  CopyBufferNode = AllocateCopyBufferNode();
  if ( !CopyBufferNode )
    return -1011;
  *(_BYTE *)(CopyBufferNode + 4) = *(_BYTE *)(a2 + 28);
  *(_WORD *)(CopyBufferNode + 8) = 1028;
  *(_DWORD *)(CopyBufferNode + 12) = a3;
  *(_DWORD *)(CopyBufferNode + 24) = a4;
  AddCopyCell(a1, CopyBufferNode);
  return 0;
}

```

## disassembly

```asm
0x10032097  mov     edi, edi
0x10032099  push    ebp
0x1003209a  mov     ebp, esp
0x1003209c  push    esi
0x1003209d  push    edi
0x1003209e  mov     esi, edx
0x100320a0  mov     edi, ecx
0x100320a2  call    AllocateCopyBufferNode
0x100320a7  mov     edx, eax
0x100320a9  test    edx, edx
0x100320ab  jnz     short loc_100320B4
0x100320ad  mov     eax, 0FFFFFC0Dh
0x100320b2  jmp     short loc_100320D9
0x100320b4  mov     al, [esi+1Ch]
0x100320b7  mov     ecx, edi
0x100320b9  mov     [edx+4], al
0x100320bc  mov     eax, 404h
0x100320c1  mov     [edx+8], ax
0x100320c5  mov     eax, [ebp+arg_0]
0x100320c8  mov     [edx+0Ch], eax
0x100320cb  movzx   eax, [ebp+arg_4]
0x100320cf  mov     [edx+18h], eax
0x100320d2  call    AddCopyCell
0x100320d7  xor     eax, eax
0x100320d9  pop     edi
0x100320da  pop     esi
0x100320db  pop     ebp
0x100320dc  retn    8
```
