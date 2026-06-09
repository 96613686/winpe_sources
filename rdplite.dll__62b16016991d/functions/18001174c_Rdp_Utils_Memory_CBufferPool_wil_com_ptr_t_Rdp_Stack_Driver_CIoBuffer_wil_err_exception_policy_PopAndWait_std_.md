# Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::nothrow_t const &)

- ea: `0x18001174c`
- end: `0x18001180e`
- name: `?PopAndWait@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@std@@AEBUnothrow_t@9@@Z`
- size: `194`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800106e4`
- `0x180011048`
- `0x180011b5c`

## callees

- `0x180007b28`
- `0x18000a0e4`
- `0x18000f0a4`
- `0x18000f30c`
- `0x18000fc30`
- `0x18001174c`
- `0x1800128e0`

## pseudocode

```c
__int64 *Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        ...)
{
  __int64 v6; // rax
  _BYTE v8[24]; // [rsp+20h] [rbp-18h] BYREF
  __int64 v9; // [rsp+58h] [rbp+20h] BYREF
  va_list va; // [rsp+58h] [rbp+20h]
  va_list va1; // [rsp+60h] [rbp+28h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v9 = va_arg(va1, _QWORD);
  std::unique_lock<std::mutex>::unique_lock<std::mutex>(v8, a1);
  if ( !(unsigned __int8)___wait_for__JU__ratio__00_0DOI__std__V_lambda_1___0__PopAndWait___CBufferPool_V__com_ptr_t_UCIoBuffer_Driver_Stack_Rdp__Uerr_exception_policy_wil___wil___Memory_Utils_Rdp__QEAA_AV__com_ptr_t_UCIoBuffer_Driver_Stack_Rdp__Uerr_exception_policy_wil___wil__AEBV__duration__JU__ratio__00_0DOI__std___chrono_2_AEBUnothrow_t_2__Z__condition_variable_std__QEAA_NAEAV__unique_lock_Vmutex_std___1_AEBV__duration__JU__ratio__00_0DOI__std___chrono_1_V_lambda_1___0__PopAndWait___CBufferPool_V__com_ptr_t_UCIoBuffer_Driver_Stack_Rdp__Uerr_exception_policy_wil___wil___Memory_Utils_Rdp__QEAA_AV__com_ptr_t_UCIoBuffer_Driver_Stack_Rdp__Uerr_exception_policy_wil___wil__1AEBUnothrow_t_1__Z__Z(
                           a1 + 120,
                           v8,
                           a3,
                           a1)
    || *(_BYTE *)(a1 + 192) )
  {
    *a2 = 0;
  }
  else
  {
    wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(
      (__int64 *)va,
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 88) + 8 * ((*(_QWORD *)(a1 + 96) - 1LL) & (*(_QWORD *)(a1 + 104) >> 1)))
                + 8 * (*(_QWORD *)(a1 + 104) & 1LL)));
    std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::pop_front(a1 + 80);
    v6 = v9;
    v9 = 0;
    *a2 = v6;
    wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>((__int64 *)va);
  }
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v8);
  return a2;
}

```

## disassembly

```asm
0x18001174c  mov     rax, rsp
0x18001174f  mov     [rax+8], rbx
0x180011753  mov     [rax+10h], rsi
0x180011757  mov     [rax+20h], r9
0x18001175b  push    rdi
0x18001175c  sub     rsp, 30h
0x180011760  mov     rbx, r8
0x180011763  mov     rdi, rdx
0x180011766  mov     rsi, rcx
0x180011769  mov     rdx, rcx
0x18001176c  lea     rcx, [rax-18h]
0x180011770  call    ??0?$unique_lock@Vmutex@std@@@std@@QEAA@AEAVmutex@1@@Z; std::unique_lock<std::mutex>::unique_lock<std::mutex>(std::mutex &)
0x180011775  lea     rcx, [rsi+78h]
0x180011779  mov     r9, rsi
0x18001177c  mov     r8, rbx
0x18001177f  lea     rdx, [rsp+38h+var_18]
0x180011784  call    ??$wait_for@_JU?$ratio@$00$0DOI@@std@@V_lambda_1_@?0??PopAndWait@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@2@AEBUnothrow_t@2@@Z@@condition_variable@std@@QEAA_NAEAV?$unique_lock@Vmutex@std@@@1@AEBV?$duration@_JU?$ratio@$00$0DOI@@std@@@chrono@1@V_lambda_1_@?0??PopAndWait@?$CBufferPool@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@Memory@Utils@Rdp@@QEAA?AV?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@1AEBUnothrow_t@1@@Z@@Z; std::condition_variable::wait_for<__int64,std::ratio<1,1000>,`Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::nothrow_t const &)'::`1'::_lambda_1_>(std::unique_lock<std::mutex> &,std::chrono::duration<__int64,std::ratio<1,1000>> const &,`Rdp::Utils::Memory::CBufferPool<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::PopAndWait(std::chrono::duration<__int64,std::ratio<1,1000>> const &,std::nothrow_t const &)'::`1'::_lambda_1_)
0x180011789  test    al, al
0x18001178b  jz      short loc_1800117EA
0x18001178d  cmp     byte ptr [rsi+0C0h], 0
0x180011794  jnz     short loc_1800117EA
0x180011796  mov     r9, [rsi+68h]
0x18001179a  mov     r8, r9
0x18001179d  shr     r8, 1
0x1800117a0  mov     rax, [rsi+60h]
0x1800117a4  dec     rax
0x1800117a7  and     r8, rax
0x1800117aa  mov     rdx, [rsi+58h]
0x1800117ae  and     r9d, 1
0x1800117b2  mov     rdx, [rdx+r8*8]
0x1800117b6  mov     rdx, [rdx+r9*8]
0x1800117ba  lea     rcx, [rsp+38h+arg_18]
0x1800117bf  call    ??0?$com_ptr_t@VCMonitorShim@Shim@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAVCMonitorShim@Shim@Stack@Rdp@@@Z; wil::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>::com_ptr_t<Rdp::Stack::Shim::CMonitorShim,wil::err_exception_policy>(Rdp::Stack::Shim::CMonitorShim *)
0x1800117c4  lea     rcx, [rsi+50h]
0x1800117c8  call    ?pop_front@?$deque@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@V?$allocator@V?$com_ptr_t@UCIoBuffer@Driver@Stack@Rdp@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@QEAAXXZ; std::deque<wil::com_ptr_t<Rdp::Stack::Driver::CIoBuffer,wil::err_exception_policy>>::pop_front(void)
0x1800117cd  mov     rax, [rsp+38h+arg_18]
0x1800117d2  mov     [rsp+38h+arg_18], 0
0x1800117db  mov     [rdi], rax
0x1800117de  lea     rcx, [rsp+38h+arg_18]
0x1800117e3  call    ??1?$com_ptr_t@UIDXGIResource@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IDXGIResource,wil::err_exception_policy>::~com_ptr_t<IDXGIResource,wil::err_exception_policy>(void)
0x1800117e8  jmp     short loc_1800117F1
0x1800117ea  mov     qword ptr [rdi], 0
0x1800117f1  lea     rcx, [rsp+38h+var_18]
0x1800117f6  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x1800117fb  mov     rax, rdi
0x1800117fe  mov     rbx, [rsp+38h+arg_0]
0x180011803  mov     rsi, [rsp+38h+arg_8]
0x180011808  add     rsp, 30h
0x18001180c  pop     rdi
0x18001180d  retn
```
