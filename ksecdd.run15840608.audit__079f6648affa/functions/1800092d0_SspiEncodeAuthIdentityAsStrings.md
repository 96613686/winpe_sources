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
- `0x180010a00`

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
  char *v15; // rax
  char *v16; // rcx
  __int64 v17; // rax
  char *v18; // rcx
  __int64 v19; // rsi
  WCHAR *v20; // rax
  int v21; // eax
  __int64 v22; // rbx
  WCHAR *v23; // rax
  __int64 v24; // rdx
  _WORD *v25; // rax
  _WORD *v26; // rdx
  int v27; // eax
  _WORD *v28; // rbx
  char *v29; // rcx
  int v30; // eax
  unsigned int v31; // esi
  WCHAR *v32; // rax
  WCHAR *v33; // rax
  void *v34; // rax
  BOOL v35; // esi
  char *v36; // r14
  int v37; // ecx
  unsigned __int8 *v38; // rax
  unsigned __int8 *v39; // rcx
  unsigned __int8 *v40; // rcx
  unsigned __int16 *v41; // rax
  unsigned int v42; // r12d
  WCHAR *v43; // rax
  WCHAR *v44; // rax
  unsigned __int16 *v45; // rax
  void *v46; // rax
  PCWSTR v47; // rax
  __int64 v48; // r15
  __int64 v49; // rdi
  __int64 v50; // rdx
  void *Pool2; // rax
  char *v52; // rcx
  size_t v53; // rbx
  char *v54; // rcx
  WCHAR *v55; // rax
  int v56; // eax
  __int64 v57; // rbx
  WCHAR *v58; // rax
  __int64 v59; // rdx
  _WORD *v60; // rax
  _WORD *v61; // rdx
  __int16 v62; // ax
  __int64 v63; // rax
  unsigned int v64; // edx
  unsigned int v65; // r15d
  _WORD *v66; // rax
  _WORD *v67; // rdx
  int v68; // eax
  PVOID v69; // rcx
  char *v70; // rdi
  int v71; // eax
  WCHAR *v72; // rbx
  PCWSTR *v73; // rdi
  wchar_t *v74; // rax
  __int64 v75; // rsi
  _WORD *v76; // r14
  __int64 v77; // rdi
  WCHAR *v78; // rax
  WCHAR *v79; // rax
  __int64 v80; // rdx
  _BYTE *v81; // rax
  PVOID v82; // rcx
  __int64 v83; // rdx
  _BYTE *v84; // rax
  unsigned __int16 *v85; // rdx
  __int64 i; // rax
  unsigned __int16 *v87; // [rsp+28h] [rbp-49h]
  _WORD *v88; // [rsp+30h] [rbp-41h]
  void *Src; // [rsp+38h] [rbp-39h] BYREF
  PVOID v90; // [rsp+40h] [rbp-31h]
  unsigned __int16 *v91; // [rsp+48h] [rbp-29h] BYREF
  __int64 v92; // [rsp+50h] [rbp-21h]
  unsigned __int16 *v93; // [rsp+58h] [rbp-19h] BYREF
  _WORD *v94; // [rsp+60h] [rbp-11h]
  PVOID v95; // [rsp+68h] [rbp-9h]
  __int64 v96; // [rsp+70h] [rbp-1h]
  PVOID v97; // [rsp+78h] [rbp+7h] BYREF
  PVOID DataBuffer; // [rsp+80h] [rbp+Fh]
  unsigned int Size; // [rsp+D8h] [rbp+67h]

  v4 = (PVOID *)ppszDomainName;
  v5 = (PVOID *)ppszPackedCredentialsString;
  v6 = ppszUserName;
  Src = 0;
  v95 = 0;
  v8 = 0;
  v91 = 0;
  v9 = 0;
  v87 = 0;
  v93 = 0;
  v97 = 0;
  if ( !pAuthIdentity )
    return -1073741811;
  *ppszUserName = 0;
  v11 = 0;
  *ppszDomainName = 0;
  v88 = 0;
  DataBuffer = 0;
  LODWORD(v92) = 24;
  Size = 0;
  v90 = 0;
  LODWORD(v96) = 0;
  if ( ppszPackedCredentialsString )
    *ppszPackedCredentialsString = 0;
  if ( *(_DWORD *)pAuthIdentity != 513 )
  {
    v35 = 0;
    if ( *(_DWORD *)pAuthIdentity == 512 )
    {
      v36 = (char *)pAuthIdentity + 8;
      if ( ppszPackedCredentialsString )
        v35 = *((_DWORD *)pAuthIdentity + 16) != 0;
    }
    else
    {
      v36 = (char *)pAuthIdentity;
    }
    v37 = *((_DWORD *)v36 + 11);
    if ( (v37 & 0x10) != 0 )
    {
      v14 = -1073741811;
LABEL_69:
      v4 = (PVOID *)ppszDomainName;
      v5 = (PVOID *)ppszPackedCredentialsString;
      goto LABEL_35;
    }
    v38 = *(unsigned __int8 **)v36;
    if ( (v37 & 1) != 0 )
    {
      if ( v38 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(*(unsigned __int8 **)v36, *((_DWORD *)v36 + 2), ppszUserName);
        if ( v14 < 0 )
          goto LABEL_31;
      }
      v39 = (unsigned __int8 *)*((_QWORD *)v36 + 2);
      if ( v39 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(v39, *((_DWORD *)v36 + 6), ppszDomainName);
        if ( v14 < 0 )
          goto LABEL_31;
      }
      if ( ppszPackedCredentialsString && (v40 = (unsigned __int8 *)*((_QWORD *)v36 + 4)) != 0 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(v40, *((_DWORD *)v36 + 10), (const unsigned __int16 **)&v93);
        if ( v14 < 0 )
        {
          v9 = v93;
LABEL_135:
          v11 = 0;
          goto LABEL_69;
        }
        v41 = v93;
        v87 = v93;
      }
      else
      {
        v41 = 0;
      }
      if ( v35 )
      {
        v14 = SspiHelperConvertAnsiStringToUnicodeString(
                *((unsigned __int8 **)pAuthIdentity + 7),
                *((_DWORD *)pAuthIdentity + 16),
                (const unsigned __int16 **)&v91);
        v95 = v91;
        if ( v14 < 0 )
          goto LABEL_31;
        v42 = *((_DWORD *)pAuthIdentity + 16);
        v6 = ppszUserName;
LABEL_97:
        v47 = *v6;
        v19 = -1;
        HIDWORD(v93) = 0;
        if ( v47 )
        {
          v48 = -1;
          do
            ++v48;
          while ( v47[v48] );
        }
        else
        {
          LODWORD(v48) = 0;
        }
        if ( *ppszDomainName )
        {
          v49 = -1;
          do
            ++v49;
          while ( (*ppszDomainName)[v49] );
        }
        else
        {
          LODWORD(v49) = 0;
        }
        if ( v87 )
        {
          v50 = -1;
          do
            ++v50;
          while ( v87[v50] );
        }
        else
        {
          v50 = 0;
        }
        v96 = v50;
        if ( (unsigned int)v48 > 0x7FFD || (unsigned int)v49 > 0x7FFD || (unsigned int)v50 > 0x7FFD )
          goto LABEL_141;
        Pool2 = (void *)ExAllocatePool2(256, (unsigned int)(2 * (v49 + v48) + 4) + 2LL, 1230267731);
        v90 = Pool2;
        if ( Pool2 )
        {
          v52 = (char *)Pool2;
          if ( (_DWORD)v49 )
          {
            v53 = 2LL * (unsigned int)v49;
            memmove(Pool2, *ppszDomainName, v53);
            v54 = (char *)v90 + 2;
            *(_WORD *)((char *)v90 + v53) = 92;
            v52 = &v54[v53];
          }
          memmove(v52, *ppszUserName, 2LL * (unsigned int)v48);
          v91 = (unsigned __int16 *)v90;
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
          if ( (_DWORD)v48 || (_DWORD)v49 )
          {
            v56 = LocalCredMarshalCredentialW(4, &v91, &Src);
            v8 = (char *)Src;
            if ( v56 )
            {
              v14 = -1073741670;
              goto LABEL_31;
            }
            v57 = -1;
            do
              ++v57;
            while ( *((_WORD *)Src + v57) );
            v58 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * v57 + 2) + 2LL, 1230267731);
            *ppszUserName = v58;
            if ( !v58 )
              goto LABEL_30;
            memmove(v58, v8, 2LL * (unsigned int)v57);
          }
          else
          {
            v55 = (WCHAR *)ExAllocatePool2(256, 12, 1230267731);
            *ppszUserName = v55;
            if ( !v55 )
              goto LABEL_30;
            *(_QWORD *)v55 = 0x40004000400040LL;
          }
          v9 = v87;
          if ( v87 )
          {
            v59 = (unsigned int)(2 * v96 + 32);
            Size = v59;
            if ( (unsigned int)v59 >= 0xFFFF )
            {
              v14 = -1073741811;
              goto LABEL_135;
            }
            v60 = (_WORD *)ExAllocatePool2(256, v59 + 2, 1230267731);
            DataBuffer = v60;
            v61 = v60;
            if ( !v60 )
            {
              v14 = -1073741801;
              goto LABEL_135;
            }
            *v60 = 28;
            v60[1] = Size;
            v62 = v96;
            *((_DWORD *)v61 + 5) = 28;
            v63 = (unsigned __int16)(2 * v62);
            v61[12] = v63;
            *(_OWORD *)(v61 + 2) = SEC_WINNT_AUTH_DATA_TYPE_PASSWORD;
            memmove(v61 + 14, v87, (unsigned __int16)v63);
            v64 = Size;
          }
          else
          {
            v64 = 0;
            Size = 0;
          }
          v65 = v64 + 2 * (v42 + 12);
          LODWORD(v92) = v65;
          if ( v65 >= 0xFFFF )
          {
LABEL_141:
            v14 = -1073741811;
            goto LABEL_31;
          }
          v66 = (_WORD *)ExAllocatePool2(256, v65 + 2LL, 1230267731);
          v88 = v66;
          v67 = v66;
          if ( v66 )
          {
            *v66 = 24;
            v68 = *((_DWORD *)v36 + 11);
            *((_DWORD *)v67 + 1) = v68;
            if ( !*((_QWORD *)v36 + 2) )
            {
              v68 |= 0x40000u;
              *((_DWORD *)v67 + 1) = v68;
            }
            if ( !*(_QWORD *)v36 )
              *((_DWORD *)v67 + 1) = v68 | 0x20000;
            v69 = DataBuffer;
            v70 = (char *)(v67 + 12);
            if ( DataBuffer )
            {
              *((_DWORD *)v67 + 2) = 24;
              v67[6] = Size;
              memmove(v70, v69, Size);
              v67 = v88;
              v70 += Size;
            }
            if ( v42 )
            {
              v67[10] = v42;
              *((_DWORD *)v67 + 4) = (_DWORD)v70 - (_DWORD)v67;
              memmove(v70, v95, 2LL * v42);
            }
            v11 = v88;
            LODWORD(v93) = v65;
            v94 = v88;
            if ( v8 )
            {
              SspiLocalFree(v8);
              Src = 0;
            }
            v71 = LocalCredMarshalCredentialW(3, &v93, &Src);
            v8 = (char *)Src;
            if ( !v71 )
            {
              do
                ++v19;
              while ( *((_WORD *)Src + v19) );
              if ( (unsigned int)v19 > 8 )
                goto LABEL_51;
              goto LABEL_55;
            }
            goto LABEL_22;
          }
        }
LABEL_30:
        v14 = -1073741801;
LABEL_31:
        v11 = v88;
        goto LABEL_32;
      }
      v6 = ppszUserName;
    }
    else
    {
      if ( v38 )
      {
        v43 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * *((_DWORD *)v36 + 2) + 2) + 2LL, 1230267731);
        *v6 = v43;
        if ( !v43 )
          goto LABEL_30;
        memmove(v43, *(const void **)v36, 2LL * *((unsigned int *)v36 + 2));
      }
      if ( *((_QWORD *)v36 + 2) )
      {
        v44 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * *((_DWORD *)v36 + 6) + 2) + 2LL, 1230267731);
        *ppszDomainName = v44;
        if ( !v44 )
          goto LABEL_30;
        memmove(v44, *((const void **)v36 + 2), 2LL * *((unsigned int *)v36 + 6));
      }
      if ( ppszPackedCredentialsString && *((_QWORD *)v36 + 4) )
      {
        v45 = (unsigned __int16 *)ExAllocatePool2(256, (unsigned int)(2 * *((_DWORD *)v36 + 10) + 2) + 2LL, 1230267731);
        v87 = v45;
        if ( !v45 )
          goto LABEL_30;
        memmove(v45, *((const void **)v36 + 4), 2LL * *((unsigned int *)v36 + 10));
      }
      if ( v35 )
      {
        v42 = *((_DWORD *)pAuthIdentity + 16);
        v46 = (void *)ExAllocatePool2(256, 2 * v42 + 2 + 2LL, 1230267731);
        v95 = v46;
        if ( !v46 )
          goto LABEL_30;
        memmove(v46, *((const void **)pAuthIdentity + 7), 2LL * *((unsigned int *)pAuthIdentity + 16));
        goto LABEL_97;
      }
      v41 = v87;
    }
    v5 = (PVOID *)ppszPackedCredentialsString;
    if ( ppszPackedCredentialsString )
    {
      v11 = 0;
      v9 = 0;
      *ppszPackedCredentialsString = v41;
      goto LABEL_191;
    }
    v4 = (PVOID *)ppszDomainName;
    if ( !*ppszDomainName || !**ppszDomainName )
    {
      v72 = (WCHAR *)*v6;
      LODWORD(Src) = 0;
      if ( (unsigned int)SspiHelperIsEncodedNullUserName(v72) )
      {
        if ( v72 )
        {
          SspiLocalFree(v72);
          *ppszUserName = 0;
        }
        if ( *ppszDomainName )
        {
          SspiLocalFree((PVOID)*ppszDomainName);
          *ppszDomainName = 0;
        }
        goto LABEL_189;
      }
      if ( !(unsigned int)LocalCredIsMarshaledCredentialW(v72) )
        goto LABEL_189;
      v73 = ppszUserName;
      if ( LocalCredUnmarshalCredentialW(*ppszUserName, (enum _CRED_MARSHAL_TYPE *)&Src, &v97) )
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
      v74 = wcschr(*(const wchar_t **)v97, 0x5Cu);
      v75 = -1;
      if ( v74 )
      {
        *v74 = 0;
        v76 = v74 + 1;
        v77 = -1;
        do
          ++v77;
        while ( v76[v77] );
        if ( (unsigned int)v77 > 0x7FFD )
          goto LABEL_141;
        v78 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * v77 + 2) + 2LL, 1230267731);
        *ppszDomainName = v78;
        if ( !v78 )
          goto LABEL_30;
        memmove(v78, v76, 2LL * (unsigned int)v77);
        v73 = ppszUserName;
        v5 = 0;
      }
      do
        ++v75;
      while ( *(_WORD *)(*(_QWORD *)v97 + 2 * v75) );
      if ( (unsigned int)v75 > 0x7FFD )
      {
        v14 = -1073741811;
LABEL_185:
        v11 = 0;
        goto LABEL_53;
      }
      v79 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * v75 + 2) + 2LL, 1230267731);
      *v73 = v79;
      if ( !v79 )
      {
        v14 = -1073741801;
        goto LABEL_185;
      }
      memmove(v79, *(const void **)v97, 2LL * (unsigned int)v75);
    }
