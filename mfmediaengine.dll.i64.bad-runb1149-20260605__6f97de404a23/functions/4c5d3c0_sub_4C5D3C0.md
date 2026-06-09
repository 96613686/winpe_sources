# sub_4C5D3C0

- ea: `0x4c5d3c0`
- end: `0x4c5d3d2`
- name: `sub_4C5D3C0`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_4C5D3C0(__int64 a1, __int64 a2, int _EDX, __int64 a4)
{
  _DWORD *v5; // rbx
  __int64 v6; // rbp

  *(_BYTE *)(v6 + 3) += (_BYTE)_RAX;
  *_RAX &= (unsigned __int8)_RAX;
  __asm { lock add edx, [rax] }
  *(_BYTE *)(a4 - 97) += (_BYTE)_RAX;
  *(_DWORD *)_RAX += (_DWORD)_RAX;
  *(_BYTE *)(unsigned int)*v5 &= *v5;
  __asm { iret }
}

```

## disassembly

```asm
0x4c5d3c0  add     [rbp+3], al
0x4c5d3c3  and     [rax], al
0x4c5d3c5  lock add edx, [rax]
0x4c5d3c8  add     [rcx-61h], al
0x4c5d3cb  add     [rax], eax
0x4c5d3cd  mov     eax, [rbx]
0x4c5d3cf  and     [rax], al
0x4c5d3d1  iret
```
