# CXactRingBuffer::~CXactRingBuffer(void)

- ea: `0x1800189b0`
- end: `0x1800189e6`
- name: `??1CXactRingBuffer@@QEAA@XZ`
- size: `54`
- prototype: `void __fastcall(CXactRingBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800256a0`

## callees

- `0x180001fac`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x1800189c0`
- `KERNEL32!DeleteCriticalSection` at `0x1800189c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CXactRingBuffer::~CXactRingBuffer(CXactRingBuffer *this)
{
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 392));
  `eh vector destructor iterator'(this, 0x18u, 0x10u, (void (*)(void *))CXactDigest::~CXactDigest);
}

```

## disassembly

```asm
0x1800189b0  push    rbx
0x1800189b2  sub     rsp, 20h
0x1800189b6  mov     rbx, rcx
0x1800189b9  add     rcx, 188h; lpCriticalSection
0x1800189c0  call    cs:__imp_DeleteCriticalSection
0x1800189c6  nop
0x1800189c7  lea     r9, ??1CXactDigest@@QEAA@XZ; void (*)(void *)
0x1800189ce  mov     edx, 18h; unsigned __int64
0x1800189d3  lea     r8d, [rdx-8]; unsigned __int64
0x1800189d7  mov     rcx, rbx; void *
0x1800189da  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800189df  nop
0x1800189e0  add     rsp, 20h
0x1800189e4  pop     rbx
0x1800189e5  retn
```
