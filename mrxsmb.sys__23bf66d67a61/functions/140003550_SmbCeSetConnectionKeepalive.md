# SmbCeSetConnectionKeepalive

- ea: `0x140003550`
- end: `0x140004354`
- name: `SmbCeSetConnectionKeepalive`
- size: `3588`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400017f0`
- `0x14000a260`
- `0x140027dc0`

## callees

- `0x140003550`
- `0x140004360`
- `0x140004480`
- `0x140037cdc`
- `0x140037fa4`
- `0x1400518b0`
- `0x1400571a4`
- `0x140059dc0`
- `0x140059ea0`
- `0x14005a200`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000397a`
- `ntoskrnl!KeInitializeEvent` at `0x140003d49`
- `ntoskrnl!KeInitializeEvent` at `0x14000397a`
- `ntoskrnl!KeInitializeEvent` at `0x140003d49`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004262`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400042f8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140004262`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400042f8`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140003a79`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140003e56`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140003a79`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140003e56`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000364a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140003892`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140003c55`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140003fc6`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000364a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140003892`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140003c55`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140003fc6`
- `ntoskrnl!KeBugCheckEx` at `0x140003b15`
- `ntoskrnl!KeBugCheckEx` at `0x140003b37`
- `ntoskrnl!KeBugCheckEx` at `0x14000401c`
- `ntoskrnl!KeBugCheckEx` at `0x1400040a5`
- `ntoskrnl!KeBugCheckEx` at `0x1400040d1`
- `ntoskrnl!KeBugCheckEx` at `0x140003b15`
- `ntoskrnl!KeBugCheckEx` at `0x140003b37`
- `ntoskrnl!KeBugCheckEx` at `0x14000401c`
- `ntoskrnl!KeBugCheckEx` at `0x1400040a5`
- `ntoskrnl!KeBugCheckEx` at `0x1400040d1`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000361b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140003828`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000385a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140003c26`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000361b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140003828`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14000385a`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140003c26`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400035c0`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000369b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140003e65`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x1400035c0`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x14000369b`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140003e65`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400035cf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400036aa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003e74`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400035cf`
- `ntoskrnl!PsGetCurrentThreadId` at `0x1400036aa`
- `ntoskrnl!PsGetCurrentThreadId` at `0x140003e74`
- `rdbss!RxCeFreeIrp` at `0x140003a32`
- `rdbss!RxCeFreeIrp` at `0x140003e0b`
- `rdbss!RxCeFreeIrp` at `0x140003a32`
- `rdbss!RxCeFreeIrp` at `0x140003e0b`
- `rdbss!RxCeAllocateIrp` at `0x14000394e`
- `rdbss!RxCeAllocateIrp` at `0x140003d1c`
- `rdbss!RxCeAllocateIrp` at `0x14000394e`
- `rdbss!RxCeAllocateIrp` at `0x140003d1c`

## pseudocode

```c
void __fastcall SmbCeSetConnectionKeepalive(__int64 a1, int a2, int a3)
{
  unsigned __int64 v3; // rbp
  __int64 v4; // r13
  __int64 v5; // rdi
  char v7; // r14
  KIRQL v8; // si
  char v9; // al
  __int64 v10; // rbx
  unsigned int v11; // r13d
  __int64 v12; // rsi
  __int64 v13; // r12
  unsigned int v14; // eax
  __int64 v15; // rax
  __int64 v16; // rcx
  int *v17; // rax
  _QWORD *v18; // rdx
  ULONG_PTR v19; // r15
  int **v20; // r8
  int v21; // edx
  __int64 v22; // r8
  char v23; // cl
  __int64 v24; // rcx
  __int64 v25; // r9
  ULONG_PTR v26; // r15
  int *v27; // rcx
  _QWORD *v28; // r8
  int *v29; // r9
  KIRQL v30; // dl
  int v31; // esi
  unsigned int v32; // ecx
  unsigned int v33; // eax
  unsigned int v34; // eax
  unsigned int v35; // eax
  unsigned int v36; // r14d
  int v37; // ecx
  __int64 v38; // r8
  IRP *v39; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int64 (__fastcall ***v41)(_QWORD, __int64, __int64, _QWORD, __int64, unsigned __int64, _QWORD, _QWORD, _QWORD, IRP *); // r10
  __int64 (__fastcall **v42)(_QWORD, __int64, __int64, _QWORD, __int64, unsigned __int64, _QWORD, _QWORD, _QWORD, IRP *); // r8
  unsigned int v43; // edx
  int v44; // eax
  int v45; // eax
  int v46; // r13d
  int **v47; // r10
  char v48; // cl
  signed __int32 v49; // r8d
  _QWORD *v50; // rax
  __int64 v51; // rcx
  KIRQL v52; // dl
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // r9
  __int64 v56; // rcx
  int v57; // eax
  unsigned int v58; // ecx
  unsigned int v59; // eax
  unsigned int v60; // eax
  unsigned int v61; // eax
  unsigned int v62; // edx
  int v63; // ecx
  __int64 Irp; // rax
  __int64 v65; // r8
  __int64 v66; // r8
  __int64 v67; // rax
  __int64 (__fastcall ***v68)(_QWORD, __int64, __int64, _QWORD, __int64, unsigned __int64, _QWORD, _QWORD, _QWORD, __int64); // r10
  unsigned int v69; // ecx
  __int64 (__fastcall **v70)(_QWORD, __int64, __int64, _QWORD, __int64, unsigned __int64, _QWORD, _QWORD, _QWORD, __int64); // r9
  unsigned int v71; // edx
  int v72; // eax
  IRP *v73; // rcx
  int v74; // eax
  __int64 v75; // rax
  __int64 v76; // rcx
  int *v77; // rax
  _QWORD *v78; // rdx
  int *v79; // rcx
  __int64 v80; // rcx
  _QWORD *v81; // rax
  int **v82; // r8
  unsigned int v83; // edi
  __int64 v84; // r8
  __int64 v85; // r8
  int v86; // ecx
  int v87; // ecx
  __int64 v88; // rdx
  __int64 v89; // r8
  __int64 v90; // rdx
  __int64 v91; // r8
  _BYTE v92[4]; // [rsp+A0h] [rbp+0h] BYREF

  v3 = (unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL;
  v4 = *(_QWORD *)(a1 + 24);
  v5 = a3;
  *(_DWORD *)(v3 + 12) = a3;
  *(_DWORD *)(v3 + 8) = a2;
  *(_OWORD *)(v3 + 160) = 0;
  *(_OWORD *)(v3 + 176) = 0;
  if ( *(_WORD *)a1 != 0xE206 )
  {
    memset((void *)(v3 + 130), 0, 0x23Eu);
    *(_WORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x80) = -7425;
    *(_BYTE *)v3 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920));
    *(_DWORD *)(v4 + 2352) = (unsigned int)PsGetCurrentThreadId();
    v15 = *(unsigned __int16 *)(a1 + 2);
    if ( (_WORD)v15 )
    {
      v16 = a1 + v15 + 8;
      if ( !v16 )
        goto LABEL_128;
    }
    else
    {
      v16 = 8;
    }
    v17 = *(int **)v16;
    if ( *(_QWORD *)v16 )
    {
      v18 = *(_QWORD **)(v16 + 8);
      if ( v18 )
      {
        if ( *((_QWORD *)v17 + 1) == v16 && *v18 == v16 )
        {
          while ( 1 )
          {
            v19 = 0;
            if ( v17 == (int *)v16 )
              break;
            if ( !v17 )
              goto LABEL_128;
            if ( !*(_QWORD *)v17 )
              goto LABEL_128;
            v20 = (int **)*((_QWORD *)v17 + 1);
            if ( !v20 || *(int **)(*(_QWORD *)v17 + 8LL) != v17 || *v20 != v17 )
              goto LABEL_128;
            v19 = (ULONG_PTR)(v17 - 100);
            if ( *(v17 - 98) < 0 )
              KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v17 - 100), *(v17 - 98), 0);
            if ( *(_WORD *)v19 != 0xE2FF )
              break;
            v17 = *(int **)v17;
          }
          if ( !v19 )
          {
LABEL_36:
            v30 = *(_BYTE *)v3;
            *(_DWORD *)(v4 + 2352) = -1;
            ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920), v30);
            return;
          }
          v21 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
          v22 = *(int *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC);
          for ( *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = v22;
                ;
                v22 = *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) )
          {
            v23 = *(_BYTE *)(v22 + v19 + 440);
            if ( v21 )
            {
              if ( v23 )
                goto LABEL_25;
              v48 = 1;
            }
            else
            {
              if ( !v23 )
              {
LABEL_25:
                v24 = *(unsigned __int16 *)(a1 + 2);
                if ( (_WORD)v24 )
                  v25 = a1 + v24;
                else
                  v25 = 0;
                if ( *(int *)(v19 + 8) < 0 )
                  KeBugCheckEx(0x27u, 0xA0001u, v19, *(int *)(v19 + 8), 0);
                v26 = v19 + 400;
                if ( !v26 )
                  goto LABEL_128;
                v27 = *(int **)v26;
                if ( !*(_QWORD *)v26 )
                  goto LABEL_128;
                v28 = *(_QWORD **)(v26 + 8);
                if ( !v28 || *((_QWORD *)v27 + 1) != v26 || *v28 != v26 )
                  goto LABEL_128;
                v29 = (int *)(v25 + 8);
                while ( 1 )
                {
                  v19 = 0;
                  if ( v27 == v29 )
                    goto LABEL_35;
                  if ( !v27 )
                    goto LABEL_128;
                  if ( !*(_QWORD *)v27 )
                    goto LABEL_128;
                  v47 = (int **)*((_QWORD *)v27 + 1);
                  if ( !v47 || *(int **)(*(_QWORD *)v27 + 8LL) != v27 || *v47 != v27 )
                    goto LABEL_128;
                  v19 = (ULONG_PTR)(v27 - 100);
                  if ( *(v27 - 98) < 0 )
                    KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v27 - 100), *(v27 - 98), 0);
                  if ( *(_WORD *)v19 != 0xE2FF )
                    goto LABEL_35;
                  v27 = *(int **)v27;
                }
              }
              v48 = 0;
            }
            *(_BYTE *)(v22 + v19 + 440) = v48;
            v49 = _InterlockedIncrement((volatile signed __int32 *)(v19 + 8));
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qDD(
                WPP_GLOBAL_Control->AttachedDevice,
                14,
                WPP_1342ee1acfa830e98f791bdb08bd815d_Traceguids,
                v19,
                v49 - 1,
                v49);
            }
            v50 = (_QWORD *)(v19 + 400);
            v51 = *(_QWORD *)(v19 + 400);
            if ( *(_QWORD *)(v51 + 8) != v19 + 400 )
              goto LABEL_128;
            *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x210) = v51;
            *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x218) = v50;
            *(_QWORD *)(v51 + 8) = v3 + 528;
            v52 = *(_BYTE *)v3;
            *v50 = v3 + 528;
            *(_DWORD *)(v4 + 2352) = -1;
            ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920), v52);
            v53 = *(_QWORD *)(v19 + 392);
            *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) = v53;
            v54 = v53 + 376;
            *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = v54;
            if ( *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8) )
            {
              *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = dword_14007D158;
              ExAcquirePushLockExclusiveEx(v54, 0);
              v55 = *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
              v56 = *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58);
              if ( _InterlockedIncrement((volatile signed __int32 *)(v55 + 4 * v56 + 352)) != 1 )
                goto LABEL_110;
              v57 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
            }
            else
            {
              ExAcquirePushLockExclusiveEx(v54, 0);
              v55 = *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
              v56 = *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58);
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v55 + 4 * v56 + 352), 0xFFFFFFFF) != 1 )
                goto LABEL_110;
              v57 = 0;
              *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18) = *(_QWORD *)(((unsigned __int64)v92
                                                                                               & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                              + 0x18);
              *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = 0;
            }
            *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 4;
            *(_DWORD *)(v55 + 4 * v56 + 336) = v57;
            v58 = -1;
            if ( (unsigned int)(*(_DWORD *)(v55 + 336) - 1) <= 0xFFFFFFFD )
            {
              v58 = *(_DWORD *)(v55 + 336);
              *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
            }
            v59 = *(_DWORD *)(v55 + 340);
            if ( v59 && v59 < v58 )
            {
              v58 = *(_DWORD *)(v55 + 340);
              *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 1;
            }
            v60 = *(_DWORD *)(v55 + 344);
            if ( v60 && v60 < v58 )
            {
              v58 = *(_DWORD *)(v55 + 344);
              *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 2;
            }
            v61 = *(_DWORD *)(v55 + 348);
            if ( v61 && v61 < v58 )
            {
              v58 = *(_DWORD *)(v55 + 348);
              *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 3;
            }
            v62 = 0;
            if ( v58 != -1 )
              v62 = v58;
            v63 = *(_DWORD *)(v55 + 320);
            *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = v62;
            if ( v63 == 1 )
              break;
            if ( v63 )
            {
              v87 = v63 - 2;
              if ( !v87 )
              {
                v90 = 1000 * v62;
                v91 = (unsigned int)v90;
                if ( (unsigned int)v90 > 0x1388 )
                  v91 = 5000;
                (*(void (__fastcall **)(_QWORD, __int64, __int64))(SmbdFastDispatch + 144))(
                  *(_QWORD *)(v55 + 104),
                  v90,
                  v91);
LABEL_106:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_dqdd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    32,
                    v65,
                    *(unsigned int *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8),
                    *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20),
                    *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC),
                    *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4));
                }
                goto LABEL_108;
              }
              if ( v87 != 2 )
                goto LABEL_109;
              v74 = SmbQuicEnableKeepAlive(v55);
            }
            else
            {
              v74 = RxTdiEnableKeepAlive(v55);
            }
