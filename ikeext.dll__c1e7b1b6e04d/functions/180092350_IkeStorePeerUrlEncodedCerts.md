# IkeStorePeerUrlEncodedCerts

- ea: `0x180092350`
- end: `0x1800929c6`
- name: `IkeStorePeerUrlEncodedCerts`
- size: `1654`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180092190`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x18005bce4`
- `0x18008c8cc`
- `0x18008fe98`
- `0x18008ffe8`
- `0x180090584`
- `0x180090700`
- `0x180092350`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800928d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800928ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092851`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800928d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800928ee`
- `CRYPT32!CertOpenStore` at `0x180092843`
- `CRYPT32!CertOpenStore` at `0x180092843`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18009288c`
- `CRYPT32!CertAddCertificateContextToStore` at `0x18009288c`
- `CRYPT32!CertAddCRLContextToStore` at `0x1800928bf`
- `CRYPT32!CertAddCRLContextToStore` at `0x1800928bf`

## string_xrefs

- `0x18009285a`: `CertOpenStore`

## pseudocode

```c
__int64 __fastcall IkeStorePeerUrlEncodedCerts(__int64 a1, unsigned __int8 a2, unsigned int *a3)
{
  int v3; // r12d
  __int64 v6; // rcx
  __int64 v7; // rsi
  __int64 TlsPeerAddr; // rbx
  __int64 v9; // rcx
  int TlsMmLuid; // eax
  __int64 v11; // rcx
  const WCHAR *v12; // rax
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rdi
  __int64 v16; // rbx
  __int64 v17; // rcx
  int v18; // eax
  __int64 v19; // rcx
  const WCHAR *v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int8 *v23; // rdx
  const char *v24; // rdx
  __int64 v25; // r8
  __int64 v26; // rbx
  unsigned int v28; // esi
  __int64 v29; // rdi
  __int64 v30; // rbx
  __int64 v31; // rcx
  int v32; // eax
  __int64 v33; // rcx
  const WCHAR *v34; // rax
  __int64 v35; // r8
  __int64 v36; // r9
  __int64 CertInfo; // rsi
  int v38; // eax
  __int64 v39; // rdi
  __int64 v40; // rbx
  __int64 v41; // rcx
  int v42; // eax
  __int64 v43; // rcx
  const WCHAR *v44; // rax
  __int64 v45; // rdi
  char v46; // r8
  __int64 i; // rdx
  char v48; // cl
  char v49; // al
  HCERTSTORE v50; // rax
  DWORD v51; // eax
  int v52; // edi
  unsigned int v53; // edi
  DWORD LastError; // eax
  DWORD v55; // eax
  __int64 v56; // rdi
  __int64 v57; // rbx
  __int64 v58; // rcx
  int v59; // eax
  __int64 v60; // rcx
  const WCHAR *v61; // rax
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // [rsp+28h] [rbp-B1h]
  __int64 v65; // [rsp+40h] [rbp-99h] BYREF
  PCCERT_CONTEXT *v66; // [rsp+48h] [rbp-91h] BYREF
  __int64 v67; // [rsp+50h] [rbp-89h] BYREF
  __int128 v68; // [rsp+58h] [rbp-81h] BYREF
  __int128 v69; // [rsp+68h] [rbp-71h] BYREF
  unsigned int v70; // [rsp+78h] [rbp-61h] BYREF
  unsigned int v71; // [rsp+7Ch] [rbp-5Dh] BYREF
  __int64 v72; // [rsp+80h] [rbp-59h] BYREF
  unsigned int v73; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v74[32]; // [rsp+90h] [rbp-49h] BYREF
  __int64 *v75; // [rsp+B0h] [rbp-29h]
  __int64 v76; // [rsp+B8h] [rbp-21h]
  _BYTE v77[16]; // [rsp+C0h] [rbp-19h] BYREF
  const char *v78; // [rsp+D0h] [rbp-9h]
  __int64 v79; // [rsp+D8h] [rbp-1h]
  int *v80; // [rsp+E0h] [rbp+7h]
  __int64 v81; // [rsp+E8h] [rbp+Fh]

  v3 = a2;
  v66 = 0;
  v70 = 0;
  v67 = 0;
  v71 = 0;
  v65 = 0;
  v68 = 0;
  v69 = 0;
  TraceLogHelper("IkeStorePeerUrlEncodedCerts", 1);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v7 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    TlsPeerAddr = IkeGetTlsPeerAddr(v6);
    TlsMmLuid = IkeGetTlsMmLuid(v9);
    WPP_SF_iSL(v7, 138, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, TlsMmLuid, TlsPeerAddr, v3);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v72 = IkeGetTlsMmLuid(v6);
    v75 = &v72;
    v76 = 8;
    v12 = (const WCHAR *)IkeGetTlsPeerAddr(v11);
    tlgCreate1Sz_wchar_t((__int64)v77, v12);
    v79 = 40;
    v80 = (int *)&v73;
    v78 = "Peer sent Hash & Url cert encoding type";
    v73 = v3;
    v81 = 4;
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)&word_180156466,
      v13,
      v14,
      6,
      (__int64)v74);
  }
  if ( *(_DWORD *)(a1 + 584) != 2 )
    goto LABEL_16;
  IkeGetCertAuthFromPolicy(*(_QWORD *)(a1 + 736), *(unsigned int *)(*(_QWORD *)(a1 + 1104) + 504LL), &v65);
  if ( (*(_BYTE *)(v65 + 48) & 0x10) == 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v15 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v16 = IkeGetTlsPeerAddr(v6);
      v18 = IkeGetTlsMmLuid(v17);
      WPP_SF_iS(v15, 139, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v18, v16);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_16;
    v72 = IkeGetTlsMmLuid(v6);
    v75 = &v72;
    v76 = 8;
    v20 = (const WCHAR *)IkeGetTlsPeerAddr(v19);
    tlgCreate1Sz_wchar_t((__int64)v77, v20);
    v79 = 70;
    v78 = "Peer sent Hash & Url cert encoding, but local policy doesn't allow it";
    v23 = (unsigned __int8 *)qword_180156428;
    goto LABEL_15;
  }
  v28 = *a3;
  if ( *a3 <= 0x14 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v29 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v30 = IkeGetTlsPeerAddr(v6);
      v32 = IkeGetTlsMmLuid(v31);
      LODWORD(v64) = v28;
      WPP_SF_iSL(v29, 140, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v32, v30, v64);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v72 = IkeGetTlsMmLuid(v6);
      v75 = &v72;
      v76 = 8;
      v34 = (const WCHAR *)IkeGetTlsPeerAddr(v33);
      tlgCreate1Sz_wchar_t((__int64)v77, v34);
      v73 = *a3;
      v78 = "Peer didnt send encough cert data";
      v80 = (int *)&v73;
      v79 = 34;
      v81 = 4;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_180156503,
        v35,
        v36,
        6,
        (__int64)v74);
    }
    goto LABEL_16;
  }
  CertInfo = IkeGetCertInfo(a1);
  v38 = *(_DWORD *)(CertInfo + 80);
  if ( (v38 & 4) != 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v39 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v40 = IkeGetTlsPeerAddr(v6);
      v42 = IkeGetTlsMmLuid(v41);
      WPP_SF_iS(v39, 141, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v42, v40);
    }
    if ( (unsigned int)dword_180173278 <= 4 )
      goto LABEL_16;
    v72 = IkeGetTlsMmLuid(v6);
    v75 = &v72;
    v76 = 8;
    v44 = (const WCHAR *)IkeGetTlsPeerAddr(v43);
    tlgCreate1Sz_wchar_t((__int64)v77, v44);
    v79 = 57;
    v78 = "Peer sent more than 1 cert with Hash & Url cert encoding";
    v23 = (unsigned __int8 *)byte_1801564BD;
