# UpdateGPCoreStatus(IWbemLocator *,ushort const *,ushort const *)

- ea: `0x1800ad5ec`
- end: `0x1800ada35`
- name: `?UpdateGPCoreStatus@@YAJPEAUIWbemLocator@@PEBG1@Z`
- size: `1097`
- prototype: `__int64 __fastcall(struct IWbemLocator *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180071890`

## callees

- `0x18000a504`
- `0x18001ee6c`
- `0x18002c690`
- `0x18003d630`
- `0x1800490b0`
- `0x18004fb0c`
- `0x180050010`
- `0x180057b9c`
- `0x1800585e8`
- `0x180068650`
- `0x1800757a8`
- `0x180075ec0`
- `0x18007d320`
- `0x1800ad5ec`
- `0x1800b1f6c`
- `0x1800b8d14`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad8ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ad8ec`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ad852`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800ad852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad86f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad8f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad670`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad86f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad8f7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ad653`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ad653`

## string_xrefs

- `0x1800ad712`: `Computer`
- `0x1800ad6a1`: `UpdateGPCoreStatus: failed to allocate memory, 0x%x`
- `0x1800ad6d4`: `UpdateGPCoreStatus: failed to allocate memory, 0x%x`
- `0x1800ad756`: `UpdateGPCoreStatus: updating status from <%s> registry for gp core`
- `0x1800ad77e`: `UpdateGPCoreStatus: updating status from <%s> registry for gp core`
- `0x1800ad7eb`: `UpdateGPCoreStatus: GetWbemServicesPtr failed, hr = 0x%x`
- `0x1800ad813`: `UpdateGPCoreStatus: GetWbemServicesPtr failed, hr = 0x%x`
- `0x1800ad84b`: `gpscript.dll`
- `0x1800ad899`: `UpdateGPCoreStatus: LoadLibraryEx of gpscript.dll failed, hr = 0x%x`
- `0x1800ad8c1`: `UpdateGPCoreStatus: LoadLibraryEx of gpscript.dll failed, hr = 0x%x`
- `0x1800ad921`: `UpdateGPCoreStatus: GetProcAddresss to ScrRegGPOListToWbem() in gpscript.dll failed, hr = 0x%x`
- `0x1800ad93f`: `UpdateGPCoreStatus: GetProcAddresss to ScrRegGPOListToWbem() in gpscript.dll failed, hr = 0x%x`
- `0x1800ad974`: `UpdateGPCoreStatus: ScrRegGPOListToWbem failed, hr = 0x%x`
- `0x1800ad99a`: `UpdateGPCoreStatus: ScrRegGPOListToWbem failed, hr = 0x%x`

## pseudocode

```c
__int64 __fastcall UpdateGPCoreStatus(struct IWbemLocator *a1, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  __int64 v5; // rax
  unsigned __int64 v6; // rdi
  HLOCAL v7; // rax
  unsigned __int16 *v8; // rbx
  signed int v9; // eax
  unsigned int WbemServicesPtr; // ebx
  signed int LoggingStatusInternal; // eax
  unsigned __int16 *v12; // rax
  const unsigned __int16 *v13; // rsi
  const unsigned __int16 *v14; // rdx
  HMODULE Library; // rax
  signed int LastError; // eax
  void (*v17)(unsigned int, const unsigned __int16 *, ...); // rax
  const wchar_t *v18; // rdx
  FARPROC ProcAddress; // rax
  signed int v20; // eax
  struct _GPEXT *v21; // rdx
  int v22; // r8d
  struct IWbemServices *v24; // [rsp+20h] [rbp-E0h] BYREF
  HMODULE hModule; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int16 *v26; // [rsp+30h] [rbp-D0h] BYREF
  _OWORD v27[2]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v28[288]; // [rsp+60h] [rbp-A0h] BYREF

  hModule = (HMODULE)a1;
  memset(v27, 0, 28);
  v26 = 0;
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  v6 = v5 + 13;
  v7 = LocalAlloc(0x40u, 2 * (v5 + 13));
  XPtrLF<unsigned short>::operator=(&v26, v7);
  v8 = v26;
  if ( v26 )
  {
    LoggingStatusInternal = StringCchCopyW(v26, v6, a3);
    if ( LoggingStatusInternal < 0 )
      goto LABEL_13;
    v12 = CheckSlash(v8);
    v13 = L"Computer";
    if ( a2 )
      v13 = L"User";
    LoggingStatusInternal = StringCchCopyW(v12, v6 - (v12 - v8), v13);
    if ( LoggingStatusInternal < 0 )
      goto LABEL_13;
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(4u, L"UpdateGPCoreStatus: updating status from <%s> registry for gp core", v13);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(4u, L"UpdateGPCoreStatus: updating status from <%s> registry for gp core", v13);
      }
    }
    LoggingStatusInternal = ReadLoggingStatusInternal(a2, v14, (struct _RSOPEXTSTATUS *)v27, 0);
    if ( LoggingStatusInternal )
    {
      if ( LoggingStatusInternal > 0 )
        LoggingStatusInternal = (unsigned __int16)LoggingStatusInternal | 0x80070000;
LABEL_13:
      WbemServicesPtr = LoggingStatusInternal;
      goto LABEL_66;
    }
    v24 = 0;
    WbemServicesPtr = GetWbemServicesPtr(v8);
    if ( (WbemServicesPtr & 0x80000000) != 0 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"UpdateGPCoreStatus: GetWbemServicesPtr failed, hr = 0x%x", WbemServicesPtr);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"UpdateGPCoreStatus: GetWbemServicesPtr failed, hr = 0x%x", WbemServicesPtr);
        }
      }
      goto LABEL_33;
    }
    if ( !(unsigned int)CSKU::IsDomainIncapableSystem() )
    {
      hModule = 0;
      Library = LoadLibraryExW(L"gpscript.dll", 0, 0);
      XHLibrary::operator=(&hModule, Library);
      if ( !hModule )
      {
        LastError = GetLastError();
        WbemServicesPtr = LastError;
        if ( LastError > 0 )
          WbemServicesPtr = (unsigned __int16)LastError | 0x80070000;
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_45;
        v17 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(
              2u,
              L"UpdateGPCoreStatus: LoadLibraryEx of gpscript.dll failed, hr = 0x%x",
              WbemServicesPtr);
          goto LABEL_45;
        }
        v18 = L"UpdateGPCoreStatus: LoadLibraryEx of gpscript.dll failed, hr = 0x%x";
        goto LABEL_41;
      }
      ProcAddress = GetProcAddress(hModule, "ScrRegGPOListToWbem");
      if ( !ProcAddress )
      {
        v20 = GetLastError();
        WbemServicesPtr = v20;
        if ( v20 > 0 )
          WbemServicesPtr = (unsigned __int16)v20 | 0x80070000;
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_45;
        v17 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(
              2u,
              L"UpdateGPCoreStatus: GetProcAddresss to ScrRegGPOListToWbem() in gpscript.dll failed, hr = 0x%x",
              WbemServicesPtr);
          goto LABEL_45;
        }
        v18 = L"UpdateGPCoreStatus: GetProcAddresss to ScrRegGPOListToWbem() in gpscript.dll failed, hr = 0x%x";
        goto LABEL_41;
      }
      WbemServicesPtr = ((__int64 (__fastcall *)(const unsigned __int16 *, struct IWbemServices *))ProcAddress)(a2, v24);
      if ( (WbemServicesPtr & 0x80000000) != 0 )
      {
        if ( !*(_DWORD *)&g_dwDebugLevel )
          goto LABEL_45;
        v17 = g_lpDebugMsg;
        if ( !g_lpDebugMsg )
        {
          if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
            RedirectDebugMsg(2u, L"UpdateGPCoreStatus: ScrRegGPOListToWbem failed, hr = 0x%x", WbemServicesPtr);
          goto LABEL_45;
        }
        v18 = L"UpdateGPCoreStatus: ScrRegGPOListToWbem failed, hr = 0x%x";
LABEL_41:
        v17(2u, v18, WbemServicesPtr);
LABEL_45:
        XHLibrary::~XHLibrary((XHLibrary *)&hModule);
LABEL_33:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
        goto LABEL_66;
      }
      XHLibrary::~XHLibrary((XHLibrary *)&hModule);
    }
    CExtSessionLogger::CExtSessionLogger((CExtSessionLogger *)v28, v24);
    if ( CExtSessionLogger::Set((CExtSessionLogger *)v28, v21, v22, (struct _RSOPEXTSTATUS *)v27) )
    {
      CExtSessionLogger::~CExtSessionLogger((CExtSessionLogger *)v28);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      WbemServicesPtr = 0;
    }
    else
    {
      CExtSessionLogger::~CExtSessionLogger((CExtSessionLogger *)v28);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      WbemServicesPtr = -2147467259;
    }
    goto LABEL_66;
  }
  v9 = GetLastError();
  WbemServicesPtr = v9;
  if ( v9 > 0 )
    WbemServicesPtr = (unsigned __int16)v9 | 0x80070000;
  if ( *(_DWORD *)&g_dwDebugLevel )
  {
    if ( g_lpDebugMsg )
    {
      g_lpDebugMsg(2u, L"UpdateGPCoreStatus: failed to allocate memory, 0x%x", WbemServicesPtr);
    }
    else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
    {
      RedirectDebugMsg(2u, L"UpdateGPCoreStatus: failed to allocate memory, 0x%x", WbemServicesPtr);
    }
  }
