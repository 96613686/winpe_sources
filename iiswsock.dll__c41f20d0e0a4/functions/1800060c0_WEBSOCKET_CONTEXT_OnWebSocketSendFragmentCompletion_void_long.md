# WEBSOCKET_CONTEXT::OnWebSocketSendFragmentCompletion(void *,long)

- ea: `0x1800060c0`
- end: `0x180006164`
- name: `?OnWebSocketSendFragmentCompletion@WEBSOCKET_CONTEXT@@CAXPEAXJ@Z`
- size: `164`
- prototype: `void __fastcall(WEBSOCKET_CONTEXT *this, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002168`
- `0x180002500`
- `0x180005cb8`
- `0x1800060c0`
- `0x180009010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x180006123`
- `iisutil!WriteRefTraceLog` at `0x180006123`

## pseudocode

```c
void __fastcall WEBSOCKET_CONTEXT::OnWebSocketSendFragmentCompletion(WEBSOCKET_CONTEXT *this, int a2)
{
  bool v3; // sf
  struct IHttpContext *v4; // rdx
  __int64 v6; // rcx

  v3 = a2 < 0;
  v4 = (struct IHttpContext *)*((_QWORD *)this + 43);
  if ( v3 )
    TRACE_HELPER::RaiseTraceEventError(this, v4, 0x23u, a2);
  else
    TRACE_HELPER::RaiseTraceEventGeneral(this, v4, 0x22u, *((_DWORD *)this + 24));
  if ( *((_DWORD *)this + 88) != 3 )
    WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest(this, a2);
  v6 = *((_QWORD *)this + 54);
  if ( v6 )
    WriteRefTraceLog(v6, *((unsigned int *)this + 95), this);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 95, 0xFFFFFFFF) == 1 && *((_DWORD *)this + 88) == 3 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 43) + 64LL))(*((_QWORD *)this + 43), 0);
}

```

## disassembly

```asm
0x1800060c0  mov     [rsp+arg_0], rbx
0x1800060c5  push    rdi
0x1800060c6  sub     rsp, 20h
0x1800060ca  mov     edi, edx
0x1800060cc  test    edx, edx
0x1800060ce  mov     rdx, [rcx+158h]; struct IHttpContext *
0x1800060d5  mov     rbx, rcx
0x1800060d8  jns     short loc_1800060EA
0x1800060da  mov     r9d, edi; int
0x1800060dd  mov     r8d, 23h ; '#'; unsigned int
0x1800060e3  call    ?RaiseTraceEventError@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KJ@Z; TRACE_HELPER::RaiseTraceEventError(IHttpContext *,ulong,long)
0x1800060e8  jmp     short loc_1800060F9
0x1800060ea  mov     r9d, [rcx+60h]; unsigned int
0x1800060ee  mov     r8d, 22h ; '"'; unsigned int
0x1800060f4  call    ?RaiseTraceEventGeneral@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KK@Z; TRACE_HELPER::RaiseTraceEventGeneral(IHttpContext *,ulong,ulong)
0x1800060f9  mov     eax, [rbx+160h]
0x1800060ff  cmp     eax, 3
0x180006102  jz      short loc_18000610E
0x180006104  mov     edx, edi; int
0x180006106  mov     rcx, rbx; this
0x180006109  call    ?CompleteApplicationWriteRequest@WEBSOCKET_CONTEXT@@AEAAJJ@Z; WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest(long)
0x18000610e  mov     rcx, [rbx+1B0h]
0x180006115  test    rcx, rcx
0x180006118  jz      short loc_180006129
0x18000611a  mov     edx, [rbx+17Ch]
0x180006120  mov     r8, rbx
0x180006123  call    cs:__imp_WriteRefTraceLog
0x180006129  or      eax, 0FFFFFFFFh
0x18000612c  lock xadd [rbx+17Ch], eax
0x180006134  cmp     eax, 1
0x180006137  jnz     short loc_180006159
0x180006139  mov     eax, [rbx+160h]
0x18000613f  cmp     eax, 3
0x180006142  jnz     short loc_180006159
0x180006144  mov     rcx, [rbx+158h]
0x18000614b  xor     edx, edx
0x18000614d  mov     rax, [rcx]
0x180006150  mov     rax, [rax+40h]
0x180006154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006159  mov     rbx, [rsp+28h+arg_0]
0x18000615e  add     rsp, 20h
0x180006162  pop     rdi
0x180006163  retn
```
