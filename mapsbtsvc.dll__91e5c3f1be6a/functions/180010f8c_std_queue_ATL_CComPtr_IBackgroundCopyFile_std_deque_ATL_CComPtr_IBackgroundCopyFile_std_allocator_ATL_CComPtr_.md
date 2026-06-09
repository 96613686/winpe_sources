# std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>::front(void)

- ea: `0x180010f8c`
- end: `0x180010f91`
- name: `?front@?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@std@@QEAAAEAV?$CComPtr@UIBackgroundCopyFile@@@ATL@@XZ`
- size: `5`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c4dc`

## callees

- `0x180010f54`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall std::queue<ATL::CComPtr<IBackgroundCopyFile>>::front(_QWORD *a1)
{
  return std::deque<ATL::CComPtr<IBackgroundCopyFile>>::front(a1);
}

```

## disassembly

```asm
0x180010f8c  jmp     ?front@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@QEAAAEAV?$CComPtr@UIBackgroundCopyFile@@@ATL@@XZ; std::deque<ATL::CComPtr<IBackgroundCopyFile>>::front(void)
```
