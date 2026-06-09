# NtfsWriteRawEncrypted

- ea: `0x140280ccc`
- end: `0x140282a44`
- name: `NtfsWriteRawEncrypted`
- size: `7544`
- prototype: `__int64 __fastcall(_DWORD *, IRP *)`
- caller_count: `1`
- callee_count: `32`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1401f5890`

## callees

- `0x140007ea0`
- `0x1400082b0`
- `0x14000c290`
- `0x14000cb00`
- `0x14000d510`
- `0x14000eaa0`
- `0x14001e810`
- `0x140021910`
- `0x14002b680`
- `0x140030418`
- `0x140037db4`
- `0x14003ebc4`
- `0x140041d28`
- `0x14004a204`
- `0x1400592c0`
- `0x1400596c0`
- `0x1400bdce0`
- `0x1400bdd18`
- `0x1400bdd54`
- `0x1400bdd90`
- `0x14012c1ec`
- `0x14013c2d0`
- `0x140140380`
- `0x140150bc0`
- `0x140150c80`
- `0x140151d54`
- `0x14015ec38`
- `0x140160be0`
- `0x140162370`
- `0x1401c00e0`
- `0x1401c08b4`
- `0x140280ccc`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140281ad5`
- `ntoskrnl!IoFreeIrp` at `0x140281b69`
- `ntoskrnl!IoFreeIrp` at `0x140281ad5`
- `ntoskrnl!IoFreeIrp` at `0x140281b69`
- `ntoskrnl!IoAllocateMdl` at `0x140281abd`
- `ntoskrnl!IoAllocateMdl` at `0x140281abd`
- `ntoskrnl!MmProbeAndLockPages` at `0x140281b16`
- `ntoskrnl!MmProbeAndLockPages` at `0x140281b16`
- `ntoskrnl!IoFreeMdl` at `0x140281b52`
- `ntoskrnl!IoFreeMdl` at `0x140281b52`
- `ntoskrnl!MmMdlPageContentsState` at `0x140281b2a`
- `ntoskrnl!MmMdlPageContentsState` at `0x140281b2a`
- `ntoskrnl!IofCallDriver` at `0x140281c66`
- `ntoskrnl!IofCallDriver` at `0x140281c66`
- `ntoskrnl!ProbeForRead` at `0x140281187`
- `ntoskrnl!ProbeForRead` at `0x140281187`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140281a63`
- `ntoskrnl!IoBuildSynchronousFsdRequest` at `0x140281a63`
- `ntoskrnl!KeWaitForSingleObject` at `0x140281c92`
- `ntoskrnl!KeWaitForSingleObject` at `0x140281c92`
- `ntoskrnl!KeInitializeEvent` at `0x140280d69`
- `ntoskrnl!KeInitializeEvent` at `0x140280d69`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028192b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028261b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc499`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028192b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14028261b`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402bc499`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140281975`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140281975`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140281502`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140281502`
- `ntoskrnl!ExReleaseResourceLite` at `0x140282600`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc47e`
- `ntoskrnl!ExReleaseResourceLite` at `0x140282600`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402bc47e`
- `ntoskrnl!CcFlushCache` at `0x140281651`
- `ntoskrnl!CcFlushCache` at `0x140281651`

## pseudocode

