# CipCatDbRpcConnect

- ea: `0x18008b15c`
- end: `0x18008b3ad`
- name: `CipCatDbRpcConnect`
- size: `593`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180061ec8`
- `0x1800620e0`
- `0x180062498`
- `0x18008ad14`
- `0x18008b3b4`
- `0x1800c87d4`

## callees

- `0x18002bf20`
- `0x18002c380`
- `0x18008b15c`

## import_xrefs

- `ntoskrnl!ZwQueryWnfStateData` at `0x18008b1ea`
- `ntoskrnl!ZwQueryWnfStateData` at `0x18008b1ea`
- `ntoskrnl!KeInitializeEvent` at `0x18008b27a`
- `ntoskrnl!KeInitializeEvent` at `0x18008b27a`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008b2ce`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008b311`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008b2ce`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008b311`
- `msrpc!RpcBindingFree` at `0x18008b37a`
- `msrpc!RpcBindingFree` at `0x18008b37a`
- `msrpc!RpcAsyncCancelCall` at `0x18008b2f2`
- `msrpc!RpcAsyncCancelCall` at `0x18008b2f2`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b336`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b336`
- `msrpc!RpcBindingBind` at `0x18008b29d`
- `msrpc!RpcBindingBind` at `0x18008b29d`
- `msrpc!RpcAsyncInitializeHandle` at `0x18008b24e`
- `msrpc!RpcAsyncInitializeHandle` at `0x18008b24e`
- `msrpc!RpcBindingCreateW` at `0x18008b22a`
- `msrpc!RpcBindingCreateW` at `0x18008b22a`
- `msrpc!RpcAsyncGetCallStatus` at `0x18008b347`
- `msrpc!RpcAsyncGetCallStatus` at `0x18008b347`

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
  if ( !byte_180049990 )
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
    byte_180049990 = 1;
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
0x18008b15c  mov     [rsp-8+arg_10], rbx
0x18008b161  mov     [rsp-8+arg_18], rsi
0x18008b166  push    rbp
0x18008b167  push    rdi
0x18008b168  push    r14
0x18008b16a  lea     rbp, [rsp-47h]
0x18008b16f  sub     rsp, 0E0h
0x18008b176  mov     rax, cs:__security_cookie
0x18008b17d  xor     rax, rsp
0x18008b180  mov     [rbp+57h+var_20], rax
0x18008b184  mov     rdi, rdx
0x18008b187  mov     rsi, rcx
0x18008b18a  xor     edx, edx; Val
0x18008b18c  lea     rcx, [rbp+57h+pAsync]; void *
0x18008b190  lea     r8d, [rdx+58h]; Size
0x18008b194  call    memset
0x18008b199  xor     eax, eax
0x18008b19b  xor     r14d, r14d
0x18008b19e  cmp     cs:byte_180049990, r14b
0x18008b1a5  xorps   xmm0, xmm0
0x18008b1a8  movups  xmmword ptr [rbp+57h+Event.Header], xmm0
0x18008b1ac  mov     [rbp+57h+Event.Header.WaitListHead.Blink], rax
0x18008b1b0  lea     ebx, [rax+4]
0x18008b1b3  mov     [rbp+57h+Binding], r14
0x18008b1b7  mov     qword ptr [rbp+57h+var_A8], r14
0x18008b1bb  jnz     short loc_18008B211
0x18008b1bd  lea     rax, [rbp+57h+var_AC]
0x18008b1c1  mov     [rbp+57h+var_B0], r14d
0x18008b1c5  mov     [rsp+0F0h+var_C8], rax
0x18008b1ca  lea     r9, [rbp+57h+Reply]
0x18008b1ce  lea     rax, [rbp+57h+var_B0]
0x18008b1d2  mov     [rbp+57h+var_AC], ebx
0x18008b1d5  xor     r8d, r8d
0x18008b1d8  mov     [rsp+0F0h+Timeout], rax
0x18008b1dd  xor     edx, edx
0x18008b1df  mov     [rbp+57h+Reply], r14d
0x18008b1e3  lea     rcx, WNF_SCM_AUTOSTART_STATE
0x18008b1ea  call    cs:__imp_ZwQueryWnfStateData
0x18008b1f1  nop     dword ptr [rax+rax+00h]
0x18008b1f6  test    eax, eax
0x18008b1f8  js      short loc_18008B20A
0x18008b1fa  cmp     [rbp+57h+var_B0], 2
0x18008b1fe  jnb     short loc_18008B20A
0x18008b200  mov     ebx, 0C0000001h
0x18008b205  jmp     loc_18008B370
0x18008b20a  mov     cs:byte_180049990, 1
0x18008b211  lea     r9, [rbp+57h+Binding]; Binding
0x18008b215  lea     r8, Options; Options
0x18008b21c  lea     rdx, Security; Security
0x18008b223  lea     rcx, Template; Template
0x18008b22a  call    cs:__imp_RpcBindingCreateW
0x18008b231  nop     dword ptr [rax+rax+00h]
0x18008b236  test    eax, eax
0x18008b238  jz      short loc_18008B245
0x18008b23a  mov     dword ptr [rdi], 3
0x18008b240  mov     [rdi+4], eax
0x18008b243  jmp     short loc_18008B200
0x18008b245  mov     edx, 58h ; 'X'; Size
0x18008b24a  lea     rcx, [rbp+57h+pAsync]; pAsync
0x18008b24e  call    cs:__imp_RpcAsyncInitializeHandle
0x18008b255  nop     dword ptr [rax+rax+00h]
0x18008b25a  test    eax, eax
0x18008b25c  jz      short loc_18008B266
0x18008b25e  mov     dword ptr [rdi], 0Ch
0x18008b264  jmp     short loc_18008B240
0x18008b266  xor     r8d, r8d; State
0x18008b269  mov     [rbp+57h+pAsync.UserInfo], r14
0x18008b26d  xor     edx, edx; Type
0x18008b26f  mov     [rbp+57h+pAsync.NotificationType], 1
0x18008b276  lea     rcx, [rbp+57h+Event]; Event
0x18008b27a  call    cs:__imp_KeInitializeEvent
0x18008b281  nop     dword ptr [rax+rax+00h]
0x18008b286  mov     rdx, [rbp+57h+Binding]; Binding
0x18008b28a  lea     rax, [rbp+57h+Event]
0x18008b28e  lea     r8, qword_18002E4D0; IfSpec
0x18008b295  mov     qword ptr [rbp+57h+pAsync.u], rax
0x18008b299  lea     rcx, [rbp+57h+pAsync]; pAsync
0x18008b29d  call    cs:__imp_RpcBindingBind
0x18008b2a4  nop     dword ptr [rax+rax+00h]
0x18008b2a9  test    eax, eax
0x18008b2ab  jz      short loc_18008B2B1
0x18008b2ad  mov     [rdi], ebx
0x18008b2af  jmp     short loc_18008B240
0x18008b2b1  lea     rax, [rbp+57h+var_A8]
0x18008b2b5  mov     qword ptr [rbp+57h+var_A8], 0FFFFFFFFFF676980h
0x18008b2bd  xor     r9d, r9d; Alertable
0x18008b2c0  mov     [rsp+0F0h+Timeout], rax; Timeout
0x18008b2c5  xor     r8d, r8d; WaitMode
0x18008b2c8  lea     rcx, [rbp+57h+Event]; Object
0x18008b2cc  xor     edx, edx; WaitReason
0x18008b2ce  call    cs:__imp_KeWaitForSingleObject
0x18008b2d5  nop     dword ptr [rax+rax+00h]
0x18008b2da  lea     rcx, [rbp+57h+pAsync]; pAsync
0x18008b2de  mov     ebx, eax
0x18008b2e0  test    eax, eax
0x18008b2e2  jz      short loc_18008B347
0x18008b2e4  mov     edx, 1; fAbort
0x18008b2e9  mov     dword ptr [rdi], 0Dh
0x18008b2ef  mov     [rdi+4], eax
0x18008b2f2  call    cs:__imp_RpcAsyncCancelCall
0x18008b2f9  nop     dword ptr [rax+rax+00h]
0x18008b2fe  xor     r9d, r9d; Alertable
0x18008b301  mov     [rsp+0F0h+Timeout], r14; Timeout
0x18008b306  xor     r8d, r8d; WaitMode
0x18008b309  lea     rcx, [rbp+57h+Event]; Object
0x18008b30d  xor     edx, edx; WaitReason
0x18008b30f  mov     ebx, eax
0x18008b311  call    cs:__imp_KeWaitForSingleObject
0x18008b318  nop     dword ptr [rax+rax+00h]
0x18008b31d  test    ebx, ebx
0x18008b31f  jz      short loc_18008B32A
0x18008b321  mov     dword ptr [rdi], 10h
0x18008b327  mov     [rdi+4], ebx
0x18008b32a  lea     rdx, [rbp+57h+Reply]; Reply
0x18008b32e  mov     [rbp+57h+Reply], r14d
0x18008b332  lea     rcx, [rbp+57h+pAsync]; pAsync
0x18008b336  call    cs:__imp_RpcAsyncCompleteCall
0x18008b33d  nop     dword ptr [rax+rax+00h]
0x18008b342  jmp     loc_18008B200
0x18008b347  call    cs:__imp_RpcAsyncGetCallStatus
0x18008b34e  nop     dword ptr [rax+rax+00h]
0x18008b353  test    eax, eax
0x18008b355  jz      short loc_18008B362
0x18008b357  mov     dword ptr [rdi], 0Eh
0x18008b35d  jmp     loc_18008B240
0x18008b362  mov     rax, [rbp+57h+Binding]
0x18008b366  mov     [rdi], r14
0x18008b369  mov     [rsi], rax
0x18008b36c  mov     [rbp+57h+Binding], r14
0x18008b370  cmp     [rbp+57h+Binding], r14
0x18008b374  jz      short loc_18008B386
0x18008b376  lea     rcx, [rbp+57h+Binding]; Binding
0x18008b37a  call    cs:__imp_RpcBindingFree
0x18008b381  nop     dword ptr [rax+rax+00h]
0x18008b386  mov     eax, ebx
0x18008b388  mov     rcx, [rbp+57h+var_20]
0x18008b38c  xor     rcx, rsp; StackCookie
0x18008b38f  call    __security_check_cookie
0x18008b394  lea     r11, [rsp+0F0h+var_10]
0x18008b39c  mov     rbx, [r11+30h]
0x18008b3a0  mov     rsi, [r11+38h]
0x18008b3a4  mov     rsp, r11
0x18008b3a7  pop     r14
0x18008b3a9  pop     rdi
0x18008b3aa  pop     rbp
0x18008b3ab  retn
```
