# InternalGatherCreds(ushort const *,_XRdpGatewayAuthSchemes,HWND__ *,ushort const *,ushort const *,HBITMAP__ *,ushort const *,int,int,int,int,ushort const *,ushort const *,int *,int *,ushort * *,ushort * *,void * *,_AAUSERCREDS * *,_XRdpGatewayAuthSchemes *,int,int)

- ea: `0x140093644`
- end: `0x1400943e2`
- name: `?InternalGatherCreds@@YAJPEBGW4_XRdpGatewayAuthSchemes@@PEAUHWND__@@00PEAUHBITMAP__@@0HHHH00PEAH4PEAPEAG5PEAPEAXPEAPEAU_AAUSERCREDS@@PEAW41@HH@Z`
- size: `3486`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140092d74`

## callees

- `0x140003b08`
- `0x140004703`
- `0x140008a34`
- `0x140008a78`
- `0x14000b7d8`
- `0x14000c7d0`
- `0x14000c7f8`
- `0x14000cf70`
- `0x14000cffc`
- `0x14000d078`
- `0x14001e210`
- `0x140042394`
- `0x140092e5c`
- `0x1400931b8`
- `0x140093424`
- `0x140093644`
- `0x1400943e8`
- `0x140095e08`
- `0x140096024`
- `0x140096c80`
- `0x1400970b0`
- `0x140113390`
- `0x140113450`
- `0x140114010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x140093921`
- `KERNEL32!LocalAlloc` at `0x140093dc3`
- `KERNEL32!LocalAlloc` at `0x140093e3e`
- `KERNEL32!LocalAlloc` at `0x140093921`
- `KERNEL32!LocalAlloc` at `0x140093dc3`
- `KERNEL32!LocalAlloc` at `0x140093e3e`
- `KERNEL32!LocalFree` at `0x140094285`
- `KERNEL32!LocalFree` at `0x1400942ac`
- `KERNEL32!LocalFree` at `0x1400942ba`
- `KERNEL32!LocalFree` at `0x14009435d`
- `KERNEL32!LocalFree` at `0x14009436c`
- `KERNEL32!LocalFree` at `0x14009437a`
- `KERNEL32!LocalFree` at `0x14009438c`
- `KERNEL32!LocalFree` at `0x14009439e`
- `KERNEL32!LocalFree` at `0x140094285`
- `KERNEL32!LocalFree` at `0x1400942ac`
- `KERNEL32!LocalFree` at `0x1400942ba`
- `KERNEL32!LocalFree` at `0x14009435d`
- `KERNEL32!LocalFree` at `0x14009436c`
- `KERNEL32!LocalFree` at `0x14009437a`
- `KERNEL32!LocalFree` at `0x14009438c`
- `KERNEL32!LocalFree` at `0x14009439e`
- `KERNEL32!lstrcmpiW` at `0x140093d95`
- `KERNEL32!lstrcmpiW` at `0x140093d95`
- `KERNEL32!GetLastError` at `0x14009407e`
- `KERNEL32!GetLastError` at `0x140094109`
- `KERNEL32!GetLastError` at `0x14009407e`
- `KERNEL32!GetLastError` at `0x140094109`
- `credui!CredUIParseUserNameW` at `0x14009417f`
- `credui!CredUIParseUserNameW` at `0x14009417f`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x140094074`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x1400940ff`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x140094074`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x1400940ff`

## string_xrefs

- `0x140094212`: `StringCbCopy`
- `0x1400938f0`: `CTscCredentialsQueryUi::CreateInstance failed!`
- `0x140093faa`: `StringCchCopy`
- `0x140093c73`: `CTscAuthenticationBlob::CreateInstance`
- `0x1400940ca`: `CredWriteDomainCredentials failed`
- `0x140094155`: `CredWriteDomainCredentials for canonical name failed`

## pseudocode

```c
__int64 __fastcall InternalGatherCreds(
        wchar_t *a1,
        unsigned int a2,
        __int64 a3,
        unsigned __int16 *a4,
        const unsigned __int16 *a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        __int64 a12,
        unsigned __int16 *a13,
        _DWORD *a14,
        int *a15,
        unsigned __int16 **a16,
        HLOCAL *a17,
        struct CTscAuthenticationBlob **a18,
        _QWORD *a19,
        unsigned int *a20)
{
  void *v20; // r12
  unsigned __int16 *v23; // r13
  __int64 v24; // r8
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v26; // edx
  const char *v27; // rcx
  signed int v28; // edi
  unsigned int v29; // eax
  unsigned int v30; // eax
  _DWORD *v31; // rax
  _DWORD *v32; // rdi
  unsigned int v33; // eax
  const unsigned __int16 *v34; // r8
  const unsigned __int16 *v35; // r8
  CTscCredentialsQueryUi *v36; // rcx
  const unsigned __int16 *v37; // r8
  int v38; // eax
  int v39; // ecx
  unsigned int v40; // eax
  unsigned __int16 *v41; // r12
  unsigned int v42; // r13d
  BOOL v43; // r12d
  int v44; // eax
  unsigned int v45; // eax
  int v46; // edx
  const char *v47; // rcx
  PVOID *v48; // rax
  unsigned int v49; // eax
  unsigned int v50; // eax
  unsigned int v51; // eax
  __int64 v52; // rdx
  unsigned int v53; // eax
  unsigned __int64 v54; // rdi
  unsigned int v55; // eax
  unsigned int v56; // r12d
  int CanonicalName; // eax
  char v58; // di
  unsigned int v59; // eax
  unsigned int v60; // eax
  int v61; // edx
  const char *v62; // rcx
  WCHAR *v63; // rdi
  signed int LastError; // eax
  signed int v65; // eax
  signed int v66; // eax
  unsigned int v67; // eax
  HLOCAL v68; // rcx
  __int64 v69; // rdx
  _BYTE *v70; // rax
  _BYTE *v71; // rdx
  HLOCAL v72; // rcx
  unsigned __int64 i; // rax
  HLOCAL *v74; // rcx
  struct CTscAuthenticationBlob *v75; // rbx
  __int64 v76; // rcx
  unsigned __int64 v77; // rdx
  unsigned __int16 *j; // rax
  unsigned __int16 *v80; // [rsp+60h] [rbp-A0h]
  unsigned int v81; // [rsp+68h] [rbp-98h]
  unsigned int v82; // [rsp+6Ch] [rbp-94h] BYREF
  LPCWSTR lpString1; // [rsp+70h] [rbp-90h] BYREF
  DWORD v84; // [rsp+78h] [rbp-88h] BYREF
  void *Src; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 v86; // [rsp+88h] [rbp-78h] BYREF
  size_t Size; // [rsp+90h] [rbp-70h] BYREF
  int v88; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR UserName; // [rsp+A0h] [rbp-60h] BYREF
  wchar_t *String1; // [rsp+A8h] [rbp-58h]
  HLOCAL hMem; // [rsp+B0h] [rbp-50h]
  HLOCAL v92; // [rsp+B8h] [rbp-48h]
  struct CTscAuthenticationBlob *v93; // [rsp+C0h] [rbp-40h] BYREF
  void *Block; // [rsp+C8h] [rbp-38h]
  struct CTscCredentialsQueryUi *v95; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v96; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD *v97; // [rsp+E0h] [rbp-20h]
  unsigned int *v98; // [rsp+E8h] [rbp-18h]
  HLOCAL *v99; // [rsp+F0h] [rbp-10h]
  struct CTscAuthenticationBlob **v100; // [rsp+F8h] [rbp-8h]
  _DWORD *v101; // [rsp+100h] [rbp+0h]
  int *v102; // [rsp+108h] [rbp+8h]
  HLOCAL MessageText; // [rsp+110h] [rbp+10h]
  HLOCAL CaptionText; // [rsp+118h] [rbp+18h]
  __int64 v105; // [rsp+120h] [rbp+20h]
  const unsigned __int16 *v106; // [rsp+128h] [rbp+28h]
  unsigned __int16 *v107; // [rsp+130h] [rbp+30h]
  __int64 v108; // [rsp+138h] [rbp+38h]
  unsigned __int16 **v109; // [rsp+140h] [rbp+40h]
  _CREDENTIALW Credential; // [rsp+150h] [rbp+50h] BYREF
  struct _CREDENTIAL_TARGET_INFORMATIONW TargetInfo; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v112; // [rsp+1F0h] [rbp+F0h] BYREF
  unsigned __int16 v113[128]; // [rsp+1F8h] [rbp+F8h] BYREF
  unsigned __int16 v114[2052]; // [rsp+2F8h] [rbp+1F8h] BYREF
  unsigned __int16 v115[264]; // [rsp+1300h] [rbp+1200h] BYREF
  unsigned __int16 v116[520]; // [rsp+1510h] [rbp+1410h] BYREF
  unsigned __int16 v117[2056]; // [rsp+1920h] [rbp+1820h] BYREF

  v20 = 0;
  v23 = 0;
  v106 = a5;
  v108 = a7;
  v101 = a14;
  v102 = a15;
  v109 = a16;
  v99 = a17;
  v105 = a3;
  v81 = a2;
  String1 = a1;
  v100 = a18;
  v107 = a4;
  v97 = a19;
  v98 = a20;
  UserName = 0;
  v96 = 0;
  lpString1 = 0;
  v86 = 0;
  memset_0(&v112, 0, 0x1108u);
  v88 = 0;
  v84 = 0;
  memset_0(&Credential, 0, sizeof(Credential));
  CaptionText = GetCaptionText(a1);
  MessageText = GetMessageText(a1);
  v95 = 0;
  TCntPtr<CTscSettings>::SafeAddRef(&v95);
  v93 = 0;
  TCntPtr<CTscSettings>::SafeAddRef(&v93);
  Src = 0;
  Size = 0;
  Block = 0;
  if ( !a19 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v26 = 37;
    v27 = "ppUserCreds";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v26,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v27);
LABEL_7:
    v28 = -2147467261;
    goto LABEL_192;
  }
  if ( !a20 )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v26 = 38;
    v27 = "pAuthSchemeUsed";
    goto LABEL_6;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    v29 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      39,
      (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
      v29,
      (__int64)a1);
  }
  v82 = 0;
  *v100 = 0;
  *v101 = 0;
  *v102 = 0;
  *v97 = 0;
  *v98 = 6;
  *v99 = 0;
  AACredHelper::ReadCreds(a2, a1, v24, &v82);
  v28 = CTscCredentialsQueryUi::CreateInstance(&v95);
  if ( v28 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v30 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        40,
        (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
        v30,
        (__int64)"CTscCredentialsQueryUi::CreateInstance failed!",
        v28);
    }
    goto LABEL_184;
  }
  v31 = LocalAlloc(0x40u, 0x638u);
  hMem = v31;
  v32 = v31;
  if ( !v31 )
  {
    v28 = -2147024882;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
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
    goto LABEL_184;
  }
  v92 = 0;
  v80 = 0;
  *v31 = -559038737;
  memset_0(v116, 0, 0x404u);
  if ( a13 && StringCchCopyW(v116, 0x202u, a13) < 0 )
    v116[0] = 0;
  v82 = 0;
  memset_0(v32 + 2, 0, 0x630u);
  switch ( a2 )
  {
    case 1u:
    case 2u:
      goto LABEL_42;
    case 3u:
      LODWORD(v20) = 1;
      v82 = 32;
      break;
    case 5u:
LABEL_42:
      LODWORD(v20) = 2;
      break;
    default:
      if ( a2 != 6
        && a2 != 9
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v81);
      }
      break;
  }
  v112 = v105;
  v34 = v106;
  if ( !v106 )
    v34 = (const unsigned __int16 *)CaptionText;
  StringCchCopyW(v113, 0x80u, v34);
  if ( v107 )
  {
    if ( v108 )
      StringCchPrintfW(v117, 0x800u, v107, String1, v108);
    else
      StringCchPrintfW(v117, 0x800u, v107, String1);
    v35 = v117;
  }
  else
  {
    v35 = (const unsigned __int16 *)MessageText;
  }
  StringCchCopyW(v114, 0x800u, v35);
  v38 = CTscCredentialsQueryUi::PromptForCredentials(
          v36,
          (struct tagTSC_CREDENTIALS_UI_INFO *)&v112,
          v37,
          0,
          v116,
          0,
          &v88,
          v82,
          (unsigned int)v20,
          &Src,
          (unsigned int *)&Size);
  v28 = v38;
  if ( v38 )
  {
    if ( v38 > 0 )
      v28 = (unsigned __int16)v38 | 0x80070000;
    if ( v28 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v40 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          43,
          (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
          v40,
          (__int64)"pCredentialsQueryUi->PromptForCredentials",
          v28);
      }
      v41 = 0;
      goto LABEL_171;
    }
  }
  v42 = Size;
  v43 = (unsigned int)Size >= 0x38 && ((*(_DWORD *)Src - 13) & 0xFFFFFFFD) == 0;
  v44 = CTscCredentialsQueryUi::UnpackBlob(
          v39,
          Src,
          Size,
          (unsigned __int16 **)&UserName,
          &v96,
          (unsigned __int16 **)&lpString1,
          &v86,
          (int *)&Size + 1);
  v28 = v44;
  if ( v44 )
  {
    if ( v44 > 0 )
      v28 = (unsigned __int16)v44 | 0x80070000;
    if ( v28 < 0 )
    {
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_72;
      }
      v45 = RdpWppGetCurrentThreadActivityIdPrefix();
      v46 = 44;
      v47 = "pCredentialsQueryUi->UnpackBlob";
      goto LABEL_71;
    }
  }
  v28 = CTscAuthenticationBlob::CreateInstance(Src, v42, &v93);
  if ( v28 >= 0 )
  {
    v48 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      v49 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v49);
      v48 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v81 == 3 )
    {
      if ( !v43 )
      {
        if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 1) != 0 && *((_BYTE *)v48 + 25) >= 2u )
        {
          v50 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v50);
        }
        v28 = -2147001870;
        goto LABEL_72;
      }
