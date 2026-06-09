# Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::~CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>(void)

- ea: `0x18000fb04`
- end: `0x18000fb20`
- name: `??1?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA@XZ`
- size: `28`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fd10`
- `0x18001890c`
- `0x180028c33`
- `0x180028c49`
- `0x18002979f`
- `0x1800297b5`

## callees

- `0x18000fba8`
- `0x1800101cc`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::~CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>(
        struct _Mtx_internal_imp_t *a1)
{
  Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Cancel(a1);
  return std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::~deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>((char *)a1 + 80);
}

```

## disassembly

```asm
0x18000fb04  push    rbx
0x18000fb06  sub     rsp, 20h
0x18000fb0a  mov     rbx, rcx
0x18000fb0d  call    ?Cancel@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAAXXZ; Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Cancel(void)
0x18000fb12  lea     rcx, [rbx+50h]
0x18000fb16  add     rsp, 20h
0x18000fb1a  pop     rbx
0x18000fb1b  jmp     ??1?$deque@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAA@XZ; std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::~deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>(void)
```
