# NtfsSetRenameInfo

- ea: `0x14024c894`
- end: `0x14024f784`
- name: `NtfsSetRenameInfo`
- size: `12016`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `59`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140202288`

## callees

- `0x140007ea0`
- `0x140009c80`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d1e0`
- `0x14000d510`
- `0x14000eaa0`
- `0x140012e10`
- `0x140012e70`
- `0x14003f358`
- `0x14003f52c`
- `0x140046ad8`
- `0x140046bc8`
- `0x140046d50`
- `0x140059250`
- `0x1400593c0`
- `0x1400596c0`
- `0x140059be0`
- `0x1400d2540`
- `0x1400d2740`
- `0x14011e31c`
- `0x140121590`
- `0x140128d50`
- `0x14012c7bc`
- `0x14012f930`
- `0x140140380`
- `0x1401419ec`
- `0x14014a7d0`
- `0x14014a930`
- `0x14014b5a8`
- `0x14014bae0`
- `0x140154138`
- `0x140154d10`
- `0x1401633d0`
- `0x140185788`
- `0x14018bf40`
- `0x14018c610`
- `0x14018dc4c`
- `0x14018f740`
- `0x140190410`
- `0x140192470`
- `0x14019379c`
- `0x1401990f0`
- `0x14019b330`
- `0x14019f220`
- `0x1401c00e0`
- `0x1401e0660`
- `0x1401eaf08`
- `0x1401fc460`
- `0x140204dac`

## import_xrefs

- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x14024e420`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x14024e420`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x14024e81d`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x14024e81d`
- `ntoskrnl!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14024d38e`
- `ntoskrnl!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14024d38e`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14024f498`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b88c9`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14024f498`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b88c9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14024f4b5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b88e9`
- `ntoskrnl!ExReleasePushLockEx` at `0x14024f4b5`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b88e9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024e75d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f3a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f3c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f3e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f400`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f41e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f441`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f476`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b87e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b87fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8819`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8834`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b884f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8871`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b88a3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024e75d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f3a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f3c7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f3e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f400`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f41e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f441`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f476`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b87e3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b87fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8819`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8834`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b884f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8871`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b88a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024dd24`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024dde2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024e453`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024ebe8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024edbb`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024dd24`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024dde2`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024e453`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024ebe8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024edbb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024db33`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024db33`
- `ntoskrnl!CcUnpinData` at `0x14024d8e8`
- `ntoskrnl!CcUnpinData` at `0x14024e145`
- `ntoskrnl!CcUnpinData` at `0x14024d8e8`
- `ntoskrnl!CcUnpinData` at `0x14024e145`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024dc90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024f722`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024dc90`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024f722`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14024ef16`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14024efcb`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14024ef16`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14024efcb`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14024d42b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14024d42b`
- `ntoskrnl!ExRaiseStatus` at `0x14024cd8a`
- `ntoskrnl!ExRaiseStatus` at `0x14024ce53`
- `ntoskrnl!ExRaiseStatus` at `0x14024e031`
- `ntoskrnl!ExRaiseStatus` at `0x14024e208`
- `ntoskrnl!ExRaiseStatus` at `0x14024cd8a`
- `ntoskrnl!ExRaiseStatus` at `0x14024ce53`
- `ntoskrnl!ExRaiseStatus` at `0x14024e031`
- `ntoskrnl!ExRaiseStatus` at `0x14024e208`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14024cde9`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14024cde9`

## pseudocode

