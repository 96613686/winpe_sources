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
  __int64 v4; // rbx
  __int64 v5; // rsi
  unsigned __int16 v6; // ax
  _WORD *v7; // rcx
  _WORD *v8; // rax
  struct _UNICODE_STRING v10; // xmm6
  __int64 v11; // r14
  unsigned int v12; // r8d
  __int64 v13; // r13
  char v14; // cl
  unsigned int v15; // eax
  int v16; // ebx
  unsigned int v17; // eax
  bool v18; // zf
  unsigned int v19; // edx
  int v20; // ecx
  char v21; // dl
  __int64 v22; // r8
  PWSTR Buffer; // r9
  NTSTATUS v24; // ebx
  unsigned __int16 v25; // bx
  unsigned __int64 v26; // rcx
  __m128i *v27; // rax
  __m128i v28; // xmm1
  _WORD *v29; // xmm0_8
  _WORD *v30; // r14
  _WORD *v31; // xmm0_8
  unsigned __int64 v32; // rcx
  ULONG_PTR v33; // r14
  UNICODE_STRING v34; // xmm0
  __int64 v35; // rcx
  int v36; // eax
  ULONG_PTR Fcb; // r14
  __int64 v38; // rcx
  int v39; // eax
  __int64 v40; // r8
  __int64 v41; // rdx
  __int64 v42; // rdx
  _QWORD *v43; // rbx
  unsigned __int64 v44; // rcx
  unsigned __int64 v45; // rcx
  unsigned __int64 v46; // rcx
  char v47; // al
  __int64 v48; // rcx
  NTSTATUS v49; // eax
  __int64 v50; // rbx
  __int64 v51; // rcx
  __int64 v52; // r10
  __int64 v53; // rdx
  int v54; // ebx
  __m128i *v55; // rax
  __int64 v56; // rdx
  struct _FILE_OBJECT *v57; // r14
  __int64 v58; // rdx
  __int64 v59; // r8
  __int64 v60; // r9
  __int64 v61; // rdx
  __int64 v62; // r8
  __int64 v63; // r9
  __int64 v64; // rdx
  __int64 v65; // r8
  __int64 v66; // r9
  char v67; // r14
  __int64 v68; // rcx
  __int64 v69; // r8
  struct _MDL *Mdl; // rdx
  unsigned __int64 v71; // rcx
  __int64 v72; // rax
  int PostIrpRoutine; // [rsp+C8h] [rbp-4D0h]
  int v74; // [rsp+D0h] [rbp-4C8h]
  int Name; // [rsp+D8h] [rbp-4C0h]
  int v76; // [rsp+E8h] [rbp-4B0h]
  char v77[8]; // [rsp+160h] [rbp-438h] BYREF
  char i; // [rsp+168h] [rbp-430h]
  char v79; // [rsp+169h] [rbp-42Fh]
  char v80; // [rsp+16Ah] [rbp-42Eh]
  char v81; // [rsp+16Bh] [rbp-42Dh]
  char v82; // [rsp+16Ch] [rbp-42Ch]
  char v83; // [rsp+16Dh] [rbp-42Bh] BYREF
  __int16 v84; // [rsp+16Eh] [rbp-42Ah]
  __m128i v85; // [rsp+170h] [rbp-428h]
  char v86; // [rsp+180h] [rbp-418h]
  char v87; // [rsp+181h] [rbp-417h]
  ULONG_PTR BugCheckParameter3; // [rsp+188h] [rbp-410h] BYREF
  unsigned int v89; // [rsp+190h] [rbp-408h]
  unsigned int v90; // [rsp+194h] [rbp-404h]
  unsigned int v91; // [rsp+198h] [rbp-400h]
  char v92; // [rsp+19Ch] [rbp-3FCh]
  char v93; // [rsp+19Dh] [rbp-3FBh]
  char v94; // [rsp+19Eh] [rbp-3FAh]
  char v95; // [rsp+19Fh] [rbp-3F9h]
  int v96; // [rsp+1A0h] [rbp-3F8h]
  PVOID Context2; // [rsp+1A8h] [rbp-3F0h]
  struct _UNICODE_STRING FirstName; // [rsp+1B0h] [rbp-3E8h] BYREF
  int v99; // [rsp+1C0h] [rbp-3D8h] BYREF
  int v100; // [rsp+1C4h] [rbp-3D4h]
  __int64 v101; // [rsp+1C8h] [rbp-3D0h]
  ULONG_PTR v102; // [rsp+1D0h] [rbp-3C8h] BYREF
  int v103; // [rsp+1D8h] [rbp-3C0h]
  int v104; // [rsp+1DCh] [rbp-3BCh]
  __int64 v105; // [rsp+1E0h] [rbp-3B8h] BYREF
  __int64 v106; // [rsp+1E8h] [rbp-3B0h] BYREF
  _STRING DestinationString; // [rsp+1F0h] [rbp-3A8h] BYREF
  ULONG_PTR v108[2]; // [rsp+200h] [rbp-398h] BYREF
  struct _UNICODE_STRING v109; // [rsp+210h] [rbp-388h] BYREF
  UNICODE_STRING SourceString; // [rsp+220h] [rbp-378h] BYREF
  int v111; // [rsp+230h] [rbp-368h]
  __int16 v112; // [rsp+234h] [rbp-364h]
  __int16 v113; // [rsp+238h] [rbp-360h]
  __int16 v114; // [rsp+23Ch] [rbp-35Ch]
  void *Src[2]; // [rsp+240h] [rbp-358h] BYREF
  __int64 v116; // [rsp+250h] [rbp-348h]
  PVOID Bcb; // [rsp+258h] [rbp-340h] BYREF
  int v118; // [rsp+260h] [rbp-338h]
  __int64 Dcb; // [rsp+268h] [rbp-330h] BYREF
  volatile signed __int32 *v120; // [rsp+278h] [rbp-320h]
  __int64 v121; // [rsp+280h] [rbp-318h]
  PIRP *v122; // [rsp+288h] [rbp-310h]
  UNICODE_STRING String1; // [rsp+290h] [rbp-308h] BYREF
  UNICODE_STRING v124; // [rsp+2A0h] [rbp-2F8h] BYREF
  int v125[4]; // [rsp+2B0h] [rbp-2E8h] BYREF
  __int64 v126; // [rsp+2C0h] [rbp-2D8h] BYREF
  STRING v127; // [rsp+2D0h] [rbp-2C8h] BYREF
  ULONG_PTR v128; // [rsp+2E0h] [rbp-2B8h]
  __int64 v129; // [rsp+2E8h] [rbp-2B0h]
  int v130; // [rsp+2F0h] [rbp-2A8h]
  int v131; // [rsp+2F4h] [rbp-2A4h]
  __int64 v132; // [rsp+2F8h] [rbp-2A0h] BYREF
  int v133; // [rsp+300h] [rbp-298h]
  struct _UNICODE_STRING RemainingName; // [rsp+310h] [rbp-288h] BYREF
  __int64 v135[2]; // [rsp+320h] [rbp-278h] BYREF
  UNICODE_STRING v136; // [rsp+330h] [rbp-268h] BYREF
  __int64 v137; // [rsp+340h] [rbp-258h] BYREF
  struct _UNICODE_STRING v138; // [rsp+350h] [rbp-248h]
  UNICODE_STRING v139[5]; // [rsp+360h] [rbp-238h] BYREF
  UNICODE_STRING Path; // [rsp+3B0h] [rbp-1E8h] BYREF
  ANSI_STRING DbcsName; // [rsp+3C0h] [rbp-1D8h] BYREF
  _STRING v142; // [rsp+3D0h] [rbp-1C8h] BYREF
  char v143[16]; // [rsp+3E0h] [rbp-1B8h] BYREF
  char v144[16]; // [rsp+3F0h] [rbp-1A8h] BYREF
  char v145[16]; // [rsp+400h] [rbp-198h] BYREF
  char v146[16]; // [rsp+410h] [rbp-188h] BYREF
  char v147[16]; // [rsp+420h] [rbp-178h] BYREF
  int v148; // [rsp+430h] [rbp-168h] BYREF
  char v149[16]; // [rsp+440h] [rbp-158h] BYREF
  __int64 v150; // [rsp+450h] [rbp-148h] BYREF
  char v151; // [rsp+460h] [rbp-138h] BYREF
  char v152; // [rsp+478h] [rbp-120h] BYREF
  char v153; // [rsp+490h] [rbp-108h] BYREF
  POPLOCK_WAIT_COMPLETE_ROUTINE CompletionRoutine; // [rsp+4D0h] [rbp-C8h] BYREF
  char v155; // [rsp+510h] [rbp-88h] BYREF

  Context2 = (PVOID)a2;
  v122 = Context1;
  v150 = a2;
  v85 = 0;
  v77[0] = 0;
  BugCheckParameter3 = 0;
  v132 = 0;
  FirstName = 0;
  v109 = 0;
  RemainingName = 0;
  SourceString = 0;
  DestinationString = 0;
  v106 = 0;
  Bcb = 0;
  LODWORD(v105) = 0;
  v83 = 0;
  v99 = 0;
  memset(v139, 0, sizeof(v139));
  *(_OWORD *)Src = 0;
  *(_OWORD *)v135 = 0;
  v4 = *(_QWORD *)(a2 + 184);
  *(_QWORD *)v125 = v4;
  v5 = *(_QWORD *)(v4 + 48);
  v6 = *(_WORD *)(v5 + 88);
  if ( v6 > 2u )
  {
    v7 = *(_WORD **)(v5 + 96);
    if ( v7[1] == 92 && *v7 == 92 )
    {
      *(_WORD *)(v5 + 88) = v6 - 2;
      memmove(
        *(void **)(*(_QWORD *)(v4 + 48) + 96LL),
        (const void *)(*(_QWORD *)(*(_QWORD *)(v4 + 48) + 96LL) + 2LL),
        *(unsigned __int16 *)(*(_QWORD *)(v4 + 48) + 88LL));
      v5 = *(_QWORD *)(v4 + 48);
      if ( *(_WORD *)(v5 + 88) > 2u )
      {
        v8 = *(_WORD **)(v5 + 96);
        if ( v8[1] == 92 && *v8 == 92 )
          return 3221225523LL;
      }
    }
  }
  v10 = *(struct _UNICODE_STRING *)(v5 + 88);
  v138 = v10;
  v11 = *(_QWORD *)(v5 + 64);
  *(_QWORD *)&String1.Length = v11;
  v104 = *(_DWORD *)(a2 + 88);
  v126 = *(_QWORD *)(a2 + 24);
  v102 = *(_QWORD *)(v4 + 8);
  v12 = *(_DWORD *)(v4 + 16);
  v96 = v12;
  v84 = *(_WORD *)(v4 + 24);
  *(_WORD *)&v77[6] = *(_WORD *)(v4 + 26);
  v100 = *(_DWORD *)(v4 + 32);
  if ( v11 )
    *(_QWORD *)(v5 + 16) = *(_QWORD *)(v11 + 16);
  if ( (v12 & 0x2000) != 0 )
    return 3221225474LL;
  v13 = *(_QWORD *)(v4 + 40) + 416LL;
  v116 = v13;
  v14 = v12 & 1;
  v77[4] = v12 & 1;
  v15 = v12 >> 9;
  LOBYTE(v15) = (v12 & 0x200) != 0;
  v89 = v15;
  v16 = v12 & 0x1000;
  LODWORD(v108[0]) = v16;
  v77[2] = v16 != 0;
  v17 = HIWORD(v12);
  LOBYTE(v17) = BYTE2(v12) & 1;
  v90 = v17;
  v87 = BYTE2(v12) & 1;
  v18 = (*(_WORD *)(*(_QWORD *)v125 + 24LL) & 0x100) == 0;
  v111 = *(_WORD *)(*(_QWORD *)v125 + 24LL) & 0x100;
  v82 = !v18;
  v19 = HIBYTE(v12);
  v91 = HIBYTE(v12);
  v77[1] = *(_BYTE *)(*(_QWORD *)v125 + 2LL);
  v77[3] = (v77[1] & 2) != 0;
  if ( (v12 & 1) == 0 || (v86 = 1, v19 - 2 > 1) )
    v86 = 0;
  if ( !v14 || (v81 = 1, ((v19 - 1) & 0xFFFFFFFD) != 0) )
    v81 = 0;
  v120 = (volatile signed __int32 *)(v13 + 200);
  if ( (*(_DWORD *)(v13 + 200) & 0x400000) != 0 && (*((_DWORD *)Context1 + 17) & 0x80000) != 0 )
  {
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    *((_DWORD *)Context1 + 17) &= ~0x80000u;
    v14 = v77[4];
    LOBYTE(v12) = v96;
  }
  if ( *((_DWORD *)Context2 + 23) )
    return 3221225485LL;
  v103 = v12 & 0x40;
  if ( v14 )
  {
    if ( (v12 & 0x40) != 0 )
      return 3221225485LL;
  }
  if ( !(unsigned __int8)FatAcquireExclusiveVcb_Real(Context1, v13, 0) )
    return FatFsdPostRequest(Context1, Context2);
  *(_QWORD *)&v136.Length = *(_QWORD *)v125;
  v20 = v96 & 8;
  v96 = v20;
  v114 = v111;
  v21 = v77[1] & 4;
  v77[1] &= 4u;
  *(_QWORD *)&v124.Length = v13 + 200;
  if ( (*(_DWORD *)(v13 + 200) & 0x200) != 0 )
    KeBugCheckEx(0x23u, 0x60393u, 0, 0, 0);
  v121 = 0;
  v79 = 0;
  i = 1;
  v80 = 0;
  v129 = v5;
  v131 = v104;
  *(_QWORD *)&v127.Length = v126;
  v101 = v102 + 16;
  v113 = *(_WORD *)&v77[6];
  v130 = v100;
  v84 &= 0x4027u;
  v112 = v84;
  v133 = v103;
  LODWORD(Dcb) = v20;
  v92 = v89;
  v93 = v77[2];
  v94 = v82;
  v95 = v21;
  Bcb = 0;
  *(_DWORD *)&DestinationString.Length = 0x400000;
  DestinationString.Buffer = &v153;
  *(_DWORD *)&SourceString.Length = 0x400000;
  SourceString.Buffer = (PWSTR)&CompletionRoutine;
  LODWORD(Src[0]) = 0x400000;
  Src[1] = &v155;
  FatVerifyVcb(Context1, v13);
  if ( (*(_DWORD *)(v13 + 200) & 1) != 0 )
  {
    v24 = -1073741202;
    if ( *(_DWORD *)(v13 + 204) == 1 )
      v24 = -1073741790;
LABEL_228:
    v85.m128i_i32[0] = v24;
    goto LABEL_229;
  }
  if ( v16 && (*(_DWORD *)(v13 + 200) & 0x4000) != 0 )
  {
    IoSetHardErrorOrVerifyDevice(Context1[5], *(PDEVICE_OBJECT *)(*(_QWORD *)(v13 + 192) + 16LL));
    *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 192) + 16LL) + 48LL) |= 2u;
    *((_DWORD *)Context1 + 18) = -1073741662;
    ExRaiseStatus(-1073741662);
  }
  if ( v126 )
  {
    v24 = -1073741745;
LABEL_37:
    v85.m128i_i32[0] = v24;
    goto LABEL_235;
  }
  v25 = _mm_cvtsi128_si32((__m128i)v10);
  if ( !v25 )
  {
    v137 = 0;
    if ( !v11 || (unsigned int)FatDecodeFileObject(v11, &v137, &BugCheckParameter3, &v132) == 4 )
    {
      if ( v77[4] )
      {
        v24 = -1073741565;
      }
      else
      {
        if ( !v77[1] )
        {
          v26 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
          ++*(_DWORD *)(v26 + *(_QWORD *)(v13 + 1024) + 56);
          v27 = (__m128i *)FatOpenVolume(v125, Context1, v5, v13, v101, *(_WORD *)&v77[6], v91);
          goto LABEL_46;
        }
        v24 = -1073741811;
      }
      goto LABEL_37;
    }
  }
  if ( v11 )
  {
    v108[0] = 0;
    v102 = 0;
    v132 = 0;
    if ( (unsigned int)FatDecodeFileObject(v11, v108, &v102, &v132) - 2 > 1 )
    {
      v24 = -1073741766;
      goto LABEL_37;
    }
    v29 = (_WORD *)_mm_srli_si128((__m128i)v10, 8).m128i_u64[0];
    v30 = v29;
    if ( v25 && *v29 == 92 )
    {
LABEL_53:
      v24 = -1073741773;
      goto LABEL_37;
    }
    *(_QWORD *)(v5 + 16) = *(_QWORD *)(*(_QWORD *)&String1.Length + 16LL);
    v108[0] = v102;
    FatVerifyFcb(Context1, v102);
  }
  else
  {
    v31 = (_WORD *)_mm_srli_si128((__m128i)v10, 8).m128i_u64[0];
    v30 = v31;
    if ( v25 == 2 && *v31 == 92 )
    {
      if ( v103 )
      {
        v24 = -1073741638;
      }
      else if ( v77[1] )
      {
        v24 = -1073741811;
      }
      else
      {
        if ( !LODWORD(v108[0]) )
        {
          v32 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
          ++*(_DWORD *)(v32 + *(_QWORD *)(v13 + 1024) + 56);
          v27 = (__m128i *)FatOpenRootDcb(&v126, Context1, v5, v13, v101, *(_WORD *)&v77[6], v91);
          goto LABEL_46;
        }
        v24 = -1073741535;
      }
      goto LABEL_59;
    }
    v108[0] = *(_QWORD *)(v13 + 208);
    v102 = v108[0];
    FatVerifyFcb(Context1, v108[0]);
  }
  if ( v25 && v30[((unsigned __int64)v25 >> 1) - 1] == 92 )
  {
    v25 -= 2;
    v138.Length = v25;
    v77[4] = 1;
    v10 = v138;
  }
  else
  {
    v77[4] = 0;
  }
  v33 = v108[0];
  if ( !*(_QWORD *)(v108[0] + 536) )
    FatSetFullFileNameInFcb((int)Context1);
  if ( (unsigned __int16)(*(_WORD *)(v33 + 528) + v25 + 2) <= v25 )
  {
    v24 = -1073741773;
LABEL_59:
    v85.m128i_i32[0] = v24;
    goto LABEL_235;
  }
  while ( 1 )
  {
    while ( 1 )
    {
      BugCheckParameter3 = v33;
      v109 = v10;
      do
      {
        v34 = v109;
        v109.Length = _mm_cvtsi128_si32((__m128i)v109);
        if ( !v109.Length )
          break;
        v128 = 0;
        Path = v34;
        FsRtlDissectName(&Path, &FirstName, &RemainingName);
        if ( RemainingName.Length && *RemainingName.Buffer == 92 || FirstName.Length > 0x1FEu )
          goto LABEL_53;
        FatEnsureStringBufferEnough(&DestinationString);
        v24 = RtlUpcaseUnicodeStringToCountedOemString(&DestinationString, &FirstName, 0);
        if ( (*(_DWORD *)(v13 + 200) & 0x400000) != 0 )
        {
          LOBYTE(v35) = *(_BYTE *)Buf1;
          v36 = *DestinationString.Buffer == *(_BYTE *)Buf1
              ? FatCompareNames(&DestinationString, &_EFS_SHORT)
              : *DestinationString.Buffer >= *(_BYTE *)Buf1;
          if ( v36 == 2 )
          {
LABEL_84:
            v24 = -1073741790;
            v85.m128i_i32[0] = -1073741790;
            goto LABEL_235;
          }
        }
        if ( v24 < 0 )
        {
          Fcb = 0;
          v128 = 0;
          DestinationString.Length = 0;
          if ( v24 != -1073741470 )
          {
            v85.m128i_i32[0] = v24;
            goto LABEL_229;
          }
        }
        else
        {
          Fcb = FatFindFcb(v35, BugCheckParameter3 + 384, &DestinationString, v77);
          v128 = Fcb;
        }
        if ( !Fcb )
        {
          if ( *(_QWORD *)(BugCheckParameter3 + 392) )
          {
            FatEnsureStringBufferEnough(&SourceString);
            RtlDowncaseUnicodeString(&SourceString, &FirstName, 0);
            RtlUpcaseUnicodeString(&SourceString, &SourceString, 0);
            if ( (*(_DWORD *)(v13 + 200) & 0x400000) != 0 )
            {
              LOBYTE(v38) = *(_BYTE *)_EFS.Buffer;
              v39 = *(_BYTE *)FirstName.Buffer == *(_BYTE *)_EFS.Buffer
                  ? FatCompareNames(&FirstName, &_EFS)
                  : *(_BYTE *)FirstName.Buffer >= *(_BYTE *)_EFS.Buffer;
              if ( v39 == 2 )
                goto LABEL_84;
            }
            Fcb = FatFindFcb(v38, BugCheckParameter3 + 392, &SourceString, v77);
            v128 = Fcb;
          }
          if ( !Fcb )
            break;
        }
        if ( v77[0]
          && (*(_DWORD *)(&String1.MaximumLength + 1) = 0,
              String1.Buffer = (PWSTR)&v151,
              *(_DWORD *)&String1.Length = 1572864,
              RtlOemStringToCountedUnicodeString(&String1, (PCOEM_STRING)(Fcb + 480), 0),
              RtlCompareUnicodeString(&String1, (PCUNICODE_STRING)(Fcb + 552), 1u)) )
        {
          RtlCopyUnicodeString(&FirstName, &String1);
          v40 = *(_DWORD *)(Fcb + 192) >> 13;
          LOBYTE(v40) = (*(_DWORD *)(Fcb + 192) & 0x2000) != 0;
          v41 = *(_DWORD *)(Fcb + 192) >> 12;
          LOBYTE(v41) = (*(_DWORD *)(Fcb + 192) & 0x1000) != 0;
          FatUnicodeRestoreShortNameCase(&FirstName, v41, v40);
        }
        else
        {
          memmove(FirstName.Buffer, *(const void **)(Fcb + 560), FirstName.Length);
        }
        BugCheckParameter3 = Fcb;
        v109 = RemainingName;
        if ( *(_WORD *)Fcb == 1282 )
          break;
      }
      while ( RemainingName.Length );
      if ( v109.Length && *v109.Buffer == 92 )
      {
        v109.Length -= 2;
        ++v109.Buffer;
      }
      FatVerifyFcb(Context1, BugCheckParameter3);
      v33 = v108[0];
      v42 = 1282;
      v22 = *(_QWORD *)v125;
      v43 = Context2;
      Buffer = (PWSTR)v91;
      if ( *(_DWORD *)(BugCheckParameter3 + 196) == 1 )
        break;
      FatRemoveNames(BugCheckParameter3, BugCheckParameter3);
    }
    if ( !v77[3] )
    {
      if ( (*(_DWORD *)(BugCheckParameter3 + 192) & 0x80u) != 0 )
      {
        v24 = -1073741790;
        v85.m128i_i32[0] = -1073741790;
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
    FatFspClose(v13, 1282, *(_QWORD *)v125, v91);
    i = 0;
  }
  if ( *(_WORD *)BugCheckParameter3 == 1282 && (*(_DWORD *)(BugCheckParameter3 + 192) & 4) == 0 )
  {
    v24 = -1073741757;
LABEL_117:
    v85.m128i_i32[0] = v24;
    goto LABEL_236;
  }
LABEL_120:
  if ( (*(_DWORD *)(BugCheckParameter3 + 192) & 1) != 0 )
  {
    v24 = -1073741738;
    goto LABEL_117;
  }
  if ( !v109.Length )
  {
    if ( v77[1] )
    {
      v44 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
      ++*(_DWORD *)(v44 + *(_QWORD *)(v13 + 1024) + 56);
      v28 = *(__m128i *)FatOpenTargetDirectory(
                          &Dcb,
                          Context1,
                          v5,
                          *(_QWORD *)(BugCheckParameter3 + 176),
                          v101,
                          *(_WORD *)&v77[6],
                          1,
                          v77[0]);
      v85 = v28;
      v43[7] = _mm_srli_si128(v28, 8).m128i_u64[0];
      goto LABEL_47;
    }
    if ( (unsigned __int16)(*(_WORD *)BugCheckParameter3 - 1283) <= 1u )
    {
      if ( !v103 )
      {
        v46 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
        ++*(_DWORD *)(v46 + *(_QWORD *)(v13 + 1024) + 56);
        v85 = *(__m128i *)FatOpenExistingDcb(
                            v144,
                            Context1,
                            v22,
                            v5,
                            v13,
                            BugCheckParameter3,
                            v101,
                            *(_WORD *)&v77[6],
                            (_DWORD)Buffer,
                            (_BYTE)v89,
                            v77[2],
                            (_BYTE)v90,
                            v77[0],
                            &v83);
        v24 = _mm_cvtsi128_si32(v85);
        if ( v24 == 259 )
          v79 = 1;
        else
          *((_QWORD *)Context2 + 7) = v85.m128i_i64[1];
        goto LABEL_229;
      }
      v24 = -1073741638;
      goto LABEL_129;
    }
    if ( *(_WORD *)BugCheckParameter3 != 1282 )
      KeBugCheckEx(0x23u, 0x60675u, *(unsigned __int16 *)BugCheckParameter3, BugCheckParameter3, 0);
    if ( v81 )
    {
      v24 = -1073741565;
LABEL_129:
      v85.m128i_i32[0] = v24;
      goto LABEL_236;
    }
    if ( v77[4] )
    {
      v24 = -1073741773;
      goto LABEL_129;
    }
    v45 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
    ++*(_DWORD *)(v45 + *(_QWORD *)(v13 + 1024) + 56);
    v85 = *(__m128i *)FatOpenExistingFcb(
                        v143,
                        Context1,
                        v22,
                        v5,
                        v13,
                        BugCheckParameter3,
                        v101,
                        *(_WORD *)&v77[6],
                        v104,
                        v126,
                        v100,
                        v84,
                        (_DWORD)Buffer,
                        (_BYTE)v89,
                        v77[2],
                        (_BYTE)v90,
                        v77[0],
                        &v83);
    v24 = _mm_cvtsi128_si32(v85);
    if ( v24 == 259 )
    {
      v79 = 1;
      goto LABEL_229;
    }
LABEL_133:
    if ( v24 >= 0 && !v96 )
      *(_DWORD *)(v5 + 80) |= 0x40u;
    *((_QWORD *)Context2 + 7) = v85.m128i_i64[1];
    goto LABEL_229;
  }
  if ( (unsigned __int16)(*(_WORD *)BugCheckParameter3 - 1283) > 1u )
  {
    v24 = -1073741766;
    goto LABEL_129;
  }
  Dcb = BugCheckParameter3;
  v47 = 1;
  for ( i = 1; ; v47 = i )
  {
    if ( v47 )
    {
      i = 0;
      v109 = RemainingName;
      if ( DestinationString.Length )
        goto LABEL_157;
      v24 = -1073741470;
    }
    else
    {
      v136 = v109;
      FsRtlDissectName(&v136, &FirstName, &v109);
      if ( v109.Length && *v109.Buffer == 92 || FirstName.Length > 0x1FEu )
        goto LABEL_153;
      FatEnsureStringBufferEnough(&DestinationString);
      v24 = RtlUpcaseUnicodeStringToCountedOemString(&DestinationString, &FirstName, 0);
    }
    if ( v24 >= 0 )
    {
LABEL_157:
      DbcsName = DestinationString;
      if ( FsRtlIsFatDbcsLegal(&DbcsName, 0, 0, 0) )
      {
        v142 = DestinationString;
        FatStringTo8dot3(v48, &v142, &v139[2]);
        v22 = *(_DWORD *)(&v139[0].MaximumLength + 1) & 0xFF000000;
        *(_DWORD *)(&v139[0].MaximumLength + 1) &= 0xFF000000;
      }
      else
      {
        v22 = *(_DWORD *)(&v139[0].MaximumLength + 1) & 0xFF000000 | 2;
        *(_DWORD *)(&v139[0].MaximumLength + 1) = *(_DWORD *)(&v139[0].MaximumLength + 1) & 0xFF000000 | 2;
      }
      goto LABEL_159;
    }
    v22 = *(_DWORD *)(&v139[0].MaximumLength + 1) & 0xFF000000 | 2;
    *(_DWORD *)(&v139[0].MaximumLength + 1) = *(_DWORD *)(&v139[0].MaximumLength + 1) & 0xFF000000 | 2;
    if ( v24 != -1073741470 )
    {
      v85.m128i_i32[0] = v24;
      goto LABEL_229;
    }
LABEL_159:
    if ( (byte_140017D4C & 1) != 0 )
    {
      v22 = 0;
      v118 = 0;
      Buffer = FirstName.Buffer;
      while ( (unsigned int)v22 < FirstName.Length >> 1 )
      {
        if ( FirstName.Buffer[(unsigned int)v22] < 0x80u
          && SLOBYTE(FirstName.Buffer[(unsigned int)v22]) >= 0
          && (*((_BYTE *)FsRtlLegalAnsiCharacterArray + FirstName.Buffer[(unsigned int)v22]) & 2) == 0 )
        {
          goto LABEL_165;
        }
        v22 = (unsigned int)(v22 + 1);
        v118 = v22;
      }
    }
    else if ( (v22 & 2) != 0 )
    {
LABEL_165:
      v24 = -1073741773;
      v85.m128i_i32[0] = -1073741773;
      goto LABEL_235;
    }
    FatEnsureStringBufferEnough(&SourceString);
    v49 = RtlUpcaseUnicodeString(&SourceString, &FirstName, 0);
    v24 = v49;
    if ( v49 < 0 )
    {
      v85.m128i_i32[0] = v49;
      goto LABEL_229;
    }
    v139[3] = SourceString;
    LOBYTE(v139[0].Buffer) = 0;
    LOWORD(Src[0]) = 0;
    if ( (*(_DWORD *)(v13 + 200) & 0x400000) != 0 )
    {
      if ( v91 == 1 || v91 == 4 )
      {
        v80 = 0;
        v99 = 2;
      }
      else
      {
        v80 = 1;
        v99 = 15;
      }
    }
    v50 = Dcb;
    FatLocateDirent(
      (int)Context1,
      Dcb,
      (int)v139,
      0,
      (__int64)&v99,
      (__int64)&v106,
      (__int64)&Bcb,
      (__int64)&v105,
      (__int64)v77,
      (PCUNICODE_STRING)Src,
      (__int64)v135);
    v121 = v50;
    v52 = v106;
    if ( v106 )
    {
      if ( !v77[0] )
        goto LABEL_180;
      *(_DWORD *)(&v127.MaximumLength + 1) = 0;
      *(_DWORD *)(&v124.MaximumLength + 1) = 0;
      v124.Buffer = (PWSTR)&v152;
      *(_DWORD *)&v124.Length = 1572864;
      v127.Buffer = (PCHAR)&v150;
      *(_DWORD *)&v127.Length = 786432;
      LOBYTE(v22) = 1;
      Fat8dot3ToString(v51, v106, v22, &v127);
      RtlOemStringToCountedUnicodeString(&v124, &v127, 0);
      if ( RtlCompareUnicodeString(&v124, (PCUNICODE_STRING)Src, 1u) )
        RtlCopyUnicodeString(&FirstName, &v124);
      else
LABEL_180:
        memmove(FirstName.Buffer, Src[1], FirstName.Length);
      v52 = v106;
    }
    if ( !v109.Length )
      break;
    if ( !v52 )
    {
      v24 = -1073741766;
      goto LABEL_154;
    }
    if ( (*(_BYTE *)(v52 + 11) & 0x10) == 0 )
    {
      v24 = -1073741766;
      goto LABEL_228;
    }
    Dcb = FatCreateDcb(
            (unsigned int)Src,
            v13,
            v50,
            v105 - 32 * ((((unsigned __int64)LOWORD(v135[0]) >> 1) + 12) / 0xD),
            v105,
            v52,
            (__int64)Src);
    v121 = Dcb;
    FatSetFullNameInFcb(Context1, Dcb, &FirstName);
  }
  if ( (*(_DWORD *)(v13 + 200) & 0x400000) != 0 && v80 && v106 )
    FatSearchRemainderOfDirectoryForCollisions((_DWORD)Context1, v50, (unsigned int)v139, (__int64)&v99);
  if ( v77[1] )
  {
    LOBYTE(Name) = v77[0];
    LOBYTE(v74) = v106 != 0;
    LOWORD(PostIrpRoutine) = *(_WORD *)&v77[6];
    v27 = (__m128i *)FatOpenTargetDirectory(v149, Context1, v5, v50, v101, PostIrpRoutine, v74, Name);
    goto LABEL_46;
  }
  v22 = v106;
  if ( !v106 )
  {
    if ( v91 == 1 || v91 == 4 )
    {
      v24 = -1073741772;
      goto LABEL_154;
    }
    if ( (*(_BYTE *)(&v139[0].MaximumLength + 1) & 2) != 0 )
      DestinationString.Length = 0;
    v24 = FatCheckSystemSecurityAccess(Context1);
    v85.m128i_i32[0] = v24;
    if ( v24 < 0 )
      goto LABEL_229;
    if ( v86 )
    {
      if ( (*(_DWORD *)(v13 + 200) & 0x4000) != 0 )
      {
        IoSetHardErrorOrVerifyDevice(Context1[5], *(PDEVICE_OBJECT *)(*(_QWORD *)(v13 + 192) + 16LL));
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 192) + 16LL) + 48LL) |= 2u;
        *((_DWORD *)Context1 + 18) = -1073741662;
        ExRaiseStatus(-1073741662);
      }
      if ( (_WORD)v111 )
      {
        v24 = -1073741811;
        goto LABEL_154;
      }
      LOWORD(v76) = *(_WORD *)&v77[6];
      v27 = (__m128i *)FatCreateNewDirectory(
                         v147,
                         Context1,
                         *(_QWORD *)v125,
                         v5,
                         v13,
                         Dcb,
                         &DestinationString,
                         &FirstName,
                         v101,
                         v76,
                         v126,
                         v100,
                         v84,
                         (_BYTE)v89,
                         v77[2],
                         (_BYTE)v90);
      goto LABEL_46;
    }
    if ( !v77[4] )
    {
      if ( (*(_DWORD *)(v13 + 200) & 0x4000) != 0 )
      {
        IoSetHardErrorOrVerifyDevice(Context1[5], *(PDEVICE_OBJECT *)(*(_QWORD *)(v13 + 192) + 16LL));
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v13 + 192) + 16LL) + 48LL) |= 2u;
        *((_DWORD *)Context1 + 18) = -1073741662;
        ExRaiseStatus(-1073741662);
      }
      if ( (*(_DWORD *)(v13 + 200) & 0x400000) != 0 && (v99 & 0xC10) != 0 )
        goto LABEL_203;
      v55 = (__m128i *)FatCreateNewFile(
                         (int)&v148,
                         (int)Context1,
                         v125[0],
                         v5,
                         v13,
                         Dcb,
                         (__int64)&DestinationString,
                         &FirstName,
                         v101,
                         *(__int16 *)&v77[6],
                         v104,
                         v126,
                         v100,
                         v84,
                         (__int64)Src,
                         v77[3],
                         v89,
                         v77[2],
                         v90,
                         v82);
      goto LABEL_205;
    }
