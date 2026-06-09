# RefsMountVolume(_IRP_CONTEXT *,_IRP *,_VCB * *,_FILE_OBJECT * *)

- ea: `0x140324914`
- end: `0x1403269eb`
- name: `?RefsMountVolume@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAPEAU_VCB@@PEAPEAU_FILE_OBJECT@@@Z`
- size: `8407`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp, struct _VCB **, struct _FILE_OBJECT **)`
- caller_count: `2`
- callee_count: `82`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x140323940`
- `0x140323ce0`

## callees

- `0x140009ecc`
- `0x14000c9b0`
- `0x14000e0e0`
- `0x1400298a0`
- `0x140037820`
- `0x140076a40`
- `0x140076ad0`
- `0x1400862c0`
- `0x140099d90`
- `0x14009e670`
- `0x1400a9850`
- `0x1400a9f80`
- `0x1400ab4e8`
- `0x1400ab688`
- `0x1400adddc`
- `0x1400aecd8`
- `0x1400b2790`
- `0x1400cd01c`
- `0x1400cd0f0`
- `0x1400cf398`
- `0x1400d0fd8`
- `0x1400d30e4`
- `0x1400d3534`
- `0x1400d35d0`
- `0x1400d3b7c`
- `0x1400d3c1c`
- `0x1400d3d1c`
- `0x1400d3d38`
- `0x1400d3da8`
- `0x1400e6524`
- `0x1400e8334`
- `0x1400ebe74`
- `0x1400f3f74`
- `0x1400f8a80`
- `0x1400f8ac0`
- `0x1400f8bd4`
- `0x1400f8c78`
- `0x140102ff0`
- `0x1401186d0`
- `0x140119804`
- `0x1401198b8`
- `0x140119a20`
- `0x140119a84`
- `0x1401f3fb0`
- `0x14028d2c8`
- `0x14028d5a4`
- `0x14028d6e0`
- `0x14028e0ec`
- `0x14028e578`
- `0x1402904d8`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140326383`
- `ntoskrnl!ObfDereferenceObject` at `0x140326383`
- `ntoskrnl!IoGetActivityIdThread` at `0x1403257d7`
- `ntoskrnl!IoGetActivityIdThread` at `0x140326948`
- `ntoskrnl!IoGetActivityIdThread` at `0x1403257d7`
- `ntoskrnl!IoGetActivityIdThread` at `0x140326948`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403262c6`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140326309`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403262c6`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x140326309`
- `ntoskrnl!KdDebuggerEnabled` at `0x140324a2a`
- `ntoskrnl!FsRtlDedupChangeInit` at `0x140325826`
- `ntoskrnl!FsRtlDedupChangeInit` at `0x140325826`
- `ntoskrnl!ObfReferenceObject` at `0x140325d73`
- `ntoskrnl!ObfReferenceObject` at `0x140325d73`
- `ntoskrnl!FsRtlBalanceReads` at `0x14032587f`
- `ntoskrnl!FsRtlBalanceReads` at `0x14032587f`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325eb9`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325ef4`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325f2f`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325f6a`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325fa5`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325fe0`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14032601b`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343ac7`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343b15`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343b53`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343b91`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343bcf`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343c0d`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343c4b`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325eb9`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325ef4`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325f2f`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325f6a`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325fa5`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140325fe0`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14032601b`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343ac7`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343b15`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343b53`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343b91`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343bcf`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343c0d`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140343c4b`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14032621c`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x14032621c`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1403262ab`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1403262ab`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140343a1c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140343a4c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140343a1c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140343a4c`
- `ntoskrnl!PcwCreateInstance` at `0x1403253a7`
- `ntoskrnl!PcwCreateInstance` at `0x1403253a7`
- `ntoskrnl!ExReleaseFastResource` at `0x1403262e7`
- `ntoskrnl!ExReleaseFastResource` at `0x140326349`
- `ntoskrnl!ExReleaseFastResource` at `0x1403262e7`
- `ntoskrnl!ExReleaseFastResource` at `0x140326349`

## string_xrefs

- `0x140324ca9`: `mount.c`
- `0x14032567c`: `mount.c`
- `0x1403263e5`: `mount.c`
- `0x140326475`: `mount.c`
- `0x1403264ed`: `mount.c`
- `0x14032655f`: `mount.c`
- `0x1403265d2`: `mount.c`
- `0x140326651`: `mount.c`
- `0x1403266c9`: `mount.c`
- `0x140326743`: `mount.c`
- `0x1403267bb`: `mount.c`
- `0x14032682f`: `mount.c`
- `0x1403268a6`: `mount.c`
- `0x14032691d`: `mount.c`
- `0x1403269ce`: `mount.c`

## pseudocode

