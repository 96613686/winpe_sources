# CiCatDbSendSmartAppControlSwitchEnforceToast

- ea: `0x180062498`
- end: `0x1800626a6`
- name: `CiCatDbSendSmartAppControlSwitchEnforceToast`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180073700`

## callees

- `0x180020734`
- `0x18002bf20`
- `0x18002c380`
- `0x180062498`
- `0x18008b15c`
- `0x1800bbba4`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x180062646`
- `ntoskrnl!KeDelayExecutionThread` at `0x180062646`
- `ntoskrnl!KeInitializeEvent` at `0x180062559`
- `ntoskrnl!KeInitializeEvent` at `0x180062559`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800625ad`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800625ea`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800625ad`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800625ea`
- `msrpc!RpcAsyncCancelCall` at `0x1800625c8`
- `msrpc!RpcAsyncCancelCall` at `0x1800625c8`
- `msrpc!RpcAsyncCompleteCall` at `0x180062600`
- `msrpc!RpcAsyncCompleteCall` at `0x180062616`
- `msrpc!RpcAsyncCompleteCall` at `0x180062600`
- `msrpc!RpcAsyncCompleteCall` at `0x180062616`
- `msrpc!I_RpcExceptionFilter` at `0x1800e9c93`
- `msrpc!I_RpcExceptionFilter` at `0x1800e9c93`
- `msrpc!RpcAsyncInitializeHandle` at `0x18006251c`
- `msrpc!RpcAsyncInitializeHandle` at `0x18006251c`

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
0x180062498  mov     [rsp+arg_0], rbx
0x18006249d  mov     [rsp+arg_8], rsi
0x1800624a2  push    r14
0x1800624a4  sub     rsp, 0E0h
0x1800624ab  mov     rax, cs:__security_cookie
0x1800624b2  xor     rax, rsp
0x1800624b5  mov     [rsp+0E8h+var_18], rax
0x1800624bd  xor     edx, edx; Val
0x1800624bf  lea     r8d, [rdx+58h]; Size
0x1800624c3  lea     rcx, [rsp+0E8h+pAsync]; void *
0x1800624c8  call    memset
0x1800624cd  mov     [rsp+0E8h+Binding], 0
0x1800624d6  xorps   xmm0, xmm0
0x1800624d9  xor     eax, eax
0x1800624db  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm0
0x1800624e0  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x1800624e5  xor     esi, esi
0x1800624e7  mov     [rsp+0E8h+var_B4], esi
0x1800624eb  mov     qword ptr [rsp+0E8h+Interval], rax
0x1800624f0  mov     [rsp+0E8h+Reply], eax
0x1800624f4  mov     [rsp+0E8h+var_A0], rax
0x1800624f9  lea     rdx, [rsp+0E8h+var_A0]
0x1800624fe  lea     rcx, [rsp+0E8h+Binding]
0x180062503  call    CipCatDbRpcConnect
0x180062508  mov     ebx, eax
0x18006250a  test    eax, eax
0x18006250c  js      loc_18006266B
0x180062512  mov     edx, 58h ; 'X'; Size
0x180062517  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x18006251c  call    cs:__imp_RpcAsyncInitializeHandle
0x180062523  nop     dword ptr [rax+rax+00h]
0x180062528  mov     ebx, eax
0x18006252a  test    eax, eax
0x18006252c  jz      short loc_180062538
0x18006252e  mov     ebx, 0C0000001h
0x180062533  jmp     loc_18006266B
0x180062538  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x180062544  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x18006254f  xor     r8d, r8d; State
0x180062552  xor     edx, edx; Type
0x180062554  lea     rcx, [rsp+0E8h+Event]; Event
0x180062559  call    cs:__imp_KeInitializeEvent
0x180062560  nop     dword ptr [rax+rax+00h]
0x180062565  lea     rax, [rsp+0E8h+Event]
0x18006256a  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x180062572  mov     rdx, [rsp+0E8h+Binding]
0x180062577  lea     rcx, [rsp+0E8h+pAsync]
0x18006257c  call    SSCatDBSendSmartAppControlSwitchEnforceToast
0x180062581  jmp     short loc_180062589
0x180062583  mov     ebx, eax
0x180062585  mov     esi, [rsp+0E8h+var_B4]
0x180062589  test    ebx, ebx
0x18006258b  jnz     short loc_18006252E
0x18006258d  mov     qword ptr [rsp+0E8h+Interval], 0FFFFFFFFFB3B4C00h
0x180062596  lea     rax, [rsp+0E8h+Interval]
0x18006259b  mov     [rsp+0E8h+Timeout], rax; Timeout
0x1800625a0  xor     r9d, r9d; Alertable
0x1800625a3  xor     r8d, r8d; WaitMode
0x1800625a6  xor     edx, edx; WaitReason
0x1800625a8  lea     rcx, [rsp+0E8h+Event]; Object
0x1800625ad  call    cs:__imp_KeWaitForSingleObject
0x1800625b4  nop     dword ptr [rax+rax+00h]
0x1800625b9  mov     r14d, eax
0x1800625bc  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x1800625c1  test    eax, eax
0x1800625c3  jz      short loc_180062611
0x1800625c5  lea     edx, [rbx+1]; fAbort
0x1800625c8  call    cs:__imp_RpcAsyncCancelCall
0x1800625cf  nop     dword ptr [rax+rax+00h]
0x1800625d4  mov     [rsp+0E8h+Timeout], 0; Timeout
0x1800625dd  xor     r9d, r9d; Alertable
0x1800625e0  xor     r8d, r8d; WaitMode
0x1800625e3  xor     edx, edx; WaitReason
0x1800625e5  lea     rcx, [rsp+0E8h+Event]; Object
0x1800625ea  call    cs:__imp_KeWaitForSingleObject
0x1800625f1  nop     dword ptr [rax+rax+00h]
0x1800625f6  lea     rdx, [rsp+0E8h+Reply]; Reply
0x1800625fb  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180062600  call    cs:__imp_RpcAsyncCompleteCall
0x180062607  nop     dword ptr [rax+rax+00h]
0x18006260c  jmp     loc_18006252E
0x180062611  lea     rdx, [rsp+0E8h+Reply]; Reply
0x180062616  call    cs:__imp_RpcAsyncCompleteCall
0x18006261d  nop     dword ptr [rax+rax+00h]
0x180062622  cmp     eax, 0C0020018h
0x180062627  jnz     short loc_180062657
0x180062629  cmp     esi, 14h
0x18006262c  jnb     short loc_180062657
0x18006262e  inc     esi
0x180062630  mov     [rsp+0E8h+var_B4], esi
0x180062634  mov     qword ptr [rsp+0E8h+Interval], 0FFFFFFFFFFF0BDC0h
0x18006263d  lea     r8, [rsp+0E8h+Interval]; Interval
0x180062642  xor     edx, edx; Alertable
0x180062644  xor     ecx, ecx; WaitMode
0x180062646  call    cs:__imp_KeDelayExecutionThread
0x18006264d  nop     dword ptr [rax+rax+00h]
0x180062652  jmp     loc_180062512
0x180062657  mov     ebx, 0C0000001h
0x18006265c  test    eax, eax
0x18006265e  jnz     short loc_18006266B
0x180062660  cmp     [rsp+0E8h+Reply], eax
0x180062664  cmovnz  r14d, ebx
0x180062668  mov     ebx, r14d
0x18006266b  cmp     [rsp+0E8h+Binding], 0
0x180062671  jz      short loc_18006267D
0x180062673  lea     rcx, [rsp+0E8h+Binding]; Binding
0x180062678  call    CipCatDbRpcDisconnect
0x18006267d  mov     eax, ebx
0x18006267f  mov     rcx, [rsp+0E8h+var_18]
0x180062687  xor     rcx, rsp; StackCookie
0x18006268a  call    __security_check_cookie
0x18006268f  lea     r11, [rsp+0E8h+var_8]
0x180062697  mov     rbx, [r11+10h]
0x18006269b  mov     rsi, [r11+18h]
0x18006269f  mov     rsp, r11
0x1800626a2  pop     r14
0x1800626a4  retn
0x1800e9c85  push    rbp
0x1800e9c87  sub     rsp, 30h
0x1800e9c8b  mov     rbp, rdx
0x1800e9c8e  mov     rcx, [rcx]
0x1800e9c91  mov     ecx, [rcx]; ExceptionCode
0x1800e9c93  call    cs:__imp_I_RpcExceptionFilter
0x1800e9c9a  nop     dword ptr [rax+rax+00h]
0x1800e9c9f  nop
0x1800e9ca0  add     rsp, 30h
0x1800e9ca4  pop     rbp
0x1800e9ca5  retn
```
