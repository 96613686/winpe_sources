# NgcCreateContainer

- ea: `0x1800374f0`
- end: `0x180037916`
- name: `NgcCreateContainer`
- size: `1062`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001424`
- `0x180006560`
- `0x1800076ac`
- `0x1800158e0`
- `0x180016b6c`
- `0x180018790`
- `0x18001a36c`
- `0x18001a4b8`
- `0x18001c1a0`
- `0x18001c630`
- `0x180021a80`
- `0x18002494c`
- `0x180032fcc`
- `0x180035144`
- `0x180036784`
- `0x1800374f0`
- `0x1800420d4`
- `0x18004367c`
- `0x180043eb8`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037813`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180037813`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800377ba`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800377ba`

## string_xrefs

- `0x180037545`: `onecore\ds\security\ngc\cryptngc\dll\ngcpinmanagement.cpp`

## pseudocode

```c
__int64 NgcCreateContainer(const WCHAR *a1, bool *a2, __int64 a3, ...)
{
  int IsVsmAvailable; // eax
  NgcUtils *v4; // rcx
  NgcUtils *v5; // rcx
  bool IsZero; // al
  struct _GUID *v7; // r9
  unsigned int v8; // ebx
  __int16 *v10; // rdx
  enum NgcUserAccountType *v11; // r8
  DWORD LastError; // eax
  int v13; // eax
  int v14; // [rsp+28h] [rbp-E0h]
  int TenantId; // [rsp+68h] [rbp-A0h] BYREF
  char v16; // [rsp+6Ch] [rbp-9Ch] BYREF
  bool v17; // [rsp+6Dh] [rbp-9Bh] BYREF
  bool v18; // [rsp+6Eh] [rbp-9Ah] BYREF
  int v19; // [rsp+70h] [rbp-98h] BYREF
  bool v20; // [rsp+74h] [rbp-94h] BYREF
  bool v21; // [rsp+75h] [rbp-93h] BYREF
  char v22; // [rsp+76h] [rbp-92h] BYREF
  bool IsNgcInVsmEnabled; // [rsp+77h] [rbp-91h] BYREF
  char v24; // [rsp+78h] [rbp-90h] BYREF
  bool IsSecureBioEnabled; // [rsp+79h] [rbp-8Fh] BYREF
  DWORD v26; // [rsp+7Ch] [rbp-8Ch] BYREF
  PSID Sid; // [rsp+80h] [rbp-88h] BYREF
  unsigned __int16 *v28; // [rsp+88h] [rbp-80h] BYREF
  int v29; // [rsp+90h] [rbp-78h] BYREF
  LPCWSTR StringSid; // [rsp+98h] [rbp-70h] BYREF
  int v31; // [rsp+A0h] [rbp-68h] BYREF
  unsigned __int16 v32[2]; // [rsp+A4h] [rbp-64h] BYREF
  _QWORD v33[5]; // [rsp+A8h] [rbp-60h] BYREF
  __int16 v34; // [rsp+D0h] [rbp-38h]
  _QWORD v35[9]; // [rsp+D8h] [rbp-30h] BYREF
  int v36; // [rsp+120h] [rbp+18h] BYREF
  char v37; // [rsp+124h] [rbp+1Ch]
  char v38; // [rsp+128h] [rbp+20h] BYREF
  struct _GUID v39; // [rsp+138h] [rbp+30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]
  __int64 v41; // [rsp+180h] [rbp+78h] BYREF
  va_list va; // [rsp+180h] [rbp+78h]
  __int64 v43; // [rsp+188h] [rbp+80h] BYREF
  va_list va1; // [rsp+188h] [rbp+80h]
  __int64 v45; // [rsp+190h] [rbp+88h] BYREF
  va_list va2; // [rsp+190h] [rbp+88h]
  __int64 v47; // [rsp+198h] [rbp+90h] BYREF
  va_list va3; // [rsp+198h] [rbp+90h]
  __int64 v49; // [rsp+1A0h] [rbp+98h] BYREF
  va_list va4; // [rsp+1A0h] [rbp+98h]
  __int64 v51; // [rsp+1A8h] [rbp+A0h] BYREF
  va_list va5; // [rsp+1A8h] [rbp+A0h]
  __int64 v53; // [rsp+1B0h] [rbp+A8h] BYREF
  va_list va6; // [rsp+1B0h] [rbp+A8h]
  va_list va7; // [rsp+1B8h] [rbp+B0h] BYREF

  va_start(va7, a3);
  va_start(va6, a3);
  va_start(va5, a3);
  va_start(va4, a3);
  va_start(va3, a3);
  va_start(va2, a3);
  va_start(va1, a3);
  va_start(va, a3);
  v41 = va_arg(va1, _QWORD);
  va_copy(va2, va1);
  v43 = va_arg(va2, _QWORD);
  va_copy(va3, va2);
  v45 = va_arg(va3, _QWORD);
  va_copy(va4, va3);
  v47 = va_arg(va4, _QWORD);
  va_copy(va5, va4);
  v49 = va_arg(va5, _QWORD);
  va_copy(va6, va5);
  v51 = va_arg(va6, _QWORD);
  va_copy(va7, va6);
  v53 = va_arg(va7, _QWORD);
  StringSid = a1;
  TenantId = 0;
  v28 = 0;
  v17 = 0;
  v18 = 0;
  v16 = 0;
  IsVsmAvailable = VsmUtils::IsVsmAvailable((VsmUtils *)&v16, a2);
  if ( IsVsmAvailable < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x1D8,
      (unsigned int)"onecore\\ds\\security\\ngc\\cryptngc\\dll\\ngcpinmanagement.cpp",
      (const char *)(unsigned int)IsVsmAvailable,
      v14);
  v36 = 0;
  v37 = 0;
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v36);
  if ( (unsigned int)dword_18006E000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_18006E000, 0x400000000000LL) )
  {
    v20 = v18;
    v21 = v17;
    v22 = v16;
    IsNgcInVsmEnabled = NgcUtils::IsNgcInVsmEnabled(v4);
    v24 = 0;
    IsSecureBioEnabled = NgcUtils::IsSecureBioEnabled(v5);
    v19 = TenantId;
    Sid = (PSID)16779264;
    if ( !v37 || (IsZero = _tlgGuidIsZero(&v39), v7 = &v39, IsZero) )
      LODWORD(v7) = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(
      (unsigned int)&dword_18006E000,
      (unsigned int)&word_1800602B6,
      (unsigned int)&v38,
      (_DWORD)v7,
      (__int64)&v19,
      (__int64)&Sid,
      (__int64)&IsSecureBioEnabled,
      (__int64)&v24,
      (__int64)&IsNgcInVsmEnabled,
      (__int64)&v22,
      (__int64)&v21,
      (__int64)&v20);
  }
  v34 = 256;
  v33[0] = &v36;
  v33[1] = &TenantId;
  v33[2] = &v16;
  v33[3] = &v17;
  v33[4] = &v18;
  if ( !StringSid )
    goto LABEL_12;
  if ( !v51 )
  {
    if ( v53 )
      goto LABEL_12;
LABEL_16:
    *(_DWORD *)v32 = 0;
    v31 = 0;
    v29 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v28,
      0);
    TenantId = I_NgcGetTenantId(&v28);
    if ( TenantId >= 0 )
    {
      TenantId = PolicyManager::QueryIsNgcEnabled(
                   StringSid,
                   v28,
                   v32,
                   (enum _NGC_ENABLED_STATE *)&v31,
                   (enum _NGC_POLICY_SOURCE *)&v29);
      if ( TenantId >= 0 )
      {
        v17 = (v29 & 2) != 0;
        v18 = (v29 & 8) != 0;
        if ( (v29 & 2) != 0 )
        {
          v19 = 0;
          Sid = 0;
          if ( ConvertStringSidToSidW(StringSid, &Sid) )
          {
            TenantId = NgcUtils::GetUserAccountType((NgcUtils *)Sid, &v19, v11);
            if ( TenantId < 0 )
            {
              if ( (unsigned int)dword_18006E000 > 3 )
              {
                v26 = TenantId;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                  (unsigned int)&dword_18006E000,
                  (unsigned int)&word_1800601F6,
                  0,
                  0,
                  (__int64)&v26);
              }
              TenantId = 0;
            }
          }
          else
          {
            LastError = GetLastError();
            if ( (unsigned int)dword_18006E000 > 3 )
            {
              v26 = LastError;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
                (unsigned int)&dword_18006E000,
                (unsigned int)&unk_180060228,
                0,
                0,
                (__int64)&v26);
            }
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
          if ( (unsigned int)(v19 - 3) <= 1 )
            LODWORD(v47) = v47 | 2;
        }
        v35[0] = &StringSid;
        va_copy((va_list)&v35[1], va);
        va_copy((va_list)&v35[2], va1);
        va_copy((va_list)&v35[3], va2);
        va_copy((va_list)&v35[4], va3);
        va_copy((va_list)&v35[5], va4);
        va_copy((va_list)&v35[6], va5);
        va_copy((va_list)&v35[7], va6);
        va_copy((va_list)&v35[8], va7);
        v13 = HResultErrorContract__lambda_33a78af50c2f5186637b6bd53001fd04_(v35);
        TenantId = v13;
        if ( v13 < 0 )
        {
          if ( (unsigned int)dword_18006E000 > 2 )
          {
            v26 = TenantId;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
              (unsigned int)&dword_18006E000,
              (unsigned int)word_1800601CA,
              0,
              0,
              (__int64)&v26);
          }
          v13 = TenantId;
        }
        v8 = HResultToSecurityStatus(v13);
        goto LABEL_13;
      }
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v10 = &word_180060256;
        goto LABEL_22;
      }
    }
    else if ( (unsigned int)dword_18006E000 > 2 )
    {
      v10 = &word_18006028E;
LABEL_22:
      v19 = TenantId;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18006E000,
        (_DWORD)v10,
        0,
        0,
        (__int64)&v19);
    }
    v8 = TenantId;
    goto LABEL_14;
  }
  if ( v53 )
    goto LABEL_16;
