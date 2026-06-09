# wil::details::EnabledStateManager::ProcessShutdown(void)

- ea: `0x14001bf5c`
- end: `0x14001c1bb`
- name: `?ProcessShutdown@EnabledStateManager@details@wil@@QEAAXXZ`
- size: `607`
- prototype: `void __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140015b98`
- `0x14002f2a0`

## callees

- `0x1400020b0`
- `0x14001bf5c`
- `0x14001efa8`
- `0x1400204b8`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c139`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x14001c139`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001bfa2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001bfa2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001c166`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001c166`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001c178`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001c178`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001c187`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001c187`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::EnabledStateManager::ProcessShutdown(wil::details::EnabledStateManager *this)
{
  RTL_SRWLOCK *v2; // rbp
  int *v3; // rbx
  int *v4; // rdi
  __int64 v5; // r8
  int v6; // r10d
  unsigned __int32 v7; // ecx
  unsigned __int32 v8; // eax
  char *v9; // rdx
  unsigned __int64 v10; // r8
  __int64 v11; // rdx
  void (__fastcall *v12)(_QWORD, __int64, _QWORD, _QWORD); // rax
  struct _TP_TIMER *v13; // rbx
  PTP_TIMER pti; // [rsp+30h] [rbp-68h] BYREF
  _DWORD v15[2]; // [rsp+38h] [rbp-60h] BYREF
  char v16; // [rsp+40h] [rbp-58h] BYREF

  *(_DWORD *)this = 0;
  pti = (PTP_TIMER)*((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = 0;
  v2 = (RTL_SRWLOCK *)((char *)this + 8);
  AcquireSRWLockExclusive((PSRWLOCK)this + 1);
  v3 = (int *)*((_QWORD *)this + 4);
  v4 = (int *)*((_QWORD *)this + 5);
  if ( (unsigned __int64)((char *)v4 - (char *)v3) >= 0x10 )
  {
    while ( v3 != v4 )
    {
      v5 = *((_QWORD *)v3 + 1);
      v6 = *v3;
      _m_prefetchw((const void *)v5);
      v7 = _InterlockedAnd((volatile signed __int32 *)v5, 0xFFC0401E);
      if ( ((v7 >> 1) & 0xF) != 0 )
      {
        _m_prefetchw((const void *)(v5 + 4));
        v8 = (v7 >> 1) & 0xF & ~_InterlockedOr((volatile signed __int32 *)(v5 + 4), (v7 >> 1) & 0xF);
      }
      else
      {
        v8 = 0;
      }
      if ( (v8 & 1) != 0 )
      {
        v15[0] = v6;
        v15[1] = 65538;
        v9 = &v16;
      }
      else
      {
        v9 = (char *)v15;
      }
      if ( (v8 & 2) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65542;
        v9 += 8;
      }
      if ( (v8 & 4) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65539;
        v9 += 8;
      }
      if ( v8 >= 8 )
      {
        *(_DWORD *)v9 = v6;
        *((_DWORD *)v9 + 1) = 65543;
        v9 += 8;
      }
      v10 = v7 >> 5;
      if ( (v10 & 0x1FF) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 14) & 1);
        LOWORD(v10) = v10 & 0x1FF;
        *((_WORD *)v9 + 3) = v10;
        v9 += 8;
      }
      if ( ((v7 >> 15) & 0x7F) != 0 )
      {
        *(_DWORD *)v9 = v6;
        *((_WORD *)v9 + 2) = 4 * ((v7 >> 22) & 1) + 1;
        *((_WORD *)v9 + 3) = (v7 >> 15) & 0x7F;
        v9 += 8;
      }
      v11 = (v9 - (char *)v15) >> 3;
      if ( v11 > 0 )
        wil::details::WilApi_RecordFeatureUsageReports(
          (wil::details *)v15,
          (struct __WIL_RTL_FEATURE_USAGE_DATA *)v11,
          v10);
      v3 += 4;
    }
    *((_QWORD *)this + 5) = *((_QWORD *)this + 4);
    v12 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_internalRecordFeatureUsage;
    if ( g_wil_details_internalRecordFeatureUsage
      || (v12 = (void (__fastcall *)(_QWORD, __int64, _QWORD, _QWORD))g_wil_details_apiRecordFeatureUsage) != 0 )
    {
      v12(0, 254, 0, 0);
    }
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
    &pti,
    0);
  v13 = pti;
  if ( pti )
  {
    SetThreadpoolTimer(pti, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v13, 1);
    CloseThreadpoolTimer(v13);
  }
}

