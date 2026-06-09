# IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(void)

- ea: `0x1800298e0`
- end: `0x180029b81`
- name: `?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ`
- size: `673`
- prototype: `void __fastcall(IPM2_MESSAGE_PIPE *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002b444`
- `0x18002b570`

## callees

- `0x180005c80`
- `0x180008000`
- `0x180008f20`
- `0x180016f20`
- `0x1800298e0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ab0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029980`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800299c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029ab0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029a80`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029b02`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029a80`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180029b02`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029a12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b1b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029b49`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x18002996c`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x18002996c`

## string_xrefs

- `0x180029922`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800299f7`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029a54`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029ad3`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`

## pseudocode

```c
void __fastcall IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(IPM2_MESSAGE_PIPE *this)
{
  unsigned int v1; // ebp
  __int64 v3; // rbx
  unsigned int v4; // r8d
  char *v5; // rax

  v1 = 0;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x398u,
      "IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe",
      "IPM2_MESSAGE_PIPE::DestroyMessagePipe called this=%p\n",
      (char)this);
  CReaderWriterLock3::WriteLock((IPM2_MESSAGE_PIPE *)((char *)this + 8));
  _InterlockedExchange((volatile __int32 *)this + 22, 4);
  v3 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = -1;
  CReaderWriterLock3::WriteUnlock((IPM2_MESSAGE_PIPE *)((char *)this + 8));
  if ( *((_DWORD *)this + 12) )
  {
    if ( DisconnectNamedPipe((HANDLE)v3) )
      goto LABEL_14;
    GetLastError();
    if ( (g_dwDebugFlagsIISUtil & 3) == 0 )
      goto LABEL_14;
    v4 = 941;
    v5 = "IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe error calling DisconnectNamedPipe on handle %p, GetLastError: %d\n";
  }
  else
  {
    if ( !IISUtil2CancelIoEx )
    {
      CloseHandle((HANDLE)v3);
      v3 = -1;
      goto LABEL_14;
    }
    if ( IISUtil2CancelIoEx((void *)v3, 0) || GetLastError() == 1168 || (g_dwDebugFlagsIISUtil & 3) == 0 )
      goto LABEL_14;
    v4 = 960;
    v5 = "IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe error calling CancelIOEx on handle %p, GetLastError: %d\n";
  }
  PuDbgPrint(
    (struct _DEBUG_PRINTS *)g_pDebug,
    "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
    v4,
    "IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe",
    v5,
    v3);
