# L2Manager::ProcessChangesFromWlanPlugin(_GUID const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &&,Sha256Hash const &,bool)

- ea: `0x18003ac5c`
- end: `0x18003add8`
- name: `?ProcessChangesFromWlanPlugin@L2Manager@@SAXAEBU_GUID@@$$QEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVSha256Hash@@_N@Z`
- size: `380`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180065508`

## callees

- `0x18000e190`
- `0x180015608`
- `0x18001ae28`
- `0x180021850`
- `0x18002bd40`
- `0x18003ac5c`
- `0x18003b010`
- `0x180090e44`
- `0x1800a88a0`
- `0x1801019fc`
- `0x180101aa0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ad2e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003ad2e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ad4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ad7d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ad4e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003ad7d`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003ad92`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18003ad92`

## string_xrefs

- `0x18003acde`: `onecore\net\netprofiles\service\src\l2manager\lib\l2manager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall L2Manager::ProcessChangesFromWlanPlugin(__int128 *a1, __int64 a2, __int128 *a3, char a4)
{
  __int64 v8; // rax
  __int64 v9; // r9
  __int64 v10; // rcx
  std::_Ref_count_base *v11; // rbx
  const char *v12; // r9
  int v13; // [rsp+20h] [rbp-C8h]
  std::_Ref_count_base *v14; // [rsp+30h] [rbp-B8h] BYREF
  __int128 v15; // [rsp+38h] [rbp-B0h]
  _BYTE v16[32]; // [rsp+48h] [rbp-A0h] BYREF
  __int128 v17; // [rsp+68h] [rbp-80h]
  __int128 v18; // [rsp+78h] [rbp-70h]
  char v19; // [rsp+88h] [rbp-60h]
  std::_Ref_count_base *v20[2]; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  try
  {
    v8 = std::wstring::wstring(v20, a2);
    LOBYTE(v9) = a4;
    StandbyMonitor::ProcessWlanPluginDataIndication(a1, v8, a3, v9);
    *(_OWORD *)v20 = 0;
    std::weak_ptr<L2Manager>::lock(v10, v20);
    v11 = v20[0];
    if ( !v20[0] )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x248,
        (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\l2manager.cpp",
        (const char *)0x8007045BLL,
        v13);
    v14 = v20[0];
    v15 = *a1;
    std::wstring::wstring(v16, a2);
    v17 = *a3;
    v18 = a3[1];
    v19 = a4;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 336));
    if ( *((_BYTE *)v11 + 600) )
    {
      if ( v11 != (std::_Ref_count_base *)-336LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 336));
    }
    else
    {
      if ( *((_DWORD *)v11 + 82) == 1 )
        std::deque_std::function_void___cdecl_void___std::allocator_std::function_void___cdecl_void______::emplace_back__L2Manager::ProcessChangesFromWlanPlugin_::_3_::_lambda_1___(
          (char *)v11 + 480,
          &v14);
      else
        std::deque_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult____std::allocator_std::variant_std::function_void___cdecl_void___std::shared_ptr_WcmCommon::BaseThreadPoolWaitableResult_______::emplace_back__L2Manager::ProcessChangesFromWlanPlugin_::_3_::_lambda_1___(
          (char *)v11 + 560,
          &v14);
      if ( v11 != (std::_Ref_count_base *)-336LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v11 + 336));
      _InterlockedIncrement64((volatile signed __int64 *)v11 + 58);
      SubmitThreadpoolWork(*((PTP_WORK *)v11 + 57));
    }
    std::pair<std::wstring,enum Marshal::UnmarshalError>::~pair<std::wstring,enum Marshal::UnmarshalError>(v16);
    if ( v20[1] )
      std::_Ref_count_base::_Decref(v20[1]);
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x25A,
      (unsigned int)"onecore\\net\\netprofiles\\service\\src\\l2manager\\lib\\l2manager.cpp",
      v12);
  }
}

