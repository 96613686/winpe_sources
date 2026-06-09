# sandbox::SandboxManager::SandboxManager(bool,ushort const *)

- ea: `0x18003d250`
- end: `0x18003d3f0`
- name: `??0SandboxManager@sandbox@@AEAA@_NPEBG@Z`
- size: `416`
- prototype: `char *__fastcall(char *pv, char, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800d85fc`

## callees

- `0x1800116c0`
- `0x180015e28`
- `0x18002e91c`
- `0x18002fda0`
- `0x18002fdcc`
- `0x18003d250`
- `0x180047330`
- `0x1800d78a4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d35c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d381`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d35c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003d381`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003d2f5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003d2f5`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003d28e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x18003d28e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d36b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d32a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d36b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d398`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003d3c5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d3b3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003d3b3`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003d33e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18003d33e`

## string_xrefs

- `0x18003d3d1`: `Sandbox is now invalid because idle-timeout timer was not created. Error %u`
- `0x18003d337`: `PrintIsolationProxy.dll`

## pseudocode

```c
char *__fastcall sandbox::SandboxManager::SandboxManager(char *pv, char a2, const unsigned __int16 *a3)
{
  NCoreLibrary *v5; // rcx
  int LastErrorAsFailHRNoBreak; // eax
  HMODULE *v7; // rsi
  HMODULE Library; // rax
  HMODULE v9; // rcx
  DWORD LastError; // eax
  HMODULE LibraryW; // rax
  FARPROC ProcAddress; // rax
  FARPROC v13; // rax
  PTP_TIMER ThreadpoolTimer; // rax
  DWORD v15; // eax
  _BYTE v17[120]; // [rsp+20h] [rbp-78h] BYREF

  *((_DWORD *)pv + 2) = 1;
  *(_QWORD *)pv = &sandbox::SandboxManager::`vftable';
  *((_DWORD *)pv + 14) = 0;
  *((_DWORD *)pv + 15) = 0;
  *((_DWORD *)pv + 16) = -2147467259;
  *((_DWORD *)pv + 15) = 0;
  *((_DWORD *)pv + 14) = 0;
  if ( InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)(pv + 16), 0x80000FA0) )
    LastErrorAsFailHRNoBreak = 0;
  else
    LastErrorAsFailHRNoBreak = NCoreLibrary::GetLastErrorAsFailHRNoBreak(v5);
  *((_DWORD *)pv + 16) = LastErrorAsFailHRNoBreak;
  *((_DWORD *)pv + 19) = 0;
  pv[72] = a2;
  *((_QWORD *)pv + 10) = 0;
  *((_QWORD *)pv + 11) = 0;
  *((_DWORD *)pv + 24) = 0;
  *((_QWORD *)pv + 13) = 0;
  NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(pv + 104);
  *((_QWORD *)pv + 13) = 0;
  v7 = (HMODULE *)(pv + 112);
  *((_QWORD *)pv + 14) = 0;
  *((_QWORD *)pv + 15) = 0;
  sandbox::SandboxManagerUtil::SandboxManagerUtil((sandbox::SandboxManagerUtil *)(pv + 128));
  *((_QWORD *)pv + 28) = 0;
  Library = LoadLibraryExW(L"winspool.drv", 0, 0x800u);
  NCoreLibrary::TAutoHandleHMODULE::operator=(pv + 104, Library);
  memset_0(v17, 0, 0x50u);
  v9 = (HMODULE)*((_QWORD *)pv + 13);
  if ( v9 )
    LastError = InitializeWinSpoolFunctions(v9);
  else
    LastError = GetLastError();
  *((_DWORD *)pv + 19) = LastError;
  if ( !LastError )
  {
    LibraryW = LoadLibraryW(L"PrintIsolationProxy.dll");
    NCoreLibrary::TAutoHandleHMODULE::operator=(pv + 112, LibraryW);
  }
  if ( !*v7 || (ProcAddress = GetProcAddress(*v7, (LPCSTR)0x190), (*((_QWORD *)pv + 15) = ProcAddress) == 0) )
    *((_DWORD *)pv + 19) = GetLastError();
  if ( *v7 && (v13 = GetProcAddress(*v7, (LPCSTR)0x191)) != 0 )
    ((void (__fastcall *)(_BYTE *))v13)(v17);
  else
    *((_DWORD *)pv + 19) = GetLastError();
  if ( !*((_DWORD *)pv + 19) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(sandbox::SandboxManager::IdleTimeoutTimerCallback, pv, 0);
    *((_QWORD *)pv + 28) = ThreadpoolTimer;
    if ( !ThreadpoolTimer )
    {
      v15 = GetLastError();
      *((_DWORD *)pv + 19) = v15;
      SandboxTelemetry::WriteDbgTraceError(
        "sandbox::SandboxManager::SandboxManager",
        L"Sandbox is now invalid because idle-timeout timer was not created. Error %u",
        v15);
    }
  }
  return pv;
}

```

## disassembly

```asm
0x18003d250  push    rbx
0x18003d252  push    rbp
0x18003d253  push    rsi
0x18003d254  push    rdi
0x18003d255  sub     rsp, 78h
0x18003d259  mov     dword ptr [rcx+8], 1
0x18003d260  lea     rax, ??_7SandboxManager@sandbox@@6B@; const sandbox::SandboxManager::`vftable'
0x18003d267  mov     [rcx], rax
0x18003d26a  xor     ebp, ebp
0x18003d26c  mov     [rcx+38h], ebp
0x18003d26f  mov     sil, dl
0x18003d272  mov     [rcx+3Ch], ebp
0x18003d275  mov     rdi, rcx
0x18003d278  mov     dword ptr [rcx+40h], 80004005h
0x18003d27f  mov     edx, 80000FA0h; dwSpinCount
0x18003d284  mov     [rcx+3Ch], ebp
0x18003d287  mov     [rcx+38h], ebp
0x18003d28a  add     rcx, 10h; lpCriticalSection
0x18003d28e  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x18003d294  test    eax, eax
0x18003d296  jz      short loc_18003D29C
0x18003d298  mov     eax, ebp
0x18003d29a  jmp     short loc_18003D2A1
0x18003d29c  call    ?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ; NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)
0x18003d2a1  mov     [rdi+40h], eax
0x18003d2a4  lea     rbx, [rdi+68h]
0x18003d2a8  mov     [rdi+4Ch], ebp
0x18003d2ab  mov     rcx, rbx
0x18003d2ae  mov     [rdi+48h], sil
0x18003d2b2  mov     [rdi+50h], rbp
0x18003d2b6  mov     [rdi+58h], rbp
0x18003d2ba  mov     [rdi+60h], ebp
0x18003d2bd  mov     [rbx], rbp
0x18003d2c0  call    ?Reset@?$TGenericSP@PEAUHINSTANCE__@@VTAutoHandleHMODULE@NCoreLibrary@@PEAU1@$0A@PEBQEAU1@@NCoreLibrary@@QEAAXXZ; NCoreLibrary::TGenericSP<HINSTANCE__ *,NCoreLibrary::TAutoHandleHMODULE,HINSTANCE__ *,0,HINSTANCE__ * const *>::Reset(void)
0x18003d2c5  mov     [rbx], rbp
0x18003d2c8  lea     rsi, [rdi+70h]
0x18003d2cc  mov     [rsi], rbp
0x18003d2cf  lea     rcx, [rdi+80h]; this
0x18003d2d6  mov     [rdi+78h], rbp
0x18003d2da  call    ??0SandboxManagerUtil@sandbox@@QEAA@XZ; sandbox::SandboxManagerUtil::SandboxManagerUtil(void)
0x18003d2df  xor     edx, edx; hFile
0x18003d2e1  mov     [rdi+0E0h], rbp
0x18003d2e8  mov     r8d, 800h; dwFlags
0x18003d2ee  lea     rcx, aWinspoolDrv; "winspool.drv"
0x18003d2f5  call    cs:__imp_LoadLibraryExW
0x18003d2fb  mov     rdx, rax
0x18003d2fe  mov     rcx, rbx
0x18003d301  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x18003d306  xor     edx, edx; Val
0x18003d308  lea     rcx, [rsp+98h+var_78]; void *
0x18003d30d  lea     r8d, [rdx+50h]; Size
0x18003d311  call    memset_0
0x18003d316  mov     rcx, [rbx]; hModule
0x18003d319  test    rcx, rcx
0x18003d31c  jz      short loc_18003D32A
0x18003d31e  lea     rdx, [rsp+98h+var_78]
0x18003d323  call    InitializeWinSpoolFunctions
0x18003d328  jmp     short loc_18003D330
0x18003d32a  call    cs:__imp_GetLastError
0x18003d330  mov     [rdi+4Ch], eax
0x18003d333  test    eax, eax
0x18003d335  jnz     short loc_18003D34F
0x18003d337  lea     rcx, aPrintisolation_1; "PrintIsolationProxy.dll"
0x18003d33e  call    cs:__imp_LoadLibraryW
0x18003d344  mov     rdx, rax
0x18003d347  mov     rcx, rsi
0x18003d34a  call    ??4TAutoHandleHMODULE@NCoreLibrary@@QEAAPEAUHINSTANCE__@@PEAU2@@Z; NCoreLibrary::TAutoHandleHMODULE::operator=(HINSTANCE__ *)
0x18003d34f  mov     rcx, [rsi]; hModule
0x18003d352  test    rcx, rcx
0x18003d355  jz      short loc_18003D36B
0x18003d357  mov     edx, 190h; lpProcName
0x18003d35c  call    cs:__imp_GetProcAddress
0x18003d362  mov     [rdi+78h], rax
0x18003d366  test    rax, rax
0x18003d369  jnz     short loc_18003D374
0x18003d36b  call    cs:__imp_GetLastError
0x18003d371  mov     [rdi+4Ch], eax
0x18003d374  mov     rcx, [rsi]; hModule
0x18003d377  test    rcx, rcx
0x18003d37a  jz      short loc_18003D398
0x18003d37c  mov     edx, 191h; lpProcName
0x18003d381  call    cs:__imp_GetProcAddress
0x18003d387  test    rax, rax
0x18003d38a  jz      short loc_18003D398
0x18003d38c  lea     rcx, [rsp+98h+var_78]
0x18003d391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d396  jmp     short loc_18003D3A1
0x18003d398  call    cs:__imp_GetLastError
0x18003d39e  mov     [rdi+4Ch], eax
0x18003d3a1  cmp     [rdi+4Ch], ebp
0x18003d3a4  jnz     short loc_18003D3E4
0x18003d3a6  xor     r8d, r8d; pcbe
0x18003d3a9  lea     rcx, ?IdleTimeoutTimerCallback@SandboxManager@sandbox@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003d3b0  mov     rdx, rdi; pv
0x18003d3b3  call    cs:__imp_CreateThreadpoolTimer
0x18003d3b9  mov     [rdi+0E0h], rax
0x18003d3c0  test    rax, rax
0x18003d3c3  jnz     short loc_18003D3E4
0x18003d3c5  call    cs:__imp_GetLastError
0x18003d3cb  mov     r8d, eax
0x18003d3ce  mov     [rdi+4Ch], eax
0x18003d3d1  lea     rdx, aSandboxIsNowIn; "Sandbox is now invalid because idle-tim"...
0x18003d3d8  lea     rcx, aSandboxSandbox_12; "sandbox::SandboxManager::SandboxManager"
0x18003d3df  call    ?WriteDbgTraceError@SandboxTelemetry@@SAXPEADPEAGZZ; SandboxTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18003d3e4  mov     rax, rdi
0x18003d3e7  add     rsp, 78h
0x18003d3eb  pop     rdi
0x18003d3ec  pop     rsi
0x18003d3ed  pop     rbp
0x18003d3ee  pop     rbx
0x18003d3ef  retn
```
