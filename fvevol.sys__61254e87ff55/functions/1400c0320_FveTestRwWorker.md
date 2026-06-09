# FveTestRwWorker

- ea: `0x1400c0320`
- end: `0x1400c0af9`
- name: `FveTestRwWorker`
- size: `2009`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140007088`
- `0x140022d40`
- `0x140023040`
- `0x140023560`
- `0x14002aa38`
- `0x1400bfa7c`
- `0x1400bfe30`
- `0x1400c0320`
- `0x1400dd18c`
- `0x1400dd79c`
- `0x1400e1d84`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400c04cc`
- `ntoskrnl!KeReadStateEvent` at `0x1400c04f1`
- `ntoskrnl!KeReadStateEvent` at `0x1400c04cc`
- `ntoskrnl!KeReadStateEvent` at `0x1400c04f1`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400c0884`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400c0a3b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400c0884`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400c0a3b`
- `ntoskrnl!KeClearEvent` at `0x1400c040f`
- `ntoskrnl!KeClearEvent` at `0x1400c08a8`
- `ntoskrnl!KeClearEvent` at `0x1400c0a5e`
- `ntoskrnl!KeClearEvent` at `0x1400c040f`
- `ntoskrnl!KeClearEvent` at `0x1400c08a8`
- `ntoskrnl!KeClearEvent` at `0x1400c0a5e`
- `ntoskrnl!IoQueueWorkItem` at `0x1400c07f8`
- `ntoskrnl!IoQueueWorkItem` at `0x1400c07f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c091c`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c091c`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400c0445`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400c0445`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c08ee`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c08ee`
- `ntoskrnl!KeSetEvent` at `0x1400c0459`
- `ntoskrnl!KeSetEvent` at `0x1400c09cc`
- `ntoskrnl!KeSetEvent` at `0x1400c0459`
- `ntoskrnl!KeSetEvent` at `0x1400c09cc`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c0479`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400c0479`
- `HAL!KeQueryPerformanceCounter` at `0x1400c0a90`
- `HAL!KeQueryPerformanceCounter` at `0x1400c0a90`

## pseudocode