```c
__int64 __fastcall NtfsSetRenameInfo(_QWORD *Context, __int64 a2, IRP *a3, __int64 a4, __int64 a5, __int64 a6)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v9; // r15
  int *v10; // rax
  int v11; // edx
  __int64 v13; // r11
  LARGE_INTEGER ByteOffset; // rbx
  __int64 v15; // rdx
  int v16; // r12d
  int v17; // r9d
  __int64 v18; // rdx
  unsigned __int16 v19; // ax
  unsigned int v20; // edi
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // r8
  char v24; // al
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // r8
  CLFS_LSN *v29; // rax
  CLFS_LSN v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // r10
  int v34; // r11d
  __int64 v35; // r9
  unsigned __int16 v36; // cx
  unsigned __int16 v37; // ax
  __int64 v38; // r10
  unsigned __int16 v39; // cx
  unsigned __int16 v40; // ax
  __int64 v41; // rdx
  __int64 v42; // rdx
  __int64 v43; // r8
  int v44; // edi
  __int64 v45; // rbx
  int v46; // eax
  unsigned int CurrentFileInfo; // eax
  __int64 v48; // rcx
  __int64 v49; // rbx
  __int64 v50; // r10
  unsigned __int16 v51; // cx
  unsigned __int16 v52; // ax
  __int64 NextScb; // rax
  __int64 v54; // r10
  int v55; // ecx
  char v56; // al
  char v57; // dl
  __int64 v58; // rcx
  int v59; // eax
  int v60; // eax
  __int64 v61; // rdx
  int v62; // ecx
  __int64 v63; // rdx
  int v64; // r8d
  int v65; // eax
  char v66; // al
  __int64 v67; // rbx
  int v68; // eax
  BOOL v69; // eax
  __int64 v70; // rax
  char v71; // bl
  char v72; // cl
  __int64 v73; // rax
  __int64 v74; // rax
  int v75; // eax
  __int64 v76; // rdx
  __int64 v77; // rax
  int v78; // eax
  int v79; // ecx
  unsigned __int8 *v80; // rbx
  __int64 v81; // rcx
  char *v82; // rbx
  char *v83; // rbx
  char *v84; // rcx
  int v85; // eax
  int v86; // eax
  __int64 *v87; // rax
  __int64 *v88; // rax
  __int64 v89; // rbx
  char v90; // cl
  int v91; // r8d
  int v92; // r8d
  int v93; // r8d
  __m128i *v94; // rdx
  __m128i *v95; // xmm1_8
  __m128i *v96; // rdx
  __m128i *v97; // xmm0_8
  char v98; // bl
  char v99; // dl
  int v100; // eax
  __int64 v101; // r9
  __int64 v102; // rbx
  int v103; // ecx
  BOOL v104; // ecx
  BOOL v105; // ecx
  __int16 v106; // bx
  int v107; // ebx
  __int16 v108; // bx
  __int64 v109; // rax
  _WORD *v110; // rcx
  PVOID v111; // r8
  char v112; // cl
  _DWORD *v113; // rcx
  char v114; // cl
  int v115; // r12d
  int v116; // r9d
  __int64 v117; // r10
  unsigned __int16 v118; // r8
  __int64 v119; // rax
  char v120[4]; // [rsp+F8h] [rbp-388h] BYREF
  unsigned int v121; // [rsp+FCh] [rbp-384h]
  char v122; // [rsp+100h] [rbp-380h]
  PVOID Contexta[2]; // [rsp+108h] [rbp-378h] BYREF
  int v124[4]; // [rsp+118h] [rbp-368h]
  PVOID Bcb[2]; // [rsp+128h] [rbp-358h] BYREF
  __int64 v126; // [rsp+138h] [rbp-348h]
  int v127; // [rsp+140h] [rbp-340h]
  _WORD v128[2]; // [rsp+144h] [rbp-33Ch] BYREF
  __int64 v129; // [rsp+148h] [rbp-338h]
  int v130; // [rsp+150h] [rbp-330h]
  int v131; // [rsp+154h] [rbp-32Ch] BYREF
  char v132; // [rsp+158h] [rbp-328h]
  __int64 v133; // [rsp+160h] [rbp-320h]
  void *Buf1[2]; // [rsp+168h] [rbp-318h] BYREF
  PVOID v135; // [rsp+178h] [rbp-308h] BYREF
  int v136; // [rsp+180h] [rbp-300h]
  int v137; // [rsp+184h] [rbp-2FCh]
  __int64 v138; // [rsp+188h] [rbp-2F8h]
  __int64 v139; // [rsp+190h] [rbp-2F0h] BYREF
  void *Src; // [rsp+198h] [rbp-2E8h]
  char v141; // [rsp+1A0h] [rbp-2E0h]
  int v142; // [rsp+1A4h] [rbp-2DCh]
  int v143; // [rsp+1A8h] [rbp-2D8h]
  __m128i *v144; // [rsp+1B0h] [rbp-2D0h]
  __int128 v145; // [rsp+1B8h] [rbp-2C8h] BYREF
  PVOID v146; // [rsp+1C8h] [rbp-2B8h]
  __int64 v147; // [rsp+1D0h] [rbp-2B0h] BYREF
  int v148; // [rsp+1D8h] [rbp-2A8h]
  int v149; // [rsp+1DCh] [rbp-2A4h]
  int v150; // [rsp+1E0h] [rbp-2A0h]
  int v151; // [rsp+1E4h] [rbp-29Ch]
  PVOID PoolWithTag; // [rsp+1E8h] [rbp-298h]
  void *Buf2[2]; // [rsp+1F0h] [rbp-290h] BYREF
  PIRP Irp; // [rsp+200h] [rbp-280h]
  __int64 v155; // [rsp+208h] [rbp-278h]
  PVOID v156[2]; // [rsp+210h] [rbp-270h] BYREF
  __int64 v157; // [rsp+220h] [rbp-260h]
  __int64 v158; // [rsp+228h] [rbp-258h]
  CLFS_LSN plsn; // [rsp+230h] [rbp-250h] BYREF
  int v160; // [rsp+238h] [rbp-248h]
  PVOID v161; // [rsp+240h] [rbp-240h]
  PVOID v162[2]; // [rsp+248h] [rbp-238h] BYREF
  __int128 v163; // [rsp+258h] [rbp-228h] BYREF
  __int64 v164; // [rsp+268h] [rbp-218h]
  __int64 v165; // [rsp+270h] [rbp-210h]
  _QWORD v166[4]; // [rsp+278h] [rbp-208h] BYREF
  __int64 v167[12]; // [rsp+298h] [rbp-1E8h] BYREF
  __m128i v168[7]; // [rsp+2F8h] [rbp-188h] BYREF
  _OWORD v169[7]; // [rsp+368h] [rbp-118h] BYREF
  __int64 v170[10]; // [rsp+3D8h] [rbp-A8h] BYREF
  char v171; // [rsp+428h] [rbp-58h] BYREF

  Irp = a3;
  v164 = a2;
  v166[3] = Context;
  v166[2] = a4;
  v157 = a5;
  v129 = a6;
  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  v9 = 0;
  v147 = 0;
  v166[0] = 0;
  *(_OWORD *)Buf1 = 0;
  v145 = 0;
  v120[0] = 0;
  v135 = 0;
  v128[0] = 0;
  *(_OWORD *)Buf2 = 0;
  *(_OWORD *)v156 = 0;
  *(_OWORD *)v162 = 0;
  v139 = 0;
  v163 = 0;
  memset(v168, 0, sizeof(v168));
  memset(v170, 0, sizeof(v170));
  v149 = 0;
  memset(v169, 0, sizeof(v169));
  plsn.ullOffset = CLFS_LSN_NULL_EXT;
  *(_OWORD *)Contexta = 0;
  *(_OWORD *)v124 = 0;
  *(_OWORD *)Bcb = 0;
  v126 = 0;
  v10 = *(int **)(Context[14] + 24LL);
  v131 = 10;
  if ( CurrentStackLocation->Parameters.Create.Options == 10 )
  {
    LOBYTE(v11) = *(_BYTE *)v10 != 0;
    v127 = (unsigned __int8)v11;
LABEL_7:
    v143 = v11 & 2;
    if ( (v11 & 2) != 0 && !*(_QWORD *)(a4 + 200) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 3221226140LL, 993457);
      return 3221226140LL;
    }
    Contexta[0] = Context;
    BYTE1(Bcb[1]) = 88;
    v13 = *(_QWORD *)(a5 + 184);
    Contexta[1] = (PVOID)v13;
    ByteOffset = CurrentStackLocation->Parameters.Read.ByteOffset;
    if ( !ByteOffset.QuadPart && (unsigned int)v10[4] >= 2 && *((_WORD *)v10 + 10) == 58 )
    {
      Buf1[1] = v10 + 5;
      LOWORD(Buf1[0]) = *((_WORD *)v10 + 8);
      WORD1(Buf1[0]) = Buf1[0];
      return NtfsStreamRename((int)Context, a6, v11 & 1, (__int64)Buf1);
    }
    if ( (*(_DWORD *)(a6 + 4) & 2) == 0
      || (v15 = *(_QWORD *)(a6 + 72), (v133 = v15) == 0)
      || (*(_DWORD *)(v13 + 4) & 0x100) != 0 )
    {
      v20 = -1073741811;
      if ( NtfsStatusDebugFlags )
      {
        v21 = 993512;
        goto LABEL_464;
      }
      return v20;
    }
    v16 = *(_DWORD *)(v15 + 4);
    if ( (v16 & 1) != 0
      || (*(_BYTE *)(*(_QWORD *)(v15 + 192) + 65LL) & 3) != 0 && (*(_DWORD *)(*(_QWORD *)(v15 + 48) + 4LL) & 0x20) != 0 )
    {
      if ( (Context[2] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v117 = *(_QWORD *)(a4 + 248);
        v118 = *(_WORD *)(v117 + 6);
        if ( v118 > 0x40u || (v118 & 1) != 0 )
          v118 = 0;
        v119 = *(_QWORD *)(v15 + 192);
        McTemplateU0ppwwpidpwdd_EtwWriteTransfer(
          *(unsigned __int8 *)(v119 + 65),
          v119 + 66,
          (unsigned int)KeGetCurrentThread(),
          a4,
          *(_WORD *)(a4 + 7872) >> 1,
          *(_QWORD *)(a4 + 7880),
          v118 >> 1,
          v117 + 32,
          *(_QWORD *)(v15 + 48),
          *(_QWORD *)(*(_QWORD *)(v15 + 48) + 8LL),
          *(_DWORD *)(*(_QWORD *)(v15 + 48) + 4LL),
          v133,
          *(unsigned __int8 *)(v119 + 64) >> 1,
          v119 + 66,
          *(_BYTE *)(v119 + 65),
          v16);
      }
      if ( NtfsStatusDebugFlags )
      {
        v20 = -1073741790;
        v21 = 993539;
        goto LABEL_464;
      }
      return (unsigned int)-1073741790;
    }
    v17 = *(_DWORD *)(v13 + 176);
    if ( v17 < 0 )
    {
      if ( (Context[2] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v18 = *(_QWORD *)(a4 + 248);
        v19 = *(_WORD *)(v18 + 6);
        if ( v19 > 0x40u || (v19 & 1) != 0 )
          v19 = 0;
        McTemplateU0ppwwpid_EtwWriteTransfer(
          v18 + 32,
          (unsigned int)fileinfo_c10508,
          (unsigned int)KeGetCurrentThread(),
          a4,
          *(_WORD *)(a4 + 7872) >> 1,
          *(_QWORD *)(a4 + 7880),
          v19 >> 1,
          v18 + 32,
          v13,
          *(_QWORD *)(v13 + 8),
          v17);
      }
      if ( NtfsStatusDebugFlags )
      {
        v20 = -1073741790;
        v21 = 993561;
LABEL_464:
        NtfsStatusTraceAndDebugInternal(0, v20, v21);
        return v20;
      }
      return (unsigned int)-1073741790;
    }
    if ( (*((_DWORD *)Context + 3) & 1) == 0 )
      return NtfsPostRequest(Context);
    v20 = 0;
    v121 = 0;
    v136 = 0;
    v146 = 0;
    v161 = 0;
    PoolWithTag = 0;
    v137 = 0;
    v144 = 0;
    v122 = 0;
    v130 = 0;
    v22 = v129;
    *((_DWORD *)Context + 68) = *(_DWORD *)(v129 + 100);
    *(_QWORD *)&v124[2] = *(_QWORD *)(v15 + 24);
    v168[0].m128i_i64[1] = (__int64)v168[2].m128i_i64;
    v168[1].m128i_i64[1] = (__int64)&v168[3].m128i_i64[1];
    v168[0].m128i_i32[0] = 1572864;
    v168[1].m128i_i32[0] = 3407872;
    v23 = Context[50];
    v138 = v23;
    v24 = 88;
    if ( (*(_BYTE *)(v22 + 4) & 8) == 0 )
      v24 = 89;
    BYTE1(Bcb[1]) = v24;
    v156[1] = 0;
    v162[1] = 0;
    if ( (*(_DWORD *)(v13 + 176) & 0x10000000) != 0 )
    {
      v25 = *(_QWORD *)(v13 + 328);
      if ( v25 )
      {
        v26 = *(_DWORD *)(v25 + 128);
        if ( v26 )
        {
          if ( !v23 || v26 != 1 || !(unsigned __int8)TxfSearchNoRenameList(v23) )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal(Context, 3222863927LL, 993625);
            ExRaiseStatus(-1072103369);
          }
        }
      }
      v20 = NtfsProcessTreeForRename(Context, Irp, (__int64)&plsn);
      v121 = v20;
      if ( v20 )
        goto LABEL_425;
      if ( v138 )
        _InterlockedOr((volatile signed __int32 *)(v138 + 16), 0x10000u);
      if ( !ClfsLsnNull(&plsn) )
      {
        v29 = (CLFS_LSN *)TxfSearchAddTxfFcbCleanupList(Context[18], 0, 5, 0, 1);
        v29[2].offset.idxRecord |= 0x8000u;
        v29[5] = plsn;
        v30 = *(CLFS_LSN *)((char *)Contexta[1] + 320);
        v29[4] = v30;
        _InterlockedAdd((volatile signed __int32 *)(v30.ullOffset + 64), 1u);
        _InterlockedAdd((volatile signed __int32 *)(v29[4].ullOffset + 48), 1u);
        ExRaiseStatus(-1073741608);
      }
    }
    NtfsFindTargetElements(
      (_DWORD)Context,
      ByteOffset.LowPart,
      v124[2],
      (unsigned int)&v147,
      (__int64)v166,
      (__int64)&v145,
      (__int64)Buf1);
    v9 = v147;
    if ( v147 == v157 )
    {
      v20 = -1073741811;
      if ( NtfsStatusDebugFlags )
      {
        v31 = 993710;
LABEL_423:
        NtfsStatusTraceAndDebugInternal(0, v20, v31);
        goto LABEL_424;
      }
      goto LABEL_424;
    }
    if ( LOWORD(Buf1[0]) > 0x1FEu || !(unsigned __int8)NtfsIsFileNameValid(Buf1, 0) )
    {
      v20 = -1073741773;
      if ( NtfsStatusDebugFlags )
      {
        v31 = 993721;
        goto LABEL_423;
      }
      goto LABEL_424;
    }
    v33 = *(_QWORD *)(v9 + 184);
    v34 = *(_DWORD *)(v33 + 4);
    if ( (v34 & 0x100) != 0 && v9 != *(_QWORD *)(a4 + 32) )
    {
      if ( (Context[2] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v35 = *(_QWORD *)(a4 + 248);
        v36 = *(_WORD *)(v35 + 6);
        if ( v36 > 0x40u || (v36 & 1) != 0 )
        {
          v37 = 0;
          v137 = 0;
        }
        else
        {
          v37 = *(_WORD *)(v35 + 6);
          v137 = v37;
        }
        LOWORD(v166[0]) = v37;
        v166[1] = v35 + 32;
        McTemplateU0ppwwpid_EtwWriteTransfer(
          v37 >> 1,
          (unsigned int)fileinfo_c10692,
          (unsigned int)KeGetCurrentThread(),
          a4,
          *(_WORD *)(a4 + 7872) >> 1,
          *(_QWORD *)(a4 + 7880),
          v37 >> 1,
          v35 + 32,
          v33,
          *(_QWORD *)(v33 + 8),
          v34);
      }
      v20 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_424;
      v31 = 993745;
      goto LABEL_423;
    }
    if ( *(int *)(v33 + 176) < 0
      && (*((_DWORD *)Context + 109) & 0x80008) == 0
      && (_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v33 + 320) + 132LL), 4, 4)
       || (int)TxfConvertMungedNameToTxfFileId(0, Buf1, 0, v32) < 0) )
    {
      if ( (Context[2] & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v38 = *(_QWORD *)(a4 + 248);
        v39 = *(_WORD *)(v38 + 6);
        if ( v39 > 0x40u || (v39 & 1) != 0 )
        {
          v40 = 0;
          v136 = 0;
        }
        else
        {
          v40 = *(_WORD *)(v38 + 6);
          v136 = v40;
        }
        LOWORD(v164) = v40;
        v165 = v38 + 32;
        McTemplateU0ppwwpidd_EtwWriteTransfer(
          *(_QWORD *)(v9 + 184),
          (unsigned int)fileinfo_c10729,
          (unsigned int)KeGetCurrentThread(),
          a4,
          *(_WORD *)(a4 + 7872) >> 1,
          *(_QWORD *)(a4 + 7880),
          v40 >> 1,
          v38 + 32,
          *(_QWORD *)(v9 + 184),
          *(_QWORD *)(*(_QWORD *)(v9 + 184) + 8LL),
          *(_DWORD *)(*(_QWORD *)(v9 + 184) + 176LL),
          *(_DWORD *)(*(_QWORD *)(v9 + 184) + 4LL));
      }
      v20 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_424;
      v31 = 993783;
      goto LABEL_423;
    }
    v41 = *(_QWORD *)&v124[2];
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v124[2] + 184LL) + 112LL) )
    {
      LOBYTE(v28) = 1;
      NtfsAcquirePagingResourceExclusive(Context, *(_QWORD *)(*(_QWORD *)&v124[2] + 184LL), v28);
      LOBYTE(Bcb[1]) |= 2u;
      v41 = *(_QWORD *)&v124[2];
    }
    NtfsAcquireExclusiveScbEx(Context, v41, 0);
    if ( ((__int64)Bcb[1] & 2) == 0 )
    {
      v42 = *(_QWORD *)(*(_QWORD *)&v124[2] + 184LL);
      if ( *(_QWORD *)(v42 + 112) )
      {
        NtfsReleaseFcbEx(Context, v42, 0);
        LOBYTE(v43) = 1;
        NtfsAcquirePagingResourceExclusive(Context, *(_QWORD *)(*(_QWORD *)&v124[2] + 184LL), v43);
        LOBYTE(Bcb[1]) |= 2u;
        NtfsAcquireExclusiveScbEx(Context, *(_QWORD *)&v124[2], 0);
      }
    }
    if ( !*(_WORD *)(*(_QWORD *)&v124[2] + 656LL) )
      NtfsBuildNormalizedNameWithTxfIsolation(
        (_DWORD)Context,
        *(_QWORD *)(*(_QWORD *)&v124[2] + 184LL),
        v124[2],
        0,
        0,
        0,
        *(_QWORD *)&v124[2] + 656LL);
    if ( v138 )
    {
      v20 = TxfPrepareFileForPotentialTxLinkDelete((int)Context);
      v121 = v20;
      v27 = 0;
      if ( v20 )
        goto LABEL_425;
    }
    if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 && !*(_WORD *)(v157 + 656) )
      NtfsUpdateNormalizedName((int)Context, 0);
    if ( v9 == *(_QWORD *)&v124[2] )
    {
      if ( LOWORD(Buf1[0]) == *(_WORD *)(v133 + 72) && !memcmp(Buf1[1], *(const void **)(v133 + 80), LOWORD(Buf1[0])) )
        goto LABEL_425;
      goto LABEL_94;
    }
    if ( (*((_DWORD *)Context + 3) & 0x100) != 0 )
    {
      NtfsAcquireExclusiveScbEx(Context, v9, 0);
    }
    else
    {
      v45 = 0;
      if ( !(unsigned __int8)NtfsAcquireExclusiveFcb(Context, *(_QWORD *)(v9 + 184), v9, 66) )
      {
        *((_DWORD *)Context + 3) |= 0x100u;
        NtfsRaiseStatusInternal((_DWORD)Context, -1073741608, 0, 0, 993897);
        goto LABEL_467;
      }
      if ( (*(_DWORD *)(v9 + 200) & 0x200) != 0 )
        NtfsSnapshotScb(Context, v9);
    }
    v27 = *(_QWORD *)(v9 + 184);
    if ( (*(_DWORD *)(v27 + 176) & 0x400) != 0 )
    {
      CurrentFileInfo = TxfGetCurrentFileInfo((_DWORD)Context, v27, 0, 0, 0);
      if ( !(unsigned __int8)RtlIsNonEmptyDirectoryReparsePointAllowed(CurrentFileInfo) )
      {
        v20 = -1073741183;
        if ( NtfsStatusDebugFlags )
        {
          v31 = 993935;
          goto LABEL_423;
        }
LABEL_424:
        v121 = v20;
        goto LABEL_425;
      }
    }
    if ( !*(_WORD *)(*(_QWORD *)(v9 + 184) + 188LL) )
    {
      v20 = -1073741738;
      if ( NtfsStatusDebugFlags )
      {
        v31 = 993948;
        goto LABEL_423;
      }
      goto LABEL_424;
    }
    BYTE2(Bcb[1]) |= 2u;
    v45 = v9 + 656;
    if ( *(_WORD *)(v9 + 656) )
      goto LABEL_119;
    if ( (*((_DWORD *)Context + 3) & 0x100) != 0
      || (Context[2] & 0x40000000) != 0
      || (*(_DWORD *)(Context[18] + 16LL) & 0x40000000) != 0
      || ExIsResourceAcquiredExclusiveLite((PERESOURCE)(a4 + 2160)) )
    {
      NtfsBuildNormalizedNameWithTxfIsolation((_DWORD)Context, *(_QWORD *)(v9 + 184), v9, 0, 0, 0, v9 + 656);
LABEL_119:
      v48 = *(unsigned int *)(v166[0] + 4LL);
      if ( (v48 & 8) != 0 && (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 )
      {
        v49 = v157;
        if ( (*((_DWORD *)Context + 3) & 0x100) != 0 )
        {
          NextScb = v157;
          do
          {
            NextScb = NtfsGetNextScb(v48, NextScb, v49, 0);
            if ( !NextScb )
              goto LABEL_94;
          }
          while ( NextScb != v9 );
          if ( (!Context || (Context[2] & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
          {
            v54 = *(_QWORD *)(a4 + 248);
            v55 = *(unsigned __int16 *)(v54 + 6);
            if ( (unsigned __int16)v55 > 0x40u || (v55 & 1) != 0 )
              v55 = 0;
            v143 = v55;
            LOWORD(Irp) = v55;
            v155 = v54 + 32;
            McTemplateU0ppwwpii_EtwWriteTransfer(
              (unsigned __int16)v55 >> 1,
              *(_QWORD *)(v49 + 184),
              (unsigned int)KeGetCurrentThread(),
              a4,
              *(_WORD *)(a4 + 7872) >> 1,
              *(_QWORD *)(a4 + 7880),
              (unsigned __int16)v55 >> 1,
              v54 + 32,
              *(_QWORD *)(v49 + 184),
              *(_QWORD *)(*(_QWORD *)(v49 + 184) + 8LL),
              *(_QWORD *)(*(_QWORD *)(v9 + 184) + 8LL));
          }
          v20 = -1073741790;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_424;
          v31 = 994045;
          goto LABEL_423;
        }
        if ( (unsigned __int8)NtfsHasSubdirectory(v48, v157) )
        {
          if ( (Context[2] & 0x100000) == 0
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
          {
            v50 = *(_QWORD *)(a4 + 248);
            v51 = *(_WORD *)(v50 + 6);
            if ( v51 > 0x40u || (v51 & 1) != 0 )
            {
              v52 = 0;
              v127 = 0;
            }
            else
            {
              v52 = *(_WORD *)(v50 + 6);
              v127 = v52;
            }
            LOWORD(v157) = v52;
            v158 = v50 + 32;
            McTemplateU0ppwwpi_EtwWriteTransfer(
              *(_QWORD *)(v49 + 184),
              (unsigned int)fileinfo_c10972,
              (unsigned int)KeGetCurrentThread(),
              a4,
              *(_WORD *)(a4 + 7872) >> 1,
              *(_QWORD *)(a4 + 7880),
              v52 >> 1,
              v50 + 32,
              *(_QWORD *)(v49 + 184),
              *(_QWORD *)(*(_QWORD *)(v49 + 184) + 8LL));
          }
          v20 = -1073741790;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_424;
          v31 = 994024;
          goto LABEL_423;
        }
      }
LABEL_94:
      v44 = v133;
      v45 = v129;
      if ( (*(_BYTE *)(*(_QWORD *)(v133 + 192) + 65LL) & 3) != 0 && (*(_DWORD *)(v129 + 4) & 1) != 0 )
        BYTE2(Bcb[1]) |= 4u;
      v46 = *(_DWORD *)(v129 + 4);
      LOBYTE(v28) = (v46 & 1) != 0
                 && ((v46 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
      v56 = NtfsLookupEntry(
              (_DWORD)Context,
              v9,
              v28,
              (unsigned int)Buf1,
              (__int64)&v135,
              (__int64)v128,
              0,
              (__int64)&v139,
              (__int64)Bcb,
              0);
      v57 = (__int64)Bcb[1] & 0xDF | (32 * (v56 & 1));
      LOBYTE(Bcb[1]) = v57;
      if ( *((_DWORD *)Context + 7) )
      {
        NtfsCheckpointCurrentTransaction(Context);
        NtfsReleaseSharedResources(Context);
        NtfsReleaseExclusiveScbIfOwned(Context, *(_QWORD *)(a4 + 48));
        v57 = (char)Bcb[1];
      }
      if ( v138 )
      {
        v58 = *(_QWORD *)(v9 + 184);
        if ( *((_QWORD *)Contexta[1] + 40) != *(_QWORD *)(v58 + 320) )
        {
          if ( (v57 & 0x20) != 0 )
          {
            v131 = (int)Bcb[1];
            BYTE1(v131) = BYTE1(Bcb[1]) | 0x20;
            v59 = *(_DWORD *)(v45 + 4);
            if ( (v59 & 1) != 0 && ((v59 & 0x4000000) != 0 || (*(_DWORD *)(v58 + 16) & 0x400) == 0) )
            {
              v60 = 1;
              v45 = 0;
            }
            else
            {
              v45 = 0;
              v60 = 0;
            }
            NtfsCheckLinkForRename(Contexta[1], v44, v139 + 16, *(_QWORD *)v139, (__int64)Buf1, v60, (__int64)&v131);
            if ( (v131 & 0x2000) != 0 && (v131 & 0x200) == 0 && (v127 & 1) == 0 )
            {
              v20 = -1073741771;
              if ( NtfsStatusDebugFlags )
              {
                v31 = 994201;
                goto LABEL_423;
              }
              goto LABEL_424;
            }
          }
          goto LABEL_468;
        }
      }
      v20 = TxfCheckTargetForRename(Context, Buf1, v9);
      v121 = v20;
      if ( v20 )
        goto LABEL_425;
      v28 = v138;
      if ( v138 )
      {
        v61 = *(_QWORD *)(v9 + 184);
        v62 = *(_DWORD *)(v61 + 8);
        if ( v62 != 5 && *(_DWORD *)(*(_QWORD *)(v61 + 320) + 88LL) != v62 )
        {
          v63 = *(_QWORD *)(v61 + 328);
          if ( !v63 || *(_QWORD *)(v63 + 24) != v138 && !(unsigned __int8)TxfSearchNoRenameList(v138) )
          {
            TxfPrepareFileForTxfLogging((int)Context, 0, 0, 1, (*((_DWORD *)Context + 3) & 0x100) == 0);
            v139 = 0;
            if ( Bcb[0] )
            {
              CcUnpinData(Bcb[0]);
              Bcb[0] = 0;
            }
            v65 = *(_DWORD *)(v45 + 4);
            LOBYTE(v64) = (v65 & 1) != 0
                       && ((v65 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
            v66 = NtfsLookupEntry(
                    (_DWORD)Context,
                    v9,
                    v64,
                    (unsigned int)Buf1,
                    (__int64)&v135,
                    (__int64)v128,
                    0,
                    (__int64)&v139,
                    (__int64)Bcb,
                    0);
            LOBYTE(Bcb[1]) = (__int64)Bcb[1] & 0xDF | (32 * (v66 & 1));
            if ( *((_DWORD *)Context + 7) )
            {
              NtfsCheckpointCurrentTransaction(Context);
              NtfsReleaseSharedResources(Context);
              NtfsReleaseExclusiveScbIfOwned(Context, *(_QWORD *)(a4 + 48));
            }
          }
        }
      }
      if ( ((__int64)Bcb[1] & 0x20) != 0 )
      {
        BYTE1(Bcb[1]) |= 0x20u;
        v67 = v139;
        v68 = *(_DWORD *)(v129 + 4);
        v69 = (v68 & 1) != 0 && ((v68 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
        v70 = NtfsCheckLinkForRename(
                Contexta[1],
                v133,
                (int)v139 + 16,
                *(_QWORD *)v139,
                (__int64)Buf1,
                v69,
                (__int64)&Bcb[1]);
        v120[0] = *(_BYTE *)(v67 + 81);
        LOBYTE(v70) = v120[0];
        v131 = v70;
        v141 = v120[0];
        v71 = v127;
        if ( (BYTE1(Bcb[1]) & 0x20) != 0 && (BYTE1(Bcb[1]) & 2) == 0 && (v127 & 1) == 0 )
        {
          v20 = -1073741771;
          if ( NtfsStatusDebugFlags )
          {
            v31 = 994370;
            goto LABEL_423;
          }
          goto LABEL_424;
        }
      }
      else
      {
        v71 = v127;
      }
      if ( (BYTE1(Bcb[1]) & 0x40) != 0 )
        NtfsCheckIndexForAddOrDelete(
          (_DWORD)Context,
          (_DWORD)Irp,
          *(_QWORD *)(v9 + 184),
          (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 ? 4 : 2,
          v129);
      if ( (BYTE2(Bcb[1]) & 2) != 0
        && *(_BYTE *)(*(_QWORD *)(v9 + 184) + 38LL) != *((_BYTE *)Contexta[1] + 38)
        && (v71 & 8) == 0 )
      {
        v45 = a4 + 10688;
        ExAcquireResourceExclusiveLite((PERESOURCE)(a4 + 10688), 1u);
        v72 = BYTE2(Bcb[1]) | 0x40;
        BYTE2(Bcb[1]) |= 0x40u;
        v73 = *((unsigned __int8 *)Contexta[1] + 38);
        if ( !(_BYTE)v73
          || (v74 = *(_QWORD *)(a4 + 8 * v73 + 10904)) == 0
          || (v75 = *(_DWORD *)(v74 + 4), (v75 & 4) == 0) && ((v75 & 0x10) == 0 || *((_WORD *)Contexta[1] + 94) == 1) )
        {
          v76 = *(unsigned __int8 *)(*(_QWORD *)(v9 + 184) + 38LL);
          if ( !(_BYTE)v76
            || (v77 = *(_QWORD *)(a4 + 8 * v76 + 10904)) == 0
            || (v78 = *(_DWORD *)(v77 + 4), (v78 & 8) == 0) && ((v78 & 0x20) == 0 || *((_WORD *)Contexta[1] + 94) == 1) )
          {
            BYTE2(Bcb[1]) = v72 | 0x80;
            v79 = v130;
            if ( (v127 & 0x10) != 0 )
              v79 = 1;
            v130 = v79;
            v142 = v79;
            if ( (v127 & 0x20) != 0 )
            {
              v79 |= 2u;
              v130 = v79;
              v142 = v79;
            }
            if ( (v127 & 0x80u) != 0 )
            {
              v79 |= 4u;
              v130 = v79;
              v142 = v79;
            }
            if ( (v127 & 0x100) != 0 )
            {
              v79 |= 8u;
              v130 = v79;
              v142 = v79;
            }
            if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 )
            {
              if ( !*(_BYTE *)(*(_QWORD *)(v9 + 184) + 38LL) )
              {
                v20 = NtfsChangeStorageReserveId((_DWORD)Context, 0, v79);
                v121 = v20;
                if ( v20 )
                  goto LABEL_425;
LABEL_471:
                ExReleaseResourceLite((PERESOURCE)v45);
                BYTE2(Bcb[1]) &= ~0x40u;
                NtfsCheckpointCurrentTransaction(Context);
                *((_DWORD *)Context + 92) = *(unsigned __int8 *)(*(_QWORD *)(v9 + 184) + 38LL);
                *((_DWORD *)Context + 93) = v130;
                *((_DWORD *)Context + 3) |= 4u;
                NtfsRaiseStatusInternal((_DWORD)Context, -1073741608, 0, 0, 994500);
                __debugbreak();
                JUMPOUT(0x14024F784LL);
              }
              BYTE3(Bcb[1]) |= 1u;
            }
          }
        }
        ExReleaseResourceLite((PERESOURCE)(a4 + 10688));
        BYTE2(Bcb[1]) &= ~0x40u;
      }
      if ( (*(_BYTE *)(*(_QWORD *)(v133 + 192) + 65LL) & 3) == 2 )
      {
        memset(v167, 0, 0x58u);
        Src = 0;
        NtfsLookupPrimaryLink((int)Context, (int)Contexta[1], (__int64)v167);
        v80 = (unsigned __int8 *)Src;
        PoolWithTag = ExAllocatePoolWithTag(
                        (POOL_TYPE)(PoolType | 0x10),
                        2LL * *((unsigned __int8 *)Src + 64) + 66,
                        0x4646744Eu);
        memmove(PoolWithTag, v80, 2LL * v80[64] + 66);
        NtfsCleanupAttributeContext(v81, v167);
      }
      if ( ((__int64)Bcb[1] & 0x20) != 0 && (BYTE1(Bcb[1]) & 0x20) != 0 )
      {
        Src = (void *)(v139 + 16);
        v27 = *(unsigned __int16 *)(v9 + 656) + 2 + 2 * (unsigned int)*(unsigned __int8 *)(v139 + 80);
        if ( (unsigned int)v27 > 0xFFFE )
        {
          v20 = -1073741562;
          if ( NtfsStatusDebugFlags )
          {
            v31 = 994605;
            goto LABEL_423;
          }
          goto LABEL_424;
        }
        WORD1(v156[0]) = *(_WORD *)(v9 + 656) + 2 + 2 * *(unsigned __int8 *)(v139 + 80);
        v82 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v27, 0x4646744Eu);
        v156[1] = v82;
        memmove(v82, *(const void **)(v9 + 664), *(unsigned __int16 *)(v9 + 656));
        v83 = &v82[*(unsigned __int16 *)(v9 + 656)];
        v147 = (__int64)v83;
        if ( v9 == *(_QWORD *)(a4 + 32) )
        {
          v84 = v83;
        }
        else
        {
          *(_WORD *)v83 = 92;
          v84 = v83 + 2;
          v83 = v84;
          v147 = (__int64)v84;
        }
        memmove(v84, (char *)Src + 66, 2LL * *((unsigned __int8 *)Src + 64));
        Buf2[1] = v83;
        LOWORD(Buf2[0]) = 2 * *((unsigned __int8 *)Src + 64);
        WORD1(Buf2[0]) = Buf2[0];
        LOWORD(v156[0]) = LOWORD(Buf2[0]) + (_WORD)v83 - LOWORD(v156[1]);
        if ( (BYTE1(Bcb[1]) & 2) != 0 )
        {
          *(PVOID *)v124 = Contexta[1];
          if ( v138 )
          {
            LOBYTE(v128[0]) = 1;
            v148 = 14;
            v85 = *(_DWORD *)(v129 + 4);
            if ( (v85 & 1) != 0 && ((v85 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0) )
              v148 = 15;
            Src = (void *)NtfsCreateLcb(
                            (_DWORD)Context,
                            v9,
                            Contexta[1],
                            (unsigned int)Buf2,
                            *((_BYTE *)Src + 65),
                            (__int64)v128);
            v20 = TxfPrepareFileForPotentialTxLinkDelete((int)Context);
            v121 = v20;
            if ( (v20 & 0x80000000) != 0 )
            {
              if ( NtfsStatusDebugFlags
                && v20 < 0xFFFFFFED
                && v20 != -1073741802
                && v20 + 2147483643 > 1
                && v20 != -1073741807
                && v20 != -1073741608 )
              {
                NtfsStatusTraceAndDebugInternal(Context, v20, 994717);
              }
              ExRaiseStatus(v20);
            }
            if ( (BYTE1(Bcb[1]) & 8) != 0 )
            {
              TxfDeleteFile((int)Context, (int)Contexta[1], (__int64)&Bcb[1] + 6, 0, 0);
            }
            else
            {
              v144 = (__m128i *)v169;
              *((_QWORD *)&v169[0] + 1) = &v169[2];
              *((_QWORD *)&v169[1] + 1) = (char *)&v169[3] + 8;
              LODWORD(v169[0]) = 1572864;
              LODWORD(v169[1]) = 3407872;
              v122 = *(_BYTE *)(*((_QWORD *)Src + 24) + 65LL);
              v132 = v122;
              TxfRemoveLink((int)Context, (int)Contexta[1], 0);
            }
          }
          else
          {
            NtfsRemoveLink((int)Context, (int)Contexta[1], 0, 0);
            ++WORD2(Bcb[1]);
          }
        }
        else
        {
          v20 = NtfsRemoveSupersededTarget(
                  (int)Context,
                  (__int64)Src,
                  Contexta[1],
                  Irp,
                  v129,
                  v143 != 0,
                  (v127 & 0x40) != 0,
                  (__int64)Buf2,
                  (__int64)Contexta);
          v121 = v20;
          if ( v20 )
            goto LABEL_425;
        }
      }
      if ( Bcb[0] )
      {
        CcUnpinData(Bcb[0]);
        Bcb[0] = 0;
      }
      if ( (BYTE1(Bcb[1]) & 0x10) != 0 )
      {
        if ( (BYTE1(Bcb[1]) & 8) != 0 )
        {
          LOBYTE(v170[9]) = 0;
          if ( v138 )
          {
            v160 = 14;
            v86 = *(_DWORD *)(v129 + 4);
            if ( (v86 & 1) != 0 && ((v86 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0) )
              v160 = 15;
            if ( (BYTE1(Bcb[1]) & 0x40) != 0 )
            {
              v144 = v168;
              v122 = *(_BYTE *)(*(_QWORD *)(v133 + 192) + 65LL);
              v132 = v122;
              TxfRemoveLink((int)Context, (int)Contexta[1], 0);
            }
            else
            {
              if ( *(int *)(a4 + 4) < 0 || (v87 = v170, (*(_DWORD *)(v164 + 80) & 0x20000) != 0) )
                v87 = 0;
              TxfDeleteFile((int)Context, (int)Contexta[1], (__int64)&Bcb[1] + 6, (__int64)v168, (__int64)v87);
            }
          }
          else
          {
            if ( *(int *)(a4 + 4) < 0 || (v88 = v170, (*(_DWORD *)(v164 + 80) & 0x20000) != 0) )
              v88 = 0;
            NtfsRemoveLink((int)Context, (int)Contexta[1], (__int64)v168, (__int64)v88);
            ++WORD2(Bcb[1]);
          }
          v89 = v129;
          v28 = *(unsigned int *)(v129 + 4);
          if ( (v28 & 8) == 0
            && (*((_DWORD *)Contexta[1] + 44) & 0x10000000) == 0
            && *(int *)(a4 + 4) >= 0
            && (*(_DWORD *)(v164 + 80) & 0x20000) == 0 )
          {
            v90 = *(_BYTE *)(*(_QWORD *)(v133 + 192) + 65LL);
            v170[0] = *((_QWORD *)Contexta[1] + 16);
            BYTE1(v170[9]) = (v90 & 2) != 0;
            if ( (v28 & 0x4000000) != 0
              || (v91 = 1, (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v124[2] + 184LL) + 16LL) & 0x400) == 0) )
            {
              v91 = 0;
            }
            FsRtlAddToTunnelCacheEx(
              a4 + 4720,
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v124[2] + 184LL) + 8LL),
              v168,
              &v168[1],
              (2 * BYTE1(v170[9])) | v91,
              80,
              v170);
          }
        }
        else
        {
          v89 = v129;
        }
        if ( (BYTE1(Bcb[1]) & 1) != 0 )
        {
          v162[1] = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), *(unsigned __int16 *)(v89 + 16), 0x4646744Eu);
          memmove(v162[1], *(const void **)(v89 + 24), *(unsigned __int16 *)(v89 + 16));
          LOWORD(v162[0]) = *(_WORD *)(v89 + 16);
          WORD1(v162[0]) = v162[0];
          v137 = *(unsigned __int16 *)(v89 + 32);
        }
      }
      if ( (BYTE1(Bcb[1]) & 0x40) == 0 )
      {
LABEL_354:
        if ( SBYTE2(Bcb[1]) >= 0 )
        {
          v107 = 0;
LABEL_358:
          if ( (*((_DWORD *)Contexta[1] + 1) & 0x10) != 0 )
            NtfsUpdateStandardInformation((_DWORD)Context, Contexta[1]);
          if ( (BYTE1(Bcb[1]) & 2) != 0 )
          {
            if ( (BYTE1(Bcb[1]) & 0x20) != 0 )
              BYTE1(Bcb[1]) |= 0x80u;
            else
              BYTE2(Bcb[1]) |= 1u;
          }
          if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 && (BYTE1(Bcb[1]) & 0x40) != 0 )
            NtfsUpdateNormalizedName((int)Context, 1);
          if ( v166[0] && (*(_DWORD *)(v166[0] + 4LL) & 8) != 0 )
          {
            v27 = *(unsigned __int16 *)(v9 + 656) + (unsigned int)LOWORD(Buf1[0]) + 2;
            if ( (unsigned int)v27 > 0xFFFE )
            {
              v20 = -1073741562;
              if ( NtfsStatusDebugFlags )
              {
                v31 = 995380;
                goto LABEL_423;
              }
              goto LABEL_424;
            }
            v108 = *(_WORD *)(v9 + 656) + LOWORD(Buf1[0]) + 2;
            LOWORD(v145) = v108;
            WORD1(v145) = v27;
            v146 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v27, 0x4646744Eu);
            *((_QWORD *)&v145 + 1) = v146;
            v161 = v146;
            memmove(v146, *(const void **)(v9 + 664), *(unsigned __int16 *)(v9 + 656));
            v109 = *(unsigned __int16 *)(v9 + 656);
            v110 = (char *)v146 + v109;
            v147 = (__int64)v146 + v109;
            if ( (_WORD)v109 == 2 )
            {
              LOWORD(v145) = v108 - 2;
            }
            else
            {
              *v110++ = 92;
              v147 = (__int64)v110;
            }
            memmove(v110, Buf1[1], LOWORD(Buf1[0]));
            v107 = 0;
          }
          v111 = v135;
          v112 = *((_BYTE *)v135 + 65) & 3;
          if ( (BYTE2(Bcb[1]) & 2) != 0 )
          {
            if ( v112 == 2 )
              v111 = 0;
            NtfsMoveLinkToNewDir(
              (int)Context,
              v9,
              (int)Contexta[1],
              v136,
              v133,
              (char)Bcb[1],
              (__int64)Buf2,
              v131,
              (__int64)PoolWithTag,
              (__int64)v111);
            FsRtlCheckOplockEx((POPLOCK)(v9 + 88), Irp, 0x10u, 0, 0, 0);
          }
          else
          {
            if ( v112 == 2 )
              v111 = 0;
            NtfsRenameLinkInDir(
              (int)Context,
              v133,
              (__int64)Buf1,
              v120[0],
              (char)Bcb[1],
              (__int64)Buf2,
              v131,
              (__int64)PoolWithTag,
              (__int64)v111);
          }
          LOBYTE(v126) = 1;
          *((_DWORD *)Context + 3) |= 0x2000000u;
          FsRtlCheckOplockEx((POPLOCK)(*(_QWORD *)&v124[2] + 88LL), Irp, 0x10u, 0, 0, 0);
          v113 = Contexta[1];
          if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 && (BYTE1(Bcb[1]) & 0x40) != 0 )
          {
            NtfsUpdateNormalizedName((int)Context, 0);
            v113 = Contexta[1];
          }
          if ( (BYTE1(Bcb[1]) & 0x10) != 0 )
          {
            NtfsUpdateFcbTimestamps(*(_QWORD *)(*(_QWORD *)&v124[2] + 184LL), 2684354576LL);
            v113 = Contexta[1];
          }
          NtfsUpdateFileTimestampsForChange(v113, v129, ~(v113[44] >> 6) & 0x400000);
          v114 = BYTE1(Bcb[1]);
          if ( (BYTE1(Bcb[1]) & 1) == 0 )
            goto LABEL_420;
          v115 = 0;
          v150 = 0;
          v151 = 0;
          if ( v156[1] && (BYTE1(Bcb[1]) & 0x20) != 0 )
          {
            if ( (BYTE2(Bcb[1]) & 8) == 0 && (BYTE1(Bcb[1]) & 4) == 0 )
              goto LABEL_396;
            if ( (BYTE1(Bcb[1]) & 0x40) != 0 )
            {
              if ( (BYTE1(Bcb[1]) & 0x10) == 0 )
                goto LABEL_402;
              if ( (BYTE2(Bcb[1]) & 0x20) == 0 )
              {
LABEL_396:
                NtfsReportDirNotify(
                  (_DWORD)Context,
                  v9,
                  a4,
                  (unsigned int)v156,
                  LOWORD(v156[0]) - LOWORD(Buf2[0]),
                  0,
                  ((*(_DWORD *)(*(_QWORD *)v124 + 176LL) & 0x10000000) != 0) + 1,
                  2,
                  *(_QWORD *)(v9 + 184),
                  *(__int64 *)v124);
                v114 = BYTE1(Bcb[1]);
              }
            }
          }
          if ( (v114 & 0x10) != 0 )
          {
            if ( (BYTE2(Bcb[1]) & 2) != 0 || (v116 = 4, (v114 & 0x40) == 0) )
              v116 = 2;
            NtfsReportDirNotify(
              (_DWORD)Context,
              v124[2],
              a4,
              (unsigned int)v162,
              (unsigned __int16)v137,
              0,
              ((*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0) + 1,
              v116,
              *(_QWORD *)(*(_QWORD *)&v124[2] + 184LL),
              (__int64)Contexta[1]);
            v114 = BYTE1(Bcb[1]);
          }
LABEL_402:
          if ( ((__int64)Bcb[1] & 0x20) == 0
            || (BYTE2(Bcb[1]) & 8) != 0 && (v114 & 4) == 0
            || (v114 & 0x20) != 0 && ((v114 & 4) == 0 || (v114 & 0x40) != 0 && (v114 & 0x10) != 0) )
          {
            v115 = ((*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0) + 1;
            v107 = (2 * (~BYTE2(Bcb[1]) & 2)) | 1;
            v27 = 0;
          }
          else
          {
            v27 = 0;
            if ( (v114 & 0x20) == 0 || (v114 & 2) != 0 )
              goto LABEL_414;
            v115 = 508;
            v107 = 3;
          }
          v151 = v107;
          v150 = v115;
LABEL_414:
          if ( v115 )
          {
            NtfsReportDirNotify(
              (_DWORD)Context,
              v9,
              a4,
              (unsigned int)&v145,
              (unsigned __int16)v145 - LOWORD(Buf1[0]),
              0,
              v115,
              v107,
              *(_QWORD *)(v9 + 184),
              (__int64)Contexta[1]);
            v27 = 0;
          }
          if ( HIBYTE(Bcb[1]) )
          {
            v27 = 4;
            if ( (v115 & 4) == 0 || v107 != 3 )
              NtfsReportDirNotify(
                (_DWORD)Context,
                v9,
                a4,
                (unsigned int)&v145,
                (unsigned __int16)v145 - LOWORD(Buf1[0]),
                0,
                4,
                3,
                *(_QWORD *)(v9 + 184),
                (__int64)Contexta[1]);
          }
LABEL_420:
          *((_WORD *)Contexta[1] + 95) -= WORD2(Bcb[1]);
          *((_WORD *)Contexta[1] + 94) -= WORD2(Bcb[1]);
          goto LABEL_425;
        }
        v20 = NtfsChangeStorageReserveId((_DWORD)Context, *(unsigned __int8 *)(*(_QWORD *)(v9 + 184) + 38LL), v130);
        v121 = v20;
        v107 = 0;
        if ( !v20 )
          goto LABEL_358;
LABEL_425:
        NtfsRenameCleanup(Contexta, v27, v28);
        if ( PoolWithTag )
          ExFreePoolWithTag(PoolWithTag, 0);
        if ( v146 )
          ExFreePoolWithTag(v146, 0);
        if ( v156[1] )
          ExFreePoolWithTag(v156[1], 0);
        if ( v162[1] )
          ExFreePoolWithTag(v162[1], 0);
        if ( v135 )
          ExFreePoolWithTag(v135, 0);
        if ( (unsigned __int64 *)v168[1].m128i_i64[1] != &v168[3].m128i_u64[1] )
          ExFreePoolWithTag((PVOID)v168[1].m128i_i64[1], 0);
        if ( v144 == (__m128i *)v169 && *((_OWORD **)&v169[1] + 1) != (_OWORD *)((char *)&v169[3] + 8) )
          ExFreePoolWithTag(*((PVOID *)&v169[1] + 1), 0);
        if ( SLOBYTE(Bcb[1]) < 0 )
        {
          ExAcquirePushLockSharedEx(a4 + 656, 0);
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v124 + 28LL));
          ExReleasePushLockEx(a4 + 656, 0);
        }
        if ( HIBYTE(Bcb[1]) && !(_BYTE)v126 )
          *((_DWORD *)Contexta[1] + 44) = HIDWORD(v126);
        if ( v20 != 259 && ((__int64)Bcb[1] & 8) != 0 )
          NtfsTeardownStructures((int)Context, v124[0], 0);
        if ( (BYTE3(Bcb[1]) & 1) != 0 && (v20 & 0x80000000) == 0 && v20 != 259 && v20 != 871 )
        {
          *((_DWORD *)Context + 92) = *(unsigned __int8 *)(*(_QWORD *)(v9 + 184) + 38LL);
          *((_DWORD *)Context + 93) = v130;
          *((_DWORD *)Context + 3) |= 4u;
        }
        return v20;
      }
      if ( (BYTE2(Bcb[1]) & 2) == 0 || (v127 & 4) != 0 )
      {
        if ( (BYTE2(Bcb[1]) & 2) == 0 )
        {
          HIDWORD(v126) = *((_DWORD *)Contexta[1] + 44);
          if ( (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 176LL) & 0x180000) != 0x180000
            && (*((_DWORD *)Contexta[1] + 44) & 0x180000) == 0x180000 )
          {
            *((_DWORD *)Contexta[1] + 44) &= 0xFFE7FFFF;
LABEL_295:
            HIBYTE(Bcb[1]) = 1;
          }
        }
      }
      else
      {
        HIDWORD(v126) = *((_DWORD *)Contexta[1] + 44);
        v92 = *((_DWORD *)Contexta[1] + 44);
        if ( (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 176LL) & 0x180000) == 0x180000 )
        {
          *((_DWORD *)Contexta[1] + 44) = v92 | 0x180000;
        }
        else
        {
          if ( (v92 & 0x180000) == 0x180000 )
            *((_DWORD *)Contexta[1] + 44) = v92 & 0xFFE7FFFF;
          v93 = *((_DWORD *)Contexta[1] + 44);
          if ( (v93 & 0x180000) == 0
            && ((v93 & 0x10000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 176LL) & 0x180000) != 0x100000) )
          {
            *((_DWORD *)Contexta[1] + 44) = v93 | *(_DWORD *)(*(_QWORD *)(v9 + 184) + 176LL) & 0x180000;
          }
        }
        if ( *((_DWORD *)Contexta[1] + 44) != HIDWORD(v126) )
          goto LABEL_295;
      }
      if ( HIBYTE(Bcb[1]) )
      {
        v136 = 0x8000;
        *((_DWORD *)Contexta[1] + 1) |= 0x10u;
      }
      if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) == 0
        && *(int *)(a4 + 4) >= 0
        && (*(_DWORD *)(v164 + 80) & 0x20000) == 0 )
      {
        if ( v144 == v168 )
        {
          v169[0] = v168[0];
          v169[1] = v168[1];
          v169[2] = v168[2];
          v169[3] = v168[3];
          v169[4] = v168[4];
          v169[5] = v168[5];
          v169[6] = v168[6];
          v94 = (__m128i *)((char *)&v169[3] + 8);
          v95 = (__m128i *)_mm_srli_si128(v168[1], 8).m128i_u64[0];
          if ( v95 != (__m128i *)&v168[3].m128i_u64[1] )
            v94 = v95;
          *((_QWORD *)&v169[1] + 1) = v94;
          v96 = (__m128i *)&v169[2];
          v97 = (__m128i *)_mm_srli_si128(v168[0], 8).m128i_u64[0];
          if ( v97 != &v168[2] )
            v96 = v97;
          *((_QWORD *)&v169[0] + 1) = v96;
          v144 = (__m128i *)v169;
        }
        else if ( (unsigned __int64 *)v168[1].m128i_i64[1] != &v168[3].m128i_u64[1] )
        {
          ExFreePoolWithTag((PVOID)v168[1].m128i_i64[1], 0);
        }
        v168[0].m128i_i64[1] = (__int64)v168[2].m128i_i64;
        v168[1].m128i_i64[1] = (__int64)&v168[3].m128i_i64[1];
        v168[1].m128i_i32[0] = 3407872;
        v168[0].m128i_i32[0] = 1572864;
        v149 = 80;
        if ( (unsigned __int8)FsRtlFindInTunnelCacheEx(
                                a4 + 4720,
                                *(_QWORD *)(*(_QWORD *)(v9 + 184) + 8LL),
                                Buf1,
                                v168,
                                &v168[1]) )
        {
          LOBYTE(Bcb[1]) |= 0x40u;
          if ( ((__int64)Bcb[1] & 1) == 0 )
          {
            if ( LOBYTE(v170[9]) )
            {
              NtfsAcquireExclusiveScbEx(Context, *(_QWORD *)(a4 + 160), 0);
              LOBYTE(Bcb[1]) |= 1u;
            }
          }
        }
      }
      if ( v138 )
      {
        LODWORD(v163) = 1572864;
        *((_QWORD *)&v163 + 1) = &v171;
      }
      NtfsAddLink(
        (_DWORD)Context,
        Contexta[1],
        (__int64)v135,
        0,
        (__int64)v120,
        0,
        (unsigned __int64)&v163 & -(__int64)(v138 != 0),
        (unsigned __int64)v168 & -(__int64)(((__int64)Bcb[1] & 0x40) != 0),
        0);
      if ( ((__int64)Bcb[1] & 0x20) != 0
        && (v98 = BYTE1(Bcb[1]), v28 = 2, (BYTE1(Bcb[1]) & 2) != 0)
        && (BYTE1(Bcb[1]) & 4) != 0
        && ((__int64)Bcb[1] & 0x40) != 0
        && (*(_BYTE *)(*(_QWORD *)(v133 + 192) + 65LL) & 3) != 0
        && (v131 & 3) == 0 )
      {
        v99 = v120[0];
        if ( v120[0] == 2 && v168[0].m128i_i16[0] == LOWORD(Buf2[0]) )
        {
          v100 = memcmp((const void *)v168[0].m128i_i64[1], Buf2[1], v168[0].m128i_u16[0]);
          v101 = 0;
          if ( v100 )
            BYTE1(Bcb[1]) = v98 & 0xFB;
          v99 = v120[0];
          goto LABEL_328;
        }
      }
      else
      {
        v99 = v120[0];
      }
      v101 = 0;
LABEL_328:
      v102 = v129;
      if ( v138 )
      {
        v103 = *(_DWORD *)(v129 + 4);
        if ( v144 )
        {
          v105 = (v103 & 1) != 0
              && ((v103 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
          TxfAddLinkForRename(
            (_DWORD)Context,
            v122,
            v99,
            (__int64)v144,
            (__int64)v168,
            (__int64)&v163,
            v105,
            Contexta[1]);
        }
        else
        {
          v104 = (v103 & 1) != 0
              && ((v103 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
          TxfAddHardLink((_DWORD)Context, (__int64)v168, (__int64)&v163, v104, Contexta[1]);
        }
      }
      if ( ((__int64)Bcb[1] & 0x40) != 0 )
      {
        NtfsSetTunneledData(Context, Contexta[1], v170, v101);
        *((_DWORD *)Contexta[1] + 46) |= 0x40u;
        *((_DWORD *)Contexta[1] + 1) |= 0x10u;
        if ( v120[0] == 2 )
          memmove(Buf1[1], (const void *)v168[0].m128i_i64[1], LOWORD(Buf1[0]));
      }
      *((_BYTE *)v135 + 65) = v120[0];
      if ( *(_QWORD *)&v124[2] != v9 )
        NtfsUpdateFcbTimestamps(*(_QWORD *)(v9 + 184), 2684354576LL);
      if ( (BYTE1(Bcb[1]) & 1) != 0 && !*((_QWORD *)&v145 + 1) )
      {
        v27 = LOWORD(Buf1[0]) + (unsigned int)*(unsigned __int16 *)(v102 + 32);
        if ( (unsigned int)v27 > 0xFFFE )
        {
          v20 = -1073741562;
          if ( NtfsStatusDebugFlags )
          {
            v31 = 995252;
            goto LABEL_423;
          }
          goto LABEL_424;
        }
        v106 = LOWORD(Buf1[0]) + *(_WORD *)(v102 + 32);
        WORD1(v145) = v27;
        v146 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v27, 0x4646744Eu);
        v161 = v146;
        memmove(v146, *(const void **)(v129 + 24), *(unsigned __int16 *)(v129 + 32));
        memmove((char *)v146 + *(unsigned __int16 *)(v129 + 32), Buf1[1], LOWORD(Buf1[0]));
        *((_QWORD *)&v145 + 1) = v146;
        LOWORD(v145) = v106;
      }
      --WORD2(Bcb[1]);
      goto LABEL_354;
    }
LABEL_467:
    *((_DWORD *)Context + 3) |= 0x100u;
    NtfsRaiseStatusInternal((_DWORD)Context, -1073741608, 0, 0, 993973);
LABEL_468:
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(Context, 3222863928LL, 994213);
    NtfsRaiseStatusInternal((_DWORD)Context, -1072103368, 0, 0, 994213);
    goto LABEL_471;
  }
  v11 = *v10;
  v127 = v11;
  if ( (v11 & 0xFFFFFE00) == 0 )
    goto LABEL_7;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225659LL, 993447);
  return 3221225659LL;
}

```