LABEL_105:
            if ( v74 >= 0 )
              goto LABEL_106;
LABEL_108:
            v55 = *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20);
LABEL_109:
            if ( (unsigned int)(*(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC) - 2) <= 1
              && *(_DWORD *)(v55 + 320) == 1
              && (int)SmbWskEnableMaxRT(v55, *(unsigned int *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10)) >= 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_dqdd(
                WPP_GLOBAL_Control->AttachedDevice,
                33,
                v85,
                *(unsigned int *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10),
                *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20),
                *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC),
                *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4));
            }
LABEL_110:
            ExReleasePushLockExclusiveEx(*(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x18), 0);
            *(_BYTE *)v3 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920));
            *(_DWORD *)(v4 + 2352) = (unsigned int)PsGetCurrentThreadId();
            SmbCeDereferenceBindingObject(v19);
            v75 = *(unsigned __int16 *)(a1 + 2);
            if ( (_WORD)v75 )
              v76 = a1 + v75;
            else
              v76 = 0;
            if ( *(int *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88) < 0 )
              KeBugCheckEx(
                0x27u,
                0xA0001u,
                v3 + 128,
                *(int *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x88),
                0);
            v77 = *(int **)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x210);
            if ( !v77 )
              goto LABEL_128;
            v78 = *(_QWORD **)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x218);
            if ( !v78 || *((_QWORD *)v77 + 1) != v3 + 528 || *v78 != v3 + 528 )
              goto LABEL_128;
            v79 = (int *)(v76 + 8);
            while ( 1 )
            {
              v19 = 0;
              if ( v77 == v79 )
                break;
              if ( !v77 )
                goto LABEL_128;
              if ( !*(_QWORD *)v77 )
                goto LABEL_128;
              v82 = (int **)*((_QWORD *)v77 + 1);
              if ( !v82 || *(int **)(*(_QWORD *)v77 + 8LL) != v77 || *v82 != v77 )
                goto LABEL_128;
              v19 = (ULONG_PTR)(v77 - 100);
              if ( *(v77 - 98) < 0 )
                KeBugCheckEx(0x27u, 0xA0001u, (ULONG_PTR)(v77 - 100), *(v77 - 98), 0);
              if ( *(_WORD *)v19 != 0xE2FF )
                break;
              v77 = *(int **)v77;
            }
            v80 = *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x210);
            if ( *(_QWORD *)(v80 + 8) != v3 + 528 )
              goto LABEL_128;
            v81 = *(_QWORD **)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x218);
            if ( *v81 != v3 + 528 )
              goto LABEL_128;
            v21 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
            *v81 = v80;
            *(_QWORD *)(v80 + 8) = v81;
            *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x218) = ((unsigned __int64)v92
                                                                                  & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                 + 528;
            *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x210) = ((unsigned __int64)v92
                                                                                  & 0xFFFFFFFFFFFFFFC0uLL)
                                                                                 + 528;
