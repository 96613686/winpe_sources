# FveTestRwWorker

- ea: `0x1400bc8b0`
- end: `0x1400bd089`
- name: `FveTestRwWorker`
- size: `2009`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140006fc8`
- `0x140021a00`
- `0x140021d00`
- `0x140022220`
- `0x140029a38`
- `0x1400bc00c`
- `0x1400bc3c0`
- `0x1400bc8b0`
- `0x1400da91c`
- `0x1400daf2c`
- `0x1400df568`

## import_xrefs

- `ntoskrnl!KeReadStateEvent` at `0x1400bca5c`
- `ntoskrnl!KeReadStateEvent` at `0x1400bca81`
- `ntoskrnl!KeReadStateEvent` at `0x1400bca5c`
- `ntoskrnl!KeReadStateEvent` at `0x1400bca81`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400bce14`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400bcfcb`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400bce14`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x1400bcfcb`
- `ntoskrnl!KeClearEvent` at `0x1400bc99f`
- `ntoskrnl!KeClearEvent` at `0x1400bce38`
- `ntoskrnl!KeClearEvent` at `0x1400bcfee`
- `ntoskrnl!KeClearEvent` at `0x1400bc99f`
- `ntoskrnl!KeClearEvent` at `0x1400bce38`
- `ntoskrnl!KeClearEvent` at `0x1400bcfee`
- `ntoskrnl!IoQueueWorkItem` at `0x1400bcd88`
- `ntoskrnl!IoQueueWorkItem` at `0x1400bcd88`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bceac`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400bceac`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400bc9d5`
- `ntoskrnl!KeSetActualBasePriorityThread` at `0x1400bc9d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bce7e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400bce7e`
- `ntoskrnl!KeSetEvent` at `0x1400bc9e9`
- `ntoskrnl!KeSetEvent` at `0x1400bcf5c`
- `ntoskrnl!KeSetEvent` at `0x1400bc9e9`
- `ntoskrnl!KeSetEvent` at `0x1400bcf5c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bca09`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400bca09`
- `HAL!KeQueryPerformanceCounter` at `0x1400bd020`
- `HAL!KeQueryPerformanceCounter` at `0x1400bd020`

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
  if ( !KeReadStateEvent((PRKEVENT)(v58 + 4688)) )
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
              FvepLockAcquireLock((PFAST_MUTEX)(v58 + 4600));
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
    FvepLockAcquireLock((PFAST_MUTEX)(v16 + 4600));
    *(LARGE_INTEGER *)(*(_QWORD *)(v1 + 328) + 56LL) = PerformanceCounter;
    *(_DWORD *)(*(_QWORD *)(v1 + 328) + 88LL) = ((*(int *)(*(_QWORD *)(v1 + 328) + 84LL) >> 31) & 0xFFFFFFFE) + 1;
    FvepLockReleaseLock(v65);
    FvepReleaseRemoveLock(v16 + 56);
  }
}

```

## disassembly

