# OpenFileSpace

- ea: `0x10013ee0`
- end: `0x10013f3b`
- name: `OpenFileSpace`
- size: `91`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x10014020`
- `0x10014320`
- `0x10016060`
- `0x100163d0`
- `0x10016680`
- `0x10018430`

## callees

- `0x10013d10`
- `0x10013ee0`
- `0x10026233`

## pseudocode

```c
int __fastcall OpenFileSpace(int a1, int a2, unsigned int a3, int a4)
{
  int v6; // eax
  int result; // eax
  int savedregs; // [esp+8h] [ebp+0h] BYREF

  v6 = a1;
  if ( *(_DWORD *)a1 == 1 )
    v6 = *(_DWORD *)(a1 + 44);
  *(_DWORD *)(v6 + 104) = 0;
  *(_WORD *)(v6 + 96) = 0x4000;
  UpdateIndex(a2, (_DWORD *)a1, (int)&savedregs, a3, a4);
  result = dword_10001970[abs32(BFOpenFileSpace(*(size_t **)(a1 + 20), a2, a3))];
  if ( result == -10 )
    return -10;
  return result;
}

```

## disassembly

```asm
0x10013ee0  mov     edi, edi
0x10013ee2  push    ebp
0x10013ee3  mov     ebp, esp
0x10013ee5  push    ebx
0x10013ee6  push    edi
0x10013ee7  mov     edi, ecx
0x10013ee9  mov     ebx, edx
0x10013eeb  mov     eax, edi
0x10013eed  cmp     dword ptr [edi], 1
0x10013ef0  jnz     short loc_10013EF5
0x10013ef2  mov     eax, [edi+2Ch]
0x10013ef5  push    [ebp+arg_4]
0x10013ef8  mov     ecx, 4000h
0x10013efd  mov     dword ptr [eax+68h], 0
0x10013f04  push    [ebp+arg_0]
0x10013f07  mov     [eax+60h], cx
0x10013f0b  mov     ecx, edi
0x10013f0d  call    UpdateIndex
0x10013f12  push    [ebp+arg_0]
0x10013f15  mov     ecx, [edi+14h]
0x10013f18  mov     edx, ebx
0x10013f1a  call    _BFOpenFileSpace@12; BFOpenFileSpace(x,x,x)
0x10013f1f  cdq
0x10013f20  mov     ecx, 0FFFFFFF6h
0x10013f25  xor     eax, edx
0x10013f27  sub     eax, edx
0x10013f29  pop     edi
0x10013f2a  pop     ebx
0x10013f2b  mov     eax, ds:dword_10001970[eax*4]
0x10013f32  cmp     eax, ecx
0x10013f34  cmovz   eax, ecx
0x10013f37  pop     ebp
0x10013f38  retn    8
```
