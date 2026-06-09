# IPM2_MESSAGE_PIPE::MessagePipeCompletion(void *,uchar)

- ea: `0x180028630`
- end: `0x180028c93`
- name: `?MessagePipeCompletion@IPM2_MESSAGE_PIPE@@SAXPEAXE@Z`
- size: `1635`
- prototype: `void __fastcall(char *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004f40`
- `0x180007300`
- `0x18000e850`
- `0x180012820`
- `0x180016330`
- `0x180027b40`
- `0x180027e9c`
- `0x180027f7c`
- `0x180028630`
- `0x180028ca0`
- `0x180028ea8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002874d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002874d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800287d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b19`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180028744`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180028b0b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180028744`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180028b0b`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x1800289dd`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x1800289dd`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002865a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002865a`

## string_xrefs

- `0x180028916`: `Message length in the IPM header is smaller than the amount of data already read. This is unexpected.\n`
- `0x1800289af`: `********ERROR_MORE_DATA path, dwNumBytesTransferred=%d\n`
- `0x1800286b6`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800287a8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002883d`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800288a6`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002892f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002899e`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028a1a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028aaa`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028b77`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028c78`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028698`: `IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion called with pv = %p\n`
- `0x1800286a4`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002879d`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002882f`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x180028894`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002891d`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x180028990`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x180028a0c`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x180028a98`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x180028b69`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x180028c66`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002884e`: `IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion issuing read\n`
- `0x180028889`: `IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion ReadMessage failed hr=%x\n`
- `0x180028c5b`: `IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion disconnecting, hr=%x\n`

## pseudocode

```c
void __fastcall IPM2_MESSAGE_PIPE::MessagePipeCompletion(char *a1)
{
  void *v2; // rcx
  __int64 v3; // rsi
  void *v4; // rcx
  signed int FileChunked; // ebx
  int v6; // r14d
  BOOL OverlappedResult; // r15d
  signed int LastError; // eax
  int v9; // edx
  int v10; // edx
  int v11; // eax
  DWORD v12; // r15d
  int v13; // eax
  bool v14; // zf
  void **v15; // r15
  _DWORD *v16; // r13
  __int64 v17; // r12
  void *v18; // rcx
  BOOL v19; // eax
  int v20; // r8d
  BOOL v21; // ebx
  signed int v22; // eax
  __int64 v23; // rbx
  int File; // eax
  void *v25; // rcx
  int DataOk; // eax
  __int64 *v27; // rcx
  __int64 v28; // r8
  char lpBytesLeftThisMessage; // [rsp+28h] [rbp-18h]
  DWORD v30[4]; // [rsp+30h] [rbp-10h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+80h] [rbp+40h] BYREF
  DWORD BytesLeftThisMessage; // [rsp+90h] [rbp+50h] BYREF
  DWORD nNumberOfBytesToRead; // [rsp+98h] [rbp+58h]

  NumberOfBytesTransferred = 0;
  v2 = (void *)*((_QWORD *)a1 + 5);
  if ( v2 )
  {
    UnregisterWait(v2);
    *((_QWORD *)a1 + 5) = 0;
  }
  v3 = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)a1 + 48LL))(a1);
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x7C8u,
      "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
      "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion called with pv = %p\n",
      (char)a1);
  _InterlockedAdd((volatile signed __int32 *)(v3 + 76), 1u);
  if ( !*(_QWORD *)(v3 + 40) )
    goto LABEL_8;
  CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v3 + 8));
  v4 = *(void **)(v3 + 32);
  if ( v4 == (void *)-1LL )
  {
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v3 + 8));
    IPM2_MESSAGE_PIPE::NotifyPipeDisconnected((IPM2_MESSAGE_PIPE *)v3, -2147024787);
