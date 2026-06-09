# CopyPutLongText(x,x,x,x,x)

- ea: `0x10032274`
- end: `0x10032319`
- name: `_CopyPutLongText@20`
- size: `165`
- prototype: `int __stdcall(int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1002cee0`

## callees

- `0x1002580a`
- `0x10025ab7`
- `0x10031ef2`
- `0x10031f11`
- `0x10031fd9`
- `0x10032274`
- `0x1003669c`

## pseudocode

```c
int __fastcall CopyPutLongText(int a1, int a2, int a3, void *Src, size_t Size)
{
  size_t v5; // edi
  int CopyBufferNode; // eax
  _DWORD *v7; // esi
  unsigned __int8 v9; // cl
  _DWORD *v10; // ecx
  void *v11; // eax
  int v14; // [esp+10h] [ebp-4h]

  v5 = Size >> 1;
  CopyBufferNode = AllocateCopyBufferNode();
  v7 = (_DWORD *)CopyBufferNode;
  if ( !CopyBufferNode )
    return -1011;
  v9 = *(_BYTE *)(a2 + 28);
  *(_BYTE *)(CopyBufferNode + 4) = v9;
  *(_WORD *)(CopyBufferNode + 8) = 1168;
  *(_DWORD *)(CopyBufferNode + 12) = a3;
  v14 = AssociatedColumnMemo(a1, v9);
  v10 = *(_DWORD **)(v14 + 12);
  if ( v10 )
    MemFree(v10);
  v11 = (void *)MemAllocate(Size + 2);
  *(_DWORD *)(v14 + 12) = v11;
  if ( !v11 )
  {
    MemFree(v7);
    return -1011;
  }
  *(_DWORD *)(v14 + 8) = v5;
  memcpy(v11, Src, Size);
  *(_WORD *)(*(_DWORD *)(v14 + 12) + 2 * v5) = 0;
  AddCopyCell(a1, v7);
  return 0;
}

```

## disassembly

```asm
0x10032274  mov     edi, edi
0x10032276  push    ebp
0x10032277  mov     ebp, esp
0x10032279  push    ecx
0x1003227a  push    ecx
0x1003227b  push    ebx
0x1003227c  mov     ebx, [ebp+Size]
0x1003227f  push    esi
0x10032280  push    edi
0x10032281  mov     edi, ebx
0x10032283  mov     [ebp+var_4], edx
0x10032286  mov     [ebp+var_8], ecx
0x10032289  shr     edi, 1
0x1003228b  call    AllocateCopyBufferNode
0x10032290  mov     esi, eax
0x10032292  test    esi, esi
0x10032294  jnz     short loc_1003229D
0x10032296  mov     eax, 0FFFFFC0Dh
0x1003229b  jmp     short loc_10032312
0x1003229d  mov     ecx, [ebp+var_4]
0x100322a0  mov     eax, 490h
0x100322a5  mov     cl, [ecx+1Ch]
0x100322a8  mov     [esi+4], cl
0x100322ab  mov     [esi+8], ax
0x100322af  mov     eax, [ebp+arg_0]
0x100322b2  movzx   edx, cl
0x100322b5  mov     ecx, [ebp+var_8]
0x100322b8  mov     [esi+0Ch], eax
0x100322bb  call    _AssociatedColumnMemo@8; AssociatedColumnMemo(x,x)
0x100322c0  mov     [ebp+var_4], eax
0x100322c3  mov     ecx, [eax+0Ch]
0x100322c6  test    ecx, ecx
0x100322c8  jz      short loc_100322CF
0x100322ca  call    _MemFree@4; MemFree(x)
0x100322cf  lea     ecx, [ebx+2]
0x100322d2  call    _MemAllocate@4; MemAllocate(x)
0x100322d7  mov     ecx, [ebp+var_4]
0x100322da  mov     [ecx+0Ch], eax
0x100322dd  test    eax, eax
0x100322df  jnz     short loc_100322EA
0x100322e1  mov     ecx, esi
0x100322e3  call    _MemFree@4; MemFree(x)
0x100322e8  jmp     short loc_10032296
0x100322ea  push    ebx; Size
0x100322eb  push    [ebp+Src]; Src
0x100322ee  mov     [ecx+8], edi
0x100322f1  push    eax; void *
0x100322f2  call    _memcpy
0x100322f7  mov     eax, [ebp+var_4]
0x100322fa  xor     ecx, ecx
0x100322fc  add     esp, 0Ch
0x100322ff  mov     edx, esi
0x10032301  mov     eax, [eax+0Ch]
0x10032304  mov     [eax+edi*2], cx
0x10032308  mov     ecx, [ebp+var_8]
0x1003230b  call    AddCopyCell
0x10032310  xor     eax, eax
0x10032312  pop     edi
0x10032313  pop     esi
0x10032314  pop     ebx
0x10032315  leave
0x10032316  retn    0Ch
```
