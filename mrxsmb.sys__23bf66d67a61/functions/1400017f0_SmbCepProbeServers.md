# SmbCepProbeServers

- ea: `0x1400017f0`
- end: `0x140002263`
- name: `SmbCepProbeServers`
- size: `2675`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter4)`
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x1400017f0`
- `0x140002270`
- `0x1400028d0`
- `0x140002e40`
- `0x140002f30`
- `0x140003480`
- `0x140003550`
- `0x140004360`
- `0x140013540`
- `0x1400135e0`
- `0x140014400`
- `0x140021130`
- `0x1400221e0`
- `0x140037bb8`
- `0x140038068`
- `0x1400383d0`
- `0x14003d2c4`
- `0x140044420`
- `0x140044e30`
- `0x140059ea0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001d0b`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140001d0b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001d4e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002188`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140001d4e`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140002188`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000183b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000183b`
- `ntoskrnl!KeDelayExecutionThread` at `0x14005abcc`
- `ntoskrnl!KeDelayExecutionThread` at `0x14005abcc`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001860`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001860`
- `ntoskrnl!KeBugCheckEx` at `0x140001e37`
- `ntoskrnl!KeBugCheckEx` at `0x140001e81`
- `ntoskrnl!KeBugCheckEx` at `0x140001ea7`
- `ntoskrnl!KeBugCheckEx` at `0x140001f5d`
- `ntoskrnl!KeBugCheckEx` at `0x140001f83`
- `ntoskrnl!KeBugCheckEx` at `0x140001fd8`
- `ntoskrnl!KeBugCheckEx` at `0x140001ffb`
- `ntoskrnl!KeBugCheckEx` at `0x140002057`
- `ntoskrnl!KeBugCheckEx` at `0x1400021f5`
- `ntoskrnl!KeBugCheckEx` at `0x140002217`
- `ntoskrnl!KeBugCheckEx` at `0x140002239`
- `ntoskrnl!KeBugCheckEx` at `0x14005ac42`
- `ntoskrnl!KeBugCheckEx` at `0x140001e37`
- `ntoskrnl!KeBugCheckEx` at `0x140001e81`
- `ntoskrnl!KeBugCheckEx` at `0x140001ea7`
- `ntoskrnl!KeBugCheckEx` at `0x140001f5d`
- `ntoskrnl!KeBugCheckEx` at `0x140001f83`
- `ntoskrnl!KeBugCheckEx` at `0x140001fd8`
- `ntoskrnl!KeBugCheckEx` at `0x140001ffb`
- `ntoskrnl!KeBugCheckEx` at `0x140002057`
- `ntoskrnl!KeBugCheckEx` at `0x1400021f5`
- `ntoskrnl!KeBugCheckEx` at `0x140002217`
- `ntoskrnl!KeBugCheckEx` at `0x140002239`
- `ntoskrnl!KeBugCheckEx` at `0x14005ac42`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400018db`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005ab04`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005abae`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400018db`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005ab04`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14005abae`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140001877`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140001877`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000188a`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000188a`
- `rdbss!RxNameCacheScavengeEntries` at `0x1400018e9`
- `rdbss!RxNameCacheScavengeEntries` at `0x1400018e9`
- `rdbss!RxDispatchToWorkerThread` at `0x14005aabc`
- `rdbss!RxDispatchToWorkerThread` at `0x14005aabc`

## pseudocode

