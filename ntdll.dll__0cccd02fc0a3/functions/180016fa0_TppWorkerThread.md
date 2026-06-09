# TppWorkerThread

- ea: `0x180016fa0`
- end: `0x180017e81`
- name: `TppWorkerThread`
- size: `3809`
- prototype: ``
- caller_count: `0`
- callee_count: `40`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x180014ec4`
- `0x180014f40`
- `0x180015d00`
- `0x180016560`
- `0x180016fa0`
- `0x180017e90`
- `0x1800183a0`
- `0x18001855c`
- `0x18001861c`
- `0x180018640`
- `0x180018bc0`
- `0x180019050`
- `0x18001b984`
- `0x180043140`
- `0x1800526f0`
- `0x180053150`
- `0x180053dd0`
- `0x18009a2b0`
- `0x18009a360`
- `0x1800e02b8`
- `0x1800e0770`
- `0x1800e0af0`
- `0x1800e1340`
- `0x1800e44cc`
- `0x1800e4e0c`
- `0x1800e4e5c`
- `0x1800e5edc`
- `0x1800e9214`
- `0x18011dd20`
- `0x180139f68`
- `0x180159510`
- `0x18015e2f0`
- `0x18015e470`
- `0x18015ee80`
- `0x18015f480`
- `0x1801618e0`
- `0x180161f80`
- `0x180162000`
- `0x18016f020`
- `0x18016f030`

## pseudocode

```c
void __fastcall __noreturn TppWorkerThread(__int64 a1)
{
  char v2; // di
  __int64 v3; // rdx
  struct _PEB *v4; // rdi
  _LIST_ENTRY *Blink; // rcx
  unsigned __int64 Number; // r15
  int Group; // esi
  int v8; // r14d
  int v9; // ecx
  unsigned int i; // edx
  __int64 v11; // rax
  __int64 v12; // rax
  __int16 v13; // r15
  __int128 **v14; // rdi
  unsigned int v15; // r14d
  __int128 *v16; // rsi
  __int64 v17; // rdx
  int v18; // edi
  __int64 v19; // r8
  __int64 v20; // r9
  int v21; // ecx
  __int64 v22; // rdi
  unsigned __int8 v23; // r13
  __int64 v24; // rsi
  __int64 v25; // r14
  int v26; // r12d
  int v27; // eax
  bool v28; // si
  int v29; // ecx
  signed __int64 v30; // rax
  __int64 v31; // r9
  signed __int64 v32; // r10
  char v33; // r8
  int v34; // ecx
  struct _TEB *v35; // rcx
  int v36; // ecx
  struct _TEB *v37; // rcx
  _QWORD *v38; // rdx
  unsigned __int16 j; // dx
  _DWORD *SharedData; // rcx
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r9
  __int64 v45; // rcx
  int v46; // edi
  int v47; // edi
  __int64 Heap_0; // rax
  __int128 **v49; // rax
  signed __int64 v50; // rax
  signed __int64 v51; // r8
  struct _PEB *v52; // rdi
  _LIST_ENTRY *v53; // rax
  _LIST_ENTRY *v54; // rcx
  __int128 **v55; // r8
  bool v56; // [rsp+41h] [rbp-287h]
  char v57; // [rsp+42h] [rbp-286h] BYREF
  char v58; // [rsp+43h] [rbp-285h]
  char v59; // [rsp+44h] [rbp-284h]
  char v60; // [rsp+45h] [rbp-283h]
  char v61; // [rsp+46h] [rbp-282h]
  bool v62; // [rsp+47h] [rbp-281h]
  int v63; // [rsp+48h] [rbp-280h]
  int v64; // [rsp+4Ch] [rbp-27Ch]
  int v65; // [rsp+50h] [rbp-278h]
  int v66; // [rsp+54h] [rbp-274h] BYREF
  int v67; // [rsp+58h] [rbp-270h] BYREF
  signed __int64 v68; // [rsp+60h] [rbp-268h]
  char v69; // [rsp+68h] [rbp-260h]
  __int64 v70; // [rsp+70h] [rbp-258h]
  struct _PEB *v71; // [rsp+78h] [rbp-250h]
  unsigned int v72; // [rsp+80h] [rbp-248h]
  int v73; // [rsp+84h] [rbp-244h] BYREF
  _LIST_ENTRY ***v74; // [rsp+88h] [rbp-240h] BYREF
  _DWORD *v75; // [rsp+90h] [rbp-238h]
  __int64 v76; // [rsp+98h] [rbp-230h] BYREF
  __int64 **v77; // [rsp+A0h] [rbp-228h] BYREF
  __int64 v78; // [rsp+A8h] [rbp-220h]
  __int64 v79; // [rsp+B0h] [rbp-218h]
  __int128 *v80; // [rsp+B8h] [rbp-210h]
  __int64 v81; // [rsp+C0h] [rbp-208h]
  _LIST_ENTRY *p_TppWorkerpList; // [rsp+D0h] [rbp-1F8h] BYREF
  _LIST_ENTRY *v83; // [rsp+D8h] [rbp-1F0h]
  __int64 **v84; // [rsp+F0h] [rbp-1D8h]
  __int64 v85; // [rsp+100h] [rbp-1C8h]
  _BYTE v86[72]; // [rsp+108h] [rbp-1C0h] BYREF
  int v87; // [rsp+150h] [rbp-178h]
  char v88; // [rsp+154h] [rbp-174h]
  __int64 v89; // [rsp+160h] [rbp-168h]
  __int64 **v90; // [rsp+168h] [rbp-160h]
  int v91; // [rsp+170h] [rbp-158h]
  __int64 v92; // [rsp+188h] [rbp-140h]
  _QWORD v93[2]; // [rsp+1D8h] [rbp-F0h] BYREF
  unsigned int v94; // [rsp+1E8h] [rbp-E0h]
  int v95; // [rsp+1ECh] [rbp-DCh]
  _GUID ActivityId; // [rsp+1F0h] [rbp-D8h]
  __int64 v97; // [rsp+200h] [rbp-C8h]
  __int128 v98; // [rsp+208h] [rbp-C0h] BYREF
  __int128 v99; // [rsp+218h] [rbp-B0h] BYREF
  __int128 **v100; // [rsp+228h] [rbp-A0h]
  unsigned int v101; // [rsp+230h] [rbp-98h]
  char v102; // [rsp+238h] [rbp-90h]
  unsigned __int16 v103; // [rsp+23Ah] [rbp-8Eh]
  _BYTE v104[6]; // [rsp+240h] [rbp-88h] BYREF
  __int16 v105; // [rsp+246h] [rbp-82h]
  __int64 v106; // [rsp+260h] [rbp-68h]
  int v107; // [rsp+268h] [rbp-60h]
  int v108; // [rsp+26Ch] [rbp-5Ch]
  __int16 v109; // [rsp+270h] [rbp-58h]
  __int16 v110; // [rsp+272h] [rbp-56h]
  int v111; // [rsp+274h] [rbp-54h]
  unsigned int v112; // [rsp+278h] [rbp-50h]
  __int128 v113; // [rsp+280h] [rbp-48h] BYREF

  v75 = (_DWORD *)a1;
  v76 = 0;
  v66 = 0;
  v70 = a1;
  v78 = a1;
  v79 = a1;
  v58 = 0;
  v59 = 0;
  v2 = 0;
  v60 = 0;
  v57 = 0;
  v61 = 0;
  v77 = 0;
  memset_thunk_772440563353939046(&p_TppWorkerpList, 0, 0x170u);
  v74 = 0;
  v73 = 0;
  v63 = 0;
  RtlRegisterThreadWithCsrss();
  v71 = NtCurrentPeb();
  TppCritSetThread(&v76);
  TppAllocThreadData(&v74);
  if ( v74 )
    *v74 = &p_TppWorkerpList;
  memset_thunk_772440563353939046(&p_TppWorkerpList, 0, 0x170u);
  RtlAcquireSRWLockShared(a1 + 368);
  if ( *(_BYTE *)(a1 + 377) )
  {
    v64 = -1073741558;
  }
  else
  {
    v64 = NtWorkerFactoryWorkerReady(*(_QWORD *)(a1 + 56));
    if ( v64 >= 0 )
    {
      _InterlockedIncrement((volatile signed __int32 *)a1);
      goto LABEL_8;
    }
  }
  v2 = 1;
  v69 = 1;
LABEL_8:
  RtlReleaseSRWLockShared(a1 + 368, v3);
  if ( v2 )
    goto LABEL_134;
  TppPoolAddWorker(a1, &p_TppWorkerpList);
  v60 = 1;
  v4 = v71;
  RtlAcquireSRWLockExclusive(&v71->TppWorkerpListLock);
  Blink = v71->TppWorkerpList.Blink;
  if ( Blink->Flink != &v71->TppWorkerpList )
    __fastfail(3u);
  p_TppWorkerpList = &v71->TppWorkerpList;
  v83 = Blink;
  Blink->Flink = (_LIST_ENTRY *)&p_TppWorkerpList;
  v4->TppWorkerpList.Blink = (_LIST_ENTRY *)&p_TppWorkerpList;
  v59 = 1;
  RtlReleaseSRWLockExclusive(&v4->TppWorkerpListLock);
  memset_thunk_772440563353939046(v86, 0, 0x100u);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 416));
  v58 = 1;
  v72 = 0;
  Number = NtCurrentTeb()->CurrentIdealProcessor.Number;
  Group = NtCurrentTeb()->CurrentIdealProcessor.Group;
  v8 = TppNumberNodes;
  v9 = *(_DWORD *)(a1 + 440);
  if ( !v9 )
    v9 = MEMORY[0x7FFE03C0];
  v75 = (_DWORD *)(a1 + 424);
  if ( *(_DWORD *)(a1 + 424) != v9 )
  {
    RtlAcquireSRWLockExclusive(a1 + 72);
    TppAdjustRunningThreadGoalWithLock(a1);
    RtlReleaseSRWLockExclusive(a1 + 72);
  }
  for ( i = 0; ; ++i )
  {
    v72 = i;
    if ( i >= TppNumberNodes )
      goto LABEL_20;
    v11 = *(_QWORD *)(a1 + 48);
    if ( *(_WORD *)(v11 + 16LL * (Group + TppMaximumGroups * i) + 8) == (_WORD)Group )
    {
      v12 = *(_QWORD *)(v11 + 16LL * (Group + TppMaximumGroups * i));
      if ( _bittest64(&v12, Number) )
        break;
    }
  }
  v8 = i;
