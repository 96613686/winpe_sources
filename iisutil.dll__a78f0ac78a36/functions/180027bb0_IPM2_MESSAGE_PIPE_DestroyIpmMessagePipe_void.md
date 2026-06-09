# IPM2_MESSAGE_PIPE::DestroyIpmMessagePipe(void)

- ea: `0x180027bb0`
- end: `0x180027e17`
- name: `?DestroyIpmMessagePipe@IPM2_MESSAGE_PIPE@@QEAAXXZ`
- size: `615`
- prototype: `void __fastcall(IPM2_MESSAGE_PIPE *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180029604`
- `0x180029730`

## callees

- `0x180005110`
- `0x180007300`
- `0x1800081e0`
- `0x180016330`
- `0x180027bb0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027c83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027d5e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027d34`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027daa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027d34`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180027daa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027de5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027ccc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027dbd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027de5`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x180027c3c`
- `api-ms-win-core-namedpipe-l1-1-0!DisconnectNamedPipe` at `0x180027c3c`

## string_xrefs

- `0x180027bf2`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027cb1`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027d08`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027d7b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`

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
0x180027bb0  push    rbx
0x180027bb2  push    rbp
0x180027bb3  push    rsi
0x180027bb4  push    rdi
0x180027bb5  push    r13
0x180027bb7  push    r15
0x180027bb9  sub     rsp, 48h
0x180027bbd  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180027bc3  lea     r13, aIpm2MessagePip_32; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x180027bca  xor     ebp, ebp
0x180027bcc  mov     rdi, rcx
0x180027bcf  test    al, 3
0x180027bd1  setnz   dl
0x180027bd4  bt      eax, 1Ch
0x180027bd8  setb    al
0x180027bdb  test    al, dl
0x180027bdd  jz      short loc_180027C0C
0x180027bdf  mov     qword ptr [rsp+78h+var_50], rcx; char
0x180027be4  lea     rax, aIpm2MessagePip_8; "IPM2_MESSAGE_PIPE::DestroyMessagePipe c"...
0x180027beb  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027bf2  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027bf9  mov     r9, r13; char *
0x180027bfc  mov     [rsp+78h+var_58], rax; char *
0x180027c01  mov     r8d, 398h; unsigned int
0x180027c07  call    PuDbgPrint
0x180027c0c  lea     rsi, [rdi+8]
0x180027c10  mov     rcx, rsi; this
0x180027c13  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180027c18  mov     eax, 4
0x180027c1d  or      r15, 0FFFFFFFFFFFFFFFFh
0x180027c21  xchg    eax, [rdi+58h]
0x180027c24  mov     rbx, [rdi+20h]
0x180027c28  mov     rcx, rsi; this
0x180027c2b  mov     [rdi+20h], r15
0x180027c2f  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180027c34  mov     rcx, rbx; hObject
0x180027c37  cmp     [rdi+30h], ebp
0x180027c3a  jz      short loc_180027C6C
0x180027c3c  call    cs:__imp_DisconnectNamedPipe
0x180027c42  test    eax, eax
0x180027c44  jnz     loc_180027CD5
0x180027c4a  call    cs:__imp_GetLastError
0x180027c50  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180027c57  jz      short loc_180027CD5
0x180027c59  mov     [rsp+78h+var_48], eax
0x180027c5d  mov     r8d, 3ADh
0x180027c63  lea     rax, aIpm2MessagePip_7; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x180027c6a  jmp     short loc_180027CAA
0x180027c6c  mov     rax, cs:?IISUtil2CancelIoEx@@3P6AHPEAXPEAU_OVERLAPPED@@@ZEA; int (*IISUtil2CancelIoEx)(void *,_OVERLAPPED *)
0x180027c73  test    rax, rax
0x180027c76  jz      short loc_180027CCC
0x180027c78  xor     edx, edx
0x180027c7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027c7f  test    eax, eax
0x180027c81  jnz     short loc_180027CD5
0x180027c83  call    cs:__imp_GetLastError
0x180027c89  cmp     eax, 490h
0x180027c8e  jz      short loc_180027CD5
0x180027c90  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180027c97  jz      short loc_180027CD5
0x180027c99  mov     [rsp+78h+var_48], eax
0x180027c9d  mov     r8d, 3C0h; unsigned int
0x180027ca3  lea     rax, aIpm2MessagePip_12; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x180027caa  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027cb1  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027cb8  mov     qword ptr [rsp+78h+var_50], rbx; char
0x180027cbd  mov     r9, r13; char *
0x180027cc0  mov     [rsp+78h+var_58], rax; char *
0x180027cc5  call    PuDbgPrint
0x180027cca  jmp     short loc_180027CD5
0x180027ccc  call    cs:__imp_CloseHandle
0x180027cd2  mov     rbx, r15
0x180027cd5  mov     rcx, rsi; this
0x180027cd8  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180027cdd  cmp     dword ptr [rdi+34h], 0
0x180027ce1  jnz     short loc_180027CED
0x180027ce3  cmp     dword ptr [rdi+4Ch], 0
0x180027ce7  jz      loc_180027DD5
0x180027ced  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180027cf4  jz      short loc_180027D22
0x180027cf6  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027cfd  lea     rax, aIpm2MessagePip_35; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x180027d04  mov     dword ptr [rsp+78h+var_50], ebp; char
0x180027d08  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027d0f  mov     r9, r13; char *
0x180027d12  mov     [rsp+78h+var_58], rax; char *
0x180027d17  mov     r8d, 3D0h; unsigned int
0x180027d1d  call    PuDbgPrint
0x180027d22  mov     rcx, rsi; this
0x180027d25  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180027d2a  cmp     ebp, 0Ah
0x180027d2d  jnb     short loc_180027D3F
0x180027d2f  mov     ecx, 64h ; 'd'; dwMilliseconds
0x180027d34  call    cs:__imp_Sleep
0x180027d3a  jmp     loc_180027DC6
0x180027d3f  cmp     rbx, r15
0x180027d42  jz      short loc_180027DB0
0x180027d44  mov     rax, cs:?IISUtil2CancelIoEx@@3P6AHPEAXPEAU_OVERLAPPED@@@ZEA; int (*IISUtil2CancelIoEx)(void *,_OVERLAPPED *)
0x180027d4b  test    rax, rax
0x180027d4e  jz      short loc_180027DB0
0x180027d50  xor     edx, edx
0x180027d52  mov     rcx, rbx
0x180027d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027d5a  test    eax, eax
0x180027d5c  jnz     short loc_180027DA5
0x180027d5e  call    cs:__imp_GetLastError
0x180027d64  cmp     eax, 490h
0x180027d69  jz      short loc_180027DA5
0x180027d6b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180027d72  jz      short loc_180027DA5
0x180027d74  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027d7b  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027d82  mov     [rsp+78h+var_48], eax
0x180027d86  mov     r9, r13; char *
0x180027d89  lea     rax, aIpm2MessagePip_12; "IPM2_MESSAGE_PIPE::DestroyIpmMessagePip"...
0x180027d90  mov     qword ptr [rsp+78h+var_50], rbx; char
0x180027d95  mov     r8d, 3E8h; unsigned int
0x180027d9b  mov     [rsp+78h+var_58], rax; char *
0x180027da0  call    PuDbgPrint
0x180027da5  mov     ecx, 3E8h; dwMilliseconds
0x180027daa  call    cs:__imp_Sleep
0x180027db0  cmp     ebp, 1Eh
0x180027db3  jb      short loc_180027DC6
0x180027db5  cmp     rbx, r15
0x180027db8  jz      short loc_180027DC6
0x180027dba  mov     rcx, rbx; hObject
0x180027dbd  call    cs:__imp_CloseHandle
0x180027dc3  mov     rbx, r15
0x180027dc6  mov     rcx, rsi; this
0x180027dc9  call    ?WriteLock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteLock(void)
0x180027dce  inc     ebp
0x180027dd0  jmp     loc_180027CDD
0x180027dd5  mov     rcx, rsi; this
0x180027dd8  call    ?WriteUnlock@CReaderWriterLock3@@QEAAXXZ; CReaderWriterLock3::WriteUnlock(void)
0x180027ddd  cmp     rbx, r15
0x180027de0  jz      short loc_180027DEB
0x180027de2  mov     rcx, rbx; hObject
0x180027de5  call    cs:__imp_CloseHandle
0x180027deb  mov     edx, 8007006Dh; int
0x180027df0  mov     rcx, rdi; this
0x180027df3  call    ?NotifyPipeDisconnected@IPM2_MESSAGE_PIPE@@AEAAXJ@Z; IPM2_MESSAGE_PIPE::NotifyPipeDisconnected(long)
0x180027df8  mov     rax, [rdi]
0x180027dfb  mov     edx, 1
0x180027e00  mov     rcx, rdi
0x180027e03  mov     rax, [rax]
0x180027e06  add     rsp, 48h
0x180027e0a  pop     r15
0x180027e0c  pop     r13
0x180027e0e  pop     rdi
0x180027e0f  pop     rsi
0x180027e10  pop     rbp
0x180027e11  pop     rbx
0x180027e12  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
