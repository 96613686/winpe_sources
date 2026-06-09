# s_SrvRpcCreateContext

- ea: `0x180007f40`
- end: `0x18000807c`
- name: `s_SrvRpcCreateContext`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180007f40`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180007f59`
- `RPCRT4!RpcImpersonateClient` at `0x180007f59`
- `RPCRT4!RpcRevertToSelf` at `0x180007fd3`
- `RPCRT4!RpcRevertToSelf` at `0x180007fd3`

## string_xrefs

- `0x180007f92`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007fb1`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000800c`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000805a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCreateContext(void *a1, _QWORD *a2)
{
  RPC_STATUS v4; // edx
  int v5; // eax
  unsigned int v6; // ebx

  if ( a2 )
  {
    v4 = RpcImpersonateClient(a1);
    if ( v4 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v4,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          (unsigned int)"Status",
          v4,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          224);
      return (unsigned int)-2146893792;
    }
    else
    {
      *a2 = 0;
      v5 = ((__int64 (__fastcall *)(void *, _QWORD *))off_180025008[0])(a1, a2);
      v6 = v5;
      if ( v5 < 0 )
        DebugTraceError(
          (unsigned int)v5,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          238);
      RpcRevertToSelf();
    }
  }
  else
  {
    v6 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        217);
  }
  return v6;
}

```

## disassembly

```asm
0x180007f40  mov     [rsp+arg_0], rbx
0x180007f45  push    rdi
0x180007f46  sub     rsp, 50h
0x180007f4a  mov     rbx, rdx
0x180007f4d  mov     rdi, rcx
0x180007f50  test    rdx, rdx
0x180007f53  jz      loc_180007FE6
0x180007f59  call    cs:__imp_RpcImpersonateClient
0x180007f5f  mov     edx, eax
0x180007f61  test    eax, eax
0x180007f63  jnz     loc_180008032
0x180007f69  mov     qword ptr [rbx], 0
0x180007f70  mov     rdx, rbx
0x180007f73  mov     rcx, rdi
0x180007f76  mov     rax, cs:off_180025008
0x180007f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f82  mov     ebx, eax
0x180007f84  mov     [rsp+58h+var_18], eax
0x180007f88  test    eax, eax
0x180007f8a  jns     short loc_180007FA7
0x180007f8c  mov     r9d, 0EEh
0x180007f92  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f99  lea     rdx, aStatus; "Status"
0x180007fa0  mov     ecx, eax
0x180007fa2  call    DebugTraceError
0x180007fa7  jmp     short loc_180007FD3
0x180007fa9  mov     ebx, eax
0x180007fab  mov     r9d, 0F4h
0x180007fb1  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007fb8  lea     rdx, aNtstatus; "ntStatus"
0x180007fbf  mov     ecx, eax
0x180007fc1  call    DebugTraceError
0x180007fc6  mov     ecx, ebx
0x180007fc8  call    NormalizeNteStatus
0x180007fcd  mov     ebx, eax
0x180007fcf  mov     [rsp+58h+var_18], eax
0x180007fd3  call    cs:__imp_RpcRevertToSelf
0x180007fd9  mov     eax, ebx
0x180007fdb  mov     rbx, [rsp+58h+arg_0]
0x180007fe0  add     rsp, 50h
0x180007fe4  pop     rdi
0x180007fe5  retn
0x180007fe6  mov     ebx, 80090027h
0x180007feb  lea     rax, WPP_GLOBAL_Control
0x180007ff2  mov     rcx, cs:WPP_GLOBAL_Control
0x180007ff9  cmp     rcx, rax
0x180007ffc  jz      short loc_180007FD9
0x180007ffe  test    byte ptr [rcx+1Ch], 1
0x180008002  jz      short loc_180007FD9
0x180008004  mov     [rsp+58h+var_28], 0D9h
0x18000800c  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008013  mov     [rsp+58h+var_30], r8
0x180008018  mov     [rsp+58h+var_38], 80090027h
0x180008020  lea     r9, aStatus; "Status"
0x180008027  mov     rcx, [rcx+10h]
0x18000802b  call    WPP_SF_sDsd
0x180008030  jmp     short loc_180007FD9
0x180008032  lea     rax, WPP_GLOBAL_Control
0x180008039  mov     rcx, cs:WPP_GLOBAL_Control
0x180008040  cmp     rcx, rax
0x180008043  jz      short loc_18000804B
0x180008045  test    byte ptr [rcx+1Ch], 1
0x180008049  jnz     short loc_180008052
0x18000804b  mov     ebx, 80090020h
0x180008050  jmp     short loc_180007FD9
0x180008052  mov     [rsp+58h+var_28], 0E0h
0x18000805a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180008061  mov     [rsp+58h+var_30], r8
0x180008066  mov     [rsp+58h+var_38], edx
0x18000806a  lea     r9, aStatus; "Status"
0x180008071  mov     rcx, [rcx+10h]
0x180008075  call    WPP_SF_sDsd
0x18000807a  jmp     short loc_18000804B
```
