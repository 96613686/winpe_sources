# NtfsReadRawEncrypted

- ea: `0x1402836cc`
- end: `0x140284f05`
- name: `NtfsReadRawEncrypted`
- size: `6201`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x1400055f0`
- `0x140007ea0`
- `0x1400082b0`
- `0x140009710`
- `0x14000c290`
- `0x14000cb80`
- `0x140015b90`
- `0x140025830`
- `0x14002b680`
- `0x140030418`
- `0x140037db4`
- `0x14003ebc4`
- `0x140059250`
- `0x1400592c0`
- `0x1400592e0`
- `0x1400596c0`
- `0x1400bdc7c`
- `0x1400bdd18`
- `0x1400bdd54`
- `0x1400bddcc`
- `0x1400bde2c`
- `0x1400bde74`
- `0x1400bdebc`
- `0x1400bdf00`
- `0x140160be0`
- `0x140175a80`
- `0x1401c08b4`
- `0x1402836cc`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140284b97`
- `ntoskrnl!IoFreeIrp` at `0x140284ce1`
- `ntoskrnl!IoFreeIrp` at `0x1402bc841`
- `ntoskrnl!IoFreeIrp` at `0x140284b97`
- `ntoskrnl!IoFreeIrp` at `0x140284ce1`
- `ntoskrnl!IoFreeIrp` at `0x1402bc841`
- `ntoskrnl!IoFreeMdl` at `0x140284b80`
- `ntoskrnl!IoFreeMdl` at `0x140284cd2`
- `ntoskrnl!IoFreeMdl` at `0x1402bc831`
- `ntoskrnl!IoFreeMdl` at `0x140284b80`
- `ntoskrnl!IoFreeMdl` at `0x140284cd2`
- `ntoskrnl!IoFreeMdl` at `0x1402bc831`
- `ntoskrnl!MmUnlockPages` at `0x140284b5f`
- `ntoskrnl!MmUnlockPages` at `0x140284cc2`
- `ntoskrnl!MmUnlockPages` at `0x1402bc820`
- `ntoskrnl!MmUnlockPages` at `0x140284b5f`
- `ntoskrnl!MmUnlockPages` at `0x140284cc2`
- `ntoskrnl!MmUnlockPages` at `0x1402bc820`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140284780`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x140284780`
- `ntoskrnl!ProbeForWrite` at `0x140283b1f`
- `ntoskrnl!ProbeForWrite` at `0x140283b1f`
- `ntoskrnl!ProbeForRead` at `0x140283b03`
- `ntoskrnl!ProbeForRead` at `0x140283b03`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140283ba0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140283ba0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140284d0a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc869`
- `ntoskrnl!ExReleaseResourceLite` at `0x140284d0a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc869`
- `ntoskrnl!CcFlushCache` at `0x140284401`
- `ntoskrnl!CcFlushCache` at `0x140284401`

## pseudocode

```c
__int64 __fastcall NtfsReadRawEncrypted(__int64 a1, __int64 a2)
{
  char v4; // r12
  __int64 v5; // r9
  __int64 v6; // rbx
  union _LARGE_INTEGER *v7; // rax
  union _LARGE_INTEGER v8; // rcx
  union _LARGE_INTEGER v9; // r13
  __int64 v10; // rsi
  int v11; // eax
  __int64 v12; // r15
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // r8
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned __int16 v19; // r8
  unsigned int v20; // esi
  __int64 v21; // r9
  union _LARGE_INTEGER *v22; // r15
  unsigned int v23; // esi
  unsigned int v24; // eax
  __int64 ULong64FromUser; // rdi
  __int64 v26; // rbx
  __int64 v27; // rcx
  union _LARGE_INTEGER v28; // r8
  LONGLONG i; // rdx
  __int64 v30; // r8
  __int64 QuadPart; // r13
  __int64 v32; // r11
  int v33; // r10d
  __int16 v34; // cx
  int v35; // eax
  char v36; // dl
  ULONG m; // eax
  unsigned int v38; // eax
  ULONG_PTR v39; // rcx
  struct _IO_STATUS_BLOCK *v40; // rbx
  __int16 v41; // ax
  _WORD *v42; // rcx
  union _LARGE_INTEGER v43; // r8
  __int64 v44; // rbx
  char v45; // di
  ULONG k; // eax
  __int64 v47; // r8
  unsigned __int64 v48; // rdx
  char v49; // r9
  _WORD *v50; // rcx
  int v51; // ecx
  __int64 v52; // r8
  LONGLONG v53; // r8
  unsigned int v54; // edi
  _DWORD *v55; // rbx
  struct _IO_STATUS_BLOCK *v56; // rdi
  __int64 v57; // rdx
  __int64 v58; // rbx
  union _LARGE_INTEGER *v59; // rcx
  DWORD ULongFromUser; // eax
  int v61; // eax
  __int16 v62; // cx
  char v63; // al
  __int64 v64; // rdi
  LONGLONG v65; // r9
  LONGLONG v66; // rax
  __int64 v67; // rbx
  char v68; // bl
  ULONG j; // eax
  ULONG v70; // r9d
  PIRP v71; // rax
  ULONG v72; // ebx
  PIRP v73; // rbx
  unsigned int Information; // ebx
  LONGLONG v75; // r8
  union _LARGE_INTEGER v76; // rcx
  __int64 v77; // r9
  union _LARGE_INTEGER v78; // r8
  DWORD v79; // r10d
  ULONG_PTR v80; // r8
  unsigned int v81; // ecx
  union _LARGE_INTEGER v82; // rcx
  int v83; // eax
  PIRP v84; // rbx
  struct _MDL *MdlAddress; // rcx
  unsigned int v86; // ecx
  __int64 v87; // r9
  PIRP v88; // rdi
  struct _MDL *v89; // rcx
  unsigned int StartingOffset; // [rsp+20h] [rbp-208h]
  char v91; // [rsp+71h] [rbp-1B7h]
  char v92; // [rsp+72h] [rbp-1B6h]
  char v93; // [rsp+72h] [rbp-1B6h]
  char v94; // [rsp+73h] [rbp-1B5h]
  char v95; // [rsp+74h] [rbp-1B4h]
  char v96; // [rsp+75h] [rbp-1B3h]
  char IsRangeAllocated; // [rsp+76h] [rbp-1B2h]
  union _LARGE_INTEGER FileOffset; // [rsp+78h] [rbp-1B0h] BYREF
  int v99; // [rsp+80h] [rbp-1A8h]
  unsigned int v100; // [rsp+84h] [rbp-1A4h]
  int v101; // [rsp+88h] [rbp-1A0h]
  ULONG v102[2]; // [rsp+90h] [rbp-198h]
  SIZE_T Size; // [rsp+98h] [rbp-190h]
  DWORD v104; // [rsp+A0h] [rbp-188h]
  unsigned int Length; // [rsp+A4h] [rbp-184h]
  ULONG Length_4; // [rsp+A8h] [rbp-180h]
  DWORD v107; // [rsp+ACh] [rbp-17Ch]
  unsigned int v108; // [rsp+B0h] [rbp-178h]
  __int64 v109; // [rsp+B8h] [rbp-170h]
  ULONG v110[2]; // [rsp+C0h] [rbp-168h]
  __int64 v111; // [rsp+C8h] [rbp-160h]
  int v112; // [rsp+D0h] [rbp-158h]
  unsigned int v113; // [rsp+D4h] [rbp-154h]
  int v114; // [rsp+D8h] [rbp-150h]
  unsigned int v115; // [rsp+DCh] [rbp-14Ch]
  char v116; // [rsp+E0h] [rbp-148h]
  struct _IO_STATUS_BLOCK *v117; // [rsp+E8h] [rbp-140h]
  PSECTION_OBJECT_POINTERS *v118; // [rsp+F0h] [rbp-138h]
  union _LARGE_INTEGER v119; // [rsp+F8h] [rbp-130h]
  PIRP Irp; // [rsp+100h] [rbp-128h]
  volatile void *Address; // [rsp+108h] [rbp-120h]
  signed __int64 v122; // [rsp+110h] [rbp-118h]
  LONGLONG v123; // [rsp+118h] [rbp-110h]
  __int64 v124; // [rsp+120h] [rbp-108h]
  union _LARGE_INTEGER v125; // [rsp+128h] [rbp-100h]
  DWORD v126; // [rsp+130h] [rbp-F8h]
  DWORD v127; // [rsp+134h] [rbp-F4h]
  signed __int64 v128; // [rsp+138h] [rbp-F0h]
  __int64 v129; // [rsp+140h] [rbp-E8h]
  signed __int64 v130; // [rsp+148h] [rbp-E0h]
  __int64 v131; // [rsp+150h] [rbp-D8h]
  __int64 v132; // [rsp+158h] [rbp-D0h] BYREF
  __int64 v133; // [rsp+160h] [rbp-C8h]
  _DWORD v134[24]; // [rsp+170h] [rbp-B8h] BYREF
  _DWORD Src[2]; // [rsp+1D0h] [rbp-58h] BYREF
  __int128 v136; // [rsp+1D8h] [rbp-50h]
  __int64 v137; // [rsp+1E8h] [rbp-40h]

  v117 = (struct _IO_STATUS_BLOCK *)a2;
  v109 = a1;
  v4 = 0;
  FileOffset.QuadPart = 0;
  v129 = 0;
  v114 = 0;
  memset(v134, 0, 0x5Cu);
  *(_DWORD *)(a1 + 12) |= 1u;
  v6 = *(_QWORD *)(a2 + 184);
  v7 = *(union _LARGE_INTEGER **)(v6 + 48);
  v118 = (PSECTION_OBJECT_POINTERS *)v7;
  v8 = v7[3];
  v125 = v8;
  if ( v8.QuadPart )
  {
    v9 = v7[4];
    v10 = *(_QWORD *)(v8.QuadPart + 192);
    v111 = v10;
    v11 = *(_DWORD *)(v10 + 4);
    if ( (v11 & 1) == 0 && (!v9.QuadPart || *(_BYTE *)(v9.QuadPart + 88) != 4 || (v11 & 2) == 0) )
    {
      NtfsRaiseStatusInternal(a1, -1073741202, 0, 0, 0);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v109, 3221225704LL, 1197282);
      NtfsRaiseStatusInternal(v109, -1073741592, 0, 0, 1197282);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v109, 3221225704LL, 1198114);
      NtfsRaiseStatusInternal(v109, -1073741592, 0, 0, 1198114);
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal(v109, 3221225704LL, 1196994);
      NtfsRaiseStatusInternal(v109, -1073741592, 0, 0, 1196994);
      JUMPOUT(0x140284F05LL);
    }
    if ( !v9.QuadPart )
      goto LABEL_10;
    v12 = *(_QWORD *)(v8.QuadPart + 184);
    v13 = *(unsigned __int8 *)(v9.QuadPart + 88);
  }
  else
  {
    v10 = 0;
    v111 = 0;
    v9.QuadPart = 0;
    v12 = 0;
    v13 = 1;
  }
  v131 = v12;
  v124 = v12;
  if ( v13 != 2 )
  {
LABEL_10:
    v14 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225485LL, 1196885);
    LOBYTE(v5) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225485LL, v5, 0);
    if ( !NtfsStatusDebugFlags )
      return v14;
    v15 = 1196886;
