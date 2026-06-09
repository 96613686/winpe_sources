# DRMCreateIssuanceLicense

- ea: `0x180004970`
- end: `0x180004eb0`
- name: `DRMCreateIssuanceLicense`
- size: `1344`
- prototype: `HRESULT __stdcall(SYSTEMTIME *pstTimeFrom, SYSTEMTIME *pstTimeUntil, PWSTR wszReferralInfoName, PWSTR wszReferralInfoURL, DRMPUBHANDLE hOwner, PWSTR wszIssuanceLicense, DRMHANDLE hBoundLicense, DRMPUBHANDLE *phIssuanceLicense)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180059780`
- `0x18005a144`

## callees

- `0x180001244`
- `0x180001284`
- `0x18000420c`
- `0x180004328`
- `0x180004590`
- `0x180004610`
- `0x1800046c8`
- `0x180004970`
- `0x180007fc4`
- `0x1800098e8`
- `0x180012524`
- `0x180013d80`
- `0x18001513c`
- `0x18001ef6c`
- `0x18001fe60`
- `0x18001ffd8`
- `0x18003b3b8`
- `0x18004d920`
- `0x18004dd00`
- `0x18004e4e0`
- `0x18005bd72`
- `0x18005f010`

## import_xrefs

- `msvcrt!wcsstr` at `0x180004af2`
- `msvcrt!wcsstr` at `0x180004d77`
- `msvcrt!wcsstr` at `0x180004d8c`
- `msvcrt!wcsstr` at `0x180004af2`
- `msvcrt!wcsstr` at `0x180004d77`
- `msvcrt!wcsstr` at `0x180004d8c`

## string_xrefs

- `0x1800049a0`: `[msdrm]:+DRMCreateIssuanceLicense`
- `0x180004ac9`: `([msdrm]:Referral Info Name=%ls, Referral Info URL=%ls, Rights Template=%ls)\n`
- `0x180004b97`: `[msdrm]:DRMCreateEnablingBitsDecryptor FAILED for VIEWRIGHTSDATA : %x`
- `0x180004bc9`: `[msdrm]:DRMCreateEnablingBitsDecryptor FAILED for EDITRIGHTSDATA: %x`
- `0x180004d51`: `[msdrm]:ParseIssuanceLicenseTemplate FAILED : %x`
- `0x180004d6d`: `Microsoft Rights Template`
- `0x180004d82`: `Microsoft Official Rights Template`
- `0x180004dd3`: `[msdrm]:EscapeXML FAILED : %x`
- `0x180004e56`: `[msdrm]:CreateHandle FAILED : %x`
- `0x180004e74`: `[msdrm]:CreateEvents FAILED : %x`
- `0x180004c76`: `[msdrm]:-DRMCreateIssuanceLicense HR=%x\n`

## pseudocode

