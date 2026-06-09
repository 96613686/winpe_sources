# IkeGetIDPayloadFromCert

- ea: `0x180090874`
- end: `0x180090ca4`
- name: `IkeGetIDPayloadFromCert`
- size: `1072`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `loader_planting`

## callers

- `0x18008f628`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800037c4`
- `0x180003c7c`
- `0x180003cf0`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005482c`
- `0x18005bc40`
- `0x180074314`
- `0x180090874`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800908fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800908fc`
- `CRYPT32!CertFindExtension` at `0x180090a83`
- `CRYPT32!CertFindExtension` at `0x180090a83`
- `CRYPT32!CryptDecodeObject` at `0x1800908f2`
- `CRYPT32!CryptDecodeObject` at `0x180090969`
- `CRYPT32!CryptDecodeObject` at `0x180090aba`
- `CRYPT32!CryptDecodeObject` at `0x180090b13`
- `CRYPT32!CryptDecodeObject` at `0x1800908f2`
- `CRYPT32!CryptDecodeObject` at `0x180090969`
- `CRYPT32!CryptDecodeObject` at `0x180090aba`
- `CRYPT32!CryptDecodeObject` at `0x180090b13`

## pseudocode

```c
__int64 __fastcall IkeGetIDPayloadFromCert(__int64 a1, __int64 a2)
{
  DWORD LastError; // eax
  __int64 v5; // rcx
  __int64 v6; // rax
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  int TlsMmLuid; // eax
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // r8
  __int64 v22; // r9
  PCERT_EXTENSION Extension; // rdi
  _QWORD *v24; // r14
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdi
  __int64 v29; // rcx
  __int64 v30; // r12
  __int64 v31; // rdi
  __int64 v32; // rsi
  __int64 v33; // rbx
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // eax
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // r8
  __int64 v42; // r9
  __int64 v43; // rdx
  const WCHAR *v44; // rcx
  void *pvStructInfo; // [rsp+40h] [rbp-69h] BYREF
  void *v47; // [rsp+48h] [rbp-61h] BYREF
  DWORD pcbStructInfo; // [rsp+50h] [rbp-59h] BYREF
  __int64 v49; // [rsp+58h] [rbp-51h] BYREF
  _BYTE v50[32]; // [rsp+60h] [rbp-49h] BYREF
  __int64 *v51; // [rsp+80h] [rbp-29h]
  __int64 v52; // [rsp+88h] [rbp-21h]
  _BYTE v53[16]; // [rsp+90h] [rbp-19h] BYREF
  const char *v54; // [rsp+A0h] [rbp-9h]
  __int64 v55; // [rsp+A8h] [rbp-1h]
  _BYTE v56[16]; // [rsp+B0h] [rbp+7h] BYREF

  pcbStructInfo = 0;
  pvStructInfo = 0;
  v47 = 0;
  TraceLogHelper("IkeGetIDPayloadFromCert", 1);
  if ( !CryptDecodeObject(
          0x10001u,
          (LPCSTR)7,
          *(const BYTE **)(*(_QWORD *)(a1 + 24) + 88LL),
          *(_DWORD *)(*(_QWORD *)(a1 + 24) + 80LL),
          1u,
          0,
          &pcbStructInfo) )
    goto LABEL_2;
  v7 = 0;
  if ( pcbStructInfo )
  {
    v7 = WfpMemAlloc(pcbStructInfo, 0);
    if ( v7 )
      goto LABEL_35;
    if ( !CryptDecodeObject(
            0x10001u,
            (LPCSTR)7,
            *(const BYTE **)(*(_QWORD *)(a1 + 24) + 88LL),
            *(_DWORD *)(*(_QWORD *)(a1 + 24) + 80LL),
            1u,
            pvStructInfo,
            &pcbStructInfo) )
      goto LABEL_2;
    if ( *(_DWORD *)pvStructInfo )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v12 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        TlsPeerAddr = IkeGetTlsPeerAddr(v9);
        TlsMmLuid = IkeGetTlsMmLuid(v15, v14, v16, v17);
        WPP_SF_iS(v12, 112, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, TlsMmLuid, TlsPeerAddr);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v49 = IkeGetTlsMmLuid(v9, v8, v10, v11);
        v51 = &v49;
        v52 = 8;
        v20 = IkeGetTlsPeerAddr(v19);
        tlgCreate1Sz_wchar_t(v53, v20);
        v55 = 32;
        v54 = "Sending cert subject-name as ID";
        tlgWriteTransfer_EtwEventWriteTransfer(
          (__int64)&dword_180173278,
          (unsigned __int8 *)word_180156BF2,
          v21,
          v22,
          5,
          (__int64)v50);
      }
      *(_BYTE *)a2 = 9;
      v7 = WfpBufferCopy(*(void **)(*(_QWORD *)(a1 + 24) + 88LL), *(unsigned int *)(*(_QWORD *)(a1 + 24) + 80LL));
      if ( !v7 )
        *(_DWORD *)(a2 + 8) = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 80LL);
      goto LABEL_35;
    }
  }
  Extension = CertFindExtension(
                "2.5.29.17",
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  if ( !Extension )
    goto LABEL_35;
  pcbStructInfo = 0;
  if ( !CryptDecodeObject(
          0x10001u,
          "2.5.29.17",
          Extension->Value.pbData,
          Extension->Value.cbData,
          1u,
          0,
          &pcbStructInfo) )
    goto LABEL_2;
  if ( !pcbStructInfo )
    goto LABEL_35;
  v7 = WfpMemAlloc(pcbStructInfo, 0);
  if ( v7 )
    goto LABEL_35;
  v24 = v47;
  if ( !CryptDecodeObject(
          0x10001u,
          "2.5.29.17",
          Extension->Value.pbData,
          Extension->Value.cbData,
          1u,
          v47,
          &pcbStructInfo) )
  {
LABEL_2:
    LastError = GetLastError();
    v6 = WfpReportSysErrorAsWinError(v5, "CryptDecodeObject", LastError, 1);
LABEL_34:
    v7 = v6;
    goto LABEL_35;
  }
  if ( *(_DWORD *)v47 )
  {
    v28 = *((_QWORD *)v47 + 1);
    v29 = 0;
    while ( 1 )
    {
      v30 = 3LL * (unsigned int)v29;
      if ( *(_DWORD *)(v28 + 24LL * (unsigned int)v29) == 3 )
        break;
      v29 = (unsigned int)(v29 + 1);
      if ( (unsigned int)v29 >= *(_DWORD *)v47 )
        goto LABEL_35;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v31 = *(_QWORD *)(v28 + 24LL * (unsigned int)v29 + 8);
      v32 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v33 = IkeGetTlsPeerAddr(v29);
      v38 = IkeGetTlsMmLuid(v35, v34, v36, v37);
      WPP_SF_iSS(v32, 113, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v38, v33, v31);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v49 = IkeGetTlsMmLuid(v29, v25, v26, v27);
      v51 = &v49;
      v52 = 8;
      v40 = IkeGetTlsPeerAddr(v39);
      tlgCreate1Sz_wchar_t(v53, v40);
      v55 = 41;
      v54 = "Sending cert subject-alt-name FQDN as ID";
      tlgCreate1Sz_wchar_t(v56, *(_QWORD *)(*((_QWORD *)v47 + 1) + 8 * v30 + 8));
      tlgWriteTransfer_EtwEventWriteTransfer(
        (__int64)&dword_180173278,
        (unsigned __int8 *)byte_180156BA5,
        v41,
        v42,
        6,
        (__int64)v50);
    }
    *(_BYTE *)a2 = 2;
    v43 = -1;
    v44 = *(const WCHAR **)(v24[1] + 8 * v30 + 8);
    do
      ++v43;
    while ( v44[v43] );
    v6 = WfpStringCopyWtoAAlloc(v44, v43, a2 + 8);
    goto LABEL_34;
  }
LABEL_35:
  WfpMemFree(&pvStructInfo);
  WfpMemFree(&v47);
  TraceLogHelper("IkeGetIDPayloadFromCert", 0);
  return IkeReturnError(v7, "IkeGetIDPayloadFromCert");
}

