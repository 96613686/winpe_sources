# WEBSOCKET_CONTEXT::ProcessReceivedMessage(_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE,int *)

- ea: `0x180006284`
- end: `0x1800063c3`
- name: `?ProcessReceivedMessage@WEBSOCKET_CONTEXT@@AEAAJPEAT_WEB_SOCKET_BUFFER@@W4_WEB_SOCKET_BUFFER_TYPE@@PEAH@Z`
- size: `319`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180005d88`
- `0x1800066b4`

## callees

- `0x18000282c`
- `0x1800041dc`
- `0x180006284`
- `0x180009010`

## import_xrefs

- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x180006387`
- `iisutil!?CopyA@STRU@@QEAAJPEBDK@Z` at `0x180006387`
- `iisutil!PuDbgPrint` at `0x1800062d0`
- `iisutil!PuDbgPrint` at `0x1800062d0`

## string_xrefs

- `0x1800062c9`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::ProcessReceivedMessage(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  int v8; // esi
  __int64 v9; // rax
  TRACE_HELPER *v10; // rcx

  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1686,
      "WEBSOCKET_CONTEXT::ProcessReceivedMessage",
      "Type = %08x\n",
      a3);
  if ( a3 < -2147483642 )
  {
    if ( a3 == -2147483643 )
    {
      v8 = 0;
      *(_DWORD *)(a1 + 364) = 0;
    }
    else
    {
      v8 = RECEIVE_QUEUE::PostData(*(_QWORD *)(a1 + 272), (unsigned int)a3, a2, a4);
      if ( v8 >= 0 && a3 == -2147483644 )
      {
        *(_DWORD *)(a1 + 356) = 1;
        if ( *(_DWORD *)(a1 + 360) )
        {
          v9 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 344) + 32LL))(*(_QWORD *)(a1 + 344));
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 96LL))(v9);
        }
        _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 368), 0, 1);
        *(_WORD *)(a1 + 280) = *(_WORD *)(a2 + 12);
        v8 = STRU::CopyA((STRU *)(a1 + 288), *(const char **)a2, *(_DWORD *)(a2 + 8));
        if ( v8 >= 0 )
          TRACE_HELPER::RaiseTraceEventOnClose(
            v10,
            *(struct IHttpContext **)(a1 + 344),
            0x30u,
            *(unsigned __int16 *)(a2 + 12),
            *(const unsigned __int16 **)(a1 + 320));
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180006284  push    rbx
0x180006286  push    rbp
0x180006287  push    rsi
0x180006288  push    rdi
0x180006289  push    r14
0x18000628b  sub     rsp, 30h
0x18000628f  test    byte ptr cs:g_dwDebugFlags, 3
0x180006296  mov     rdi, r9
0x180006299  mov     ebp, r8d
0x18000629c  mov     r14, rdx
0x18000629f  mov     rbx, rcx
0x1800062a2  jz      short loc_1800062D6
0x1800062a4  mov     rcx, cs:g_pDebug
0x1800062ab  lea     rax, aType08x; "Type = %08x\n"
0x1800062b2  mov     [rsp+58h+var_30], r8d
0x1800062b7  lea     r9, aWebsocketConte_5; "WEBSOCKET_CONTEXT::ProcessReceivedMessa"...
0x1800062be  mov     r8d, 696h
0x1800062c4  mov     [rsp+58h+var_38], rax
0x1800062c9  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800062d0  call    cs:__imp_PuDbgPrint
0x1800062d6  cmp     ebp, 80000006h
0x1800062dc  jl      short loc_1800062E8
0x1800062de  mov     esi, 80070057h
0x1800062e3  jmp     loc_1800063B6
0x1800062e8  cmp     ebp, 80000005h
0x1800062ee  jnz     short loc_1800062FF
0x1800062f0  xor     edi, edi
0x1800062f2  mov     esi, edi
0x1800062f4  mov     [rbx+16Ch], edi
0x1800062fa  jmp     loc_1800063B6
0x1800062ff  mov     rcx, [rbx+110h]
0x180006306  mov     r9, rdi
0x180006309  mov     r8, r14
0x18000630c  mov     edx, ebp
0x18000630e  call    ?PostData@RECEIVE_QUEUE@@QEAAJW4_WEB_SOCKET_BUFFER_TYPE@@PEAT_WEB_SOCKET_BUFFER@@PEAH@Z; RECEIVE_QUEUE::PostData(_WEB_SOCKET_BUFFER_TYPE,_WEB_SOCKET_BUFFER *,int *)
0x180006313  xor     edi, edi
0x180006315  mov     esi, eax
0x180006317  test    eax, eax
0x180006319  js      loc_1800063B6
0x18000631f  cmp     ebp, 80000004h
0x180006325  jnz     loc_1800063B6
0x18000632b  lea     esi, [rdi+1]
0x18000632e  mov     [rbx+164h], esi
0x180006334  mov     eax, [rbx+168h]
0x18000633a  test    eax, eax
0x18000633c  jz      short loc_180006363
0x18000633e  mov     rcx, [rbx+158h]
0x180006345  mov     rax, [rcx]
0x180006348  mov     rax, [rax+20h]
0x18000634c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006351  mov     rdx, rax
0x180006354  mov     rcx, [rax]
0x180006357  mov     rax, [rcx+60h]
0x18000635b  mov     rcx, rdx
0x18000635e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006363  mov     eax, esi
0x180006365  lock cmpxchg [rbx+170h], edi
0x18000636d  movzx   eax, word ptr [r14+0Ch]
0x180006372  lea     rcx, [rbx+120h]
0x180006379  mov     [rbx+118h], ax
0x180006380  mov     r8d, [r14+8]
0x180006384  mov     rdx, [r14]
0x180006387  call    cs:__imp_?CopyA@STRU@@QEAAJPEBDK@Z; STRU::CopyA(char const *,ulong)
0x18000638d  mov     esi, eax
0x18000638f  test    eax, eax
0x180006391  js      short loc_1800063B6
0x180006393  mov     rax, [rbx+140h]
0x18000639a  mov     r8d, 30h ; '0'; unsigned int
0x1800063a0  movzx   r9d, word ptr [r14+0Ch]; unsigned int
0x1800063a5  mov     rdx, [rbx+158h]; struct IHttpContext *
0x1800063ac  mov     [rsp+58h+var_38], rax; unsigned __int16 *
0x1800063b1  call    ?RaiseTraceEventOnClose@TRACE_HELPER@@QEAAXPEAVIHttpContext@@KKPEBG@Z; TRACE_HELPER::RaiseTraceEventOnClose(IHttpContext *,ulong,ulong,ushort const *)
0x1800063b6  mov     eax, esi
0x1800063b8  add     rsp, 30h
0x1800063bc  pop     r14
0x1800063be  pop     rdi
0x1800063bf  pop     rsi
0x1800063c0  pop     rbp
0x1800063c1  pop     rbx
0x1800063c2  retn
```
