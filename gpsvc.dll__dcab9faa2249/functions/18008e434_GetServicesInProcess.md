# GetServicesInProcess

- ea: `0x18008e434`
- end: `0x18008e84a`
- name: `GetServicesInProcess`
- size: `1046`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18008d780`

## callees

- `0x18000a504`
- `0x18003d8d0`
- `0x180075ec0`
- `0x18008c444`
- `0x18008e434`
- `0x1800bf010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e605`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e605`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e636`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e78a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7c6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008e540`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18008e540`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008e46e`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x18008e46e`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18008e4cd`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18008e5e6`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18008e4cd`
- `api-ms-win-service-core-l1-1-1!EnumServicesStatusExW` at `0x18008e5e6`

## string_xrefs

- `0x18008e7fa`: `RPC Attribution: GetServicesInProcess - Invalid parameters`
- `0x18008e81f`: `RPC Attribution: GetServicesInProcess - Invalid parameters`
- `0x18008e793`: `RPC Attribution: Failed to open SCM, error=%lu`
- `0x18008e7cf`: `RPC Attribution: Failed to open SCM, error=%lu`
- `0x18008e4f3`: `RPC Attribution: No services found or enumeration returned zero buffer size`
- `0x18008e522`: `RPC Attribution: No services found or enumeration returned zero buffer size`
- `0x18008e56b`: `RPC Attribution: Failed to allocate memory for service enumeration`
- `0x18008e599`: `RPC Attribution: Failed to allocate memory for service enumeration`
- `0x18008e60e`: `RPC Attribution: EnumServicesStatusEx failed, error=%lu`
- `0x18008e63f`: `RPC Attribution: EnumServicesStatusEx failed, error=%lu`
- `0x18008e6cf`: `RPC Attribution: Service with PID %lu has NULL name`
- `0x18008e6f7`: `RPC Attribution: Service with PID %lu has NULL name`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall GetServicesInProcess(unsigned int a1, unsigned __int16 *a2, __int64 a3)
{
  SC_HANDLE v5; // rbx
  char *lpServices; // rsi
  void (*v7)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD v8; // eax
  DWORD v9; // eax
  unsigned int v10; // r15d
  int v11; // edx
  unsigned int v12; // ebx
  DWORD v13; // ecx
  __int64 v14; // r14
  const unsigned __int16 *v15; // r8
  void (*v17)(unsigned int, const unsigned __int16 *, ...); // rbx
  DWORD LastError; // eax
  DWORD v19; // eax
  SC_HANDLE v20; // [rsp+50h] [rbp-10h] BYREF
  void *v21; // [rsp+58h] [rbp-8h] BYREF
  DWORD ServicesReturned; // [rsp+A8h] [rbp+48h] BYREF
  __int64 pcbBytesNeeded; // [rsp+B0h] [rbp+50h] BYREF
  DWORD ResumeHandle; // [rsp+B8h] [rbp+58h] BYREF

  pcbBytesNeeded = a3;
  if ( !a2 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"RPC Attribution: GetServicesInProcess - Invalid parameters");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"RPC Attribution: GetServicesInProcess - Invalid parameters");
      }
    }
    return 0;
  }
  *a2 = 0;
  v5 = OpenSCManagerW(0, 0, 4u);
  v20 = v5;
  if ( !v5 )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v17 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        LastError = GetLastError();
        v17(2u, L"RPC Attribution: Failed to open SCM, error=%lu", LastError);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v19 = GetLastError();
        RedirectDebugMsg(2u, L"RPC Attribution: Failed to open SCM, error=%lu", v19);
      }
    }
    goto LABEL_25;
  }
  LODWORD(pcbBytesNeeded) = 0;
  ServicesReturned = 0;
  ResumeHandle = 0;
  EnumServicesStatusExW(
    v5,
    SC_ENUM_PROCESS_INFO,
    0x30u,
    1u,
    0,
    0,
    (LPDWORD)&pcbBytesNeeded,
    &ServicesReturned,
    &ResumeHandle,
    0);
  if ( !(_DWORD)pcbBytesNeeded )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"RPC Attribution: No services found or enumeration returned zero buffer size");
      }
      else if ( g_lpDebugMsgContextInstance )
      {
        if ( g_lpDebugMsgContext )
          RedirectDebugMsg(2u, L"RPC Attribution: No services found or enumeration returned zero buffer size");
      }
    }
    goto LABEL_25;
  }
  lpServices = (char *)LocalAlloc(0x40u, (unsigned int)pcbBytesNeeded);
  v21 = lpServices;
  if ( !lpServices )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      if ( g_lpDebugMsg )
      {
        g_lpDebugMsg(2u, L"RPC Attribution: Failed to allocate memory for service enumeration");
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        RedirectDebugMsg(2u, L"RPC Attribution: Failed to allocate memory for service enumeration");
      }
    }
