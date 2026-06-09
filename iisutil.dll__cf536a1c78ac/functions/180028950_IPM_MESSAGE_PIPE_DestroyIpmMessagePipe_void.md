# IPM_MESSAGE_PIPE::DestroyIpmMessagePipe(void)

- ea: `0x180028950`
- end: `0x180028bca`
- name: `?DestroyIpmMessagePipe@IPM_MESSAGE_PIPE@@QEAAXXZ`
- size: `634`
- prototype: `void __fastcall(IPM_MESSAGE_PIPE *__hidden this)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180005c80`
- `0x180008000`
- `0x180008f20`
- `0x180009420`
- `0x180028950`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028af8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800289e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028a20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028af8`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028acc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028b4a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028acc`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180028b4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b94`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180028b94`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180028a10`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180028ae8`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180028a10`
- `api-ms-win-core-io-l1-1-0!CancelIoEx` at `0x180028ae8`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x1800289d2`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x1800289d2`

## string_xrefs

- `0x180028990`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180028a54`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180028aa0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`
- `0x180028b1b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata.cxx`

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
  IPM_MESSAGE_PIPE::NotifyPipeDisconnected(this, -2147024787);
  (**(void (__fastcall ***)(IPM_MESSAGE_PIPE *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x180028950  push    rbx
0x180028952  push    rbp
0x180028953  push    rsi
0x180028954  push    rdi
0x180028955  push    r13
0x180028957  sub     rsp, 40h
0x18002895b  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180028961  lea     r13, aIpmMessagePipe_9; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"
0x180028968  xor     ebp, ebp
0x18002896a  mov     rdi, rcx
0x18002896d  test    al, 3
0x18002896f  setnz   dl
0x180028972  bt      eax, 1Ch
0x180028976  setb    al
0x180028979  test    al, dl
0x18002897b  jz      short loc_1800289AA
0x18002897d  mov     qword ptr [rsp+68h+var_40], rcx; char
0x180028982  lea     rax, aIpmMessagePipe_0; "IPM_MESSAGE_PIPE::DestroyMessagePipe ca"...
0x180028989  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028990  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028997  mov     r9, r13; char *
0x18002899a  mov     [rsp+68h+var_48], rax; char *
0x18002899f  mov     r8d, 417h; unsigned int
0x1800289a5  call    PuDbgPrint
0x1800289aa  lea     rsi, [rdi+8]
0x1800289ae  mov     rcx, rsi; this
0x1800289b1  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x1800289b6  mov     rbx, [rdi+10h]
0x1800289ba  mov     rcx, rsi; this
0x1800289bd  mov     qword ptr [rdi+10h], 0FFFFFFFFFFFFFFFFh
0x1800289c5  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x1800289ca  mov     rcx, rbx; hFile
0x1800289cd  cmp     [rdi+20h], ebp
0x1800289d0  jz      short loc_180028A0E
0x1800289d2  call    cs:__imp_DisconnectNamedPipe
0x1800289d9  nop     dword ptr [rax+rax+00h]
0x1800289de  test    eax, eax
0x1800289e0  jnz     loc_180028A6D
0x1800289e6  call    cs:__imp_GetLastError
0x1800289ed  nop     dword ptr [rax+rax+00h]
0x1800289f2  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800289f9  jz      short loc_180028A6D
0x1800289fb  mov     [rsp+68h+var_38], eax
0x1800289ff  mov     r8d, 42Ah
0x180028a05  lea     rax, aIpmMessagePipe_2; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"...
0x180028a0c  jmp     short loc_180028A4D
0x180028a0e  xor     edx, edx; lpOverlapped
0x180028a10  call    cs:__imp_CancelIoEx
0x180028a17  nop     dword ptr [rax+rax+00h]
0x180028a1c  test    eax, eax
0x180028a1e  jnz     short loc_180028A6D
0x180028a20  call    cs:__imp_GetLastError
0x180028a27  nop     dword ptr [rax+rax+00h]
0x180028a2c  cmp     eax, 490h
0x180028a31  jz      short loc_180028A6D
0x180028a33  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180028a3a  jz      short loc_180028A6D
0x180028a3c  mov     [rsp+68h+var_38], eax
0x180028a40  mov     r8d, 43Bh; unsigned int
0x180028a46  lea     rax, aIpmMessagePipe_29; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"...
0x180028a4d  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028a54  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028a5b  mov     qword ptr [rsp+68h+var_40], rbx; char
0x180028a60  mov     r9, r13; char *
0x180028a63  mov     [rsp+68h+var_48], rax; char *
0x180028a68  call    PuDbgPrint
0x180028a6d  mov     rcx, rsi; this
0x180028a70  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180028a75  cmp     dword ptr [rdi+24h], 0
0x180028a79  jnz     short loc_180028A85
0x180028a7b  cmp     dword ptr [rdi+3Ch], 0
0x180028a7f  jz      loc_180028B83
0x180028a85  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180028a8c  jz      short loc_180028ABA
0x180028a8e  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028a95  lea     rax, aIpmMessagePipe_8; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"...
0x180028a9c  mov     dword ptr [rsp+68h+var_40], ebp; char
0x180028aa0  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028aa7  mov     r9, r13; char *
0x180028aaa  mov     [rsp+68h+var_48], rax; char *
0x180028aaf  mov     r8d, 445h; unsigned int
0x180028ab5  call    PuDbgPrint
0x180028aba  mov     rcx, rsi; this
0x180028abd  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180028ac2  cmp     ebp, 0Ah
0x180028ac5  jnb     short loc_180028ADD
0x180028ac7  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180028acc  call    cs:__imp_Sleep
0x180028ad3  nop     dword ptr [rax+rax+00h]
0x180028ad8  jmp     loc_180028B74
0x180028add  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180028ae1  jz      short loc_180028B56
0x180028ae3  xor     edx, edx; lpOverlapped
0x180028ae5  mov     rcx, rbx; hFile
0x180028ae8  call    cs:__imp_CancelIoEx
0x180028aef  nop     dword ptr [rax+rax+00h]
0x180028af4  test    eax, eax
0x180028af6  jnz     short loc_180028B45
0x180028af8  call    cs:__imp_GetLastError
0x180028aff  nop     dword ptr [rax+rax+00h]
0x180028b04  cmp     eax, 490h
0x180028b09  jz      short loc_180028B45
0x180028b0b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180028b12  jz      short loc_180028B45
0x180028b14  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028b1b  lea     rdx, aServercommonIn_6; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028b22  mov     [rsp+68h+var_38], eax
0x180028b26  mov     r9, r13; char *
0x180028b29  lea     rax, aIpmMessagePipe_29; "IPM_MESSAGE_PIPE::DestroyIpmMessagePipe"...
0x180028b30  mov     qword ptr [rsp+68h+var_40], rbx; char
0x180028b35  mov     r8d, 45Ch; unsigned int
0x180028b3b  mov     [rsp+68h+var_48], rax; char *
0x180028b40  call    PuDbgPrint
0x180028b45  mov     ecx, 3E8h; dwMilliseconds
0x180028b4a  call    cs:__imp_Sleep
0x180028b51  nop     dword ptr [rax+rax+00h]
0x180028b56  cmp     ebp, 1Eh
0x180028b59  jb      short loc_180028B74
0x180028b5b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180028b5f  jz      short loc_180028B74
0x180028b61  mov     rcx, rbx; hObject
0x180028b64  call    cs:__imp_CloseHandle
0x180028b6b  nop     dword ptr [rax+rax+00h]
0x180028b70  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180028b74  mov     rcx, rsi; this
0x180028b77  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180028b7c  inc     ebp
0x180028b7e  jmp     loc_180028A75
0x180028b83  mov     rcx, rsi; this
0x180028b86  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180028b8b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180028b8f  jz      short loc_180028BA0
0x180028b91  mov     rcx, rbx; hObject
0x180028b94  call    cs:__imp_CloseHandle
0x180028b9b  nop     dword ptr [rax+rax+00h]
0x180028ba0  mov     edx, 8007006Dh; int
0x180028ba5  mov     rcx, rdi; this
0x180028ba8  call    ?NotifyPipeDisconnected@IPM_MESSAGE_PIPE@@AEAAXJ@Z; IPM_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x180028bad  mov     rax, [rdi]
0x180028bb0  mov     edx, 1
0x180028bb5  mov     rcx, rdi
0x180028bb8  mov     rax, [rax]
0x180028bbb  add     rsp, 40h
0x180028bbf  pop     r13
0x180028bc1  pop     rdi
0x180028bc2  pop     rsi
0x180028bc3  pop     rbp
0x180028bc4  pop     rbx
0x180028bc5  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
