# CUMRDPListenerInet::LoadConfiguration(ulong &)

- ea: `0x18003ef10`
- end: `0x18003f645`
- name: `?LoadConfiguration@CUMRDPListenerInet@@AEAAXAEAK@Z`
- size: `1845`
- prototype: `void __fastcall(CUMRDPListenerInet *__hidden this, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800422e0`

## callees

- `0x1800015f0`
- `0x1800071c0`
- `0x180009088`
- `0x18000ee00`
- `0x18000f784`
- `0x180010aa0`
- `0x180012200`
- `0x18001e174`
- `0x180033da0`
- `0x18003c5a4`
- `0x18003ef10`
- `0x180044680`
- `0x18014d010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003efe5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f08c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003efe5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18003f08c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f267`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003f267`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003efa2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003efa2`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18003f283`
- `RDPBASE!PAL_System_CritSecEnter` at `0x18003f283`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18003f411`
- `RDPBASE!RDPENCHLPREG_ReadValueDWORD` at `0x18003f411`
- `OLEAUT32!__imp_VariantInit` at `0x18003f1ee`
- `OLEAUT32!__imp_VariantInit` at `0x18003f1ee`

## string_xrefs

- `0x18003f16a`: `LoadConfiguration`
- `0x18003f4fb`: `LoadConfiguration`
- `0x18003f5ff`: `LoadConfiguration`
- `0x18003f235`: `Failed to write AdapterIndex property.`
- `0x18003f405`: `System\CurrentControlSet\Services\TcpIp\Parameters`
- `0x18003f429`: `Listener has KeepAliveTimeOut and KeepAliveInterval configured`
- `0x18003f502`: `Reading the group policy for Enable Microsoft Entra ID Authentication Enforcement failed.`

## pseudocode

