# IPM_MESSAGE_PIPE::ReadMessage(ulong)

- ea: `0x180010080`
- end: `0x1800103e0`
- name: `?ReadMessage@IPM_MESSAGE_PIPE@@AEAAJK@Z`
- size: `864`
- prototype: `__int64 __fastcall(IPM_MESSAGE_PIPE *this, unsigned int)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004910`
- `0x180004f40`
- `0x180005110`
- `0x180005184`
- `0x180007300`
- `0x1800081e0`
- `0x18000e850`
- `0x180010080`
- `0x1800183f8`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800101c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800102d3`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800101d9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800101d9`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800101ba`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800101ba`

## string_xrefs

- `0x180010174`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180010240`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180010310`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180010371`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800103b1`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180010169`: `IpmReadFile`
- `0x18001015d`: `IpmReadFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x18001022e`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180010305`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x18001035f`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x1800103a6`: `IPM_MESSAGE_PIPE::ReadMessage`
- `0x180010223`: `IPM_MESSAGE_PIPE::ReadMessage failed IpmReadFile, hr = %x\n`
- `0x180010354`: `IPM_MESSAGE_PIPE::ReadMessage called with size=%d\n`
- `0x180010317`: `IPM_MESSAGE_PIPE::ReadMessage failed CreateMessage, hr = %x\n`
- `0x18001039b`: `IPM_MESSAGE_PIPE::ReadMessage failed allocation of Read Buffer, hr = %x, size = %d\n`

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
0x180010080  mov     [rsp+arg_18], rbx
0x180010085  push    rsi
0x180010086  push    rdi
0x180010087  push    r15
0x180010089  sub     rsp, 50h
0x18001008d  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180010093  xor     r15d, r15d
0x180010096  test    al, 3
0x180010098  mov     esi, edx
0x18001009a  mov     rbx, rcx
0x18001009d  mov     [rsp+68h+arg_10], r15
0x1800100a5  setnz   r8b
0x1800100a9  bt      eax, 1Ch
0x1800100ad  setb    al
0x1800100b0  test    al, r8b
0x1800100b3  jnz     loc_18001034D
0x1800100b9  xor     r8d, r8d; int
0x1800100bc  mov     [rsp+68h+arg_0], rbp
0x1800100c1  mov     rdx, rbx; struct IPM_MESSAGE_PIPE *
0x1800100c4  lea     rcx, [rsp+68h+arg_10]; struct IPM_MESSAGE_IMP **
0x1800100cc  call    ?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z; IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)
0x1800100d1  mov     edi, eax
0x1800100d3  test    eax, eax
0x1800100d5  js      loc_1800102F1
0x1800100db  mov     rax, [rsp+68h+arg_10]
0x1800100e3  mov     rcx, rsi; Size
0x1800100e6  mov     [rax+0Ch], r15d
0x1800100ea  mov     rdi, [rsp+68h+arg_10]
0x1800100f2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800100f7  test    rax, rax
0x1800100fa  jz      loc_180010382
0x180010100  lea     rcx, [rbx+8]; this
0x180010104  mov     [rdi+18h], rax
0x180010108  mov     [rdi+10h], esi
0x18001010b  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180010110  cmp     qword ptr [rbx+10h], 0FFFFFFFFFFFFFFFFh
0x180010115  jz      loc_1800103CD
0x18001011b  mov     rax, [rsp+68h+arg_10]
0x180010123  mov     [rsp+68h+arg_8], r14
0x180010128  lock inc dword ptr [rax+30h]
0x18001012c  mov     rax, [rsp+68h+arg_10]
0x180010134  mov     r14, [rbx+10h]
0x180010138  mov     rbp, [rax+18h]
0x18001013c  lea     rdi, [rax+38h]
0x180010140  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180010146  test    al, 3
0x180010148  setnz   cl
0x18001014b  bt      eax, 1Ch
0x18001014f  setb    al
0x180010152  test    al, cl
0x180010154  jz      short loc_180010195
0x180010156  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001015d  lea     rax, aIpmreadfileCal; "IpmReadFile called with hFile=%d, pBuff"...
0x180010164  mov     [rsp+68h+var_28], rdi
0x180010169  lea     r9, aIpmreadfile; "IpmReadFile"
0x180010170  mov     [rsp+68h+var_30], esi
0x180010174  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18001017b  mov     [rsp+68h+var_38], rbp
0x180010180  mov     r8d, 14Ch; unsigned int
0x180010186  mov     qword ptr [rsp+68h+var_40], r14; char
0x18001018b  mov     [rsp+68h+lpOverlapped], rax; char *
0x180010190  call    PuDbgPrint
0x180010195  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180010199  jz      short loc_1800101E4
0x18001019b  test    rbp, rbp
0x18001019e  jz      short loc_1800101E4
0x1800101a0  test    esi, esi
0x1800101a2  jz      short loc_1800101E4
0x1800101a4  test    rdi, rdi
0x1800101a7  jz      short loc_1800101E4
0x1800101a9  xor     r9d, r9d; lpNumberOfBytesRead
0x1800101ac  mov     [rsp+68h+lpOverlapped], rdi; lpOverlapped
0x1800101b1  mov     r8d, esi; nNumberOfBytesToRead
0x1800101b4  mov     rdx, rbp; lpBuffer
0x1800101b7  mov     rcx, r14; hFile
0x1800101ba  call    cs:__imp_ReadFile
0x1800101c0  test    eax, eax
0x1800101c2  jnz     short loc_1800101DF
0x1800101c4  call    cs:__imp_GetLastError
0x1800101ca  cmp     eax, 0EAh
0x1800101cf  jnz     loc_1800102D3
0x1800101d5  mov     rcx, [rdi+18h]; hEvent
0x1800101d9  call    cs:__imp_SetEvent
0x1800101df  mov     edi, r15d
0x1800101e2  jmp     short loc_1800101E9
0x1800101e4  mov     edi, 80070057h
0x1800101e9  mov     r14, [rsp+68h+arg_8]
0x1800101ee  mov     ecx, [rbx+8]
0x1800101f1  mov     eax, ecx
0x1800101f3  lea     edx, [rcx-1]
0x1800101f6  lock cmpxchg [rbx+8], edx
0x1800101fb  cmp     ecx, eax
0x1800101fd  jz      short loc_180010203
0x1800101ff  pause
0x180010201  jmp     short loc_1800101EE
0x180010203  test    edi, edi
0x180010205  jns     short loc_180010259
0x180010207  cmp     edi, 800703E5h
0x18001020d  jz      loc_180010333
0x180010213  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18001021a  jz      short loc_18001024C
0x18001021c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180010223  lea     rax, aIpmMessagePipe_5; "IPM_MESSAGE_PIPE::ReadMessage failed Ip"...
0x18001022a  mov     dword ptr [rsp+68h+var_40], edi; char
0x18001022e  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x180010235  mov     r8d, 54Bh; unsigned int
0x18001023b  mov     [rsp+68h+lpOverlapped], rax; char *
0x180010240  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180010247  call    PuDbgPrint
0x18001024c  mov     rcx, [rsp+68h+arg_10]; this
0x180010254  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x180010259  mov     rcx, [rsp+68h+arg_10]; this
0x180010261  test    rcx, rcx
0x180010264  jnz     loc_18001033B
0x18001026a  test    edi, edi
0x18001026c  jns     short loc_1800102A7
0x18001026e  lea     rcx, [rbx+8]; this
0x180010272  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180010277  cmp     [rbx+3Ch], r15d
0x18001027b  jnz     short loc_1800102BF
0x18001027d  mov     rax, [rbx+18h]
0x180010281  test    rax, rax
0x180010284  jz      short loc_1800102C8
0x180010286  lea     rcx, [rbx+8]; this
0x18001028a  mov     [rbx+18h], r15
0x18001028e  mov     rsi, rax
0x180010291  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180010296  mov     rax, [rsi]
0x180010299  mov     edx, edi
0x18001029b  mov     rcx, rsi
0x18001029e  mov     rax, [rax+10h]
0x1800102a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102a7  mov     rbp, [rsp+68h+arg_0]
0x1800102ac  mov     eax, edi
0x1800102ae  mov     rbx, [rsp+68h+arg_18]
0x1800102b6  add     rsp, 50h
0x1800102ba  pop     r15
0x1800102bc  pop     rdi
0x1800102bd  pop     rsi
0x1800102be  retn
0x1800102bf  cmp     [rbx+38h], r15d
0x1800102c3  jl      short loc_1800102C8
0x1800102c5  mov     [rbx+38h], edi
0x1800102c8  lea     rcx, [rbx+8]; this
0x1800102cc  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800102d1  jmp     short loc_1800102A7
0x1800102d3  call    cs:__imp_GetLastError
0x1800102d9  mov     edi, eax
0x1800102db  test    eax, eax
0x1800102dd  jle     loc_1800101E9
0x1800102e3  movzx   edi, ax
0x1800102e6  or      edi, 80070000h
0x1800102ec  jmp     loc_1800101E9
0x1800102f1  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800102f8  jz      loc_180010259
0x1800102fe  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180010305  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x18001030c  mov     dword ptr [rsp+68h+var_40], eax; char
0x180010310  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180010317  lea     rax, aIpmMessagePipe_20; "IPM_MESSAGE_PIPE::ReadMessage failed Cr"...
0x18001031e  mov     r8d, 51Ah; unsigned int
0x180010324  mov     [rsp+68h+lpOverlapped], rax; char *
0x180010329  call    PuDbgPrint
0x18001032e  jmp     loc_180010259
0x180010333  mov     edi, r15d
0x180010336  jmp     loc_180010259
0x18001033b  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x180010340  mov     [rsp+68h+arg_10], r15
0x180010348  jmp     loc_18001026A
0x18001034d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180010354  lea     rax, aIpmMessagePipe_12; "IPM_MESSAGE_PIPE::ReadMessage called wi"...
0x18001035b  mov     dword ptr [rsp+68h+var_40], esi; char
0x18001035f  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x180010366  mov     r8d, 511h; unsigned int
0x18001036c  mov     [rsp+68h+lpOverlapped], rax; char *
0x180010371  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180010378  call    PuDbgPrint
0x18001037d  jmp     loc_1800100B9
0x180010382  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180010389  mov     edi, 8007000Eh
0x18001038e  jz      loc_180010259
0x180010394  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18001039b  lea     rax, aIpmMessagePipe_19; "IPM_MESSAGE_PIPE::ReadMessage failed al"...
0x1800103a2  mov     dword ptr [rsp+68h+var_38], esi
0x1800103a6  lea     r9, aIpmMessagePipe_6; "IPM_MESSAGE_PIPE::ReadMessage"
0x1800103ad  mov     dword ptr [rsp+68h+var_40], edi; char
0x1800103b1  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800103b8  mov     r8d, 527h; unsigned int
0x1800103be  mov     [rsp+68h+lpOverlapped], rax; char *
0x1800103c3  call    PuDbgPrint
0x1800103c8  jmp     loc_180010259
0x1800103cd  lea     rcx, [rbx+8]; this
0x1800103d1  call    ?ReadUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadUnlock(void)
0x1800103d6  mov     edi, 8007006Dh
0x1800103db  jmp     loc_180010259
```