LABEL_14:
  CReaderWriterLock3::WriteLock((IPM2_MESSAGE_PIPE *)((char *)this + 8));
  while ( *((_DWORD *)this + 13) || *((_DWORD *)this + 19) )
  {
    if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
      PuDbgPrint(
        (struct _DEBUG_PRINTS *)g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
        0x3D0u,
        "IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe",
        "IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe waiting for messages to drain, %d\n",
        v1);
    CReaderWriterLock3::WriteUnlock((IPM2_MESSAGE_PIPE *)((char *)this + 8));
    if ( v1 >= 0xA )
    {
      if ( v3 != -1 && IISUtil2CancelIoEx )
      {
        if ( !IISUtil2CancelIoEx((void *)v3, 0) && GetLastError() != 1168 && (g_dwDebugFlagsIISUtil & 3) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
            0x3E8u,
            "IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe",
            "IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe error calling CancelIOEx on handle %p, GetLastError: %d\n",
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
    CReaderWriterLock3::WriteLock((IPM2_MESSAGE_PIPE *)((char *)this + 8));
    ++v1;
  }
  CReaderWriterLock3::WriteUnlock((IPM2_MESSAGE_PIPE *)((char *)this + 8));
  if ( v3 != -1 )
    CloseHandle((HANDLE)v3);
  IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(this, -2147024787);
  (**(void (__fastcall ***)(IPM2_MESSAGE_PIPE *, __int64))this)(this, 1);
}

```

## disassembly

```asm
0x1800298e0  push    rbx
0x1800298e2  push    rbp
0x1800298e3  push    rsi
0x1800298e4  push    rdi
0x1800298e5  push    r13
0x1800298e7  push    r15
0x1800298e9  sub     rsp, 48h
0x1800298ed  mov     eax, cs:g_dwDebugFlagsIISUtil
0x1800298f3  lea     r13, aIpm2MessagePip_32; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x1800298fa  xor     ebp, ebp
0x1800298fc  mov     rdi, rcx
0x1800298ff  test    al, 3
0x180029901  setnz   dl
0x180029904  bt      eax, 1Ch
0x180029908  setb    al
0x18002990b  test    al, dl
0x18002990d  jz      short loc_18002993C
0x18002990f  mov     qword ptr [rsp+78h+var_50], rcx; char
0x180029914  lea     rax, aIpm2MessagePip_8; "IPM2_MESSAGE_PIPE::DestroyMessagePipe c"...
0x18002991b  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029922  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029929  mov     r9, r13; char *
0x18002992c  mov     [rsp+78h+var_58], rax; char *
0x180029931  mov     r8d, 398h; unsigned int
0x180029937  call    PuDbgPrint
0x18002993c  lea     rsi, [rdi+8]
0x180029940  mov     rcx, rsi; this
0x180029943  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180029948  mov     eax, 4
0x18002994d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180029951  xchg    eax, [rdi+58h]
0x180029954  mov     rbx, [rdi+20h]
0x180029958  mov     rcx, rsi; this
0x18002995b  mov     [rdi+20h], r15
0x18002995f  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180029964  mov     rcx, rbx; hObject
0x180029967  cmp     [rdi+30h], ebp
0x18002996a  jz      short loc_1800299AC
0x18002996c  call    cs:__imp_DisconnectNamedPipe
0x180029973  nop     dword ptr [rax+rax+00h]
0x180029978  test    eax, eax
0x18002997a  jnz     loc_180029A21
0x180029980  call    cs:__imp_GetLastError
0x180029987  nop     dword ptr [rax+rax+00h]
0x18002998c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180029993  jz      loc_180029A21
0x180029999  mov     [rsp+78h+var_48], eax
0x18002999d  mov     r8d, 3ADh
0x1800299a3  lea     rax, aIpm2MessagePip_7; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x1800299aa  jmp     short loc_1800299F0
0x1800299ac  mov     rax, cs:?IISUtil2CancelIoEx@@3P6AHPEAXPEAU_OVERLAPPED@@@ZEA; int (*IISUtil2CancelIoEx)(void *,_OVERLAPPED *)
0x1800299b3  test    rax, rax
0x1800299b6  jz      short loc_180029A12
0x1800299b8  xor     edx, edx
0x1800299ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299bf  test    eax, eax
0x1800299c1  jnz     short loc_180029A21
0x1800299c3  call    cs:__imp_GetLastError
0x1800299ca  nop     dword ptr [rax+rax+00h]
0x1800299cf  cmp     eax, 490h
0x1800299d4  jz      short loc_180029A21
0x1800299d6  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800299dd  jz      short loc_180029A21
0x1800299df  mov     [rsp+78h+var_48], eax
0x1800299e3  mov     r8d, 3C0h; unsigned int
0x1800299e9  lea     rax, aIpm2MessagePip_12; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x1800299f0  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800299f7  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800299fe  mov     qword ptr [rsp+78h+var_50], rbx; char
0x180029a03  mov     r9, r13; char *
0x180029a06  mov     [rsp+78h+var_58], rax; char *
0x180029a0b  call    PuDbgPrint
0x180029a10  jmp     short loc_180029A21
0x180029a12  call    cs:__imp_CloseHandle
0x180029a19  nop     dword ptr [rax+rax+00h]
0x180029a1e  mov     rbx, r15
0x180029a21  mov     rcx, rsi; this
0x180029a24  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180029a29  cmp     dword ptr [rdi+34h], 0
0x180029a2d  jnz     short loc_180029A39
0x180029a2f  cmp     dword ptr [rdi+4Ch], 0
0x180029a33  jz      loc_180029B39
0x180029a39  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180029a40  jz      short loc_180029A6E
0x180029a42  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029a49  lea     rax, aIpm2MessagePip_35; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x180029a50  mov     dword ptr [rsp+78h+var_50], ebp; char
0x180029a54  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029a5b  mov     r9, r13; char *
0x180029a5e  mov     [rsp+78h+var_58], rax; char *
0x180029a63  mov     r8d, 3D0h; unsigned int
0x180029a69  call    PuDbgPrint
0x180029a6e  mov     rcx, rsi; this
0x180029a71  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180029a76  cmp     ebp, 0Ah
0x180029a79  jnb     short loc_180029A91
0x180029a7b  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180029a80  call    cs:__imp_Sleep
0x180029a87  nop     dword ptr [rax+rax+00h]
0x180029a8c  jmp     loc_180029B2A
0x180029a91  cmp     rbx, r15
0x180029a94  jz      short loc_180029B0E
0x180029a96  mov     rax, cs:?IISUtil2CancelIoEx@@3P6AHPEAXPEAU_OVERLAPPED@@@ZEA; int (*IISUtil2CancelIoEx)(void *,_OVERLAPPED *)
0x180029a9d  test    rax, rax
0x180029aa0  jz      short loc_180029B0E
0x180029aa2  xor     edx, edx
0x180029aa4  mov     rcx, rbx
0x180029aa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029aac  test    eax, eax
0x180029aae  jnz     short loc_180029AFD
0x180029ab0  call    cs:__imp_GetLastError
0x180029ab7  nop     dword ptr [rax+rax+00h]
0x180029abc  cmp     eax, 490h
0x180029ac1  jz      short loc_180029AFD
0x180029ac3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180029aca  jz      short loc_180029AFD
0x180029acc  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029ad3  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029ada  mov     [rsp+78h+var_48], eax
0x180029ade  mov     r9, r13; char *
0x180029ae1  lea     rax, aIpm2MessagePip_12; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x180029ae8  mov     qword ptr [rsp+78h+var_50], rbx; char
0x180029aed  mov     r8d, 3E8h; unsigned int
0x180029af3  mov     [rsp+78h+var_58], rax; char *
0x180029af8  call    PuDbgPrint
0x180029afd  mov     ecx, 3E8h; dwMilliseconds
0x180029b02  call    cs:__imp_Sleep
0x180029b09  nop     dword ptr [rax+rax+00h]
0x180029b0e  cmp     ebp, 1Eh
0x180029b11  jb      short loc_180029B2A
0x180029b13  cmp     rbx, r15
0x180029b16  jz      short loc_180029B2A
0x180029b18  mov     rcx, rbx; hObject
0x180029b1b  call    cs:__imp_CloseHandle
0x180029b22  nop     dword ptr [rax+rax+00h]
0x180029b27  mov     rbx, r15
0x180029b2a  mov     rcx, rsi; this
0x180029b2d  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180029b32  inc     ebp
0x180029b34  jmp     loc_180029A29
0x180029b39  mov     rcx, rsi; this
0x180029b3c  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180029b41  cmp     rbx, r15
0x180029b44  jz      short loc_180029B55
0x180029b46  mov     rcx, rbx; hObject
0x180029b49  call    cs:__imp_CloseHandle
0x180029b50  nop     dword ptr [rax+rax+00h]
0x180029b55  mov     edx, 8007006Dh; int
0x180029b5a  mov     rcx, rdi; this
0x180029b5d  call    ?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x180029b62  mov     rax, [rdi]
0x180029b65  mov     edx, 1
0x180029b6a  mov     rcx, rdi
0x180029b6d  mov     rax, [rax]
0x180029b70  add     rsp, 48h
0x180029b74  pop     r15
0x180029b76  pop     r13
0x180029b78  pop     rdi
0x180029b79  pop     rsi
0x180029b7a  pop     rbp
0x180029b7b  pop     rbx
0x180029b7c  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