```c
__int64 __fastcall RefsMountVolume(
        struct CmsTransactionContext **a1,
        PIRP Irp,
        struct _VCB **a3,
        struct _FILE_OBJECT **a4)
{
  PIRP v4; // r10
  __int64 v6; // rsi
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _VPB *Vpb; // r11
  struct _DEVICE_OBJECT *RealDevice; // r8
  NTSTATUS BootSectorForMount; // ebx
  unsigned int v11; // r9d
  struct _DEVICE_OBJECT *DeviceObject; // r9
  ULONG *p_Flags; // r14
  __int64 v14; // rdi
  __int64 v15; // rbx
  struct _UNICODE_STRING *v16; // rcx
  unsigned int v17; // r8d
  __int64 v18; // rdx
  bool v19; // zf
  ULONG v20; // ecx
  int v21; // edx
  ULONG v22; // ecx
  unsigned int v23; // edx
  unsigned __int64 v24; // rbx
  unsigned int v25; // r8d
  unsigned int v26; // ecx
  int v27; // eax
  unsigned int v28; // r8d
  int started; // eax
  unsigned int v30; // r8d
  unsigned int v31; // r8d
  NTSTATUS v32; // r10d
  __int16 v33; // cx
  struct _VPB *v34; // rax
  int v35; // ecx
  __int64 v36; // rcx
  __int64 v37; // r8
  unsigned int v38; // r8d
  __int64 v39; // rcx
  __int64 v40; // rsi
  int v41; // ebx
  __int64 VolumeUniqueGuid; // rax
  __int64 v43; // r9
  struct _VPB *v44; // rbx
  __int64 v45; // r9
  __int64 v46; // r8
  unsigned int v47; // r8d
  unsigned int v48; // ecx
  unsigned int v49; // r8d
  NTSTATUS v50; // r10d
  int v51; // eax
  unsigned int v52; // r8d
  NTSTATUS updated; // ecx
  unsigned int v54; // r8d
  NTSTATUS v55; // ecx
  unsigned int v56; // r8d
  NTSTATUS v57; // ecx
  unsigned int v58; // r8d
  _DWORD *v59; // r12
  _DWORD *v60; // roff
  struct _FILE_OBJECT *v61; // rcx
  struct _IRP *MasterIrp; // rbx
  __int64 v63; // rcx
  char v64; // r8
  CCHAR StackSize; // dl
  char v66; // dl
  __int64 v67; // rax
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  char v74; // r12
  struct _UNICODE_STRING *v75; // rcx
  int v76; // ebx
  __int64 v77; // r9
  __int64 v78; // r8
  int v79; // ecx
  __int64 v80; // r8
  __int64 v81; // r8
  _QWORD *v82; // rdx
  char v84; // bl
  int ActivityIdThread; // eax
  int v86; // ecx
  int v87; // edx
  int v88; // r9d
  PPCW_DATA Data; // [rsp+B8h] [rbp-258h]
  int Context; // [rsp+C0h] [rbp-250h]
  ULONG v91; // [rsp+D0h] [rbp-240h]
  int v92; // [rsp+D8h] [rbp-238h]
  int v93; // [rsp+E0h] [rbp-230h]
  int v94; // [rsp+E8h] [rbp-228h]
  NTSTATUS Status; // [rsp+128h] [rbp-1E8h]
  NTSTATUS Statusa; // [rsp+128h] [rbp-1E8h]
  bool v97; // [rsp+12Ch] [rbp-1E4h]
  char v98; // [rsp+12Dh] [rbp-1E3h]
  char v99; // [rsp+12Eh] [rbp-1E2h]
  char v100; // [rsp+12Fh] [rbp-1E1h] BYREF
  bool v101; // [rsp+130h] [rbp-1E0h]
  bool v102; // [rsp+131h] [rbp-1DFh]
  char v103; // [rsp+132h] [rbp-1DEh]
  char v104; // [rsp+133h] [rbp-1DDh]
  int v105; // [rsp+134h] [rbp-1DCh]
  bool v106; // [rsp+138h] [rbp-1D8h]
  unsigned int v107; // [rsp+13Ch] [rbp-1D4h]
  struct _DEVICE_OBJECT **p_RealDevice; // [rsp+140h] [rbp-1D0h]
  int v109; // [rsp+148h] [rbp-1C8h]
  _DWORD *v110; // [rsp+150h] [rbp-1C0h]
  PIRP Irpa; // [rsp+158h] [rbp-1B8h]
  struct _VPB *v112; // [rsp+160h] [rbp-1B0h]
  char v113; // [rsp+168h] [rbp-1A8h]
  char v114; // [rsp+169h] [rbp-1A7h]
  char v115; // [rsp+16Ah] [rbp-1A6h]
  char v116; // [rsp+16Bh] [rbp-1A5h]
  bool v117; // [rsp+16Ch] [rbp-1A4h]
  bool v118; // [rsp+16Dh] [rbp-1A3h]
  bool v119; // [rsp+170h] [rbp-1A0h]
  char v120; // [rsp+171h] [rbp-19Fh]
  char v121; // [rsp+172h] [rbp-19Eh]
  char v122; // [rsp+173h] [rbp-19Dh]
  char v123; // [rsp+174h] [rbp-19Ch]
  char v124; // [rsp+175h] [rbp-19Bh]
  char v125; // [rsp+176h] [rbp-19Ah]
  char v126; // [rsp+177h] [rbp-199h]
  char v127; // [rsp+178h] [rbp-198h]
  bool v128; // [rsp+179h] [rbp-197h]
  bool v129; // [rsp+17Ah] [rbp-196h]
  char v130; // [rsp+17Bh] [rbp-195h]
  char v131; // [rsp+17Ch] [rbp-194h]
  char v132; // [rsp+17Dh] [rbp-193h]
  char v133; // [rsp+17Eh] [rbp-192h]
  char v134; // [rsp+17Fh] [rbp-191h]
  char v135; // [rsp+180h] [rbp-190h]
  char v136; // [rsp+181h] [rbp-18Fh]
  char v137; // [rsp+182h] [rbp-18Eh]
  bool v138; // [rsp+183h] [rbp-18Dh]
  bool v139; // [rsp+184h] [rbp-18Ch]
  bool v140; // [rsp+185h] [rbp-18Bh]
  int v141; // [rsp+188h] [rbp-188h]
  bool v142; // [rsp+18Ch] [rbp-184h]
  char v143; // [rsp+18Dh] [rbp-183h]
  char v144; // [rsp+18Eh] [rbp-182h]
  char v145; // [rsp+18Fh] [rbp-181h]
  struct _IRP_CONTEXT *v146; // [rsp+190h] [rbp-180h]
  char v147; // [rsp+198h] [rbp-178h]
  __int64 v148; // [rsp+1A0h] [rbp-170h]
  ULONG *v149; // [rsp+1A8h] [rbp-168h]
  PDEVICE_OBJECT v150; // [rsp+1B0h] [rbp-160h] BYREF
  PDEVICE_OBJECT TargetDevice; // [rsp+1B8h] [rbp-158h]
  struct _VPB *v152; // [rsp+1C0h] [rbp-150h]
  int v153; // [rsp+1C8h] [rbp-148h]
  ULONG_PTR v154; // [rsp+1D0h] [rbp-140h] BYREF
  struct _IO_STACK_LOCATION *v155; // [rsp+1D8h] [rbp-138h]
  struct _DEVICE_OBJECT **v156; // [rsp+1E0h] [rbp-130h]
  PIRP v157; // [rsp+1E8h] [rbp-128h]
  struct _DEVICE_OBJECT *v158; // [rsp+1F0h] [rbp-120h]
  struct _DEVICE_OBJECT *v159; // [rsp+1F8h] [rbp-118h]
  __int64 v160; // [rsp+200h] [rbp-110h] BYREF
  int v161; // [rsp+208h] [rbp-108h]
  unsigned __int8 *v162; // [rsp+210h] [rbp-100h]
  unsigned __int8 *v163; // [rsp+218h] [rbp-F8h]
  _QWORD *v164; // [rsp+220h] [rbp-F0h]
  int v165; // [rsp+228h] [rbp-E8h]
  int v166; // [rsp+22Ch] [rbp-E4h]
  int v167; // [rsp+230h] [rbp-E0h]
  BOOL v169; // [rsp+23Ch] [rbp-D4h]
  int v173; // [rsp+24Ch] [rbp-C4h]
  int v174; // [rsp+250h] [rbp-C0h]
  int v175; // [rsp+254h] [rbp-BCh]
  int v176; // [rsp+258h] [rbp-B8h]
  int v177; // [rsp+25Ch] [rbp-B4h]
  int v178; // [rsp+260h] [rbp-B0h]
  int v179; // [rsp+264h] [rbp-ACh]
  int v180; // [rsp+268h] [rbp-A8h]
  int v182; // [rsp+270h] [rbp-A0h]
  int v183; // [rsp+274h] [rbp-9Ch]
  char v184[4]; // [rsp+278h] [rbp-98h]
  int v185; // [rsp+27Ch] [rbp-94h]
  int v187; // [rsp+284h] [rbp-8Ch]
  int v188; // [rsp+288h] [rbp-88h]
  struct _FILE_OBJECT **v189; // [rsp+290h] [rbp-80h]
  struct _VCB **v190; // [rsp+298h] [rbp-78h]
  struct _PCW_DATA v191; // [rsp+2A0h] [rbp-70h] BYREF
  int *v192; // [rsp+2B0h] [rbp-60h]
  __int64 v193; // [rsp+2B8h] [rbp-58h]
  __int64 v194; // [rsp+2C0h] [rbp-50h] BYREF
  ULONG v195; // [rsp+2C8h] [rbp-48h]

  v4 = Irp;
  Irpa = Irp;
  v146 = (struct _IRP_CONTEXT *)a1;
  v157 = Irp;
  v190 = a3;
  v189 = a4;
  v150 = 0;
  v149 = 0;
  v104 = 0;
  v98 = 1;
  v103 = 0;
  v101 = 0;
  v106 = 0;
  v107 = 0;
  v6 = 0;
  v105 = 0;
  v160 = 0;
  v102 = 0;
  v110 = 0;
  v148 = 0;
  v155 = 0;
  v100 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids);
    v4 = Irpa;
  }
  if ( !dword_14026DDE8 && (_BYTE)KdDebuggerEnabled && dword_14026DDEC )
    __debugbreak();
  if ( dword_14026DDF0 || dword_14026DDE8 )
  {
    BootSectorForMount = -1073741489;
    RefsCompleteRequest((struct _IRP_CONTEXT *)a1, v4, -1073741489);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids, 3221225807LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v11 = 357;
      goto LABEL_218;
    }
    return (unsigned int)BootSectorForMount;
  }
  CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
  Vpb = CurrentStackLocation->Parameters.MountVolume.Vpb;
  v152 = Vpb;
  p_RealDevice = &Vpb->RealDevice;
  RealDevice = Vpb->RealDevice;
  if ( (RealDevice->Characteristics & 5) != 0 )
  {
    v4->IoStatus.Information = 0;
    BootSectorForMount = -1073741489;
    RefsCompleteRequest((struct _IRP_CONTEXT *)a1, v4, -1073741489);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids, 3221225807LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v11 = 378;
LABEL_218:
      RefsStatusDebug(BootSectorForMount, 0, "mount.c", v11);
      return (unsigned int)BootSectorForMount;
    }
    return (unsigned int)BootSectorForMount;
  }
  DeviceObject = CurrentStackLocation->Parameters.MountVolume.DeviceObject;
  TargetDevice = DeviceObject;
  RealDevice->Flags &= ~2u;
  if ( (PUNICODE_STRING)qword_14026DDF8 != CurrentStackLocation->Parameters.QueryDirectory.FileName )
  {
    v155 = CurrentStackLocation;
    v112 = Vpb;
    v156 = &Vpb->RealDevice;
    if ( ((unsigned __int16)dword_1402682EC & 0x1000) != 0 )
    {
      BootSectorForMount = -1073741077;
      RefsCompleteRequest((struct _IRP_CONTEXT *)a1, v4, -1073741077);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids, 3221226219LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v11 = 398;
        goto LABEL_218;
      }
      return (unsigned int)BootSectorForMount;
    }
    v158 = DeviceObject;
    p_Flags = 0;
    v149 = 0;
    v14 = MEMORY[0xFFFFF78000000320];
    v148 = MEMORY[0xFFFFF78000000320];
    v15 = MEMORY[0xFFFFF78000000014];
    v110 = (_DWORD *)MEMORY[0xFFFFF78000000014];
    Status = InitializeDevice((struct _IRP_CONTEXT *)a1, Vpb, TargetDevice, &v150);
    if ( Status < 0 )
    {
      BootSectorForMount = Status;
    }
    else
    {
      p_Flags = (ULONG *)a1[8];
      v149 = p_Flags;
      *((_QWORD *)p_Flags + 838) = v110;
      *((_QWORD *)p_Flags + 842) = v15;
      *((_QWORD *)p_Flags + 843) = v15;
      *((_QWORD *)p_Flags + 1245) = v14;
      *((_QWORD *)p_Flags + 1246) = v14;
      *((_QWORD *)p_Flags + 1247) = v14;
      *((_QWORD *)p_Flags + 862) = v14;
      *((_QWORD *)p_Flags + 863) = v14;
      *((_QWORD *)p_Flags + 844) = 0;
      *((_QWORD *)p_Flags + 860) = 0;
      *((_QWORD *)p_Flags + 906) = 0;
      *((_QWORD *)p_Flags + 851) = 0;
      *((_QWORD *)p_Flags + 950) = 0;
      RefsQueryNumberDataCopies((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags, 0, 0);
      p_Flags[107] = -1;
      RefsQueryPowerProtectedMode((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags, 0, 0);
      BootSectorForMount = _VCB::ReadBootSectorForMount((_VCB *)p_Flags, (const struct _IRP_CONTEXT *)a1);
      Status = BootSectorForMount;
      if ( BootSectorForMount >= 0 )
      {
        v18 = *((_QWORD *)p_Flags + 1639);
        v156 = (struct _DEVICE_OBJECT **)v18;
        v159 = (struct _DEVICE_OBJECT *)(v18 + 44);
        if ( *(_DWORD *)(v18 + 44) & 0x100 )
          p_Flags[6] |= 0x2000000u;
        v99 = *(_BYTE *)(v18 + 40);
        if ( v99 != 3 || *(_BYTE *)(v18 + 41) > 0xFu )
        {
LABEL_297:
          if ( (Microsoft_Windows_ReFSEnableBits & 0x10) != 0 )
          {
            v84 = *(_BYTE *)(v18 + 41);
            ActivityIdThread = IoGetActivityIdThread();
            LOBYTE(v86) = v99;
            McTemplateK0uuuu_EtwWriteTransfer(v86, v87, ActivityIdThread, v88, (_DWORD)Data, v99, v84);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
              3221225807LL);
          }
          v136 = (char)RefsStatusDebugEnabled;
          v137 = (char)RefsStatusDebugEnabled;
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741489, (struct _IRP_CONTEXT *)a1, "mount.c", 0x1F0u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741489, v17);
          __debugbreak();
          JUMPOUT(0x1403269EBLL);
        }
        v160 = *(_QWORD *)(v18 + 64);
        if ( !v160 )
        {
          v160 = 0x4000000;
          v19 = (p_Flags[6] & 0x2000000) == 0;
          v173 = p_Flags[6] & 0x2000000;
          v138 = !v19;
          v139 = !v19;
          v102 = v173 == 0;
        }
        InitializeVcbFromBootSector(p_Flags, v152, v18);
        if ( ((*p_RealDevice)->Flags & 0x100) != 0 )
        {
          ++p_Flags[58];
          p_Flags[7] |= 0x1000u;
          LODWORD(dword_1402682EC) = (unsigned int)dword_1402682EC | 0x100000;
        }
        RefsFillVcbVolumeName((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags, 1u);
        BootSectorForMount = MsKmeInitializeReservedIoRequestsForVcb((struct _VCB *)p_Flags);
        Status = BootSectorForMount;
        if ( BootSectorForMount < 0 )
          goto LABEL_156;
        BootSectorForMount = MsKmeInitializeReservedIoRunsForVcb((struct _VCB *)p_Flags);
        Status = BootSectorForMount;
        if ( BootSectorForMount < 0 )
          goto LABEL_156;
        v103 = 1;
        v110 = p_Flags + 6;
        v20 = p_Flags[6];
        v21 = v20 & 0x2000000;
        v174 = v20 & 0x2000000;
        if ( (v20 & 0x2000000) != 0 )
        {
          v6 = 2;
          v105 = 2;
        }
        v175 = v20 & 0x80;
        if ( (v20 & 0x80) != 0 )
        {
          v6 = (unsigned int)v6 | 0x40;
          v105 = v6;
        }
        v112 = (struct _VPB *)(p_Flags + 7);
        v22 = p_Flags[7];
        v176 = v22 & 0x10;
        if ( (v22 & 0x10) != 0 )
        {
          LODWORD(v6) = v6 | 0x100000;
          v105 = v6;
        }
        v177 = (unsigned __int16)dword_1402682EC & 0x8000;
        v140 = v177 != 0;
        if ( ((unsigned __int16)dword_1402682EC & 0x8000) != 0 )
        {
          v6 = (unsigned int)v6 | 8;
          v105 = v6;
        }
        if ( dword_140268164 == 1 )
        {
          LODWORD(v6) = v6 | 0x1000000;
          v105 = v6;
        }
        if ( dword_140268164 == 2 )
        {
          v6 = (unsigned int)v6 | 0x2000000;
          v105 = v6;
        }
        LODWORD(v6) = v6 | 0x80000;
        v105 = v6;
        v178 = v22 & 0x200;
        if ( (v22 & 0x200) != 0 )
        {
          v179 = v21;
          if ( !v21 && p_Flags[1572] == 16 )
          {
            LODWORD(v6) = v6 | 0x1000;
            v105 = v6;
          }
        }
        v23 = v6;
        v180 = v22 & 0x100;
        if ( (v22 & 0x100) != 0 )
        {
          LODWORD(v6) = v6 | 0x10000000;
          v105 = v6;
          v23 = v6;
        }
        v24 = (unsigned __int64)v159;
        if ( *(_DWORD *)&v159->Type & 0x10 )
        {
          v6 = v23;
          LODWORD(v6) = v23 | 0x4000;
          v105 = v23 | 0x4000;
          v23 |= 0x4000u;
        }
        v192 = (int *)(*(_QWORD *)(*((_QWORD *)p_Flags + 26) + 16LL) + 48LL);
        v183 = *v192;
        *(_DWORD *)v184 = v183;
        v185 = v183;
        LODWORD(v162) = v183;
        LODWORD(v163) = v183;
        v142 = (v183 & 0x600100) != 0;
        if ( (v183 & 0x600100) != 0 )
        {
          v6 = v23;
          LODWORD(v6) = v23 | 0x200000;
          v105 = v23 | 0x200000;
        }
        RefsFillVcbVolumeGuid((struct _IRP_CONTEXT *)a1);
        v163 = (unsigned __int8 *)(p_Flags + 198);
        v162 = (unsigned __int8 *)p_Flags + 793;
        v26 = *((unsigned __int8 *)p_Flags + 793) | (*((unsigned __int8 *)p_Flags + 792) << 8);
        if ( v26 >= 0x306 )
        {
          v161 = v26 > 0x306;
          if ( v26 >= 0x30B )
          {
            v109 = v26 > 0x30B;
            p_Flags[2686] = 480;
            p_Flags[2687] = 512;
            p_Flags[2688] = 496;
          }
          else
          {
            v109 = -1;
            p_Flags[2686] = 448;
            p_Flags[2687] = 416;
            p_Flags[2688] = 464;
          }
        }
        else
        {
          v161 = -1;
          LODWORD(v164) = *(_DWORD *)v24 & 4;
          if ( !(_DWORD)v164 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                17,
                WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                3221226140LL);
            }
            v143 = (char)RefsStatusDebugEnabled;
            v144 = (char)RefsStatusDebugEnabled;
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741156, (struct _IRP_CONTEXT *)a1, "mount.c", 0x2A3u);
            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741156, v25);
            goto LABEL_227;
          }
          p_Flags[2686] = 384;
          p_Flags[2687] = 416;
          p_Flags[2688] = 400;
        }
        p_RealDevice = (struct _DEVICE_OBJECT **)(p_Flags + 28);
        v27 = MsInitializeVolume(
                (struct _VCB *)p_Flags,
                p_Flags[138],
                Context,
                v6,
                v91,
                v92,
                v93,
                v94,
                *((unsigned __int8 *)v156 + 40),
                *((unsigned __int8 *)v156 + 41),
                (__int64)(p_Flags + 28),
                (__int64)&v100,
                (__int64)v156[8],
                *((_WORD *)p_Flags + 397));
        v24 = (unsigned int)v27;
        Status = v27;
        if ( v27 >= 0 )
        {
          InitializeVcbWithPerMachineState((struct _VCB *)p_Flags);
          RefsBindMinstoreTransaction((struct _IRP_CONTEXT *)a1);
          v164 = a1 + 3;
          started = MsStartTrashTable(a1[3]);
          v24 = (unsigned int)started;
          Status = started;
          if ( started >= 0 )
          {
            RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
            v24 = (unsigned __int64)&WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              Data = (PPCW_DATA)*((_QWORD *)p_Flags + 1337);
              WPP_SF_ii(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                *((_QWORD *)p_Flags + 1336));
            }
            p_Flags[2552] = 1;
            if ( *(_DWORD *)&v112->Type & 0x10 )
            {
              v6 = (__int64)p_RealDevice;
            }
            else
            {
              IoPerfInitializeEntityData((struct _IO_PERF_ENTITY_DATA *)(p_Flags + 2576));
              v6 = (__int64)p_RealDevice;
              if ( (unsigned __int8)MsIsVolumeOnSmr(*p_RealDevice) )
              {
                ++p_Flags[2552];
                IoPerfInitializeEntityData((struct _IO_PERF_ENTITY_DATA *)(p_Flags + 2624));
              }
            }
            RefsInitializePerVolumeTelemetry(a1[8]);
            *((_QWORD *)p_Flags + 836) = MsGetVolumePerfCounterBlock(*(_QWORD *)v6);
            *((_QWORD *)p_Flags + 837) = 0;
            if ( RefsPcwCmsCounterSet && *((_QWORD *)p_Flags + 836) && *((_WORD *)p_Flags + 3076) )
            {
              v191.Data = (const void *)*((_QWORD *)p_Flags + 836);
              v191.Size = 608;
              PcwCreateInstance(
                (PPCW_INSTANCE *)p_Flags + 837,
                RefsPcwCmsCounterSet,
                (PCUNICODE_STRING)(p_Flags + 1538),
                1u,
                &v191);
            }
            v32 = InitializeRefsSchemas(*(struct CmsVolume **)v6);
            Status = v32;
            if ( v32 >= 0 )
            {
              InitializeVolumeInfoTable((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
              v33 = v107;
              v187 = v107 & 0x200;
              v34 = v112;
              if ( (v107 & 0x200) != 0 )
                *(_DWORD *)&v112->Type |= 0x4000u;
              v35 = v33 & 0x400;
              v188 = v35;
              if ( v35 )
                *(_DWORD *)&v34->Type |= 0x8000u;
              v165 = v35;
              if ( v35 )
                MsChangeVolumeOptionDynamically(*(_QWORD *)v6, 0x80000, 0);
              if ( (unsigned __int8)MsIsReallocateAllDataWritesEnabled(*(_QWORD *)v6) )
              {
                LOBYTE(v37) = 1;
                MsChangeVolumeOptionDynamically(v36, 256, v37);
              }
              MsChangeVolumeContainerRotationThresholds(
                *(_QWORD *)v6,
                dword_1402688A4,
                dword_1402688A8,
                dword_1402688AC,
                dword_1402688B0,
                dword_1402688B4);
              MsChangeVolumeContainerRotationEventThresholds(*(_QWORD *)v6, (unsigned int)dword_1402688B8);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 1, &RefsTelemetrySampling);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 2, (char *)&RefsTelemetrySampling + 8);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 3, &qword_140267908);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 4, &qword_140267910);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 6, &qword_140267918);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 7, &qword_140267920);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 8, &qword_140267928);
              _InterlockedExchange64((volatile __int64 *)p_Flags + 858, qword_140267900);
              _InterlockedExchange64((volatile __int64 *)p_Flags + 1150, qword_140267930);
              v166 = v107 & 4;
              v97 = v166 != 0;
              v117 = v166 != 0;
              v101 = v166 != 0;
              v167 = v107 & 0x40;
              v99 = v167 != 0;
              v118 = v167 != 0;
              v106 = v167 != 0;
              InitializeVcbDeviceName((struct _IRP_CONTEXT *)a1);
              if ( *(_DWORD *)&v112->Type & 0x10 )
              {
LABEL_108:
                v6 = (__int64)v110;
                if ( !(*v110 & 8) )
                  FsRtlBalanceReads(TargetDevice);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                CreateTemplateFiles((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                LOBYTE(v45) = v99;
                LOBYTE(v46) = v97;
                OpenRootDirectory(a1, p_Flags, v46, v45);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                OpenMetadataDirectory((struct _IRP_CONTEXT *)a1);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                OpenDegenerateMetadataDirectory((struct _IRP_CONTEXT *)a1);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                LODWORD(v24) = RefsSecurityInitialize((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
                Statusa = v24;
                if ( (v24 & 0x80000000) == 0LL )
                {
                  OpenSecurityFile((struct _IRP_CONTEXT *)a1);
                  RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                  if ( *(_DWORD *)v6 & 0x2000000 )
                    goto LABEL_118;
                  v48 = *v162 | (*v163 << 8);
                  if ( v48 >= 0x307 )
                  {
                    if ( v48 > 0x307 )
                    {
                      v153 = 1;
                      goto LABEL_118;
                    }
                    v153 = 0;
                  }
                  else
                  {
                    v153 = -1;
                  }
                  CreateDownlevelDegenerateMetadataObjects((struct _IRP_CONTEXT *)a1);
                  RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
LABEL_118:
                  InitializeDasdFile((struct _IRP_CONTEXT *)a1);
                  RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                  InitializeReparseIndexTable((struct _IRP_CONTEXT *)a1);
                  RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                  v50 = InitializeVerifyBlock((struct _IRP_CONTEXT *)a1, Irpa, (struct _VCB *)p_Flags);
                  Statusa = v50;
                  if ( v50 >= 0 )
                  {
                    RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                    LODWORD(v156) = v107 & 8;
                    if ( (v107 & 8) != 0 )
                    {
                      *(_DWORD *)v6 |= 0x100000u;
                      v6 = (__int64)&WPP_GLOBAL_Control;
LABEL_123:
                      MsStartVolumeAnalyzer(*p_RealDevice);
                      MsSetMinimumNewObjectId(*p_RealDevice);
                      RefsCleanupTransaction((struct _IRP_CONTEXT *)a1, 0, 0);
                      RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                      v19 = (*v110 & 0x2000000) == 0;
                      LODWORD(v158) = *v110 & 0x2000000;
                      v128 = !v19;
                      v129 = !v19;
                      if ( (_DWORD)v158 )
                        goto LABEL_132;
                      v109 = *(_DWORD *)&v159->Type;
                      v141 = v109;
                      SetVolumeMounted((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
                      LODWORD(v157) = v107 & 0x10;
                      if ( (v107 & 0x10) != 0 )
                      {
                        LOBYTE(Data) = 0;
                        RefsSetClearVolumeFlag(a1, p_Flags, 16);
                      }
                      LODWORD(TargetDevice) = v109 & 2;
                      if ( (v109 & 2) == 0 )
                      {
                        v141 = v109 | 2;
                        LODWORD(v152) = *v110 & 0x80;
                        if ( (_DWORD)v152 )
                          v141 = v109 | 3;
                        v102 = 1;
                      }
                      if ( !v102
                        || (updated = _VCB::UpdateBootSector((struct _VCB *)p_Flags, (__int64)&v160, 0, 0),
                            Statusa = updated,
                            updated >= 0) )
                      {
LABEL_132:
                        if ( v97 )
                        {
                          RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                          RefsReleaseAllResources((struct _IRP_CONTEXT *)a1);
                          if ( RefsUseFlushVolumeParallel )
                            RefsFlushVolumeParallel(a1, p_Flags, 3);
                          else
                            RefsFlushVolumeOriginal(a1, p_Flags, 3);
                        }
                        else if ( *((_QWORD *)p_Flags + 5) )
                        {
                          LODWORD(v112) = 262145;
                          v57 = MsFlushVolume((unsigned int)*p_RealDevice, 262145, 0, 0, 0, 0);
                          Statusa = v57;
                          if ( v57 < 0 )
                          {
LABEL_290:
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v6
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                28,
                                WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                                (unsigned int)v57);
                              v57 = Statusa;
                            }
                            v132 = (char)RefsStatusDebugEnabled;
                            v133 = (char)RefsStatusDebugEnabled;
                            if ( (_BYTE)RefsStatusDebugEnabled )
                              RefsStatusDebug(v57, (struct _IRP_CONTEXT *)a1, "mount.c", 0x4F4u);
                            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Statusa, v58);
                            goto LABEL_297;
                          }
                        }
                        v55 = MsReserveLogSpace(*p_RealDevice);
                        Statusa = v55;
                        if ( v55 >= 0 )
                        {
                          v59 = v110;
                          v60 = v110;
                          *v110 |= 0x4000u;
                          LODWORD(p_RealDevice) = *v60 & 0x100000;
                          if ( (_DWORD)p_RealDevice )
                            RefsPostSpecial(
                              (struct _IRP_CONTEXT *)a1,
                              (struct _VCB *)p_Flags,
                              (void (*)(struct _IRP_CONTEXT *, void *))RefsDeleteUsnSpecial,
                              p_Flags + 298,
                              1u,
                              0);
                          v61 = (struct _FILE_OBJECT *)*((_QWORD *)p_Flags + 12);
                          *v189 = v61;
                          ObfReferenceObject(v61);
                          MasterIrp = Irpa->AssociatedIrp.MasterIrp;
                          if ( MasterIrp && v155->Parameters.Read.ByteOffset.LowPart >= 0x2C )
                          {
                            *(_OWORD *)&MasterIrp->Type = 0;
                            *(_OWORD *)&MasterIrp->Flags = 0;
                            *(_OWORD *)((char *)&MasterIrp->AssociatedIrp.SystemBuffer + 4) = 0;
                            *(_DWORD *)(&MasterIrp->Size + 1) = 25343;
                            RefsQueryPersistentVolumeStateFlags(p_Flags, v107, 25343, &MasterIrp->MdlAddress);
                            *(_OWORD *)((char *)&MasterIrp->MdlAddress + 4) = *((_OWORD *)p_Flags + 378);
                            *(_OWORD *)((char *)&MasterIrp->AssociatedIrp.SystemBuffer + 4) = *(_OWORD *)(p_Flags + 3274);
                            Irpa->IoStatus.Information = 44;
                          }
                          BootSectorForMount = 0;
                          Status = 0;
                          v98 = 0;
                          *v59 |= 0x10000000u;
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                          {
                            Data = (PPCW_DATA)*((_QWORD *)p_Flags + 1337);
                            WPP_SF_ii(
                              WPP_GLOBAL_Control->AttachedDevice,
                              30,
                              WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                              *((_QWORD *)p_Flags + 1336));
                          }
                          v63 = qword_1402680E0;
                          v64 = *(_BYTE *)(qword_1402680E0 + 76);
                          StackSize = v150->StackSize;
                          if ( StackSize > v64 )
                          {
                            v66 = StackSize - v64;
                            while ( v63 )
                            {
                              *(_BYTE *)(v63 + 76) += v66;
                              v63 = *(_QWORD *)(v63 + 24);
                            }
                          }
                          RefsInitializePerfCountersTelemetry(p_Flags);
                          goto LABEL_156;
                        }
LABEL_283:
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v6
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        {
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            29,
                            WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                            (unsigned int)v55);
                          v55 = Statusa;
                        }
                        v134 = (char)RefsStatusDebugEnabled;
                        v135 = (char)RefsStatusDebugEnabled;
                        if ( (_BYTE)RefsStatusDebugEnabled )
                          RefsStatusDebug(v55, (struct _IRP_CONTEXT *)a1, "mount.c", 0x500u);
                        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Statusa, v56);
                        goto LABEL_290;
                      }
LABEL_276:
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v6
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          27,
                          WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                          (unsigned int)updated);
                        updated = Statusa;
                      }
                      v130 = (char)RefsStatusDebugEnabled;
                      v131 = (char)RefsStatusDebugEnabled;
                      if ( (_BYTE)RefsStatusDebugEnabled )
                        RefsStatusDebug(updated, (struct _IRP_CONTEXT *)a1, "mount.c", 0x4C7u);
                      RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Statusa, v54);
                      goto LABEL_283;
                    }
                    RefsBindMinstoreTransaction((struct _IRP_CONTEXT *)a1);
                    v193 = *((_QWORD *)p_Flags + 13);
                    v51 = MsUpdateTree(*v164, v193, 1, 0, 0);
                    v6 = (unsigned int)v51;
                    Statusa = v51;
                    if ( v51 >= 0 )
                    {
                      RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                      RefsOpenUsnJournal(
                        (struct _IRP_CONTEXT *)a1,
                        (struct _VCB *)p_Flags,
                        0,
                        1u,
                        (struct CREATE_USN_JOURNAL_DATA *)(p_Flags + 222),
                        0);
                      RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                      v6 = (__int64)&WPP_GLOBAL_Control;
                      goto LABEL_123;
                    }
LABEL_269:
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        26,
                        WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                        (unsigned int)v6);
                    }
                    v126 = (char)RefsStatusDebugEnabled;
                    v127 = (char)RefsStatusDebugEnabled;
                    if ( (_BYTE)RefsStatusDebugEnabled )
                      RefsStatusDebug(v6, (struct _IRP_CONTEXT *)a1, "mount.c", 0x45Au);
                    RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v6, v52);
                    goto LABEL_276;
                  }
LABEL_262:
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      25,
                      WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                      (unsigned int)v50);
                    v50 = Statusa;
                  }
                  v124 = (char)RefsStatusDebugEnabled;
                  v125 = (char)RefsStatusDebugEnabled;
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(v50, (struct _IRP_CONTEXT *)a1, "mount.c", 0x438u);
                  RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Statusa, v49);
                  goto LABEL_269;
                }
LABEL_255:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    24,
                    WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                    (unsigned int)v24);
                }
                v122 = (char)RefsStatusDebugEnabled;
                v123 = (char)RefsStatusDebugEnabled;
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(v24, (struct _IRP_CONTEXT *)a1, "mount.c", 0x40Bu);
                RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v24, v47);
                goto LABEL_262;
              }
              v194 = 0;
              v195 = 0;
              if ( (int)RefsDeviceIoControl(
                          (struct _IRP_CONTEXT *)a1,
                          *((PDEVICE_OBJECT *)a1[8] + 24),
                          0x2D1080u,
                          0,
                          0,
                          0,
                          &v194,
                          0xCu,
                          0) < 0 )
              {
                v194 = 0;
                v195 = 0;
              }
              v39 = *((_QWORD *)p_Flags + 756) - *(_QWORD *)&`IsGuidZero'::`2'::ZeroGuid.Data1;
              if ( !v39 )
                v39 = *((_QWORD *)p_Flags + 757) - *(_QWORD *)`IsGuidZero'::`2'::ZeroGuid.Data4;
              v169 = v39 == 0;
              v119 = v39 == 0;
              if ( v39 )
              {
                *(_OWORD *)(p_Flags + 1647) = *((_OWORD *)p_Flags + 378);
                goto LABEL_104;
              }
              if ( (_DWORD)v194 )
              {
                *(_OWORD *)(p_Flags + 1647) = 0;
                p_Flags[1647] = HIDWORD(v194);
                p_Flags[1648] = v195;
LABEL_104:
                if ( (unsigned __int8)MsIsDedupEnabled(*(_QWORD *)v6) )
                {
                  v40 = IoGetActivityIdThread();
                  v182 = *(_DWORD *)&v112->Type & 0x100;
                  v41 = v182;
                  VolumeUniqueGuid = MsGetVolumeUniqueGuid(*p_RealDevice);
                  LOBYTE(v43) = v41 != 0;
                  Data = (PPCW_DATA)v40;
                  if ( (int)FsRtlDedupChangeInit(p_Flags + 1643, p_Flags + 1647, VolumeUniqueGuid, v43) >= 0 )
                  {
                    v44 = v112;
                    *(_DWORD *)&v112->Type |= 0x80u;
                    if ( (unsigned __int8)MsIsDirtyStateTrackingEnabled(*p_RealDevice) )
                      *(_DWORD *)&v44->Type |= 0x400u;
                  }
                }
                goto LABEL_108;
              }
