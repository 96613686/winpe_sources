# DoubleList::~DoubleList(void)

- ea: `0x140002b90`
- end: `0x140002bb3`
- name: `??1DoubleList@@UEAA@XZ`
- size: `35`
- prototype: `void __fastcall(DoubleList *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003970`
- `0x140011a7c`
- `0x14001bcb0`
- `0x14001d904`
- `0x14001fb94`

## callees

- `0x140002bbc`

## pseudocode

```c
void __fastcall DoubleList::~DoubleList(DoubleList *this)
{
  KernelResource::~KernelResource((DoubleList *)((char *)this + 32));
  *(_QWORD *)this = &TopObj::`vftable';
}

```

## disassembly

```asm
0x140002b90  push    rbx
0x140002b92  sub     rsp, 20h
0x140002b96  mov     rbx, rcx
0x140002b99  add     rcx, 20h ; ' '; this
0x140002b9d  call    ??1KernelResource@@UEAA@XZ; KernelResource::~KernelResource(void)
0x140002ba2  lea     rax, ??_7TopObj@@6B@; const TopObj::`vftable'
0x140002ba9  mov     [rbx], rax
0x140002bac  add     rsp, 20h
0x140002bb0  pop     rbx
0x140002bb1  retn
```