## disassembly

```asm
0x14024c894  mov     r11, rsp
0x14024c897  push    rbx
0x14024c898  push    rsi
0x14024c899  push    rdi
0x14024c89a  push    r12
0x14024c89c  push    r13
0x14024c89e  push    r14
0x14024c8a0  push    r15
0x14024c8a2  sub     rsp, 3D0h
0x14024c8a9  mov     rax, cs:__security_cookie
0x14024c8b0  xor     rax, rsp
0x14024c8b3  mov     [rsp+408h+var_40], rax
0x14024c8bb  mov     r13, r9
0x14024c8be  mov     [rsp+408h+Irp], r8
0x14024c8c6  mov     r12, rdx
0x14024c8c9  mov     [rsp+408h+var_218], rdx
0x14024c8d1  mov     rsi, rcx
0x14024c8d4  mov     [rsp+408h+var_1F0], rcx
0x14024c8dc  mov     [rsp+408h+var_1F8], r9
0x14024c8e4  mov     r14, [rsp+408h+arg_20]
0x14024c8ec  mov     [rsp+408h+var_260], r14
0x14024c8f4  mov     rdi, [rsp+408h+arg_28]
0x14024c8fc  mov     [rsp+408h+var_338], rdi
0x14024c904  mov     rbx, [r8+0B8h]
0x14024c90b  xor     ecx, ecx
0x14024c90d  mov     r15d, ecx
0x14024c910  mov     [r11-2B0h], rcx
0x14024c917  mov     [r11-208h], rcx
0x14024c91e  xorps   xmm0, xmm0
0x14024c921  movups  xmmword ptr [rsp+408h+Buf1], xmm0
0x14024c929  xorps   xmm1, xmm1
0x14024c92c  movups  [rsp+408h+var_2C8], xmm1
0x14024c934  mov     [rsp+408h+var_388], cl
0x14024c93b  mov     [r11-308h], rcx
0x14024c942  mov     [rsp+408h+var_33C], cx
0x14024c94a  movups  xmmword ptr [rsp+408h+Buf2], xmm0
0x14024c952  movups  xmmword ptr [rsp+408h+var_270], xmm1
0x14024c95a  movups  xmmword ptr [rsp+408h+var_238], xmm0
0x14024c962  mov     [r11-2F0h], rcx
0x14024c969  movups  [rsp+408h+var_228], xmm1
0x14024c971  xor     edx, edx; Val
0x14024c973  lea     r8d, [rcx+70h]; Size
0x14024c977  lea     rcx, [r11-188h]; void *
0x14024c97e  call    memset
0x14024c983  xor     edx, edx; Val
0x14024c985  lea     r8d, [r15+50h]; Size
0x14024c989  lea     rcx, [rsp+408h+var_A8]; void *
0x14024c991  call    memset
0x14024c996  mov     [rsp+408h+var_2A4], r15d
0x14024c99e  xor     edx, edx; Val
0x14024c9a0  lea     r8d, [r15+70h]; Size
0x14024c9a4  lea     rcx, [rsp+408h+var_118]; void *
0x14024c9ac  call    memset
0x14024c9b1  mov     rax, cs:CLFS_LSN_NULL_EXT
0x14024c9b8  mov     qword ptr [rsp+408h+plsn], rax
0x14024c9c0  xorps   xmm0, xmm0
0x14024c9c3  xor     eax, eax
0x14024c9c5  movups  xmmword ptr [rsp+408h+Context], xmm0
0x14024c9cd  movups  xmmword ptr [rsp+408h+var_368], xmm0
0x14024c9d5  movups  xmmword ptr [rsp+408h+Bcb], xmm0
0x14024c9dd  mov     [rsp+408h+var_348], rax
0x14024c9e5  mov     rax, [rsi+70h]
0x14024c9e9  mov     rax, [rax+18h]
0x14024c9ed  lea     ecx, [r15+0Ah]
0x14024c9f1  mov     [rsp+408h+var_32C], ecx
0x14024c9f8  cmp     [rbx+10h], ecx
0x14024c9fb  jnz     short loc_14024CA12
0x14024c9fd  xor     r10d, r10d
0x14024ca00  mov     edx, r10d
0x14024ca03  cmp     [rax], r10b
0x14024ca06  setnz   dl
0x14024ca09  mov     [rsp+408h+var_340], edx
0x14024ca10  jmp     short loc_14024CA4C
0x14024ca12  mov     edx, [rax]
0x14024ca14  mov     [rsp+408h+var_340], edx
0x14024ca1b  test    edx, 0FFFFFE00h
0x14024ca21  jz      short loc_14024CA49
0x14024ca23  mov     al, cs:NtfsStatusDebugFlags
0x14024ca29  test    al, al
0x14024ca2b  jz      short loc_14024CA3F
0x14024ca2d  mov     edx, 0C00000BBh
0x14024ca32  xor     ecx, ecx
0x14024ca34  mov     r8d, 0F28A7h
0x14024ca3a  call    NtfsStatusTraceAndDebugInternal
0x14024ca3f  mov     eax, 0C00000BBh
0x14024ca44  jmp     loc_14024F676
0x14024ca49  xor     r10d, r10d
0x14024ca4c  mov     ecx, edx
0x14024ca4e  mov     r8d, 2
0x14024ca54  and     ecx, r8d
0x14024ca57  mov     [rsp+408h+var_2D8], ecx
0x14024ca5e  jz      short loc_14024CA8F
0x14024ca60  cmp     [r13+0C8h], r10
0x14024ca67  jnz     short loc_14024CA8F
0x14024ca69  mov     al, cs:NtfsStatusDebugFlags
0x14024ca6f  test    al, al
0x14024ca71  jz      short loc_14024CA85
0x14024ca73  mov     edx, 0C000029Ch
0x14024ca78  xor     ecx, ecx
0x14024ca7a  mov     r8d, 0F28B1h
0x14024ca80  call    NtfsStatusTraceAndDebugInternal
0x14024ca85  mov     eax, 0C000029Ch
0x14024ca8a  jmp     loc_14024F676
0x14024ca8f  mov     [rsp+408h+Context], rsi
0x14024ca97  mov     byte ptr [rsp+408h+Bcb+9], 58h ; 'X'
0x14024ca9f  mov     r11, [r14+0B8h]
0x14024caa6  mov     [rsp+408h+Context+8], r11
0x14024caae  mov     rbx, [rbx+18h]
0x14024cab2  test    rbx, rbx
0x14024cab5  jnz     short loc_14024CB12
0x14024cab7  cmp     [rax+10h], r8d
0x14024cabb  jb      short loc_14024CB12
0x14024cabd  lea     rcx, [rax+14h]
0x14024cac1  cmp     word ptr [rcx], 3Ah ; ':'
0x14024cac5  jnz     short loc_14024CB12
0x14024cac7  mov     [rsp+408h+Buf1+8], rcx
0x14024cacf  movzx   eax, word ptr [rax+10h]
0x14024cad3  mov     word ptr [rsp+408h+Buf1], ax
0x14024cadb  mov     word ptr [rsp+408h+Buf1+2], ax
0x14024cae3  and     dl, 1
0x14024cae6  lea     rax, [rsp+408h+Buf1]
0x14024caee  mov     [rsp+408h+var_3D8], rax; __int64
0x14024caf3  mov     byte ptr [rsp+408h+PostIrpRoutine], dl; char
0x14024caf7  mov     [rsp+408h+CompletionRoutine], rdi; __int64
0x14024cafc  mov     r9, r14
0x14024caff  mov     r8, r11
0x14024cb02  mov     rdx, r12
0x14024cb05  mov     rcx, rsi; int
0x14024cb08  call    NtfsStreamRename
0x14024cb0d  jmp     loc_14024F676
0x14024cb12  mov     eax, [rdi+4]
0x14024cb15  test    r8b, al
0x14024cb18  jz      loc_14024F656
0x14024cb1e  mov     rdx, [rdi+48h]
0x14024cb22  mov     [rsp+408h+var_320], rdx
0x14024cb2a  test    rdx, rdx
0x14024cb2d  jz      loc_14024F656
0x14024cb33  test    dword ptr [r11+4], 100h
0x14024cb3b  jnz     loc_14024F656
0x14024cb41  mov     r12d, [rdx+4]
0x14024cb45  mov     r14d, 1
0x14024cb4b  test    r14b, r12b
0x14024cb4e  jnz     loc_14024F56C
0x14024cb54  mov     rax, [rdx+0C0h]
0x14024cb5b  test    byte ptr [rax+41h], 3
0x14024cb5f  jz      short loc_14024CB71
0x14024cb61  mov     rax, [rdx+30h]
0x14024cb65  mov     ecx, [rax+4]
0x14024cb68  test    cl, 20h
0x14024cb6b  jnz     loc_14024F56C
0x14024cb71  mov     r12b, 20h ; ' '
0x14024cb74  mov     r9d, [r11+0B0h]
0x14024cb7b  test    r9d, r9d
0x14024cb7e  jns     loc_14024CC32
0x14024cb84  mov     eax, [rsi+10h]
0x14024cb87  bt      rax, 14h
0x14024cb8c  jb      loc_14024CC14
0x14024cb92  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x14024cb99  test    r12b, al
0x14024cb9c  jz      short loc_14024CC14
0x14024cb9e  mov     rdx, [r13+0F8h]
0x14024cba5  movzx   eax, word ptr [rdx+6]
0x14024cba9  mov     ecx, 40h ; '@'
0x14024cbae  cmp     ax, cx
0x14024cbb1  ja      short loc_14024CBB8
0x14024cbb3  test    r14b, al
0x14024cbb6  jz      short loc_14024CBBB
0x14024cbb8  mov     eax, r10d
0x14024cbbb  lea     rcx, [rdx+20h]
0x14024cbbf  movzx   edx, ax
0x14024cbc2  shr     edx, 1
0x14024cbc4  movzx   r10d, word ptr [r13+1EC0h]
0x14024cbcc  shr     r10d, 1
0x14024cbcf  mov     r8, gs:188h
0x14024cbd8  mov     dword ptr [rsp+408h+var_3B8], r9d
0x14024cbdd  mov     rax, [r11+8]
0x14024cbe1  mov     qword ptr [rsp+408h+var_3C0], rax
0x14024cbe6  mov     qword ptr [rsp+408h+var_3C8], r11
0x14024cbeb  mov     qword ptr [rsp+408h+var_3D0], rcx
0x14024cbf0  mov     dword ptr [rsp+408h+var_3D8], edx
0x14024cbf4  mov     rax, [r13+1EC8h]
0x14024cbfb  mov     [rsp+408h+PostIrpRoutine], rax
0x14024cc00  mov     dword ptr [rsp+408h+CompletionRoutine], r10d
0x14024cc05  mov     r9, r13
0x14024cc08  lea     rdx, fileinfo_c10508
0x14024cc0f  call    McTemplateU0ppwwpid_EtwWriteTransfer
0x14024cc14  mov     al, cs:NtfsStatusDebugFlags
0x14024cc1a  test    al, al
0x14024cc1c  jz      loc_14024F64F
0x14024cc22  mov     edi, 0C0000022h
0x14024cc27  mov     r8d, 0F2919h
0x14024cc2d  jmp     loc_14024F66B
0x14024cc32  mov     eax, [rsi+0Ch]
0x14024cc35  test    r14b, al
0x14024cc38  jnz     short loc_14024CC55
0x14024cc3a  xor     r9d, r9d
0x14024cc3d  xor     r8d, r8d
0x14024cc40  mov     rdx, [rsp+408h+Irp]
0x14024cc48  mov     rcx, rsi; StartContext
0x14024cc4b  call    NtfsPostRequest
0x14024cc50  jmp     loc_14024F676
0x14024cc55  mov     edi, r10d
0x14024cc58  mov     [rsp+408h+var_384], r10d
0x14024cc60  mov     [rsp+408h+var_300], r10d
0x14024cc68  mov     rax, r10
0x14024cc6b  mov     [rsp+408h+var_2B8], rax
0x14024cc73  mov     [rsp+408h+var_240], rax
0x14024cc7b  mov     [rsp+408h+var_298], r10
0x14024cc83  mov     [rsp+408h+var_2FC], r10d
0x14024cc8b  mov     [rsp+408h+var_2D0], r10
0x14024cc93  mov     [rsp+408h+var_380], r10b
0x14024cc9b  mov     [rsp+408h+var_330], r10d
0x14024cca3  mov     rcx, [rsp+408h+var_338]
0x14024ccab  mov     eax, [rcx+64h]
0x14024ccae  mov     [rsi+110h], eax
0x14024ccb4  mov     rax, [rdx+18h]
0x14024ccb8  mov     qword ptr [rsp+408h+var_368+8], rax
0x14024ccc0  lea     rax, [rsp+408h+var_168]
0x14024ccc8  mov     [rsp+408h+var_188+8], rax
0x14024ccd0  lea     rax, [rsp+408h+var_150]
0x14024ccd8  mov     [rsp+408h+P+8], rax
0x14024cce0  mov     dword ptr [rsp+408h+var_188], 180000h
0x14024cceb  mov     dword ptr [rsp+408h+P], 340000h
0x14024ccf6  mov     r8, [rsi+190h]
0x14024ccfd  mov     [rsp+408h+var_2F8], r8
0x14024cd05  test    byte ptr [rcx+4], 8
0x14024cd09  mov     eax, 58h ; 'X'
0x14024cd0e  lea     ecx, [rax+1]
0x14024cd11  cmovz   eax, ecx
0x14024cd14  mov     byte ptr [rsp+408h+Bcb+9], al
0x14024cd1b  mov     [rsp+408h+var_270+8], r10
0x14024cd23  mov     [rsp+408h+var_238+8], r10
0x14024cd2b  test    dword ptr [r11+0B0h], 10000000h
0x14024cd36  jz      loc_14024CE5F
0x14024cd3c  mov     rdx, [r11+148h]
0x14024cd43  test    rdx, rdx
0x14024cd46  jz      short loc_14024CD96
0x14024cd48  mov     eax, [rdx+80h]
0x14024cd4e  test    eax, eax
0x14024cd50  jz      short loc_14024CD96
0x14024cd52  test    r8, r8
0x14024cd55  jz      short loc_14024CD68
0x14024cd57  cmp     eax, r14d
0x14024cd5a  jnz     short loc_14024CD68
0x14024cd5c  mov     rcx, r8
0x14024cd5f  call    TxfSearchNoRenameList
0x14024cd64  test    al, al
0x14024cd66  jnz     short loc_14024CD96
0x14024cd68  mov     al, cs:NtfsStatusDebugFlags
0x14024cd6e  test    al, al
0x14024cd70  jz      short loc_14024CD85
0x14024cd72  mov     edx, 0C0190037h
0x14024cd77  mov     r8d, 0F2959h
0x14024cd7d  mov     rcx, rsi
0x14024cd80  call    NtfsStatusTraceAndDebugInternal
0x14024cd85  mov     ecx, 0C0190037h; Status
0x14024cd8a  call    cs:__imp_ExRaiseStatus
0x14024cd96  lea     rax, [rsp+408h+plsn]
0x14024cd9e  mov     [rsp+408h+CompletionRoutine], rax; __int64
0x14024cda3  mov     r8, [rsp+408h+var_260]
0x14024cdab  mov     rdx, [rsp+408h+Irp]; Irp
0x14024cdb3  mov     rcx, rsi; Context
0x14024cdb6  call    NtfsProcessTreeForRename
0x14024cdbb  mov     edi, eax
0x14024cdbd  mov     [rsp+408h+var_384], eax
0x14024cdc4  test    eax, eax
0x14024cdc6  jnz     loc_14024D234
0x14024cdcc  mov     rax, [rsp+408h+var_2F8]
0x14024cdd4  test    rax, rax
0x14024cdd7  jz      short loc_14024CDE1
0x14024cdd9  lock or dword ptr [rax+10h], 10000h
0x14024cde1  lea     rcx, [rsp+408h+plsn]; plsn
0x14024cde9  call    cs:__imp_ClfsLsnNull
0x14024cdf0  nop     dword ptr [rax+rax+00h]
0x14024cdf5  test    al, al
0x14024cdf7  jnz     short loc_14024CE5F
0x14024cdf9  mov     byte ptr [rsp+408h+CompletionRoutine], r14b
0x14024cdfe  xor     r9d, r9d
0x14024ce01  xor     edx, edx
0x14024ce03  lea     r8d, [r9+5]
0x14024ce07  mov     rcx, [rsi+90h]
0x14024ce0e  call    TxfSearchAddTxfFcbCleanupList
0x14024ce13  mov     ecx, 8000h
0x14024ce18  or      [rax+10h], ecx
0x14024ce1b  mov     rcx, qword ptr [rsp+408h+plsn]
0x14024ce23  mov     [rax+28h], rcx
0x14024ce27  mov     rcx, [rsp+408h+Context+8]
0x14024ce2f  mov     rdx, [rcx+140h]
0x14024ce36  mov     [rax+20h], rdx
0x14024ce3a  lock add [rdx+40h], r14d
0x14024ce3f  mov     rax, [rax+20h]
0x14024ce43  lock add [rax+30h], r14d
0x14024ce48  mov     al, cs:NtfsStatusDebugFlags
0x14024ce4e  mov     ecx, 0C00000D8h; Status
0x14024ce53  call    cs:__imp_ExRaiseStatus
0x14024ce5f  lea     rax, [rsp+408h+Buf1]
0x14024ce67  mov     [rsp+408h+var_3D8], rax
0x14024ce6c  lea     rax, [rsp+408h+var_2C8]
0x14024ce74  mov     [rsp+408h+PostIrpRoutine], rax
0x14024ce79  lea     rax, [rsp+408h+var_208]
  ... truncated ...
```
