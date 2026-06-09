# ndisReceiveWorkerThread

- ea: `0x14004fe80`
- end: `0x140050224`
- name: `ndisReceiveWorkerThread`
- size: `932`
- prototype: `__int64 __fastcall(char)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14001cf60`
- `0x14004fe80`
- `0x1400eb380`
- `0x1400eb460`
- `0x14015d480`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14005001c`
- `ntoskrnl!KeLowerIrql` at `0x1400501df`
- `ntoskrnl!KeLowerIrql` at `0x14005001c`
- `ntoskrnl!KeLowerIrql` at `0x1400501df`
- `ntoskrnl!IoWMIWriteEvent` at `0x1400500a5`
- `ntoskrnl!IoWMIWriteEvent` at `0x1400500f3`
- `ntoskrnl!IoWMIWriteEvent` at `0x1400500a5`
- `ntoskrnl!IoWMIWriteEvent` at `0x1400500f3`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14004fec7`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14004fec7`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14004ff1e`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14004ff1e`
- `ntoskrnl!KfRaiseIrql` at `0x14004ff3b`
- `ntoskrnl!KfRaiseIrql` at `0x14004ff3b`
- `ntoskrnl!KeSetTimer` at `0x14005004d`
- `ntoskrnl!KeSetTimer` at `0x14005004d`
- `ntoskrnl!KeReleaseSemaphore` at `0x140050161`
- `ntoskrnl!KeReleaseSemaphore` at `0x140050161`
- `ntoskrnl!KeCancelTimer` at `0x14004ffb0`
- `ntoskrnl!KeCancelTimer` at `0x14004ffb0`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14004ff4e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005010d`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14004ff4e`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14005010d`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14004ffc0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140050146`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14004ffc0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140050146`

## pseudocode

