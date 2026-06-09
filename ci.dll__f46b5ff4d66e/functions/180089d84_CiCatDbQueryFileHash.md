# CiCatDbQueryFileHash

- ea: `0x180089d84`
- end: `0x18008a0ef`
- name: `CiCatDbQueryFileHash`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008a63c`

## callees

- `0x18000ea60`
- `0x18002bef0`
- `0x18002c340`
- `0x180089b2c`
- `0x180089d84`
- `0x18008af40`
- `0x1800ba724`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x18008a050`
- `ntoskrnl!KeDelayExecutionThread` at `0x18008a050`
- `ntoskrnl!KeInitializeEvent` at `0x180089ed5`
- `ntoskrnl!KeInitializeEvent` at `0x180089ed5`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089f90`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089fe0`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089f90`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089fe0`
- `msrpc!RpcAsyncCancelCall` at `0x180089fb9`
- `msrpc!RpcAsyncCancelCall` at `0x180089fb9`
- `msrpc!RpcAsyncCompleteCall` at `0x18008a007`
- `msrpc!RpcAsyncCompleteCall` at `0x18008a01d`
- `msrpc!RpcAsyncCompleteCall` at `0x18008a007`
- `msrpc!RpcAsyncCompleteCall` at `0x18008a01d`
- `msrpc!I_RpcExceptionFilter` at `0x1800e7f66`
- `msrpc!I_RpcExceptionFilter` at `0x1800e7f66`
- `msrpc!RpcAsyncInitializeHandle` at `0x180089e8b`
- `msrpc!RpcAsyncInitializeHandle` at `0x180089e8b`

## pseudocode

