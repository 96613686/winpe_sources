# RemoteMgmtGetInfo

- ea: `0x18001593c`
- end: `0x180015a79`
- name: `RemoteMgmtGetInfo`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x180015c30`

## callees

- `0x180013c74`
- `0x1800155e0`
- `0x180015738`
- `0x18001593c`

## import_xrefs

- `mqsec!MQSec_RpcAuthnLevel` at `0x18001595f`
- `mqsec!MQSec_RpcAuthnLevel` at `0x18001595f`
- `mqsec!mqrpcBindQMService` at `0x180015996`
- `mqsec!mqrpcBindQMService` at `0x180015996`
- `mqsec!g_CancelRpc` at `0x180015a06`
- `mqsec!ProduceRPCErrorTracing` at `0x1800159da`
- `mqsec!ProduceRPCErrorTracing` at `0x1800159da`
- `mqsec!mqrpcUnbindQMService` at `0x180015a23`
- `mqsec!mqrpcUnbindQMService` at `0x180015a23`
- `mqsec!?Remove@CCancelRpc@@QEAAXPEAX@Z` at `0x180015a0d`
- `mqsec!?Remove@CCancelRpc@@QEAAXPEAX@Z` at `0x180015a0d`

## pseudocode

```c
__int64 __fastcall RemoteMgmtGetInfo(const wchar_t *a1, __int64 a2, __int64 a3)
{
  unsigned int v6; // edx
  int Info; // ebx
  int v8; // edi
  void *v10; // [rsp+38h] [rbp-40h] BYREF
  void *v11; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+98h] [rbp+20h] BYREF

  v12 = MQSec_RpcAuthnLevel();
  do
  {
    v10 = 0;
    Info = mqrpcBindQMService(a1, 0x65u, qword_180029D30, &v12, &v10);
    if ( !Info )
    {
      v11 = 0;
      RegisterRpcCallForCancel(&v11, v6);
      Info = RTpMgmtGetInfo(v10, a2, a3);
      CCancelRpc::Remove(g_CancelRpc, v11);
    }
    v8 = 0;
    if ( v10 )
      mqrpcUnbindQMService(&v10, 0);
    if ( Info == -1072824309 && v12 != 1 )
    {
      v12 = 1;
      v8 = 1;
    }
  }
  while ( v8 );
  if ( Info < 0 )
    LogMsgHR(Info, (wchar_t *)L"rt/rtmgmt", 0xAAu);
  return (unsigned int)Info;
}

```

## disassembly

```asm
0x18001593c  mov     [rsp+arg_10], r8
0x180015941  mov     [rsp+arg_8], rdx
0x180015946  mov     [rsp+arg_0], rcx
0x18001594b  push    rbx
0x18001594c  push    rsi
0x18001594d  push    rdi
0x18001594e  push    r14
0x180015950  push    r15
0x180015952  sub     rsp, 50h
0x180015956  mov     rsi, r8
0x180015959  mov     r14, rdx
0x18001595c  mov     r15, rcx
0x18001595f  call    cs:__imp_?MQSec_RpcAuthnLevel@@YAKXZ; MQSec_RpcAuthnLevel(void)
0x180015965  mov     [rsp+78h+arg_18], eax
0x18001596c  mov     [rsp+78h+var_40], 0
0x180015975  lea     rax, [rsp+78h+var_40]
0x18001597a  mov     [rsp+78h+var_58], rax
0x18001597f  lea     r9, [rsp+78h+arg_18]
0x180015987  lea     r8, qword_180029D30
0x18001598e  mov     edx, 65h ; 'e'
0x180015993  mov     rcx, r15
0x180015996  call    cs:__imp_?mqrpcBindQMService@@YAJPEB_WKPEAXPEAKPEAPEAX@Z; mqrpcBindQMService(wchar_t const *,ulong,void *,ulong *,void * *)
0x18001599c  mov     ebx, eax
0x18001599e  test    eax, eax
0x1800159a0  jnz     short loc_180015A13
0x1800159a2  mov     [rsp+78h+var_38], 0
0x1800159ab  lea     rcx, [rsp+78h+var_38]; void **
0x1800159b0  call    ?RegisterRpcCallForCancel@@YAXPEAPEAXK@Z; RegisterRpcCallForCancel(void * *,ulong)
0x1800159b5  nop
0x1800159b6  mov     r8, rsi
0x1800159b9  mov     rdx, r14
0x1800159bc  mov     rcx, [rsp+78h+var_40]
0x1800159c1  call    RTpMgmtGetInfo
0x1800159c6  mov     ebx, eax
0x1800159c8  mov     [rsp+78h+var_48], eax
0x1800159cc  jmp     short loc_180015A01
0x1800159ce  mov     edx, 160h
0x1800159d3  lea     rcx, aRtRtmgmt; "rt/rtmgmt"
0x1800159da  call    cs:__imp_?ProduceRPCErrorTracing@@YAXPEA_WK@Z; ProduceRPCErrorTracing(wchar_t *,ulong)
0x1800159e0  mov     ebx, 0C00E000Bh
0x1800159e5  mov     [rsp+78h+var_48], ebx
0x1800159e9  mov     rsi, [rsp+78h+arg_10]
0x1800159f1  mov     r14, [rsp+78h+arg_8]
0x1800159f9  mov     r15, [rsp+78h+arg_0]
0x180015a01  mov     rdx, [rsp+78h+var_38]
0x180015a06  mov     rcx, cs:__imp_?g_CancelRpc@@3VCCancelRpc@@A; CCancelRpc g_CancelRpc
0x180015a0d  call    cs:__imp_?Remove@CCancelRpc@@QEAAXPEAX@Z; CCancelRpc::Remove(void *)
0x180015a13  xor     edi, edi
0x180015a15  cmp     [rsp+78h+var_40], rdi
0x180015a1a  jz      short loc_180015A29
0x180015a1c  xor     edx, edx
0x180015a1e  lea     rcx, [rsp+78h+var_40]
0x180015a23  call    cs:__imp_?mqrpcUnbindQMService@@YAJPEAPEAXPEAPEA_W@Z; mqrpcUnbindQMService(void * *,wchar_t * *)
0x180015a29  cmp     ebx, 0C00E000Bh
0x180015a2f  jnz     short loc_180015A4B
0x180015a31  cmp     [rsp+78h+arg_18], 1
0x180015a39  jz      short loc_180015A4B
0x180015a3b  mov     [rsp+78h+arg_18], 1
0x180015a46  mov     edi, 1
0x180015a4b  test    edi, edi
0x180015a4d  jnz     loc_18001596C
0x180015a53  test    ebx, ebx
0x180015a55  jns     short loc_180015A6B
0x180015a57  mov     r8d, 0AAh; unsigned __int16
0x180015a5d  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x180015a64  mov     ecx, ebx; int
0x180015a66  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015a6b  mov     eax, ebx
0x180015a6d  add     rsp, 50h
0x180015a71  pop     r15
0x180015a73  pop     r14
0x180015a75  pop     rdi
0x180015a76  pop     rsi
0x180015a77  pop     rbx
0x180015a78  retn
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