LABEL_20:
  v101 = v8;
  v103 = Group;
LABEL_21:
  v13 = -1;
  while ( 1 )
  {
    v63 = 0;
    v98 = 0;
    v99 = 0;
    v14 = v100;
    v65 = 16;
    if ( !v100 )
      break;
    if ( *((_DWORD *)v100 + 2) != 1 )
      goto LABEL_130;
    memset_thunk_772440563353939046(*v100, 0, 56LL * *((unsigned int *)v100 + 3));
    v15 = *((_DWORD *)v14 + 3);
    v65 = v15;
    v16 = *v14;
LABEL_25:
    *(_QWORD *)&v113 = v16;
    v80 = v16;
    v66 = 0;
    v18 = ZwWaitForWorkViaWorkerFactory(*(_QWORD *)(a1 + 56), v16, v15, &v66, v93);
    v64 = v18;
    if ( v18 )
      v66 = 0;
    if ( (v95 & 1) != 0 )
    {
      RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v93[0]);
      v95 &= ~1u;
    }
    if ( v18 )
    {
      v46 = v18 - 128;
      if ( !v46 )
        goto LABEL_134;
      v47 = v46 - 64;
      if ( v47 )
      {
        if ( v47 == 66 )
        {
          v61 = 1;
          goto LABEL_134;
        }
      }
      else
      {
        TppCallbackCheckThreadAfterCallback(0, v17, v19, v20);
      }
    }
    else
    {
      if ( !a1 || (v21 = *(_DWORD *)(a1 + 440)) == 0 )
        v21 = MEMORY[0x7FFE03C0];
      if ( *v75 != v21 )
      {
        RtlAcquireSRWLockExclusive(a1 + 72);
        TppAdjustRunningThreadGoalWithLock(a1);
        RtlReleaseSRWLockExclusive(a1 + 72);
      }
      if ( (unsigned __int8)TppPrepareDirectParams(
                              (unsigned int)&p_TppWorkerpList,
                              (_DWORD)v16,
                              v66,
                              v15,
                              a1,
                              (__int64)&v57) )
        goto LABEL_134;
      if ( !v57 )
      {
        v22 = v98;
        if ( (_QWORD)v98 )
        {
          v81 = v98;
          v89 = *(_QWORD *)(v98 + 56);
          v90 = (__int64 **)v98;
          v23 = *(_BYTE *)(v98 + 68);
          v24 = *(unsigned int *)(v98 + 64);
          v113 = 0;
          v67 = 0;
          v25 = v101;
          v26 = v103;
          v27 = *(_DWORD *)(a1 + 428);
          if ( (_DWORD)v24 == v101 )
          {
            if ( v27 == -1 && !v102 )
            {
              v102 = 1;
              _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 4 * v24));
            }
          }
          else
          {
            if ( v27 == -1 )
            {
              if ( v102 )
              {
                v38 = (_QWORD *)(a1 + 40);
                _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)(a1 + 40) + 4LL * v101));
              }
              else
              {
                v102 = 1;
                v38 = (_QWORD *)(v78 + 40);
              }
              _InterlockedIncrement((volatile signed __int32 *)(*v38 + 4 * v24));
            }
            if ( ((1LL << v23) & *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL * (unsigned int)(v26 + TppMaximumGroups * v24))) != 0 )
            {
              v13 = v26;
            }
            else
            {
              for ( j = 0; ; ++j )
              {
                while ( 1 )
                {
                  if ( j >= (unsigned int)TppMaximumGroups )
                    goto LABEL_102;
                  if ( j != (_WORD)v26 )
                    break;
                  ++j;
                }
                if ( ((1LL << v23)
                    & *(_QWORD *)(*(_QWORD *)(a1 + 48) + 16LL * (TppMaximumGroups * (_DWORD)v24 + (unsigned int)j))) != 0 )
                  break;
              }
              v13 = j;
            }
