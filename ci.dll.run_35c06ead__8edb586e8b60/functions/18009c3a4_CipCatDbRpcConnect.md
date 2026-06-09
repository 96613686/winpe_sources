# CipCatDbRpcConnect

- ea: `0x18009c3a4`
- end: `0x18009c5f5`
- name: `CipCatDbRpcConnect`
- size: `593`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006202c`
- `0x180062244`
- `0x1800625fc`
- `0x18009bf5c`
- `0x18009d4a0`
- `0x1800c87e4`

## callees

- `0x18002c0d0`
- `0x18002c500`
- `0x18009c3a4`

## import_xrefs

- `ntoskrnl!ZwQueryWnfStateData` at `0x18009c432`
- `ntoskrnl!ZwQueryWnfStateData` at `0x18009c432`
- `ntoskrnl!KeInitializeEvent` at `0x18009c4c2`
- `ntoskrnl!KeInitializeEvent` at `0x18009c4c2`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009c516`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009c559`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009c516`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009c559`
- `msrpc!RpcBindingFree` at `0x18009c5c2`
- `msrpc!RpcBindingFree` at `0x18009c5c2`
- `msrpc!RpcAsyncCancelCall` at `0x18009c53a`
- `msrpc!RpcAsyncCancelCall` at `0x18009c53a`
- `msrpc!RpcAsyncCompleteCall` at `0x18009c57e`
- `msrpc!RpcAsyncCompleteCall` at `0x18009c57e`
- `msrpc!RpcBindingBind` at `0x18009c4e5`
- `msrpc!RpcBindingBind` at `0x18009c4e5`
- `msrpc!RpcAsyncInitializeHandle` at `0x18009c496`
- `msrpc!RpcAsyncInitializeHandle` at `0x18009c496`
- `msrpc!RpcBindingCreateW` at `0x18009c472`
- `msrpc!RpcBindingCreateW` at `0x18009c472`
- `msrpc!RpcAsyncGetCallStatus` at `0x18009c58f`
- `msrpc!RpcAsyncGetCallStatus` at `0x18009c58f`

## pseudocode

```c
__int64 __fastcall CipCatDbRpcConnect(_QWORD *a1, _DWORD *a2)
{
  unsigned int v4; // ebx
  RPC_STATUS v5; // eax
  NTSTATUS v6; // eax
  RPC_STATUS v7; // ebx
  RPC_BINDING_HANDLE v8; // rax
  int Reply; // [rsp+30h] [rbp-69h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-61h] BYREF
  unsigned int v12; // [rsp+40h] [rbp-59h] BYREF
  int v13; // [rsp+44h] [rbp-55h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+48h] [rbp-51h] BYREF
  struct _KEVENT Event; // [rsp+50h] [rbp-49h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+70h] [rbp-29h] BYREF

  memset(&pAsync, 0, sizeof(pAsync));
  memset(&Event, 0, sizeof(Event));
  Binding = 0;
  Timeout.QuadPart = 0;
  if ( !byte_180049998 )
  {
    v12 = 0;
    v13 = 4;
    Reply = 0;
    if ( (int)((__int64 (__fastcall *)(__int64 *, _QWORD, _QWORD, int *, unsigned int *, int *))ZwQueryWnfStateData)(
                &WNF_SCM_AUTOSTART_STATE,
                0,
                0,
                &Reply,
                &v12,
                &v13) >= 0
      && v12 < 2 )
    {
      goto LABEL_4;
    }
    byte_180049998 = 1;
  }
  v5 = RpcBindingCreateW(
         (RPC_BINDING_HANDLE_TEMPLATE_V1_W *)&Template,
         (RPC_BINDING_HANDLE_SECURITY_V1_W *)&Security,
         (RPC_BINDING_HANDLE_OPTIONS_V1 *)&Options,
         &Binding);
  if ( v5 )
  {
    *a2 = 3;
LABEL_8:
    a2[1] = v5;
LABEL_4:
    v4 = -1073741823;
    goto LABEL_20;
  }
  v5 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
  if ( v5 )
  {
    *a2 = 12;
    goto LABEL_8;
  }
  pAsync.UserInfo = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  pAsync.u.Event = &Event;
  v5 = RpcBindingBind(&pAsync, Binding, qword_18002EE90);
  if ( v5 )
  {
    *a2 = 4;
    goto LABEL_8;
  }
  Timeout.QuadPart = -10000000;
  v6 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
  v4 = v6;
  if ( v6 )
  {
    *a2 = 13;
    a2[1] = v6;
    v7 = RpcAsyncCancelCall(&pAsync, 1);
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( v7 )
    {
      *a2 = 16;
      a2[1] = v7;
    }
    Reply = 0;
    RpcAsyncCompleteCall(&pAsync, &Reply);
    goto LABEL_4;
  }
  v5 = RpcAsyncGetCallStatus(&pAsync);
  if ( v5 )
  {
    *a2 = 14;
    goto LABEL_8;
  }
  v8 = Binding;
  *(_QWORD *)a2 = 0;
  *a1 = v8;
  Binding = 0;
LABEL_20:
  if ( Binding )
    RpcBindingFree(&Binding);
  return v4;
}

