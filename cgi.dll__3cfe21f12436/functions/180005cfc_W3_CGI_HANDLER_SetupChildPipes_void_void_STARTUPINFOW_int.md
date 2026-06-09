# W3_CGI_HANDLER::SetupChildPipes(void * *,void * *,_STARTUPINFOW *,int)

- ea: `0x180005cfc`
- end: `0x18000610b`
- name: `?SetupChildPipes@W3_CGI_HANDLER@@CAJPEAPEAX0PEAU_STARTUPINFOW@@H@Z`
- size: `1039`
- prototype: `__int64 __fastcall(void **, void **, struct _STARTUPINFOW *, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000337c`

## callees

- `0x180005cfc`
- `0x180006e52`
- `0x180006e90`
- `0x180008010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f6c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005f6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e54`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e1e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e31`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e43`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005e54`
- `RPCRT4!UuidToStringW` at `0x180005e9f`
- `RPCRT4!UuidToStringW` at `0x180005e9f`
- `RPCRT4!UuidCreate` at `0x180005dc4`
- `RPCRT4!UuidCreate` at `0x180005dc4`
- `RPCRT4!RpcStringFreeW` at `0x180005f0c`
- `RPCRT4!RpcStringFreeW` at `0x180005f19`
- `RPCRT4!RpcStringFreeW` at `0x180005f0c`
- `RPCRT4!RpcStringFreeW` at `0x180005f19`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180005f57`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180006065`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180005f57`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180006065`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006015`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800060dc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180006015`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800060dc`
- `iisutil!PuDbgPrint` at `0x180005e0f`
- `iisutil!PuDbgPrint` at `0x180005fe2`
- `iisutil!PuDbgPrint` at `0x180005e0f`
- `iisutil!PuDbgPrint` at `0x180005fe2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e62`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e6c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800060f4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800060fe`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e62`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180005e6c`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800060f4`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800060fe`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005eb8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005ee5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005eb8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005ee5`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005ecd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005efb`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005ecd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180005efb`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005d57`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005d7d`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005d57`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180005d7d`

## string_xrefs

- `0x180005e08`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180005fcf`: `servercommon\inetsrv\iis\iisrearc\iis70\cgi_handler\cgi_handler.cxx`
- `0x180005fd6`: `ThreadPoolBindIo failed, error %x\n`

## pseudocode

```c
__int64 __fastcall W3_CGI_HANDLER::SetupChildPipes(void **a1, void **a2, struct _STARTUPINFOW *a3, int a4)
{
  signed int v8; // ebx
  HANDLE hStdOutput; // rcx
  HANDLE hStdInput; // rcx
  HANDLE NamedPipeW; // rax
  signed int LastError; // eax
  int v14; // eax
  __int64 v15; // r8
  HANDLE v16; // rax
  HANDLE v17; // rax
  HANDLE v18; // rax
  RPC_WSTR StringUuid; // [rsp+40h] [rbp-C0h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+48h] [rbp-B8h] BYREF
  UUID Uuid; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v22[32]; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR lpFileName; // [rsp+90h] [rbp-70h]
  _BYTE v24[32]; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpName; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v26[128]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v27[128]; // [rsp+1E0h] [rbp+E0h] BYREF

  memset_0(v26, 0, sizeof(v26));
  STRU::STRU((STRU *)v24, v26, 0x80u);
  memset_0(v27, 0, sizeof(v27));
  STRU::STRU((STRU *)v22, v27, 0x80u);
  *(_QWORD *)&SecurityAttributes.nLength = 24;
  a3->hStdOutput = (HANDLE)-1LL;
  a3->hStdInput = (HANDLE)-1LL;
  Uuid = 0;
  *(_QWORD *)&SecurityAttributes.bInheritHandle = 1;
  SecurityAttributes.lpSecurityDescriptor = 0;
  a3->dwFlags = 256;
  StringUuid = 0;
  if ( UuidCreate(&Uuid) || UuidToStringW(&Uuid, &StringUuid) )
  {
    v8 = -2147467259;
    goto LABEL_3;
  }
  v8 = STRU::Copy((STRU *)v24, L"\\\\.\\pipe\\IISCGIStdout");
  if ( v8 < 0
    || (v8 = STRU::Append((STRU *)v24, StringUuid), v8 < 0)
    || (v8 = STRU::Copy((STRU *)v22, L"\\\\.\\pipe\\IISCGIStdin"), v8 < 0)
    || (v8 = STRU::Append((STRU *)v22, StringUuid), v8 < 0) )
  {
    RpcStringFreeW(&StringUuid);
    goto LABEL_3;
  }
  RpcStringFreeW(&StringUuid);
  NamedPipeW = CreateNamedPipeW(lpName, 0x40080001u, 0, 1u, 0x2000u, 0x2000u, 0xFFFFFFFF, 0);
  *a1 = NamedPipeW;
  if ( NamedPipeW == (HANDLE)-1LL )
  {
LABEL_22:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_3;
  }
  v14 = (*(__int64 (__fastcall **)(struct IHttpServer *, HANDLE, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *)))(*(_QWORD *)g_pGlobalInfo + 16LL))(
          g_pGlobalInfo,
          NamedPipeW,
          W3_CGI_HANDLER::OnPipeIoCompletion);
  v8 = v14;
  if ( v14 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      v15 = 590;
LABEL_27:
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
        v15,
        "W3_CGI_HANDLER::SetupChildPipes",
        "ThreadPoolBindIo failed, error %x\n",
        v14);