LABEL_105:
      v23 = (unsigned __int16 *)lpString1;
      if ( !lstrcmpiW(lpString1, &pszPassword) )
      {
        if ( v43 )
        {
          v28 = -2146435030;
          goto LABEL_170;
        }
        v56 = v81;
LABEL_180:
        v74 = v99;
        v75 = v93;
        *v97 = (char *)hMem + 8;
        *v98 = v56;
        *v74 = v92;
        *v109 = v80;
        if ( v75 )
        {
          v76 = ((unsigned __int64)v75 + 48) & ((unsigned __int128)-(__int128)(unsigned __int64)v75 >> 64);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 8LL))(v76);
          *v100 = v75;
        }
        *v101 = HIDWORD(Size);
        *v102 = v88;
        goto LABEL_183;
      }
      v92 = LocalAlloc(0x40u, 2 * v86);
      if ( !v92 )
      {
        v28 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v53 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            50,
            (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
            v53,
            (__int64)"allocate memory for pCredSharePassword",
            14);
        }
        goto LABEL_170;
      }
      v54 = v96;
      v80 = (unsigned __int16 *)LocalAlloc(0x40u, 2 * v96);
      v41 = v80;
      if ( !v80 )
      {
        v28 = -2147024882;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v55 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            51,
            (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
            v55,
            (__int64)"allocate memory for pCredShareUsername",
            14);
        }
        goto LABEL_171;
      }
      StringCchCopyW((unsigned __int16 *)v92, v86, v23);
      StringCchCopyW(v80, v54, UserName);
      v56 = v81;
      if ( v81 == 2 || v81 == 5 )
      {
        CanonicalName = GetCanonicalName(String1);
        v58 = CanonicalName;
        if ( CanonicalName < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v59 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            52,
            (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
            v59,
            (__int64)"GetCanonicalName failed",
            v58);
        }
        memset_0(&Credential, 0, sizeof(Credential));
        v84 = 3 - (v81 != 3);
        v28 = StringCbCopyW(v115, 0x20Au, String1);
        if ( v28 < 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v60 = RdpWppGetCurrentThreadActivityIdPrefix();
            v61 = 53;
            v62 = "StringCchCopy";
LABEL_130:
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v61,
              (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
              v60,
              (__int64)v62,
              v28);
            goto LABEL_167;
          }
          goto LABEL_167;
        }
        v63 = (WCHAR *)Block;
        Credential.Type = v84;
        Credential.TargetName = v115;
        Credential.Flags = 0;
        Credential.CredentialBlob = (LPBYTE)v23;
        Credential.Persist = 2;
        Credential.Comment = (LPWSTR)Block;
        Credential.CredentialBlobSize = 2 * v86 - 2;
        Credential.UserName = (LPWSTR)UserName;
        memset_0(&TargetInfo, 0, sizeof(TargetInfo));
        TargetInfo.CredTypeCount = 1;
        TargetInfo.TargetName = v115;
        TargetInfo.Flags = 1;
        TargetInfo.CredTypes = &v84;
        TargetInfo.DnsServerName = v115;
        if ( !CredWriteDomainCredentialsW(&TargetInfo, &Credential, 0) )
        {
          LastError = GetLastError();
          v28 = LastError;
          if ( LastError > 0 )
            v28 = (unsigned __int16)LastError | 0x80070000;
          if ( v28 >= 0 )
            v28 = -2147467259;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v60 = RdpWppGetCurrentThreadActivityIdPrefix();
            v61 = 54;
            v62 = "CredWriteDomainCredentials failed";
            goto LABEL_130;
          }
