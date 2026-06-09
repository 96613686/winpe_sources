# IPM2_MESSAGE_PIPE::CreateIpmMessagePipe(IPM2_MESSAGE_ACCEPTOR *,ushort const *,int,int,ulong,_SECURITY_ATTRIBUTES *,IPM2_MESSAGE_PIPE * *,int *)

- ea: `0x180027520`
- end: `0x1800278e1`
- name: `?CreateIpmMessagePipe@IPM2_MESSAGE_PIPE@@SAJPEAVIPM2_MESSAGE_ACCEPTOR@@PEBGHHKPEAU_SECURITY_ATTRIBUTES@@PEAPEAV1@PEAH@Z`
- size: `961`
- prototype: `static int(struct IPM2_MESSAGE_ACCEPTOR *, const unsigned __int16 *, int, int, unsigned int, struct _SECURITY_ATTRIBUTES *, struct IPM2_MESSAGE_PIPE **, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800278f0`
- `0x180029730`

## callees

- `0x180007300`
- `0x1800183f8`
- `0x180027270`
- `0x180027520`
- `0x180028ca0`
- `0x180028f50`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002764a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002774a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002779e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002764a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002774a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002779e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800275b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800275b7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800275a2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800275a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800277ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027864`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800277ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180027864`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002773b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002773b`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180027794`
- `api-ms-win-core-namedpipe-l1-1-0!SetNamedPipeHandleState` at `0x180027794`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18002763e`
- `api-ms-win-core-namedpipe-l1-1-0!CreateNamedPipeW` at `0x18002763e`

## string_xrefs

- `0x18002759b`: `kernel32.dll`
- `0x18002756b`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027683`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800276ea`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800277e0`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x18002783c`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x1800278c6`: `servercommon\inetsrv\iis\iisrearc\core\common\util\pipedata2.cxx`
- `0x180027558`: `IPM2_MESSAGE_PIPE::CreateMessagePipe called name=%S\n`
- `0x180027564`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x180027675`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800276df`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800277ce`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x180027831`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x1800278b4`: `IPM2_MESSAGE_PIPE::CreateIpmMessagePipe`
- `0x18002768e`: `Pipe %S failed create, hr = 0x%08x Pipestate=%d\n `
- `0x1800277c3`: `IPM2_MESSAGE_PIPE::CreateMessagePipe failed SetNamedPipeHandleState, hr = %x\n`
- `0x180027843`: `IPM2_MESSAGE_PIPE::CreateMessagePipe failed ReadMessage, hr = %x\n`

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
0x180027520  push    rbx
0x180027522  push    rbp
0x180027523  push    rsi
0x180027524  push    rdi
0x180027525  push    r14
0x180027527  push    r15
0x180027529  sub     rsp, 48h
0x18002752d  mov     eax, cs:g_dwDebugFlagsIISUtil
0x180027533  mov     r15d, r9d
0x180027536  test    al, 3
0x180027538  mov     edi, r8d
0x18002753b  mov     rsi, rdx
0x18002753e  mov     rbp, rcx
0x180027541  setnz   r10b
0x180027545  bt      eax, 1Ch
0x180027549  setb    al
0x18002754c  test    al, r10b
0x18002754f  jz      short loc_180027582
0x180027551  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027558  lea     rax, aIpm2MessagePip_28; "IPM2_MESSAGE_PIPE::CreateMessagePipe ca"...
0x18002755f  mov     qword ptr [rsp+78h+nInBufferSize], rdx; char
0x180027564  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x18002756b  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027572  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x180027577  mov     r8d, 2ACh; unsigned int
0x18002757d  call    PuDbgPrint
0x180027582  cmp     cs:?IISUtil2CancelIoEx@@3P6AHPEAXPEAU_OVERLAPPED@@@ZEA, 0; int (*IISUtil2CancelIoEx)(void *,_OVERLAPPED *)
0x18002758a  mov     r14, [rsp+78h+Mode]
0x180027592  mov     qword ptr [r14], 0
0x180027599  jnz     short loc_1800275C4
0x18002759b  lea     rcx, ModuleName; "kernel32.dll"
0x1800275a2  call    cs:__imp_GetModuleHandleW
0x1800275a8  test    rax, rax
0x1800275ab  jz      short loc_1800275C4
0x1800275ad  lea     rdx, aCancelioex; "CancelIoEx"
0x1800275b4  mov     rcx, rax; hModule
0x1800275b7  call    cs:__imp_GetProcAddress
0x1800275bd  mov     cs:?IISUtil2CancelIoEx@@3P6AHPEAXPEAU_OVERLAPPED@@@ZEA, rax; int (*IISUtil2CancelIoEx)(void *,_OVERLAPPED *)
0x1800275c4  mov     ecx, 60h ; '`'; Size
0x1800275c9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800275ce  test    rax, rax
0x1800275d1  jz      loc_180027894
0x1800275d7  mov     rcx, rax; this
0x1800275da  call    ??0IPM2_MESSAGE_PIPE@@AEAA@XZ; IPM2_MESSAGE_PIPE::IPM2_MESSAGE_PIPE(void)
0x1800275df  mov     rbx, rax
0x1800275e2  test    rax, rax
0x1800275e5  jz      loc_180027894
0x1800275eb  mov     [rax+28h], rbp
0x1800275ef  mov     rcx, rsi; lpFileName
0x1800275f2  mov     [rax+30h], edi
0x1800275f5  test    edi, edi
0x1800275f7  jz      loc_180027712
0x1800275fd  mov     rax, [rsp+78h+arg_28]
0x180027605  neg     r15d
0x180027608  mov     r9d, [rsp+78h+nMaxInstances]; nMaxInstances
0x180027610  mov     r8d, 6; dwPipeMode
0x180027616  mov     [rsp+78h+lpSecurityAttributes], rax; lpSecurityAttributes
0x18002761b  sbb     edx, edx
0x18002761d  mov     eax, 1000h
0x180027622  mov     [rsp+78h+nDefaultTimeOut], 0; nDefaultTimeOut
0x18002762a  and     edx, 80000h
0x180027630  mov     [rsp+78h+nInBufferSize], eax; nInBufferSize
0x180027634  add     edx, 40000003h; dwOpenMode
0x18002763a  mov     [rsp+78h+nOutBufferSize], eax; nOutBufferSize
0x18002763e  call    cs:__imp_CreateNamedPipeW
0x180027644  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027648  jnz     short loc_1800276AD
0x18002764a  call    cs:__imp_GetLastError
0x180027650  mov     edi, eax
0x180027652  test    eax, eax
0x180027654  jle     short loc_18002765F
0x180027656  movzx   edi, ax
0x180027659  or      edi, 80070000h
0x18002765f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180027666  jz      loc_18002785A
0x18002766c  mov     r8d, 2F8h; unsigned int
0x180027672  mov     eax, [rbx+58h]
0x180027675  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x18002767c  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027683  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18002768a  mov     dword ptr [rsp+78h+lpSecurityAttributes], eax
0x18002768e  lea     rax, aPipeSFailedCre; "Pipe %S failed create, hr = 0x%08x Pipe"...
0x180027695  mov     [rsp+78h+nDefaultTimeOut], edi
0x180027699  mov     qword ptr [rsp+78h+nInBufferSize], rsi; char
0x18002769e  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x1800276a3  call    PuDbgPrint
0x1800276a8  jmp     loc_18002785A
0x1800276ad  mov     rdx, [rsp+78h+arg_38]; int *
0x1800276b5  mov     rcx, rbx; this
0x1800276b8  mov     [rbx+20h], rax
0x1800276bc  call    ?StartNamedPipe@IPM2_MESSAGE_PIPE@@AEAAJPEAH@Z; IPM2_MESSAGE_PIPE::StartNamedPipe(int *)
0x1800276c1  mov     edi, eax
0x1800276c3  test    eax, eax
0x1800276c5  jns     loc_18002788F
0x1800276cb  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800276d2  jz      loc_18002785A
0x1800276d8  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800276df  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x1800276e6  mov     [rsp+78h+nDefaultTimeOut], eax
0x1800276ea  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800276f1  lea     rax, aPipeSFailedCon; "Pipe %S failed connect, hr = %x\n"
0x1800276f8  mov     qword ptr [rsp+78h+nInBufferSize], rsi; char
0x1800276fd  mov     r8d, 307h; unsigned int
0x180027703  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x180027708  call    PuDbgPrint
0x18002770d  jmp     loc_18002785A
0x180027712  mov     r9, [rsp+78h+arg_28]; lpSecurityAttributes
0x18002771a  xor     r8d, r8d; dwShareMode
0x18002771d  mov     qword ptr [rsp+78h+nDefaultTimeOut], 0; hTemplateFile
0x180027726  mov     edx, 120183h; dwDesiredAccess
0x18002772b  mov     [rsp+78h+nInBufferSize], 40100000h; dwFlagsAndAttributes
0x180027733  mov     [rsp+78h+nOutBufferSize], 3; dwCreationDisposition
0x18002773b  call    cs:__imp_CreateFileW
0x180027741  mov     rbp, rax
0x180027744  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180027748  jnz     short loc_180027777
0x18002774a  call    cs:__imp_GetLastError
0x180027750  mov     edi, eax
0x180027752  test    eax, eax
0x180027754  jle     short loc_18002775F
0x180027756  movzx   edi, ax
0x180027759  or      edi, 80070000h
0x18002775f  test    byte ptr cs:g_dwDebugFlagsIISUtil, 0Fh
0x180027766  jz      loc_18002785A
0x18002776c  mov     r8d, 338h
0x180027772  jmp     loc_180027672
0x180027777  mov     edi, 2
0x18002777c  lea     rdx, [rsp+78h+Mode]; lpMode
0x180027784  xor     r9d, r9d; lpCollectDataTimeout
0x180027787  mov     dword ptr [rsp+78h+Mode], edi
0x18002778e  xor     r8d, r8d; lpMaxCollectionCount
0x180027791  mov     rcx, rbp; hNamedPipe
0x180027794  call    cs:__imp_SetNamedPipeHandleState
0x18002779a  test    eax, eax
0x18002779c  jnz     short loc_1800277F7
0x18002779e  call    cs:__imp_GetLastError
0x1800277a4  mov     edi, eax
0x1800277a6  test    eax, eax
0x1800277a8  jle     short loc_1800277B3
0x1800277aa  movzx   edi, ax
0x1800277ad  or      edi, 80070000h
0x1800277b3  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x1800277ba  jz      short loc_1800277EC
0x1800277bc  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800277c3  lea     rax, aIpm2MessagePip_27; "IPM2_MESSAGE_PIPE::CreateMessagePipe fa"...
0x1800277ca  mov     [rsp+78h+nInBufferSize], edi; char
0x1800277ce  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x1800277d5  mov     r8d, 345h; unsigned int
0x1800277db  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x1800277e0  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800277e7  call    PuDbgPrint
0x1800277ec  mov     rcx, rbp; hObject
0x1800277ef  call    cs:__imp_CloseHandle
0x1800277f5  jmp     short loc_18002785A
0x1800277f7  mov     [rbx+20h], rbp
0x1800277fb  xchg    edi, [rbx+58h]
0x1800277fe  mov     rcx, [rbx+28h]
0x180027802  mov     rax, [rcx]
0x180027805  mov     rax, [rax+8]
0x180027809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002780e  mov     edx, 20h ; ' '; nNumberOfBytesToRead
0x180027813  mov     rcx, rbx; this
0x180027816  call    ?ReadMessage@IPM2_MESSAGE_PIPE@@AEAAJK@Z; IPM2_MESSAGE_PIPE::ReadMessage(ulong)
0x18002781b  mov     edi, eax
0x18002781d  test    eax, eax
0x18002781f  jns     short loc_18002788F
0x180027821  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x180027828  jz      short loc_18002785A
0x18002782a  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x180027831  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x180027838  mov     [rsp+78h+nInBufferSize], eax; char
0x18002783c  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x180027843  lea     rax, aIpm2MessagePip_31; "IPM2_MESSAGE_PIPE::CreateMessagePipe fa"...
0x18002784a  mov     r8d, 359h; unsigned int
0x180027850  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x180027855  call    PuDbgPrint
0x18002785a  mov     rcx, [rbx+20h]; hObject
0x18002785e  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180027862  jz      short loc_180027872
0x180027864  call    cs:__imp_CloseHandle
0x18002786a  mov     qword ptr [rbx+20h], 0FFFFFFFFFFFFFFFFh
0x180027872  mov     rax, [rbx]
0x180027875  mov     edx, 1
0x18002787a  mov     rcx, rbx
0x18002787d  mov     qword ptr [rbx+28h], 0
0x180027885  mov     rax, [rax]
0x180027888  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002788d  jmp     short loc_1800278D2
0x18002788f  mov     [r14], rbx
0x180027892  jmp     short loc_1800278D2
0x180027894  test    byte ptr cs:g_dwDebugFlagsIISUtil, 3
0x18002789b  mov     edi, 8007000Eh
0x1800278a0  jz      short loc_1800278D2
0x1800278a2  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x1800278a9  lea     rax, aFailedAllocati; "Failed allocation of IPM2_MESSAGE_PIPE,"...
0x1800278b0  mov     [rsp+78h+nInBufferSize], edi; char
0x1800278b4  lea     r9, aIpm2MessagePip_10; "IPM2_MESSAGE_PIPE::CreateIpmMessagePipe"
0x1800278bb  mov     r8d, 2D4h; unsigned int
0x1800278c1  mov     qword ptr [rsp+78h+nOutBufferSize], rax; char *
0x1800278c6  lea     rdx, aServercommonIn_4; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x1800278cd  call    PuDbgPrint
0x1800278d2  mov     eax, edi
0x1800278d4  add     rsp, 48h
0x1800278d8  pop     r15
0x1800278da  pop     r14
0x1800278dc  pop     rdi
0x1800278dd  pop     rsi
0x1800278de  pop     rbp
0x1800278df  pop     rbx
0x1800278e0  retn
```
