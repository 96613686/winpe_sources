# HidpIrpMajorCreate

- ea: `0x18000b140`
- end: `0x18000c246`
- name: `HidpIrpMajorCreate`
- size: `4358`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180004c00`

## callees

- `0x18000a15c`
- `0x18000b140`
- `0x18000c250`
- `0x18000c2c0`
- `0x18000c2e0`
- `0x18000c5c0`
- `0x18000c948`
- `0x18000ca30`
- `0x180011ab0`
- `0x1800127d0`
- `0x180013f7c`
- `0x18001b2b4`
- `0x18001b744`
- `0x18001ee14`
- `0x18001f148`
- `0x180027d00`

## import_xrefs

- `ntoskrnl!IoGetRequestorSessionId` at `0x18000b1af`
- `ntoskrnl!IoGetRequestorSessionId` at `0x18000b1af`
- `ntoskrnl!IoGetInitiatorProcess` at `0x18000b47c`
- `ntoskrnl!IoGetInitiatorProcess` at `0x18000b47c`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000b508`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c074`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c0a6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c0d8`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c111`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c14a`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000b508`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c074`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c0a6`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c0d8`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c111`
- `ntoskrnl!PsGetCurrentProcessId` at `0x18000c14a`
- `ntoskrnl!SeQuerySessionIdToken` at `0x18000b763`
- `ntoskrnl!SeQuerySessionIdToken` at `0x18000b763`
- `ntoskrnl!PsGetProcessImageFileName` at `0x18000b797`
- `ntoskrnl!PsGetProcessImageFileName` at `0x18000b797`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000b51b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c087`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c0b9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c0eb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c124`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c15d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000b51b`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c087`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c0b9`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c0eb`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c124`
- `ntoskrnl!PsGetCurrentThreadId` at `0x18000c15d`
- `ntoskrnl!IoGetRequestorProcess` at `0x18000b77f`
- `ntoskrnl!IoGetRequestorProcess` at `0x18000b77f`
- `ntoskrnl!KeInitializeSpinLock` at `0x18000b383`
- `ntoskrnl!KeInitializeSpinLock` at `0x18000b383`
- `ntoskrnl!IofCompleteRequest` at `0x18000b66b`
- `ntoskrnl!IofCompleteRequest` at `0x18000b66b`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b892`
- `ntoskrnl!ExFreePoolWithTag` at `0x18000b892`
- `ntoskrnl!ExAllocatePool2` at `0x18000b217`
- `ntoskrnl!ExAllocatePool2` at `0x18000b7da`
- `ntoskrnl!ExAllocatePool2` at `0x18000b217`
- `ntoskrnl!ExAllocatePool2` at `0x18000b7da`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000b645`
- `ntoskrnl!KeReleaseSpinLock` at `0x18000b645`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000b311`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x18000b311`

## string_xrefs

- `0x18000b9d8`: `Receive unexpected Open for FDO`

## pseudocode

