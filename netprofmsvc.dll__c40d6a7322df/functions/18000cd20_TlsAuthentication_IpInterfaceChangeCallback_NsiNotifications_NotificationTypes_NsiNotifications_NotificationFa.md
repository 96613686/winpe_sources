# TlsAuthentication::IpInterfaceChangeCallback(NsiNotifications::NotificationTypes,NsiNotifications::NotificationFamily,_NET_LUID_LH const &,_NL_INTERFACE_RW const *,_NL_INTERFACE_ROD const *,_NL_INTERFACE_ROS const *)

- ea: `0x18000cd20`
- end: `0x18000ceed`
- name: `?IpInterfaceChangeCallback@TlsAuthentication@@CAXW4NotificationTypes@NsiNotifications@@W4NotificationFamily@3@AEBT_NET_LUID_LH@@PEBU_NL_INTERFACE_RW@@PEBU_NL_INTERFACE_ROD@@PEBU_NL_INTERFACE_ROS@@@Z`
- size: `461`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000cd20`
- `0x18000e190`
- `0x180015608`
- `0x180122f3c`
- `0x180122ffc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ce11`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000ce11`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce38`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ce93`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000cea8`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000cea8`

## string_xrefs

- `0x18000ce71`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\tlsauthentication.cpp`
- `0x18000ceb6`: `onecore\net\netprofiles\service\src\tlsauthentication\lib\tlsauthentication.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall TlsAuthentication::IpInterfaceChangeCallback(
        int a1,
        unsigned int a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  const char *v7; // r9
  __m128i v8; // xmm6
  __int64 v9; // rdx
  signed __int32 v10; // eax
  signed __int32 v11; // ett
  __int16 v12; // r8
  bool v13; // dl
  int v14; // ecx
  std::_Ref_count_base *v15; // rcx
  int v16; // [rsp+20h] [rbp-48h]
  int v17; // [rsp+20h] [rbp-48h]
  _QWORD v18[2]; // [rsp+30h] [rbp-38h] BYREF
  __int16 v19; // [rsp+40h] [rbp-28h]
  int v20; // [rsp+44h] [rbp-24h]
  bool v21; // [rsp+48h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  try
  {
    v7 = (const char *)a2;
    if ( !a6 || *(_DWORD *)(a6 + 4) != 24 )
    {
      if ( a2 - 1 > 1 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4F6,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\tlsauthentication.cpp",
          (const char *)0x8000FFFFLL,
          v16);
      v8 = 0;
      v17 = 0;
      v9 = *((_QWORD *)&TlsAuthentication::s_weakRef + 1);
      if ( *((_QWORD *)&TlsAuthentication::s_weakRef + 1) )
      {
        v10 = *(_DWORD *)(*((_QWORD *)&TlsAuthentication::s_weakRef + 1) + 8LL);
        while ( v10 )
        {
          v11 = v10;
          v10 = _InterlockedCompareExchange((volatile signed __int32 *)(v9 + 8), v10 + 1, v10);
          if ( v11 == v10 )
          {
            v8 = *(__m128i *)&TlsAuthentication::s_weakRef;
            v17 = TlsAuthentication::s_weakRef;
            break;
          }
        }
      }
      if ( !v8.m128i_i64[0] )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4F9,
          (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\tlsauthentication.cpp",
          (const char *)0x80070015LL,
          v17);
      v12 = 2;
      if ( (_DWORD)v7 != 1 )
        v12 = 23;
      v13 = a1 == 8 || a1 == 2;
      if ( a5 )
        v14 = *(_DWORD *)(a5 + 16);
      else
        v14 = 0;
      v18[0] = v8.m128i_i64[0];
      v18[1] = *a3;
      v19 = v12;
      v20 = v14;
      v21 = v13;
      EnterCriticalSection((LPCRITICAL_SECTION)(v8.m128i_i64[0] + 136));
      if ( *(_BYTE *)(v8.m128i_i64[0] + 400) )
      {
        if ( v8.m128i_i64[0] != -136 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v8.m128i_i64[0] + 136));
      }
      else
      {
        if ( *(_DWORD *)(v8.m128i_i64[0] + 128) == 1 )
          std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__TlsAuthentication::IpInterfaceChangeCallback_::_3_::_lambda_1___(
            v8.m128i_i64[0] + 280,
            v18);
        else
          std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__TlsAuthentication::IpInterfaceChangeCallback_::_3_::_lambda_1___(
            v8.m128i_i64[0] + 360,
            v18);
        if ( v8.m128i_i64[0] != -136 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v8.m128i_i64[0] + 136));
        _InterlockedIncrement64((volatile signed __int64 *)(v8.m128i_i64[0] + 264));
        SubmitThreadpoolWork(*(PTP_WORK *)(v8.m128i_i64[0] + 256));
      }
      v15 = (std::_Ref_count_base *)_mm_srli_si128(v8, 8).m128i_u64[0];
      if ( v15 )
        std::_Ref_count_base::_Decref(v15);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x51E,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\tlsauthentication\\lib\\tlsauthentication.cpp",
      v7);
  }
}

