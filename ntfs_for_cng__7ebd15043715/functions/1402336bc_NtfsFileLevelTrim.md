# NtfsFileLevelTrim

- ea: `0x1402336bc`
- end: `0x140234f9e`
- name: `NtfsFileLevelTrim`
- size: `6370`
- prototype: `__int64 __fastcall(__int64 Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000e220`
- `0x14000e670`
- `0x1400100b0`
- `0x140012e70`
- `0x140021590`
- `0x1400410a8`
- `0x1400596c0`
- `0x14012c1ec`
- `0x14012d150`
- `0x140140380`
- `0x140160be0`
- `0x140160e90`
- `0x1401620c0`
- `0x140162370`
- `0x140181b60`
- `0x1401be398`
- `0x1401c00e0`
- `0x1402336bc`
- `0x140234fa4`
- `0x140234fd0`

## import_xrefs

- `ntoskrnl!IoGetRequestorProcess` at `0x1402343c0`
- `ntoskrnl!IoGetRequestorProcess` at `0x1402343c0`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x140234e8e`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x1402b6f07`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x140234e8e`
- `ntoskrnl!ExSetResourceOwnerPointerEx` at `0x1402b6f07`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x1402343ee`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x1402343ee`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140234e07`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140234ec4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b6e4b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b6f3e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140234e07`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140234ec4`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b6e4b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b6f3e`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140233c08`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402340f8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140234991`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140233c08`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1402340f8`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140234991`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140234030`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140234030`
- `HAL!KeQueryPerformanceCounter` at `0x1402337b6`
- `HAL!KeQueryPerformanceCounter` at `0x140234cdc`
- `HAL!KeQueryPerformanceCounter` at `0x1402b6d22`
- `HAL!KeQueryPerformanceCounter` at `0x1402337b6`
- `HAL!KeQueryPerformanceCounter` at `0x140234cdc`
- `HAL!KeQueryPerformanceCounter` at `0x1402b6d22`

## pseudocode

