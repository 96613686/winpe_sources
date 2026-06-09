# CWorkerThread::`scalar deleting destructor'(uint)

- ea: `0x18000ef8c`
- end: `0x18000efac`
- name: `??_GCWorkerThread@@QEAAPEAXI@Z`
- size: `32`
- prototype: `CWorkerThread *__fastcall(CWorkerThread *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000eee0`
- `0x18001204f`

## callees

- `0x180010848`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ef9d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ef9d`

## pseudocode

```c
CWorkerThread *__fastcall CWorkerThread::`scalar deleting destructor'(CWorkerThread *this)
{
  CWorkerThread::~CWorkerThread(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000ef8c  push    rbx
0x18000ef8e  sub     rsp, 20h
0x18000ef92  mov     rbx, rcx
0x18000ef95  call    ??1CWorkerThread@@QEAA@XZ; CWorkerThread::~CWorkerThread(void)
0x18000ef9a  mov     rcx, rbx
0x18000ef9d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000efa3  mov     rax, rbx
0x18000efa6  add     rsp, 20h
0x18000efaa  pop     rbx
0x18000efab  retn
```
