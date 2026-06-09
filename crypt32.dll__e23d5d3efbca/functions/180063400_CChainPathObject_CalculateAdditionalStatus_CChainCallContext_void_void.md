# CChainPathObject::CalculateAdditionalStatus(CChainCallContext *,void *,void *)

- ea: `0x180063400`
- end: `0x180063910`
- name: `?CalculateAdditionalStatus@CChainPathObject@@QEAAXPEAVCChainCallContext@@PEAX1@Z`
- size: `1296`
- prototype: `void __fastcall(CChainPathObject *__hidden this, struct CChainCallContext *, void *, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180062198`

## callees

- `0x18001347c`
- `0x180028d60`
- `0x18005083c`
- `0x180050abc`
- `0x18005936c`
- `0x180063400`
- `0x180064fa4`
- `0x180066b00`
- `0x1800870c8`
- `0x1800b9034`
- `0x1800bba14`
- `0x1800bec20`
- `0x1800f40ac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800634b5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800634c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800634f2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180063504`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180063643`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180063655`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800636c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800634b5`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800634c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800634f2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180063504`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180063643`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180063655`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800636c7`

## pseudocode

```c
void __fastcall CChainPathObject::CalculateAdditionalStatus(
        CChainPathObject *this,
        struct CChainCallContext *a2,
        void *a3,
        void *a4)
{
  __int64 v4; // rax
  unsigned __int16 **v5; // r12
  struct CChainCallContext *v6; // r15
  void *v8; // r13
  struct _CERT_INFO *v9; // rdi
  void *v10; // rcx
  bool v11; // zf
  int v12; // eax
  __int64 v13; // rcx
  int v14; // r14d
  __int64 v15; // rax
  struct _CERT_USAGE_MATCH *v16; // r13
  __int64 v17; // rcx
  __int64 v18; // rax
  struct _CERT_NAME_CONSTRAINTS_INFO *v19; // r12
  struct _FILETIME *p_pTimeToVerify; // r9
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // r14
  __int64 v24; // rsi
  int *v25; // rdx
  int v26; // ecx
  CCertObject **v27; // rdi
  _DWORD *v28; // rcx
  int v29; // esi
  struct _CHAIN_SUBJECT_NAME_CONSTRAINTS_INFO *v30; // rax
  CCertObject *v31; // rax
  HKEY v32; // rcx
  int v33; // edi
  unsigned __int16 *SZValueFromRegistry; // rax
  unsigned __int16 *v35; // rsi
  __int64 v36; // rdx
  __int64 v37; // rcx
  unsigned int v38; // [rsp+28h] [rbp-61h]
  struct _FILETIME pTimeToVerify; // [rsp+40h] [rbp-49h] BYREF
  FILETIME FileTime1; // [rsp+48h] [rbp-41h] BYREF
  FILETIME FileTime2; // [rsp+50h] [rbp-39h] BYREF
  void *v42; // [rsp+58h] [rbp-31h]
  FILETIME v43; // [rsp+60h] [rbp-29h] BYREF
  struct CChainCallContext *v44; // [rsp+68h] [rbp-21h]
  void *v45; // [rsp+70h] [rbp-19h]
  __int128 v46; // [rsp+78h] [rbp-11h] BYREF
  FILETIME *v47; // [rsp+88h] [rbp-1h]

  v4 = *(_QWORD *)this;
  v5 = (unsigned __int16 **)((char *)this + 160);
  v6 = a2;
  v44 = a2;
  v45 = a4;
  v8 = a3;
  v42 = a3;
  v9 = *(struct _CERT_INFO **)(*(_QWORD *)(v4 + 96) + 24LL);
  *(_QWORD *)((char *)this + 60) = 0;
  v10 = (void *)*((_QWORD *)this + 20);
  FileTime1 = 0;
  pTimeToVerify = 0;
  if ( v10 )
  {
    PkiDefaultCryptFree(v10);
    *v5 = 0;
  }
  v11 = *((_DWORD *)this + 6) == 0;
  FileTime1 = (FILETIME)*((_QWORD *)v6 + 4);
  pTimeToVerify = (struct _FILETIME)*((_QWORD *)v6 + 3);
  if ( !v11 )
  {
    v46 = 0;
    if ( CompareFileTime(&pTimeToVerify, &v9->NotBefore) >= 0 && CompareFileTime(&pTimeToVerify, &v9->NotAfter) <= 0 )
      goto LABEL_13;
    goto LABEL_12;
  }
  v12 = *((_DWORD *)v6 + 35) & 0x200;
  if ( *((_DWORD *)this + 7) )
  {
    if ( !v12 )
    {
      v46 = 0;
      if ( CompareFileTime(&FileTime1, &v9->NotBefore) >= 0 && CompareFileTime(&FileTime1, &v9->NotAfter) <= 0 )
        goto LABEL_13;
    }
    if ( !CertVerifyTimeValidity(&pTimeToVerify, v9) )
      goto LABEL_13;
LABEL_12:
    *((_DWORD *)this + 15) |= 1u;
    goto LABEL_13;
  }
  if ( v12 )
  {
    if ( !CertVerifyTimeValidity(&FileTime1, v9) && !CertVerifyTimeValidity(&pTimeToVerify, v9) )
      goto LABEL_37;
  }
  else
  {
    v46 = 0;
    if ( CompareFileTime(&FileTime1, &v9->NotBefore) >= 0 && CompareFileTime(&FileTime1, &v9->NotAfter) <= 0 )
      goto LABEL_37;
  }
  *((_DWORD *)this + 15) |= 1u;
LABEL_37:
  v21 = *((_QWORD *)this + 6);
  v22 = *((_DWORD *)this + 2);
  if ( v21 )
    v22 |= *(_DWORD *)(v21 + 8);
  if ( (v22 & 8) == 0 )
  {
    if ( *((_QWORD *)v6 + 23)
      && (*((_BYTE *)v6 + 128) & 1) == 0
      && !(unsigned int)I_CertCheckStrongSignature(
                          **(_DWORD **)(*(_QWORD *)this + 96LL),
                          100,
                          (CERT_CONTEXT *)&szPassword,
                          2,
                          *(PCCERT_CONTEXT *)(*(_QWORD *)this + 96LL),
                          v38,
                          *((const struct _CERT_STRONG_SIGN_PARA **)v6 + 23)) )
    {
      goto LABEL_71;
    }
    v23 = *(_QWORD *)this;
    v24 = *(_QWORD *)(*(_QWORD *)this + 8LL);
    v43 = 0;
    FileTime2 = 0;
    if ( (*(_DWORD *)(v23 + 48) & 0x10) != 0 )
    {
      v43 = (FILETIME)*((_QWORD *)v6 + 4);
      FileTime2 = *(FILETIME *)(v24 + 312);
      if ( CompareFileTime(&v43, &FileTime2) > 0 )
      {
        if ( (*(_DWORD *)(v24 + 296) & 0xC) == 0 )
          goto LABEL_71;
        v32 = *(HKEY *)(v24 + 800);
        v33 = *(_DWORD *)(v24 + 296) & 8;
        if ( v32 )
        {
          SZValueFromRegistry = ILS_ReadSZValueFromRegistry(v32, L"WeakSignatureLogDir");
          v35 = SZValueFromRegistry;
          if ( SZValueFromRegistry )
          {
            v36 = *(_QWORD *)(v23 + 96);
            *((_QWORD *)&v46 + 1) = *(_QWORD *)(v36 + 8);
            v37 = *(unsigned int *)(v36 + 16);
            *(_QWORD *)&v46 = (unsigned int)v37;
            CertDiagWriteX509ObjectBlobToFile(v37, &v46, SZValueFromRegistry);
            PkiDefaultCryptFree(v35);
          }
        }
        if ( !v33 )
LABEL_71:
          *((_DWORD *)this + 15) |= 0x100008u;
      }
    }
  }
LABEL_13:
  v13 = *((_QWORD *)this + 4);
  v14 = 0;
  if ( !v13 )
    goto LABEL_14;
  v47 = 0;
  v43 = (FILETIME)"1.3.6.1.4.1.311.10.3.1";
  v15 = *((_QWORD *)this + 5);
  v46 = 0;
  if ( *(_DWORD *)(v15 + 24) )
  {
    DWORD2(v46) = 1;
    v47 = &v43;
    v16 = (struct _CERT_USAGE_MATCH *)&v46;
  }
  else
  {
    v16 = (struct _CERT_USAGE_MATCH *)((char *)v6 + 48);
  }
  if ( *(_DWORD *)(v13 + 16) )
  {
    *(_QWORD *)(v13 + 8) = 0;
    SSCtlGetCtlTrustStatus(
      *(const struct _CTL_CONTEXT **)(**(_QWORD **)(*((_QWORD *)this + 4) + 48LL) + 8LL),
      *(_DWORD *)(**(_QWORD **)(*((_QWORD *)this + 4) + 48LL) + 100LL),
      &pTimeToVerify,
      v16,
      (struct _CERT_TRUST_STATUS *)(*((_QWORD *)this + 4) + 8LL));
    goto LABEL_29;
  }
  CChainPathObject::CalculateBasicConstraintsStatus(this);
  v17 = *(_QWORD *)this;
  if ( (*(_BYTE *)(*(_QWORD *)this + 48LL) & 4) != 0 )
    *((_DWORD *)this + 15) |= 0x110u;
  v18 = *(_QWORD *)(v17 + 216);
  if ( v18 && (!*(_DWORD *)v18 || (**(_BYTE **)(v18 + 8) & 4) == 0) )
    *((_DWORD *)this + 15) |= 0x10u;
  v11 = (*(_BYTE *)(v17 + 48) & 2) == 0;
  FileTime2.dwLowDateTime = 0;
  if ( !v11 )
  {
    *((_DWORD *)this + 15) |= 0x900u;
    ChainFormatAndAppendExtendedErrorInfo(v5, 0x1964u);
  }
  v19 = *(struct _CERT_NAME_CONSTRAINTS_INFO **)(*(_QWORD *)this + 224LL);
  if ( v19 )
  {
    v25 = (int *)*((_QWORD *)this + 4);
    if ( !v25 )
      goto LABEL_51;
    v26 = *v25 | 0x8000000;
    if ( (v25[2] & 0x100000) == 0 )
      v26 = *v25;
    if ( (v26 & 0xD000000) == 0xD000000 )
    {
LABEL_51:
      v27 = (CCertObject **)*((_QWORD *)this + 5);
      if ( !v27 )
        goto LABEL_69;
      while ( 1 )
      {
        if ( *((_DWORD *)this + 6) != *((_DWORD *)v27 + 6) )
        {
LABEL_62:
          v6 = v44;
          if ( FileTime2.dwLowDateTime )
          {
            *((_DWORD *)this + 15) |= FileTime2.dwLowDateTime;
            goto LABEL_29;
          }
LABEL_69:
          *((_DWORD *)this + 16) |= 0x400u;
          goto LABEL_29;
        }
        if ( *((_DWORD *)v27 + 7) )
        {
          v31 = v27[6];
          if ( v31 && *((_DWORD *)v31 + 8) )
            goto LABEL_61;
          v29 = 1;
        }
        else
        {
          v28 = (_DWORD *)*((_QWORD *)*v27 + 26);
          if ( !v28 || (v29 = 1, !*v28) )
            v29 = 0;
        }
        if ( (*(_BYTE *)(*(_QWORD *)this + 48LL) & 0x40) == 0 )
          break;
        if ( !v29 )
        {
          v14 = 1;
          goto LABEL_59;
        }
LABEL_61:
        v27 = (CCertObject **)v27[5];
        if ( !v27 )
          goto LABEL_62;
      }
      if ( !v29 || !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)this + 8LL) + 252LL) )
      {
LABEL_59:
        v30 = CCertObject::SubjectNameConstraintsInfo(*v27);
        CalculateNameConstraintsStatusForSubject(
          v16,
          v30,
          v19,
          v29,
          v14,
          (unsigned int *)&FileTime2,
          (unsigned __int16 **)this + 20);
      }
      v14 = 0;
      goto LABEL_61;
    }
  }
