# SuInitialize(void)

- ea: `0x1801b0094`
- end: `0x1801b02b1`
- name: `?SuInitialize@@YAHXZ`
- size: `541`
- prototype: `__int64(void)`
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002af94`
- `0x18004e634`
- `0x18009304c`
- `0x180118fc4`
- `0x18019a8a0`

## callees

- `0x18000b6b8`
- `0x18000b6dc`
- `0x1801af7f4`
- `0x1801af850`
- `0x1801afb60`
- `0x1801b0094`
- `0x1801b0364`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0256`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b0256`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1801b010b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1801b010b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801b0133`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1801b0133`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1801b0173`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x1801b0173`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1801b0161`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x1801b0161`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1801b0240`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x1801b0240`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1801b013b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x1801b013b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b0215`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801b0215`

## string_xrefs

- `0x1801b022f`: `CreateFile`
- `0x1801b014d`: `CreateThreadpool`
- `0x1801b0186`: `SetThreadpoolThreadMinimum`

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
0x1801b0094  mov     [rsp+arg_8], rbx
0x1801b0099  push    rsi
0x1801b009a  sub     rsp, 60h
0x1801b009e  mov     [rsp+68h+hModule], 0
0x1801b00a7  call    ?SiAcquireSpinLock@@YAXPEAPEAX@Z; SiAcquireSpinLock(void * *)
0x1801b00ac  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1801b00b2  test    eax, eax
0x1801b00b4  jz      short loc_1801B00C8
0x1801b00b6  inc     eax
0x1801b00b8  mov     ebx, 1
0x1801b00bd  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x1801b00c3  jmp     loc_1801B0291
0x1801b00c8  lea     r9, SpaceApiProvider_Context
0x1801b00cf  lea     r8, SpaceApiProvider_Context
0x1801b00d6  lea     rcx, SpaceApiProvider
0x1801b00dd  call    McGenEventRegister_EventRegister
0x1801b00e2  lea     rax, [rsp+68h+hModule]
0x1801b00e7  mov     [rsp+68h+phModule], 0
0x1801b00f0  lea     r8, [rsp+68h+phModule]; phModule
0x1801b00f5  mov     [rsp+68h+var_28], rax
0x1801b00fa  lea     rdx, ?Spaceport@@3PEAXEA; lpModuleName
0x1801b0101  mov     [rsp+68h+var_18], 1
0x1801b0106  mov     ecx, 4; dwFlags
0x1801b010b  call    cs:__imp_GetModuleHandleExW
0x1801b0111  lea     rcx, [rsp+68h+var_28]
0x1801b0116  mov     ebx, eax
0x1801b0118  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x1801b011d  test    ebx, ebx
0x1801b011f  jz      short loc_1801B0139
0x1801b0121  mov     rcx, [rsp+68h+hModule]; hModule
0x1801b0126  lea     rdx, ?ModuleName@@3PAGA; lpFilename
0x1801b012d  mov     r8d, 104h; nSize
0x1801b0133  call    cs:__imp_GetModuleFileNameW
0x1801b0139  xor     ecx, ecx; reserved
0x1801b013b  call    cs:__imp_CreateThreadpool
0x1801b0141  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * Threadpool
0x1801b0148  test    rax, rax
0x1801b014b  jnz     short loc_1801B0159
0x1801b014d  lea     rsi, aCreatethreadpo; "CreateThreadpool"
0x1801b0154  jmp     loc_1801B0236
0x1801b0159  mov     edx, 80h; cthrdMost
0x1801b015e  mov     rcx, rax; ptpp
0x1801b0161  call    cs:__imp_SetThreadpoolThreadMaximum
0x1801b0167  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x1801b016e  mov     edx, 1; cthrdMic
0x1801b0173  call    cs:__imp_SetThreadpoolThreadMinimum
0x1801b0179  mov     ebx, eax
0x1801b017b  test    eax, eax
0x1801b017d  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x1801b0184  jnz     short loc_1801B0192
0x1801b0186  lea     rsi, aSetthreadpoolt; "SetThreadpoolThreadMinimum"
0x1801b018d  jmp     loc_1801B0236
0x1801b0192  mov     r8d, 3; dwShareMode
0x1801b0198  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x1801b01a1  xorps   xmm0, xmm0
0x1801b01a4  mov     [rsp+68h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x1801b01ac  xor     r9d, r9d; lpSecurityAttributes
0x1801b01af  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Version, r8d; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b01b6  mov     edx, 0C0000000h; dwDesiredAccess
0x1801b01bb  movdqa  xmmword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.RaceDll, xmm0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b01c3  lea     rcx, aSpaceport; "\\\\.\\Spaceport"
0x1801b01ca  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x1801b01cf  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroup, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b01da  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CleanupGroupCancelCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b01e5  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.FinalizationCallback, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b01f0  mov     dword ptr cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.u, 0; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b01fa  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.CallbackPriority, 1; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b0204  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Size, 48h ; 'H'; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b020e  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A.Pool, rax; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv ...
0x1801b0215  call    cs:__imp_CreateFileW
0x1801b021b  mov     cs:?Spaceport@@3PEAXEA, rax; void * Spaceport
0x1801b0222  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801b0226  jnz     short loc_1801B028B
0x1801b0228  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x1801b022f  lea     rsi, aCreatefile; "CreateFile"
0x1801b0236  xor     ebx, ebx
0x1801b0238  test    rax, rax
0x1801b023b  jz      short loc_1801B024D
0x1801b023d  mov     rcx, rax; ptpp
0x1801b0240  call    cs:__imp_CloseThreadpool
0x1801b0246  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rbx; _TP_POOL * Threadpool
0x1801b024d  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x1801b0254  jz      short loc_1801B027D
0x1801b0256  call    cs:__imp_GetLastError
0x1801b025c  mov     dword ptr [rsp+68h+hTemplateFile], eax
0x1801b0260  lea     rdx, InitializeApiFailed
0x1801b0267  lea     rax, aSuinitialize; "SuInitialize"
0x1801b026e  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi
0x1801b0273  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x1801b0278  call    McTemplateK0zssq_EventWriteTransfer
0x1801b027d  lea     rcx, SpaceApiProvider_Context
0x1801b0284  call    McGenEventUnregister_EventUnregister
0x1801b0289  jmp     short loc_1801B0291
0x1801b028b  inc     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1801b0291  xor     ecx, ecx
0x1801b0293  xchg    rcx, cs:?Lock@@3PEAXEA; void * Lock
0x1801b029a  lea     rcx, [rsp+68h+hModule]
0x1801b029f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x1801b02a4  mov     eax, ebx
0x1801b02a6  mov     rbx, [rsp+68h+arg_8]
0x1801b02ab  add     rsp, 60h
0x1801b02af  pop     rsi
0x1801b02b0  retn
```
