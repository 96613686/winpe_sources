# SuInitialize(void)

- ea: `0x180035684`
- end: `0x1800358a1`
- name: `?SuInitialize@@YAHXZ`
- size: `541`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001323c`

## callees

- `0x180007ab8`
- `0x180007adc`
- `0x18003224c`
- `0x1800322c4`
- `0x1800353e0`
- `0x180035684`
- `0x180036874`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x180035805`
- `KERNEL32!CreateFileW` at `0x180035805`
- `KERNEL32!CloseThreadpool` at `0x180035830`
- `KERNEL32!CloseThreadpool` at `0x180035830`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180035751`
- `KERNEL32!SetThreadpoolThreadMaximum` at `0x180035751`
- `KERNEL32!CreateThreadpool` at `0x18003572b`
- `KERNEL32!CreateThreadpool` at `0x18003572b`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x180035763`
- `KERNEL32!SetThreadpoolThreadMinimum` at `0x180035763`
- `KERNEL32!GetLastError` at `0x180035846`
- `KERNEL32!GetLastError` at `0x180035846`
- `KERNEL32!GetModuleHandleExW` at `0x1800356fb`
- `KERNEL32!GetModuleHandleExW` at `0x1800356fb`
- `KERNEL32!GetModuleFileNameW` at `0x180035723`
- `KERNEL32!GetModuleFileNameW` at `0x180035723`

## string_xrefs

