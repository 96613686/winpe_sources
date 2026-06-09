# SspiEncodeAuthIdentityAsStrings

- ea: `0x1800092d0`
- end: `0x18000a069`
- name: `SspiEncodeAuthIdentityAsStrings`
- size: `3481`
- prototype: `SECURITY_STATUS __stdcall(PSEC_WINNT_AUTH_IDENTITY_OPAQUE pAuthIdentity, PCWSTR *ppszUserName, PCWSTR *ppszDomainName, PCWSTR *ppszPackedCredentialsString)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180008a40`
- `0x18000a6d0`

## callees

- `0x180004050`
- `0x180006830`
- `0x180007fc4`
- `0x18000800c`
- `0x1800081c4`
- `0x1800087e8`
- `0x180008a04`
- `0x1800092d0`
- `0x180010980`

## import_xrefs

- `ntoskrnl!wcschr` at `0x180009e99`
- `ntoskrnl!wcschr` at `0x180009e99`
- `ntoskrnl!ExAllocatePool2` at `0x1800093c6`
- `ntoskrnl!ExAllocatePool2` at `0x18000944d`
- `ntoskrnl!ExAllocatePool2` at `0x1800094ca`
- `ntoskrnl!ExAllocatePool2` at `0x18000952e`
- `ntoskrnl!ExAllocatePool2` at `0x180009697`
- `ntoskrnl!ExAllocatePool2` at `0x1800096fc`
- `ntoskrnl!ExAllocatePool2` at `0x180009754`
- `ntoskrnl!ExAllocatePool2` at `0x1800098b1`
- `ntoskrnl!ExAllocatePool2` at `0x1800098fc`
- `ntoskrnl!ExAllocatePool2` at `0x180009952`
- `ntoskrnl!ExAllocatePool2` at `0x1800099a4`
- `ntoskrnl!ExAllocatePool2` at `0x180009a6d`
- `ntoskrnl!ExAllocatePool2` at `0x180009b17`
- `ntoskrnl!ExAllocatePool2` at `0x180009b94`
- `ntoskrnl!ExAllocatePool2` at `0x180009c05`
- `ntoskrnl!ExAllocatePool2` at `0x180009c9a`
- `ntoskrnl!ExAllocatePool2` at `0x180009ee4`
- `ntoskrnl!ExAllocatePool2` at `0x180009f53`
- `ntoskrnl!ExAllocatePool2` at `0x1800093c6`
- `ntoskrnl!ExAllocatePool2` at `0x18000944d`
- `ntoskrnl!ExAllocatePool2` at `0x1800094ca`
- `ntoskrnl!ExAllocatePool2` at `0x18000952e`
- `ntoskrnl!ExAllocatePool2` at `0x180009697`
- `ntoskrnl!ExAllocatePool2` at `0x1800096fc`
- `ntoskrnl!ExAllocatePool2` at `0x180009754`
- `ntoskrnl!ExAllocatePool2` at `0x1800098b1`
- `ntoskrnl!ExAllocatePool2` at `0x1800098fc`
- `ntoskrnl!ExAllocatePool2` at `0x180009952`
- `ntoskrnl!ExAllocatePool2` at `0x1800099a4`
- `ntoskrnl!ExAllocatePool2` at `0x180009a6d`
- `ntoskrnl!ExAllocatePool2` at `0x180009b17`
- `ntoskrnl!ExAllocatePool2` at `0x180009b94`
- `ntoskrnl!ExAllocatePool2` at `0x180009c05`
- `ntoskrnl!ExAllocatePool2` at `0x180009c9a`
- `ntoskrnl!ExAllocatePool2` at `0x180009ee4`
- `ntoskrnl!ExAllocatePool2` at `0x180009f53`

## pseudocode