LABEL_167:
          if ( Block )
            operator delete(Block);
          if ( v28 < 0 )
            goto LABEL_170;
          goto LABEL_180;
        }
        if ( v63 )
        {
          TargetInfo.TargetName = v63;
          TargetInfo.DnsServerName = v63;
          Credential.TargetName = v63;
          if ( !CredWriteDomainCredentialsW(&TargetInfo, &Credential, 0) )
          {
            v65 = GetLastError();
            v28 = v65;
            if ( v65 > 0 )
              v28 = (unsigned __int16)v65 | 0x80070000;
            if ( v28 >= 0 )
              v28 = -2147467259;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v60 = RdpWppGetCurrentThreadActivityIdPrefix();
              v61 = 55;
              v62 = "CredWriteDomainCredentials for canonical name failed";
              goto LABEL_130;
            }
            goto LABEL_167;
          }
        }
      }
      v66 = CredUIParseUserNameW(UserName, (WCHAR *)hMem + 4, 0x104u, (WCHAR *)hMem + 526, 0x104u);
      v28 = v66;
      if ( !v66 )
        goto LABEL_158;
      if ( v66 > 0 )
        v28 = (unsigned __int16)v66 | 0x80070000;
      if ( v28 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v60 = RdpWppGetCurrentThreadActivityIdPrefix();
          v61 = 56;
          v62 = "CredUIParseUserName";
          goto LABEL_130;
        }
      }
      else
      {
LABEL_158:
        v28 = StringCbCopyW((unsigned __int16 *)hMem + 265, 0x20Au, v23);
        if ( v28 >= 0 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
          {
            v67 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v67);
          }
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v60 = RdpWppGetCurrentThreadActivityIdPrefix();
          v61 = 57;
          v62 = "StringCbCopy";
          goto LABEL_130;
        }
      }
      goto LABEL_167;
    }
    if ( v81 == 2 )
    {
      if ( !v43 )
        goto LABEL_105;
      if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 1) != 0 && *((_BYTE *)v48 + 25) >= 2u )
      {
        v51 = RdpWppGetCurrentThreadActivityIdPrefix();
        v52 = 48;
LABEL_95:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v52, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids, v51);
      }
    }
    else
    {
      if ( v81 != 1 )
      {
        if ( v81 == 6 )
          v81 = v43 ? 3 : 5;
        goto LABEL_105;
      }
      if ( !v43 )
        goto LABEL_105;
      if ( v48 != &WPP_GLOBAL_Control && (*((_BYTE *)v48 + 28) & 1) != 0 && *((_BYTE *)v48 + 25) >= 2u )
      {
        v51 = RdpWppGetCurrentThreadActivityIdPrefix();
        v52 = 49;
        goto LABEL_95;
      }
    }
    v28 = -2147001871;
    goto LABEL_72;
  }
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
    || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
    || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
  {
    goto LABEL_72;
  }
  v45 = RdpWppGetCurrentThreadActivityIdPrefix();
  v46 = 45;
  v47 = "CTscAuthenticationBlob::CreateInstance";
