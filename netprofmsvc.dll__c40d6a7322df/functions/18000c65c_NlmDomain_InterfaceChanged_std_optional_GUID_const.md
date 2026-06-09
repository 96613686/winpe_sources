# NlmDomain::InterfaceChanged(std::optional<_GUID> const &)

- ea: `0x18000c65c`
- end: `0x18000c76f`
- name: `?InterfaceChanged@NlmDomain@@SAXAEBV?$optional@U_GUID@@@std@@@Z`
- size: `275`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008a80`
- `0x1800270c8`
- `0x18002b5ac`
- `0x18002bde8`
- `0x180051c00`
- `0x180054ee0`
- `0x18005a040`
- `0x180064350`
- `0x180066a90`
- `0x180089a90`
- `0x180091500`
- `0x180104280`
- `0x180105244`
- `0x1801069f8`
- `0x18010b3bc`

## callees

- `0x18000c65c`
- `0x18000e190`
- `0x180015608`
- `0x18012e004`
- `0x18012e0bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000c6c5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c730`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c6e5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c730`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000c745`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000c745`

## string_xrefs

- `0x18000c717`: `onecore\net\netprofiles\service\src\domain\lib\nlmdomain.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall NlmDomain::InterfaceChanged(__int64 a1)
{
  __m128i v1; // xmm6
  __int64 v2; // rdx
  signed __int32 v3; // eax
  signed __int32 v4; // ett
  const char *v5; // r9
  std::_Ref_count_base *v6; // rcx
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v9; // [rsp+50h] [rbp+8h] BYREF
  __int64 v10; // [rsp+58h] [rbp+10h]

  v9 = a1;
  v1 = 0;
  v7 = 0;
  v2 = *((_QWORD *)&xmmword_1801C8800 + 1);
  if ( *((_QWORD *)&xmmword_1801C8800 + 1) )
  {
    v3 = *(_DWORD *)(*((_QWORD *)&xmmword_1801C8800 + 1) + 8LL);
    while ( v3 )
    {
      v4 = v3;
      v3 = _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 8), v3 + 1, v3);
      if ( v4 == v3 )
      {
        v1 = *(__m128i *)&xmmword_1801C8800;
        v7 = xmmword_1801C8800;
        break;
      }
    }
  }
  try
  {
    if ( !v1.m128i_i64[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x113,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\domain\\lib\\nlmdomain.cpp",
        (const char *)0x80070015LL,
        v7);
    v9 = v1.m128i_i64[0];
    EnterCriticalSection((LPCRITICAL_SECTION)(v1.m128i_i64[0] + 288));
    v10 = v1.m128i_i64[0] + 288;
    if ( *(_BYTE *)(v1.m128i_i64[0] + 552) )
    {
      if ( v1.m128i_i64[0] != -288 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v1.m128i_i64[0] + 288));
    }
    else
    {
      if ( *(_DWORD *)(v1.m128i_i64[0] + 280) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__NlmDomain::InterfaceChanged_::_3_::_lambda_1___(
          v1.m128i_i64[0] + 432,
          &v9);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__NlmDomain::InterfaceChanged_::_3_::_lambda_1___(
          v1.m128i_i64[0] + 512,
          &v9);
      if ( v1.m128i_i64[0] != -288 )
        LeaveCriticalSection((LPCRITICAL_SECTION)(v1.m128i_i64[0] + 288));
      _InterlockedIncrement64((volatile signed __int64 *)(v1.m128i_i64[0] + 416));
      SubmitThreadpoolWork(*(PTP_WORK *)(v1.m128i_i64[0] + 408));
    }
    v6 = (std::_Ref_count_base *)_mm_srli_si128(v1, 8).m128i_u64[0];
    if ( v6 )
      std::_Ref_count_base::_Decref(v6);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1AB,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\domain\\lib\\nlmdomain.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x18000c65c  mov     rax, rsp
0x18000c65f  mov     [rax+18h], rbx
0x18000c663  mov     [rax+8], rcx
0x18000c667  push    rdi
0x18000c668  sub     rsp, 40h
0x18000c66c  movaps  xmmword ptr [rax-18h], xmm6
0x18000c670  xorps   xmm6, xmm6
0x18000c673  movdqu  xmmword ptr [rax-28h], xmm6
0x18000c678  mov     rdx, qword ptr cs:xmmword_1801C8800+8
0x18000c67f  test    rdx, rdx
0x18000c682  jz      short loc_18000C6A2
0x18000c684  mov     eax, [rdx+8]
0x18000c687  test    eax, eax
0x18000c689  jz      short loc_18000C6A2
0x18000c68b  lea     ecx, [rax+1]
0x18000c68e  lock cmpxchg [rdx+8], ecx
0x18000c693  jnz     short loc_18000C687
0x18000c695  movups  xmm6, cs:xmmword_1801C8800
0x18000c69c  movdqu  xmmword ptr [rsp+48h+var_28], xmm6; int
0x18000c6a2  movq    rbx, xmm6
0x18000c6a7  test    rbx, rbx
0x18000c6aa  setz    al
0x18000c6ad  mov     rcx, [rsp+48h]; this
0x18000c6b2  test    al, al
0x18000c6b4  jnz     short loc_18000C711
0x18000c6b6  mov     [rsp+48h+arg_0], rbx
0x18000c6bb  lea     rdi, [rbx+120h]
0x18000c6c2  mov     rcx, rdi; lpCriticalSection
0x18000c6c5  call    cs:__imp_EnterCriticalSection
0x18000c6cb  mov     [rsp+48h+arg_8], rdi
0x18000c6d0  lea     rcx, [rbx+1B0h]
0x18000c6d7  cmp     byte ptr [rcx+78h], 0
0x18000c6db  jz      short loc_18000C74D
0x18000c6dd  test    rdi, rdi
0x18000c6e0  jz      short loc_18000C6EC
0x18000c6e2  mov     rcx, rdi; lpCriticalSection
0x18000c6e5  call    cs:__imp_LeaveCriticalSection
0x18000c6eb  nop
0x18000c6ec  psrldq  xmm6, 8
0x18000c6f1  movq    rcx, xmm6; this
0x18000c6f6  test    rcx, rcx
0x18000c6f9  jz      short loc_18000C701
0x18000c6fb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000c700  nop
0x18000c701  mov     rbx, [rsp+48h+arg_10]
0x18000c706  movaps  xmm6, [rsp+48h+var_18]
0x18000c70b  add     rsp, 40h
0x18000c70f  pop     rdi
0x18000c710  retn
0x18000c711  mov     r9d, 80070015h; char *
0x18000c717  lea     r8, aOnecoreNetNetp_21; "onecore\\net\\netprofiles\\service\\src"...
0x18000c71e  mov     edx, 113h; void *
0x18000c723  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000c728  test    rdi, rdi
0x18000c72b  jz      short loc_18000C736
0x18000c72d  mov     rcx, rdi; lpCriticalSection
0x18000c730  call    cs:__imp_LeaveCriticalSection
0x18000c736  lock inc qword ptr [rbx+1A0h]
0x18000c73e  mov     rcx, [rbx+198h]; pwk
0x18000c745  call    cs:__imp_SubmitThreadpoolWork
0x18000c74b  jmp     short loc_18000C6EC
0x18000c74d  lea     rdx, [rsp+48h+arg_0]
0x18000c752  cmp     dword ptr [rbx+118h], 1
0x18000c759  jnz     short loc_18000C762
0x18000c75b  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__NlmDomain__InterfaceChanged____3____lambda_1___
0x18000c760  jmp     short loc_18000C728
0x18000c762  add     rcx, 50h ; 'P'
0x18000c766  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__NlmDomain__InterfaceChanged____3____lambda_1___
0x18000c76b  jmp     short loc_18000C728
0x18000c76d  jmp     short loc_18000C701
```
