# LPA::Lpd::DownloadInstance::ValidateServerCertificateExtensions(_CERT_INFO * const)

- ea: `0x1800b926c`
- end: `0x1800b95e0`
- name: `?ValidateServerCertificateExtensions@DownloadInstance@Lpd@LPA@@CAJQEAU_CERT_INFO@@@Z`
- size: `884`
- prototype: `__int64 __fastcall(struct _CERT_INFO *const)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task`

## callers

- `0x1800b8840`

## callees

- `0x1800010f0`
- `0x18000df90`
- `0x1800adc0c`
- `0x1800b926c`
- `0x1800f1cc4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b9398`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b941b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b94ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b9398`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b941b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b94ed`
- `CRYPT32!CertFindExtension` at `0x1800b92e0`
- `CRYPT32!CertFindExtension` at `0x1800b93ca`
- `CRYPT32!CertFindExtension` at `0x1800b944d`
- `CRYPT32!CertFindExtension` at `0x1800b92e0`
- `CRYPT32!CertFindExtension` at `0x1800b93ca`
- `CRYPT32!CertFindExtension` at `0x1800b944d`

## string_xrefs

- `0x1800b9524`: `LpaServiceLpd`
- `0x1800b9593`: `LpaServiceLpd`
- `0x1800b950e`: `LPA::Lpd::DownloadInstance::ValidateServerCertificateExtensions`
- `0x1800b9588`: `LPA::Lpd::DownloadInstance::ValidateServerCertificateExtensions`

## pseudocode

