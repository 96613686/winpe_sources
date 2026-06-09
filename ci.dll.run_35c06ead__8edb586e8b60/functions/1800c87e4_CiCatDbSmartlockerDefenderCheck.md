# CiCatDbSmartlockerDefenderCheck

- ea: `0x1800c87e4`
- end: `0x1800c8dd6`
- name: `CiCatDbSmartlockerDefenderCheck`
- size: `1522`
- prototype: `__int64 __usercall@<rax>(PCUNICODE_STRING StringIn@<rcx>, __int64, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800c77d0`
- `0x1800c810c`

## callees

- `0x18000f6cc`
- `0x18002c0d0`
- `0x18002c500`
- `0x18009c3a4`
- `0x1800bba44`
- `0x1800c8098`
- `0x1800c87e4`
- `0x1800e27f8`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800c8da6`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800c8da6`
- `ntoskrnl!KeStackAttachProcess` at `0x1800c89ca`
- `ntoskrnl!KeStackAttachProcess` at `0x1800c89ca`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800c890b`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800c890b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c8999`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c8d7e`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c8999`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1800c8d7e`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800c895a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x1800c895a`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c89a8`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c8d92`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c89a8`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x1800c8d92`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800c894b`
- `ntoskrnl!PsGetCurrentServerSilo` at `0x1800c894b`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800c8c3e`
- `ntoskrnl!KeDelayExecutionThread` at `0x1800c8c3e`
- `ntoskrnl!KeInitializeEvent` at `0x1800c8a54`
- `ntoskrnl!KeInitializeEvent` at `0x1800c8a54`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c8b70`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c8bbd`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c8b70`
- `ntoskrnl!KeWaitForSingleObject` at `0x1800c8bbd`
- `msrpc!RpcAsyncCancelCall` at `0x1800c8b9a`
- `msrpc!RpcAsyncCancelCall` at `0x1800c8b9a`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c8be5`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c8c00`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c8be5`
- `msrpc!RpcAsyncCompleteCall` at `0x1800c8c00`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea2f0`
- `msrpc!I_RpcExceptionFilter` at `0x1800ea2f0`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800c89fa`
- `msrpc!RpcAsyncInitializeHandle` at `0x1800c89fa`

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
0x1800c87e4  mov     r11, rsp
0x1800c87e7  mov     [r11+18h], r8d
0x1800c87eb  push    rbx
0x1800c87ec  push    rsi
0x1800c87ed  push    rdi
0x1800c87ee  push    r12
0x1800c87f0  push    r13
0x1800c87f2  push    r14
0x1800c87f4  sub     rsp, 1C8h
0x1800c87fb  mov     rax, cs:__security_cookie
0x1800c8802  xor     rax, rsp
0x1800c8805  mov     [rsp+1F8h+var_48], rax
0x1800c880d  mov     [rsp+1F8h+var_160], r9
0x1800c8815  mov     [rsp+1F8h+PROCESS], rdx
0x1800c881d  mov     rdi, rcx
0x1800c8820  mov     rsi, [rsp+1F8h+arg_30]
0x1800c8828  mov     [rsp+1F8h+var_170], rsi
0x1800c8830  mov     r14, [rsp+1F8h+arg_38]
0x1800c8838  mov     [rsp+1F8h+var_138], r14
0x1800c8840  mov     [rsp+1F8h+var_130], rdx
0x1800c8848  mov     [rsp+1F8h+var_128], r9
0x1800c8850  mov     rax, [rsp+1F8h+arg_20]
0x1800c8858  mov     [rsp+1F8h+var_150], rax
0x1800c8860  mov     rax, [rsp+1F8h+arg_28]
0x1800c8868  mov     [rsp+1F8h+var_148], rax
0x1800c8870  mov     [rsp+1F8h+var_140], rsi
0x1800c8878  mov     r13, r14
0x1800c887b  xorps   xmm0, xmm0
0x1800c887e  movups  xmmword ptr [r11-78h], xmm0
0x1800c8883  movups  xmmword ptr [r11-68h], xmm0
0x1800c8888  movups  xmmword ptr [r11-58h], xmm0
0x1800c888d  xor     edx, edx; Val
0x1800c888f  lea     r8d, [rdx+58h]; Size
0x1800c8893  lea     rcx, [r11-0E8h]; void *
0x1800c889a  call    memset
0x1800c889f  xor     ebx, ebx
0x1800c88a1  mov     [rsp+1F8h+Binding], rbx
0x1800c88a6  xorps   xmm0, xmm0
0x1800c88a9  movups  xmmword ptr [rsp+1F8h+StringOut.Length], xmm0
0x1800c88b1  xorps   xmm1, xmm1
0x1800c88b4  xor     eax, eax
0x1800c88b6  movups  xmmword ptr [rsp+1F8h+Event.Header], xmm1
0x1800c88be  mov     [rsp+1F8h+Event.Header.WaitListHead.Blink], rax
0x1800c88c6  mov     qword ptr [rsp+1F8h+Interval], rbx
0x1800c88cb  movups  [rsp+1F8h+var_88], xmm0
0x1800c88d3  mov     [rsp+1F8h+Reply], ebx
0x1800c88d7  mov     [rsp+1F8h+var_1A8], ebx
0x1800c88db  mov     [rsp+1F8h+P], rbx
0x1800c88e0  mov     dword ptr [rsp+1F8h+var_88+4], 0FFFFFFFFh
0x1800c88eb  cmp     [rdi+8], rbx
0x1800c88ef  jnz     short loc_1800C88FB
0x1800c88f1  mov     eax, 0C000000Dh
0x1800c88f6  jmp     loc_1800C8DB4
0x1800c88fb  lea     r8, [rsp+1F8h+StringOut]; StringOut
0x1800c8903  mov     rdx, rdi; StringIn
0x1800c8906  mov     ecx, 1; Flags
0x1800c890b  call    cs:__imp_RtlDuplicateUnicodeString
0x1800c8912  nop     dword ptr [rax+rax+00h]
0x1800c8917  mov     edi, eax
0x1800c8919  test    eax, eax
0x1800c891b  js      loc_1800C8DB4
0x1800c8921  mov     [rsp+1F8h+var_158], r14
0x1800c8929  mov     r12, rbx
0x1800c892c  mov     [rsp+1F8h+var_190], ebx
0x1800c8930  mov     eax, ebx
0x1800c8932  mov     [rsp+1F8h+var_1A0], ebx
0x1800c8936  mov     rsi, [rsp+1F8h+PROCESS]
0x1800c893e  cmp     eax, 2
0x1800c8941  jge     loc_1800C8CAF
0x1800c8947  test    eax, eax
0x1800c8949  jnz     short loc_1800C8972
0x1800c894b  call    cs:__imp_PsGetCurrentServerSilo
0x1800c8952  nop     dword ptr [rax+rax+00h]
0x1800c8957  mov     rcx, rax
0x1800c895a  call    cs:__imp_PsAttachSiloToCurrentThread
0x1800c8961  nop     dword ptr [rax+rax+00h]
0x1800c8966  mov     r12, rax
0x1800c8969  mov     rcx, cs:g_CiSystemProcess
0x1800c8970  jmp     short loc_1800C89BA
0x1800c8972  test    rsi, rsi
0x1800c8975  jz      loc_1800C8CA4
0x1800c897b  cmp     [rsp+1F8h+Binding], rbx
0x1800c8980  jz      short loc_1800C8991
0x1800c8982  lea     rcx, [rsp+1F8h+Binding]; Binding
0x1800c8987  call    CipCatDbRpcDisconnect
0x1800c898c  mov     [rsp+1F8h+Binding], rbx
0x1800c8991  lea     rcx, [rsp+1F8h+ApcState]; ApcState
0x1800c8999  call    cs:__imp_KeUnstackDetachProcess
0x1800c89a0  nop     dword ptr [rax+rax+00h]
0x1800c89a5  mov     rcx, r12
0x1800c89a8  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1800c89af  nop     dword ptr [rax+rax+00h]
0x1800c89b4  mov     r12, rbx
0x1800c89b7  mov     rcx, rsi; PROCESS
0x1800c89ba  mov     [rsp+1F8h+var_168], r12
0x1800c89c2  lea     rdx, [rsp+1F8h+ApcState]; ApcState
0x1800c89ca  call    cs:__imp_KeStackAttachProcess
0x1800c89d1  nop     dword ptr [rax+rax+00h]
0x1800c89d6  mov     rdx, r13
0x1800c89d9  lea     rcx, [rsp+1F8h+Binding]
0x1800c89de  call    CipCatDbRpcConnect
0x1800c89e3  mov     edi, eax
0x1800c89e5  test    eax, eax
0x1800c89e7  js      loc_1800C8CAF
0x1800c89ed  mov     edx, 58h ; 'X'; Size
0x1800c89f2  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c89fa  call    cs:__imp_RpcAsyncInitializeHandle
0x1800c8a01  nop     dword ptr [rax+rax+00h]
0x1800c8a06  mov     esi, eax
0x1800c8a08  test    eax, eax
0x1800c8a0a  jz      short loc_1800C8A34
0x1800c8a0c  mov     dword ptr [r14], 5
0x1800c8a13  mov     [r13+4], eax
0x1800c8a17  mov     edi, 0C0000001h
0x1800c8a1c  test    esi, esi
0x1800c8a1e  jz      loc_1800C8C4F
0x1800c8a24  mov     dword ptr [r14], 8
0x1800c8a2b  mov     [r13+4], esi
0x1800c8a2f  jmp     loc_1800C8C93
0x1800c8a34  mov     [rsp+1F8h+pAsync.UserInfo], rbx
0x1800c8a3c  mov     [rsp+1F8h+pAsync.NotificationType], 1
0x1800c8a47  xor     r8d, r8d; State
0x1800c8a4a  xor     edx, edx; Type
0x1800c8a4c  lea     rcx, [rsp+1F8h+Event]; Event
0x1800c8a54  call    cs:__imp_KeInitializeEvent
0x1800c8a5b  nop     dword ptr [rax+rax+00h]
0x1800c8a60  lea     rax, [rsp+1F8h+Event]
0x1800c8a68  mov     qword ptr [rsp+1F8h+pAsync.u], rax
0x1800c8a70  mov     dword ptr [rsp+1F8h+var_88], 10h
0x1800c8a7b  lea     rax, [rsp+1F8h+var_88]
0x1800c8a83  mov     [rsp+1F8h+var_1B8], rax
0x1800c8a88  lea     rax, [rsp+1F8h+P]
0x1800c8a8d  mov     [rsp+1F8h+var_1C0], rax
0x1800c8a92  lea     rax, [rsp+1F8h+var_1A8]
0x1800c8a97  mov     [rsp+1F8h+var_1C8], rax
0x1800c8a9c  mov     rax, [rsp+1F8h+var_160]
0x1800c8aa4  mov     [rsp+1F8h+var_1D0], rax
0x1800c8aa9  mov     eax, [rsp+1F8h+arg_10]
0x1800c8ab0  mov     dword ptr [rsp+1F8h+Timeout], eax
0x1800c8ab4  mov     r9d, 10h
0x1800c8aba  mov     r8, [rsp+1F8h+StringOut.Buffer]
0x1800c8ac2  mov     rdx, [rsp+1F8h+Binding]
0x1800c8ac7  lea     rcx, [rsp+1F8h+pAsync]
0x1800c8acf  call    SSCatDBSmartlockerDefenderCheck2
0x1800c8ad4  jmp     short loc_1800C8B0D
0x1800c8ad6  mov     esi, eax
0x1800c8ad8  xor     ebx, ebx
0x1800c8ada  mov     r12, [rsp+1F8h+var_168]
0x1800c8ae2  mov     r14, [rsp+1F8h+var_138]
0x1800c8aea  mov     rax, [rsp+1F8h+var_130]
0x1800c8af2  mov     [rsp+1F8h+PROCESS], rax
0x1800c8afa  mov     rax, [rsp+1F8h+var_128]
0x1800c8b02  mov     [rsp+1F8h+var_160], rax
0x1800c8b0a  mov     r13, r14
0x1800c8b0d  test    esi, esi
0x1800c8b0f  jz      short loc_1800C8B21
0x1800c8b11  mov     dword ptr [r14], 6
0x1800c8b18  mov     [r13+4], esi
0x1800c8b1c  jmp     loc_1800C8A17
0x1800c8b21  xor     edx, edx
0x1800c8b23  lea     rcx, SiPolicyIDNightsWatchDesktop
0x1800c8b2a  call    SIPolicyIsPolicyActive
0x1800c8b2f  test    al, al
0x1800c8b31  jnz     short loc_1800C8B4A
0x1800c8b33  lea     rcx, SiPolicyIDNightsWatchDesktopEval
0x1800c8b3a  call    SIPolicyIsPolicyActive
0x1800c8b3f  test    al, al
0x1800c8b41  mov     rax, 0FFFFFFFFFB3B4C00h
0x1800c8b48  jz      short loc_1800C8B51
0x1800c8b4a  mov     rax, 0FFFFFFFFDC3CBA00h
0x1800c8b51  mov     qword ptr [rsp+1F8h+Interval], rax
0x1800c8b56  lea     rax, [rsp+1F8h+Interval]
0x1800c8b5b  mov     [rsp+1F8h+Timeout], rax; Timeout
0x1800c8b60  xor     r9d, r9d; Alertable
0x1800c8b63  xor     r8d, r8d; WaitMode
0x1800c8b66  xor     edx, edx; WaitReason
0x1800c8b68  lea     rcx, [rsp+1F8h+Event]; Object
0x1800c8b70  call    cs:__imp_KeWaitForSingleObject
0x1800c8b77  nop     dword ptr [rax+rax+00h]
0x1800c8b7c  mov     edi, eax
0x1800c8b7e  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c8b86  test    eax, eax
0x1800c8b88  jz      short loc_1800C8BFB
0x1800c8b8a  mov     dword ptr [r14], 7
0x1800c8b91  mov     [r13+4], eax
0x1800c8b95  mov     edx, 1; fAbort
0x1800c8b9a  call    cs:__imp_RpcAsyncCancelCall
0x1800c8ba1  nop     dword ptr [rax+rax+00h]
0x1800c8ba6  mov     edi, eax
0x1800c8ba8  mov     [rsp+1F8h+Timeout], rbx; Timeout
0x1800c8bad  xor     r9d, r9d; Alertable
0x1800c8bb0  xor     r8d, r8d; WaitMode
0x1800c8bb3  xor     edx, edx; WaitReason
0x1800c8bb5  lea     rcx, [rsp+1F8h+Event]; Object
0x1800c8bbd  call    cs:__imp_KeWaitForSingleObject
0x1800c8bc4  nop     dword ptr [rax+rax+00h]
0x1800c8bc9  test    edi, edi
0x1800c8bcb  jz      short loc_1800C8BD8
0x1800c8bcd  mov     dword ptr [r14], 10h
0x1800c8bd4  mov     [r13+4], edi
0x1800c8bd8  lea     rdx, [rsp+1F8h+Reply]; Reply
0x1800c8bdd  lea     rcx, [rsp+1F8h+pAsync]; pAsync
0x1800c8be5  call    cs:__imp_RpcAsyncCompleteCall
0x1800c8bec  nop     dword ptr [rax+rax+00h]
0x1800c8bf1  mov     edi, 0C0000001h
0x1800c8bf6  jmp     loc_1800C8D57
0x1800c8bfb  lea     rdx, [rsp+1F8h+Reply]; Reply
0x1800c8c00  call    cs:__imp_RpcAsyncCompleteCall
0x1800c8c07  nop     dword ptr [rax+rax+00h]
0x1800c8c0c  mov     esi, eax
0x1800c8c0e  cmp     eax, 0C0020018h
0x1800c8c13  jnz     loc_1800C8A1C
0x1800c8c19  mov     ecx, [rsp+1F8h+var_190]
0x1800c8c1d  cmp     ecx, 14h
0x1800c8c20  jnb     loc_1800C8A1C
0x1800c8c26  inc     ecx
0x1800c8c28  mov     [rsp+1F8h+var_190], ecx
0x1800c8c2c  mov     qword ptr [rsp+1F8h+Interval], 0FFFFFFFFFFF0BDC0h
0x1800c8c35  lea     r8, [rsp+1F8h+Interval]; Interval
0x1800c8c3a  xor     edx, edx; Alertable
0x1800c8c3c  xor     ecx, ecx; WaitMode
0x1800c8c3e  call    cs:__imp_KeDelayExecutionThread
0x1800c8c45  nop     dword ptr [rax+rax+00h]
0x1800c8c4a  jmp     loc_1800C89ED
0x1800c8c4f  mov     eax, [rsp+1F8h+Reply]
0x1800c8c53  test    eax, eax
0x1800c8c55  jz      short loc_1800C8CAF
0x1800c8c57  mov     rcx, [rsp+1F8h+var_158]
0x1800c8c5f  cmp     eax, 422h
0x1800c8c64  jnz     short loc_1800C8C89
0x1800c8c66  mov     dword ptr [r14], 11h
0x1800c8c6d  mov     [rcx+4], eax
0x1800c8c70  mov     rcx, [rsp+1F8h+var_140]
0x1800c8c78  mov     dword ptr [rcx+8], 0FFFFFFFFh
0x1800c8c7f  mov     [rcx], rbx
0x1800c8c82  mov     edi, ebx
0x1800c8c84  jmp     loc_1800C8D57
0x1800c8c89  mov     dword ptr [r14], 0Ah
0x1800c8c90  mov     [rcx+4], eax
0x1800c8c93  mov     rsi, [rsp+1F8h+PROCESS]
0x1800c8c9b  mov     eax, [rsp+1F8h+var_1A0]
0x1800c8c9f  mov     edi, 0C0000001h
0x1800c8ca4  inc     eax
0x1800c8ca6  mov     [rsp+1F8h+var_1A0], eax
0x1800c8caa  jmp     loc_1800C893E
0x1800c8caf  test    edi, edi
0x1800c8cb1  js      loc_1800C8D57
0x1800c8cb7  mov     ecx, ebx
0x1800c8cb9  cmp     ecx, [rsp+1F8h+var_1A8]
0x1800c8cbd  jnb     short loc_1800C8CEA
0x1800c8cbf  mov     eax, ecx
0x1800c8cc1  lea     rdx, [rax+rax*2]
0x1800c8cc5  mov     rax, [rsp+1F8h+P]
0x1800c8cca  cmp     [rax+rdx*8+10h], rbx
0x1800c8ccf  jz      short loc_1800C8CE3
0x1800c8cd1  cmp     dword ptr [rax+rdx*8+4], 1
0x1800c8cd6  jnz     short loc_1800C8CDF
0x1800c8cd8  cmp     dword ptr [rax+rdx*8+8], 1Ch
0x1800c8cdd  jnz     short loc_1800C8CE3
0x1800c8cdf  inc     ecx
0x1800c8ce1  jmp     short loc_1800C8CB9
0x1800c8ce3  mov     edi, 0C000000Dh
0x1800c8ce8  jmp     short loc_1800C8D57
0x1800c8cea  mov     eax, [rsp+1F8h+var_1A8]
0x1800c8cee  mov     rcx, [rsp+1F8h+var_150]
0x1800c8cf6  mov     [rcx], eax
0x1800c8cf8  mov     rax, [rsp+1F8h+P]
0x1800c8cfd  mov     rcx, [rsp+1F8h+var_148]
0x1800c8d05  mov     [rcx], rax
0x1800c8d08  mov     [rsp+1F8h+P], rbx
0x1800c8d0d  mov     eax, dword ptr [rsp+1F8h+var_88+4]
0x1800c8d14  mov     rcx, [rsp+1F8h+var_140]
0x1800c8d1c  mov     [rcx+8], eax
0x1800c8d1f  mov     rax, 0FFFFF78000000014h
0x1800c8d29  mov     rax, [rax]
0x1800c8d2c  mov     ecx, 1C20h
0x1800c8d31  cmp     qword ptr [rsp+1F8h+var_88+8], rcx
0x1800c8d39  cmova   rcx, qword ptr [rsp+1F8h+var_88+8]
0x1800c8d42  imul    rcx, 989680h
0x1800c8d49  add     rcx, rax
0x1800c8d4c  mov     rax, [rsp+1F8h+var_170]
0x1800c8d54  mov     [rax], rcx
0x1800c8d57  cmp     [rsp+1F8h+Binding], rbx
0x1800c8d5c  jz      short loc_1800C8D68
0x1800c8d5e  lea     rcx, [rsp+1F8h+Binding]; Binding
0x1800c8d63  call    CipCatDbRpcDisconnect
0x1800c8d68  mov     edx, [rsp+1F8h+var_1A8]
0x1800c8d6c  mov     rcx, [rsp+1F8h+P]; P
0x1800c8d71  call    CiCatDbFreeExtraInfoFromDefender
0x1800c8d76  lea     rcx, [rsp+1F8h+ApcState]; ApcState
0x1800c8d7e  call    cs:__imp_KeUnstackDetachProcess
0x1800c8d85  nop     dword ptr [rax+rax+00h]
0x1800c8d8a  test    r12, r12
0x1800c8d8d  jz      short loc_1800C8D9E
0x1800c8d8f  mov     rcx, r12
0x1800c8d92  call    cs:__imp_PsDetachSiloFromCurrentThread
0x1800c8d99  nop     dword ptr [rax+rax+00h]
0x1800c8d9e  lea     rcx, [rsp+1F8h+StringOut]; UnicodeString
0x1800c8da6  call    cs:__imp_RtlFreeUnicodeString
0x1800c8dad  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
