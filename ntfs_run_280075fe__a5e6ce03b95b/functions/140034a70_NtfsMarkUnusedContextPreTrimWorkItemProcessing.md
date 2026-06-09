# NtfsMarkUnusedContextPreTrimWorkItemProcessing

- ea: `0x140034a70`
- end: `0x14003567e`
- name: `NtfsMarkUnusedContextPreTrimWorkItemProcessing`
- size: `3086`
- prototype: ``
- caller_count: `0`
- callee_count: `25`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x14000549c`
- `0x1400054e8`
- `0x140007ea0`
- `0x140008740`
- `0x1400117e0`
- `0x140012ab0`
- `0x140012b50`
- `0x140016ea0`
- `0x140017030`
- `0x140034a70`
- `0x14003b914`
- `0x14003c184`
- `0x14003c210`
- `0x14004062c`
- `0x140040d48`
- `0x140044f7c`
- `0x140059250`
- `0x1400596c0`
- `0x1400cb8c4`
- `0x1400cbe04`
- `0x140223224`
- `0x14022b9dc`
- `0x1402434fc`
- `0x140243a24`
- `0x140251f2c`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140035207`
- `ntoskrnl!IoFreeIrp` at `0x140035207`
- `ntoskrnl!KeSetEvent` at `0x140035419`
- `ntoskrnl!KeSetEvent` at `0x140035419`
- `ntoskrnl!IoSetActivityIdThread` at `0x140034d68`
- `ntoskrnl!IoSetActivityIdThread` at `0x140034d68`
- `ntoskrnl!IoClearActivityIdThread` at `0x14003529c`
- `ntoskrnl!IoClearActivityIdThread` at `0x14003529c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140034c2e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140034c2e`
- `ntoskrnl!KeReleaseSpinLock` at `0x140034ce4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035622`
- `ntoskrnl!KeReleaseSpinLock` at `0x140034ce4`
- `ntoskrnl!KeReleaseSpinLock` at `0x140035622`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400350dd`
- `ntoskrnl!PsGetCurrentProcessId` at `0x1400350dd`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003503e`
- `ntoskrnl!KeWaitForSingleObject` at `0x14003503e`
- `ntoskrnl!KeInitializeEvent` at `0x140034f33`
- `ntoskrnl!KeInitializeEvent` at `0x140034f33`
- `HAL!KeQueryPerformanceCounter` at `0x140034f41`
- `HAL!KeQueryPerformanceCounter` at `0x14003504c`
- `HAL!KeQueryPerformanceCounter` at `0x1400355a1`
- `HAL!KeQueryPerformanceCounter` at `0x1400355c2`
- `HAL!KeQueryPerformanceCounter` at `0x140034f41`
- `HAL!KeQueryPerformanceCounter` at `0x14003504c`
- `HAL!KeQueryPerformanceCounter` at `0x1400355a1`
- `HAL!KeQueryPerformanceCounter` at `0x1400355c2`

## pseudocode

