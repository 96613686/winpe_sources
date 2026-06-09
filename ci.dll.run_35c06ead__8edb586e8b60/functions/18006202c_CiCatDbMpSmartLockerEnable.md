# CiCatDbMpSmartLockerEnable

- ea: `0x18006202c`
- end: `0x18006223c`
- name: `CiCatDbMpSmartLockerEnable`
- size: `528`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180058048`
- `0x180071740`

## callees

- `0x180020700`
- `0x18002c0d0`
- `0x18002c500`
- `0x18006202c`
- `0x18009c3a4`
- `0x1800bba44`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1800621e4`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800621e4`
- `ntoskrnl!KeInitializeEvent` at `0x1800620ef`
- `ntoskrnl!KeInitializeEvent` at `0x1800620ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006214b`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062188`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006214b`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062188`
- `msrpc!RpcAsyncCancelCall` at `0x180062166`
- `msrpc!RpcAsyncCancelCall` at `0x180062166`
- `msrpc!RpcAsyncCompleteCall` at `0x18006219e`
- `msrpc!RpcAsyncCompleteCall` at `0x1800621b4`
- `msrpc!RpcAsyncCompleteCall` at `0x18006219e`
- `msrpc!RpcAsyncCompleteCall` at `0x1800621b4`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800620b2`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800620b2`

## pseudocode

