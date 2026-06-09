# ndisReceiveWorkerThread

- ea: `0x14004b420`
- end: `0x14004b7c4`
- name: `ndisReceiveWorkerThread`
- size: `932`
- prototype: `__int64 __fastcall(char)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x140028e00`
- `0x14004b420`
- `0x1400e6160`
- `0x1400e6240`
- `0x1401564e0`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14004b4db`
- `ntoskrnl!KfRaiseIrql` at `0x14004b4db`
- `ntoskrnl!KeLowerIrql` at `0x14004b5bc`
- `ntoskrnl!KeLowerIrql` at `0x14004b77f`
- `ntoskrnl!KeLowerIrql` at `0x14004b5bc`
- `ntoskrnl!KeLowerIrql` at `0x14004b77f`
- `ntoskrnl!IoWMIWriteEvent` at `0x14004b645`
- `ntoskrnl!IoWMIWriteEvent` at `0x14004b693`
- `ntoskrnl!IoWMIWriteEvent` at `0x14004b645`
- `ntoskrnl!IoWMIWriteEvent` at `0x14004b693`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14004b467`
- `ntoskrnl!KeGetProcessorNumberFromIndex` at `0x14004b467`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14004b4be`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14004b4be`
- `ntoskrnl!KeSetTimer` at `0x14004b5ed`
- `ntoskrnl!KeSetTimer` at `0x14004b5ed`
- `ntoskrnl!KeReleaseSemaphore` at `0x14004b701`
- `ntoskrnl!KeReleaseSemaphore` at `0x14004b701`
- `ntoskrnl!KeCancelTimer` at `0x14004b550`
- `ntoskrnl!KeCancelTimer` at `0x14004b550`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14004b560`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14004b6e6`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14004b560`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14004b6e6`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14004b4ee`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14004b6ad`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14004b4ee`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14004b6ad`

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
  v3 = (char *)qword_14011B440 + 64 * (unsigned __int64)v1;
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
      *((_DWORD *)qword_14011B438 + v4) = 0;
      KeCancelTimer((PKTIMER)((char *)qword_14011B430 + v8));
    }
    else
    {
      v11 = (char *)qword_14011B430 + v8;
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
    if ( (_BYTE)word_14011CF94 )
    {
      memset(&v18[16], 0, 22);
      *(_DWORD *)&v18[26] = 0x20000;
      v17 = 0;
      WnodeEventItem = 56;
      *(_QWORD *)v18 = 0;
      *(_QWORD *)((char *)&v17 + 6) = qword_14011CF88;
      BYTE2(v17) = 22;
      *(GUID *)&v18[6] = EtwGuidNdisReceive;
      IoWMIWriteEvent(&WnodeEventItem);
    }
    (*((void (__fastcall **)(_QWORD))v6 + 2))(*((_QWORD *)v6 + 3));
    if ( (_BYTE)word_14011CF94 )
    {
      *(_QWORD *)v18 = 0;
      *(_QWORD *)&v18[22] = 0x2000000000000LL;
      WnodeEventItem = 48;
      v17 = 0;
      BYTE2(v17) = 23;
      *(_QWORD *)((char *)&v17 + 6) = qword_14011CF88;
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
0x14004b420  push    rbp
0x14004b422  push    rbx
0x14004b423  push    rsi
0x14004b424  push    rdi
0x14004b425  push    r12
0x14004b427  push    r13
0x14004b429  push    r14
0x14004b42b  push    r15
0x14004b42d  lea     rbp, [rsp-1Fh]
0x14004b432  sub     rsp, 0A8h
0x14004b439  mov     rax, cs:__security_cookie
0x14004b440  xor     rax, rsp
0x14004b443  mov     [rbp+57h+var_48], rax
0x14004b447  xor     r15d, r15d
0x14004b44a  mov     qword ptr [rbp+57h+var_70], rcx
0x14004b44e  xorps   xmm0, xmm0
0x14004b451  mov     dword ptr [rbp+57h+ProcNumber.Group], r15d
0x14004b455  xorps   xmm1, xmm1
0x14004b458  lea     rdx, [rbp+57h+ProcNumber]; ProcNumber
0x14004b45c  movups  xmmword ptr [rbp+57h+Affinity.Mask], xmm0
0x14004b460  mov     rbx, rcx
0x14004b463  movups  xmmword ptr [rbp+57h+PreviousAffinity.Mask], xmm1
0x14004b467  call    cs:__imp_KeGetProcessorNumberFromIndex
0x14004b46e  nop     dword ptr [rax+rax+00h]
0x14004b473  lea     rax, WPP_RECORDER_INITIALIZED
0x14004b47a  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004b481  lea     rcx, WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids
0x14004b488  jnz     loc_14004B74F
0x14004b48e  movzx   ecx, [rbp+57h+ProcNumber.Number]
0x14004b492  lea     rdx, [rbp+57h+PreviousAffinity]; PreviousAffinity
0x14004b496  mov     eax, 1
0x14004b49b  mov     edi, ebx
0x14004b49d  shl     rax, cl
0x14004b4a0  lea     rcx, [rbp+57h+Affinity]; Affinity
0x14004b4a4  mov     [rbp+57h+Affinity.Mask], rax
0x14004b4a8  movzx   eax, [rbp+57h+ProcNumber.Group]
0x14004b4ac  shl     rdi, 6
0x14004b4b0  add     rdi, cs:qword_14011B440
0x14004b4b7  mov     [rbp+57h+Affinity.Group], ax
0x14004b4bb  mov     r12d, ebx
0x14004b4be  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14004b4c5  nop     dword ptr [rax+rax+00h]
0x14004b4ca  nop     word ptr [rax+rax+00h]
0x14004b4d0  lea     rcx, [rdi+20h]; void *
0x14004b4d4  call    ?ndisWaitForKernelObject@@YAXPEAX@Z; ndisWaitForKernelObject(void *)
0x14004b4d9  mov     cl, 2; NewIrql
0x14004b4db  call    cs:__imp_KfRaiseIrql
0x14004b4e2  nop     dword ptr [rax+rax+00h]
0x14004b4e7  lea     rcx, [rdi+10h]; SpinLock
0x14004b4eb  movzx   esi, al
0x14004b4ee  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14004b4f5  nop     dword ptr [rax+rax+00h]
0x14004b4fa  mov     rbx, [rdi]
0x14004b4fd  cmp     rbx, rdi
0x14004b500  jz      loc_14004B6C9
0x14004b506  cmp     [rbx+8], rdi
0x14004b50a  jnz     loc_14004B6C2
0x14004b510  mov     rax, [rbx]
0x14004b513  cmp     [rax+8], rbx
0x14004b517  jnz     loc_14004B6C2
0x14004b51d  mov     [rdi], rax
0x14004b520  mov     [rax+8], rdi
0x14004b524  mov     [rbx+8], r15
0x14004b528  mov     [rbx], r15
0x14004b52b  dec     dword ptr [rdi+18h]
0x14004b52e  mov     rcx, r12
0x14004b531  shl     rcx, 7
0x14004b535  cmp     [rdi], rdi
0x14004b538  jnz     loc_14004B5CD
0x14004b53e  mov     rax, cs:qword_14011B438
0x14004b545  mov     [rax+r12*4], r15d
0x14004b549  add     rcx, cs:qword_14011B430; PKTIMER
0x14004b550  call    cs:__imp_KeCancelTimer
0x14004b557  nop     dword ptr [rax+rax+00h]
0x14004b55c  lea     rcx, [rdi+10h]; SpinLock
0x14004b560  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14004b567  nop     dword ptr [rax+rax+00h]
0x14004b56c  test    rbx, rbx
0x14004b56f  jz      short loc_14004B5AE
0x14004b571  mov     r15, r12
0x14004b574  shl     r15, 5
0x14004b578  add     r15, cs:?ndisPerCpuPoisonPills@@3PEAU_WORK_QUEUE_ITEM@@EA; _WORK_QUEUE_ITEM * ndisPerCpuPoisonPills
0x14004b57f  cmp     rbx, r15
0x14004b582  jz      loc_14004B6A4
0x14004b588  cmp     byte ptr cs:word_14011CF94, 0
0x14004b58f  jnz     short loc_14004B5FE
0x14004b591  mov     rax, [rbx+10h]
0x14004b595  mov     rcx, [rbx+18h]
0x14004b599  call    _guard_dispatch_icall
0x14004b59e  cmp     byte ptr cs:word_14011CF94, 0
0x14004b5a5  jnz     loc_14004B656
0x14004b5ab  xor     r15d, r15d
0x14004b5ae  cmp     sil, 2
0x14004b5b2  jz      loc_14004B4D0
0x14004b5b8  movzx   ecx, sil; NewIrql
0x14004b5bc  call    cs:__imp_KeLowerIrql
0x14004b5c3  nop     dword ptr [rax+rax+00h]
0x14004b5c8  jmp     loc_14004B4D0
0x14004b5cd  add     rcx, cs:qword_14011B430; Timer
0x14004b5d4  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x14004b5db  mov     rax, qword ptr cs:DueTime
0x14004b5e2  test    rax, rax
0x14004b5e5  cmovnz  rdx, rax; DueTime
0x14004b5e9  lea     r8, [rcx+40h]; Dpc
0x14004b5ed  call    cs:__imp_KeSetTimer
0x14004b5f4  nop     dword ptr [rax+rax+00h]
0x14004b5f9  jmp     loc_14004B55C
0x14004b5fe  xorps   xmm0, xmm0
0x14004b601  lea     rcx, [rbp+57h+WnodeEventItem]; WnodeEventItem
0x14004b605  movups  [rbp+57h+var_86], xmm0
0x14004b609  xor     eax, eax
0x14004b60b  mov     dword ptr [rbp+57h+var_86+0Ah], 20000h
0x14004b612  mov     qword ptr [rbp+57h+var_86+0Eh], rax
0x14004b616  mov     eax, 38h ; '8'
0x14004b61b  movups  [rbp+57h+var_A6], xmm0
0x14004b61f  mov     [rbp+57h+WnodeEventItem], ax
0x14004b623  mov     rax, cs:qword_14011CF88
0x14004b62a  movups  [rbp+57h+var_96], xmm0
0x14004b62e  mov     qword ptr [rbp+57h+var_A6+6], rax
0x14004b632  movups  xmm0, xmmword ptr cs:?EtwGuidNdisReceive@@3U_GUID@@A.Data1; _GUID EtwGuidNdisReceive ...
0x14004b639  mov     byte ptr [rbp+57h+var_A6+2], 16h
0x14004b63d  mov     byte ptr [rbp+57h+var_86+0Eh], 0
0x14004b641  movups  [rbp+57h+var_96+6], xmm0
0x14004b645  call    cs:__imp_IoWMIWriteEvent
0x14004b64c  nop     dword ptr [rax+rax+00h]
0x14004b651  jmp     loc_14004B591
0x14004b656  xorps   xmm0, xmm0
0x14004b659  lea     rcx, [rbp+57h+WnodeEventItem]; WnodeEventItem
0x14004b65d  movups  [rbp+57h+var_96], xmm0
0x14004b661  mov     eax, 30h ; '0'
0x14004b666  movups  [rbp+57h+var_96+0Eh], xmm0
0x14004b66a  mov     [rbp+57h+WnodeEventItem], ax
0x14004b66e  mov     rax, cs:qword_14011CF88
0x14004b675  movups  [rbp+57h+var_A6], xmm0
0x14004b679  mov     dword ptr [rbp+57h+var_86+0Ah], 20000h
0x14004b680  movups  xmm0, xmmword ptr cs:?EtwGuidNdisReceive@@3U_GUID@@A.Data1; _GUID EtwGuidNdisReceive ...
0x14004b687  mov     byte ptr [rbp+57h+var_A6+2], 17h
0x14004b68b  mov     qword ptr [rbp+57h+var_A6+6], rax
0x14004b68f  movups  [rbp+57h+var_96+6], xmm0
0x14004b693  call    cs:__imp_IoWMIWriteEvent
0x14004b69a  nop     dword ptr [rax+rax+00h]
0x14004b69f  jmp     loc_14004B5AB
0x14004b6a4  cmp     [rdi], rdi
0x14004b6a7  jz      short loc_14004B718
0x14004b6a9  lea     rcx, [rdi+10h]; SpinLock
0x14004b6ad  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14004b6b4  nop     dword ptr [rax+rax+00h]
0x14004b6b9  mov     rax, [rdi+8]
0x14004b6bd  cmp     [rax], rdi
0x14004b6c0  jz      short loc_14004B6D1
0x14004b6c2  mov     ecx, 3
0x14004b6c7  int     29h; Win8: RtlFailFast(ecx)
0x14004b6c9  mov     rbx, r15
0x14004b6cc  jmp     loc_14004B52E
0x14004b6d1  mov     [r15], rdi
0x14004b6d4  lea     rcx, [rdi+10h]; SpinLock
0x14004b6d8  mov     [r15+8], rax
0x14004b6dc  mov     [rax], r15
0x14004b6df  mov     [rdi+8], r15
0x14004b6e3  inc     dword ptr [rdi+18h]
0x14004b6e6  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14004b6ed  nop     dword ptr [rax+rax+00h]
0x14004b6f2  xor     r9d, r9d; Wait
0x14004b6f5  lea     rcx, [rdi+20h]; Semaphore
0x14004b6f9  xor     edx, edx; Increment
0x14004b6fb  mov     r8d, 1; Adjustment
0x14004b701  call    cs:__imp_KeReleaseSemaphore
0x14004b708  nop     dword ptr [rax+rax+00h]
0x14004b70d  mov     r15d, 0
0x14004b713  jmp     loc_14004B5AE
0x14004b718  cmp     sil, 2
0x14004b71c  jnz     short loc_14004B77B
0x14004b71e  lea     rax, WPP_RECORDER_INITIALIZED
0x14004b725  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14004b72c  jnz     short loc_14004B78D
0x14004b72e  mov     rcx, [rbp+57h+var_48]
0x14004b732  xor     rcx, rsp; StackCookie
0x14004b735  call    __security_check_cookie
0x14004b73a  add     rsp, 0A8h
0x14004b741  pop     r15
0x14004b743  pop     r14
0x14004b745  pop     r13
0x14004b747  pop     r12
0x14004b749  pop     rdi
0x14004b74a  pop     rsi
0x14004b74b  pop     rbx
0x14004b74c  pop     rbp
0x14004b74d  retn
0x14004b74f  mov     dword ptr [rsp+0E0h+var_B8], ebx; char
0x14004b753  mov     r9d, 10h; int
0x14004b759  mov     [rsp+0E0h+var_C0], rcx; struct _GUID *
0x14004b75e  mov     r8d, 0Ch; int
0x14004b764  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b76b  mov     dl, 4; int
0x14004b76d  mov     rcx, [rcx+40h]; int
0x14004b771  call    WPP_RECORDER_SF_d
0x14004b776  jmp     loc_14004B48E
0x14004b77b  movzx   ecx, sil; NewIrql
0x14004b77f  call    cs:__imp_KeLowerIrql
0x14004b786  nop     dword ptr [rax+rax+00h]
0x14004b78b  jmp     short loc_14004B71E
0x14004b78d  mov     rcx, cs:WPP_GLOBAL_Control
0x14004b794  mov     r9d, 11h; int
0x14004b79a  mov     rax, qword ptr [rbp+57h+var_70]
0x14004b79e  mov     r8d, 0Ch; int
0x14004b7a4  mov     dword ptr [rsp+0E0h+var_B8], eax; char
0x14004b7a8  mov     dl, 4; int
0x14004b7aa  lea     rax, WPP_2fb632d9e69632cc5880b19a4ac60799_Traceguids
0x14004b7b1  mov     rcx, [rcx+40h]; int
0x14004b7b5  mov     [rsp+0E0h+var_C0], rax; struct _GUID *
0x14004b7ba  call    WPP_RECORDER_SF_d
0x14004b7bf  jmp     loc_14004B72E
```
