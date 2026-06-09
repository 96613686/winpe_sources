# LPA::EnterpriseManager::SetDownloadServerToRegistry(ushort const (&)[33],ushort const *,bool,bool,bool,LPAENTERPRISEDISCOVERYSTATE,ulong,ulong,ulong,ushort * const,LPAERROR,ushort const *)

- ea: `0x18007e4f8`
- end: `0x18007ed66`
- name: `?SetDownloadServerToRegistry@EnterpriseManager@LPA@@AEAAJAEAY0CB@$$CBGPEBG_N22W4LPAENTERPRISEDISCOVERYSTATE@@KKKQEAGW4LPAERROR@@1@Z`
- size: `2158`
- prototype: ``
- caller_count: `3`
- callee_count: `21`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180078340`
- `0x180078f20`
- `0x18007da00`

## callees

- `0x180002a3c`
- `0x180002bdc`
- `0x18000df90`
- `0x18000ebf4`
- `0x18005cd20`
- `0x18006d990`
- `0x18006da14`
- `0x180071344`
- `0x180071650`
- `0x180074368`
- `0x1800743c4`
- `0x180076cd0`
- `0x180077758`
- `0x180079b14`
- `0x180079b84`
- `0x18007e4f8`
- `0x18007ed6c`
- `0x18007f774`
- `0x18007fdd8`
- `0x180080a28`
- `0x180080dfc`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18007e998`
- `msvcp_win!_Xtime_get_ticks` at `0x18007e998`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007e60b`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x18007e60b`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007e663`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007e713`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007e663`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x18007e713`

## string_xrefs

- `0x18007e77c`: `LpaServiceEnterpriseManager`
- `0x18007e7f3`: `LpaServiceEnterpriseManager`
- `0x18007eb99`: `LpaServiceEnterpriseManager`
- `0x18007ec91`: `LpaServiceEnterpriseManager`
- `0x18007e771`: `LPA::EnterpriseManager::SetDownloadServerToRegistry`
- `0x18007e7e8`: `LPA::EnterpriseManager::SetDownloadServerToRegistry`
- `0x18007eb8e`: `LPA::EnterpriseManager::SetDownloadServerToRegistry`
- `0x18007ec86`: `LPA::EnterpriseManager::SetDownloadServerToRegistry`
- `0x18007e984`: `DownloadsAttempted`
- `0x18007e957`: `MaximumAttempts`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall LPA::EnterpriseManager::SetDownloadServerToRegistry(
        LPA::EnterpriseManager *a1,
        CommonUtil *a2,
        struct _SECURITY_ATTRIBUTES *a3,
        unsigned __int8 a4,
        char a5,
        unsigned __int8 a6,
        unsigned int a7,
        unsigned int a8,
        unsigned int a9,
        unsigned int a10,
        unsigned __int16 *a11,
        unsigned int a12,
        struct _SECURITY_ATTRIBUTES *a13)
{
  unsigned int v13; // r13d
  int v17; // edi
  const WCHAR *v19; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  const WCHAR *v22; // rax
  unsigned __int16 *v23; // r8
  __int64 v24; // rax
  __int64 v25; // rax
  const WCHAR *v26; // rax
  LSTATUS v27; // eax
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  int *v31; // rax
  char *v32; // rdx
  __int64 v33; // rax
  __int64 v34; // rax
  const WCHAR *v35; // rax
  const unsigned __int16 *v36; // r8
  int v37; // ebx
  const WCHAR *v38; // rax
  const unsigned __int16 *v39; // r8
  unsigned __int16 *v40; // r8
  const WCHAR *v41; // rax
  const unsigned __int16 *v42; // r8
  const WCHAR *v43; // rax
  const unsigned __int16 *v44; // r8
  __int64 v45; // rdi
  const WCHAR *v46; // rax
  const unsigned __int16 *v47; // rdx
  const unsigned __int16 *v48; // r8
  const WCHAR *v49; // rax
  const unsigned __int16 *v50; // r8
  const WCHAR *v51; // rax
  const unsigned __int16 *v52; // r8
  unsigned __int64 v53; // r9
  const WCHAR *v54; // rdx
  const WCHAR *v55; // rax
  const unsigned __int16 *v56; // r8
  unsigned int v57; // r11d
  struct _SECURITY_ATTRIBUTES *v58; // rsi
  unsigned __int64 v59; // r9
  unsigned __int64 v60; // rdi
  __int64 v61; // rcx
  unsigned __int16 v62; // ax
  unsigned __int16 *v63; // rdi
  int v64; // ecx
  int v65; // r8d
  int v66; // r9d
  int v67; // ecx
  int v68; // r8d
  int v69; // r9d
  unsigned __int16 *v70; // [rsp+20h] [rbp-F0h]
  unsigned __int16 *v71; // [rsp+20h] [rbp-F0h]
  unsigned int v72; // [rsp+28h] [rbp-E8h]
  unsigned int v73; // [rsp+28h] [rbp-E8h]
  unsigned int v74; // [rsp+28h] [rbp-E8h]
  int *v75; // [rsp+58h] [rbp-B8h]
  int v77; // [rsp+94h] [rbp-7Ch] BYREF
  unsigned int v78; // [rsp+98h] [rbp-78h] BYREF
  int v79; // [rsp+9Ch] [rbp-74h] BYREF
  struct _SECURITY_ATTRIBUTES *v80; // [rsp+A0h] [rbp-70h] BYREF
  const char *v81; // [rsp+A8h] [rbp-68h] BYREF
  const char *v82; // [rsp+B0h] [rbp-60h] BYREF
  const char *v83; // [rsp+B8h] [rbp-58h] BYREF
  unsigned __int16 *v84; // [rsp+C0h] [rbp-50h] BYREF
  unsigned __int16 *v85; // [rsp+C8h] [rbp-48h] BYREF
  unsigned __int16 *v86; // [rsp+D0h] [rbp-40h] BYREF
  unsigned __int16 *v87; // [rsp+D8h] [rbp-38h] BYREF
  const char *v88; // [rsp+E0h] [rbp-30h] BYREF
  unsigned __int16 *v89; // [rsp+E8h] [rbp-28h] BYREF
  _OWORD v90[2]; // [rsp+F0h] [rbp-20h] BYREF
  _OWORD v91[2]; // [rsp+110h] [rbp+0h] BYREF
  _BYTE v92[32]; // [rsp+130h] [rbp+20h] BYREF
  _BYTE v93[32]; // [rsp+150h] [rbp+40h] BYREF
  unsigned __int16 v94[17]; // [rsp+170h] [rbp+60h] BYREF
  __int64 v95; // [rsp+192h] [rbp+82h]
  _BYTE v97[34]; // [rsp+1A0h] [rbp+90h] BYREF
  __int64 v98; // [rsp+1C2h] [rbp+B2h]
  unsigned __int16 v99[33]; // [rsp+1D0h] [rbp+C0h] BYREF