LABEL_35:
            if ( !v19 )
              goto LABEL_36;
          }
          *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = 0;
          *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = 0;
          *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = 0;
          *(_OWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 0;
          *(_OWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = 0;
          Irp = RxCeAllocateIrp(1, 0, 1);
          *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28) = Irp;
          if ( !Irp )
          {
            v74 = -1073741670;
            goto LABEL_105;
          }
          *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 259;
          *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = 0;
          KeInitializeEvent((PRKEVENT)(v3 + 64), NotificationEvent, 0);
          v66 = *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
          v67 = *(_QWORD *)(v66 + 184);
          *(_QWORD *)(v67 - 16) = SmbWskSynchronousIrpComplete;
          *(_QWORD *)(v67 - 8) = v3 + 48;
          *(_BYTE *)(v67 - 69) = -32;
          v68 = *(__int64 (__fastcall ****)(_QWORD, __int64, __int64, _QWORD, __int64, unsigned __int64, _QWORD, _QWORD, _QWORD, __int64))(*(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x20) + 104LL);
          LODWORD(v67) = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14);
          v69 = 1000 * v67;
          v70 = *v68;
          *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x6C) = 1000 * v67;
          if ( (_DWORD)v67 )
          {
            *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = 1;
            v71 = v69 / 0xA;
            if ( v69 / 0xA > 0x3E8 )
            {
              *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = 1000;
LABEL_102:
              v72 = (*v70)(v68, 2, 2550136836LL, 0, 12, v3 + 104, 0, 0, 0, v66);
              *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = v72;
              if ( v72 == 259 )
              {
                KeWaitForSingleObject((PVOID)(v3 + 64), UserRequest, 0, 0, 0);
                v73 = *(IRP **)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
                *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14) = v73->IoStatus.Status;
              }
              else
              {
                v73 = *(IRP **)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x28);
              }
              RxCeFreeIrp(v73);
              v74 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x14);
              goto LABEL_105;
            }
          }
          else
          {
            *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x68) = 0;
            v71 = v69 / 0xA;
          }
          *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x70) = v71;
          goto LABEL_102;
        }
      }
    }
