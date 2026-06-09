# CiCatDbSendSmartAppControlSwitchEnforceToast

- ea: `0x180061c54`
- end: `0x180061e62`
- name: `CiCatDbSendSmartAppControlSwitchEnforceToast`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180072450`

## callees

- `0x1800207c4`
- `0x18002bef0`
- `0x18002c340`
- `0x180061c54`
- `0x180089b2c`
- `0x1800ba724`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x180061e02`
- `ntoskrnl!KeDelayExecutionThread` at `0x180061e02`
- `ntoskrnl!KeInitializeEvent` at `0x180061d15`
- `ntoskrnl!KeInitializeEvent` at `0x180061d15`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061d69`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061da6`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061d69`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061da6`
- `msrpc!RpcAsyncCancelCall` at `0x180061d84`
- `msrpc!RpcAsyncCancelCall` at `0x180061d84`
- `msrpc!RpcAsyncCompleteCall` at `0x180061dbc`
- `msrpc!RpcAsyncCompleteCall` at `0x180061dd2`
- `msrpc!RpcAsyncCompleteCall` at `0x180061dbc`
- `msrpc!RpcAsyncCompleteCall` at `0x180061dd2`
- `msrpc!I_RpcExceptionFilter` at `0x1800e848a`
- `msrpc!I_RpcExceptionFilter` at `0x1800e848a`
- `msrpc!RpcAsyncInitializeHandle` at `0x180061cd8`
- `msrpc!RpcAsyncInitializeHandle` at `0x180061cd8`

## pseudocode

