# CiAuthRootQueryChainByCerts

- ea: `0x18009bf5c`
- end: `0x18009c39d`
- name: `CiAuthRootQueryChainByCerts`
- size: `1089`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800e5990`

## callees

- `0x180020738`
- `0x18002c0d0`
- `0x18002c500`
- `0x18009bf5c`
- `0x18009c3a4`
- `0x1800bba44`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x18009c089`
- `ntoskrnl!KeStackAttachProcess` at `0x18009c089`
- `ntoskrnl!ExFreePoolWithTag` at `0x18009c319`
- `ntoskrnl!ExFreePoolWithTag` at `0x18009c337`
- `ntoskrnl!ExFreePoolWithTag` at `0x18009c319`
- `ntoskrnl!ExFreePoolWithTag` at `0x18009c337`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009c35c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18009c35c`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18009c063`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x18009c063`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18009c36b`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18009c36b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18009c054`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x18009c054`
- `ntoskrnl!KeDelayExecutionThread` at `0x18009c291`
- `ntoskrnl!KeDelayExecutionThread` at `0x18009c291`
- `ntoskrnl!KeInitializeEvent` at `0x18009c114`
- `ntoskrnl!KeInitializeEvent` at `0x18009c114`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009c1f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009c232`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009c1f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x18009c232`
- `msrpc!RpcAsyncCancelCall` at `0x18009c211`
- `msrpc!RpcAsyncCancelCall` at `0x18009c211`
- `msrpc!RpcAsyncCompleteCall` at `0x18009c24b`
- `msrpc!RpcAsyncCompleteCall` at `0x18009c261`
- `msrpc!RpcAsyncCompleteCall` at `0x18009c24b`
- `msrpc!RpcAsyncCompleteCall` at `0x18009c261`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea2a0`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea2a0`
- `msrpc!RpcAsyncInitializeHandle` at `0x18009c0de`
- `msrpc!RpcAsyncInitializeHandle` at `0x18009c0de`

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
0x18009bf5c  mov     r11, rsp
0x18009bf5f  push    rbx
0x18009bf60  push    rsi
0x18009bf61  push    rdi
0x18009bf62  push    r12
0x18009bf64  push    r13
0x18009bf66  push    r14
0x18009bf68  push    r15
0x18009bf6a  sub     rsp, 180h
0x18009bf71  mov     rax, cs:__security_cookie
0x18009bf78  xor     rax, rsp
0x18009bf7b  mov     [rsp+1B8h+var_48], rax
0x18009bf83  mov     [rsp+1B8h+var_128], r9
0x18009bf8b  mov     rdi, r8
0x18009bf8e  mov     [rsp+1B8h+var_130], rdx
0x18009bf96  mov     [rsp+1B8h+var_160], ecx
0x18009bf9a  mov     [rsp+1B8h+var_148], ecx
0x18009bf9e  mov     [rsp+1B8h+var_118], rdx
0x18009bfa6  mov     [rsp+1B8h+var_110], r9
0x18009bfae  mov     r12, [rsp+1B8h+arg_20]
0x18009bfb6  mov     [rsp+1B8h+var_108], r12
0x18009bfbe  mov     r13, [rsp+1B8h+arg_28]
0x18009bfc6  mov     [rsp+1B8h+var_100], r13
0x18009bfce  xorps   xmm0, xmm0
0x18009bfd1  movups  xmmword ptr [r11-78h], xmm0
0x18009bfd6  movups  xmmword ptr [r11-68h], xmm0
0x18009bfdb  movups  xmmword ptr [r11-58h], xmm0
0x18009bfe0  xor     edx, edx; Val
0x18009bfe2  lea     r8d, [rdx+58h]; Size
0x18009bfe6  lea     rcx, [r11-0D8h]; void *
0x18009bfed  call    memset
0x18009bff2  xor     ebx, ebx
0x18009bff4  mov     [rsp+1B8h+Binding], rbx
0x18009bff9  xorps   xmm0, xmm0
0x18009bffc  xor     eax, eax
0x18009bffe  movups  xmmword ptr [rsp+1B8h+Event.Header], xmm0
0x18009c006  mov     [rsp+1B8h+Event.Header.WaitListHead.Blink], rax
0x18009c00e  mov     [rsp+1B8h+var_168], rbx
0x18009c013  mov     qword ptr [rsp+1B8h+Interval], rbx
0x18009c018  mov     [rsp+1B8h+Reply], ebx
0x18009c01c  mov     [rsp+1B8h+var_178], ebx
0x18009c020  mov     [rsp+1B8h+P], rbx
0x18009c025  mov     [rsp+1B8h+var_140], rbx
0x18009c02a  mov     r14d, ebx
0x18009c02d  mov     [rsp+1B8h+var_138], rbx
0x18009c035  test    rdi, rdi
0x18009c038  jz      short loc_18009C054
0x18009c03a  mov     eax, [rdi]
0x18009c03c  mov     dword ptr [rsp+1B8h+var_140], eax
0x18009c040  mov     eax, [rdi+4]
0x18009c043  mov     dword ptr [rsp+1B8h+var_140+4], eax
0x18009c047  lea     r14, [rsp+1B8h+var_140]
0x18009c04c  mov     [rsp+1B8h+var_138], r14
0x18009c054  call    cs:__imp_PsGetCurrentServerSilo
0x18009c05b  nop     dword ptr [rax+rax+00h]
0x18009c060  mov     rcx, rax
0x18009c063  call    cs:__imp_PsAttachSiloToCurrentThread
0x18009c06a  nop     dword ptr [rax+rax+00h]
0x18009c06f  mov     r15, rax
0x18009c072  mov     [rsp+1B8h+var_120], rax
0x18009c07a  lea     rdx, [rsp+1B8h+ApcState]; ApcState
0x18009c082  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x18009c089  call    cs:__imp_KeStackAttachProcess
0x18009c090  nop     dword ptr [rax+rax+00h]
0x18009c095  lea     rdx, [rsp+1B8h+var_168]
0x18009c09a  lea     rcx, [rsp+1B8h+Binding]
0x18009c09f  call    CipCatDbRpcConnect
0x18009c0a4  mov     edi, eax
0x18009c0a6  test    eax, eax
0x18009c0a8  jns     short loc_18009C0CB
0x18009c0aa  cmp     dword ptr [rsp+1B8h+var_168], 0Eh
0x18009c0af  jnz     loc_18009C2F1
0x18009c0b5  mov     eax, 0C0020017h
0x18009c0ba  cmp     dword ptr [rsp+1B8h+var_168+4], eax
0x18009c0be  jnz     loc_18009C2F1
0x18009c0c4  mov     edi, eax
0x18009c0c6  jmp     loc_18009C2F1
0x18009c0cb  mov     esi, ebx
0x18009c0cd  mov     dword ptr [rsp+1B8h+var_168], ebx
0x18009c0d1  mov     edx, 58h ; 'X'; Size
0x18009c0d6  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x18009c0de  call    cs:__imp_RpcAsyncInitializeHandle
0x18009c0e5  nop     dword ptr [rax+rax+00h]
0x18009c0ea  mov     edi, eax
0x18009c0ec  test    eax, eax
0x18009c0ee  jnz     loc_18009C2F1
0x18009c0f4  mov     [rsp+1B8h+pAsync.UserInfo], rbx
0x18009c0fc  mov     [rsp+1B8h+pAsync.NotificationType], 1
0x18009c107  xor     r8d, r8d; State
0x18009c10a  xor     edx, edx; Type
0x18009c10c  lea     rcx, [rsp+1B8h+Event]; Event
0x18009c114  call    cs:__imp_KeInitializeEvent
0x18009c11b  nop     dword ptr [rax+rax+00h]
0x18009c120  lea     rax, [rsp+1B8h+Event]
0x18009c128  mov     qword ptr [rsp+1B8h+pAsync.u], rax
0x18009c130  lea     rax, [rsp+1B8h+P]
0x18009c135  mov     [rsp+1B8h+var_180], rax
0x18009c13a  lea     rax, [rsp+1B8h+var_178]
0x18009c13f  mov     [rsp+1B8h+var_188], rax
0x18009c144  mov     rax, [rsp+1B8h+var_128]
0x18009c14c  mov     [rsp+1B8h+var_190], rax
0x18009c151  mov     [rsp+1B8h+Timeout], r14
0x18009c156  mov     r9, [rsp+1B8h+var_130]
0x18009c15e  mov     r8d, [rsp+1B8h+var_160]
0x18009c163  mov     rdx, [rsp+1B8h+Binding]
0x18009c168  lea     rcx, [rsp+1B8h+pAsync]
0x18009c170  call    SSCatDBQueryChainByCerts2
0x18009c175  jmp     short loc_18009C1C7
0x18009c177  mov     edi, eax
0x18009c179  xor     ebx, ebx
0x18009c17b  mov     esi, dword ptr [rsp+1B8h+var_168]
0x18009c17f  mov     r14, [rsp+1B8h+var_138]
0x18009c187  mov     r15, [rsp+1B8h+var_120]
0x18009c18f  mov     eax, [rsp+1B8h+var_148]
0x18009c193  mov     [rsp+1B8h+var_160], eax
0x18009c197  mov     rax, [rsp+1B8h+var_118]
0x18009c19f  mov     [rsp+1B8h+var_130], rax
0x18009c1a7  mov     rax, [rsp+1B8h+var_110]
0x18009c1af  mov     [rsp+1B8h+var_128], rax
0x18009c1b7  mov     r12, [rsp+1B8h+var_108]
0x18009c1bf  mov     r13, [rsp+1B8h+var_100]
0x18009c1c7  test    edi, edi
0x18009c1c9  jnz     loc_18009C2F1
0x18009c1cf  mov     qword ptr [rsp+1B8h+Interval], 0FFFFFFFFF70F2E80h
0x18009c1d8  lea     rax, [rsp+1B8h+Interval]
0x18009c1dd  mov     [rsp+1B8h+Timeout], rax; Timeout
0x18009c1e2  xor     r9d, r9d; Alertable
0x18009c1e5  xor     r8d, r8d; WaitMode
0x18009c1e8  xor     edx, edx; WaitReason
0x18009c1ea  lea     rcx, [rsp+1B8h+Event]; Object
0x18009c1f2  call    cs:__imp_KeWaitForSingleObject
0x18009c1f9  nop     dword ptr [rax+rax+00h]
0x18009c1fe  mov     edi, eax
0x18009c200  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x18009c208  test    eax, eax
0x18009c20a  jz      short loc_18009C25C
0x18009c20c  mov     edx, 1; fAbort
0x18009c211  call    cs:__imp_RpcAsyncCancelCall
0x18009c218  nop     dword ptr [rax+rax+00h]
0x18009c21d  mov     [rsp+1B8h+Timeout], rbx; Timeout
0x18009c222  xor     r9d, r9d; Alertable
0x18009c225  xor     r8d, r8d; WaitMode
0x18009c228  xor     edx, edx; WaitReason
0x18009c22a  lea     rcx, [rsp+1B8h+Event]; Object
0x18009c232  call    cs:__imp_KeWaitForSingleObject
0x18009c239  nop     dword ptr [rax+rax+00h]
0x18009c23e  lea     rdx, [rsp+1B8h+Reply]; Reply
0x18009c243  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x18009c24b  call    cs:__imp_RpcAsyncCompleteCall
0x18009c252  nop     dword ptr [rax+rax+00h]
0x18009c257  jmp     loc_18009C2F1
0x18009c25c  lea     rdx, [rsp+1B8h+Reply]; Reply
0x18009c261  call    cs:__imp_RpcAsyncCompleteCall
0x18009c268  nop     dword ptr [rax+rax+00h]
0x18009c26d  cmp     eax, 0C0020018h
0x18009c272  jnz     short loc_18009C2A2
0x18009c274  cmp     esi, 14h
0x18009c277  jnb     short loc_18009C2A2
0x18009c279  inc     esi
0x18009c27b  mov     dword ptr [rsp+1B8h+var_168], esi
0x18009c27f  mov     qword ptr [rsp+1B8h+Interval], 0FFFFFFFFFFF0BDC0h
0x18009c288  lea     r8, [rsp+1B8h+Interval]; Interval
0x18009c28d  xor     edx, edx; Alertable
0x18009c28f  xor     ecx, ecx; WaitMode
0x18009c291  call    cs:__imp_KeDelayExecutionThread
0x18009c298  nop     dword ptr [rax+rax+00h]
0x18009c29d  jmp     loc_18009C0D1
0x18009c2a2  test    eax, eax
0x18009c2a4  jnz     loc_18009C0C4
0x18009c2aa  cmp     [rsp+1B8h+Reply], ebx
0x18009c2ae  jz      short loc_18009C2B7
0x18009c2b0  mov     edi, 0C0000001h
0x18009c2b5  jmp     short loc_18009C2F1
0x18009c2b7  mov     edx, ebx
0x18009c2b9  cmp     edx, [rsp+1B8h+var_178]
0x18009c2bd  jnb     short loc_18009C2DB
0x18009c2bf  mov     ecx, edx
0x18009c2c1  add     rcx, rcx
0x18009c2c4  mov     rax, [rsp+1B8h+P]
0x18009c2c9  cmp     [rax+rcx*8+8], rbx
0x18009c2ce  jz      short loc_18009C2D4
0x18009c2d0  inc     edx
0x18009c2d2  jmp     short loc_18009C2B9
0x18009c2d4  mov     edi, 0C000000Dh
0x18009c2d9  jmp     short loc_18009C2F1
0x18009c2db  mov     eax, [rsp+1B8h+var_178]
0x18009c2df  mov     [r12], eax
0x18009c2e3  mov     rax, [rsp+1B8h+P]
0x18009c2e8  mov     [r13+0], rax
0x18009c2ec  mov     [rsp+1B8h+P], rbx
0x18009c2f1  cmp     [rsp+1B8h+P], rbx
0x18009c2f6  jz      short loc_18009C343
0x18009c2f8  mov     esi, ebx
0x18009c2fa  cmp     [rsp+1B8h+var_178], ebx
0x18009c2fe  jbe     short loc_18009C32D
0x18009c300  mov     ecx, esi
0x18009c302  add     rcx, rcx
0x18009c305  mov     rax, [rsp+1B8h+P]
0x18009c30a  mov     rcx, [rax+rcx*8+8]; P
0x18009c30f  test    rcx, rcx
0x18009c312  jz      short loc_18009C325
0x18009c314  mov     edx, 63734943h; Tag
0x18009c319  call    cs:__imp_ExFreePoolWithTag
0x18009c320  nop     dword ptr [rax+rax+00h]
0x18009c325  inc     esi
0x18009c327  cmp     esi, [rsp+1B8h+var_178]
0x18009c32b  jb      short loc_18009C300
0x18009c32d  mov     edx, 63734943h; Tag
0x18009c332  mov     rcx, [rsp+1B8h+P]; P
0x18009c337  call    cs:__imp_ExFreePoolWithTag
0x18009c33e  nop     dword ptr [rax+rax+00h]
0x18009c343  cmp     [rsp+1B8h+Binding], rbx
0x18009c348  jz      short loc_18009C354
0x18009c34a  lea     rcx, [rsp+1B8h+Binding]; Binding
0x18009c34f  call    CipCatDbRpcDisconnect
0x18009c354  lea     rcx, [rsp+1B8h+ApcState]; ApcState
0x18009c35c  call    cs:__imp_KeUnstackDetachProcess
0x18009c363  nop     dword ptr [rax+rax+00h]
0x18009c368  mov     rcx, r15
0x18009c36b  call    cs:__imp_PsDetachSiloFromCurrentThread
0x18009c372  nop     dword ptr [rax+rax+00h]
0x18009c377  mov     eax, edi
0x18009c379  mov     rcx, [rsp+1B8h+var_48]
0x18009c381  xor     rcx, rsp; StackCookie
0x18009c384  call    __security_check_cookie
0x18009c389  add     rsp, 180h
0x18009c390  pop     r15
0x18009c392  pop     r14
0x18009c394  pop     r13
0x18009c396  pop     r12
0x18009c398  pop     rdi
0x18009c399  pop     rsi
0x18009c39a  pop     rbx
0x18009c39b  retn
0x1800ea292  push    rbp
0x1800ea294  sub     rsp, 40h
0x1800ea298  mov     rbp, rdx
0x1800ea29b  mov     rcx, [rcx]
0x1800ea29e  mov     ecx, [rcx]; ExceptionCode
0x1800ea2a0  call    cs:__imp_I_RpcExceptionFilter
0x1800ea2a7  nop     dword ptr [rax+rax+00h]
0x1800ea2ac  nop
0x1800ea2ad  add     rsp, 40h
0x1800ea2b1  pop     rbp
0x1800ea2b2  retn
```
