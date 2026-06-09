# IPM_MESSAGE_PIPE::DestroyIpmMessagePipe(void)

- ea: `0x180026d10`
- end: `0x180026f47`
- name: `?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ`
- size: `567`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005110`
- `0x180007300`
- `0x1800081e0`
- `0x1800086e0`
- `0x180026d10`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e8d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026d9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026dca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026e8d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026e70`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026ed9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026e70`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180026ed9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026eed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026f17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026eed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026f17`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180026dc0`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180026e83`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180026dc0`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180026e83`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x180026d92`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x180026d92`

## string_xrefs

- `0x180026d50`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180026df8`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180026e44`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180026eaa`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`

## pseudocode

```c
void __fastcall IPM_MESSAGE_PIPE::DestroyIpmMessagePipe(IPM_MESSAGE_PIPE *this)
{
  unsigned int v1; // ebp
  __int64 v3; // rbx
  unsigned int v4; // r8d
  char *v5; // rax

  v1 = 0;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
      0x417u,
      "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe",
      "IPM_MESSAGE_PIPE::DestroyMessagePipe called this=%p\n",
      (char)this);
  CReaderWriterLock3::WriteLock((IPM_MESSAGE_PIPE *)((char *)this + 8));
  v3 = *((_QWORD *)this + 2);
  *((_QWORD *)this + 2) = -1;
  CReaderWriterLock3::WriteUnlock((IPM_MESSAGE_PIPE *)((char *)this + 8));
  if ( *((_DWORD *)this + 8) )
  {
    if ( DisconnectNamedPipe((HANDLE)v3) )
      goto LABEL_12;
    GetLastError();
    if ( (g_dwDebugFlagsIISUtil & 3) == 0 )
      goto LABEL_12;
    v4 = 1066;
    v5 = "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe error calling DisconnectNamedPipe on handle %p, GetLastError: %d\n";
  }
  else
  {
    if ( CancelIoEx((HANDLE)v3, 0) || GetLastError() == 1168 || (g_dwDebugFlagsIISUtil & 3) == 0 )
      goto LABEL_12;
    v4 = 1083;
    v5 = "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe error calling CancelIOEx on handle %p, GetLastError: %d\n";
  }
  PuDbgPrint(
    (struct _DEBUG_PRINTS *)g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
    v4,
    "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe",
    v5,
    v3);
LABEL_12:
  CReaderWriterLock3::WriteLock((IPM_MESSAGE_PIPE *)((char *)this + 8));
  while ( *((_DWORD *)this + 9) || *((_DWORD *)this + 15) )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
        0x445u,
        "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe",
        "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe waiting for messages to drain, %d\n",
        v1);
    CReaderWriterLock3::WriteUnlock((IPM_MESSAGE_PIPE *)((char *)this + 8));
    if ( v1 >= 0xA )
    {
      if ( v3 != -1 )
      {
        if ( !CancelIoEx((HANDLE)v3, 0) && GetLastError() != 1168 && (g_dwDebugFlagsIISUtil & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata.cxx",
            0x45Cu,
            "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe",
            "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe error calling CancelIOEx on handle %p, GetLastError: %d\n",
            v3);
        Sleep(0x3E8u);
      }
      if ( v1 >= 0x1E && v3 != -1 )
      {
        CloseHandle((HANDLE)v3);
        v3 = -1;
      }
    }
    else
    {
      Sleep(0x64u);
    }
    CReaderWriterLock3::WriteLock((IPM_MESSAGE_PIPE *)((char *)this + 8));
    ++v1;
  }
  CReaderWriterLock3::WriteUnlock((IPM_MESSAGE_PIPE *)((char *)this + 8));
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  IPM_MESSAGE_PIPE::NotifyPipeDisconnected(this, 0x8007006D);
  (**(void (__fastcall ***)(IPM_MESSAGE_PIPE *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x180026d10  push    rbx
0x180026d12  push    rbp
0x180026d13  push    rsi
0x180026d14  push    rdi
0x180026d15  push    r13
0x180026d17  sub     rsp, 40h
0x180026d1b  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180026d21  lea     r13, aIpmMessagePipe_9; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"
0x180026d28  xor     ebp, ebp
0x180026d2a  mov     rdi, rcx
0x180026d2d  test    al, 3
0x180026d2f  setnz   dl
0x180026d32  bt      eax, 1Ch
0x180026d36  setb    al
0x180026d39  test    al, dl
0x180026d3b  jz      short loc_180026D6A
0x180026d3d  mov     qword ptr [rsp+68h+var_40], rcx; char
0x180026d42  lea     rax, aIpmMessagePipe_0; "IPM_MESSAGE_PIPE::DestroyMessagePipe ca"...
0x180026d49  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180026d50  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026d57  mov     r9, r13; char *
0x180026d5a  mov     [rsp+68h+var_48], rax; char *
0x180026d5f  mov     r8d, 417h; unsigned int
0x180026d65  call    PuDbgPrint
0x180026d6a  lea     rsi, [rdi+8]
0x180026d6e  mov     rcx, rsi; this
0x180026d71  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180026d76  mov     rbx, [rdi+10h]
0x180026d7a  mov     rcx, rsi; this
0x180026d7d  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x180026d85  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180026d8a  mov     rcx, rbx; hFile
0x180026d8d  cmp     [rdi+20h], ebp
0x180026d90  jz      short loc_180026DBE
0x180026d92  call    cs:__imp_DisconnectNamedPipe
0x180026d98  test    eax, eax
0x180026d9a  jnz     short loc_180026E11
0x180026d9c  call    cs:__imp_GetLastError
0x180026da2  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180026da9  jz      short loc_180026E11
0x180026dab  mov     [rsp+68h+var_38], eax
0x180026daf  mov     r8d, 42Ah
0x180026db5  lea     rax, aIpmMessagePipe_2; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"...
0x180026dbc  jmp     short loc_180026DF1
0x180026dbe  xor     edx, edx; lpOverlapped
0x180026dc0  call    cs:__imp_CancelIoEx
0x180026dc6  test    eax, eax
0x180026dc8  jnz     short loc_180026E11
0x180026dca  call    cs:__imp_GetLastError
0x180026dd0  cmp     eax, 490h
0x180026dd5  jz      short loc_180026E11
0x180026dd7  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180026dde  jz      short loc_180026E11
0x180026de0  mov     [rsp+68h+var_38], eax
0x180026de4  mov     r8d, 43Bh; unsigned int
0x180026dea  lea     rax, aIpmMessagePipe_29; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"...
0x180026df1  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180026df8  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026dff  mov     qword ptr [rsp+68h+var_40], rbx; char
0x180026e04  mov     r9, r13; char *
0x180026e07  mov     [rsp+68h+var_48], rax; char *
0x180026e0c  call    PuDbgPrint
0x180026e11  mov     rcx, rsi; this
0x180026e14  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180026e19  cmp     dword ptr [rdi+24h], 0
0x180026e1d  jnz     short loc_180026E29
0x180026e1f  cmp     dword ptr [rdi+3Ch], 0
0x180026e23  jz      loc_180026F06
0x180026e29  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180026e30  jz      short loc_180026E5E
0x180026e32  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180026e39  lea     rax, aIpmMessagePipe_8; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"...
0x180026e40  mov     dword ptr [rsp+68h+var_40], ebp; char
0x180026e44  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026e4b  mov     r9, r13; char *
0x180026e4e  mov     [rsp+68h+var_48], rax; char *
0x180026e53  mov     r8d, 445h; unsigned int
0x180026e59  call    PuDbgPrint
0x180026e5e  mov     rcx, rsi; this
0x180026e61  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180026e66  cmp     ebp, 0Ah
0x180026e69  jnb     short loc_180026E78
0x180026e6b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180026e70  call    cs:__imp_Sleep
0x180026e76  jmp     short loc_180026EF7
0x180026e78  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180026e7c  jz      short loc_180026EDF
0x180026e7e  xor     edx, edx; lpOverlapped
0x180026e80  mov     rcx, rbx; hFile
0x180026e83  call    cs:__imp_CancelIoEx
0x180026e89  test    eax, eax
0x180026e8b  jnz     short loc_180026ED4
0x180026e8d  call    cs:__imp_GetLastError
0x180026e93  cmp     eax, 490h
0x180026e98  jz      short loc_180026ED4
0x180026e9a  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180026ea1  jz      short loc_180026ED4
0x180026ea3  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180026eaa  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180026eb1  mov     [rsp+68h+var_38], eax
0x180026eb5  mov     r9, r13; char *
0x180026eb8  lea     rax, aIpmMessagePipe_29; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"...
0x180026ebf  mov     qword ptr [rsp+68h+var_40], rbx; char
0x180026ec4  mov     r8d, 45Ch; unsigned int
0x180026eca  mov     [rsp+68h+var_48], rax; char *
0x180026ecf  call    PuDbgPrint
0x180026ed4  mov     ecx, 3E8h; dwMilliseconds
0x180026ed9  call    cs:__imp_Sleep
0x180026edf  cmp     ebp, 1Eh
0x180026ee2  jb      short loc_180026EF7
0x180026ee4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180026ee8  jz      short loc_180026EF7
0x180026eea  mov     rcx, rbx; hObject
0x180026eed  call    cs:__imp_CloseHandle
0x180026ef3  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180026ef7  mov     rcx, rsi; this
0x180026efa  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180026eff  inc     ebp
0x180026f01  jmp     loc_180026E19
0x180026f06  mov     rcx, rsi; this
0x180026f09  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180026f0e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180026f12  jz      short loc_180026F1D
0x180026f14  mov     rcx, rbx; hObject
0x180026f17  call    cs:__imp_CloseHandle
0x180026f1d  mov     edx, 8007006Dh; int
0x180026f22  mov     rcx, rdi; this
0x180026f25  call    ?NotifyPipeDisconnected@IPM_MESSAGE_PIPE@@AEAAXJ@Z; IPM_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x180026f2a  mov     rax, [rdi]
0x180026f2d  mov     edx, 1
0x180026f32  mov     rcx, rdi
0x180026f35  mov     rax, [rax]
0x180026f38  add     rsp, 40h
0x180026f3c  pop     r13
0x180026f3e  pop     rdi
0x180026f3f  pop     rsi
0x180026f40  pop     rbp
0x180026f41  pop     rbx
0x180026f42  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
