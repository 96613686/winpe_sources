# WEBSOCKET_WRAPPER::DoSendLoop(int *,COMPLETION_CONTEXT *,COMPLETION_CONTEXT * *,ulong *)

- ea: `0x180004568`
- end: `0x180004775`
- name: `?DoSendLoop@WEBSOCKET_WRAPPER@@AEAAJPEAHPEATCOMPLETION_CONTEXT@@PEAPEAT2@PEAK@Z`
- size: `525`
- prototype: `__int64 __fastcall(WEBSOCKET_WRAPPER *__hidden this, int *, union COMPLETION_CONTEXT *, union COMPLETION_CONTEXT **, unsigned int *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004ad4`
- `0x180004ebc`

## callees

- `0x180004568`
- `0x180005568`

## import_xrefs

- `websocket!WebSocketCompleteAction` at `0x18000473e`
- `websocket!WebSocketCompleteAction` at `0x18000473e`
- `websocket!WebSocketAbortHandle` at `0x180004726`
- `websocket!WebSocketAbortHandle` at `0x180004726`
- `websocket!WebSocketGetAction` at `0x180004608`
- `websocket!WebSocketGetAction` at `0x180004608`
- `iisutil!PuDbgPrint` at `0x180004650`
- `iisutil!PuDbgPrint` at `0x18000471c`
- `iisutil!PuDbgPrint` at `0x180004650`
- `iisutil!PuDbgPrint` at `0x18000471c`

## string_xrefs

- `0x180004633`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`
- `0x18000470a`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\wswrapper.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_WRAPPER::DoSendLoop(
        WEBSOCKET_WRAPPER *this,
        int *a2,
        union COMPLETION_CONTEXT *a3,
        union COMPLETION_CONTEXT **a4,
        unsigned int *a5)
{
  _QWORD *v5; // r15
  int v6; // edi
  __int64 v9; // r12
  int v10; // r13d
  __int64 v11; // rcx
  __int64 v12; // rdx
  int Action; // r14d
  int v14; // ecx
  int v15; // ecx
  unsigned int *v16; // rax
  unsigned int v18[2]; // [rsp+40h] [rbp-31h] BYREF
  __int64 v19; // [rsp+48h] [rbp-29h]
  union COMPLETION_CONTEXT *v20; // [rsp+50h] [rbp-21h]
  _OWORD v21[6]; // [rsp+58h] [rbp-19h] BYREF
  int v22; // [rsp+D0h] [rbp+5Fh] BYREF
  unsigned int v23; // [rsp+D8h] [rbp+67h] BYREF
  union COMPLETION_CONTEXT *v24; // [rsp+E0h] [rbp+6Fh]
  union COMPLETION_CONTEXT **v25; // [rsp+E8h] [rbp+77h]

  v25 = a4;
  v24 = a3;
  v5 = (_QWORD *)((char *)this + 16);
  v6 = 0;
  v20 = 0;
  v19 = 0;
  *a5 = 0;
  v9 = 0;
  v10 = 1;
  memset(v21, 0, 32);
  do
  {
    v11 = *((_QWORD *)this + 3);
    v22 = 0;
    v18[0] = 0;
    v23 = 2;
    v18[1] = 0;
    Action = WebSocketGetAction(v11, 1, v21, &v23, &v22);
    if ( Action < 0 )
      break;
    if ( (g_dwDebugFlags & 3) != 0 )
    {
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
        338,
        "WEBSOCKET_WRAPPER::DoSendLoop",
        "Action = %08x\n",
        v22);
      v5 = (_QWORD *)((char *)this + 16);
    }
    v14 = v22;
    if ( !v22 )
      break;
    *v5 = v19;
    v15 = v14 - 1;
    if ( v15 )
    {
      if ( v15 == 1 && (unsigned int)v9 < 2 )
      {
        if ( v24 == v20 )
        {
          v10 = 0;
        }
        else
        {
          v16 = a5;
          v25[v9] = v20;
          v9 = (unsigned int)(v9 + 1);
          *v16 = v9;
        }
      }
    }
    else
    {
      v6 = WEBSOCKET_IO_MANAGER::Send(
             (WEBSOCKET_WRAPPER *)((char *)this + 32),
             v12,
             (union _WEB_SOCKET_BUFFER *)v21,
             v23,
             v18,
             (void (*)(void *, int, unsigned int))WEBSOCKET_WRAPPER::SendLoopCompletionCallback,
             this,
             a2);
      if ( v6 >= 0 )
      {
        if ( *a2 )
          break;
      }
      else
      {
        if ( (g_dwDebugFlags & 0xF) != 0 )
          PuDbgPrint(
            g_pDebug,
            "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\wswrapper.cxx",
            378,
            "WEBSOCKET_WRAPPER::DoSendLoop",
            "Aborting Handle %08x\n",
            *((_QWORD *)this + 3));
        WebSocketAbortHandle(*((_QWORD *)this + 3));
      }
    }
    WebSocketCompleteAction(*((_QWORD *)this + 3), *v5, v18[0]);
  }
  while ( v22 );
  *a2 = v10;
  if ( v6 < 0 )
  {
    Action = v6;
    *a2 = 0;
  }
  return (unsigned int)Action;
}

```

