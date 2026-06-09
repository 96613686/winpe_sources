# NtfsProcessRepairQueue

- ea: `0x14004dc90`
- end: `0x14004e0d2`
- name: `NtfsProcessRepairQueue`
- size: `1090`
- prototype: `void __fastcall(char *StartContext)`
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400054e8`
- `0x14002b4a0`
- `0x14004161c`
- `0x14004dc90`
- `0x14004e18c`
- `0x140059250`
- `0x1400ec74c`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14004ddbe`
- `ntoskrnl!KeSetEvent` at `0x14004dde4`
- `ntoskrnl!KeSetEvent` at `0x14004df83`
- `ntoskrnl!KeSetEvent` at `0x14004df9e`
- `ntoskrnl!KeSetEvent` at `0x14004dfda`
- `ntoskrnl!KeSetEvent` at `0x14004e040`
- `ntoskrnl!KeSetEvent` at `0x14004e064`
- `ntoskrnl!KeSetEvent` at `0x14004ddbe`
- `ntoskrnl!KeSetEvent` at `0x14004dde4`
- `ntoskrnl!KeSetEvent` at `0x14004df83`
- `ntoskrnl!KeSetEvent` at `0x14004df9e`
- `ntoskrnl!KeSetEvent` at `0x14004dfda`
- `ntoskrnl!KeSetEvent` at `0x14004e040`
- `ntoskrnl!KeSetEvent` at `0x14004e064`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004dcba`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004dcba`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e099`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004e099`
- `ntoskrnl!IoSetActivityIdThread` at `0x14004de8f`
- `ntoskrnl!IoSetActivityIdThread` at `0x14004de8f`
- `ntoskrnl!IoClearActivityIdThread` at `0x14004e00a`
- `ntoskrnl!IoClearActivityIdThread` at `0x14004e00a`
- `ntoskrnl!RtlFindMessage` at `0x14004dd08`
- `ntoskrnl!RtlFindMessage` at `0x14004dd08`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004dd62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004de25`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004dd62`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14004de25`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004ddf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004def5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004df57`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e088`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004ddf6`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004def5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004df57`
- `ntoskrnl!KeReleaseSpinLock` at `0x14004e088`
- `ntoskrnl!KeClearEvent` at `0x14004dd98`
- `ntoskrnl!KeClearEvent` at `0x14004dd98`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004de16`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004df19`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004de16`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004df19`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14004dd3f`
- `ntoskrnl!KeReleaseGuardedMutex` at `0x14004dd3f`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14004dd26`
- `ntoskrnl!KeAcquireGuardedMutex` at `0x14004dd26`

## pseudocode

```c
void __fastcall NtfsProcessRepairQueue(char *StartContext)
{
  KIRQL v2; // r15
  int v3; // eax
  __int64 *v4; // rdi
  int v5; // esi
  _QWORD *v6; // rcx
  __int64 v7; // rcx
  __int64 v8; // r9
  __int64 v9; // r14
  __int64 v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 *v13; // rcx
  __int64 **v14; // rax
  int v15; // eax
  PMESSAGE_RESOURCE_ENTRY *MessageResourceEntry; // [rsp+20h] [rbp-40h]
  PMESSAGE_RESOURCE_ENTRY v17; // [rsp+30h] [rbp-30h] BYREF
  __int128 v18; // [rsp+38h] [rbp-28h] BYREF
  __int64 v19; // [rsp+48h] [rbp-18h]

  KeEnterCriticalRegion();
  *((_QWORD *)StartContext + 691) = KeGetCurrentThread();
  if ( !byte_140095C55 )
  {
    v17 = 0;
    byte_140095C55 = RtlFindMessage(DriverObject->DriverStart, 0xBu, 0, 0x61B0u, &v17) >= 0;
  }
  KeAcquireGuardedMutex(&NtfsRepairEventCounterMutex);
  ++NtfsRepairThreadCount;
  KeReleaseGuardedMutex(&NtfsRepairEventCounterMutex);
  while ( 1 )
  {
    v19 = 0;
    v18 = 0;
    v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)StartContext + 692);
    if ( *((_DWORD *)StartContext + 1390) )
      goto LABEL_12;
    *((_DWORD *)StartContext + 1391) |= 0x800u;
    v17 = (PMESSAGE_RESOURCE_ENTRY)-600000000LL;
    KeClearEvent((PRKEVENT)StartContext + 232);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1398, 0, 0) )
      KeSetEvent((PRKEVENT)(StartContext + 5600), 0, 0);
    if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1406, 0, 0) )
      KeSetEvent((PRKEVENT)(StartContext + 5632), 0, 0);
    do
    {
      KeReleaseSpinLock((PKSPIN_LOCK)StartContext + 692, v2);
      KeWaitForSingleObject(StartContext + 5568, Executive, 0, 0, (PLARGE_INTEGER)&v17);
      v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)StartContext + 692);
      v3 = *((_DWORD *)StartContext + 1391);
    }
    while ( (v3 & 4) != 0 );
    if ( !*((_DWORD *)StartContext + 1390) )
      break;
    *((_DWORD *)StartContext + 1391) = v3 & 0xFFFFF7FF;
