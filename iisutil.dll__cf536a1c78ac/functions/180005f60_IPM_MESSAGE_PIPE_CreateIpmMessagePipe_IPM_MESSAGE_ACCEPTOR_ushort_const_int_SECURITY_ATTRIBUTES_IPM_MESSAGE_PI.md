# IPM_MESSAGE_PIPE::CreateIpmMessagePipe(IPM_MESSAGE_ACCEPTOR *,ushort const *,int,_SECURITY_ATTRIBUTES *,IPM_MESSAGE_PIPE * *)

- ea: `0x180005f60`
- end: `0x18000671c`
- name: `?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z`
- size: `1980`
- prototype: `__int64 __fastcall(struct IPM_MESSAGE_ACCEPTOR *, const unsigned __int16 *, int, struct _SECURITY_ATTRIBUTES *, struct IPM_MESSAGE_PIPE **Mode)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005460`
- `0x180005aa0`
- `0x180005c80`
- `0x180005d00`
- `0x180005f60`
- `0x180008000`
- `0x180008f20`
- `0x18000f810`
- `0x180019230`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000655e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006078`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006115`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006295`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006451`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800064cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000655e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800062b0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800062b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060e5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060cf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800060e5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000602f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000602f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180006285`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180006285`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18000643d`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18000643d`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180006064`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180006064`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x1800063ec`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x1800063ec`

## string_xrefs

- `0x1800060c0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180006158`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180006240`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180006318`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180006513`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800065c1`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180006611`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180006666`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800066aa`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x18000670b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800060ae`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x180006151`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800065af`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x18000660a`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800066f9`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x180006231`: `IpmReadFile`
- `0x180006225`: `IpmReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x18000613d`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateFile, hr = %x\n`
- `0x1800060a3`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed SetNamedPipeHandleState, hr = %x\n`
- `0x1800063af`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed ReadMessage, hr = %x\n`
- `0x180006306`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180006508`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180006654`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x18000669f`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x1800062fb`: `IPM_MESSAGE_PIPE::ReadMessage failed IpmReadFile, hr = %x\n`
- `0x1800065a3`: `IPM_MESSAGE_PIPE::CreateMessagePipe called name=%S\n`
- `0x1800066ee`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed allocation of IPM_MESSAGE_PIPE, hr = %x\n`
- `0x18000658a`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateNamedPipe, hr = %x\n`
- `0x1800065e9`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateMessage, hr = %x\n`
- `0x1800065f6`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed ConnectNamedPipe, hr = %x\n`
- `0x180006645`: `IPM_MESSAGE_PIPE::ReadMessage called with size=%d\n`
- `0x18000651a`: `IPM_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n`
- `0x180006690`: `IPM_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n`

## pseudocode

