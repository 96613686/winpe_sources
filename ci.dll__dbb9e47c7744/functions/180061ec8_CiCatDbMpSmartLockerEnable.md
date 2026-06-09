# CiCatDbMpSmartLockerEnable

- ea: `0x180061ec8`
- end: `0x1800620d8`
- name: `CiCatDbMpSmartLockerEnable`
- size: `528`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180058120`
- `0x180071460`

## callees

- `0x180020630`
- `0x18002bf20`
- `0x18002c380`
- `0x180061ec8`
- `0x18008b15c`
- `0x1800bbba4`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x180062080`
- `ntoskrnl!KeDelayExecutionThread` at `0x180062080`
- `ntoskrnl!KeInitializeEvent` at `0x180061f8b`
- `ntoskrnl!KeInitializeEvent` at `0x180061f8b`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061fe7`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062024`
- `ntoskrnl!KeWaitForSingleObject` at `0x180061fe7`
- `ntoskrnl!KeWaitForSingleObject` at `0x180062024`
- `msrpc!RpcAsyncCancelCall` at `0x180062002`
- `msrpc!RpcAsyncCancelCall` at `0x180062002`
- `msrpc!RpcAsyncCompleteCall` at `0x18006203a`
- `msrpc!RpcAsyncCompleteCall` at `0x180062050`
- `msrpc!RpcAsyncCompleteCall` at `0x18006203a`
- `msrpc!RpcAsyncCompleteCall` at `0x180062050`
- `msrpc!RpcAsyncInitializeHandle` at `0x180061f4e`
- `msrpc!RpcAsyncInitializeHandle` at `0x180061f4e`

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
0x180061ec8  push    rbx
0x180061eca  push    rsi
0x180061ecb  push    r14
0x180061ecd  push    r15
0x180061ecf  sub     rsp, 0E8h
0x180061ed6  mov     rax, cs:__security_cookie
0x180061edd  xor     rax, rsp
0x180061ee0  mov     [rsp+108h+var_38], rax
0x180061ee8  mov     r15d, ecx
0x180061eeb  mov     [rsp+108h+var_C0], ecx
0x180061eef  xor     edx, edx; Val
0x180061ef1  lea     r8d, [rdx+58h]; Size
0x180061ef5  lea     rcx, [rsp+108h+pAsync]; void *
0x180061efa  call    memset
0x180061eff  mov     [rsp+108h+Binding], 0
0x180061f08  xorps   xmm0, xmm0
0x180061f0b  xor     eax, eax
0x180061f0d  movups  xmmword ptr [rsp+108h+Event.Header], xmm0
0x180061f12  mov     [rsp+108h+Event.Header.WaitListHead.Blink], rax
0x180061f17  xor     esi, esi
0x180061f19  mov     [rsp+108h+var_D4], esi
0x180061f1d  mov     qword ptr [rsp+108h+Interval], rax
0x180061f22  mov     [rsp+108h+Reply], eax
0x180061f26  mov     [rsp+108h+var_B8], rax
0x180061f2b  lea     rdx, [rsp+108h+var_B8]
0x180061f30  lea     rcx, [rsp+108h+Binding]
0x180061f35  call    CipCatDbRpcConnect
0x180061f3a  mov     ebx, eax
0x180061f3c  test    eax, eax
0x180061f3e  js      loc_1800620A5
0x180061f44  mov     edx, 58h ; 'X'; Size
0x180061f49  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180061f4e  call    cs:__imp_RpcAsyncInitializeHandle
0x180061f55  nop     dword ptr [rax+rax+00h]
0x180061f5a  mov     ebx, eax
0x180061f5c  test    eax, eax
0x180061f5e  jz      short loc_180061F6A
0x180061f60  mov     ebx, 0C0000001h
0x180061f65  jmp     loc_1800620A5
0x180061f6a  mov     [rsp+108h+pAsync.UserInfo], 0
0x180061f76  mov     [rsp+108h+pAsync.NotificationType], 1
0x180061f81  xor     r8d, r8d; State
0x180061f84  xor     edx, edx; Type
0x180061f86  lea     rcx, [rsp+108h+Event]; Event
0x180061f8b  call    cs:__imp_KeInitializeEvent
0x180061f92  nop     dword ptr [rax+rax+00h]
0x180061f97  lea     rax, [rsp+108h+Event]
0x180061f9c  mov     qword ptr [rsp+108h+pAsync.u], rax
0x180061fa4  mov     r8d, r15d
0x180061fa7  mov     rdx, [rsp+108h+Binding]
0x180061fac  lea     rcx, [rsp+108h+pAsync]
0x180061fb1  call    SSCatDBMpSmartLockerEnable
0x180061fb6  jmp     short loc_180061FC3
0x180061fb8  mov     ebx, eax
0x180061fba  mov     esi, [rsp+108h+var_D4]
0x180061fbe  mov     r15d, [rsp+108h+var_C0]
0x180061fc3  test    ebx, ebx
0x180061fc5  jnz     short loc_180061F60
0x180061fc7  mov     qword ptr [rsp+108h+Interval], 0FFFFFFFFFB3B4C00h
0x180061fd0  lea     rax, [rsp+108h+Interval]
0x180061fd5  mov     [rsp+108h+Timeout], rax; Timeout
0x180061fda  xor     r9d, r9d; Alertable
0x180061fdd  xor     r8d, r8d; WaitMode
0x180061fe0  xor     edx, edx; WaitReason
0x180061fe2  lea     rcx, [rsp+108h+Event]; Object
0x180061fe7  call    cs:__imp_KeWaitForSingleObject
0x180061fee  nop     dword ptr [rax+rax+00h]
0x180061ff3  mov     r14d, eax
0x180061ff6  lea     rcx, [rsp+108h+pAsync]; pAsync
0x180061ffb  test    eax, eax
0x180061ffd  jz      short loc_18006204B
0x180061fff  lea     edx, [rbx+1]; fAbort
0x180062002  call    cs:__imp_RpcAsyncCancelCall
0x180062009  nop     dword ptr [rax+rax+00h]
0x18006200e  mov     [rsp+108h+Timeout], 0; Timeout
0x180062017  xor     r9d, r9d; Alertable
0x18006201a  xor     r8d, r8d; WaitMode
0x18006201d  xor     edx, edx; WaitReason
0x18006201f  lea     rcx, [rsp+108h+Event]; Object
0x180062024  call    cs:__imp_KeWaitForSingleObject
0x18006202b  nop     dword ptr [rax+rax+00h]
0x180062030  lea     rdx, [rsp+108h+Reply]; Reply
0x180062035  lea     rcx, [rsp+108h+pAsync]; pAsync
0x18006203a  call    cs:__imp_RpcAsyncCompleteCall
0x180062041  nop     dword ptr [rax+rax+00h]
0x180062046  jmp     loc_180061F60
0x18006204b  lea     rdx, [rsp+108h+Reply]; Reply
0x180062050  call    cs:__imp_RpcAsyncCompleteCall
0x180062057  nop     dword ptr [rax+rax+00h]
0x18006205c  cmp     eax, 0C0020018h
0x180062061  jnz     short loc_180062091
0x180062063  cmp     esi, 14h
0x180062066  jnb     short loc_180062091
0x180062068  inc     esi
0x18006206a  mov     [rsp+108h+var_D4], esi
0x18006206e  mov     qword ptr [rsp+108h+Interval], 0FFFFFFFFFFF0BDC0h
0x180062077  lea     r8, [rsp+108h+Interval]; Interval
0x18006207c  xor     edx, edx; Alertable
0x18006207e  xor     ecx, ecx; WaitMode
0x180062080  call    cs:__imp_KeDelayExecutionThread
0x180062087  nop     dword ptr [rax+rax+00h]
0x18006208c  jmp     loc_180061F44
0x180062091  mov     ebx, 0C0000001h
0x180062096  test    eax, eax
0x180062098  jnz     short loc_1800620A5
0x18006209a  cmp     [rsp+108h+Reply], eax
0x18006209e  cmovnz  r14d, ebx
0x1800620a2  mov     ebx, r14d
0x1800620a5  cmp     [rsp+108h+Binding], 0
0x1800620ab  jz      short loc_1800620B7
0x1800620ad  lea     rcx, [rsp+108h+Binding]; Binding
0x1800620b2  call    CipCatDbRpcDisconnect
0x1800620b7  mov     eax, ebx
0x1800620b9  mov     rcx, [rsp+108h+var_38]
0x1800620c1  xor     rcx, rsp; StackCookie
0x1800620c4  call    __security_check_cookie
0x1800620c9  add     rsp, 0E8h
0x1800620d0  pop     r15
0x1800620d2  pop     r14
0x1800620d4  pop     rsi
0x1800620d5  pop     rbx
0x1800620d6  retn
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