LABEL_128:
    __fastfail(3u);
  }
  v7 = 0;
  v8 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920));
  *(_DWORD *)(v4 + 2352) = (unsigned int)PsGetCurrentThreadId();
  v9 = *(_BYTE *)(v5 + a1 + 440);
  if ( *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8) )
  {
    if ( !v9 )
    {
      *(_BYTE *)(v5 + a1 + 440) = 1;
      *(_DWORD *)(v4 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920), v8);
      v10 = *(_QWORD *)(a1 + 392);
      v11 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
      v12 = v10;
      goto LABEL_5;
    }
  }
  else if ( v9 )
  {
    v7 = 1;
    *(_BYTE *)(v5 + a1 + 440) = 0;
  }
  *(_DWORD *)(v4 + 2352) = -1;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v4 + 1920), v8);
  if ( !v7 )
    return;
  v10 = *(_QWORD *)(a1 + 392);
  v11 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 8);
  v12 = v10;
  if ( v11 )
  {
LABEL_5:
    v13 = v12 + 376;
    *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = dword_14007D158;
    ExAcquirePushLockExclusiveEx(v12 + 376, 0);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v12 + 4 * v5 + 352)) == 1 )
    {
      v14 = v11;
      goto LABEL_43;
    }
    goto LABEL_62;
  }
  v13 = v10 + 376;
  ExAcquirePushLockExclusiveEx(v10 + 376, 0);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v10 + 4 * v5 + 352), 0xFFFFFFFF) == 1 )
  {
    v14 = 0;
    *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4) = 0;