LABEL_102:
            v101 = v24;
            v103 = v13;
            SharedData = NtCurrentPeb()->SharedData;
            if ( SharedData && *SharedData )
              v41 = (__int64)NtCurrentPeb()->SharedData + 556;
            else
              v41 = 2147353478;
            if ( *(_BYTE *)v41 )
            {
              memset_thunk_772440563353939046(v104, 0, 0x40u);
              v105 = 7209;
              v106 = a1;
              v107 = v25;
              v108 = v24;
              v109 = v26;
              v110 = v13;
              v42 = *(_QWORD *)(a1 + 40);
              v111 = *(_DWORD *)(v42 + 4 * v25);
              v112 = *(_DWORD *)(v42 + 4 * v24);
              if ( (unsigned int)RtlGetCurrentServiceSessionId(v112, v42, v43, v44) )
                v45 = (__int64)NtCurrentPeb()->SharedData + 556;
              else
                v45 = 2147353478;
              NtTraceEvent(*(unsigned __int8 *)v45, 1026, 28, v104);
            }
            v113 = 0;
            NtSetInformationThread(-2, 30, &v113, 16);
            LOWORD(v67) = v13;
            HIWORD(v67) = v23;
            NtSetInformationThread(-2, 33, &v67, 4);
          }
          ActivityId = NtCurrentTeb()->ActivityId;
          if ( v92 && (*(_BYTE *)(v92 + 436) & 1) == 0 )
          {
            v34 = v91 | 8;
            v91 |= 8u;
            if ( NtCurrentTeb()->IsImpersonating )
              v91 = v34 | 4;
            v35 = NtCurrentTeb();
            if ( (((unsigned __int64)v35->CurrentTransactionHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
              || v35->TxnScopeEnterCallback
              || v35->TxnScopeExitCallback
              || v35->TxnScopeContext
              || v35->TxFsContext != 65534 )
            {
              v91 |= 0x10u;
            }
            if ( NtCurrentPeb()->LoaderLock->OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
              v91 |= 0x20u;
            if ( NtCurrentTeb()->PreferredLanguages )
              v91 |= 0x40u;
            if ( NtCurrentTeb()->SavedPriorityState )
              v91 |= 0x80u;
          }
          (*(void (__fastcall **)(_BYTE *, __int64, _QWORD, __int128 *))(v22 + 56))(
            v86,
            v22,
            *((_QWORD *)&v98 + 1),
            &v99);
          goto LABEL_42;
        }
        while ( 1 )
        {
          if ( !(unsigned int)TppWorkerFindTask(a1, &p_TppWorkerpList, &v77) )
            goto LABEL_134;
          if ( (v95 & 1) != 0 )
          {
            ZwAlpcSendWaitReceivePort(v93[1], v94, v93[0], 0, 0, 0, 0, 0);
            RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, 0, v93[0]);
            v95 &= ~1u;
          }
          v97 = 0;
          RtlClearThreadWorkOnBehalfTicket();
          v84 = v77;
          v89 = **v77;
          v90 = v77;
          v92 = v85;
          ActivityId = NtCurrentTeb()->ActivityId;
          if ( v85 && (*(_BYTE *)(v85 + 436) & 1) == 0 )
          {
            v36 = v91 | 8;
            v91 |= 8u;
            if ( NtCurrentTeb()->IsImpersonating )
              v91 = v36 | 4;
            v37 = NtCurrentTeb();
            if ( (((unsigned __int64)v37->CurrentTransactionHandle + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
              || v37->TxnScopeEnterCallback
              || v37->TxnScopeExitCallback
              || v37->TxnScopeContext
              || v37->TxFsContext != 65534 )
            {
              v91 |= 0x10u;
            }
            if ( NtCurrentPeb()->LoaderLock->OwningThread == NtCurrentTeb()->ClientId.UniqueThread )
              v91 |= 0x20u;
            if ( NtCurrentTeb()->PreferredLanguages )
              v91 |= 0x40u;
            if ( NtCurrentTeb()->SavedPriorityState )
              v91 |= 0x80u;
          }
          ((void (__fastcall *)(_BYTE *, __int64 **))**v77)(v86, v77);
LABEL_42:
          v56 = (v88 & 4) != 0;
          v28 = v87 == 4;
          v62 = v87 == 4;
          TppCallbackEpilog(v86);
          v84 = 0;
          if ( v56 )
            break;
          if ( !a1 || (v29 = *(_DWORD *)(a1 + 440)) == 0 )
            v29 = MEMORY[0x7FFE03C0];
          if ( *v75 != v29 )
          {
            RtlAcquireSRWLockExclusive(a1 + 72);
            TppAdjustRunningThreadGoalWithLock(a1);
            RtlReleaseSRWLockExclusive(a1 + 72);
          }
          v68 = 0;
          _m_prefetchw((const void *)(a1 + 8));
          v30 = *(_QWORD *)(a1 + 8);
          v68 = v30;
          v31 = v79;
          do
          {
            if ( *(_BYTE *)(v31 + 376) )
              goto LABEL_134;
            v32 = v30;
            if ( HIDWORD(v30) && ((v68 & 0x8000u) == 0LL || v28) )
            {
              v33 = 0;
              HIDWORD(v68) = HIDWORD(v30) - 1;
            }
            else
            {
              v33 = 1;
              LODWORD(v68) = ((__int16)v68 + 1) ^ (((__int16)v68 + 1) ^ v68) & 0xFFFF0000;
            }
            v30 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v68, v30);
            v68 = v30;
          }
          while ( v30 != v32 );
          v57 = v33;
          if ( v33 )
            goto LABEL_21;
        }
        *(_QWORD *)&v113 = 0;
        _m_prefetchw((const void *)(a1 + 8));
        v50 = *(_QWORD *)(a1 + 8);
        *(_QWORD *)&v113 = v50;
        do
        {
          v51 = v50;
          LODWORD(v113) = ((__int16)v50 + 1) ^ (((__int16)v50 + 1) ^ v50) & 0xFFFF0000;
          v50 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 8), v113, v50);
          *(_QWORD *)&v113 = v50;
        }
        while ( v50 != v51 );
        v73 = 3;
        NtSetInformationWorkerFactory(*(_QWORD *)(a1 + 56), 9, &v73, 4);
