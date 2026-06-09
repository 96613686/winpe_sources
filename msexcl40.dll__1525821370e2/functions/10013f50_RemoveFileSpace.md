# RemoveFileSpace

- ea: `0x10013f50`
- end: `0x10013fae`
- name: `RemoveFileSpace`
- size: `94`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, installer_update`

## callers

- `0x10014320`
- `0x100168a0`

## callees

- `0x10013d10`
- `0x10013f50`
- `0x100264c2`

## pseudocode

```c
int __fastcall RemoveFileSpace(int a1, int a2, int a3, int a4)
{
  int v6; // eax
  int result; // eax
  int savedregs; // [esp+8h] [ebp+0h] BYREF

  v6 = a1;
  if ( *(_DWORD *)a1 == 1 )
    v6 = *(_DWORD *)(a1 + 44);
  *(_DWORD *)(v6 + 104) = 0;
  *(_WORD *)(v6 + 96) = 0x4000;
  UpdateIndex(a2, (_DWORD *)a1, (int)&savedregs, -a3, a4);
  result = dword_10001970[abs32(BFRemoveFileSpace(*(_DWORD **)(a1 + 20), a2, a3))];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x10013f50  mov     edi, edi
0x10013f52  push    ebp
0x10013f53  mov     ebp, esp
0x10013f55  push    ebx
0x10013f56  push    edi
0x10013f57  mov     edi, ecx
0x10013f59  mov     ebx, edx
0x10013f5b  mov     eax, edi
0x10013f5d  cmp     dword ptr [edi], 1
0x10013f60  jnz     short loc_10013F65
0x10013f62  mov     eax, [edi+2Ch]
0x10013f65  push    [ebp+arg_4]
0x10013f68  mov     ecx, 4000h
0x10013f6d  mov     dword ptr [eax+68h], 0
0x10013f74  mov     [eax+60h], cx
0x10013f78  mov     ecx, edi
0x10013f7a  mov     eax, [ebp+arg_0]
0x10013f7d  neg     eax
0x10013f7f  push    eax
0x10013f80  call    UpdateIndex
0x10013f85  push    [ebp+arg_0]
0x10013f88  mov     ecx, [edi+14h]
0x10013f8b  mov     edx, ebx
0x10013f8d  call    _BFRemoveFileSpace@12; BFRemoveFileSpace(x,x,x)
0x10013f92  cdq
0x10013f93  mov     ecx, 0FFFFFFF6h
0x10013f98  xor     eax, edx
0x10013f9a  sub     eax, edx
0x10013f9c  pop     edi
0x10013f9d  pop     ebx
0x10013f9e  mov     eax, ds:dword_10001970[eax*4]
0x10013fa5  cmp     eax, ecx
0x10013fa7  cmovz   eax, ecx
0x10013faa  pop     ebp
0x10013fab  retn    8
```
