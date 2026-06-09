# FwIcfAuthBypassServiceDestroy

- ea: `0x180007140`
- end: `0x18000716d`
- name: `FwIcfAuthBypassServiceDestroy`
- size: `45`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task`

## callees

- `0x180004840`
- `0x180006a50`
- `0x18001eb54`

## pseudocode

```c
void *__fastcall FwIcfAuthBypassServiceDestroy(char *a1)
{
  FwFree(*(_QWORD *)a1);
  FwIcfAuthBypassSubNetsDestroy(a1 + 24);
  return memset_0(a1, 0, 0x40u);
}

```

## disassembly

```asm
0x180007140  push    rbx
0x180007142  sub     rsp, 20h
0x180007146  mov     rbx, rcx
0x180007149  mov     rcx, [rcx]
0x18000714c  call    FwFree
0x180007151  lea     rcx, [rbx+18h]
0x180007155  call    FwIcfAuthBypassSubNetsDestroy
0x18000715a  xor     edx, edx; Val
0x18000715c  mov     rcx, rbx; void *
0x18000715f  lea     r8d, [rdx+40h]; Size
0x180007163  add     rsp, 20h
0x180007167  pop     rbx
0x180007168  jmp     memset_0
```
