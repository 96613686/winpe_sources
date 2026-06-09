# W3_SERVER::LoadModulesFromConfig(MULTISZ *,int)

- ea: `0x18001e020`
- end: `0x18001e645`
- name: `?LoadModulesFromConfig@W3_SERVER@@QEAAJPEAVMULTISZ@@H@Z`
- size: `1573`
- prototype: `__int64 __fastcall(W3_SERVER *__hidden this, struct MULTISZ *, int)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d2ec`
- `0x18001dbf0`

## callees

- `0x180013850`
- `0x180018f70`
- `0x180019588`
- `0x18001a64c`
- `0x18001ab30`
- `0x18001b8e8`
- `0x18001c464`
- `0x18001c4ec`
- `0x18001c530`
- `0x18001c660`
- `0x18001e020`
- `0x18002fa9c`
- `0x180037790`
- `0x180038010`

## import_xrefs

- `msvcrt!_ultow_s` at `0x18001e14b`
- `msvcrt!_ultow_s` at `0x18001e14b`
- `iisutil!PuDbgPrint` at `0x18001e60b`
- `iisutil!PuDbgPrint` at `0x18001e60b`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e17d`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e214`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e45c`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e500`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e17d`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e214`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e45c`
- `iisutil!?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z` at `0x18001e500`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001e2dc`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001e2f7`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001e312`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001e2dc`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001e2f7`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x18001e312`
- `iisutil!PuDbgPrintError` at `0x18001e4b2`
- `iisutil!PuDbgPrintError` at `0x18001e4b2`

## string_xrefs

- `0x18001e487`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`
- `0x18001e604`: `servercommon\inetsrv\iis\iisrearc\iis70\core\w3server.cxx`
- `0x18001e4a2`: `Failed to call RegisterModule for dll=%S, mod=%S\n`
- `0x18001e479`: `W3_SERVER::LoadModulesFromConfig`
- `0x18001e5f2`: `W3_SERVER::LoadModulesFromConfig`

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
0x18001e020  mov     [rsp-8+arg_10], rbx
0x18001e025  push    rbp
0x18001e026  push    rsi
0x18001e027  push    rdi
0x18001e028  push    r12
0x18001e02a  push    r13
0x18001e02c  push    r14
0x18001e02e  push    r15
0x18001e030  lea     rbp, [rsp-27h]
0x18001e035  sub     rsp, 0E0h
0x18001e03c  mov     rax, cs:__security_cookie
0x18001e043  xor     rax, rsp
0x18001e046  mov     [rbp+57h+var_38], rax
0x18001e04a  xor     edi, edi
0x18001e04c  lea     r9, [rbp+57h+var_A8]
0x18001e050  mov     r12, rdx
0x18001e053  mov     [rbp+57h+var_A8], rdi
0x18001e057  mov     rsi, rcx
0x18001e05a  mov     [rbp+57h+var_B0], rdi
0x18001e05e  mov     rcx, [rcx+5D8h]
0x18001e065  lea     rdx, [rbp+57h+var_88]
0x18001e069  mov     [rbp+57h+var_D0], rdi
0x18001e06d  mov     r13d, r8d
0x18001e070  mov     qword ptr [rbp+57h+var_C0], rdi
0x18001e074  lea     r8, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x18001e07b  mov     qword ptr [rbp+57h+var_C0+8], rdi
0x18001e07f  mov     r14d, edi
0x18001e082  mov     [rbp+57h+var_80], rdi
0x18001e086  mov     [rbp+57h+var_C8], edi
0x18001e089  mov     [rbp+57h+var_88], rdi
0x18001e08d  mov     [rbp+57h+var_90], edi
0x18001e090  mov     rax, [rcx]
0x18001e093  mov     [rsp+110h+var_E8], rdi
0x18001e098  mov     [rsp+110h+var_F0], rdx
0x18001e09d  lea     rdx, aSystemWebserve_1; "system.webServer/globalModules"
0x18001e0a4  mov     qword ptr [rbp+57h+var_A0], rdi
0x18001e0a8  mov     rax, [rax+18h]
0x18001e0ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0b1  mov     ebx, eax
0x18001e0b3  test    eax, eax
0x18001e0b5  jns     loc_18001E1A7
0x18001e0bb  mov     rcx, [rsi]
0x18001e0be  xorps   xmm0, xmm0
0x18001e0c1  movups  [rbp+57h+var_78], xmm0
0x18001e0c5  mov     dword ptr [rbp+57h+var_A0], edi
0x18001e0c8  movups  [rbp+57h+var_68], xmm0
0x18001e0cc  mov     rax, [rcx+8]
0x18001e0d0  mov     rcx, rsi
0x18001e0d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0d8  mov     rcx, [rbp+57h+var_88]
0x18001e0dc  mov     qword ptr [rbp+57h+var_78], rax
0x18001e0e0  test    rcx, rcx
0x18001e0e3  jz      short loc_18001E122
0x18001e0e5  mov     rax, [rcx]
0x18001e0e8  lea     rdx, [rbp+57h+var_78+8]
0x18001e0ec  mov     rax, [rax+18h]
0x18001e0f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e0f5  mov     rcx, [rbp+57h+var_88]
0x18001e0f9  lea     rdx, [rbp+57h+var_68]
0x18001e0fd  mov     rax, [rcx]
0x18001e100  mov     rax, [rax+28h]
0x18001e104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e109  mov     rcx, [rbp+57h+var_88]
0x18001e10d  lea     rdx, [rbp+57h+var_A0]
0x18001e111  mov     rax, [rcx]
0x18001e114  mov     rax, [rax+20h]
0x18001e118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e11d  mov     ecx, dword ptr [rbp+57h+var_A0]
0x18001e120  jmp     short loc_18001E13D
0x18001e122  lea     rax, aUnknownError; "Unknown Error"
0x18001e129  mov     ecx, edi; Value
0x18001e12b  mov     qword ptr [rbp+57h+var_78+8], rax
0x18001e12f  lea     rax, aUnknownFile; "Unknown File"
0x18001e136  mov     qword ptr [rbp+57h+var_68], rax
0x18001e13a  mov     dword ptr [rbp+57h+var_A0], ecx
0x18001e13d  mov     r9d, 0Ah; Radix
0x18001e143  lea     rdx, [rbp+57h+Buffer]; Buffer
0x18001e147  lea     r8d, [r9+6]; BufferCount
0x18001e14b  call    cs:__imp__ultow_s
0x18001e152  nop     dword ptr [rax+rax+00h]
0x18001e157  lea     rax, [rbp+57h+Buffer]
0x18001e15b  mov     ecx, ebx; int
0x18001e15d  mov     qword ptr [rbp+57h+var_68+8], rax
0x18001e161  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001e166  lea     rcx, [rsi+1Ch]
0x18001e16a  mov     dword ptr [rsp+110h+var_F0], eax
0x18001e16e  mov     edx, 0C00008F9h
0x18001e173  lea     r9, [rbp+57h+var_78]
0x18001e177  mov     r8d, 4
0x18001e17d  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001e184  nop     dword ptr [rax+rax+00h]
0x18001e189  mov     rcx, [rbp+57h+var_88]
0x18001e18d  test    rcx, rcx
0x18001e190  jz      loc_18001E617
0x18001e196  mov     rax, [rcx]
0x18001e199  mov     rax, [rax+10h]
0x18001e19d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1a2  jmp     loc_18001E617
0x18001e1a7  mov     rcx, [rbp+57h+var_A8]
0x18001e1ab  lea     rdx, [rbp+57h+var_B0]
0x18001e1af  mov     rax, [rcx]
0x18001e1b2  mov     rax, [rax+28h]
0x18001e1b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1bb  mov     rcx, [rbp+57h+var_A8]
0x18001e1bf  mov     ebx, eax
0x18001e1c1  mov     rdx, [rcx]
0x18001e1c4  mov     rax, [rdx+10h]
0x18001e1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1cd  mov     [rbp+57h+var_A8], rdi
0x18001e1d1  test    ebx, ebx
0x18001e1d3  js      loc_18001E617
0x18001e1d9  mov     rcx, [rbp+57h+var_B0]
0x18001e1dd  lea     rdx, [rbp+57h+var_C8]
0x18001e1e1  mov     rax, [rcx]
0x18001e1e4  mov     rax, [rax+18h]
0x18001e1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e1ed  mov     ebx, eax
0x18001e1ef  test    eax, eax
0x18001e1f1  js      loc_18001E57B
0x18001e1f7  test    r13d, r13d
0x18001e1fa  jz      short loc_18001E220
0x18001e1fc  cmp     [rbp+57h+var_C8], edi
0x18001e1ff  jnz     short loc_18001E220
0x18001e201  xor     r8d, r8d
0x18001e204  mov     dword ptr [rsp+110h+var_F0], edi
0x18001e208  lea     rcx, [rsi+1Ch]
0x18001e20c  xor     r9d, r9d
0x18001e20f  mov     edx, 800008FAh
0x18001e214  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001e21b  nop     dword ptr [rax+rax+00h]
0x18001e220  mov     r15d, edi
0x18001e223  mov     rcx, [rbp+57h+var_B0]
0x18001e227  mov     rax, [rcx]
0x18001e22a  cmp     r15d, [rbp+57h+var_C8]
0x18001e22e  jnb     loc_18001E51A
0x18001e234  mov     rax, [rax+20h]
0x18001e238  lea     r8, [rbp+57h+var_D0]
0x18001e23c  mov     edx, r15d
0x18001e23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e244  mov     ebx, eax
0x18001e246  test    eax, eax
0x18001e248  js      loc_18001E57B
0x18001e24e  mov     rcx, [rbp+57h+var_D0]
0x18001e252  lea     r8, [rbp+57h+var_C0]
0x18001e256  xor     r9d, r9d
0x18001e259  mov     [rsp+110h+var_F0], rdi
0x18001e25e  lea     rdx, aName_0; "name"
0x18001e265  mov     rax, [rcx]
0x18001e268  mov     rax, [rax+40h]
0x18001e26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e271  mov     ebx, eax
0x18001e273  test    eax, eax
0x18001e275  js      loc_18001E57B
0x18001e27b  mov     rcx, [rbp+57h+var_D0]
0x18001e27f  lea     r8, [rbp+57h+var_C0+8]
0x18001e283  xor     r9d, r9d
0x18001e286  mov     [rsp+110h+var_F0], rdi
0x18001e28b  lea     rdx, aImage; "image"
0x18001e292  mov     rax, [rcx]
0x18001e295  mov     rax, [rax+40h]
0x18001e299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e29e  mov     ebx, eax
0x18001e2a0  test    eax, eax
0x18001e2a2  js      loc_18001E57B
0x18001e2a8  mov     rcx, [rbp+57h+var_D0]
0x18001e2ac  lea     r8, [rbp+57h+var_80]
0x18001e2b0  xor     r9d, r9d
0x18001e2b3  mov     [rsp+110h+var_F0], rdi
0x18001e2b8  lea     rdx, aPrecondition; "preCondition"
0x18001e2bf  mov     rax, [rcx]
0x18001e2c2  mov     rax, [rax+40h]
0x18001e2c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2cb  mov     ebx, eax
0x18001e2cd  test    eax, eax
0x18001e2cf  js      loc_18001E57B
0x18001e2d5  mov     rdx, qword ptr [rbp+57h+var_C0]
0x18001e2d9  mov     rcx, r12
0x18001e2dc  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001e2e3  nop     dword ptr [rax+rax+00h]
0x18001e2e8  test    eax, eax
0x18001e2ea  jz      loc_18001E513
0x18001e2f0  mov     rdx, qword ptr [rbp+57h+var_C0+8]
0x18001e2f4  mov     rcx, r12
0x18001e2f7  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001e2fe  nop     dword ptr [rax+rax+00h]
0x18001e303  test    eax, eax
0x18001e305  jz      loc_18001E513
0x18001e30b  mov     rdx, [rbp+57h+var_80]
0x18001e30f  mov     rcx, r12
0x18001e312  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x18001e319  nop     dword ptr [rax+rax+00h]
0x18001e31e  test    eax, eax
0x18001e320  jz      loc_18001E513
0x18001e326  mov     rax, [rsi]
0x18001e329  lea     r8, [rbp+57h+var_90]
0x18001e32d  mov     rdx, [rbp+57h+var_80]
0x18001e331  mov     rcx, rsi
0x18001e334  mov     rax, [rax+0B0h]
0x18001e33b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e340  cmp     [rbp+57h+var_90], edi
0x18001e343  jnz     loc_18001E4D1
0x18001e349  test    r13d, r13d
0x18001e34c  jz      loc_18001E40A
0x18001e352  test    eax, eax
0x18001e354  jz      loc_18001E40A
0x18001e35a  mov     rcx, qword ptr [rbp+57h+var_C0+8]; unsigned __int16 *
0x18001e35e  lea     rdx, [rbp+57h+var_A0]; struct MODULE_DLL **
0x18001e362  call    ?GetModuleDll@MODULE_DLL@@SAJPEBGPEAPEAV1@@Z; MODULE_DLL::GetModuleDll(ushort const *,MODULE_DLL * *)
0x18001e367  mov     ebx, eax
0x18001e369  test    eax, eax
0x18001e36b  js      loc_18001E4C8
0x18001e371  mov     ecx, 0B0h; Size
0x18001e376  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001e37b  test    rax, rax
0x18001e37e  jz      loc_18001E4C3
0x18001e384  mov     rcx, rax; this
0x18001e387  call    ??0VIRTUAL_MODULE@@QEAA@XZ; VIRTUAL_MODULE::VIRTUAL_MODULE(void)
0x18001e38c  mov     rdi, rax
0x18001e38f  test    rax, rax
0x18001e392  jz      loc_18001E4C3
0x18001e398  mov     r14, qword ptr [rbp+57h+var_A0]
0x18001e39c  mov     rcx, rax; this
0x18001e39f  mov     rdx, qword ptr [rbp+57h+var_C0]; unsigned __int16 *
0x18001e3a3  mov     r8, r14; struct MODULE_DLL *
0x18001e3a6  call    ?Create@VIRTUAL_MODULE@@QEAAJPEBGPEAVMODULE_DLL@@@Z; VIRTUAL_MODULE::Create(ushort const *,MODULE_DLL *)
0x18001e3ab  mov     ebx, eax
0x18001e3ad  test    eax, eax
0x18001e3af  js      loc_18001E55F
0x18001e3b5  mov     rax, [rdi+60h]
0x18001e3b9  xor     r14d, r14d
0x18001e3bc  mov     qword ptr [rbp+57h+var_A0], r14
0x18001e3c0  test    rax, rax
0x18001e3c3  jz      short loc_18001E426
0x18001e3c5  mov     r8, cs:?g_pW3Server@@3PEAVW3_SERVER@@EA; W3_SERVER * g_pW3Server
0x18001e3cc  mov     rdx, rdi
0x18001e3cf  mov     rax, [rax+30h]
0x18001e3d3  mov     ecx, 0A0000h
0x18001e3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3dd  mov     ebx, eax
0x18001e3df  test    eax, eax
0x18001e3e1  js      short loc_18001E42B
0x18001e3e3  lea     rcx, [rsi+230h]; this
0x18001e3ea  mov     rdx, rdi; struct VIRTUAL_MODULE *
0x18001e3ed  call    ?AppendModule@MODULE_LIST@@QEAAJPEAVVIRTUAL_MODULE@@@Z; MODULE_LIST::AppendModule(VIRTUAL_MODULE *)
0x18001e3f2  mov     ebx, eax
0x18001e3f4  test    eax, eax
0x18001e3f6  js      loc_18001E571
0x18001e3fc  xor     edi, edi
0x18001e3fe  mov     qword ptr [rbp+57h+var_C0+8], rdi
0x18001e402  mov     qword ptr [rbp+57h+var_C0], rdi
0x18001e406  mov     [rbp+57h+var_80], rdi
0x18001e40a  mov     rcx, [rbp+57h+var_D0]
0x18001e40e  mov     rax, [rcx]
0x18001e411  mov     rax, [rax+10h]
0x18001e415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e41a  inc     r15d
0x18001e41d  mov     [rbp+57h+var_D0], rdi
0x18001e421  jmp     loc_18001E223
0x18001e426  mov     ebx, 80070032h
0x18001e42b  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001e42f  mov     ecx, ebx; int
0x18001e431  mov     qword ptr [rbp+57h+var_A0], rax
0x18001e435  mov     r14d, ebx
0x18001e438  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18001e43c  mov     qword ptr [rbp+57h+var_A0+8], rax
0x18001e440  call    ?WIN32_FROM_HRESULT@@YAKJ@Z; WIN32_FROM_HRESULT(long)
0x18001e445  lea     rcx, [rsi+1Ch]
0x18001e449  mov     dword ptr [rsp+110h+var_F0], eax
0x18001e44d  mov     edx, 0C00008F5h
0x18001e452  lea     r9, [rbp+57h+var_A0]
0x18001e456  mov     r8d, 2
0x18001e45c  call    cs:__imp_?LogEvent@EVENT_LOG@@QEAAXKGQEAPEBGK@Z; EVENT_LOG::LogEvent(ulong,ushort,ushort const * * const,ulong)
0x18001e463  nop     dword ptr [rax+rax+00h]
0x18001e468  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18001e46f  jz      loc_18001E571
0x18001e475  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001e479  lea     r9, aW3ServerLoadmo; "W3_SERVER::LoadModulesFromConfig"
0x18001e480  mov     rcx, cs:g_pDebug
0x18001e487  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18001e48e  mov     [rsp+110h+var_D8], rax
0x18001e493  mov     r8d, 563h
0x18001e499  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18001e49d  mov     [rsp+110h+var_E0], rax
0x18001e4a2  lea     rax, aFailedToCallRe; "Failed to call RegisterModule for dll=%"...
0x18001e4a9  mov     [rsp+110h+var_E8], rax
0x18001e4ae  mov     dword ptr [rsp+110h+var_F0], ebx
0x18001e4b2  call    cs:__imp_PuDbgPrintError
0x18001e4b9  nop     dword ptr [rax+rax+00h]
0x18001e4be  jmp     loc_18001E571
0x18001e4c3  mov     ebx, 80070008h
0x18001e4c8  mov     r14, qword ptr [rbp+57h+var_A0]
0x18001e4cc  jmp     loc_18001E55F
0x18001e4d1  mov     rax, qword ptr [rbp+57h+var_C0]
0x18001e4d5  lea     rcx, [rsi+1Ch]
0x18001e4d9  mov     qword ptr [rbp+57h+var_78], rax
0x18001e4dd  lea     r9, [rbp+57h+var_78]
0x18001e4e1  mov     rax, qword ptr [rbp+57h+var_C0+8]
0x18001e4e5  mov     r8d, 3
0x18001e4eb  mov     qword ptr [rbp+57h+var_78+8], rax
0x18001e4ef  mov     edx, 0C00008F8h
  ... truncated ...
```
