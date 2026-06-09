# sub_3BF3EF0

- ea: `0x3bf3ef0`
- end: `0x3bf3efd`
- name: `sub_3BF3EF0`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall sub_3BF3EF0(_DWORD *a1, __int64 a2, __int64 a3)
{
  _BYTE *v3; // rax

  ++*a1;
  *(_BYTE *)(a3 + 73) += (_BYTE)v3;
  *v3 |= (unsigned __int8)v3;
  __asm { iret }
}

```

## disassembly

```asm
0x3bf3ef0  inc     dword ptr [rdi]
0x3bf3ef2  add     [rdx+49h], al
0x3bf3ef5  push    rax
0x3bf3ef8  push    rsp
0x3bf3ef9  push    rdx
0x3bf3efa  or      [rax], al
0x3bf3efc  iret
```