```

## disassembly

```asm
0x18009c3a4  mov     [rsp-8+arg_10], rbx
0x18009c3a9  mov     [rsp-8+arg_18], rsi
0x18009c3ae  push    rbp
0x18009c3af  push    rdi
0x18009c3b0  push    r14
0x18009c3b2  lea     rbp, [rsp-47h]
0x18009c3b7  sub     rsp, 0E0h
0x18009c3be  mov     rax, cs:__security_cookie
0x18009c3c5  xor     rax, rsp
0x18009c3c8  mov     [rbp+57h+var_20], rax
0x18009c3cc  mov     rdi, rdx
0x18009c3cf  mov     rsi, rcx
0x18009c3d2  xor     edx, edx; Val
0x18009c3d4  lea     rcx, [rbp+57h+pAsync]; void *
0x18009c3d8  lea     r8d, [rdx+58h]; Size
0x18009c3dc  call    memset
0x18009c3e1  xor     eax, eax
0x18009c3e3  xor     r14d, r14d
0x18009c3e6  cmp     cs:byte_180049998, r14b
0x18009c3ed  xorps   xmm0, xmm0
0x18009c3f0  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x18009c3f4  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18009c3f8  lea     ebx, [rax+4]
0x18009c3fb  mov     [rbp+57h+Binding], r14
0x18009c3ff  mov     qword ptr [rbp+57h+var_A8], r14
0x18009c403  jnz     short loc_18009C459
0x18009c405  lea     rax, [rbp+57h+var_AC]
0x18009c409  mov     [rbp+57h+var_B0], r14d
0x18009c40d  mov     [rsp+0F0h+var_C8], rax
0x18009c412  lea     r9, [rbp+57h+Reply]
0x18009c416  lea     rax, [rbp+57h+var_B0]
0x18009c41a  mov     [rbp+57h+var_AC], ebx
0x18009c41d  xor     r8d, r8d
0x18009c420  mov     [rsp+0F0h+Timeout], rax
0x18009c425  xor     edx, edx
0x18009c427  mov     [rbp+57h+Reply], r14d
0x18009c42b  lea     rcx, WNF_SCM_AUTOSTART_STATE
0x18009c432  call    cs:__imp_ZwQueryWnfStateData
0x18009c439  nop     dword ptr [rax+rax+00h]
0x18009c43e  test    eax, eax
0x18009c440  js      short loc_18009C452
0x18009c442  cmp     [rbp+57h+var_B0], 2
0x18009c446  jnb     short loc_18009C452
0x18009c448  mov     ebx, 0C0000001h
0x18009c44d  jmp     loc_18009C5B8
0x18009c452  mov     cs:byte_180049998, 1
0x18009c459  lea     r9, [rbp+57h+Binding]; Binding
0x18009c45d  lea     r8, Options; Options
0x18009c464  lea     rdx, Security; Security
0x18009c46b  lea     rcx, Template; Template
0x18009c472  call    cs:__imp_RpcBindingCreateW
0x18009c479  nop     dword ptr [rax+rax+00h]
0x18009c47e  test    eax, eax
0x18009c480  jz      short loc_18009C48D
0x18009c482  mov     dword ptr [rdi], 3
0x18009c488  mov     [rdi+4], eax
0x18009c48b  jmp     short loc_18009C448
0x18009c48d  mov     edx, 58h ; 'X'; Size
0x18009c492  lea     rcx, [rbp+57h+pAsync]; pAsync
0x18009c496  call    cs:__imp_RpcAsyncInitializeHandle
0x18009c49d  nop     dword ptr [rax+rax+00h]
0x18009c4a2  test    eax, eax
0x18009c4a4  jz      short loc_18009C4AE
0x18009c4a6  mov     dword ptr [rdi], 0Ch
0x18009c4ac  jmp     short loc_18009C488
0x18009c4ae  xor     r8d, r8d; State
0x18009c4b1  mov     [rbp+57h+pAsync.UserInfo], r14
0x18009c4b5  xor     edx, edx; Type
0x18009c4b7  mov     [rbp+57h+pAsync.NotificationType], 1
0x18009c4be  lea     rcx, [rbp+57h+Event]; Event
0x18009c4c2  call    cs:__imp_KeInitializeEvent
0x18009c4c9  nop     dword ptr [rax+rax+00h]
0x18009c4ce  mov     rdx, [rbp+57h+Binding]; Binding
0x18009c4d2  lea     rax, [rbp+57h+Event]
0x18009c4d6  lea     r8, qword_18002EE90; IfSpec
0x18009c4dd  mov     qword ptr [rbp+57h+pAsync.u], rax
0x18009c4e1  lea     rcx, [rbp+57h+pAsync]; pAsync
0x18009c4e5  call    cs:__imp_RpcBindingBind
0x18009c4ec  nop     dword ptr [rax+rax+00h]
0x18009c4f1  test    eax, eax
0x18009c4f3  jz      short loc_18009C4F9
0x18009c4f5  mov     [rdi], ebx
0x18009c4f7  jmp     short loc_18009C488
0x18009c4f9  lea     rax, [rbp+57h+var_A8]
0x18009c4fd  mov     qword ptr [rbp+57h+var_A8], 0FFFFFFFFFF676980h
0x18009c505  xor     r9d, r9d; Alertable
0x18009c508  mov     [rsp+0F0h+Timeout], rax; Timeout
0x18009c50d  xor     r8d, r8d; WaitMode
0x18009c510  lea     rcx, [rbp+57h+Event]; Object
0x18009c514  xor     edx, edx; WaitReason
0x18009c516  call    cs:__imp_KeWaitForSingleObject
0x18009c51d  nop     dword ptr [rax+rax+00h]
0x18009c522  lea     rcx, [rbp+57h+pAsync]; pAsync
0x18009c526  mov     ebx, eax
0x18009c528  test    eax, eax
0x18009c52a  jz      short loc_18009C58F
0x18009c52c  mov     edx, 1; fAbort
0x18009c531  mov     dword ptr [rdi], 0Dh
0x18009c537  mov     [rdi+4], eax
0x18009c53a  call    cs:__imp_RpcAsyncCancelCall
0x18009c541  nop     dword ptr [rax+rax+00h]
0x18009c546  xor     r9d, r9d; Alertable
0x18009c549  mov     [rsp+0F0h+Timeout], r14; Timeout
0x18009c54e  xor     r8d, r8d; WaitMode
0x18009c551  lea     rcx, [rbp+57h+Event]; Object
0x18009c555  xor     edx, edx; WaitReason
0x18009c557  mov     ebx, eax
0x18009c559  call    cs:__imp_KeWaitForSingleObject
0x18009c560  nop     dword ptr [rax+rax+00h]
0x18009c565  test    ebx, ebx
0x18009c567  jz      short loc_18009C572
0x18009c569  mov     dword ptr [rdi], 10h
0x18009c56f  mov     [rdi+4], ebx
0x18009c572  lea     rdx, [rbp+57h+Reply]; Reply
0x18009c576  mov     [rbp+57h+Reply], r14d
0x18009c57a  lea     rcx, [rbp+57h+pAsync]; pAsync
0x18009c57e  call    cs:__imp_RpcAsyncCompleteCall
0x18009c585  nop     dword ptr [rax+rax+00h]
0x18009c58a  jmp     loc_18009C448
0x18009c58f  call    cs:__imp_RpcAsyncGetCallStatus
0x18009c596  nop     dword ptr [rax+rax+00h]
0x18009c59b  test    eax, eax
0x18009c59d  jz      short loc_18009C5AA
0x18009c59f  mov     dword ptr [rdi], 0Eh
0x18009c5a5  jmp     loc_18009C488
0x18009c5aa  mov     rax, [rbp+57h+Binding]
0x18009c5ae  mov     [rdi], r14
0x18009c5b1  mov     [rsi], rax
0x18009c5b4  mov     [rbp+57h+Binding], r14
0x18009c5b8  cmp     [rbp+57h+Binding], r14
0x18009c5bc  jz      short loc_18009C5CE
0x18009c5be  lea     rcx, [rbp+57h+Binding]; Binding
0x18009c5c2  call    cs:__imp_RpcBindingFree
0x18009c5c9  nop     dword ptr [rax+rax+00h]
0x18009c5ce  mov     eax, ebx
0x18009c5d0  mov     rcx, [rbp+57h+var_20]
0x18009c5d4  xor     rcx, rsp; StackCookie
0x18009c5d7  call    __security_check_cookie
0x18009c5dc  lea     r11, [rsp+0F0h+var_10]
0x18009c5e4  mov     rbx, [r11+30h]
0x18009c5e8  mov     rsi, [r11+38h]
0x18009c5ec  mov     rsp, r11
0x18009c5ef  pop     r14
0x18009c5f1  pop     rdi
0x18009c5f2  pop     rbp
0x18009c5f3  retn
```
