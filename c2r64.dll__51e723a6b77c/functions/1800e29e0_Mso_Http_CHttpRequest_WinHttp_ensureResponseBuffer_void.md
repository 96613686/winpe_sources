# Mso::Http::CHttpRequest_WinHttp::ensureResponseBuffer(void)

- ea: `0x1800e29e0`
- end: `0x1800e2f06`
- name: `?ensureResponseBuffer@CHttpRequest_WinHttp@Http@Mso@@AEAA?AUResult@23@XZ`
- size: `1318`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `service_task`

## callers

- `0x1800e52a0`

## callees

- `0x18000adf0`
- `0x18000ffb0`
- `0x180010a84`
- `0x18001c6b4`
- `0x18001c760`
- `0x1800258b4`
- `0x18002acd8`
- `0x18003e690`
- `0x180063814`
- `0x18008cfc4`
- `0x1800d1094`
- `0x1800d113c`
- `0x1800da9a8`
- `0x1800de508`
- `0x1800dfbf4`
- `0x1800e29e0`
- `0x1801460c0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800e2b51`
- `KERNEL32!GetLastError` at `0x1800e2d47`
- `KERNEL32!GetLastError` at `0x1800e2d9e`
- `KERNEL32!GetLastError` at `0x1800e2b51`
- `KERNEL32!GetLastError` at `0x1800e2d47`
- `KERNEL32!GetLastError` at `0x1800e2d9e`
- `WINHTTP!WinHttpReadData` at `0x1800e2d02`
- `WINHTTP!WinHttpReadData` at `0x1800e2d02`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800e2b36`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800e2b36`

## string_xrefs

