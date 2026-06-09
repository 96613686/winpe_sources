# WEBSOCKET_CONTEXT::ReadMessage(_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE *,int *,int *)

- ea: `0x1800066b4`
- end: `0x18000678a`
- name: `?ReadMessage@WEBSOCKET_CONTEXT@@AEAAJPEAT_WEB_SOCKET_BUFFER@@PEAW4_WEB_SOCKET_BUFFER_TYPE@@PEAH2@Z`
- size: `214`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *this, union _WEB_SOCKET_BUFFER *, enum _WEB_SOCKET_BUFFER_TYPE *, void (__high *)(void *, int, union _WEB_SOCKET_BUFFER *, enum _WEB_SOCKET_BUFFER_TYPE), int *)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180005d88`
- `0x180007318`

## callees

- `0x180004bac`
- `0x180006284`
- `0x1800066b4`
- `0x180009010`

## import_xrefs

- `iisutil!WriteRefTraceLog` at `0x1800066eb`
- `iisutil!WriteRefTraceLog` at `0x180006745`
- `iisutil!WriteRefTraceLog` at `0x1800066eb`
- `iisutil!WriteRefTraceLog` at `0x180006745`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::ReadMessage(
        WEBSOCKET_CONTEXT *this,
        union _WEB_SOCKET_BUFFER *a2,
        enum _WEB_SOCKET_BUFFER_TYPE *a3,
        void (__high *a4)(void *, int, union _WEB_SOCKET_BUFFER *, enum _WEB_SOCKET_BUFFER_TYPE),
        int *a5)
{
  signed __int32 v9; // edx
  __int64 v10; // rcx
  __int64 v11; // rdx
  int v12; // edi
  __int64 v13; // rcx

  v9 = _InterlockedExchangeAdd((volatile signed __int32 *)this + 95, 1u);
  v10 = *((_QWORD *)this + 54);
  v11 = (unsigned int)(v9 + 1);
  if ( v10 )
    WriteRefTraceLog(v10, v11, this);
  v12 = WEBSOCKET_WRAPPER::Receive((WEBSOCKET_CONTEXT *)((char *)this + 112), a2, a3, a4, this, a5);
  if ( v12 >= 0 )
  {
    if ( *a5 )
      return (unsigned int)v12;
    v12 = WEBSOCKET_CONTEXT::ProcessReceivedMessage((__int64)this, (__int64)a2, *(_DWORD *)a3, (__int64)a4);
  }
  v13 = *((_QWORD *)this + 54);
  if ( v13 )
    WriteRefTraceLog(v13, *((unsigned int *)this + 95), this);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 95, 0xFFFFFFFF) == 1 && *((_DWORD *)this + 88) == 3 )
    (*(void (__fastcall **)(_QWORD, _QWORD))(**((_QWORD **)this + 43) + 64LL))(*((_QWORD *)this + 43), 0);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800066b4  push    rbx
0x1800066b6  push    rbp
0x1800066b7  push    rsi
0x1800066b8  push    rdi
0x1800066b9  push    r14
0x1800066bb  push    r15
0x1800066bd  sub     rsp, 38h
0x1800066c1  mov     rbp, rdx
0x1800066c4  mov     r15, r9
0x1800066c7  mov     edx, 1
0x1800066cc  mov     r14, r8
0x1800066cf  mov     rbx, rcx
0x1800066d2  lock xadd [rcx+17Ch], edx
0x1800066da  mov     rcx, [rcx+1B0h]
0x1800066e1  inc     edx
0x1800066e3  test    rcx, rcx
0x1800066e6  jz      short loc_1800066F1
0x1800066e8  mov     r8, rbx
0x1800066eb  call    cs:__imp_WriteRefTraceLog
0x1800066f1  mov     rsi, [rsp+68h+arg_20]
0x1800066f9  lea     rcx, [rbx+70h]; this
0x1800066fd  mov     [rsp+68h+var_40], rsi; int *
0x180006702  mov     r8, r14; enum _WEB_SOCKET_BUFFER_TYPE *
0x180006705  mov     rdx, rbp; union _WEB_SOCKET_BUFFER *
0x180006708  mov     [rsp+68h+var_48], rbx; void *
0x18000670d  call    ?Receive@WEBSOCKET_WRAPPER@@QEAAJPEAT_WEB_SOCKET_BUFFER@@PEAW4_WEB_SOCKET_BUFFER_TYPE@@P6AXPEAXJ0W43@@Z2PEAH@Z; WEBSOCKET_WRAPPER::Receive(_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE *,void (*)(void *,long,_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE),void *,int *)
0x180006712  mov     edi, eax
0x180006714  test    eax, eax
0x180006716  js      short loc_180006730
0x180006718  cmp     dword ptr [rsi], 0
0x18000671b  jnz     short loc_18000677B
0x18000671d  mov     r8d, [r14]
0x180006720  mov     r9, r15
0x180006723  mov     rdx, rbp
0x180006726  mov     rcx, rbx
0x180006729  call    ?ProcessReceivedMessage@WEBSOCKET_CONTEXT@@AEAAJPEAT_WEB_SOCKET_BUFFER@@W4_WEB_SOCKET_BUFFER_TYPE@@PEAH@Z; WEBSOCKET_CONTEXT::ProcessReceivedMessage(_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE,int *)
0x18000672e  mov     edi, eax
0x180006730  mov     rcx, [rbx+1B0h]
0x180006737  test    rcx, rcx
0x18000673a  jz      short loc_18000674B
0x18000673c  mov     edx, [rbx+17Ch]
0x180006742  mov     r8, rbx
0x180006745  call    cs:__imp_WriteRefTraceLog
0x18000674b  or      eax, 0FFFFFFFFh
0x18000674e  lock xadd [rbx+17Ch], eax
0x180006756  cmp     eax, 1
0x180006759  jnz     short loc_18000677B
0x18000675b  mov     eax, [rbx+160h]
0x180006761  cmp     eax, 3
0x180006764  jnz     short loc_18000677B
0x180006766  mov     rcx, [rbx+158h]
0x18000676d  xor     edx, edx
0x18000676f  mov     rax, [rcx]
0x180006772  mov     rax, [rax+40h]
0x180006776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000677b  mov     eax, edi
0x18000677d  add     rsp, 38h
0x180006781  pop     r15
0x180006783  pop     r14
0x180006785  pop     rdi
0x180006786  pop     rsi
0x180006787  pop     rbp
0x180006788  pop     rbx
0x180006789  retn
```