LABEL_12:
    v4 = (__int64 *)*((_QWORD *)StartContext + 693);
    v5 = 0;
    v6 = (_QWORD *)v4[22];
    if ( v6 )
    {
      *((_QWORD *)&v18 + 1) = *v6;
      v19 = v6[1];
      *(_QWORD *)&v18 = (char *)&v18 + 8;
    }
    else
    {
      *(_QWORD *)&v18 = 0;
    }
    v9 = IoSetActivityIdThread(v18);
    if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
    {
      LODWORD(MessageResourceEntry) = 8;
      McTemplateK0pq_EtwWriteTransfer(
        v7,
        (const EVENT_DESCRIPTOR *)WORKITEM_START,
        (const GUID *)v18,
        v8,
        (__int64)MessageResourceEntry);
    }
    while ( 1 )
    {
      v10 = v4[6];
      if ( !v10 || NtfsSetCancelRoutine(v10, 0, 0, 0) )
        break;
      _InterlockedIncrement((volatile signed __int32 *)&xmmword_140094D10);
      if ( *((_DWORD *)StartContext + 1390) <= (unsigned int)++v5 )
      {
        KeReleaseSpinLock((PKSPIN_LOCK)StartContext + 692, v2);
        KeWaitForSingleObject(StartContext + 5568, Executive, 0, 0, 0);
        goto LABEL_32;
      }
      v4 = (__int64 *)*v4;
    }
    v13 = (__int64 *)*v4;
    if ( *(__int64 **)(*v4 + 8) != v4 || (v14 = (__int64 **)v4[1], *v14 != v4) )
      __fastfail(3u);
    *v14 = v13;
    v13[1] = (__int64)v14;
    --*((_DWORD *)StartContext + 1390);
    KeReleaseSpinLock((PKSPIN_LOCK)StartContext + 692, v2);
    if ( v5 != -1 )
    {
      NtfsRepairItem(StartContext, v4);
      v15 = *((_DWORD *)v4 + 4);
      if ( (v15 & 1) != 0 )
      {
        KeSetEvent((PRKEVENT)v4 + 1, 0, 0);
      }
      else if ( (v15 & 2) == 0
             || (KeSetEvent((PRKEVENT)v4 + 1, 0, 0),
                 !_InterlockedCompareExchange((volatile signed __int32 *)v4 + 5, 0, 1)) )
      {
        NtfsFreeRepairItem(v4);
      }
      v11 = 0;
      if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1398, 0, 0) )
        KeSetEvent((PRKEVENT)(StartContext + 5600), 0, 0);
    }
