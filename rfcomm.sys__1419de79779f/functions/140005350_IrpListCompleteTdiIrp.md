# _IrpListCompleteTdiIrp

- ea: `0x140005350`
- end: `0x14000536f`
- name: `_IrpListCompleteTdiIrp`
- size: `31`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140005c38`

## pseudocode

```c
__int64 __fastcall IrpListCompleteTdiIrp(__int64 a1, IRP *a2, unsigned int a3, int a4)
{
  RfcommCompleteTdiIrp(a2, a3, 0, a4);
  return a3;
}

```

## disassembly

```asm
0x140005350  push    rbx
0x140005352  sub     rsp, 20h
0x140005356  mov     ebx, r8d
0x140005359  mov     rcx, rdx; Irp
0x14000535c  mov     edx, ebx
0x14000535e  xor     r8d, r8d
0x140005361  call    RfcommCompleteTdiIrp
0x140005366  mov     eax, ebx
0x140005368  add     rsp, 20h
0x14000536c  pop     rbx
0x14000536d  retn
```