```

## disassembly

```asm
0x14001bf5c  mov     [rsp+arg_8], rbx
0x14001bf61  mov     [rsp+arg_10], rbp
0x14001bf66  push    rsi
0x14001bf67  push    rdi
0x14001bf68  push    r12
0x14001bf6a  push    r14
0x14001bf6c  push    r15
0x14001bf6e  sub     rsp, 70h
0x14001bf72  mov     rax, cs:__security_cookie
0x14001bf79  xor     rax, rsp
0x14001bf7c  mov     [rsp+98h+var_30], rax
0x14001bf81  mov     rsi, rcx
0x14001bf84  mov     dword ptr [rcx], 0
0x14001bf8a  mov     rax, [rcx+10h]
0x14001bf8e  mov     [rsp+98h+pti], rax
0x14001bf93  mov     qword ptr [rcx+10h], 0
0x14001bf9b  lea     rbp, [rcx+8]
0x14001bf9f  mov     rcx, rbp; SRWLock
0x14001bfa2  call    cs:__imp_AcquireSRWLockExclusive
0x14001bfa9  nop     dword ptr [rax+rax+00h]
0x14001bfae  nop
0x14001bfaf  mov     rbx, [rsi+20h]
0x14001bfb3  mov     rdi, [rsi+28h]
0x14001bfb7  mov     rax, rdi
0x14001bfba  sub     rax, rbx
0x14001bfbd  mov     r14d, 1
0x14001bfc3  cmp     rax, 10h
0x14001bfc7  jb      loc_14001C131
0x14001bfcd  lea     r15d, [r14+1]
0x14001bfd1  mov     r12d, 1FFh
0x14001bfd7  cmp     rbx, rdi
0x14001bfda  jz      loc_14001C0FE
0x14001bfe0  mov     r8, [rbx+8]
0x14001bfe4  mov     r10d, [rbx]
0x14001bfe7  prefetchw byte ptr [r8]
0x14001bfeb  mov     eax, [r8]
0x14001bfee  mov     ecx, eax
0x14001bff0  and     ecx, 0FFC0401Eh
0x14001bff6  lock cmpxchg [r8], ecx
0x14001bffb  jnz     short loc_14001BFEE
0x14001bffd  mov     ecx, eax
0x14001bfff  mov     r9d, eax
0x14001c002  shr     r9d, 1
0x14001c005  and     r9d, 0Fh
0x14001c009  jz      short loc_14001C028
0x14001c00b  prefetchw byte ptr [r8+4]
0x14001c010  mov     eax, [r8+4]
0x14001c014  mov     edx, eax
0x14001c016  or      edx, r9d
0x14001c019  lock cmpxchg [r8+4], edx
0x14001c01f  jnz     short loc_14001C014
0x14001c021  not     eax
0x14001c023  and     eax, r9d
0x14001c026  jmp     short loc_14001C02B
0x14001c028  mov     eax, r9d
0x14001c02b  test    r14b, al
0x14001c02e  jz      short loc_14001C044
0x14001c030  mov     [rsp+98h+var_60], r10d
0x14001c035  mov     [rsp+98h+var_5C], 10002h
0x14001c03d  lea     rdx, [rsp+98h+var_58]
0x14001c042  jmp     short loc_14001C049
0x14001c044  lea     rdx, [rsp+98h+var_60]
0x14001c049  test    r15b, al
0x14001c04c  jz      short loc_14001C05C
0x14001c04e  mov     [rdx], r10d
0x14001c051  mov     dword ptr [rdx+4], 10006h
0x14001c058  add     rdx, 8
0x14001c05c  test    al, 4
0x14001c05e  jz      short loc_14001C06E
0x14001c060  mov     [rdx], r10d
0x14001c063  mov     dword ptr [rdx+4], 10003h
0x14001c06a  add     rdx, 8
0x14001c06e  cmp     eax, 8
0x14001c071  jb      short loc_14001C081
0x14001c073  mov     [rdx], r10d
0x14001c076  mov     dword ptr [rdx+4], 10007h
0x14001c07d  add     rdx, 8
0x14001c081  mov     r8d, ecx
0x14001c084  shr     r8d, 5
0x14001c088  test    r12d, r8d
0x14001c08b  jz      short loc_14001C0AE
0x14001c08d  mov     [rdx], r10d
0x14001c090  mov     eax, ecx
0x14001c092  shr     eax, 0Eh
0x14001c095  and     ax, r14w
0x14001c099  shl     ax, 2
0x14001c09d  mov     [rdx+4], ax
0x14001c0a1  and     r8w, r12w; unsigned __int64
0x14001c0a5  mov     [rdx+6], r8w
0x14001c0aa  add     rdx, 8
0x14001c0ae  mov     eax, ecx
0x14001c0b0  shr     eax, 0Fh
0x14001c0b3  test    al, 7Fh
0x14001c0b5  jz      short loc_14001C0D9
0x14001c0b7  mov     [rdx], r10d
0x14001c0ba  shr     ecx, 16h
0x14001c0bd  and     cx, r14w
0x14001c0c1  shl     cx, 2
0x14001c0c5  add     cx, r14w
0x14001c0c9  mov     [rdx+4], cx
0x14001c0cd  and     ax, 7Fh
0x14001c0d1  mov     [rdx+6], ax
0x14001c0d5  add     rdx, 8
0x14001c0d9  lea     rax, [rsp+98h+var_60]
0x14001c0de  sub     rdx, rax
0x14001c0e1  sar     rdx, 3; struct __WIL_RTL_FEATURE_USAGE_DATA *
0x14001c0e5  test    rdx, rdx
0x14001c0e8  jle     short loc_14001C0F5
0x14001c0ea  lea     rcx, [rsp+98h+var_60]; this
0x14001c0ef  call    ?WilApi_RecordFeatureUsageReports@details@wil@@YAXPEAU__WIL_RTL_FEATURE_USAGE_DATA@@_K@Z; wil::details::WilApi_RecordFeatureUsageReports(__WIL_RTL_FEATURE_USAGE_DATA *,unsigned __int64)
0x14001c0f4  nop
0x14001c0f5  add     rbx, 10h
0x14001c0f9  jmp     loc_14001BFD7
0x14001c0fe  mov     rax, [rsi+20h]
0x14001c102  mov     [rsi+28h], rax
0x14001c106  mov     rax, cs:g_wil_details_internalRecordFeatureUsage
0x14001c10d  test    rax, rax
0x14001c110  jnz     short loc_14001C11E
0x14001c112  mov     rax, cs:g_wil_details_apiRecordFeatureUsage
0x14001c119  test    rax, rax
0x14001c11c  jz      short loc_14001C131
0x14001c11e  xor     r9d, r9d
0x14001c121  xor     r8d, r8d
0x14001c124  mov     edx, 0FEh
0x14001c129  xor     ecx, ecx
0x14001c12b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c130  nop
0x14001c131  test    rbp, rbp
0x14001c134  jz      short loc_14001C145
0x14001c136  mov     rcx, rbp; SRWLock
0x14001c139  call    cs:__imp_ReleaseSRWLockExclusive
0x14001c140  nop     dword ptr [rax+rax+00h]
0x14001c145  xor     edx, edx
0x14001c147  lea     rcx, [rsp+98h+pti]
0x14001c14c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x14001c151  mov     rbx, [rsp+98h+pti]
0x14001c156  test    rbx, rbx
0x14001c159  jz      short loc_14001C194
0x14001c15b  xor     r9d, r9d; msWindowLength
0x14001c15e  xor     r8d, r8d; msPeriod
0x14001c161  xor     edx, edx; pftDueTime
0x14001c163  mov     rcx, rbx; pti
0x14001c166  call    cs:__imp_SetThreadpoolTimer
0x14001c16d  nop     dword ptr [rax+rax+00h]
0x14001c172  mov     edx, r14d; fCancelPendingCallbacks
0x14001c175  mov     rcx, rbx; pti
0x14001c178  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14001c17f  nop     dword ptr [rax+rax+00h]
0x14001c184  mov     rcx, rbx; pti
0x14001c187  call    cs:__imp_CloseThreadpoolTimer
0x14001c18e  nop     dword ptr [rax+rax+00h]
0x14001c193  nop
0x14001c194  mov     rcx, [rsp+98h+var_30]
0x14001c199  xor     rcx, rsp; StackCookie
0x14001c19c  call    __security_check_cookie
0x14001c1a1  lea     r11, [rsp+98h+var_28]
0x14001c1a6  mov     rbx, [r11+38h]
0x14001c1aa  mov     rbp, [r11+40h]
0x14001c1ae  mov     rsp, r11
0x14001c1b1  pop     r15
0x14001c1b3  pop     r14
0x14001c1b5  pop     r12
0x14001c1b7  pop     rdi
0x14001c1b8  pop     rsi
0x14001c1b9  retn
```
