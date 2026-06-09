# SuInitialize(void)

- ea: `0x1801b5e7c`
- end: `0x1801b60ca`
- name: `?SuInitialize@@YAHXZ`
- size: `590`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002bc64`
- `0x18004ff18`
- `0x1800958b8`
- `0x18011cb18`
- `0x18019f5d8`

## callees

- `0x18000b578`
- `0x18000b5a4`
- `0x1801b5488`
- `0x1801b54ec`
- `0x1801b5884`
- `0x1801b5e7c`
- `0x1801b61e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6068`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b6068`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1801b5ef3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1801b5ef3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801b5f21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801b5f21`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1801b5f73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1801b5f73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1801b5f5b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1801b5f5b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1801b604c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1801b604c`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1801b5f2f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1801b5f2f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b601b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b601b`

## string_xrefs

- `0x1801b603b`: `CreateFile`
- `0x1801b5f47`: `CreateThreadpool`
- `0x1801b5f8c`: `SetThreadpoolThreadMinimum`

## pseudocode

```c
__int64 __fastcall SuInitialize(void **a1)
{
  __int64 v1; // rdx
  unsigned int v2; // ebx
  BOOL ModuleHandle; // ebx
  struct _TP_POOL *Threadpool; // rax
  const char *v5; // rsi
  char LastError; // al
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  HMODULE *p_hModule; // [rsp+40h] [rbp-28h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-20h] BYREF
  char v13; // [rsp+50h] [rbp-18h]
  HMODULE hModule; // [rsp+70h] [rbp+8h] BYREF

  hModule = 0;
  SiAcquireSpinLock(a1);
  if ( ReferenceCount )
  {
    v2 = 1;
    ++ReferenceCount;
  }
  else
  {
    McGenEventRegister_EventRegister(SpaceApiProvider, v1, SpaceApiProvider_Context, SpaceApiProvider_Context);
    phModule = 0;
    p_hModule = &hModule;
    v13 = 1;
    ModuleHandle = GetModuleHandleExW(4u, (LPCWSTR)&Spaceport, &phModule);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(&p_hModule);
    if ( ModuleHandle )
      GetModuleFileNameW(hModule, &ModuleName, 0x104u);
    Threadpool = CreateThreadpool(0);
    ::Threadpool = Threadpool;
    if ( Threadpool )
    {
      SetThreadpoolThreadMaximum(Threadpool, 0x80u);
      v2 = SetThreadpoolThreadMinimum(::Threadpool, 1u);
      Threadpool = ::Threadpool;
      if ( v2 )
      {
        ThreadpoolEnv.Version = 3;
        *(_OWORD *)&ThreadpoolEnv.RaceDll = 0;
        ThreadpoolEnv.CleanupGroup = 0;
        ThreadpoolEnv.CleanupGroupCancelCallback = 0;
        ThreadpoolEnv.FinalizationCallback = 0;
        ThreadpoolEnv.u.Flags = 0;
        ThreadpoolEnv.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
        ThreadpoolEnv.Size = 72;
        ThreadpoolEnv.Pool = ::Threadpool;
        Spaceport = CreateFileW(L"\\\\.\\Spaceport", 0xC0000000, 3u, 0, 3u, 0x40000000u, 0);
        if ( Spaceport != (HANDLE)-1LL )
        {
          ++ReferenceCount;
          goto LABEL_17;
        }
        Threadpool = ::Threadpool;
        v5 = "CreateFile";
      }
      else
      {
        v5 = "SetThreadpoolThreadMinimum";
      }
    }
    else
    {
      v5 = "CreateThreadpool";
    }
    v2 = 0;
    if ( Threadpool )
    {
      CloseThreadpool(Threadpool);
      ::Threadpool = 0;
    }
    if ( (Microsoft_Windows_StorageSpaces_ApiEnableBits & 1) != 0 )
    {
      LastError = GetLastError();
      McTemplateK0zssq_EventWriteTransfer(
        v7,
        (unsigned int)InitializeApiFailed,
        v8,
        v9,
        (__int64)"SuInitialize",
        (__int64)v5,
        LastError);
    }
    McGenEventUnregister_EventUnregister(SpaceApiProvider_Context);
  }
LABEL_17:
  _InterlockedExchange64((volatile __int64 *)&Lock, 0);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&hModule);
  return v2;
}