LABEL_66:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v26);
  return WbemServicesPtr;
}

```

## disassembly

```asm
0x1800ad5ec  mov     [rsp-8+arg_18], rbx
0x1800ad5f1  push    rbp
0x1800ad5f2  push    rsi
0x1800ad5f3  push    rdi
0x1800ad5f4  push    r14
0x1800ad5f6  push    r15
0x1800ad5f8  lea     rbp, [rsp-90h]
0x1800ad600  sub     rsp, 190h
0x1800ad607  mov     rax, cs:__security_cookie
0x1800ad60e  xor     rax, rsp
0x1800ad611  mov     [rbp+0B0h+var_30], rax
0x1800ad618  mov     rsi, r8
0x1800ad61b  mov     r14, rdx
0x1800ad61e  mov     [rsp+1B0h+hModule], rcx
0x1800ad623  xorps   xmm0, xmm0
0x1800ad626  movups  [rsp+1B0h+var_178], xmm0
0x1800ad62b  movups  [rsp+1B0h+var_178+0Ch], xmm0
0x1800ad630  xor     r15d, r15d
0x1800ad633  mov     [rsp+1B0h+var_180], r15
0x1800ad638  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ad63c  inc     rax
0x1800ad63f  cmp     [r8+rax*2], r15w
0x1800ad644  jnz     short loc_1800AD63C
0x1800ad646  lea     rdi, [rax+0Dh]
0x1800ad64a  lea     rdx, [rdi+rdi]; uBytes
0x1800ad64e  mov     ecx, 40h ; '@'; uFlags
0x1800ad653  call    cs:__imp_LocalAlloc
0x1800ad659  mov     rdx, rax
0x1800ad65c  lea     rcx, [rsp+1B0h+var_180]
0x1800ad661  call    ??4?$XPtrLF@G@@QEAAPEAGPEAG@Z; XPtrLF<ushort>::operator=(ushort *)
0x1800ad666  mov     rbx, [rsp+1B0h+var_180]
0x1800ad66b  test    rbx, rbx
0x1800ad66e  jnz     short loc_1800AD6EA
0x1800ad670  call    cs:__imp_GetLastError
0x1800ad676  mov     ebx, eax
0x1800ad678  test    eax, eax
0x1800ad67a  jle     short loc_1800AD685
0x1800ad67c  movzx   ebx, ax
0x1800ad67f  or      ebx, 80070000h
0x1800ad685  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800ad68c  jz      loc_1800ADA03
0x1800ad692  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800ad699  test    rax, rax
0x1800ad69c  jz      short loc_1800AD6B7
0x1800ad69e  mov     r8d, ebx
0x1800ad6a1  lea     rdx, aUpdategpcorest_4; "UpdateGPCoreStatus: failed to allocate "...
0x1800ad6a8  mov     ecx, 2
0x1800ad6ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad6b2  jmp     loc_1800ADA03
0x1800ad6b7  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800ad6be  jz      loc_1800ADA03
0x1800ad6c4  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800ad6cb  jz      loc_1800ADA03
0x1800ad6d1  mov     r8d, ebx
0x1800ad6d4  lea     rdx, aUpdategpcorest_4; "UpdateGPCoreStatus: failed to allocate "...
0x1800ad6db  mov     ecx, 2; unsigned int
0x1800ad6e0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800ad6e5  jmp     loc_1800ADA03
0x1800ad6ea  mov     r8, rsi; unsigned __int16 *
0x1800ad6ed  mov     rdx, rdi; unsigned __int64
0x1800ad6f0  mov     rcx, rbx; unsigned __int16 *
0x1800ad6f3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ad6f8  test    eax, eax
0x1800ad6fa  jns     short loc_1800AD703
0x1800ad6fc  mov     ebx, eax
0x1800ad6fe  jmp     loc_1800ADA03
0x1800ad703  mov     rcx, rbx; unsigned __int16 *
0x1800ad706  call    ?CheckSlash@@YAPEAGPEAG@Z; CheckSlash(ushort *)
0x1800ad70b  lea     rcx, aUser; "User"
0x1800ad712  lea     rsi, aComputer; "Computer"
0x1800ad719  test    r14, r14
0x1800ad71c  cmovnz  rsi, rcx
0x1800ad720  mov     rcx, rax
0x1800ad723  sub     rcx, rbx
0x1800ad726  sar     rcx, 1
0x1800ad729  sub     rdi, rcx
0x1800ad72c  mov     r8, rsi; unsigned __int16 *
0x1800ad72f  mov     rdx, rdi; unsigned __int64
0x1800ad732  mov     rcx, rax; unsigned __int16 *
0x1800ad735  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800ad73a  test    eax, eax
0x1800ad73c  js      short loc_1800AD6FC
0x1800ad73e  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800ad745  jz      short loc_1800AD78F
0x1800ad747  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800ad74e  test    rax, rax
0x1800ad751  jz      short loc_1800AD769
0x1800ad753  mov     r8, rsi
0x1800ad756  lea     rdx, aUpdategpcorest_1; "UpdateGPCoreStatus: updating status fro"...
0x1800ad75d  mov     ecx, 4
0x1800ad762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad767  jmp     short loc_1800AD78F
0x1800ad769  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800ad770  jz      short loc_1800AD78F
0x1800ad772  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800ad779  jz      short loc_1800AD78F
0x1800ad77b  mov     r8, rsi
0x1800ad77e  lea     rdx, aUpdategpcorest_1; "UpdateGPCoreStatus: updating status fro"...
0x1800ad785  mov     ecx, 4; unsigned int
0x1800ad78a  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800ad78f  xor     r9d, r9d; unsigned int *
0x1800ad792  lea     r8, [rsp+1B0h+var_178]; struct _RSOPEXTSTATUS *
0x1800ad797  mov     rcx, r14; unsigned __int16 *
0x1800ad79a  call    ?ReadLoggingStatusInternal@@YAKPEBG0PEAU_RSOPEXTSTATUS@@PEAK@Z; ReadLoggingStatusInternal(ushort const *,ushort const *,_RSOPEXTSTATUS *,ulong *)
0x1800ad79f  test    eax, eax
0x1800ad7a1  jz      short loc_1800AD7B6
0x1800ad7a3  jle     loc_1800AD6FC
0x1800ad7a9  movzx   eax, ax
0x1800ad7ac  or      eax, 80070000h
0x1800ad7b1  jmp     loc_1800AD6FC
0x1800ad7b6  mov     [rsp+1B0h+var_190], r15
0x1800ad7bb  lea     r8, [rsp+1B0h+var_190]
0x1800ad7c0  lea     rdx, [rsp+1B0h+hModule]
0x1800ad7c5  mov     rcx, rbx; unsigned __int16 *
0x1800ad7c8  call    GetWbemServicesPtr
0x1800ad7cd  mov     ebx, eax
0x1800ad7cf  test    eax, eax
0x1800ad7d1  jns     short loc_1800AD834
0x1800ad7d3  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800ad7da  jz      short loc_1800AD825
0x1800ad7dc  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800ad7e3  test    rax, rax
0x1800ad7e6  jz      short loc_1800AD7FE
0x1800ad7e8  mov     r8d, ebx
0x1800ad7eb  lea     rdx, aUpdategpcorest_0; "UpdateGPCoreStatus: GetWbemServicesPtr "...
0x1800ad7f2  mov     ecx, 2
0x1800ad7f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad7fc  jmp     short loc_1800AD825
0x1800ad7fe  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800ad805  jz      short loc_1800AD825
0x1800ad807  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800ad80e  jz      short loc_1800AD825
0x1800ad810  mov     r8d, ebx
0x1800ad813  lea     rdx, aUpdategpcorest_0; "UpdateGPCoreStatus: GetWbemServicesPtr "...
0x1800ad81a  mov     ecx, 2; unsigned int
0x1800ad81f  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800ad824  nop
0x1800ad825  lea     rcx, [rsp+1B0h+var_190]
0x1800ad82a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800ad82f  jmp     loc_1800ADA03
0x1800ad834  call    ?IsDomainIncapableSystem@CSKU@@SAHXZ; CSKU::IsDomainIncapableSystem(void)
0x1800ad839  test    eax, eax
0x1800ad83b  jnz     loc_1800AD9B0
0x1800ad841  mov     [rsp+1B0h+hModule], r15
0x1800ad846  xor     r8d, r8d; dwFlags
0x1800ad849  xor     edx, edx; hFile
0x1800ad84b  lea     rcx, aGpscriptDll; "gpscript.dll"
0x1800ad852  call    cs:__imp_LoadLibraryExW
0x1800ad858  mov     rdx, rax
0x1800ad85b  lea     rcx, [rsp+1B0h+hModule]
0x1800ad860  call    ??4XHLibrary@@QEAAXPEAUHINSTANCE__@@@Z; XHLibrary::operator=(HINSTANCE__ *)
0x1800ad865  mov     rcx, [rsp+1B0h+hModule]; hModule
0x1800ad86a  test    rcx, rcx
0x1800ad86d  jnz     short loc_1800AD8E5
0x1800ad86f  call    cs:__imp_GetLastError
0x1800ad875  mov     ebx, eax
0x1800ad877  test    eax, eax
0x1800ad879  jle     short loc_1800AD884
0x1800ad87b  movzx   ebx, ax
0x1800ad87e  or      ebx, 80070000h
0x1800ad884  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800ad88b  jz      short loc_1800AD8D6
0x1800ad88d  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800ad894  test    rax, rax
0x1800ad897  jz      short loc_1800AD8AF
0x1800ad899  lea     rdx, aUpdategpcorest_2; "UpdateGPCoreStatus: LoadLibraryEx of gp"...
0x1800ad8a0  mov     r8d, ebx
0x1800ad8a3  mov     ecx, 2
0x1800ad8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad8ad  jmp     short loc_1800AD8D6
0x1800ad8af  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800ad8b6  jz      short loc_1800AD8D6
0x1800ad8b8  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800ad8bf  jz      short loc_1800AD8D6
0x1800ad8c1  lea     rdx, aUpdategpcorest_2; "UpdateGPCoreStatus: LoadLibraryEx of gp"...
0x1800ad8c8  mov     r8d, ebx
0x1800ad8cb  mov     ecx, 2; unsigned int
0x1800ad8d0  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x1800ad8d5  nop
0x1800ad8d6  lea     rcx, [rsp+1B0h+hModule]; this
0x1800ad8db  call    ??1XHLibrary@@QEAA@XZ; XHLibrary::~XHLibrary(void)
0x1800ad8e0  jmp     loc_1800AD825
0x1800ad8e5  lea     rdx, aScrreggpolistt; "ScrRegGPOListToWbem"
0x1800ad8ec  call    cs:__imp_GetProcAddress
0x1800ad8f2  test    rax, rax
0x1800ad8f5  jnz     short loc_1800AD948
0x1800ad8f7  call    cs:__imp_GetLastError
0x1800ad8fd  mov     ebx, eax
0x1800ad8ff  test    eax, eax
0x1800ad901  jle     short loc_1800AD90C
0x1800ad903  movzx   ebx, ax
0x1800ad906  or      ebx, 80070000h
0x1800ad90c  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800ad913  jz      short loc_1800AD8D6
0x1800ad915  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800ad91c  test    rax, rax
0x1800ad91f  jz      short loc_1800AD92D
0x1800ad921  lea     rdx, aUpdategpcorest_3; "UpdateGPCoreStatus: GetProcAddresss to "...
0x1800ad928  jmp     loc_1800AD8A0
0x1800ad92d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800ad934  jz      short loc_1800AD8D6
0x1800ad936  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800ad93d  jz      short loc_1800AD8D6
0x1800ad93f  lea     rdx, aUpdategpcorest_3; "UpdateGPCoreStatus: GetProcAddresss to "...
0x1800ad946  jmp     short loc_1800AD8C8
0x1800ad948  mov     rdx, [rsp+1B0h+var_190]
0x1800ad94d  mov     rcx, r14
0x1800ad950  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ad955  mov     ebx, eax
0x1800ad957  test    eax, eax
0x1800ad959  jns     short loc_1800AD9A6
0x1800ad95b  cmp     cs:?g_dwDebugLevel@@3KA, r15d; ulong g_dwDebugLevel
0x1800ad962  jz      loc_1800AD8D6
0x1800ad968  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x1800ad96f  test    rax, rax
0x1800ad972  jz      short loc_1800AD980
0x1800ad974  lea     rdx, aUpdategpcorest; "UpdateGPCoreStatus: ScrRegGPOListToWbem"...
0x1800ad97b  jmp     loc_1800AD8A0
0x1800ad980  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r15; void * g_lpDebugMsgContextInstance
0x1800ad987  jz      loc_1800AD8D6
0x1800ad98d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r15; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x1800ad994  jz      loc_1800AD8D6
0x1800ad99a  lea     rdx, aUpdategpcorest; "UpdateGPCoreStatus: ScrRegGPOListToWbem"...
0x1800ad9a1  jmp     loc_1800AD8C8
0x1800ad9a6  lea     rcx, [rsp+1B0h+hModule]; this
0x1800ad9ab  call    ??1XHLibrary@@QEAA@XZ; XHLibrary::~XHLibrary(void)
0x1800ad9b0  mov     rdx, [rsp+1B0h+var_190]; struct IWbemServices *
0x1800ad9b5  lea     rcx, [rsp+1B0h+var_150]; this
0x1800ad9ba  call    ??0CExtSessionLogger@@QEAA@PEAUIWbemServices@@@Z; CExtSessionLogger::CExtSessionLogger(IWbemServices *)
0x1800ad9bf  nop
0x1800ad9c0  lea     r9, [rsp+1B0h+var_178]; struct _RSOPEXTSTATUS *
0x1800ad9c5  lea     rcx, [rsp+1B0h+var_150]; this
0x1800ad9ca  call    ?Set@CExtSessionLogger@@QEAAHPEAU_GPEXT@@HPEAU_RSOPEXTSTATUS@@@Z; CExtSessionLogger::Set(_GPEXT *,int,_RSOPEXTSTATUS *)
0x1800ad9cf  nop
0x1800ad9d0  lea     rcx, [rsp+1B0h+var_150]; this
0x1800ad9d5  test    eax, eax
0x1800ad9d7  jnz     short loc_1800AD9F0
0x1800ad9d9  call    ??1CExtSessionLogger@@QEAA@XZ; CExtSessionLogger::~CExtSessionLogger(void)
0x1800ad9de  nop
0x1800ad9df  lea     rcx, [rsp+1B0h+var_190]
0x1800ad9e4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800ad9e9  mov     ebx, 80004005h
0x1800ad9ee  jmp     short loc_1800ADA03
0x1800ad9f0  call    ??1CExtSessionLogger@@QEAA@XZ; CExtSessionLogger::~CExtSessionLogger(void)
0x1800ad9f5  nop
0x1800ad9f6  lea     rcx, [rsp+1B0h+var_190]
0x1800ad9fb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800ada00  mov     ebx, r15d
0x1800ada03  lea     rcx, [rsp+1B0h+var_180]
0x1800ada08  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x1800ada0d  mov     eax, ebx
0x1800ada0f  mov     rcx, [rbp+0B0h+var_30]
0x1800ada16  xor     rcx, rsp; StackCookie
0x1800ada19  call    __security_check_cookie
0x1800ada1e  mov     rbx, [rsp+1B0h+arg_18]
0x1800ada26  add     rsp, 190h
0x1800ada2d  pop     r15
0x1800ada2f  pop     r14
0x1800ada31  pop     rdi
0x1800ada32  pop     rsi
0x1800ada33  pop     rbp
0x1800ada34  retn
```
