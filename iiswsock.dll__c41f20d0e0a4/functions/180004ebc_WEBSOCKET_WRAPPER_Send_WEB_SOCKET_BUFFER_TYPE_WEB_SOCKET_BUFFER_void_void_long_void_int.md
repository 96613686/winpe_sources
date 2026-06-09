# WEBSOCKET_WRAPPER::Send(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,void (*)(void *,long),void *,int *)

- ea: `0x180004ebc`
- end: `0x18000503b`
- name: `?Send@WEBSOCKET_WRAPPER@@QEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@P6AXPEAXJ@Z2PEAH@Z`
- size: `383`
- prototype: `__int64 __fastcall(ULONGLONG *, unsigned int, __int64, __int64, __int64, int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800069a0`
- `0x180007674`

## callees

- `0x180001008`
- `0x180001048`
- `0x180004568`
- `0x180004ebc`
- `0x180009010`

## import_xrefs

- `websocket!WebSocketSend` at `0x180004f61`
- `websocket!WebSocketSend` at `0x180004f61`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004f21`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180004f21`
- `iisutil!PuDbgPrint` at `0x180004f1b`
- `iisutil!PuDbgPrint` at `0x18000501e`
- `iisutil!PuDbgPrint` at `0x180004f1b`
- `iisutil!PuDbgPrint` at `0x18000501e`

## string_xrefs

