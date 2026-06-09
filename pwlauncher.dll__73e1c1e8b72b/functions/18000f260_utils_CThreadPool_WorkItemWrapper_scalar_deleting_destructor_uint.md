# utils::CThreadPool::WorkItemWrapper::`scalar deleting destructor'(uint)

- ea: `0x18000f260`
- end: `0x18000f280`
- name: `??_GWorkItemWrapper@CThreadPool@utils@@QEAAPEAXI@Z`
- size: `32`
- prototype: `utils::CThreadPool::WorkItemWrapper *__fastcall(utils::CThreadPool::WorkItemWrapper *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x18000f288`

## callees

- `0x18000f20c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f271`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f271`

## pseudocode

```c
utils::CThreadPool::WorkItemWrapper *__fastcall utils::CThreadPool::WorkItemWrapper::`scalar deleting destructor'(
        utils::CThreadPool::WorkItemWrapper *this)
{
  utils::CThreadPool::WorkItemWrapper::~WorkItemWrapper(this);
  operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000f260  push    rbx
0x18000f262  sub     rsp, 20h
0x18000f266  mov     rbx, rcx
0x18000f269  call    ??1WorkItemWrapper@CThreadPool@utils@@QEAA@XZ; utils::CThreadPool::WorkItemWrapper::~WorkItemWrapper(void)
0x18000f26e  mov     rcx, rbx
0x18000f271  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f277  mov     rax, rbx
0x18000f27a  add     rsp, 20h
0x18000f27e  pop     rbx
0x18000f27f  retn
```