```c
enum Ndis::ReadBindingsOptions::Flags *__fastcall ndisReceiveWorkerThread(__int64 a1)
{
  unsigned int v1; // ebx
  int v2; // edx
  char *v3; // rdi
  __int64 v4; // r12
  KIRQL v5; // si
  char *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rcx
  int v9; // edx
  char *v10; // r15
  char *v11; // rcx
  LARGE_INTEGER v12; // rdx
  char **v13; // rax
  enum Ndis::ReadBindingsOptions::Flags *result; // rax
  struct _PROCESSOR_NUMBER ProcNumber; // [rsp+30h] [rbp-59h] BYREF
  __int16 WnodeEventItem; // [rsp+38h] [rbp-51h] BYREF
  __int128 v17; // [rsp+3Ah] [rbp-4Fh]
  _BYTE v18[38]; // [rsp+4Ah] [rbp-3Fh] BYREF
  char v19[8]; // [rsp+70h] [rbp-19h]
  struct _GROUP_AFFINITY Affinity; // [rsp+78h] [rbp-11h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+88h] [rbp-1h] BYREF

  *(_QWORD *)v19 = a1;
  ProcNumber = 0;
  Affinity = 0;
  v1 = a1;
  PreviousAffinity = 0;
  KeGetProcessorNumberFromIndex(a1, &ProcNumber);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v2) = 4;
    WPP_RECORDER_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v2,
      12,
      16,
      (struct _GUID *)&WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids,
      v1);
  }
  Affinity.Mask = 1LL << ProcNumber.Number;
  v3 = (char *)qword_140121440 + 64 * (unsigned __int64)v1;
  Affinity.Group = ProcNumber.Group;
  v4 = v1;
  KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
  while ( 1 )
  {
    ndisWaitForKernelObject(v3 + 32);
    v5 = KfRaiseIrql(2u);
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v3 + 2);
    v6 = *(char **)v3;
    if ( *(char **)v3 == v3 )
    {
      v6 = 0;
    }
    else
    {
      if ( *((char **)v6 + 1) != v3 || (v7 = *(_QWORD *)v6, *(char **)(*(_QWORD *)v6 + 8LL) != v6) )
LABEL_23:
        __fastfail(3u);
      *(_QWORD *)v3 = v7;
      *(_QWORD *)(v7 + 8) = v3;
      *((_QWORD *)v6 + 1) = 0;
      *(_QWORD *)v6 = 0;
      --*((_DWORD *)v3 + 6);
    }
    v8 = v4 << 7;
    if ( *(char **)v3 == v3 )
    {
      *((_DWORD *)qword_140121438 + v4) = 0;
      KeCancelTimer((PKTIMER)((char *)qword_140121430 + v8));
    }
    else
    {
      v11 = (char *)qword_140121430 + v8;
      v12.QuadPart = -1;
      if ( DueTime.QuadPart )
        v12 = DueTime;
      KeSetTimer((PKTIMER)v11, v12, (PKDPC)v11 + 1);
    }
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v3 + 2);
    if ( v6 )
      break;
LABEL_16:
    if ( v5 != 2 )
      KeLowerIrql(v5);
  }
  v10 = (char *)ndisPerCpuPoisonPills + 32 * v4;
  if ( v6 != v10 )
  {
    if ( (_BYTE)word_140122F94 )
    {
      memset(&v18[16], 0, 22);
      *(_DWORD *)&v18[26] = 0x20000;
      v17 = 0;
      WnodeEventItem = 56;
      *(_QWORD *)v18 = 0;
      *(_QWORD *)((char *)&v17 + 6) = qword_140122F88;
      BYTE2(v17) = 22;
      *(GUID *)&v18[6] = EtwGuidNdisReceive;
      IoWMIWriteEvent(&WnodeEventItem);
    }
    (*((void (__fastcall **)(_QWORD))v6 + 2))(*((_QWORD *)v6 + 3));
    if ( (_BYTE)word_140122F94 )
    {
      *(_QWORD *)v18 = 0;
      *(_QWORD *)&v18[22] = 0x2000000000000LL;
      WnodeEventItem = 48;
      v17 = 0;
      BYTE2(v17) = 23;
      *(_QWORD *)((char *)&v17 + 6) = qword_140122F88;
      *(GUID *)&v18[6] = EtwGuidNdisReceive;
      IoWMIWriteEvent(&WnodeEventItem);
    }
    goto LABEL_16;
  }
  if ( *(char **)v3 != v3 )
  {
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)v3 + 2);
    v13 = (char **)*((_QWORD *)v3 + 1);
    if ( *v13 != v3 )
      goto LABEL_23;
    *(_QWORD *)v10 = v3;
    *((_QWORD *)v10 + 1) = v13;
    *v13 = v10;
    *((_QWORD *)v3 + 1) = v10;
    ++*((_DWORD *)v3 + 6);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)v3 + 2);
    KeReleaseSemaphore((PRKSEMAPHORE)v3 + 1, 0, 1, 0);
    goto LABEL_16;
  }
  if ( v5 != 2 )
    KeLowerIrql(v5);
  result = &WPP_RECORDER_INITIALIZED;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v9) = 4;
    return (enum Ndis::ReadBindingsOptions::Flags *)WPP_RECORDER_SF_d(
                                                      *((_QWORD *)WPP_GLOBAL_Control + 8),
                                                      v9,
                                                      12,
                                                      17,
                                                      (struct _GUID *)&WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids,
                                                      v19[0]);
  }
  return result;
}

```

## disassembly