```c
__int64 __fastcall SmbCepProbeServers(ULONG_PTR BugCheckParameter4)
{
  volatile LONG *v2; // rbp
  ULONG_PTR v3; // r14
  int **v4; // r8
  __int64 v5; // rax
  ULONG_PTR v6; // r13
  char v7; // si
  __int64 v8; // r9
  __int64 v9; // rdx
  __int64 v10; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  int *v14; // rcx
  _QWORD *v15; // rdx
  int *v16; // rbx
  int *v17; // r9
  _QWORD *v18; // r15
  unsigned __int64 v19; // rax
  ULONG_PTR v20; // rdi
  __int64 v21; // rax
  __int64 v22; // rax
  int *v23; // rcx
  _QWORD *v24; // rdx
  ULONG_PTR v25; // rbx
  _QWORD *v26; // rbx
  ULONG_PTR v27; // rsi
  __int64 v28; // rax
  __int64 v29; // rcx
  int *v30; // rax
  _QWORD *v31; // rdx
  ULONG_PTR FirstBindingObject; // rbx
  char v33; // bp
  _QWORD *v34; // rdx
  ULONG_PTR v35; // rdi
  __int64 v36; // rax
  __int64 v37; // rcx
  int *v38; // rax
  _QWORD *v39; // rdx
  ULONG_PTR v40; // rbx
  _QWORD *v41; // rcx
  __int64 v42; // rcx
  __int64 v43; // rax
  ULONG_PTR v44; // rdx
  int **v45; // rax
  int ***v46; // rcx
  int *v47; // r10
  _QWORD *v48; // rcx
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // r10
  __int64 v52; // r9
  __int64 v53; // r9
  int *v54; // rsi
  int *v55; // r10
  __int16 v56; // r11
  __int64 v57; // rsi
  __int64 v58; // rax
  __int64 v59; // rcx
  __int64 v60; // rax
  ULONG_PTR v61; // r14
  __int64 NextBindingObject; // rdi
  int v63; // ecx
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // rdx
  __int64 v67; // r8
  KIRQL v68; // al
  __int64 v69; // rbx
  _WORD *v70; // [rsp+30h] [rbp-68h]
  LARGE_INTEGER Interval; // [rsp+40h] [rbp-58h] BYREF
  KIRQL v72; // [rsp+A0h] [rbp+8h]
  char v73; // [rsp+A8h] [rbp+10h]
  char v74; // [rsp+B0h] [rbp+18h]
  unsigned __int64 v75; // [rsp+B8h] [rbp+20h]

  v73 = 0;
  v70 = 0;
  v74 = 0;
  v75 = MEMORY[0xFFFFF78000000008];
  ExAcquireResourceExclusiveLite(&Resource, 1u);
  if ( dword_140070940 != dword_140070938 )
  {
    v74 = 1;
    dword_140070938 = dword_140070940;
  }
  ExReleaseResourceLite(&Resource);
  v2 = (volatile LONG *)(BugCheckParameter4 + 1920);
  v72 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(BugCheckParameter4 + 1920));
  v3 = BugCheckParameter4 + 1904;
  *(_DWORD *)(BugCheckParameter4 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v5 = *(_QWORD *)(BugCheckParameter4 + 1904);
  if ( v5 == BugCheckParameter4 + 1904 )
    v6 = 0;
  else
    v6 = v5 - 32;
  v7 = 0;
  while ( 1 )
  {
    v8 = 58111;
    if ( !v6 )
      break;
    v12 = *(unsigned __int16 *)(v6 + 2);
    if ( (_WORD)v12 )
    {
      v13 = v6 + v12 + 8;
      if ( !v13 )
        goto LABEL_141;
    }
    else
    {
      v13 = 8;
    }
    v14 = *(int **)v13;
    if ( !*(_QWORD *)v13 || (v15 = *(_QWORD **)(v13 + 8)) == 0 || *((_QWORD *)v14 + 1) != v13 || *v15 != v13 )
LABEL_141:
      __fastfail(3u);
    while ( 1 )
    {
      v16 = 0;
      if ( v14 == (int *)v13 )
        break;
      if ( !v14 )
        goto LABEL_141;
      if ( !*(_QWORD *)v14 )
        goto LABEL_141;
      v4 = (int **)*((_QWORD *)v14 + 1);
      if ( !v4 || *(int **)(*(_QWORD *)v14 + 8LL) != v14 || *v4 != v14 )
        goto LABEL_141;
      v16 = v14 - 100;
      if ( *(v14 - 98) < 0 )
        KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v14 - 100), *(v14 - 98), 0);
      if ( *(_WORD *)v16 != 0xE2FF )
        break;
      v14 = *(int **)v14;
    }
    while ( v16 )
    {
      NextBindingObject = SmbCeGetNextBindingObject(v6, v16, v4, v8);
      if ( (int *)NextBindingObject == v16 )
        KeBugCheckEx(0x27u, 0x65534DF7u, v6, (ULONG_PTR)v16, BugCheckParameter4);
      if ( (int)SmbCepExpireExchangesLite(v16) > 0 )
      {
        v7 = 1;
        v70 = v16;
        v73 = 1;
      }
      v16 = (int *)NextBindingObject;
    }
    SmbCepExpireExchangesLite(v6);
    v18 = (_QWORD *)(v6 + 528);
    if ( (_QWORD *)*v18 == v18 )
    {
      v59 = *(_QWORD *)(v6 + 32);
      v6 = 0;
      if ( v59 != v3 )
        v6 = v59 - 32;
    }
    else
    {
      v19 = *(_QWORD *)(v6 + 728);
      if ( v19 && v75 >= v19 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_qZ(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            (unsigned int)WPP_948a51171ac53989b14c3e6a960354da_Traceguids,
            v6,
            v6 + 80);
        }
        SmbCeUnSuspendServerConnectionsLite(v6, 0);
      }
      if ( (*(_DWORD *)(v6 + 4) & 1) != 0 && *(_QWORD *)(v6 + 576) && !*(_DWORD *)(v6 + 608) && v74 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_948a51171ac53989b14c3e6a960354da_Traceguids, v6);
        }
        SmbCeReferenceServerEntry(v6);
        if ( RxDispatchToWorkerThread(
               (PRDBSS_DEVICE_OBJECT)BugCheckParameter4,
               NormalWorkQueue,
               (PRX_WORKERTHREAD_ROUTINE)SmbCeComputeConnectionInfo,
               (PVOID)v6) )
        {
          SmbCeDereferenceServerEntryEx(v6);
        }
      }
      if ( (_QWORD *)*v18 == v18 )
        v20 = 0;
      else
        v20 = *v18 - 392LL;
      while ( v20 )
      {
        v21 = *(unsigned __int16 *)(v20 + 2);
        if ( (_WORD)v21 )
        {
          v22 = v20 + v21 + 8;
          if ( !v22 )
            goto LABEL_141;
        }
        else
        {
          v22 = 8;
        }
        v23 = *(int **)v22;
        if ( !*(_QWORD *)v22 )
          goto LABEL_141;
        v24 = *(_QWORD **)(v22 + 8);
        if ( !v24 || *((_QWORD *)v23 + 1) != v22 || *v24 != v22 )
          goto LABEL_141;
        while ( 1 )
        {
          v25 = 0;
          if ( v23 == (int *)v22 )
            break;
          if ( !v23 )
            goto LABEL_141;
          if ( !*(_QWORD *)v23 )
            goto LABEL_141;
          v4 = (int **)*((_QWORD *)v23 + 1);
          if ( !v4 || *(int **)(*(_QWORD *)v23 + 8LL) != v23 || *v4 != v23 )
            goto LABEL_141;
          v25 = (ULONG_PTR)(v23 - 100);
          v24 = (_QWORD *)*(v23 - 98);
          if ( (int)v24 < 0 )
            KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v23 - 100), *(v23 - 98), 0);
          if ( *(_WORD *)v25 != 0xE2FF )
            break;
          v23 = *(int **)v23;
        }
        while ( v25 )
        {
          if ( *(int *)(v25 + 8) < 0 )
            KeBugCheckEx(0x27u, 0xA0001u, v25, *(int *)(v25 + 8), 0);
          SMBCE_VERIFY_LIST_ENTRY(v25 + 400, v24, v4);
          v51 = *(_QWORD *)(v25 + 400);
          v53 = v52 + 8;
          while ( 1 )
          {
            v54 = 0;
            if ( v51 == v53 )
              break;
            SMBCE_VERIFY_LIST_ENTRY(v51, v49, v50);
            v54 = v55 - 100;
            if ( *(v55 - 98) < 0 )
              KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v55 - 100), *(v55 - 98), 0);
            if ( *(_WORD *)v54 != v56 )
            {
              if ( v54 == (int *)v25 )
                KeBugCheckEx(0x27u, 0x65534D7Bu, v20, v25, BugCheckParameter4);
              break;
            }
            v51 = *(_QWORD *)v55;
          }
          if ( (int)SmbCepExpireExchangesLite(v25) > 0 )
          {
            v73 = 1;
            v70 = (_WORD *)v25;
          }
          v25 = (ULONG_PTR)v54;
        }
        v26 = *(_QWORD **)(v20 + 392);
        SmbCepExpireExchangesLite(v20);
        v20 = 0;
        if ( v26 != v18 )
          v20 = (ULONG_PTR)(v26 - 49);
      }
      if ( (_QWORD *)*v18 == v18 )
        v27 = 0;
      else
        v27 = *v18 - 392LL;
      while ( v27 )
      {
        if ( *(int *)(v27 + 12) > 5 )
        {
          v48 = *(_QWORD **)(v27 + 392);
          v27 = 0;
          if ( v48 != v18 )
            v27 = (ULONG_PTR)(v48 - 49);
        }
        else
        {
          v28 = *(unsigned __int16 *)(v27 + 2);
          if ( (_WORD)v28 )
          {
            v29 = v27 + v28 + 8;
            if ( !v29 )
              goto LABEL_141;
          }
          else
          {
            v29 = 8;
          }
          v30 = *(int **)v29;
          if ( !*(_QWORD *)v29 )
            goto LABEL_141;
          v31 = *(_QWORD **)(v29 + 8);
          if ( !v31 || *((_QWORD *)v30 + 1) != v29 || *v31 != v29 )
            goto LABEL_141;
          while ( 1 )
          {
            FirstBindingObject = 0;
            if ( v30 == (int *)v29 )
              break;
            if ( !v30 )
              goto LABEL_141;
            if ( !*(_QWORD *)v30 )
              goto LABEL_141;
            v4 = (int **)*((_QWORD *)v30 + 1);
            if ( !v4 || *(int **)(*(_QWORD *)v30 + 8LL) != v30 || *v4 != v30 )
              goto LABEL_141;
            FirstBindingObject = (ULONG_PTR)(v30 - 100);
            if ( *(v30 - 98) < 0 )
              KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v30 - 100), *(v30 - 98), 0);
            if ( *(_WORD *)FirstBindingObject != 0xE2FF )
              break;
            v30 = *(int **)v30;
          }
          v33 = 0;
          while ( FirstBindingObject )
          {
            KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(FirstBindingObject + 192));
            if ( *(_QWORD *)(FirstBindingObject + 280) == FirstBindingObject + 280
              && v75 - *(_QWORD *)(FirstBindingObject + 448) > 0x23C34600
              && *(_BYTE *)(FirstBindingObject + 441) == 1 )
            {
              KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(FirstBindingObject + 192));
              if ( !v33 )
              {
                SmbCeReferenceSessionEntry(v27);
                v33 = 1;
              }
              SmbCeReferenceBindingObject(FirstBindingObject);
              *(_DWORD *)(BugCheckParameter4 + 2352) = -1;
              ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(BugCheckParameter4 + 1920), v72);
              SmbCeSetConnectionKeepalive(FirstBindingObject, 0, 1);
              v72 = SmbCeAcquireSpinLock(BugCheckParameter4, v64, v65);
              SmbCeDereferenceBindingObject(FirstBindingObject);
              FirstBindingObject = SmbCeGetFirstBindingObjectEx(v27, 0);
            }
            else
            {
              KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(FirstBindingObject + 192));
              v43 = *(unsigned __int16 *)(v27 + 2);
              if ( (_WORD)v43 )
                v44 = v27 + v43;
              else
                v44 = 0;
              if ( *(int *)(FirstBindingObject + 8) < 0 )
                KeBugCheckEx(0x27u, 0xA0001u, FirstBindingObject, *(int *)(FirstBindingObject + 8), 0);
              v45 = (int **)(FirstBindingObject + 400);
              if ( FirstBindingObject == -400 )
                goto LABEL_141;
              v17 = *v45;
              if ( !*v45 )
                goto LABEL_141;
              v46 = *(int ****)(FirstBindingObject + 408);
              if ( !v46 || *((int ***)v17 + 1) != v45 || *v46 != v45 )
                goto LABEL_141;
              v47 = (int *)(v44 + 8);
              while ( 1 )
              {
                v4 = 0;
                if ( v17 == v47 )
                  break;
                SMBCE_VERIFY_LIST_ENTRY(v17, v44, 0);
                v4 = (int **)(v17 - 100);
                if ( *(v17 - 98) < 0 )
                  KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)v4, *(v17 - 98), 0);
                if ( *(_WORD *)v4 != 0xE2FF )
                {
                  if ( v4 == (int **)FirstBindingObject )
                    KeBugCheckEx(0x27u, 0x65534DD3u, v27, FirstBindingObject, BugCheckParameter4);
                  break;
                }
                v17 = *(int **)v17;
              }
              FirstBindingObject = (ULONG_PTR)v4;
            }
          }
          v34 = *(_QWORD **)(v27 + 392);
          if ( v34 != v18 )
            FirstBindingObject = (ULONG_PTR)(v34 - 49);
          if ( v33 )
            SmbCeDereferenceSessionEntryEx(v27);
          v27 = FirstBindingObject;
        }
      }
      if ( (_QWORD *)*v18 == v18 )
        v35 = 0;
      else
        v35 = *v18 - 392LL;
      while ( v35 )
      {
        v36 = *(unsigned __int16 *)(v35 + 2);
        if ( (_WORD)v36 )
        {
          v37 = v35 + v36 + 8;
          if ( !v37 )
            goto LABEL_141;
        }
        else
        {
          v37 = 8;
        }
        v38 = *(int **)v37;
        if ( !*(_QWORD *)v37 )
          goto LABEL_141;
        v39 = *(_QWORD **)(v37 + 8);
        if ( !v39 || *((_QWORD *)v38 + 1) != v37 || *v39 != v37 )
          goto LABEL_141;
        while ( 1 )
        {
          v40 = 0;
          if ( v38 == (int *)v37 )
            break;
          if ( !v38 )
            goto LABEL_141;
          if ( !*(_QWORD *)v38 )
            goto LABEL_141;
          v4 = (int **)*((_QWORD *)v38 + 1);
          if ( !v4 || *(int **)(*(_QWORD *)v38 + 8LL) != v38 || *v4 != v38 )
            goto LABEL_141;
          v40 = (ULONG_PTR)(v38 - 100);
          if ( *(v38 - 98) < 0 )
            KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v38 - 100), *(v38 - 98), 0);
          if ( *(_WORD *)v40 != 0xE2FF )
            break;
          v38 = *(int **)v38;
        }
        while ( v40 )
        {
          v57 = SmbCeGetNextBindingObject(v35, v40, v4, v17);
          if ( v57 == v40 )
            KeBugCheckEx(0x27u, 0x65534DF3u, v35, v40, BugCheckParameter4);
          v58 = *(_QWORD *)(v40 + 392);
          if ( v58 )
          {
            v63 = *(_DWORD *)(v58 + 4);
            if ( (v63 & 1) != 0
              && (v63 & 2) == 0
              && *(_DWORD *)(v35 + 88) > 1u
              && *(_QWORD *)(v40 + 280) == v40 + 280
              && *(_QWORD *)(v40 + 312) == v40 + 312 )
            {
              v60 = *(unsigned __int16 *)(v35 + 2);
              if ( (_WORD)v60 )
                v61 = v35 + v60;
              else
                v61 = 0;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                WPP_SF_qq(
                  WPP_GLOBAL_Control->AttachedDevice,
                  33,
                  WPP_948a51171ac53989b14c3e6a960354da_Traceguids,
                  v40,
                  v35);
              }
              (*(void (__fastcall **)(ULONG_PTR, ULONG_PTR, __int64))(*(_QWORD *)v61 + 16LL))(v35, v40, 3221225996LL);
            }
          }
          v40 = v57;
        }
        v41 = *(_QWORD **)(v35 + 392);
        v35 = 0;
        if ( v41 != v18 )
          v35 = (ULONG_PTR)(v41 - 49);
      }
      if ( MEMORY[0xFFFFF78000000008] - v75 >= 0x7A120 && (unsigned int)SmbCeReferenceServerEntrySafe(v6) )
      {
        v2 = (volatile LONG *)(BugCheckParameter4 + 1920);
        Interval.QuadPart = 0;
        *(_DWORD *)(BugCheckParameter4 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(BugCheckParameter4 + 1920), v72);
        Interval.QuadPart = -100000;
        KeDelayExecutionThread(0, 0, &Interval);
        v75 = MEMORY[0xFFFFF78000000008];
        v68 = SmbCeAcquireSpinLock(BugCheckParameter4, v66, v67);
        v69 = *(_QWORD *)(v6 + 32);
        v72 = v68;
        SmbCeDereferenceServerEntryEx(v6);
        v7 = v73;
        v3 = BugCheckParameter4 + 1904;
        v6 = 0;
        if ( v69 != BugCheckParameter4 + 1904 )
          v6 = v69 - 32;
      }
      else
      {
        v42 = *(_QWORD *)(v6 + 32);
        v3 = BugCheckParameter4 + 1904;
        v7 = v73;
        v2 = (volatile LONG *)(BugCheckParameter4 + 1920);
        v6 = 0;
        if ( v42 != BugCheckParameter4 + 1904 )
          v6 = v42 - 32;
      }
    }
  }
  *(_DWORD *)(BugCheckParameter4 + 2352) = -1;
  ExReleaseSpinLockExclusive(v2, v72);
  RxNameCacheScavengeEntries(0);
  if ( v7 && (dword_14007D208 & 1) != 0 )
    MRxSmbCaptureLiveKernelDump(v10, v9, v70);
  return 0;
}

```