LABEL_3:
      if ( (g_dwDebugFlags & 3) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\cgi_handler\\cgi_handler.cxx",
          652,
          "W3_CGI_HANDLER::SetupChildPipes",
          "SetupChildPipes Failed, hr %x\n",
          v8);
      goto LABEL_5;
    }
    goto LABEL_5;
  }
  v16 = CreateFileW(lpName, 0x40000000u, 0, &SecurityAttributes, 3u, 0x40000000u, 0);
  a3->hStdOutput = v16;
  if ( v16 == (HANDLE)-1LL )
    goto LABEL_22;
  a3->hStdError = v16;
  if ( !a4 )
  {
LABEL_35:
    STRU::~STRU((STRU *)v22);
    STRU::~STRU((STRU *)v24);
    return 0;
  }
  v17 = CreateNamedPipeW(lpFileName, 0x40080002u, 0, 1u, 0x2000u, 0x2000u, 0xFFFFFFFF, 0);
  *a2 = v17;
  if ( v17 == (HANDLE)-1LL )
    goto LABEL_22;
  v14 = (*(__int64 (__fastcall **)(struct IHttpServer *, HANDLE, void (*)(unsigned int, unsigned int, struct _OVERLAPPED *)))(*(_QWORD *)g_pGlobalInfo + 16LL))(
          g_pGlobalInfo,
          v17,
          W3_CGI_HANDLER::OnPipeIoCompletion);
  v8 = v14;
  if ( v14 >= 0 )
  {
    v18 = CreateFileW(lpFileName, 0x80000000, 0, &SecurityAttributes, 3u, 0x40000000u, 0);
    a3->hStdInput = v18;
    if ( v18 == (HANDLE)-1LL )
      goto LABEL_22;
    goto LABEL_35;
  }
  if ( (g_dwDebugFlags & 3) != 0 )
  {
    v15 = 633;
    goto LABEL_27;
  }
LABEL_5:
  hStdOutput = a3->hStdOutput;
  if ( hStdOutput != (HANDLE)-1LL )
  {
    CloseHandle(hStdOutput);
    a3->hStdOutput = (HANDLE)-1LL;
  }
  hStdInput = a3->hStdInput;
  if ( hStdInput != (HANDLE)-1LL )
  {
    CloseHandle(hStdInput);
    a3->hStdInput = (HANDLE)-1LL;
  }
  if ( *a1 != (void *)-1LL )
  {
    CloseHandle(*a1);
    *a1 = (void *)-1LL;
  }
  if ( *a2 != (void *)-1LL )
  {
    CloseHandle(*a2);
    *a2 = (void *)-1LL;
  }
  STRU::~STRU((STRU *)v22);
  STRU::~STRU((STRU *)v24);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180005cfc  push    rbp
