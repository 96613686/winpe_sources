# _utils::CThreadPool::ThreadEntry_::_1_::dtor$0

- ea: `0x180010a6a`
- end: `0x180010a76`
- name: `_utils::CThreadPool::ThreadEntry_::_1_::dtor$0`
- size: `12`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18000f1e0`

## pseudocode

```c
void __fastcall utils::CThreadPool::ThreadEntry_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  std::unique_ptr<utils::CThreadPool::WorkItemWrapper>::~unique_ptr<utils::CThreadPool::WorkItemWrapper>((utils::CThreadPool::WorkItemWrapper **)(a2 + 48));
}

```

## disassembly

```asm
0x180010a6a  lea     rcx, [rdx+30h]
0x180010a71  jmp     ??1?$unique_ptr@VWorkItemWrapper@CThreadPool@utils@@U?$default_delete@VWorkItemWrapper@CThreadPool@utils@@@std@@@std@@QEAA@XZ; std::unique_ptr<utils::CThreadPool::WorkItemWrapper>::~unique_ptr<utils::CThreadPool::WorkItemWrapper>(void)
```
