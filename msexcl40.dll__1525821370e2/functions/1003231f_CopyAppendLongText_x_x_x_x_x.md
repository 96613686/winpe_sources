# CopyAppendLongText(x,x,x,x,x)

- ea: `0x1003231f`
- end: `0x10032381`
- name: `_CopyAppendLongText@20`
- size: `98`
- prototype: `int __stdcall(int, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1002cee0`

## callees

- `0x10025986`
- `0x10031ef2`
- `0x1003231f`
- `0x1003669c`

## pseudocode

```c
int __fastcall CopyAppendLongText(int a1, int a2, int a3, void *Src, size_t Size)
{
  int v5; // esi
  size_t v6; // edi
  _DWORD *v7; // ecx
  int v9; // eax
  int v10; // eax

  v5 = AssociatedColumnMemo(a1, *(__int16 *)(a2 + 28));
  v6 = *(_DWORD *)(v5 + 8) + (Size >> 1);
  v7 = MemReAllocate(*(_DWORD **)(v5 + 12), 2 * v6 + 2);
  if ( !v7 )
    return -1011;
  v9 = *(_DWORD *)(v5 + 8);
  *(_DWORD *)(v5 + 12) = v7;
  memcpy((char *)v7 + 2 * v9, Src, Size);
  v10 = *(_DWORD *)(v5 + 12);
  *(_DWORD *)(v5 + 8) = v6;
  *(_WORD *)(v10 + 2 * v6) = 0;
  return 0;
}

```

## disassembly

```asm
0x1003231f  mov     edi, edi
0x10032321  push    ebp
0x10032322  mov     ebp, esp
0x10032324  movsx   edx, word ptr [edx+1Ch]
0x10032328  push    esi
0x10032329  push    edi
0x1003232a  call    _AssociatedColumnMemo@8; AssociatedColumnMemo(x,x)
0x1003232f  mov     edi, [ebp+Size]
0x10032332  mov     esi, eax
0x10032334  shr     edi, 1
0x10032336  add     edi, [esi+8]
0x10032339  mov     ecx, [esi+0Ch]; Src
0x1003233c  lea     edx, ds:2[edi*2]
0x10032343  call    _MemReAllocate@8; MemReAllocate(x,x)
0x10032348  mov     ecx, eax
0x1003234a  test    ecx, ecx
0x1003234c  jnz     short loc_10032355
0x1003234e  mov     eax, 0FFFFFC0Dh
0x10032353  jmp     short loc_1003237B
0x10032355  mov     eax, [esi+8]
0x10032358  push    [ebp+Size]; Size
0x1003235b  mov     [esi+0Ch], ecx
0x1003235e  push    [ebp+Src]; Src
0x10032361  lea     eax, [ecx+eax*2]
0x10032364  push    eax; void *
0x10032365  call    _memcpy
0x1003236a  mov     eax, [esi+0Ch]
0x1003236d  xor     ecx, ecx
0x1003236f  mov     [esi+8], edi
0x10032372  add     esp, 0Ch
0x10032375  mov     [eax+edi*2], cx
0x10032379  xor     eax, eax
0x1003237b  pop     edi
0x1003237c  pop     esi
0x1003237d  pop     ebp
0x1003237e  retn    0Ch
```
