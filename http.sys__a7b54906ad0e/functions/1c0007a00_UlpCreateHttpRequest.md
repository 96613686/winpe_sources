# UlpCreateHttpRequest

- ea: `0x1c0007a00`
- end: `0x1c0007fdc`
- name: `UlpCreateHttpRequest`
- size: `1500`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1c0006870`
- `0x1c002dc90`

## callees

- `0x1c0001118`
- `0x1c0001ae0`
- `0x1c0007a00`
- `0x1c0007fe4`
- `0x1c001556c`
- `0x1c001a4b0`
- `0x1c001a548`
- `0x1c001a568`
- `0x1c001b610`
- `0x1c001b900`
- `0x1c002caa4`
- `0x1c008f21c`
- `0x1c008f374`
- `0x1c008f3ec`
- `0x1c008f4f0`
- `0x1c008f570`
- `0x1c00903a4`
- `0x1c009677c`
- `0x1c00a9970`
- `0x1c00ad980`
- `0x1c00adc20`
- `0x1c00add20`
- `0x1c00addf0`
- `0x1c00d6070`
- `0x1c00d60c4`

## import_xrefs

- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001f28f`
- `ntoskrnl!ExpInterlockedPushEntrySList` at `0x1c001f28f`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0007aa0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001f066`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c0007aa0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x1c001f066`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f272`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f355`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f272`
- `ntoskrnl!ExQueryDepthSList` at `0x1c001f355`
- `ntoskrnl!KeBugCheckEx` at `0x1c001f3a3`
- `ntoskrnl!KeBugCheckEx` at `0x1c001f416`
- `ntoskrnl!KeBugCheckEx` at `0x1c001f3a3`
- `ntoskrnl!KeBugCheckEx` at `0x1c001f416`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0007c1c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001f026`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001f22f`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c0007c1c`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001f026`
- `ntoskrnl!KeGetCurrentNodeNumber` at `0x1c001f22f`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c001f2aa`
- `ntoskrnl!IoGetCurrentProcess` at `0x1c001f2aa`

## pseudocode