LABEL_43:
    v31 = 4;
    *(_DWORD *)(v10 + 4 * v5 + 336) = v14;
    v32 = -1;
    if ( (unsigned int)(*(_DWORD *)(v10 + 336) - 1) <= 0xFFFFFFFD )
    {
      v32 = *(_DWORD *)(v10 + 336);
      v31 = 0;
    }
    v33 = *(_DWORD *)(v10 + 340);
    if ( v33 && v33 < v32 )
    {
      v32 = *(_DWORD *)(v10 + 340);
      v31 = 1;
    }
    v34 = *(_DWORD *)(v10 + 344);
    if ( v34 && v34 < v32 )
    {
      v32 = *(_DWORD *)(v10 + 344);
      v31 = 2;
    }
    v35 = *(_DWORD *)(v10 + 348);
    if ( v35 && v35 < v32 )
    {
      v32 = *(_DWORD *)(v10 + 348);
      v31 = 3;
    }
    v36 = 0;
    if ( v32 != -1 )
      v36 = v32;
    v37 = *(_DWORD *)(v10 + 320);
    if ( v37 != 1 )
    {
      if ( v37 )
      {
        v86 = v37 - 2;
        if ( !v86 )
        {
          v88 = 1000 * v36;
          v89 = v88;
          if ( (unsigned int)v88 > 0x1388 )
            v89 = 5000;
          (*(void (__fastcall **)(_QWORD, __int64, __int64))(SmbdFastDispatch + 144))(*(_QWORD *)(v10 + 104), v88, v89);
          goto LABEL_59;
        }
        if ( v86 != 2 )
        {
LABEL_61:
          v46 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC);
          if ( (unsigned int)(v46 - 2) <= 1 && *(_DWORD *)(v10 + 320) == 1 )
          {
            v83 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 4);
            if ( (int)SmbWskEnableMaxRT(v10, v83) >= 0
              && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_dqdd(WPP_GLOBAL_Control->AttachedDevice, 33, v84, v83, v10, v46, v31);
            }
          }
          goto LABEL_62;
        }
        v45 = SmbQuicEnableKeepAlive(v10);
      }
      else
      {
        v45 = RxTdiEnableKeepAlive(v10);
      }
LABEL_58:
      if ( v45 >= 0 )
      {
LABEL_59:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_dqdd(
            WPP_GLOBAL_Control->AttachedDevice,
            32,
            v38,
            v11,
            v10,
            *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0xC),
            v31);
        }
        goto LABEL_61;
      }
      goto LABEL_61;
    }
    *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x50) = 0;
    *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = 0;
    *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = 0;
    *(_OWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 0;
    *(_OWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x40) = 0;
    v39 = (IRP *)RxCeAllocateIrp(1, 0, 1);
    if ( !v39 )
    {
      v45 = -1073741670;
      goto LABEL_58;
    }
    *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x30) = 259;
    *(_QWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x38) = 0;
    KeInitializeEvent((PRKEVENT)(v3 + 64), NotificationEvent, 0);
    CurrentStackLocation = v39->Tail.Overlay.CurrentStackLocation;
    CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)SmbWskSynchronousIrpComplete;
    CurrentStackLocation[-1].Context = (PVOID)(v3 + 48);
    CurrentStackLocation[-1].Control = -32;
    v41 = *(__int64 (__fastcall ****)(_QWORD, __int64, __int64, _QWORD, __int64, unsigned __int64, _QWORD, _QWORD, _QWORD, IRP *))(v10 + 104);
    v42 = *v41;
    *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x5C) = 1000 * v36;
    v43 = 1000 * v36 / 0xA;
    if ( v36 )
    {
      *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = 1;
      if ( v43 > 0x3E8 )
      {
        *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = 1000;
LABEL_55:
        v44 = (*v42)(v41, 2, 2550136836LL, 0, 12, v3 + 88, 0, 0, 0, v39);
        *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v44;
        if ( v44 == 259 )
        {
          KeWaitForSingleObject((PVOID)(v3 + 64), UserRequest, 0, 0, 0);
          *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10) = v39->IoStatus.Status;
        }
        RxCeFreeIrp(v39);
        v45 = *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x10);
        goto LABEL_58;
      }
    }
    else
    {
      *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x58) = 0;
    }
    *(_DWORD *)(((unsigned __int64)v92 & 0xFFFFFFFFFFFFFFC0uLL) + 0x60) = v43;
    goto LABEL_55;
  }
LABEL_62:
  ExReleasePushLockExclusiveEx(v13, 0);
}

