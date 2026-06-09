# s_SrvRpcCryptFreeProvider

- ea: `0x180003270`
- end: `0x180003353`
- name: `s_SrvRpcCryptFreeProvider`
- size: `227`
- prototype: `__int64 __fastcall(void *, __int64, __int64)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003270`
- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180003280`
- `RPCRT4!RpcImpersonateClient` at `0x180003280`
- `RPCRT4!RpcRevertToSelf` at `0x1800032ed`
- `RPCRT4!RpcRevertToSelf` at `0x1800032ed`

## string_xrefs

- `0x1800032ac`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800032cb`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180003321`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptFreeProvider(void *a1, __int64 a2, __int64 a3)
{
  RPC_STATUS v5; // eax
  int v6; // eax
  unsigned int v7; // ebx

  v5 = RpcImpersonateClient(a1);
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)&WPP_GLOBAL_Control,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        v5,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        123);
    return 2148073504LL;
  }
  else
  {
    v6 = ((__int64 (__fastcall *)(__int64, __int64))off_180025060[0])(a2, a3);
    v7 = v6;
    if ( v6 < 0 )
      DebugTraceError(
        (unsigned int)v6,
        "Status",
        "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        1927);
    RpcRevertToSelf();
    return v7;
  }
}

```

## disassembly

```asm
0x180003270  mov     [rsp+arg_0], rbx
0x180003275  push    rdi
0x180003276  sub     rsp, 50h
0x18000327a  mov     rdi, r8
0x18000327d  mov     rbx, rdx
0x180003280  call    cs:__imp_RpcImpersonateClient
0x180003286  test    eax, eax
0x180003288  jnz     short loc_180003300
0x18000328a  mov     rdx, rdi
0x18000328d  mov     rcx, rbx
0x180003290  mov     rax, cs:off_180025060
0x180003297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000329c  mov     ebx, eax
0x18000329e  mov     [rsp+58h+var_18], eax
0x1800032a2  test    eax, eax
0x1800032a4  jns     short loc_1800032C1
0x1800032a6  mov     r9d, 787h
0x1800032ac  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800032b3  lea     rdx, aStatus; "Status"
0x1800032ba  mov     ecx, eax
0x1800032bc  call    DebugTraceError
0x1800032c1  jmp     short loc_1800032ED
0x1800032c3  mov     ebx, eax
0x1800032c5  mov     r9d, 78Dh
0x1800032cb  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800032d2  lea     rdx, aNtstatus; "ntStatus"
0x1800032d9  mov     ecx, eax
0x1800032db  call    DebugTraceError
0x1800032e0  mov     ecx, ebx
0x1800032e2  call    NormalizeNteStatus
0x1800032e7  mov     ebx, eax
0x1800032e9  mov     [rsp+58h+var_18], eax
0x1800032ed  call    cs:__imp_RpcRevertToSelf
0x1800032f3  mov     eax, ebx
0x1800032f5  mov     rbx, [rsp+58h+arg_0]
0x1800032fa  add     rsp, 50h
0x1800032fe  pop     rdi
0x1800032ff  retn
0x180003300  lea     rdx, WPP_GLOBAL_Control
0x180003307  mov     rcx, cs:WPP_GLOBAL_Control
0x18000330e  cmp     rcx, rdx
0x180003311  jz      short loc_180003341
0x180003313  test    byte ptr [rcx+1Ch], 1
0x180003317  jz      short loc_180003341
0x180003319  mov     [rsp+58h+var_28], 77Bh
0x180003321  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180003328  mov     [rsp+58h+var_30], r8
0x18000332d  mov     [rsp+58h+var_38], eax
0x180003331  lea     r9, aStatus; "Status"
0x180003338  mov     rcx, [rcx+10h]
0x18000333c  call    WPP_SF_sDsd
0x180003341  mov     ebx, 80090020h
0x180003346  mov     eax, ebx
0x180003348  mov     rbx, [rsp+58h+arg_0]
0x18000334d  add     rsp, 50h
0x180003351  pop     rdi
0x180003352  retn
```
