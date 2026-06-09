# SspAcceptCredentials

- ea: `0x1800193e0`
- end: `0x18001a0e7`
- name: `SspAcceptCredentials`
- size: `3335`
- prototype: `__int64 __fastcall(int, __int64, __int64)`
- caller_count: `2`
- callee_count: `21`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180019340`
- `0x18003e6a0`

## callees

- `0x18000b890`
- `0x18000c000`
- `0x18000c5d0`
- `0x18000c630`
- `0x18000cba0`
- `0x1800122c0`
- `0x1800127c0`
- `0x1800186d4`
- `0x1800193e0`
- `0x18001fefc`
- `0x18002ead4`
- `0x18002ee7c`
- `0x18002f014`
- `0x18002fb50`
- `0x18002fb90`
- `0x180030844`
- `0x18003509c`
- `0x180040124`
- `0x1800403c4`
- `0x18006bd74`
- `0x18006d010`

## import_xrefs

- `NtlmShared!MsvpValidateSupplementalCreds` at `0x18001945e`
- `NtlmShared!MsvpValidateSupplementalCreds` at `0x180019fbd`
- `NtlmShared!MsvpValidateSupplementalCreds` at `0x18001945e`
- `NtlmShared!MsvpValidateSupplementalCreds` at `0x180019fbd`
- `ntdll!RtlLengthSid` at `0x180019bd0`
- `ntdll!RtlLengthSid` at `0x180019bd0`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001980b`
- `ntdll!RtlAcquireResourceExclusive` at `0x18001980b`
- `ntdll!RtlCopyUnicodeString` at `0x180019961`
- `ntdll!RtlCopyUnicodeString` at `0x1800199a4`
- `ntdll!RtlCopyUnicodeString` at `0x180019d0e`
- `ntdll!RtlCopyUnicodeString` at `0x180019d52`
- `ntdll!RtlCopyUnicodeString` at `0x180019d93`
- `ntdll!RtlCopyUnicodeString` at `0x180019961`
- `ntdll!RtlCopyUnicodeString` at `0x1800199a4`
- `ntdll!RtlCopyUnicodeString` at `0x180019d0e`
- `ntdll!RtlCopyUnicodeString` at `0x180019d52`
- `ntdll!RtlCopyUnicodeString` at `0x180019d93`
- `ntdll!EtwEventWriteTransfer` at `0x180019bb2`
- `ntdll!EtwEventWriteTransfer` at `0x180019bb2`
- `ntdll!RtlCopySid` at `0x180019cc5`
- `ntdll!RtlCopySid` at `0x180019cc5`
- `ntdll!RtlConvertSharedToExclusive` at `0x180019ed7`
- `ntdll!RtlConvertSharedToExclusive` at `0x180019ed7`
- `ntdll!RtlAvlInsertNodeEx` at `0x180019f2c`
- `ntdll!RtlAvlInsertNodeEx` at `0x180019f2c`
- `ntdll!RtlReleaseResource` at `0x180019561`
- `ntdll!RtlReleaseResource` at `0x180019869`
- `ntdll!RtlReleaseResource` at `0x180019def`
- `ntdll!RtlReleaseResource` at `0x180019eb1`
- `ntdll!RtlReleaseResource` at `0x180019f66`
- `ntdll!RtlReleaseResource` at `0x180019561`
- `ntdll!RtlReleaseResource` at `0x180019869`
- `ntdll!RtlReleaseResource` at `0x180019def`
- `ntdll!RtlReleaseResource` at `0x180019eb1`
- `ntdll!RtlReleaseResource` at `0x180019f66`
- `ntdll!RtlAcquireResourceShared` at `0x180019542`
- `ntdll!RtlAcquireResourceShared` at `0x180019db7`
- `ntdll!RtlAcquireResourceShared` at `0x180019542`
- `ntdll!RtlAcquireResourceShared` at `0x180019db7`
- `ntdll!RtlInitUnicodeString` at `0x18001997e`
- `ntdll!RtlInitUnicodeString` at `0x1800199b7`
- `ntdll!RtlInitUnicodeString` at `0x180019d2a`
- `ntdll!RtlInitUnicodeString` at `0x180019d6e`
- `ntdll!RtlInitUnicodeString` at `0x180019da8`
- `ntdll!RtlInitUnicodeString` at `0x18001997e`
- `ntdll!RtlInitUnicodeString` at `0x1800199b7`
- `ntdll!RtlInitUnicodeString` at `0x180019d2a`
- `ntdll!RtlInitUnicodeString` at `0x180019d6e`
- `ntdll!RtlInitUnicodeString` at `0x180019da8`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x1800195e1`
- `api-ms-win-security-credentials-l2-1-0!CredParseUserNameWithType` at `0x1800195e1`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x18001a035`
- `LSASRV!LsaIEventWritePackageNotCacheLogonUser` at `0x18001a035`

## pseudocode