LABEL_8:
    (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
    goto LABEL_9;
  }
  nNumberOfBytesToRead = 0;
  FileChunked = 0;
  v6 = 0;
  OverlappedResult = GetOverlappedResult(v4, (LPOVERLAPPED)(a1 + 56), &NumberOfBytesTransferred, 0);
  LastError = GetLastError();
  v9 = *((_DWORD *)a1 + 3);
  if ( v9 )
  {
    v10 = v9 - 1;
    if ( v10 )
    {
      if ( v10 != 1 )
        goto LABEL_20;
      if ( OverlappedResult )
      {
        _InterlockedExchange((volatile __int32 *)(v3 + 88), 2);
        v11 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 40) + 8LL))(*(_QWORD *)(v3 + 40));
        FileChunked = v11;
        if ( v11 < 0 && (g_dwDebugFlagsIISUtil & 0xF) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
            0x800u,
            "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
            "Case IPM2_MESSAGE_IMP_CONNECT m_pAcceptor->PipeConnected failed hr=0x%08x\n",
            v11);
        nNumberOfBytesToRead = 32;
        goto LABEL_20;
      }
    }
    else if ( OverlappedResult )
    {
      goto LABEL_20;
    }
    v6 = 1;
    LastError = GetLastError();
    FileChunked = LastError;
    if ( LastError > 0 )
LABEL_19:
      FileChunked = (unsigned __int16)LastError | 0x80070000;
LABEL_20:
    CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v3 + 8));
    v12 = nNumberOfBytesToRead;
    goto LABEL_21;
  }
  if ( OverlappedResult )
  {
    if ( NumberOfBytesTransferred >= 0x10 )
    {
      *((_DWORD *)a1 + 4) = NumberOfBytesTransferred;
      v15 = (void **)(a1 + 24);
      goto LABEL_33;
    }
    FileChunked = -2147024885;
LABEL_39:
    v6 = 1;
    goto LABEL_20;
  }
  if ( LastError != 234 )
  {
    v6 = 1;
    if ( LastError <= 0 )
    {
      FileChunked = LastError;
      goto LABEL_20;
    }
    goto LABEL_19;
  }
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x83Eu,
      "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
      "********ERROR_MORE_DATA path, dwNumBytesTransferred=%d\n",
      NumberOfBytesTransferred);
  v18 = *(void **)(v3 + 32);
  BytesLeftThisMessage = 0;
  v19 = PeekNamedPipe(v18, 0, 0, 0, 0, &BytesLeftThisMessage);
  v20 = g_dwDebugFlagsIISUtil;
  v21 = v19;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
  {
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x84Bu,
      "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
      "********dwRemaining = %d\n",
      BytesLeftThisMessage);
    v20 = g_dwDebugFlagsIISUtil;
  }
  if ( !v21 )
  {
LABEL_46:
    v22 = GetLastError();
    FileChunked = v22;
    if ( v22 > 0 )
      FileChunked = (unsigned __int16)v22 | 0x80070000;
    goto LABEL_39;
  }
  v23 = NumberOfBytesTransferred + BytesLeftThisMessage;
  if ( NumberOfBytesTransferred + (unsigned __int64)BytesLeftThisMessage != v23 )
  {
    FileChunked = -2147024362;
    goto LABEL_39;
  }
  if ( (v20 & 3) != 0 && (v20 & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x863u,
      "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
      "********reallocating size = %d\n",
      NumberOfBytesTransferred + BytesLeftThisMessage);
  FileChunked = IPM2_MESSAGE_IMP::Reallocate((IPM2_MESSAGE_IMP *)a1, v23);
  if ( FileChunked < 0 )
    goto LABEL_39;
  v15 = (void **)(a1 + 24);
  File = Ipm2ReadFile(
           *(HANDLE *)(v3 + 32),
           (void *)(*((_QWORD *)a1 + 3) + NumberOfBytesTransferred),
           BytesLeftThisMessage,
           (LPOVERLAPPED)(a1 + 56));
  FileChunked = File;
  if ( File < 0 )
  {
    if ( File != -2147023899 )
      goto LABEL_39;
    v25 = *(void **)(v3 + 32);
    v30[0] = 0;
    if ( !GetOverlappedResult(v25, (LPOVERLAPPED)(a1 + 56), v30, 1) )
    {
      if ( !GetLastError() )
      {
        FileChunked = -2147467259;
        goto LABEL_39;
      }
      goto LABEL_46;
    }
  }
LABEL_33:
  v16 = *v15;
  v17 = *((unsigned int *)*v15 + 1);
  BytesLeftThisMessage = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)a1 + 24LL))(a1) + 16;
  if ( (unsigned int)v17 < BytesLeftThisMessage )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
        0x8ACu,
        "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
        "Message length in the IPM header is smaller than the amount of data already read. This is unexpected.\n",
        lpBytesLeftThisMessage);
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(v3 + 40) + 32LL))(*(_QWORD *)(v3 + 40));
    FileChunked = -2089418750;
