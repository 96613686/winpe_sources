# VmbusTlSetupPartition

- ea: `0x140020124`
- end: `0x140020525`
- name: `VmbusTlSetupPartition`
- size: `1025`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, _OWORD *, __int64, _OWORD *, __int64 *)`
- caller_count: `3`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140019960`
- `0x140023280`
- `0x140023af0`

## callees

- `0x140006904`
- `0x140009df0`
- `0x140009fa4`
- `0x14000a048`
- `0x14000b088`
- `0x14000b86c`
- `0x14000bfe0`
- `0x14000c0a0`
- `0x14000c4c0`
- `0x14001d304`
- `0x14001d568`
- `0x14001df1c`
- `0x14001edd0`
- `0x140020124`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400202ee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020420`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002044e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400202ee`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140020420`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14002044e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400202e2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140020414`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140020442`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400202e2`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140020414`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140020442`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400204f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400204f7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002019b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020240`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14002019b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140020240`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400204e1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400204e1`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400201b3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140020253`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400201b3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140020253`
- `NETIO!NetioInitializeWorkQueue` at `0x1400202aa`
- `NETIO!NetioInitializeWorkQueue` at `0x1400202aa`

## pseudocode

```c
__int64 __fastcall VmbusTlSetupPartition(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _OWORD *a4,
        __int64 a5,
        _OWORD *a6,
        __int64 *a7)
{
  char v10; // r14
  int UninitializedPartition; // eax
  int v12; // edi
  __int64 v13; // rbx
  __int64 v14; // r8
  int v15; // edx
  struct _FAST_MUTEX *v16; // rdi
  __int64 v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // rdx
  _QWORD *v21; // r8
  __int64 v22; // rdx
  __int64 v23; // r8
  __int64 v24; // r9
  signed __int64 v25; // rax
  bool v26; // cc
  signed __int64 v27; // rax
  void (__fastcall *v28)(__int64); // rax

  if ( (unsigned int)dword_140013058 > 4 )
    HvsocketTraceMessage((const int *)"VmbusTlSetupPartition", (__int64)a4, a3, (__int64)a4);
  v10 = a6 && memcmp(a4, &HV_GUID_CHILDREN, 0x10u);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  if ( !HvSocketPartitionExists(a1, (__int64)a4) )
  {
    UninitializedPartition = HvSocketCreateUninitializedPartition(a1, a4, v10);
    v12 = UninitializedPartition;
    if ( UninitializedPartition < 0 )
    {
      v13 = 0;
      if ( (unsigned int)dword_140013058 <= 2 )
        goto LABEL_34;
      v14 = (unsigned int)UninitializedPartition;
      v15 = 249;
      goto LABEL_11;
    }
  }
  v13 = HvSocketFindAndReferenceUninitializedPartition(a1, a4);
  if ( v13 )
  {
    KeEnterCriticalRegion();
    v16 = (struct _FAST_MUTEX *)(v13 + 16);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v13 + 16));
    *(_QWORD *)(v13 + 208) = a5;
    *(_QWORD *)(v13 + 96) = a2;
    *(_QWORD *)(v13 + 416) = a3;
    memset((void *)(v13 + 104), 0, 0x60u);
    if ( *(_QWORD *)(a1 + 176) )
    {
      v12 = NetioInitializeWorkQueue(v13 + 424, VmbusTlConnectRequestWorkQueueRoutine, 0);
      if ( v12 < 0 )
      {
        if ( (unsigned int)dword_140013058 > 2 )
          HvsocketTraceGuidError((const int *)"VmbusTlSetupPartition", 281, (unsigned int)v12, (__int64)a4);
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v13 + 16));
        KeLeaveCriticalRegion();
        goto LABEL_34;
      }
      *(_BYTE *)(v13 + 472) = 1;
      v16 = (struct _FAST_MUTEX *)(v13 + 16);
    }
    if ( v10 )
    {
      v17 = *(_QWORD *)(v13 + 200);
      *(_BYTE *)(v13 + 248) = 1;
      *(_OWORD *)(v13 + 480) = *a6;
      *(_OWORD *)(v13 + 496) = a6[1];
      if ( v17 && *(_BYTE *)(v17 + 121) )
      {
        *(_OWORD *)(v13 + 104) = *(_OWORD *)HvsocketXboxInterfacePrototype;
        *(_OWORD *)(v13 + 120) = *(_OWORD *)off_14000E190;
        *(_OWORD *)(v13 + 136) = *(_OWORD *)&off_14000E1A0;
        *(_OWORD *)(v13 + 152) = *(_OWORD *)&off_14000E1B0;
        *(_OWORD *)(v13 + 168) = *(_OWORD *)&off_14000E1C0;
        *(_OWORD *)(v13 + 184) = xmmword_14000E1D0;
      }
      else
      {
        if ( !a5 && !a3 )
          MicrosoftTelemetryAssertTriggeredNoArgsKM();
        VmbusTlXPartSetupPartitionTransport(v13);
      }
    }
    else
    {
      *(_BYTE *)(v13 + 248) = 0;
      VmbusTlLoopbackSetupPartitionTransport(v13);
    }
    v18 = (_QWORD *)(v13 + 216);
    v19 = *(_QWORD *)(v13 + 216);
    if ( *(_QWORD *)(v19 + 8) != v13 + 216
      || (v20 = *(_QWORD **)(v13 + 224), (_QWORD *)*v20 != v18)
      || (*v20 = v19,
          *(_QWORD *)(v19 + 8) = v20,
          *(_QWORD *)(v13 + 224) = v13 + 216,
          *v18 = v18,
          v21 = *(_QWORD **)(a1 + 136),
          *v21 != a1 + 128) )
    {
      __fastfail(3u);
    }
    *v18 = a1 + 128;
    *(_QWORD *)(v13 + 224) = v21;
    *v21 = v18;
    *(_QWORD *)(a1 + 136) = v18;
    ++*(_DWORD *)(a1 + 160);
    ExReleaseFastMutexUnsafe(v16);
    KeLeaveCriticalRegion();
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 1160));
    v12 = 0;
    *a7 = v13;
  }
  else
  {
    v12 = -1073741302;
    if ( (unsigned int)dword_140013058 > 2 )
    {
      v14 = 3221225994LL;
      v15 = 258;
LABEL_11:
      HvsocketTraceGuidError((const int *)"VmbusTlSetupPartition", v15, v14, (__int64)a4);
    }
  }
