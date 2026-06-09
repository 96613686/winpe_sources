# NtfsSetRenameInfo

- ea: `0x14024c894`
- end: `0x14024f784`
- name: `NtfsSetRenameInfo`
- size: `12016`
- prototype: `__int64 __fastcall(CLFS_LSN *Context, __int64, IRP *, __int64, __int64, __int64)`
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
__int64 __fastcall NtfsSetRenameInfo(CLFS_LSN *Context, __int64 a2, IRP *a3, __int64 a4, __int64 a5, __int64 a6)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  __int64 v10; // r15
  int *v11; // rax
  int v12; // edx
  __int64 v14; // r11
  __int64 QuadPart; // rbx
  __int64 v16; // rdx
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned __int16 v19; // ax
  int v20; // edi
  unsigned int v21; // r8d
  __int64 v22; // rcx
  __int64 ullOffset; // r8
  char v24; // al
  unsigned __int64 v25; // rdx
  int v26; // eax
  CLFS_LSN *v27; // rax
  CLFS_LSN v28; // rdx
  unsigned int v29; // r8d
  __int64 v30; // r10
  int v31; // r11d
  __int64 v32; // r9
  unsigned __int16 v33; // cx
  unsigned __int16 v34; // ax
  __int64 v35; // r10
  unsigned __int16 v36; // cx
  unsigned __int16 v37; // ax
  __int64 v38; // rcx
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // rdi
  __int64 v43; // rbx
  int v44; // eax
  __int64 v45; // rdx
  unsigned int CurrentFileInfo; // eax
  __int64 v47; // rcx
  _WORD *v48; // rbx
  __int64 v49; // r10
  unsigned __int16 v50; // cx
  unsigned __int16 v51; // ax
  _QWORD *NextScb; // rax
  __int64 v53; // r10
  int v54; // ecx
  __int64 v55; // rcx
  char v56; // al
  char v57; // dl
  __int64 v58; // rcx
  int v59; // eax
  int v60; // eax
  __int64 v61; // rdx
  int v62; // ecx
  unsigned __int64 v63; // rdx
  __int64 v64; // r8
  int v65; // eax
  char v66; // al
  _QWORD *v67; // rbx
  int v68; // eax
  BOOL v69; // eax
  int v70; // eax
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
  unsigned int v82; // edx
  char *v83; // rbx
  char *v84; // rbx
  char *v85; // rcx
  int v86; // ebx
  int v87; // eax
  int v88; // eax
  __int64 *v89; // rax
  __int64 *v90; // rax
  __int64 v91; // rbx
  int v92; // r8d
  char v93; // cl
  int v94; // r8d
  int v95; // r8d
  int v96; // r8d
  __m128i *v97; // rdx
  __m128i *v98; // xmm1_8
  __m128i *v99; // rdx
  __m128i *v100; // xmm0_8
  int v101; // eax
  char v102; // r8
  char v103; // bl
  char v104; // dl
  __int64 v105; // rbx
  int v106; // ecx
  BOOL v107; // ecx
  BOOL v108; // ecx
  unsigned int v109; // edx
  __int16 v110; // bx
  int v111; // ebx
  unsigned int v112; // edx
  __int16 v113; // bx
  __int64 v114; // rax
  _WORD *v115; // rcx
  PVOID v116; // r8
  char v117; // cl
  _DWORD *v118; // rcx
  char v119; // cl
  int v120; // r12d
  int v121; // r9d
  __int64 v122; // r10
  unsigned __int16 v123; // r8
  __int64 v124; // rax
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+98h] [rbp-3E8h]
  PIRP v126; // [rsp+A8h] [rbp-3D8h]
  char v127[4]; // [rsp+F8h] [rbp-388h] BYREF
  int v128; // [rsp+FCh] [rbp-384h]
  char v129; // [rsp+100h] [rbp-380h]
  PVOID Contexta[2]; // [rsp+108h] [rbp-378h] BYREF
  int v131[4]; // [rsp+118h] [rbp-368h]
  PVOID Bcb[2]; // [rsp+128h] [rbp-358h] BYREF
  __int64 v133; // [rsp+138h] [rbp-348h]
  int v134; // [rsp+140h] [rbp-340h]
  _WORD v135[2]; // [rsp+144h] [rbp-33Ch] BYREF
  __int64 v136; // [rsp+148h] [rbp-338h]
  int v137; // [rsp+150h] [rbp-330h]
  int v138; // [rsp+154h] [rbp-32Ch] BYREF
  char v139; // [rsp+158h] [rbp-328h]
  __int64 v140; // [rsp+160h] [rbp-320h]
  void *Buf1[2]; // [rsp+168h] [rbp-318h] BYREF
  PVOID v142; // [rsp+178h] [rbp-308h] BYREF
  int v143; // [rsp+180h] [rbp-300h]
  int v144; // [rsp+184h] [rbp-2FCh]
  __int64 v145; // [rsp+188h] [rbp-2F8h]
  _QWORD *v146; // [rsp+190h] [rbp-2F0h] BYREF
  void *Src; // [rsp+198h] [rbp-2E8h] BYREF
  char v148; // [rsp+1A0h] [rbp-2E0h]
  int v149; // [rsp+1A4h] [rbp-2DCh]
  int v150; // [rsp+1A8h] [rbp-2D8h]
  __m128i *v151; // [rsp+1B0h] [rbp-2D0h]
  __m128i v152; // [rsp+1B8h] [rbp-2C8h] BYREF
  PVOID v153; // [rsp+1C8h] [rbp-2B8h]
  __int64 v154; // [rsp+1D0h] [rbp-2B0h] BYREF
  int v155; // [rsp+1D8h] [rbp-2A8h]
  int v156; // [rsp+1DCh] [rbp-2A4h] BYREF
  int v157; // [rsp+1E0h] [rbp-2A0h]
  int v158; // [rsp+1E4h] [rbp-29Ch]
  PVOID PoolWithTag; // [rsp+1E8h] [rbp-298h]
  void *Buf2[2]; // [rsp+1F0h] [rbp-290h] BYREF
  PIRP Irp; // [rsp+200h] [rbp-280h]
  __int64 v162; // [rsp+208h] [rbp-278h]
  PVOID v163[2]; // [rsp+210h] [rbp-270h] BYREF
  _WORD *v164; // [rsp+220h] [rbp-260h]
  __int64 v165; // [rsp+228h] [rbp-258h]
  CLFS_LSN plsn; // [rsp+230h] [rbp-250h] BYREF
  int v167; // [rsp+238h] [rbp-248h]
  PVOID v168; // [rsp+240h] [rbp-240h]
  PVOID v169[2]; // [rsp+248h] [rbp-238h] BYREF
  __int128 v170; // [rsp+258h] [rbp-228h] BYREF
  __int64 v171; // [rsp+268h] [rbp-218h]
  __int64 v172; // [rsp+270h] [rbp-210h]
  _QWORD v173[4]; // [rsp+278h] [rbp-208h] BYREF
  __int64 v174[12]; // [rsp+298h] [rbp-1E8h] BYREF
  __m128i v175[7]; // [rsp+2F8h] [rbp-188h] BYREF
  _OWORD v176[7]; // [rsp+368h] [rbp-118h] BYREF
  __int64 v177[10]; // [rsp+3D8h] [rbp-A8h] BYREF
  char v178; // [rsp+428h] [rbp-58h] BYREF

  Irp = a3;
  v171 = a2;
  v173[3] = Context;
  v173[2] = a4;
  v164 = (_WORD *)a5;
  v136 = a6;
  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  v10 = 0;
  v154 = 0;
  v173[0] = 0;
  *(_OWORD *)Buf1 = 0;
  v152 = 0;
  v127[0] = 0;
  v142 = 0;
  v135[0] = 0;
  *(_OWORD *)Buf2 = 0;
  *(_OWORD *)v163 = 0;
  *(_OWORD *)v169 = 0;
  v146 = 0;
  v170 = 0;
  memset(v175, 0, sizeof(v175));
  memset(v177, 0, sizeof(v177));
  v156 = 0;
  memset(v176, 0, sizeof(v176));
  plsn.ullOffset = CLFS_LSN_NULL_EXT;
  *(_OWORD *)Contexta = 0;
  *(_OWORD *)v131 = 0;
  *(_OWORD *)Bcb = 0;
  v133 = 0;
  v11 = *(int **)(Context[14].ullOffset + 24);
  v138 = 10;
  if ( CurrentStackLocation->Parameters.Create.Options == 10 )
  {
    LOBYTE(v12) = *(_BYTE *)v11 != 0;
    v134 = (unsigned __int8)v12;
LABEL_7:
    v150 = v12 & 2;
    if ( (v12 & 2) != 0 && !*(_QWORD *)(a4 + 200) )
    {
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(0, 0xC000029C, 0xF28B1u);
      return 3221226140LL;
    }
    Contexta[0] = Context;
    BYTE1(Bcb[1]) = 88;
    v14 = *(_QWORD *)(a5 + 184);
    Contexta[1] = (PVOID)v14;
    QuadPart = CurrentStackLocation->Parameters.Read.ByteOffset.QuadPart;
    if ( !QuadPart && (unsigned int)v11[4] >= 2 && *((_WORD *)v11 + 10) == 58 )
    {
      Buf1[1] = v11 + 5;
      LOWORD(Buf1[0]) = *((_WORD *)v11 + 8);
      WORD1(Buf1[0]) = Buf1[0];
      return NtfsStreamRename((__int64)Context, a2, v14, a5, a6, v12 & 1, (__int128 *)Buf1);
    }
    if ( (*(_DWORD *)(a6 + 4) & 2) == 0
      || (v16 = *(_QWORD *)(a6 + 72), (v140 = v16) == 0)
      || (*(_DWORD *)(v14 + 4) & 0x100) != 0 )
    {
      v20 = -1073741811;
      if ( NtfsStatusDebugFlags )
      {
        v21 = 993512;
        goto LABEL_469;
      }
      return (unsigned int)v20;
    }
    if ( (*(_DWORD *)(v16 + 4) & 1) != 0
      || (*(_BYTE *)(*(_QWORD *)(v16 + 192) + 65LL) & 3) != 0 && (*(_DWORD *)(*(_QWORD *)(v16 + 48) + 4LL) & 0x20) != 0 )
    {
      if ( (Context[2].offset.idxRecord & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v122 = *(_QWORD *)(a4 + 248);
        v123 = *(_WORD *)(v122 + 6);
        if ( v123 > 0x40u || (v123 & 1) != 0 )
          v123 = 0;
        v124 = *(_QWORD *)(v16 + 192);
        McTemplateU0ppwwpidpwdd_EtwWriteTransfer(
          *(unsigned __int8 *)(v124 + 65),
          v124 + 66,
          KeGetCurrentThread(),
          a4,
          *(unsigned __int16 *)(a4 + 7872) >> 1,
          *(_QWORD *)(a4 + 7880),
          v123 >> 1,
          v122 + 32,
          *(_QWORD *)(v16 + 48),
          *(_QWORD *)(*(_QWORD *)(v16 + 48) + 8LL),
          *(_DWORD *)(*(_QWORD *)(v16 + 48) + 4LL),
          v140,
          *(unsigned __int8 *)(v124 + 64) >> 1,
          v124 + 66,
          *(unsigned __int8 *)(v124 + 65),
          *(_DWORD *)(v16 + 4));
      }
      if ( NtfsStatusDebugFlags )
      {
        v20 = -1073741790;
        v21 = 993539;
        goto LABEL_469;
      }
      return (unsigned int)-1073741790;
    }
    v17 = *(unsigned int *)(v14 + 176);
    if ( (int)v17 < 0 )
    {
      if ( (Context[2].offset.idxRecord & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v18 = *(_QWORD *)(a4 + 248);
        v19 = *(_WORD *)(v18 + 6);
        if ( v19 > 0x40u || (v19 & 1) != 0 )
          v19 = 0;
        McTemplateU0ppwwpid_EtwWriteTransfer(
          v18 + 32,
          (const EVENT_DESCRIPTOR *)fileinfo_c10508,
          KeGetCurrentThread(),
          a4,
          *(unsigned __int16 *)(a4 + 7872) >> 1,
          *(_QWORD *)(a4 + 7880),
          v19 >> 1,
          v18 + 32,
          v14,
          *(_QWORD *)(v14 + 8),
          v17);
      }
      if ( NtfsStatusDebugFlags )
      {
        v20 = -1073741790;
        v21 = 993561;
LABEL_469:
        NtfsStatusTraceAndDebugInternal(0, v20, v21);
        return (unsigned int)v20;
      }
      return (unsigned int)-1073741790;
    }
    if ( (Context[1].offset.cidContainer & 1) == 0 )
      return NtfsPostRequest((char *)Context, Irp, 0, 0);
    v20 = 0;
    v128 = 0;
    v143 = 0;
    v153 = 0;
    v168 = 0;
    PoolWithTag = 0;
    v144 = 0;
    v151 = 0;
    v129 = 0;
    v137 = 0;
    v22 = v136;
    Context[34].offset.idxRecord = *(_DWORD *)(v136 + 100);
    *(_QWORD *)&v131[2] = *(_QWORD *)(v16 + 24);
    v175[0].m128i_i64[1] = (__int64)v175[2].m128i_i64;
    v175[1].m128i_i64[1] = (__int64)&v175[3].m128i_i64[1];
    v175[0].m128i_i32[0] = 1572864;
    v175[1].m128i_i32[0] = 3407872;
    ullOffset = Context[50].ullOffset;
    v145 = ullOffset;
    v24 = 88;
    if ( (*(_BYTE *)(v22 + 4) & 8) == 0 )
      v24 = 89;
    BYTE1(Bcb[1]) = v24;
    v163[1] = 0;
    v169[1] = 0;
    if ( (*(_DWORD *)(v14 + 176) & 0x10000000) != 0 )
    {
      v25 = *(_QWORD *)(v14 + 328);
      if ( v25 )
      {
        v26 = *(_DWORD *)(v25 + 128);
        if ( v26 )
        {
          if ( !ullOffset || v26 != 1 || !TxfSearchNoRenameList(ullOffset, v25) )
          {
            if ( NtfsStatusDebugFlags )
              NtfsStatusTraceAndDebugInternal((__int64)Context, 0xC0190037, 0xF2959u);
            ExRaiseStatus(-1072103369);
          }
        }
      }
      v20 = NtfsProcessTreeForRename(Context, Irp, (__int64)v164, v17, &plsn);
      v128 = v20;
      if ( v20 )
        goto LABEL_430;
      if ( v145 )
        _InterlockedOr((volatile signed __int32 *)(v145 + 16), 0x10000u);
      if ( !ClfsLsnNull(&plsn) )
      {
        v27 = (CLFS_LSN *)TxfSearchAddTxfFcbCleanupList(Context[18].ullOffset, 0, 5, 0, 1);
        v27[2].offset.idxRecord |= 0x8000u;
        v27[5] = plsn;
        v28 = *(CLFS_LSN *)((char *)Contexta[1] + 320);
        v27[4] = v28;
        _InterlockedAdd((volatile signed __int32 *)(v28.ullOffset + 64), 1u);
        _InterlockedAdd((volatile signed __int32 *)(v27[4].ullOffset + 48), 1u);
        ExRaiseStatus(-1073741608);
      }
    }
    NtfsFindTargetElements((__int64)Context, QuadPart, *(__int64 *)&v131[2], &v154, v173, (__int64)&v152, (__int64)Buf1);
    v10 = v154;
    if ( (_WORD *)v154 == v164 )
    {
      v20 = -1073741811;
      if ( NtfsStatusDebugFlags )
      {
        v29 = 993710;
LABEL_428:
        NtfsStatusTraceAndDebugInternal(0, v20, v29);
        goto LABEL_429;
      }
      goto LABEL_429;
    }
    if ( LOWORD(Buf1[0]) > 0x1FEu || !NtfsIsFileNameValid((unsigned __int16 *)Buf1, 0) )
    {
      v20 = -1073741773;
      if ( NtfsStatusDebugFlags )
      {
        v29 = 993721;
        goto LABEL_428;
      }
      goto LABEL_429;
    }
    v30 = *(_QWORD *)(v10 + 184);
    v31 = *(_DWORD *)(v30 + 4);
    if ( (v31 & 0x100) != 0 && v10 != *(_QWORD *)(a4 + 32) )
    {
      if ( (Context[2].offset.idxRecord & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v32 = *(_QWORD *)(a4 + 248);
        v33 = *(_WORD *)(v32 + 6);
        if ( v33 > 0x40u || (v33 & 1) != 0 )
        {
          v34 = 0;
          v144 = 0;
        }
        else
        {
          v34 = *(_WORD *)(v32 + 6);
          v144 = v34;
        }
        LOWORD(v173[0]) = v34;
        v173[1] = v32 + 32;
        LODWORD(v126) = v34 >> 1;
        LODWORD(CompletionRoutine) = *(unsigned __int16 *)(a4 + 7872) >> 1;
        McTemplateU0ppwwpid_EtwWriteTransfer(
          (unsigned int)v126,
          (const EVENT_DESCRIPTOR *)fileinfo_c10692,
          KeGetCurrentThread(),
          a4,
          CompletionRoutine,
          *(_QWORD *)(a4 + 7880),
          v126,
          v32 + 32,
          v30,
          *(_QWORD *)(v30 + 8),
          v31);
      }
      v20 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_429;
      v29 = 993745;
      goto LABEL_428;
    }
    if ( *(int *)(v30 + 176) < 0
      && (Context[54].offset.cidContainer & 0x80008) == 0
      && (_InterlockedCompareExchange((volatile signed __int32 *)(*(_QWORD *)(v30 + 320) + 132LL), 4, 4)
       || (int)TxfConvertMungedNameToTxfFileId(0, (__int64)Buf1, 0) < 0) )
    {
      if ( (Context[2].offset.idxRecord & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
      {
        v35 = *(_QWORD *)(a4 + 248);
        v36 = *(_WORD *)(v35 + 6);
        if ( v36 > 0x40u || (v36 & 1) != 0 )
        {
          v37 = 0;
          v143 = 0;
        }
        else
        {
          v37 = *(_WORD *)(v35 + 6);
          v143 = v37;
        }
        LOWORD(v171) = v37;
        v172 = v35 + 32;
        v38 = *(_QWORD *)(v10 + 184);
        LODWORD(v126) = v37 >> 1;
        LODWORD(CompletionRoutine) = *(unsigned __int16 *)(a4 + 7872) >> 1;
        McTemplateU0ppwwpidd_EtwWriteTransfer(
          v38,
          (const EVENT_DESCRIPTOR *)fileinfo_c10729,
          KeGetCurrentThread(),
          a4,
          CompletionRoutine,
          *(_QWORD *)(a4 + 7880),
          v126,
          v35 + 32,
          v38,
          *(_QWORD *)(v38 + 8),
          *(_DWORD *)(v38 + 176),
          *(_DWORD *)(v38 + 4));
      }
      v20 = -1073741790;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_429;
      v29 = 993783;
      goto LABEL_428;
    }
    v39 = *(_QWORD *)&v131[2];
    if ( *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v131[2] + 184LL) + 112LL) )
    {
      NtfsAcquirePagingResourceExclusive((__int64)Context, *(_QWORD *)(*(_QWORD *)&v131[2] + 184LL), 1u);
      LOBYTE(Bcb[1]) |= 2u;
      v39 = *(_QWORD *)&v131[2];
    }
    NtfsAcquireExclusiveScbEx((__int64)Context, v39, 0);
    if ( ((__int64)Bcb[1] & 2) == 0 )
    {
      v41 = *(_QWORD *)(*(_QWORD *)&v131[2] + 184LL);
      if ( *(_QWORD *)(v41 + 112) )
      {
        NtfsReleaseFcbEx((__int64)Context, v41, 0);
        NtfsAcquirePagingResourceExclusive((__int64)Context, *(_QWORD *)(*(_QWORD *)&v131[2] + 184LL), 1u);
        LOBYTE(Bcb[1]) |= 2u;
        NtfsAcquireExclusiveScbEx((__int64)Context, *(__int64 *)&v131[2], 0);
      }
    }
    if ( !*(_WORD *)(*(_QWORD *)&v131[2] + 656LL) )
      NtfsBuildNormalizedNameWithTxfIsolation(
        (__int64)Context,
        *(_QWORD *)(*(_QWORD *)&v131[2] + 184LL),
        *(__int64 *)&v131[2],
        0,
        0,
        0,
        (_QWORD *)(*(_QWORD *)&v131[2] + 656LL));
    if ( v145 )
    {
      v20 = TxfPrepareFileForPotentialTxLinkDelete((__int64)Context, (__int64 *)v140);
      v128 = v20;
      if ( v20 )
        goto LABEL_430;
    }
    if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 && !v164[328] )
      NtfsUpdateNormalizedName((__int64)Context, *(__int64 *)&v131[2], (__int64)v164, 0, 0);
    if ( v10 == *(_QWORD *)&v131[2] )
    {
      if ( LOWORD(Buf1[0]) == *(_WORD *)(v140 + 72) && !memcmp(Buf1[1], *(const void **)(v140 + 80), LOWORD(Buf1[0])) )
        goto LABEL_430;
    }
    else
    {
      if ( (Context[1].offset.cidContainer & 0x100) != 0 )
      {
        NtfsAcquireExclusiveScbEx((__int64)Context, v10, 0);
      }
      else
      {
        if ( !NtfsAcquireExclusiveFcb((__int64)Context, *(_QWORD *)(v10 + 184), v10, 66) )
        {
          Context[1].offset.cidContainer |= 0x100u;
          NtfsRaiseStatusInternal((__int64)Context, -1073741608, 0, 0, 993897);
        }
        if ( (*(_DWORD *)(v10 + 200) & 0x200) != 0 )
          NtfsSnapshotScb((__int64)Context, v10);
      }
      v45 = *(_QWORD *)(v10 + 184);
      if ( (*(_DWORD *)(v45 + 176) & 0x400) != 0 )
      {
        CurrentFileInfo = TxfGetCurrentFileInfo((__int64)Context, v45, 0, 0, 0);
        if ( !(unsigned __int8)RtlIsNonEmptyDirectoryReparsePointAllowed(CurrentFileInfo) )
        {
          v20 = -1073741183;
          if ( NtfsStatusDebugFlags )
          {
            v29 = 993935;
            goto LABEL_428;
          }
LABEL_429:
          v128 = v20;
          goto LABEL_430;
        }
      }
      if ( !*(_WORD *)(*(_QWORD *)(v10 + 184) + 188LL) )
      {
        v20 = -1073741738;
        if ( NtfsStatusDebugFlags )
        {
          v29 = 993948;
          goto LABEL_428;
        }
        goto LABEL_429;
      }
      BYTE2(Bcb[1]) |= 2u;
      if ( !*(_WORD *)(v10 + 656) )
      {
        if ( (Context[1].offset.cidContainer & 0x100) == 0
          && (Context[2].offset.idxRecord & 0x40000000) == 0
          && (*(_DWORD *)(Context[18].ullOffset + 16) & 0x40000000) == 0
          && !ExIsResourceAcquiredExclusiveLite((PERESOURCE)(a4 + 2160)) )
        {
          Context[1].offset.cidContainer |= 0x100u;
          NtfsRaiseStatusInternal((__int64)Context, -1073741608, 0, 0, 993973);
        }
        NtfsBuildNormalizedNameWithTxfIsolation(
          (__int64)Context,
          *(_QWORD *)(v10 + 184),
          v10,
          0,
          0,
          0,
          (_QWORD *)(v10 + 656));
      }
      v47 = *(unsigned int *)(v173[0] + 4LL);
      if ( (v47 & 8) != 0 && (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 )
      {
        v48 = v164;
        if ( (Context[1].offset.cidContainer & 0x100) != 0 )
        {
          NextScb = v164;
          while ( 1 )
          {
            NextScb = NtfsGetNextScb(v47, (__int64)NextScb, (__int64)v48, 0);
            if ( !NextScb )
              break;
            if ( NextScb == (_QWORD *)v10 )
            {
              if ( (!Context || (Context[2].offset.idxRecord & 0x100000) == 0)
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
              {
                v53 = *(_QWORD *)(a4 + 248);
                v54 = *(unsigned __int16 *)(v53 + 6);
                if ( (unsigned __int16)v54 > 0x40u || (v54 & 1) != 0 )
                  v54 = 0;
                v150 = v54;
                LOWORD(Irp) = v54;
                v162 = v53 + 32;
                v55 = (unsigned __int16)v54 >> 1;
                LODWORD(v126) = v55;
                LODWORD(CompletionRoutine) = *(unsigned __int16 *)(a4 + 7872) >> 1;
                McTemplateU0ppwwpii_EtwWriteTransfer(
                  v55,
                  *((_QWORD *)v48 + 23),
                  KeGetCurrentThread(),
                  a4,
                  CompletionRoutine,
                  *(_QWORD *)(a4 + 7880),
                  v126,
                  v53 + 32,
                  *((_QWORD *)v48 + 23),
                  *(_QWORD *)(*((_QWORD *)v48 + 23) + 8LL),
                  *(_QWORD *)(*(_QWORD *)(v10 + 184) + 8LL));
              }
              v20 = -1073741790;
              if ( NtfsStatusDebugFlags )
              {
                v29 = 994045;
                goto LABEL_428;
              }
              goto LABEL_429;
            }
          }
        }
        else if ( NtfsHasSubdirectory(v47, v164) )
        {
          if ( (Context[2].offset.idxRecord & 0x100000) == 0
            && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
          {
            v49 = *(_QWORD *)(a4 + 248);
            v50 = *(_WORD *)(v49 + 6);
            if ( v50 > 0x40u || (v50 & 1) != 0 )
            {
              v51 = 0;
              v134 = 0;
            }
            else
            {
              v51 = *(_WORD *)(v49 + 6);
              v134 = v51;
            }
            LOWORD(v164) = v51;
            v165 = v49 + 32;
            LODWORD(v126) = v51 >> 1;
            LODWORD(CompletionRoutine) = *(unsigned __int16 *)(a4 + 7872) >> 1;
            McTemplateU0ppwwpi_EtwWriteTransfer(
              *((_QWORD *)v48 + 23),
              (const EVENT_DESCRIPTOR *)fileinfo_c10972,
              KeGetCurrentThread(),
              a4,
              CompletionRoutine,
              *(_QWORD *)(a4 + 7880),
              v126,
              v49 + 32,
              *((_QWORD *)v48 + 23),
              *(_QWORD *)(*((_QWORD *)v48 + 23) + 8LL));
          }
          v20 = -1073741790;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_429;
          v29 = 994024;
          goto LABEL_428;
        }
      }
    }
    v42 = v140;
    v43 = v136;
    if ( (*(_BYTE *)(*(_QWORD *)(v140 + 192) + 65LL) & 3) != 0 && (*(_DWORD *)(v136 + 4) & 1) != 0 )
      BYTE2(Bcb[1]) |= 4u;
    v44 = *(_DWORD *)(v136 + 4);
    LOBYTE(v40) = (v44 & 1) != 0
               && ((v44 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 16LL) & 0x400) == 0);
    v56 = NtfsLookupEntry(
            (int)Context,
            v10,
            v40,
            (unsigned __int16 *)Buf1,
            &v142,
            v135,
            0,
            (__int64)&v146,
            (__int64)Bcb,
            0);
    v57 = (__int64)Bcb[1] & 0xDF | (32 * (v56 & 1));
    LOBYTE(Bcb[1]) = v57;
    if ( Context[3].offset.cidContainer )
    {
      NtfsCheckpointCurrentTransaction((__int64)Context);
      NtfsReleaseSharedResources((__int64)Context);
      NtfsReleaseExclusiveScbIfOwned((__int64)Context, *(_QWORD *)(a4 + 48));
      v57 = (char)Bcb[1];
    }
    if ( v145 )
    {
      v58 = *(_QWORD *)(v10 + 184);
      if ( *((_QWORD *)Contexta[1] + 40) != *(_QWORD *)(v58 + 320) )
      {
        if ( (v57 & 0x20) == 0
          || ((v138 = (int)Bcb[1], BYTE1(v138) = BYTE1(Bcb[1]) | 0x20, v59 = *(_DWORD *)(v43 + 4), (v59 & 1) == 0)
           || (v59 & 0x4000000) == 0 && (*(_DWORD *)(v58 + 16) & 0x400) != 0
            ? (v60 = 0)
            : (v60 = 1),
              (NtfsCheckLinkForRename(
                 (__int64)Contexta[1],
                 v42,
                 (__int64)(v146 + 2),
                 *v146,
                 (const void **)Buf1,
                 v60,
                 (__int64)&v138),
               (v138 & 0x2000) == 0)
           || (v138 & 0x200) != 0
           || (v134 & 1) != 0) )
        {
          if ( NtfsStatusDebugFlags )
            NtfsStatusTraceAndDebugInternal((__int64)Context, 0xC0190038, 0xF2BA5u);
          NtfsRaiseStatusInternal((__int64)Context, -1072103368, 0, 0, 994213);
        }
        v20 = -1073741771;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_429;
        v29 = 994201;
        goto LABEL_428;
      }
    }
    v20 = TxfCheckTargetForRename((__int64)Context, (__int64)Buf1, v10);
    v128 = v20;
    if ( v20 )
      goto LABEL_430;
    if ( v145 )
    {
      v61 = *(_QWORD *)(v10 + 184);
      v62 = *(_DWORD *)(v61 + 8);
      if ( v62 != 5 && *(_DWORD *)(*(_QWORD *)(v61 + 320) + 88LL) != v62 )
      {
        v63 = *(_QWORD *)(v61 + 328);
        if ( !v63 || *(_QWORD *)(v63 + 24) != v145 && !TxfSearchNoRenameList(v145, v63) )
        {
          TxfPrepareFileForTxfLogging(
            (__int64)Context,
            (void *)Context[50].ullOffset,
            *(_QWORD *)(v10 + 184),
            0,
            0,
            0,
            1,
            (Context[1].offset.cidContainer & 0x100) == 0);
          v146 = 0;
          if ( Bcb[0] )
          {
            CcUnpinData(Bcb[0]);
            Bcb[0] = 0;
          }
          v65 = *(_DWORD *)(v43 + 4);
          LOBYTE(v64) = (v65 & 1) != 0
                     && ((v65 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 16LL) & 0x400) == 0);
          v66 = NtfsLookupEntry(
                  (int)Context,
                  v10,
                  v64,
                  (unsigned __int16 *)Buf1,
                  &v142,
                  v135,
                  0,
                  (__int64)&v146,
                  (__int64)Bcb,
                  0);
          LOBYTE(Bcb[1]) = (__int64)Bcb[1] & 0xDF | (32 * (v66 & 1));
          if ( Context[3].offset.cidContainer )
          {
            NtfsCheckpointCurrentTransaction((__int64)Context);
            NtfsReleaseSharedResources((__int64)Context);
            NtfsReleaseExclusiveScbIfOwned((__int64)Context, *(_QWORD *)(a4 + 48));
          }
        }
      }
    }
    if ( ((__int64)Bcb[1] & 0x20) != 0 )
    {
      BYTE1(Bcb[1]) |= 0x20u;
      v67 = v146;
      v68 = *(_DWORD *)(v136 + 4);
      v69 = (v68 & 1) != 0 && ((v68 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 16LL) & 0x400) == 0);
      v70 = NtfsCheckLinkForRename(
              (__int64)Contexta[1],
              v140,
              (__int64)(v146 + 2),
              *v146,
              (const void **)Buf1,
              v69,
              (__int64)&Bcb[1]);
      v127[0] = *((_BYTE *)v67 + 81);
      LOBYTE(v70) = v127[0];
      v138 = v70;
      v148 = v127[0];
      v71 = v134;
      if ( (BYTE1(Bcb[1]) & 0x20) != 0 && (BYTE1(Bcb[1]) & 2) == 0 && (v134 & 1) == 0 )
      {
        v20 = -1073741771;
        if ( NtfsStatusDebugFlags )
        {
          v29 = 994370;
          goto LABEL_428;
        }
        goto LABEL_429;
      }
    }
    else
    {
      v71 = v134;
    }
    if ( (BYTE1(Bcb[1]) & 0x40) != 0 )
      NtfsCheckIndexForAddOrDelete(
        (__int64)Context,
        (__int64)Irp,
        *(_QWORD *)(v10 + 184),
        (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 ? 4 : 2,
        v136);
    if ( (BYTE2(Bcb[1]) & 2) != 0
      && *(_BYTE *)(*(_QWORD *)(v10 + 184) + 38LL) != *((_BYTE *)Contexta[1] + 38)
      && (v71 & 8) == 0 )
    {
      ExAcquireResourceExclusiveLite((PERESOURCE)(a4 + 10688), 1u);
      v72 = BYTE2(Bcb[1]) | 0x40;
      BYTE2(Bcb[1]) |= 0x40u;
      v73 = *((unsigned __int8 *)Contexta[1] + 38);
      if ( !(_BYTE)v73
        || (v74 = *(_QWORD *)(a4 + 8 * v73 + 10904)) == 0
        || (v75 = *(_DWORD *)(v74 + 4), (v75 & 4) == 0) && ((v75 & 0x10) == 0 || *((_WORD *)Contexta[1] + 94) == 1) )
      {
        v76 = *(unsigned __int8 *)(*(_QWORD *)(v10 + 184) + 38LL);
        if ( !(_BYTE)v76
          || (v77 = *(_QWORD *)(a4 + 8 * v76 + 10904)) == 0
          || (v78 = *(_DWORD *)(v77 + 4), (v78 & 8) == 0) && ((v78 & 0x20) == 0 || *((_WORD *)Contexta[1] + 94) == 1) )
        {
          BYTE2(Bcb[1]) = v72 | 0x80;
          v79 = v137;
          if ( (v134 & 0x10) != 0 )
            v79 = 1;
          v137 = v79;
          v149 = v79;
          if ( (v134 & 0x20) != 0 )
          {
            v79 |= 2u;
            v137 = v79;
            v149 = v79;
          }
          if ( (v134 & 0x80u) != 0 )
          {
            v79 |= 4u;
            v137 = v79;
            v149 = v79;
          }
          if ( (v134 & 0x100) != 0 )
          {
            v79 |= 8u;
            v137 = v79;
            v149 = v79;
          }
          if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 )
          {
            if ( !*(_BYTE *)(*(_QWORD *)(v10 + 184) + 38LL) )
            {
              v20 = NtfsChangeStorageReserveId((__int64)Context, (__int64)Irp, (__int64)Contexta[1], v136, 0, v79);
              v128 = v20;
              if ( !v20 )
              {
                ExReleaseResourceLite((PERESOURCE)(a4 + 10688));
                BYTE2(Bcb[1]) &= ~0x40u;
                NtfsCheckpointCurrentTransaction((__int64)Context);
                Context[46].offset.idxRecord = *(unsigned __int8 *)(*(_QWORD *)(v10 + 184) + 38LL);
                Context[46].offset.cidContainer = v137;
                Context[1].offset.cidContainer |= 4u;
                NtfsRaiseStatusInternal((__int64)Context, -1073741608, 0, 0, 994500);
              }
              goto LABEL_430;
            }
            BYTE3(Bcb[1]) |= 1u;
          }
        }
      }
      ExReleaseResourceLite((PERESOURCE)(a4 + 10688));
      BYTE2(Bcb[1]) &= ~0x40u;
    }
    if ( (*(_BYTE *)(*(_QWORD *)(v140 + 192) + 65LL) & 3) == 2 )
    {
      memset(v174, 0, 0x58u);
      Src = 0;
      NtfsLookupPrimaryLink((__int64)Context, (__int64)Contexta[1], v174, &Src);
      v80 = (unsigned __int8 *)Src;
      PoolWithTag = ExAllocatePoolWithTag(
                      (POOL_TYPE)(PoolType | 0x10),
                      2LL * *((unsigned __int8 *)Src + 64) + 66,
                      0x4646744Eu);
      memmove(PoolWithTag, v80, 2LL * v80[64] + 66);
      NtfsCleanupAttributeContext(v81, v174);
    }
    if ( ((__int64)Bcb[1] & 0x20) != 0 && (BYTE1(Bcb[1]) & 0x20) != 0 )
    {
      Src = v146 + 2;
      v82 = *(unsigned __int16 *)(v10 + 656) + 2 + 2 * *((unsigned __int8 *)v146 + 80);
      if ( v82 > 0xFFFE )
      {
        v20 = -1073741562;
        if ( NtfsStatusDebugFlags )
        {
          v29 = 994605;
          goto LABEL_428;
        }
        goto LABEL_429;
      }
      WORD1(v163[0]) = *(_WORD *)(v10 + 656) + 2 + 2 * *((unsigned __int8 *)v146 + 80);
      v83 = (char *)ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v82, 0x4646744Eu);
      v163[1] = v83;
      memmove(v83, *(const void **)(v10 + 664), *(unsigned __int16 *)(v10 + 656));
      v84 = &v83[*(unsigned __int16 *)(v10 + 656)];
      v154 = (__int64)v84;
      if ( v10 == *(_QWORD *)(a4 + 32) )
      {
        v85 = v84;
      }
      else
      {
        *(_WORD *)v84 = 92;
        v85 = v84 + 2;
        v84 = v85;
        v154 = (__int64)v85;
      }
      memmove(v85, (char *)Src + 66, 2LL * *((unsigned __int8 *)Src + 64));
      Buf2[1] = v84;
      LOWORD(Buf2[0]) = 2 * *((unsigned __int8 *)Src + 64);
      WORD1(Buf2[0]) = Buf2[0];
      LOWORD(v163[0]) = LOWORD(Buf2[0]) + (_WORD)v84 - LOWORD(v163[1]);
      if ( (BYTE1(Bcb[1]) & 2) != 0 )
      {
        *(PVOID *)v131 = Contexta[1];
        if ( v145 )
        {
          LOBYTE(v135[0]) = 1;
          v86 = 14;
          v155 = 14;
          v87 = *(_DWORD *)(v136 + 4);
          if ( (v87 & 1) != 0 && ((v87 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 16LL) & 0x400) == 0) )
            v155 = 15;
          Src = NtfsCreateLcb(
                  (__int64)Context,
                  v10,
                  (__int64)Contexta[1],
                  (const void **)Buf2,
                  *((_BYTE *)Src + 65),
                  (__int64)v135);
          v20 = TxfPrepareFileForPotentialTxLinkDelete((__int64)Context, (__int64 *)Src);
          v128 = v20;
          if ( v20 < 0 )
          {
            if ( NtfsStatusDebugFlags
              && (unsigned int)v20 < 0xFFFFFFED
              && v20 != -1073741802
              && (unsigned int)(v20 + 2147483643) > 1
              && v20 != -1073741807
              && v20 != -1073741608 )
            {
              NtfsStatusTraceAndDebugInternal((__int64)Context, v20, 0xF2D9Du);
            }
            ExRaiseStatus(v20);
          }
          if ( (BYTE1(Bcb[1]) & 8) != 0 )
          {
            TxfDeleteFile(Context, (__int64)Contexta[1], (__int64)Src, v155, (char *)&Bcb[1] + 6, 0, 0);
          }
          else
          {
            v151 = (__m128i *)v176;
            *((_QWORD *)&v176[0] + 1) = &v176[2];
            *((_QWORD *)&v176[1] + 1) = (char *)&v176[3] + 8;
            LODWORD(v176[0]) = 1572864;
            LODWORD(v176[1]) = 3407872;
            v129 = *(_BYTE *)(*((_QWORD *)Src + 24) + 65LL);
            v139 = v129;
            TxfRemoveLink((__int64)Context, (__int64)Contexta[1], (__int64)Src, v176, 0);
          }
LABEL_249:
          if ( Bcb[0] )
          {
            CcUnpinData(Bcb[0]);
            Bcb[0] = 0;
          }
          if ( (BYTE1(Bcb[1]) & 0x10) != 0 )
          {
            if ( (BYTE1(Bcb[1]) & 8) != 0 )
            {
              LOBYTE(v177[9]) = 0;
              if ( v145 )
              {
                v167 = 14;
                v88 = *(_DWORD *)(v136 + 4);
                if ( (v88 & 1) != 0
                  && ((v88 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 16LL) & 0x400) == 0) )
                {
                  v86 = 15;
                  v167 = 15;
                }
                if ( (BYTE1(Bcb[1]) & 0x40) != 0 )
                {
                  v151 = v175;
                  v129 = *(_BYTE *)(*(_QWORD *)(v140 + 192) + 65LL);
                  v139 = v129;
                  TxfRemoveLink((__int64)Context, (__int64)Contexta[1], v140, v175, 0);
                }
                else
                {
                  if ( *(int *)(a4 + 4) < 0 || (v89 = v177, (*(_DWORD *)(v171 + 80) & 0x20000) != 0) )
                    v89 = 0;
                  TxfDeleteFile(Context, (__int64)Contexta[1], v140, v86, (char *)&Bcb[1] + 6, v175, (__int64)v89);
                }
              }
              else
              {
                if ( *(int *)(a4 + 4) < 0 || (v90 = v177, (*(_DWORD *)(v171 + 80) & 0x20000) != 0) )
                  v90 = 0;
                NtfsRemoveLink(
                  (__int64)Context,
                  (__int64)Contexta[1],
                  *(__int64 *)&v131[2],
                  (const void **)(v140 + 72),
                  (__int64)v175,
                  (__int64)v90);
                ++WORD2(Bcb[1]);
              }
              v91 = v136;
              v92 = *(_DWORD *)(v136 + 4);
              if ( (v92 & 8) == 0
                && (*((_DWORD *)Contexta[1] + 44) & 0x10000000) == 0
                && *(int *)(a4 + 4) >= 0
                && (*(_DWORD *)(v171 + 80) & 0x20000) == 0 )
              {
                v93 = *(_BYTE *)(*(_QWORD *)(v140 + 192) + 65LL);
                v177[0] = *((_QWORD *)Contexta[1] + 16);
                BYTE1(v177[9]) = (v93 & 2) != 0;
                if ( (v92 & 0x4000000) != 0
                  || (v94 = 1, (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)&v131[2] + 184LL) + 16LL) & 0x400) == 0) )
                {
                  v94 = 0;
                }
                FsRtlAddToTunnelCacheEx(
                  a4 + 4720,
                  *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&v131[2] + 184LL) + 8LL),
                  v175,
                  &v175[1],
                  (2 * BYTE1(v177[9])) | v94,
                  80,
                  v177);
              }
            }
            else
            {
              v91 = v136;
            }
            if ( (BYTE1(Bcb[1]) & 1) != 0 )
            {
              v169[1] = ExAllocatePoolWithTag(
                          (POOL_TYPE)(PoolType | 0x10),
                          *(unsigned __int16 *)(v91 + 16),
                          0x4646744Eu);
              memmove(v169[1], *(const void **)(v91 + 24), *(unsigned __int16 *)(v91 + 16));
              LOWORD(v169[0]) = *(_WORD *)(v91 + 16);
              WORD1(v169[0]) = v169[0];
              v144 = *(unsigned __int16 *)(v91 + 32);
            }
          }
          if ( (BYTE1(Bcb[1]) & 0x40) == 0 )
          {
LABEL_359:
            if ( SBYTE2(Bcb[1]) >= 0 )
            {
              v111 = 0;
LABEL_363:
              if ( (*((_DWORD *)Contexta[1] + 1) & 0x10) != 0 )
                NtfsUpdateStandardInformation((__int64)Context, (__int64)Contexta[1], 0);
              if ( (BYTE1(Bcb[1]) & 2) != 0 )
              {
                if ( (BYTE1(Bcb[1]) & 0x20) != 0 )
                  BYTE1(Bcb[1]) |= 0x80u;
                else
                  BYTE2(Bcb[1]) |= 1u;
              }
              if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 && (BYTE1(Bcb[1]) & 0x40) != 0 )
                NtfsUpdateNormalizedName((__int64)Context, v10, (__int64)v164, (unsigned __int8 *)v142, 1);
              if ( v173[0] && (*(_DWORD *)(v173[0] + 4LL) & 8) != 0 )
              {
                v112 = *(unsigned __int16 *)(v10 + 656) + LOWORD(Buf1[0]) + 2;
                if ( v112 > 0xFFFE )
                {
                  v20 = -1073741562;
                  if ( NtfsStatusDebugFlags )
                  {
                    v29 = 995380;
                    goto LABEL_428;
                  }
                  goto LABEL_429;
                }
                v113 = *(_WORD *)(v10 + 656) + LOWORD(Buf1[0]) + 2;
                v152.m128i_i16[0] = v113;
                v152.m128i_i16[1] = v112;
                v153 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v112, 0x4646744Eu);
                v152.m128i_i64[1] = (__int64)v153;
                v168 = v153;
                memmove(v153, *(const void **)(v10 + 664), *(unsigned __int16 *)(v10 + 656));
                v114 = *(unsigned __int16 *)(v10 + 656);
                v115 = (char *)v153 + v114;
                v154 = (__int64)v153 + v114;
                if ( (_WORD)v114 == 2 )
                {
                  v152.m128i_i16[0] = v113 - 2;
                }
                else
                {
                  *v115++ = 92;
                  v154 = (__int64)v115;
                }
                memmove(v115, Buf1[1], LOWORD(Buf1[0]));
                v111 = 0;
              }
              v116 = v142;
              v117 = *((_BYTE *)v142 + 65) & 3;
              if ( (BYTE2(Bcb[1]) & 2) != 0 )
              {
                if ( v117 == 2 )
                  v116 = 0;
                NtfsMoveLinkToNewDir(
                  (__int64)Context,
                  &v152,
                  (const void **)Buf1,
                  v127[0],
                  v10,
                  (__int64)Contexta[1],
                  v143,
                  v140,
                  (int)Bcb[1],
                  (__int64)Buf2,
                  v138,
                  (__int64)PoolWithTag,
                  (__int64)v116);
                FsRtlCheckOplockEx((POPLOCK)(v10 + 88), Irp, 0x10u, 0, 0, 0);
              }
              else
              {
                if ( v117 == 2 )
                  v116 = 0;
                NtfsRenameLinkInDir(
                  (__int64)Context,
                  v131[2],
                  (__int64)Contexta[1],
                  v143,
                  v140,
                  (const void **)Buf1,
                  v127[0],
                  (int)Bcb[1],
                  (__int64)Buf2,
                  v138,
                  (__int64)PoolWithTag,
                  (__int64)v116);
              }
              LOBYTE(v133) = 1;
              Context[1].offset.cidContainer |= 0x2000000u;
              FsRtlCheckOplockEx((POPLOCK)(*(_QWORD *)&v131[2] + 88LL), Irp, 0x10u, 0, 0, 0);
              v118 = Contexta[1];
              if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0 && (BYTE1(Bcb[1]) & 0x40) != 0 )
              {
                NtfsUpdateNormalizedName((__int64)Context, v10, (__int64)v164, (unsigned __int8 *)v142, 0);
                v118 = Contexta[1];
              }
              if ( (BYTE1(Bcb[1]) & 0x10) != 0 )
              {
                NtfsUpdateFcbTimestamps(*(_QWORD *)(*(_QWORD *)&v131[2] + 184LL), -1610612720);
                v118 = Contexta[1];
              }
              NtfsUpdateFileTimestampsForChange((__int64)v118, v136, ~(v118[44] >> 6) & 0x400000);
              v119 = BYTE1(Bcb[1]);
              if ( (BYTE1(Bcb[1]) & 1) == 0 )
                goto LABEL_425;
              v120 = 0;
              v157 = 0;
              v158 = 0;
              if ( v163[1] && (BYTE1(Bcb[1]) & 0x20) != 0 )
              {
                if ( (BYTE2(Bcb[1]) & 8) == 0 && (BYTE1(Bcb[1]) & 4) == 0 )
                  goto LABEL_401;
                if ( (BYTE1(Bcb[1]) & 0x40) != 0 )
                {
                  if ( (BYTE1(Bcb[1]) & 0x10) == 0 )
                    goto LABEL_407;
                  if ( (BYTE2(Bcb[1]) & 0x20) == 0 )
                  {
LABEL_401:
                    NtfsReportDirNotify(
                      (__int64)Context,
                      v10,
                      a4,
                      (unsigned __int16 *)v163,
                      LOWORD(v163[0]) - LOWORD(Buf2[0]),
                      0,
                      ((*(_DWORD *)(*(_QWORD *)v131 + 176LL) & 0x10000000) != 0) + 1,
                      2,
                      *(_QWORD *)(v10 + 184),
                      *(__int64 *)v131);
                    v119 = BYTE1(Bcb[1]);
                  }
                }
              }
              if ( (v119 & 0x10) != 0 )
              {
                if ( (BYTE2(Bcb[1]) & 2) != 0 || (v121 = 4, (v119 & 0x40) == 0) )
                  v121 = 2;
                NtfsReportDirNotify(
                  (__int64)Context,
                  *(__int64 *)&v131[2],
                  a4,
                  (unsigned __int16 *)v169,
                  (unsigned __int16)v144,
                  0,
                  ((*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0) + 1,
                  v121,
                  *(_QWORD *)(*(_QWORD *)&v131[2] + 184LL),
                  (__int64)Contexta[1]);
                v119 = BYTE1(Bcb[1]);
              }
LABEL_407:
              if ( ((__int64)Bcb[1] & 0x20) == 0
                || (BYTE2(Bcb[1]) & 8) != 0 && (v119 & 4) == 0
                || (v119 & 0x20) != 0 && ((v119 & 4) == 0 || (v119 & 0x40) != 0 && (v119 & 0x10) != 0) )
              {
                v120 = ((*((_DWORD *)Contexta[1] + 44) & 0x10000000) != 0) + 1;
                v111 = (2 * (~BYTE2(Bcb[1]) & 2)) | 1;
              }
              else
              {
                if ( (v119 & 0x20) == 0 || (v119 & 2) != 0 )
                  goto LABEL_419;
                v120 = 508;
                v111 = 3;
              }
              v158 = v111;
              v157 = v120;
LABEL_419:
              if ( v120 )
                NtfsReportDirNotify(
                  (__int64)Context,
                  v10,
                  a4,
                  (unsigned __int16 *)&v152,
                  v152.m128i_u16[0] - LOWORD(Buf1[0]),
                  0,
                  v120,
                  v111,
                  *(_QWORD *)(v10 + 184),
                  (__int64)Contexta[1]);
              if ( HIBYTE(Bcb[1]) && ((v120 & 4) == 0 || v111 != 3) )
                NtfsReportDirNotify(
                  (__int64)Context,
                  v10,
                  a4,
                  (unsigned __int16 *)&v152,
                  v152.m128i_u16[0] - LOWORD(Buf1[0]),
                  0,
                  4,
                  3,
                  *(_QWORD *)(v10 + 184),
                  (__int64)Contexta[1]);
LABEL_425:
              *((_WORD *)Contexta[1] + 95) -= WORD2(Bcb[1]);
              *((_WORD *)Contexta[1] + 94) -= WORD2(Bcb[1]);
              goto LABEL_430;
            }
            v20 = NtfsChangeStorageReserveId(
                    (__int64)Context,
                    (__int64)Irp,
                    (__int64)Contexta[1],
                    v136,
                    *(unsigned __int8 *)(*(_QWORD *)(v10 + 184) + 38LL),
                    v137);
            v128 = v20;
            v111 = 0;
            if ( !v20 )
              goto LABEL_363;
