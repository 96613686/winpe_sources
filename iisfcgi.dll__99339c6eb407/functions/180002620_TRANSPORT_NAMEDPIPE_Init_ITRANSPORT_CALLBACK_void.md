# TRANSPORT_NAMEDPIPE::Init(ITRANSPORT_CALLBACK *,void * *)

- ea: `0x180002620`
- end: `0x1800028ab`
- name: `?Init@TRANSPORT_NAMEDPIPE@@UEAAJPEAVITRANSPORT_CALLBACK@@PEAPEAX@Z`
- size: `651`
- prototype: `__int64 __fastcall(TRANSPORT_NAMEDPIPE *__hidden this, struct ITRANSPORT_CALLBACK *, void **)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002620`
- `0x18000ee10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002730`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800027fa`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800026e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000271f`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800026e5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18000271f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002822`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000282b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002839`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002848`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002857`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002822`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000282b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002839`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002848`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180002857`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800027e8`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800027e8`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180002788`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180002788`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800027c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800027c2`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800026aa`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800026aa`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800026bd`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800026bd`
- `RPCRT4!UuidToStringW` at `0x18000268f`
- `RPCRT4!UuidToStringW` at `0x18000268f`
- `RPCRT4!UuidCreate` at `0x180002673`
- `RPCRT4!UuidCreate` at `0x180002673`
- `RPCRT4!RpcStringFreeW` at `0x1800026c9`
- `RPCRT4!RpcStringFreeW` at `0x1800026c9`

## pseudocode

```c
__int64 __fastcall TRANSPORT_NAMEDPIPE::Init(TRANSPORT_NAMEDPIPE *this, struct ITRANSPORT_CALLBACK *a2, void **a3)
{
  signed int v4; // ebx
  HANDLE EventW; // r13
  signed int LastError; // eax
  __int64 v7; // r14
  HANDLE v8; // r12
  __int64 v9; // rdi
  signed int v10; // eax
  const WCHAR *v11; // rcx
  HANDLE FileW; // rax
  HANDLE IoCompletionPort; // r15
  signed int v14; // eax
  _QWORD *v15; // rax
  RPC_WSTR StringUuid; // [rsp+40h] [rbp-40h] BYREF
  void **v18; // [rsp+48h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+50h] [rbp-30h] BYREF
  UUID Uuid; // [rsp+68h] [rbp-18h] BYREF

  *a3 = (void *)-1LL;
  *((_QWORD *)this + 1) = a2;
  v18 = a3;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  StringUuid = 0;
  Uuid = 0;
  if ( UuidCreate(&Uuid) || UuidToStringW(&Uuid, &StringUuid) )
    return (unsigned int)-2147467259;
  v4 = STRU::Copy((TRANSPORT_NAMEDPIPE *)((char *)this + 160), L"\\\\.\\pipe\\IISFCGI-");
  if ( v4 >= 0 )
    v4 = STRU::Append((TRANSPORT_NAMEDPIPE *)((char *)this + 160), StringUuid);
  RpcStringFreeW(&StringUuid);
  if ( v4 >= 0 )
  {
    EventW = CreateEventW(0, 1, 0, 0);
    if ( !EventW )
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
      return (unsigned int)v4;
    }
    v7 = -1;
    v8 = CreateEventW(0, 1, 0, 0);
    if ( v8 )
    {
      v11 = (const WCHAR *)*((_QWORD *)this + 24);
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 1;
      v9 = (__int64)CreateNamedPipeW(v11, 0x40000003u, 0, 1u, 0x1000u, 0x1000u, 0, &SecurityAttributes);
      if ( v9 != -1 )
      {
        FileW = CreateFileW(*((LPCWSTR *)this + 24), 0xC0000000, 0, 0, 3u, 0x40000000u, 0);
        v7 = (__int64)FileW;
        if ( FileW != (HANDLE)-1LL )
        {
          IoCompletionPort = CreateIoCompletionPort(FileW, TRANSPORT::sm_hCompletionPort, 0xABCDDCBA, 0);
          if ( TRANSPORT::sm_hCompletionPort == IoCompletionPort )
          {
            v15 = v18;
            *((_QWORD *)this + 29) = EventW;
            *((_QWORD *)this + 30) = v8;
            *((_QWORD *)this + 27) = v9;
            *((_QWORD *)this + 28) = v7;
            *v15 = v9;
            return (unsigned int)v4;
          }
          v14 = GetLastError();
          v4 = v14;
          if ( v14 > 0 )
            v4 = (unsigned __int16)v14 | 0x80070000;
          if ( v4 >= 0 )
            v4 = -2147023483;
          if ( IoCompletionPort != (HANDLE)-1LL )
            CloseHandle(IoCompletionPort);
          goto LABEL_23;
        }
      }
    }
    else
    {
      v9 = -1;
    }
    v10 = GetLastError();
    v4 = v10;
    if ( v10 > 0 )
      v4 = (unsigned __int16)v10 | 0x80070000;
LABEL_23:
    CloseHandle(EventW);
    if ( v8 )
      CloseHandle(v8);
    if ( v9 != -1 )
      CloseHandle((HANDLE)v9);
    if ( v7 != -1 )
      CloseHandle((HANDLE)v7);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180002620  mov     [rsp-38h+arg_8], rbx
0x180002625  push    rbp
0x180002626  push    rsi
0x180002627  push    rdi
0x180002628  push    r12
0x18000262a  push    r13
0x18000262c  push    r14
0x18000262e  push    r15
0x180002630  mov     rbp, rsp
0x180002633  sub     rsp, 80h
0x18000263a  mov     rax, cs:__security_cookie
0x180002641  xor     rax, rsp
0x180002644  mov     [rbp+var_8], rax
0x180002648  xorps   xmm0, xmm0
0x18000264b  mov     qword ptr [r8], 0FFFFFFFFFFFFFFFFh
0x180002652  xor     eax, eax
0x180002654  mov     [rcx+8], rdx
0x180002658  mov     rsi, rcx
0x18000265b  mov     [rbp+var_38], r8
0x18000265f  lea     rcx, [rbp+Uuid]; Uuid
0x180002663  mov     qword ptr [rbp+SecurityAttributes.bInheritHandle], rax
0x180002667  movups  xmmword ptr [rbp+SecurityAttributes.nLength], xmm0
0x18000266b  mov     [rbp+StringUuid], rax
0x18000266f  movups  xmmword ptr [rbp+Uuid.Data1], xmm0
0x180002673  call    cs:__imp_UuidCreate
0x180002679  test    eax, eax
0x18000267b  jz      short loc_180002687
0x18000267d  mov     ebx, 80004005h
0x180002682  jmp     loc_180002882
0x180002687  lea     rdx, [rbp+StringUuid]; StringUuid
0x18000268b  lea     rcx, [rbp+Uuid]; Uuid
0x18000268f  call    cs:__imp_UuidToStringW
0x180002695  test    eax, eax
0x180002697  jnz     short loc_18000267D
0x180002699  lea     rdi, [rsi+0A0h]
0x1800026a0  mov     rcx, rdi
0x1800026a3  lea     rdx, aPipeIisfcgi; "\\\\.\\pipe\\IISFCGI-"
0x1800026aa  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800026b0  mov     ebx, eax
0x1800026b2  test    eax, eax
0x1800026b4  js      short loc_1800026C5
0x1800026b6  mov     rdx, [rbp+StringUuid]
0x1800026ba  mov     rcx, rdi
0x1800026bd  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800026c3  mov     ebx, eax
0x1800026c5  lea     rcx, [rbp+StringUuid]; String
0x1800026c9  call    cs:__imp_RpcStringFreeW
0x1800026cf  test    ebx, ebx
0x1800026d1  js      loc_180002882
0x1800026d7  xor     r9d, r9d; lpName
0x1800026da  xor     r8d, r8d; bInitialState
0x1800026dd  xor     ecx, ecx; lpEventAttributes
0x1800026df  lea     edi, [r9+1]
0x1800026e3  mov     edx, edi; bManualReset
0x1800026e5  call    cs:__imp_CreateEventW
0x1800026eb  mov     r13, rax
0x1800026ee  test    rax, rax
0x1800026f1  jnz     short loc_180002711
0x1800026f3  call    cs:__imp_GetLastError
0x1800026f9  mov     ebx, eax
0x1800026fb  test    eax, eax
0x1800026fd  jle     loc_180002882
0x180002703  movzx   ebx, ax
0x180002706  or      ebx, 80070000h
0x18000270c  jmp     loc_180002882
0x180002711  xor     r9d, r9d; lpName
0x180002714  xor     r8d, r8d; bInitialState
0x180002717  mov     edx, edi; bManualReset
0x180002719  xor     ecx, ecx; lpEventAttributes
0x18000271b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000271f  call    cs:__imp_CreateEventW
0x180002725  mov     r12, rax
0x180002728  test    rax, rax
0x18000272b  jnz     short loc_18000274E
0x18000272d  or      rdi, r14
0x180002730  call    cs:__imp_GetLastError
0x180002736  mov     ebx, eax
0x180002738  test    eax, eax
0x18000273a  jle     loc_180002828
0x180002740  movzx   ebx, ax
0x180002743  or      ebx, 80070000h
0x180002749  jmp     loc_180002828
0x18000274e  mov     rcx, [rsi+0C0h]; lpName
0x180002755  lea     rax, [rbp+SecurityAttributes]
0x180002759  mov     [rsp+80h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18000275e  mov     r9d, edi; nMaxInstances
0x180002761  mov     eax, 1000h
0x180002766  mov     [rsp+80h+nDefaultTimeOut], 0; nDefaultTimeOut
0x18000276e  mov     [rsp+80h+nInBufferSize], eax; nInBufferSize
0x180002772  xor     r8d, r8d; dwPipeMode
0x180002775  mov     edx, 40000003h; dwOpenMode
0x18000277a  mov     [rsp+80h+nOutBufferSize], eax; nOutBufferSize
0x18000277e  mov     [rbp+SecurityAttributes.nLength], 18h
0x180002785  mov     [rbp+SecurityAttributes.bInheritHandle], edi
0x180002788  call    cs:__imp_CreateNamedPipeW
0x18000278e  mov     rdi, rax
0x180002791  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180002795  jz      short loc_180002730
0x180002797  mov     rcx, [rsi+0C0h]; lpFileName
0x18000279e  xor     r9d, r9d; lpSecurityAttributes
0x1800027a1  mov     qword ptr [rsp+80h+nDefaultTimeOut], 0; hTemplateFile
0x1800027aa  xor     r8d, r8d; dwShareMode
0x1800027ad  mov     [rsp+80h+nInBufferSize], 40000000h; dwFlagsAndAttributes
0x1800027b5  mov     edx, 0C0000000h; dwDesiredAccess
0x1800027ba  mov     [rsp+80h+nOutBufferSize], 3; dwCreationDisposition
0x1800027c2  call    cs:__imp_CreateFileW
0x1800027c8  mov     r14, rax
0x1800027cb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800027cf  jz      loc_180002730
0x1800027d5  mov     rdx, cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA; ExistingCompletionPort
0x1800027dc  xor     r9d, r9d; NumberOfConcurrentThreads
0x1800027df  mov     r8d, 0ABCDDCBAh; CompletionKey
0x1800027e5  mov     rcx, rax; FileHandle
0x1800027e8  call    cs:__imp_CreateIoCompletionPort
0x1800027ee  cmp     cs:?sm_hCompletionPort@TRANSPORT@@1PEAXEA, rax; void * TRANSPORT::sm_hCompletionPort
0x1800027f5  mov     r15, rax
0x1800027f8  jz      short loc_18000285F
0x1800027fa  call    cs:__imp_GetLastError
0x180002800  mov     ebx, eax
0x180002802  test    eax, eax
0x180002804  jle     short loc_18000280F
0x180002806  movzx   ebx, ax
0x180002809  or      ebx, 80070000h
0x18000280f  test    ebx, ebx
0x180002811  mov     eax, 80070585h
0x180002816  cmovns  ebx, eax
0x180002819  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000281d  jz      short loc_180002828
0x18000281f  mov     rcx, r15; hObject
0x180002822  call    cs:__imp_CloseHandle
0x180002828  mov     rcx, r13; hObject
0x18000282b  call    cs:__imp_CloseHandle
0x180002831  test    r12, r12
0x180002834  jz      short loc_18000283F
0x180002836  mov     rcx, r12; hObject
0x180002839  call    cs:__imp_CloseHandle
0x18000283f  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180002843  jz      short loc_18000284E
0x180002845  mov     rcx, rdi; hObject
0x180002848  call    cs:__imp_CloseHandle
0x18000284e  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180002852  jz      short loc_180002882
0x180002854  mov     rcx, r14; hObject
0x180002857  call    cs:__imp_CloseHandle
0x18000285d  jmp     short loc_180002882
0x18000285f  mov     rax, [rbp+var_38]
0x180002863  mov     [rsi+0E8h], r13
0x18000286a  mov     [rsi+0F0h], r12
0x180002871  mov     [rsi+0D8h], rdi
0x180002878  mov     [rsi+0E0h], r14
0x18000287f  mov     [rax], rdi
0x180002882  mov     eax, ebx
0x180002884  mov     rcx, [rbp+var_8]
0x180002888  xor     rcx, rsp; StackCookie
0x18000288b  call    __security_check_cookie
0x180002890  mov     rbx, [rsp+80h+arg_8]
0x180002898  add     rsp, 80h
0x18000289f  pop     r15
0x1800028a1  pop     r14
0x1800028a3  pop     r13
0x1800028a5  pop     r12
0x1800028a7  pop     rdi
0x1800028a8  pop     rsi
0x1800028a9  pop     rbp
0x1800028aa  retn
```
