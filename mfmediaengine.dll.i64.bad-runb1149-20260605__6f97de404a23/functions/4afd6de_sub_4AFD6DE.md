# sub_4AFD6DE

- ea: `0x4afd6de`
- end: `0x4afd6e6`
- name: `sub_4AFD6DE`
- size: `8`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_4AFD6DE()
{
  char v0; // cf
  void *v1; // rax
  _DWORD *v2; // rbx

  __sgdt(v1);
  *(_BYTE *)(unsigned int)*v2 += *v2 + v0;
  __asm { iret }
}

```

## disassembly

```asm
0x4afd6de  sgdt    fword ptr [rax]
0x4afd6e1  mov     eax, [rbx]
0x4afd6e3  adc     [rax], al
0x4afd6e5  iret
```