```c
__int64 __fastcall UlpCreateHttpRequest(__int64 a1, PSLIST_ENTRY *a2)
{
  __int64 v2; // r14
  PSLIST_ENTRY *v3; // r12
  unsigned int v5; // r8d
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // rax
  __int64 v9; // rdi
  PSLIST_ENTRY v10; // rbx
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 (__fastcall *v14)(__int64, __int64, __int64, __int64); // rax
  struct _SLIST_ENTRY *v15; // r15
  USHORT CurrentNodeNumber; // di
  int OpaqueId; // edi
  int v18; // r8d
  int v19; // r9d
  __int64 v20; // r13
  __int64 v21; // r12
  int v22; // edx
  char *v23; // r12
  struct _SLIST_ENTRY *Next; // r9
  __int64 v25; // rax
  __int64 v26; // rdi
  __int64 v28; // rdi
  __int64 v29; // rbx
  unsigned int v30; // r8d
  unsigned int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // rax
  ADDRESS_FAMILY v34; // cx
  UCHAR v35; // al
  struct _SLIST_ENTRY *v36; // r9
  int v37; // edx
  __int64 v38; // rax
  int v39; // ecx
  __int64 v40; // r15
  unsigned int v41; // r8d
  unsigned int v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // r14
  struct _KPROCESS *CurrentProcess; // rax
  __int64 v47; // r9
  __int64 v48; // rcx
  unsigned int v49; // r8d
  unsigned int v50; // eax
  __int64 v51; // rdx
  __int64 v52; // rax
  void (__fastcall *v53)(PSLIST_ENTRY, __int64); // rax
  bool v54; // zf
  char BugCheckParameter4; // [rsp+20h] [rbp-99h]
  int BugCheckParameter4a; // [rsp+20h] [rbp-99h]
  __int64 v57; // [rsp+28h] [rbp-91h]
  _BYTE v58[4]; // [rsp+40h] [rbp-79h] BYREF
  int v59; // [rsp+44h] [rbp-75h] BYREF
  PSLIST_ENTRY *v60; // [rsp+48h] [rbp-71h]
  __int64 v61; // [rsp+50h] [rbp-69h]
  __int128 v62; // [rsp+60h] [rbp-59h]
  __int128 v63; // [rsp+70h] [rbp-49h] BYREF
  __int128 v64; // [rsp+80h] [rbp-39h] BYREF
  _QWORD v65[3]; // [rsp+90h] [rbp-29h] BYREF
  char v66; // [rsp+A8h] [rbp-11h]
  int v67; // [rsp+A9h] [rbp-10h]
  __int16 v68; // [rsp+ADh] [rbp-Ch]
  char v69; // [rsp+AFh] [rbp-Ah]
  _QWORD v70[3]; // [rsp+B0h] [rbp-9h] BYREF
  char v71; // [rsp+C8h] [rbp+Fh]
  int v72; // [rsp+C9h] [rbp+10h]
  __int16 v73; // [rsp+CDh] [rbp+14h]
  char v74; // [rsp+CFh] [rbp+16h]

  v2 = *(_QWORD *)(a1 + 960);
  v59 = 0;
  v3 = a2;
  v60 = a2;
  v58[0] = 0;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qqq(33, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, a1, *(_QWORD *)(a1 + 24), a2);
  if ( UxCompactMode )
  {
    v29 = qword_1C0074120;
    v30 = KeGetCurrentNodeNumber() + 1;
    v31 = *(_DWORD *)v29 - 1;
    if ( v30 < *(_DWORD *)v29 )
      v31 = v30;
    v32 = v31;
    v33 = *(_QWORD *)(v29 + 32);
    v9 = *(_QWORD *)(v33 + 8 * v32);
    if ( !*(_BYTE *)(v9 + 112) )
      PplpLazyInitializeLookasideList(v29, *(_QWORD *)(v33 + 8 * v32));
    ++*(_DWORD *)(v9 + 20);
    v10 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v9);
    if ( v10 )
      goto LABEL_10;
  }
  else
  {
    v5 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
    v6 = *(_DWORD *)qword_1C0074120 - 1;
    if ( v5 < *(_DWORD *)qword_1C0074120 )
      v6 = v5;
    v7 = v6;
    v8 = *(_QWORD *)(qword_1C0074120 + 32);
    v9 = *(_QWORD *)(v8 + 8 * v7);
    if ( !*(_BYTE *)(v9 + 112) )
      PplpLazyInitializeLookasideList(qword_1C0074120, *(_QWORD *)(v8 + 8 * v7));
    ++*(_DWORD *)(v9 + 20);
    v10 = ExpInterlockedPopEntrySList((PSLIST_HEADER)v9);
    if ( v10 )
      goto LABEL_10;
  }
  v11 = *(unsigned int *)(v9 + 40);
  v12 = *(unsigned int *)(v9 + 44);
  v13 = *(unsigned int *)(v9 + 36);
  v14 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64))(v9 + 48);
  ++*(_DWORD *)(v9 + 24);
  v10 = (PSLIST_ENTRY)v14(v13, v12, v11, v9);
LABEL_10:
  if ( !v10 )
  {
    OpaqueId = -1073741670;
    goto LABEL_51;
  }
  LODWORD(v10[1].Next) = 1380478037;
  *((_BYTE *)&v10[5].Next + 8) = 0;
  LODWORD(v10[3].Next) = 1;
  v15 = v10 + 4;
  v10[32].Next = (PSLIST_ENTRY)((char *)v10 + 504);
  *((_QWORD *)&v10[31].Next + 1) = (char *)v10 + 504;
  v10[77].Next = 0;
  v10[31].Next = (PSLIST_ENTRY)((char *)v10 + 488);
  *((_QWORD *)&v10[30].Next + 1) = (char *)v10 + 488;
  v10[78].Next = 0;
  v10[79].Next = 0;
  LODWORD(v10[30].Next) = 1;
  HIDWORD(v10[30].Next) = 1;
  v10[4].Next = 0;
  *((_QWORD *)&v10[3].Next + 1) = 0;
  *((_WORD *)&v10[122].Next + 6) = 0;
  *(struct _SLIST_ENTRY *)((char *)&v10[4] + 8) = 0;
  LODWORD(v10[99].Next) = 1;
  *((_QWORD *)&v10[99].Next + 1) = v10 + 100;
  *((_DWORD *)&v10[101].Next + 3) = g_UlInternalRequestSize;
  LOBYTE(v10[33].Next) = 41;
  *((_DWORD *)&v10[100].Next + 2) = 0;
  v10[101].Next = 0;
  *((_DWORD *)&v10[101].Next + 2) = 0;
  UlInitializeConfigGroupInfo(&v10[80]);
  memset(&v10[102], 0, 0x750u);
  v10[174].Next = 0;
  *((_QWORD *)&v10[153].Next + 1) = v10 + 153;
  v10[153].Next = v10 + 153;
  *((_QWORD *)&v10[173].Next + 1) = v10 + 173;
  v10[173].Next = v10 + 173;
  *((_QWORD *)&v10[32].Next + 1) = v10 + 219;
  *((_QWORD *)&v10[157].Next + 1) = 0;
  LODWORD(v10[122].Next) = 0;
  *((_DWORD *)&v10[170].Next + 2) = 3;
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_(16, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  if ( (unsigned __int16)UlNumberOfLanes <= 1u )
    CurrentNodeNumber = 0;
  else
    CurrentNodeNumber = KeGetCurrentNodeNumber();
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(17, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids);
  *((_WORD *)&v10[114].Next + 4) = CurrentNodeNumber;
  *((_QWORD *)&v10[105].Next + 1) = 0;
  v10[214] = 0;
  v10[215] = 0;
  HIDWORD(v10[215].Next) = 1;
  *((_DWORD *)&v10[214].Next + 3) = 19;
  *((_DWORD *)&v10[215].Next + 2) = 1448704085;
  v10[216].Next = 0;
  *((_QWORD *)&v10[216].Next + 1) = 0;
  v10[217].Next = 0;
  *((_QWORD *)&v10[217].Next + 1) = 0;
  *((_WORD *)&v10[218].Next + 6) = 0;
  *((_BYTE *)&v10[218].Next + 14) = 0;
  *((_DWORD *)&v10[218].Next + 2) = 0;
  v10[218].Next = 0;
  UxDuoInitializeCollection(&v10[193]);
  _InterlockedIncrement((volatile signed __int32 *)(a1 + 20));
  *((_QWORD *)&v10[1].Next + 1) = a1;
  v10[2].Next = *(struct _SLIST_ENTRY **)(a1 + 24);
  *((_DWORD *)&v10[136].Next + 2) ^= (*((_DWORD *)&v10[136].Next + 2) ^ *(unsigned __int8 *)(a1 + 369)) & 1;
  OpaqueId = UlpInitializeRequestSizingInfo(v10);
  if ( OpaqueId < 0 )
    goto LABEL_75;
  OpaqueId = UlpInitializeRequestTimings(v10);
  if ( OpaqueId < 0 )
    goto LABEL_75;
  if ( (!*(_BYTE *)(v2 + 79) || !Microsoft_Windows_Networking_CorrelationEnabled) && !*(_BYTE *)(v2 + 1568) )
    goto LABEL_42;
  v20 = *((_QWORD *)&v10[1].Next + 1);
  v61 = *(_QWORD *)(a1 + 24);
  v21 = *(_QWORD *)(v20 + 24);
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qq(94, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, v10, v10[4].Next);
  OpaqueId = UxAllocateOpaqueIdEx((int)v20 + 24, (int)v10 + 64, v18, v19, v20, (__int64)v10);
  if ( OpaqueId < 0 )
  {
    v15 = v10 + 4;
    v23 = (char *)(&v10[4].Next + 1);
  }
  else
  {
    if ( !v21 )
      _InterlockedIncrement((volatile signed __int32 *)(v20 + 20));
    _InterlockedIncrement((volatile signed __int32 *)&v10[3]);
    v15 = v10 + 4;
    v10[2].Next = *(struct _SLIST_ENTRY **)(v20 + 24);
    v23 = (char *)(&v10[4].Next + 1);
    *((_QWORD *)&v10[3].Next + 1) = v10[4].Next;
    *(struct _SLIST_ENTRY *)((char *)&v10[4] + 8) = (struct _SLIST_ENTRY)UlEtwBaseOpaqueIdActivityGuid;
    *((_QWORD *)&v10[4].Next + 1) = v10[4].Next;
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_D(95, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids);
  if ( OpaqueId < 0 )
  {
LABEL_75:
    _InterlockedDecrement((volatile signed __int32 *)&v10[3]);
    LODWORD(v10[1].Next) = 1380469877;
    if ( UxCompactMode )
    {
      v40 = qword_1C0074120;
      v41 = KeGetCurrentNodeNumber() + 1;
      v42 = *(_DWORD *)v40 - 1;
      if ( v41 < *(_DWORD *)v40 )
        v42 = v41;
      v43 = v42;
      v44 = *(_QWORD *)(v40 + 32);
      v45 = *(_QWORD *)(v44 + 8 * v43);
      if ( !*(_BYTE *)(v45 + 112) )
        PplpLazyInitializeLookasideList(v40, *(_QWORD *)(v44 + 8 * v43));
      ++*(_DWORD *)(v45 + 28);
      if ( ExQueryDepthSList((PSLIST_HEADER)v45) < *(_WORD *)(v45 + 16) )
      {
LABEL_81:
        ExpInterlockedPushEntrySList((PSLIST_HEADER)v45, v10);
        goto LABEL_82;
      }
    }
    else
    {
      v49 = HIDWORD(KeGetPcr()[1].LockArray) + 1;
      v50 = *(_DWORD *)qword_1C0074120 - 1;
      if ( v49 < *(_DWORD *)qword_1C0074120 )
        v50 = v49;
      v51 = v50;
      v52 = *(_QWORD *)(qword_1C0074120 + 32);
      v45 = *(_QWORD *)(v52 + 8 * v51);
      if ( !*(_BYTE *)(v45 + 112) )
        PplpLazyInitializeLookasideList(qword_1C0074120, *(_QWORD *)(v52 + 8 * v51));
      ++*(_DWORD *)(v45 + 28);
      if ( ExQueryDepthSList((PSLIST_HEADER)v45) < *(_WORD *)(v45 + 16) )
        goto LABEL_81;
    }
    v53 = *(void (__fastcall **)(PSLIST_ENTRY, __int64))(v45 + 56);
    ++*(_DWORD *)(v45 + 32);
    v53(v10, v45);
LABEL_82:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(a1 + 20), 0xFFFFFFFF) == 1 )
    {
      CurrentProcess = IoGetCurrentProcess();
      v48 = *(_QWORD *)(a1 + 952);
      if ( UxSystemProcess == CurrentProcess )
      {
        v54 = *(_QWORD *)(a1 + 32) == 0;
        v63 = 0;
        if ( !v54 || *(_QWORD *)(a1 + 48) || *(_QWORD *)(a1 + 64) )
          KeBugCheckEx(0xFAu, 1u, a1 + 32, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xE1u);
        if ( !KeGetCurrentIrql() )
        {
          UxPodAttachThread(v48, &v63);
          UlFreeHttpConnection(a1 + 32);
          UxPodDetachThread(&v63);
          goto LABEL_88;
        }
      }
      else if ( *(_QWORD *)(a1 + 32) || *(_QWORD *)(a1 + 48) || *(_QWORD *)(a1 + 64) )
      {
        KeBugCheckEx(0xFAu, 1u, a1 + 32, (ULONG_PTR)"minio\\http\\sys\\httpconn.h", 0xDBu);
      }
      LODWORD(v57) = -1;
      LOBYTE(v47) = 1;
      UlThreadPoolEnqueueWorkItem(0, a1 + 32, UlFreeHttpConnection, v47, v48, v57);
    }
LABEL_88:
    v3 = v60;
    goto LABEL_51;
  }
  if ( v61 )
    goto LABEL_34;
  if ( *(_BYTE *)(v2 + 1568) )
  {
    Next = v15->Next;
    v65[0] = a1 + 344;
    BugCheckParameter4 = *(_QWORD *)(a1 + 24);
    v67 = 0;
    v68 = 0;
    v69 = 0;
    v65[2] = v2;
    v65[1] = 0;
    v66 = 0;
    McTemplateK0xxp_UlEtwWriteEventWrapper(0, v22, (unsigned int)v65, (_DWORD)Next, BugCheckParameter4, a1);
LABEL_34:
    if ( *(_BYTE *)(v2 + 1568) )
    {
      v70[2] = v2;
      v72 = 0;
      v70[0] = a1 + 344;
      v25 = *(unsigned __int16 *)(a1 + 316);
      v73 = 0;
      v74 = 0;
      v70[1] = v23;
      v71 = 0;
      if ( (unsigned int)v25 >= 0x23 )
        LOBYTE(v22) = 0;
      else
        v22 = sockaddr_size[v25];
      McTemplateK0xxqbr2_UlEtwWriteEventWrapper(
        a1 + 316,
        v22,
        (unsigned int)v70,
        v15->Next,
        *(_QWORD *)(a1 + 24),
        (unsigned __int8)v22,
        a1 + 316);
    }
  }
  if ( *(_BYTE *)(v2 + 79) && Microsoft_Windows_Networking_CorrelationEnabled )
    UlEtwStartActivity(v23, 5);
  v3 = v60;
LABEL_42:
  v26 = *((_QWORD *)&v10[1].Next + 1);
  *((_QWORD *)&v10[2].Next + 1) = v10[2].Next;
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, v26 + 384, 13, v58, &v59, 0, 0);
  OpaqueId = (*(__int64 (__fastcall **)(_QWORD, __int64, _BYTE *, int *, _QWORD, _QWORD))(*(_QWORD *)(v26 + 392) + 120LL))(
               *(_QWORD *)(v26 + 384),
               13,
               v58,
               &v59,
               0,
               0);
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
    WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
  if ( OpaqueId < 0 )
    goto LABEL_75;
  if ( v58[0] )
  {
    if ( v59 == 2 )
    {
      BYTE4(v10[131].Next) = 1;
    }
    else if ( v59 == 3 )
    {
      BYTE5(v10[131].Next) = 1;
      *((_BYTE *)&v10[218].Next + 14) = 1;
    }
    v28 = *((_QWORD *)&v10[1].Next + 1);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
      WPP_SF_qLqqqq(10, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids, v28 + 384, 48, &v10[2].Next + 1, 0, 0, 0);
    HIDWORD(v57) = 0;
    OpaqueId = (*(__int64 (__fastcall **)(_QWORD, __int64, struct _SLIST_ENTRY **))(*(_QWORD *)(v28 + 392) + 120LL))(
                 *(_QWORD *)(v28 + 384),
                 48,
                 &v10[2].Next + 1);
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 0x1000000) != 0 )
      WPP_SF_D(11, WPP_65b7d4bd579d3dd3f0a1109448b1ff1a_Traceguids);
    if ( OpaqueId < 0 )
      goto LABEL_75;
  }
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
  {
    v34 = *(_WORD *)(a1 + 316);
    v62 = (unsigned __int64)(a1 + 316);
    v35 = SOCKADDR_SIZE(v34);
    v36 = v15->Next;
    v37 = v35;
    v38 = *(_QWORD *)(a1 + 24);
    WORD4(v62) = v37;
    BugCheckParameter4a = (int)v10[3].Next;
    v64 = v62;
    WPP_SF_qidiq_SOCKADDR_(v39, v37, (_DWORD)v10, (_DWORD)v36, BugCheckParameter4a, v38, a1, (__int64)&v64);
  }
  *v3 = v10;
  OpaqueId = 0;
LABEL_51:
  if ( SLOBYTE(WPP_MAIN_CB.Queue.ListEntry.Flink) < 0 )
    WPP_SF_qD(35, WPP_6cebc73ec5833d6d901146f2aa6dea31_Traceguids, *v3, (unsigned int)OpaqueId);
  return (unsigned int)OpaqueId;
}

```