LABEL_37:
    v6 = 1;
    goto LABEL_20;
  }
  if ( v17 != (*(unsigned int (__fastcall **)(char *))(*(_QWORD *)a1 + 24LL))(a1) + 16LL )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
        0x8BDu,
        "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
        "******** Chunked reallocating size = %d\n",
        v16[1]);
    FileChunked = IPM2_MESSAGE_IMP::Reallocate((IPM2_MESSAGE_IMP *)a1, v17);
    if ( FileChunked < 0 )
      goto LABEL_37;
    v16 = *v15;
    FileChunked = Ipm2ReadFileChunked(
                    *(void **)(v3 + 32),
                    *v15,
                    *((_DWORD *)*v15 + 1),
                    BytesLeftThisMessage,
                    (struct _OVERLAPPED *)(a1 + 56));
    if ( FileChunked < 0 )
      goto LABEL_37;
  }
  CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v3 + 8));
  DataOk = IsReadDataOk((struct IPM2_MESSAGE_IMP *)a1, v16[1], *(_DWORD *)(v3 + 48));
  v27 = *(__int64 **)(v3 + 40);
  v28 = *v27;
  if ( DataOk )
  {
    (*(void (__fastcall **)(__int64 *, char *))v28)(v27, a1);
    v12 = 32;
  }
  else
  {
    (*(void (**)(void))(v28 + 32))();
    v12 = 0;
  }
LABEL_21:
  (*(void (__fastcall **)(char *))(*(_QWORD *)a1 + 8LL))(a1);
  if ( *(_DWORD *)(v3 + 88) != 2 )
    goto LABEL_9;
  if ( !v12 )
    goto LABEL_68;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x914u,
      "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
      "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion issuing read\n",
      NumberOfBytesTransferred);
  FileChunked = IPM2_MESSAGE_PIPE::ReadMessage((IPM2_MESSAGE_PIPE *)v3, v12);
  if ( FileChunked >= 0 )
  {
LABEL_68:
    if ( !v6 )
      goto LABEL_9;
    goto LABEL_69;
  }
  v13 = g_dwDebugFlagsIISUtil;
  v14 = (g_dwDebugFlagsIISUtil & 3) == 0;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
  {
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x91Fu,
      "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
      "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion ReadMessage failed hr=%x\n",
      FileChunked);
LABEL_69:
    v13 = g_dwDebugFlagsIISUtil;
    v14 = (g_dwDebugFlagsIISUtil & 3) == 0;
  }
  if ( !v14 && (v13 & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x92Eu,
      "IPM2_MESSAGE_PIPE::MessagePipeCompletion",
      "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion disconnecting, hr=%x\n",
      FileChunked);
  IPM2_MESSAGE_PIPE::NotifyPipeDisconnected((IPM2_MESSAGE_PIPE *)v3, FileChunked);
LABEL_9:
  IPM2_MESSAGE_PIPE::DecrementAcceptorInUse((IPM2_MESSAGE_PIPE *)v3);
}

