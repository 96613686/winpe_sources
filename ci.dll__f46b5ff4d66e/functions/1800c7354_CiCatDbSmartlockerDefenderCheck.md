# CiCatDbSmartlockerDefenderCheck

- ea: `0x1800c7354`
- end: `0x1800c7946`
- name: `CiCatDbSmartlockerDefenderCheck`
- size: `1522`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING StringIn@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c6340`
- `0x1800c6c7c`

## callees

- `0x18000f6bc`
- `0x18002bef0`
- `0x18002c340`
- `0x180089b2c`
- `0x1800ba724`
- `0x1800c6c08`
- `0x1800c7354`
- `0x1800e18f8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800c7916`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800c7916`
- `ntoskrnl!KeStackAttachProcess` at `0x1800c753a`
- `ntoskrnl!KeStackAttachProcess` at `0x1800c753a`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800c747b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800c747b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c7509`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c78ee`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c7509`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c78ee`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800c74ca`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800c74ca`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c7518`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c7902`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c7518`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c7902`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800c74bb`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800c74bb`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800c77ae`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800c77ae`
- `ntoskrnl!KeInitializeEvent` at `0x1800c75c4`
- `ntoskrnl!KeInitializeEvent` at `0x1800c75c4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c76e0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c772d`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c76e0`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c772d`
- `msrpc!RpcAsyncCancelCall` at `0x1800c770a`
- `msrpc!RpcAsyncCancelCall` at `0x1800c770a`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c7755`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c7770`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c7755`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c7770`
- `msrpc!I_RpcExceptionFilter` at `0x1800e8356`
- `msrpc!I_RpcExceptionFilter` at `0x1800e8356`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800c756a`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800c756a`

## pseudocode

