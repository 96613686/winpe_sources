# ConnectivityAggregator::OnFirewallReadyAndStable(void)

- ea: `0x18000d428`
- end: `0x18000d531`
- name: `?OnFirewallReadyAndStable@ConnectivityAggregator@@SAXXZ`
- size: `265`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180085d20`

## callees

- `0x18000d428`
- `0x18000e190`
- `0x180015608`
- `0x18012b890`
- `0x18012b948`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d48a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d48a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4f5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d4f5`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d50a`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000d50a`

## string_xrefs

- `0x18000d4dc`: `onecore\net\netprofiles\service\src\common\connectivityaggregator.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void ConnectivityAggregator::OnFirewallReadyAndStable(void)
{
  __m128i v0; // xmm6
  __int64 v1; // rdx
  signed __int32 v2; // eax
  signed __int32 v3; // ett
  const char *v4; // r9
  std::_Ref_count_base *v5; // rcx
  int v6; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  __int64 v9; // [rsp+58h] [rbp+10h]

  v0 = 0;
  v6 = 0;
  v1 = *((_QWORD *)&xmmword_1801C87A0 + 1);
  if ( *((_QWORD *)&xmmword_1801C87A0 + 1) )
  {
    v2 = *(_DWORD *)(*((_QWORD *)&xmmword_1801C87A0 + 1) + 8LL);
    while ( v2 )
    {
      v3 = v2;
      v2 = _InterlockedCompareExchange((volatile signed __int32 *)(v1 + 8), v2 + 1, v2);
      if ( v3 == v2 )
      {
        v0 = *(__m128i *)&xmmword_1801C87A0;
        v6 = xmmword_1801C87A0;
        break;
      }
    }
  }
  try
  {
    if ( !v0.m128i_i64[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1B8,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectivityaggregator.cpp",
        (const char *)0x80070015LL,
        v6);
    v8 = v0.m128i_i64[0];
    EnterCriticalSection((LPCRITICAL_SECTION)(v0.m128i_i64[0] + 16));
    v9 = v0.m128i_i64[0] + 16;
    if ( *(_BYTE *)(v0.m128i_i64[0] + 280) )
    {
      if ( v0.m128i_i64[0] != -16 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v0.m128i_i64[0] + 16));
    }
    else
    {
      if ( *(_DWORD *)(v0.m128i_i64[0] + 8) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__ConnectivityAggregator::OnFirewallReadyAndStable_::_3_::_lambda_1___(
          v0.m128i_i64[0] + 160,
          &v8);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__ConnectivityAggregator::OnFirewallReadyAndStable_::_3_::_lambda_1___(
          v0.m128i_i64[0] + 240,
          &v8);
      if ( v0.m128i_i64[0] != -16 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v0.m128i_i64[0] + 16));
      _InterlockedIncrement64((volatile signed __int64 *)(v0.m128i_i64[0] + 144));
      SubmitThreadpoolWork(*(PTP_WORK *)(v0.m128i_i64[0] + 136));
    }
    v5 = (std::_Ref_count_base *)_mm_srli_si128(v0, 8).m128i_u64[0];
    if ( v5 )
      std::_Ref_count_base::_Decref(v5);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1E0,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\common\\connectivityaggregator.cpp",
      v4);
  }
}

```

## disassembly

```asm
0x18000d428  mov     [rsp+arg_10], rbx
0x18000d42d  push    rdi
0x18000d42e  sub     rsp, 40h
0x18000d432  movaps  [rsp+48h+var_18], xmm6
0x18000d437  xorps   xmm6, xmm6
0x18000d43a  movdqu  xmmword ptr [rsp+48h+var_28], xmm6
0x18000d440  mov     rdx, qword ptr cs:xmmword_1801C87A0+8
0x18000d447  test    rdx, rdx
0x18000d44a  jz      short loc_18000D46A
0x18000d44c  mov     eax, [rdx+8]
0x18000d44f  test    eax, eax
0x18000d451  jz      short loc_18000D46A
0x18000d453  lea     ecx, [rax+1]
0x18000d456  lock cmpxchg [rdx+8], ecx
0x18000d45b  jnz     short loc_18000D44F
0x18000d45d  movups  xmm6, cs:xmmword_1801C87A0
0x18000d464  movdqu  xmmword ptr [rsp+48h+var_28], xmm6; int
0x18000d46a  movq    rbx, xmm6
0x18000d46f  test    rbx, rbx
0x18000d472  setz    al
0x18000d475  mov     rcx, [rsp+48h]; this
0x18000d47a  test    al, al
0x18000d47c  jnz     short loc_18000D4D6
0x18000d47e  mov     [rsp+48h+arg_0], rbx
0x18000d483  lea     rdi, [rbx+10h]
0x18000d487  mov     rcx, rdi; lpCriticalSection
0x18000d48a  call    cs:__imp_EnterCriticalSection
0x18000d490  mov     [rsp+48h+arg_8], rdi
0x18000d495  lea     rcx, [rbx+0A0h]
0x18000d49c  cmp     byte ptr [rcx+78h], 0
0x18000d4a0  jz      short loc_18000D512
0x18000d4a2  test    rdi, rdi
0x18000d4a5  jz      short loc_18000D4B1
0x18000d4a7  mov     rcx, rdi; lpCriticalSection
0x18000d4aa  call    cs:__imp_LeaveCriticalSection
0x18000d4b0  nop
0x18000d4b1  psrldq  xmm6, 8
0x18000d4b6  movq    rcx, xmm6; this
0x18000d4bb  test    rcx, rcx
0x18000d4be  jz      short loc_18000D4C6
0x18000d4c0  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d4c5  nop
0x18000d4c6  mov     rbx, [rsp+48h+arg_10]
0x18000d4cb  movaps  xmm6, [rsp+48h+var_18]
0x18000d4d0  add     rsp, 40h
0x18000d4d4  pop     rdi
0x18000d4d5  retn
0x18000d4d6  mov     r9d, 80070015h; char *
0x18000d4dc  lea     r8, aOnecoreNetNetp_45; "onecore\\net\\netprofiles\\service\\src"...
0x18000d4e3  mov     edx, 1B8h; void *
0x18000d4e8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000d4ed  test    rdi, rdi
0x18000d4f0  jz      short loc_18000D4FB
0x18000d4f2  mov     rcx, rdi; lpCriticalSection
0x18000d4f5  call    cs:__imp_LeaveCriticalSection
0x18000d4fb  lock inc qword ptr [rbx+90h]
0x18000d503  mov     rcx, [rbx+88h]; pwk
0x18000d50a  call    cs:__imp_SubmitThreadpoolWork
0x18000d510  jmp     short loc_18000D4B1
0x18000d512  lea     rdx, [rsp+48h+arg_0]
0x18000d517  cmp     dword ptr [rbx+8], 1
0x18000d51b  jnz     short loc_18000D524
0x18000d51d  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__ConnectivityAggregator__OnFirewallReadyAndStable____3____lambda_1___
0x18000d522  jmp     short loc_18000D4ED
0x18000d524  add     rcx, 50h ; 'P'
0x18000d528  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__ConnectivityAggregator__OnFirewallReadyAndStable____3____lambda_1___
0x18000d52d  jmp     short loc_18000D4ED
0x18000d52f  jmp     short loc_18000D4C6
```
