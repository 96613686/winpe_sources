# CComExport::ExportAsMSI(_GUID const &,ushort const *,ushort const *,ulong)

- ea: `0x180051a60`
- end: `0x180051e29`
- name: `?ExportAsMSI@CComExport@@UEAAJAEBU_GUID@@PEBG1K@Z`
- size: `969`
- prototype: `__int64 __fastcall(CComExport *this, const struct _GUID *, const unsigned __int16 *, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180050e68`
- `0x180051030`
- `0x1800513f8`
- `0x1800516e4`
- `0x180051800`
- `0x180051a60`
- `0x1800524f0`
- `0x180052ea4`
- `0x18005551a`
- `0x180055550`
- `0x180058010`

## import_xrefs

- `CLBCatQ!ServerGetApplicationType` at `0x180051c02`
- `CLBCatQ!ServerGetApplicationType` at `0x180051c02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180051b59`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180051b4f`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180051b4f`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180051b8b`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180051b8b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180051daa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180051db4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180051daa`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180051db4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051dfe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051dd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051dfe`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180051c19`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x180051c19`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180051dbf`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180051dbf`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180051c8d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180051c8d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051b1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051be6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051b1d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180051be6`

## pseudocode

```c
__int64 __fastcall CComExport::ExportAsMSI(
        CComExport *this,
        const struct _GUID *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        unsigned int a5)
{
  unsigned __int16 *v8; // rsi
  CComExport *v10; // rcx
  int Instance; // edi
  int v12; // eax
  signed int LastError; // eax
  int v14; // ebx
  int v15; // r14d
  CComExport *v16; // rcx
  struct ISimpleTableDispenser *v17; // rcx
  unsigned __int16 *v18; // rbx
  int v19; // eax
  CComExport *v20; // rcx
  CComExport *v21; // rcx
  int v22; // eax
  struct ISimpleTableDispenser *ppv; // [rsp+68h] [rbp-98h] BYREF
  struct ICOMMSIGen *v25; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v26; // [rsp+78h] [rbp-88h] BYREF
  int v27; // [rsp+80h] [rbp-80h] BYREF
  LPOLESTR lpsz; // [rsp+88h] [rbp-78h] BYREF
  int v29; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v30[12]; // [rsp+94h] [rbp-6Ch] BYREF
  __int64 v31; // [rsp+A0h] [rbp-60h]
  __int64 v32; // [rsp+A8h] [rbp-58h]
  __int64 v33; // [rsp+B0h] [rbp-50h]
  __int64 v34; // [rsp+B8h] [rbp-48h]
  WCHAR Buffer; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v36[526]; // [rsp+112h] [rbp+12h] BYREF

  v25 = 0;
  lpsz = 0;
  v26 = 0;
  Buffer = 0;
  v8 = 0;
  memset_0(v36, 0, 0x206u);
  v27 = 1;
  v29 = 0;
  memset_0(v30, 0, 0x74u);
  ppv = 0;
  CComExport::Uninit(this);
  if ( a4 && *a4 )
  {
    v8 = a4;
  }
  else
  {
    Instance = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
    if ( Instance < 0
      || (v12 = CComExport::CalculateRSN(v10, ppv, a2, (const unsigned __int16 **)&v26),
          v8 = v26,
          Instance = v12,
          v12 < 0) )
    {
LABEL_9:
      v14 = 0;
      v15 = 0;
      goto LABEL_30;
    }
  }
  if ( !GetTempPathW(0x104u, &Buffer) || !GetTempFileNameW(&Buffer, L"APL", 0, &Buffer) )
  {
    LastError = GetLastError();
    Instance = LastError;
    if ( LastError > 0 )
      Instance = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_9;
  }
  Instance = CComExport::ExportApplication(v16, a2, &Buffer, a5, (struct CComExport::AppExportInfo *)&v29);
  if ( Instance < 0 )
    goto LABEL_29;
  v17 = ppv;
  if ( !ppv )
  {
    Instance = CoCreateInstance(&clsidSTDISP, 0, 1u, &IID_ISimpleTableDispenser, (LPVOID *)&ppv);
    if ( Instance >= 0 )
    {
      v17 = ppv;
      goto LABEL_15;
    }
LABEL_29:
    v14 = 0;
    v15 = 0;
    goto LABEL_30;
  }
LABEL_15:
  Instance = ServerGetApplicationType(v17, a2, &v27);
  if ( Instance < 0 )
    goto LABEL_29;
  Instance = StringFromCLSID(a2, &lpsz);
  if ( Instance < 0 )
    goto LABEL_29;
  v26 = 0;
  Instance = ATL::CComObject<CGenerateMSI>::CreateInstance(&v26);
  if ( Instance < 0 )
    goto LABEL_29;
  v18 = v26;
  (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v26 + 8LL))(v26);
  Instance = (**(__int64 (__fastcall ***)(unsigned __int16 *, GUID *, struct ICOMMSIGen **))v18)(
               v18,
               &IID_ICOMMSIGen,
               &v25);
  (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v18 + 16LL))(v18);
  if ( Instance < 0 )
    goto LABEL_29;
  Instance = CoImpersonateClient();
  if ( Instance < 0 )
    goto LABEL_29;
  v14 = 1;
  v15 = 1;
  v19 = (*(__int64 (__fastcall **)(struct ICOMMSIGen *, const unsigned __int16 *, int *, __int64, __int64, __int64, __int64, LPOLESTR, unsigned int, int))(*(_QWORD *)v25 + 24LL))(
          v25,
          a3,
          &v29,
          v31,
          v33,
          v34,
          v32,
          lpsz,
          a5,
          v27);
  Instance = v19;
  if ( v19 >= 0 )
  {
    Instance = CComExport::AddApplicationToMSI(v20, v25, (struct CComExport::AppExportInfo *)&v29, v8, a5);
    if ( Instance >= 0 )
    {
      if ( (*(int (__fastcall **)(struct ICOMMSIGen *))(*(_QWORD *)v25 + 72LL))(v25) >= 0 )
      {
        v22 = CComExport::CabMsiFile(v21, a3, a5);
        if ( v22 )
          v22 = -2146368505;
        Instance = v22;
      }
      else
      {
        Instance = -2146368505;
      }
    }
  }
  else
  {
    v14 = 0;
    if ( v19 != -2146368499 )
      Instance = -2146368505;
  }
LABEL_30:
  if ( ppv )
    (*(void (__fastcall **)(struct ISimpleTableDispenser *))(*(_QWORD *)ppv + 16LL))(ppv);
  CComExport::FreeAppInfo((struct CComExport::AppExportInfo *)&v29);
  if ( Instance < 0 )
  {
    if ( v25 )
    {
      (*(void (__fastcall **)(struct ICOMMSIGen *))(*(_QWORD *)v25 + 72LL))(v25);
      if ( v14 )
        DeleteFileW(a3);
    }
  }
  DeleteFileW(&Buffer);
  if ( v15 )
    CoRevertToSelf();
  if ( v8 && (!a4 || !*a4) )
    CoTaskMemFree(v8);
  if ( v25 )
    (*(void (__fastcall **)(struct ICOMMSIGen *))(*(_QWORD *)v25 + 16LL))(v25);
  if ( lpsz )
    CoTaskMemFree(lpsz);
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x180051a60  push    rbp
0x180051a62  push    rbx
0x180051a63  push    rsi
0x180051a64  push    rdi
0x180051a65  push    r12
0x180051a67  push    r13
0x180051a69  push    r14
0x180051a6b  push    r15
0x180051a6d  lea     rbp, [rsp-238h]
0x180051a75  sub     rsp, 338h
0x180051a7c  mov     rax, cs:__security_cookie
0x180051a83  xor     rax, rsp
0x180051a86  mov     [rbp+270h+var_50], rax
0x180051a8d  xor     r15d, r15d
0x180051a90  mov     r13, r8
0x180051a93  mov     r14, rdx
0x180051a96  mov     [rsp+370h+var_300], r15
0x180051a9b  mov     rbx, rcx
0x180051a9e  mov     [rbp+270h+lpsz], r15
0x180051aa2  xor     edx, edx; Val
0x180051aa4  mov     [rsp+370h+var_2F8], r15
0x180051aa9  mov     r8d, 206h; Size
0x180051aaf  mov     [rbp+270h+Buffer], r15w
0x180051ab4  lea     rcx, [rbp+270h+var_25E]; void *
0x180051ab8  mov     esi, r15d
0x180051abb  mov     r12, r9
0x180051abe  call    memset_0
0x180051ac3  lea     edi, [r15+1]
0x180051ac7  mov     [rsp+370h+var_310], r15d
0x180051acc  xor     edx, edx; Val
0x180051ace  mov     [rbp+270h+var_2F0], edi
0x180051ad1  lea     r8d, [r15+74h]; Size
0x180051ad5  mov     [rbp+270h+var_2E0], r15d
0x180051ad9  lea     rcx, [rbp+270h+var_2DC]; void *
0x180051add  call    memset_0
0x180051ae2  mov     rcx, rbx; this
0x180051ae5  mov     [rsp+370h+var_308], r15
0x180051aea  call    ?Uninit@CComExport@@IEAAXXZ; CComExport::Uninit(void)
0x180051aef  test    r12, r12
0x180051af2  jz      short loc_180051B00
0x180051af4  cmp     [r12], r15w
0x180051af9  jz      short loc_180051B00
0x180051afb  mov     rsi, r12
0x180051afe  jmp     short loc_180051B46
0x180051b00  lea     rax, [rsp+370h+var_308]
0x180051b05  mov     r8d, edi; dwClsContext
0x180051b08  lea     r9, IID_ISimpleTableDispenser; riid
0x180051b0f  mov     [rsp+370h+ppv], rax; ppv
0x180051b14  xor     edx, edx; pUnkOuter
0x180051b16  lea     rcx, clsidSTDISP; rclsid
0x180051b1d  call    cs:__imp_CoCreateInstance
0x180051b23  mov     edi, eax
0x180051b25  test    eax, eax
0x180051b27  js      short loc_180051B6E
0x180051b29  mov     rdx, [rsp+370h+var_308]; struct ISimpleTableDispenser *
0x180051b2e  lea     r9, [rsp+370h+var_2F8]; unsigned __int16 **
0x180051b33  mov     r8, r14; struct _GUID *
0x180051b36  call    ?CalculateRSN@CComExport@@IEAAJPEAUISimpleTableDispenser@@AEBU_GUID@@PEAPEBG@Z; CComExport::CalculateRSN(ISimpleTableDispenser *,_GUID const &,ushort const * *)
0x180051b3b  mov     rsi, [rsp+370h+var_2F8]
0x180051b40  mov     edi, eax
0x180051b42  test    eax, eax
0x180051b44  js      short loc_180051B6E
0x180051b46  lea     rdx, [rbp+270h+Buffer]; lpBuffer
0x180051b4a  mov     ecx, 104h; nBufferLength
0x180051b4f  call    cs:__imp_GetTempPathW
0x180051b55  test    eax, eax
0x180051b57  jnz     short loc_180051B79
0x180051b59  call    cs:__imp_GetLastError
0x180051b5f  mov     edi, eax
0x180051b61  test    eax, eax
0x180051b63  jle     short loc_180051B6E
0x180051b65  movzx   edi, ax
0x180051b68  or      edi, 80070000h
0x180051b6e  mov     ebx, r15d
0x180051b71  mov     r14d, r15d
0x180051b74  jmp     loc_180051D6A
0x180051b79  lea     r9, [rbp+270h+Buffer]; lpTempFileName
0x180051b7d  xor     r8d, r8d; uUnique
0x180051b80  lea     rdx, aApl; "APL"
0x180051b87  lea     rcx, [rbp+270h+Buffer]; lpPathName
0x180051b8b  call    cs:__imp_GetTempFileNameW
0x180051b91  test    eax, eax
0x180051b93  jz      short loc_180051B59
0x180051b95  mov     r15d, [rbp+270h+arg_20]
0x180051b9c  lea     rax, [rbp+270h+var_2E0]
0x180051ba0  mov     r9d, r15d; unsigned int
0x180051ba3  mov     [rsp+370h+ppv], rax; struct CComExport::AppExportInfo *
0x180051ba8  lea     r8, [rbp+270h+Buffer]; unsigned __int16 *
0x180051bac  mov     rdx, r14; struct _GUID *
0x180051baf  call    ?ExportApplication@CComExport@@IEAAJAEBU_GUID@@PEBGKPEAUAppExportInfo@1@@Z; CComExport::ExportApplication(_GUID const &,ushort const *,ulong,CComExport::AppExportInfo *)
0x180051bb4  mov     edi, eax
0x180051bb6  test    eax, eax
0x180051bb8  js      loc_180051D60
0x180051bbe  mov     rcx, [rsp+370h+var_308]
0x180051bc3  test    rcx, rcx
0x180051bc6  jnz     short loc_180051BFB
0x180051bc8  lea     rax, [rsp+370h+var_308]
0x180051bcd  xor     edx, edx; pUnkOuter
0x180051bcf  lea     r8d, [rcx+1]; dwClsContext
0x180051bd3  mov     [rsp+370h+ppv], rax; ppv
0x180051bd8  lea     rcx, clsidSTDISP; rclsid
0x180051bdf  lea     r9, IID_ISimpleTableDispenser; riid
0x180051be6  call    cs:__imp_CoCreateInstance
0x180051bec  mov     edi, eax
0x180051bee  test    eax, eax
0x180051bf0  js      loc_180051D60
0x180051bf6  mov     rcx, [rsp+370h+var_308]
0x180051bfb  lea     r8, [rbp+270h+var_2F0]
0x180051bff  mov     rdx, r14
0x180051c02  call    cs:__imp_ServerGetApplicationType
0x180051c08  mov     edi, eax
0x180051c0a  test    eax, eax
0x180051c0c  js      loc_180051D60
0x180051c12  lea     rdx, [rbp+270h+lpsz]; lplpsz
0x180051c16  mov     rcx, r14; rclsid
0x180051c19  call    cs:__imp_StringFromCLSID
0x180051c1f  mov     edi, eax
0x180051c21  test    eax, eax
0x180051c23  js      loc_180051D60
0x180051c29  lea     rcx, [rsp+370h+var_2F8]
0x180051c2e  mov     [rsp+370h+var_2F8], 0
0x180051c37  call    ?CreateInstance@?$CComObject@VCGenerateMSI@@@ATL@@SAJPEAPEAV12@@Z; ATL::CComObject<CGenerateMSI>::CreateInstance(ATL::CComObject<CGenerateMSI> * *)
0x180051c3c  mov     edi, eax
0x180051c3e  test    eax, eax
0x180051c40  js      loc_180051D60
0x180051c46  mov     rbx, [rsp+370h+var_2F8]
0x180051c4b  mov     rcx, rbx
0x180051c4e  mov     rax, [rbx]
0x180051c51  mov     rax, [rax+8]
0x180051c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c5a  mov     rax, [rbx]
0x180051c5d  lea     r8, [rsp+370h+var_300]
0x180051c62  lea     rdx, IID_ICOMMSIGen
0x180051c69  mov     rcx, rbx
0x180051c6c  mov     rax, [rax]
0x180051c6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c74  mov     edi, eax
0x180051c76  mov     rcx, rbx
0x180051c79  mov     rax, [rbx]
0x180051c7c  mov     rax, [rax+10h]
0x180051c80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c85  test    edi, edi
0x180051c87  js      loc_180051D60
0x180051c8d  call    cs:__imp_CoImpersonateClient
0x180051c93  mov     edi, eax
0x180051c95  test    eax, eax
0x180051c97  js      loc_180051D60
0x180051c9d  mov     edx, [rbp+270h+var_2F0]
0x180051ca0  lea     r8, [rbp+270h+var_2E0]
0x180051ca4  mov     rcx, [rsp+370h+var_300]
0x180051ca9  mov     ebx, 1
0x180051cae  mov     r9, [rbp+270h+var_2D0]
0x180051cb2  mov     r14d, ebx
0x180051cb5  mov     [rsp+370h+var_328], edx
0x180051cb9  mov     rdx, [rbp+270h+lpsz]
0x180051cbd  mov     rax, [rcx]
0x180051cc0  mov     [rsp+370h+var_330], r15d
0x180051cc5  mov     [rsp+370h+var_338], rdx
0x180051cca  mov     rdx, [rbp+270h+var_2C8]
0x180051cce  mov     rax, [rax+18h]
0x180051cd2  mov     [rsp+370h+var_340], rdx
0x180051cd7  mov     rdx, [rbp+270h+var_2B8]
0x180051cdb  mov     [rsp+370h+var_348], rdx
0x180051ce0  mov     rdx, [rbp+270h+var_2C0]
0x180051ce4  mov     [rsp+370h+ppv], rdx
0x180051ce9  mov     rdx, r13
0x180051cec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051cf1  mov     edi, eax
0x180051cf3  test    eax, eax
0x180051cf5  jns     short loc_180051D0C
0x180051cf7  mov     ebx, [rsp+370h+var_310]
0x180051cfb  xor     r15d, r15d
0x180051cfe  cmp     eax, 8011040Dh
0x180051d03  jz      short loc_180051D6A
0x180051d05  mov     edi, 80110407h
0x180051d0a  jmp     short loc_180051D6A
0x180051d0c  mov     rdx, [rsp+370h+var_300]; struct ICOMMSIGen *
0x180051d11  lea     r8, [rbp+270h+var_2E0]; struct CComExport::AppExportInfo *
0x180051d15  mov     r9, rsi; unsigned __int16 *
0x180051d18  mov     dword ptr [rsp+370h+ppv], r15d; unsigned int
0x180051d1d  call    ?AddApplicationToMSI@CComExport@@IEAAJPEAUICOMMSIGen@@PEAUAppExportInfo@1@PEBGK@Z; CComExport::AddApplicationToMSI(ICOMMSIGen *,CComExport::AppExportInfo *,ushort const *,ulong)
0x180051d22  mov     edi, eax
0x180051d24  test    eax, eax
0x180051d26  js      short loc_180051D67
0x180051d28  mov     rcx, [rsp+370h+var_300]
0x180051d2d  mov     rax, [rcx]
0x180051d30  mov     rax, [rax+48h]
0x180051d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d39  test    eax, eax
0x180051d3b  jns     short loc_180051D44
0x180051d3d  mov     edi, 80110407h
0x180051d42  jmp     short loc_180051D67
0x180051d44  mov     r8d, r15d; unsigned int
0x180051d47  mov     rdx, r13; unsigned __int16 *
0x180051d4a  call    ?CabMsiFile@CComExport@@IEAAJPEBGK@Z; CComExport::CabMsiFile(ushort const *,ulong)
0x180051d4f  mov     edi, 80110407h
0x180051d54  xor     r15d, r15d
0x180051d57  test    eax, eax
0x180051d59  cmovnz  eax, edi
0x180051d5c  mov     edi, eax
0x180051d5e  jmp     short loc_180051D6A
0x180051d60  mov     ebx, [rsp+370h+var_310]
0x180051d64  mov     r14d, ebx
0x180051d67  xor     r15d, r15d
0x180051d6a  mov     rcx, [rsp+370h+var_308]
0x180051d6f  test    rcx, rcx
0x180051d72  jz      short loc_180051D80
0x180051d74  mov     rax, [rcx]
0x180051d77  mov     rax, [rax+10h]
0x180051d7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d80  lea     rcx, [rbp+270h+var_2E0]; struct CComExport::AppExportInfo *
0x180051d84  call    ?FreeAppInfo@CComExport@@KAXPEAUAppExportInfo@1@@Z; CComExport::FreeAppInfo(CComExport::AppExportInfo *)
0x180051d89  test    edi, edi
0x180051d8b  jns     short loc_180051DB0
0x180051d8d  mov     rcx, [rsp+370h+var_300]
0x180051d92  test    rcx, rcx
0x180051d95  jz      short loc_180051DB0
0x180051d97  mov     rax, [rcx]
0x180051d9a  mov     rax, [rax+48h]
0x180051d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051da3  test    ebx, ebx
0x180051da5  jz      short loc_180051DB0
0x180051da7  mov     rcx, r13; lpFileName
0x180051daa  call    cs:__imp_DeleteFileW
0x180051db0  lea     rcx, [rbp+270h+Buffer]; lpFileName
0x180051db4  call    cs:__imp_DeleteFileW
0x180051dba  test    r14d, r14d
0x180051dbd  jz      short loc_180051DC5
0x180051dbf  call    cs:__imp_CoRevertToSelf
0x180051dc5  test    rsi, rsi
0x180051dc8  jz      short loc_180051DDF
0x180051dca  test    r12, r12
0x180051dcd  jz      short loc_180051DD6
0x180051dcf  cmp     [r12], r15w
0x180051dd4  jnz     short loc_180051DDF
0x180051dd6  mov     rcx, rsi; pv
0x180051dd9  call    cs:__imp_CoTaskMemFree
0x180051ddf  mov     rcx, [rsp+370h+var_300]
0x180051de4  test    rcx, rcx
0x180051de7  jz      short loc_180051DF5
0x180051de9  mov     rax, [rcx]
0x180051dec  mov     rax, [rax+10h]
0x180051df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051df5  mov     rcx, [rbp+270h+lpsz]; pv
0x180051df9  test    rcx, rcx
0x180051dfc  jz      short loc_180051E04
0x180051dfe  call    cs:__imp_CoTaskMemFree
0x180051e04  mov     eax, edi
0x180051e06  mov     rcx, [rbp+270h+var_50]
0x180051e0d  xor     rcx, rsp; StackCookie
0x180051e10  call    __security_check_cookie
0x180051e15  add     rsp, 338h
0x180051e1c  pop     r15
0x180051e1e  pop     r14
0x180051e20  pop     r13
0x180051e22  pop     r12
0x180051e24  pop     rdi
0x180051e25  pop     rsi
0x180051e26  pop     rbx
0x180051e27  pop     rbp
0x180051e28  retn
```
