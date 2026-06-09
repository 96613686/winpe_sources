# WEBSOCKET_CONTEXT::TryStartReadLoop(void)

- ea: `0x180007318`
- end: `0x18000740e`
- name: `?TryStartReadLoop@WEBSOCKET_CONTEXT@@AEAAJXZ`
- size: `246`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800063d0`
- `0x180007420`

## callees

- `0x1800066b4`
- `0x180007318`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x1800073a4`
- `iisutil!PuDbgPrint` at `0x1800073a4`

## string_xrefs

- `0x18000739d`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180007384`: `Starting Read Loop\n`
- `0x18000738b`: `WEBSOCKET_CONTEXT::TryStartReadLoop`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::TryStartReadLoop(WEBSOCKET_CONTEXT *this)
{
  __int64 v1; // rdx
  int v2; // edi
  int v4; // esi
  _OWORD v6[3]; // [rsp+30h] [rbp-38h] BYREF
  int v7; // [rsp+70h] [rbp+8h] BYREF
  int v8; // [rsp+78h] [rbp+10h] BYREF
  int v9; // [rsp+80h] [rbp+18h] BYREF

  v1 = *((_QWORD *)this + 34);
  v2 = 0;
  v9 = 0;
  v6[0] = 0;
  v8 = 0;
  v7 = 0;
  if ( *(_DWORD *)(v1 + 76) >= *(_DWORD *)(v1 + 8) || *((_DWORD *)this + 89) )
    return 0;
  v4 = 0;
  if ( !_InterlockedCompareExchange((volatile signed __int32 *)this + 92, 1, 0) )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
        1458,
        "WEBSOCKET_CONTEXT::TryStartReadLoop",
        "Starting Read Loop\n");
    do
    {
      if ( *((_DWORD *)this + 89) )
        break;
      v4 = WEBSOCKET_CONTEXT::ReadMessage(
             this,
             (union _WEB_SOCKET_BUFFER *)v6,
             (enum _WEB_SOCKET_BUFFER_TYPE *)&v9,
             (void (__high *)(void *, int, union _WEB_SOCKET_BUFFER *, enum _WEB_SOCKET_BUFFER_TYPE))&v8,
             &v7);
      if ( v4 < 0 || v7 )
        return (unsigned int)v4;
      v2 = v8;
    }
    while ( !v8 );
    if ( v2 )
      _InterlockedCompareExchange((volatile signed __int32 *)this + 92, 0, 1);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007318  mov     rax, rsp
0x18000731b  push    rbx
0x18000731c  push    rsi
0x18000731d  push    rdi
0x18000731e  push    r14
0x180007320  sub     rsp, 48h
0x180007324  mov     rdx, [rcx+110h]
0x18000732b  xor     edi, edi
0x18000732d  xorps   xmm0, xmm0
0x180007330  mov     dword ptr [rax+18h], 0
0x180007337  movdqu  xmmword ptr [rax-38h], xmm0
0x18000733c  mov     [rax+10h], edi
0x18000733f  mov     rbx, rcx
0x180007342  mov     [rax+8], edi
0x180007345  mov     eax, [rdx+8]
0x180007348  cmp     [rdx+4Ch], eax
0x18000734b  jnb     loc_180007402
0x180007351  mov     eax, [rcx+164h]
0x180007357  test    eax, eax
0x180007359  jnz     loc_180007402
0x18000735f  xor     esi, esi
0x180007361  lea     r14d, [rdi+1]
0x180007365  lock cmpxchg [rcx+170h], r14d
0x18000736e  jnz     loc_1800073FE
0x180007374  test    byte ptr cs:g_dwDebugFlags, 3
0x18000737b  jz      short loc_1800073AA
0x18000737d  mov     rcx, cs:g_pDebug
0x180007384  lea     rax, aStartingReadLo; "Starting Read Loop\n"
0x18000738b  lea     r9, aWebsocketConte_8; "WEBSOCKET_CONTEXT::TryStartReadLoop"
0x180007392  mov     [rsp+68h+var_48], rax
0x180007397  mov     r8d, 5B2h
0x18000739d  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x1800073a4  call    cs:__imp_PuDbgPrint
0x1800073aa  mov     eax, [rbx+164h]
0x1800073b0  test    eax, eax
0x1800073b2  jnz     short loc_1800073ED
0x1800073b4  lea     rax, [rsp+68h+arg_0]
0x1800073b9  mov     rcx, rbx; this
0x1800073bc  lea     r9, [rsp+68h+arg_8]; int *
0x1800073c1  mov     [rsp+68h+var_48], rax; int *
0x1800073c6  lea     r8, [rsp+68h+arg_10]; enum _WEB_SOCKET_BUFFER_TYPE *
0x1800073ce  lea     rdx, [rsp+68h+var_38]; union _WEB_SOCKET_BUFFER *
0x1800073d3  call    ?ReadMessage@WEBSOCKET_CONTEXT@@AEAAJPEAT_WEB_SOCKET_BUFFER@@PEAW4_WEB_SOCKET_BUFFER_TYPE@@PEAH2@Z; WEBSOCKET_CONTEXT::ReadMessage(_WEB_SOCKET_BUFFER *,_WEB_SOCKET_BUFFER_TYPE *,int *,int *)
0x1800073d8  mov     esi, eax
0x1800073da  test    eax, eax
0x1800073dc  js      short loc_1800073FE
0x1800073de  cmp     [rsp+68h+arg_0], 0
0x1800073e3  jnz     short loc_1800073FE
0x1800073e5  mov     edi, [rsp+68h+arg_8]
0x1800073e9  test    edi, edi
0x1800073eb  jz      short loc_1800073AA
0x1800073ed  test    edi, edi
0x1800073ef  jz      short loc_1800073FE
0x1800073f1  xor     ecx, ecx
0x1800073f3  mov     eax, r14d
0x1800073f6  lock cmpxchg [rbx+170h], ecx
0x1800073fe  mov     eax, esi
0x180007400  jmp     short loc_180007404
0x180007402  xor     eax, eax
0x180007404  add     rsp, 48h
0x180007408  pop     r14
0x18000740a  pop     rdi
0x18000740b  pop     rsi
0x18000740c  pop     rbx
0x18000740d  retn
```