LABEL_134:
        if ( (v95 & 1) != 0 )
        {
          TppCallbackSendAndDestroyAlpcMessage(v86);
          v95 &= ~1u;
        }
        v97 = 0;
        RtlClearThreadWorkOnBehalfTicket();
        if ( v58 )
          _InterlockedDecrement((volatile signed __int32 *)(a1 + 416));
        if ( v59 )
        {
          v52 = v71;
          RtlAcquireSRWLockExclusive(&v71->TppWorkerpListLock);
          v53 = p_TppWorkerpList;
          if ( (_LIST_ENTRY **)p_TppWorkerpList->Blink != &p_TppWorkerpList
            || (v54 = v83, (_LIST_ENTRY **)v83->Flink != &p_TppWorkerpList) )
          {
            __fastfail(3u);
          }
          v83->Flink = p_TppWorkerpList;
          v53->Blink = v54;
          RtlReleaseSRWLockExclusive(&v52->TppWorkerpListLock);
        }
        if ( v60 )
        {
          TppPoolRemoveWorker(&p_TppWorkerpList);
          if ( v61 )
            TppPoolUpdateTrimmedWorker(a1);
        }
        if ( a1 == TppPoolpGlobalPool )
        {
          TppPoolpDereferenceGlobalPool(&TppPoolpGlobalPool, &TppPoolpGlobalPoolLock);
        }
        else if ( a1 == TppPoolpSerializedPool )
        {
          TppPoolpDereferenceGlobalPool(&TppPoolpSerializedPool, &TppPoolpSerializedPoolLock);
        }
        else if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1, 0xFFFFFFFF) == 1 )
        {
          TppPoolpFree(a1);
        }
        TppCritResetThread(v76);
        TppFreeThreadData(v74);
        v55 = v100;
        if ( v100 && _InterlockedExchangeAdd((volatile signed __int32 *)v100 + 2, 0xFFFFFFFF) == 1 )
          RtlFreeHeap_0(NtCurrentPeb()->ProcessHeap, (unsigned int)(TppHeapTag + 3145728), *v55);
        v64 = 0;
        RtlExitUserThread(0);
        __debugbreak();
      }
    }
  }
  Heap_0 = RtlAllocateHeap_0(NtCurrentPeb()->ProcessHeap, (TppHeapTag + 3145728) | 8u, 912);
  v16 = (__int128 *)Heap_0;
  if ( Heap_0 )
  {
    v49 = (__int128 **)(Heap_0 + 896);
    *v49 = v16;
    *((_DWORD *)v16 + 226) = 1;
    *((_DWORD *)v16 + 227) = 16;
    v100 = v49;
    v15 = 16;
  }
  else
  {
LABEL_130:
    v15 = 1;
    v16 = &v98;
  }
  v65 = v15;
  goto LABEL_25;
}