```asm
0x1400bc8b0  push    rbp
0x1400bc8b2  push    rbx
0x1400bc8b3  push    rsi
0x1400bc8b4  push    rdi
0x1400bc8b5  push    r12
0x1400bc8b7  push    r13
0x1400bc8b9  push    r14
0x1400bc8bb  push    r15
0x1400bc8bd  lea     rbp, [rsp-1Fh]
0x1400bc8c2  sub     rsp, 0E8h
0x1400bc8c9  mov     rdi, [rcx+10h]
0x1400bc8cd  xor     r12d, r12d
0x1400bc8d0  mov     r15, [rcx+28h]
0x1400bc8d4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1400bc8d8  mov     r14, rcx
0x1400bc8db  mov     dword ptr [rbp+57h+Size], r12d
0x1400bc8df  mov     [rbp+57h+arg_8], r12d
0x1400bc8e3  mov     rax, [rdi+48h]
0x1400bc8e7  mov     [rbp+57h+var_B8], rax
0x1400bc8eb  movzx   eax, byte ptr [rdi+13Dh]
0x1400bc8f2  mov     [rbp+57h+var_88], eax
0x1400bc8f5  mov     [rbp+57h+var_A0], rbx
0x1400bc8f9  cmp     [rdi+0F8h], r12
0x1400bc900  jz      short loc_1400BC916
0x1400bc902  mov     rdx, [rdi+110h]
0x1400bc909  add     rdx, [rdi+108h]
0x1400bc910  mov     [rbp+57h+var_90], rdx
0x1400bc914  jmp     short loc_1400BC921
0x1400bc916  mov     rax, [rdi+0B8h]
0x1400bc91d  mov     [rbp+57h+var_90], rax
0x1400bc921  mov     al, [rcx+40h]
0x1400bc924  add     al, 41h ; 'A'
0x1400bc926  mov     [rcx+28h], r12
0x1400bc92a  mov     ecx, [rdi+138h]
0x1400bc930  mov     [rbp+57h+arg_0], al
0x1400bc933  mov     eax, 4
0x1400bc938  sub     ecx, 1
0x1400bc93b  jz      short loc_1400BC966
0x1400bc93d  sub     ecx, 1
0x1400bc940  jz      loc_1400BCBC7
0x1400bc946  sub     ecx, 1
0x1400bc949  jz      loc_1400BCBBF
0x1400bc94f  sub     ecx, 1
0x1400bc952  jz      loc_1400BCBB0
0x1400bc958  sub     ecx, 1
0x1400bc95b  jz      short loc_1400BC966
0x1400bc95d  cmp     ecx, 1
0x1400bc960  jz      loc_1400BCBC7
0x1400bc966  mov     esi, eax
0x1400bc968  mov     [rbp+57h+arg_18], esi
0x1400bc96b  mov     [rbp+57h+pulResult], r12d
0x1400bc96f  cmp     [rdi+128h], r12d
0x1400bc976  jbe     short loc_1400BC9BE
0x1400bc978  mov     ebx, r12d
0x1400bc97b  mov     edx, r12d
0x1400bc97e  mov     rax, [r14+20h]
0x1400bc982  mov     ecx, ebx
0x1400bc984  mov     rcx, [rax+rcx*8]
0x1400bc988  mov     [rcx+58h], esi
0x1400bc98b  mov     rax, [r14+20h]
0x1400bc98f  mov     rcx, [rax+rdx*8]
0x1400bc993  mov     [rcx+79h], r12b
0x1400bc997  mov     rcx, [r14+30h]
0x1400bc99b  mov     rcx, [rcx+rdx*8]; Event
0x1400bc99f  call    cs:__imp_KeClearEvent
0x1400bc9a6  nop     dword ptr [rax+rax+00h]
0x1400bc9ab  inc     ebx
0x1400bc9ad  mov     edx, ebx
0x1400bc9af  cmp     ebx, [rdi+128h]
0x1400bc9b5  jb      short loc_1400BC97E
0x1400bc9b7  mov     [rbp+57h+pulResult], ebx
0x1400bc9ba  mov     rbx, [rbp+57h+var_A0]
0x1400bc9be  lock inc dword ptr [rdi+150h]
0x1400bc9c5  movzx   edx, byte ptr [rdi+13Ch]
0x1400bc9cc  mov     rcx, gs:188h
0x1400bc9d5  call    cs:__imp_KeSetActualBasePriorityThread
0x1400bc9dc  nop     dword ptr [rax+rax+00h]
0x1400bc9e1  xor     r8d, r8d; Wait
0x1400bc9e4  xor     edx, edx; Increment
0x1400bc9e6  mov     rcx, r15; Event
0x1400bc9e9  call    cs:__imp_KeSetEvent
0x1400bc9f0  nop     dword ptr [rax+rax+00h]
0x1400bc9f5  lea     rcx, [rdi+0C8h]; Object
0x1400bc9fc  mov     [rsp+120h+Timeout], r12; Timeout
0x1400bca01  xor     r9d, r9d; Alertable
0x1400bca04  xor     r8d, r8d; WaitMode
0x1400bca07  xor     edx, edx; WaitReason
0x1400bca09  call    cs:__imp_KeWaitForSingleObject
0x1400bca10  nop     dword ptr [rax+rax+00h]
0x1400bca15  lea     rax, [r14+38h]
0x1400bca19  lea     rcx, [r14+30h]
0x1400bca1d  mov     r13, rax
0x1400bca20  mov     r12, rcx
0x1400bca23  lea     rdx, [rdi+120h]
0x1400bca2a  mov     [rbp+57h+var_A8], rdx
0x1400bca2e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1400bca32  jz      short loc_1400BCA4F
0x1400bca34  mov     r13, rax
0x1400bca37  mov     r12, rcx
0x1400bca3a  cmp     rbx, [rbp+57h+var_90]
0x1400bca3e  jb      short loc_1400BCA4F
0x1400bca40  cmp     dword ptr [rdx], 0
0x1400bca43  mov     r15, rax
0x1400bca46  mov     rbx, rcx
0x1400bca49  jge     loc_1400BCF95
0x1400bca4f  mov     rbx, rcx
0x1400bca52  mov     r15, rax
0x1400bca55  lea     rcx, [rdi+0E0h]; Event
0x1400bca5c  call    cs:__imp_KeReadStateEvent
0x1400bca63  nop     dword ptr [rax+rax+00h]
0x1400bca68  test    eax, eax
0x1400bca6a  jnz     loc_1400BCF95
0x1400bca70  mov     r15, r13
0x1400bca73  mov     rbx, r12
0x1400bca76  mov     r13, [rbp+57h+var_B8]
0x1400bca7a  lea     rcx, [r13+1250h]; Event
0x1400bca81  call    cs:__imp_KeReadStateEvent
0x1400bca88  nop     dword ptr [rax+rax+00h]
0x1400bca8d  test    eax, eax
0x1400bca8f  jnz     loc_1400BCF99
0x1400bca95  mov     rax, [rbp+57h+var_A8]
0x1400bca99  cmp     dword ptr [rax], 0
0x1400bca9c  jz      short loc_1400BCABD
0x1400bca9e  mov     rax, 0FFFFF78000000320h
0x1400bcaa8  lea     r15, [r14+38h]
0x1400bcaac  lea     rbx, [r14+30h]
0x1400bcab0  mov     rax, [rax]
0x1400bcab3  cmp     rax, [rdi+28h]
0x1400bcab7  jg      loc_1400BCF99
0x1400bcabd  xor     r13d, r13d
0x1400bcac0  xor     edx, edx
0x1400bcac2  mov     [rbp+57h+pulResult], r13d
0x1400bcac6  mov     [rbp+57h+var_B0], edx
0x1400bcac9  cmp     [rdi+128h], edx
0x1400bcacf  jbe     loc_1400BCD0F
0x1400bcad5  mov     r12, [rbp+57h+var_A0]
0x1400bcad9  xor     ecx, ecx
0x1400bcadb  mov     al, [rdi+13Eh]
0x1400bcae1  neg     al
0x1400bcae3  mov     rax, [r14+20h]
0x1400bcae7  sbb     r15d, r15d
0x1400bcaea  and     r15d, 0FFFFFFF7h
0x1400bcaee  add     r15d, 0Ah
0x1400bcaf2  mov     rbx, [rax+rcx*8]
0x1400bcaf6  cmp     byte ptr [rbx+79h], 0
0x1400bcafa  jnz     loc_1400BCCF8
0x1400bcb00  mov     rax, r12
0x1400bcb03  xor     r13d, r13d
0x1400bcb06  mov     [rbp+57h+var_98], rax
0x1400bcb0a  lea     r9, [rbp+57h+Size]
0x1400bcb0e  mov     rdx, rax
0x1400bcb11  lea     r8, [rbp+57h+var_98]
0x1400bcb15  mov     rcx, rdi
0x1400bcb18  call    FveTestRwGetNextRequestParameters
0x1400bcb1d  mov     rax, [rbp+57h+var_98]
0x1400bcb21  mov     rdx, [rbp+57h+var_90]
0x1400bcb25  cmp     rax, rdx
0x1400bcb28  jb      short loc_1400BCB53
0x1400bcb2a  mov     rcx, [rbp+57h+var_A8]
0x1400bcb2e  cmp     dword ptr [rcx], 0
0x1400bcb31  jge     loc_1400BCBD1
0x1400bcb37  lea     r9, [rbp+57h+Size]
0x1400bcb3b  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1400bcb3f  lea     r8, [rbp+57h+var_98]
0x1400bcb43  mov     rcx, rdi
0x1400bcb46  call    FveTestRwGetNextRequestParameters
0x1400bcb4b  mov     rax, [rbp+57h+var_98]
0x1400bcb4f  mov     rdx, [rbp+57h+var_90]
0x1400bcb53  mov     r12d, dword ptr [rbp+57h+Size]
0x1400bcb57  cmp     r12d, [rdi+118h]
0x1400bcb5e  jz      short loc_1400BCB68
0x1400bcb60  inc     r13d
0x1400bcb63  cmp     r13d, r15d
0x1400bcb66  jb      short loc_1400BCB0A
0x1400bcb68  mov     rcx, [rbp+57h+var_A8]
0x1400bcb6c  cmp     rax, rdx
0x1400bcb6f  jb      short loc_1400BCB7A
0x1400bcb71  cmp     dword ptr [rcx], 0
0x1400bcb74  jge     loc_1400BCD0B
0x1400bcb7a  inc     [rbp+57h+pulResult]
0x1400bcb7d  mov     [rbx+10h], rax
0x1400bcb81  mov     [rbx+50h], r12d
0x1400bcb85  mov     byte ptr [rbx+78h], 0
0x1400bcb89  cmp     byte ptr [rdi+13Eh], 0
0x1400bcb90  mov     [rbp+57h+var_A0], rax
0x1400bcb94  jz      loc_1400BCC4D
0x1400bcb9a  mov     r15b, [r14+40h]
0x1400bcb9e  mov     rcx, [rbx+28h]; void *
0x1400bcba2  mov     r13d, r12d
0x1400bcba5  cmp     esi, 4
0x1400bcba8  jnz     short loc_1400BCC10
0x1400bcbaa  lea     rax, [rcx+r13]
0x1400bcbae  jmp     short loc_1400BCBE0
0x1400bcbb0  mov     esi, [r14+40h]
0x1400bcbb4  and     esi, 1
0x1400bcbb7  add     esi, 3
0x1400bcbba  jmp     loc_1400BC968
0x1400bcbbf  mov     esi, [r14+40h]
0x1400bcbc3  not     esi
0x1400bcbc5  jmp     short loc_1400BCBB4
0x1400bcbc7  mov     esi, 3
0x1400bcbcc  jmp     loc_1400BC968
0x1400bcbd1  mov     r12d, dword ptr [rbp+57h+Size]
0x1400bcbd5  jmp     short loc_1400BCB6C
0x1400bcbd7  mov     [rcx], r15b
0x1400bcbda  inc     r15b
0x1400bcbdd  inc     rcx
0x1400bcbe0  cmp     rcx, rax
0x1400bcbe3  jb      short loc_1400BCBD7
0x1400bcbe5  cmp     dword ptr [rdi+138h], 5
0x1400bcbec  jnz     short loc_1400BCBFE
0x1400bcbee  mov     rdx, [rbx+28h]; Src
0x1400bcbf2  mov     r8, r13; Size
0x1400bcbf5  mov     rcx, [rbx+38h]; void *
0x1400bcbf9  call    memmove
0x1400bcbfe  movzx   edx, [rbp+57h+arg_0]; Val
0x1400bcc02  mov     r8, r13; Size
0x1400bcc05  mov     rcx, [rbx+30h]; void *
0x1400bcc09  call    memset
0x1400bcc0e  jmp     short loc_1400BCC4D
0x1400bcc10  movzx   edx, [rbp+57h+arg_0]; Val
0x1400bcc14  mov     r8d, r12d; Size
0x1400bcc17  call    memset
0x1400bcc1c  mov     rax, [rbx+30h]
0x1400bcc20  lea     rcx, [rax+r13]
0x1400bcc24  jmp     short loc_1400BCC2F
0x1400bcc26  mov     [rax], r15b
0x1400bcc29  inc     r15b
0x1400bcc2c  inc     rax
0x1400bcc2f  cmp     rax, rcx
0x1400bcc32  jb      short loc_1400BCC26
0x1400bcc34  cmp     dword ptr [rdi+138h], 6
0x1400bcc3b  jnz     short loc_1400BCC4D
0x1400bcc3d  mov     rdx, [rbx+30h]; Src
0x1400bcc41  mov     r8, r13; Size
0x1400bcc44  mov     rcx, [rbx+38h]; void *
0x1400bcc48  call    memmove
0x1400bcc4d  mov     rax, [rbx+18h]
0x1400bcc51  mov     edx, esi
0x1400bcc53  mov     r8d, [rbp+57h+var_88]
0x1400bcc57  mov     rcx, [rbp+57h+var_B8]
0x1400bcc5b  mov     [rsp+120h+var_D0], 0
0x1400bcc60  mov     [rsp+120h+var_D8], 0
0x1400bcc68  mov     [rsp+120h+var_E0], 0
0x1400bcc70  mov     [rsp+120h+WaitBlockArray], rax
0x1400bcc75  mov     rax, [rbx+20h]
0x1400bcc79  mov     [rsp+120h+var_F0], 0
0x1400bcc82  mov     qword ptr [rsp+120h+Alertable], rax
0x1400bcc87  mov     dword ptr [rsp+120h+Timeout], r12d
0x1400bcc8c  mov     r12, [rbp+57h+var_A0]
0x1400bcc90  mov     r9, r12
0x1400bcc93  call    FveInitPreallocatedIrp
0x1400bcc98  mov     rax, [rbx+18h]
0x1400bcc9c  mov     edx, [rbp+57h+var_B0]
0x1400bcc9f  dec     byte ptr [rax+43h]
0x1400bcca2  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400bccaa  mov     rax, [rbx+18h]
0x1400bccae  mov     rcx, [rax+0B8h]
0x1400bccb5  movups  xmm0, xmmword ptr [rcx]
0x1400bccb8  movups  xmmword ptr [rcx-48h], xmm0
0x1400bccbc  movups  xmm1, xmmword ptr [rcx+10h]
0x1400bccc0  movups  xmmword ptr [rcx-38h], xmm1
0x1400bccc4  movups  xmm0, xmmword ptr [rcx+20h]
0x1400bccc8  movups  xmmword ptr [rcx-28h], xmm0
0x1400bcccc  movsd   xmm1, qword ptr [rcx+30h]
0x1400bccd1  movsd   qword ptr [rcx-18h], xmm1
0x1400bccd6  mov     byte ptr [rcx-45h], 0
0x1400bccda  mov     rax, [rbx+18h]
0x1400bccde  mov     rcx, [rax+0B8h]
0x1400bcce5  lea     rax, FveTestRwCompletion
0x1400bccec  mov     [rcx-10h], rax
0x1400bccf0  mov     [rcx-8], rbx
0x1400bccf4  mov     byte ptr [rcx-45h], 0E0h
0x1400bccf8  inc     edx
0x1400bccfa  mov     [rbp+57h+var_B0], edx
0x1400bccfd  mov     ecx, edx
0x1400bccff  cmp     edx, [rdi+128h]
0x1400bcd05  jb      loc_1400BCADB
0x1400bcd0b  mov     r13d, [rbp+57h+pulResult]
0x1400bcd0f  cmp     dword ptr [rdi+128h], 0
0x1400bcd16  mov     [rbp+57h+pulResult], 0
0x1400bcd1d  jbe     loc_1400BCDCD
0x1400bcd23  mov     esi, [rbp+57h+arg_8]
0x1400bcd26  xor     ebx, ebx
0x1400bcd28  xor     eax, eax
0x1400bcd2a  xor     r8d, r8d
0x1400bcd2d  test    r13d, r13d
0x1400bcd30  jz      loc_1400BCDC7
0x1400bcd36  mov     ecx, eax
0x1400bcd38  mov     rax, [r14+20h]
0x1400bcd3c  mov     rdx, [rax+rcx*8]
0x1400bcd40  cmp     byte ptr [rdx+79h], 0
0x1400bcd44  jnz     short loc_1400BCDB1
0x1400bcd46  mov     rax, [rdx+18h]
0x1400bcd4a  inc     esi
0x1400bcd4c  or      r15d, 0FFFFFFFFh
0x1400bcd50  mov     ecx, r8d
0x1400bcd53  mov     [rax+78h], rdx
0x1400bcd57  mov     byte ptr [rdx+79h], 1
0x1400bcd5b  cmp     [rdi+11Ch], r15d
  ... truncated ...
```
