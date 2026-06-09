# GetCertsOnFile

- ea: `0x18002d450`
- end: `0x18002d882`
- name: `GetCertsOnFile`
- size: `1074`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops`

## callers

- `0x18002d888`

## callees

- `0x18000164c`
- `0x180001920`
- `0x18000270c`
- `0x180003e6c`
- `0x180004d68`
- `0x18001b388`
- `0x180020710`
- `0x18002072c`
- `0x18002d450`
- `0x18002dc20`
- `0x180033e9a`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18002d640`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002d70f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002d640`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18002d70f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d55e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d7ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002d811`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d571`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002d571`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d569`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002d569`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d4f9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002d4f9`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002d6d6`
- `CRYPT32!CertDuplicateCertificateContext` at `0x18002d6d6`
- `CRYPT32!CertDuplicateStore` at `0x18002d6f9`
- `CRYPT32!CertDuplicateStore` at `0x18002d6f9`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18002d66d`
- `WINTRUST!WTHelperProvDataFromStateData` at `0x18002d66d`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002d524`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002d547`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002d524`
- `WINTRUST!CryptCATAdminCalcHashFromFileHandle` at `0x18002d547`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18002d687`
- `WINTRUST!WTHelperGetProvSignerFromChain` at `0x18002d687`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
char __fastcall GetCertsOnFile(_QWORD *a1, WCHAR *a2, PCCERT_CONTEXT *a3, _QWORD *a4)
{
  const WCHAR *v8; // rcx
  HANDLE FileW; // rax
  const char *v10; // r9
  void *v11; // rbx
  BYTE *v12; // rdi
  const char *v13; // r9
  DWORD LastError; // esi
  unsigned int v15; // eax
  CRYPT_PROVIDER_DATA *v17; // rax
  CRYPT_PROVIDER_SGNR *ProvSignerFromChain; // rax
  CRYPT_PROVIDER_SGNR *v19; // rbx
  PCCERT_CHAIN_CONTEXT pChainContext; // rdx
  char v21; // al
  PCCERT_CONTEXT v22; // rax
  const char *v23; // r9
  HCERTSTORE v24; // rax
  const char *v25; // r9
  __int64 v26; // rbx
  unsigned int v27; // eax
  __int64 v28; // rbx
  unsigned int v29; // eax
  int *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  BYTE *v31; // [rsp+40h] [rbp-C0h] BYREF
  int pWVTData; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  __int64 v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+70h] [rbp-90h]
  int *v37; // [rsp+78h] [rbp-88h]
  int v38; // [rsp+80h] [rbp-80h]
  HANDLE hStateData; // [rsp+88h] [rbp-78h]
  __int64 v40; // [rsp+90h] [rbp-70h]
  __int64 v41; // [rsp+98h] [rbp-68h]
  int *p_pWVTData; // [rsp+B0h] [rbp-50h]
  char v43; // [rsp+B8h] [rbp-48h]
  int v44; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD *v45; // [rsp+C8h] [rbp-38h]
  BYTE *v46; // [rsp+D8h] [rbp-28h]
  BYTE *v47; // [rsp+E8h] [rbp-18h]
  DWORD v48; // [rsp+F0h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]
  DWORD pcbHash; // [rsp+158h] [rbp+58h] BYREF
  int v51; // [rsp+160h] [rbp+60h] BYREF
  __int64 v52; // [rsp+168h] [rbp+68h] BYREF

  *a3 = 0;
  *a4 = 0;
  memset_0(&pWVTData, 0, 0x58u);
  pWVTData = 88;
  v33 = 0;
  v34 = 0;
  v35 = 2;
  v41 = 4112;
  v38 = 1;
  hStateData = 0;
  v40 = 0;
  p_pWVTData = &pWVTData;
  v43 = 1;
  if ( *((_QWORD *)a2 + 3) < 8u )
    v8 = a2;
  else
    v8 = *(const WCHAR **)a2;
  FileW = CreateFileW(v8, 0x80000000, 5u, 0, 3u, 0, 0);
  v11 = FileW;
  v52 = (__int64)FileW;
  if ( FileW == (HANDLE)-1LL )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x4E,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
      v10);
  pcbHash = 0;
  CryptCATAdminCalcHashFromFileHandle(FileW, &pcbHash, 0, 0);
  v12 = (BYTE *)operator new[](pcbHash);
  v31 = v12;
  if ( !CryptCATAdminCalcHashFromFileHandle(v11, &pcbHash, v12, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x52,
      (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
      v13);
  if ( v11 )
  {
    LastError = GetLastError();
    CloseHandle(v11);
    SetLastError(LastError);
  }
  v52 = -1;
  memset_0(&v44, 0, 0x48u);
  v44 = 72;
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  v45 = a1;
  if ( *((_QWORD *)a2 + 3) >= 8u )
    a2 = *(WCHAR **)a2;
  v46 = (BYTE *)a2;
  v47 = v12;
  v48 = pcbHash;
  v36 = 2;
  v37 = &v44;
  v15 = VerifyTrust(&pWVTData);
  if ( v15 + 2146762487 > 1 && v15 )
  {
    if ( *(_DWORD *)g_hProvTraceProvider > 4u )
    {
      v52 = (__int64)v45;
      v31 = v46;
      v51 = v15;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        g_hProvTraceProvider,
        (__int64)byte_180041AB9,
        v15,
        g_hProvTraceProvider,
        (__int64)&v51,
        &v31,
        &v52);
    }
    operator delete[](v12);
    v38 = 2;
    VerifyTrust(&pWVTData);
    return 0;
  }
  else
  {
    if ( !hStateData )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
        (const char *)0x8000FFFFLL,
        (int)dwCreationDisposition);
    v17 = WTHelperProvDataFromStateData(hStateData);
    if ( !v17 )
    {
      v26 = g_hProvTraceProvider;
      if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
      {
        v51 = GetLastError();
        dwCreationDisposition = &v51;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v26,
          (__int64)byte_180041A89,
          0);
      }
      v27 = wil::verify_hresult<long>(0x8000FFFF);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x78,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
        (const char *)v27,
        (int)dwCreationDisposition);
    }
    ProvSignerFromChain = WTHelperGetProvSignerFromChain(v17, 0, 0, 0);
    v19 = ProvSignerFromChain;
    if ( !ProvSignerFromChain )
    {
      v28 = g_hProvTraceProvider;
      if ( *(_DWORD *)g_hProvTraceProvider > 2u && (unsigned __int8)tlgKeywordOn(g_hProvTraceProvider, 0) )
      {
        v51 = GetLastError();
        dwCreationDisposition = &v51;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          v28,
          (__int64)byte_180041A5B,
          0);
      }
      v29 = wil::verify_hresult<long>(0x8000FFFF);
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x80,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
        (const char *)v29,
        (int)dwCreationDisposition);
    }
    pChainContext = ProvSignerFromChain->pChainContext;
    if ( !pChainContext || !pChainContext->cChain || (v21 = 1, !(*pChainContext->rgpChain)->cElement) )
      v21 = 0;
    if ( !v21 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
        (const char *)0x8000FFFFLL,
        (int)dwCreationDisposition);
    v22 = CertDuplicateCertificateContext((*(*pChainContext->rgpChain)->rgpElement)->pCertContext);
    *a3 = v22;
    if ( !v22 )
      wil::details::in1diag3::_Throw_NullAlloc(
        retaddr,
        (void *)0x8B,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
        v23);
    v24 = CertDuplicateStore(v19->pasCertChain->pCert->hCertStore);
    *a4 = v24;
    if ( !v24 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x8D,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecatalog.cpp",
        v25);
    operator delete[](v12);
    v38 = 2;
    VerifyTrust(&pWVTData);
    return 1;
  }
}

```

