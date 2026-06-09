# IPM_MESSAGE_PIPE::CreateIpmMessagePipe(IPM_MESSAGE_ACCEPTOR *,ushort const *,int,_SECURITY_ATTRIBUTES *,IPM_MESSAGE_PIPE * *)

- ea: `0x1800053d0`
- end: `0x180005b33`
- name: `?CreateIpmMessagePipe@IPM_MESSAGE_PIPE@@SAJPEAVIPM_MESSAGE_ACCEPTOR@@PEBGHPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@@Z`
- size: `1891`
- prototype: `static int(struct IPM_MESSAGE_ACCEPTOR *, const unsigned __int16 *, int, struct _SECURITY_ATTRIBUTES *, struct IPM_MESSAGE_PIPE **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004910`
- `0x180004f40`
- `0x180005110`
- `0x180005184`
- `0x1800053d0`
- `0x180007300`
- `0x1800081e0`
- `0x18000e850`
- `0x1800183f8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000587f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000597b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800054dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800056db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000587f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800058ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000597b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800056f0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800056f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000552d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000553d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000552d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000553d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000549f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000549f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800056d1`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800056d1`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180005871`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180005871`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x1800054ce`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x1800054ce`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180005826`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x180005826`

## string_xrefs

- `0x18000551e`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800055a4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x18000568c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005752`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005930`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800059d8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005a28`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005a7d`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005ac1`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180005b22`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x18000550c`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x18000559d`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800059c6`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x180005a21`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x180005b10`: `IPM_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x18000567d`: `IpmReadFile`
- `0x180005671`: `IpmReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x180005589`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateFile, hr = %x\n`
- `0x180005501`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed SetNamedPipeHandleState, hr = %x\n`
- `0x1800057e9`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed ReadMessage, hr = %x\n`
- `0x180005740`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180005925`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180005a6b`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180005ab6`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180005735`: `IPM_MESSAGE_PIPE::ReadMessage failed IpmReadFile, hr = %x\n`
- `0x1800059ba`: `IPM_MESSAGE_PIPE::CreateMessagePipe called name=%S\n`
- `0x180005b05`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed allocation of IPM_MESSAGE_PIPE, hr = %x\n`
- `0x1800059a1`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateNamedPipe, hr = %x\n`
- `0x180005a00`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed CreateMessage, hr = %x\n`
- `0x180005a0d`: `IPM_MESSAGE_PIPE::CreateMessagePipe failed ConnectNamedPipe, hr = %x\n`
- `0x180005a5c`: `IPM_MESSAGE_PIPE::ReadMessage called with size=%d\n`
- `0x180005937`: `IPM_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n`
- `0x180005aa7`: `IPM_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n`

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
0x1800053d0  mov     [rsp+arg_8], rbx
0x1800053d5  mov     [rsp+arg_10], rbp
0x1800053da  push    rsi
0x1800053db  push    rdi
0x1800053dc  push    r12
0x1800053de  push    r13
0x1800053e0  push    r14
0x1800053e2  sub     rsp, 60h
0x1800053e6  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800053ec  mov     r14, r9
0x1800053ef  test    al, 3
0x1800053f1  mov     edi, r8d
0x1800053f4  mov     rbp, rdx
0x1800053f7  mov     rsi, rcx
0x1800053fa  setnz   r10b
0x1800053fe  bt      eax, 1Ch
0x180005402  setb    al
0x180005405  test    al, r10b
0x180005408  jnz     loc_1800059B3
0x18000540e  mov     r12, qword ptr [rsp+88h+Mode]
0x180005416  xor     r13d, r13d
0x180005419  mov     ecx, 40h ; '@'; Size
0x18000541e  mov     [rsp+88h+var_38], r13
0x180005423  mov     [r12], r13
0x180005427  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000542c  mov     rbx, rax
0x18000542f  test    rax, rax
0x180005432  jz      loc_1800058C2
0x180005438  mov     [rsp+88h+arg_0], r15
0x180005440  lea     rax, ??_7IPM_MESSAGE_PIPE@@6B@; const IPM_MESSAGE_PIPE::`vftable'
0x180005447  mov     [rbx], rax
0x18000544a  lea     rax, [rbx+28h]
0x18000544e  mov     [rbx+8], r13d
0x180005452  mov     rcx, rbp; lpName
0x180005455  mov     [rbx+0Ch], r13d
0x180005459  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180005461  mov     [rbx+24h], r13d
0x180005465  mov     [rbx+38h], r13
0x180005469  mov     [rax+8], rax
0x18000546d  mov     [rax], rax
0x180005470  mov     [rbx+18h], rsi
0x180005474  mov     [rbx+20h], edi
0x180005477  test    edi, edi
0x180005479  jnz     loc_1800057FB
0x18000547f  mov     [rsp+88h+hTemplateFile], r13; hTemplateFile
0x180005484  mov     r9, r14; lpSecurityAttributes
0x180005487  mov     [rsp+88h+dwFlagsAndAttributes], 40000000h; dwFlagsAndAttributes
0x18000548f  xor     r8d, r8d; dwShareMode
0x180005492  mov     edx, 120183h; dwDesiredAccess
0x180005497  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18000549f  call    cs:__imp_CreateFileW
0x1800054a5  mov     rsi, rax
0x1800054a8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800054ac  jz      loc_180005567
0x1800054b2  xor     r9d, r9d; lpCollectDataTimeout
0x1800054b5  mov     [rsp+88h+Mode], 2
0x1800054c0  xor     r8d, r8d; lpMaxCollectionCount
0x1800054c3  lea     rdx, [rsp+88h+Mode]; lpMode
0x1800054cb  mov     rcx, rax; hNamedPipe
0x1800054ce  call    cs:__imp_SetNamedPipeHandleState
0x1800054d4  test    eax, eax
0x1800054d6  jnz     loc_1800055BA
0x1800054dc  call    cs:__imp_GetLastError
0x1800054e2  mov     edi, eax
0x1800054e4  test    eax, eax
0x1800054e6  jle     short loc_1800054F1
0x1800054e8  movzx   edi, ax
0x1800054eb  or      edi, 80070000h
0x1800054f1  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800054f8  jz      short loc_18000552A
0x1800054fa  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005501  lea     rax, aIpmMessagePipe_27; "IPM_MESSAGE_PIPE::CreateMessagePipe fai"...
0x180005508  mov     [rsp+88h+dwFlagsAndAttributes], edi; char
0x18000550c  lea     r9, aIpmMessagePipe_15; "IPM_MESSAGE_PIPE::CreateIpmMessagePipe"
0x180005513  mov     r8d, 3C0h; unsigned int
0x180005519  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; char *
0x18000551e  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005525  call    PuDbgPrint
0x18000552a  mov     rcx, rsi; hObject
0x18000552d  call    cs:__imp_CloseHandle
0x180005533  mov     rcx, [rbx+10h]; hObject
0x180005537  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18000553b  jz      short loc_18000554B
0x18000553d  call    cs:__imp_CloseHandle
0x180005543  mov     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x18000554b  mov     rax, [rbx]
0x18000554e  mov     edx, 1
0x180005553  mov     rcx, rbx
0x180005556  mov     [rbx+18h], r13
0x18000555a  mov     rax, [rax]
0x18000555d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005562  jmp     loc_18000596C
0x180005567  call    cs:__imp_GetLastError
0x18000556d  mov     edi, eax
0x18000556f  test    eax, eax
0x180005571  jle     short loc_18000557C
0x180005573  movzx   edi, ax
0x180005576  or      edi, 80070000h
0x18000557c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180005583  jz      short loc_180005533
0x180005585  mov     [rsp+88h+dwFlagsAndAttributes], edi; char
0x180005589  lea     rax, aIpmMessagePipe_33; "IPM_MESSAGE_PIPE::CreateMessagePipe fai"...
0x180005590  mov     r8d, 3B3h; unsigned int
0x180005596  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000559d  lea     r9, aIpmMessagePipe_15; "IPM_MESSAGE_PIPE::CreateIpmMessagePipe"
0x1800055a4  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800055ab  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; char *
0x1800055b0  call    PuDbgPrint
0x1800055b5  jmp     loc_180005533
0x1800055ba  mov     rcx, [rbx+18h]
0x1800055be  mov     [rbx+10h], rsi
0x1800055c2  mov     rax, [rcx]
0x1800055c5  mov     rax, [rax+8]
0x1800055c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055ce  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800055d4  test    al, 3
0x1800055d6  mov     [rsp+88h+var_38], r13
0x1800055db  setnz   cl
0x1800055de  bt      eax, 1Ch
0x1800055e2  setb    al
0x1800055e5  test    al, cl
0x1800055e7  jnz     loc_180005A55
0x1800055ed  xor     r8d, r8d; int
0x1800055f0  lea     rcx, [rsp+88h+var_38]; struct IPM_MESSAGE_IMP **
0x1800055f5  mov     rdx, rbx; struct IPM_MESSAGE_PIPE *
0x1800055f8  call    ?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z; IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)
0x1800055fd  mov     r14, [rsp+88h+var_38]
0x180005602  mov     esi, eax
0x180005604  test    eax, eax
0x180005606  js      loc_180005911
0x18000560c  mov     ecx, 10h; Size
0x180005611  mov     [r14+0Ch], r13d
0x180005615  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000561a  test    rax, rax
0x18000561d  jz      loc_180005A8E
0x180005623  lea     rcx, [rbx+8]; this
0x180005627  mov     [r14+18h], rax
0x18000562b  mov     dword ptr [r14+10h], 10h
0x180005633  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180005638  cmp     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x18000563d  jz      loc_180005ADD
0x180005643  lock inc dword ptr [r14+30h]
0x180005648  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18000564e  lea     rdi, [r14+38h]
0x180005652  mov     rsi, [r14+18h]
0x180005656  test    al, 3
0x180005658  mov     rbp, [rbx+10h]
0x18000565c  setnz   cl
0x18000565f  bt      eax, 1Ch
0x180005663  setb    al
0x180005666  test    al, cl
0x180005668  jz      short loc_1800056AD
0x18000566a  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005671  lea     rax, aIpmreadfileCal; "IpmReadFile called with hFile=%d, pBuff"...
0x180005678  mov     [rsp+88h+var_48], rdi
0x18000567d  lea     r9, aIpmreadfile; "IpmReadFile"
0x180005684  mov     dword ptr [rsp+88h+lpSecurityAttributes], 10h
0x18000568c  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005693  mov     [rsp+88h+hTemplateFile], rsi
0x180005698  mov     r8d, 14Ch; unsigned int
0x18000569e  mov     qword ptr [rsp+88h+dwFlagsAndAttributes], rbp; char
0x1800056a3  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; char *
0x1800056a8  call    PuDbgPrint
0x1800056ad  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x1800056b1  jz      short loc_1800056FB
0x1800056b3  test    rsi, rsi
0x1800056b6  jz      short loc_1800056FB
0x1800056b8  test    rdi, rdi
0x1800056bb  jz      short loc_1800056FB
0x1800056bd  xor     r9d, r9d; lpNumberOfBytesRead
0x1800056c0  mov     qword ptr [rsp+88h+dwCreationDisposition], rdi; lpOverlapped
0x1800056c5  mov     r8d, 10h; nNumberOfBytesToRead
0x1800056cb  mov     rdx, rsi; lpBuffer
0x1800056ce  mov     rcx, rbp; hFile
0x1800056d1  call    cs:__imp_ReadFile
0x1800056d7  test    eax, eax
0x1800056d9  jnz     short loc_1800056F6
0x1800056db  call    cs:__imp_GetLastError
0x1800056e1  cmp     eax, 0EAh
0x1800056e6  jnz     loc_1800058EF
0x1800056ec  mov     rcx, [rdi+18h]; hEvent
0x1800056f0  call    cs:__imp_SetEvent
0x1800056f6  mov     esi, r13d
0x1800056f9  jmp     short loc_180005700
0x1800056fb  mov     esi, 80070057h
0x180005700  mov     edx, [rbx+8]
0x180005703  mov     eax, edx
0x180005705  lea     ecx, [rdx-1]
0x180005708  lock cmpxchg [rbx+8], ecx
0x18000570d  cmp     edx, eax
0x18000570f  jz      short loc_180005715
0x180005711  pause
0x180005713  jmp     short loc_180005700
0x180005715  test    esi, esi
0x180005717  jns     short loc_180005766
0x180005719  cmp     esi, 800703E5h
0x18000571f  jz      loc_180005953
0x180005725  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18000572c  jz      short loc_18000575E
0x18000572e  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180005735  lea     rax, aIpmMessagePipe_5; "IPM_MESSAGE_PIPE::ReadMessage failed Ip"...
0x18000573c  mov     [rsp+88h+dwFlagsAndAttributes], esi; char
0x180005740  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x180005747  mov     r8d, 54Bh; unsigned int
0x18000574d  mov     qword ptr [rsp+88h+dwCreationDisposition], rax; char *
0x180005752  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180005759  call    PuDbgPrint
0x18000575e  mov     rcx, r14; this
0x180005761  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x180005766  test    r14, r14
0x180005769  jnz     loc_18000595B
0x18000576f  test    esi, esi
0x180005771  jns     short loc_1800057CE
0x180005773  lea     rcx, [rbx+8]; this
0x180005777  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x18000577c  cmp     [rbx+3Ch], r13d
0x180005780  jnz     short loc_1800057B4
0x180005782  mov     rax, [rbx+18h]
0x180005786  test    rax, rax
0x180005789  jz      loc_180005AF0
0x18000578f  lea     rcx, [rbx+8]; this
0x180005793  mov     [rbx+18h], r13
0x180005797  mov     rdi, rax
0x18000579a  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x18000579f  mov     rax, [rdi]
0x1800057a2  mov     edx, esi
0x1800057a4  mov     rcx, rdi
0x1800057a7  mov     rax, [rax+10h]
0x1800057ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057b0  mov     edi, esi
0x1800057b2  jmp     short loc_1800057D8
0x1800057b4  cmp     [rbx+38h], r13d
0x1800057b8  jl      loc_180005AF0
0x1800057be  lea     rcx, [rbx+8]; this
0x1800057c2  mov     [rbx+38h], esi
0x1800057c5  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800057ca  mov     edi, esi
0x1800057cc  jmp     short loc_1800057D8
0x1800057ce  mov     edi, esi
0x1800057d0  test    esi, esi
0x1800057d2  jns     loc_180005968
0x1800057d8  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800057df  jz      loc_180005533
0x1800057e5  mov     [rsp+88h+dwFlagsAndAttributes], esi
0x1800057e9  lea     rax, aIpmMessagePipe_10; "IPM_MESSAGE_PIPE::CreateMessagePipe fai"...
0x1800057f0  mov     r8d, 3D3h
0x1800057f6  jmp     loc_180005596
0x1800057fb  mov     [rsp+88h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180005800  mov     edx, 40080003h; dwOpenMode
0x180005805  mov     dword ptr [rsp+88h+hTemplateFile], r13d; nDefaultTimeOut
0x18000580a  mov     r9d, 1; nMaxInstances
0x180005810  mov     [rsp+88h+dwFlagsAndAttributes], 1000h; nInBufferSize
0x180005818  mov     r8d, 6; dwPipeMode
0x18000581e  mov     [rsp+88h+dwCreationDisposition], 1000h; nOutBufferSize
0x180005826  call    cs:__imp_CreateNamedPipeW
0x18000582c  mov     rsi, rax
0x18000582f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005833  jz      loc_18000597B
0x180005839  xor     r8d, r8d; int
0x18000583c  lea     rcx, [rsp+88h+var_38]; struct IPM_MESSAGE_IMP **
0x180005841  mov     rdx, rbx; struct IPM_MESSAGE_PIPE *
0x180005844  call    ?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z; IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)
0x180005849  mov     rbp, [rsp+88h+var_38]
0x18000584e  mov     edi, eax
0x180005850  test    eax, eax
0x180005852  js      loc_1800059E9
0x180005858  mov     dword ptr [rbp+0Ch], 2
0x18000585f  lea     rdx, [rbp+38h]; lpOverlapped
0x180005863  mov     [rbx+10h], rsi
0x180005867  mov     rcx, rsi; hNamedPipe
0x18000586a  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180005871  call    cs:__imp_ConnectNamedPipe
0x180005877  test    eax, eax
0x180005879  jnz     loc_180005A3E
0x18000587f  call    cs:__imp_GetLastError
0x180005885  cmp     eax, 3E5h
0x18000588a  jz      loc_180005968
0x180005890  test    eax, eax
0x180005892  jle     short loc_18000590D
0x180005894  movzx   edi, ax
0x180005897  or      edi, 80070000h
0x18000589d  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800058a4  jnz     loc_180005A09
0x1800058aa  test    rbp, rbp
0x1800058ad  jnz     loc_180005A48
0x1800058b3  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800058b7  jz      loc_180005533
0x1800058bd  jmp     loc_18000552A
0x1800058c2  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800058c9  mov     esi, 8007000Eh
0x1800058ce  jnz     loc_180005AFE
0x1800058d4  mov     eax, esi
0x1800058d6  lea     r11, [rsp+88h+var_28]
0x1800058db  mov     rbx, [r11+38h]
0x1800058df  mov     rbp, [r11+40h]
0x1800058e3  mov     rsp, r11
0x1800058e6  pop     r14
0x1800058e8  pop     r13
0x1800058ea  pop     r12
0x1800058ec  pop     rdi
  ... truncated ...
```
