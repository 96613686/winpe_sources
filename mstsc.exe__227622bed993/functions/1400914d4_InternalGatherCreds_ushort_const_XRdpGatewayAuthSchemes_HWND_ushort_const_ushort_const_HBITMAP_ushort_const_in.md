# InternalGatherCreds(ushort const *,_XRdpGatewayAuthSchemes,HWND__ *,ushort const *,ushort const *,HBITMAP__ *,ushort const *,int,int,int,int,ushort const *,ushort const *,int *,int *,ushort * *,ushort * *,void * *,_AAUSERCREDS * *,_XRdpGatewayAuthSchemes *,int,int)

- ea: `0x1400914d4`
- end: `0x140092272`
- name: `?InternalGatherCreds@@YAJPEBGW4_XRdpGatewayAuthSchemes@@PEAUHWND__@@00PEAUHBITMAP__@@0HHHH00PEAH4PEAPEAG5PEAPEAXPEAPEAU_AAUSERCREDS@@PEAW41@HH@Z`
- size: `3486`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x140090c04`

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
- `0x1400403d0`
- `0x140090cec`
- `0x140091048`
- `0x1400912b4`
- `0x1400914d4`
- `0x140092278`
- `0x140093c98`
- `0x140093eb4`
- `0x140094b10`
- `0x140094f40`
- `0x140111220`
- `0x1401112e0`
- `0x140112010`

## import_xrefs

- `KERNEL32!LocalAlloc` at `0x1400917b1`
- `KERNEL32!LocalAlloc` at `0x140091c53`
- `KERNEL32!LocalAlloc` at `0x140091cce`
- `KERNEL32!LocalAlloc` at `0x1400917b1`
- `KERNEL32!LocalAlloc` at `0x140091c53`
- `KERNEL32!LocalAlloc` at `0x140091cce`
- `KERNEL32!LocalFree` at `0x140092115`
- `KERNEL32!LocalFree` at `0x14009213c`
- `KERNEL32!LocalFree` at `0x14009214a`
- `KERNEL32!LocalFree` at `0x1400921ed`
- `KERNEL32!LocalFree` at `0x1400921fc`
- `KERNEL32!LocalFree` at `0x14009220a`
- `KERNEL32!LocalFree` at `0x14009221c`
- `KERNEL32!LocalFree` at `0x14009222e`
- `KERNEL32!LocalFree` at `0x140092115`
- `KERNEL32!LocalFree` at `0x14009213c`
- `KERNEL32!LocalFree` at `0x14009214a`
- `KERNEL32!LocalFree` at `0x1400921ed`
- `KERNEL32!LocalFree` at `0x1400921fc`
- `KERNEL32!LocalFree` at `0x14009220a`
- `KERNEL32!LocalFree` at `0x14009221c`
- `KERNEL32!LocalFree` at `0x14009222e`
- `KERNEL32!lstrcmpiW` at `0x140091c25`
- `KERNEL32!lstrcmpiW` at `0x140091c25`
- `KERNEL32!GetLastError` at `0x140091f0e`
- `KERNEL32!GetLastError` at `0x140091f99`
- `KERNEL32!GetLastError` at `0x140091f0e`
- `KERNEL32!GetLastError` at `0x140091f99`
- `credui!CredUIParseUserNameW` at `0x14009200f`
- `credui!CredUIParseUserNameW` at `0x14009200f`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x140091f04`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x140091f8f`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x140091f04`
- `ADVAPI32!CredWriteDomainCredentialsW` at `0x140091f8f`

## string_xrefs

