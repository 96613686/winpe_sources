# FatCommonCreate

- ea: `0x1400268c0`
- end: `0x1400289cf`
- name: `FatCommonCreate`
- size: `8463`
- prototype: `__int64 __fastcall(PVOID Context1)`
- caller_count: `2`
- callee_count: `40`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400289e0`
- `0x1400438e0`

## callees

- `0x140002b30`
- `0x140007408`
- `0x14000c230`
- `0x14000c380`
- `0x14000c680`
- `0x140023ad4`
- `0x14002486c`
- `0x140026390`
- `0x140026864`
- `0x1400268c0`
- `0x140028cc0`
- `0x140029774`
- `0x14002a614`
- `0x14002aae8`
- `0x14002adec`
- `0x14002b790`
- `0x14002bf3c`
- `0x14002c080`
- `0x14002c234`
- `0x14002c910`
- `0x14002ca48`
- `0x140031468`
- `0x140031938`
- `0x140031e8c`
- `0x14003d880`
- `0x140044518`
- `0x140044bac`
- `0x140044df4`
- `0x140044e74`
- `0x1400466c8`
- `0x14004763c`
- `0x14004814c`
- `0x140048184`
- `0x140048680`
- `0x1400486ec`
- `0x1400490a8`
- `0x14004912c`
- `0x1400492a4`
- `0x14004a1d4`
- `0x14004a37c`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140026bc3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140026bc3`
- `ntoskrnl!IoFreeMdl` at `0x14002889d`
- `ntoskrnl!IoFreeMdl` at `0x14005bf28`
- `ntoskrnl!IoFreeMdl` at `0x14002889d`
- `ntoskrnl!IoFreeMdl` at `0x14005bf28`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140028790`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14005bc80`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14005be26`
- `ntoskrnl!CcUninitializeCacheMap` at `0x140028790`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14005bc80`
- `ntoskrnl!CcUninitializeCacheMap` at `0x14005be26`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140026e42`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400283dd`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400284f8`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x140026e42`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400283dd`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x1400284f8`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400286fd`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14005bbd4`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1400286fd`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14005bbd4`
- `ntoskrnl!FsRtlDissectName` at `0x14002720a`
- `ntoskrnl!FsRtlDissectName` at `0x140027bbe`
- `ntoskrnl!FsRtlDissectName` at `0x14002720a`
- `ntoskrnl!FsRtlDissectName` at `0x140027bbe`
- `ntoskrnl!RtlUpcaseUnicodeStringToCountedOemString` at `0x140027263`
- `ntoskrnl!RtlUpcaseUnicodeStringToCountedOemString` at `0x140027c25`
- `ntoskrnl!RtlUpcaseUnicodeStringToCountedOemString` at `0x140027263`
- `ntoskrnl!RtlUpcaseUnicodeStringToCountedOemString` at `0x140027c25`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x14002734f`
- `ntoskrnl!RtlDowncaseUnicodeString` at `0x14002734f`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002736e`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140027dcd`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x14002736e`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x140027dcd`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x140027471`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x140027fb0`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x140027471`
- `ntoskrnl!RtlOemStringToCountedUnicodeString` at `0x140027fb0`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002748f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140027fcf`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14002748f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140027fcf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400274ce`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140027ff3`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400274ce`
- `ntoskrnl!RtlCopyUnicodeString` at `0x140027ff3`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x140027c5c`
- `ntoskrnl!FsRtlIsFatDbcsLegal` at `0x140027c5c`
- `ntoskrnl!FsRtlLegalAnsiCharacterArray` at `0x140027d0e`
- `ntoskrnl!IoAllocateMdl` at `0x140028877`
- `ntoskrnl!IoAllocateMdl` at `0x14005bf02`
- `ntoskrnl!IoAllocateMdl` at `0x140028877`
- `ntoskrnl!IoAllocateMdl` at `0x14005bf02`
- `ntoskrnl!ExReleaseResourceLite` at `0x140028820`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bcb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be79`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be98`
- `ntoskrnl!ExReleaseResourceLite` at `0x140028820`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005bcb5`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be79`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005be98`
- `ntoskrnl!CcUnpinData` at `0x140028716`
- `ntoskrnl!CcUnpinData` at `0x14005bbf5`
- `ntoskrnl!CcUnpinData` at `0x140028716`
- `ntoskrnl!CcUnpinData` at `0x14005bbf5`
- `ntoskrnl!KeBugCheckEx` at `0x140026ca6`
- `ntoskrnl!KeBugCheckEx` at `0x140027a21`
- `ntoskrnl!KeBugCheckEx` at `0x140026ca6`
- `ntoskrnl!KeBugCheckEx` at `0x140027a21`
- `ntoskrnl!ExRaiseStatus` at `0x140026e66`
- `ntoskrnl!ExRaiseStatus` at `0x140028401`
- `ntoskrnl!ExRaiseStatus` at `0x14002851c`
- `ntoskrnl!ExRaiseStatus` at `0x140026e66`
- `ntoskrnl!ExRaiseStatus` at `0x140028401`
- `ntoskrnl!ExRaiseStatus` at `0x14002851c`
- `ntoskrnl!ObfDereferenceObject` at `0x14002879f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bc8f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005be35`
- `ntoskrnl!ObfDereferenceObject` at `0x14002879f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005bc8f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005be35`

## pseudocode