```c
void __fastcall FveTestRwWorker(_QWORD *StartContext)
{
  __int64 v1; // rdi
  struct _KEVENT *v2; // r15
  unsigned __int64 v3; // rbx
  unsigned __int8 v5; // al
  unsigned int v6; // esi
  ULONG v7; // ebx
  __int64 v8; // rdx
  PKWAIT_BLOCK *v9; // rax
  PVOID *__attribute__((__org_arrdim(0,0))) *v10; // rcx
  PKWAIT_BLOCK *v11; // r13
  PVOID *__attribute__((__org_arrdim(0,0))) *v12; // r12
  int *v13; // rdx
  PKWAIT_BLOCK *v14; // r15
  PVOID *__attribute__((__org_arrdim(0,0))) *v15; // rbx
  __int64 v16; // r13
  ULONG v17; // r13d
  unsigned int v18; // edx
  __int64 v19; // r12
  __int64 v20; // rcx
  unsigned int v21; // r15d
  __int64 v22; // rbx
  unsigned __int64 v23; // rax
  int v24; // r13d
  unsigned __int64 v25; // rdx
  int *v26; // rcx
  unsigned int v27; // r12d
  bool v28; // zf
  char v29; // r15
  _BYTE *v30; // rcx
  _BYTE *v31; // rax
  int v32; // esi
  _BYTE *v33; // rax
  _BYTE *v34; // rcx
  __int64 v35; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  unsigned int v38; // esi
  ULONG v39; // ebx
  ULONG v40; // eax
  ULONG v41; // r8d
  __int64 v42; // rdx
  __int64 v43; // rcx
  NTSTATUS v44; // eax
  __int64 v45; // rbx
  __int64 v46; // r15
  __int64 v47; // rax
  signed int v48; // ebx
  KIRQL v49; // al
  size_t v50; // r8
  const void *v51; // rdx
  __int64 v52; // rax
  unsigned int i; // esi
  NTSTATUS v54; // eax
  LARGE_INTEGER PerformanceCounter; // rbx
  unsigned int Timeout; // [rsp+20h] [rbp-A9h]
  size_t Size; // [rsp+60h] [rbp-69h] BYREF
  __int64 v58; // [rsp+68h] [rbp-61h]
  int v59; // [rsp+70h] [rbp-59h]
  int *v60; // [rsp+78h] [rbp-51h]
  __int64 v61; // [rsp+80h] [rbp-49h]
  unsigned __int64 v62; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int64 v63; // [rsp+90h] [rbp-39h]
  unsigned int v64; // [rsp+98h] [rbp-31h]
  _BYTE v65[128]; // [rsp+A0h] [rbp-29h] BYREF
  unsigned __int8 v66; // [rsp+130h] [rbp+67h]
  unsigned int v67; // [rsp+138h] [rbp+6Fh]
  ULONG pulResult; // [rsp+140h] [rbp+77h] BYREF
  unsigned int v69; // [rsp+148h] [rbp+7Fh]

  v1 = StartContext[2];
  v2 = (struct _KEVENT *)StartContext[5];
  v3 = -1;
  LODWORD(Size) = 0;
  v67 = 0;
  v58 = *(_QWORD *)(v1 + 72);
  v64 = *(unsigned __int8 *)(v1 + 317);
  v61 = -1;
  if ( *(_QWORD *)(v1 + 248) )
    v63 = *(_QWORD *)(v1 + 264) + *(_QWORD *)(v1 + 272);
  else
    v63 = *(_QWORD *)(v1 + 184);
  v5 = *((_BYTE *)StartContext + 64) + 65;
  StartContext[5] = 0;
  v66 = v5;
  switch ( *(_DWORD *)(v1 + 312) )
  {
    case 1:
      break;
    case 2:
LABEL_40:
      v6 = 3;
      goto LABEL_10;
    case 3:
      v32 = ~*((_DWORD *)StartContext + 16);
      goto LABEL_38;
    case 4:
      v32 = *((_DWORD *)StartContext + 16);
LABEL_38:
      v6 = (v32 & 1) + 3;
      goto LABEL_10;
    case 6:
      goto LABEL_40;
  }
  v6 = 4;
LABEL_10:
  v69 = v6;
  pulResult = 0;
  if ( *(_DWORD *)(v1 + 296) )
  {
    v7 = 0;
    v8 = 0;
    do
    {
      *(_DWORD *)(*(_QWORD *)(StartContext[4] + 8LL * v7) + 88LL) = v6;
      *(_BYTE *)(*(_QWORD *)(StartContext[4] + 8 * v8) + 121LL) = 0;
      KeClearEvent(*(PRKEVENT *)(StartContext[6] + 8 * v8));
      v8 = ++v7;
    }
    while ( v7 < *(_DWORD *)(v1 + 296) );
    pulResult = v7;
    v3 = v61;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v1 + 336));
  KeSetActualBasePriorityThread(KeGetCurrentThread(), *(unsigned __int8 *)(v1 + 316));
  KeSetEvent(v2, 0, 0);
  KeWaitForSingleObject((PVOID)(v1 + 200), Executive, 0, 0, 0);
  v9 = (PKWAIT_BLOCK *)(StartContext + 7);
  v10 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(StartContext + 6);
  v11 = (PKWAIT_BLOCK *)(StartContext + 7);
  v12 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(StartContext + 6);
  v13 = (int *)(v1 + 288);
LABEL_15:
  v60 = v13;
  if ( v3 != -1 && (v11 = v9, v12 = v10, v3 >= v63) && (v14 = v9, v15 = v10, *v13 >= 0)
    || (v15 = v10, v14 = v9, KeReadStateEvent((PRKEVENT)(v1 + 224))) )
  {
LABEL_84:
    v16 = v58;
    goto LABEL_85;
  }
  v14 = v11;
  v15 = v12;
  v16 = v58;
  if ( !KeReadStateEvent((PRKEVENT)(v58 + 4704)) )
  {
    if ( !*v60
      || (v14 = (PKWAIT_BLOCK *)(StartContext + 7),
          v15 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(StartContext + 6),
          MEMORY[0xFFFFF78000000320] <= *(_QWORD *)(v1 + 40)) )
    {
      v17 = 0;
      v18 = 0;
      pulResult = 0;
      v59 = 0;
      if ( !*(_DWORD *)(v1 + 296) )
        goto LABEL_55;
      v19 = v61;
      v20 = 0;
      do
      {
        v21 = *(_BYTE *)(v1 + 318) != 0 ? 1 : 10;
        v22 = *(_QWORD *)(StartContext[4] + 8 * v20);
        if ( *(_BYTE *)(v22 + 121) )
          goto LABEL_53;
        v23 = v19;
        v24 = 0;
        v62 = v19;
        while ( 1 )
        {
          FveTestRwGetNextRequestParameters(v1, v23, &v62, &Size);
          v23 = v62;
          v25 = v63;
          if ( v62 < v63 )
            goto LABEL_29;
          v26 = v60;
          if ( *v60 >= 0 )
            break;
          FveTestRwGetNextRequestParameters(v1, -1, &v62, &Size);
          v23 = v62;
          v25 = v63;
LABEL_29:
          v27 = Size;
          if ( (_DWORD)Size != *(_DWORD *)(v1 + 280) && ++v24 < v21 )
            continue;
          v26 = v60;
          goto LABEL_32;
        }
        v27 = Size;
LABEL_32:
        if ( v23 >= v25 && *v26 >= 0 )
          break;
        ++pulResult;
        *(_QWORD *)(v22 + 16) = v23;
        *(_DWORD *)(v22 + 80) = v27;
        *(_BYTE *)(v22 + 120) = 0;
        v28 = *(_BYTE *)(v1 + 318) == 0;
        v61 = v23;
        if ( !v28 )
        {
          v29 = *((_BYTE *)StartContext + 64);
          v30 = *(_BYTE **)(v22 + 40);
          if ( v6 == 4 )
          {
            v31 = &v30[v27];
            while ( v30 < v31 )
              *v30++ = v29++;
            if ( *(_DWORD *)(v1 + 312) == 5 )
              memmove(*(void **)(v22 + 56), *(const void **)(v22 + 40), v27);
            memset(*(void **)(v22 + 48), v66, v27);
          }
          else
          {
            memset(v30, v66, v27);
            v33 = *(_BYTE **)(v22 + 48);
            v34 = &v33[v27];
            while ( v33 < v34 )
              *v33++ = v29++;
            if ( *(_DWORD *)(v1 + 312) == 6 )
              memmove(*(void **)(v22 + 56), *(const void **)(v22 + 48), v27);
          }
        }
        Timeout = v27;
        v19 = v61;
        FveInitPreallocatedIrp(v58, v6, v64, v61, Timeout, *(_QWORD *)(v22 + 32));
        v35 = *(_QWORD *)(v22 + 24);
        v18 = v59;
        --*(_BYTE *)(v35 + 67);
        *(_QWORD *)(v35 + 184) -= 72LL;
        v36 = *(_QWORD *)(*(_QWORD *)(v22 + 24) + 184LL);
        *(_OWORD *)(v36 - 72) = *(_OWORD *)v36;
        *(_OWORD *)(v36 - 56) = *(_OWORD *)(v36 + 16);
        *(_OWORD *)(v36 - 40) = *(_OWORD *)(v36 + 32);
        *(_QWORD *)(v36 - 24) = *(_QWORD *)(v36 + 48);
        *(_BYTE *)(v36 - 69) = 0;
        v37 = *(_QWORD *)(*(_QWORD *)(v22 + 24) + 184LL);
        *(_QWORD *)(v37 - 16) = FveTestRwCompletion;
        *(_QWORD *)(v37 - 8) = v22;
        *(_BYTE *)(v37 - 69) = -32;
LABEL_53:
        v59 = ++v18;
        v20 = v18;
      }
      while ( v18 < *(_DWORD *)(v1 + 296) );
      v17 = pulResult;
LABEL_55:
      v28 = *(_DWORD *)(v1 + 296) == 0;
      pulResult = 0;
      if ( !v28 )
      {
        v38 = v67;
        v39 = 0;
        v40 = 0;
        v41 = 0;
        do
        {
          if ( !v17 )
            break;
          v42 = *(_QWORD *)(StartContext[4] + 8LL * v40);
          if ( !*(_BYTE *)(v42 + 121) )
          {
            ++v38;
            *(_QWORD *)(*(_QWORD *)(v42 + 24) + 120LL) = v42;
            *(_BYTE *)(v42 + 121) = 1;
            if ( *(_DWORD *)(v1 + 284) == -1 && v17 > 1 )
            {
              v43 = *(_QWORD *)(StartContext[4] + 8LL * v41);
              IoQueueWorkItem(
                *(PIO_WORKITEM *)(v43 + 72),
                FveTestRwIssueWorker,
                *(WORK_QUEUE_TYPE *)(v1 + 344),
                *(PVOID *)(v43 + 24));
            }
            else
            {
              FveTestRwIssueWorker(
                **(PDEVICE_OBJECT **)(v1 + 72),
                *(PVOID *)(*(_QWORD *)(StartContext[4] + 8LL * v41) + 24LL));
            }
            --v17;
          }
          v40 = ++v39;
          pulResult = v39;
          v41 = v39;
        }
        while ( v39 < *(_DWORD *)(v1 + 296) );
        v67 = v38;
        v6 = v69;
      }
      v14 = (PKWAIT_BLOCK *)(StartContext + 7);
      v15 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(StartContext + 6);
      if ( v67 )
      {
        v11 = (PKWAIT_BLOCK *)(StartContext + 7);
        v12 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(StartContext + 6);
        while ( 1 )
        {
          v44 = KeWaitForMultipleObjects(*(_DWORD *)(v1 + 296), *v12, WaitAny, Executive, 0, 0, 0, *v11);
          RtlULongSub(v44, 0, &pulResult);
          v45 = pulResult;
          KeClearEvent((PRKEVENT)(*v12)[pulResult]);
          --v67;
          v46 = *(_QWORD *)(StartContext[4] + 8 * v45);
          v28 = *(_BYTE *)(v46 + 120) == 0;
          v47 = *(_QWORD *)(v46 + 24);
          *(_BYTE *)(v46 + 121) = 0;
          v48 = *(_DWORD *)(v47 + 48);
          if ( !v28 )
            break;
          if ( v48 < 0 )
            goto LABEL_79;
          if ( *(_BYTE *)(v1 + 318) )
          {
            v50 = *(unsigned int *)(v46 + 80);
            v51 = *(const void **)(v46 + 56);
            if ( v6 == 4 )
            {
              if ( !memcmp(*(const void **)(v46 + 48), v51, v50) )
                goto LABEL_71;
              v48 = -1073741823;
              goto LABEL_70;
            }
            if ( memcmp(*(const void **)(v46 + 40), v51, v50) )
            {
              v48 = -1073741823;
LABEL_79:
              memset(v65, 0, 0x40u);
              FvepLockAcquireLock((PFAST_MUTEX)(v58 + 4616));
              v52 = *(_QWORD *)(v1 + 328);
              if ( *(int *)(v52 + 84) >= 0 )
              {
                *(_DWORD *)(v52 + 84) = v48;
                *(_QWORD *)(*(_QWORD *)(v1 + 328) + 72LL) = *(_QWORD *)(v46 + 16);
                *(_DWORD *)(*(_QWORD *)(v1 + 328) + 80LL) = *(_DWORD *)(v46 + 80);
                KeSetEvent((PRKEVENT)(v1 + 224), 0, 0);
              }
              FvepLockReleaseLock(v65);
              goto LABEL_82;
            }
          }
LABEL_71:
          v49 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 48));
          _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v1 + 328) + 32LL));
          _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(v1 + 328) + 16LL), *(unsigned int *)(v46 + 80));
          KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 48), v49);
LABEL_82:
          if ( v67 <= *(_DWORD *)(v1 + 300) )
          {
            v13 = v60;
            v9 = (PKWAIT_BLOCK *)(StartContext + 7);
            v3 = v61;
            v10 = (PVOID *__attribute__((__org_arrdim(0,0))) *)(StartContext + 6);
            goto LABEL_15;
          }
        }
        v48 = v48 != -1073741668 ? 0xC0000001 : 0;
LABEL_70:
        if ( v48 < 0 )
          goto LABEL_79;
        goto LABEL_71;
      }
      goto LABEL_84;
    }
  }
LABEL_85:
  for ( i = v67; i; --i )
  {
    v54 = KeWaitForMultipleObjects(*(_DWORD *)(v1 + 296), *v15, WaitAny, Executive, 0, 0, 0, *v14);
    RtlULongSub(v54, 0, &pulResult);
    KeClearEvent((PRKEVENT)(*v15)[pulResult]);
  }
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 336), 0xFFFFFFFF) == 1 )
  {
    memset(v65, 0, 0x40u);
    PerformanceCounter = KeQueryPerformanceCounter(0);
    FvepLockAcquireLock((PFAST_MUTEX)(v16 + 4616));
    *(LARGE_INTEGER *)(*(_QWORD *)(v1 + 328) + 56LL) = PerformanceCounter;
    *(_DWORD *)(*(_QWORD *)(v1 + 328) + 88LL) = ((*(int *)(*(_QWORD *)(v1 + 328) + 84LL) >> 31) & 0xFFFFFFFE) + 1;
    FvepLockReleaseLock(v65);
    FvepReleaseRemoveLock(v16 + 56);
  }
}

```

