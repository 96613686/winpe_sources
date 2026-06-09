# RealtimeProtection::CSenseCloudCncProxy::RefreshQueryParametersData(void)

- ea: `0x1800619e0`
- end: `0x180061ffb`
- name: `?RefreshQueryParametersData@CSenseCloudCncProxy@RealtimeProtection@@AEAAJXZ`
- size: `1563`
- prototype: `__int64 __fastcall(RealtimeProtection::CSenseCloudCncProxy *__hidden this)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180066130`

## callees

- `0x180034420`
- `0x180037afc`
- `0x18003e384`
- `0x18004b3bc`
- `0x18004bc70`
- `0x1800619e0`
- `0x180061ffc`
- `0x180062054`
- `0x180062384`
- `0x180062454`
- `0x1800809d0`
- `0x1800ad914`
- `0x1800bcca4`
- `0x1800ca30c`
- `0x1801034d4`
- `0x180103640`
- `0x180103844`
- `0x18010cb40`
- `0x18010ce3c`

## import_xrefs

- `KERNEL32!AcquireSRWLockShared` at `0x180061aba`
- `KERNEL32!AcquireSRWLockShared` at `0x180061aba`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180061eb6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180061eb6`
- `KERNEL32!CompareFileTime` at `0x180061acc`
- `KERNEL32!CompareFileTime` at `0x180061acc`
- `ADVAPI32!RegCloseKey` at `0x180061a75`
- `ADVAPI32!RegCloseKey` at `0x180061c34`
- `ADVAPI32!RegCloseKey` at `0x180061fc9`
- `ADVAPI32!RegCloseKey` at `0x180061a75`
- `ADVAPI32!RegCloseKey` at `0x180061c34`
- `ADVAPI32!RegCloseKey` at `0x180061fc9`

## string_xrefs

- `0x180061be3`: `ConfigurationVersion`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall RealtimeProtection::CSenseCloudCncProxy::RefreshQueryParametersData(
        RealtimeProtection::CSenseCloudCncProxy *this)
{
  int v2; // eax
  int ComputerDnsName; // ebx
  __m128i si128; // xmm6
  int InfoFromOnboardingInfo; // eax
  const struct std::nothrow_t *v7; // rdx
  __int64 v8; // rax
  int ValueString; // eax
  const struct std::nothrow_t *v10; // rdx
  __int64 v11; // rax
  const struct std::nothrow_t *v12; // rdx
  int v13; // eax
  __int64 v14; // rax
  int SenseClientVersion; // eax
  unsigned __int64 *v16; // r8
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  const struct std::nothrow_t *v19; // rdx
  unsigned int v20; // [rsp+28h] [rbp-E0h]
  unsigned int v21; // [rsp+28h] [rbp-E0h]
  _OWORD v22[2]; // [rsp+48h] [rbp-C0h] BYREF
  _OWORD v23[2]; // [rsp+68h] [rbp-A0h] BYREF
  _OWORD v24[2]; // [rsp+88h] [rbp-80h] BYREF
  _OWORD v25[2]; // [rsp+A8h] [rbp-60h] BYREF
  _OWORD v26[2]; // [rsp+C8h] [rbp-40h] BYREF
  _OWORD v27[2]; // [rsp+E8h] [rbp-20h] BYREF
  _OWORD v28[2]; // [rsp+108h] [rbp+0h] BYREF
  char *v29; // [rsp+128h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+130h] [rbp+28h] BYREF
  void *v31; // [rsp+138h] [rbp+30h] BYREF
  HKEY v32; // [rsp+140h] [rbp+38h] BYREF
  void *v33; // [rsp+148h] [rbp+40h] BYREF
  FILETIME FileTime2; // [rsp+150h] [rbp+48h] BYREF
  __int128 v35; // [rsp+158h] [rbp+50h] BYREF
  __int64 v36; // [rsp+168h] [rbp+60h]
  __int64 v37; // [rsp+170h] [rbp+68h]

  hKey = 0;
  v2 = CommonUtil::UtilRegOpenKey(
         (CommonUtil *)&hKey,
         (HKEY *)0xFFFFFFFF80000002LL,
         (HKEY)&stru_18025D270,
         (const wchar_t *)0x20019,
         v20);
  ComputerDnsName = v2;
  if ( v2 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        13,
        WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids,
        (unsigned int)v2);
    goto LABEL_5;
  }
  FileTime2 = 0;
  if ( (int)CommonUtil::UtilRegQueryInfoKey(
              (CommonUtil *)hKey,
              0,
              0,
              0,
              0,
              0,
              0,
              (unsigned __int64 *)&FileTime2,
              *(struct _FILETIME **)&v22[0]) < 0 )
  {
LABEL_12:
    v24[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v24[1] = si128;
    LOWORD(v24[0]) = 0;
    v23[0] = 0;
    v23[1] = si128;
    LOWORD(v23[0]) = 0;
    InfoFromOnboardingInfo = Dlp::SenseCnC::GetInfoFromOnboardingInfo(hKey, v24, v23);
    ComputerDnsName = InfoFromOnboardingInfo;
    if ( InfoFromOnboardingInfo < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids,
          (unsigned int)InfoFromOnboardingInfo);
LABEL_16:
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v23);
      std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v24);
LABEL_5:
      if ( hKey )
        RegCloseKey(hKey);
      return (unsigned int)ComputerDnsName;
    }
    v35 = 0;
    v36 = 0;
    v37 = 7;
    LOWORD(v35) = 0;
    v26[0] = 0;
    v26[1] = si128;
    LOWORD(v26[0]) = 0;
    if ( (int)Dlp::SenseCnC::GetInfoFromSenseConfiguration(hKey, &v35, v26) < 0 )
    {
      v32 = 0;
      if ( CommonUtil::UtilRegOpenKey(
             (CommonUtil *)&v32,
             (HKEY *)hKey,
             (HKEY)&stru_1802AD728,
             (const wchar_t *)0x20019,
             v21) >= 0 )
      {
        v33 = 0;
        if ( (int)CommonUtil::UtilRegGetValueString(v32, L"ConfigurationVersion", &v33, 0, 0) >= 0 )
        {
          v8 = Dlp::SenseCnC::ToLowerCase(v22, v33);
          std::wstring::operator=(&v35, v8);
          std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v22);
        }
        if ( v33 )
          operator delete(v33, v7);
      }
      if ( v32 )
        RegCloseKey(v32);
    }
    if ( !v36 )
      std::wstring::assign(&v35, L"0.0.0.0");
    v25[0] = 0;
    v25[1] = si128;
    LOWORD(v25[0]) = 0;
    v31 = 0;
    ValueString = CommonUtil::UtilRegGetValueString(hKey, L"senseId", &v31, 0, 0);
    ComputerDnsName = ValueString;
    if ( ValueString < 0 )
    {
      v10 = (const struct std::nothrow_t *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids,
          (unsigned int)ValueString);
      goto LABEL_31;
    }
    v11 = Dlp::SenseCnC::ToLowerCase(v22, v31);
    std::wstring::operator=(v25, v11);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v22);
    v27[0] = 0;
    v27[1] = si128;
    LOWORD(v27[0]) = 0;
    if ( v31 )
    {
      operator delete(v31, v12);
      v31 = 0;
    }
    v13 = CommonUtil::UtilRegGetValueString(hKey, L"senseGuid", &v31, 0, 0);
    ComputerDnsName = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids,
          (unsigned int)v13);
      goto LABEL_40;
    }
    v14 = Dlp::SenseCnC::ToLowerCase(v22, v31);
    std::wstring::operator=(v27, v14);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v22);
    v28[0] = 0;
    v28[1] = si128;
    LOWORD(v28[0]) = 0;
    SenseClientVersion = Dlp::SenseCnC::GetSenseClientVersion(v28);
    ComputerDnsName = SenseClientVersion;
    if ( SenseClientVersion < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids,
          (unsigned int)SenseClientVersion);
      goto LABEL_45;
    }
    v22[0] = 0;
    v22[1] = si128;
    LOWORD(v22[0]) = 0;
    ComputerDnsName = Dlp::SenseCnC::GetComputerDnsName((__int64)v22);
    if ( ComputerDnsName >= 0 )
    {
      LODWORD(v33) = 0;
      v32 = 0;
      ComputerDnsName = RealtimeProtection::DlpUtils::GetProductTypeAndInfo(
                          (RealtimeProtection::DlpUtils *)&v33,
                          (unsigned int *)&v32,
                          v16);
      if ( ComputerDnsName >= 0 )
      {
        AcquireSRWLockExclusive((PSRWLOCK)this + 1);
        v29 = (char *)this + 8;
        std::wstring::swap((char *)this + 56, v23);
        std::wstring::swap((char *)this + 88, v26);
        std::wstring::swap((char *)this + 120, v24);
        std::wstring::swap((char *)this + 152, &v35);
        std::wstring::swap((char *)this + 184, v28);
        std::wstring::swap((char *)this + 216, v25);
        std::wstring::swap((char *)this + 248, v27);
        std::wstring::swap((char *)this + 280, v22);
        *((_DWORD *)this + 78) = (_DWORD)v33;
        *((_QWORD *)this + 44) = v32;
        *((FILETIME *)this + 2) = FileTime2;
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v29);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v22);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v28);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v27);
        if ( v31 )
          operator delete(v31, v19);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v25);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v26);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v35);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v23);
        std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v24);
        goto LABEL_59;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v18 = 19;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_51;
      v18 = 18;
    }
    WPP_SF_d(v17[2], v18, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids, (unsigned int)ComputerDnsName);
LABEL_51:
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v22);
LABEL_45:
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v28);
LABEL_40:
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v27);
LABEL_31:
    if ( v31 )
      operator delete(v31, v10);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v25);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(v26);
    std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(&v35);
    goto LABEL_16;
  }
  AcquireSRWLockShared((PSRWLOCK)this + 1);
  v32 = (HKEY)((char *)this + 8);
  if ( CompareFileTime((const FILETIME *)this + 2, &FileTime2) < 0 )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
    goto LABEL_12;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v32);
LABEL_59:
  if ( hKey )
    RegCloseKey(hKey);
  return 0;
}

```

