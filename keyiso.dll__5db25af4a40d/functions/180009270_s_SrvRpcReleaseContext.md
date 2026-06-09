# s_SrvRpcReleaseContext

- ea: `0x180009270`
- end: `0x180009308`
- name: `s_SrvRpcReleaseContext`
- size: `152`
- prototype: `__int64 __fastcall(void *, _QWORD *)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x1800048f0`
- `0x180009270`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180009282`
- `RPCRT4!RpcImpersonateClient` at `0x180009282`
- `RPCRT4!RpcRevertToSelf` at `0x1800092cc`
- `RPCRT4!RpcRevertToSelf` at `0x1800092cc`

## string_xrefs

- `0x1800092ae`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800092ec`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcReleaseContext(void *a1, _QWORD *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx

  if ( a2 )
  {
    v3 = RpcImpersonateClient(a1);
    v4 = v3;
    if ( v3 )
    {
      DebugTraceError(v3, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 272);
      return (unsigned int)-2146893792;
    }
    else
    {
      ((void (__fastcall *)(_QWORD))off_180025010)(*a2);
      *a2 = 0;
      RpcRevertToSelf();
    }
  }
  else
  {
    return (unsigned int)-2146893785;
  }
  return v4;
}

```

## disassembly

```asm
0x180009270  mov     [rsp+arg_0], rbx
0x180009275  push    rdi
0x180009276  sub     rsp, 20h
0x18000927a  mov     rdi, rdx
0x18000927d  test    rdx, rdx
0x180009280  jz      short loc_1800092DF
0x180009282  call    cs:__imp_RpcImpersonateClient
0x180009288  mov     ebx, eax
0x18000928a  test    eax, eax
0x18000928c  jnz     short loc_1800092E6
0x18000928e  mov     rcx, [rdi]
0x180009291  mov     rax, cs:off_180025010
0x180009298  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000929d  mov     qword ptr [rdi], 0
0x1800092a4  jmp     short loc_1800092CC
0x1800092a6  mov     ebx, eax
0x1800092a8  mov     r9d, 11Eh
0x1800092ae  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800092b5  lea     rdx, aNtstatus; "ntStatus"
0x1800092bc  mov     ecx, eax
0x1800092be  call    DebugTraceError
0x1800092c3  mov     ecx, ebx
0x1800092c5  call    NormalizeNteStatus
0x1800092ca  mov     ebx, eax
0x1800092cc  call    cs:__imp_RpcRevertToSelf
0x1800092d2  mov     eax, ebx
0x1800092d4  mov     rbx, [rsp+28h+arg_0]
0x1800092d9  add     rsp, 20h
0x1800092dd  pop     rdi
0x1800092de  retn
0x1800092df  mov     ebx, 80090027h
0x1800092e4  jmp     short loc_1800092D2
0x1800092e6  mov     r9d, 110h
0x1800092ec  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800092f3  lea     rdx, aStatus; "Status"
0x1800092fa  mov     ecx, eax
0x1800092fc  call    DebugTraceError
0x180009301  mov     ebx, 80090020h
0x180009306  jmp     short loc_1800092D2
```
