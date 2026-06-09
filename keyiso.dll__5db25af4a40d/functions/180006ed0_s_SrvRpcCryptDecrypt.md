# s_SrvRpcCryptDecrypt

- ea: `0x180006ed0`
- end: `0x180007082`
- name: `s_SrvRpcCryptDecrypt`
- size: `434`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, int, __int64, __int64, int, _DWORD *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180006ed0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180006f07`
- `RPCRT4!RpcImpersonateClient` at `0x180006f07`
- `RPCRT4!RpcRevertToSelf` at `0x180006fc9`
- `RPCRT4!RpcRevertToSelf` at `0x180006fc9`

## string_xrefs

- `0x180006f88`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180006fa7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007003`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007040`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007063`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptDecrypt(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        __int64 a7,
        __int64 a8,
        int a9,
        _DWORD *a10,
        int a11)
{
  RPC_STATUS v14; // eax
  __int64 v15; // rcx
  signed int v16; // eax
  unsigned int v17; // ebx

  if ( a10 )
  {
    if ( (a11 & 0x10) != 0 )
    {
      v17 = -2146893815;
      DebugTraceError(
        0x80090009,
        (int)"Status",
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        70);
    }
    else
    {
      v14 = RpcImpersonateClient(a1);
      if ( v14 )
      {
        DebugTraceError(
          v14,
          (int)"Status",
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          77);
        return (unsigned int)-2146893792;
      }
      else
      {
        *a10 = 0;
        v15 = 0;
        if ( a7 )
          v15 = *(_QWORD *)(a7 + 8);
        v16 = off_180025080(a2, a3, a4, a5, a6, v15, a8, a9, (__int64)a10, a11);
        v17 = v16;
        if ( v16 < 0 )
          DebugTraceError(
            v16,
            (int)"Status",
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
            99);
        RpcRevertToSelf();
      }
    }
    return v17;
  }
  v17 = -2146893785;
  if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    return v17;
  WPP_SF_sDsd(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    a2,
    (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
    (unsigned int)"Status",
    39,
    (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
    63);
  return 2148073511LL;
}

```

## disassembly

```asm
0x180006ed0  push    rbx
0x180006ed2  push    rsi
0x180006ed3  push    rdi
0x180006ed4  push    r14
0x180006ed6  push    r15
0x180006ed8  sub     rsp, 70h
0x180006edc  mov     rsi, r9
0x180006edf  mov     r14, r8
0x180006ee2  mov     r15, rdx
0x180006ee5  mov     rbx, [rsp+98h+arg_48]
0x180006eed  test    rbx, rbx
0x180006ef0  jz      loc_180006FDD
0x180006ef6  mov     edi, [rsp+98h+arg_50]
0x180006efd  test    dil, 10h
0x180006f01  jnz     loc_180007035
0x180006f07  call    cs:__imp_RpcImpersonateClient
0x180006f0d  test    eax, eax
0x180006f0f  jnz     loc_18000705D
0x180006f15  mov     [rbx], eax
0x180006f17  xor     ecx, ecx
0x180006f19  mov     rax, [rsp+98h+arg_30]
0x180006f21  test    rax, rax
0x180006f24  jz      short loc_180006F2A
0x180006f26  mov     rcx, [rax+8]
0x180006f2a  mov     [rsp+98h+var_50], edi
0x180006f2e  mov     [rsp+98h+var_58], rbx
0x180006f33  mov     eax, [rsp+98h+arg_40]
0x180006f3a  mov     [rsp+98h+var_60], eax
0x180006f3e  mov     rax, [rsp+98h+arg_38]
0x180006f46  mov     [rsp+98h+var_68], rax
0x180006f4b  mov     [rsp+98h+var_70], rcx
0x180006f50  mov     eax, [rsp+98h+arg_28]
0x180006f57  mov     [rsp+98h+var_78], eax
0x180006f5b  mov     r9, [rsp+98h+arg_20]
0x180006f63  mov     r8, rsi
0x180006f66  mov     rdx, r14
0x180006f69  mov     rcx, r15
0x180006f6c  mov     rax, cs:off_180025080
0x180006f73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f78  mov     ebx, eax
0x180006f7a  mov     [rsp+98h+var_38], eax
0x180006f7e  test    eax, eax
0x180006f80  jns     short loc_180006F9D
0x180006f82  mov     r9d, 463h
0x180006f88  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006f8f  lea     rdx, aStatus; "Status"
0x180006f96  mov     ecx, eax
0x180006f98  call    DebugTraceError
0x180006f9d  jmp     short loc_180006FC9
0x180006f9f  mov     ebx, eax
0x180006fa1  mov     r9d, 469h
0x180006fa7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180006fae  lea     rdx, aNtstatus; "ntStatus"
0x180006fb5  mov     ecx, eax
0x180006fb7  call    DebugTraceError
0x180006fbc  mov     ecx, ebx
0x180006fbe  call    NormalizeNteStatus
0x180006fc3  mov     ebx, eax
0x180006fc5  mov     [rsp+98h+var_38], eax
0x180006fc9  call    cs:__imp_RpcRevertToSelf
0x180006fcf  mov     eax, ebx
0x180006fd1  add     rsp, 70h
0x180006fd5  pop     r15
0x180006fd7  pop     r14
0x180006fd9  pop     rdi
0x180006fda  pop     rsi
0x180006fdb  pop     rbx
0x180006fdc  retn
0x180006fdd  mov     ebx, 80090027h
0x180006fe2  lea     rax, WPP_GLOBAL_Control
0x180006fe9  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ff0  cmp     rcx, rax
0x180006ff3  jz      short loc_180006FCF
0x180006ff5  test    byte ptr [rcx+1Ch], 1
0x180006ff9  jz      short loc_180006FCF
0x180006ffb  mov     dword ptr [rsp+98h+var_68], 43Fh
0x180007003  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000700a  mov     [rsp+98h+var_70], r8
0x18000700f  mov     [rsp+98h+var_78], 80090027h
0x180007017  lea     r9, aStatus; "Status"
0x18000701e  mov     rcx, [rcx+10h]
0x180007022  call    WPP_SF_sDsd
0x180007027  mov     eax, ebx
0x180007029  add     rsp, 70h
0x18000702d  pop     r15
0x18000702f  pop     r14
0x180007031  pop     rdi
0x180007032  pop     rsi
0x180007033  pop     rbx
0x180007034  retn
0x180007035  mov     ebx, 80090009h
0x18000703a  mov     r9d, 446h
0x180007040  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007047  lea     rdx, aStatus; "Status"
0x18000704e  mov     ecx, 80090009h
0x180007053  call    DebugTraceError
0x180007058  jmp     loc_180006FCF
0x18000705d  mov     r9d, 44Dh
0x180007063  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000706a  lea     rdx, aStatus; "Status"
0x180007071  mov     ecx, eax
0x180007073  call    DebugTraceError
0x180007078  mov     ebx, 80090020h
0x18000707d  jmp     loc_180006FCF
```