LABEL_15:
    tlgWriteTransfer_EtwEventWriteTransfer((__int64)&dword_180173278, v23, v21, v22, 5, (__int64)v74);
    goto LABEL_16;
  }
  *(_DWORD *)(CertInfo + 80) = v38 | 4;
  v45 = *((_QWORD *)a3 + 1);
  *((_QWORD *)&v68 + 1) = v45 + 20;
  LODWORD(v68) = *a3 - 20;
  v26 = IkeDownloadCertInfoFromUrl((unsigned int *)&v68, (_BYTE)v3 == 13, &v69, 0, &v66, &v70, &v67, &v71);
  if ( v26 )
    goto LABEL_18;
  v46 = 0;
  for ( i = 0; i != 20; ++i )
  {
    v48 = *(_BYTE *)(*((_QWORD *)&v69 + 1) + i);
    v49 = *(_BYTE *)(v45 + i);
    LOBYTE(v6) = v49 ^ v48;
    v46 |= v6;
  }
  if ( !v46 )
  {
    if ( *(_QWORD *)CertInfo || (v50 = CertOpenStore((LPCSTR)2, 1u, 0, 1u, 0), (*(_QWORD *)CertInfo = v50) != 0) )
    {
      v52 = 0;
      if ( v70 )
      {
        while ( CertAddCertificateContextToStore(*(HCERTSTORE *)CertInfo, v66[v52], 3u, 0) )
        {
          if ( ++v52 >= v70 )
            goto LABEL_43;
        }
        LastError = GetLastError();
        v24 = "CertAddCertificateContextToStore";
        v25 = LastError;
      }
      else
      {
LABEL_43:
        v53 = 0;
        if ( !v71 )
          goto LABEL_18;
        while ( CertAddCRLContextToStore(*(HCERTSTORE *)CertInfo, *(PCCRL_CONTEXT *)(v67 + 8LL * v53), 3u, 0) )
        {
          if ( ++v53 >= v71 )
            goto LABEL_18;
        }
        v55 = GetLastError();
        v24 = "CertAddCRLContextToStore";
        v25 = v55;
      }
    }
    else
    {
      v51 = GetLastError();
      v24 = "CertOpenStore";
      v25 = v51;
    }
    goto LABEL_17;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
  {
    v56 = *((_QWORD *)WPP_GLOBAL_Control + 2);
    v57 = IkeGetTlsPeerAddr(v6);
    v59 = IkeGetTlsMmLuid(v58);
    WPP_SF_iS(v56, 142, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v59, v57);
  }
  if ( (unsigned int)dword_180173278 > 4 )
  {
    v72 = IkeGetTlsMmLuid(v6);
    v75 = &v72;
    v76 = 8;
    v61 = (const WCHAR *)IkeGetTlsPeerAddr(v60);
    tlgCreate1Sz_wchar_t((__int64)v77, v61);
    v79 = 54;
    v78 = "Peer sent incorrect hash for Hash & Url cert encoding";
    tlgWriteTransfer_EtwEventWriteTransfer(
      (__int64)&dword_180173278,
      (unsigned __int8 *)byte_1801563E1,
      v62,
      v63,
      5,
      (__int64)v74);
  }
LABEL_16:
  v24 = "IkeStorePeerUrlEncodedCerts";
  v25 = 13835;
LABEL_17:
  v26 = WfpReportSysErrorAsWinError(v6, v24, v25, 1);
LABEL_18:
  IkeFreeCertCtxtArray(v66, v70);
  IkeFreeCrlCtxtArray(v67, v71);
  WfpMemFree((LPCVOID *)&v69 + 1);
  TraceLogHelper("IkeStorePeerUrlEncodedCerts", 0);
  return IkeReturnError(v26, "IkeStorePeerUrlEncodedCerts");
}

