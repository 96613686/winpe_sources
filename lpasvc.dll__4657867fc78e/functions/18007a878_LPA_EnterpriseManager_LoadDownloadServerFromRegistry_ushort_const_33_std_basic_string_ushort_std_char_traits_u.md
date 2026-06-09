# LPA::EnterpriseManager::LoadDownloadServerFromRegistry(ushort const (*)[33],std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,bool &,LPAENTERPRISEDISCOVERYSTATE &,ulong &,ulong &,ulong &,unsigned __int64 &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &,LPAERROR &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18007a878`
- end: `0x18007ac34`
- name: `?LoadDownloadServerFromRegistry@EnterpriseManager@LPA@@AEAAJPEAY0CB@$$CBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEA_NAEAW4LPAENTERPRISEDISCOVERYSTATE@@AEAK44AEA_K1AEAW4LPAERROR@@1@Z`
- size: `956`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, LPBYTE, LPBYTE lpData, LPBYTE, unsigned __int16 *, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180078dd0`
- `0x18007ac3c`

## callees

- `0x1800017c8`
- `0x1800028e0`
- `0x18000df90`
- `0x180071344`
- `0x180071650`
- `0x18007430c`
- `0x1800743c4`
- `0x180076cd0`
- `0x180079550`
- `0x180079b84`
- `0x18007a320`
- `0x18007a4d8`
- `0x18007a878`
- `0x180080dfc`
- `0x180080f38`

## string_xrefs

- `0x18007aa1b`: `LpaServiceEnterpriseManager`
- `0x18007abb6`: `LpaServiceEnterpriseManager`
- `0x18007aa0f`: `LPA::EnterpriseManager::LoadDownloadServerFromRegistry`
- `0x18007abaa`: `LPA::EnterpriseManager::LoadDownloadServerFromRegistry`
- `0x18007aa82`: `DownloadsAttempted`
- `0x18007aa65`: `MaximumAttempts`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall LPA::EnterpriseManager::LoadDownloadServerFromRegistry(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        char *a4,
        char *a5,
        LPBYTE a6,
        LPBYTE lpData,
        LPBYTE a8,
        unsigned __int16 *a9,
        __int64 a10,
        _DWORD *a11,
        __int64 a12)
{
  const WCHAR *v13; // rax
  int StringFromRegistry; // ebx
  __int64 v15; // rax
  __int64 v16; // rax
  const WCHAR *v17; // rax
  unsigned int *v18; // r9
  const WCHAR *v19; // rax
  unsigned int *v20; // r9
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  const WCHAR *v24; // rbx
  unsigned int *v25; // r9
  unsigned int *v26; // r9
  const unsigned __int16 *v27; // rdx
  unsigned __int64 *v28; // r9
  unsigned int *v29; // r9
  int DwordFromRegistry; // eax
  int v31; // ecx
  const WCHAR *v32; // rax
  unsigned int *v33; // r9
  const WCHAR *v34; // rax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  BYTE Data[8]; // [rsp+50h] [rbp-A1h] BYREF
  _DWORD *v40; // [rsp+58h] [rbp-99h] BYREF
  char *v41; // [rsp+60h] [rbp-91h] BYREF
  char *v42; // [rsp+68h] [rbp-89h] BYREF
  __int64 v43; // [rsp+70h] [rbp-81h] BYREF
  const char *v44; // [rsp+78h] [rbp-79h] BYREF
  _OWORD v45[2]; // [rsp+80h] [rbp-71h] BYREF
  _BYTE v46[32]; // [rsp+A0h] [rbp-51h] BYREF
  _BYTE v47[32]; // [rsp+C0h] [rbp-31h] BYREF

  v41 = a4;
  v42 = a5;
  v40 = a11;
  v43 = a12;
  v45[0] = 0;
  v45[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v45[0]) = 0;
  LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDownloadServerKey(a1, a2, v45);
  if ( *(_QWORD *)(a3 + 16) )
  {
    v15 = std::operator+<unsigned short>(v47, v45, L"\\");
    v16 = std::operator+<unsigned short>(v46, v15, a3);
    std::wstring::operator=(v45, v16);
    std::wstring::_Tidy_deallocate(v46);
    std::wstring::_Tidy_deallocate(v47);
  }
  else
  {
    v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
    StringFromRegistry = CommonUtil::GetStringFromRegistry(v13, L"ServerName");
    if ( StringFromRegistry < 0 )
      goto LABEL_7;
  }
  *(_DWORD *)Data = 0;
  v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
  StringFromRegistry = CommonUtil::GetDwordFromRegistry(v17, L"Enable", Data, v18);
  if ( StringFromRegistry >= 0 )
  {
    *v41 = *(_DWORD *)Data != 0;
    *(_DWORD *)Data = 0;
    v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
    StringFromRegistry = CommonUtil::GetDwordFromRegistry(v19, L"State", Data, v20);
    *(_DWORD *)v42 = *(_DWORD *)Data;
  }
LABEL_7:
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl) )
  {
    if ( StringFromRegistry < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v40) = StringFromRegistry;
        v42 = "LPA::EnterpriseManager::LoadDownloadServerFromRegistry";
        v41 = "LpaServiceEnterpriseManager";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          v21,
          (unsigned int)&unk_18012BAC8,
          v22,
          v23,
          (__int64)&v41,
          (__int64)&v42,
          (__int64)&v40);
      }
      goto LABEL_28;
    }
    v24 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
    if ( (int)CommonUtil::GetDwordFromRegistry(v24, L"MaximumAttempts", lpData, v25) < 0 )
      *(_DWORD *)lpData = 3;
    if ( (int)CommonUtil::GetDwordFromRegistry(v24, L"DownloadsAttempted", a8, v26) < 0 )
      *(_DWORD *)a8 = 0;
    if ( (int)CommonUtil::GetQuadFromRegistry(v24, v27, a9, v28) < 0 )
      *(_QWORD *)a9 = 0;
    if ( (int)CommonUtil::GetStringFromRegistry(v24, L"ProfileId") < 0 )
      std::wstring::assign(a10, &qword_1801130E8);
    *(_DWORD *)Data = 0;
    DwordFromRegistry = CommonUtil::GetDwordFromRegistry(v24, L"ErrorDetail", Data, v29);
    v31 = 0;
    if ( DwordFromRegistry >= 0 )
      v31 = *(_DWORD *)Data;
    *v40 = v31;
    *(_DWORD *)a6 = 0;
  }
  else
  {
    if ( StringFromRegistry >= 0 )
    {
      v32 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
      StringFromRegistry = CommonUtil::GetDwordFromRegistry(v32, L"RetriesLeft", a6, v33);
    }
    *(_DWORD *)lpData = 0;
    *(_DWORD *)a8 = 0;
    *(_QWORD *)a9 = 0;
    std::wstring::assign(a10, &qword_1801130E8);
    *v40 = 0;
    if ( StringFromRegistry < 0 )
      goto LABEL_26;
  }
  v34 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
  StringFromRegistry = CommonUtil::GetStringFromRegistry(v34, L"AccountId");
LABEL_26:
  if ( (unsigned int)CallbackContext > 4 )
  {
    LODWORD(v40) = StringFromRegistry;
    v43 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
    v42 = (char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3);
    *(_DWORD *)Data = *(_DWORD *)a6;
    v41 = "LPA::EnterpriseManager::LoadDownloadServerFromRegistry";
    v44 = "LpaServiceEnterpriseManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v35,
      (unsigned int)&byte_18012BA2F,
      v36,
      v37,
      (__int64)&v44,
      (__int64)&v41,
      (__int64)Data,
      (__int64)&v42,
      (__int64)&v43,
      (__int64)&v40);
  }
LABEL_28:
  std::wstring::_Tidy_deallocate(v45);
  return (unsigned int)StringFromRegistry;
}

```

