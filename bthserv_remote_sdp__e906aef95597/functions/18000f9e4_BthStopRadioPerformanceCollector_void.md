# BthStopRadioPerformanceCollector(void)

- ea: `0x18000f9e4`
- end: `0x18000fb4d`
- name: `?BthStopRadioPerformanceCollector@@YAXXZ`
- size: `361`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config`

## callers

- `0x18000f0e0`

## callees

- `0x180001b94`
- `0x180009c50`
- `0x18000f9e4`
- `0x180012004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000fb41`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fa63`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000fa63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fac2`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fac2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fab3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fab3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000faa2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000faa2`

## pseudocode

```c
void BthStopRadioPerformanceCollector(void)
{
  char v0; // di
  bool v1; // dl
  struct _TP_TIMER **v2; // rsi
  struct _TP_TIMER *v3; // rbx

  v0 = 1;
  v1 = WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u;
  if ( v1 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v1,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  AcquireSRWLockExclusive(&stru_180047118);
  v2 = (struct _TP_TIMER **)qword_180047130;
  qword_180047130 = 0;
  if ( v2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v2 + 1,
      0);
    v3 = v2[1];
    if ( v3 )
    {
      SetThreadpoolTimer(v2[1], 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(v3, 1);
      CloseThreadpoolTimer(v3);
    }
    operator delete(v2, (const struct std::nothrow_t *)0x10);
  }
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || *((_BYTE *)WPP_GLOBAL_Control + 25) < 5u )
    v0 = 0;
  if ( v0 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_AND_TRACE_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v0,
      WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
      *((_QWORD *)WPP_GLOBAL_Control + 5));
  ReleaseSRWLockExclusive(&stru_180047118);
}

```

## disassembly

```asm
0x18000f9e4  mov     [rsp+arg_0], rbx
0x18000f9e9  mov     [rsp+arg_8], rbp
0x18000f9ee  mov     [rsp+arg_10], rsi
0x18000f9f3  push    rdi
0x18000f9f4  push    r14
0x18000f9f6  push    r15
0x18000f9f8  sub     rsp, 50h
0x18000f9fc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fa03  lea     rbp, WPP_GLOBAL_Control
0x18000fa0a  mov     edi, 1
0x18000fa0f  cmp     rcx, rbp
0x18000fa12  jz      short loc_18000FA1F
0x18000fa14  cmp     byte ptr [rcx+19h], 5
0x18000fa18  jb      short loc_18000FA1F
0x18000fa1a  mov     dl, dil
0x18000fa1d  jmp     short loc_18000FA21
0x18000fa1f  xor     dl, dl
0x18000fa21  lea     r14, WPP_RECORDER_INITIALIZED
0x18000fa28  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000fa2f  lea     r15, WPP_bcf7bf2191843370f4639d603d2379a2_Traceguids
0x18000fa36  setnz   r8b
0x18000fa3a  test    dl, dl
0x18000fa3c  jnz     short loc_18000FA43
0x18000fa3e  test    r8b, r8b
0x18000fa41  jz      short loc_18000FA5C
0x18000fa43  mov     r9, [rcx+28h]
0x18000fa47  mov     rcx, [rcx+10h]
0x18000fa4b  mov     [rsp+68h+var_30], r15
0x18000fa50  mov     [rsp+68h+var_38], 8Eh
0x18000fa57  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000fa5c  lea     rcx, stru_180047118; SRWLock
0x18000fa63  call    cs:__imp_AcquireSRWLockExclusive
0x18000fa6a  nop     dword ptr [rax+rax+00h]
0x18000fa6f  mov     rsi, cs:qword_180047130
0x18000fa76  and     cs:qword_180047130, 0
0x18000fa7e  test    rsi, rsi
0x18000fa81  jz      short loc_18000FADB
0x18000fa83  xor     edx, edx
0x18000fa85  lea     rcx, [rsi+8]
0x18000fa89  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18000fa8e  mov     rbx, [rsi+8]
0x18000fa92  test    rbx, rbx
0x18000fa95  jz      short loc_18000FACE
0x18000fa97  xor     r9d, r9d; msWindowLength
0x18000fa9a  xor     r8d, r8d; msPeriod
0x18000fa9d  xor     edx, edx; pftDueTime
0x18000fa9f  mov     rcx, rbx; pti
0x18000faa2  call    cs:__imp_SetThreadpoolTimer
0x18000faa9  nop     dword ptr [rax+rax+00h]
0x18000faae  mov     edx, edi; fCancelPendingCallbacks
0x18000fab0  mov     rcx, rbx; pti
0x18000fab3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000faba  nop     dword ptr [rax+rax+00h]
0x18000fabf  mov     rcx, rbx; pti
0x18000fac2  call    cs:__imp_CloseThreadpoolTimer
0x18000fac9  nop     dword ptr [rax+rax+00h]
0x18000face  mov     edx, 10h; struct std::nothrow_t *
0x18000fad3  mov     rcx, rsi; void *
0x18000fad6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000fadb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000fae2  cmp     rcx, rbp
0x18000fae5  jz      short loc_18000FAED
0x18000fae7  cmp     byte ptr [rcx+19h], 5
0x18000faeb  jnb     short loc_18000FAF0
0x18000faed  xor     dil, dil
0x18000faf0  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x18000faf7  setnz   r8b
0x18000fafb  test    dil, dil
0x18000fafe  jnz     short loc_18000FB05
0x18000fb00  test    r8b, r8b
0x18000fb03  jz      short loc_18000FB21
0x18000fb05  mov     r9, [rcx+28h]
0x18000fb09  mov     dl, dil
0x18000fb0c  mov     rcx, [rcx+10h]
0x18000fb10  mov     [rsp+68h+var_30], r15
0x18000fb15  mov     [rsp+68h+var_38], 8Fh
0x18000fb1c  call    WPP_RECORDER_AND_TRACE_SF_s
0x18000fb21  lea     rcx, stru_180047118
0x18000fb28  lea     r11, [rsp+68h+var_18]
0x18000fb2d  mov     rbx, [r11+20h]
0x18000fb31  mov     rbp, [r11+28h]
0x18000fb35  mov     rsi, [r11+30h]
0x18000fb39  mov     rsp, r11
0x18000fb3c  pop     r15
0x18000fb3e  pop     r14
0x18000fb40  pop     rdi
0x18000fb41  jmp     cs:__imp_ReleaseSRWLockExclusive
```
