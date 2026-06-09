# KerbAcquireGlobalKdcProxyClientCertContext(void *,_CERT_CONTEXT const * *)

- ea: `0x180095f48`
- end: `0x1800963fd`
- name: `?KerbAcquireGlobalKdcProxyClientCertContext@@YAKPEAXPEAPEBU_CERT_CONTEXT@@@Z`
- size: `1205`
- prototype: `__int64 __fastcall(void *, const struct _CERT_CONTEXT **)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800990f4`

## callees

- `0x1800069a0`
- `0x1800093f0`
- `0x180009afc`
- `0x18000a630`
- `0x180037c64`
- `0x1800514dc`
- `0x1800603d8`
- `0x18008b70c`
- `0x180095f48`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800961cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009629a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800962f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009633e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096015`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096132`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180096185`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800961cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009629a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800962f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009633e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800963d1`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x1800963d1`
- `ntdll!RtlEnterCriticalSection` at `0x180095fed`
- `ntdll!RtlEnterCriticalSection` at `0x180096311`
- `ntdll!RtlEnterCriticalSection` at `0x180095fed`
- `ntdll!RtlEnterCriticalSection` at `0x180096311`
- `ntdll!RtlLeaveCriticalSection` at `0x180096152`
- `ntdll!RtlLeaveCriticalSection` at `0x180096368`
- `ntdll!RtlLeaveCriticalSection` at `0x180096152`
- `ntdll!RtlLeaveCriticalSection` at `0x180096368`
- `CRYPT32!CertCloseStore` at `0x1800963e1`
- `CRYPT32!CertCloseStore` at `0x1800963e1`
- `CRYPT32!CertFreeCertificateChainList` at `0x1800963b4`
- `CRYPT32!CertFreeCertificateChainList` at `0x1800963b4`
- `CRYPT32!CertFreeCertificateChain` at `0x18009639e`
- `CRYPT32!CertFreeCertificateChain` at `0x18009639e`
- `CRYPT32!CertSelectCertificateChains` at `0x180096290`
- `CRYPT32!CertSelectCertificateChains` at `0x180096290`
- `CRYPT32!CertOpenStore` at `0x180096173`
- `CRYPT32!CertOpenStore` at `0x180096173`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180096002`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180096123`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800962e8`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18009632f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180096002`
- `CRYPT32!CertDuplicateCertificateContext` at `0x180096123`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800962e8`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18009632f`
- `CRYPT32!CertFreeCertificateContext` at `0x1800963c2`
- `CRYPT32!CertFreeCertificateContext` at `0x1800963c2`
- `WINHTTP!WinHttpQueryOption` at `0x1800961c2`
- `WINHTTP!WinHttpQueryOption` at `0x1800961c2`

## string_xrefs

- `0x18009618b`: `CertOpenStore failed: %#x`

## pseudocode