```c
__int64 __fastcall NtfsFileLevelTrim(__int64 Context, PIRP Irp)
{
  PIRP v2; // rsi
  _BYTE *v3; // r13
  _QWORD *p_Type; // rax
  __int64 v5; // r14
  __int64 v6; // rbx
  __int64 v7; // r15
  int v8; // eax
  unsigned int v9; // r14d
  unsigned int v10; // r8d
  LARGE_INTEGER PerformanceCounter; // rdi
  int v12; // ecx
  unsigned int v13; // ebx
  unsigned int v14; // r8d
  unsigned int Options; // r8d
  ULONG v17; // eax
  char v18; // bl
  unsigned __int64 v19; // rcx
  _QWORD *v20; // rax
  _QWORD *v21; // r14
  struct _IRP *v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rax
  __int64 v25; // rcx
  int v26; // edx
  __int64 v27; // rax
  __int16 v28; // r8
  char v29; // bl
  __int16 v30; // ax
  int v31; // eax
  signed int v32; // r14d
  unsigned int v33; // r8d
  __int64 v34; // rbx
  NTSTATUS v35; // eax
  _WORD *v36; // rax
  __int64 v37; // rsi
  __int16 v38; // ax
  ULONG v39; // eax
  ULONG *v40; // rcx
  __int64 v41; // r11
  union _LARGE_INTEGER v42; // rax
  union _LARGE_INTEGER v43; // r8
  __int64 v44; // r9
  __int64 v45; // rdx
  unsigned __int64 QuadPart; // rcx
  unsigned int v47; // r8d
  unsigned __int64 v48; // rdx
  unsigned __int64 v49; // r10
  union _LARGE_INTEGER v50; // rdx
  ULONG v51; // ebx
  FILE_LOCK *v52; // rsi
  PEPROCESS RequestorProcess; // rax
  union _LARGE_INTEGER v54; // rax
  union _LARGE_INTEGER v55; // rcx
  __int16 v56; // cx
  unsigned int v57; // r8d
  union _LARGE_INTEGER v58; // r8
  union _LARGE_INTEGER v59; // rdx
  __int64 v60; // rbx
  __int16 v61; // ax
  char v62; // al
  __int64 v63; // r9
  char v64; // cl
  __int64 v65; // r8
  PVOID v66; // rax
  _DWORD *v67; // rax
  unsigned __int64 v68; // rcx
  __int64 v69; // r11
  union _LARGE_INTEGER v70; // r9
  unsigned __int64 v71; // rdx
  unsigned __int64 v72; // rcx
  __int64 v73; // rax
  _DWORD *v74; // rdx
  int v75; // edi
  int v76; // ebx
  __int64 v77; // rax
  int *v78; // rdx
  unsigned __int64 v79; // r11
  unsigned __int64 v80; // rdi
  unsigned __int64 v81; // rdx
  unsigned __int64 v82; // r11
  unsigned __int64 v83; // rdx
  __int64 v84; // rax
  unsigned __int64 v85; // r11
  unsigned __int64 v86; // rdx
  __int64 v87; // rcx
  __int64 v88; // rcx
  __int64 v89; // r11
  unsigned __int64 v90; // rax
  __int64 v91; // rdx
  unsigned int i; // ecx
  int v93; // edx
  PVOID v94; // rdi
  char v95; // [rsp+58h] [rbp-120h]
  union _LARGE_INTEGER StartingByte; // [rsp+60h] [rbp-118h] BYREF
  union _LARGE_INTEGER Length; // [rsp+68h] [rbp-110h] BYREF
  __int64 v98; // [rsp+70h] [rbp-108h] BYREF
  __int64 v99; // [rsp+78h] [rbp-100h]
  PVOID Entry; // [rsp+80h] [rbp-F8h] BYREF
  int v101[2]; // [rsp+88h] [rbp-F0h]
  PVOID Src; // [rsp+90h] [rbp-E8h]
  __int64 v103; // [rsp+98h] [rbp-E0h]
  int v104; // [rsp+A0h] [rbp-D8h]
  ULONG v105; // [rsp+A4h] [rbp-D4h]
  PVOID FileObject; // [rsp+A8h] [rbp-D0h]
  ULONG *MasterIrp; // [rsp+B0h] [rbp-C8h]
  __int64 v108; // [rsp+B8h] [rbp-C0h] BYREF
  unsigned __int64 v109; // [rsp+C0h] [rbp-B8h]
  __int64 v110; // [rsp+C8h] [rbp-B0h]
  unsigned __int64 v111; // [rsp+D0h] [rbp-A8h]
  __int64 v112; // [rsp+D8h] [rbp-A0h]
  unsigned __int64 v113; // [rsp+E0h] [rbp-98h]
  __int64 v114; // [rsp+E8h] [rbp-90h]
  union _LARGE_INTEGER v115; // [rsp+F0h] [rbp-88h] BYREF
  __int64 v116; // [rsp+F8h] [rbp-80h]
  __int64 v117; // [rsp+100h] [rbp-78h] BYREF
  __int64 v118; // [rsp+108h] [rbp-70h]
  __int64 v119; // [rsp+110h] [rbp-68h]
  __int64 v120; // [rsp+118h] [rbp-60h] BYREF
  _DWORD *v121; // [rsp+120h] [rbp-58h]
  int v122; // [rsp+128h] [rbp-50h]
  LARGE_INTEGER v123; // [rsp+130h] [rbp-48h]
  __int64 v124; // [rsp+138h] [rbp-40h]
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+190h] [rbp+18h]
  union _LARGE_INTEGER v127; // [rsp+190h] [rbp+18h]
  bool v128; // [rsp+190h] [rbp+18h]
  __int16 v129; // [rsp+198h] [rbp+20h]
  __int16 v130; // [rsp+198h] [rbp+20h]

  v2 = Irp;
  v3 = (_BYTE *)Context;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  p_Type = &CurrentStackLocation->FileObject->Type;
  FileObject = p_Type;
  Entry = 0;
  v5 = p_Type[3];
  *(_QWORD *)v101 = v5;
  if ( v5 )
  {
    v6 = p_Type[4];
    if ( !v6 )
    {
LABEL_6:
      v9 = -1073741811;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(Context, 0xC000000D, 0x1272CAu);
      NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741811, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v9;
      v10 = 1209035;
LABEL_311:
      NtfsStatusTraceAndDebugInternal(0, v9, v10);
      return v9;
    }
    v7 = *(_QWORD *)(v5 + 192);
    v103 = *(_QWORD *)(v5 + 184);
    v8 = *(unsigned __int8 *)(v6 + 88);
  }
  else
  {
    v7 = 0;
    v6 = 0;
    v103 = 0;
    v8 = 1;
  }
  v119 = v7;
  if ( v8 != 2 )
    goto LABEL_6;
  PerformanceCounter = KeQueryPerformanceCounter(0);
  ++*(_QWORD *)(v7 + 9712);
  v12 = *(_DWORD *)(v7 + 4);
  if ( (v12 & 0xA000021) != 1 )
  {
    if ( (v12 & 0x20) != 0 )
    {
      ++*(_QWORD *)(v7 + 9728);
      v9 = -1073741431;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000189, 0x1272E5u);
      NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741431, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v9;
      v10 = 1209062;
      goto LABEL_311;
    }
    if ( (v12 & 0x8000001) != 1 )
    {
      ++*(_QWORD *)(v7 + 9728);
      v9 = -1073741202;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC000026E, 0x1272F3u);
      NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741202, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v9;
      v10 = 1209076;
      goto LABEL_311;
    }
    if ( (v12 & 0x2000000) != 0 )
    {
      ++*(_QWORD *)(v7 + 9728);
      v13 = -1073741662;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC00000A2, 0x1272FFu);
      NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741662, v2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v13;
      v14 = 1209088;
      goto LABEL_22;
    }
  }
  v124 = v5;
  if ( (*(_DWORD *)(v5 + 512) & 0x1000000) != 0 )
  {
    ++*(_QWORD *)(v7 + 9728);
    v13 = -1073741816;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000008, 0x127308u);
    NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741816, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1209097;
    goto LABEL_22;
  }
  if ( v6 && (*(_DWORD *)(v6 + 4) & 0x2000) != 0 )
  {
    ++*(_QWORD *)(v7 + 9728);
    v9 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC000000D, 0x127316u);
    NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v9;
    v10 = 1209111;
    goto LABEL_311;
  }
  if ( (*(_WORD *)(v5 + 460) & 0x40FF) != 0 )
  {
    ++*(_QWORD *)(v7 + 9728);
    v9 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC000000D, 0x127322u);
    NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v9;
    v10 = 1209123;
    goto LABEL_311;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  if ( Options < 0x18 )
  {
    ++*(_QWORD *)(v7 + 9728);
    v9 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC000000D, 0x12732Eu);
    NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v9;
    v10 = 1209135;
    goto LABEL_311;
  }
  MasterIrp = (ULONG *)v2->AssociatedIrp.MasterIrp;
  v17 = MasterIrp[1];
  v18 = 0;
  if ( !v17
    || (v19 = 16LL * (v17 - 1), v19 > 0xFFFFFFFF)
    || (int)v19 + 24 < (unsigned int)v19
    || Options < (int)v19 + 24 )
  {
    ++*(_QWORD *)(v7 + 9728);
    v9 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC000000D, 0x127344u);
    NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v9;
    v10 = 1209157;
    goto LABEL_311;
  }
  if ( CurrentStackLocation->Parameters.Read.Length - 1 <= 2 )
  {
    ++*(_QWORD *)(v7 + 9728);
    v9 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC000000D, 0x127352u);
    NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741811, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v9;
    v10 = 1209171;
    goto LABEL_311;
  }
  if ( *(_BYTE *)(v7 + 5521) )
  {
    ++*(_QWORD *)(v7 + 9728);
    if ( (*(_DWORD *)(v7 + 24) & 0x40000) != 0 )
    {
      NtfsExtendedCompleteRequestInternal((__int64)v3, v2, 0, v2 != 0, 1);
      return 0;
    }
    v13 = -1073741637;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC00000BB, 0x12736Cu);
    NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741637, v2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1209197;
LABEL_22:
    NtfsStatusTraceAndDebugInternal(0, v13, v14);
    return v13;
  }
  v20 = ExAllocateFromLookasideListEx(&NtfsFileLevelTrimContextLookasideList);
  v21 = v20;
  v99 = (__int64)v20;
  if ( !v20 )
  {
    ++*(_QWORD *)(v7 + 9728);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC000009A, 0x12737Bu);
    NtfsExtendedCompleteRequestInternal((__int64)v3, v2, -1073741670, v2 != 0, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x12737Cu);
    return 3221225626LL;
  }
  v109 = 0;
  v113 = 0;
  v118 = 0;
  v110 = 0;
  Src = 0;
  v104 = 0;
  v123 = PerformanceCounter;
  *(_WORD *)v20 = 1862;
  v20[1] = v7;
  v20[2] = v2;
  v20[6] = 1;
  *((_DWORD *)v20 + 14) = 0;
  v20[3] = 0;
  v20[4] = 0;
  if ( CurrentStackLocation->Parameters.Read.Length )
    v22 = v2->AssociatedIrp.MasterIrp;
  else
    v22 = 0;
  v21[5] = v22;
  *(_QWORD *)(v7 + 9736) += MasterIrp[1];
  v121 = 0;
  LODWORD(v98) = 0;
  v108 = 0;
  if ( **((_QWORD **)FileObject + 5)
    || (*(_DWORD *)(*(_QWORD *)v101 + 200LL) & 0x10) != 0
    && ((v23 = *(_QWORD *)(*(_QWORD *)v101 + 184LL), (v24 = *(_QWORD *)(v23 + 328)) == 0) || !*(_QWORD *)(v24 + 24))
    && (*(_DWORD *)(v23 + 4) & 0x20020100) == 0x20000000 )
  {
    if ( !NtfsAcquirePagingResourceExclusive((__int64)v3, v103, v3[12] & 1) )
      NtfsRaiseStatusInternal((__int64)v3, -1073741608, 0, 0, 1209289);
    goto LABEL_98;
  }
  if ( !NtfsAcquirePagingShared((__int64)v3, v103, v3[12] & 1, 0) )
    NtfsRaiseStatusInternal((__int64)v3, -1073741608, 0, 0, 1209296);
  if ( !**((_QWORD **)FileObject + 5) )
  {
    v25 = *(_QWORD *)v101;
    v26 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)v101 + 184LL) + 4LL);
    if ( (*(_DWORD *)(*(_QWORD *)v101 + 200LL) & 0x10) == 0 )
      goto LABEL_90;
    v27 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)v101 + 184LL) + 328LL);
    if ( v27 )
    {
      if ( *(_QWORD *)(v27 + 24) )
        goto LABEL_90;
    }
    if ( (v26 & 0x20100) != 0 )
      goto LABEL_90;
    if ( (v26 & 0x20000000) == 0 )
    {
      if ( (v26 & 0x10000000) == 0 )
      {
        if ( !NtfsGetPurgeKernelEAState(*(_QWORD *)(*(_QWORD *)v101 + 184LL)) )
        {
          v25 = *(_QWORD *)v101;
          goto LABEL_90;
        }
        goto LABEL_94;
      }
LABEL_90:
      if ( *(_DWORD *)(v25 + 448) || (v18 = 0, (*(_WORD *)(v25 + 460) & 0x80FF) != 0) )
        v18 = 2;
      goto LABEL_99;
    }
  }
LABEL_94:
  NtfsReleasePagingResourcePriv(v25, v103);
  if ( !NtfsAcquirePagingResourceExclusive((__int64)v3, v103, v3[12] & 1) )
    NtfsRaiseStatusInternal((__int64)v3, -1073741608, 0, 0, 1209306);
LABEL_98:
  v25 = *(_QWORD *)v101;
LABEL_99:
  v21[3] = *(_QWORD *)(v103 + 112);
  v21[4] = KeGetCurrentThread();
  v28 = *(_WORD *)(v25 + 460);
  v30 = (unsigned __int16)v28 >> 15;
  v29 = v18 & 0xFB;
  LOBYTE(v30) = v29 | (4 * (v28 < 0));
  v129 = v30;
  if ( ((v29 & 2) != 0 || (v30 & 4) != 0) && (*((_DWORD *)v3 + 3) & 1) == 0 )
    NtfsRaiseStatusInternal((__int64)v3, -1073741608, 0, 0, 1209340);
  v31 = *(_DWORD *)(v25 + 512);
  if ( (v31 & 0x4000000) != 0 )
  {
    v32 = -1073741431;
    if ( !NtfsStatusDebugFlags )
    {
LABEL_106:
      v34 = v99;
      *(_DWORD *)(v99 + 56) = v32;
      goto LABEL_267;
    }
    v33 = 1209350;
LABEL_105:
    NtfsStatusTraceAndDebugInternal(0, v32, v33);
    goto LABEL_106;
  }
  if ( (v31 & 0x40) != 0 )
  {
    v32 = -1073741533;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_106;
    v33 = 1209361;
    goto LABEL_105;
  }
  if ( (v31 & 0x10000) != 0 )
    v32 = -1073741202;
  else
    v32 = (v31 & 0x1000000) != 0 ? 0xC0000008 : 0;
  if ( v32 < 0 )
  {
    if ( !NtfsStatusDebugFlags )
      goto LABEL_106;
    v33 = 1209372;
    goto LABEL_105;
  }
  if ( (v28 & 0x40FF) != 0 )
  {
    v32 = -1073741811;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_106;
    v33 = 1209386;
    goto LABEL_105;
  }
  v35 = FsRtlCheckOplockEx((POPLOCK)(v25 + 88), v2, 0, v3, NtfsOplockComplete, (POPLOCK_FS_PREPOST_IRP)NtfsPrePostIrp);
  v32 = v35;
  if ( v35 < 0 )
  {
    if ( !NtfsStatusDebugFlags
      || (unsigned int)v35 >= 0xFFFFFFED
      || v35 == -1073741802
      || v35 == -1073741807
      || (unsigned int)(v35 + 2147483643) <= 1
      || v35 == -1073741608 )
    {
      goto LABEL_106;
    }
    v33 = 1209409;
    goto LABEL_105;
  }
  if ( v35 == 259 )
  {
    v34 = v99;
    *(_QWORD *)(v99 + 16) = 0;
    v3 = 0;
    goto LABEL_267;
  }
  if ( (*(_DWORD *)(*(_QWORD *)v101 + 200LL) & 8) != 0 )
  {
    v32 = 0;
    v34 = v99;
    goto LABEL_267;
  }
  if ( (v129 & 2) != 0 )
  {
    v36 = ExAllocateFromLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList);
    Src = v36;
    if ( !v36 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x127472u);
      v32 = -1073741670;
      goto LABEL_106;
    }
    *v36 = 1863;
    v34 = v99;
    *((_QWORD *)v36 + 1) = v99;
    *((_DWORD *)v36 + 4) = 0;
  }
  else
  {
    v34 = v99;
  }
  v37 = *(_QWORD *)v101;
  NtfsPostUsnChangeWithOverrideOption((__int64)v3, *(__int64 *)v101, 1, 0, 0, 0, 0);
  NtfsCheckpointCurrentTransaction((__int64)v3);
  *(_QWORD *)(v34 + 32) |= 3uLL;
  HIBYTE(v38) = HIBYTE(v129);
  LOBYTE(v38) = v129 | 1;
  v129 = v38;
  v39 = 0;
  v40 = MasterIrp;
  while ( 1 )
  {
    v105 = v39;
    if ( v39 >= v40[1] )
      goto LABEL_256;
    v41 = 2LL * v39;
    v42 = *(union _LARGE_INTEGER *)&v40[4 * v39 + 2];
    StartingByte = v42;
    v43 = *(union _LARGE_INTEGER *)&v40[2 * v41 + 4];
    Length = v43;
    v44 = 0;
    v114 = 0;
    if ( v43.QuadPart < 0x1000000000000000uLL )
    {
      v109 += v43.QuadPart;
    }
    else
    {
      v113 += v43.QuadPart;
      v118 = v113;
      if ( v113 < v43.QuadPart )
      {
        v113 = -1;
        v118 = -1;
      }
    }
    v45 = v42.LowPart & 0xFFF;
    if ( (v42.LowPart & 0xFFF) != 0 )
    {
      v44 = v42.LowPart & 0xFFF;
      v114 = v44;
      QuadPart = 4096 - v45 + v42.QuadPart;
      if ( QuadPart < v42.QuadPart )
      {
        StartingByte.QuadPart = -1;
        v32 = -1073741675;
        QuadPart = -1;
      }
      else
      {
        StartingByte.QuadPart = 4096 - v45 + v42.QuadPart;
        v32 = 0;
      }
      if ( v32 < 0 )
      {
        if ( *(int *)(v34 + 56) < 0 )
          goto LABEL_266;
        if ( NtfsStatusDebugFlags )
        {
          v47 = 1209566;
          goto LABEL_152;
        }
        goto LABEL_153;
      }
      if ( v43.QuadPart < (unsigned __int64)(4096 - v45) )
      {
        Length.QuadPart = 0;
        v43.QuadPart = 0;
      }
      else
      {
        v43.QuadPart = v45 + v43.QuadPart - 4096;
        Length = v43;
        v44 = 4096;
        v114 = 4096;
      }
    }
    else
    {
      QuadPart = v42.QuadPart;
    }
    v48 = *(_QWORD *)(v37 + 24);
    if ( QuadPart >= v48 )
    {
LABEL_254:
      v40 = MasterIrp;
      goto LABEL_255;
    }
    v49 = -1;
    if ( v43.QuadPart + QuadPart >= QuadPart )
      v49 = v43.QuadPart + QuadPart;
    v32 = v43.QuadPart + QuadPart < QuadPart ? 0xC0000095 : 0;
    if ( v43.QuadPart + QuadPart < QuadPart )
    {
      if ( *(int *)(v34 + 56) < 0 )
        goto LABEL_266;
      if ( NtfsStatusDebugFlags )
      {
        v47 = 1209607;
LABEL_152:
        NtfsStatusTraceAndDebugInternal(0, v32, v47);
      }
LABEL_153:
      *(_DWORD *)(v34 + 56) = v32;
      goto LABEL_266;
    }
    if ( v49 <= v48 )
    {
      v50 = v43;
    }
    else
    {
      v50.QuadPart = v48 - QuadPart;
      Length = v50;
    }
    v40 = MasterIrp;
    if ( *(_QWORD *)&MasterIrp[2 * v41 + 4] != -1 )
    {
      v44 += v50.LowPart & 0xFFF;
      v114 = v44;
    }
    Length.QuadPart = v50.QuadPart & 0xFFFFFFFFFFFFF000uLL;
    if ( (v50.QuadPart & 0xFFFFFFFFFFFFF000uLL) != 0 )
      break;
LABEL_255:
    v39 = v105 + 1;
  }
  if ( v44 )
  {
    ++*(_QWORD *)(v7 + 9760);
    *(_QWORD *)(v7 + 9768) += v44;
  }
  if ( *(_QWORD *)(v37 + 584) )
  {
    v51 = *v40;
    v52 = *(FILE_LOCK **)(v37 + 584);
    RequestorProcess = IoGetRequestorProcess(Irp);
    if ( !FsRtlFastCheckLockForWrite(v52, &StartingByte, &Length, v51, FileObject, RequestorProcess) )
    {
      v32 = -1073741740;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC0000054, 0x127547u);
      v34 = v99;
      LODWORD(v37) = v101[0];
      if ( *(int *)(v99 + 56) >= 0 )
        *(_DWORD *)(v99 + 56) = -1073741740;
LABEL_256:
      if ( !(_DWORD)v98 )
        goto LABEL_266;
      v32 = NtfsSendTrimRequestToStorage((int)v3, v7, v37, (int)&Entry, (__int64)&v108, (__int64)&v98, v34, Src, 0);
      if ( v32 >= 0
        || !NtfsStatusDebugFlags
        || (unsigned int)v32 >= 0xFFFFFFED
        || v32 == -1073741802
        || v32 == -1073741807
        || (unsigned int)(v32 + 2147483643) <= 1
        || v32 == -1073741608 )
      {
        goto LABEL_266;
      }
      v57 = 1210166;
LABEL_265:
      NtfsStatusTraceAndDebugInternal(0, v32, v57);
      goto LABEL_266;
    }
    v34 = v99;
    v37 = *(_QWORD *)v101;
  }
  NtfsPostUsnChangeWithOverrideOption((__int64)v3, v37, 1, 0, StartingByte.QuadPart, Length.QuadPart, 0);
  if ( **((_QWORD **)FileObject + 5) )
  {
    v115 = StartingByte;
    v54 = Length;
    v55 = Length;
    v127 = Length;
    while ( 1 )
    {
      if ( !v55.QuadPart )
        goto LABEL_191;
      if ( v55.QuadPart > 0xFFFFF000uLL )
        v54.QuadPart = 4294963200LL;
      v111 = v54.QuadPart;
      if ( !NtfsPurgeCacheSection((__int64)v3, (__int64 *)v37, &v115, v54.LowPart, 2u) )
        break;
      v115.QuadPart += (unsigned int)v111;
      v55.QuadPart = v127.QuadPart - (unsigned int)v111;
      v127 = v55;
      v54.QuadPart = v55.LowPart;
    }
    v32 = -1073740747;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 0xC0000435, 0x127582u);
    if ( *(int *)(v34 + 56) < 0 )
      goto LABEL_266;
    goto LABEL_153;
  }
LABEL_191:
  NtfsPreloadAllocationInternal(
    (__int64)v3,
    v37,
    0,
    StartingByte.QuadPart >> *(_BYTE *)(v7 + 488),
    (StartingByte.QuadPart + Length.QuadPart + *(unsigned int *)(v7 + 480)) >> *(_BYTE *)(v7 + 488),
    0);
  LOBYTE(v56) = v129;
  if ( (v129 & 2) != 0 )
  {
    if ( Entry )
    {
      if ( (unsigned int)(1024 - *((_DWORD *)Entry + 5)) < 16
                                                         * ((unsigned int)(v98 + 1)
                                                          + 2
                                                          * (unsigned __int64)(unsigned int)(*((_DWORD *)Src + 4) + 1))
                                                         + 40 )
      {
        v32 = NtfsSendTrimRequestToStorage((int)v3, v7, v37, (int)&Entry, (__int64)&v108, (__int64)&v98, v34, Src, 0);
        if ( v32 < 0 )
        {
          if ( !NtfsStatusDebugFlags
            || (unsigned int)v32 >= 0xFFFFFFED
            || v32 == -1073741802
            || v32 == -1073741807
            || (unsigned int)(v32 + 2147483643) <= 1
            || v32 == -1073741608 )
          {
            goto LABEL_266;
          }
          v57 = 1209805;
          goto LABEL_265;
        }
      }
    }
    NtfsAcquireRange(
      (__int64)v3,
      v37,
      StartingByte.QuadPart,
      Length.QuadPart,
      v104 | 0x14,
      (__int64)Src + 32 * *((unsigned int *)Src + 4) + 24);
    v104 = 32;
    v122 = 32;
    ++*((_DWORD *)Src + 4);
    LOBYTE(v56) = v129;
  }
  v95 = 0;
  v58 = Length;
  while ( 1 )
  {
LABEL_204:
    if ( !v58.QuadPart )
    {
      if ( v95 )
      {
        ++*(_DWORD *)(v34 + 52);
      }
      else if ( (v56 & 2) != 0 )
      {
        v78 = (int *)Src;
        --*((_DWORD *)Src + 4);
        NtfsReleaseRangeInternal(&v78[8 * v78[4] + 6]);
      }
      goto LABEL_254;
    }
    v120 = 0;
    v117 = 0;
    v128 = (v56 & 4) != 0;
    if ( (v56 & 4) == 0 )
      break;
    v59.QuadPart = *(unsigned int *)(v37 + 452);
    if ( ((v59.LowPart - 1) & StartingByte.LowPart) != 0 || v58.QuadPart < (unsigned __int64)v59.QuadPart )
      break;
    v60 = v58.LowPart & -v59.LowPart;
    NtfsAcquireExclusiveScbEx((__int64)v3, v37, 0);
    HIBYTE(v61) = HIBYTE(v129);
    LOBYTE(v61) = v129 | 8;
    v130 = v61;
    NtfsDeleteAllocation(
      (__int64)v3,
      (struct _FILE_OBJECT *)FileObject,
      v37,
      StartingByte.QuadPart >> *(_BYTE *)(v7 + 488),
      (v60 + StartingByte.QuadPart - 1) >> *(_BYTE *)(v7 + 488),
      1u,
      1);
    NtfsCheckpointCurrentTransaction((__int64)v3);
    NtfsReleaseFcbEx((__int64)v3, *(_QWORD *)(v37 + 184), 0);
    HIBYTE(v56) = HIBYTE(v130);
    LOBYTE(v56) = v130 & 0xF7;
    v129 = v56;
    StartingByte.QuadPart += v60;
    v58.QuadPart = Length.QuadPart - v60;
    Length.QuadPart -= v60;
    v34 = v99;
  }
  v62 = NtfsLookupAllocation((__int64)v3, v37, StartingByte.QuadPart >> *(_BYTE *)(v7 + 488), &v120, &v117);
  v64 = *(_BYTE *)(v7 + 488);
  if ( !v62 )
  {
    if ( *(__int16 *)(v37 + 460) >= 0 )
    {
      v75 = v103;
      v76 = v103 + 8;
      NtfsAttachCorruption_BadOrOrphanFRS((__int64)v3, 2, 1210083, v63, (_DWORD *)(v103 + 8), v103, 0);
      NtfsAttachRepairInfoPriv((__int64)v3, 256, 0, (struct _LIST_ENTRY *)0x10E001276E3LL);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)v3, 0xC0000102, 0x1276E3u);
      NtfsRaiseStatusInternal((__int64)v3, -1073741566, v76, v75, 1210083);
    }
    v77 = v117 << v64;
    if ( (unsigned __int64)(v117 << v64) >= Length.QuadPart )
    {
      StartingByte.QuadPart += Length.QuadPart;
      v58.QuadPart = 0;
      Length.QuadPart = 0;
    }
    else
    {
      v58.QuadPart = Length.QuadPart - v77;
      Length.QuadPart -= v77;
      StartingByte.QuadPart += v77;
    }
    goto LABEL_249;
  }
  v116 = v120 << v64;
  v112 = v117 << v64;
  v111 = StartingByte.QuadPart % (unsigned __int64)*(unsigned int *)(v7 + 356);
  if ( !Entry )
    goto LABEL_224;
  if ( (v129 & 2) != 0 )
    v65 = 32LL * *((unsigned int *)Src + 4) + 40;
  else
    v65 = 16;
  if ( (unsigned int)(1024 - *((_DWORD *)Entry + 5)) >= v65 + 16 * (unsigned __int64)(unsigned int)(v98 + 1)
    || (v32 = NtfsSendTrimRequestToStorage((int)v3, v7, v37, (int)&Entry, (__int64)&v108, (__int64)&v98, v34, Src, 1),
        v32 >= 0) )
  {
    if ( Entry )
    {
LABEL_231:
      v68 = v111;
      v69 = v116;
      v70.QuadPart = v112;
      if ( v111 )
      {
        v69 = v111 + v116;
        v116 += v111;
        v70.QuadPart = v112 - v111;
        v112 -= v111;
      }
      if ( v128 )
      {
        v71 = (unsigned int)-*(_DWORD *)(v37 + 452);
        v72 = v71 & (StartingByte.QuadPart + (unsigned int)(*(_DWORD *)(v37 + 452) - 1));
        if ( v72 < (v71 & (Length.QuadPart + StartingByte.QuadPart)) )
        {
          v70.QuadPart = v72 - StartingByte.QuadPart;
          v112 = v72 - StartingByte.QuadPart;
        }
        v68 = v111;
      }
      if ( v70.QuadPart >= (unsigned __int64)Length.QuadPart )
      {
        v70 = Length;
        v58.QuadPart = 0;
        Length.QuadPart = 0;
      }
      else
      {
        v58.QuadPart = Length.QuadPart - v70.QuadPart;
        Length.QuadPart -= v70.QuadPart;
      }
      StartingByte.QuadPart += v70.QuadPart;
      if ( v70.QuadPart )
      {
        v73 = 2LL * (unsigned int)v98;
        v74 = v121;
        *(_QWORD *)&v121[2 * v73] = v69;
        *(union _LARGE_INTEGER *)&v74[2 * v73 + 2] = v70;
        v108 += v70.QuadPart;
        v110 += v70.QuadPart;
        LODWORD(v98) = v98 + 1;
        v95 = 1;
        ++*(_QWORD *)(v7 + 9776);
        *(_QWORD *)(v7 + 9784) += v68;
        v58 = Length;
      }
LABEL_249:
      LOBYTE(v56) = v129;
      goto LABEL_204;
    }
LABEL_224:
    v66 = ExAllocateFromLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList);
    Entry = v66;
    if ( !v66 )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC000009A, 0x127667u);
      v32 = -1073741670;
      goto LABEL_153;
    }
    memset(v66, 0, 0x400u);
    v67 = Entry;
    *(_DWORD *)Entry = 28;
    v67[1] = 1;
    if ( (*(_DWORD *)(v103 + 4) & 4) != 0 )
      v67[2] |= 0x40000000u;
    v67[5] = 32;
    v121 = v67 + 8;
    goto LABEL_231;
  }
  if ( NtfsStatusDebugFlags
    && (unsigned int)v32 < 0xFFFFFFED
    && v32 != -1073741802
    && v32 != -1073741807
    && (unsigned int)(v32 + 2147483643) > 1
    && v32 != -1073741608 )
  {
    v57 = 1209939;
    goto LABEL_265;
  }
LABEL_266:
  v2 = Irp;
LABEL_267:
  KeQueryPerformanceCounter(0);
  v79 = v109;
  *(_QWORD *)(v7 + 9744) += v109;
  v80 = v113;
  *(_QWORD *)(v7 + 9752) += v113;
  *(_QWORD *)(v7 + 9792) += v110;
  v81 = v80;
  if ( !v80 )
    v81 = v79;
  NtfsTelemetryBucketizeFileLevelTrimSize(1, v81, v7 + 9800);
  v83 = v80;
  if ( !v80 )
    v83 = v82;
  v84 = NtfsTelemetryBucketizeFileLevelTrimSize(v82, v83, v7 + 9896);
  v86 = v80;
  if ( !v80 )
    v86 = v85;
  NtfsTelemetryBucketizeFileLevelTrimSize(v84, v86, v7 + 10088);
  NtfsTelemetryBucketizeFileLevelTrimSize(v87, v110, v7 + 9992);
  if ( !v80 )
    v80 = v109;
  v90 = NtfsTelemetryBucketizeFileLevelTrimSize(v88, v80, v89);
  v91 = 0;
  do
  {
    if ( v90 < FileLevelTrimLatencyBuckets[v91] )
      break;
    v91 = (unsigned int)(v91 + 1);
  }
  while ( (unsigned int)v91 < 0xE );
  if ( (unsigned int)v91 < 0xF )
    ++*(_QWORD *)(v7 + 8 * v91 + 10184);
  if ( (v129 & 8) != 0 )
    NtfsReleaseFcbEx((__int64)v3, *(_QWORD *)(*(_QWORD *)v101 + 184LL), 0);
  if ( Entry )
    ExFreeToLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList, Entry);
  if ( v32 < 0 )
  {
    if ( v32 == -1073741608 || v32 == -1073741432 )
    {
      ++*(_QWORD *)(v7 + 9720);
    }
    else
    {
      ++*(_QWORD *)(v7 + 9728);
      for ( i = 0; i < 0xC; ++i )
      {
        v93 = *(_DWORD *)(v7 + 4LL * i + 10304);
        if ( v32 == v93 )
          goto LABEL_293;
        if ( !v93 )
        {
          *(_DWORD *)(v7 + 4LL * i + 10304) = v32;
LABEL_293:
          ++*(_QWORD *)(v7 + 8LL * i + 10352);
          break;
        }
      }
    }
  }
  if ( *(_QWORD *)(v34 + 16) )
    v2->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  if ( (v129 & 1) != 0 )
    ExSetResourceOwnerPointerEx(*(PERESOURCE *)(v34 + 24), *(PVOID *)(v34 + 32), 1u);
  v94 = Src;
  if ( Src )
    v34 = (__int64)Src;
  NtfsAsyncFileLevelTrimCompletionRoutine(0, 0, v34);
  if ( v94 )
    ExFreeToLookasideListEx(&NtfsDeviceManageDataSetAttributesLookasideList, v94);
  if ( v3 )
    NtfsExtendedCompleteRequestInternal((__int64)v3, 0, 259, 0, 1);
  return 259;
}

```

