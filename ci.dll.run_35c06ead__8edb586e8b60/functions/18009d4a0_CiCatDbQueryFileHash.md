# CiCatDbQueryFileHash

- ea: `0x18009d4a0`
- end: `0x18009d80b`
- name: `CiCatDbQueryFileHash`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18009cb40`

## callees

- `0x18000ea70`
- `0x18002c0d0`
- `0x18002c500`
- `0x18009c3a4`
- `0x18009d444`
- `0x18009d4a0`
- `0x1800bba44`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x18009d76c`
- `ntoskrnl!KeDelayExecutionThread` at `0x18009d76c`
- `ntoskrnl!KeInitializeEvent` at `0x18009d5f1`
- `ntoskrnl!KeInitializeEvent` at `0x18009d5f1`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009d6ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009d6fc`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009d6ac`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009d6fc`
- `msrpc!RpcAsyncCancelCall` at `0x18009d6d5`
- `msrpc!RpcAsyncCancelCall` at `0x18009d6d5`
- `msrpc!RpcAsyncCompleteCall` at `0x18009d723`
- `msrpc!RpcAsyncCompleteCall` at `0x18009d739`
- `msrpc!RpcAsyncCompleteCall` at `0x18009d723`
- `msrpc!RpcAsyncCompleteCall` at `0x18009d739`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea2c8`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea2c8`
- `msrpc!RpcAsyncInitializeHandle` at `0x18009d5a7`
- `msrpc!RpcAsyncInitializeHandle` at `0x18009d5a7`

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
0x18009d4a0  mov     [rsp+arg_0], rbx
0x18009d4a5  mov     [rsp+arg_10], r8d
0x18009d4aa  push    rsi
0x18009d4ab  push    r12
0x18009d4ad  push    r13
0x18009d4af  push    r14
0x18009d4b1  push    r15
0x18009d4b3  sub     rsp, 120h
0x18009d4ba  mov     rax, cs:__security_cookie
0x18009d4c1  xor     rax, rsp
0x18009d4c4  mov     [rsp+148h+var_38], rax
0x18009d4cc  mov     r13, r9
0x18009d4cf  mov     [rsp+148h+var_E0], rdx
0x18009d4d4  mov     r15d, ecx
0x18009d4d7  mov     r14, [rsp+148h+arg_28]
0x18009d4df  mov     [rsp+148h+var_D0], rdx
0x18009d4e4  mov     [rsp+148h+var_C8], r9
0x18009d4ec  mov     rax, [rsp+148h+arg_20]
0x18009d4f4  mov     [rsp+148h+var_D8], rax
0x18009d4f9  mov     rsi, r14
0x18009d4fc  mov     [rsp+148h+var_C0], r14
0x18009d504  xor     edx, edx; Val
0x18009d506  lea     r8d, [rdx+58h]; Size
0x18009d50a  lea     rcx, [rsp+148h+pAsync]; void *
0x18009d512  call    memset
0x18009d517  mov     [rsp+148h+Binding], 0
0x18009d520  xorps   xmm0, xmm0
0x18009d523  xor     eax, eax
0x18009d525  movups  xmmword ptr [rsp+148h+Event.Header], xmm0
0x18009d52d  mov     [rsp+148h+Event.Header.WaitListHead.Blink], rax
0x18009d535  mov     [rsp+148h+P], rax
0x18009d53a  mov     [rsp+148h+var_104], eax
0x18009d53e  mov     qword ptr [rsp+148h+Interval], rax
0x18009d543  mov     [rsp+148h+Reply], eax
0x18009d547  mov     eax, r15d
0x18009d54a  sub     eax, 8004h
0x18009d54f  jz      short loc_18009D573
0x18009d551  cmp     eax, 8
0x18009d554  jz      short loc_18009D56B
0x18009d556  mov     ebx, 0C00000BBh
0x18009d55b  mov     dword ptr [r14], 2
0x18009d562  mov     [r14+4], r15d
0x18009d566  jmp     loc_18009D7BF
0x18009d56b  mov     r12d, 1
0x18009d571  jmp     short loc_18009D576
0x18009d573  xor     r12d, r12d
0x18009d576  mov     [rsp+148h+var_100], r12d
0x18009d57b  xor     r15d, r15d
0x18009d57e  mov     [rsp+148h+var_FC], r15d
0x18009d583  mov     rdx, r14
0x18009d586  lea     rcx, [rsp+148h+Binding]
0x18009d58b  call    CipCatDbRpcConnect
0x18009d590  mov     ebx, eax
0x18009d592  test    eax, eax
0x18009d594  js      loc_18009D7BF
0x18009d59a  mov     edx, 58h ; 'X'; Size
0x18009d59f  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18009d5a7  call    cs:__imp_RpcAsyncInitializeHandle
0x18009d5ae  nop     dword ptr [rax+rax+00h]
0x18009d5b3  mov     ebx, eax
0x18009d5b5  test    eax, eax
0x18009d5b7  jz      short loc_18009D5CD
0x18009d5b9  mov     dword ptr [r14], 5
0x18009d5c0  mov     [rsi+4], eax
0x18009d5c3  mov     ebx, 0C0000001h
0x18009d5c8  jmp     loc_18009D7BF
0x18009d5cd  mov     [rsp+148h+pAsync.UserInfo], 0
0x18009d5d9  mov     [rsp+148h+pAsync.NotificationType], 1
0x18009d5e4  xor     r8d, r8d; State
0x18009d5e7  xor     edx, edx; Type
0x18009d5e9  lea     rcx, [rsp+148h+Event]; Event
0x18009d5f1  call    cs:__imp_KeInitializeEvent
0x18009d5f8  nop     dword ptr [rax+rax+00h]
0x18009d5fd  lea     rax, [rsp+148h+Event]
0x18009d605  mov     qword ptr [rsp+148h+pAsync.u], rax
0x18009d60d  lea     rax, [rsp+148h+P]
0x18009d612  mov     [rsp+148h+var_110], rax
0x18009d617  lea     rax, [rsp+148h+var_104]
0x18009d61c  mov     [rsp+148h+var_118], rax
0x18009d621  mov     rax, [rsp+148h+var_E0]
0x18009d626  mov     [rsp+148h+var_120], rax
0x18009d62b  mov     eax, [rsp+148h+arg_10]
0x18009d632  mov     dword ptr [rsp+148h+Timeout], eax
0x18009d636  mov     r9d, r12d
0x18009d639  mov     rdx, [rsp+148h+Binding]
0x18009d63e  lea     rcx, [rsp+148h+pAsync]
0x18009d646  call    SSCatDBEnumCatalogs
0x18009d64b  jmp     short loc_18009D676
0x18009d64d  mov     ebx, eax
0x18009d64f  mov     r12d, [rsp+148h+var_100]
0x18009d654  mov     r15d, [rsp+148h+var_FC]
0x18009d659  mov     rax, [rsp+148h+var_D0]
0x18009d65e  mov     [rsp+148h+var_E0], rax
0x18009d663  mov     r13, [rsp+148h+var_C8]
0x18009d66b  mov     rsi, [rsp+148h+var_C0]
0x18009d673  mov     r14, rsi
0x18009d676  test    ebx, ebx
0x18009d678  jz      short loc_18009D689
0x18009d67a  mov     dword ptr [r14], 6
0x18009d681  mov     [rsi+4], ebx
0x18009d684  jmp     loc_18009D5C3
0x18009d689  mov     qword ptr [rsp+148h+Interval], 0FFFFFFFFFB3B4C00h
0x18009d692  lea     rax, [rsp+148h+Interval]
0x18009d697  mov     [rsp+148h+Timeout], rax; Timeout
0x18009d69c  xor     r9d, r9d; Alertable
0x18009d69f  xor     r8d, r8d; WaitMode
0x18009d6a2  xor     edx, edx; WaitReason
0x18009d6a4  lea     rcx, [rsp+148h+Event]; Object
0x18009d6ac  call    cs:__imp_KeWaitForSingleObject
0x18009d6b3  nop     dword ptr [rax+rax+00h]
0x18009d6b8  mov     ebx, eax
0x18009d6ba  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18009d6c2  test    eax, eax
0x18009d6c4  jz      short loc_18009D734
0x18009d6c6  mov     dword ptr [r14], 7
0x18009d6cd  mov     [rsi+4], eax
0x18009d6d0  mov     edx, 1; fAbort
0x18009d6d5  call    cs:__imp_RpcAsyncCancelCall
0x18009d6dc  nop     dword ptr [rax+rax+00h]
0x18009d6e1  mov     ebx, eax
0x18009d6e3  mov     [rsp+148h+Timeout], 0; Timeout
0x18009d6ec  xor     r9d, r9d; Alertable
0x18009d6ef  xor     r8d, r8d; WaitMode
0x18009d6f2  xor     edx, edx; WaitReason
0x18009d6f4  lea     rcx, [rsp+148h+Event]; Object
0x18009d6fc  call    cs:__imp_KeWaitForSingleObject
0x18009d703  nop     dword ptr [rax+rax+00h]
0x18009d708  test    ebx, ebx
0x18009d70a  jz      short loc_18009D716
0x18009d70c  mov     dword ptr [r14], 10h
0x18009d713  mov     [rsi+4], ebx
0x18009d716  lea     rdx, [rsp+148h+Reply]; Reply
0x18009d71b  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18009d723  call    cs:__imp_RpcAsyncCompleteCall
0x18009d72a  nop     dword ptr [rax+rax+00h]
0x18009d72f  jmp     loc_18009D5C3
0x18009d734  lea     rdx, [rsp+148h+Reply]; Reply
0x18009d739  call    cs:__imp_RpcAsyncCompleteCall
0x18009d740  nop     dword ptr [rax+rax+00h]
0x18009d745  cmp     eax, 0C0020018h
0x18009d74a  jnz     short loc_18009D77D
0x18009d74c  cmp     r15d, 14h
0x18009d750  jnb     short loc_18009D77D
0x18009d752  inc     r15d
0x18009d755  mov     [rsp+148h+var_FC], r15d
0x18009d75a  mov     qword ptr [rsp+148h+Interval], 0FFFFFFFFFFF0BDC0h
0x18009d763  lea     r8, [rsp+148h+Interval]; Interval
0x18009d768  xor     edx, edx; Alertable
0x18009d76a  xor     ecx, ecx; WaitMode
0x18009d76c  call    cs:__imp_KeDelayExecutionThread
0x18009d773  nop     dword ptr [rax+rax+00h]
0x18009d778  jmp     loc_18009D59A
0x18009d77d  test    eax, eax
0x18009d77f  jz      short loc_18009D78D
0x18009d781  mov     dword ptr [r14], 8
0x18009d788  jmp     loc_18009D5C0
0x18009d78d  mov     eax, [rsp+148h+Reply]
0x18009d791  test    eax, eax
0x18009d793  jz      short loc_18009D7A1
0x18009d795  mov     dword ptr [r14], 9
0x18009d79c  jmp     loc_18009D5C0
0x18009d7a1  mov     eax, [rsp+148h+var_104]
0x18009d7a5  mov     [r13+0], eax
0x18009d7a9  mov     rax, [rsp+148h+P]
0x18009d7ae  mov     rcx, [rsp+148h+var_D8]
0x18009d7b3  mov     [rcx], rax
0x18009d7b6  mov     [rsp+148h+P], 0
0x18009d7bf  mov     edx, [rsp+148h+var_104]
0x18009d7c3  mov     rcx, [rsp+148h+P]; P
0x18009d7c8  call    CiCatDbFreeListOfCatalogs
0x18009d7cd  cmp     [rsp+148h+Binding], 0
0x18009d7d3  jz      short loc_18009D7DF
0x18009d7d5  lea     rcx, [rsp+148h+Binding]; Binding
0x18009d7da  call    CipCatDbRpcDisconnect
0x18009d7df  mov     eax, ebx
0x18009d7e1  mov     rcx, [rsp+148h+var_38]
0x18009d7e9  xor     rcx, rsp; StackCookie
0x18009d7ec  call    __security_check_cookie
0x18009d7f1  mov     rbx, [rsp+148h+arg_0]
0x18009d7f9  add     rsp, 120h
0x18009d800  pop     r15
0x18009d802  pop     r14
0x18009d804  pop     r13
0x18009d806  pop     r12
0x18009d808  pop     rsi
0x18009d809  retn
0x1800ea2ba  push    rbp
0x1800ea2bc  sub     rsp, 40h
0x1800ea2c0  mov     rbp, rdx
0x1800ea2c3  mov     rcx, [rcx]
0x1800ea2c6  mov     ecx, [rcx]; ExceptionCode
0x1800ea2c8  call    cs:__imp_I_RpcExceptionFilter
0x1800ea2cf  nop     dword ptr [rax+rax+00h]
0x1800ea2d4  nop
0x1800ea2d5  add     rsp, 40h
0x1800ea2d9  pop     rbp
0x1800ea2da  retn
```
