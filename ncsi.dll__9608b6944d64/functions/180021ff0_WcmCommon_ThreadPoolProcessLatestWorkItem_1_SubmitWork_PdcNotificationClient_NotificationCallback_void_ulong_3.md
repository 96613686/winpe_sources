# WcmCommon::ThreadPoolProcessLatestWorkItem<1>::SubmitWork<`PdcNotificationClient::NotificationCallback(void *,ulong)'::`3'::_lambda_1_>(`PdcNotificationClient::NotificationCallback(void *,ulong)'::`3'::_lambda_1_ &&,ulong)

- ea: `0x180021ff0`
- end: `0x180022088`
- name: `??$SubmitWork@V_lambda_1_@?2??NotificationCallback@PdcNotificationClient@@CAJPEAXK@Z@@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@QEAAX$$QEAV_lambda_1_@?2??NotificationCallback@PdcNotificationClient@@CAJPEAXK@Z@K@Z`
- size: `152`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800606e0`

## callees

- `0x18000b0f4`
- `0x180021ff0`
- `0x180022318`
- `0x180022758`
- `0x18005fbbc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180022072`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x180022072`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002202e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022063`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002202e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180022063`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002200e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002200e`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ___SubmitWork_V_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z____ThreadPoolProcessLatestWorkItem__00_WcmCommon__QEAAX__QEAV_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z_K_Z(
        LPCRITICAL_SECTION lpCriticalSection,
        __int64 a2)
{
  __int64 v4; // rbx
  __int64 any_V__function___A6AXXZ_std__V_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z__0A__std__YA_AVany_0___QEAV_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z__Z; // rax
  _BYTE v6[96]; // [rsp+28h] [rbp-60h] BYREF

  if ( !(unsigned __int8)WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady() )
  {
    EnterCriticalSection(lpCriticalSection);
    if ( LOBYTE(lpCriticalSection[5].OwningThread) )
    {
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
    else
    {
      v4 = *(_QWORD *)&lpCriticalSection[5].LockCount;
      any_V__function___A6AXXZ_std__V_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z__0A__std__YA_AVany_0___QEAV_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z__Z = ___make_any_V__function___A6AXXZ_std__V_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z__0A__std__YA_AVany_0___QEAV_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z__Z(v6, a2);
      std::any::operator=(
        &lpCriticalSection[3].SpinCount,
        any_V__function___A6AXXZ_std__V_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z__0A__std__YA_AVany_0___QEAV_lambda_1___2__NotificationCallback_PdcNotificationClient__CAJPEAXK_Z__Z);
      std::any::reset((std::any *)v6);
      LeaveCriticalSection(lpCriticalSection);
      if ( !v4 )
        SubmitThreadpoolWork((PTP_WORK)lpCriticalSection[3].DebugInfo);
    }
  }
}

```

## disassembly

```asm
0x180021ff0  mov     [rsp+arg_10], rbx
0x180021ff5  push    rbp
0x180021ff6  push    rsi
0x180021ff7  push    rdi
0x180021ff8  sub     rsp, 70h
0x180021ffc  mov     rbp, rdx
0x180021fff  mov     rdi, rcx
0x180022002  call    ?BackoffTimerNotReady@?$ThreadPoolProcessLatestWorkItem@$00@WcmCommon@@AEAA_NXZ; WcmCommon::ThreadPoolProcessLatestWorkItem<1>::BackoffTimerNotReady(void)
0x180022007  test    al, al
0x180022009  jnz     short loc_180022078
0x18002200b  mov     rcx, rdi; lpCriticalSection
0x18002200e  call    cs:__imp_EnterCriticalSection
0x180022014  mov     [rsp+88h+var_68], rdi
0x180022019  lea     rsi, [rdi+98h]
0x180022020  cmp     byte ptr [rsi+40h], 0
0x180022024  jz      short loc_180022036
0x180022026  test    rdi, rdi
0x180022029  jz      short loc_180022078
0x18002202b  mov     rcx, rdi; lpCriticalSection
0x18002202e  call    cs:__imp_LeaveCriticalSection
0x180022034  jmp     short loc_180022078
0x180022036  mov     rbx, [rdi+0D0h]
0x18002203d  mov     rdx, rbp
0x180022040  lea     rcx, [rsp+88h+var_60]
0x180022045  call    ??$make_any@V?$function@$$A6AXXZ@std@@V_lambda_1_@?2??NotificationCallback@PdcNotificationClient@@CAJPEAXK@Z@$0A@@std@@YA?AVany@0@$$QEAV_lambda_1_@?2??NotificationCallback@PdcNotificationClient@@CAJPEAXK@Z@@Z; std::make_any<std::function<void (void)>,`PdcNotificationClient::NotificationCallback(void *,ulong)'::`3'::_lambda_1_,0>(`PdcNotificationClient::NotificationCallback(void *,ulong)'::`3'::_lambda_1_ &&)
0x18002204a  mov     rdx, rax
0x18002204d  mov     rcx, rsi
0x180022050  call    ??4any@std@@QEAAAEAV01@$$QEAV01@@Z; std::any::operator=(std::any &&)
0x180022055  lea     rcx, [rsp+88h+var_60]; this
0x18002205a  call    ?reset@any@std@@QEAAXXZ; std::any::reset(void)
0x18002205f  nop
0x180022060  mov     rcx, rdi; lpCriticalSection
0x180022063  call    cs:__imp_LeaveCriticalSection
0x180022069  test    rbx, rbx
0x18002206c  jnz     short loc_180022078
0x18002206e  mov     rcx, [rdi+78h]; pwk
0x180022072  call    cs:__imp_SubmitThreadpoolWork
0x180022078  mov     rbx, [rsp+88h+arg_10]
0x180022080  add     rsp, 70h
0x180022084  pop     rdi
0x180022085  pop     rsi
0x180022086  pop     rbp
0x180022087  retn
```