LABEL_14:
    NtfsStatusTraceAndDebugInternal(0, v14, v15);
    return v14;
  }
  if ( !_bittest16((const signed __int16 *)(v8.QuadPart + 460), 0xEu) )
  {
    v14 = -1073740633;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226663LL, 1196896);
    LOBYTE(v5) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221226663LL, v5, 0);
    if ( !NtfsStatusDebugFlags )
      return v14;
    v15 = 1196897;
    goto LABEL_14;
  }
  v17 = *(unsigned __int16 *)(v9.QuadPart + 104);
  if ( (v17 & 9) == 0 )
  {
    if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
      && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      v18 = *(_QWORD *)(v10 + 248);
      v19 = *(_WORD *)(v18 + 6);
      if ( v19 > 0x40u || (v19 & 1) != 0 )
        v19 = 0;
      McTemplateU0ppwwpiwd_EtwWriteTransfer(
        *(unsigned __int16 *)(v9.QuadPart + 16) >> 1,
        (unsigned int)fsctrl_c17258,
        (unsigned int)KeGetCurrentThread(),
        v10,
        *(_WORD *)(v10 + 7872) >> 1,
        *(_QWORD *)(v10 + 7880),
        v19 >> 1,
        v18 + 32,
        v12,
        *(_QWORD *)(v12 + 8),
        *(_WORD *)(v9.QuadPart + 16) >> 1,
        *(_QWORD *)(v9.QuadPart + 24),
        v17);
    }
    v14 = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225506LL, 1196921);
    LOBYTE(v17) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225506LL, v17, 0);
    if ( !NtfsStatusDebugFlags )
      return v14;
    v15 = 1196922;
    goto LABEL_14;
  }
  if ( (*(_DWORD *)(v10 + 24) & 0x40000) != 0 )
  {
    v14 = -1073740646;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221226650LL, 1196931);
    LOBYTE(v17) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221226650LL, v17, 0);
    if ( !NtfsStatusDebugFlags )
      return v14;
    v15 = 1196932;
    goto LABEL_14;
  }
  if ( (*(_DWORD *)(v8.QuadPart + 512) & 0x1000000) != 0 )
  {
    v14 = -1073741816;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225480LL, 1196940);
    LOBYTE(v17) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225480LL, v17, 0);
    if ( !NtfsStatusDebugFlags )
      return v14;
    v15 = 1196941;
    goto LABEL_14;
  }
  Address = *(volatile void **)(v6 + 32);
  v20 = *(_DWORD *)(v6 + 16);
  Length = v20;
  v22 = (union _LARGE_INTEGER *)NtfsMapUserBuffer(a2, 16);
  if ( !*(_QWORD *)(a2 + 8) )
    v4 = *(_BYTE *)(a2 + 64);
  if ( v20 < 0x10 )
    goto LABEL_292;
  v119.QuadPart = 0;
  v110[0] = 0;
  Irp = 0;
  v104 = 0;
  v107 = 0;
  v23 = 0;
  v91 = 0;
  v94 = 0;
  IsRangeAllocated = 1;
  v96 = 0;
  v95 = 0;
  v24 = *(_DWORD *)(v6 + 8);
  Size = v24;
  if ( v24 < 0x30 )
  {
LABEL_292:
    v23 = -1073741789;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(a1, 3221225507LL, 1196963);
    LOBYTE(v21) = a2 != 0;
    NtfsExtendedCompleteRequestInternal(a1, a2, 3221225507LL, v21, 0);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225507LL, 1196964);
    return v23;
  }
  if ( *(_BYTE *)(a2 + 64) )
  {
    ProbeForRead(Address, Length, 1u);
    ProbeForWrite(v22, (unsigned int)Size, 1u);
  }
  if ( v4 )
    ULong64FromUser = RtlReadULong64FromUser(Address);
  else
    ULong64FromUser = *(_QWORD *)Address;
  v129 = ULong64FromUser;
  if ( v4 )
    LODWORD(v26) = RtlReadULongFromUser((char *)Address + 8);
  else
    LODWORD(v26) = *((_DWORD *)Address + 2);
  v114 = v26;
  if ( v4 )
    RtlSetUserMemory(v22);
  else
    RtlSetVolatileMemory(v22, 0, (unsigned int)Size);
  v27 = *(_QWORD *)(v124 + 328);
  if ( v27 )
  {
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v27 + 136), 1u);
    i = 1;
    v96 = 1;
    if ( (*(_DWORD *)(*(_QWORD *)(v124 + 328) + 4LL) & 1) != 0
      || (unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD))TxfIsCurrentHandleInTransaction)(
                            a1,
                            (union _LARGE_INTEGER)v9.QuadPart) )
    {
      v23 = -1072103362;
      if ( !NtfsStatusDebugFlags )
      {
LABEL_276:
        v40 = v117;
        goto LABEL_277;
      }
      v30 = 1197057;
LABEL_62:
      NtfsStatusTraceAndDebugInternal(0, v23, v30);
      goto LABEL_276;
    }
  }
  *(_DWORD *)(a1 + 4) |= 0x10000u;
  QuadPart = v125.QuadPart;
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))NtfsAcquireFcbWithPaging)(
    a1,
    *(_QWORD *)(v125.QuadPart + 184),
    (union _LARGE_INTEGER)v125.QuadPart,
    0);
  if ( ULong64FromUser >= *(_QWORD *)(v125.QuadPart + 32) || ULong64FromUser >= *(_QWORD *)(v125.QuadPart + 24) )
  {
    v23 = -1073741807;
    goto LABEL_276;
  }
  v28.QuadPart = 0;
  if ( ULong64FromUser < 0 || !(_DWORD)v26 )
  {
    v23 = -1073740631;
    if ( !NtfsStatusDebugFlags )
      goto LABEL_276;
    v30 = 1197105;
    goto LABEL_62;
  }
  v32 = v111;
  v33 = *(_DWORD *)(v111 + 364);
  v101 = v33;
  Length = v33 - 1;
  i = -v33 & (v33 - 1 + *(_QWORD *)(v125.QuadPart + 40));
  v130 = i;
  if ( ULong64FromUser < i )
  {
    if ( ULong64FromUser + (unsigned int)v26 > i )
    {
      LODWORD(v26) = i - ULong64FromUser;
      v114 = i - ULong64FromUser;
      v95 = 1;
    }
    v41 = *(_WORD *)(v125.QuadPart + 460);
    if ( (v41 & 0x80FF) != 0 )
    {
      if ( (_BYTE)v41 )
      {
        v23 = -1073741822;
        if ( NtfsStatusDebugFlags )
        {
          v52 = 1197537;
          goto LABEL_270;
        }
LABEL_271:
        v108 = v23;
LABEL_272:
        v40 = v117;
        goto LABEL_277;
      }
      v94 = 1;
      v49 = *(_BYTE *)(v111 + 488) + *(_BYTE *)(v125.QuadPart + 462);
      v92 = v49;
      v50 = (_WORD *)&v22[2].QuadPart + 2;
      if ( v4 )
      {
        RtlWriteUShortToUser(v50, 0, 0);
        v49 = v92;
        v33 = v101;
        v32 = v111;
      }
      else
      {
        *v50 = 0;
      }
      v28.QuadPart = ULong64FromUser & -*(_DWORD *)(v32 + 364);
      FileOffset = v28;
      *(_QWORD *)v102 = -*(_DWORD *)(v32 + 364)
                      & (unsigned int)(ULong64FromUser + *(_DWORD *)(v32 + 364) + v26 - v28.LowPart - 1);
      v99 = v102[0];
      v51 = *(_DWORD *)(QuadPart + 452);
      i = (unsigned int)-v51;
      v119.QuadPart = ULong64FromUser & (int)i;
      HIDWORD(Size) = i & (ULong64FromUser + v51 + v26 - v119.LowPart - 1);
      v100 = HIDWORD(Size) >> v49;
      if ( !(unsigned __int16)(HIDWORD(Size) >> v49) )
      {
        v23 = -1073740631;
        if ( NtfsStatusDebugFlags )
        {
          v52 = 1197444;
          goto LABEL_270;
        }
        goto LABEL_271;
      }
      if ( (unsigned __int16)(HIDWORD(Size) >> v49) <= 1u )
      {
        if ( v95 )
        {
          v113 = (-v33 & (v33 + (_DWORD)v22 + 31)) - (_DWORD)v22;
          if ( v113 + HIDWORD(Size) > (unsigned int)Size )
          {
            v28.QuadPart = ULong64FromUser & 0x7FFFFFFFFFFF0000LL;
            FileOffset.QuadPart = ULong64FromUser & 0xFFFFFFFFFFFF0000uLL;
            v44 = ((_DWORD)ULong64FromUser + (_DWORD)v26 - (ULong64FromUser & 0xFFFF0000) + 0xFFFF) & 0xFFFF0000;
            *(_QWORD *)v102 = v44;
            v99 = v44;
          }
          else
          {
            FileOffset = v119;
            LODWORD(v44) = HIDWORD(Size);
            *(_QWORD *)v102 = HIDWORD(Size);
            v99 = HIDWORD(Size);
            v28 = v119;
          }
        }
        else
        {
          LODWORD(v44) = v102[0];
        }
      }
      else
      {
        FileOffset = v119;
        LODWORD(v44) = HIDWORD(Size);
        *(_QWORD *)v102 = HIDWORD(Size);
        v99 = HIDWORD(Size);
        v28 = v119;
      }
      v53 = (unsigned int)v44 + v28.QuadPart;
      if ( v53 >= *(_QWORD *)(QuadPart + 32) )
        v53 = *(_QWORD *)(QuadPart + 32);
      v123 = v53;
      v48 = -*(_DWORD *)(v32 + 364) & (unsigned __int64)(v53 + *(_DWORD *)(v32 + 364) - 1);
      v122 = v48;
      v128 = v48;
      v28.QuadPart = 0;
      if ( v4 )
      {
        LOBYTE(v48) = v49;
        RtlWriteUCharToUser((char *)&v22[2].QuadPart + 6, v48);
        v49 = v92;
        v28.QuadPart = 0;
      }
      else
      {
        BYTE6(v22[2].QuadPart) = v49;
      }
      if ( !v4 )
      {
        HIBYTE(v22[2].QuadPart) = v49;
LABEL_147:
        v54 = (-v101 & (Length + (_DWORD)v22 + 4 * (unsigned __int16)v100 + 44)) - (_DWORD)v22;
        v115 = v54;
        v113 = v54;
        i = (unsigned int)Size;
        if ( v54 > (unsigned int)Size
          || !v94 && (v54 + (unsigned int)v44 < v54 || v54 + (unsigned int)v44 > (unsigned int)Size) )
        {
          v23 = -1073741789;
          if ( NtfsStatusDebugFlags )
          {
            v52 = 1197573;
            goto LABEL_270;
          }
          goto LABEL_271;
        }
        v55 = (_DWORD *)v22 + (unsigned __int16)v100;
        if ( v4 )
        {
          RtlWriteULongToUser(v55 + 7, (unsigned int)ExtendedEncryptedDataInfoSignature);
          v28.QuadPart = 0;
        }
        else
        {
          v55[7] = ExtendedEncryptedDataInfoSignature;
        }
        if ( v4 )
        {
          RtlWriteULongToUser(v55 + 8, 16);
          v28.QuadPart = 0;
        }
        else
        {
          v55[8] = 16;
        }
        if ( *(__int16 *)(QuadPart + 460) < 0 )
        {
          if ( v4 )
          {
            RtlWriteULongToUser(v55 + 9, 1);
            v28.QuadPart = 0;
          }
          else
          {
            v55[9] = 1;
          }
        }
        if ( v4 )
        {
          RtlWriteULongToUser(&v22[1], v54);
          v28.QuadPart = 0;
        }
        else
        {
          v22[1].LowPart = v54;
        }
        if ( v4 )
        {
          RtlWriteUShortToUser((char *)&v22[3].u.LowPart + 2, v100, 0);
          v28.QuadPart = 0;
        }
        else
        {
          HIWORD(v22[3].u.LowPart) = v100;
        }
        if ( (*(_DWORD *)(QuadPart + 512) & 0x10000) != 0 )
        {
          v23 = -1073741202;
          if ( NtfsStatusDebugFlags )
          {
            v52 = 1197609;
            goto LABEL_270;
          }
          goto LABEL_271;
        }
        v56 = v117;
        CcFlushCache(v118[5], &FileOffset, v102[0], v117 + 3);
        NtfsNormalizeAndCleanupTransaction(a1, &v56[3]);
        v125 = FileOffset;
        if ( v4 )
          ((void (__fastcall *)(_QWORD, _QWORD))RtlWriteULong64ToUser)(v22, (union _LARGE_INTEGER)FileOffset.QuadPart);
        else
          *v22 = FileOffset;
        v58 = v111;
        v59 = v22 + 3;
        if ( v4 )
        {
          LOBYTE(v57) = *(_BYTE *)(v111 + 488);
          RtlWriteUCharToUser(v59, v57);
        }
        else
        {
          LOBYTE(v59->LowPart) = *(_BYTE *)(v111 + 488);
        }
        if ( v4 )
          RtlWriteUCharToUser((char *)&v22[3].LowPart + 1, 1);
        else
          BYTE1(v22[3].LowPart) = 1;
        if ( !*(_QWORD *)(a1 + 208) )
          NtfsInitializeIoContext(a1, v134, 0);
        if ( v4 )
          ULongFromUser = RtlReadULongFromUser(&v22[1]);
        else
          ULongFromUser = v22[1].LowPart;
        v56[3].Information = ULongFromUser;
        v61 = 0;
        v28 = FileOffset;
        for ( i = 1; ; i = 1 )
        {
          v101 = v61;
          v62 = v100;
          if ( (unsigned __int16)v61 >= (unsigned __int16)v100 )
          {
            v86 = v123 - v125.LowPart;
            v28.QuadPart = 0;
            if ( v4 )
            {
              RtlWriteULongToUser((char *)&v22[1].QuadPart + 4, v86);
              v28.QuadPart = 0;
            }
            else
            {
              v22[1].HighPart = v86;
            }
            if ( v4 )
            {
              RtlWriteULongToUser(&v22[2], v104);
              v28.QuadPart = 0;
            }
            else
            {
              v22[2].LowPart = v104;
            }
            goto LABEL_272;
          }
          v93 = 0;
          Address = (char *)v22 + v115;
          v63 = v94;
          if ( v94 )
          {
            v64 = v28.QuadPart >> *(_BYTE *)(v58 + 488);
            v65 = v28.QuadPart + *(unsigned int *)(QuadPart + 452);
            v66 = v65;
            if ( v122 < v65 )
              v66 = v122;
            v67 = (v66 + *(unsigned int *)(v58 + 480)) >> *(_BYTE *)(v58 + 488);
            v132 = 0;
            if ( v122 < v65 )
              LODWORD(v65) = v122;
            *(_QWORD *)v110 = (unsigned int)(v65 - v28.LowPart);
            v112 = v65 - v28.LowPart;
            NtfsPreloadAllocationInternal(a1, v67 - 1, 0);
            IsRangeAllocated = NtfsIsRangeAllocated(QuadPart, v64, v67, 0, (__int64)&v132);
            v116 = IsRangeAllocated;
            v28 = FileOffset;
            v56 = v117;
            v58 = v111;
            v62 = v100;
            v63 = v94;
          }
          if ( IsRangeAllocated )
          {
            if ( v63 )
            {
              i = 1;
              if ( v62 == 1 && (v28.QuadPart != v119.QuadPart || v102[0] != HIDWORD(Size)) )
              {
                v68 = 0;
                for ( j = v102[0] - 1; ; j >>= 1 )
                {
                  Length_4 = j;
                  if ( !j )
                    break;
                  ++v68;
                }
                v118 = (PSECTION_OBJECT_POINTERS *)(unsigned int)(1 << v68);
                *(_QWORD *)v102 = v118;
                v99 = 1 << v68;
                *(_QWORD *)v110 = v118;
                v112 = 1 << v68;
                if ( v4 )
                {
                  LOBYTE(i) = v68;
                  RtlWriteUCharToUser((char *)&v22[2].QuadPart + 6, i);
                }
                else
                {
                  BYTE6(v22[2].QuadPart) = v68;
                }
                if ( v4 )
                {
                  LOBYTE(i) = v68;
                  RtlWriteUCharToUser((char *)&v22[2].QuadPart + 7, i);
                }
                else
                {
                  HIBYTE(v22[2].QuadPart) = v68;
                }
                v28 = FileOffset;
                i = FileOffset.QuadPart + (unsigned int)v118;
                if ( i >= *(_QWORD *)(QuadPart + 32) )
                  i = *(_QWORD *)(QuadPart + 32);
                v123 = (unsigned int)i;
                v58 = v111;
                v122 = -*(_DWORD *)(v111 + 364) & (unsigned __int64)(i + *(_DWORD *)(v111 + 364) - 1);
                v128 = v122;
              }
              v70 = v110[0];
              if ( v28.QuadPart + v110[0] > v130 )
              {
                *(_QWORD *)v110 = (unsigned int)(v130 - v28.LowPart);
                v112 = v130 - v28.LowPart;
                v70 = v130 - v28.LowPart;
              }
              if ( v115 + v70 < v115 || v115 + v70 > (unsigned int)Size )
              {
                v23 = -1073741789;
                if ( !NtfsStatusDebugFlags )
                  goto LABEL_271;
                v52 = 1197802;
                goto LABEL_270;
              }
            }
            else
            {
              v70 = v110[0];
            }
            v71 = IoBuildAsynchronousFsdRequest(
                    3u,
                    *(PDEVICE_OBJECT *)(*(_QWORD *)(v58 + 248) + 8LL),
                    (PVOID)Address,
                    v70,
                    &FileOffset,
                    0);
            Irp = v71;
            v28.QuadPart = 0;
            if ( !v71 )
            {
              v23 = -1073741670;
              if ( !NtfsStatusDebugFlags )
                goto LABEL_271;
              v52 = 1197823;
LABEL_270:
              NtfsStatusTraceAndDebugInternal(0, v23, v52);
              goto LABEL_271;
            }
            --v71->CurrentLocation;
            --v71->Tail.Overlay.CurrentStackLocation;
            v71->Tail.Overlay.CurrentStackLocation->DeviceObject = *(PDEVICE_OBJECT *)(*(_QWORD *)(v58 + 248) + 8LL);
            v71->UserBuffer = (PVOID)Address;
            v72 = v110[0];
            NtfsLockUserBuffer(a1, v71, 1, v110[0]);
            v91 = 1;
            *(_BYTE *)(a1 + 32) = 3;
            StartingOffset = v72;
            v73 = Irp;
            NtfsNonCachedIo(a1, Irp, QuadPart, FileOffset.QuadPart, StartingOffset, 2);
            Information = v73->IoStatus.Information;
            v56[3].Information += Information;
            Length = Information;
            v118 = (PSECTION_OBJECT_POINTERS *)((char *)&v22[3].QuadPart + 4 * (unsigned __int16)v101 + 4);
            if ( v4 )
              RtlWriteULongToUser((char *)&v22[3].QuadPart + 4 * (unsigned __int16)v101 + 4, Information);
            else
              *(&v22[3].HighPart + (unsigned __int16)v101) = Information;
            v115 += Information;
            v113 = v115;
          }
          else
          {
            Information = *(_DWORD *)(QuadPart + 452);
            *(_QWORD *)v110 = Information;
            v112 = Information;
            v93 = 1;
            if ( v62 == 1 && (v28.QuadPart != v119.QuadPart || v102[0] != HIDWORD(Size)) )
            {
              FileOffset = v119;
              v125.LowPart = v119.LowPart;
              if ( v4 )
                ((void (__fastcall *)(_QWORD, _QWORD))RtlWriteULong64ToUser)(v22, (union _LARGE_INTEGER)v119.QuadPart);
              else
                *v22 = v119;
              *(_QWORD *)v102 = HIDWORD(Size);
              v99 = HIDWORD(Size);
              v75 = FileOffset.QuadPart + HIDWORD(Size);
              if ( v75 >= *(_QWORD *)(QuadPart + 32) )
                v75 = *(_QWORD *)(QuadPart + 32);
              v123 = (unsigned int)v75;
              v122 = -*(_DWORD *)(v111 + 364) & (unsigned __int64)(v75 + *(_DWORD *)(v111 + 364) - 1);
              v128 = v122;
            }
            Length = 0;
            v118 = (PSECTION_OBJECT_POINTERS *)((char *)&v22[3].QuadPart + 4 * (unsigned __int16)v101 + 4);
            if ( v4 )
              RtlWriteULongToUser((char *)&v22[3].QuadPart + 4 * (unsigned __int16)v101 + 4, 0);
            else
              *(&v22[3].HighPart + (unsigned __int16)v101) = 0;
          }
          v76 = *(union _LARGE_INTEGER *)(QuadPart + 32);
          v77 = Information;
          v133 = Information;
          v78 = FileOffset;
          if ( Information + FileOffset.QuadPart <= v76.QuadPart )
          {
            v107 += Information;
            v126 = v107;
          }
          else
          {
            v79 = v107;
            if ( FileOffset.QuadPart < v76.QuadPart )
            {
              v79 = v76.LowPart - FileOffset.LowPart + v107;
              v107 = v79;
              v126 = v79;
            }
            if ( (*(_WORD *)(QuadPart + 460) & 0x80FF) == 0 )
            {
              v80 = v56[3].Information - Length;
              v56[3].Information = v80;
              v81 = -*(_DWORD *)(v111 + 364) & (v79 + *(_DWORD *)(v111 + 364) - 1);
              v56[3].Information = v80 + v81;
              if ( v4 )
              {
                RtlWriteULongToUser(v118, v81);
                v77 = v133;
              }
              else
              {
                *(_DWORD *)v118 = v81;
              }
              v78 = FileOffset;
            }
          }
          v82 = *(union _LARGE_INTEGER *)(QuadPart + 40);
          if ( v77 + v78.QuadPart <= v82.QuadPart )
          {
            v104 += Information;
            v127 = v104;
          }
          else if ( v82.QuadPart > v78.QuadPart )
          {
            if ( (_WORD)v100 == 1 && !v93 )
            {
              v83 = ((v82.LowPart + 511) & 0xFFFFFE00) - v78.LowPart;
              if ( v83 > 0 && v83 < Information )
              {
                memset((char *)Address + v83, 0, Information - v83);
                v78 = FileOffset;
              }
            }
            v104 += *(_DWORD *)(QuadPart + 40) - v78.LowPart;
            v127 = v104;
          }
          v28.QuadPart = v110[0] + v78.QuadPart;
          FileOffset = v28;
          v84 = Irp;
          if ( Irp )
          {
            MdlAddress = Irp->MdlAddress;
            if ( MdlAddress )
            {
              if ( v91 )
              {
                MmUnlockPages(MdlAddress);
                v91 = 0;
                *(_DWORD *)(a1 + 12) &= ~0x40000u;
              }
              IoFreeMdl(v84->MdlAddress);
              v84->MdlAddress = 0;
            }
            IoFreeIrp(v84);
            Irp = 0;
            v28 = FileOffset;
          }
          HIWORD(v61) = HIWORD(v101);
          LOWORD(v61) = v101 + 1;
          v58 = v111;
        }
      }
      LOBYTE(v48) = v49;
    }
    else
    {
      v42 = (_WORD *)&v22[2].QuadPart + 2;
      if ( v4 )
      {
        RtlWriteUShortToUser(v42, 0, 0);
        v32 = v111;
        i = v130;
      }
      else
      {
        *v42 = 0;
      }
      v43.QuadPart = ULong64FromUser & -*(_DWORD *)(v32 + 364);
      FileOffset = v43;
      v44 = -*(_DWORD *)(v32 + 364) & (unsigned int)(*(_DWORD *)(v32 + 364) + ULong64FromUser - v43.LowPart + v26 - 1);
      *(_QWORD *)v102 = v44;
      v99 = v44;
      v45 = 0;
      for ( k = v44 - 1; ; k >>= 1 )
      {
        Length_4 = k;
        if ( !k )
          break;
        ++v45;
      }
      if ( !v95 )
      {
        LODWORD(v44) = 1 << v45;
        *(_QWORD *)v102 = (unsigned int)(1 << v45);
        v99 = 1 << v45;
        if ( v43.QuadPart + *(_QWORD *)v102 > i )
        {
          LODWORD(v44) = i - v43.LowPart;
          *(_QWORD *)v102 = (unsigned int)(i - v43.LowPart);
          v99 = i - v43.LowPart;
        }
      }
      LOWORD(v100) = 1;
      *(_QWORD *)v110 = (unsigned int)v44;
      v112 = v44;
      v47 = (1LL << v45) + v43.QuadPart;
      if ( v47 >= *(_QWORD *)(QuadPart + 32) )
        v47 = *(_QWORD *)(QuadPart + 32);
      v123 = v47;
      v48 = -*(_DWORD *)(v32 + 364) & (unsigned __int64)(v47 + *(_DWORD *)(v32 + 364) - 1);
      v122 = v48;
      v128 = v48;
      v28.QuadPart = 0;
      if ( v4 )
      {
        LOBYTE(v48) = v45;
        RtlWriteUCharToUser((char *)&v22[2].QuadPart + 6, v48);
        v28.QuadPart = 0;
      }
      else
      {
        BYTE6(v22[2].QuadPart) = v45;
      }
      if ( !v4 )
      {
        HIBYTE(v22[2].QuadPart) = v45;
        goto LABEL_147;
      }
      LOBYTE(v48) = v45;
    }
    RtlWriteUCharToUser((char *)&v22[2].QuadPart + 7, v48);
    v28.QuadPart = 0;
    goto LABEL_147;
  }
  v34 = *(_WORD *)(v125.QuadPart + 460);
  if ( !(_BYTE)v34 )
  {
    if ( v34 >= 0 || ((*(_DWORD *)(v125.QuadPart + 452) - 1) & (unsigned int)ULong64FromUser) != 0 )
      v35 = -v33 & (v26 + v33 - 1);
    else
      v35 = -*(_DWORD *)(v125.QuadPart + 452) & (v26 + *(_DWORD *)(v125.QuadPart + 452) - 1);
    v36 = 0;
    for ( m = v35 - 1; ; m >>= 1 )
    {
      Length_4 = m;
      if ( !m )
        break;
      ++v36;
    }
    v26 = (unsigned int)(1 << v36);
    v114 = 1 << v36;
    v136 = 0;
    v137 = 0;
    Src[0] = ULong64FromUser;
    Src[1] = HIDWORD(v129);
    LODWORD(v136) = 48;
    v38 = 1 << v36;
    if ( v26 >= *(_QWORD *)(v125.QuadPart + 32) - ULong64FromUser )
      v38 = *(_DWORD *)(v125.QuadPart + 32) - ULong64FromUser;
    *(_QWORD *)((char *)&v136 + 4) = v38;
    WORD6(v136) = 0;
    BYTE14(v136) = v36;
    HIBYTE(v136) = v36;
    LOBYTE(v137) = *(_BYTE *)(v111 + 488);
    BYTE1(v137) = 1;
    WORD1(v137) = 1;
    if ( v4 )
      RtlCopyToUser(v22, Src, 0x20u);
    else
      RtlCopyVolatileMemory(v22, Src, 0x20u);
    i = 0;
    if ( v4 )
    {
      RtlWriteULongToUser(&v22[4], (unsigned int)ExtendedEncryptedDataInfoSignature);
      i = 0;
    }
    else
    {
      v22[4].LowPart = ExtendedEncryptedDataInfoSignature;
    }
    if ( v4 )
    {
      RtlWriteULongToUser((char *)&v22[4].QuadPart + 4, 16);
      i = 0;
    }
    else
    {
      v22[4].HighPart = 16;
    }
    if ( *(__int16 *)(QuadPart + 460) < 0 )
    {
      LODWORD(v26) = ((unsigned int)ULong64FromUser & (*(_DWORD *)(QuadPart + 452) - 1)) != 0 ? v26 : 0;
      v114 = v26;
      if ( v4 )
        RtlWriteULongToUser(&v22[5], 1);
      else
        v22[5].LowPart = 1;
      if ( v4 )
      {
        LOBYTE(i) = 2;
        RtlWriteUCharToUser((char *)&v22[3].LowPart + 1, i);
      }
      else
      {
        BYTE1(v22[3].LowPart) = 2;
      }
    }
    if ( (int)v26 + 48 > (unsigned int)Size && NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(0, 3221225507LL, 1197272);
    v28.QuadPart = 0;
    if ( !v4 )
    {
      v22[3].HighPart = v26;
      goto LABEL_103;
    }
    RtlWriteULongToUser((char *)&v22[3].QuadPart + 4, (unsigned int)v26);
    goto LABEL_101;
  }
  if ( NtfsStatusDebugFlags )
  {
    NtfsStatusTraceAndDebugInternal(0, 3221225474LL, 1197136);
LABEL_101:
    v28.QuadPart = 0;
  }
LABEL_103:
  v39 = (unsigned int)(v26 + 48);
  v40 = v117;
  v117[3].Information = v39;
  v23 = 0;
LABEL_277:
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))NtfsFreeIoContext)(a1, i, (union _LARGE_INTEGER)v28.QuadPart);
  v88 = Irp;
  if ( Irp )
  {
    v89 = Irp->MdlAddress;
    if ( v89 )
    {
      if ( v91 )
        MmUnlockPages(v89);
      IoFreeMdl(v88->MdlAddress);
    }
    IoFreeIrp(v88);
  }
  if ( v96 )
    ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(v124 + 328) + 136LL));
  if ( NtfsStatusDebugFlags && v23 && v23 - 298 > 1 && v23 + 2147483643 > 1 && v23 != -1073741807 )
    NtfsStatusTraceAndDebugInternal(a1, v23, 1198148);
  LOBYTE(v87) = v40 != 0;
  NtfsExtendedCompleteRequestInternal(a1, v40, v23, v87, (v23 & 0x80000000) == 0);
  return v23;
}

