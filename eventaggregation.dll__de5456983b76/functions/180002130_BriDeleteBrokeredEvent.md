# BriDeleteBrokeredEvent

- ea: `0x180002130`
- end: `0x18000229e`
- name: `BriDeleteBrokeredEvent`
- size: `366`
- prototype: `__int64 __fastcall(void *Source1, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180002000`
- `0x180008940`

## callees

- `0x180002130`
- `0x1800026f0`
- `0x1800029b0`
- `0x180002a40`
- `0x180006e70`
- `0x1800072e0`

## import_xrefs

- `ntdll!RtlAcquireSRWLockShared` at `0x1800021a1`
- `ntdll!RtlAcquireSRWLockShared` at `0x1800021a1`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800021d1`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002291`
- `ntdll!RtlReleaseSRWLockShared` at `0x1800021d1`
- `ntdll!RtlReleaseSRWLockShared` at `0x180002291`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000218a`
- `ntdll!RtlRunOnceExecuteOnce` at `0x18000218a`
- `RPCRT4!NdrClientCall3` at `0x18000223c`
- `RPCRT4!NdrClientCall3` at `0x18000223c`
- `RPCRT4!RpcBindingFree` at `0x180002255`
- `RPCRT4!RpcBindingFree` at `0x180002255`
- `RPCRT4!UuidEqual` at `0x180002212`
- `RPCRT4!UuidEqual` at `0x180002212`

## pseudocode

```c
__int64 __fastcall BriDeleteBrokeredEvent(void *Source1, int a2)
{
  char v2; // di
  __int64 v4; // rdx
  int v5; // ebx
  __int64 EventContextByEventId; // rax
  unsigned int Pointer; // eax
  RPC_BINDING_HANDLE v8; // rbx
  unsigned int v9; // edx
  MIDL_STUBLESS_PROXY_INFO *v10; // rcx
  int v11; // eax
  RPC_STATUS Status; // [rsp+30h] [rbp-58h] BYREF
  __int64 v14; // [rsp+38h] [rbp-50h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-48h] BYREF
  UUID Uuid1; // [rsp+48h] [rbp-40h] BYREF

  v14 = 0;
  v2 = a2;
  Binding = 0;
  Uuid1 = 0;
  if ( !Source1 || (a2 & 0xFFFFFFFE) != 0 )
  {
    v5 = -1073741811;
  }
  else
  {
    v5 = RtlRunOnceExecuteOnce(&BrokerInternalClientInitOnce, BrpInitOnceRunOnceCallback, 0, 0);
    if ( v5 >= 0 )
    {
      RtlAcquireSRWLockShared(&BrokeredEventTableLock, v4);
      EventContextByEventId = BripFindEventContextByEventId(Source1);
      if ( EventContextByEventId )
      {
        Uuid1 = *(UUID *)(EventContextByEventId + 40);
        v14 = *(_QWORD *)(EventContextByEventId + 24);
        RtlReleaseSRWLockShared(&BrokeredEventTableLock);
        Pointer = BripCreateRpcBindingHandle(&Uuid1);
        if ( Pointer
          || ((v8 = Binding, Status = 0, UuidEqual(&Uuid1, (UUID *)&g_SmsRouterBrokerId, &Status))
            ? (v9 = 1, v10 = (MIDL_STUBLESS_PROXY_INFO *)&stru_18000D0F0)
            : (v9 = 2, v10 = (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo),
              (Pointer = (unsigned int)NdrClientCall3(v10, v9, 0, v8, 2 * (v2 & 1u) + 1, &v14).Pointer) != 0) )
        {
          v11 = BripMapRpcStatus(Pointer);
        }
        else
        {
          v11 = BripDeleteEventContext(Source1);
        }
        v5 = v11;
      }
      else
      {
        RtlReleaseSRWLockShared(&BrokeredEventTableLock);
        v5 = -1073741275;
      }
    }
  }
  RpcBindingFree(&Binding);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180002130  push    rbx
0x180002132  push    rbp
0x180002133  push    rsi
0x180002134  push    rdi
0x180002135  sub     rsp, 68h
0x180002139  mov     rax, cs:__security_cookie
0x180002140  xor     rax, rsp
0x180002143  mov     [rsp+88h+var_30], rax
0x180002148  xor     ebp, ebp
0x18000214a  xorps   xmm0, xmm0
0x18000214d  mov     [rsp+88h+var_50], rbp
0x180002152  mov     edi, edx
0x180002154  mov     [rsp+88h+Binding], rbp
0x180002159  mov     rsi, rcx
0x18000215c  movups  xmmword ptr [rsp+88h+Uuid1.Data1], xmm0
0x180002161  test    rcx, rcx
0x180002164  jz      loc_180002273
0x18000216a  test    edx, 0FFFFFFFEh
0x180002170  jnz     loc_180002273
0x180002176  xor     r9d, r9d
0x180002179  lea     rdx, BrpInitOnceRunOnceCallback
0x180002180  xor     r8d, r8d
0x180002183  lea     rcx, BrokerInternalClientInitOnce
0x18000218a  call    cs:__imp_RtlRunOnceExecuteOnce
0x180002190  mov     ebx, eax
0x180002192  test    eax, eax
0x180002194  js      loc_180002250
0x18000219a  lea     rcx, BrokeredEventTableLock
0x1800021a1  call    cs:__imp_RtlAcquireSRWLockShared
0x1800021a7  mov     rcx, rsi; Source1
0x1800021aa  call    BripFindEventContextByEventId
0x1800021af  lea     rcx, BrokeredEventTableLock
0x1800021b6  test    rax, rax
0x1800021b9  jz      loc_180002291
0x1800021bf  movups  xmm0, xmmword ptr [rax+28h]
0x1800021c3  movups  xmmword ptr [rsp+88h+Uuid1.Data1], xmm0
0x1800021c8  mov     rax, [rax+18h]
0x1800021cc  mov     [rsp+88h+var_50], rax
0x1800021d1  call    cs:__imp_RtlReleaseSRWLockShared
0x1800021d7  lea     rdx, [rsp+88h+Binding]
0x1800021dc  lea     rcx, [rsp+88h+Uuid1]; Source1
0x1800021e1  call    BripCreateRpcBindingHandle
0x1800021e6  test    eax, eax
0x1800021e8  jnz     loc_180002288
0x1800021ee  mov     rbx, [rsp+88h+Binding]
0x1800021f3  lea     r8, [rsp+88h+Status]; Status
0x1800021f8  and     edi, 1
0x1800021fb  mov     [rsp+88h+Status], ebp
0x1800021ff  lea     rdx, g_SmsRouterBrokerId; Uuid2
0x180002206  lea     rcx, [rsp+88h+Uuid1]; Uuid1
0x18000220b  lea     edi, ds:1[rdi*2]
0x180002212  call    cs:__imp_UuidEqual
0x180002218  xor     r8d, r8d; pReturnValue
0x18000221b  mov     r9, rbx
0x18000221e  test    eax, eax
0x180002220  lea     rax, [rsp+88h+var_50]
0x180002225  mov     [rsp+88h+var_60], rax
0x18000222a  mov     [rsp+88h+var_68], edi
0x18000222e  jnz     short loc_18000227A
0x180002230  mov     edx, 2; nProcNum
0x180002235  lea     rcx, pProxyInfo; pProxyInfo
0x18000223c  call    cs:__imp_NdrClientCall3
0x180002242  test    eax, eax
0x180002244  jnz     short loc_180002288
0x180002246  mov     rcx, rsi; Source1
0x180002249  call    BripDeleteEventContext
0x18000224e  mov     ebx, eax
0x180002250  lea     rcx, [rsp+88h+Binding]; Binding
0x180002255  call    cs:__imp_RpcBindingFree
0x18000225b  mov     eax, ebx
0x18000225d  mov     rcx, [rsp+88h+var_30]
0x180002262  xor     rcx, rsp; StackCookie
0x180002265  call    __security_check_cookie
0x18000226a  add     rsp, 68h
0x18000226e  pop     rdi
0x18000226f  pop     rsi
0x180002270  pop     rbp
0x180002271  pop     rbx
0x180002272  retn
0x180002273  mov     ebx, 0C000000Dh
0x180002278  jmp     short loc_180002250
0x18000227a  mov     edx, 1
0x18000227f  lea     rcx, stru_18000D0F0
0x180002286  jmp     short loc_18000223C
0x180002288  mov     ecx, eax
0x18000228a  call    BripMapRpcStatus
0x18000228f  jmp     short loc_18000224E
0x180002291  call    cs:__imp_RtlReleaseSRWLockShared
0x180002297  mov     ebx, 0C0000225h
0x18000229c  jmp     short loc_180002250
```