LABEL_430:
            NtfsRenameCleanup((__int64)Contexta);
            if ( PoolWithTag )
              ExFreePoolWithTag(PoolWithTag, 0);
            if ( v153 )
              ExFreePoolWithTag(v153, 0);
            if ( v163[1] )
              ExFreePoolWithTag(v163[1], 0);
            if ( v169[1] )
              ExFreePoolWithTag(v169[1], 0);
            if ( v142 )
              ExFreePoolWithTag(v142, 0);
            if ( (unsigned __int64 *)v175[1].m128i_i64[1] != &v175[3].m128i_u64[1] )
              ExFreePoolWithTag((PVOID)v175[1].m128i_i64[1], 0);
            if ( v151 == (__m128i *)v176 && *((_OWORD **)&v176[1] + 1) != (_OWORD *)((char *)&v176[3] + 8) )
              ExFreePoolWithTag(*((PVOID *)&v176[1] + 1), 0);
            if ( SLOBYTE(Bcb[1]) < 0 )
            {
              ExAcquirePushLockSharedEx(a4 + 656, 0);
              _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)v131 + 28LL));
              ExReleasePushLockEx(a4 + 656, 0);
            }
            if ( HIBYTE(Bcb[1]) && !(_BYTE)v133 )
              *((_DWORD *)Contexta[1] + 44) = HIDWORD(v133);
            if ( v20 != 259 && ((__int64)Bcb[1] & 8) != 0 )
              NtfsTeardownStructures((__int64)Context, *(__int64 *)v131, 0, 0, 0);
            if ( (BYTE3(Bcb[1]) & 1) != 0 && v20 >= 0 && v20 != 259 && v20 != 871 )
            {
              Context[46].offset.idxRecord = *(unsigned __int8 *)(*(_QWORD *)(v10 + 184) + 38LL);
              Context[46].offset.cidContainer = v137;
              Context[1].offset.cidContainer |= 4u;
            }
            return (unsigned int)v20;
          }
          if ( (BYTE2(Bcb[1]) & 2) == 0 || (v134 & 4) != 0 )
          {
            if ( (BYTE2(Bcb[1]) & 2) != 0 )
              goto LABEL_297;
            HIDWORD(v133) = *((_DWORD *)Contexta[1] + 44);
            if ( (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 176LL) & 0x180000) == 0x180000
              || (*((_DWORD *)Contexta[1] + 44) & 0x180000) != 0x180000 )
            {
              goto LABEL_297;
            }
            *((_DWORD *)Contexta[1] + 44) &= 0xFFE7FFFF;
          }
          else
          {
            HIDWORD(v133) = *((_DWORD *)Contexta[1] + 44);
            v95 = *((_DWORD *)Contexta[1] + 44);
            if ( (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 176LL) & 0x180000) == 0x180000 )
            {
              *((_DWORD *)Contexta[1] + 44) = v95 | 0x180000;
            }
            else
            {
              if ( (v95 & 0x180000) == 0x180000 )
                *((_DWORD *)Contexta[1] + 44) = v95 & 0xFFE7FFFF;
              v96 = *((_DWORD *)Contexta[1] + 44);
              if ( (v96 & 0x180000) == 0
                && ((v96 & 0x10000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 176LL) & 0x180000) != 0x100000) )
              {
                *((_DWORD *)Contexta[1] + 44) = v96 | *(_DWORD *)(*(_QWORD *)(v10 + 184) + 176LL) & 0x180000;
              }
            }
            if ( *((_DWORD *)Contexta[1] + 44) == HIDWORD(v133) )
              goto LABEL_297;
          }
          HIBYTE(Bcb[1]) = 1;