```c
SECURITY_STATUS __stdcall SspiEncodeAuthIdentityAsStrings(
        PSEC_WINNT_AUTH_IDENTITY_OPAQUE pAuthIdentity,
        PCWSTR *ppszUserName,
        PCWSTR *ppszDomainName,
        PCWSTR *ppszPackedCredentialsString)
{
  PVOID *v4; // rsi
  PVOID *v5; // r14
  PCWSTR *v6; // rbx
  char *v8; // r13
  unsigned __int16 *v9; // r15
  _BYTE *v11; // r12
  int v12; // edx
  unsigned int v13; // ecx
  int v14; // ebx
  char *v15; // rcx
  __int64 v16; // rax
  char *v17; // rcx
  __int64 v18; // rsi
  WCHAR *v19; // rax
  int v20; // eax
  __int64 v21; // rbx
  WCHAR *v22; // rax
  __int64 v23; // rdx
  _WORD *v24; // rax
  _WORD *v25; // rdx
  int v26; // eax
  _WORD *v27; // rbx
  char *v28; // rcx
  int v29; // eax
  unsigned int v30; // esi
  WCHAR *v31; // rax
  WCHAR *v32; // rax
  void *v33; // rax
  BOOL v34; // esi
  char *v35; // r14
  int v36; // ecx
  CHAR *v37; // rax
  CHAR *v38; // rcx
  CHAR *v39; // rcx
  unsigned __int16 *v40; // rax
  unsigned int v41; // r12d
  WCHAR *v42; // rax
  WCHAR *v43; // rax
  unsigned __int16 *v44; // rax
  void *v45; // rax
  PCWSTR v46; // rax
  __int64 v47; // r15
  __int64 v48; // rdi
  __int64 v49; // rdx
  void *Pool2; // rax
  char *v51; // rcx
  size_t v52; // rbx
  char *v53; // rcx
  WCHAR *v54; // rax
  int v55; // eax
  __int64 v56; // rbx
  WCHAR *v57; // rax
  __int64 v58; // rdx
  _WORD *v59; // rax
  _WORD *v60; // rdx
  __int16 v61; // ax
  __int64 v62; // rax
  unsigned int v63; // edx
  unsigned int v64; // r15d
  _WORD *v65; // rax
  _WORD *v66; // rdx
  int v67; // eax
  PVOID v68; // rcx
  char *v69; // rdi
  int v70; // eax
  WCHAR *v71; // rbx
  PCWSTR *v72; // rdi
  wchar_t *v73; // rax
  __int64 v74; // rsi
  _WORD *v75; // r14
  __int64 v76; // rdi
  WCHAR *v77; // rax
  WCHAR *v78; // rax
  __int64 v79; // rdx
  _BYTE *v80; // rax
  PVOID v81; // rcx
  __int64 v82; // rdx
  _BYTE *v83; // rax
  unsigned __int16 *v84; // rdx
  __int64 i; // rax
  unsigned __int16 *v86; // [rsp+28h] [rbp-49h]
  _WORD *v87; // [rsp+30h] [rbp-41h]
  void *Src; // [rsp+38h] [rbp-39h] BYREF
  PVOID v89; // [rsp+40h] [rbp-31h]
  unsigned __int16 *v90; // [rsp+48h] [rbp-29h] BYREF
  __int64 v91; // [rsp+50h] [rbp-21h]
  unsigned __int16 *v92; // [rsp+58h] [rbp-19h] BYREF
  _WORD *v93; // [rsp+60h] [rbp-11h]
  PVOID v94; // [rsp+68h] [rbp-9h]
  __int64 v95; // [rsp+70h] [rbp-1h]
  PVOID v96; // [rsp+78h] [rbp+7h] BYREF
  PVOID DataBuffer; // [rsp+80h] [rbp+Fh]
  unsigned int Size; // [rsp+D8h] [rbp+67h]

  v4 = (PVOID *)ppszDomainName;
  v5 = (PVOID *)ppszPackedCredentialsString;
  v6 = ppszUserName;
  Src = 0;
  v94 = 0;
  v8 = 0;
  v90 = 0;
  v9 = 0;
  v86 = 0;
  v92 = 0;
  v96 = 0;
  if ( !pAuthIdentity )
    return -1073741811;
  *ppszUserName = 0;
  v11 = 0;
  *ppszDomainName = 0;
  v87 = 0;
  DataBuffer = 0;
  LODWORD(v91) = 24;
  Size = 0;
  v89 = 0;
  LODWORD(v95) = 0;
  if ( ppszPackedCredentialsString )
    *ppszPackedCredentialsString = 0;
  if ( *(_DWORD *)pAuthIdentity != 513 )
  {
    v34 = 0;
    if ( *(_DWORD *)pAuthIdentity == 512 )
    {
      v35 = (char *)pAuthIdentity + 8;
      if ( ppszPackedCredentialsString )
        v34 = *((_DWORD *)pAuthIdentity + 16) != 0;
    }
    else
    {
      v35 = (char *)pAuthIdentity;
    }
    v36 = *((_DWORD *)v35 + 11);
    if ( (v36 & 0x10) != 0 )
    {
      v14 = -1073741811;
LABEL_69:
      v4 = (PVOID *)ppszDomainName;
      v5 = (PVOID *)ppszPackedCredentialsString;
      goto LABEL_35;
    }
    v37 = *(CHAR **)v35;
    if ( (v36 & 1) != 0 )
    {
      if ( v37 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(
                *(CHAR **)v35,
                *((_DWORD *)v35 + 2),
                (unsigned __int16 **)ppszUserName);
        if ( v14 < 0 )
          goto LABEL_31;
      }
      v38 = (CHAR *)*((_QWORD *)v35 + 2);
      if ( v38 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(v38, *((_DWORD *)v35 + 6), (unsigned __int16 **)ppszDomainName);
        if ( v14 < 0 )
          goto LABEL_31;
      }
      if ( ppszPackedCredentialsString && (v39 = (CHAR *)*((_QWORD *)v35 + 4)) != 0 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(v39, *((_DWORD *)v35 + 10), &v92);
        if ( v14 < 0 )
        {
          v9 = v92;
LABEL_135:
          v11 = 0;
          goto LABEL_69;
        }
        v40 = v92;
        v86 = v92;
      }
      else
      {
        v40 = 0;
      }
      if ( v34 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(
                *((CHAR **)pAuthIdentity + 7),
                *((_DWORD *)pAuthIdentity + 16),
                &v90);
        v94 = v90;
        if ( v14 < 0 )
          goto LABEL_31;
        v41 = *((_DWORD *)pAuthIdentity + 16);
        v6 = ppszUserName;
LABEL_97:
        v46 = *v6;
        v18 = -1;
        HIDWORD(v92) = 0;
        if ( v46 )
        {
          v47 = -1;
          do
            ++v47;
          while ( v46[v47] );
        }
        else
        {
          LODWORD(v47) = 0;
        }
        if ( *ppszDomainName )
        {
          v48 = -1;
          do
            ++v48;
          while ( (*ppszDomainName)[v48] );
        }
        else
        {
          LODWORD(v48) = 0;
        }
        if ( v86 )
        {
          v49 = -1;
          do
            ++v49;
          while ( v86[v49] );
        }
        else
        {
          v49 = 0;
        }
        v95 = v49;
        if ( (unsigned int)v47 > 0x7FFD || (unsigned int)v48 > 0x7FFD || (unsigned int)v49 > 0x7FFD )
          goto LABEL_141;
        Pool2 = (void *)ExAllocatePool2(256, (unsigned int)(2 * (v48 + v47) + 4) + 2LL, 1230267731);
        v89 = Pool2;
        if ( Pool2 )
        {
          v51 = (char *)Pool2;
          if ( (_DWORD)v48 )
          {
            v52 = 2LL * (unsigned int)v48;
            memmove(Pool2, *ppszDomainName, v52);
            v53 = (char *)v89 + 2;
            *(_WORD *)((char *)v89 + v52) = 92;
            v51 = &v53[v52];
          }
          memmove(v51, *ppszUserName, 2LL * (unsigned int)v47);
          v90 = (unsigned __int16 *)v89;
          if ( *ppszDomainName )
          {
            SspiLocalFree((PVOID)*ppszDomainName);
            *ppszDomainName = 0;
          }
          if ( *ppszUserName )
          {
            SspiLocalFree((PVOID)*ppszUserName);
            *ppszUserName = 0;
          }
          if ( (_DWORD)v47 || (_DWORD)v48 )
          {
            v55 = LocalCredMarshalCredentialW(4, &v90, &Src);
            v8 = (char *)Src;
            if ( v55 )
            {
              v14 = -1073741670;
              goto LABEL_31;
            }
            v56 = -1;
            do
              ++v56;
            while ( *((_WORD *)Src + v56) );
            v57 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * v56 + 2) + 2LL, 1230267731);
            *ppszUserName = v57;
            if ( !v57 )
              goto LABEL_30;
            memmove(v57, v8, 2LL * (unsigned int)v56);
          }
          else
          {
            v54 = (WCHAR *)ExAllocatePool2(256, 12, 1230267731);
            *ppszUserName = v54;
            if ( !v54 )
              goto LABEL_30;
            *(_QWORD *)v54 = 0x40004000400040LL;
          }
          v9 = v86;
          if ( v86 )
          {
            v58 = (unsigned int)(2 * v95 + 32);
            Size = v58;
            if ( (unsigned int)v58 >= 0xFFFF )
            {
              v14 = -1073741811;
              goto LABEL_135;
            }
            v59 = (_WORD *)ExAllocatePool2(256, v58 + 2, 1230267731);
            DataBuffer = v59;
            v60 = v59;
            if ( !v59 )
            {
              v14 = -1073741801;
              goto LABEL_135;
            }
            *v59 = 28;
            v59[1] = Size;
            v61 = v95;
            *((_DWORD *)v60 + 5) = 28;
            v62 = (unsigned __int16)(2 * v61);
            v60[12] = v62;
            *(_OWORD *)(v60 + 2) = SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
            memmove(v60 + 14, v86, (unsigned __int16)v62);
            v63 = Size;
          }
          else
          {
            v63 = 0;
            Size = 0;
          }
          v64 = v63 + 2 * (v41 + 12);
          LODWORD(v91) = v64;
          if ( v64 >= 0xFFFF )
          {
LABEL_141:
            v14 = -1073741811;
            goto LABEL_31;
          }
          v65 = (_WORD *)ExAllocatePool2(256, v64 + 2LL, 1230267731);
          v87 = v65;
          v66 = v65;
          if ( v65 )
          {
            *v65 = 24;
            v67 = *((_DWORD *)v35 + 11);
            *((_DWORD *)v66 + 1) = v67;
            if ( !*((_QWORD *)v35 + 2) )
            {
              v67 |= 0x40000u;
              *((_DWORD *)v66 + 1) = v67;
            }
            if ( !*(_QWORD *)v35 )
              *((_DWORD *)v66 + 1) = v67 | 0x20000;
            v68 = DataBuffer;
            v69 = (char *)(v66 + 12);
            if ( DataBuffer )
            {
              *((_DWORD *)v66 + 2) = 24;
              v66[6] = Size;
              memmove(v69, v68, Size);
              v66 = v87;
              v69 += Size;
            }
            if ( v41 )
            {
              v66[10] = v41;
              *((_DWORD *)v66 + 4) = (_DWORD)v69 - (_DWORD)v66;
              memmove(v69, v94, 2LL * v41);
            }
            v11 = v87;
            LODWORD(v92) = v64;
            v93 = v87;
            if ( v8 )
            {
              SspiLocalFree(v8);
              Src = 0;
            }
            v70 = LocalCredMarshalCredentialW(3, &v92, &Src);
            v8 = (char *)Src;
            if ( !v70 )
            {
              do
                ++v18;
              while ( *((_WORD *)Src + v18) );
              if ( (unsigned int)v18 > 8 )
                goto LABEL_51;
              goto LABEL_55;
            }
            goto LABEL_22;
          }
        }
LABEL_30:
        v14 = -1073741801;
LABEL_31:
        v11 = v87;
        goto LABEL_32;
      }
      v6 = ppszUserName;
    }
    else
    {
      if ( v37 )
      {
        v42 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * *((_DWORD *)v35 + 2) + 2) + 2LL, 1230267731);
        *v6 = v42;
        if ( !v42 )
          goto LABEL_30;
        memmove(v42, *(const void **)v35, 2LL * *((unsigned int *)v35 + 2));
      }
      if ( *((_QWORD *)v35 + 2) )
      {
        v43 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * *((_DWORD *)v35 + 6) + 2) + 2LL, 1230267731);
        *ppszDomainName = v43;
        if ( !v43 )
          goto LABEL_30;
        memmove(v43, *((const void **)v35 + 2), 2LL * *((unsigned int *)v35 + 6));
      }
      if ( ppszPackedCredentialsString && *((_QWORD *)v35 + 4) )
      {
        v44 = (unsigned __int16 *)ExAllocatePool2(256, (unsigned int)(2 * *((_DWORD *)v35 + 10) + 2) + 2LL, 1230267731);
        v86 = v44;
        if ( !v44 )
          goto LABEL_30;
        memmove(v44, *((const void **)v35 + 4), 2LL * *((unsigned int *)v35 + 10));
      }
      if ( v34 )
      {
        v41 = *((_DWORD *)pAuthIdentity + 16);
        v45 = (void *)ExAllocatePool2(256, 2 * v41 + 2 + 2LL, 1230267731);
        v94 = v45;
        if ( !v45 )
          goto LABEL_30;
        memmove(v45, *((const void **)pAuthIdentity + 7), 2LL * *((unsigned int *)pAuthIdentity + 16));
        goto LABEL_97;
      }
      v40 = v86;
    }
    v5 = (PVOID *)ppszPackedCredentialsString;
    if ( ppszPackedCredentialsString )
    {
      v11 = 0;
      v9 = 0;
      *ppszPackedCredentialsString = v40;
      goto LABEL_191;
    }
    v4 = (PVOID *)ppszDomainName;
    if ( !*ppszDomainName || !**ppszDomainName )
    {
      v71 = (WCHAR *)*v6;
      LODWORD(Src) = 0;
      if ( SspiHelperIsEncodedNullUserName(v71) )
      {
        if ( v71 )
        {
          SspiLocalFree(v71);
          *ppszUserName = 0;
        }
        if ( *ppszDomainName )
        {
          SspiLocalFree((PVOID)*ppszDomainName);
          *ppszDomainName = 0;
        }
        goto LABEL_189;
      }
      if ( !(unsigned int)LocalCredIsMarshaledCredentialW(v71) )
        goto LABEL_189;
      v72 = ppszUserName;
      if ( LocalCredUnmarshalCredentialW(*ppszUserName, (enum _CRED_MARSHAL_TYPE *)&Src, &v96) )
      {
        v11 = 0;
        v14 = -1073741670;
        goto LABEL_34;
      }
      if ( (_DWORD)Src != 4 )
        goto LABEL_189;
      if ( *ppszUserName )
      {
        SspiLocalFree((PVOID)*ppszUserName);
        *ppszUserName = 0;
      }
      if ( *ppszDomainName )
      {
        SspiLocalFree((PVOID)*ppszDomainName);
        *ppszDomainName = 0;
      }
      v73 = wcschr(*(const wchar_t **)v96, 0x5Cu);
      v74 = -1;
      if ( v73 )
      {
        *v73 = 0;
        v75 = v73 + 1;
        v76 = -1;
        do
          ++v76;
        while ( v75[v76] );
        if ( (unsigned int)v76 > 0x7FFD )
          goto LABEL_141;
        v77 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * v76 + 2) + 2LL, 1230267731);
        *ppszDomainName = v77;
        if ( !v77 )
          goto LABEL_30;
        memmove(v77, v75, 2LL * (unsigned int)v76);
        v72 = ppszUserName;
        v5 = 0;
      }
      do
        ++v74;
      while ( *(_WORD *)(*(_QWORD *)v96 + 2 * v74) );
      if ( (unsigned int)v74 > 0x7FFD )
      {
        v14 = -1073741811;
LABEL_185:
        v11 = 0;
        goto LABEL_53;
      }
      v78 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * v74 + 2) + 2LL, 1230267731);
      *v72 = v78;
      if ( !v78 )
      {
        v14 = -1073741801;
        goto LABEL_185;
      }
      memmove(v78, *(const void **)v96, 2LL * (unsigned int)v74);
    }
LABEL_189:
    v11 = 0;
LABEL_190:
    v9 = v86;
    goto LABEL_191;
  }
  v12 = *((unsigned __int16 *)pAuthIdentity + 8);
  v13 = v12 + *((unsigned __int16 *)pAuthIdentity + 12);
  HIDWORD(v92) = 0;
  if ( v13 >= 0x7FFD || (*((_DWORD *)pAuthIdentity + 9) & 0x10) != 0 )
  {
    v14 = -1073741811;
LABEL_35:
    if ( *ppszUserName )
    {
      SspiLocalFree((PVOID)*ppszUserName);
      *ppszUserName = 0;
    }
    if ( *v4 )
    {
      SspiLocalFree(*v4);
      *v4 = 0;
    }
    if ( v5 && *v5 )
    {
      SspiLocalFree(*v5);
      *v5 = 0;
    }
    goto LABEL_192;
  }
  if ( ppszPackedCredentialsString && (*((_DWORD *)pAuthIdentity + 7) || *((_WORD *)pAuthIdentity + 22)) )
  {
    v89 = (PVOID)ExAllocatePool2(256, v13 + 4 + 2LL, 1230267731);
    if ( !v89 )
    {
      v14 = -1073741801;
LABEL_33:
      v5 = (PVOID *)ppszPackedCredentialsString;
LABEL_34:
      v9 = v86;
      goto LABEL_35;
    }
    v15 = (char *)v89;
    if ( *((_WORD *)pAuthIdentity + 12) )
    {
      memmove(
        v89,
        (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 5),
        *((unsigned __int16 *)pAuthIdentity + 12));
      v16 = *((unsigned __int16 *)pAuthIdentity + 12);
      v17 = (char *)v89;
      *(_WORD *)((char *)v89 + v16) = 92;
      v15 = &v17[v16 + 2];
    }
    memmove(v15, (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 3), *((unsigned __int16 *)pAuthIdentity + 8));
    v18 = -1;
    v90 = (unsigned __int16 *)v89;
    if ( *((_WORD *)pAuthIdentity + 8) || *((_WORD *)pAuthIdentity + 12) )
    {
      v20 = LocalCredMarshalCredentialW(4, &v90, &Src);
      v8 = (char *)Src;
      if ( v20 )
        goto LABEL_22;
      v21 = -1;
      do
        ++v21;
      while ( *((_WORD *)Src + v21) );
      v22 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * v21 + 2) + 2LL, 1230267731);
      *ppszUserName = v22;
      if ( !v22 )
        goto LABEL_19;
      memmove(v22, v8, 2LL * (unsigned int)v21);
    }
    else
    {
      v19 = (WCHAR *)ExAllocatePool2(256, 12, 1230267731);
      *ppszUserName = v19;
      if ( !v19 )
      {
LABEL_19:
        v14 = -1073741801;
LABEL_32:
        v4 = (PVOID *)ppszDomainName;
        goto LABEL_33;
      }
      *(_QWORD *)v19 = 0x40004000400040LL;
    }
    v23 = *((unsigned __int16 *)pAuthIdentity + 22) + (unsigned int)*((unsigned __int16 *)pAuthIdentity + 16) + 24;
    v91 = v23;
    if ( (unsigned int)v23 >= 0xFFFF )
    {
      v14 = -1073741811;
      goto LABEL_32;
    }
    v91 = ((_DWORD)v23 + 1) & 0xFFFFFFFE;
    v24 = (_WORD *)ExAllocatePool2(256, v91 + 2, 1230267731);
    v87 = v24;
    v25 = v24;
    if ( !v24 )
      goto LABEL_30;
    *v24 = 24;
    v26 = *((_DWORD *)pAuthIdentity + 9);
    *((_DWORD *)v25 + 1) = v26;
    if ( !*((_DWORD *)pAuthIdentity + 5) )
    {
      v26 |= 0x40000u;
      *((_DWORD *)v25 + 1) = v26;
    }
    if ( !*((_DWORD *)pAuthIdentity + 3) )
      *((_DWORD *)v25 + 1) = v26 | 0x20000;
    v27 = v25 + 12;
    *((_DWORD *)v25 + 2) = 24;
    v25[6] = *((_WORD *)pAuthIdentity + 16);
    memmove(
      v25 + 12,
      (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 7),
      *((unsigned __int16 *)pAuthIdentity + 16));
    v11 = v87;
    v28 = (char *)v27 + *((unsigned __int16 *)pAuthIdentity + 16);
    *((_DWORD *)v87 + 4) = (_DWORD)v27 + *((unsigned __int16 *)pAuthIdentity + 16) - (_DWORD)v87;
    v87[10] = *((_WORD *)pAuthIdentity + 22) >> 1;
    memmove(
      v28,
      (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 10),
      *((unsigned __int16 *)pAuthIdentity + 22));
    LODWORD(v92) = v91;
    v93 = v87;
    if ( v8 )
    {
      SspiLocalFree(v8);
      Src = 0;
    }
    v29 = LocalCredMarshalCredentialW(3, &v92, &Src);
    v8 = (char *)Src;
    if ( !v29 )
    {
      do
        ++v18;
      while ( *((_WORD *)Src + v18) );
      if ( (unsigned int)v18 > 8 )
      {
LABEL_51:
        v30 = v18 - 8;
        v31 = (WCHAR *)ExAllocatePool2(256, 2 * v30 + 2 + 2LL, 1230267731);
        v5 = (PVOID *)ppszPackedCredentialsString;
        *ppszPackedCredentialsString = v31;
        if ( !v31 )
        {
          v14 = -1073741801;
LABEL_53:
          v4 = (PVOID *)ppszDomainName;
          goto LABEL_34;
        }
        memmove(v31, v8 + 16, 2LL * v30);
        goto LABEL_190;
      }
LABEL_55:
      v14 = -1073741637;
      goto LABEL_32;
    }
LABEL_22:
    v14 = -1073741670;
    goto LABEL_32;
  }
  if ( *((_DWORD *)pAuthIdentity + 3) )
  {
    v32 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(v12 + 2) + 2LL, 1230267731);
    *ppszUserName = v32;
    if ( !v32 )
    {
LABEL_58:
      v14 = -1073741801;
      goto LABEL_35;
    }
    memmove(v32, (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 3), *((unsigned __int16 *)pAuthIdentity + 8));
  }
  if ( *((_DWORD *)pAuthIdentity + 5) )
  {
    v33 = (void *)ExAllocatePool2(256, *((unsigned __int16 *)pAuthIdentity + 12) + 4LL, 1230267731);
    *v4 = v33;
    if ( !v33 )
      goto LABEL_58;
    memmove(
      v33,
      (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 5),
      *((unsigned __int16 *)pAuthIdentity + 12));
  }
LABEL_191:
  v14 = 0;
LABEL_192:
  if ( v8 )
    SspiLocalFree(v8);
  if ( v11 )
  {
    v79 = (unsigned int)v91;
    v80 = v11;
    if ( (_DWORD)v91 )
    {
      do
      {
        *v80++ = 0;
        --v79;
      }
      while ( v79 );
    }
    SspiLocalFree(v11);
  }
  v81 = DataBuffer;
  if ( DataBuffer )
  {
    v82 = Size;
    v83 = DataBuffer;
    if ( Size )
    {
      do
      {
        *v83++ = 0;
        --v82;
      }
      while ( v82 );
    }
    SspiLocalFree(v81);
  }
  if ( v94 )
    SspiLocalFree(v94);
  if ( v9 )
  {
    v84 = v9;
    for ( i = 2LL * (unsigned int)v95; i; --i )
    {
      *(_BYTE *)v84 = 0;
      v84 = (unsigned __int16 *)((char *)v84 + 1);
    }
    SspiLocalFree(v9);
  }
  if ( v89 )
    SspiLocalFree(v89);
  if ( v96 )
    SspiLocalFree(v96);
  return SspNtStatusToSecStatus((unsigned int)v14);
}

```