```c
__int64 __fastcall KerbAcquireGlobalKdcProxyClientCertContext(void *a1, const struct _CERT_CONTEXT **a2)
{
  void *v2; // r15
  const CERT_CONTEXT *v3; // rsi
  struct _RTL_CRITICAL_SECTION *v5; // rax
  struct _RTL_CRITICAL_SECTION *v6; // r14
  unsigned int v7; // ebx
  struct _RTL_CRITICAL_SECTION *v8; // r15
  _QWORD *v9; // r12
  const struct _CERT_CONTEXT *v10; // rax
  DWORD LastError; // eax
  __int64 v12; // r8
  int v13; // ecx
  int ClientCertContext; // ecx
  const struct _CERT_CONTEXT *v15; // rax
  void *hStore; // r14
  DWORD v17; // eax
  const char *v18; // r9
  __int64 v19; // r8
  _DWORD *v20; // rdx
  __int64 i; // r8
  const CERT_CONTEXT *v22; // rcx
  const struct _CERT_CONTEXT *v23; // rax
  PCCERT_CHAIN_CONTEXT *v24; // rax
  __int64 j; // r14
  void *pvPara; // [rsp+20h] [rbp-59h]
  PCCERT_CHAIN_CONTEXT *prgpSelection; // [rsp+40h] [rbp-39h] BYREF
  _DWORD *Buffer; // [rsp+48h] [rbp-31h] BYREF
  PCCERT_CONTEXT pCertContext; // [rsp+50h] [rbp-29h] BYREF
  HCERTSTORE v31; // [rsp+58h] [rbp-21h]
  struct _KERB_LOGON_SESSION *v32; // [rsp+60h] [rbp-19h]
  const char *v33; // [rsp+68h] [rbp-11h] BYREF
  CERT_SELECT_CRITERIA rgpCriteria; // [rsp+70h] [rbp-9h] BYREF
  int v35; // [rsp+80h] [rbp+7h]
  int v36; // [rsp+84h] [rbp+Bh]
  _QWORD *v37; // [rsp+88h] [rbp+Fh]
  DWORD pcSelection; // [rsp+E8h] [rbp+6Fh] BYREF
  struct _LUID v40; // [rsp+F0h] [rbp+77h] BYREF
  DWORD dwBufferLength; // [rsp+F8h] [rbp+7Fh] BYREF

  v2 = 0;
  v40 = (struct _LUID)999LL;
  v3 = 0;
  v31 = 0;
  *a2 = 0;
  Buffer = 0;
  dwBufferLength = 8;
  v33 = "1.3.6.1.5.5.7.3.2";
  pcSelection = 0;
  prgpSelection = 0;
  pCertContext = 0;
  v5 = (struct _RTL_CRITICAL_SECTION *)KerbLocateLogonSession(&v40, 0);
  v32 = (struct _KERB_LOGON_SESSION *)v5;
  v6 = v5;
  if ( !v5 )
  {
    v7 = 1312;
    KerbTracerT::Log(
      1,
      "KerbAcquireGlobalKdcProxyClientCertContext",
      3358,
      "Failed to locate system logon session: %#x",
      1312);
    goto LABEL_44;
  }
  v8 = v5 + 2;
  v9 = 0;
  v7 = 0;
  RtlEnterCriticalSection(v5 + 2);
  if ( KerbGlobalKdcProxyClientCertContext )
  {
    v10 = CertDuplicateCertificateContext(KerbGlobalKdcProxyClientCertContext);
    *a2 = v10;
    if ( !v10 )
    {
      LastError = GetLastError();
      v12 = 3372;
LABEL_39:
      LODWORD(pvPara) = LastError;
      v7 = LastError;
      KerbTracerT::Log(
        1,
        "KerbAcquireGlobalKdcProxyClientCertContext",
        v12,
        "Failed to duplicate from global cert context: %#x",
        pvPara);
      goto LABEL_40;
    }
    goto LABEL_40;
  }
  if ( v6[10].DebugInfo )
  {
    v40.LowPart = 0;
    v13 = KerbInitializePkCreds((struct _KERB_PRIMARY_CREDENTIAL *)&v6[3], 0);
    if ( v13 < 0 )
    {
      v7 = 1264;
      KerbTracerT::Log(
        1,
        "KerbAcquireGlobalKdcProxyClientCertContext",
        3394,
        "Failed to initialize machine public credentials: %#x, Status %#x",
        1264,
        v13);
      goto LABEL_40;
    }
    if ( !*(_QWORD *)&v6[10].DebugInfo->EntryCount )
    {
      v7 = 87;
      KerbTracerT::Log(
        1,
        "KerbAcquireGlobalKdcProxyClientCertContext",
        3401,
        "Failed to find cert context for machine public credentials: %#x",
        87);
      goto LABEL_40;
    }
    ClientCertContext = KerbGetClientCertContext((struct _KERB_PRIMARY_CREDENTIAL *)&v6[3], &pCertContext);
    if ( ClientCertContext < 0 )
    {
      v7 = 1264;
      KerbTracerT::Log(
        1,
        "KerbAcquireGlobalKdcProxyClientCertContext",
        3412,
        "Failed to duplicate global cert contxt: %#x, Status %#x",
        1264,
        ClientCertContext);
      v3 = pCertContext;
      goto LABEL_40;
    }
    v3 = pCertContext;
    v7 = IsCertValidForTlsClientAuth(pCertContext);
    if ( v7 )
      goto LABEL_40;
    if ( v40.LowPart )
    {
      KerbTracerT::Log(
        22,
        "KerbAcquireGlobalKdcProxyClientCertContext",
        3425,
        "Duplicate global cert context from machine's public credentials\n");
      v15 = CertDuplicateCertificateContext(v3);
      *a2 = v15;
      if ( !v15 )
      {
        LastError = GetLastError();
        v12 = 3432;
        goto LABEL_39;
      }
      KerbGlobalKdcProxyClientCertContext = v3;
LABEL_40:
      RtlLeaveCriticalSection(v8);
      goto LABEL_41;
    }
  }
  RtlLeaveCriticalSection(v8);
  v31 = CertOpenStore((LPCSTR)0xA, 1u, 0, 0x20000u, L"MY");
  hStore = v31;
  if ( v31 )
  {
    if ( WinHttpQueryOption(a1, 0x5Eu, &Buffer, &dwBufferLength) )
    {
      if ( Buffer )
      {
        v9 = MIDL_user_allocate(8LL * (unsigned int)Buffer[2]);
        if ( !v9 )
        {
          v7 = 8;
          goto LABEL_41;
        }
        v20 = Buffer;
        for ( i = 0; (unsigned int)i < Buffer[2]; v20 = Buffer )
        {
          v9[i] = *(_QWORD *)v20 + 16LL * (unsigned int)i;
          i = (unsigned int)(i + 1);
        }
        rgpCriteria.dwType = 1;
        rgpCriteria.ppPara = (void **)&v33;
        rgpCriteria.cPara = 1;
        v35 = 9;
        v36 = v20[2];
        v37 = v9;
        if ( CertSelectCertificateChains(0, 8u, 0, 2u, &rgpCriteria, hStore, &pcSelection, &prgpSelection) )
        {
          if ( pcSelection )
          {
            v3 = CertDuplicateCertificateContext((*(*(*prgpSelection)->rgpChain)->rgpElement)->pCertContext);
            if ( v3 )
            {
              RtlEnterCriticalSection(v8);
              v22 = KerbGlobalKdcProxyClientCertContext;
              if ( !KerbGlobalKdcProxyClientCertContext )
              {
                v22 = v3;
                v3 = 0;
                KerbGlobalKdcProxyClientCertContext = v22;
              }
              v23 = CertDuplicateCertificateContext(v22);
              *a2 = v23;
              if ( v23 )
                goto LABEL_40;
              LastError = GetLastError();
              v12 = 3558;
              goto LABEL_39;
            }
            v17 = GetLastError();
            v18 = "Failed to duplicate cert context: %#x";
            v19 = 3540;
          }
          else
          {
            v17 = 1168;
            v18 = "CertSelectCertificateChains found no suitable chain: %#x";
            v19 = 3527;
          }
        }
        else
        {
          v17 = GetLastError();
          v18 = "CertSelectCertificateChains failed: %#x";
          v19 = 3520;
        }
      }
      else
      {
        v17 = 1168;
        v18 = "WinHttpQueryOption returns no issuer list: %#x";
        v19 = 3481;
      }
    }
    else
    {
      v17 = GetLastError();
      v18 = "WinHttpQueryOption failed to get issuer list: %#x";
      v19 = 3474;
    }
  }
  else
  {
    v17 = GetLastError();
    v18 = "CertOpenStore failed: %#x";
    v19 = 3460;
  }
  LODWORD(pvPara) = v17;
  v7 = v17;
  KerbTracerT::Log(1, "KerbAcquireGlobalKdcProxyClientCertContext", v19, v18, pvPara);
LABEL_41:
  KerbDereferenceLogonSession(v32);
  if ( v9 )
    KerbFree(v9);
  v2 = v31;
LABEL_44:
  v24 = prgpSelection;
  if ( prgpSelection )
  {
    for ( j = 0; (unsigned int)j < pcSelection; j = (unsigned int)(j + 1) )
    {
      CertFreeCertificateChain(v24[j]);
      v24 = prgpSelection;
    }
    CertFreeCertificateChainList(v24);
  }
  if ( v3 )
    CertFreeCertificateContext(v3);
  if ( Buffer )
    GlobalFree(Buffer);
  if ( v2 )
    CertCloseStore(v2, 0);
  return v7;
}

```

