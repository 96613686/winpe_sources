# CapabilityAccessHelper::RuntimeClassInitialize(ThreadProcHelper *)

- ea: `0x1800440d0`
- end: `0x1800443c8`
- name: `?RuntimeClassInitialize@CapabilityAccessHelper@@QEAAJPEAVThreadProcHelper@@@Z`
- size: `760`
- prototype: `__int64 __fastcall(CapabilityAccessHelper *__hidden this, struct ThreadProcHelper *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180042b4c`

## callees

- `0x180007b14`
- `0x1800081e4`
- `0x18001597c`
- `0x180015f20`
- `0x180018874`
- `0x18001c9e0`
- `0x18001f620`
- `0x18001f644`
- `0x1800429ec`
- `0x18004369c`
- `0x180043d18`
- `0x1800440d0`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180044199`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180044199`

## string_xrefs

- `0x180044176`: `Windows.Security.Authorization.AppCapabilityAccess.AppCapability`
- `0x180044106`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\capabilityaccesshelper.cpp`
- `0x180044222`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\capabilityaccesshelper.cpp`
- `0x1800442d2`: `multimedia\dshow\filters.ks\ksproxy\capabilityhelpers\lib\capabilityaccesshelper.cpp`

## pseudocode

```c
__int64 __fastcall CapabilityAccessHelper::RuntimeClassInitialize(
        CapabilityAccessHelper *this,
        struct ThreadProcHelper *a2)
{
  int v4; // ebx
  char *v5; // r12
  __int64 v6; // rcx
  int ActivationFactory; // eax
  __int64 v8; // rdx
  _QWORD *v9; // rbx
  _QWORD *v10; // rsi
  __int64 v11; // rcx
  __int64 v12; // rax
  __int64 (__fastcall *v13)(_QWORD *, HSTRING__ *, char *); // r15
  __int64 v14; // r9
  __int64 v15; // rdx
  unsigned __int64 v16; // r9
  __int64 *v17; // rdi
  void *v18; // rax
  __int64 v19; // rbx
  int v20; // eax
  __int64 v22; // [rsp+20h] [rbp-50h] BYREF
  void *v23; // [rsp+28h] [rbp-48h] BYREF
  _QWORD *v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h] BYREF
  Microsoft::WRL::Wrappers::HStringReference v26; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( a2 )
  {
    v5 = (char *)this + 128;
    v24 = 0;
    *((_QWORD *)this + 16) = 0;
    v25 = 0;
    wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=((__int64 *)this + 14, (__int64)a2);
    v6 = (__int64)v24;
    v24 = 0;
    if ( v6 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    v26.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &v26,
      L"Windows.Security.Authorization.AppCapabilityAccess.AppCapability",
      0x41u,
      0x40u);
    ActivationFactory = RoGetActivationFactory(v26.hstr_, &GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22, &v24);
    v4 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v8 = 30;
LABEL_11:
      v14 = (unsigned int)ActivationFactory;
LABEL_12:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityaccesshelper.cpp",
        (const char *)v14);
LABEL_30:
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v25);
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v24);
      return (unsigned int)v4;
    }
    v9 = v24;
    v10 = (_QWORD *)((char *)this + 120);
    v11 = *((_QWORD *)this + 15);
    v12 = *v24;
    *((_QWORD *)this + 15) = 0;
    v13 = *(__int64 (__fastcall **)(_QWORD *, HSTRING__ *, char *))(v12 + 64);
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v26.hstr_ = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(&v26, L"webcam", 7u, 6u);
    ActivationFactory = v13(v9, v26.hstr_, (char *)this + 120);
    v4 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v8 = 32;
      goto LABEL_11;
    }
    ActivationFactory = (*(__int64 (__fastcall **)(_QWORD, char *))(*(_QWORD *)*v10 + 72LL))(*v10, (char *)this + 136);
    v4 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      v8 = 35;
      goto LABEL_11;
    }
    if ( *((_DWORD *)this + 34) != 4 )
    {
      v4 = -2147024891;
      v8 = 36;
      v14 = 2147942405LL;
      goto LABEL_12;
    }
    ThreadProcHelper::UpdateCapabilityState((__int64)a2, 4);
    v22 = 0;
    v23 = 0;
    v4 = Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>>(
           (__int64)this,
           &GUID_00000038_0000_0000_c000_000000000046,
           &v23);
    if ( v4 >= 0 )
      v4 = (*(__int64 (__fastcall **)(void *, __int64 *))(*(_QWORD *)v23 + 24LL))(v23, &v22);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v23);
    if ( v4 >= 0 )
    {
      v17 = lambda_32f1db981d03e860ebaed49377ad9295_::_lambda_32f1db981d03e860ebaed49377ad9295_(
              (__int64 *)&v26,
              &v22,
              (__int64)this);
      v18 = operator new(0x50u, &std::nothrow);
      v19 = 0;
      v23 = v18;
      if ( v18 )
      {
        v19 = Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::Security::Authorization::AppCapabilityAccess::AppCapability___Windows::Security::Authorization::AppCapabilityAccess::IAppCapability____Windows::Foundation::Internal::AggregateType_Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs___Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityAccessChangedEventArgs_____::___Windows::Security::Authorization::AppCapabilityAccess::IAppCapability___Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityAccessChangedEventArgs____::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::Security::Authorization::AppCapabilityAccess::AppCapability___Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs____Microsoft::WRL::FtmBase___lambda_32f1db981d03e860ebaed49377ad9295___1_Windows::Security::Authorization::AppCapabilityAccess::IAppCapability___Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityAccessChangedEventArgs___::DelegateInvokeHelper_Microsoft::WRL::Implements_Microsoft::WRL::RuntimeClassFlags_2__Windows::Foundation::ITypedEventHandler_Windows::Security::Authorization::AppCapabilityAccess::AppCapability___Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessChangedEventArgs____Microsoft::WRL::FtmBase___lambda_32f1db981d03e860ebaed49377ad9295___1_Windows::Security::Authorization::AppCapabilityAccess::IAppCapability___Windows::Security::Authorization::AppCapabilityAccess::IAppCapabilityAccessChangedEventArgs___(
                (__int64)v18,
                v17);
        v23 = 0;
      }
      Microsoft::WRL::Details::MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____::_MakeAllocator_Windows::Internal::ComTaskPool::CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____(&v23);
      v25 = v19;
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>((__int64 *)&v26);
      if ( v19 )
      {
        v20 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v10 + 80LL))(*v10, v19, v5);
        v4 = v20;
        if ( v20 >= 0 )
        {
          wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v22);
          v4 = 0;
          goto LABEL_30;
        }
        v16 = (unsigned int)v20;
        v15 = 74;
        goto LABEL_22;
      }
      v4 = -2147024882;
      v15 = 72;
    }
    else
    {
      v15 = 45;
    }
    v16 = (unsigned int)v4;
LABEL_22:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityaccesshelper.cpp",
      (const char *)v16);
    wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(&v22);
    goto LABEL_30;
  }
  v4 = -2147024809;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15,
    (int)"multimedia\\dshow\\filters.ks\\ksproxy\\capabilityhelpers\\lib\\capabilityaccesshelper.cpp",
    (const char *)0x80070057LL);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800440d0  mov     [rsp-28h+arg_10], rbx
0x1800440d5  mov     [rsp-28h+arg_18], rsi
0x1800440da  push    rbp
0x1800440db  push    rdi
0x1800440dc  push    r12
0x1800440de  push    r14
0x1800440e0  push    r15
0x1800440e2  mov     rbp, rsp
0x1800440e5  sub     rsp, 70h
0x1800440e9  mov     rax, cs:__security_cookie
0x1800440f0  xor     rax, rsp
0x1800440f3  mov     [rbp+var_10], rax
0x1800440f7  mov     r14, rdx
0x1800440fa  mov     rdi, rcx
0x1800440fd  test    rdx, rdx
0x180044100  jnz     short loc_180044123
0x180044102  mov     rcx, [rbp+28h]; this
0x180044106  lea     r8, aMultimediaDsho_4; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x18004410d  mov     ebx, 80070057h
0x180044112  lea     edx, [r14+15h]; void *
0x180044116  mov     r9d, ebx; char *
0x180044119  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004411e  jmp     loc_1800443A0
0x180044123  lea     r12, [rcx+80h]
0x18004412a  mov     [rbp+var_40], 0
0x180044132  add     rcx, 70h ; 'p'
0x180044136  mov     qword ptr [r12], 0
0x18004413e  mov     [rbp+var_38], 0
0x180044146  call    ??4?$com_ptr_t@VThreadProcHelper@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAVThreadProcHelper@@@Z; wil::com_ptr_t<ThreadProcHelper,wil::err_returncode_policy>::operator=(ThreadProcHelper *)
0x18004414b  mov     rcx, [rbp+var_40]
0x18004414f  mov     [rbp+var_40], 0
0x180044157  test    rcx, rcx
0x18004415a  jz      short loc_180044168
0x18004415c  mov     rax, [rcx]
0x18004415f  mov     rax, [rax+10h]
0x180044163  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044168  mov     r9d, 40h ; '@'; unsigned int
0x18004416e  mov     [rbp+var_30.hstr_], 0
0x180044176  lea     rdx, ?RuntimeClass_Windows_Security_Authorization_AppCapabilityAccess_AppCapability@@3QBGB; "Windows.Security.Authorization.AppCapab"...
0x18004417d  lea     rcx, [rbp+var_30]; this
0x180044181  lea     r8d, [r9+1]; unsigned int
0x180044185  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18004418a  mov     rcx, [rbp+var_30.hstr_]
0x18004418e  lea     r8, [rbp+var_40]
0x180044192  lea     rdx, _GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22
0x180044199  call    cs:__imp_RoGetActivationFactory
0x1800441a0  nop     dword ptr [rax+rax+00h]
0x1800441a5  mov     ebx, eax
0x1800441a7  test    eax, eax
0x1800441a9  jns     short loc_1800441B2
0x1800441ab  mov     edx, 1Eh
0x1800441b0  jmp     short loc_18004421B
0x1800441b2  mov     rbx, [rbp+var_40]
0x1800441b6  lea     rsi, [rdi+78h]
0x1800441ba  mov     rcx, [rsi]
0x1800441bd  mov     rax, [rbx]
0x1800441c0  mov     qword ptr [rsi], 0
0x1800441c7  mov     r15, [rax+40h]
0x1800441cb  test    rcx, rcx
0x1800441ce  jz      short loc_1800441DC
0x1800441d0  mov     rax, [rcx]
0x1800441d3  mov     rax, [rax+10h]
0x1800441d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800441dc  mov     r9d, 6; unsigned int
0x1800441e2  mov     [rbp+var_30.hstr_], 0
0x1800441ea  lea     rdx, sourceString; "webcam"
0x1800441f1  lea     rcx, [rbp+var_30]; this
0x1800441f5  lea     r8d, [r9+1]; unsigned int
0x1800441f9  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x1800441fe  mov     rdx, [rbp+var_30.hstr_]
0x180044202  mov     r8, rsi
0x180044205  mov     rcx, rbx
0x180044208  mov     rax, r15
0x18004420b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044210  mov     ebx, eax
0x180044212  test    eax, eax
0x180044214  jns     short loc_180044233
0x180044216  mov     edx, 20h ; ' '; void *
0x18004421b  mov     r9d, eax; char *
0x18004421e  mov     rcx, [rbp+28h]; this
0x180044222  lea     r8, aMultimediaDsho_4; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x180044229  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004422e  jmp     loc_18004438E
0x180044233  mov     rcx, [rsi]
0x180044236  lea     r15, [rdi+88h]
0x18004423d  mov     rdx, r15
0x180044240  mov     rax, [rcx]
0x180044243  mov     rax, [rax+48h]
0x180044247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004424c  mov     ebx, eax
0x18004424e  test    eax, eax
0x180044250  jns     short loc_180044259
0x180044252  mov     edx, 23h ; '#'
0x180044257  jmp     short loc_18004421B
0x180044259  mov     edx, 4
0x18004425e  cmp     [r15], edx
0x180044261  jz      short loc_180044272
0x180044263  mov     ebx, 80070005h
0x180044268  mov     edx, 24h ; '$'
0x18004426d  mov     r9d, ebx
0x180044270  jmp     short loc_18004421E
0x180044272  mov     rcx, r14
0x180044275  call    ?UpdateCapabilityState@ThreadProcHelper@@QEAAXW4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@Z; ThreadProcHelper::UpdateCapabilityState(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus)
0x18004427a  lea     r8, [rbp+var_48]
0x18004427e  mov     [rbp+var_50], 0
0x180044286  lea     rdx, _GUID_00000038_0000_0000_c000_000000000046
0x18004428d  mov     [rbp+var_48], 0
0x180044295  mov     rcx, rdi
0x180044298  call    ??$AsIID@V?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@Details@WRL@Microsoft@@@?$RuntimeClassBaseT@$02@Details@WRL@Microsoft@@KAJPEAV?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UICapabilityAccessHelper@@VFtmBase@23@@123@AEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::Details::RuntimeClassBaseT<3>::AsIID<Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase>>(Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,ICapabilityAccessHelper,Microsoft::WRL::FtmBase> *,_GUID const &,void * *)
0x18004429d  mov     ebx, eax
0x18004429f  test    eax, eax
0x1800442a1  js      short loc_1800442B9
0x1800442a3  mov     rcx, [rbp+var_48]
0x1800442a7  lea     rdx, [rbp+var_50]
0x1800442ab  mov     rax, [rcx]
0x1800442ae  mov     rax, [rax+18h]
0x1800442b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800442b7  mov     ebx, eax
0x1800442b9  lea     rcx, [rbp+var_48]
0x1800442bd  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x1800442c2  test    ebx, ebx
0x1800442c4  jns     short loc_1800442EC
0x1800442c6  mov     edx, 2Dh ; '-'; void *
0x1800442cb  mov     r9d, ebx; char *
0x1800442ce  mov     rcx, [rbp+28h]; this
0x1800442d2  lea     r8, aMultimediaDsho_4; "multimedia\\dshow\\filters.ks\\ksproxy"...
0x1800442d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800442de  lea     rcx, [rbp+var_50]
0x1800442e2  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x1800442e7  jmp     loc_18004438E
0x1800442ec  mov     r8, rdi
0x1800442ef  lea     rdx, [rbp+var_50]
0x1800442f3  lea     rcx, [rbp+var_30]
0x1800442f7  call    _lambda_32f1db981d03e860ebaed49377ad9295____lambda_32f1db981d03e860ebaed49377ad9295_
0x1800442fc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180044303  mov     ecx, 50h ; 'P'; unsigned __int64
0x180044308  mov     rdi, rax
0x18004430b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180044310  xor     ebx, ebx
0x180044312  mov     [rbp+var_48], rax
0x180044316  test    rax, rax
0x180044319  jz      short loc_180044331
0x18004431b  mov     rdx, rdi
0x18004431e  mov     rcx, rax
0x180044321  call    Microsoft__WRL__Details__DelegateArgTraits_long____cdecl_Windows__Foundation__ITypedEventHandler_impl_Windows__Foundation__Internal__AggregateType_Windows__Security__Authorization__AppCapabilityAccess__AppCapability___Windows__Security__Authorization__AppCapabilityAccess__IAppCapability____Windows__Foundation__Internal__AggregateType_Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessChangedEventArgs___Windows__Security__Authorization__AppCapabilityAccess__IAppCapabilityAccessChangedEventArgs__________Windows__Security__Authorization__AppCapabilityAccess__IAppCapability___Windows__Security__Authorization__AppCapabilityAccess__IAppCapabilityAccessChangedEventArgs______DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__Security__Authorization__AppCapabilityAccess__AppCapability___Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessChangedEventArgs____Microsoft__WRL__FtmBase___lambda_32f1db981d03e860ebaed49377ad9295___1_Windows__Security__Authorization__AppCapabilityAccess__IAppCapability___Windows__Security__Authorization__AppCapabilityAccess__IAppCapabilityAccessChangedEventArgs_____DelegateInvokeHelper_Microsoft__WRL__Implements_Microsoft__WRL__RuntimeClassFlags_2__Windows__Foundation__ITypedEventHandler_Windows__Security__Authorization__AppCapabilityAccess__AppCapability___Windows__Security__Authorization__AppCapabilityAccess__AppCapabilityAccessChangedEventArgs____Microsoft__WRL__FtmBase___lambda_32f1db981d03e860ebaed49377ad9295___1_Windows__Security__Authorization__AppCapabilityAccess__IAppCapability___Windows__Security__Authorization__AppCapabilityAccess__IAppCapabilityAccessChangedEventArgs___
0x180044326  mov     rbx, rax
0x180044329  mov     [rbp+var_48], 0
0x180044331  lea     rcx, [rbp+var_48]
0x180044335  call    Microsoft__WRL__Details__MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d________MakeAllocator_Windows__Internal__ComTaskPool__CTaskWrapper__lambda_d44e3682f6df0343f3c5f57a4a0d9f6d_____
0x18004433a  lea     rcx, [rbp+var_30]
0x18004433e  mov     [rbp+var_38], rbx
0x180044342  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180044347  test    rbx, rbx
0x18004434a  jnz     short loc_18004435B
0x18004434c  mov     ebx, 8007000Eh
0x180044351  mov     edx, 48h ; 'H'
0x180044356  jmp     loc_1800442CB
0x18004435b  mov     rcx, [rsi]
0x18004435e  mov     r8, r12
0x180044361  mov     rdx, rbx
0x180044364  mov     rax, [rcx]
0x180044367  mov     rax, [rax+50h]
0x18004436b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044370  mov     ebx, eax
0x180044372  test    eax, eax
0x180044374  jns     short loc_180044383
0x180044376  mov     r9d, eax
0x180044379  mov     edx, 4Ah ; 'J'
0x18004437e  jmp     loc_1800442CE
0x180044383  lea     rcx, [rbp+var_50]
0x180044387  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18004438c  xor     ebx, ebx
0x18004438e  lea     rcx, [rbp+var_38]
0x180044392  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x180044397  lea     rcx, [rbp+var_40]
0x18004439b  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x1800443a0  mov     eax, ebx
0x1800443a2  mov     rcx, [rbp+var_10]
0x1800443a6  xor     rcx, rsp; StackCookie
0x1800443a9  call    __security_check_cookie
0x1800443ae  lea     r11, [rsp+70h+var_s0]
0x1800443b3  mov     rbx, [r11+40h]
0x1800443b7  mov     rsi, [r11+48h]
0x1800443bb  mov     rsp, r11
0x1800443be  pop     r15
0x1800443c0  pop     r14
0x1800443c2  pop     r12
0x1800443c4  pop     rdi
0x1800443c5  pop     rbp
0x1800443c6  retn
```