```c
__int64 __fastcall HidpIrpMajorCreate(__int64 a1, IRP *a2)
{
  _QWORD *FdoExtension; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  _QWORD *v8; // r9
  __int64 v9; // rsi
  KSPIN_LOCK v10; // rbx
  __int64 v11; // rdi
  KSPIN_LOCK v12; // rsi
  int v13; // r8d
  NTSTATUS RequestorSessionId; // r12d
  int v15; // edx
  __int64 v16; // rax
  unsigned __int16 v17; // r11
  int v18; // r10d
  char v19; // di
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // rax
  KSPIN_LOCK *v23; // r9
  __int64 v24; // rdx
  bool v25; // zf
  int v26; // eax
  __int64 v27; // rdx
  KSPIN_LOCK v28; // rcx
  __int64 v29; // rdx
  KSPIN_LOCK v30; // rcx
  PEPROCESS InitiatorProcess; // rcx
  int v32; // edx
  HANDLE CurrentThreadId; // rax
  __int64 v34; // rdx
  __int64 v35; // rcx
  __int64 v36; // r8
  __int64 v37; // r9
  int v38; // eax
  int v39; // r8d
  __int64 v40; // rdx
  PDEVICE_OBJECT v42; // rcx
  __int64 v43; // rdx
  void *v44; // rcx
  __int64 v45; // rax
  void *Pool2; // rcx
  PDEVICE_OBJECT v47; // rcx
  KSPIN_LOCK *v48; // rax
  KSPIN_LOCK v49; // rcx
  KSPIN_LOCK **v50; // r8
  unsigned __int64 v51; // rdx
  bool v52; // di
  KSPIN_LOCK v53; // rcx
  const char *v54; // rdx
  int v55; // edx
  bool v56; // di
  __int64 v57; // rdx
  _DEVICE_OBJECT *AttachedDevice; // rcx
  bool v59; // di
  __int64 v60; // rdx
  int v61; // eax
  __int64 v62; // r10
  __int64 v63; // rcx
  __int64 v64; // rdx
  int v65; // [rsp+20h] [rbp-108h]
  int v66; // [rsp+28h] [rbp-100h]
  __int16 v67; // [rsp+30h] [rbp-F8h]
  __int16 v68; // [rsp+30h] [rbp-F8h]
  __int64 v69; // [rsp+40h] [rbp-E8h]
  __int64 v70; // [rsp+40h] [rbp-E8h]
  int v71; // [rsp+48h] [rbp-E0h]
  int v72; // [rsp+48h] [rbp-E0h]
  __int64 v73; // [rsp+50h] [rbp-D8h]
  __int64 v74; // [rsp+50h] [rbp-D8h]
  char v75; // [rsp+58h] [rbp-D0h]
  char v76; // [rsp+58h] [rbp-D0h]
  __int64 v77; // [rsp+60h] [rbp-C8h]
  char v78; // [rsp+60h] [rbp-C8h]
  __int64 v79; // [rsp+68h] [rbp-C0h]
  KSPIN_LOCK *P; // [rsp+A0h] [rbp-88h]
  ULONG pSessionId; // [rsp+A8h] [rbp-80h] BYREF
  int v82; // [rsp+ACh] [rbp-7Ch]
  int v83; // [rsp+B0h] [rbp-78h]
  __int64 HidclassCollection; // [rsp+B8h] [rbp-70h]
  __int64 v85; // [rsp+C0h] [rbp-68h]
  int v86; // [rsp+C8h] [rbp-60h]
  __int64 v87; // [rsp+D0h] [rbp-58h]
  void *Src; // [rsp+D8h] [rbp-50h]
  PKSPIN_LOCK SpinLock; // [rsp+E0h] [rbp-48h]
  char v90; // [rsp+130h] [rbp+8h]
  char Size; // [rsp+140h] [rbp+18h]
  unsigned int Sizea; // [rsp+140h] [rbp+18h]
  KIRQL NewIrql; // [rsp+148h] [rbp+20h]

  pSessionId = 0;
  FdoExtension = (_QWORD *)GetFdoExtension();
  v8 = FdoExtension;
  if ( !*(_BYTE *)(v6 + 24) )
  {
    RequestorSessionId = -1073741823;
    v52 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v52 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v5) = v52;
      WPP_RECORDER_AND_TRACE_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        v5,
        v7,
        FdoExtension[84],
        3,
        4,
        25,
        (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
        *FdoExtension,
        (char)a2,
        1);
    }
    v53 = a1 + 32;
    v54 = "Receive unexpected Open for FDO";
    goto LABEL_90;
  }
  v9 = *(_QWORD *)(a1 + 96);
  v10 = a1 + 32;
  v11 = *(_QWORD *)(v5 + 184);
  v12 = v9 + 32;
  v85 = v11;
  if ( (unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(v6, v5, v7, FdoExtension) )
    v87 = *(_QWORD *)(v11 + 48);
  else
    v87 = 0;
  RequestorSessionId = IoGetRequestorSessionId(a2, &pSessionId);
  if ( RequestorSessionId < 0 )
  {
    v56 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v56 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v57 = *(_QWORD *)(v10 + 64);
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v78 = RequestorSessionId;
    v75 = (char)a2;
    v73 = *(_QWORD *)(v10 + 48);
    v71 = *(_DWORD *)(v10 + 8);
    v69 = *(_QWORD *)(v57 + 32);
    v67 = 26;
LABEL_100:
    LOBYTE(v57) = v56;
    WPP_RECORDER_AND_TRACE_SF_qdqqd(
      (_DWORD)AttachedDevice,
      v57,
      v13,
      *(_QWORD *)(v12 + 672),
      2,
      4,
      v67,
      (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
      v69,
      v71,
      v73,
      v75,
      v78);
    goto LABEL_46;
  }
  if ( !pSessionId )
  {
    v43 = *(_QWORD *)(*(_QWORD *)(v11 + 8) + 8LL);
    v44 = *(void **)(v43 + 32);
    if ( !v44 )
      v44 = *(void **)(v43 + 48);
    RequestorSessionId = SeQuerySessionIdToken(v44, &pSessionId);
  }
  a2->IoStatus.Information = 0;
  HidclassCollection = GetHidclassCollection(v12, *(unsigned int *)(v10 + 8));
  if ( !HidclassCollection )
  {
    RequestorSessionId = -1073741667;
    v59 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v7) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v59 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v55 = *(_DWORD *)(v10 + 8);
      LOBYTE(v55) = v59;
      WPP_RECORDER_AND_TRACE_SF_qdqqLd(WPP_GLOBAL_Control->AttachedDevice, v55, v7, *(_QWORD *)(v12 + 672));
    }
    v54 = "Fail to find collection";
    v53 = v12;
LABEL_90:
    TraceLoggingIrpCreateFailed(v53, v54, v7, v8);
    goto LABEL_46;
  }
  Size = CheckPrivilege(v12, v10, a2);
  P = (KSPIN_LOCK *)ExAllocatePool2(65, 192, 1130654024);
  if ( !P )
  {
    RequestorSessionId = -1073741670;
    v56 = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
       && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
       && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v56 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_46;
    v57 = *(_QWORD *)(v10 + 64);
    AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
    v78 = -102;
    v75 = (char)a2;
    v73 = *(_QWORD *)(v10 + 48);
    v71 = *(_DWORD *)(v10 + 8);
    v69 = *(_QWORD *)(v57 + 32);
    v67 = 28;
    goto LABEL_100;
  }
  v16 = *(_QWORD *)(v11 + 8);
  v17 = *(_WORD *)(v11 + 26);
  v83 = v17;
  v18 = *(_DWORD *)(v16 + 16);
  v82 = v18;
  v19 = 1;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
    || (LOBYTE(v15) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
  {
    LOBYTE(v15) = 0;
  }
  if ( (_BYTE)v15 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LODWORD(v79) = v18 & 1;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_qdqqLLLDL(WPP_GLOBAL_Control->AttachedDevice, v15, v13, *(_QWORD *)(v12 + 672));
    v17 = v83;
    LOBYTE(v18) = v82;
  }
  if ( *(_DWORD *)(v10 + 156) )
  {
    v42 = WPP_GLOBAL_Control;
    LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_69;
    v79 = *(_QWORD *)(v10 + 248);
    v77 = *(_QWORD *)(v10 + 240);
    goto LABEL_163;
  }
  if ( *(_DWORD *)(v10 + 136) && !v17 )
  {
    v42 = WPP_GLOBAL_Control;
    LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_69;
    v79 = *(_QWORD *)(v10 + 168);
    v77 = *(_QWORD *)(v10 + 160);
LABEL_163:
    WPP_RECORDER_AND_TRACE_SF_qdqqqq(v42->AttachedDevice, v15, v13, *(_QWORD *)(v12 + 672));
LABEL_69:
    RequestorSessionId = -1073741757;
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v19 = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v19 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_73;
    v60 = *(_QWORD *)(v10 + 64);
    LODWORD(v77) = -1073741757;
    v76 = (char)a2;
    v74 = *(_QWORD *)(v10 + 48);
    v72 = *(_DWORD *)(v10 + 8);
    v70 = *(_QWORD *)(v60 + 32);
    v68 = 36;
    goto LABEL_169;
  }
  if ( *(_DWORD *)(v10 + 148) && (v18 & 1) != 0 )
  {
    v42 = WPP_GLOBAL_Control;
    LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_69;
    v79 = *(_QWORD *)(v10 + 216);
    v77 = *(_QWORD *)(v10 + 208);
    goto LABEL_163;
  }
  if ( *(_DWORD *)(v10 + 152) && (v18 & 2) != 0 )
  {
    v42 = WPP_GLOBAL_Control;
    LOBYTE(v15) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_69;
    v79 = *(_QWORD *)(v10 + 232);
    v77 = *(_QWORD *)(v10 + 224);
    goto LABEL_163;
  }
  if ( *(_DWORD *)(v10 + 140) && (v17 & 1) == 0 )
  {
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v15) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
    {
      LOBYTE(v15) = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_69;
    v79 = *(_QWORD *)(v10 + 184);
    v77 = *(_QWORD *)(v10 + 176);
    goto LABEL_163;
  }
  if ( *(_DWORD *)(v10 + 144) && (v17 & 2) == 0 )
  {
    v42 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || (LOBYTE(v15) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
    {
      LOBYTE(v15) = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !(_BYTE)v15 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_69;
    v79 = *(_QWORD *)(v10 + 200);
    v77 = *(_QWORD *)(v10 + 192);
    goto LABEL_163;
  }
  if ( (*(_DWORD *)(v85 + 16) & 1) != 0 )
  {
    RequestorSessionId = -1073741565;
    v47 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 3u )
    {
      v19 = 0;
    }
    LOBYTE(v13) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( !v19 && WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_73;
    v60 = *(_QWORD *)(v10 + 64);
    LODWORD(v77) = -1073741565;
    v76 = (char)a2;
    v74 = *(_QWORD *)(v10 + 48);
    v72 = *(_DWORD *)(v10 + 8);
    v70 = *(_QWORD *)(v60 + 32);
    v68 = 37;
LABEL_169:
    LOBYTE(v60) = v19;
    WPP_RECORDER_AND_TRACE_SF_qdqqd(
      v47->AttachedDevice,
      v60,
      v13,
      *(_QWORD *)(v12 + 672),
      3,
      4,
      v68,
      (__int64)WPP_09551ba6d0fe3383c1d3f23d6d3d8f25_Traceguids,
      v70,
      v72,
      v74,
      v76,
      v77,
      v79);
LABEL_73:
    ExFreePoolWithTag(P, 0);
    goto LABEL_46;
  }
  SpinLock = (PKSPIN_LOCK)(HidclassCollection + 40);
  NewIrql = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(HidclassCollection + 40));
  if ( *(_DWORD *)(v12 + 1720) && (unsigned int)(*(_DWORD *)(v10 + 4) - 3) <= 2 )
  {
    v22 = v85;
    *(_DWORD *)P = *(_DWORD *)(v10 + 8);
    P[1] = v12;
    P[2] = v10;
    P[12] = *(_QWORD *)(v22 + 48);
    *((_BYTE *)P + 117) = 0;
    P[6] = (KSPIN_LOCK)(P + 5);
    P[5] = (KSPIN_LOCK)(P + 5);
    P[4] = (KSPIN_LOCK)(P + 3);
    P[3] = (KSPIN_LOCK)(P + 3);
    KeInitializeSpinLock(P + 9);
    v23 = P;
    v24 = HidclassCollection;
    v25 = (v82 & 1) == 0;
    v86 = v82 & 1;
    *((_BYTE *)P + 114) = 0;
    if ( !v25 && *(_DWORD *)(v24 + 12) == 2 )
    {
      v61 = *(_DWORD *)(v24 + 64);
      if ( v61 )
      {
        *((_DWORD *)P + 22) = v61;
        if ( *(_DWORD *)(v24 + 64) )
        {
          v62 = v24 + 48;
          while ( 1 )
          {
            v48 = *(KSPIN_LOCK **)v62;
            if ( *(_QWORD *)(*(_QWORD *)v62 + 8LL) != v62 )
              break;
            v49 = *v48;
            if ( *(KSPIN_LOCK **)(*v48 + 8) != v48 )
              break;
            *(_QWORD *)(v24 + 48) = v49;
            *(_QWORD *)(v49 + 8) = v62;
            v50 = (KSPIN_LOCK **)P[6];
            if ( *v50 != P + 5 )
              break;
            *v48 = (KSPIN_LOCK)(P + 5);
            v48[1] = (KSPIN_LOCK)v50;
            *v50 = v48;
            P[6] = (KSPIN_LOCK)v48;
            v25 = (*(_DWORD *)(v24 + 64))-- == 1;
            if ( v25 )
              goto LABEL_78;
          }
LABEL_25:
          __fastfail(3u);
        }
LABEL_78:
        v51 = (__int64)((unsigned __int128)((MEMORY[0xFFFFF78000000014] - *(_QWORD *)(v24 + 72) + 5000LL)
                                          * (__int128)0x346DC5D63886594BLL) >> 64) >> 11;
        TraceLoggingUnreadKeyboardReportsFlushed(v12, *((unsigned int *)P + 22), v51 + (v51 >> 63));
        v23 = P;
        v24 = HidclassCollection;
      }
    }
    *((_DWORD *)v23 + 37) = 1;
    v26 = *(_DWORD *)(v12 + 1764);
    if ( !v26 || (v90 = 1, (v26 & 1) != 0) && *(_WORD *)(v24 + 8) == 13 && *(_WORD *)(v24 + 10) == 4 )
      v90 = 0;
    v27 = v24 + 24;
    *((_DWORD *)v23 + 23) = 32;
    *((_DWORD *)v23 + 32) = 0;
    v28 = *(_QWORD *)v27;
    if ( *(_QWORD *)(*(_QWORD *)v27 + 8LL) != v27 )
      goto LABEL_25;
    v23[8] = v27;
    v23[7] = v28;
    *(_QWORD *)(v28 + 8) = v23 + 7;
    *(_QWORD *)v27 = v23 + 7;
    v29 = v85;
    *((_WORD *)v23 + 52) = *(_WORD *)(v85 + 24);
    *((_DWORD *)v23 + 27) = *(_DWORD *)(*(_QWORD *)(v29 + 8) + 16LL);
    v30 = v23[12];
    *((_WORD *)v23 + 56) = *(_WORD *)(v29 + 26);
    *((_BYTE *)v23 + 118) = Size;
    *((_DWORD *)v23 + 30) = 0;
    *((_DWORD *)v23 + 31) = pSessionId;
    InitiatorProcess = (PEPROCESS)IoGetInitiatorProcess(v30);
    P[17] = (KSPIN_LOCK)InitiatorProcess;
    *((_DWORD *)P + 36) = 0;
    if ( (a2->RequestorMode == 1 || (*(_BYTE *)(v85 + 2) & 1) != 0)
      && (InitiatorProcess || (InitiatorProcess = IoGetRequestorProcess(a2)) != 0) )
    {
      Src = (void *)PsGetProcessImageFileName(InitiatorProcess);
      if ( Src )
      {
        v45 = -1;
        do
          ++v45;
        while ( *((_BYTE *)Src + v45) );
        Sizea = v45;
        Pool2 = (void *)ExAllocatePool2(64, (unsigned int)(v45 + 1), 1130654024);
        P[19] = (KSPIN_LOCK)Pool2;
        if ( Pool2 )
          memmove(Pool2, Src, Sizea);
      }
    }
    v32 = HidclassCollection;
    *(_QWORD *)(*(_QWORD *)(v85 + 48) + 24LL) = P;
    *((_BYTE *)P + 160) = a2->RequestorMode;
    HidpFdoUpdateOpenCounts(v12, v32, v10, (_DWORD)P, 1, v90);
    *(_QWORD *)(v10 + 160) = PsGetCurrentProcessId();
    CurrentThreadId = PsGetCurrentThreadId();
    v25 = v86 == 0;
    *(_QWORD *)(v10 + 168) = CurrentThreadId;
    if ( !v25 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v10 + 140), 1u);
      v63 = HidclassCollection;
      if ( _InterlockedIncrement((volatile signed __int32 *)(HidclassCollection + 356)) == 1 )
        _InterlockedExchange64((volatile __int64 *)(v63 + 408), 0);
      *(_QWORD *)(v10 + 176) = PsGetCurrentProcessId();
      *(_QWORD *)(v10 + 184) = PsGetCurrentThreadId();
    }
    if ( (v82 & 2) != 0 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v10 + 144), 1u);
      *(_QWORD *)(v10 + 192) = PsGetCurrentProcessId();
      *(_QWORD *)(v10 + 200) = PsGetCurrentThreadId();
    }
    v38 = v83;
    if ( (v83 & 1) == 0 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v10 + 148), 1u);
      *(_QWORD *)(v10 + 208) = PsGetCurrentProcessId();
      *(_QWORD *)(v10 + 216) = PsGetCurrentThreadId();
      v38 = v83;
    }
    if ( (v38 & 2) == 0 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v10 + 152), 1u);
      *(_QWORD *)(v10 + 224) = PsGetCurrentProcessId();
      *(_QWORD *)(v10 + 232) = PsGetCurrentThreadId();
      v38 = v83;
    }
    if ( !v38 )
    {
      _InterlockedAdd((volatile signed __int32 *)(v10 + 156), 1u);
      *(_QWORD *)(v10 + 240) = PsGetCurrentProcessId();
      *(_QWORD *)(v10 + 248) = PsGetCurrentThreadId();
    }
    if ( (unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(v35, v34, v36, v37) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v19 = 0;
      }
      if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v40 = *(_QWORD *)(v10 + 64);
        LOBYTE(v40) = v19;
        LOBYTE(v39) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqqqlllllL(
          WPP_GLOBAL_Control->AttachedDevice,
          v40,
          v39,
          *(_QWORD *)(v12 + 672),
          v65,
          v66);
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v19 = 0;
      }
      if ( v19 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v64 = *(_QWORD *)(v10 + 64);
        LOBYTE(v64) = v19;
        LOBYTE(v39) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qdqqlllllL(
          WPP_GLOBAL_Control->AttachedDevice,
          v64,
          v39,
          *(_QWORD *)(v12 + 672),
          v65,
          v66);
      }
    }
    P = 0;
  }
  else
  {
    RequestorSessionId = -1073741667;
    TraceLoggingIrpCreateFailed(v12, "Device not started", v20, v21);
  }
  KeReleaseSpinLock(SpinLock, NewIrql);
  if ( P )
    goto LABEL_73;
LABEL_46:
  a2->IoStatus.Status = RequestorSessionId;
  IofCompleteRequest(a2, 0);
  return (unsigned int)RequestorSessionId;
}

```