## disassembly

```asm
0x1800619e0  mov     rax, rsp
0x1800619e3  mov     [rax+10h], rbx
0x1800619e7  mov     [rax+18h], rsi
0x1800619eb  mov     [rax+20h], rdi
0x1800619ef  push    rbp
0x1800619f0  lea     rbp, [rax-98h]
0x1800619f7  sub     rsp, 190h
0x1800619fe  movaps  xmmword ptr [rax-18h], xmm6
0x180061a02  mov     rax, cs:__security_cookie
0x180061a09  xor     rax, rsp
0x180061a0c  mov     [rbp+90h+var_20], rax
0x180061a10  mov     rdi, rcx
0x180061a13  xor     esi, esi
0x180061a15  mov     [rbp+90h+hKey], rsi
0x180061a19  mov     r9d, 20019h; wchar_t *
0x180061a1f  lea     r8, stru_18025D270; HKEY
0x180061a26  mov     rdx, 0FFFFFFFF80000002h; HKEY *
0x180061a2d  lea     rcx, [rbp+90h+hKey]; this
0x180061a31  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x180061a36  mov     ebx, eax
0x180061a38  test    eax, eax
0x180061a3a  jns     short loc_180061A82
0x180061a3c  lea     rdx, WPP_GLOBAL_Control
0x180061a43  mov     rcx, cs:WPP_GLOBAL_Control
0x180061a4a  cmp     rcx, rdx
0x180061a4d  jz      short loc_180061A6C
0x180061a4f  test    byte ptr [rcx+1Ch], 1
0x180061a53  jz      short loc_180061A6C
0x180061a55  lea     edx, [rsi+0Dh]
0x180061a58  mov     r9d, eax
0x180061a5b  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180061a62  mov     rcx, [rcx+10h]
0x180061a66  call    WPP_SF_d
0x180061a6b  nop
0x180061a6c  mov     rcx, [rbp+90h+hKey]; hKey
0x180061a70  test    rcx, rcx
0x180061a73  jz      short loc_180061A7B
0x180061a75  call    cs:__imp_RegCloseKey
0x180061a7b  mov     eax, ebx
0x180061a7d  jmp     loc_180061FD1
0x180061a82  mov     qword ptr [rbp+90h+FileTime2.dwLowDateTime], rsi
0x180061a86  lea     rax, [rbp+90h+FileTime2]
0x180061a8a  mov     [rsp+190h+var_158], rax; unsigned __int64 *
0x180061a8f  mov     [rsp+190h+var_160], rsi; unsigned __int64 *
0x180061a94  mov     [rsp+190h+var_168], rsi; unsigned __int64 *
0x180061a99  mov     [rsp+190h+var_170], rsi; unsigned int
0x180061a9e  xor     r9d, r9d; unsigned __int64 *
0x180061aa1  xor     r8d, r8d; unsigned __int64 *
0x180061aa4  xor     edx, edx; HKEY
0x180061aa6  mov     rcx, [rbp+90h+hKey]; this
0x180061aaa  call    ?UtilRegQueryInfoKey@CommonUtil@@YAJPEAUHKEY__@@PEA_K11111PEAU_FILETIME@@@Z; CommonUtil::UtilRegQueryInfoKey(HKEY__ *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,_FILETIME *)
0x180061aaf  test    eax, eax
0x180061ab1  js      short loc_180061AE9
0x180061ab3  lea     rbx, [rdi+8]
0x180061ab7  mov     rcx, rbx; SRWLock
0x180061aba  call    cs:__imp_AcquireSRWLockShared
0x180061ac0  mov     [rbp+90h+var_58], rbx
0x180061ac4  lea     rcx, [rdi+10h]; lpFileTime1
0x180061ac8  lea     rdx, [rbp+90h+FileTime2]; lpFileTime2
0x180061acc  call    cs:__imp_CompareFileTime
0x180061ad2  lea     rcx, [rbp+90h+var_58]
0x180061ad6  test    eax, eax
0x180061ad8  js      short loc_180061AE4
0x180061ada  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180061adf  jmp     loc_180061FC0
0x180061ae4  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x180061ae9  xorps   xmm0, xmm0
0x180061aec  movups  [rbp+90h+var_110], xmm0
0x180061af0  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180061af8  movdqu  [rbp+90h+var_100], xmm6
0x180061afd  mov     word ptr [rbp+90h+var_110], si
0x180061b01  movups  [rsp+190h+var_138+8], xmm0
0x180061b06  movdqu  [rsp+190h+var_128+8], xmm6
0x180061b0c  mov     word ptr [rsp+190h+var_138+8], si
0x180061b11  lea     r8, [rsp+190h+var_138+8]
0x180061b16  lea     rdx, [rbp+90h+var_110]
0x180061b1a  mov     rcx, [rbp+90h+hKey]
0x180061b1e  call    ?GetInfoFromOnboardingInfo@SenseCnC@Dlp@@YAJPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; Dlp::SenseCnC::GetInfoFromOnboardingInfo(HKEY__ *,std::wstring &,std::wstring &)
0x180061b23  mov     ebx, eax
0x180061b25  test    eax, eax
0x180061b27  jns     short loc_180061B74
0x180061b29  lea     rdx, WPP_GLOBAL_Control
0x180061b30  mov     rcx, cs:WPP_GLOBAL_Control
0x180061b37  cmp     rcx, rdx
0x180061b3a  jz      short loc_180061B5B
0x180061b3c  test    byte ptr [rcx+1Ch], 1
0x180061b40  jz      short loc_180061B5B
0x180061b42  mov     edx, 0Eh
0x180061b47  mov     r9d, eax
0x180061b4a  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180061b51  mov     rcx, [rcx+10h]
0x180061b55  call    WPP_SF_d
0x180061b5a  nop
0x180061b5b  lea     rcx, [rsp+190h+var_138+8]; void *
0x180061b60  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061b65  nop
0x180061b66  lea     rcx, [rbp+90h+var_110]; void *
0x180061b6a  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061b6f  jmp     loc_180061A6C
0x180061b74  xorps   xmm0, xmm0
0x180061b77  movups  [rbp+90h+var_40], xmm0
0x180061b7b  mov     [rbp+90h+var_30], rsi
0x180061b7f  mov     [rbp+90h+var_28], 7
0x180061b87  mov     word ptr [rbp+90h+var_40], si
0x180061b8b  movups  [rbp+90h+var_D0], xmm0
0x180061b8f  movdqu  [rbp+90h+var_C0], xmm6
0x180061b94  mov     word ptr [rbp+90h+var_D0], si
0x180061b98  lea     r8, [rbp+90h+var_D0]
0x180061b9c  lea     rdx, [rbp+90h+var_40]
0x180061ba0  mov     rcx, [rbp+90h+hKey]
0x180061ba4  call    ?GetInfoFromSenseConfiguration@SenseCnC@Dlp@@YAJPEAUHKEY__@@AEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@1@Z; Dlp::SenseCnC::GetInfoFromSenseConfiguration(HKEY__ *,std::wstring &,std::wstring &)
0x180061ba9  test    eax, eax
0x180061bab  jns     loc_180061C3A
0x180061bb1  mov     [rbp+90h+var_58], rsi
0x180061bb5  mov     r9d, 20019h; wchar_t *
0x180061bbb  lea     r8, stru_1802AD728; HKEY
0x180061bc2  mov     rdx, [rbp+90h+hKey]; HKEY *
0x180061bc6  lea     rcx, [rbp+90h+var_58]; this
0x180061bca  call    ?UtilRegOpenKey@CommonUtil@@YAJPEAPEAUHKEY__@@PEAU2@PEB_WK@Z; CommonUtil::UtilRegOpenKey(HKEY__ * *,HKEY__ *,wchar_t const *,ulong)
0x180061bcf  test    eax, eax
0x180061bd1  js      short loc_180061C2B
0x180061bd3  mov     [rbp+90h+var_50], rsi
0x180061bd7  mov     [rsp+190h+var_170], rsi
0x180061bdc  xor     r9d, r9d
0x180061bdf  lea     r8, [rbp+90h+var_50]
0x180061be3  lea     rdx, aConfigurationv; "ConfigurationVersion"
0x180061bea  mov     rcx, [rbp+90h+var_58]
0x180061bee  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x180061bf3  test    eax, eax
0x180061bf5  js      short loc_180061C1C
0x180061bf7  mov     rdx, [rbp+90h+var_50]
0x180061bfb  lea     rcx, [rsp+190h+var_158+8]
0x180061c00  call    ?ToLowerCase@SenseCnC@Dlp@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Dlp::SenseCnC::ToLowerCase(wchar_t const *)
0x180061c05  mov     rdx, rax
0x180061c08  lea     rcx, [rbp+90h+var_40]
0x180061c0c  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180061c11  lea     rcx, [rsp+190h+var_158+8]; void *
0x180061c16  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061c1b  nop
0x180061c1c  mov     rcx, [rbp+90h+var_50]; void *
0x180061c20  test    rcx, rcx
0x180061c23  jz      short loc_180061C2B
0x180061c25  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061c2a  nop
0x180061c2b  mov     rcx, [rbp+90h+var_58]; hKey
0x180061c2f  test    rcx, rcx
0x180061c32  jz      short loc_180061C3A
0x180061c34  call    cs:__imp_RegCloseKey
0x180061c3a  cmp     [rbp+90h+var_30], rsi
0x180061c3e  jnz     short loc_180061C50
0x180061c40  lea     rdx, a0000; "0.0.0.0"
0x180061c47  lea     rcx, [rbp+90h+var_40]; void *
0x180061c4b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::assign(wchar_t const * const)
0x180061c50  xorps   xmm0, xmm0
0x180061c53  movups  [rbp+90h+var_F0], xmm0
0x180061c57  movdqu  [rbp+90h+var_E0], xmm6
0x180061c5c  mov     word ptr [rbp+90h+var_F0], si
0x180061c60  mov     [rbp+90h+var_60], rsi
0x180061c64  mov     [rsp+190h+var_170], rsi
0x180061c69  xor     r9d, r9d
0x180061c6c  lea     r8, [rbp+90h+var_60]
0x180061c70  lea     rdx, aSenseid; "senseId"
0x180061c77  mov     rcx, [rbp+90h+hKey]
0x180061c7b  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x180061c80  mov     ebx, eax
0x180061c82  test    eax, eax
0x180061c84  jns     short loc_180061CE9
0x180061c86  lea     rdx, WPP_GLOBAL_Control
0x180061c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180061c94  cmp     rcx, rdx
0x180061c97  jz      short loc_180061CB8
0x180061c99  test    byte ptr [rcx+1Ch], 1
0x180061c9d  jz      short loc_180061CB8
0x180061c9f  mov     edx, 0Fh
0x180061ca4  mov     r9d, eax
0x180061ca7  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180061cae  mov     rcx, [rcx+10h]
0x180061cb2  call    WPP_SF_d
0x180061cb7  nop
0x180061cb8  mov     rcx, [rbp+90h+var_60]; void *
0x180061cbc  test    rcx, rcx
0x180061cbf  jz      short loc_180061CC7
0x180061cc1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061cc6  nop
0x180061cc7  lea     rcx, [rbp+90h+var_F0]; void *
0x180061ccb  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061cd0  nop
0x180061cd1  lea     rcx, [rbp+90h+var_D0]; void *
0x180061cd5  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061cda  nop
0x180061cdb  lea     rcx, [rbp+90h+var_40]; void *
0x180061cdf  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061ce4  jmp     loc_180061B5B
0x180061ce9  mov     rdx, [rbp+90h+var_60]
0x180061ced  lea     rcx, [rsp+190h+var_158+8]
0x180061cf2  call    ?ToLowerCase@SenseCnC@Dlp@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Dlp::SenseCnC::ToLowerCase(wchar_t const *)
0x180061cf7  mov     rdx, rax
0x180061cfa  lea     rcx, [rbp+90h+var_F0]
0x180061cfe  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180061d03  lea     rcx, [rsp+190h+var_158+8]; void *
0x180061d08  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061d0d  xorps   xmm0, xmm0
0x180061d10  movups  [rbp+90h+var_B0], xmm0
0x180061d14  movdqu  [rbp+90h+var_A0], xmm6
0x180061d19  mov     word ptr [rbp+90h+var_B0], si
0x180061d1d  mov     rcx, [rbp+90h+var_60]; void *
0x180061d21  test    rcx, rcx
0x180061d24  jz      short loc_180061D2F
0x180061d26  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180061d2b  mov     [rbp+90h+var_60], rsi
0x180061d2f  mov     [rsp+190h+var_170], rsi
0x180061d34  xor     r9d, r9d
0x180061d37  lea     r8, [rbp+90h+var_60]
0x180061d3b  lea     rdx, aSenseguid; "senseGuid"
0x180061d42  mov     rcx, [rbp+90h+hKey]
0x180061d46  call    ?UtilRegGetValueString@CommonUtil@@YAJPEAUHKEY__@@PEB_WPEAPEA_WW4UTIL_REG_EXPAND_STRING@1@PEAK@Z; CommonUtil::UtilRegGetValueString(HKEY__ *,wchar_t const *,wchar_t * *,CommonUtil::UTIL_REG_EXPAND_STRING,ulong *)
0x180061d4b  mov     ebx, eax
0x180061d4d  test    eax, eax
0x180061d4f  jns     short loc_180061D91
0x180061d51  lea     rdx, WPP_GLOBAL_Control
0x180061d58  mov     rcx, cs:WPP_GLOBAL_Control
0x180061d5f  cmp     rcx, rdx
0x180061d62  jz      short loc_180061D83
0x180061d64  test    byte ptr [rcx+1Ch], 1
0x180061d68  jz      short loc_180061D83
0x180061d6a  mov     edx, 10h
0x180061d6f  mov     r9d, eax
0x180061d72  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180061d79  mov     rcx, [rcx+10h]
0x180061d7d  call    WPP_SF_d
0x180061d82  nop
0x180061d83  lea     rcx, [rbp+90h+var_B0]; void *
0x180061d87  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061d8c  jmp     loc_180061CB8
0x180061d91  mov     rdx, [rbp+90h+var_60]
0x180061d95  lea     rcx, [rsp+190h+var_158+8]
0x180061d9a  call    ?ToLowerCase@SenseCnC@Dlp@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; Dlp::SenseCnC::ToLowerCase(wchar_t const *)
0x180061d9f  mov     rdx, rax
0x180061da2  lea     rcx, [rbp+90h+var_B0]
0x180061da6  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180061dab  lea     rcx, [rsp+190h+var_158+8]; void *
0x180061db0  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061db5  xorps   xmm0, xmm0
0x180061db8  movups  [rbp+90h+var_90], xmm0
0x180061dbc  movdqu  [rbp+90h+var_80], xmm6
0x180061dc1  mov     word ptr [rbp+90h+var_90], si
0x180061dc5  lea     rcx, [rbp+90h+var_90]
0x180061dc9  call    ?GetSenseClientVersion@SenseCnC@Dlp@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Dlp::SenseCnC::GetSenseClientVersion(std::wstring &)
0x180061dce  mov     ebx, eax
0x180061dd0  test    eax, eax
0x180061dd2  jns     short loc_180061E14
0x180061dd4  lea     rdx, WPP_GLOBAL_Control
0x180061ddb  mov     rcx, cs:WPP_GLOBAL_Control
0x180061de2  cmp     rcx, rdx
0x180061de5  jz      short loc_180061E06
0x180061de7  test    byte ptr [rcx+1Ch], 1
0x180061deb  jz      short loc_180061E06
0x180061ded  mov     edx, 11h
0x180061df2  mov     r9d, eax
0x180061df5  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180061dfc  mov     rcx, [rcx+10h]
0x180061e00  call    WPP_SF_d
0x180061e05  nop
0x180061e06  lea     rcx, [rbp+90h+var_90]; void *
0x180061e0a  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061e0f  jmp     loc_180061D83
0x180061e14  xorps   xmm0, xmm0
0x180061e17  movups  xmmword ptr [rsp+190h+var_158+8], xmm0
0x180061e1c  movdqu  [rsp+190h+var_148+8], xmm6
0x180061e22  mov     word ptr [rsp+190h+var_158+8], si
0x180061e27  lea     rcx, [rsp+190h+var_158+8]
0x180061e2c  call    ?GetComputerDnsName@SenseCnC@Dlp@@YAJAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; Dlp::SenseCnC::GetComputerDnsName(std::wstring &)
0x180061e31  mov     ebx, eax
0x180061e33  test    eax, eax
0x180061e35  jns     short loc_180061E75
0x180061e37  lea     rdx, WPP_GLOBAL_Control
0x180061e3e  mov     rcx, cs:WPP_GLOBAL_Control
0x180061e45  cmp     rcx, rdx
0x180061e48  jz      short loc_180061E69
0x180061e4a  test    byte ptr [rcx+1Ch], 1
0x180061e4e  jz      short loc_180061E69
0x180061e50  mov     edx, 12h
0x180061e55  mov     r9d, ebx
0x180061e58  lea     r8, WPP_c54effbff82f39d58715a37b7a6c653d_Traceguids
0x180061e5f  mov     rcx, [rcx+10h]
0x180061e63  call    WPP_SF_d
0x180061e68  nop
0x180061e69  lea     rcx, [rsp+190h+var_158+8]; void *
0x180061e6e  call    ??1?$pair@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@VWebSiteActions@EndpointDlp@@@std@@QEAA@XZ; std::pair<std::wstring,EndpointDlp::WebSiteActions>::~pair<std::wstring,EndpointDlp::WebSiteActions>(void)
0x180061e73  jmp     short loc_180061E06
0x180061e75  mov     dword ptr [rbp+90h+var_50], esi
0x180061e78  mov     [rbp+90h+var_58], rsi
0x180061e7c  lea     rdx, [rbp+90h+var_58]; unsigned int *
0x180061e80  lea     rcx, [rbp+90h+var_50]; this
0x180061e84  call    ?GetProductTypeAndInfo@DlpUtils@RealtimeProtection@@YAJAEAIAEA_K@Z; RealtimeProtection::DlpUtils::GetProductTypeAndInfo(uint &,unsigned __int64 &)
0x180061e89  mov     ebx, eax
0x180061e8b  test    eax, eax
0x180061e8d  jns     short loc_180061EAF
0x180061e8f  lea     rdx, WPP_GLOBAL_Control
0x180061e96  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