- `0x18003573d`: `CreateThreadpool`
- `0x180035776`: `SetThreadpoolThreadMinimum`
- `0x18003581f`: `CreateFile`

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
        xmmword_180048160 = 0;
        qword_180048150 = 0;
        qword_180048158 = 0;
        qword_180048170 = 0;
        dword_180048178 = 0;
        dword_18004817C = 1;
        dword_180048180 = 72;
        qword_180048148 = (__int64)::Threadpool;
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
0x180035684  mov     [rsp+arg_8], rbx
0x180035689  push    rsi
0x18003568a  sub     rsp, 60h
0x18003568e  mov     [rsp+68h+hModule], 0
0x180035697  call    ?SiAcquireSpinLock@@YAXPEAPEAX@Z; SiAcquireSpinLock(void * *)
0x18003569c  mov     eax, cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x1800356a2  test    eax, eax
0x1800356a4  jz      short loc_1800356B8
0x1800356a6  inc     eax
0x1800356a8  mov     ebx, 1
0x1800356ad  mov     cs:?ReferenceCount@@3KA, eax; ulong ReferenceCount
0x1800356b3  jmp     loc_180035881
0x1800356b8  lea     r9, SpaceApiProvider_Context
0x1800356bf  lea     r8, SpaceApiProvider_Context
0x1800356c6  lea     rcx, SpaceApiProvider
0x1800356cd  call    McGenEventRegister_EventRegister
0x1800356d2  lea     rax, [rsp+68h+hModule]
0x1800356d7  mov     [rsp+68h+phModule], 0
0x1800356e0  lea     r8, [rsp+68h+phModule]; phModule
0x1800356e5  mov     [rsp+68h+var_28], rax
0x1800356ea  lea     rdx, ?Spaceport@@3PEAXEA; lpModuleName
0x1800356f1  mov     [rsp+68h+var_18], 1
0x1800356f6  mov     ecx, 4; dwFlags
0x1800356fb  call    cs:__imp_GetModuleHandleExW
0x180035701  lea     rcx, [rsp+68h+var_28]
0x180035706  mov     ebx, eax
0x180035708  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>>>(void)
0x18003570d  test    ebx, ebx
0x18003570f  jz      short loc_180035729
0x180035711  mov     rcx, [rsp+68h+hModule]; hModule
0x180035716  lea     rdx, ?ModuleName@@3PAGA; lpFilename
0x18003571d  mov     r8d, 104h; nSize
0x180035723  call    cs:__imp_GetModuleFileNameW
0x180035729  xor     ecx, ecx; reserved
0x18003572b  call    cs:__imp_CreateThreadpool
0x180035731  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rax; _TP_POOL * Threadpool
0x180035738  test    rax, rax
0x18003573b  jnz     short loc_180035749
0x18003573d  lea     rsi, aCreatethreadpo; "CreateThreadpool"
0x180035744  jmp     loc_180035826
0x180035749  mov     edx, 80h; cthrdMost
0x18003574e  mov     rcx, rax; ptpp
0x180035751  call    cs:__imp_SetThreadpoolThreadMaximum
0x180035757  mov     rcx, cs:?Threadpool@@3PEAU_TP_POOL@@EA; ptpp
0x18003575e  mov     edx, 1; cthrdMic
0x180035763  call    cs:__imp_SetThreadpoolThreadMinimum
0x180035769  mov     ebx, eax
0x18003576b  test    eax, eax
0x18003576d  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x180035774  jnz     short loc_180035782
0x180035776  lea     rsi, aSetthreadpoolt; "SetThreadpoolThreadMinimum"
0x18003577d  jmp     loc_180035826
0x180035782  mov     r8d, 3; dwShareMode
0x180035788  mov     [rsp+68h+hTemplateFile], 0; hTemplateFile
0x180035791  xorps   xmm0, xmm0
0x180035794  mov     [rsp+68h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18003579c  xor     r9d, r9d; lpSecurityAttributes
0x18003579f  mov     cs:?ThreadpoolEnv@@3U_TP_CALLBACK_ENVIRON_V3@@A, r8d; _TP_CALLBACK_ENVIRON_V3 ThreadpoolEnv
0x1800357a6  mov     edx, 0C0000000h; dwDesiredAccess
0x1800357ab  movdqa  cs:xmmword_180048160, xmm0
0x1800357b3  lea     rcx, FileName; "\\\\.\\Spaceport"
0x1800357ba  mov     [rsp+68h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800357bf  mov     cs:qword_180048150, 0
0x1800357ca  mov     cs:qword_180048158, 0
0x1800357d5  mov     cs:qword_180048170, 0
0x1800357e0  mov     cs:dword_180048178, 0
0x1800357ea  mov     cs:dword_18004817C, 1
0x1800357f4  mov     cs:dword_180048180, 48h ; 'H'
0x1800357fe  mov     cs:qword_180048148, rax
0x180035805  call    cs:__imp_CreateFileW
0x18003580b  mov     cs:?Spaceport@@3PEAXEA, rax; void * Spaceport
0x180035812  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180035816  jnz     short loc_18003587B
0x180035818  mov     rax, cs:?Threadpool@@3PEAU_TP_POOL@@EA; _TP_POOL * Threadpool
0x18003581f  lea     rsi, aCreatefile; "CreateFile"
0x180035826  xor     ebx, ebx
0x180035828  test    rax, rax
0x18003582b  jz      short loc_18003583D
0x18003582d  mov     rcx, rax; ptpp
0x180035830  call    cs:__imp_CloseThreadpool
0x180035836  mov     cs:?Threadpool@@3PEAU_TP_POOL@@EA, rbx; _TP_POOL * Threadpool
0x18003583d  test    cs:Microsoft_Windows_StorageSpaces_ApiEnableBits, 1
0x180035844  jz      short loc_18003586D
0x180035846  call    cs:__imp_GetLastError
0x18003584c  mov     dword ptr [rsp+68h+hTemplateFile], eax
0x180035850  lea     rdx, InitializeApiFailed
0x180035857  lea     rax, aSuinitialize; "SuInitialize"
0x18003585e  mov     qword ptr [rsp+68h+dwFlagsAndAttributes], rsi
0x180035863  mov     qword ptr [rsp+68h+dwCreationDisposition], rax
0x180035868  call    McTemplateK0zssq_EventWriteTransfer
0x18003586d  lea     rcx, SpaceApiProvider_Context
0x180035874  call    McGenEventUnregister_EventUnregister
0x180035879  jmp     short loc_180035881
0x18003587b  inc     cs:?ReferenceCount@@3KA; ulong ReferenceCount
0x180035881  xor     ecx, ecx
0x180035883  xchg    rcx, cs:?Lock@@3PEAXEA; void * Lock
0x18003588a  lea     rcx, [rsp+68h+hModule]
0x18003588f  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x180035894  mov     eax, ebx
0x180035896  mov     rbx, [rsp+68h+arg_8]
0x18003589b  add     rsp, 60h
0x18003589f  pop     rsi
0x1800358a0  retn
```
