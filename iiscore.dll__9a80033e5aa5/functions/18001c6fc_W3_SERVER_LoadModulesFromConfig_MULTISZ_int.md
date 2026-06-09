# W3_SERVER::LoadModulesFromConfig(MULTISZ *,int)

- ea: `0x18001c6fc`
- end: `0x18001cce4`
- name: `?LoadModulesFromConfig@W3_SERVER@@QEAAJPEAVMULTISZ@@H@Z`
- size: `1512`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, struct MULTISZ *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001baac`
- `0x18001c344`

## callees

- `0x1800128b0`
- `0x180017b2c`
- `0x180018108`
- `0x180019094`
- `0x180019558`
- `0x18001a2e0`
- `0x18001ad58`
- `0x18001add8`
- `0x18001ae20`
- `0x18001af30`
- `0x18001c6fc`
- `0x18002d0d4`
- `0x1800343f0`
- `0x180035010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18001c827`
- `msvcrt!_ultow_s` at `0x18001c827`
- `iisutil!PuDbgPrint` at `0x18001ccb1`
- `iisutil!PuDbgPrint` at `0x18001ccb1`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001c853`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001c8e4`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001cb14`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001cbac`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001c853`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001c8e4`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001cb14`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001cbac`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001c9a6`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001c9bb`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001c9d0`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001c9a6`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001c9bb`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001c9d0`
- `iisutil!PuDbgPrintError` at `0x18001cb64`
- `iisutil!PuDbgPrintError` at `0x18001cb64`

## string_xrefs

- `0x18001cb39`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`
- `0x18001ccaa`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`
- `0x18001cb54`: `Failed to call RegisterModule for dll=%S, mod=%S\n`
- `0x18001cb2b`: `W3_SERVER::LoadModulesFromConfig`
- `0x18001cc98`: `W3_SERVER::LoadModulesFromConfig`

## pseudocode

```c
__int64 __fastcall W3_SERVER::LoadModulesFromConfig(W3_SERVER *this, struct MULTISZ *a2, int a3)
{
  VIRTUAL_MODULE *v3; // rdi
  __int64 *v6; // rcx
  MODULE_DLL *v8; // r14
  __int64 v9; // rax
  int ModuleDll; // ebx
  __int64 v11; // rcx
  unsigned int v12; // ecx
  unsigned int v13; // eax
  unsigned int i; // r15d
  __int64 v15; // rax
  int v16; // eax
  VIRTUAL_MODULE *v17; // rax
  VIRTUAL_MODULE *v18; // rax
  __int64 v19; // rax
  unsigned int v20; // eax
  __int64 v22; // [rsp+40h] [rbp-79h] BYREF
  unsigned int v23; // [rsp+48h] [rbp-71h] BYREF
  __int128 v24; // [rsp+50h] [rbp-69h] BYREF
  __int64 *v25; // [rsp+60h] [rbp-59h] BYREF
  __int64 v26; // [rsp+68h] [rbp-51h] BYREF
  __int128 v27; // [rsp+70h] [rbp-49h] BYREF
  int v28; // [rsp+80h] [rbp-39h] BYREF
  __int64 v29; // [rsp+88h] [rbp-31h] BYREF
  const unsigned __int16 *v30; // [rsp+90h] [rbp-29h] BYREF
  __int128 v31; // [rsp+98h] [rbp-21h] BYREF
  __int128 v32; // [rsp+A8h] [rbp-11h] BYREF
  wchar_t Buffer[16]; // [rsp+B8h] [rbp-1h] BYREF

  v3 = 0;
  v26 = 0;
  v25 = 0;
  v6 = (__int64 *)*((_QWORD *)this + 187);
  v22 = 0;
  v24 = 0u;
  v8 = 0;
  v30 = 0;
  v23 = 0;
  v29 = 0;
  v28 = 0;
  v9 = *v6;
  *(_QWORD *)&v27 = 0;
  ModuleDll = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, const wchar_t *, __int64 *, __int64 *, _QWORD))(v9 + 24))(
                v6,
                L"system.webServer/globalModules",
                L"MACHINE/WEBROOT/APPHOST",
                &v26,
                &v29,
                0);
  if ( ModuleDll >= 0 )
  {
    ModuleDll = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v26 + 40LL))(v26, &v25);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
    if ( ModuleDll >= 0 )
    {
      ModuleDll = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v25 + 24))(v25, &v23);
      if ( ModuleDll >= 0 )
      {
        if ( a3 && !v23 )
          EVENT_LOG::LogEvent((W3_SERVER *)((char *)this + 28), 0x800008FA, 0, 0, 0);
        for ( i = 0; ; ++i )
        {
          v15 = *v25;
          if ( i >= v23 )
            break;
          ModuleDll = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v15 + 32))(v25, i, &v22);
          if ( ModuleDll < 0 )
            goto LABEL_47;
          ModuleDll = (*(__int64 (__fastcall **)(__int64, const wchar_t *, __int128 *, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
                        v22,
                        L"name",
                        &v24,
                        0,
                        0);
          if ( ModuleDll < 0 )
            goto LABEL_47;
          ModuleDll = (*(__int64 (__fastcall **)(__int64, const wchar_t *, char *, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
                        v22,
                        L"image",
                        (char *)&v24 + 8,
                        0,
                        0);
          if ( ModuleDll < 0 )
            goto LABEL_47;
          ModuleDll = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v22 + 64LL))(
                        v22,
                        L"preCondition",
                        &v30,
                        0,
                        0);
          if ( ModuleDll < 0 )
            goto LABEL_47;
          if ( !MULTISZ::Append(a2, (const unsigned __int16 *)v24)
            || !MULTISZ::Append(a2, *((const unsigned __int16 **)&v24 + 1))
            || !MULTISZ::Append(a2, v30) )
          {
            ModuleDll = -2147024888;
            goto LABEL_47;
          }
          v16 = (*(__int64 (__fastcall **)(W3_SERVER *, const unsigned __int16 *, int *))(*(_QWORD *)this + 176LL))(
                  this,
                  v30,
                  &v28);
          if ( v28 )
          {
            v31 = v24;
            *(_QWORD *)&v32 = v30;
            EVENT_LOG::LogEvent(
              (W3_SERVER *)((char *)this + 28),
              0xC00008F8,
              3u,
              (const unsigned __int16 **const)&v31,
              0);
            ModuleDll = -2147024883;
            goto LABEL_47;
          }
          if ( a3 && v16 )
          {
            ModuleDll = MODULE_DLL::GetModuleDll(*((const unsigned __int16 **)&v24 + 1), (struct MODULE_DLL **)&v27);
            if ( ModuleDll < 0 )
              goto LABEL_37;
            v17 = (VIRTUAL_MODULE *)operator new(0xB0u);
            if ( !v17 || (v18 = VIRTUAL_MODULE::VIRTUAL_MODULE(v17), (v3 = v18) == 0) )
            {
              ModuleDll = -2147024888;
LABEL_37:
              v8 = (MODULE_DLL *)v27;
              goto LABEL_43;
            }
            v8 = (MODULE_DLL *)v27;
            ModuleDll = VIRTUAL_MODULE::Create(v18, (const unsigned __int16 *)v24, (struct MODULE_DLL *)v27);
            if ( ModuleDll < 0 )
              goto LABEL_43;
            v19 = *((_QWORD *)v3 + 12);
            v8 = 0;
            *(_QWORD *)&v27 = 0;
            if ( !v19 )
            {
              ModuleDll = -2147024846;
LABEL_34:
              v27 = v24;
              v20 = WIN32_FROM_HRESULT(ModuleDll);
              EVENT_LOG::LogEvent(
                (W3_SERVER *)((char *)this + 28),
                0xC00008F5,
                2u,
                (const unsigned __int16 **const)&v27,
                v20);
              if ( (g_dwDebugFlags & 0xF) != 0 )
                PuDbgPrintError(
                  g_pDebug,
                  "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.cxx",
                  1379,
                  "W3_SERVER::LoadModulesFromConfig",
                  ModuleDll,
                  "Failed to call RegisterModule for dll=%S, mod=%S\n",
                  *((const wchar_t **)&v24 + 1),
                  (const wchar_t *)v24);
LABEL_46:
              VIRTUAL_MODULE::DereferenceVirtualModule(v3);
              goto LABEL_47;
            }
            ModuleDll = (*(__int64 (__fastcall **)(__int64, VIRTUAL_MODULE *, W3_SERVER *))(v19 + 48))(
                          655360,
                          v3,
                          g_pW3Server);
            if ( ModuleDll < 0 )
              goto LABEL_34;
            ModuleDll = MODULE_LIST::AppendModule((W3_SERVER *)((char *)this + 560), v3);
            if ( ModuleDll < 0 )
              goto LABEL_46;
            v3 = 0;
            v24 = 0u;
            v30 = 0;
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
          v22 = 0;
        }
        (*(void (**)(void))(v15 + 16))();
        v25 = 0;
        if ( !a3 )
          return 0;
        MODULE_LIST::Optimize((W3_SERVER *)((char *)this + 560));
        ModuleDll = NOTIFICATION_CONTEXT::GenerateCachedModuleList((W3_SERVER *)((char *)this + 560));
        if ( ModuleDll < 0 )
          goto LABEL_47;
        ModuleDll = W3_SERVER::GenerateCachedGlobalModuleList(this);
        if ( ModuleDll >= 0 )
          return 0;
LABEL_43:
        if ( v8 )
          MODULE_DLL::DereferenceModuleDll(v8);
        if ( v3 )
          goto LABEL_46;
      }
LABEL_47:
      if ( v22 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
        v22 = 0;
      }
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64 *))(*v25 + 16))(v25);
        v25 = 0;
      }
      if ( v26 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
        v26 = 0;
      }
      if ( a3 )
        MODULE_LIST::Optimize((W3_SERVER *)((char *)this + 560));
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\core\\w3server.cxx",
          1474,
          "W3_SERVER::LoadModulesFromConfig",
          "Failed processing with hr = %x\n",
          ModuleDll);
    }
  }
  else
  {
    v11 = *(_QWORD *)this;
    v31 = 0;
    LODWORD(v27) = 0;
    v32 = 0;
    *(_QWORD *)&v31 = (*(__int64 (__fastcall **)(W3_SERVER *))(v11 + 8))(this);
    if ( v29 )
    {
      (*(void (__fastcall **)(__int64, char *))(*(_QWORD *)v29 + 24LL))(v29, (char *)&v31 + 8);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v29 + 40LL))(v29, &v32);
      (*(void (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v29 + 32LL))(v29, &v27);
      v12 = v27;
    }
    else
    {
      v12 = 0;
      *((_QWORD *)&v31 + 1) = L"Unknown Error";
      *(_QWORD *)&v32 = L"Unknown File";
      LODWORD(v27) = 0;
    }
    _ultow_s(v12, Buffer, 0x10u, 10);
    *((_QWORD *)&v32 + 1) = Buffer;
    v13 = WIN32_FROM_HRESULT(ModuleDll);
    EVENT_LOG::LogEvent((W3_SERVER *)((char *)this + 28), 0xC00008F9, 4u, (const unsigned __int16 **const)&v31, v13);
    if ( v29 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  }
  return (unsigned int)ModuleDll;
}

