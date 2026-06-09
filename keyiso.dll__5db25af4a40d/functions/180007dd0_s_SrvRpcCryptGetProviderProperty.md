# s_SrvRpcCryptGetProviderProperty

- ea: `0x180007dd0`
- end: `0x180007f38`
- name: `s_SrvRpcCryptGetProviderProperty`
- size: `360`
- prototype: `__int64 __fastcall(void *, __int64, __int64, __int64, __int64, int, _DWORD *, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180007dd0`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180007df4`
- `RPCRT4!RpcImpersonateClient` at `0x180007df4`
- `RPCRT4!RpcRevertToSelf` at `0x180007e8f`
- `RPCRT4!RpcRevertToSelf` at `0x180007e8f`

## string_xrefs

- `0x180007e4e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007e6d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007ec7`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007f0e`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptGetProviderProperty(
        void *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        _DWORD *a7,
        int a8)
{
  RPC_STATUS v11; // edx
  int v12; // eax
  unsigned int v13; // ebx

  if ( a7 )
  {
    v11 = RpcImpersonateClient(a1);
    if ( v11 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v11,
          (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          (unsigned int)"Status",
          v11,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          19);
      return (unsigned int)-2146893792;
    }
    else
    {
      *a7 = 0;
      v12 = off_180025030(a2, a3, a4, a5, a6, (__int64)a7, a8);
      v13 = v12;
      if ( v12 < 0 )
        DebugTraceError(
          (unsigned int)v12,
          "Status",
          "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          550);
      RpcRevertToSelf();
    }
  }
  else
  {
    v13 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        12);
  }
  return v13;
}

```

## disassembly

```asm
0x180007dd0  push    rbx
0x180007dd2  push    rsi
0x180007dd3  push    rdi
0x180007dd4  push    r14
0x180007dd6  sub     rsp, 58h
0x180007dda  mov     rdi, r9
0x180007ddd  mov     rsi, r8
0x180007de0  mov     r14, rdx
0x180007de3  mov     rbx, [rsp+78h+arg_30]
0x180007deb  test    rbx, rbx
0x180007dee  jz      loc_180007EA1
0x180007df4  call    cs:__imp_RpcImpersonateClient
0x180007dfa  mov     edx, eax
0x180007dfc  test    eax, eax
0x180007dfe  jnz     loc_180007EED
0x180007e04  mov     [rbx], eax
0x180007e06  mov     eax, [rsp+78h+arg_38]
0x180007e0d  mov     [rsp+78h+var_48], eax
0x180007e11  mov     [rsp+78h+var_50], rbx
0x180007e16  mov     eax, [rsp+78h+arg_28]
0x180007e1d  mov     [rsp+78h+var_58], eax
0x180007e21  mov     r9, [rsp+78h+arg_20]
0x180007e29  mov     r8, rdi
0x180007e2c  mov     rdx, rsi
0x180007e2f  mov     rcx, r14
0x180007e32  mov     rax, cs:off_180025030
0x180007e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e3e  mov     ebx, eax
0x180007e40  mov     [rsp+78h+var_38], eax
0x180007e44  test    eax, eax
0x180007e46  jns     short loc_180007E63
0x180007e48  mov     r9d, 226h
0x180007e4e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007e55  lea     rdx, aStatus; "Status"
0x180007e5c  mov     ecx, eax
0x180007e5e  call    DebugTraceError
0x180007e63  jmp     short loc_180007E8F
0x180007e65  mov     ebx, eax
0x180007e67  mov     r9d, 22Ch
0x180007e6d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007e74  lea     rdx, aNtstatus; "ntStatus"
0x180007e7b  mov     ecx, eax
0x180007e7d  call    DebugTraceError
0x180007e82  mov     ecx, ebx
0x180007e84  call    NormalizeNteStatus
0x180007e89  mov     ebx, eax
0x180007e8b  mov     [rsp+78h+var_38], eax
0x180007e8f  call    cs:__imp_RpcRevertToSelf
0x180007e95  mov     eax, ebx
0x180007e97  add     rsp, 58h
0x180007e9b  pop     r14
0x180007e9d  pop     rdi
0x180007e9e  pop     rsi
0x180007e9f  pop     rbx
0x180007ea0  retn
0x180007ea1  mov     ebx, 80090027h
0x180007ea6  lea     rax, WPP_GLOBAL_Control
0x180007ead  mov     rcx, cs:WPP_GLOBAL_Control
0x180007eb4  cmp     rcx, rax
0x180007eb7  jz      short loc_180007E95
0x180007eb9  test    byte ptr [rcx+1Ch], 1
0x180007ebd  jz      short loc_180007E95
0x180007ebf  mov     [rsp+78h+var_48], 20Ch
0x180007ec7  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007ece  mov     [rsp+78h+var_50], r8
0x180007ed3  mov     [rsp+78h+var_58], 80090027h
0x180007edb  lea     r9, aStatus; "Status"
0x180007ee2  mov     rcx, [rcx+10h]
0x180007ee6  call    WPP_SF_sDsd
0x180007eeb  jmp     short loc_180007E95
0x180007eed  lea     rax, WPP_GLOBAL_Control
0x180007ef4  mov     rcx, cs:WPP_GLOBAL_Control
0x180007efb  cmp     rcx, rax
0x180007efe  jz      short loc_180007F2E
0x180007f00  test    byte ptr [rcx+1Ch], 1
0x180007f04  jz      short loc_180007F2E
0x180007f06  mov     [rsp+78h+var_48], 213h
0x180007f0e  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007f15  mov     [rsp+78h+var_50], r8
0x180007f1a  mov     [rsp+78h+var_58], edx
0x180007f1e  lea     r9, aStatus; "Status"
0x180007f25  mov     rcx, [rcx+10h]
0x180007f29  call    WPP_SF_sDsd
0x180007f2e  mov     ebx, 80090020h
0x180007f33  jmp     loc_180007E95
```
