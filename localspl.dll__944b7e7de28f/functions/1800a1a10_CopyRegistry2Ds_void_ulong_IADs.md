# CopyRegistry2Ds(void *,ulong,IADs *)

- ea: `0x1800a1a10`
- end: `0x1800a1ebb`
- name: `?CopyRegistry2Ds@@YAJPEAXKPEAUIADs@@@Z`
- size: `1195`
- prototype: `int(void *, unsigned int, struct IADs *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800a2374`

## callees

- `0x180008520`
- `0x180008560`
- `0x18000edc4`
- `0x180035ae4`
- `0x18003e984`
- `0x1800431d0`
- `0x180046650`
- `0x180054638`
- `0x18008d480`
- `0x1800a1a10`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1aab`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1b38`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1d0a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a1dd0`
- `SPOOLSS!DllFreeSplMem` at `0x1800a1e78`
- `SPOOLSS!DllFreeSplMem` at `0x1800a1e78`
- `SPOOLSS!DllAllocSplMem` at `0x1800a1b21`
- `SPOOLSS!DllAllocSplMem` at `0x1800a1b21`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800a1a9d`
- `SPOOLSS!RevertToPrinterSelf` at `0x1800a1a9d`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a1aff`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a1b32`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a1b72`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a1aff`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a1b32`
- `SPOOLSS!ImpersonatePrinterClient` at `0x1800a1b72`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a1d3a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a1e00`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a1d3a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800a1e00`
- `ACTIVEDS!__imp_ADsGetLastError` at `0x1800a1c25`
- `ACTIVEDS!__imp_ADsGetLastError` at `0x1800a1d86`
- `ACTIVEDS!__imp_ADsGetLastError` at `0x1800a1c25`
- `ACTIVEDS!__imp_ADsGetLastError` at `0x1800a1d86`

## string_xrefs

- `0x1800a1bab`: `CopyRegistry2Ds`
- `0x1800a1bfa`: `CopyRegistry2Ds`
- `0x1800a1c40`: `CopyRegistry2Ds`
- `0x1800a1c8f`: `CopyRegistry2Ds`
- `0x1800a1e28`: `CopyRegistry2Ds`
- `0x1800a1e89`: `CopyRegistry2Ds`

## pseudocode

```c
__int64 __fastcall CopyRegistry2Ds(_QWORD *a1, int a2, struct IADs *a3)
{
  __int64 v3; // rsi
  unsigned int v5; // ecx
  __int64 v6; // r14
  HANDLE v9; // rdi
  signed int LastError; // eax
  signed int v11; // ebx
  DWORD v12; // ebx
  int v13; // ebx
  void *v14; // rcx
  __int64 v15; // rax
  unsigned int i; // edi
  __int64 v17; // rbx
  int v18; // eax
  signed int v19; // eax
  unsigned int j; // r13d
  __int64 v21; // r14
  int v22; // eax
  unsigned int v23; // ebx
  const unsigned __int16 *v24; // rbx
  BSTR v25; // rdi
  DWORD v26; // eax
  const unsigned __int16 *v27; // rbx
  BSTR v28; // rdi
  DWORD v29; // eax
  __int64 v30; // rcx
  __int64 v31; // rax
  unsigned int v33; // [rsp+30h] [rbp-40h] BYREF
  unsigned int v34; // [rsp+34h] [rbp-3Ch] BYREF
  DWORD Error; // [rsp+38h] [rbp-38h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-30h] BYREF
  __int64 v37; // [rsp+48h] [rbp-28h]
  unsigned __int16 v38[12]; // [rsp+50h] [rbp-20h] BYREF

  v3 = 0;
  Error = 0;
  v34 = 0;
  v5 = 0;
  v33 = 0;
  v6 = 0;
  bstrString = 0;
  if ( !off_18013D598 )
    goto LABEL_55;
  do
  {
    if ( (a2 & qword_18013D590[2 * v5]) != 0 )
      v6 = qword_18013D590[2 * v5 + 1];
    ++v5;
  }
  while ( qword_18013D590[2 * v5 + 1] );
  if ( !v6 )
  {
LABEL_55:
    v11 = -2147024809;
    goto LABEL_56;
  }
  v37 = a1[8];
  v9 = RevertToPrinterSelf();
  if ( !v9 )
  {
LABEL_7:
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError <= 0 )
      goto LABEL_56;
    v12 = (unsigned __int16)LastError;
    goto LABEL_9;
  }
  v13 = SplEnumPrinterDataEx((_DWORD)a1, v6, 0, v34, (char)&v34, (char)&v33);
  if ( v13 != 234 )
  {
    v14 = v9;
    goto LABEL_12;
  }
  v15 = DllAllocSplMem(v34);
  v3 = v15;
  if ( !v15 )
  {
    ImpersonatePrinterClient(v9);
    v12 = GetLastError();
LABEL_9:
    v11 = v12 | 0x80070000;
    goto LABEL_56;
  }
  v13 = SplEnumPrinterDataEx((_DWORD)a1, v6, v15, v34, (char)&v34, (char)&v33);
  v14 = v9;
  if ( v13 )
  {
LABEL_12:
    v11 = v13 | 0x80070000;
    ImpersonatePrinterClient(v14);
    if ( (_WORD)v11 != 2 || a2 == 1 )
      goto LABEL_56;
    goto LABEL_52;
  }
  if ( !ImpersonatePrinterClient(v9) )
    goto LABEL_7;
  for ( i = 0; i < v33; ++i )
  {
    v17 = 32LL * i;
    v18 = PublishDsData(
            a3,
            *(unsigned __int16 **)(v17 + v3),
            *(_DWORD *)(v17 + v3 + 12),
            *(unsigned __int8 **)(v17 + v3 + 16));
    if ( v18 < 0 )
    {
      if ( *(_QWORD *)(v17 + v3) )
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "CopyRegistry2Ds",
          L"Put property failed: hr: 0x%x, %ws",
          (unsigned int)v18);
      else
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "CopyRegistry2Ds",
          L"Put property failed: hr: 0x%x",
          (unsigned int)v18);
    }
  }
  v19 = ((__int64 (__fastcall *)(struct IADs *))a3->lpVtbl->SetInfo)(a3);
  v11 = v19;
  if ( v19 < 0 )
  {
    if ( (_WORD)v19 == 1208 )
    {
      ADsGetLastError(&Error, 0, 0, 0, 0);
      v11 = Error;
    }
    else
    {
      Error = v19;
    }
    LocalSpoolerTelemetry::WriteDbgTraceInfo(
      "CopyRegistry2Ds",
      L"Mass Publishing Failed for %ws: hr: 0x%x",
      v6,
      (unsigned int)v11);
    v11 = ((__int64 (__fastcall *)(struct IADs *))a3->lpVtbl->GetInfo)(a3);
    if ( v11 < 0 )
      goto LABEL_56;
    for ( j = 0; j < v33; ++j )
    {
      v21 = 32LL * j;
      v22 = PublishDsData(
              a3,
              *(unsigned __int16 **)(v21 + v3),
              *(_DWORD *)(v21 + v3 + 12),
              *(unsigned __int8 **)(v21 + v3 + 16));
      v23 = v22;
      if ( v22 >= 0 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo("CopyRegistry2Ds", L"Put2 %ws succeeded", *(_QWORD *)(v21 + v3));
      }
      else
      {
        if ( *(_QWORD *)(v21 + v3) )
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "CopyRegistry2Ds",
            L"Put property failed: hr: 0x%x, %ws",
            (unsigned int)v22);
        else
          LocalSpoolerTelemetry::WriteDbgTraceWarning(
            "CopyRegistry2Ds",
            L"Put property failed: hr: 0x%x",
            (unsigned int)v22);
        StringCchPrintfW(v38, 0xBu, L"%x", v23);
        if ( ((int (__fastcall *)(struct IADs *, BSTR *))a3->lpVtbl->get_ADsPath)(a3, &bstrString) >= 0 )
        {
          v24 = L"NULLName";
          v25 = bstrString;
          if ( *(_QWORD *)(v21 + v3) )
            v24 = *(const unsigned __int16 **)(v21 + v3);
          v26 = GetLastError();
          SplLogEvent(&MSG_CANT_PUBLISH_PROPERTY, v26, v24, v25, v38, 0);
          SysFreeString(bstrString);
        }
      }
      v11 = ((__int64 (__fastcall *)(struct IADs *))a3->lpVtbl->SetInfo)(a3);
      if ( v11 >= 0 )
      {
        LocalSpoolerTelemetry::WriteDbgTraceInfo("CopyRegistry2Ds", L"Published: %ws", *(_QWORD *)(v21 + v3));
      }
      else
      {
        if ( (_WORD)v11 == 1208 )
          ADsGetLastError(&Error, 0, 0, 0, 0);
        StringCchPrintfW(v38, 0xBu, L"%x", (unsigned int)v11);
        if ( ((int (__fastcall *)(struct IADs *, BSTR *))a3->lpVtbl->get_ADsPath)(a3, &bstrString) >= 0 )
        {
          v27 = L"NULLName";
          v28 = bstrString;
          if ( *(_QWORD *)(v21 + v3) )
            v27 = *(const unsigned __int16 **)(v21 + v3);
          v29 = GetLastError();
          SplLogEvent(&MSG_CANT_PUBLISH_PROPERTY, v29, v27, v28, v38, 0);
          SysFreeString(bstrString);
        }
        v11 = ((__int64 (__fastcall *)(struct IADs *))a3->lpVtbl->GetInfo)(a3);
        if ( v11 < 0 )
          goto LABEL_56;
      }
    }
  }
  else
  {
    LocalSpoolerTelemetry::WriteDbgTraceInfo("CopyRegistry2Ds", L"Mass Publishing Succeeded for %ws", v6);
  }
