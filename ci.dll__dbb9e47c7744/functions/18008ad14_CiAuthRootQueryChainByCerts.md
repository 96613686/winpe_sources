# CiAuthRootQueryChainByCerts

- ea: `0x18008ad14`
- end: `0x18008b155`
- name: `CiAuthRootQueryChainByCerts`
- size: `1089`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800e5410`

## callees

- `0x180020668`
- `0x18002bf20`
- `0x18002c380`
- `0x18008ad14`
- `0x18008b15c`
- `0x1800bbba4`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x18008ae41`
- `ntoskrnl!KeStackAttachProcess` at `0x18008ae41`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008b0d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008b0ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008b0d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x18008b0ef`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18008b114`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18008b114`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18008ae1b`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18008ae1b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18008b123`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18008b123`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18008ae0c`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18008ae0c`
- `ntoskrnl!KeDelayExecutionThread` at `0x18008b049`
- `ntoskrnl!KeDelayExecutionThread` at `0x18008b049`
- `ntoskrnl!KeInitializeEvent` at `0x18008aecc`
- `ntoskrnl!KeInitializeEvent` at `0x18008aecc`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008afaa`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008afea`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008afaa`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008afea`
- `msrpc!RpcAsyncCancelCall` at `0x18008afc9`
- `msrpc!RpcAsyncCancelCall` at `0x18008afc9`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b003`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b019`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b003`
- `msrpc!RpcAsyncCompleteCall` at `0x18008b019`
- `msrpc!I_RpcExceptionFilter` at `0x1800e96de`
- `msrpc!I_RpcExceptionFilter` at `0x1800e96de`
- `msrpc!RpcAsyncInitializeHandle` at `0x18008ae96`
- `msrpc!RpcAsyncInitializeHandle` at `0x18008ae96`

## pseudocode

```c
__int64 __fastcall CiAuthRootQueryChainByCerts(
        int a1,
        __int64 a2,
        __int64 *a3,
        __int64 a4,
        unsigned int *a5,
        PVOID *a6)
{
  __int64 *v7; // r14
  __int64 CurrentServerSilo; // rax
  __int64 v9; // r15
  RPC_STATUS v10; // edi
  RPC_STATUS v11; // eax
  unsigned int v12; // esi
  unsigned int i; // edx
  unsigned int j; // esi
  void *v15; // rcx
  unsigned int v17; // [rsp+40h] [rbp-178h] BYREF
  int Reply; // [rsp+44h] [rbp-174h] BYREF
  PVOID P; // [rsp+48h] [rbp-170h] BYREF
  __int64 v20; // [rsp+50h] [rbp-168h] BYREF
  int v21; // [rsp+58h] [rbp-160h]
  union _LARGE_INTEGER Interval; // [rsp+60h] [rbp-158h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+68h] [rbp-150h] BYREF
  int v24; // [rsp+70h] [rbp-148h]
  __int64 v25; // [rsp+78h] [rbp-140h] BYREF
  __int64 *v26; // [rsp+80h] [rbp-138h]
  __int64 v27; // [rsp+88h] [rbp-130h]
  __int64 v28; // [rsp+90h] [rbp-128h]
  __int64 v29; // [rsp+98h] [rbp-120h]
  __int64 v30; // [rsp+A0h] [rbp-118h]
  __int64 v31; // [rsp+A8h] [rbp-110h]
  unsigned int *v32; // [rsp+B0h] [rbp-108h]
  PVOID *v33; // [rsp+B8h] [rbp-100h]
  struct _KEVENT Event; // [rsp+C0h] [rbp-F8h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+E0h] [rbp-D8h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+140h] [rbp-78h] BYREF

  v28 = a4;
  v27 = a2;
  v21 = a1;
  v24 = a1;
  v30 = a2;
  v31 = a4;
  v32 = a5;
  v33 = a6;
  memset(&ApcState, 0, sizeof(ApcState));
  memset(&pAsync, 0, sizeof(pAsync));
  Binding = 0;
  memset(&Event, 0, sizeof(Event));
  v20 = 0;
  Interval.QuadPart = 0;
  Reply = 0;
  v17 = 0;
  P = 0;
  v25 = 0;
  v7 = 0;
  v26 = 0;
  if ( a3 )
  {
    v25 = *a3;
    v7 = &v25;
    v26 = &v25;
  }
  CurrentServerSilo = PsGetCurrentServerSilo();
  v9 = PsAttachSiloToCurrentThread(CurrentServerSilo);
  v29 = v9;
  KeStackAttachProcess(g_CiSystemProcess, &ApcState);
  v10 = CipCatDbRpcConnect(&Binding, &v20);
  if ( v10 >= 0 )
  {
    v12 = 0;
    LODWORD(v20) = 0;
    while ( 1 )
    {
      v10 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
      if ( v10 )
        break;
      pAsync.UserInfo = 0;
      pAsync.NotificationType = RpcNotificationTypeEvent;
      KeInitializeEvent(&Event, NotificationEvent, 0);
      pAsync.u.Event = &Event;
      SSCatDBQueryChainByCerts2(
        (unsigned int)&pAsync,
        (_DWORD)Binding,
        v21,
        v27,
        (__int64)v7,
        v28,
        (__int64)&v17,
        (__int64)&P);
      Interval.QuadPart = -150000000;
      v10 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Interval);
      if ( v10 )
      {
        RpcAsyncCancelCall(&pAsync, 1);
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        RpcAsyncCompleteCall(&pAsync, &Reply);
        break;
      }
      v11 = RpcAsyncCompleteCall(&pAsync, &Reply);
      if ( v11 != -1073610728 || v12 >= 0x14 )
      {
        if ( v11 )
          goto LABEL_6;
        if ( Reply )
        {
          v10 = -1073741823;
        }
        else
        {
          for ( i = 0; i < v17; ++i )
          {
            if ( !*((_QWORD *)P + 2 * i + 1) )
            {
              v10 = -1073741811;
              goto LABEL_24;
            }
          }
          *a5 = v17;
          *a6 = P;
          P = 0;
        }
        break;
      }
      LODWORD(v20) = ++v12;
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
  }
  else if ( (_DWORD)v20 == 14 )
  {
    v11 = -1073610729;
    if ( HIDWORD(v20) == -1073610729 )
LABEL_6:
      v10 = v11;
  }
LABEL_24:
  if ( P )
  {
    for ( j = 0; j < v17; ++j )
    {
      v15 = (void *)*((_QWORD *)P + 2 * j + 1);
      if ( v15 )
        ExFreePoolWithTag(v15, 0x63734943u);
    }
    ExFreePoolWithTag(P, 0x63734943u);
  }
  if ( Binding )
    CipCatDbRpcDisconnect(&Binding);
  KeUnstackDetachProcess(&ApcState);
  PsDetachSiloFromCurrentThread(v9);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18008ad14  mov     r11, rsp
0x18008ad17  push    rbx
0x18008ad18  push    rsi
0x18008ad19  push    rdi
0x18008ad1a  push    r12
0x18008ad1c  push    r13
0x18008ad1e  push    r14
0x18008ad20  push    r15
0x18008ad22  sub     rsp, 180h
0x18008ad29  mov     rax, cs:__security_cookie
0x18008ad30  xor     rax, rsp
0x18008ad33  mov     [rsp+1B8h+var_48], rax
0x18008ad3b  mov     [rsp+1B8h+var_128], r9
0x18008ad43  mov     rdi, r8
0x18008ad46  mov     [rsp+1B8h+var_130], rdx
0x18008ad4e  mov     [rsp+1B8h+var_160], ecx
0x18008ad52  mov     [rsp+1B8h+var_148], ecx
0x18008ad56  mov     [rsp+1B8h+var_118], rdx
0x18008ad5e  mov     [rsp+1B8h+var_110], r9
0x18008ad66  mov     r12, [rsp+1B8h+arg_20]
0x18008ad6e  mov     [rsp+1B8h+var_108], r12
0x18008ad76  mov     r13, [rsp+1B8h+arg_28]
0x18008ad7e  mov     [rsp+1B8h+var_100], r13
0x18008ad86  xorps   xmm0, xmm0
0x18008ad89  movups  xmmword ptr [r11-78h], xmm0
0x18008ad8e  movups  xmmword ptr [r11-68h], xmm0
0x18008ad93  movups  xmmword ptr [r11-58h], xmm0
0x18008ad98  xor     edx, edx; Val
0x18008ad9a  lea     r8d, [rdx+58h]; Size
0x18008ad9e  lea     rcx, [r11-0D8h]; void *
0x18008ada5  call    memset
0x18008adaa  xor     ebx, ebx
0x18008adac  mov     [rsp+1B8h+Binding], rbx
0x18008adb1  xorps   xmm0, xmm0
0x18008adb4  xor     eax, eax
0x18008adb6  movups  xmmword ptr [rsp+1B8h+Event.Header], xmm0
0x18008adbe  mov     [rsp+1B8h+Event.Header.WaitListHead.Blink], rax
0x18008adc6  mov     [rsp+1B8h+var_168], rbx
0x18008adcb  mov     qword ptr [rsp+1B8h+Interval], rbx
0x18008add0  mov     [rsp+1B8h+Reply], ebx
0x18008add4  mov     [rsp+1B8h+var_178], ebx
0x18008add8  mov     [rsp+1B8h+P], rbx
0x18008addd  mov     [rsp+1B8h+var_140], rbx
0x18008ade2  mov     r14d, ebx
0x18008ade5  mov     [rsp+1B8h+var_138], rbx
0x18008aded  test    rdi, rdi
0x18008adf0  jz      short loc_18008AE0C
0x18008adf2  mov     eax, [rdi]
0x18008adf4  mov     dword ptr [rsp+1B8h+var_140], eax
0x18008adf8  mov     eax, [rdi+4]
0x18008adfb  mov     dword ptr [rsp+1B8h+var_140+4], eax
0x18008adff  lea     r14, [rsp+1B8h+var_140]
0x18008ae04  mov     [rsp+1B8h+var_138], r14
0x18008ae0c  call    cs:__imp_PsGetCurrentServerSilo
0x18008ae13  nop     dword ptr [rax+rax+00h]
0x18008ae18  mov     rcx, rax
0x18008ae1b  call    cs:__imp_PsAttachSiloToCurrentThread
0x18008ae22  nop     dword ptr [rax+rax+00h]
0x18008ae27  mov     r15, rax
0x18008ae2a  mov     [rsp+1B8h+var_120], rax
0x18008ae32  lea     rdx, [rsp+1B8h+ApcState]; ApcState
0x18008ae3a  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x18008ae41  call    cs:__imp_KeStackAttachProcess
0x18008ae48  nop     dword ptr [rax+rax+00h]
0x18008ae4d  lea     rdx, [rsp+1B8h+var_168]
0x18008ae52  lea     rcx, [rsp+1B8h+Binding]
0x18008ae57  call    CipCatDbRpcConnect
0x18008ae5c  mov     edi, eax
0x18008ae5e  test    eax, eax
0x18008ae60  jns     short loc_18008AE83
0x18008ae62  cmp     dword ptr [rsp+1B8h+var_168], 0Eh
0x18008ae67  jnz     loc_18008B0A9
0x18008ae6d  mov     eax, 0C0020017h
0x18008ae72  cmp     dword ptr [rsp+1B8h+var_168+4], eax
0x18008ae76  jnz     loc_18008B0A9
0x18008ae7c  mov     edi, eax
0x18008ae7e  jmp     loc_18008B0A9
0x18008ae83  mov     esi, ebx
0x18008ae85  mov     dword ptr [rsp+1B8h+var_168], ebx
0x18008ae89  mov     edx, 58h ; 'X'; Size
0x18008ae8e  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x18008ae96  call    cs:__imp_RpcAsyncInitializeHandle
0x18008ae9d  nop     dword ptr [rax+rax+00h]
0x18008aea2  mov     edi, eax
0x18008aea4  test    eax, eax
0x18008aea6  jnz     loc_18008B0A9
0x18008aeac  mov     [rsp+1B8h+pAsync.UserInfo], rbx
0x18008aeb4  mov     [rsp+1B8h+pAsync.NotificationType], 1
0x18008aebf  xor     r8d, r8d; State
0x18008aec2  xor     edx, edx; Type
0x18008aec4  lea     rcx, [rsp+1B8h+Event]; Event
0x18008aecc  call    cs:__imp_KeInitializeEvent
0x18008aed3  nop     dword ptr [rax+rax+00h]
0x18008aed8  lea     rax, [rsp+1B8h+Event]
0x18008aee0  mov     qword ptr [rsp+1B8h+pAsync.u], rax
0x18008aee8  lea     rax, [rsp+1B8h+P]
0x18008aeed  mov     [rsp+1B8h+var_180], rax
0x18008aef2  lea     rax, [rsp+1B8h+var_178]
0x18008aef7  mov     [rsp+1B8h+var_188], rax
0x18008aefc  mov     rax, [rsp+1B8h+var_128]
0x18008af04  mov     [rsp+1B8h+var_190], rax
0x18008af09  mov     [rsp+1B8h+Timeout], r14
0x18008af0e  mov     r9, [rsp+1B8h+var_130]
0x18008af16  mov     r8d, [rsp+1B8h+var_160]
0x18008af1b  mov     rdx, [rsp+1B8h+Binding]
0x18008af20  lea     rcx, [rsp+1B8h+pAsync]
0x18008af28  call    SSCatDBQueryChainByCerts2
0x18008af2d  jmp     short loc_18008AF7F
0x18008af2f  mov     edi, eax
0x18008af31  xor     ebx, ebx
0x18008af33  mov     esi, dword ptr [rsp+1B8h+var_168]
0x18008af37  mov     r14, [rsp+1B8h+var_138]
0x18008af3f  mov     r15, [rsp+1B8h+var_120]
0x18008af47  mov     eax, [rsp+1B8h+var_148]
0x18008af4b  mov     [rsp+1B8h+var_160], eax
0x18008af4f  mov     rax, [rsp+1B8h+var_118]
0x18008af57  mov     [rsp+1B8h+var_130], rax
0x18008af5f  mov     rax, [rsp+1B8h+var_110]
0x18008af67  mov     [rsp+1B8h+var_128], rax
0x18008af6f  mov     r12, [rsp+1B8h+var_108]
0x18008af77  mov     r13, [rsp+1B8h+var_100]
0x18008af7f  test    edi, edi
0x18008af81  jnz     loc_18008B0A9
0x18008af87  mov     qword ptr [rsp+1B8h+Interval], 0FFFFFFFFF70F2E80h
0x18008af90  lea     rax, [rsp+1B8h+Interval]
0x18008af95  mov     [rsp+1B8h+Timeout], rax; Timeout
0x18008af9a  xor     r9d, r9d; Alertable
0x18008af9d  xor     r8d, r8d; WaitMode
0x18008afa0  xor     edx, edx; WaitReason
0x18008afa2  lea     rcx, [rsp+1B8h+Event]; Object
0x18008afaa  call    cs:__imp_KeWaitForSingleObject
0x18008afb1  nop     dword ptr [rax+rax+00h]
0x18008afb6  mov     edi, eax
0x18008afb8  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x18008afc0  test    eax, eax
0x18008afc2  jz      short loc_18008B014
0x18008afc4  mov     edx, 1; fAbort
0x18008afc9  call    cs:__imp_RpcAsyncCancelCall
0x18008afd0  nop     dword ptr [rax+rax+00h]
0x18008afd5  mov     [rsp+1B8h+Timeout], rbx; Timeout
0x18008afda  xor     r9d, r9d; Alertable
0x18008afdd  xor     r8d, r8d; WaitMode
0x18008afe0  xor     edx, edx; WaitReason
0x18008afe2  lea     rcx, [rsp+1B8h+Event]; Object
0x18008afea  call    cs:__imp_KeWaitForSingleObject
0x18008aff1  nop     dword ptr [rax+rax+00h]
0x18008aff6  lea     rdx, [rsp+1B8h+Reply]; Reply
0x18008affb  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x18008b003  call    cs:__imp_RpcAsyncCompleteCall
0x18008b00a  nop     dword ptr [rax+rax+00h]
0x18008b00f  jmp     loc_18008B0A9
0x18008b014  lea     rdx, [rsp+1B8h+Reply]; Reply
0x18008b019  call    cs:__imp_RpcAsyncCompleteCall
0x18008b020  nop     dword ptr [rax+rax+00h]
0x18008b025  cmp     eax, 0C0020018h
0x18008b02a  jnz     short loc_18008B05A
0x18008b02c  cmp     esi, 14h
0x18008b02f  jnb     short loc_18008B05A
0x18008b031  inc     esi
0x18008b033  mov     dword ptr [rsp+1B8h+var_168], esi
0x18008b037  mov     qword ptr [rsp+1B8h+Interval], 0FFFFFFFFFFF0BDC0h
0x18008b040  lea     r8, [rsp+1B8h+Interval]; Interval
0x18008b045  xor     edx, edx; Alertable
0x18008b047  xor     ecx, ecx; WaitMode
0x18008b049  call    cs:__imp_KeDelayExecutionThread
0x18008b050  nop     dword ptr [rax+rax+00h]
0x18008b055  jmp     loc_18008AE89
0x18008b05a  test    eax, eax
0x18008b05c  jnz     loc_18008AE7C
0x18008b062  cmp     [rsp+1B8h+Reply], ebx
0x18008b066  jz      short loc_18008B06F
0x18008b068  mov     edi, 0C0000001h
0x18008b06d  jmp     short loc_18008B0A9
0x18008b06f  mov     edx, ebx
0x18008b071  cmp     edx, [rsp+1B8h+var_178]
0x18008b075  jnb     short loc_18008B093
0x18008b077  mov     ecx, edx
0x18008b079  add     rcx, rcx
0x18008b07c  mov     rax, [rsp+1B8h+P]
0x18008b081  cmp     [rax+rcx*8+8], rbx
0x18008b086  jz      short loc_18008B08C
0x18008b088  inc     edx
0x18008b08a  jmp     short loc_18008B071
0x18008b08c  mov     edi, 0C000000Dh
0x18008b091  jmp     short loc_18008B0A9
0x18008b093  mov     eax, [rsp+1B8h+var_178]
0x18008b097  mov     [r12], eax
0x18008b09b  mov     rax, [rsp+1B8h+P]
0x18008b0a0  mov     [r13+0], rax
0x18008b0a4  mov     [rsp+1B8h+P], rbx
0x18008b0a9  cmp     [rsp+1B8h+P], rbx
0x18008b0ae  jz      short loc_18008B0FB
0x18008b0b0  mov     esi, ebx
0x18008b0b2  cmp     [rsp+1B8h+var_178], ebx
0x18008b0b6  jbe     short loc_18008B0E5
0x18008b0b8  mov     ecx, esi
0x18008b0ba  add     rcx, rcx
0x18008b0bd  mov     rax, [rsp+1B8h+P]
0x18008b0c2  mov     rcx, [rax+rcx*8+8]; P
0x18008b0c7  test    rcx, rcx
0x18008b0ca  jz      short loc_18008B0DD
0x18008b0cc  mov     edx, 63734943h; Tag
0x18008b0d1  call    cs:__imp_ExFreePoolWithTag
0x18008b0d8  nop     dword ptr [rax+rax+00h]
0x18008b0dd  inc     esi
0x18008b0df  cmp     esi, [rsp+1B8h+var_178]
0x18008b0e3  jb      short loc_18008B0B8
0x18008b0e5  mov     edx, 63734943h; Tag
0x18008b0ea  mov     rcx, [rsp+1B8h+P]; P
0x18008b0ef  call    cs:__imp_ExFreePoolWithTag
0x18008b0f6  nop     dword ptr [rax+rax+00h]
0x18008b0fb  cmp     [rsp+1B8h+Binding], rbx
0x18008b100  jz      short loc_18008B10C
0x18008b102  lea     rcx, [rsp+1B8h+Binding]; Binding
0x18008b107  call    CipCatDbRpcDisconnect
0x18008b10c  lea     rcx, [rsp+1B8h+ApcState]; ApcState
0x18008b114  call    cs:__imp_KeUnstackDetachProcess
0x18008b11b  nop     dword ptr [rax+rax+00h]
0x18008b120  mov     rcx, r15
0x18008b123  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18008b12a  nop     dword ptr [rax+rax+00h]
0x18008b12f  mov     eax, edi
0x18008b131  mov     rcx, [rsp+1B8h+var_48]
0x18008b139  xor     rcx, rsp; StackCookie
0x18008b13c  call    __security_check_cookie
0x18008b141  add     rsp, 180h
0x18008b148  pop     r15
0x18008b14a  pop     r14
0x18008b14c  pop     r13
0x18008b14e  pop     r12
0x18008b150  pop     rdi
0x18008b151  pop     rsi
0x18008b152  pop     rbx
0x18008b153  retn
0x1800e96d0  push    rbp
0x1800e96d2  sub     rsp, 40h
0x1800e96d6  mov     rbp, rdx
0x1800e96d9  mov     rcx, [rcx]
0x1800e96dc  mov     ecx, [rcx]; ExceptionCode
0x1800e96de  call    cs:__imp_I_RpcExceptionFilter
0x1800e96e5  nop     dword ptr [rax+rax+00h]
0x1800e96ea  nop
0x1800e96eb  add     rsp, 40h
0x1800e96ef  pop     rbp
0x1800e96f0  retn
```