```c
__int64 __fastcall SspAcceptCredentials(int a1, __int64 a2, __int64 a3)
{
  struct _MSV1_0_PRIMARY_CREDENTIAL *v3; // rdi
  int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  LUID v9; // rcx
  int v10; // esi
  __int64 v11; // rax
  __int64 v12; // r9
  NTSTATUS CredentialKey; // ebx
  unsigned int v14; // eax
  __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  int v17; // eax
  _QWORD *v18; // rcx
  int v19; // eax
  NTSTATUS PrimaryCredentialFromStrongSupplementalCredential; // eax
  __int64 ActiveLogon; // rax
  __int64 v22; // r9
  int v23; // ecx
  int v24; // r8d
  unsigned int v25; // ecx
  unsigned int v26; // eax
  int v27; // r8d
  int v28; // r12d
  __int64 v29; // rcx
  int v30; // r12d
  LONG CredEncryptionTypeForUser; // eax
  int v32; // edx
  int v33; // ecx
  int v34; // r8d
  int v35; // edx
  unsigned int v36; // ebx
  __int64 v37; // rsi
  __int64 v38; // rbx
  __int64 Length; // rcx
  struct _UNICODE_STRING *v40; // rcx
  int v41; // eax
  int v42; // eax
  ULONG v43; // eax
  int v44; // ecx
  ULONG v45; // ebx
  __int64 v46; // rax
  __int64 v47; // rsi
  int v48; // eax
  int v49; // ecx
  void *v50; // r8
  struct _MSV1_0_PRIMARY_CREDENTIAL *v51; // rcx
  __int64 v52; // rax
  unsigned __int64 v53; // rbx
  struct _UNICODE_STRING *v54; // rcx
  unsigned __int64 v55; // rbx
  __int64 v56; // rcx
  struct _UNICODE_STRING *v57; // rcx
  __int64 v58; // rcx
  const UNICODE_STRING *v59; // rdx
  struct _UNICODE_STRING *v60; // rcx
  __int64 v61; // rax
  struct _RTL_BALANCED_NODE *v63; // rbx
  __int64 v64; // r8
  struct _RTL_BALANCED_NODE *v65; // rax
  __int64 v66; // rax
  _QWORD *v67; // rcx
  __int64 v68; // rbx
  int v69; // eax
  int v70; // ebx
  __int128 v71; // xmm6
  char v72; // dl
  int v73; // r8d
  __int64 v74; // r9
  _BYTE *v75; // rax
  __int64 v76; // rcx
  int v77; // eax
  __int64 v78; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v79; // [rsp+38h] [rbp-C8h] BYREF
  struct _MSV1_0_PRIMARY_CREDENTIAL *v80; // [rsp+40h] [rbp-C0h] BYREF
  LUID v81; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v82; // [rsp+50h] [rbp-B0h] BYREF
  LONG HighPart; // [rsp+54h] [rbp-ACh] BYREF
  unsigned int v84; // [rsp+58h] [rbp-A8h]
  int v85; // [rsp+5Ch] [rbp-A4h]
  UNICODE_STRING SourceString; // [rsp+60h] [rbp-A0h] BYREF
  int v87; // [rsp+70h] [rbp-90h] BYREF
  _QWORD v88[2]; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v89[3]; // [rsp+88h] [rbp-78h] BYREF
  UNICODE_STRING v90; // [rsp+A0h] [rbp-60h] BYREF
  __int16 *v91; // [rsp+B0h] [rbp-50h] BYREF
  int v92; // [rsp+B8h] [rbp-48h]
  int v93; // [rsp+BCh] [rbp-44h]
  int *v94; // [rsp+C0h] [rbp-40h]
  int v95; // [rsp+C8h] [rbp-38h]
  int v96; // [rsp+CCh] [rbp-34h]
  const char *v97; // [rsp+D0h] [rbp-30h]
  __int64 v98; // [rsp+D8h] [rbp-28h]
  char *v99; // [rsp+E0h] [rbp-20h]
  __int64 v100; // [rsp+E8h] [rbp-18h]
  LONG *p_HighPart; // [rsp+F0h] [rbp-10h]
  __int64 v102; // [rsp+F8h] [rbp-8h]
  unsigned int *v103; // [rsp+100h] [rbp+0h]
  __int64 v104; // [rsp+108h] [rbp+8h]
  __int64 *v105; // [rsp+110h] [rbp+10h]
  __int64 v106; // [rsp+118h] [rbp+18h]
  _WORD v107[520]; // [rsp+120h] [rbp+20h] BYREF

  v85 = a1;
  v80 = 0;
  v79 = 0;
  v87 = 0;
  v89[1] = L"NTLM";
  v3 = 0;
  v81 = 0;
  SourceString = 0;
  v88[0] = a3;
  v90 = 0;
  v89[0] = 655368;
  v6 = MsvpValidateSupplementalCreds(a3);
  v7 = *(unsigned int *)(a2 + 80);
  LOBYTE(v8) = 0;
  v9 = *(LUID *)a2;
  v10 = v6;
  HIDWORD(v78) = v8;
  v11 = a2;
  v81 = v9;
  if ( (v7 & 0x1000) == 0 )
    v11 = 0;
  v12 = 1;
  if ( (v7 & 0x20001) != 0 )
  {
    if ( (v7 & 0x10001) == 0x10001 )
    {
      v8 = *(_QWORD *)(a2 + 48) == 0;
      HIDWORD(v78) = *(_QWORD *)(a2 + 48) == 0;
    }
  }
  else if ( v10 == -1 )
  {
    if ( (v7 & 0x10000) == 0 || (v7 & 0x108000) == 0 && (!v11 || (*(_BYTE *)(v11 + 216) & 1) == 0) )
    {
      CredentialKey = 0;
      goto LABEL_126;
    }
    BYTE4(v78) = 1;
  }
  if ( v9 == 999 )
    v81 = NtLmGlobalLuidMachineLogon;
  if ( NtLmLocklessGlobalPreferredDomainString.Buffer )
  {
    SourceString = NtLmLocklessGlobalPreferredDomainString;
  }
  else if ( v9 == 999 || v9 == 996 )
  {
    RtlAcquireResourceShared(&NtLmGlobalCritSect, 1u);
    CredentialKey = NtLmDuplicateUnicodeString(&v90, &NtLmGlobalUnicodePrimaryDomainNameString);
    RtlReleaseResource(&NtLmGlobalCritSect);
    if ( CredentialKey < 0 )
      goto LABEL_126;
    SourceString = v90;
  }
  else
  {
    SourceString = *(UNICODE_STRING *)(a2 + 24);
  }
  v14 = 1024;
  if ( *(_WORD *)(a2 + 8) >= 0x400u || (v14 = *(unsigned __int16 *)(a2 + 8), *(_WORD *)(a2 + 8)) )
  {
    v15 = v14;
    memcpy_0(v107, *(const void **)(a2 + 16), v14);
    if ( v107[(unsigned __int64)(unsigned int)v15 >> 1] )
    {
      v16 = v15 & 0xFFFFFFFFFFFFFFFEuLL;
      if ( v16 >= 0x402 )
        _report_rangecheckfailure();
      *(_WORD *)((char *)v107 + v16) = 0;
    }
    v17 = CredParseUserNameWithType(v107, 0, 0, &v87);
    CredentialKey = v17;
    if ( v17 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          126,
          WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids,
          (unsigned int)v17);
      goto LABEL_126;
    }
    if ( v87 == 3 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 127, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
      CredentialKey = -1073741637;
      goto LABEL_126;
    }
  }
  switch ( v10 )
  {
    case -65533:
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x4000) != 0 )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids);
        v18 = WPP_GLOBAL_Control;
      }
      v7 = *(unsigned int *)(a3 + 16);
      if ( (unsigned int)v7 < 0x70 )
      {
        if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
          WPP_SF_(v18[2], 16, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids);
        CredentialKey = -1073741811;
        goto LABEL_54;
      }
      v19 = MspDeserializeTbalCredential(*(unsigned __int8 **)(a3 + 24), v7, &v80, &v79);
      CredentialKey = v19;
      if ( v19 >= 0 )
      {
        v3 = v80;
        *((_QWORD *)v80 + 4) = LocalhostNtLmCredIsoObj::IsoObj;
        goto LABEL_54;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids,
          (unsigned int)v19);
LABEL_53:
      v3 = v80;
      goto LABEL_54;
    case 4:
      PrimaryCredentialFromStrongSupplementalCredential = NlpMakePrimaryCredentialFromStrongSupplementalCredential(
                                                            (PCUNICODE_STRING)(a2 + 24),
                                                            (PCUNICODE_STRING)(a2 + 8),
                                                            (__int64)&v79);
LABEL_52:
      CredentialKey = PrimaryCredentialFromStrongSupplementalCredential;
      goto LABEL_53;
    case -65534:
      PrimaryCredentialFromStrongSupplementalCredential = NlpMakePrimaryCredentialFromRemoteCred(
                                                            a2,
                                                            (int)a2 + 24,
                                                            (int)a2 + 8,
                                                            a3,
                                                            (__int64)&v80,
                                                            (__int64)&v79);
      goto LABEL_52;
  }
  v28 = *(_DWORD *)(a2 + 80);
  if ( (v28 & 0x20001) == 0 || v10 == 2 )
  {
    v42 = NlpMakePrimaryCredentialFromStrongSupplementalCredential(
            &SourceString,
            (PCUNICODE_STRING)(a2 + 8),
            (__int64)&v79);
    CredentialKey = v42;
    if ( v10 == -65535 )
    {
      if ( v42 < 0 )
      {
        if ( (unsigned int)dword_1800861D8 > 5
          && (qword_1800861E8 & 0x400000000000LL) != 0
          && (qword_1800861F0 & 0x400000000000LL) == qword_1800861F0 )
        {
          LOBYTE(v78) = (*(__int64 (__fastcall **)(struct NtlmCredIsoApi *))(*(_QWORD *)LocalhostNtLmCredIsoObj::IsoObj
                                                                           + 16LL))(LocalhostNtLmCredIsoObj::IsoObj);
          HighPart = v81.HighPart;
          HIDWORD(v78) = v81.LowPart;
          v105 = &v78;
          v103 = &v82;
          v97 = "SspAcceptCredentials";
          v91 = (__int16 *)off_1800861E0;
          p_HighPart = &HighPart;
          v99 = (char *)&v78 + 4;
          v82 = CredentialKey;
          v106 = 1;
          v104 = 4;
          v102 = 4;
          v100 = 4;
          v98 = 21;
          v88[0] = 0x50B000000LL;
          v88[1] = 0x400000000000LL;
          v92 = *(unsigned __int16 *)off_1800861E0;
          v94 = &dword_18007A324;
          v93 = 2;
          v95 = 121;
          v96 = 1;
          v84 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_1800861F8, v88, 0, 0, 7, &v91, v78);
        }
        v3 = v80;
        goto LABEL_124;
      }
      v3 = v80;
      goto LABEL_55;
    }
    goto LABEL_53;
  }
  v29 = *(_QWORD *)(a2 + 72);
  v30 = v28 & 0x20000;
  LOBYTE(v78) = v30 != 0;
  CredEncryptionTypeForUser = NlpGetCredEncryptionTypeForUser(v29, &v81, v8, v12);
  v32 = *(unsigned __int16 *)(a2 + 8);
  v33 = 0;
  HighPart = CredEncryptionTypeForUser;
  v34 = v32 + SourceString.Length + 388;
  v35 = ((_BYTE)v32 + LOBYTE(SourceString.Length) - 124) & 7;
  if ( v35 )
    v33 = 8 - v35;
  v36 = v33 + v34;
  v82 = v33 + v34;
  v37 = ((__int64 (__fastcall *)(_QWORD))qword_180088238)((unsigned int)(v33 + v34));
  memset_0((void *)v37, 0, v36);
  v38 = v37 + 384;
  *(_QWORD *)(v37 + 32) = LocalhostNtLmCredIsoObj::IsoObj;
  if ( SourceString.Length )
  {
    *(_QWORD *)(v37 + 8) = v38;
    *(_WORD *)(v37 + 2) = SourceString.Length + 2;
    RtlCopyUnicodeString((PUNICODE_STRING)v37, &SourceString);
    Length = SourceString.Length;
    *(_WORD *)(SourceString.Length + v38) = 0;
    v38 = Length + v37 + 386;
  }
  else
  {
    RtlInitUnicodeString((PUNICODE_STRING)v37, 0);
  }
  v40 = (struct _UNICODE_STRING *)(v37 + 16);
  if ( *(_WORD *)(a2 + 8) )
  {
    *(_QWORD *)(v37 + 24) = v38;
    *(_WORD *)(v37 + 18) = *(_WORD *)(a2 + 8) + 2;
    RtlCopyUnicodeString(v40, (PCUNICODE_STRING)(a2 + 8));
    *(_WORD *)(*(unsigned __int16 *)(a2 + 8) + v38) = 0;
  }
  else
  {
    RtlInitUnicodeString(v40, 0);
  }
  if ( v30 )
    v41 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64))(**(_QWORD **)(v37 + 32) + 144LL))(
            *(_QWORD *)(v37 + 32),
            *(unsigned __int16 *)(a2 + 40),
            *(_QWORD *)(a2 + 48),
            v37 + 32);
  else
    v41 = NlpPutOwfsInPrimaryCredential((int)a2 + 40, 0, (unsigned __int8)v78, HighPart, v37 + 32);
  CredentialKey = v41;
  if ( v41 < 0 )
  {
    if ( v37 )
      ((void (__fastcall *)(__int64))qword_180088240)(v37);
  }
  else
  {
    v3 = (struct _MSV1_0_PRIMARY_CREDENTIAL *)v37;
    v79 = v82;
  }
LABEL_54:
  if ( CredentialKey < 0 )
    goto LABEL_124;
LABEL_55:
  if ( !*((_QWORD *)v3 + 4) )
    *((_QWORD *)v3 + 4) = LocalhostNtLmCredIsoObj::IsoObj;
  if ( !*((_BYTE *)v3 + 43) )
  {
    if ( *((_BYTE *)v3 + 41) )
    {
      CredentialKey = MsvpGenerateCredentialKey(v3, *(void **)(a2 + 72));
      if ( CredentialKey < 0 )
        goto LABEL_124;
    }
  }
  v8 = *(unsigned int *)(a2 + 80);
  if ( (v8 & 4) != 0 )
  {
    if ( !BYTE4(v78) )
    {
      HIDWORD(v78) = 0;
      CredentialKey = NlpChangePwdCredByLogonId(&v81, (__int64)&v78 + 4);
      if ( HIDWORD(v78) )
      {
        RtlAcquireResourceExclusive(&NlpActiveLogonLock, 1u);
        ActiveLogon = NlpFindActiveLogon(&v81);
        v22 = ActiveLogon;
        if ( ActiveLogon )
        {
          v23 = *(_DWORD *)(ActiveLogon + 120);
          v24 = v23 | 0x40;
          v25 = v23 & 0xFFFFFFBF;
          if ( (*(_DWORD *)(a2 + 80) & 0x100) == 0 )
            v24 = v25;
          *(_DWORD *)(ActiveLogon + 120) = v24;
          v26 = v24 & 0xFFFFFF7F;
          v27 = v24 | 0x80;
          if ( (*(_DWORD *)(a2 + 80) & 0x10000) == 0 )
            v27 = v26;
          *(_DWORD *)(v22 + 120) = v27 & 0xFFFFFEFF;
        }
        RtlReleaseResource(&NlpActiveLogonLock);
      }
    }
    goto LABEL_124;
  }
  v43 = RtlLengthSid(*(PSID *)(a2 + 72));
  v44 = *(unsigned __int16 *)(a2 + 120);
  v45 = v43;
  v82 = v43;
  v84 = *(unsigned __int16 *)(a2 + 8) + v44 + ((v43 + 1) & 0xFFFFFFFE) + SourceString.Length + 142;
  v46 = ((__int64 (__fastcall *)(_QWORD))qword_180088390)(v84);
  v47 = v46;
  if ( !v46 )
  {
    CredentialKey = -1073741801;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 128, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids, v84);
    goto LABEL_124;
  }
  *(_DWORD *)(v46 + 40) = 1296847950;
  *(LUID *)(v46 + 44) = v81;
  v48 = 4;
  *(_DWORD *)(v47 + 120) = 4;
  v49 = *(_DWORD *)(a2 + 80);
  if ( (v49 & 0x100) != 0 )
  {
    v48 = 68;
    *(_DWORD *)(v47 + 120) = 68;
  }
  else if ( (v49 & 0x10000) != 0 )
  {
    *(_DWORD *)(v47 + 120) = 132;
    v48 = 132;
  }
  if ( BYTE4(v78) )
    *(_DWORD *)(v47 + 120) = v48 | 0x100;
  *(_DWORD *)(v47 + 56) = v85;
  v50 = *(void **)(a2 + 72);
  v80 = (struct _MSV1_0_PRIMARY_CREDENTIAL *)((v47 + 139) & 0xFFFFFFFFFFFFFFFCuLL);
  CredentialKey = RtlCopySid(v45, v80, v50);
  if ( CredentialKey < 0 )
  {
LABEL_123:
    ((void (__fastcall *)(__int64))qword_180088398)(v47);
    goto LABEL_124;
  }
  v51 = v80;
  v52 = v82;
  *(_QWORD *)(v47 + 64) = v80;
  v53 = (unsigned __int64)v51 + v52 + 1;
  v54 = (struct _UNICODE_STRING *)(v47 + 72);
  v55 = v53 & 0xFFFFFFFFFFFFFFFEuLL;
  if ( *(_WORD *)(a2 + 8) )
  {
    *(_QWORD *)(v47 + 80) = v55;
    *(_WORD *)(v47 + 74) = *(_WORD *)(a2 + 8) + 2;
    RtlCopyUnicodeString(v54, (PCUNICODE_STRING)(a2 + 8));
    v56 = *(unsigned __int16 *)(a2 + 8);
    *(_WORD *)(v56 + v55) = 0;
    v55 += v56 + 2;
  }
  else
  {
    RtlInitUnicodeString(v54, 0);
  }
  v57 = (struct _UNICODE_STRING *)(v47 + 88);
  if ( SourceString.Length )
  {
    *(_QWORD *)(v47 + 96) = v55;
    *(_WORD *)(v47 + 90) = SourceString.Length + 2;
    RtlCopyUnicodeString(v57, &SourceString);
    v58 = SourceString.Length;
    *(_WORD *)(SourceString.Length + v55) = 0;
    v55 += v58 + 2;
  }
  else
  {
    RtlInitUnicodeString(v57, 0);
  }
  v59 = (const UNICODE_STRING *)(a2 + 120);
  v60 = (struct _UNICODE_STRING *)(v47 + 104);
  if ( *(_WORD *)(a2 + 120) )
  {
    *(_QWORD *)(v47 + 112) = v55;
    *(_WORD *)(v47 + 106) = v59->Length + 2;
    RtlCopyUnicodeString(v60, v59);
    *(_WORD *)(*(unsigned __int16 *)(a2 + 120) + v55) = 0;
  }
  else
  {
    RtlInitUnicodeString(v60, 0);
  }
  RtlAcquireResourceShared(&NlpActiveLogonLock, 1u);
  v61 = NlpFindActiveLogon(&v81);
  if ( v61 )
  {
    if ( BYTE4(v78) || (*(_DWORD *)(v61 + 120) & 0x10B) != 0 )
    {
      RtlReleaseResource(&NlpActiveLogonLock);
      CredentialKey = 0;
    }
    else
    {
      RtlReleaseResource(&NlpActiveLogonLock);
      CredentialKey = -1073741563;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          129,
          WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids,
          *(unsigned int *)(v47 + 48),
          *(_DWORD *)(v47 + 44));
    }
    goto LABEL_123;
  }
  *(_DWORD *)(v47 + 52) = _InterlockedIncrement(&NlpEnumerationHandle);
  RtlConvertSharedToExclusive(&NlpActiveLogonLock);
  v63 = NlpActiveLogonTable;
  LOBYTE(v64) = 0;
  if ( !NlpActiveLogonTable )
    goto LABEL_137;
  while ( (int)NlpActiveLogonCompare((void *)(v47 + 44), v63) >= 0 )
  {
    v65 = v63->Children[1];
    if ( !v65 )
    {
      LOBYTE(v64) = 1;
      goto LABEL_137;
    }
LABEL_135:
    v63 = v65;
  }
  v65 = v63->Children[0];
  if ( v63->Children[0] )
    goto LABEL_135;
  LOBYTE(v64) = 0;
LABEL_137:
  RtlAvlInsertNodeEx(&NlpActiveLogonTable, v63, v64, v47 + 16);
  v66 = NlpActiveLogonListAnchor;
  if ( *(__int64 **)(NlpActiveLogonListAnchor + 8) != &NlpActiveLogonListAnchor )
    __fastfail(3u);
  *(_QWORD *)(v47 + 8) = &NlpActiveLogonListAnchor;
  *(_QWORD *)v47 = v66;
  *(_QWORD *)(v66 + 8) = v47;
  NlpActiveLogonListAnchor = v47;
  RtlReleaseResource(&NlpActiveLogonLock);
  v67 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    WPP_SF_dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      130,
      WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids,
      *(unsigned int *)(v47 + 48),
      *(_DWORD *)(v47 + 44));
    v67 = WPP_GLOBAL_Control;
  }
  if ( (*(_DWORD *)(a2 + 80) & 0x801) == 0x801 )
  {
LABEL_147:
    v70 = 0;
    v71 = 0;
    if ( v67 != &WPP_GLOBAL_Control && (*((_DWORD *)v67 + 7) & 0x4000) != 0 )
      WPP_SF_(v67[2], 131, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids);
    *(_DWORD *)(v47 + 120) |= 0x20u;
    LsaIEventWritePackageNotCacheLogonUser(v89, a2 + 8, a2 + 24, 1);
    v72 = *((_BYTE *)v3 + 43);
    if ( v72 )
    {
      v71 = *(_OWORD *)((char *)v3 + 50);
      v70 = *(_DWORD *)((char *)v3 + 66);
      v73 = *((_DWORD *)v3 + 11);
    }
    else
    {
      v73 = 0;
    }
    v74 = *((_QWORD *)v3 + 4);
    v75 = (char *)v3 + 32;
    v76 = 352;
    do
    {
      *v75++ = 0;
      --v76;
    }
    while ( v76 );
    *((_QWORD *)v3 + 4) = v74;
    if ( v72 )
    {
      *(_OWORD *)((char *)v3 + 50) = v71;
      *(_DWORD *)((char *)v3 + 66) = v70;
      *((_BYTE *)v3 + 43) = 1;
      *((_DWORD *)v3 + 11) = v73;
    }
  }
  else
  {
    v68 = v88[0];
    v69 = MsvpValidateSupplementalCreds(v88[0]);
    if ( (v69 & 0xFFFFFFF9) == 0 && v69 != 6 && (*(_BYTE *)(*(_QWORD *)(v68 + 24) + 4LL) & 4) != 0 )
    {
      v67 = WPP_GLOBAL_Control;
      goto LABEL_147;
    }
  }
  v77 = NlpAddPrimaryCredential(&v81, v3, v79);
  CredentialKey = v77;
  if ( v77 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        132,
        WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids,
        (unsigned int)v77);
    LsaApLogonTerminated(&v81);
  }
LABEL_124:
  if ( v3 )
  {
    memset_0(v3, 0, v79);
    ((void (__fastcall *)(struct _MSV1_0_PRIMARY_CREDENTIAL *))LsaFunctions->FreeLsaHeap)(v3);
  }
LABEL_126:
  if ( v90.Buffer )
    ((void (__fastcall *)(PWSTR, __int64, __int64, __int64))LsaFunctions->FreePrivateHeap)(v90.Buffer, v7, v8, v12);
  return (unsigned int)CredentialKey;
}

```

