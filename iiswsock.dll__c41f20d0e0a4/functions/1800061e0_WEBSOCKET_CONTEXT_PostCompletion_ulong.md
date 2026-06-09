# WEBSOCKET_CONTEXT::PostCompletion(ulong)

- ea: `0x1800061e0`
- end: `0x18000627e`
- name: `?PostCompletion@WEBSOCKET_CONTEXT@@AEAAJK@Z`
- size: `158`
- prototype: `__int64 __fastcall(WEBSOCKET_CONTEXT *__hidden this, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800063d0`
- `0x180007674`

## callees

- `0x180005970`
- `0x1800061e0`
- `0x180009010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180006267`
- `iisutil!PuDbgPrint` at `0x180006267`

## string_xrefs

- `0x18000624e`: `servercommon\inetsrv\iis\iisrearc\iis70\websockets\module\websocketcontext.cxx`
- `0x180006243`: `WEBSOCKET_CONTEXT::PostCompletion`

## pseudocode

```c
__int64 __fastcall WEBSOCKET_CONTEXT::PostCompletion(WEBSOCKET_CONTEXT *this, unsigned int a2)
{
  __int64 result; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // [rsp+40h] [rbp+8h] BYREF

  v7 = 0;
  result = HttpGetExtendedInterface<IHttpContext,IHttpContext3>(this, *((_QWORD *)this + 43), &v7);
  if ( (int)result >= 0 )
  {
    v5 = (*(__int64 (__fastcall **)(__int64, _QWORD, void (__fastcall *)(unsigned int, unsigned int, struct _OVERLAPPED *), WEBSOCKET_CONTEXT *))(*(_QWORD *)v7 + 344LL))(
           v7,
           a2,
           WEBSOCKET_CONTEXT::OnPostedCompletion,
           this);
    v6 = v5;
    if ( v5 >= 0 )
    {
      return 0;
    }
    else
    {
      if ( (g_dwDebugFlags & 0xF) != 0 )
        PuDbgPrint(
          g_pDebug,
          "servercommon\\inetsrv\\iis\\iisrearc\\iis70\\websockets\\module\\websocketcontext.cxx",
          1280,
          "WEBSOCKET_CONTEXT::PostCompletion",
          "ERROR = %08x\n",
          v5);
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800061e0  mov     [rsp+arg_8], rbx
0x1800061e5  push    rdi
0x1800061e6  sub     rsp, 30h
0x1800061ea  mov     edi, edx
0x1800061ec  mov     [rsp+38h+arg_0], 0
0x1800061f5  mov     rdx, [rcx+158h]
0x1800061fc  lea     r8, [rsp+38h+arg_0]
0x180006201  mov     rbx, rcx
0x180006204  call    ??$HttpGetExtendedInterface@VIHttpContext@@VIHttpContext3@@@@YAJPEAVIHttpServer@@PEAVIHttpContext@@PEAPEAVIHttpContext3@@@Z; HttpGetExtendedInterface<IHttpContext,IHttpContext3>(IHttpServer *,IHttpContext *,IHttpContext3 * *)
0x180006209  test    eax, eax
0x18000620b  js      short loc_180006273
0x18000620d  mov     rcx, [rsp+38h+arg_0]
0x180006212  lea     r8, ?OnPostedCompletion@WEBSOCKET_CONTEXT@@CAXKKPEAU_OVERLAPPED@@@Z; WEBSOCKET_CONTEXT::OnPostedCompletion(ulong,ulong,_OVERLAPPED *)
0x180006219  mov     r9, rbx
0x18000621c  mov     edx, edi
0x18000621e  mov     rax, [rcx]
0x180006221  mov     rax, [rax+158h]
0x180006228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000622d  mov     ebx, eax
0x18000622f  test    eax, eax
0x180006231  jns     short loc_180006271
0x180006233  test    byte ptr cs:g_dwDebugFlags, 0Fh
0x18000623a  jz      short loc_18000626D
0x18000623c  mov     rcx, cs:g_pDebug
0x180006243  lea     r9, aWebsocketConte_6; "WEBSOCKET_CONTEXT::PostCompletion"
0x18000624a  mov     [rsp+38h+var_10], eax
0x18000624e  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\i"...
0x180006255  lea     rax, aError08x; "ERROR = %08x\n"
0x18000625c  mov     r8d, 500h
0x180006262  mov     [rsp+38h+var_18], rax
0x180006267  call    cs:__imp_PuDbgPrint
0x18000626d  mov     eax, ebx
0x18000626f  jmp     short loc_180006273
0x180006271  xor     eax, eax
0x180006273  mov     rbx, [rsp+38h+arg_8]
0x180006278  add     rsp, 30h
0x18000627c  pop     rdi
0x18000627d  retn
```
