# IpGetAllInterfaceParameters

- ea: `0x140065200`
- end: `0x1400656bf`
- name: `IpGetAllInterfaceParameters`
- size: `1215`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x140031040`
- `0x1400490e0`
- `0x140065200`
- `0x140065e20`
- `0x14014ca68`
- `0x1401bf4d0`
- `0x1401bfa80`
- `0x1401bffa0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400652ab`
- `ntoskrnl!KfRaiseIrql` at `0x1400653bc`
- `ntoskrnl!KfRaiseIrql` at `0x1400652ab`
- `ntoskrnl!KfRaiseIrql` at `0x1400653bc`
- `ntoskrnl!KeLowerIrql` at `0x14006536a`
- `ntoskrnl!KeLowerIrql` at `0x140065461`
- `ntoskrnl!KeLowerIrql` at `0x140065491`
- `ntoskrnl!KeLowerIrql` at `0x14006563a`
- `ntoskrnl!KeLowerIrql` at `0x14006536a`
- `ntoskrnl!KeLowerIrql` at `0x140065461`
- `ntoskrnl!KeLowerIrql` at `0x140065491`
- `ntoskrnl!KeLowerIrql` at `0x14006563a`
- `ntoskrnl!IoQueueWorkItem` at `0x140065621`
- `ntoskrnl!IoQueueWorkItem` at `0x140065621`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400652ed`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140065400`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x1400652ed`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x140065400`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065302`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065416`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065302`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x140065416`
- `ntoskrnl!KeTestSpinLock` at `0x1400652d1`
- `ntoskrnl!KeTestSpinLock` at `0x1400653e3`
- `ntoskrnl!KeTestSpinLock` at `0x1400652d1`
- `ntoskrnl!KeTestSpinLock` at `0x1400653e3`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400655ae`
- `NETIO!NetioIsCompartmentAccessibleByThread` at `0x1400655ae`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140065277`
- `NDIS!NdisGetThreadObjectCompartmentScope` at `0x140065277`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140065294`
- `NDIS!NdisGetThreadObjectCompartmentId` at `0x140065294`

## pseudocode