LABEL_248:
              Statusa = -1073741823;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v24
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  23,
                  WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                  3221225473LL);
              }
              v120 = (char)RefsStatusDebugEnabled;
              v121 = (char)RefsStatusDebugEnabled;
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741823, (struct _IRP_CONTEXT *)a1, "mount.c", 0x39Bu);
              RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741823, v38);
              goto LABEL_255;
            }
LABEL_241:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v24
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                21,
                WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
                (unsigned int)v32);
              v32 = Status;
            }
            v115 = (char)RefsStatusDebugEnabled;
            v116 = (char)RefsStatusDebugEnabled;
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(v32, (struct _IRP_CONTEXT *)a1, "mount.c", 0x30Cu);
            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Status, v31);
            goto LABEL_248;
          }
LABEL_234:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              19,
              WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
              (unsigned int)v24);
          }
          v113 = (char)RefsStatusDebugEnabled;
          v114 = (char)RefsStatusDebugEnabled;
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v24, (struct _IRP_CONTEXT *)a1, "mount.c", 0x2C9u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v24, v30);
          goto LABEL_241;
        }
LABEL_227:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids,
            (unsigned int)v24);
        }
        v145 = (char)RefsStatusDebugEnabled;
        v147 = (char)RefsStatusDebugEnabled;
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v24, (struct _IRP_CONTEXT *)a1, "mount.c", 0x2BCu);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v24, v28);
        goto LABEL_234;
      }
    }