## disassembly

```asm
0x180095f48  mov     [rsp-8+hInternet], rcx
0x180095f4d  push    rbp
0x180095f4e  push    rbx
0x180095f4f  push    rsi
0x180095f50  push    rdi
0x180095f51  push    r12
0x180095f53  push    r13
0x180095f55  push    r14
0x180095f57  push    r15
0x180095f59  lea     rbp, [rsp-1Fh]
0x180095f5e  sub     rsp, 98h
0x180095f65  xor     r15d, r15d
0x180095f68  mov     qword ptr [rbp+57h+arg_10.LowPart], 3E7h
0x180095f70  xor     esi, esi
0x180095f72  mov     [rbp+57h+var_78], r15
0x180095f76  mov     [rdx], rsi
0x180095f79  lea     rax, a136155732; "1.3.6.1.5.5.7.3.2"
0x180095f80  mov     r13, rdx
0x180095f83  mov     [rbp+57h+Buffer], r15
0x180095f87  xor     edx, edx; unsigned __int8
0x180095f89  mov     [rbp+57h+dwBufferLength], 8
0x180095f90  lea     rcx, [rbp+57h+arg_10]; struct _LUID *
0x180095f94  mov     [rbp+57h+var_68], rax
0x180095f98  mov     [rbp+57h+arg_8], r15d
0x180095f9c  mov     [rbp+57h+prgpSelection], r15
0x180095fa0  mov     [rbp+57h+pCertContext], rsi
0x180095fa4  call    ?KerbLocateLogonSession@@YAPEAU_KERB_LOGON_SESSION@@PEBU_LUID@@E@Z; KerbLocateLogonSession(_LUID const *,uchar)
0x180095fa9  mov     [rbp+57h+var_70], rax
0x180095fad  mov     r14, rax
0x180095fb0  test    rax, rax
0x180095fb3  jnz     short loc_180095FE1
0x180095fb5  lea     edi, [rsi+1]
0x180095fb8  mov     ebx, 520h
0x180095fbd  mov     ecx, edi
0x180095fbf  mov     dword ptr [rsp+0D0h+pvPara], ebx
0x180095fc3  lea     r9, aFailedToLocate_1; "Failed to locate system logon session: "...
0x180095fca  mov     r8d, 0D1Eh
0x180095fd0  lea     rdx, aKerbacquireglo_0; "KerbAcquireGlobalKdcProxyClientCertCont"...
0x180095fd7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180095fdc  jmp     loc_180096388
0x180095fe1  lea     r15, [rax+50h]
0x180095fe5  xor     r12d, r12d
0x180095fe8  mov     rcx, r15; CriticalSection
0x180095feb  xor     ebx, ebx
0x180095fed  call    cs:__imp_RtlEnterCriticalSection
0x180095ff3  mov     rcx, cs:?KerbGlobalKdcProxyClientCertContext@@3PEBU_CERT_CONTEXT@@EB; pCertContext
0x180095ffa  lea     edi, [rbx+1]
0x180095ffd  test    rcx, rcx
0x180096000  jz      short loc_180096026
0x180096002  call    cs:__imp_CertDuplicateCertificateContext
0x180096008  mov     [r13+0], rax
0x18009600c  test    rax, rax
0x18009600f  jnz     loc_180096365
0x180096015  call    cs:__imp_GetLastError
0x18009601b  mov     r8d, 0D2Ch
0x180096021  jmp     loc_18009634A
0x180096026  cmp     [r14+190h], rbx
0x18009602d  jz      loc_18009614F
0x180096033  xor     edx, edx; struct _UNICODE_STRING *
0x180096035  mov     [rbp+57h+arg_10.LowPart], ebx
0x180096038  lea     rcx, [r14+78h]; struct _KERB_PRIMARY_CREDENTIAL *
0x18009603c  call    ?KerbInitializePkCreds@@YAJPEAU_KERB_PRIMARY_CREDENTIAL@@PEAU_UNICODE_STRING@@@Z; KerbInitializePkCreds(_KERB_PRIMARY_CREDENTIAL *,_UNICODE_STRING *)
0x180096041  mov     ecx, eax
0x180096043  test    eax, eax
0x180096045  jns     short loc_180096076
0x180096047  mov     eax, 4F0h
0x18009604c  mov     dword ptr [rsp+0D0h+hStore], ecx
0x180096050  mov     ecx, edi
0x180096052  mov     dword ptr [rsp+0D0h+pvPara], eax
0x180096056  lea     r9, aFailedToInitia_6; "Failed to initialize machine public cre"...
0x18009605d  mov     r8d, 0D42h
0x180096063  lea     rdx, aKerbacquireglo_0; "KerbAcquireGlobalKdcProxyClientCertCont"...
0x18009606a  mov     ebx, eax
0x18009606c  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180096071  jmp     loc_180096365
0x180096076  mov     rax, [r14+190h]
0x18009607d  cmp     [rax+20h], rbx
0x180096081  jnz     short loc_18009609E
0x180096083  mov     ebx, 57h ; 'W'
0x180096088  lea     r9, aFailedToFindCe; "Failed to find cert context for machine"...
0x18009608f  mov     dword ptr [rsp+0D0h+pvPara], ebx
0x180096093  mov     r8d, 0D49h
0x180096099  jmp     loc_180096357
0x18009609e  lea     rdx, [rbp+57h+pCertContext]; struct _CERT_CONTEXT **
0x1800960a2  lea     rcx, [r14+78h]; struct _KERB_PRIMARY_CREDENTIAL *
0x1800960a6  call    ?KerbGetClientCertContext@@YAJPEAU_KERB_PRIMARY_CREDENTIAL@@PEAPEBU_CERT_CONTEXT@@@Z; KerbGetClientCertContext(_KERB_PRIMARY_CREDENTIAL *,_CERT_CONTEXT const * *)
0x1800960ab  mov     ecx, eax
0x1800960ad  test    eax, eax
0x1800960af  jns     short loc_1800960E4
0x1800960b1  mov     eax, 4F0h
0x1800960b6  mov     dword ptr [rsp+0D0h+hStore], ecx
0x1800960ba  mov     ecx, edi
0x1800960bc  mov     dword ptr [rsp+0D0h+pvPara], eax
0x1800960c0  lea     r9, aFailedToDuplic_17; "Failed to duplicate global cert contxt:"...
0x1800960c7  mov     r8d, 0D54h
0x1800960cd  lea     rdx, aKerbacquireglo_0; "KerbAcquireGlobalKdcProxyClientCertCont"...
0x1800960d4  mov     ebx, eax
0x1800960d6  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800960db  mov     rsi, [rbp+57h+pCertContext]
0x1800960df  jmp     loc_180096365
0x1800960e4  mov     rsi, [rbp+57h+pCertContext]
0x1800960e8  lea     rdx, [rbp+57h+arg_10]
0x1800960ec  mov     rcx, rsi; pCertContext
0x1800960ef  call    IsCertValidForTlsClientAuth
0x1800960f4  mov     ebx, eax
0x1800960f6  test    eax, eax
0x1800960f8  jnz     loc_180096365
0x1800960fe  cmp     [rbp+57h+arg_10.LowPart], r12d
0x180096102  jz      short loc_18009614F
0x180096104  lea     r9, aDuplicateGloba; "Duplicate global cert context from mach"...
0x18009610b  mov     r8d, 0D61h
0x180096111  lea     rdx, aKerbacquireglo_0; "KerbAcquireGlobalKdcProxyClientCertCont"...
0x180096118  lea     ecx, [rax+16h]
0x18009611b  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180096120  mov     rcx, rsi; pCertContext
0x180096123  call    cs:__imp_CertDuplicateCertificateContext
0x180096129  mov     [r13+0], rax
0x18009612d  test    rax, rax
0x180096130  jnz     short loc_180096143
0x180096132  call    cs:__imp_GetLastError
0x180096138  mov     r8d, 0D68h
0x18009613e  jmp     loc_18009634A
0x180096143  mov     cs:?KerbGlobalKdcProxyClientCertContext@@3PEBU_CERT_CONTEXT@@EB, rsi; _CERT_CONTEXT const * const KerbGlobalKdcProxyClientCertContext
0x18009614a  jmp     loc_180096365
0x18009614f  mov     rcx, r15; CriticalSection
0x180096152  call    cs:__imp_RtlLeaveCriticalSection
0x180096158  xor     r8d, r8d; hCryptProv
0x18009615b  lea     rax, aMy_0; "MY"
0x180096162  mov     r9d, 20000h; dwFlags
0x180096168  mov     [rsp+0D0h+pvPara], rax; pvPara
0x18009616d  mov     edx, edi; dwEncodingType
0x18009616f  lea     ecx, [r8+0Ah]; lpszStoreProvider
0x180096173  call    cs:__imp_CertOpenStore
0x180096179  mov     [rbp+57h+var_78], rax
0x18009617d  mov     r14, rax
0x180096180  test    rax, rax
0x180096183  jnz     short loc_1800961B1
0x180096185  call    cs:__imp_GetLastError
0x18009618b  lea     r9, aCertopenstoreF; "CertOpenStore failed: %#x"
0x180096192  mov     r8d, 0D84h
0x180096198  lea     rdx, aKerbacquireglo_0; "KerbAcquireGlobalKdcProxyClientCertCont"...
0x18009619f  mov     dword ptr [rsp+0D0h+pvPara], eax
0x1800961a3  mov     ecx, edi
0x1800961a5  mov     ebx, eax
0x1800961a7  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x1800961ac  jmp     loc_18009636E
0x1800961b1  mov     rcx, [rbp+57h+hInternet]; hInternet
0x1800961b5  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x1800961b9  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x1800961bd  mov     edx, 5Eh ; '^'; dwOption
0x1800961c2  call    cs:__imp_WinHttpQueryOption
0x1800961c8  test    eax, eax
0x1800961ca  jnz     short loc_1800961E1
0x1800961cc  call    cs:__imp_GetLastError
0x1800961d2  lea     r9, aWinhttpqueryop_0; "WinHttpQueryOption failed to get issuer"...
0x1800961d9  mov     r8d, 0D92h
0x1800961df  jmp     short loc_180096198
0x1800961e1  mov     rax, [rbp+57h+Buffer]
0x1800961e5  test    rax, rax
0x1800961e8  jnz     short loc_1800961FE
0x1800961ea  mov     eax, 490h
0x1800961ef  lea     r9, aWinhttpqueryop_1; "WinHttpQueryOption returns no issuer li"...
0x1800961f6  mov     r8d, 0D99h
0x1800961fc  jmp     short loc_180096198
0x1800961fe  mov     ecx, [rax+8]
0x180096201  shl     rcx, 3; size
0x180096205  call    MIDL_user_allocate
0x18009620a  mov     r12, rax
0x18009620d  test    rax, rax
0x180096210  jnz     short loc_18009621A
0x180096212  lea     ebx, [rax+8]
0x180096215  jmp     loc_18009636E
0x18009621a  mov     rdx, [rbp+57h+Buffer]
0x18009621e  xor     r8d, r8d
0x180096221  cmp     [rdx+8], r8d
0x180096225  jbe     short loc_180096242
0x180096227  mov     eax, r8d
0x18009622a  shl     rax, 4
0x18009622e  add     rax, [rdx]
0x180096231  mov     [r12+r8*8], rax
0x180096235  add     r8d, edi
0x180096238  mov     rdx, [rbp+57h+Buffer]
0x18009623c  cmp     r8d, [rdx+8]
0x180096240  jb      short loc_180096227
0x180096242  lea     rax, [rbp+57h+var_68]
0x180096246  mov     [rbp+57h+rgpCriteria.dwType], edi
0x180096249  mov     [rbp+57h+rgpCriteria.ppPara], rax
0x18009624d  mov     r9d, 2; cCriteria
0x180096253  mov     [rbp+57h+rgpCriteria.cPara], edi
0x180096256  xor     r8d, r8d; pChainParameters
0x180096259  mov     [rbp+57h+var_50], 9
0x180096260  xor     ecx, ecx; pSelectionContext
0x180096262  mov     eax, [rdx+8]
0x180096265  mov     [rbp+57h+var_4C], eax
0x180096268  lea     edx, [r9+6]; dwFlags
0x18009626c  lea     rax, [rbp+57h+prgpSelection]
0x180096270  mov     [rbp+57h+var_48], r12
0x180096274  mov     [rsp+0D0h+pprgpSelection], rax; pprgpSelection
0x180096279  lea     rax, [rbp+57h+arg_8]
0x18009627d  mov     [rsp+0D0h+pcSelection], rax; pcSelection
0x180096282  lea     rax, [rbp+57h+rgpCriteria]
0x180096286  mov     [rsp+0D0h+hStore], r14; hStore
0x18009628b  mov     [rsp+0D0h+pvPara], rax; rgpCriteria
0x180096290  call    cs:__imp_CertSelectCertificateChains
0x180096296  test    eax, eax
0x180096298  jnz     short loc_1800962B2
0x18009629a  call    cs:__imp_GetLastError
0x1800962a0  lea     r9, aCertselectcert_0; "CertSelectCertificateChains failed: %#x"
0x1800962a7  mov     r8d, 0DC0h
0x1800962ad  jmp     loc_180096198
0x1800962b2  cmp     [rbp+57h+arg_8], 0
0x1800962b6  jnz     short loc_1800962CF
0x1800962b8  mov     eax, 490h
0x1800962bd  lea     r9, aCertselectcert_1; "CertSelectCertificateChains found no su"...
0x1800962c4  mov     r8d, 0DC7h
0x1800962ca  jmp     loc_180096198
0x1800962cf  mov     rax, [rbp+57h+prgpSelection]
0x1800962d3  mov     rcx, [rax]
0x1800962d6  mov     rax, [rcx+10h]
0x1800962da  mov     rcx, [rax]
0x1800962dd  mov     rax, [rcx+10h]
0x1800962e1  mov     rcx, [rax]
0x1800962e4  mov     rcx, [rcx+8]; pCertContext
0x1800962e8  call    cs:__imp_CertDuplicateCertificateContext
0x1800962ee  mov     rsi, rax
0x1800962f1  test    rax, rax
0x1800962f4  jnz     short loc_18009630E
0x1800962f6  call    cs:__imp_GetLastError
0x1800962fc  lea     r9, aFailedToDuplic_11; "Failed to duplicate cert context: %#x"
0x180096303  mov     r8d, 0DD4h
0x180096309  jmp     loc_180096198
0x18009630e  mov     rcx, r15; CriticalSection
0x180096311  call    cs:__imp_RtlEnterCriticalSection
0x180096317  mov     rcx, cs:?KerbGlobalKdcProxyClientCertContext@@3PEBU_CERT_CONTEXT@@EB; _CERT_CONTEXT const * const KerbGlobalKdcProxyClientCertContext
0x18009631e  test    rcx, rcx
0x180096321  jnz     short loc_18009632F
0x180096323  mov     rcx, rsi; pCertContext
0x180096326  xor     esi, esi
0x180096328  mov     cs:?KerbGlobalKdcProxyClientCertContext@@3PEBU_CERT_CONTEXT@@EB, rcx; _CERT_CONTEXT const * const KerbGlobalKdcProxyClientCertContext
0x18009632f  call    cs:__imp_CertDuplicateCertificateContext
0x180096335  mov     [r13+0], rax
0x180096339  test    rax, rax
0x18009633c  jnz     short loc_180096365
0x18009633e  call    cs:__imp_GetLastError
0x180096344  mov     r8d, 0DE6h
0x18009634a  lea     r9, aFailedToDuplic_8; "Failed to duplicate from global cert co"...
0x180096351  mov     dword ptr [rsp+0D0h+pvPara], eax
0x180096355  mov     ebx, eax
0x180096357  lea     rdx, aKerbacquireglo_0; "KerbAcquireGlobalKdcProxyClientCertCont"...
0x18009635e  mov     ecx, edi
0x180096360  call    ?Log@KerbTracerT@@SAXW4WPP_DEFINE_BIT_NAMES@@PEBDK1ZZ; KerbTracerT::Log(WPP_DEFINE_BIT_NAMES,char const *,ulong,char const *,...)
0x180096365  mov     rcx, r15; CriticalSection
0x180096368  call    cs:__imp_RtlLeaveCriticalSection
0x18009636e  mov     rcx, [rbp+57h+var_70]; struct _KERB_LOGON_SESSION *
0x180096372  call    ?KerbDereferenceLogonSession@@YAXPEAU_KERB_LOGON_SESSION@@@Z; KerbDereferenceLogonSession(_KERB_LOGON_SESSION *)
0x180096377  test    r12, r12
0x18009637a  jz      short loc_180096384
0x18009637c  mov     rcx, r12
0x18009637f  call    KerbFree
0x180096384  mov     r15, [rbp+57h+var_78]
0x180096388  mov     rax, [rbp+57h+prgpSelection]
0x18009638c  test    rax, rax
0x18009638f  jz      short loc_1800963BA
0x180096391  xor     r14d, r14d
0x180096394  cmp     [rbp+57h+arg_8], r14d
0x180096398  jbe     short loc_1800963B1
0x18009639a  mov     rcx, [rax+r14*8]; pChainContext
0x18009639e  call    cs:__imp_CertFreeCertificateChain
0x1800963a4  mov     rax, [rbp+57h+prgpSelection]
0x1800963a8  add     r14d, edi
0x1800963ab  cmp     r14d, [rbp+57h+arg_8]
0x1800963af  jb      short loc_18009639A
0x1800963b1  mov     rcx, rax; prgpSelection
0x1800963b4  call    cs:__imp_CertFreeCertificateChainList
0x1800963ba  test    rsi, rsi
0x1800963bd  jz      short loc_1800963C8
0x1800963bf  mov     rcx, rsi; pCertContext
0x1800963c2  call    cs:__imp_CertFreeCertificateContext
0x1800963c8  mov     rcx, [rbp+57h+Buffer]; hMem
0x1800963cc  test    rcx, rcx
0x1800963cf  jz      short loc_1800963D7
0x1800963d1  call    cs:__imp_GlobalFree
0x1800963d7  test    r15, r15
0x1800963da  jz      short loc_1800963E7
0x1800963dc  xor     edx, edx; dwFlags
0x1800963de  mov     rcx, r15; hCertStore
0x1800963e1  call    cs:__imp_CertCloseStore
0x1800963e7  mov     eax, ebx
0x1800963e9  add     rsp, 98h
0x1800963f0  pop     r15
0x1800963f2  pop     r14
0x1800963f4  pop     r13
0x1800963f6  pop     r12
0x1800963f8  pop     rdi
0x1800963f9  pop     rsi
0x1800963fa  pop     rbx
0x1800963fb  pop     rbp
0x1800963fc  retn
```