- `0x1800e2ddd`: `Failed to read data into buffer`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Mso::Http::CHttpRequest_WinHttp::ensureResponseBuffer(__int64 a1, __int64 a2)
{
  __int64 v4; // rdx
  __int64 v5; // r12
  __int64 v6; // rax
  unsigned int v7; // r15d
  __int64 i; // rax
  void *v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // rax
  int v12; // r14d
  const char *v13; // xmm1_8
  DWORD LastError; // ebx
  int v15; // edx
  int v16; // r9d
  __int64 v17; // rax
  __int64 v18; // rax
  char *v19; // r14
  char *v20; // rax
  size_t v21; // rbx
  __int64 v22; // rdx
  __int64 v23; // rax
  const char *v24; // xmm1_8
  DWORD v25; // ebx
  void *v26; // rax
  BOOL v27; // ebx
  int *v28; // rax
  DWORD v29; // eax
  DWORD v30; // eax
  int v31; // edx
  int v32; // r9d
  char *v33; // r13
  char *v34; // rax
  size_t v35; // rbx
  char v37[8]; // [rsp+30h] [rbp-D0h] BYREF
  const char *v38; // [rsp+38h] [rbp-C8h] BYREF
  int v39; // [rsp+40h] [rbp-C0h]
  DWORD dwNumberOfBytesAvailable; // [rsp+44h] [rbp-BCh] BYREF
  DWORD dwNumberOfBytesRead; // [rsp+48h] [rbp-B8h] BYREF
  void *v42[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v43; // [rsp+60h] [rbp-A0h]
  const char *v44; // [rsp+68h] [rbp-98h] BYREF
  int v45; // [rsp+70h] [rbp-90h] BYREF
  __int64 v46; // [rsp+78h] [rbp-88h]
  __int64 v47; // [rsp+80h] [rbp-80h]
  _BYTE v48[16]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v49; // [rsp+A0h] [rbp-60h]
  _QWORD v50[2]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v51[16]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v52[16]; // [rsp+D0h] [rbp-30h] BYREF
  char v53[24]; // [rsp+E0h] [rbp-20h] BYREF
  void **v54; // [rsp+F8h] [rbp-8h] BYREF
  const char *v55; // [rsp+100h] [rbp+0h]
  DWORD v56; // [rsp+108h] [rbp+8h]
  __int16 v57; // [rsp+10Ch] [rbp+Ch]
  __int128 v58; // [rsp+110h] [rbp+10h] BYREF
  __int64 v59; // [rsp+120h] [rbp+20h]
  __int64 v60; // [rsp+128h] [rbp+28h]

  if ( *(_BYTE *)(a1 + 164) )
  {
    *(_OWORD *)a2 = *(_OWORD *)(a1 + 208);
    *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 224);
    return a2;
  }
  if ( !*(_BYTE *)(a1 + 25) )
  {
    v38 = "Request not sent";
    Mso::Diagnostics::SendDiagnosticTrace<>(507348564, 831, 15, 2, (__int64)&v38);
    Mso::Http::Results::InvalidStateError(a2, v4, 42497689);
    return a2;
  }
  v5 = a1 + 136;
  v6 = *(_QWORD *)(a1 + 136);
  if ( v6 != *(_QWORD *)(a1 + 144) )
    *(_QWORD *)(a1 + 144) = v6;
  *(_DWORD *)(a1 + 160) = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  v7 = 0;
  for ( i = a1 + 232; ; i = a1 + 232 )
  {
    dwNumberOfBytesAvailable = 0;
    std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v51, i);
    v9 = *(void **)(a1 + 120);
    if ( v9 )
    {
      if ( WinHttpQueryDataAvailable(v9, &dwNumberOfBytesAvailable) )
      {
        v38 = 0;
        v39 = 0;
        v12 = 0;
        goto LABEL_14;
      }
      LastError = GetLastError();
      v55 = "SH_ErrorCode";
      v56 = LastError;
      v57 = 4;
      v58 = 0;
      v59 = 0;
      v60 = 7;
      LOWORD(v58) = 0;
      v54 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
      v38 = "Failed to query the response data";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
        507348562,
        v15,
        15,
        v16,
        (__int64)&v38,
        (__int64)&v54);
      std::wstring::~wstring(&v58);
      v17 = Mso::Http::ConvertDwToResult(v48, LastError, 42497692);
      v47 = *(_QWORD *)(v17 + 16);
      v12 = *(_DWORD *)v17;
      v13 = *(const char **)(v17 + 8);
      v39 = v47;
    }
    else
    {
      v38 = "Invalid requst handle";
      Mso::Diagnostics::SendDiagnosticTrace<>(507348563, 831, 15, 2, (__int64)&v38);
      v11 = Mso::Http::Results::InvalidStateError(v48, v10, 42497691);
      v47 = *(_QWORD *)(v11 + 16);
      v12 = *(_DWORD *)v11;
      v13 = *(const char **)(v11 + 8);
      v39 = v47;
    }
    v38 = v13;
LABEL_14:
    std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v51);
    if ( v12 )
      goto LABEL_40;
    if ( !dwNumberOfBytesAvailable )
      break;
    v18 = v7 + dwNumberOfBytesAvailable;
    v19 = (char *)v42[1];
    if ( (void *)(unsigned int)v18 >= (void *)((char *)v42[1] - (char *)v42[0]) )
    {
      if ( (void *)(unsigned int)v18 <= (void *)((char *)v42[1] - (char *)v42[0]) )
        goto LABEL_23;
      if ( (unsigned int)v18 > v43 - (unsigned __int64)v42[0] )
      {
        _mm_lfence();
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v42);
        goto LABEL_23;
      }
      v21 = (unsigned int)v18 - (unsigned __int64)((char *)v42[1] - (char *)v42[0]);
      memset(v42[1], 0, v21);
      v20 = &v19[v21];
    }
    else
    {
      v20 = (char *)v42[0] + v18;
    }
    v42[1] = v20;
