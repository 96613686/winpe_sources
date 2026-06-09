# FreeCmapFormat4

- ea: `0x18000dda0`
- end: `0x18000ddbb`
- name: `FreeCmapFormat4`
- size: `27`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a8dc`
- `0x18000e4c8`
- `0x18000ec50`
- `0x1800143f0`

## callees

- `0x180011574`

## pseudocode

```c
void __fastcall FreeCmapFormat4(void *a1, void *a2)
{
  Mem_Free(a1);
  Mem_Free(a2);
}

```

## disassembly

```asm
0x18000dda0  push    rbx
0x18000dda2  sub     rsp, 20h
0x18000dda6  mov     rbx, rdx
0x18000dda9  call    Mem_Free
0x18000ddae  mov     rcx, rbx
0x18000ddb1  add     rsp, 20h
0x18000ddb5  pop     rbx
0x18000ddb6  jmp     Mem_Free
```
