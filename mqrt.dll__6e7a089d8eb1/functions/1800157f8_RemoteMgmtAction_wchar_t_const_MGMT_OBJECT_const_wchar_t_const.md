# RemoteMgmtAction(wchar_t const *,_MGMT_OBJECT const *,wchar_t const *)

- ea: `0x1800157f8`
- end: `0x180015933`
- name: `?RemoteMgmtAction@@YAJPEB_WPEBU_MGMT_OBJECT@@0@Z`
- size: `315`
- prototype: `__int64 __fastcall(const wchar_t *, const struct _MGMT_OBJECT *, const wchar_t *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task`

## callers

- `0x180015a80`

## callees

- `0x180013c74`
- `0x18001551c`
- `0x180015738`
- `0x1800157f8`

## import_xrefs

- `mqsec!MQSec_RpcAuthnLevel` at `0x18001581b`
- `mqsec!MQSec_RpcAuthnLevel` at `0x18001581b`
- `mqsec!mqrpcBindQMService` at `0x180015852`
- `mqsec!mqrpcBindQMService` at `0x180015852`
- `mqsec!g_CancelRpc` at `0x1800158c2`
- `mqsec!ProduceRPCErrorTracing` at `0x180015896`
- `mqsec!ProduceRPCErrorTracing` at `0x180015896`
- `mqsec!mqrpcUnbindQMService` at `0x1800158df`
- `mqsec!mqrpcUnbindQMService` at `0x1800158df`
- `mqsec!?Remove@CCancelRpc@@QEAAXPEAX@Z` at `0x1800158c9`
- `mqsec!?Remove@CCancelRpc@@QEAAXPEAX@Z` at `0x1800158c9`

## pseudocode