```c
__int64 __fastcall IPM_MESSAGE_PIPE::CreateIpmMessagePipe(
        struct IPM_MESSAGE_ACCEPTOR *a1,
        const unsigned __int16 *a2,
        int a3,
        struct _SECURITY_ATTRIBUTES *a4,
        struct IPM_MESSAGE_PIPE **Mode)
{
  struct IPM_MESSAGE_PIPE **v9; // r12
  _DWORD *v10; // rax
  _DWORD *v11; // rbx
  HANDLE FileW; // rax
  __int64 NamedPipeW; // rsi
  signed int v14; // eax
  unsigned int v15; // edi
  void *v16; // rcx
  void (__fastcall **v17)(_DWORD *, __int64); // rax
  signed int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  IPM_MESSAGE_IMP *v21; // r14
  signed int v22; // esi
  void *v23; // rax
  void *v24; // rsi
  void *v25; // rbp
  signed __int32 v26; // edx
  __int64 v27; // rax
  __int64 v28; // rdi
  int Message; // eax
  IPM_MESSAGE_IMP *v30; // rbp
  void *v31; // rcx
  signed int v32; // eax
  signed int v34; // eax
  signed int LastError; // eax
  IPM_MESSAGE_IMP *v36[2]; // [rsp+50h] [rbp-38h] BYREF

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      0x330u,
      "IPM_MESSAGE_PIPE::CreateIpmMessagePipe",
      "IPM_MESSAGE_PIPE::CreateMessagePipe called name=%S\n",
      (char)a2);
  v9 = Mode;
  v36[0] = 0;
  *Mode = 0;
  v10 = operator new(0x40u);
  v11 = v10;
  if ( v10 )
  {
    *(_QWORD *)v10 = &IPM_MESSAGE_PIPE::`vftable';
    v10[2] = 0;
    v10[3] = 0;
    *((_QWORD *)v10 + 2) = -1;
    v10[9] = 0;
    *((_QWORD *)v10 + 7) = 0;
    *((_QWORD *)v10 + 6) = v10 + 10;
    *((_QWORD *)v10 + 5) = v10 + 10;
    *((_QWORD *)v10 + 3) = a1;
    v10[8] = a3;
    if ( a3 )
    {
      NamedPipeW = (__int64)CreateNamedPipeW(a2, 0x40080003u, 6u, 1u, 0x1000u, 0x1000u, 0, a4);
      if ( NamedPipeW == -1 )
      {
        LastError = GetLastError();
        v15 = LastError;
        if ( LastError > 0 )
          v15 = (unsigned __int16)LastError | 0x80070000;
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
            0x360u,
            "IPM_MESSAGE_PIPE::CreateIpmMessagePipe",
            "IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateNamedPipe, hr = %x\n",
            v15);
        goto LABEL_12;
      }
      Message = IPM_MESSAGE_IMP::CreateMessage(v36, (struct IPM_MESSAGE_PIPE *)v11, 0);
      v30 = v36[0];
      v15 = Message;
      if ( Message < 0 )
      {
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
            0x36Au,
            "IPM_MESSAGE_PIPE::CreateIpmMessagePipe",
            "IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateMessage, hr = %x\n",
            Message);
      }
      else
      {
        *((_DWORD *)v36[0] + 3) = 2;
        *((_QWORD *)v11 + 2) = NamedPipeW;
        v31 = (void *)NamedPipeW;
        NamedPipeW = -1;
        if ( ConnectNamedPipe(v31, (LPOVERLAPPED)((char *)v30 + 56)) )
        {
          v15 = -2147467259;
        }
        else
        {
          v32 = GetLastError();
          if ( v32 == 997 )
            goto LABEL_73;
          if ( v32 <= 0 )
            v15 = v32;
          else
            v15 = (unsigned __int16)v32 | 0x80070000;
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
              0x37Du,
              "IPM_MESSAGE_PIPE::CreateIpmMessagePipe",
              "IPM_MESSAGE_PIPE::CreateMessagePipe failed ConnectNamedPipe, hr = %x\n",
              v15);
        }
      }
      if ( v30 )
        IPM_MESSAGE_IMP::DereferenceMessage(v30);
      if ( NamedPipeW == -1 )
        goto LABEL_12;
      goto LABEL_11;
    }
    FileW = CreateFileW(a2, 0x120183u, 0, a4, 3u, 0x40000000u, 0);
    NamedPipeW = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v18 = GetLastError();
      v15 = v18;
      if ( v18 > 0 )
        v15 = (unsigned __int16)v18 | 0x80070000;
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
          0x3B3u,
          "IPM_MESSAGE_PIPE::CreateIpmMessagePipe",
          "IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateFile, hr = %x\n",
          v15);
      goto LABEL_12;
    }
    LODWORD(Mode) = 2;
    if ( !SetNamedPipeHandleState(FileW, (LPDWORD)&Mode, 0, 0) )
    {
      v14 = GetLastError();
      v15 = v14;
      if ( v14 > 0 )
        v15 = (unsigned __int16)v14 | 0x80070000;
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
          0x3C0u,
          "IPM_MESSAGE_PIPE::CreateIpmMessagePipe",
          "IPM_MESSAGE_PIPE::CreateMessagePipe failed SetNamedPipeHandleState, hr = %x\n",
          v15);
