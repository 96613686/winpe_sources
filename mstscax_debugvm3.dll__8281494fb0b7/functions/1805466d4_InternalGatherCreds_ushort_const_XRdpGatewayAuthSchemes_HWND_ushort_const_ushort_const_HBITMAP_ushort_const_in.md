# InternalGatherCreds(ushort const *,_XRdpGatewayAuthSchemes,HWND__ *,ushort const *,ushort const *,HBITMAP__ *,ushort const *,int,int,int,int,ushort const *,ushort const *,int *,int *,ushort * *,ushort * *,void * *,_AAUSERCREDS * *,_XRdpGatewayAuthSchemes *,int,int)

- ea: `0x1805466d4`
- end: `0x1805474ef`
- name: `?InternalGatherCreds@@YAJPEBGW4_XRdpGatewayAuthSchemes@@PEAUHWND__@@00PEAUHBITMAP__@@0HHHH00PEAH4PEAPEAG5PEAPEAXPEAPEAU_AAUSERCREDS@@PEAW41@HH@Z`
- size: `3611`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180545c30`

## callees

- `0x18001e170`
- `0x18002311c`
- `0x18002a334`
- `0x180039ce4`
- `0x180085e04`
- `0x18008a2c0`
- `0x1800cfa74`
- `0x1800dafe4`
- `0x1800e9b1c`
- `0x1800ebae0`
- `0x18012966c`
- `0x180472ed0`
- `0x1804730ec`
- `0x180473da8`
- `0x180474234`
- `0x180474668`
- `0x180545838`
- `0x180545eec`
- `0x180546248`
- `0x1805464b4`
- `0x1805466d4`
- `0x1805474f8`
- `0x180688f3e`
- `0x180688fc0`
- `0x180689080`
- `0x18068c010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1805471cd`
- `KERNEL32!GetLastError` at `0x180547258`
- `KERNEL32!GetLastError` at `0x1805471cd`
- `KERNEL32!GetLastError` at `0x180547258`
- `KERNEL32!LocalAlloc` at `0x180546a2a`
- `KERNEL32!LocalAlloc` at `0x180546f31`
- `KERNEL32!LocalAlloc` at `0x180546f91`
- `KERNEL32!LocalAlloc` at `0x180546a2a`
- `KERNEL32!LocalAlloc` at `0x180546f31`
- `KERNEL32!LocalAlloc` at `0x180546f91`
- `KERNEL32!LocalFree` at `0x180546cc9`
- `KERNEL32!LocalFree` at `0x180546cf8`
- `KERNEL32!LocalFree` at `0x18054744b`
- `KERNEL32!LocalFree` at `0x18054745a`
- `KERNEL32!LocalFree` at `0x18054746c`
- `KERNEL32!LocalFree` at `0x18054747e`
- `KERNEL32!LocalFree` at `0x180547490`
- `KERNEL32!LocalFree` at `0x1805474e4`
- `KERNEL32!LocalFree` at `0x180546cc9`
- `KERNEL32!LocalFree` at `0x180546cf8`
- `KERNEL32!LocalFree` at `0x18054744b`
- `KERNEL32!LocalFree` at `0x18054745a`
- `KERNEL32!LocalFree` at `0x18054746c`
- `KERNEL32!LocalFree` at `0x18054747e`
- `KERNEL32!LocalFree` at `0x180547490`
- `KERNEL32!LocalFree` at `0x1805474e4`
- `KERNEL32!lstrcmpiW` at `0x180546efe`
- `KERNEL32!lstrcmpiW` at `0x180546efe`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x1805471c3`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x18054724e`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x1805471c3`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x18054724e`
- `credui!CredUIParseUserNameW` at `0x1805472ce`
- `credui!CredUIParseUserNameW` at `0x1805472ce`

## string_xrefs

- `0x1805469b8`: `CTscCredentialsQueryUi::CreateInstance failed!`
- `0x1805470f9`: `StringCchCopy`
- `0x180546dde`: `CTscAuthenticationBlob::CreateInstance`
- `0x180547362`: `StringCbCopy`
- `0x180547219`: `CredWriteDomainCredentials failed`
- `0x1805472a4`: `CredWriteDomainCredentials for canonical name failed`

## pseudocode

```c
__int64 __fastcall InternalGatherCreds(
        wchar_t *a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int16 *a4,
        unsigned __int16 *a5,
        __int64 a6,
        wchar_t *a7,
        int a8,
        int a9,
        int a10,
        int a11,
        __int64 a12,
        unsigned __int16 *a13,
        int *a14,
        int *a15,
        HLOCAL *a16,
        HLOCAL *a17,
        struct CTscAuthenticationBlob **a18,
        WCHAR **a19,
        unsigned int *a20)
{
  struct CTscAuthenticationBlob *v20; // rbx
  BYTE *v23; // r12
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v25; // edx
  const char *v26; // rcx
  signed int v27; // edi
  unsigned int v28; // eax
  int v29; // eax
  unsigned int v30; // eax
  int v31; // eax
  _DWORD *v32; // rax
  unsigned int v33; // eax
  unsigned int v34; // edi
  const unsigned __int16 *v35; // r8
  wchar_t *v36; // r9
  const unsigned __int16 *v37; // r8
  CTscCredentialsQueryUi *v38; // rcx
  const unsigned __int16 *v39; // r8
  int v40; // eax
  int v41; // eax
  unsigned int v42; // eax
  int v43; // edx
  const char *v44; // rcx
  HLOCAL v45; // rcx
  __int64 v46; // rdx
  _BYTE *v47; // rax
  _BYTE *v48; // rdx
  HLOCAL v49; // rcx
  unsigned __int64 i; // rax
  HLOCAL v51; // rbx
  int IsBlobSmartCard; // r12d
  unsigned int v53; // edx
  void *v54; // rcx
  int v55; // eax
  HKEY v56; // rax
  unsigned int v57; // eax
  unsigned int v58; // eax
  unsigned int v59; // eax
  __int64 v60; // rdx
  bool v61; // zf
  unsigned int v62; // eax
  unsigned __int64 v63; // rdi
  unsigned int v64; // eax
  unsigned __int16 *v65; // r11
  int CanonicalName; // eax
  char v67; // di
  unsigned int v68; // eax
  unsigned int v69; // eax
  int v70; // edx
  const char *v71; // rcx
  WCHAR *v72; // rdi
  signed int LastError; // eax
  signed int v74; // eax
  signed int v75; // eax
  unsigned int v76; // eax
  HLOCAL *v77; // rcx
  __int64 v78; // rcx
  unsigned __int64 v79; // rdx
  BYTE *j; // rax
  unsigned __int16 **v82; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpString1; // [rsp+60h] [rbp-A0h] BYREF
  size_t Size; // [rsp+68h] [rbp-98h] BYREF
  int v85; // [rsp+70h] [rbp-90h] BYREF
  WCHAR *user; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v87; // [rsp+80h] [rbp-80h] BYREF
  int v88; // [rsp+88h] [rbp-78h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp-70h]
  HLOCAL v90; // [rsp+98h] [rbp-68h]
  PCWSTR UserName; // [rsp+A0h] [rbp-60h] BYREF
  struct CTscAuthenticationBlob *v92; // [rsp+A8h] [rbp-58h] BYREF
  HLOCAL v93; // [rsp+B0h] [rbp-50h]
  HLOCAL Src; // [rsp+B8h] [rbp-48h] BYREF
  void *Block; // [rsp+C0h] [rbp-40h]
  struct CTscCredentialsQueryUi *v96; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int64 v97; // [rsp+D0h] [rbp-30h] BYREF
  HLOCAL hMem; // [rsp+D8h] [rbp-28h]
  WCHAR **v99; // [rsp+E0h] [rbp-20h]
  unsigned int *v100; // [rsp+E8h] [rbp-18h]
  HLOCAL *v101; // [rsp+F0h] [rbp-10h]
  struct CTscAuthenticationBlob **v102; // [rsp+F8h] [rbp-8h]
  int *v103; // [rsp+100h] [rbp+0h]
  int *v104; // [rsp+108h] [rbp+8h]
  HLOCAL MessageText; // [rsp+110h] [rbp+10h]
  HLOCAL CaptionText; // [rsp+118h] [rbp+18h]
  __int64 v107; // [rsp+120h] [rbp+20h]
  unsigned __int16 *v108; // [rsp+128h] [rbp+28h]
  unsigned __int16 *v109; // [rsp+130h] [rbp+30h]
  wchar_t *v110; // [rsp+138h] [rbp+38h]
  HLOCAL *v111; // [rsp+140h] [rbp+40h]
  struct _CREDENTIALW Credential; // [rsp+150h] [rbp+50h] BYREF
  struct _CREDENTIAL_TARGET_INFORMATIONW TargetInfo; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v114; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v115[128]; // [rsp+1F8h] [rbp+F8h] BYREF
  unsigned __int16 v116[2052]; // [rsp+2F8h] [rbp+1F8h] BYREF
  unsigned __int16 v117[264]; // [rsp+1300h] [rbp+1200h] BYREF
  unsigned __int16 v118[520]; // [rsp+1510h] [rbp+1410h] BYREF
  unsigned __int16 v119[2056]; // [rsp+1920h] [rbp+1820h] BYREF

  v20 = 0;
  v108 = a5;
  v23 = 0;
  v110 = a7;
  v103 = a14;
  v104 = a15;
  v111 = a16;
  v101 = a17;
  v107 = a3;
  String1 = a1;
  v102 = a18;
  v109 = a4;
  v99 = a19;
  v100 = a20;
  UserName = 0;
  v97 = 0;
  lpString1 = 0;
  v87 = 0;
  memset_0(&v114, 0, 0x1108u);
  v85 = 0;
  memset_0(&Credential, 0, sizeof(Credential));
  CaptionText = GetCaptionText(a1);
  MessageText = GetMessageText(a1);
  v96 = 0;
  TCntPtr<WindowsRemoteAppLib::CRailNotify>::SafeAddRef(&v96);
  v88 = 0;
  v92 = 0;
  TCntPtr<WindowsRemoteAppLib::CRailNotify>::SafeAddRef(&v92);
  Src = 0;
  Size = 0;
  Block = 0;
  if ( !a19 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 37;
    v26 = "ppUserCreds";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v25,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v26);
LABEL_7:
    v27 = -2147467261;
    goto LABEL_208;
  }
  if ( !a20 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v25 = 38;
    v26 = "pAuthSchemeUsed";
    goto LABEL_6;
  }
  v93 = 0;
  v90 = 0;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v28 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      v28,
      (__int64)a1);
  }
  *v102 = 0;
  *v103 = 0;
  *v104 = 0;
  *v99 = 0;
  *v100 = 6;
  *v101 = 0;
  if ( !a8 )
  {
    LODWORD(user) = 0;
    AACredHelper::ReadCreds(a2, a1, 0, &user);
    if ( (_DWORD)user )
    {
      if ( !a9 )
      {
        user = 0;
        v27 = 0;
        v29 = 5;
        if ( a2 != 6 )
          v29 = a2;
        a2 = v29;
        goto LABEL_197;
      }
    }
  }
  v27 = CTscCredentialsQueryUi::CreateInstance(&v96);
  if ( v27 < 0 )
  {
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v30 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
        v30,
        (__int64)"CTscCredentialsQueryUi::CreateInstance failed!",
        v27);
    }
    goto LABEL_200;
  }
  if ( a8 || a9 )
  {
    v31 = 5;
    if ( a2 != 4 )
      v31 = a2;
    a2 = v31;
    if ( (v31 == 2 || (unsigned int)(v31 - 5) <= 1) && a8 )
      AACredHelper::CleanUpCreds(String1);
  }
  v32 = LocalAlloc(0x40u, 0x638u);
  hMem = v32;
  if ( !v32 )
  {
    v27 = -2147024882;
    if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
      && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v33 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
        v33,
        (__int64)"allocate memory for myCredsBuf",
        14);
    }
    goto LABEL_200;
  }
  *v32 = -559038737;
  memset_0(v118, 0, 0x404u);
  if ( a13 && (int)StringCchCopyW(v118, 0x202u, a13) < 0 )
    v118[0] = 0;
  user = (WCHAR *)((char *)hMem + 8);
  v34 = 0;
  memset_0((char *)hMem + 8, 0, 0x630u);
  switch ( a2 )
  {
    case 1u:
    case 2u:
      goto LABEL_56;
    case 3u:
      v34 = 32;
      LODWORD(v23) = 1;
      break;
    case 5u:
LABEL_56:
      LODWORD(v23) = 2;
      break;
    default:
      if ( a2 != 6
        && a2 != 9
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, a2);
      }
      break;
  }
  v35 = (const unsigned __int16 *)CaptionText;
  v114 = v107;
  if ( v108 )
    v35 = v108;
  StringCchCopyW(v115, 0x80u, v35);
  if ( !v109 )
  {
    v37 = (const unsigned __int16 *)MessageText;
    goto LABEL_68;
  }
  if ( !v110 )
  {
    v36 = String1;
    goto LABEL_65;
  }
  if ( a11 )
  {
    v36 = v110;
LABEL_65:
    StringCchPrintfW(v119, 0x800u, v109, v36);
    goto LABEL_66;
  }
  StringCchPrintfW(v119, 0x800u, v109, String1, v110);
