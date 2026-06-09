# s_SrvRpcCryptFinalizeKey

- ea: `0x180009190`
- end: `0x180009261`
- name: `s_SrvRpcCryptFinalizeKey`
- size: `209`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180009190`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800091a8`
- `RPCRT4!RpcImpersonateClient` at `0x1800091a8`
- `RPCRT4!RpcRevertToSelf` at `0x180009201`
- `RPCRT4!RpcRevertToSelf` at `0x180009201`

## string_xrefs

- `0x1800091df`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000923a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptFinalizeKey(void *a1, __int64 a2, __int64 a3, __int64 a4, unsigned int a5)
{
  RPC_STATUS v8; // eax
  int v9; // r8d
  unsigned int v10; // ebx

  v8 = RpcImpersonateClient(a1);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        v9,
        (unsigned int)"Status",
        v8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        50);
    return (unsigned int)-2146893792;
  }
  else
  {
    v10 = ((__int64 (__fastcall *)(__int64, __int64, __int64, _QWORD))off_180025050[0])(a2, a3, a4, a5);
    RpcRevertToSelf();
  }
  return v10;
}

```

## disassembly

```asm
0x180009190  mov     [rsp+arg_0], rbx
0x180009195  mov     [rsp+arg_8], rsi
0x18000919a  push    rdi
0x18000919b  sub     rsp, 50h
0x18000919f  mov     rbx, r9
0x1800091a2  mov     rdi, r8
0x1800091a5  mov     rsi, rdx
0x1800091a8  call    cs:__imp_RpcImpersonateClient
0x1800091ae  test    eax, eax
0x1800091b0  jnz     short loc_180009219
0x1800091b2  mov     r9d, [rsp+58h+arg_20]
0x1800091ba  mov     r8, rbx
0x1800091bd  mov     rdx, rdi
0x1800091c0  mov     rcx, rsi
0x1800091c3  mov     rax, cs:off_180025050
0x1800091ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091cf  mov     ebx, eax
0x1800091d1  mov     [rsp+58h+var_18], eax
0x1800091d5  jmp     short loc_180009201
0x1800091d7  mov     ebx, eax
0x1800091d9  mov     r9d, 342h
0x1800091df  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800091e6  lea     rdx, aNtstatus; "ntStatus"
0x1800091ed  mov     ecx, eax
0x1800091ef  call    DebugTraceError
0x1800091f4  mov     ecx, ebx
0x1800091f6  call    NormalizeNteStatus
0x1800091fb  mov     ebx, eax
0x1800091fd  mov     [rsp+58h+var_18], eax
0x180009201  call    cs:__imp_RpcRevertToSelf
0x180009207  mov     eax, ebx
0x180009209  mov     rbx, [rsp+58h+arg_0]
0x18000920e  mov     rsi, [rsp+58h+arg_8]
0x180009213  add     rsp, 50h
0x180009217  pop     rdi
0x180009218  retn
0x180009219  lea     rdx, WPP_GLOBAL_Control
0x180009220  mov     rcx, cs:WPP_GLOBAL_Control
0x180009227  cmp     rcx, rdx
0x18000922a  jz      short loc_18000925A
0x18000922c  test    byte ptr [rcx+1Ch], 1
0x180009230  jz      short loc_18000925A
0x180009232  mov     [rsp+58h+var_28], 332h
0x18000923a  lea     rdx, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009241  mov     [rsp+58h+var_30], rdx
0x180009246  mov     [rsp+58h+var_38], eax
0x18000924a  lea     r9, aStatus; "Status"
0x180009251  mov     rcx, [rcx+10h]
0x180009255  call    WPP_SF_sDsd
0x18000925a  mov     ebx, 80090020h
0x18000925f  jmp     short loc_180009207
```
