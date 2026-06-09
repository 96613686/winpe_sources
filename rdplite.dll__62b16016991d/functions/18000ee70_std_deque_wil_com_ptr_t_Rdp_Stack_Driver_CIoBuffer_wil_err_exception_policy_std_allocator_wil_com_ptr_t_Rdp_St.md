# std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>,std::allocator<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>>::_Emplace_back_internal<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &>(wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &)

- ea: `0x18000ee70`
- end: `0x18000ef15`
- name: `??$_Emplace_back_internal@AEBV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@?$deque@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAXAEBV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Z`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011a1c`

## callees

- `0x180004958`
- `0x18000a0e4`
- `0x18000ee70`
- `0x18001233c`

## pseudocode

```c
_QWORD *__fastcall std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::_Emplace_back_internal<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy> const &>(
        __int64 a1,
        __int64 *a2)
{
  __int64 v4; // rcx
  __int64 v5; // rdx
  unsigned __int64 v6; // rdi
  __int64 v7; // rsi
  _QWORD *result; // rax

  v4 = *(_QWORD *)(a1 + 32);
  if ( ((*(_BYTE *)(a1 + 24) + (_BYTE)v4) & 1) == 0 && *(_QWORD *)(a1 + 16) <= (unsigned __int64)(v4 + 2) >> 1 )
    std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::_Growmap((_QWORD *)a1);
  v5 = *(_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 24) &= 2 * v5 - 1;
  v6 = *(_QWORD *)(a1 + 32) + *(_QWORD *)(a1 + 24);
  v7 = (v6 >> 1) & (v5 - 1);
  if ( !*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v7) )
    *(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * v7) = std::_Allocate<16,std::_Default_allocate_traits>(16);
  result = wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
             (_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 8) + 8 * ((v6 >> 1) & (*(_QWORD *)(a1 + 16) - 1LL))) + 8 * (v6 & 1)),
             *a2);
  ++*(_QWORD *)(a1 + 32);
  return result;
}

```

## disassembly

```asm
0x18000ee70  push    rbx
0x18000ee72  push    rbp
0x18000ee73  push    rsi
0x18000ee74  push    rdi
0x18000ee75  push    r14
0x18000ee77  sub     rsp, 20h
0x18000ee7b  mov     rbx, rcx
0x18000ee7e  mov     r14, rdx
0x18000ee81  mov     rcx, [rcx+20h]
0x18000ee85  mov     al, cl
0x18000ee87  add     al, [rbx+18h]
0x18000ee8a  test    al, 1
0x18000ee8c  jnz     short loc_18000EEA3
0x18000ee8e  lea     rax, [rcx+2]
0x18000ee92  shr     rax, 1
0x18000ee95  cmp     [rbx+10h], rax
0x18000ee99  ja      short loc_18000EEA3
0x18000ee9b  mov     rcx, rbx
0x18000ee9e  call    ?_Growmap@?$deque@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@AEAAX_K@Z; std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::_Growmap(unsigned __int64)
0x18000eea3  mov     rdx, [rbx+10h]
0x18000eea7  lea     rax, ds:0FFFFFFFFFFFFFFFFh[rdx*2]
0x18000eeaf  and     [rbx+18h], rax
0x18000eeb3  lea     rsi, [rdx-1]
0x18000eeb7  mov     rdi, [rbx+18h]
0x18000eebb  add     rdi, [rbx+20h]
0x18000eebf  mov     rax, [rbx+8]
0x18000eec3  mov     rbp, rdi
0x18000eec6  shr     rbp, 1
0x18000eec9  and     rsi, rbp
0x18000eecc  cmp     qword ptr [rax+rsi*8], 0
0x18000eed1  jnz     short loc_18000EEE5
0x18000eed3  mov     ecx, 10h
0x18000eed8  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18000eedd  mov     rcx, [rbx+8]
0x18000eee1  mov     [rcx+rsi*8], rax
0x18000eee5  mov     rcx, [rbx+10h]
0x18000eee9  and     edi, 1
0x18000eeec  mov     rax, [rbx+8]
0x18000eef0  dec     rcx
0x18000eef3  mov     rdx, [r14]
0x18000eef6  and     rcx, rbp
0x18000eef9  mov     rax, [rax+rcx*8]
0x18000eefd  lea     rcx, [rax+rdi*8]
0x18000ef01  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x18000ef06  inc     qword ptr [rbx+20h]
0x18000ef0a  add     rsp, 20h
0x18000ef0e  pop     r14
0x18000ef10  pop     rdi
0x18000ef11  pop     rsi
0x18000ef12  pop     rbp
0x18000ef13  pop     rbx
0x18000ef14  retn
```
