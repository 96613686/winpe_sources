# IPM_MESSAGE_PIPE::ReadMessage(ulong)

- ea: `0x180011210`
- end: `0x180011589`
- name: `?ReadMessage@IPM_MESSAGE_PIPE@@AEAAJK@Z`
- size: `889`
- prototype: `__int64 __fastcall(IPM_MESSAGE_PIPE *this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005460`
- `0x180005aa0`
- `0x180005c80`
- `0x180005d00`
- `0x180008000`
- `0x180008f20`
- `0x18000f810`
- `0x180011210`
- `0x180019230`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001135a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001135a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011476`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011375`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180011375`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001134a`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18001134a`

## string_xrefs

- `0x180011304`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800113e2`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800114b9`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x18001151a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x18001155a`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800112f9`: `IpmReadFile`
- `0x1800112ed`: `IpmReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x1800113d0`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x1800114ae`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180011508`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x18001154f`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x1800113c5`: `IPM_MESSAGE_PIPE::ReadMessage failed IpmReadFile, hr = %x\n`
- `0x1800114fd`: `IPM_MESSAGE_PIPE::ReadMessage called with size=%d\n`
- `0x1800114c0`: `IPM_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n`
- `0x180011544`: `IPM_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n`

## pseudocode

```c
__int64 __fastcall IPM_MESSAGE_PIPE::ReadMessage(IPM_MESSAGE_PIPE *this, unsigned int a2)
{
  size_t v2; // rsi
  int v4; // eax
  signed int v5; // edi
  IPM_MESSAGE_IMP *v6; // rdi
  void *v7; // rax
  void *v8; // r14
  void *v9; // rbp
  struct _OVERLAPPED *lpOverlapped; // rdi
  signed __int32 v11; // ecx
  __int64 v12; // rax
  __int64 v13; // rsi
  signed int LastError; // eax
  IPM_MESSAGE_IMP *v16; // [rsp+80h] [rbp+18h] BYREF

  v2 = a2;
  v16 = 0;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      0x511u,
      "IPM_MESSAGE_PIPE::ReadMessage",
      "IPM_MESSAGE_PIPE::ReadMessage called with size=%d\n",
      a2);
  v4 = IPM_MESSAGE_IMP::CreateMessage(&v16, this, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x51Au,
        "IPM_MESSAGE_PIPE::ReadMessage",
        "IPM_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n",
        v4);
  }
  else
  {
    *((_DWORD *)v16 + 3) = 0;
    v6 = v16;
    v7 = operator new(v2);
    if ( v7 )
    {
      *((_QWORD *)v6 + 3) = v7;
      *((_DWORD *)v6 + 4) = v2;
      CReaderWriterLock3::ReadLock((IPM_MESSAGE_PIPE *)((char *)this + 8));
      if ( *((_QWORD *)this + 2) == -1 )
      {
        CReaderWriterLock3::ReadUnlock((IPM_MESSAGE_PIPE *)((char *)this + 8));
        v5 = -2147024787;
        goto LABEL_24;
      }
      _InterlockedIncrement((volatile signed __int32 *)v16 + 12);
      v8 = (void *)*((_QWORD *)this + 2);
      v9 = (void *)*((_QWORD *)v16 + 3);
      lpOverlapped = (struct _OVERLAPPED *)((char *)v16 + 56);
      if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
        PuDbgPrint(
          (struct _DEBUG_PRINTS *)g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
          0x14Cu,
          "IpmReadFile",
          "IpmReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
          (char)v8);
      if ( v8 != (void *)-1LL && v9 && (_DWORD)v2 && lpOverlapped )
      {
        if ( !ReadFile(v8, v9, v2, 0, lpOverlapped) )
        {
          if ( GetLastError() != 234 )
          {
            LastError = GetLastError();
            v5 = LastError;
            if ( LastError > 0 )
              v5 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_17;
          }
          SetEvent(lpOverlapped->hEvent);
        }
        v5 = 0;
      }
      else
      {
        v5 = -2147024809;
      }
LABEL_17:
      while ( 1 )
      {
        v11 = *((_DWORD *)this + 2);
        if ( v11 == _InterlockedCompareExchange((volatile signed __int32 *)this + 2, v11 - 1, v11) )
          break;
        _mm_pause();
      }
      if ( v5 < 0 )
      {
        if ( v5 == -2147023899 )
        {
          v5 = 0;
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
              v5);
          IPM_MESSAGE_IMP::DereferenceMessage(v16);
        }
      }
      goto LABEL_24;
    }
    v5 = -2147024882;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x527u,
        "IPM_MESSAGE_PIPE::ReadMessage",
        "IPM_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n",
        14);
  }
