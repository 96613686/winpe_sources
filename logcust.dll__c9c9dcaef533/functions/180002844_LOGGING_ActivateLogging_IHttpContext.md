# LOGGING::ActivateLogging(IHttpContext *)

- ea: `0x180002844`
- end: `0x180002df5`
- name: `?ActivateLogging@LOGGING@@QEAAJPEAVIHttpContext@@@Z`
- size: `1457`
- prototype: `__int64 __fastcall(LOGGING *__hidden this, struct IHttpContext *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002378`

## callees

- `0x180002844`
- `0x1800031d4`
- `0x1800037a2`
- `0x1800037d0`
- `0x180004010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180002af1`
- `msvcrt!_wcsicmp` at `0x180002b0a`
- `msvcrt!_wcsicmp` at `0x180002b23`
- `msvcrt!_wcsicmp` at `0x180002af1`
- `msvcrt!_wcsicmp` at `0x180002b0a`
- `msvcrt!_wcsicmp` at `0x180002b23`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180002b40`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180002b40`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002c76`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180002c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d99`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002d99`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002aaa`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180002aaa`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a15`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002c29`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002a15`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180002c29`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800028b5`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x1800028b5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002a5f`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002a5f`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002a8b`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180002a8b`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002a71`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002a71`
- `iisutil!PuDbgPrint` at `0x180002b89`
- `iisutil!PuDbgPrint` at `0x180002b89`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002d5b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002d8f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002d5b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002d8f`
- `iisutil!?RecalcLen@MULTISZA@@QEAAXXZ` at `0x180002de7`
- `iisutil!?RecalcLen@MULTISZA@@QEAAXXZ` at `0x180002de7`

## string_xrefs

- `0x180002a33`: `customLogPluginClsid`
- `0x180002b7d`: `Could not convert string %S to CLSID\n`
- `0x180002b6b`: `servercommon\inetsrv\iis\iisrearc\iis70\custom_logging\logging.cxx`

## pseudocode

```c
__int64 __fastcall LOGGING::ActivateLogging(LOGGING *this, struct IHttpContext *a2)
{
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64 *); // rax
  int v5; // ebx
  unsigned int (__fastcall ***v6)(_QWORD); // rax
  __int64 v7; // rdi
  __int64 v8; // rax
  int v10; // eax
  __int64 v11; // rcx
  _QWORD *v12; // r14
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, char *, char *, __int64); // rbx
  __int64 v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  signed int LastError; // eax
  __int64 v19; // rcx
  __int64 v20; // r8
  unsigned int v21; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+58h] [rbp-A8h] BYREF
  const unsigned __int16 *v27; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID ppv; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[32]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t *String1; // [rsp+90h] [rbp-70h]
  CLSID pclsid; // [rsp+A8h] [rbp-58h] BYREF
  char v32[32]; // [rsp+B8h] [rbp-48h] BYREF
  char v33[40]; // [rsp+D8h] [rbp-28h] BYREF
  unsigned __int16 v34[64]; // [rsp+100h] [rbp+0h] BYREF

  v23 = 0;
  v25 = 0;
  v22 = 0;
  v24 = 0;
  v26 = 0;
  v27 = 0;
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v29, v34, 0x40u);
  v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
  v5 = (**v4)(v4, &IID_INativeConfigurationSystem, &v23);
  if ( v5 < 0 )
    goto LABEL_21;
  v5 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v23 + 56LL))(v23, &v25);
  if ( v5 < 0 )
    goto LABEL_21;
  v6 = (unsigned int (__fastcall ***)(_QWORD))(**(__int64 (__fastcall ***)(struct IHttpContext *))a2)(a2);
  v7 = (**v6)(v6);
  v5 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *, _QWORD))(*(_QWORD *)v25 + 32LL))(v25, v7, &v24, 0);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v25 = 0;
  if ( v5 < 0 )
    goto LABEL_21;
  v5 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 **))(*(_QWORD *)v24 + 32LL))(v24, L"logFile", &v22);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  v24 = 0;
  if ( v5 < 0 )
    goto LABEL_21;
  v5 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, int *, _QWORD, _QWORD))(*v22 + 48))(
         v22,
         L"logFormat",
         &v26,
         0,
         0);
  if ( v5 < 0 )
    goto LABEL_21;
  v8 = *v22;
  if ( v26 != 3 )
  {
    (*(void (**)(void))(v8 + 16))();
    v22 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v23 = 0;
    STRU::~STRU((STRU *)v29);
    return 0;
  }
  v5 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(v8 + 64))(
         v22,
         L"customLogPluginClsid",
         &v27,
         0,
         0);
  if ( v5 < 0 )
    goto LABEL_21;
  if ( *v27 == 123 )
  {
    v10 = STRU::Copy((STRU *)v29, v27);
  }
  else
  {
    v5 = STRU::Copy((STRU *)v29, L"{", 1u);
    if ( v5 < 0 )
      goto LABEL_21;
    v5 = STRU::Append((STRU *)v29, v27);
    if ( v5 < 0 )
      goto LABEL_21;
    v10 = STRU::Append((STRU *)v29, L"}", 1u);
  }
  v5 = v10;
  if ( v10 < 0 )
    goto LABEL_21;
  (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
  v22 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  v23 = 0;
  if ( !_wcsicmp(String1, L"{FF16065F-DE82-11CF-BC0A-00AA006111E0}")
    || !_wcsicmp(String1, L"{FF160657-DE82-11CF-BC0A-00AA006111E0}")
    || !_wcsicmp(String1, L"{FF160663-DE82-11CF-BC0A-00AA006111E0}") )
  {
    goto LABEL_47;
  }
  pclsid = 0;
  v5 = CLSIDFromString(String1, &pclsid);
  if ( v5 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\custom_logging\\logging.cxx",
        146,
        "LOGGING::ActivateLogging",
        "Could not convert string %S to CLSID\n",
        String1);
    goto LABEL_21;
  }
  ppv = 0;
  v5 = CoCreateInstance(&pclsid, 0, 1u, &GUID_00000000_0000_0000_c000_000000000046, &ppv);
  if ( v5 >= 0 )
  {
    v12 = (_QWORD *)((char *)this + 16);
    v5 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, char *))ppv)(ppv, &IID_ILogPlugin, (char *)this + 16);
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    if ( v5 >= 0 )
    {
      v5 = StringCchPrintfA(v32, 0x20u, "/LM/W3SVC/%u", v7);
      if ( v5 >= 0 )
      {
        v5 = StringCchPrintfA(v33, 0x20u, "W3SVC%u", v7);
        if ( v5 >= 0 )
        {
          v13 = *v12;
          v14 = *(__int64 (__fastcall **)(__int64, char *, char *, __int64))(*(_QWORD *)*v12 + 24LL);
          v15 = (*(__int64 (__fastcall **)(struct IHttpServer *))(*(_QWORD *)g_pGlobalInfo + 56LL))(g_pGlobalInfo);
          v5 = v14(v13, v33, v32, v15);
          if ( v5 < 0 )
          {
            (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v12 + 16LL))(*v12);
            *v12 = 0;
            goto LABEL_31;
          }
          if ( !BUFFER::Resize((LOGGING *)((char *)this + 24), 0x104u) )
          {
LABEL_41:
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
            if ( v5 >= 0 )
              goto LABEL_23;
            goto LABEL_21;
          }
          v16 = *v12;
          v17 = *((_QWORD *)this + 7);
          v21 = *((_DWORD *)this + 16);
          if ( (*(int (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v16 + 64LL))(v16, &v21, v17) >= 0 )
            goto LABEL_46;
          if ( !BUFFER::Resize((LOGGING *)((char *)this + 24), v21) )
            goto LABEL_41;
          v19 = *v12;
          v20 = *((_QWORD *)this + 7);
          v21 = *((_DWORD *)this + 16);
          v5 = (*(__int64 (__fastcall **)(__int64, unsigned int *, __int64))(*(_QWORD *)v19 + 64LL))(v19, &v21, v20);
          if ( v5 >= 0 )
          {
LABEL_46:
            MULTISZA::RecalcLen((LOGGING *)((char *)this + 24));
LABEL_47:
            v5 = 0;
            goto LABEL_31;
          }
        }
      }
LABEL_21:
      v11 = *((_QWORD *)this + 2);
      if ( v11 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 32LL))(v11);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
        *((_QWORD *)this + 2) = 0;
      }