LABEL_23:
    dwNumberOfBytesRead = 0;
    std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(v52, a1 + 232);
    if ( *(_QWORD *)(a1 + 120) )
    {
      v25 = dwNumberOfBytesAvailable;
      v26 = (void *)std::vector<unsigned char>::operator[](v42, v7);
      v27 = WinHttpReadData(*(HINTERNET *)(a1 + 120), v26, v25, &dwNumberOfBytesRead);
      std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(
        v50,
        a1 + 168);
      *(_DWORD *)(v50[0] + 20LL) += dwNumberOfBytesRead;
      std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(v50);
      if ( v27 )
      {
        v45 = 0;
        v46 = 0;
        LODWORD(v47) = 0;
        v28 = &v45;
      }
      else
      {
        v29 = GetLastError();
        v28 = (int *)Mso::Http::ConvertDwToResult(v53, v29, 42497694);
      }
      v49 = *((_QWORD *)v28 + 2);
      v12 = *v28;
      v24 = (const char *)*((_QWORD *)v28 + 1);
      v39 = v49;
    }
    else
    {
      v38 = "Invalid request handle";
      Mso::Diagnostics::SendDiagnosticTrace<>(507348561, 831, 15, 2, (__int64)&v38);
      v23 = Mso::Http::Results::InvalidStateError(v48, v22, 42497693);
      v47 = *(_QWORD *)(v23 + 16);
      v12 = *(_DWORD *)v23;
      v24 = *(const char **)(v23 + 8);
      v39 = v47;
    }
    v38 = v24;
    std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(v52);
    if ( v12 )
    {
      v30 = GetLastError();
      v55 = "SH_ErrorCode";
      v56 = v30;
      v57 = 4;
      v58 = 0;
      v59 = 0;
      v60 = 7;
      LOWORD(v58) = 0;
      v54 = &Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable';
      v44 = "Failed to read data into buffer";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(
        507348560,
        v31,
        15,
        v32,
        (__int64)&v44,
        (__int64)&v54);
      std::wstring::~wstring(&v58);
      goto LABEL_40;
    }
    v7 += dwNumberOfBytesRead;
  }
  v33 = (char *)v42[1];
  if ( (void *)v7 < (void *)((char *)v42[1] - (char *)v42[0]) )
  {
    v34 = (char *)v42[0] + v7;
    goto LABEL_38;
  }
  if ( (void *)v7 > (void *)((char *)v42[1] - (char *)v42[0]) )
  {
    if ( v7 <= v43 - (unsigned __int64)v42[0] )
    {
      v35 = v7 - (unsigned __int64)((char *)v42[1] - (char *)v42[0]);
      memset(v42[1], 0, v35);
      v34 = &v33[v35];
LABEL_38:
      v42[1] = v34;
    }
    else
    {
      _mm_lfence();
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(v42);
    }
  }
  std::vector<unsigned char>::operator=(v5, v42);
  *(_DWORD *)(a1 + 160) = v7;
  v37[0] = 10;
  Mso::Http::HttpRequestWinTimings::SetTiming(
    (Mso::Http::HttpRequestWinTimings *)(a1 + 320),
    (const enum Mso::Http::HttpRequestWinTimings::TimingEvent *)v37,
    1);
LABEL_40:
  *(_BYTE *)(a1 + 164) = 1;
  *(_DWORD *)(a1 + 208) = v12;
  *(_QWORD *)(a1 + 216) = v38;
  *(_DWORD *)(a1 + 224) = v39;
  *(_OWORD *)a2 = *(_OWORD *)(a1 + 208);
  *(_QWORD *)(a2 + 16) = *(_QWORD *)(a1 + 224);
  std::vector<unsigned char>::~vector<unsigned char>(v42);
  return a2;
}