## disassembly

```asm
0x18000b140  mov     rax, rsp
0x18000b143  push    rbx
0x18000b144  push    rsi
0x18000b145  push    rdi
0x18000b146  push    r12
0x18000b148  push    r13
0x18000b14a  push    r14
0x18000b14c  push    r15
0x18000b14e  sub     rsp, 0F0h
0x18000b155  xor     r15d, r15d
0x18000b158  mov     r13, rdx
0x18000b15b  mov     [rax-80h], r15d
0x18000b15f  mov     rbx, rcx
0x18000b162  call    GetFdoExtension
0x18000b167  mov     r9, rax
0x18000b16a  cmp     [rcx+18h], r15b
0x18000b16e  jz      loc_18000B940
0x18000b174  mov     rsi, [rbx+60h]
0x18000b178  add     rbx, 20h ; ' '
0x18000b17c  mov     rdi, [rdx+0B8h]
0x18000b183  add     rsi, 20h ; ' '
0x18000b187  mov     [rsp+128h+var_68], rdi
0x18000b18f  call    Feature_HCTI01__private_IsEnabledDeviceUsageNoInline
0x18000b194  test    eax, eax
0x18000b196  jnz     loc_18000B3FC
0x18000b19c  mov     [rsp+128h+var_58], r15
0x18000b1a4  lea     rdx, [rsp+128h+pSessionId]; pSessionId
0x18000b1ac  mov     rcx, r13; Irp
0x18000b1af  call    cs:__imp_IoGetRequestorSessionId
0x18000b1b6  nop     dword ptr [rax+rax+00h]
0x18000b1bb  mov     r12d, eax
0x18000b1be  test    eax, eax
0x18000b1c0  js      loc_18000BA2E
0x18000b1c6  cmp     [rsp+128h+pSessionId], r15d
0x18000b1ce  jz      loc_18000B746
0x18000b1d4  mov     [r13+38h], r15
0x18000b1d8  mov     rcx, rsi
0x18000b1db  mov     edx, [rbx+8]
0x18000b1de  call    GetHidclassCollection
0x18000b1e3  mov     [rsp+128h+var_70], rax
0x18000b1eb  test    rax, rax
0x18000b1ee  jz      loc_18000BB1A
0x18000b1f4  mov     r8, r13
0x18000b1f7  mov     rdx, rbx
0x18000b1fa  mov     rcx, rsi
0x18000b1fd  call    CheckPrivilege
0x18000b202  mov     edx, 0C0h
0x18000b207  mov     byte ptr [rsp+128h+Size], al
0x18000b20e  mov     r8d, 43646948h
0x18000b214  lea     ecx, [rdx-7Fh]
0x18000b217  call    cs:__imp_ExAllocatePool2
0x18000b21e  nop     dword ptr [rax+rax+00h]
0x18000b223  mov     [rsp+128h+P], rax
0x18000b22b  test    rax, rax
0x18000b22e  jz      loc_18000BB73
0x18000b234  mov     rax, [rdi+8]
0x18000b238  movzx   r11d, word ptr [rdi+1Ah]
0x18000b23d  mov     [rsp+128h+var_78], r11d
0x18000b245  mov     r10d, [rax+10h]
0x18000b249  mov     [rsp+128h+var_7C], r10d
0x18000b251  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b258  lea     r14, WPP_GLOBAL_Control
0x18000b25f  mov     edi, 1
0x18000b264  lea     r9d, [rdi+3]
0x18000b268  cmp     rcx, r14
0x18000b26b  jnz     loc_18000B835
0x18000b271  mov     dl, r15b
0x18000b274  lea     r15, WPP_RECORDER_INITIALIZED
0x18000b27b  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000b282  setnz   r8b
0x18000b286  xor     eax, eax
0x18000b288  test    dl, dl
0x18000b28a  jnz     loc_18000B6C8
0x18000b290  test    r8b, r8b
0x18000b293  jnz     loc_18000B6C8
0x18000b299  cmp     [rbx+9Ch], eax
0x18000b29f  jnz     loc_18000BBCC
0x18000b2a5  cmp     [rbx+88h], eax
0x18000b2ab  jnz     loc_18000B68E
0x18000b2b1  cmp     [rbx+94h], eax
0x18000b2b7  jnz     loc_18000BCB5
0x18000b2bd  cmp     [rbx+98h], eax
0x18000b2c3  jnz     loc_18000BD43
0x18000b2c9  xor     r10d, r10d
0x18000b2cc  cmp     [rbx+8Ch], r10d
0x18000b2d3  jnz     loc_18000BDD2
0x18000b2d9  cmp     [rbx+90h], r10d
0x18000b2e0  jnz     loc_18000BE58
0x18000b2e6  mov     rax, [rsp+128h+var_68]
0x18000b2ee  mov     eax, [rax+10h]
0x18000b2f1  test    dil, al
0x18000b2f4  jnz     loc_18000BFAC
0x18000b2fa  mov     rax, [rsp+128h+var_70]
0x18000b302  add     rax, 28h ; '('
0x18000b306  mov     rcx, rax; SpinLock
0x18000b309  mov     [rsp+128h+SpinLock], rax
0x18000b311  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x18000b318  nop     dword ptr [rax+rax+00h]
0x18000b31d  cmp     dword ptr [rsi+6B8h], 0
0x18000b324  mov     [rsp+128h+NewIrql], al
0x18000b32b  jz      loc_18000B40D
0x18000b331  mov     ecx, [rbx+4]
0x18000b334  sub     ecx, 3
0x18000b337  cmp     ecx, 2
0x18000b33a  ja      loc_18000B40D
0x18000b340  mov     ecx, [rbx+8]
0x18000b343  mov     rdx, [rsp+128h+P]
0x18000b34b  mov     rax, [rsp+128h+var_68]
0x18000b353  mov     [rdx], ecx
0x18000b355  lea     rcx, [rdx+48h]; SpinLock
0x18000b359  mov     [rdx+8], rsi
0x18000b35d  mov     [rdx+10h], rbx
0x18000b361  mov     rax, [rax+30h]
0x18000b365  mov     [rdx+60h], rax
0x18000b369  lea     rax, [rdx+28h]
0x18000b36d  mov     byte ptr [rdx+75h], 0
0x18000b371  mov     [rax+8], rax
0x18000b375  mov     [rax], rax
0x18000b378  lea     rax, [rdx+18h]
0x18000b37c  mov     [rax+8], rax
0x18000b380  mov     [rax], rax
0x18000b383  call    cs:__imp_KeInitializeSpinLock
0x18000b38a  nop     dword ptr [rax+rax+00h]
0x18000b38f  mov     r9, [rsp+128h+P]
0x18000b397  xor     r11d, r11d
0x18000b39a  mov     eax, [rsp+128h+var_7C]
0x18000b3a1  mov     rdx, [rsp+128h+var_70]
0x18000b3a9  and     eax, edi
0x18000b3ab  mov     [rsp+128h+var_60], eax
0x18000b3b2  mov     [r9+72h], r11b
0x18000b3b6  jnz     loc_18000BFF0
0x18000b3bc  mov     [r9+94h], edi
0x18000b3c3  mov     eax, [rsi+6E4h]
0x18000b3c9  test    eax, eax
0x18000b3cb  jnz     loc_18000C01C
0x18000b3d1  mov     [rsp+128h+arg_0], r11b
0x18000b3d9  add     rdx, 18h
0x18000b3dd  mov     dword ptr [r9+5Ch], 20h ; ' '
0x18000b3e5  mov     [r9+80h], r11d
0x18000b3ec  mov     rcx, [rdx]
0x18000b3ef  cmp     [rcx+8], rdx
0x18000b3f3  jz      short loc_18000B427
0x18000b3f5  mov     ecx, 3
0x18000b3fa  int     29h; Win8: RtlFailFast(ecx)
0x18000b3fc  mov     rax, [rdi+30h]
0x18000b400  mov     [rsp+128h+var_58], rax
0x18000b408  jmp     loc_18000B1A4
0x18000b40d  lea     rdx, aDeviceNotStart; "Device not started"
0x18000b414  mov     rcx, rsi
0x18000b417  mov     r12d, 0C000009Dh
0x18000b41d  call    TraceLoggingIrpCreateFailed
0x18000b422  jmp     loc_18000B636
0x18000b427  lea     rax, [r9+38h]
0x18000b42b  mov     [rax+8], rdx
0x18000b42f  mov     [rax], rcx
0x18000b432  mov     [rcx+8], rax
0x18000b436  mov     [rdx], rax
0x18000b439  mov     rdx, [rsp+128h+var_68]
0x18000b441  movzx   eax, word ptr [rdx+18h]
0x18000b445  mov     [r9+68h], ax
0x18000b44a  mov     rax, [rdx+8]
0x18000b44e  mov     ecx, [rax+10h]
0x18000b451  mov     [r9+6Ch], ecx
0x18000b455  movzx   eax, word ptr [rdx+1Ah]
0x18000b459  mov     rcx, [r9+60h]
0x18000b45d  mov     [r9+70h], ax
0x18000b462  mov     al, byte ptr [rsp+128h+Size]
0x18000b469  mov     [r9+76h], al
0x18000b46d  mov     [r9+78h], r11d
0x18000b471  mov     eax, [rsp+128h+pSessionId]
0x18000b478  mov     [r9+7Ch], eax
0x18000b47c  call    cs:__imp_IoGetInitiatorProcess
0x18000b483  nop     dword ptr [rax+rax+00h]
0x18000b488  mov     rcx, rax
0x18000b48b  mov     rax, [rsp+128h+P]
0x18000b493  mov     [rax+88h], rcx
0x18000b49a  mov     dword ptr [rax+90h], 0
0x18000b4a4  cmp     [r13+40h], dil
0x18000b4a8  jz      loc_18000B777
0x18000b4ae  mov     rax, [rsp+128h+var_68]
0x18000b4b6  test    [rax+2], dil
0x18000b4ba  jnz     loc_18000B777
0x18000b4c0  mov     rcx, [rsp+128h+P]
0x18000b4c8  mov     r8, rbx
0x18000b4cb  mov     rax, [rsp+128h+var_68]
0x18000b4d3  mov     r9, rcx
0x18000b4d6  mov     rdx, [rsp+128h+var_70]
0x18000b4de  mov     rax, [rax+30h]
0x18000b4e2  mov     [rax+18h], rcx
0x18000b4e6  mov     al, [r13+40h]
0x18000b4ea  mov     [rcx+0A0h], al
0x18000b4f0  mov     rcx, rsi
0x18000b4f3  mov     al, [rsp+128h+arg_0]
0x18000b4fa  mov     byte ptr [rsp+128h+var_100], al
0x18000b4fe  mov     [rsp+128h+var_108], dil
0x18000b503  call    HidpFdoUpdateOpenCounts
0x18000b508  call    cs:__imp_PsGetCurrentProcessId
0x18000b50f  nop     dword ptr [rax+rax+00h]
0x18000b514  mov     [rbx+0A0h], rax
0x18000b51b  call    cs:__imp_PsGetCurrentThreadId
0x18000b522  nop     dword ptr [rax+rax+00h]
0x18000b527  cmp     [rsp+128h+var_60], 0
0x18000b52f  mov     [rbx+0A8h], rax
0x18000b536  jnz     loc_18000C04C
0x18000b53c  test    byte ptr [rsp+128h+var_7C], 2
0x18000b544  jnz     loc_18000C09F
0x18000b54a  mov     eax, [rsp+128h+var_78]
0x18000b551  test    dil, al
0x18000b554  jz      loc_18000C0D1
0x18000b55a  test    al, 2
0x18000b55c  jz      loc_18000C10A
0x18000b562  test    eax, eax
0x18000b564  jz      loc_18000C143
0x18000b56a  call    Feature_HCTI01__private_IsEnabledDeviceUsageNoInline
0x18000b56f  xor     edx, edx
0x18000b571  test    eax, eax
0x18000b573  jz      loc_18000C175
0x18000b579  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b580  cmp     rcx, r14
0x18000b583  jnz     loc_18000B81B
0x18000b589  mov     dil, dl
0x18000b58c  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x18000b593  setnz   r8b
0x18000b597  test    dil, dil
0x18000b59a  jz      loc_18000C22B
0x18000b5a0  mov     rdx, [rbx+40h]
0x18000b5a4  mov     rax, [rsp+128h+P]
0x18000b5ac  mov     r9, [rsi+2A0h]
0x18000b5b3  mov     rcx, [rcx+18h]
0x18000b5b7  mov     eax, [rax+58h]
0x18000b5ba  mov     [rsp+128h+var_98], eax
0x18000b5c1  mov     eax, [rbx+9Ch]
0x18000b5c7  mov     [rsp+128h+var_A0], eax
0x18000b5ce  mov     eax, [rbx+98h]
0x18000b5d4  mov     [rsp+128h+var_A8], eax
0x18000b5db  mov     eax, [rbx+94h]
0x18000b5e1  mov     [rsp+128h+var_B0], eax
0x18000b5e5  mov     eax, [rsi+0F8h]
0x18000b5eb  mov     [rsp+128h+var_B8], eax
0x18000b5ef  mov     eax, [rbx+88h]
0x18000b5f5  mov     dword ptr [rsp+128h+var_C0], eax
0x18000b5f9  mov     rax, [rsp+128h+var_58]
0x18000b601  mov     [rsp+128h+var_C8], rax
0x18000b606  mov     rax, [rbx+30h]
0x18000b60a  mov     [rsp+128h+var_D0], r13
0x18000b60f  mov     [rsp+128h+var_D8], rax
0x18000b614  mov     eax, [rbx+8]
0x18000b617  mov     dword ptr [rsp+128h+var_E0], eax
0x18000b61b  mov     rax, [rdx+20h]
0x18000b61f  mov     dl, dil
0x18000b622  mov     [rsp+128h+var_E8], rax
0x18000b627  call    WPP_RECORDER_AND_TRACE_SF_qdqqqlllllL
0x18000b62c  xor     edx, edx
0x18000b62e  mov     [rsp+128h+P], rdx
0x18000b636  mov     dl, [rsp+128h+NewIrql]; NewIrql
0x18000b63d  mov     rcx, [rsp+128h+SpinLock]; SpinLock
0x18000b645  call    cs:__imp_KeReleaseSpinLock
0x18000b64c  nop     dword ptr [rax+rax+00h]
0x18000b651  mov     rdx, [rsp+128h+P]
0x18000b659  test    rdx, rdx
0x18000b65c  jnz     loc_18000C239
0x18000b662  xor     edx, edx; PriorityBoost
0x18000b664  mov     [r13+30h], r12d
0x18000b668  mov     rcx, r13; Irp
0x18000b66b  call    cs:__imp_IofCompleteRequest
0x18000b672  nop     dword ptr [rax+rax+00h]
0x18000b677  mov     eax, r12d
0x18000b67a  add     rsp, 0F0h
0x18000b681  pop     r15
0x18000b683  pop     r14
0x18000b685  pop     r13
0x18000b687  pop     r12
0x18000b689  pop     rdi
0x18000b68a  pop     rsi
0x18000b68b  pop     rbx
0x18000b68c  retn
0x18000b68e  test    r11w, r11w
0x18000b692  jnz     loc_18000B2B1
0x18000b698  mov     rcx, cs:WPP_GLOBAL_Control
0x18000b69f  cmp     rcx, r14
0x18000b6a2  jz      loc_18000BC51
0x18000b6a8  mov     eax, [rcx+2Ch]
0x18000b6ab  test    al, 8
0x18000b6ad  jz      loc_18000BC51
0x18000b6b3  cmp     byte ptr [rcx+29h], 3
0x18000b6b7  jb      loc_18000BC51
0x18000b6bd  mov     dl, dil
0x18000b6c0  xor     r10d, r10d
0x18000b6c3  jmp     loc_18000BC57
0x18000b6c8  mov     rcx, [rcx+18h]
0x18000b6cc  mov     r9d, r10d
0x18000b6cf  mov     [rsp+128h+var_A8], r11d
0x18000b6d7  mov     eax, r10d
0x18000b6da  mov     r10, [rbx+40h]
0x18000b6de  and     eax, edi
0x18000b6e0  mov     [rsp+128h+var_B0], r11d
0x18000b6e5  shr     r9d, 1
0x18000b6e8  and     r9d, edi
0x18000b6eb  mov     [rsp+128h+var_B8], r9d
0x18000b6f0  mov     r9, [rsi+2A0h]
  ... truncated ...
```
