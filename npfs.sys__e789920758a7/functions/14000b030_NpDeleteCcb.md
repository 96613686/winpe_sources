# NpDeleteCcb

- ea: `0x14000b030`
- end: `0x14000b04d`
- name: `NpDeleteCcb`
- size: `29`
- prototype: `void __fastcall(int, _QWORD **, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x140010ef4`
- `0x14001399c`

## callees

- `0x14000e774`
- `0x14001070c`

## pseudocode

```c
void __fastcall NpDeleteCcb(int a1, _QWORD **a2, int a3)
{
  NpUnlinkCcb(a1, (__int64)a2, a3);
  NpFreeCcb(a2);
}

```

## disassembly

```asm
0x14000b030  push    rbx
0x14000b032  sub     rsp, 20h
0x14000b036  mov     rbx, rdx
0x14000b039  call    NpUnlinkCcb
0x14000b03e  mov     rcx, rbx; P
0x14000b041  call    NpFreeCcb
0x14000b046  add     rsp, 20h
0x14000b04a  pop     rbx
0x14000b04b  retn
```
