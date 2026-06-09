# std::unique_ptr<utils::CThreadPool::WorkItemWrapper,std::default_delete<utils::CThreadPool::WorkItemWrapper>>::~unique_ptr<utils::CThreadPool::WorkItemWrapper,std::default_delete<utils::CThreadPool::WorkItemWrapper>>(void)

- ea: `0x18000f1e0`
- end: `0x18000f205`
- name: `??1?$unique_ptr@VWorkItemWrapper@CThreadPool@utils@@U?$default_delete@VWorkItemWrapper@CThreadPool@utils@@@std@@@std@@QEAA@XZ`
- size: `37`
- prototype: `void __fastcall(utils::CThreadPool::WorkItemWrapper **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180010a6a`

## callees

- `0x18000f1e0`
- `0x18000f20c`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000f1f9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000f1f9`

## pseudocode

```c
void __fastcall std::unique_ptr<utils::CThreadPool::WorkItemWrapper>::~unique_ptr<utils::CThreadPool::WorkItemWrapper>(
        utils::CThreadPool::WorkItemWrapper **a1)
{
  utils::CThreadPool::WorkItemWrapper *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    utils::CThreadPool::WorkItemWrapper::~WorkItemWrapper(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x18000f1e0  push    rbx
0x18000f1e2  sub     rsp, 20h
0x18000f1e6  mov     rbx, [rcx]
0x18000f1e9  test    rbx, rbx
0x18000f1ec  jz      short loc_18000F1FF
0x18000f1ee  mov     rcx, rbx; this
0x18000f1f1  call    ??1WorkItemWrapper@CThreadPool@utils@@QEAA@XZ; utils::CThreadPool::WorkItemWrapper::~WorkItemWrapper(void)
0x18000f1f6  mov     rcx, rbx
0x18000f1f9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000f1ff  add     rsp, 20h
0x18000f203  pop     rbx
0x18000f204  retn
```
