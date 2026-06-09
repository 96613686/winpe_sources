# L2Manager::ProcessChangesFromWwanPlugin(_GUID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&)

- ea: `0x180019d14`
- end: `0x180019eae`
- name: `?ProcessChangesFromWwanPlugin@L2Manager@@SAXAEBU_GUID@@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z`
- size: `410`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800656ec`

## callees

- `0x18000e190`
- `0x180015608`
- `0x180019d14`
- `0x18001ae28`
- `0x180021850`
- `0x18002bd40`
- `0x18003b010`
- `0x1800902b0`
- `0x1800a88a0`
- `0x180101b44`
- `0x180101be8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019df5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180019df5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e44`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e15`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019e44`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180019e59`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180019e59`

## string_xrefs

- `0x180019db0`: `onecore\net\netprofiles\service\src\l2manager\lib\l2manager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall L2Manager::ProcessChangesFromWwanPlugin(__int128 *a1, __int64 a2, __int64 a3)
{
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  std::_Ref_count_base *v9; // rbx
  const char *v10; // r9
  int v11; // [rsp+20h] [rbp-E8h]
  std::_Ref_count_base *v12; // [rsp+30h] [rbp-D8h] BYREF
  __int128 v13; // [rsp+38h] [rbp-D0h]
  _BYTE v14[32]; // [rsp+48h] [rbp-C0h] BYREF
  _BYTE v15[40]; // [rsp+68h] [rbp-A0h] BYREF
  _BYTE v16[32]; // [rsp+90h] [rbp-78h] BYREF
  _BYTE v17[32]; // [rsp+B0h] [rbp-58h] BYREF
  std::_Ref_count_base *v18[2]; // [rsp+D0h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v18[0] = (std::_Ref_count_base *)v16;
  try
  {
    v6 = std::wstring::wstring(v16, a3);
    v7 = std::wstring::wstring(v17, a2);
    StandbyMonitor::ProcessWwanPluginDataIndication(a1, v7, v6);
    *(_OWORD *)v18 = 0;
    std::weak_ptr<L2Manager>::lock(v8, v18);
    v9 = v18[0];
    if ( !v18[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22B,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\l2manager.cpp",
        (const char *)0x8007045BLL,
        v11);
    v12 = v18[0];
    v13 = *a1;
    std::wstring::wstring(v14, a3);
    std::wstring::wstring(v15, a2);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 336));
    if ( *((_BYTE *)v9 + 600) )
    {
      if ( v9 != (std::_Ref_count_base *)-336LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 336));
    }
    else
    {
      if ( *((_DWORD *)v9 + 82) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__L2Manager::ProcessChangesFromWwanPlugin_::_3_::_lambda_1___(
          (char *)v9 + 480,
          &v12);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__L2Manager::ProcessChangesFromWwanPlugin_::_3_::_lambda_1___(
          (char *)v9 + 560,
          &v12);
      if ( v9 != (std::_Ref_count_base *)-336LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v9 + 336));
      _InterlockedIncrement64((volatile signed __int64 *)v9 + 58);
      SubmitThreadpoolWork(*((PTP_WORK *)v9 + 57));
    }
    std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(v15);
    std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(v14);
    if ( v18[1] )
      std::_Ref_count_base::_Decref(v18[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x240,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\l2manager.cpp",
      v10);
  }
}