LABEL_153:
    v24 = -1073741773;
LABEL_154:
    v85.m128i_i32[0] = v24;
    goto LABEL_235;
  }
  v53 = 32 * (unsigned int)((((unsigned __int64)LOWORD(v135[0]) >> 1) + 12) / 0xD);
  v54 = v105 - v53;
  if ( (*(_BYTE *)(v106 + 11) & 0x10) == 0 )
  {
    if ( v81 )
    {
      v24 = -1073741565;
      goto LABEL_154;
    }
    if ( !v77[4] )
    {
      if ( (*(_DWORD *)(v13 + 200) & 0x400000) != 0 && (v99 & 0x20) != 0 && (*(_BYTE *)(v106 + 12) & 1) != 0 )
      {
        LOBYTE(v53) = 1;
        if ( (unsigned __int8)FatFileExtensionIsPfile(v135, v53) )
        {
LABEL_203:
          v24 = -1073741790;
          v85.m128i_i32[0] = -1073741790;
          goto LABEL_235;
        }
      }
      v55 = (__m128i *)FatOpenExistingFile(
                         v146,
                         Context1,
                         v5,
                         v13,
                         &BugCheckParameter3,
                         Dcb,
                         v106,
                         v54,
                         v105,
                         Src,
                         v135,
                         v101,
                         *(_WORD *)&v77[6],
                         v104,
                         v126,
                         v100,
                         v84,
                         v91,
                         v77[3],
                         (_BYTE)v89,
                         v77[2],
                         (_BYTE)v90,
                         v77[0]);
LABEL_205:
      v85 = *v55;
      v24 = _mm_cvtsi128_si32(v85);
      goto LABEL_133;
    }
    goto LABEL_153;
  }
  if ( v103 )
  {
    v24 = -1073741638;
    goto LABEL_154;
  }
  v27 = (__m128i *)FatOpenExistingDirectory(
                     v145,
                     Context1,
                     *(_QWORD *)v125,
                     v5,
                     v13,
                     &BugCheckParameter3,
                     Dcb,
                     v106,
                     (int)v105 - (int)v53,
                     v105,
                     Src,
                     v101,
                     *(_WORD *)&v77[6],
                     v91,
                     (_BYTE)v89);