  v13 = a4;
  v81 = (const char *)a3;
  v80 = a13;
  v90[0] = 0;
  v90[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v90[0]) = 0;
  v99[0] = 0;
  memset_0(&v99[1], 0, 0x40u);
  memset(v97, 0, sizeof(v97));
  v98 = 0;
  if ( a11 )
  {
    v17 = StringCchCopyW((unsigned __int16 *)v97, 0x15u, a11);
    if ( v17 < 0 )
      goto LABEL_3;
  }
  if ( a6 )
  {
    LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDownloadServerKey(a1, a2, v90);
    v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
    RegDeleteKeyValueW(HKEY_LOCAL_MACHINE, v19, L"ServerName");
    v20 = std::operator+<unsigned short>(v92, v90, L"\\");
    v21 = std::operator+<unsigned short>(v91, v20, a3);
    std::wstring::operator=(v90, v21);
    std::wstring::_Tidy_deallocate(v91);
    std::wstring::_Tidy_deallocate(v92);
    v22 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
    v17 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v22);
    if ( (unsigned int)(v17 - 2) <= 1 || v17 == 1168 )
    {
      v91[0] = 0;
      v91[1] = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v91[0]) = 0;
      LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDiscoveryServerKey(a1, L"Enterprise", a2, v91);
      v24 = std::operator+<unsigned short>(v93, v91, L"\\");
      v25 = std::operator+<unsigned short>(v92, v24, a3);
      std::wstring::operator=(v91, v25);
      std::wstring::_Tidy_deallocate(v92);
      std::wstring::_Tidy_deallocate(v93);
      v26 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v91);
      v27 = RegDeleteKeyW(HKEY_LOCAL_MACHINE, v26);
      v17 = v27;
      if ( v27 > 0 )
        v17 = (unsigned __int16)v27 | 0x80070000;
      std::wstring::_Tidy_deallocate(v91);
    }
    else if ( v17 > 0 )
    {
      v17 = (unsigned __int16)v17 | 0x80070000;
    }
    CommonUtil::WritePiiFilteredEsimIdToBuffer(a2, (const unsigned __int16 (*)[33])v99, (unsigned __int16 (*)[33])v23);
    if ( v17 < 0 )
    {
      if ( (unsigned int)CallbackContext > 2 )
      {
        v79 = a6;
        v81 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
        v84 = v99;
        v77 = v17;
        v83 = "LPA::EnterpriseManager::SetDownloadServerToRegistry";
        v82 = "LpaServiceEnterpriseManager";
        v75 = &v79;
        v31 = &v77;
        v32 = byte_18012B4B1;
        goto LABEL_17;
      }
    }
    else if ( (unsigned int)CallbackContext > 4 )
    {
      v77 = a6;
      v81 = (const char *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
      v84 = v99;
      v79 = v17;
      v83 = "LPA::EnterpriseManager::SetDownloadServerToRegistry";
      v82 = "LpaServiceEnterpriseManager";
      v75 = &v77;
      v31 = &v79;
      v32 = byte_18012B51D;
LABEL_17:
      v78 = v13;
      v80 = a3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v28,
        (_DWORD)v32,
        v29,
        v30,
        (__int64)&v82,
        (__int64)&v83,
        (__int64)v31,
        (__int64)&v84,
        (__int64)&v80,
        (__int64)&v78,
        (__int64)&v81,
        (__int64)v75);
    }
