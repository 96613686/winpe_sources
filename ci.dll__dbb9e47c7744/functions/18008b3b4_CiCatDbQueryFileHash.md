# CiCatDbQueryFileHash

- ea: `0x18008b3b4`
- end: `0x18008b71f`
- name: `CiCatDbQueryFileHash`
- size: `875`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18008bc6c`

## callees

- `0x18000ea60`
- `0x18002bf20`
- `0x18002c380`
- `0x18008b15c`
- `0x18008b3b4`
- `0x18008c570`
- `0x1800bbba4`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x18008b680`
- `ntoskrnl!KeDelayExecutionThread` at `0x18008b680`
- `ntoskrnl!KeInitializeEvent` at `0x18008b505`
- `ntoskrnl!KeInitializeEvent` at `0x18008b505`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008b5c0`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008b610`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008b5c0`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008b610`
- `msrpc!RpcAsyncCancelCall` at `0x18008b5e9`
- `msrpc!RpcAsyncCancelCall` at `0x18008b5e9`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b637`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b64d`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b637`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b64d`
- `msrpc!I_RpcExceptionFilter` at `0x1800e9706`
- `msrpc!I_RpcExceptionFilter` at `0x1800e9706`
- `msrpc!RpcAsyncInitializeHandle` at `0x18008b4bb`
- `msrpc!RpcAsyncInitializeHandle` at `0x18008b4bb`

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
0x18008b3b4  mov     [rsp+arg_0], rbx
0x18008b3b9  mov     [rsp+arg_10], r8d
0x18008b3be  push    rsi
0x18008b3bf  push    r12
0x18008b3c1  push    r13
0x18008b3c3  push    r14
0x18008b3c5  push    r15
0x18008b3c7  sub     rsp, 120h
0x18008b3ce  mov     rax, cs:__security_cookie
0x18008b3d5  xor     rax, rsp
0x18008b3d8  mov     [rsp+148h+var_38], rax
0x18008b3e0  mov     r13, r9
0x18008b3e3  mov     [rsp+148h+var_E0], rdx
0x18008b3e8  mov     r15d, ecx
0x18008b3eb  mov     r14, [rsp+148h+arg_28]
0x18008b3f3  mov     [rsp+148h+var_D0], rdx
0x18008b3f8  mov     [rsp+148h+var_C8], r9
0x18008b400  mov     rax, [rsp+148h+arg_20]
0x18008b408  mov     [rsp+148h+var_D8], rax
0x18008b40d  mov     rsi, r14
0x18008b410  mov     [rsp+148h+var_C0], r14
0x18008b418  xor     edx, edx; Val
0x18008b41a  lea     r8d, [rdx+58h]; Size
0x18008b41e  lea     rcx, [rsp+148h+pAsync]; void *
0x18008b426  call    memset
0x18008b42b  mov     [rsp+148h+Binding], 0
0x18008b434  xorps   xmm0, xmm0
0x18008b437  xor     eax, eax
0x18008b439  movups  xmmword ptr [rsp+148h+Event.Header], xmm0
0x18008b441  mov     [rsp+148h+Event.Header.WaitListHead.Blink], rax
0x18008b449  mov     [rsp+148h+P], rax
0x18008b44e  mov     [rsp+148h+var_104], eax
0x18008b452  mov     qword ptr [rsp+148h+Interval], rax
0x18008b457  mov     [rsp+148h+Reply], eax
0x18008b45b  mov     eax, r15d
0x18008b45e  sub     eax, 8004h
0x18008b463  jz      short loc_18008B487
0x18008b465  cmp     eax, 8
0x18008b468  jz      short loc_18008B47F
0x18008b46a  mov     ebx, 0C00000BBh
0x18008b46f  mov     dword ptr [r14], 2
0x18008b476  mov     [r14+4], r15d
0x18008b47a  jmp     loc_18008B6D3
0x18008b47f  mov     r12d, 1
0x18008b485  jmp     short loc_18008B48A
0x18008b487  xor     r12d, r12d
0x18008b48a  mov     [rsp+148h+var_100], r12d
0x18008b48f  xor     r15d, r15d
0x18008b492  mov     [rsp+148h+var_FC], r15d
0x18008b497  mov     rdx, r14
0x18008b49a  lea     rcx, [rsp+148h+Binding]
0x18008b49f  call    CipCatDbRpcConnect
0x18008b4a4  mov     ebx, eax
0x18008b4a6  test    eax, eax
0x18008b4a8  js      loc_18008B6D3
0x18008b4ae  mov     edx, 58h ; 'X'; Size
0x18008b4b3  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18008b4bb  call    cs:__imp_RpcAsyncInitializeHandle
0x18008b4c2  nop     dword ptr [rax+rax+00h]
0x18008b4c7  mov     ebx, eax
0x18008b4c9  test    eax, eax
0x18008b4cb  jz      short loc_18008B4E1
0x18008b4cd  mov     dword ptr [r14], 5
0x18008b4d4  mov     [rsi+4], eax
0x18008b4d7  mov     ebx, 0C0000001h
0x18008b4dc  jmp     loc_18008B6D3
0x18008b4e1  mov     [rsp+148h+pAsync.UserInfo], 0
0x18008b4ed  mov     [rsp+148h+pAsync.NotificationType], 1
0x18008b4f8  xor     r8d, r8d; State
0x18008b4fb  xor     edx, edx; Type
0x18008b4fd  lea     rcx, [rsp+148h+Event]; Event
0x18008b505  call    cs:__imp_KeInitializeEvent
0x18008b50c  nop     dword ptr [rax+rax+00h]
0x18008b511  lea     rax, [rsp+148h+Event]
0x18008b519  mov     qword ptr [rsp+148h+pAsync.u], rax
0x18008b521  lea     rax, [rsp+148h+P]
0x18008b526  mov     [rsp+148h+var_110], rax
0x18008b52b  lea     rax, [rsp+148h+var_104]
0x18008b530  mov     [rsp+148h+var_118], rax
0x18008b535  mov     rax, [rsp+148h+var_E0]
0x18008b53a  mov     [rsp+148h+var_120], rax
0x18008b53f  mov     eax, [rsp+148h+arg_10]
0x18008b546  mov     dword ptr [rsp+148h+Timeout], eax
0x18008b54a  mov     r9d, r12d
0x18008b54d  mov     rdx, [rsp+148h+Binding]
0x18008b552  lea     rcx, [rsp+148h+pAsync]
0x18008b55a  call    SSCatDBEnumCatalogs
0x18008b55f  jmp     short loc_18008B58A
0x18008b561  mov     ebx, eax
0x18008b563  mov     r12d, [rsp+148h+var_100]
0x18008b568  mov     r15d, [rsp+148h+var_FC]
0x18008b56d  mov     rax, [rsp+148h+var_D0]
0x18008b572  mov     [rsp+148h+var_E0], rax
0x18008b577  mov     r13, [rsp+148h+var_C8]
0x18008b57f  mov     rsi, [rsp+148h+var_C0]
0x18008b587  mov     r14, rsi
0x18008b58a  test    ebx, ebx
0x18008b58c  jz      short loc_18008B59D
0x18008b58e  mov     dword ptr [r14], 6
0x18008b595  mov     [rsi+4], ebx
0x18008b598  jmp     loc_18008B4D7
0x18008b59d  mov     qword ptr [rsp+148h+Interval], 0FFFFFFFFFB3B4C00h
0x18008b5a6  lea     rax, [rsp+148h+Interval]
0x18008b5ab  mov     [rsp+148h+Timeout], rax; Timeout
0x18008b5b0  xor     r9d, r9d; Alertable
0x18008b5b3  xor     r8d, r8d; WaitMode
0x18008b5b6  xor     edx, edx; WaitReason
0x18008b5b8  lea     rcx, [rsp+148h+Event]; Object
0x18008b5c0  call    cs:__imp_KeWaitForSingleObject
0x18008b5c7  nop     dword ptr [rax+rax+00h]
0x18008b5cc  mov     ebx, eax
0x18008b5ce  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18008b5d6  test    eax, eax
0x18008b5d8  jz      short loc_18008B648
0x18008b5da  mov     dword ptr [r14], 7
0x18008b5e1  mov     [rsi+4], eax
0x18008b5e4  mov     edx, 1; fAbort
0x18008b5e9  call    cs:__imp_RpcAsyncCancelCall
0x18008b5f0  nop     dword ptr [rax+rax+00h]
0x18008b5f5  mov     ebx, eax
0x18008b5f7  mov     [rsp+148h+Timeout], 0; Timeout
0x18008b600  xor     r9d, r9d; Alertable
0x18008b603  xor     r8d, r8d; WaitMode
0x18008b606  xor     edx, edx; WaitReason
0x18008b608  lea     rcx, [rsp+148h+Event]; Object
0x18008b610  call    cs:__imp_KeWaitForSingleObject
0x18008b617  nop     dword ptr [rax+rax+00h]
0x18008b61c  test    ebx, ebx
0x18008b61e  jz      short loc_18008B62A
0x18008b620  mov     dword ptr [r14], 10h
0x18008b627  mov     [rsi+4], ebx
0x18008b62a  lea     rdx, [rsp+148h+Reply]; Reply
0x18008b62f  lea     rcx, [rsp+148h+pAsync]; pAsync
0x18008b637  call    cs:__imp_RpcAsyncCompleteCall
0x18008b63e  nop     dword ptr [rax+rax+00h]
0x18008b643  jmp     loc_18008B4D7
0x18008b648  lea     rdx, [rsp+148h+Reply]; Reply
0x18008b64d  call    cs:__imp_RpcAsyncCompleteCall
0x18008b654  nop     dword ptr [rax+rax+00h]
0x18008b659  cmp     eax, 0C0020018h
0x18008b65e  jnz     short loc_18008B691
0x18008b660  cmp     r15d, 14h
0x18008b664  jnb     short loc_18008B691
0x18008b666  inc     r15d
0x18008b669  mov     [rsp+148h+var_FC], r15d
0x18008b66e  mov     qword ptr [rsp+148h+Interval], 0FFFFFFFFFFF0BDC0h
0x18008b677  lea     r8, [rsp+148h+Interval]; Interval
0x18008b67c  xor     edx, edx; Alertable
0x18008b67e  xor     ecx, ecx; WaitMode
0x18008b680  call    cs:__imp_KeDelayExecutionThread
0x18008b687  nop     dword ptr [rax+rax+00h]
0x18008b68c  jmp     loc_18008B4AE
0x18008b691  test    eax, eax
0x18008b693  jz      short loc_18008B6A1
0x18008b695  mov     dword ptr [r14], 8
0x18008b69c  jmp     loc_18008B4D4
0x18008b6a1  mov     eax, [rsp+148h+Reply]
0x18008b6a5  test    eax, eax
0x18008b6a7  jz      short loc_18008B6B5
0x18008b6a9  mov     dword ptr [r14], 9
0x18008b6b0  jmp     loc_18008B4D4
0x18008b6b5  mov     eax, [rsp+148h+var_104]
0x18008b6b9  mov     [r13+0], eax
0x18008b6bd  mov     rax, [rsp+148h+P]
0x18008b6c2  mov     rcx, [rsp+148h+var_D8]
0x18008b6c7  mov     [rcx], rax
0x18008b6ca  mov     [rsp+148h+P], 0
0x18008b6d3  mov     edx, [rsp+148h+var_104]
0x18008b6d7  mov     rcx, [rsp+148h+P]; P
0x18008b6dc  call    CiCatDbFreeListOfCatalogs
0x18008b6e1  cmp     [rsp+148h+Binding], 0
0x18008b6e7  jz      short loc_18008B6F3
0x18008b6e9  lea     rcx, [rsp+148h+Binding]; Binding
0x18008b6ee  call    CipCatDbRpcDisconnect
0x18008b6f3  mov     eax, ebx
0x18008b6f5  mov     rcx, [rsp+148h+var_38]
0x18008b6fd  xor     rcx, rsp; StackCookie
0x18008b700  call    __security_check_cookie
0x18008b705  mov     rbx, [rsp+148h+arg_0]
0x18008b70d  add     rsp, 120h
0x18008b714  pop     r15
0x18008b716  pop     r14
0x18008b718  pop     r13
0x18008b71a  pop     r12
0x18008b71c  pop     rsi
0x18008b71d  retn
0x1800e96f8  push    rbp
0x1800e96fa  sub     rsp, 40h
0x1800e96fe  mov     rbp, rdx
0x1800e9701  mov     rcx, [rcx]
0x1800e9704  mov     ecx, [rcx]; ExceptionCode
0x1800e9706  call    cs:__imp_I_RpcExceptionFilter
0x1800e970d  nop     dword ptr [rax+rax+00h]
0x1800e9712  nop
0x1800e9713  add     rsp, 40h
0x1800e9717  pop     rbp
0x1800e9718  retn
```