```asm
0x14004fe80  push    rbp
0x14004fe82  push    rbx
0x14004fe83  push    rsi
0x14004fe84  push    rdi
0x14004fe85  push    r12
0x14004fe87  push    r13
0x14004fe89  push    r14
0x14004fe8b  push    r15
0x14004fe8d  lea     rbp, [rsp-1Fh]
0x14004fe92  sub     rsp, 0A8h
0x14004fe99  mov     rax, cs:__security_cookie
0x14004fea0  xor     rax, rsp
0x14004fea3  mov     [rbp+57h+var_48], rax
0x14004fea7  xor     r15d, r15d
0x14004feaa  mov     qword ptr [rbp+57h+var_70], rcx
0x14004feae  xorps   xmm0, xmm0
0x14004feb1  mov     dword ptr [rbp+57h+ProcNumber.Group], r15d
0x14004feb5  xorps   xmm1, xmm1
0x14004feb8  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x14004febc  movups  xmmword ptr [rbp+57h+Affinity.Mask], xmm0
0x14004fec0  mov     rbx, rcx
0x14004fec3  movups  xmmword ptr [rbp+57h+PreviousAffinity.Mask], xmm1
0x14004fec7  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14004fece  nop     dword ptr [rax+rax+00h]
0x14004fed3  lea     rax, WPP_RECORDER_INITIALIZED
0x14004feda  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004fee1  lea     rcx, WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids
0x14004fee8  jnz     loc_1400501AF
0x14004feee  movzx   ecx, [rbp+57h+ProcNumber.Number]
0x14004fef2  lea     rdx, [rbp+57h+PreviousAffinity]; PreviousAffinity
0x14004fef6  mov     eax, 1
0x14004fefb  mov     edi, ebx
0x14004fefd  shl     rax, cl
0x14004ff00  lea     rcx, [rbp+57h+Affinity]; Affinity
0x14004ff04  mov     [rbp+57h+Affinity.Mask], rax
0x14004ff08  movzx   eax, [rbp+57h+ProcNumber.Group]
0x14004ff0c  shl     rdi, 6
0x14004ff10  add     rdi, cs:qword_140121440
0x14004ff17  mov     [rbp+57h+Affinity.Group], ax
0x14004ff1b  mov     r12d, ebx
0x14004ff1e  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14004ff25  nop     dword ptr [rax+rax+00h]
0x14004ff2a  nop     word ptr [rax+rax+00h]
0x14004ff30  lea     rcx, [rdi+20h]; void *
0x14004ff34  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x14004ff39  mov     cl, 2; NewIrql
0x14004ff3b  call    cs:__imp_KfRaiseIrql
0x14004ff42  nop     dword ptr [rax+rax+00h]
0x14004ff47  lea     rcx, [rdi+10h]; SpinLock
0x14004ff4b  movzx   esi, al
0x14004ff4e  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14004ff55  nop     dword ptr [rax+rax+00h]
0x14004ff5a  mov     rbx, [rdi]
0x14004ff5d  cmp     rbx, rdi
0x14004ff60  jz      loc_140050129
0x14004ff66  cmp     [rbx+8], rdi
0x14004ff6a  jnz     loc_140050122
0x14004ff70  mov     rax, [rbx]
0x14004ff73  cmp     [rax+8], rbx
0x14004ff77  jnz     loc_140050122
0x14004ff7d  mov     [rdi], rax
0x14004ff80  mov     [rax+8], rdi
0x14004ff84  mov     [rbx+8], r15
0x14004ff88  mov     [rbx], r15
0x14004ff8b  dec     dword ptr [rdi+18h]
0x14004ff8e  mov     rcx, r12
0x14004ff91  shl     rcx, 7
0x14004ff95  cmp     [rdi], rdi
0x14004ff98  jnz     loc_14005002D
0x14004ff9e  mov     rax, cs:qword_140121438
0x14004ffa5  mov     [rax+r12*4], r15d
0x14004ffa9  add     rcx, cs:qword_140121430; PKTIMER
0x14004ffb0  call    cs:__imp_KeCancelTimer
0x14004ffb7  nop     dword ptr [rax+rax+00h]
0x14004ffbc  lea     rcx, [rdi+10h]; SpinLock
0x14004ffc0  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14004ffc7  nop     dword ptr [rax+rax+00h]
0x14004ffcc  test    rbx, rbx
0x14004ffcf  jz      short loc_14005000E
0x14004ffd1  mov     r15, r12
0x14004ffd4  shl     r15, 5
0x14004ffd8  add     r15, cs:?ndisPerCpuPoisonPills@@3PEAU_WORK_QUEUE_ITEM@@EA; _WORK_QUEUE_ITEM * ndisPerCpuPoisonPills
0x14004ffdf  cmp     rbx, r15
0x14004ffe2  jz      loc_140050104
0x14004ffe8  cmp     byte ptr cs:word_140122F94, 0
0x14004ffef  jnz     short loc_14005005E
0x14004fff1  mov     rax, [rbx+10h]
0x14004fff5  mov     rcx, [rbx+18h]
0x14004fff9  call    _guard_dispatch_icall
0x14004fffe  cmp     byte ptr cs:word_140122F94, 0
0x140050005  jnz     loc_1400500B6
0x14005000b  xor     r15d, r15d
0x14005000e  cmp     sil, 2
0x140050012  jz      loc_14004FF30
0x140050018  movzx   ecx, sil; NewIrql
0x14005001c  call    cs:__imp_KeLowerIrql
0x140050023  nop     dword ptr [rax+rax+00h]
0x140050028  jmp     loc_14004FF30
0x14005002d  add     rcx, cs:qword_140121430; Timer
0x140050034  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14005003b  mov     rax, qword ptr cs:DueTime
0x140050042  test    rax, rax
0x140050045  cmovnz  rdx, rax; DueTime
0x140050049  lea     r8, [rcx+40h]; Dpc
0x14005004d  call    cs:__imp_KeSetTimer
0x140050054  nop     dword ptr [rax+rax+00h]
0x140050059  jmp     loc_14004FFBC
0x14005005e  xorps   xmm0, xmm0
0x140050061  lea     rcx, [rbp+57h+WnodeEventItem]; WnodeEventItem
0x140050065  movups  [rbp+57h+var_86], xmm0
0x140050069  xor     eax, eax
0x14005006b  mov     dword ptr [rbp+57h+var_86+0Ah], 20000h
0x140050072  mov     qword ptr [rbp+57h+var_86+0Eh], rax
0x140050076  mov     eax, 38h ; '8'
0x14005007b  movups  [rbp+57h+var_A6], xmm0
0x14005007f  mov     [rbp+57h+WnodeEventItem], ax
0x140050083  mov     rax, cs:qword_140122F88
0x14005008a  movups  [rbp+57h+var_96], xmm0
0x14005008e  mov     qword ptr [rbp+57h+var_A6+6], rax
0x140050092  movups  xmm0, xmmword ptr cs:?EtwGuidNdisReceive@@3U_GUID@@A.Data1; _GUID EtwGuidNdisReceive ...
0x140050099  mov     byte ptr [rbp+57h+var_A6+2], 16h
0x14005009d  mov     byte ptr [rbp+57h+var_86+0Eh], 0
0x1400500a1  movups  [rbp+57h+var_96+6], xmm0
0x1400500a5  call    cs:__imp_IoWMIWriteEvent
0x1400500ac  nop     dword ptr [rax+rax+00h]
0x1400500b1  jmp     loc_14004FFF1
0x1400500b6  xorps   xmm0, xmm0
0x1400500b9  lea     rcx, [rbp+57h+WnodeEventItem]; WnodeEventItem
0x1400500bd  movups  [rbp+57h+var_96], xmm0
0x1400500c1  mov     eax, 30h ; '0'
0x1400500c6  movups  [rbp+57h+var_96+0Eh], xmm0
0x1400500ca  mov     [rbp+57h+WnodeEventItem], ax
0x1400500ce  mov     rax, cs:qword_140122F88
0x1400500d5  movups  [rbp+57h+var_A6], xmm0
0x1400500d9  mov     dword ptr [rbp+57h+var_86+0Ah], 20000h
0x1400500e0  movups  xmm0, xmmword ptr cs:?EtwGuidNdisReceive@@3U_GUID@@A.Data1; _GUID EtwGuidNdisReceive ...
0x1400500e7  mov     byte ptr [rbp+57h+var_A6+2], 17h
0x1400500eb  mov     qword ptr [rbp+57h+var_A6+6], rax
0x1400500ef  movups  [rbp+57h+var_96+6], xmm0
0x1400500f3  call    cs:__imp_IoWMIWriteEvent
0x1400500fa  nop     dword ptr [rax+rax+00h]
0x1400500ff  jmp     loc_14005000B
0x140050104  cmp     [rdi], rdi
0x140050107  jz      short loc_140050178
0x140050109  lea     rcx, [rdi+10h]; SpinLock
0x14005010d  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140050114  nop     dword ptr [rax+rax+00h]
0x140050119  mov     rax, [rdi+8]
0x14005011d  cmp     [rax], rdi
0x140050120  jz      short loc_140050131
0x140050122  mov     ecx, 3
0x140050127  int     29h; Win8: RtlFailFast(ecx)
0x140050129  mov     rbx, r15
0x14005012c  jmp     loc_14004FF8E
0x140050131  mov     [r15], rdi
0x140050134  lea     rcx, [rdi+10h]; SpinLock
0x140050138  mov     [r15+8], rax
0x14005013c  mov     [rax], r15
0x14005013f  mov     [rdi+8], r15
0x140050143  inc     dword ptr [rdi+18h]
0x140050146  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14005014d  nop     dword ptr [rax+rax+00h]
0x140050152  xor     r9d, r9d; Wait
0x140050155  lea     rcx, [rdi+20h]; Semaphore
0x140050159  xor     edx, edx; Increment
0x14005015b  mov     r8d, 1; Adjustment
0x140050161  call    cs:__imp_KeReleaseSemaphore
0x140050168  nop     dword ptr [rax+rax+00h]
0x14005016d  mov     r15d, 0
0x140050173  jmp     loc_14005000E
0x140050178  cmp     sil, 2
0x14005017c  jnz     short loc_1400501DB
0x14005017e  lea     rax, WPP_RECORDER_INITIALIZED
0x140050185  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14005018c  jnz     short loc_1400501ED
0x14005018e  mov     rcx, [rbp+57h+var_48]
0x140050192  xor     rcx, rsp; StackCookie
0x140050195  call    __security_check_cookie
0x14005019a  add     rsp, 0A8h
0x1400501a1  pop     r15
0x1400501a3  pop     r14
0x1400501a5  pop     r13
0x1400501a7  pop     r12
0x1400501a9  pop     rdi
0x1400501aa  pop     rsi
0x1400501ab  pop     rbx
0x1400501ac  pop     rbp
0x1400501ad  retn
0x1400501af  mov     dword ptr [rsp+0E0h+var_B8], ebx; char
0x1400501b3  mov     r9d, 10h; int
0x1400501b9  mov     [rsp+0E0h+var_C0], rcx; struct _GUID *
0x1400501be  mov     r8d, 0Ch; int
0x1400501c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400501cb  mov     dl, 4; int
0x1400501cd  mov     rcx, [rcx+40h]; int
0x1400501d1  call    WPP_RECORDER_SF_d
0x1400501d6  jmp     loc_14004FEEE
0x1400501db  movzx   ecx, sil; NewIrql
0x1400501df  call    cs:__imp_KeLowerIrql
0x1400501e6  nop     dword ptr [rax+rax+00h]
0x1400501eb  jmp     short loc_14005017E
0x1400501ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1400501f4  mov     r9d, 11h; int
0x1400501fa  mov     rax, qword ptr [rbp+57h+var_70]
0x1400501fe  mov     r8d, 0Ch; int
0x140050204  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x140050208  mov     dl, 4; int
0x14005020a  lea     rax, WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids
0x140050211  mov     rcx, [rcx+40h]; int
0x140050215  mov     [rsp+0E0h+var_C0], rax; struct _GUID *
0x14005021a  call    WPP_RECORDER_SF_d
0x14005021f  jmp     loc_14005018E
```