LABEL_24:
    XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v21);
LABEL_25:
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
    return 0;
  }
  if ( !EnumServicesStatusExW(
          v5,
          SC_ENUM_PROCESS_INFO,
          0x30u,
          1u,
          (LPBYTE)lpServices,
          pcbBytesNeeded,
          (LPDWORD)&pcbBytesNeeded,
          &ServicesReturned,
          &ResumeHandle,
          0) )
  {
    if ( *(_DWORD *)&g_dwDebugLevel )
    {
      v7 = g_lpDebugMsg;
      if ( g_lpDebugMsg )
      {
        v8 = GetLastError();
        v7(2u, L"RPC Attribution: EnumServicesStatusEx failed, error=%lu", v8);
      }
      else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
      {
        v9 = GetLastError();
        RedirectDebugMsg(2u, L"RPC Attribution: EnumServicesStatusEx failed, error=%lu", v9);
      }
    }
    goto LABEL_24;
  }
  v10 = 0;
  v11 = 1;
  v12 = 0;
  v13 = ServicesReturned;
  if ( !ServicesReturned )
    goto LABEL_43;
  while ( 1 )
  {
    v14 = 56LL * v12;
    if ( *(_DWORD *)&lpServices[v14 + 44] == a1 )
      break;
LABEL_40:
    if ( ++v12 >= v13 )
      goto LABEL_43;
  }
  if ( v11 || (int)StringCchCatW(a2, 0x400u, L", ") >= 0 )
  {
    v15 = *(const unsigned __int16 **)&lpServices[v14];
    if ( !v15 )
    {
      if ( *(_DWORD *)&g_dwDebugLevel )
      {
        if ( g_lpDebugMsg )
        {
          g_lpDebugMsg(2u, L"RPC Attribution: Service with PID %lu has NULL name", a1);
        }
        else if ( g_lpDebugMsgContextInstance && g_lpDebugMsgContext )
        {
          RedirectDebugMsg(2u, L"RPC Attribution: Service with PID %lu has NULL name", a1);
        }
      }
      v15 = L"(unknown)";
    }
    if ( (int)StringCchCatW(a2, 0x400u, v15) >= 0 )
    {
      v11 = 0;
      v10 = 1;
      v13 = ServicesReturned;
      goto LABEL_40;
    }
  }
  StringCchCatW(a2, 0x400u, L"...");
LABEL_43:
  XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(&v21);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v20);
  return v10;
}

