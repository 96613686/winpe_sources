# RtpQMGetMsmqServiceName(void *,wchar_t * *)

- ea: `0x1800144c8`
- end: `0x18001453f`
- name: `?RtpQMGetMsmqServiceName@@YAJPEAXPEAPEA_W@Z`
- size: `119`
- prototype: `__int64 __fastcall(void *, wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x180013af4`

## callees

- `0x180005488`
- `0x180013c74`
- `0x1800144c8`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800144eb`
- `RPCRT4!NdrClientCall3` at `0x1800144eb`
- `mqsec!ProduceRPCErrorTracing` at `0x180014518`
- `mqsec!ProduceRPCErrorTracing` at `0x180014518`

## pseudocode

```c
__int64 __fastcall RtpQMGetMsmqServiceName(void *a1, wchar_t **a2)
{
  int Pointer; // [rsp+50h] [rbp+18h]

  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x20u, 0, a1, a2).Pointer;
  return LogHR(Pointer, (wchar_t *)L"rt/rtmain", 0x44Du);
}

```

## disassembly

```asm
0x1800144c8  sub     rsp, 38h
0x1800144cc  mov     [rsp+38h+arg_10], 0
0x1800144d5  mov     [rsp+38h+var_18], rdx
0x1800144da  mov     r9, rcx
0x1800144dd  xor     r8d, r8d; pReturnValue
0x1800144e0  lea     edx, [r8+20h]; nProcNum
0x1800144e4  lea     rcx, pProxyInfo; pProxyInfo
0x1800144eb  call    cs:__imp_NdrClientCall3
0x1800144f1  mov     [rsp+38h+arg_10], rax
0x1800144f6  mov     r8d, 44Dh; unsigned __int16
0x1800144fc  lea     rdx, aRtRtmain; "rt/rtmain"
0x180014503  mov     ecx, eax; int
0x180014505  call    ?LogHR@@YAJJPEA_WG@Z; LogHR(long,wchar_t *,ushort)
0x18001450a  jmp     short loc_18001453A
0x18001450c  mov     edx, 0F2h
0x180014511  lea     rcx, aRtRtmain; "rt/rtmain"
0x180014518  call    cs:__imp_?ProduceRPCErrorTracing@@YAXPEA_WK@Z; ProduceRPCErrorTracing(wchar_t *,ulong)
0x18001451e  mov     r8d, 44Eh; unsigned __int16
0x180014524  lea     rdx, aRtRtmain; "rt/rtmain"
0x18001452b  mov     ecx, 0C00E000Bh; int
0x180014530  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180014535  mov     eax, 0C00E000Bh
0x18001453a  add     rsp, 38h
0x18001453e  retn
0x180024b25  push    rbp
0x180024b27  sub     rsp, 30h
0x180024b2b  mov     rbp, rdx
0x180024b2e  mov     rcx, [rcx]
0x180024b31  mov     ecx, [rcx]; ExceptionCode
0x180024b33  call    cs:__imp_I_RpcExceptionFilter
0x180024b39  nop
0x180024b3a  add     rsp, 30h
0x180024b3e  pop     rbp
0x180024b3f  retn
```