## disassembly

```asm
0x18002d450  mov     [rsp-8+arg_0], rbx
0x18002d455  push    rbp
0x18002d456  push    rsi
0x18002d457  push    rdi
0x18002d458  push    r12
0x18002d45a  push    r13
0x18002d45c  push    r14
0x18002d45e  push    r15
0x18002d460  lea     rbp, [rsp-10h]
0x18002d465  sub     rsp, 110h
0x18002d46c  mov     r12, r9
0x18002d46f  mov     r13, r8
0x18002d472  mov     r14, rdx
0x18002d475  mov     r15, rcx
0x18002d478  xor     esi, esi
0x18002d47a  mov     [r8], rsi
0x18002d47d  mov     [r9], rsi
0x18002d480  lea     ebx, [rsi+58h]
0x18002d483  mov     r8d, ebx; Size
0x18002d486  xor     edx, edx; Val
0x18002d488  lea     rcx, [rsp+140h+pWVTData]; void *
0x18002d48d  call    memset_0
0x18002d492  mov     [rsp+140h+pWVTData], ebx
0x18002d496  mov     [rsp+140h+var_E8], rsi
0x18002d49b  mov     [rsp+140h+var_E0], rsi
0x18002d4a0  mov     [rsp+140h+var_D8], 2
0x18002d4a9  mov     [rbp+40h+var_A8], 1010h
0x18002d4b1  mov     [rbp+40h+var_C0], 1
0x18002d4b8  mov     [rbp+40h+hStateData], rsi
0x18002d4bc  mov     [rbp+40h+var_B0], rsi
0x18002d4c0  lea     rax, [rsp+140h+pWVTData]
0x18002d4c5  mov     [rbp+40h+var_90], rax
0x18002d4c9  mov     [rbp+40h+var_88], 1
0x18002d4cd  cmp     qword ptr [r14+18h], 8
0x18002d4d2  jb      short loc_18002D4D9
0x18002d4d4  mov     rcx, [r14]
0x18002d4d7  jmp     short loc_18002D4DC
0x18002d4d9  mov     rcx, r14; lpFileName
0x18002d4dc  mov     [rsp+140h+hTemplateFile], rsi; hTemplateFile
0x18002d4e1  mov     [rsp+140h+dwFlagsAndAttributes], esi; dwFlagsAndAttributes
0x18002d4e5  mov     [rsp+140h+dwCreationDisposition], 3; int
0x18002d4ed  xor     r9d, r9d; lpSecurityAttributes
0x18002d4f0  mov     edx, 80000000h; dwDesiredAccess
0x18002d4f5  lea     r8d, [r9+5]; dwShareMode
0x18002d4f9  call    cs:__imp_CreateFileW
0x18002d4ff  mov     rbx, rax
0x18002d502  mov     [rbp+40h+arg_18], rax
0x18002d506  mov     rcx, [rbp+48h]; this
0x18002d50a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002d50e  jz      loc_18002D753
0x18002d514  mov     [rbp+40h+pcbHash], esi
0x18002d517  xor     r9d, r9d; dwFlags
0x18002d51a  xor     r8d, r8d; pbHash
0x18002d51d  lea     rdx, [rbp+40h+pcbHash]; pcbHash
0x18002d521  mov     rcx, rax; hFile
0x18002d524  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18002d52a  mov     ecx, [rbp+40h+pcbHash]; unsigned __int64
0x18002d52d  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18002d532  mov     rdi, rax
0x18002d535  mov     [rsp+140h+var_100], rax
0x18002d53a  xor     r9d, r9d; dwFlags
0x18002d53d  mov     r8, rax; pbHash
0x18002d540  lea     rdx, [rbp+40h+pcbHash]; pcbHash
0x18002d544  mov     rcx, rbx; hFile
0x18002d547  call    cs:__imp_CryptCATAdminCalcHashFromFileHandle
0x18002d54d  mov     rcx, [rbp+48h]; this
0x18002d551  test    eax, eax
0x18002d553  jz      loc_18002D765
0x18002d559  test    rbx, rbx
0x18002d55c  jz      short loc_18002D579
0x18002d55e  call    cs:__imp_GetLastError
0x18002d564  mov     esi, eax
0x18002d566  mov     rcx, rbx; hObject
0x18002d569  call    cs:__imp_CloseHandle
0x18002d56f  mov     ecx, esi; dwErrCode
0x18002d571  call    cs:__imp_SetLastError
0x18002d577  xor     esi, esi
0x18002d579  mov     [rbp+40h+arg_18], 0FFFFFFFFFFFFFFFFh
0x18002d581  mov     ebx, 48h ; 'H'
0x18002d586  mov     r8d, ebx; Size
0x18002d589  xor     edx, edx; Val
0x18002d58b  lea     rcx, [rbp+40h+var_80]; void *
0x18002d58f  call    memset_0
0x18002d594  mov     [rbp+40h+var_80], ebx
0x18002d597  cmp     qword ptr [r15+18h], 8
0x18002d59c  jb      short loc_18002D5A1
0x18002d59e  mov     r15, [r15]
0x18002d5a1  mov     [rbp+40h+var_78], r15
0x18002d5a5  cmp     qword ptr [r14+18h], 8
0x18002d5aa  jb      short loc_18002D5AF
0x18002d5ac  mov     r14, [r14]
0x18002d5af  mov     [rbp+40h+var_68], r14
0x18002d5b3  mov     [rbp+40h+var_58], rdi
0x18002d5b7  mov     eax, [rbp+40h+pcbHash]
0x18002d5ba  mov     [rbp+40h+var_50], eax
0x18002d5bd  mov     r14d, 2
0x18002d5c3  mov     [rsp+140h+var_D0], r14d
0x18002d5c8  lea     rax, [rbp+40h+var_80]
0x18002d5cc  mov     [rsp+140h+var_C8], rax
0x18002d5d1  lea     rcx, [rsp+140h+pWVTData]; pWVTData
0x18002d5d6  call    VerifyTrust
0x18002d5db  mov     r8d, eax
0x18002d5de  lea     ecx, [rax+7FF4FEF7h]
0x18002d5e4  cmp     ecx, 1
0x18002d5e7  jbe     short loc_18002D65C
0x18002d5e9  test    eax, eax
0x18002d5eb  jz      short loc_18002D65C
0x18002d5ed  mov     r9, cs:g_hProvTraceProvider
0x18002d5f4  mov     ecx, [r9]
0x18002d5f7  cmp     ecx, 4
0x18002d5fa  jbe     short loc_18002D63D
0x18002d5fc  mov     rdx, [rbp+40h+var_78]
0x18002d600  mov     [rbp+40h+arg_18], rdx
0x18002d604  mov     rax, [rbp+40h+var_68]
0x18002d608  mov     [rsp+140h+var_100], rax
0x18002d60d  mov     [rbp+40h+arg_10], r8d
0x18002d611  lea     rax, [rbp+40h+arg_18]
0x18002d615  mov     [rsp+140h+hTemplateFile], rax
0x18002d61a  lea     rax, [rsp+140h+var_100]
0x18002d61f  mov     qword ptr [rsp+140h+dwFlagsAndAttributes], rax
0x18002d624  lea     rax, [rbp+40h+arg_10]
0x18002d628  mov     qword ptr [rsp+140h+dwCreationDisposition], rax
0x18002d62d  lea     rdx, byte_180041AB9
0x18002d634  mov     rcx, r9
0x18002d637  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002d63c  nop
0x18002d63d  mov     rcx, rdi
0x18002d640  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002d646  nop
0x18002d647  mov     [rbp+40h+var_C0], r14d
0x18002d64b  lea     rcx, [rsp+140h+pWVTData]; pWVTData
0x18002d650  call    VerifyTrust
0x18002d655  xor     al, al
0x18002d657  jmp     loc_18002D726
0x18002d65c  mov     rax, [rbp+48h]
0x18002d660  mov     rcx, [rbp+40h+hStateData]; hStateData
0x18002d664  test    rcx, rcx
0x18002d667  jz      loc_18002D777
0x18002d66d  call    cs:__imp_WTHelperProvDataFromStateData
0x18002d673  test    rax, rax
0x18002d676  jz      loc_18002D792
0x18002d67c  xor     r9d, r9d; idxCounterSigner
0x18002d67f  xor     r8d, r8d; fCounterSigner
0x18002d682  xor     edx, edx; idxSigner
0x18002d684  mov     rcx, rax; pProvData
0x18002d687  call    cs:__imp_WTHelperGetProvSignerFromChain
0x18002d68d  mov     rbx, rax
0x18002d690  test    rax, rax
0x18002d693  jz      loc_18002D7F5
0x18002d699  mov     rdx, [rax+38h]
0x18002d69d  test    rdx, rdx
0x18002d6a0  jz      short loc_18002D6B5
0x18002d6a2  cmp     [rdx+0Ch], esi
0x18002d6a5  jbe     short loc_18002D6B5
0x18002d6a7  mov     rax, [rdx+10h]
0x18002d6ab  mov     rcx, [rax]
0x18002d6ae  cmp     [rcx+0Ch], esi
0x18002d6b1  mov     al, 1
0x18002d6b3  ja      short loc_18002D6B8
0x18002d6b5  mov     al, sil
0x18002d6b8  mov     rcx, [rbp+48h]; this
0x18002d6bc  test    al, al
0x18002d6be  jz      loc_18002D858
0x18002d6c4  mov     rax, [rdx+10h]
0x18002d6c8  mov     rcx, [rax]
0x18002d6cb  mov     rax, [rcx+10h]
0x18002d6cf  mov     rcx, [rax]
0x18002d6d2  mov     rcx, [rcx+8]; pCertContext
0x18002d6d6  call    cs:__imp_CertDuplicateCertificateContext
0x18002d6dc  mov     [r13+0], rax
0x18002d6e0  mov     rcx, [rbp+48h]; this
0x18002d6e4  test    rax, rax
0x18002d6e7  jz      loc_18002D870
0x18002d6ed  mov     rax, [rbx+10h]
0x18002d6f1  mov     rcx, [rax+8]
0x18002d6f5  mov     rcx, [rcx+20h]; hCertStore
0x18002d6f9  call    cs:__imp_CertDuplicateStore
0x18002d6ff  mov     [r12], rax
0x18002d703  mov     rcx, [rbp+48h]; this
0x18002d707  test    rax, rax
0x18002d70a  jz      short loc_18002D741
0x18002d70c  mov     rcx, rdi
0x18002d70f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x18002d715  nop
0x18002d716  mov     [rbp+40h+var_C0], r14d
0x18002d71a  lea     rcx, [rsp+140h+pWVTData]; pWVTData
0x18002d71f  call    VerifyTrust
0x18002d724  mov     al, 1
0x18002d726  mov     rbx, [rsp+140h+arg_0]
0x18002d72e  add     rsp, 110h
0x18002d735  pop     r15
0x18002d737  pop     r14
0x18002d739  pop     r13
0x18002d73b  pop     r12
0x18002d73d  pop     rdi
0x18002d73e  pop     rsi
0x18002d73f  pop     rbp
0x18002d740  retn
0x18002d741  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002d748  mov     edx, 8Dh; void *
0x18002d74d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002d753  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002d75a  mov     edx, 4Eh ; 'N'; void *
0x18002d75f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002d765  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002d76c  mov     edx, 52h ; 'R'; void *
0x18002d771  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18002d777  mov     r9d, 8000FFFFh; char *
0x18002d77d  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002d784  mov     edx, 72h ; 'r'; void *
0x18002d789  mov     rcx, rax; this
0x18002d78c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d792  mov     rbx, cs:g_hProvTraceProvider
0x18002d799  mov     eax, [rbx]
0x18002d79b  cmp     eax, r14d
0x18002d79e  jbe     short loc_18002D7D2
0x18002d7a0  xor     edx, edx
0x18002d7a2  mov     rcx, rbx
0x18002d7a5  call    _tlgKeywordOn
0x18002d7aa  test    al, al
0x18002d7ac  jz      short loc_18002D7D2
0x18002d7ae  call    cs:__imp_GetLastError
0x18002d7b4  mov     [rbp+40h+arg_10], eax
0x18002d7b7  lea     rax, [rbp+40h+arg_10]
0x18002d7bb  mov     qword ptr [rsp+140h+dwCreationDisposition], rax; int
0x18002d7c0  xor     r8d, r8d
0x18002d7c3  lea     rdx, byte_180041A89
0x18002d7ca  mov     rcx, rbx
0x18002d7cd  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002d7d2  mov     ecx, 8000FFFFh
0x18002d7d7  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d7dc  mov     r9d, eax; char *
0x18002d7df  mov     rcx, [rbp+48h]; this
0x18002d7e3  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002d7ea  mov     edx, 78h ; 'x'; void *
0x18002d7ef  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d7f5  mov     rbx, cs:g_hProvTraceProvider
0x18002d7fc  mov     eax, [rbx]
0x18002d7fe  cmp     eax, r14d
0x18002d801  jbe     short loc_18002D835
0x18002d803  xor     edx, edx
0x18002d805  mov     rcx, rbx
0x18002d808  call    _tlgKeywordOn
0x18002d80d  test    al, al
0x18002d80f  jz      short loc_18002D835
0x18002d811  call    cs:__imp_GetLastError
0x18002d817  mov     [rbp+40h+arg_10], eax
0x18002d81a  lea     rax, [rbp+40h+arg_10]
0x18002d81e  mov     qword ptr [rsp+140h+dwCreationDisposition], rax; int
0x18002d823  xor     r8d, r8d
0x18002d826  lea     rdx, byte_180041A5B
0x18002d82d  mov     rcx, rbx
0x18002d830  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002d835  mov     ecx, 8000FFFFh
0x18002d83a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18002d83f  mov     r9d, eax; char *
0x18002d842  mov     rcx, [rbp+48h]; this
0x18002d846  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002d84d  mov     edx, 80h; void *
0x18002d852  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d858  mov     r9d, 8000FFFFh; char *
0x18002d85e  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002d865  mov     edx, 85h; void *
0x18002d86a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18002d870  lea     r8, aOnecoreuapAdmi_12; "onecoreuap\\admin\\prov\\lib\\packageca"...
0x18002d877  mov     edx, 8Bh; void *
0x18002d87c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
