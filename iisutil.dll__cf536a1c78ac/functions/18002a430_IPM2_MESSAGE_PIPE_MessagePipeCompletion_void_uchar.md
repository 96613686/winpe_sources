# IPM2_MESSAGE_PIPE::MessagePipeCompletion(void *,uchar)

- ea: `0x18002a430`
- end: `0x18002aac8`
- name: `?MessagePipeCompletion@IPM2_MESSAGE_PIPE@@SAXPEAXE@Z`
- size: `1688`
- prototype: `void __fastcall(char *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005aa0`
- `0x180008000`
- `0x18000f810`
- `0x18001318c`
- `0x180016f20`
- `0x180029870`
- `0x180029c0c`
- `0x180029d04`
- `0x18002a430`
- `0x18002aad0`
- `0x18002acd8`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a55a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a85f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a948`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a55a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a5e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a85f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a948`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a54b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a934`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a54b`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002a934`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x18002a7fa`
- `api-ms-win-core-namedpipe-l1-1-0!PeekNamedPipe` at `0x18002a7fa`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002a45a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!UnregisterWait` at `0x18002a45a`

## string_xrefs

- `0x18002a733`: `Message length in the IPM header is smaller than the amount of data already read. This is unexpected.\n`
- `0x18002a7cc`: `********ERROR_MORE_DATA path, dwNumBytesTransferred=%d\n`
- `0x18002a4bc`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a5bf`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a65a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a6c3`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a74c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a7bb`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a83d`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a8d3`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a9ac`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002aaad`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002a49e`: `IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion called with pv = %p\n`
- `0x18002a4aa`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a5b4`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a64c`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a6b1`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a73a`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a7ad`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a82f`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a8c1`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a99e`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002aa9b`: `IPM2_MESSAGE_PIPE::MessagePipeCompletion`
- `0x18002a66b`: `IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion issuing read\n`
- `0x18002a6a6`: `IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion ReadMessage failed hr=%x\n`
- `0x18002aa90`: `IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECompletion disconnecting, hr=%x\n`

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
0x18002a430  mov     [rsp-38h+arg_8], rbx
0x18002a435  push    rbp
0x18002a436  push    rsi
0x18002a437  push    rdi
0x18002a438  push    r12
0x18002a43a  push    r13
0x18002a43c  push    r14
0x18002a43e  push    r15
0x18002a440  mov     rbp, rsp
0x18002a443  sub     rsp, 40h
0x18002a447  mov     rdi, rcx
0x18002a44a  mov     [rbp+NumberOfBytesTransferred], 0
0x18002a451  mov     rcx, [rcx+28h]; WaitHandle
0x18002a455  test    rcx, rcx
0x18002a458  jz      short loc_18002A46E
0x18002a45a  call    cs:__imp_UnregisterWait
0x18002a461  nop     dword ptr [rax+rax+00h]
0x18002a466  mov     qword ptr [rdi+28h], 0
0x18002a46e  mov     rax, [rdi]
0x18002a471  mov     rcx, rdi
0x18002a474  mov     rax, [rax+30h]
0x18002a478  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a47d  mov     ecx, cs:g_dwDebugFlagsIISUtil
0x18002a483  mov     rsi, rax
0x18002a486  test    cl, 3
0x18002a489  setnz   dl
0x18002a48c  bt      ecx, 1Ch
0x18002a490  setb    cl
0x18002a493  test    cl, dl
0x18002a495  jz      short loc_18002A4C8
0x18002a497  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a49e  lea     rax, aIpm2MessagePip_0; "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECom"...
0x18002a4a5  mov     [rsp+40h+lpBytesLeftThisMessage], rdi; char
0x18002a4aa  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002a4b1  mov     r8d, 7C8h; unsigned int
0x18002a4b7  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002a4bc  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a4c3  call    PuDbgPrint
0x18002a4c8  mov     r13d, 1
0x18002a4ce  lock add [rsi+4Ch], r13d
0x18002a4d3  cmp     qword ptr [rsi+28h], 0
0x18002a4d8  jz      short loc_18002A503
0x18002a4da  lea     rcx, [rsi+8]; this
0x18002a4de  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18002a4e3  mov     rcx, [rsi+20h]; hFile
0x18002a4e7  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002a4eb  jnz     short loc_18002A533
0x18002a4ed  lea     rcx, [rsi+8]; this
0x18002a4f1  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002a4f6  mov     edx, 8007006Dh; int
0x18002a4fb  mov     rcx, rsi; this
0x18002a4fe  call    ?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x18002a503  mov     rax, [rdi]
0x18002a506  mov     rcx, rdi
0x18002a509  mov     rax, [rax+8]
0x18002a50d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a512  mov     rcx, rsi; this
0x18002a515  call    ?DecrementAcceptorInUse@IPM2_MESSAGE_PIPE@@AEAAXXZ; IPM2_MESSAGE_PIPE::DecrementAcceptorInUse(void)
0x18002a51a  mov     rbx, [rsp+40h+arg_8]
0x18002a522  add     rsp, 40h
0x18002a526  pop     r15
0x18002a528  pop     r14
0x18002a52a  pop     r13
0x18002a52c  pop     r12
0x18002a52e  pop     rdi
0x18002a52f  pop     rsi
0x18002a530  pop     rbp
0x18002a531  retn
0x18002a533  xor     eax, eax
0x18002a535  lea     r12, [rdi+38h]
0x18002a539  mov     rdx, r12; lpOverlapped
0x18002a53c  mov     [rbp+nNumberOfBytesToRead], eax
0x18002a53f  xor     r9d, r9d; bWait
0x18002a542  lea     r8, [rbp+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002a546  xor     ebx, ebx
0x18002a548  xor     r14d, r14d
0x18002a54b  call    cs:__imp_GetOverlappedResult
0x18002a552  nop     dword ptr [rax+rax+00h]
0x18002a557  mov     r15d, eax
0x18002a55a  call    cs:__imp_GetLastError
0x18002a561  nop     dword ptr [rax+rax+00h]
0x18002a566  mov     edx, [rdi+0Ch]
0x18002a569  test    edx, edx
0x18002a56b  jz      loc_18002A6E2
0x18002a571  sub     edx, r13d
0x18002a574  jz      loc_18002A6D4
0x18002a57a  cmp     edx, r13d
0x18002a57d  jnz     loc_18002A604
0x18002a583  test    r15d, r15d
0x18002a586  jz      short loc_18002A5E6
0x18002a588  lea     eax, [rbx+2]
0x18002a58b  xchg    eax, [rsi+58h]
0x18002a58e  mov     rcx, [rsi+28h]
0x18002a592  mov     rax, [rcx]
0x18002a595  mov     rax, [rax+8]
0x18002a599  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a59e  mov     ebx, eax
0x18002a5a0  test    eax, eax
0x18002a5a2  jns     short loc_18002A5DD
0x18002a5a4  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002a5ab  jz      short loc_18002A5DD
0x18002a5ad  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a5b4  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002a5bb  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], eax; char
0x18002a5bf  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a5c6  lea     rax, aCaseIpm2Messag; "Case IPM2_MESSAGE_IMP_CONNECT m_pAccept"...
0x18002a5cd  mov     r8d, 800h; unsigned int
0x18002a5d3  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002a5d8  call    PuDbgPrint
0x18002a5dd  mov     [rbp+nNumberOfBytesToRead], 20h ; ' '
0x18002a5e4  jmp     short loc_18002A604
0x18002a5e6  mov     r14d, r13d
0x18002a5e9  call    cs:__imp_GetLastError
0x18002a5f0  nop     dword ptr [rax+rax+00h]
0x18002a5f5  mov     ebx, eax
0x18002a5f7  test    eax, eax
0x18002a5f9  jle     short loc_18002A604
0x18002a5fb  movzx   ebx, ax
0x18002a5fe  or      ebx, 80070000h
0x18002a604  lea     rcx, [rsi+8]; this
0x18002a608  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18002a60d  mov     r15d, [rbp+nNumberOfBytesToRead]
0x18002a611  mov     rax, [rdi]
0x18002a614  mov     rcx, rdi
0x18002a617  mov     rax, [rax+8]
0x18002a61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a620  cmp     dword ptr [rsi+58h], 2
0x18002a624  jnz     loc_18002A512
0x18002a62a  test    r15d, r15d
0x18002a62d  jz      loc_18002AA6A
0x18002a633  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002a639  test    al, 3
0x18002a63b  setnz   cl
0x18002a63e  bt      eax, 1Ch
0x18002a642  setb    al
0x18002a645  test    al, cl
0x18002a647  jz      short loc_18002A67C
0x18002a649  mov     eax, [rbp+NumberOfBytesTransferred]
0x18002a64c  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002a653  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a65a  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a661  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], eax; char
0x18002a665  mov     r8d, 914h; unsigned int
0x18002a66b  lea     rax, aIpm2MessagePip_1; "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECom"...
0x18002a672  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002a677  call    PuDbgPrint
0x18002a67c  mov     edx, r15d; nNumberOfBytesToRead
0x18002a67f  mov     rcx, rsi; this
0x18002a682  call    ?ReadMessage@IPM2_MESSAGE_PIPE@@AEAAJK@Z; IPM2_MESSAGE_PIPE::ReadMessage(ulong)
0x18002a687  mov     ebx, eax
0x18002a689  test    eax, eax
0x18002a68b  jns     loc_18002AA6A
0x18002a691  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002a697  test    al, 3
0x18002a699  jz      loc_18002AA7B
0x18002a69f  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a6a6  lea     rax, aIpm2MessagePip_34; "IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPECom"...
0x18002a6ad  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], ebx; char
0x18002a6b1  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002a6b8  mov     r8d, 91Fh; unsigned int
0x18002a6be  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002a6c3  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a6ca  call    PuDbgPrint
0x18002a6cf  jmp     loc_18002AA73
0x18002a6d4  test    r15d, r15d
0x18002a6d7  jnz     loc_18002A604
0x18002a6dd  jmp     loc_18002A5E6
0x18002a6e2  test    r15d, r15d
0x18002a6e5  jz      loc_18002A785
0x18002a6eb  mov     eax, [rbp+NumberOfBytesTransferred]
0x18002a6ee  cmp     eax, 10h
0x18002a6f1  jb      loc_18002A778
0x18002a6f7  mov     [rdi+10h], eax
0x18002a6fa  lea     r15, [rdi+18h]
0x18002a6fe  mov     rax, [rdi]
0x18002a701  mov     rcx, rdi
0x18002a704  mov     r13, [r15]
0x18002a707  mov     rax, [rax+18h]
0x18002a70b  mov     r12d, [r13+4]
0x18002a70f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a714  add     eax, 10h
0x18002a717  mov     [rbp+BytesLeftThisMessage], eax
0x18002a71a  cmp     r12d, eax
0x18002a71d  jnb     loc_18002A966
0x18002a723  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002a72a  jz      short loc_18002A758
0x18002a72c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a733  lea     rax, aMessageLengthI; "Message length in the IPM header is sma"...
0x18002a73a  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002a741  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002a746  mov     r8d, 8ACh; unsigned int
0x18002a74c  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a753  call    PuDbgPrint
0x18002a758  mov     rcx, [rsi+28h]
0x18002a75c  mov     rax, [rcx]
0x18002a75f  mov     rax, [rax+20h]
0x18002a763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a768  mov     ebx, 83760002h
0x18002a76d  mov     r14d, 1
0x18002a773  jmp     loc_18002A604
0x18002a778  mov     ebx, 8007000Bh
0x18002a77d  mov     r14d, r13d
0x18002a780  jmp     loc_18002A604
0x18002a785  cmp     eax, 0EAh
0x18002a78a  jnz     loc_18002AA58
0x18002a790  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18002a796  mov     r15b, 3
0x18002a799  test    r15b, al
0x18002a79c  setnz   cl
0x18002a79f  bt      eax, 1Ch
0x18002a7a3  setb    al
0x18002a7a6  test    al, cl
0x18002a7a8  jz      short loc_18002A7DD
0x18002a7aa  mov     eax, [rbp+NumberOfBytesTransferred]
0x18002a7ad  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002a7b4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a7bb  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a7c2  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], eax; char
0x18002a7c6  mov     r8d, 83Eh; unsigned int
0x18002a7cc  lea     rax, aErrorMoreDataP; "********ERROR_MORE_DATA path, dwNumByte"...
0x18002a7d3  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002a7d8  call    PuDbgPrint
0x18002a7dd  mov     rcx, [rsi+20h]; hNamedPipe
0x18002a7e1  lea     rax, [rbp+BytesLeftThisMessage]
0x18002a7e5  mov     [rsp+40h+lpBytesLeftThisMessage], rax; lpBytesLeftThisMessage
0x18002a7ea  xor     r9d, r9d; lpBytesRead
0x18002a7ed  xor     r8d, r8d; nBufferSize
0x18002a7f0  mov     [rsp+40h+lpTotalBytesAvail], rbx; lpTotalBytesAvail
0x18002a7f5  xor     edx, edx; lpBuffer
0x18002a7f7  mov     [rbp+BytesLeftThisMessage], ebx
0x18002a7fa  call    cs:__imp_PeekNamedPipe
0x18002a801  nop     dword ptr [rax+rax+00h]
0x18002a806  mov     r8d, cs:g_dwDebugFlagsIISUtil
0x18002a80d  test    r15b, r8b
0x18002a810  mov     ebx, eax
0x18002a812  setnz   dl
0x18002a815  bt      r8d, 1Ch
0x18002a81a  setb    cl
0x18002a81d  test    cl, dl
0x18002a81f  jz      short loc_18002A85B
0x18002a821  mov     ecx, [rbp+BytesLeftThisMessage]
0x18002a824  lea     rax, aDwremainingD; "********dwRemaining = %d\n"
0x18002a82b  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], ecx; char
0x18002a82f  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002a836  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a83d  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a844  mov     r8d, 84Bh; unsigned int
0x18002a84a  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002a84f  call    PuDbgPrint
0x18002a854  mov     r8d, cs:g_dwDebugFlagsIISUtil
0x18002a85b  test    ebx, ebx
0x18002a85d  jnz     short loc_18002A883
0x18002a85f  call    cs:__imp_GetLastError
0x18002a866  nop     dword ptr [rax+rax+00h]
0x18002a86b  mov     ebx, eax
0x18002a86d  test    eax, eax
0x18002a86f  jle     loc_18002A77D
0x18002a875  movzx   ebx, ax
0x18002a878  or      ebx, 80070000h
0x18002a87e  jmp     loc_18002A77D
0x18002a883  mov     edx, [rbp+BytesLeftThisMessage]
0x18002a886  mov     eax, [rbp+NumberOfBytesTransferred]
0x18002a889  add     rdx, rax
0x18002a88c  mov     ebx, edx
0x18002a88e  cmp     rdx, rbx
0x18002a891  jz      short loc_18002A89D
0x18002a893  mov     ebx, 80070216h
0x18002a898  jmp     loc_18002A77D
0x18002a89d  test    r15b, r8b
0x18002a8a0  setnz   cl
0x18002a8a3  bt      r8d, 1Ch
0x18002a8a8  setb    al
0x18002a8ab  test    al, cl
0x18002a8ad  jz      short loc_18002A8DF
0x18002a8af  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002a8b6  lea     rax, aReallocatingSi; "********reallocating size = %d\n"
0x18002a8bd  mov     dword ptr [rsp+40h+lpBytesLeftThisMessage], ebx; char
0x18002a8c1  lea     r9, aIpm2MessagePip_15; "IPM2_MESSAGE_PIPE::MessagePipeCompletio"...
0x18002a8c8  mov     r8d, 863h; unsigned int
0x18002a8ce  mov     [rsp+40h+lpTotalBytesAvail], rax; char *
0x18002a8d3  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002a8da  call    PuDbgPrint
0x18002a8df  mov     edx, ebx; unsigned int
0x18002a8e1  mov     rcx, rdi; this
0x18002a8e4  call    ?Reallocate@IPM2_MESSAGE_IMP@@QEAAJK@Z; IPM2_MESSAGE_IMP::Reallocate(ulong)
0x18002a8e9  mov     ebx, eax
0x18002a8eb  test    eax, eax
0x18002a8ed  js      loc_18002A77D
0x18002a8f3  mov     edx, [rbp+NumberOfBytesTransferred]
0x18002a8f6  lea     r15, [rdi+18h]
0x18002a8fa  add     rdx, [r15]; lpBuffer
0x18002a8fd  mov     r9, r12; lpOverlapped
0x18002a900  mov     r8d, [rbp+BytesLeftThisMessage]; nNumberOfBytesToRead
0x18002a904  mov     rcx, [rsi+20h]; hFile
0x18002a908  call    ?Ipm2ReadFile@@YAJPEAX0KPEAU_OVERLAPPED@@@Z; Ipm2ReadFile(void *,void *,ulong,_OVERLAPPED *)
0x18002a90d  mov     ebx, eax
0x18002a90f  test    eax, eax
0x18002a911  jns     loc_18002A6FE
0x18002a917  cmp     eax, 800703E5h
0x18002a91c  jnz     loc_18002A77D
  ... truncated ...
```