```

## disassembly

```asm
0x180090874  mov     [rsp-8+arg_10], rbx
0x180090879  push    rbp
0x18009087a  push    rsi
0x18009087b  push    rdi
0x18009087c  push    r12
0x18009087e  push    r13
0x180090880  push    r14
0x180090882  push    r15
0x180090884  lea     rbp, [rsp-27h]
0x180090889  sub     rsp, 0D0h
0x180090890  mov     rax, cs:__security_cookie
0x180090897  xor     rax, rsp
0x18009089a  mov     [rbp+57h+var_40], rax
0x18009089e  xor     r13d, r13d
0x1800908a1  mov     r15, rdx
0x1800908a4  mov     rsi, rcx
0x1800908a7  mov     [rbp+57h+var_B0], r13d
0x1800908ab  lea     rcx, aIkegetidpayloa; "IkeGetIDPayloadFromCert"
0x1800908b2  mov     [rbp+57h+var_C0], r13
0x1800908b6  mov     [rbp+57h+var_B8], r13
0x1800908ba  lea     r12d, [r13+1]
0x1800908be  mov     edx, r12d
0x1800908c1  call    TraceLogHelper
0x1800908c6  mov     r8, [rsi+18h]
0x1800908ca  lea     rax, [rbp+57h+var_B0]
0x1800908ce  mov     [rsp+100h+pcbStructInfo], rax; pcbStructInfo
0x1800908d3  lea     edx, [r13+7]; lpszStructType
0x1800908d7  mov     r14d, 10001h
0x1800908dd  mov     [rsp+100h+pvStructInfo], r13; pvStructInfo
0x1800908e2  mov     ecx, r14d; dwCertEncodingType
0x1800908e5  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x1800908ea  mov     r9d, [r8+50h]; cbEncoded
0x1800908ee  mov     r8, [r8+58h]; pbEncoded
0x1800908f2  call    cs:__imp_CryptDecodeObject
0x1800908f8  test    eax, eax
0x1800908fa  jnz     short loc_180090919
0x1800908fc  call    cs:__imp_GetLastError
0x180090902  mov     r9d, r12d
0x180090905  lea     rdx, aCryptdecodeobj_1; "CryptDecodeObject"
0x18009090c  mov     r8d, eax
0x18009090f  call    WfpReportSysErrorAsWinError
0x180090914  jmp     loc_180090C4B
0x180090919  mov     eax, [rbp+57h+var_B0]
0x18009091c  mov     rbx, r13
0x18009091f  test    eax, eax
0x180090921  jz      loc_180090A68
0x180090927  mov     ecx, eax; dwBytes
0x180090929  lea     r8, [rbp+57h+var_C0]
0x18009092d  xor     edx, edx; dwFlags
0x18009092f  call    WfpMemAlloc
0x180090934  mov     rbx, rax
0x180090937  test    rax, rax
0x18009093a  jnz     loc_180090C4E
0x180090940  mov     r8, [rsi+18h]
0x180090944  lea     rax, [rbp+57h+var_B0]
0x180090948  mov     rdi, [rbp+57h+var_C0]
0x18009094c  lea     edx, [rbx+7]; lpszStructType
0x18009094f  mov     [rsp+100h+pcbStructInfo], rax; pcbStructInfo
0x180090954  mov     ecx, r14d; dwCertEncodingType
0x180090957  mov     [rsp+100h+pvStructInfo], rdi; pvStructInfo
0x18009095c  mov     r9d, [r8+50h]; cbEncoded
0x180090960  mov     r8, [r8+58h]; pbEncoded
0x180090964  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x180090969  call    cs:__imp_CryptDecodeObject
0x18009096f  test    eax, eax
0x180090971  jz      short loc_1800908FC
0x180090973  cmp     [rdi], r13d
0x180090976  jbe     loc_180090A68
0x18009097c  mov     rdi, cs:WPP_GLOBAL_Control
0x180090983  lea     rax, WPP_GLOBAL_Control
0x18009098a  cmp     rdi, rax
0x18009098d  jz      short loc_1800909C8
0x18009098f  cmp     byte ptr [rdi+19h], 4
0x180090993  jb      short loc_1800909C8
0x180090995  test    byte ptr [rdi+1Ch], 10h
0x180090999  jz      short loc_1800909C8
0x18009099b  mov     rdi, [rdi+10h]
0x18009099f  call    IkeGetTlsPeerAddr
0x1800909a4  mov     rbx, rax
0x1800909a7  call    IkeGetTlsMmLuid
0x1800909ac  mov     r9, rax
0x1800909af  mov     qword ptr [rsp+100h+dwFlags], rbx
0x1800909b4  mov     edx, 70h ; 'p'
0x1800909b9  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x1800909c0  mov     rcx, rdi
0x1800909c3  call    WPP_SF_iS
0x1800909c8  mov     eax, cs:dword_180173278
0x1800909ce  cmp     eax, 4
0x1800909d1  jbe     short loc_180090A34
0x1800909d3  call    IkeGetTlsMmLuid
0x1800909d8  mov     [rbp+57h+var_A8], rax
0x1800909dc  lea     rax, [rbp+57h+var_A8]
0x1800909e0  mov     [rbp+57h+var_80], rax
0x1800909e4  mov     [rbp+57h+var_78], 8
0x1800909ec  call    IkeGetTlsPeerAddr
0x1800909f1  mov     rdx, rax
0x1800909f4  lea     rcx, [rbp+57h+var_70]
0x1800909f8  call    _tlgCreate1Sz_wchar_t
0x1800909fd  lea     rcx, aSendingCertSub; "Sending cert subject-name as ID"
0x180090a04  mov     [rbp+57h+var_58], 20h ; ' '
0x180090a0c  lea     rax, [rbp+57h+var_A0]
0x180090a10  mov     [rbp+57h+var_60], rcx
0x180090a14  mov     [rsp+100h+pvStructInfo], rax
0x180090a19  lea     rcx, dword_180173278
0x180090a20  lea     rdx, word_180156BF2
0x180090a27  mov     [rsp+100h+dwFlags], 5
0x180090a2f  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180090a34  mov     byte ptr [r15], 9
0x180090a38  lea     r9, [r15+10h]
0x180090a3c  mov     rcx, [rsi+18h]
0x180090a40  mov     edx, [rcx+50h]; Size
0x180090a43  mov     rcx, [rcx+58h]; Src
0x180090a47  call    WfpBufferCopy
0x180090a4c  mov     rbx, rax
0x180090a4f  test    rax, rax
0x180090a52  jnz     loc_180090C4E
0x180090a58  mov     rax, [rsi+18h]
0x180090a5c  mov     ecx, [rax+50h]
0x180090a5f  mov     [r15+8], ecx
0x180090a63  jmp     loc_180090C4E
0x180090a68  mov     rdx, [rsi+18h]
0x180090a6c  lea     rsi, szStructType; "2.5.29.17"
0x180090a73  mov     rcx, rsi; pszObjId
0x180090a76  mov     r8, [rdx+0C8h]; rgExtensions
0x180090a7d  mov     edx, [rdx+0C0h]; cExtensions
0x180090a83  call    cs:__imp_CertFindExtension
0x180090a89  mov     rdi, rax
0x180090a8c  test    rax, rax
0x180090a8f  jz      loc_180090C4E
0x180090a95  mov     [rbp+57h+var_B0], r13d
0x180090a99  lea     rax, [rbp+57h+var_B0]
0x180090a9d  mov     r9d, [rdi+10h]; cbEncoded
0x180090aa1  mov     rdx, rsi; lpszStructType
0x180090aa4  mov     r8, [rdi+18h]; pbEncoded
0x180090aa8  mov     ecx, r14d; dwCertEncodingType
0x180090aab  mov     [rsp+100h+pcbStructInfo], rax; pcbStructInfo
0x180090ab0  mov     [rsp+100h+pvStructInfo], r13; pvStructInfo
0x180090ab5  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x180090aba  call    cs:__imp_CryptDecodeObject
0x180090ac0  test    eax, eax
0x180090ac2  jz      loc_1800908FC
0x180090ac8  mov     eax, [rbp+57h+var_B0]
0x180090acb  test    eax, eax
0x180090acd  jz      loc_180090C4E
0x180090ad3  mov     ecx, eax; dwBytes
0x180090ad5  lea     r8, [rbp+57h+var_B8]
0x180090ad9  xor     edx, edx; dwFlags
0x180090adb  call    WfpMemAlloc
0x180090ae0  mov     rbx, rax
0x180090ae3  test    rax, rax
0x180090ae6  jnz     loc_180090C4E
0x180090aec  mov     r14, [rbp+57h+var_B8]
0x180090af0  lea     rax, [rbp+57h+var_B0]
0x180090af4  mov     r9d, [rdi+10h]; cbEncoded
0x180090af8  mov     rdx, rsi; lpszStructType
0x180090afb  mov     r8, [rdi+18h]; pbEncoded
0x180090aff  mov     ecx, 10001h; dwCertEncodingType
0x180090b04  mov     [rsp+100h+pcbStructInfo], rax; pcbStructInfo
0x180090b09  mov     [rsp+100h+pvStructInfo], r14; pvStructInfo
0x180090b0e  mov     [rsp+100h+dwFlags], r12d; dwFlags
0x180090b13  call    cs:__imp_CryptDecodeObject
0x180090b19  test    eax, eax
0x180090b1b  jz      loc_1800908FC
0x180090b21  cmp     [r14], r13d
0x180090b24  jbe     loc_180090C4E
0x180090b2a  mov     rdi, [r14+8]
0x180090b2e  mov     ecx, r13d
0x180090b31  mov     eax, ecx
0x180090b33  lea     r12, [rax+rax*2]
0x180090b37  cmp     dword ptr [rdi+r12*8], 3
0x180090b3c  jz      short loc_180090B4A
0x180090b3e  inc     ecx
0x180090b40  cmp     ecx, [r14]
0x180090b43  jb      short loc_180090B31
0x180090b45  jmp     loc_180090C4E
0x180090b4a  mov     rsi, cs:WPP_GLOBAL_Control
0x180090b51  lea     rax, WPP_GLOBAL_Control
0x180090b58  cmp     rsi, rax
0x180090b5b  jz      short loc_180090BA0
0x180090b5d  cmp     byte ptr [rsi+19h], 4
0x180090b61  jb      short loc_180090BA0
0x180090b63  test    byte ptr [rsi+1Ch], 10h
0x180090b67  jz      short loc_180090BA0
0x180090b69  mov     rdi, [rdi+r12*8+8]
0x180090b6e  mov     rsi, [rsi+10h]
0x180090b72  call    IkeGetTlsPeerAddr
0x180090b77  mov     rbx, rax
0x180090b7a  call    IkeGetTlsMmLuid
0x180090b7f  mov     r9, rax
0x180090b82  mov     [rsp+100h+pvStructInfo], rdi
0x180090b87  mov     edx, 71h ; 'q'
0x180090b8c  mov     qword ptr [rsp+100h+dwFlags], rbx
0x180090b91  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x180090b98  mov     rcx, rsi
0x180090b9b  call    WPP_SF_iSS
0x180090ba0  mov     eax, cs:dword_180173278
0x180090ba6  cmp     eax, 4
0x180090ba9  jbe     short loc_180090C1E
0x180090bab  call    IkeGetTlsMmLuid
0x180090bb0  mov     [rbp+57h+var_A8], rax
0x180090bb4  lea     rax, [rbp+57h+var_A8]
0x180090bb8  mov     [rbp+57h+var_80], rax
0x180090bbc  mov     [rbp+57h+var_78], 8
0x180090bc4  call    IkeGetTlsPeerAddr
0x180090bc9  mov     rdx, rax
0x180090bcc  lea     rcx, [rbp+57h+var_70]
0x180090bd0  call    _tlgCreate1Sz_wchar_t
0x180090bd5  mov     [rbp+57h+var_58], 29h ; ')'
0x180090bdd  lea     rcx, aSendingCertSub_0; "Sending cert subject-alt-name FQDN as I"...
0x180090be4  mov     [rbp+57h+var_60], rcx
0x180090be8  lea     rcx, [rbp+57h+var_50]
0x180090bec  mov     rdx, [r14+8]
0x180090bf0  mov     rdx, [rdx+r12*8+8]
0x180090bf5  call    _tlgCreate1Sz_wchar_t
0x180090bfa  lea     rcx, [rbp+57h+var_A0]
0x180090bfe  mov     [rsp+100h+pvStructInfo], rcx
0x180090c03  lea     rdx, byte_180156BA5
0x180090c0a  lea     rcx, dword_180173278
0x180090c11  mov     [rsp+100h+dwFlags], 6
0x180090c19  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180090c1e  mov     byte ptr [r15], 2
0x180090c22  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180090c26  mov     rax, [r14+8]
0x180090c2a  mov     rcx, [rax+r12*8+8]; lpWideCharStr
0x180090c2f  inc     rdx; cchWideChar
0x180090c32  cmp     [rcx+rdx*2], r13w
0x180090c37  jnz     short loc_180090C2F
0x180090c39  lea     rax, [r15+8]
0x180090c3d  lea     r9, [r15+10h]
0x180090c41  mov     qword ptr [rsp+100h+dwFlags], rax; __int64
0x180090c46  call    WfpStringCopyWtoAAlloc
0x180090c4b  mov     rbx, rax
0x180090c4e  lea     rcx, [rbp+57h+var_C0]
0x180090c52  call    WfpMemFree
0x180090c57  lea     rcx, [rbp+57h+var_B8]
0x180090c5b  call    WfpMemFree
0x180090c60  xor     edx, edx
0x180090c62  lea     rcx, aIkegetidpayloa; "IkeGetIDPayloadFromCert"
0x180090c69  call    TraceLogHelper
0x180090c6e  lea     rdx, aIkegetidpayloa; "IkeGetIDPayloadFromCert"
0x180090c75  mov     rcx, rbx
0x180090c78  call    IkeReturnError
0x180090c7d  mov     rcx, [rbp+57h+var_40]
0x180090c81  xor     rcx, rsp; StackCookie
0x180090c84  call    __security_check_cookie
0x180090c89  mov     rbx, [rsp+100h+arg_10]
0x180090c91  add     rsp, 0D0h
0x180090c98  pop     r15
0x180090c9a  pop     r14
0x180090c9c  pop     r13
0x180090c9e  pop     r12
0x180090ca0  pop     rdi
0x180090ca1  pop     rsi
0x180090ca2  pop     rbp
0x180090ca3  retn
```