```c
NTSTATUS __fastcall CiCatDbSmartlockerDefenderCheck(
        PCUNICODE_STRING StringIn,
        struct _KPROCESS *a2,
        int a3,
        __int64 a4,
        unsigned int *a5,
        PVOID *a6,
        _QWORD *a7,
        _DWORD *a8)
{
  NTSTATUS result; // eax
  int v10; // edi
  __int64 v11; // r12
  int v12; // eax
  PRKPROCESS v13; // rsi
  __int64 CurrentServerSilo; // rax
  struct _KPROCESS *v15; // rcx
  RPC_STATUS v16; // eax
  RPC_STATUS v17; // esi
  __int64 v18; // rdx
  bool v19; // zf
  union _LARGE_INTEGER v20; // rax
  NTSTATUS v21; // eax
  RPC_STATUS v22; // edi
  int v23; // eax
  _DWORD *v24; // rcx
  _QWORD *v25; // rcx
  unsigned int i; // ecx
  __int64 v27; // rcx
  unsigned int v28; // [rsp+50h] [rbp-1A8h] BYREF
  int Reply; // [rsp+54h] [rbp-1A4h] BYREF
  int v30; // [rsp+58h] [rbp-1A0h]
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp-198h] BYREF
  unsigned int v32; // [rsp+68h] [rbp-190h]
  PVOID P; // [rsp+70h] [rbp-188h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+78h] [rbp-180h] BYREF
  PRKPROCESS PROCESS; // [rsp+80h] [rbp-178h]
  _QWORD *v36; // [rsp+88h] [rbp-170h]
  __int64 v37; // [rsp+90h] [rbp-168h]
  __int64 v38; // [rsp+98h] [rbp-160h]
  _DWORD *v39; // [rsp+A0h] [rbp-158h]
  unsigned int *v40; // [rsp+A8h] [rbp-150h]
  PVOID *v41; // [rsp+B0h] [rbp-148h]
  __int64 v42; // [rsp+B8h] [rbp-140h]
  _DWORD *v43; // [rsp+C0h] [rbp-138h]
  struct _KPROCESS *v44; // [rsp+C8h] [rbp-130h]
  __int64 v45; // [rsp+D0h] [rbp-128h]
  struct _UNICODE_STRING StringOut; // [rsp+E0h] [rbp-118h] BYREF
  struct _KEVENT Event; // [rsp+F0h] [rbp-108h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+110h] [rbp-E8h] BYREF
  __int128 v49; // [rsp+170h] [rbp-88h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+180h] [rbp-78h] BYREF

  v38 = a4;
  PROCESS = a2;
  v36 = a7;
  v43 = a8;
  v44 = a2;
  v45 = a4;
  v40 = a5;
  v41 = a6;
  v42 = (__int64)a7;
  memset(&ApcState, 0, sizeof(ApcState));
  memset(&pAsync, 0, sizeof(pAsync));
  Binding = 0;
  StringOut = 0;
  memset(&Event, 0, sizeof(Event));
  Interval.QuadPart = 0;
  v49 = 0;
  Reply = 0;
  v28 = 0;
  P = 0;
  DWORD1(v49) = -1;
  if ( !StringIn->Buffer )
    return -1073741811;
  result = RtlDuplicateUnicodeString(1u, StringIn, &StringOut);
  v10 = result;
  if ( result >= 0 )
  {
    v39 = a8;
    v11 = 0;
    v32 = 0;
    v12 = 0;
    v30 = 0;
    v13 = PROCESS;
    while ( 1 )
    {
      if ( v12 >= 2 )
      {
LABEL_33:
        if ( v10 >= 0 )
        {
          for ( i = 0; i < v28; ++i )
          {
            if ( !*((_QWORD *)P + 3 * i + 2) || *((_DWORD *)P + 6 * i + 1) == 1 && *((_DWORD *)P + 6 * i + 2) != 28 )
            {
              v10 = -1073741811;
              goto LABEL_44;
            }
          }
          *v40 = v28;
          *v41 = P;
          P = 0;
          *(_DWORD *)(v42 + 8) = DWORD1(v49);
          v27 = 7200;
          if ( *((_QWORD *)&v49 + 1) > 0x1C20u )
            v27 = *((_QWORD *)&v49 + 1);
          *v36 = MEMORY[0xFFFFF78000000014] + 10000000 * v27;
        }
LABEL_44:
        if ( Binding )
          CipCatDbRpcDisconnect(&Binding);
        CiCatDbFreeExtraInfoFromDefender(P);
        KeUnstackDetachProcess(&ApcState);
        if ( v11 )
          PsDetachSiloFromCurrentThread(v11);
        RtlFreeUnicodeString(&StringOut);
        return v10;
      }
      if ( v12 )
      {
        if ( !v13 )
          goto LABEL_32;
        if ( Binding )
        {
          CipCatDbRpcDisconnect(&Binding);
          Binding = 0;
        }
        KeUnstackDetachProcess(&ApcState);
        PsDetachSiloFromCurrentThread(v11);
        v11 = 0;
        v15 = v13;
      }
      else
      {
        CurrentServerSilo = PsGetCurrentServerSilo();
        v11 = PsAttachSiloToCurrentThread(CurrentServerSilo);
        v15 = g_CiSystemProcess;
      }
      v37 = v11;
      KeStackAttachProcess(v15, &ApcState);
      v10 = CipCatDbRpcConnect(&Binding, a8);
      if ( v10 < 0 )
        goto LABEL_33;
      while ( 1 )
      {
        v16 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
        v17 = v16;
        if ( v16 )
          break;
        pAsync.UserInfo = 0;
        pAsync.NotificationType = RpcNotificationTypeEvent;
        KeInitializeEvent(&Event, NotificationEvent, 0);
        pAsync.u.Event = &Event;
        LODWORD(v49) = 16;
        SSCatDBSmartlockerDefenderCheck2(
          (unsigned int)&pAsync,
          (_DWORD)Binding,
          StringOut.Buffer,
          16,
          a3,
          v38,
          (__int64)&v28,
          (__int64)&P,
          (__int64)&v49);
        if ( (unsigned __int8)SIPolicyIsPolicyActive(&SiPolicyIDNightsWatchDesktop, 0)
          || (v19 = (unsigned __int8)SIPolicyIsPolicyActive(&SiPolicyIDNightsWatchDesktopEval, v18) == 0,
              v20.QuadPart = -80000000,
              !v19) )
        {
          v20.QuadPart = -600000000;
        }
        Interval = v20;
        v21 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Interval);
        v10 = v21;
        if ( v21 )
        {
          *a8 = 7;
          a8[1] = v21;
          v22 = RpcAsyncCancelCall(&pAsync, 1);
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          if ( v22 )
          {
            *a8 = 16;
            a8[1] = v22;
          }
          RpcAsyncCompleteCall(&pAsync, &Reply);
          v10 = -1073741823;
          goto LABEL_44;
        }
        v17 = RpcAsyncCompleteCall(&pAsync, &Reply);
        if ( v17 != -1073610728 || v32 >= 0x14 )
          goto LABEL_15;
        ++v32;
        Interval.QuadPart = -1000000;
        KeDelayExecutionThread(0, 0, &Interval);
      }
      *a8 = 5;
      a8[1] = v16;
      v10 = -1073741823;
LABEL_15:
      if ( v17 )
      {
        *a8 = 8;
        a8[1] = v17;
      }
      else
      {
        v23 = Reply;
        if ( !Reply )
          goto LABEL_33;
        v24 = v39;
        if ( Reply == 1058 )
        {
          *a8 = 17;
          v24[1] = 1058;
          v25 = (_QWORD *)v42;
          *(_DWORD *)(v42 + 8) = -1;
          *v25 = 0;
          v10 = 0;
          goto LABEL_44;
        }
        *a8 = 10;
        v24[1] = v23;
      }
      v13 = PROCESS;
      v12 = v30;
      v10 = -1073741823;
LABEL_32:
      v30 = ++v12;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800c7354  mov     r11, rsp
0x1800c7357  mov     [r11+18h], r8d
0x1800c735b  push    rbx
0x1800c735c  push    rsi
0x1800c735d  push    rdi
0x1800c735e  push    r12
0x1800c7360  push    r13
0x1800c7362  push    r14
0x1800c7364  sub     rsp, 1C8h
0x1800c736b  mov     rax, cs:__security_cookie
0x1800c7372  xor     rax, rsp
0x1800c7375  mov     [rsp+1F8h+var_48], rax
0x1800c737d  mov     [rsp+1F8h+var_160], r9
0x1800c7385  mov     [rsp+1F8h+PROCESS], rdx
0x1800c738d  mov     rdi, rcx
0x1800c7390  mov     rsi, [rsp+1F8h+arg_30]
0x1800c7398  mov     [rsp+1F8h+var_170], rsi
0x1800c73a0  mov     r14, [rsp+1F8h+arg_38]
0x1800c73a8  mov     [rsp+1F8h+var_138], r14
0x1800c73b0  mov     [rsp+1F8h+var_130], rdx
0x1800c73b8  mov     [rsp+1F8h+var_128], r9
0x1800c73c0  mov     rax, [rsp+1F8h+arg_20]
0x1800c73c8  mov     [rsp+1F8h+var_150], rax
0x1800c73d0  mov     rax, [rsp+1F8h+arg_28]
0x1800c73d8  mov     [rsp+1F8h+var_148], rax
0x1800c73e0  mov     [rsp+1F8h+var_140], rsi
0x1800c73e8  mov     r13, r14
0x1800c73eb  xorps   xmm0, xmm0
0x1800c73ee  movups  xmmword ptr [r11-78h], xmm0
0x1800c73f3  movups  xmmword ptr [r11-68h], xmm0
0x1800c73f8  movups  xmmword ptr [r11-58h], xmm0
0x1800c73fd  xor     edx, edx; Val
0x1800c73ff  lea     r8d, [rdx+58h]; Size
0x1800c7403  lea     rcx, [r11-0E8h]; void *
0x1800c740a  call    memset
0x1800c740f  xor     ebx, ebx
0x1800c7411  mov     [rsp+1F8h+Binding], rbx
0x1800c7416  xorps   xmm0, xmm0
0x1800c7419  movups  xmmword ptr [rsp+1F8h+StringOut.Length], xmm0
0x1800c7421  xorps   xmm1, xmm1
0x1800c7424  xor     eax, eax
0x1800c7426  movups  xmmword ptr [rsp+1F8h+Event.Header], xmm1
0x1800c742e  mov     [rsp+1F8h+Event.Header.WaitListHead.Blink], rax
0x1800c7436  mov     qword ptr [rsp+1F8h+Interval], rbx
0x1800c743b  movups  [rsp+1F8h+var_88], xmm0
0x1800c7443  mov     [rsp+1F8h+Reply], ebx
0x1800c7447  mov     [rsp+1F8h+var_1A8], ebx
0x1800c744b  mov     [rsp+1F8h+P], rbx
0x1800c7450  mov     dword ptr [rsp+1F8h+var_88+4], 0FFFFFFFFh
0x1800c745b  cmp     [rdi+8], rbx
0x1800c745f  jnz     short loc_1800C746B
0x1800c7461  mov     eax, 0C000000Dh
0x1800c7466  jmp     loc_1800C7924
0x1800c746b  lea     r8, [rsp+1F8h+StringOut]; StringOut
0x1800c7473  mov     rdx, rdi; StringIn
0x1800c7476  mov     ecx, 1; Flags
0x1800c747b  call    cs:__imp_RtlDuplicateUnicodeString
0x1800c7482  nop     dword ptr [rax+rax+00h]
0x1800c7487  mov     edi, eax
0x1800c7489  test    eax, eax
0x1800c748b  js      loc_1800C7924
0x1800c7491  mov     [rsp+1F8h+var_158], r14
0x1800c7499  mov     r12, rbx
0x1800c749c  mov     [rsp+1F8h+var_190], ebx
0x1800c74a0  mov     eax, ebx
0x1800c74a2  mov     [rsp+1F8h+var_1A0], ebx
0x1800c74a6  mov     rsi, [rsp+1F8h+PROCESS]
0x1800c74ae  cmp     eax, 2
0x1800c74b1  jge     loc_1800C781F
0x1800c74b7  test    eax, eax
0x1800c74b9  jnz     short loc_1800C74E2
0x1800c74bb  call    cs:__imp_PsGetCurrentServerSilo
0x1800c74c2  nop     dword ptr [rax+rax+00h]
0x1800c74c7  mov     rcx, rax
0x1800c74ca  call    cs:__imp_PsAttachSiloToCurrentThread
0x1800c74d1  nop     dword ptr [rax+rax+00h]
0x1800c74d6  mov     r12, rax
0x1800c74d9  mov     rcx, cs:g_CiSystemProcess
0x1800c74e0  jmp     short loc_1800C752A
0x1800c74e2  test    rsi, rsi
0x1800c74e5  jz      loc_1800C7814
0x1800c74eb  cmp     [rsp+1F8h+Binding], rbx
0x1800c74f0  jz      short loc_1800C7501
0x1800c74f2  lea     rcx, [rsp+1F8h+Binding]; Binding
0x1800c74f7  call    CipCatDbRpcDisconnect
0x1800c74fc  mov     [rsp+1F8h+Binding], rbx
0x1800c7501  lea     rcx, [rsp+1F8h+ApcState]; ApcState
0x1800c7509  call    cs:__imp_KeUnstackDetachProcess
0x1800c7510  nop     dword ptr [rax+rax+00h]
0x1800c7515  mov     rcx, r12
0x1800c7518  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1800c751f  nop     dword ptr [rax+rax+00h]
0x1800c7524  mov     r12, rbx
0x1800c7527  mov     rcx, rsi; PROCESS
0x1800c752a  mov     [rsp+1F8h+var_168], r12
0x1800c7532  lea     rdx, [rsp+1F8h+ApcState]; ApcState
0x1800c753a  call    cs:__imp_KeStackAttachProcess
0x1800c7541  nop     dword ptr [rax+rax+00h]
0x1800c7546  mov     rdx, r13
0x1800c7549  lea     rcx, [rsp+1F8h+Binding]
0x1800c754e  call    CipCatDbRpcConnect
0x1800c7553  mov     edi, eax
0x1800c7555  test    eax, eax
0x1800c7557  js      loc_1800C781F
0x1800c755d  mov     edx, 58h ; 'X'; Size
0x1800c7562  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c756a  call    cs:__imp_RpcAsyncInitializeHandle
0x1800c7571  nop     dword ptr [rax+rax+00h]
0x1800c7576  mov     esi, eax
0x1800c7578  test    eax, eax
0x1800c757a  jz      short loc_1800C75A4
0x1800c757c  mov     dword ptr [r14], 5
0x1800c7583  mov     [r13+4], eax
0x1800c7587  mov     edi, 0C0000001h
0x1800c758c  test    esi, esi
0x1800c758e  jz      loc_1800C77BF
0x1800c7594  mov     dword ptr [r14], 8
0x1800c759b  mov     [r13+4], esi
0x1800c759f  jmp     loc_1800C7803
0x1800c75a4  mov     [rsp+1F8h+pAsync.UserInfo], rbx
0x1800c75ac  mov     [rsp+1F8h+pAsync.NotificationType], 1
0x1800c75b7  xor     r8d, r8d; State
0x1800c75ba  xor     edx, edx; Type
0x1800c75bc  lea     rcx, [rsp+1F8h+Event]; Event
0x1800c75c4  call    cs:__imp_KeInitializeEvent
0x1800c75cb  nop     dword ptr [rax+rax+00h]
0x1800c75d0  lea     rax, [rsp+1F8h+Event]
0x1800c75d8  mov     qword ptr [rsp+1F8h+pAsync.u], rax
0x1800c75e0  mov     dword ptr [rsp+1F8h+var_88], 10h
0x1800c75eb  lea     rax, [rsp+1F8h+var_88]
0x1800c75f3  mov     [rsp+1F8h+var_1B8], rax
0x1800c75f8  lea     rax, [rsp+1F8h+P]
0x1800c75fd  mov     [rsp+1F8h+var_1C0], rax
0x1800c7602  lea     rax, [rsp+1F8h+var_1A8]
0x1800c7607  mov     [rsp+1F8h+var_1C8], rax
0x1800c760c  mov     rax, [rsp+1F8h+var_160]
0x1800c7614  mov     [rsp+1F8h+var_1D0], rax
0x1800c7619  mov     eax, [rsp+1F8h+arg_10]
0x1800c7620  mov     dword ptr [rsp+1F8h+Timeout], eax
0x1800c7624  mov     r9d, 10h
0x1800c762a  mov     r8, [rsp+1F8h+StringOut.Buffer]
0x1800c7632  mov     rdx, [rsp+1F8h+Binding]
0x1800c7637  lea     rcx, [rsp+1F8h+pAsync]
0x1800c763f  call    SSCatDBSmartlockerDefenderCheck2
0x1800c7644  jmp     short loc_1800C767D
0x1800c7646  mov     esi, eax
0x1800c7648  xor     ebx, ebx
0x1800c764a  mov     r12, [rsp+1F8h+var_168]
0x1800c7652  mov     r14, [rsp+1F8h+var_138]
0x1800c765a  mov     rax, [rsp+1F8h+var_130]
0x1800c7662  mov     [rsp+1F8h+PROCESS], rax
0x1800c766a  mov     rax, [rsp+1F8h+var_128]
0x1800c7672  mov     [rsp+1F8h+var_160], rax
0x1800c767a  mov     r13, r14
0x1800c767d  test    esi, esi
0x1800c767f  jz      short loc_1800C7691
0x1800c7681  mov     dword ptr [r14], 6
0x1800c7688  mov     [r13+4], esi
0x1800c768c  jmp     loc_1800C7587
0x1800c7691  xor     edx, edx
0x1800c7693  lea     rcx, SiPolicyIDNightsWatchDesktop
0x1800c769a  call    SIPolicyIsPolicyActive
0x1800c769f  test    al, al
0x1800c76a1  jnz     short loc_1800C76BA
0x1800c76a3  lea     rcx, SiPolicyIDNightsWatchDesktopEval
0x1800c76aa  call    SIPolicyIsPolicyActive
0x1800c76af  test    al, al
0x1800c76b1  mov     rax, 0FFFFFFFFFB3B4C00h
0x1800c76b8  jz      short loc_1800C76C1
0x1800c76ba  mov     rax, 0FFFFFFFFDC3CBA00h
0x1800c76c1  mov     qword ptr [rsp+1F8h+Interval], rax
0x1800c76c6  lea     rax, [rsp+1F8h+Interval]
0x1800c76cb  mov     [rsp+1F8h+Timeout], rax; Timeout
0x1800c76d0  xor     r9d, r9d; Alertable
0x1800c76d3  xor     r8d, r8d; WaitMode
0x1800c76d6  xor     edx, edx; WaitReason
0x1800c76d8  lea     rcx, [rsp+1F8h+Event]; Object
0x1800c76e0  call    cs:__imp_KeWaitForSingleObject
0x1800c76e7  nop     dword ptr [rax+rax+00h]
0x1800c76ec  mov     edi, eax
0x1800c76ee  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c76f6  test    eax, eax
0x1800c76f8  jz      short loc_1800C776B
0x1800c76fa  mov     dword ptr [r14], 7
0x1800c7701  mov     [r13+4], eax
0x1800c7705  mov     edx, 1; fAbort
0x1800c770a  call    cs:__imp_RpcAsyncCancelCall
0x1800c7711  nop     dword ptr [rax+rax+00h]
0x1800c7716  mov     edi, eax
0x1800c7718  mov     [rsp+1F8h+Timeout], rbx; Timeout
0x1800c771d  xor     r9d, r9d; Alertable
0x1800c7720  xor     r8d, r8d; WaitMode
0x1800c7723  xor     edx, edx; WaitReason
0x1800c7725  lea     rcx, [rsp+1F8h+Event]; Object
0x1800c772d  call    cs:__imp_KeWaitForSingleObject
0x1800c7734  nop     dword ptr [rax+rax+00h]
0x1800c7739  test    edi, edi
0x1800c773b  jz      short loc_1800C7748
0x1800c773d  mov     dword ptr [r14], 10h
0x1800c7744  mov     [r13+4], edi
0x1800c7748  lea     rdx, [rsp+1F8h+Reply]; Reply
0x1800c774d  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c7755  call    cs:__imp_RpcAsyncCompleteCall
0x1800c775c  nop     dword ptr [rax+rax+00h]
0x1800c7761  mov     edi, 0C0000001h
0x1800c7766  jmp     loc_1800C78C7
0x1800c776b  lea     rdx, [rsp+1F8h+Reply]; Reply
0x1800c7770  call    cs:__imp_RpcAsyncCompleteCall
0x1800c7777  nop     dword ptr [rax+rax+00h]
0x1800c777c  mov     esi, eax
0x1800c777e  cmp     eax, 0C0020018h
0x1800c7783  jnz     loc_1800C758C
0x1800c7789  mov     ecx, [rsp+1F8h+var_190]
0x1800c778d  cmp     ecx, 14h
0x1800c7790  jnb     loc_1800C758C
0x1800c7796  inc     ecx
0x1800c7798  mov     [rsp+1F8h+var_190], ecx
0x1800c779c  mov     qword ptr [rsp+1F8h+Interval], 0FFFFFFFFFFF0BDC0h
0x1800c77a5  lea     r8, [rsp+1F8h+Interval]; Interval
0x1800c77aa  xor     edx, edx; Alertable
0x1800c77ac  xor     ecx, ecx; WaitMode
0x1800c77ae  call    cs:__imp_KeDelayExecutionThread
0x1800c77b5  nop     dword ptr [rax+rax+00h]
0x1800c77ba  jmp     loc_1800C755D
0x1800c77bf  mov     eax, [rsp+1F8h+Reply]
0x1800c77c3  test    eax, eax
0x1800c77c5  jz      short loc_1800C781F
0x1800c77c7  mov     rcx, [rsp+1F8h+var_158]
0x1800c77cf  cmp     eax, 422h
0x1800c77d4  jnz     short loc_1800C77F9
0x1800c77d6  mov     dword ptr [r14], 11h
0x1800c77dd  mov     [rcx+4], eax
0x1800c77e0  mov     rcx, [rsp+1F8h+var_140]
0x1800c77e8  mov     dword ptr [rcx+8], 0FFFFFFFFh
0x1800c77ef  mov     [rcx], rbx
0x1800c77f2  mov     edi, ebx
0x1800c77f4  jmp     loc_1800C78C7
0x1800c77f9  mov     dword ptr [r14], 0Ah
0x1800c7800  mov     [rcx+4], eax
0x1800c7803  mov     rsi, [rsp+1F8h+PROCESS]
0x1800c780b  mov     eax, [rsp+1F8h+var_1A0]
0x1800c780f  mov     edi, 0C0000001h
0x1800c7814  inc     eax
0x1800c7816  mov     [rsp+1F8h+var_1A0], eax
0x1800c781a  jmp     loc_1800C74AE
0x1800c781f  test    edi, edi
0x1800c7821  js      loc_1800C78C7
0x1800c7827  mov     ecx, ebx
0x1800c7829  cmp     ecx, [rsp+1F8h+var_1A8]
0x1800c782d  jnb     short loc_1800C785A
0x1800c782f  mov     eax, ecx
0x1800c7831  lea     rdx, [rax+rax*2]
0x1800c7835  mov     rax, [rsp+1F8h+P]
0x1800c783a  cmp     [rax+rdx*8+10h], rbx
0x1800c783f  jz      short loc_1800C7853
0x1800c7841  cmp     dword ptr [rax+rdx*8+4], 1
0x1800c7846  jnz     short loc_1800C784F
0x1800c7848  cmp     dword ptr [rax+rdx*8+8], 1Ch
0x1800c784d  jnz     short loc_1800C7853
0x1800c784f  inc     ecx
0x1800c7851  jmp     short loc_1800C7829
0x1800c7853  mov     edi, 0C000000Dh
0x1800c7858  jmp     short loc_1800C78C7
0x1800c785a  mov     eax, [rsp+1F8h+var_1A8]
0x1800c785e  mov     rcx, [rsp+1F8h+var_150]
0x1800c7866  mov     [rcx], eax
0x1800c7868  mov     rax, [rsp+1F8h+P]
0x1800c786d  mov     rcx, [rsp+1F8h+var_148]
0x1800c7875  mov     [rcx], rax
0x1800c7878  mov     [rsp+1F8h+P], rbx
0x1800c787d  mov     eax, dword ptr [rsp+1F8h+var_88+4]
0x1800c7884  mov     rcx, [rsp+1F8h+var_140]
0x1800c788c  mov     [rcx+8], eax
0x1800c788f  mov     rax, 0FFFFF78000000014h
0x1800c7899  mov     rax, [rax]
0x1800c789c  mov     ecx, 1C20h
0x1800c78a1  cmp     qword ptr [rsp+1F8h+var_88+8], rcx
0x1800c78a9  cmova   rcx, qword ptr [rsp+1F8h+var_88+8]
0x1800c78b2  imul    rcx, 989680h
0x1800c78b9  add     rcx, rax
0x1800c78bc  mov     rax, [rsp+1F8h+var_170]
0x1800c78c4  mov     [rax], rcx
0x1800c78c7  cmp     [rsp+1F8h+Binding], rbx
0x1800c78cc  jz      short loc_1800C78D8
0x1800c78ce  lea     rcx, [rsp+1F8h+Binding]; Binding
0x1800c78d3  call    CipCatDbRpcDisconnect
0x1800c78d8  mov     edx, [rsp+1F8h+var_1A8]
0x1800c78dc  mov     rcx, [rsp+1F8h+P]; P
0x1800c78e1  call    CiCatDbFreeExtraInfoFromDefender
0x1800c78e6  lea     rcx, [rsp+1F8h+ApcState]; ApcState
0x1800c78ee  call    cs:__imp_KeUnstackDetachProcess
0x1800c78f5  nop     dword ptr [rax+rax+00h]
0x1800c78fa  test    r12, r12
0x1800c78fd  jz      short loc_1800C790E
0x1800c78ff  mov     rcx, r12
0x1800c7902  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1800c7909  nop     dword ptr [rax+rax+00h]
0x1800c790e  lea     rcx, [rsp+1F8h+StringOut]; UnicodeString
0x1800c7916  call    cs:__imp_RtlFreeUnicodeString
0x1800c791d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