```c
void __fastcall CUMRDPListenerInet::LoadConfiguration(CUMRDPListenerInet *this, unsigned int *a2)
{
  __int64 v4; // rdx
  __int64 v5; // r8
  int v6; // ecx
  int v7; // r8d
  int v8; // r9d
  CUMRDPListenerInet *v9; // rcx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  LONG v13; // edi
  signed int v14; // eax
  __int64 v15; // r8
  int v16; // r9d
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // r8
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  int v23; // r9d
  unsigned int v24; // edi
  signed int v25; // eax
  int v26; // r9d
  char *v27; // rdx
  void *v28; // rax
  signed int v29; // eax
  unsigned int v30; // ebx
  int v31; // ecx
  int v32; // r8d
  int v33; // r9d
  int v34; // eax
  const char *v35; // rax
  int v36; // eax
  int v37; // r9d
  int v38; // eax
  unsigned int v39; // [rsp+50h] [rbp-B0h] BYREF
  int v40; // [rsp+54h] [rbp-ACh] BYREF
  BYTE v41[4]; // [rsp+58h] [rbp-A8h] BYREF
  const char *v42; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+68h] [rbp-98h] BYREF
  DWORD Type; // [rsp+6Ch] [rbp-94h] BYREF
  const char *v45; // [rsp+70h] [rbp-90h] BYREF
  const char *v46; // [rsp+78h] [rbp-88h] BYREF
  const char *v47; // [rsp+80h] [rbp-80h] BYREF
  BYTE Data[8]; // [rsp+88h] [rbp-78h] BYREF
  const char *v49; // [rsp+90h] [rbp-70h] BYREF
  __int64 v50; // [rsp+98h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+A0h] [rbp-60h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR SubKey[264]; // [rsp+C0h] [rbp-40h] BYREF

  v50 = 0;
  if ( (int)StringCchPrintfW(
              SubKey,
              0x104u,
              L"%s\\%s",
              L"System\\CurrentControlSet\\Control\\Terminal Server\\WinStations",
              (char *)this + 128) >= 0 )
  {
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0x20019u, &hKey) )
    {
      *(_DWORD *)Data = *a2;
      cbData = 4;
      Type = 4;
      if ( !RegQueryValueExW(hKey, L"PortNumber", 0, &Type, Data, &cbData) && cbData == 4 && Type == 4 )
      {
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v39 = *(_DWORD *)Data;
          v49 = "Using non-default port";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v6,
            (unsigned int)&dword_18018FC64,
            v7,
            v8,
            (__int64)&v49,
            (__int64)&v39);
        }
        *a2 = *(_DWORD *)Data;
      }
      *(_DWORD *)v41 = 0;
      v39 = 0;
      cbData = 4;
      memset(&pvarg, 0, sizeof(pvarg));
      Type = 4;
      if ( !RegQueryValueExW(hKey, L"LanAdapter", 0, &Type, v41, &cbData)
        && cbData == 4
        && Type == 4
        && *(_DWORD *)v41
        && (unsigned int)CUMRDPListenerInet::GetAdapterIndexFromId(v9, *(unsigned int *)v41, &v39) )
      {
        v13 = v39;
        v49 = 0;
        if ( (unsigned int)dword_1801B76C8 > 4 )
        {
          v40 = *(_DWORD *)v41;
          v45 = "Using non-default LanAdapter";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v10,
            (unsigned int)word_18018FC2A,
            v11,
            v12,
            (__int64)&v45,
            (__int64)&v40,
            (__int64)&v39);
        }
        v14 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, const char **))this + 14))(
                *((_QWORD *)this + 14),
                &IID_IRDPENCPlatformContext,
                &v49);
        v17 = (unsigned int)v14;
        if ( v14 < 0 )
        {
          if ( (unsigned int)dword_1801B76C8 > 2 )
          {
            v39 = v14;
            v45 = "Failed to QI for platformContext";
            v46 = "LoadConfiguration";
            v47 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
            v40 = 1436;
            v42 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              (unsigned int)"LoadConfiguration",
              (unsigned int)&byte_18018FBD7,
              v15,
              v16,
              (__int64)&v42,
              (__int64)&v39,
              (__int64)&v47,
              (__int64)&v40,
              (__int64)&v46,
              (__int64)&v45);
          }
          TCntPtr<IRdpSQMLogger>::SafeRelease(&v49, v17, v15);
          goto LABEL_55;
        }
        VariantInit(&pvarg);
        pvarg.lVal = v13;
        pvarg.vt = 19;
        v20 = (*(__int64 (__fastcall **)(const char *, const WCHAR *, VARIANTARG *))(*(_QWORD *)v49 + 56LL))(
                v49,
                L"LanAdapter",
                &pvarg);
        if ( v20 < 0 && (unsigned int)dword_1801B76C8 > 3 )
        {
          v40 = v20;
          v42 = "Failed to write AdapterIndex property.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_1801B76C8,
            (unsigned int)&unk_18018FBA8,
            v22,
            v23,
            (__int64)&v42,
            (__int64)&v40);
        }
        TCntPtr<IRdpSQMLogger>::SafeRelease(&v49, v21, v22);
      }
      RegCloseKey(hKey);
    }
  }
  v24 = 0;
  v42 = (char *)this + 264;
  if ( *((_DWORD *)this + 68) )
    PAL_System_CritSecEnter(*((_QWORD *)this + 33), v4, v5);
  if ( *((int *)this + 71) >= 1 && *((_DWORD *)this + 100) == 1 && *((_BYTE *)this + 404) == 1 )
    v24 = *((_DWORD *)this + 102);
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)&v42);
  v25 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 14))(
          *((_QWORD *)this + 14),
          &IID_IRDPCollection,
          &v50);
  v18 = (unsigned int)v25;
  if ( v25 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_55;
    v39 = v25;
    v42 = "Failed to QI the platform context properties.";
    v27 = byte_18018FB55;
    v40 = 1472;
    v46 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
    v45 = "Error HResult failed";
    v28 = &v39;
LABEL_54:
    v47 = "LoadConfiguration";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"LoadConfiguration",
      (_DWORD)v27,
      v19,
      v26,
      (__int64)&v45,
      (__int64)v28,
      (__int64)&v46,
      (__int64)&v40,
      (__int64)&v47,
      (__int64)&v42);
    goto LABEL_55;
  }
  v29 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v50 + 72LL))(
          v50,
          L"Tcp::KeepAliveTimeout",
          v24);
  v18 = (unsigned int)v29;
  if ( v29 < 0 )
  {
    if ( (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_55;
    v39 = v29;
    v42 = "Failed to set the RDP TCP Keep Alive Timeout property.";
    v27 = (char *)word_18018FB02;
    v40 = 1476;
    v46 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
    v45 = "Error HResult failed";
    v28 = &v39;
    goto LABEL_54;
  }
  if ( v24 )
  {
    v39 = 0;
    v30 = 1000;
    if ( (unsigned int)RDPENCHLPREG_ReadValueDWORD(
                         -2147483646,
                         L"System\\CurrentControlSet\\Services\\TcpIp\\Parameters",
                         L"KeepAliveInterval",
                         &v39) )
      v30 = v39;
    if ( (unsigned int)dword_1801B76C8 > 4 )
    {
      v40 = v30;
      v42 = "Listener has KeepAliveTimeOut and KeepAliveInterval configured";
      *(_DWORD *)v41 = v24;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v31,
        (unsigned int)&word_18018FAB6,
        v32,
        v33,
        (__int64)&v42,
        (__int64)v41,
        (__int64)&v40);
    }
    v34 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD))(*(_QWORD *)v50 + 72LL))(
            v50,
            L"Tcp::KeepAliveInterval",
            v30);
    v18 = (unsigned int)v34;
    if ( v34 < 0 )
    {
      if ( (unsigned int)dword_1801B76C8 <= 2 )
        goto LABEL_55;
      *(_DWORD *)v41 = v34;
      v35 = "Failed to set the RDP TCP Keep Alive Interval property.";
      v27 = byte_18018FA63;
      v40 = 1494;
LABEL_53:
      v42 = v35;
      v46 = "clientcore\\termsrv\\rdp_bin\\win\\rdpcorets\\umrdplistener.cpp";
      v45 = "Error HResult failed";
      v28 = v41;
      goto LABEL_54;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableMicrosoftEntraIdAuthEnforcement>::__private_IsEnabled(
                           `wil::Feature<__WilFeatureTraits_Feature_EnableMicrosoftEntraIdAuthEnforcement>::GetImpl'::`2'::impl,
                           v18) )
    goto LABEL_55;
  v39 = 0;
  v36 = ReadRegistryGroupPolicyDwordValue(L"EnableMicrosoftEntraIdAuthenticationEnforcement", 0, &v39);
  if ( v36 >= 0 )
  {
    if ( v39 != 1 )
      goto LABEL_55;
    v38 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, __int64))(*(_QWORD *)v50 + 64LL))(
            v50,
            L"EnableMicrosoftEntraIdAuthenticationEnforcement",
            1);
    v18 = (unsigned int)v38;
    if ( v38 >= 0 || (unsigned int)dword_1801B76C8 <= 2 )
      goto LABEL_55;
    *(_DWORD *)v41 = v38;
    v35 = "Failed to set the Enable Microsoft Entra ID Authentication Enforcement property in the platform context.";
    v27 = &byte_18018F9CF;
    v40 = 1511;
    goto LABEL_53;
  }
  if ( (unsigned int)dword_1801B76C8 > 3 )
  {
    v40 = v36;
    v42 = "LoadConfiguration";
    v47 = "Reading the group policy for Enable Microsoft Entra ID Authentication Enforcement failed.";
    v46 = "HResult failed but continue";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (unsigned int)"LoadConfiguration",
      (unsigned int)word_18018FA22,
      v19,
      v37,
      (__int64)&v46,
      (__int64)&v47,
      (__int64)&v40,
      (__int64)&v42);
  }