LABEL_29:
  v8 = v42;
LABEL_14:
  if ( (*((_DWORD *)this + 2) & 0x4000000) == 0
    && ((*((_DWORD *)this + 3) & 0x800) == 0 || (*((_DWORD *)v6 + 35) & 0x400) == 0)
    && (*((_DWORD *)v6 + 35) & 0x70000000) != 0 )
  {
    p_pTimeToVerify = &pTimeToVerify;
    if ( !*((_DWORD *)this + 6) )
      p_pTimeToVerify = &FileTime1;
    CChainPathObject::CalculateRevocationStatus(this, v6, v8, p_pTimeToVerify, v45);
  }
  *((_DWORD *)this + 14) = 1;
}

```

## disassembly

```asm
0x180063400  push    rbp
0x180063402  push    rbx
0x180063403  push    rsi
0x180063404  push    rdi
0x180063405  push    r12
0x180063407  push    r13
0x180063409  push    r14
0x18006340b  push    r15
0x18006340d  lea     rbp, [rsp-1Fh]
0x180063412  sub     rsp, 0A8h
0x180063419  mov     rax, cs:__security_cookie
0x180063420  xor     rax, rsp
0x180063423  mov     [rbp+57h+var_50], rax
0x180063427  mov     rax, [rcx]
0x18006342a  lea     r12, [rcx+0A0h]
0x180063431  mov     r15, rdx
0x180063434  mov     [rbp+57h+var_78], rdx
0x180063438  mov     rbx, rcx
0x18006343b  mov     [rbp+57h+var_70], r9
0x18006343f  mov     r13, r8
0x180063442  mov     [rbp+57h+var_88], r8
0x180063446  mov     rdx, [rax+60h]
0x18006344a  xor     eax, eax
0x18006344c  mov     rdi, [rdx+18h]
0x180063450  mov     [rcx+3Ch], rax
0x180063454  mov     rcx, [r12]; hMem
0x180063458  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], 0
0x180063460  mov     qword ptr [rbp+57h+pTimeToVerify.dwLowDateTime], 0
0x180063468  test    rcx, rcx
0x18006346b  jnz     loc_180063864
0x180063471  cmp     dword ptr [rbx+18h], 0
0x180063475  mov     esi, 1
0x18006347a  mov     rax, [r15+20h]
0x18006347e  mov     qword ptr [rbp+57h+FileTime1.dwLowDateTime], rax
0x180063482  mov     rax, [r15+18h]
0x180063486  mov     qword ptr [rbp+57h+pTimeToVerify.dwLowDateTime], rax
0x18006348a  jnz     short loc_1800634E3
0x18006348c  mov     eax, [r15+8Ch]
0x180063493  and     eax, 200h
0x180063498  cmp     dword ptr [rbx+1Ch], 0
0x18006349c  jz      loc_18006362C
0x1800634a2  test    eax, eax
0x1800634a4  jnz     short loc_1800634D1
0x1800634a6  xorps   xmm0, xmm0
0x1800634a9  lea     rdx, [rdi+40h]; lpFileTime2
0x1800634ad  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x1800634b1  movups  [rbp+57h+var_68], xmm0
0x1800634b5  call    cs:__imp_CompareFileTime
0x1800634bb  test    eax, eax
0x1800634bd  js      short loc_1800634D1
0x1800634bf  lea     rdx, [rdi+48h]; lpFileTime2
0x1800634c3  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x1800634c7  call    cs:__imp_CompareFileTime
0x1800634cd  test    eax, eax
0x1800634cf  jle     short loc_180063511
0x1800634d1  mov     rdx, rdi; pCertInfo
0x1800634d4  lea     rcx, [rbp+57h+pTimeToVerify]; pTimeToVerify
0x1800634d8  call    CertVerifyTimeValidity
0x1800634dd  test    eax, eax
0x1800634df  jnz     short loc_18006350E
0x1800634e1  jmp     short loc_180063511
0x1800634e3  xorps   xmm0, xmm0
0x1800634e6  lea     rdx, [rdi+40h]; lpFileTime2
0x1800634ea  lea     rcx, [rbp+57h+pTimeToVerify]; lpFileTime1
0x1800634ee  movups  [rbp+57h+var_68], xmm0
0x1800634f2  call    cs:__imp_CompareFileTime
0x1800634f8  test    eax, eax
0x1800634fa  js      short loc_18006350E
0x1800634fc  lea     rdx, [rdi+48h]; lpFileTime2
0x180063500  lea     rcx, [rbp+57h+pTimeToVerify]; lpFileTime1
0x180063504  call    cs:__imp_CompareFileTime
0x18006350a  test    eax, eax
0x18006350c  jle     short loc_180063511
0x18006350e  or      [rbx+3Ch], esi
0x180063511  mov     rcx, [rbx+20h]
0x180063515  xor     r14d, r14d
0x180063518  test    rcx, rcx
0x18006351b  jnz     short loc_18006356B
0x18006351d  test    dword ptr [rbx+8], 4000000h
0x180063524  jnz     short loc_180063544
0x180063526  test    dword ptr [rbx+0Ch], 800h
0x18006352d  jnz     loc_1800637C3
0x180063533  test    dword ptr [r15+8Ch], 70000000h
0x18006353e  jnz     loc_180063600
0x180063544  mov     dword ptr [rbx+38h], 1
0x18006354b  mov     rcx, [rbp+57h+var_50]
0x18006354f  xor     rcx, rsp; StackCookie
0x180063552  call    __security_check_cookie
0x180063557  add     rsp, 0A8h
0x18006355e  pop     r15
0x180063560  pop     r14
0x180063562  pop     r13
0x180063564  pop     r12
0x180063566  pop     rdi
0x180063567  pop     rsi
0x180063568  pop     rbx
0x180063569  pop     rbp
0x18006356a  retn
0x18006356b  xor     eax, eax
0x18006356d  xorps   xmm0, xmm0
0x180063570  mov     [rbp+57h+var_58], rax
0x180063574  lea     rax, a1361413111031; "1.3.6.1.4.1.311.10.3.1"
0x18006357b  mov     qword ptr [rbp+57h+var_80.dwLowDateTime], rax
0x18006357f  mov     rax, [rbx+28h]
0x180063583  movups  [rbp+57h+var_68], xmm0
0x180063587  cmp     [rax+18h], r14d
0x18006358b  jnz     loc_180063876
0x180063591  lea     r13, [r15+30h]
0x180063595  cmp     [rcx+10h], r14d
0x180063599  jnz     loc_18006388E
0x18006359f  mov     rcx, rbx; this
0x1800635a2  call    ?CalculateBasicConstraintsStatus@CChainPathObject@@QEAAXXZ; CChainPathObject::CalculateBasicConstraintsStatus(void)
0x1800635a7  mov     rcx, [rbx]
0x1800635aa  test    byte ptr [rcx+30h], 4
0x1800635ae  jnz     loc_1800638C0
0x1800635b4  mov     rax, [rcx+0D8h]
0x1800635bb  test    rax, rax
0x1800635be  jz      short loc_1800635D6
0x1800635c0  cmp     dword ptr [rax], 1
0x1800635c3  jb      loc_1800638CC
0x1800635c9  mov     rax, [rax+8]
0x1800635cd  test    byte ptr [rax], 4
0x1800635d0  jz      loc_1800638CC
0x1800635d6  test    byte ptr [rcx+30h], 2
0x1800635da  mov     [rbp+57h+FileTime2.dwLowDateTime], r14d
0x1800635de  jnz     loc_1800638D5
0x1800635e4  mov     rax, [rbx]
0x1800635e7  mov     r12, [rax+0E0h]
0x1800635ee  test    r12, r12
0x1800635f1  jnz     loc_180063703
0x1800635f7  mov     r13, [rbp+57h+var_88]
0x1800635fb  jmp     loc_18006351D
0x180063600  cmp     [rbx+18h], r14d
0x180063604  lea     rax, [rbp+57h+FileTime1]
0x180063608  lea     r9, [rbp+57h+pTimeToVerify]
0x18006360c  mov     r8, r13; void *
0x18006360f  cmovz   r9, rax; struct _FILETIME *
0x180063613  mov     rdx, r15; struct CChainCallContext *
0x180063616  mov     rax, [rbp+57h+var_70]
0x18006361a  mov     rcx, rbx; this
0x18006361d  mov     [rsp+0E0h+var_C0], rax; void *
0x180063622  call    ?CalculateRevocationStatus@CChainPathObject@@QEAAXPEAVCChainCallContext@@PEAXPEAU_FILETIME@@1@Z; CChainPathObject::CalculateRevocationStatus(CChainCallContext *,void *,_FILETIME *,void *)
0x180063627  jmp     loc_180063544
0x18006362c  lea     rcx, [rbp+57h+FileTime1]; pTimeToVerify
0x180063630  test    eax, eax
0x180063632  jnz     loc_1800636DA
0x180063638  xorps   xmm0, xmm0
0x18006363b  lea     rdx, [rdi+40h]; lpFileTime2
0x18006363f  movups  [rbp+57h+var_68], xmm0
0x180063643  call    cs:__imp_CompareFileTime
0x180063649  test    eax, eax
0x18006364b  js      short loc_18006365F
0x18006364d  lea     rdx, [rdi+48h]; lpFileTime2
0x180063651  lea     rcx, [rbp+57h+FileTime1]; lpFileTime1
0x180063655  call    cs:__imp_CompareFileTime
0x18006365b  test    eax, eax
0x18006365d  jle     short loc_180063662
0x18006365f  or      [rbx+3Ch], esi
0x180063662  mov     rcx, [rbx+30h]
0x180063666  mov     eax, [rbx+8]
0x180063669  test    rcx, rcx
0x18006366c  jz      short loc_180063671
0x18006366e  or      eax, [rcx+8]
0x180063671  test    al, 8
0x180063673  jnz     loc_180063511
0x180063679  mov     rdx, [r15+0B8h]
0x180063680  test    rdx, rdx
0x180063683  jnz     loc_18006380A
0x180063689  mov     r14, [rbx]
0x18006368c  mov     rsi, [r14+8]
0x180063690  mov     qword ptr [rbp+57h+var_80.dwLowDateTime], 0
0x180063698  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], 0
0x1800636a0  mov     eax, [r14+30h]
0x1800636a4  test    al, 10h
0x1800636a6  jz      loc_180063511
0x1800636ac  mov     rax, [r15+20h]
0x1800636b0  lea     rdx, [rbp+57h+FileTime2]; lpFileTime2
0x1800636b4  mov     qword ptr [rbp+57h+var_80.dwLowDateTime], rax
0x1800636b8  lea     rcx, [rbp+57h+var_80]; lpFileTime1
0x1800636bc  mov     rax, [rsi+138h]
0x1800636c3  mov     qword ptr [rbp+57h+FileTime2.dwLowDateTime], rax
0x1800636c7  call    cs:__imp_CompareFileTime
0x1800636cd  test    eax, eax
0x1800636cf  jle     loc_180063511
0x1800636d5  jmp     loc_180119AC0
0x1800636da  mov     rdx, rdi; pCertInfo
0x1800636dd  call    CertVerifyTimeValidity
0x1800636e2  test    eax, eax
0x1800636e4  jnz     loc_18006365F
0x1800636ea  mov     rdx, rdi; pCertInfo
0x1800636ed  lea     rcx, [rbp+57h+pTimeToVerify]; pTimeToVerify
0x1800636f1  call    CertVerifyTimeValidity
0x1800636f6  test    eax, eax
0x1800636f8  jz      loc_180063662
0x1800636fe  jmp     loc_18006365F
0x180063703  mov     rdx, [rbx+20h]
0x180063707  test    rdx, rdx
0x18006370a  jz      short loc_18006372B
0x18006370c  mov     ecx, [rdx]
0x18006370e  mov     eax, 0D000000h
0x180063713  bts     ecx, 1Bh
0x180063717  test    dword ptr [rdx+8], 100000h
0x18006371e  cmovz   ecx, [rdx]
0x180063721  and     ecx, eax
0x180063723  cmp     ecx, eax
0x180063725  jnz     loc_1800635F7
0x18006372b  mov     rdi, [rbx+28h]
0x18006372f  test    rdi, rdi
0x180063732  jz      loc_1800637EC
0x180063738  lea     r15, [rbx+0A0h]
0x18006373f  mov     eax, [rdi+18h]
0x180063742  cmp     [rbx+18h], eax
0x180063745  jnz     short loc_1800637B0
0x180063747  cmp     [rdi+1Ch], r14d
0x18006374b  jnz     loc_18006384D
0x180063751  mov     rax, [rdi]
0x180063754  mov     rcx, [rax+0D0h]
0x18006375b  test    rcx, rcx
0x18006375e  jnz     loc_1800638FD
0x180063764  mov     esi, r14d
0x180063767  mov     rax, [rbx]
0x18006376a  test    byte ptr [rax+30h], 40h
0x18006376e  jz      short loc_1800637D9
0x180063770  test    esi, esi
0x180063772  jnz     short loc_1800637A7
0x180063774  lea     r14d, [rsi+1]
0x180063778  mov     rcx, [rdi]; this
0x18006377b  call    ?SubjectNameConstraintsInfo@CCertObject@@QEAAPEAU_CHAIN_SUBJECT_NAME_CONSTRAINTS_INFO@@XZ; CCertObject::SubjectNameConstraintsInfo(void)
0x180063780  mov     rdx, rax; struct _CHAIN_SUBJECT_NAME_CONSTRAINTS_INFO *
0x180063783  mov     [rsp+0E0h+var_B0], r15; unsigned __int16 **
0x180063788  lea     rax, [rbp+57h+FileTime2]
0x18006378c  mov     r9d, esi; int
0x18006378f  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x180063794  mov     r8, r12; struct _CERT_NAME_CONSTRAINTS_INFO *
0x180063797  mov     rcx, r13; struct _CERT_USAGE_MATCH *
0x18006379a  mov     dword ptr [rsp+0E0h+var_C0], r14d; int
0x18006379f  call    ?CalculateNameConstraintsStatusForSubject@@YAXPEAU_CERT_USAGE_MATCH@@PEAU_CHAIN_SUBJECT_NAME_CONSTRAINTS_INFO@@PEAU_CERT_NAME_CONSTRAINTS_INFO@@HHPEAKPEAPEAG@Z; CalculateNameConstraintsStatusForSubject(_CERT_USAGE_MATCH *,_CHAIN_SUBJECT_NAME_CONSTRAINTS_INFO *,_CERT_NAME_CONSTRAINTS_INFO *,int,int,ulong *,ushort * *)
0x1800637a4  xor     r14d, r14d
0x1800637a7  mov     rdi, [rdi+28h]
0x1800637ab  test    rdi, rdi
0x1800637ae  jnz     short loc_18006373F
0x1800637b0  mov     eax, [rbp+57h+FileTime2.dwLowDateTime]
0x1800637b3  mov     r15, [rbp+57h+var_78]
0x1800637b7  test    eax, eax
0x1800637b9  jz      short loc_1800637EC
0x1800637bb  or      [rbx+3Ch], eax
0x1800637be  jmp     loc_1800635F7
0x1800637c3  test    dword ptr [r15+8Ch], 400h
0x1800637ce  jz      loc_180063533
0x1800637d4  jmp     loc_180063544
0x1800637d9  test    esi, esi
0x1800637db  jz      short loc_180063778
0x1800637dd  mov     rax, [rax+8]
0x1800637e1  cmp     dword ptr [rax+0FCh], 0
0x1800637e8  jnz     short loc_1800637A4
0x1800637ea  jmp     short loc_180063778
0x1800637ec  bts     dword ptr [rbx+40h], 0Ah
0x1800637f1  jmp     loc_1800635F7
0x1800637f6  test    edi, edi
0x1800637f8  jnz     loc_180063511
0x1800637fe  or      dword ptr [rbx+3Ch], 100008h
0x180063805  jmp     loc_180063511
0x18006380a  mov     eax, [r15+80h]
0x180063811  and     eax, esi
0x180063813  test    al, al
0x180063815  jnz     loc_180063689
0x18006381b  mov     rax, [rbx]
0x18006381e  lea     r8, szPassword; void *
0x180063825  mov     [rsp+0E0h+var_B0], rdx; struct _CERT_STRONG_SIGN_PARA *
0x18006382a  mov     r9d, 2; unsigned int
0x180063830  mov     rcx, [rax+60h]
0x180063834  mov     [rsp+0E0h+var_C0], rcx; void *
0x180063839  lea     edx, [r9+62h]; unsigned int
0x18006383d  mov     ecx, [rcx]; unsigned int
0x18006383f  call    ?I_CertCheckStrongSignature@@YAHKKPEAXK0KPEBU_CERT_STRONG_SIGN_PARA@@@Z; I_CertCheckStrongSignature(ulong,ulong,void *,ulong,void *,ulong,_CERT_STRONG_SIGN_PARA const *)
0x180063844  test    eax, eax
0x180063846  jz      short loc_1800637FE
0x180063848  jmp     loc_180063689
0x18006384d  mov     rax, [rdi+30h]
0x180063851  test    rax, rax
0x180063854  jnz     loc_1800638EE
0x18006385a  mov     esi, 1
0x18006385f  jmp     loc_180063767
0x180063864  call    PkiDefaultCryptFree
0x180063869  mov     qword ptr [r12], 0
0x180063871  jmp     loc_180063471
0x180063876  lea     rax, [rbp+57h+var_80]
0x18006387a  mov     dword ptr [rbp+57h+var_68+8], 1
0x180063881  mov     [rbp+57h+var_58], rax
0x180063885  lea     r13, [rbp+57h+var_68]
0x180063889  jmp     loc_180063595
0x18006388e  xor     eax, eax
0x180063890  lea     r8, [rbp+57h+pTimeToVerify]; struct _FILETIME *
0x180063894  mov     [rcx+8], rax
0x180063898  mov     r9, r13; struct _CERT_USAGE_MATCH *
0x18006389b  mov     rdx, [rbx+20h]
0x18006389f  mov     rax, [rdx+30h]
0x1800638a3  mov     rcx, [rax]
0x1800638a6  lea     rax, [rdx+8]
0x1800638aa  mov     [rsp+0E0h+var_C0], rax; struct _CERT_TRUST_STATUS *
  ... truncated ...
```