LABEL_66:
  v37 = v119;
LABEL_68:
  StringCchCopyW(v116, 0x800u, v37);
  if ( !a9 && a2 <= 9 )
  {
    v40 = 580;
    if ( _bittest(&v40, a2) )
    {
      if ( !a10 )
        v34 = 2;
    }
  }
  v41 = CTscCredentialsQueryUi::PromptForCredentials(
          v38,
          (struct tagTSC_CREDENTIALS_UI_INFO *)&v114,
          v39,
          a8 != 0 ? 0x8009030C : 0,
          v118,
          (const unsigned __int16 *)v82,
          &v85,
          v34,
          (unsigned int)v23,
          &Src,
          (unsigned int *)&Size);
  v27 = v41;
  if ( v41 )
  {
    if ( v41 > 0 )
      v27 = (unsigned __int16)v41 | 0x80070000;
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
      v43 = 43;
      v44 = "pCredentialsQueryUi->PromptForCredentials";
      goto LABEL_81;
    }
  }
  IsBlobSmartCard = CTscCredentialsQueryUi::IsBlobSmartCard(Src, Size);
  v55 = CTscCredentialsQueryUi::UnpackBlob(
          1,
          v54,
          v53,
          (unsigned __int16 **)&UserName,
          &v97,
          (unsigned __int16 **)&lpString1,
          &v87,
          &v88);
  v27 = v55;
  if ( v55 )
  {
    if ( v55 > 0 )
      v27 = (unsigned __int16)v55 | 0x80070000;
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
        || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_82;
      }
      v42 = RdpWppGetCurrentThreadActivityIdPrefix();
      v43 = 44;
      v44 = "pCredentialsQueryUi->UnpackBlob";
      goto LABEL_81;
    }
  }
  v27 = CTscAuthenticationBlob::CreateInstance(Src, (unsigned int)Size, &v92);
  if ( v27 < 0 )
  {
    if ( WPP_GLOBAL_Control == (HKEY)&WPP_GLOBAL_Control
      || ((_BYTE)WPP_GLOBAL_Control[7] & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_82;
    }
    v42 = RdpWppGetCurrentThreadActivityIdPrefix();
    v43 = 45;
    v44 = "CTscAuthenticationBlob::CreateInstance";
LABEL_81:
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v43,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      v42,
      (__int64)v44,
      v27);
LABEL_82:
    v23 = (BYTE *)lpString1;
    goto LABEL_83;
  }
  v56 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
    && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v57 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v57);
    v56 = WPP_GLOBAL_Control;
  }
  if ( a2 != 3 )
  {
    if ( a2 == 2 )
    {
      if ( IsBlobSmartCard != 1 )
        goto LABEL_129;
      if ( v56 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v56[7] & 1) != 0 && *((_BYTE *)v56 + 25) >= 2u )
      {
        v59 = RdpWppGetCurrentThreadActivityIdPrefix();
        v60 = 48;
LABEL_119:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v60, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v59);
      }
    }
    else
    {
      if ( a2 != 1 )
      {
        if ( a2 == 6 )
          a2 = IsBlobSmartCard != 0 ? 3 : 5;
        goto LABEL_129;
      }
      if ( IsBlobSmartCard != 1 )
        goto LABEL_129;
      if ( v56 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v56[7] & 1) != 0 && *((_BYTE *)v56 + 25) >= 2u )
      {
        v59 = RdpWppGetCurrentThreadActivityIdPrefix();
        v60 = 49;
        goto LABEL_119;
      }
    }
    v27 = -2147001871;
    goto LABEL_82;
  }
  if ( !IsBlobSmartCard )
  {
    if ( v56 != (HKEY)&WPP_GLOBAL_Control && ((_BYTE)v56[7] & 1) != 0 && *((_BYTE *)v56 + 25) >= 2u )
    {
      v58 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v58);
    }
    v27 = -2147001870;
    goto LABEL_82;
  }