```c
__int64 __fastcall RemoteMgmtAction(const wchar_t *a1, const struct _MGMT_OBJECT *a2, const wchar_t *a3)
{
  unsigned int v6; // edx
  int v7; // ebx
  int v8; // edi
  void *v10; // [rsp+38h] [rbp-40h] BYREF
  void *v11; // [rsp+40h] [rbp-38h] BYREF
  unsigned int v12; // [rsp+98h] [rbp+20h] BYREF

  v12 = MQSec_RpcAuthnLevel();
  do
  {
    v10 = 0;
    v7 = mqrpcBindQMService(a1, 0x65u, qword_180029D30, &v12, &v10);
    if ( !v7 )
    {
      v11 = 0;
      RegisterRpcCallForCancel(&v11, v6);
      v7 = RTpMgmtAction(v10, a2, a3);
      CCancelRpc::Remove(g_CancelRpc, v11);
    }
    v8 = 0;
    if ( v10 )
      mqrpcUnbindQMService(&v10, 0);
    if ( v7 == -1072824309 && v12 != 1 )
    {
      v12 = 1;
      v8 = 1;
    }
  }
  while ( v8 );
  if ( v7 < 0 )
    LogMsgHR(v7, (wchar_t *)L"rt/rtmgmt", 0x50u);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800157f8  mov     [rsp+arg_10], r8
0x1800157fd  mov     [rsp+arg_8], rdx
0x180015802  mov     [rsp+arg_0], rcx
0x180015807  push    rbx
0x180015808  push    rsi
0x180015809  push    rdi
0x18001580a  push    r14
0x18001580c  push    r15
0x18001580e  sub     rsp, 50h
0x180015812  mov     rsi, r8
0x180015815  mov     r14, rdx
0x180015818  mov     r15, rcx
0x18001581b  call    cs:__imp_?MQSec_RpcAuthnLevel@@YAKXZ; MQSec_RpcAuthnLevel(void)
0x180015821  mov     [rsp+78h+arg_18], eax
0x180015828  mov     [rsp+78h+var_40], 0
0x180015831  lea     rax, [rsp+78h+var_40]
0x180015836  mov     [rsp+78h+var_58], rax
0x18001583b  lea     r9, [rsp+78h+arg_18]
0x180015843  lea     r8, qword_180029D30
0x18001584a  mov     edx, 65h ; 'e'
0x18001584f  mov     rcx, r15
0x180015852  call    cs:__imp_?mqrpcBindQMService@@YAJPEB_WKPEAXPEAKPEAPEAX@Z; mqrpcBindQMService(wchar_t const *,ulong,void *,ulong *,void * *)
0x180015858  mov     ebx, eax
0x18001585a  test    eax, eax
0x18001585c  jnz     short loc_1800158CF
0x18001585e  mov     [rsp+78h+var_38], 0
0x180015867  lea     rcx, [rsp+78h+var_38]; void **
0x18001586c  call    ?RegisterRpcCallForCancel@@YAXPEAPEAXK@Z; RegisterRpcCallForCancel(void * *,ulong)
0x180015871  nop
0x180015872  mov     r8, rsi
0x180015875  mov     rdx, r14
0x180015878  mov     rcx, [rsp+78h+var_40]
0x18001587d  call    RTpMgmtAction
0x180015882  mov     ebx, eax
0x180015884  mov     [rsp+78h+var_48], eax
0x180015888  jmp     short loc_1800158BD
0x18001588a  mov     edx, 0CDh
0x18001588f  lea     rcx, aRtRtmgmt; "rt/rtmgmt"
0x180015896  call    cs:__imp_?ProduceRPCErrorTracing@@YAXPEA_WK@Z; ProduceRPCErrorTracing(wchar_t *,ulong)
0x18001589c  mov     ebx, 0C00E000Bh
0x1800158a1  mov     [rsp+78h+var_48], ebx
0x1800158a5  mov     rsi, [rsp+78h+arg_10]
0x1800158ad  mov     r14, [rsp+78h+arg_8]
0x1800158b5  mov     r15, [rsp+78h+arg_0]
0x1800158bd  mov     rdx, [rsp+78h+var_38]
0x1800158c2  mov     rcx, cs:__imp_?g_CancelRpc@@3VCCancelRpc@@A; CCancelRpc g_CancelRpc
0x1800158c9  call    cs:__imp_?Remove@CCancelRpc@@QEAAXPEAX@Z; CCancelRpc::Remove(void *)
0x1800158cf  xor     edi, edi
0x1800158d1  cmp     [rsp+78h+var_40], rdi
0x1800158d6  jz      short loc_1800158E5
0x1800158d8  xor     edx, edx
0x1800158da  lea     rcx, [rsp+78h+var_40]
0x1800158df  call    cs:__imp_?mqrpcUnbindQMService@@YAJPEAPEAXPEAPEA_W@Z; mqrpcUnbindQMService(void * *,wchar_t * *)
0x1800158e5  cmp     ebx, 0C00E000Bh
0x1800158eb  jnz     short loc_180015907
0x1800158ed  cmp     [rsp+78h+arg_18], 1
0x1800158f5  jz      short loc_180015907
0x1800158f7  mov     [rsp+78h+arg_18], 1
0x180015902  mov     edi, 1
0x180015907  test    edi, edi
0x180015909  jnz     loc_180015828
0x18001590f  test    ebx, ebx
0x180015911  jns     short loc_180015925
0x180015913  lea     r8d, [rdi+50h]; unsigned __int16
0x180015917  lea     rdx, aRtRtmgmt; "rt/rtmgmt"
0x18001591e  mov     ecx, ebx; int
0x180015920  call    ?LogMsgHR@@YAXJPEA_WG@Z; LogMsgHR(long,wchar_t *,ushort)
0x180015925  mov     eax, ebx
0x180015927  add     rsp, 50h
0x18001592b  pop     r15
0x18001592d  pop     r14
0x18001592f  pop     rdi
0x180015930  pop     rsi
0x180015931  pop     rbx
0x180015932  retn
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