```

## disassembly

```asm
0x18001c6fc  mov     [rsp-8+arg_10], rbx
0x18001c701  push    rbp
0x18001c702  push    rsi
0x18001c703  push    rdi
0x18001c704  push    r12
0x18001c706  push    r13
0x18001c708  push    r14
0x18001c70a  push    r15
0x18001c70c  lea     rbp, [rsp-27h]
0x18001c711  sub     rsp, 0E0h
0x18001c718  mov     rax, cs:__security_cookie
0x18001c71f  xor     rax, rsp
0x18001c722  mov     [rbp+57h+var_38], rax
0x18001c726  xor     edi, edi
0x18001c728  lea     r9, [rbp+57h+var_A8]
0x18001c72c  mov     r12, rdx
0x18001c72f  mov     [rbp+57h+var_A8], rdi
0x18001c733  mov     rsi, rcx
0x18001c736  mov     [rbp+57h+var_B0], rdi
0x18001c73a  mov     rcx, [rcx+5D8h]
0x18001c741  lea     rdx, [rbp+57h+var_88]
0x18001c745  mov     [rbp+57h+var_D0], rdi
0x18001c749  mov     r13d, r8d
0x18001c74c  mov     qword ptr [rbp+57h+var_C0], rdi
0x18001c750  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001c757  mov     qword ptr [rbp+57h+var_C0+8], rdi
0x18001c75b  mov     r14d, edi
0x18001c75e  mov     [rbp+57h+var_80], rdi
0x18001c762  mov     [rbp+57h+var_C8], edi
0x18001c765  mov     [rbp+57h+var_88], rdi
0x18001c769  mov     [rbp+57h+var_90], edi
0x18001c76c  mov     rax, [rcx]
0x18001c76f  mov     [rsp+110h+var_E8], rdi
0x18001c774  mov     [rsp+110h+var_F0], rdx
0x18001c779  lea     rdx, aSystemWebserve_1; "system.webServer/globalModules"
0x18001c780  mov     qword ptr [rbp+57h+var_A0], rdi
0x18001c784  mov     rax, [rax+18h]
0x18001c788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c78d  mov     ebx, eax
0x18001c78f  test    eax, eax
0x18001c791  jns     loc_18001C877
0x18001c797  mov     rcx, [rsi]
0x18001c79a  xorps   xmm0, xmm0
0x18001c79d  movups  [rbp+57h+var_78], xmm0
0x18001c7a1  mov     dword ptr [rbp+57h+var_A0], edi
0x18001c7a4  movups  [rbp+57h+var_68], xmm0
0x18001c7a8  mov     rax, [rcx+8]
0x18001c7ac  mov     rcx, rsi
0x18001c7af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7b4  mov     rcx, [rbp+57h+var_88]
0x18001c7b8  mov     qword ptr [rbp+57h+var_78], rax
0x18001c7bc  test    rcx, rcx
0x18001c7bf  jz      short loc_18001C7FE
0x18001c7c1  mov     rax, [rcx]
0x18001c7c4  lea     rdx, [rbp+57h+var_78+8]
0x18001c7c8  mov     rax, [rax+18h]
0x18001c7cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7d1  mov     rcx, [rbp+57h+var_88]
0x18001c7d5  lea     rdx, [rbp+57h+var_68]
0x18001c7d9  mov     rax, [rcx]
0x18001c7dc  mov     rax, [rax+28h]
0x18001c7e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7e5  mov     rcx, [rbp+57h+var_88]
0x18001c7e9  lea     rdx, [rbp+57h+var_A0]
0x18001c7ed  mov     rax, [rcx]
0x18001c7f0  mov     rax, [rax+20h]
0x18001c7f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c7f9  mov     ecx, dword ptr [rbp+57h+var_A0]
0x18001c7fc  jmp     short loc_18001C819
0x18001c7fe  lea     rax, aUnknownError; "Unknown Error"
0x18001c805  mov     ecx, edi; Value
0x18001c807  mov     qword ptr [rbp+57h+var_78+8], rax
0x18001c80b  lea     rax, aUnknownFile; "Unknown File"
0x18001c812  mov     qword ptr [rbp+57h+var_68], rax
0x18001c816  mov     dword ptr [rbp+57h+var_A0], ecx
0x18001c819  mov     r9d, 0Ah; Radix
0x18001c81f  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001c823  lea     r8d, [r9+6]; BufferCount
0x18001c827  call    cs:__imp__ultow_s
0x18001c82d  lea     rax, [rbp+57h+Buffer]
0x18001c831  mov     ecx, ebx; int
0x18001c833  mov     qword ptr [rbp+57h+var_68+8], rax
0x18001c837  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001c83c  lea     rcx, [rsi+1Ch]
0x18001c840  mov     dword ptr [rsp+110h+var_F0], eax
0x18001c844  mov     edx, 0C00008F9h
0x18001c849  lea     r9, [rbp+57h+var_78]
0x18001c84d  mov     r8d, 4
0x18001c853  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001c859  mov     rcx, [rbp+57h+var_88]
0x18001c85d  test    rcx, rcx
0x18001c860  jz      loc_18001CCB7
0x18001c866  mov     rax, [rcx]
0x18001c869  mov     rax, [rax+10h]
0x18001c86d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c872  jmp     loc_18001CCB7
0x18001c877  mov     rcx, [rbp+57h+var_A8]
0x18001c87b  lea     rdx, [rbp+57h+var_B0]
0x18001c87f  mov     rax, [rcx]
0x18001c882  mov     rax, [rax+28h]
0x18001c886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c88b  mov     rcx, [rbp+57h+var_A8]
0x18001c88f  mov     ebx, eax
0x18001c891  mov     rdx, [rcx]
0x18001c894  mov     rax, [rdx+10h]
0x18001c898  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c89d  mov     [rbp+57h+var_A8], rdi
0x18001c8a1  test    ebx, ebx
0x18001c8a3  js      loc_18001CCB7
0x18001c8a9  mov     rcx, [rbp+57h+var_B0]
0x18001c8ad  lea     rdx, [rbp+57h+var_C8]
0x18001c8b1  mov     rax, [rcx]
0x18001c8b4  mov     rax, [rax+18h]
0x18001c8b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c8bd  mov     ebx, eax
0x18001c8bf  test    eax, eax
0x18001c8c1  js      loc_18001CC21
0x18001c8c7  test    r13d, r13d
0x18001c8ca  jz      short loc_18001C8EA
0x18001c8cc  cmp     [rbp+57h+var_C8], edi
0x18001c8cf  jnz     short loc_18001C8EA
0x18001c8d1  xor     r8d, r8d
0x18001c8d4  mov     dword ptr [rsp+110h+var_F0], edi
0x18001c8d8  lea     rcx, [rsi+1Ch]
0x18001c8dc  xor     r9d, r9d
0x18001c8df  mov     edx, 800008FAh
0x18001c8e4  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001c8ea  mov     r15d, edi
0x18001c8ed  mov     rcx, [rbp+57h+var_B0]
0x18001c8f1  mov     rax, [rcx]
0x18001c8f4  cmp     r15d, [rbp+57h+var_C8]
0x18001c8f8  jnb     loc_18001CBC0
0x18001c8fe  mov     rax, [rax+20h]
0x18001c902  lea     r8, [rbp+57h+var_D0]
0x18001c906  mov     edx, r15d
0x18001c909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c90e  mov     ebx, eax
0x18001c910  test    eax, eax
0x18001c912  js      loc_18001CC21
0x18001c918  mov     rcx, [rbp+57h+var_D0]
0x18001c91c  lea     r8, [rbp+57h+var_C0]
0x18001c920  xor     r9d, r9d
0x18001c923  mov     [rsp+110h+var_F0], rdi
0x18001c928  lea     rdx, aName_0; "name"
0x18001c92f  mov     rax, [rcx]
0x18001c932  mov     rax, [rax+40h]
0x18001c936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c93b  mov     ebx, eax
0x18001c93d  test    eax, eax
0x18001c93f  js      loc_18001CC21
0x18001c945  mov     rcx, [rbp+57h+var_D0]
0x18001c949  lea     r8, [rbp+57h+var_C0+8]
0x18001c94d  xor     r9d, r9d
0x18001c950  mov     [rsp+110h+var_F0], rdi
0x18001c955  lea     rdx, aImage; "image"
0x18001c95c  mov     rax, [rcx]
0x18001c95f  mov     rax, [rax+40h]
0x18001c963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c968  mov     ebx, eax
0x18001c96a  test    eax, eax
0x18001c96c  js      loc_18001CC21
0x18001c972  mov     rcx, [rbp+57h+var_D0]
0x18001c976  lea     r8, [rbp+57h+var_80]
0x18001c97a  xor     r9d, r9d
0x18001c97d  mov     [rsp+110h+var_F0], rdi
0x18001c982  lea     rdx, aPrecondition; "preCondition"
0x18001c989  mov     rax, [rcx]
0x18001c98c  mov     rax, [rax+40h]
0x18001c990  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c995  mov     ebx, eax
0x18001c997  test    eax, eax
0x18001c999  js      loc_18001CC21
0x18001c99f  mov     rdx, qword ptr [rbp+57h+var_C0]
0x18001c9a3  mov     rcx, r12
0x18001c9a6  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001c9ac  test    eax, eax
0x18001c9ae  jz      loc_18001CBB9
0x18001c9b4  mov     rdx, qword ptr [rbp+57h+var_C0+8]
0x18001c9b8  mov     rcx, r12
0x18001c9bb  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001c9c1  test    eax, eax
0x18001c9c3  jz      loc_18001CBB9
0x18001c9c9  mov     rdx, [rbp+57h+var_80]
0x18001c9cd  mov     rcx, r12
0x18001c9d0  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001c9d6  test    eax, eax
0x18001c9d8  jz      loc_18001CBB9
0x18001c9de  mov     rax, [rsi]
0x18001c9e1  lea     r8, [rbp+57h+var_90]
0x18001c9e5  mov     rdx, [rbp+57h+var_80]
0x18001c9e9  mov     rcx, rsi
0x18001c9ec  mov     rax, [rax+0B0h]
0x18001c9f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c9f8  cmp     [rbp+57h+var_90], edi
0x18001c9fb  jnz     loc_18001CB7D
0x18001ca01  test    r13d, r13d
0x18001ca04  jz      loc_18001CAC2
0x18001ca0a  test    eax, eax
0x18001ca0c  jz      loc_18001CAC2
0x18001ca12  mov     rcx, qword ptr [rbp+57h+var_C0+8]; unsigned __int16 *
0x18001ca16  lea     rdx, [rbp+57h+var_A0]; struct MODULE_DLL **
0x18001ca1a  call    ?GetModuleDll@MODULE_DLL@@SAJPEBGPEAPEAV1@@Z; MODULE_DLL::GetModuleDll(ushort const *,MODULE_DLL * *)
0x18001ca1f  mov     ebx, eax
0x18001ca21  test    eax, eax
0x18001ca23  js      loc_18001CB74
0x18001ca29  mov     ecx, 0B0h; Size
0x18001ca2e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ca33  test    rax, rax
0x18001ca36  jz      loc_18001CB6F
0x18001ca3c  mov     rcx, rax; this
0x18001ca3f  call    ??0VIRTUAL_MODULE@@QEAA@XZ; VIRTUAL_MODULE::VIRTUAL_MODULE(void)
0x18001ca44  mov     rdi, rax
0x18001ca47  test    rax, rax
0x18001ca4a  jz      loc_18001CB6F
0x18001ca50  mov     r14, qword ptr [rbp+57h+var_A0]
0x18001ca54  mov     rcx, rax; this
0x18001ca57  mov     rdx, qword ptr [rbp+57h+var_C0]; unsigned __int16 *
0x18001ca5b  mov     r8, r14; struct MODULE_DLL *
0x18001ca5e  call    ?Create@VIRTUAL_MODULE@@QEAAJPEBGPEAVMODULE_DLL@@@Z; VIRTUAL_MODULE::Create(ushort const *,MODULE_DLL *)
0x18001ca63  mov     ebx, eax
0x18001ca65  test    eax, eax
0x18001ca67  js      loc_18001CC05
0x18001ca6d  mov     rax, [rdi+60h]
0x18001ca71  xor     r14d, r14d
0x18001ca74  mov     qword ptr [rbp+57h+var_A0], r14
0x18001ca78  test    rax, rax
0x18001ca7b  jz      short loc_18001CADE
0x18001ca7d  mov     r8, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001ca84  mov     rdx, rdi
0x18001ca87  mov     rax, [rax+30h]
0x18001ca8b  mov     ecx, 0A0000h
0x18001ca90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ca95  mov     ebx, eax
0x18001ca97  test    eax, eax
0x18001ca99  js      short loc_18001CAE3
0x18001ca9b  lea     rcx, [rsi+230h]; this
0x18001caa2  mov     rdx, rdi; struct VIRTUAL_MODULE *
0x18001caa5  call    ?AppendModule@MODULE_LIST@@QEAAJPEAVVIRTUAL_MODULE@@@Z; MODULE_LIST::AppendModule(VIRTUAL_MODULE *)
0x18001caaa  mov     ebx, eax
0x18001caac  test    eax, eax
0x18001caae  js      loc_18001CC17
0x18001cab4  xor     edi, edi
0x18001cab6  mov     qword ptr [rbp+57h+var_C0+8], rdi
0x18001caba  mov     qword ptr [rbp+57h+var_C0], rdi
0x18001cabe  mov     [rbp+57h+var_80], rdi
0x18001cac2  mov     rcx, [rbp+57h+var_D0]
0x18001cac6  mov     rax, [rcx]
0x18001cac9  mov     rax, [rax+10h]
0x18001cacd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cad2  inc     r15d
0x18001cad5  mov     [rbp+57h+var_D0], rdi
0x18001cad9  jmp     loc_18001C8ED
0x18001cade  mov     ebx, 80070032h
0x18001cae3  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001cae7  mov     ecx, ebx; int
0x18001cae9  mov     qword ptr [rbp+57h+var_A0], rax
0x18001caed  mov     r14d, ebx
0x18001caf0  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18001caf4  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18001caf8  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001cafd  lea     rcx, [rsi+1Ch]
0x18001cb01  mov     dword ptr [rsp+110h+var_F0], eax
0x18001cb05  mov     edx, 0C00008F5h
0x18001cb0a  lea     r9, [rbp+57h+var_A0]
0x18001cb0e  mov     r8d, 2
0x18001cb14  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001cb1a  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001cb21  jz      loc_18001CC17
0x18001cb27  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001cb2b  lea     r9, aW3ServerLoadmo; "W3_SERVER::LoadModulesFromConfig"
0x18001cb32  mov     rcx, cs:g_pDebug
0x18001cb39  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001cb40  mov     [rsp+110h+var_D8], rax
0x18001cb45  mov     r8d, 563h
0x18001cb4b  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18001cb4f  mov     [rsp+110h+var_E0], rax
0x18001cb54  lea     rax, aFailedToCallRe; "Failed to call RegisterModule for dll=%"...
0x18001cb5b  mov     [rsp+110h+var_E8], rax
0x18001cb60  mov     dword ptr [rsp+110h+var_F0], ebx
0x18001cb64  call    cs:__imp_PuDbgPrintError
0x18001cb6a  jmp     loc_18001CC17
0x18001cb6f  mov     ebx, 80070008h
0x18001cb74  mov     r14, qword ptr [rbp+57h+var_A0]
0x18001cb78  jmp     loc_18001CC05
0x18001cb7d  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001cb81  lea     rcx, [rsi+1Ch]
0x18001cb85  mov     qword ptr [rbp+57h+var_78], rax
0x18001cb89  lea     r9, [rbp+57h+var_78]
0x18001cb8d  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18001cb91  mov     r8d, 3
0x18001cb97  mov     qword ptr [rbp+57h+var_78+8], rax
0x18001cb9b  mov     edx, 0C00008F8h
0x18001cba0  mov     rax, [rbp+57h+var_80]
0x18001cba4  mov     qword ptr [rbp+57h+var_68], rax
0x18001cba8  mov     dword ptr [rsp+110h+var_F0], edi
0x18001cbac  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001cbb2  mov     ebx, 8007000Dh
0x18001cbb7  jmp     short loc_18001CC21
0x18001cbb9  mov     ebx, 80070008h
0x18001cbbe  jmp     short loc_18001CC21
  ... truncated ...
```