```c
HRESULT __stdcall DRMCreateIssuanceLicense(
        SYSTEMTIME *pstTimeFrom,
        SYSTEMTIME *pstTimeUntil,
        PWSTR wszReferralInfoName,
        PWSTR wszReferralInfoURL,
        DRMPUBHANDLE hOwner,
        PWSTR wszIssuanceLicense,
        DRMHANDLE hBoundLicense,
        DRMPUBHANDLE *phIssuanceLicense)
{
  wchar_t *v9; // r12
  SYSTEMTIME *v11; // r13
  __int64 v12; // r9
  DRMHANDLE *v13; // rdi
  DRMHANDLE v14; // r15d
  wchar_t *v15; // rsi
  HRESULT SPHandle; // ebx
  int UserPointer; // eax
  const char *v18; // rcx
  CIssuanceLicense *v19; // rax
  __int64 v20; // rdx
  HRESULT v21; // eax
  HRESULT v22; // eax
  unsigned int v23; // r13d
  CDRMCBase *v24; // r12
  unsigned __int8 *v26; // r12
  CHandlesTable *v27; // rcx
  HRESULT v28; // eax
  const char *v29; // rcx
  DRMPUBHANDLE v30; // esi
  int Events; // eax
  struct CUser *v32; // [rsp+48h] [rbp-41h] BYREF
  DRMHANDLE phDecryptor; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+54h] [rbp-35h] BYREF
  unsigned int v35; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v36; // [rsp+5Ch] [rbp-2Dh] BYREF
  wchar_t *Str; // [rsp+60h] [rbp-29h]
  void *Block; // [rsp+68h] [rbp-21h] BYREF
  unsigned __int16 *v39; // [rsp+70h] [rbp-19h] BYREF
  unsigned __int8 *v40; // [rsp+78h] [rbp-11h] BYREF
  unsigned __int16 *v41; // [rsp+80h] [rbp-9h] BYREF

  v9 = wszReferralInfoURL;
  v11 = pstTimeUntil;
  _RTLTRACE("[msdrm]:+DRMCreateIssuanceLicense");
  v32 = 0;
  v13 = 0;
  v36 = 0;
  v14 = 0;
  Block = 0;
  v39 = 0;
  v41 = 0;
  v40 = 0;
  v34 = 0;
  phDecryptor = 0;
  v35 = 0;
  Str = 0;
  if ( wszReferralInfoName && !(unsigned __int8)DRMIsValidStringT<unsigned short>(wszReferralInfoName, 0, 0, v12) )
    goto LABEL_8;
  if ( v9 && !(unsigned __int8)DRMIsValidStringT<unsigned short>(v9, 0, 0, v12) )
    goto LABEL_8;
  v15 = wszIssuanceLicense;
  if ( wszIssuanceLicense )
  {
    if ( !(unsigned __int8)DRMIsValidStringT<unsigned short>(wszIssuanceLicense, 0, 0, v12) )
      goto LABEL_8;
  }
  if ( !phIssuanceLicense || pstTimeFrom && !v11 )
    goto LABEL_8;
  if ( v11 )
  {
    if ( !pstTimeFrom )
    {
LABEL_8:
      SPHandle = -2147024809;
LABEL_39:
      v24 = v32;
      goto LABEL_40;
    }
  }
  else if ( !pstTimeFrom )
  {
    goto LABEL_18;
  }
  if ( !IsSystemTimeValid(pstTimeFrom) || v11 && !IsSystemTimeValid(v11) )
    goto LABEL_8;
LABEL_18:
  if ( hOwner )
  {
    UserPointer = GetUserPointer(hOwner, &v32);
    SPHandle = UserPointer;
    if ( UserPointer < 0 )
    {
      v18 = "[msdrm]:GetUserPointer FAILED : %x";
LABEL_21:
      _RTLTRACE(v18, (unsigned int)UserPointer);
      goto LABEL_39;
    }
  }
  v19 = (CIssuanceLicense *)operator new(0x3D0u);
  if ( !v19 || (v13 = (DRMHANDLE *)CIssuanceLicense::CIssuanceLicense(v19)) == 0 )
  {
LABEL_38:
    SPHandle = -2147024882;
    goto LABEL_39;
  }
  _RTLTRACE(
    "([msdrm]:Referral Info Name=%ls, Referral Info URL=%ls, Rights Template=%ls)\n",
    wszReferralInfoName,
    v9,
    wszIssuanceLicense);
  if ( wszIssuanceLicense )
  {
    if ( wcsstr(wszIssuanceLicense, L"Microsoft Rights Label") )
    {
      UserPointer = CIssuanceLicense::ParseSignedIssuanceLicense(
                      (CIssuanceLicense *)v13,
                      wszIssuanceLicense,
                      (unsigned __int16 **)((unsigned __int64)&v41 & -(__int64)(hBoundLicense != 0)));
      SPHandle = UserPointer;
      if ( UserPointer < 0 )
      {
        v18 = "[msdrm]:ParseSignedIssuanceLicense FAILED : %x";
        goto LABEL_21;
      }
      if ( hBoundLicense )
      {
        v20 = -1;
        do
          ++v20;
        while ( v41[v20] );
        UserPointer = CDRMCBase::Base64DecodeData((CDRMCBase *)&v40, v20, v41, &v34, &v40);
        SPHandle = UserPointer;
        if ( UserPointer < 0 )
        {
          v18 = "[msdrm]:Base64DecodeData FAILED : %x";
          goto LABEL_21;
        }
        v21 = DRMCreateEnablingBitsDecryptor(hBoundLicense, (PWSTR)L"VIEWRIGHTSDATA", 0, 0, &phDecryptor);
        if ( v21 < 0 )
        {
          _RTLTRACE("[msdrm]:DRMCreateEnablingBitsDecryptor FAILED for VIEWRIGHTSDATA : %x", v21);
          v22 = DRMCreateEnablingBitsDecryptor(hBoundLicense, (PWSTR)L"EDITRIGHTSDATA", 0, 0, &phDecryptor);
          SPHandle = v22;
          if ( v22 < 0 )
          {
            _RTLTRACE("[msdrm]:DRMCreateEnablingBitsDecryptor FAILED for EDITRIGHTSDATA: %x", v22);
            v14 = phDecryptor;
            goto LABEL_39;
          }
        }
        v23 = v34;
        v35 = 2 * v34;
        Str = (wchar_t *)operator new(saturated_mul(((2 * v34) >> 1) + 1, 2u));
        if ( !Str )
        {
          v14 = phDecryptor;
          goto LABEL_38;
        }
        memset_0(Str, 0, 2LL * ((v35 >> 1) + 1));
        v26 = v40;
        _RTLTRACE("[msdrm]:+_DRMDecryptECB\n");
        v34 = 0;
        v14 = phDecryptor;
        if ( v26 )
        {
          SPHandle = CHandlesTable::GetSPHandle(v27, phDecryptor, &v34);
          if ( SPHandle >= 0 )
            SPHandle = ((__int64 (__fastcall *)(_QWORD, _QWORD, __int64, _QWORD, unsigned __int8 *, unsigned int *, wchar_t *))g_pfnSPDecrypt)(
                         v34,
                         0,
                         4096,
                         v23,
                         v26,
                         &v35,
                         Str);
        }
        else
        {
          SPHandle = -2147024809;
        }
        _RTLTRACE("[msdrm]:-_DRMDecryptECB HR=0x%x\n", SPHandle);
        if ( SPHandle == -2147024774 )
        {
          SPHandle = -2147024774;
          goto LABEL_58;
        }
        if ( SPHandle == -1073426388 )
        {
          SPHandle = -2147168468;
LABEL_58:
          _RTLTRACE("[msdrm]:DRMDecrypt FAILED : %x", (unsigned int)SPHandle);
          goto LABEL_39;
        }
        if ( SPHandle < 0 )
          goto LABEL_58;
        UserPointer = CIssuanceLicense::ParseIssuanceLicenseTemplate((CIssuanceLicense *)v13, Str);
        SPHandle = UserPointer;
        if ( UserPointer < 0 )
        {
LABEL_56:
          v18 = "[msdrm]:ParseIssuanceLicenseTemplate FAILED : %x";
          goto LABEL_21;
        }
        v9 = wszReferralInfoURL;
        v11 = pstTimeUntil;
      }
    }
    else
    {
      if ( !wcsstr(wszIssuanceLicense, L"Microsoft Rights Template")
        && !wcsstr(wszIssuanceLicense, L"Microsoft Official Rights Template") )
      {
        goto LABEL_8;
      }
      UserPointer = CIssuanceLicense::ParseIssuanceLicenseTemplate((CIssuanceLicense *)v13, wszIssuanceLicense);
      SPHandle = UserPointer;
      if ( UserPointer < 0 )
        goto LABEL_56;
    }
  }
  if ( wszReferralInfoName || v9 )
  {
    UserPointer = EscapeXML(wszReferralInfoName, (unsigned __int16 **)&Block);
    SPHandle = UserPointer;
    if ( UserPointer < 0 || (UserPointer = EscapeXML(v9, &v39), SPHandle = UserPointer, UserPointer < 0) )
    {
      v18 = "[msdrm]:EscapeXML FAILED : %x";
      goto LABEL_21;
    }
  }
  v24 = v32;
  if ( Str )
    v15 = Str;
  v28 = CIssuanceLicense::Init((CIssuanceLicense *)v13, pstTimeFrom, v11, (unsigned __int16 *)Block, v39, v32, v15);
  SPHandle = v28;
  if ( v28 < 0 )
  {
    v29 = "[msdrm]:pCIssuanceLicense->Init FAILED : %x";
LABEL_73:
    _RTLTRACE(v29, (unsigned int)v28);
    goto LABEL_40;
  }
  v28 = DRMCInt::CreateHandle(5u, v13, &v36);
  SPHandle = v28;
  if ( v28 < 0 )
  {
    v29 = "[msdrm]:CreateHandle FAILED : %x";
    goto LABEL_73;
  }
  v30 = v36;
  Events = CIssuanceLicense::CreateEvents((CIssuanceLicense *)v13, v36);
  SPHandle = Events;
  if ( Events >= 0 )
  {
    if ( hBoundLicense )
    {
      v28 = DRMDuplicateHandle(hBoundLicense, v13 + 240);
      SPHandle = v28;
      if ( v28 < 0 )
      {
        v29 = "[msdrm]:Duplication of Bound License FAILED : %x";
        goto LABEL_73;
      }
    }
    v13 = 0;
    *phIssuanceLicense = v30;
  }
  else
  {
    _RTLTRACE("[msdrm]:CreateEvents FAILED : %x", (unsigned int)Events);
  }
LABEL_40:
  operator delete(Block);
  operator delete(v39);
  operator delete(v40);
  operator delete(v41);
  operator delete(Str);
  if ( v13 )
    CDRMCBase::Release((CDRMCBase *)v13);
  if ( v24 )
    CDRMCBase::Release(v24);
  if ( v14 )
    DRMCloseHandle(v14);
  _RTLTRACE("[msdrm]:-DRMCreateIssuanceLicense HR=%x\n", SPHandle);
  return SPHandle;
}

```

