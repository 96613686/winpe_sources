# LPA::EsimManager::ProcessActivationCodeInternal(ushort const (*)[33],LPA::LPAESIMOPERATIONINTERNAL,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,bool,bool,ushort const (*)[21],ulong,void * const *,LPA::LPACLIENTMODEINTERNAL,std::weak_ptr<LPA::EsimManagerCompletionHandler>,LPA_ERROR_DETAILS &,ulong &)

- ea: `0x180091c7c`
- end: `0x180092412`
- name: `?ProcessActivationCodeInternal@EsimManager@LPA@@AEAAJPEAY0CB@$$CBGW4LPAESIMOPERATIONINTERNAL@2@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@22_N233PEAY0BF@$$CBGKPEBQEAXW4LPACLIENTMODEINTERNAL@2@V?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@5@AEAULPA_ERROR_DETAILS@@AEAK@Z`
- size: `1942`
- prototype: `__int64 __usercall@<rax>(LPA::EsimManager *this@<rcx>, unsigned __int16 (*)[33]@<rdx>, __int64, __int64, char, __int64, bool, char, __int64, int, __int64, char, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180091ae0`
- `0x180092418`

## callees

- `0x1800024e8`
- `0x1800037f4`
- `0x180004ed8`
- `0x18000df90`
- `0x18005fa50`
- `0x18006361c`
- `0x180063668`
- `0x180065170`
- `0x1800709e4`
- `0x180070a1c`
- `0x180071320`
- `0x180071650`
- `0x180071a8c`
- `0x180081678`
- `0x1800826d0`
- `0x180083a2c`
- `0x180084b7c`
- `0x180085280`
- `0x180088184`
- `0x18008af08`
- `0x18008bcc4`
- `0x18008c444`
- `0x180091434`
- `0x180091c7c`
- `0x180095f60`
- `0x1800973e0`
- `0x180101010`

## string_xrefs

