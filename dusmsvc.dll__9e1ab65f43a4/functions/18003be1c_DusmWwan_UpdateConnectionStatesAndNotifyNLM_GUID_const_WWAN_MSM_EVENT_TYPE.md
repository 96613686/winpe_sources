# DusmWwan::UpdateConnectionStatesAndNotifyNLM(_GUID const &,WWAN_MSM_EVENT_TYPE)

- ea: `0x18003be1c`
- end: `0x18003c1b3`
- name: `?UpdateConnectionStatesAndNotifyNLM@DusmWwan@@AEBAXAEBU_GUID@@W4WWAN_MSM_EVENT_TYPE@@@Z`
- size: `919`
- prototype: ``
- caller_count: `3`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180039cd8`
- `0x18003b814`
- `0x18003c1c0`

## callees

- `0x1800068fc`
- `0x180007c90`
- `0x18000e828`
- `0x18000f094`
- `0x180012368`
- `0x180013114`
- `0x180013444`
- `0x18001db50`
- `0x18002f510`
- `0x180039418`
- `0x18003974c`
- `0x1800397b4`
- `0x18003adf0`
- `0x18003be1c`
- `0x180043f48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003be6f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003be6f`
- `wwapi!WwanQueryInterface` at `0x18003bede`
- `wwapi!WwanQueryInterface` at `0x18003bede`
- `wwapi!WwanFreeMemory` at `0x18003c15d`
- `wwapi!WwanFreeMemory` at `0x18003c182`
- `wwapi!WwanFreeMemory` at `0x18003c15d`
- `wwapi!WwanFreeMemory` at `0x18003c182`

## string_xrefs

- `0x18003beee`: `DusmWwan::UpdateConnectionStatesAndNotifyNLM::WwanQueryInterface`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall DusmWwan::UpdateConnectionStatesAndNotifyNLM(__int64 a1, __int128 *a2, int a3)
{
  __int64 v6; // rbx
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // rsi
  __int64 *v10; // rax
  __int64 v11; // rcx
  unsigned int Interface; // eax
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 v15; // rdi
  __int64 v16; // rax
  int *v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rdx
  _DWORD *v22; // r8
  __int64 v23; // r9
  int *v24; // rcx
  bool v25; // zf
  __int64 result; // rax
  __int64 v27; // rcx
  bool v28; // [rsp+50h] [rbp-B0h] BYREF
  int v29; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  __int64 v33; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h] BYREF
  __int64 *v35; // [rsp+80h] [rbp-80h] BYREF
  char v36[8]; // [rsp+88h] [rbp-78h] BYREF
  char v37; // [rsp+90h] [rbp-70h]
  __int128 v38; // [rsp+A0h] [rbp-60h] BYREF
  int v39; // [rsp+B0h] [rbp-50h]
  int v40; // [rsp+B4h] [rbp-4Ch]
  __int128 v41; // [rsp+B8h] [rbp-48h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  __int64 v43; // [rsp+D0h] [rbp-30h]
  __int128 v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E8h] [rbp-18h]
  __int64 v46; // [rsp+F0h] [rbp-10h]
  int v47; // [rsp+F8h] [rbp-8h]
  __int64 (__fastcall **v48)(); // [rsp+100h] [rbp+0h] BYREF
  __int128 v49; // [rsp+108h] [rbp+8h]
  __int64 (__fastcall ***v50)(); // [rsp+138h] [rbp+38h]
  _BYTE v51[64]; // [rsp+140h] [rbp+40h] BYREF
  int *v52; // [rsp+180h] [rbp+80h] BYREF
  __int64 v53; // [rsp+188h] [rbp+88h] BYREF
  int v54; // [rsp+190h] [rbp+90h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+C8h]

  v53 = 0;
  v54 = 0;
  v6 = a1 + 24;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 24));
  v30 = v6;
  v8 = *(_QWORD **)(a1 + 64);
  v9 = -1;
  if ( !v8 || *v8 == -1 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v7);
  v35 = &v53;
  *(_QWORD *)v36 = 0;
  v37 = 1;
  v10 = *(__int64 **)(a1 + 64);
  if ( v10 )
    v11 = *v10;
  else
    v11 = -1;
  Interface = WwanQueryInterface(v11, a2, 3);
  wil::details::in1diag3::Throw_IfWin32ErrorMsg(
    retaddr,
    (void *)0x25B,
    (unsigned int)"onecoreuap\\net\\dusm\\lib\\dusmwwan.cpp",
    (const char *)Interface,
    (unsigned int)"DusmWwan::UpdateConnectionStatesAndNotifyNLM::WwanQueryInterface",
    v36);
  wil::details::out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>::~out_param_ptr_t<unsigned char * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&void WwanFreeMemory(void *)>>>(&v35);
  DusmWwan::QueryWwanSubscriberInfo(v13, &v52, a2);
  v14 = v53;
  v15 = std::wstring::wstring((__int64)&v48, (__int64)(v52 + 10));
  v16 = std::wstring::wstring((__int64)&v35, (__int64)(v52 + 2));
  v17 = v52;
  v38 = *a2;
  v39 = *(_DWORD *)(v14 + 4);
  v40 = *(_DWORD *)(v14 + 12);
  v41 = 0;
  v41 = *(_OWORD *)v15;
  v42 = *(_QWORD *)(v15 + 16);
  v43 = *(_QWORD *)(v15 + 24);
  *(_QWORD *)(v15 + 24) = 7;
  *(_WORD *)v15 = 0;
  *(_QWORD *)(v15 + 16) = 0;
  v44 = 0;
  v44 = *(_OWORD *)v16;
  v45 = *(_QWORD *)(v16 + 16);
  v46 = *(_QWORD *)(v16 + 24);
  *(_WORD *)v16 = 0;
  *(_QWORD *)(v16 + 16) = 0;
  *(_QWORD *)(v16 + 24) = 7;
  v47 = *v17;
  std::function_void___cdecl_void__::function_void___cdecl_void____DusmWwan::UpdateConnectionStatesAndNotifyNLM_::_2_::_lambda_1__0_(
    v51,
    &v38);
  DusmAsync::SubmitOrderedWork((__int64)v51);
  std::function<long (void)>::~function<long (void)>((__int64)v51, v18);
  DusmWwan::UpdateConnectionStatesAndNotifyNLM_::_2_::_lambda_1_::__lambda_1_(&v38);
  std::wstring::_Tidy_deallocate(&v35);
  std::wstring::_Tidy_deallocate(&v48);
  if ( *(_DWORD *)(v53 + 4) == 9
    || a3 == 49
    || a3 == 10
    || a3 == 6 && (v20 = (unsigned int)(*(_DWORD *)(v53 + 12) - 3), (unsigned int)v20 <= 2) )
  {
    if ( *v52 != 1 )
      goto LABEL_19;
    v20 = -1;
    do
      ++v20;
    while ( *((_WORD *)v52 + v20 + 20) );
    if ( !v20 )
      goto LABEL_19;
    do
      ++v9;
    while ( *((_WORD *)v52 + v9 + 4) );
    if ( v9 )
    {
      v48 = off_18004CC98;
      v49 = *a2;
      v50 = &v48;
      DusmAsync::SubmitOrderedWork((__int64)&v48);
      std::function<long (void)>::~function<long (void)>((__int64)&v48, v21);
    }
    else
    {
LABEL_19:
      v22 = *(_DWORD **)(wil::details::static_lazy<DusmTraceLoggingProvider>::get(v20, v19) + 8);
      if ( *v22 > 3u )
      {
        v31 = (__int64)"WwanNotificationSourceMsm";
        v29 = a3;
        v28 = *v52 == 1;
        v32 = (__int64)(v52 + 2);
        v33 = (__int64)(v52 + 10);
        v34 = (__int64)a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          (int)v22,
          (int)&byte_18005A6E9,
          (__int64)v22,
          v23,
          &v34,
          (const WCHAR **)&v33,
          (const WCHAR **)&v32,
          (__int64)&v28,
          (__int64)&v29,
          (const wchar_t **)&v31);
      }
    }
  }
  v24 = v52;
  v25 = v52 == 0;
  v52 = 0;
  if ( !v25 )
    WwanFreeMemory(v24);
  result = wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v30);
  v27 = v53;
  v25 = v53 == 0;
  v53 = 0;
  if ( !v25 )
    return WwanFreeMemory(v27);
  return result;
}

```