## disassembly

```asm
0x180004568  mov     [rsp-8+arg_18], r9
0x18000456d  mov     [rsp-8+arg_10], r8
0x180004572  push    rbp
0x180004573  push    rbx
0x180004574  push    rsi
0x180004575  push    rdi
0x180004576  push    r12
0x180004578  push    r13
0x18000457a  push    r14
0x18000457c  push    r15
0x18000457e  lea     rbp, [rsp-17h]
0x180004583  sub     rsp, 88h
0x18000458a  mov     rax, [rbp+4Fh+arg_20]
0x18000458e  lea     r15, [rcx+10h]
0x180004592  xor     edi, edi
0x180004594  xorps   xmm0, xmm0
0x180004597  mov     rbx, rdx
0x18000459a  mov     [rbp+4Fh+var_70], rdi
0x18000459e  mov     rsi, rcx
0x1800045a1  mov     [rbp+4Fh+var_78], rdi
0x1800045a5  mov     [rax], edi
0x1800045a7  xor     r12d, r12d
0x1800045aa  lea     r13d, [rdi+1]
0x1800045ae  movdqu  [rbp+4Fh+var_68], xmm0
0x1800045b3  movups  [rbp+4Fh+var_58], xmm0
0x1800045b7  mov     rcx, [rsi+18h]
0x1800045bb  lea     rax, [rbp+4Fh+var_78]
0x1800045bf  mov     [rsp+0C0h+var_88], rax
0x1800045c4  lea     r9, [rbp+4Fh+arg_8]
0x1800045c8  lea     rax, [rbp+4Fh+var_70]
0x1800045cc  mov     [rbp+4Fh+arg_0], 0
0x1800045d3  mov     [rsp+0C0h+var_90], rax
0x1800045d8  lea     r8, [rbp+4Fh+var_68]
0x1800045dc  lea     rax, [rbp+4Fh+var_7C]
0x1800045e0  mov     [rbp+4Fh+var_80], 0
0x1800045e7  mov     [rsp+0C0h+var_98], rax
0x1800045ec  mov     edx, 1
0x1800045f1  lea     rax, [rbp+4Fh+arg_0]
0x1800045f5  mov     [rbp+4Fh+arg_8], 2
0x1800045fc  mov     [rsp+0C0h+var_A0], rax
0x180004601  mov     [rbp+4Fh+var_7C], 0
0x180004608  call    cs:__imp_WebSocketGetAction
0x18000460e  mov     r14d, eax
0x180004611  test    eax, eax
0x180004613  js      loc_18000474E
0x180004619  test    byte ptr cs:g_dwDebugFlags, 3
0x180004620  jz      short loc_18000465A
0x180004622  mov     eax, [rbp+4Fh+arg_0]
0x180004625  lea     r9, aWebsocketWrapp_2; "WEBSOCKET_WRAPPER::DoSendLoop"
0x18000462c  mov     rcx, cs:g_pDebug
0x180004633  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x18000463a  mov     dword ptr [rsp+0C0h+var_98], eax
0x18000463e  mov     r8d, 152h
0x180004644  lea     rax, aAction08x; "Action = %08x\n"
0x18000464b  mov     [rsp+0C0h+var_A0], rax
0x180004650  call    cs:__imp_PuDbgPrint
0x180004656  lea     r15, [rsi+10h]
0x18000465a  mov     ecx, [rbp+4Fh+arg_0]
0x18000465d  test    ecx, ecx
0x18000465f  jz      loc_18000474E
0x180004665  mov     rax, [rbp+4Fh+var_78]
0x180004669  mov     [r15], rax
0x18000466c  sub     ecx, 1
0x18000466f  jz      short loc_1800046AD
0x180004671  cmp     ecx, 1
0x180004674  jnz     loc_180004733
0x18000467a  cmp     r12d, 2
0x18000467e  jnb     loc_180004733
0x180004684  mov     rcx, [rbp+4Fh+var_70]
0x180004688  cmp     [rbp+4Fh+arg_10], rcx
0x18000468c  jz      short loc_1800046A5
0x18000468e  mov     rdx, [rbp+4Fh+arg_18]
0x180004692  mov     rax, [rbp+4Fh+arg_20]
0x180004696  mov     [rdx+r12*8], rcx
0x18000469a  inc     r12d
0x18000469d  mov     [rax], r12d
0x1800046a0  jmp     loc_180004733
0x1800046a5  xor     r13d, r13d
0x1800046a8  jmp     loc_180004733
0x1800046ad  mov     r9d, [rbp+4Fh+arg_8]; unsigned int
0x1800046b1  lea     rax, ?SendLoopCompletionCallback@WEBSOCKET_WRAPPER@@CAXPEAXJK@Z; WEBSOCKET_WRAPPER::SendLoopCompletionCallback(void *,long,ulong)
0x1800046b8  mov     [rsp+0C0h+var_88], rbx; int *
0x1800046bd  lea     rcx, [rsi+20h]; this
0x1800046c1  mov     [rsp+0C0h+var_90], rsi; void *
0x1800046c6  lea     r8, [rbp+4Fh+var_68]; union _WEB_SOCKET_BUFFER *
0x1800046ca  mov     [rsp+0C0h+var_98], rax; void (*)(void *, int, unsigned int)
0x1800046cf  lea     rax, [rbp+4Fh+var_80]
0x1800046d3  mov     [rsp+0C0h+var_A0], rax; unsigned int *
0x1800046d8  call    ?Send@WEBSOCKET_IO_MANAGER@@QEAAJHPEAT_WEB_SOCKET_BUFFER@@KPEAKP6AXPEAXJK@Z2PEAH@Z; WEBSOCKET_IO_MANAGER::Send(int,_WEB_SOCKET_BUFFER *,ulong,ulong *,void (*)(void *,long,ulong),void *,int *)
0x1800046dd  mov     edi, eax
0x1800046df  test    eax, eax
0x1800046e1  jns     short loc_18000472E
0x1800046e3  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x1800046ea  jz      short loc_180004722
0x1800046ec  mov     rcx, [rsi+18h]
0x1800046f0  lea     rax, aAbortingHandle; "Aborting Handle %08x\n"
0x1800046f7  mov     [rsp+0C0h+var_98], rcx
0x1800046fc  lea     r9, aWebsocketWrapp_2; "WEBSOCKET_WRAPPER::DoSendLoop"
0x180004703  mov     rcx, cs:g_pDebug
0x18000470a  lea     rdx, aServercommonIn_3; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180004711  mov     r8d, 17Ah
0x180004717  mov     [rsp+0C0h+var_A0], rax
0x18000471c  call    cs:__imp_PuDbgPrint
0x180004722  mov     rcx, [rsi+18h]
0x180004726  call    cs:__imp_WebSocketAbortHandle
0x18000472c  jmp     short loc_180004733
0x18000472e  cmp     dword ptr [rbx], 0
0x180004731  jnz     short loc_18000474E
0x180004733  mov     r8d, [rbp+4Fh+var_80]
0x180004737  mov     rdx, [r15]
0x18000473a  mov     rcx, [rsi+18h]
0x18000473e  call    cs:__imp_WebSocketCompleteAction
0x180004744  cmp     [rbp+4Fh+arg_0], 0
0x180004748  jnz     loc_1800045B7
0x18000474e  mov     [rbx], r13d
0x180004751  test    edi, edi
0x180004753  jns     short loc_18000475E
0x180004755  mov     r14d, edi
0x180004758  mov     dword ptr [rbx], 0
0x18000475e  mov     eax, r14d
0x180004761  add     rsp, 88h
0x180004768  pop     r15
0x18000476a  pop     r14
0x18000476c  pop     r13
0x18000476e  pop     r12
0x180004770  pop     rdi
0x180004771  pop     rsi
0x180004772  pop     rbx
0x180004773  pop     rbp
0x180004774  retn
```