## disassembly

```asm
0x1400017f0  push    rbx
0x1400017f2  push    rbp
0x1400017f3  push    rsi
0x1400017f4  push    rdi
0x1400017f5  push    r12
0x1400017f7  push    r13
0x1400017f9  push    r14
0x1400017fb  push    r15
0x1400017fd  sub     rsp, 58h
0x140001801  mov     rax, 0FFFFF78000000008h
0x14000180b  mov     [rsp+98h+arg_8], 0
0x140001813  mov     r12, rcx
0x140001816  mov     [rsp+98h+var_68], 0
0x14000181f  mov     dl, 1; Wait
0x140001821  mov     [rsp+98h+arg_10], 0
0x140001829  lea     rcx, Resource; Resource
0x140001830  mov     rdi, [rax]
0x140001833  mov     [rsp+98h+arg_18], rdi
0x14000183b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001842  nop     dword ptr [rax+rax+00h]
0x140001847  mov     eax, cs:dword_140070940
0x14000184d  cmp     eax, cs:dword_140070938
0x140001853  jnz     loc_140002064
0x140001859  lea     rcx, Resource; Resource
0x140001860  call    cs:__imp_ExReleaseResourceLite
0x140001867  nop     dword ptr [rax+rax+00h]
0x14000186c  lea     rbp, [r12+780h]
0x140001874  mov     rcx, rbp; SpinLock
0x140001877  call    cs:__imp_ExAcquireSpinLockExclusive
0x14000187e  nop     dword ptr [rax+rax+00h]
0x140001883  mov     [rsp+98h+arg_0], al
0x14000188a  call    cs:__imp_PsGetCurrentThreadId
0x140001891  nop     dword ptr [rax+rax+00h]
0x140001896  lea     r14, [r12+770h]
0x14000189e  mov     [r12+930h], eax
0x1400018a6  mov     rax, [r14]
0x1400018a9  cmp     rax, r14
0x1400018ac  jz      loc_140001DFA
0x1400018b2  lea     r13, [rax-20h]
0x1400018b6  xor     sil, sil
0x1400018b9  mov     r9d, 0E2FFh
0x1400018bf  test    r13, r13
0x1400018c2  jnz     short loc_140001912
0x1400018c4  movzx   edx, [rsp+98h+arg_0]; OldIrql
0x1400018cc  mov     rcx, rbp; SpinLock
0x1400018cf  mov     dword ptr [r12+930h], 0FFFFFFFFh
0x1400018db  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400018e2  nop     dword ptr [rax+rax+00h]
0x1400018e7  xor     ecx, ecx
0x1400018e9  call    cs:__imp_RxNameCacheScavengeEntries
0x1400018f0  nop     dword ptr [rax+rax+00h]
0x1400018f5  test    sil, sil
0x1400018f8  jnz     loc_140002246
0x1400018fe  xor     eax, eax
0x140001900  add     rsp, 58h
0x140001904  pop     r15
0x140001906  pop     r14
0x140001908  pop     r13
0x14000190a  pop     r12
0x14000190c  pop     rdi
0x14000190d  pop     rsi
0x14000190e  pop     rbp
0x14000190f  pop     rbx
0x140001910  retn
0x140001912  movzx   eax, word ptr [r13+2]
0x140001917  test    ax, ax
0x14000191a  jz      loc_14000202D
0x140001920  add     rax, 8
0x140001924  add     rax, r13
0x140001927  jz      loc_140002008
0x14000192d  mov     rcx, [rax]
0x140001930  test    rcx, rcx
0x140001933  jz      loc_140002008
0x140001939  mov     rdx, [rax+8]
0x14000193d  test    rdx, rdx
0x140001940  jz      loc_140002008
0x140001946  cmp     [rcx+8], rax
0x14000194a  jnz     loc_140002008
0x140001950  cmp     [rdx], rax
0x140001953  jnz     loc_140002008
0x140001959  xor     ebx, ebx
0x14000195b  cmp     rcx, rax
0x14000195e  jz      short loc_1400019B2
0x140001960  test    rcx, rcx
0x140001963  jz      loc_140002008
0x140001969  mov     rdx, [rcx]
0x14000196c  test    rdx, rdx
0x14000196f  jz      loc_140002008
0x140001975  mov     r8, [rcx+8]
0x140001979  test    r8, r8
0x14000197c  jz      loc_140002008
0x140001982  cmp     [rdx+8], rcx
0x140001986  jnz     loc_140002008
0x14000198c  cmp     [r8], rcx
0x14000198f  jnz     loc_140002008
0x140001995  lea     rbx, [rcx-190h]
0x14000199c  movsxd  rdx, dword ptr [rbx+8]
0x1400019a0  test    edx, edx
0x1400019a2  js      loc_140001F6A
0x1400019a8  cmp     [rbx], r9w
0x1400019ac  jz      loc_140002097
0x1400019b2  mov     rcx, r13
0x1400019b5  test    rbx, rbx
0x1400019b8  jnz     loc_140002149
0x1400019be  call    SmbCepExpireExchangesLite
0x1400019c3  lea     r15, [r13+210h]
0x1400019ca  cmp     [r15], r15
0x1400019cd  jz      loc_1400020A7
0x1400019d3  mov     rax, [r13+2D8h]
0x1400019da  test    rax, rax
0x1400019dd  jnz     loc_14005A9E6
0x1400019e3  lea     rdi, WPP_GLOBAL_Control
0x1400019ea  mov     eax, [r13+4]
0x1400019ee  test    al, 1
0x1400019f0  jnz     loc_14005AA45
0x1400019f6  mov     rdi, [r15]
0x1400019f9  cmp     rdi, r15
0x1400019fc  jnz     loc_140001E44
0x140001a02  xor     edi, edi
0x140001a04  test    rdi, rdi
0x140001a07  jz      loc_140001ADF
0x140001a0d  movzx   eax, word ptr [rdi+2]
0x140001a11  test    ax, ax
0x140001a14  jz      loc_140002023
0x140001a1a  add     rax, 8
0x140001a1e  add     rax, rdi
0x140001a21  jz      loc_140002008
0x140001a27  mov     rcx, [rax]
0x140001a2a  test    rcx, rcx
0x140001a2d  jz      loc_140002008
0x140001a33  mov     rdx, [rax+8]
0x140001a37  test    rdx, rdx
0x140001a3a  jz      loc_140002008
0x140001a40  cmp     [rcx+8], rax
0x140001a44  jnz     loc_140002008
0x140001a4a  cmp     [rdx], rax
0x140001a4d  jnz     loc_140002008
0x140001a53  mov     r11d, 0E2FFh
0x140001a59  xor     ebx, ebx
0x140001a5b  cmp     rcx, rax
0x140001a5e  jz      short loc_140001AB2
0x140001a60  test    rcx, rcx
0x140001a63  jz      loc_140002008
0x140001a69  mov     rdx, [rcx]
0x140001a6c  test    rdx, rdx
0x140001a6f  jz      loc_140002008
0x140001a75  mov     r8, [rcx+8]
0x140001a79  test    r8, r8
0x140001a7c  jz      loc_140002008
0x140001a82  cmp     [rdx+8], rcx
0x140001a86  jnz     loc_140002008
0x140001a8c  cmp     [r8], rcx
0x140001a8f  jnz     loc_140002008
0x140001a95  lea     rbx, [rcx-190h]
0x140001a9c  movsxd  rdx, dword ptr [rbx+8]
0x140001aa0  test    edx, edx
0x140001aa2  js      loc_140001F44
0x140001aa8  cmp     [rbx], r11w
0x140001aac  jz      loc_14000208F
0x140001ab2  test    rbx, rbx
0x140001ab5  jnz     loc_140001EB4
0x140001abb  mov     rbx, [rdi+188h]
0x140001ac2  mov     rcx, rdi
0x140001ac5  call    SmbCepExpireExchangesLite
0x140001aca  xor     edi, edi
0x140001acc  lea     rax, [rbx-188h]
0x140001ad3  cmp     rbx, r15
0x140001ad6  cmovnz  rdi, rax
0x140001ada  jmp     loc_140001A04
0x140001adf  mov     rax, [r15]
0x140001ae2  cmp     rax, r15
0x140001ae5  jnz     loc_140001E50
0x140001aeb  xor     esi, esi
0x140001aed  nop     dword ptr [rax]
0x140001af0  test    rsi, rsi
0x140001af3  jz      loc_140001BD8
0x140001af9  cmp     dword ptr [rsi+0Ch], 5
0x140001afd  jg      loc_140001E02
0x140001b03  movzx   eax, word ptr [rsi+2]
0x140001b07  test    ax, ax
0x140001b0a  jz      loc_14000200F
0x140001b10  lea     rcx, [rax+8]
0x140001b14  add     rcx, rsi
0x140001b17  jz      loc_140002008
0x140001b1d  mov     rax, [rcx]
0x140001b20  test    rax, rax
0x140001b23  jz      loc_140002008
0x140001b29  mov     rdx, [rcx+8]
0x140001b2d  test    rdx, rdx
0x140001b30  jz      loc_140002008
0x140001b36  cmp     [rax+8], rcx
0x140001b3a  jnz     loc_140002008
0x140001b40  cmp     [rdx], rcx
0x140001b43  jnz     loc_140002008
0x140001b49  mov     ebp, 0E2FFh
0x140001b4e  xor     ebx, ebx
0x140001b50  cmp     rax, rcx
0x140001b53  jz      short loc_140001BA6
0x140001b55  test    rax, rax
0x140001b58  jz      loc_140002008
0x140001b5e  mov     rdx, [rax]
0x140001b61  test    rdx, rdx
0x140001b64  jz      loc_140002008
0x140001b6a  mov     r8, [rax+8]
0x140001b6e  test    r8, r8
0x140001b71  jz      loc_140002008
0x140001b77  cmp     [rdx+8], rax
0x140001b7b  jnz     loc_140002008
0x140001b81  cmp     [r8], rax
0x140001b84  jnz     loc_140002008
0x140001b8a  lea     rbx, [rax-190h]
0x140001b91  movsxd  rdx, dword ptr [rbx+8]
0x140001b95  test    edx, edx
0x140001b97  js      loc_140001E1E
0x140001b9d  cmp     [rbx], bp
0x140001ba0  jz      loc_140002077
0x140001ba6  xor     bpl, bpl
0x140001ba9  test    rbx, rbx
0x140001bac  jnz     loc_140001D04
0x140001bb2  mov     rdx, [rsi+188h]
0x140001bb9  cmp     rdx, r15
0x140001bbc  lea     rax, [rdx-188h]
0x140001bc3  cmovnz  rbx, rax
0x140001bc7  test    bpl, bpl
0x140001bca  jnz     loc_1400021AD
0x140001bd0  mov     rsi, rbx
0x140001bd3  jmp     loc_140001AF0
0x140001bd8  mov     rax, [r15]
0x140001bdb  cmp     rax, r15
0x140001bde  jnz     loc_140001E5C
0x140001be4  xor     edi, edi
0x140001be6  mov     ebp, 0E2FFh
0x140001beb  test    rdi, rdi
0x140001bee  jz      loc_140001CB7
0x140001bf4  movzx   eax, word ptr [rdi+2]
0x140001bf8  test    ax, ax
0x140001bfb  jz      loc_140002019
0x140001c01  lea     rcx, [rax+8]
0x140001c05  add     rcx, rdi
0x140001c08  jz      loc_140002008
0x140001c0e  mov     rax, [rcx]
0x140001c11  test    rax, rax
0x140001c14  jz      loc_140002008
0x140001c1a  mov     rdx, [rcx+8]
0x140001c1e  test    rdx, rdx
0x140001c21  jz      loc_140002008
0x140001c27  cmp     [rax+8], rcx
0x140001c2b  jnz     loc_140002008
0x140001c31  cmp     [rdx], rcx
0x140001c34  jnz     loc_140002008
0x140001c3a  xor     ebx, ebx
0x140001c3c  cmp     rax, rcx
0x140001c3f  jz      short loc_140001C92
0x140001c41  test    rax, rax
0x140001c44  jz      loc_140002008
0x140001c4a  mov     rdx, [rax]
0x140001c4d  test    rdx, rdx
0x140001c50  jz      loc_140002008
0x140001c56  mov     r8, [rax+8]
0x140001c5a  test    r8, r8
0x140001c5d  jz      loc_140002008
0x140001c63  cmp     [rdx+8], rax
0x140001c67  jnz     loc_140002008
0x140001c6d  cmp     [r8], rax
0x140001c70  jnz     loc_140002008
0x140001c76  lea     rbx, [rax-190h]
0x140001c7d  movsxd  rdx, dword ptr [rbx+8]
0x140001c81  test    edx, edx
0x140001c83  js      loc_140001E68
0x140001c89  cmp     [rbx], bp
0x140001c8c  jz      loc_140002087
0x140001c92  test    rbx, rbx
0x140001c95  jnz     loc_140001F90
0x140001c9b  mov     rcx, [rdi+188h]
0x140001ca2  xor     edi, edi
0x140001ca4  cmp     rcx, r15
0x140001ca7  lea     rax, [rcx-188h]
0x140001cae  cmovnz  rdi, rax
0x140001cb2  jmp     loc_140001BEB
0x140001cb7  mov     rax, ds:0FFFFF78000000008h
0x140001cc1  sub     rax, [rsp+98h+arg_18]
0x140001cc9  cmp     rax, 7A120h
0x140001ccf  jnb     loc_14005AB76
0x140001cd5  mov     rcx, [r13+20h]
0x140001cd9  lea     r14, [r12+770h]
0x140001ce1  movzx   esi, [rsp+98h+arg_8]
0x140001ce9  lea     rbp, [r12+780h]
0x140001cf1  xor     r13d, r13d
0x140001cf4  cmp     rcx, r14
0x140001cf7  lea     rax, [rcx-20h]
0x140001cfb  cmovnz  r13, rax
0x140001cff  jmp     loc_1400018B9
0x140001d04  lea     rcx, [rbx+0C0h]; SpinLock
0x140001d0b  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140001d12  nop     dword ptr [rax+rax+00h]
0x140001d17  lea     rax, [rbx+118h]
0x140001d1e  cmp     [rax], rax
0x140001d21  jnz     short loc_140001D47
0x140001d23  mov     rax, [rsp+98h+arg_18]
0x140001d2b  sub     rax, [rbx+1C0h]
  ... truncated ...
```