LABEL_32:
    if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
    {
      LODWORD(MessageResourceEntry) = 8;
      McTemplateK0pq_EtwWriteTransfer(
        v11,
        (const EVENT_DESCRIPTOR *)WORKITEM_COMPLETE,
        (const GUID *)v18,
        v12,
        (__int64)MessageResourceEntry);
    }
    IoClearActivityIdThread(v9);
  }
  *((_DWORD *)StartContext + 1391) = v3 & 0xFFFFF7FE;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1398, 0, 0) )
    KeSetEvent((PRKEVENT)(StartContext + 5600), 0, 0);
  if ( _InterlockedCompareExchange((volatile signed __int32 *)StartContext + 1406, 0, 0) )
    KeSetEvent((PRKEVENT)(StartContext + 5632), 0, 0);
  *((_QWORD *)StartContext + 691) = 0;
  _InterlockedDecrement((volatile signed __int32 *)StartContext + 65);
  KeReleaseSpinLock((PKSPIN_LOCK)StartContext + 692, v2);
  NtfsRepairEndThreadUpdate();
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14004dc90  mov     [rsp-28h+arg_8], rbx
0x14004dc95  mov     [rsp-28h+arg_10], rsi
0x14004dc9a  push    rbp
0x14004dc9b  push    rdi
0x14004dc9c  push    r12
0x14004dc9e  push    r14
0x14004dca0  push    r15
0x14004dca2  mov     rbp, rsp
0x14004dca5  sub     rsp, 60h
0x14004dca9  mov     rax, cs:__security_cookie
0x14004dcb0  xor     rax, rsp
0x14004dcb3  mov     [rbp+var_10], rax
0x14004dcb7  mov     rbx, rcx
0x14004dcba  call    cs:__imp_KeEnterCriticalRegion
0x14004dcc1  nop     dword ptr [rax+rax+00h]
0x14004dcc6  mov     rax, gs:188h
0x14004dccf  mov     [rbx+1598h], rax
0x14004dcd6  cmp     cs:byte_140095C55, 0
0x14004dcdd  jnz     short loc_14004DD1F
0x14004dcdf  mov     rcx, cs:DriverObject
0x14004dce6  lea     rax, [rbp+var_30]
0x14004dcea  xor     r8d, r8d; Language
0x14004dced  mov     [rbp+var_30], 0
0x14004dcf5  mov     r9d, 61B0h; MessageId
0x14004dcfb  mov     [rsp+60h+MessageResourceEntry], rax; MessageResourceEntry
0x14004dd00  mov     rcx, [rcx+18h]; BaseAddress
0x14004dd04  lea     edx, [r8+0Bh]; Type
0x14004dd08  call    cs:__imp_RtlFindMessage
0x14004dd0f  nop     dword ptr [rax+rax+00h]
0x14004dd14  test    eax, eax
0x14004dd16  js      short loc_14004DD1F
0x14004dd18  mov     cs:byte_140095C55, 1
0x14004dd1f  lea     rcx, NtfsRepairEventCounterMutex; Mutex
0x14004dd26  call    cs:__imp_KeAcquireGuardedMutex
0x14004dd2d  nop     dword ptr [rax+rax+00h]
0x14004dd32  inc     cs:NtfsRepairThreadCount
0x14004dd38  lea     rcx, NtfsRepairEventCounterMutex; Mutex
0x14004dd3f  call    cs:__imp_KeReleaseGuardedMutex
0x14004dd46  nop     dword ptr [rax+rax+00h]
0x14004dd4b  lea     r12, [rbx+15A0h]
0x14004dd52  xorps   xmm0, xmm0
0x14004dd55  xor     eax, eax
0x14004dd57  mov     rcx, r12; SpinLock
0x14004dd5a  mov     [rbp+var_18], rax
0x14004dd5e  movups  [rbp+var_28], xmm0
0x14004dd62  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004dd69  nop     dword ptr [rax+rax+00h]
0x14004dd6e  cmp     dword ptr [rbx+15B8h], 0
0x14004dd75  mov     r15b, al
0x14004dd78  jnz     loc_14004DE55
0x14004dd7e  bts     dword ptr [rbx+15BCh], 0Bh
0x14004dd86  lea     rdi, [rbx+15C0h]
0x14004dd8d  mov     rcx, rdi; Event
0x14004dd90  mov     [rbp+var_30], 0FFFFFFFFDC3CBA00h
0x14004dd98  call    cs:__imp_KeClearEvent
0x14004dd9f  nop     dword ptr [rax+rax+00h]
0x14004dda4  xor     ecx, ecx
0x14004dda6  xor     eax, eax
0x14004dda8  lock cmpxchg [rbx+15D8h], ecx
0x14004ddb0  jz      short loc_14004DDCA
0x14004ddb2  lea     rcx, [rbx+15E0h]; Event
0x14004ddb9  xor     r8d, r8d; Wait
0x14004ddbc  xor     edx, edx; Increment
0x14004ddbe  call    cs:__imp_KeSetEvent
0x14004ddc5  nop     dword ptr [rax+rax+00h]
0x14004ddca  xor     ecx, ecx
0x14004ddcc  xor     eax, eax
0x14004ddce  lock cmpxchg [rbx+15F8h], ecx
0x14004ddd6  jz      short loc_14004DDF0
0x14004ddd8  lea     rcx, [rbx+1600h]; Event
0x14004dddf  xor     r8d, r8d; Wait
0x14004dde2  xor     edx, edx; Increment
0x14004dde4  call    cs:__imp_KeSetEvent
0x14004ddeb  nop     dword ptr [rax+rax+00h]
0x14004ddf0  mov     dl, r15b; NewIrql
0x14004ddf3  mov     rcx, r12; SpinLock
0x14004ddf6  call    cs:__imp_KeReleaseSpinLock
0x14004ddfd  nop     dword ptr [rax+rax+00h]
0x14004de02  lea     rax, [rbp+var_30]
0x14004de06  xor     r9d, r9d; Alertable
0x14004de09  xor     r8d, r8d; WaitMode
0x14004de0c  mov     [rsp+60h+MessageResourceEntry], rax; Timeout
0x14004de11  xor     edx, edx; WaitReason
0x14004de13  mov     rcx, rdi; Object
0x14004de16  call    cs:__imp_KeWaitForSingleObject
0x14004de1d  nop     dword ptr [rax+rax+00h]
0x14004de22  mov     rcx, r12; SpinLock
0x14004de25  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14004de2c  nop     dword ptr [rax+rax+00h]
0x14004de31  mov     r15b, al
0x14004de34  mov     eax, [rbx+15BCh]
0x14004de3a  test    al, 4
0x14004de3c  jnz     short loc_14004DDF0
0x14004de3e  cmp     dword ptr [rbx+15B8h], 0
0x14004de45  jz      loc_14004E01B
0x14004de4b  btr     eax, 0Bh
0x14004de4f  mov     [rbx+15BCh], eax
0x14004de55  mov     rdi, [rbx+15A8h]
0x14004de5c  xor     esi, esi
0x14004de5e  mov     rcx, [rdi+0B0h]
0x14004de65  test    rcx, rcx
0x14004de68  jz      short loc_14004DE83
0x14004de6a  mov     rax, [rcx]
0x14004de6d  mov     qword ptr [rbp+var_28+8], rax
0x14004de71  mov     rax, [rcx+8]
0x14004de75  mov     [rbp+var_18], rax
0x14004de79  lea     rax, [rbp+var_28+8]
0x14004de7d  mov     qword ptr [rbp+var_28], rax
0x14004de81  jmp     short loc_14004DE87
0x14004de83  mov     qword ptr [rbp+var_28], rsi
0x14004de87  mov     rax, qword ptr [rbp+var_28]
0x14004de8b  mov     rcx, qword ptr [rbp+var_28]
0x14004de8f  call    cs:__imp_IoSetActivityIdThread
0x14004de96  nop     dword ptr [rax+rax+00h]
0x14004de9b  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14004dea2  mov     r14, rax
0x14004dea5  jz      short loc_14004DEBF
0x14004dea7  mov     r8, qword ptr [rbp+var_28]
0x14004deab  lea     rdx, WORKITEM_START
0x14004deb2  mov     dword ptr [rsp+60h+MessageResourceEntry], 8
0x14004deba  call    McTemplateK0pq_EtwWriteTransfer
0x14004debf  mov     rcx, [rdi+30h]
0x14004dec3  test    rcx, rcx
0x14004dec6  jz      short loc_14004DF2A
0x14004dec8  xor     r9d, r9d
0x14004decb  xor     r8d, r8d
0x14004dece  xor     edx, edx
0x14004ded0  call    NtfsSetCancelRoutine
0x14004ded5  test    al, al
0x14004ded7  jnz     short loc_14004DF2A
0x14004ded9  lock inc dword ptr cs:xmmword_140094D10
0x14004dee0  inc     esi
0x14004dee2  cmp     [rbx+15B8h], esi
0x14004dee8  jbe     short loc_14004DEEF
0x14004deea  mov     rdi, [rdi]
0x14004deed  jmp     short loc_14004DEBF
0x14004deef  mov     dl, r15b; NewIrql
0x14004def2  mov     rcx, r12; SpinLock
0x14004def5  call    cs:__imp_KeReleaseSpinLock
0x14004defc  nop     dword ptr [rax+rax+00h]
0x14004df01  lea     rcx, [rbx+15C0h]; Object
0x14004df08  mov     [rsp+60h+MessageResourceEntry], 0; Timeout
0x14004df11  xor     r9d, r9d; Alertable
0x14004df14  xor     r8d, r8d; WaitMode
0x14004df17  xor     edx, edx; WaitReason
0x14004df19  call    cs:__imp_KeWaitForSingleObject
0x14004df20  nop     dword ptr [rax+rax+00h]
0x14004df25  jmp     loc_14004DFE6
0x14004df2a  mov     rcx, [rdi]
0x14004df2d  cmp     [rcx+8], rdi
0x14004df31  jnz     loc_14004E0CB
0x14004df37  mov     rax, [rdi+8]
0x14004df3b  cmp     [rax], rdi
0x14004df3e  jnz     loc_14004E0CB
0x14004df44  mov     [rax], rcx
0x14004df47  mov     dl, r15b; NewIrql
0x14004df4a  mov     [rcx+8], rax
0x14004df4e  mov     rcx, r12; SpinLock
0x14004df51  dec     dword ptr [rbx+15B8h]
0x14004df57  call    cs:__imp_KeReleaseSpinLock
0x14004df5e  nop     dword ptr [rax+rax+00h]
0x14004df63  cmp     esi, 0FFFFFFFFh
0x14004df66  jz      short loc_14004DFE6
0x14004df68  mov     rdx, rdi
0x14004df6b  mov     rcx, rbx
0x14004df6e  call    NtfsRepairItem
0x14004df73  mov     eax, [rdi+10h]
0x14004df76  test    al, 1
0x14004df78  jz      short loc_14004DF91
0x14004df7a  lea     rcx, [rdi+18h]; Event
0x14004df7e  xor     r8d, r8d; Wait
0x14004df81  xor     edx, edx; Increment
0x14004df83  call    cs:__imp_KeSetEvent
0x14004df8a  nop     dword ptr [rax+rax+00h]
0x14004df8f  jmp     short loc_14004DFC0
0x14004df91  test    al, 2
0x14004df93  jz      short loc_14004DFB8
0x14004df95  lea     rcx, [rdi+18h]; Event
0x14004df99  xor     r8d, r8d; Wait
0x14004df9c  xor     edx, edx; Increment
0x14004df9e  call    cs:__imp_KeSetEvent
0x14004dfa5  nop     dword ptr [rax+rax+00h]
0x14004dfaa  xor     edx, edx
0x14004dfac  lea     eax, [rdx+1]
0x14004dfaf  lock cmpxchg [rdi+14h], edx
0x14004dfb4  test    eax, eax
0x14004dfb6  jnz     short loc_14004DFC0
0x14004dfb8  mov     rcx, rdi; P
0x14004dfbb  call    NtfsFreeRepairItem
0x14004dfc0  xor     ecx, ecx
0x14004dfc2  xor     eax, eax
0x14004dfc4  lock cmpxchg [rbx+15D8h], ecx
0x14004dfcc  jz      short loc_14004DFE6
0x14004dfce  lea     rcx, [rbx+15E0h]; Event
0x14004dfd5  xor     r8d, r8d; Wait
0x14004dfd8  xor     edx, edx; Increment
0x14004dfda  call    cs:__imp_KeSetEvent
0x14004dfe1  nop     dword ptr [rax+rax+00h]
0x14004dfe6  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x14004dfed  jz      short loc_14004E007
0x14004dfef  mov     r8, qword ptr [rbp+var_28]
0x14004dff3  lea     rdx, WORKITEM_COMPLETE
0x14004dffa  mov     dword ptr [rsp+60h+MessageResourceEntry], 8
0x14004e002  call    McTemplateK0pq_EtwWriteTransfer
0x14004e007  mov     rcx, r14
0x14004e00a  call    cs:__imp_IoClearActivityIdThread
0x14004e011  nop     dword ptr [rax+rax+00h]
0x14004e016  jmp     loc_14004DD52
0x14004e01b  and     eax, 0FFFFF7FEh
0x14004e020  xor     ecx, ecx
0x14004e022  mov     [rbx+15BCh], eax
0x14004e028  xor     eax, eax
0x14004e02a  lock cmpxchg [rbx+15D8h], ecx
0x14004e032  jz      short loc_14004E04C
0x14004e034  lea     rcx, [rbx+15E0h]; Event
0x14004e03b  xor     r8d, r8d; Wait
0x14004e03e  xor     edx, edx; Increment
0x14004e040  call    cs:__imp_KeSetEvent
0x14004e047  nop     dword ptr [rax+rax+00h]
0x14004e04c  xor     edx, edx; Increment
0x14004e04e  xor     eax, eax
0x14004e050  lock cmpxchg [rbx+15F8h], edx
0x14004e058  jz      short loc_14004E070
0x14004e05a  lea     rcx, [rbx+1600h]; Event
0x14004e061  xor     r8d, r8d; Wait
0x14004e064  call    cs:__imp_KeSetEvent
0x14004e06b  nop     dword ptr [rax+rax+00h]
0x14004e070  mov     qword ptr [rbx+1598h], 0
0x14004e07b  mov     dl, r15b; NewIrql
0x14004e07e  lock dec dword ptr [rbx+104h]
0x14004e085  mov     rcx, r12; SpinLock
0x14004e088  call    cs:__imp_KeReleaseSpinLock
0x14004e08f  nop     dword ptr [rax+rax+00h]
0x14004e094  call    NtfsRepairEndThreadUpdate
0x14004e099  call    cs:__imp_KeLeaveCriticalRegion
0x14004e0a0  nop     dword ptr [rax+rax+00h]
0x14004e0a5  mov     rcx, [rbp+var_10]
0x14004e0a9  xor     rcx, rsp; StackCookie
0x14004e0ac  call    __security_check_cookie
0x14004e0b1  lea     r11, [rsp+60h+var_s0]
0x14004e0b6  mov     rbx, [r11+38h]
0x14004e0ba  mov     rsi, [r11+40h]
0x14004e0be  mov     rsp, r11
0x14004e0c1  pop     r15
0x14004e0c3  pop     r14
0x14004e0c5  pop     r12
0x14004e0c7  pop     rdi
0x14004e0c8  pop     rbp
0x14004e0c9  retn
0x14004e0cb  mov     ecx, 3
0x14004e0d0  int     29h; Win8: RtlFailFast(ecx)
```
