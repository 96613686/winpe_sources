# WEBSOCKET_CONTEXT::OnWebSocketSendCloseCompletion(void *,long)

- ea: `0x180005fd0`
- end: `0x1800060b1`
- name: `?OnWebSocketSendCloseCompletion@WEBSOCKET_CONTEXT@@CAXPEAXJ@Z`
- size: `225`
- prototype: `void __fastcall(WEBSOCKET_CONTEXT *this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001ce0`
- `0x180002168`
- `0x180005cb8`
- `0x180005fd0`
- `0x180009010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x18000606f`
- `iisutil!WriteRefTraceLog` at `0x18000606f`

## pseudocode

```c
void __fastcall WEBSOCKET_CONTEXT::OnWebSocketSendCloseCompletion(WEBSOCKET_CONTEXT *this, int a2)
{
  struct IHttpContext **v2; // rdi
  __int64 v5; // rax
  struct IHttpContext *v6; // rdx
  volatile signed __int32 *v7; // rdi
  __int64 v8; // rcx

  *((_DWORD *)this + 90) = 1;
  v2 = (struct IHttpContext **)((char *)this + 344);
  if ( *((_DWORD *)this + 89) )
  {
    v5 = (*(__int64 (__fastcall **)(struct IHttpContext *))(*(_QWORD *)*v2 + 32LL))(*v2);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 96LL))(v5);
  }
  v6 = *v2;
  if ( a2 >= 0 )
    TRACE_HELPER::RaiseTraceEvent(this, v6, 0x32u);
  else
    TRACE_HELPER::RaiseTraceEventError(this, v6, 0x33u, a2);
  v7 = (volatile signed __int32 *)((char *)this + 380);
  if ( *((_DWORD *)this + 88) != 3 )
    WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest(this, a2);
  v8 = *((_QWORD *)this + 54);
  if ( v8 )
    WriteRefTraceLog(v8, *(unsigned int *)v7, this);
  if ( _InterlockedExchangeAdd(v7, 0xFFFFFFFF) == 1 && *((_DWORD *)this + 88) == 3 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 43) + 64LL))(*((_QWORD *)this + 43), 0);
}

```

## disassembly

```asm
0x180005fd0  mov     [rsp+arg_0], rbx
0x180005fd5  mov     [rsp+arg_8], rsi
0x180005fda  push    rdi
0x180005fdb  sub     rsp, 20h
0x180005fdf  mov     dword ptr [rcx+168h], 1
0x180005fe9  lea     rdi, [rcx+158h]
0x180005ff0  mov     eax, [rcx+164h]
0x180005ff6  mov     esi, edx
0x180005ff8  mov     rbx, rcx
0x180005ffb  test    eax, eax
0x180005ffd  jz      short loc_180006020
0x180005fff  mov     rcx, [rdi]
0x180006002  mov     rax, [rcx]
0x180006005  mov     rax, [rax+20h]
0x180006009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000600e  mov     rdx, rax
0x180006011  mov     rcx, [rax]
0x180006014  mov     rax, [rcx+60h]
0x180006018  mov     rcx, rdx
0x18000601b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006020  mov     rdx, [rdi]; struct IHttpContext *
0x180006023  test    esi, esi
0x180006025  jns     short loc_180006037
0x180006027  mov     r9d, esi; int
0x18000602a  mov     r8d, 33h ; '3'; unsigned int
0x180006030  call    ?RaiseTraceEventError@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KJ@Z; TRACE_HELPER::RaiseTraceEventError(IHttpContext *,ulong,long)
0x180006035  jmp     short loc_180006042
0x180006037  mov     r8d, 32h ; '2'; unsigned int
0x18000603d  call    ?RaiseTraceEvent@TRACE_HELPER@@QEAAXPEAVIHttpContext@@K@Z; TRACE_HELPER::RaiseTraceEvent(IHttpContext *,ulong)
0x180006042  mov     eax, [rbx+160h]
0x180006048  lea     rdi, [rbx+17Ch]
0x18000604f  cmp     eax, 3
0x180006052  jz      short loc_18000605E
0x180006054  mov     edx, esi; int
0x180006056  mov     rcx, rbx; this
0x180006059  call    ?CompleteApplicationWriteRequest@WEBSOCKET_CONTEXT@@AEAAJJ@Z; WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest(long)
0x18000605e  mov     rcx, [rbx+1B0h]
0x180006065  test    rcx, rcx
0x180006068  jz      short loc_180006075
0x18000606a  mov     edx, [rdi]
0x18000606c  mov     r8, rbx
0x18000606f  call    cs:__imp_WriteRefTraceLog
0x180006075  or      eax, 0FFFFFFFFh
0x180006078  lock xadd [rdi], eax
0x18000607c  cmp     eax, 1
0x18000607f  jnz     short loc_1800060A1
0x180006081  mov     eax, [rbx+160h]
0x180006087  cmp     eax, 3
0x18000608a  jnz     short loc_1800060A1
0x18000608c  mov     rcx, [rbx+158h]
0x180006093  xor     edx, edx
0x180006095  mov     rax, [rcx]
0x180006098  mov     rax, [rax+40h]
0x18000609c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a1  mov     rbx, [rsp+28h+arg_0]
0x1800060a6  mov     rsi, [rsp+28h+arg_8]
0x1800060ab  add     rsp, 20h
0x1800060af  pop     rdi
0x1800060b0  retn
```