LABEL_3:
    std::wstring::_Tidy_deallocate(v90);
    return (unsigned int)v17;
  }
  if ( a5 )
    LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDiscoveryServerKey(a1, L"Enterprise", a2, v90);
  else
    LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDownloadServerKey(a1, a2, v90);
  v33 = std::operator+<unsigned short>(v92, v90, L"\\");
  v34 = std::operator+<unsigned short>(v93, v33, a3);
  std::wstring::operator=(v90, v34);
  std::wstring::_Tidy_deallocate(v93);
  std::wstring::_Tidy_deallocate(v92);
  v35 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
  v37 = CommonUtil::SetDwordToRegistry(v35, L"Enable", v36, (struct _SECURITY_ATTRIBUTES *)v13, 0, v72);
  if ( v37 >= 0 )
  {
    v38 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
    v37 = CommonUtil::SetDwordToRegistry(v38, L"State", v39, (struct _SECURITY_ATTRIBUTES *)a7, 0, v73);
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl'::`2'::impl) )
  {
    if ( v37 >= 0 )
    {
      v41 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
      v37 = CommonUtil::SetDwordToRegistry(v41, L"MaximumAttempts", v42, (struct _SECURITY_ATTRIBUTES *)a9, 0, v73);
      if ( v37 >= 0 )
      {
        v43 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
        v37 = CommonUtil::SetDwordToRegistry(
                v43,
                L"DownloadsAttempted",
                v44,
                (struct _SECURITY_ATTRIBUTES *)a10,
                0,
                v73);
      }
    }
    if ( a7 == 2 )
    {
      v45 = _Xtime_get_ticks() / 10000000;
      v46 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
      v37 = CommonUtil::SetQuadToRegistry(v46, v47, v48, (struct _SECURITY_ATTRIBUTES *)v45, (unsigned __int64)v70, v73);
    }
    if ( v37 < 0 )
      goto LABEL_36;
    v49 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
    v37 = CommonUtil::SetStringToRegistry(v49, L"ProfileId", v50, (struct _SECURITY_ATTRIBUTES *)v97, v70, v73);
    if ( v37 < 0 )
      goto LABEL_36;
    v51 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
    v53 = a12;
    v54 = L"ErrorDetail";
    goto LABEL_34;
  }
  if ( v37 >= 0 )
  {
    v51 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
    v53 = a8;
    v54 = L"RetriesLeft";
LABEL_34:
    v37 = CommonUtil::SetDwordToRegistry(v51, v54, v52, (struct _SECURITY_ATTRIBUTES *)v53, 0, v73);
    if ( v37 >= 0 )
    {
      v55 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
      v37 = CommonUtil::SetStringToRegistry(v55, L"AccountId", v56, v80, v71, v74);
    }
  }
