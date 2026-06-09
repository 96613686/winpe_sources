# CopyPutBlank(x,x,x)

- ea: `0x10032050`
- end: `0x10032091`
- name: `_CopyPutBlank@12`
- size: `65`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x10029aad`
- `0x1002c918`
- `0x1002cee0`
- `0x100321bc`

## callees

- `0x10031f11`
- `0x10031fd9`
- `0x10032050`

## pseudocode

```c
int __fastcall CopyPutBlank(int a1, int a2, int a3)
{
  int CopyBufferNode; // eax

  CopyBufferNode = AllocateCopyBufferNode();
  if ( !CopyBufferNode )
    return -1011;
  *(_BYTE *)(CopyBufferNode + 4) = *(_BYTE *)(a2 + 28);
  *(_WORD *)(CopyBufferNode + 8) = 1025;
  *(_DWORD *)(CopyBufferNode + 12) = a3;
  AddCopyCell(a1, CopyBufferNode);
  return 0;
}

```

## disassembly

```asm
0x10032050  mov     edi, edi
0x10032052  push    ebp
0x10032053  mov     ebp, esp
0x10032055  push    esi
0x10032056  push    edi
0x10032057  mov     esi, edx
0x10032059  mov     edi, ecx
0x1003205b  call    AllocateCopyBufferNode
0x10032060  mov     edx, eax
0x10032062  test    edx, edx
0x10032064  jnz     short loc_1003206D
0x10032066  mov     eax, 0FFFFFC0Dh
0x1003206b  jmp     short loc_1003208B
0x1003206d  mov     al, [esi+1Ch]
0x10032070  mov     ecx, edi
0x10032072  mov     [edx+4], al
0x10032075  mov     eax, 401h
0x1003207a  mov     [edx+8], ax
0x1003207e  mov     eax, [ebp+arg_0]
0x10032081  mov     [edx+0Ch], eax
0x10032084  call    AddCopyCell
0x10032089  xor     eax, eax
0x1003208b  pop     edi
0x1003208c  pop     esi
0x1003208d  pop     ebp
0x1003208e  retn    4
```
