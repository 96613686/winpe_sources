# s_SrvRpcCryptEnumAlgorithms

- ea: `0x180009410`
- end: `0x18000955c`
- name: `s_SrvRpcCryptEnumAlgorithms`
- size: `332`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003cf0`
- `0x180004470`
- `0x1800048f0`
- `0x180009410`
- `0x180019010`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180009447`
- `RPCRT4!RpcImpersonateClient` at `0x180009447`
- `RPCRT4!RpcRevertToSelf` at `0x1800094d0`
- `RPCRT4!RpcRevertToSelf` at `0x1800094d0`

## string_xrefs

- `0x18000948f`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x1800094ae`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000950a`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`
- `0x18000953d`: `onecore\ds\security\cryptoapi\ncrypt\iso\service\srvrpc.c`

## pseudocode

```c
__int64 __fastcall s_SrvRpcCryptEnumAlgorithms(
        void *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        _DWORD *a5,
        __int64 a6,
        int a7)
{
  unsigned int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx

  if ( a5 )
  {
    if ( a6 )
    {
      v10 = RpcImpersonateClient(a1);
      if ( v10 )
      {
        DebugTraceError(v10, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c", 1760);
        return (unsigned int)-2146893792;
      }
      else
      {
        *a5 = 0;
        v11 = off_180025090[0](a2, a3, a4, (int)a5, a6, a7);
        v12 = v11;
        if ( v11 < 0 )
          DebugTraceError(
            (unsigned int)v11,
            "Status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
            1778);
        RpcRevertToSelf();
      }
    }
    else
    {
      return (unsigned int)-2146893785;
    }
  }
  else
  {
    v12 = -2146893785;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a2,
        (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        (unsigned int)"Status",
        39,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\iso\\service\\srvrpc.c",
        211);
  }
  return v12;
}

```

## disassembly

```asm
0x180009410  push    rbx
0x180009412  push    rsi
0x180009413  push    rdi
0x180009414  push    r14
0x180009416  push    r15
0x180009418  sub     rsp, 50h
0x18000941c  mov     esi, r9d
0x18000941f  mov     r14, r8
0x180009422  mov     r15, rdx
0x180009425  mov     rdi, [rsp+78h+arg_20]
0x18000942d  test    rdi, rdi
0x180009430  jz      loc_1800094E4
0x180009436  mov     rbx, [rsp+78h+arg_28]
0x18000943e  test    rbx, rbx
0x180009441  jz      loc_180009530
0x180009447  call    cs:__imp_RpcImpersonateClient
0x18000944d  test    eax, eax
0x18000944f  jnz     loc_180009537
0x180009455  mov     [rdi], eax
0x180009457  mov     eax, [rsp+78h+arg_30]
0x18000945e  mov     dword ptr [rsp+78h+var_50], eax
0x180009462  mov     [rsp+78h+var_58], rbx
0x180009467  mov     r9, rdi
0x18000946a  mov     r8d, esi
0x18000946d  mov     rdx, r14
0x180009470  mov     rcx, r15
0x180009473  mov     rax, cs:off_180025090
0x18000947a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000947f  mov     ebx, eax
0x180009481  mov     [rsp+78h+var_38], eax
0x180009485  test    eax, eax
0x180009487  jns     short loc_1800094A4
0x180009489  mov     r9d, 6F2h
0x18000948f  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009496  lea     rdx, aStatus; "Status"
0x18000949d  mov     ecx, eax
0x18000949f  call    DebugTraceError
0x1800094a4  jmp     short loc_1800094D0
0x1800094a6  mov     ebx, eax
0x1800094a8  mov     r9d, 6F8h
0x1800094ae  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800094b5  lea     rdx, aNtstatus; "ntStatus"
0x1800094bc  mov     ecx, eax
0x1800094be  call    DebugTraceError
0x1800094c3  mov     ecx, ebx
0x1800094c5  call    NormalizeNteStatus
0x1800094ca  mov     ebx, eax
0x1800094cc  mov     [rsp+78h+var_38], eax
0x1800094d0  call    cs:__imp_RpcRevertToSelf
0x1800094d6  mov     eax, ebx
0x1800094d8  add     rsp, 50h
0x1800094dc  pop     r15
0x1800094de  pop     r14
0x1800094e0  pop     rdi
0x1800094e1  pop     rsi
0x1800094e2  pop     rbx
0x1800094e3  retn
0x1800094e4  mov     ebx, 80090027h
0x1800094e9  lea     rax, WPP_GLOBAL_Control
0x1800094f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800094f7  cmp     rcx, rax
0x1800094fa  jz      short loc_1800094D6
0x1800094fc  test    byte ptr [rcx+1Ch], 1
0x180009500  jz      short loc_1800094D6
0x180009502  mov     [rsp+78h+var_48], 6D3h
0x18000950a  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009511  mov     [rsp+78h+var_50], r8
0x180009516  mov     dword ptr [rsp+78h+var_58], 80090027h
0x18000951e  lea     r9, aStatus; "Status"
0x180009525  mov     rcx, [rcx+10h]
0x180009529  call    WPP_SF_sDsd
0x18000952e  jmp     short loc_1800094D6
0x180009530  mov     ebx, 80090027h
0x180009535  jmp     short loc_1800094D6
0x180009537  mov     r9d, 6E0h
0x18000953d  lea     r8, aOnecoreDsSecur_8; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180009544  lea     rdx, aStatus; "Status"
0x18000954b  mov     ecx, eax
0x18000954d  call    DebugTraceError
0x180009552  mov     ebx, 80090020h
0x180009557  jmp     loc_1800094D6
```
