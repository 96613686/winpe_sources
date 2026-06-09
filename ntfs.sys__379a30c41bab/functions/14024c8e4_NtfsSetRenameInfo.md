# NtfsSetRenameInfo

- ea: `0x14024c8e4`
- end: `0x14024f7d4`
- name: `NtfsSetRenameInfo`
- size: `12016`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `59`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x1402022d8`

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
- `0x140046b48`
- `0x140046c38`
- `0x140046dc0`
- `0x1400592c0`
- `0x140059440`
- `0x140059740`
- `0x140059c60`
- `0x1400d2540`
- `0x1400d2740`
- `0x14011e36c`
- `0x1401215e0`
- `0x140128da0`
- `0x14012c80c`
- `0x14012f980`
- `0x1401403d0`
- `0x140141a3c`
- `0x14014a820`
- `0x14014a980`
- `0x14014b5f8`
- `0x14014bb30`
- `0x140154188`
- `0x140154d60`
- `0x140163420`
- `0x1401857d8`
- `0x14018bf90`
- `0x14018c660`
- `0x14018dc9c`
- `0x14018f790`
- `0x140190460`
- `0x1401924c0`
- `0x1401937ec`
- `0x140199140`
- `0x14019b380`
- `0x14019f270`
- `0x1401c0130`
- `0x1401e06b0`
- `0x1401eaf58`
- `0x1401fc4b0`
- `0x140204dfc`

## import_xrefs

- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x14024e470`
- `ntoskrnl!FsRtlAddToTunnelCacheEx` at `0x14024e470`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x14024e86d`
- `ntoskrnl!FsRtlFindInTunnelCacheEx` at `0x14024e86d`
- `ntoskrnl!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14024d3de`
- `ntoskrnl!RtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14024d3de`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14024f4e8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b8919`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14024f4e8`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1402b8919`
- `ntoskrnl!ExReleasePushLockEx` at `0x14024f505`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b8939`
- `ntoskrnl!ExReleasePushLockEx` at `0x14024f505`
- `ntoskrnl!ExReleasePushLockEx` at `0x1402b8939`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024e7ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f3f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f417`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f435`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f450`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f46e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f491`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f4c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8833`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b884e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8869`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8884`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b889f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b88c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b88f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024e7ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f3f9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f417`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f435`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f450`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f46e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f491`
- `ntoskrnl!ExFreePoolWithTag` at `0x14024f4c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8833`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b884e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8869`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b8884`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b889f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b88c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b88f3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024dd74`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024de32`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024e4a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024ec38`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024ee0b`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024dd74`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024de32`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024e4a3`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024ec38`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14024ee0b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024db83`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14024db83`
- `ntoskrnl!CcUnpinData` at `0x14024d938`
- `ntoskrnl!CcUnpinData` at `0x14024e195`
- `ntoskrnl!CcUnpinData` at `0x14024d938`
- `ntoskrnl!CcUnpinData` at `0x14024e195`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024dce0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024f772`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024dce0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14024f772`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14024ef66`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14024f01b`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14024ef66`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14024f01b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14024d47b`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x14024d47b`
- `ntoskrnl!ExRaiseStatus` at `0x14024cdda`
- `ntoskrnl!ExRaiseStatus` at `0x14024cea3`
- `ntoskrnl!ExRaiseStatus` at `0x14024e081`
- `ntoskrnl!ExRaiseStatus` at `0x14024e258`
- `ntoskrnl!ExRaiseStatus` at `0x14024cdda`
- `ntoskrnl!ExRaiseStatus` at `0x14024cea3`
- `ntoskrnl!ExRaiseStatus` at `0x14024e081`
- `ntoskrnl!ExRaiseStatus` at `0x14024e258`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14024ce39`
- `ext-ms-win-fs-clfs-l1-1-0!ClfsLsnNull` at `0x14024ce39`

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
  __int64 v44; // r9
  int v45; // edi
  __int64 v46; // rbx
  int v47; // eax
  unsigned int CurrentFileInfo; // eax
  __int64 v49; // rcx
  __int64 v50; // rbx
  __int64 v51; // r10
  unsigned __int16 v52; // cx
  unsigned __int16 v53; // ax
  __int64 NextScb; // rax
  __int64 v55; // r10
  int v56; // ecx
  char v57; // al
  char v58; // dl
  __int64 v59; // rcx
  int v60; // eax
  int v61; // eax
  __int64 v62; // rdx
  int v63; // ecx
  __int64 v64; // rdx
  int v65; // r8d
  int v66; // eax
  char v67; // al
  __int64 v68; // rbx
  int v69; // eax
  BOOL v70; // eax
  __int64 v71; // rax
  char v72; // bl
  char v73; // cl
  __int64 v74; // rax
  __int64 v75; // rax
  int v76; // eax
  __int64 v77; // rdx
  __int64 v78; // rax
  int v79; // eax
  int v80; // ecx
  unsigned __int8 *v81; // rbx
  __int64 v82; // rcx
  char *v83; // rbx
  char *v84; // rbx
  char *v85; // rcx
  int v86; // eax
  int v87; // eax
  __int64 *v88; // rax
  __int64 *v89; // rax
  __int64 v90; // rbx
  char v91; // cl
  int v92; // r8d
  int v93; // r8d
  int v94; // r8d
  __m128i *v95; // rdx
  __m128i *v96; // xmm1_8
  __m128i *v97; // rdx
  __m128i *v98; // xmm0_8
  char v99; // bl
  char v100; // dl
  int v101; // eax
  __int64 v102; // r9
  __int64 v103; // rbx
  int v104; // ecx
  BOOL v105; // ecx
  BOOL v106; // ecx
  __int16 v107; // bx
  int v108; // ebx
  __int16 v109; // bx
  __int64 v110; // rax
  _WORD *v111; // rcx
  PVOID v112; // r8
  char v113; // cl
  _DWORD *v114; // rcx
  char v115; // cl
  int v116; // r12d
  int v117; // r9d
  __int64 v118; // r10
  unsigned __int16 v119; // r8
  __int64 v120; // rax
  char v121[4]; // [rsp+F8h] [rbp-388h] BYREF
  unsigned int v122; // [rsp+FCh] [rbp-384h]
  char v123; // [rsp+100h] [rbp-380h]
  PVOID Contexta[2]; // [rsp+108h] [rbp-378h] BYREF
  int v125[4]; // [rsp+118h] [rbp-368h]
  PVOID Bcb[2]; // [rsp+128h] [rbp-358h] BYREF
  __int64 v127; // [rsp+138h] [rbp-348h]
  int v128; // [rsp+140h] [rbp-340h]
  _WORD v129[2]; // [rsp+144h] [rbp-33Ch] BYREF
  __int64 v130; // [rsp+148h] [rbp-338h]
  int v131; // [rsp+150h] [rbp-330h]
  int v132; // [rsp+154h] [rbp-32Ch] BYREF
  char v133; // [rsp+158h] [rbp-328h]
  __int64 v134; // [rsp+160h] [rbp-320h]
  void *Buf1[2]; // [rsp+168h] [rbp-318h] BYREF
  PVOID v136; // [rsp+178h] [rbp-308h] BYREF
  int v137; // [rsp+180h] [rbp-300h]
  int v138; // [rsp+184h] [rbp-2FCh]
  __int64 v139; // [rsp+188h] [rbp-2F8h]
  __int64 v140; // [rsp+190h] [rbp-2F0h] BYREF
  void *Src; // [rsp+198h] [rbp-2E8h]
  char v142; // [rsp+1A0h] [rbp-2E0h]
  int v143; // [rsp+1A4h] [rbp-2DCh]
  int v144; // [rsp+1A8h] [rbp-2D8h]
  __m128i *v145; // [rsp+1B0h] [rbp-2D0h]
  __int128 v146; // [rsp+1B8h] [rbp-2C8h] BYREF
  PVOID v147; // [rsp+1C8h] [rbp-2B8h]
  __int64 v148; // [rsp+1D0h] [rbp-2B0h] BYREF
  int v149; // [rsp+1D8h] [rbp-2A8h]
  int v150; // [rsp+1DCh] [rbp-2A4h]
  int v151; // [rsp+1E0h] [rbp-2A0h]
  int v152; // [rsp+1E4h] [rbp-29Ch]
  PVOID PoolWithTag; // [rsp+1E8h] [rbp-298h]
  void *Buf2[2]; // [rsp+1F0h] [rbp-290h] BYREF
  PIRP Irp; // [rsp+200h] [rbp-280h]
  __int64 v156; // [rsp+208h] [rbp-278h]
  PVOID v157[2]; // [rsp+210h] [rbp-270h] BYREF
  __int64 v158; // [rsp+220h] [rbp-260h]
  __int64 v159; // [rsp+228h] [rbp-258h]
  CLFS_LSN plsn; // [rsp+230h] [rbp-250h] BYREF
  int v161; // [rsp+238h] [rbp-248h]
  PVOID v162; // [rsp+240h] [rbp-240h]
  PVOID v163[2]; // [rsp+248h] [rbp-238h] BYREF
  __int128 v164; // [rsp+258h] [rbp-228h] BYREF
  __int64 v165; // [rsp+268h] [rbp-218h]
  __int64 v166; // [rsp+270h] [rbp-210h]
  _QWORD v167[4]; // [rsp+278h] [rbp-208h] BYREF
  __int64 v168[12]; // [rsp+298h] [rbp-1E8h] BYREF
  __m128i v169[7]; // [rsp+2F8h] [rbp-188h] BYREF
  _OWORD v170[7]; // [rsp+368h] [rbp-118h] BYREF
  __int64 v171[10]; // [rsp+3D8h] [rbp-A8h] BYREF
  char v172; // [rsp+428h] [rbp-58h] BYREF

  Irp = a3;
  v165 = a2;
  v167[3] = Context;
  v167[2] = a4;
  v158 = a5;
  v130 = a6;
  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  v9 = 0;
  v148 = 0;
  v167[0] = 0;
  *(_OWORD *)Buf1 = 0;
  v146 = 0;
  v121[0] = 0;
  v136 = 0;
  v129[0] = 0;
  *(_OWORD *)Buf2 = 0;
  *(_OWORD *)v157 = 0;
  *(_OWORD *)v163 = 0;
  v140 = 0;
  v164 = 0;
  memset(v169, 0, sizeof(v169));
  memset(v171, 0, sizeof(v171));
  v150 = 0;
  memset(v170, 0, sizeof(v170));
  plsn.ullOffset = CLFS_LSN_NULL_EXT;
  *(_OWORD *)Contexta = 0;
  *(_OWORD *)v125 = 0;
  *(_OWORD *)Bcb = 0;
  v127 = 0;
  v10 = *(int **)(Context[14] + 24LL);
  v132 = 10;
  if ( CurrentStackLocation->Parameters.Create.Options == 10 )
  {
    LOBYTE(v11) = *(_BYTE *)v10 != 0;
    v128 = (unsigned __int8)v11;
LABEL_7:
    v144 = v11 & 2;
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
      || (v15 = *(_QWORD *)(a6 + 72), (v134 = v15) == 0)
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
        v118 = *(_QWORD *)(a4 + 248);
        v119 = *(_WORD *)(v118 + 6);
        if ( v119 > 0x40u || (v119 & 1) != 0 )
          v119 = 0;
        v120 = *(_QWORD *)(v15 + 192);
        McTemplateU0ppwwpidpwdd_EtwWriteTransfer(
          *(unsigned __int8 *)(v120 + 65),
          v120 + 66,
          (unsigned int)KeGetCurrentThread(),
          a4,
          *(_WORD *)(a4 + 7872) >> 1,
          *(_QWORD *)(a4 + 7880),
          v119 >> 1,
          v118 + 32,
          *(_QWORD *)(v15 + 48),
          *(_QWORD *)(*(_QWORD *)(v15 + 48) + 8LL),
          *(_DWORD *)(*(_QWORD *)(v15 + 48) + 4LL),
          v134,
          *(unsigned __int8 *)(v120 + 64) >> 1,
          v120 + 66,
          *(_BYTE *)(v120 + 65),
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
    v122 = 0;
    v137 = 0;
    v147 = 0;
    v162 = 0;
    PoolWithTag = 0;
    v138 = 0;
    v145 = 0;
    v123 = 0;
    v131 = 0;
    v22 = v130;
    *((_DWORD *)Context + 68) = *(_DWORD *)(v130 + 100);
    *(_QWORD *)&v125[2] = *(_QWORD *)(v15 + 24);
    v169[0].m128i_i64[1] = (__int64)v169[2].m128i_i64;
    v169[1].m128i_i64[1] = (__int64)&v169[3].m128i_i64[1];
    v169[0].m128i_i32[0] = 1572864;
    v169[1].m128i_i32[0] = 3407872;
    v23 = Context[50];
    v139 = v23;
    v24 = 88;
    if ( (*(_BYTE *)(v22 + 4) & 8) == 0 )
      v24 = 89;
    BYTE1(Bcb[1]) = v24;
    v157[1] = 0;
    v163[1] = 0;
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
      v122 = v20;
      if ( v20 )
        goto LABEL_425;
      if ( v139 )
        _InterlockedOr((volatile signed __int32 *)(v139 + 16), 0x10000u);
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
      v125[2],
      (unsigned int)&v148,
      (__int64)v167,
      (__int64)&v146,
      (__int64)Buf1);
    v9 = v148;
    if ( v148 == v158 )
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
          v138 = 0;
        }
        else
        {
          v37 = *(_WORD *)(v35 + 6);
          v138 = v37;
        }
        LOWORD(v167[0]) = v37;
        v167[1] = v35 + 32;
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
          v137 = 0;
        }
        else
        {
          v40 = *(_WORD *)(v38 + 6);
          v137 = v40;
        }
        LOWORD(v165) = v40;
        v166 = v38 + 32;
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
    v41 = *(_QWORD *)&v125[2];
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v125[2] + 184LL) + 112LL) )
    {
      LOBYTE(v28) = 1;
      NtfsAcquirePagingResourceExclusive(Context, *(_QWORD *)(*(_QWORD *)&v125[2] + 184LL), v28, v32);
      LOBYTE(Bcb[1]) |= 2u;
      v41 = *(_QWORD *)&v125[2];
    }
    NtfsAcquireExclusiveScbEx(Context, v41, 0);
    if ( ((__int64)Bcb[1] & 2) == 0 )
    {
      v42 = *(_QWORD *)(*(_QWORD *)&v125[2] + 184LL);
      if ( *(_QWORD *)(v42 + 112) )
      {
        NtfsReleaseFcbEx(Context, v42, 0);
        LOBYTE(v43) = 1;
        NtfsAcquirePagingResourceExclusive(Context, *(_QWORD *)(*(_QWORD *)&v125[2] + 184LL), v43, v44);
        LOBYTE(Bcb[1]) |= 2u;
        NtfsAcquireExclusiveScbEx(Context, *(_QWORD *)&v125[2], 0);
      }
    }
    if ( !*(_WORD *)(*(_QWORD *)&v125[2] + 656LL) )
      NtfsBuildNormalizedNameWithTxfIsolation(
        (_DWORD)Context,
        *(_QWORD *)(*(_QWORD *)&v125[2] + 184LL),
        v125[2],
        0,
        0,
        0,
        *(_QWORD *)&v125[2] + 656LL);
    if ( v139 )
    {
      v20 = TxfPrepareFileForPotentialTxLinkDelete((int)Context);
      v122 = v20;
      v27 = 0;
      if ( v20 )
        goto LABEL_425;
    }
    if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 && !*(_WORD *)(v158 + 656) )
      NtfsUpdateNormalizedName((int)Context, 0);
    if ( v9 == *(_QWORD *)&v125[2] )
    {
      if ( LOWORD(Buf1[0]) == *(_WORD *)(v134 + 72) && !memcmp(Buf1[1], *(const void **)(v134 + 80), LOWORD(Buf1[0])) )
        goto LABEL_425;
      goto LABEL_94;
    }
    if ( (*((_DWORD *)Context + 3) & 0x100) != 0 )
    {
      NtfsAcquireExclusiveScbEx(Context, v9, 0);
    }
    else
    {
      v46 = 0;
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
        v122 = v20;
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
    v46 = v9 + 656;
    if ( *(_WORD *)(v9 + 656) )
      goto LABEL_119;
    if ( (*((_DWORD *)Context + 3) & 0x100) != 0
      || (Context[2] & 0x40000000) != 0
      || (*(_DWORD *)(Context[18] + 16LL) & 0x40000000) != 0
      || ExIsResourceAcquiredExclusiveLite((PERESOURCE)(a4 + 2160)) )
    {
      NtfsBuildNormalizedNameWithTxfIsolation((_DWORD)Context, *(_QWORD *)(v9 + 184), v9, 0, 0, 0, v9 + 656);
LABEL_119:
      v49 = *(unsigned int *)(v167[0] + 4LL);
      if ( (v49 & 8) != 0 && (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 )
      {
        v50 = v158;
        if ( (*((_DWORD *)Context + 3) & 0x100) != 0 )
        {
          NextScb = v158;
          do
          {
            NextScb = NtfsGetNextScb(v49, NextScb, v50, 0);
            if ( !NextScb )
              goto LABEL_94;
          }
          while ( NextScb != v9 );
          if ( (!Context || (Context[2] & 0x100000) == 0)
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
          {
            v55 = *(_QWORD *)(a4 + 248);
            v56 = *(unsigned __int16 *)(v55 + 6);
            if ( (unsigned __int16)v56 > 0x40u || (v56 & 1) != 0 )
              v56 = 0;
            v144 = v56;
            LOWORD(Irp) = v56;
            v156 = v55 + 32;
            McTemplateU0ppwwpii_EtwWriteTransfer(
              (unsigned __int16)v56 >> 1,
              *(_QWORD *)(v50 + 184),
              (unsigned int)KeGetCurrentThread(),
              a4,
              *(_WORD *)(a4 + 7872) >> 1,
              *(_QWORD *)(a4 + 7880),
              (unsigned __int16)v56 >> 1,
              v55 + 32,
              *(_QWORD *)(v50 + 184),
              *(_QWORD *)(*(_QWORD *)(v50 + 184) + 8LL),
              *(_QWORD *)(*(_QWORD *)(v9 + 184) + 8LL));
          }
          v20 = -1073741790;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_424;
          v31 = 994045;
          goto LABEL_423;
        }
        if ( (unsigned __int8)NtfsHasSubdirectory(v49, v158) )
        {
          if ( (Context[2] & 0x100000) == 0
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
          {
            v51 = *(_QWORD *)(a4 + 248);
            v52 = *(_WORD *)(v51 + 6);
            if ( v52 > 0x40u || (v52 & 1) != 0 )
            {
              v53 = 0;
              v128 = 0;
            }
            else
            {
              v53 = *(_WORD *)(v51 + 6);
              v128 = v53;
            }
            LOWORD(v158) = v53;
            v159 = v51 + 32;
            McTemplateU0ppwwpi_EtwWriteTransfer(
              *(_QWORD *)(v50 + 184),
              (unsigned int)fileinfo_c10972,
              (unsigned int)KeGetCurrentThread(),
              a4,
              *(_WORD *)(a4 + 7872) >> 1,
              *(_QWORD *)(a4 + 7880),
              v53 >> 1,
              v51 + 32,
              *(_QWORD *)(v50 + 184),
              *(_QWORD *)(*(_QWORD *)(v50 + 184) + 8LL));
          }
          v20 = -1073741790;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_424;
          v31 = 994024;
          goto LABEL_423;
        }
      }
LABEL_94:
      v45 = v134;
      v46 = v130;
      if ( (*(_BYTE *)(*(_QWORD *)(v134 + 192) + 65LL) & 3) != 0 && (*(_DWORD *)(v130 + 4) & 1) != 0 )
        BYTE2(Bcb[1]) |= 4u;
      v47 = *(_DWORD *)(v130 + 4);
      LOBYTE(v28) = (v47 & 1) != 0
                 && ((v47 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
      v57 = NtfsLookupEntry(
              (_DWORD)Context,
              v9,
              v28,
              (unsigned int)Buf1,
              (__int64)&v136,
              (__int64)v129,
              0,
              (__int64)&v140,
              (__int64)Bcb,
              0);
      v58 = (__int64)Bcb[1] & 0xDF | (32 * (v57 & 1));
      LOBYTE(Bcb[1]) = v58;
      if ( *((_DWORD *)Context + 7) )
      {
        NtfsCheckpointCurrentTransaction(Context);
        NtfsReleaseSharedResources(Context);
        NtfsReleaseExclusiveScbIfOwned(Context, *(_QWORD *)(a4 + 48));
        v58 = (char)Bcb[1];
      }
      if ( v139 )
      {
        v59 = *(_QWORD *)(v9 + 184);
        if ( *((_QWORD *)Contexta[1] + 40) != *(_QWORD *)(v59 + 320) )
        {
          if ( (v58 & 0x20) != 0 )
          {
            v132 = (int)Bcb[1];
            BYTE1(v132) = BYTE1(Bcb[1]) | 0x20;
            v60 = *(_DWORD *)(v46 + 4);
            if ( (v60 & 1) != 0 && ((v60 & 0x4000000) != 0 || (*(_DWORD *)(v59 + 16) & 0x400) == 0) )
            {
              v61 = 1;
              v46 = 0;
            }
            else
            {
              v46 = 0;
              v61 = 0;
            }
            NtfsCheckLinkForRename(Contexta[1], v45, v140 + 16, *(_QWORD *)v140, (__int64)Buf1, v61, (__int64)&v132);
            if ( (v132 & 0x2000) != 0 && (v132 & 0x200) == 0 && (v128 & 1) == 0 )
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
      v122 = v20;
      if ( v20 )
        goto LABEL_425;
      v28 = v139;
      if ( v139 )
      {
        v62 = *(_QWORD *)(v9 + 184);
        v63 = *(_DWORD *)(v62 + 8);
        if ( v63 != 5 && *(_DWORD *)(*(_QWORD *)(v62 + 320) + 88LL) != v63 )
        {
          v64 = *(_QWORD *)(v62 + 328);
          if ( !v64 || *(_QWORD *)(v64 + 24) != v139 && !(unsigned __int8)TxfSearchNoRenameList(v139) )
          {
            TxfPrepareFileForTxfLogging((int)Context, 0, 0, 1, (*((_DWORD *)Context + 3) & 0x100) == 0);
            v140 = 0;
            if ( Bcb[0] )
            {
              CcUnpinData(Bcb[0]);
              Bcb[0] = 0;
            }
            v66 = *(_DWORD *)(v46 + 4);
            LOBYTE(v65) = (v66 & 1) != 0
                       && ((v66 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
            v67 = NtfsLookupEntry(
                    (_DWORD)Context,
                    v9,
                    v65,
                    (unsigned int)Buf1,
                    (__int64)&v136,
                    (__int64)v129,
                    0,
                    (__int64)&v140,
                    (__int64)Bcb,
                    0);
            LOBYTE(Bcb[1]) = (__int64)Bcb[1] & 0xDF | (32 * (v67 & 1));
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
        v68 = v140;
        v69 = *(_DWORD *)(v130 + 4);
        v70 = (v69 & 1) != 0 && ((v69 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
        v71 = NtfsCheckLinkForRename(
                Contexta[1],
                v134,
                (int)v140 + 16,
                *(_QWORD *)v140,
                (__int64)Buf1,
                v70,
                (__int64)&Bcb[1]);
        v121[0] = *(_BYTE *)(v68 + 81);
        LOBYTE(v71) = v121[0];
        v132 = v71;
        v142 = v121[0];
        v72 = v128;
        if ( (BYTE1(Bcb[1]) & 0x20) != 0 && (BYTE1(Bcb[1]) & 2) == 0 && (v128 & 1) == 0 )
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
        v72 = v128;
      }
      if ( (BYTE1(Bcb[1]) & 0x40) != 0 )
        NtfsCheckIndexForAddOrDelete(
          (_DWORD)Context,
          (_DWORD)Irp,
          *(_QWORD *)(v9 + 184),
          (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 ? 4 : 2,
          v130);
      if ( (BYTE2(Bcb[1]) & 2) != 0
        && *(_BYTE *)(*(_QWORD *)(v9 + 184) + 38LL) != *((_BYTE *)Contexta[1] + 38)
        && (v72 & 8) == 0 )
      {
        v46 = a4 + 10688;
        ExAcquireResourceExclusiveLite((PERESOURCE)(a4 + 10688), 1u);
        v73 = BYTE2(Bcb[1]) | 0x40;
        BYTE2(Bcb[1]) |= 0x40u;
        v74 = *((unsigned __int8 *)Contexta[1] + 38);
        if ( !(_BYTE)v74
          || (v75 = *(_QWORD *)(a4 + 8 * v74 + 10904)) == 0
          || (v76 = *(_DWORD *)(v75 + 4), (v76 & 4) == 0) && ((v76 & 0x10) == 0 || *((_WORD *)Contexta[1] + 94) == 1) )
        {
          v77 = *(unsigned __int8 *)(*(_QWORD *)(v9 + 184) + 38LL);
          if ( !(_BYTE)v77
            || (v78 = *(_QWORD *)(a4 + 8 * v77 + 10904)) == 0
            || (v79 = *(_DWORD *)(v78 + 4), (v79 & 8) == 0) && ((v79 & 0x20) == 0 || *((_WORD *)Contexta[1] + 94) == 1) )
          {
            BYTE2(Bcb[1]) = v73 | 0x80;
            v80 = v131;
            if ( (v128 & 0x10) != 0 )
              v80 = 1;
            v131 = v80;
            v143 = v80;
            if ( (v128 & 0x20) != 0 )
            {
              v80 |= 2u;
              v131 = v80;
              v143 = v80;
            }
            if ( (v128 & 0x80u) != 0 )
            {
              v80 |= 4u;
              v131 = v80;
              v143 = v80;
            }
            if ( (v128 & 0x100) != 0 )
            {
              v80 |= 8u;
              v131 = v80;
              v143 = v80;
            }
            if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 )
            {
              if ( !*(_BYTE *)(*(_QWORD *)(v9 + 184) + 38LL) )
              {
                v20 = NtfsChangeStorageReserveId((_DWORD)Context, 0, v80);
                v122 = v20;
                if ( v20 )
                  goto LABEL_425;
LABEL_471:
                ExReleaseResourceLite((PERESOURCE)v46);
                BYTE2(Bcb[1]) &= ~0x40u;
                NtfsCheckpointCurrentTransaction(Context);
                *((_DWORD *)Context + 92) = *(unsigned __int8 *)(*(_QWORD *)(v9 + 184) + 38LL);
                *((_DWORD *)Context + 93) = v131;
                *((_DWORD *)Context + 3) |= 4u;
                NtfsRaiseStatusInternal((_DWORD)Context, -1073741608, 0, 0, 994500);
                __debugbreak();
                JUMPOUT(0x14024F7D4LL);
              }
              BYTE3(Bcb[1]) |= 1u;
            }
          }
        }
        ExReleaseResourceLite((PERESOURCE)(a4 + 10688));
        BYTE2(Bcb[1]) &= ~0x40u;
      }
      if ( (*(_BYTE *)(*(_QWORD *)(v134 + 192) + 65LL) & 3) == 2 )
      {
        memset(v168, 0, 0x58u);
        Src = 0;
        NtfsLookupPrimaryLink((int)Context, (int)Contexta[1], (__int64)v168);
        v81 = (unsigned __int8 *)Src;
        PoolWithTag = ExAllocatePoolWithTag(
                        (POOL_TYPE)(PoolType | 0x10),
                        2LL * *((unsigned __int8 *)Src + 64) + 66,
                        0x4646744Eu);
        memmove(PoolWithTag, v81, 2LL * v81[64] + 66);
        NtfsCleanupAttributeContext(v82, v168);
      }
      if ( ((__int64)Bcb[1] & 0x20) != 0 && (BYTE1(Bcb[1]) & 0x20) != 0 )
      {
        Src = (void *)(v140 + 16);
        v27 = *(unsigned __int16 *)(v9 + 656) + 2 + 2 * (unsigned int)*(unsigned __int8 *)(v140 + 80);
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
        WORD1(v157[0]) = *(_WORD *)(v9 + 656) + 2 + 2 * *(unsigned __int8 *)(v140 + 80);
        v83 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v27, 0x4646744Eu);
        v157[1] = v83;
        memmove(v83, *(const void **)(v9 + 664), *(unsigned __int16 *)(v9 + 656));
        v84 = &v83[*(unsigned __int16 *)(v9 + 656)];
        v148 = (__int64)v84;
        if ( v9 == *(_QWORD *)(a4 + 32) )
        {
          v85 = v84;
        }
        else
        {
          *(_WORD *)v84 = 92;
          v85 = v84 + 2;
          v84 = v85;
          v148 = (__int64)v85;
        }
        memmove(v85, (char *)Src + 66, 2LL * *((unsigned __int8 *)Src + 64));
        Buf2[1] = v84;
        LOWORD(Buf2[0]) = 2 * *((unsigned __int8 *)Src + 64);
        WORD1(Buf2[0]) = Buf2[0];
        LOWORD(v157[0]) = LOWORD(Buf2[0]) + (_WORD)v84 - LOWORD(v157[1]);
        if ( (BYTE1(Bcb[1]) & 2) != 0 )
        {
          *(PVOID *)v125 = Contexta[1];
          if ( v139 )
          {
            LOBYTE(v129[0]) = 1;
            v149 = 14;
            v86 = *(_DWORD *)(v130 + 4);
            if ( (v86 & 1) != 0 && ((v86 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0) )
              v149 = 15;
            Src = (void *)NtfsCreateLcb(
                            (_DWORD)Context,
                            v9,
                            Contexta[1],
                            (unsigned int)Buf2,
                            *((_BYTE *)Src + 65),
                            (__int64)v129);
            v20 = TxfPrepareFileForPotentialTxLinkDelete((int)Context);
            v122 = v20;
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
              v145 = (__m128i *)v170;
              *((_QWORD *)&v170[0] + 1) = &v170[2];
              *((_QWORD *)&v170[1] + 1) = (char *)&v170[3] + 8;
              LODWORD(v170[0]) = 1572864;
              LODWORD(v170[1]) = 3407872;
              v123 = *(_BYTE *)(*((_QWORD *)Src + 24) + 65LL);
              v133 = v123;
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
                  v130,
                  v144 != 0,
                  (v128 & 0x40) != 0,
                  (__int64)Buf2,
                  (__int64)Contexta);
          v122 = v20;
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
          LOBYTE(v171[9]) = 0;
          if ( v139 )
          {
            v161 = 14;
            v87 = *(_DWORD *)(v130 + 4);
            if ( (v87 & 1) != 0 && ((v87 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0) )
              v161 = 15;
            if ( (BYTE1(Bcb[1]) & 0x40) != 0 )
            {
              v145 = v169;
              v123 = *(_BYTE *)(*(_QWORD *)(v134 + 192) + 65LL);
              v133 = v123;
              TxfRemoveLink((int)Context, (int)Contexta[1], 0);
            }
            else
            {
              if ( *(int *)(a4 + 4) < 0 || (v88 = v171, (*(_DWORD *)(v165 + 80) & 0x20000) != 0) )
                v88 = 0;
              TxfDeleteFile((int)Context, (int)Contexta[1], (__int64)&Bcb[1] + 6, (__int64)v169, (__int64)v88);
            }
          }
          else
          {
            if ( *(int *)(a4 + 4) < 0 || (v89 = v171, (*(_DWORD *)(v165 + 80) & 0x20000) != 0) )
              v89 = 0;
            NtfsRemoveLink((int)Context, (int)Contexta[1], (__int64)v169, (__int64)v89);
            ++WORD2(Bcb[1]);
          }
          v90 = v130;
          v28 = *(unsigned int *)(v130 + 4);
          if ( (v28 & 8) == 0
            && (*((_DWORD *)Contexta[1] + 44) & 0x10000000) == 0
            && *(int *)(a4 + 4) >= 0
            && (*(_DWORD *)(v165 + 80) & 0x20000) == 0 )
          {
            v91 = *(_BYTE *)(*(_QWORD *)(v134 + 192) + 65LL);
            v171[0] = *((_QWORD *)Contexta[1] + 16);
            BYTE1(v171[9]) = (v91 & 2) != 0;
            if ( (v28 & 0x4000000) != 0
              || (v92 = 1, (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v125[2] + 184LL) + 16LL) & 0x400) == 0) )
            {
              v92 = 0;
            }
            FsRtlAddToTunnelCacheEx(
              a4 + 4720,
              *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v125[2] + 184LL) + 8LL),
              v169,
              &v169[1],
              (2 * BYTE1(v171[9])) | v92,
              80,
              v171);
          }
        }
        else
        {
          v90 = v130;
        }
        if ( (BYTE1(Bcb[1]) & 1) != 0 )
        {
          v163[1] = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), *(unsigned __int16 *)(v90 + 16), 0x4646744Eu);
          memmove(v163[1], *(const void **)(v90 + 24), *(unsigned __int16 *)(v90 + 16));
          LOWORD(v163[0]) = *(_WORD *)(v90 + 16);
          WORD1(v163[0]) = v163[0];
          v138 = *(unsigned __int16 *)(v90 + 32);
        }
      }
      if ( (BYTE1(Bcb[1]) & 0x40) == 0 )
      {
LABEL_354:
        if ( SBYTE2(Bcb[1]) >= 0 )
        {
          v108 = 0;
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
          if ( v167[0] && (*(_DWORD *)(v167[0] + 4LL) & 8) != 0 )
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
            v109 = *(_WORD *)(v9 + 656) + LOWORD(Buf1[0]) + 2;
            LOWORD(v146) = v109;
            WORD1(v146) = v27;
            v147 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v27, 0x4646744Eu);
            *((_QWORD *)&v146 + 1) = v147;
            v162 = v147;
            memmove(v147, *(const void **)(v9 + 664), *(unsigned __int16 *)(v9 + 656));
            v110 = *(unsigned __int16 *)(v9 + 656);
            v111 = (char *)v147 + v110;
            v148 = (__int64)v147 + v110;
            if ( (_WORD)v110 == 2 )
            {
              LOWORD(v146) = v109 - 2;
            }
            else
            {
              *v111++ = 92;
              v148 = (__int64)v111;
            }
            memmove(v111, Buf1[1], LOWORD(Buf1[0]));
            v108 = 0;
          }
          v112 = v136;
          v113 = *((_BYTE *)v136 + 65) & 3;
          if ( (BYTE2(Bcb[1]) & 2) != 0 )
          {
            if ( v113 == 2 )
              v112 = 0;
            NtfsMoveLinkToNewDir(
              (int)Context,
              v9,
              (int)Contexta[1],
              v137,
              v134,
              (char)Bcb[1],
              (__int64)Buf2,
              v132,
              (__int64)PoolWithTag,
              (__int64)v112);
            FsRtlCheckOplockEx((POPLOCK)(v9 + 88), Irp, 0x10u, 0, 0, 0);
          }
          else
          {
            if ( v113 == 2 )
              v112 = 0;
            NtfsRenameLinkInDir(
              (int)Context,
              v134,
              (__int64)Buf1,
              v121[0],
              (char)Bcb[1],
              (__int64)Buf2,
              v132,
              (__int64)PoolWithTag,
              (__int64)v112);
          }
          LOBYTE(v127) = 1;
          *((_DWORD *)Context + 3) |= 0x2000000u;
          FsRtlCheckOplockEx((POPLOCK)(*(_QWORD *)&v125[2] + 88LL), Irp, 0x10u, 0, 0, 0);
          v114 = Contexta[1];
          if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 && (BYTE1(Bcb[1]) & 0x40) != 0 )
          {
            NtfsUpdateNormalizedName((int)Context, 0);
            v114 = Contexta[1];
          }
          if ( (BYTE1(Bcb[1]) & 0x10) != 0 )
          {
            NtfsUpdateFcbTimestamps(*(_QWORD *)(*(_QWORD *)&v125[2] + 184LL), 2684354576LL);
            v114 = Contexta[1];
          }
          NtfsUpdateFileTimestampsForChange(v114, v130, ~(v114[44] >> 6) & 0x400000);
          v115 = BYTE1(Bcb[1]);
          if ( (BYTE1(Bcb[1]) & 1) == 0 )
            goto LABEL_420;
          v116 = 0;
          v151 = 0;
          v152 = 0;
          if ( v157[1] && (BYTE1(Bcb[1]) & 0x20) != 0 )
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
                  (unsigned int)v157,
                  LOWORD(v157[0]) - LOWORD(Buf2[0]),
                  0,
                  ((*(_DWORD *)(*(_QWORD *)v125 + 176LL) & 0x10000000) != 0) + 1,
                  2,
                  *(_QWORD *)(v9 + 184),
                  *(__int64 *)v125);
                v115 = BYTE1(Bcb[1]);
              }
            }
          }
          if ( (v115 & 0x10) != 0 )
          {
            if ( (BYTE2(Bcb[1]) & 2) != 0 || (v117 = 4, (v115 & 0x40) == 0) )
              v117 = 2;
            NtfsReportDirNotify(
              (_DWORD)Context,
              v125[2],
              a4,
              (unsigned int)v163,
              (unsigned __int16)v138,
              0,
              ((*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0) + 1,
              v117,
              *(_QWORD *)(*(_QWORD *)&v125[2] + 184LL),
              (__int64)Contexta[1]);
            v115 = BYTE1(Bcb[1]);
          }
LABEL_402:
          if ( ((__int64)Bcb[1] & 0x20) == 0
            || (BYTE2(Bcb[1]) & 8) != 0 && (v115 & 4) == 0
            || (v115 & 0x20) != 0 && ((v115 & 4) == 0 || (v115 & 0x40) != 0 && (v115 & 0x10) != 0) )
          {
            v116 = ((*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0) + 1;
            v108 = (2 * (~BYTE2(Bcb[1]) & 2)) | 1;
            v27 = 0;
          }
          else
          {
            v27 = 0;
            if ( (v115 & 0x20) == 0 || (v115 & 2) != 0 )
              goto LABEL_414;
            v116 = 508;
            v108 = 3;
          }
          v152 = v108;
          v151 = v116;
LABEL_414:
          if ( v116 )
          {
            NtfsReportDirNotify(
              (_DWORD)Context,
              v9,
              a4,
              (unsigned int)&v146,
              (unsigned __int16)v146 - LOWORD(Buf1[0]),
              0,
              v116,
              v108,
              *(_QWORD *)(v9 + 184),
              (__int64)Contexta[1]);
            v27 = 0;
          }
          if ( HIBYTE(Bcb[1]) )
          {
            v27 = 4;
            if ( (v116 & 4) == 0 || v108 != 3 )
              NtfsReportDirNotify(
                (_DWORD)Context,
                v9,
                a4,
                (unsigned int)&v146,
                (unsigned __int16)v146 - LOWORD(Buf1[0]),
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
        v20 = NtfsChangeStorageReserveId((_DWORD)Context, *(unsigned __int8 *)(*(_QWORD *)(v9 + 184) + 38LL), v131);
        v122 = v20;
        v108 = 0;
        if ( !v20 )
          goto LABEL_358;
LABEL_425:
        NtfsRenameCleanup(Contexta, v27, v28);
        if ( PoolWithTag )
          ExFreePoolWithTag(PoolWithTag, 0);
        if ( v147 )
          ExFreePoolWithTag(v147, 0);
        if ( v157[1] )
          ExFreePoolWithTag(v157[1], 0);
        if ( v163[1] )
          ExFreePoolWithTag(v163[1], 0);
        if ( v136 )
          ExFreePoolWithTag(v136, 0);
        if ( (unsigned __int64 *)v169[1].m128i_i64[1] != &v169[3].m128i_u64[1] )
          ExFreePoolWithTag((PVOID)v169[1].m128i_i64[1], 0);
        if ( v145 == (__m128i *)v170 && *((_OWORD **)&v170[1] + 1) != (_OWORD *)((char *)&v170[3] + 8) )
          ExFreePoolWithTag(*((PVOID *)&v170[1] + 1), 0);
        if ( SLOBYTE(Bcb[1]) < 0 )
        {
          ExAcquirePushLockSharedEx(a4 + 656, 0);
          _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v125 + 28LL));
          ExReleasePushLockEx(a4 + 656, 0);
        }
        if ( HIBYTE(Bcb[1]) && !(_BYTE)v127 )
          *((_DWORD *)Contexta[1] + 44) = HIDWORD(v127);
        if ( v20 != 259 && ((__int64)Bcb[1] & 8) != 0 )
          NtfsTeardownStructures((int)Context, v125[0], 0);
        if ( (BYTE3(Bcb[1]) & 1) != 0 && (v20 & 0x80000000) == 0 && v20 != 259 && v20 != 871 )
        {
          *((_DWORD *)Context + 92) = *(unsigned __int8 *)(*(_QWORD *)(v9 + 184) + 38LL);
          *((_DWORD *)Context + 93) = v131;
          *((_DWORD *)Context + 3) |= 4u;
        }
        return v20;
      }
      if ( (BYTE2(Bcb[1]) & 2) == 0 || (v128 & 4) != 0 )
      {
        if ( (BYTE2(Bcb[1]) & 2) == 0 )
        {
          HIDWORD(v127) = *((_DWORD *)Contexta[1] + 44);
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
        HIDWORD(v127) = *((_DWORD *)Contexta[1] + 44);
        v93 = *((_DWORD *)Contexta[1] + 44);
        if ( (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 176LL) & 0x180000) == 0x180000 )
        {
          *((_DWORD *)Contexta[1] + 44) = v93 | 0x180000;
        }
        else
        {
          if ( (v93 & 0x180000) == 0x180000 )
            *((_DWORD *)Contexta[1] + 44) = v93 & 0xFFE7FFFF;
          v94 = *((_DWORD *)Contexta[1] + 44);
          if ( (v94 & 0x180000) == 0
            && ((v94 & 0x10000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 176LL) & 0x180000) != 0x100000) )
          {
            *((_DWORD *)Contexta[1] + 44) = v94 | *(_DWORD *)(*(_QWORD *)(v9 + 184) + 176LL) & 0x180000;
          }
        }
        if ( *((_DWORD *)Contexta[1] + 44) != HIDWORD(v127) )
          goto LABEL_295;
      }
      if ( HIBYTE(Bcb[1]) )
      {
        v137 = 0x8000;
        *((_DWORD *)Contexta[1] + 1) |= 0x10u;
      }
      if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) == 0
        && *(int *)(a4 + 4) >= 0
        && (*(_DWORD *)(v165 + 80) & 0x20000) == 0 )
      {
        if ( v145 == v169 )
        {
          v170[0] = v169[0];
          v170[1] = v169[1];
          v170[2] = v169[2];
          v170[3] = v169[3];
          v170[4] = v169[4];
          v170[5] = v169[5];
          v170[6] = v169[6];
          v95 = (__m128i *)((char *)&v170[3] + 8);
          v96 = (__m128i *)_mm_srli_si128(v169[1], 8).m128i_u64[0];
          if ( v96 != (__m128i *)&v169[3].m128i_u64[1] )
            v95 = v96;
          *((_QWORD *)&v170[1] + 1) = v95;
          v97 = (__m128i *)&v170[2];
          v98 = (__m128i *)_mm_srli_si128(v169[0], 8).m128i_u64[0];
          if ( v98 != &v169[2] )
            v97 = v98;
          *((_QWORD *)&v170[0] + 1) = v97;
          v145 = (__m128i *)v170;
        }
        else if ( (unsigned __int64 *)v169[1].m128i_i64[1] != &v169[3].m128i_u64[1] )
        {
          ExFreePoolWithTag((PVOID)v169[1].m128i_i64[1], 0);
        }
        v169[0].m128i_i64[1] = (__int64)v169[2].m128i_i64;
        v169[1].m128i_i64[1] = (__int64)&v169[3].m128i_i64[1];
        v169[1].m128i_i32[0] = 3407872;
        v169[0].m128i_i32[0] = 1572864;
        v150 = 80;
        if ( (unsigned __int8)FsRtlFindInTunnelCacheEx(
                                a4 + 4720,
                                *(_QWORD *)(*(_QWORD *)(v9 + 184) + 8LL),
                                Buf1,
                                v169,
                                &v169[1]) )
        {
          LOBYTE(Bcb[1]) |= 0x40u;
          if ( ((__int64)Bcb[1] & 1) == 0 )
          {
            if ( LOBYTE(v171[9]) )
            {
              NtfsAcquireExclusiveScbEx(Context, *(_QWORD *)(a4 + 160), 0);
              LOBYTE(Bcb[1]) |= 1u;
            }
          }
        }
      }
      if ( v139 )
      {
        LODWORD(v164) = 1572864;
        *((_QWORD *)&v164 + 1) = &v172;
      }
      NtfsAddLink(
        (_DWORD)Context,
        Contexta[1],
        (__int64)v136,
        0,
        (__int64)v121,
        0,
        (unsigned __int64)&v164 & -(__int64)(v139 != 0),
        (unsigned __int64)v169 & -(__int64)(((__int64)Bcb[1] & 0x40) != 0),
        0);
      if ( ((__int64)Bcb[1] & 0x20) != 0
        && (v99 = BYTE1(Bcb[1]), v28 = 2, (BYTE1(Bcb[1]) & 2) != 0)
        && (BYTE1(Bcb[1]) & 4) != 0
        && ((__int64)Bcb[1] & 0x40) != 0
        && (*(_BYTE *)(*(_QWORD *)(v134 + 192) + 65LL) & 3) != 0
        && (v132 & 3) == 0 )
      {
        v100 = v121[0];
        if ( v121[0] == 2 && v169[0].m128i_i16[0] == LOWORD(Buf2[0]) )
        {
          v101 = memcmp((const void *)v169[0].m128i_i64[1], Buf2[1], v169[0].m128i_u16[0]);
          v102 = 0;
          if ( v101 )
            BYTE1(Bcb[1]) = v99 & 0xFB;
          v100 = v121[0];
          goto LABEL_328;
        }
      }
      else
      {
        v100 = v121[0];
      }
      v102 = 0;
LABEL_328:
      v103 = v130;
      if ( v139 )
      {
        v104 = *(_DWORD *)(v130 + 4);
        if ( v145 )
        {
          v106 = (v104 & 1) != 0
              && ((v104 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
          TxfAddLinkForRename(
            (_DWORD)Context,
            v123,
            v100,
            (__int64)v145,
            (__int64)v169,
            (__int64)&v164,
            v106,
            Contexta[1]);
        }
        else
        {
          v105 = (v104 & 1) != 0
              && ((v104 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v9 + 184) + 16LL) & 0x400) == 0);
          TxfAddHardLink((_DWORD)Context, (__int64)v169, (__int64)&v164, v105, Contexta[1]);
        }
      }
      if ( ((__int64)Bcb[1] & 0x40) != 0 )
      {
        NtfsSetTunneledData(Context, Contexta[1], v171, v102);
        *((_DWORD *)Contexta[1] + 46) |= 0x40u;
        *((_DWORD *)Contexta[1] + 1) |= 0x10u;
        if ( v121[0] == 2 )
          memmove(Buf1[1], (const void *)v169[0].m128i_i64[1], LOWORD(Buf1[0]));
      }
      *((_BYTE *)v136 + 65) = v121[0];
      if ( *(_QWORD *)&v125[2] != v9 )
        NtfsUpdateFcbTimestamps(*(_QWORD *)(v9 + 184), 2684354576LL);
      if ( (BYTE1(Bcb[1]) & 1) != 0 && !*((_QWORD *)&v146 + 1) )
      {
        v27 = LOWORD(Buf1[0]) + (unsigned int)*(unsigned __int16 *)(v103 + 32);
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
        v107 = LOWORD(Buf1[0]) + *(_WORD *)(v103 + 32);
        WORD1(v146) = v27;
        v147 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v27, 0x4646744Eu);
        v162 = v147;
        memmove(v147, *(const void **)(v130 + 24), *(unsigned __int16 *)(v130 + 32));
        memmove((char *)v147 + *(unsigned __int16 *)(v130 + 32), Buf1[1], LOWORD(Buf1[0]));
        *((_QWORD *)&v146 + 1) = v147;
        LOWORD(v146) = v107;
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
  v128 = v11;
  if ( (v11 & 0xFFFFFE00) == 0 )
    goto LABEL_7;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 3221225659LL, 993447);
  return 3221225659LL;
}

```

## disassembly

```asm
0x14024c8e4  mov     r11, rsp
0x14024c8e7  push    rbx
0x14024c8e8  push    rsi
0x14024c8e9  push    rdi
0x14024c8ea  push    r12
0x14024c8ec  push    r13
0x14024c8ee  push    r14
0x14024c8f0  push    r15
0x14024c8f2  sub     rsp, 3D0h
0x14024c8f9  mov     rax, cs:__security_cookie
0x14024c900  xor     rax, rsp
0x14024c903  mov     [rsp+408h+var_40], rax
0x14024c90b  mov     r13, r9
0x14024c90e  mov     [rsp+408h+Irp], r8
0x14024c916  mov     r12, rdx
0x14024c919  mov     [rsp+408h+var_218], rdx
0x14024c921  mov     rsi, rcx
0x14024c924  mov     [rsp+408h+var_1F0], rcx
0x14024c92c  mov     [rsp+408h+var_1F8], r9
0x14024c934  mov     r14, [rsp+408h+arg_20]
0x14024c93c  mov     [rsp+408h+var_260], r14
0x14024c944  mov     rdi, [rsp+408h+arg_28]
0x14024c94c  mov     [rsp+408h+var_338], rdi
0x14024c954  mov     rbx, [r8+0B8h]
0x14024c95b  xor     ecx, ecx
0x14024c95d  mov     r15d, ecx
0x14024c960  mov     [r11-2B0h], rcx
0x14024c967  mov     [r11-208h], rcx
0x14024c96e  xorps   xmm0, xmm0
0x14024c971  movups  xmmword ptr [rsp+408h+Buf1], xmm0
0x14024c979  xorps   xmm1, xmm1
0x14024c97c  movups  [rsp+408h+var_2C8], xmm1
0x14024c984  mov     [rsp+408h+var_388], cl
0x14024c98b  mov     [r11-308h], rcx
0x14024c992  mov     [rsp+408h+var_33C], cx
0x14024c99a  movups  xmmword ptr [rsp+408h+Buf2], xmm0
0x14024c9a2  movups  xmmword ptr [rsp+408h+var_270], xmm1
0x14024c9aa  movups  xmmword ptr [rsp+408h+var_238], xmm0
0x14024c9b2  mov     [r11-2F0h], rcx
0x14024c9b9  movups  [rsp+408h+var_228], xmm1
0x14024c9c1  xor     edx, edx; Val
0x14024c9c3  lea     r8d, [rcx+70h]; Size
0x14024c9c7  lea     rcx, [r11-188h]; void *
0x14024c9ce  call    memset
0x14024c9d3  xor     edx, edx; Val
0x14024c9d5  lea     r8d, [r15+50h]; Size
0x14024c9d9  lea     rcx, [rsp+408h+var_A8]; void *
0x14024c9e1  call    memset
0x14024c9e6  mov     [rsp+408h+var_2A4], r15d
0x14024c9ee  xor     edx, edx; Val
0x14024c9f0  lea     r8d, [r15+70h]; Size
0x14024c9f4  lea     rcx, [rsp+408h+var_118]; void *
0x14024c9fc  call    memset
0x14024ca01  mov     rax, cs:CLFS_LSN_NULL_EXT
0x14024ca08  mov     qword ptr [rsp+408h+plsn], rax
0x14024ca10  xorps   xmm0, xmm0
0x14024ca13  xor     eax, eax
0x14024ca15  movups  xmmword ptr [rsp+408h+Context], xmm0
0x14024ca1d  movups  xmmword ptr [rsp+408h+var_368], xmm0
0x14024ca25  movups  xmmword ptr [rsp+408h+Bcb], xmm0
0x14024ca2d  mov     [rsp+408h+var_348], rax
0x14024ca35  mov     rax, [rsi+70h]
0x14024ca39  mov     rax, [rax+18h]
0x14024ca3d  lea     ecx, [r15+0Ah]
0x14024ca41  mov     [rsp+408h+var_32C], ecx
0x14024ca48  cmp     [rbx+10h], ecx
0x14024ca4b  jnz     short loc_14024CA62
0x14024ca4d  xor     r10d, r10d
0x14024ca50  mov     edx, r10d
0x14024ca53  cmp     [rax], r10b
0x14024ca56  setnz   dl
0x14024ca59  mov     [rsp+408h+var_340], edx
0x14024ca60  jmp     short loc_14024CA9C
0x14024ca62  mov     edx, [rax]
0x14024ca64  mov     [rsp+408h+var_340], edx
0x14024ca6b  test    edx, 0FFFFFE00h
0x14024ca71  jz      short loc_14024CA99
0x14024ca73  mov     al, cs:NtfsStatusDebugFlags
0x14024ca79  test    al, al
0x14024ca7b  jz      short loc_14024CA8F
0x14024ca7d  mov     edx, 0C00000BBh
0x14024ca82  xor     ecx, ecx
0x14024ca84  mov     r8d, 0F28A7h
0x14024ca8a  call    NtfsStatusTraceAndDebugInternal
0x14024ca8f  mov     eax, 0C00000BBh
0x14024ca94  jmp     loc_14024F6C6
0x14024ca99  xor     r10d, r10d
0x14024ca9c  mov     ecx, edx
0x14024ca9e  mov     r8d, 2
0x14024caa4  and     ecx, r8d
0x14024caa7  mov     [rsp+408h+var_2D8], ecx
0x14024caae  jz      short loc_14024CADF
0x14024cab0  cmp     [r13+0C8h], r10
0x14024cab7  jnz     short loc_14024CADF
0x14024cab9  mov     al, cs:NtfsStatusDebugFlags
0x14024cabf  test    al, al
0x14024cac1  jz      short loc_14024CAD5
0x14024cac3  mov     edx, 0C000029Ch
0x14024cac8  xor     ecx, ecx
0x14024caca  mov     r8d, 0F28B1h
0x14024cad0  call    NtfsStatusTraceAndDebugInternal
0x14024cad5  mov     eax, 0C000029Ch
0x14024cada  jmp     loc_14024F6C6
0x14024cadf  mov     [rsp+408h+Context], rsi
0x14024cae7  mov     byte ptr [rsp+408h+Bcb+9], 58h ; 'X'
0x14024caef  mov     r11, [r14+0B8h]
0x14024caf6  mov     [rsp+408h+Context+8], r11
0x14024cafe  mov     rbx, [rbx+18h]
0x14024cb02  test    rbx, rbx
0x14024cb05  jnz     short loc_14024CB62
0x14024cb07  cmp     [rax+10h], r8d
0x14024cb0b  jb      short loc_14024CB62
0x14024cb0d  lea     rcx, [rax+14h]
0x14024cb11  cmp     word ptr [rcx], 3Ah ; ':'
0x14024cb15  jnz     short loc_14024CB62
0x14024cb17  mov     [rsp+408h+Buf1+8], rcx
0x14024cb1f  movzx   eax, word ptr [rax+10h]
0x14024cb23  mov     word ptr [rsp+408h+Buf1], ax
0x14024cb2b  mov     word ptr [rsp+408h+Buf1+2], ax
0x14024cb33  and     dl, 1
0x14024cb36  lea     rax, [rsp+408h+Buf1]
0x14024cb3e  mov     [rsp+408h+var_3D8], rax; __int64
0x14024cb43  mov     byte ptr [rsp+408h+PostIrpRoutine], dl; char
0x14024cb47  mov     [rsp+408h+CompletionRoutine], rdi; __int64
0x14024cb4c  mov     r9, r14
0x14024cb4f  mov     r8, r11
0x14024cb52  mov     rdx, r12
0x14024cb55  mov     rcx, rsi; int
0x14024cb58  call    NtfsStreamRename
0x14024cb5d  jmp     loc_14024F6C6
0x14024cb62  mov     eax, [rdi+4]
0x14024cb65  test    r8b, al
0x14024cb68  jz      loc_14024F6A6
0x14024cb6e  mov     rdx, [rdi+48h]
0x14024cb72  mov     [rsp+408h+var_320], rdx
0x14024cb7a  test    rdx, rdx
0x14024cb7d  jz      loc_14024F6A6
0x14024cb83  test    dword ptr [r11+4], 100h
0x14024cb8b  jnz     loc_14024F6A6
0x14024cb91  mov     r12d, [rdx+4]
0x14024cb95  mov     r14d, 1
0x14024cb9b  test    r14b, r12b
0x14024cb9e  jnz     loc_14024F5BC
0x14024cba4  mov     rax, [rdx+0C0h]
0x14024cbab  test    byte ptr [rax+41h], 3
0x14024cbaf  jz      short loc_14024CBC1
0x14024cbb1  mov     rax, [rdx+30h]
0x14024cbb5  mov     ecx, [rax+4]
0x14024cbb8  test    cl, 20h
0x14024cbbb  jnz     loc_14024F5BC
0x14024cbc1  mov     r12b, 20h ; ' '
0x14024cbc4  mov     r9d, [r11+0B0h]
0x14024cbcb  test    r9d, r9d
0x14024cbce  jns     loc_14024CC82
0x14024cbd4  mov     eax, [rsi+10h]
0x14024cbd7  bt      rax, 14h
0x14024cbdc  jb      loc_14024CC64
0x14024cbe2  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x14024cbe9  test    r12b, al
0x14024cbec  jz      short loc_14024CC64
0x14024cbee  mov     rdx, [r13+0F8h]
0x14024cbf5  movzx   eax, word ptr [rdx+6]
0x14024cbf9  mov     ecx, 40h ; '@'
0x14024cbfe  cmp     ax, cx
0x14024cc01  ja      short loc_14024CC08
0x14024cc03  test    r14b, al
0x14024cc06  jz      short loc_14024CC0B
0x14024cc08  mov     eax, r10d
0x14024cc0b  lea     rcx, [rdx+20h]
0x14024cc0f  movzx   edx, ax
0x14024cc12  shr     edx, 1
0x14024cc14  movzx   r10d, word ptr [r13+1EC0h]
0x14024cc1c  shr     r10d, 1
0x14024cc1f  mov     r8, gs:188h
0x14024cc28  mov     dword ptr [rsp+408h+var_3B8], r9d
0x14024cc2d  mov     rax, [r11+8]
0x14024cc31  mov     qword ptr [rsp+408h+var_3C0], rax
0x14024cc36  mov     qword ptr [rsp+408h+var_3C8], r11
0x14024cc3b  mov     qword ptr [rsp+408h+var_3D0], rcx
0x14024cc40  mov     dword ptr [rsp+408h+var_3D8], edx
0x14024cc44  mov     rax, [r13+1EC8h]
0x14024cc4b  mov     [rsp+408h+PostIrpRoutine], rax
0x14024cc50  mov     dword ptr [rsp+408h+CompletionRoutine], r10d
0x14024cc55  mov     r9, r13
0x14024cc58  lea     rdx, fileinfo_c10508
0x14024cc5f  call    McTemplateU0ppwwpid_EtwWriteTransfer
0x14024cc64  mov     al, cs:NtfsStatusDebugFlags
0x14024cc6a  test    al, al
0x14024cc6c  jz      loc_14024F69F
0x14024cc72  mov     edi, 0C0000022h
0x14024cc77  mov     r8d, 0F2919h
0x14024cc7d  jmp     loc_14024F6BB
0x14024cc82  mov     eax, [rsi+0Ch]
0x14024cc85  test    r14b, al
0x14024cc88  jnz     short loc_14024CCA5
0x14024cc8a  xor     r9d, r9d
0x14024cc8d  xor     r8d, r8d
0x14024cc90  mov     rdx, [rsp+408h+Irp]
0x14024cc98  mov     rcx, rsi; StartContext
0x14024cc9b  call    NtfsPostRequest
0x14024cca0  jmp     loc_14024F6C6
0x14024cca5  mov     edi, r10d
0x14024cca8  mov     [rsp+408h+var_384], r10d
0x14024ccb0  mov     [rsp+408h+var_300], r10d
0x14024ccb8  mov     rax, r10
0x14024ccbb  mov     [rsp+408h+var_2B8], rax
0x14024ccc3  mov     [rsp+408h+var_240], rax
0x14024cccb  mov     [rsp+408h+var_298], r10
0x14024ccd3  mov     [rsp+408h+var_2FC], r10d
0x14024ccdb  mov     [rsp+408h+var_2D0], r10
0x14024cce3  mov     [rsp+408h+var_380], r10b
0x14024cceb  mov     [rsp+408h+var_330], r10d
0x14024ccf3  mov     rcx, [rsp+408h+var_338]
0x14024ccfb  mov     eax, [rcx+64h]
0x14024ccfe  mov     [rsi+110h], eax
0x14024cd04  mov     rax, [rdx+18h]
0x14024cd08  mov     qword ptr [rsp+408h+var_368+8], rax
0x14024cd10  lea     rax, [rsp+408h+var_168]
0x14024cd18  mov     [rsp+408h+var_188+8], rax
0x14024cd20  lea     rax, [rsp+408h+var_150]
0x14024cd28  mov     [rsp+408h+P+8], rax
0x14024cd30  mov     dword ptr [rsp+408h+var_188], 180000h
0x14024cd3b  mov     dword ptr [rsp+408h+P], 340000h
0x14024cd46  mov     r8, [rsi+190h]
0x14024cd4d  mov     [rsp+408h+var_2F8], r8
0x14024cd55  test    byte ptr [rcx+4], 8
0x14024cd59  mov     eax, 58h ; 'X'
0x14024cd5e  lea     ecx, [rax+1]
0x14024cd61  cmovz   eax, ecx
0x14024cd64  mov     byte ptr [rsp+408h+Bcb+9], al
0x14024cd6b  mov     [rsp+408h+var_270+8], r10
0x14024cd73  mov     [rsp+408h+var_238+8], r10
0x14024cd7b  test    dword ptr [r11+0B0h], 10000000h
0x14024cd86  jz      loc_14024CEAF
0x14024cd8c  mov     rdx, [r11+148h]
0x14024cd93  test    rdx, rdx
0x14024cd96  jz      short loc_14024CDE6
0x14024cd98  mov     eax, [rdx+80h]
0x14024cd9e  test    eax, eax
0x14024cda0  jz      short loc_14024CDE6
0x14024cda2  test    r8, r8
0x14024cda5  jz      short loc_14024CDB8
0x14024cda7  cmp     eax, r14d
0x14024cdaa  jnz     short loc_14024CDB8
0x14024cdac  mov     rcx, r8
0x14024cdaf  call    TxfSearchNoRenameList
0x14024cdb4  test    al, al
0x14024cdb6  jnz     short loc_14024CDE6
0x14024cdb8  mov     al, cs:NtfsStatusDebugFlags
0x14024cdbe  test    al, al
0x14024cdc0  jz      short loc_14024CDD5
0x14024cdc2  mov     edx, 0C0190037h
0x14024cdc7  mov     r8d, 0F2959h
0x14024cdcd  mov     rcx, rsi
0x14024cdd0  call    NtfsStatusTraceAndDebugInternal
0x14024cdd5  mov     ecx, 0C0190037h; Status
0x14024cdda  call    cs:__imp_ExRaiseStatus
0x14024cde6  lea     rax, [rsp+408h+plsn]
0x14024cdee  mov     [rsp+408h+CompletionRoutine], rax; __int64
0x14024cdf3  mov     r8, [rsp+408h+var_260]
0x14024cdfb  mov     rdx, [rsp+408h+Irp]; Irp
0x14024ce03  mov     rcx, rsi; Context
0x14024ce06  call    NtfsProcessTreeForRename
0x14024ce0b  mov     edi, eax
0x14024ce0d  mov     [rsp+408h+var_384], eax
0x14024ce14  test    eax, eax
0x14024ce16  jnz     loc_14024D284
0x14024ce1c  mov     rax, [rsp+408h+var_2F8]
0x14024ce24  test    rax, rax
0x14024ce27  jz      short loc_14024CE31
0x14024ce29  lock or dword ptr [rax+10h], 10000h
0x14024ce31  lea     rcx, [rsp+408h+plsn]; plsn
0x14024ce39  call    cs:__imp_ClfsLsnNull
0x14024ce40  nop     dword ptr [rax+rax+00h]
0x14024ce45  test    al, al
0x14024ce47  jnz     short loc_14024CEAF
0x14024ce49  mov     byte ptr [rsp+408h+CompletionRoutine], r14b
0x14024ce4e  xor     r9d, r9d
0x14024ce51  xor     edx, edx
0x14024ce53  lea     r8d, [r9+5]
0x14024ce57  mov     rcx, [rsi+90h]
0x14024ce5e  call    TxfSearchAddTxfFcbCleanupList
0x14024ce63  mov     ecx, 8000h
0x14024ce68  or      [rax+10h], ecx
0x14024ce6b  mov     rcx, qword ptr [rsp+408h+plsn]
0x14024ce73  mov     [rax+28h], rcx
0x14024ce77  mov     rcx, [rsp+408h+Context+8]
0x14024ce7f  mov     rdx, [rcx+140h]
0x14024ce86  mov     [rax+20h], rdx
0x14024ce8a  lock add [rdx+40h], r14d
0x14024ce8f  mov     rax, [rax+20h]
0x14024ce93  lock add [rax+30h], r14d
0x14024ce98  mov     al, cs:NtfsStatusDebugFlags
0x14024ce9e  mov     ecx, 0C00000D8h; Status
0x14024cea3  call    cs:__imp_ExRaiseStatus
0x14024ceaf  lea     rax, [rsp+408h+Buf1]
0x14024ceb7  mov     [rsp+408h+var_3D8], rax
0x14024cebc  lea     rax, [rsp+408h+var_2C8]
0x14024cec4  mov     [rsp+408h+PostIrpRoutine], rax
0x14024cec9  lea     rax, [rsp+408h+var_208]
  ... truncated ...
```
