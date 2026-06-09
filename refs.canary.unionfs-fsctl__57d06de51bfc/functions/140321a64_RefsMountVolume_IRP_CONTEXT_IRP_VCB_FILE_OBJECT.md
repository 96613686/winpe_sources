# RefsMountVolume(_IRP_CONTEXT *,_IRP *,_VCB * *,_FILE_OBJECT * *)

- ea: `0x140321a64`
- end: `0x140323be0`
- name: `?RefsMountVolume@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAPEAU_VCB@@PEAPEAU_FILE_OBJECT@@@Z`
- size: `8572`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp, struct _VCB **, struct _FILE_OBJECT **)`
- caller_count: `2`
- callee_count: `84`
- tags: `reparse_path, installer_update, broker_com_uri`

## callers

- `0x1403209e0`
- `0x140320d80`

## callees

- `0x14000bcc0`
- `0x14000cd70`
- `0x140013934`
- `0x14003d4cc`
- `0x140040410`
- `0x140041b40`
- `0x1400815e0`
- `0x140081670`
- `0x14008dbd0`
- `0x14009f140`
- `0x1400a3da0`
- `0x1400ae270`
- `0x1400ae940`
- `0x1400afa08`
- `0x1400afb00`
- `0x1400b1dfc`
- `0x1400b2a90`
- `0x1400b2d58`
- `0x1400c6144`
- `0x1400c6218`
- `0x1400c8bf0`
- `0x1400c9484`
- `0x1400ca788`
- `0x1400cd404`
- `0x1400cdb34`
- `0x1400cdbd0`
- `0x1400ce17c`
- `0x1400ce53c`
- `0x1400ce63c`
- `0x1400ce658`
- `0x1400e1534`
- `0x1400e32e4`
- `0x1400e6e2c`
- `0x1400eec34`
- `0x1400f3760`
- `0x1400f37a0`
- `0x1400f38b4`
- `0x1400f3a34`
- `0x1400fe130`
- `0x140113370`
- `0x1401143a4`
- `0x140114458`
- `0x1401145c0`
- `0x140114624`
- `0x1401e9ce0`
- `0x1402862c8`
- `0x1402865a4`
- `0x1402866e0`
- `0x1402870ec`
- `0x140287578`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140323578`
- `ntoskrnl!ObfDereferenceObject` at `0x140323578`
- `ntoskrnl!IoGetActivityIdThread` at `0x140322952`
- `ntoskrnl!IoGetActivityIdThread` at `0x1403229d4`
- `ntoskrnl!IoGetActivityIdThread` at `0x140323b3d`
- `ntoskrnl!IoGetActivityIdThread` at `0x140322952`
- `ntoskrnl!IoGetActivityIdThread` at `0x1403229d4`
- `ntoskrnl!IoGetActivityIdThread` at `0x140323b3d`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403234bb`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403234fe`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403234bb`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1403234fe`
- `ntoskrnl!KdDebuggerEnabled` at `0x140321b7a`
- `ntoskrnl!FsRtlDedupChangeInit` at `0x140322a1b`
- `ntoskrnl!FsRtlDedupChangeInit` at `0x140322a1b`
- `ntoskrnl!ObfReferenceObject` at `0x140322f68`
- `ntoskrnl!ObfReferenceObject` at `0x140322f68`
- `ntoskrnl!PcwCreateInstance` at `0x140322515`
- `ntoskrnl!PcwCreateInstance` at `0x140322515`
- `ntoskrnl!FsRtlBalanceReads` at `0x140322a74`
- `ntoskrnl!FsRtlBalanceReads` at `0x140322a74`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1403230ae`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1403230e9`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140323124`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14032315f`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14032319a`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1403231d5`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140323210`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340be7`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340c35`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340c73`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340cb1`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340cef`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340d2d`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340d6b`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1403230ae`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1403230e9`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140323124`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14032315f`
- `ntoskrnl!ExIsFastResourceHeld` at `0x14032319a`
- `ntoskrnl!ExIsFastResourceHeld` at `0x1403231d5`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140323210`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340be7`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340c35`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340c73`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340cb1`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340cef`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340d2d`
- `ntoskrnl!ExIsFastResourceHeld` at `0x140340d6b`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140323411`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x140323411`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1403234a0`
- `ntoskrnl!KeSetCoalescableTimer` at `0x1403234a0`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140340b3c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140340b6c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140340b3c`
- `ntoskrnl!FsRtlIsNtstatusExpected` at `0x140340b6c`
- `ntoskrnl!FsRtlHeatInit` at `0x14032296f`
- `ntoskrnl!FsRtlHeatInit` at `0x14032296f`
- `ntoskrnl!ExReleaseFastResource` at `0x1403234dc`
- `ntoskrnl!ExReleaseFastResource` at `0x14032353e`
- `ntoskrnl!ExReleaseFastResource` at `0x1403234dc`
- `ntoskrnl!ExReleaseFastResource` at `0x14032353e`

## string_xrefs

- `0x140321df9`: `mount.c`
- `0x1403227fe`: `mount.c`
- `0x1403235da`: `mount.c`
- `0x14032366a`: `mount.c`
- `0x1403236e2`: `mount.c`
- `0x140323754`: `mount.c`
- `0x1403237c7`: `mount.c`
- `0x140323846`: `mount.c`
- `0x1403238be`: `mount.c`
- `0x140323938`: `mount.c`
- `0x1403239b0`: `mount.c`
- `0x140323a24`: `mount.c`
- `0x140323a9b`: `mount.c`
- `0x140323b12`: `mount.c`
- `0x140323bc3`: `mount.c`

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
  ULONG v20; // edx
  ULONG v21; // r8d
  unsigned int v22; // edx
  unsigned __int64 v23; // rbx
  unsigned int v24; // r8d
  unsigned int v25; // ecx
  int v26; // eax
  unsigned int v27; // r8d
  int started; // eax
  unsigned int v29; // r8d
  unsigned int v30; // r8d
  NTSTATUS v31; // r10d
  __int16 v32; // cx
  struct _VPB *v33; // rax
  int v34; // ecx
  __int64 v35; // rcx
  __int64 v36; // r8
  unsigned int v37; // r8d
  __int64 v38; // rcx
  __int64 v39; // rax
  struct _VPB *v40; // rbx
  __int64 v41; // rsi
  int v42; // ebx
  __int64 VolumeUniqueGuid; // rax
  __int64 v44; // r9
  struct _VPB *v45; // rbx
  __int64 v46; // r9
  __int64 v47; // r8
  unsigned int v48; // r8d
  unsigned int v49; // ecx
  unsigned int v50; // r8d
  NTSTATUS v51; // r10d
  int v52; // eax
  unsigned int v53; // r8d
  NTSTATUS updated; // ecx
  unsigned int v55; // r8d
  NTSTATUS v56; // ecx
  unsigned int v57; // r8d
  NTSTATUS v58; // ecx
  unsigned int v59; // r8d
  _DWORD *v60; // r12
  _DWORD *v61; // roff
  struct _FILE_OBJECT *v62; // rcx
  struct _IRP *MasterIrp; // rbx
  __int64 v64; // rcx
  char v65; // r8
  CCHAR StackSize; // dl
  char v67; // dl
  __int64 v68; // rax
  __int64 v69; // rax
  __int64 v70; // rax
  __int64 v71; // rax
  __int64 v72; // rax
  __int64 v73; // rax
  __int64 v74; // rax
  char v75; // r12
  struct _UNICODE_STRING *v76; // rcx
  int v77; // ebx
  __int64 v78; // r9
  __int64 v79; // r8
  int v80; // ecx
  __int64 v81; // r8
  __int64 v82; // r8
  _QWORD *v83; // rdx
  char v85; // bl
  int ActivityIdThread; // eax
  int v87; // ecx
  int v88; // edx
  int v89; // r9d
  PPCW_DATA Data; // [rsp+B8h] [rbp-258h]
  int Context; // [rsp+C0h] [rbp-250h]
  ULONG v92; // [rsp+D0h] [rbp-240h]
  int v93; // [rsp+D8h] [rbp-238h]
  int v94; // [rsp+E0h] [rbp-230h]
  int v95; // [rsp+E8h] [rbp-228h]
  NTSTATUS Status; // [rsp+128h] [rbp-1E8h]
  NTSTATUS Statusa; // [rsp+128h] [rbp-1E8h]
  bool v98; // [rsp+12Ch] [rbp-1E4h]
  char v99; // [rsp+12Dh] [rbp-1E3h]
  char v100; // [rsp+12Eh] [rbp-1E2h]
  char v101; // [rsp+12Fh] [rbp-1E1h] BYREF
  bool v102; // [rsp+130h] [rbp-1E0h]
  bool v103; // [rsp+131h] [rbp-1DFh]
  char v104; // [rsp+132h] [rbp-1DEh]
  char v105; // [rsp+133h] [rbp-1DDh]
  int v106; // [rsp+134h] [rbp-1DCh]
  bool v107; // [rsp+138h] [rbp-1D8h]
  unsigned int v108; // [rsp+13Ch] [rbp-1D4h]
  struct _DEVICE_OBJECT **p_RealDevice; // [rsp+140h] [rbp-1D0h]
  int v110; // [rsp+148h] [rbp-1C8h]
  struct _VPB *v111; // [rsp+150h] [rbp-1C0h]
  _DWORD *v112; // [rsp+158h] [rbp-1B8h]
  PIRP Irpa; // [rsp+160h] [rbp-1B0h]
  char v114; // [rsp+168h] [rbp-1A8h]
  char v115; // [rsp+169h] [rbp-1A7h]
  char v116; // [rsp+16Ah] [rbp-1A6h]
  char v117; // [rsp+16Bh] [rbp-1A5h]
  bool v118; // [rsp+16Ch] [rbp-1A4h]
  bool v119; // [rsp+16Dh] [rbp-1A3h]
  bool v120; // [rsp+170h] [rbp-1A0h]
  char v121; // [rsp+171h] [rbp-19Fh]
  char v122; // [rsp+172h] [rbp-19Eh]
  char v123; // [rsp+173h] [rbp-19Dh]
  char v124; // [rsp+174h] [rbp-19Ch]
  char v125; // [rsp+175h] [rbp-19Bh]
  char v126; // [rsp+176h] [rbp-19Ah]
  char v127; // [rsp+177h] [rbp-199h]
  char v128; // [rsp+178h] [rbp-198h]
  bool v129; // [rsp+179h] [rbp-197h]
  bool v130; // [rsp+17Ah] [rbp-196h]
  char v131; // [rsp+17Bh] [rbp-195h]
  char v132; // [rsp+17Ch] [rbp-194h]
  char v133; // [rsp+17Dh] [rbp-193h]
  char v134; // [rsp+17Eh] [rbp-192h]
  char v135; // [rsp+17Fh] [rbp-191h]
  char v136; // [rsp+180h] [rbp-190h]
  char v137; // [rsp+181h] [rbp-18Fh]
  char v138; // [rsp+182h] [rbp-18Eh]
  bool v139; // [rsp+183h] [rbp-18Dh]
  bool v140; // [rsp+184h] [rbp-18Ch]
  bool v141; // [rsp+185h] [rbp-18Bh]
  int v142; // [rsp+188h] [rbp-188h]
  bool v143; // [rsp+18Ch] [rbp-184h]
  char v144; // [rsp+18Dh] [rbp-183h]
  char v145; // [rsp+18Eh] [rbp-182h]
  char v146; // [rsp+18Fh] [rbp-181h]
  struct _IRP_CONTEXT *v147; // [rsp+190h] [rbp-180h]
  char v148; // [rsp+198h] [rbp-178h]
  __int64 v149; // [rsp+1A0h] [rbp-170h]
  ULONG *v150; // [rsp+1A8h] [rbp-168h]
  PDEVICE_OBJECT v151; // [rsp+1B0h] [rbp-160h] BYREF
  PDEVICE_OBJECT TargetDevice; // [rsp+1B8h] [rbp-158h]
  struct _VPB *v153; // [rsp+1C0h] [rbp-150h]
  int v154; // [rsp+1C8h] [rbp-148h]
  ULONG_PTR v155; // [rsp+1D0h] [rbp-140h] BYREF
  struct _IO_STACK_LOCATION *v156; // [rsp+1D8h] [rbp-138h]
  struct _DEVICE_OBJECT **v157; // [rsp+1E0h] [rbp-130h]
  PIRP v158; // [rsp+1E8h] [rbp-128h]
  struct _DEVICE_OBJECT *v159; // [rsp+1F0h] [rbp-120h]
  struct _DEVICE_OBJECT *v160; // [rsp+1F8h] [rbp-118h]
  __int64 v161; // [rsp+200h] [rbp-110h] BYREF
  int v162; // [rsp+208h] [rbp-108h]
  unsigned __int8 *v163; // [rsp+210h] [rbp-100h]
  unsigned __int8 *v164; // [rsp+218h] [rbp-F8h]
  _QWORD *v165; // [rsp+220h] [rbp-F0h]
  int v166; // [rsp+228h] [rbp-E8h]
  int v167; // [rsp+22Ch] [rbp-E4h]
  int v168; // [rsp+230h] [rbp-E0h]
  BOOL v170; // [rsp+23Ch] [rbp-D4h]
  int v175; // [rsp+250h] [rbp-C0h]
  int v176; // [rsp+254h] [rbp-BCh]
  int v177; // [rsp+258h] [rbp-B8h]
  int v178; // [rsp+25Ch] [rbp-B4h]
  int v179; // [rsp+260h] [rbp-B0h]
  int v180; // [rsp+264h] [rbp-ACh]
  int v181; // [rsp+268h] [rbp-A8h]
  int v182; // [rsp+26Ch] [rbp-A4h]
  int v184; // [rsp+274h] [rbp-9Ch]
  char v185[4]; // [rsp+278h] [rbp-98h]
  int v186; // [rsp+27Ch] [rbp-94h]
  int v187; // [rsp+280h] [rbp-90h]
  int v189; // [rsp+288h] [rbp-88h]
  int v190; // [rsp+28Ch] [rbp-84h]
  struct _FILE_OBJECT **v191; // [rsp+290h] [rbp-80h]
  struct _VCB **v192; // [rsp+298h] [rbp-78h]
  struct _PCW_DATA v193; // [rsp+2A0h] [rbp-70h] BYREF
  _DWORD *v194; // [rsp+2B0h] [rbp-60h]
  __int64 v195; // [rsp+2B8h] [rbp-58h]
  __int64 v196; // [rsp+2C0h] [rbp-50h] BYREF
  ULONG v197; // [rsp+2C8h] [rbp-48h]

  v4 = Irp;
  Irpa = Irp;
  v147 = (struct _IRP_CONTEXT *)a1;
  v158 = Irp;
  v192 = a3;
  v191 = a4;
  v151 = 0;
  v150 = 0;
  v105 = 0;
  v99 = 1;
  v104 = 0;
  v102 = 0;
  v107 = 0;
  v108 = 0;
  v6 = 0;
  v106 = 0;
  v161 = 0;
  v103 = 0;
  v112 = 0;
  v149 = 0;
  v156 = 0;
  v101 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids);
    v4 = Irpa;
  }
  if ( !dword_140266E28 && (_BYTE)KdDebuggerEnabled && dword_140266E2C )
    __debugbreak();
  if ( dword_140266E30 || dword_140266E28 )
  {
    BootSectorForMount = -1073741489;
    RefsCompleteRequest((struct _IRP_CONTEXT *)a1, v4, -1073741489);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids, 3221225807LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v11 = 368;
      goto LABEL_223;
    }
    return (unsigned int)BootSectorForMount;
  }
  CurrentStackLocation = v4->Tail.Overlay.CurrentStackLocation;
  Vpb = CurrentStackLocation->Parameters.MountVolume.Vpb;
  v153 = Vpb;
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids, 3221225807LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
    {
      v11 = 389;
LABEL_223:
      RefsStatusDebug(BootSectorForMount, 0, "mount.c", v11);
      return (unsigned int)BootSectorForMount;
    }
    return (unsigned int)BootSectorForMount;
  }
  DeviceObject = CurrentStackLocation->Parameters.MountVolume.DeviceObject;
  TargetDevice = DeviceObject;
  RealDevice->Flags &= ~2u;
  if ( (PUNICODE_STRING)qword_140266E38 != CurrentStackLocation->Parameters.QueryDirectory.FileName )
  {
    v156 = CurrentStackLocation;
    v111 = Vpb;
    v157 = &Vpb->RealDevice;
    if ( ((unsigned __int16)dword_1402612AC & 0x1000) != 0 )
    {
      BootSectorForMount = -1073741077;
      RefsCompleteRequest((struct _IRP_CONTEXT *)a1, v4, -1073741077);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids, 3221226219LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v11 = 409;
        goto LABEL_223;
      }
      return (unsigned int)BootSectorForMount;
    }
    v159 = DeviceObject;
    p_Flags = 0;
    v150 = 0;
    v14 = MEMORY[0xFFFFF78000000320];
    v149 = MEMORY[0xFFFFF78000000320];
    v15 = MEMORY[0xFFFFF78000000014];
    v112 = (_DWORD *)MEMORY[0xFFFFF78000000014];
    Status = InitializeDevice((struct _IRP_CONTEXT *)a1, Vpb, TargetDevice, &v151);
    if ( Status < 0 )
    {
      BootSectorForMount = Status;
    }
    else
    {
      p_Flags = (ULONG *)a1[8];
      v150 = p_Flags;
      *((_QWORD *)p_Flags + 838) = v112;
      *((_QWORD *)p_Flags + 842) = v15;
      *((_QWORD *)p_Flags + 843) = v15;
      *((_QWORD *)p_Flags + 1275) = v14;
      *((_QWORD *)p_Flags + 1276) = v14;
      *((_QWORD *)p_Flags + 1277) = v14;
      *((_QWORD *)p_Flags + 862) = v14;
      *((_QWORD *)p_Flags + 863) = v14;
      *((_QWORD *)p_Flags + 908) = v14;
      *((_QWORD *)p_Flags + 909) = v14;
      *((_QWORD *)p_Flags + 844) = 0;
      *((_QWORD *)p_Flags + 860) = 0;
      *((_QWORD *)p_Flags + 906) = 0;
      *((_QWORD *)p_Flags + 936) = 0;
      *((_QWORD *)p_Flags + 851) = 0;
      *((_QWORD *)p_Flags + 980) = 0;
      RefsQueryNumberDataCopies((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags, 0, 0);
      p_Flags[107] = -1;
      RefsQueryPowerProtectedMode((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags, 0, 0);
      BootSectorForMount = _VCB::ReadBootSectorForMount((_VCB *)p_Flags, (const struct _IRP_CONTEXT *)a1);
      Status = BootSectorForMount;
      if ( BootSectorForMount >= 0 )
      {
        v18 = *((_QWORD *)p_Flags + 1664);
        v157 = (struct _DEVICE_OBJECT **)v18;
        v160 = (struct _DEVICE_OBJECT *)(v18 + 44);
        if ( *(_DWORD *)(v18 + 44) & 0x100 )
          p_Flags[6] |= 0x2000000u;
        v100 = *(_BYTE *)(v18 + 40);
        if ( v100 != 3 || *(_BYTE *)(v18 + 41) > 0xFu )
        {
LABEL_302:
          if ( (Microsoft_Windows_ReFSEnableBits & 0x10) != 0 )
          {
            v85 = *(_BYTE *)(v18 + 41);
            ActivityIdThread = IoGetActivityIdThread();
            LOBYTE(v87) = v100;
            McTemplateK0uuuu_EtwWriteTransfer(v87, v88, ActivityIdThread, v89, (_DWORD)Data, v100, v85);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              16,
              WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
              3221225807LL);
          }
          v137 = (char)RefsStatusDebugEnabled;
          v138 = (char)RefsStatusDebugEnabled;
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741489, (struct _IRP_CONTEXT *)a1, "mount.c", 0x204u);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741489, v17);
          __debugbreak();
          JUMPOUT(0x140323BE0LL);
        }
        v161 = *(_QWORD *)(v18 + 64);
        if ( !v161 )
        {
          v161 = 0x4000000;
          v19 = (p_Flags[6] & 0x2000000) == 0;
          v175 = p_Flags[6] & 0x2000000;
          v139 = !v19;
          v140 = !v19;
          v103 = v175 == 0;
        }
        InitializeVcbFromBootSector(p_Flags, v153, v18);
        if ( ((*p_RealDevice)->Flags & 0x100) != 0 )
        {
          ++p_Flags[58];
          LODWORD(dword_1402612AC) = (unsigned int)dword_1402612AC | 0x100000;
        }
        RefsFillVcbVolumeName((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags, 1u);
        BootSectorForMount = MsKmeInitializeReservedIoRequestsForVcb((struct _VCB *)p_Flags);
        Status = BootSectorForMount;
        if ( BootSectorForMount < 0 )
          goto LABEL_161;
        BootSectorForMount = MsKmeInitializeReservedIoRunsForVcb((struct _VCB *)p_Flags);
        Status = BootSectorForMount;
        if ( BootSectorForMount < 0 )
          goto LABEL_161;
        v104 = 1;
        v112 = p_Flags + 6;
        v20 = p_Flags[6];
        v176 = v20 & 0x2000000;
        if ( (v20 & 0x2000000) != 0 )
        {
          v6 = 2;
          v106 = 2;
        }
        v177 = v20 & 0x80;
        if ( (v20 & 0x80) != 0 )
        {
          v6 = (unsigned int)v6 | 0x40;
          v106 = v6;
        }
        v111 = (struct _VPB *)(p_Flags + 7);
        v21 = p_Flags[7];
        v178 = v21 & 0x10;
        if ( (v21 & 0x10) != 0 )
        {
          LODWORD(v6) = v6 | 0x100000;
          v106 = v6;
        }
        v179 = (unsigned __int16)dword_1402612AC & 0x8000;
        v141 = v179 != 0;
        if ( ((unsigned __int16)dword_1402612AC & 0x8000) != 0 )
        {
          v6 = (unsigned int)v6 | 8;
          v106 = v6;
        }
        if ( dword_140261124 == 1 )
        {
          LODWORD(v6) = v6 | 0x1000000;
          v106 = v6;
        }
        if ( dword_140261124 == 2 )
        {
          v6 = (unsigned int)v6 | 0x2000000;
          v106 = v6;
        }
        LODWORD(v6) = v6 | 0x80000;
        v106 = v6;
        v180 = v21 & 0x200;
        if ( (v21 & 0x200) != 0 )
        {
          v181 = v20 & 0x2000000;
          if ( (v20 & 0x2000000) == 0 && p_Flags[1572] == 16 )
          {
            LODWORD(v6) = v6 | 0x1000;
            v106 = v6;
          }
        }
        v22 = v6;
        v182 = v21 & 0x100;
        if ( (v21 & 0x100) != 0 )
        {
          LODWORD(v6) = v6 | 0x10000000;
          v106 = v6;
          v22 = v6;
        }
        v23 = (unsigned __int64)v160;
        if ( *(_DWORD *)&v160->Type & 0x10 )
        {
          v6 = v22;
          LODWORD(v6) = v22 | 0x4000;
          v106 = v22 | 0x4000;
          v22 |= 0x4000u;
        }
        v194 = (_DWORD *)(*(_QWORD *)(*((_QWORD *)p_Flags + 26) + 16LL) + 48LL);
        *(_DWORD *)v185 = *v194;
        v186 = *(_DWORD *)v185;
        v187 = *(_DWORD *)v185;
        LODWORD(v163) = *(_DWORD *)v185;
        LODWORD(v164) = *(_DWORD *)v185;
        v143 = (*(_DWORD *)v185 & 0x600100) != 0;
        if ( (*(_DWORD *)v185 & 0x600100) != 0 )
        {
          v6 = v22;
          LODWORD(v6) = v22 | 0x200000;
          v106 = v22 | 0x200000;
        }
        RefsFillVcbVolumeGuid((struct _IRP_CONTEXT *)a1);
        RefsCheckToAllowForReadCache((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
        v164 = (unsigned __int8 *)(p_Flags + 198);
        v163 = (unsigned __int8 *)p_Flags + 793;
        v25 = *((unsigned __int8 *)p_Flags + 793) | (*((unsigned __int8 *)p_Flags + 792) << 8);
        if ( v25 >= 0x306 )
        {
          v162 = v25 > 0x306;
          if ( v25 >= 0x30B )
          {
            v110 = v25 > 0x30B;
            p_Flags[2736] = 480;
            p_Flags[2737] = 512;
            p_Flags[2738] = 496;
          }
          else
          {
            v110 = -1;
            p_Flags[2736] = 448;
            p_Flags[2737] = 416;
            p_Flags[2738] = 464;
          }
        }
        else
        {
          v162 = -1;
          LODWORD(v165) = *(_DWORD *)v23 & 4;
          if ( !(_DWORD)v165 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                17,
                WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                3221226140LL);
            }
            v144 = (char)RefsStatusDebugEnabled;
            v145 = (char)RefsStatusDebugEnabled;
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741156, (struct _IRP_CONTEXT *)a1, "mount.c", 0x2B9u);
            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741156, v24);
            goto LABEL_232;
          }
          p_Flags[2736] = 384;
          p_Flags[2737] = 416;
          p_Flags[2738] = 400;
        }
        p_RealDevice = (struct _DEVICE_OBJECT **)(p_Flags + 28);
        v26 = MsInitializeVolume(
                (struct _VCB *)p_Flags,
                p_Flags[138],
                Context,
                v6,
                v92,
                v93,
                v94,
                v95,
                *((unsigned __int8 *)v157 + 40),
                *((unsigned __int8 *)v157 + 41),
                (__int64)(p_Flags + 28),
                (__int64)&v101,
                (__int64)v157[8],
                *((_WORD *)p_Flags + 397));
        v23 = (unsigned int)v26;
        Status = v26;
        if ( v26 >= 0 )
        {
          InitializeVcbWithPerMachineState((struct _VCB *)p_Flags);
          RefsBindMinstoreTransaction((struct _IRP_CONTEXT *)a1);
          v165 = a1 + 3;
          started = MsStartTrashTable(a1[3]);
          v23 = (unsigned int)started;
          Status = started;
          if ( started >= 0 )
          {
            RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
            v23 = (unsigned __int64)&WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              Data = (PPCW_DATA)*((_QWORD *)p_Flags + 1361);
              WPP_SF_qq(
                WPP_GLOBAL_Control->AttachedDevice,
                20,
                WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                *((_QWORD *)p_Flags + 1360));
            }
            p_Flags[2612] = 1;
            if ( *(_DWORD *)&v111->Type & 0x10 )
            {
              v6 = (__int64)p_RealDevice;
            }
            else
            {
              IoPerfInitializeEntityData((struct _IO_PERF_ENTITY_DATA *)(p_Flags + 2624));
              v6 = (__int64)p_RealDevice;
              if ( (unsigned __int8)MsIsVolumeOnSmr(*p_RealDevice) )
              {
                ++p_Flags[2612];
                IoPerfInitializeEntityData((struct _IO_PERF_ENTITY_DATA *)(p_Flags + 2672));
              }
            }
            RefsInitializePerVolumeTelemetry(a1[8]);
            *((_QWORD *)p_Flags + 836) = MsGetVolumePerfCounterBlock(*(_QWORD *)v6);
            *((_QWORD *)p_Flags + 837) = 0;
            if ( RefsPcwCmsCounterSet && *((_QWORD *)p_Flags + 836) && *((_WORD *)p_Flags + 3076) )
            {
              v193.Data = (const void *)*((_QWORD *)p_Flags + 836);
              v193.Size = 608;
              PcwCreateInstance(
                (PPCW_INSTANCE *)p_Flags + 837,
                RefsPcwCmsCounterSet,
                (PCUNICODE_STRING)(p_Flags + 1538),
                1u,
                &v193);
            }
            v31 = InitializeRefsSchemas(*(struct CmsVolume **)v6);
            Status = v31;
            if ( v31 >= 0 )
            {
              InitializeVolumeInfoTable((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
              v32 = v108;
              v189 = v108 & 0x200;
              v33 = v111;
              if ( (v108 & 0x200) != 0 )
                *(_DWORD *)&v111->Type |= 0x4000u;
              v34 = v32 & 0x400;
              v190 = v34;
              if ( v34 )
                *(_DWORD *)&v33->Type |= 0x8000u;
              v166 = v34;
              if ( v34 )
                MsChangeVolumeOptionDynamically(*(_QWORD *)v6, 0x80000, 0);
              if ( (unsigned __int8)MsIsReallocateAllDataWritesEnabled(*(_QWORD *)v6) )
              {
                LOBYTE(v36) = 1;
                MsChangeVolumeOptionDynamically(v35, 256, v36);
              }
              MsChangeVolumeContainerRotationThresholds(
                *(_QWORD *)v6,
                dword_140261874,
                dword_140261878,
                dword_14026187C,
                dword_140261880,
                dword_140261884);
              MsChangeVolumeContainerRotationEventThresholds(*(_QWORD *)v6, (unsigned int)dword_140261888);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 1, &RefsTelemetrySampling);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 2, (char *)&RefsTelemetrySampling + 8);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 3, &qword_1402608C8);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 4, &qword_1402608D0);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 5, &qword_1402608D8);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 6, &xmmword_1402608E0);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 7, (char *)&xmmword_1402608E0 + 8);
              MsChangeVolumeSettingDynamically(*(_QWORD *)v6, 8, &qword_1402608F0);
              _InterlockedExchange64((volatile __int64 *)p_Flags + 858, qword_1402608C0);
              _InterlockedExchange64((volatile __int64 *)p_Flags + 1180, qword_1402608F8);
              v167 = v108 & 4;
              v98 = v167 != 0;
              v118 = v167 != 0;
              v102 = v167 != 0;
              v168 = v108 & 0x40;
              v100 = v168 != 0;
              v119 = v168 != 0;
              v107 = v168 != 0;
              InitializeVcbDeviceName((struct _IRP_CONTEXT *)a1);
              if ( *(_DWORD *)&v111->Type & 0x10 )
              {
LABEL_113:
                v6 = (__int64)v112;
                if ( !(*v112 & 8) )
                  FsRtlBalanceReads(TargetDevice);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                CreateTemplateFiles((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                LOBYTE(v46) = v100;
                LOBYTE(v47) = v98;
                OpenRootDirectory(a1, p_Flags, v47, v46);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                OpenMetadataDirectory((struct _IRP_CONTEXT *)a1);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                OpenDegenerateMetadataDirectory((struct _IRP_CONTEXT *)a1);
                RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                LODWORD(v23) = RefsSecurityInitialize((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
                Statusa = v23;
                if ( (v23 & 0x80000000) == 0LL )
                {
                  OpenSecurityFile((struct _IRP_CONTEXT *)a1);
                  RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                  if ( *(_DWORD *)v6 & 0x2000000 )
                    goto LABEL_123;
                  v49 = *v163 | (*v164 << 8);
                  if ( v49 >= 0x307 )
                  {
                    if ( v49 > 0x307 )
                    {
                      v154 = 1;
                      goto LABEL_123;
                    }
                    v154 = 0;
                  }
                  else
                  {
                    v154 = -1;
                  }
                  CreateDownlevelDegenerateMetadataObjects((struct _IRP_CONTEXT *)a1);
                  RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
LABEL_123:
                  InitializeDasdFile((struct _IRP_CONTEXT *)a1);
                  RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                  InitializeReparseIndexTable((struct _IRP_CONTEXT *)a1);
                  RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                  v51 = InitializeVerifyBlock((struct _IRP_CONTEXT *)a1);
                  Statusa = v51;
                  if ( v51 >= 0 )
                  {
                    RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                    LODWORD(v157) = v108 & 8;
                    if ( (v108 & 8) != 0 )
                    {
                      *(_DWORD *)v6 |= 0x100000u;
                      v6 = (__int64)&WPP_GLOBAL_Control;
LABEL_128:
                      MsStartVolumeAnalyzer(*p_RealDevice);
                      MsSetMinimumNewObjectId(*p_RealDevice);
                      RefsCleanupTransaction((struct _IRP_CONTEXT *)a1, 0, 0);
                      RefsCheckpointCurrentTransaction((struct _IRP_CONTEXT *)a1);
                      v19 = (*v112 & 0x2000000) == 0;
                      LODWORD(v159) = *v112 & 0x2000000;
                      v129 = !v19;
                      v130 = !v19;
                      if ( (_DWORD)v159 )
                        goto LABEL_137;
                      v110 = *(_DWORD *)&v160->Type;
                      v142 = v110;
                      SetVolumeMounted((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
                      LODWORD(v158) = v108 & 0x10;
                      if ( (v108 & 0x10) != 0 )
                      {
                        LOBYTE(Data) = 0;
                        RefsSetClearVolumeFlag(a1, p_Flags, 16);
                      }
                      LODWORD(TargetDevice) = v110 & 2;
                      if ( (v110 & 2) == 0 )
                      {
                        v142 = v110 | 2;
                        LODWORD(v153) = *v112 & 0x80;
                        if ( (_DWORD)v153 )
                          v142 = v110 | 3;
                        v103 = 1;
                      }
                      if ( !v103
                        || (updated = _VCB::UpdateBootSector((struct _VCB *)p_Flags, (__int64)&v161, 0, 0),
                            Statusa = updated,
                            updated >= 0) )
                      {
LABEL_137:
                        if ( v98 )
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
                          LODWORD(v111) = 262145;
                          v58 = MsFlushVolume((unsigned int)*p_RealDevice, 262145, 0, 0, 0, 0);
                          Statusa = v58;
                          if ( v58 < 0 )
                          {
LABEL_295:
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v6
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                            {
                              WPP_SF_d(
                                WPP_GLOBAL_Control->AttachedDevice,
                                28,
                                WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                                (unsigned int)v58);
                              v58 = Statusa;
                            }
                            v133 = (char)RefsStatusDebugEnabled;
                            v134 = (char)RefsStatusDebugEnabled;
                            if ( (_BYTE)RefsStatusDebugEnabled )
                              RefsStatusDebug(v58, (struct _IRP_CONTEXT *)a1, "mount.c", 0x537u);
                            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Statusa, v59);
                            goto LABEL_302;
                          }
                        }
                        v56 = MsReserveLogSpace(*p_RealDevice);
                        Statusa = v56;
                        if ( v56 >= 0 )
                        {
                          v60 = v112;
                          v61 = v112;
                          *v112 |= 0x4000u;
                          LODWORD(p_RealDevice) = *v61 & 0x100000;
                          if ( (_DWORD)p_RealDevice )
                            RefsPostSpecial(
                              (struct _IRP_CONTEXT *)a1,
                              (struct _VCB *)p_Flags,
                              (void (*)(struct _IRP_CONTEXT *, void *))RefsDeleteUsnSpecial,
                              p_Flags + 298,
                              1u,
                              0);
                          v62 = (struct _FILE_OBJECT *)*((_QWORD *)p_Flags + 12);
                          *v191 = v62;
                          ObfReferenceObject(v62);
                          MasterIrp = Irpa->AssociatedIrp.MasterIrp;
                          if ( MasterIrp && v156->Parameters.Read.ByteOffset.LowPart >= 0x2C )
                          {
                            *(_OWORD *)&MasterIrp->Type = 0;
                            *(_OWORD *)&MasterIrp->Flags = 0;
                            *(_OWORD *)((char *)&MasterIrp->AssociatedIrp.SystemBuffer + 4) = 0;
                            *(_DWORD *)(&MasterIrp->Size + 1) = 25343;
                            RefsQueryPersistentVolumeStateFlags(p_Flags, v108, 25343, &MasterIrp->MdlAddress);
                            *(_OWORD *)((char *)&MasterIrp->MdlAddress + 4) = *((_OWORD *)p_Flags + 378);
                            *(_OWORD *)((char *)&MasterIrp->AssociatedIrp.SystemBuffer + 4) = *((_OWORD *)p_Flags + 831);
                            Irpa->IoStatus.Information = 44;
                          }
                          BootSectorForMount = 0;
                          Status = 0;
                          v99 = 0;
                          *v60 |= 0x10000000u;
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                          {
                            Data = (PPCW_DATA)*((_QWORD *)p_Flags + 1361);
                            WPP_SF_qq(
                              WPP_GLOBAL_Control->AttachedDevice,
                              30,
                              WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                              *((_QWORD *)p_Flags + 1360));
                          }
                          v64 = qword_1402610A0;
                          v65 = *(_BYTE *)(qword_1402610A0 + 76);
                          StackSize = v151->StackSize;
                          if ( StackSize > v65 )
                          {
                            v67 = StackSize - v65;
                            while ( v64 )
                            {
                              *(_BYTE *)(v64 + 76) += v67;
                              v64 = *(_QWORD *)(v64 + 24);
                            }
                          }
                          RefsInitializePerfCountersTelemetry(p_Flags);
                          goto LABEL_161;
                        }
LABEL_288:
                        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v6
                          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        {
                          WPP_SF_d(
                            WPP_GLOBAL_Control->AttachedDevice,
                            29,
                            WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                            (unsigned int)v56);
                          v56 = Statusa;
                        }
                        v135 = (char)RefsStatusDebugEnabled;
                        v136 = (char)RefsStatusDebugEnabled;
                        if ( (_BYTE)RefsStatusDebugEnabled )
                          RefsStatusDebug(v56, (struct _IRP_CONTEXT *)a1, "mount.c", 0x543u);
                        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Statusa, v57);
                        goto LABEL_295;
                      }
LABEL_281:
                      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v6
                        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      {
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          27,
                          WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                          (unsigned int)updated);
                        updated = Statusa;
                      }
                      v131 = (char)RefsStatusDebugEnabled;
                      v132 = (char)RefsStatusDebugEnabled;
                      if ( (_BYTE)RefsStatusDebugEnabled )
                        RefsStatusDebug(updated, (struct _IRP_CONTEXT *)a1, "mount.c", 0x50Au);
                      RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Statusa, v55);
                      goto LABEL_288;
                    }
                    RefsBindMinstoreTransaction((struct _IRP_CONTEXT *)a1);
                    v195 = *((_QWORD *)p_Flags + 13);
                    v52 = MsUpdateTree(*v165, v195, 1, 0, 0);
                    v6 = (unsigned int)v52;
                    Statusa = v52;
                    if ( v52 >= 0 )
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
                      goto LABEL_128;
                    }
LABEL_274:
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        26,
                        WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                        (unsigned int)v6);
                    }
                    v127 = (char)RefsStatusDebugEnabled;
                    v128 = (char)RefsStatusDebugEnabled;
                    if ( (_BYTE)RefsStatusDebugEnabled )
                      RefsStatusDebug(v6, (struct _IRP_CONTEXT *)a1, "mount.c", 0x49Du);
                    RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v6, v53);
                    goto LABEL_281;
                  }
LABEL_267:
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      25,
                      WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                      (unsigned int)v51);
                    v51 = Statusa;
                  }
                  v125 = (char)RefsStatusDebugEnabled;
                  v126 = (char)RefsStatusDebugEnabled;
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(v51, (struct _IRP_CONTEXT *)a1, "mount.c", 0x47Bu);
                  RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Statusa, v50);
                  goto LABEL_274;
                }
LABEL_260:
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    24,
                    WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                    (unsigned int)v23);
                }
                v123 = (char)RefsStatusDebugEnabled;
                v124 = (char)RefsStatusDebugEnabled;
                if ( (_BYTE)RefsStatusDebugEnabled )
                  RefsStatusDebug(v23, (struct _IRP_CONTEXT *)a1, "mount.c", 0x44Eu);
                RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v23, v48);
                goto LABEL_267;
              }
              v196 = 0;
              v197 = 0;
              if ( (int)RefsDeviceIoControl(
                          (struct _IRP_CONTEXT *)a1,
                          *((PDEVICE_OBJECT *)a1[8] + 24),
                          0x2D1080u,
                          0,
                          0,
                          0,
                          &v196,
                          0xCu,
                          0) < 0 )
              {
                v196 = 0;
                v197 = 0;
              }
              v38 = *((_QWORD *)p_Flags + 756) - *(_QWORD *)&`IsGuidZero'::`2'::ZeroGuid.Data1;
              if ( !v38 )
                v38 = *((_QWORD *)p_Flags + 757) - *(_QWORD *)`IsGuidZero'::`2'::ZeroGuid.Data4;
              v170 = v38 == 0;
              v120 = v38 == 0;
              if ( v38 )
              {
                *(_OWORD *)(p_Flags + 1647) = *((_OWORD *)p_Flags + 378);
LABEL_104:
                if ( (unsigned __int8)MsShouldEnableHeatDetection()
                  && (v39 = IoGetActivityIdThread(), (int)FsRtlHeatInit(p_Flags + 1641, p_Flags + 1647, v39) >= 0) )
                {
                  v40 = v111;
                  *(_DWORD *)&v111->Type |= 0x20u;
                  p_Flags[1646] = p_Flags[1642] & 7;
                  if ( *(_DWORD *)&v40->Type & 0x4000 )
                    p_Flags[1642] &= 0xFFFFFFF8;
                }
                else
                {
                  v40 = v111;
                }
                if ( (unsigned __int8)MsIsDedupEnabled(*(_QWORD *)v6) )
                {
                  v41 = IoGetActivityIdThread();
                  v42 = *(_DWORD *)&v40->Type & 0x100;
                  v184 = v42;
                  VolumeUniqueGuid = MsGetVolumeUniqueGuid(*p_RealDevice);
                  LOBYTE(v44) = v42 != 0;
                  Data = (PPCW_DATA)v41;
                  if ( (int)FsRtlDedupChangeInit(p_Flags + 1643, p_Flags + 1647, VolumeUniqueGuid, v44) >= 0 )
                  {
                    v45 = v111;
                    *(_DWORD *)&v111->Type |= 0x80u;
                    if ( (unsigned __int8)MsIsDirtyStateTrackingEnabled(*p_RealDevice) )
                      *(_DWORD *)&v45->Type |= 0x400u;
                  }
                }
                goto LABEL_113;
              }
              if ( (_DWORD)v196 )
              {
                *(_OWORD *)(p_Flags + 1647) = 0;
                p_Flags[1647] = HIDWORD(v196);
                p_Flags[1648] = v197;
                goto LABEL_104;
              }