```c
__int64 __fastcall CiCatDbQueryFileHash(int a1, __int64 a2, int a3, _DWORD *a4, PVOID *a5, _DWORD *a6)
{
  int v8; // ebx
  int v9; // r12d
  unsigned int v10; // r15d
  RPC_STATUS v11; // eax
  int v12; // r8d
  NTSTATUS v13; // eax
  RPC_STATUS v14; // ebx
  RPC_STATUS Reply; // [rsp+40h] [rbp-108h] BYREF
  _DWORD v17[2]; // [rsp+44h] [rbp-104h] BYREF
  unsigned int v18; // [rsp+4Ch] [rbp-FCh]
  union _LARGE_INTEGER Interval; // [rsp+50h] [rbp-F8h] BYREF
  PVOID P; // [rsp+58h] [rbp-F0h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-E8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-E0h]
  PVOID *v23; // [rsp+70h] [rbp-D8h]
  __int64 v24; // [rsp+78h] [rbp-D0h]
  _DWORD *v25; // [rsp+80h] [rbp-C8h]
  _DWORD *v26; // [rsp+88h] [rbp-C0h]
  struct _KEVENT Event; // [rsp+98h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+B0h] [rbp-98h] BYREF

  v22 = a2;
  v24 = a2;
  v25 = a4;
  v23 = a5;
  v26 = a6;
  memset(&pAsync, 0, sizeof(pAsync));
  Binding = 0;
  memset(&Event, 0, sizeof(Event));
  P = 0;
  v17[0] = 0;
  Interval.QuadPart = 0;
  Reply = 0;
  if ( a1 == 32772 )
  {
    v9 = 0;
  }
  else
  {
    if ( a1 != 32780 )
    {
      v8 = -1073741637;
      *a6 = 2;
      a6[1] = a1;
      goto LABEL_23;
    }
    v9 = 1;
  }
  v17[1] = v9;
  v10 = 0;
  v18 = 0;
  v8 = CipCatDbRpcConnect(&Binding, a6);
  if ( v8 >= 0 )
  {
    while ( 1 )
    {
      v11 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
      if ( v11 )
      {
        *a6 = 5;
        goto LABEL_9;
      }
      pAsync.UserInfo = 0;
      pAsync.NotificationType = RpcNotificationTypeEvent;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      pAsync.u.Event = &Event;
      SSCatDBEnumCatalogs((unsigned int)&pAsync, (_DWORD)Binding, v12, v9, a3, v22, (__int64)v17, (__int64)&P);
      Interval.QuadPart = -80000000;
      v13 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Interval);
      v8 = v13;
      if ( v13 )
      {
        *a6 = 7;
        a6[1] = v13;
        v14 = RpcAsyncCancelCall(&pAsync, 1);
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        if ( v14 )
        {
          *a6 = 16;
          a6[1] = v14;
        }
        RpcAsyncCompleteCall(&pAsync, &Reply);
        goto LABEL_10;
      }
      v11 = RpcAsyncCompleteCall(&pAsync, &Reply);
      if ( v11 != -1073610728 || v10 >= 0x14 )
        break;
      v18 = ++v10;
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    if ( v11 )
    {
      *a6 = 8;
      goto LABEL_9;
    }
    v11 = Reply;
    if ( Reply )
    {
      *a6 = 9;
LABEL_9:
      a6[1] = v11;
LABEL_10:
      v8 = -1073741823;
      goto LABEL_23;
    }
    *a4 = v17[0];
    *v23 = P;
    P = 0;
  }
LABEL_23:
  CiCatDbFreeListOfCatalogs(P);
  if ( Binding )
    CipCatDbRpcDisconnect(&Binding);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180089d84  mov     [rsp+arg_0], rbx
0x180089d89  mov     [rsp+arg_10], r8d
0x180089d8e  push    rsi
0x180089d8f  push    r12
0x180089d91  push    r13
0x180089d93  push    r14
0x180089d95  push    r15
0x180089d97  sub     rsp, 120h
0x180089d9e  mov     rax, cs:__security_cookie
0x180089da5  xor     rax, rsp
0x180089da8  mov     [rsp+148h+var_38], rax
0x180089db0  mov     r13, r9
0x180089db3  mov     [rsp+148h+var_E0], rdx
0x180089db8  mov     r15d, ecx
0x180089dbb  mov     r14, [rsp+148h+arg_28]
0x180089dc3  mov     [rsp+148h+var_D0], rdx
0x180089dc8  mov     [rsp+148h+var_C8], r9
0x180089dd0  mov     rax, [rsp+148h+arg_20]
0x180089dd8  mov     [rsp+148h+var_D8], rax
0x180089ddd  mov     rsi, r14
0x180089de0  mov     [rsp+148h+var_C0], r14
0x180089de8  xor     edx, edx; Val
0x180089dea  lea     r8d, [rdx+58h]; Size
0x180089dee  lea     rcx, [rsp+148h+pAsync]; void *
0x180089df6  call    memset
0x180089dfb  mov     [rsp+148h+Binding], 0
0x180089e04  xorps   xmm0, xmm0
0x180089e07  xor     eax, eax
0x180089e09  movups  xmmword ptr [rsp+148h+Event.Header], xmm0
0x180089e11  mov     [rsp+148h+Event.Header.WaitListHead.Blink], rax
0x180089e19  mov     [rsp+148h+P], rax
0x180089e1e  mov     [rsp+148h+var_104], eax
0x180089e22  mov     qword ptr [rsp+148h+Interval], rax
0x180089e27  mov     [rsp+148h+Reply], eax
0x180089e2b  mov     eax, r15d
0x180089e2e  sub     eax, 8004h
0x180089e33  jz      short loc_180089E57
0x180089e35  cmp     eax, 8
0x180089e38  jz      short loc_180089E4F
0x180089e3a  mov     ebx, 0C00000BBh
0x180089e3f  mov     dword ptr [r14], 2
0x180089e46  mov     [r14+4], r15d
0x180089e4a  jmp     loc_18008A0A3
0x180089e4f  mov     r12d, 1
0x180089e55  jmp     short loc_180089E5A
0x180089e57  xor     r12d, r12d
0x180089e5a  mov     [rsp+148h+var_100], r12d
0x180089e5f  xor     r15d, r15d
0x180089e62  mov     [rsp+148h+var_FC], r15d
0x180089e67  mov     rdx, r14
0x180089e6a  lea     rcx, [rsp+148h+Binding]
0x180089e6f  call    CipCatDbRpcConnect
0x180089e74  mov     ebx, eax
0x180089e76  test    eax, eax
0x180089e78  js      loc_18008A0A3
0x180089e7e  mov     edx, 58h ; 'X'; Size
0x180089e83  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180089e8b  call    cs:__imp_RpcAsyncInitializeHandle
0x180089e92  nop     dword ptr [rax+rax+00h]
0x180089e97  mov     ebx, eax
0x180089e99  test    eax, eax
0x180089e9b  jz      short loc_180089EB1
0x180089e9d  mov     dword ptr [r14], 5
0x180089ea4  mov     [rsi+4], eax
0x180089ea7  mov     ebx, 0C0000001h
0x180089eac  jmp     loc_18008A0A3
0x180089eb1  mov     [rsp+148h+pAsync.UserInfo], 0
0x180089ebd  mov     [rsp+148h+pAsync.NotificationType], 1
0x180089ec8  xor     r8d, r8d; State
0x180089ecb  xor     edx, edx; Type
0x180089ecd  lea     rcx, [rsp+148h+Event]; Event
0x180089ed5  call    cs:__imp_KeInitializeEvent
0x180089edc  nop     dword ptr [rax+rax+00h]
0x180089ee1  lea     rax, [rsp+148h+Event]
0x180089ee9  mov     qword ptr [rsp+148h+pAsync.u], rax
0x180089ef1  lea     rax, [rsp+148h+P]
0x180089ef6  mov     [rsp+148h+var_110], rax
0x180089efb  lea     rax, [rsp+148h+var_104]
0x180089f00  mov     [rsp+148h+var_118], rax
0x180089f05  mov     rax, [rsp+148h+var_E0]
0x180089f0a  mov     [rsp+148h+var_120], rax
0x180089f0f  mov     eax, [rsp+148h+arg_10]
0x180089f16  mov     dword ptr [rsp+148h+Timeout], eax
0x180089f1a  mov     r9d, r12d
0x180089f1d  mov     rdx, [rsp+148h+Binding]
0x180089f22  lea     rcx, [rsp+148h+pAsync]
0x180089f2a  call    SSCatDBEnumCatalogs
0x180089f2f  jmp     short loc_180089F5A
0x180089f31  mov     ebx, eax
0x180089f33  mov     r12d, [rsp+148h+var_100]
0x180089f38  mov     r15d, [rsp+148h+var_FC]
0x180089f3d  mov     rax, [rsp+148h+var_D0]
0x180089f42  mov     [rsp+148h+var_E0], rax
0x180089f47  mov     r13, [rsp+148h+var_C8]
0x180089f4f  mov     rsi, [rsp+148h+var_C0]
0x180089f57  mov     r14, rsi
0x180089f5a  test    ebx, ebx
0x180089f5c  jz      short loc_180089F6D
0x180089f5e  mov     dword ptr [r14], 6
0x180089f65  mov     [rsi+4], ebx
0x180089f68  jmp     loc_180089EA7
0x180089f6d  mov     qword ptr [rsp+148h+Interval], 0FFFFFFFFFB3B4C00h
0x180089f76  lea     rax, [rsp+148h+Interval]
0x180089f7b  mov     [rsp+148h+Timeout], rax; Timeout
0x180089f80  xor     r9d, r9d; Alertable
0x180089f83  xor     r8d, r8d; WaitMode
0x180089f86  xor     edx, edx; WaitReason
0x180089f88  lea     rcx, [rsp+148h+Event]; Object
0x180089f90  call    cs:__imp_KeWaitForSingleObject
0x180089f97  nop     dword ptr [rax+rax+00h]
0x180089f9c  mov     ebx, eax
0x180089f9e  lea     rcx, [rsp+148h+pAsync]; pAsync
0x180089fa6  test    eax, eax
0x180089fa8  jz      short loc_18008A018
0x180089faa  mov     dword ptr [r14], 7
0x180089fb1  mov     [rsi+4], eax
0x180089fb4  mov     edx, 1; fAbort
0x180089fb9  call    cs:__imp_RpcAsyncCancelCall
0x180089fc0  nop     dword ptr [rax+rax+00h]
0x180089fc5  mov     ebx, eax
0x180089fc7  mov     [rsp+148h+Timeout], 0; Timeout
0x180089fd0  xor     r9d, r9d; Alertable
0x180089fd3  xor     r8d, r8d; WaitMode
0x180089fd6  xor     edx, edx; WaitReason
0x180089fd8  lea     rcx, [rsp+148h+Event]; Object
0x180089fe0  call    cs:__imp_KeWaitForSingleObject
0x180089fe7  nop     dword ptr [rax+rax+00h]
0x180089fec  test    ebx, ebx
0x180089fee  jz      short loc_180089FFA
0x180089ff0  mov     dword ptr [r14], 10h
0x180089ff7  mov     [rsi+4], ebx
0x180089ffa  lea     rdx, [rsp+148h+Reply]; Reply
0x180089fff  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18008a007  call    cs:__imp_RpcAsyncCompleteCall
0x18008a00e  nop     dword ptr [rax+rax+00h]
0x18008a013  jmp     loc_180089EA7
0x18008a018  lea     rdx, [rsp+148h+Reply]; Reply
0x18008a01d  call    cs:__imp_RpcAsyncCompleteCall
0x18008a024  nop     dword ptr [rax+rax+00h]
0x18008a029  cmp     eax, 0C0020018h
0x18008a02e  jnz     short loc_18008A061
0x18008a030  cmp     r15d, 14h
0x18008a034  jnb     short loc_18008A061
0x18008a036  inc     r15d
0x18008a039  mov     [rsp+148h+var_FC], r15d
0x18008a03e  mov     qword ptr [rsp+148h+Interval], 0FFFFFFFFFFF0BDC0h
0x18008a047  lea     r8, [rsp+148h+Interval]; Interval
0x18008a04c  xor     edx, edx; Alertable
0x18008a04e  xor     ecx, ecx; WaitMode
0x18008a050  call    cs:__imp_KeDelayExecutionThread
0x18008a057  nop     dword ptr [rax+rax+00h]
0x18008a05c  jmp     loc_180089E7E
0x18008a061  test    eax, eax
0x18008a063  jz      short loc_18008A071
0x18008a065  mov     dword ptr [r14], 8
0x18008a06c  jmp     loc_180089EA4
0x18008a071  mov     eax, [rsp+148h+Reply]
0x18008a075  test    eax, eax
0x18008a077  jz      short loc_18008A085
0x18008a079  mov     dword ptr [r14], 9
0x18008a080  jmp     loc_180089EA4
0x18008a085  mov     eax, [rsp+148h+var_104]
0x18008a089  mov     [r13+0], eax
0x18008a08d  mov     rax, [rsp+148h+P]
0x18008a092  mov     rcx, [rsp+148h+var_D8]
0x18008a097  mov     [rcx], rax
0x18008a09a  mov     [rsp+148h+P], 0
0x18008a0a3  mov     edx, [rsp+148h+var_104]
0x18008a0a7  mov     rcx, [rsp+148h+P]; P
0x18008a0ac  call    CiCatDbFreeListOfCatalogs
0x18008a0b1  cmp     [rsp+148h+Binding], 0
0x18008a0b7  jz      short loc_18008A0C3
0x18008a0b9  lea     rcx, [rsp+148h+Binding]; Binding
0x18008a0be  call    CipCatDbRpcDisconnect
0x18008a0c3  mov     eax, ebx
0x18008a0c5  mov     rcx, [rsp+148h+var_38]
0x18008a0cd  xor     rcx, rsp; StackCookie
0x18008a0d0  call    __security_check_cookie
0x18008a0d5  mov     rbx, [rsp+148h+arg_0]
0x18008a0dd  add     rsp, 120h
0x18008a0e4  pop     r15
0x18008a0e6  pop     r14
0x18008a0e8  pop     r13
0x18008a0ea  pop     r12
0x18008a0ec  pop     rsi
0x18008a0ed  retn
0x1800e7f58  push    rbp
0x1800e7f5a  sub     rsp, 40h
0x1800e7f5e  mov     rbp, rdx
0x1800e7f61  mov     rcx, [rcx]
0x1800e7f64  mov     ecx, [rcx]; ExceptionCode
0x1800e7f66  call    cs:__imp_I_RpcExceptionFilter
0x1800e7f6d  nop     dword ptr [rax+rax+00h]
0x1800e7f72  nop
0x1800e7f73  add     rsp, 40h
0x1800e7f77  pop     rbp
0x1800e7f78  retn
```