LABEL_23:
      if ( v24 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        v24 = 0;
      }
      if ( v22 )
      {
        (*(void (__fastcall **)(__int64 *))(*v22 + 16))(v22);
        v22 = 0;
      }
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v25 = 0;
      }
      if ( v23 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
        v23 = 0;
      }
    }
  }
LABEL_31:
  STRU::~STRU((STRU *)v29);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002844  mov     [rsp-8+arg_10], rbx
0x180002849  push    rbp
0x18000284a  push    rsi
0x18000284b  push    rdi
0x18000284c  push    r14
0x18000284e  push    r15
0x180002850  lea     rbp, [rsp-90h]
0x180002858  sub     rsp, 190h
0x18000285f  mov     rax, cs:__security_cookie
0x180002866  xor     rax, rsp
0x180002869  mov     [rbp+0B0h+var_30], rax
0x180002870  xor     r15d, r15d
0x180002873  mov     rdi, rdx
0x180002876  mov     rsi, rcx
0x180002879  mov     [rsp+1B0h+var_170], r15
0x18000287e  xor     edx, edx; Val
0x180002880  mov     [rsp+1B0h+var_160], r15
0x180002885  lea     rcx, [rbp+0B0h+var_B0]; void *
0x180002889  mov     [rsp+1B0h+var_178], r15
0x18000288e  mov     r8d, 80h; Size
0x180002894  mov     [rsp+1B0h+var_168], r15
0x180002899  mov     [rsp+1B0h+var_158], r15d
0x18000289e  mov     [rsp+1B0h+var_150], r15
0x1800028a3  call    memset_0
0x1800028a8  lea     r8d, [r15+40h]
0x1800028ac  lea     rdx, [rbp+0B0h+var_B0]
0x1800028b0  lea     rcx, [rsp+1B0h+var_140]
0x1800028b5  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x1800028bb  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x1800028c2  mov     rax, [rcx]
0x1800028c5  mov     rax, [rax+38h]
0x1800028c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028ce  mov     r9, rax
0x1800028d1  lea     r8, [rsp+1B0h+var_170]
0x1800028d6  lea     rdx, IID_INativeConfigurationSystem
0x1800028dd  mov     rcx, [rax]
0x1800028e0  mov     rax, [rcx]
0x1800028e3  mov     rcx, r9
0x1800028e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028eb  mov     ebx, eax
0x1800028ed  test    eax, eax
0x1800028ef  js      loc_180002B8F
0x1800028f5  mov     rcx, [rsp+1B0h+var_170]
0x1800028fa  lea     rdx, [rsp+1B0h+var_160]
0x1800028ff  mov     rax, [rcx]
0x180002902  mov     rax, [rax+38h]
0x180002906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000290b  mov     ebx, eax
0x18000290d  test    eax, eax
0x18000290f  js      loc_180002B8F
0x180002915  mov     rax, [rdi]
0x180002918  mov     rcx, rdi
0x18000291b  mov     rax, [rax]
0x18000291e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002923  mov     rdx, rax
0x180002926  mov     rcx, [rax]
0x180002929  mov     rax, [rcx]
0x18000292c  mov     rcx, rdx
0x18000292f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002934  mov     rcx, [rsp+1B0h+var_160]
0x180002939  lea     r8, [rsp+1B0h+var_168]
0x18000293e  mov     edi, eax
0x180002940  xor     r9d, r9d
0x180002943  mov     rdx, [rcx]
0x180002946  mov     rax, [rdx+20h]
0x18000294a  mov     edx, edi
0x18000294c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002951  mov     rcx, [rsp+1B0h+var_160]
0x180002956  mov     ebx, eax
0x180002958  mov     rdx, [rcx]
0x18000295b  mov     rax, [rdx+10h]
0x18000295f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002964  mov     [rsp+1B0h+var_160], r15
0x180002969  test    ebx, ebx
0x18000296b  js      loc_180002B8F
0x180002971  mov     rcx, [rsp+1B0h+var_168]
0x180002976  lea     r8, [rsp+1B0h+var_178]
0x18000297b  lea     rdx, aLogfile; "logFile"
0x180002982  mov     rax, [rcx]
0x180002985  mov     rax, [rax+20h]
0x180002989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298e  mov     rcx, [rsp+1B0h+var_168]
0x180002993  mov     ebx, eax
0x180002995  mov     rax, [rcx]
0x180002998  mov     rax, [rax+10h]
0x18000299c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029a1  mov     [rsp+1B0h+var_168], r15
0x1800029a6  test    ebx, ebx
0x1800029a8  js      loc_180002B8F
0x1800029ae  mov     rcx, [rsp+1B0h+var_178]
0x1800029b3  lea     r8, [rsp+1B0h+var_158]
0x1800029b8  xor     r9d, r9d
0x1800029bb  mov     [rsp+1B0h+ppv], r15
0x1800029c0  lea     rdx, aLogformat; "logFormat"
0x1800029c7  mov     rax, [rcx]
0x1800029ca  mov     rax, [rax+30h]
0x1800029ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029d3  mov     ebx, eax
0x1800029d5  test    eax, eax
0x1800029d7  js      loc_180002B8F
0x1800029dd  cmp     [rsp+1B0h+var_158], 3
0x1800029e2  mov     rcx, [rsp+1B0h+var_178]
0x1800029e7  mov     rax, [rcx]
0x1800029ea  jz      short loc_180002A22
0x1800029ec  mov     rax, [rax+10h]
0x1800029f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029f5  mov     rcx, [rsp+1B0h+var_170]
0x1800029fa  mov     [rsp+1B0h+var_178], r15
0x1800029ff  mov     rax, [rcx]
0x180002a02  mov     rax, [rax+10h]
0x180002a06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a0b  lea     rcx, [rsp+1B0h+var_140]
0x180002a10  mov     [rsp+1B0h+var_170], r15
0x180002a15  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002a1b  xor     eax, eax
0x180002a1d  jmp     loc_180002C31
0x180002a22  mov     rax, [rax+40h]
0x180002a26  lea     r8, [rsp+1B0h+var_150]
0x180002a2b  xor     r9d, r9d
0x180002a2e  mov     [rsp+1B0h+ppv], r15
0x180002a33  lea     rdx, aCustomlogplugi; "customLogPluginClsid"
0x180002a3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a3f  mov     ebx, eax
0x180002a41  test    eax, eax
0x180002a43  js      loc_180002B8F
0x180002a49  mov     rdx, [rsp+1B0h+var_150]
0x180002a4e  lea     rcx, [rsp+1B0h+var_140]
0x180002a53  mov     r14d, 1
0x180002a59  cmp     word ptr [rdx], 7Bh ; '{'
0x180002a5d  jnz     short loc_180002A67
0x180002a5f  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002a65  jmp     short loc_180002AB0
0x180002a67  mov     r8d, r14d
0x180002a6a  lea     rdx, asc_180005D74; "{"
0x180002a71  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180002a77  mov     ebx, eax
0x180002a79  test    eax, eax
0x180002a7b  js      loc_180002B8F
0x180002a81  mov     rdx, [rsp+1B0h+var_150]
0x180002a86  lea     rcx, [rsp+1B0h+var_140]
0x180002a8b  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180002a91  mov     ebx, eax
0x180002a93  test    eax, eax
0x180002a95  js      loc_180002B8F
0x180002a9b  mov     r8d, r14d
0x180002a9e  lea     rdx, asc_180005D78; "}"
0x180002aa5  lea     rcx, [rsp+1B0h+var_140]
0x180002aaa  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180002ab0  mov     ebx, eax
0x180002ab2  test    eax, eax
0x180002ab4  js      loc_180002B8F
0x180002aba  mov     rcx, [rsp+1B0h+var_178]
0x180002abf  mov     rax, [rcx]
0x180002ac2  mov     rax, [rax+10h]
0x180002ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002acb  mov     rcx, [rsp+1B0h+var_170]
0x180002ad0  mov     [rsp+1B0h+var_178], r15
0x180002ad5  mov     rax, [rcx]
0x180002ad8  mov     rax, [rax+10h]
0x180002adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ae1  mov     rcx, [rbp+0B0h+String1]; String1
0x180002ae5  lea     rdx, aFf16065fDe8211; "{FF16065F-DE82-11CF-BC0A-00AA006111E0}"
0x180002aec  mov     [rsp+1B0h+var_170], r15
0x180002af1  call    cs:__imp__wcsicmp
0x180002af7  test    eax, eax
0x180002af9  jz      loc_180002DED
0x180002aff  mov     rcx, [rbp+0B0h+String1]; String1
0x180002b03  lea     rdx, aFf160657De8211; "{FF160657-DE82-11CF-BC0A-00AA006111E0}"
0x180002b0a  call    cs:__imp__wcsicmp
0x180002b10  test    eax, eax
0x180002b12  jz      loc_180002DED
0x180002b18  mov     rcx, [rbp+0B0h+String1]; String1
0x180002b1c  lea     rdx, aFf160663De8211; "{FF160663-DE82-11CF-BC0A-00AA006111E0}"
0x180002b23  call    cs:__imp__wcsicmp
0x180002b29  test    eax, eax
0x180002b2b  jz      loc_180002DED
0x180002b31  mov     rcx, [rbp+0B0h+String1]; lpsz
0x180002b35  lea     rdx, [rbp+0B0h+pclsid]; pclsid
0x180002b39  xorps   xmm0, xmm0
0x180002b3c  movups  xmmword ptr [rbp+0B0h+pclsid.Data1], xmm0
0x180002b40  call    cs:__imp_CLSIDFromString
0x180002b46  mov     ebx, eax
0x180002b48  test    eax, eax
0x180002b4a  jns     loc_180002C57
0x180002b50  test    cs:g_dwDebugFlags, 3
0x180002b57  jz      short loc_180002B8F
0x180002b59  mov     rax, [rbp+0B0h+String1]
0x180002b5d  lea     r9, aLoggingActivat; "LOGGING::ActivateLogging"
0x180002b64  mov     rcx, cs:g_pDebug
0x180002b6b  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180002b72  mov     [rsp+1B0h+var_188], rax
0x180002b77  mov     r8d, 92h
0x180002b7d  lea     rax, aCouldNotConver; "Could not convert string %S to CLSID\n"
0x180002b84  mov     [rsp+1B0h+ppv], rax
0x180002b89  call    cs:__imp_PuDbgPrint
0x180002b8f  mov     rcx, [rsi+10h]
0x180002b93  test    rcx, rcx
0x180002b96  jz      short loc_180002BB8
0x180002b98  mov     rax, [rcx]
0x180002b9b  mov     rax, [rax+20h]
0x180002b9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ba4  mov     rcx, [rsi+10h]
0x180002ba8  mov     rax, [rcx]
0x180002bab  mov     rax, [rax+10h]
0x180002baf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bb4  mov     [rsi+10h], r15
0x180002bb8  mov     rcx, [rsp+1B0h+var_168]
0x180002bbd  test    rcx, rcx
0x180002bc0  jz      short loc_180002BD3
0x180002bc2  mov     rax, [rcx]
0x180002bc5  mov     rax, [rax+10h]
0x180002bc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bce  mov     [rsp+1B0h+var_168], r15
0x180002bd3  mov     rcx, [rsp+1B0h+var_178]
0x180002bd8  test    rcx, rcx
0x180002bdb  jz      short loc_180002BEE
0x180002bdd  mov     rax, [rcx]
0x180002be0  mov     rax, [rax+10h]
0x180002be4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002be9  mov     [rsp+1B0h+var_178], r15
0x180002bee  mov     rcx, [rsp+1B0h+var_160]
0x180002bf3  test    rcx, rcx
0x180002bf6  jz      short loc_180002C09
0x180002bf8  mov     rax, [rcx]
0x180002bfb  mov     rax, [rax+10h]
0x180002bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c04  mov     [rsp+1B0h+var_160], r15
0x180002c09  mov     rcx, [rsp+1B0h+var_170]
0x180002c0e  test    rcx, rcx
0x180002c11  jz      short loc_180002C24
0x180002c13  mov     rax, [rcx]
0x180002c16  mov     rax, [rax+10h]
0x180002c1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c1f  mov     [rsp+1B0h+var_170], r15
0x180002c24  lea     rcx, [rsp+1B0h+var_140]
0x180002c29  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180002c2f  mov     eax, ebx
0x180002c31  mov     rcx, [rbp+0B0h+var_30]
0x180002c38  xor     rcx, rsp; StackCookie
0x180002c3b  call    __security_check_cookie
0x180002c40  mov     rbx, [rsp+1B0h+arg_10]
0x180002c48  add     rsp, 190h
0x180002c4f  pop     r15
0x180002c51  pop     r14
0x180002c53  pop     rdi
0x180002c54  pop     rsi
0x180002c55  pop     rbp
0x180002c56  retn
0x180002c57  lea     rax, [rsp+1B0h+var_148]
0x180002c5c  mov     [rsp+1B0h+var_148], r15
0x180002c61  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x180002c68  mov     [rsp+1B0h+ppv], rax; ppv
0x180002c6d  mov     r8d, r14d; dwClsContext
0x180002c70  lea     rcx, [rbp+0B0h+pclsid]; rclsid
0x180002c74  xor     edx, edx; pUnkOuter
0x180002c76  call    cs:__imp_CoCreateInstance
0x180002c7c  mov     ebx, eax
0x180002c7e  test    eax, eax
0x180002c80  js      short loc_180002C24
0x180002c82  mov     rcx, [rsp+1B0h+var_148]
0x180002c87  lea     r14, [rsi+10h]
0x180002c8b  mov     r8, r14
0x180002c8e  lea     rdx, IID_ILogPlugin
0x180002c95  mov     rax, [rcx]
0x180002c98  mov     rax, [rax]
0x180002c9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ca0  mov     rcx, [rsp+1B0h+var_148]
0x180002ca5  mov     ebx, eax
0x180002ca7  mov     rdx, [rcx]
0x180002caa  mov     rax, [rdx+10h]
0x180002cae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002cb3  test    ebx, ebx
0x180002cb5  js      loc_180002C24
0x180002cbb  mov     r9d, edi
0x180002cbe  lea     r8, aLmW3svcU; "/LM/W3SVC/%u"
0x180002cc5  mov     edx, 20h ; ' '; unsigned __int64
0x180002cca  lea     rcx, [rbp+0B0h+var_F8]; char *
0x180002cce  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180002cd3  mov     ebx, eax
0x180002cd5  test    eax, eax
0x180002cd7  js      loc_180002B8F
0x180002cdd  mov     r9d, edi
0x180002ce0  lea     r8, aW3svcU; "W3SVC%u"
0x180002ce7  mov     edx, 20h ; ' '; unsigned __int64
0x180002cec  lea     rcx, [rbp+0B0h+var_D8]; char *
0x180002cf0  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180002cf5  mov     ebx, eax
0x180002cf7  test    eax, eax
0x180002cf9  js      loc_180002B8F
0x180002cff  mov     rdi, [r14]
0x180002d02  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180002d09  mov     rax, [rdi]
0x180002d0c  mov     rdx, [rcx]
0x180002d0f  mov     rbx, [rax+18h]
0x180002d13  mov     rax, [rdx+38h]
0x180002d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002d1c  mov     r9, rax
0x180002d1f  lea     r8, [rbp+0B0h+var_F8]
0x180002d23  mov     rax, rbx
0x180002d26  lea     rdx, [rbp+0B0h+var_D8]
  ... truncated ...
```