```c
__int64 __fastcall IpGetAllInterfaceParameters(__int64 a1)
{
  _QWORD *v1; // r15
  __int64 v3; // rbp
  int ThreadObjectCompartmentId; // esi
  KIRQL v5; // r14
  _QWORD **v6; // rdx
  _QWORD *i; // rax
  _QWORD *v8; // rbx
  signed __int64 v9; // rax
  bool v10; // cc
  signed __int64 v11; // rax
  int v12; // ecx
  _QWORD *j; // rbx
  volatile signed __int64 *NextInterfaceForThread; // rdi
  __int64 v15; // rcx
  __int64 result; // rax
  __int64 v17; // rbp
  __int64 v18; // rsi
  __int64 v19; // rbx
  int IsEnabledDeviceUsageNoInline; // eax
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // rcx
  __int64 v24; // rdx
  __int64 v25; // rdx
  __int64 v26; // rcx
  int v27; // ecx
  KIRQL v28; // [rsp+40h] [rbp-68h]
  _BYTE v29[24]; // [rsp+48h] [rbp-60h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+60h] [rbp-48h] BYREF

  v1 = *(_QWORD **)(a1 + 16);
  v3 = *(_QWORD *)(*(_QWORD *)a1 + 32LL);
  memset(v29, 0, sizeof(v29));
  if ( (Feature_CLAT_DHCP_Option108__private_featureState & 0x10) == 0 )
    ((void (*)(void))Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline)();
  memset(v29, 0, sizeof(v29));
  NdisGetThreadObjectCompartmentScope(KeGetCurrentThread(), v29, &v29[4]);
  ThreadObjectCompartmentId = *(_DWORD *)&v29[4];
  if ( !*(_DWORD *)&v29[4] )
    ThreadObjectCompartmentId = NdisGetThreadObjectCompartmentId(KeGetCurrentThread());
  v5 = KfRaiseIrql(2u);
  memset(&LockHandle, 0, sizeof(LockHandle));
  _InterlockedIncrement((volatile signed __int32 *)(v3 + 19888));
  if ( !KeTestSpinLock((PKSPIN_LOCK)(v3 + 19880)) )
  {
    _InterlockedDecrement((volatile signed __int32 *)(v3 + 19888));
    KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 19880), &LockHandle);
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 19888));
    KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
  }
  v6 = (_QWORD **)(*(_QWORD *)(v3 + 19872)
                 + 16LL * (ThreadObjectCompartmentId & (unsigned int)(*(_DWORD *)(v3 + 19868) - 1)));
  for ( i = *v6; ; i = (_QWORD *)*i )
  {
    if ( i == v6 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v3 + 19888));
      KeLowerIrql(v5);
      goto LABEL_15;
    }
    v8 = i - 6;
    if ( *((_DWORD *)i - 12) == ThreadObjectCompartmentId )
      break;
  }
  if ( _InterlockedIncrement64(v8 + 4) <= 1 )
    __fastfail(0xEu);
  _InterlockedDecrement((volatile signed __int32 *)(v3 + 19888));
  KeLowerIrql(v5);
  if ( v8 )
  {
    *(_OWORD *)&v29[8] = *(_OWORD *)((char *)v8 + 4);
    v9 = _InterlockedExchangeAdd64(v8 + 4, 0xFFFFFFFFFFFFFFFFuLL);
    v10 = v9 <= 1;
    v11 = v9 - 1;
    if ( v10 )
    {
      if ( v11 )
        __fastfail(0xEu);
      IoQueueWorkItem((PIO_WORKITEM)v8[16], IppCleanupCompartmentWorkerRoutine, DelayedWorkQueue, v8);
    }
  }
LABEL_15:
  v12 = *(_DWORD *)(a1 + 32);
  if ( v12 )
  {
    v27 = v12 - 1;
    if ( v27 )
    {
      if ( v27 != 1 )
        return 3221225485LL;
    }
    else
    {
      memset(v1, 0, *(unsigned int *)(a1 + 24));
    }
    NextInterfaceForThread = (volatile signed __int64 *)IppGetNextInterfaceForThread(v3, v29, v1);
  }
  else
  {
    v28 = KfRaiseIrql(2u);
    memset(&LockHandle, 0, sizeof(LockHandle));
    _InterlockedIncrement((volatile signed __int32 *)(v3 + 19904));
    if ( !KeTestSpinLock((PKSPIN_LOCK)(v3 + 19896)) )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v3 + 19904));
      KeAcquireInStackQueuedSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 19896), &LockHandle);
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 19904));
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    }
    for ( j = *(_QWORD **)(v3 + 19912); ; j = (_QWORD *)*j )
    {
      if ( j == (_QWORD *)(v3 + 19912) )
      {
        _InterlockedDecrement((volatile signed __int32 *)(v3 + 19904));
        KeLowerIrql(v28);
        NextInterfaceForThread = 0;
        goto LABEL_25;
      }
      NextInterfaceForThread = j - 20;
      if ( !memcmp(v1, j - 18, 8u) )
        break;
    }
    if ( _InterlockedIncrement64(NextInterfaceForThread + 19) <= 1 )
      __fastfail(0xEu);
    _InterlockedDecrement((volatile signed __int32 *)(v3 + 19904));
    KeLowerIrql(v28);
    if ( j != (_QWORD *)160 )
    {
      v25 = *NextInterfaceForThread + 4;
      v26 = **(unsigned int **)NextInterfaceForThread;
      memset(&LockHandle, 0, sizeof(LockHandle));
      if ( !(unsigned __int8)NetioIsCompartmentAccessibleByThread(v26, v25, 1) )
      {
        IppDereferenceInterface(j - 20);
        NextInterfaceForThread = 0;
      }
    }
  }
LABEL_25:
  v15 = *(unsigned int *)(a1 + 32);
  if ( NextInterfaceForThread )
  {
    if ( (_DWORD)v15 )
      *v1 = *((_QWORD *)NextInterfaceForThread + 2);
    v17 = *(_QWORD *)(a1 + 40);
    v18 = *(_QWORD *)(a1 + 56);
    v19 = *(_QWORD *)(a1 + 72);
    if ( (Feature_CLAT_DHCP_Option108__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_CLAT_DHCP_Option108__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline(v15);
    if ( !IsEnabledDeviceUsageNoInline && *(_QWORD *)(a1 + 72) )
      *(_DWORD *)(a1 + 80) = 32;
    if ( (Feature_CLAT_DHCP_Option108__private_featureState & 0x10) != 0 )
      v21 = Feature_CLAT_DHCP_Option108__private_featureState & 1;
    else
      v21 = Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline(v15);
    if ( v21 )
    {
      if ( v19 )
        v24 = a1 + 80;
      else
        v24 = 0;
      if ( v18 )
        v23 = a1 + 64;
      else
        v23 = 0;
      if ( v17 )
        v22 = a1 + 48;
      else
        v22 = 0;
    }
    else
    {
      v22 = 0;
      v23 = 0;
      v24 = 0;
    }
    IppFillInterfaceData(NextInterfaceForThread, 0, v17, v18, v19, v22, v23, v24);
    IppDereferenceInterface((PVOID)NextInterfaceForThread);
    return 0;
  }
  else
  {
    result = 3221226021LL;
    if ( (_DWORD)v15 )
      return 2147483674LL;
  }
  return result;
}

```