```c
void __fastcall NtfsMarkUnusedContextPreTrimWorkItemProcessing(__int64 a1)
{
  int v1; // r14d
  int v2; // r12d
  __int64 v3; // rdi
  __int64 v4; // r15
  unsigned int v5; // r13d
  char v6; // r14
  __int64 v7; // rbx
  PVOID *v8; // rsi
  KIRQL v9; // al
  PVOID *v10; // rdx
  PVOID *v11; // rcx
  PVOID **v12; // r8
  PVOID **v13; // r9
  __int128 v14; // rax
  _QWORD *v15; // rsi
  _QWORD *v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // r14
  __int64 v19; // rcx
  _QWORD *v20; // rax
  _QWORD *SmallMarkUnusedContext; // rax
  __int64 v22; // rcx
  _QWORD *v23; // rbx
  unsigned int *Src; // r15
  char *v25; // rbx
  char *v26; // r14
  LARGE_INTEGER v27; // rbx
  int v28; // r9d
  unsigned int v29; // eax
  __int64 v30; // rcx
  int v31; // r14d
  LARGE_INTEGER v32; // rax
  char v33; // cl
  __int64 v34; // r9
  IRP *v35; // r13
  __int64 v36; // r12
  __int64 v37; // r15
  __m128i v38; // xmm0
  unsigned int CurrentProcessId; // eax
  __int64 v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rbx
  _QWORD *v43; // rax
  _QWORD *v44; // rax
  __int64 v45; // rdx
  __int64 v46; // r8
  __int64 v47; // rax
  __int64 v48; // rcx
  unsigned int v49; // r14d
  __int64 v50; // rax
  __int128 v51; // rax
  LARGE_INTEGER PerformanceCounter; // rbx
  LARGE_INTEGER v53; // rax
  unsigned int v54; // et2
  __int64 v55; // r8
  __int64 v56; // rcx
  int Timeout; // [rsp+20h] [rbp-E0h]
  SIZE_T NumberOfBytes; // [rsp+38h] [rbp-C8h]
  char v59; // [rsp+60h] [rbp-A0h]
  char v60; // [rsp+61h] [rbp-9Fh]
  unsigned int v61; // [rsp+64h] [rbp-9Ch]
  unsigned int v62; // [rsp+68h] [rbp-98h]
  __int128 v63; // [rsp+70h] [rbp-90h] BYREF
  __int64 v64; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+88h] [rbp-78h] BYREF
  PVOID *v66; // [rsp+90h] [rbp-70h] BYREF
  __int128 v67; // [rsp+98h] [rbp-68h] BYREF
  PVOID Entry[2]; // [rsp+A8h] [rbp-58h] BYREF
  PIRP Irp; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v70; // [rsp+C0h] [rbp-40h]
  __int64 v71; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v72; // [rsp+D0h] [rbp-30h]
  struct _KEVENT Event; // [rsp+D8h] [rbp-28h] BYREF
  _OWORD v74[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v75; // [rsp+110h] [rbp+10h]
  __int128 v76; // [rsp+118h] [rbp+18h] BYREF
  __int64 v77; // [rsp+128h] [rbp+28h]
  _DWORD v78[164]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v79[528]; // [rsp+3C0h] [rbp+2C0h] BYREF

  v1 = *(_DWORD *)(a1 + 480);
  v2 = 0;
  LODWORD(v65) = 0;
  v3 = a1;
  v61 = (unsigned int)(v1 + 0x40000000) >> *(_DWORD *)(a1 + 488);
  Irp = 0;
  v64 = 0;
  v63 = 0;
  v4 = 0;
  v70 = 0;
  v67 = 0;
  v77 = 0;
  *(_OWORD *)Entry = 0;
  v75 = 0;
  memset(&Event, 0, sizeof(Event));
  v76 = 0;
  memset(v74, 0, sizeof(v74));
  memset(v78, 0, sizeof(v78));
  memset(v79, 0, 0x204u);
  v62 = 0;
  v5 = 0;
  v59 = 1;
  if ( (dword_1400956BC & 1) != 0 || !*(_QWORD *)(v3 + 8144) || (v6 = 1, (*(_DWORD *)(v3 + 8164) & 2) == 0) )
    v6 = 0;
  v60 = v6;
  if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
    McTemplateU0p_EtwWriteTransfer(1, delnotify_c1598, v3);
  *((_QWORD *)&v63 + 1) = &v63;
  *(_QWORD *)&v63 = &v63;
  *((_QWORD *)&v67 + 1) = &v67;
  *(_QWORD *)&v67 = &v67;
  Entry[1] = Entry;
  Entry[0] = Entry;
  v7 = NtfsInitializeTopLevelIrp(v74, 0, v3);
  v66 = (PVOID *)v78;
  memset(v78, 0, sizeof(v78));
  if ( !(unsigned int)NtfsInitializeIrpContextInternal(0, 1, 0, (__int64 *)&v66) )
    *((_WORD *)v66 + 1) = 656;
  NtfsSetIrpContextVcb(v78, v3);
  NtfsUpdateIrpContextWithTopLevel(v78, v7);
  v78[3] |= 0x10001u;
  v8 = (PVOID *)&v67;
  if ( !v6 )
    v8 = Entry;
  v66 = v8;
LABEL_12:
  v9 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 1752));
  v10 = (PVOID *)(v3 + 1760);
  v11 = *(PVOID **)(v3 + 1760);
  if ( v11 != (PVOID *)(v3 + 1760) )
  {
    if ( v11[1] != v10
      || (v12 = *(PVOID ***)(v3 + 1768), *v12 != v10)
      || (*v12 = v11, v11[1] = v12, *((PVOID **)*v8 + 1) != v8)
      || (v13 = (PVOID **)v8[1], *v13 != v8)
      || *((PVOID **)*v11 + 1) != v11
      || *v12 != v11 )
    {
LABEL_154:
      __fastfail(3u);
    }
    *v13 = v11;
    v8[1] = v11[1];
    *(_QWORD *)v11[1] = v8;
    v11[1] = v13;
    *(_QWORD *)(v3 + 1768) = v10;
    *v10 = v10;
  }
  if ( (__int128 *)v67 != &v67 || Entry[0] != Entry || (__int128 *)v63 != &v63 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 1752), v9);
    if ( (__int128 *)v67 != &v67 )
      NtfsUpdateSmartTrimState(v78, &v67, Entry, v79, Timeout);
    while ( 1 )
    {
      v15 = Entry[0];
      if ( Entry[0] == Entry )
      {
        if ( (__int128 *)v63 != &v63 )
        {
          BYTE8(v14) = 1;
          v59 = NtfsMarkUnusedContextPostTrimProcessing(&v63, *((_QWORD *)&v14 + 1));
          v5 = 0;
          v62 = 0;
          v4 = 0;
          v64 = 0;
        }
        v8 = v66;
        if ( v60 )
        {
          PerformanceCounter = KeQueryPerformanceCounter(0);
          NtfsEvalSmartTrimState(v78, v79);
          v53 = KeQueryPerformanceCounter(0);
          v54 = HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors;
          *(_QWORD *)(704LL * v54 + *(_QWORD *)(v3 + 808) + 632) += v53.QuadPart - PerformanceCounter.QuadPart;
          memset(v79, 0, 0x204u);
        }
        goto LABEL_12;
      }
      v3 = *((_QWORD *)Entry[0] + 2);
      if ( *((_QWORD *)Entry[0] + 5) == *(_QWORD *)(*((_QWORD *)Entry[0] + 3) + 48LL) )
      {
        v16 = (_QWORD *)*((_QWORD *)Entry[0] + 6);
        if ( v16 )
        {
          *((_QWORD *)&v76 + 1) = *v16;
          v77 = v16[1];
          *(_QWORD *)&v76 = (char *)&v76 + 8;
        }
        else
        {
          *(_QWORD *)&v76 = 0;
        }
        v70 = IoSetActivityIdThread(v76);
        if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
        {
          Timeout = 24;
          McTemplateK0pq_EtwWriteTransfer(v17, WORKITEM_START, v76);
        }
      }
      _InterlockedAdd((volatile signed __int32 *)(v3 + 1536), 1u);
      if ( *(_BYTE *)(v3 + 5521)
        || (dword_1400956B8 & 0x20000) == 0 && *(_DWORD *)(v3 + 1516)
        || (*(_DWORD *)(v3 + 4) & 0x21) != 1
        || !*(_BYTE *)(v3 + 1545) && *(_QWORD *)(v3 + 1584) && MEMORY[0xFFFFF78000000320] >= *(_QWORD *)(v3 + 1584) )
      {
        goto LABEL_102;
      }
      v18 = *(unsigned int *)(v3 + 1532);
      if ( v15[5] > v18 || *(_DWORD *)(v15[4] + 24LL) > *(_DWORD *)(v3 + 1528) )
      {
        SmallMarkUnusedContext = NtfsAllocateSmallMarkUnusedContext();
        v23 = SmallMarkUnusedContext;
        if ( !SmallMarkUnusedContext )
        {
          if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000) != 0 )
            McTemplateU0pp_EtwWriteTransfer(v22, delnotify_c1820, v3, v15);
LABEL_102:
          v30 = *v15;
          if ( *(_QWORD **)(*v15 + 8LL) != v15 )
            goto LABEL_154;
          v44 = (_QWORD *)v15[1];
          if ( (_QWORD *)*v44 != v15 )
            goto LABEL_154;
          *v44 = v30;
          *(_QWORD *)(v30 + 8) = v44;
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal(0, 3221225473LL, 3737593);
          v31 = -1073741823;
          if ( !*(_BYTE *)(v3 + 5521) )
          {
            v30 = HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors;
            v45 = *(_QWORD *)(v3 + 808);
            v46 = 704 * v30;
            LOBYTE(v30) = *(_BYTE *)(v3 + 488);
            *(_QWORD *)(v46 + v45 + 568) += v15[5] << v30;
            ++*(_QWORD *)(v46 + v45 + 560);
          }
          goto LABEL_91;
        }
        NtfsTransferMaxDataSetRanges((unsigned int)v18, v15, SmallMarkUnusedContext);
        if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          McTemplateU0ppp_EtwWriteTransfer(v19, (unsigned int)delnotify_c1805, v3, (_DWORD)v23, (char)v15);
        v15 = v23;
      }
      else
      {
        v19 = *v15;
        if ( *(_QWORD **)(*v15 + 8LL) != v15 )
          goto LABEL_154;
        v20 = (_QWORD *)v15[1];
        if ( (_QWORD *)*v20 != v15 )
          goto LABEL_154;
        *v20 = v19;
        *(_QWORD *)(v19 + 8) = v20;
      }
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        McTemplateU0pp_EtwWriteTransfer(v19, delnotify_c1843, v3, v15);
      Src = (unsigned int *)v15[4];
      if ( dword_140092174
        && (unsigned __int8)(byte_140092178 - 1) > 3u
        && (qword_140092160 & 0x100000) != 0
        && (qword_140092168 & 0x100000) == qword_140092168 )
      {
        v25 = (char *)Src + Src[5];
        v26 = &v25[Src[6]];
        while ( v25 < v26 )
        {
          if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
            McTemplateU0ppdii_EtwWriteTransfer(
              v19,
              (unsigned int)delnotify_c1884,
              v3,
              (_DWORD)v15,
              v2++,
              *(_QWORD *)v25,
              *((_QWORD *)v25 + 1));
          v25 += 16;
        }
        v2 = 0;
      }
      KeInitializeEvent(&Event, NotificationEvent, 0);
      v27 = KeQueryPerformanceCounter(0);
      LODWORD(NumberOfBytes) = Src[6] + Src[5];
      v29 = NtfsDeviceIoControlAsync3(
              0,
              *(_QWORD *)(v3 + 224),
              v3,
              v28,
              (__int64)&NtfsAsyncSendUnusedClustersHintCompletionRoutine,
              (__int64)&Event,
              Src,
              NumberOfBytes,
              0,
              3,
              (__int64)&v65,
              (__int64)&Irp);
      LOBYTE(v30) = NtfsStatusDebugFlags;
      v31 = v29;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_72;
      if ( !v29 )
        goto LABEL_73;
      if ( v29 == 294 )
        goto LABEL_73;
      v30 = v29 - 298;
      if ( (unsigned int)v30 <= 1 )
        goto LABEL_73;
      if ( v29 >= 0xFFFFFFED )
        goto LABEL_72;
      if ( v29 == -1073741802 || v29 == -2147483642 || v29 == -1073741807 )
      {
LABEL_98:
        if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          McTemplateU0ppd_EtwWriteTransfer(v30, (unsigned int)delnotify_c2012, v3, (_DWORD)v15, v31);
        goto LABEL_90;
      }
      if ( v29 != 259 )
        break;
LABEL_73:
      if ( (_DWORD)v65 == 259 )
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v32 = KeQueryPerformanceCounter(0);
      v33 = *(_BYTE *)(v3 + 488);
      v34 = v15[5];
      v35 = Irp;
      v72 = (unsigned __int64)Src[6] >> 4;
      v36 = *(_QWORD *)(v3 + 808);
      v37 = 704LL * (HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors);
      v71 = v34 << v33;
      v38 = _mm_loadu_si128((const __m128i *)(v37 + v36 + 512));
      *(_QWORD *)(v37 + v36 + 528) += v34 << v33;
      *(__m128i *)(v37 + v36 + 512) = _mm_add_epi64(
                                        _mm_unpacklo_epi64(
                                          (__m128i)1uLL,
                                          (__m128i)(unsigned __int64)(v32.QuadPart - v27.QuadPart)),
                                        v38);
      if ( *(_BYTE *)(v3 + 10496) )
      {
        CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
        NtfsIoPerfCollectTrimData(v3, (_DWORD)v35, CurrentProcessId, 20, v27.QuadPart, v72, v71);
      }
      v40 = 704LL * (HIDWORD(KeGetPcr()[1].LockArray) % NtfsNumberProcessors);
      v41 = *(_QWORD *)(v3 + 808);
      if ( *(__int64 *)(v37 + v36 + 528) >= 0
        && *(__int64 *)(v37 + v36 + 520) >= 0
        && *(__int64 *)(v37 + v36 + 512) >= 0
        && *(__int64 *)(v40 + v41 + 600) >= 0
        && *(__int64 *)(v40 + v41 + 616) >= 0
        && *(__int64 *)(v40 + v41 + 624) >= 0
        && *(__int64 *)(v40 + v41 + 632) >= 0
        && *(__int64 *)(v40 + v41 + 640) >= 0 )
      {
        v2 = 0;
      }
      else
      {
        ++*(_DWORD *)(v40 + v41 + 612);
        *(_QWORD *)(v37 + v36 + 528) = 0;
        *(_QWORD *)(v37 + v36 + 520) = 0;
        *(_QWORD *)(v37 + v36 + 512) = 0;
        v2 = 0;
        *(_QWORD *)(v40 + v41 + 600) = 0;
        *(_DWORD *)(v40 + v41 + 608) = 0;
        *(_QWORD *)(v40 + v41 + 616) = 0;
        *(_QWORD *)(v40 + v41 + 624) = 0;
        *(_QWORD *)(v40 + v41 + 632) = 0;
        *(_QWORD *)(v40 + v41 + 640) = 0;
      }
      if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
        McTemplateU0ppp_EtwWriteTransfer(v41, (unsigned int)delnotify_c1999, v3, (_DWORD)v15, (char)v35);
      IoFreeIrp(v35);
      v5 = v62;
      Irp = 0;
LABEL_90:
      v4 = v64;
LABEL_91:
      v42 = v15[5];
      _InterlockedDecrement((volatile signed __int32 *)(v3 + 1536));
      if ( v15[3] )
      {
        if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          McTemplateU0pp_EtwWriteTransfer(v30, delnotify_c2060, v3, v15);
        v43 = (_QWORD *)*((_QWORD *)&v63 + 1);
        if ( **((__int128 ***)&v63 + 1) != &v63 )
          goto LABEL_154;
        v15[1] = *((_QWORD *)&v63 + 1);
        *v15 = &v63;
        *v43 = v15;
        *((_QWORD *)&v63 + 1) = v15;
        if ( (Microsoft_Windows_NtfsEnableBits & 0x8000000) != 0 )
        {
          Timeout = 24;
          McTemplateK0pq_EtwWriteTransfer(&v63, WORKITEM_COMPLETE, v76);
        }
        IoClearActivityIdThread(v70);
      }
      else
      {
        if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40) != 0 )
          McTemplateU0pp_EtwWriteTransfer(v30, delnotify_c2077, v3, v15);
        NtfsFreeMarkUnusedContext(v15);
        v15 = 0;
      }
      v4 += v42;
      v64 = v4;
      if ( v31 < 0 && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x100000) != 0 )
      {
        if ( v15 && (v47 = v15[3]) != 0 )
          v48 = *(_QWORD *)(v47 + 48);
        else
          LODWORD(v48) = -1;
        McTemplateU0pdpi_EtwWriteTransfer(v48, DWORD2(v14), v3, v31, (char)v15, v48);
      }
      if ( !*(_DWORD *)(v3 + 1536) && _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 1540), 0, 1) == 1 )
        KeSetEvent((PRKEVENT)(v3 + 1552), 0, 0);
      v62 = ++v5;
      if ( !v59 )
        goto LABEL_133;
      if ( (__int128 *)v63 == &v63 )
        goto LABEL_132;
      if ( *(_BYTE *)(v3 + 1545) || v5 >= 0x200 )
      {
LABEL_133:
        v49 = v61;
        goto LABEL_134;
      }
      v49 = v61;
      if ( v4 >= v61
        || ((__int64)(*(_QWORD *)(v3 + 304) - *(_QWORD *)(v3 + 6368) - *(_QWORD *)(v3 + 328)) <= 0
          ? (v50 = 0)
          : (v50 = *(_QWORD *)(v3 + 304) - *(_QWORD *)(v3 + 6368) - *(_QWORD *)(v3 + 328)),
            (*((_QWORD *)&v14 + 1) = (v50 >> 63) & 3, v4 > v50 / 4) || v15 && (*(_DWORD *)(v15[3] + 56LL) & 4) != 0) )
      {
LABEL_134:
        BYTE8(v14) = *(_BYTE *)(v3 + 1545)
                  || v5 >= 0x400
                  || v4 >= 2 * v49
                  || ((__int64)(*(_QWORD *)(v3 + 304) - *(_QWORD *)(v3 + 6368) - *(_QWORD *)(v3 + 328)) <= 0
                    ? (*(_QWORD *)&v51 = 0)
                    : (*(_QWORD *)&v51 = *(_QWORD *)(v3 + 304) - *(_QWORD *)(v3 + 6368) - *(_QWORD *)(v3 + 328)),
                      (v14 = (__int64)v51, v4 > (__int64)v51 / 2) || v15 && (*(_DWORD *)(v15[3] + 56LL) & 4) != 0);
        v59 = NtfsMarkUnusedContextPostTrimProcessing(&v63, *((_QWORD *)&v14 + 1));
        if ( v59 )
        {
          v5 = 0;
          v62 = 0;
          v4 = 0;
          v64 = 0;
        }
      }
      else
      {
LABEL_132:
        *(_BYTE *)(v3 + 1545) = 0;
      }
    }
    if ( v29 == -2147483643 || v29 == -1073741608 )
      goto LABEL_98;
    NtfsStatusTraceAndDebugInternal(0, v29, 3737469);
LABEL_72:
    if ( v31 < 0 )
      goto LABEL_98;
    goto LABEL_73;
  }
  *(_BYTE *)(v3 + 1808) = 0;
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 1752), v9);
  v78[3] &= ~0x10000u;
  NtfsCleanupIrpContext((__int64)v78, 0, v55);
  if ( (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x200000) != 0 )
    McTemplateU0_EtwWriteTransfer(v56, delnotify_c2230);
}

```