- `0x140091780`: `CTscCredentialsQueryUi::CreateInstance failed!`
- `0x1400920a2`: `StringCbCopy`
- `0x140091e3a`: `StringCchCopy`
- `0x140091b03`: `CTscAuthenticationBlob::CreateInstance`
- `0x140091f5a`: `CredWriteDomainCredentials failed`
- `0x140091fe5`: `CredWriteDomainCredentials for canonical name failed`

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
0x1400914d4  mov     [rsp-8+arg_18], rbx
0x1400914d9  push    rbp
0x1400914da  push    rsi
0x1400914db  push    rdi
0x1400914dc  push    r12
0x1400914de  push    r13
0x1400914e0  push    r14
0x1400914e2  push    r15
0x1400914e4  lea     rbp, [rsp-2840h]
0x1400914ec  mov     eax, 2940h
0x1400914f1  call    _alloca_probe
0x1400914f6  sub     rsp, rax
0x1400914f9  mov     rax, cs:__security_cookie
0x140091500  xor     rax, rsp
0x140091503  mov     [rbp+2870h+var_40], rax
0x14009150a  mov     rax, [rbp+2870h+arg_20]
0x140091511  xor     r12d, r12d
0x140091514  mov     r15, [rbp+2870h+arg_90]
0x14009151b  mov     r14d, edx
0x14009151e  mov     rsi, [rbp+2870h+arg_98]
0x140091525  mov     rdi, rcx
0x140091528  mov     rbx, [rbp+2870h+arg_60]
0x14009152f  mov     r13d, r12d
0x140091532  mov     [rbp+2870h+var_2848], rax
0x140091536  mov     rax, [rbp+2870h+arg_30]
0x14009153d  mov     [rbp+2870h+var_2838], rax
0x140091541  mov     rax, [rbp+2870h+arg_68]
0x140091548  mov     [rbp+2870h+var_2870], rax
0x14009154c  mov     rax, [rbp+2870h+arg_70]
0x140091553  mov     [rbp+2870h+var_2868], rax
0x140091557  mov     rax, [rbp+2870h+arg_78]
0x14009155e  mov     [rbp+2870h+var_2830], rax
0x140091562  mov     rax, [rbp+2870h+arg_80]
0x140091569  mov     [rbp+2870h+var_2880], rax
0x14009156d  mov     rax, [rbp+2870h+arg_88]
0x140091574  mov     [rbp+2870h+var_2850], r8
0x140091578  mov     r8d, 1108h; Size
0x14009157e  mov     [rsp+2970h+var_2908], edx
0x140091582  xor     edx, edx; Val
0x140091584  mov     [rbp+2870h+String1], rcx
0x140091588  lea     rcx, [rbp+2870h+var_2780]; void *
0x14009158f  mov     [rbp+2870h+var_2878], rax
0x140091593  mov     [rbp+2870h+var_2840], r9
0x140091597  mov     [rbp+2870h+var_2890], r15
0x14009159b  mov     [rbp+2870h+var_2888], rsi
0x14009159f  mov     [rbp+2870h+UserName], r12
0x1400915a3  mov     [rbp+2870h+var_2898], r12
0x1400915a7  mov     [rsp+2970h+lpString1], r12
0x1400915ac  mov     [rbp+2870h+var_28E8], r12
0x1400915b0  call    memset_0
0x1400915b5  xor     edx, edx; Val
0x1400915b7  mov     [rbp+2870h+var_28D8], r12d
0x1400915bb  lea     r8d, [r12+50h]; Size
0x1400915c0  mov     [rsp+2970h+var_28F8], r12d
0x1400915c5  lea     rcx, [rbp+2870h+Credential]; void *
0x1400915c9  call    memset_0
0x1400915ce  mov     rcx, rdi; unsigned __int16 *
0x1400915d1  call    ?GetCaptionText@@YAPEAGPEBG@Z; GetCaptionText(ushort const *)
0x1400915d6  mov     rcx, rdi; unsigned __int16 *
0x1400915d9  mov     [rbp+2870h+var_2858], rax
0x1400915dd  call    ?GetMessageText@@YAPEAGPEBG@Z; GetMessageText(ushort const *)
0x1400915e2  lea     rcx, [rbp+2870h+var_28A0]
0x1400915e6  mov     [rbp+2870h+var_2860], rax
0x1400915ea  mov     [rbp+2870h+var_28A0], r12
0x1400915ee  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x1400915f3  lea     rcx, [rbp+2870h+var_28B0]
0x1400915f7  mov     dword ptr [rbp+2870h+Size+4], r12d
0x1400915fb  mov     [rbp+2870h+var_28B0], r12
0x1400915ff  call    ?SafeAddRef@?$TCntPtr@VCTscSettings@@@@AEAAXXZ; TCntPtr<CTscSettings>::SafeAddRef(void)
0x140091604  xor     ecx, ecx
0x140091606  mov     [rbp+2870h+Src], r12
0x14009160a  mov     dword ptr [rbp+2870h+Size], ecx
0x14009160d  mov     [rbp+2870h+Block], rcx
0x140091611  test    r15, r15
0x140091614  jnz     short loc_140091672
0x140091616  mov     rax, cs:WPP_GLOBAL_Control
0x14009161d  lea     rsi, WPP_GLOBAL_Control
0x140091624  cmp     rax, rsi
0x140091627  jz      short loc_140091668
0x140091629  mov     r14b, 8
0x14009162c  test    [rax+1Ch], r14b
0x140091630  jz      short loc_140091668
0x140091632  lea     ebx, [rcx+2]
0x140091635  cmp     [rax+19h], bl
0x140091638  jb      short loc_140091668
0x14009163a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x14009163f  lea     edx, [rbx+23h]
0x140091642  lea     rcx, aPpusercreds; "ppUserCreds"
0x140091649  mov     qword ptr [rsp+2970h+domainBufferSize], rcx
0x14009164e  lea     r8, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x140091655  mov     rcx, cs:WPP_GLOBAL_Control
0x14009165c  mov     r9d, eax
0x14009165f  mov     rcx, [rcx+10h]
0x140091663  call    WPP_SF_Ds
0x140091668  mov     edi, 80004003h
0x14009166d  jmp     loc_140092210
0x140091672  test    rsi, rsi
0x140091675  jnz     short loc_1400916AE
0x140091677  mov     rax, cs:WPP_GLOBAL_Control
0x14009167e  lea     rsi, WPP_GLOBAL_Control
0x140091685  cmp     rax, rsi
0x140091688  jz      short loc_140091668
0x14009168a  mov     r14b, 8
0x14009168d  test    [rax+1Ch], r14b
0x140091691  jz      short loc_140091668
0x140091693  mov     ebx, 2
0x140091698  cmp     [rax+19h], bl
0x14009169b  jb      short loc_140091668
0x14009169d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400916a2  lea     edx, [rbx+24h]
0x1400916a5  lea     rcx, aPauthschemeuse; "pAuthSchemeUsed"
0x1400916ac  jmp     short loc_140091649
0x1400916ae  mov     rax, cs:WPP_GLOBAL_Control
0x1400916b5  lea     rsi, WPP_GLOBAL_Control
0x1400916bc  lea     r15, WPP_b9af9f5e65e23e14c1126ae7f524cc69_Traceguids
0x1400916c3  cmp     rax, rsi
0x1400916c6  jz      short loc_1400916FB
0x1400916c8  test    byte ptr [rax+1Ch], 1
0x1400916cc  jz      short loc_1400916FB
0x1400916ce  cmp     byte ptr [rax+19h], 5
0x1400916d2  jb      short loc_1400916FB
0x1400916d4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400916d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400916e0  mov     edx, 27h ; '''
0x1400916e5  mov     r9d, eax
0x1400916e8  mov     qword ptr [rsp+2970h+domainBufferSize], rdi
0x1400916ed  mov     r8, r15
0x1400916f0  mov     rcx, [rcx+10h]
0x1400916f4  call    WPP_SF_DS
0x1400916f9  xor     ecx, ecx
0x1400916fb  mov     rax, [rbp+2870h+var_2878]
0x1400916ff  lea     r9, [rsp+2970h+var_2904]
0x140091704  mov     [rsp+2970h+var_2904], ecx
0x140091708  mov     rdx, rdi
0x14009170b  mov     [rax], rcx
0x14009170e  mov     rax, [rbp+2870h+var_2870]
0x140091712  mov     [rax], ecx
0x140091714  mov     rax, [rbp+2870h+var_2868]
0x140091718  mov     [rax], ecx
0x14009171a  mov     rax, [rbp+2870h+var_2890]
0x14009171e  mov     [rax], rcx
0x140091721  mov     rax, [rbp+2870h+var_2888]
0x140091725  mov     dword ptr [rax], 6
0x14009172b  mov     rax, [rbp+2870h+var_2880]
0x14009172f  mov     [rax], rcx
0x140091732  mov     ecx, r14d
0x140091735  call    ?ReadCreds@AACredHelper@@SAJW4_XRdpGatewayAuthSchemes@@PEBGPEAPEAGPEAH@Z; AACredHelper::ReadCreds(_XRdpGatewayAuthSchemes,ushort const *,ushort * *,int *)
0x14009173a  lea     rcx, [rbp+2870h+var_28A0]; struct CTscCredentialsQueryUi **
0x14009173e  call    ?CreateInstance@CTscCredentialsQueryUi@@SAJPEAPEAV1@@Z; CTscCredentialsQueryUi::CreateInstance(CTscCredentialsQueryUi * *)
0x140091743  mov     edi, eax
0x140091745  test    eax, eax
0x140091747  jns     short loc_1400917A7
0x140091749  mov     rax, cs:WPP_GLOBAL_Control
0x140091750  cmp     rax, rsi
0x140091753  jz      loc_1400921C9
0x140091759  mov     r14b, 8
0x14009175c  test    [rax+1Ch], r14b
0x140091760  jz      loc_1400921C9
0x140091766  mov     ebx, 2
0x14009176b  cmp     [rax+19h], bl
0x14009176e  jb      loc_1400921C9
0x140091774  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x140091779  lea     edx, [rbx+26h]
0x14009177c  mov     dword ptr [rsp+2970h+var_2948], edi
0x140091780  lea     rcx, aCtsccredential; "CTscCredentialsQueryUi::CreateInstance "...
0x140091787  mov     qword ptr [rsp+2970h+domainBufferSize], rcx
0x14009178c  mov     r9d, eax
0x14009178f  mov     rcx, cs:WPP_GLOBAL_Control
0x140091796  mov     r8, r15
0x140091799  mov     rcx, [rcx+10h]
0x14009179d  call    WPP_SF_DsD
0x1400917a2  jmp     loc_1400921C9
0x1400917a7  mov     edx, 638h; uBytes
0x1400917ac  mov     ecx, 40h ; '@'; uFlags
0x1400917b1  call    cs:__imp_LocalAlloc
0x1400917b7  mov     [rbp+2870h+hMem], rax
0x1400917bb  mov     rdi, rax
0x1400917be  test    rax, rax
0x1400917c1  jnz     short loc_14009180F
0x1400917c3  mov     edi, 8007000Eh
0x1400917c8  mov     rax, cs:WPP_GLOBAL_Control
0x1400917cf  cmp     rax, rsi
0x1400917d2  jz      loc_1400921C9
0x1400917d8  mov     r14b, 8
0x1400917db  test    [rax+1Ch], r14b
0x1400917df  jz      loc_1400921C9
0x1400917e5  mov     ebx, 2
0x1400917ea  cmp     [rax+19h], bl
0x1400917ed  jb      loc_1400921C9
0x1400917f3  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1400917f8  lea     edx, [rbx+27h]
0x1400917fb  mov     dword ptr [rsp+2970h+var_2948], 8007000Eh
0x140091803  lea     rcx, aAllocateMemory_3; "allocate memory for myCredsBuf"
0x14009180a  jmp     loc_140091787
0x14009180f  xor     edx, edx; Val
0x140091811  mov     [rbp+2870h+var_28B8], r12
0x140091815  mov     r8d, 404h; Size
0x14009181b  mov     [rsp+2970h+var_2910], r12
0x140091820  lea     rcx, [rbp+2870h+var_1460]; void *
0x140091827  mov     dword ptr [rax], 0DEADBEEFh
0x14009182d  call    memset_0
0x140091832  test    rbx, rbx
0x140091835  jz      short loc_140091857
0x140091837  mov     r8, rbx; unsigned __int16 *
0x14009183a  lea     rcx, [rbp+2870h+var_1460]; unsigned __int16 *
0x140091841  mov     edx, 202h; unsigned __int64
0x140091846  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14009184b  test    eax, eax
0x14009184d  jns     short loc_140091857
0x14009184f  mov     [rbp+2870h+var_1460], r12w
0x140091857  lea     rcx, [rdi+8]; void *
0x14009185b  mov     [rsp+2970h+var_2904], r12d
0x140091860  xor     edx, edx; Val
0x140091862  mov     r8d, 630h; Size
0x140091868  call    memset_0
0x14009186d  mov     ecx, r14d
0x140091870  mov     ebx, 2
0x140091875  mov     r14b, 8
0x140091878  sub     ecx, 1
0x14009187b  jz      short loc_1400918D3
0x14009187d  sub     ecx, 1
0x140091880  jz      short loc_1400918D3
0x140091882  sub     ecx, 1
0x140091885  jz      short loc_1400918C3
0x140091887  sub     ecx, ebx
0x140091889  jz      short loc_1400918D3
0x14009188b  sub     ecx, 1
0x14009188e  jz      short loc_1400918D6
0x140091890  cmp     ecx, 3
0x140091893  jz      short loc_1400918D6
0x140091895  mov     rcx, cs:WPP_GLOBAL_Control
0x14009189c  cmp     rcx, rsi
0x14009189f  jz      short loc_1400918D6
0x1400918a1  test    [rcx+1Ch], r14b
0x1400918a5  jz      short loc_1400918D6
0x1400918a7  cmp     byte ptr [rcx+19h], 1
0x1400918ab  jb      short loc_1400918D6
0x1400918ad  mov     r9d, [rsp+2970h+var_2908]
0x1400918b2  lea     edx, [rbx+28h]
0x1400918b5  mov     rcx, [rcx+10h]
0x1400918b9  mov     r8, r15
0x1400918bc  call    WPP_SF_d
0x1400918c1  jmp     short loc_1400918D6
0x1400918c3  mov     r12d, 1
0x1400918c9  mov     [rsp+2970h+var_2904], 20h ; ' '
0x1400918d1  jmp     short loc_1400918D6
0x1400918d3  mov     r12d, ebx
0x1400918d6  mov     rax, [rbp+2870h+var_2850]
0x1400918da  lea     rcx, [rbp+2870h+var_2778]; unsigned __int16 *
0x1400918e1  mov     [rbp+2870h+var_2780], rax
0x1400918e8  mov     edx, 80h; unsigned __int64
0x1400918ed  mov     rax, [rbp+2870h+var_2848]
0x1400918f1  mov     r8, rax
0x1400918f4  test    rax, rax
0x1400918f7  jnz     short loc_1400918FD
0x1400918f9  mov     r8, [rbp+2870h+var_2858]; unsigned __int16 *
0x1400918fd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140091902  mov     rax, [rbp+2870h+var_2840]
0x140091906  test    rax, rax
0x140091909  jz      short loc_14009194D
0x14009190b  mov     rcx, [rbp+2870h+var_2838]
0x14009190f  mov     edi, 800h
0x140091914  mov     r9, [rbp+2870h+String1]
0x140091918  mov     r8, rax; unsigned __int16 *
0x14009191b  mov     edx, edi; unsigned __int64
0x14009191d  test    rcx, rcx
0x140091920  jz      short loc_140091935
0x140091922  mov     qword ptr [rsp+2970h+domainBufferSize], rcx
0x140091927  lea     rcx, [rbp+2870h+var_1050]; unsigned __int16 *
0x14009192e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140091933  jmp     short loc_140091941
0x140091935  lea     rcx, [rbp+2870h+var_1050]; unsigned __int16 *
0x14009193c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140091941  lea     r8, [rbp+2870h+var_1050]
0x140091948  mov     rdx, rdi
0x14009194b  jmp     short loc_140091956
0x14009194d  mov     r8, [rbp+2870h+var_2860]; unsigned __int16 *
0x140091951  mov     edx, 800h; unsigned __int64
0x140091956  lea     rcx, [rbp+2870h+var_2678]; unsigned __int16 *
0x14009195d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140091962  lea     rax, [rbp+2870h+Size]
0x140091966  xor     r9d, r9d; unsigned int
0x140091969  mov     [rsp+2970h+var_2920], rax; unsigned int *
0x14009196e  lea     rdx, [rbp+2870h+var_2780]; struct tagTSC_CREDENTIALS_UI_INFO *
0x140091975  lea     rax, [rbp+2870h+Src]
0x140091979  mov     [rsp+2970h+var_2928], rax; void **
0x14009197e  mov     eax, [rsp+2970h+var_2904]
0x140091982  mov     [rsp+2970h+var_2930], r12d; unsigned int
0x140091987  mov     dword ptr [rsp+2970h+var_2938], eax; unsigned int
0x14009198b  lea     rax, [rbp+2870h+var_28D8]
0x14009198f  mov     [rsp+2970h+var_2940], rax; int *
0x140091994  lea     rax, [rbp+2870h+var_1460]
0x14009199b  mov     [rsp+2970h+var_2948], r13; unsigned __int16 *
0x1400919a0  mov     qword ptr [rsp+2970h+domainBufferSize], rax; unsigned __int16 *
0x1400919a5  call    ?PromptForCredentials@CTscCredentialsQueryUi@@QEAAKPEAUtagTSC_CREDENTIALS_UI_INFO@@PEBGKPEAG1PEAHKKPEAPEAXPEAK@Z; CTscCredentialsQueryUi::PromptForCredentials(tagTSC_CREDENTIALS_UI_INFO *,ushort const *,ulong,ushort *,ushort const *,int *,ulong,ulong,void * *,ulong *)
0x1400919aa  mov     edi, eax
0x1400919ac  test    eax, eax
0x1400919ae  jz      short loc_140091A0E
0x1400919b0  jle     short loc_1400919BB
0x1400919b2  movzx   edi, ax
  ... truncated ...
```