```c
__int64 __fastcall CiCatDbMpSmartLockerEnable(unsigned int a1)
{
  unsigned int v2; // esi
  int v3; // ebx
  RPC_STATUS v4; // ebx
  NTSTATUS v5; // r14d
  RPC_STATUS v6; // eax
  int Reply; // [rsp+30h] [rbp-D8h] BYREF
  unsigned int v9; // [rsp+34h] [rbp-D4h]
  union _LARGE_INTEGER Interval; // [rsp+38h] [rbp-D0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-C8h] BYREF
  unsigned int v12; // [rsp+48h] [rbp-C0h]
  __int64 v13; // [rsp+50h] [rbp-B8h] BYREF
  struct _KEVENT Event; // [rsp+58h] [rbp-B0h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-98h] BYREF

  v12 = a1;
  memset(&pAsync, 0, sizeof(pAsync));
  Binding = 0;
  memset(&Event, 0, sizeof(Event));
  v2 = 0;
  v9 = 0;
  Interval.QuadPart = 0;
  Reply = 0;
  v13 = 0;
  v3 = CipCatDbRpcConnect(&Binding, &v13);
  if ( v3 >= 0 )
  {
    while ( 1 )
    {
      v4 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
      if ( v4 )
        goto LABEL_3;
      pAsync.UserInfo = 0;
      pAsync.NotificationType = RpcNotificationTypeEvent;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      pAsync.u.Event = &Event;
      SSCatDBMpSmartLockerEnable(&pAsync, Binding, a1);
      Interval.QuadPart = -80000000;
      v5 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Interval);
      if ( v5 )
      {
        RpcAsyncCancelCall(&pAsync, v4 + 1);
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        RpcAsyncCompleteCall(&pAsync, &Reply);
LABEL_3:
        v3 = -1073741823;
        goto LABEL_13;
      }
      v6 = RpcAsyncCompleteCall(&pAsync, &Reply);
      if ( v6 != -1073610728 || v2 >= 0x14 )
        break;
      v9 = ++v2;
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    v3 = -1073741823;
    if ( !v6 )
    {
      if ( Reply )
        v5 = -1073741823;
      v3 = v5;
    }
  }
LABEL_13:
  if ( Binding )
    CipCatDbRpcDisconnect(&Binding);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006202c  push    rbx
0x18006202e  push    rsi
0x18006202f  push    r14
0x180062031  push    r15
0x180062033  sub     rsp, 0E8h
0x18006203a  mov     rax, cs:__security_cookie
0x180062041  xor     rax, rsp
0x180062044  mov     [rsp+108h+var_38], rax
0x18006204c  mov     r15d, ecx
0x18006204f  mov     [rsp+108h+var_C0], ecx
0x180062053  xor     edx, edx; Val
0x180062055  lea     r8d, [rdx+58h]; Size
0x180062059  lea     rcx, [rsp+108h+pAsync]; void *
0x18006205e  call    memset
0x180062063  mov     [rsp+108h+Binding], 0
0x18006206c  xorps   xmm0, xmm0
0x18006206f  xor     eax, eax
0x180062071  movups  xmmword ptr [rsp+108h+Event.Header], xmm0
0x180062076  mov     [rsp+108h+Event.Header.WaitListHead.Blink], rax
0x18006207b  xor     esi, esi
0x18006207d  mov     [rsp+108h+var_D4], esi
0x180062081  mov     qword ptr [rsp+108h+Interval], rax
0x180062086  mov     [rsp+108h+Reply], eax
0x18006208a  mov     [rsp+108h+var_B8], rax
0x18006208f  lea     rdx, [rsp+108h+var_B8]
0x180062094  lea     rcx, [rsp+108h+Binding]
0x180062099  call    CipCatDbRpcConnect
0x18006209e  mov     ebx, eax
0x1800620a0  test    eax, eax
0x1800620a2  js      loc_180062209
0x1800620a8  mov     edx, 58h ; 'X'; Size
0x1800620ad  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800620b2  call    cs:__imp_RpcAsyncInitializeHandle
0x1800620b9  nop     dword ptr [rax+rax+00h]
0x1800620be  mov     ebx, eax
0x1800620c0  test    eax, eax
0x1800620c2  jz      short loc_1800620CE
0x1800620c4  mov     ebx, 0C0000001h
0x1800620c9  jmp     loc_180062209
0x1800620ce  mov     [rsp+108h+pAsync.UserInfo], 0
0x1800620da  mov     [rsp+108h+pAsync.NotificationType], 1
0x1800620e5  xor     r8d, r8d; State
0x1800620e8  xor     edx, edx; Type
0x1800620ea  lea     rcx, [rsp+108h+Event]; Event
0x1800620ef  call    cs:__imp_KeInitializeEvent
0x1800620f6  nop     dword ptr [rax+rax+00h]
0x1800620fb  lea     rax, [rsp+108h+Event]
0x180062100  mov     qword ptr [rsp+108h+pAsync.u], rax
0x180062108  mov     r8d, r15d
0x18006210b  mov     rdx, [rsp+108h+Binding]
0x180062110  lea     rcx, [rsp+108h+pAsync]
0x180062115  call    SSCatDBMpSmartLockerEnable
0x18006211a  jmp     short loc_180062127
0x18006211c  mov     ebx, eax
0x18006211e  mov     esi, [rsp+108h+var_D4]
0x180062122  mov     r15d, [rsp+108h+var_C0]
0x180062127  test    ebx, ebx
0x180062129  jnz     short loc_1800620C4
0x18006212b  mov     qword ptr [rsp+108h+Interval], 0FFFFFFFFFB3B4C00h
0x180062134  lea     rax, [rsp+108h+Interval]
0x180062139  mov     [rsp+108h+Timeout], rax; Timeout
0x18006213e  xor     r9d, r9d; Alertable
0x180062141  xor     r8d, r8d; WaitMode
0x180062144  xor     edx, edx; WaitReason
0x180062146  lea     rcx, [rsp+108h+Event]; Object
0x18006214b  call    cs:__imp_KeWaitForSingleObject
0x180062152  nop     dword ptr [rax+rax+00h]
0x180062157  mov     r14d, eax
0x18006215a  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18006215f  test    eax, eax
0x180062161  jz      short loc_1800621AF
0x180062163  lea     edx, [rbx+1]; fAbort
0x180062166  call    cs:__imp_RpcAsyncCancelCall
0x18006216d  nop     dword ptr [rax+rax+00h]
0x180062172  mov     [rsp+108h+Timeout], 0; Timeout
0x18006217b  xor     r9d, r9d; Alertable
0x18006217e  xor     r8d, r8d; WaitMode
0x180062181  xor     edx, edx; WaitReason
0x180062183  lea     rcx, [rsp+108h+Event]; Object
0x180062188  call    cs:__imp_KeWaitForSingleObject
0x18006218f  nop     dword ptr [rax+rax+00h]
0x180062194  lea     rdx, [rsp+108h+Reply]; Reply
0x180062199  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18006219e  call    cs:__imp_RpcAsyncCompleteCall
0x1800621a5  nop     dword ptr [rax+rax+00h]
0x1800621aa  jmp     loc_1800620C4
0x1800621af  lea     rdx, [rsp+108h+Reply]; Reply
0x1800621b4  call    cs:__imp_RpcAsyncCompleteCall
0x1800621bb  nop     dword ptr [rax+rax+00h]
0x1800621c0  cmp     eax, 0C0020018h
0x1800621c5  jnz     short loc_1800621F5
0x1800621c7  cmp     esi, 14h
0x1800621ca  jnb     short loc_1800621F5
0x1800621cc  inc     esi
0x1800621ce  mov     [rsp+108h+var_D4], esi
0x1800621d2  mov     qword ptr [rsp+108h+Interval], 0FFFFFFFFFFF0BDC0h
0x1800621db  lea     r8, [rsp+108h+Interval]; Interval
0x1800621e0  xor     edx, edx; Alertable
0x1800621e2  xor     ecx, ecx; WaitMode
0x1800621e4  call    cs:__imp_KeDelayExecutionThread
0x1800621eb  nop     dword ptr [rax+rax+00h]
0x1800621f0  jmp     loc_1800620A8
0x1800621f5  mov     ebx, 0C0000001h
0x1800621fa  test    eax, eax
0x1800621fc  jnz     short loc_180062209
0x1800621fe  cmp     [rsp+108h+Reply], eax
0x180062202  cmovnz  r14d, ebx
0x180062206  mov     ebx, r14d
0x180062209  cmp     [rsp+108h+Binding], 0
0x18006220f  jz      short loc_18006221B
0x180062211  lea     rcx, [rsp+108h+Binding]; Binding
0x180062216  call    CipCatDbRpcDisconnect
0x18006221b  mov     eax, ebx
0x18006221d  mov     rcx, [rsp+108h+var_38]
0x180062225  xor     rcx, rsp; StackCookie
0x180062228  call    __security_check_cookie
0x18006222d  add     rsp, 0E8h
0x180062234  pop     r15
0x180062236  pop     r14
0x180062238  pop     rsi
0x180062239  pop     rbx
0x18006223a  retn
0x1800ea4c5  push    rbp
0x1800ea4c7  sub     rsp, 30h
0x1800ea4cb  mov     rbp, rdx
0x1800ea4ce  mov     rcx, [rcx]
0x1800ea4d1  mov     ecx, [rcx]; ExceptionCode
0x1800ea4d3  call    cs:__imp_I_RpcExceptionFilter
0x1800ea4da  nop     dword ptr [rax+rax+00h]
0x1800ea4df  nop
0x1800ea4e0  add     rsp, 30h
0x1800ea4e4  pop     rbp
0x1800ea4e5  retn
```
