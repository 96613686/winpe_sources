# IPM2_MESSAGE_PIPE::StartNamedPipe(int *)

- ea: `0x180028f50`
- end: `0x180029121`
- name: `?StartNamedPipe@IPM2_MESSAGE_PIPE@@AEAAJPEAH@Z`
- size: `465`
- prototype: `__int64 __fastcall(IPM2_MESSAGE_PIPE *__hidden this, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016330`
- `0x180027520`

## callees

- `0x180007300`
- `0x180027934`
- `0x180028ca0`
- `0x180028f50`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ff8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028ff8`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180028fea`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x180028fea`

## string_xrefs

- `0x180028fc3`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002907b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800290d0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180028fae`: `IPM2_MESSAGE_PIPE::CreateMessagePipe failed CreateMessage, hr = 0x%08x\n`
- `0x180029082`: `IPM2_MESSAGE_PIPE::StartNamedPipe failed ReadMessage hr=0x%08x\n`

## pseudocode

```c
__int64 __fastcall IPM2_MESSAGE_PIPE::StartNamedPipe(IPM2_MESSAGE_PIPE *this, int *a2)
{
  int v4; // eax
  struct IPM2_MESSAGE_IMP *v5; // r14
  unsigned int v6; // ebx
  struct _OVERLAPPED *v7; // rdx
  signed int LastError; // eax
  int Message; // eax
  char v11; // [rsp+28h] [rbp-20h]
  struct IPM2_MESSAGE_IMP *v12; // [rsp+58h] [rbp+10h] BYREF

  v12 = 0;
  if ( a2 )
    *a2 = 0;
  v4 = IPM2_MESSAGE_IMP::CreateMessage(&v12, this, 0);
  v5 = v12;
  v6 = v4;
  if ( v4 >= 0 )
  {
    v7 = (struct _OVERLAPPED *)((char *)v12 + 56);
    *((_DWORD *)v12 + 3) = 2;
    if ( ConnectNamedPipe(*((HANDLE *)this + 4), v7) )
    {
      v6 = -2147467259;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError == 997 )
      {
        _InterlockedExchange((volatile __int32 *)this + 22, 1);
        return v6;
      }
      if ( LastError == 535 )
      {
        _InterlockedExchange((volatile __int32 *)this + 22, 2);
        Message = IPM2_MESSAGE_PIPE::ReadMessage((HANDLE *)this, 0x20u);
        v6 = Message;
        if ( Message >= 0 )
        {
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
              0x4E9u,
              "IPM2_MESSAGE_PIPE::StartNamedPipe",
              "IPM2_MESSAGE_PIPE::StartNamedPipe pipe connected.\n",
              v11);
          if ( a2 )
            *a2 = 1;
        }
        else
        {
          if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
              0x4E0u,
              "IPM2_MESSAGE_PIPE::StartNamedPipe",
              "IPM2_MESSAGE_PIPE::StartNamedPipe failed ReadMessage hr=0x%08x\n",
              Message);
          _InterlockedExchange((volatile __int32 *)this + 22, 3);
        }
      }
      else
      {
        if ( LastError > 0 )
          v6 = (unsigned __int16)LastError | 0x80070000;
        else
          v6 = LastError;
        if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
            0x4C9u,
            "IPM2_MESSAGE_PIPE::StartNamedPipe",
            "IPM2_MESSAGE_PIPE::StartNamedPipe failed ConnectNamedPipe, hr = 0x%08x\n",
            v6);
      }
    }
  }
  else if ( (g_dwDebugFlagsIISUtil & 0xF) != 0 )
  {
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x4BAu,
      "IPM2_MESSAGE_PIPE::StartNamedPipe",
      "IPM2_MESSAGE_PIPE::CreateMessagePipe failed CreateMessage, hr = 0x%08x\n",
      v4);
  }
  if ( v5 )
    (*(void (__fastcall **)(struct IPM2_MESSAGE_IMP *))(*(_QWORD *)v5 + 8LL))(v5);
  return v6;
}

```

## disassembly