```c
__int64 __fastcall FatCommonCreate(PIRP *Context1, __int64 a2)
{
  __int64 v4; // r9
  __int64 v5; // rbx
  __int64 v6; // rsi
  unsigned __int16 v7; // ax
  _WORD *v8; // rcx
  _WORD *v9; // rax
  struct _UNICODE_STRING v11; // xmm6
  __int64 v12; // r14
  unsigned int v13; // r8d
  __int64 v14; // r13
  char v15; // cl
  unsigned int v16; // eax
  int v17; // ebx
  unsigned int v18; // eax
  bool v19; // zf
  unsigned int v20; // edx
  int v21; // ecx
  char v22; // dl
  __int64 v23; // r8
  PWSTR Buffer; // r9
  NTSTATUS v25; // ebx
  unsigned __int16 v26; // bx
  unsigned __int64 v27; // rcx
  __m128i *v28; // rax
  __m128i v29; // xmm1
  _WORD *v30; // xmm0_8
  _WORD *v31; // r14
  _WORD *v32; // xmm0_8
  unsigned __int64 v33; // rcx
  ULONG_PTR v34; // r14
  UNICODE_STRING v35; // xmm0
  __int64 v36; // rcx
  int v37; // eax
  ULONG_PTR Fcb; // r14
  __int64 v39; // rcx
  int v40; // eax
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // rdx
  _QWORD *v44; // rbx
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rcx
  unsigned __int64 v47; // rcx
  char v48; // al
  __int64 v49; // rcx
  NTSTATUS v50; // eax
  __int64 v51; // rbx
  __int64 v52; // rcx
  __int64 v53; // r10
  __int64 v54; // rdx
  int v55; // ebx
  __m128i *v56; // rax
  __int64 v57; // rdx
  struct _FILE_OBJECT *v58; // r14
  __int64 v59; // rdx
  __int64 v60; // r8
  __int64 v61; // r9
  __int64 v62; // rdx
  __int64 v63; // r8
  __int64 v64; // r9
  __int64 v65; // rdx
  __int64 v66; // r8
  __int64 v67; // r9
  char v68; // r14
  __int64 v69; // rcx
  __int64 v70; // r8
  struct _MDL *Mdl; // rdx
  unsigned __int64 v72; // rcx
  __int64 v73; // rax
  int PostIrpRoutine; // [rsp+C8h] [rbp-4D0h]
  int v75; // [rsp+D0h] [rbp-4C8h]
  int Name; // [rsp+D8h] [rbp-4C0h]
  int v77; // [rsp+E8h] [rbp-4B0h]
  char v78[8]; // [rsp+160h] [rbp-438h] BYREF
  char i; // [rsp+168h] [rbp-430h]
  char v80; // [rsp+169h] [rbp-42Fh]
  char v81; // [rsp+16Ah] [rbp-42Eh]
  char v82; // [rsp+16Bh] [rbp-42Dh]
  char v83; // [rsp+16Ch] [rbp-42Ch]
  char v84; // [rsp+16Dh] [rbp-42Bh] BYREF
  __int16 v85; // [rsp+16Eh] [rbp-42Ah]
  __m128i v86; // [rsp+170h] [rbp-428h]
  char v87; // [rsp+180h] [rbp-418h]
  char v88; // [rsp+181h] [rbp-417h]
  ULONG_PTR BugCheckParameter3; // [rsp+188h] [rbp-410h] BYREF
  unsigned int v90; // [rsp+190h] [rbp-408h]
  unsigned int v91; // [rsp+194h] [rbp-404h]
  unsigned int v92; // [rsp+198h] [rbp-400h]
  char v93; // [rsp+19Ch] [rbp-3FCh]
  char v94; // [rsp+19Dh] [rbp-3FBh]
  char v95; // [rsp+19Eh] [rbp-3FAh]
  char v96; // [rsp+19Fh] [rbp-3F9h]
  int v97; // [rsp+1A0h] [rbp-3F8h]
  PVOID Context2; // [rsp+1A8h] [rbp-3F0h]
  struct _UNICODE_STRING FirstName; // [rsp+1B0h] [rbp-3E8h] BYREF
  int v100; // [rsp+1C0h] [rbp-3D8h] BYREF
  int v101; // [rsp+1C4h] [rbp-3D4h]
  __int64 v102; // [rsp+1C8h] [rbp-3D0h]
  ULONG_PTR v103; // [rsp+1D0h] [rbp-3C8h] BYREF
  int v104; // [rsp+1D8h] [rbp-3C0h]
  int v105; // [rsp+1DCh] [rbp-3BCh]
  __int64 v106; // [rsp+1E0h] [rbp-3B8h] BYREF
  __int64 v107; // [rsp+1E8h] [rbp-3B0h] BYREF
  _STRING DestinationString; // [rsp+1F0h] [rbp-3A8h] BYREF
  ULONG_PTR v109[2]; // [rsp+200h] [rbp-398h] BYREF
  struct _UNICODE_STRING v110; // [rsp+210h] [rbp-388h] BYREF
  UNICODE_STRING SourceString; // [rsp+220h] [rbp-378h] BYREF
  int v112; // [rsp+230h] [rbp-368h]
  __int16 v113; // [rsp+234h] [rbp-364h]
  __int16 v114; // [rsp+238h] [rbp-360h]
  __int16 v115; // [rsp+23Ch] [rbp-35Ch]
  void *Src[2]; // [rsp+240h] [rbp-358h] BYREF
  __int64 v117; // [rsp+250h] [rbp-348h]
  PVOID Bcb; // [rsp+258h] [rbp-340h] BYREF
  int v119; // [rsp+260h] [rbp-338h]
  __int64 Dcb; // [rsp+268h] [rbp-330h] BYREF
  volatile signed __int32 *v121; // [rsp+278h] [rbp-320h]
  __int64 v122; // [rsp+280h] [rbp-318h]
  PIRP *v123; // [rsp+288h] [rbp-310h]
  UNICODE_STRING String1; // [rsp+290h] [rbp-308h] BYREF
  UNICODE_STRING v125; // [rsp+2A0h] [rbp-2F8h] BYREF
  int v126[4]; // [rsp+2B0h] [rbp-2E8h] BYREF
  __int64 v127; // [rsp+2C0h] [rbp-2D8h] BYREF
  STRING v128; // [rsp+2D0h] [rbp-2C8h] BYREF
  ULONG_PTR v129; // [rsp+2E0h] [rbp-2B8h]
  __int64 v130; // [rsp+2E8h] [rbp-2B0h]
  int v131; // [rsp+2F0h] [rbp-2A8h]
  int v132; // [rsp+2F4h] [rbp-2A4h]
  __int64 v133; // [rsp+2F8h] [rbp-2A0h] BYREF
  int v134; // [rsp+300h] [rbp-298h]
  struct _UNICODE_STRING RemainingName; // [rsp+310h] [rbp-288h] BYREF
  __int64 v136[2]; // [rsp+320h] [rbp-278h] BYREF
  UNICODE_STRING v137; // [rsp+330h] [rbp-268h] BYREF
  __int64 v138; // [rsp+340h] [rbp-258h] BYREF
  struct _UNICODE_STRING v139; // [rsp+350h] [rbp-248h]
  UNICODE_STRING v140[5]; // [rsp+360h] [rbp-238h] BYREF
  UNICODE_STRING Path; // [rsp+3B0h] [rbp-1E8h] BYREF
  ANSI_STRING DbcsName; // [rsp+3C0h] [rbp-1D8h] BYREF
  _STRING v143; // [rsp+3D0h] [rbp-1C8h] BYREF
  char v144[16]; // [rsp+3E0h] [rbp-1B8h] BYREF
  char v145[16]; // [rsp+3F0h] [rbp-1A8h] BYREF
  char v146[16]; // [rsp+400h] [rbp-198h] BYREF
  char v147[16]; // [rsp+410h] [rbp-188h] BYREF
  char v148[16]; // [rsp+420h] [rbp-178h] BYREF
  int v149; // [rsp+430h] [rbp-168h] BYREF
  char v150[16]; // [rsp+440h] [rbp-158h] BYREF
  __int64 v151; // [rsp+450h] [rbp-148h] BYREF
  char v152; // [rsp+460h] [rbp-138h] BYREF
  char v153; // [rsp+478h] [rbp-120h] BYREF
  char v154; // [rsp+490h] [rbp-108h] BYREF
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+4D0h] [rbp-C8h] BYREF
  char v156; // [rsp+510h] [rbp-88h] BYREF

  Context2 = (PVOID)a2;
  v123 = Context1;
  v151 = a2;
  v86 = 0;
  v78[0] = 0;
  BugCheckParameter3 = 0;
  v133 = 0;
  FirstName = 0;
  v110 = 0;
  RemainingName = 0;
  SourceString = 0;
  DestinationString = 0;
  v107 = 0;
  Bcb = 0;
  LODWORD(v106) = 0;
  v84 = 0;
  v100 = 0;
  memset(v140, 0, sizeof(v140));
  *(_OWORD *)Src = 0;
  *(_OWORD *)v136 = 0;
  v5 = *(_QWORD *)(a2 + 184);
  *(_QWORD *)v126 = v5;
  v6 = *(_QWORD *)(v5 + 48);
  v7 = *(_WORD *)(v6 + 88);
  if ( v7 > 2u )
  {
    v8 = *(_WORD **)(v6 + 96);
    if ( v8[1] == 92 && *v8 == 92 )
    {
      *(_WORD *)(v6 + 88) = v7 - 2;
      memmove(
        *(void **)(*(_QWORD *)(v5 + 48) + 96LL),
        (const void *)(*(_QWORD *)(*(_QWORD *)(v5 + 48) + 96LL) + 2LL),
        *(unsigned __int16 *)(*(_QWORD *)(v5 + 48) + 88LL));
      v6 = *(_QWORD *)(v5 + 48);
      if ( *(_WORD *)(v6 + 88) > 2u )
      {
        v9 = *(_WORD **)(v6 + 96);
        if ( v9[1] == 92 && *v9 == 92 )
          return 3221225523LL;
      }
    }
  }
  v11 = *(struct _UNICODE_STRING *)(v6 + 88);
  v139 = v11;
  v12 = *(_QWORD *)(v6 + 64);
  *(_QWORD *)&String1.Length = v12;
  v105 = *(_DWORD *)(a2 + 88);
  v127 = *(_QWORD *)(a2 + 24);
  v103 = *(_QWORD *)(v5 + 8);
  v13 = *(_DWORD *)(v5 + 16);
  v97 = v13;
  v85 = *(_WORD *)(v5 + 24);
  *(_WORD *)&v78[6] = *(_WORD *)(v5 + 26);
  v101 = *(_DWORD *)(v5 + 32);
  if ( v12 )
    *(_QWORD *)(v6 + 16) = *(_QWORD *)(v12 + 16);
  if ( (v13 & 0x2000) != 0 )
    return 3221225474LL;
  v14 = *(_QWORD *)(v5 + 40) + 416LL;
  v117 = v14;
  v15 = v13 & 1;
  v78[4] = v13 & 1;
  v16 = v13 >> 9;
  LOBYTE(v16) = (v13 & 0x200) != 0;
  v90 = v16;
  v17 = v13 & 0x1000;
  LODWORD(v109[0]) = v17;
  v78[2] = v17 != 0;
  v18 = HIWORD(v13);
  LOBYTE(v18) = BYTE2(v13) & 1;
  v91 = v18;
  v88 = BYTE2(v13) & 1;
  v19 = (*(_WORD *)(*(_QWORD *)v126 + 24LL) & 0x100) == 0;
  v112 = *(_WORD *)(*(_QWORD *)v126 + 24LL) & 0x100;
  v83 = !v19;
  v20 = HIBYTE(v13);
  v92 = HIBYTE(v13);
  v78[1] = *(_BYTE *)(*(_QWORD *)v126 + 2LL);
  v78[3] = (v78[1] & 2) != 0;
  if ( (v13 & 1) == 0 || (v87 = 1, v20 - 2 > 1) )
    v87 = 0;
  if ( !v15 || (v82 = 1, ((v20 - 1) & 0xFFFFFFFD) != 0) )
    v82 = 0;
  v121 = (volatile signed __int32 *)(v14 + 200);
  if ( (*(_DWORD *)(v14 + 200) & 0x400000) != 0 && (*((_DWORD *)Context1 + 17) & 0x80000) != 0 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    *((_DWORD *)Context1 + 17) &= ~0x80000u;
    v15 = v78[4];
    LOBYTE(v13) = v97;
  }
  if ( *((_DWORD *)Context2 + 23) )
    return 3221225485LL;
  v104 = v13 & 0x40;
  if ( v15 )
  {
    if ( (v13 & 0x40) != 0 )
      return 3221225485LL;
  }
  if ( !(unsigned __int8)FatAcquireExclusiveVcb_Real(Context1, v14, 0, v4) )
    return FatFsdPostRequest(Context1, Context2);
  *(_QWORD *)&v137.Length = *(_QWORD *)v126;
  v21 = v97 & 8;
  v97 = v21;
  v115 = v112;
  v22 = v78[1] & 4;
  v78[1] &= 4u;
  *(_QWORD *)&v125.Length = v14 + 200;
  if ( (*(_DWORD *)(v14 + 200) & 0x200) != 0 )
    KeBugCheckEx(0x23u, 0x60393u, 0, 0, 0);
  v122 = 0;
  v80 = 0;
  i = 1;
  v81 = 0;
  v130 = v6;
  v132 = v105;
  *(_QWORD *)&v128.Length = v127;
  v102 = v103 + 16;
  v114 = *(_WORD *)&v78[6];
  v131 = v101;
  v85 &= 0x4027u;
  v113 = v85;
  v134 = v104;
  LODWORD(Dcb) = v21;
  v93 = v90;
  v94 = v78[2];
  v95 = v83;
  v96 = v22;
  Bcb = 0;
  *(_DWORD *)&DestinationString.Length = 0x400000;
  DestinationString.Buffer = &v154;
  *(_DWORD *)&SourceString.Length = 0x400000;
  SourceString.Buffer = (PWSTR)&CompletionRoutine;
  LODWORD(Src[0]) = 0x400000;
  Src[1] = &v156;
  FatVerifyVcb(Context1, v14);
  if ( (*(_DWORD *)(v14 + 200) & 1) != 0 )
  {
    v25 = -1073741202;
    if ( *(_DWORD *)(v14 + 204) == 1 )
      v25 = -1073741790;
LABEL_228:
    v86.m128i_i32[0] = v25;
    goto LABEL_229;
  }
  if ( v17 && (*(_DWORD *)(v14 + 200) & 0x4000) != 0 )
  {
    IoSetHardErrorOrVerifyDevice(Context1[5], *(PDEVICE_OBJECT *)(*(_QWORD *)(v14 + 192) + 16LL));
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 192) + 16LL) + 48LL) |= 2u;
    *((_DWORD *)Context1 + 18) = -1073741662;
    ExRaiseStatus(-1073741662);
  }
  if ( v127 )
  {
    v25 = -1073741745;
LABEL_37:
    v86.m128i_i32[0] = v25;
    goto LABEL_235;
  }
  v26 = _mm_cvtsi128_si32((__m128i)v11);
  if ( !v26 )
  {
    v138 = 0;
    if ( !v12 || (unsigned int)FatDecodeFileObject(v12, &v138, &BugCheckParameter3, &v133) == 4 )
    {
      if ( v78[4] )
      {
        v25 = -1073741565;
      }
      else
      {
        if ( !v78[1] )
        {
          v27 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
          ++*(_DWORD *)(v27 + *(_QWORD *)(v14 + 1024) + 56);
          v28 = (__m128i *)FatOpenVolume(v126, Context1, v6, v14, v102, *(_WORD *)&v78[6], v92);
          goto LABEL_46;
        }
        v25 = -1073741811;
      }
      goto LABEL_37;
    }
  }
  if ( v12 )
  {
    v109[0] = 0;
    v103 = 0;
    v133 = 0;
    if ( (unsigned int)FatDecodeFileObject(v12, v109, &v103, &v133) - 2 > 1 )
    {
      v25 = -1073741766;
      goto LABEL_37;
    }
    v30 = (_WORD *)_mm_srli_si128((__m128i)v11, 8).m128i_u64[0];
    v31 = v30;
    if ( v26 && *v30 == 92 )
    {
LABEL_53:
      v25 = -1073741773;
      goto LABEL_37;
    }
    *(_QWORD *)(v6 + 16) = *(_QWORD *)(*(_QWORD *)&String1.Length + 16LL);
    v109[0] = v103;
    FatVerifyFcb(Context1, v103);
  }
  else
  {
    v32 = (_WORD *)_mm_srli_si128((__m128i)v11, 8).m128i_u64[0];
    v31 = v32;
    if ( v26 == 2 && *v32 == 92 )
    {
      if ( v104 )
      {
        v25 = -1073741638;
      }
      else if ( v78[1] )
      {
        v25 = -1073741811;
      }
      else
      {
        if ( !LODWORD(v109[0]) )
        {
          v33 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
          ++*(_DWORD *)(v33 + *(_QWORD *)(v14 + 1024) + 56);
          v28 = (__m128i *)FatOpenRootDcb(&v127, Context1, v6, v14, v102, *(_WORD *)&v78[6], v92);
          goto LABEL_46;
        }
        v25 = -1073741535;
      }
      goto LABEL_59;
    }
    v109[0] = *(_QWORD *)(v14 + 208);
    v103 = v109[0];
    FatVerifyFcb(Context1, v109[0]);
  }
  if ( v26 && v31[((unsigned __int64)v26 >> 1) - 1] == 92 )
  {
    v26 -= 2;
    v139.Length = v26;
    v78[4] = 1;
    v11 = v139;
  }
  else
  {
    v78[4] = 0;
  }
  v34 = v109[0];
  if ( !*(_QWORD *)(v109[0] + 536) )
    FatSetFullFileNameInFcb((int)Context1);
  if ( (unsigned __int16)(*(_WORD *)(v34 + 528) + v26 + 2) <= v26 )
  {
    v25 = -1073741773;
LABEL_59:
    v86.m128i_i32[0] = v25;
    goto LABEL_235;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      BugCheckParameter3 = v34;
      v110 = v11;
      do
      {
        v35 = v110;
        v110.Length = _mm_cvtsi128_si32((__m128i)v110);
        if ( !v110.Length )
          break;
        v129 = 0;
        Path = v35;
        FsRtlDissectName(&Path, &FirstName, &RemainingName);
        if ( RemainingName.Length && *RemainingName.Buffer == 92 || FirstName.Length > 0x1FEu )
          goto LABEL_53;
        FatEnsureStringBufferEnough(&DestinationString);
        v25 = RtlUpcaseUnicodeStringToCountedOemString(&DestinationString, &FirstName, 0);
        if ( (*(_DWORD *)(v14 + 200) & 0x400000) != 0 )
        {
          LOBYTE(v36) = *(_BYTE *)Buf1;
          v37 = *DestinationString.Buffer == *(_BYTE *)Buf1
              ? FatCompareNames(&DestinationString, &_EFS_SHORT)
              : *DestinationString.Buffer >= *(_BYTE *)Buf1;
          if ( v37 == 2 )
          {
LABEL_84:
            v25 = -1073741790;
            v86.m128i_i32[0] = -1073741790;
            goto LABEL_235;
          }
        }
        if ( v25 < 0 )
        {
          Fcb = 0;
          v129 = 0;
          DestinationString.Length = 0;
          if ( v25 != -1073741470 )
          {
            v86.m128i_i32[0] = v25;
            goto LABEL_229;
          }
        }
        else
        {
          Fcb = FatFindFcb(v36, BugCheckParameter3 + 384, &DestinationString, v78);
          v129 = Fcb;
        }
        if ( !Fcb )
        {
          if ( *(_QWORD *)(BugCheckParameter3 + 392) )
          {
            FatEnsureStringBufferEnough(&SourceString);
            RtlDowncaseUnicodeString(&SourceString, &FirstName, 0);
            RtlUpcaseUnicodeString(&SourceString, &SourceString, 0);
            if ( (*(_DWORD *)(v14 + 200) & 0x400000) != 0 )
            {
              LOBYTE(v39) = *(_BYTE *)_EFS.Buffer;
              v40 = *(_BYTE *)FirstName.Buffer == *(_BYTE *)_EFS.Buffer
                  ? FatCompareNames(&FirstName, &_EFS)
                  : *(_BYTE *)FirstName.Buffer >= *(_BYTE *)_EFS.Buffer;
              if ( v40 == 2 )
                goto LABEL_84;
            }
            Fcb = FatFindFcb(v39, BugCheckParameter3 + 392, &SourceString, v78);
            v129 = Fcb;
          }
          if ( !Fcb )
            break;
        }
        if ( v78[0]
          && (*(_DWORD *)(&String1.MaximumLength + 1) = 0,
              String1.Buffer = (PWSTR)&v152,
              *(_DWORD *)&String1.Length = 1572864,
              RtlOemStringToCountedUnicodeString(&String1, (PCOEM_STRING)(Fcb + 480), 0),
              RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(Fcb + 552), 1u)) )
        {
          RtlCopyUnicodeString(&FirstName, &String1);
          v41 = *(_DWORD *)(Fcb + 192) >> 13;
          LOBYTE(v41) = (*(_DWORD *)(Fcb + 192) & 0x2000) != 0;
          v42 = *(_DWORD *)(Fcb + 192) >> 12;
          LOBYTE(v42) = (*(_DWORD *)(Fcb + 192) & 0x1000) != 0;
          FatUnicodeRestoreShortNameCase(&FirstName, v42, v41);
        }
        else
        {
          memmove(FirstName.Buffer, *(const void **)(Fcb + 560), FirstName.Length);
        }
        BugCheckParameter3 = Fcb;
        v110 = RemainingName;
        if ( *(_WORD *)Fcb == 1282 )
          break;
      }
      while ( RemainingName.Length );
      if ( v110.Length && *v110.Buffer == 92 )
      {
        v110.Length -= 2;
        ++v110.Buffer;
      }
      FatVerifyFcb(Context1, BugCheckParameter3);
      v34 = v109[0];
      v43 = 1282;
      v23 = *(_QWORD *)v126;
      v44 = Context2;
      Buffer = (PWSTR)v92;
      if ( *(_DWORD *)(BugCheckParameter3 + 196) == 1 )
        break;
      FatRemoveNames(BugCheckParameter3, BugCheckParameter3);
    }
    if ( !v78[3] )
    {
      if ( (*(_DWORD *)(BugCheckParameter3 + 192) & 0x80u) != 0 )
      {
        v25 = -1073741790;
        v86.m128i_i32[0] = -1073741790;
        goto LABEL_236;
      }
      goto LABEL_120;
    }
    if ( !i
      || *(_WORD *)BugCheckParameter3 != 1282
      || (__int64 *)qword_140017D58 == &qword_140017D58 && (__int64 *)qword_140017D70 == &qword_140017D70 )
    {
      break;
    }
    FatFspClose(v14, 1282, *(_QWORD *)v126, v92);
    i = 0;
  }
  if ( *(_WORD *)BugCheckParameter3 == 1282 && (*(_DWORD *)(BugCheckParameter3 + 192) & 4) == 0 )
  {
    v25 = -1073741757;
LABEL_117:
    v86.m128i_i32[0] = v25;
    goto LABEL_236;
  }
LABEL_120:
  if ( (*(_DWORD *)(BugCheckParameter3 + 192) & 1) != 0 )
  {
    v25 = -1073741738;
    goto LABEL_117;
  }
  if ( !v110.Length )
  {
    if ( v78[1] )
    {
      v45 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
      ++*(_DWORD *)(v45 + *(_QWORD *)(v14 + 1024) + 56);
      v29 = *(__m128i *)FatOpenTargetDirectory(
                          &Dcb,
                          Context1,
                          v6,
                          *(_QWORD *)(BugCheckParameter3 + 176),
                          v102,
                          *(_WORD *)&v78[6],
                          1,
                          v78[0]);
      v86 = v29;
      v44[7] = _mm_srli_si128(v29, 8).m128i_u64[0];
      goto LABEL_47;
    }
    if ( (unsigned __int16)(*(_WORD *)BugCheckParameter3 - 1283) <= 1u )
    {
      if ( !v104 )
      {
        v47 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
        ++*(_DWORD *)(v47 + *(_QWORD *)(v14 + 1024) + 56);
        v86 = *(__m128i *)FatOpenExistingDcb(
                            v145,
                            Context1,
                            v23,
                            v6,
                            v14,
                            BugCheckParameter3,
                            v102,
                            *(_WORD *)&v78[6],
                            (_DWORD)Buffer,
                            (_BYTE)v90,
                            v78[2],
                            (_BYTE)v91,
                            v78[0],
                            &v84);
        v25 = _mm_cvtsi128_si32(v86);
        if ( v25 == 259 )
          v80 = 1;
        else
          *((_QWORD *)Context2 + 7) = v86.m128i_i64[1];
        goto LABEL_229;
      }
      v25 = -1073741638;
      goto LABEL_129;
    }
    if ( *(_WORD *)BugCheckParameter3 != 1282 )
      KeBugCheckEx(0x23u, 0x60675u, *(unsigned __int16 *)BugCheckParameter3, BugCheckParameter3, 0);
    if ( v82 )
    {
      v25 = -1073741565;
LABEL_129:
      v86.m128i_i32[0] = v25;
      goto LABEL_236;
    }
    if ( v78[4] )
    {
      v25 = -1073741773;
      goto LABEL_129;
    }
    v46 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
    ++*(_DWORD *)(v46 + *(_QWORD *)(v14 + 1024) + 56);
    v86 = *(__m128i *)FatOpenExistingFcb(
                        v144,
                        Context1,
                        v23,
                        v6,
                        v14,
                        BugCheckParameter3,
                        v102,
                        *(_WORD *)&v78[6],
                        v105,
                        v127,
                        v101,
                        v85,
                        (_DWORD)Buffer,
                        (_BYTE)v90,
                        v78[2],
                        (_BYTE)v91,
                        v78[0],
                        &v84);
    v25 = _mm_cvtsi128_si32(v86);
    if ( v25 == 259 )
    {
      v80 = 1;
      goto LABEL_229;
    }
LABEL_133:
    if ( v25 >= 0 && !v97 )
      *(_DWORD *)(v6 + 80) |= 0x40u;
    *((_QWORD *)Context2 + 7) = v86.m128i_i64[1];
    goto LABEL_229;
  }
  if ( (unsigned __int16)(*(_WORD *)BugCheckParameter3 - 1283) > 1u )
  {
    v25 = -1073741766;
    goto LABEL_129;
  }
  Dcb = BugCheckParameter3;
  v48 = 1;
  for ( i = 1; ; v48 = i )
  {
    if ( v48 )
    {
      i = 0;
      v110 = RemainingName;
      if ( DestinationString.Length )
        goto LABEL_157;
      v25 = -1073741470;
    }
    else
    {
      v137 = v110;
      FsRtlDissectName(&v137, &FirstName, &v110);
      if ( v110.Length && *v110.Buffer == 92 || FirstName.Length > 0x1FEu )
        goto LABEL_153;
      FatEnsureStringBufferEnough(&DestinationString);
      v25 = RtlUpcaseUnicodeStringToCountedOemString(&DestinationString, &FirstName, 0);
    }
    if ( v25 >= 0 )
    {
LABEL_157:
      DbcsName = DestinationString;
      if ( FsRtlIsFatDbcsLegal(&DbcsName, 0, 0, 0) )
      {
        v143 = DestinationString;
        FatStringTo8dot3(v49, &v143, &v140[2]);
        v23 = *(_DWORD *)(&v140[0].MaximumLength + 1) & 0xFF000000;
        *(_DWORD *)(&v140[0].MaximumLength + 1) &= 0xFF000000;
      }
      else
      {
        v23 = *(_DWORD *)(&v140[0].MaximumLength + 1) & 0xFF000000 | 2;
        *(_DWORD *)(&v140[0].MaximumLength + 1) = *(_DWORD *)(&v140[0].MaximumLength + 1) & 0xFF000000 | 2;
      }
      goto LABEL_159;
    }
    v23 = *(_DWORD *)(&v140[0].MaximumLength + 1) & 0xFF000000 | 2;
    *(_DWORD *)(&v140[0].MaximumLength + 1) = *(_DWORD *)(&v140[0].MaximumLength + 1) & 0xFF000000 | 2;
    if ( v25 != -1073741470 )
    {
      v86.m128i_i32[0] = v25;
      goto LABEL_229;
    }
LABEL_159:
    if ( (byte_140017D4C & 1) != 0 )
    {
      v23 = 0;
      v119 = 0;
      Buffer = FirstName.Buffer;
      while ( (unsigned int)v23 < FirstName.Length >> 1 )
      {
        if ( FirstName.Buffer[(unsigned int)v23] < 0x80u
          && SLOBYTE(FirstName.Buffer[(unsigned int)v23]) >= 0
          && (*((_BYTE *)FsRtlLegalAnsiCharacterArray + FirstName.Buffer[(unsigned int)v23]) & 2) == 0 )
        {
          goto LABEL_165;
        }
        v23 = (unsigned int)(v23 + 1);
        v119 = v23;
      }
    }
    else if ( (v23 & 2) != 0 )
    {
LABEL_165:
      v25 = -1073741773;
      v86.m128i_i32[0] = -1073741773;
      goto LABEL_235;
    }
    FatEnsureStringBufferEnough(&SourceString);
    v50 = RtlUpcaseUnicodeString(&SourceString, &FirstName, 0);
    v25 = v50;
    if ( v50 < 0 )
    {
      v86.m128i_i32[0] = v50;
      goto LABEL_229;
    }
    v140[3] = SourceString;
    LOBYTE(v140[0].Buffer) = 0;
    LOWORD(Src[0]) = 0;
    if ( (*(_DWORD *)(v14 + 200) & 0x400000) != 0 )
    {
      if ( v92 == 1 || v92 == 4 )
      {
        v81 = 0;
        v100 = 2;
      }
      else
      {
        v81 = 1;
        v100 = 15;
      }
    }
    v51 = Dcb;
    FatLocateDirent(
      (int)Context1,
      Dcb,
      (int)v140,
      0,
      (__int64)&v100,
      (__int64)&v107,
      (__int64)&Bcb,
      (__int64)&v106,
      (__int64)v78,
      (PCUNICODE_STRING)Src,
      (__int64)v136);
    v122 = v51;
    v53 = v107;
    if ( v107 )
    {
      if ( !v78[0] )
        goto LABEL_180;
      *(_DWORD *)(&v128.MaximumLength + 1) = 0;
      *(_DWORD *)(&v125.MaximumLength + 1) = 0;
      v125.Buffer = (PWSTR)&v153;
      *(_DWORD *)&v125.Length = 1572864;
      v128.Buffer = (PCHAR)&v151;
      *(_DWORD *)&v128.Length = 786432;
      LOBYTE(v23) = 1;
      Fat8dot3ToString(v52, v107, v23, &v128);
      RtlOemStringToCountedUnicodeString(&v125, &v128, 0);
      if ( RtlCompareUnicodeString(&v125, (PCUNICODE_STRING)Src, 1u) )
        RtlCopyUnicodeString(&FirstName, &v125);
      else
LABEL_180:
        memmove(FirstName.Buffer, Src[1], FirstName.Length);
      v53 = v107;
    }
    if ( !v110.Length )
      break;
    if ( !v53 )
    {
      v25 = -1073741766;
      goto LABEL_154;
    }
    if ( (*(_BYTE *)(v53 + 11) & 0x10) == 0 )
    {
      v25 = -1073741766;
      goto LABEL_228;
    }
    Dcb = FatCreateDcb(
            (unsigned int)Src,
            v14,
            v51,
            v106 - 32 * ((((unsigned __int64)LOWORD(v136[0]) >> 1) + 12) / 0xD),
            v106,
            v53,
            (__int64)Src);
    v122 = Dcb;
    FatSetFullNameInFcb(Context1, Dcb, &FirstName);
  }
  if ( (*(_DWORD *)(v14 + 200) & 0x400000) != 0 && v81 && v107 )
    FatSearchRemainderOfDirectoryForCollisions((_DWORD)Context1, v51, (unsigned int)v140, (__int64)&v100);
  if ( v78[1] )
  {
    LOBYTE(Name) = v78[0];
    LOBYTE(v75) = v107 != 0;
    LOWORD(PostIrpRoutine) = *(_WORD *)&v78[6];
    v28 = (__m128i *)FatOpenTargetDirectory(v150, Context1, v6, v51, v102, PostIrpRoutine, v75, Name);
    goto LABEL_46;
  }
  v23 = v107;
  if ( !v107 )
  {
    if ( v92 == 1 || v92 == 4 )
    {
      v25 = -1073741772;
      goto LABEL_154;
    }
    if ( (*(_BYTE *)(&v140[0].MaximumLength + 1) & 2) != 0 )
      DestinationString.Length = 0;
    v25 = FatCheckSystemSecurityAccess(Context1);
    v86.m128i_i32[0] = v25;
    if ( v25 < 0 )
      goto LABEL_229;
    if ( v87 )
    {
      if ( (*(_DWORD *)(v14 + 200) & 0x4000) != 0 )
      {
        IoSetHardErrorOrVerifyDevice(Context1[5], *(PDEVICE_OBJECT *)(*(_QWORD *)(v14 + 192) + 16LL));
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 192) + 16LL) + 48LL) |= 2u;
        *((_DWORD *)Context1 + 18) = -1073741662;
        ExRaiseStatus(-1073741662);
      }
      if ( (_WORD)v112 )
      {
        v25 = -1073741811;
        goto LABEL_154;
      }
      LOWORD(v77) = *(_WORD *)&v78[6];
      v28 = (__m128i *)FatCreateNewDirectory(
                         v148,
                         Context1,
                         *(_QWORD *)v126,
                         v6,
                         v14,
                         Dcb,
                         &DestinationString,
                         &FirstName,
                         v102,
                         v77,
                         v127,
                         v101,
                         v85,
                         (_BYTE)v90,
                         v78[2],
                         (_BYTE)v91);
      goto LABEL_46;
    }
    if ( !v78[4] )
    {
      if ( (*(_DWORD *)(v14 + 200) & 0x4000) != 0 )
      {
        IoSetHardErrorOrVerifyDevice(Context1[5], *(PDEVICE_OBJECT *)(*(_QWORD *)(v14 + 192) + 16LL));
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v14 + 192) + 16LL) + 48LL) |= 2u;
        *((_DWORD *)Context1 + 18) = -1073741662;
        ExRaiseStatus(-1073741662);
      }
      if ( (*(_DWORD *)(v14 + 200) & 0x400000) != 0 && (v100 & 0xC10) != 0 )
        goto LABEL_203;
      v56 = (__m128i *)FatCreateNewFile(
                         (int)&v149,
                         (int)Context1,
                         v126[0],
                         v6,
                         v14,
                         Dcb,
                         (__int64)&DestinationString,
                         &FirstName,
                         v102,
                         *(__int16 *)&v78[6],
                         v105,
                         v127,
                         v101,
                         v85,
                         (__int64)Src,
                         v78[3],
                         v90,
                         v78[2],
                         v91,
                         v83);
      goto LABEL_205;
    }
LABEL_153:
    v25 = -1073741773;
LABEL_154:
    v86.m128i_i32[0] = v25;
    goto LABEL_235;
  }
  v54 = 32 * (unsigned int)((((unsigned __int64)LOWORD(v136[0]) >> 1) + 12) / 0xD);
  v55 = v106 - v54;
  if ( (*(_BYTE *)(v107 + 11) & 0x10) == 0 )
  {
    if ( v82 )
    {
      v25 = -1073741565;
      goto LABEL_154;
    }
    if ( !v78[4] )
    {
      if ( (*(_DWORD *)(v14 + 200) & 0x400000) != 0 && (v100 & 0x20) != 0 && (*(_BYTE *)(v107 + 12) & 1) != 0 )
      {
        LOBYTE(v54) = 1;
        if ( (unsigned __int8)FatFileExtensionIsPfile(v136, v54) )
        {
LABEL_203:
          v25 = -1073741790;
          v86.m128i_i32[0] = -1073741790;
          goto LABEL_235;
        }
      }
      v56 = (__m128i *)FatOpenExistingFile(
                         v147,
                         Context1,
                         v6,
                         v14,
                         &BugCheckParameter3,
                         Dcb,
                         v107,
                         v55,
                         v106,
                         Src,
                         v136,
                         v102,
                         *(_WORD *)&v78[6],
                         v105,
                         v127,
                         v101,
                         v85,
                         v92,
                         v78[3],
                         (_BYTE)v90,
                         v78[2],
                         (_BYTE)v91,
                         v78[0]);
LABEL_205:
      v86 = *v56;
      v25 = _mm_cvtsi128_si32(v86);
      goto LABEL_133;
    }
    goto LABEL_153;
  }
  if ( v104 )
  {
    v25 = -1073741638;
    goto LABEL_154;
  }
  v28 = (__m128i *)FatOpenExistingDirectory(
                     v146,
                     Context1,
                     *(_QWORD *)v126,
                     v6,
                     v14,
                     &BugCheckParameter3,
                     Dcb,
                     v107,
                     (int)v106 - (int)v54,
                     v106,
                     Src,
                     v102,
                     *(_WORD *)&v78[6],
                     v92,
                     (_BYTE)v90);
LABEL_46:
  v29 = *v28;
  v86 = v29;
  *((_QWORD *)Context2 + 7) = _mm_srli_si128(v29, 8).m128i_u64[0];
LABEL_47:
  v25 = _mm_cvtsi128_si32(v29);
LABEL_229:
  if ( v25 >= 0 && !v78[1] )
  {
    v57 = *(_QWORD *)(v6 + 24);
    if ( v57 )
    {
      if ( (unsigned __int16)(*(_WORD *)v57 - 1282) <= 1u && !*(_QWORD *)(v57 + 536) )
        FatSetFullNameInFcb(Context1, v57, &FirstName);
    }
  }
LABEL_235:
  v43 = 1282;
LABEL_236:
  if ( v25 < 0
    && (_BYTE)v91
    && v25 != -1073739511
    && *((_DWORD *)Context1 + 18) != -1073739511
    && BugCheckParameter3
    && (unsigned __int16)(*(_WORD *)BugCheckParameter3 - 1282) <= 2u )
  {
    FsRtlCheckOplockEx((POPLOCK)(BugCheckParameter3 + 88), Context1[5], 4u, 0, 0, 0);
  }
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  if ( v25 < 0 )
  {
    LODWORD(Dcb) = *((_DWORD *)Context1 + 17);
    *((_DWORD *)Context1 + 17) = Dcb | 0x808;
    FatUnpinRepinnedBcbs(Context1, v43, v23, Buffer);
    if ( v122 )
    {
      if ( *(_WORD *)v122 == 1283 && *(_QWORD *)(v122 + 320) == v122 + 320 && !*(_DWORD *)(v122 + 232) )
      {
        v58 = *(struct _FILE_OBJECT **)(v122 + 344);
        if ( v58 )
        {
          *(_QWORD *)(v122 + 344) = 0;
          CcUninitializeCacheMap(v58, 0, 0);
          ObfDereferenceObject(v58);
        }
      }
    }
    *((_DWORD *)Context1 + 17) = Dcb;
  }
  FatFreeStringBuffer(&DestinationString, v43, v23, Buffer);
  FatFreeStringBuffer(&SourceString, v59, v60, v61);
  FatFreeStringBuffer(Src, v62, v63, v64);
  v68 = v80;
  if ( v80 )
  {
    if ( !v84 )
    {
      v25 = FatFsdPostRequest(Context1, Context2);
      v86.m128i_i32[0] = v25;
    }
  }
  else
  {
    FatUnpinRepinnedBcbs(Context1, v65, v66, v67);
  }
  ExReleaseResourceLite((PERESOURCE)(v14 + 520));
  if ( !v68 )
  {
    if ( (*(_DWORD *)v102 & 0x20) != 0 )
      *(_DWORD *)(v6 + 80) |= 0x80000u;
    if ( v78[3] && v25 >= 0 )
    {
      if ( !FatReserveMdl )
      {
        Mdl = IoAllocateMdl(0, 0x10000u, 1u, 0, 0);
        _InterlockedCompareExchange64(&FatReserveMdl, (signed __int64)Mdl, 0);
        if ( (struct _MDL *)FatReserveMdl != Mdl )
          IoFreeMdl(Mdl);
      }
      _InterlockedOr(v121, 0x800u);
      if ( (*(_DWORD *)(v14 + 200) & 2) != 0 )
      {
        LOBYTE(v70) = 1;
        FatToggleMediaEjectDisable(v69, v14, v70);
      }
    }
  }
  v72 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
  v73 = *(_QWORD *)(v14 + 1024);
  if ( v25 )
    ++*(_DWORD *)(v72 + v73 + 64);
  else
    ++*(_DWORD *)(v72 + v73 + 60);
  return (unsigned int)v25;
}

```