```

## disassembly

```asm
0x180016fa0  mov     [rsp+arg_8], rbx
0x180016fa5  mov     [rsp+arg_10], rsi
0x180016faa  push    rdi
0x180016fab  push    r12
0x180016fad  push    r13
0x180016faf  push    r14
0x180016fb1  push    r15
0x180016fb3  sub     rsp, 2A0h
0x180016fba  mov     rax, cs:__security_cookie
0x180016fc1  xor     rax, rsp
0x180016fc4  mov     [rsp+2C8h+var_38], rax
0x180016fcc  mov     rbx, rcx
0x180016fcf  mov     [rsp+2C8h+var_238], rcx
0x180016fd7  xor     r12d, r12d
0x180016fda  mov     [rsp+2C8h+var_230], r12
0x180016fe2  mov     [rsp+2C8h+var_274], r12d
0x180016fe7  mov     [rsp+2C8h+var_258], rcx
0x180016fec  mov     [rsp+2C8h+var_220], rcx
0x180016ff4  mov     [rsp+2C8h+var_218], rcx
0x180016ffc  mov     [rsp+2C8h+var_285], r12b
0x180017001  mov     [rsp+2C8h+var_284], r12b
0x180017006  xor     dil, dil
0x180017009  mov     [rsp+2C8h+var_288], dil
0x18001700e  mov     [rsp+2C8h+var_283], dil
0x180017013  mov     [rsp+2C8h+var_286], dil
0x180017018  mov     [rsp+2C8h+var_287], dil
0x18001701d  mov     [rsp+2C8h+var_282], dil
0x180017022  mov     [rsp+2C8h+var_228], r12
0x18001702a  xor     edx, edx; Val
0x18001702c  mov     r8d, 170h; Size
0x180017032  lea     rcx, [rsp+2C8h+var_1F8]; void *
0x18001703a  call    memset$thunk$772440563353939046
0x18001703f  mov     [rsp+2C8h+var_240], r12
0x180017047  mov     [rsp+2C8h+var_244], r12d
0x18001704f  mov     [rsp+2C8h+var_280], r12d
0x180017054  call    RtlRegisterThreadWithCsrss
0x180017059  mov     rax, gs:60h
0x180017062  mov     [rsp+2C8h+var_250], rax
0x180017067  lea     rcx, [rsp+2C8h+var_230]
0x18001706f  call    TppCritSetThread
0x180017074  lea     rcx, [rsp+2C8h+var_240]
0x18001707c  call    TppAllocThreadData
0x180017081  mov     rax, [rsp+2C8h+var_240]
0x180017089  test    rax, rax
0x18001708c  jz      short loc_180017099
0x18001708e  lea     rcx, [rsp+2C8h+var_1F8]
0x180017096  mov     [rax], rcx
0x180017099  xor     edx, edx; Val
0x18001709b  mov     r8d, 170h; Size
0x1800170a1  lea     rcx, [rsp+2C8h+var_1F8]; void *
0x1800170a9  call    memset$thunk$772440563353939046
0x1800170ae  nop
0x1800170af  lea     rcx, [rbx+170h]
0x1800170b6  call    RtlAcquireSRWLockShared
0x1800170bb  nop
0x1800170bc  cmp     byte ptr [rbx+179h], 0
0x1800170c3  jnz     short loc_1800170E0
0x1800170c5  mov     rcx, [rbx+38h]
0x1800170c9  call    NtWorkerFactoryWorkerReady
0x1800170ce  mov     [rsp+2C8h+var_27C], eax
0x1800170d2  test    eax, eax
0x1800170d4  js      short loc_1800170E8
0x1800170d6  lock inc dword ptr [rbx]
0x1800170d9  mov     [rsp+2C8h+var_288], 1
0x1800170de  jmp     short loc_1800170F5
0x1800170e0  mov     [rsp+2C8h+var_27C], 0C000010Ah
0x1800170e8  mov     [rsp+2C8h+var_288], 1
0x1800170ed  mov     dil, 1
0x1800170f0  mov     [rsp+2C8h+var_260], dil
0x1800170f5  lea     rcx, [rbx+170h]
0x1800170fc  call    RtlReleaseSRWLockShared
0x180017101  test    dil, dil
0x180017104  jnz     loc_180017C9F
0x18001710a  lea     rdx, [rsp+2C8h+var_1F8]
0x180017112  mov     rcx, rbx
0x180017115  call    TppPoolAddWorker
0x18001711a  mov     [rsp+2C8h+var_283], 1
0x18001711f  mov     rdi, [rsp+2C8h+var_250]
0x180017124  lea     rcx, [rdi+388h]
0x18001712b  call    RtlAcquireSRWLockExclusive
0x180017130  nop
0x180017131  lea     rax, [rdi+390h]
0x180017138  mov     rcx, [rax+8]
0x18001713c  cmp     [rcx], rax
0x18001713f  jz      short loc_180017148
0x180017141  mov     ecx, 3
0x180017146  int     29h; Win8: RtlFailFast(ecx)
0x180017148  mov     [rsp+2C8h+var_1F8], rax
0x180017150  mov     [rsp+2C8h+var_1F0], rcx
0x180017158  lea     rdx, [rsp+2C8h+var_1F8]
0x180017160  mov     [rcx], rdx
0x180017163  lea     rcx, [rsp+2C8h+var_1F8]
0x18001716b  mov     [rax+8], rcx
0x18001716f  mov     [rsp+2C8h+var_284], 1
0x180017174  lea     rcx, [rdi+388h]
0x18001717b  call    RtlReleaseSRWLockExclusive
0x180017180  xor     edx, edx; Val
0x180017182  mov     r8d, 100h; Size
0x180017188  lea     rcx, [rsp+2C8h+var_1C0]; void *
0x180017190  call    memset$thunk$772440563353939046
0x180017195  lock inc dword ptr [rbx+1A0h]
0x18001719c  mov     [rsp+2C8h+var_285], 1
0x1800171a1  lea     r13, [rsp+2C8h+var_8E]
0x1800171a9  mov     [rsp+2C8h+var_248], r12d
0x1800171b1  mov     rax, gs:30h
0x1800171ba  movzx   r15d, byte ptr [rax+1746h]
0x1800171c2  mov     rax, gs:30h
0x1800171cb  movzx   esi, word ptr [rax+1744h]
0x1800171d2  mov     r14d, cs:TppNumberNodes
0x1800171d9  mov     ecx, [rbx+1B8h]
0x1800171df  test    ecx, ecx
0x1800171e1  jnz     short loc_1800171EA
0x1800171e3  mov     ecx, ds:7FFE03C0h
0x1800171ea  lea     rax, [rbx+1A8h]
0x1800171f1  mov     [rsp+2C8h+var_238], rax
0x1800171f9  cmp     [rax], ecx
0x1800171fb  jz      short loc_180017217
0x1800171fd  lea     rcx, [rbx+48h]
0x180017201  call    RtlAcquireSRWLockExclusive
0x180017206  mov     rcx, rbx
0x180017209  call    TppAdjustRunningThreadGoalWithLock
0x18001720e  lea     rcx, [rbx+48h]
0x180017212  call    RtlReleaseSRWLockExclusive
0x180017217  mov     edx, r12d
0x18001721a  mov     [rsp+2C8h+var_248], edx
0x180017221  cmp     edx, cs:TppNumberNodes
0x180017227  jnb     short loc_180017257
0x180017229  mov     ecx, edx
0x18001722b  imul    ecx, cs:TppMaximumGroups
0x180017232  add     ecx, esi
0x180017234  add     rcx, rcx
0x180017237  mov     rax, [rbx+30h]
0x18001723b  cmp     [rax+rcx*8+8], si
0x180017240  jnz     loc_180017C98
0x180017246  mov     rax, [rax+rcx*8]
0x18001724a  bt      rax, r15
0x18001724e  jnb     loc_180017C98
0x180017254  mov     r14d, edx
0x180017257  mov     [rsp+2C8h+var_98], r14d
0x18001725f  mov     [r13+0], si
0x180017264  mov     r15d, 0FFFFh
0x18001726a  mov     [rsp+2C8h+var_280], r12d
0x18001726f  xorps   xmm0, xmm0
0x180017272  movups  [rsp+2C8h+var_C0], xmm0
0x18001727a  movups  [rsp+2C8h+var_B0], xmm0
0x180017282  mov     rdi, [rsp+2C8h+var_A0]
0x18001728a  mov     [rsp+2C8h+var_278], 10h
0x180017292  test    rdi, rdi
0x180017295  jz      loc_180017B61
0x18001729b  mov     eax, [rdi+8]
0x18001729e  cmp     eax, 1
0x1800172a1  jnz     loc_180017C55
0x1800172a7  mov     eax, [rdi+0Ch]
0x1800172aa  imul    r8, rax, 38h ; '8'; Size
0x1800172ae  xor     edx, edx; Val
0x1800172b0  mov     rcx, [rdi]; void *
0x1800172b3  call    memset$thunk$772440563353939046
0x1800172b8  mov     r14d, [rdi+0Ch]
0x1800172bc  mov     [rsp+2C8h+var_278], r14d
0x1800172c1  mov     rsi, [rdi]
0x1800172c4  mov     qword ptr [rsp+2C8h+var_48], rsi
0x1800172cc  mov     [rsp+2C8h+var_210], rsi
0x1800172d4  mov     [rsp+2C8h+var_274], r12d
0x1800172d9  lea     rax, [rsp+2C8h+var_F0]
0x1800172e1  mov     [rsp+2C8h+var_2A8], rax
0x1800172e6  lea     r9, [rsp+2C8h+var_274]
0x1800172eb  mov     r8d, r14d
0x1800172ee  mov     rdx, rsi
0x1800172f1  mov     rcx, [rbx+38h]
0x1800172f5  call    ZwWaitForWorkViaWorkerFactory
0x1800172fa  mov     edi, eax
0x1800172fc  mov     [rsp+2C8h+var_27C], eax
0x180017300  jmp     short loc_180017332
0x180017302  cmp     eax, 0C00000FDh
0x180017307  jnz     short loc_18001730E
0x180017309  call    RtlResetStackOverflow
0x18001730e  mov     edi, 0C0h
0x180017313  mov     [rsp+2C8h+var_27C], edi
0x180017317  xor     r12d, r12d
0x18001731a  mov     r15d, 0FFFFh
0x180017320  mov     r14d, [rsp+2C8h+var_278]
0x180017325  mov     rbx, [rsp+2C8h+var_258]
0x18001732a  mov     rsi, qword ptr [rsp+2C8h+var_48]
0x180017332  test    edi, edi
0x180017334  jz      short loc_18001733B
0x180017336  mov     [rsp+2C8h+var_274], r12d
0x18001733b  test    byte ptr [rsp+2C8h+var_DC], 1
0x180017343  jz      short loc_180017369
0x180017345  mov     rcx, gs:60h
0x18001734e  mov     r8, [rsp+2C8h+var_F0]
0x180017356  xor     edx, edx
0x180017358  mov     rcx, [rcx+30h]
0x18001735c  call    RtlFreeHeap_0
0x180017361  and     [rsp+2C8h+var_DC], 0FFFFFFFEh
0x180017369  test    edi, edi
0x18001736b  jnz     loc_180017AC2
0x180017371  test    rbx, rbx
0x180017374  jz      short loc_180017380
0x180017376  mov     ecx, [rbx+1B8h]
0x18001737c  test    ecx, ecx
0x18001737e  jnz     short loc_180017387
0x180017380  mov     ecx, ds:7FFE03C0h
0x180017387  mov     rax, [rsp+2C8h+var_238]
0x18001738f  cmp     [rax], ecx
0x180017391  jz      short loc_1800173AD
0x180017393  lea     rcx, [rbx+48h]
0x180017397  call    RtlAcquireSRWLockExclusive
0x18001739c  mov     rcx, rbx
0x18001739f  call    TppAdjustRunningThreadGoalWithLock
0x1800173a4  lea     rcx, [rbx+48h]
0x1800173a8  call    RtlReleaseSRWLockExclusive
0x1800173ad  lea     rax, [rsp+2C8h+var_286]
0x1800173b2  mov     [rsp+2C8h+var_2A0], rax
0x1800173b7  mov     [rsp+2C8h+var_2A8], rbx
0x1800173bc  mov     r9d, r14d
0x1800173bf  mov     r8d, [rsp+2C8h+var_274]
0x1800173c4  mov     rdx, rsi
0x1800173c7  lea     rcx, [rsp+2C8h+var_1F8]
0x1800173cf  call    TppPrepareDirectParams
0x1800173d4  test    al, al
0x1800173d6  jnz     loc_180017C9F
0x1800173dc  cmp     [rsp+2C8h+var_286], al
0x1800173e0  jnz     loc_1800177FA
0x1800173e6  mov     rdi, qword ptr [rsp+2C8h+var_C0]
0x1800173ee  test    rdi, rdi
0x1800173f1  jz      loc_1800175D5
0x1800173f7  mov     [rsp+2C8h+var_208], rdi
0x1800173ff  mov     rax, [rdi+38h]
0x180017403  mov     [rsp+2C8h+var_168], rax
0x18001740b  mov     [rsp+2C8h+var_160], rdi
0x180017413  movzx   r13d, byte ptr [rdi+44h]
0x180017418  mov     esi, [rdi+40h]
0x18001741b  xorps   xmm0, xmm0
0x18001741e  movups  [rsp+2C8h+var_48], xmm0
0x180017426  mov     [rsp+2C8h+var_270], r12d
0x18001742b  mov     r14d, [rsp+2C8h+var_98]
0x180017433  movzx   r12d, [rsp+2C8h+var_8E]
0x18001743c  mov     eax, [rbx+1ACh]
0x180017442  cmp     esi, r14d
0x180017445  jnz     loc_180017905
0x18001744b  cmp     eax, 0FFFFFFFFh
0x18001744e  jz      loc_180017AE5
0x180017454  xor     r12d, r12d
0x180017457  mov     rax, gs:30h
0x180017460  movups  xmm0, xmmword ptr [rax+1710h]
0x180017467  movaps  [rsp+2C8h+var_D8], xmm0
0x18001746f  mov     rax, [rsp+2C8h+var_140]
0x180017477  test    rax, rax
0x18001747a  jnz     loc_180017712
0x180017480  lea     r9, [rsp+2C8h+var_B0]
0x180017488  mov     r8, qword ptr [rsp+2C8h+var_C0+8]
0x180017490  mov     rdx, rdi
0x180017493  lea     rcx, [rsp+2C8h+var_1C0]
0x18001749b  mov     rax, [rdi+38h]
0x18001749f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174a4  jmp     short loc_1800174BA
0x1800174a6  cmp     eax, 0C00000FDh
0x1800174ab  jnz     short loc_1800174B2
0x1800174ad  call    RtlResetStackOverflow
0x1800174b2  xor     r12d, r12d
0x1800174b5  mov     rbx, [rsp+2C8h+var_258]
0x1800174ba  test    [rsp+2C8h+var_174], 4
0x1800174c2  movzx   eax, [rsp+2C8h+var_287]
0x1800174c7  mov     ecx, 1
0x1800174cc  cmovnz  eax, ecx
0x1800174cf  mov     [rsp+2C8h+var_287], al
0x1800174d3  cmp     [rsp+2C8h+var_178], 4
0x1800174db  setz    sil
0x1800174df  mov     [rsp+2C8h+var_281], sil
0x1800174e4  lea     rcx, [rsp+2C8h+var_1C0]; void *
0x1800174ec  call    TppCallbackEpilog
0x1800174f1  jmp     short loc_18001750C
0x1800174f3  cmp     eax, 0C00000FDh
0x1800174f8  jnz     short loc_1800174FF
0x1800174fa  call    RtlResetStackOverflow
0x1800174ff  xor     r12d, r12d
0x180017502  mov     rbx, [rsp+2C8h+var_258]
0x180017507  movzx   esi, [rsp+2C8h+var_281]
0x18001750c  mov     [rsp+2C8h+var_1D8], r12
0x180017514  cmp     [rsp+2C8h+var_287], 0
0x180017519  jnz     loc_180017BC9
0x18001751f  test    rbx, rbx
0x180017522  jz      short loc_18001752E
0x180017524  mov     ecx, [rbx+1B8h]
0x18001752a  test    ecx, ecx
0x18001752c  jnz     short loc_180017535
0x18001752e  mov     ecx, ds:7FFE03C0h
0x180017535  mov     rax, [rsp+2C8h+var_238]
0x18001753d  cmp     [rax], ecx
0x18001753f  jz      short loc_18001755B
0x180017541  lea     rcx, [rbx+48h]
0x180017545  call    RtlAcquireSRWLockExclusive
0x18001754a  mov     rcx, rbx
0x18001754d  call    TppAdjustRunningThreadGoalWithLock
0x180017552  lea     rcx, [rbx+48h]
0x180017556  call    RtlReleaseSRWLockExclusive
0x18001755b  mov     [rsp+2C8h+var_268], r12
0x180017560  prefetchw byte ptr [rbx+8]
0x180017564  mov     rax, [rbx+8]
0x180017568  mov     [rsp+2C8h+var_268], rax
  ... truncated ...
```