```

## disassembly

```asm
0x18003ac5c  mov     r11, rsp
0x18003ac5f  push    rbx
0x18003ac60  push    rsi
0x18003ac61  push    rdi
0x18003ac62  push    r14
0x18003ac64  push    r15
0x18003ac66  sub     rsp, 0C0h
0x18003ac6d  mov     rax, cs:__security_cookie
0x18003ac74  xor     rax, rsp
0x18003ac77  mov     [rsp+0E8h+var_38], rax
0x18003ac7f  mov     r15b, r9b
0x18003ac82  mov     rsi, r8
0x18003ac85  mov     rdi, rdx
0x18003ac88  mov     r14, rcx
0x18003ac8b  lea     rcx, [r11-58h]
0x18003ac8f  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18003ac94  mov     r9b, r15b
0x18003ac97  mov     r8, rsi
0x18003ac9a  mov     rdx, rax
0x18003ac9d  mov     rcx, r14
0x18003aca0  call    ?ProcessWlanPluginDataIndication@StandbyMonitor@@YAXAEBU_GUID@@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBVSha256Hash@@_N@Z; StandbyMonitor::ProcessWlanPluginDataIndication(_GUID const &,std::wstring,Sha256Hash const &,bool)
0x18003aca5  xorps   xmm0, xmm0
0x18003aca8  movups  xmmword ptr [rsp+0E8h+var_58], xmm0
0x18003acb0  lea     rdx, [rsp+0E8h+var_58]
0x18003acb8  call    ?lock@?$weak_ptr@VL2Manager@@@std@@QEBA?AV?$shared_ptr@VL2Manager@@@2@XZ; std::weak_ptr<L2Manager>::lock(void)
0x18003acbd  nop
0x18003acbe  mov     rbx, [rsp+0E8h+var_58]
0x18003acc6  test    rbx, rbx
0x18003acc9  setz    al
0x18003accc  mov     rcx, [rsp+0E8h]; this
0x18003acd4  test    al, al
0x18003acd6  jz      short loc_18003ACEF
0x18003acd8  mov     r9d, 8007045Bh; char *
0x18003acde  lea     r8, aOnecoreNetNetp_55; "onecore\\net\\netprofiles\\service\\src"...
0x18003ace5  mov     edx, 248h; void *
0x18003acea  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18003acef  mov     [rsp+0E8h+var_B8], rbx
0x18003acf4  movups  xmm0, xmmword ptr [r14]
0x18003acf8  movdqu  [rsp+0E8h+var_B0], xmm0
0x18003acfe  mov     rdx, rdi
0x18003ad01  lea     rcx, [rsp+0E8h+var_A0]
0x18003ad06  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18003ad0b  movups  xmm2, xmmword ptr [rsi]
0x18003ad0e  movups  [rsp+0E8h+var_80], xmm2
0x18003ad13  movups  xmm0, xmmword ptr [rsi+10h]
0x18003ad17  movups  [rsp+0E8h+var_70], xmm0
0x18003ad1c  mov     [rsp+0E8h+var_60], r15b
0x18003ad24  lea     rdi, [rbx+150h]
0x18003ad2b  mov     rcx, rdi; lpCriticalSection
0x18003ad2e  call    cs:__imp_EnterCriticalSection
0x18003ad34  mov     qword ptr [rsp+0E8h+var_C8], rdi
0x18003ad39  lea     rcx, [rbx+1E0h]
0x18003ad40  cmp     byte ptr [rcx+78h], 0
0x18003ad44  jz      short loc_18003AD56
0x18003ad46  test    rdi, rdi
0x18003ad49  jz      short loc_18003AD99
0x18003ad4b  mov     rcx, rdi; lpCriticalSection
0x18003ad4e  call    cs:__imp_LeaveCriticalSection
0x18003ad54  jmp     short loc_18003AD99
0x18003ad56  lea     rdx, [rsp+0E8h+var_B8]
0x18003ad5b  cmp     dword ptr [rbx+148h], 1
0x18003ad62  jnz     short loc_18003AD6B
0x18003ad64  call    std__deque_std__function_void___cdecl_void___std__allocator_std__function_void___cdecl_void________emplace_back__L2Manager__ProcessChangesFromWlanPlugin____3____lambda_1___
0x18003ad69  jmp     short loc_18003AD75
0x18003ad6b  add     rcx, 50h ; 'P'
0x18003ad6f  call    std__deque_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult____std__allocator_std__variant_std__function_void___cdecl_void___std__shared_ptr_WcmCommon__BaseThreadPoolWaitableResult_________emplace_back__L2Manager__ProcessChangesFromWlanPlugin____3____lambda_1___
0x18003ad74  nop
0x18003ad75  test    rdi, rdi
0x18003ad78  jz      short loc_18003AD83
0x18003ad7a  mov     rcx, rdi; lpCriticalSection
0x18003ad7d  call    cs:__imp_LeaveCriticalSection
0x18003ad83  lock inc qword ptr [rbx+1D0h]
0x18003ad8b  mov     rcx, [rbx+1C8h]; pwk
0x18003ad92  call    cs:__imp_SubmitThreadpoolWork
0x18003ad98  nop
0x18003ad99  lea     rcx, [rsp+0E8h+var_A0]; void *
0x18003ad9e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@W4UnmarshalError@Marshal@@@std@@QEAA@XZ; std::pair<std::wstring,Marshal::UnmarshalError>::~pair<std::wstring,Marshal::UnmarshalError>(void)
0x18003ada3  nop
0x18003ada4  mov     rcx, [rsp+0E8h+var_58+8]; this
0x18003adac  test    rcx, rcx
0x18003adaf  jz      short loc_18003ADB7
0x18003adb1  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18003adb6  nop
0x18003adb7  jmp     short $+2
0x18003adb9  mov     rcx, [rsp+0E8h+var_38]
0x18003adc1  xor     rcx, rsp; StackCookie
0x18003adc4  call    __security_check_cookie
0x18003adc9  add     rsp, 0C0h
0x18003add0  pop     r15
0x18003add2  pop     r14
0x18003add4  pop     rdi
0x18003add5  pop     rsi
0x18003add6  pop     rbx
0x18003add7  retn
```
