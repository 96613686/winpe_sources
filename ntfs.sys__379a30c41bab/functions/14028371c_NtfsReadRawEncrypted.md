# NtfsReadRawEncrypted

- ea: `0x14028371c`
- end: `0x140284f55`
- name: `NtfsReadRawEncrypted`
- size: `6201`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `28`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x1401f58e0`

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
- `0x1400592c0`
- `0x140059330`
- `0x140059350`
- `0x140059740`
- `0x1400bdc7c`
- `0x1400bdd18`
- `0x1400bdd54`
- `0x1400bddcc`
- `0x1400bde2c`
- `0x1400bde74`
- `0x1400bdebc`
- `0x1400bdf00`
- `0x140160c30`
- `0x140175ad0`
- `0x1401c0904`
- `0x14028371c`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140284be7`
- `ntoskrnl!IoFreeIrp` at `0x140284d31`
- `ntoskrnl!IoFreeIrp` at `0x1402bc891`
- `ntoskrnl!IoFreeIrp` at `0x140284be7`
- `ntoskrnl!IoFreeIrp` at `0x140284d31`
- `ntoskrnl!IoFreeIrp` at `0x1402bc891`
- `ntoskrnl!IoFreeMdl` at `0x140284bd0`
- `ntoskrnl!IoFreeMdl` at `0x140284d22`
- `ntoskrnl!IoFreeMdl` at `0x1402bc881`
- `ntoskrnl!IoFreeMdl` at `0x140284bd0`
- `ntoskrnl!IoFreeMdl` at `0x140284d22`
- `ntoskrnl!IoFreeMdl` at `0x1402bc881`
- `ntoskrnl!MmUnlockPages` at `0x140284baf`
- `ntoskrnl!MmUnlockPages` at `0x140284d12`
- `ntoskrnl!MmUnlockPages` at `0x1402bc870`
- `ntoskrnl!MmUnlockPages` at `0x140284baf`
- `ntoskrnl!MmUnlockPages` at `0x140284d12`
- `ntoskrnl!MmUnlockPages` at `0x1402bc870`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1402847d0`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x1402847d0`
- `ntoskrnl!ProbeForWrite` at `0x140283b6f`
- `ntoskrnl!ProbeForWrite` at `0x140283b6f`
- `ntoskrnl!ProbeForRead` at `0x140283b53`
- `ntoskrnl!ProbeForRead` at `0x140283b53`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140283bf0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140283bf0`
- `ntoskrnl!ExReleaseResourceLite` at `0x140284d5a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc8b9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140284d5a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc8b9`
- `ntoskrnl!CcFlushCache` at `0x140284451`
- `ntoskrnl!CcFlushCache` at `0x140284451`

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
      JUMPOUT(0x140284F55LL);
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
0x14028371c  mov     r11, rsp
0x14028371f  mov     [r11+18h], rbx
0x140283723  mov     [r11+20h], rsi
0x140283727  push    rdi
0x140283728  push    r12
0x14028372a  push    r13
0x14028372c  push    r14
0x14028372e  push    r15
0x140283730  sub     rsp, 200h
0x140283737  mov     rax, cs:__security_cookie
0x14028373e  xor     rax, rsp
0x140283741  mov     [rsp+228h+var_38], rax
0x140283749  mov     rdi, rdx
0x14028374c  mov     [rsp+228h+var_140], rdx
0x140283754  mov     r14, rcx
0x140283757  mov     [rsp+228h+var_170], rcx
0x14028375f  xor     r12d, r12d
0x140283762  mov     qword ptr [rsp+228h+FileOffset], r12
0x140283767  mov     [r11-0E8h], r12
0x14028376e  mov     [r11-150h], r12d
0x140283775  xor     eax, eax
0x140283777  mov     [rsp+228h+var_B4], eax
0x14028377e  xor     edx, edx; Val
0x140283780  lea     r8d, [r12+5Ch]; Size
0x140283785  lea     rcx, [r11-0B8h]; void *
0x14028378c  call    memset
0x140283791  lea     r10d, [r12+1]
0x140283796  or      [r14+0Ch], r10d
0x14028379a  mov     rbx, [rdi+0B8h]
0x1402837a1  mov     rax, [rbx+30h]
0x1402837a5  mov     [rsp+228h+var_138], rax
0x1402837ad  mov     rcx, [rax+18h]
0x1402837b1  mov     [rsp+228h+var_100], rcx
0x1402837b9  test    rcx, rcx
0x1402837bc  jz      short loc_140283808
0x1402837be  mov     r13, [rax+20h]
0x1402837c2  mov     rsi, [rcx+0C0h]
0x1402837c9  mov     [rsp+228h+var_160], rsi
0x1402837d1  mov     eax, [rsi+4]
0x1402837d4  test    r10b, al
0x1402837d7  jnz     short loc_1402837F5
0x1402837d9  test    r13, r13
0x1402837dc  jz      loc_140284E6F
0x1402837e2  cmp     byte ptr [r13+58h], 4
0x1402837e7  jnz     loc_140284E6F
0x1402837ed  test    al, 2
0x1402837ef  jz      loc_140284E6F
0x1402837f5  test    r13, r13
0x1402837f8  jz      short loc_140283831
0x1402837fa  mov     r15, [rcx+0B8h]
0x140283801  movzx   eax, byte ptr [r13+58h]
0x140283806  jmp     short loc_14028381C
0x140283808  mov     rsi, r12
0x14028380b  mov     [rsp+228h+var_160], r12
0x140283813  mov     r13, r12
0x140283816  mov     r15, r12
0x140283819  mov     eax, r10d
0x14028381c  mov     [rsp+228h+var_D8], r15
0x140283824  mov     [rsp+228h+var_108], r15
0x14028382c  cmp     eax, 2
0x14028382f  jz      short loc_14028388A
0x140283831  mov     al, cs:NtfsStatusDebugFlags
0x140283837  mov     ebx, 0C000000Dh
0x14028383c  test    al, al
0x14028383e  jz      short loc_140283850
0x140283840  mov     r8d, 124355h
0x140283846  mov     edx, ebx
0x140283848  mov     rcx, r14
0x14028384b  call    NtfsStatusTraceAndDebugInternal
0x140283850  test    rdi, rdi
0x140283853  setnz   r9b
0x140283857  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x14028385c  mov     r8d, ebx
0x14028385f  mov     rdx, rdi
0x140283862  mov     rcx, r14
0x140283865  call    NtfsExtendedCompleteRequestInternal
0x14028386a  mov     cl, cs:NtfsStatusDebugFlags
0x140283870  test    cl, cl
0x140283872  jz      short loc_140283883
0x140283874  mov     r8d, 124356h
0x14028387a  mov     edx, ebx
0x14028387c  xor     ecx, ecx
0x14028387e  call    NtfsStatusTraceAndDebugInternal
0x140283883  mov     eax, ebx
0x140283885  jmp     loc_140284E41
0x14028388a  bt      word ptr [rcx+1CCh], 0Eh
0x140283893  jb      short loc_1402838E0
0x140283895  mov     al, cs:NtfsStatusDebugFlags
0x14028389b  mov     ebx, 0C00004A7h
0x1402838a0  test    al, al
0x1402838a2  jz      short loc_1402838B4
0x1402838a4  mov     r8d, 124360h
0x1402838aa  mov     edx, ebx
0x1402838ac  mov     rcx, r14
0x1402838af  call    NtfsStatusTraceAndDebugInternal
0x1402838b4  test    rdi, rdi
0x1402838b7  setnz   r9b
0x1402838bb  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x1402838c0  mov     r8d, ebx
0x1402838c3  mov     rdx, rdi
0x1402838c6  mov     rcx, r14
0x1402838c9  call    NtfsExtendedCompleteRequestInternal
0x1402838ce  mov     cl, cs:NtfsStatusDebugFlags
0x1402838d4  test    cl, cl
0x1402838d6  jz      short loc_140283883
0x1402838d8  mov     r8d, 124361h
0x1402838de  jmp     short loc_14028387A
0x1402838e0  movzx   r9d, word ptr [r13+68h]
0x1402838e5  test    r9b, 9
0x1402838e9  jnz     loc_1402839EA
0x1402838ef  mov     eax, [r14+10h]
0x1402838f3  bt      rax, 14h
0x1402838f8  jb      loc_140283998
0x1402838fe  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x140283905  test    al, 20h
0x140283907  jz      loc_140283998
0x14028390d  mov     rdx, [rsi+0F8h]
0x140283914  movzx   r8d, word ptr [rdx+6]
0x140283919  cmp     r8w, 40h ; '@'
0x14028391e  ja      short loc_140283925
0x140283920  test    r10b, r8b
0x140283923  jz      short loc_140283928
0x140283925  mov     r8d, r12d
0x140283928  movzx   ecx, word ptr [r13+10h]
0x14028392d  shr     ecx, 1
0x14028392f  add     rdx, 20h ; ' '
0x140283933  movzx   r10d, r8w
0x140283937  shr     r10d, 1
0x14028393a  movzx   r11d, word ptr [rsi+1EC0h]
0x140283942  shr     r11d, 1
0x140283945  mov     r8, gs:188h
0x14028394e  mov     [rsp+228h+var_1C8], r9d
0x140283953  mov     rax, [r13+18h]
0x140283957  mov     [rsp+228h+var_1D0], rax
0x14028395c  mov     [rsp+228h+var_1D8], ecx
0x140283960  mov     rax, [r15+8]
0x140283964  mov     [rsp+228h+var_1E0], rax
0x140283969  mov     [rsp+228h+var_1E8], r15
0x14028396e  mov     [rsp+228h+var_1F0], rdx
0x140283973  mov     [rsp+228h+var_1F8], r10d
0x140283978  mov     rax, [rsi+1EC8h]
0x14028397f  mov     [rsp+228h+IoStatusBlock], rax
0x140283984  mov     dword ptr [rsp+228h+StartingOffset], r11d
0x140283989  mov     r9, rsi
0x14028398c  lea     rdx, fsctrl_c17258
0x140283993  call    McTemplateU0ppwwpiwd_EtwWriteTransfer
0x140283998  mov     al, cs:NtfsStatusDebugFlags
0x14028399e  mov     ebx, 0C0000022h
0x1402839a3  test    al, al
0x1402839a5  jz      short loc_1402839B7
0x1402839a7  mov     r8d, 124379h
0x1402839ad  mov     edx, ebx
0x1402839af  mov     rcx, r14
0x1402839b2  call    NtfsStatusTraceAndDebugInternal
0x1402839b7  test    rdi, rdi
0x1402839ba  setnz   r9b
0x1402839be  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x1402839c3  mov     r8d, ebx
0x1402839c6  mov     rdx, rdi
0x1402839c9  mov     rcx, r14
0x1402839cc  call    NtfsExtendedCompleteRequestInternal
0x1402839d1  mov     cl, cs:NtfsStatusDebugFlags
0x1402839d7  test    cl, cl
0x1402839d9  jz      loc_140283883
0x1402839df  mov     r8d, 12437Ah
0x1402839e5  jmp     loc_14028387A
0x1402839ea  test    dword ptr [rsi+18h], 40000h
0x1402839f1  jz      short loc_140283A45
0x1402839f3  mov     al, cs:NtfsStatusDebugFlags
0x1402839f9  mov     ebx, 0C000049Ah
0x1402839fe  test    al, al
0x140283a00  jz      short loc_140283A12
0x140283a02  mov     r8d, 124383h
0x140283a08  mov     edx, ebx
0x140283a0a  mov     rcx, r14
0x140283a0d  call    NtfsStatusTraceAndDebugInternal
0x140283a12  test    rdi, rdi
0x140283a15  setnz   r9b
0x140283a19  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x140283a1e  mov     r8d, ebx
0x140283a21  mov     rdx, rdi
0x140283a24  mov     rcx, r14
0x140283a27  call    NtfsExtendedCompleteRequestInternal
0x140283a2c  mov     cl, cs:NtfsStatusDebugFlags
0x140283a32  test    cl, cl
0x140283a34  jz      loc_140283883
0x140283a3a  mov     r8d, 124384h
0x140283a40  jmp     loc_14028387A
0x140283a45  test    dword ptr [rcx+200h], 1000000h
0x140283a4f  jz      short loc_140283AA3
0x140283a51  mov     al, cs:NtfsStatusDebugFlags
0x140283a57  mov     ebx, 0C0000008h
0x140283a5c  test    al, al
0x140283a5e  jz      short loc_140283A70
0x140283a60  mov     r8d, 12438Ch
0x140283a66  mov     edx, ebx
0x140283a68  mov     rcx, r14
0x140283a6b  call    NtfsStatusTraceAndDebugInternal
0x140283a70  test    rdi, rdi
0x140283a73  setnz   r9b
0x140283a77  mov     dword ptr [rsp+228h+StartingOffset], r12d
0x140283a7c  mov     r8d, ebx
0x140283a7f  mov     rdx, rdi
0x140283a82  mov     rcx, r14
0x140283a85  call    NtfsExtendedCompleteRequestInternal
0x140283a8a  mov     cl, cs:NtfsStatusDebugFlags
0x140283a90  test    cl, cl
0x140283a92  jz      loc_140283883
0x140283a98  mov     r8d, 12438Dh
0x140283a9e  jmp     loc_14028387A
0x140283aa3  mov     rax, [rbx+20h]
0x140283aa7  mov     [rsp+228h+Address], rax
0x140283aaf  mov     esi, [rbx+10h]
0x140283ab2  mov     dword ptr [rsp+228h+Length], esi
0x140283ab9  mov     edx, 10h
0x140283abe  mov     rcx, rdi
0x140283ac1  call    NtfsMapUserBuffer
0x140283ac6  mov     r15, rax
0x140283ac9  cmp     [rdi+8], r12
0x140283acd  jnz     short loc_140283AD3
0x140283acf  mov     r12b, [rdi+40h]
0x140283ad3  xor     ecx, ecx
0x140283ad5  cmp     esi, 10h
0x140283ad8  jb      loc_140284DEC
0x140283ade  mov     [rsp+228h+var_130], rcx
0x140283ae6  mov     dword ptr [rsp+228h+Size+4], ecx
0x140283aed  mov     [rsp+228h+var_168], ecx
0x140283af4  mov     [rsp+228h+Irp], rcx
0x140283afc  mov     [rsp+228h+var_188], ecx
0x140283b03  mov     [rsp+228h+var_17C], ecx
0x140283b0a  mov     esi, ecx
0x140283b0c  mov     [rsp+228h+var_1B7], cl
0x140283b10  mov     [rsp+228h+var_1B5], cl
0x140283b14  lea     r8d, [rcx+1]; Alignment
0x140283b18  mov     [rsp+228h+var_1B2], r8b
0x140283b1d  mov     [rsp+228h+var_1B8], cl
0x140283b21  mov     [rsp+228h+var_1B3], cl
0x140283b25  mov     [rsp+228h+var_1B4], cl
0x140283b29  mov     eax, [rbx+8]
0x140283b2c  mov     dword ptr [rsp+228h+Size], eax
0x140283b33  cmp     eax, 30h ; '0'
0x140283b36  jb      loc_140284DEC
0x140283b3c  mov     rbx, [rsp+228h+Address]
0x140283b44  cmp     [rdi+40h], cl
0x140283b47  jz      short loc_140283B7B
0x140283b49  mov     edx, dword ptr [rsp+228h+Length]; Length
0x140283b50  mov     rcx, rbx; Address
0x140283b53  call    cs:__imp_ProbeForRead
0x140283b5a  nop     dword ptr [rax+rax+00h]
0x140283b5f  mov     edx, dword ptr [rsp+228h+Size]; Length
0x140283b66  mov     r8d, 1; Alignment
0x140283b6c  mov     rcx, r15; Address
0x140283b6f  call    cs:__imp_ProbeForWrite
0x140283b76  nop     dword ptr [rax+rax+00h]
0x140283b7b  test    r12b, r12b
0x140283b7e  jz      short loc_140283B8D
0x140283b80  mov     rcx, rbx
0x140283b83  call    RtlReadULong64FromUser
0x140283b88  mov     rdi, rax
0x140283b8b  jmp     short loc_140283B90
0x140283b8d  mov     rdi, [rbx]
0x140283b90  mov     [rsp+228h+var_E8], rdi
0x140283b98  test    r12b, r12b
0x140283b9b  jz      short loc_140283BAA
0x140283b9d  lea     rcx, [rbx+8]
0x140283ba1  call    RtlReadULongFromUser
0x140283ba6  mov     ebx, eax
0x140283ba8  jmp     short loc_140283BAD
0x140283baa  mov     ebx, [rbx+8]
0x140283bad  mov     [rsp+228h+var_150], ebx
0x140283bb4  mov     r8d, dword ptr [rsp+228h+Size]; Size
0x140283bbc  xor     edx, edx; Val
0x140283bbe  mov     rcx, r15; void *
0x140283bc1  test    r12b, r12b
0x140283bc4  jz      short loc_140283BCD
0x140283bc6  call    RtlSetUserMemory
0x140283bcb  jmp     short loc_140283BD3
0x140283bcd  call    RtlSetVolatileMemory
0x140283bd2  nop
0x140283bd3  mov     rcx, [rsp+228h+var_108]
0x140283bdb  mov     rcx, [rcx+148h]
0x140283be2  test    rcx, rcx
0x140283be5  jz      short loc_140283C51
0x140283be7  mov     dl, 1; Wait
0x140283be9  mov     rcx, [rcx+88h]; Resource
0x140283bf0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140283bf7  nop     dword ptr [rax+rax+00h]
0x140283bfc  mov     edx, 1
0x140283c01  mov     [rsp+228h+var_1B3], dl
0x140283c05  mov     rax, [rsp+228h+var_108]
0x140283c0d  mov     rax, [rax+148h]
0x140283c14  mov     ecx, [rax+4]
0x140283c17  test    dl, cl
0x140283c19  jnz     short loc_140283C2A
0x140283c1b  mov     rdx, r13
0x140283c1e  mov     rcx, r14
0x140283c21  call    TxfIsCurrentHandleInTransaction
0x140283c26  test    al, al
0x140283c28  jz      short loc_140283C51
0x140283c2a  mov     al, cs:NtfsStatusDebugFlags
  ... truncated ...
```
