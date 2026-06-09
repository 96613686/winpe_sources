# Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Pop(void)

- ea: `0x1800197e4`
- end: `0x18001988d`
- name: `?Pop@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@XZ`
- size: `169`
- prototype: `__int64 __fastcall(_Mtx_t)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180018cd0`
- `0x18001b698`
- `0x18001c230`

## callees

- `0x1800081d0`
- `0x180008c30`
- `0x18000a0e4`
- `0x18000cea4`
- `0x1800128e0`

## string_xrefs

- `0x18001982b`: `onecoreuap\termsrv\rdp_bin\win\common/inc/BufferPool.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::Pop(
        char *a1,
        __int64 a2)
{
  const char *v5; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  std::_Mutex_base::lock((std::_Mutex_base *)a1);
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x4B,
    (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common/inc/BufferPool.h",
    (const char *)0x80070490LL,
    *((_QWORD *)a1 + 14) == 0,
    (bool)"I/O buffer pool is empty",
    v5);
  wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
    a2,
    *(_QWORD *)(*(_QWORD *)(*((_QWORD *)a1 + 11) + 8 * ((*((_QWORD *)a1 + 12) - 1LL) & (*((_QWORD *)a1 + 13) >> 1)))
              + 8 * (*((_QWORD *)a1 + 13) & 1LL)));
  std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::pop_front(a1 + 80);
  Mtx_unlock((_Mtx_t)a1);
  return a2;
}

```

## disassembly

```asm
0x1800197e4  mov     rax, rsp
0x1800197e7  mov     [rax+8], rbx
0x1800197eb  mov     [rax+18h], rsi
0x1800197ef  mov     [rax+10h], rdx
0x1800197f3  push    rdi
0x1800197f4  sub     rsp, 40h
0x1800197f8  mov     rsi, rdx
0x1800197fb  mov     rdi, rcx
0x1800197fe  mov     [rax+10h], rcx
0x180019802  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x180019807  nop
0x180019808  cmp     qword ptr [rdi+70h], 0
0x18001980d  setz    al
0x180019810  mov     rcx, [rsp+48h]; this
0x180019815  lea     rdx, aIOBufferPoolIs; "I/O buffer pool is empty"
0x18001981c  mov     qword ptr [rsp+48h+var_20], rdx; bool
0x180019821  mov     [rsp+48h+var_28], al; char
0x180019825  mov     r9d, 80070490h; char *
0x18001982b  lea     r8, aOnecoreuapTerm_16; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x180019832  mov     edx, 4Bh ; 'K'; void *
0x180019837  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x18001983c  mov     r9, [rdi+68h]
0x180019840  mov     r8, r9
0x180019843  shr     r8, 1
0x180019846  mov     rax, [rdi+60h]
0x18001984a  dec     rax
0x18001984d  and     r8, rax
0x180019850  mov     rdx, [rdi+58h]
0x180019854  and     r9d, 1
0x180019858  mov     rdx, [rdx+r8*8]
0x18001985c  mov     rdx, [rdx+r9*8]
0x180019860  mov     rcx, rsi
0x180019863  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x180019868  lea     rcx, [rdi+50h]
0x18001986c  call    ?pop_front@?$deque@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::pop_front(void)
0x180019871  nop
0x180019872  mov     rcx, rdi; _Mtx_t
0x180019875  call    _Mtx_unlock
0x18001987a  mov     rax, rsi
0x18001987d  mov     rbx, [rsp+48h+arg_0]
0x180019882  mov     rsi, [rsp+48h+arg_10]
0x180019887  add     rsp, 40h
0x18001988b  pop     rdi
0x18001988c  retn
```