LABEL_12:
  v8 = -2146893785;
LABEL_13:
  TenantId = v8;
LABEL_14:
  wil::details::ScopeExitFnGuard__lambda_879929235e0af2658290990810c5524f___::operator()(v33);
  _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v36);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v28);
  return v8;
}

```

## disassembly

```asm
0x1800374f0  mov     rax, rsp
0x1800374f3  mov     [rax+10h], rbx
0x1800374f7  mov     [rax+18h], rdi
0x1800374fb  mov     [rax+20h], r9
0x1800374ff  push    rbp
0x180037500  lea     rbp, [rax-58h]
0x180037504  sub     rsp, 150h
0x18003750b  mov     rax, cs:__security_cookie
0x180037512  xor     rax, rsp
0x180037515  mov     [rbp+50h+var_10], rax
0x180037519  xor     ebx, ebx
0x18003751b  mov     [rbp+50h+StringSid], rcx
0x18003751f  lea     rcx, [rsp+150h+var_EC]; this
0x180037524  mov     [rsp+150h+var_F0], ebx
0x180037528  mov     [rbp+50h+var_D0], rbx
0x18003752c  mov     [rsp+150h+var_EB], bl
0x180037530  mov     [rsp+150h+var_EA], bl
0x180037534  mov     [rsp+150h+var_EC], bl
0x180037538  call    ?IsVsmAvailable@VsmUtils@@YAJPEA_N@Z; VsmUtils::IsVsmAvailable(bool *)
0x18003753d  test    eax, eax
0x18003753f  jns     short loc_180037559
0x180037541  mov     rcx, [rbp+58h]; this
0x180037545  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\ngc\\cryptngc\\d"...
0x18003754c  mov     r9d, eax; char *
0x18003754f  mov     edx, 1D8h; void *
0x180037554  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180037559  lea     rcx, [rbp+50h+var_38]
0x18003755d  mov     [rbp+50h+var_38], ebx
0x180037560  mov     [rbp+50h+var_34], bl
0x180037563  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x180037568  mov     eax, cs:dword_18006E000
0x18003756e  lea     rdi, dword_18006E000
0x180037575  cmp     eax, 5
0x180037578  jbe     loc_180037653
0x18003757e  mov     rdx, 400000000000h
0x180037588  mov     rcx, rdi
0x18003758b  call    _tlgKeywordOn
0x180037590  test    al, al
0x180037592  jz      loc_180037653
0x180037598  mov     al, [rsp+150h+var_EA]
0x18003759c  mov     byte ptr [rsp+150h+var_E4], al
0x1800375a0  mov     al, [rsp+150h+var_EB]
0x1800375a4  mov     byte ptr [rsp+150h+var_E4+1], al
0x1800375a8  mov     al, [rsp+150h+var_EC]
0x1800375ac  mov     byte ptr [rsp+150h+var_E4+2], al
0x1800375b0  call    ?IsNgcInVsmEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNgcInVsmEnabled(void)
0x1800375b5  mov     byte ptr [rsp+150h+var_E4+3], al
0x1800375b9  mov     byte ptr [rsp+150h+var_E0], bl
0x1800375bd  call    ?IsSecureBioEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsSecureBioEnabled(void)
0x1800375c2  mov     byte ptr [rsp+150h+var_E0+1], al
0x1800375c6  mov     eax, [rsp+150h+var_F0]
0x1800375ca  mov     [rsp+150h+var_E8], eax
0x1800375ce  mov     [rsp+150h+Sid], 1000800h
0x1800375d7  cmp     [rbp+50h+var_34], bl
0x1800375da  jz      short loc_1800375ED
0x1800375dc  lea     rcx, [rbp+50h+var_20]; struct _GUID *
0x1800375e0  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x1800375e5  lea     r9, [rbp+50h+var_20]
0x1800375e9  test    al, al
0x1800375eb  jz      short loc_1800375F0
0x1800375ed  mov     r9, rbx
0x1800375f0  lea     rax, [rsp+150h+var_E4]
0x1800375f5  mov     rcx, rdi
0x1800375f8  mov     qword ptr [rsp+150h+var_F8], rax
0x1800375fd  lea     r8, [rbp+50h+var_30]
0x180037601  lea     rax, [rsp+150h+var_E4+1]
0x180037606  mov     [rsp+150h+var_100], rax
0x18003760b  lea     rdx, word_1800602B6
0x180037612  lea     rax, [rsp+150h+var_E4+2]
0x180037617  mov     [rsp+150h+var_108], rax
0x18003761c  lea     rax, [rsp+150h+var_E4+3]
0x180037621  mov     [rsp+150h+var_110], rax
0x180037626  lea     rax, [rsp+150h+var_E0]
0x18003762b  mov     [rsp+150h+var_118], rax
0x180037630  lea     rax, [rsp+150h+var_E0+1]
0x180037635  mov     [rsp+150h+var_120], rax
0x18003763a  lea     rax, [rsp+150h+Sid]
0x18003763f  mov     [rsp+150h+var_128], rax; enum _NgcEnabledModifiers *
0x180037644  lea     rax, [rsp+150h+var_E8]
0x180037649  mov     [rsp+150h+var_130], rax
0x18003764e  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$00@@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$00@@55555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &)
0x180037653  lea     rax, [rbp+50h+var_38]
0x180037657  mov     [rbp+50h+var_88], 100h
0x18003765d  mov     [rbp+50h+var_B0], rax
0x180037661  lea     rax, [rsp+150h+var_F0]
0x180037666  mov     [rbp+50h+var_A8], rax
0x18003766a  lea     rax, [rsp+150h+var_EC]
0x18003766f  mov     [rbp+50h+var_A0], rax
0x180037673  lea     rax, [rsp+150h+var_EB]
0x180037678  mov     [rbp+50h+var_98], rax
0x18003767c  lea     rax, [rsp+150h+var_EA]
0x180037681  mov     [rbp+50h+var_90], rax
0x180037685  cmp     [rbp+50h+StringSid], rbx
0x180037689  jz      short loc_18003769D
0x18003768b  cmp     [rbp+50h+arg_40], rbx
0x180037692  jz      short loc_1800376E4
0x180037694  cmp     [rbp+50h+arg_48], rbx
0x18003769b  jnz     short loc_1800376ED
0x18003769d  mov     ebx, 80090027h
0x1800376a2  mov     [rsp+150h+var_F0], ebx
0x1800376a6  lea     rcx, [rbp+50h+var_B0]
0x1800376aa  call    wil__details__ScopeExitFnGuard__lambda_879929235e0af2658290990810c5524f_____operator__
0x1800376af  lea     rcx, [rbp+50h+var_38]
0x1800376b3  call    ??1?$_TlgActivityBase@V?$TraceLoggingThreadActivity@$1?g_logProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingThreadActivity<&_tlgProvider_t const * const g_logProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x1800376b8  lea     rcx, [rbp+50h+var_D0]; void *
0x1800376bc  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800376c1  mov     eax, ebx
0x1800376c3  mov     rcx, [rbp+50h+var_10]
0x1800376c7  xor     rcx, rsp; StackCookie
0x1800376ca  call    __security_check_cookie
0x1800376cf  lea     r11, [rsp+150h+var_s0]
0x1800376d7  mov     rbx, [r11+18h]
0x1800376db  mov     rdi, [r11+20h]
0x1800376df  mov     rsp, r11
0x1800376e2  pop     rbp
0x1800376e3  retn
0x1800376e4  cmp     [rbp+50h+arg_48], rbx
0x1800376eb  jnz     short loc_18003769D
0x1800376ed  xor     edx, edx
0x1800376ef  mov     dword ptr [rbp+50h+var_B4], ebx
0x1800376f2  lea     rcx, [rbp+50h+var_D0]
0x1800376f6  mov     [rbp+50h+var_B8], ebx
0x1800376f9  mov     [rbp+50h+var_C8], ebx
0x1800376fc  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180037701  lea     rcx, [rbp+50h+var_D0]; unsigned __int16 **
0x180037705  call    ?I_NgcGetTenantId@@YAJPEAPEAG@Z; I_NgcGetTenantId(ushort * *)
0x18003770a  mov     [rsp+150h+var_F0], eax
0x18003770e  test    eax, eax
0x180037710  jns     short loc_180037726
0x180037712  mov     eax, cs:dword_18006E000
0x180037718  cmp     eax, 2
0x18003771b  jbe     short loc_18003777E
0x18003771d  lea     rdx, word_18006028E
0x180037724  jmp     short loc_18003775E
0x180037726  mov     rdx, [rbp+50h+var_D0]; unsigned __int16 *
0x18003772a  lea     rax, [rbp+50h+var_C8]
0x18003772e  mov     rcx, [rbp+50h+StringSid]; this
0x180037732  lea     r9, [rbp+50h+var_B8]; enum _NGC_ENABLED_STATE *
0x180037736  lea     r8, [rbp+50h+var_B4]; unsigned __int16 *
0x18003773a  mov     [rsp+150h+var_130], rax; enum _NGC_POLICY_SOURCE *
0x18003773f  call    ?QueryIsNgcEnabled@PolicyManager@@YAJPEBG0PEAW4_NGC_ENABLED_STATE@@PEAW4_NGC_POLICY_SOURCE@@PEAW4_NgcEnabledModifiers@@@Z; PolicyManager::QueryIsNgcEnabled(ushort const *,ushort const *,_NGC_ENABLED_STATE *,_NGC_POLICY_SOURCE *,_NgcEnabledModifiers *)
0x180037744  mov     [rsp+150h+var_F0], eax
0x180037748  test    eax, eax
0x18003774a  jns     short loc_180037787
0x18003774c  mov     eax, cs:dword_18006E000
0x180037752  cmp     eax, 2
0x180037755  jbe     short loc_18003777E
0x180037757  lea     rdx, word_180060256
0x18003775e  mov     eax, [rsp+150h+var_F0]
0x180037762  xor     r9d, r9d
0x180037765  mov     [rsp+150h+var_E8], eax
0x180037769  xor     r8d, r8d
0x18003776c  lea     rax, [rsp+150h+var_E8]
0x180037771  mov     rcx, rdi
0x180037774  mov     [rsp+150h+var_130], rax
0x180037779  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003777e  mov     ebx, [rsp+150h+var_F0]
0x180037782  jmp     loc_1800376A6
0x180037787  mov     eax, [rbp+50h+var_C8]
0x18003778a  bt      eax, 1
0x18003778e  mov     ecx, eax
0x180037790  setb    [rsp+150h+var_EB]
0x180037795  shr     eax, 3
0x180037798  and     al, 1
0x18003779a  mov     [rsp+150h+var_EA], al
0x18003779e  bt      ecx, 1
0x1800377a2  jnb     loc_180037864
0x1800377a8  mov     rcx, [rbp+50h+StringSid]; StringSid
0x1800377ac  lea     rdx, [rsp+150h+Sid]; Sid
0x1800377b1  mov     [rsp+150h+var_E8], ebx
0x1800377b5  mov     [rsp+150h+Sid], rbx
0x1800377ba  call    cs:__imp_ConvertStringSidToSidW
0x1800377c0  test    eax, eax
0x1800377c2  jz      short loc_180037813
0x1800377c4  mov     rcx, [rsp+150h+Sid]; this
0x1800377c9  lea     rdx, [rsp+150h+var_E8]; void *
0x1800377ce  call    ?GetUserAccountType@NgcUtils@@YAJPEAXPEAW4NgcUserAccountType@@@Z; NgcUtils::GetUserAccountType(void *,NgcUserAccountType *)
0x1800377d3  mov     [rsp+150h+var_F0], eax
0x1800377d7  test    eax, eax
0x1800377d9  jns     short loc_180037847
0x1800377db  mov     eax, cs:dword_18006E000
0x1800377e1  cmp     eax, 3
0x1800377e4  jbe     short loc_18003780D
0x1800377e6  mov     eax, [rsp+150h+var_F0]
0x1800377ea  lea     rdx, word_1800601F6
0x1800377f1  mov     dword ptr [rsp+150h+var_E0+4], eax
0x1800377f5  xor     r9d, r9d
0x1800377f8  lea     rax, [rsp+150h+var_E0+4]
0x1800377fd  xor     r8d, r8d
0x180037800  mov     rcx, rdi
0x180037803  mov     [rsp+150h+var_130], rax
0x180037808  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003780d  mov     [rsp+150h+var_F0], ebx
0x180037811  jmp     short loc_180037847
0x180037813  call    cs:__imp_GetLastError
0x180037819  mov     ecx, cs:dword_18006E000
0x18003781f  cmp     ecx, 3
0x180037822  jbe     short loc_180037847
0x180037824  mov     dword ptr [rsp+150h+var_E0+4], eax
0x180037828  lea     rdx, unk_180060228
0x18003782f  lea     rax, [rsp+150h+var_E0+4]
0x180037834  xor     r9d, r9d
0x180037837  xor     r8d, r8d
0x18003783a  mov     [rsp+150h+var_130], rax
0x18003783f  mov     rcx, rdi
0x180037842  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180037847  lea     rcx, [rsp+150h+Sid]; void *
0x18003784c  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180037851  mov     eax, [rsp+150h+var_E8]
0x180037855  add     eax, 0FFFFFFFDh
0x180037858  cmp     eax, 1
0x18003785b  ja      short loc_180037864
0x18003785d  or      dword ptr [rbp+50h+arg_30], 2
0x180037864  lea     rax, [rbp+50h+StringSid]
0x180037868  mov     [rbp+50h+var_80], rax
0x18003786c  lea     rcx, [rbp+50h+var_80]
0x180037870  lea     rax, [rbp+50h+arg_18]
0x180037874  mov     [rbp+50h+var_78], rax
0x180037878  lea     rax, [rbp+50h+arg_20]
0x18003787f  mov     [rbp+50h+var_70], rax
0x180037883  lea     rax, [rbp+50h+arg_28]
0x18003788a  mov     [rbp+50h+var_68], rax
0x18003788e  lea     rax, [rbp+50h+arg_30]
0x180037895  mov     [rbp+50h+var_60], rax
0x180037899  lea     rax, [rbp+50h+arg_38]
0x1800378a0  mov     [rbp+50h+var_58], rax
0x1800378a4  lea     rax, [rbp+50h+arg_40]
0x1800378ab  mov     [rbp+50h+var_50], rax
0x1800378af  lea     rax, [rbp+50h+arg_48]
0x1800378b6  mov     [rbp+50h+var_48], rax
0x1800378ba  lea     rax, [rbp+50h+arg_50]
0x1800378c1  mov     [rbp+50h+var_40], rax
0x1800378c5  call    HResultErrorContract__lambda_33a78af50c2f5186637b6bd53001fd04___; HResultErrorContract__lambda_33a78af50c2f5186637b6bd53001fd04_
0x1800378ca  mov     [rsp+150h+var_F0], eax
0x1800378ce  test    eax, eax
0x1800378d0  jns     short loc_180037908
0x1800378d2  mov     eax, cs:dword_18006E000
0x1800378d8  cmp     eax, 2
0x1800378db  jbe     short loc_180037904
0x1800378dd  mov     eax, [rsp+150h+var_F0]
0x1800378e1  lea     rdx, word_1800601CA
0x1800378e8  mov     dword ptr [rsp+150h+var_E0+4], eax
0x1800378ec  xor     r9d, r9d
0x1800378ef  lea     rax, [rsp+150h+var_E0+4]
0x1800378f4  xor     r8d, r8d
0x1800378f7  mov     rcx, rdi
0x1800378fa  mov     [rsp+150h+var_130], rax
0x1800378ff  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180037904  mov     eax, [rsp+150h+var_F0]
0x180037908  mov     ecx, eax; int
0x18003790a  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18003790f  mov     ebx, eax
0x180037911  jmp     loc_1800376A2
```