LABEL_189:
    v11 = 0;
LABEL_190:
    v9 = v87;
    goto LABEL_191;
  }
  v12 = *((unsigned __int16 *)pAuthIdentity + 8);
  v13 = v12 + *((unsigned __int16 *)pAuthIdentity + 12);
  HIDWORD(v93) = 0;
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
    v15 = (char *)ExAllocatePool2(256, v13 + 4 + 2LL, 1230267731);
    v90 = v15;
    if ( !v15 )
    {
      v14 = -1073741801;
LABEL_33:
      v5 = (PVOID *)ppszPackedCredentialsString;
LABEL_34:
      v9 = v87;
      goto LABEL_35;
    }
    v16 = v15;
    if ( *((_WORD *)pAuthIdentity + 12) )
    {
      memmove(
        v15,
        (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 5),
        *((unsigned __int16 *)pAuthIdentity + 12));
      v17 = *((unsigned __int16 *)pAuthIdentity + 12);
      v18 = (char *)v90;
      *(_WORD *)((char *)v90 + v17) = 92;
      v16 = &v18[v17 + 2];
    }
    memmove(v16, (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 3), *((unsigned __int16 *)pAuthIdentity + 8));
    v19 = -1;
    v91 = (unsigned __int16 *)v90;
    if ( *((_WORD *)pAuthIdentity + 8) || *((_WORD *)pAuthIdentity + 12) )
    {
      v21 = LocalCredMarshalCredentialW(4, &v91, &Src);
      v8 = (char *)Src;
      if ( v21 )
        goto LABEL_22;
      v22 = -1;
      do
        ++v22;
      while ( *((_WORD *)Src + v22) );
      v23 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(2 * v22 + 2) + 2LL, 1230267731);
      *ppszUserName = v23;
      if ( !v23 )
        goto LABEL_19;
      memmove(v23, v8, 2LL * (unsigned int)v22);
    }
    else
    {
      v20 = (WCHAR *)ExAllocatePool2(256, 12, 1230267731);
      *ppszUserName = v20;
      if ( !v20 )
      {
LABEL_19:
        v14 = -1073741801;
LABEL_32:
        v4 = (PVOID *)ppszDomainName;
        goto LABEL_33;
      }
      *(_QWORD *)v20 = 0x40004000400040LL;
    }
    v24 = *((unsigned __int16 *)pAuthIdentity + 22) + (unsigned int)*((unsigned __int16 *)pAuthIdentity + 16) + 24;
    v92 = v24;
    if ( (unsigned int)v24 >= 0xFFFF )
    {
      v14 = -1073741811;
      goto LABEL_32;
    }
    v92 = ((_DWORD)v24 + 1) & 0xFFFFFFFE;
    v25 = (_WORD *)ExAllocatePool2(256, v92 + 2, 1230267731);
    v88 = v25;
    v26 = v25;
    if ( !v25 )
      goto LABEL_30;
    *v25 = 24;
    v27 = *((_DWORD *)pAuthIdentity + 9);
    *((_DWORD *)v26 + 1) = v27;
    if ( !*((_DWORD *)pAuthIdentity + 5) )
    {
      v27 |= 0x40000u;
      *((_DWORD *)v26 + 1) = v27;
    }
    if ( !*((_DWORD *)pAuthIdentity + 3) )
      *((_DWORD *)v26 + 1) = v27 | 0x20000;
    v28 = v26 + 12;
    *((_DWORD *)v26 + 2) = 24;
    v26[6] = *((_WORD *)pAuthIdentity + 16);
    memmove(
      v26 + 12,
      (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 7),
      *((unsigned __int16 *)pAuthIdentity + 16));
    v11 = v88;
    v29 = (char *)v28 + *((unsigned __int16 *)pAuthIdentity + 16);
    *((_DWORD *)v88 + 4) = (_DWORD)v28 + *((unsigned __int16 *)pAuthIdentity + 16) - (_DWORD)v88;
    v88[10] = *((_WORD *)pAuthIdentity + 22) >> 1;
    memmove(
      v29,
      (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 10),
      *((unsigned __int16 *)pAuthIdentity + 22));
    LODWORD(v93) = v92;
    v94 = v88;
    if ( v8 )
    {
      SspiLocalFree(v8);
      Src = 0;
    }
    v30 = LocalCredMarshalCredentialW(3, &v93, &Src);
    v8 = (char *)Src;
    if ( !v30 )
    {
      do
        ++v19;
      while ( *((_WORD *)Src + v19) );
      if ( (unsigned int)v19 > 8 )
      {
LABEL_51:
        v31 = v19 - 8;
        v32 = (WCHAR *)ExAllocatePool2(256, 2 * v31 + 2 + 2LL, 1230267731);
        v5 = (PVOID *)ppszPackedCredentialsString;
        *ppszPackedCredentialsString = v32;
        if ( !v32 )
        {
          v14 = -1073741801;
LABEL_53:
          v4 = (PVOID *)ppszDomainName;
          goto LABEL_34;
        }
        memmove(v32, v8 + 16, 2LL * v31);
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
    v33 = (WCHAR *)ExAllocatePool2(256, (unsigned int)(v12 + 2) + 2LL, 1230267731);
    *ppszUserName = v33;
    if ( !v33 )
    {
LABEL_58:
      v14 = -1073741801;
      goto LABEL_35;
    }
    memmove(v33, (char *)pAuthIdentity + *((unsigned int *)pAuthIdentity + 3), *((unsigned __int16 *)pAuthIdentity + 8));
  }
  if ( *((_DWORD *)pAuthIdentity + 5) )
  {
    v34 = (void *)ExAllocatePool2(256, *((unsigned __int16 *)pAuthIdentity + 12) + 4LL, 1230267731);
    *v4 = v34;
    if ( !v34 )
      goto LABEL_58;
    memmove(
      v34,
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
    v80 = (unsigned int)v92;
    v81 = v11;
    if ( (_DWORD)v92 )
    {
      do
      {
        *v81++ = 0;
        --v80;
      }
      while ( v80 );
    }
    SspiLocalFree(v11);
  }
  v82 = DataBuffer;
  if ( DataBuffer )
  {
    v83 = Size;
    v84 = DataBuffer;
    if ( Size )
    {
      do
      {
        *v84++ = 0;
        --v83;
      }
      while ( v83 );
    }
    SspiLocalFree(v82);
  }
  if ( v95 )
    SspiLocalFree(v95);
  if ( v9 )
  {
    v85 = v9;
    for ( i = 2LL * (unsigned int)v96; i; --i )
    {
      *(_BYTE *)v85 = 0;
      v85 = (unsigned __int16 *)((char *)v85 + 1);
    }
    SspiLocalFree(v9);
  }
  if ( v90 )
    SspiLocalFree(v90);
  if ( v97 )
    SspiLocalFree(v97);
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
