# CiAuthRootQueryChainByCerts

- ea: `0x1800896e4`
- end: `0x180089b25`
- name: `CiAuthRootQueryChainByCerts`
- size: `1089`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1800dbbf8`

## callees

- `0x1800206f8`
- `0x18002bef0`
- `0x18002c340`
- `0x1800896e4`
- `0x180089b2c`
- `0x1800ba724`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x180089811`
- `ntoskrnl!KeStackAttachProcess` at `0x180089811`
- `ntoskrnl!ExFreePoolWithTag` at `0x180089aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180089abf`
- `ntoskrnl!ExFreePoolWithTag` at `0x180089aa1`
- `ntoskrnl!ExFreePoolWithTag` at `0x180089abf`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180089ae4`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180089ae4`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800897eb`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800897eb`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180089af3`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180089af3`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800897dc`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800897dc`
- `ntoskrnl!KeDelayExecutionThread` at `0x180089a19`
- `ntoskrnl!KeDelayExecutionThread` at `0x180089a19`
- `ntoskrnl!KeInitializeEvent` at `0x18008989c`
- `ntoskrnl!KeInitializeEvent` at `0x18008989c`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008997a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800899ba`
- `ntoskrnl!KeWaitForSingleObject` at `0x18008997a`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800899ba`
- `msrpc!RpcAsyncCancelCall` at `0x180089999`
- `msrpc!RpcAsyncCancelCall` at `0x180089999`
- `msrpc!RpcAsyncCompleteCall` at `0x1800899d3`
- `msrpc!RpcAsyncCompleteCall` at `0x1800899e9`
- `msrpc!RpcAsyncCompleteCall` at `0x1800899d3`
- `msrpc!RpcAsyncCompleteCall` at `0x1800899e9`
- `msrpc!I_RpcExceptionFilter` at `0x1800e7f3e`
- `msrpc!I_RpcExceptionFilter` at `0x1800e7f3e`
- `msrpc!RpcAsyncInitializeHandle` at `0x180089866`
- `msrpc!RpcAsyncInitializeHandle` at `0x180089866`

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
0x1800896e4  mov     r11, rsp
0x1800896e7  push    rbx
0x1800896e8  push    rsi
0x1800896e9  push    rdi
0x1800896ea  push    r12
0x1800896ec  push    r13
0x1800896ee  push    r14
0x1800896f0  push    r15
0x1800896f2  sub     rsp, 180h
0x1800896f9  mov     rax, cs:__security_cookie
0x180089700  xor     rax, rsp
0x180089703  mov     [rsp+1B8h+var_48], rax
0x18008970b  mov     [rsp+1B8h+var_128], r9
0x180089713  mov     rdi, r8
0x180089716  mov     [rsp+1B8h+var_130], rdx
0x18008971e  mov     [rsp+1B8h+var_160], ecx
0x180089722  mov     [rsp+1B8h+var_148], ecx
0x180089726  mov     [rsp+1B8h+var_118], rdx
0x18008972e  mov     [rsp+1B8h+var_110], r9
0x180089736  mov     r12, [rsp+1B8h+arg_20]
0x18008973e  mov     [rsp+1B8h+var_108], r12
0x180089746  mov     r13, [rsp+1B8h+arg_28]
0x18008974e  mov     [rsp+1B8h+var_100], r13
0x180089756  xorps   xmm0, xmm0
0x180089759  movups  xmmword ptr [r11-78h], xmm0
0x18008975e  movups  xmmword ptr [r11-68h], xmm0
0x180089763  movups  xmmword ptr [r11-58h], xmm0
0x180089768  xor     edx, edx; Val
0x18008976a  lea     r8d, [rdx+58h]; Size
0x18008976e  lea     rcx, [r11-0D8h]; void *
0x180089775  call    memset
0x18008977a  xor     ebx, ebx
0x18008977c  mov     [rsp+1B8h+Binding], rbx
0x180089781  xorps   xmm0, xmm0
0x180089784  xor     eax, eax
0x180089786  movups  xmmword ptr [rsp+1B8h+Event.Header], xmm0
0x18008978e  mov     [rsp+1B8h+Event.Header.WaitListHead.Blink], rax
0x180089796  mov     [rsp+1B8h+var_168], rbx
0x18008979b  mov     qword ptr [rsp+1B8h+Interval], rbx
0x1800897a0  mov     [rsp+1B8h+Reply], ebx
0x1800897a4  mov     [rsp+1B8h+var_178], ebx
0x1800897a8  mov     [rsp+1B8h+P], rbx
0x1800897ad  mov     [rsp+1B8h+var_140], rbx
0x1800897b2  mov     r14d, ebx
0x1800897b5  mov     [rsp+1B8h+var_138], rbx
0x1800897bd  test    rdi, rdi
0x1800897c0  jz      short loc_1800897DC
0x1800897c2  mov     eax, [rdi]
0x1800897c4  mov     dword ptr [rsp+1B8h+var_140], eax
0x1800897c8  mov     eax, [rdi+4]
0x1800897cb  mov     dword ptr [rsp+1B8h+var_140+4], eax
0x1800897cf  lea     r14, [rsp+1B8h+var_140]
0x1800897d4  mov     [rsp+1B8h+var_138], r14
0x1800897dc  call    cs:__imp_PsGetCurrentServerSilo
0x1800897e3  nop     dword ptr [rax+rax+00h]
0x1800897e8  mov     rcx, rax
0x1800897eb  call    cs:__imp_PsAttachSiloToCurrentThread
0x1800897f2  nop     dword ptr [rax+rax+00h]
0x1800897f7  mov     r15, rax
0x1800897fa  mov     [rsp+1B8h+var_120], rax
0x180089802  lea     rdx, [rsp+1B8h+ApcState]; ApcState
0x18008980a  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180089811  call    cs:__imp_KeStackAttachProcess
0x180089818  nop     dword ptr [rax+rax+00h]
0x18008981d  lea     rdx, [rsp+1B8h+var_168]
0x180089822  lea     rcx, [rsp+1B8h+Binding]
0x180089827  call    CipCatDbRpcConnect
0x18008982c  mov     edi, eax
0x18008982e  test    eax, eax
0x180089830  jns     short loc_180089853
0x180089832  cmp     dword ptr [rsp+1B8h+var_168], 0Eh
0x180089837  jnz     loc_180089A79
0x18008983d  mov     eax, 0C0020017h
0x180089842  cmp     dword ptr [rsp+1B8h+var_168+4], eax
0x180089846  jnz     loc_180089A79
0x18008984c  mov     edi, eax
0x18008984e  jmp     loc_180089A79
0x180089853  mov     esi, ebx
0x180089855  mov     dword ptr [rsp+1B8h+var_168], ebx
0x180089859  mov     edx, 58h ; 'X'; Size
0x18008985e  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x180089866  call    cs:__imp_RpcAsyncInitializeHandle
0x18008986d  nop     dword ptr [rax+rax+00h]
0x180089872  mov     edi, eax
0x180089874  test    eax, eax
0x180089876  jnz     loc_180089A79
0x18008987c  mov     [rsp+1B8h+pAsync.UserInfo], rbx
0x180089884  mov     [rsp+1B8h+pAsync.NotificationType], 1
0x18008988f  xor     r8d, r8d; State
0x180089892  xor     edx, edx; Type
0x180089894  lea     rcx, [rsp+1B8h+Event]; Event
0x18008989c  call    cs:__imp_KeInitializeEvent
0x1800898a3  nop     dword ptr [rax+rax+00h]
0x1800898a8  lea     rax, [rsp+1B8h+Event]
0x1800898b0  mov     qword ptr [rsp+1B8h+pAsync.u], rax
0x1800898b8  lea     rax, [rsp+1B8h+P]
0x1800898bd  mov     [rsp+1B8h+var_180], rax
0x1800898c2  lea     rax, [rsp+1B8h+var_178]
0x1800898c7  mov     [rsp+1B8h+var_188], rax
0x1800898cc  mov     rax, [rsp+1B8h+var_128]
0x1800898d4  mov     [rsp+1B8h+var_190], rax
0x1800898d9  mov     [rsp+1B8h+Timeout], r14
0x1800898de  mov     r9, [rsp+1B8h+var_130]
0x1800898e6  mov     r8d, [rsp+1B8h+var_160]
0x1800898eb  mov     rdx, [rsp+1B8h+Binding]
0x1800898f0  lea     rcx, [rsp+1B8h+pAsync]
0x1800898f8  call    SSCatDBQueryChainByCerts2
0x1800898fd  jmp     short loc_18008994F
0x1800898ff  mov     edi, eax
0x180089901  xor     ebx, ebx
0x180089903  mov     esi, dword ptr [rsp+1B8h+var_168]
0x180089907  mov     r14, [rsp+1B8h+var_138]
0x18008990f  mov     r15, [rsp+1B8h+var_120]
0x180089917  mov     eax, [rsp+1B8h+var_148]
0x18008991b  mov     [rsp+1B8h+var_160], eax
0x18008991f  mov     rax, [rsp+1B8h+var_118]
0x180089927  mov     [rsp+1B8h+var_130], rax
0x18008992f  mov     rax, [rsp+1B8h+var_110]
0x180089937  mov     [rsp+1B8h+var_128], rax
0x18008993f  mov     r12, [rsp+1B8h+var_108]
0x180089947  mov     r13, [rsp+1B8h+var_100]
0x18008994f  test    edi, edi
0x180089951  jnz     loc_180089A79
0x180089957  mov     qword ptr [rsp+1B8h+Interval], 0FFFFFFFFF70F2E80h
0x180089960  lea     rax, [rsp+1B8h+Interval]
0x180089965  mov     [rsp+1B8h+Timeout], rax; Timeout
0x18008996a  xor     r9d, r9d; Alertable
0x18008996d  xor     r8d, r8d; WaitMode
0x180089970  xor     edx, edx; WaitReason
0x180089972  lea     rcx, [rsp+1B8h+Event]; Object
0x18008997a  call    cs:__imp_KeWaitForSingleObject
0x180089981  nop     dword ptr [rax+rax+00h]
0x180089986  mov     edi, eax
0x180089988  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x180089990  test    eax, eax
0x180089992  jz      short loc_1800899E4
0x180089994  mov     edx, 1; fAbort
0x180089999  call    cs:__imp_RpcAsyncCancelCall
0x1800899a0  nop     dword ptr [rax+rax+00h]
0x1800899a5  mov     [rsp+1B8h+Timeout], rbx; Timeout
0x1800899aa  xor     r9d, r9d; Alertable
0x1800899ad  xor     r8d, r8d; WaitMode
0x1800899b0  xor     edx, edx; WaitReason
0x1800899b2  lea     rcx, [rsp+1B8h+Event]; Object
0x1800899ba  call    cs:__imp_KeWaitForSingleObject
0x1800899c1  nop     dword ptr [rax+rax+00h]
0x1800899c6  lea     rdx, [rsp+1B8h+Reply]; Reply
0x1800899cb  lea     rcx, [rsp+1B8h+pAsync]; pAsync
0x1800899d3  call    cs:__imp_RpcAsyncCompleteCall
0x1800899da  nop     dword ptr [rax+rax+00h]
0x1800899df  jmp     loc_180089A79
0x1800899e4  lea     rdx, [rsp+1B8h+Reply]; Reply
0x1800899e9  call    cs:__imp_RpcAsyncCompleteCall
0x1800899f0  nop     dword ptr [rax+rax+00h]
0x1800899f5  cmp     eax, 0C0020018h
0x1800899fa  jnz     short loc_180089A2A
0x1800899fc  cmp     esi, 14h
0x1800899ff  jnb     short loc_180089A2A
0x180089a01  inc     esi
0x180089a03  mov     dword ptr [rsp+1B8h+var_168], esi
0x180089a07  mov     qword ptr [rsp+1B8h+Interval], 0FFFFFFFFFFF0BDC0h
0x180089a10  lea     r8, [rsp+1B8h+Interval]; Interval
0x180089a15  xor     edx, edx; Alertable
0x180089a17  xor     ecx, ecx; WaitMode
0x180089a19  call    cs:__imp_KeDelayExecutionThread
0x180089a20  nop     dword ptr [rax+rax+00h]
0x180089a25  jmp     loc_180089859
0x180089a2a  test    eax, eax
0x180089a2c  jnz     loc_18008984C
0x180089a32  cmp     [rsp+1B8h+Reply], ebx
0x180089a36  jz      short loc_180089A3F
0x180089a38  mov     edi, 0C0000001h
0x180089a3d  jmp     short loc_180089A79
0x180089a3f  mov     edx, ebx
0x180089a41  cmp     edx, [rsp+1B8h+var_178]
0x180089a45  jnb     short loc_180089A63
0x180089a47  mov     ecx, edx
0x180089a49  add     rcx, rcx
0x180089a4c  mov     rax, [rsp+1B8h+P]
0x180089a51  cmp     [rax+rcx*8+8], rbx
0x180089a56  jz      short loc_180089A5C
0x180089a58  inc     edx
0x180089a5a  jmp     short loc_180089A41
0x180089a5c  mov     edi, 0C000000Dh
0x180089a61  jmp     short loc_180089A79
0x180089a63  mov     eax, [rsp+1B8h+var_178]
0x180089a67  mov     [r12], eax
0x180089a6b  mov     rax, [rsp+1B8h+P]
0x180089a70  mov     [r13+0], rax
0x180089a74  mov     [rsp+1B8h+P], rbx
0x180089a79  cmp     [rsp+1B8h+P], rbx
0x180089a7e  jz      short loc_180089ACB
0x180089a80  mov     esi, ebx
0x180089a82  cmp     [rsp+1B8h+var_178], ebx
0x180089a86  jbe     short loc_180089AB5
0x180089a88  mov     ecx, esi
0x180089a8a  add     rcx, rcx
0x180089a8d  mov     rax, [rsp+1B8h+P]
0x180089a92  mov     rcx, [rax+rcx*8+8]; P
0x180089a97  test    rcx, rcx
0x180089a9a  jz      short loc_180089AAD
0x180089a9c  mov     edx, 63734943h; Tag
0x180089aa1  call    cs:__imp_ExFreePoolWithTag
0x180089aa8  nop     dword ptr [rax+rax+00h]
0x180089aad  inc     esi
0x180089aaf  cmp     esi, [rsp+1B8h+var_178]
0x180089ab3  jb      short loc_180089A88
0x180089ab5  mov     edx, 63734943h; Tag
0x180089aba  mov     rcx, [rsp+1B8h+P]; P
0x180089abf  call    cs:__imp_ExFreePoolWithTag
0x180089ac6  nop     dword ptr [rax+rax+00h]
0x180089acb  cmp     [rsp+1B8h+Binding], rbx
0x180089ad0  jz      short loc_180089ADC
0x180089ad2  lea     rcx, [rsp+1B8h+Binding]; Binding
0x180089ad7  call    CipCatDbRpcDisconnect
0x180089adc  lea     rcx, [rsp+1B8h+ApcState]; ApcState
0x180089ae4  call    cs:__imp_KeUnstackDetachProcess
0x180089aeb  nop     dword ptr [rax+rax+00h]
0x180089af0  mov     rcx, r15
0x180089af3  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180089afa  nop     dword ptr [rax+rax+00h]
0x180089aff  mov     eax, edi
0x180089b01  mov     rcx, [rsp+1B8h+var_48]
0x180089b09  xor     rcx, rsp; StackCookie
0x180089b0c  call    __security_check_cookie
0x180089b11  add     rsp, 180h
0x180089b18  pop     r15
0x180089b1a  pop     r14
0x180089b1c  pop     r13
0x180089b1e  pop     r12
0x180089b20  pop     rdi
0x180089b21  pop     rsi
0x180089b22  pop     rbx
0x180089b23  retn
0x1800e7f30  push    rbp
0x1800e7f32  sub     rsp, 40h
0x1800e7f36  mov     rbp, rdx
0x1800e7f39  mov     rcx, [rcx]
0x1800e7f3c  mov     ecx, [rcx]; ExceptionCode
0x1800e7f3e  call    cs:__imp_I_RpcExceptionFilter
0x1800e7f45  nop     dword ptr [rax+rax+00h]
0x1800e7f4a  nop
0x1800e7f4b  add     rsp, 40h
0x1800e7f4f  pop     rbp
0x1800e7f50  retn
```