```

## disassembly

```asm
0x1402836cc  mov     r11, rsp
0x1402836cf  mov     [r11+18h], rbx
0x1402836d3  mov     [r11+20h], rsi
0x1402836d7  push    rdi
0x1402836d8  push    r12
0x1402836da  push    r13
0x1402836dc  push    r14
0x1402836de  push    r15
0x1402836e0  sub     rsp, 200h
0x1402836e7  mov     rax, cs:__security_cookie
0x1402836ee  xor     rax, rsp
0x1402836f1  mov     [rsp+228h+var_38], rax
0x1402836f9  mov     rdi, rdx
0x1402836fc  mov     [rsp+228h+var_140], rdx
0x140283704  mov     r14, rcx
0x140283707  mov     [rsp+228h+var_170], rcx
0x14028370f  xor     r12d, r12d
0x140283712  mov     qword ptr [rsp+228h+FileOffset], r12
0x140283717  mov     [r11-0E8h], r12
0x14028371e  mov     [r11-150h], r12d
0x140283725  xor     eax, eax
0x140283727  mov     [rsp+228h+var_B4], eax
0x14028372e  xor     edx, edx; Val
0x140283730  lea     r8d, [r12+5Ch]; Size
0x140283735  lea     rcx, [r11-0B8h]; void *
0x14028373c  call    memset
0x140283741  lea     r10d, [r12+1]
0x140283746  or      [r14+0Ch], r10d
0x14028374a  mov     rbx, [rdi+0B8h]
0x140283751  mov     rax, [rbx+30h]
0x140283755  mov     [rsp+228h+var_138], rax
0x14028375d  mov     rcx, [rax+18h]
0x140283761  mov     [rsp+228h+var_100], rcx
0x140283769  test    rcx, rcx
0x14028376c  jz      short loc_1402837B8
0x14028376e  mov     r13, [rax+20h]
0x140283772  mov     rsi, [rcx+0C0h]
0x140283779  mov     [rsp+228h+var_160], rsi
0x140283781  mov     eax, [rsi+4]
0x140283784  test    r10b, al
0x140283787  jnz     short loc_1402837A5
0x140283789  test    r13, r13
0x14028378c  jz      loc_140284E1F
0x140283792  cmp     byte ptr [r13+58h], 4
0x140283797  jnz     loc_140284E1F
0x14028379d  test    al, 2
0x14028379f  jz      loc_140284E1F
0x1402837a5  test    r13, r13
0x1402837a8  jz      short loc_1402837E1
0x1402837aa  mov     r15, [rcx+0B8h]
0x1402837b1  movzx   eax, byte ptr [r13+58h]
0x1402837b6  jmp     short loc_1402837CC
0x1402837b8  mov     rsi, r12
0x1402837bb  mov     [rsp+228h+var_160], r12
0x1402837c3  mov     r13, r12
0x1402837c6  mov     r15, r12
0x1402837c9  mov     eax, r10d
0x1402837cc  mov     [rsp+228h+var_D8], r15
0x1402837d4  mov     [rsp+228h+var_108], r15
0x1402837dc  cmp     eax, 2
0x1402837df  jz      short loc_14028383A
0x1402837e1  mov     al, cs:NtfsStatusDebugFlags
0x1402837e7  mov     ebx, 0C000000Dh
0x1402837ec  test    al, al
0x1402837ee  jz      short loc_140283800
0x1402837f0  mov     r8d, 124355h
0x1402837f6  mov     edx, ebx
0x1402837f8  mov     rcx, r14
0x1402837fb  call    NtfsStatusTraceAndDebugInternal
0x140283800  test    rdi, rdi
0x140283803  setnz   r9b
0x140283807  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x14028380c  mov     r8d, ebx
0x14028380f  mov     rdx, rdi
0x140283812  mov     rcx, r14
0x140283815  call    NtfsExtendedCompleteRequestInternal
0x14028381a  mov     cl, cs:NtfsStatusDebugFlags
0x140283820  test    cl, cl
0x140283822  jz      short loc_140283833
0x140283824  mov     r8d, 124356h
0x14028382a  mov     edx, ebx
0x14028382c  xor     ecx, ecx
0x14028382e  call    NtfsStatusTraceAndDebugInternal
0x140283833  mov     eax, ebx
0x140283835  jmp     loc_140284DF1
0x14028383a  bt      word ptr [rcx+1CCh], 0Eh
0x140283843  jb      short loc_140283890
0x140283845  mov     al, cs:NtfsStatusDebugFlags
0x14028384b  mov     ebx, 0C00004A7h
0x140283850  test    al, al
0x140283852  jz      short loc_140283864
0x140283854  mov     r8d, 124360h
0x14028385a  mov     edx, ebx
0x14028385c  mov     rcx, r14
0x14028385f  call    NtfsStatusTraceAndDebugInternal
0x140283864  test    rdi, rdi
0x140283867  setnz   r9b
0x14028386b  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x140283870  mov     r8d, ebx
0x140283873  mov     rdx, rdi
0x140283876  mov     rcx, r14
0x140283879  call    NtfsExtendedCompleteRequestInternal
0x14028387e  mov     cl, cs:NtfsStatusDebugFlags
0x140283884  test    cl, cl
0x140283886  jz      short loc_140283833
0x140283888  mov     r8d, 124361h
0x14028388e  jmp     short loc_14028382A
0x140283890  movzx   r9d, word ptr [r13+68h]
0x140283895  test    r9b, 9
0x140283899  jnz     loc_14028399A
0x14028389f  mov     eax, [r14+10h]
0x1402838a3  bt      rax, 14h
0x1402838a8  jb      loc_140283948
0x1402838ae  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x1402838b5  test    al, 20h
0x1402838b7  jz      loc_140283948
0x1402838bd  mov     rdx, [rsi+0F8h]
0x1402838c4  movzx   r8d, word ptr [rdx+6]
0x1402838c9  cmp     r8w, 40h ; '@'
0x1402838ce  ja      short loc_1402838D5
0x1402838d0  test    r10b, r8b
0x1402838d3  jz      short loc_1402838D8
0x1402838d5  mov     r8d, r12d
0x1402838d8  movzx   ecx, word ptr [r13+10h]
0x1402838dd  shr     ecx, 1
0x1402838df  add     rdx, 20h ; ' '
0x1402838e3  movzx   r10d, r8w
0x1402838e7  shr     r10d, 1
0x1402838ea  movzx   r11d, word ptr [rsi+1EC0h]
0x1402838f2  shr     r11d, 1
0x1402838f5  mov     r8, gs:188h
0x1402838fe  mov     [rsp+228h+var_1C8], r9d
0x140283903  mov     rax, [r13+18h]
0x140283907  mov     [rsp+228h+var_1D0], rax
0x14028390c  mov     [rsp+228h+var_1D8], ecx
0x140283910  mov     rax, [r15+8]
0x140283914  mov     [rsp+228h+var_1E0], rax
0x140283919  mov     [rsp+228h+var_1E8], r15
0x14028391e  mov     [rsp+228h+var_1F0], rdx
0x140283923  mov     [rsp+228h+var_1F8], r10d
0x140283928  mov     rax, [rsi+1EC8h]
0x14028392f  mov     [rsp+228h+IoStatusBlock], rax
0x140283934  mov     dword ptr [rsp+228h+StartingOffset], r11d
0x140283939  mov     r9, rsi
0x14028393c  lea     rdx, fsctrl_c17258
0x140283943  call    McTemplateU0ppwwpiwd_EtwWriteTransfer
0x140283948  mov     al, cs:NtfsStatusDebugFlags
0x14028394e  mov     ebx, 0C0000022h
0x140283953  test    al, al
0x140283955  jz      short loc_140283967
0x140283957  mov     r8d, 124379h
0x14028395d  mov     edx, ebx
0x14028395f  mov     rcx, r14
0x140283962  call    NtfsStatusTraceAndDebugInternal
0x140283967  test    rdi, rdi
0x14028396a  setnz   r9b
0x14028396e  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x140283973  mov     r8d, ebx
0x140283976  mov     rdx, rdi
0x140283979  mov     rcx, r14
0x14028397c  call    NtfsExtendedCompleteRequestInternal
0x140283981  mov     cl, cs:NtfsStatusDebugFlags
0x140283987  test    cl, cl
0x140283989  jz      loc_140283833
0x14028398f  mov     r8d, 12437Ah
0x140283995  jmp     loc_14028382A
0x14028399a  test    dword ptr [rsi+18h], 40000h
0x1402839a1  jz      short loc_1402839F5
0x1402839a3  mov     al, cs:NtfsStatusDebugFlags
0x1402839a9  mov     ebx, 0C000049Ah
0x1402839ae  test    al, al
0x1402839b0  jz      short loc_1402839C2
0x1402839b2  mov     r8d, 124383h
0x1402839b8  mov     edx, ebx
0x1402839ba  mov     rcx, r14
0x1402839bd  call    NtfsStatusTraceAndDebugInternal
0x1402839c2  test    rdi, rdi
0x1402839c5  setnz   r9b
0x1402839c9  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x1402839ce  mov     r8d, ebx
0x1402839d1  mov     rdx, rdi
0x1402839d4  mov     rcx, r14
0x1402839d7  call    NtfsExtendedCompleteRequestInternal
0x1402839dc  mov     cl, cs:NtfsStatusDebugFlags
0x1402839e2  test    cl, cl
0x1402839e4  jz      loc_140283833
0x1402839ea  mov     r8d, 124384h
0x1402839f0  jmp     loc_14028382A
0x1402839f5  test    dword ptr [rcx+200h], 1000000h
0x1402839ff  jz      short loc_140283A53
0x140283a01  mov     al, cs:NtfsStatusDebugFlags
0x140283a07  mov     ebx, 0C0000008h
0x140283a0c  test    al, al
0x140283a0e  jz      short loc_140283A20
0x140283a10  mov     r8d, 12438Ch
0x140283a16  mov     edx, ebx
0x140283a18  mov     rcx, r14
0x140283a1b  call    NtfsStatusTraceAndDebugInternal
0x140283a20  test    rdi, rdi
0x140283a23  setnz   r9b
0x140283a27  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x140283a2c  mov     r8d, ebx
0x140283a2f  mov     rdx, rdi
0x140283a32  mov     rcx, r14
0x140283a35  call    NtfsExtendedCompleteRequestInternal
0x140283a3a  mov     cl, cs:NtfsStatusDebugFlags
0x140283a40  test    cl, cl
0x140283a42  jz      loc_140283833
0x140283a48  mov     r8d, 12438Dh
0x140283a4e  jmp     loc_14028382A
0x140283a53  mov     rax, [rbx+20h]
0x140283a57  mov     [rsp+228h+Address], rax
0x140283a5f  mov     esi, [rbx+10h]
0x140283a62  mov     dword ptr [rsp+228h+Length], esi
0x140283a69  mov     edx, 10h
0x140283a6e  mov     rcx, rdi
0x140283a71  call    NtfsMapUserBuffer
0x140283a76  mov     r15, rax
0x140283a79  cmp     [rdi+8], r12
0x140283a7d  jnz     short loc_140283A83
0x140283a7f  mov     r12b, [rdi+40h]
0x140283a83  xor     ecx, ecx
0x140283a85  cmp     esi, 10h
0x140283a88  jb      loc_140284D9C
0x140283a8e  mov     [rsp+228h+var_130], rcx
0x140283a96  mov     dword ptr [rsp+228h+Size+4], ecx
0x140283a9d  mov     [rsp+228h+var_168], ecx
0x140283aa4  mov     [rsp+228h+Irp], rcx
0x140283aac  mov     [rsp+228h+var_188], ecx
0x140283ab3  mov     [rsp+228h+var_17C], ecx
0x140283aba  mov     esi, ecx
0x140283abc  mov     [rsp+228h+var_1B7], cl
0x140283ac0  mov     [rsp+228h+var_1B5], cl
0x140283ac4  lea     r8d, [rcx+1]; Alignment
0x140283ac8  mov     [rsp+228h+var_1B2], r8b
0x140283acd  mov     [rsp+228h+var_1B8], cl
0x140283ad1  mov     [rsp+228h+var_1B3], cl
0x140283ad5  mov     [rsp+228h+var_1B4], cl
0x140283ad9  mov     eax, [rbx+8]
0x140283adc  mov     dword ptr [rsp+228h+Size], eax
0x140283ae3  cmp     eax, 30h ; '0'
0x140283ae6  jb      loc_140284D9C
0x140283aec  mov     rbx, [rsp+228h+Address]
0x140283af4  cmp     [rdi+40h], cl
0x140283af7  jz      short loc_140283B2B
0x140283af9  mov     edx, dword ptr [rsp+228h+Length]; Length
0x140283b00  mov     rcx, rbx; Address
0x140283b03  call    cs:__imp_ProbeForRead
0x140283b0a  nop     dword ptr [rax+rax+00h]
0x140283b0f  mov     edx, dword ptr [rsp+228h+Size]; Length
0x140283b16  mov     r8d, 1; Alignment
0x140283b1c  mov     rcx, r15; Address
0x140283b1f  call    cs:__imp_ProbeForWrite
0x140283b26  nop     dword ptr [rax+rax+00h]
0x140283b2b  test    r12b, r12b
0x140283b2e  jz      short loc_140283B3D
0x140283b30  mov     rcx, rbx
0x140283b33  call    RtlReadULong64FromUser
0x140283b38  mov     rdi, rax
0x140283b3b  jmp     short loc_140283B40
0x140283b3d  mov     rdi, [rbx]
0x140283b40  mov     [rsp+228h+var_E8], rdi
0x140283b48  test    r12b, r12b
0x140283b4b  jz      short loc_140283B5A
0x140283b4d  lea     rcx, [rbx+8]
0x140283b51  call    RtlReadULongFromUser
0x140283b56  mov     ebx, eax
0x140283b58  jmp     short loc_140283B5D
0x140283b5a  mov     ebx, [rbx+8]
0x140283b5d  mov     [rsp+228h+var_150], ebx
0x140283b64  mov     r8d, dword ptr [rsp+228h+Size]; Size
0x140283b6c  xor     edx, edx; Val
0x140283b6e  mov     rcx, r15; void *
0x140283b71  test    r12b, r12b
0x140283b74  jz      short loc_140283B7D
0x140283b76  call    RtlSetUserMemory
0x140283b7b  jmp     short loc_140283B83
0x140283b7d  call    RtlSetVolatileMemory
0x140283b82  nop
0x140283b83  mov     rcx, [rsp+228h+var_108]
0x140283b8b  mov     rcx, [rcx+148h]
0x140283b92  test    rcx, rcx
0x140283b95  jz      short loc_140283C01
0x140283b97  mov     dl, 1; Wait
0x140283b99  mov     rcx, [rcx+88h]; Resource
0x140283ba0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140283ba7  nop     dword ptr [rax+rax+00h]
0x140283bac  mov     edx, 1
0x140283bb1  mov     [rsp+228h+var_1B3], dl
0x140283bb5  mov     rax, [rsp+228h+var_108]
0x140283bbd  mov     rax, [rax+148h]
0x140283bc4  mov     ecx, [rax+4]
0x140283bc7  test    dl, cl
0x140283bc9  jnz     short loc_140283BDA
0x140283bcb  mov     rdx, r13
0x140283bce  mov     rcx, r14
0x140283bd1  call    TxfIsCurrentHandleInTransaction
0x140283bd6  test    al, al
0x140283bd8  jz      short loc_140283C01
0x140283bda  mov     al, cs:NtfsStatusDebugFlags
  ... truncated ...
```