- `0x180004f0f`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x18000500c`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_WRAPPER::Send(ULONGLONG *a1, unsigned int a2, __int64 a3, __int64 a4, __int64 a5, int *a6)
{
  _QWORD *v10; // rax
  void *v11; // rbx
  int v12; // esi
  int *v13; // rdi
  unsigned int v14; // r14d
  __int64 i; // rbp
  _QWORD *v16; // rbx
  void *Block[2]; // [rsp+40h] [rbp-28h] BYREF
  unsigned int v19; // [rsp+70h] [rbp+8h] BYREF

  *(_OWORD *)Block = 0;
  v19 = 2;
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
      163,
      "WEBSOCKET_WRAPPER::Send",
      "BufferType = %08x\n",
      a2);
  *a1 = GetTickCount64();
  v10 = operator new(0x10u);
  v11 = v10;
  if ( !v10 )
  {
    v12 = -2147024882;
    goto LABEL_13;
  }
  *v10 = a4;
  v10[1] = a5;
  v12 = WebSocketSend(a1[3], a2, a3, v10);
  if ( v12 < 0
    || (v13 = a6,
        v12 = WEBSOCKET_WRAPPER::DoSendLoop(
                (WEBSOCKET_WRAPPER *)a1,
                a6,
                (union COMPLETION_CONTEXT *)v11,
                (union COMPLETION_CONTEXT **)Block,
                &v19),
        v12 < 0) )
  {
    operator delete(v11);
LABEL_13:
    if ( (g_dwDebugFlags & 0xF) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
        241,
        "WEBSOCKET_WRAPPER::Send",
        "ERROR = %08x for BufferType = %08x\n",
        v12,
        a2);
    return (unsigned int)v12;
  }
  if ( !*v13 )
    operator delete(v11);
  v14 = v19;
  for ( i = 0; (unsigned int)i < v14; i = (unsigned int)(i + 1) )
  {
    v16 = Block[i];
    ((void (__fastcall *)(_QWORD, _QWORD))*v16)(v16[1], (unsigned int)v12);
    operator delete(v16);
    Block[i] = 0;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180004ebc  mov     rax, rsp
0x180004ebf  mov     [rax+10h], rbx
0x180004ec3  mov     [rax+18h], rbp
0x180004ec7  push    rsi
0x180004ec8  push    rdi
0x180004ec9  push    r14
0x180004ecb  sub     rsp, 50h
0x180004ecf  test    byte ptr cs:g_dwDebugFlags, 3
0x180004ed6  xorps   xmm0, xmm0
0x180004ed9  movups  xmmword ptr [rax-28h], xmm0
0x180004edd  mov     rdi, r9
0x180004ee0  mov     dword ptr [rax+8], 2
0x180004ee7  mov     rsi, r8
0x180004eea  mov     ebp, edx
0x180004eec  mov     r14, rcx
0x180004eef  jz      short loc_180004F21
0x180004ef1  mov     rcx, cs:g_pDebug
0x180004ef8  lea     r9, aWebsocketWrapp_4; "WEBSOCKET_WRAPPER::Send"
0x180004eff  mov     [rax-40h], edx
0x180004f02  mov     r8d, 0A3h
0x180004f08  lea     rax, aBuffertype08x; "BufferType = %08x\n"
0x180004f0f  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004f16  mov     [rsp+68h+var_48], rax
0x180004f1b  call    cs:__imp_PuDbgPrint
0x180004f21  call    cs:__imp_GetTickCount64
0x180004f27  mov     ecx, 10h; Size
0x180004f2c  mov     [r14], rax
0x180004f2f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180004f34  mov     rbx, rax
0x180004f37  test    rax, rax
0x180004f3a  jnz     short loc_180004F46
0x180004f3c  mov     esi, 8007000Eh
0x180004f41  jmp     loc_180004FE6
0x180004f46  mov     [rax], rdi
0x180004f49  mov     r9, rbx
0x180004f4c  mov     rax, [rsp+68h+arg_20]
0x180004f54  mov     r8, rsi
0x180004f57  mov     [rbx+8], rax
0x180004f5b  mov     edx, ebp
0x180004f5d  mov     rcx, [r14+18h]
0x180004f61  call    cs:__imp_WebSocketSend
0x180004f67  mov     esi, eax
0x180004f69  test    eax, eax
0x180004f6b  js      short loc_180004FDE
0x180004f6d  mov     rdi, [rsp+68h+arg_28]
0x180004f75  lea     rax, [rsp+68h+arg_0]
0x180004f7a  mov     rdx, rdi; int *
0x180004f7d  mov     [rsp+68h+var_48], rax; unsigned int *
0x180004f82  lea     r9, [rsp+68h+Block]; union COMPLETION_CONTEXT **
0x180004f87  mov     r8, rbx; union COMPLETION_CONTEXT *
0x180004f8a  mov     rcx, r14; this
0x180004f8d  call    ?DoSendLoop@WEBSOCKET_WRAPPER@@AEAAJPEAHPEATCOMPLETION_CONTEXT@@PEAPEAT2@PEAK@Z; WEBSOCKET_WRAPPER::DoSendLoop(int *,COMPLETION_CONTEXT *,COMPLETION_CONTEXT * *,ulong *)
0x180004f92  mov     esi, eax
0x180004f94  test    eax, eax
0x180004f96  js      short loc_180004FDE
0x180004f98  cmp     dword ptr [rdi], 0
0x180004f9b  jnz     short loc_180004FA5
0x180004f9d  mov     rcx, rbx; Block
0x180004fa0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004fa5  mov     r14d, [rsp+68h+arg_0]
0x180004faa  xor     ebp, ebp
0x180004fac  test    r14d, r14d
0x180004faf  jz      short loc_180005024
0x180004fb1  mov     rbx, [rsp+rbp*8+68h+Block]
0x180004fb6  mov     edx, esi
0x180004fb8  mov     rcx, [rbx+8]
0x180004fbc  mov     rax, [rbx]
0x180004fbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc4  mov     rcx, rbx; Block
0x180004fc7  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004fcc  mov     [rsp+rbp*8+68h+Block], 0
0x180004fd5  inc     ebp
0x180004fd7  cmp     ebp, r14d
0x180004fda  jb      short loc_180004FB1
0x180004fdc  jmp     short loc_180005024
0x180004fde  mov     rcx, rbx; Block
0x180004fe1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180004fe6  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x180004fed  jz      short loc_180005024
0x180004fef  mov     rcx, cs:g_pDebug
0x180004ff6  lea     rax, aError08xForBuf; "ERROR = %08x for BufferType = %08x\n"
0x180004ffd  mov     [rsp+68h+var_38], ebp
0x180005001  lea     r9, aWebsocketWrapp_4; "WEBSOCKET_WRAPPER::Send"
0x180005008  mov     [rsp+68h+var_40], esi
0x18000500c  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005013  mov     r8d, 0F1h
0x180005019  mov     [rsp+68h+var_48], rax
0x18000501e  call    cs:__imp_PuDbgPrint
0x180005024  lea     r11, [rsp+68h+var_18]
0x180005029  mov     eax, esi
0x18000502b  mov     rbx, [r11+28h]
0x18000502f  mov     rbp, [r11+30h]
0x180005033  mov     rsp, r11
0x180005036  pop     r14
0x180005038  pop     rdi
0x180005039  pop     rsi
0x18000503a  retn
```
