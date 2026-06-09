# RPC_SERVER::CloseInterfaceGroup(void *)

- ea: `0x1800873e4`
- end: `0x18008754e`
- name: `?CloseInterfaceGroup@RPC_SERVER@@QEAAJPEAX@Z`
- size: `362`
- prototype: `int(RPC_SERVER *__hidden this, void *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800873b0`

## callees

- `0x180021ce0`
- `0x180086e94`
- `0x1800873e4`
- `0x180087554`
- `0x180087ad0`
- `0x1800b42dc`
- `0x1800d2010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180087448`
- `ntdll!RtlLeaveCriticalSection` at `0x180087498`
- `ntdll!RtlLeaveCriticalSection` at `0x1800874a1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800874d2`
- `ntdll!RtlLeaveCriticalSection` at `0x180087448`
- `ntdll!RtlLeaveCriticalSection` at `0x180087498`
- `ntdll!RtlLeaveCriticalSection` at `0x1800874a1`
- `ntdll!RtlLeaveCriticalSection` at `0x1800874d2`
- `ntdll!RtlEnterCriticalSection` at `0x180087405`
- `ntdll!RtlEnterCriticalSection` at `0x18008746a`
- `ntdll!RtlEnterCriticalSection` at `0x1800874c9`
- `ntdll!RtlEnterCriticalSection` at `0x180087405`
- `ntdll!RtlEnterCriticalSection` at `0x18008746a`
- `ntdll!RtlEnterCriticalSection` at `0x1800874c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800874f2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x1800874f2`

## pseudocode

```c
__int64 __fastcall RPC_SERVER::CloseInterfaceGroup(RPC_SERVER *this, char *a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // r14
  struct _RTL_CRITICAL_SECTION *v3; // rbp
  int v5; // eax
  BOOL v6; // esi
  unsigned int v7; // ebx
  char **v8; // rdx
  void **v9; // rcx
  PTP_WORK *v10; // rcx
  unsigned int v12; // eax
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // [rsp+28h] [rbp-50h]
  int v16; // [rsp+30h] [rbp-48h]

  v2 = GlobalRpcServer;
  v3 = (struct _RTL_CRITICAL_SECTION *)(a2 + 176);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(a2 + 176));
  if ( *((_DWORD *)a2 + 10) != 667022880 )
  {
    v7 = 87;
    goto LABEL_4;
  }
  v5 = *((_DWORD *)a2 + 58);
  v6 = 0;
  if ( v5 == 1 )
  {
    v7 = RPC_SERVER::DeactivateInterfaceGroup(v2, (struct RPCP_INTERFACE_GROUP *)a2, 0, 1, 1);
    if ( v7 )
    {
LABEL_4:
      RtlLeaveCriticalSection(v3);
      return v7;
    }
  }
  else
  {
    v6 = v5 == 2;
  }
  _InterlockedExchange((volatile __int32 *)a2 + 58, 3);
  RtlEnterCriticalSection(v2);
  v8 = (char **)*((_QWORD *)a2 + 3);
  if ( v8[1] != a2 + 24 || (v9 = (void **)*((_QWORD *)a2 + 4), *v9 != a2 + 24) )
    __fastfail(3u);
  *v9 = v8;
  v8[1] = (char *)v9;
  RtlLeaveCriticalSection(v2);
  RtlLeaveCriticalSection(v3);
  LogEvent(0x67u, 0x44u, a2, 0, 0, v15, v16);
  RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)a2 + 6);
  RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)a2 + 6);
  RPCP_INTERFACE_GROUP::CancelIdleTimer((RPCP_INTERFACE_GROUP *)a2);
  v10 = (PTP_WORK *)*((_QWORD *)a2 + 21);
  if ( v10 )
    WaitForThreadpoolWorkCallbacks(*v10, 1);
  if ( v6 )
  {
    v12 = RpcpEpReRaiseTriggers(*((unsigned int *)a2 + 14), *((_QWORD *)a2 + 6));
    if ( v12 )
    {
      if ( (Microsoft_Windows_RPCEnableBits & 2) != 0 )
        McTemplateU0d_EtwEventWriteTransfer(v14, v13, v12);
    }
  }
  v7 = 0;
  (*(void (__fastcall **)(char *))(*(_QWORD *)a2 + 32LL))(a2);
  return v7;
}

```

## disassembly