LABEL_156:
    if ( v150 )
    {
      p_Flags = &v150[1].Flags;
      v67 = *(_QWORD *)&v150[1].Queue.Wcb.NumberOfMapRegisters;
      if ( v67 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v67 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 9) + 136LL));
      v68 = *((_QWORD *)p_Flags + 4);
      if ( v68 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v68 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 4) + 136LL));
      v69 = *((_QWORD *)p_Flags + 8);
      if ( v69 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v69 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 8) + 136LL));
      v70 = *((_QWORD *)p_Flags + 5);
      if ( v70 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v70 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 5) + 136LL));
      v71 = *((_QWORD *)p_Flags + 6);
      if ( v71 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v71 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 6) + 136LL));
      v72 = *((_QWORD *)p_Flags + 11);
      if ( v72 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v72 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 11) + 136LL));
      v73 = *((_QWORD *)p_Flags + 10);
      if ( v73 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v73 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 10) + 136LL));
      v74 = v98;
      if ( v98 )
      {
        v154 = 0;
        if ( v103 )
        {
          if ( RefsInstrumentThrottle(v16, 0x206u) )
            RefsEtwWriteVolumeFailureEvent(
              (struct _VCB *)p_Flags,
              &REFS_ETW_VOLUME_MOUNT_FAILURE,
              *((_DWORD *)a1[13] + 4),
              0);
          if ( RefsInstrumentThrottle(v75, 0x409u) )
            RefsTelemetryMountVolumeStatusFailure(
              (struct _VCB *)p_Flags,
              BootSectorForMount,
              MEMORY[0xFFFFF78000000320] - v14,
              *(_DWORD *)(*((_QWORD *)p_Flags + 1639) + 44LL),
              v100);
        }
        if ( RefsIsTriagePending((struct _IRP_CONTEXT *)a1) )
          RefsDiscardTriageInfo((struct _IRP_CONTEXT *)a1);
        RefsAbortTransaction((struct _IRP_CONTEXT *)a1);
        RefsCleanupFailedTransaction((struct _IRP_CONTEXT *)a1, 0);
        RefsReleaseAllResources((struct _IRP_CONTEXT *)a1);
        p_Flags[6] &= ~1u;
        v76 = *((_DWORD *)a1 + 4);
        RefsPurgeVolumeCatchExceptions(a1, p_Flags);
        *((_DWORD *)a1 + 4) = v76;
        LODWORD(Data) = 6;
        LOBYTE(v77) = 1;
        LOBYTE(v78) = 1;
        RefsPerformDismountOnVcb(a1, p_Flags, v78, v77, Data, &v154);
        v79 = *((_DWORD *)a1[13] + 4);
        if ( v79 == -1073741432 || v79 == -1073741400 || v79 == -1073741608 )
        {
          BootSectorForMount = Status;
          if ( v154 )
            v155->Parameters.WMI.ProviderId = v154;
        }
        else
        {
          BootSectorForMount = Status;
        }
      }
    }
    else
    {
      v74 = v98;
    }
    if ( v104 )
      RefsReleaseVcbCheckDelete((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
    if ( v150 && v74 )
      a1[8] = 0;
    RefsForEachVcb((struct _IRP_CONTEXT *)a1, FilterVcbForDeletion, CheckVcbForDeletion, 0, 0);
    if ( !v74 )
    {
      *((_QWORD *)p_Flags + 765) = MEMORY[0xFFFFF78000000014];
      IoRegisterPlugPlayNotification(
        EventCategoryTargetDeviceChange,
        0,
        *((PVOID *)p_Flags + 12),
        DriverObject,
        RefsPnpCallbackRoutine,
        p_Flags,
        (PVOID *)p_Flags + 784);
      if ( (v107 & 0x20) != 0 )
        p_Flags[6] |= 0x200u;
      else
        p_Flags[6] &= ~0x200u;
      RefsPostSqmVolumeInfo((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
      RefsPostTelemetryVolumeInfo(
        (struct _IRP_CONTEXT *)a1,
        (struct _VCB *)p_Flags,
        MEMORY[0xFFFFF78000000320] - v14,
        *(_DWORD *)(*((_QWORD *)p_Flags + 1639) + 44LL),
        v100);
      if ( !_InterlockedCompareExchange(&dword_1402682DC, 1, 0) )
        KeSetCoalescableTimer(&stru_140268278, RefsPeriodicTimerInterval, 0, 0x3A98u, &stru_140268238);
      LOBYTE(v80) = 1;
      ExAcquireFastResourceExclusive(qword_1402680F8, 0, v80);
      a1[8] = (struct CmsTransactionContext *)p_Flags;
      if ( ((unsigned __int16)dword_1402682EC & 0x1000) != 0 )
      {
        ExReleaseFastResource(qword_1402680F8, 0);
        RefsShutdownVolume((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags, 0);
        LOBYTE(v81) = 1;
        ExAcquireFastResourceExclusive(qword_1402680F8, 0, v81);
      }
      v82 = (_QWORD *)qword_1402680F0;
      if ( *(__int64 **)qword_1402680F0 != &qword_1402680E8 )
        __fastfail(3u);
      *((_QWORD *)p_Flags + 1) = &qword_1402680E8;
      *((_QWORD *)p_Flags + 2) = v82;
      *v82 = p_Flags + 2;
      qword_1402680F0 = (__int64)(p_Flags + 2);
      ExReleaseFastResource(qword_1402680F8, 0);
      if ( v190 )
        *v190 = (struct _VCB *)p_Flags;
    }
    RefsCompleteRequest((struct _IRP_CONTEXT *)a1, Irpa, BootSectorForMount);
    if ( BootSectorForMount >= 0 )
      ObfDereferenceObject(*((PVOID *)p_Flags + 24));
    return (unsigned int)BootSectorForMount;
  }
  BootSectorForMount = -1073741489;
  RefsCompleteRequest((struct _IRP_CONTEXT *)a1, v4, -1073741489);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids, 3221225807LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v11 = 386;
    goto LABEL_218;
  }
  return (unsigned int)BootSectorForMount;
}

```

## disassembly

```asm
0x140324914  mov     r11, rsp
0x140324917  push    rbx
0x140324918  push    rsi
0x140324919  push    rdi
0x14032491a  push    r12
0x14032491c  push    r13
0x14032491e  push    r14
0x140324920  push    r15
0x140324922  sub     rsp, 240h
0x140324929  mov     rax, cs:__security_cookie
0x140324930  xor     rax, rsp
0x140324933  mov     [rsp+278h+var_40], rax
0x14032493b  mov     r10, rdx
0x14032493e  mov     [rsp+278h+Irp], rdx
0x140324946  mov     r13, rcx
0x140324949  mov     [rsp+278h+var_180], rcx
0x140324951  mov     [rsp+278h+var_128], rdx
0x140324959  mov     [rsp+278h+var_78], r8
0x140324961  mov     [rsp+278h+var_80], r9
0x140324969  mov     [rsp+278h+Status], 0C0000001h
0x140324974  xor     r15d, r15d
0x140324977  mov     [r11-160h], r15
0x14032497e  mov     [r11-168h], r15
0x140324985  mov     [r11-1DDh], r15b
0x14032498c  mov     [rsp+278h+var_1E3], 1
0x140324994  mov     [r11-1DEh], r15b
0x14032499b  mov     [r11-1E0h], r15b
0x1403249a2  mov     [r11-1D8h], r15b
0x1403249a9  mov     [r11-1D4h], r15d
0x1403249b0  mov     esi, r15d
0x1403249b3  mov     [r11-1DCh], r15d
0x1403249ba  mov     [r11-110h], r15
0x1403249c1  mov     [r11-1DFh], r15b
0x1403249c8  mov     [r11-1C0h], r15
0x1403249cf  mov     [r11-170h], r15
0x1403249d6  mov     [r11-138h], r15
0x1403249dd  mov     [r11-1E1h], r15b
0x1403249e4  lea     r12, WPP_GLOBAL_Control
0x1403249eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1403249f2  cmp     rcx, r12
0x1403249f5  jz      short loc_140324A20
0x1403249f7  mov     eax, [rcx+2Ch]
0x1403249fa  test    al, 2
0x1403249fc  jz      short loc_140324A20
0x1403249fe  cmp     byte ptr [rcx+29h], 2
0x140324a02  jb      short loc_140324A20
0x140324a04  lea     edx, [r15+0Ah]
0x140324a08  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x140324a0f  mov     rcx, [rcx+18h]
0x140324a13  call    WPP_SF_
0x140324a18  mov     r10, [rsp+278h+Irp]
0x140324a20  mov     ecx, cs:dword_14026DDE8
0x140324a26  test    ecx, ecx
0x140324a28  jnz     short loc_140324A40
0x140324a2a  mov     rax, cs:KdDebuggerEnabled
0x140324a31  cmp     [rax], r15b
0x140324a34  jz      short loc_140324A40
0x140324a36  cmp     cs:dword_14026DDEC, r15d
0x140324a3d  jz      short loc_140324A40
0x140324a3f  int     3; Trap to Debugger
0x140324a40  cmp     cs:dword_14026DDF0, r15d
0x140324a47  jnz     loc_140326391
0x140324a4d  test    ecx, ecx
0x140324a4f  jnz     loc_140326391
0x140324a55  mov     rcx, [r10+0B8h]
0x140324a5c  mov     r11, [rcx+8]
0x140324a60  mov     [rsp+278h+var_150], r11
0x140324a68  lea     rdx, [r11+10h]
0x140324a6c  mov     [rsp+278h+var_1D0], rdx
0x140324a74  mov     r8, [rdx]
0x140324a77  mov     eax, [r8+34h]
0x140324a7b  test    al, 5
0x140324a7d  jz      short loc_140324AE0
0x140324a7f  mov     [r10+38h], r15
0x140324a83  mov     ebx, 0C000014Fh
0x140324a88  mov     r8d, ebx; Status
0x140324a8b  mov     rdx, r10; Irp
0x140324a8e  mov     rcx, r13; struct _IRP_CONTEXT *
0x140324a91  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140324a96  mov     rcx, cs:WPP_GLOBAL_Control
0x140324a9d  cmp     rcx, r12
0x140324aa0  jz      short loc_140324AC7
0x140324aa2  bt      dword ptr [rcx+2Ch], 8
0x140324aa7  jnb     short loc_140324AC7
0x140324aa9  cmp     byte ptr [rcx+29h], 4
0x140324aad  jb      short loc_140324AC7
0x140324aaf  mov     edx, 0Ch
0x140324ab4  mov     r9d, ebx
0x140324ab7  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x140324abe  mov     rcx, [rcx+18h]
0x140324ac2  call    WPP_SF_d
0x140324ac7  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140324acd  test    al, al
0x140324acf  jz      loc_1403263F5
0x140324ad5  mov     r9d, 17Ah
0x140324adb  jmp     loc_1403263E5
0x140324ae0  mov     r9, [rcx+10h]
0x140324ae4  mov     [rsp+278h+TargetDevice], r9
0x140324aec  and     dword ptr [r8+30h], 0FFFFFFFDh
0x140324af1  mov     rax, cs:qword_14026DDF8
0x140324af8  cmp     rax, [rcx+10h]
0x140324afc  jnz     short loc_140324B5B
0x140324afe  mov     ebx, 0C000014Fh
0x140324b03  mov     r8d, ebx; Status
0x140324b06  mov     rdx, r10; Irp
0x140324b09  mov     rcx, r13; struct _IRP_CONTEXT *
0x140324b0c  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140324b11  mov     rcx, cs:WPP_GLOBAL_Control
0x140324b18  cmp     rcx, r12
0x140324b1b  jz      short loc_140324B42
0x140324b1d  bt      dword ptr [rcx+2Ch], 8
0x140324b22  jnb     short loc_140324B42
0x140324b24  cmp     byte ptr [rcx+29h], 4
0x140324b28  jb      short loc_140324B42
0x140324b2a  mov     edx, 0Dh
0x140324b2f  mov     r9d, ebx
0x140324b32  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x140324b39  mov     rcx, [rcx+18h]
0x140324b3d  call    WPP_SF_d
0x140324b42  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140324b48  test    al, al
0x140324b4a  jz      loc_1403263F5
0x140324b50  mov     r9d, 182h
0x140324b56  jmp     loc_1403263E5
0x140324b5b  mov     [rsp+278h+var_138], rcx
0x140324b63  mov     [rsp+278h+var_1B0], r11
0x140324b6b  mov     [rsp+278h+var_130], rdx
0x140324b73  mov     eax, cs:dword_1402682EC
0x140324b79  bt      eax, 0Ch
0x140324b7d  jnb     short loc_140324BDC
0x140324b7f  mov     ebx, 0C00002EBh
0x140324b84  mov     r8d, ebx; Status
0x140324b87  mov     rdx, r10; Irp
0x140324b8a  mov     rcx, r13; struct _IRP_CONTEXT *
0x140324b8d  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140324b92  mov     rcx, cs:WPP_GLOBAL_Control
0x140324b99  cmp     rcx, r12
0x140324b9c  jz      short loc_140324BC3
0x140324b9e  bt      dword ptr [rcx+2Ch], 8
0x140324ba3  jnb     short loc_140324BC3
0x140324ba5  cmp     byte ptr [rcx+29h], 4
0x140324ba9  jb      short loc_140324BC3
0x140324bab  mov     edx, 0Eh
0x140324bb0  mov     r9d, ebx
0x140324bb3  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x140324bba  mov     rcx, [rcx+18h]
0x140324bbe  call    WPP_SF_d
0x140324bc3  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140324bc9  test    cl, cl
0x140324bcb  jz      loc_1403263F5
0x140324bd1  mov     r9d, 18Eh
0x140324bd7  jmp     loc_1403263E5
0x140324bdc  mov     [rsp+278h+var_120], r9
0x140324be4  mov     r14, r15
0x140324be7  mov     [rsp+278h+var_168], r15
0x140324bef  mov     r12, 0FFFFF78000000320h
0x140324bf9  mov     rdi, [r12]
0x140324bfd  mov     [rsp+278h+var_170], rdi
0x140324c05  mov     rbx, 0FFFFF78000000014h
0x140324c0f  mov     rbx, [rbx]
0x140324c12  mov     [rsp+278h+var_1C0], rbx
0x140324c1a  lea     rax, [rsp+278h+var_160]
0x140324c22  mov     [rsp+278h+Data], rax; PDEVICE_OBJECT *
0x140324c27  lea     r9, [rsp+278h+var_1DD]
0x140324c2f  mov     r8, [rsp+278h+TargetDevice]; Object
0x140324c37  mov     rdx, r11; struct _VPB *
0x140324c3a  mov     rcx, r13; struct _IRP_CONTEXT *
0x140324c3d  call    InitializeDevice
0x140324c42  mov     [rsp+278h+Status], eax
0x140324c49  jmp     loc_140324D50
0x140324c4e  lea     rax, WPP_GLOBAL_Control
0x140324c55  mov     rcx, cs:WPP_GLOBAL_Control
0x140324c5c  cmp     rcx, rax
0x140324c5f  jz      short loc_140324C8B
0x140324c61  test    dword ptr [rcx+2Ch], 100h
0x140324c68  jz      short loc_140324C8B
0x140324c6a  cmp     byte ptr [rcx+29h], 4
0x140324c6e  jb      short loc_140324C8B
0x140324c70  mov     edx, 0Fh
0x140324c75  mov     r9d, 0C000014Fh
0x140324c7b  lea     r8, WPP_e74db425dd72352f352fea48a9d9a40b_Traceguids
0x140324c82  mov     rcx, [rcx+18h]
0x140324c86  call    WPP_SF_d
0x140324c8b  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140324c91  mov     [rsp+278h+var_1E2], al
0x140324c98  mov     [rsp+278h+var_1E4], al
0x140324c9f  test    al, al
0x140324ca1  jz      short loc_140324CBC
0x140324ca3  mov     r9d, 1AAh; unsigned int
0x140324ca9  lea     r8, aMountC; "mount.c"
0x140324cb0  xor     edx, edx; struct _IRP_CONTEXT *
0x140324cb2  mov     ecx, 0C000014Fh; Status
0x140324cb7  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140324cbc  mov     eax, 0C000014Fh
0x140324cc1  mov     [rsp+278h+Status], eax
0x140324cc8  mov     r13, [rsp+278h+var_180]
0x140324cd0  test    r13, r13
0x140324cd3  jz      short loc_140324CEE
0x140324cd5  mov     dword ptr [rsp+278h+var_118], 0FFFFFEFFh
0x140324ce0  btr     dword ptr [r13+4], 8
0x140324ce6  mov     dword ptr [r13+10h], 0
0x140324cee  xor     r15d, r15d
0x140324cf1  mov     rcx, [rsp+278h+var_120]
0x140324cf9  mov     [rsp+278h+TargetDevice], rcx
0x140324d01  mov     rcx, [rsp+278h+var_1B0]
0x140324d09  mov     [rsp+278h+var_150], rcx
0x140324d11  mov     r14, [rsp+278h+var_168]
0x140324d19  mov     esi, [rsp+278h+var_1DC]
0x140324d20  mov     rbx, [rsp+278h+var_1C0]
0x140324d28  mov     rdi, [rsp+278h+var_170]
0x140324d30  mov     rcx, [rsp+278h+var_130]
0x140324d38  mov     [rsp+278h+var_1D0], rcx
0x140324d40  mov     rcx, [rsp+278h+var_128]
0x140324d48  mov     [rsp+278h+Irp], rcx
0x140324d50  test    eax, eax
0x140324d52  js      loc_140325E82
0x140324d58  mov     r14, [r13+40h]
0x140324d5c  mov     [rsp+278h+var_168], r14
0x140324d64  mov     eax, dword ptr [rsp+278h+var_1C0+4]
0x140324d6b  mov     [r14+1A34h], eax
0x140324d72  mov     eax, dword ptr [rsp+278h+var_1C0]
0x140324d79  mov     [r14+1A30h], eax
0x140324d80  mov     [r14+1A50h], rbx
0x140324d87  mov     [r14+1A58h], rbx
0x140324d8e  mov     [r14+26E8h], rdi
0x140324d95  mov     [r14+26F0h], rdi
0x140324d9c  mov     [r14+26F8h], rdi
0x140324da3  mov     [r14+1AF0h], rdi
0x140324daa  mov     [r14+1AF8h], rdi
0x140324db1  mov     [r14+1A60h], r15
0x140324db8  mov     [r14+1AE0h], r15
0x140324dbf  mov     [r14+1C50h], r15
0x140324dc6  mov     [r14+1A98h], r15
0x140324dcd  mov     [r14+1DB0h], r15
0x140324dd4  xor     r9d, r9d; struct _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR **
0x140324dd7  xor     r8d, r8d; unsigned int *
0x140324dda  mov     rdx, r14; struct _VCB *
0x140324ddd  mov     rcx, r13; struct _IRP_CONTEXT *
0x140324de0  call    ?RefsQueryNumberDataCopies@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAKPEAPEAU_STORAGE_DEVICE_RESILIENCY_DESCRIPTOR@@@Z; RefsQueryNumberDataCopies(_IRP_CONTEXT *,_VCB *,ulong *,_STORAGE_DEVICE_RESILIENCY_DESCRIPTOR * *)
0x140324de5  mov     dword ptr [r14+1ACh], 0FFFFFFFFh
0x140324df0  xor     r9d, r9d; struct _DISK_CACHE_INFORMATION **
0x140324df3  xor     r8d, r8d; unsigned __int8 *
0x140324df6  mov     rdx, r14; struct _VCB *
0x140324df9  mov     rcx, r13; struct _IRP_CONTEXT *
0x140324dfc  call    ?RefsQueryPowerProtectedMode@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAEPEAPEAU_DISK_CACHE_INFORMATION@@@Z; RefsQueryPowerProtectedMode(_IRP_CONTEXT *,_VCB *,uchar *,_DISK_CACHE_INFORMATION * *)
0x140324e01  mov     rdx, r13; struct _IRP_CONTEXT *
0x140324e04  mov     rcx, r14; this
0x140324e07  call    ?ReadBootSectorForMount@_VCB@@QEAAJAEBU_IRP_CONTEXT@@@Z; _VCB::ReadBootSectorForMount(_IRP_CONTEXT const &)
0x140324e0c  mov     ebx, eax
0x140324e0e  mov     [rsp+278h+Status], eax
0x140324e15  test    eax, eax
0x140324e17  js      loc_140325E89
0x140324e1d  mov     rdx, [r14+3338h]
0x140324e24  mov     [rsp+278h+var_130], rdx
0x140324e2c  lea     rax, [rdx+2Ch]
0x140324e30  mov     [rsp+278h+var_118], rax
0x140324e38  mov     eax, [rax]
0x140324e3a  mov     r12d, 100h
0x140324e40  and     eax, r12d
0x140324e43  mov     [rsp+278h+var_D0], eax
0x140324e4a  jz      short loc_140324E52
0x140324e4c  bts     dword ptr [r14+18h], 19h
0x140324e52  mov     al, [rdx+28h]
0x140324e55  mov     [rsp+278h+var_1E2], al
0x140324e5c  cmp     al, 3
0x140324e5e  jnz     loc_14032693B
0x140324e64  cmp     byte ptr [rdx+29h], 0Fh
0x140324e68  ja      loc_14032693B
0x140324e6e  mov     rax, [rdx+40h]
0x140324e72  mov     [rsp+278h+var_110], rax
0x140324e7a  test    rax, rax
0x140324e7d  jnz     short loc_140324EB7
0x140324e7f  mov     [rsp+278h+var_110], 4000000h
0x140324e8b  mov     ecx, [r14+18h]
0x140324e8f  and     ecx, 2000000h
0x140324e95  mov     [rsp+278h+var_C4], ecx
0x140324e9c  setnz   al
0x140324e9f  mov     [rsp+278h+var_18D], al
0x140324ea6  mov     [rsp+278h+var_18C], al
0x140324ead  test    ecx, ecx
0x140324eaf  setz    [rsp+278h+var_1DF]
0x140324eb7  mov     r8, rdx
0x140324eba  mov     rdx, [rsp+278h+var_150]
0x140324ec2  mov     rcx, r14
0x140324ec5  call    InitializeVcbFromBootSector
0x140324eca  mov     r8, [rsp+278h+var_1D0]
0x140324ed2  mov     r8, [r8]
0x140324ed5  test    [r8+30h], r12d
0x140324ed9  jz      short loc_140324EF8
0x140324edb  inc     dword ptr [r14+0E8h]
0x140324ee2  bts     dword ptr [r14+1Ch], 0Ch
0x140324ee8  mov     eax, cs:dword_1402682EC
0x140324eee  bts     eax, 14h
0x140324ef2  mov     cs:dword_1402682EC, eax
0x140324ef8  mov     r8b, 1; unsigned __int8
0x140324efb  mov     rdx, r14; struct _VCB *
0x140324efe  mov     rcx, r13; struct _IRP_CONTEXT *
0x140324f01  call    ?RefsFillVcbVolumeName@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsFillVcbVolumeName(_IRP_CONTEXT *,_VCB *,uchar)
0x140324f06  mov     rcx, r14; struct _VCB *
0x140324f09  call    ?MsKmeInitializeReservedIoRequestsForVcb@@YAJPEAU_VCB@@@Z; MsKmeInitializeReservedIoRequestsForVcb(_VCB *)
  ... truncated ...
```