```

## disassembly

```asm
0x140003550  mov     [rsp-8+arg_18], rbx
0x140003555  push    rbp
0x140003556  push    rsi
0x140003557  push    rdi
0x140003558  push    r12
0x14000355a  push    r13
0x14000355c  push    r14
0x14000355e  push    r15
0x140003560  sub     rsp, 370h
0x140003567  lea     rbp, [rsp+0A0h]
0x14000356f  and     rbp, 0FFFFFFFFFFFFFFC0h
0x140003573  mov     rax, cs:__security_cookie
0x14000357a  xor     rax, rsp
0x14000357d  mov     [rbp+300h+var_40], rax
0x140003584  mov     r13, [rcx+18h]
0x140003588  xorps   xmm0, xmm0
0x14000358b  mov     eax, 0E206h
0x140003590  movsxd  rdi, r8d
0x140003593  mov     rbx, rcx
0x140003596  mov     [rbp+300h+var_2F4], edi
0x140003599  mov     [rbp+300h+var_2F8], edx
0x14000359c  lea     r12, [r13+780h]
0x1400035a3  movups  [rbp+300h+var_260], xmm0
0x1400035aa  movups  [rbp+300h+var_250], xmm0
0x1400035b1  cmp     [rcx], ax
0x1400035b4  jnz     loc_140003678
0x1400035ba  mov     rcx, r12; SpinLock
0x1400035bd  xor     r14b, r14b
0x1400035c0  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400035c7  nop     dword ptr [rax+rax+00h]
0x1400035cc  movzx   esi, al
0x1400035cf  call    cs:__imp_PsGetCurrentThreadId
0x1400035d6  nop     dword ptr [rax+rax+00h]
0x1400035db  mov     [r13+930h], eax
0x1400035e2  mov     r15, rdi
0x1400035e5  movzx   eax, byte ptr [rdi+rbx+1B8h]
0x1400035ed  xor     edi, edi
0x1400035ef  cmp     [rbp+300h+var_2F8], edi
0x1400035f2  jz      loc_140003839
0x1400035f8  test    al, al
0x1400035fa  jnz     loc_140003848
0x140003600  mov     byte ptr [r15+rbx+1B8h], 1
0x140003609  movzx   edx, sil; OldIrql
0x14000360d  mov     rcx, r12; SpinLock
0x140003610  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x14000361b  call    cs:__imp_ExReleaseSpinLockExclusive
0x140003622  nop     dword ptr [rax+rax+00h]
0x140003627  mov     rbx, [rbx+188h]
0x14000362e  mov     r13d, [rbp+300h+var_2F8]
0x140003632  mov     rsi, rbx
0x140003635  mov     eax, cs:dword_14007D158
0x14000363b  lea     r12, [rsi+178h]
0x140003642  mov     rcx, r12
0x140003645  mov     [rbp+300h+var_2FC], eax
0x140003648  xor     edx, edx
0x14000364a  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140003651  nop     dword ptr [rax+rax+00h]
0x140003656  mov     eax, 1
0x14000365b  lock xadd [rsi+r15*4+160h], eax
0x140003665  inc     eax
0x140003667  cmp     eax, 1
0x14000366a  jnz     loc_140003A74
0x140003670  mov     eax, r13d
0x140003673  jmp     loc_1400038BD
0x140003678  xor     edx, edx; Val
0x14000367a  lea     rcx, [rbp+300h+BugCheckParameter2+2]; void *
0x140003681  mov     r8d, 23Eh; Size
0x140003687  call    memset
0x14000368c  mov     esi, 0E2FFh
0x140003691  mov     rcx, r12; SpinLock
0x140003694  mov     word ptr [rbp+300h+BugCheckParameter2], si
0x14000369b  call    cs:__imp_ExAcquireSpinLockExclusive
0x1400036a2  nop     dword ptr [rax+rax+00h]
0x1400036a7  mov     [rbp+300h+var_300], al
0x1400036aa  call    cs:__imp_PsGetCurrentThreadId
0x1400036b1  nop     dword ptr [rax+rax+00h]
0x1400036b6  mov     [r13+930h], eax
0x1400036bd  movzx   eax, word ptr [rbx+2]
0x1400036c1  test    ax, ax
0x1400036c4  jz      loc_1400040B2
0x1400036ca  lea     rcx, [rax+8]
0x1400036ce  add     rcx, rbx
0x1400036d1  jz      loc_140003FB3
0x1400036d7  mov     rax, [rcx]
0x1400036da  test    rax, rax
0x1400036dd  jz      loc_140003FB3
0x1400036e3  mov     rdx, [rcx+8]
0x1400036e7  test    rdx, rdx
0x1400036ea  jz      loc_140003FB3
0x1400036f0  cmp     [rax+8], rcx
0x1400036f4  jnz     loc_140003FB3
0x1400036fa  cmp     [rdx], rcx
0x1400036fd  jnz     loc_140003FB3
0x140003703  xor     edi, edi
0x140003705  mov     r15, rdi
0x140003708  cmp     rax, rcx
0x14000370b  jz      short loc_14000375F
0x14000370d  test    rax, rax
0x140003710  jz      loc_140003FB3
0x140003716  mov     rdx, [rax]
0x140003719  test    rdx, rdx
0x14000371c  jz      loc_140003FB3
0x140003722  mov     r8, [rax+8]
0x140003726  test    r8, r8
0x140003729  jz      loc_140003FB3
0x14000372f  cmp     [rdx+8], rax
0x140003733  jnz     loc_140003FB3
0x140003739  cmp     [r8], rax
0x14000373c  jnz     loc_140003FB3
0x140003742  lea     r15, [rax-190h]
0x140003749  movsxd  rdx, dword ptr [r15+8]
0x14000374d  test    edx, edx
0x14000374f  js      loc_140003B00
0x140003755  cmp     [r15], si
0x140003759  jz      loc_140004151
0x14000375f  test    r15, r15
0x140003762  jz      loc_140003816
0x140003768  movsxd  rax, [rbp+300h+var_2F4]
0x14000376c  mov     esi, 4
0x140003771  mov     edx, [rbp+300h+var_2F8]
0x140003774  mov     r8, rax
0x140003777  mov     [rbp+300h+var_2A8], rax
0x14000377b  mov     r14d, 0FFFFFFFFh
0x140003781  lea     rax, WPP_GLOBAL_Control
0x140003788  mov     r11d, 0E2FFh
0x14000378e  movzx   ecx, byte ptr [r8+r15+1B8h]
0x140003797  test    edx, edx
0x140003799  jz      loc_140003B9F
0x14000379f  test    cl, cl
0x1400037a1  jz      loc_140003FFC
0x1400037a7  movzx   ecx, word ptr [rbx+2]
0x1400037ab  test    cx, cx
0x1400037ae  jz      loc_1400040DE
0x1400037b4  lea     r9, [rbx+rcx]
0x1400037b8  movsxd  rcx, dword ptr [r15+8]
0x1400037bc  test    ecx, ecx
0x1400037be  js      loc_140003B22
0x1400037c4  add     r15, 190h
0x1400037cb  jz      loc_140003FB3
0x1400037d1  mov     rcx, [r15]
0x1400037d4  test    rcx, rcx
0x1400037d7  jz      loc_140003FB3
0x1400037dd  mov     r8, [r15+8]
0x1400037e1  test    r8, r8
0x1400037e4  jz      loc_140003FB3
0x1400037ea  cmp     [rcx+8], r15
0x1400037ee  jnz     loc_140003FB3
0x1400037f4  cmp     [r8], r15
0x1400037f7  jnz     loc_140003FB3
0x1400037fd  add     r9, 8
0x140003801  mov     r15, rdi
0x140003804  cmp     rcx, r9
0x140003807  jnz     loc_140003B44
0x14000380d  test    r15, r15
0x140003810  jnz     loc_14000434B
0x140003816  movzx   edx, [rbp+300h+var_300]; OldIrql
0x14000381a  mov     rcx, r12; SpinLock
0x14000381d  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x140003828  call    cs:__imp_ExReleaseSpinLockExclusive
0x14000382f  nop     dword ptr [rax+rax+00h]
0x140003834  jmp     loc_140003A85
0x140003839  test    al, al
0x14000383b  jz      short loc_140003848
0x14000383d  mov     r14b, 1
0x140003840  mov     [r15+rbx+1B8h], dil
0x140003848  movzx   edx, sil; OldIrql
0x14000384c  mov     dword ptr [r13+930h], 0FFFFFFFFh
0x140003857  mov     rcx, r12; SpinLock
0x14000385a  call    cs:__imp_ExReleaseSpinLockExclusive
0x140003861  nop     dword ptr [rax+rax+00h]
0x140003866  test    r14b, r14b
0x140003869  jz      loc_140003A85
0x14000386f  mov     rbx, [rbx+188h]
0x140003876  mov     r13d, [rbp+300h+var_2F8]
0x14000387a  mov     rsi, rbx
0x14000387d  test    r13d, r13d
0x140003880  jnz     loc_140003635
0x140003886  lea     r12, [rbx+178h]
0x14000388d  xor     edx, edx
0x14000388f  mov     rcx, r12
0x140003892  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140003899  nop     dword ptr [rax+rax+00h]
0x14000389e  mov     r14d, 0FFFFFFFFh
0x1400038a4  lock xadd [rbx+r15*4+160h], r14d
0x1400038ae  cmp     r14d, 1
0x1400038b2  jnz     loc_140003A74
0x1400038b8  mov     eax, edi
0x1400038ba  mov     [rbp+300h+var_2FC], edi
0x1400038bd  lea     rcx, [rbx+r15*4]
0x1400038c1  mov     esi, 4
0x1400038c6  mov     [rcx+150h], eax
0x1400038cc  mov     ecx, 0FFFFFFFFh
0x1400038d1  mov     edx, [rbx+150h]
0x1400038d7  lea     eax, [rdx-1]
0x1400038da  cmp     eax, 0FFFFFFFDh
0x1400038dd  jbe     loc_140003AEC
0x1400038e3  mov     eax, [rbx+154h]
0x1400038e9  test    eax, eax
0x1400038eb  jnz     loc_140003AB0
0x1400038f1  mov     eax, [rbx+158h]
0x1400038f7  test    eax, eax
0x1400038f9  jnz     loc_140003AC4
0x1400038ff  mov     eax, [rbx+15Ch]
0x140003905  test    eax, eax
0x140003907  jnz     loc_140003AD8
0x14000390d  cmp     ecx, 0FFFFFFFFh
0x140003910  lea     r15, WPP_GLOBAL_Control
0x140003917  mov     r14d, edi
0x14000391a  cmovnz  r14d, ecx
0x14000391e  mov     ecx, [rbx+140h]
0x140003924  cmp     ecx, 1
0x140003927  jnz     loc_140004211
0x14000392d  xor     eax, eax
0x14000392f  xorps   xmm0, xmm0
0x140003932  mov     r8d, ecx
0x140003935  mov     [rbp+300h+Event.Header.WaitListHead.Blink], rax
0x140003939  movzx   ecx, r8b
0x14000393d  mov     [rbp+300h+var_2A8], rax
0x140003941  xor     edx, edx
0x140003943  mov     [rbp+300h+var_2A0], eax
0x140003946  movups  [rbp+300h+var_2D0], xmm0
0x14000394a  movups  xmmword ptr [rbp+300h+Event.Header], xmm0
0x14000394e  call    cs:__imp_RxCeAllocateIrp
0x140003955  nop     dword ptr [rax+rax+00h]
0x14000395a  mov     r15, rax
0x14000395d  test    rax, rax
0x140003960  jz      loc_140004244
0x140003966  xor     r8d, r8d; State
0x140003969  mov     dword ptr [rbp+300h+var_2D0], 103h
0x140003970  xor     edx, edx; Type
0x140003972  mov     qword ptr [rbp+300h+var_2D0+8], rdi
0x140003976  lea     rcx, [rbp+300h+Event]; Event
0x14000397a  call    cs:__imp_KeInitializeEvent
0x140003981  nop     dword ptr [rax+rax+00h]
0x140003986  mov     rax, [r15+0B8h]
0x14000398d  lea     rcx, SmbWskSynchronousIrpComplete
0x140003994  mov     [rax-10h], rcx
0x140003998  lea     rcx, [rbp+300h+var_2D0]
0x14000399c  mov     [rax-8], rcx
0x1400039a0  mov     byte ptr [rax-45h], 0E0h
0x1400039a4  mov     eax, 0CCCCCCCDh
0x1400039a9  mov     r10, [rbx+68h]
0x1400039ad  imul    ecx, r14d, 3E8h
0x1400039b4  mov     r8, [r10]
0x1400039b7  mul     ecx
0x1400039b9  mov     dword ptr [rbp+300h+var_2A8+4], ecx
0x1400039bc  shr     edx, 3
0x1400039bf  test    r14d, r14d
0x1400039c2  jz      loc_140003AF5
0x1400039c8  mov     dword ptr [rbp+300h+var_2A8], 1
0x1400039cf  cmp     edx, 3E8h
0x1400039d5  jbe     loc_140003AF8
0x1400039db  mov     [rbp+300h+var_2A0], 3E8h
0x1400039e2  mov     rax, [r8]
0x1400039e5  lea     rcx, [rbp+300h+var_2A8]
0x1400039e9  mov     [rsp+3A0h+var_358], r15
0x1400039ee  xor     r9d, r9d
0x1400039f1  mov     [rsp+3A0h+var_360], rdi
0x1400039f6  mov     edx, 2
0x1400039fb  mov     [rsp+3A0h+var_368], rdi
0x140003a00  mov     r8d, 98000004h
0x140003a06  mov     [rsp+3A0h+var_370], rdi
0x140003a0b  mov     [rsp+3A0h+var_378], rcx
0x140003a10  mov     rcx, r10
0x140003a13  mov     [rsp+3A0h+BugCheckParameter4], 0Ch
0x140003a1c  call    _guard_dispatch_icall
0x140003a21  mov     [rbp+300h+var_2F0], eax
0x140003a24  cmp     eax, 103h
0x140003a29  jz      loc_14000424E
0x140003a2f  mov     rcx, r15; pIrp
0x140003a32  call    cs:__imp_RxCeFreeIrp
0x140003a39  nop     dword ptr [rax+rax+00h]
0x140003a3e  mov     eax, [rbp+300h+var_2F0]
0x140003a41  lea     r15, WPP_GLOBAL_Control
0x140003a48  test    eax, eax
0x140003a4a  js      short loc_140003A63
0x140003a4c  mov     rcx, cs:WPP_GLOBAL_Control
0x140003a53  cmp     rcx, r15
0x140003a56  jz      short loc_140003A63
0x140003a58  mov     eax, [rcx+2Ch]
0x140003a5b  test    al, 4
0x140003a5d  jnz     loc_14000427A
0x140003a63  mov     r13d, [rbp+300h+var_2F4]
0x140003a67  lea     eax, [r13-2]
0x140003a6b  cmp     eax, 1
0x140003a6e  jbe     loc_1400040E6
0x140003a74  xor     edx, edx
0x140003a76  mov     rcx, r12
0x140003a79  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140003a80  nop     dword ptr [rax+rax+00h]
0x140003a85  mov     rcx, [rbp+300h+var_40]
0x140003a8c  xor     rcx, rsp; StackCookie
0x140003a8f  call    __security_check_cookie
0x140003a94  mov     rbx, [rsp+3A0h+arg_18]
0x140003a9c  add     rsp, 370h
0x140003aa3  pop     r15
0x140003aa5  pop     r14
0x140003aa7  pop     r13
0x140003aa9  pop     r12
0x140003aab  pop     rdi
  ... truncated ...
```