LABEL_129:
  if ( lstrcmpiW(lpString1, &sourceString) )
  {
    v93 = LocalAlloc(0x40u, 2 * v87);
    if ( !v93 )
    {
      v27 = -2147024882;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v62 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          50,
          (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
          v62,
          (__int64)"allocate memory for pCredSharePassword",
          14);
      }
      goto LABEL_82;
    }
    v63 = v97;
    v90 = LocalAlloc(0x40u, 2 * v97);
    if ( !v90 )
    {
      v27 = -2147024882;
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v64 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
          v64,
          (__int64)"allocate memory for pCredShareUsername",
          14);
      }
      goto LABEL_82;
    }
    v23 = (BYTE *)lpString1;
    StringCchCopyW((unsigned __int16 *)v93, v87, lpString1);
    StringCchCopyW(v65, v63, UserName);
    if ( (a2 == 2 || a2 == 5) && !a9 && v85 == 1 )
    {
      CanonicalName = GetCanonicalName(String1);
      v67 = CanonicalName;
      if ( CanonicalName < 0
        && WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v68 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
          v68,
          (__int64)"GetCanonicalName failed",
          v67);
      }
      memset_0(&Credential, 0, sizeof(Credential));
      HIDWORD(Size) = 3 - (a2 != 3);
      v27 = StringCbCopyW(v117, 0x20Au, String1);
      if ( v27 < 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v69 = RdpWppGetCurrentThreadActivityIdPrefix();
          v70 = 53;
          v71 = "StringCchCopy";
LABEL_156:
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v70,
            (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
            v69,
            (__int64)v71,
            v27);
          goto LABEL_193;
        }
        goto LABEL_193;
      }
      v72 = (WCHAR *)Block;
      Credential.Type = HIDWORD(Size);
      Credential.TargetName = v117;
      Credential.Flags = 0;
      Credential.CredentialBlob = v23;
      Credential.Persist = 2;
      Credential.Comment = (LPWSTR)Block;
      Credential.CredentialBlobSize = 2 * v87 - 2;
      Credential.UserName = (LPWSTR)UserName;
      memset_0(&TargetInfo, 0, sizeof(TargetInfo));
      TargetInfo.CredTypeCount = 1;
      TargetInfo.TargetName = v117;
      TargetInfo.Flags = 1;
      TargetInfo.CredTypes = (LPDWORD)&Size + 1;
      TargetInfo.DnsServerName = v117;
      if ( !CredWriteDomainCredentialsW(&TargetInfo, &Credential, 0) )
      {
        LastError = GetLastError();
        v27 = LastError;
        if ( LastError > 0 )
          v27 = (unsigned __int16)LastError | 0x80070000;
        if ( v27 >= 0 )
          v27 = -2147467259;
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v69 = RdpWppGetCurrentThreadActivityIdPrefix();
          v70 = 54;
          v71 = "CredWriteDomainCredentials failed";
          goto LABEL_156;
        }
