# IPM2_MESSAGE_PIPE::StartNamedPipe(int *)

- ea: `0x18002ad80`
- end: `0x18002af5e`
- name: `?StartNamedPipe@IPM2_MESSAGE_PIPE@@AEAAJPEAH@Z`
- size: `478`
- prototype: `__int64 __fastcall(IPM2_MESSAGE_PIPE *__hidden this, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180016f20`
- `0x1800291f0`

## callees

- `0x180008000`
- `0x180029644`
- `0x18002aad0`
- `0x18002ad80`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ae2e`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18002ae1a`
- `api-ms-win-core-namedpipe-l1-1-0!ConnectNamedPipe` at `0x18002ae1a`

## string_xrefs

- `0x18002adf3`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002aeb7`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002af0c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002adde`: `IPM2_MESSAGE_PIPE::CreateMessagePipe failed CreateMessage, hr = 0x%08x\n`
- `0x18002aebe`: `IPM2_MESSAGE_PIPE::StartNamedPipe failed ReadMessage hr=0x%08x\n`

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
0x18002ad80  mov     [rsp+arg_0], rbx
0x18002ad85  mov     [rsp+arg_10], rbp
0x18002ad8a  push    rsi
0x18002ad8b  push    rdi
0x18002ad8c  push    r14
0x18002ad8e  sub     rsp, 30h
0x18002ad92  mov     [rsp+48h+arg_8], 0
0x18002ad9b  mov     rsi, rdx
0x18002ad9e  mov     rdi, rcx
0x18002ada1  test    rdx, rdx
0x18002ada4  jz      short loc_18002ADAC
0x18002ada6  mov     dword ptr [rdx], 0
0x18002adac  xor     r8d, r8d; int
0x18002adaf  lea     rcx, [rsp+48h+arg_8]; struct IPM2_MESSAGE_IMP **
0x18002adb4  mov     rdx, rdi; struct IPM2_MESSAGE_PIPE *
0x18002adb7  call    ?CreateMessage@IPM2_MESSAGE_IMP@@SAJPEAPEAV1@PEAVIPM2_MESSAGE_PIPE@@H@Z; IPM2_MESSAGE_IMP::CreateMessage(IPM2_MESSAGE_IMP * *,IPM2_MESSAGE_PIPE *,int)
0x18002adbc  mov     r14, [rsp+48h+arg_8]
0x18002adc1  mov     ebx, eax
0x18002adc3  test    eax, eax
0x18002adc5  jns     short loc_18002AE09
0x18002adc7  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002adce  jz      loc_18002AF34
0x18002add4  mov     dword ptr [rsp+48h+var_20], eax; char
0x18002add8  mov     r8d, 4BAh; unsigned int
0x18002adde  lea     rax, aIpm2MessagePip_18; "IPM2_MESSAGE_PIPE::CreateMessagePipe fa"...
0x18002ade5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002adec  lea     r9, aIpm2MessagePip_4; "IPM2_MESSAGE_PIPE::StartNamedPipe"
0x18002adf3  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002adfa  mov     [rsp+48h+var_28], rax; char *
0x18002adff  call    PuDbgPrint
0x18002ae04  jmp     loc_18002AF34
0x18002ae09  mov     ebp, 2
0x18002ae0e  lea     rdx, [r14+38h]; lpOverlapped
0x18002ae12  mov     [r14+0Ch], ebp
0x18002ae16  mov     rcx, [rdi+20h]; hNamedPipe
0x18002ae1a  call    cs:__imp_ConnectNamedPipe
0x18002ae21  nop     dword ptr [rax+rax+00h]
0x18002ae26  test    eax, eax
0x18002ae28  jnz     loc_18002AF2F
0x18002ae2e  call    cs:__imp_GetLastError
0x18002ae35  nop     dword ptr [rax+rax+00h]
0x18002ae3a  mov     ecx, 217h
0x18002ae3f  cmp     eax, 3E5h
0x18002ae44  jz      short loc_18002AE7E
0x18002ae46  cmp     eax, ecx
0x18002ae48  jz      short loc_18002AE86
0x18002ae4a  test    eax, eax
0x18002ae4c  jg      short loc_18002AE52
0x18002ae4e  mov     ebx, eax
0x18002ae50  jmp     short loc_18002AE5B
0x18002ae52  movzx   ebx, ax
0x18002ae55  or      ebx, 80070000h
0x18002ae5b  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002ae62  jz      loc_18002AF34
0x18002ae68  mov     dword ptr [rsp+48h+var_20], ebx
0x18002ae6c  lea     rax, aIpm2MessagePip; "IPM2_MESSAGE_PIPE::StartNamedPipe faile"...
0x18002ae73  mov     r8d, 4C9h
0x18002ae79  jmp     loc_18002ADE5
0x18002ae7e  cmp     eax, ecx
0x18002ae80  jnz     loc_18002AF25
0x18002ae86  xchg    ebp, [rdi+58h]
0x18002ae89  mov     edx, 20h ; ' '; nNumberOfBytesToRead
0x18002ae8e  mov     rcx, rdi; this
0x18002ae91  call    ?ReadMessage@IPM2_MESSAGE_PIPE@@AEAAJK@Z; IPM2_MESSAGE_PIPE::ReadMessage(ulong)
0x18002ae96  mov     ebx, eax
0x18002ae98  test    eax, eax
0x18002ae9a  jns     short loc_18002AEDF
0x18002ae9c  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002aea3  jz      short loc_18002AED5
0x18002aea5  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002aeac  lea     r9, aIpm2MessagePip_4; "IPM2_MESSAGE_PIPE::StartNamedPipe"
0x18002aeb3  mov     dword ptr [rsp+48h+var_20], eax; char
0x18002aeb7  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002aebe  lea     rax, aIpm2MessagePip_37; "IPM2_MESSAGE_PIPE::StartNamedPipe faile"...
0x18002aec5  mov     r8d, 4E0h; unsigned int
0x18002aecb  mov     [rsp+48h+var_28], rax; char *
0x18002aed0  call    PuDbgPrint
0x18002aed5  mov     eax, 3
0x18002aeda  xchg    eax, [rdi+58h]
0x18002aedd  jmp     short loc_18002AF34
0x18002aedf  mov     eax, 3
0x18002aee4  test    byte ptr cs:g_dwDebugFlagsIISUtil, al
0x18002aeea  jz      short loc_18002AF18
0x18002aeec  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002aef3  lea     rax, aIpm2MessagePip_30; "IPM2_MESSAGE_PIPE::StartNamedPipe pipe "...
0x18002aefa  lea     r9, aIpm2MessagePip_4; "IPM2_MESSAGE_PIPE::StartNamedPipe"
0x18002af01  mov     [rsp+48h+var_28], rax; char *
0x18002af06  mov     r8d, 4E9h; unsigned int
0x18002af0c  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002af13  call    PuDbgPrint
0x18002af18  test    rsi, rsi
0x18002af1b  jz      short loc_18002AF34
0x18002af1d  mov     dword ptr [rsi], 1
0x18002af23  jmp     short loc_18002AF34
0x18002af25  mov     eax, 1
0x18002af2a  xchg    eax, [rdi+58h]
0x18002af2d  jmp     short loc_18002AF48
0x18002af2f  mov     ebx, 80004005h
0x18002af34  test    r14, r14
0x18002af37  jz      short loc_18002AF48
0x18002af39  mov     rax, [r14]
0x18002af3c  mov     rcx, r14
0x18002af3f  mov     rax, [rax+8]
0x18002af43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002af48  mov     rbp, [rsp+48h+arg_10]
0x18002af4d  mov     eax, ebx
0x18002af4f  mov     rbx, [rsp+48h+arg_0]
0x18002af54  add     rsp, 30h
0x18002af58  pop     r14
0x18002af5a  pop     rdi
0x18002af5b  pop     rsi
0x18002af5c  retn
```