LABEL_36:
  memset(v94, 0, sizeof(v94));
  v95 = 0;
  CommonUtil::WritePiiFilteredEsimIdToBuffer(a2, (const unsigned __int16 (*)[33])v99, (unsigned __int16 (*)[33])v40);
  v80 = 0;
  if ( (int)StringCchLengthW((const unsigned __int16 *)v97, 0x15u, (unsigned __int64 *)&v80) < 0 )
    goto LABEL_47;
  v58 = v80;
  v59 = (unsigned __int64)v80;
  v60 = v57 - 14;
  if ( (unsigned __int64)v80 > v60 )
    v59 = v57 - 14;
  if ( (int)StringCchCopyNW(v94, v57, (const unsigned __int16 *)v97, v59) < 0 )
  {
LABEL_47:
    v94[0] = 0;
  }
  else
  {
    if ( v58 )
    {
      if ( (unsigned __int64)&v58[-1].bInheritHandle + 7 > v60 )
      {
        v61 = (unsigned __int8)((_BYTE)v58 - 1 - v60);
        v62 = v60 + 35;
        v63 = &v94[7];
        while ( v61 )
        {
          *v63++ = v62;
          --v61;
        }
      }
      *(_WORD *)&v93[2 * (_QWORD)v58 + 30] = *(_WORD *)&v97[2 * (_QWORD)v58 - 2];
    }
    v94[(_QWORD)v58] = 0;
  }
  if ( v37 < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(v80) = a12;
      v89 = v94;
      LODWORD(v84) = a10;
      LODWORD(v83) = a9;
      LODWORD(v82) = a8;
      v79 = a7;
      v78 = a4;
      v88 = v81;
      v87 = v99;
      v86 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
      v77 = v37;
      v85 = (unsigned __int16 *)"LPA::EnterpriseManager::SetDownloadServerToRegistry";
      v81 = "LpaServiceEnterpriseManager";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v67,
        (unsigned int)byte_18012B321,
        v68,
        v69,
        (__int64)&v81,
        (__int64)&v85,
        (__int64)&v77,
        (__int64)&v86,
        (__int64)&v87,
        (__int64)&v88,
        (__int64)&v78,
        (__int64)&v79,
        (__int64)&v82,
        (__int64)&v83,
        (__int64)&v84,
        (__int64)&v89,
        (__int64)&v80);
    }
  }
  else if ( (unsigned int)CallbackContext > 4 )
  {
    v79 = a12;
    v85 = v94;
    v78 = a10;
    v77 = a9;
    LODWORD(v82) = a8;
    LODWORD(v83) = a7;
    LODWORD(v84) = a4;
    v86 = v99;
    v87 = (unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
    LODWORD(v80) = v37;
    v88 = "LPA::EnterpriseManager::SetDownloadServerToRegistry";
    v89 = (unsigned __int16 *)"LpaServiceEnterpriseManager";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
      v64,
      (unsigned int)byte_18012B3E9,
      v65,
      v66,
      (__int64)&v89,
      (__int64)&v88,
      (__int64)&v80,
      (__int64)&v87,
      (__int64)&v86,
      (__int64)&v81,
      (__int64)&v84,
      (__int64)&v83,
      (__int64)&v82,
      (__int64)&v77,
      (__int64)&v78,
      (__int64)&v85,
      (__int64)&v79);
  }
  if ( !a5 )
    LPA::EnterpriseManager::BroadcastDownloadServerUpdates(a1, (const unsigned __int16 (*)[33])a2);
  std::wstring::_Tidy_deallocate(v90);
  return (unsigned int)v37;
}