```

## disassembly

```asm
0x1801b5e7c  mov     [rsp+arg_8], rbx
0x1801b5e81  push    rsi
0x1801b5e82  sub     rsp, 60h
0x1801b5e86  mov     [rsp+68h+hModule], 0
0x1801b5e8f  call    ?SiAcquireSpinLock@@YAXPEAPEAX@Z; SiAcquireSpinLock(void * *)
0x1801b5e94  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1801b5e9a  test    eax, eax
0x1801b5e9c  jz      short loc_1801B5EB0
0x1801b5e9e  inc     eax
0x1801b5ea0  mov     ebx, 1
0x1801b5ea5  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x1801b5eab  jmp     loc_1801B60A9
0x1801b5eb0  lea     r9, SpaceApiProvider_Context
0x1801b5eb7  lea     r8, SpaceApiProvider_Context
0x1801b5ebe  lea     rcx, SpaceApiProvider
0x1801b5ec5  call    McGenEventRegister_EventRegister
0x1801b5eca  lea     rax, [rsp+68h+hModule]
0x1801b5ecf  mov     [rsp+68h+phModule], 0
0x1801b5ed8  lea     r8, [rsp+68h+phModule]; phModule
0x1801b5edd  mov     [rsp+68h+var_28], rax
0x1801b5ee2  lea     rdx, ?Spaceport@@3PEAXEA; lpModuleName
0x1801b5ee9  mov     [rsp+68h+var_18], 1
0x1801b5eee  mov     ecx, 4; dwFlags
0x1801b5ef3  call    cs:__imp_GetModuleHandleExW
0x1801b5efa  nop     dword ptr [rax+rax+00h]
0x1801b5eff  lea     rcx, [rsp+68h+var_28]
0x1801b5f04  mov     ebx, eax
0x1801b5f06  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x1801b5f0b  test    ebx, ebx
0x1801b5f0d  jz      short loc_1801B5F2D
0x1801b5f0f  mov     rcx, [rsp+68h+hModule]; hModule
0x1801b5f14  lea     rdx, ?ModuleName@@3PAGA; lpFilename
0x1801b5f1b  mov     r8d, 104h; nSize
0x1801b5f21  call    cs:__imp_GetModuleFileNameW
0x1801b5f28  nop     dword ptr [rax+rax+00h]
0x1801b5f2d  xor     ecx, ecx; reserved
0x1801b5f2f  call    cs:__imp_CreateThreadpool
0x1801b5f36  nop     dword ptr [rax+rax+00h]
0x1801b5f3b  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * Threadpool
0x1801b5f42  test    rax, rax
0x1801b5f45  jnz     short loc_1801B5F53
0x1801b5f47  lea     rsi, aCreatethreadpo; "CreateThreadpool"
0x1801b5f4e  jmp     loc_1801B6042
0x1801b5f53  mov     edx, 80h; cthrdMost
0x1801b5f58  mov     rcx, rax; ptpp
0x1801b5f5b  call    cs:__imp_SetThreadpoolThreadMaximum
0x1801b5f62  nop     dword ptr [rax+rax+00h]
0x1801b5f67  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x1801b5f6e  mov     edx, 1; cthrdMic
0x1801b5f73  call    cs:__imp_SetThreadpoolThreadMinimum
0x1801b5f7a  nop     dword ptr [rax+rax+00h]
0x1801b5f7f  mov     ebx, eax
0x1801b5f81  test    eax, eax
0x1801b5f83  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x1801b5f8a  jnz     short loc_1801B5F98
0x1801b5f8c  lea     rsi, aSetthreadpoolt; "SetThreadpoolThreadMinimum"
0x1801b5f93  jmp     loc_1801B6042
0x1801b5f98  mov     r8d, 3; dwShareMode
0x1801b5f9e  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1801b5fa7  xorps   xmm0, xmm0
0x1801b5faa  mov     [rsp+68h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1801b5fb2  xor     r9d, r9d; lpSecurityAttributes
0x1801b5fb5  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, r8d; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b5fbc  mov     edx, 0C0000000h; dwDesiredAccess
0x1801b5fc1  movdqa  xmmword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b5fc9  lea     rcx, aSpaceport; "\\\\.\\Spaceport"
0x1801b5fd0  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801b5fd5  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b5fe0  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b5feb  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b5ff6  mov     dword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b6000  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b600a  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b6014  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b601b  call    cs:__imp_CreateFileW
0x1801b6022  nop     dword ptr [rax+rax+00h]
0x1801b6027  mov     cs:?Spaceport@@3PEAXEA, rax; void * Spaceport
0x1801b602e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801b6032  jnz     short loc_1801B60A3
0x1801b6034  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x1801b603b  lea     rsi, aCreatefile; "CreateFile"
0x1801b6042  xor     ebx, ebx
0x1801b6044  test    rax, rax
0x1801b6047  jz      short loc_1801B605F
0x1801b6049  mov     rcx, rax; ptpp
0x1801b604c  call    cs:__imp_CloseThreadpool
0x1801b6053  nop     dword ptr [rax+rax+00h]
0x1801b6058  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rbx; _TP_POOL * Threadpool
0x1801b605f  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x1801b6066  jz      short loc_1801B6095
0x1801b6068  call    cs:__imp_GetLastError
0x1801b606f  nop     dword ptr [rax+rax+00h]
0x1801b6074  mov     dword ptr [rsp+68h+hTemplateFile], eax
0x1801b6078  lea     rdx, InitializeApiFailed
0x1801b607f  lea     rax, aSuinitialize; "SuInitialize"
0x1801b6086  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi
0x1801b608b  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1801b6090  call    McTemplateK0zssq_EventWriteTransfer
0x1801b6095  lea     rcx, SpaceApiProvider_Context
0x1801b609c  call    McGenEventUnregister_EventUnregister
0x1801b60a1  jmp     short loc_1801B60A9
0x1801b60a3  inc     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1801b60a9  xor     ecx, ecx
0x1801b60ab  xchg    rcx, cs:?Lock@@3PEAXEA; void * Lock
0x1801b60b2  lea     rcx, [rsp+68h+hModule]
0x1801b60b7  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801b60bc  mov     eax, ebx
0x1801b60be  mov     rbx, [rsp+68h+arg_8]
0x1801b60c3  add     rsp, 60h
0x1801b60c7  pop     rsi
0x1801b60c8  retn
```