```

## disassembly

```asm
0x1800e29e0  mov     [rsp-8+arg_10], rbx
0x1800e29e5  push    rbp
0x1800e29e6  push    rsi
0x1800e29e7  push    rdi
0x1800e29e8  push    r12
0x1800e29ea  push    r13
0x1800e29ec  push    r14
0x1800e29ee  push    r15
0x1800e29f0  lea     rbp, [rsp-40h]
0x1800e29f5  sub     rsp, 140h
0x1800e29fc  mov     rax, cs:__security_cookie
0x1800e2a03  xor     rax, rsp
0x1800e2a06  mov     [rbp+70h+var_40], rax
0x1800e2a0a  mov     rsi, rdx
0x1800e2a0d  mov     rdi, rcx
0x1800e2a10  xor     ebx, ebx
0x1800e2a12  cmp     [rcx+0A4h], bl
0x1800e2a18  jz      short loc_1800E2A36
0x1800e2a1a  movups  xmm0, xmmword ptr [rcx+0D0h]
0x1800e2a21  movups  xmmword ptr [rdx], xmm0
0x1800e2a24  movsd   xmm1, qword ptr [rcx+0E0h]
0x1800e2a2c  movsd   qword ptr [rdx+10h], xmm1
0x1800e2a31  jmp     loc_1800E2EDC
0x1800e2a36  cmp     [rcx+19h], bl
0x1800e2a39  jnz     short loc_1800E2A7D
0x1800e2a3b  lea     rax, aRequestNotSent; "Request not sent"
0x1800e2a42  mov     [rsp+170h+var_138], rax
0x1800e2a47  mov     r9d, 2
0x1800e2a4d  lea     rax, [rsp+170h+var_138]
0x1800e2a52  mov     [rsp+170h+var_150], rax
0x1800e2a57  mov     edx, 33Fh
0x1800e2a5c  mov     ecx, 1E3D8654h
0x1800e2a61  lea     r8d, [r9+0Dh]
0x1800e2a65  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x1800e2a6a  mov     r8d, 2887699h
0x1800e2a70  mov     rcx, rsi
0x1800e2a73  call    ?InvalidStateError@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::InvalidStateError(__int64,uint)
0x1800e2a78  jmp     loc_1800E2EDC
0x1800e2a7d  lea     r12, [rcx+88h]
0x1800e2a84  mov     rax, [r12]
0x1800e2a88  cmp     rax, [r12+8]
0x1800e2a8d  jz      short loc_1800E2A94
0x1800e2a8f  mov     [r12+8], rax
0x1800e2a94  mov     [rcx+0A0h], ebx
0x1800e2a9a  xorps   xmm0, xmm0
0x1800e2a9d  movdqu  xmmword ptr [rsp+170h+var_120], xmm0
0x1800e2aa3  mov     [rsp+170h+var_110], rbx
0x1800e2aa8  mov     r15d, ebx
0x1800e2aab  lea     rax, [rcx+0E8h]
0x1800e2ab2  mov     r13d, 0Fh
0x1800e2ab8  lea     r14, aShErrorcode; "SH_ErrorCode"
0x1800e2abf  mov     [rsp+170h+dwNumberOfBytesAvailable], ebx
0x1800e2ac3  mov     rdx, rax
0x1800e2ac6  lea     rcx, [rbp+70h+var_B0]
0x1800e2aca  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x1800e2acf  mov     rcx, [rdi+78h]; hRequest
0x1800e2ad3  test    rcx, rcx
0x1800e2ad6  jnz     short loc_1800E2B31
0x1800e2ad8  lea     rax, aInvalidRequstH; "Invalid requst handle"
0x1800e2adf  mov     [rsp+170h+var_138], rax
0x1800e2ae4  lea     r9d, [rcx+2]
0x1800e2ae8  lea     rax, [rsp+170h+var_138]
0x1800e2aed  mov     [rsp+170h+var_150], rax
0x1800e2af2  mov     r8d, r13d
0x1800e2af5  mov     edx, 33Fh
0x1800e2afa  mov     ecx, 1E3D8653h
0x1800e2aff  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x1800e2b04  mov     r8d, 288769Bh
0x1800e2b0a  lea     rcx, [rbp+70h+var_E0]
0x1800e2b0e  call    ?InvalidStateError@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::InvalidStateError(__int64,uint)
0x1800e2b13  movsd   xmm0, qword ptr [rax+10h]
0x1800e2b18  movsd   [rbp+70h+var_F0], xmm0
0x1800e2b1d  mov     r14d, [rax]
0x1800e2b20  movq    xmm1, qword ptr [rax+8]
0x1800e2b25  mov     ebx, dword ptr [rbp+70h+var_F0]
0x1800e2b28  mov     [rsp+170h+var_130], ebx
0x1800e2b2c  jmp     loc_1800E2BEE
0x1800e2b31  lea     rdx, [rsp+170h+dwNumberOfBytesAvailable]; lpdwNumberOfBytesAvailable
0x1800e2b36  call    cs:__imp_WinHttpQueryDataAvailable
0x1800e2b3c  test    eax, eax
0x1800e2b3e  jz      short loc_1800E2B51
0x1800e2b40  mov     [rsp+170h+var_138], rbx
0x1800e2b45  mov     [rsp+170h+var_130], ebx
0x1800e2b49  mov     r14d, ebx
0x1800e2b4c  jmp     loc_1800E2BF4
0x1800e2b51  call    cs:__imp_GetLastError
0x1800e2b57  mov     ebx, eax
0x1800e2b59  mov     [rbp+70h+var_70], r14
0x1800e2b5d  mov     [rbp+70h+var_68], eax
0x1800e2b60  mov     eax, 4
0x1800e2b65  mov     [rbp+70h+var_64], ax
0x1800e2b69  xorps   xmm0, xmm0
0x1800e2b6c  movups  [rbp+70h+var_60], xmm0
0x1800e2b70  xor     r14d, r14d
0x1800e2b73  mov     [rbp+70h+var_50], r14
0x1800e2b77  mov     [rbp+70h+var_48], 7
0x1800e2b7f  mov     word ptr [rbp+70h+var_60], r14w
0x1800e2b84  lea     rax, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x1800e2b8b  mov     [rbp+70h+var_78], rax
0x1800e2b8f  lea     rax, aFailedToQueryT; "Failed to query the response data"
0x1800e2b96  mov     [rsp+170h+var_138], rax
0x1800e2b9b  lea     rax, [rbp+70h+var_78]
0x1800e2b9f  mov     [rsp+170h+var_148], rax
0x1800e2ba4  lea     rax, [rsp+170h+var_138]
0x1800e2ba9  mov     [rsp+170h+var_150], rax
0x1800e2bae  mov     r8d, r13d
0x1800e2bb1  mov     ecx, 1E3D8652h
0x1800e2bb6  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800e2bbb  lea     rcx, [rbp+70h+var_60]; void *
0x1800e2bbf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e2bc4  mov     r8d, 288769Ch
0x1800e2bca  mov     edx, ebx
0x1800e2bcc  lea     rcx, [rbp+70h+var_E0]
0x1800e2bd0  call    ?ConvertDwToResult@Http@Mso@@YA?AUResult@12@KI@Z; Mso::Http::ConvertDwToResult(ulong,uint)
0x1800e2bd5  movsd   xmm0, qword ptr [rax+10h]
0x1800e2bda  movsd   [rbp+70h+var_F0], xmm0
0x1800e2bdf  mov     r14d, [rax]
0x1800e2be2  movq    xmm1, qword ptr [rax+8]
0x1800e2be7  mov     eax, dword ptr [rbp+70h+var_F0]
0x1800e2bea  mov     [rsp+170h+var_130], eax
0x1800e2bee  movq    [rsp+170h+var_138], xmm1
0x1800e2bf4  lea     rcx, [rbp+70h+var_B0]
0x1800e2bf8  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x1800e2bfd  test    r14d, r14d
0x1800e2c00  jnz     loc_1800E2E97
0x1800e2c06  mov     eax, [rsp+170h+dwNumberOfBytesAvailable]
0x1800e2c0a  mov     rdx, [rsp+170h+var_120]
0x1800e2c0f  test    eax, eax
0x1800e2c11  jz      loc_1800E2E17
0x1800e2c17  add     eax, r15d
0x1800e2c1a  mov     ebx, eax
0x1800e2c1c  mov     r14, [rsp+170h+var_120+8]
0x1800e2c21  mov     rcx, r14
0x1800e2c24  sub     rcx, rdx
0x1800e2c27  cmp     rbx, rcx
0x1800e2c2a  jnb     short loc_1800E2C31
0x1800e2c2c  add     rax, rdx
0x1800e2c2f  jmp     short loc_1800E2C66
0x1800e2c31  jbe     short loc_1800E2C6B
0x1800e2c33  mov     rax, [rsp+170h+var_110]
0x1800e2c38  sub     rax, rdx
0x1800e2c3b  cmp     rbx, rax
0x1800e2c3e  jbe     short loc_1800E2C52
0x1800e2c40  lfence
0x1800e2c43  mov     rdx, rbx
0x1800e2c46  lea     rcx, [rsp+170h+var_120]
0x1800e2c4b  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800e2c50  jmp     short loc_1800E2C6B
0x1800e2c52  sub     rbx, rcx
0x1800e2c55  mov     r8, rbx; Size
0x1800e2c58  xor     edx, edx; Val
0x1800e2c5a  mov     rcx, r14; void *
0x1800e2c5d  call    memset
0x1800e2c62  lea     rax, [r14+rbx]
0x1800e2c66  mov     [rsp+170h+var_120+8], rax
0x1800e2c6b  xor     r14d, r14d
0x1800e2c6e  mov     [rsp+170h+dwNumberOfBytesRead], r14d
0x1800e2c73  lea     rdx, [rdi+0E8h]
0x1800e2c7a  lea     rcx, [rbp+70h+var_A0]
0x1800e2c7e  call    ??0?$shared_lock@Vshared_mutex@std@@@std@@QEAA@AEAVshared_mutex@1@@Z; std::shared_lock<std::shared_mutex>::shared_lock<std::shared_mutex>(std::shared_mutex &)
0x1800e2c83  cmp     [rdi+78h], r14
0x1800e2c87  jnz     short loc_1800E2CE2
0x1800e2c89  lea     rax, aInvalidRequest; "Invalid request handle"
0x1800e2c90  mov     [rsp+170h+var_138], rax
0x1800e2c95  lea     r9d, [r14+2]
0x1800e2c99  lea     rax, [rsp+170h+var_138]
0x1800e2c9e  mov     [rsp+170h+var_150], rax
0x1800e2ca3  mov     r8d, r13d
0x1800e2ca6  mov     edx, 33Fh
0x1800e2cab  mov     ecx, 1E3D8651h
0x1800e2cb0  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x1800e2cb5  mov     r8d, 288769Dh
0x1800e2cbb  lea     rcx, [rbp+70h+var_E0]
0x1800e2cbf  call    ?InvalidStateError@Results@Http@Mso@@YA?AUResult@23@_JI@Z; Mso::Http::Results::InvalidStateError(__int64,uint)
0x1800e2cc4  movsd   xmm0, qword ptr [rax+10h]
0x1800e2cc9  movsd   [rbp+70h+var_F0], xmm0
0x1800e2cce  mov     r14d, [rax]
0x1800e2cd1  movq    xmm1, qword ptr [rax+8]
0x1800e2cd6  mov     ebx, dword ptr [rbp+70h+var_F0]
0x1800e2cd9  mov     [rsp+170h+var_130], ebx
0x1800e2cdd  jmp     loc_1800E2D77
0x1800e2ce2  mov     ebx, [rsp+170h+dwNumberOfBytesAvailable]
0x1800e2ce6  mov     edx, r15d
0x1800e2ce9  lea     rcx, [rsp+170h+var_120]
0x1800e2cee  call    ??A?$vector@EV?$allocator@E@std@@@std@@QEAAAEAE_K@Z; std::vector<uchar>::operator[](unsigned __int64)
0x1800e2cf3  lea     r9, [rsp+170h+dwNumberOfBytesRead]; lpdwNumberOfBytesRead
0x1800e2cf8  mov     r8d, ebx; dwNumberOfBytesToRead
0x1800e2cfb  mov     rdx, rax; lpBuffer
0x1800e2cfe  mov     rcx, [rdi+78h]; hRequest
0x1800e2d02  call    cs:__imp_WinHttpReadData
0x1800e2d08  mov     ebx, eax
0x1800e2d0a  lea     rdx, [rdi+0A8h]
0x1800e2d11  lea     rcx, [rbp+70h+var_C0]
0x1800e2d15  call    ??0?$shared_ptr@UIServiceRequestTelemetryActivity@OfficeWebServiceApi@Mso@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity>(std::shared_ptr<Mso::OfficeWebServiceApi::IServiceRequestTelemetryActivity> const &)
0x1800e2d1a  mov     rdx, [rbp+70h+var_C0]
0x1800e2d1e  mov     ecx, [rsp+170h+dwNumberOfBytesRead]
0x1800e2d22  add     [rdx+14h], ecx
0x1800e2d25  lea     rcx, [rbp+70h+var_C0]; void *
0x1800e2d29  call    ??1?$shared_ptr@V?$StructuredObjectCopy@PEB_W@StructuredTraceCopier@Logging@Mso@@@std@@QEAA@XZ; std::shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>::~shared_ptr<Mso::Logging::StructuredTraceCopier::StructuredObjectCopy<wchar_t const *>>(void)
0x1800e2d2e  test    ebx, ebx
0x1800e2d30  jz      short loc_1800E2D47
0x1800e2d32  mov     [rsp+170h+var_100], r14d
0x1800e2d37  mov     [rsp+170h+var_F8], r14
0x1800e2d3c  mov     dword ptr [rbp+70h+var_F0], r14d
0x1800e2d40  lea     rax, [rsp+170h+var_100]
0x1800e2d45  jmp     short loc_1800E2D5E
0x1800e2d47  call    cs:__imp_GetLastError
0x1800e2d4d  mov     r8d, 288769Eh
0x1800e2d53  mov     edx, eax
0x1800e2d55  lea     rcx, [rbp+70h+var_90]
0x1800e2d59  call    ?ConvertDwToResult@Http@Mso@@YA?AUResult@12@KI@Z; Mso::Http::ConvertDwToResult(ulong,uint)
0x1800e2d5e  movsd   xmm0, qword ptr [rax+10h]
0x1800e2d63  movsd   [rbp+70h+var_D0], xmm0
0x1800e2d68  mov     r14d, [rax]
0x1800e2d6b  movq    xmm1, qword ptr [rax+8]
0x1800e2d70  mov     eax, dword ptr [rbp+70h+var_D0]
0x1800e2d73  mov     [rsp+170h+var_130], eax
0x1800e2d77  movq    [rsp+170h+var_138], xmm1
0x1800e2d7d  lea     rcx, [rbp+70h+var_A0]
0x1800e2d81  call    ??1?$shared_lock@Vshared_mutex@std@@@std@@QEAA@XZ; std::shared_lock<std::shared_mutex>::~shared_lock<std::shared_mutex>(void)
0x1800e2d86  xor     ebx, ebx
0x1800e2d88  test    r14d, r14d
0x1800e2d8b  jnz     short loc_1800E2D9E
0x1800e2d8d  add     r15d, [rsp+170h+dwNumberOfBytesRead]
0x1800e2d92  lea     rax, [rdi+0E8h]
0x1800e2d99  jmp     loc_1800E2AB8
0x1800e2d9e  call    cs:__imp_GetLastError
0x1800e2da4  lea     rcx, aShErrorcode; "SH_ErrorCode"
0x1800e2dab  mov     [rbp+70h+var_70], rcx
0x1800e2daf  mov     [rbp+70h+var_68], eax
0x1800e2db2  mov     eax, 4
0x1800e2db7  mov     [rbp+70h+var_64], ax
0x1800e2dbb  xorps   xmm0, xmm0
0x1800e2dbe  movups  [rbp+70h+var_60], xmm0
0x1800e2dc2  mov     [rbp+70h+var_50], rbx
0x1800e2dc6  mov     [rbp+70h+var_48], 7
0x1800e2dce  mov     word ptr [rbp+70h+var_60], bx
0x1800e2dd2  lea     rax, ??_7ClassifiedStructuredErrorId@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredErrorId::`vftable'
0x1800e2dd9  mov     [rbp+70h+var_78], rax
0x1800e2ddd  lea     rax, aFailedToReadDa; "Failed to read data into buffer"
0x1800e2de4  mov     [rsp+170h+var_108], rax
0x1800e2de9  lea     rax, [rbp+70h+var_78]
0x1800e2ded  mov     [rsp+170h+var_148], rax
0x1800e2df2  lea     rax, [rsp+170h+var_108]
0x1800e2df7  mov     [rsp+170h+var_150], rax
0x1800e2dfc  mov     r8d, r13d
0x1800e2dff  mov     ecx, 1E3D8650h
0x1800e2e04  call    ??$SendDiagnosticTrace@UResult@Structured@Logging@Http@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAUResult@Structured@3Http@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Http::Logging::Structured::Result>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Http::Logging::Structured::Result &&)
0x1800e2e09  lea     rcx, [rbp+70h+var_60]; void *
0x1800e2e0d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800e2e12  jmp     loc_1800E2E97
0x1800e2e17  mov     ebx, r15d
0x1800e2e1a  mov     r13, [rsp+170h+var_120+8]
0x1800e2e1f  mov     rcx, r13
0x1800e2e22  sub     rcx, rdx
0x1800e2e25  cmp     rbx, rcx
0x1800e2e28  jnb     short loc_1800E2E30
0x1800e2e2a  lea     rax, [rdx+rbx]
0x1800e2e2e  jmp     short loc_1800E2E65
0x1800e2e30  jbe     short loc_1800E2E6A
0x1800e2e32  mov     rax, [rsp+170h+var_110]
0x1800e2e37  sub     rax, rdx
0x1800e2e3a  cmp     rbx, rax
0x1800e2e3d  jbe     short loc_1800E2E51
0x1800e2e3f  lfence
0x1800e2e42  mov     rdx, rbx
0x1800e2e45  lea     rcx, [rsp+170h+var_120]
0x1800e2e4a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800e2e4f  jmp     short loc_1800E2E6A
0x1800e2e51  sub     rbx, rcx
0x1800e2e54  mov     r8, rbx; Size
0x1800e2e57  xor     edx, edx; Val
0x1800e2e59  mov     rcx, r13; void *
0x1800e2e5c  call    memset
0x1800e2e61  lea     rax, [rbx+r13]
0x1800e2e65  mov     [rsp+170h+var_120+8], rax
0x1800e2e6a  lea     rdx, [rsp+170h+var_120]
0x1800e2e6f  mov     rcx, r12
0x1800e2e72  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> &&)
0x1800e2e77  mov     [rdi+0A0h], r15d
0x1800e2e7e  mov     [rsp+170h+var_140], 0Ah
0x1800e2e83  lea     rcx, [rdi+140h]; this
0x1800e2e8a  mov     r8b, 1; bool
0x1800e2e8d  lea     rdx, [rsp+170h+var_140]; enum Mso::Http::HttpRequestWinTimings::TimingEvent *
0x1800e2e92  call    ?SetTiming@HttpRequestWinTimings@Http@Mso@@QEAAXAEBW4TimingEvent@123@_N@Z; Mso::Http::HttpRequestWinTimings::SetTiming(Mso::Http::HttpRequestWinTimings::TimingEvent const &,bool)
0x1800e2e97  mov     byte ptr [rdi+0A4h], 1
0x1800e2e9e  mov     [rdi+0D0h], r14d
0x1800e2ea5  mov     rax, [rsp+170h+var_138]
0x1800e2eaa  mov     [rdi+0D8h], rax
0x1800e2eb1  mov     eax, [rsp+170h+var_130]
0x1800e2eb5  mov     [rdi+0E0h], eax
0x1800e2ebb  movups  xmm0, xmmword ptr [rdi+0D0h]
0x1800e2ec2  movups  xmmword ptr [rsi], xmm0
0x1800e2ec5  movsd   xmm1, qword ptr [rdi+0E0h]
0x1800e2ecd  movsd   qword ptr [rsi+10h], xmm1
0x1800e2ed2  lea     rcx, [rsp+170h+var_120]
0x1800e2ed7  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x1800e2edc  mov     rax, rsi
0x1800e2edf  mov     rcx, [rbp+70h+var_40]
0x1800e2ee3  xor     rcx, rsp; StackCookie
  ... truncated ...
```