```

## disassembly

```asm
0x18007e4f8  mov     [rsp-8+arg_18], rbx
0x18007e4fd  push    rbp
0x18007e4fe  push    rsi
0x18007e4ff  push    rdi
0x18007e500  push    r12
0x18007e502  push    r13
0x18007e504  push    r14
0x18007e506  push    r15
0x18007e508  lea     rbp, [rsp-120h]
0x18007e510  sub     rsp, 230h
0x18007e517  mov     rax, cs:__security_cookie
0x18007e51e  xor     rax, rsp
0x18007e521  mov     [rbp+150h+var_40], rax
0x18007e528  movzx   r13d, r9b
0x18007e52c  mov     [rbp+150h+var_1D0], r13b
0x18007e530  mov     rsi, r8
0x18007e533  mov     [rbp+150h+var_1B8], r8
0x18007e537  mov     r14, rdx
0x18007e53a  mov     r15, rcx
0x18007e53d  mov     rdi, [rbp+150h+arg_50]
0x18007e544  mov     rax, [rbp+150h+arg_60]
0x18007e54b  mov     [rbp+150h+var_1C0], rax
0x18007e54f  xorps   xmm0, xmm0
0x18007e552  movups  [rbp+150h+var_170], xmm0
0x18007e556  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007e55e  movdqu  [rbp+150h+var_160], xmm1
0x18007e563  xor     eax, eax
0x18007e565  mov     word ptr [rbp+150h+var_170], ax
0x18007e569  mov     [rbp+150h+var_90], ax
0x18007e570  xor     edx, edx; Val
0x18007e572  lea     r8d, [rax+40h]; Size
0x18007e576  lea     rcx, [rbp+150h+var_90+2]; void *
0x18007e57d  call    memset_0
0x18007e582  xor     eax, eax
0x18007e584  mov     word ptr [rbp+150h+var_C0], ax
0x18007e58b  xorps   xmm0, xmm0
0x18007e58e  movups  xmmword ptr [rbp+150h+var_C0+2], xmm0
0x18007e595  movups  xmmword ptr [rbp+150h+var_C0+12h], xmm0
0x18007e59c  mov     [rbp+150h+var_9E], rax
0x18007e5a3  test    rdi, rdi
0x18007e5a6  jz      short loc_18007E5D0
0x18007e5a8  mov     r8, rdi; unsigned __int16 *
0x18007e5ab  lea     edx, [rax+15h]; unsigned __int64
0x18007e5ae  lea     rcx, [rbp+150h+var_C0]; unsigned __int16 *
0x18007e5b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007e5ba  mov     edi, eax
0x18007e5bc  test    eax, eax
0x18007e5be  jns     short loc_18007E5D0
0x18007e5c0  lea     rcx, [rbp+150h+var_170]
0x18007e5c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e5c9  mov     eax, edi
0x18007e5cb  jmp     loc_18007ED3C
0x18007e5d0  movzx   ebx, [rbp+150h+arg_28]
0x18007e5d7  mov     rcx, r15
0x18007e5da  test    bl, bl
0x18007e5dc  jz      loc_18007E85F
0x18007e5e2  lea     r8, [rbp+150h+var_170]
0x18007e5e6  mov     rdx, r14
0x18007e5e9  call    ?GetEnterpriseSettingsEuiccsDownloadServerKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDownloadServerKey(ushort const (&)[33],std::wstring &)
0x18007e5ee  lea     rcx, [rbp+150h+var_170]
0x18007e5f2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e5f7  mov     rdx, rax; lpSubKey
0x18007e5fa  lea     r8, aServername; "ServerName"
0x18007e601  mov     r12, 0FFFFFFFF80000002h
0x18007e608  mov     rcx, r12; hKey
0x18007e60b  call    cs:__imp_RegDeleteKeyValueW
0x18007e611  lea     r8, asc_1801118E4; "\\"
0x18007e618  lea     rdx, [rbp+150h+var_170]
0x18007e61c  lea     rcx, [rbp+150h+var_130]
0x18007e620  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18007e625  nop
0x18007e626  mov     r8, rsi
0x18007e629  mov     rdx, rax
0x18007e62c  lea     rcx, [rbp+150h+var_150]
0x18007e630  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18007e635  mov     rdx, rax
0x18007e638  lea     rcx, [rbp+150h+var_170]
0x18007e63c  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007e641  lea     rcx, [rbp+150h+var_150]
0x18007e645  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e64a  nop
0x18007e64b  lea     rcx, [rbp+150h+var_130]
0x18007e64f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e654  lea     rcx, [rbp+150h+var_170]
0x18007e658  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e65d  mov     rdx, rax; lpSubKey
0x18007e660  mov     rcx, r12; hKey
0x18007e663  call    cs:__imp_RegDeleteKeyW
0x18007e669  mov     edi, eax
0x18007e66b  add     eax, 0FFFFFFFEh
0x18007e66e  cmp     eax, 1
0x18007e671  jbe     short loc_18007E691
0x18007e673  cmp     edi, 490h
0x18007e679  jz      short loc_18007E691
0x18007e67b  test    edi, edi
0x18007e67d  jle     loc_18007E731
0x18007e683  movzx   edi, di
0x18007e686  or      edi, 80070000h
0x18007e68c  jmp     loc_18007E731
0x18007e691  xorps   xmm0, xmm0
0x18007e694  movups  [rbp+150h+var_150], xmm0
0x18007e698  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18007e6a0  movdqu  [rbp+150h+var_140], xmm1
0x18007e6a5  xor     eax, eax
0x18007e6a7  mov     word ptr [rbp+150h+var_150], ax
0x18007e6ab  lea     r9, [rbp+150h+var_150]
0x18007e6af  mov     r8, r14
0x18007e6b2  lea     rdx, aEnterprise; "Enterprise"
0x18007e6b9  mov     rcx, r15
0x18007e6bc  call    ?GetEnterpriseSettingsEuiccsDiscoveryServerKey@EnterpriseManager@LPA@@AEAAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDiscoveryServerKey(ushort const *,ushort const *,std::wstring &)
0x18007e6c1  lea     r8, asc_1801118E4; "\\"
0x18007e6c8  lea     rdx, [rbp+150h+var_150]
0x18007e6cc  lea     rcx, [rbp+150h+var_110]
0x18007e6d0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18007e6d5  nop
0x18007e6d6  mov     r8, rsi
0x18007e6d9  mov     rdx, rax
0x18007e6dc  lea     rcx, [rbp+150h+var_130]
0x18007e6e0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18007e6e5  mov     rdx, rax
0x18007e6e8  lea     rcx, [rbp+150h+var_150]
0x18007e6ec  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007e6f1  lea     rcx, [rbp+150h+var_130]
0x18007e6f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e6fa  nop
0x18007e6fb  lea     rcx, [rbp+150h+var_110]
0x18007e6ff  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e704  lea     rcx, [rbp+150h+var_150]
0x18007e708  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e70d  mov     rdx, rax; lpSubKey
0x18007e710  mov     rcx, r12; hKey
0x18007e713  call    cs:__imp_RegDeleteKeyW
0x18007e719  mov     edi, eax
0x18007e71b  test    eax, eax
0x18007e71d  jle     short loc_18007E728
0x18007e71f  movzx   edi, ax
0x18007e722  or      edi, 80070000h
0x18007e728  lea     rcx, [rbp+150h+var_150]
0x18007e72c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e731  lea     rdx, [rbp+150h+var_90]; unsigned __int16 (*)[33]
0x18007e738  mov     rcx, r14; this
0x18007e73b  call    ?WritePiiFilteredEsimIdToBuffer@CommonUtil@@YAXPEAY0CB@$$CBGAEAY0CB@G@Z; CommonUtil::WritePiiFilteredEsimIdToBuffer(ushort const (*)[33],ushort (&)[33])
0x18007e740  mov     eax, cs:CallbackContext
0x18007e746  test    edi, edi
0x18007e748  js      short loc_18007E7C1
0x18007e74a  cmp     eax, 4
0x18007e74d  jbe     loc_18007E5C0
0x18007e753  mov     [rbp+150h+var_1CC], ebx
0x18007e756  lea     rcx, [rbp+150h+var_170]
0x18007e75a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e75f  mov     [rbp+150h+var_1B8], rax
0x18007e763  lea     rax, [rbp+150h+var_90]
0x18007e76a  mov     [rbp+150h+var_1A0], rax
0x18007e76e  mov     [rbp+150h+var_1C4], edi
0x18007e771  lea     rax, aLpaEnterprisem_21; "LPA::EnterpriseManager::SetDownloadServ"...
0x18007e778  mov     [rbp+150h+var_1A8], rax
0x18007e77c  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007e783  mov     [rbp+150h+var_1B0], rax
0x18007e787  lea     rax, [rbp+150h+var_1CC]
0x18007e78b  mov     [rsp+260h+var_208], rax
0x18007e790  lea     rax, [rbp+150h+var_1B8]
0x18007e794  mov     [rsp+260h+var_210], rax
0x18007e799  lea     rax, [rbp+150h+var_1C8]
0x18007e79d  mov     [rsp+260h+var_218], rax
0x18007e7a2  lea     rax, [rbp+150h+var_1C0]
0x18007e7a6  mov     [rsp+260h+var_220], rax
0x18007e7ab  lea     rax, [rbp+150h+var_1A0]
0x18007e7af  mov     [rsp+260h+var_228], rax
0x18007e7b4  lea     rax, [rbp+150h+var_1C4]
0x18007e7b8  lea     rdx, byte_18012B51D
0x18007e7bf  jmp     short loc_18007E836
0x18007e7c1  cmp     eax, 2
0x18007e7c4  jbe     loc_18007E5C0
0x18007e7ca  mov     [rbp+150h+var_1C4], ebx
0x18007e7cd  lea     rcx, [rbp+150h+var_170]
0x18007e7d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e7d6  mov     [rbp+150h+var_1B8], rax
0x18007e7da  lea     rax, [rbp+150h+var_90]
0x18007e7e1  mov     [rbp+150h+var_1A0], rax
0x18007e7e5  mov     [rbp+150h+var_1CC], edi
0x18007e7e8  lea     rax, aLpaEnterprisem_21; "LPA::EnterpriseManager::SetDownloadServ"...
0x18007e7ef  mov     [rbp+150h+var_1A8], rax
0x18007e7f3  lea     rax, aLpaserviceente; "LpaServiceEnterpriseManager"
0x18007e7fa  mov     [rbp+150h+var_1B0], rax
0x18007e7fe  lea     rax, [rbp+150h+var_1C4]
0x18007e802  mov     [rsp+260h+var_208], rax
0x18007e807  lea     rax, [rbp+150h+var_1B8]
0x18007e80b  mov     [rsp+260h+var_210], rax
0x18007e810  lea     rax, [rbp+150h+var_1C8]
0x18007e814  mov     [rsp+260h+var_218], rax
0x18007e819  lea     rax, [rbp+150h+var_1C0]
0x18007e81d  mov     [rsp+260h+var_220], rax
0x18007e822  lea     rax, [rbp+150h+var_1A0]
0x18007e826  mov     [rsp+260h+var_228], rax
0x18007e82b  lea     rax, [rbp+150h+var_1CC]
0x18007e82f  lea     rdx, byte_18012B4B1
0x18007e836  mov     [rsp+260h+var_230], rax
0x18007e83b  lea     rax, [rbp+150h+var_1A8]
0x18007e83f  mov     [rsp+260h+var_238], rax
0x18007e844  lea     rax, [rbp+150h+var_1B0]
0x18007e848  mov     [rsp+260h+var_240], rax
0x18007e84d  mov     [rbp+150h+var_1C8], r13d
0x18007e851  mov     [rbp+150h+var_1C0], rsi
0x18007e855  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U3@U2@U3@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@5454@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18007e85a  jmp     loc_18007E5C0
0x18007e85f  mov     r12b, [rbp+150h+arg_20]
0x18007e866  test    r12b, r12b
0x18007e869  jz      short loc_18007E880
0x18007e86b  lea     r9, [rbp+150h+var_170]
0x18007e86f  mov     r8, r14
0x18007e872  lea     rdx, aEnterprise; "Enterprise"
0x18007e879  call    ?GetEnterpriseSettingsEuiccsDiscoveryServerKey@EnterpriseManager@LPA@@AEAAXPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDiscoveryServerKey(ushort const *,ushort const *,std::wstring &)
0x18007e87e  jmp     short loc_18007E88C
0x18007e880  lea     r8, [rbp+150h+var_170]
0x18007e884  mov     rdx, r14
0x18007e887  call    ?GetEnterpriseSettingsEuiccsDownloadServerKey@EnterpriseManager@LPA@@AEAAXAEAY0CB@$$CBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; LPA::EnterpriseManager::GetEnterpriseSettingsEuiccsDownloadServerKey(ushort const (&)[33],std::wstring &)
0x18007e88c  lea     r8, asc_1801118E4; "\\"
0x18007e893  lea     rdx, [rbp+150h+var_170]
0x18007e897  lea     rcx, [rbp+150h+var_130]
0x18007e89b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x18007e8a0  nop
0x18007e8a1  mov     r8, rsi
0x18007e8a4  mov     rdx, rax
0x18007e8a7  lea     rcx, [rbp+150h+var_110]
0x18007e8ab  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x18007e8b0  mov     rdx, rax
0x18007e8b3  lea     rcx, [rbp+150h+var_170]
0x18007e8b7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18007e8bc  lea     rcx, [rbp+150h+var_110]
0x18007e8c0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e8c5  nop
0x18007e8c6  lea     rcx, [rbp+150h+var_130]
0x18007e8ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18007e8cf  lea     rcx, [rbp+150h+var_170]
0x18007e8d3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e8d8  mov     rcx, rax; lpSubKey
0x18007e8db  mov     dword ptr [rsp+260h+var_240], 0; unsigned int
0x18007e8e3  mov     r9d, r13d; struct _SECURITY_ATTRIBUTES *
0x18007e8e6  lea     rdx, aEnable; "Enable"
0x18007e8ed  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007e8f2  mov     ebx, eax
0x18007e8f4  mov     r13d, dword ptr [rbp+150h+arg_30]
0x18007e8fb  test    eax, eax
0x18007e8fd  js      short loc_18007E924
0x18007e8ff  lea     rcx, [rbp+150h+var_170]
0x18007e903  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e908  mov     rcx, rax; lpSubKey
0x18007e90b  mov     dword ptr [rsp+260h+var_240], 0; unsigned int
0x18007e913  mov     r9d, r13d; struct _SECURITY_ATTRIBUTES *
0x18007e916  lea     rdx, aState; "State"
0x18007e91d  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007e922  mov     ebx, eax
0x18007e924  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY> `wil::Feature<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::GetImpl(void)'::`2'::impl
0x18007e92b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EUICCS_CSP_CONTINUED_RETRY>::__private_IsEnabled(void)
0x18007e930  test    al, al
0x18007e932  jz      loc_18007EA1C
0x18007e938  test    ebx, ebx
0x18007e93a  js      short loc_18007E992
0x18007e93c  lea     rcx, [rbp+150h+var_170]
0x18007e940  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e945  mov     rcx, rax; lpSubKey
0x18007e948  mov     dword ptr [rsp+260h+var_240], 0; unsigned int
0x18007e950  mov     r9d, dword ptr [rbp+150h+arg_40]; struct _SECURITY_ATTRIBUTES *
0x18007e957  lea     rdx, aMaximumattempt; "MaximumAttempts"
0x18007e95e  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007e963  mov     ebx, eax
0x18007e965  test    eax, eax
0x18007e967  js      short loc_18007E992
0x18007e969  lea     rcx, [rbp+150h+var_170]
0x18007e96d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e972  mov     rcx, rax; lpSubKey
0x18007e975  mov     dword ptr [rsp+260h+var_240], 0; unsigned __int16 *
0x18007e97d  mov     r9d, dword ptr [rbp+150h+arg_48]; struct _SECURITY_ATTRIBUTES *
0x18007e984  lea     rdx, aDownloadsattem; "DownloadsAttempted"
0x18007e98b  call    ?SetDwordToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@KK@Z; CommonUtil::SetDwordToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x18007e990  mov     ebx, eax
0x18007e992  cmp     r13d, 2
0x18007e996  jnz     short loc_18007E9D6
0x18007e998  call    cs:__imp__Xtime_get_ticks
0x18007e99e  mov     rcx, rax
0x18007e9a1  mov     rax, 0D6BF94D5E57A42BDh
0x18007e9ab  imul    rcx
0x18007e9ae  lea     rdi, [rcx+rdx]
0x18007e9b2  sar     rdi, 17h
0x18007e9b6  mov     rax, rdi
0x18007e9b9  shr     rax, 3Fh
0x18007e9bd  add     rdi, rax
0x18007e9c0  lea     rcx, [rbp+150h+var_170]
0x18007e9c4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e9c9  mov     rcx, rax; lpSubKey
0x18007e9cc  mov     r9, rdi; struct _SECURITY_ATTRIBUTES *
0x18007e9cf  call    ?SetQuadToRegistry@CommonUtil@@YAJPEBG0PEAU_SECURITY_ATTRIBUTES@@_KK@Z; CommonUtil::SetQuadToRegistry(ushort const *,ushort const *,_SECURITY_ATTRIBUTES *,unsigned __int64,ulong)
0x18007e9d4  mov     ebx, eax
0x18007e9d6  test    ebx, ebx
0x18007e9d8  js      loc_18007EA6B
0x18007e9de  lea     rcx, [rbp+150h+var_170]
0x18007e9e2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18007e9e7  mov     rcx, rax; lpSubKey
0x18007e9ea  lea     r9, [rbp+150h+var_C0]; struct _SECURITY_ATTRIBUTES *
0x18007e9f1  lea     rdx, aProfileid; "ProfileId"
  ... truncated ...
```