LABEL_297:
          if ( HIBYTE(Bcb[1]) )
          {
            v143 = 0x8000;
            *((_DWORD *)Contexta[1] + 1) |= 0x10u;
          }
          if ( (*((_DWORD *)Contexta[1] + 44) & 0x10000000) == 0
            && *(int *)(a4 + 4) >= 0
            && (*(_DWORD *)(v171 + 80) & 0x20000) == 0 )
          {
            if ( v151 == v175 )
            {
              v176[0] = v175[0];
              v176[1] = v175[1];
              v176[2] = v175[2];
              v176[3] = v175[3];
              v176[4] = v175[4];
              v176[5] = v175[5];
              v176[6] = v175[6];
              v97 = (__m128i *)((char *)&v176[3] + 8);
              v98 = (__m128i *)_mm_srli_si128(v175[1], 8).m128i_u64[0];
              if ( v98 != (__m128i *)&v175[3].m128i_u64[1] )
                v97 = v98;
              *((_QWORD *)&v176[1] + 1) = v97;
              v99 = (__m128i *)&v176[2];
              v100 = (__m128i *)_mm_srli_si128(v175[0], 8).m128i_u64[0];
              if ( v100 != &v175[2] )
                v99 = v100;
              *((_QWORD *)&v176[0] + 1) = v99;
              v151 = (__m128i *)v176;
            }
            else if ( (unsigned __int64 *)v175[1].m128i_i64[1] != &v175[3].m128i_u64[1] )
            {
              ExFreePoolWithTag((PVOID)v175[1].m128i_i64[1], 0);
            }
            v175[0].m128i_i64[1] = (__int64)v175[2].m128i_i64;
            v175[1].m128i_i64[1] = (__int64)&v175[3].m128i_i64[1];
            v175[1].m128i_i32[0] = 3407872;
            v175[0].m128i_i32[0] = 1572864;
            v156 = 80;
            if ( (*(_DWORD *)(v136 + 4) & 0x4000000) != 0
              || (v101 = 1, (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 16LL) & 0x400) == 0) )
            {
              v101 = 0;
            }
            if ( (unsigned __int8)FsRtlFindInTunnelCacheEx(
                                    a4 + 4720,
                                    *(_QWORD *)(*(_QWORD *)(v10 + 184) + 8LL),
                                    Buf1,
                                    v175,
                                    &v175[1],
                                    v101,
                                    &v156,
                                    v177) )
            {
              LOBYTE(Bcb[1]) |= 0x40u;
              if ( ((__int64)Bcb[1] & 1) == 0 )
              {
                if ( LOBYTE(v177[9]) )
                {
                  NtfsAcquireExclusiveScbEx((__int64)Context, *(_QWORD *)(a4 + 160), 0);
                  LOBYTE(Bcb[1]) |= 1u;
                }
              }
            }
          }
          if ( v145 )
          {
            LODWORD(v170) = 1572864;
            *((_QWORD *)&v170 + 1) = &v178;
          }
          v102 = BYTE1(v177[9]);
          if ( ((__int64)Bcb[1] & 0x40) == 0 )
            v102 = 0;
          NtfsAddLink(
            (__int64)Context,
            (BYTE2(Bcb[1]) & 4) != 0,
            v102,
            v10,
            (__int64)Contexta[1],
            (__int64)v142,
            0,
            v127,
            0,
            (unsigned __int64)&v170 & -(__int64)(v145 != 0),
            (unsigned __int64)v175 & -(__int64)(((__int64)Bcb[1] & 0x40) != 0),
            0);
          if ( ((__int64)Bcb[1] & 0x20) != 0
            && (v103 = BYTE1(Bcb[1]), (BYTE1(Bcb[1]) & 2) != 0)
            && (BYTE1(Bcb[1]) & 4) != 0
            && ((__int64)Bcb[1] & 0x40) != 0
            && (*(_BYTE *)(*(_QWORD *)(v140 + 192) + 65LL) & 3) != 0
            && (v138 & 3) == 0 )
          {
            v104 = v127[0];
            if ( v127[0] == 2 && v175[0].m128i_i16[0] == LOWORD(Buf2[0]) )
            {
              if ( memcmp((const void *)v175[0].m128i_i64[1], Buf2[1], v175[0].m128i_u16[0]) )
                BYTE1(Bcb[1]) = v103 & 0xFB;
              v104 = v127[0];
            }
          }
          else
          {
            v104 = v127[0];
          }
          v105 = v136;
          if ( v145 )
          {
            v106 = *(_DWORD *)(v136 + 4);
            if ( v151 )
            {
              v108 = (v106 & 1) != 0
                  && ((v106 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 16LL) & 0x400) == 0);
              TxfAddLinkForRename(
                Context,
                *(_QWORD **)&v131[2],
                (_QWORD *)v10,
                (__int64)v142,
                v129,
                v104,
                (__int64)v151,
                (__int64)v175,
                (__int16 *)&v170,
                v108,
                (__int64)Contexta[1]);
            }
            else
            {
              v107 = (v106 & 1) != 0
                  && ((v106 & 0x4000000) != 0 || (*(_DWORD *)(*(_QWORD *)(v10 + 184) + 16LL) & 0x400) == 0);
              TxfAddHardLink(
                (__int64)Context,
                v10,
                (__int64)v142,
                v104,
                (__int64)v175,
                (__int16 *)&v170,
                v107,
                (__int64)Contexta[1]);
            }
          }
          if ( ((__int64)Bcb[1] & 0x40) != 0 )
          {
            NtfsSetTunneledData((int)Context, (__int64)Contexta[1], (__int64)v177);
            *((_DWORD *)Contexta[1] + 46) |= 0x40u;
            *((_DWORD *)Contexta[1] + 1) |= 0x10u;
            if ( v127[0] == 2 )
              memmove(Buf1[1], (const void *)v175[0].m128i_i64[1], LOWORD(Buf1[0]));
          }
          *((_BYTE *)v142 + 65) = v127[0];
          if ( *(_QWORD *)&v131[2] != v10 )
            NtfsUpdateFcbTimestamps(*(_QWORD *)(v10 + 184), -1610612720);
          if ( (BYTE1(Bcb[1]) & 1) != 0 && !v152.m128i_i64[1] )
          {
            v109 = LOWORD(Buf1[0]) + *(unsigned __int16 *)(v105 + 32);
            if ( v109 > 0xFFFE )
            {
              v20 = -1073741562;
              if ( NtfsStatusDebugFlags )
              {
                v29 = 995252;
                goto LABEL_428;
              }
              goto LABEL_429;
            }
            v110 = LOWORD(Buf1[0]) + *(_WORD *)(v105 + 32);
            v152.m128i_i16[1] = v109;
            v153 = ExAllocatePoolWithTag((POOL_TYPE)(PoolType | 0x10), (unsigned __int16)v109, 0x4646744Eu);
            v168 = v153;
            memmove(v153, *(const void **)(v136 + 24), *(unsigned __int16 *)(v136 + 32));
            memmove((char *)v153 + *(unsigned __int16 *)(v136 + 32), Buf1[1], LOWORD(Buf1[0]));
            v152.m128i_i64[1] = (__int64)v153;
            v152.m128i_i16[0] = v110;
          }
          --WORD2(Bcb[1]);
          goto LABEL_359;
        }
        NtfsRemoveLink((__int64)Context, (__int64)Contexta[1], v10, (const void **)Buf2, 0, 0);
        ++WORD2(Bcb[1]);
      }
      else
      {
        v20 = NtfsRemoveSupersededTarget(
                Context,
                v145,
                v10,
                v146,
                (__int64)Src,
                (_DWORD *)Contexta[1],
                Irp,
                v136,
                v150 != 0,
                (v134 & 0x40) != 0,
                (const void **)Buf2,
                (__int64)Contexta);
        v128 = v20;
        if ( v20 )
          goto LABEL_430;
      }
    }
    v86 = 14;
    goto LABEL_249;
  }
  v12 = *v11;
  v134 = v12;
  if ( (v12 & 0xFFFFFE00) == 0 )
    goto LABEL_7;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC00000BB, 0xF28A7u);
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