LABEL_52:
  EnterSplSem(0);
  v31 = v37;
  *(_DWORD *)(v37 + 344) &= ~a2;
  if ( (*(_BYTE *)(v31 + 344) & 7) == 0 )
    *(_DWORD *)(v31 + 344) = 0;
  LeaveSplSem(v30);
LABEL_56:
  DllFreeSplMem(v3);
  if ( v11 < 0 )
    LocalSpoolerTelemetry::WriteDbgTraceInfo("CopyRegistry2Ds", L"Mass publishing failed.");
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800a1a10  mov     [rsp-38h+arg_8], rbx
0x1800a1a15  push    rbp
0x1800a1a16  push    rsi
0x1800a1a17  push    rdi
0x1800a1a18  push    r12
0x1800a1a1a  push    r13
0x1800a1a1c  push    r14
0x1800a1a1e  push    r15
0x1800a1a20  mov     rbp, rsp
0x1800a1a23  sub     rsp, 70h
0x1800a1a27  mov     rax, cs:__security_cookie
0x1800a1a2e  xor     rax, rsp
0x1800a1a31  mov     [rbp+var_8], rax
0x1800a1a35  xor     esi, esi
0x1800a1a37  mov     [rbp+Error], 0
0x1800a1a3e  mov     r13, rcx
0x1800a1a41  mov     [rbp+var_3C], 0
0x1800a1a48  xor     ecx, ecx
0x1800a1a4a  mov     [rbp+var_40], esi
0x1800a1a4d  xor     r14d, r14d
0x1800a1a50  mov     [rbp+bstrString], rsi
0x1800a1a54  cmp     cs:off_18013D598, rcx; "DsSpooler"
0x1800a1a5b  mov     r15, r8
0x1800a1a5e  mov     r12d, edx
0x1800a1a61  jz      loc_1800A1E70
0x1800a1a67  lea     rdx, qword_18013D590
0x1800a1a6e  mov     eax, ecx
0x1800a1a70  add     rax, rax
0x1800a1a73  test    [rdx+rax*8], r12d
0x1800a1a77  jz      short loc_1800A1A7E
0x1800a1a79  mov     r14, [rdx+rax*8+8]
0x1800a1a7e  inc     ecx
0x1800a1a80  mov     eax, ecx
0x1800a1a82  add     rax, rax
0x1800a1a85  cmp     [rdx+rax*8+8], rsi
0x1800a1a8a  jnz     short loc_1800A1A6E
0x1800a1a8c  test    r14, r14
0x1800a1a8f  jz      loc_1800A1E70
0x1800a1a95  mov     rax, [r13+40h]
0x1800a1a99  mov     [rbp+var_28], rax
0x1800a1a9d  call    cs:__imp_RevertToPrinterSelf
0x1800a1aa3  mov     rdi, rax
0x1800a1aa6  test    rax, rax
0x1800a1aa9  jnz     short loc_1800A1AC9
0x1800a1aab  call    cs:__imp_GetLastError
0x1800a1ab1  mov     ebx, eax
0x1800a1ab3  test    eax, eax
0x1800a1ab5  jle     loc_1800A1E75
0x1800a1abb  movzx   ebx, ax
0x1800a1abe  or      ebx, 80070000h
0x1800a1ac4  jmp     loc_1800A1E75
0x1800a1ac9  mov     r9d, [rbp+var_3C]
0x1800a1acd  lea     rax, [rbp+var_40]
0x1800a1ad1  mov     [rsp+70h+var_48], rax
0x1800a1ad6  xor     r8d, r8d
0x1800a1ad9  lea     rax, [rbp+var_3C]
0x1800a1add  mov     rdx, r14
0x1800a1ae0  mov     rcx, r13
0x1800a1ae3  mov     qword ptr [rsp+70h+dwNameBufLen], rax
0x1800a1ae8  call    SplEnumPrinterDataEx
0x1800a1aed  mov     ebx, eax
0x1800a1aef  cmp     eax, 0EAh
0x1800a1af4  jz      short loc_1800A1B1E
0x1800a1af6  mov     rcx, rdi; hToken
0x1800a1af9  or      ebx, 80070000h
0x1800a1aff  call    cs:__imp_ImpersonatePrinterClient
0x1800a1b05  cmp     bx, 2
0x1800a1b09  jnz     loc_1800A1E75
0x1800a1b0f  cmp     r12d, 1
0x1800a1b13  jnz     loc_1800A1E41
0x1800a1b19  jmp     loc_1800A1E75
0x1800a1b1e  mov     ecx, [rbp+var_3C]
0x1800a1b21  call    cs:__imp_DllAllocSplMem
0x1800a1b27  mov     rsi, rax
0x1800a1b2a  test    rax, rax
0x1800a1b2d  jnz     short loc_1800A1B45
0x1800a1b2f  mov     rcx, rdi; hToken
0x1800a1b32  call    cs:__imp_ImpersonatePrinterClient
0x1800a1b38  call    cs:__imp_GetLastError
0x1800a1b3e  mov     ebx, eax
0x1800a1b40  jmp     loc_1800A1ABE
0x1800a1b45  mov     r9d, [rbp+var_3C]
0x1800a1b49  lea     rax, [rbp+var_40]
0x1800a1b4d  mov     [rsp+70h+var_48], rax
0x1800a1b52  mov     r8, rsi
0x1800a1b55  lea     rax, [rbp+var_3C]
0x1800a1b59  mov     rdx, r14
0x1800a1b5c  mov     rcx, r13
0x1800a1b5f  mov     qword ptr [rsp+70h+dwNameBufLen], rax
0x1800a1b64  call    SplEnumPrinterDataEx
0x1800a1b69  mov     ebx, eax
0x1800a1b6b  mov     rcx, rdi; hToken
0x1800a1b6e  test    eax, eax
0x1800a1b70  jnz     short loc_1800A1AF9
0x1800a1b72  call    cs:__imp_ImpersonatePrinterClient
0x1800a1b78  test    eax, eax
0x1800a1b7a  jz      loc_1800A1AAB
0x1800a1b80  xor     edi, edi
0x1800a1b82  cmp     [rbp+var_40], edi
0x1800a1b85  jbe     short loc_1800A1BDB
0x1800a1b87  mov     ebx, edi
0x1800a1b89  mov     rcx, r15; struct IADs *
0x1800a1b8c  shl     rbx, 5
0x1800a1b90  mov     r9, [rbx+rsi+10h]; unsigned __int8 *
0x1800a1b95  mov     r8d, [rbx+rsi+0Ch]; unsigned int
0x1800a1b9a  mov     rdx, [rbx+rsi]; unsigned __int16 *
0x1800a1b9e  call    ?PublishDsData@@YAJPEAUIADs@@PEAGKPEAE@Z; PublishDsData(IADs *,ushort *,ulong,uchar *)
0x1800a1ba3  test    eax, eax
0x1800a1ba5  jns     short loc_1800A1BD4
0x1800a1ba7  mov     r9, [rbx+rsi]
0x1800a1bab  lea     rcx, aCopyregistry2d; "CopyRegistry2Ds"
0x1800a1bb2  mov     r8d, eax
0x1800a1bb5  test    r9, r9
0x1800a1bb8  jz      short loc_1800A1BC8
0x1800a1bba  lea     rdx, aPutPropertyFai_0; "Put property failed: hr: 0x%x, %ws"
0x1800a1bc1  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800a1bc6  jmp     short loc_1800A1BD4
0x1800a1bc8  lea     rdx, aPutPropertyFai; "Put property failed: hr: 0x%x"
0x1800a1bcf  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800a1bd4  inc     edi
0x1800a1bd6  cmp     edi, [rbp+var_40]
0x1800a1bd9  jb      short loc_1800A1B87
0x1800a1bdb  mov     rax, [r15]
0x1800a1bde  mov     rcx, r15
0x1800a1be1  mov     rax, [rax+70h]
0x1800a1be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1bea  mov     ebx, eax
0x1800a1bec  test    eax, eax
0x1800a1bee  js      short loc_1800A1C0B
0x1800a1bf0  mov     r8, r14
0x1800a1bf3  lea     rdx, aMassPublishing; "Mass Publishing Succeeded for %ws"
0x1800a1bfa  lea     rcx, aCopyregistry2d; "CopyRegistry2Ds"
0x1800a1c01  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800a1c06  jmp     loc_1800A1E41
0x1800a1c0b  cmp     ax, 4B8h
0x1800a1c0f  jnz     short loc_1800A1C30
0x1800a1c11  xor     r9d, r9d; lpNameBuf
0x1800a1c14  mov     [rsp+70h+dwNameBufLen], 0; dwNameBufLen
0x1800a1c1c  xor     r8d, r8d; dwErrorBufLen
0x1800a1c1f  lea     rcx, [rbp+Error]; lpError
0x1800a1c23  xor     edx, edx; lpErrorBuf
0x1800a1c25  call    cs:__imp_ADsGetLastError
0x1800a1c2b  mov     ebx, [rbp+Error]
0x1800a1c2e  jmp     short loc_1800A1C33
0x1800a1c30  mov     [rbp+Error], eax
0x1800a1c33  mov     r9d, ebx
0x1800a1c36  lea     rdx, aMassPublishing_0; "Mass Publishing Failed for %ws: hr: 0x%"...
0x1800a1c3d  mov     r8, r14
0x1800a1c40  lea     rcx, aCopyregistry2d; "CopyRegistry2Ds"
0x1800a1c47  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800a1c4c  mov     rax, [r15]
0x1800a1c4f  mov     rcx, r15
0x1800a1c52  mov     rax, [rax+68h]
0x1800a1c56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1c5b  mov     ebx, eax
0x1800a1c5d  test    eax, eax
0x1800a1c5f  js      loc_1800A1E75
0x1800a1c65  xor     r13d, r13d
0x1800a1c68  cmp     [rbp+var_40], r13d
0x1800a1c6c  jbe     loc_1800A1E41
0x1800a1c72  mov     r14d, r13d
0x1800a1c75  mov     rcx, r15; struct IADs *
0x1800a1c78  shl     r14, 5
0x1800a1c7c  mov     r9, [r14+rsi+10h]; unsigned __int8 *
0x1800a1c81  mov     r8d, [r14+rsi+0Ch]; unsigned int
0x1800a1c86  mov     rdx, [r14+rsi]; unsigned __int16 *
0x1800a1c8a  call    ?PublishDsData@@YAJPEAUIADs@@PEAGKPEAE@Z; PublishDsData(IADs *,ushort *,ulong,uchar *)
0x1800a1c8f  lea     rcx, aCopyregistry2d; "CopyRegistry2Ds"
0x1800a1c96  mov     ebx, eax
0x1800a1c98  test    eax, eax
0x1800a1c9a  jns     loc_1800A1D42
0x1800a1ca0  mov     r9, [r14+rsi]
0x1800a1ca4  mov     r8d, eax
0x1800a1ca7  test    r9, r9
0x1800a1caa  jz      short loc_1800A1CBA
0x1800a1cac  lea     rdx, aPutPropertyFai_0; "Put property failed: hr: 0x%x, %ws"
0x1800a1cb3  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800a1cb8  jmp     short loc_1800A1CC6
0x1800a1cba  lea     rdx, aPutPropertyFai; "Put property failed: hr: 0x%x"
0x1800a1cc1  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x1800a1cc6  mov     r9d, ebx
0x1800a1cc9  lea     r8, Format; "%x"
0x1800a1cd0  mov     edx, 0Bh; unsigned __int64
0x1800a1cd5  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x1800a1cd9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1cde  mov     rax, [r15]
0x1800a1ce1  lea     rdx, [rbp+bstrString]
0x1800a1ce5  mov     rcx, r15
0x1800a1ce8  mov     rax, [rax+50h]
0x1800a1cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1cf1  test    eax, eax
0x1800a1cf3  js      short loc_1800A1D52
0x1800a1cf5  cmp     qword ptr [r14+rsi], 0
0x1800a1cfa  lea     rbx, aNullname; "NULLName"
0x1800a1d01  mov     rdi, [rbp+bstrString]
0x1800a1d05  cmovnz  rbx, [r14+rsi]
0x1800a1d0a  call    cs:__imp_GetLastError
0x1800a1d10  lea     rcx, [rbp+var_20]
0x1800a1d14  mov     [rsp+70h+var_48], 0
0x1800a1d1d  mov     qword ptr [rsp+70h+dwNameBufLen], rcx
0x1800a1d22  mov     r9, rdi
0x1800a1d25  lea     rcx, MSG_CANT_PUBLISH_PROPERTY; struct _EVENT_DESCRIPTOR *
0x1800a1d2c  mov     r8, rbx; unsigned __int16 *
0x1800a1d2f  mov     edx, eax; unsigned int
0x1800a1d31  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800a1d36  mov     rcx, [rbp+bstrString]; bstrString
0x1800a1d3a  call    cs:__imp_SysFreeString
0x1800a1d40  jmp     short loc_1800A1D52
0x1800a1d42  mov     r8, [r14+rsi]
0x1800a1d46  lea     rdx, aPut2WsSucceede; "Put2 %ws succeeded"
0x1800a1d4d  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800a1d52  mov     rax, [r15]
0x1800a1d55  mov     rcx, r15
0x1800a1d58  mov     rax, [rax+70h]
0x1800a1d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1d61  mov     ebx, eax
0x1800a1d63  test    eax, eax
0x1800a1d65  jns     loc_1800A1E1D
0x1800a1d6b  cmp     bx, 4B8h
0x1800a1d70  jnz     short loc_1800A1D8C
0x1800a1d72  xor     r9d, r9d; lpNameBuf
0x1800a1d75  mov     [rsp+70h+dwNameBufLen], 0; dwNameBufLen
0x1800a1d7d  xor     r8d, r8d; dwErrorBufLen
0x1800a1d80  lea     rcx, [rbp+Error]; lpError
0x1800a1d84  xor     edx, edx; lpErrorBuf
0x1800a1d86  call    cs:__imp_ADsGetLastError
0x1800a1d8c  mov     r9d, ebx
0x1800a1d8f  lea     r8, Format; "%x"
0x1800a1d96  mov     edx, 0Bh; unsigned __int64
0x1800a1d9b  lea     rcx, [rbp+var_20]; unsigned __int16 *
0x1800a1d9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800a1da4  mov     rax, [r15]
0x1800a1da7  lea     rdx, [rbp+bstrString]
0x1800a1dab  mov     rcx, r15
0x1800a1dae  mov     rax, [rax+50h]
0x1800a1db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1db7  test    eax, eax
0x1800a1db9  js      short loc_1800A1E06
0x1800a1dbb  cmp     qword ptr [r14+rsi], 0
0x1800a1dc0  lea     rbx, aNullname; "NULLName"
0x1800a1dc7  mov     rdi, [rbp+bstrString]
0x1800a1dcb  cmovnz  rbx, [r14+rsi]
0x1800a1dd0  call    cs:__imp_GetLastError
0x1800a1dd6  lea     rcx, [rbp+var_20]
0x1800a1dda  mov     [rsp+70h+var_48], 0
0x1800a1de3  mov     qword ptr [rsp+70h+dwNameBufLen], rcx
0x1800a1de8  mov     r9, rdi
0x1800a1deb  lea     rcx, MSG_CANT_PUBLISH_PROPERTY; struct _EVENT_DESCRIPTOR *
0x1800a1df2  mov     r8, rbx; unsigned __int16 *
0x1800a1df5  mov     edx, eax; unsigned int
0x1800a1df7  call    ?SplLogEvent@@YAXPEBU_EVENT_DESCRIPTOR@@KPEBGZZ; SplLogEvent(_EVENT_DESCRIPTOR const *,ulong,ushort const *,...)
0x1800a1dfc  mov     rcx, [rbp+bstrString]; bstrString
0x1800a1e00  call    cs:__imp_SysFreeString
0x1800a1e06  mov     rax, [r15]
0x1800a1e09  mov     rcx, r15
0x1800a1e0c  mov     rax, [rax+68h]
0x1800a1e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a1e15  mov     ebx, eax
0x1800a1e17  test    eax, eax
0x1800a1e19  js      short loc_1800A1E75
0x1800a1e1b  jmp     short loc_1800A1E34
0x1800a1e1d  mov     r8, [r14+rsi]
0x1800a1e21  lea     rdx, aPublishedWs; "Published: %ws"
0x1800a1e28  lea     rcx, aCopyregistry2d; "CopyRegistry2Ds"
0x1800a1e2f  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800a1e34  inc     r13d
0x1800a1e37  cmp     r13d, [rbp+var_40]
0x1800a1e3b  jb      loc_1800A1C72
0x1800a1e41  xor     ecx, ecx
0x1800a1e43  call    EnterSplSem
0x1800a1e48  mov     rax, [rbp+var_28]
0x1800a1e4c  not     r12d
0x1800a1e4f  and     [rax+158h], r12d
0x1800a1e56  test    byte ptr [rax+158h], 7
0x1800a1e5d  jnz     short loc_1800A1E69
0x1800a1e5f  mov     dword ptr [rax+158h], 0
0x1800a1e69  call    LeaveSplSem
0x1800a1e6e  jmp     short loc_1800A1E75
0x1800a1e70  mov     ebx, 80070057h
0x1800a1e75  mov     rcx, rsi
0x1800a1e78  call    cs:__imp_DllFreeSplMem
0x1800a1e7e  test    ebx, ebx
0x1800a1e80  jns     short loc_1800A1E95
0x1800a1e82  lea     rdx, aMassPublishing_1; "Mass publishing failed."
0x1800a1e89  lea     rcx, aCopyregistry2d; "CopyRegistry2Ds"
0x1800a1e90  call    ?WriteDbgTraceInfo@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800a1e95  mov     eax, ebx
0x1800a1e97  mov     rcx, [rbp+var_8]
0x1800a1e9b  xor     rcx, rsp; StackCookie
0x1800a1e9e  call    __security_check_cookie
0x1800a1ea3  mov     rbx, [rsp+70h+arg_8]
0x1800a1eab  add     rsp, 70h
0x1800a1eaf  pop     r15
0x1800a1eb1  pop     r14
0x1800a1eb3  pop     r13
0x1800a1eb5  pop     r12
0x1800a1eb7  pop     rdi
0x1800a1eb8  pop     rsi
0x1800a1eb9  pop     rbp
0x1800a1eba  retn
  ... truncated ...
```