```c
__int64 __fastcall NtfsWriteRawEncrypted(_DWORD *a1, IRP *a2)
{
  unsigned int v4; // r14d
  signed __int64 v5; // rbx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _FILE_OBJECT *FileObject; // rax
  __int64 FsContext; // r15
  __int64 FsContext2; // r10
  __int64 v10; // r11
  int v11; // eax
  int v12; // eax
  unsigned int v13; // ebx
  unsigned int v14; // r8d
  unsigned int v16; // r8d
  __int64 v17; // rdx
  unsigned __int16 v18; // r8
  SIZE_T Options; // rdx
  PNAMED_PIPE_CREATE_PARAMETERS Parameters; // r9
  unsigned int ULongFromUser; // eax
  unsigned int InboundQuota; // eax
  unsigned int MaximumInstances; // eax
  unsigned __int16 UShortFromUser; // ax
  char UCharFromUser; // r12
  KPROCESSOR_MODE v26; // r8
  __int64 ULong64FromUser; // rax
  char v28; // al
  unsigned __int16 OutboundQuota; // ax
  __int64 v30; // rax
  _DWORD *v31; // rdi
  int v32; // eax
  unsigned int v33; // eax
  int v34; // eax
  char v35; // di
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned int i; // eax
  __int64 v39; // rcx
  __int16 v40; // cx
  unsigned int v41; // r8d
  int v42; // edi
  unsigned __int16 j; // r12
  __int64 v44; // rcx
  struct _NAMED_PIPE_CREATE_PARAMETERS *v45; // rdx
  __int64 v46; // rax
  KPROCESSOR_MODE v47; // r8
  int v48; // eax
  int v49; // eax
  __int64 v50; // rax
  unsigned int v51; // r8d
  unsigned __int16 v52; // dx
  LONGLONG QuadPart; // r8
  __int64 v54; // r9
  unsigned int v55; // r9d
  char v56; // di
  unsigned int v57; // ebx
  __int64 v58; // rbx
  unsigned int v59; // ecx
  ULONG v60; // r14d
  unsigned __int64 v61; // r12
  unsigned int *v62; // rdi
  unsigned __int64 v63; // r8
  unsigned __int64 PoolWithTag; // r9
  PIRP v65; // rax
  IRP *v66; // rdi
  struct _MDL *Mdl; // rax
  struct _IO_STACK_LOCATION *v68; // rdx
  unsigned int *v69; // r8
  NTSTATUS Status; // eax
  unsigned int v71; // eax
  __int16 v72; // ax
  unsigned int v73; // ebx
  __int64 v74; // rcx
  __int64 v75; // rax
  __int64 v76; // rdx
  __int64 v77; // rdi
  LONGLONG v78; // rbx
  _DWORD *v79; // r10
  LONGLONG v80; // rcx
  signed __int64 v81; // r9
  signed __int64 v82; // r8
  LONGLONG v83; // r8
  signed __int64 v84; // rdx
  struct _FILE_OBJECT *v85; // rcx
  __int64 v86; // rdi
  unsigned int v87; // ecx
  __int64 v88; // rdx
  __int64 v89; // rcx
  LONGLONG v90; // r9
  LONGLONG v91; // rdi
  __int64 v92; // rax
  __int64 v93; // rdx
  __int64 v94; // rbx
  __int64 v95; // r12
  LONGLONG v96; // rbx
  int v97; // eax
  signed __int64 v98; // rcx
  int v99; // edx
  signed __int64 v100; // r9
  signed __int64 v101; // r8
  struct _FILE_OBJECT *v102; // rcx
  __int64 v103; // rdi
  signed __int64 v104; // rbx
  int v105; // r8d
  signed __int64 v106; // rcx
  signed __int64 v107; // rdx
  signed __int64 v108; // rax
  int v109; // r8d
  signed __int64 v110; // r9
  signed __int64 v111; // rdx
  int v112; // ecx
  signed __int64 v113; // r8
  signed __int64 v114; // rdx
  __int64 v115; // rcx
  struct _FILE_OBJECT *v116; // rcx
  PKEVENT Event; // [rsp+28h] [rbp-1B0h]
  NTSTATUS v118; // [rsp+74h] [rbp-164h] BYREF
  char v119; // [rsp+78h] [rbp-160h]
  char v120; // [rsp+79h] [rbp-15Fh]
  unsigned __int16 v121; // [rsp+7Ah] [rbp-15Eh]
  unsigned __int16 v122; // [rsp+7Ch] [rbp-15Ch]
  unsigned int v123; // [rsp+80h] [rbp-158h]
  char v124; // [rsp+84h] [rbp-154h]
  char v125; // [rsp+85h] [rbp-153h]
  union _LARGE_INTEGER StartingOffset; // [rsp+88h] [rbp-150h] BYREF
  struct _NAMED_PIPE_CREATE_PARAMETERS *v127; // [rsp+90h] [rbp-148h]
  unsigned int v128; // [rsp+98h] [rbp-140h]
  int v129; // [rsp+9Ch] [rbp-13Ch]
  unsigned int v130; // [rsp+A0h] [rbp-138h]
  unsigned int *v131; // [rsp+A8h] [rbp-130h]
  __int64 v132; // [rsp+B0h] [rbp-128h]
  unsigned __int16 v133; // [rsp+B8h] [rbp-120h]
  char v134; // [rsp+BCh] [rbp-11Ch]
  unsigned int v135; // [rsp+C0h] [rbp-118h]
  int v136; // [rsp+C4h] [rbp-114h]
  __int64 v137; // [rsp+C8h] [rbp-110h]
  void *v138; // [rsp+D0h] [rbp-108h]
  unsigned int v139; // [rsp+D8h] [rbp-100h]
  int v140; // [rsp+DCh] [rbp-FCh]
  ULONG v141; // [rsp+E0h] [rbp-F8h]
  __int64 v142; // [rsp+E8h] [rbp-F0h]
  __int64 v143; // [rsp+F0h] [rbp-E8h]
  PVOID P; // [rsp+F8h] [rbp-E0h]
  struct _FILE_OBJECT *v145; // [rsp+100h] [rbp-D8h]
  unsigned __int16 v146; // [rsp+108h] [rbp-D0h]
  unsigned int v147; // [rsp+10Ch] [rbp-CCh]
  unsigned int v148; // [rsp+110h] [rbp-C8h]
  PIRP Irp; // [rsp+118h] [rbp-C0h]
  unsigned __int64 v150; // [rsp+120h] [rbp-B8h]
  __int64 v151; // [rsp+128h] [rbp-B0h] BYREF
  __int64 v152; // [rsp+130h] [rbp-A8h]
  __int64 v153; // [rsp+138h] [rbp-A0h]
  __int64 v154; // [rsp+140h] [rbp-98h]
  __int64 v155; // [rsp+148h] [rbp-90h]
  __int64 v156; // [rsp+150h] [rbp-88h]
  PNAMED_PIPE_CREATE_PARAMETERS v157; // [rsp+158h] [rbp-80h]
  ULONG v158; // [rsp+160h] [rbp-78h]
  __int64 v159; // [rsp+168h] [rbp-70h]
  __int64 v160; // [rsp+170h] [rbp-68h]
  struct _KEVENT Object; // [rsp+178h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+190h] [rbp-48h] BYREF
  KPROCESSOR_MODE RequestorMode; // [rsp+1F0h] [rbp+18h]
  signed __int64 v165; // [rsp+1F8h] [rbp+20h]
  char v166; // [rsp+1F8h] [rbp+20h]

  StartingOffset.QuadPart = 0;
  v159 = 0;
  v148 = 0;
  v147 = 0;
  v136 = 0;
  v133 = 0;
  v124 = 0;
  memset(&Object, 0, sizeof(Object));
  IoStatusBlock = 0;
  v118 = 0;
  v125 = 0;
  v4 = 0;
  v5 = 0;
  RequestorMode = a2->RequestorMode;
  a1[3] |= 1u;
  KeInitializeEvent(&Object, SynchronizationEvent, 0);
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  FileObject = CurrentStackLocation->FileObject;
  v145 = FileObject;
  FsContext = (__int64)FileObject->FsContext;
  if ( FsContext )
  {
    FsContext2 = (__int64)FileObject->FsContext2;
    v142 = FsContext2;
    v10 = *(_QWORD *)(FsContext + 192);
    v131 = (unsigned int *)v10;
    v11 = *(_DWORD *)(v10 + 4);
    if ( (v11 & 1) == 0 && (!FsContext2 || *(_BYTE *)(FsContext2 + 88) != 4 || (v11 & 2) == 0) )
      NtfsRaiseStatusInternal((__int64)a1, -1073741202, 0, 0, 0);
    if ( !FsContext2 )
      goto LABEL_10;
    v132 = *(_QWORD *)(FsContext + 184);
    v156 = v132;
    v12 = *(unsigned __int8 *)(FsContext2 + 88);
  }
  else
  {
    v10 = 0;
    v131 = 0;
    FsContext2 = 0;
    v142 = 0;
    v132 = 0;
    v156 = 0;
    v12 = 1;
  }
  if ( v12 != 2 )
  {
LABEL_10:
    v13 = -1073741811;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000000D, 0x1248F6u);
    NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073741811, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1198327;
LABEL_14:
    NtfsStatusTraceAndDebugInternal(0, v13, v14);
    return v13;
  }
  if ( (*(_DWORD *)(v10 + 4) & 0x2000000) != 0 )
  {
    v13 = -1073741662;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC00000A2, 0x124900u);
    NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073741662, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1198337;
    goto LABEL_14;
  }
  a1[68] = *(_DWORD *)(FsContext2 + 100);
  if ( !_bittest16((const signed __int16 *)(FsContext + 460), 0xEu) )
  {
    v4 = -1073740633;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC00004A7, 0x124911u);
    NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073740633, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v4;
    v16 = 1198354;
LABEL_26:
    NtfsStatusTraceAndDebugInternal(0, v4, v16);
    return v4;
  }
  if ( (*(_WORD *)(FsContext2 + 104) & 0x12) == 0 )
  {
    if ( (a1[4] & 0x100000) == 0 && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x20) != 0 )
    {
      v17 = *(_QWORD *)(v10 + 248);
      v18 = *(_WORD *)(v17 + 6);
      if ( v18 > 0x40u || (v18 & 1) != 0 )
        v18 = 0;
      McTemplateU0ppwwpiwd_EtwWriteTransfer(
        (__int64)v131,
        (const EVENT_DESCRIPTOR *)fsctrl_c18715,
        KeGetCurrentThread(),
        v131,
        *(unsigned __int16 *)(v10 + 7872) >> 1,
        *((_QWORD *)v131 + 985),
        v18 >> 1,
        v17 + 32,
        v132,
        *(_QWORD *)(v132 + 8),
        *(unsigned __int16 *)(FsContext2 + 16) >> 1,
        *(_QWORD *)(v142 + 24),
        *(unsigned __int16 *)(FsContext2 + 104));
    }
    v13 = -1073741790;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000022, 0x12492Au);
    NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073741790, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1198379;
    goto LABEL_14;
  }
  if ( (*(_DWORD *)(v10 + 24) & 0x40000) != 0 )
  {
    v13 = -1073740646;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC000049A, 0x124934u);
    NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073740646, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1198389;
    goto LABEL_14;
  }
  Options = CurrentStackLocation->Parameters.Create.Options;
  v135 = Options;
  v140 = Options;
  if ( (unsigned int)Options < 0x20 )
  {
    v13 = -1073741789;
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC0000023, 0x124945u);
    NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073741789, a2 != 0, 0);
    if ( !NtfsStatusDebugFlags )
      return v13;
    v14 = 1198406;
    goto LABEL_14;
  }
  Parameters = CurrentStackLocation->Parameters.CreatePipe.Parameters;
  v127 = Parameters;
  v157 = Parameters;
  if ( CurrentStackLocation[-1].Parameters.Read.Length == -1 )
  {
    v120 = 0;
    CurrentStackLocation[-1].Parameters.Read.Length = 0;
    CurrentStackLocation[-1].Parameters.Create.Options = *(_DWORD *)(FsContext + 40);
    CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = *(_DWORD *)(FsContext + 44);
  }
  else
  {
    v120 = 1;
    LODWORD(v165) = CurrentStackLocation[-1].Parameters.Create.Options;
    HIDWORD(v165) = CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart;
    v5 = v165;
  }
  if ( a2->RequestorMode )
  {
    ProbeForRead(Parameters, Options, 1u);
    Parameters = v127;
  }
  if ( RequestorMode )
  {
    ULongFromUser = RtlReadULongFromUser(&Parameters->CompletionMode);
    Parameters = v127;
  }
  else
  {
    ULongFromUser = Parameters->CompletionMode;
  }
  v128 = ULongFromUser;
  v136 = ULongFromUser;
  if ( RequestorMode )
  {
    InboundQuota = RtlReadULongFromUser(&Parameters->InboundQuota);
    Parameters = v127;
  }
  else
  {
    InboundQuota = Parameters->InboundQuota;
  }
  v123 = InboundQuota;
  v148 = InboundQuota;
  if ( RequestorMode )
  {
    MaximumInstances = RtlReadULongFromUser(&Parameters->MaximumInstances);
    Parameters = v127;
  }
  else
  {
    MaximumInstances = Parameters->MaximumInstances;
  }
  v130 = MaximumInstances;
  v147 = MaximumInstances;
  if ( RequestorMode )
  {
    UShortFromUser = RtlReadUShortFromUser((unsigned __int16 *)&Parameters->DefaultTimeout + 1);
    Parameters = v127;
  }
  else
  {
    UShortFromUser = HIWORD(Parameters->DefaultTimeout.u.LowPart);
  }
  v121 = UShortFromUser;
  v133 = UShortFromUser;
  if ( RequestorMode )
  {
    UCharFromUser = RtlReadUCharFromUser((char *)&Parameters->DefaultTimeout + 1);
    Parameters = v127;
  }
  else
  {
    UCharFromUser = BYTE1(Parameters->DefaultTimeout.LowPart);
  }
  v134 = UCharFromUser;
  v26 = RequestorMode;
  if ( RequestorMode )
  {
    ULong64FromUser = RtlReadULong64FromUser(Parameters);
    Parameters = v127;
    v26 = RequestorMode;
  }
  else
  {
    ULong64FromUser = *(_QWORD *)&Parameters->NamedPipeType;
  }
  v143 = ULong64FromUser;
  StartingOffset.QuadPart = ULong64FromUser;
  v159 = ULong64FromUser;
  if ( v26 )
  {
    v28 = RtlReadUCharFromUser((char *)&Parameters->OutboundQuota + 2);
    Parameters = v127;
    v26 = RequestorMode;
  }
  else
  {
    v28 = BYTE2(Parameters->OutboundQuota);
  }
  v166 = v28;
  v124 = v28;
  if ( v26 )
  {
    RtlReadUCharFromUser((char *)&Parameters->OutboundQuota + 3);
    Parameters = v127;
    v26 = RequestorMode;
  }
  if ( v26 )
  {
    OutboundQuota = RtlReadUShortFromUser((unsigned __int16 *)&Parameters->OutboundQuota);
    Parameters = v127;
    v26 = RequestorMode;
  }
  else
  {
    OutboundQuota = Parameters->OutboundQuota;
  }
  v122 = OutboundQuota;
  v146 = OutboundQuota;
  v30 = 4 * (unsigned int)v121 + 28;
  if ( (unsigned int)v30 <= v128 && (unsigned int)v30 <= v135 )
  {
    if ( v30 + 16 <= (unsigned __int64)v128
      && v30 + 16 <= (unsigned __int64)v135
      && ((v31 = (ULONG *)((char *)&Parameters->NamedPipeType + v30), !v26)
        ? (v32 = *v31)
        : (v32 = RtlReadULongFromUser((unsigned int *)((char *)&Parameters->NamedPipeType + v30)), v26 = RequestorMode),
          v32 == ExtendedEncryptedDataInfoSignature) )
    {
      if ( v26 )
      {
        v33 = RtlReadULongFromUser(v31 + 1);
        v26 = RequestorMode;
      }
      else
      {
        v33 = v31[1];
      }
      if ( v33 < 0x10 )
      {
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC00004AA, 0x1249B8u);
        NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073740630, a2 != 0, 0);
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC00004AA, 0x1249B9u);
        return 3221226666LL;
      }
      if ( v26 )
        LOBYTE(v34) = RtlReadULongFromUser(v31 + 2);
      else
        v34 = v31[2];
      v35 = v118;
      if ( (v34 & 1) != 0 )
        v35 = 1;
      v125 = v35;
    }
    else
    {
      v35 = v118;
    }
    if ( (unsigned __int8)(UCharFromUser - 1) > 1u )
    {
      v13 = -1073741637;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC00000BB, 0x1249DDu);
      NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073741637, a2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v13;
      v14 = 1198558;
      goto LABEL_14;
    }
    if ( v123 > v130 || v122 || !v121 || (v137 = 0, v138 = 0, P = 0, v141 = 0, v119 = 0, v128 > v135) )
    {
      v4 = -1073740630;
      if ( NtfsStatusDebugFlags )
        NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC00004AA, 0x1249E6u);
      NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073740630, a2 != 0, 0);
      if ( !NtfsStatusDebugFlags )
        return v4;
      v16 = 1198567;
      goto LABEL_26;
    }
    v36 = v132;
    v155 = v132 + 328;
    v37 = *(_QWORD *)(v132 + 328);
    if ( v37 )
    {
      ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v37 + 136), 1u);
      v119 = 1;
      if ( (*(_DWORD *)(*(_QWORD *)v155 + 4LL) & 1) != 0 || TxfIsCurrentHandleInTransaction((__int64)a1, v142) )
      {
        v4 = -1072103362;
        if ( NtfsStatusDebugFlags )
          NtfsStatusTraceAndDebugInternal(0, 0xC019003E, 0x124A0Eu);
        v118 = -1072103362;
LABEL_318:
        if ( v119 )
          ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)v155 + 136LL));
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( NtfsStatusDebugFlags
          && v4
          && v4 != 294
          && v4 - 298 > 1
          && v4 < 0xFFFFFFED
          && v4 != -1073741802
          && v4 + 2147483643 > 1
          && v4 != -1073741807
          && v4 != 259
          && v4 != -1073741608 )
        {
          NtfsStatusTraceAndDebugInternal((__int64)a1, v4, 0x124D34u);
        }
        NtfsExtendedCompleteRequestInternal((__int64)a1, a2, v4, a2 != 0, (v4 & 0x80000000) == 0);
        return v4;
      }
      v36 = v132;
    }
    if ( NtfsAcquirePagingResourceExclusive((__int64)a1, v36, 1u) )
    {
      v139 = 0;
      for ( i = 0; ; ++i )
      {
        v139 = i;
        if ( i >= 2 )
          break;
        v39 = *(_QWORD *)&a1[2 * i + 12];
        if ( !v39 || v39 == v132 )
        {
          *(_QWORD *)&a1[2 * i + 12] = v132;
          break;
        }
      }
    }
    NtfsAcquireExclusiveScbEx((__int64)a1, FsContext, 0);
    SetFlagInterlocked((unsigned int *)(FsContext + 200), 0x1000000u);
    v40 = *(_WORD *)(FsContext + 460);
    if ( (v40 & 0x4000) == 0 )
    {
      v4 = -1073740633;
      if ( NtfsStatusDebugFlags )
      {
        v41 = 1198638;
        goto LABEL_316;
      }
      goto LABEL_317;
    }
    if ( v35 && v40 >= 0 )
      NtfsChangeAttributeCompression((__int64)a1, FsContext, v131, v142, v40 | 0x8000);
    CcFlushCache((PSECTION_OBJECT_POINTERS)(*(_QWORD *)(FsContext + 288) + 16LL), 0, 0, &a2->IoStatus);
    NtfsNormalizeAndCleanupTransaction((__int64)a1, (NTSTATUS *)&a2->IoStatus.0);
    if ( !NtfsPurgeCacheSection((__int64)a1, (__int64 *)FsContext, 0, 0, 0) )
    {
      v4 = -1073741797;
      if ( NtfsStatusDebugFlags )
      {
        v41 = 1198661;
        goto LABEL_316;
      }
      goto LABEL_317;
    }
    if ( StartingOffset.QuadPart > *(_QWORD *)(FsContext + 32) || StartingOffset.QuadPart < 0 )
    {
      v4 = -1073740632;
      if ( NtfsStatusDebugFlags )
      {
        v41 = 1198674;
        goto LABEL_316;
      }
LABEL_317:
      v118 = v4;
      goto LABEL_318;
    }
    v42 = 0;
    v129 = 0;
    for ( j = 0; j < v121; ++j )
    {
      v44 = j;
      v45 = v127;
      v46 = (__int64)v127 + 4 * j;
      v47 = RequestorMode;
      if ( RequestorMode )
      {
        v48 = RtlReadULongFromUser((unsigned int *)(v46 + 28));
        v44 = j;
        v45 = v127;
        v47 = RequestorMode;
      }
      else
      {
        v48 = *(_DWORD *)(v46 + 28);
      }
      if ( v48 )
      {
        v50 = (__int64)v45 + 4 * v44;
        if ( v47 )
          v49 = RtlReadULongFromUser((unsigned int *)(v50 + 28));
        else
          v49 = *(_DWORD *)(v50 + 28);
      }
      else
      {
        v49 = 1 << v166;
      }
      v42 += v49;
      v129 = v42;
    }
    if ( v123 != v42 )
    {
      if ( !v120 )
        v5 = *(_QWORD *)(FsContext + 40);
      if ( v143 + v123 < v5 )
      {
        v4 = -1073740631;
        if ( !NtfsStatusDebugFlags )
          goto LABEL_317;
        v51 = 1198721;
        goto LABEL_151;
      }
    }
    NtfsCheckpointCurrentTransaction((__int64)a1);
    NtfsFreeSnapshotsForFcb((__int64)a1, v132);
    v52 = 0;
    QuadPart = StartingOffset.QuadPart;
    v54 = 0;
    while ( 1 )
    {
      v122 = v52;
      if ( v52 >= v121 )
      {
        if ( (v4 & 0x80000000) != 0 )
          goto LABEL_318;
        v103 = v130;
        if ( v130 == v54 && v123 >= v54 )
          goto LABEL_318;
        v104 = v143 + v123;
        NtfsSnapshotScb((__int64)a1, FsContext);
        v105 = *(_DWORD *)(FsContext + 200);
        if ( (v105 & 0x20000) != 0 )
        {
          v106 = v103 + v143;
          if ( *(_QWORD *)(FsContext + 32) < v103 + v143 )
          {
            v107 = *(_QWORD *)(FsContext + 464);
            if ( v106 >= v107 )
              v106 = *(_QWORD *)(FsContext + 464);
            v108 = *(_QWORD *)(FsContext + 40);
            if ( v106 > v108 )
            {
              if ( (v105 & 0x200) != 0 )
              {
                v107 = *(_QWORD *)(FsContext + 464);
                v108 = *(_QWORD *)(FsContext + 40);
              }
              v109 = *(_DWORD *)(FsContext + 200);
              if ( (v109 & 0x20000) != 0 )
              {
                if ( v107 < v106 )
                  goto LABEL_294;
                if ( v108 <= v106 )
                  goto LABEL_295;
                if ( !*(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL) || v106 == 0x7FFFFFFFFFFFFFFFLL )
                {
LABEL_294:
                  *(_QWORD *)(FsContext + 464) = v106;
                }
                else
                {
                  v110 = (v106 + 4095) & 0xFFFFFFFFFFFFF000uLL;
                  if ( v110 < v107 )
                    *(_QWORD *)(FsContext + 464) = v110;
                }
              }
LABEL_295:
              *(_QWORD *)(FsContext + 40) = v106;
            }
          }
        }
        *(_QWORD *)(FsContext + 32) = v103 + v143;
        v111 = *(_QWORD *)(FsContext + 40);
        if ( v104 < v111 )
        {
          if ( (*(_DWORD *)(FsContext + 200) & 0x200) != 0 )
            v111 = *(_QWORD *)(FsContext + 40);
          v112 = *(_DWORD *)(FsContext + 200);
          if ( (v112 & 0x20000) != 0 )
          {
            v113 = *(_QWORD *)(FsContext + 464);
            if ( v113 < v104 )
              goto LABEL_306;
            if ( v111 <= v104 )
              goto LABEL_307;
            if ( !*(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL) || v104 == 0x7FFFFFFFFFFFFFFFLL )
            {
LABEL_306:
              *(_QWORD *)(FsContext + 464) = v104;
            }
            else
            {
              v114 = (v104 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v114 < v113 )
                *(_QWORD *)(FsContext + 464) = v114;
            }
          }
LABEL_307:
          *(_QWORD *)(FsContext + 40) = v104;
        }
        NtfsWriteFileSizes((__int64)a1, FsContext, 0, 0, 1, 1);
        v115 = *(_QWORD *)(FsContext + 40);
        if ( *(_QWORD *)(FsContext + 464) > v115
          && (*(_BYTE *)(FsContext + 460) || (*(_DWORD *)(FsContext + 512) & 1) != 0) )
        {
          *(_QWORD *)(FsContext + 464) = v115;
        }
        v116 = *(struct _FILE_OBJECT **)(FsContext + 280);
        if ( v116 )
          NtfsSetCcFileSizes(v116, FsContext, (struct _CC_FILE_SIZES *)(FsContext + 24));
        goto LABEL_318;
      }
      v55 = v123;
      if ( v123
        || (v56 = v166, *(_DWORD *)(FsContext + 452) > (unsigned int)(1 << v166))
        || *(__int16 *)(FsContext + 460) >= 0 )
      {
        v58 = (__int64)v127 + 4 * v52;
        if ( RequestorMode )
        {
          v57 = RtlReadULongFromUser((unsigned int *)(v58 + 28));
          v55 = v123;
        }
        else
        {
          v57 = *(_DWORD *)(v58 + 28);
        }
        v129 = v57;
        v56 = v166;
        QuadPart = StartingOffset.QuadPart;
      }
      else
      {
        v57 = 0;
        v129 = 0;
      }
      if ( !v57 )
        break;
      if ( v55 )
      {
        v59 = v128 + v57;
        if ( v128 + v57 < v128 )
        {
          v136 = -1;
LABEL_202:
          v4 = -1073740630;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_317;
          v51 = 1198791;
          goto LABEL_151;
        }
        v60 = v57;
        v61 = (unsigned __int64)v127 + v128;
        v128 += v57;
        v136 = v59;
        if ( v59 > v135 )
          goto LABEL_202;
        v62 = v131;
        v63 = v131[91];
        if ( v57 % (unsigned int)v63 || v61 % v63 )
        {
          v60 = -(int)v63 & (v57 + v63 - 1);
          if ( v60 < v57 )
          {
            v4 = -1073740630;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_317;
            v51 = 1198823;
LABEL_151:
            NtfsStatusTraceAndDebugInternal(0, v4, v51);
            goto LABEL_317;
          }
          PoolWithTag = (unsigned __int64)v138;
          if ( !v138 )
            goto LABEL_176;
          if ( v141 < v60 )
          {
            ExFreePoolWithTag(P, 0);
            PoolWithTag = 0;
            v138 = 0;
            v150 = 0;
            P = 0;
          }
          if ( !PoolWithTag )
          {
LABEL_176:
            PoolWithTag = (unsigned __int64)ExAllocatePoolWithTag(
                                              (POOL_TYPE)(PoolType | 0x10),
                                              v60 + v62[91] - 1,
                                              0x6646744Eu);
            v138 = (void *)PoolWithTag;
            P = (PVOID)PoolWithTag;
            v150 = PoolWithTag;
            v141 = v60;
            v158 = v60;
            if ( PoolWithTag % v62[91] )
            {
              PoolWithTag = -v62[91] & ((int)(v62[91] - 1) + PoolWithTag);
              v138 = (void *)PoolWithTag;
              v150 = PoolWithTag;
            }
          }
          if ( RequestorMode )
            RtlCopyFromUser((void *)PoolWithTag, (void *)v61, v57);
          else
            RtlCopyVolatileMemory((void *)PoolWithTag, (const void *)v61, v57);
          v61 = (unsigned __int64)v138;
          memset((char *)v138 + v57, 0, v60 - v57);
          v62 = v131;
        }
        v65 = IoBuildSynchronousFsdRequest(
                4u,
                *(PDEVICE_OBJECT *)(*((_QWORD *)v62 + 31) + 8LL),
                (PVOID)v61,
                v60,
                &StartingOffset,
                &Object,
                &IoStatusBlock);
        v66 = v65;
        Irp = v65;
        if ( !v65 )
        {
          v4 = -1073741670;
          if ( !NtfsStatusDebugFlags )
            goto LABEL_317;
          v51 = 1198861;
          goto LABEL_151;
        }
        if ( (void *)v61 == v138 )
        {
          Mdl = IoAllocateMdl((PVOID)v61, v60, 0, 0, 0);
          v66->MdlAddress = Mdl;
          if ( !Mdl )
          {
            IoFreeIrp(v66);
            Irp = 0;
            v4 = -1073741670;
            if ( !NtfsStatusDebugFlags )
              goto LABEL_317;
            v51 = 1198874;
            goto LABEL_151;
          }
          MmProbeAndLockPages(Mdl, 0, IoWriteAccess);
          MmMdlPageContentsState(v66->MdlAddress, 1);
          v66->UserBuffer = 0;
          v66->RequestorMode = 0;
        }
        else
        {
          v65->UserBuffer = (PVOID)v61;
          v65->RequestorMode = a2->RequestorMode;
        }
        v66->Flags |= 5u;
        v68 = v66->Tail.Overlay.CurrentStackLocation;
        v69 = v131;
        v68[-1].DeviceObject = *(PDEVICE_OBJECT *)(*((_QWORD *)v131 + 31) + 8LL);
        v68[-1].Parameters.Read.ByteOffset = StartingOffset;
        v68[-1].Parameters.Read.Length = v57;
        v68[-1].FileObject = v145;
        v118 = IofCallDriver(*(PDEVICE_OBJECT *)(*((_QWORD *)v69 + 31) + 8LL), v66);
        if ( v118 == 259 )
        {
          Status = KeWaitForSingleObject(&Object, Executive, 0, 0, 0);
          v118 = Status;
          if ( !Status )
            Status = IoStatusBlock.Status;
          v118 = Status;
        }
        NtfsNormalizeAndCleanupTransaction((__int64)a1, &v118);
        v54 = v57 + v137;
        v137 = v54;
        v154 = v54;
        QuadPart = v57 + StartingOffset.QuadPart;
        StartingOffset.QuadPart = QuadPart;
        if ( v57 >= 1 << v166 || v130 <= v123 )
        {
          v71 = 0;
          v4 = v118;
        }
        else
        {
          v4 = v118;
          if ( *(__int16 *)(FsContext + 460) >= 0 )
            v71 = v130 - v123;
          else
            v71 = (1 << v166) - v57;
        }
      }
      else
      {
        v71 = v57;
        v54 = v137;
      }
LABEL_243:
      v86 = v71;
      v153 = v71;
      if ( !v71 )
        goto LABEL_276;
      v151 = 0;
      v152 = 0;
      if ( *(__int16 *)(FsContext + 460) >= 0 )
        v87 = v131[89];
      else
        v87 = *(_DWORD *)(FsContext + 452);
      v88 = -v87;
      v89 = (int)(v87 - 1);
      v90 = v88 & (v89 + QuadPart);
      v91 = v88 & (QuadPart + v89 + v71);
      v92 = *(_QWORD *)(FsContext + 192);
      LOBYTE(v89) = *(_BYTE *)(v92 + 488);
      v93 = *(unsigned int *)(v92 + 480);
      v160 = (v93 + *(_QWORD *)(FsContext + 24)) >> v89;
      v94 = (v93 + v90) >> v89;
      v152 = v94;
      v95 = (v93 + v91) >> v89;
      NtfsPreloadAllocationInternal((__int64)a1, FsContext, 0, v94, v95 - 1, 0);
      if ( *(__int16 *)(FsContext + 460) < 0 )
      {
        if ( NtfsIsRangeAllocated(FsContext, v94, v95, 0, &v151)
          && v151 == (v153 + *(unsigned int *)(*(_QWORD *)(FsContext + 192) + 480LL)) >> *(_BYTE *)(*(_QWORD *)(FsContext + 192)
                                                                                                  + 488LL) )
        {
          goto LABEL_258;
        }
      }
      else if ( *(_QWORD *)(FsContext + 24) >= v91 )
      {
        goto LABEL_258;
      }
      if ( *(__int16 *)(FsContext + 460) >= 0 )
      {
        if ( v160 > v94 )
          v94 = v160;
        v152 = v94;
      }
      if ( v94 <= v95 )
      {
        NtfsDeleteAllocation((__int64)a1, v145, FsContext, v94, v95, 1u, 1);
        LODWORD(Event) = 0;
        NtfsAddAllocation((__int64)a1, (__int64)v145, FsContext, v94, v95 - v94 + 1, Event, 0);
      }
LABEL_258:
      v86 = v153;
      v96 = v153 + StartingOffset.QuadPart;
      NtfsSnapshotScb((__int64)a1, FsContext);
      if ( v96 > *(_QWORD *)(FsContext + 32) )
      {
        v97 = *(_DWORD *)(FsContext + 200);
        if ( (v97 & 0x20000) != 0 )
        {
          v98 = *(_QWORD *)(FsContext + 464);
          if ( v96 < v98 )
            v98 = v96;
          if ( v98 > *(_QWORD *)(FsContext + 40) )
          {
            v99 = *(_DWORD *)(FsContext + 200);
            if ( (v99 & 0x20000) == 0 )
              goto LABEL_271;
            v100 = *(_QWORD *)(FsContext + 464);
            if ( v100 < v98 )
              goto LABEL_270;
            if ( *(_QWORD *)(FsContext + 40) <= v98 )
              goto LABEL_271;
            if ( !*(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL) || v98 == 0x7FFFFFFFFFFFFFFFLL )
            {
LABEL_270:
              *(_QWORD *)(FsContext + 464) = v98;
            }
            else
            {
              v101 = (v98 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v101 < v100 )
                *(_QWORD *)(FsContext + 464) = v101;
            }
LABEL_271:
            *(_QWORD *)(FsContext + 40) = v98;
          }
        }
        *(_QWORD *)(FsContext + 32) = v96;
      }
      NtfsWriteFileSizes((__int64)a1, FsContext, 0, 0, 1, 1);
      v102 = *(struct _FILE_OBJECT **)(FsContext + 280);
      if ( v102 )
        NtfsSetCcFileSizes(v102, FsContext, (struct _CC_FILE_SIZES *)(FsContext + 24));
      NtfsCheckpointCurrentTransaction((__int64)a1);
      NtfsReleaseSharedResources((__int64)a1);
      NtfsFreeSnapshotsForFcb((__int64)a1, v132);
      v54 = v86 + v137;
      v137 = v54;
      v154 = v54;
      QuadPart = StartingOffset.QuadPart;
LABEL_276:
      QuadPart += v86;
      StartingOffset.QuadPart = QuadPart;
      v52 = v122 + 1;
    }
    v72 = *(_WORD *)(FsContext + 460);
    if ( v72 >= 0 )
    {
      NtfsChangeAttributeCompression((__int64)a1, FsContext, v131, v142, v72 | 0x8000);
      QuadPart = StartingOffset.QuadPart;
    }
    v73 = 1 << v56;
    v129 = 1 << v56;
    v74 = *(unsigned int *)(FsContext + 452);
    if ( (1 << v56) % (unsigned int)v74 || QuadPart % v74 )
    {
      v4 = -1073740630;
      if ( !NtfsStatusDebugFlags )
        goto LABEL_317;
      v41 = 1199073;
LABEL_316:
      NtfsStatusTraceAndDebugInternal(0, v4, v41);
      goto LABEL_317;
    }
    v75 = *(_QWORD *)(FsContext + 24);
    if ( v75 )
    {
      v76 = *(_QWORD *)(FsContext + 32);
      if ( v76 != v75 )
        NtfsDeleteAllocation(
          (__int64)a1,
          v145,
          FsContext,
          (v76 + *(unsigned int *)(*(_QWORD *)(FsContext + 192) + 480LL)) >> *(_BYTE *)(*(_QWORD *)(FsContext + 192)
                                                                                      + 488LL),
          0x7FFFFFFFFFFFFFFFLL,
          1u,
          1);
    }
    v77 = v73;
    NtfsAddSparseAllocation((__int64)a1, 0, FsContext, *(_QWORD *)(FsContext + 32), v73);
    v78 = v73 + StartingOffset.QuadPart;
    NtfsSnapshotScb((__int64)a1, FsContext);
    v79 = (_DWORD *)(FsContext + 200);
    if ( v78 <= *(_QWORD *)(FsContext + 32) )
    {
LABEL_227:
      if ( !v123 || v78 <= *(_QWORD *)(FsContext + 40) )
        goto LABEL_238;
      *v79 = *v79;
      if ( (*v79 & 0x20000) != 0 )
      {
        v83 = *(_QWORD *)(FsContext + 464);
        if ( v83 < v78 )
        {
LABEL_236:
          *(_QWORD *)(FsContext + 464) = v78;
          goto LABEL_237;
        }
        if ( *(_QWORD *)(FsContext + 40) > v78 )
        {
          if ( *(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL) && v78 != 0x7FFFFFFFFFFFFFFFLL )
          {
            v84 = (v78 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v84 < v83 )
              *(_QWORD *)(FsContext + 464) = v84;
            goto LABEL_237;
          }
          goto LABEL_236;
        }
      }
LABEL_237:
      *(_QWORD *)(FsContext + 40) = v78;
LABEL_238:
      NtfsWriteFileSizes((__int64)a1, FsContext, 0, 0, 1, 1);
      v85 = *(struct _FILE_OBJECT **)(FsContext + 280);
      if ( v85 )
        NtfsSetCcFileSizes(v85, FsContext, (struct _CC_FILE_SIZES *)(FsContext + 24));
      NtfsCheckpointCurrentTransaction((__int64)a1);
      NtfsReleaseSharedResources((__int64)a1);
      NtfsFreeSnapshotsForFcb((__int64)a1, v132);
      v54 = v77 + v137;
      v137 = v54;
      v154 = v54;
      QuadPart = v77 + StartingOffset.QuadPart;
      StartingOffset.QuadPart += v77;
      v71 = 0;
      goto LABEL_243;
    }
    if ( (*v79 & 0x20000) == 0 )
      goto LABEL_226;
    v80 = *(_QWORD *)(FsContext + 464);
    if ( v78 < v80 )
      v80 = v78;
    if ( v80 <= *(_QWORD *)(FsContext + 40) )
    {
LABEL_226:
      *(_QWORD *)(FsContext + 32) = v78;
      goto LABEL_227;
    }
    if ( (*v79 & 0x20000) != 0 )
    {
      v81 = *(_QWORD *)(FsContext + 464);
      if ( v81 < v80 )
      {
LABEL_224:
        *(_QWORD *)(FsContext + 464) = v80;
        goto LABEL_225;
      }
      if ( *(_QWORD *)(FsContext + 40) > v80 )
      {
        if ( *(_QWORD *)(*(_QWORD *)(FsContext + 288) + 16LL) && v80 != 0x7FFFFFFFFFFFFFFFLL )
        {
          v82 = (v80 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          if ( v82 < v81 )
            *(_QWORD *)(FsContext + 464) = v82;
          goto LABEL_225;
        }
        goto LABEL_224;
      }
    }
LABEL_225:
    *(_QWORD *)(FsContext + 40) = v80;
    goto LABEL_226;
  }
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal((__int64)a1, 0xC00004AA, 0x12499Eu);
  NtfsExtendedCompleteRequestInternal((__int64)a1, a2, -1073740630, a2 != 0, 0);
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0xC00004AA, 0x12499Fu);
  return 3221226666LL;
}

```