LABEL_46:
  v28 = *v27;
  v85 = v28;
  *((_QWORD *)Context2 + 7) = _mm_srli_si128(v28, 8).m128i_u64[0];
LABEL_47:
  v24 = _mm_cvtsi128_si32(v28);
LABEL_229:
  if ( v24 >= 0 && !v77[1] )
  {
    v56 = *(_QWORD *)(v5 + 24);
    if ( v56 )
    {
      if ( (unsigned __int16)(*(_WORD *)v56 - 1282) <= 1u && !*(_QWORD *)(v56 + 536) )
        FatSetFullNameInFcb(Context1, v56, &FirstName);
    }
  }
LABEL_235:
  v42 = 1282;
LABEL_236:
  if ( v24 < 0
    && (_BYTE)v90
    && v24 != -1073739511
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
  if ( v24 < 0 )
  {
    LODWORD(Dcb) = *((_DWORD *)Context1 + 17);
    *((_DWORD *)Context1 + 17) = Dcb | 0x808;
    FatUnpinRepinnedBcbs(Context1, v42, v22, Buffer);
    if ( v121 )
    {
      if ( *(_WORD *)v121 == 1283 && *(_QWORD *)(v121 + 320) == v121 + 320 && !*(_DWORD *)(v121 + 232) )
      {
        v57 = *(struct _FILE_OBJECT **)(v121 + 344);
        if ( v57 )
        {
          *(_QWORD *)(v121 + 344) = 0;
          CcUninitializeCacheMap(v57, 0, 0);
          ObfDereferenceObject(v57);
        }
      }
    }
    *((_DWORD *)Context1 + 17) = Dcb;
  }
  FatFreeStringBuffer(&DestinationString, v42, v22, Buffer);
  FatFreeStringBuffer(&SourceString, v58, v59, v60);
  FatFreeStringBuffer(Src, v61, v62, v63);
  v67 = v79;
  if ( v79 )
  {
    if ( !v83 )
    {
      v24 = FatFsdPostRequest(Context1, Context2);
      v85.m128i_i32[0] = v24;
    }
  }
  else
  {
    FatUnpinRepinnedBcbs(Context1, v64, v65, v66);
  }
  ExReleaseResourceLite((PERESOURCE)(v13 + 520));
  if ( !v67 )
  {
    if ( (*(_DWORD *)v101 & 0x20) != 0 )
      *(_DWORD *)(v5 + 80) |= 0x80000u;
    if ( v77[3] && v24 >= 0 )
    {
      if ( !FatReserveMdl )
      {
        Mdl = IoAllocateMdl(0, 0x10000u, 1u, 0, 0);
        _InterlockedCompareExchange64(&FatReserveMdl, (signed __int64)Mdl, 0);
        if ( (struct _MDL *)FatReserveMdl != Mdl )
          IoFreeMdl(Mdl);
      }
      _InterlockedOr(v120, 0x800u);
      if ( (*(_DWORD *)(v13 + 200) & 2) != 0 )
      {
        LOBYTE(v69) = 1;
        FatToggleMediaEjectDisable(v68, v13, v69);
      }
    }
  }
  v71 = (unsigned __int64)(KeGetCurrentProcessorNumber() % (unsigned int)dword_140017D48) << 7;
  v72 = *(_QWORD *)(v13 + 1024);
  if ( v24 )
    ++*(_DWORD *)(v71 + v72 + 64);
  else
    ++*(_DWORD *)(v71 + v72 + 60);
  return (unsigned int)v24;
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
