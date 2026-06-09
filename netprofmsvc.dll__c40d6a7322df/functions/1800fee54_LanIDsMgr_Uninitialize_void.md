# LanIDsMgr::Uninitialize(void)

- ea: `0x1800fee54`
- end: `0x1800fefd0`
- name: `?Uninitialize@LanIDsMgr@@AEAAXXZ`
- size: `380`
- prototype: `void __fastcall(LanIDsMgr *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x1800fd728`
- `0x1800fecd4`

## callees

- `0x180009990`
- `0x18000fab0`
- `0x18000ff18`
- `0x18001003c`
- `0x1800fee54`
- `0x1800fefd8`
- `0x1800ffb38`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800feede`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fefc0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800feede`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800fefc0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800feece`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800feece`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800feef1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800feef1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800fef17`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800fef17`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanIDsMgr::Uninitialize(struct _TP_TIMER **this)
{
  struct _TP_TIMER *v2; // rdi
  struct _TP_TIMER *v3; // rcx
  struct _TP_TIMER *v4; // rcx
  struct _TP_TIMER *v5; // rcx
  struct _TP_TIMER *v6; // rdx
  LPCRITICAL_SECTION lpCriticalSection[7]; // [rsp+20h] [rbp-38h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  v2 = 0;
  LanIDsMgr::UnregisterForNotifications((LanIDsMgr *)this);
  lpCriticalSection[0] = 0;
  wil::EnterCriticalSection(lpCriticalSection, this + 1);
  v3 = this[20];
  if ( v3 )
  {
    v2 = this[20];
    this[20] = 0;
    SetThreadpoolTimer(v3, 0, 0, 0);
  }
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
  if ( v2 )
    WaitForThreadpoolTimerCallbacks(v2, 1);
  lpCriticalSection[0] = 0;
  wil::EnterCriticalSection(lpCriticalSection, this + 1);
  if ( v2 )
    CloseThreadpoolTimer(v2);
  LanIDsMgr::ManageLLDPDriver((LanIDsMgr *)this, 1);
  v4 = this[7];
  if ( v4 )
  {
    LANIdsRPCHelper::RpcServerStop(v4);
    this[7] = 0;
  }
  LanIDsMgr::ResetData((LanIDsMgr *)this);
  v5 = this[96];
  if ( v5 )
  {
    v6 = this[16];
    if ( v6 )
    {
      (*(void (__fastcall **)(struct _TP_TIMER *, struct _TP_TIMER *, _QWORD))(*(_QWORD *)v5 + 24LL))(v5, v6, 0);
      this[16] = 0;
    }
    (*(void (__fastcall **)(struct _TP_TIMER *))(*(_QWORD *)this[96] + 8LL))(this[96]);
  }
  *((_BYTE *)this + 48) = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, &WPP_a7d930b269293553628841c7763b54c1_Traceguids);
  if ( lpCriticalSection[0] )
    LeaveCriticalSection(lpCriticalSection[0]);
}