## disassembly

```asm
0x1402336bc  mov     [rsp+Irp], rdx
0x1402336c1  mov     [rsp+arg_0], rcx
0x1402336c6  push    rbx
0x1402336c7  push    rsi
0x1402336c8  push    rdi
0x1402336c9  push    r12
0x1402336cb  push    r13
0x1402336cd  push    r14
0x1402336cf  push    r15
0x1402336d1  sub     rsp, 140h
0x1402336d8  mov     rsi, rdx
0x1402336db  mov     r13, rcx
0x1402336de  mov     rax, [rdx+0B8h]
0x1402336e5  mov     [rsp+178h+arg_10], rax
0x1402336ed  mov     rax, [rax+30h]
0x1402336f1  mov     [rsp+178h+FileObject], rax
0x1402336f9  xor     edi, edi
0x1402336fb  mov     [rsp+178h+Entry], rdi
0x140233703  mov     r14, [rax+18h]
0x140233707  mov     qword ptr [rsp+178h+var_F0], r14
0x14023370f  test    r14, r14
0x140233712  jz      short loc_14023373D
0x140233714  mov     rbx, [rax+20h]
0x140233718  test    rbx, rbx
0x14023371b  jz      short loc_140233761
0x14023371d  mov     r15, [r14+0C0h]
0x140233724  mov     rcx, [r14+0B8h]
0x14023372b  mov     [rsp+178h+var_E0], rcx
0x140233733  movzx   eax, byte ptr [rbx+58h]
0x140233737  lea     r12d, [rdi+1]
0x14023373b  jmp     short loc_140233754
0x14023373d  mov     r15, rdi
0x140233740  mov     rbx, rdi
0x140233743  mov     [rsp+178h+var_E0], rdi
0x14023374b  mov     r12d, 1
0x140233751  mov     eax, r12d
0x140233754  mov     [rsp+178h+var_68], r15
0x14023375c  cmp     eax, 2
0x14023375f  jz      short loc_1402337B4
0x140233761  mov     al, cs:NtfsStatusDebugFlags
0x140233767  mov     r14d, 0C000000Dh
0x14023376d  test    al, al
0x14023376f  jz      short loc_140233782
0x140233771  mov     r8d, 1272CAh
0x140233777  mov     edx, r14d
0x14023377a  mov     rcx, r13
0x14023377d  call    NtfsStatusTraceAndDebugInternal
0x140233782  test    rsi, rsi
0x140233785  setnz   r9b
0x140233789  mov     dword ptr [rsp+178h+CompletionRoutine], edi
0x14023378d  mov     r8d, r14d
0x140233790  mov     rdx, rsi
0x140233793  mov     rcx, r13
0x140233796  call    NtfsExtendedCompleteRequestInternal
0x14023379b  mov     al, cs:NtfsStatusDebugFlags
0x1402337a1  test    al, al
0x1402337a3  jz      loc_140234F87
0x1402337a9  mov     r8d, 1272CBh
0x1402337af  jmp     loc_140234F7D
0x1402337b4  xor     ecx, ecx; PerformanceFrequency
0x1402337b6  call    cs:__imp_KeQueryPerformanceCounter
0x1402337bd  nop     dword ptr [rax+rax+00h]
0x1402337c2  mov     rdi, rax
0x1402337c5  add     [r15+25F0h], r12
0x1402337cc  mov     ecx, [r15+4]
0x1402337d0  mov     eax, ecx
0x1402337d2  and     eax, 0A000021h
0x1402337d7  cmp     eax, r12d
0x1402337da  jz      loc_140233914
0x1402337e0  test    cl, 20h
0x1402337e3  jz      short loc_140233841
0x1402337e5  add     [r15+2600h], r12
0x1402337ec  mov     al, cs:NtfsStatusDebugFlags
0x1402337f2  xor     ebx, ebx
0x1402337f4  mov     r14d, 0C0000189h
0x1402337fa  test    al, al
0x1402337fc  jz      short loc_14023380F
0x1402337fe  mov     r8d, 1272E5h
0x140233804  mov     edx, r14d
0x140233807  mov     rcx, r13
0x14023380a  call    NtfsStatusTraceAndDebugInternal
0x14023380f  test    rsi, rsi
0x140233812  setnz   r9b
0x140233816  mov     dword ptr [rsp+178h+CompletionRoutine], ebx
0x14023381a  mov     r8d, r14d
0x14023381d  mov     rdx, rsi
0x140233820  mov     rcx, r13
0x140233823  call    NtfsExtendedCompleteRequestInternal
0x140233828  mov     al, cs:NtfsStatusDebugFlags
0x14023382e  test    al, al
0x140233830  jz      loc_140234F87
0x140233836  mov     r8d, 1272E6h
0x14023383c  jmp     loc_140234F7D
0x140233841  mov     eax, ecx
0x140233843  and     eax, 8000001h
0x140233848  cmp     eax, r12d
0x14023384b  jnz     short loc_1402338B8
0x14023384d  bt      ecx, 19h
0x140233851  jnb     loc_140233914
0x140233857  add     [r15+2600h], r12
0x14023385e  mov     al, cs:NtfsStatusDebugFlags
0x140233864  xor     edi, edi
0x140233866  mov     ebx, 0C00000A2h
0x14023386b  test    al, al
0x14023386d  jz      short loc_14023387F
0x14023386f  mov     r8d, 1272FFh
0x140233875  mov     edx, ebx
0x140233877  mov     rcx, r13
0x14023387a  call    NtfsStatusTraceAndDebugInternal
0x14023387f  test    rsi, rsi
0x140233882  setnz   r9b
0x140233886  mov     dword ptr [rsp+178h+CompletionRoutine], edi
0x14023388a  mov     r8d, ebx
0x14023388d  mov     rdx, rsi
0x140233890  mov     rcx, r13
0x140233893  call    NtfsExtendedCompleteRequestInternal
0x140233898  mov     cl, cs:NtfsStatusDebugFlags
0x14023389e  test    cl, cl
0x1402338a0  jz      short loc_1402338B1
0x1402338a2  mov     r8d, 127300h
0x1402338a8  mov     edx, ebx
0x1402338aa  xor     ecx, ecx
0x1402338ac  call    NtfsStatusTraceAndDebugInternal
0x1402338b1  mov     eax, ebx
0x1402338b3  jmp     loc_140234F8A
0x1402338b8  add     [r15+2600h], r12
0x1402338bf  mov     al, cs:NtfsStatusDebugFlags
0x1402338c5  xor     ebx, ebx
0x1402338c7  mov     r14d, 0C000026Eh
0x1402338cd  test    al, al
0x1402338cf  jz      short loc_1402338E2
0x1402338d1  mov     r8d, 1272F3h
0x1402338d7  mov     edx, r14d
0x1402338da  mov     rcx, r13
0x1402338dd  call    NtfsStatusTraceAndDebugInternal
0x1402338e2  test    rsi, rsi
0x1402338e5  setnz   r9b
0x1402338e9  mov     dword ptr [rsp+178h+CompletionRoutine], ebx
0x1402338ed  mov     r8d, r14d
0x1402338f0  mov     rdx, rsi
0x1402338f3  mov     rcx, r13
0x1402338f6  call    NtfsExtendedCompleteRequestInternal
0x1402338fb  mov     al, cs:NtfsStatusDebugFlags
0x140233901  test    al, al
0x140233903  jz      loc_140234F87
0x140233909  mov     r8d, 1272F4h
0x14023390f  jmp     loc_140234F7D
0x140233914  mov     [rsp+178h+var_40], r14
0x14023391c  test    dword ptr [r14+200h], 1000000h
0x140233927  jz      short loc_140233983
0x140233929  add     [r15+2600h], r12
0x140233930  mov     al, cs:NtfsStatusDebugFlags
0x140233936  xor     edi, edi
0x140233938  mov     ebx, 0C0000008h
0x14023393d  test    al, al
0x14023393f  jz      short loc_140233951
0x140233941  mov     r8d, 127308h
0x140233947  mov     edx, ebx
0x140233949  mov     rcx, r13
0x14023394c  call    NtfsStatusTraceAndDebugInternal
0x140233951  test    rsi, rsi
0x140233954  setnz   r9b
0x140233958  mov     dword ptr [rsp+178h+CompletionRoutine], edi
0x14023395c  mov     r8d, ebx
0x14023395f  mov     rdx, rsi
0x140233962  mov     rcx, r13
0x140233965  call    NtfsExtendedCompleteRequestInternal
0x14023396a  mov     cl, cs:NtfsStatusDebugFlags
0x140233970  test    cl, cl
0x140233972  jz      loc_1402338B1
0x140233978  mov     r8d, 127309h
0x14023397e  jmp     loc_1402338A8
0x140233983  xor     ecx, ecx
0x140233985  test    rbx, rbx
0x140233988  jz      short loc_1402339EF
0x14023398a  test    dword ptr [rbx+4], 2000h
0x140233991  jz      short loc_1402339EF
0x140233993  add     [r15+2600h], r12
0x14023399a  mov     al, cs:NtfsStatusDebugFlags
0x1402339a0  mov     r14d, 0C000000Dh
0x1402339a6  test    al, al
0x1402339a8  jz      short loc_1402339BD
0x1402339aa  mov     r8d, 127316h
0x1402339b0  mov     edx, r14d
0x1402339b3  mov     rcx, r13
0x1402339b6  call    NtfsStatusTraceAndDebugInternal
0x1402339bb  xor     ecx, ecx
0x1402339bd  test    rsi, rsi
0x1402339c0  setnz   r9b
0x1402339c4  mov     dword ptr [rsp+178h+CompletionRoutine], ecx
0x1402339c8  mov     r8d, r14d
0x1402339cb  mov     rdx, rsi
0x1402339ce  mov     rcx, r13
0x1402339d1  call    NtfsExtendedCompleteRequestInternal
0x1402339d6  mov     al, cs:NtfsStatusDebugFlags
0x1402339dc  test    al, al
0x1402339de  jz      loc_140234F87
0x1402339e4  mov     r8d, 127317h
0x1402339ea  jmp     loc_140234F7D
0x1402339ef  mov     edx, 40FFh
0x1402339f4  test    [r14+1CCh], dx
0x1402339fc  jz      short loc_140233A5A
0x1402339fe  add     [r15+2600h], r12
0x140233a05  mov     al, cs:NtfsStatusDebugFlags
0x140233a0b  mov     r14d, 0C000000Dh
0x140233a11  test    al, al
0x140233a13  jz      short loc_140233A28
0x140233a15  mov     r8d, 127322h
0x140233a1b  mov     edx, r14d
0x140233a1e  mov     rcx, r13
0x140233a21  call    NtfsStatusTraceAndDebugInternal
0x140233a26  xor     ecx, ecx
0x140233a28  test    rsi, rsi
0x140233a2b  setnz   r9b
0x140233a2f  mov     dword ptr [rsp+178h+CompletionRoutine], ecx
0x140233a33  mov     r8d, r14d
0x140233a36  mov     rdx, rsi
0x140233a39  mov     rcx, r13
0x140233a3c  call    NtfsExtendedCompleteRequestInternal
0x140233a41  mov     al, cs:NtfsStatusDebugFlags
0x140233a47  test    al, al
0x140233a49  jz      loc_140234F87
0x140233a4f  mov     r8d, 127323h
0x140233a55  jmp     loc_140234F7D
0x140233a5a  mov     rdx, [rsp+178h+arg_10]
0x140233a62  mov     r8d, [rdx+10h]
0x140233a66  cmp     r8d, 18h
0x140233a6a  jnb     short loc_140233AC8
0x140233a6c  add     [r15+2600h], r12
0x140233a73  mov     al, cs:NtfsStatusDebugFlags
0x140233a79  mov     r14d, 0C000000Dh
0x140233a7f  test    al, al
0x140233a81  jz      short loc_140233A96
0x140233a83  mov     r8d, 12732Eh
0x140233a89  mov     edx, r14d
0x140233a8c  mov     rcx, r13
0x140233a8f  call    NtfsStatusTraceAndDebugInternal
0x140233a94  xor     ecx, ecx
0x140233a96  test    rsi, rsi
0x140233a99  setnz   r9b
0x140233a9d  mov     dword ptr [rsp+178h+CompletionRoutine], ecx
0x140233aa1  mov     r8d, r14d
0x140233aa4  mov     rdx, rsi
0x140233aa7  mov     rcx, r13
0x140233aaa  call    NtfsExtendedCompleteRequestInternal
0x140233aaf  mov     al, cs:NtfsStatusDebugFlags
0x140233ab5  test    al, al
0x140233ab7  jz      loc_140234F87
0x140233abd  mov     r8d, 12732Fh
0x140233ac3  jmp     loc_140234F7D
0x140233ac8  mov     rax, [rsi+18h]
0x140233acc  mov     [rsp+178h+var_C8], rax
0x140233ad4  mov     eax, [rax+4]
0x140233ad7  xor     ebx, ebx
0x140233ad9  test    eax, eax
0x140233adb  jz      loc_140234F2C
0x140233ae1  lea     ecx, [rax-1]
0x140233ae4  shl     rcx, 4
0x140233ae8  mov     eax, 0FFFFFFFFh
0x140233aed  cmp     rcx, rax
0x140233af0  ja      loc_140234F2C
0x140233af6  lea     eax, [rcx+18h]
0x140233af9  cmp     eax, ecx
0x140233afb  jb      loc_140234F2C
0x140233b01  cmp     r8d, eax
0x140233b04  jb      loc_140234F2C
0x140233b0a  mov     eax, [rdx+8]
0x140233b0d  sub     eax, r12d
0x140233b10  cmp     eax, 2
0x140233b13  ja      short loc_140233B6F
0x140233b15  add     [r15+2600h], r12
0x140233b1c  mov     al, cs:NtfsStatusDebugFlags
0x140233b22  mov     r14d, 0C000000Dh
0x140233b28  test    al, al
0x140233b2a  jz      short loc_140233B3D
0x140233b2c  mov     r8d, 127352h
0x140233b32  mov     edx, r14d
0x140233b35  mov     rcx, r13
0x140233b38  call    NtfsStatusTraceAndDebugInternal
0x140233b3d  test    rsi, rsi
0x140233b40  setnz   r9b
0x140233b44  mov     dword ptr [rsp+178h+CompletionRoutine], ebx
0x140233b48  mov     r8d, r14d
0x140233b4b  mov     rdx, rsi
0x140233b4e  mov     rcx, r13
0x140233b51  call    NtfsExtendedCompleteRequestInternal
0x140233b56  mov     al, cs:NtfsStatusDebugFlags
0x140233b5c  test    al, al
0x140233b5e  jz      loc_140234F87
0x140233b64  mov     r8d, 127353h
0x140233b6a  jmp     loc_140234F7D
0x140233b6f  cmp     [r15+1591h], bl
0x140233b76  jz      loc_140233C01
0x140233b7c  add     [r15+2600h], r12
0x140233b83  test    dword ptr [r15+18h], 40000h
0x140233b8b  mov     al, cs:NtfsStatusDebugFlags
0x140233b91  jz      short loc_140233BB4
0x140233b93  test    rsi, rsi
0x140233b96  setnz   r9b
0x140233b9a  mov     dword ptr [rsp+178h+CompletionRoutine], r12d
  ... truncated ...
```
