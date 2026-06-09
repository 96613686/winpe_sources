# IkeOptionalCheckCACert

- ea: `0x180091c4c`
- end: `0x180091f24`
- name: `IkeOptionalCheckCACert`
- size: `728`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, loader_planting`

## callers

- `0x1800915e4`

## callees

- `0x180001008`
- `0x1800010c8`
- `0x1800061ec`
- `0x180008388`
- `0x1800488f0`
- `0x18004890c`
- `0x18004aa3c`
- `0x180050850`
- `0x18005bc40`
- `0x18005bce4`
- `0x180091c4c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091e8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091ce5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091d65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091e8e`
- `CRYPT32!CertFindExtension` at `0x180091cb3`
- `CRYPT32!CertFindExtension` at `0x180091cb3`
- `CRYPT32!CryptDecodeObject` at `0x180091dcb`
- `CRYPT32!CryptDecodeObject` at `0x180091dcb`

## string_xrefs

- `0x180091d52`: `CertFindExtension (CACheck) failed with the following error.             This is OK as it means cert is not a CA cert`

## pseudocode

```c
__int64 __fastcall IkeOptionalCheckCACert(__int64 a1)
{
  __int64 v2; // r14
  PCERT_EXTENSION Extension; // rax
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  __int64 v7; // r9
  __int64 v8; // rsi
  DWORD v9; // edi
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  DWORD v19; // eax
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // r9
  __int64 v26; // rdi
  __int64 TlsPeerAddr; // rbx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  int TlsMmLuid; // eax
  __int64 v33; // rcx
  __int64 v34; // rax
  DWORD LastError; // eax
  int v36; // r8d
  int v37; // r9d
  DWORD pvStructInfo; // [rsp+28h] [rbp-61h]
  DWORD v40; // [rsp+40h] [rbp-49h] BYREF
  DWORD pcbStructInfo; // [rsp+44h] [rbp-45h] BYREF
  __int64 v42; // [rsp+48h] [rbp-41h] BYREF
  __int64 v43; // [rsp+50h] [rbp-39h] BYREF
  int v44; // [rsp+58h] [rbp-31h]
  _BYTE v45[32]; // [rsp+60h] [rbp-29h] BYREF
  __int64 *v46; // [rsp+80h] [rbp-9h]
  __int64 v47; // [rsp+88h] [rbp-1h]
  _BYTE v48[16]; // [rsp+90h] [rbp+7h] BYREF
  const char *v49; // [rsp+A0h] [rbp+17h]
  __int64 v50; // [rsp+A8h] [rbp+1Fh]
  DWORD *v51; // [rsp+B0h] [rbp+27h]
  __int64 v52; // [rsp+B8h] [rbp+2Fh]

  pcbStructInfo = 12;
  v43 = 0;
  v44 = 0;
  v2 = 0;
  TraceLogHelper("IkeOptionalCheckCACert", 1);
  Extension = CertFindExtension(
                "2.5.29.19",
                *(_DWORD *)(*(_QWORD *)(a1 + 24) + 192LL),
                *(CERT_EXTENSION **)(*(_QWORD *)(a1 + 24) + 200LL));
  if ( Extension )
  {
    if ( CryptDecodeObject(
           1u,
           Extension->pszObjId,
           Extension->Value.pbData,
           Extension->Value.cbData,
           0,
           &v43,
           &pcbStructInfo)
      && (_DWORD)v43
      && ((__int64)gIkeExtGlobals[50].LockSemaphore & 0x8000) != 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
      {
        v26 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        TlsPeerAddr = IkeGetTlsPeerAddr(v23);
        TlsMmLuid = IkeGetTlsMmLuid(v29, v28, v30, v31);
        WPP_SF_iS(v26, 25, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, TlsMmLuid, TlsPeerAddr);
      }
      if ( (unsigned int)dword_180173278 > 4 )
      {
        v42 = IkeGetTlsMmLuid(v23, v22, v24, v25);
        v46 = &v42;
        v47 = 8;
        v34 = IkeGetTlsPeerAddr(v33);
        tlgCreate1Sz_wchar_t(v48, v34);
        v50 = 31;
        v49 = "Ignoring CA Cert due to policy";
        LastError = GetLastError();
        v52 = 4;
        v40 = LastError;
        v51 = &v40;
        tlgWriteTransfer_EtwEventWriteTransfer(
          (unsigned int)&dword_180173278,
          (unsigned int)&dword_18015837C,
          v36,
          v37,
          6,
          (__int64)v45);
      }
      v2 = WfpReportSysErrorAsWinError(v23, "IkeOptionalCheckCACert", 13887, 1);
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    {
      v8 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v9 = GetLastError();
      v11 = IkeGetTlsPeerAddr(v10);
      v16 = IkeGetTlsMmLuid(v13, v12, v14, v15);
      pvStructInfo = v9;
      WPP_SF_iSL(v8, 24, (unsigned int)WPP_867431ae952033dfea5b8d66753a6411_Traceguids, v16, v11, pvStructInfo);
    }
    if ( (unsigned int)dword_180173278 > 4 )
    {
      v42 = IkeGetTlsMmLuid(v5, v4, v6, v7);
      v46 = &v42;
      v47 = 8;
      v18 = IkeGetTlsPeerAddr(v17);
      tlgCreate1Sz_wchar_t(v48, v18);
      v50 = 118;
      v49 = "CertFindExtension (CACheck) failed with the following error.             This is OK as it means cert is not a CA cert";
      v19 = GetLastError();
      v52 = 4;
      v40 = v19;
      v51 = &v40;
      tlgWriteTransfer_EtwEventWriteTransfer(
        (unsigned int)&dword_180173278,
        (unsigned int)&byte_18015840F,
        v20,
        v21,
        6,
        (__int64)v45);
    }
  }
  TraceLogHelper("IkeOptionalCheckCACert", 0);
  return IkeReturnError(v2, "IkeOptionalCheckCACert");
}

```

## disassembly

```asm
0x180091c4c  mov     [rsp-8+arg_8], rbx
0x180091c51  mov     [rsp-8+arg_10], rsi
0x180091c56  push    rbp
0x180091c57  push    rdi
0x180091c58  push    r14
0x180091c5a  lea     rbp, [rsp-47h]
0x180091c5f  sub     rsp, 0D0h
0x180091c66  mov     rax, cs:__security_cookie
0x180091c6d  xor     rax, rsp
0x180091c70  mov     [rbp+57h+var_20], rax
0x180091c74  xor     eax, eax
0x180091c76  mov     [rbp+57h+var_9C], 0Ch
0x180091c7d  mov     rbx, rcx
0x180091c80  mov     [rbp+57h+var_90], rax
0x180091c84  lea     rcx, aIkeoptionalche; "IkeOptionalCheckCACert"
0x180091c8b  mov     [rbp+57h+var_88], eax
0x180091c8e  xor     r14d, r14d
0x180091c91  lea     esi, [rax+1]
0x180091c94  mov     edx, esi
0x180091c96  call    TraceLogHelper
0x180091c9b  mov     rdx, [rbx+18h]
0x180091c9f  lea     rcx, pszObjId; "2.5.29.19"
0x180091ca6  mov     r8, [rdx+0C8h]; rgExtensions
0x180091cad  mov     edx, [rdx+0C0h]; cExtensions
0x180091cb3  call    cs:__imp_CertFindExtension
0x180091cb9  test    rax, rax
0x180091cbc  jnz     loc_180091DA7
0x180091cc2  mov     rsi, cs:WPP_GLOBAL_Control
0x180091cc9  lea     rax, WPP_GLOBAL_Control
0x180091cd0  cmp     rsi, rax
0x180091cd3  jz      short loc_180091D19
0x180091cd5  cmp     byte ptr [rsi+19h], 4
0x180091cd9  jb      short loc_180091D19
0x180091cdb  test    byte ptr [rsi+1Ch], 10h
0x180091cdf  jz      short loc_180091D19
0x180091ce1  mov     rsi, [rsi+10h]
0x180091ce5  call    cs:__imp_GetLastError
0x180091ceb  mov     edi, eax
0x180091ced  call    IkeGetTlsPeerAddr
0x180091cf2  mov     rbx, rax
0x180091cf5  call    IkeGetTlsMmLuid
0x180091cfa  mov     r9, rax
0x180091cfd  mov     dword ptr [rsp+0E0h+pvStructInfo], edi
0x180091d01  lea     edx, [r14+18h]
0x180091d05  mov     qword ptr [rsp+0E0h+dwFlags], rbx
0x180091d0a  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x180091d11  mov     rcx, rsi
0x180091d14  call    WPP_SF_iSL
0x180091d19  mov     eax, cs:dword_180173278
0x180091d1f  cmp     eax, 4
0x180091d22  jbe     loc_180091EE3
0x180091d28  call    IkeGetTlsMmLuid
0x180091d2d  mov     [rbp+57h+var_98], rax
0x180091d31  lea     rax, [rbp+57h+var_98]
0x180091d35  mov     [rbp+57h+var_60], rax
0x180091d39  mov     [rbp+57h+var_58], 8
0x180091d41  call    IkeGetTlsPeerAddr
0x180091d46  mov     rdx, rax
0x180091d49  lea     rcx, [rbp+57h+var_50]
0x180091d4d  call    _tlgCreate1Sz_wchar_t
0x180091d52  lea     rcx, aCertfindextens_1; "CertFindExtension (CACheck) failed with"...
0x180091d59  mov     [rbp+57h+var_38], 76h ; 'v'
0x180091d61  mov     [rbp+57h+var_40], rcx
0x180091d65  call    cs:__imp_GetLastError
0x180091d6b  lea     rdx, byte_18015840F
0x180091d72  mov     [rbp+57h+var_28], 4
0x180091d7a  mov     [rbp+57h+var_A0], eax
0x180091d7d  lea     rcx, dword_180173278
0x180091d84  lea     rax, [rbp+57h+var_A0]
0x180091d88  mov     [rbp+57h+var_30], rax
0x180091d8c  lea     rax, [rbp+57h+var_80]
0x180091d90  mov     [rsp+0E0h+pvStructInfo], rax
0x180091d95  mov     [rsp+0E0h+dwFlags], 6
0x180091d9d  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180091da2  jmp     loc_180091EE3
0x180091da7  mov     r9d, [rax+10h]; cbEncoded
0x180091dab  lea     rcx, [rbp+57h+var_9C]
0x180091daf  mov     r8, [rax+18h]; pbEncoded
0x180091db3  mov     rdx, [rax]; lpszStructType
0x180091db6  mov     [rsp+0E0h+pcbStructInfo], rcx; pcbStructInfo
0x180091dbb  lea     rcx, [rbp+57h+var_90]
0x180091dbf  mov     [rsp+0E0h+pvStructInfo], rcx; pvStructInfo
0x180091dc4  mov     ecx, esi; dwCertEncodingType
0x180091dc6  mov     [rsp+0E0h+dwFlags], r14d; dwFlags
0x180091dcb  call    cs:__imp_CryptDecodeObject
0x180091dd1  test    eax, eax
0x180091dd3  jz      loc_180091EE3
0x180091dd9  cmp     dword ptr [rbp+57h+var_90], r14d
0x180091ddd  jz      loc_180091EE3
0x180091de3  mov     rax, cs:gIkeExtGlobals
0x180091dea  test    dword ptr [rax+7E8h], 8000h
0x180091df4  jz      loc_180091EE3
0x180091dfa  mov     rdi, cs:WPP_GLOBAL_Control
0x180091e01  lea     rax, WPP_GLOBAL_Control
0x180091e08  cmp     rdi, rax
0x180091e0b  jz      short loc_180091E46
0x180091e0d  cmp     byte ptr [rdi+19h], 4
0x180091e11  jb      short loc_180091E46
0x180091e13  test    byte ptr [rdi+1Ch], 10h
0x180091e17  jz      short loc_180091E46
0x180091e19  mov     rdi, [rdi+10h]
0x180091e1d  call    IkeGetTlsPeerAddr
0x180091e22  mov     rbx, rax
0x180091e25  call    IkeGetTlsMmLuid
0x180091e2a  mov     r9, rax
0x180091e2d  mov     qword ptr [rsp+0E0h+dwFlags], rbx
0x180091e32  mov     edx, 19h
0x180091e37  lea     r8, WPP_867431ae952033dfea5b8d66753a6411_Traceguids
0x180091e3e  mov     rcx, rdi
0x180091e41  call    WPP_SF_iS
0x180091e46  mov     eax, cs:dword_180173278
0x180091e4c  cmp     eax, 4
0x180091e4f  jbe     short loc_180091ECB
0x180091e51  call    IkeGetTlsMmLuid
0x180091e56  mov     [rbp+57h+var_98], rax
0x180091e5a  lea     rax, [rbp+57h+var_98]
0x180091e5e  mov     [rbp+57h+var_60], rax
0x180091e62  mov     [rbp+57h+var_58], 8
0x180091e6a  call    IkeGetTlsPeerAddr
0x180091e6f  mov     rdx, rax
0x180091e72  lea     rcx, [rbp+57h+var_50]
0x180091e76  call    _tlgCreate1Sz_wchar_t
0x180091e7b  lea     rcx, aIgnoringCaCert; "Ignoring CA Cert due to policy"
0x180091e82  mov     [rbp+57h+var_38], 1Fh
0x180091e8a  mov     [rbp+57h+var_40], rcx
0x180091e8e  call    cs:__imp_GetLastError
0x180091e94  lea     rdx, dword_18015837C
0x180091e9b  mov     [rbp+57h+var_28], 4
0x180091ea3  mov     [rbp+57h+var_A0], eax
0x180091ea6  lea     rcx, dword_180173278
0x180091ead  lea     rax, [rbp+57h+var_A0]
0x180091eb1  mov     [rbp+57h+var_30], rax
0x180091eb5  lea     rax, [rbp+57h+var_80]
0x180091eb9  mov     [rsp+0E0h+pvStructInfo], rax
0x180091ebe  mov     [rsp+0E0h+dwFlags], 6
0x180091ec6  call    _tlgWriteTransfer_EtwEventWriteTransfer
0x180091ecb  mov     r9d, esi
0x180091ece  lea     rdx, aIkeoptionalche; "IkeOptionalCheckCACert"
0x180091ed5  mov     r8d, 363Fh
0x180091edb  call    WfpReportSysErrorAsWinError
0x180091ee0  mov     r14, rax
0x180091ee3  xor     edx, edx
0x180091ee5  lea     rcx, aIkeoptionalche; "IkeOptionalCheckCACert"
0x180091eec  call    TraceLogHelper
0x180091ef1  lea     rdx, aIkeoptionalche; "IkeOptionalCheckCACert"
0x180091ef8  mov     rcx, r14
0x180091efb  call    IkeReturnError
0x180091f00  mov     rcx, [rbp+57h+var_20]
0x180091f04  xor     rcx, rsp; StackCookie
0x180091f07  call    __security_check_cookie
0x180091f0c  lea     r11, [rsp+0E0h+var_10]
0x180091f14  mov     rbx, [r11+28h]
0x180091f18  mov     rsi, [r11+30h]
0x180091f1c  mov     rsp, r11
0x180091f1f  pop     r14
0x180091f21  pop     rdi
0x180091f22  pop     rbp
0x180091f23  retn
```