```

## disassembly

```asm
0x180092350  mov     [rsp-8+arg_8], rbx
0x180092355  push    rbp
0x180092356  push    rsi
0x180092357  push    rdi
0x180092358  push    r12
0x18009235a  push    r13
0x18009235c  push    r14
0x18009235e  push    r15
0x180092360  lea     rbp, [rsp-27h]
0x180092365  sub     rsp, 100h
0x18009236c  mov     rax, cs:__security_cookie
0x180092373  xor     rax, rsp
0x180092376  mov     [rbp+57h+var_40], rax
0x18009237a  xor     r13d, r13d
0x18009237d  movzx   r12d, dl
0x180092381  mov     r14, rcx
0x180092384  mov     [rsp+130h+var_E8], r13
0x180092389  xorps   xmm0, xmm0
0x18009238c  mov     [rbp+57h+var_B8], r13d
0x180092390  xorps   xmm1, xmm1
0x180092393  mov     [rsp+130h+var_E0], r13
0x180092398  lea     edx, [r13+1]
0x18009239c  mov     [rbp+57h+var_B4], r13d
0x1800923a0  lea     rcx, aIkestorepeerur; "IkeStorePeerUrlEncodedCerts"
0x1800923a7  mov     [rsp+130h+var_F0], r13
0x1800923ac  mov     r15, r8
0x1800923af  movups  [rsp+130h+var_D8], xmm0
0x1800923b4  movups  [rbp+57h+var_C8], xmm1
0x1800923b8  call    TraceLogHelper
0x1800923bd  mov     rsi, cs:WPP_GLOBAL_Control
0x1800923c4  lea     rax, WPP_GLOBAL_Control
0x1800923cb  mov     bl, 10h
0x1800923cd  cmp     rsi, rax
0x1800923d0  jz      short loc_180092411
0x1800923d2  cmp     byte ptr [rsi+19h], 4
0x1800923d6  jb      short loc_180092411
0x1800923d8  test    [rsi+1Ch], bl
0x1800923db  jz      short loc_180092411
0x1800923dd  mov     rsi, [rsi+10h]
0x1800923e1  call    IkeGetTlsPeerAddr
0x1800923e6  mov     rbx, rax
0x1800923e9  call    IkeGetTlsMmLuid
0x1800923ee  mov     r9, rax
0x1800923f1  mov     dword ptr [rsp+130h+var_108], r12d
0x1800923f6  mov     edx, 8Ah
0x1800923fb  mov     [rsp+130h+pvPara], rbx
0x180092400  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x180092407  mov     rcx, rsi
0x18009240a  call    WPP_SF_iSL
0x18009240f  mov     bl, 10h
0x180092411  mov     eax, cs:dword_180173278
0x180092417  cmp     eax, 4
0x18009241a  jbe     short loc_180092491
0x18009241c  call    IkeGetTlsMmLuid
0x180092421  mov     [rbp+57h+var_B0], rax
0x180092425  lea     rax, [rbp+57h+var_B0]
0x180092429  mov     [rbp+57h+var_80], rax
0x18009242d  mov     [rbp+57h+var_78], 8
0x180092435  call    IkeGetTlsPeerAddr
0x18009243a  mov     rdx, rax
0x18009243d  lea     rcx, [rbp+57h+var_70]
0x180092441  call    _tlgCreate1Sz_wchar_t
0x180092446  lea     rax, [rbp+57h+var_A8]
0x18009244a  mov     [rbp+57h+var_58], 28h ; '('
0x180092452  mov     [rbp+57h+var_50], rax
0x180092456  lea     rcx, aPeerSentHashUr; "Peer sent Hash & Url cert encoding type"
0x18009245d  lea     rax, [rbp+57h+var_A0]
0x180092461  mov     [rbp+57h+var_60], rcx
0x180092465  mov     [rsp+130h+var_108], rax
0x18009246a  lea     rdx, word_180156466
0x180092471  lea     rcx, dword_180173278
0x180092478  mov     dword ptr [rsp+130h+pvPara], 6
0x180092480  mov     [rbp+57h+var_A8], r12d
0x180092484  mov     [rbp+57h+var_48], 4
0x18009248c  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180092491  cmp     dword ptr [r14+248h], 2
0x180092499  jnz     loc_180092582
0x18009249f  mov     rdx, [r14+450h]
0x1800924a6  lea     r8, [rsp+130h+var_F0]
0x1800924ab  mov     rcx, [r14+2E0h]
0x1800924b2  mov     edx, [rdx+1F8h]
0x1800924b8  call    IkeGetCertAuthFromPolicy
0x1800924bd  mov     rax, [rsp+130h+var_F0]
0x1800924c2  test    [rax+30h], bl
0x1800924c5  jnz     loc_180092604
0x1800924cb  mov     rdi, cs:WPP_GLOBAL_Control
0x1800924d2  lea     rax, WPP_GLOBAL_Control
0x1800924d9  cmp     rdi, rax
0x1800924dc  jz      short loc_180092516
0x1800924de  cmp     byte ptr [rdi+19h], 4
0x1800924e2  jb      short loc_180092516
0x1800924e4  test    [rdi+1Ch], bl
0x1800924e7  jz      short loc_180092516
0x1800924e9  mov     rdi, [rdi+10h]
0x1800924ed  call    IkeGetTlsPeerAddr
0x1800924f2  mov     rbx, rax
0x1800924f5  call    IkeGetTlsMmLuid
0x1800924fa  mov     r9, rax
0x1800924fd  mov     [rsp+130h+pvPara], rbx
0x180092502  mov     edx, 8Bh
0x180092507  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x18009250e  mov     rcx, rdi
0x180092511  call    WPP_SF_iS
0x180092516  mov     eax, cs:dword_180173278
0x18009251c  cmp     eax, 4
0x18009251f  jbe     short loc_180092582
0x180092521  call    IkeGetTlsMmLuid
0x180092526  mov     [rbp+57h+var_B0], rax
0x18009252a  lea     rax, [rbp+57h+var_B0]
0x18009252e  mov     [rbp+57h+var_80], rax
0x180092532  mov     [rbp+57h+var_78], 8
0x18009253a  call    IkeGetTlsPeerAddr
0x18009253f  mov     rdx, rax
0x180092542  lea     rcx, [rbp+57h+var_70]
0x180092546  call    _tlgCreate1Sz_wchar_t
0x18009254b  lea     r10, aPeerSentHashUr_0; "Peer sent Hash & Url cert encoding, but"...
0x180092552  mov     [rbp+57h+var_58], 46h ; 'F'
0x18009255a  mov     [rbp+57h+var_60], r10
0x18009255e  lea     rdx, qword_180156428
0x180092565  lea     rax, [rbp+57h+var_A0]
0x180092569  mov     [rsp+130h+var_108], rax
0x18009256e  mov     dword ptr [rsp+130h+pvPara], 5
0x180092576  lea     rcx, dword_180173278
0x18009257d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180092582  mov     r9d, 1
0x180092588  lea     rdx, aIkestorepeerur; "IkeStorePeerUrlEncodedCerts"
0x18009258f  mov     r8d, 360Bh
0x180092595  call    WfpReportSysErrorAsWinError
0x18009259a  mov     rbx, rax
0x18009259d  mov     edx, [rbp+57h+var_B8]
0x1800925a0  mov     rcx, [rsp+130h+var_E8]
0x1800925a5  call    IkeFreeCertCtxtArray
0x1800925aa  mov     edx, [rbp+57h+var_B4]
0x1800925ad  mov     rcx, [rsp+130h+var_E0]
0x1800925b2  call    IkeFreeCrlCtxtArray
0x1800925b7  lea     rcx, [rbp+57h+var_C8+8]
0x1800925bb  call    WfpMemFree
0x1800925c0  xor     edx, edx
0x1800925c2  lea     rcx, aIkestorepeerur; "IkeStorePeerUrlEncodedCerts"
0x1800925c9  call    TraceLogHelper
0x1800925ce  lea     rdx, aIkestorepeerur; "IkeStorePeerUrlEncodedCerts"
0x1800925d5  mov     rcx, rbx
0x1800925d8  call    IkeReturnError
0x1800925dd  mov     rcx, [rbp+57h+var_40]
0x1800925e1  xor     rcx, rsp; StackCookie
0x1800925e4  call    __security_check_cookie
0x1800925e9  mov     rbx, [rsp+130h+arg_8]
0x1800925f1  add     rsp, 100h
0x1800925f8  pop     r15
0x1800925fa  pop     r14
0x1800925fc  pop     r13
0x1800925fe  pop     r12
0x180092600  pop     rdi
0x180092601  pop     rsi
0x180092602  pop     rbp
0x180092603  retn
0x180092604  mov     esi, [r15]
0x180092607  cmp     esi, 14h
0x18009260a  ja      loc_1800926DE
0x180092610  mov     rdi, cs:WPP_GLOBAL_Control
0x180092617  lea     rax, WPP_GLOBAL_Control
0x18009261e  cmp     rdi, rax
0x180092621  jz      short loc_18009265F
0x180092623  cmp     byte ptr [rdi+19h], 4
0x180092627  jb      short loc_18009265F
0x180092629  test    [rdi+1Ch], bl
0x18009262c  jz      short loc_18009265F
0x18009262e  mov     rdi, [rdi+10h]
0x180092632  call    IkeGetTlsPeerAddr
0x180092637  mov     rbx, rax
0x18009263a  call    IkeGetTlsMmLuid
0x18009263f  mov     r9, rax
0x180092642  mov     dword ptr [rsp+130h+var_108], esi
0x180092646  mov     edx, 8Ch
0x18009264b  mov     [rsp+130h+pvPara], rbx
0x180092650  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x180092657  mov     rcx, rdi
0x18009265a  call    WPP_SF_iSL
0x18009265f  mov     eax, cs:dword_180173278
0x180092665  cmp     eax, 4
0x180092668  jbe     loc_180092582
0x18009266e  call    IkeGetTlsMmLuid
0x180092673  mov     [rbp+57h+var_B0], rax
0x180092677  lea     rax, [rbp+57h+var_B0]
0x18009267b  mov     [rbp+57h+var_80], rax
0x18009267f  mov     [rbp+57h+var_78], 8
0x180092687  call    IkeGetTlsPeerAddr
0x18009268c  mov     rdx, rax
0x18009268f  lea     rcx, [rbp+57h+var_70]
0x180092693  call    _tlgCreate1Sz_wchar_t
0x180092698  mov     eax, [r15]
0x18009269b  lea     rcx, aPeerDidntSendE; "Peer didnt send encough cert data"
0x1800926a2  mov     [rbp+57h+var_A8], eax
0x1800926a5  lea     rdx, byte_180156503
0x1800926ac  lea     rax, [rbp+57h+var_A8]
0x1800926b0  mov     [rbp+57h+var_60], rcx
0x1800926b4  mov     [rbp+57h+var_50], rax
0x1800926b8  lea     rax, [rbp+57h+var_A0]
0x1800926bc  mov     [rsp+130h+var_108], rax
0x1800926c1  mov     dword ptr [rsp+130h+pvPara], 6
0x1800926c9  mov     [rbp+57h+var_58], 22h ; '"'
0x1800926d1  mov     [rbp+57h+var_48], 4
0x1800926d9  jmp     loc_180092576
0x1800926de  mov     rcx, r14
0x1800926e1  call    IkeGetCertInfo
0x1800926e6  mov     rsi, rax
0x1800926e9  mov     eax, [rax+50h]
0x1800926ec  test    al, 4
0x1800926ee  jz      loc_180092797
0x1800926f4  mov     rdi, cs:WPP_GLOBAL_Control
0x1800926fb  lea     rax, WPP_GLOBAL_Control
0x180092702  cmp     rdi, rax
0x180092705  jz      short loc_18009273F
0x180092707  cmp     byte ptr [rdi+19h], 4
0x18009270b  jb      short loc_18009273F
0x18009270d  test    [rdi+1Ch], bl
0x180092710  jz      short loc_18009273F
0x180092712  mov     rdi, [rdi+10h]
0x180092716  call    IkeGetTlsPeerAddr
0x18009271b  mov     rbx, rax
0x18009271e  call    IkeGetTlsMmLuid
0x180092723  mov     r9, rax
0x180092726  mov     [rsp+130h+pvPara], rbx
0x18009272b  mov     edx, 8Dh
0x180092730  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x180092737  mov     rcx, rdi
0x18009273a  call    WPP_SF_iS
0x18009273f  mov     eax, cs:dword_180173278
0x180092745  cmp     eax, 4
0x180092748  jbe     loc_180092582
0x18009274e  call    IkeGetTlsMmLuid
0x180092753  mov     [rbp+57h+var_B0], rax
0x180092757  lea     rax, [rbp+57h+var_B0]
0x18009275b  mov     [rbp+57h+var_80], rax
0x18009275f  mov     [rbp+57h+var_78], 8
0x180092767  call    IkeGetTlsPeerAddr
0x18009276c  mov     rdx, rax
0x18009276f  lea     rcx, [rbp+57h+var_70]
0x180092773  call    _tlgCreate1Sz_wchar_t
0x180092778  lea     rcx, aPeerSentMoreTh; "Peer sent more than 1 cert with Hash & "...
0x18009277f  mov     [rbp+57h+var_58], 39h ; '9'
0x180092787  mov     [rbp+57h+var_60], rcx
0x18009278b  lea     rdx, byte_1801564BD
0x180092792  jmp     loc_180092565
0x180092797  or      eax, 4
0x18009279a  lea     r8, [rbp+57h+var_C8]
0x18009279e  mov     [rsi+50h], eax
0x1800927a1  lea     rcx, [rsp+130h+var_D8]
0x1800927a6  mov     rdi, [r15+8]
0x1800927aa  mov     edx, r13d
0x1800927ad  lea     rax, [rdi+14h]
0x1800927b1  mov     qword ptr [rbp+57h+var_D8+8], rax
0x1800927b5  mov     eax, [r15]
0x1800927b8  sub     eax, 14h
0x1800927bb  mov     dword ptr [rsp+130h+var_D8], eax
0x1800927bf  cmp     r12b, 0Dh
0x1800927c3  lea     rax, [rbp+57h+var_B4]
0x1800927c7  mov     [rsp+130h+var_F8], rax
0x1800927cc  setz    dl
0x1800927cf  lea     rax, [rsp+130h+var_E0]
0x1800927d4  xor     r9d, r9d
0x1800927d7  mov     [rsp+130h+var_100], rax
0x1800927dc  lea     rax, [rbp+57h+var_B8]
0x1800927e0  mov     [rsp+130h+var_108], rax
0x1800927e5  lea     rax, [rsp+130h+var_E8]
0x1800927ea  mov     [rsp+130h+pvPara], rax
0x1800927ef  call    IkeDownloadCertInfoFromUrl
0x1800927f4  mov     rbx, rax
0x1800927f7  test    rax, rax
0x1800927fa  jnz     loc_18009259D
0x180092800  mov     r9, qword ptr [rbp+57h+var_C8+8]
0x180092804  lea     r14d, [rax+1]
0x180092808  mov     r8b, r13b
0x18009280b  mov     rdx, r13
0x18009280e  mov     cl, [r9+rdx]
0x180092812  mov     al, [rdi+rdx]
0x180092815  add     rdx, r14
0x180092818  xor     cl, al
0x18009281a  or      r8b, cl
0x18009281d  cmp     rdx, 14h
0x180092821  jnz     short loc_18009280E
0x180092823  test    r8b, r8b
0x180092826  jnz     loc_180092906
0x18009282c  cmp     [rsi], r13
0x18009282f  jnz     short loc_180092869
0x180092831  xor     r8d, r8d; hCryptProv
0x180092834  mov     [rsp+130h+pvPara], r13; pvPara
0x180092839  mov     r9d, r14d; dwFlags
0x18009283c  mov     edx, r14d; dwEncodingType
0x18009283f  lea     ecx, [r8+2]; lpszStoreProvider
0x180092843  call    cs:__imp_CertOpenStore
0x180092849  mov     [rsi], rax
0x18009284c  test    rax, rax
0x18009284f  jnz     short loc_180092869
0x180092851  call    cs:__imp_GetLastError
0x180092857  mov     r9d, r14d
0x18009285a  lea     rdx, aCertopenstore_0; "CertOpenStore"
0x180092861  mov     r8d, eax
0x180092864  jmp     loc_180092595
0x180092869  mov     edi, r13d
  ... truncated ...
```