LABEL_71:
  WPP_SF_DsD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v46,
    (unsigned int)WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids,
    v45,
    (__int64)v47,
    v28);
LABEL_72:
  v23 = (unsigned __int16 *)lpString1;
LABEL_170:
  v41 = v80;
LABEL_171:
  v68 = hMem;
  v69 = 1592;
  v70 = hMem;
  do
  {
    *v70++ = 0;
    --v69;
  }
  while ( v69 );
  LocalFree(v68);
  v71 = v92;
  if ( v92 )
  {
    v72 = v92;
    for ( i = 2 * v86; i; --i )
      *v71++ = 0;
    LocalFree(v72);
  }
  if ( v41 )
    LocalFree(v41);
LABEL_183:
  v20 = Src;
LABEL_184:
  if ( v23 )
  {
    v77 = 2 * v86;
    for ( j = v23; v77; --v77 )
    {
      *(_BYTE *)j = 0;
      j = (unsigned __int16 *)((char *)j + 1);
    }
    LocalFree(v23);
  }
  if ( UserName )
    LocalFree((HLOCAL)UserName);
  if ( v20 )
    LocalFree(v20);
LABEL_192:
  if ( MessageText )
    LocalFree(MessageText);
  if ( CaptionText )
    LocalFree(CaptionText);
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v93);
  TCntPtr<CTSCoreEventSink>::SafeRelease(&v95);
  return (unsigned int)v28;
}