```asm
0x1800873e4  push    rbx
0x1800873e6  push    rbp
0x1800873e7  push    rsi
0x1800873e8  push    rdi
0x1800873e9  push    r14
0x1800873eb  push    r15
0x1800873ed  sub     rsp, 48h
0x1800873f1  mov     r14, cs:?GlobalRpcServer@@3PEAVRPC_SERVER@@EA; RPC_SERVER * GlobalRpcServer
0x1800873f8  lea     rbp, [rdx+0B0h]
0x1800873ff  mov     rcx, rbp; CriticalSection
0x180087402  mov     rdi, rdx
0x180087405  call    cs:__imp_RtlEnterCriticalSection
0x18008740b  cmp     dword ptr [rdi+28h], 27C1F620h
0x180087412  jnz     loc_180087544
0x180087418  mov     eax, [rdi+0E8h]
0x18008741e  xor     esi, esi
0x180087420  lea     r15d, [rsi+1]
0x180087424  cmp     eax, r15d
0x180087427  jnz     short loc_180087453
0x180087429  mov     r9d, r15d; int
0x18008742c  mov     dword ptr [rsp+78h+var_58], r15d; int
0x180087431  xor     r8d, r8d; int
0x180087434  mov     rdx, rdi; struct RPCP_INTERFACE_GROUP *
0x180087437  mov     rcx, r14; CriticalSection
0x18008743a  call    ?DeactivateInterfaceGroup@RPC_SERVER@@QEAAJPEAXHHH@Z; RPC_SERVER::DeactivateInterfaceGroup(void *,int,int,int)
0x18008743f  mov     ebx, eax
0x180087441  test    eax, eax
0x180087443  jz      short loc_18008745A
0x180087445  mov     rcx, rbp; CriticalSection
0x180087448  call    cs:__imp_RtlLeaveCriticalSection
0x18008744e  jmp     loc_18008750D
0x180087453  cmp     eax, 2
0x180087456  cmovz   esi, r15d
0x18008745a  mov     ebx, 3
0x18008745f  mov     rcx, r14; CriticalSection
0x180087462  mov     eax, ebx
0x180087464  xchg    eax, [rdi+0E8h]
0x18008746a  call    cs:__imp_RtlEnterCriticalSection
0x180087470  lea     rax, [rdi+18h]
0x180087474  mov     rdx, [rax]
0x180087477  cmp     [rdx+8], rax
0x18008747b  jnz     loc_18008753F
0x180087481  mov     rcx, [rax+8]
0x180087485  cmp     [rcx], rax
0x180087488  jnz     loc_18008753F
0x18008748e  mov     [rcx], rdx
0x180087491  mov     [rdx+8], rcx
0x180087495  mov     rcx, r14; CriticalSection
0x180087498  call    cs:__imp_RtlLeaveCriticalSection
0x18008749e  mov     rcx, rbp; CriticalSection
0x1800874a1  call    cs:__imp_RtlLeaveCriticalSection
0x1800874a7  xor     r9d, r9d; void *
0x1800874aa  mov     [rsp+78h+var_58], 0; unsigned __int64
0x1800874b3  mov     r8, rdi; void *
0x1800874b6  mov     dl, 44h ; 'D'; unsigned __int8
0x1800874b8  mov     cl, 67h ; 'g'; unsigned __int8
0x1800874ba  call    ?LogEvent@@YAXEEPEAX0_KHH@Z; LogEvent(uchar,uchar,void *,void *,unsigned __int64,int,int)
0x1800874bf  lea     rbx, [rdi+0F0h]
0x1800874c6  mov     rcx, rbx; CriticalSection
0x1800874c9  call    cs:__imp_RtlEnterCriticalSection
0x1800874cf  mov     rcx, rbx; CriticalSection
0x1800874d2  call    cs:__imp_RtlLeaveCriticalSection
0x1800874d8  mov     rcx, rdi; this
0x1800874db  call    ?CancelIdleTimer@RPCP_INTERFACE_GROUP@@QEAAXXZ; RPCP_INTERFACE_GROUP::CancelIdleTimer(void)
0x1800874e0  mov     rcx, [rdi+0A8h]
0x1800874e7  test    rcx, rcx
0x1800874ea  jz      short loc_1800874F8
0x1800874ec  mov     rcx, [rcx]; pwk
0x1800874ef  mov     edx, r15d; fCancelPendingCallbacks
0x1800874f2  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x1800874f8  test    esi, esi
0x1800874fa  jnz     short loc_18008751C
0x1800874fc  xor     ebx, ebx
0x1800874fe  mov     rax, [rdi]
0x180087501  mov     rcx, rdi
0x180087504  mov     rax, [rax+20h]
0x180087508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008750d  mov     eax, ebx
0x18008750f  add     rsp, 48h
0x180087513  pop     r15
0x180087515  pop     r14
0x180087517  pop     rdi
0x180087518  pop     rsi
0x180087519  pop     rbp
0x18008751a  pop     rbx
0x18008751b  retn
0x18008751c  mov     rdx, [rdi+30h]
0x180087520  mov     ecx, [rdi+38h]
0x180087523  call    RpcpEpReRaiseTriggers
0x180087528  test    eax, eax
0x18008752a  jz      short loc_1800874FC
0x18008752c  test    cs:Microsoft_Windows_RPCEnableBits, 2
0x180087533  jz      short loc_1800874FC
0x180087535  mov     r8d, eax
0x180087538  call    McTemplateU0d_EtwEventWriteTransfer
0x18008753d  jmp     short loc_1800874FC
0x18008753f  mov     rcx, rbx
0x180087542  int     29h; Win8: RtlFailFast(ecx)
0x180087544  mov     ebx, 57h ; 'W'
0x180087549  jmp     loc_180087445
```
