# RegisterModule(ulong,IHttpModuleRegistrationInfo *,IHttpServer *)

- ea: `0x180009fa0`
- end: `0x18000a1ca`
- name: `?RegisterModule@@YAJKPEAVIHttpModuleRegistrationInfo@@PEAVIHttpServer@@@Z`
- size: `554`
- prototype: `__int64 __fastcall(unsigned int, struct IHttpModuleRegistrationInfo *, struct IHttpServer *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callees

- `0x1800088bc`
- `0x1800088fc`
- `0x180009fa0`
- `0x18000ad78`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a190`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a190`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a02e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a02e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a040`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x18000a00c`
- `iisutil!??0EVENT_LOG@@QEAA@PEBG@Z` at `0x18000a00c`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x18000a074`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x18000a074`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x18000a09a`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x18000a09a`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x18000a167`
- `iisutil!?Terminate@LANG_STRING@@QEAAJXZ` at `0x18000a167`

## string_xrefs

- `0x18000a025`: `iisres.dll`

## pseudocode

```c
__int64 __fastcall RegisterModule(__int64 a1, struct IHttpModuleRegistrationInfo *a2, struct IHttpServer *a3)
{
  EVENT_LOG *v5; // rbx
  int v6; // eax
  const unsigned __int16 *v7; // rdx
  signed int LastError; // eax
  signed int v9; // ebx
  LANG_STRING *v10; // rax
  LANG_STRING *v11; // rax
  _QWORD *v12; // rax
  _QWORD *v13; // rax

  g_pFilterModuleContext = (void *)(*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *))(*(_QWORD *)a2 + 8LL))(a2);
  g_pGlobalInfo = a3;
  v5 = (EVENT_LOG *)operator new(4u);
  if ( !v5 )
  {
    g_pEventLog = 0;
    goto LABEL_20;
  }
  v6 = (**(__int64 (__fastcall ***)(struct IHttpServer *))g_pGlobalInfo)(g_pGlobalInfo);
  v7 = L"HostableWebCore";
  if ( !v6 )
    v7 = L"W3SVC-WP";
  g_pEventLog = EVENT_LOG::EVENT_LOG(v5, v7);
  if ( !g_pEventLog )
    goto LABEL_20;
  g_hResourceDll = LoadLibraryExW(L"iisres.dll", 0, 0);
  if ( !g_hResourceDll )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
LABEL_16:
    if ( v9 >= 0 )
      return (unsigned int)v9;
    goto LABEL_21;
  }
  v10 = (LANG_STRING *)operator new(0x58u);
  if ( !v10 )
  {
    g_pLangString = 0;
    goto LABEL_20;
  }
  v11 = LANG_STRING::LANG_STRING(v10);
  g_pLangString = v11;
  if ( !v11 )
    goto LABEL_20;
  v9 = LANG_STRING::Initialize(v11, g_hResourceDll, 5u);
  if ( v9 < 0 )
    goto LABEL_21;
  v12 = operator new(0x10u);
  if ( !v12 )
    goto LABEL_20;
  *v12 = &CIISModuleFactory::`vftable';
  v12[1] = &CIISHttpModule::`vftable';
  v9 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64, __int64))(*(_QWORD *)a2 + 16LL))(
         a2,
         v12,
         2684354562LL,
         2);
  if ( v9 < 0 )
    goto LABEL_21;
  v13 = operator new(8u);
  if ( !v13 )
  {
LABEL_20:
    v9 = -2147024888;
    goto LABEL_21;
  }
  *v13 = &CIISGlobalModule::`vftable';
  v9 = (*(__int64 (__fastcall **)(struct IHttpModuleRegistrationInfo *, _QWORD *, __int64))(*(_QWORD *)a2 + 24LL))(
         a2,
         v13,
         256);
  if ( v9 >= 0 )
  {
    v9 = GlobalFilterInitialize();
    goto LABEL_16;
  }