```c
__int64 CiCatDbSendSmartAppControlSwitchEnforceToast()
{
  unsigned int v0; // esi
  int v1; // ebx
  RPC_STATUS v2; // ebx
  NTSTATUS v3; // r14d
  RPC_STATUS v4; // eax
  int Reply; // [rsp+30h] [rbp-B8h] BYREF
  unsigned int v7; // [rsp+34h] [rbp-B4h]
  union _LARGE_INTEGER Interval; // [rsp+38h] [rbp-B0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp-A8h] BYREF
  __int64 v10; // [rsp+48h] [rbp-A0h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-98h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-78h] BYREF

  memset(&pAsync, 0, sizeof(pAsync));
  Binding = 0;
  memset(&Event, 0, sizeof(Event));
  v0 = 0;
  v7 = 0;
  Interval.QuadPart = 0;
  Reply = 0;
  v10 = 0;
  v1 = CipCatDbRpcConnect(&Binding, &v10);
  if ( v1 >= 0 )
  {
    while ( 1 )
    {
      v2 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
      if ( v2 )
        goto LABEL_3;
      pAsync.UserInfo = 0;
      pAsync.NotificationType = RpcNotificationTypeEvent;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      pAsync.u.Event = &Event;
      SSCatDBSendSmartAppControlSwitchEnforceToast(&pAsync, Binding);
      Interval.QuadPart = -80000000;
      v3 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Interval);
      if ( v3 )
      {
        RpcAsyncCancelCall(&pAsync, v2 + 1);
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        RpcAsyncCompleteCall(&pAsync, &Reply);
LABEL_3:
        v1 = -1073741823;
        goto LABEL_13;
      }
      v4 = RpcAsyncCompleteCall(&pAsync, &Reply);
      if ( v4 != -1073610728 || v0 >= 0x14 )
        break;
      v7 = ++v0;
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    v1 = -1073741823;
    if ( !v4 )
    {
      if ( Reply )
        v3 = -1073741823;
      v1 = v3;
    }
  }
LABEL_13:
  if ( Binding )
    CipCatDbRpcDisconnect(&Binding);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x180061c54  mov     [rsp+arg_0], rbx
0x180061c59  mov     [rsp+arg_8], rsi
0x180061c5e  push    r14
0x180061c60  sub     rsp, 0E0h
0x180061c67  mov     rax, cs:__security_cookie
0x180061c6e  xor     rax, rsp
0x180061c71  mov     [rsp+0E8h+var_18], rax
0x180061c79  xor     edx, edx; Val
0x180061c7b  lea     r8d, [rdx+58h]; Size
0x180061c7f  lea     rcx, [rsp+0E8h+pAsync]; void *
0x180061c84  call    memset
0x180061c89  mov     [rsp+0E8h+Binding], 0
0x180061c92  xorps   xmm0, xmm0
0x180061c95  xor     eax, eax
0x180061c97  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm0
0x180061c9c  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x180061ca1  xor     esi, esi
0x180061ca3  mov     [rsp+0E8h+var_B4], esi
0x180061ca7  mov     qword ptr [rsp+0E8h+Interval], rax
0x180061cac  mov     [rsp+0E8h+Reply], eax
0x180061cb0  mov     [rsp+0E8h+var_A0], rax
0x180061cb5  lea     rdx, [rsp+0E8h+var_A0]
0x180061cba  lea     rcx, [rsp+0E8h+Binding]
0x180061cbf  call    CipCatDbRpcConnect
0x180061cc4  mov     ebx, eax
0x180061cc6  test    eax, eax
0x180061cc8  js      loc_180061E27
0x180061cce  mov     edx, 58h ; 'X'; Size
0x180061cd3  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180061cd8  call    cs:__imp_RpcAsyncInitializeHandle
0x180061cdf  nop     dword ptr [rax+rax+00h]
0x180061ce4  mov     ebx, eax
0x180061ce6  test    eax, eax
0x180061ce8  jz      short loc_180061CF4
0x180061cea  mov     ebx, 0C0000001h
0x180061cef  jmp     loc_180061E27
0x180061cf4  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x180061d00  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x180061d0b  xor     r8d, r8d; State
0x180061d0e  xor     edx, edx; Type
0x180061d10  lea     rcx, [rsp+0E8h+Event]; Event
0x180061d15  call    cs:__imp_KeInitializeEvent
0x180061d1c  nop     dword ptr [rax+rax+00h]
0x180061d21  lea     rax, [rsp+0E8h+Event]
0x180061d26  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x180061d2e  mov     rdx, [rsp+0E8h+Binding]
0x180061d33  lea     rcx, [rsp+0E8h+pAsync]
0x180061d38  call    SSCatDBSendSmartAppControlSwitchEnforceToast
0x180061d3d  jmp     short loc_180061D45
0x180061d3f  mov     ebx, eax
0x180061d41  mov     esi, [rsp+0E8h+var_B4]
0x180061d45  test    ebx, ebx
0x180061d47  jnz     short loc_180061CEA
0x180061d49  mov     qword ptr [rsp+0E8h+Interval], 0FFFFFFFFFB3B4C00h
0x180061d52  lea     rax, [rsp+0E8h+Interval]
0x180061d57  mov     [rsp+0E8h+Timeout], rax; Timeout
0x180061d5c  xor     r9d, r9d; Alertable
0x180061d5f  xor     r8d, r8d; WaitMode
0x180061d62  xor     edx, edx; WaitReason
0x180061d64  lea     rcx, [rsp+0E8h+Event]; Object
0x180061d69  call    cs:__imp_KeWaitForSingleObject
0x180061d70  nop     dword ptr [rax+rax+00h]
0x180061d75  mov     r14d, eax
0x180061d78  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180061d7d  test    eax, eax
0x180061d7f  jz      short loc_180061DCD
0x180061d81  lea     edx, [rbx+1]; fAbort
0x180061d84  call    cs:__imp_RpcAsyncCancelCall
0x180061d8b  nop     dword ptr [rax+rax+00h]
0x180061d90  mov     [rsp+0E8h+Timeout], 0; Timeout
0x180061d99  xor     r9d, r9d; Alertable
0x180061d9c  xor     r8d, r8d; WaitMode
0x180061d9f  xor     edx, edx; WaitReason
0x180061da1  lea     rcx, [rsp+0E8h+Event]; Object
0x180061da6  call    cs:__imp_KeWaitForSingleObject
0x180061dad  nop     dword ptr [rax+rax+00h]
0x180061db2  lea     rdx, [rsp+0E8h+Reply]; Reply
0x180061db7  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180061dbc  call    cs:__imp_RpcAsyncCompleteCall
0x180061dc3  nop     dword ptr [rax+rax+00h]
0x180061dc8  jmp     loc_180061CEA
0x180061dcd  lea     rdx, [rsp+0E8h+Reply]; Reply
0x180061dd2  call    cs:__imp_RpcAsyncCompleteCall
0x180061dd9  nop     dword ptr [rax+rax+00h]
0x180061dde  cmp     eax, 0C0020018h
0x180061de3  jnz     short loc_180061E13
0x180061de5  cmp     esi, 14h
0x180061de8  jnb     short loc_180061E13
0x180061dea  inc     esi
0x180061dec  mov     [rsp+0E8h+var_B4], esi
0x180061df0  mov     qword ptr [rsp+0E8h+Interval], 0FFFFFFFFFFF0BDC0h
0x180061df9  lea     r8, [rsp+0E8h+Interval]; Interval
0x180061dfe  xor     edx, edx; Alertable
0x180061e00  xor     ecx, ecx; WaitMode
0x180061e02  call    cs:__imp_KeDelayExecutionThread
0x180061e09  nop     dword ptr [rax+rax+00h]
0x180061e0e  jmp     loc_180061CCE
0x180061e13  mov     ebx, 0C0000001h
0x180061e18  test    eax, eax
0x180061e1a  jnz     short loc_180061E27
0x180061e1c  cmp     [rsp+0E8h+Reply], eax
0x180061e20  cmovnz  r14d, ebx
0x180061e24  mov     ebx, r14d
0x180061e27  cmp     [rsp+0E8h+Binding], 0
0x180061e2d  jz      short loc_180061E39
0x180061e2f  lea     rcx, [rsp+0E8h+Binding]; Binding
0x180061e34  call    CipCatDbRpcDisconnect
0x180061e39  mov     eax, ebx
0x180061e3b  mov     rcx, [rsp+0E8h+var_18]
0x180061e43  xor     rcx, rsp; StackCookie
0x180061e46  call    __security_check_cookie
0x180061e4b  lea     r11, [rsp+0E8h+var_8]
0x180061e53  mov     rbx, [r11+10h]
0x180061e57  mov     rsi, [r11+18h]
0x180061e5b  mov     rsp, r11
0x180061e5e  pop     r14
0x180061e60  retn
0x1800e847c  push    rbp
0x1800e847e  sub     rsp, 30h
0x1800e8482  mov     rbp, rdx
0x1800e8485  mov     rcx, [rcx]
0x1800e8488  mov     ecx, [rcx]; ExceptionCode
0x1800e848a  call    cs:__imp_I_RpcExceptionFilter
0x1800e8491  nop     dword ptr [rax+rax+00h]
0x1800e8496  nop
0x1800e8497  add     rsp, 30h
0x1800e849b  pop     rbp
0x1800e849c  retn
```