## disassembly

```asm
0x1800092d0  mov     rax, rsp
0x1800092d3  mov     [rax+20h], r9
0x1800092d7  mov     [rax+18h], r8
0x1800092db  mov     [rax+10h], rdx
0x1800092df  push    rbp
0x1800092e0  push    rbx
0x1800092e1  push    rsi
0x1800092e2  push    rdi
0x1800092e3  push    r12
0x1800092e5  push    r13
0x1800092e7  push    r14
0x1800092e9  push    r15
0x1800092eb  lea     rbp, [rax-5Fh]
0x1800092ef  sub     rsp, 88h
0x1800092f6  mov     rsi, r8
0x1800092f9  mov     r14, r9
0x1800092fc  xor     r8d, r8d
0x1800092ff  mov     rbx, rdx
0x180009302  mov     [rbp+57h+Src], r8
0x180009306  mov     rdi, rcx
0x180009309  mov     [rbp+57h+var_60], r8
0x18000930d  mov     r13d, r8d
0x180009310  mov     [rbp+57h+var_80], r8
0x180009314  mov     r15d, r8d
0x180009317  mov     [rbp+57h+var_A0], r8
0x18000931b  mov     [rbp+57h+var_70], r8
0x18000931f  mov     [rbp+57h+var_50], r8
0x180009323  test    rcx, rcx
0x180009326  jnz     short loc_180009332
0x180009328  mov     eax, 0C000000Dh
0x18000932d  jmp     loc_18000A054
0x180009332  mov     [rdx], r8
0x180009335  mov     r12, r8
0x180009338  mov     [rsi], r8
0x18000933b  mov     [rbp+57h+var_98], r8
0x18000933f  mov     [rbp+57h+DataBuffer], r8
0x180009343  mov     dword ptr [rbp+57h+var_78], 18h
0x18000934a  mov     dword ptr [rbp+57h+Size], r8d
0x18000934e  mov     [rbp+57h+var_88], r8
0x180009352  mov     dword ptr [rbp+57h+var_58], r8d
0x180009356  test    r9, r9
0x180009359  jz      short loc_18000935E
0x18000935b  mov     [r9], r8
0x18000935e  mov     eax, [rcx]
0x180009360  cmp     eax, 201h
0x180009365  jnz     loc_180009786
0x18000936b  movzx   edx, word ptr [rcx+10h]
0x18000936f  mov     ebx, 7FFDh
0x180009374  movzx   ecx, word ptr [rcx+18h]
0x180009378  add     ecx, edx
0x18000937a  mov     dword ptr [rbp+57h+var_70+4], r8d
0x18000937e  cmp     ecx, ebx
0x180009380  jb      short loc_18000938C
0x180009382  mov     ebx, 0C000000Dh
0x180009387  jmp     loc_18000955E
0x18000938c  mov     eax, [rdi+24h]
0x18000938f  test    al, 10h
0x180009391  jnz     short loc_180009382
0x180009393  test    r9, r9
0x180009396  jz      loc_1800096E4
0x18000939c  cmp     [rdi+1Ch], r8d
0x1800093a0  jnz     short loc_1800093AD
0x1800093a2  cmp     [rdi+2Ch], r8w
0x1800093a7  jz      loc_1800096E4
0x1800093ad  lea     edx, [rcx+4]
0x1800093b0  mov     r14d, 49546553h
0x1800093b6  mov     r15d, 100h
0x1800093bc  add     rdx, 2
0x1800093c0  mov     r8d, r14d
0x1800093c3  mov     ecx, r15d
0x1800093c6  call    cs:__imp_ExAllocatePool2
0x1800093cd  nop     dword ptr [rax+rax+00h]
0x1800093d2  xor     r8d, r8d
0x1800093d5  mov     [rbp+57h+var_88], rax
0x1800093d9  mov     r9, rax
0x1800093dc  test    rax, rax
0x1800093df  jnz     short loc_1800093EB
0x1800093e1  mov     ebx, 0C0000017h
0x1800093e6  jmp     loc_180009556
0x1800093eb  movzx   eax, word ptr [rdi+18h]
0x1800093ef  mov     rcx, r9; void *
0x1800093f2  test    ax, ax
0x1800093f5  jz      short loc_18000941A
0x1800093f7  mov     edx, [rdi+14h]
0x1800093fa  mov     r8d, eax; Size
0x1800093fd  add     rdx, rdi; Src
0x180009400  call    memmove
0x180009405  movzx   eax, word ptr [rdi+18h]
0x180009409  mov     rcx, [rbp+57h+var_88]
0x18000940d  mov     word ptr [rax+rcx], 5Ch ; '\'
0x180009413  add     rcx, 2
0x180009417  add     rcx, rax; void *
0x18000941a  mov     edx, [rdi+0Ch]
0x18000941d  movzx   r8d, word ptr [rdi+10h]; Size
0x180009422  add     rdx, rdi; Src
0x180009425  call    memmove
0x18000942a  mov     rax, [rbp+57h+var_88]
0x18000942e  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009432  mov     [rbp+57h+var_80], rax
0x180009436  xor     eax, eax
0x180009438  cmp     [rdi+10h], ax
0x18000943c  jnz     short loc_180009484
0x18000943e  cmp     [rdi+18h], ax
0x180009442  jnz     short loc_180009484
0x180009444  mov     r8d, r14d
0x180009447  lea     edx, [rsi+0Dh]
0x18000944a  mov     rcx, r15
0x18000944d  call    cs:__imp_ExAllocatePool2
0x180009454  nop     dword ptr [rax+rax+00h]
0x180009459  mov     rdx, [rbp+57h+arg_8]
0x18000945d  xor     r8d, r8d
0x180009460  mov     rcx, rax
0x180009463  mov     [rdx], rax
0x180009466  test    rax, rax
0x180009469  jnz     short loc_180009475
0x18000946b  mov     ebx, 0C0000017h
0x180009470  jmp     loc_180009552
0x180009475  mov     rax, 40004000400040h
0x18000947f  mov     [rcx], rax
0x180009482  jmp     short loc_1800094F9
0x180009484  lea     r8, [rbp+57h+Src]
0x180009488  mov     ecx, 4
0x18000948d  lea     rdx, [rbp+57h+var_80]
0x180009491  call    ?LocalCredMarshalCredentialW@@YAKW4_CRED_MARSHAL_TYPE@@PEAXPEAPEAG@Z; LocalCredMarshalCredentialW(_CRED_MARSHAL_TYPE,void *,ushort * *)
0x180009496  mov     r13, [rbp+57h+Src]
0x18000949a  xor     r8d, r8d
0x18000949d  test    eax, eax
0x18000949f  jz      short loc_1800094AB
0x1800094a1  mov     ebx, 0C000009Ah
0x1800094a6  jmp     loc_180009552
0x1800094ab  mov     rbx, rsi
0x1800094ae  inc     rbx
0x1800094b1  cmp     [r13+rbx*2+0], r8w
0x1800094b7  jnz     short loc_1800094AE
0x1800094b9  lea     edx, ds:2[rbx*2]
0x1800094c0  mov     r8d, r14d
0x1800094c3  add     rdx, 2
0x1800094c7  mov     rcx, r15
0x1800094ca  call    cs:__imp_ExAllocatePool2
0x1800094d1  nop     dword ptr [rax+rax+00h]
0x1800094d6  mov     rdx, [rbp+57h+arg_8]
0x1800094da  xor     r8d, r8d
0x1800094dd  mov     [rdx], rax
0x1800094e0  test    rax, rax
0x1800094e3  jz      short loc_18000946B
0x1800094e5  mov     r8d, ebx
0x1800094e8  mov     rdx, r13; Src
0x1800094eb  add     r8, r8; Size
0x1800094ee  mov     rcx, rax; void *
0x1800094f1  call    memmove
0x1800094f6  xor     r8d, r8d
0x1800094f9  movzx   edx, word ptr [rdi+20h]
0x1800094fd  mov     ebx, 0FFFFh
0x180009502  movzx   ecx, word ptr [rdi+2Ch]
0x180009506  add     edx, 18h
0x180009509  add     edx, ecx
0x18000950b  mov     [rbp+57h+var_78], rdx
0x18000950f  cmp     edx, ebx
0x180009511  jb      short loc_18000951A
0x180009513  mov     ebx, 0C000000Dh
0x180009518  jmp     short loc_180009552
0x18000951a  lea     eax, [rdx+1]
0x18000951d  mov     r8d, r14d
0x180009520  and     eax, 0FFFFFFFEh
0x180009523  mov     rcx, r15
0x180009526  mov     [rbp+57h+var_78], rax
0x18000952a  lea     rdx, [rax+2]
0x18000952e  call    cs:__imp_ExAllocatePool2
0x180009535  nop     dword ptr [rax+rax+00h]
0x18000953a  xor     r8d, r8d
0x18000953d  mov     [rbp+57h+var_98], rax
0x180009541  mov     rdx, rax
0x180009544  test    rax, rax
0x180009547  jnz     short loc_1800095AD
0x180009549  mov     ebx, 0C0000017h
0x18000954e  mov     r12, [rbp+57h+var_98]
0x180009552  mov     rsi, [rbp+57h+arg_10]
0x180009556  mov     r14, [rbp+57h+arg_18]
0x18000955a  mov     r15, [rbp+57h+var_A0]
0x18000955e  mov     rdi, [rbp+57h+arg_8]
0x180009562  mov     rcx, [rdi]; DataBuffer
0x180009565  test    rcx, rcx
0x180009568  jz      short loc_180009575
0x18000956a  call    SspiLocalFree
0x18000956f  xor     r8d, r8d
0x180009572  mov     [rdi], r8
0x180009575  mov     rcx, [rsi]; DataBuffer
0x180009578  test    rcx, rcx
0x18000957b  jz      short loc_180009588
0x18000957d  call    SspiLocalFree
0x180009582  xor     r8d, r8d
0x180009585  mov     [rsi], r8
0x180009588  test    r14, r14
0x18000958b  jz      loc_180009F94
0x180009591  mov     rcx, [r14]; DataBuffer
0x180009594  test    rcx, rcx
0x180009597  jz      loc_180009F94
0x18000959d  call    SspiLocalFree
0x1800095a2  xor     r8d, r8d
0x1800095a5  mov     [r14], r8
0x1800095a8  jmp     loc_180009F94
0x1800095ad  mov     word ptr [rax], 18h
0x1800095b2  mov     eax, [rdi+24h]
0x1800095b5  mov     [rdx+4], eax
0x1800095b8  cmp     [rdi+14h], r8d
0x1800095bc  jnz     short loc_1800095C5
0x1800095be  bts     eax, 12h
0x1800095c2  mov     [rdx+4], eax
0x1800095c5  cmp     [rdi+0Ch], r8d
0x1800095c9  jnz     short loc_1800095D2
0x1800095cb  bts     eax, 11h
0x1800095cf  mov     [rdx+4], eax
0x1800095d2  lea     rbx, [rdx+18h]
0x1800095d6  mov     eax, ebx
0x1800095d8  mov     rcx, rbx; void *
0x1800095db  sub     eax, edx
0x1800095dd  mov     [rdx+8], eax
0x1800095e0  movzx   eax, word ptr [rdi+20h]
0x1800095e4  mov     [rdx+0Ch], ax
0x1800095e8  mov     edx, [rdi+1Ch]
0x1800095eb  movzx   r8d, word ptr [rdi+20h]; Size
0x1800095f0  add     rdx, rdi; Src
0x1800095f3  call    memmove
0x1800095f8  movzx   ecx, word ptr [rdi+20h]
0x1800095fc  mov     r12, [rbp+57h+var_98]
0x180009600  add     rcx, rbx; void *
0x180009603  mov     eax, ecx
0x180009605  sub     eax, r12d
0x180009608  mov     [r12+10h], eax
0x18000960d  movzx   eax, word ptr [rdi+2Ch]
0x180009611  shr     ax, 1
0x180009614  mov     [r12+14h], ax
0x18000961a  mov     edx, [rdi+28h]
0x18000961d  movzx   r8d, word ptr [rdi+2Ch]; Size
0x180009622  add     rdx, rdi; Src
0x180009625  call    memmove
0x18000962a  mov     rax, [rbp+57h+var_78]
0x18000962e  xor     ebx, ebx
0x180009630  mov     dword ptr [rbp+57h+var_70], eax
0x180009633  mov     rax, r12
0x180009636  sar     rax, 20h
0x18000963a  mov     dword ptr [rbp+57h+var_68], r12d
0x18000963e  mov     dword ptr [rbp+57h+var_68+4], eax
0x180009641  test    r13, r13
0x180009644  jz      short loc_180009652
0x180009646  mov     rcx, r13; DataBuffer
0x180009649  call    SspiLocalFree
0x18000964e  mov     [rbp+57h+Src], rbx
0x180009652  lea     r8, [rbp+57h+Src]
0x180009656  mov     ecx, 3
0x18000965b  lea     rdx, [rbp+57h+var_70]
0x18000965f  call    ?LocalCredMarshalCredentialW@@YAKW4_CRED_MARSHAL_TYPE@@PEAXPEAPEAG@Z; LocalCredMarshalCredentialW(_CRED_MARSHAL_TYPE,void *,ushort * *)
0x180009664  mov     r13, [rbp+57h+Src]
0x180009668  xor     r8d, r8d
0x18000966b  test    eax, eax
0x18000966d  jnz     loc_1800094A1
0x180009673  inc     rsi
0x180009676  cmp     [r13+rsi*2+0], r8w
0x18000967c  jnz     short loc_180009673
0x18000967e  cmp     esi, 8
0x180009681  jbe     short loc_1800096DA
0x180009683  mov     r8d, r14d
0x180009686  mov     rcx, r15
0x180009689  add     esi, 0FFFFFFF8h
0x18000968c  lea     edx, ds:2[rsi*2]
0x180009693  add     rdx, 2
0x180009697  call    cs:__imp_ExAllocatePool2
0x18000969e  nop     dword ptr [rax+rax+00h]
0x1800096a3  mov     r14, [rbp+57h+arg_18]
0x1800096a7  xor     r8d, r8d
0x1800096aa  mov     [r14], rax
0x1800096ad  test    rax, rax
0x1800096b0  jnz     short loc_1800096C0
0x1800096b2  mov     ebx, 0C0000017h
0x1800096b7  mov     rsi, [rbp+57h+arg_10]
0x1800096bb  jmp     loc_18000955A
0x1800096c0  mov     r8d, esi
0x1800096c3  lea     rdx, [r13+10h]; Src
0x1800096c7  add     r8, r8; Size
0x1800096ca  mov     rcx, rax; void *
0x1800096cd  call    memmove
0x1800096d2  xor     r8d, r8d
0x1800096d5  jmp     loc_180009F8D
0x1800096da  mov     ebx, 0C00000BBh
0x1800096df  jmp     loc_180009552
0x1800096e4  cmp     [rdi+0Ch], r8d
0x1800096e8  jz      short loc_180009737
0x1800096ea  add     edx, 2
0x1800096ed  mov     ecx, 100h
0x1800096f2  add     rdx, 2
0x1800096f6  mov     r8d, 49546553h
0x1800096fc  call    cs:__imp_ExAllocatePool2
0x180009703  nop     dword ptr [rax+rax+00h]
0x180009708  mov     rdx, [rbp+57h+arg_8]
0x18000970c  xor     r8d, r8d
0x18000970f  mov     [rdx], rax
0x180009712  test    rax, rax
0x180009715  jnz     short loc_180009721
0x180009717  mov     ebx, 0C0000017h
0x18000971c  jmp     loc_18000955E
  ... truncated ...
```