LABEL_24:
  if ( v16 )
  {
    IPM_MESSAGE_IMP::DereferenceMessage(v16);
    v16 = 0;
  }
  if ( v5 < 0 )
  {
    CReaderWriterLock3::WriteLock((IPM_MESSAGE_PIPE *)((char *)this + 8));
    if ( *((_DWORD *)this + 15) )
    {
      if ( *((int *)this + 14) >= 0 )
        *((_DWORD *)this + 14) = v5;
    }
    else
    {
      v12 = *((_QWORD *)this + 3);
      if ( v12 )
      {
        *((_QWORD *)this + 3) = 0;
        v13 = v12;
        CReaderWriterLock3::WriteUnlock((IPM_MESSAGE_PIPE *)((char *)this + 8));
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 16LL))(v13, (unsigned int)v5);
        return (unsigned int)v5;
      }
    }
    CReaderWriterLock3::WriteUnlock((IPM_MESSAGE_PIPE *)((char *)this + 8));
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180011210  mov     [rsp+arg_18], rbx
0x180011215  push    rsi
0x180011216  push    rdi
0x180011217  push    r15
0x180011219  sub     rsp, 50h
0x18001121d  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180011223  xor     r15d, r15d
0x180011226  test    al, 3
0x180011228  mov     esi, edx
0x18001122a  mov     rbx, rcx
0x18001122d  mov     [rsp+68h+arg_10], r15
0x180011235  setnz   r8b
0x180011239  bt      eax, 1Ch
0x18001123d  setb    al
0x180011240  test    al, r8b
0x180011243  jnz     loc_1800114F6
0x180011249  xor     r8d, r8d; int
0x18001124c  mov     [rsp+68h+arg_0], rbp
0x180011251  mov     rdx, rbx; struct IPM_MESSAGE_PIPE *
0x180011254  lea     rcx, [rsp+68h+arg_10]; struct IPM_MESSAGE_IMP **
0x18001125c  call    ?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z; IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)
0x180011261  mov     edi, eax
0x180011263  test    eax, eax
0x180011265  js      loc_18001149A
0x18001126b  mov     rax, [rsp+68h+arg_10]
0x180011273  mov     rcx, rsi; Size
0x180011276  mov     [rax+0Ch], r15d
0x18001127a  mov     rdi, [rsp+68h+arg_10]
0x180011282  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011287  test    rax, rax
0x18001128a  jz      loc_18001152B
0x180011290  lea     rcx, [rbx+8]; this
0x180011294  mov     [rdi+18h], rax
0x180011298  mov     [rdi+10h], esi
0x18001129b  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x1800112a0  cmp     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x1800112a5  jz      loc_180011576
0x1800112ab  mov     rax, [rsp+68h+arg_10]
0x1800112b3  mov     [rsp+68h+arg_8], r14
0x1800112b8  lock inc dword ptr [rax+30h]
0x1800112bc  mov     rax, [rsp+68h+arg_10]
0x1800112c4  mov     r14, [rbx+10h]
0x1800112c8  mov     rbp, [rax+18h]
0x1800112cc  lea     rdi, [rax+38h]
0x1800112d0  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800112d6  test    al, 3
0x1800112d8  setnz   cl
0x1800112db  bt      eax, 1Ch
0x1800112df  setb    al
0x1800112e2  test    al, cl
0x1800112e4  jz      short loc_180011325
0x1800112e6  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800112ed  lea     rax, aIpmreadfileCal; "IpmReadFile called with hFile=%d, pBuff"...
0x1800112f4  mov     [rsp+68h+var_28], rdi
0x1800112f9  lea     r9, aIpmreadfile; "IpmReadFile"
0x180011300  mov     [rsp+68h+var_30], esi
0x180011304  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001130b  mov     [rsp+68h+var_38], rbp
0x180011310  mov     r8d, 14Ch; unsigned int
0x180011316  mov     qword ptr [rsp+68h+var_40], r14; char
0x18001131b  mov     [rsp+68h+lpOverlapped], rax; char *
0x180011320  call    PuDbgPrint
0x180011325  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180011329  jz      short loc_180011386
0x18001132b  test    rbp, rbp
0x18001132e  jz      short loc_180011386
0x180011330  test    esi, esi
0x180011332  jz      short loc_180011386
0x180011334  test    rdi, rdi
0x180011337  jz      short loc_180011386
0x180011339  xor     r9d, r9d; lpNumberOfBytesRead
0x18001133c  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x180011341  mov     r8d, esi; nNumberOfBytesToRead
0x180011344  mov     rdx, rbp; lpBuffer
0x180011347  mov     rcx, r14; hFile
0x18001134a  call    cs:__imp_ReadFile
0x180011351  nop     dword ptr [rax+rax+00h]
0x180011356  test    eax, eax
0x180011358  jnz     short loc_180011381
0x18001135a  call    cs:__imp_GetLastError
0x180011361  nop     dword ptr [rax+rax+00h]
0x180011366  cmp     eax, 0EAh
0x18001136b  jnz     loc_180011476
0x180011371  mov     rcx, [rdi+18h]; hEvent
0x180011375  call    cs:__imp_SetEvent
0x18001137c  nop     dword ptr [rax+rax+00h]
0x180011381  mov     edi, r15d
0x180011384  jmp     short loc_18001138B
0x180011386  mov     edi, 80070057h
0x18001138b  mov     r14, [rsp+68h+arg_8]
0x180011390  mov     ecx, [rbx+8]
0x180011393  mov     eax, ecx
0x180011395  lea     edx, [rcx-1]
0x180011398  lock cmpxchg [rbx+8], edx
0x18001139d  cmp     ecx, eax
0x18001139f  jz      short loc_1800113A5
0x1800113a1  pause
0x1800113a3  jmp     short loc_180011390
0x1800113a5  test    edi, edi
0x1800113a7  jns     short loc_1800113FB
0x1800113a9  cmp     edi, 800703E5h
0x1800113af  jz      loc_1800114DC
0x1800113b5  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800113bc  jz      short loc_1800113EE
0x1800113be  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800113c5  lea     rax, aIpmMessagePipe_5; "IPM_MESSAGE_PIPE::ReadMessage failed Ip"...
0x1800113cc  mov     dword ptr [rsp+68h+var_40], edi; char
0x1800113d0  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x1800113d7  mov     r8d, 54Bh; unsigned int
0x1800113dd  mov     [rsp+68h+lpOverlapped], rax; char *
0x1800113e2  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800113e9  call    PuDbgPrint
0x1800113ee  mov     rcx, [rsp+68h+arg_10]; this
0x1800113f6  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x1800113fb  mov     rcx, [rsp+68h+arg_10]; this
0x180011403  test    rcx, rcx
0x180011406  jnz     loc_1800114E4
0x18001140c  test    edi, edi
0x18001140e  jns     short loc_180011449
0x180011410  lea     rcx, [rbx+8]; this
0x180011414  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180011419  cmp     [rbx+3Ch], r15d
0x18001141d  jnz     short loc_180011462
0x18001141f  mov     rax, [rbx+18h]
0x180011423  test    rax, rax
0x180011426  jz      short loc_18001146B
0x180011428  lea     rcx, [rbx+8]; this
0x18001142c  mov     [rbx+18h], r15
0x180011430  mov     rsi, rax
0x180011433  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180011438  mov     rax, [rsi]
0x18001143b  mov     edx, edi
0x18001143d  mov     rcx, rsi
0x180011440  mov     rax, [rax+10h]
0x180011444  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011449  mov     rbp, [rsp+68h+arg_0]
0x18001144e  mov     eax, edi
0x180011450  mov     rbx, [rsp+68h+arg_18]
0x180011458  add     rsp, 50h
0x18001145c  pop     r15
0x18001145e  pop     rdi
0x18001145f  pop     rsi
0x180011460  retn
0x180011462  cmp     [rbx+38h], r15d
0x180011466  jl      short loc_18001146B
0x180011468  mov     [rbx+38h], edi
0x18001146b  lea     rcx, [rbx+8]; this
0x18001146f  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180011474  jmp     short loc_180011449
0x180011476  call    cs:__imp_GetLastError
0x18001147d  nop     dword ptr [rax+rax+00h]
0x180011482  mov     edi, eax
0x180011484  test    eax, eax
0x180011486  jle     loc_18001138B
0x18001148c  movzx   edi, ax
0x18001148f  or      edi, 80070000h
0x180011495  jmp     loc_18001138B
0x18001149a  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800114a1  jz      loc_1800113FB
0x1800114a7  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800114ae  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x1800114b5  mov     dword ptr [rsp+68h+var_40], eax; char
0x1800114b9  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800114c0  lea     rax, aIpmMessagePipe_20; "IPM_MESSAGE_PIPE::ReadMessage failed Cr"...
0x1800114c7  mov     r8d, 51Ah; unsigned int
0x1800114cd  mov     [rsp+68h+lpOverlapped], rax; char *
0x1800114d2  call    PuDbgPrint
0x1800114d7  jmp     loc_1800113FB
0x1800114dc  mov     edi, r15d
0x1800114df  jmp     loc_1800113FB
0x1800114e4  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x1800114e9  mov     [rsp+68h+arg_10], r15
0x1800114f1  jmp     loc_18001140C
0x1800114f6  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800114fd  lea     rax, aIpmMessagePipe_12; "IPM_MESSAGE_PIPE::ReadMessage called wi"...
0x180011504  mov     dword ptr [rsp+68h+var_40], esi; char
0x180011508  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x18001150f  mov     r8d, 511h; unsigned int
0x180011515  mov     [rsp+68h+lpOverlapped], rax; char *
0x18001151a  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180011521  call    PuDbgPrint
0x180011526  jmp     loc_180011249
0x18001152b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180011532  mov     edi, 8007000Eh
0x180011537  jz      loc_1800113FB
0x18001153d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180011544  lea     rax, aIpmMessagePipe_19; "IPM_MESSAGE_PIPE::ReadMessage failed al"...
0x18001154b  mov     dword ptr [rsp+68h+var_38], esi
0x18001154f  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x180011556  mov     dword ptr [rsp+68h+var_40], edi; char
0x18001155a  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180011561  mov     r8d, 527h; unsigned int
0x180011567  mov     [rsp+68h+lpOverlapped], rax; char *
0x18001156c  call    PuDbgPrint
0x180011571  jmp     loc_1800113FB
0x180011576  lea     rcx, [rbx+8]; this
0x18001157a  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x18001157f  mov     edi, 8007006Dh
0x180011584  jmp     loc_1800113FB
```
