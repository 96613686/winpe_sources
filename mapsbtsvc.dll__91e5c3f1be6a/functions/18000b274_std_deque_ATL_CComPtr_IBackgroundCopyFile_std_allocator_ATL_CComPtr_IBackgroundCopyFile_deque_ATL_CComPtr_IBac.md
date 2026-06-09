# std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::~deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>(void)

- ea: `0x18000b274`
- end: `0x18000b29b`
- name: `??1?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@QEAA@XZ`
- size: `39`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000b370`

## callees

- `0x180003c34`
- `0x1800108e8`

## pseudocode

```c
void __fastcall std::deque<ATL::CComPtr<IBackgroundCopyFile>>::~deque<ATL::CComPtr<IBackgroundCopyFile>>(void **a1)
{
  void *v2; // rcx

  std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Tidy();
  v2 = *a1;
  *a1 = 0;
  std::_Deallocate<16>(v2, 0x10u);
}

```

## disassembly

```asm
0x18000b274  push    rbx
0x18000b276  sub     rsp, 20h
0x18000b27a  mov     rbx, rcx
0x18000b27d  call    ?_Tidy@?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@AEAAXXZ; std::deque<ATL::CComPtr<IBackgroundCopyFile>>::_Tidy(void)
0x18000b282  mov     rcx, [rbx]
0x18000b285  mov     edx, 10h
0x18000b28a  mov     qword ptr [rbx], 0
0x18000b291  add     rsp, 20h
0x18000b295  pop     rbx
0x18000b296  jmp     ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
```