LABEL_193:
        if ( Block )
          operator delete(Block);
        if ( v27 < 0 )
          goto LABEL_83;
        goto LABEL_196;
      }
      if ( v72 )
      {
        TargetInfo.TargetName = v72;
        TargetInfo.DnsServerName = v72;
        Credential.TargetName = v72;
        if ( !CredWriteDomainCredentialsW(&TargetInfo, &Credential, 0) )
        {
          v74 = GetLastError();
          v27 = v74;
          if ( v74 > 0 )
            v27 = (unsigned __int16)v74 | 0x80070000;
          if ( v27 >= 0 )
            v27 = -2147467259;
          if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
            && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v69 = RdpWppGetCurrentThreadActivityIdPrefix();
            v70 = 55;
            v71 = "CredWriteDomainCredentials for canonical name failed";
            goto LABEL_156;
          }
          goto LABEL_193;
        }
      }
    }
    v75 = CredUIParseUserNameW(UserName, user, 0x104u, user + 522, 0x104u);
    v27 = v75;
    if ( !v75 )
      goto LABEL_184;
    if ( v75 > 0 )
      v27 = (unsigned __int16)v75 | 0x80070000;
    if ( v27 < 0 )
    {
      if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
        && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v69 = RdpWppGetCurrentThreadActivityIdPrefix();
        v70 = 56;
        v71 = "CredUIParseUserName";
        goto LABEL_156;
      }
    }
    else
    {
LABEL_184:
      v27 = StringCbCopyW(user + 261, 0x20Au, (const unsigned __int16 *)v23);
      if ( v27 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
          && ((_BYTE)WPP_GLOBAL_Control[7] & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          v76 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v76);
        }
      }
      else if ( WPP_GLOBAL_Control != (HKEY)&WPP_GLOBAL_Control
             && ((_BYTE)WPP_GLOBAL_Control[7] & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v69 = RdpWppGetCurrentThreadActivityIdPrefix();
        v70 = 57;
        v71 = "StringCbCopy";
        goto LABEL_156;
      }
    }
    goto LABEL_193;
  }
  v61 = IsBlobSmartCard == 1;
  v23 = (BYTE *)lpString1;
  if ( v61 )
  {
    v27 = -2146435030;
LABEL_83:
    v45 = hMem;
    v46 = 1592;
    v47 = hMem;
    do
    {
      *v47++ = 0;
      --v46;
    }
    while ( v46 );
    LocalFree(v45);
    v48 = v93;
    if ( v93 )
    {
      v49 = v93;
      for ( i = 2 * v87; i; --i )
        *v48++ = 0;
      v51 = v90;
      LocalFree(v49);
    }
    else
    {
      v51 = v90;
    }
    if ( v51 )
      LocalFree(v51);
    goto LABEL_200;
  }