```

## disassembly

```asm
0x18000cd20  mov     [rsp+arg_0], rbx
0x18000cd25  push    rdi
0x18000cd26  sub     rsp, 60h
0x18000cd2a  movaps  [rsp+68h+var_18], xmm6
0x18000cd2f  mov     r11, r8
0x18000cd32  mov     r9d, edx
0x18000cd35  mov     r10d, ecx
0x18000cd38  mov     rax, [rsp+68h+arg_28]
0x18000cd40  test    rax, rax
0x18000cd43  jz      short loc_18000CD4F
0x18000cd45  cmp     dword ptr [rax+4], 18h
0x18000cd49  jz      loc_18000CE89
0x18000cd4f  lea     eax, [rdx-1]
0x18000cd52  cmp     eax, 1
0x18000cd55  setbe   al
0x18000cd58  mov     rcx, [rsp+68h]; this
0x18000cd5d  test    al, al
0x18000cd5f  jz      loc_18000CEB0
0x18000cd65  xorps   xmm6, xmm6
0x18000cd68  movdqu  xmmword ptr [rsp+68h+var_48], xmm6
0x18000cd6e  mov     rdx, qword ptr cs:?s_weakRef@TlsAuthentication@@0V?$weak_ptr@VTlsAuthentication@@@std@@A+8; std::weak_ptr<TlsAuthentication> TlsAuthentication::s_weakRef
0x18000cd75  test    rdx, rdx
0x18000cd78  jz      short loc_18000CD98
0x18000cd7a  mov     eax, [rdx+8]
0x18000cd7d  test    eax, eax
0x18000cd7f  jz      short loc_18000CD98
0x18000cd81  lea     ecx, [rax+1]
0x18000cd84  lock cmpxchg [rdx+8], ecx
0x18000cd89  jnz     short loc_18000CD7D
0x18000cd8b  movups  xmm6, cs:?s_weakRef@TlsAuthentication@@0V?$weak_ptr@VTlsAuthentication@@@std@@A; std::weak_ptr<TlsAuthentication> TlsAuthentication::s_weakRef
0x18000cd92  movdqu  xmmword ptr [rsp+68h+var_48], xmm6; int
0x18000cd98  movq    rbx, xmm6
0x18000cd9d  test    rbx, rbx
0x18000cda0  setz    al
0x18000cda3  mov     rcx, [rsp+68h]; this
0x18000cda8  test    al, al
0x18000cdaa  jnz     loc_18000CE6B
0x18000cdb0  mov     eax, 17h
0x18000cdb5  lea     r8d, [rax-15h]
0x18000cdb9  cmp     r9d, 1
0x18000cdbd  cmovnz  r8w, ax
0x18000cdc2  cmp     r10d, 8
0x18000cdc6  jz      loc_18000CE64
0x18000cdcc  cmp     r10d, 2
0x18000cdd0  jz      loc_18000CE64
0x18000cdd6  xor     dl, dl
0x18000cdd8  mov     rax, [rsp+68h+arg_20]
0x18000cde0  test    rax, rax
0x18000cde3  jz      loc_18000CE82
0x18000cde9  mov     ecx, [rax+10h]
0x18000cdec  mov     [rsp+68h+var_38], rbx
0x18000cdf1  mov     rax, [r11]
0x18000cdf4  mov     [rsp+68h+var_30], rax
0x18000cdf9  mov     [rsp+68h+var_28], r8w
0x18000cdff  mov     [rsp+68h+var_24], ecx
0x18000ce03  mov     [rsp+68h+var_20], dl
0x18000ce07  lea     rdi, [rbx+88h]
0x18000ce0e  mov     rcx, rdi; lpCriticalSection
0x18000ce11  call    cs:__imp_EnterCriticalSection
0x18000ce17  mov     [rsp+68h+arg_28], rdi
0x18000ce1f  lea     rcx, [rbx+118h]
0x18000ce26  cmp     byte ptr [rcx+78h], 0
0x18000ce2a  jz      loc_18000CEC8
0x18000ce30  test    rdi, rdi
0x18000ce33  jz      short loc_18000CE3F
0x18000ce35  mov     rcx, rdi; lpCriticalSection
0x18000ce38  call    cs:__imp_LeaveCriticalSection
0x18000ce3e  nop
0x18000ce3f  psrldq  xmm6, 8
0x18000ce44  movq    rcx, xmm6; this
0x18000ce49  test    rcx, rcx
0x18000ce4c  jz      short loc_18000CE54
0x18000ce4e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000ce53  nop
0x18000ce54  mov     rbx, [rsp+68h+arg_0]
0x18000ce59  movaps  xmm6, [rsp+68h+var_18]
0x18000ce5e  add     rsp, 60h
0x18000ce62  pop     rdi
0x18000ce63  retn
0x18000ce64  mov     dl, 1
0x18000ce66  jmp     loc_18000CDD8
0x18000ce6b  mov     r9d, 80070015h; char *
0x18000ce71  lea     r8, aOnecoreNetNetp_56; "onecore\\net\\netprofiles\\service\\src"...
0x18000ce78  mov     edx, 4F9h; void *
0x18000ce7d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000ce82  xor     ecx, ecx
0x18000ce84  jmp     loc_18000CDEC
0x18000ce89  jmp     short loc_18000CE54
0x18000ce8b  test    rdi, rdi
0x18000ce8e  jz      short loc_18000CE99
0x18000ce90  mov     rcx, rdi; lpCriticalSection
0x18000ce93  call    cs:__imp_LeaveCriticalSection
0x18000ce99  lock inc qword ptr [rbx+108h]
0x18000cea1  mov     rcx, [rbx+100h]; pwk
0x18000cea8  call    cs:__imp_SubmitThreadpoolWork
0x18000ceae  jmp     short loc_18000CE3F
0x18000ceb0  mov     r9d, 8000FFFFh; char *
0x18000ceb6  lea     r8, aOnecoreNetNetp_56; "onecore\\net\\netprofiles\\service\\src"...
0x18000cebd  mov     edx, 4F6h; void *
0x18000cec2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18000cec8  lea     rdx, [rsp+68h+var_38]
0x18000cecd  cmp     dword ptr [rbx+80h], 1
0x18000ced4  jnz     short loc_18000CEDD
0x18000ced6  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__TlsAuthentication__IpInterfaceChangeCallback____3____lambda_1___
0x18000cedb  jmp     short loc_18000CE8B
0x18000cedd  add     rcx, 50h ; 'P'
0x18000cee1  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__TlsAuthentication__IpInterfaceChangeCallback____3____lambda_1___
0x18000cee6  jmp     short loc_18000CE8B
0x18000cee8  jmp     loc_18000CE54
```