LABEL_11:
      CloseHandle((HANDLE)NamedPipeW);
LABEL_12:
      v16 = (void *)*((_QWORD *)v11 + 2);
      if ( v16 != (void *)-1LL )
      {
        CloseHandle(v16);
        *((_QWORD *)v11 + 2) = -1;
      }
      v17 = *(void (__fastcall ***)(_DWORD *, __int64))v11;
      *((_QWORD *)v11 + 3) = 0;
      (*v17)(v11, 1);
      return v15;
    }
    v19 = *((_QWORD *)v11 + 3);
    *((_QWORD *)v11 + 2) = NamedPipeW;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 8LL))(v19);
    v36[0] = 0;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x511u,
        "IPM_MESSAGE_PIPE::ReadMessage",
        "IPM_MESSAGE_PIPE::ReadMessage called with size=%d\n",
        16);
    v20 = IPM_MESSAGE_IMP::CreateMessage(v36, (struct IPM_MESSAGE_PIPE *)v11, 0);
    v21 = v36[0];
    v22 = v20;
    if ( v20 < 0 )
    {
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
          0x51Au,
          "IPM_MESSAGE_PIPE::ReadMessage",
          "IPM_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n",
          v20);
      goto LABEL_41;
    }
    *((_DWORD *)v36[0] + 3) = 0;
    v23 = operator new(0x10u);
    if ( !v23 )
    {
      v22 = -2147024882;
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
          0x527u,
          "IPM_MESSAGE_PIPE::ReadMessage",
          "IPM_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n",
          14);
      goto LABEL_41;
    }
    *((_QWORD *)v21 + 3) = v23;
    *((_DWORD *)v21 + 4) = 16;
    CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v11 + 2));
    if ( *((_QWORD *)v11 + 2) == -1 )
    {
      CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v11 + 2));
      v22 = -2147024787;
LABEL_41:
      if ( v21 )
        IPM_MESSAGE_IMP::DereferenceMessage(v21);
      if ( v22 < 0 )
      {
        CReaderWriterLock3::WriteLock((CReaderWriterLock3 *)(v11 + 2));
        if ( v11[15] )
        {
          if ( (int)v11[14] >= 0 )
          {
            v11[14] = v22;
            CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v11 + 2));
            v15 = v22;
            goto LABEL_50;
          }
        }
        else
        {
          v27 = *((_QWORD *)v11 + 3);
          if ( v27 )
          {
            *((_QWORD *)v11 + 3) = 0;
            v28 = v27;
            CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v11 + 2));
            (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v28 + 16LL))(v28, (unsigned int)v22);
            v15 = v22;
            goto LABEL_50;
          }
        }
        CReaderWriterLock3::WriteUnlock((CReaderWriterLock3 *)(v11 + 2));
      }
      v15 = v22;
      if ( v22 < 0 )
      {
LABEL_50:
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
            0x3D3u,
            "IPM_MESSAGE_PIPE::CreateIpmMessagePipe",
            "IPM_MESSAGE_PIPE::CreateMessagePipe failed ReadMessage, hr = %x\n",
            v22);
        goto LABEL_12;
      }
LABEL_73:
      *v9 = (struct IPM_MESSAGE_PIPE *)v11;
      return v15;
    }
    _InterlockedIncrement((volatile signed __int32 *)v21 + 12);
    v24 = (void *)*((_QWORD *)v21 + 3);
    v25 = (void *)*((_QWORD *)v11 + 2);
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x14Cu,
        "IpmReadFile",
        "IpmReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
        (char)v25);
    if ( v25 == (void *)-1LL || !v24 || v21 == (IPM_MESSAGE_IMP *)-56LL )
    {
      v22 = -2147024809;
    }
    else
    {
      if ( !ReadFile(v25, v24, 0x10u, 0, (LPOVERLAPPED)((char *)v21 + 56)) )
      {
        if ( GetLastError() != 234 )
        {
          v34 = GetLastError();
          v22 = v34;
          if ( v34 > 0 )
            v22 = (unsigned __int16)v34 | 0x80070000;
          goto LABEL_34;
        }
        SetEvent(*((HANDLE *)v21 + 10));
      }
      v22 = 0;
    }