## disassembly

```asm
0x1400c0320  push    rbp
0x1400c0322  push    rbx
0x1400c0323  push    rsi
0x1400c0324  push    rdi
0x1400c0325  push    r12
0x1400c0327  push    r13
0x1400c0329  push    r14
0x1400c032b  push    r15
0x1400c032d  lea     rbp, [rsp-1Fh]
0x1400c0332  sub     rsp, 0E8h
0x1400c0339  mov     rdi, [rcx+10h]
0x1400c033d  xor     r12d, r12d
0x1400c0340  mov     r15, [rcx+28h]
0x1400c0344  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400c0348  mov     r14, rcx
0x1400c034b  mov     dword ptr [rbp+57h+Size], r12d
0x1400c034f  mov     [rbp+57h+arg_8], r12d
0x1400c0353  mov     rax, [rdi+48h]
0x1400c0357  mov     [rbp+57h+var_B8], rax
0x1400c035b  movzx   eax, byte ptr [rdi+13Dh]
0x1400c0362  mov     [rbp+57h+var_88], eax
0x1400c0365  mov     [rbp+57h+var_A0], rbx
0x1400c0369  cmp     [rdi+0F8h], r12
0x1400c0370  jz      short loc_1400C0386
0x1400c0372  mov     rdx, [rdi+110h]
0x1400c0379  add     rdx, [rdi+108h]
0x1400c0380  mov     [rbp+57h+var_90], rdx
0x1400c0384  jmp     short loc_1400C0391
0x1400c0386  mov     rax, [rdi+0B8h]
0x1400c038d  mov     [rbp+57h+var_90], rax
0x1400c0391  mov     al, [rcx+40h]
0x1400c0394  add     al, 41h ; 'A'
0x1400c0396  mov     [rcx+28h], r12
0x1400c039a  mov     ecx, [rdi+138h]
0x1400c03a0  mov     [rbp+57h+arg_0], al
0x1400c03a3  mov     eax, 4
0x1400c03a8  sub     ecx, 1
0x1400c03ab  jz      short loc_1400C03D6
0x1400c03ad  sub     ecx, 1
0x1400c03b0  jz      loc_1400C0637
0x1400c03b6  sub     ecx, 1
0x1400c03b9  jz      loc_1400C062F
0x1400c03bf  sub     ecx, 1
0x1400c03c2  jz      loc_1400C0620
0x1400c03c8  sub     ecx, 1
0x1400c03cb  jz      short loc_1400C03D6
0x1400c03cd  cmp     ecx, 1
0x1400c03d0  jz      loc_1400C0637
0x1400c03d6  mov     esi, eax
0x1400c03d8  mov     [rbp+57h+arg_18], esi
0x1400c03db  mov     [rbp+57h+pulResult], r12d
0x1400c03df  cmp     [rdi+128h], r12d
0x1400c03e6  jbe     short loc_1400C042E
0x1400c03e8  mov     ebx, r12d
0x1400c03eb  mov     edx, r12d
0x1400c03ee  mov     rax, [r14+20h]
0x1400c03f2  mov     ecx, ebx
0x1400c03f4  mov     rcx, [rax+rcx*8]
0x1400c03f8  mov     [rcx+58h], esi
0x1400c03fb  mov     rax, [r14+20h]
0x1400c03ff  mov     rcx, [rax+rdx*8]
0x1400c0403  mov     [rcx+79h], r12b
0x1400c0407  mov     rcx, [r14+30h]
0x1400c040b  mov     rcx, [rcx+rdx*8]; Event
0x1400c040f  call    cs:__imp_KeClearEvent
0x1400c0416  nop     dword ptr [rax+rax+00h]
0x1400c041b  inc     ebx
0x1400c041d  mov     edx, ebx
0x1400c041f  cmp     ebx, [rdi+128h]
0x1400c0425  jb      short loc_1400C03EE
0x1400c0427  mov     [rbp+57h+pulResult], ebx
0x1400c042a  mov     rbx, [rbp+57h+var_A0]
0x1400c042e  lock inc dword ptr [rdi+150h]
0x1400c0435  movzx   edx, byte ptr [rdi+13Ch]
0x1400c043c  mov     rcx, gs:188h
0x1400c0445  call    cs:__imp_KeSetActualBasePriorityThread
0x1400c044c  nop     dword ptr [rax+rax+00h]
0x1400c0451  xor     r8d, r8d; Wait
0x1400c0454  xor     edx, edx; Increment
0x1400c0456  mov     rcx, r15; Event
0x1400c0459  call    cs:__imp_KeSetEvent
0x1400c0460  nop     dword ptr [rax+rax+00h]
0x1400c0465  lea     rcx, [rdi+0C8h]; Object
0x1400c046c  mov     [rsp+120h+Timeout], r12; Timeout
0x1400c0471  xor     r9d, r9d; Alertable
0x1400c0474  xor     r8d, r8d; WaitMode
0x1400c0477  xor     edx, edx; WaitReason
0x1400c0479  call    cs:__imp_KeWaitForSingleObject
0x1400c0480  nop     dword ptr [rax+rax+00h]
0x1400c0485  lea     rax, [r14+38h]
0x1400c0489  lea     rcx, [r14+30h]
0x1400c048d  mov     r13, rax
0x1400c0490  mov     r12, rcx
0x1400c0493  lea     rdx, [rdi+120h]
0x1400c049a  mov     [rbp+57h+var_A8], rdx
0x1400c049e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400c04a2  jz      short loc_1400C04BF
0x1400c04a4  mov     r13, rax
0x1400c04a7  mov     r12, rcx
0x1400c04aa  cmp     rbx, [rbp+57h+var_90]
0x1400c04ae  jb      short loc_1400C04BF
0x1400c04b0  cmp     dword ptr [rdx], 0
0x1400c04b3  mov     r15, rax
0x1400c04b6  mov     rbx, rcx
0x1400c04b9  jge     loc_1400C0A05
0x1400c04bf  mov     rbx, rcx
0x1400c04c2  mov     r15, rax
0x1400c04c5  lea     rcx, [rdi+0E0h]; Event
0x1400c04cc  call    cs:__imp_KeReadStateEvent
0x1400c04d3  nop     dword ptr [rax+rax+00h]
0x1400c04d8  test    eax, eax
0x1400c04da  jnz     loc_1400C0A05
0x1400c04e0  mov     r15, r13
0x1400c04e3  mov     rbx, r12
0x1400c04e6  mov     r13, [rbp+57h+var_B8]
0x1400c04ea  lea     rcx, [r13+1260h]; Event
0x1400c04f1  call    cs:__imp_KeReadStateEvent
0x1400c04f8  nop     dword ptr [rax+rax+00h]
0x1400c04fd  test    eax, eax
0x1400c04ff  jnz     loc_1400C0A09
0x1400c0505  mov     rax, [rbp+57h+var_A8]
0x1400c0509  cmp     dword ptr [rax], 0
0x1400c050c  jz      short loc_1400C052D
0x1400c050e  mov     rax, 0FFFFF78000000320h
0x1400c0518  lea     r15, [r14+38h]
0x1400c051c  lea     rbx, [r14+30h]
0x1400c0520  mov     rax, [rax]
0x1400c0523  cmp     rax, [rdi+28h]
0x1400c0527  jg      loc_1400C0A09
0x1400c052d  xor     r13d, r13d
0x1400c0530  xor     edx, edx
0x1400c0532  mov     [rbp+57h+pulResult], r13d
0x1400c0536  mov     [rbp+57h+var_B0], edx
0x1400c0539  cmp     [rdi+128h], edx
0x1400c053f  jbe     loc_1400C077F
0x1400c0545  mov     r12, [rbp+57h+var_A0]
0x1400c0549  xor     ecx, ecx
0x1400c054b  mov     al, [rdi+13Eh]
0x1400c0551  neg     al
0x1400c0553  mov     rax, [r14+20h]
0x1400c0557  sbb     r15d, r15d
0x1400c055a  and     r15d, 0FFFFFFF7h
0x1400c055e  add     r15d, 0Ah
0x1400c0562  mov     rbx, [rax+rcx*8]
0x1400c0566  cmp     byte ptr [rbx+79h], 0
0x1400c056a  jnz     loc_1400C0768
0x1400c0570  mov     rax, r12
0x1400c0573  xor     r13d, r13d
0x1400c0576  mov     [rbp+57h+var_98], rax
0x1400c057a  lea     r9, [rbp+57h+Size]
0x1400c057e  mov     rdx, rax
0x1400c0581  lea     r8, [rbp+57h+var_98]
0x1400c0585  mov     rcx, rdi
0x1400c0588  call    FveTestRwGetNextRequestParameters
0x1400c058d  mov     rax, [rbp+57h+var_98]
0x1400c0591  mov     rdx, [rbp+57h+var_90]
0x1400c0595  cmp     rax, rdx
0x1400c0598  jb      short loc_1400C05C3
0x1400c059a  mov     rcx, [rbp+57h+var_A8]
0x1400c059e  cmp     dword ptr [rcx], 0
0x1400c05a1  jge     loc_1400C0641
0x1400c05a7  lea     r9, [rbp+57h+Size]
0x1400c05ab  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400c05af  lea     r8, [rbp+57h+var_98]
0x1400c05b3  mov     rcx, rdi
0x1400c05b6  call    FveTestRwGetNextRequestParameters
0x1400c05bb  mov     rax, [rbp+57h+var_98]
0x1400c05bf  mov     rdx, [rbp+57h+var_90]
0x1400c05c3  mov     r12d, dword ptr [rbp+57h+Size]
0x1400c05c7  cmp     r12d, [rdi+118h]
0x1400c05ce  jz      short loc_1400C05D8
0x1400c05d0  inc     r13d
0x1400c05d3  cmp     r13d, r15d
0x1400c05d6  jb      short loc_1400C057A
0x1400c05d8  mov     rcx, [rbp+57h+var_A8]
0x1400c05dc  cmp     rax, rdx
0x1400c05df  jb      short loc_1400C05EA
0x1400c05e1  cmp     dword ptr [rcx], 0
0x1400c05e4  jge     loc_1400C077B
0x1400c05ea  inc     [rbp+57h+pulResult]
0x1400c05ed  mov     [rbx+10h], rax
0x1400c05f1  mov     [rbx+50h], r12d
0x1400c05f5  mov     byte ptr [rbx+78h], 0
0x1400c05f9  cmp     byte ptr [rdi+13Eh], 0
0x1400c0600  mov     [rbp+57h+var_A0], rax
0x1400c0604  jz      loc_1400C06BD
0x1400c060a  mov     r15b, [r14+40h]
0x1400c060e  mov     rcx, [rbx+28h]; void *
0x1400c0612  mov     r13d, r12d
0x1400c0615  cmp     esi, 4
0x1400c0618  jnz     short loc_1400C0680
0x1400c061a  lea     rax, [rcx+r13]
0x1400c061e  jmp     short loc_1400C0650
0x1400c0620  mov     esi, [r14+40h]
0x1400c0624  and     esi, 1
0x1400c0627  add     esi, 3
0x1400c062a  jmp     loc_1400C03D8
0x1400c062f  mov     esi, [r14+40h]
0x1400c0633  not     esi
0x1400c0635  jmp     short loc_1400C0624
0x1400c0637  mov     esi, 3
0x1400c063c  jmp     loc_1400C03D8
0x1400c0641  mov     r12d, dword ptr [rbp+57h+Size]
0x1400c0645  jmp     short loc_1400C05DC
0x1400c0647  mov     [rcx], r15b
0x1400c064a  inc     r15b
0x1400c064d  inc     rcx
0x1400c0650  cmp     rcx, rax
0x1400c0653  jb      short loc_1400C0647
0x1400c0655  cmp     dword ptr [rdi+138h], 5
0x1400c065c  jnz     short loc_1400C066E
0x1400c065e  mov     rdx, [rbx+28h]; Src
0x1400c0662  mov     r8, r13; Size
0x1400c0665  mov     rcx, [rbx+38h]; void *
0x1400c0669  call    memmove
0x1400c066e  movzx   edx, [rbp+57h+arg_0]; Val
0x1400c0672  mov     r8, r13; Size
0x1400c0675  mov     rcx, [rbx+30h]; void *
0x1400c0679  call    memset
0x1400c067e  jmp     short loc_1400C06BD
0x1400c0680  movzx   edx, [rbp+57h+arg_0]; Val
0x1400c0684  mov     r8d, r12d; Size
0x1400c0687  call    memset
0x1400c068c  mov     rax, [rbx+30h]
0x1400c0690  lea     rcx, [rax+r13]
0x1400c0694  jmp     short loc_1400C069F
0x1400c0696  mov     [rax], r15b
0x1400c0699  inc     r15b
0x1400c069c  inc     rax
0x1400c069f  cmp     rax, rcx
0x1400c06a2  jb      short loc_1400C0696
0x1400c06a4  cmp     dword ptr [rdi+138h], 6
0x1400c06ab  jnz     short loc_1400C06BD
0x1400c06ad  mov     rdx, [rbx+30h]; Src
0x1400c06b1  mov     r8, r13; Size
0x1400c06b4  mov     rcx, [rbx+38h]; void *
0x1400c06b8  call    memmove
0x1400c06bd  mov     rax, [rbx+18h]
0x1400c06c1  mov     edx, esi
0x1400c06c3  mov     r8d, [rbp+57h+var_88]
0x1400c06c7  mov     rcx, [rbp+57h+var_B8]
0x1400c06cb  mov     [rsp+120h+var_D0], 0
0x1400c06d0  mov     [rsp+120h+var_D8], 0
0x1400c06d8  mov     [rsp+120h+var_E0], 0
0x1400c06e0  mov     [rsp+120h+WaitBlockArray], rax
0x1400c06e5  mov     rax, [rbx+20h]
0x1400c06e9  mov     [rsp+120h+var_F0], 0
0x1400c06f2  mov     qword ptr [rsp+120h+Alertable], rax
0x1400c06f7  mov     dword ptr [rsp+120h+Timeout], r12d
0x1400c06fc  mov     r12, [rbp+57h+var_A0]
0x1400c0700  mov     r9, r12
0x1400c0703  call    FveInitPreallocatedIrp
0x1400c0708  mov     rax, [rbx+18h]
0x1400c070c  mov     edx, [rbp+57h+var_B0]
0x1400c070f  dec     byte ptr [rax+43h]
0x1400c0712  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400c071a  mov     rax, [rbx+18h]
0x1400c071e  mov     rcx, [rax+0B8h]
0x1400c0725  movups  xmm0, xmmword ptr [rcx]
0x1400c0728  movups  xmmword ptr [rcx-48h], xmm0
0x1400c072c  movups  xmm1, xmmword ptr [rcx+10h]
0x1400c0730  movups  xmmword ptr [rcx-38h], xmm1
0x1400c0734  movups  xmm0, xmmword ptr [rcx+20h]
0x1400c0738  movups  xmmword ptr [rcx-28h], xmm0
0x1400c073c  movsd   xmm1, qword ptr [rcx+30h]
0x1400c0741  movsd   qword ptr [rcx-18h], xmm1
0x1400c0746  mov     byte ptr [rcx-45h], 0
0x1400c074a  mov     rax, [rbx+18h]
0x1400c074e  mov     rcx, [rax+0B8h]
0x1400c0755  lea     rax, FveTestRwCompletion
0x1400c075c  mov     [rcx-10h], rax
0x1400c0760  mov     [rcx-8], rbx
0x1400c0764  mov     byte ptr [rcx-45h], 0E0h
0x1400c0768  inc     edx
0x1400c076a  mov     [rbp+57h+var_B0], edx
0x1400c076d  mov     ecx, edx
0x1400c076f  cmp     edx, [rdi+128h]
0x1400c0775  jb      loc_1400C054B
0x1400c077b  mov     r13d, [rbp+57h+pulResult]
0x1400c077f  cmp     dword ptr [rdi+128h], 0
0x1400c0786  mov     [rbp+57h+pulResult], 0
0x1400c078d  jbe     loc_1400C083D
0x1400c0793  mov     esi, [rbp+57h+arg_8]
0x1400c0796  xor     ebx, ebx
0x1400c0798  xor     eax, eax
0x1400c079a  xor     r8d, r8d
0x1400c079d  test    r13d, r13d
0x1400c07a0  jz      loc_1400C0837
0x1400c07a6  mov     ecx, eax
0x1400c07a8  mov     rax, [r14+20h]
0x1400c07ac  mov     rdx, [rax+rcx*8]
0x1400c07b0  cmp     byte ptr [rdx+79h], 0
0x1400c07b4  jnz     short loc_1400C0821
0x1400c07b6  mov     rax, [rdx+18h]
0x1400c07ba  inc     esi
0x1400c07bc  or      r15d, 0FFFFFFFFh
0x1400c07c0  mov     ecx, r8d
0x1400c07c3  mov     [rax+78h], rdx
0x1400c07c7  mov     byte ptr [rdx+79h], 1
0x1400c07cb  cmp     [rdi+11Ch], r15d
  ... truncated ...
```