```

## disassembly

```asm
0x180028630  mov     [rsp-38h+arg_8], rbx
0x180028635  push    rbp
0x180028636  push    rsi
0x180028637  push    rdi
0x180028638  push    r12
0x18002863a  push    r13
0x18002863c  push    r14
0x18002863e  push    r15
0x180028640  mov     rbp, rsp
0x180028643  sub     rsp, 40h
0x180028647  mov     rdi, rcx
0x18002864a  mov     [rbp+NumberOfBytesTransferred], 0
0x180028651  mov     rcx, [rcx+28h]; WaitHandle
0x180028655  test    rcx, rcx
0x180028658  jz      short loc_180028668
0x18002865a  call    cs:__imp_UnregisterWait
0x180028660  mov     qword ptr [rdi+28h], 0
0x180028668  mov     rax, [rdi]
0x18002866b  mov     rcx, rdi
0x18002866e  mov     rax, [rax+30h]
0x180028672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028677  mov     ecx, cs:g_dwDebugFlagsIISUtil
0x18002867d  mov     rsi, rax
0x180028680  test    cl, 3
0x180028683  setnz   dl
0x180028686  bt      ecx, 1Ch
0x18002868a  setb    cl
0x18002868d  test    cl, dl
0x18002868f  jz      short loc_1800286C2
0x180028691  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028698  lea     rax, aIpm2MessagePip_0; "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECom"...
0x18002869f  mov     [rsp+40h+lpBytesLeftThisMessage], rdi; char
0x1800286a4  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x1800286ab  mov     r8d, 7C8h; unsigned int
0x1800286b1  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x1800286b6  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800286bd  call    PuDbgPrint
0x1800286c2  mov     r13d, 1
0x1800286c8  lock add [rsi+4Ch], r13d
0x1800286cd  cmp     qword ptr [rsi+28h], 0
0x1800286d2  jz      short loc_1800286FD
0x1800286d4  lea     rcx, [rsi+8]; this
0x1800286d8  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800286dd  mov     rcx, [rsi+20h]; hFile
0x1800286e1  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800286e5  jnz     short loc_18002872C
0x1800286e7  lea     rcx, [rsi+8]; this
0x1800286eb  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800286f0  mov     edx, 8007006Dh; int
0x1800286f5  mov     rcx, rsi; this
0x1800286f8  call    ?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x1800286fd  mov     rax, [rdi]
0x180028700  mov     rcx, rdi
0x180028703  mov     rax, [rax+8]
0x180028707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002870c  mov     rcx, rsi; this
0x18002870f  call    ?DecrementAcceptorInUse@IPM2_MESSAGE_PIPE@@AEAAXXZ; IPM2_MESSAGE_PIPE::DecrementAcceptorInUse(void)
0x180028714  mov     rbx, [rsp+40h+arg_8]
0x18002871c  add     rsp, 40h
0x180028720  pop     r15
0x180028722  pop     r14
0x180028724  pop     r13
0x180028726  pop     r12
0x180028728  pop     rdi
0x180028729  pop     rsi
0x18002872a  pop     rbp
0x18002872b  retn
0x18002872c  xor     eax, eax
0x18002872e  lea     r12, [rdi+38h]
0x180028732  mov     rdx, r12; lpOverlapped
0x180028735  mov     [rbp+nNumberOfBytesToRead], eax
0x180028738  xor     r9d, r9d; bWait
0x18002873b  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002873f  xor     ebx, ebx
0x180028741  xor     r14d, r14d
0x180028744  call    cs:__imp_GetOverlappedResult
0x18002874a  mov     r15d, eax
0x18002874d  call    cs:__imp_GetLastError
0x180028753  mov     edx, [rdi+0Ch]
0x180028756  test    edx, edx
0x180028758  jz      loc_1800288C5
0x18002875e  sub     edx, r13d
0x180028761  jz      loc_1800288B7
0x180028767  cmp     edx, r13d
0x18002876a  jnz     short loc_1800287E7
0x18002876c  test    r15d, r15d
0x18002876f  jz      short loc_1800287CF
0x180028771  lea     eax, [rbx+2]
0x180028774  xchg    eax, [rsi+58h]
0x180028777  mov     rcx, [rsi+28h]
0x18002877b  mov     rax, [rcx]
0x18002877e  mov     rax, [rax+8]
0x180028782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028787  mov     ebx, eax
0x180028789  test    eax, eax
0x18002878b  jns     short loc_1800287C6
0x18002878d  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180028794  jz      short loc_1800287C6
0x180028796  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002879d  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x1800287a4  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], eax; char
0x1800287a8  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800287af  lea     rax, aCaseIpm2Messag; "Case IPM2_MESSAGE_IMP_CONNECT m_pAccept"...
0x1800287b6  mov     r8d, 800h; unsigned int
0x1800287bc  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x1800287c1  call    PuDbgPrint
0x1800287c6  mov     [rbp+nNumberOfBytesToRead], 20h ; ' '
0x1800287cd  jmp     short loc_1800287E7
0x1800287cf  mov     r14d, r13d
0x1800287d2  call    cs:__imp_GetLastError
0x1800287d8  mov     ebx, eax
0x1800287da  test    eax, eax
0x1800287dc  jle     short loc_1800287E7
0x1800287de  movzx   ebx, ax
0x1800287e1  or      ebx, 80070000h
0x1800287e7  lea     rcx, [rsi+8]; this
0x1800287eb  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800287f0  mov     r15d, [rbp+nNumberOfBytesToRead]
0x1800287f4  mov     rax, [rdi]
0x1800287f7  mov     rcx, rdi
0x1800287fa  mov     rax, [rax+8]
0x1800287fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028803  cmp     dword ptr [rsi+58h], 2
0x180028807  jnz     loc_18002870C
0x18002880d  test    r15d, r15d
0x180028810  jz      loc_180028C35
0x180028816  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002881c  test    al, 3
0x18002881e  setnz   cl
0x180028821  bt      eax, 1Ch
0x180028825  setb    al
0x180028828  test    al, cl
0x18002882a  jz      short loc_18002885F
0x18002882c  mov     eax, [rbp+NumberOfBytesTransferred]
0x18002882f  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x180028836  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002883d  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028844  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], eax; char
0x180028848  mov     r8d, 914h; unsigned int
0x18002884e  lea     rax, aIpm2MessagePip_1; "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECom"...
0x180028855  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002885a  call    PuDbgPrint
0x18002885f  mov     edx, r15d; nNumberOfBytesToRead
0x180028862  mov     rcx, rsi; this
0x180028865  call    ?ReadMessage@IPM2_MESSAGE_PIPE@@AEAAJK@Z; IPM2_MESSAGE_PIPE::ReadMessage(ulong)
0x18002886a  mov     ebx, eax
0x18002886c  test    eax, eax
0x18002886e  jns     loc_180028C35
0x180028874  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002887a  test    al, 3
0x18002887c  jz      loc_180028C46
0x180028882  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028889  lea     rax, aIpm2MessagePip_34; "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECom"...
0x180028890  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], ebx; char
0x180028894  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002889b  mov     r8d, 91Fh; unsigned int
0x1800288a1  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x1800288a6  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800288ad  call    PuDbgPrint
0x1800288b2  jmp     loc_180028C3E
0x1800288b7  test    r15d, r15d
0x1800288ba  jnz     loc_1800287E7
0x1800288c0  jmp     loc_1800287CF
0x1800288c5  test    r15d, r15d
0x1800288c8  jz      loc_180028968
0x1800288ce  mov     eax, [rbp+NumberOfBytesTransferred]
0x1800288d1  cmp     eax, 10h
0x1800288d4  jb      loc_18002895B
0x1800288da  mov     [rdi+10h], eax
0x1800288dd  lea     r15, [rdi+18h]
0x1800288e1  mov     rax, [rdi]
0x1800288e4  mov     rcx, rdi
0x1800288e7  mov     r13, [r15]
0x1800288ea  mov     rax, [rax+18h]
0x1800288ee  mov     r12d, [r13+4]
0x1800288f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800288f7  add     eax, 10h
0x1800288fa  mov     [rbp+BytesLeftThisMessage], eax
0x1800288fd  cmp     r12d, eax
0x180028900  jnb     loc_180028B31
0x180028906  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002890d  jz      short loc_18002893B
0x18002890f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028916  lea     rax, aMessageLengthI; "Message length in the IPM header is sma"...
0x18002891d  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x180028924  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x180028929  mov     r8d, 8ACh; unsigned int
0x18002892f  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028936  call    PuDbgPrint
0x18002893b  mov     rcx, [rsi+28h]
0x18002893f  mov     rax, [rcx]
0x180028942  mov     rax, [rax+20h]
0x180028946  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002894b  mov     ebx, 83760002h
0x180028950  mov     r14d, 1
0x180028956  jmp     loc_1800287E7
0x18002895b  mov     ebx, 8007000Bh
0x180028960  mov     r14d, r13d
0x180028963  jmp     loc_1800287E7
0x180028968  cmp     eax, 0EAh
0x18002896d  jnz     loc_180028C23
0x180028973  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180028979  mov     r15b, 3
0x18002897c  test    r15b, al
0x18002897f  setnz   cl
0x180028982  bt      eax, 1Ch
0x180028986  setb    al
0x180028989  test    al, cl
0x18002898b  jz      short loc_1800289C0
0x18002898d  mov     eax, [rbp+NumberOfBytesTransferred]
0x180028990  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x180028997  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002899e  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800289a5  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], eax; char
0x1800289a9  mov     r8d, 83Eh; unsigned int
0x1800289af  lea     rax, aErrorMoreDataP; "********ERROR_MORE_DATA path, dwNumByte"...
0x1800289b6  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x1800289bb  call    PuDbgPrint
0x1800289c0  mov     rcx, [rsi+20h]; hNamedPipe
0x1800289c4  lea     rax, [rbp+BytesLeftThisMessage]
0x1800289c8  mov     [rsp+40h+lpBytesLeftThisMessage], rax; lpBytesLeftThisMessage
0x1800289cd  xor     r9d, r9d; lpBytesRead
0x1800289d0  xor     r8d, r8d; nBufferSize
0x1800289d3  mov     [rsp+40h+lpTotalBytesAvail], rbx; lpTotalBytesAvail
0x1800289d8  xor     edx, edx; lpBuffer
0x1800289da  mov     [rbp+BytesLeftThisMessage], ebx
0x1800289dd  call    cs:__imp_PeekNamedPipe
0x1800289e3  mov     r8d, cs:g_dwDebugFlagsIISUtil
0x1800289ea  test    r15b, r8b
0x1800289ed  mov     ebx, eax
0x1800289ef  setnz   dl
0x1800289f2  bt      r8d, 1Ch
0x1800289f7  setb    cl
0x1800289fa  test    cl, dl
0x1800289fc  jz      short loc_180028A38
0x1800289fe  mov     ecx, [rbp+BytesLeftThisMessage]
0x180028a01  lea     rax, aDwremainingD; "********dwRemaining = %d\n"
0x180028a08  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], ecx; char
0x180028a0c  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x180028a13  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028a1a  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028a21  mov     r8d, 84Bh; unsigned int
0x180028a27  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x180028a2c  call    PuDbgPrint
0x180028a31  mov     r8d, cs:g_dwDebugFlagsIISUtil
0x180028a38  test    ebx, ebx
0x180028a3a  jnz     short loc_180028A5A
0x180028a3c  call    cs:__imp_GetLastError
0x180028a42  mov     ebx, eax
0x180028a44  test    eax, eax
0x180028a46  jle     loc_180028960
0x180028a4c  movzx   ebx, ax
0x180028a4f  or      ebx, 80070000h
0x180028a55  jmp     loc_180028960
0x180028a5a  mov     edx, [rbp+BytesLeftThisMessage]
0x180028a5d  mov     eax, [rbp+NumberOfBytesTransferred]
0x180028a60  add     rdx, rax
0x180028a63  mov     ebx, edx
0x180028a65  cmp     rdx, rbx
0x180028a68  jz      short loc_180028A74
0x180028a6a  mov     ebx, 80070216h
0x180028a6f  jmp     loc_180028960
0x180028a74  test    r15b, r8b
0x180028a77  setnz   cl
0x180028a7a  bt      r8d, 1Ch
0x180028a7f  setb    al
0x180028a82  test    al, cl
0x180028a84  jz      short loc_180028AB6
0x180028a86  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028a8d  lea     rax, aReallocatingSi; "********reallocating size = %d\n"
0x180028a94  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], ebx; char
0x180028a98  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x180028a9f  mov     r8d, 863h; unsigned int
0x180028aa5  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x180028aaa  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028ab1  call    PuDbgPrint
0x180028ab6  mov     edx, ebx; unsigned int
0x180028ab8  mov     rcx, rdi; this
0x180028abb  call    ?Reallocate@IPM2_MESSAGE_IMP@@QEAAJK@Z; IPM2_MESSAGE_IMP::Reallocate(ulong)
0x180028ac0  mov     ebx, eax
0x180028ac2  test    eax, eax
0x180028ac4  js      loc_180028960
0x180028aca  mov     edx, [rbp+NumberOfBytesTransferred]
0x180028acd  lea     r15, [rdi+18h]
0x180028ad1  add     rdx, [r15]; lpBuffer
0x180028ad4  mov     r9, r12; lpOverlapped
0x180028ad7  mov     r8d, [rbp+BytesLeftThisMessage]; nNumberOfBytesToRead
0x180028adb  mov     rcx, [rsi+20h]; hFile
0x180028adf  call    ?Ipm2ReadFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2ReadFile(void *,void *,ulong,_OVERLAPPED *)
0x180028ae4  mov     ebx, eax
0x180028ae6  test    eax, eax
0x180028ae8  jns     loc_1800288E1
0x180028aee  cmp     eax, 800703E5h
0x180028af3  jnz     loc_180028960
0x180028af9  mov     rcx, [rsi+20h]; hFile
0x180028afd  lea     r8, [rbp+var_10]; lpNumberOfBytesTransferred
0x180028b01  mov     r9d, r13d; bWait
0x180028b04  mov     [rbp+var_10], r14d
0x180028b08  mov     rdx, r12; lpOverlapped
0x180028b0b  call    cs:__imp_GetOverlappedResult
  ... truncated ...
```