```

## disassembly

```asm
0x18008e434  mov     [rsp-38h+arg_0], rbx
0x18008e439  mov     [rsp-38h+arg_10], r8
0x18008e43e  push    rbp
0x18008e43f  push    rsi
0x18008e440  push    rdi
0x18008e441  push    r12
0x18008e443  push    r13
0x18008e445  push    r14
0x18008e447  push    r15
0x18008e449  mov     rbp, rsp
0x18008e44c  sub     rsp, 60h
0x18008e450  mov     rdi, rdx
0x18008e453  mov     r12d, ecx
0x18008e456  xor     r13d, r13d
0x18008e459  test    rdx, rdx
0x18008e45c  jz      loc_18008E7E5
0x18008e462  mov     [rdx], r13w
0x18008e466  xor     edx, edx; lpDatabaseName
0x18008e468  xor     ecx, ecx; lpMachineName
0x18008e46a  lea     r8d, [r13+4]; dwDesiredAccess
0x18008e46e  call    cs:__imp_OpenSCManagerW
0x18008e474  mov     rbx, rax
0x18008e477  mov     [rbp+var_10], rax
0x18008e47b  test    rax, rax
0x18008e47e  jz      loc_18008E771
0x18008e484  mov     dword ptr [rbp+arg_10], r13d
0x18008e488  mov     [rbp+ServicesReturned], r13d
0x18008e48c  mov     [rbp+ResumeHandle], r13d
0x18008e490  mov     [rsp+60h+pszGroupName], r13; pszGroupName
0x18008e495  lea     rax, [rbp+ResumeHandle]
0x18008e499  mov     [rsp+60h+lpResumeHandle], rax; lpResumeHandle
0x18008e49e  lea     rax, [rbp+ServicesReturned]
0x18008e4a2  mov     [rsp+60h+lpServicesReturned], rax; lpServicesReturned
0x18008e4a7  lea     rax, [rbp+arg_10]
0x18008e4ab  mov     [rsp+60h+pcbBytesNeeded], rax; pcbBytesNeeded
0x18008e4b0  mov     [rsp+60h+cbBufSize], r13d; cbBufSize
0x18008e4b5  mov     [rsp+60h+lpServices], r13; lpServices
0x18008e4ba  lea     r14d, [r13+1]
0x18008e4be  mov     r9d, r14d; dwServiceState
0x18008e4c1  lea     r15d, [r13+30h]
0x18008e4c5  mov     r8d, r15d; dwServiceType
0x18008e4c8  xor     edx, edx; InfoLevel
0x18008e4ca  mov     rcx, rbx; hSCManager
0x18008e4cd  call    cs:__imp_EnumServicesStatusExW
0x18008e4d3  mov     eax, dword ptr [rbp+arg_10]
0x18008e4d6  test    eax, eax
0x18008e4d8  jnz     short loc_18008E538
0x18008e4da  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e4e1  jz      loc_18008E65B
0x18008e4e7  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e4ee  test    rax, rax
0x18008e4f1  jz      short loc_18008E508
0x18008e4f3  lea     rdx, aRpcAttribution_11; "RPC Attribution: No services found or e"...
0x18008e4fa  lea     ecx, [r13+2]
0x18008e4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e503  jmp     loc_18008E65B
0x18008e508  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e50f  jz      loc_18008E65B
0x18008e515  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e51c  jz      loc_18008E65B
0x18008e522  lea     rdx, aRpcAttribution_11; "RPC Attribution: No services found or e"...
0x18008e529  mov     ecx, 2; unsigned int
0x18008e52e  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e533  jmp     loc_18008E65B
0x18008e538  mov     rdx, rax; uBytes
0x18008e53b  mov     ecx, 40h ; '@'; uFlags
0x18008e540  call    cs:__imp_LocalAlloc
0x18008e546  mov     rsi, rax
0x18008e549  mov     [rbp+var_8], rax
0x18008e54d  test    rax, rax
0x18008e550  jnz     short loc_18008E5AF
0x18008e552  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e559  jz      loc_18008E651
0x18008e55f  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e566  test    rax, rax
0x18008e569  jz      short loc_18008E57F
0x18008e56b  lea     rdx, aRpcAttribution_0; "RPC Attribution: Failed to allocate mem"...
0x18008e572  lea     ecx, [rsi+2]
0x18008e575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e57a  jmp     loc_18008E651
0x18008e57f  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e586  jz      loc_18008E651
0x18008e58c  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e593  jz      loc_18008E651
0x18008e599  lea     rdx, aRpcAttribution_0; "RPC Attribution: Failed to allocate mem"...
0x18008e5a0  mov     ecx, 2; unsigned int
0x18008e5a5  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e5aa  jmp     loc_18008E651
0x18008e5af  mov     eax, dword ptr [rbp+arg_10]
0x18008e5b2  mov     [rsp+60h+pszGroupName], r13; pszGroupName
0x18008e5b7  lea     rcx, [rbp+ResumeHandle]
0x18008e5bb  mov     [rsp+60h+lpResumeHandle], rcx; lpResumeHandle
0x18008e5c0  lea     rcx, [rbp+ServicesReturned]
0x18008e5c4  mov     [rsp+60h+lpServicesReturned], rcx; lpServicesReturned
0x18008e5c9  lea     rcx, [rbp+arg_10]
0x18008e5cd  mov     [rsp+60h+pcbBytesNeeded], rcx; pcbBytesNeeded
0x18008e5d2  mov     [rsp+60h+cbBufSize], eax; cbBufSize
0x18008e5d6  mov     [rsp+60h+lpServices], rsi; lpServices
0x18008e5db  mov     r9d, r14d; dwServiceState
0x18008e5de  mov     r8d, r15d; dwServiceType
0x18008e5e1  xor     edx, edx; InfoLevel
0x18008e5e3  mov     rcx, rbx; hSCManager
0x18008e5e6  call    cs:__imp_EnumServicesStatusExW
0x18008e5ec  test    eax, eax
0x18008e5ee  jnz     short loc_18008E669
0x18008e5f0  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e5f7  jz      short loc_18008E651
0x18008e5f9  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e600  test    rbx, rbx
0x18008e603  jz      short loc_18008E624
0x18008e605  call    cs:__imp_GetLastError
0x18008e60b  mov     r8d, eax
0x18008e60e  lea     rdx, aRpcAttribution; "RPC Attribution: EnumServicesStatusEx f"...
0x18008e615  mov     ecx, 2
0x18008e61a  mov     rax, rbx
0x18008e61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e622  jmp     short loc_18008E651
0x18008e624  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e62b  jz      short loc_18008E651
0x18008e62d  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e634  jz      short loc_18008E651
0x18008e636  call    cs:__imp_GetLastError
0x18008e63c  mov     r8d, eax
0x18008e63f  lea     rdx, aRpcAttribution; "RPC Attribution: EnumServicesStatusEx f"...
0x18008e646  mov     ecx, 2; unsigned int
0x18008e64b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e650  nop
0x18008e651  lea     rcx, [rbp+var_8]
0x18008e655  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18008e65a  nop
0x18008e65b  lea     rcx, [rbp+var_10]
0x18008e65f  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008e664  jmp     loc_18008E830
0x18008e669  mov     r15d, r13d
0x18008e66c  mov     edx, r14d
0x18008e66f  mov     ebx, r13d
0x18008e672  mov     ecx, [rbp+ServicesReturned]
0x18008e675  test    ecx, ecx
0x18008e677  jz      loc_18008E756
0x18008e67d  mov     eax, ebx
0x18008e67f  imul    r14, rax, 38h ; '8'
0x18008e683  cmp     [r14+rsi+2Ch], r12d
0x18008e688  jnz     loc_18008E730
0x18008e68e  test    edx, edx
0x18008e690  jnz     short loc_18008E6AE
0x18008e692  lea     r8, asc_1800D5190; ", "
0x18008e699  mov     edx, 400h; unsigned __int64
0x18008e69e  mov     rcx, rdi; unsigned __int16 *
0x18008e6a1  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008e6a6  test    eax, eax
0x18008e6a8  js      loc_18008E73C
0x18008e6ae  mov     r8, [r14+rsi]
0x18008e6b2  test    r8, r8
0x18008e6b5  jnz     short loc_18008E70F
0x18008e6b7  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e6be  jz      short loc_18008E708
0x18008e6c0  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e6c7  test    rax, rax
0x18008e6ca  jz      short loc_18008E6E2
0x18008e6cc  mov     r8d, r12d
0x18008e6cf  lea     rdx, aRpcAttribution_13; "RPC Attribution: Service with PID %lu h"...
0x18008e6d6  mov     ecx, 2
0x18008e6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e6e0  jmp     short loc_18008E708
0x18008e6e2  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e6e9  jz      short loc_18008E708
0x18008e6eb  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e6f2  jz      short loc_18008E708
0x18008e6f4  mov     r8d, r12d
0x18008e6f7  lea     rdx, aRpcAttribution_13; "RPC Attribution: Service with PID %lu h"...
0x18008e6fe  mov     ecx, 2; unsigned int
0x18008e703  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e708  lea     r8, aUnknown; "(unknown)"
0x18008e70f  mov     r14d, 400h
0x18008e715  mov     edx, r14d; unsigned __int64
0x18008e718  mov     rcx, rdi; unsigned __int16 *
0x18008e71b  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008e720  test    eax, eax
0x18008e722  js      short loc_18008E743
0x18008e724  mov     edx, r13d
0x18008e727  mov     r15d, 1
0x18008e72d  mov     ecx, [rbp+ServicesReturned]
0x18008e730  inc     ebx
0x18008e732  cmp     ebx, ecx
0x18008e734  jb      loc_18008E67D
0x18008e73a  jmp     short loc_18008E756
0x18008e73c  mov     edx, 400h
0x18008e741  jmp     short loc_18008E746
0x18008e743  mov     rdx, r14; unsigned __int64
0x18008e746  lea     r8, asc_1800D5198; "..."
0x18008e74d  mov     rcx, rdi; unsigned __int16 *
0x18008e750  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18008e755  nop
0x18008e756  lea     rcx, [rbp+var_8]
0x18008e75a  call    ??1?$XPtrLF@U_NOTIFYCONTEXT@@@@QEAA@XZ; XPtrLF<_NOTIFYCONTEXT>::~XPtrLF<_NOTIFYCONTEXT>(void)
0x18008e75f  nop
0x18008e760  lea     rcx, [rbp+var_10]
0x18008e764  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x18008e769  mov     eax, r15d
0x18008e76c  jmp     loc_18008E832
0x18008e771  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e778  jz      loc_18008E65B
0x18008e77e  mov     rbx, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e785  test    rbx, rbx
0x18008e788  jz      short loc_18008E7AC
0x18008e78a  call    cs:__imp_GetLastError
0x18008e790  mov     r8d, eax
0x18008e793  lea     rdx, aRpcAttribution_4; "RPC Attribution: Failed to open SCM, er"...
0x18008e79a  mov     ecx, 2
0x18008e79f  mov     rax, rbx
0x18008e7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e7a7  jmp     loc_18008E65B
0x18008e7ac  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e7b3  jz      loc_18008E65B
0x18008e7b9  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e7c0  jz      loc_18008E65B
0x18008e7c6  call    cs:__imp_GetLastError
0x18008e7cc  mov     r8d, eax
0x18008e7cf  lea     rdx, aRpcAttribution_4; "RPC Attribution: Failed to open SCM, er"...
0x18008e7d6  mov     ecx, 2; unsigned int
0x18008e7db  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e7e0  jmp     loc_18008E65B
0x18008e7e5  cmp     cs:?g_dwDebugLevel@@3KA, r13d; ulong g_dwDebugLevel
0x18008e7ec  jz      short loc_18008E830
0x18008e7ee  mov     rax, cs:?g_lpDebugMsg@@3P6AXIPEBGZZEA; void (*g_lpDebugMsg)(uint,ushort const *,...)
0x18008e7f5  test    rax, rax
0x18008e7f8  jz      short loc_18008E80D
0x18008e7fa  lea     rdx, aRpcAttribution_3; "RPC Attribution: GetServicesInProcess -"...
0x18008e801  mov     ecx, 2
0x18008e806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e80b  jmp     short loc_18008E830
0x18008e80d  cmp     cs:?g_lpDebugMsgContextInstance@@3PEAXEA, r13; void * g_lpDebugMsgContextInstance
0x18008e814  jz      short loc_18008E830
0x18008e816  cmp     cs:?g_lpDebugMsgContext@@3P6AXPEAXIPEBGPEAPEAD@ZEA, r13; void (*g_lpDebugMsgContext)(void *,uint,ushort const *,char * *)
0x18008e81d  jz      short loc_18008E830
0x18008e81f  lea     rdx, aRpcAttribution_3; "RPC Attribution: GetServicesInProcess -"...
0x18008e826  mov     ecx, 2; unsigned int
0x18008e82b  call    ?RedirectDebugMsg@@YAXIPEBGZZ; RedirectDebugMsg(uint,ushort const *,...)
0x18008e830  xor     eax, eax
0x18008e832  mov     rbx, [rsp+60h+arg_0]
0x18008e83a  add     rsp, 60h
0x18008e83e  pop     r15
0x18008e840  pop     r14
0x18008e842  pop     r13
0x18008e844  pop     r12
0x18008e846  pop     rdi
0x18008e847  pop     rsi
0x18008e848  pop     rbp
0x18008e849  retn
```