LABEL_34:
    while ( 1 )
    {
      v26 = v11[2];
      if ( v26 == _InterlockedCompareExchange(v11 + 2, v26 - 1, v26) )
        break;
      _mm_pause();
    }
    if ( v22 < 0 )
    {
      if ( v22 == -2147023899 )
      {
        v22 = 0;
      }
      else
      {
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
            0x54Bu,
            "IPM_MESSAGE_PIPE::ReadMessage",
            "IPM_MESSAGE_PIPE::ReadMessage failed IpmReadFile, hr = %x\n",
            v22);
        IPM_MESSAGE_IMP::DereferenceMessage(v21);
      }
    }
    goto LABEL_41;
  }
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      0x345u,
      "IPM_MESSAGE_PIPE::CreateIpmMessagePipe",
      "IPM_MESSAGE_PIPE::CreateMessagePipe failed allocation of IPM_MESSAGE_PIPE, hr = %x\n",
      14);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180005f60  mov     [rsp+arg_8], rbx
0x180005f65  mov     [rsp+arg_10], rbp
0x180005f6a  push    rsi
0x180005f6b  push    rdi
0x180005f6c  push    r12
0x180005f6e  push    r13
0x180005f70  push    r14
0x180005f72  sub     rsp, 60h
0x180005f76  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180005f7c  mov     r14, r9
0x180005f7f  test    al, 3
0x180005f81  mov     edi, r8d
0x180005f84  mov     rbp, rdx
0x180005f87  mov     rsi, rcx
0x180005f8a  setnz   r10b
0x180005f8e  bt      eax, 1Ch
0x180005f92  setb    al
0x180005f95  test    al, r10b
0x180005f98  jnz     loc_18000659C
0x180005f9e  mov     r12, qword ptr [rsp+88h+Mode]
0x180005fa6  xor     r13d, r13d
0x180005fa9  mov     ecx, 40h ; '@'; Size
0x180005fae  mov     [rsp+88h+var_38], r13
0x180005fb3  mov     [r12], r13
0x180005fb7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180005fbc  mov     rbx, rax
0x180005fbf  test    rax, rax
0x180005fc2  jz      loc_18000649E
0x180005fc8  mov     [rsp+88h+arg_0], r15
0x180005fd0  lea     rax, ??_7IPM_MESSAGE_PIPE@@6B@; const IPM_MESSAGE_PIPE::`vftable'
0x180005fd7  mov     [rbx], rax
0x180005fda  lea     rax, [rbx+28h]
0x180005fde  mov     [rbx+8], r13d
0x180005fe2  mov     rcx, rbp; lpName
0x180005fe5  mov     [rbx+0Ch], r13d
0x180005fe9  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180005ff1  mov     [rbx+24h], r13d
0x180005ff5  mov     [rbx+38h], r13
0x180005ff9  mov     [rax+8], rax
0x180005ffd  mov     [rax], rax
0x180006000  mov     [rbx+18h], rsi
0x180006004  mov     [rbx+20h], edi
0x180006007  test    edi, edi
0x180006009  jnz     loc_1800063C1
0x18000600f  mov     [rsp+88h+hTemplateFile], r13; hTemplateFile
0x180006014  mov     r9, r14; lpSecurityAttributes
0x180006017  mov     [rsp+88h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18000601f  xor     r8d, r8d; dwShareMode
0x180006022  mov     edx, 120183h; dwDesiredAccess
0x180006027  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18000602f  call    cs:__imp_CreateFileW
0x180006036  nop     dword ptr [rax+rax+00h]
0x18000603b  mov     rsi, rax
0x18000603e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006042  jz      loc_180006115
0x180006048  xor     r9d, r9d; lpCollectDataTimeout
0x18000604b  mov     [rsp+88h+Mode], 2
0x180006056  xor     r8d, r8d; lpMaxCollectionCount
0x180006059  lea     rdx, [rsp+88h+Mode]; lpMode
0x180006061  mov     rcx, rax; hNamedPipe
0x180006064  call    cs:__imp_SetNamedPipeHandleState
0x18000606b  nop     dword ptr [rax+rax+00h]
0x180006070  test    eax, eax
0x180006072  jnz     loc_18000616E
0x180006078  call    cs:__imp_GetLastError
0x18000607f  nop     dword ptr [rax+rax+00h]
0x180006084  mov     edi, eax
0x180006086  test    eax, eax
0x180006088  jle     short loc_180006093
0x18000608a  movzx   edi, ax
0x18000608d  or      edi, 80070000h
0x180006093  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18000609a  jz      short loc_1800060CC
0x18000609c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800060a3  lea     rax, aIpmMessagePipe_27; "IPM_MESSAGE_PIPE::CreateMessagePipe fai"...
0x1800060aa  mov     [rsp+88h+dwFlagsAndAttributes], edi; char
0x1800060ae  lea     r9, aIpmMessagePipe_15; "IPM_MESSAGE_PIPE::CreateIpmMessagePipe"
0x1800060b5  mov     r8d, 3C0h; unsigned int
0x1800060bb  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; char *
0x1800060c0  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800060c7  call    PuDbgPrint
0x1800060cc  mov     rcx, rsi; hObject
0x1800060cf  call    cs:__imp_CloseHandle
0x1800060d6  nop     dword ptr [rax+rax+00h]
0x1800060db  mov     rcx, [rbx+10h]; hObject
0x1800060df  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800060e3  jz      short loc_1800060F9
0x1800060e5  call    cs:__imp_CloseHandle
0x1800060ec  nop     dword ptr [rax+rax+00h]
0x1800060f1  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800060f9  mov     rax, [rbx]
0x1800060fc  mov     edx, 1
0x180006101  mov     rcx, rbx
0x180006104  mov     [rbx+18h], r13
0x180006108  mov     rax, [rax]
0x18000610b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006110  jmp     loc_18000654F
0x180006115  call    cs:__imp_GetLastError
0x18000611c  nop     dword ptr [rax+rax+00h]
0x180006121  mov     edi, eax
0x180006123  test    eax, eax
0x180006125  jle     short loc_180006130
0x180006127  movzx   edi, ax
0x18000612a  or      edi, 80070000h
0x180006130  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180006137  jz      short loc_1800060DB
0x180006139  mov     [rsp+88h+dwFlagsAndAttributes], edi; char
0x18000613d  lea     rax, aIpmMessagePipe_33; "IPM_MESSAGE_PIPE::CreateMessagePipe fai"...
0x180006144  mov     r8d, 3B3h; unsigned int
0x18000614a  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180006151  lea     r9, aIpmMessagePipe_15; "IPM_MESSAGE_PIPE::CreateIpmMessagePipe"
0x180006158  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000615f  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; char *
0x180006164  call    PuDbgPrint
0x180006169  jmp     loc_1800060DB
0x18000616e  mov     rcx, [rbx+18h]
0x180006172  mov     [rbx+10h], rsi
0x180006176  mov     rax, [rcx]
0x180006179  mov     rax, [rax+8]
0x18000617d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006182  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180006188  test    al, 3
0x18000618a  mov     [rsp+88h+var_38], r13
0x18000618f  setnz   cl
0x180006192  bt      eax, 1Ch
0x180006196  setb    al
0x180006199  test    al, cl
0x18000619b  jnz     loc_18000663E
0x1800061a1  xor     r8d, r8d; int
0x1800061a4  lea     rcx, [rsp+88h+var_38]; struct IPM_MESSAGE_IMP **
0x1800061a9  mov     rdx, rbx; struct IPM_MESSAGE_PIPE *
0x1800061ac  call    ?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z; IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)
0x1800061b1  mov     r14, [rsp+88h+var_38]
0x1800061b6  mov     esi, eax
0x1800061b8  test    eax, eax
0x1800061ba  js      loc_1800064F4
0x1800061c0  mov     ecx, 10h; Size
0x1800061c5  mov     [r14+0Ch], r13d
0x1800061c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061ce  test    rax, rax
0x1800061d1  jz      loc_180006677
0x1800061d7  lea     rcx, [rbx+8]; this
0x1800061db  mov     [r14+18h], rax
0x1800061df  mov     dword ptr [r14+10h], 10h
0x1800061e7  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800061ec  cmp     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800061f1  jz      loc_1800066C6
0x1800061f7  lock inc dword ptr [r14+30h]
0x1800061fc  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180006202  lea     rdi, [r14+38h]
0x180006206  mov     rsi, [r14+18h]
0x18000620a  test    al, 3
0x18000620c  mov     rbp, [rbx+10h]
0x180006210  setnz   cl
0x180006213  bt      eax, 1Ch
0x180006217  setb    al
0x18000621a  test    al, cl
0x18000621c  jz      short loc_180006261
0x18000621e  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180006225  lea     rax, aIpmreadfileCal; "IpmReadFile called with hFile=%d, pBuff"...
0x18000622c  mov     [rsp+88h+var_48], rdi
0x180006231  lea     r9, aIpmreadfile; "IpmReadFile"
0x180006238  mov     dword ptr [rsp+88h+lpSecurityAttributes], 10h
0x180006240  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180006247  mov     [rsp+88h+hTemplateFile], rsi
0x18000624c  mov     r8d, 14Ch; unsigned int
0x180006252  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbp; char
0x180006257  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; char *
0x18000625c  call    PuDbgPrint
0x180006261  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180006265  jz      short loc_1800062C1
0x180006267  test    rsi, rsi
0x18000626a  jz      short loc_1800062C1
0x18000626c  test    rdi, rdi
0x18000626f  jz      short loc_1800062C1
0x180006271  xor     r9d, r9d; lpNumberOfBytesRead
0x180006274  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; lpOverlapped
0x180006279  mov     r8d, 10h; nNumberOfBytesToRead
0x18000627f  mov     rdx, rsi; lpBuffer
0x180006282  mov     rcx, rbp; hFile
0x180006285  call    cs:__imp_ReadFile
0x18000628c  nop     dword ptr [rax+rax+00h]
0x180006291  test    eax, eax
0x180006293  jnz     short loc_1800062BC
0x180006295  call    cs:__imp_GetLastError
0x18000629c  nop     dword ptr [rax+rax+00h]
0x1800062a1  cmp     eax, 0EAh
0x1800062a6  jnz     loc_1800064CC
0x1800062ac  mov     rcx, [rdi+18h]; hEvent
0x1800062b0  call    cs:__imp_SetEvent
0x1800062b7  nop     dword ptr [rax+rax+00h]
0x1800062bc  mov     esi, r13d
0x1800062bf  jmp     short loc_1800062C6
0x1800062c1  mov     esi, 80070057h
0x1800062c6  mov     edx, [rbx+8]
0x1800062c9  mov     eax, edx
0x1800062cb  lea     ecx, [rdx-1]
0x1800062ce  lock cmpxchg [rbx+8], ecx
0x1800062d3  cmp     edx, eax
0x1800062d5  jz      short loc_1800062DB
0x1800062d7  pause
0x1800062d9  jmp     short loc_1800062C6
0x1800062db  test    esi, esi
0x1800062dd  jns     short loc_18000632C
0x1800062df  cmp     esi, 800703E5h
0x1800062e5  jz      loc_180006536
0x1800062eb  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800062f2  jz      short loc_180006324
0x1800062f4  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800062fb  lea     rax, aIpmMessagePipe_5; "IPM_MESSAGE_PIPE::ReadMessage failed Ip"...
0x180006302  mov     [rsp+88h+dwFlagsAndAttributes], esi; char
0x180006306  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x18000630d  mov     r8d, 54Bh; unsigned int
0x180006313  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; char *
0x180006318  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000631f  call    PuDbgPrint
0x180006324  mov     rcx, r14; this
0x180006327  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x18000632c  test    r14, r14
0x18000632f  jnz     loc_18000653E
0x180006335  test    esi, esi
0x180006337  jns     short loc_180006394
0x180006339  lea     rcx, [rbx+8]; this
0x18000633d  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180006342  cmp     [rbx+3Ch], r13d
0x180006346  jnz     short loc_18000637A
0x180006348  mov     rax, [rbx+18h]
0x18000634c  test    rax, rax
0x18000634f  jz      loc_1800066D9
0x180006355  lea     rcx, [rbx+8]; this
0x180006359  mov     [rbx+18h], r13
0x18000635d  mov     rdi, rax
0x180006360  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180006365  mov     rax, [rdi]
0x180006368  mov     edx, esi
0x18000636a  mov     rcx, rdi
0x18000636d  mov     rax, [rax+10h]
0x180006371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006376  mov     edi, esi
0x180006378  jmp     short loc_18000639E
0x18000637a  cmp     [rbx+38h], r13d
0x18000637e  jl      loc_1800066D9
0x180006384  lea     rcx, [rbx+8]; this
0x180006388  mov     [rbx+38h], esi
0x18000638b  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180006390  mov     edi, esi
0x180006392  jmp     short loc_18000639E
0x180006394  mov     edi, esi
0x180006396  test    esi, esi
0x180006398  jns     loc_18000654B
0x18000639e  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800063a5  jz      loc_1800060DB
0x1800063ab  mov     [rsp+88h+dwFlagsAndAttributes], esi
0x1800063af  lea     rax, aIpmMessagePipe_10; "IPM_MESSAGE_PIPE::CreateMessagePipe fai"...
0x1800063b6  mov     r8d, 3D3h
0x1800063bc  jmp     loc_18000614A
0x1800063c1  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800063c6  mov     edx, 40080003h; dwOpenMode
0x1800063cb  mov     dword ptr [rsp+88h+hTemplateFile], r13d; nDefaultTimeOut
0x1800063d0  mov     r9d, 1; nMaxInstances
0x1800063d6  mov     [rsp+88h+dwFlagsAndAttributes], 1000h; nInBufferSize
0x1800063de  mov     r8d, 6; dwPipeMode
0x1800063e4  mov     [rsp+88h+dwCreationDisposition], 1000h; nOutBufferSize
0x1800063ec  call    cs:__imp_CreateNamedPipeW
0x1800063f3  nop     dword ptr [rax+rax+00h]
0x1800063f8  mov     rsi, rax
0x1800063fb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800063ff  jz      loc_18000655E
0x180006405  xor     r8d, r8d; int
0x180006408  lea     rcx, [rsp+88h+var_38]; struct IPM_MESSAGE_IMP **
0x18000640d  mov     rdx, rbx; struct IPM_MESSAGE_PIPE *
0x180006410  call    ?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z; IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)
0x180006415  mov     rbp, [rsp+88h+var_38]
0x18000641a  mov     edi, eax
0x18000641c  test    eax, eax
0x18000641e  js      loc_1800065D2
0x180006424  mov     dword ptr [rbp+0Ch], 2
0x18000642b  lea     rdx, [rbp+38h]; lpOverlapped
0x18000642f  mov     [rbx+10h], rsi
0x180006433  mov     rcx, rsi; hNamedPipe
0x180006436  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000643d  call    cs:__imp_ConnectNamedPipe
0x180006444  nop     dword ptr [rax+rax+00h]
0x180006449  test    eax, eax
0x18000644b  jnz     loc_180006627
0x180006451  call    cs:__imp_GetLastError
0x180006458  nop     dword ptr [rax+rax+00h]
0x18000645d  cmp     eax, 3E5h
0x180006462  jz      loc_18000654B
0x180006468  test    eax, eax
0x18000646a  jle     loc_1800064F0
0x180006470  movzx   edi, ax
0x180006473  or      edi, 80070000h
0x180006479  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180006480  jnz     loc_1800065F2
0x180006486  test    rbp, rbp
0x180006489  jnz     loc_180006631
0x18000648f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180006493  jz      loc_1800060DB
0x180006499  jmp     loc_1800060CC
  ... truncated ...
```
