# EscalateAsPNRPNode(CRATicket *,CReadWriteLock *,void * *,ushort *)

- ea: `0x140027f24`
- end: `0x1400287aa`
- name: `?EscalateAsPNRPNode@@YAJPEAVCRATicket@@PEAVCReadWriteLock@@PEAPEAXPEAG@Z`
- size: `2182`
- prototype: `__int64 __fastcall(struct CRATicket *, struct CReadWriteLock *, void **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140031440`

## callees

- `0x1400020f4`
- `0x140002156`
- `0x140002463`
- `0x1400080fc`
- `0x1400269f0`
- `0x140027f24`
- `0x140029418`
- `0x14002b26c`
- `0x140034ce4`
- `0x140040390`
- `0x140040a30`
- `0x140041704`
- `0x1400417f8`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `ADVAPI32!CryptEncrypt` at `0x140028451`
- `ADVAPI32!CryptEncrypt` at `0x14002853d`
- `ADVAPI32!CryptEncrypt` at `0x140028451`
- `ADVAPI32!CryptEncrypt` at `0x14002853d`
- `KERNEL32!GetTickCount` at `0x14002817e`
- `KERNEL32!GetTickCount` at `0x1400281b1`
- `KERNEL32!GetTickCount` at `0x14002817e`
- `KERNEL32!GetTickCount` at `0x1400281b1`
- `msvcrt!_time64` at `0x1400282a5`
- `msvcrt!_time64` at `0x1400282a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140028247`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002825e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400284a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400284f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002862d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140028641`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140028247`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002825e`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400284a5`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1400284f4`
- `msvcrt!??_V@YAXPEAX@Z` at `0x14002862d`
- `msvcrt!??_V@YAXPEAX@Z` at `0x140028641`
- `OLEAUT32!__imp_SysAllocString` at `0x140028201`
- `OLEAUT32!__imp_SysAllocString` at `0x140028300`
- `OLEAUT32!__imp_SysAllocString` at `0x140028201`
- `OLEAUT32!__imp_SysAllocString` at `0x140028300`
- `OLEAUT32!__imp_SysFreeString` at `0x140028371`
- `OLEAUT32!__imp_SysFreeString` at `0x140028714`
- `OLEAUT32!__imp_SysFreeString` at `0x14002872a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002873f`
- `OLEAUT32!__imp_SysFreeString` at `0x140028753`
- `OLEAUT32!__imp_SysFreeString` at `0x140028767`
- `OLEAUT32!__imp_SysFreeString` at `0x140028371`
- `OLEAUT32!__imp_SysFreeString` at `0x140028714`
- `OLEAUT32!__imp_SysFreeString` at `0x14002872a`
- `OLEAUT32!__imp_SysFreeString` at `0x14002873f`
- `OLEAUT32!__imp_SysFreeString` at `0x140028753`
- `OLEAUT32!__imp_SysFreeString` at `0x140028767`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140028571`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x140028571`

## string_xrefs

- `0x140027ff8`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x14002804b`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x140028109`: `base\diagnosis\ra\ui\commonfunc.cpp`
- `0x1400283fe`: `CRAEncryption::LoopEncrypt`
- `0x1400285a0`: `CRAEncryption::LoopEncrypt`
- `0x1400285d1`: `CRAEncryption::LoopEncrypt`
- `0x140028605`: `CRAEncryption::LoopEncrypt`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall EscalateAsPNRPNode(struct CRATicket *a1, struct CReadWriteLock *a2, void **a3, unsigned __int16 *a4)
{
  unsigned __int16 *v4; // r12
  OLECHAR *v7; // r13
  unsigned __int16 *v8; // r14
  CEventLogger *v9; // rcx
  struct CReadWriteLock *v10; // r8
  BSTR v11; // r15
  unsigned int v12; // r9d
  signed int v13; // ebx
  signed int RAConnectionString; // eax
  CEventLogger *v15; // rcx
  OLECHAR *v16; // rdi
  signed int v17; // eax
  CEventLogger *v18; // rcx
  _DWORD *v19; // r15
  unsigned __int8 *v20; // rax
  unsigned __int8 *v21; // r14
  signed int v22; // eax
  signed int i; // r8d
  CEventLogger *v24; // rcx
  signed int v25; // eax
  CEventLogger *v26; // rcx
  unsigned __int16 *v27; // rax
  CEventLogger *v28; // rcx
  signed int v29; // eax
  CEventLogger *v30; // rcx
  signed int EncryptedDataAsBSTR; // eax
  CEventLogger *v32; // rcx
  __int64 v33; // rax
  DWORD dwBufLen; // r12d
  signed int v35; // eax
  CEventLogger *v36; // rcx
  CEventLogger *v37; // rcx
  BYTE *v38; // r14
  DWORD v39; // r13d
  DWORD v40; // eax
  OLECHAR *v41; // rax
  CEventLogger *v42; // rcx
  BYTE *v43; // rax
  unsigned int v44; // r9d
  unsigned int v45; // r9d
  signed int v46; // eax
  CEventLogger *v47; // rcx
  BYTE *pbData; // [rsp+20h] [rbp-E0h]
  DWORD len; // [rsp+40h] [rbp-C0h] BYREF
  void *Src; // [rsp+48h] [rbp-B8h]
  unsigned __int16 *v52; // [rsp+50h] [rbp-B0h] BYREF
  BSTR v53; // [rsp+58h] [rbp-A8h]
  BSTR bstrString; // [rsp+60h] [rbp-A0h] BYREF
  int v55; // [rsp+68h] [rbp-98h]
  __time64_t Time; // [rsp+70h] [rbp-90h] BYREF
  BSTR v57; // [rsp+78h] [rbp-88h]
  BSTR v58; // [rsp+80h] [rbp-80h] BYREF
  HCRYPTKEY v59[4]; // [rsp+88h] [rbp-78h] BYREF
  HCRYPTKEY hKey; // [rsp+A8h] [rbp-58h]
  __int64 v61; // [rsp+B0h] [rbp-50h]
  unsigned __int8 v62[16]; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v63[6]; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD v64[2]; // [rsp+F8h] [rbp-8h]
  _OWORD v65[2]; // [rsp+118h] [rbp+18h]
  OLECHAR psz[1024]; // [rsp+140h] [rbp+40h] BYREF
  char v67[2048]; // [rsp+940h] [rbp+840h] BYREF

  v4 = a4;
  Src = a4;
  bstrString = a4;
  v58 = 0;
  v7 = 0;
  v57 = 0;
  v8 = 0;
  *(_OWORD *)v62 = 0;
  memset(v59, 0, sizeof(v59));
  hKey = 0;
  v61 = 0;
  Time = 0;
  memset_0(psz, 0, sizeof(psz));
  memset_0(v67, 0, sizeof(v67));
  v11 = 0;
  v53 = 0;
  v55 = 0;
  if ( !a1 )
  {
    v12 = 4841;
LABEL_3:
    v13 = -2147467261;
    CEventLogger::LogError(
      v9,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      v12,
      L"EscalateAsPNRPNode",
      0x80004003);
    goto LABEL_76;
  }
  if ( !a2 )
  {
    v12 = 4842;
    goto LABEL_3;
  }
  if ( !v4 )
  {
    RAConnectionString = GetRAConnectionString(&bstrString, a1, v10);
    v13 = RAConnectionString;
    if ( RAConnectionString < 0 )
    {
      CEventLogger::LogError(
        v15,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x12EEu,
        L"EscalateAsPNRPNode",
        RAConnectionString);
      v16 = bstrString;
      goto LABEL_77;
    }
    v55 = 1;
    v4 = bstrString;
    Src = bstrString;
  }
  v17 = CreatePassword(6u, &v58);
  v13 = v17;
  if ( v17 < 0 )
  {
    CEventLogger::LogError(
      v18,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x12F4u,
      L"EscalateAsPNRPNode",
      v17);
    goto LABEL_76;
  }
  v64[0] = *(_OWORD *)L"BCDFGHJKLMNPQRSTVWXYZ23456789";
  v64[1] = *(_OWORD *)L"LMNPQRSTVWXYZ23456789";
  v65[0] = *(_OWORD *)L"VWXYZ23456789";
  *(_OWORD *)((char *)v65 + 12) = *(_OWORD *)L"3456789";
  memset(v63, 0, sizeof(v63));
  v19 = operator new[](0xEu, (const struct std::nothrow_t *)&std::nothrow);
  v20 = (unsigned __int8 *)operator new[](6u, (const struct std::nothrow_t *)&std::nothrow);
  v21 = v20;
  if ( v19 )
  {
    if ( v20 )
    {
      *(_QWORD *)v19 = 0;
      v19[2] = 0;
      *((_WORD *)v19 + 6) = 0;
      *(_DWORD *)v20 = 0;
      *((_WORD *)v20 + 2) = 0;
      GetTickCount();
      v22 = CRAEncryption::DeriveBytes((CRAEncryption *)v63, v4, v21, 6u);
      v13 = v22;
      if ( v22 >= 0 )
      {
        GetTickCount();
        for ( i = 0; (unsigned int)i < 6; ++i )
          *((_WORD *)v19 + i) = *((_WORD *)v64 + (unsigned int)(int)(float)((double)v21[i] * 0.00390625 * 29.0));
        v7 = SysAllocString((const OLECHAR *)v19);
        v57 = v7;
        if ( !v7 )
        {
          v13 = -2147467261;
          CEventLogger::LogError(
            (CEventLogger *)L"DerivePassword",
            &Recoverable_Error,
            L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
            0x12AEu,
            L"DerivePassword",
            0x80004003);
        }
      }
      else
      {
        CEventLogger::LogError(
          (CEventLogger *)L"DerivePassword",
          &Recoverable_Error,
          L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
          0x1292u,
          L"DerivePassword",
          v22);
      }
    }
    else
    {
      v13 = -2147024882;
      CEventLogger::LogError(
        (CEventLogger *)L"DerivePassword",
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x128Cu,
        L"DerivePassword",
        0x8007000E);
    }
    operator delete[](v19);
  }
  else
  {
    v13 = -2147024882;
    CEventLogger::LogError(
      (CEventLogger *)L"DerivePassword",
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x128Bu,
      L"DerivePassword",
      0x8007000E);
  }
  v11 = 0;
  if ( v21 )
    operator delete[](v21);
  CRAEncryption::~CRAEncryption((CRAEncryption *)v63);
  if ( v13 < 0 )
  {
    CEventLogger::LogError(
      v24,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x12F9u,
      L"EscalateAsPNRPNode",
      v13);
LABEL_28:
    v8 = 0;
    goto LABEL_76;
  }
  _time64(&Time);
  LODWORD(pbData) = (int)Time / 3600;
  v25 = StringCchPrintfW(psz, 0x400u, L"%s%d", v7, pbData);
  v13 = v25;
  if ( v25 < 0 )
  {
    CEventLogger::LogError(
      v26,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1306u,
      L"EscalateAsPNRPNode",
      v25);
    goto LABEL_28;
  }
  v27 = SysAllocString(psz);
  v8 = v27;
  if ( !v27 )
  {
    v13 = -2147024882;
    CEventLogger::LogError(
      v28,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1309u,
      L"EscalateAsPNRPNode",
      0x8007000E);
    goto LABEL_76;
  }
  v29 = CRAEncryption::DeriveBytes((CRAEncryption *)v59, v27, v62, 0x10u);
  v13 = v29;
  if ( v29 < 0 )
  {
    CEventLogger::LogError(
      v30,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x130Du,
      L"EscalateAsPNRPNode",
      v29);
    goto LABEL_76;
  }
  SysFreeString(v8);
  v52 = 0;
  EncryptedDataAsBSTR = GetEncryptedDataAsBSTR(0x10u, v62, &v52);
  v13 = EncryptedDataAsBSTR;
  if ( EncryptedDataAsBSTR < 0 )
  {
    CEventLogger::LogError(
      v32,
      &Recoverable_Error,
      L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
      0x1313u,
      L"EscalateAsPNRPNode",
      EncryptedDataAsBSTR);
LABEL_75:
    v8 = v52;
    goto LABEL_76;
  }
  v33 = -1;
  do
    ++v33;
  while ( v4[v33] );
  dwBufLen = 2 * v33;
  len = 2 * v33;
  v8 = v52;
  v13 = 0;
  if ( v52 )
  {
    v35 = CRAEncryption::InitializeEnh((CRAEncryption *)v59, v52);
    v13 = v35;
    if ( v35 < 0 )
    {
      CEventLogger::LogError(
        v36,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
        0x4BAu,
        L"CRAEncryption::LoopEncrypt",
        v35);
      goto LABEL_70;
    }
  }
  v38 = 0;
  LODWORD(bstrString) = 0;
  v39 = 0;
  while ( 1 )
  {
    if ( !CryptEncrypt(hKey, 0, 1, 0, 0, &len, dwBufLen) )
    {
      v45 = 1230;
      goto LABEL_63;
    }
    v40 = len;
    if ( v39 < len )
      break;
LABEL_54:
    if ( !CryptEncrypt(hKey, 0, 1, 0, v38, &len, v39) )
    {
      v45 = 1270;
LABEL_63:
      CEventLogger::LogError(
        0,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
        v45,
        L"CRAEncryption::LoopEncrypt",
        0);
      v13 = -2147467259;
      goto LABEL_64;
    }
    dwBufLen = len;
    LODWORD(bstrString) = (_DWORD)bstrString + 1;
    if ( (_DWORD)bstrString )
    {
      v53 = SysAllocStringByteLen((LPCSTR)v38, len);
      if ( !v53 )
      {
        v44 = 1299;
        goto LABEL_60;
      }
      goto LABEL_64;
    }
  }
  if ( v38 )
  {
    v41 = (OLECHAR *)operator new[](v39, (const struct std::nothrow_t *)&std::nothrow);
    v11 = v41;
    if ( !v41 )
    {
      v13 = -2147024882;
      CEventLogger::LogError(
        v42,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
        0x4D5u,
        L"CRAEncryption::LoopEncrypt",
        0x8007000E);
      goto LABEL_67;
    }
    memcpy_0(v41, v38, v39);
    operator delete[](v38);
    v40 = len;
  }
  v43 = (BYTE *)operator new[](v40, (const struct std::nothrow_t *)&std::nothrow);
  v38 = v43;
  if ( v43 )
  {
    memset_0(v43, 0, len);
    if ( v11 )
    {
      memcpy_0(v38, v11, v39);
      operator delete[](v11);
      v11 = 0;
    }
    else
    {
      memcpy_0(v38, Src, dwBufLen);
    }
    v39 = len;
    len = dwBufLen;
    goto LABEL_54;
  }
  v44 = 1245;
LABEL_60:
  v13 = -2147024882;
  CEventLogger::LogError(
    v37,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\core\\lib\\raencryption.cpp",
    v44,
    L"CRAEncryption::LoopEncrypt",
    0x8007000E);
LABEL_64:
  if ( v11 )
    operator delete[](v11);
  if ( v38 )
LABEL_67:
    operator delete[](v38);
  if ( v13 >= 0 )
  {
    v46 = StringCchPrintfW(psz, 0x400u, L"%d", 1);
    v13 = v46;
    if ( v46 >= 0 )
    {
      v13 = -2147467263;
      CEventLogger::LogError(
        v47,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x1323u,
        L"EscalateAsPNRPNode",
        0x80004001);
    }
    else
    {
      CEventLogger::LogError(
        v47,
        &Recoverable_Error,
        L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
        0x131Fu,
        L"EscalateAsPNRPNode",
        v46);
    }
    v11 = v53;
    goto LABEL_75;
  }
  v8 = v52;
LABEL_70:
  CEventLogger::LogError(
    v37,
    &Recoverable_Error,
    L"base\\diagnosis\\ra\\ui\\commonfunc.cpp",
    0x131Au,
    L"EscalateAsPNRPNode",
    v13);
  v11 = v53;
LABEL_76:
  v16 = (OLECHAR *)Src;
LABEL_77:
  ReleaseLock(1);
  if ( v13 != -2147483099 && v13 != -2147483122 )
    v13 = -2147483069;
  if ( v55 && v16 )
    SysFreeString(v16);
  if ( v57 )
    SysFreeString(v57);
  if ( v58 )
    SysFreeString(v58);
  if ( v8 )
    SysFreeString(v8);
  if ( v11 )
    SysFreeString(v11);
  CRAEncryption::~CRAEncryption((CRAEncryption *)v59);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x140027f24  mov     [rsp-8+arg_8], rbx
0x140027f29  push    rbp
0x140027f2a  push    rsi
0x140027f2b  push    rdi
0x140027f2c  push    r12
0x140027f2e  push    r13
0x140027f30  push    r14
0x140027f32  push    r15
0x140027f34  lea     rbp, [rsp-1050h]
0x140027f3c  mov     eax, 1150h
0x140027f41  call    _alloca_probe
0x140027f46  sub     rsp, rax
0x140027f49  mov     rax, cs:__security_cookie
0x140027f50  xor     rax, rsp
0x140027f53  mov     [rbp+1080h+var_40], rax
0x140027f5a  mov     r12, r9
0x140027f5d  mov     [rsp+1180h+Src], r9
0x140027f62  mov     rdi, rdx
0x140027f65  mov     rbx, rcx
0x140027f68  mov     [rsp+1180h+bstrString], r9
0x140027f6d  xor     eax, eax
0x140027f6f  mov     [rbp+1080h+var_1100], rax
0x140027f73  mov     r13d, eax
0x140027f76  mov     [rsp+1180h+var_1108], rax
0x140027f7b  mov     r14d, eax
0x140027f7e  xorps   xmm0, xmm0
0x140027f81  movups  xmmword ptr [rbp+1080h+var_10C8], xmm0
0x140027f85  mov     [rbp+1080h+var_10F8], rax
0x140027f89  mov     [rbp+1080h+var_10F0], rax
0x140027f8d  mov     [rbp+1080h+var_10E8], rax
0x140027f91  mov     [rbp+1080h+var_10E0], rax
0x140027f95  mov     [rbp+1080h+hKey], rax
0x140027f99  mov     [rbp+1080h+var_10D0], rax
0x140027f9d  mov     [rsp+1180h+Time], rax
0x140027fa2  mov     esi, 800h
0x140027fa7  mov     r8d, esi; Size
0x140027faa  xor     edx, edx; Val
0x140027fac  lea     rcx, [rbp+1080h+psz]; void *
0x140027fb0  call    memset_0
0x140027fb5  mov     r8d, esi; Size
0x140027fb8  xor     edx, edx; Val
0x140027fba  lea     rcx, [rbp+1080h+var_840]; void *
0x140027fc1  call    memset_0
0x140027fc6  xor     esi, esi
0x140027fc8  mov     r15d, esi
0x140027fcb  mov     [rsp+1180h+var_1128], rsi
0x140027fd0  mov     [rsp+1180h+var_1118], esi
0x140027fd4  test    rbx, rbx
0x140027fd7  jnz     short loc_140028010
0x140027fd9  mov     r9d, 12E9h; unsigned int
0x140027fdf  mov     dword ptr [rsp+1180h+pdwDataLen], 80004003h; unsigned int
0x140027fe7  mov     ebx, 80004003h
0x140027fec  lea     rax, aEscalateaspnrp; "EscalateAsPNRPNode"
0x140027ff3  mov     [rsp+1180h+pbData], rax; unsigned __int16 *
0x140027ff8  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140027fff  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140028006  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002800b  jmp     loc_1400286DF
0x140028010  test    rdi, rdi
0x140028013  jnz     short loc_14002801D
0x140028015  mov     r9d, 12EAh
0x14002801b  jmp     short loc_140027FDF
0x14002801d  test    r12, r12
0x140028020  jnz     short loc_14002807A
0x140028022  mov     rdx, rbx; this
0x140028025  lea     rcx, [rsp+1180h+bstrString]; unsigned __int16 **
0x14002802a  call    ?GetRAConnectionString@@YAJPEAPEAGPEAVCRATicket@@PEAVCReadWriteLock@@@Z; GetRAConnectionString(ushort * *,CRATicket *,CReadWriteLock *)
0x14002802f  mov     ebx, eax
0x140028031  test    eax, eax
0x140028033  jns     short loc_140028068
0x140028035  mov     dword ptr [rsp+1180h+pdwDataLen], eax; unsigned int
0x140028039  lea     rax, aEscalateaspnrp; "EscalateAsPNRPNode"
0x140028040  mov     [rsp+1180h+pbData], rax; unsigned __int16 *
0x140028045  mov     r9d, 12EEh; unsigned int
0x14002804b  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140028052  lea     rdx, Recoverable_Error; struct _EVENT_DESCRIPTOR *
0x140028059  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002805e  mov     rdi, [rsp+1180h+bstrString]
0x140028063  jmp     loc_1400286E4
0x140028068  mov     [rsp+1180h+var_1118], 1
0x140028070  mov     r12, [rsp+1180h+bstrString]
0x140028075  mov     [rsp+1180h+Src], r12
0x14002807a  lea     rdx, [rbp+1080h+var_1100]; unsigned __int16 **
0x14002807e  mov     edi, 6
0x140028083  mov     ecx, edi; unsigned int
0x140028085  call    ?CreatePassword@@YAJIPEAPEAG@Z; CreatePassword(uint,ushort * *)
0x14002808a  mov     ebx, eax
0x14002808c  test    eax, eax
0x14002808e  jns     short loc_14002809F
0x140028090  mov     dword ptr [rsp+1180h+pdwDataLen], eax
0x140028094  mov     r9d, 12F4h
0x14002809a  jmp     loc_140027FEC
0x14002809f  movups  xmm0, xmmword ptr cs:aBcdfghjklmnpqr; "BCDFGHJKLMNPQRSTVWXYZ23456789"
0x1400280a6  movups  [rbp+1080h+var_1088], xmm0
0x1400280aa  movups  xmm1, xmmword ptr cs:aBcdfghjklmnpqr+10h; "LMNPQRSTVWXYZ23456789"
0x1400280b1  movups  [rbp+1080h+var_1078], xmm1
0x1400280b5  movups  xmm0, xmmword ptr cs:aBcdfghjklmnpqr+20h; "VWXYZ23456789"
0x1400280bc  movups  xmmword ptr [rbp+1080h+var_1068], xmm0
0x1400280c0  movups  xmm1, xmmword ptr cs:aBcdfghjklmnpqr+2Ch; "3456789"
0x1400280c7  movups  xmmword ptr [rbp+1080h+var_1068+0Ch], xmm1
0x1400280cb  mov     [rbp+1080h+var_10B8], rsi
0x1400280cf  mov     [rbp+1080h+var_10B0], rsi
0x1400280d3  mov     [rbp+1080h+var_10A8], rsi
0x1400280d7  mov     [rbp+1080h+var_10A0], rsi
0x1400280db  mov     [rbp+1080h+var_1098], rsi
0x1400280df  mov     [rbp+1080h+var_1090], rsi
0x1400280e3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400280ea  mov     ecx, 0Eh; unsigned __int64
0x1400280ef  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400280f4  mov     r15, rax
0x1400280f7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400280fe  mov     rcx, rdi; unsigned __int64
0x140028101  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140028106  mov     r14, rax
0x140028109  lea     rsi, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\ui\\commonfunc.cpp"
0x140028110  lea     rdi, Recoverable_Error
0x140028117  test    r15, r15
0x14002811a  jnz     short loc_14002814B
0x14002811c  mov     ebx, 8007000Eh
0x140028121  mov     dword ptr [rsp+1180h+pdwDataLen], 8007000Eh; unsigned int
0x140028129  lea     rcx, aDerivepassword; "DerivePassword"
0x140028130  mov     [rsp+1180h+pbData], rcx; unsigned __int16 *
0x140028135  mov     r9d, 128Bh; unsigned int
0x14002813b  mov     r8, rsi; unsigned __int16 *
0x14002813e  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x140028141  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028146  jmp     loc_140028253
0x14002814b  test    r14, r14
0x14002814e  jnz     short loc_140028168
0x140028150  mov     ebx, 8007000Eh
0x140028155  mov     dword ptr [rsp+1180h+pdwDataLen], 8007000Eh
0x14002815d  mov     r9d, 128Ch
0x140028163  jmp     loc_14002822D
0x140028168  xor     eax, eax
0x14002816a  mov     [r15], rax
0x14002816d  mov     [r15+8], eax
0x140028171  mov     [r15+0Ch], ax
0x140028176  mov     [r14], eax
0x140028179  mov     [r14+4], ax
0x14002817e  call    cs:__imp_GetTickCount
0x140028185  nop     dword ptr [rax+rax+00h]
0x14002818a  mov     r9d, 6; unsigned int
0x140028190  mov     r8, r14; unsigned __int8 *
0x140028193  mov     rdx, r12; unsigned __int16 *
0x140028196  lea     rcx, [rbp+1080h+var_10B8]; this
0x14002819a  call    ?DeriveBytes@CRAEncryption@@QEAAJPEAGPEAEI@Z; CRAEncryption::DeriveBytes(ushort *,uchar *,uint)
0x14002819f  mov     ebx, eax
0x1400281a1  test    eax, eax
0x1400281a3  jns     short loc_1400281B1
0x1400281a5  mov     dword ptr [rsp+1180h+pdwDataLen], eax
0x1400281a9  mov     r9d, 1292h
0x1400281af  jmp     short loc_14002822D
0x1400281b1  call    cs:__imp_GetTickCount
0x1400281b8  nop     dword ptr [rax+rax+00h]
0x1400281bd  xor     r8d, r8d
0x1400281c0  movsxd  rdx, r8d
0x1400281c3  movzx   eax, byte ptr [rdx+r14]
0x1400281c8  movd    xmm0, eax
0x1400281cc  cvtdq2pd xmm0, xmm0
0x1400281d0  mulsd   xmm0, cs:__real@3f70000000000000
0x1400281d8  mulsd   xmm0, cs:__real@403d000000000000
0x1400281e0  cvtpd2ps xmm0, xmm0
0x1400281e4  cvttss2si rcx, xmm0
0x1400281e9  mov     ecx, ecx
0x1400281eb  movzx   eax, word ptr [rbp+rcx*2+1080h+var_1088]
0x1400281f0  mov     [r15+rdx*2], ax
0x1400281f5  inc     r8d
0x1400281f8  cmp     r8d, 6
0x1400281fc  jb      short loc_1400281C0
0x1400281fe  mov     rcx, r15; psz
0x140028201  call    cs:__imp_SysAllocString
0x140028208  nop     dword ptr [rax+rax+00h]
0x14002820d  mov     r13, rax
0x140028210  mov     [rsp+1180h+var_1108], rax
0x140028215  test    rax, rax
0x140028218  jnz     short loc_140028244
0x14002821a  mov     ebx, 80004003h
0x14002821f  mov     dword ptr [rsp+1180h+pdwDataLen], 80004003h; unsigned int
0x140028227  mov     r9d, 12AEh; unsigned int
0x14002822d  lea     rcx, aDerivepassword; "DerivePassword"
0x140028234  mov     [rsp+1180h+pbData], rcx; unsigned __int16 *
0x140028239  mov     r8, rsi; unsigned __int16 *
0x14002823c  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x14002823f  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028244  mov     rcx, r15
0x140028247  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x14002824e  nop     dword ptr [rax+rax+00h]
0x140028253  xor     r15d, r15d
0x140028256  test    r14, r14
0x140028259  jz      short loc_14002826A
0x14002825b  mov     rcx, r14
0x14002825e  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x140028265  nop     dword ptr [rax+rax+00h]
0x14002826a  lea     rcx, [rbp+1080h+var_10B8]; this
0x14002826e  call    ??1CRAEncryption@@QEAA@XZ; CRAEncryption::~CRAEncryption(void)
0x140028273  test    ebx, ebx
0x140028275  jns     short loc_1400282A0
0x140028277  mov     dword ptr [rsp+1180h+pdwDataLen], ebx; unsigned int
0x14002827b  mov     r9d, 12F9h; unsigned int
0x140028281  lea     rax, aEscalateaspnrp; "EscalateAsPNRPNode"
0x140028288  mov     [rsp+1180h+pbData], rax; unsigned __int16 *
0x14002828d  mov     r8, rsi; unsigned __int16 *
0x140028290  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x140028293  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x140028298  mov     r14, r15
0x14002829b  jmp     loc_1400286DF
0x1400282a0  lea     rcx, [rsp+1180h+Time]; Time
0x1400282a5  call    cs:__imp__time64
0x1400282ac  nop     dword ptr [rax+rax+00h]
0x1400282b1  mov     rax, 48D159E26AF37C05h
0x1400282bb  imul    [rsp+1180h+Time]
0x1400282c0  sar     rdx, 0Ah
0x1400282c4  mov     rax, rdx
0x1400282c7  shr     rax, 3Fh
0x1400282cb  add     rdx, rax
0x1400282ce  mov     dword ptr [rsp+1180h+pbData], edx
0x1400282d2  mov     r9, r13
0x1400282d5  lea     r8, aSD; "%s%d"
0x1400282dc  mov     edx, 400h; unsigned __int64
0x1400282e1  lea     rcx, [rbp+1080h+psz]; unsigned __int16 *
0x1400282e5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1400282ea  mov     ebx, eax
0x1400282ec  test    eax, eax
0x1400282ee  jns     short loc_1400282FC
0x1400282f0  mov     dword ptr [rsp+1180h+pdwDataLen], eax
0x1400282f4  mov     r9d, 1306h
0x1400282fa  jmp     short loc_140028281
0x1400282fc  lea     rcx, [rbp+1080h+psz]; psz
0x140028300  call    cs:__imp_SysAllocString
0x140028307  nop     dword ptr [rax+rax+00h]
0x14002830c  mov     r14, rax
0x14002830f  test    rax, rax
0x140028312  jnz     short loc_140028343
0x140028314  mov     ebx, 8007000Eh
0x140028319  mov     dword ptr [rsp+1180h+pdwDataLen], 8007000Eh; unsigned int
0x140028321  mov     r9d, 1309h; unsigned int
0x140028327  lea     rax, aEscalateaspnrp; "EscalateAsPNRPNode"
0x14002832e  mov     [rsp+1180h+pbData], rax; unsigned __int16 *
0x140028333  mov     r8, rsi; unsigned __int16 *
0x140028336  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x140028339  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002833e  jmp     loc_1400286DF
0x140028343  mov     r13d, 10h
0x140028349  mov     r9d, r13d; unsigned int
0x14002834c  lea     r8, [rbp+1080h+var_10C8]; unsigned __int8 *
0x140028350  mov     rdx, r14; unsigned __int16 *
0x140028353  lea     rcx, [rbp+1080h+var_10F8]; this
0x140028357  call    ?DeriveBytes@CRAEncryption@@QEAAJPEAGPEAEI@Z; CRAEncryption::DeriveBytes(ushort *,uchar *,uint)
0x14002835c  mov     ebx, eax
0x14002835e  test    eax, eax
0x140028360  jns     short loc_14002836E
0x140028362  mov     dword ptr [rsp+1180h+pdwDataLen], eax
0x140028366  mov     r9d, 130Dh
0x14002836c  jmp     short loc_140028327
0x14002836e  mov     rcx, r14; bstrString
0x140028371  call    cs:__imp_SysFreeString
0x140028378  nop     dword ptr [rax+rax+00h]
0x14002837d  mov     [rsp+1180h+var_1130], r15
0x140028382  lea     r8, [rsp+1180h+var_1130]; unsigned __int16 **
0x140028387  lea     rdx, [rbp+1080h+var_10C8]; unsigned __int8 *
0x14002838b  mov     ecx, r13d; unsigned int
0x14002838e  call    ?GetEncryptedDataAsBSTR@@YAJKQEAEPEAPEAG@Z; GetEncryptedDataAsBSTR(ulong,uchar * const,ushort * *)
0x140028393  mov     ebx, eax
0x140028395  test    eax, eax
0x140028397  jns     short loc_1400283BF
0x140028399  mov     dword ptr [rsp+1180h+pdwDataLen], eax; unsigned int
0x14002839d  lea     rax, aEscalateaspnrp; "EscalateAsPNRPNode"
0x1400283a4  mov     [rsp+1180h+pbData], rax; unsigned __int16 *
0x1400283a9  mov     r9d, 1313h; unsigned int
0x1400283af  mov     r8, rsi; unsigned __int16 *
0x1400283b2  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x1400283b5  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1400283ba  jmp     loc_1400286DA
0x1400283bf  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400283c3  inc     rax
0x1400283c6  cmp     [r12+rax*2], r15w
0x1400283cb  jnz     short loc_1400283C3
0x1400283cd  lea     r12d, [rax+rax]
0x1400283d1  mov     [rsp+1180h+len], r12d
0x1400283d6  mov     r14, [rsp+1180h+var_1130]
0x1400283db  mov     [rsp+1180h+var_1130], r14
0x1400283e0  mov     ebx, r15d
0x1400283e3  test    r14, r14
0x1400283e6  jz      short loc_140028424
0x1400283e8  mov     rdx, r14; unsigned __int16 *
0x1400283eb  lea     rcx, [rbp+1080h+var_10F8]; this
0x1400283ef  call    ?InitializeEnh@CRAEncryption@@QEAAJPEAG@Z; CRAEncryption::InitializeEnh(ushort *)
0x1400283f4  mov     ebx, eax
0x1400283f6  test    eax, eax
0x1400283f8  jns     short loc_140028424
0x1400283fa  mov     dword ptr [rsp+1180h+pdwDataLen], eax; unsigned int
0x1400283fe  lea     rax, aCraencryptionL; "CRAEncryption::LoopEncrypt"
0x140028405  mov     [rsp+1180h+pbData], rax; unsigned __int16 *
0x14002840a  mov     r9d, 4BAh; unsigned int
0x140028410  lea     r8, aBaseDiagnosisR_29; "base\\diagnosis\\ra\\core\\lib\\raencry"...
0x140028417  mov     rdx, rdi; struct _EVENT_DESCRIPTOR *
0x14002841a  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x14002841f  jmp     loc_140028656
0x140028424  xor     ecx, ecx
0x140028426  mov     r14d, ecx
  ... truncated ...
```