## disassembly

```asm
0x1c0007a00  push    rbp
0x1c0007a02  push    rbx
0x1c0007a03  push    rsi
0x1c0007a04  push    r12
0x1c0007a06  push    r13
0x1c0007a08  push    r14
0x1c0007a0a  lea     rbp, [rsp-2Fh]
0x1c0007a0f  sub     rsp, 0E8h
0x1c0007a16  mov     rax, cs:__security_cookie
0x1c0007a1d  xor     rax, rsp
0x1c0007a20  mov     [rbp+57h+var_40], rax
0x1c0007a24  mov     r14, [rcx+3C0h]
0x1c0007a2b  xor     r13d, r13d
0x1c0007a2e  mov     [rbp+57h+var_CC], r13d
0x1c0007a32  mov     r12, rdx
0x1c0007a35  mov     [rbp+57h+var_C8], rdx
0x1c0007a39  mov     rsi, rcx
0x1c0007a3c  mov     [rbp+57h+var_D0], 0
0x1c0007a40  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0007a46  test    al, al
0x1c0007a48  js      loc_1C001EFFC
0x1c0007a4e  cmp     cs:UxCompactMode, r13b
0x1c0007a55  mov     [rsp+110h+arg_10], rdi
0x1c0007a5d  jnz     loc_1C001F01F
0x1c0007a63  mov     eax, gs:1A4h
0x1c0007a6b  mov     rcx, cs:qword_1C0074120
0x1c0007a72  lea     r8d, [rax+1]
0x1c0007a76  mov     edx, [rcx]
0x1c0007a78  cmp     r8d, edx
0x1c0007a7b  lea     eax, [rdx-1]
0x1c0007a7e  cmovb   eax, r8d
0x1c0007a82  mov     edx, eax
0x1c0007a84  mov     rax, [rcx+20h]
0x1c0007a88  mov     rdi, [rax+rdx*8]
0x1c0007a8c  cmp     [rdi+70h], r13b
0x1c0007a90  jnz     short loc_1C0007A9A
0x1c0007a92  mov     rdx, rdi
0x1c0007a95  call    PplpLazyInitializeLookasideList
0x1c0007a9a  inc     dword ptr [rdi+14h]
0x1c0007a9d  mov     rcx, rdi; ListHead
0x1c0007aa0  call    cs:__imp_ExpInterlockedPopEntrySList
0x1c0007aa7  nop     dword ptr [rax+rax+00h]
0x1c0007aac  mov     rbx, rax
0x1c0007aaf  test    rax, rax
0x1c0007ab2  jnz     short loc_1C0007AD1
0x1c0007ab4  mov     r8d, [rdi+28h]
0x1c0007ab8  mov     r9, rdi
0x1c0007abb  mov     edx, [rdi+2Ch]
0x1c0007abe  mov     ecx, [rdi+24h]
0x1c0007ac1  mov     rax, [rdi+30h]
0x1c0007ac5  inc     dword ptr [rdi+18h]
0x1c0007ac8  call    cs:__guard_dispatch_icall_fptr
0x1c0007ace  mov     rbx, rax
0x1c0007ad1  mov     [rsp+110h+var_30], r15
0x1c0007ad9  test    rbx, rbx
0x1c0007adc  jz      loc_1C001F083
0x1c0007ae2  mov     dword ptr [rbx+10h], 52486C55h
0x1c0007ae9  lea     rax, [rbx+1F8h]
0x1c0007af0  mov     ecx, 1
0x1c0007af5  mov     [rbx+58h], r13b
0x1c0007af9  mov     [rbx+30h], ecx
0x1c0007afc  lea     r15, [rbx+40h]
0x1c0007b00  mov     [rax+8], rax
0x1c0007b04  xorps   xmm0, xmm0
0x1c0007b07  mov     [rax], rax
0x1c0007b0a  mov     dl, 1
0x1c0007b0c  mov     [rbx+4D0h], r13
0x1c0007b13  lea     rax, [rbx+1E8h]
0x1c0007b1a  mov     [rax+8], rax
0x1c0007b1e  mov     [rax], rax
0x1c0007b21  lea     rax, [rbx+640h]
0x1c0007b28  mov     [rbx+4E0h], r13
0x1c0007b2f  mov     [rbx+4F0h], r13
0x1c0007b36  mov     [rbx+1E0h], ecx
0x1c0007b3c  mov     [rbx+1E4h], ecx
0x1c0007b42  mov     [r15], r13
0x1c0007b45  mov     [rbx+38h], r13
0x1c0007b49  mov     [rbx+7ACh], r13w
0x1c0007b51  movups  xmmword ptr [rbx+48h], xmm0
0x1c0007b55  mov     [rbx+630h], ecx
0x1c0007b5b  lea     rcx, [rbx+500h]; void *
0x1c0007b62  mov     [rbx+638h], rax
0x1c0007b69  mov     eax, cs:g_UlInternalRequestSize
0x1c0007b6f  mov     [rbx+65Ch], eax
0x1c0007b75  mov     byte ptr [rbx+210h], 29h ; ')'
0x1c0007b7c  mov     [rbx+648h], r13d
0x1c0007b83  mov     [rbx+650h], r13
0x1c0007b8a  mov     [rbx+658h], r13d
0x1c0007b91  call    UlInitializeConfigGroupInfo
0x1c0007b96  lea     rcx, [rbx+660h]; void *
0x1c0007b9d  xor     edx, edx; Val
0x1c0007b9f  mov     r8d, 750h; Size
0x1c0007ba5  call    memset
0x1c0007baa  lea     rax, [rbx+990h]
0x1c0007bb1  mov     [rbx+0AE0h], r13
0x1c0007bb8  mov     [rax+8], rax
0x1c0007bbc  mov     [rax], rax
0x1c0007bbf  lea     rax, [rbx+0AD0h]
0x1c0007bc6  mov     [rax+8], rax
0x1c0007bca  mov     [rax], rax
0x1c0007bcd  lea     rax, [rbx+0DB0h]
0x1c0007bd4  mov     [rbx+208h], rax
0x1c0007bdb  mov     [rbx+9D8h], r13
0x1c0007be2  mov     [rbx+7A0h], r13d
0x1c0007be9  mov     dword ptr [rbx+0AA8h], 3
0x1c0007bf3  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0007bf9  test    al, al
0x1c0007bfb  jns     short loc_1C0007C0E
0x1c0007bfd  mov     ecx, 10h
0x1c0007c02  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0007c09  call    WPP_SF_
0x1c0007c0e  cmp     cs:UlNumberOfLanes, 1
0x1c0007c16  jbe     loc_1C0007F62
0x1c0007c1c  call    cs:__imp_KeGetCurrentNodeNumber
0x1c0007c23  nop     dword ptr [rax+rax+00h]
0x1c0007c28  movzx   edi, ax
0x1c0007c2b  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0007c31  test    al, al
0x1c0007c33  jns     short loc_1C0007C4A
0x1c0007c35  movzx   r8d, di
0x1c0007c39  lea     rdx, WPP_80d4b18777633ecb8759c7c8a3c5c10e_Traceguids
0x1c0007c40  mov     ecx, 11h
0x1c0007c45  call    WPP_SF_D
0x1c0007c4a  mov     [rbx+728h], di
0x1c0007c51  lea     rcx, [rbx+0C10h]
0x1c0007c58  mov     [rbx+698h], r13
0x1c0007c5f  xorps   xmm0, xmm0
0x1c0007c62  movups  xmmword ptr [rbx+0D60h], xmm0
0x1c0007c69  movups  xmmword ptr [rbx+0D70h], xmm0
0x1c0007c70  mov     dword ptr [rbx+0D74h], 1
0x1c0007c7a  mov     dword ptr [rbx+0D6Ch], 13h
0x1c0007c84  mov     dword ptr [rbx+0D78h], 56597855h
0x1c0007c8e  mov     [rbx+0D80h], r13
0x1c0007c95  mov     [rbx+0D88h], r13
0x1c0007c9c  mov     [rbx+0D90h], r13
0x1c0007ca3  mov     [rbx+0D98h], r13
0x1c0007caa  mov     [rbx+0DACh], r13w
0x1c0007cb2  mov     [rbx+0DAEh], r13b
0x1c0007cb9  mov     [rbx+0DA8h], r13d
0x1c0007cc0  mov     [rbx+0DA0h], r13
0x1c0007cc7  call    UxDuoInitializeCollection
0x1c0007ccc  lock inc dword ptr [rsi+14h]
0x1c0007cd0  mov     [rbx+18h], rsi
0x1c0007cd4  mov     rcx, rbx
0x1c0007cd7  mov     rax, [rsi+18h]
0x1c0007cdb  mov     [rbx+20h], rax
0x1c0007cdf  movzx   eax, byte ptr [rsi+171h]
0x1c0007ce6  xor     eax, [rbx+888h]
0x1c0007cec  and     eax, 1
0x1c0007cef  xor     [rbx+888h], eax
0x1c0007cf5  call    UlpInitializeRequestSizingInfo
0x1c0007cfa  mov     edi, eax
0x1c0007cfc  test    eax, eax
0x1c0007cfe  js      loc_1C001F210
0x1c0007d04  mov     rcx, rbx
0x1c0007d07  call    UlpInitializeRequestTimings
0x1c0007d0c  mov     edi, eax
0x1c0007d0e  test    eax, eax
0x1c0007d10  js      loc_1C001F210
0x1c0007d16  cmp     [r14+4Fh], r13b
0x1c0007d1a  jz      short loc_1C0007D26
0x1c0007d1c  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1c0007d22  test    eax, eax
0x1c0007d24  jnz     short loc_1C0007D33
0x1c0007d26  cmp     [r14+620h], r13b
0x1c0007d2d  jz      loc_1C0007EA1
0x1c0007d33  mov     r13, [rbx+18h]
0x1c0007d37  mov     rax, [rsi+18h]
0x1c0007d3b  mov     [rbp+57h+var_C0], rax
0x1c0007d3f  mov     r12, [r13+18h]
0x1c0007d43  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0007d49  lea     rdi, [rbx+40h]
0x1c0007d4d  test    al, al
0x1c0007d4f  js      loc_1C001F08D
0x1c0007d55  mov     [rsp+110h+var_E8], rbx
0x1c0007d5a  lea     rcx, [r13+18h]
0x1c0007d5e  mov     rdx, rdi
0x1c0007d61  mov     [rsp+110h+BugCheckParameter4], r13
0x1c0007d66  call    UxAllocateOpaqueIdEx
0x1c0007d6b  mov     edi, eax
0x1c0007d6d  test    eax, eax
0x1c0007d6f  js      loc_1C001F0AA
0x1c0007d75  test    r12, r12
0x1c0007d78  jnz     short loc_1C0007D7F
0x1c0007d7a  lock inc dword ptr [r13+14h]
0x1c0007d7f  lock inc dword ptr [rbx+30h]
0x1c0007d83  mov     rax, [r13+18h]
0x1c0007d87  lea     r15, [rbx+40h]
0x1c0007d8b  mov     [rbx+20h], rax
0x1c0007d8f  lea     r12, [rbx+48h]
0x1c0007d93  mov     rax, [r15]
0x1c0007d96  mov     [rbx+38h], rax
0x1c0007d9a  movups  xmm0, cs:UlEtwBaseOpaqueIdActivityGuid
0x1c0007da1  movups  xmmword ptr [r12], xmm0
0x1c0007da6  mov     rax, [r15]
0x1c0007da9  mov     [r12], rax
0x1c0007dad  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0007db3  test    al, al
0x1c0007db5  js      loc_1C001F0B7
0x1c0007dbb  test    edi, edi
0x1c0007dbd  js      loc_1C001F210
0x1c0007dc3  cmp     [rbp+57h+var_C0], 0
0x1c0007dc8  jnz     short loc_1C0007E14
0x1c0007dca  cmp     byte ptr [r14+620h], 0
0x1c0007dd2  jz      loc_1C001F0D8
0x1c0007dd8  mov     r9, [r15]
0x1c0007ddb  lea     rax, [rsi+158h]
0x1c0007de2  xor     ecx, ecx
0x1c0007de4  mov     [rbp+57h+var_80], rax
0x1c0007de8  mov     rax, [rsi+18h]
0x1c0007dec  lea     r8, [rbp+57h+var_80]
0x1c0007df0  mov     [rsp+110h+var_E8], rsi
0x1c0007df5  mov     [rsp+110h+BugCheckParameter4], rax
0x1c0007dfa  mov     [rbp+57h+var_67], ecx
0x1c0007dfd  mov     [rbp+57h+var_63], cx
0x1c0007e01  mov     [rbp+57h+var_61], cl
0x1c0007e04  mov     [rbp+57h+var_70], r14
0x1c0007e08  mov     [rbp+57h+var_78], rcx
0x1c0007e0c  mov     [rbp+57h+var_68], cl
0x1c0007e0f  call    McTemplateK0xxp_UlEtwWriteEventWrapper
0x1c0007e14  cmp     byte ptr [r14+620h], 0
0x1c0007e1c  jz      loc_1C001F0D8
0x1c0007e22  xor     r13d, r13d
0x1c0007e25  mov     [rbp+57h+var_50], r14
0x1c0007e29  lea     rax, [rsi+158h]
0x1c0007e30  mov     [rbp+57h+var_47], r13d
0x1c0007e34  lea     rcx, [rsi+13Ch]
0x1c0007e3b  mov     [rbp+57h+var_60], rax
0x1c0007e3f  movzx   eax, word ptr [rcx]
0x1c0007e42  mov     [rbp+57h+var_43], r13w
0x1c0007e47  mov     [rbp+57h+var_41], r13b
0x1c0007e4b  mov     [rbp+57h+var_58], r12
0x1c0007e4f  mov     [rbp+57h+var_48], r13b
0x1c0007e53  cmp     eax, 23h ; '#'
0x1c0007e56  jnb     loc_1C001F0D1
0x1c0007e5c  lea     rdx, sockaddr_size
0x1c0007e63  movzx   edx, byte ptr [rax+rdx]
0x1c0007e67  mov     r9, [r15]
0x1c0007e6a  lea     r8, [rbp+57h+var_60]
0x1c0007e6e  movzx   eax, dl
0x1c0007e71  mov     [rsp+110h+var_E0], rcx
0x1c0007e76  mov     dword ptr [rsp+110h+var_E8], eax
0x1c0007e7a  mov     rax, [rsi+18h]
0x1c0007e7e  mov     [rsp+110h+BugCheckParameter4], rax
0x1c0007e83  call    McTemplateK0xxqbr2_UlEtwWriteEventWrapper
0x1c0007e88  cmp     byte ptr [r14+4Fh], 0
0x1c0007e8d  jz      short loc_1C0007E9D
0x1c0007e8f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1c0007e95  test    eax, eax
0x1c0007e97  jnz     loc_1C001F0E0
0x1c0007e9d  mov     r12, [rbp+57h+var_C8]
0x1c0007ea1  mov     rax, [rbx+20h]
0x1c0007ea5  lea     r14, [rbx+28h]
0x1c0007ea9  mov     rdi, [rbx+18h]
0x1c0007ead  mov     [r14], rax
0x1c0007eb0  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0007eba  jnz     loc_1C001F0F3
0x1c0007ec0  mov     rax, [rdi+188h]
0x1c0007ec7  lea     r9, [rbp+57h+var_CC]
0x1c0007ecb  mov     rcx, [rdi+180h]
0x1c0007ed2  lea     r8, [rbp+57h+var_D0]
0x1c0007ed6  mov     [rsp+110h+var_E8], r13
0x1c0007edb  mov     edx, 0Dh
0x1c0007ee0  mov     [rsp+110h+BugCheckParameter4], r13
0x1c0007ee5  mov     rax, [rax+78h]
0x1c0007ee9  call    cs:__guard_dispatch_icall_fptr
0x1c0007eef  mov     edi, eax
0x1c0007ef1  test    dword ptr cs:WPP_MAIN_CB.Queue, 1000000h
0x1c0007efb  jnz     loc_1C001F131
0x1c0007f01  test    edi, edi
0x1c0007f03  js      loc_1C001F210
0x1c0007f09  cmp     [rbp+57h+var_D0], 0
0x1c0007f0d  jnz     short loc_1C0007F6A
0x1c0007f0f  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0007f15  test    al, al
0x1c0007f17  js      loc_1C001F1B7
0x1c0007f1d  mov     [r12], rbx
0x1c0007f21  mov     edi, r13d
0x1c0007f24  mov     eax, dword ptr cs:WPP_MAIN_CB.Queue
0x1c0007f2a  test    al, al
0x1c0007f2c  js      loc_1C001F423
0x1c0007f32  mov     r15, [rsp+110h+var_30]
0x1c0007f3a  mov     eax, edi
0x1c0007f3c  mov     rdi, [rsp+110h+arg_10]
0x1c0007f44  mov     rcx, [rbp+57h+var_40]
0x1c0007f48  xor     rcx, rsp; StackCookie
0x1c0007f4b  call    __security_check_cookie
0x1c0007f50  add     rsp, 0E8h
0x1c0007f57  pop     r14
0x1c0007f59  pop     r13
0x1c0007f5b  pop     r12
0x1c0007f5d  pop     rsi
0x1c0007f5e  pop     rbx
0x1c0007f5f  pop     rbp
0x1c0007f60  retn
0x1c0007f62  mov     edi, r13d
0x1c0007f65  jmp     loc_1C0007C2B
0x1c0007f6a  mov     eax, [rbp+57h+var_CC]
0x1c0007f6d  cmp     eax, 2
0x1c0007f70  jnz     loc_1C001F14B
  ... truncated ...
```
