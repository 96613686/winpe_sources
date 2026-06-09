# sub_4CD9BD9

- ea: `0x4cd9bd9`
- end: `0x4cd9be2`
- name: `sub_4CD9BD9`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall sub_4CD9BD9()
{
  void *v0; // rax
  _DWORD *v1; // rbx
  _BYTE retaddr[16]; // [rsp+0h] [rbp+0h]

  __sgdt(v0);
  *(_BYTE *)(unsigned int)*v1 &= *v1;
  return MK_FP(*(_WORD *)retaddr, *(_QWORD *)retaddr)();
}

```

## disassembly

```asm
0x4cd9bd9  sgdt    fword ptr [rax]
0x4cd9bdd  mov     eax, [rbx]
0x4cd9bdf  and     [rax], al
0x4cd9be1  retf
```