LABEL_253:
              Statusa = -1073741823;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v23
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              {
                WPP_SF_d(
                  WPP_GLOBAL_Control->AttachedDevice,
                  23,
                  WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                  3221225473LL);
              }
              v121 = (char)RefsStatusDebugEnabled;
              v122 = (char)RefsStatusDebugEnabled;
              if ( (_BYTE)RefsStatusDebugEnabled )
                RefsStatusDebug(-1073741823, (struct _IRP_CONTEXT *)a1, "mount.c", 0x3BEu);
              RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, -1073741823, v37);
              goto LABEL_260;
            }
LABEL_246:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)v23
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                21,
                WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
                (unsigned int)v31);
              v31 = Status;
            }
            v116 = (char)RefsStatusDebugEnabled;
            v117 = (char)RefsStatusDebugEnabled;
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(v31, (struct _IRP_CONTEXT *)a1, "mount.c", 0x32Au);
            RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, Status, v30);
            goto LABEL_253;
          }
LABEL_239:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              19,
              WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
              (unsigned int)v23);
          }
          v114 = (char)RefsStatusDebugEnabled;
          v115 = (char)RefsStatusDebugEnabled;
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v23, (struct _IRP_CONTEXT *)a1, "mount.c", 0x2DFu);
          RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v23, v29);
          goto LABEL_246;
        }
