# CiCatDbMpSmartLockerEnable

- ea: `0x180061684`
- end: `0x180061894`
- name: `CiCatDbMpSmartLockerEnable`
- size: `528`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180057408`
- `0x1800701b0`

## callees

- `0x1800206c0`
- `0x18002bef0`
- `0x18002c340`
- `0x180061684`
- `0x180089b2c`
- `0x1800ba724`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x18006183c`
- `ntoskrnl!KeDelayExecutionThread` at `0x18006183c`
- `ntoskrnl!KeInitializeEvent` at `0x180061747`
- `ntoskrnl!KeInitializeEvent` at `0x180061747`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800617a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800617e0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800617a3`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800617e0`
- `msrpc!RpcAsyncCancelCall` at `0x1800617be`
- `msrpc!RpcAsyncCancelCall` at `0x1800617be`
- `msrpc!RpcAsyncCompleteCall` at `0x1800617f6`
- `msrpc!RpcAsyncCompleteCall` at `0x18006180c`
- `msrpc!RpcAsyncCompleteCall` at `0x1800617f6`
- `msrpc!RpcAsyncCompleteCall` at `0x18006180c`
- `msrpc!RpcAsyncInitializeHandle` at `0x18006170a`
- `msrpc!RpcAsyncInitializeHandle` at `0x18006170a`

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
0x180061684  push    rbx
0x180061686  push    rsi
0x180061687  push    r14
0x180061689  push    r15
0x18006168b  sub     rsp, 0E8h
0x180061692  mov     rax, cs:__security_cookie
0x180061699  xor     rax, rsp
0x18006169c  mov     [rsp+108h+var_38], rax
0x1800616a4  mov     r15d, ecx
0x1800616a7  mov     [rsp+108h+var_C0], ecx
0x1800616ab  xor     edx, edx; Val
0x1800616ad  lea     r8d, [rdx+58h]; Size
0x1800616b1  lea     rcx, [rsp+108h+pAsync]; void *
0x1800616b6  call    memset
0x1800616bb  mov     [rsp+108h+Binding], 0
0x1800616c4  xorps   xmm0, xmm0
0x1800616c7  xor     eax, eax
0x1800616c9  movups  xmmword ptr [rsp+108h+Event.Header], xmm0
0x1800616ce  mov     [rsp+108h+Event.Header.WaitListHead.Blink], rax
0x1800616d3  xor     esi, esi
0x1800616d5  mov     [rsp+108h+var_D4], esi
0x1800616d9  mov     qword ptr [rsp+108h+Interval], rax
0x1800616de  mov     [rsp+108h+Reply], eax
0x1800616e2  mov     [rsp+108h+var_B8], rax
0x1800616e7  lea     rdx, [rsp+108h+var_B8]
0x1800616ec  lea     rcx, [rsp+108h+Binding]
0x1800616f1  call    CipCatDbRpcConnect
0x1800616f6  mov     ebx, eax
0x1800616f8  test    eax, eax
0x1800616fa  js      loc_180061861
0x180061700  mov     edx, 58h ; 'X'; Size
0x180061705  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18006170a  call    cs:__imp_RpcAsyncInitializeHandle
0x180061711  nop     dword ptr [rax+rax+00h]
0x180061716  mov     ebx, eax
0x180061718  test    eax, eax
0x18006171a  jz      short loc_180061726
0x18006171c  mov     ebx, 0C0000001h
0x180061721  jmp     loc_180061861
0x180061726  mov     [rsp+108h+pAsync.UserInfo], 0
0x180061732  mov     [rsp+108h+pAsync.NotificationType], 1
0x18006173d  xor     r8d, r8d; State
0x180061740  xor     edx, edx; Type
0x180061742  lea     rcx, [rsp+108h+Event]; Event
0x180061747  call    cs:__imp_KeInitializeEvent
0x18006174e  nop     dword ptr [rax+rax+00h]
0x180061753  lea     rax, [rsp+108h+Event]
0x180061758  mov     qword ptr [rsp+108h+pAsync.u], rax
0x180061760  mov     r8d, r15d
0x180061763  mov     rdx, [rsp+108h+Binding]
0x180061768  lea     rcx, [rsp+108h+pAsync]
0x18006176d  call    SSCatDBMpSmartLockerEnable
0x180061772  jmp     short loc_18006177F
0x180061774  mov     ebx, eax
0x180061776  mov     esi, [rsp+108h+var_D4]
0x18006177a  mov     r15d, [rsp+108h+var_C0]
0x18006177f  test    ebx, ebx
0x180061781  jnz     short loc_18006171C
0x180061783  mov     qword ptr [rsp+108h+Interval], 0FFFFFFFFFB3B4C00h
0x18006178c  lea     rax, [rsp+108h+Interval]
0x180061791  mov     [rsp+108h+Timeout], rax; Timeout
0x180061796  xor     r9d, r9d; Alertable
0x180061799  xor     r8d, r8d; WaitMode
0x18006179c  xor     edx, edx; WaitReason
0x18006179e  lea     rcx, [rsp+108h+Event]; Object
0x1800617a3  call    cs:__imp_KeWaitForSingleObject
0x1800617aa  nop     dword ptr [rax+rax+00h]
0x1800617af  mov     r14d, eax
0x1800617b2  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800617b7  test    eax, eax
0x1800617b9  jz      short loc_180061807
0x1800617bb  lea     edx, [rbx+1]; fAbort
0x1800617be  call    cs:__imp_RpcAsyncCancelCall
0x1800617c5  nop     dword ptr [rax+rax+00h]
0x1800617ca  mov     [rsp+108h+Timeout], 0; Timeout
0x1800617d3  xor     r9d, r9d; Alertable
0x1800617d6  xor     r8d, r8d; WaitMode
0x1800617d9  xor     edx, edx; WaitReason
0x1800617db  lea     rcx, [rsp+108h+Event]; Object
0x1800617e0  call    cs:__imp_KeWaitForSingleObject
0x1800617e7  nop     dword ptr [rax+rax+00h]
0x1800617ec  lea     rdx, [rsp+108h+Reply]; Reply
0x1800617f1  lea     rcx, [rsp+108h+pAsync]; pAsync
0x1800617f6  call    cs:__imp_RpcAsyncCompleteCall
0x1800617fd  nop     dword ptr [rax+rax+00h]
0x180061802  jmp     loc_18006171C
0x180061807  lea     rdx, [rsp+108h+Reply]; Reply
0x18006180c  call    cs:__imp_RpcAsyncCompleteCall
0x180061813  nop     dword ptr [rax+rax+00h]
0x180061818  cmp     eax, 0C0020018h
0x18006181d  jnz     short loc_18006184D
0x18006181f  cmp     esi, 14h
0x180061822  jnb     short loc_18006184D
0x180061824  inc     esi
0x180061826  mov     [rsp+108h+var_D4], esi
0x18006182a  mov     qword ptr [rsp+108h+Interval], 0FFFFFFFFFFF0BDC0h
0x180061833  lea     r8, [rsp+108h+Interval]; Interval
0x180061838  xor     edx, edx; Alertable
0x18006183a  xor     ecx, ecx; WaitMode
0x18006183c  call    cs:__imp_KeDelayExecutionThread
0x180061843  nop     dword ptr [rax+rax+00h]
0x180061848  jmp     loc_180061700
0x18006184d  mov     ebx, 0C0000001h
0x180061852  test    eax, eax
0x180061854  jnz     short loc_180061861
0x180061856  cmp     [rsp+108h+Reply], eax
0x18006185a  cmovnz  r14d, ebx
0x18006185e  mov     ebx, r14d
0x180061861  cmp     [rsp+108h+Binding], 0
0x180061867  jz      short loc_180061873
0x180061869  lea     rcx, [rsp+108h+Binding]; Binding
0x18006186e  call    CipCatDbRpcDisconnect
0x180061873  mov     eax, ebx
0x180061875  mov     rcx, [rsp+108h+var_38]
0x18006187d  xor     rcx, rsp; StackCookie
0x180061880  call    __security_check_cookie
0x180061885  add     rsp, 0E8h
0x18006188c  pop     r15
0x18006188e  pop     r14
0x180061890  pop     rsi
0x180061891  pop     rbx
0x180061892  retn
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