```

## disassembly

```asm
0x180019d14  mov     r11, rsp
0x180019d17  mov     [r11+20h], rbx
0x180019d1b  push    rsi
0x180019d1c  push    rdi
0x180019d1d  push    r14
0x180019d1f  sub     rsp, 0F0h
0x180019d26  mov     rax, cs:__security_cookie
0x180019d2d  xor     rax, rsp
0x180019d30  mov     [rsp+108h+var_28], rax
0x180019d38  mov     rdi, r8
0x180019d3b  mov     rsi, rdx
0x180019d3e  mov     r14, rcx
0x180019d41  lea     rax, [r11-78h]
0x180019d45  mov     [r11-38h], rax
0x180019d49  mov     rdx, r8
0x180019d4c  lea     rcx, [r11-78h]
0x180019d50  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180019d55  mov     rbx, rax
0x180019d58  mov     rdx, rsi
0x180019d5b  lea     rcx, [rsp+108h+var_58]
0x180019d63  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180019d68  nop
0x180019d69  mov     r8, rbx
0x180019d6c  mov     rdx, rax
0x180019d6f  mov     rcx, r14
0x180019d72  call    ?ProcessWwanPluginDataIndication@StandbyMonitor@@YAXAEBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; StandbyMonitor::ProcessWwanPluginDataIndication(_GUID const &,std::wstring,std::wstring)
0x180019d77  xorps   xmm0, xmm0
0x180019d7a  movups  xmmword ptr [rsp+108h+var_38], xmm0
0x180019d82  lea     rdx, [rsp+108h+var_38]
0x180019d8a  call    ?lock@?$weak_ptr@VL2Manager@@@std@@QEBA?AV?$shared_ptr@VL2Manager@@@2@XZ; std::weak_ptr<L2Manager>::lock(void)
0x180019d8f  nop
0x180019d90  mov     rbx, [rsp+108h+var_38]
0x180019d98  test    rbx, rbx
0x180019d9b  setz    al
0x180019d9e  mov     rcx, [rsp+108h]; this
0x180019da6  test    al, al
0x180019da8  jz      short loc_180019DC1
0x180019daa  mov     r9d, 8007045Bh; char *
0x180019db0  lea     r8, aOnecoreNetNetp_55; "onecore\\net\\netprofiles\\service\\src"...
0x180019db7  mov     edx, 22Bh; void *
0x180019dbc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180019dc1  mov     [rsp+108h+var_D8], rbx
0x180019dc6  movups  xmm0, xmmword ptr [r14]
0x180019dca  movdqu  [rsp+108h+var_D0], xmm0
0x180019dd0  mov     rdx, rdi
0x180019dd3  lea     rcx, [rsp+108h+var_C0]
0x180019dd8  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180019ddd  mov     rdx, rsi
0x180019de0  lea     rcx, [rsp+108h+var_A0]
0x180019de5  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180019dea  nop
0x180019deb  lea     rdi, [rbx+150h]
0x180019df2  mov     rcx, rdi; lpCriticalSection
0x180019df5  call    cs:__imp_EnterCriticalSection
0x180019dfb  mov     qword ptr [rsp+108h+var_E8], rdi
0x180019e00  lea     rcx, [rbx+1E0h]
0x180019e07  cmp     byte ptr [rcx+78h], 0
0x180019e0b  jz      short loc_180019E1D
0x180019e0d  test    rdi, rdi
0x180019e10  jz      short loc_180019E60
0x180019e12  mov     rcx, rdi; lpCriticalSection
0x180019e15  call    cs:__imp_LeaveCriticalSection
0x180019e1b  jmp     short loc_180019E60
0x180019e1d  lea     rdx, [rsp+108h+var_D8]
0x180019e22  cmp     dword ptr [rbx+148h], 1
0x180019e29  jnz     short loc_180019E32
0x180019e2b  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__L2Manager__ProcessChangesFromWwanPlugin____3____lambda_1___
0x180019e30  jmp     short loc_180019E3C
0x180019e32  add     rcx, 50h ; 'P'
0x180019e36  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__L2Manager__ProcessChangesFromWwanPlugin____3____lambda_1___
0x180019e3b  nop
0x180019e3c  test    rdi, rdi
0x180019e3f  jz      short loc_180019E4A
0x180019e41  mov     rcx, rdi; lpCriticalSection
0x180019e44  call    cs:__imp_LeaveCriticalSection
0x180019e4a  lock inc qword ptr [rbx+1D0h]
0x180019e52  mov     rcx, [rbx+1C8h]; pwk
0x180019e59  call    cs:__imp_SubmitThreadpoolWork
0x180019e5f  nop
0x180019e60  lea     rcx, [rsp+108h+var_A0]; void *
0x180019e65  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; std::pair<std::wstring,Marshal::UnmarshalError>::~pair<std::wstring,Marshal::UnmarshalError>(void)
0x180019e6a  lea     rcx, [rsp+108h+var_C0]; void *
0x180019e6f  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; std::pair<std::wstring,Marshal::UnmarshalError>::~pair<std::wstring,Marshal::UnmarshalError>(void)
0x180019e74  nop
0x180019e75  mov     rcx, [rsp+108h+var_38+8]; this
0x180019e7d  test    rcx, rcx
0x180019e80  jz      short loc_180019E88
0x180019e82  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180019e87  nop
0x180019e88  jmp     short $+2
0x180019e8a  mov     rcx, [rsp+108h+var_28]
0x180019e92  xor     rcx, rsp; StackCookie
0x180019e95  call    __security_check_cookie
0x180019e9a  mov     rbx, [rsp+108h+arg_18]
0x180019ea2  add     rsp, 0F0h
0x180019ea9  pop     r14
0x180019eab  pop     rdi
0x180019eac  pop     rsi
0x180019ead  retn
```
