# Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>)

- ea: `0x180011a1c`
- end: `0x180011a74`
- name: `?Push@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA_NV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(_Mtx_t)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f39c`
- `0x180010a30`
- `0x180010bc0`
- `0x180010cbc`
- `0x180011048`
- `0x180011490`
- `0x180018570`
- `0x18001b698`

## callees

- `0x180007b28`
- `0x1800081d0`
- `0x180008c30`
- `0x18000ee70`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180011a58`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180011a58`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Push(
        RTL_CONDITION_VARIABLE *a1,
        __int64 *a2)
{
  std::_Mutex_base::lock((std::_Mutex_base *)a1);
  std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::_Emplace_back_internal<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &>(
    &a1[10],
    a2);
  Mtx_unlock((_Mtx_t)a1);
  WakeConditionVariable(a1 + 16);
  wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(a2);
  return 1;
}

```

## disassembly

```asm
0x180011a1c  mov     [rsp+arg_10], rbx
0x180011a21  mov     [rsp+arg_8], rdx
0x180011a26  push    rdi
0x180011a27  sub     rsp, 20h
0x180011a2b  mov     rdi, rdx
0x180011a2e  mov     rbx, rcx
0x180011a31  mov     [rsp+28h+arg_0], rcx
0x180011a36  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180011a3b  nop
0x180011a3c  lea     rcx, [rbx+50h]
0x180011a40  mov     rdx, rdi
0x180011a43  call    ??$_Emplace_back_internal@AEBV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$deque@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXAEBV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z; std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::_Emplace_back_internal<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &>(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &)
0x180011a48  nop
0x180011a49  mov     rcx, rbx; _Mtx_t
0x180011a4c  call    _Mtx_unlock
0x180011a51  lea     rcx, [rbx+80h]; ConditionVariable
0x180011a58  call    cs:__imp_WakeConditionVariable
0x180011a5e  nop
0x180011a5f  mov     rcx, rdi
0x180011a62  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x180011a67  mov     al, 1
0x180011a69  mov     rbx, [rsp+28h+arg_10]
0x180011a6e  add     rsp, 20h
0x180011a72  pop     rdi
0x180011a73  retn
```