## disassembly

```asm
0x18007a878  push    rbp
0x18007a87a  push    rbx
0x18007a87b  push    rsi
0x18007a87c  push    rdi
0x18007a87d  push    r12
0x18007a87f  push    r13
0x18007a881  push    r14
0x18007a883  push    r15
0x18007a885  lea     rbp, [rsp-7]
0x18007a88a  sub     rsp, 0F8h
0x18007a891  mov     rax, cs:__security_cookie
0x18007a898  xor     rax, rsp
0x18007a89b  mov     [rbp+3Fh+var_50], rax
0x18007a89f  mov     [rsp+130h+var_D0], r9
0x18007a8a4  mov     r13, r8
0x18007a8a7  mov     rax, [rbp+3Fh+arg_20]
0x18007a8ab  mov     [rsp+130h+var_C8], rax
0x18007a8b0  mov     r12, [rbp+3Fh+arg_28]
0x18007a8b4  mov     r14, [rbp+3Fh+lpData]
0x18007a8b8  mov     rsi, [rbp+3Fh+arg_38]
0x18007a8bf  mov     rdi, [rbp+3Fh+arg_40]
0x18007a8c6  mov     r15, [rbp+3Fh+arg_48]
0x18007a8cd  mov     rax, [rbp+3Fh+arg_50]
0x18007a8d4  mov     [rsp+130h+var_D8], rax
0x18007a8d9  mov     rax, [rbp+3Fh+arg_58]
0x18007a8e0  mov     [rsp+130h+var_C0], rax
0x18007a8e5  xorps   xmm0, xmm0
0x18007a8e8  movups  [rbp+3Fh+var_B0], xmm0
0x18007a8ec  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007a8f4  movdqu  [rbp+3Fh+var_A0], xmm1
0x18007a8f9  xor     eax, eax
0x18007a8fb  mov     word ptr [rbp+3Fh+var_B0], ax
0x18007a8ff  lea     r8, [rbp+3Fh+var_B0]
0x18007a903  call    ?GetEnterpriseSettingsEuiccsDownloadServerKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDownloadServerKey(ushort const (&)[33],std::wstring &)
0x18007a908  cmp     qword ptr [r13+10h], 0
0x18007a90d  jnz     short loc_18007A935
0x18007a90f  lea     rcx, [rbp+3Fh+var_B0]
0x18007a913  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a918  mov     rcx, rax; lpSubKey
0x18007a91b  mov     r8, r13
0x18007a91e  lea     rdx, aServername; "ServerName"
0x18007a925  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007a92a  mov     ebx, eax
0x18007a92c  test    eax, eax
0x18007a92e  jns     short loc_18007A978
0x18007a930  jmp     loc_18007A9E4
0x18007a935  lea     r8, asc_1801118E4; "\\"
0x18007a93c  lea     rdx, [rbp+3Fh+var_B0]
0x18007a940  lea     rcx, [rbp+3Fh+var_70]
0x18007a944  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18007a949  nop
0x18007a94a  mov     r8, r13
0x18007a94d  mov     rdx, rax
0x18007a950  lea     rcx, [rbp+3Fh+var_90]
0x18007a954  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x18007a959  mov     rdx, rax
0x18007a95c  lea     rcx, [rbp+3Fh+var_B0]
0x18007a960  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007a965  lea     rcx, [rbp+3Fh+var_90]
0x18007a969  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a96e  nop
0x18007a96f  lea     rcx, [rbp+3Fh+var_70]
0x18007a973  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007a978  mov     dword ptr [rsp+130h+Data], 0
0x18007a980  lea     rcx, [rbp+3Fh+var_B0]
0x18007a984  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a989  mov     rcx, rax; lpSubKey
0x18007a98c  lea     r8, [rsp+130h+Data]; lpData
0x18007a991  lea     rdx, aEnable; "Enable"
0x18007a998  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007a99d  mov     ebx, eax
0x18007a99f  test    eax, eax
0x18007a9a1  js      short loc_18007A9E4
0x18007a9a3  cmp     dword ptr [rsp+130h+Data], 0
0x18007a9a8  setnz   al
0x18007a9ab  mov     rcx, [rsp+130h+var_D0]
0x18007a9b0  mov     [rcx], al
0x18007a9b2  mov     dword ptr [rsp+130h+Data], 0
0x18007a9ba  lea     rcx, [rbp+3Fh+var_B0]
0x18007a9be  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007a9c3  mov     rcx, rax; lpSubKey
0x18007a9c6  lea     r8, [rsp+130h+Data]; lpData
0x18007a9cb  lea     rdx, aState; "State"
0x18007a9d2  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007a9d7  mov     ebx, eax
0x18007a9d9  mov     eax, dword ptr [rsp+130h+Data]
0x18007a9dd  mov     rcx, [rsp+130h+var_C8]
0x18007a9e2  mov     [rcx], eax
0x18007a9e4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY> `wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl(void)'::`2'::impl
0x18007a9eb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(void)
0x18007a9f0  test    al, al
0x18007a9f2  jz      loc_18007AB02
0x18007a9f8  test    ebx, ebx
0x18007a9fa  jns     short loc_18007AA56
0x18007a9fc  mov     eax, cs:CallbackContext
0x18007aa02  cmp     eax, 2
0x18007aa05  jbe     loc_18007AC09
0x18007aa0b  mov     dword ptr [rsp+130h+var_D8], ebx
0x18007aa0f  lea     rax, aLpaEnterprisem_18; "LPA::EnterpriseManager::LoadDownloadSer"...
0x18007aa16  mov     [rsp+130h+var_C8], rax
0x18007aa1b  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007aa22  mov     [rsp+130h+var_D0], rax
0x18007aa27  lea     rax, [rsp+130h+var_D8]
0x18007aa2c  mov     [rsp+130h+var_100], rax
0x18007aa31  lea     rax, [rsp+130h+var_C8]
0x18007aa36  mov     [rsp+130h+var_108], rax
0x18007aa3b  lea     rax, [rsp+130h+var_D0]
0x18007aa40  mov     [rsp+130h+var_110], rax
0x18007aa45  lea     rdx, unk_18012BAC8
0x18007aa4c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18007aa51  jmp     loc_18007AC09
0x18007aa56  lea     rcx, [rbp+3Fh+var_B0]
0x18007aa5a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007aa5f  mov     rbx, rax
0x18007aa62  mov     r8, r14; lpData
0x18007aa65  lea     rdx, aMaximumattempt; "MaximumAttempts"
0x18007aa6c  mov     rcx, rax; lpSubKey
0x18007aa6f  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007aa74  test    eax, eax
0x18007aa76  jns     short loc_18007AA7F
0x18007aa78  mov     dword ptr [r14], 3
0x18007aa7f  mov     r8, rsi; lpData
0x18007aa82  lea     rdx, aDownloadsattem; "DownloadsAttempted"
0x18007aa89  mov     rcx, rbx; lpSubKey
0x18007aa8c  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007aa91  xor     r14d, r14d
0x18007aa94  test    eax, eax
0x18007aa96  jns     short loc_18007AA9B
0x18007aa98  mov     [rsi], r14d
0x18007aa9b  mov     r8, rdi; unsigned __int16 *
0x18007aa9e  mov     rcx, rbx; lpSubKey
0x18007aaa1  call    ?GetQuadFromRegistry@CommonUtil@@YAJPEBG0AEA_K@Z; CommonUtil::GetQuadFromRegistry(ushort const *,ushort const *,unsigned __int64 &)
0x18007aaa6  test    eax, eax
0x18007aaa8  jns     short loc_18007AAAD
0x18007aaaa  mov     [rdi], r14
0x18007aaad  mov     r8, r15
0x18007aab0  lea     rdx, aProfileid; "ProfileId"
0x18007aab7  mov     rcx, rbx; lpSubKey
0x18007aaba  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007aabf  test    eax, eax
0x18007aac1  jns     short loc_18007AAD2
0x18007aac3  lea     rdx, qword_1801130E8
0x18007aaca  mov     rcx, r15
0x18007aacd  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18007aad2  mov     dword ptr [rsp+130h+Data], r14d
0x18007aad7  lea     r8, [rsp+130h+Data]; lpData
0x18007aadc  lea     rdx, aErrordetail; "ErrorDetail"
0x18007aae3  mov     rcx, rbx; lpSubKey
0x18007aae6  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007aaeb  mov     ecx, r14d
0x18007aaee  test    eax, eax
0x18007aaf0  cmovns  ecx, dword ptr [rsp+130h+Data]
0x18007aaf5  mov     rax, [rsp+130h+var_D8]
0x18007aafa  mov     [rax], ecx
0x18007aafc  mov     [r12], r14d
0x18007ab00  jmp     short loc_18007AB55
0x18007ab02  test    ebx, ebx
0x18007ab04  js      short loc_18007AB23
0x18007ab06  lea     rcx, [rbp+3Fh+var_B0]
0x18007ab0a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ab0f  mov     rcx, rax; lpSubKey
0x18007ab12  mov     r8, r12; lpData
0x18007ab15  lea     rdx, aRetriesleft; "RetriesLeft"
0x18007ab1c  call    ?GetDwordFromRegistry@CommonUtil@@YAJPEBG0AEAK@Z; CommonUtil::GetDwordFromRegistry(ushort const *,ushort const *,ulong &)
0x18007ab21  mov     ebx, eax
0x18007ab23  mov     dword ptr [r14], 0
0x18007ab2a  mov     dword ptr [rsi], 0
0x18007ab30  mov     qword ptr [rdi], 0
0x18007ab37  lea     rdx, qword_1801130E8
0x18007ab3e  mov     rcx, r15
0x18007ab41  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18007ab46  mov     rax, [rsp+130h+var_D8]
0x18007ab4b  mov     dword ptr [rax], 0
0x18007ab51  test    ebx, ebx
0x18007ab53  js      short loc_18007AB74
0x18007ab55  lea     rcx, [rbp+3Fh+var_B0]
0x18007ab59  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ab5e  mov     rcx, rax; lpSubKey
0x18007ab61  mov     r8, [rsp+130h+var_C0]
0x18007ab66  lea     rdx, aAccountid; "AccountId"
0x18007ab6d  call    ?GetStringFromRegistry@CommonUtil@@YAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CommonUtil::GetStringFromRegistry(ushort const *,ushort const *,std::wstring &)
0x18007ab72  mov     ebx, eax
0x18007ab74  mov     eax, cs:CallbackContext
0x18007ab7a  cmp     eax, 4
0x18007ab7d  jbe     loc_18007AC09
0x18007ab83  mov     dword ptr [rsp+130h+var_D8], ebx
0x18007ab87  lea     rcx, [rbp+3Fh+var_B0]
0x18007ab8b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ab90  mov     [rsp+130h+var_C0], rax
0x18007ab95  mov     rcx, r13
0x18007ab98  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007ab9d  mov     [rsp+130h+var_C8], rax
0x18007aba2  mov     eax, [r12]
0x18007aba6  mov     dword ptr [rsp+130h+Data], eax
0x18007abaa  lea     rax, aLpaEnterprisem_18; "LPA::EnterpriseManager::LoadDownloadSer"...
0x18007abb1  mov     [rsp+130h+var_D0], rax
0x18007abb6  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007abbd  mov     [rbp+3Fh+var_B8], rax
0x18007abc1  lea     rax, [rsp+130h+var_D8]
0x18007abc6  mov     [rsp+130h+var_E8], rax
0x18007abcb  lea     rax, [rsp+130h+var_C0]
0x18007abd0  mov     [rsp+130h+var_F0], rax
0x18007abd5  lea     rax, [rsp+130h+var_C8]
0x18007abda  mov     [rsp+130h+var_F8], rax
0x18007abdf  lea     rax, [rsp+130h+Data]
0x18007abe4  mov     [rsp+130h+var_100], rax
0x18007abe9  lea     rax, [rsp+130h+var_D0]
0x18007abee  mov     [rsp+130h+var_108], rax
0x18007abf3  lea     rax, [rbp+3Fh+var_B8]
0x18007abf7  mov     [rsp+130h+var_110], rax
0x18007abfc  lea     rdx, byte_18012BA2F
0x18007ac03  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@54@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18007ac08  nop
0x18007ac09  lea     rcx, [rbp+3Fh+var_B0]
0x18007ac0d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007ac12  mov     eax, ebx
0x18007ac14  mov     rcx, [rbp+3Fh+var_50]
0x18007ac18  xor     rcx, rsp; StackCookie
0x18007ac1b  call    __security_check_cookie
0x18007ac20  add     rsp, 0F8h
0x18007ac27  pop     r15
0x18007ac29  pop     r14
0x18007ac2b  pop     r13
0x18007ac2d  pop     r12
0x18007ac2f  pop     rdi
0x18007ac30  pop     rsi
0x18007ac31  pop     rbx
0x18007ac32  pop     rbp
0x18007ac33  retn
```