## disassembly

```asm
0x1800193e0  mov     [rsp-8+arg_0], rbx
0x1800193e5  push    rbp
0x1800193e6  push    rsi
0x1800193e7  push    rdi
0x1800193e8  push    r12
0x1800193ea  push    r13
0x1800193ec  push    r14
0x1800193ee  push    r15
0x1800193f0  lea     rbp, [rsp-450h]
0x1800193f8  sub     rsp, 550h
0x1800193ff  mov     rax, cs:__security_cookie
0x180019406  xor     rax, rsp
0x180019409  mov     [rbp+480h+var_50], rax
0x180019410  xor     r15d, r15d
0x180019413  mov     [rsp+580h+var_524], ecx
0x180019417  xorps   xmm0, xmm0
0x18001941a  mov     [rsp+580h+var_540], r15
0x18001941f  xorps   xmm1, xmm1
0x180019422  mov     [rsp+580h+var_54C+4], r15d
0x180019427  lea     rax, pszPackageName; "NTLM"
0x18001942e  mov     [rsp+580h+var_510], r15d
0x180019433  mov     rcx, r8
0x180019436  mov     [rbp+480h+var_4F0], rax
0x18001943a  mov     edi, r15d
0x18001943d  mov     [rsp+580h+var_538], r15
0x180019442  movups  xmmword ptr [rsp+580h+SourceString.Length], xmm0
0x180019447  mov     r12, r8
0x18001944a  mov     [rsp+580h+var_508], r8
0x18001944f  movups  [rbp+480h+var_4E0], xmm1
0x180019453  mov     r14, rdx
0x180019456  mov     [rbp+480h+var_4F8], 0A0008h
0x18001945e  call    cs:__imp_MsvpValidateSupplementalCreds
0x180019464  mov     edx, [r14+50h]
0x180019468  xor     r8b, r8b
0x18001946b  mov     rcx, [r14]
0x18001946e  bt      edx, 0Ch
0x180019472  mov     esi, eax
0x180019474  mov     [rsp+580h+var_54C], r8d
0x180019479  mov     rax, r14
0x18001947c  mov     [rsp+580h+var_538], rcx
0x180019481  cmovnb  rax, r15
0x180019485  mov     r9d, 1
0x18001948b  test    edx, 20001h
0x180019491  jnz     short loc_1800194C3
0x180019493  cmp     esi, 0FFFFFFFFh
0x180019496  jnz     short loc_1800194E2
0x180019498  bt      edx, 10h
0x18001949c  jnb     short loc_1800194BB
0x18001949e  test    edx, 108000h
0x1800194a4  jnz     short loc_1800194B4
0x1800194a6  test    rax, rax
0x1800194a9  jz      short loc_1800194BB
0x1800194ab  test    [rax+0D8h], r9b
0x1800194b2  jz      short loc_1800194BB
0x1800194b4  mov     byte ptr [rsp+580h+var_54C], r9b
0x1800194b9  jmp     short loc_1800194E2
0x1800194bb  mov     ebx, r15d
0x1800194be  jmp     loc_180019E62
0x1800194c3  and     edx, 10001h
0x1800194c9  cmp     edx, 10001h
0x1800194cf  jnz     short loc_1800194E2
0x1800194d1  cmp     [r14+30h], rdi
0x1800194d5  movzx   r8d, r8b
0x1800194d9  cmovz   r8d, r9d
0x1800194dd  mov     [rsp+580h+var_54C], r8d
0x1800194e2  cmp     ecx, 3E7h
0x1800194e8  jnz     short loc_180019501
0x1800194ea  mov     rax, rcx
0x1800194ed  shr     rax, 20h
0x1800194f1  test    eax, eax
0x1800194f3  jnz     short loc_180019501
0x1800194f5  mov     rax, qword ptr cs:NtLmGlobalLuidMachineLogon.LowPart
0x1800194fc  mov     [rsp+580h+var_538], rax
0x180019501  cmp     cs:NtLmLocklessGlobalPreferredDomainString.Buffer, rdi
0x180019508  jz      short loc_180019518
0x18001950a  movups  xmm0, xmmword ptr cs:NtLmLocklessGlobalPreferredDomainString.Length
0x180019511  movaps  xmmword ptr [rsp+580h+SourceString.Length], xmm0
0x180019516  jmp     short loc_180019585
0x180019518  mov     rax, rcx
0x18001951b  shr     rax, 20h
0x18001951f  cmp     ecx, 3E7h
0x180019525  jnz     short loc_18001952B
0x180019527  test    eax, eax
0x180019529  jz      short loc_180019537
0x18001952b  cmp     ecx, 3E4h
0x180019531  jnz     short loc_18001957B
0x180019533  test    eax, eax
0x180019535  jnz     short loc_18001957B
0x180019537  movzx   edx, r9b; Wait
0x18001953b  lea     rcx, NtLmGlobalCritSect; Resource
0x180019542  call    cs:__imp_RtlAcquireResourceShared
0x180019548  lea     rdx, NtLmGlobalUnicodePrimaryDomainNameString
0x18001954f  lea     rcx, [rbp+480h+var_4E0]
0x180019553  call    NtLmDuplicateUnicodeString
0x180019558  lea     rcx, NtLmGlobalCritSect; Resource
0x18001955f  mov     ebx, eax
0x180019561  call    cs:__imp_RtlReleaseResource
0x180019567  test    ebx, ebx
0x180019569  js      loc_180019E62
0x18001956f  movaps  xmm0, [rbp+480h+var_4E0]
0x180019573  movdqa  xmmword ptr [rsp+580h+SourceString.Length], xmm0
0x180019579  jmp     short loc_180019585
0x18001957b  movups  xmm0, xmmword ptr [r14+18h]
0x180019580  movups  xmmword ptr [rsp+580h+SourceString.Length], xmm0
0x180019585  movzx   ecx, word ptr [r14+8]
0x18001958a  mov     eax, 400h
0x18001958f  cmp     cx, ax
0x180019592  jnb     short loc_18001959E
0x180019594  mov     eax, ecx
0x180019596  test    ecx, ecx
0x180019598  jz      loc_18001966A
0x18001959e  mov     rdx, [r14+10h]; Src
0x1800195a2  lea     rcx, [rbp+480h+var_460]; void *
0x1800195a6  mov     r8d, eax; Size
0x1800195a9  mov     ebx, eax
0x1800195ab  call    memcpy_0
0x1800195b0  mov     eax, ebx
0x1800195b2  shr     rax, 1
0x1800195b5  cmp     [rbp+rax*2+480h+var_460], di
0x1800195ba  jz      short loc_1800195D3
0x1800195bc  and     rbx, 0FFFFFFFFFFFFFFFEh
0x1800195c0  cmp     rbx, 402h
0x1800195c7  jnb     loc_18001A0E1
0x1800195cd  mov     [rbp+rbx+480h+var_460], r15w
0x1800195d3  lea     r9, [rsp+580h+var_510]
0x1800195d8  xor     r8d, r8d
0x1800195db  xor     edx, edx
0x1800195dd  lea     rcx, [rbp+480h+var_460]
0x1800195e1  call    cs:__imp_CredParseUserNameWithType
0x1800195e7  mov     ebx, eax
0x1800195e9  test    eax, eax
0x1800195eb  jns     short loc_18001962B
0x1800195ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800195f4  lea     r15, WPP_GLOBAL_Control
0x1800195fb  cmp     rcx, r15
0x1800195fe  jz      loc_180019E62
0x180019604  test    byte ptr [rcx+1Ch], 1
0x180019608  jz      loc_180019E62
0x18001960e  mov     rcx, [rcx+10h]
0x180019612  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x180019619  mov     edx, 7Eh ; '~'
0x18001961e  mov     r9d, eax
0x180019621  call    WPP_SF_d
0x180019626  jmp     loc_180019E62
0x18001962b  cmp     [rsp+580h+var_510], 3
0x180019630  jnz     short loc_18001966A
0x180019632  mov     rcx, cs:WPP_GLOBAL_Control
0x180019639  lea     r15, WPP_GLOBAL_Control
0x180019640  cmp     rcx, r15
0x180019643  jz      short loc_180019660
0x180019645  test    byte ptr [rcx+1Ch], 2
0x180019649  jz      short loc_180019660
0x18001964b  mov     rcx, [rcx+10h]
0x18001964f  lea     r8, WPP_007385984b1d3cf5efa72758d98c23d6_Traceguids
0x180019656  mov     edx, 7Fh
0x18001965b  call    WPP_SF_
0x180019660  mov     ebx, 0C00000BBh
0x180019665  jmp     loc_180019E62
0x18001966a  lea     r15, WPP_GLOBAL_Control
0x180019671  cmp     esi, 0FFFF0003h
0x180019677  jnz     loc_18001973A
0x18001967d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019684  cmp     rcx, r15
0x180019687  jz      short loc_1800196AE
0x180019689  test    dword ptr [rcx+1Ch], 4000h
0x180019690  jz      short loc_1800196AE
0x180019692  mov     rcx, [rcx+10h]
0x180019696  lea     r8, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids
0x18001969d  mov     edx, 0Fh
0x1800196a2  call    WPP_SF_
0x1800196a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800196ae  mov     edx, [r12+10h]; unsigned int
0x1800196b3  cmp     edx, 70h ; 'p'
0x1800196b6  jnb     short loc_1800196E2
0x1800196b8  cmp     rcx, r15
0x1800196bb  jz      short loc_1800196D8
0x1800196bd  test    byte ptr [rcx+1Ch], 1
0x1800196c1  jz      short loc_1800196D8
0x1800196c3  mov     rcx, [rcx+10h]
0x1800196c7  lea     r8, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids
0x1800196ce  mov     edx, 10h
0x1800196d3  call    WPP_SF_
0x1800196d8  mov     ebx, 0C000000Dh
0x1800196dd  jmp     loc_180019769
0x1800196e2  mov     rcx, [r12+18h]; unsigned __int8 *
0x1800196e7  lea     r9, [rsp+580h+var_54C+4]; unsigned int *
0x1800196ec  lea     r8, [rsp+580h+var_540]; struct _MSV1_0_PRIMARY_CREDENTIAL **
0x1800196f1  call    ?MspDeserializeTbalCredential@@YAJPEAEKPEAPEAU_MSV1_0_PRIMARY_CREDENTIAL@@PEAK@Z; MspDeserializeTbalCredential(uchar *,ulong,_MSV1_0_PRIMARY_CREDENTIAL * *,ulong *)
0x1800196f6  mov     ebx, eax
0x1800196f8  test    eax, eax
0x1800196fa  jns     short loc_180019728
0x1800196fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180019703  cmp     rcx, r15
0x180019706  jz      short loc_180019764
0x180019708  test    byte ptr [rcx+1Ch], 1
0x18001970c  jz      short loc_180019764
0x18001970e  mov     rcx, [rcx+10h]
0x180019712  lea     r8, WPP_392ea864dd3e33f07e463c681f7a5069_Traceguids
0x180019719  mov     edx, 11h
0x18001971e  mov     r9d, eax
0x180019721  call    WPP_SF_d
0x180019726  jmp     short loc_180019764
0x180019728  mov     rdi, [rsp+580h+var_540]
0x18001972d  mov     rax, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x180019734  mov     [rdi+20h], rax
0x180019738  jmp     short loc_180019769
0x18001973a  cmp     esi, 4
0x18001973d  jnz     loc_180019874
0x180019743  lea     rax, [rsp+580h+var_54C+4]
0x180019748  mov     r8, r12
0x18001974b  lea     rcx, [r14+18h]; SourceString
0x18001974f  mov     [rsp+580h+var_560], rax; __int64
0x180019754  lea     r9, [rsp+580h+var_540]
0x180019759  lea     rdx, [r14+8]; PCUNICODE_STRING
0x18001975d  call    NlpMakePrimaryCredentialFromStrongSupplementalCredential
0x180019762  mov     ebx, eax
0x180019764  mov     rdi, [rsp+580h+var_540]
0x180019769  test    ebx, ebx
0x18001976b  js      loc_180019E3B
0x180019771  cmp     qword ptr [rdi+20h], 0
0x180019776  jnz     short loc_180019783
0x180019778  mov     rax, cs:?IsoObj@LocalhostNtLmCredIsoObj@@0PEAVNtlmCredIsoApi@@EA; NtlmCredIsoApi * LocalhostNtLmCredIsoObj::IsoObj
0x18001977f  mov     [rdi+20h], rax
0x180019783  cmp     byte ptr [rdi+2Bh], 0
0x180019787  jnz     short loc_1800197A5
0x180019789  cmp     byte ptr [rdi+29h], 0
0x18001978d  jz      short loc_1800197A5
0x18001978f  mov     rdx, [r14+48h]; void *
0x180019793  mov     rcx, rdi; struct _MSV1_0_PRIMARY_CREDENTIAL *
0x180019796  call    ?MsvpGenerateCredentialKey@@YAJPEAU_MSV1_0_PRIMARY_CREDENTIAL@@PEAX@Z; MsvpGenerateCredentialKey(_MSV1_0_PRIMARY_CREDENTIAL *,void *)
0x18001979b  mov     ebx, eax
0x18001979d  test    eax, eax
0x18001979f  js      loc_180019E3B
0x1800197a5  mov     r8d, [r14+50h]
0x1800197a9  test    r8b, 4
0x1800197ad  jz      loc_180019BCC
0x1800197b3  cmp     byte ptr [rsp+580h+var_54C], 0
0x1800197b8  jnz     loc_180019E3B
0x1800197be  test    r8d, 10100h
0x1800197c5  mov     [rsp+580h+var_54C], 0
0x1800197cd  mov     r9d, 0
0x1800197d3  lea     rax, [rsp+580h+var_54C]
0x1800197d8  not     r8d
0x1800197db  mov     [rsp+580h+var_560], rax; __int64
0x1800197e0  setz    r9b
0x1800197e4  lea     rcx, [rsp+580h+var_538]; void *
0x1800197e9  and     r8d, 1
0x1800197ed  mov     rdx, rdi
0x1800197f0  call    NlpChangePwdCredByLogonId
0x1800197f5  cmp     [rsp+580h+var_54C], 0
0x1800197fa  mov     ebx, eax
0x1800197fc  jz      loc_180019E3B
0x180019802  mov     dl, 1; Wait
0x180019804  lea     rcx, NlpActiveLogonLock; Resource
0x18001980b  call    cs:__imp_RtlAcquireResourceExclusive
0x180019811  lea     rcx, [rsp+580h+var_538]; void *
0x180019816  call    NlpFindActiveLogon
0x18001981b  mov     r9, rax
0x18001981e  test    rax, rax
0x180019821  jz      short loc_180019862
0x180019823  mov     r8d, [rax+78h]
0x180019827  mov     ecx, r8d
0x18001982a  or      r8d, 40h
0x18001982e  and     ecx, 0FFFFFFBFh
0x180019831  test    dword ptr [r14+50h], 100h
0x180019839  cmovz   r8d, ecx
0x18001983d  mov     [rax+78h], r8d
0x180019841  mov     eax, r8d
0x180019844  btr     eax, 7
0x180019848  bts     r8d, 7
0x18001984d  test    dword ptr [r14+50h], 10000h
0x180019855  cmovz   r8d, eax
0x180019859  btr     r8d, 8
0x18001985e  mov     [r9+78h], r8d
0x180019862  lea     rcx, NlpActiveLogonLock; Resource
0x180019869  call    cs:__imp_RtlReleaseResource
0x18001986f  jmp     loc_180019E3B
0x180019874  cmp     esi, 0FFFF0002h
0x18001987a  jnz     short loc_1800198A8
0x18001987c  lea     rax, [rsp+580h+var_54C+4]
0x180019881  mov     r9, r12
0x180019884  mov     [rsp+580h+var_558], rax
0x180019889  lea     rdx, [r14+18h]
0x18001988d  lea     rax, [rsp+580h+var_540]
0x180019892  mov     rcx, r14
0x180019895  lea     r8, [r14+8]
0x180019899  mov     [rsp+580h+var_560], rax
0x18001989e  call    NlpMakePrimaryCredentialFromRemoteCred
0x1800198a3  jmp     loc_180019762
0x1800198a8  mov     r12d, [r14+50h]
0x1800198ac  test    r12d, 20001h
0x1800198b3  jz      loc_180019A36
0x1800198b9  cmp     esi, 2
0x1800198bc  jz      loc_180019A36
0x1800198c2  mov     rcx, [r14+48h]
0x1800198c6  lea     rdx, [rsp+580h+var_538]
0x1800198cb  and     r12d, 20000h
0x1800198d2  setnz   [rsp+580h+var_550]
0x1800198d7  call    NlpGetCredEncryptionTypeForUser
0x1800198dc  movzx   edx, word ptr [r14+8]
  ... truncated ...
```
