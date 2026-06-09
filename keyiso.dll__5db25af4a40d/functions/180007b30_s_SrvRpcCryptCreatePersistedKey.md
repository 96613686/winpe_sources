# s_SrvRpcCryptCreatePersistedKey

- ea: `0x180007b30`
- end: `0x180007ca3`
- name: `s_SrvRpcCryptCreatePersistedKey`
- size: `371`
- prototype: `__int64 __fastcall(void *, __int64, __int64, _QWORD *, __int64, __int64, int, int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180007b30`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180007b51`
- `RPCRT4!RpcImpersonateClient` at `0x180007b51`
- `RPCRT4!RpcRevertToSelf` at `0x180007c1f`
- `RPCRT4!RpcRevertToSelf` at `0x180007c1f`

## string_xrefs

- `0x180007bd3`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007bfd`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007c5d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x180007c89`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptCreatePersistedKey(
        void *a1,
        __int64 a2,
        __int64 a3,
        _QWORD *a4,
        __int64 a5,
        __int64 a6,
        int a7,
        int a8)
{
  unsigned int v11; // eax
  int v12; // edx
  int v13; // ebx
  int v14; // r8d

  if ( a4 )
  {
    v11 = RpcImpersonateClient(a1);
    if ( v11 )
    {
      DebugTraceError(v11, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 472);
      return (unsigned int)-2146893792;
    }
    else
    {
      *a4 = -1;
      v13 = off_180025028(a2, a3, (int)a4, a5, a6, a7, a8);
      if ( v13 < 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v12,
          v14,
          (unsigned int)"Status",
          v13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
          235);
      }
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
        a3,
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        209);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x180007b30  mov     [rsp+arg_0], rbx
0x180007b35  mov     [rsp+arg_8], rsi
0x180007b3a  push    rdi
0x180007b3b  sub     rsp, 50h
0x180007b3f  mov     rbx, r9
0x180007b42  mov     rdi, r8
0x180007b45  mov     rsi, rdx
0x180007b48  test    r9, r9
0x180007b4b  jz      loc_180007C37
0x180007b51  call    cs:__imp_RpcImpersonateClient
0x180007b57  mov     ecx, eax
0x180007b59  test    eax, eax
0x180007b5b  jnz     loc_180007C83
0x180007b61  mov     qword ptr [rbx], 0FFFFFFFFFFFFFFFFh
0x180007b68  mov     eax, [rsp+58h+arg_38]
0x180007b6f  mov     [rsp+58h+var_28], eax
0x180007b73  mov     eax, [rsp+58h+arg_30]
0x180007b7a  mov     dword ptr [rsp+58h+var_30], eax
0x180007b7e  mov     rax, [rsp+58h+arg_28]
0x180007b86  mov     [rsp+58h+var_38], rax
0x180007b8b  mov     r9, [rsp+58h+arg_20]
0x180007b93  mov     r8, rbx
0x180007b96  mov     rdx, rdi
0x180007b99  mov     rcx, rsi
0x180007b9c  mov     rax, cs:off_180025028
0x180007ba3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ba8  mov     ebx, eax
0x180007baa  mov     [rsp+58h+var_18], eax
0x180007bae  test    eax, eax
0x180007bb0  jns     short loc_180007BF3
0x180007bb2  lea     rax, WPP_GLOBAL_Control
0x180007bb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180007bc0  cmp     rcx, rax
0x180007bc3  jz      short loc_180007BF3
0x180007bc5  test    byte ptr [rcx+1Ch], 1
0x180007bc9  jz      short loc_180007BF3
0x180007bcb  mov     [rsp+58h+var_28], 1EBh
0x180007bd3  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007bda  mov     [rsp+58h+var_30], rax
0x180007bdf  mov     dword ptr [rsp+58h+var_38], ebx
0x180007be3  lea     r9, aStatus; "Status"
0x180007bea  mov     rcx, [rcx+10h]
0x180007bee  call    WPP_SF_sDsd
0x180007bf3  jmp     short loc_180007C1F
0x180007bf5  mov     ebx, eax
0x180007bf7  mov     r9d, 1F1h
0x180007bfd  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007c04  lea     rdx, aNtstatus; "ntStatus"
0x180007c0b  mov     ecx, eax
0x180007c0d  call    DebugTraceError
0x180007c12  mov     ecx, ebx
0x180007c14  call    NormalizeNteStatus
0x180007c19  mov     ebx, eax
0x180007c1b  mov     [rsp+58h+var_18], eax
0x180007c1f  call    cs:__imp_RpcRevertToSelf
0x180007c25  mov     eax, ebx
0x180007c27  mov     rbx, [rsp+58h+arg_0]
0x180007c2c  mov     rsi, [rsp+58h+arg_8]
0x180007c31  add     rsp, 50h
0x180007c35  pop     rdi
0x180007c36  retn
0x180007c37  mov     ebx, 80090027h
0x180007c3c  lea     rax, WPP_GLOBAL_Control
0x180007c43  mov     rcx, cs:WPP_GLOBAL_Control
0x180007c4a  cmp     rcx, rax
0x180007c4d  jz      short loc_180007C25
0x180007c4f  test    byte ptr [rcx+1Ch], 1
0x180007c53  jz      short loc_180007C25
0x180007c55  mov     [rsp+58h+var_28], 1D1h
0x180007c5d  lea     rax, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007c64  mov     [rsp+58h+var_30], rax
0x180007c69  mov     dword ptr [rsp+58h+var_38], 80090027h
0x180007c71  lea     r9, aStatus; "Status"
0x180007c78  mov     rcx, [rcx+10h]
0x180007c7c  call    WPP_SF_sDsd
0x180007c81  jmp     short loc_180007C25
0x180007c83  mov     r9d, 1D8h
0x180007c89  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180007c90  lea     rdx, aStatus; "Status"
0x180007c97  call    DebugTraceError
0x180007c9c  mov     ebx, 80090020h
0x180007ca1  jmp     short loc_180007C25
```
