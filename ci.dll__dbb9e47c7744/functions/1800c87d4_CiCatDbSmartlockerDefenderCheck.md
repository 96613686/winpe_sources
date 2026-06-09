# CiCatDbSmartlockerDefenderCheck

- ea: `0x1800c87d4`
- end: `0x1800c8dc6`
- name: `CiCatDbSmartlockerDefenderCheck`
- size: `1522`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING StringIn@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c77c0`
- `0x1800c80fc`

## callees

- `0x18000f6bc`
- `0x18002bf20`
- `0x18002c380`
- `0x18008b15c`
- `0x1800bbba4`
- `0x1800c8088`
- `0x1800c87d4`
- `0x1800e28e8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800c8d96`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800c8d96`
- `ntoskrnl!KeStackAttachProcess` at `0x1800c89ba`
- `ntoskrnl!KeStackAttachProcess` at `0x1800c89ba`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800c88fb`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800c88fb`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c8989`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c8d6e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c8989`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c8d6e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800c894a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800c894a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c8998`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c8d82`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c8998`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c8d82`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800c893b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800c893b`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800c8c2e`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800c8c2e`
- `ntoskrnl!KeInitializeEvent` at `0x1800c8a44`
- `ntoskrnl!KeInitializeEvent` at `0x1800c8a44`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c8b60`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c8bad`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c8b60`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c8bad`
- `msrpc!RpcAsyncCancelCall` at `0x1800c8b8a`
- `msrpc!RpcAsyncCancelCall` at `0x1800c8b8a`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c8bd5`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c8bf0`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c8bd5`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c8bf0`
- `msrpc!I_RpcExceptionFilter` at `0x1800e9ab0`
- `msrpc!I_RpcExceptionFilter` at `0x1800e9ab0`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800c89ea`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800c89ea`

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
0x1800c87d4  mov     r11, rsp
0x1800c87d7  mov     [r11+18h], r8d
0x1800c87db  push    rbx
0x1800c87dc  push    rsi
0x1800c87dd  push    rdi
0x1800c87de  push    r12
0x1800c87e0  push    r13
0x1800c87e2  push    r14
0x1800c87e4  sub     rsp, 1C8h
0x1800c87eb  mov     rax, cs:__security_cookie
0x1800c87f2  xor     rax, rsp
0x1800c87f5  mov     [rsp+1F8h+var_48], rax
0x1800c87fd  mov     [rsp+1F8h+var_160], r9
0x1800c8805  mov     [rsp+1F8h+PROCESS], rdx
0x1800c880d  mov     rdi, rcx
0x1800c8810  mov     rsi, [rsp+1F8h+arg_30]
0x1800c8818  mov     [rsp+1F8h+var_170], rsi
0x1800c8820  mov     r14, [rsp+1F8h+arg_38]
0x1800c8828  mov     [rsp+1F8h+var_138], r14
0x1800c8830  mov     [rsp+1F8h+var_130], rdx
0x1800c8838  mov     [rsp+1F8h+var_128], r9
0x1800c8840  mov     rax, [rsp+1F8h+arg_20]
0x1800c8848  mov     [rsp+1F8h+var_150], rax
0x1800c8850  mov     rax, [rsp+1F8h+arg_28]
0x1800c8858  mov     [rsp+1F8h+var_148], rax
0x1800c8860  mov     [rsp+1F8h+var_140], rsi
0x1800c8868  mov     r13, r14
0x1800c886b  xorps   xmm0, xmm0
0x1800c886e  movups  xmmword ptr [r11-78h], xmm0
0x1800c8873  movups  xmmword ptr [r11-68h], xmm0
0x1800c8878  movups  xmmword ptr [r11-58h], xmm0
0x1800c887d  xor     edx, edx; Val
0x1800c887f  lea     r8d, [rdx+58h]; Size
0x1800c8883  lea     rcx, [r11-0E8h]; void *
0x1800c888a  call    memset
0x1800c888f  xor     ebx, ebx
0x1800c8891  mov     [rsp+1F8h+Binding], rbx
0x1800c8896  xorps   xmm0, xmm0
0x1800c8899  movups  xmmword ptr [rsp+1F8h+StringOut.Length], xmm0
0x1800c88a1  xorps   xmm1, xmm1
0x1800c88a4  xor     eax, eax
0x1800c88a6  movups  xmmword ptr [rsp+1F8h+Event.Header], xmm1
0x1800c88ae  mov     [rsp+1F8h+Event.Header.WaitListHead.Blink], rax
0x1800c88b6  mov     qword ptr [rsp+1F8h+Interval], rbx
0x1800c88bb  movups  [rsp+1F8h+var_88], xmm0
0x1800c88c3  mov     [rsp+1F8h+Reply], ebx
0x1800c88c7  mov     [rsp+1F8h+var_1A8], ebx
0x1800c88cb  mov     [rsp+1F8h+P], rbx
0x1800c88d0  mov     dword ptr [rsp+1F8h+var_88+4], 0FFFFFFFFh
0x1800c88db  cmp     [rdi+8], rbx
0x1800c88df  jnz     short loc_1800C88EB
0x1800c88e1  mov     eax, 0C000000Dh
0x1800c88e6  jmp     loc_1800C8DA4
0x1800c88eb  lea     r8, [rsp+1F8h+StringOut]; StringOut
0x1800c88f3  mov     rdx, rdi; StringIn
0x1800c88f6  mov     ecx, 1; Flags
0x1800c88fb  call    cs:__imp_RtlDuplicateUnicodeString
0x1800c8902  nop     dword ptr [rax+rax+00h]
0x1800c8907  mov     edi, eax
0x1800c8909  test    eax, eax
0x1800c890b  js      loc_1800C8DA4
0x1800c8911  mov     [rsp+1F8h+var_158], r14
0x1800c8919  mov     r12, rbx
0x1800c891c  mov     [rsp+1F8h+var_190], ebx
0x1800c8920  mov     eax, ebx
0x1800c8922  mov     [rsp+1F8h+var_1A0], ebx
0x1800c8926  mov     rsi, [rsp+1F8h+PROCESS]
0x1800c892e  cmp     eax, 2
0x1800c8931  jge     loc_1800C8C9F
0x1800c8937  test    eax, eax
0x1800c8939  jnz     short loc_1800C8962
0x1800c893b  call    cs:__imp_PsGetCurrentServerSilo
0x1800c8942  nop     dword ptr [rax+rax+00h]
0x1800c8947  mov     rcx, rax
0x1800c894a  call    cs:__imp_PsAttachSiloToCurrentThread
0x1800c8951  nop     dword ptr [rax+rax+00h]
0x1800c8956  mov     r12, rax
0x1800c8959  mov     rcx, cs:g_CiSystemProcess
0x1800c8960  jmp     short loc_1800C89AA
0x1800c8962  test    rsi, rsi
0x1800c8965  jz      loc_1800C8C94
0x1800c896b  cmp     [rsp+1F8h+Binding], rbx
0x1800c8970  jz      short loc_1800C8981
0x1800c8972  lea     rcx, [rsp+1F8h+Binding]; Binding
0x1800c8977  call    CipCatDbRpcDisconnect
0x1800c897c  mov     [rsp+1F8h+Binding], rbx
0x1800c8981  lea     rcx, [rsp+1F8h+ApcState]; ApcState
0x1800c8989  call    cs:__imp_KeUnstackDetachProcess
0x1800c8990  nop     dword ptr [rax+rax+00h]
0x1800c8995  mov     rcx, r12
0x1800c8998  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1800c899f  nop     dword ptr [rax+rax+00h]
0x1800c89a4  mov     r12, rbx
0x1800c89a7  mov     rcx, rsi; PROCESS
0x1800c89aa  mov     [rsp+1F8h+var_168], r12
0x1800c89b2  lea     rdx, [rsp+1F8h+ApcState]; ApcState
0x1800c89ba  call    cs:__imp_KeStackAttachProcess
0x1800c89c1  nop     dword ptr [rax+rax+00h]
0x1800c89c6  mov     rdx, r13
0x1800c89c9  lea     rcx, [rsp+1F8h+Binding]
0x1800c89ce  call    CipCatDbRpcConnect
0x1800c89d3  mov     edi, eax
0x1800c89d5  test    eax, eax
0x1800c89d7  js      loc_1800C8C9F
0x1800c89dd  mov     edx, 58h ; 'X'; Size
0x1800c89e2  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c89ea  call    cs:__imp_RpcAsyncInitializeHandle
0x1800c89f1  nop     dword ptr [rax+rax+00h]
0x1800c89f6  mov     esi, eax
0x1800c89f8  test    eax, eax
0x1800c89fa  jz      short loc_1800C8A24
0x1800c89fc  mov     dword ptr [r14], 5
0x1800c8a03  mov     [r13+4], eax
0x1800c8a07  mov     edi, 0C0000001h
0x1800c8a0c  test    esi, esi
0x1800c8a0e  jz      loc_1800C8C3F
0x1800c8a14  mov     dword ptr [r14], 8
0x1800c8a1b  mov     [r13+4], esi
0x1800c8a1f  jmp     loc_1800C8C83
0x1800c8a24  mov     [rsp+1F8h+pAsync.UserInfo], rbx
0x1800c8a2c  mov     [rsp+1F8h+pAsync.NotificationType], 1
0x1800c8a37  xor     r8d, r8d; State
0x1800c8a3a  xor     edx, edx; Type
0x1800c8a3c  lea     rcx, [rsp+1F8h+Event]; Event
0x1800c8a44  call    cs:__imp_KeInitializeEvent
0x1800c8a4b  nop     dword ptr [rax+rax+00h]
0x1800c8a50  lea     rax, [rsp+1F8h+Event]
0x1800c8a58  mov     qword ptr [rsp+1F8h+pAsync.u], rax
0x1800c8a60  mov     dword ptr [rsp+1F8h+var_88], 10h
0x1800c8a6b  lea     rax, [rsp+1F8h+var_88]
0x1800c8a73  mov     [rsp+1F8h+var_1B8], rax
0x1800c8a78  lea     rax, [rsp+1F8h+P]
0x1800c8a7d  mov     [rsp+1F8h+var_1C0], rax
0x1800c8a82  lea     rax, [rsp+1F8h+var_1A8]
0x1800c8a87  mov     [rsp+1F8h+var_1C8], rax
0x1800c8a8c  mov     rax, [rsp+1F8h+var_160]
0x1800c8a94  mov     [rsp+1F8h+var_1D0], rax
0x1800c8a99  mov     eax, [rsp+1F8h+arg_10]
0x1800c8aa0  mov     dword ptr [rsp+1F8h+Timeout], eax
0x1800c8aa4  mov     r9d, 10h
0x1800c8aaa  mov     r8, [rsp+1F8h+StringOut.Buffer]
0x1800c8ab2  mov     rdx, [rsp+1F8h+Binding]
0x1800c8ab7  lea     rcx, [rsp+1F8h+pAsync]
0x1800c8abf  call    SSCatDBSmartlockerDefenderCheck2
0x1800c8ac4  jmp     short loc_1800C8AFD
0x1800c8ac6  mov     esi, eax
0x1800c8ac8  xor     ebx, ebx
0x1800c8aca  mov     r12, [rsp+1F8h+var_168]
0x1800c8ad2  mov     r14, [rsp+1F8h+var_138]
0x1800c8ada  mov     rax, [rsp+1F8h+var_130]
0x1800c8ae2  mov     [rsp+1F8h+PROCESS], rax
0x1800c8aea  mov     rax, [rsp+1F8h+var_128]
0x1800c8af2  mov     [rsp+1F8h+var_160], rax
0x1800c8afa  mov     r13, r14
0x1800c8afd  test    esi, esi
0x1800c8aff  jz      short loc_1800C8B11
0x1800c8b01  mov     dword ptr [r14], 6
0x1800c8b08  mov     [r13+4], esi
0x1800c8b0c  jmp     loc_1800C8A07
0x1800c8b11  xor     edx, edx
0x1800c8b13  lea     rcx, SiPolicyIDNightsWatchDesktop
0x1800c8b1a  call    SIPolicyIsPolicyActive
0x1800c8b1f  test    al, al
0x1800c8b21  jnz     short loc_1800C8B3A
0x1800c8b23  lea     rcx, SiPolicyIDNightsWatchDesktopEval
0x1800c8b2a  call    SIPolicyIsPolicyActive
0x1800c8b2f  test    al, al
0x1800c8b31  mov     rax, 0FFFFFFFFFB3B4C00h
0x1800c8b38  jz      short loc_1800C8B41
0x1800c8b3a  mov     rax, 0FFFFFFFFDC3CBA00h
0x1800c8b41  mov     qword ptr [rsp+1F8h+Interval], rax
0x1800c8b46  lea     rax, [rsp+1F8h+Interval]
0x1800c8b4b  mov     [rsp+1F8h+Timeout], rax; Timeout
0x1800c8b50  xor     r9d, r9d; Alertable
0x1800c8b53  xor     r8d, r8d; WaitMode
0x1800c8b56  xor     edx, edx; WaitReason
0x1800c8b58  lea     rcx, [rsp+1F8h+Event]; Object
0x1800c8b60  call    cs:__imp_KeWaitForSingleObject
0x1800c8b67  nop     dword ptr [rax+rax+00h]
0x1800c8b6c  mov     edi, eax
0x1800c8b6e  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c8b76  test    eax, eax
0x1800c8b78  jz      short loc_1800C8BEB
0x1800c8b7a  mov     dword ptr [r14], 7
0x1800c8b81  mov     [r13+4], eax
0x1800c8b85  mov     edx, 1; fAbort
0x1800c8b8a  call    cs:__imp_RpcAsyncCancelCall
0x1800c8b91  nop     dword ptr [rax+rax+00h]
0x1800c8b96  mov     edi, eax
0x1800c8b98  mov     [rsp+1F8h+Timeout], rbx; Timeout
0x1800c8b9d  xor     r9d, r9d; Alertable
0x1800c8ba0  xor     r8d, r8d; WaitMode
0x1800c8ba3  xor     edx, edx; WaitReason
0x1800c8ba5  lea     rcx, [rsp+1F8h+Event]; Object
0x1800c8bad  call    cs:__imp_KeWaitForSingleObject
0x1800c8bb4  nop     dword ptr [rax+rax+00h]
0x1800c8bb9  test    edi, edi
0x1800c8bbb  jz      short loc_1800C8BC8
0x1800c8bbd  mov     dword ptr [r14], 10h
0x1800c8bc4  mov     [r13+4], edi
0x1800c8bc8  lea     rdx, [rsp+1F8h+Reply]; Reply
0x1800c8bcd  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c8bd5  call    cs:__imp_RpcAsyncCompleteCall
0x1800c8bdc  nop     dword ptr [rax+rax+00h]
0x1800c8be1  mov     edi, 0C0000001h
0x1800c8be6  jmp     loc_1800C8D47
0x1800c8beb  lea     rdx, [rsp+1F8h+Reply]; Reply
0x1800c8bf0  call    cs:__imp_RpcAsyncCompleteCall
0x1800c8bf7  nop     dword ptr [rax+rax+00h]
0x1800c8bfc  mov     esi, eax
0x1800c8bfe  cmp     eax, 0C0020018h
0x1800c8c03  jnz     loc_1800C8A0C
0x1800c8c09  mov     ecx, [rsp+1F8h+var_190]
0x1800c8c0d  cmp     ecx, 14h
0x1800c8c10  jnb     loc_1800C8A0C
0x1800c8c16  inc     ecx
0x1800c8c18  mov     [rsp+1F8h+var_190], ecx
0x1800c8c1c  mov     qword ptr [rsp+1F8h+Interval], 0FFFFFFFFFFF0BDC0h
0x1800c8c25  lea     r8, [rsp+1F8h+Interval]; Interval
0x1800c8c2a  xor     edx, edx; Alertable
0x1800c8c2c  xor     ecx, ecx; WaitMode
0x1800c8c2e  call    cs:__imp_KeDelayExecutionThread
0x1800c8c35  nop     dword ptr [rax+rax+00h]
0x1800c8c3a  jmp     loc_1800C89DD
0x1800c8c3f  mov     eax, [rsp+1F8h+Reply]
0x1800c8c43  test    eax, eax
0x1800c8c45  jz      short loc_1800C8C9F
0x1800c8c47  mov     rcx, [rsp+1F8h+var_158]
0x1800c8c4f  cmp     eax, 422h
0x1800c8c54  jnz     short loc_1800C8C79
0x1800c8c56  mov     dword ptr [r14], 11h
0x1800c8c5d  mov     [rcx+4], eax
0x1800c8c60  mov     rcx, [rsp+1F8h+var_140]
0x1800c8c68  mov     dword ptr [rcx+8], 0FFFFFFFFh
0x1800c8c6f  mov     [rcx], rbx
0x1800c8c72  mov     edi, ebx
0x1800c8c74  jmp     loc_1800C8D47
0x1800c8c79  mov     dword ptr [r14], 0Ah
0x1800c8c80  mov     [rcx+4], eax
0x1800c8c83  mov     rsi, [rsp+1F8h+PROCESS]
0x1800c8c8b  mov     eax, [rsp+1F8h+var_1A0]
0x1800c8c8f  mov     edi, 0C0000001h
0x1800c8c94  inc     eax
0x1800c8c96  mov     [rsp+1F8h+var_1A0], eax
0x1800c8c9a  jmp     loc_1800C892E
0x1800c8c9f  test    edi, edi
0x1800c8ca1  js      loc_1800C8D47
0x1800c8ca7  mov     ecx, ebx
0x1800c8ca9  cmp     ecx, [rsp+1F8h+var_1A8]
0x1800c8cad  jnb     short loc_1800C8CDA
0x1800c8caf  mov     eax, ecx
0x1800c8cb1  lea     rdx, [rax+rax*2]
0x1800c8cb5  mov     rax, [rsp+1F8h+P]
0x1800c8cba  cmp     [rax+rdx*8+10h], rbx
0x1800c8cbf  jz      short loc_1800C8CD3
0x1800c8cc1  cmp     dword ptr [rax+rdx*8+4], 1
0x1800c8cc6  jnz     short loc_1800C8CCF
0x1800c8cc8  cmp     dword ptr [rax+rdx*8+8], 1Ch
0x1800c8ccd  jnz     short loc_1800C8CD3
0x1800c8ccf  inc     ecx
0x1800c8cd1  jmp     short loc_1800C8CA9
0x1800c8cd3  mov     edi, 0C000000Dh
0x1800c8cd8  jmp     short loc_1800C8D47
0x1800c8cda  mov     eax, [rsp+1F8h+var_1A8]
0x1800c8cde  mov     rcx, [rsp+1F8h+var_150]
0x1800c8ce6  mov     [rcx], eax
0x1800c8ce8  mov     rax, [rsp+1F8h+P]
0x1800c8ced  mov     rcx, [rsp+1F8h+var_148]
0x1800c8cf5  mov     [rcx], rax
0x1800c8cf8  mov     [rsp+1F8h+P], rbx
0x1800c8cfd  mov     eax, dword ptr [rsp+1F8h+var_88+4]
0x1800c8d04  mov     rcx, [rsp+1F8h+var_140]
0x1800c8d0c  mov     [rcx+8], eax
0x1800c8d0f  mov     rax, 0FFFFF78000000014h
0x1800c8d19  mov     rax, [rax]
0x1800c8d1c  mov     ecx, 1C20h
0x1800c8d21  cmp     qword ptr [rsp+1F8h+var_88+8], rcx
0x1800c8d29  cmova   rcx, qword ptr [rsp+1F8h+var_88+8]
0x1800c8d32  imul    rcx, 989680h
0x1800c8d39  add     rcx, rax
0x1800c8d3c  mov     rax, [rsp+1F8h+var_170]
0x1800c8d44  mov     [rax], rcx
0x1800c8d47  cmp     [rsp+1F8h+Binding], rbx
0x1800c8d4c  jz      short loc_1800C8D58
0x1800c8d4e  lea     rcx, [rsp+1F8h+Binding]; Binding
0x1800c8d53  call    CipCatDbRpcDisconnect
0x1800c8d58  mov     edx, [rsp+1F8h+var_1A8]
0x1800c8d5c  mov     rcx, [rsp+1F8h+P]; P
0x1800c8d61  call    CiCatDbFreeExtraInfoFromDefender
0x1800c8d66  lea     rcx, [rsp+1F8h+ApcState]; ApcState
0x1800c8d6e  call    cs:__imp_KeUnstackDetachProcess
0x1800c8d75  nop     dword ptr [rax+rax+00h]
0x1800c8d7a  test    r12, r12
0x1800c8d7d  jz      short loc_1800C8D8E
0x1800c8d7f  mov     rcx, r12
0x1800c8d82  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1800c8d89  nop     dword ptr [rax+rax+00h]
0x1800c8d8e  lea     rcx, [rsp+1F8h+StringOut]; UnicodeString
0x1800c8d96  call    cs:__imp_RtlFreeUnicodeString
0x1800c8d9d  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
