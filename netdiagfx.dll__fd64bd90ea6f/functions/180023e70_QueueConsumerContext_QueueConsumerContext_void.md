# QueueConsumerContext::~QueueConsumerContext(void)

- ea: `0x180023e70`
- end: `0x180023e91`
- name: `??1QueueConsumerContext@@QEAA@XZ`
- size: `33`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023edc`

## callees

- `0x180017d34`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x180023e8a`

## pseudocode

```c
void __fastcall QueueConsumerContext::~QueueConsumerContext(struct _RTL_CRITICAL_SECTION *this)
{
  std::deque<int>::~deque<int>(&this[1].LockCount);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180023e70  push    rbx
0x180023e72  sub     rsp, 20h
0x180023e76  mov     rbx, rcx
0x180023e79  add     rcx, 30h ; '0'
0x180023e7d  call    ??1?$deque@HV?$allocator@H@std@@@std@@QEAA@XZ; std::deque<int>::~deque<int>(void)
0x180023e82  mov     rcx, rbx
0x180023e85  add     rsp, 20h
0x180023e89  pop     rbx
0x180023e8a  jmp     cs:__imp_DeleteCriticalSection
```