## disassembly

```asm
0x180004970  mov     rax, rsp
0x180004973  mov     [rax+20h], r9
0x180004977  mov     [rax+18h], r8
0x18000497b  mov     [rax+10h], rdx
0x18000497f  mov     [rax+8], rcx
0x180004983  push    rbp
0x180004984  push    rbx
0x180004985  push    rsi
0x180004986  push    rdi
0x180004987  push    r12
0x180004989  push    r13
0x18000498b  push    r14
0x18000498d  push    r15
0x18000498f  lea     rbp, [rax-47h]
0x180004993  sub     rsp, 88h
0x18000499a  mov     rbx, rcx
0x18000499d  mov     r12, r9
0x1800049a0  lea     rcx, aMsdrmDrmcreate_14; "[msdrm]:+DRMCreateIssuanceLicense"
0x1800049a7  mov     r14, r8
0x1800049aa  mov     r13, rdx
0x1800049ad  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x1800049b2  xor     r8d, r8d
0x1800049b5  mov     [rbp+3Fh+var_80], r8
0x1800049b9  mov     edi, r8d
0x1800049bc  mov     [rbp+3Fh+var_6C], r8d
0x1800049c0  mov     r15d, r8d
0x1800049c3  mov     [rbp+3Fh+Block], r8
0x1800049c7  mov     [rbp+3Fh+var_58], r8
0x1800049cb  mov     [rbp+3Fh+var_48], r8
0x1800049cf  mov     [rbp+3Fh+var_50], r8
0x1800049d3  mov     [rbp+3Fh+var_74], r8d
0x1800049d7  mov     [rbp+3Fh+var_78], r8d
0x1800049db  mov     [rbp+3Fh+var_70], r8d
0x1800049df  mov     [rbp+3Fh+Str], r8
0x1800049e3  test    r14, r14
0x1800049e6  jz      short loc_1800049F9
0x1800049e8  xor     edx, edx
0x1800049ea  mov     rcx, r14
0x1800049ed  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x1800049f2  xor     r8d, r8d
0x1800049f5  test    al, al
0x1800049f7  jz      short loc_180004A32
0x1800049f9  test    r12, r12
0x1800049fc  jz      short loc_180004A0F
0x1800049fe  xor     edx, edx
0x180004a00  mov     rcx, r12
0x180004a03  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180004a08  xor     r8d, r8d
0x180004a0b  test    al, al
0x180004a0d  jz      short loc_180004A32
0x180004a0f  mov     rsi, [rbp+3Fh+wszIssuanceLicense]
0x180004a13  test    rsi, rsi
0x180004a16  jz      short loc_180004A29
0x180004a18  xor     edx, edx
0x180004a1a  mov     rcx, rsi
0x180004a1d  call    ??$DRMIsValidStringT@G@@YA_NPEBGPEA_K@Z; DRMIsValidStringT<ushort>(ushort const *,unsigned __int64 *)
0x180004a22  xor     r8d, r8d
0x180004a25  test    al, al
0x180004a27  jz      short loc_180004A32
0x180004a29  cmp     [rbp+3Fh+phIssuanceLicense], r8
0x180004a30  jnz     short loc_180004A3C
0x180004a32  mov     ebx, 80070057h
0x180004a37  jmp     loc_180004C1C
0x180004a3c  test    rbx, rbx
0x180004a3f  jz      short loc_180004A46
0x180004a41  test    r13, r13
0x180004a44  jz      short loc_180004A32
0x180004a46  test    r13, r13
0x180004a49  jz      short loc_180004A52
0x180004a4b  test    rbx, rbx
0x180004a4e  jnz     short loc_180004A57
0x180004a50  jmp     short loc_180004A32
0x180004a52  test    rbx, rbx
0x180004a55  jz      short loc_180004A74
0x180004a57  mov     rcx, rbx; struct _SYSTEMTIME *
0x180004a5a  call    ?IsSystemTimeValid@@YA_NPEAU_SYSTEMTIME@@@Z; IsSystemTimeValid(_SYSTEMTIME *)
0x180004a5f  test    al, al
0x180004a61  jz      short loc_180004A32
0x180004a63  test    r13, r13
0x180004a66  jz      short loc_180004A74
0x180004a68  mov     rcx, r13; struct _SYSTEMTIME *
0x180004a6b  call    ?IsSystemTimeValid@@YA_NPEAU_SYSTEMTIME@@@Z; IsSystemTimeValid(_SYSTEMTIME *)
0x180004a70  test    al, al
0x180004a72  jz      short loc_180004A32
0x180004a74  mov     ecx, [rbp+3Fh+hOwner]; unsigned int
0x180004a77  test    ecx, ecx
0x180004a79  jz      short loc_180004A9D
0x180004a7b  lea     rdx, [rbp+3Fh+var_80]; struct CUser **
0x180004a7f  call    ?GetUserPointer@@YAJKPEAPEAVCUser@@@Z; GetUserPointer(ulong,CUser * *)
0x180004a84  mov     ebx, eax
0x180004a86  test    eax, eax
0x180004a88  jns     short loc_180004A9D
0x180004a8a  lea     rcx, aMsdrmGetuserpo; "[msdrm]:GetUserPointer FAILED : %x"
0x180004a91  mov     edx, eax
0x180004a93  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004a98  jmp     loc_180004C1C
0x180004a9d  mov     ecx, 3D0h; Size
0x180004aa2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004aa7  xor     ebx, ebx
0x180004aa9  test    rax, rax
0x180004aac  jz      loc_180004C17
0x180004ab2  mov     rcx, rax; this
0x180004ab5  call    ??0CIssuanceLicense@@QEAA@XZ; CIssuanceLicense::CIssuanceLicense(void)
0x180004aba  mov     rdi, rax
0x180004abd  test    rax, rax
0x180004ac0  jz      loc_180004C17
0x180004ac6  mov     r9, rsi
0x180004ac9  lea     rcx, aMsdrmReferralI; "([msdrm]:Referral Info Name=%ls, Referr"...
0x180004ad0  mov     r8, r12
0x180004ad3  mov     rdx, r14
0x180004ad6  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004adb  mov     r14d, [rbp+3Fh+hBoundLicense]
0x180004adf  test    rsi, rsi
0x180004ae2  jz      loc_180004DB6
0x180004ae8  lea     rdx, aMicrosoftRight; "Microsoft Rights Label"
0x180004aef  mov     rcx, rsi; Str
0x180004af2  call    cs:__imp_wcsstr
0x180004af8  test    rax, rax
0x180004afb  jz      loc_180004D6D
0x180004b01  mov     eax, r14d
0x180004b04  mov     rdx, rsi; unsigned __int16 *
0x180004b07  neg     eax
0x180004b09  mov     rcx, rdi; this
0x180004b0c  lea     rax, [rbp+3Fh+var_48]
0x180004b10  sbb     r8, r8
0x180004b13  and     r8, rax; unsigned __int16 **
0x180004b16  call    ?ParseSignedIssuanceLicense@CIssuanceLicense@@QEAAJPEAGPEAPEAG@Z; CIssuanceLicense::ParseSignedIssuanceLicense(ushort *,ushort * *)
0x180004b1b  mov     ebx, eax
0x180004b1d  test    eax, eax
0x180004b1f  jns     short loc_180004B2D
0x180004b21  lea     rcx, aMsdrmParsesign; "[msdrm]:ParseSignedIssuanceLicense FAIL"...
0x180004b28  jmp     loc_180004A91
0x180004b2d  xor     ebx, ebx
0x180004b2f  test    r14d, r14d
0x180004b32  jz      loc_180004DB6
0x180004b38  mov     rax, [rbp+3Fh+var_48]
0x180004b3c  or      r12, 0FFFFFFFFFFFFFFFFh
0x180004b40  mov     rdx, r12
0x180004b43  inc     rdx; unsigned int
0x180004b46  cmp     [rax+rdx*2], bx
0x180004b4a  jnz     short loc_180004B43
0x180004b4c  lea     rcx, [rbp+3Fh+var_50]; this
0x180004b50  mov     r8, rax; unsigned __int16 *
0x180004b53  lea     r9, [rbp+3Fh+var_74]; unsigned int *
0x180004b57  mov     [rsp+0C0h+phDecryptor], rcx; unsigned __int8 **
0x180004b5c  call    ?Base64DecodeData@CDRMCBase@@QEAAJIPEAGPEAIPEAPEAE@Z; CDRMCBase::Base64DecodeData(uint,ushort *,uint *,uchar * *)
0x180004b61  mov     ebx, eax
0x180004b63  test    eax, eax
0x180004b65  jns     short loc_180004B73
0x180004b67  lea     rcx, aMsdrmBase64dec; "[msdrm]:Base64DecodeData FAILED : %x"
0x180004b6e  jmp     loc_180004A91
0x180004b73  lea     rax, [rbp+3Fh+var_78]
0x180004b77  xor     r9d, r9d; wszAuxPlug
0x180004b7a  xor     r8d, r8d; hAuxLib
0x180004b7d  mov     [rsp+0C0h+phDecryptor], rax; phDecryptor
0x180004b82  lea     rdx, wszRight; "VIEWRIGHTSDATA"
0x180004b89  mov     ecx, r14d; hBoundLicense
0x180004b8c  call    DRMCreateEnablingBitsDecryptor
0x180004b91  test    eax, eax
0x180004b93  jns     short loc_180004BDB
0x180004b95  mov     edx, eax
0x180004b97  lea     rcx, aMsdrmDrmcreate_15; "[msdrm]:DRMCreateEnablingBitsDecryptor "...
0x180004b9e  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004ba3  lea     rax, [rbp+3Fh+var_78]
0x180004ba7  xor     r9d, r9d; wszAuxPlug
0x180004baa  xor     r8d, r8d; hAuxLib
0x180004bad  mov     [rsp+0C0h+phDecryptor], rax; phDecryptor
0x180004bb2  lea     rdx, aEditrightsdata; "EDITRIGHTSDATA"
0x180004bb9  mov     ecx, r14d; hBoundLicense
0x180004bbc  call    DRMCreateEnablingBitsDecryptor
0x180004bc1  mov     ebx, eax
0x180004bc3  test    eax, eax
0x180004bc5  jns     short loc_180004BDB
0x180004bc7  mov     edx, eax
0x180004bc9  lea     rcx, aMsdrmDrmcreate_0; "[msdrm]:DRMCreateEnablingBitsDecryptor "...
0x180004bd0  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004bd5  mov     r15d, [rbp+3Fh+var_78]
0x180004bd9  jmp     short loc_180004C1C
0x180004bdb  mov     r13d, [rbp+3Fh+var_74]
0x180004bdf  lea     eax, ds:0[r13*2]
0x180004be7  mov     [rbp+3Fh+var_70], eax
0x180004bea  shr     eax, 1
0x180004bec  lea     ecx, [rax+1]
0x180004bef  mov     eax, 2
0x180004bf4  mul     rcx
0x180004bf7  cmovb   rax, r12
0x180004bfb  mov     rcx, rax; Size
0x180004bfe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004c03  mov     [rbp+3Fh+Str], rax
0x180004c07  mov     rcx, rax; void *
0x180004c0a  test    rax, rax
0x180004c0d  jnz     loc_180004C98
0x180004c13  mov     r15d, [rbp+3Fh+var_78]
0x180004c17  mov     ebx, 8007000Eh
0x180004c1c  mov     r12, [rbp+3Fh+var_80]
0x180004c20  mov     rcx, [rbp+3Fh+Block]; Block
0x180004c24  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c29  mov     rcx, [rbp+3Fh+var_58]; Block
0x180004c2d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c32  mov     rcx, [rbp+3Fh+var_50]; Block
0x180004c36  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c3b  mov     rcx, [rbp+3Fh+var_48]; Block
0x180004c3f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c44  mov     rcx, [rbp+3Fh+Str]; Block
0x180004c48  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004c4d  test    rdi, rdi
0x180004c50  jz      short loc_180004C5A
0x180004c52  mov     rcx, rdi; this
0x180004c55  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x180004c5a  test    r12, r12
0x180004c5d  jz      short loc_180004C67
0x180004c5f  mov     rcx, r12; this
0x180004c62  call    ?Release@CDRMCBase@@QEAAKXZ; CDRMCBase::Release(void)
0x180004c67  test    r15d, r15d
0x180004c6a  jz      short loc_180004C74
0x180004c6c  mov     ecx, r15d; handle
0x180004c6f  call    DRMCloseHandle
0x180004c74  mov     edx, ebx
0x180004c76  lea     rcx, aMsdrmDrmcreate_4; "[msdrm]:-DRMCreateIssuanceLicense HR=%x"...
0x180004c7d  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004c82  mov     eax, ebx
0x180004c84  add     rsp, 88h
0x180004c8b  pop     r15
0x180004c8d  pop     r14
0x180004c8f  pop     r13
0x180004c91  pop     r12
0x180004c93  pop     rdi
0x180004c94  pop     rsi
0x180004c95  pop     rbx
0x180004c96  pop     rbp
0x180004c97  retn
0x180004c98  mov     r8d, [rbp+3Fh+var_70]
0x180004c9c  xor     edx, edx; Val
0x180004c9e  shr     r8d, 1
0x180004ca1  inc     r8d
0x180004ca4  add     r8, r8; Size
0x180004ca7  call    memset_0
0x180004cac  mov     r12, [rbp+3Fh+var_50]
0x180004cb0  lea     rcx, aMsdrmDrmdecryp_1; "[msdrm]:+_DRMDecryptECB\n"
0x180004cb7  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004cbc  mov     [rbp+3Fh+var_74], r15d
0x180004cc0  mov     r15d, [rbp+3Fh+var_78]
0x180004cc4  test    r12, r12
0x180004cc7  jz      short loc_180004D10
0x180004cc9  lea     r8, [rbp+3Fh+var_74]; unsigned int *
0x180004ccd  mov     edx, r15d; unsigned int
0x180004cd0  call    ?GetSPHandle@CHandlesTable@@QEAAJKPEAK@Z; CHandlesTable::GetSPHandle(ulong,ulong *)
0x180004cd5  mov     ebx, eax
0x180004cd7  test    eax, eax
0x180004cd9  js      short loc_180004D15
0x180004cdb  mov     rax, [rbp+3Fh+Str]
0x180004cdf  mov     r9d, r13d
0x180004ce2  mov     ecx, [rbp+3Fh+var_74]
0x180004ce5  xor     edx, edx
0x180004ce7  mov     [rsp+30h], rax
0x180004cec  mov     r8d, 1000h
0x180004cf2  lea     rax, [rbp+3Fh+var_70]
0x180004cf6  mov     [rsp+0C0h+var_98], rax
0x180004cfb  mov     rax, cs:?g_pfnSPDecrypt@@3P6AJKIKKPEAEPEAK0@ZEA; long (*g_pfnSPDecrypt)(ulong,uint,ulong,ulong,uchar *,ulong *,uchar *)
0x180004d02  mov     [rsp+0C0h+phDecryptor], r12
0x180004d07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d0c  mov     ebx, eax
0x180004d0e  jmp     short loc_180004D15
0x180004d10  mov     ebx, 80070057h
0x180004d15  mov     edx, ebx
0x180004d17  lea     rcx, aMsdrmDrmdecryp_3; "[msdrm]:-_DRMDecryptECB HR=0x%x\n"
0x180004d1e  call    ?_RTLTRACE@@YAXPEBDZZ; _RTLTRACE(char const *,...)
0x180004d23  mov     eax, 8007007Ah
0x180004d28  cmp     ebx, eax
0x180004d2a  jz      short loc_180004D5D
0x180004d2c  cmp     ebx, 0C004D02Ch
0x180004d32  jnz     short loc_180004D3B
0x180004d34  mov     ebx, 8004CF2Ch
0x180004d39  jmp     short loc_180004D5F
0x180004d3b  test    ebx, ebx
0x180004d3d  js      short loc_180004D5F
0x180004d3f  mov     rdx, [rbp+3Fh+Str]; unsigned __int16 *
0x180004d43  mov     rcx, rdi; this
0x180004d46  call    ?ParseIssuanceLicenseTemplate@CIssuanceLicense@@QEAAJPEAG@Z; CIssuanceLicense::ParseIssuanceLicenseTemplate(ushort *)
0x180004d4b  mov     ebx, eax
0x180004d4d  test    eax, eax
0x180004d4f  jns     short loc_180004DAE
0x180004d51  lea     rcx, aMsdrmParseissu; "[msdrm]:ParseIssuanceLicenseTemplate FA"...
0x180004d58  jmp     loc_180004A91
0x180004d5d  mov     ebx, eax
0x180004d5f  mov     edx, ebx
0x180004d61  lea     rcx, aMsdrmDrmdecryp; "[msdrm]:DRMDecrypt FAILED : %x"
0x180004d68  jmp     loc_180004A93
0x180004d6d  lea     rdx, aMicrosoftRight_0; "Microsoft Rights Template"
0x180004d74  mov     rcx, rsi; Str
0x180004d77  call    cs:__imp_wcsstr
0x180004d7d  test    rax, rax
0x180004d80  jnz     short loc_180004D9B
0x180004d82  lea     rdx, aMicrosoftOffic; "Microsoft Official Rights Template"
0x180004d89  mov     rcx, rsi; Str
0x180004d8c  call    cs:__imp_wcsstr
0x180004d92  test    rax, rax
0x180004d95  jz      loc_180004A32
0x180004d9b  mov     rdx, rsi; unsigned __int16 *
0x180004d9e  mov     rcx, rdi; this
  ... truncated ...
```