## disassembly

```asm
0x18003be1c  mov     [rsp-8+arg_10], rbx
0x18003be21  mov     [rsp-8+arg_18], rsi
0x18003be26  push    rbp
0x18003be27  push    rdi
0x18003be28  push    r12
0x18003be2a  push    r14
0x18003be2c  push    r15
0x18003be2e  lea     rbp, [rsp-0A0h]
0x18003be36  sub     rsp, 1A0h
0x18003be3d  mov     rax, cs:__security_cookie
0x18003be44  xor     rax, rsp
0x18003be47  mov     [rbp+0C0h+var_28], rax
0x18003be4e  mov     r14d, r8d
0x18003be51  mov     r15, rdx
0x18003be54  mov     rdi, rcx
0x18003be57  xor     r12d, r12d
0x18003be5a  mov     [rbp+0C0h+var_38], r12
0x18003be61  mov     [rbp+0C0h+var_30], r12d
0x18003be68  lea     rbx, [rcx+18h]
0x18003be6c  mov     rcx, rbx; lpCriticalSection
0x18003be6f  call    cs:__imp_EnterCriticalSection
0x18003be75  mov     [rsp+1C0h+var_168], rbx
0x18003be7a  mov     rax, [rdi+40h]
0x18003be7e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18003be82  test    rax, rax
0x18003be85  jz      short loc_18003BE8C
0x18003be87  cmp     [rax], rsi
0x18003be8a  jnz     short loc_18003BE91
0x18003be8c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18003be91  lea     rax, [rbp+0C0h+var_38]
0x18003be98  mov     [rbp+0C0h+var_140], rax
0x18003be9c  mov     qword ptr [rbp+0C0h+var_138], r12
0x18003bea0  mov     [rbp+0C0h+var_130], 1
0x18003bea4  mov     rax, [rdi+40h]
0x18003bea8  test    rax, rax
0x18003beab  jz      short loc_18003BEB2
0x18003bead  mov     rcx, [rax]
0x18003beb0  jmp     short loc_18003BEB5
0x18003beb2  mov     rcx, rsi
0x18003beb5  mov     [rsp+1C0h+var_188], r12
0x18003beba  mov     [rsp+1C0h+var_190], r12
0x18003bebf  lea     rax, [rbp+0C0h+var_138]
0x18003bec3  mov     [rsp+1C0h+var_198], rax; char *
0x18003bec8  lea     rax, [rbp+0C0h+var_30]
0x18003becf  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18003bed4  xor     r9d, r9d
0x18003bed7  lea     r8d, [r9+3]
0x18003bedb  mov     rdx, r15
0x18003bede  call    cs:__imp_WwanQueryInterface
0x18003bee4  mov     r9d, eax; char *
0x18003bee7  mov     rcx, [rbp+0C8h]; this
0x18003beee  lea     rax, aDusmwwanUpdate; "DusmWwan::UpdateConnectionStatesAndNoti"...
0x18003bef5  mov     qword ptr [rsp+1C0h+var_1A0], rax; unsigned int
0x18003befa  lea     r8, aOnecoreuapNetD_6; "onecoreuap\\net\\dusm\\lib\\dusmwwan.cp"...
0x18003bf01  mov     edx, 25Bh; void *
0x18003bf06  call    ?Throw_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Throw_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18003bf0b  nop
0x18003bf0c  lea     rcx, [rbp+0C0h+var_140]
0x18003bf10  call    ??1?$out_param_ptr_t@PEAPEAEV?$unique_ptr@UWWAN_INTERFACE_OBJECT@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>::~out_param_ptr_t<uchar * *,wistd::unique_ptr<WWAN_INTERFACE_OBJECT,wil::function_deleter<void (*)(void *),&WwanFreeMemory(void *)>>>(void)
0x18003bf15  mov     r8, r15
0x18003bf18  lea     rdx, [rbp+0C0h+var_40]
0x18003bf1f  call    ?QueryWwanSubscriberInfo@DusmWwan@@AEBA?AV?$unique_ptr@UWWAN_SUBSCRIBER_INFORMATION@@U?$function_deleter@P6AXPEAX@Z$1?WwanFreeMemory@@YAX0@Z@wil@@@wistd@@AEBU_GUID@@@Z; DusmWwan::QueryWwanSubscriberInfo(_GUID const &)
0x18003bf24  nop
0x18003bf25  mov     rbx, [rbp+0C0h+var_38]
0x18003bf2c  mov     rdx, [rbp+0C0h+var_40]
0x18003bf33  add     rdx, 28h ; '('
0x18003bf37  lea     rcx, [rbp+0C0h+var_C0]
0x18003bf3b  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003bf40  mov     rdi, rax
0x18003bf43  mov     rdx, [rbp+0C0h+var_40]
0x18003bf4a  add     rdx, 8
0x18003bf4e  lea     rcx, [rbp+0C0h+var_140]
0x18003bf52  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@QEB_W@Z; std::wstring::wstring(wchar_t const * const)
0x18003bf57  mov     r8, rax
0x18003bf5a  mov     rdx, [rbp+0C0h+var_40]
0x18003bf61  movups  xmm0, xmmword ptr [r15]
0x18003bf65  movdqu  [rbp+0C0h+var_120], xmm0
0x18003bf6a  mov     ecx, [rbx+4]
0x18003bf6d  mov     [rbp+0C0h+var_110], ecx
0x18003bf70  mov     ecx, [rbx+0Ch]
0x18003bf73  mov     [rbp+0C0h+var_10C], ecx
0x18003bf76  xorps   xmm0, xmm0
0x18003bf79  movups  [rbp+0C0h+var_108], xmm0
0x18003bf7d  mov     rcx, [rdi]
0x18003bf80  mov     qword ptr [rbp+0C0h+var_108], rcx
0x18003bf84  mov     rax, [rdi+8]
0x18003bf88  mov     qword ptr [rbp+0C0h+var_108+8], rax
0x18003bf8c  mov     rax, [rdi+10h]
0x18003bf90  mov     [rbp+0C0h+var_F8], rax
0x18003bf94  mov     rax, [rdi+18h]
0x18003bf98  mov     [rbp+0C0h+var_F0], rax
0x18003bf9c  mov     ecx, 7
0x18003bfa1  mov     [rdi+18h], rcx
0x18003bfa5  mov     [rdi], r12w
0x18003bfa9  mov     [rdi+10h], r12
0x18003bfad  movups  [rbp+0C0h+var_E8], xmm0
0x18003bfb1  mov     rax, [r8]
0x18003bfb4  mov     qword ptr [rbp+0C0h+var_E8], rax
0x18003bfb8  mov     rax, [r8+8]
0x18003bfbc  mov     qword ptr [rbp+0C0h+var_E8+8], rax
0x18003bfc0  mov     rax, [r8+10h]
0x18003bfc4  mov     [rbp+0C0h+var_D8], rax
0x18003bfc8  mov     rax, [r8+18h]
0x18003bfcc  mov     [rbp+0C0h+var_D0], rax
0x18003bfd0  mov     [r8], r12w
0x18003bfd4  mov     [r8+10h], r12
0x18003bfd8  mov     [r8+18h], rcx
0x18003bfdc  mov     eax, [rdx]
0x18003bfde  mov     [rbp+0C0h+var_C8], eax
0x18003bfe1  lea     rdx, [rbp+0C0h+var_120]
0x18003bfe5  lea     rcx, [rbp+0C0h+var_80]
0x18003bfe9  call    std__function_void___cdecl_void____function_void___cdecl_void____DusmWwan__UpdateConnectionStatesAndNotifyNLM____2____lambda_1__0_
0x18003bfee  lea     rcx, [rbp+0C0h+var_80]
0x18003bff2  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x18003bff7  lea     rcx, [rbp+0C0h+var_80]
0x18003bffb  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18003c000  nop
0x18003c001  lea     rcx, [rbp+0C0h+var_120]
0x18003c005  call    _DusmWwan__UpdateConnectionStatesAndNotifyNLM____2____lambda_1_____lambda_1_
0x18003c00a  nop
0x18003c00b  lea     rcx, [rbp+0C0h+var_140]
0x18003c00f  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c014  nop
0x18003c015  lea     rcx, [rbp+0C0h+var_C0]
0x18003c019  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003c01e  mov     rax, [rbp+0C0h+var_38]
0x18003c025  cmp     dword ptr [rax+4], 9
0x18003c029  jz      short loc_18003C050
0x18003c02b  cmp     r14d, 31h ; '1'
0x18003c02f  jz      short loc_18003C050
0x18003c031  cmp     r14d, 0Ah
0x18003c035  jz      short loc_18003C050
0x18003c037  cmp     r14d, 6
0x18003c03b  jnz     loc_18003C14A
0x18003c041  mov     ecx, [rax+0Ch]
0x18003c044  sub     ecx, 3
0x18003c047  cmp     ecx, 2
0x18003c04a  ja      loc_18003C14A
0x18003c050  mov     rax, [rbp+0C0h+var_40]
0x18003c057  cmp     dword ptr [rax], 1
0x18003c05a  jnz     short loc_18003C0B2
0x18003c05c  mov     rcx, rsi
0x18003c05f  inc     rcx
0x18003c062  cmp     [rax+rcx*2+28h], r12w
0x18003c068  jnz     short loc_18003C05F
0x18003c06a  test    rcx, rcx
0x18003c06d  jz      short loc_18003C0B2
0x18003c06f  inc     rsi
0x18003c072  cmp     [rax+rsi*2+8], r12w
0x18003c078  jnz     short loc_18003C06F
0x18003c07a  test    rsi, rsi
0x18003c07d  jz      short loc_18003C0B2
0x18003c07f  lea     rax, off_18004CC98
0x18003c086  mov     [rbp+0C0h+var_C0], rax
0x18003c08a  movups  xmm0, xmmword ptr [r15]
0x18003c08e  movdqu  [rbp+0C0h+var_B8], xmm0
0x18003c093  lea     rax, [rbp+0C0h+var_C0]
0x18003c097  mov     [rbp+0C0h+var_88], rax
0x18003c09b  lea     rcx, [rbp+0C0h+var_C0]
0x18003c09f  call    ?SubmitOrderedWork@DusmAsync@@SAX$$QEAV?$function@$$A6AXXZ@std@@@Z; DusmAsync::SubmitOrderedWork(std::function<void (void)> &&)
0x18003c0a4  lea     rcx, [rbp+0C0h+var_C0]
0x18003c0a8  call    ??1?$function@$$A6AJXZ@std@@QEAA@XZ; std::function<long (void)>::~function<long (void)>(void)
0x18003c0ad  jmp     loc_18003C14A
0x18003c0b2  call    ?get@?$static_lazy@VDusmTraceLoggingProvider@@@details@wil@@QEAAPEAVDusmTraceLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<DusmTraceLoggingProvider>::get(void (*)(void))
0x18003c0b7  mov     r8, [rax+8]
0x18003c0bb  mov     eax, [r8]
0x18003c0be  cmp     eax, 3
0x18003c0c1  jbe     loc_18003C14A
0x18003c0c7  lea     rax, aWwannotificati; "WwanNotificationSourceMsm"
0x18003c0ce  mov     [rsp+1C0h+var_160], rax
0x18003c0d3  mov     dword ptr [rsp+1C0h+var_170+4], r14d
0x18003c0d8  mov     rax, [rbp+0C0h+var_40]
0x18003c0df  cmp     dword ptr [rax], 1
0x18003c0e2  setz    byte ptr [rsp+1C0h+var_170]
0x18003c0e7  lea     rcx, [rax+8]
0x18003c0eb  mov     [rsp+1C0h+var_158], rcx
0x18003c0f0  add     rax, 28h ; '('
0x18003c0f4  mov     [rsp+1C0h+var_150], rax
0x18003c0f9  mov     [rsp+1C0h+var_148], r15
0x18003c0fe  lea     rax, [rsp+1C0h+var_160]
0x18003c103  mov     [rsp+1C0h+var_178], rax; __int64
0x18003c108  lea     rax, [rsp+1C0h+var_170+4]
0x18003c10d  mov     [rsp+1C0h+var_180], rax; __int64
0x18003c112  lea     rax, [rsp+1C0h+var_170]
0x18003c117  mov     [rsp+1C0h+var_188], rax; __int64
0x18003c11c  lea     rax, [rsp+1C0h+var_158]
0x18003c121  mov     [rsp+1C0h+var_190], rax; __int64
0x18003c126  lea     rax, [rsp+1C0h+var_150]
0x18003c12b  mov     [rsp+1C0h+var_198], rax; __int64
0x18003c130  lea     rax, [rsp+1C0h+var_148]
0x18003c135  mov     qword ptr [rsp+1C0h+var_1A0], rax; __int64
0x18003c13a  lea     rdx, byte_18005A6E9; int
0x18003c141  mov     rcx, r8; int
0x18003c144  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@_W@@U2@U?$_tlgWrapperByVal@$00@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@_W@@4AEBU?$_tlgWrapperByVal@$00@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18003c149  nop
0x18003c14a  mov     rcx, [rbp+0C0h+var_40]
0x18003c151  test    rcx, rcx
0x18003c154  mov     [rbp+0C0h+var_40], r12
0x18003c15b  jz      short loc_18003C164
0x18003c15d  call    cs:__imp_WwanFreeMemory
0x18003c163  nop
0x18003c164  lea     rcx, [rsp+1C0h+var_168]
0x18003c169  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18003c16e  nop
0x18003c16f  mov     rcx, [rbp+0C0h+var_38]
0x18003c176  test    rcx, rcx
0x18003c179  mov     [rbp+0C0h+var_38], r12
0x18003c180  jz      short loc_18003C188
0x18003c182  call    cs:__imp_WwanFreeMemory
0x18003c188  mov     rcx, [rbp+0C0h+var_28]
0x18003c18f  xor     rcx, rsp; StackCookie
0x18003c192  call    __security_check_cookie
0x18003c197  lea     r11, [rsp+1C0h+var_20]
0x18003c19f  mov     rbx, [r11+40h]
0x18003c1a3  mov     rsi, [r11+48h]
0x18003c1a7  mov     rsp, r11
0x18003c1aa  pop     r15
0x18003c1ac  pop     r14
0x18003c1ae  pop     r12
0x18003c1b0  pop     rdi
0x18003c1b1  pop     rbp
0x18003c1b2  retn
```