## disassembly

```asm
0x1400268c0  mov     r11, rsp
0x1400268c3  mov     [r11+18h], rbx
0x1400268c7  mov     [r11+20h], rsi
0x1400268cb  push    rdi
0x1400268cc  push    r12
0x1400268ce  push    r13
0x1400268d0  push    r14
0x1400268d2  push    r15
0x1400268d4  sub     rsp, 4D0h
0x1400268db  movaps  xmmword ptr [r11-38h], xmm6
0x1400268e0  mov     rax, cs:__security_cookie
0x1400268e7  xor     rax, rsp
0x1400268ea  mov     [rsp+4F8h+var_48], rax
0x1400268f2  mov     r13, rdx
0x1400268f5  mov     [rsp+4F8h+Context2], rdx
0x1400268fd  mov     r15, rcx
0x140026900  mov     [rsp+4F8h+var_310], rcx
0x140026908  mov     [rsp+4F8h+var_148], rdx
0x140026910  xorps   xmm0, xmm0
0x140026913  movups  [rsp+4F8h+var_428], xmm0
0x14002691b  xor     edi, edi
0x14002691d  mov     [rsp+4F8h+var_438], dil
0x140026925  mov     [r11-410h], rdi
0x14002692c  mov     [r11-2A0h], rdi
0x140026933  movups  xmmword ptr [rsp+4F8h+FirstName.Length], xmm0
0x14002693b  xorps   xmm1, xmm1
0x14002693e  movups  xmmword ptr [rsp+4F8h+var_388.Length], xmm1
0x140026946  movups  xmmword ptr [rsp+4F8h+RemainingName.Length], xmm0
0x14002694e  movups  xmmword ptr [rsp+4F8h+SourceString.Length], xmm1
0x140026956  movups  xmmword ptr [rsp+4F8h+DestinationString.Length], xmm0
0x14002695e  mov     [r11-3B0h], rdi
0x140026965  mov     [r11-340h], rdi
0x14002696c  mov     dword ptr [rsp+4F8h+var_3B8], edi
0x140026973  mov     [rsp+4F8h+var_42B], dil
0x14002697b  mov     dword ptr [rsp+4F8h+var_3D8], edi
0x140026982  xor     edx, edx; Val
0x140026984  lea     r8d, [rdi+50h]; Size
0x140026988  lea     rcx, [r11-238h]; void *
0x14002698f  call    memset
0x140026994  xorps   xmm0, xmm0
0x140026997  movups  xmmword ptr [rsp+4F8h+Src], xmm0
0x14002699f  xorps   xmm1, xmm1
0x1400269a2  movups  xmmword ptr [rsp+4F8h+var_278], xmm1
0x1400269aa  mov     rbx, [r13+0B8h]
0x1400269b1  mov     qword ptr [rsp+4F8h+var_2E8], rbx
0x1400269b9  mov     rsi, [rbx+30h]
0x1400269bd  movzx   eax, word ptr [rsi+58h]
0x1400269c1  lea     r14d, [rdi+2]
0x1400269c5  cmp     ax, r14w
0x1400269c9  jbe     short loc_140026A25
0x1400269cb  mov     rcx, [rsi+60h]
0x1400269cf  mov     r12w, 5Ch ; '\'
0x1400269d4  cmp     [rcx+2], r12w
0x1400269d9  jnz     short loc_140026A25
0x1400269db  cmp     [rcx], r12w
0x1400269df  jnz     short loc_140026A25
0x1400269e1  sub     ax, r14w
0x1400269e5  mov     [rsi+58h], ax
0x1400269e9  mov     rax, [rbx+30h]
0x1400269ed  mov     rcx, [rax+60h]; void *
0x1400269f1  movzx   r8d, word ptr [rax+58h]; Size
0x1400269f6  lea     rdx, [rcx+2]; Src
0x1400269fa  call    memmove
0x1400269ff  mov     rsi, [rbx+30h]
0x140026a03  cmp     [rsi+58h], r14w
0x140026a08  jbe     short loc_140026A25
0x140026a0a  mov     rax, [rsi+60h]
0x140026a0e  cmp     [rax+2], r12w
0x140026a13  jnz     short loc_140026A25
0x140026a15  cmp     [rax], r12w
0x140026a19  jnz     short loc_140026A25
0x140026a1b  mov     eax, 0C0000033h
0x140026a20  jmp     loc_14002899C
0x140026a25  movups  xmm6, xmmword ptr [rsi+58h]
0x140026a29  movaps  [rsp+4F8h+var_248], xmm6
0x140026a31  mov     r14, [rsi+40h]
0x140026a35  mov     qword ptr [rsp+4F8h+String1.Length], r14
0x140026a3d  mov     eax, [r13+58h]
0x140026a41  mov     [rsp+4F8h+var_3BC], eax
0x140026a48  mov     rax, [r13+18h]
0x140026a4c  mov     [rsp+4F8h+var_2D8], rax
0x140026a54  mov     rax, [rbx+8]
0x140026a58  mov     [rsp+4F8h+var_3C8], rax
0x140026a60  mov     r8d, [rbx+10h]
0x140026a64  mov     [rsp+4F8h+var_3F8], r8d
0x140026a6c  movzx   eax, word ptr [rbx+18h]
0x140026a70  mov     [rsp+4F8h+var_42A], ax
0x140026a78  movzx   eax, word ptr [rbx+1Ah]
0x140026a7c  mov     word ptr [rsp+4F8h+var_438+6], ax
0x140026a84  mov     eax, [rbx+20h]
0x140026a87  mov     dword ptr [rsp+4F8h+var_3D8+4], eax
0x140026a8e  test    r14, r14
0x140026a91  jz      short loc_140026A9B
0x140026a93  mov     rax, [r14+10h]
0x140026a97  mov     [rsi+10h], rax
0x140026a9b  bt      r8d, 0Dh
0x140026aa0  jnb     short loc_140026AAC
0x140026aa2  mov     eax, 0C0000002h
0x140026aa7  jmp     loc_14002899C
0x140026aac  mov     r13, [rbx+28h]
0x140026ab0  add     r13, 1A0h
0x140026ab7  mov     [rsp+4F8h+var_348], r13
0x140026abf  mov     cl, r8b
0x140026ac2  mov     r12d, 1
0x140026ac8  and     cl, r12b
0x140026acb  mov     [rsp+4F8h+var_438+4], cl
0x140026ad2  mov     eax, r8d
0x140026ad5  shr     eax, 9
0x140026ad8  and     al, r12b
0x140026adb  mov     [rsp+4F8h+var_408], eax
0x140026ae2  mov     ebx, r8d
0x140026ae5  and     ebx, 1000h
0x140026aeb  mov     dword ptr [rsp+4F8h+var_398], ebx
0x140026af2  setnz   [rsp+4F8h+var_438+2]
0x140026afa  mov     eax, r8d
0x140026afd  shr     eax, 10h
0x140026b00  and     al, r12b
0x140026b03  mov     [rsp+4F8h+var_404], eax
0x140026b0a  mov     [rsp+4F8h+var_417], al
0x140026b11  mov     edx, 100h
0x140026b16  mov     rax, qword ptr [rsp+4F8h+var_2E8]
0x140026b1e  and     dx, [rax+18h]
0x140026b22  mov     [rsp+4F8h+var_368], edx
0x140026b29  setnz   [rsp+4F8h+var_42C]
0x140026b31  mov     edx, r8d
0x140026b34  shr     edx, 18h
0x140026b37  mov     [rsp+4F8h+var_400], edx
0x140026b3e  mov     al, [rax+2]
0x140026b41  mov     [rsp+4F8h+var_438+1], al
0x140026b48  shr     al, 1
0x140026b4a  and     al, r12b
0x140026b4d  mov     [rsp+4F8h+var_438+3], al
0x140026b54  test    cl, cl
0x140026b56  jz      short loc_140026B68
0x140026b58  lea     eax, [rdx-2]
0x140026b5b  cmp     eax, r12d
0x140026b5e  mov     [rsp+4F8h+var_418], r12b
0x140026b66  jbe     short loc_140026B70
0x140026b68  mov     [rsp+4F8h+var_418], dil
0x140026b70  test    cl, cl
0x140026b72  jz      short loc_140026B86
0x140026b74  lea     eax, [rdx-1]
0x140026b77  test    eax, 0FFFFFFFDh
0x140026b7c  mov     [rsp+4F8h+var_42D], r12b
0x140026b84  jz      short loc_140026B8E
0x140026b86  mov     [rsp+4F8h+var_42D], dil
0x140026b8e  lea     rax, [r13+0C8h]
0x140026b95  mov     [rsp+4F8h+var_320], rax
0x140026b9d  mov     eax, [rax]
0x140026b9f  bt      eax, 16h
0x140026ba3  jnb     short loc_140026BE4
0x140026ba5  test    dword ptr [r15+44h], 80000h
0x140026bad  jz      short loc_140026BE4
0x140026baf  mov     [rsp+4F8h+Timeout], rdi; Timeout
0x140026bb4  xor     r9d, r9d; Alertable
0x140026bb7  xor     r8d, r8d; WaitMode
0x140026bba  xor     edx, edx; WaitReason
0x140026bbc  lea     rcx, Event; Object
0x140026bc3  call    cs:__imp_KeWaitForSingleObject
0x140026bca  nop     dword ptr [rax+rax+00h]
0x140026bcf  btr     dword ptr [r15+44h], 13h
0x140026bd5  mov     cl, [rsp+4F8h+var_438+4]
0x140026bdc  mov     r8d, [rsp+4F8h+var_3F8]
0x140026be4  mov     rax, [rsp+4F8h+Context2]
0x140026bec  cmp     [rax+5Ch], edi
0x140026bef  jnz     loc_140028997
0x140026bf5  mov     eax, r8d
0x140026bf8  and     eax, 40h
0x140026bfb  mov     [rsp+4F8h+var_3C0], eax
0x140026c02  test    cl, cl
0x140026c04  jz      short loc_140026C0E
0x140026c06  test    eax, eax
0x140026c08  jnz     loc_140028997
0x140026c0e  xor     r8d, r8d
0x140026c11  mov     rdx, r13
0x140026c14  mov     rcx, r15
0x140026c17  call    FatAcquireExclusiveVcb_Real
0x140026c1c  test    al, al
0x140026c1e  jnz     short loc_140026C35
0x140026c20  mov     rdx, [rsp+4F8h+Context2]; Context2
0x140026c28  mov     rcx, r15; Context1
0x140026c2b  call    FatFsdPostRequest
0x140026c30  jmp     loc_14002899C
0x140026c35  mov     r8, qword ptr [rsp+4F8h+var_2E8]
0x140026c3d  mov     qword ptr [rsp+4F8h+var_268.Length], r8
0x140026c45  mov     ecx, [rsp+4F8h+var_3F8]
0x140026c4c  and     ecx, 8
0x140026c4f  mov     [rsp+4F8h+var_3F8], ecx
0x140026c56  mov     eax, [rsp+4F8h+var_368]
0x140026c5d  mov     [rsp+4F8h+var_35C], ax
0x140026c65  mov     dl, [rsp+4F8h+var_438+1]
0x140026c6c  and     dl, 4
0x140026c6f  mov     [rsp+4F8h+var_438+1], dl
0x140026c76  lea     rax, [r13+0C8h]
0x140026c7d  mov     qword ptr [rsp+4F8h+var_2F8.Length], rax
0x140026c85  mov     eax, [r13+0C8h]
0x140026c8c  bt      eax, 9
0x140026c90  jnb     short loc_140026CB3
0x140026c92  mov     [rsp+4F8h+Timeout], rdi; BugCheckParameter4
0x140026c97  xor     r9d, r9d; BugCheckParameter3
0x140026c9a  xor     r8d, r8d; BugCheckParameter2
0x140026c9d  mov     edx, 60393h; BugCheckParameter1
0x140026ca2  lea     ecx, [r9+23h]; BugCheckCode
0x140026ca6  call    cs:__imp_KeBugCheckEx
0x140026cb3  mov     [rsp+4F8h+var_318], rdi
0x140026cbb  mov     [rsp+4F8h+var_42F], dil
0x140026cc3  mov     [rsp+4F8h+var_430], r12b
0x140026ccb  mov     [rsp+4F8h+var_42E], dil
0x140026cd3  mov     [rsp+4F8h+var_2B0], rsi
0x140026cdb  mov     eax, [rsp+4F8h+var_3BC]
0x140026ce2  mov     [rsp+4F8h+var_2A4], eax
0x140026ce9  mov     rax, [rsp+4F8h+var_2D8]
0x140026cf1  mov     qword ptr [rsp+4F8h+var_2C8.Length], rax
0x140026cf9  mov     rax, [rsp+4F8h+var_3C8]
0x140026d01  add     rax, 10h
0x140026d05  mov     [rsp+4F8h+var_3D0], rax
0x140026d0d  movzx   eax, word ptr [rsp+4F8h+var_438+6]
0x140026d15  mov     [rsp+4F8h+var_360], ax
0x140026d1d  mov     eax, dword ptr [rsp+4F8h+var_3D8+4]
0x140026d24  mov     [rsp+4F8h+var_2A8], eax
0x140026d2b  mov     r8d, 4027h
0x140026d31  movzx   eax, [rsp+4F8h+var_42A]
0x140026d39  and     ax, r8w
0x140026d3d  mov     [rsp+4F8h+var_42A], ax
0x140026d45  mov     [rsp+4F8h+var_364], ax
0x140026d4d  mov     eax, [rsp+4F8h+var_3C0]
0x140026d54  mov     [rsp+4F8h+var_298], eax
0x140026d5b  mov     dword ptr [rsp+4F8h+var_330], ecx
0x140026d62  mov     eax, [rsp+4F8h+var_408]
0x140026d69  mov     [rsp+4F8h+var_3FC], al
0x140026d70  mov     al, [rsp+4F8h+var_438+2]
0x140026d77  mov     [rsp+4F8h+var_3FB], al
0x140026d7e  mov     al, [rsp+4F8h+var_42C]
0x140026d85  mov     [rsp+4F8h+var_3FA], al
0x140026d8c  mov     [rsp+4F8h+var_3F9], dl
0x140026d93  mov     [rsp+4F8h+Bcb], rdi
0x140026d9b  mov     dword ptr [rsp+4F8h+DestinationString.Length], 400000h
0x140026da6  lea     rcx, [rsp+4F8h+var_108]
0x140026dae  mov     [rsp+4F8h+DestinationString.Buffer], rcx
0x140026db6  mov     dword ptr [rsp+4F8h+SourceString.Length], 400000h
0x140026dc1  lea     rcx, [rsp+4F8h+CompletionRoutine]
0x140026dc9  mov     [rsp+4F8h+SourceString.Buffer], rcx
0x140026dd1  mov     dword ptr [rsp+4F8h+Src], 400000h
0x140026ddc  lea     rax, [rsp+4F8h+var_88]
0x140026de4  mov     [rsp+4F8h+Src+8], rax
0x140026dec  mov     rdx, r13
0x140026def  mov     rcx, r15
0x140026df2  call    FatVerifyVcb
0x140026df7  mov     eax, [r13+0C8h]
0x140026dfe  test    r12b, al
0x140026e01  jz      short loc_140026E22
0x140026e03  mov     ebx, 0C000026Eh
0x140026e08  mov     eax, 0C0000022h
0x140026e0d  cmp     [r13+0CCh], r12d
0x140026e14  cmovz   ebx, eax
0x140026e17  mov     r14d, 503h
0x140026e1d  jmp     loc_140028655
0x140026e22  test    ebx, ebx
0x140026e24  jz      short loc_140026E72
0x140026e26  mov     eax, [r13+0C8h]
0x140026e2d  bt      eax, 0Eh
0x140026e31  jnb     short loc_140026E72
0x140026e33  mov     rdx, [r13+0C0h]
0x140026e3a  mov     rdx, [rdx+10h]; DeviceObject
0x140026e3e  mov     rcx, [r15+28h]; Irp
0x140026e42  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x140026e49  nop     dword ptr [rax+rax+00h]
0x140026e4e  mov     rax, [r13+0C0h]
0x140026e55  mov     rcx, [rax+10h]
0x140026e59  or      dword ptr [rcx+30h], 2
0x140026e5d  mov     ecx, 0C00000A2h; Status
0x140026e62  mov     [r15+48h], ecx
0x140026e66  call    cs:__imp_ExRaiseStatus
0x140026e72  cmp     [rsp+4F8h+var_2D8], rdi
0x140026e7a  jz      short loc_140026E93
0x140026e7c  mov     ebx, 0C000004Fh
0x140026e81  mov     dword ptr [rsp+4F8h+var_428], ebx
0x140026e88  mov     r14d, 503h
0x140026e8e  jmp     loc_1400286A3
0x140026e93  movd    ebx, xmm6
0x140026e97  test    bx, bx
0x140026e9a  jnz     loc_140026F88
0x140026ea0  mov     [rsp+4F8h+var_258], rdi
0x140026ea8  test    r14, r14
0x140026eab  jz      short loc_140026ED6
0x140026ead  lea     r9, [rsp+4F8h+var_2A0]
0x140026eb5  lea     r8, [rsp+4F8h+BugCheckParameter3]
0x140026ebd  lea     rdx, [rsp+4F8h+var_258]
0x140026ec5  mov     rcx, r14
0x140026ec8  call    FatDecodeFileObject
0x140026ecd  cmp     eax, 4
0x140026ed0  jnz     loc_140026F88
0x140026ed6  cmp     [rsp+4F8h+var_438+4], dil
0x140026ede  jz      short loc_140026EE7
0x140026ee0  mov     ebx, 0C0000103h
0x140026ee5  jmp     short loc_140026E81
0x140026ee7  cmp     [rsp+4F8h+var_438+1], dil
0x140026eef  jz      short loc_140026EF8
0x140026ef1  mov     ebx, 0C000000Dh
0x140026ef6  jmp     short loc_140026E81
  ... truncated ...
```