## disassembly

```asm
0x140065200  mov     [rsp+arg_10], rbp
0x140065205  mov     [rsp+arg_18], rsi
0x14006520a  push    rdi
0x14006520b  push    r12
0x14006520d  push    r13
0x14006520f  push    r14
0x140065211  push    r15
0x140065213  sub     rsp, 80h
0x14006521a  mov     rax, cs:__security_cookie
0x140065221  xor     rax, rsp
0x140065224  mov     [rsp+0A8h+var_30], rax
0x140065229  mov     rax, [rcx]
0x14006522c  xorps   xmm0, xmm0
0x14006522f  mov     r15, [rcx+10h]
0x140065233  mov     r12, rcx
0x140065236  mov     rbp, [rax+20h]
0x14006523a  xor     eax, eax
0x14006523c  mov     [rsp+0A8h+var_50], rax
0x140065241  movups  [rsp+0A8h+var_60], xmm0
0x140065246  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x14006524c  test    al, 10h
0x14006524e  jnz     short loc_140065255
0x140065250  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x140065255  xorps   xmm0, xmm0
0x140065258  lea     r8, [rsp+0A8h+var_60+4]
0x14006525d  xor     eax, eax
0x14006525f  lea     rdx, [rsp+0A8h+var_60]
0x140065264  movups  [rsp+0A8h+var_60], xmm0
0x140065269  mov     [rsp+0A8h+var_50], rax
0x14006526e  mov     rcx, gs:188h
0x140065277  call    cs:__imp_NdisGetThreadObjectCompartmentScope
0x14006527e  nop     dword ptr [rax+rax+00h]
0x140065283  mov     esi, dword ptr [rsp+0A8h+var_60+4]
0x140065287  test    esi, esi
0x140065289  jnz     short loc_1400652A2
0x14006528b  mov     rcx, gs:188h
0x140065294  call    cs:__imp_NdisGetThreadObjectCompartmentId
0x14006529b  nop     dword ptr [rax+rax+00h]
0x1400652a0  mov     esi, eax
0x1400652a2  mov     cl, 2; NewIrql
0x1400652a4  lea     rdi, [rbp+4DA8h]
0x1400652ab  call    cs:__imp_KfRaiseIrql
0x1400652b2  nop     dword ptr [rax+rax+00h]
0x1400652b7  movzx   r14d, al
0x1400652bb  xorps   xmm0, xmm0
0x1400652be  xor     eax, eax
0x1400652c0  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x1400652c5  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x1400652ca  lock inc dword ptr [rdi+8]
0x1400652ce  mov     rcx, rdi; SpinLock
0x1400652d1  call    cs:__imp_KeTestSpinLock
0x1400652d8  nop     dword ptr [rax+rax+00h]
0x1400652dd  test    al, al
0x1400652df  jnz     short loc_14006530E
0x1400652e1  lock dec dword ptr [rdi+8]
0x1400652e5  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x1400652ea  mov     rcx, rdi; SpinLock
0x1400652ed  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400652f4  nop     dword ptr [rax+rax+00h]
0x1400652f9  lock inc dword ptr [rdi+8]
0x1400652fd  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140065302  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x140065309  nop     dword ptr [rax+rax+00h]
0x14006530e  mov     edx, [rbp+4D9Ch]
0x140065314  dec     edx
0x140065316  mov     eax, esi
0x140065318  and     rdx, rax
0x14006531b  mov     [rsp+0A8h+arg_8], rbx
0x140065323  shl     rdx, 4
0x140065327  add     rdx, [rbp+4DA0h]
0x14006532e  mov     rax, [rdx]
0x140065331  mov     r13d, 1
0x140065337  cmp     rax, rdx
0x14006533a  jz      loc_140065632
0x140065340  cmp     [rax-30h], esi
0x140065343  lea     rbx, [rax-30h]
0x140065347  jnz     loc_140065605
0x14006534d  mov     eax, r13d
0x140065350  lock xadd [rbx+20h], rax
0x140065356  inc     rax
0x140065359  cmp     rax, r13
0x14006535c  jle     loc_140065672
0x140065362  lock dec dword ptr [rdi+8]
0x140065366  movzx   ecx, r14b; NewIrql
0x14006536a  call    cs:__imp_KeLowerIrql
0x140065371  nop     dword ptr [rax+rax+00h]
0x140065376  test    rbx, rbx
0x140065379  jz      short loc_1400653A6
0x14006537b  movups  xmm0, xmmword ptr [rbx+4]
0x14006537f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140065386  movups  [rsp+0A8h+var_60+8], xmm0
0x14006538b  lock xadd [rbx+20h], rax
0x140065391  sub     rax, r13
0x140065394  jg      short loc_1400653A6
0x140065396  test    rax, rax
0x140065399  jz      loc_14006560D
0x14006539f  mov     ecx, 0Eh
0x1400653a4  int     29h; Win8: RtlFailFast(ecx)
0x1400653a6  mov     ecx, [r12+20h]
0x1400653ab  test    ecx, ecx
0x1400653ad  jnz     loc_1400655F1
0x1400653b3  mov     cl, 2; NewIrql
0x1400653b5  lea     r14, [rbp+4DB8h]
0x1400653bc  call    cs:__imp_KfRaiseIrql
0x1400653c3  nop     dword ptr [rax+rax+00h]
0x1400653c8  mov     [rsp+0A8h+var_68], al
0x1400653cc  xorps   xmm0, xmm0
0x1400653cf  xor     eax, eax
0x1400653d1  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x1400653d6  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x1400653db  lock inc dword ptr [r14+8]
0x1400653e0  mov     rcx, r14; SpinLock
0x1400653e3  call    cs:__imp_KeTestSpinLock
0x1400653ea  nop     dword ptr [rax+rax+00h]
0x1400653ef  test    al, al
0x1400653f1  jnz     short loc_140065422
0x1400653f3  lock dec dword ptr [r14+8]
0x1400653f8  lea     rdx, [rsp+0A8h+LockHandle]; LockHandle
0x1400653fd  mov     rcx, r14; SpinLock
0x140065400  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x140065407  nop     dword ptr [rax+rax+00h]
0x14006540c  lock inc dword ptr [r14+8]
0x140065411  lea     rcx, [rsp+0A8h+LockHandle]; LockHandle
0x140065416  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14006541d  nop     dword ptr [rax+rax+00h]
0x140065422  lea     rsi, [rbp+4DC8h]
0x140065429  mov     rbx, [rsi]
0x14006542c  nop     dword ptr [rax+00h]
0x140065430  cmp     rbx, rsi
0x140065433  jz      short loc_140065457
0x140065435  lea     rdi, [rbx-0A0h]
0x14006543c  mov     r8d, 8; Size
0x140065442  lea     rdx, [rdi+10h]; Buf2
0x140065446  mov     rcx, r15; Buf1
0x140065449  call    memcmp
0x14006544e  test    eax, eax
0x140065450  jz      short loc_140065471
0x140065452  mov     rbx, [rbx]
0x140065455  jmp     short loc_140065430
0x140065457  movzx   ecx, [rsp+0A8h+var_68]; NewIrql
0x14006545c  lock dec dword ptr [r14+8]
0x140065461  call    cs:__imp_KeLowerIrql
0x140065468  nop     dword ptr [rax+rax+00h]
0x14006546d  xor     edi, edi
0x14006546f  jmp     short loc_1400654A6
0x140065471  lock xadd [rdi+98h], r13
0x14006547a  inc     r13
0x14006547d  cmp     r13, 1
0x140065481  jle     loc_1400656A7
0x140065487  movzx   ecx, [rsp+0A8h+var_68]; NewIrql
0x14006548c  lock dec dword ptr [r14+8]
0x140065491  call    cs:__imp_KeLowerIrql
0x140065498  nop     dword ptr [rax+rax+00h]
0x14006549d  test    rdi, rdi
0x1400654a0  jnz     loc_140065585
0x1400654a6  mov     ecx, [r12+20h]
0x1400654ab  test    rdi, rdi
0x1400654ae  jnz     short loc_1400654F2
0x1400654b0  test    ecx, ecx
0x1400654b2  mov     eax, 0C0000225h
0x1400654b7  mov     edx, 8000001Ah
0x1400654bc  cmovnz  eax, edx
0x1400654bf  mov     rbx, [rsp+0A8h+arg_8]
0x1400654c7  mov     rcx, [rsp+0A8h+var_30]
0x1400654cc  xor     rcx, rsp; StackCookie
0x1400654cf  call    __security_check_cookie
0x1400654d4  lea     r11, [rsp+0A8h+var_28]
0x1400654dc  mov     rbp, [r11+40h]
0x1400654e0  mov     rsi, [r11+48h]
0x1400654e4  mov     rsp, r11
0x1400654e7  pop     r15
0x1400654e9  pop     r14
0x1400654eb  pop     r13
0x1400654ed  pop     r12
0x1400654ef  pop     rdi
0x1400654f0  retn
0x1400654f2  test    ecx, ecx
0x1400654f4  jnz     loc_1400656B3
0x1400654fa  mov     rbp, [r12+28h]
0x1400654ff  mov     rsi, [r12+38h]
0x140065504  mov     rbx, [r12+48h]
0x140065509  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x14006550f  test    al, 10h
0x140065511  jnz     loc_1400655E1
0x140065517  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x14006551c  test    eax, eax
0x14006551e  jnz     short loc_140065531
0x140065520  cmp     qword ptr [r12+48h], 0
0x140065526  jz      short loc_140065531
0x140065528  mov     dword ptr [r12+50h], 20h ; ' '
0x140065531  mov     eax, cs:Feature_CLAT_DHCP_Option108__private_featureState
0x140065537  test    al, 10h
0x140065539  jnz     loc_1400655E9
0x14006553f  call    Feature_CLAT_DHCP_Option108__private_IsEnabledDeviceUsageNoInline
0x140065544  test    eax, eax
0x140065546  jnz     loc_1400655D1
0x14006554c  xor     eax, eax
0x14006554e  xor     ecx, ecx
0x140065550  xor     edx, edx
0x140065552  mov     [rsp+0A8h+var_70], rdx
0x140065557  mov     r9, rsi
0x14006555a  mov     [rsp+0A8h+var_78], rcx
0x14006555f  mov     r8, rbp
0x140065562  mov     [rsp+0A8h+var_80], rax
0x140065567  mov     rcx, rdi
0x14006556a  xor     edx, edx
0x14006556c  mov     [rsp+0A8h+var_88], rbx
0x140065571  call    IppFillInterfaceData
0x140065576  mov     rcx, rdi; Context
0x140065579  call    IppDereferenceInterface
0x14006557e  xor     eax, eax
0x140065580  jmp     loc_1400654BF
0x140065585  mov     rcx, [rdi]
0x140065588  xor     eax, eax
0x14006558a  mov     qword ptr [rsp+0A8h+LockHandle.OldIrql], rax
0x14006558f  mov     r9b, 1
0x140065592  xorps   xmm0, xmm0
0x140065595  lea     rax, [rsp+0A8h+var_60]
0x14006559a  movzx   r8d, r9b
0x14006559e  mov     [rsp+0A8h+var_88], rax
0x1400655a3  lea     rdx, [rcx+4]
0x1400655a7  mov     ecx, [rcx]
0x1400655a9  movups  xmmword ptr [rsp+0A8h+LockHandle.LockQueue.Next], xmm0
0x1400655ae  call    cs:__imp_NetioIsCompartmentAccessibleByThread
0x1400655b5  nop     dword ptr [rax+rax+00h]
0x1400655ba  test    al, al
0x1400655bc  jnz     loc_1400654A6
0x1400655c2  mov     rcx, rdi; Context
0x1400655c5  call    IppDereferenceInterface
0x1400655ca  xor     edi, edi
0x1400655cc  jmp     loc_1400654A6
0x1400655d1  test    rbx, rbx
0x1400655d4  jnz     loc_14006567E
0x1400655da  xor     edx, edx
0x1400655dc  jmp     loc_140065683
0x1400655e1  and     eax, 1
0x1400655e4  jmp     loc_14006551C
0x1400655e9  and     eax, 1
0x1400655ec  jmp     loc_140065544
0x1400655f1  sub     ecx, r13d
0x1400655f4  jz      short loc_14006564B
0x1400655f6  cmp     ecx, r13d
0x1400655f9  jz      short loc_14006565A
0x1400655fb  mov     eax, 0C000000Dh
0x140065600  jmp     loc_1400654BF
0x140065605  mov     rax, [rax]
0x140065608  jmp     loc_140065331
0x14006560d  mov     rcx, [rbx+80h]; IoWorkItem
0x140065614  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x14006561b  mov     r9, rbx; Context
0x14006561e  mov     r8d, r13d; QueueType
0x140065621  call    cs:__imp_IoQueueWorkItem
0x140065628  nop     dword ptr [rax+rax+00h]
0x14006562d  jmp     loc_1400653A6
0x140065632  lock dec dword ptr [rdi+8]
0x140065636  movzx   ecx, r14b; NewIrql
0x14006563a  call    cs:__imp_KeLowerIrql
0x140065641  nop     dword ptr [rax+rax+00h]
0x140065646  jmp     loc_1400653A6
0x14006564b  mov     r8d, [r12+18h]; Size
0x140065650  xor     edx, edx; Val
0x140065652  mov     rcx, r15; void *
0x140065655  call    memset
0x14006565a  mov     r8, r15
0x14006565d  lea     rdx, [rsp+0A8h+var_60]
0x140065662  mov     rcx, rbp
0x140065665  call    IppGetNextInterfaceForThread
0x14006566a  mov     rdi, rax
0x14006566d  jmp     loc_1400654A6
0x140065672  mov     ecx, 0Eh
0x140065677  int     29h; Win8: RtlFailFast(ecx)
0x140065679  jmp     loc_140065362
0x14006567e  lea     rdx, [r12+50h]
0x140065683  test    rsi, rsi
0x140065686  jz      short loc_14006569C
0x140065688  lea     rcx, [r12+40h]
0x14006568d  test    rbp, rbp
0x140065690  jz      short loc_1400656A0
0x140065692  lea     rax, [r12+30h]
0x140065697  jmp     loc_140065552
0x14006569c  xor     ecx, ecx
0x14006569e  jmp     short loc_14006568D
0x1400656a0  xor     eax, eax
0x1400656a2  jmp     loc_140065552
0x1400656a7  mov     ecx, 0Eh
0x1400656ac  int     29h; Win8: RtlFailFast(ecx)
0x1400656ae  jmp     loc_140065487
0x1400656b3  mov     rax, [rdi+10h]
0x1400656b7  mov     [r15], rax
0x1400656ba  jmp     loc_1400654FA
```