LABEL_21:
  if ( g_pLangString )
  {
    LANG_STRING::Terminate((LANG_STRING *)g_pLangString);
    operator delete(g_pLangString);
    g_pLangString = 0;
  }
  if ( g_hResourceDll )
  {
    FreeLibrary(g_hResourceDll);
    g_hResourceDll = 0;
  }
  if ( g_pEventLog )
  {
    operator delete(g_pEventLog);
    g_pEventLog = 0;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180009fa0  mov     [rsp+arg_0], rbx
0x180009fa5  push    rdi
0x180009fa6  sub     rsp, 30h
0x180009faa  mov     rax, [rdx]
0x180009fad  mov     rcx, rdx
0x180009fb0  mov     rbx, r8
0x180009fb3  mov     rdi, rdx
0x180009fb6  mov     rax, [rax+8]
0x180009fba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fbf  mov     ecx, 4; Size
0x180009fc4  mov     cs:?g_pFilterModuleContext@@3PEAXEA, rax; void * g_pFilterModuleContext
0x180009fcb  mov     cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA, rbx; IHttpServer * g_pGlobalInfo
0x180009fd2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180009fd7  mov     rbx, rax
0x180009fda  test    rax, rax
0x180009fdd  jz      loc_18000A14B
0x180009fe3  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180009fea  mov     rdx, [rcx]
0x180009fed  mov     rax, [rdx]
0x180009ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ff5  test    eax, eax
0x180009ff7  lea     rcx, aW3svcWp; "W3SVC-WP"
0x180009ffe  lea     rdx, aHostablewebcor; "HostableWebCore"
0x18000a005  cmovz   rdx, rcx
0x18000a009  mov     rcx, rbx
0x18000a00c  call    cs:__imp_??0EVENT_LOG@@QEAA@PEBG@Z; EVENT_LOG::EVENT_LOG(ushort const *)
0x18000a012  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, rax; EVENT_LOG * g_pEventLog
0x18000a019  test    rax, rax
0x18000a01c  jz      loc_18000A156
0x18000a022  xor     r8d, r8d; dwFlags
0x18000a025  lea     rcx, LibFileName; "iisres.dll"
0x18000a02c  xor     edx, edx; hFile
0x18000a02e  call    cs:__imp_LoadLibraryExW
0x18000a034  mov     cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * g_hResourceDll
0x18000a03b  test    rax, rax
0x18000a03e  jnz     short loc_18000A05E
0x18000a040  call    cs:__imp_GetLastError
0x18000a046  mov     ebx, eax
0x18000a048  test    eax, eax
0x18000a04a  jle     loc_18000A134
0x18000a050  movzx   ebx, ax
0x18000a053  or      ebx, 80070000h
0x18000a059  jmp     loc_18000A134
0x18000a05e  mov     ecx, 58h ; 'X'; Size
0x18000a063  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a068  test    rax, rax
0x18000a06b  jz      loc_18000A13E
0x18000a071  mov     rcx, rax
0x18000a074  call    cs:__imp_??0LANG_STRING@@QEAA@XZ; LANG_STRING::LANG_STRING(void)
0x18000a07a  mov     cs:?g_pLangString@@3PEAVLANG_STRING@@EA, rax; LANG_STRING * g_pLangString
0x18000a081  test    rax, rax
0x18000a084  jz      loc_18000A156
0x18000a08a  mov     rdx, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hResourceDll
0x18000a091  mov     r8d, 5
0x18000a097  mov     rcx, rax
0x18000a09a  call    cs:__imp_?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z; LANG_STRING::Initialize(HINSTANCE__ *,ulong)
0x18000a0a0  mov     ebx, eax
0x18000a0a2  test    eax, eax
0x18000a0a4  js      loc_18000A15B
0x18000a0aa  mov     ecx, 10h; Size
0x18000a0af  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a0b4  mov     rdx, rax
0x18000a0b7  test    rax, rax
0x18000a0ba  jz      loc_18000A156
0x18000a0c0  lea     rax, ??_7CIISModuleFactory@@6B@; const CIISModuleFactory::`vftable'
0x18000a0c7  mov     r9d, 2
0x18000a0cd  mov     [rdx], rax
0x18000a0d0  mov     r8d, 0A0000002h
0x18000a0d6  lea     rax, ??_7CIISHttpModule@@6B@; const CIISHttpModule::`vftable'
0x18000a0dd  mov     [rdx+8], rax
0x18000a0e1  mov     rcx, [rdi]
0x18000a0e4  mov     rax, [rcx+10h]
0x18000a0e8  mov     rcx, rdi
0x18000a0eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0f0  mov     ebx, eax
0x18000a0f2  test    eax, eax
0x18000a0f4  js      short loc_18000A15B
0x18000a0f6  mov     ecx, 8; Size
0x18000a0fb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a100  mov     rdx, rax
0x18000a103  test    rax, rax
0x18000a106  jz      short loc_18000A156
0x18000a108  lea     rax, ??_7CIISGlobalModule@@6B@; const CIISGlobalModule::`vftable'
0x18000a10f  mov     r8d, 100h
0x18000a115  mov     [rdx], rax
0x18000a118  mov     rcx, [rdi]
0x18000a11b  mov     rax, [rcx+18h]
0x18000a11f  mov     rcx, rdi
0x18000a122  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a127  mov     ebx, eax
0x18000a129  test    eax, eax
0x18000a12b  js      short loc_18000A15B
0x18000a12d  call    ?GlobalFilterInitialize@@YAJXZ; GlobalFilterInitialize(void)
0x18000a132  mov     ebx, eax
0x18000a134  test    ebx, ebx
0x18000a136  jns     loc_18000A1BD
0x18000a13c  jmp     short loc_18000A15B
0x18000a13e  mov     cs:?g_pLangString@@3PEAVLANG_STRING@@EA, 0; LANG_STRING * g_pLangString
0x18000a149  jmp     short loc_18000A156
0x18000a14b  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, 0; EVENT_LOG * g_pEventLog
0x18000a156  mov     ebx, 80070008h
0x18000a15b  mov     rcx, cs:?g_pLangString@@3PEAVLANG_STRING@@EA; LANG_STRING * g_pLangString
0x18000a162  test    rcx, rcx
0x18000a165  jz      short loc_18000A184
0x18000a167  call    cs:__imp_?Terminate@LANG_STRING@@QEAAJXZ; LANG_STRING::Terminate(void)
0x18000a16d  mov     rcx, cs:?g_pLangString@@3PEAVLANG_STRING@@EA; Block
0x18000a174  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a179  mov     cs:?g_pLangString@@3PEAVLANG_STRING@@EA, 0; LANG_STRING * g_pLangString
0x18000a184  mov     rcx, cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA; hLibModule
0x18000a18b  test    rcx, rcx
0x18000a18e  jz      short loc_18000A1A1
0x18000a190  call    cs:__imp_FreeLibrary
0x18000a196  mov     cs:?g_hResourceDll@@3PEAUHINSTANCE__@@EA, 0; HINSTANCE__ * g_hResourceDll
0x18000a1a1  mov     rcx, cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA; Block
0x18000a1a8  test    rcx, rcx
0x18000a1ab  jz      short loc_18000A1BD
0x18000a1ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000a1b2  mov     cs:?g_pEventLog@@3PEAVEVENT_LOG@@EA, 0; EVENT_LOG * g_pEventLog
0x18000a1bd  mov     eax, ebx
0x18000a1bf  mov     rbx, [rsp+38h+arg_0]
0x18000a1c4  add     rsp, 30h
0x18000a1c8  pop     rdi
0x18000a1c9  retn
```