```c
__int64 __fastcall LPA::Lpd::DownloadInstance::ValidateServerCertificateExtensions(struct _CERT_INFO *const a1)
{
  CERT_EXTENSION *rgExtension; // r8
  DWORD cExtension; // edx
  PCERT_EXTENSION Extension; // rax
  int v5; // ecx
  int v6; // r8d
  int v7; // r9d
  int v8; // ebx
  HLOCAL v9; // r14
  unsigned int v10; // esi
  __int64 v11; // r13
  unsigned int v12; // edi
  const char *v13; // r12
  CERT_EXTENSION *v14; // r8
  DWORD v15; // edx
  PCERT_EXTENSION v16; // rax
  CERT_EXTENSION *v17; // r8
  DWORD v18; // edx
  PCERT_EXTENSION v19; // rax
  _DWORD *v20; // rsi
  __int64 v21; // r15
  unsigned int v22; // edi
  const char *v23; // r14
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  char *v27; // rdx
  unsigned int v29; // [rsp+40h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-41h] BYREF
  const char *v31; // [rsp+50h] [rbp-39h] BYREF
  const char *v32; // [rsp+58h] [rbp-31h] BYREF
  const char *v33; // [rsp+60h] [rbp-29h] BYREF
  char Str2[24]; // [rsp+68h] [rbp-21h] BYREF
  char v35[24]; // [rsp+80h] [rbp-9h] BYREF

  rgExtension = a1->rgExtension;
  cExtension = a1->cExtension;
  strcpy(Str2, "2.23.146.1.2.1.3");
  strcpy(v35, "2.23.146.1.2.1.6");
  hMem = 0;
  v29 = 0;
  Extension = CertFindExtension("2.5.29.37", cExtension, rgExtension);
  if ( !Extension )
  {
    v8 = -2147023728;
    goto LABEL_32;
  }
  v8 = LPA::Lpd::DownloadInstance::DecodeX509ExtensionValue(
         (LPCSTR)0x24,
         Extension->Value.pbData,
         Extension->Value.cbData,
         0x8001u,
         &hMem,
         &v29);
  if ( v8 < 0 )
  {
LABEL_32:
    if ( (unsigned int)CallbackContext <= 2 )
      return (unsigned int)v8;
    v33 = "2.5.29.37";
    v27 = byte_180132279;
    goto LABEL_34;
  }
  v9 = hMem;
  v10 = *(_DWORD *)hMem;
  if ( (unsigned int)(*(_DWORD *)hMem - 1) <= 1 )
  {
    if ( !v10 )
      goto LABEL_10;
    v11 = *((_QWORD *)hMem + 1);
    v12 = 0;
    while ( 1 )
    {
      v13 = *(const char **)(v11 + 8LL * v12);
      if ( strncmp_0(v13, "1.3.6.1.5.5.7.3.1", 0x12u) )
      {
        if ( strncmp_0(v13, "1.3.6.1.5.5.7.3.2", 0x12u) )
          break;
      }
      if ( ++v12 >= v10 )
        goto LABEL_10;
    }
  }
  v8 = -2147418113;
LABEL_10:
  LocalFree(v9);
  hMem = 0;
  if ( v8 < 0 )
    goto LABEL_32;
  v14 = a1->rgExtension;
  v15 = a1->cExtension;
  hMem = 0;
  v29 = 0;
  v16 = CertFindExtension("2.5.29.15", v15, v14);
  if ( !v16 )
  {
    v8 = -2147023728;
LABEL_29:
    if ( (unsigned int)CallbackContext <= 2 )
      return (unsigned int)v8;
    v33 = "2.5.29.15";
    v27 = byte_180132225;
LABEL_34:
    v32 = "LPA::Lpd::DownloadInstance::ValidateServerCertificateExtensions";
    v31 = "LpaServiceLpd";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v5,
      (_DWORD)v27,
      v6,
      v7,
      (__int64)&v31,
      (__int64)&v32,
      (__int64)&v33);
    return (unsigned int)v8;
  }
  v8 = LPA::Lpd::DownloadInstance::DecodeX509ExtensionValue(
         (LPCSTR)0xE,
         v16->Value.pbData,
         v16->Value.cbData,
         0x8001u,
         &hMem,
         &v29);
  if ( v8 < 0 )
    goto LABEL_29;
  if ( **((char **)hMem + 1) >= 0 )
    v8 = -2147418113;
  LocalFree(hMem);
  hMem = 0;
  if ( v8 < 0 )
    goto LABEL_29;
  v17 = a1->rgExtension;
  v18 = a1->cExtension;
  hMem = 0;
  v29 = 0;
  v19 = CertFindExtension("2.5.29.32", v18, v17);
  if ( v19
    && (int)LPA::Lpd::DownloadInstance::DecodeX509ExtensionValue(
              (LPCSTR)0x10,
              v19->Value.pbData,
              v19->Value.cbData,
              0x8001u,
              &hMem,
              &v29) >= 0 )
  {
    v20 = hMem;
    if ( *(_DWORD *)hMem )
    {
      v8 = -2147418113;
      v21 = *((_QWORD *)hMem + 1);
      v22 = 0;
      while ( 1 )
      {
        v23 = *(const char **)(v21 + 24LL * v22);
        if ( !strncmp_0(v23, Str2, 0x11u) || !strncmp_0(v23, v35, 0x11u) )
          break;
        if ( ++v22 >= *v20 )
          goto LABEL_25;
      }
      v8 = 0;
    }
LABEL_25:
    LocalFree(v20);
    hMem = 0;
    if ( v8 < 0 && (unsigned int)CallbackContext > 2 )
    {
      v31 = "2.5.29.32";
      v32 = "LPA::Lpd::DownloadInstance::ValidateServerCertificateExtensions";
      v33 = "LpaServiceLpd";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v24,
        (unsigned int)byte_1801321CD,
        v25,
        v26,
        (__int64)&v33,
        (__int64)&v32,
        (__int64)&v31);
    }
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800b926c  push    rbp
0x1800b926e  push    rbx
0x1800b926f  push    rsi
0x1800b9270  push    rdi
0x1800b9271  push    r12
0x1800b9273  push    r13
0x1800b9275  push    r14
0x1800b9277  push    r15
0x1800b9279  lea     rbp, [rsp-1Fh]
0x1800b927e  sub     rsp, 0A8h
0x1800b9285  mov     rax, cs:__security_cookie
0x1800b928c  xor     rax, rsp
0x1800b928f  mov     [rbp+57h+var_48], rax
0x1800b9293  movups  xmm0, xmmword ptr cs:a2231461213; "2.23.146.1.2.1.3"
0x1800b929a  mov     al, byte ptr cs:a2231461213+10h; ""
0x1800b92a0  lea     rdi, a252937; "2.5.29.37"
0x1800b92a7  mov     r8, [rcx+0C8h]; rgExtensions
0x1800b92ae  mov     r15, rcx
0x1800b92b1  mov     edx, [rcx+0C0h]; cExtensions
0x1800b92b7  xor     r12d, r12d
0x1800b92ba  movups  xmmword ptr [rbp+57h+Str2], xmm0
0x1800b92be  mov     [rbp+57h+var_68], al
0x1800b92c1  mov     rcx, rdi; pszObjId
0x1800b92c4  movups  xmm0, xmmword ptr cs:a2231461216; "2.23.146.1.2.1.6"
0x1800b92cb  mov     al, byte ptr cs:a2231461216+10h; ""
0x1800b92d1  mov     [rbp+57h+var_60+10h], al
0x1800b92d4  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x1800b92d8  mov     [rbp+57h+hMem], r12
0x1800b92dc  mov     [rbp+57h+var_A0], r12d
0x1800b92e0  call    cs:__imp_CertFindExtension
0x1800b92e6  test    rax, rax
0x1800b92e9  jz      loc_1800B9564
0x1800b92ef  mov     r8d, [rax+10h]; cbEncoded
0x1800b92f3  lea     rcx, [rbp+57h+var_A0]
0x1800b92f7  mov     rdx, [rax+18h]; pbEncoded
0x1800b92fb  mov     r9d, 8001h; unsigned int
0x1800b9301  mov     [rsp+0E0h+var_B8], rcx; unsigned int *
0x1800b9306  lea     rcx, [rbp+57h+hMem]
0x1800b930a  mov     [rsp+0E0h+var_C0], rcx; void **
0x1800b930f  lea     ecx, [r12+24h]; lpszStructType
0x1800b9314  call    ?DecodeX509ExtensionValue@DownloadInstance@Lpd@LPA@@CAJPEBDPEBEKKPEAPEAXAEAK@Z; LPA::Lpd::DownloadInstance::DecodeX509ExtensionValue(char const *,uchar const *,ulong,ulong,void * *,ulong &)
0x1800b9319  mov     ebx, eax
0x1800b931b  test    eax, eax
0x1800b931d  js      loc_1800B9572
0x1800b9323  mov     r14, [rbp+57h+hMem]
0x1800b9327  mov     edi, 8000FFFFh
0x1800b932c  mov     esi, [r14]
0x1800b932f  lea     eax, [rsi-1]
0x1800b9332  cmp     eax, 1
0x1800b9335  ja      short loc_1800B9383
0x1800b9337  test    esi, esi
0x1800b9339  jz      short loc_1800B9395
0x1800b933b  mov     r13, [r14+8]
0x1800b933f  mov     edi, r12d
0x1800b9342  mov     eax, edi
0x1800b9344  lea     rdx, a136155731; "1.3.6.1.5.5.7.3.1"
0x1800b934b  mov     r8d, 12h; MaxCount
0x1800b9351  mov     r12, [r13+rax*8+0]
0x1800b9356  mov     rcx, r12; Str1
0x1800b9359  call    strncmp_0
0x1800b935e  test    eax, eax
0x1800b9360  jz      short loc_1800B9387
0x1800b9362  mov     r8d, 12h; MaxCount
0x1800b9368  lea     rdx, a136155732; "1.3.6.1.5.5.7.3.2"
0x1800b936f  mov     rcx, r12; Str1
0x1800b9372  call    strncmp_0
0x1800b9377  xor     r12d, r12d
0x1800b937a  test    eax, eax
0x1800b937c  jz      short loc_1800B938A
0x1800b937e  mov     edi, 8000FFFFh
0x1800b9383  mov     ebx, edi
0x1800b9385  jmp     short loc_1800B9395
0x1800b9387  xor     r12d, r12d
0x1800b938a  inc     edi
0x1800b938c  cmp     edi, esi
0x1800b938e  jb      short loc_1800B9342
0x1800b9390  mov     edi, 8000FFFFh
0x1800b9395  mov     rcx, r14; hMem
0x1800b9398  call    cs:__imp_LocalFree
0x1800b939e  mov     [rbp+57h+hMem], r12
0x1800b93a2  test    ebx, ebx
0x1800b93a4  js      loc_1800B956B
0x1800b93aa  mov     r8, [r15+0C8h]; rgExtensions
0x1800b93b1  lea     rsi, a252915; "2.5.29.15"
0x1800b93b8  mov     edx, [r15+0C0h]; cExtensions
0x1800b93bf  mov     rcx, rsi; pszObjId
0x1800b93c2  mov     [rbp+57h+hMem], r12
0x1800b93c6  mov     [rbp+57h+var_A0], r12d
0x1800b93ca  call    cs:__imp_CertFindExtension
0x1800b93d0  test    rax, rax
0x1800b93d3  jz      loc_1800B9547
0x1800b93d9  mov     r8d, [rax+10h]; cbEncoded
0x1800b93dd  lea     rcx, [rbp+57h+var_A0]
0x1800b93e1  mov     rdx, [rax+18h]; pbEncoded
0x1800b93e5  mov     r9d, 8001h; unsigned int
0x1800b93eb  mov     [rsp+0E0h+var_B8], rcx; unsigned int *
0x1800b93f0  lea     rcx, [rbp+57h+hMem]
0x1800b93f4  mov     [rsp+0E0h+var_C0], rcx; void **
0x1800b93f9  mov     ecx, 0Eh; lpszStructType
0x1800b93fe  call    ?DecodeX509ExtensionValue@DownloadInstance@Lpd@LPA@@CAJPEBDPEBEKKPEAPEAXAEAK@Z; LPA::Lpd::DownloadInstance::DecodeX509ExtensionValue(char const *,uchar const *,ulong,ulong,void * *,ulong &)
0x1800b9403  mov     ebx, eax
0x1800b9405  test    eax, eax
0x1800b9407  js      loc_1800B954C
0x1800b940d  mov     rcx, [rbp+57h+hMem]; hMem
0x1800b9411  mov     rax, [rcx+8]
0x1800b9415  cmp     [rax], r12b
0x1800b9418  cmovge  ebx, edi
0x1800b941b  call    cs:__imp_LocalFree
0x1800b9421  mov     [rbp+57h+hMem], r12
0x1800b9425  test    ebx, ebx
0x1800b9427  js      loc_1800B954C
0x1800b942d  mov     r8, [r15+0C8h]; rgExtensions
0x1800b9434  lea     r14, a252932; "2.5.29.32"
0x1800b943b  mov     edx, [r15+0C0h]; cExtensions
0x1800b9442  mov     rcx, r14; pszObjId
0x1800b9445  mov     [rbp+57h+hMem], r12
0x1800b9449  mov     [rbp+57h+var_A0], r12d
0x1800b944d  call    cs:__imp_CertFindExtension
0x1800b9453  test    rax, rax
0x1800b9456  jz      loc_1800B95BE
0x1800b945c  mov     r8d, [rax+10h]; cbEncoded
0x1800b9460  lea     rcx, [rbp+57h+var_A0]
0x1800b9464  mov     rdx, [rax+18h]; pbEncoded
0x1800b9468  mov     r9d, 8001h; unsigned int
0x1800b946e  mov     [rsp+0E0h+var_B8], rcx; unsigned int *
0x1800b9473  lea     rcx, [rbp+57h+hMem]
0x1800b9477  mov     [rsp+0E0h+var_C0], rcx; void **
0x1800b947c  mov     ecx, 10h; lpszStructType
0x1800b9481  call    ?DecodeX509ExtensionValue@DownloadInstance@Lpd@LPA@@CAJPEBDPEBEKKPEAPEAXAEAK@Z; LPA::Lpd::DownloadInstance::DecodeX509ExtensionValue(char const *,uchar const *,ulong,ulong,void * *,ulong &)
0x1800b9486  test    eax, eax
0x1800b9488  js      loc_1800B95BE
0x1800b948e  mov     rsi, [rbp+57h+hMem]
0x1800b9492  cmp     [rsi], r12d
0x1800b9495  jz      short loc_1800B94EA
0x1800b9497  mov     ebx, edi
0x1800b9499  jbe     short loc_1800B94EA
0x1800b949b  mov     r15, [rsi+8]
0x1800b949f  mov     edi, r12d
0x1800b94a2  mov     r13d, 11h
0x1800b94a8  mov     eax, edi
0x1800b94aa  lea     rdx, [rbp+57h+Str2]; Str2
0x1800b94ae  mov     r8d, r13d; MaxCount
0x1800b94b1  lea     rcx, [rax+rax*2]
0x1800b94b5  mov     r14, [r15+rcx*8]
0x1800b94b9  mov     rcx, r14; Str1
0x1800b94bc  call    strncmp_0
0x1800b94c1  test    eax, eax
0x1800b94c3  jz      short loc_1800B94E0
0x1800b94c5  mov     r8d, r13d; MaxCount
0x1800b94c8  lea     rdx, [rbp+57h+var_60]; Str2
0x1800b94cc  mov     rcx, r14; Str1
0x1800b94cf  call    strncmp_0
0x1800b94d4  test    eax, eax
0x1800b94d6  jz      short loc_1800B94E0
0x1800b94d8  inc     edi
0x1800b94da  cmp     edi, [rsi]
0x1800b94dc  jb      short loc_1800B94A8
0x1800b94de  jmp     short loc_1800B94E3
0x1800b94e0  mov     ebx, r12d
0x1800b94e3  lea     r14, a252932; "2.5.29.32"
0x1800b94ea  mov     rcx, rsi; hMem
0x1800b94ed  call    cs:__imp_LocalFree
0x1800b94f3  mov     [rbp+57h+hMem], r12
0x1800b94f7  test    ebx, ebx
0x1800b94f9  jns     loc_1800B95BE
0x1800b94ff  mov     eax, cs:CallbackContext
0x1800b9505  cmp     eax, 2
0x1800b9508  jbe     loc_1800B95BE
0x1800b950e  lea     rax, aLpaLpdDownload_35; "LPA::Lpd::DownloadInstance::ValidateSer"...
0x1800b9515  mov     [rbp+57h+var_90], r14
0x1800b9519  mov     [rbp+57h+var_88], rax
0x1800b951d  lea     rdx, byte_1801321CD
0x1800b9524  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b952b  mov     [rbp+57h+var_80], rax
0x1800b952f  lea     rax, [rbp+57h+var_90]
0x1800b9533  mov     [rsp+0E0h+var_B0], rax
0x1800b9538  lea     rax, [rbp+57h+var_88]
0x1800b953c  mov     [rsp+0E0h+var_B8], rax
0x1800b9541  lea     rax, [rbp+57h+var_80]
0x1800b9545  jmp     short loc_1800B95B4
0x1800b9547  mov     ebx, 80070490h
0x1800b954c  mov     eax, cs:CallbackContext
0x1800b9552  cmp     eax, 2
0x1800b9555  jbe     short loc_1800B95BE
0x1800b9557  mov     [rbp+57h+var_80], rsi
0x1800b955b  lea     rdx, byte_180132225
0x1800b9562  jmp     short loc_1800B9588
0x1800b9564  mov     ebx, 80070490h
0x1800b9569  jmp     short loc_1800B9572
0x1800b956b  lea     rdi, a252937; "2.5.29.37"
0x1800b9572  mov     eax, cs:CallbackContext
0x1800b9578  cmp     eax, 2
0x1800b957b  jbe     short loc_1800B95BE
0x1800b957d  mov     [rbp+57h+var_80], rdi
0x1800b9581  lea     rdx, byte_180132279
0x1800b9588  lea     rax, aLpaLpdDownload_35; "LPA::Lpd::DownloadInstance::ValidateSer"...
0x1800b958f  mov     [rbp+57h+var_88], rax
0x1800b9593  lea     rax, aLpaservicelpd; "LpaServiceLpd"
0x1800b959a  mov     [rbp+57h+var_90], rax
0x1800b959e  lea     rax, [rbp+57h+var_80]
0x1800b95a2  mov     [rsp+0E0h+var_B0], rax
0x1800b95a7  lea     rax, [rbp+57h+var_88]
0x1800b95ab  mov     [rsp+0E0h+var_B8], rax
0x1800b95b0  lea     rax, [rbp+57h+var_90]
0x1800b95b4  mov     [rsp+0E0h+var_C0], rax
0x1800b95b9  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800b95be  mov     eax, ebx
0x1800b95c0  mov     rcx, [rbp+57h+var_48]
0x1800b95c4  xor     rcx, rsp; StackCookie
0x1800b95c7  call    __security_check_cookie
0x1800b95cc  add     rsp, 0A8h
0x1800b95d3  pop     r15
0x1800b95d5  pop     r14
0x1800b95d7  pop     r13
0x1800b95d9  pop     r12
0x1800b95db  pop     rdi
0x1800b95dc  pop     rsi
0x1800b95dd  pop     rbx
0x1800b95de  pop     rbp
0x1800b95df  retn
```