0x180005cfe  push    rbx
0x180005cff  push    rsi
0x180005d00  push    rdi
0x180005d01  push    r12
0x180005d03  push    r14
0x180005d05  push    r15
0x180005d07  lea     rbp, [rsp-1F0h]
0x180005d0f  sub     rsp, 2F0h
0x180005d16  mov     rax, cs:__security_cookie
0x180005d1d  xor     rax, rsp
0x180005d20  mov     [rbp+220h+var_40], rax
0x180005d27  mov     rdi, r8
0x180005d2a  mov     rsi, rdx
0x180005d2d  mov     r14, rcx
0x180005d30  mov     r12d, 100h
0x180005d36  mov     r8d, r12d; Size
0x180005d39  lea     rcx, [rbp+220h+var_240]; void *
0x180005d3d  xor     edx, edx; Val
0x180005d3f  mov     r15d, r9d
0x180005d42  call    memset_0
0x180005d47  lea     ebx, [r12-80h]
0x180005d4c  mov     r8d, ebx
0x180005d4f  lea     rdx, [rbp+220h+var_240]
0x180005d53  lea     rcx, [rbp+220h+var_278]
0x180005d57  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005d5d  mov     r8d, r12d; Size
0x180005d60  lea     rcx, [rbp+220h+var_140]; void *
0x180005d67  xor     edx, edx; Val
0x180005d69  call    memset_0
0x180005d6e  mov     r8d, ebx
0x180005d71  lea     rdx, [rbp+220h+var_140]
0x180005d78  lea     rcx, [rsp+320h+var_2B0]
0x180005d7d  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180005d83  or      rax, 0FFFFFFFFFFFFFFFFh
0x180005d87  mov     qword ptr [rsp+320h+SecurityAttributes.nLength], 18h
0x180005d90  xorps   xmm0, xmm0
0x180005d93  mov     [rdi+58h], rax
0x180005d97  lea     rcx, [rsp+320h+Uuid]; Uuid
0x180005d9c  mov     [rdi+50h], rax
0x180005da0  movups  xmmword ptr [rsp+320h+Uuid.Data1], xmm0
0x180005da5  mov     qword ptr [rsp+320h+SecurityAttributes.bInheritHandle], 1
0x180005dae  mov     [rsp+320h+SecurityAttributes.lpSecurityDescriptor], 0
0x180005db7  mov     [rdi+3Ch], r12d
0x180005dbb  mov     [rsp+320h+StringUuid], 0
0x180005dc4  call    cs:__imp_UuidCreate
0x180005dca  test    eax, eax
0x180005dcc  jz      loc_180005E95
0x180005dd2  mov     ebx, 80004005h
0x180005dd7  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005ddb  test    cs:g_dwDebugFlags, 3
0x180005de2  jz      short loc_180005E15
0x180005de4  mov     rcx, cs:g_pDebug
0x180005deb  lea     rax, aSetupchildpipe; "SetupChildPipes Failed, hr %x\n"
0x180005df2  mov     [rsp+320h+nInBufferSize], ebx
0x180005df6  lea     r9, aW3CgiHandlerSe; "W3_CGI_HANDLER::SetupChildPipes"
0x180005dfd  mov     r8d, 28Ch
0x180005e03  mov     qword ptr [rsp+320h+nOutBufferSize], rax
0x180005e08  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005e0f  call    cs:__imp_PuDbgPrint
0x180005e15  mov     rcx, [rdi+58h]; hObject
0x180005e19  cmp     rcx, r12
0x180005e1c  jz      short loc_180005E28
0x180005e1e  call    cs:__imp_CloseHandle
0x180005e24  mov     [rdi+58h], r12
0x180005e28  mov     rcx, [rdi+50h]; hObject
0x180005e2c  cmp     rcx, r12
0x180005e2f  jz      short loc_180005E3B
0x180005e31  call    cs:__imp_CloseHandle
0x180005e37  mov     [rdi+50h], r12
0x180005e3b  cmp     [r14], r12
0x180005e3e  jz      short loc_180005E4C
0x180005e40  mov     rcx, [r14]; hObject
0x180005e43  call    cs:__imp_CloseHandle
0x180005e49  mov     [r14], r12
0x180005e4c  cmp     [rsi], r12
0x180005e4f  jz      short loc_180005E5D
0x180005e51  mov     rcx, [rsi]; hObject
0x180005e54  call    cs:__imp_CloseHandle
0x180005e5a  mov     [rsi], r12
0x180005e5d  lea     rcx, [rsp+320h+var_2B0]
0x180005e62  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005e68  lea     rcx, [rbp+220h+var_278]
0x180005e6c  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180005e72  mov     eax, ebx
0x180005e74  mov     rcx, [rbp+220h+var_40]
0x180005e7b  xor     rcx, rsp; StackCookie
0x180005e7e  call    __security_check_cookie
0x180005e83  add     rsp, 2F0h
0x180005e8a  pop     r15
0x180005e8c  pop     r14
0x180005e8e  pop     r12
0x180005e90  pop     rdi
0x180005e91  pop     rsi
0x180005e92  pop     rbx
0x180005e93  pop     rbp
0x180005e94  retn
0x180005e95  lea     rdx, [rsp+320h+StringUuid]; StringUuid
0x180005e9a  lea     rcx, [rsp+320h+Uuid]; Uuid
0x180005e9f  call    cs:__imp_UuidToStringW
0x180005ea5  test    eax, eax
0x180005ea7  jnz     loc_180005DD2
0x180005ead  lea     rdx, aPipeIiscgistdo; "\\\\.\\pipe\\IISCGIStdout"
0x180005eb4  lea     rcx, [rbp+220h+var_278]
0x180005eb8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005ebe  mov     ebx, eax
0x180005ec0  test    eax, eax
0x180005ec2  js      short loc_180005F14
0x180005ec4  mov     rdx, [rsp+320h+StringUuid]
0x180005ec9  lea     rcx, [rbp+220h+var_278]
0x180005ecd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005ed3  mov     ebx, eax
0x180005ed5  test    eax, eax
0x180005ed7  js      short loc_180005F14
0x180005ed9  lea     rdx, aPipeIiscgistdi; "\\\\.\\pipe\\IISCGIStdin"
0x180005ee0  lea     rcx, [rsp+320h+var_2B0]
0x180005ee5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005eeb  mov     ebx, eax
0x180005eed  test    eax, eax
0x180005eef  js      short loc_180005F14
0x180005ef1  mov     rdx, [rsp+320h+StringUuid]
0x180005ef6  lea     rcx, [rsp+320h+var_2B0]
0x180005efb  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180005f01  mov     ebx, eax
0x180005f03  test    eax, eax
0x180005f05  js      short loc_180005F14
0x180005f07  lea     rcx, [rsp+320h+StringUuid]; String
0x180005f0c  call    cs:__imp_RpcStringFreeW
0x180005f12  jmp     short loc_180005F27
0x180005f14  lea     rcx, [rsp+320h+StringUuid]; String
0x180005f19  call    cs:__imp_RpcStringFreeW
0x180005f1f  test    ebx, ebx
0x180005f21  js      loc_180005DD7
0x180005f27  mov     rcx, [rbp+220h+lpName]; lpName
0x180005f2b  mov     eax, 2000h
0x180005f30  mov     [rsp+320h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180005f39  mov     r9d, 1; nMaxInstances
0x180005f3f  mov     [rsp+320h+nDefaultTimeOut], 0FFFFFFFFh; nDefaultTimeOut
0x180005f47  xor     r8d, r8d; dwPipeMode
0x180005f4a  mov     [rsp+320h+nInBufferSize], eax; nInBufferSize
0x180005f4e  mov     edx, 40080001h; dwOpenMode
0x180005f53  mov     [rsp+320h+nOutBufferSize], eax; nOutBufferSize
0x180005f57  call    cs:__imp_CreateNamedPipeW
0x180005f5d  or      r12, 0FFFFFFFFFFFFFFFFh
0x180005f61  mov     [r14], rax
0x180005f64  mov     rdx, rax
0x180005f67  cmp     rax, r12
0x180005f6a  jnz     short loc_180005F8A
0x180005f6c  call    cs:__imp_GetLastError
0x180005f72  mov     ebx, eax
0x180005f74  test    eax, eax
0x180005f76  jle     loc_180005DDB
0x180005f7c  movzx   ebx, ax
0x180005f7f  or      ebx, 80070000h
0x180005f85  jmp     loc_180005DDB
0x180005f8a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180005f91  lea     r8, ?OnPipeIoCompletion@W3_CGI_HANDLER@@CAXKKPEAU_OVERLAPPED@@@Z; W3_CGI_HANDLER::OnPipeIoCompletion(ulong,ulong,_OVERLAPPED *)
0x180005f98  mov     rax, [rcx]
0x180005f9b  mov     rax, [rax+10h]
0x180005f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fa4  mov     ebx, eax
0x180005fa6  test    eax, eax
0x180005fa8  jns     short loc_180005FED
0x180005faa  test    cs:g_dwDebugFlags, 3
0x180005fb1  jz      loc_180005E15
0x180005fb7  mov     r8d, 24Eh
0x180005fbd  mov     rcx, cs:g_pDebug
0x180005fc4  lea     r9, aW3CgiHandlerSe; "W3_CGI_HANDLER::SetupChildPipes"
0x180005fcb  mov     [rsp+320h+nInBufferSize], eax
0x180005fcf  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005fd6  lea     rax, aThreadpoolbind; "ThreadPoolBindIo failed, error %x\n"
0x180005fdd  mov     qword ptr [rsp+320h+nOutBufferSize], rax
0x180005fe2  call    cs:__imp_PuDbgPrint
0x180005fe8  jmp     loc_180005DDB
0x180005fed  mov     rcx, [rbp+220h+lpName]; lpFileName
0x180005ff1  lea     r9, [rsp+320h+SecurityAttributes]; lpSecurityAttributes
0x180005ff6  mov     eax, 40000000h
0x180005ffb  mov     qword ptr [rsp+320h+nDefaultTimeOut], 0; hTemplateFile
0x180006004  mov     [rsp+320h+nInBufferSize], eax; dwFlagsAndAttributes
0x180006008  mov     edx, eax; dwDesiredAccess
0x18000600a  xor     r8d, r8d; dwShareMode
0x18000600d  mov     [rsp+320h+nOutBufferSize], 3; dwCreationDisposition
0x180006015  call    cs:__imp_CreateFileW
0x18000601b  mov     [rdi+58h], rax
0x18000601f  cmp     rax, r12
0x180006022  jz      loc_180005F6C
0x180006028  mov     [rdi+60h], rax
0x18000602c  test    r15d, r15d
0x18000602f  jz      loc_1800060EF
0x180006035  mov     rcx, [rbp+220h+lpFileName]; lpName
0x180006039  mov     eax, 2000h
0x18000603e  mov     [rsp+320h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180006047  mov     r9d, 1; nMaxInstances
0x18000604d  mov     [rsp+320h+nDefaultTimeOut], 0FFFFFFFFh; nDefaultTimeOut
0x180006055  xor     r8d, r8d; dwPipeMode
0x180006058  mov     [rsp+320h+nInBufferSize], eax; nInBufferSize
0x18000605c  mov     edx, 40080002h; dwOpenMode
0x180006061  mov     [rsp+320h+nOutBufferSize], eax; nOutBufferSize
0x180006065  call    cs:__imp_CreateNamedPipeW
0x18000606b  mov     [rsi], rax
0x18000606e  mov     rdx, rax
0x180006071  cmp     rax, r12
0x180006074  jz      loc_180005F6C
0x18000607a  mov     rcx, cs:?g_pGlobalInfo@@3PEAVIHttpServer@@EA; IHttpServer * g_pGlobalInfo
0x180006081  lea     r8, ?OnPipeIoCompletion@W3_CGI_HANDLER@@CAXKKPEAU_OVERLAPPED@@@Z; W3_CGI_HANDLER::OnPipeIoCompletion(ulong,ulong,_OVERLAPPED *)
0x180006088  mov     rax, [rcx]
0x18000608b  mov     rax, [rax+10h]
0x18000608f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006094  mov     ebx, eax
0x180006096  test    eax, eax
0x180006098  jns     short loc_1800060B2
0x18000609a  test    cs:g_dwDebugFlags, 3
0x1800060a1  jz      loc_180005E15
0x1800060a7  mov     r8d, 279h
0x1800060ad  jmp     loc_180005FBD
0x1800060b2  mov     rcx, [rbp+220h+lpFileName]; lpFileName
0x1800060b6  lea     r9, [rsp+320h+SecurityAttributes]; lpSecurityAttributes
0x1800060bb  mov     qword ptr [rsp+320h+nDefaultTimeOut], 0; hTemplateFile
0x1800060c4  xor     r8d, r8d; dwShareMode
0x1800060c7  mov     [rsp+320h+nInBufferSize], 40000000h; dwFlagsAndAttributes
0x1800060cf  mov     edx, 80000000h; dwDesiredAccess
0x1800060d4  mov     [rsp+320h+nOutBufferSize], 3; dwCreationDisposition
0x1800060dc  call    cs:__imp_CreateFileW
0x1800060e2  mov     [rdi+50h], rax
0x1800060e6  cmp     rax, r12
0x1800060e9  jz      loc_180005F6C
0x1800060ef  lea     rcx, [rsp+320h+var_2B0]
0x1800060f4  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x1800060fa  lea     rcx, [rbp+220h+var_278]
0x1800060fe  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x180006104  xor     eax, eax
0x180006106  jmp     loc_180005E74
```