- `0x180091f43`: `LpaServiceEsimManager`
- `0x180091d44`: `LpaServiceLpd`
- `0x180091dc0`: `LpaServiceLpd`
- `0x1800922eb`: `LpaServiceLpd`
- `0x18009237e`: `LpaServiceLpd`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall LPA::EsimManager::ProcessActivationCodeInternal(
        LPA::EsimManager *this,
        unsigned __int16 (*a2)[33],
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        char a7,
        __int64 a8,
        bool a9,
        char a10,
        __int64 a11,
        int a12,
        __int64 a13,
        char a14,
        _QWORD *a15,
        __int64 a16,
        _DWORD *a17)
{
  const unsigned __int16 *v17; // rdi
  _DWORD *v19; // r12
  int InterfaceGuidIfOperationAllowed; // esi
  int v21; // r8d
  int v22; // r9d
  __int64 *EsimRecordByEid; // rax
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  __int64 v27; // rbx
  unsigned int *v28; // rcx
  __int64 v29; // r13
  int v30; // ecx
  int v31; // r8d
  int v32; // r9d
  _QWORD *v33; // rax
  bool v34; // r15
  GUID *v35; // rax
  __int64 v36; // r15
  __int64 v37; // r13
  __int64 (__fastcall *v38)(__int64, struct _GUID *, unsigned int *, __int64, int, __int64, __int64, __int64, __int64, int, __int64, __int64, GUID *, __int64, int *); // r12
  __int64 v39; // r14
  __int64 v40; // rsi
  __int64 v41; // rdi
  __int64 v42; // rbx
  __int64 v43; // rax
  _QWORD *v44; // r15
  _QWORD *v45; // rax
  LPA::EsimManager *v46; // rbx
  int v47; // r8d
  __int64 v48; // r14
  _QWORD *v49; // rax
  __int64 v50; // rbx
  __int64 v51; // r14
  __int64 v52; // rcx
  __int64 v53; // rax
  std::_Ref_count_base *v54; // rcx
  int v56; // [rsp+48h] [rbp-C8h]
  unsigned int v57; // [rsp+90h] [rbp-80h] BYREF
  int v58; // [rsp+94h] [rbp-7Ch] BYREF
  GUID *v59; // [rsp+98h] [rbp-78h] BYREF
  int v60; // [rsp+A0h] [rbp-70h] BYREF
  const char *v61; // [rsp+A8h] [rbp-68h] BYREF
  __int64 v62; // [rsp+B0h] [rbp-60h] BYREF
  __int64 v63; // [rsp+B8h] [rbp-58h] BYREF
  const char *v64; // [rsp+C0h] [rbp-50h] BYREF
  _QWORD *v65; // [rsp+C8h] [rbp-48h]
  __int64 v66; // [rsp+D0h] [rbp-40h] BYREF
  std::_Ref_count_base *v67; // [rsp+D8h] [rbp-38h]
  __int64 v68; // [rsp+E0h] [rbp-30h] BYREF
  std::_Ref_count_base *v69; // [rsp+E8h] [rbp-28h]
  __int64 v70; // [rsp+F0h] [rbp-20h]
  __int64 v71; // [rsp+F8h] [rbp-18h]
  __int64 v72; // [rsp+100h] [rbp-10h]
  LPA::EsimManager *v73; // [rsp+108h] [rbp-8h]
  __int64 v74; // [rsp+110h] [rbp+0h]
  unsigned __int16 *v75; // [rsp+118h] [rbp+8h]
  __int64 v76; // [rsp+120h] [rbp+10h]
  _QWORD *v77; // [rsp+128h] [rbp+18h]
  _BYTE v78[56]; // [rsp+130h] [rbp+20h] BYREF
  __int64 v79; // [rsp+168h] [rbp+58h]
  struct _GUID v80; // [rsp+170h] [rbp+60h] BYREF
  struct _GUID v81; // [rsp+190h] [rbp+80h] BYREF
  _BYTE v82[32]; // [rsp+1A0h] [rbp+90h] BYREF
  _BYTE v83[32]; // [rsp+1C0h] [rbp+B0h] BYREF
  char v84[32]; // [rsp+1E0h] [rbp+D0h] BYREF
  __int64 v85; // [rsp+200h] [rbp+F0h] BYREF
  struct _GUID v86; // [rsp+210h] [rbp+100h]
  _BYTE v87[56]; // [rsp+220h] [rbp+110h] BYREF
  __int64 v88; // [rsp+258h] [rbp+148h]

  v71 = a4;
  v58 = a3;
  v17 = (const unsigned __int16 *)a2;
  v75 = (unsigned __int16 *)a2;
  v73 = this;
  v70 = a5;
  v62 = a6;
  v63 = a8;
  v74 = a11;
  v72 = a13;
  v65 = a15;
  v77 = a15;
  v68 = a16;
  v19 = a17;
  v76 = (__int64)a17;
  v81 = 0;
  v57 = -1;
  InterfaceGuidIfOperationAllowed = LPA::EsimManager::GetInterfaceGuidIfOperationAllowed(
                                      this,
                                      (unsigned __int16 *)a2,
                                      a3,
                                      &v81);
  if ( InterfaceGuidIfOperationAllowed < 0 )
  {
    v29 = *((_QWORD *)this + 26);
    if ( (unsigned int)CallbackContext > 2 )
    {
      *(_QWORD *)&v80.Data1 = v17;
      LODWORD(v59) = InterfaceGuidIfOperationAllowed;
      v61 = "LPA::EsimManager::ProcessActivationCodeInternal";
      v64 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
        (unsigned int)"LPA::EsimManager::ProcessActivationCodeInternal",
        (unsigned int)&byte_18012E54F,
        v21,
        v22,
        (__int64)&v64,
        (__int64)&v61,
        (__int64)&v59,
        (__int64)&v80);
    }
    v27 = v29;
  }
  else
  {
    EsimRecordByEid = (__int64 *)LPA::EsimManager::TryFindEsimRecordByEid(this, &v66, v17, &v81);
    v27 = *EsimRecordByEid;
    if ( *EsimRecordByEid == *((_QWORD *)this + 26) )
    {
      if ( (unsigned int)CallbackContext > 4 )
      {
        v64 = (const char *)v17;
        LODWORD(v59) = InterfaceGuidIfOperationAllowed;
        v61 = "LPA::EsimManager::ProcessActivationCodeInternal";
        *(_QWORD *)&v80.Data1 = "LpaServiceLpd";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
          v24,
          (unsigned int)byte_18012E593,
          v25,
          v26,
          (__int64)&v80,
          (__int64)&v61,
          (__int64)&v59,
          (__int64)&v64);
      }
    }
    else
    {
      v28 = *(unsigned int **)(*(_QWORD *)(v27 + 48) + 32LL);
      v57 = v28[27];
      if ( !*(_QWORD *)(*(_QWORD *)(v27 + 48) + 256LL) )
        LPA::EsimManager::AttemptToGetRulesAuthorizationTable((LPA::EsimManager *)v28, &v81, &v57);
    }
    v29 = v27;
  }
  v80 = v81;
  if ( LPA::EsimManager::IsAutoProvisioningApplicable(this, (const unsigned __int16 (*)[33])v17, &v80, a9) )
  {
    v33 = std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(
            &v80,
            a15);
    v34 = (int)LPA::EsimManager::PerformOperationWithAutoProvisioning(
                 this,
                 a12,
                 v71,
                 v70,
                 v62,
                 a7,
                 v63,
                 a10,
                 0,
                 v74,
                 v72,
                 a14,
                 (__int64)v33,
                 (__int64)a17) >= 0;
  }
  else
  {
    v34 = 0;
    if ( (unsigned int)CallbackContext > 3 )
    {
      LODWORD(v59) = v57;
      *(_QWORD *)&v80.Data1 = v17;
      v61 = "LPA::EsimManager::ProcessActivationCodeInternal";
      v64 = "LpaServiceEsimManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v30,
        (unsigned int)&word_18012E4FE,
        v31,
        v32,
        (__int64)&v64,
        (__int64)&v61,
        (__int64)&v80,
        (__int64)&v59);
    }
  }
  v35 = 0;
  v60 = 0;
  if ( InterfaceGuidIfOperationAllowed >= 0 )
  {
    if ( v57 == -1 || v34 )
    {
      v44 = v65;
LABEL_36:
      if ( (unsigned int)CallbackContext > 4 )
      {
        LODWORD(v59) = v57;
        v58 = v60;
        LODWORD(v62) = *v19;
        v68 = (__int64)v17;
        LODWORD(v63) = InterfaceGuidIfOperationAllowed;
        *(_QWORD *)&v80.Data1 = "LPA::EsimManager::ProcessActivationCodeInternal";
        v61 = "LpaServiceLpd";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
          v30,
          (unsigned int)&word_18012E48E,
          v31,
          v32,
          (__int64)&v61,
          (__int64)&v80,
          (__int64)&v63,
          (__int64)&v68,
          (__int64)&v62,
          (__int64)&v58,
          (__int64)&v59);
      }
      goto LABEL_42;
    }
    if ( *((_BYTE *)this + 301) )
    {
      v36 = *(_QWORD *)(v27 + 48);
    }
    else
    {
      v36 = *(_QWORD *)(v29 + 48);
      if ( *(_QWORD *)(v36 + 168) )
        v35 = &LPA::EsimManager::s_guidProvisioning;
    }
    v59 = v35;
    v37 = *((_QWORD *)this + 20);
    v38 = *(__int64 (__fastcall **)(__int64, struct _GUID *, unsigned int *, __int64, int, __int64, __int64, __int64, __int64, int, __int64, __int64, GUID *, __int64, int *))(*(_QWORD *)v37 + 24LL);
    v39 = std::_String_val<std::_Simple_types<char>>::_Myptr(v63);
    v40 = std::_String_val<std::_Simple_types<char>>::_Myptr(v62);
    v41 = std::_String_val<std::_Simple_types<char>>::_Myptr(v70);
    v42 = std::_String_val<std::_Simple_types<char>>::_Myptr(v71);
    std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)v73 + 88, &v80);
    v43 = std::weak_ptr<LPA::LpdCompletionHandler>::weak_ptr<LPA::LpdCompletionHandler>(&v66);
    LOBYTE(v56) = a7;
    InterfaceGuidIfOperationAllowed = v38(
                                        v37,
                                        &v81,
                                        &v57,
                                        v72,
                                        a12,
                                        v43,
                                        v42,
                                        v41,
                                        v40,
                                        v56,
                                        v39,
                                        v36 + 252,
                                        v59,
                                        v68,
                                        &v60);
    v30 = *(_DWORD *)v80.Data4;
    if ( *(_QWORD *)v80.Data4 )
      std::_Ref_count_base::_Decref(*(std::_Ref_count_base **)v80.Data4);
    if ( InterfaceGuidIfOperationAllowed >= 0 )
    {
      v44 = v65;
      v45 = std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(
              &v66,
              v65);
      v19 = (_DWORD *)v76;
      v17 = v75;
      v46 = v73;
      LPA::EsimManager::HandleCommandInitiated(
        v73,
        a12,
        0,
        0,
        0,
        a14,
        (__int64)v45,
        (char) LPA::EsimManagerCompletionHandler::`vcall'{48,{flat}},
        v47,
        v76);
      if ( a10 )
      {
        v48 = v74;
        if ( v74 )
        {
          v49 = (_QWORD *)std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this((char *)v46 + 88, &v68);
          std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(
            &v66,
            v49);
          if ( v69 )
            std::_Ref_count_base::_Decref(v69);
          std::wstring::wstring(v82, v48);
          std::wstring::wstring(&v80, v17);
          std::wstring::wstring(v83, &v80);
          std::wstring::wstring(v84, v82);
          std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(
            &v85,
            &v66);
          v86 = v81;
          v79 = 0;
          v79 = std::_Global_new_std::_Func_impl_no_alloc__LPA::EsimManager::ProcessActivationCodeInternal_::_48_::_lambda_1__long_long_unsigned_long_LPA_ERROR_DETAILS_____LPA::EsimManager::ProcessActivationCodeInternal_::_48_::_lambda_1___(v83);
          LPA::EsimManager::ProcessActivationCodeInternal_::_48_::_lambda_1_::__lambda_1_(v83);
          v50 = *(_QWORD *)(*(_QWORD *)std::map<unsigned long,std::unique_ptr<LPA::EsimManager::OperationEntry>>::_Try_emplace<unsigned long const &,>(
                                         (char *)v46 + 240,
                                         &v68,
                                         &v60)
                          + 40LL)
              + 144LL;
          v51 = std::function<long (long,unsigned long,LPA_ERROR_DETAILS &)>::function<long (long,unsigned long,LPA_ERROR_DETAILS &)>(
                  v83,
                  v78);
          v52 = *(_QWORD *)(v51 + 56);
          if ( v52 == v51 || (v53 = *(_QWORD *)(v50 + 56), v53 == v50) )
          {
            v88 = 0;
            std::_Func_class<long,long,unsigned long,LPA_ERROR_DETAILS &>::_Reset_move(v87, v51);
            std::_Func_class<long,long,unsigned long,LPA_ERROR_DETAILS &>::_Reset_move(v51, v50);
            std::_Func_class<long,long,unsigned long,LPA_ERROR_DETAILS &>::_Reset_move(v50, v87);
            `pplx::details::_MakeTToUnitFunc<web::json::value>'::`2'::_lambda_1_::~_lambda_1_(v87);
          }
          else
          {
            *(_QWORD *)(v51 + 56) = v53;
            *(_QWORD *)(v50 + 56) = v52;
          }
          `pplx::details::_MakeTToUnitFunc<web::json::value>'::`2'::_lambda_1_::~_lambda_1_(v83);
          `pplx::details::_MakeTToUnitFunc<web::json::value>'::`2'::_lambda_1_::~_lambda_1_(v78);
          std::wstring::_Tidy_deallocate(&v80);
          std::wstring::_Tidy_deallocate(v82);
          v30 = (int)v67;
          if ( v67 )
            std::_Ref_count_base::_Decwref(v67);
        }
      }
      goto LABEL_36;
    }
    v17 = v75;
    v19 = (_DWORD *)v76;
  }
  if ( (unsigned int)CallbackContext > 2 )
  {
    LODWORD(v63) = v57;
    LODWORD(v62) = v60;
    LODWORD(v59) = *v19;
    v68 = (__int64)v17;
    v58 = InterfaceGuidIfOperationAllowed;
    *(_QWORD *)&v80.Data1 = "LPA::EsimManager::ProcessActivationCodeInternal";
    v61 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v30,
      (unsigned int)&word_18012E41E,
      v31,
      v32,
      (__int64)&v61,
      (__int64)&v80,
      (__int64)&v58,
      (__int64)&v68,
      (__int64)&v59,
      (__int64)&v62,
      (__int64)&v63);
  }
  v44 = v65;
