# std::_Default_allocator_traits<std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::construct<ATL::CComPtr<IBackgroundCopyFile>,ATL::CComPtr<IBackgroundCopyFile>>(std::allocator<ATL::CComPtr<IBackgroundCopyFile>> &,ATL::CComPtr<IBackgroundCopyFile> * const,ATL::CComPtr<IBackgroundCopyFile> &&)

- ea: `0x18000a990`
- end: `0x18000a9b1`
- name: `??$construct@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@V12@@?$_Default_allocator_traits@V?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@std@@@std@@SAXAEAV?$allocator@V?$CComPtr@UIBackgroundCopyFile@@@ATL@@@1@QEAV?$CComPtr@UIBackgroundCopyFile@@@ATL@@$$QEAV34@@Z`
- size: `33`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180009b98`

## callees

- `0x18000a990`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall std::_Default_allocator_traits<std::allocator<ATL::CComPtr<IBackgroundCopyFile>>>::construct<ATL::CComPtr<IBackgroundCopyFile>,ATL::CComPtr<IBackgroundCopyFile>>(
        __int64 a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 v3; // rcx
  __int64 result; // rax

  v3 = *a3;
  *a2 = *a3;
  if ( v3 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  return result;
}

```

## disassembly

```asm
0x18000a990  sub     rsp, 28h
0x18000a994  mov     rcx, [r8]
0x18000a997  mov     [rdx], rcx
0x18000a99a  test    rcx, rcx
0x18000a99d  jz      short loc_18000A9AC
0x18000a99f  mov     rax, [rcx]
0x18000a9a2  mov     rax, [rax+8]
0x18000a9a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ab  nop
0x18000a9ac  add     rsp, 28h
0x18000a9b0  retn
```
