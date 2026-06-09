# CdFsdPostRequest

- ea: `0x14001a8c4`
- end: `0x14001a8f5`
- name: `CdFsdPostRequest`
- size: `49`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140001474`
- `0x1400028e0`
- `0x14001aa78`

## callees

- `0x140002b10`
- `0x14001a9a0`

## pseudocode

```c
__int64 __fastcall CdFsdPostRequest(void *a1, IRP *a2)
{
  CdPrePostIrp(a1, a2);
  CdAddToWorkque((__int64)a1, (__int64)a2);
  return 259;
}

```

## disassembly

```asm
0x14001a8c4  mov     [rsp+arg_0], rbx
0x14001a8c9  push    rdi
0x14001a8ca  sub     rsp, 20h
0x14001a8ce  mov     rbx, rdx
0x14001a8d1  mov     rdi, rcx
0x14001a8d4  call    CdPrePostIrp
0x14001a8d9  mov     rdx, rbx
0x14001a8dc  mov     rcx, rdi
0x14001a8df  call    CdAddToWorkque
0x14001a8e4  mov     rbx, [rsp+28h+arg_0]
0x14001a8e9  mov     eax, 103h
0x14001a8ee  add     rsp, 20h
0x14001a8f2  pop     rdi
0x14001a8f3  retn
```
