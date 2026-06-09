# IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(IPM2_MESSAGE_ACCEPTOR *,ushort const *,int,int,ulong,_SECURITY_ATTRIBUTES *,IPM2_MESSAGE_PIPE * *,int *)

- ea: `0x1800291f0`
- end: `0x1800295ee`
- name: `?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHHKPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@PEAH@Z`
- size: `1022`
- prototype: `__int64 __fastcall(struct IPM2_MESSAGE_ACCEPTOR *, const unsigned __int16 *, int, int, DWORD nMaxInstances, struct _SECURITY_ATTRIBUTES *lpSecurityAttributes, struct IPM2_MESSAGE_PIPE **Mode, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180029600`
- `0x18002b570`

## callees

- `0x180008000`
- `0x180019230`
- `0x180028f30`
- `0x1800291f0`
- `0x18002aad0`
- `0x18002ad80`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002932c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029498`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002932c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029438`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029498`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002928d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002928d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029272`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180029272`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800294ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002956a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800294ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002956a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029423`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029423`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180029488`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180029488`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18002931a`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18002931a`

## string_xrefs

- `0x18002926b`: `kernel32.dll`
- `0x18002923b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002936b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800293d2`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800294e0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029542`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800295d2`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180029228`: `IPM2_MESSAGE_PIPE::CreateMessagePipe called name=%S\n`
- `0x180029234`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x18002935d`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800293c7`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800294ce`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x180029537`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800295c0`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x180029376`: `Pipe %S failed create, hr = 0x%08x Pipestate=%d\n `
- `0x1800294c3`: `IPM2_MESSAGE_PIPE::CreateMessagePipe failed SetNamedPipeHandleState, hr = %x\n`
- `0x180029549`: `IPM2_MESSAGE_PIPE::CreateMessagePipe failed ReadMessage, hr = %x\n`

## pseudocode

```c
__int64 __fastcall IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(
        struct IPM2_MESSAGE_ACCEPTOR *a1,
        const unsigned __int16 *a2,
        int a3,
        int a4,
        DWORD nMaxInstances,
        struct _SECURITY_ATTRIBUTES *lpSecurityAttributes,
        struct IPM2_MESSAGE_PIPE **Mode,
        int *a8)
{
  bool v12; // zf
  struct IPM2_MESSAGE_PIPE **v13; // r14
  HMODULE ModuleHandleW; // rax
  IPM2_MESSAGE_PIPE *v15; // rax
  IPM2_MESSAGE_PIPE *v16; // rax
  IPM2_MESSAGE_PIPE *v17; // rbx
  HANDLE NamedPipeW; // rax
  signed int LastError; // eax
  unsigned int started; // edi
  unsigned int v21; // r8d
  int *v22; // rdx
  HANDLE FileW; // rax
  void *v24; // rbp
  signed int v25; // eax
  signed int v26; // eax
  int Message; // eax
  void *v28; // rcx
  void (__fastcall **v29)(IPM2_MESSAGE_PIPE *, __int64); // rax

  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 0x10000000) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x2ACu,
      "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe",
      "IPM2_MESSAGE_PIPE::CreateMessagePipe called name=%S\n",
      (char)a2);
  v12 = IISUtil2CancelIoEx == 0;
  v13 = Mode;
  *Mode = 0;
  if ( v12 )
  {
    ModuleHandleW = GetModuleHandleW(L"kernel32.dll");
    if ( ModuleHandleW )
      IISUtil2CancelIoEx = (int (*)(void *, struct _OVERLAPPED *))GetProcAddress(ModuleHandleW, "CancelIoEx");
  }
  v15 = (IPM2_MESSAGE_PIPE *)operator new(0x60u);
  if ( v15 )
  {
    v16 = IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPE(v15);
    v17 = v16;
    if ( v16 )
    {
      *((_QWORD *)v16 + 5) = a1;
      *((_DWORD *)v16 + 12) = a3;
      if ( a3 )
      {
        NamedPipeW = CreateNamedPipeW(
                       a2,
                       a4 != 0 ? 1074266115 : 1073741827,
                       6u,
                       nMaxInstances,
                       0x1000u,
                       0x1000u,
                       0,
                       lpSecurityAttributes);
        if ( NamedPipeW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          started = LastError;
          if ( LastError > 0 )
            started = (unsigned __int16)LastError | 0x80070000;
          if ( (g_dwDebugFlagsIISUtil & 0xF) == 0 )
            goto LABEL_32;
          v21 = 760;
LABEL_14:
          PuDbgPrint(
            (struct _DEBUG_PRINTS *)g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
            v21,
            "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe",
            "Pipe %S failed create, hr = 0x%08x Pipestate=%d\n ",
            (char)a2);
LABEL_32:
          v28 = (void *)*((_QWORD *)v17 + 4);
          if ( v28 != (void *)-1LL )
          {
            CloseHandle(v28);
            *((_QWORD *)v17 + 4) = -1;
          }
          v29 = *(void (__fastcall ***)(IPM2_MESSAGE_PIPE *, __int64))v17;
          *((_QWORD *)v17 + 5) = 0;
          (*v29)(v17, 1);
          return started;
        }
        v22 = a8;
        *((_QWORD *)v17 + 4) = NamedPipeW;
        started = IPM2_MESSAGE_PIPE::StartNamedPipe(v17, v22);
        if ( (started & 0x80000000) != 0 )
        {
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
              0x307u,
              "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe",
              "Pipe %S failed connect, hr = %x\n",
              (char)a2);
          goto LABEL_32;
        }
      }
      else
      {
        FileW = CreateFileW(a2, 0x120183u, 0, lpSecurityAttributes, 3u, 0x40100000u, 0);
        v24 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          v25 = GetLastError();
          started = v25;
          if ( v25 > 0 )
            started = (unsigned __int16)v25 | 0x80070000;
          if ( (g_dwDebugFlagsIISUtil & 0xF) == 0 )
            goto LABEL_32;
          v21 = 824;
          goto LABEL_14;
        }
        LODWORD(Mode) = 2;
        if ( !SetNamedPipeHandleState(FileW, (LPDWORD)&Mode, 0, 0) )
        {
          v26 = GetLastError();
          started = v26;
          if ( v26 > 0 )
            started = (unsigned __int16)v26 | 0x80070000;
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
              0x345u,
              "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe",
              "IPM2_MESSAGE_PIPE::CreateMessagePipe failed SetNamedPipeHandleState, hr = %x\n",
              started);
          CloseHandle(v24);
          goto LABEL_32;
        }
        *((_QWORD *)v17 + 4) = v24;
        _InterlockedExchange((volatile __int32 *)v17 + 22, 2);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v17 + 5) + 8LL))(*((_QWORD *)v17 + 5));
        Message = IPM2_MESSAGE_PIPE::ReadMessage(v17, 0x20u);
        started = Message;
        if ( Message < 0 )
        {
          if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
            PuDbgPrint(
              (struct _DEBUG_PRINTS *)g_pDebug,
              "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
              0x359u,
              "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe",
              "IPM2_MESSAGE_PIPE::CreateMessagePipe failed ReadMessage, hr = %x\n",
              Message);
          goto LABEL_32;
        }
      }
      *v13 = v17;
      return started;
    }
  }
  started = -2147024882;
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\pipedata2.cxx",
      0x2D4u,
      "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe",
      "Failed allocation of IPM2_MESSAGE_PIPE, hr = %x\n",
      14);
  return started;
}

```

