# WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest(long)

- ea: `0x180005cb8`
- end: `0x180005d7f`
- name: `?CompleteApplicationWriteRequest@WEBSOCKET_CONTEXT@@AEAAJJ@Z`
- size: `199`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *__hidden this, int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005ed0`
- `0x180005fd0`
- `0x1800060c0`

## callees

- `0x180005cb8`
- `0x180009010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180005cf7`
- `iisutil!PuDbgPrint` at `0x180005d6c`
- `iisutil!PuDbgPrint` at `0x180005cf7`
- `iisutil!PuDbgPrint` at `0x180005d6c`

## string_xrefs

- `0x180005cf0`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180005d65`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180005cd7`: `Completing App Write Request\n`
- `0x180005cde`: `WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest`
- `0x180005d53`: `WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest`
- `0x180005d4c`: `Completed App Write Request\n`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest(WEBSOCKET_CONTEXT *this, int a2)
{
  void (__fastcall *v4)(_QWORD, __int64, __int64, _QWORD, _DWORD, _DWORD); // r10
  __int64 v5; // rdx
  unsigned int v6; // r9d
  __int64 v7; // r8

  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1055,
      "WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest",
      "Completing App Write Request\n");
  v4 = (void (__fastcall *)(_QWORD, __int64, __int64, _QWORD, _DWORD, _DWORD))*((_QWORD *)this + 9);
  v5 = *((_QWORD *)this + 10);
  v6 = *((_DWORD *)this + 24);
  *(_OWORD *)((char *)this + 72) = 0;
  *(_OWORD *)((char *)this + 88) = 0;
  _InterlockedCompareExchange((volatile signed __int32 *)this + 27, 0, 1);
  v7 = 0;
  if ( a2 >= 0 )
    v7 = v6;
  v4((unsigned int)a2, v5, v7, 0, 0, 0);
  if ( (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
      1098,
      "WEBSOCKET_CONTEXT::CompleteApplicationWriteRequest",
      "Completed App Write Request\n");
  return 0;
}

```

## disassembly

```asm
0x180005cb8  mov     [rsp+arg_0], rbx
0x180005cbd  push    rdi
0x180005cbe  sub     rsp, 40h
0x180005cc2  test    byte ptr cs:g_dwDebugFlags, 3
0x180005cc9  mov     edi, edx
0x180005ccb  mov     rbx, rcx
0x180005cce  jz      short loc_180005CFD
0x180005cd0  mov     rcx, cs:g_pDebug
0x180005cd7  lea     rax, aCompletingAppW; "Completing App Write Request\n"
0x180005cde  lea     r9, aWebsocketConte_2; "WEBSOCKET_CONTEXT::CompleteApplicationW"...
0x180005ce5  mov     [rsp+48h+var_28], rax
0x180005cea  mov     r8d, 41Fh
0x180005cf0  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005cf7  call    cs:__imp_PuDbgPrint
0x180005cfd  mov     r10, [rbx+48h]
0x180005d01  xorps   xmm0, xmm0
0x180005d04  mov     rdx, [rbx+50h]
0x180005d08  xor     ecx, ecx
0x180005d0a  mov     r9d, [rbx+60h]
0x180005d0e  movups  xmmword ptr [rbx+48h], xmm0
0x180005d12  lea     eax, [rcx+1]
0x180005d15  movups  xmmword ptr [rbx+58h], xmm0
0x180005d19  lock cmpxchg [rbx+6Ch], ecx
0x180005d1e  xor     r8d, r8d
0x180005d21  mov     [rsp+48h+var_20], ecx
0x180005d25  mov     dword ptr [rsp+48h+var_28], ecx
0x180005d29  test    edi, edi
0x180005d2b  mov     ecx, edi
0x180005d2d  mov     rax, r10
0x180005d30  cmovns  r8d, r9d
0x180005d34  xor     r9d, r9d
0x180005d37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3c  test    byte ptr cs:g_dwDebugFlags, 3
0x180005d43  jz      short loc_180005D72
0x180005d45  mov     rcx, cs:g_pDebug
0x180005d4c  lea     rax, aCompletedAppWr; "Completed App Write Request\n"
0x180005d53  lea     r9, aWebsocketConte_2; "WEBSOCKET_CONTEXT::CompleteApplicationW"...
0x180005d5a  mov     [rsp+48h+var_28], rax
0x180005d5f  mov     r8d, 44Ah
0x180005d65  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180005d6c  call    cs:__imp_PuDbgPrint
0x180005d72  mov     rbx, [rsp+48h+arg_0]
0x180005d77  xor     eax, eax
0x180005d79  add     rsp, 40h
0x180005d7d  pop     rdi
0x180005d7e  retn
```
