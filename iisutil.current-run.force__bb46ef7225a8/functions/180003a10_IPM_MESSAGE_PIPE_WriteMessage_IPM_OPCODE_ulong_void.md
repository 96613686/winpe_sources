# IPM_MESSAGE_PIPE::WriteMessage(IPM_OPCODE,ulong,void *)

- ea: `0x180003a10`
- end: `0x180004148`
- name: `?WriteMessage@IPM_MESSAGE_PIPE@@QEAAJW4IPM_OPCODE@@KPEAX@Z`
- size: `1848`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800039d0`
- `0x180003a10`
- `0x180004910`
- `0x180004f40`
- `0x180005184`
- `0x180007180`
- `0x180007300`
- `0x18001382c`
- `0x18002c476`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000403d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004130`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ba0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f05`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f75`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000403d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004096`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004130`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d98`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d98`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003b96`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003efb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004126`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003b96`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180003efb`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004126`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180003bc6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180003f24`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180003bc6`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180003f24`

## string_xrefs

- `0x180003b32`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180003d57`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180003dcb`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180003e24`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180003e53`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180003fd9`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180004072`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800040d4`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180003d45`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x180003dc0`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x180003e12`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x180003e48`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x180003fcd`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x180003d3a`: `IPM_MESSAGE_PIPE::WriteMessage failed IpmWriteFile, hr = %x\n`
- `0x180003af2`: `IpmWriteFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x180003dd2`: `IPM_MESSAGE_PIPE::WriteMessage failed CreateMessage, hr = %x\n`
- `0x180003e3c`: `IPM_MESSAGE_PIPE::WriteMessage called with opcode=%d, len=%d, writesize=%d\n`
- `0x180003e07`: `IPM_MESSAGE_PIPE::WriteMessage failed, hr = %x\n`
- `0x1800040bc`: `IpmWriteFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x1800040c8`: `IpmWriteFile`
- `0x180003b23`: `IpmWriteFileChunked`
- `0x18000405c`: `IpmWriteFileChunked`
- `0x180003fea`: `IPM_MESSAGE_PIPE::WriteMessage failed allocation of WriteBuffer, hr = %x, size=%d\n`

## pseudocode

```c
__int64 __fastcall IPM_MESSAGE_PIPE::WriteMessage(__int64 a1, int a2, unsigned int a3, const void *a4)
{
  size_t v4; // rbp
  unsigned int v8; // r12d
  int v9; // eax
  struct IPM_MESSAGE_IMP *v10; // rdi
  signed int v11; // esi
  void *v12; // rsi
  struct _OVERLAPPED *lpOverlapped; // rdx
  unsigned int v14; // r14d
  struct IPM_MESSAGE_IMP **p_Buffer; // r15
  DWORD v16; // r8d
  const void *v17; // r14
  void *v18; // rsi
  signed __int32 v19; // edx
  __int64 v20; // r14
  signed __int32 v21; // edx
  signed __int32 v23; // edx
  signed __int32 v24; // edx
  char *v25; // r14
  void *v26; // rsi
  unsigned int i; // r15d
  DWORD v28; // r8d
  signed int v29; // eax
  signed int v30; // eax
  signed int LastError; // eax
  int DataLength; // eax
  DWORD v33; // [rsp+50h] [rbp-38h] BYREF
  struct IPM_MESSAGE_IMP *Buffer; // [rsp+58h] [rbp-30h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+A0h] [rbp+18h] BYREF

  v4 = a3;
  Buffer = 0;
  if ( (unsigned __int64)a3 + 8 > 0xFFFFFFFF )
  {
    v11 = -2147024362;
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x58Cu,
        "IPM_MESSAGE_PIPE::WriteMessage",
        "IPM_MESSAGE_PIPE::WriteMessage failed, hr = %x\n",
        22);
    goto LABEL_30;
  }
  v8 = a3 + 8;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      0x5A1u,
      "IPM_MESSAGE_PIPE::WriteMessage",
      "IPM_MESSAGE_PIPE::WriteMessage called with opcode=%d, len=%d, writesize=%d\n",
      a2);
  v9 = IPM_MESSAGE_IMP::CreateMessage(&Buffer, (struct IPM_MESSAGE_PIPE *)a1, (unsigned int)(v4 + 8) > 0x10000);
  v10 = Buffer;
  v11 = v9;
  if ( v9 < 0 )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x5AAu,
        "IPM_MESSAGE_PIPE::WriteMessage",
        "IPM_MESSAGE_PIPE::WriteMessage failed CreateMessage, hr = %x\n",
        v9);
  }
  else
  {
    *((_DWORD *)Buffer + 3) = 1;
    if ( v8 > 0x10000 )
    {
      *((_DWORD *)v10 + 4) = v4;
      *((_QWORD *)v10 + 3) = a4;
      goto LABEL_7;
    }
    DataLength = IPM2_MESSAGE_IMP::AllocateDataLength(v10, v8);
    v11 = DataLength;
    if ( DataLength >= 0 )
    {
      **((_QWORD **)v10 + 3) = 0;
      **((_DWORD **)v10 + 3) = a2;
      *(_DWORD *)(*((_QWORD *)v10 + 3) + 4LL) = v8;
      if ( (_DWORD)v4 && a4 )
        memcpy_0((void *)(*((_QWORD *)v10 + 3) + 8LL), a4, v4);
      *((_DWORD *)v10 + 4) = v8;
LABEL_7:
      CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(a1 + 8));
      v12 = *(void **)(a1 + 16);
      if ( v12 == (void *)-1LL )
      {
        while ( 1 )
        {
          v24 = *(_DWORD *)(a1 + 8);
          if ( v24 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v24 - 1, v24) )
            break;
          _mm_pause();
        }
        v11 = -2147024787;
        goto LABEL_27;
      }
      if ( v8 <= 0x10000 )
      {
        _InterlockedIncrement((volatile signed __int32 *)v10 + 12);
        v17 = (const void *)*((_QWORD *)v10 + 3);
        v18 = *(void **)(a1 + 16);
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
            0x215u,
            "IpmWriteFile",
            "IpmWriteFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
            (char)v18);
        if ( v18 != (void *)-1LL && v17 && (_DWORD)v4 != -8 && v10 != (struct IPM_MESSAGE_IMP *)-56LL )
        {
          if ( WriteFile(v18, v17, v8, 0, (LPOVERLAPPED)((char *)v10 + 56)) || GetLastError() == 997 )
          {
            v11 = 0;
          }
          else
          {
            LastError = GetLastError();
            v11 = LastError;
            if ( LastError > 0 )
              v11 = (unsigned __int16)LastError | 0x80070000;
          }
          goto LABEL_24;
        }
      }
      else
      {
        lpOverlapped = (struct _OVERLAPPED *)((char *)v10 + 56);
        LODWORD(Buffer) = a2;
        HIDWORD(Buffer) = v4 + 8;
        NumberOfBytesTransferred = 0;
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
        {
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
            0x25Du,
            "IpmWriteFileChunked",
            "IpmWriteFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
            (char)v12);
          lpOverlapped = (struct _OVERLAPPED *)((char *)v10 + 56);
        }
        if ( lpOverlapped )
        {
          v14 = 0;
          p_Buffer = &Buffer;
          while ( v14 < 8 )
          {
            v16 = 8 - v14;
            if ( 8 - v14 > 0x10000 )
              v16 = 0x10000;
            if ( !WriteFile(v12, p_Buffer, v16, 0, lpOverlapped) && GetLastError() != 997 )
            {
              v30 = GetLastError();
              v11 = v30;
              if ( v30 > 0 )
                goto LABEL_60;
              goto LABEL_61;
            }
            if ( !GetOverlappedResult(v12, (LPOVERLAPPED)((char *)v10 + 56), &NumberOfBytesTransferred, 1) )
            {
              if ( !GetLastError() )
              {
                v11 = -2147467259;
                goto LABEL_24;
              }
              v30 = GetLastError();
              v11 = v30;
              if ( v30 > 0 )
LABEL_60:
                v11 = (unsigned __int16)v30 | 0x80070000;
LABEL_61:
              if ( v11 < 0 )
                goto LABEL_24;
              lpOverlapped = (struct _OVERLAPPED *)((char *)v10 + 56);
              break;
            }
            lpOverlapped = (struct _OVERLAPPED *)((char *)v10 + 56);
            p_Buffer = (struct IPM_MESSAGE_IMP **)((char *)p_Buffer + NumberOfBytesTransferred);
            v14 += NumberOfBytesTransferred;
          }
          v25 = (char *)*((_QWORD *)v10 + 3);
          v26 = *(void **)(a1 + 16);
          v33 = 0;
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
          {
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
              0x25Du,
              "IpmWriteFileChunked",
              "IpmWriteFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n",
              (char)v26);
            lpOverlapped = (struct _OVERLAPPED *)((char *)v10 + 56);
          }
          if ( v26 != (void *)-1LL && v25 && (_DWORD)v4 )
          {
            for ( i = 0; ; i += v33 )
            {
              if ( i >= (unsigned int)v4 )
              {
                v11 = 0;
                goto LABEL_24;
              }
              v28 = v4 - i;
              if ( (unsigned int)v4 - i > 0x10000 )
                v28 = 0x10000;
              if ( !WriteFile(v26, v25, v28, 0, lpOverlapped) && GetLastError() != 997 )
                break;
              if ( !GetOverlappedResult(v26, (LPOVERLAPPED)((char *)v10 + 56), &v33, 1) )
              {
                if ( !GetLastError() )
                {
                  v11 = -2147467259;
                  goto LABEL_24;
                }
                break;
              }
              lpOverlapped = (struct _OVERLAPPED *)((char *)v10 + 56);
              v25 += v33;
            }
            v29 = GetLastError();
            v11 = v29;
            if ( v29 > 0 )
              v11 = (unsigned __int16)v29 | 0x80070000;
            goto LABEL_24;
          }
        }
      }
      v11 = -2147024809;