```asm
0x180028f50  mov     [rsp+arg_0], rbx
0x180028f55  mov     [rsp+arg_10], rbp
0x180028f5a  push    rsi
0x180028f5b  push    rdi
0x180028f5c  push    r14
0x180028f5e  sub     rsp, 30h
0x180028f62  mov     [rsp+48h+arg_8], 0
0x180028f6b  mov     rsi, rdx
0x180028f6e  mov     rdi, rcx
0x180028f71  test    rdx, rdx
0x180028f74  jz      short loc_180028F7C
0x180028f76  mov     dword ptr [rdx], 0
0x180028f7c  xor     r8d, r8d; int
0x180028f7f  lea     rcx, [rsp+48h+arg_8]; struct IPM2_MESSAGE_IMP **
0x180028f84  mov     rdx, rdi; struct IPM2_MESSAGE_PIPE *
0x180028f87  call    ?CreateMessage@IPM2_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM2_MESSAGE_PIPE@@H@Z; IPM2_MESSAGE_IMP::CreateMessage(IPM2_MESSAGE_IMP * *,IPM2_MESSAGE_PIPE *,int)
0x180028f8c  mov     r14, [rsp+48h+arg_8]
0x180028f91  mov     ebx, eax
0x180028f93  test    eax, eax
0x180028f95  jns     short loc_180028FD9
0x180028f97  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180028f9e  jz      loc_1800290F8
0x180028fa4  mov     dword ptr [rsp+48h+var_20], eax; char
0x180028fa8  mov     r8d, 4BAh; unsigned int
0x180028fae  lea     rax, aIpm2MessagePip_18; "IPM2_MESSAGE_PIPE::CreateMessagePipe fa"...
0x180028fb5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180028fbc  lea     r9, aIpm2MessagePip_4; "IPM2_MESSAGE_PIPE::StartNamedPipe"
0x180028fc3  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180028fca  mov     [rsp+48h+var_28], rax; char *
0x180028fcf  call    PuDbgPrint
0x180028fd4  jmp     loc_1800290F8
0x180028fd9  mov     ebp, 2
0x180028fde  lea     rdx, [r14+38h]; lpOverlapped
0x180028fe2  mov     [r14+0Ch], ebp
0x180028fe6  mov     rcx, [rdi+20h]; hNamedPipe
0x180028fea  call    cs:__imp_ConnectNamedPipe
0x180028ff0  test    eax, eax
0x180028ff2  jnz     loc_1800290F3
0x180028ff8  call    cs:__imp_GetLastError
0x180028ffe  mov     ecx, 217h
0x180029003  cmp     eax, 3E5h
0x180029008  jz      short loc_180029042
0x18002900a  cmp     eax, ecx
0x18002900c  jz      short loc_18002904A
0x18002900e  test    eax, eax
0x180029010  jg      short loc_180029016
0x180029012  mov     ebx, eax
0x180029014  jmp     short loc_18002901F
0x180029016  movzx   ebx, ax
0x180029019  or      ebx, 80070000h
0x18002901f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180029026  jz      loc_1800290F8
0x18002902c  mov     dword ptr [rsp+48h+var_20], ebx
0x180029030  lea     rax, aIpm2MessagePip; "IPM2_MESSAGE_PIPE::StartNamedPipe faile"...
0x180029037  mov     r8d, 4C9h
0x18002903d  jmp     loc_180028FB5
0x180029042  cmp     eax, ecx
0x180029044  jnz     loc_1800290E9
0x18002904a  xchg    ebp, [rdi+58h]
0x18002904d  mov     edx, 20h ; ' '; nNumberOfBytesToRead
0x180029052  mov     rcx, rdi; this
0x180029055  call    ?ReadMessage@IPM2_MESSAGE_PIPE@@AEAAJK@Z; IPM2_MESSAGE_PIPE::ReadMessage(ulong)
0x18002905a  mov     ebx, eax
0x18002905c  test    eax, eax
0x18002905e  jns     short loc_1800290A3
0x180029060  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180029067  jz      short loc_180029099
0x180029069  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029070  lea     r9, aIpm2MessagePip_4; "IPM2_MESSAGE_PIPE::StartNamedPipe"
0x180029077  mov     dword ptr [rsp+48h+var_20], eax; char
0x18002907b  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029082  lea     rax, aIpm2MessagePip_37; "IPM2_MESSAGE_PIPE::StartNamedPipe faile"...
0x180029089  mov     r8d, 4E0h; unsigned int
0x18002908f  mov     [rsp+48h+var_28], rax; char *
0x180029094  call    PuDbgPrint
0x180029099  mov     eax, 3
0x18002909e  xchg    eax, [rdi+58h]
0x1800290a1  jmp     short loc_1800290F8
0x1800290a3  mov     eax, 3
0x1800290a8  test    byte ptr cs:g_dwDebugFlagsIISUtil, al
0x1800290ae  jz      short loc_1800290DC
0x1800290b0  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800290b7  lea     rax, aIpm2MessagePip_30; "IPM2_MESSAGE_PIPE::StartNamedPipe pipe "...
0x1800290be  lea     r9, aIpm2MessagePip_4; "IPM2_MESSAGE_PIPE::StartNamedPipe"
0x1800290c5  mov     [rsp+48h+var_28], rax; char *
0x1800290ca  mov     r8d, 4E9h; unsigned int
0x1800290d0  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800290d7  call    PuDbgPrint
0x1800290dc  test    rsi, rsi
0x1800290df  jz      short loc_1800290F8
0x1800290e1  mov     dword ptr [rsi], 1
0x1800290e7  jmp     short loc_1800290F8
0x1800290e9  mov     eax, 1
0x1800290ee  xchg    eax, [rdi+58h]
0x1800290f1  jmp     short loc_18002910C
0x1800290f3  mov     ebx, 80004005h
0x1800290f8  test    r14, r14
0x1800290fb  jz      short loc_18002910C
0x1800290fd  mov     rax, [r14]
0x180029100  mov     rcx, r14
0x180029103  mov     rax, [rax+8]
0x180029107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002910c  mov     rbp, [rsp+48h+arg_10]
0x180029111  mov     eax, ebx
0x180029113  mov     rbx, [rsp+48h+arg_0]
0x180029118  add     rsp, 30h
0x18002911c  pop     r14
0x18002911e  pop     rdi
0x18002911f  pop     rsi
0x180029120  retn
```
