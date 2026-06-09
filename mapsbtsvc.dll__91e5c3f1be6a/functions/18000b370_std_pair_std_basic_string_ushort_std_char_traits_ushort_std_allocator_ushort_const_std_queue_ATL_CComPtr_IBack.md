# std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>::~pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::queue<ATL::CComPtr<IBackgroundCopyFile>,std::deque<ATL::CComPtr<IBackgroundCopyFile>,std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>>>(void)

- ea: `0x18000b370`
- end: `0x18000b38f`
- name: `??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$queue@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@@2@@std@@QEAA@XZ`
- size: `31`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000a0b8`
- `0x18000b1e4`

## callees

- `0x18000b274`
- `0x180010954`

## pseudocode

```c
__int64 __fastcall std::pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>::~pair<std::wstring const,std::queue<ATL::CComPtr<IBackgroundCopyFile>>>(
        __int64 a1)
{
  std::deque<ATL::CComPtr<IBackgroundCopyFile>>::~deque<ATL::CComPtr<IBackgroundCopyFile>>((void **)(a1 + 32));
  return std::wstring::_Tidy_deallocate(a1);
}

```

## disassembly

```asm
0x18000b370  push    rbx
0x18000b372  sub     rsp, 20h
0x18000b376  mov     rbx, rcx
0x18000b379  add     rcx, 20h ; ' '
0x18000b37d  call    ??1?$deque@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@QEAA@XZ; std::deque<ATL::CComPtr<IBackgroundCopyFile>>::~deque<ATL::CComPtr<IBackgroundCopyFile>>(void)
0x18000b382  mov     rcx, rbx
0x18000b385  add     rsp, 20h
0x18000b389  pop     rbx
0x18000b38a  jmp     ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