LABEL_24:
      while ( 1 )
      {
        v19 = *(_DWORD *)(a1 + 8);
        if ( v19 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), v19 - 1, v19) )
          break;
        _mm_pause();
      }
      if ( v11 < 0 )
      {
        if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
            0x611u,
            "IPM_MESSAGE_PIPE::WriteMessage",
            "IPM_MESSAGE_PIPE::WriteMessage failed IpmWriteFile, hr = %x\n",
            v11);
        if ( v8 <= 0x10000 )
          IPM_MESSAGE_IMP::DereferenceMessage(v10);
      }
      goto LABEL_27;
    }
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x5BDu,
        "IPM_MESSAGE_PIPE::WriteMessage",
        "IPM_MESSAGE_PIPE::WriteMessage failed allocation of WriteBuffer, hr = %x, size=%d\n",
        DataLength);
  }
LABEL_27:
  if ( v10 )
    IPM_MESSAGE_IMP::DereferenceMessage(v10);
  if ( v11 < 0 )
  {
LABEL_30:
    v20 = 0;
    if ( *(_DWORD *)(a1 + 12)
      || (v21 = *(_DWORD *)(a1 + 8), (_WORD)v21)
      || v21 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), (v21 + 0x10000) | 0xFFFF, v21) )
    {
      if ( !CReaderWriterLock3::_TryWriteLock2((CReaderWriterLock3 *)(a1 + 8)) )
        CReaderWriterLock3::_WriteLockSpin((CReaderWriterLock3 *)(a1 + 8));
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)(a1 + 12), GetCurrentThreadId() & 0xFFFFFFFC | 1);
    }
    if ( *(_DWORD *)(a1 + 60) )
    {
      if ( *(int *)(a1 + 56) >= 0 )
        *(_DWORD *)(a1 + 56) = v11;
    }
    else if ( *(_QWORD *)(a1 + 24) )
    {
      v20 = *(_QWORD *)(a1 + 24);
      *(_QWORD *)(a1 + 24) = 0;
    }
    if ( ((*(_BYTE *)(a1 + 12) - 1) & 3) != 0 )
    {
      _InterlockedExchange((volatile __int32 *)(a1 + 12), *(_DWORD *)(a1 + 12) - 1);
    }
    else
    {
      _InterlockedExchange((volatile __int32 *)(a1 + 12), 0);
      while ( 1 )
      {
        v23 = *(_DWORD *)(a1 + 8);
        if ( v23 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 8), (v23 - 0x10000) & 0xFFFF0000, v23) )
          break;
        _mm_pause();
      }
    }
    if ( v20 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v20 + 16LL))(v20, (unsigned int)v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180003a10  mov     r11, rsp
0x180003a13  mov     [r11+10h], rbx
0x180003a17  mov     [r11+20h], rbp
0x180003a1b  push    rsi
0x180003a1c  push    rdi
0x180003a1d  push    r13
0x180003a1f  push    r14
0x180003a21  push    r15
0x180003a23  sub     rsp, 60h
0x180003a27  mov     ebp, r8d
0x180003a2a  mov     rbx, rcx
0x180003a2d  mov     ecx, 0FFFFFFFFh
0x180003a32  mov     qword ptr [r11-30h], 0
0x180003a3a  mov     r14, r9
0x180003a3d  mov     r13d, edx
0x180003a40  lea     rax, [rbp+8]
0x180003a44  cmp     rax, rcx
0x180003a47  ja      loc_180003DEE
0x180003a4d  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180003a53  xor     edi, edi
0x180003a55  mov     [r11+8], r12
0x180003a59  lea     r12d, [rbp+8]
0x180003a5d  cmp     r12d, 10000h
0x180003a64  setnbe  dil
0x180003a68  test    al, 3
0x180003a6a  setnz   cl
0x180003a6d  bt      eax, 1Ch
0x180003a71  setb    al
0x180003a74  test    al, cl
0x180003a76  jnz     loc_180003E35
0x180003a7c  mov     r8d, edi; int
0x180003a7f  lea     rcx, [rsp+88h+Buffer]; struct IPM_MESSAGE_IMP **
0x180003a84  mov     rdx, rbx; struct IPM_MESSAGE_PIPE *
0x180003a87  call    ?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z; IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)
0x180003a8c  mov     rdi, [rsp+88h+Buffer]
0x180003a91  mov     esi, eax
0x180003a93  test    eax, eax
0x180003a95  js      loc_180003DAC
0x180003a9b  mov     dword ptr [rdi+0Ch], 1
0x180003aa2  cmp     r12d, 10000h
0x180003aa9  jbe     loc_180003FA8
0x180003aaf  mov     [rdi+10h], ebp
0x180003ab2  mov     [rdi+18h], r14
0x180003ab6  lea     rcx, [rbx+8]; this
0x180003aba  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x180003abf  mov     rsi, [rbx+10h]
0x180003ac3  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180003ac7  jz      loc_180003D79
0x180003acd  mov     r9d, 10000h
0x180003ad3  cmp     r12d, r9d
0x180003ad6  jbe     loc_180003BED
0x180003adc  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180003ae2  lea     rdx, [rdi+38h]
0x180003ae6  test    al, 3
0x180003ae8  mov     dword ptr [rsp+88h+Buffer], r13d
0x180003aed  mov     dword ptr [rsp+88h+Buffer+4], r12d
0x180003af2  lea     r13, aIpmwritefilech; "IpmWriteFileChunked called with hFile=%"...
0x180003af9  setnz   cl
0x180003afc  mov     [rsp+88h+NumberOfBytesTransferred], 0
0x180003b07  bt      eax, 1Ch
0x180003b0b  setb    al
0x180003b0e  test    al, cl
0x180003b10  jz      short loc_180003B5D
0x180003b12  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180003b19  lea     rax, [rsp+88h+Buffer]
0x180003b1e  mov     [rsp+88h+var_48], rdx
0x180003b23  lea     r9, aIpmwritefilech_0; "IpmWriteFileChunked"
0x180003b2a  mov     [rsp+88h+var_50], 8
0x180003b32  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003b39  mov     [rsp+88h+var_58], rax
0x180003b3e  mov     r8d, 25Dh; unsigned int
0x180003b44  mov     qword ptr [rsp+88h+var_60], rsi; char
0x180003b49  mov     [rsp+88h+lpOverlapped], r13; char *
0x180003b4e  call    PuDbgPrint
0x180003b53  lea     rdx, [rdi+38h]
0x180003b57  mov     r9d, 10000h
0x180003b5d  test    rdx, rdx
0x180003b60  jz      loc_180003C21
0x180003b66  xor     r14d, r14d
0x180003b69  lea     r15, [rsp+88h+Buffer]
0x180003b6e  cmp     r14d, 8
0x180003b72  jnb     loc_180003E89
0x180003b78  mov     r8d, 8
0x180003b7e  mov     [rsp+88h+lpOverlapped], rdx; lpOverlapped
0x180003b83  sub     r8d, r14d
0x180003b86  mov     rdx, r15; lpBuffer
0x180003b89  cmp     r8d, r9d
0x180003b8c  mov     rcx, rsi; hFile
0x180003b8f  cmova   r8d, r9d; nNumberOfBytesToWrite
0x180003b93  xor     r9d, r9d; lpNumberOfBytesWritten
0x180003b96  call    cs:__imp_WriteFile
0x180003b9c  test    eax, eax
0x180003b9e  jnz     short loc_180003BB1
0x180003ba0  call    cs:__imp_GetLastError
0x180003ba6  cmp     eax, 3E5h
0x180003bab  jnz     loc_180003F60
0x180003bb1  mov     r9d, 1; bWait
0x180003bb7  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x180003bbf  lea     rdx, [rdi+38h]; lpOverlapped
0x180003bc3  mov     rcx, rsi; hFile
0x180003bc6  call    cs:__imp_GetOverlappedResult
0x180003bcc  test    eax, eax
0x180003bce  jz      loc_18000403D
0x180003bd4  mov     ecx, [rsp+88h+NumberOfBytesTransferred]
0x180003bdb  lea     rdx, [rdi+38h]
0x180003bdf  add     r15, rcx
0x180003be2  mov     r9d, 10000h
0x180003be8  add     r14d, ecx
0x180003beb  jmp     short loc_180003B6E
0x180003bed  lock inc dword ptr [rdi+30h]
0x180003bf1  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180003bf7  lea     rbp, [rdi+38h]
0x180003bfb  mov     r14, [rdi+18h]
0x180003bff  test    al, 3
0x180003c01  mov     rsi, [rbx+10h]
0x180003c05  setnz   cl
0x180003c08  bt      eax, 1Ch
0x180003c0c  setb    al
0x180003c0f  test    al, cl
0x180003c11  jnz     loc_1800040B5
0x180003c17  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180003c1b  jnz     loc_1800040FA
0x180003c21  mov     esi, 80070057h
0x180003c26  mov     r13d, 10000h
0x180003c2c  mov     edx, [rbx+8]
0x180003c2f  mov     eax, edx
0x180003c31  lea     ecx, [rdx-1]
0x180003c34  lock cmpxchg [rbx+8], ecx
0x180003c39  cmp     edx, eax
0x180003c3b  jz      short loc_180003C41
0x180003c3d  pause
0x180003c3f  jmp     short loc_180003C2C
0x180003c41  test    esi, esi
0x180003c43  js      loc_180003D2A
0x180003c49  mov     r12, [rsp+88h+arg_0]
0x180003c51  test    rdi, rdi
0x180003c54  jz      short loc_180003C5E
0x180003c56  mov     rcx, rdi; this
0x180003c59  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x180003c5e  test    esi, esi
0x180003c60  jns     short loc_180003CE1
0x180003c62  mov     eax, [rbx+0Ch]
0x180003c65  xor     r14d, r14d
0x180003c68  test    eax, eax
0x180003c6a  jnz     short loc_180003C8F
0x180003c6c  mov     edx, [rbx+8]
0x180003c6f  test    dx, dx
0x180003c72  jnz     short loc_180003C8F
0x180003c74  lea     ecx, [rdx+10000h]
0x180003c7a  mov     eax, edx
0x180003c7c  or      ecx, 0FFFFh
0x180003c82  lock cmpxchg [rbx+8], ecx
0x180003c87  cmp     edx, eax
0x180003c89  jz      loc_180003D98
0x180003c8f  lea     rcx, [rbx+8]; this
0x180003c93  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x180003c98  test    al, al
0x180003c9a  jnz     short loc_180003CA5
0x180003c9c  lea     rcx, [rbx+8]; this
0x180003ca0  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x180003ca5  cmp     [rbx+3Ch], r14d
0x180003ca9  jnz     short loc_180003CFC
0x180003cab  mov     rax, [rbx+18h]
0x180003caf  test    rax, rax
0x180003cb2  jz      short loc_180003CBF
0x180003cb4  mov     r14, rax
0x180003cb7  mov     qword ptr [rbx+18h], 0
0x180003cbf  mov     eax, [rbx+0Ch]
0x180003cc2  dec     eax
0x180003cc4  test    al, 3
0x180003cc6  jz      short loc_180003D07
0x180003cc8  xchg    eax, [rbx+0Ch]
0x180003ccb  test    r14, r14
0x180003cce  jz      short loc_180003CE1
0x180003cd0  mov     rax, [r14]
0x180003cd3  mov     edx, esi
0x180003cd5  mov     rcx, r14
0x180003cd8  mov     rax, [rax+10h]
0x180003cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ce1  lea     r11, [rsp+88h+var_28]
0x180003ce6  mov     eax, esi
0x180003ce8  mov     rbx, [r11+38h]
0x180003cec  mov     rbp, [r11+48h]
0x180003cf0  mov     rsp, r11
0x180003cf3  pop     r15
0x180003cf5  pop     r14
0x180003cf7  pop     r13
0x180003cf9  pop     rdi
0x180003cfa  pop     rsi
0x180003cfb  retn
0x180003cfc  cmp     [rbx+38h], r14d
0x180003d00  jl      short loc_180003CBF
0x180003d02  mov     [rbx+38h], esi
0x180003d05  jmp     short loc_180003CBF
0x180003d07  xor     eax, eax
0x180003d09  xchg    eax, [rbx+0Ch]
0x180003d0c  mov     edx, [rbx+8]
0x180003d0f  mov     eax, edx
0x180003d11  lea     ecx, [rdx-10000h]
0x180003d17  and     ecx, 0FFFF0000h
0x180003d1d  lock cmpxchg [rbx+8], ecx
0x180003d22  cmp     edx, eax
0x180003d24  jz      short loc_180003CCB
0x180003d26  pause
0x180003d28  jmp     short loc_180003D0C
0x180003d2a  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180003d31  jz      short loc_180003D63
0x180003d33  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180003d3a  lea     rax, aIpmMessagePipe_11; "IPM_MESSAGE_PIPE::WriteMessage failed I"...
0x180003d41  mov     dword ptr [rsp+88h+var_60], esi; char
0x180003d45  lea     r9, aIpmMessagePipe_7; "IPM_MESSAGE_PIPE::WriteMessage"
0x180003d4c  mov     r8d, 611h; unsigned int
0x180003d52  mov     [rsp+88h+lpOverlapped], rax; char *
0x180003d57  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003d5e  call    PuDbgPrint
0x180003d63  cmp     r12d, r13d
0x180003d66  ja      loc_180003C49
0x180003d6c  mov     rcx, rdi; this
0x180003d6f  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x180003d74  jmp     loc_180003C49
0x180003d79  mov     edx, [rbx+8]
0x180003d7c  mov     eax, edx
0x180003d7e  lea     ecx, [rdx-1]
0x180003d81  lock cmpxchg [rbx+8], ecx
0x180003d86  cmp     edx, eax
0x180003d88  jz      short loc_180003D8E
0x180003d8a  pause
0x180003d8c  jmp     short loc_180003D79
0x180003d8e  mov     esi, 8007006Dh
0x180003d93  jmp     loc_180003C49
0x180003d98  call    cs:__imp_GetCurrentThreadId
0x180003d9e  and     eax, 0FFFFFFFCh
0x180003da1  or      eax, 1
0x180003da4  xchg    eax, [rbx+0Ch]
0x180003da7  jmp     loc_180003CA5
0x180003dac  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180003db3  jz      loc_180003C49
0x180003db9  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180003dc0  lea     r9, aIpmMessagePipe_7; "IPM_MESSAGE_PIPE::WriteMessage"
0x180003dc7  mov     dword ptr [rsp+88h+var_60], eax; char
0x180003dcb  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003dd2  lea     rax, aIpmMessagePipe_24; "IPM_MESSAGE_PIPE::WriteMessage failed C"...
0x180003dd9  mov     r8d, 5AAh; unsigned int
0x180003ddf  mov     [rsp+88h+lpOverlapped], rax; char *
0x180003de4  call    PuDbgPrint
0x180003de9  jmp     loc_180003C49
0x180003dee  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180003df5  mov     esi, 80070216h
0x180003dfa  jz      loc_180003C62
0x180003e00  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180003e07  lea     rax, aIpmMessagePipe_25; "IPM_MESSAGE_PIPE::WriteMessage failed, "...
0x180003e0e  mov     dword ptr [rsp+88h+var_60], esi; char
0x180003e12  lea     r9, aIpmMessagePipe_7; "IPM_MESSAGE_PIPE::WriteMessage"
0x180003e19  mov     r8d, 58Ch; unsigned int
0x180003e1f  mov     [rsp+88h+lpOverlapped], rax; char *
0x180003e24  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003e2b  call    PuDbgPrint
0x180003e30  jmp     loc_180003C62
0x180003e35  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180003e3c  lea     rax, aIpmMessagePipe_28; "IPM_MESSAGE_PIPE::WriteMessage called w"...
0x180003e43  mov     [rsp+88h+var_50], r12d
0x180003e48  lea     r9, aIpmMessagePipe_7; "IPM_MESSAGE_PIPE::WriteMessage"
0x180003e4f  mov     dword ptr [rsp+88h+var_58], ebp
0x180003e53  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180003e5a  mov     dword ptr [rsp+88h+var_60], r13d; char
0x180003e5f  mov     r8d, 5A1h; unsigned int
0x180003e65  mov     [rsp+88h+lpOverlapped], rax; char *
0x180003e6a  call    PuDbgPrint
0x180003e6f  jmp     loc_180003A7C
0x180003e74  movzx   esi, ax
0x180003e77  or      esi, 80070000h
0x180003e7d  test    esi, esi
0x180003e7f  js      loc_180003C26
0x180003e85  lea     rdx, [rdi+38h]
0x180003e89  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180003e8f  test    al, 3
0x180003e91  mov     r14, [rdi+18h]
0x180003e95  mov     rsi, [rbx+10h]
0x180003e99  setnz   cl
0x180003e9c  bt      eax, 1Ch
0x180003ea0  mov     [rsp+88h+var_38], 0
0x180003ea8  setb    al
0x180003eab  test    al, cl
0x180003ead  jnz     loc_180004055
0x180003eb3  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180003eb7  jz      loc_180003C21
0x180003ebd  test    r14, r14
0x180003ec0  jz      loc_180003C21
0x180003ec6  test    ebp, ebp
0x180003ec8  jz      loc_180003C21
0x180003ece  xor     r15d, r15d
0x180003ed1  mov     r13d, 10000h
0x180003ed7  cmp     r15d, ebp
0x180003eda  jnb     loc_1800040AE
0x180003ee0  mov     r8d, ebp
0x180003ee3  mov     [rsp+88h+lpOverlapped], rdx; lpOverlapped
0x180003ee8  sub     r8d, r15d
0x180003eeb  mov     rdx, r14; lpBuffer
0x180003eee  cmp     r8d, r13d
0x180003ef1  mov     rcx, rsi; hFile
  ... truncated ...
```