## disassembly

```asm
0x140034a70  push    rbp
0x140034a72  push    rbx
0x140034a73  push    rsi
0x140034a74  push    rdi
0x140034a75  push    r12
0x140034a77  push    r13
0x140034a79  push    r14
0x140034a7b  push    r15
0x140034a7d  lea     rbp, [rsp-4E8h]
0x140034a85  sub     rsp, 5E8h
0x140034a8c  mov     rax, cs:__security_cookie
0x140034a93  xor     rax, rsp
0x140034a96  mov     [rbp+520h+var_50], rax
0x140034a9d  mov     r14d, [rcx+1E0h]
0x140034aa4  xorps   xmm0, xmm0
0x140034aa7  xor     r12d, r12d
0x140034aaa  xorps   xmm1, xmm1
0x140034aad  xor     eax, eax
0x140034aaf  mov     dword ptr [rbp+520h+var_598], r12d
0x140034ab3  mov     rdi, rcx
0x140034ab6  mov     [rbp+520h+Event.Header.WaitListHead.Blink], rax
0x140034aba  mov     ecx, [rcx+1E8h]
0x140034ac0  add     r14d, 40000000h
0x140034ac7  shr     r14d, cl
0x140034aca  mov     esi, 290h
0x140034acf  lea     rcx, [rbp+520h+var_4F0]; void *
0x140034ad3  mov     [rsp+620h+var_5BC], r14d
0x140034ad8  mov     r8d, esi; Size
0x140034adb  mov     [rbp+520h+Irp], r12
0x140034adf  xor     edx, edx; Val
0x140034ae1  mov     [rbp+520h+var_5A0], r12
0x140034ae5  movups  [rsp+620h+var_5B0], xmm0
0x140034aea  mov     r15d, r12d
0x140034aed  mov     [rbp+520h+var_560], r12
0x140034af1  movups  [rbp+520h+var_588], xmm1
0x140034af5  mov     [rbp+520h+var_4F8], rax
0x140034af9  movups  xmmword ptr [rbp+520h+Entry], xmm0
0x140034afd  mov     [rbp+520h+var_510], rax
0x140034b01  movups  xmmword ptr [rbp+520h+Event.Header], xmm0
0x140034b05  movups  [rbp+520h+var_508], xmm0
0x140034b09  movups  [rbp+520h+var_530], xmm1
0x140034b0d  movups  [rbp+520h+var_520], xmm1
0x140034b11  call    memset
0x140034b16  xor     edx, edx; Val
0x140034b18  lea     rcx, [rbp+520h+var_260]; void *
0x140034b1f  mov     r8d, 204h; Size
0x140034b25  call    memset
0x140034b2a  mov     eax, cs:dword_1400956BC
0x140034b30  lea     ecx, [r12+1]
0x140034b35  mov     [rsp+620h+var_5B8], r12d
0x140034b3a  mov     r13d, r12d
0x140034b3d  mov     [rsp+620h+var_5C0], cl
0x140034b41  test    cl, al
0x140034b43  jnz     short loc_140034B5B
0x140034b45  cmp     [rdi+1FD0h], r12
0x140034b4c  jz      short loc_140034B5B
0x140034b4e  mov     eax, [rdi+1FE4h]
0x140034b54  mov     r14b, cl
0x140034b57  test    al, 2
0x140034b59  jnz     short loc_140034B5E
0x140034b5b  mov     r14b, r12b
0x140034b5e  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x140034b65  mov     [rsp+620h+var_5BF], r14b
0x140034b6a  jz      short loc_140034B7B
0x140034b6c  mov     r8, rdi
0x140034b6f  lea     rdx, delnotify_c1598
0x140034b76  call    McTemplateU0p_EtwWriteTransfer
0x140034b7b  lea     rax, [rsp+620h+var_5B0]
0x140034b80  mov     r8, rdi
0x140034b83  mov     qword ptr [rsp+620h+var_5B0+8], rax
0x140034b88  lea     rcx, [rbp+520h+var_530]
0x140034b8c  lea     rax, [rsp+620h+var_5B0]
0x140034b91  xor     edx, edx
0x140034b93  mov     qword ptr [rsp+620h+var_5B0], rax
0x140034b98  lea     rax, [rbp+520h+var_588]
0x140034b9c  mov     qword ptr [rbp+520h+var_588+8], rax
0x140034ba0  lea     rax, [rbp+520h+var_588]
0x140034ba4  mov     qword ptr [rbp+520h+var_588], rax
0x140034ba8  lea     rax, [rbp+520h+Entry]
0x140034bac  mov     [rbp+520h+Entry+8], rax
0x140034bb0  lea     rax, [rbp+520h+Entry]
0x140034bb4  mov     [rbp+520h+Entry], rax
0x140034bb8  call    NtfsInitializeTopLevelIrp
0x140034bbd  mov     rbx, rax
0x140034bc0  lea     rcx, [rbp+520h+var_4F0]; void *
0x140034bc4  lea     rax, [rbp+520h+var_4F0]
0x140034bc8  mov     r8, rsi; Size
0x140034bcb  xor     edx, edx; Val
0x140034bcd  mov     [rbp+520h+var_590], rax
0x140034bd1  call    memset
0x140034bd6  lea     r9, [rbp+520h+var_590]
0x140034bda  xor     r8d, r8d
0x140034bdd  mov     dl, 1
0x140034bdf  xor     ecx, ecx; Irp
0x140034be1  call    NtfsInitializeIrpContextInternal
0x140034be6  test    eax, eax
0x140034be8  jnz     short loc_140034BF2
0x140034bea  mov     rax, [rbp+520h+var_590]
0x140034bee  mov     [rax+2], si
0x140034bf2  mov     rdx, rdi
0x140034bf5  lea     rcx, [rbp+520h+var_4F0]
0x140034bf9  call    NtfsSetIrpContextVcb
0x140034bfe  mov     rdx, rbx
0x140034c01  lea     rcx, [rbp+520h+var_4F0]
0x140034c05  call    NtfsUpdateIrpContextWithTopLevel
0x140034c0a  or      [rbp+520h+var_4E4], 10001h
0x140034c11  lea     rsi, [rbp+520h+var_588]
0x140034c15  test    r14b, r14b
0x140034c18  lea     rax, [rbp+520h+Entry]
0x140034c1c  cmovz   rsi, rax
0x140034c20  mov     [rbp+520h+var_590], rsi
0x140034c24  lea     rbx, [rdi+6D8h]
0x140034c2b  mov     rcx, rbx; SpinLock
0x140034c2e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140034c35  nop     dword ptr [rax+rax+00h]
0x140034c3a  lea     rdx, [rdi+6E0h]
0x140034c41  mov     r10b, al
0x140034c44  mov     rcx, [rdx]
0x140034c47  cmp     rcx, rdx
0x140034c4a  jz      short loc_140034CBA
0x140034c4c  cmp     [rcx+8], rdx
0x140034c50  jnz     loc_140035677
0x140034c56  mov     r8, [rdx+8]
0x140034c5a  cmp     [r8], rdx
0x140034c5d  jnz     loc_140035677
0x140034c63  mov     [r8], rcx
0x140034c66  mov     [rcx+8], r8
0x140034c6a  mov     rax, [rsi]
0x140034c6d  cmp     [rax+8], rsi
0x140034c71  jnz     loc_140035677
0x140034c77  mov     r9, [rsi+8]
0x140034c7b  cmp     [r9], rsi
0x140034c7e  jnz     loc_140035677
0x140034c84  mov     rax, [rcx]
0x140034c87  cmp     [rax+8], rcx
0x140034c8b  jnz     loc_140035677
0x140034c91  cmp     [r8], rcx
0x140034c94  jnz     loc_140035677
0x140034c9a  mov     [r9], rcx
0x140034c9d  mov     rax, [rcx+8]
0x140034ca1  mov     [rsi+8], rax
0x140034ca5  mov     rax, [rcx+8]
0x140034ca9  mov     [rax], rsi
0x140034cac  mov     [rcx+8], r9
0x140034cb0  mov     [rdi+6E8h], rdx
0x140034cb7  mov     [rdx], rdx
0x140034cba  lea     rax, [rbp+520h+var_588]
0x140034cbe  cmp     qword ptr [rbp+520h+var_588], rax
0x140034cc2  jnz     short loc_140034CDE
0x140034cc4  lea     rax, [rbp+520h+Entry]
0x140034cc8  cmp     [rbp+520h+Entry], rax
0x140034ccc  jnz     short loc_140034CDE
0x140034cce  lea     rax, [rsp+620h+var_5B0]
0x140034cd3  cmp     qword ptr [rsp+620h+var_5B0], rax
0x140034cd8  jz      loc_140035615
0x140034cde  mov     dl, r10b; NewIrql
0x140034ce1  mov     rcx, rbx; SpinLock
0x140034ce4  call    cs:__imp_KeReleaseSpinLock
0x140034ceb  nop     dword ptr [rax+rax+00h]
0x140034cf0  lea     rax, [rbp+520h+var_588]
0x140034cf4  cmp     qword ptr [rbp+520h+var_588], rax
0x140034cf8  jz      short loc_140034D12
0x140034cfa  lea     r9, [rbp+520h+var_260]
0x140034d01  lea     r8, [rbp+520h+Entry]
0x140034d05  lea     rdx, [rbp+520h+var_588]
0x140034d09  lea     rcx, [rbp+520h+var_4F0]
0x140034d0d  call    NtfsUpdateSmartTrimState
0x140034d12  mov     ebx, 1
0x140034d17  mov     rsi, [rbp+520h+Entry]
0x140034d1b  lea     rax, [rbp+520h+Entry]
0x140034d1f  cmp     rsi, rax
0x140034d22  jz      loc_140035565
0x140034d28  mov     rax, [rsi+18h]
0x140034d2c  mov     rdi, [rsi+10h]
0x140034d30  mov     rcx, [rax+30h]
0x140034d34  cmp     [rsi+28h], rcx
0x140034d38  jnz     short loc_140034D99
0x140034d3a  mov     rcx, [rsi+30h]
0x140034d3e  test    rcx, rcx
0x140034d41  jz      short loc_140034D5C
0x140034d43  mov     rax, [rcx]
0x140034d46  mov     qword ptr [rbp+520h+var_508+8], rax
0x140034d4a  mov     rax, [rcx+8]
0x140034d4e  mov     [rbp+520h+var_4F8], rax
0x140034d52  lea     rax, [rbp+520h+var_508+8]
0x140034d56  mov     qword ptr [rbp+520h+var_508], rax
0x140034d5a  jmp     short loc_140034D60
0x140034d5c  mov     qword ptr [rbp+520h+var_508], r12
0x140034d60  mov     rax, qword ptr [rbp+520h+var_508]
0x140034d64  mov     rcx, qword ptr [rbp+520h+var_508]
0x140034d68  call    cs:__imp_IoSetActivityIdThread
0x140034d6f  nop     dword ptr [rax+rax+00h]
0x140034d74  test    byte ptr cs:Microsoft_Windows_NtfsEnableBits+3, 8
0x140034d7b  mov     [rbp+520h+var_560], rax
0x140034d7f  jz      short loc_140034D99
0x140034d81  mov     r8, qword ptr [rbp+520h+var_508]
0x140034d85  lea     rdx, WORKITEM_START
0x140034d8c  mov     dword ptr [rsp+620h+Timeout], 18h
0x140034d94  call    McTemplateK0pq_EtwWriteTransfer
0x140034d99  lock add [rdi+600h], ebx
0x140034da0  cmp     [rdi+1591h], r12b
0x140034da7  jnz     loc_1400352F6
0x140034dad  test    cs:dword_1400956B8, 20000h
0x140034db7  jnz     short loc_140034DC6
0x140034db9  cmp     [rdi+5ECh], r12d
0x140034dc0  jnz     loc_1400352F6
0x140034dc6  mov     eax, [rdi+4]
0x140034dc9  and     al, 21h
0x140034dcb  cmp     al, bl
0x140034dcd  jnz     loc_1400352F6
0x140034dd3  cmp     [rdi+609h], r12b
0x140034dda  jnz     short loc_140034DFF
0x140034ddc  cmp     [rdi+630h], r12
0x140034de3  jz      short loc_140034DFF
0x140034de5  mov     rax, 0FFFFF78000000320h
0x140034def  mov     rax, [rax]
0x140034df2  cmp     rax, [rdi+630h]
0x140034df9  jge     loc_1400352F6
0x140034dff  mov     r14d, [rdi+5FCh]
0x140034e06  cmp     [rsi+28h], r14
0x140034e0a  jg      short loc_140034E3E
0x140034e0c  mov     rcx, [rsi+20h]
0x140034e10  mov     eax, [rdi+5F8h]
0x140034e16  cmp     [rcx+18h], eax
0x140034e19  ja      short loc_140034E3E
0x140034e1b  mov     rcx, [rsi]
0x140034e1e  cmp     [rcx+8], rsi
0x140034e22  jnz     loc_140035677
0x140034e28  mov     rax, [rsi+8]
0x140034e2c  cmp     [rax], rsi
0x140034e2f  jnz     loc_140035677
0x140034e35  mov     [rax], rcx
0x140034e38  mov     [rcx+8], rax
0x140034e3c  jmp     short loc_140034E85
0x140034e3e  call    NtfsAllocateSmallMarkUnusedContext
0x140034e43  mov     rbx, rax
0x140034e46  test    rax, rax
0x140034e49  jz      loc_1400352D6
0x140034e4f  mov     r8, rax
0x140034e52  mov     rdx, rsi
0x140034e55  mov     ecx, r14d
0x140034e58  call    NtfsTransferMaxDataSetRanges
0x140034e5d  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x140034e64  jz      short loc_140034E7D
0x140034e66  mov     r9, rbx
0x140034e69  mov     [rsp+620h+Timeout], rsi
0x140034e6e  mov     r8, rdi
0x140034e71  lea     rdx, delnotify_c1805
0x140034e78  call    McTemplateU0ppp_EtwWriteTransfer
0x140034e7d  mov     rsi, rbx
0x140034e80  mov     ebx, 1
0x140034e85  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits, 40h
0x140034e8c  jz      short loc_140034EA0
0x140034e8e  mov     r9, rsi
0x140034e91  lea     rdx, delnotify_c1843
0x140034e98  mov     r8, rdi
0x140034e9b  call    McTemplateU0pp_EtwWriteTransfer
0x140034ea0  cmp     cs:dword_140092174, r12d
0x140034ea7  mov     r15, [rsi+20h]
0x140034eab  jz      short loc_140034F2A
0x140034ead  mov     al, cs:byte_140092178
0x140034eb3  sub     al, bl
0x140034eb5  cmp     al, 3
0x140034eb7  jbe     short loc_140034F2A
0x140034eb9  mov     edx, 100000h
0x140034ebe  test    cs:qword_140092160, rdx
0x140034ec5  jz      short loc_140034F2A
0x140034ec7  mov     rax, cs:qword_140092168
0x140034ece  and     rax, rdx
0x140034ed1  cmp     rax, cs:qword_140092168
0x140034ed8  jnz     short loc_140034F2A
0x140034eda  mov     ebx, [r15+14h]
0x140034ede  mov     r14d, [r15+18h]
0x140034ee2  add     rbx, r15
0x140034ee5  add     r14, rbx
0x140034ee8  cmp     rbx, r14
0x140034eeb  jnb     short loc_140034F27
0x140034eed  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+2, 20h
0x140034ef4  jz      short loc_140034F21
0x140034ef6  mov     rax, [rbx+8]
0x140034efa  lea     rdx, delnotify_c1884
0x140034f01  mov     [rsp+620h+Src], rax
0x140034f06  mov     r9, rsi
0x140034f09  mov     rax, [rbx]
0x140034f0c  mov     r8, rdi
0x140034f0f  mov     [rsp+620h+var_5F8], rax
0x140034f14  mov     dword ptr [rsp+620h+Timeout], r12d
0x140034f19  call    McTemplateU0ppdii_EtwWriteTransfer
0x140034f1e  inc     r12d
0x140034f21  add     rbx, 10h
0x140034f25  jmp     short loc_140034EE8
0x140034f27  xor     r12d, r12d
0x140034f2a  xor     r8d, r8d; State
0x140034f2d  lea     rcx, [rbp+520h+Event]; Event
0x140034f31  xor     edx, edx; Type
0x140034f33  call    cs:__imp_KeInitializeEvent
0x140034f3a  nop     dword ptr [rax+rax+00h]
0x140034f3f  xor     ecx, ecx; PerformanceFrequency
0x140034f41  call    cs:__imp_KeQueryPerformanceCounter
0x140034f48  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
