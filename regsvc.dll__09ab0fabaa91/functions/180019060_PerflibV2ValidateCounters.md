# PerflibV2ValidateCounters

- ea: `0x180019060`
- end: `0x180019170`
- name: `PerflibV2ValidateCounters`
- size: `272`
- prototype: `__int64 __fastcall(struct _PERF_QUERY *, unsigned int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation`

## callees

- `0x180005f20`
- `0x180007740`
- `0x180008042`
- `0x180016574`
- `0x180019060`
- `0x180019178`

## import_xrefs

- `RPCRT4!RpcRaiseException` at `0x1800190f6`
- `RPCRT4!RpcRaiseException` at `0x1800190ff`
- `RPCRT4!RpcRaiseException` at `0x180019114`
- `RPCRT4!RpcRaiseException` at `0x1800190f6`
- `RPCRT4!RpcRaiseException` at `0x1800190ff`
- `RPCRT4!RpcRaiseException` at `0x180019114`
- `RPCRT4!RpcImpersonateClient` at `0x180019108`
- `RPCRT4!RpcImpersonateClient` at `0x180019108`
- `RPCRT4!RpcRevertToSelf` at `0x18001912e`
- `RPCRT4!RpcRevertToSelf` at `0x18001912e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800190db`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x1800190db`

## pseudocode

```c
__int64 __fastcall PerflibV2ValidateCounters(struct _PERF_QUERY *a1, unsigned int a2, __int64 a3)
{
  unsigned int IsLocalQueryFromHandle; // eax
  unsigned int v5; // ebx
  RPC_STATUS v6; // eax
  RPC_STATUS v7; // eax
  int RpcCallAttributes; // [rsp+20h] [rbp-B8h] BYREF
  _BYTE v10[36]; // [rsp+24h] [rbp-B4h] BYREF
  unsigned int v11; // [rsp+48h] [rbp-90h]

  if ( !a1 || !a3 || a2 < 0x28 )
    return 87;
  IsLocalQueryFromHandle = PerflibciIsLocalQueryFromHandle(a1);
  v5 = IsLocalQueryFromHandle;
  if ( IsLocalQueryFromHandle )
  {
    if ( IsLocalQueryFromHandle != 13 )
      return v5;
    PerflibciReleaseMutex(*(_QWORD *)a1);
    return 87;
  }
  memset_0(v10, 0, 0x74u);
  RpcCallAttributes = 3;
  v6 = RpcServerInqCallAttributesW(0, &RpcCallAttributes);
  if ( v6 != 1746 )
  {
    if ( v6 )
      RpcRaiseException(v6);
    if ( v11 < 6 )
      RpcRaiseException(5);
  }
  v7 = RpcImpersonateClient(0);
  if ( v7 )
    RpcRaiseException(v7);
  v5 = PerflibciLocalValidateCounters(a1);
  RpcRevertToSelf();
  PerflibciReleaseMutex(*(_QWORD *)a1);
  return v5;
}

```

## disassembly

```asm
0x180019060  push    rbx
0x180019062  push    rbp
0x180019063  push    rsi
0x180019064  push    rdi
0x180019065  push    r14
0x180019067  sub     rsp, 0B0h
0x18001906e  mov     rax, cs:__security_cookie
0x180019075  xor     rax, rsp
0x180019078  mov     [rsp+0D8h+var_38], rax
0x180019080  xor     r14d, r14d
0x180019083  mov     rbp, r8
0x180019086  test    r9d, r9d
0x180019089  mov     esi, edx
0x18001908b  mov     rdi, rcx
0x18001908e  setnz   r14b
0x180019092  test    rcx, rcx
0x180019095  jz      loc_18001914B
0x18001909b  test    r8, r8
0x18001909e  jz      loc_18001914B
0x1800190a4  cmp     edx, 28h ; '('
0x1800190a7  jb      loc_18001914B
0x1800190ad  call    PerflibciIsLocalQueryFromHandle
0x1800190b2  mov     ebx, eax
0x1800190b4  test    eax, eax
0x1800190b6  jnz     loc_18001913E
0x1800190bc  xor     edx, edx; Val
0x1800190be  lea     r8d, [rax+74h]; Size
0x1800190c2  lea     rcx, [rsp+0D8h+var_B4]; void *
0x1800190c7  call    memset_0
0x1800190cc  lea     rdx, [rsp+0D8h+RpcCallAttributes]; RpcCallAttributes
0x1800190d1  mov     [rsp+0D8h+RpcCallAttributes], 3
0x1800190d9  xor     ecx, ecx; ClientBinding
0x1800190db  call    cs:__imp_RpcServerInqCallAttributesW
0x1800190e1  cmp     eax, 6D2h
0x1800190e6  jz      short loc_180019106
0x1800190e8  test    eax, eax
0x1800190ea  jnz     short loc_1800190FD
0x1800190ec  cmp     [rsp+0D8h+var_90], 6
0x1800190f1  jnb     short loc_180019106
0x1800190f3  lea     ecx, [rbx+5]; exception
0x1800190f6  call    cs:__imp_RpcRaiseException
0x1800190fc  int     3; Trap to Debugger
0x1800190fd  mov     ecx, eax; exception
0x1800190ff  call    cs:__imp_RpcRaiseException
0x180019105  int     3; Trap to Debugger
0x180019106  xor     ecx, ecx; BindingHandle
0x180019108  call    cs:__imp_RpcImpersonateClient
0x18001910e  test    eax, eax
0x180019110  jz      short loc_18001911B
0x180019112  mov     ecx, eax; exception
0x180019114  call    cs:__imp_RpcRaiseException
0x18001911a  int     3; Trap to Debugger
0x18001911b  mov     r9d, r14d
0x18001911e  mov     r8d, esi
0x180019121  mov     rdx, rbp
0x180019124  mov     rcx, rdi; struct _PERF_QUERY *
0x180019127  call    PerflibciLocalValidateCounters
0x18001912c  mov     ebx, eax
0x18001912e  call    cs:__imp_RpcRevertToSelf
0x180019134  mov     rcx, [rdi]
0x180019137  call    PerflibciReleaseMutex
0x18001913c  jmp     short loc_180019150
0x18001913e  cmp     eax, 0Dh
0x180019141  jnz     short loc_180019150
0x180019143  mov     rcx, [rdi]
0x180019146  call    PerflibciReleaseMutex
0x18001914b  mov     ebx, 57h ; 'W'
0x180019150  mov     eax, ebx
0x180019152  mov     rcx, [rsp+0D8h+var_38]
0x18001915a  xor     rcx, rsp; StackCookie
0x18001915d  call    __security_check_cookie
0x180019162  add     rsp, 0B0h
0x180019169  pop     r14
0x18001916b  pop     rdi
0x18001916c  pop     rsi
0x18001916d  pop     rbp
0x18001916e  pop     rbx
0x18001916f  retn
```
