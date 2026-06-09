# CiCatDbSendSmartAppControlSwitchEnforceToast

- ea: `0x1800625fc`
- end: `0x18006280a`
- name: `CiCatDbSendSmartAppControlSwitchEnforceToast`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800739e0`

## callees

- `0x180020804`
- `0x18002c0d0`
- `0x18002c500`
- `0x1800625fc`
- `0x18009c3a4`
- `0x1800bba44`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x1800627aa`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800627aa`
- `ntoskrnl!KeInitializeEvent` at `0x1800626bd`
- `ntoskrnl!KeInitializeEvent` at `0x1800626bd`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062711`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006274e`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062711`
- `ntoskrnl!KeWaitForSingleObject` at `0x18006274e`
- `msrpc!RpcAsyncCancelCall` at `0x18006272c`
- `msrpc!RpcAsyncCancelCall` at `0x18006272c`
- `msrpc!RpcAsyncCompleteCall` at `0x180062764`
- `msrpc!RpcAsyncCompleteCall` at `0x18006277a`
- `msrpc!RpcAsyncCompleteCall` at `0x180062764`
- `msrpc!RpcAsyncCompleteCall` at `0x18006277a`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea4d3`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea4d3`
- `msrpc!RpcAsyncInitializeHandle` at `0x180062680`
- `msrpc!RpcAsyncInitializeHandle` at `0x180062680`

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
0x1800625fc  mov     [rsp+arg_0], rbx
0x180062601  mov     [rsp+arg_8], rsi
0x180062606  push    r14
0x180062608  sub     rsp, 0E0h
0x18006260f  mov     rax, cs:__security_cookie
0x180062616  xor     rax, rsp
0x180062619  mov     [rsp+0E8h+var_18], rax
0x180062621  xor     edx, edx; Val
0x180062623  lea     r8d, [rdx+58h]; Size
0x180062627  lea     rcx, [rsp+0E8h+pAsync]; void *
0x18006262c  call    memset
0x180062631  mov     [rsp+0E8h+Binding], 0
0x18006263a  xorps   xmm0, xmm0
0x18006263d  xor     eax, eax
0x18006263f  movups  xmmword ptr [rsp+0E8h+Event.Header], xmm0
0x180062644  mov     [rsp+0E8h+Event.Header.WaitListHead.Blink], rax
0x180062649  xor     esi, esi
0x18006264b  mov     [rsp+0E8h+var_B4], esi
0x18006264f  mov     qword ptr [rsp+0E8h+Interval], rax
0x180062654  mov     [rsp+0E8h+Reply], eax
0x180062658  mov     [rsp+0E8h+var_A0], rax
0x18006265d  lea     rdx, [rsp+0E8h+var_A0]
0x180062662  lea     rcx, [rsp+0E8h+Binding]
0x180062667  call    CipCatDbRpcConnect
0x18006266c  mov     ebx, eax
0x18006266e  test    eax, eax
0x180062670  js      loc_1800627CF
0x180062676  mov     edx, 58h ; 'X'; Size
0x18006267b  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180062680  call    cs:__imp_RpcAsyncInitializeHandle
0x180062687  nop     dword ptr [rax+rax+00h]
0x18006268c  mov     ebx, eax
0x18006268e  test    eax, eax
0x180062690  jz      short loc_18006269C
0x180062692  mov     ebx, 0C0000001h
0x180062697  jmp     loc_1800627CF
0x18006269c  mov     [rsp+0E8h+pAsync.UserInfo], 0
0x1800626a8  mov     [rsp+0E8h+pAsync.NotificationType], 1
0x1800626b3  xor     r8d, r8d; State
0x1800626b6  xor     edx, edx; Type
0x1800626b8  lea     rcx, [rsp+0E8h+Event]; Event
0x1800626bd  call    cs:__imp_KeInitializeEvent
0x1800626c4  nop     dword ptr [rax+rax+00h]
0x1800626c9  lea     rax, [rsp+0E8h+Event]
0x1800626ce  mov     qword ptr [rsp+0E8h+pAsync.u], rax
0x1800626d6  mov     rdx, [rsp+0E8h+Binding]
0x1800626db  lea     rcx, [rsp+0E8h+pAsync]
0x1800626e0  call    SSCatDBSendSmartAppControlSwitchEnforceToast
0x1800626e5  jmp     short loc_1800626ED
0x1800626e7  mov     ebx, eax
0x1800626e9  mov     esi, [rsp+0E8h+var_B4]
0x1800626ed  test    ebx, ebx
0x1800626ef  jnz     short loc_180062692
0x1800626f1  mov     qword ptr [rsp+0E8h+Interval], 0FFFFFFFFFB3B4C00h
0x1800626fa  lea     rax, [rsp+0E8h+Interval]
0x1800626ff  mov     [rsp+0E8h+Timeout], rax; Timeout
0x180062704  xor     r9d, r9d; Alertable
0x180062707  xor     r8d, r8d; WaitMode
0x18006270a  xor     edx, edx; WaitReason
0x18006270c  lea     rcx, [rsp+0E8h+Event]; Object
0x180062711  call    cs:__imp_KeWaitForSingleObject
0x180062718  nop     dword ptr [rax+rax+00h]
0x18006271d  mov     r14d, eax
0x180062720  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180062725  test    eax, eax
0x180062727  jz      short loc_180062775
0x180062729  lea     edx, [rbx+1]; fAbort
0x18006272c  call    cs:__imp_RpcAsyncCancelCall
0x180062733  nop     dword ptr [rax+rax+00h]
0x180062738  mov     [rsp+0E8h+Timeout], 0; Timeout
0x180062741  xor     r9d, r9d; Alertable
0x180062744  xor     r8d, r8d; WaitMode
0x180062747  xor     edx, edx; WaitReason
0x180062749  lea     rcx, [rsp+0E8h+Event]; Object
0x18006274e  call    cs:__imp_KeWaitForSingleObject
0x180062755  nop     dword ptr [rax+rax+00h]
0x18006275a  lea     rdx, [rsp+0E8h+Reply]; Reply
0x18006275f  lea     rcx, [rsp+0E8h+pAsync]; pAsync
0x180062764  call    cs:__imp_RpcAsyncCompleteCall
0x18006276b  nop     dword ptr [rax+rax+00h]
0x180062770  jmp     loc_180062692
0x180062775  lea     rdx, [rsp+0E8h+Reply]; Reply
0x18006277a  call    cs:__imp_RpcAsyncCompleteCall
0x180062781  nop     dword ptr [rax+rax+00h]
0x180062786  cmp     eax, 0C0020018h
0x18006278b  jnz     short loc_1800627BB
0x18006278d  cmp     esi, 14h
0x180062790  jnb     short loc_1800627BB
0x180062792  inc     esi
0x180062794  mov     [rsp+0E8h+var_B4], esi
0x180062798  mov     qword ptr [rsp+0E8h+Interval], 0FFFFFFFFFFF0BDC0h
0x1800627a1  lea     r8, [rsp+0E8h+Interval]; Interval
0x1800627a6  xor     edx, edx; Alertable
0x1800627a8  xor     ecx, ecx; WaitMode
0x1800627aa  call    cs:__imp_KeDelayExecutionThread
0x1800627b1  nop     dword ptr [rax+rax+00h]
0x1800627b6  jmp     loc_180062676
0x1800627bb  mov     ebx, 0C0000001h
0x1800627c0  test    eax, eax
0x1800627c2  jnz     short loc_1800627CF
0x1800627c4  cmp     [rsp+0E8h+Reply], eax
0x1800627c8  cmovnz  r14d, ebx
0x1800627cc  mov     ebx, r14d
0x1800627cf  cmp     [rsp+0E8h+Binding], 0
0x1800627d5  jz      short loc_1800627E1
0x1800627d7  lea     rcx, [rsp+0E8h+Binding]; Binding
0x1800627dc  call    CipCatDbRpcDisconnect
0x1800627e1  mov     eax, ebx
0x1800627e3  mov     rcx, [rsp+0E8h+var_18]
0x1800627eb  xor     rcx, rsp; StackCookie
0x1800627ee  call    __security_check_cookie
0x1800627f3  lea     r11, [rsp+0E8h+var_8]
0x1800627fb  mov     rbx, [r11+10h]
0x1800627ff  mov     rsi, [r11+18h]
0x180062803  mov     rsp, r11
0x180062806  pop     r14
0x180062808  retn
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