LABEL_232:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            18,
            WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids,
            (unsigned int)v23);
        }
        v146 = (char)RefsStatusDebugEnabled;
        v148 = (char)RefsStatusDebugEnabled;
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(v23, (struct _IRP_CONTEXT *)a1, "mount.c", 0x2D2u);
        RefsRaiseStatusInternal((struct _IRP_CONTEXT *)a1, v23, v27);
        goto LABEL_239;
      }
    }
LABEL_161:
    if ( v151 )
    {
      p_Flags = &v151[1].Flags;
      v68 = *(_QWORD *)&v151[1].Queue.Wcb.NumberOfMapRegisters;
      if ( v68 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v68 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 9) + 136LL));
      v69 = *((_QWORD *)p_Flags + 4);
      if ( v69 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v69 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 4) + 136LL));
      v70 = *((_QWORD *)p_Flags + 8);
      if ( v70 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v70 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 8) + 136LL));
      v71 = *((_QWORD *)p_Flags + 5);
      if ( v71 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v71 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 5) + 136LL));
      v72 = *((_QWORD *)p_Flags + 6);
      if ( v72 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v72 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 6) + 136LL));
      v73 = *((_QWORD *)p_Flags + 11);
      if ( v73 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v73 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 11) + 136LL));
      v74 = *((_QWORD *)p_Flags + 10);
      if ( v74 && (unsigned __int8)ExIsFastResourceHeld(*(_QWORD *)(*(_QWORD *)(v74 + 136) + 88LL) + 64LL) )
        RefsReleaseFcb((struct _IRP_CONTEXT *)a1, *(struct _FCB **)(*((_QWORD *)p_Flags + 10) + 136LL));
      v75 = v99;
      if ( v99 )
      {
        v155 = 0;
        if ( v104 )
        {
          if ( RefsInstrumentThrottle(v16, 0x206u) )
            RefsEtwWriteVolumeFailureEvent(
              (struct _VCB *)p_Flags,
              &REFS_ETW_VOLUME_MOUNT_FAILURE,
              *((_DWORD *)a1[13] + 4),
              0);
          if ( RefsInstrumentThrottle(v76, 0x409u) )
            RefsTelemetryMountVolumeStatusFailure(
              (struct _VCB *)p_Flags,
              BootSectorForMount,
              MEMORY[0xFFFFF78000000320] - v14,
              *(_DWORD *)(*((_QWORD *)p_Flags + 1664) + 44LL),
              v101);
        }
        if ( RefsIsTriagePending((struct _IRP_CONTEXT *)a1) )
          RefsDiscardTriageInfo((struct _IRP_CONTEXT *)a1);
        RefsAbortTransaction((struct _IRP_CONTEXT *)a1);
        RefsCleanupFailedTransaction((struct _IRP_CONTEXT *)a1, 0);
        RefsReleaseAllResources((struct _IRP_CONTEXT *)a1);
        p_Flags[6] &= ~1u;
        v77 = *((_DWORD *)a1 + 4);
        RefsPurgeVolumeCatchExceptions(a1, p_Flags);
        *((_DWORD *)a1 + 4) = v77;
        LODWORD(Data) = 6;
        LOBYTE(v78) = 1;
        LOBYTE(v79) = 1;
        RefsPerformDismountOnVcb(a1, p_Flags, v79, v78, Data, &v155);
        v80 = *((_DWORD *)a1[13] + 4);
        if ( v80 == -1073741432 || v80 == -1073741400 || v80 == -1073741608 )
        {
          BootSectorForMount = Status;
          if ( v155 )
            v156->Parameters.WMI.ProviderId = v155;
        }
        else
        {
          BootSectorForMount = Status;
        }
      }
    }
    else
    {
      v75 = v99;
    }
    if ( v105 )
      RefsReleaseVcbCheckDelete((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
    if ( v151 && v75 )
      a1[8] = 0;
    RefsForEachVcb((struct _IRP_CONTEXT *)a1, FilterVcbForDeletion, CheckVcbForDeletion, 0, 0);
    if ( !v75 )
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
      if ( (v108 & 0x20) != 0 )
        p_Flags[6] |= 0x200u;
      else
        p_Flags[6] &= ~0x200u;
      RefsPostSqmVolumeInfo((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags);
      RefsPostTelemetryVolumeInfo(
        (struct _IRP_CONTEXT *)a1,
        (struct _VCB *)p_Flags,
        MEMORY[0xFFFFF78000000320] - v14,
        *(_DWORD *)(*((_QWORD *)p_Flags + 1664) + 44LL),
        v101);
      if ( !_InterlockedCompareExchange(&dword_14026129C, 1, 0) )
        KeSetCoalescableTimer(&stru_140261238, RefsPeriodicTimerInterval, 0, 0x3A98u, &stru_1402611F8);
      LOBYTE(v81) = 1;
      ExAcquireFastResourceExclusive(qword_1402610B8, 0, v81);
      a1[8] = (struct CmsTransactionContext *)p_Flags;
      if ( ((unsigned __int16)dword_1402612AC & 0x1000) != 0 )
      {
        ExReleaseFastResource(qword_1402610B8, 0);
        RefsShutdownVolume((struct _IRP_CONTEXT *)a1, (struct _VCB *)p_Flags, 0);
        LOBYTE(v82) = 1;
        ExAcquireFastResourceExclusive(qword_1402610B8, 0, v82);
      }
      v83 = (_QWORD *)qword_1402610B0;
      if ( *(__int64 **)qword_1402610B0 != &qword_1402610A8 )
        __fastfail(3u);
      *((_QWORD *)p_Flags + 1) = &qword_1402610A8;
      *((_QWORD *)p_Flags + 2) = v83;
      *v83 = p_Flags + 2;
      qword_1402610B0 = (__int64)(p_Flags + 2);
      ExReleaseFastResource(qword_1402610B8, 0);
      if ( v192 )
        *v192 = (struct _VCB *)p_Flags;
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
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids, 3221225807LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v11 = 397;
    goto LABEL_223;
  }
  return (unsigned int)BootSectorForMount;
}

```

## disassembly

```asm
0x140321a64  mov     r11, rsp
0x140321a67  push    rbx
0x140321a68  push    rsi
0x140321a69  push    rdi
0x140321a6a  push    r12
0x140321a6c  push    r13
0x140321a6e  push    r14
0x140321a70  push    r15
0x140321a72  sub     rsp, 240h
0x140321a79  mov     rax, cs:__security_cookie
0x140321a80  xor     rax, rsp
0x140321a83  mov     [rsp+278h+var_40], rax
0x140321a8b  mov     r10, rdx
0x140321a8e  mov     [rsp+278h+Irp], rdx
0x140321a96  mov     r13, rcx
0x140321a99  mov     [rsp+278h+var_180], rcx
0x140321aa1  mov     [rsp+278h+var_128], rdx
0x140321aa9  mov     [rsp+278h+var_78], r8
0x140321ab1  mov     [rsp+278h+var_80], r9
0x140321ab9  mov     [rsp+278h+Status], 0C0000001h
0x140321ac4  xor     r15d, r15d
0x140321ac7  mov     [r11-160h], r15
0x140321ace  mov     [r11-168h], r15
0x140321ad5  mov     [r11-1DDh], r15b
0x140321adc  mov     [rsp+278h+var_1E3], 1
0x140321ae4  mov     [r11-1DEh], r15b
0x140321aeb  mov     [r11-1E0h], r15b
0x140321af2  mov     [r11-1D8h], r15b
0x140321af9  mov     [r11-1D4h], r15d
0x140321b00  mov     esi, r15d
0x140321b03  mov     [r11-1DCh], r15d
0x140321b0a  mov     [r11-110h], r15
0x140321b11  mov     [r11-1DFh], r15b
0x140321b18  mov     [r11-1B8h], r15
0x140321b1f  mov     [r11-170h], r15
0x140321b26  mov     [r11-138h], r15
0x140321b2d  mov     [r11-1E1h], r15b
0x140321b34  lea     r12, WPP_GLOBAL_Control
0x140321b3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140321b42  cmp     rcx, r12
0x140321b45  jz      short loc_140321B70
0x140321b47  mov     eax, [rcx+2Ch]
0x140321b4a  test    al, 2
0x140321b4c  jz      short loc_140321B70
0x140321b4e  cmp     byte ptr [rcx+29h], 2
0x140321b52  jb      short loc_140321B70
0x140321b54  lea     edx, [r15+0Ah]
0x140321b58  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x140321b5f  mov     rcx, [rcx+18h]
0x140321b63  call    WPP_SF_
0x140321b68  mov     r10, [rsp+278h+Irp]
0x140321b70  mov     ecx, cs:dword_140266E28
0x140321b76  test    ecx, ecx
0x140321b78  jnz     short loc_140321B90
0x140321b7a  mov     rax, cs:KdDebuggerEnabled
0x140321b81  cmp     [rax], r15b
0x140321b84  jz      short loc_140321B90
0x140321b86  cmp     cs:dword_140266E2C, r15d
0x140321b8d  jz      short loc_140321B90
0x140321b8f  int     3; Trap to Debugger
0x140321b90  cmp     cs:dword_140266E30, r15d
0x140321b97  jnz     loc_140323586
0x140321b9d  test    ecx, ecx
0x140321b9f  jnz     loc_140323586
0x140321ba5  mov     rcx, [r10+0B8h]
0x140321bac  mov     r11, [rcx+8]
0x140321bb0  mov     [rsp+278h+var_150], r11
0x140321bb8  lea     rdx, [r11+10h]
0x140321bbc  mov     [rsp+278h+var_1D0], rdx
0x140321bc4  mov     r8, [rdx]
0x140321bc7  mov     eax, [r8+34h]
0x140321bcb  test    al, 5
0x140321bcd  jz      short loc_140321C30
0x140321bcf  mov     [r10+38h], r15
0x140321bd3  mov     ebx, 0C000014Fh
0x140321bd8  mov     r8d, ebx; Status
0x140321bdb  mov     rdx, r10; Irp
0x140321bde  mov     rcx, r13; struct _IRP_CONTEXT *
0x140321be1  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140321be6  mov     rcx, cs:WPP_GLOBAL_Control
0x140321bed  cmp     rcx, r12
0x140321bf0  jz      short loc_140321C17
0x140321bf2  bt      dword ptr [rcx+2Ch], 8
0x140321bf7  jnb     short loc_140321C17
0x140321bf9  cmp     byte ptr [rcx+29h], 4
0x140321bfd  jb      short loc_140321C17
0x140321bff  mov     edx, 0Ch
0x140321c04  mov     r9d, ebx
0x140321c07  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x140321c0e  mov     rcx, [rcx+18h]
0x140321c12  call    WPP_SF_d
0x140321c17  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140321c1d  test    al, al
0x140321c1f  jz      loc_1403235EA
0x140321c25  mov     r9d, 185h
0x140321c2b  jmp     loc_1403235DA
0x140321c30  mov     r9, [rcx+10h]
0x140321c34  mov     [rsp+278h+TargetDevice], r9
0x140321c3c  and     dword ptr [r8+30h], 0FFFFFFFDh
0x140321c41  mov     rax, cs:qword_140266E38
0x140321c48  cmp     rax, [rcx+10h]
0x140321c4c  jnz     short loc_140321CAB
0x140321c4e  mov     ebx, 0C000014Fh
0x140321c53  mov     r8d, ebx; Status
0x140321c56  mov     rdx, r10; Irp
0x140321c59  mov     rcx, r13; struct _IRP_CONTEXT *
0x140321c5c  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140321c61  mov     rcx, cs:WPP_GLOBAL_Control
0x140321c68  cmp     rcx, r12
0x140321c6b  jz      short loc_140321C92
0x140321c6d  bt      dword ptr [rcx+2Ch], 8
0x140321c72  jnb     short loc_140321C92
0x140321c74  cmp     byte ptr [rcx+29h], 4
0x140321c78  jb      short loc_140321C92
0x140321c7a  mov     edx, 0Dh
0x140321c7f  mov     r9d, ebx
0x140321c82  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x140321c89  mov     rcx, [rcx+18h]
0x140321c8d  call    WPP_SF_d
0x140321c92  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140321c98  test    al, al
0x140321c9a  jz      loc_1403235EA
0x140321ca0  mov     r9d, 18Dh
0x140321ca6  jmp     loc_1403235DA
0x140321cab  mov     [rsp+278h+var_138], rcx
0x140321cb3  mov     [rsp+278h+var_1C0], r11
0x140321cbb  mov     [rsp+278h+var_130], rdx
0x140321cc3  mov     eax, cs:dword_1402612AC
0x140321cc9  bt      eax, 0Ch
0x140321ccd  jnb     short loc_140321D2C
0x140321ccf  mov     ebx, 0C00002EBh
0x140321cd4  mov     r8d, ebx; Status
0x140321cd7  mov     rdx, r10; Irp
0x140321cda  mov     rcx, r13; struct _IRP_CONTEXT *
0x140321cdd  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140321ce2  mov     rcx, cs:WPP_GLOBAL_Control
0x140321ce9  cmp     rcx, r12
0x140321cec  jz      short loc_140321D13
0x140321cee  bt      dword ptr [rcx+2Ch], 8
0x140321cf3  jnb     short loc_140321D13
0x140321cf5  cmp     byte ptr [rcx+29h], 4
0x140321cf9  jb      short loc_140321D13
0x140321cfb  mov     edx, 0Eh
0x140321d00  mov     r9d, ebx
0x140321d03  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x140321d0a  mov     rcx, [rcx+18h]
0x140321d0e  call    WPP_SF_d
0x140321d13  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140321d19  test    cl, cl
0x140321d1b  jz      loc_1403235EA
0x140321d21  mov     r9d, 199h
0x140321d27  jmp     loc_1403235DA
0x140321d2c  mov     [rsp+278h+var_120], r9
0x140321d34  mov     r14, r15
0x140321d37  mov     [rsp+278h+var_168], r15
0x140321d3f  mov     r12, 0FFFFF78000000320h
0x140321d49  mov     rdi, [r12]
0x140321d4d  mov     [rsp+278h+var_170], rdi
0x140321d55  mov     rbx, 0FFFFF78000000014h
0x140321d5f  mov     rbx, [rbx]
0x140321d62  mov     [rsp+278h+var_1B8], rbx
0x140321d6a  lea     rax, [rsp+278h+var_160]
0x140321d72  mov     [rsp+278h+Data], rax; PDEVICE_OBJECT *
0x140321d77  lea     r9, [rsp+278h+var_1DD]
0x140321d7f  mov     r8, [rsp+278h+TargetDevice]; Object
0x140321d87  mov     rdx, r11; struct _VPB *
0x140321d8a  mov     rcx, r13; struct _IRP_CONTEXT *
0x140321d8d  call    InitializeDevice
0x140321d92  mov     [rsp+278h+Status], eax
0x140321d99  jmp     loc_140321EA0
0x140321d9e  lea     rax, WPP_GLOBAL_Control
0x140321da5  mov     rcx, cs:WPP_GLOBAL_Control
0x140321dac  cmp     rcx, rax
0x140321daf  jz      short loc_140321DDB
0x140321db1  test    dword ptr [rcx+2Ch], 100h
0x140321db8  jz      short loc_140321DDB
0x140321dba  cmp     byte ptr [rcx+29h], 4
0x140321dbe  jb      short loc_140321DDB
0x140321dc0  mov     edx, 0Fh
0x140321dc5  mov     r9d, 0C000014Fh
0x140321dcb  lea     r8, WPP_ab46abeb937339b85eab1dd3b59a67d7_Traceguids
0x140321dd2  mov     rcx, [rcx+18h]
0x140321dd6  call    WPP_SF_d
0x140321ddb  mov     al, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140321de1  mov     [rsp+278h+var_1E2], al
0x140321de8  mov     [rsp+278h+var_1E4], al
0x140321def  test    al, al
0x140321df1  jz      short loc_140321E0C
0x140321df3  mov     r9d, 1B8h; unsigned int
0x140321df9  lea     r8, aMountC; "mount.c"
0x140321e00  xor     edx, edx; struct _IRP_CONTEXT *
0x140321e02  mov     ecx, 0C000014Fh; Status
0x140321e07  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140321e0c  mov     eax, 0C000014Fh
0x140321e11  mov     [rsp+278h+Status], eax
0x140321e18  mov     r13, [rsp+278h+var_180]
0x140321e20  test    r13, r13
0x140321e23  jz      short loc_140321E3E
0x140321e25  mov     dword ptr [rsp+278h+var_118], 0FFFFFEFFh
0x140321e30  btr     dword ptr [r13+4], 8
0x140321e36  mov     dword ptr [r13+10h], 0
0x140321e3e  xor     r15d, r15d
0x140321e41  mov     rcx, [rsp+278h+var_120]
0x140321e49  mov     [rsp+278h+TargetDevice], rcx
0x140321e51  mov     rcx, [rsp+278h+var_1C0]
0x140321e59  mov     [rsp+278h+var_150], rcx
0x140321e61  mov     r14, [rsp+278h+var_168]
0x140321e69  mov     esi, [rsp+278h+var_1DC]
0x140321e70  mov     rbx, [rsp+278h+var_1B8]
0x140321e78  mov     rdi, [rsp+278h+var_170]
0x140321e80  mov     rcx, [rsp+278h+var_130]
0x140321e88  mov     [rsp+278h+var_1D0], rcx
0x140321e90  mov     rcx, [rsp+278h+var_128]
0x140321e98  mov     [rsp+278h+Irp], rcx
0x140321ea0  test    eax, eax
0x140321ea2  js      loc_140323077
0x140321ea8  mov     r14, [r13+40h]
0x140321eac  mov     [rsp+278h+var_168], r14
0x140321eb4  mov     eax, dword ptr [rsp+278h+var_1B8+4]
0x140321ebb  mov     [r14+1A34h], eax
0x140321ec2  mov     eax, dword ptr [rsp+278h+var_1B8]
0x140321ec9  mov     [r14+1A30h], eax
0x140321ed0  mov     [r14+1A50h], rbx
0x140321ed7  mov     [r14+1A58h], rbx
0x140321ede  mov     [r14+27D8h], rdi
0x140321ee5  mov     [r14+27E0h], rdi
0x140321eec  mov     [r14+27E8h], rdi
0x140321ef3  mov     [r14+1AF0h], rdi
0x140321efa  mov     [r14+1AF8h], rdi
0x140321f01  mov     [r14+1C60h], rdi
0x140321f08  mov     [r14+1C68h], rdi
0x140321f0f  mov     [r14+1A60h], r15
0x140321f16  mov     [r14+1AE0h], r15
0x140321f1d  mov     [r14+1C50h], r15
0x140321f24  mov     [r14+1D40h], r15
0x140321f2b  mov     [r14+1A98h], r15
0x140321f32  mov     [r14+1EA0h], r15
0x140321f39  xor     r9d, r9d; struct _STORAGE_DEVICE_RESILIENCY_DESCRIPTOR **
0x140321f3c  xor     r8d, r8d; unsigned int *
0x140321f3f  mov     rdx, r14; struct _VCB *
0x140321f42  mov     rcx, r13; struct _IRP_CONTEXT *
0x140321f45  call    ?RefsQueryNumberDataCopies@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAKPEAPEAU_STORAGE_DEVICE_RESILIENCY_DESCRIPTOR@@@Z; RefsQueryNumberDataCopies(_IRP_CONTEXT *,_VCB *,ulong *,_STORAGE_DEVICE_RESILIENCY_DESCRIPTOR * *)
0x140321f4a  mov     dword ptr [r14+1ACh], 0FFFFFFFFh
0x140321f55  xor     r9d, r9d; struct _DISK_CACHE_INFORMATION **
0x140321f58  xor     r8d, r8d; unsigned __int8 *
0x140321f5b  mov     rdx, r14; struct _VCB *
0x140321f5e  mov     rcx, r13; struct _IRP_CONTEXT *
0x140321f61  call    ?RefsQueryPowerProtectedMode@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAEPEAPEAU_DISK_CACHE_INFORMATION@@@Z; RefsQueryPowerProtectedMode(_IRP_CONTEXT *,_VCB *,uchar *,_DISK_CACHE_INFORMATION * *)
0x140321f66  mov     rdx, r13; struct _IRP_CONTEXT *
0x140321f69  mov     rcx, r14; this
0x140321f6c  call    ?ReadBootSectorForMount@_VCB@@QEAAJAEBU_IRP_CONTEXT@@@Z; _VCB::ReadBootSectorForMount(_IRP_CONTEXT const &)
0x140321f71  mov     ebx, eax
0x140321f73  mov     [rsp+278h+Status], eax
0x140321f7a  test    eax, eax
0x140321f7c  js      loc_14032307E
0x140321f82  mov     rdx, [r14+3400h]
0x140321f89  mov     [rsp+278h+var_130], rdx
0x140321f91  lea     rax, [rdx+2Ch]
0x140321f95  mov     [rsp+278h+var_118], rax
0x140321f9d  mov     eax, [rax]
0x140321f9f  mov     r12d, 100h
0x140321fa5  and     eax, r12d
0x140321fa8  mov     [rsp+278h+var_CC], eax
0x140321faf  jz      short loc_140321FB7
0x140321fb1  bts     dword ptr [r14+18h], 19h
0x140321fb7  mov     al, [rdx+28h]
0x140321fba  mov     [rsp+278h+var_1E2], al
0x140321fc1  cmp     al, 3
0x140321fc3  jnz     loc_140323B30
0x140321fc9  cmp     byte ptr [rdx+29h], 0Fh
0x140321fcd  ja      loc_140323B30
0x140321fd3  mov     rax, [rdx+40h]
0x140321fd7  mov     [rsp+278h+var_110], rax
0x140321fdf  test    rax, rax
0x140321fe2  jnz     short loc_14032201C
0x140321fe4  mov     [rsp+278h+var_110], 4000000h
0x140321ff0  mov     ecx, [r14+18h]
0x140321ff4  and     ecx, 2000000h
0x140321ffa  mov     [rsp+278h+var_C0], ecx
0x140322001  setnz   al
0x140322004  mov     [rsp+278h+var_18D], al
0x14032200b  mov     [rsp+278h+var_18C], al
0x140322012  test    ecx, ecx
0x140322014  setz    [rsp+278h+var_1DF]
0x14032201c  mov     r8, rdx
0x14032201f  mov     rdx, [rsp+278h+var_150]
0x140322027  mov     rcx, r14
0x14032202a  call    InitializeVcbFromBootSector
0x14032202f  mov     r8, [rsp+278h+var_1D0]
0x140322037  mov     r8, [r8]
0x14032203a  test    [r8+30h], r12d
0x14032203e  jz      short loc_140322057
0x140322040  inc     dword ptr [r14+0E8h]
0x140322047  mov     eax, cs:dword_1402612AC
0x14032204d  bts     eax, 14h
0x140322051  mov     cs:dword_1402612AC, eax
0x140322057  mov     r8b, 1; unsigned __int8
0x14032205a  mov     rdx, r14; struct _VCB *
0x14032205d  mov     rcx, r13; struct _IRP_CONTEXT *
0x140322060  call    ?RefsFillVcbVolumeName@@YAJPEAU_IRP_CONTEXT@@PEAU_VCB@@E@Z; RefsFillVcbVolumeName(_IRP_CONTEXT *,_VCB *,uchar)
  ... truncated ...
```