## disassembly

```asm
0x1800291f0  push    rbx
0x1800291f2  push    rbp
0x1800291f3  push    rsi
0x1800291f4  push    rdi
0x1800291f5  push    r14
0x1800291f7  push    r15
0x1800291f9  sub     rsp, 48h
0x1800291fd  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180029203  mov     r15d, r9d
0x180029206  test    al, 3
0x180029208  mov     edi, r8d
0x18002920b  mov     rsi, rdx
0x18002920e  mov     rbp, rcx
0x180029211  setnz   r10b
0x180029215  bt      eax, 1Ch
0x180029219  setb    al
0x18002921c  test    al, r10b
0x18002921f  jz      short loc_180029252
0x180029221  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029228  lea     rax, aIpm2MessagePip_28; "IPM2_MESSAGE_PIPE::CreateMessagePipe ca"...
0x18002922f  mov     qword ptr [rsp+78h+nInBufferSize], rdx; char
0x180029234  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x18002923b  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029242  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x180029247  mov     r8d, 2ACh; unsigned int
0x18002924d  call    PuDbgPrint
0x180029252  cmp     cs:?IISUtil2CancelIoEx@@3P6AHPEAXPEAU_OVERLAPPED@@@ZEA, 0; int (*IISUtil2CancelIoEx)(void *,_OVERLAPPED *)
0x18002925a  mov     r14, [rsp+78h+Mode]
0x180029262  mov     qword ptr [r14], 0
0x180029269  jnz     short loc_1800292A0
0x18002926b  lea     rcx, ModuleName; "kernel32.dll"
0x180029272  call    cs:__imp_GetModuleHandleW
0x180029279  nop     dword ptr [rax+rax+00h]
0x18002927e  test    rax, rax
0x180029281  jz      short loc_1800292A0
0x180029283  lea     rdx, aCancelioex; "CancelIoEx"
0x18002928a  mov     rcx, rax; hModule
0x18002928d  call    cs:__imp_GetProcAddress
0x180029294  nop     dword ptr [rax+rax+00h]
0x180029299  mov     cs:?IISUtil2CancelIoEx@@3P6AHPEAXPEAU_OVERLAPPED@@@ZEA, rax; int (*IISUtil2CancelIoEx)(void *,_OVERLAPPED *)
0x1800292a0  mov     ecx, 60h ; '`'; Size
0x1800292a5  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800292aa  test    rax, rax
0x1800292ad  jz      loc_1800295A0
0x1800292b3  mov     rcx, rax; this
0x1800292b6  call    ??0IPM2_MESSAGE_PIPE@@AEAA@XZ; IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPE(void)
0x1800292bb  mov     rbx, rax
0x1800292be  test    rax, rax
0x1800292c1  jz      loc_1800295A0
0x1800292c7  mov     [rax+28h], rbp
0x1800292cb  mov     rcx, rsi; lpFileName
0x1800292ce  mov     [rax+30h], edi
0x1800292d1  test    edi, edi
0x1800292d3  jz      loc_1800293FA
0x1800292d9  mov     rax, [rsp+78h+arg_28]
0x1800292e1  neg     r15d
0x1800292e4  mov     r9d, [rsp+78h+nMaxInstances]; nMaxInstances
0x1800292ec  mov     r8d, 6; dwPipeMode
0x1800292f2  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x1800292f7  sbb     edx, edx
0x1800292f9  mov     eax, 1000h
0x1800292fe  mov     [rsp+78h+nDefaultTimeOut], 0; nDefaultTimeOut
0x180029306  and     edx, 80000h
0x18002930c  mov     [rsp+78h+nInBufferSize], eax; nInBufferSize
0x180029310  add     edx, 40000003h; dwOpenMode
0x180029316  mov     [rsp+78h+nOutBufferSize], eax; nOutBufferSize
0x18002931a  call    cs:__imp_CreateNamedPipeW
0x180029321  nop     dword ptr [rax+rax+00h]
0x180029326  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002932a  jnz     short loc_180029395
0x18002932c  call    cs:__imp_GetLastError
0x180029333  nop     dword ptr [rax+rax+00h]
0x180029338  mov     edi, eax
0x18002933a  test    eax, eax
0x18002933c  jle     short loc_180029347
0x18002933e  movzx   edi, ax
0x180029341  or      edi, 80070000h
0x180029347  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002934e  jz      loc_180029560
0x180029354  mov     r8d, 2F8h; unsigned int
0x18002935a  mov     eax, [rbx+58h]
0x18002935d  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x180029364  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18002936b  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029372  mov     dword ptr [rsp+78h+lpSecurityAttributes], eax
0x180029376  lea     rax, aPipeSFailedCre; "Pipe %S failed create, hr = 0x%08x Pipe"...
0x18002937d  mov     [rsp+78h+nDefaultTimeOut], edi
0x180029381  mov     qword ptr [rsp+78h+nInBufferSize], rsi; char
0x180029386  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x18002938b  call    PuDbgPrint
0x180029390  jmp     loc_180029560
0x180029395  mov     rdx, [rsp+78h+arg_38]; int *
0x18002939d  mov     rcx, rbx; this
0x1800293a0  mov     [rbx+20h], rax
0x1800293a4  call    ?StartNamedPipe@IPM2_MESSAGE_PIPE@@AEAAJPEAH@Z; IPM2_MESSAGE_PIPE::StartNamedPipe(int *)
0x1800293a9  mov     edi, eax
0x1800293ab  test    eax, eax
0x1800293ad  jns     loc_18002959B
0x1800293b3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800293ba  jz      loc_180029560
0x1800293c0  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800293c7  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x1800293ce  mov     [rsp+78h+nDefaultTimeOut], eax
0x1800293d2  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800293d9  lea     rax, aPipeSFailedCon; "Pipe %S failed connect, hr = %x\n"
0x1800293e0  mov     qword ptr [rsp+78h+nInBufferSize], rsi; char
0x1800293e5  mov     r8d, 307h; unsigned int
0x1800293eb  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x1800293f0  call    PuDbgPrint
0x1800293f5  jmp     loc_180029560
0x1800293fa  mov     r9, [rsp+78h+arg_28]; lpSecurityAttributes
0x180029402  xor     r8d, r8d; dwShareMode
0x180029405  mov     qword ptr [rsp+78h+nDefaultTimeOut], 0; hTemplateFile
0x18002940e  mov     edx, 120183h; dwDesiredAccess
0x180029413  mov     [rsp+78h+nInBufferSize], 40100000h; dwFlagsAndAttributes
0x18002941b  mov     [rsp+78h+nOutBufferSize], 3; dwCreationDisposition
0x180029423  call    cs:__imp_CreateFileW
0x18002942a  nop     dword ptr [rax+rax+00h]
0x18002942f  mov     rbp, rax
0x180029432  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029436  jnz     short loc_18002946B
0x180029438  call    cs:__imp_GetLastError
0x18002943f  nop     dword ptr [rax+rax+00h]
0x180029444  mov     edi, eax
0x180029446  test    eax, eax
0x180029448  jle     short loc_180029453
0x18002944a  movzx   edi, ax
0x18002944d  or      edi, 80070000h
0x180029453  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x18002945a  jz      loc_180029560
0x180029460  mov     r8d, 338h
0x180029466  jmp     loc_18002935A
0x18002946b  mov     edi, 2
0x180029470  lea     rdx, [rsp+78h+Mode]; lpMode
0x180029478  xor     r9d, r9d; lpCollectDataTimeout
0x18002947b  mov     dword ptr [rsp+78h+Mode], edi
0x180029482  xor     r8d, r8d; lpMaxCollectionCount
0x180029485  mov     rcx, rbp; hNamedPipe
0x180029488  call    cs:__imp_SetNamedPipeHandleState
0x18002948f  nop     dword ptr [rax+rax+00h]
0x180029494  test    eax, eax
0x180029496  jnz     short loc_1800294FD
0x180029498  call    cs:__imp_GetLastError
0x18002949f  nop     dword ptr [rax+rax+00h]
0x1800294a4  mov     edi, eax
0x1800294a6  test    eax, eax
0x1800294a8  jle     short loc_1800294B3
0x1800294aa  movzx   edi, ax
0x1800294ad  or      edi, 80070000h
0x1800294b3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800294ba  jz      short loc_1800294EC
0x1800294bc  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800294c3  lea     rax, aIpm2MessagePip_27; "IPM2_MESSAGE_PIPE::CreateMessagePipe fa"...
0x1800294ca  mov     [rsp+78h+nInBufferSize], edi; char
0x1800294ce  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x1800294d5  mov     r8d, 345h; unsigned int
0x1800294db  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x1800294e0  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800294e7  call    PuDbgPrint
0x1800294ec  mov     rcx, rbp; hObject
0x1800294ef  call    cs:__imp_CloseHandle
0x1800294f6  nop     dword ptr [rax+rax+00h]
0x1800294fb  jmp     short loc_180029560
0x1800294fd  mov     [rbx+20h], rbp
0x180029501  xchg    edi, [rbx+58h]
0x180029504  mov     rcx, [rbx+28h]
0x180029508  mov     rax, [rcx]
0x18002950b  mov     rax, [rax+8]
0x18002950f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029514  mov     edx, 20h ; ' '; nNumberOfBytesToRead
0x180029519  mov     rcx, rbx; this
0x18002951c  call    ?ReadMessage@IPM2_MESSAGE_PIPE@@AEAAJK@Z; IPM2_MESSAGE_PIPE::ReadMessage(ulong)
0x180029521  mov     edi, eax
0x180029523  test    eax, eax
0x180029525  jns     short loc_18002959B
0x180029527  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002952e  jz      short loc_180029560
0x180029530  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180029537  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x18002953e  mov     [rsp+78h+nInBufferSize], eax; char
0x180029542  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180029549  lea     rax, aIpm2MessagePip_31; "IPM2_MESSAGE_PIPE::CreateMessagePipe fa"...
0x180029550  mov     r8d, 359h; unsigned int
0x180029556  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x18002955b  call    PuDbgPrint
0x180029560  mov     rcx, [rbx+20h]; hObject
0x180029564  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180029568  jz      short loc_18002957E
0x18002956a  call    cs:__imp_CloseHandle
0x180029571  nop     dword ptr [rax+rax+00h]
0x180029576  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x18002957e  mov     rax, [rbx]
0x180029581  mov     edx, 1
0x180029586  mov     rcx, rbx
0x180029589  mov     qword ptr [rbx+28h], 0
0x180029591  mov     rax, [rax]
0x180029594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029599  jmp     short loc_1800295DE
0x18002959b  mov     [r14], rbx
0x18002959e  jmp     short loc_1800295DE
0x1800295a0  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800295a7  mov     edi, 8007000Eh
0x1800295ac  jz      short loc_1800295DE
0x1800295ae  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800295b5  lea     rax, aFailedAllocati; "Failed allocation of IPM2_MESSAGE_PIPE,"...
0x1800295bc  mov     [rsp+78h+nInBufferSize], edi; char
0x1800295c0  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x1800295c7  mov     r8d, 2D4h; unsigned int
0x1800295cd  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x1800295d2  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800295d9  call    PuDbgPrint
0x1800295de  mov     eax, edi
0x1800295e0  add     rsp, 48h
0x1800295e4  pop     r15
0x1800295e6  pop     r14
0x1800295e8  pop     rdi
0x1800295e9  pop     rsi
0x1800295ea  pop     rbp
0x1800295eb  pop     rbx
0x1800295ec  retn
```