## disassembly

```asm
0x140280ccc  mov     r11, rsp
0x140280ccf  mov     [r11+10h], rdx
0x140280cd3  mov     [r11+8], rcx
0x140280cd7  push    rbx
0x140280cd8  push    rsi
0x140280cd9  push    rdi
0x140280cda  push    r12
0x140280cdc  push    r13
0x140280cde  push    r14
0x140280ce0  push    r15
0x140280ce2  sub     rsp, 1A0h
0x140280ce9  mov     rdi, rdx
0x140280cec  mov     r13, rcx
0x140280cef  xor     esi, esi
0x140280cf1  mov     [r11-150h], rsi
0x140280cf8  mov     [r11-70h], rsi
0x140280cfc  mov     [rsp+1D8h+var_C8], esi
0x140280d03  mov     [rsp+1D8h+var_CC], esi
0x140280d0a  mov     [rsp+1D8h+var_114], esi
0x140280d11  mov     [rsp+1D8h+var_120], si
0x140280d19  mov     [rsp+1D8h+var_168], sil
0x140280d1e  mov     [rsp+1D8h+var_154], sil
0x140280d26  xorps   xmm0, xmm0
0x140280d29  xor     eax, eax
0x140280d2b  movups  xmmword ptr [r11-60h], xmm0
0x140280d30  mov     [r11-50h], rax
0x140280d34  movups  xmmword ptr [r11-48h], xmm0
0x140280d39  mov     [rsp+1D8h+var_164], eax
0x140280d3d  mov     [rsp+1D8h+var_153], al
0x140280d44  mov     r14d, esi
0x140280d47  mov     ebx, esi
0x140280d49  mov     [r11+20h], rbx
0x140280d4d  mov     al, [rdx+40h]
0x140280d50  mov     [rsp+1D8h+arg_10], al
0x140280d57  lea     r12d, [rsi+1]
0x140280d5b  or      [rcx+0Ch], r12d
0x140280d5f  xor     r8d, r8d; State
0x140280d62  mov     edx, r12d; Type
0x140280d65  lea     rcx, [r11-60h]; Event
0x140280d69  call    cs:__imp_KeInitializeEvent
0x140280d70  nop     dword ptr [rax+rax+00h]
0x140280d75  mov     rcx, [rdi+0B8h]
0x140280d7c  mov     rax, [rcx+30h]
0x140280d80  mov     [rsp+1D8h+var_D8], rax
0x140280d88  mov     r15, [rax+18h]
0x140280d8c  test    r15, r15
0x140280d8f  jz      short loc_140280DF4
0x140280d91  mov     r10, [rax+20h]
0x140280d95  mov     [rsp+1D8h+var_F0], r10
0x140280d9d  mov     r11, [r15+0C0h]
0x140280da4  mov     [rsp+1D8h+var_130], r11
0x140280dac  mov     eax, [r11+4]
0x140280db0  test    r12b, al
0x140280db3  jnz     short loc_140280DD1
0x140280db5  test    r10, r10
0x140280db8  jz      loc_140282814
0x140280dbe  cmp     byte ptr [r10+58h], 4
0x140280dc3  jnz     loc_140282814
0x140280dc9  test    al, 2
0x140280dcb  jz      loc_140282814
0x140280dd1  test    r10, r10
0x140280dd4  jz      short loc_140280E25
0x140280dd6  mov     rdx, [r15+0B8h]
0x140280ddd  mov     [rsp+1D8h+var_128], rdx
0x140280de5  mov     [rsp+1D8h+var_88], rdx
0x140280ded  movzx   eax, byte ptr [r10+58h]
0x140280df2  jmp     short loc_140280E20
0x140280df4  mov     r11, rsi
0x140280df7  mov     [rsp+1D8h+var_130], rsi
0x140280dff  mov     r10, rsi
0x140280e02  mov     [rsp+1D8h+var_F0], rsi
0x140280e0a  mov     rax, rsi
0x140280e0d  mov     [rsp+1D8h+var_128], rax
0x140280e15  mov     [rsp+1D8h+var_88], rax
0x140280e1d  mov     eax, r12d
0x140280e20  cmp     eax, 2
0x140280e23  jz      short loc_140280E7E
0x140280e25  mov     al, cs:NtfsStatusDebugFlags
0x140280e2b  mov     ebx, 0C000000Dh
0x140280e30  test    al, al
0x140280e32  jz      short loc_140280E44
0x140280e34  mov     r8d, 1248F6h
0x140280e3a  mov     edx, ebx
0x140280e3c  mov     rcx, r13
0x140280e3f  call    NtfsStatusTraceAndDebugInternal
0x140280e44  test    rdi, rdi
0x140280e47  setnz   r9b
0x140280e4b  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x140280e4f  mov     r8d, ebx
0x140280e52  mov     rdx, rdi
0x140280e55  mov     rcx, r13
0x140280e58  call    NtfsExtendedCompleteRequestInternal
0x140280e5d  mov     cl, cs:NtfsStatusDebugFlags
0x140280e63  test    cl, cl
0x140280e65  jz      short loc_140280E76
0x140280e67  mov     r8d, 1248F7h
0x140280e6d  mov     edx, ebx
0x140280e6f  xor     ecx, ecx
0x140280e71  call    NtfsStatusTraceAndDebugInternal
0x140280e76  mov     eax, ebx
0x140280e78  jmp     loc_140282A31
0x140280e7e  test    dword ptr [r11+4], 2000000h
0x140280e86  jz      short loc_140280ED2
0x140280e88  mov     al, cs:NtfsStatusDebugFlags
0x140280e8e  mov     ebx, 0C00000A2h
0x140280e93  test    al, al
0x140280e95  jz      short loc_140280EA7
0x140280e97  mov     r8d, 124900h
0x140280e9d  mov     edx, ebx
0x140280e9f  mov     rcx, r13
0x140280ea2  call    NtfsStatusTraceAndDebugInternal
0x140280ea7  test    rdi, rdi
0x140280eaa  setnz   r9b
0x140280eae  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x140280eb2  mov     r8d, ebx
0x140280eb5  mov     rdx, rdi
0x140280eb8  mov     rcx, r13
0x140280ebb  call    NtfsExtendedCompleteRequestInternal
0x140280ec0  mov     cl, cs:NtfsStatusDebugFlags
0x140280ec6  test    cl, cl
0x140280ec8  jz      short loc_140280E76
0x140280eca  mov     r8d, 124901h
0x140280ed0  jmp     short loc_140280E6D
0x140280ed2  mov     eax, [r10+64h]
0x140280ed6  mov     [r13+110h], eax
0x140280edd  bt      word ptr [r15+1CCh], 0Eh
0x140280ee7  jb      short loc_140280F45
0x140280ee9  mov     al, cs:NtfsStatusDebugFlags
0x140280eef  mov     r14d, 0C00004A7h
0x140280ef5  test    al, al
0x140280ef7  jz      short loc_140280F0A
0x140280ef9  mov     r8d, 124911h
0x140280eff  mov     edx, r14d
0x140280f02  mov     rcx, r13
0x140280f05  call    NtfsStatusTraceAndDebugInternal
0x140280f0a  test    rdi, rdi
0x140280f0d  setnz   r9b
0x140280f11  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x140280f15  mov     r8d, r14d
0x140280f18  mov     rdx, rdi
0x140280f1b  mov     rcx, r13
0x140280f1e  call    NtfsExtendedCompleteRequestInternal
0x140280f23  mov     al, cs:NtfsStatusDebugFlags
0x140280f29  test    al, al
0x140280f2b  jz      short loc_140280F3D
0x140280f2d  mov     r8d, 124912h
0x140280f33  mov     edx, r14d
0x140280f36  xor     ecx, ecx
0x140280f38  call    NtfsStatusTraceAndDebugInternal
0x140280f3d  mov     eax, r14d
0x140280f40  jmp     loc_140282A31
0x140280f45  movzx   r9d, word ptr [r10+68h]
0x140280f4a  test    r9b, 12h
0x140280f4e  jnz     loc_140281066
0x140280f54  mov     eax, [r13+10h]
0x140280f58  bt      rax, 14h
0x140280f5d  jb      loc_140281015
0x140280f63  mov     rax, cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits
0x140280f6a  test    al, 20h
0x140280f6c  jz      loc_140281015
0x140280f72  mov     rdx, [r11+0F8h]
0x140280f79  movzx   r8d, word ptr [rdx+6]
0x140280f7e  cmp     r8w, 40h ; '@'
0x140280f83  ja      short loc_140280F8A
0x140280f85  test    r12b, r8b
0x140280f88  jz      short loc_140280F8D
0x140280f8a  mov     r8d, esi
0x140280f8d  movzx   ecx, word ptr [r10+10h]
0x140280f92  shr     ecx, 1
0x140280f94  add     rdx, 20h ; ' '
0x140280f98  movzx   r10d, r8w
0x140280f9c  shr     r10d, 1
0x140280f9f  movzx   r11d, word ptr [r11+1EC0h]
0x140280fa7  shr     r11d, 1
0x140280faa  mov     r8, gs:188h
0x140280fb3  mov     [rsp+1D8h+var_178], r9d
0x140280fb8  mov     rax, [rsp+1D8h+var_F0]
0x140280fc0  mov     rax, [rax+18h]
0x140280fc4  mov     [rsp+1D8h+var_180], rax
0x140280fc9  mov     [rsp+1D8h+var_188], ecx
0x140280fcd  mov     rcx, [rsp+1D8h+var_128]
0x140280fd5  mov     rax, [rcx+8]
0x140280fd9  mov     [rsp+1D8h+var_190], rax
0x140280fde  mov     [rsp+1D8h+var_198], rcx
0x140280fe3  mov     [rsp+1D8h+var_1A0], rdx
0x140280fe8  mov     dword ptr [rsp+1D8h+IoStatusBlock], r10d
0x140280fed  mov     rcx, [rsp+1D8h+var_130]
0x140280ff5  mov     rax, [rcx+1EC8h]
0x140280ffc  mov     [rsp+1D8h+Event], rax
0x140281001  mov     dword ptr [rsp+1D8h+StartingOffset], r11d
0x140281006  mov     r9, rcx
0x140281009  lea     rdx, fsctrl_c18715
0x140281010  call    McTemplateU0ppwwpiwd_EtwWriteTransfer
0x140281015  mov     al, cs:NtfsStatusDebugFlags
0x14028101b  mov     ebx, 0C0000022h
0x140281020  test    al, al
0x140281022  jz      short loc_140281034
0x140281024  mov     r8d, 12492Ah
0x14028102a  mov     edx, ebx
0x14028102c  mov     rcx, r13
0x14028102f  call    NtfsStatusTraceAndDebugInternal
0x140281034  test    rdi, rdi
0x140281037  setnz   r9b
0x14028103b  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x14028103f  mov     r8d, ebx
0x140281042  mov     rdx, rdi
0x140281045  mov     rcx, r13
0x140281048  call    NtfsExtendedCompleteRequestInternal
0x14028104d  mov     cl, cs:NtfsStatusDebugFlags
0x140281053  test    cl, cl
0x140281055  jz      loc_140280E76
0x14028105b  mov     r8d, 12492Bh
0x140281061  jmp     loc_140280E6D
0x140281066  test    dword ptr [r11+18h], 40000h
0x14028106e  jz      short loc_1402810C1
0x140281070  mov     al, cs:NtfsStatusDebugFlags
0x140281076  mov     ebx, 0C000049Ah
0x14028107b  test    al, al
0x14028107d  jz      short loc_14028108F
0x14028107f  mov     r8d, 124934h
0x140281085  mov     edx, ebx
0x140281087  mov     rcx, r13
0x14028108a  call    NtfsStatusTraceAndDebugInternal
0x14028108f  test    rdi, rdi
0x140281092  setnz   r9b
0x140281096  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x14028109a  mov     r8d, ebx
0x14028109d  mov     rdx, rdi
0x1402810a0  mov     rcx, r13
0x1402810a3  call    NtfsExtendedCompleteRequestInternal
0x1402810a8  mov     cl, cs:NtfsStatusDebugFlags
0x1402810ae  test    cl, cl
0x1402810b0  jz      loc_140280E76
0x1402810b6  mov     r8d, 124935h
0x1402810bc  jmp     loc_140280E6D
0x1402810c1  mov     edx, [rcx+10h]; Length
0x1402810c4  mov     [rsp+1D8h+var_118], edx
0x1402810cb  mov     [rsp+1D8h+var_FC], edx
0x1402810d2  cmp     edx, 20h ; ' '
0x1402810d5  jnb     short loc_140281128
0x1402810d7  mov     al, cs:NtfsStatusDebugFlags
0x1402810dd  mov     ebx, 0C0000023h
0x1402810e2  test    al, al
0x1402810e4  jz      short loc_1402810F6
0x1402810e6  mov     r8d, 124945h
0x1402810ec  mov     edx, ebx
0x1402810ee  mov     rcx, r13
0x1402810f1  call    NtfsStatusTraceAndDebugInternal
0x1402810f6  test    rdi, rdi
0x1402810f9  setnz   r9b
0x1402810fd  mov     dword ptr [rsp+1D8h+StartingOffset], esi
0x140281101  mov     r8d, ebx
0x140281104  mov     rdx, rdi
0x140281107  mov     rcx, r13
0x14028110a  call    NtfsExtendedCompleteRequestInternal
0x14028110f  mov     cl, cs:NtfsStatusDebugFlags
0x140281115  test    cl, cl
0x140281117  jz      loc_140280E76
0x14028111d  mov     r8d, 124946h
0x140281123  jmp     loc_140280E6D
0x140281128  mov     r9, [rcx+20h]
0x14028112c  mov     [rsp+1D8h+var_148], r9
0x140281134  mov     [rsp+1D8h+var_80], r9
0x14028113c  cmp     dword ptr [rcx-40h], 0FFFFFFFFh
0x140281140  jnz     short loc_14028115A
0x140281142  mov     [rsp+1D8h+var_15F], sil
0x140281147  mov     [rcx-40h], esi
0x14028114a  mov     eax, [r15+28h]
0x14028114e  mov     [rcx-38h], eax
0x140281151  mov     eax, [r15+2Ch]
0x140281155  mov     [rcx-30h], eax
0x140281158  jmp     short loc_14028117B
0x14028115a  mov     [rsp+1D8h+var_15F], r12b
0x14028115f  mov     eax, [rcx-38h]
0x140281162  mov     dword ptr [rsp+1D8h+arg_18], eax
0x140281169  mov     eax, [rcx-30h]
0x14028116c  mov     dword ptr [rsp+1D8h+arg_18+4], eax
0x140281173  mov     rbx, [rsp+1D8h+arg_18]
0x14028117b  cmp     [rdi+40h], sil
0x14028117f  jz      short loc_14028119B
0x140281181  mov     r8d, r12d; Alignment
0x140281184  mov     rcx, r9; Address
0x140281187  call    cs:__imp_ProbeForRead
0x14028118e  nop     dword ptr [rax+rax+00h]
0x140281193  mov     r9, [rsp+1D8h+var_148]
0x14028119b  mov     r12b, [rsp+1D8h+arg_10]
0x1402811a3  test    r12b, r12b
0x1402811a6  jz      short loc_1402811BB
0x1402811a8  lea     rcx, [r9+8]
0x1402811ac  call    RtlReadULongFromUser
0x1402811b1  mov     r9, [rsp+1D8h+var_148]
0x1402811b9  jmp     short loc_1402811BF
0x1402811bb  mov     eax, [r9+8]
0x1402811bf  mov     [rsp+1D8h+var_140], eax
0x1402811c6  mov     [rsp+1D8h+var_114], eax
0x1402811cd  test    r12b, r12b
0x1402811d0  jz      short loc_1402811E5
0x1402811d2  lea     rcx, [r9+10h]
0x1402811d6  call    RtlReadULongFromUser
0x1402811db  mov     r9, [rsp+1D8h+var_148]
  ... truncated ...
```
