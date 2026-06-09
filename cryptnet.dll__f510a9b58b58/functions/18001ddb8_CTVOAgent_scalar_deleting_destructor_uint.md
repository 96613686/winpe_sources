# CTVOAgent::`scalar deleting destructor'(uint)

- ea: `0x18001ddb8`
- end: `0x18001ddd7`
- name: `??_GCTVOAgent@@QEAAPEAXI@Z`
- size: `31`
- prototype: `struct _RTL_CRITICAL_SECTION *__fastcall(struct _RTL_CRITICAL_SECTION *hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, service_task`

## callers

- `0x1800165e0`

## callees

- `0x18000a990`
- `0x18001dd5c`

## pseudocode

```c
struct _RTL_CRITICAL_SECTION *__fastcall CTVOAgent::`scalar deleting destructor'(struct _RTL_CRITICAL_SECTION *hMem)
{
  CTVOAgent::~CTVOAgent(hMem);
  operator delete(hMem);
  return hMem;
}

```

## disassembly

```asm
0x18001ddb8  push    rbx
0x18001ddba  sub     rsp, 20h
0x18001ddbe  mov     rbx, rcx
0x18001ddc1  call    ??1CTVOAgent@@QEAA@XZ; CTVOAgent::~CTVOAgent(void)
0x18001ddc6  mov     rcx, rbx; hMem
0x18001ddc9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ddce  mov     rax, rbx
0x18001ddd1  add     rsp, 20h
0x18001ddd5  pop     rbx
0x18001ddd6  retn
```
