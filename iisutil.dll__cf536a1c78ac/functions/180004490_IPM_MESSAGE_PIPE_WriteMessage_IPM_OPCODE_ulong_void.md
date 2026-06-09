# IPM_MESSAGE_PIPE::WriteMessage(IPM_OPCODE,ulong,void *)

- ea: `0x180004490`
- end: `0x180004c26`
- name: `?WriteMessage@IPM_MESSAGE_PIPE@@QEAAJW4IPM_OPCODE@@KPEAX@Z`
- size: `1942`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, const void *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004450`
- `0x180004490`
- `0x180005460`
- `0x180005aa0`
- `0x180005d00`
- `0x180007e60`
- `0x180008000`
- `0x180014288`
- `0x18002e516`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c08`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004626`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800049f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004a4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004c08`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000482e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000482e`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004616`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004997`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004bf8`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004616`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004997`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180004bf8`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180004652`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800049cc`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x180004652`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x1800049cc`

## string_xrefs

- `0x1800045b2`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800047ed`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180004867`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800048c0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800048ef`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180004a9f`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180004b3e`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180004ba6`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x1800047db`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x18000485c`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x1800048ae`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x1800048e4`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x180004a93`: `IPM_MESSAGE_PIPE::WriteMessage`
- `0x1800047d0`: `IPM_MESSAGE_PIPE::WriteMessage failed IpmWriteFile, hr = %x\n`
- `0x180004572`: `IpmWriteFileChunked called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x18000486e`: `IPM_MESSAGE_PIPE::WriteMessage failed CreateMessage, hr = %x\n`
- `0x1800048d8`: `IPM_MESSAGE_PIPE::WriteMessage called with opcode=%d, len=%d, writesize=%d\n`
- `0x1800048a3`: `IPM_MESSAGE_PIPE::WriteMessage failed, hr = %x\n`
- `0x180004b8e`: `IpmWriteFile called with hFile=%d, pBuffer=%p, cbBuffer=%d, pOvl=%p\n`
- `0x180004b9a`: `IpmWriteFile`
- `0x1800045a3`: `IpmWriteFileChunked`
- `0x180004b28`: `IpmWriteFileChunked`
- `0x180004ab0`: `IPM_MESSAGE_PIPE::WriteMessage failed allocation of WriteBuffer, hr = %x, size=%d\n`

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
0x180004490  mov     r11, rsp
0x180004493  mov     [r11+10h], rbx
0x180004497  mov     [r11+20h], rbp
0x18000449b  push    rsi
0x18000449c  push    rdi
0x18000449d  push    r13
0x18000449f  push    r14
0x1800044a1  push    r15
0x1800044a3  sub     rsp, 60h
0x1800044a7  mov     ebp, r8d
0x1800044aa  mov     rbx, rcx
0x1800044ad  mov     ecx, 0FFFFFFFFh
0x1800044b2  mov     qword ptr [r11-30h], 0
0x1800044ba  mov     r14, r9
0x1800044bd  mov     r13d, edx
0x1800044c0  lea     rax, [rbp+8]
0x1800044c4  cmp     rax, rcx
0x1800044c7  ja      loc_18000488A
0x1800044cd  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800044d3  xor     edi, edi
0x1800044d5  mov     [r11+8], r12
0x1800044d9  lea     r12d, [rbp+8]
0x1800044dd  cmp     r12d, 10000h
0x1800044e4  setnbe  dil
0x1800044e8  test    al, 3
0x1800044ea  setnz   cl
0x1800044ed  bt      eax, 1Ch
0x1800044f1  setb    al
0x1800044f4  test    al, cl
0x1800044f6  jnz     loc_1800048D1
0x1800044fc  mov     r8d, edi; int
0x1800044ff  lea     rcx, [rsp+88h+Buffer]; struct IPM_MESSAGE_IMP **
0x180004504  mov     rdx, rbx; struct IPM_MESSAGE_PIPE *
0x180004507  call    ?CreateMessage@IPM_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM_MESSAGE_PIPE@@H@Z; IPM_MESSAGE_IMP::CreateMessage(IPM_MESSAGE_IMP * *,IPM_MESSAGE_PIPE *,int)
0x18000450c  mov     rdi, [rsp+88h+Buffer]
0x180004511  mov     esi, eax
0x180004513  test    eax, eax
0x180004515  js      loc_180004848
0x18000451b  mov     dword ptr [rdi+0Ch], 1
0x180004522  cmp     r12d, 10000h
0x180004529  jbe     loc_180004A6E
0x18000452f  mov     [rdi+10h], ebp
0x180004532  mov     [rdi+18h], r14
0x180004536  lea     rcx, [rbx+8]; this
0x18000453a  call    ?ReadLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::ReadLock(void)
0x18000453f  mov     rsi, [rbx+10h]
0x180004543  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180004547  jz      loc_18000480F
0x18000454d  mov     r9d, 10000h
0x180004553  cmp     r12d, r9d
0x180004556  jbe     loc_180004682
0x18000455c  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180004562  lea     rdx, [rdi+38h]
0x180004566  test    al, 3
0x180004568  mov     dword ptr [rsp+88h+Buffer], r13d
0x18000456d  mov     dword ptr [rsp+88h+Buffer+4], r12d
0x180004572  lea     r13, aIpmwritefilech; "IpmWriteFileChunked called with hFile=%"...
0x180004579  setnz   cl
0x18000457c  mov     [rsp+88h+NumberOfBytesTransferred], 0
0x180004587  bt      eax, 1Ch
0x18000458b  setb    al
0x18000458e  test    al, cl
0x180004590  jz      short loc_1800045DD
0x180004592  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180004599  lea     rax, [rsp+88h+Buffer]
0x18000459e  mov     [rsp+88h+var_48], rdx
0x1800045a3  lea     r9, aIpmwritefilech_0; "IpmWriteFileChunked"
0x1800045aa  mov     [rsp+88h+var_50], 8
0x1800045b2  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800045b9  mov     [rsp+88h+var_58], rax
0x1800045be  mov     r8d, 25Dh; unsigned int
0x1800045c4  mov     qword ptr [rsp+88h+var_60], rsi; char
0x1800045c9  mov     [rsp+88h+lpOverlapped], r13; char *
0x1800045ce  call    PuDbgPrint
0x1800045d3  lea     rdx, [rdi+38h]
0x1800045d7  mov     r9d, 10000h
0x1800045dd  test    rdx, rdx
0x1800045e0  jz      loc_1800046B6
0x1800045e6  xor     r14d, r14d
0x1800045e9  lea     r15, [rsp+88h+Buffer]
0x1800045ee  cmp     r14d, 8
0x1800045f2  jnb     loc_180004925
0x1800045f8  mov     r8d, 8
0x1800045fe  mov     [rsp+88h+lpOverlapped], rdx; lpOverlapped
0x180004603  sub     r8d, r14d
0x180004606  mov     rdx, r15; lpBuffer
0x180004609  cmp     r8d, r9d
0x18000460c  mov     rcx, rsi; hFile
0x18000460f  cmova   r8d, r9d; nNumberOfBytesToWrite
0x180004613  xor     r9d, r9d; lpNumberOfBytesWritten
0x180004616  call    cs:__imp_WriteFile
0x18000461d  nop     dword ptr [rax+rax+00h]
0x180004622  test    eax, eax
0x180004624  jnz     short loc_18000463D
0x180004626  call    cs:__imp_GetLastError
0x18000462d  nop     dword ptr [rax+rax+00h]
0x180004632  cmp     eax, 3E5h
0x180004637  jnz     loc_180004A14
0x18000463d  mov     r9d, 1; bWait
0x180004643  lea     r8, [rsp+88h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18000464b  lea     rdx, [rdi+38h]; lpOverlapped
0x18000464f  mov     rcx, rsi; hFile
0x180004652  call    cs:__imp_GetOverlappedResult
0x180004659  nop     dword ptr [rax+rax+00h]
0x18000465e  test    eax, eax
0x180004660  jz      loc_180004B03
0x180004666  mov     ecx, [rsp+88h+NumberOfBytesTransferred]
0x18000466d  lea     rdx, [rdi+38h]
0x180004671  add     r15, rcx
0x180004674  mov     r9d, 10000h
0x18000467a  add     r14d, ecx
0x18000467d  jmp     loc_1800045EE
0x180004682  lock inc dword ptr [rdi+30h]
0x180004686  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18000468c  lea     rbp, [rdi+38h]
0x180004690  mov     r14, [rdi+18h]
0x180004694  test    al, 3
0x180004696  mov     rsi, [rbx+10h]
0x18000469a  setnz   cl
0x18000469d  bt      eax, 1Ch
0x1800046a1  setb    al
0x1800046a4  test    al, cl
0x1800046a6  jnz     loc_180004B87
0x1800046ac  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800046b0  jnz     loc_180004BCC
0x1800046b6  mov     esi, 80070057h
0x1800046bb  mov     r13d, 10000h
0x1800046c1  mov     edx, [rbx+8]
0x1800046c4  mov     eax, edx
0x1800046c6  lea     ecx, [rdx-1]
0x1800046c9  lock cmpxchg [rbx+8], ecx
0x1800046ce  cmp     edx, eax
0x1800046d0  jz      short loc_1800046D6
0x1800046d2  pause
0x1800046d4  jmp     short loc_1800046C1
0x1800046d6  test    esi, esi
0x1800046d8  js      loc_1800047C0
0x1800046de  mov     r12, [rsp+88h+arg_0]
0x1800046e6  test    rdi, rdi
0x1800046e9  jz      short loc_1800046F3
0x1800046eb  mov     rcx, rdi; this
0x1800046ee  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x1800046f3  test    esi, esi
0x1800046f5  jns     short loc_180004776
0x1800046f7  mov     eax, [rbx+0Ch]
0x1800046fa  xor     r14d, r14d
0x1800046fd  test    eax, eax
0x1800046ff  jnz     short loc_180004724
0x180004701  mov     edx, [rbx+8]
0x180004704  test    dx, dx
0x180004707  jnz     short loc_180004724
0x180004709  lea     ecx, [rdx+10000h]
0x18000470f  mov     eax, edx
0x180004711  or      ecx, 0FFFFh
0x180004717  lock cmpxchg [rbx+8], ecx
0x18000471c  cmp     edx, eax
0x18000471e  jz      loc_18000482E
0x180004724  lea     rcx, [rbx+8]; this
0x180004728  call    ?_TryWriteLock2@CReaderWriterLock3@@AEAA_NXZ; CReaderWriterLock3::_TryWriteLock2(void)
0x18000472d  test    al, al
0x18000472f  jnz     short loc_18000473A
0x180004731  lea     rcx, [rbx+8]; this
0x180004735  call    ?_WriteLockSpin@CReaderWriterLock3@@AEAAXXZ; CReaderWriterLock3::_WriteLockSpin(void)
0x18000473a  cmp     [rbx+3Ch], r14d
0x18000473e  jnz     short loc_180004792
0x180004740  mov     rax, [rbx+18h]
0x180004744  test    rax, rax
0x180004747  jz      short loc_180004754
0x180004749  mov     r14, rax
0x18000474c  mov     qword ptr [rbx+18h], 0
0x180004754  mov     eax, [rbx+0Ch]
0x180004757  dec     eax
0x180004759  test    al, 3
0x18000475b  jz      short loc_18000479D
0x18000475d  xchg    eax, [rbx+0Ch]
0x180004760  test    r14, r14
0x180004763  jz      short loc_180004776
0x180004765  mov     rax, [r14]
0x180004768  mov     edx, esi
0x18000476a  mov     rcx, r14
0x18000476d  mov     rax, [rax+10h]
0x180004771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004776  lea     r11, [rsp+88h+var_28]
0x18000477b  mov     eax, esi
0x18000477d  mov     rbx, [r11+38h]
0x180004781  mov     rbp, [r11+48h]
0x180004785  mov     rsp, r11
0x180004788  pop     r15
0x18000478a  pop     r14
0x18000478c  pop     r13
0x18000478e  pop     rdi
0x18000478f  pop     rsi
0x180004790  retn
0x180004792  cmp     [rbx+38h], r14d
0x180004796  jl      short loc_180004754
0x180004798  mov     [rbx+38h], esi
0x18000479b  jmp     short loc_180004754
0x18000479d  xor     eax, eax
0x18000479f  xchg    eax, [rbx+0Ch]
0x1800047a2  mov     edx, [rbx+8]
0x1800047a5  mov     eax, edx
0x1800047a7  lea     ecx, [rdx-10000h]
0x1800047ad  and     ecx, 0FFFF0000h
0x1800047b3  lock cmpxchg [rbx+8], ecx
0x1800047b8  cmp     edx, eax
0x1800047ba  jz      short loc_180004760
0x1800047bc  pause
0x1800047be  jmp     short loc_1800047A2
0x1800047c0  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800047c7  jz      short loc_1800047F9
0x1800047c9  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800047d0  lea     rax, aIpmMessagePipe_11; "IPM_MESSAGE_PIPE::WriteMessage failed I"...
0x1800047d7  mov     dword ptr [rsp+88h+var_60], esi; char
0x1800047db  lea     r9, aIpmMessagePipe_7; "IPM_MESSAGE_PIPE::WriteMessage"
0x1800047e2  mov     r8d, 611h; unsigned int
0x1800047e8  mov     [rsp+88h+lpOverlapped], rax; char *
0x1800047ed  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800047f4  call    PuDbgPrint
0x1800047f9  cmp     r12d, r13d
0x1800047fc  ja      loc_1800046DE
0x180004802  mov     rcx, rdi; this
0x180004805  call    ?DereferenceMessage@IPM_MESSAGE_IMP@@QEAAXXZ; IPM_MESSAGE_IMP::DereferenceMessage(void)
0x18000480a  jmp     loc_1800046DE
0x18000480f  mov     edx, [rbx+8]
0x180004812  mov     eax, edx
0x180004814  lea     ecx, [rdx-1]
0x180004817  lock cmpxchg [rbx+8], ecx
0x18000481c  cmp     edx, eax
0x18000481e  jz      short loc_180004824
0x180004820  pause
0x180004822  jmp     short loc_18000480F
0x180004824  mov     esi, 8007006Dh
0x180004829  jmp     loc_1800046DE
0x18000482e  call    cs:__imp_GetCurrentThreadId
0x180004835  nop     dword ptr [rax+rax+00h]
0x18000483a  and     eax, 0FFFFFFFCh
0x18000483d  or      eax, 1
0x180004840  xchg    eax, [rbx+0Ch]
0x180004843  jmp     loc_18000473A
0x180004848  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18000484f  jz      loc_1800046DE
0x180004855  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18000485c  lea     r9, aIpmMessagePipe_7; "IPM_MESSAGE_PIPE::WriteMessage"
0x180004863  mov     dword ptr [rsp+88h+var_60], eax; char
0x180004867  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18000486e  lea     rax, aIpmMessagePipe_24; "IPM_MESSAGE_PIPE::WriteMessage failed C"...
0x180004875  mov     r8d, 5AAh; unsigned int
0x18000487b  mov     [rsp+88h+lpOverlapped], rax; char *
0x180004880  call    PuDbgPrint
0x180004885  jmp     loc_1800046DE
0x18000488a  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180004891  mov     esi, 80070216h
0x180004896  jz      loc_1800046F7
0x18000489c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800048a3  lea     rax, aIpmMessagePipe_25; "IPM_MESSAGE_PIPE::WriteMessage failed, "...
0x1800048aa  mov     dword ptr [rsp+88h+var_60], esi; char
0x1800048ae  lea     r9, aIpmMessagePipe_7; "IPM_MESSAGE_PIPE::WriteMessage"
0x1800048b5  mov     r8d, 58Ch; unsigned int
0x1800048bb  mov     [rsp+88h+lpOverlapped], rax; char *
0x1800048c0  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800048c7  call    PuDbgPrint
0x1800048cc  jmp     loc_1800046F7
0x1800048d1  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800048d8  lea     rax, aIpmMessagePipe_28; "IPM_MESSAGE_PIPE::WriteMessage called w"...
0x1800048df  mov     [rsp+88h+var_50], r12d
0x1800048e4  lea     r9, aIpmMessagePipe_7; "IPM_MESSAGE_PIPE::WriteMessage"
0x1800048eb  mov     dword ptr [rsp+88h+var_58], ebp
0x1800048ef  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800048f6  mov     dword ptr [rsp+88h+var_60], r13d; char
0x1800048fb  mov     r8d, 5A1h; unsigned int
0x180004901  mov     [rsp+88h+lpOverlapped], rax; char *
0x180004906  call    PuDbgPrint
0x18000490b  jmp     loc_1800044FC
0x180004910  movzx   esi, ax
0x180004913  or      esi, 80070000h
0x180004919  test    esi, esi
0x18000491b  js      loc_1800046BB
0x180004921  lea     rdx, [rdi+38h]
0x180004925  mov     eax, cs:g_dwDebugFlagsIISUtil
0x18000492b  test    al, 3
0x18000492d  mov     r14, [rdi+18h]
0x180004931  mov     rsi, [rbx+10h]
0x180004935  setnz   cl
0x180004938  bt      eax, 1Ch
0x18000493c  mov     [rsp+88h+var_38], 0
0x180004944  setb    al
0x180004947  test    al, cl
0x180004949  jnz     loc_180004B21
0x18000494f  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x180004953  jz      loc_1800046B6
0x180004959  test    r14, r14
0x18000495c  jz      loc_1800046B6
0x180004962  test    ebp, ebp
0x180004964  jz      loc_1800046B6
0x18000496a  xor     r15d, r15d
0x18000496d  mov     r13d, 10000h
0x180004973  cmp     r15d, ebp
0x180004976  jnb     loc_180004B80
0x18000497c  mov     r8d, ebp
0x18000497f  mov     [rsp+88h+lpOverlapped], rdx; lpOverlapped
  ... truncated ...
```