LABEL_42:
  v54 = (std::_Ref_count_base *)v44[1];
  if ( v54 )
    std::_Ref_count_base::_Decwref(v54);
  return (unsigned int)InterfaceGuidIfOperationAllowed;
}

```

## disassembly

```asm
0x180091c7c  mov     [rsp-8+arg_10], rbx
0x180091c81  push    rbp
0x180091c82  push    rsi
0x180091c83  push    rdi
0x180091c84  push    r12
0x180091c86  push    r13
0x180091c88  push    r14
0x180091c8a  push    r15
0x180091c8c  lea     rbp, [rsp-160h]
0x180091c94  sub     rsp, 270h
0x180091c9b  mov     rax, cs:__security_cookie
0x180091ca2  xor     rax, rsp
0x180091ca5  mov     [rbp+190h+var_40], rax
0x180091cac  mov     [rbp+190h+var_1A8], r9
0x180091cb0  mov     [rbp+190h+var_20C], r8d
0x180091cb4  mov     rdi, rdx
0x180091cb7  mov     [rbp+190h+var_188], rdx
0x180091cbb  mov     r14, rcx
0x180091cbe  mov     [rbp+190h+var_198], rcx
0x180091cc2  mov     rax, [rbp+190h+arg_20]
0x180091cc9  mov     [rbp+190h+var_1B0], rax
0x180091ccd  mov     rax, [rbp+190h+arg_28]
0x180091cd4  mov     [rbp+190h+var_1F0], rax
0x180091cd8  mov     rax, [rbp+190h+arg_38]
0x180091cdf  mov     [rbp+190h+var_1E8], rax
0x180091ce3  mov     rax, [rbp+190h+arg_50]
0x180091cea  mov     [rbp+190h+var_190], rax
0x180091cee  mov     rax, [rbp+190h+arg_60]
0x180091cf5  mov     [rbp+190h+var_1A0], rax
0x180091cf9  mov     r15, [rbp+190h+arg_70]
0x180091d00  mov     [rbp+190h+var_1D8], r15
0x180091d04  mov     [rbp+190h+var_178], r15
0x180091d08  mov     rax, [rbp+190h+arg_78]
0x180091d0f  mov     [rbp+190h+var_1C0], rax
0x180091d13  mov     r12, [rbp+190h+arg_80]
0x180091d1a  mov     [rbp+190h+var_180], r12
0x180091d1e  xorps   xmm0, xmm0
0x180091d21  movups  xmmword ptr [rbp+190h+var_110.Data1], xmm0
0x180091d28  mov     [rbp+190h+var_210], 0FFFFFFFFh
0x180091d2f  lea     r9, [rbp+190h+var_110]
0x180091d36  call    ?GetInterfaceGuidIfOperationAllowed@EsimManager@LPA@@AEAAJPEAY0CB@$$CBGW4LPAESIMOPERATIONINTERNAL@2@AEAU_GUID@@@Z; LPA::EsimManager::GetInterfaceGuidIfOperationAllowed(ushort const (*)[33],LPA::LPAESIMOPERATIONINTERNAL,_GUID &)
0x180091d3b  mov     esi, eax
0x180091d3d  lea     rcx, aLpaEsimmanager_36; "LPA::EsimManager::ProcessActivationCode"...
0x180091d44  lea     rdx, aLpaservicelpd; "LpaServiceLpd"
0x180091d4b  test    eax, eax
0x180091d4d  js      loc_180091E00
0x180091d53  lea     r9, [rbp+190h+var_110]
0x180091d5a  mov     r8, rdi
0x180091d5d  lea     rdx, [rbp+190h+var_1D0]
0x180091d61  mov     rcx, r14
0x180091d64  call    ?TryFindEsimRecordByEid@EsimManager@LPA@@AEAA?AV?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@V?$unique_ptr@VEsimRecord@EsimManager@LPA@@U?$default_delete@VEsimRecord@EsimManager@LPA@@@std@@@std@@@std@@@std@@@std@@@std@@PEAY0CB@$$CBGAEBU_GUID@@@Z; LPA::EsimManager::TryFindEsimRecordByEid(ushort const (*)[33],_GUID const &)
0x180091d69  mov     rbx, [rax]
0x180091d6c  cmp     rbx, [r14+0D0h]
0x180091d73  jz      short loc_180091DA3
0x180091d75  mov     rax, [rbx+30h]
0x180091d79  mov     rcx, [rax+20h]; this
0x180091d7d  mov     eax, [rcx+6Ch]
0x180091d80  mov     [rbp+190h+var_210], eax
0x180091d83  mov     rax, [rbx+30h]
0x180091d87  cmp     qword ptr [rax+100h], 0
0x180091d8f  jnz     short loc_180091DFB
0x180091d91  lea     r8, [rbp+190h+var_210]; unsigned int *
0x180091d95  lea     rdx, [rbp+190h+var_110]; struct _GUID *
0x180091d9c  call    ?AttemptToGetRulesAuthorizationTable@EsimManager@LPA@@AEAAXAEBU_GUID@@AEBK@Z; LPA::EsimManager::AttemptToGetRulesAuthorizationTable(_GUID const &,ulong const &)
0x180091da1  jmp     short loc_180091DFB
0x180091da3  mov     eax, cs:CallbackContext
0x180091da9  cmp     eax, 4
0x180091dac  jbe     short loc_180091DFB
0x180091dae  mov     [rbp+190h+var_1E0], rdi
0x180091db2  mov     dword ptr [rbp+190h+var_208], esi
0x180091db5  lea     rax, aLpaEsimmanager_36; "LPA::EsimManager::ProcessActivationCode"...
0x180091dbc  mov     [rbp+190h+var_1F8], rax
0x180091dc0  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x180091dc7  mov     qword ptr [rbp+190h+var_130.Data1], rax
0x180091dcb  lea     rax, [rbp+190h+var_1E0]
0x180091dcf  mov     [rsp+2A0h+var_268], rax
0x180091dd4  lea     rax, [rbp+190h+var_208]
0x180091dd8  mov     [rsp+2A0h+var_270], rax
0x180091ddd  lea     rax, [rbp+190h+var_1F8]
0x180091de1  mov     qword ptr [rsp+2A0h+var_278], rax
0x180091de6  lea     rax, [rbp+190h+var_130]
0x180091dea  mov     qword ptr [rsp+2A0h+var_280], rax
0x180091def  lea     rdx, byte_18012E593
0x180091df6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180091dfb  mov     r13, rbx
0x180091dfe  jmp     short loc_180091E54
0x180091e00  mov     r13, [r14+0D0h]
0x180091e07  mov     eax, cs:CallbackContext
0x180091e0d  cmp     eax, 2
0x180091e10  jbe     short loc_180091E51
0x180091e12  mov     qword ptr [rbp+190h+var_130.Data1], rdi
0x180091e16  mov     dword ptr [rbp+190h+var_208], esi
0x180091e19  mov     [rbp+190h+var_1F8], rcx
0x180091e1d  mov     [rbp+190h+var_1E0], rdx
0x180091e21  lea     rax, [rbp+190h+var_130]
0x180091e25  mov     [rsp+2A0h+var_268], rax
0x180091e2a  lea     rax, [rbp+190h+var_208]
0x180091e2e  mov     [rsp+2A0h+var_270], rax
0x180091e33  lea     rax, [rbp+190h+var_1F8]
0x180091e37  mov     qword ptr [rsp+2A0h+var_278], rax
0x180091e3c  lea     rax, [rbp+190h+var_1E0]
0x180091e40  mov     qword ptr [rsp+2A0h+var_280], rax
0x180091e45  lea     rdx, byte_18012E54F
0x180091e4c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x180091e51  mov     rbx, r13
0x180091e54  movaps  xmm0, xmmword ptr [rbp+190h+var_110.Data1]
0x180091e5b  movdqa  xmmword ptr [rbp+190h+var_130.Data1], xmm0
0x180091e60  mov     r9b, [rbp+190h+arg_40]; bool
0x180091e67  lea     r8, [rbp+190h+var_130]; struct _GUID
0x180091e6b  mov     rdx, rdi; unsigned __int16 (*)[33]
0x180091e6e  mov     rcx, r14; this
0x180091e71  call    ?IsAutoProvisioningApplicable@EsimManager@LPA@@AEAA_NPEAY0CB@$$CBGU_GUID@@_N@Z; LPA::EsimManager::IsAutoProvisioningApplicable(ushort const (*)[33],_GUID,bool)
0x180091e76  test    al, al
0x180091e78  jz      loc_180091F20
0x180091e7e  mov     rdx, r15
0x180091e81  lea     rcx, [rbp+190h+var_130]
0x180091e85  call    ??$?0V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@$0A@@?$weak_ptr@V?$streambuf_state_manager@D@details@streams@Concurrency@@@std@@QEAA@AEBV?$shared_ptr@V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@@1@@Z; std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(std::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>> const &)
0x180091e8a  mov     [rsp+2A0h+var_220], r12; __int64
0x180091e92  mov     [rsp+2A0h+var_228], rax; __int64
0x180091e97  mov     eax, dword ptr [rbp+190h+arg_68]
0x180091e9d  mov     dword ptr [rsp+2A0h+var_230], eax; char
0x180091ea1  mov     rax, [rbp+190h+var_1A0]
0x180091ea5  mov     [rsp+2A0h+var_238], rax; __int64
0x180091eaa  mov     rax, [rbp+190h+var_190]
0x180091eae  mov     [rsp+2A0h+var_240], rax; __int64
0x180091eb3  mov     dword ptr [rsp+2A0h+var_248], 0; char
0x180091ebb  mov     al, [rbp+190h+arg_48]
0x180091ec1  mov     [rsp+2A0h+var_250], al; char
0x180091ec5  mov     rax, [rbp+190h+var_1E8]
0x180091ec9  mov     [rsp+2A0h+var_258], rax; __int64
0x180091ece  mov     al, [rbp+190h+arg_30]
0x180091ed4  mov     [rsp+2A0h+var_260], al; char
0x180091ed8  mov     rax, [rbp+190h+var_1F0]
0x180091edc  mov     [rsp+2A0h+var_268], rax; __int64
0x180091ee1  mov     rax, [rbp+190h+var_1B0]
0x180091ee5  mov     [rsp+2A0h+var_270], rax; __int64
0x180091eea  mov     rax, [rbp+190h+var_1A8]
0x180091eee  mov     qword ptr [rsp+2A0h+var_278], rax; __int64
0x180091ef3  mov     eax, [rbp+190h+arg_58]
0x180091ef9  mov     [rsp+2A0h+var_280], eax; int
0x180091efd  mov     r9d, [rbp+190h+var_20C]
0x180091f01  lea     r8, [rbp+190h+var_110]
0x180091f08  mov     rdx, rdi
0x180091f0b  mov     rcx, r14; this
0x180091f0e  call    ?PerformOperationWithAutoProvisioning@EsimManager@LPA@@AEAAJPEAY0CB@$$CBGAEBU_GUID@@W4LPAESIMOPERATIONINTERNAL@2@KAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@33_N34W4LPADISCOVERYMODE@@PEAY0BF@$$CBGPEBQEAXW4LPACLIENTMODEINTERNAL@2@V?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@6@AEAK@Z; LPA::EsimManager::PerformOperationWithAutoProvisioning(ushort const (*)[33],_GUID const &,LPA::LPAESIMOPERATIONINTERNAL,ulong,std::string const &,std::string const &,std::string const &,bool,std::string const &,bool,LPADISCOVERYMODE,ushort const (*)[21],void * const *,LPA::LPACLIENTMODEINTERNAL,std::weak_ptr<LPA::EsimManagerCompletionHandler>,ulong &)
0x180091f13  mov     r15d, eax
0x180091f16  shr     r15d, 1Fh
0x180091f1a  xor     r15b, 1
0x180091f1e  jmp     short loc_180091F7E
0x180091f20  xor     r15b, r15b
0x180091f23  mov     eax, cs:CallbackContext
0x180091f29  cmp     eax, 3
0x180091f2c  jbe     short loc_180091F7E
0x180091f2e  mov     eax, [rbp+190h+var_210]
0x180091f31  mov     dword ptr [rbp+190h+var_208], eax
0x180091f34  mov     qword ptr [rbp+190h+var_130.Data1], rdi
0x180091f38  lea     rax, aLpaEsimmanager_36; "LPA::EsimManager::ProcessActivationCode"...
0x180091f3f  mov     [rbp+190h+var_1F8], rax
0x180091f43  lea     rax, aLpaserviceesim; "LpaServiceEsimManager"
0x180091f4a  mov     [rbp+190h+var_1E0], rax
0x180091f4e  lea     rax, [rbp+190h+var_208]
0x180091f52  mov     [rsp+2A0h+var_268], rax
0x180091f57  lea     rax, [rbp+190h+var_130]
0x180091f5b  mov     [rsp+2A0h+var_270], rax
0x180091f60  lea     rax, [rbp+190h+var_1F8]
0x180091f64  mov     qword ptr [rsp+2A0h+var_278], rax
0x180091f69  lea     rax, [rbp+190h+var_1E0]
0x180091f6d  mov     qword ptr [rsp+2A0h+var_280], rax
0x180091f72  lea     rdx, word_18012E4FE
0x180091f79  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180091f7e  xor     eax, eax
0x180091f80  mov     [rbp+190h+var_200], eax
0x180091f83  test    esi, esi
0x180091f85  js      loc_18009234E
0x180091f8b  cmp     [rbp+190h+var_210], 0FFFFFFFFh
0x180091f8f  jz      loc_1800922B3
0x180091f95  test    r15b, r15b
0x180091f98  jnz     loc_1800922B3
0x180091f9e  cmp     [r14+12Dh], al
0x180091fa5  jnz     short loc_180091FBD
0x180091fa7  mov     r15, [r13+30h]
0x180091fab  cmp     [r15+0A8h], rax
0x180091fb2  jbe     short loc_180091FC1
0x180091fb4  lea     rax, ?s_guidProvisioning@EsimManager@LPA@@0U_GUID@@B; _GUID const LPA::EsimManager::s_guidProvisioning
0x180091fbb  jmp     short loc_180091FC1
0x180091fbd  mov     r15, [rbx+30h]
0x180091fc1  mov     [rbp+190h+var_208], rax
0x180091fc5  mov     r13, [r14+0A0h]
0x180091fcc  mov     rax, [r13+0]
0x180091fd0  mov     r12, [rax+18h]
0x180091fd4  add     r15, 0FCh
0x180091fdb  mov     rcx, [rbp+190h+var_1E8]
0x180091fdf  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180091fe4  mov     r14, rax
0x180091fe7  mov     rcx, [rbp+190h+var_1F0]
0x180091feb  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180091ff0  mov     rsi, rax
0x180091ff3  mov     rcx, [rbp+190h+var_1B0]
0x180091ff7  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180091ffc  mov     rdi, rax
0x180091fff  mov     rcx, [rbp+190h+var_1A8]
0x180092003  call    ?_Myptr@?$_String_val@U?$_Simple_types@D@std@@@std@@QEBAPEBDXZ; std::_String_val<std::_Simple_types<char>>::_Myptr(void)
0x180092008  mov     rbx, rax
0x18009200b  mov     rcx, [rbp+190h+var_198]
0x18009200f  add     rcx, 58h ; 'X'
0x180092013  lea     rdx, [rbp+190h+var_130]
0x180092017  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x18009201c  nop
0x18009201d  mov     rdx, rax
0x180092020  lea     rcx, [rbp+190h+var_1D0]
0x180092024  call    ??$?0VEsimManager@LPA@@$0A@@?$weak_ptr@ULpdCompletionHandler@LPA@@@std@@QEAA@AEBV?$shared_ptr@VEsimManager@LPA@@@1@@Z; std::weak_ptr<LPA::LpdCompletionHandler>::weak_ptr<LPA::LpdCompletionHandler>(std::shared_ptr<LPA::EsimManager> const &)
0x180092029  lea     rcx, [rbp+190h+var_200]
0x18009202d  mov     qword ptr [rsp+2A0h+var_230], rcx
0x180092032  mov     rcx, [rbp+190h+var_1C0]
0x180092036  mov     [rsp+2A0h+var_238], rcx
0x18009203b  mov     rcx, [rbp+190h+var_208]
0x18009203f  mov     [rsp+2A0h+var_240], rcx
0x180092044  mov     qword ptr [rsp+2A0h+var_248], r15
0x180092049  mov     qword ptr [rsp+2A0h+var_250], r14
0x18009204e  mov     cl, [rbp+190h+arg_30]
0x180092054  mov     byte ptr [rsp+2A0h+var_258], cl
0x180092058  mov     qword ptr [rsp+2A0h+var_260], rsi
0x18009205d  mov     [rsp+2A0h+var_268], rdi
0x180092062  mov     [rsp+2A0h+var_270], rbx
0x180092067  mov     qword ptr [rsp+2A0h+var_278], rax
0x18009206c  mov     ebx, [rbp+190h+arg_58]
0x180092072  mov     [rsp+2A0h+var_280], ebx
0x180092076  mov     r9, [rbp+190h+var_1A0]
0x18009207a  lea     r8, [rbp+190h+var_210]
0x18009207e  lea     rdx, [rbp+190h+var_110]
0x180092085  mov     rcx, r13
0x180092088  mov     rax, r12
0x18009208b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092090  mov     esi, eax
0x180092092  mov     rcx, qword ptr [rbp+190h+var_130.Data4]; this
0x180092096  test    rcx, rcx
0x180092099  jz      short loc_1800920A0
0x18009209b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800920a0  test    esi, esi
0x1800920a2  js      loc_180092346
0x1800920a8  mov     r8d, [rbp+190h+var_200]
0x1800920ac  mov     r15, [rbp+190h+var_1D8]
0x1800920b0  mov     rdx, r15
0x1800920b3  lea     rcx, [rbp+190h+var_1D0]
0x1800920b7  call    ??$?0V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@$0A@@?$weak_ptr@V?$streambuf_state_manager@D@details@streams@Concurrency@@@std@@QEAA@AEBV?$shared_ptr@V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@@1@@Z; std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(std::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>> const &)
0x1800920bc  mov     r12, [rbp+190h+var_180]
0x1800920c0  mov     [rsp+2A0h+var_240], r12; __int64
0x1800920c5  mov     dword ptr [rsp+2A0h+var_248], r8d; int
0x1800920ca  lea     rcx, ??_9EsimManagerCompletionHandler@LPA@@$BDA@AA; [thunk]: LPA::EsimManagerCompletionHandler::`vcall'{48,{flat}}
0x1800920d1  mov     qword ptr [rsp+2A0h+var_250], rcx; char
0x1800920d6  mov     [rsp+2A0h+var_258], rax; __int64
0x1800920db  mov     eax, dword ptr [rbp+190h+arg_68]
0x1800920e1  mov     dword ptr [rsp+2A0h+var_260], eax; char
0x1800920e5  mov     [rsp+2A0h+var_268], 0; __int64
0x1800920ee  mov     [rsp+2A0h+var_270], 0; unsigned __int16 *
0x1800920f7  mov     [rsp+2A0h+var_278], 0; char
0x1800920fc  mov     [rsp+2A0h+var_280], ebx; int
0x180092100  mov     r9d, [rbp+190h+var_20C]
0x180092104  lea     r8, [rbp+190h+var_110]
0x18009210b  mov     rdi, [rbp+190h+var_188]
0x18009210f  mov     rdx, rdi
0x180092112  mov     rbx, [rbp+190h+var_198]
0x180092116  mov     rcx, rbx; this
0x180092119  call    ?HandleCommandInitiated@EsimManager@LPA@@AEAAXPEAY0CB@$$CBGAEBU_GUID@@W4LPAESIMOPERATIONINTERNAL@2@K_NPEAY0BF@$$CBGPEAW4LPAPROFILESTATE@@W4LPACLIENTMODEINTERNAL@2@V?$weak_ptr@UEsimManagerCompletionHandler@LPA@@@std@@P8EsimManagerCompletionHandler@2@EAAXJPEBULPA_ERROR_DETAILS@@K@ZKAEAK@Z; LPA::EsimManager::HandleCommandInitiated(ushort const (*)[33],_GUID const &,LPA::LPAESIMOPERATIONINTERNAL,ulong,bool,ushort const (*)[21],LPAPROFILESTATE *,LPA::LPACLIENTMODEINTERNAL,std::weak_ptr<LPA::EsimManagerCompletionHandler>,void (LPA::EsimManagerCompletionHandler::*)(long,LPA_ERROR_DETAILS const *,ulong),ulong,ulong &)
0x18009211e  cmp     [rbp+190h+arg_48], 0
0x180092125  jz      loc_1800922B7
0x18009212b  mov     r14, [rbp+190h+var_190]
0x18009212f  test    r14, r14
0x180092132  jz      loc_1800922B7
0x180092138  lea     rdx, [rbp+190h+var_1C0]
0x18009213c  lea     rcx, [rbx+58h]
0x180092140  call    ?shared_from_this@?$enable_shared_from_this@VEnterpriseManager@LPA@@@std@@QEAA?AV?$shared_ptr@VEnterpriseManager@LPA@@@2@XZ; std::enable_shared_from_this<LPA::EnterpriseManager>::shared_from_this(void)
0x180092145  mov     rdx, rax
0x180092148  lea     rcx, [rbp+190h+var_1D0]
0x18009214c  call    ??$?0V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@$0A@@?$weak_ptr@V?$streambuf_state_manager@D@details@streams@Concurrency@@@std@@QEAA@AEBV?$shared_ptr@V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@@1@@Z; std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(std::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>> const &)
0x180092151  nop
0x180092152  mov     rcx, [rbp+190h+var_1B8]; this
0x180092156  test    rcx, rcx
0x180092159  jz      short loc_180092160
0x18009215b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180092160  mov     rdx, r14
0x180092163  lea     rcx, [rbp+190h+var_100]
0x18009216a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009216f  nop
0x180092170  mov     rdx, rdi
0x180092173  lea     rcx, [rbp+190h+var_130]
0x180092177  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18009217c  nop
0x18009217d  lea     rdx, [rbp+190h+var_130]
0x180092181  lea     rcx, [rbp+190h+var_E0]
0x180092188  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18009218d  nop
0x18009218e  lea     rdx, [rbp+190h+var_100]
0x180092195  lea     rcx, [rbp+190h+var_C0]
0x18009219c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800921a1  lea     rdx, [rbp+190h+var_1D0]
0x1800921a5  lea     rcx, [rbp+190h+var_A0]
0x1800921ac  call    ??$?0V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@$0A@@?$weak_ptr@V?$streambuf_state_manager@D@details@streams@Concurrency@@@std@@QEAA@AEBV?$shared_ptr@V?$basic_container_buffer@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@details@streams@Concurrency@@@1@@Z; std::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>::weak_ptr<Concurrency::streams::details::streambuf_state_manager<char>>(std::shared_ptr<Concurrency::streams::details::basic_container_buffer<std::string>> const &)
0x1800921b1  movaps  xmm0, xmmword ptr [rbp+190h+var_110.Data1]
0x1800921b8  movdqu  [rbp+190h+var_90], xmm0
  ... truncated ...
```
