# CipCatDbRpcConnect

- ea: `0x180089b2c`
- end: `0x180089d7d`
- name: `CipCatDbRpcConnect`
- size: `593`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180061684`
- `0x18006189c`
- `0x180061c54`
- `0x1800896e4`
- `0x180089d84`
- `0x1800c7354`

## callees

- `0x18002bef0`
- `0x18002c340`
- `0x180089b2c`

## import_xrefs

- `ntoskrnl!ZwQueryWnfStateData` at `0x180089bba`
- `ntoskrnl!ZwQueryWnfStateData` at `0x180089bba`
- `ntoskrnl!KeInitializeEvent` at `0x180089c4a`
- `ntoskrnl!KeInitializeEvent` at `0x180089c4a`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089c9e`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089ce1`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089c9e`
- `ntoskrnl!KeWaitForSingleObject` at `0x180089ce1`
- `msrpc!RpcBindingFree` at `0x180089d4a`
- `msrpc!RpcBindingFree` at `0x180089d4a`
- `msrpc!RpcAsyncCancelCall` at `0x180089cc2`
- `msrpc!RpcAsyncCancelCall` at `0x180089cc2`
- `msrpc!RpcAsyncCompleteCall` at `0x180089d06`
- `msrpc!RpcAsyncCompleteCall` at `0x180089d06`
- `msrpc!RpcBindingBind` at `0x180089c6d`
- `msrpc!RpcBindingBind` at `0x180089c6d`
- `msrpc!RpcAsyncInitializeHandle` at `0x180089c1e`
- `msrpc!RpcAsyncInitializeHandle` at `0x180089c1e`
- `msrpc!RpcBindingCreateW` at `0x180089bfa`
- `msrpc!RpcBindingCreateW` at `0x180089bfa`
- `msrpc!RpcAsyncGetCallStatus` at `0x180089d17`
- `msrpc!RpcAsyncGetCallStatus` at `0x180089d17`

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
  if ( !byte_180048998 )
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
    byte_180048998 = 1;
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
  v5 = RpcBindingBind(&pAsync, Binding, qword_18002E4D0);
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
0x180089b2c  mov     [rsp-8+arg_10], rbx
0x180089b31  mov     [rsp-8+arg_18], rsi
0x180089b36  push    rbp
0x180089b37  push    rdi
0x180089b38  push    r14
0x180089b3a  lea     rbp, [rsp-47h]
0x180089b3f  sub     rsp, 0E0h
0x180089b46  mov     rax, cs:__security_cookie
0x180089b4d  xor     rax, rsp
0x180089b50  mov     [rbp+57h+var_20], rax
0x180089b54  mov     rdi, rdx
0x180089b57  mov     rsi, rcx
0x180089b5a  xor     edx, edx; Val
0x180089b5c  lea     rcx, [rbp+57h+pAsync]; void *
0x180089b60  lea     r8d, [rdx+58h]; Size
0x180089b64  call    memset
0x180089b69  xor     eax, eax
0x180089b6b  xor     r14d, r14d
0x180089b6e  cmp     cs:byte_180048998, r14b
0x180089b75  xorps   xmm0, xmm0
0x180089b78  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x180089b7c  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x180089b80  lea     ebx, [rax+4]
0x180089b83  mov     [rbp+57h+Binding], r14
0x180089b87  mov     qword ptr [rbp+57h+var_A8], r14
0x180089b8b  jnz     short loc_180089BE1
0x180089b8d  lea     rax, [rbp+57h+var_AC]
0x180089b91  mov     [rbp+57h+var_B0], r14d
0x180089b95  mov     [rsp+0F0h+var_C8], rax
0x180089b9a  lea     r9, [rbp+57h+Reply]
0x180089b9e  lea     rax, [rbp+57h+var_B0]
0x180089ba2  mov     [rbp+57h+var_AC], ebx
0x180089ba5  xor     r8d, r8d
0x180089ba8  mov     [rsp+0F0h+Timeout], rax
0x180089bad  xor     edx, edx
0x180089baf  mov     [rbp+57h+Reply], r14d
0x180089bb3  lea     rcx, WNF_SCM_AUTOSTART_STATE
0x180089bba  call    cs:__imp_ZwQueryWnfStateData
0x180089bc1  nop     dword ptr [rax+rax+00h]
0x180089bc6  test    eax, eax
0x180089bc8  js      short loc_180089BDA
0x180089bca  cmp     [rbp+57h+var_B0], 2
0x180089bce  jnb     short loc_180089BDA
0x180089bd0  mov     ebx, 0C0000001h
0x180089bd5  jmp     loc_180089D40
0x180089bda  mov     cs:byte_180048998, 1
0x180089be1  lea     r9, [rbp+57h+Binding]; Binding
0x180089be5  lea     r8, Options; Options
0x180089bec  lea     rdx, Security; Security
0x180089bf3  lea     rcx, Template; Template
0x180089bfa  call    cs:__imp_RpcBindingCreateW
0x180089c01  nop     dword ptr [rax+rax+00h]
0x180089c06  test    eax, eax
0x180089c08  jz      short loc_180089C15
0x180089c0a  mov     dword ptr [rdi], 3
0x180089c10  mov     [rdi+4], eax
0x180089c13  jmp     short loc_180089BD0
0x180089c15  mov     edx, 58h ; 'X'; Size
0x180089c1a  lea     rcx, [rbp+57h+pAsync]; pAsync
0x180089c1e  call    cs:__imp_RpcAsyncInitializeHandle
0x180089c25  nop     dword ptr [rax+rax+00h]
0x180089c2a  test    eax, eax
0x180089c2c  jz      short loc_180089C36
0x180089c2e  mov     dword ptr [rdi], 0Ch
0x180089c34  jmp     short loc_180089C10
0x180089c36  xor     r8d, r8d; State
0x180089c39  mov     [rbp+57h+pAsync.UserInfo], r14
0x180089c3d  xor     edx, edx; Type
0x180089c3f  mov     [rbp+57h+pAsync.NotificationType], 1
0x180089c46  lea     rcx, [rbp+57h+Event]; Event
0x180089c4a  call    cs:__imp_KeInitializeEvent
0x180089c51  nop     dword ptr [rax+rax+00h]
0x180089c56  mov     rdx, [rbp+57h+Binding]; Binding
0x180089c5a  lea     rax, [rbp+57h+Event]
0x180089c5e  lea     r8, qword_18002E4D0; IfSpec
0x180089c65  mov     qword ptr [rbp+57h+pAsync.u], rax
0x180089c69  lea     rcx, [rbp+57h+pAsync]; pAsync
0x180089c6d  call    cs:__imp_RpcBindingBind
0x180089c74  nop     dword ptr [rax+rax+00h]
0x180089c79  test    eax, eax
0x180089c7b  jz      short loc_180089C81
0x180089c7d  mov     [rdi], ebx
0x180089c7f  jmp     short loc_180089C10
0x180089c81  lea     rax, [rbp+57h+var_A8]
0x180089c85  mov     qword ptr [rbp+57h+var_A8], 0FFFFFFFFFF676980h
0x180089c8d  xor     r9d, r9d; Alertable
0x180089c90  mov     [rsp+0F0h+Timeout], rax; Timeout
0x180089c95  xor     r8d, r8d; WaitMode
0x180089c98  lea     rcx, [rbp+57h+Event]; Object
0x180089c9c  xor     edx, edx; WaitReason
0x180089c9e  call    cs:__imp_KeWaitForSingleObject
0x180089ca5  nop     dword ptr [rax+rax+00h]
0x180089caa  lea     rcx, [rbp+57h+pAsync]; pAsync
0x180089cae  mov     ebx, eax
0x180089cb0  test    eax, eax
0x180089cb2  jz      short loc_180089D17
0x180089cb4  mov     edx, 1; fAbort
0x180089cb9  mov     dword ptr [rdi], 0Dh
0x180089cbf  mov     [rdi+4], eax
0x180089cc2  call    cs:__imp_RpcAsyncCancelCall
0x180089cc9  nop     dword ptr [rax+rax+00h]
0x180089cce  xor     r9d, r9d; Alertable
0x180089cd1  mov     [rsp+0F0h+Timeout], r14; Timeout
0x180089cd6  xor     r8d, r8d; WaitMode
0x180089cd9  lea     rcx, [rbp+57h+Event]; Object
0x180089cdd  xor     edx, edx; WaitReason
0x180089cdf  mov     ebx, eax
0x180089ce1  call    cs:__imp_KeWaitForSingleObject
0x180089ce8  nop     dword ptr [rax+rax+00h]
0x180089ced  test    ebx, ebx
0x180089cef  jz      short loc_180089CFA
0x180089cf1  mov     dword ptr [rdi], 10h
0x180089cf7  mov     [rdi+4], ebx
0x180089cfa  lea     rdx, [rbp+57h+Reply]; Reply
0x180089cfe  mov     [rbp+57h+Reply], r14d
0x180089d02  lea     rcx, [rbp+57h+pAsync]; pAsync
0x180089d06  call    cs:__imp_RpcAsyncCompleteCall
0x180089d0d  nop     dword ptr [rax+rax+00h]
0x180089d12  jmp     loc_180089BD0
0x180089d17  call    cs:__imp_RpcAsyncGetCallStatus
0x180089d1e  nop     dword ptr [rax+rax+00h]
0x180089d23  test    eax, eax
0x180089d25  jz      short loc_180089D32
0x180089d27  mov     dword ptr [rdi], 0Eh
0x180089d2d  jmp     loc_180089C10
0x180089d32  mov     rax, [rbp+57h+Binding]
0x180089d36  mov     [rdi], r14
0x180089d39  mov     [rsi], rax
0x180089d3c  mov     [rbp+57h+Binding], r14
0x180089d40  cmp     [rbp+57h+Binding], r14
0x180089d44  jz      short loc_180089D56
0x180089d46  lea     rcx, [rbp+57h+Binding]; Binding
0x180089d4a  call    cs:__imp_RpcBindingFree
0x180089d51  nop     dword ptr [rax+rax+00h]
0x180089d56  mov     eax, ebx
0x180089d58  mov     rcx, [rbp+57h+var_20]
0x180089d5c  xor     rcx, rsp; StackCookie
0x180089d5f  call    __security_check_cookie
0x180089d64  lea     r11, [rsp+0F0h+var_10]
0x180089d6c  mov     rbx, [r11+30h]
0x180089d70  mov     rsi, [r11+38h]
0x180089d74  mov     rsp, r11
0x180089d77  pop     r14
0x180089d79  pop     rdi
0x180089d7a  pop     rbp
0x180089d7b  retn
```