LABEL_34:
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 + 16));
  KeLeaveCriticalRegion();
  if ( v13 )
  {
    if ( v12 < 0 )
      VmbusTlCleanupPartition((char *)v13, v22, v23, v24);
    if ( (unsigned int)dword_140013058 > 5 )
      HvsocketTraceReferenceCount(
        (const int *)"VmbusTlSetupPartition",
        334,
        v13,
        *(_QWORD *)(v13 + 8),
        (const int *)"Dereference object");
    v25 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v13 + 8), 0xFFFFFFFFFFFFFFFFuLL);
    v26 = v25 <= 1;
    v27 = v25 - 1;
    if ( v26 )
    {
      if ( v27 )
        __fastfail(0xEu);
      v28 = *(void (__fastcall **)(__int64))(v13 + 80);
      if ( v28 )
        v28(v13);
      if ( *(_DWORD *)(v13 + 88) == 1 )
      {
        ExFreePoolWithTag((PVOID)v13, 0x69706E56u);
      }
      else if ( *(_DWORD *)(v13 + 88) == 2 )
      {
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)(v13 + 96), (PVOID)v13);
      }
    }
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140020124  mov     [rsp+arg_8], rbx
0x140020129  push    rbp
0x14002012a  push    rsi
0x14002012b  push    rdi
0x14002012c  push    r12
0x14002012e  push    r13
0x140020130  push    r14
0x140020132  push    r15
0x140020134  sub     rsp, 50h
0x140020138  mov     rax, [rsp+88h+arg_30]
0x140020140  mov     rsi, r9
0x140020143  mov     [rsp+88h+var_48], rax
0x140020148  mov     r12, r8
0x14002014b  mov     eax, cs:dword_140013058
0x140020151  mov     rbp, rcx
0x140020154  mov     [rsp+88h+var_58], rdx
0x140020159  cmp     eax, 4
0x14002015c  jbe     short loc_14002016D
0x14002015e  mov     rdx, r9
0x140020161  lea     rcx, aVmbustlsetuppa; "VmbusTlSetupPartition"
0x140020168  call    HvsocketTraceMessage
0x14002016d  mov     r15, [rsp+88h+arg_28]
0x140020175  test    r15, r15
0x140020178  jz      short loc_140020198
0x14002017a  mov     r8d, 10h; Size
0x140020180  lea     rdx, HV_GUID_CHILDREN; Buf2
0x140020187  mov     rcx, rsi; Buf1
0x14002018a  call    memcmp
0x14002018f  test    eax, eax
0x140020191  jz      short loc_140020198
0x140020193  mov     r14b, 1
0x140020196  jmp     short loc_14002019B
0x140020198  xor     r14b, r14b
0x14002019b  call    cs:__imp_KeEnterCriticalRegion
0x1400201a2  nop     dword ptr [rax+rax+00h]
0x1400201a7  lea     rax, [rbp+10h]
0x1400201ab  mov     rcx, rax; FastMutex
0x1400201ae  mov     [rsp+88h+FastMutex], rax
0x1400201b3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400201ba  nop     dword ptr [rax+rax+00h]
0x1400201bf  mov     rdx, rsi
0x1400201c2  mov     rcx, rbp
0x1400201c5  call    HvSocketPartitionExists
0x1400201ca  test    al, al
0x1400201cc  jnz     short loc_14002020F
0x1400201ce  mov     r8b, r14b
0x1400201d1  mov     rdx, rsi
0x1400201d4  mov     rcx, rbp
0x1400201d7  call    HvSocketCreateUninitializedPartition
0x1400201dc  mov     edi, eax
0x1400201de  test    eax, eax
0x1400201e0  jns     short loc_14002020F
0x1400201e2  mov     ecx, cs:dword_140013058
0x1400201e8  xor     ebx, ebx
0x1400201ea  cmp     ecx, 2
0x1400201ed  jbe     loc_14002043D
0x1400201f3  mov     r8d, eax
0x1400201f6  mov     edx, 0F9h
0x1400201fb  mov     r9, rsi
0x1400201fe  lea     rcx, aVmbustlsetuppa; "VmbusTlSetupPartition"
0x140020205  call    HvsocketTraceGuidError
0x14002020a  jmp     loc_14002043D
0x14002020f  mov     rdx, rsi
0x140020212  mov     rcx, rbp
0x140020215  call    HvSocketFindAndReferenceUninitializedPartition
0x14002021a  mov     rbx, rax
0x14002021d  test    rax, rax
0x140020220  jnz     short loc_140020240
0x140020222  mov     ecx, cs:dword_140013058
0x140020228  mov     edi, 0C000020Ah
0x14002022d  cmp     ecx, 2
0x140020230  jbe     loc_14002043D
0x140020236  mov     r8d, edi
0x140020239  mov     edx, 102h
0x14002023e  jmp     short loc_1400201FB
0x140020240  call    cs:__imp_KeEnterCriticalRegion
0x140020247  nop     dword ptr [rax+rax+00h]
0x14002024c  lea     rdi, [rbx+10h]
0x140020250  mov     rcx, rdi; FastMutex
0x140020253  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14002025a  nop     dword ptr [rax+rax+00h]
0x14002025f  mov     rax, [rsp+88h+var_58]
0x140020264  lea     rcx, [rbx+68h]; void *
0x140020268  mov     r13, [rsp+88h+arg_20]
0x140020270  xor     edx, edx; Val
0x140020272  mov     [rbx+0D0h], r13
0x140020279  mov     [rbx+60h], rax
0x14002027d  mov     [rbx+1A0h], r12
0x140020284  lea     r8d, [rdx+60h]; Size
0x140020288  call    memset
0x14002028d  mov     r9, [rbp+0B0h]
0x140020294  test    r9, r9
0x140020297  jz      short loc_14002030A
0x140020299  lea     rcx, [rbx+1A8h]
0x1400202a0  xor     r8d, r8d
0x1400202a3  lea     rdx, VmbusTlConnectRequestWorkQueueRoutine
0x1400202aa  call    cs:__imp_NetioInitializeWorkQueue
0x1400202b1  nop     dword ptr [rax+rax+00h]
0x1400202b6  mov     edi, eax
0x1400202b8  test    eax, eax
0x1400202ba  jns     short loc_1400202FF
0x1400202bc  mov     eax, cs:dword_140013058
0x1400202c2  cmp     eax, 2
0x1400202c5  jbe     short loc_1400202DE
0x1400202c7  mov     r9, rsi
0x1400202ca  lea     rcx, aVmbustlsetuppa; "VmbusTlSetupPartition"
0x1400202d1  mov     r8d, edi
0x1400202d4  mov     edx, 119h
0x1400202d9  call    HvsocketTraceGuidError
0x1400202de  lea     rcx, [rbx+10h]; FastMutex
0x1400202e2  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400202e9  nop     dword ptr [rax+rax+00h]
0x1400202ee  call    cs:__imp_KeLeaveCriticalRegion
0x1400202f5  nop     dword ptr [rax+rax+00h]
0x1400202fa  jmp     loc_14002043D
0x1400202ff  mov     byte ptr [rbx+1D8h], 1
0x140020306  lea     rdi, [rbx+10h]
0x14002030a  test    r14b, r14b
0x14002030d  jnz     short loc_140020323
0x14002030f  mov     rcx, rbx
0x140020312  mov     [rbx+0F8h], r14b
0x140020319  call    VmbusTlLoopbackSetupPartitionTransport
0x14002031e  jmp     loc_1400203BA
0x140020323  mov     rax, [rbx+0C8h]
0x14002032a  mov     byte ptr [rbx+0F8h], 1
0x140020331  movups  xmm0, xmmword ptr [r15]
0x140020335  movups  xmmword ptr [rbx+1E0h], xmm0
0x14002033c  movups  xmm1, xmmword ptr [r15+10h]
0x140020341  movups  xmmword ptr [rbx+1F0h], xmm1
0x140020348  test    rax, rax
0x14002034b  jz      short loc_1400203A3
0x14002034d  cmp     byte ptr [rax+79h], 0
0x140020351  jz      short loc_1400203A3
0x140020353  movaps  xmm0, xmmword ptr cs:HvsocketXboxInterfacePrototype
0x14002035a  movaps  xmm1, xmmword ptr cs:off_14000E190
0x140020361  movups  xmmword ptr [rbx+68h], xmm0
0x140020365  movaps  xmm0, xmmword ptr cs:off_14000E1A0
0x14002036c  movups  xmmword ptr [rbx+78h], xmm1
0x140020370  movaps  xmm1, xmmword ptr cs:off_14000E1B0
0x140020377  movups  xmmword ptr [rbx+88h], xmm0
0x14002037e  movaps  xmm0, xmmword ptr cs:off_14000E1C0
0x140020385  movups  xmmword ptr [rbx+98h], xmm1
0x14002038c  movaps  xmm1, cs:xmmword_14000E1D0
0x140020393  movups  xmmword ptr [rbx+0A8h], xmm0
0x14002039a  movups  xmmword ptr [rbx+0B8h], xmm1
0x1400203a1  jmp     short loc_1400203BA
0x1400203a3  test    r13, r13
0x1400203a6  jnz     short loc_1400203B2
0x1400203a8  test    r12, r12
0x1400203ab  jnz     short loc_1400203B2
0x1400203ad  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x1400203b2  mov     rcx, rbx
0x1400203b5  call    VmbusTlXPartSetupPartitionTransport
0x1400203ba  lea     rax, [rbx+0D8h]
0x1400203c1  mov     rcx, [rax]
0x1400203c4  cmp     [rcx+8], rax
0x1400203c8  jnz     loc_14002051E
0x1400203ce  mov     rdx, [rax+8]
0x1400203d2  cmp     [rdx], rax
0x1400203d5  jnz     loc_14002051E
0x1400203db  mov     [rdx], rcx
0x1400203de  mov     [rcx+8], rdx
0x1400203e2  lea     rdx, [rbp+80h]
0x1400203e9  mov     [rax+8], rax
0x1400203ed  mov     [rax], rax
0x1400203f0  mov     r8, [rdx+8]
0x1400203f4  cmp     [r8], rdx
0x1400203f7  jnz     loc_14002051E
0x1400203fd  mov     [rax], rdx
0x140020400  mov     rcx, rdi; FastMutex
0x140020403  mov     [rax+8], r8
0x140020407  mov     [r8], rax
0x14002040a  mov     [rdx+8], rax
0x14002040e  inc     dword ptr [rbp+0A0h]
0x140020414  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14002041b  nop     dword ptr [rax+rax+00h]
0x140020420  call    cs:__imp_KeLeaveCriticalRegion
0x140020427  nop     dword ptr [rax+rax+00h]
0x14002042c  lock inc dword ptr [rbp+488h]
0x140020433  mov     rax, [rsp+88h+var_48]
0x140020438  xor     edi, edi
0x14002043a  mov     [rax], rbx
0x14002043d  mov     rcx, [rsp+88h+FastMutex]; FastMutex
0x140020442  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140020449  nop     dword ptr [rax+rax+00h]
0x14002044e  call    cs:__imp_KeLeaveCriticalRegion
0x140020455  nop     dword ptr [rax+rax+00h]
0x14002045a  test    rbx, rbx
0x14002045d  jz      loc_140020503
0x140020463  test    edi, edi
0x140020465  jns     short loc_14002046F
0x140020467  mov     rcx, rbx; P
0x14002046a  call    VmbusTlCleanupPartition
0x14002046f  mov     eax, cs:dword_140013058
0x140020475  cmp     eax, 5
0x140020478  jbe     short loc_14002049E
0x14002047a  mov     r9, [rbx+8]
0x14002047e  lea     rax, aDereferenceObj; "Dereference object"
0x140020485  mov     r8, rbx
0x140020488  mov     [rsp+88h+var_68], rax
0x14002048d  mov     edx, 14Eh
0x140020492  lea     rcx, aVmbustlsetuppa; "VmbusTlSetupPartition"
0x140020499  call    HvsocketTraceReferenceCount
0x14002049e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400204a2  lock xadd [rbx+8], rax
0x1400204a8  sub     rax, 1
0x1400204ac  jg      short loc_140020503
0x1400204ae  test    rax, rax
0x1400204b1  jz      short loc_1400204BC
0x1400204b3  mov     ecx, 0Eh
0x1400204b8  int     29h; Win8: RtlFailFast(ecx)
0x1400204ba  jmp     short loc_140020503
0x1400204bc  mov     rax, [rbx+50h]
0x1400204c0  test    rax, rax
0x1400204c3  jz      short loc_1400204CD
0x1400204c5  mov     rcx, rbx
0x1400204c8  call    _guard_dispatch_icall
0x1400204cd  mov     ecx, [rbx+58h]
0x1400204d0  sub     ecx, 1
0x1400204d3  jz      short loc_1400204EF
0x1400204d5  cmp     ecx, 1
0x1400204d8  jnz     short loc_140020503
0x1400204da  mov     rcx, [rbx+60h]; Lookaside
0x1400204de  mov     rdx, rbx; Entry
0x1400204e1  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400204e8  nop     dword ptr [rax+rax+00h]
0x1400204ed  jmp     short loc_140020503
0x1400204ef  mov     edx, 69706E56h; Tag
0x1400204f4  mov     rcx, rbx; P
0x1400204f7  call    cs:__imp_ExFreePoolWithTag
0x1400204fe  nop     dword ptr [rax+rax+00h]
0x140020503  mov     rbx, [rsp+88h+arg_8]
0x14002050b  mov     eax, edi
0x14002050d  add     rsp, 50h
0x140020511  pop     r15
0x140020513  pop     r14
0x140020515  pop     r13
0x140020517  pop     r12
0x140020519  pop     rdi
0x14002051a  pop     rsi
0x14002051b  pop     rbp
0x14002051c  retn
0x14002051e  mov     ecx, 3
0x140020523  int     29h; Win8: RtlFailFast(ecx)
```