```

## disassembly

```asm
0x1800fee54  push    rbx
0x1800fee56  push    rsi
0x1800fee57  push    rdi
0x1800fee58  push    r14
0x1800fee5a  sub     rsp, 38h
0x1800fee5e  mov     rbx, rcx
0x1800fee61  lea     r14, WPP_GLOBAL_Control
0x1800fee68  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fee6f  cmp     rcx, r14
0x1800fee72  jz      short loc_1800FEE8F
0x1800fee74  test    byte ptr [rcx+1Ch], 4
0x1800fee78  jz      short loc_1800FEE8F
0x1800fee7a  mov     edx, 1Dh
0x1800fee7f  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800fee86  mov     rcx, [rcx+10h]
0x1800fee8a  call    WPP_SF_
0x1800fee8f  xor     edi, edi
0x1800fee91  mov     rcx, rbx; this
0x1800fee94  call    ?UnregisterForNotifications@LanIDsMgr@@AEAAKXZ; LanIDsMgr::UnregisterForNotifications(void)
0x1800fee99  mov     [rsp+58h+lpCriticalSection], rdi
0x1800fee9e  lea     rdx, [rbx+8]
0x1800feea2  lea     rcx, [rsp+58h+lpCriticalSection]
0x1800feea7  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800feeac  mov     rcx, [rbx+0A0h]; pti
0x1800feeb3  test    rcx, rcx
0x1800feeb6  jz      short loc_1800FEED4
0x1800feeb8  mov     rdi, rcx
0x1800feebb  mov     qword ptr [rbx+0A0h], 0
0x1800feec6  xor     r9d, r9d; msWindowLength
0x1800feec9  xor     r8d, r8d; msPeriod
0x1800feecc  xor     edx, edx; pftDueTime
0x1800feece  call    cs:__imp_SetThreadpoolTimer
0x1800feed4  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800feed9  test    rcx, rcx
0x1800feedc  jz      short loc_1800FEEE4
0x1800feede  call    cs:__imp_LeaveCriticalSection
0x1800feee4  test    rdi, rdi
0x1800feee7  jz      short loc_1800FEEF7
0x1800feee9  mov     edx, 1; fCancelPendingCallbacks
0x1800feeee  mov     rcx, rdi; pti
0x1800feef1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800feef7  mov     [rsp+58h+lpCriticalSection], 0
0x1800fef00  lea     rdx, [rbx+8]
0x1800fef04  lea     rcx, [rsp+58h+lpCriticalSection]
0x1800fef09  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800fef0e  nop
0x1800fef0f  test    rdi, rdi
0x1800fef12  jz      short loc_1800FEF1D
0x1800fef14  mov     rcx, rdi; pti
0x1800fef17  call    cs:__imp_CloseThreadpoolTimer
0x1800fef1d  mov     dl, 1; bool
0x1800fef1f  mov     rcx, rbx; this
0x1800fef22  call    ?ManageLLDPDriver@LanIDsMgr@@AEAAX_N@Z; LanIDsMgr::ManageLLDPDriver(bool)
0x1800fef27  mov     rcx, [rbx+38h]; IfSpec
0x1800fef2b  test    rcx, rcx
0x1800fef2e  jz      short loc_1800FEF3D
0x1800fef30  call    ?RpcServerStop@LANIdsRPCHelper@@SAXPEAX@Z; LANIdsRPCHelper::RpcServerStop(void *)
0x1800fef35  mov     qword ptr [rbx+38h], 0
0x1800fef3d  mov     rcx, rbx; this
0x1800fef40  call    ?ResetData@LanIDsMgr@@AEAAXXZ; LanIDsMgr::ResetData(void)
0x1800fef45  mov     rcx, [rbx+300h]
0x1800fef4c  test    rcx, rcx
0x1800fef4f  jz      short loc_1800FEF8A
0x1800fef51  mov     rdx, [rbx+80h]
0x1800fef58  test    rdx, rdx
0x1800fef5b  jz      short loc_1800FEF77
0x1800fef5d  mov     rax, [rcx]
0x1800fef60  xor     r8d, r8d
0x1800fef63  mov     rax, [rax+18h]
0x1800fef67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fef6c  mov     qword ptr [rbx+80h], 0
0x1800fef77  mov     rcx, [rbx+300h]
0x1800fef7e  mov     rax, [rcx]
0x1800fef81  mov     rax, [rax+8]
0x1800fef85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fef8a  mov     byte ptr [rbx+30h], 0
0x1800fef8e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800fef95  cmp     rcx, r14
0x1800fef98  jz      short loc_1800FEFB6
0x1800fef9a  test    byte ptr [rcx+1Ch], 4
0x1800fef9e  jz      short loc_1800FEFB6
0x1800fefa0  mov     edx, 1Eh
0x1800fefa5  lea     r8, WPP_a7d930b269293553628841c7763b54c1_Traceguids
0x1800fefac  mov     rcx, [rcx+10h]
0x1800fefb0  call    WPP_SF_
0x1800fefb5  nop
0x1800fefb6  mov     rcx, [rsp+58h+lpCriticalSection]; lpCriticalSection
0x1800fefbb  test    rcx, rcx
0x1800fefbe  jz      short loc_1800FEFC6
0x1800fefc0  call    cs:__imp_LeaveCriticalSection
0x1800fefc6  add     rsp, 38h
0x1800fefca  pop     r14
0x1800fefcc  pop     rdi
0x1800fefcd  pop     rsi
0x1800fefce  pop     rbx
0x1800fefcf  retn
```