LABEL_196:
  v20 = v92;
LABEL_197:
  *v99 = user;
  v77 = v101;
  *v100 = a2;
  *v77 = v93;
  *v111 = v90;
  if ( v20 )
  {
    v78 = ((unsigned __int64)v20 + 48) & ((unsigned __int128)-(__int128)(unsigned __int64)v20 >> 64);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v78 + 8LL))(v78);
    *v102 = v20;
  }
  *v103 = v88;
  *v104 = v85;
LABEL_200:
  if ( v23 )
  {
    v79 = 2 * v87;
    for ( j = v23; v79; --v79 )
      *j++ = 0;
    LocalFree(v23);
  }
  if ( UserName )
    LocalFree((HLOCAL)UserName);
  if ( Src )
    LocalFree(Src);
LABEL_208:
  if ( MessageText )
    LocalFree(MessageText);
  if ( CaptionText )
    LocalFree(CaptionText);
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v92);
  TCntPtr<SlidingStats<double,5,1>>::SafeRelease(&v96);
  return (unsigned int)v27;
}

```

## disassembly

```asm
0x1805466d4  mov     [rsp-8+arg_18], rbx
0x1805466d9  push    rbp
0x1805466da  push    rsi
0x1805466db  push    rdi
0x1805466dc  push    r12
0x1805466de  push    r13
0x1805466e0  push    r14
0x1805466e2  push    r15
0x1805466e4  lea     rbp, [rsp-2840h]
0x1805466ec  mov     eax, 2940h
0x1805466f1  call    _alloca_probe
0x1805466f6  sub     rsp, rax
0x1805466f9  mov     rax, cs:__security_cookie
0x180546700  xor     rax, rsp
0x180546703  mov     [rbp+2870h+var_40], rax
0x18054670a  mov     rax, [rbp+2870h+arg_20]
0x180546711  xor     ebx, ebx
0x180546713  mov     r15, [rbp+2870h+arg_90]
0x18054671a  mov     r13d, edx
0x18054671d  mov     rsi, [rbp+2870h+arg_98]
0x180546724  mov     rdi, rcx
0x180546727  mov     r14, [rbp+2870h+arg_60]
0x18054672e  xor     edx, edx; Val
0x180546730  mov     [rbp+2870h+var_2848], rax
0x180546734  mov     r12d, ebx
0x180546737  mov     rax, [rbp+2870h+arg_30]
0x18054673e  mov     [rbp+2870h+var_2838], rax
0x180546742  mov     rax, [rbp+2870h+arg_68]
0x180546749  mov     [rbp+2870h+var_2870], rax
0x18054674d  mov     rax, [rbp+2870h+arg_70]
0x180546754  mov     [rbp+2870h+var_2868], rax
0x180546758  mov     rax, [rbp+2870h+arg_78]
0x18054675f  mov     [rbp+2870h+var_2830], rax
0x180546763  mov     rax, [rbp+2870h+arg_80]
0x18054676a  mov     [rbp+2870h+var_2880], rax
0x18054676e  mov     rax, [rbp+2870h+arg_88]
0x180546775  mov     [rbp+2870h+var_2850], r8
0x180546779  mov     r8d, 1108h; Size
0x18054677f  mov     [rbp+2870h+String1], rcx
0x180546783  lea     rcx, [rbp+2870h+var_2780]; void *
0x18054678a  mov     [rbp+2870h+var_2878], rax
0x18054678e  mov     [rbp+2870h+var_2840], r9
0x180546792  mov     [rbp+2870h+var_2890], r15
0x180546796  mov     [rbp+2870h+var_2888], rsi
0x18054679a  mov     [rbp+2870h+UserName], rbx
0x18054679e  mov     [rbp+2870h+var_28A0], rbx
0x1805467a2  mov     [rsp+2970h+lpString1], rbx
0x1805467a7  mov     [rbp+2870h+var_28F0], rbx
0x1805467ab  call    memset_0
0x1805467b0  xor     edx, edx; Val
0x1805467b2  mov     [rsp+2970h+var_2900], ebx
0x1805467b6  lea     r8d, [rbx+50h]; Size
0x1805467ba  mov     dword ptr [rsp+2970h+Size+4], ebx
0x1805467be  lea     rcx, [rbp+2870h+Credential]; void *
0x1805467c2  call    memset_0
0x1805467c7  mov     rcx, rdi; unsigned __int16 *
0x1805467ca  call    ?GetCaptionText@@YAPEAGPEBG@Z; GetCaptionText(ushort const *)
0x1805467cf  mov     rcx, rdi; unsigned __int16 *
0x1805467d2  mov     [rbp+2870h+var_2858], rax
0x1805467d6  call    ?GetMessageText@@YAPEAGPEBG@Z; GetMessageText(ushort const *)
0x1805467db  lea     rcx, [rbp+2870h+var_28A8]
0x1805467df  mov     [rbp+2870h+var_2860], rax
0x1805467e3  mov     [rbp+2870h+var_28A8], rbx
0x1805467e7  call    ?SafeAddRef@?$TCntPtr@VCRailNotify@WindowsRemoteAppLib@@@@AEAAXXZ; TCntPtr<WindowsRemoteAppLib::CRailNotify>::SafeAddRef(void)
0x1805467ec  lea     rcx, [rbp+2870h+var_28C8]
0x1805467f0  mov     [rbp+2870h+var_28E8], ebx
0x1805467f3  mov     [rbp+2870h+var_28C8], rbx
0x1805467f7  call    ?SafeAddRef@?$TCntPtr@VCRailNotify@WindowsRemoteAppLib@@@@AEAAXXZ; TCntPtr<WindowsRemoteAppLib::CRailNotify>::SafeAddRef(void)
0x1805467fc  xor     ecx, ecx
0x1805467fe  mov     [rbp+2870h+Src], rcx
0x180546802  mov     dword ptr [rsp+2970h+Size], ecx
0x180546806  mov     [rbp+2870h+Block], rcx
0x18054680a  test    r15, r15
0x18054680d  jnz     short loc_18054686B
0x18054680f  mov     rax, cs:WPP_GLOBAL_Control
0x180546816  lea     rsi, WPP_GLOBAL_Control
0x18054681d  cmp     rax, rsi
0x180546820  jz      short loc_180546861
0x180546822  mov     r14b, 8
0x180546825  test    [rax+1Ch], r14b
0x180546829  jz      short loc_180546861
0x18054682b  lea     ebx, [rcx+2]
0x18054682e  cmp     [rax+19h], bl
0x180546831  jb      short loc_180546861
0x180546833  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180546838  lea     edx, [rbx+23h]
0x18054683b  lea     rcx, aPpusercreds; "ppUserCreds"
0x180546842  mov     qword ptr [rsp+2970h+domainBufferSize], rcx
0x180546847  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x18054684e  mov     rcx, cs:WPP_GLOBAL_Control
0x180546855  mov     r9d, eax
0x180546858  mov     rcx, [rcx+10h]
0x18054685c  call    WPP_SF_Ds
0x180546861  mov     edi, 80004003h
0x180546866  jmp     loc_180547472
0x18054686b  test    rsi, rsi
0x18054686e  jnz     short loc_1805468A7
0x180546870  mov     rax, cs:WPP_GLOBAL_Control
0x180546877  lea     rsi, WPP_GLOBAL_Control
0x18054687e  cmp     rax, rsi
0x180546881  jz      short loc_180546861
0x180546883  mov     r14b, 8
0x180546886  test    [rax+1Ch], r14b
0x18054688a  jz      short loc_180546861
0x18054688c  mov     ebx, 2
0x180546891  cmp     [rax+19h], bl
0x180546894  jb      short loc_180546861
0x180546896  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18054689b  lea     edx, [rbx+24h]
0x18054689e  lea     rcx, aPauthschemeuse; "pAuthSchemeUsed"
0x1805468a5  jmp     short loc_180546842
0x1805468a7  mov     rax, cs:WPP_GLOBAL_Control
0x1805468ae  lea     rsi, WPP_GLOBAL_Control
0x1805468b5  mov     [rbp+2870h+var_28C0], rcx
0x1805468b9  lea     r15, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x1805468c0  mov     [rbp+2870h+var_28D8], rcx
0x1805468c4  cmp     rax, rsi
0x1805468c7  jz      short loc_1805468FC
0x1805468c9  test    byte ptr [rax+1Ch], 1
0x1805468cd  jz      short loc_1805468FC
0x1805468cf  cmp     byte ptr [rax+19h], 5
0x1805468d3  jb      short loc_1805468FC
0x1805468d5  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805468da  mov     rcx, cs:WPP_GLOBAL_Control
0x1805468e1  mov     edx, 27h ; '''
0x1805468e6  mov     r9d, eax
0x1805468e9  mov     qword ptr [rsp+2970h+domainBufferSize], rdi
0x1805468ee  mov     r8, r15
0x1805468f1  mov     rcx, [rcx+10h]
0x1805468f5  call    WPP_SF_DS
0x1805468fa  xor     ecx, ecx
0x1805468fc  mov     rax, [rbp+2870h+var_2878]
0x180546900  mov     [rax], rcx
0x180546903  mov     rax, [rbp+2870h+var_2870]
0x180546907  mov     [rax], ecx
0x180546909  mov     rax, [rbp+2870h+var_2868]
0x18054690d  mov     [rax], ecx
0x18054690f  mov     rax, [rbp+2870h+var_2890]
0x180546913  mov     [rax], rcx
0x180546916  mov     rax, [rbp+2870h+var_2888]
0x18054691a  mov     dword ptr [rax], 6
0x180546920  mov     rax, [rbp+2870h+var_2880]
0x180546924  mov     [rax], rcx
0x180546927  cmp     [rbp+2870h+arg_38], ecx
0x18054692d  jnz     short loc_180546972
0x18054692f  mov     dword ptr [rsp+2970h+user], ecx
0x180546933  lea     r9, [rsp+2970h+user]
0x180546938  mov     ecx, r13d
0x18054693b  xor     r8d, r8d
0x18054693e  mov     rdx, rdi
0x180546941  call    ?ReadCreds@AACredHelper@@SAJW4_XRdpGatewayAuthSchemes@@PEBGPEAPEAGPEAH@Z; AACredHelper::ReadCreds(_XRdpGatewayAuthSchemes,ushort const *,ushort * *,int *)
0x180546946  xor     eax, eax
0x180546948  cmp     dword ptr [rsp+2970h+user], eax
0x18054694c  jz      short loc_180546972
0x18054694e  cmp     [rbp+2870h+arg_40], eax
0x180546954  jnz     short loc_180546972
0x180546956  mov     [rsp+2970h+user], rax
0x18054695b  mov     edi, eax
0x18054695d  cmp     r13d, 6
0x180546961  mov     eax, 5
0x180546966  cmovnz  eax, r13d
0x18054696a  mov     r13d, eax
0x18054696d  jmp     loc_1805473C0
0x180546972  lea     rcx, [rbp+2870h+var_28A8]; struct CTscCredentialsQueryUi **
0x180546976  call    ?CreateInstance@CTscCredentialsQueryUi@@SAJPEAPEAV1@@Z; CTscCredentialsQueryUi::CreateInstance(CTscCredentialsQueryUi * *)
0x18054697b  mov     edi, eax
0x18054697d  test    eax, eax
0x18054697f  jns     short loc_1805469DF
0x180546981  mov     rax, cs:WPP_GLOBAL_Control
0x180546988  cmp     rax, rsi
0x18054698b  jz      loc_180547427
0x180546991  mov     r14b, 8
0x180546994  test    [rax+1Ch], r14b
0x180546998  jz      loc_180547427
0x18054699e  mov     ebx, 2
0x1805469a3  cmp     [rax+19h], bl
0x1805469a6  jb      loc_180547427
0x1805469ac  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1805469b1  lea     edx, [rbx+26h]
0x1805469b4  mov     dword ptr [rsp+2970h+var_2948], edi
0x1805469b8  lea     rcx, aCtsccredential; "CTscCredentialsQueryUi::CreateInstance "...
0x1805469bf  mov     qword ptr [rsp+2970h+domainBufferSize], rcx
0x1805469c4  mov     r9d, eax
0x1805469c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1805469ce  mov     r8, r15
0x1805469d1  mov     rcx, [rcx+10h]
0x1805469d5  call    WPP_SF_DsD
0x1805469da  jmp     loc_180547427
0x1805469df  mov     ecx, [rbp+2870h+arg_38]
0x1805469e5  mov     ebx, 2
0x1805469ea  test    ecx, ecx
0x1805469ec  jnz     short loc_1805469F7
0x1805469ee  cmp     [rbp+2870h+arg_40], r12d
0x1805469f5  jz      short loc_180546A20
0x1805469f7  cmp     r13d, 4
0x1805469fb  mov     eax, 5
0x180546a00  cmovnz  eax, r13d
0x180546a04  mov     r13d, eax
0x180546a07  cmp     eax, ebx
0x180546a09  jz      short loc_180546A13
0x180546a0b  add     eax, 0FFFFFFFBh
0x180546a0e  cmp     eax, 1
0x180546a11  ja      short loc_180546A20
0x180546a13  test    ecx, ecx
0x180546a15  jz      short loc_180546A20
0x180546a17  mov     rcx, [rbp+2870h+String1]; unsigned __int16 *
0x180546a1b  call    ?CleanUpCreds@AACredHelper@@SAJPEBG@Z; AACredHelper::CleanUpCreds(ushort const *)
0x180546a20  mov     edx, 638h; uBytes
0x180546a25  mov     ecx, 40h ; '@'; uFlags
0x180546a2a  call    cs:__imp_LocalAlloc
0x180546a30  mov     [rbp+2870h+hMem], rax
0x180546a34  test    rax, rax
0x180546a37  jnz     short loc_180546A82
0x180546a39  mov     edi, 8007000Eh
0x180546a3e  mov     rax, cs:WPP_GLOBAL_Control
0x180546a45  cmp     rax, rsi
0x180546a48  jz      loc_180547427
0x180546a4e  mov     r14b, 8
0x180546a51  test    [rax+1Ch], r14b
0x180546a55  jz      loc_180547427
0x180546a5b  cmp     [rax+19h], bl
0x180546a5e  jb      loc_180547427
0x180546a64  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180546a69  mov     edx, 29h ; ')'
0x180546a6e  mov     dword ptr [rsp+2970h+var_2948], 8007000Eh
0x180546a76  lea     rcx, aAllocateMemory_3; "allocate memory for myCredsBuf"
0x180546a7d  jmp     loc_1805469BF
0x180546a82  xor     edx, edx; Val
0x180546a84  mov     dword ptr [rax], 0DEADBEEFh
0x180546a8a  mov     r8d, 404h; Size
0x180546a90  lea     rcx, [rbp+2870h+var_1460]; void *
0x180546a97  call    memset_0
0x180546a9c  test    r14, r14
0x180546a9f  jz      short loc_180546AC2
0x180546aa1  mov     r8, r14; unsigned __int16 *
0x180546aa4  lea     rcx, [rbp+2870h+var_1460]; unsigned __int16 *
0x180546aab  mov     edx, 202h; unsigned __int64
0x180546ab0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180546ab5  test    eax, eax
0x180546ab7  jns     short loc_180546AC2
0x180546ab9  xor     eax, eax
0x180546abb  mov     [rbp+2870h+var_1460], ax
0x180546ac2  mov     rax, [rbp+2870h+hMem]
0x180546ac6  xor     edx, edx; Val
0x180546ac8  add     rax, 8
0x180546acc  mov     r8d, 630h; Size
0x180546ad2  mov     rcx, rax; void *
0x180546ad5  mov     [rsp+2970h+user], rax
0x180546ada  xor     edi, edi
0x180546adc  call    memset_0
0x180546ae1  mov     ecx, r13d
0x180546ae4  mov     r14b, 8
0x180546ae7  sub     ecx, 1
0x180546aea  jz      short loc_180546B3B
0x180546aec  sub     ecx, 1
0x180546aef  jz      short loc_180546B3B
0x180546af1  sub     ecx, 1
0x180546af4  jz      short loc_180546B30
0x180546af6  sub     ecx, ebx
0x180546af8  jz      short loc_180546B3B
0x180546afa  sub     ecx, 1
0x180546afd  jz      short loc_180546B3E
0x180546aff  cmp     ecx, 3
0x180546b02  jz      short loc_180546B3E
0x180546b04  mov     rcx, cs:WPP_GLOBAL_Control
0x180546b0b  cmp     rcx, rsi
0x180546b0e  jz      short loc_180546B3E
0x180546b10  test    [rcx+1Ch], r14b
0x180546b14  jz      short loc_180546B3E
0x180546b16  cmp     byte ptr [rcx+19h], 1
0x180546b1a  jb      short loc_180546B3E
0x180546b1c  mov     rcx, [rcx+10h]
0x180546b20  lea     edx, [rdi+2Ah]
0x180546b23  mov     r9d, r13d
0x180546b26  mov     r8, r15
0x180546b29  call    WPP_SF_d
0x180546b2e  jmp     short loc_180546B3E
0x180546b30  mov     edi, 20h ; ' '
0x180546b35  lea     r12d, [rdi-1Fh]
0x180546b39  jmp     short loc_180546B3E
0x180546b3b  mov     r12d, ebx
0x180546b3e  mov     rax, [rbp+2870h+var_2850]
0x180546b42  lea     rcx, [rbp+2870h+var_2778]; unsigned __int16 *
0x180546b49  mov     r8, [rbp+2870h+var_2858]
0x180546b4d  mov     edx, 80h; unsigned __int64
0x180546b52  mov     [rbp+2870h+var_2780], rax
0x180546b59  mov     rax, [rbp+2870h+var_2848]
0x180546b5d  test    rax, rax
0x180546b60  cmovnz  r8, rax; unsigned __int16 *
0x180546b64  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180546b69  mov     rax, [rbp+2870h+var_2840]
0x180546b6d  mov     edx, 800h; unsigned __int64
0x180546b72  test    rax, rax
0x180546b75  jz      short loc_180546BC6
0x180546b77  mov     rcx, [rbp+2870h+var_2838]
0x180546b7b  mov     r8, rax; unsigned __int16 *
0x180546b7e  test    rcx, rcx
0x180546b81  jz      short loc_180546BA8
0x180546b83  cmp     [rbp+2870h+arg_50], 0
0x180546b8a  jz      short loc_180546B91
  ... truncated ...
```