```

## disassembly

```asm
0x140093644  mov     [rsp-8+arg_18], rbx
0x140093649  push    rbp
0x14009364a  push    rsi
0x14009364b  push    rdi
0x14009364c  push    r12
0x14009364e  push    r13
0x140093650  push    r14
0x140093652  push    r15
0x140093654  lea     rbp, [rsp-2840h]
0x14009365c  mov     eax, 2940h
0x140093661  call    _alloca_probe
0x140093666  sub     rsp, rax
0x140093669  mov     rax, cs:__security_cookie
0x140093670  xor     rax, rsp
0x140093673  mov     [rbp+2870h+var_40], rax
0x14009367a  mov     rax, [rbp+2870h+arg_20]
0x140093681  xor     r12d, r12d
0x140093684  mov     r15, [rbp+2870h+arg_90]
0x14009368b  mov     r14d, edx
0x14009368e  mov     rsi, [rbp+2870h+arg_98]
0x140093695  mov     rdi, rcx
0x140093698  mov     rbx, [rbp+2870h+arg_60]
0x14009369f  mov     r13d, r12d
0x1400936a2  mov     [rbp+2870h+var_2848], rax
0x1400936a6  mov     rax, [rbp+2870h+arg_30]
0x1400936ad  mov     [rbp+2870h+var_2838], rax
0x1400936b1  mov     rax, [rbp+2870h+arg_68]
0x1400936b8  mov     [rbp+2870h+var_2870], rax
0x1400936bc  mov     rax, [rbp+2870h+arg_70]
0x1400936c3  mov     [rbp+2870h+var_2868], rax
0x1400936c7  mov     rax, [rbp+2870h+arg_78]
0x1400936ce  mov     [rbp+2870h+var_2830], rax
0x1400936d2  mov     rax, [rbp+2870h+arg_80]
0x1400936d9  mov     [rbp+2870h+var_2880], rax
0x1400936dd  mov     rax, [rbp+2870h+arg_88]
0x1400936e4  mov     [rbp+2870h+var_2850], r8
0x1400936e8  mov     r8d, 1108h; Size
0x1400936ee  mov     [rsp+2970h+var_2908], edx
0x1400936f2  xor     edx, edx; Val
0x1400936f4  mov     [rbp+2870h+String1], rcx
0x1400936f8  lea     rcx, [rbp+2870h+var_2780]; void *
0x1400936ff  mov     [rbp+2870h+var_2878], rax
0x140093703  mov     [rbp+2870h+var_2840], r9
0x140093707  mov     [rbp+2870h+var_2890], r15
0x14009370b  mov     [rbp+2870h+var_2888], rsi
0x14009370f  mov     [rbp+2870h+UserName], r12
0x140093713  mov     [rbp+2870h+var_2898], r12
0x140093717  mov     [rsp+2970h+lpString1], r12
0x14009371c  mov     [rbp+2870h+var_28E8], r12
0x140093720  call    memset_0
0x140093725  xor     edx, edx; Val
0x140093727  mov     [rbp+2870h+var_28D8], r12d
0x14009372b  lea     r8d, [r12+50h]; Size
0x140093730  mov     [rsp+2970h+var_28F8], r12d
0x140093735  lea     rcx, [rbp+2870h+Credential]; void *
0x140093739  call    memset_0
0x14009373e  mov     rcx, rdi; unsigned __int16 *
0x140093741  call    ?GetCaptionText@@YAPEAGPEBG@Z; GetCaptionText(ushort const *)
0x140093746  mov     rcx, rdi; unsigned __int16 *
0x140093749  mov     [rbp+2870h+var_2858], rax
0x14009374d  call    ?GetMessageText@@YAPEAGPEBG@Z; GetMessageText(ushort const *)
0x140093752  lea     rcx, [rbp+2870h+var_28A0]
0x140093756  mov     [rbp+2870h+var_2860], rax
0x14009375a  mov     [rbp+2870h+var_28A0], r12
0x14009375e  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x140093763  lea     rcx, [rbp+2870h+var_28B0]
0x140093767  mov     dword ptr [rbp+2870h+Size+4], r12d
0x14009376b  mov     [rbp+2870h+var_28B0], r12
0x14009376f  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x140093774  xor     ecx, ecx
0x140093776  mov     [rbp+2870h+Src], r12
0x14009377a  mov     dword ptr [rbp+2870h+Size], ecx
0x14009377d  mov     [rbp+2870h+Block], rcx
0x140093781  test    r15, r15
0x140093784  jnz     short loc_1400937E2
0x140093786  mov     rax, cs:WPP_GLOBAL_Control
0x14009378d  lea     rsi, WPP_GLOBAL_Control
0x140093794  cmp     rax, rsi
0x140093797  jz      short loc_1400937D8
0x140093799  mov     r14b, 8
0x14009379c  test    [rax+1Ch], r14b
0x1400937a0  jz      short loc_1400937D8
0x1400937a2  lea     ebx, [rcx+2]
0x1400937a5  cmp     [rax+19h], bl
0x1400937a8  jb      short loc_1400937D8
0x1400937aa  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400937af  lea     edx, [rbx+23h]
0x1400937b2  lea     rcx, aPpusercreds; "ppUserCreds"
0x1400937b9  mov     qword ptr [rsp+2970h+domainBufferSize], rcx
0x1400937be  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x1400937c5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400937cc  mov     r9d, eax
0x1400937cf  mov     rcx, [rcx+10h]
0x1400937d3  call    WPP_SF_Ds
0x1400937d8  mov     edi, 80004003h
0x1400937dd  jmp     loc_140094380
0x1400937e2  test    rsi, rsi
0x1400937e5  jnz     short loc_14009381E
0x1400937e7  mov     rax, cs:WPP_GLOBAL_Control
0x1400937ee  lea     rsi, WPP_GLOBAL_Control
0x1400937f5  cmp     rax, rsi
0x1400937f8  jz      short loc_1400937D8
0x1400937fa  mov     r14b, 8
0x1400937fd  test    [rax+1Ch], r14b
0x140093801  jz      short loc_1400937D8
0x140093803  mov     ebx, 2
0x140093808  cmp     [rax+19h], bl
0x14009380b  jb      short loc_1400937D8
0x14009380d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093812  lea     edx, [rbx+24h]
0x140093815  lea     rcx, aPauthschemeuse; "pAuthSchemeUsed"
0x14009381c  jmp     short loc_1400937B9
0x14009381e  mov     rax, cs:WPP_GLOBAL_Control
0x140093825  lea     rsi, WPP_GLOBAL_Control
0x14009382c  lea     r15, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140093833  cmp     rax, rsi
0x140093836  jz      short loc_14009386B
0x140093838  test    byte ptr [rax+1Ch], 1
0x14009383c  jz      short loc_14009386B
0x14009383e  cmp     byte ptr [rax+19h], 5
0x140093842  jb      short loc_14009386B
0x140093844  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093849  mov     rcx, cs:WPP_GLOBAL_Control
0x140093850  mov     edx, 27h ; '''
0x140093855  mov     r9d, eax
0x140093858  mov     qword ptr [rsp+2970h+domainBufferSize], rdi
0x14009385d  mov     r8, r15
0x140093860  mov     rcx, [rcx+10h]
0x140093864  call    WPP_SF_DS
0x140093869  xor     ecx, ecx
0x14009386b  mov     rax, [rbp+2870h+var_2878]
0x14009386f  lea     r9, [rsp+2970h+var_2904]
0x140093874  mov     [rsp+2970h+var_2904], ecx
0x140093878  mov     rdx, rdi
0x14009387b  mov     [rax], rcx
0x14009387e  mov     rax, [rbp+2870h+var_2870]
0x140093882  mov     [rax], ecx
0x140093884  mov     rax, [rbp+2870h+var_2868]
0x140093888  mov     [rax], ecx
0x14009388a  mov     rax, [rbp+2870h+var_2890]
0x14009388e  mov     [rax], rcx
0x140093891  mov     rax, [rbp+2870h+var_2888]
0x140093895  mov     dword ptr [rax], 6
0x14009389b  mov     rax, [rbp+2870h+var_2880]
0x14009389f  mov     [rax], rcx
0x1400938a2  mov     ecx, r14d
0x1400938a5  call    ?ReadCreds@AACredHelper@@SAJW4_XRdpGatewayAuthSchemes@@PEBGPEAPEAGPEAH@Z; AACredHelper::ReadCreds(_XRdpGatewayAuthSchemes,ushort const *,ushort * *,int *)
0x1400938aa  lea     rcx, [rbp+2870h+var_28A0]; struct CTscCredentialsQueryUi **
0x1400938ae  call    ?CreateInstance@CTscCredentialsQueryUi@@SAJPEAPEAV1@@Z; CTscCredentialsQueryUi::CreateInstance(CTscCredentialsQueryUi * *)
0x1400938b3  mov     edi, eax
0x1400938b5  test    eax, eax
0x1400938b7  jns     short loc_140093917
0x1400938b9  mov     rax, cs:WPP_GLOBAL_Control
0x1400938c0  cmp     rax, rsi
0x1400938c3  jz      loc_140094339
0x1400938c9  mov     r14b, 8
0x1400938cc  test    [rax+1Ch], r14b
0x1400938d0  jz      loc_140094339
0x1400938d6  mov     ebx, 2
0x1400938db  cmp     [rax+19h], bl
0x1400938de  jb      loc_140094339
0x1400938e4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400938e9  lea     edx, [rbx+26h]
0x1400938ec  mov     dword ptr [rsp+2970h+var_2948], edi
0x1400938f0  lea     rcx, aCtsccredential; "CTscCredentialsQueryUi::CreateInstance "...
0x1400938f7  mov     qword ptr [rsp+2970h+domainBufferSize], rcx
0x1400938fc  mov     r9d, eax
0x1400938ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140093906  mov     r8, r15
0x140093909  mov     rcx, [rcx+10h]
0x14009390d  call    WPP_SF_DsD
0x140093912  jmp     loc_140094339
0x140093917  mov     edx, 638h; uBytes
0x14009391c  mov     ecx, 40h ; '@'; uFlags
0x140093921  call    cs:__imp_LocalAlloc
0x140093927  mov     [rbp+2870h+hMem], rax
0x14009392b  mov     rdi, rax
0x14009392e  test    rax, rax
0x140093931  jnz     short loc_14009397F
0x140093933  mov     edi, 8007000Eh
0x140093938  mov     rax, cs:WPP_GLOBAL_Control
0x14009393f  cmp     rax, rsi
0x140093942  jz      loc_140094339
0x140093948  mov     r14b, 8
0x14009394b  test    [rax+1Ch], r14b
0x14009394f  jz      loc_140094339
0x140093955  mov     ebx, 2
0x14009395a  cmp     [rax+19h], bl
0x14009395d  jb      loc_140094339
0x140093963  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140093968  lea     edx, [rbx+27h]
0x14009396b  mov     dword ptr [rsp+2970h+var_2948], 8007000Eh
0x140093973  lea     rcx, aAllocateMemory_3; "allocate memory for myCredsBuf"
0x14009397a  jmp     loc_1400938F7
0x14009397f  xor     edx, edx; Val
0x140093981  mov     [rbp+2870h+var_28B8], r12
0x140093985  mov     r8d, 404h; Size
0x14009398b  mov     [rsp+2970h+var_2910], r12
0x140093990  lea     rcx, [rbp+2870h+var_1460]; void *
0x140093997  mov     dword ptr [rax], 0DEADBEEFh
0x14009399d  call    memset_0
0x1400939a2  test    rbx, rbx
0x1400939a5  jz      short loc_1400939C7
0x1400939a7  mov     r8, rbx; unsigned __int16 *
0x1400939aa  lea     rcx, [rbp+2870h+var_1460]; unsigned __int16 *
0x1400939b1  mov     edx, 202h; unsigned __int64
0x1400939b6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1400939bb  test    eax, eax
0x1400939bd  jns     short loc_1400939C7
0x1400939bf  mov     [rbp+2870h+var_1460], r12w
0x1400939c7  lea     rcx, [rdi+8]; void *
0x1400939cb  mov     [rsp+2970h+var_2904], r12d
0x1400939d0  xor     edx, edx; Val
0x1400939d2  mov     r8d, 630h; Size
0x1400939d8  call    memset_0
0x1400939dd  mov     ecx, r14d
0x1400939e0  mov     ebx, 2
0x1400939e5  mov     r14b, 8
0x1400939e8  sub     ecx, 1
0x1400939eb  jz      short loc_140093A43
0x1400939ed  sub     ecx, 1
0x1400939f0  jz      short loc_140093A43
0x1400939f2  sub     ecx, 1
0x1400939f5  jz      short loc_140093A33
0x1400939f7  sub     ecx, ebx
0x1400939f9  jz      short loc_140093A43
0x1400939fb  sub     ecx, 1
0x1400939fe  jz      short loc_140093A46
0x140093a00  cmp     ecx, 3
0x140093a03  jz      short loc_140093A46
0x140093a05  mov     rcx, cs:WPP_GLOBAL_Control
0x140093a0c  cmp     rcx, rsi
0x140093a0f  jz      short loc_140093A46
0x140093a11  test    [rcx+1Ch], r14b
0x140093a15  jz      short loc_140093A46
0x140093a17  cmp     byte ptr [rcx+19h], 1
0x140093a1b  jb      short loc_140093A46
0x140093a1d  mov     r9d, [rsp+2970h+var_2908]
0x140093a22  lea     edx, [rbx+28h]
0x140093a25  mov     rcx, [rcx+10h]
0x140093a29  mov     r8, r15
0x140093a2c  call    WPP_SF_d
0x140093a31  jmp     short loc_140093A46
0x140093a33  mov     r12d, 1
0x140093a39  mov     [rsp+2970h+var_2904], 20h ; ' '
0x140093a41  jmp     short loc_140093A46
0x140093a43  mov     r12d, ebx
0x140093a46  mov     rax, [rbp+2870h+var_2850]
0x140093a4a  lea     rcx, [rbp+2870h+var_2778]; unsigned __int16 *
0x140093a51  mov     [rbp+2870h+var_2780], rax
0x140093a58  mov     edx, 80h; unsigned __int64
0x140093a5d  mov     rax, [rbp+2870h+var_2848]
0x140093a61  mov     r8, rax
0x140093a64  test    rax, rax
0x140093a67  jnz     short loc_140093A6D
0x140093a69  mov     r8, [rbp+2870h+var_2858]; unsigned __int16 *
0x140093a6d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140093a72  mov     rax, [rbp+2870h+var_2840]
0x140093a76  test    rax, rax
0x140093a79  jz      short loc_140093ABD
0x140093a7b  mov     rcx, [rbp+2870h+var_2838]
0x140093a7f  mov     edi, 800h
0x140093a84  mov     r9, [rbp+2870h+String1]
0x140093a88  mov     r8, rax; unsigned __int16 *
0x140093a8b  mov     edx, edi; unsigned __int64
0x140093a8d  test    rcx, rcx
0x140093a90  jz      short loc_140093AA5
0x140093a92  mov     qword ptr [rsp+2970h+domainBufferSize], rcx
0x140093a97  lea     rcx, [rbp+2870h+var_1050]; unsigned __int16 *
0x140093a9e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140093aa3  jmp     short loc_140093AB1
0x140093aa5  lea     rcx, [rbp+2870h+var_1050]; unsigned __int16 *
0x140093aac  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140093ab1  lea     r8, [rbp+2870h+var_1050]
0x140093ab8  mov     rdx, rdi
0x140093abb  jmp     short loc_140093AC6
0x140093abd  mov     r8, [rbp+2870h+var_2860]; unsigned __int16 *
0x140093ac1  mov     edx, 800h; unsigned __int64
0x140093ac6  lea     rcx, [rbp+2870h+var_2678]; unsigned __int16 *
0x140093acd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140093ad2  lea     rax, [rbp+2870h+Size]
0x140093ad6  xor     r9d, r9d; unsigned int
0x140093ad9  mov     [rsp+2970h+var_2920], rax; unsigned int *
0x140093ade  lea     rdx, [rbp+2870h+var_2780]; struct tagTSC_CREDENTIALS_UI_INFO *
0x140093ae5  lea     rax, [rbp+2870h+Src]
0x140093ae9  mov     [rsp+2970h+var_2928], rax; void **
0x140093aee  mov     eax, [rsp+2970h+var_2904]
0x140093af2  mov     [rsp+2970h+var_2930], r12d; unsigned int
0x140093af7  mov     dword ptr [rsp+2970h+var_2938], eax; unsigned int
0x140093afb  lea     rax, [rbp+2870h+var_28D8]
0x140093aff  mov     [rsp+2970h+var_2940], rax; int *
0x140093b04  lea     rax, [rbp+2870h+var_1460]
0x140093b0b  mov     [rsp+2970h+var_2948], r13; unsigned __int16 *
0x140093b10  mov     qword ptr [rsp+2970h+domainBufferSize], rax; unsigned __int16 *
0x140093b15  call    ?PromptForCredentials@CTscCredentialsQueryUi@@QEAAKPEAUtagTSC_CREDENTIALS_UI_INFO@@PEBGKPEAG1PEAHKKPEAPEAXPEAK@Z; CTscCredentialsQueryUi::PromptForCredentials(tagTSC_CREDENTIALS_UI_INFO *,ushort const *,ulong,ushort *,ushort const *,int *,ulong,ulong,void * *,ulong *)
0x140093b1a  mov     edi, eax
0x140093b1c  test    eax, eax
0x140093b1e  jz      short loc_140093B7E
0x140093b20  jle     short loc_140093B2B
0x140093b22  movzx   edi, ax
  ... truncated ...
```