LABEL_55:
  TCntPtr<IRdpSQMLogger>::SafeRelease(&v50, v18, v19);
}

```

## disassembly

```asm
0x18003ef10  mov     [rsp-8+arg_10], rbx
0x18003ef15  push    rbp
0x18003ef16  push    rdi
0x18003ef17  push    r14
0x18003ef19  lea     rbp, [rsp-1E0h]
0x18003ef21  sub     rsp, 2E0h
0x18003ef28  mov     rax, cs:__security_cookie
0x18003ef2f  xor     rax, rsp
0x18003ef32  mov     [rbp+1F0h+var_20], rax
0x18003ef39  lea     rax, [rcx+80h]
0x18003ef40  mov     [rbp+1F0h+var_258], 0
0x18003ef48  mov     rdi, rdx
0x18003ef4b  mov     [rsp+2F0h+phkResult], rax
0x18003ef50  mov     rbx, rcx
0x18003ef53  lea     r9, aSystemCurrentc_4; "System\\CurrentControlSet\\Control\\Ter"...
0x18003ef5a  mov     edx, 104h; unsigned __int64
0x18003ef5f  lea     rcx, [rbp+1F0h+SubKey]; unsigned __int16 *
0x18003ef63  lea     r8, aSS; "%s\\%s"
0x18003ef6a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18003ef6f  mov     r14d, 4
0x18003ef75  test    eax, eax
0x18003ef77  js      loc_18003F26D
0x18003ef7d  lea     rax, [rbp+1F0h+hKey]
0x18003ef81  mov     [rbp+1F0h+hKey], 0
0x18003ef89  mov     r9d, 20019h; samDesired
0x18003ef8f  mov     [rsp+2F0h+phkResult], rax; phkResult
0x18003ef94  xor     r8d, r8d; ulOptions
0x18003ef97  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18003ef9b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003efa2  call    cs:__imp_RegOpenKeyExW
0x18003efa8  test    eax, eax
0x18003efaa  jnz     loc_18003F26D
0x18003efb0  mov     eax, [rdi]
0x18003efb2  lea     r9, [rsp+2F0h+Type]; lpType
0x18003efb7  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18003efbb  lea     rdx, aPortnumber; "PortNumber"
0x18003efc2  mov     dword ptr [rbp+1F0h+Data], eax
0x18003efc5  xor     r8d, r8d; lpReserved
0x18003efc8  lea     rax, [rsp+2F0h+cbData]
0x18003efcd  mov     [rsp+2F0h+cbData], r14d
0x18003efd2  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x18003efd7  lea     rax, [rbp+1F0h+Data]
0x18003efdb  mov     [rsp+2F0h+phkResult], rax; lpData
0x18003efe0  mov     [rsp+2F0h+Type], r14d
0x18003efe5  call    cs:__imp_RegQueryValueExW
0x18003efeb  test    eax, eax
0x18003efed  jnz     short loc_18003F03E
0x18003efef  cmp     [rsp+2F0h+cbData], r14d
0x18003eff4  jnz     short loc_18003F03E
0x18003eff6  cmp     [rsp+2F0h+Type], r14d
0x18003effb  jnz     short loc_18003F03E
0x18003effd  mov     eax, cs:dword_1801B76C8
0x18003f003  cmp     eax, r14d
0x18003f006  jbe     short loc_18003F039
0x18003f008  mov     eax, dword ptr [rbp+1F0h+Data]
0x18003f00b  lea     rdx, dword_18018FC64
0x18003f012  mov     [rsp+2F0h+var_2A0], eax
0x18003f016  lea     rax, aUsingNonDefaul_1; "Using non-default port"
0x18003f01d  mov     [rbp+1F0h+var_260], rax
0x18003f021  lea     rax, [rsp+2F0h+var_2A0]
0x18003f026  mov     [rsp+2F0h+lpcbData], rax
0x18003f02b  lea     rax, [rbp+1F0h+var_260]
0x18003f02f  mov     [rsp+2F0h+phkResult], rax
0x18003f034  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003f039  mov     eax, dword ptr [rbp+1F0h+Data]
0x18003f03c  mov     [rdi], eax
0x18003f03e  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18003f042  lea     r9, [rsp+2F0h+Type]; lpType
0x18003f047  xor     eax, eax
0x18003f049  mov     dword ptr [rsp+2F0h+var_298], 0
0x18003f051  mov     qword ptr [rbp+1F0h+pvarg+10h], rax
0x18003f055  lea     rdx, aLanadapter; "LanAdapter"
0x18003f05c  lea     rax, [rsp+2F0h+cbData]
0x18003f061  mov     [rsp+2F0h+var_2A0], 0
0x18003f069  mov     [rsp+2F0h+lpcbData], rax; lpcbData
0x18003f06e  xorps   xmm0, xmm0
0x18003f071  lea     rax, [rsp+2F0h+var_298]
0x18003f076  mov     [rsp+2F0h+cbData], r14d
0x18003f07b  xor     r8d, r8d; lpReserved
0x18003f07e  mov     [rsp+2F0h+phkResult], rax; lpData
0x18003f083  movups  xmmword ptr [rbp+1F0h+pvarg], xmm0
0x18003f087  mov     [rsp+2F0h+Type], r14d
0x18003f08c  call    cs:__imp_RegQueryValueExW
0x18003f092  test    eax, eax
0x18003f094  jnz     loc_18003F263
0x18003f09a  cmp     [rsp+2F0h+cbData], r14d
0x18003f09f  jnz     loc_18003F263
0x18003f0a5  cmp     [rsp+2F0h+Type], r14d
0x18003f0aa  jnz     loc_18003F263
0x18003f0b0  mov     edx, dword ptr [rsp+2F0h+var_298]; unsigned int
0x18003f0b4  test    edx, edx
0x18003f0b6  jz      loc_18003F263
0x18003f0bc  lea     r8, [rsp+2F0h+var_2A0]; unsigned int *
0x18003f0c1  call    ?GetAdapterIndexFromId@CUMRDPListenerInet@@AEAAHKPEAK@Z; CUMRDPListenerInet::GetAdapterIndexFromId(ulong,ulong *)
0x18003f0c6  test    eax, eax
0x18003f0c8  jz      loc_18003F263
0x18003f0ce  mov     eax, cs:dword_1801B76C8
0x18003f0d4  mov     edi, [rsp+2F0h+var_2A0]
0x18003f0d8  mov     [rbp+1F0h+var_260], 0
0x18003f0e0  cmp     eax, r14d
0x18003f0e3  jbe     short loc_18003F127
0x18003f0e5  mov     eax, dword ptr [rsp+2F0h+var_298]
0x18003f0e9  lea     rdx, word_18018FC2A
0x18003f0f0  mov     [rsp+2F0h+var_29C], eax
0x18003f0f4  lea     rax, aUsingNonDefaul_0; "Using non-default LanAdapter"
0x18003f0fb  mov     [rsp+2F0h+var_280], rax
0x18003f100  lea     rax, [rsp+2F0h+var_2A0]
0x18003f105  mov     [rsp+2F0h+var_2C0], rax
0x18003f10a  lea     rax, [rsp+2F0h+var_29C]
0x18003f10f  mov     [rsp+2F0h+lpcbData], rax
0x18003f114  lea     rax, [rsp+2F0h+var_280]
0x18003f119  mov     [rsp+2F0h+phkResult], rax
0x18003f11e  mov     [rsp+2F0h+var_2A0], edi
0x18003f122  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003f127  mov     rcx, [rbx+70h]
0x18003f12b  lea     r8, [rbp+1F0h+var_260]
0x18003f12f  lea     rdx, IID_IRDPENCPlatformContext
0x18003f136  mov     rax, [rcx]
0x18003f139  mov     rax, [rax]
0x18003f13c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f141  mov     edx, eax
0x18003f143  test    eax, eax
0x18003f145  jns     loc_18003F1EA
0x18003f14b  mov     ecx, cs:dword_1801B76C8
0x18003f151  cmp     ecx, 2
0x18003f154  jbe     loc_18003F1DC
0x18003f15a  lea     rax, aFailedToQiForP; "Failed to QI for platformContext"
0x18003f161  mov     [rsp+2F0h+var_2A0], edx
0x18003f165  mov     [rsp+2F0h+var_280], rax
0x18003f16a  lea     rcx, aLoadconfigurat; "LoadConfiguration"
0x18003f171  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003f178  mov     [rsp+2F0h+var_278], rcx
0x18003f17d  mov     [rbp+1F0h+var_270], rax
0x18003f181  lea     rdx, byte_18018FBD7
0x18003f188  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003f18f  mov     [rsp+2F0h+var_29C], 59Ch
0x18003f197  mov     [rsp+2F0h+var_290], rax
0x18003f19c  lea     rax, [rsp+2F0h+var_280]
0x18003f1a1  mov     [rsp+2F0h+var_2A8], rax
0x18003f1a6  lea     rax, [rsp+2F0h+var_278]
0x18003f1ab  mov     [rsp+2F0h+var_2B0], rax
0x18003f1b0  lea     rax, [rsp+2F0h+var_29C]
0x18003f1b5  mov     [rsp+2F0h+var_2B8], rax
0x18003f1ba  lea     rax, [rbp+1F0h+var_270]
0x18003f1be  mov     [rsp+2F0h+var_2C0], rax
0x18003f1c3  lea     rax, [rsp+2F0h+var_2A0]
0x18003f1c8  mov     [rsp+2F0h+lpcbData], rax
0x18003f1cd  lea     rax, [rsp+2F0h+var_290]
0x18003f1d2  mov     [rsp+2F0h+phkResult], rax
0x18003f1d7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18003f1dc  lea     rcx, [rbp+1F0h+var_260]
0x18003f1e0  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18003f1e5  jmp     loc_18003F619
0x18003f1ea  lea     rcx, [rbp+1F0h+pvarg]; pvarg
0x18003f1ee  call    cs:__imp_VariantInit
0x18003f1f4  mov     rcx, [rbp+1F0h+var_260]
0x18003f1f8  lea     r8, [rbp+1F0h+pvarg]
0x18003f1fc  mov     eax, 13h
0x18003f201  mov     dword ptr [rbp+1F0h+pvarg+8], edi
0x18003f204  mov     word ptr [rbp+1F0h+pvarg], ax
0x18003f208  lea     rdx, aLanadapter; "LanAdapter"
0x18003f20f  mov     rax, [rcx]
0x18003f212  mov     rax, [rax+38h]
0x18003f216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f21b  test    eax, eax
0x18003f21d  jns     short loc_18003F25A
0x18003f21f  mov     ecx, cs:dword_1801B76C8
0x18003f225  cmp     ecx, 3
0x18003f228  jbe     short loc_18003F25A
0x18003f22a  mov     [rsp+2F0h+var_29C], eax
0x18003f22e  lea     rdx, unk_18018FBA8
0x18003f235  lea     rax, aFailedToWriteA; "Failed to write AdapterIndex property."
0x18003f23c  mov     [rsp+2F0h+var_290], rax
0x18003f241  lea     rax, [rsp+2F0h+var_29C]
0x18003f246  mov     [rsp+2F0h+lpcbData], rax
0x18003f24b  lea     rax, [rsp+2F0h+var_290]
0x18003f250  mov     [rsp+2F0h+phkResult], rax
0x18003f255  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18003f25a  lea     rcx, [rbp+1F0h+var_260]
0x18003f25e  call    ?SafeRelease@?$TCntPtr@VIRdpSQMLogger@@@@AEAAXXZ; TCntPtr<IRdpSQMLogger>::SafeRelease(void)
0x18003f263  mov     rcx, [rbp+1F0h+hKey]; hKey
0x18003f267  call    cs:__imp_RegCloseKey
0x18003f26d  lea     rcx, [rbx+108h]
0x18003f274  xor     edi, edi
0x18003f276  mov     [rsp+2F0h+var_290], rcx
0x18003f27b  cmp     [rcx+8], edi
0x18003f27e  jz      short loc_18003F289
0x18003f280  mov     rcx, [rcx]
0x18003f283  call    cs:__imp_PAL_System_CritSecEnter
0x18003f289  cmp     dword ptr [rbx+11Ch], 1
0x18003f290  jl      short loc_18003F2AA
0x18003f292  cmp     dword ptr [rbx+190h], 1
0x18003f299  jnz     short loc_18003F2AA
0x18003f29b  cmp     byte ptr [rbx+194h], 1
0x18003f2a2  jnz     short loc_18003F2AA
0x18003f2a4  mov     edi, [rbx+198h]
0x18003f2aa  lea     rcx, [rsp+2F0h+var_290]; this
0x18003f2af  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x18003f2b4  mov     rcx, [rbx+70h]
0x18003f2b8  lea     r8, [rbp+1F0h+var_258]
0x18003f2bc  lea     rdx, IID_IRDPCollection
0x18003f2c3  mov     rax, [rcx]
0x18003f2c6  mov     rax, [rax]
0x18003f2c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f2ce  mov     edx, eax
0x18003f2d0  test    eax, eax
0x18003f2d2  jns     short loc_18003F34B
0x18003f2d4  mov     ecx, cs:dword_1801B76C8
0x18003f2da  cmp     ecx, 2
0x18003f2dd  jbe     loc_18003F619
0x18003f2e3  lea     rax, aFailedToQiTheP_0; "Failed to QI the platform context prope"...
0x18003f2ea  mov     [rsp+2F0h+var_2A0], edx
0x18003f2ee  mov     [rsp+2F0h+var_290], rax
0x18003f2f3  lea     rdx, byte_18018FB55
0x18003f2fa  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003f301  mov     [rsp+2F0h+var_29C], 5C0h
0x18003f309  mov     [rsp+2F0h+var_278], rax
0x18003f30e  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003f315  mov     [rsp+2F0h+var_280], rax
0x18003f31a  lea     rax, [rsp+2F0h+var_290]
0x18003f31f  mov     [rsp+2F0h+var_2A8], rax
0x18003f324  lea     rax, [rbp+1F0h+var_270]
0x18003f328  mov     [rsp+2F0h+var_2B0], rax
0x18003f32d  lea     rax, [rsp+2F0h+var_29C]
0x18003f332  mov     [rsp+2F0h+var_2B8], rax
0x18003f337  lea     rax, [rsp+2F0h+var_278]
0x18003f33c  mov     [rsp+2F0h+var_2C0], rax
0x18003f341  lea     rax, [rsp+2F0h+var_2A0]
0x18003f346  jmp     loc_18003F5FA
0x18003f34b  mov     rcx, [rbp+1F0h+var_258]
0x18003f34f  lea     rdx, aTcpKeepaliveti; "Tcp::KeepAliveTimeout"
0x18003f356  mov     r8d, edi
0x18003f359  mov     rax, [rcx]
0x18003f35c  mov     rax, [rax+48h]
0x18003f360  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f365  mov     edx, eax
0x18003f367  test    eax, eax
0x18003f369  jns     short loc_18003F3E2
0x18003f36b  mov     ecx, cs:dword_1801B76C8
0x18003f371  cmp     ecx, 2
0x18003f374  jbe     loc_18003F619
0x18003f37a  lea     rax, aFailedToSetThe_16; "Failed to set the RDP TCP Keep Alive Ti"...
0x18003f381  mov     [rsp+2F0h+var_2A0], edx
0x18003f385  mov     [rsp+2F0h+var_290], rax
0x18003f38a  lea     rdx, word_18018FB02
0x18003f391  lea     rax, aClientcoreTerm_8; "clientcore\\termsrv\\rdp_bin\\win\\rdpc"...
0x18003f398  mov     [rsp+2F0h+var_29C], 5C4h
0x18003f3a0  mov     [rsp+2F0h+var_278], rax
0x18003f3a5  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18003f3ac  mov     [rsp+2F0h+var_280], rax
0x18003f3b1  lea     rax, [rsp+2F0h+var_290]
0x18003f3b6  mov     [rsp+2F0h+var_2A8], rax
0x18003f3bb  lea     rax, [rbp+1F0h+var_270]
0x18003f3bf  mov     [rsp+2F0h+var_2B0], rax
0x18003f3c4  lea     rax, [rsp+2F0h+var_29C]
0x18003f3c9  mov     [rsp+2F0h+var_2B8], rax
0x18003f3ce  lea     rax, [rsp+2F0h+var_278]
0x18003f3d3  mov     [rsp+2F0h+var_2C0], rax
0x18003f3d8  lea     rax, [rsp+2F0h+var_2A0]
0x18003f3dd  jmp     loc_18003F5FA
0x18003f3e2  test    edi, edi
0x18003f3e4  jz      loc_18003F4B5
0x18003f3ea  lea     r9, [rsp+2F0h+var_2A0]
0x18003f3ef  mov     [rsp+2F0h+var_2A0], 0
0x18003f3f7  lea     r8, aKeepaliveinter; "KeepAliveInterval"
0x18003f3fe  mov     rcx, 0FFFFFFFF80000002h
0x18003f405  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Tc"...
0x18003f40c  mov     ebx, 3E8h
0x18003f411  call    cs:__imp_RDPENCHLPREG_ReadValueDWORD
0x18003f417  test    eax, eax
0x18003f419  mov     eax, cs:dword_1801B76C8
0x18003f41f  cmovnz  ebx, [rsp+2F0h+var_2A0]
0x18003f424  cmp     eax, r14d
0x18003f427  jbe     short loc_18003F467
0x18003f429  lea     rax, aListenerHasKee; "Listener has KeepAliveTimeOut and KeepA"...
0x18003f430  mov     [rsp+2F0h+var_29C], ebx
0x18003f434  mov     [rsp+2F0h+var_290], rax
0x18003f439  lea     rdx, word_18018FAB6
0x18003f440  lea     rax, [rsp+2F0h+var_29C]
0x18003f445  mov     dword ptr [rsp+2F0h+var_298], edi
0x18003f449  mov     [rsp+2F0h+var_2C0], rax
0x18003f44e  lea     rax, [rsp+2F0h+var_298]
0x18003f453  mov     [rsp+2F0h+lpcbData], rax
0x18003f458  lea     rax, [rsp+2F0h+var_290]
0x18003f45d  mov     [rsp+2F0h+phkResult], rax
0x18003f462  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18003f467  mov     rcx, [rbp+1F0h+var_258]
0x18003f46b  lea     rdx, aTcpKeepalivein; "Tcp::KeepAliveInterval"
0x18003f472  mov     r8d, ebx
0x18003f475  mov     rax, [rcx]
0x18003f478  mov     rax, [rax+48h]
0x18003f47c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f481  mov     edx, eax
0x18003f483  test    eax, eax
0x18003f485  jns     short loc_18003F4B5
0x18003f487  mov     ecx, cs:dword_1801B76C8
0x18003f48d  cmp     ecx, 2
0x18003f490  jbe     loc_18003F619
0x18003f496  mov     dword ptr [rsp+2F0h+var_298], edx
0x18003f49a  lea     rax, aFailedToSetThe_7; "Failed to set the RDP TCP Keep Alive In"...
  ... truncated ...
```
