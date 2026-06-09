# RefsReadRawEncrypted(_IRP_CONTEXT *,_IRP *)

- ea: `0x14028aa64`
- end: `0x14028c1b4`
- name: `?RefsReadRawEncrypted@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `5968`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x140320e78`

## callees

- `0x140038f80`
- `0x1400409a0`
- `0x140041b40`
- `0x140080b90`
- `0x140080c00`
- `0x140081670`
- `0x140087ee0`
- `0x14008dbd0`
- `0x14008f8b0`
- `0x140090040`
- `0x140096fd0`
- `0x1400ac034`
- `0x1400ca788`
- `0x1400e1384`
- `0x1400e2980`
- `0x1400e2c04`
- `0x1400efd0c`
- `0x1400f9854`
- `0x1401e9ce0`
- `0x1401ea140`
- `0x14028aa64`
- `0x14033b8d0`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x14028bcf4`
- `ntoskrnl!IoFreeIrp` at `0x14028c042`
- `ntoskrnl!IoFreeIrp` at `0x1403426a7`
- `ntoskrnl!IoFreeIrp` at `0x14028bcf4`
- `ntoskrnl!IoFreeIrp` at `0x14028c042`
- `ntoskrnl!IoFreeIrp` at `0x1403426a7`
- `ntoskrnl!IoFreeMdl` at `0x14028bcd5`
- `ntoskrnl!IoFreeMdl` at `0x14028c033`
- `ntoskrnl!IoFreeMdl` at `0x140342697`
- `ntoskrnl!IoFreeMdl` at `0x14028bcd5`
- `ntoskrnl!IoFreeMdl` at `0x14028c033`
- `ntoskrnl!IoFreeMdl` at `0x140342697`
- `ntoskrnl!MmUnlockPages` at `0x14028bcb8`
- `ntoskrnl!MmUnlockPages` at `0x14028c023`
- `ntoskrnl!MmUnlockPages` at `0x140342686`
- `ntoskrnl!MmUnlockPages` at `0x14028bcb8`
- `ntoskrnl!MmUnlockPages` at `0x14028c023`
- `ntoskrnl!MmUnlockPages` at `0x140342686`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14028b8f3`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14028b8f3`
- `ntoskrnl!ProbeForRead` at `0x14028adf4`
- `ntoskrnl!ProbeForRead` at `0x14028adf4`
- `ntoskrnl!ProbeForWrite` at `0x14028ae08`
- `ntoskrnl!ProbeForWrite` at `0x14028ae08`
- `ntoskrnl!CcFlushCache` at `0x14028b626`
- `ntoskrnl!CcFlushCache` at `0x14028b626`

## pseudocode

```c
__int64 __fastcall RefsReadRawEncrypted(struct _IRP_CONTEXT *a1, PIRP Irp)
{
  ULONG v4; // r15d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int v6; // ebx
  unsigned int v7; // r9d
  unsigned int *p_NamedPipeType; // rsi
  unsigned int Options; // r12d
  union _LARGE_INTEGER *v11; // r14
  PIRP v12; // r13
  unsigned int v13; // edi
  unsigned int v14; // ebx
  __int64 v15; // rbx
  __int64 v16; // rsi
  struct _IRP_CONTEXT *v17; // r12
  __int64 v18; // r10
  __int16 v19; // dx
  __int64 v20; // r13
  int v21; // ecx
  int v22; // r11d
  signed __int64 v23; // r9
  int v24; // eax
  char v25; // dl
  ULONG i; // eax
  int v27; // eax
  __int64 v28; // r12
  IRP *v29; // rbx
  char v30; // cl
  __int64 v31; // r8
  char v32; // r12
  ULONG j; // eax
  __int64 v34; // rax
  char v35; // cl
  __int64 v36; // rdx
  LONGLONG v37; // r9
  char v38; // r8
  union _LARGE_INTEGER v39; // r8
  int v40; // edx
  union _LARGE_INTEGER v41; // r9
  unsigned int v42; // r12d
  unsigned int v43; // eax
  unsigned int v44; // r9d
  LONGLONG v45; // rcx
  LONGLONG v46; // r8
  __int16 v47; // r9
  __int64 v48; // rcx
  unsigned int v49; // r12d
  LONG *v50; // rsi
  PIRP v51; // rbx
  unsigned __int8 v52; // r8
  int v53; // r9d
  bool v54; // r8
  __int64 v55; // rbx
  int v56; // r10d
  __int64 v57; // rdx
  ULONG v58; // esi
  __int16 v59; // cx
  char *v60; // r11
  char v61; // al
  signed __int64 v62; // rsi
  char v63; // dl
  ULONG k; // r15d
  __int64 v65; // rcx
  LONGLONG v66; // r8
  PIRP v67; // rax
  struct _IRP_CONTEXT *v68; // rcx
  struct _IRP_CONTEXT *v69; // rcx
  __int64 Information_low; // r8
  __int64 v71; // r9
  char v72; // r11
  LONGLONG v73; // r9
  union _LARGE_INTEGER v74; // rcx
  union _LARGE_INTEGER v75; // rdx
  PIRP v76; // rcx
  ULONG_PTR Information; // rdx
  signed __int64 v78; // rcx
  int v79; // eax
  PIRP v80; // rax
  struct _MDL *MdlAddress; // rcx
  unsigned int v82; // r9d
  int v83; // eax
  bool v84; // cf
  struct _MDL *v85; // rcx
  char v86; // [rsp+91h] [rbp-4B7h]
  char v87; // [rsp+92h] [rbp-4B6h]
  char v88; // [rsp+93h] [rbp-4B5h]
  char v89; // [rsp+94h] [rbp-4B4h] BYREF
  char v90; // [rsp+95h] [rbp-4B3h]
  int v91; // [rsp+98h] [rbp-4B0h]
  int v92; // [rsp+9Ch] [rbp-4ACh]
  union _LARGE_INTEGER FileOffset; // [rsp+A0h] [rbp-4A8h] BYREF
  char v94; // [rsp+A8h] [rbp-4A0h]
  int v95; // [rsp+ACh] [rbp-49Ch]
  PIRP v96; // [rsp+B0h] [rbp-498h]
  ULONG v97; // [rsp+B8h] [rbp-490h]
  size_t Size; // [rsp+BCh] [rbp-48Ch]
  __int64 v99; // [rsp+C8h] [rbp-480h] BYREF
  PIRP Irpa; // [rsp+D0h] [rbp-478h]
  struct _IRP_CONTEXT *v101; // [rsp+D8h] [rbp-470h]
  int v102; // [rsp+E0h] [rbp-468h]
  unsigned int v103; // [rsp+E4h] [rbp-464h]
  int v104; // [rsp+E8h] [rbp-460h]
  struct _IRP_CONTEXT *v105; // [rsp+F0h] [rbp-458h]
  signed __int64 v106; // [rsp+F8h] [rbp-450h]
  ULONG Length[2]; // [rsp+100h] [rbp-448h]
  __int64 v108; // [rsp+108h] [rbp-440h] BYREF
  __int64 v109; // [rsp+110h] [rbp-438h] BYREF
  unsigned int v110[2]; // [rsp+118h] [rbp-430h] BYREF
  LONGLONG QuadPart; // [rsp+120h] [rbp-428h]
  int v112; // [rsp+128h] [rbp-420h]
  union _LARGE_INTEGER v113; // [rsp+130h] [rbp-418h]
  LONGLONG v114; // [rsp+138h] [rbp-410h]
  signed __int64 v115; // [rsp+140h] [rbp-408h]
  int v116; // [rsp+148h] [rbp-400h]
  signed __int64 v117; // [rsp+150h] [rbp-3F8h]
  __int128 v118; // [rsp+160h] [rbp-3E8h]
  __int128 v119; // [rsp+170h] [rbp-3D8h] BYREF
  __int128 v120; // [rsp+180h] [rbp-3C8h] BYREF
  __int128 v121; // [rsp+190h] [rbp-3B8h]
  __int128 v122; // [rsp+1A0h] [rbp-3A8h] BYREF
  _BYTE v123[128]; // [rsp+1B0h] [rbp-398h] BYREF
  __int128 v124; // [rsp+230h] [rbp-318h]

  v96 = Irp;
  v105 = a1;
  v101 = a1;
  v4 = 0;
  v99 = 0;
  v108 = 0;
  v109 = 0;
  *(_QWORD *)v110 = 0;
  FileOffset.QuadPart = 0;
  v113.QuadPart = 0;
  QuadPart = 0;
  v102 = 0;
  v124 = 0;
  *(_QWORD *)&v119 = 1;
  v89 = 1;
  v120 = 0;
  Length[1] = 0;
  Length[0] = Feature_ReFS_EFS__private_featureState;
  if ( (Feature_ReFS_EFS__private_featureState & 0x10) == 0 )
  {
    HIDWORD(v106) = Length[1];
    LODWORD(v106) = Feature_ReFS_EFS__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(Feature_ReFS_EFS__private_descriptor, v106, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v106, 3, Feature_ReFS_EFS__private_descriptor);
  }
  *((_QWORD *)a1 + 1) |= 1uLL;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_QWORD *)&v118 = CurrentStackLocation->FileObject;
  if ( (unsigned __int8)RefsDecodeFileObject(a1, v118, &v99, &v108, &v109, v110, 1) != 2 )
  {
    v6 = -1073741811;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741811);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v6;
    v7 = 2342;
LABEL_10:
    RefsStatusDebug(v6, 0, "Efssup.c", v7);
    return v6;
  }
  if ( (*(_WORD *)(*(_QWORD *)v110 + 88LL) & 9) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqZqiiiZD(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        v99 + 6152,
        (unsigned int)KeGetCurrentThread(),
        v99,
        v99 + 6152,
        v108,
        *(_QWORD *)(*(_QWORD *)(v108 + 88) + 256LL),
        *(_QWORD *)(*(_QWORD *)(v108 + 88) + 248LL),
        *(_QWORD *)(v108 + 336),
        *(_QWORD *)v110 + 16LL,
        *(unsigned __int16 *)(*(_QWORD *)v110 + 88LL));
    }
    v6 = -1073741790;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)a1, Irp, -1073741790);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225506LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return v6;
    v7 = 2366;
    goto LABEL_10;
  }
  p_NamedPipeType = &CurrentStackLocation->Parameters.CreatePipe.Parameters->NamedPipeType;
  Options = CurrentStackLocation->Parameters.Create.Options;
  v11 = (union _LARGE_INTEGER *)RefsMapUserBuffer(Irp, v110[0]);
  if ( Options < 0x10 )
    goto LABEL_228;
  v12 = 0;
  Irpa = 0;
  v106 = 0;
  v13 = 0;
  v91 = 0;
  v92 = 0;
  v110[0] = 0;
  *(_QWORD *)Length = 0;
  v95 = 0;
  LODWORD(v108) = 0;
  v87 = 0;
  v88 = 0;
  v86 = 0;
  v90 = 0;
  v14 = CurrentStackLocation->Parameters.Read.Length;
  Size = v14;
  if ( v14 < 0x30 )
  {
LABEL_228:
    v13 = -1073741789;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v105, v96, -1073741789);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225507LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789, 0, "Efssup.c", 0x954u);
    return v13;
  }
  if ( v96->RequestorMode )
  {
    ProbeForRead(p_NamedPipeType, Options, 1u);
    ProbeForWrite(v11, v14, 1u);
  }
  v15 = *(_QWORD *)p_NamedPipeType;
  v117 = *(_QWORD *)p_NamedPipeType;
  v16 = p_NamedPipeType[2];
  v102 = v16;
  memset(v11, 0, (unsigned int)Size);
  v17 = v105;
  *((_DWORD *)v105 + 1) |= 0x10000u;
  RefsAcquireFcbWithPaging(v17, *(_QWORD *)(v109 + 136), v109, 0);
  v18 = v109;
  v19 = *(_WORD *)(v109 + 256);
  if ( (v19 & 0x4000) == 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v13 = -1073740633;
    }
    else
    {
      v13 = -1073740633;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226663LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_209;
    v82 = 2434;
    goto LABEL_208;
  }
  if ( v15 >= *(_QWORD *)(v109 + 32) || v15 >= *(_QWORD *)(v109 + 24) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v13 = -1073741807;
    }
    else
    {
      v13 = -1073741807;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225489LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_209;
    v82 = 2446;
    goto LABEL_208;
  }
  if ( v15 >= 0 && (_DWORD)v16 )
  {
    v20 = v99;
    v21 = *(_DWORD *)(v99 + 276);
    v22 = v21 - 1;
    LODWORD(v99) = v21 - 1;
    v23 = ~(unsigned __int64)(unsigned int)(v21 - 1) & ((unsigned int)(v21 - 1) + *(_QWORD *)(v109 + 40));
    v117 = v23;
    if ( v15 >= v23 )
    {
      if ( v19 >= 0 || (v24 = *(_DWORD *)(v20 + 544), (v24 & (unsigned int)v15) != 0) )
        v4 = -v21 & (v16 + v21 - 1);
      else
        v4 = *(_DWORD *)(v20 + 548) & (v24 + v16);
      v92 = v4;
      v25 = 0;
      for ( i = v4 - 1; ; i >>= 1 )
      {
        v97 = i;
        if ( !i )
          break;
        ++v25;
      }
      v27 = 1 << v25;
      v28 = (unsigned int)(1 << v25);
      v102 = 1 << v25;
      v11->QuadPart = v15;
      v11[1].LowPart = 48;
      if ( v28 >= *(_QWORD *)(v18 + 32) - v15 )
        v27 = *(_DWORD *)(v18 + 32) - v15;
      v11[1].HighPart = v27;
      v11[2].LowPart = 0;
      WORD2(v11[2].QuadPart) = 0;
      BYTE6(v11[2].QuadPart) = v25;
      HIBYTE(v11[2].QuadPart) = v25;
      LOBYTE(v11[3].LowPart) = *(_BYTE *)(v20 + 552);
      BYTE1(v11[3].LowPart) = 1;
      HIWORD(v11[3].u.LowPart) = 1;
      v11[4].LowPart = 1146378309;
      v11[4].HighPart = 16;
      if ( *(__int16 *)(v18 + 256) < 0 )
      {
        LODWORD(v28) = (*(_DWORD *)(v20 + 544) & (unsigned int)v15) != 0 ? v28 : 0;
        v102 = v28;
        v11[5].LowPart = 1;
        if ( *(_DWORD *)(v20 + 552) == 12 )
        {
          v11[5].LowPart = 5;
          BYTE1(v11[3].LowPart) = 3;
        }
        else
        {
          BYTE1(v11[3].LowPart) = 2;
        }
      }
      if ( (int)v28 + 48 > (unsigned int)Size )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            56,
            WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            3221225507LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741789, 0, "Efssup.c", 0xA40u);
        v91 = -1073741789;
      }
      v11[3].HighPart = v28;
      v29 = v96;
      v96->IoStatus.Information = (unsigned int)(v28 + 48);
      v13 = 0;
      v91 = 0;
      v12 = Irpa;
      v17 = v105;
      goto LABEL_210;
    }
    if ( v15 + v16 <= v23 )
    {
      v30 = 0;
    }
    else
    {
      LODWORD(v16) = v23 - v15;
      v102 = v23 - v15;
      v30 = 1;
      v87 = 1;
      v94 = 1;
    }
    if ( *(__int16 *)(v109 + 256) >= 0 )
    {
      WORD2(v11[2].QuadPart) = 0;
      v31 = v15 & -(__int64)*(int *)(v20 + 276);
      FileOffset.QuadPart = v31;
      v4 = ~(*(_DWORD *)(v20 + 276) - 1) & (v16 + v15 + *(_DWORD *)(v20 + 276) - 1 - v31);
      v92 = v4;
      v32 = 0;
      for ( j = v4 - 1; ; j >>= 1 )
      {
        v97 = j;
        if ( !j )
          break;
        ++v32;
      }
      if ( !v30 )
      {
        v4 = 1 << v32;
        v92 = 1 << v32;
        if ( v31 + (unsigned int)(1 << v32) > v23 )
        {
          v4 = v23 - v31;
          v92 = v23 - v31;
          v87 = 1;
          v94 = 1;
        }
      }
      v34 = *(_QWORD *)(v18 + 144);
      v35 = *(_BYTE *)(v34 + 552);
      v36 = *(unsigned int *)(v34 + 544);
      *(_QWORD *)&v121 = v31 >> v35;
      *((_QWORD *)&v121 + 1) = (v4 + v36) >> v35;
      v122 = v121;
      RefsIsRangeValid(v105, v18, &v122, &v89);
      if ( !v89 )
      {
        v38 = 1;
        v86 = 1;
        v18 = v109;
        v22 = v99;
        goto LABEL_70;
      }
      LOWORD(v95) = 1;
      *(_QWORD *)Length = v4;
      v104 = v4;
      v18 = v109;
      v37 = FileOffset.QuadPart + (1LL << v32);
      if ( v37 >= *(_QWORD *)(v109 + 32) )
        v37 = *(_QWORD *)(v109 + 32);
      QuadPart = v37;
      v114 = v37;
      v106 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v20 + 276) - 1)
           & ((unsigned int)(*(_DWORD *)(v20 + 276) - 1) + v37);
      v115 = v106;
      BYTE6(v11[2].QuadPart) = v32;
      HIBYTE(v11[2].QuadPart) = v32;
      v22 = v99;
    }
    v38 = 0;
LABEL_70:
    if ( !v38 && *(__int16 *)(v18 + 256) >= 0 )
      goto LABEL_90;
    WORD2(v11[2].QuadPart) = 0;
    v39.QuadPart = v15 & -(__int64)*(int *)(v20 + 276);
    FileOffset = v39;
    v4 = ~(*(_DWORD *)(v20 + 276) - 1) & (v15 + *(_DWORD *)(v20 + 276) - 1 + v16 - v39.LowPart);
    v92 = v4;
    v40 = *(_DWORD *)(v20 + 548);
    v41.QuadPart = (unsigned int)v15 & v40;
    v113 = v41;
    QuadPart = v41.QuadPart;
    v42 = v40 & (v16 + v15 + *(_DWORD *)(v20 + 544) - v41.LowPart);
    v110[0] = v42;
    v43 = v42 >> *(_DWORD *)(v20 + 552);
    if ( !(_WORD)v43 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v13 = -1073740631;
      }
      else
      {
        v13 = -1073740631;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            58,
            WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            3221226665LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v44 = 2807;
LABEL_184:
        RefsStatusDebug(v13, 0, "Efssup.c", v44);
        goto LABEL_185;
      }
      goto LABEL_185;
    }
    LOWORD(v95) = v42 >> *(_DWORD *)(v20 + 552);
    if ( (unsigned __int16)v43 > (unsigned __int16)v119 )
      goto LABEL_84;
    if ( v87 )
    {
      v103 = (~v22 & (v22 + (_DWORD)v11 + 32)) - (_DWORD)v11;
      if ( v103 + v42 <= (unsigned int)Size )
      {
LABEL_84:
        FileOffset.QuadPart = (unsigned int)v15 & v40;
        v4 = v42;
        v92 = v42;
        v39 = FileOffset;
LABEL_87:
        v45 = v39.QuadPart + v4;
        v46 = v4 + v41.QuadPart;
        if ( v45 >= *(_QWORD *)(v18 + 32) )
          v46 = *(_QWORD *)(v18 + 32);
        QuadPart = v46;
        v114 = v46;
        v106 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v20 + 276) - 1)
             & (v46 + (unsigned int)(*(_DWORD *)(v20 + 276) - 1));
        v115 = v106;
        BYTE6(v11[2].QuadPart) = *(_BYTE *)(v20 + 552);
        HIBYTE(v11[2].QuadPart) = *(_BYTE *)(v20 + 552);
        v38 = v86;
LABEL_90:
        v47 = v95;
        v48 = (unsigned __int16)v95;
        v49 = (~v22 & (v22 + 4 * (unsigned __int16)v95 + 44 + (_DWORD)v11)) - (_DWORD)v11;
        v103 = v49;
        if ( v49 <= (unsigned int)Size
          && (*(__int16 *)(v18 + 256) < 0 || v4 + v49 >= v49 && v4 + v49 <= (unsigned int)Size) )
        {
          *(&v11[3].HighPart + (unsigned __int16)v95) = 1146378309;
          *(&v11[4].LowPart + v48) = 16;
          v50 = &v11[4].HighPart + v48;
          if ( *(__int16 *)(v18 + 256) < 0 )
          {
            *v50 = 1;
            if ( *(_DWORD *)(v20 + 552) == 12 )
              *v50 = 5;
          }
          if ( v38 )
            *v50 |= 2u;
          v11[1].LowPart = v49;
          HIWORD(v11[3].u.LowPart) = v47;
          if ( (*(_DWORD *)(v18 + 300) & 0x4000) == 0 )
          {
            v51 = v96;
            CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(v118 + 40), &FileOffset, v4, &v96->IoStatus);
            RefsNormalizeAndCleanupTransaction(v105, (int *)&v51->IoStatus.0, v52, v53);
            *v11 = FileOffset;
            LOBYTE(v11[3].LowPart) = *(_BYTE *)(v20 + 552);
            BYTE1(v11[3].LowPart) = (*v50 & 6) != 0 ? 3 : 1;
            v51->IoStatus.Information = v11[1].LowPart;
            RefsInitializeIoContext(v105, (struct REFS_IO_CONTEXT *)v123, v54, 0);
            v55 = v109;
            RefsAcquireRangeLock(
              v105,
              *(struct _SCB_NONPAGED **)(v109 + 248),
              FileOffset.QuadPart,
              v4,
              0,
              (struct _RANGE_LOCK_STATE *)&v120);
            v90 = 1;
            LOWORD(v56) = 0;
            LODWORD(v99) = 0;
            v57 = FileOffset.QuadPart;
            v58 = Length[0];
            while ( 1 )
            {
              v59 = v95;
              if ( (unsigned __int16)v56 >= (unsigned __int16)v95 )
              {
                v11[1].HighPart = QuadPart - v11->LowPart;
                v11[2].LowPart = v108;
                goto LABEL_186;
              }
              v60 = (char *)v11 + v49;
              *(_QWORD *)Length = v60;
              if ( *(__int16 *)(v55 + 256) < 0 || (v61 = v86) != 0 )
              {
                v62 = v57 + *(unsigned int *)(v20 + 272);
                if ( v106 < v62 )
                  LODWORD(v62) = v106;
                v58 = v62 - v57;
                v104 = v58;
                *(_QWORD *)&v118 = v57 >> *(_BYTE *)(v20 + 552);
                *((_QWORD *)&v118 + 1) = 1;
                v119 = v118;
                RefsIsRangeValid(v105, v55, &v119, &v89);
                v57 = FileOffset.QuadPart;
                LOWORD(v56) = v99;
                v60 = *(char **)Length;
                v59 = v95;
                v61 = v86;
              }
              if ( v89 )
              {
                if ( *(__int16 *)(v55 + 256) < 0 || v61 )
                {
                  if ( v59 == 1 && (v57 != v113.QuadPart || v4 != v110[0]) )
                  {
                    v63 = 0;
                    for ( k = v4 - 1; ; k >>= 1 )
                    {
                      v97 = k;
                      if ( !k )
                        break;
                      ++v63;
                    }
                    v65 = (unsigned int)(1 << v63);
                    v4 = 1 << v63;
                    v92 = 1 << v63;
                    v58 = 1 << v63;
                    v104 = 1 << v63;
                    BYTE6(v11[2].QuadPart) = v63;
                    HIBYTE(v11[2].QuadPart) = v63;
                    v57 = FileOffset.QuadPart;
                    v66 = v65 + FileOffset.QuadPart;
                    if ( v65 + FileOffset.QuadPart >= *(_QWORD *)(v55 + 32) )
                      v66 = *(_QWORD *)(v55 + 32);
                    QuadPart = v66;
                    v114 = v66;
                    v106 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v20 + 276) - 1)
                         & (v66 + (unsigned int)(*(_DWORD *)(v20 + 276) - 1));
                    v115 = v106;
                  }
                  if ( v57 + v58 > v117 )
                  {
                    v58 = v117 - v57;
                    v104 = v117 - v57;
                  }
                  if ( v58 + v49 < v49 || v58 + v49 > (unsigned int)Size )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
                    {
                      v13 = -1073741789;
                    }
                    else
                    {
                      v13 = -1073741789;
                      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          61,
                          WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
                          3221225507LL);
                    }
                    if ( (_BYTE)RefsStatusDebugEnabled )
                    {
                      v44 = 3140;
                      goto LABEL_184;
                    }
                    goto LABEL_185;
                  }
                }
                v67 = IoBuildAsynchronousFsdRequest(
                        3u,
                        *(PDEVICE_OBJECT *)(*(_QWORD *)(v20 + 208) + 8LL),
                        v60,
                        v58,
                        &FileOffset,
                        0);
                Irpa = v67;
                if ( !v67 )
                {
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
                  {
                    v13 = -1073741670;
                  }
                  else
                  {
                    v13 = -1073741670;
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        62,
                        WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
                        3221225626LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                  {
                    v44 = 3161;
                    goto LABEL_184;
                  }
                  goto LABEL_185;
                }
                --v67->CurrentLocation;
                --v67->Tail.Overlay.CurrentStackLocation;
                v68 = *(struct _IRP_CONTEXT **)(*(_QWORD *)(v20 + 208) + 8LL);
                v67->Tail.Overlay.CurrentStackLocation->DeviceObject = (PDEVICE_OBJECT)v68;
                v67->UserBuffer = *(PVOID *)Length;
                RefsLockUserBuffer(v68, v67, IoWriteAccess, v58);
                v88 = 1;
                v69 = v105;
                *((_BYTE *)v105 + 40) = 3;
                RefsNonCachedIo((__int64)v69, (__int64)v123, Irpa, v55, FileOffset.QuadPart, v58, 2u);
                Information_low = LODWORD(Irpa->IoStatus.Information);
                v96->IoStatus.Information += Information_low;
                v71 = 4LL * (unsigned __int16)v99 + 28;
                *(DWORD *)((char *)&v11->LowPart + v71) = Information_low;
                v49 += Information_low;
                v103 = v49;
                v72 = 0;
              }
              else
              {
                LODWORD(Information_low) = *(_DWORD *)(v20 + 272);
                v58 = Information_low;
                v104 = Information_low;
                v72 = 1;
                if ( v59 == 1 && (v57 != v113.QuadPart || v4 != v110[0]) )
                {
                  FileOffset = v113;
                  *v11 = v113;
                  v4 = v110[0];
                  v92 = v110[0];
                  v73 = FileOffset.QuadPart + v110[0];
                  if ( v73 >= *(_QWORD *)(v55 + 32) )
                    v73 = *(_QWORD *)(v55 + 32);
                  QuadPart = v73;
                  v114 = v73;
                  v106 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v20 + 276) - 1)
                       & (v73 + (unsigned int)(*(_DWORD *)(v20 + 276) - 1));
                  v115 = v106;
                }
                v71 = 4LL * (unsigned __int16)v56 + 28;
                *(DWORD *)((char *)&v11->LowPart + v71) = 0;
              }
              v74 = *(union _LARGE_INTEGER *)(v55 + 32);
              v75 = FileOffset;
              if ( (unsigned int)Information_low + FileOffset.QuadPart <= v74.QuadPart )
              {
                HIDWORD(Size) += Information_low;
                v116 = HIDWORD(Size);
              }
              else
              {
                if ( FileOffset.QuadPart < v74.QuadPart )
                {
                  HIDWORD(Size) += v74.LowPart - FileOffset.LowPart;
                  v116 = HIDWORD(Size);
                }
                if ( *(__int16 *)(v55 + 256) >= 0 && !v86 )
                {
                  v76 = v96;
                  v96->IoStatus.Information -= *(unsigned int *)((char *)&v11->LowPart + v71);
                  Information = v76->IoStatus.Information;
                  LODWORD(v76) = ~(*(_DWORD *)(v20 + 276) - 1) & (*(_DWORD *)(v20 + 276) - 1 + HIDWORD(Size));
                  v96->IoStatus.Information = Information + (unsigned int)v76;
                  *(DWORD *)((char *)&v11->LowPart + v71) = (unsigned int)v76;
                  v75 = FileOffset;
                }
              }
              v78 = *(_QWORD *)(v55 + 40);
              if ( (unsigned int)Information_low + v75.QuadPart <= v78 )
              {
                LODWORD(v108) = Information_low + v108;
                v112 = v108;
              }
              else if ( v78 > v75.QuadPart )
              {
                if ( (_WORD)v95 == 1 && !v72 )
                {
                  v79 = ((v78 + 511) & 0xFFFFFE00) - v75.LowPart;
                  if ( v79 > 0 && v79 < (unsigned int)Information_low )
                  {
                    memset((void *)(*(_QWORD *)Length + v79), 0, (unsigned int)(Information_low - v79));
                    v75 = FileOffset;
                  }
                }
                LODWORD(v108) = *(_DWORD *)(v55 + 40) - v75.LowPart + v108;
                v112 = v108;
              }
              v57 = v58 + v75.QuadPart;
              FileOffset.QuadPart = v57;
              v80 = Irpa;
              if ( Irpa )
              {
                MdlAddress = Irpa->MdlAddress;
                if ( MdlAddress )
                {
                  if ( v88 )
                  {
                    MmUnlockPages(MdlAddress);
                    v88 = 0;
                    v80 = Irpa;
                  }
                  IoFreeMdl(v80->MdlAddress);
                  v80 = Irpa;
                  Irpa->MdlAddress = 0;
                }
                IoFreeIrp(v80);
                Irpa = 0;
                v57 = FileOffset.QuadPart;
              }
              HIWORD(v56) = WORD1(v99);
              LOWORD(v56) = v99 + 1;
              LODWORD(v99) = v56;
            }
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
          {
            v13 = -1073741202;
          }
          else
          {
            v13 = -1073741202;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                60,
                WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
                3221226094LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_185;
          v44 = 2976;
          goto LABEL_184;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
        {
          v13 = -1073741789;
        }
        else
        {
          v13 = -1073741789;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              59,
              WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
              3221225507LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v44 = 2926;
          goto LABEL_184;
        }
LABEL_185:
        v91 = v13;
LABEL_186:
        v12 = Irpa;
        v17 = v105;
        v29 = v96;
        goto LABEL_210;
      }
      v39.QuadPart = v15 & v40;
      FileOffset = v39;
      v4 = *(_DWORD *)(v20 + 548) & (v15 + *(_DWORD *)(v20 + 544) + v16 - v39.LowPart);
      v92 = v4;
    }
    v41 = v39;
    goto LABEL_87;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
  {
    v13 = -1073740631;
  }
  else
  {
    v13 = -1073740631;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226665LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v82 = 2456;
LABEL_208:
    RefsStatusDebug(v13, 0, "Efssup.c", v82);
  }
LABEL_209:
  v91 = v13;
  v29 = v96;
LABEL_210:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    v83 = 0;
    v84 = (v13 & 0x80000000) != 0 ? BYTE1(WPP_GLOBAL_Control->Timer) < 4u : BYTE1(WPP_GLOBAL_Control->Timer) < 5u;
    LOBYTE(v83) = !v84;
    if ( v83 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, v13);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(v13, 0, "Efssup.c", 0xD4Du);
  RefsCleanupIoContext(v17, (struct REFS_IO_CONTEXT *)v123, v13);
  if ( v12 )
  {
    v85 = v12->MdlAddress;
    if ( v85 )
    {
      if ( v88 )
        MmUnlockPages(v85);
      IoFreeMdl(v12->MdlAddress);
    }
    IoFreeIrp(v12);
  }
  if ( v90 )
    RefsReleaseRangeLock(
      *(struct _SCB_NONPAGED **)(v109 + 248),
      FileOffset.QuadPart,
      v4,
      0,
      (struct _RANGE_LOCK_STATE *)&v120);
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v17, v29, v13);
  return v13;
}

```

## disassembly

```asm
0x14028aa64  mov     r11, rsp
0x14028aa67  mov     [r11+18h], rbx
0x14028aa6b  mov     [r11+20h], rsi
0x14028aa6f  push    rdi
0x14028aa70  push    r12
0x14028aa72  push    r13
0x14028aa74  push    r14
0x14028aa76  push    r15
0x14028aa78  sub     rsp, 4F0h
0x14028aa7f  mov     rax, cs:__security_cookie
0x14028aa86  xor     rax, rsp
0x14028aa89  mov     [rsp+518h+var_38], rax
0x14028aa91  mov     r14, rdx
0x14028aa94  mov     [rsp+518h+var_498], rdx
0x14028aa9c  mov     rdi, rcx
0x14028aa9f  mov     [rsp+518h+var_458], rcx
0x14028aaa7  mov     [rsp+518h+var_470], rcx
0x14028aaaf  xor     r15d, r15d
0x14028aab2  mov     [r11-480h], r15
0x14028aab9  mov     [r11-440h], r15
0x14028aac0  mov     [r11-438h], r15
0x14028aac7  mov     [r11-430h], r15
0x14028aace  mov     qword ptr [rsp+518h+FileOffset], r15
0x14028aad3  mov     [r11-418h], r15
0x14028aada  mov     [r11-428h], r15
0x14028aae1  mov     [r11-468h], r15d
0x14028aae8  xorps   xmm0, xmm0
0x14028aaeb  movdqu  [rsp+518h+var_318], xmm0
0x14028aaf4  lea     esi, [r15+1]
0x14028aaf8  mov     qword ptr [rsp+518h+var_3D8], rsi
0x14028ab00  mov     [rsp+518h+var_4B4], sil
0x14028ab05  movups  [rsp+518h+var_3C8], xmm0
0x14028ab0d  mov     [r11-448h], r15
0x14028ab14  mov     ecx, cs:Feature_ReFS_EFS__private_featureState
0x14028ab1a  mov     [rsp+518h+Length], ecx
0x14028ab21  test    cl, 10h
0x14028ab24  jnz     short loc_14028AB6C
0x14028ab26  mov     rax, qword ptr [rsp+518h+Length]
0x14028ab2e  mov     [r11-450h], rax
0x14028ab35  or      ecx, esi
0x14028ab37  mov     dword ptr [rsp+518h+var_450], ecx
0x14028ab3e  lea     r8d, [r15+3]
0x14028ab42  mov     rdx, [r11-450h]
0x14028ab49  lea     rcx, Feature_ReFS_EFS__private_descriptor
0x14028ab50  call    wil_details_FeatureReporting_ReportUsageToService
0x14028ab55  lea     r8, Feature_ReFS_EFS__private_descriptor
0x14028ab5c  lea     edx, [rsi+2]
0x14028ab5f  mov     rcx, [rsp+518h+var_450]
0x14028ab67  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x14028ab6c  or      [rdi+8], rsi
0x14028ab70  mov     rbx, [r14+0B8h]
0x14028ab77  mov     rax, [rbx+30h]
0x14028ab7b  mov     qword ptr [rsp+518h+var_3E8], rax
0x14028ab83  mov     byte ptr [rsp+518h+var_4E8], sil
0x14028ab88  lea     rcx, [rsp+518h+var_430]
0x14028ab90  mov     [rsp+518h+IoStatusBlock], rcx
0x14028ab95  lea     rcx, [rsp+518h+var_438]
0x14028ab9d  mov     [rsp+518h+StartingOffset], rcx
0x14028aba2  lea     r9, [rsp+518h+var_440]
0x14028abaa  lea     r8, [rsp+518h+var_480]
0x14028abb2  mov     rdx, rax
0x14028abb5  mov     rcx, rdi
0x14028abb8  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x14028abbd  cmp     al, 2
0x14028abbf  jz      short loc_14028AC35
0x14028abc1  mov     ebx, 0C000000Dh
0x14028abc6  mov     r8d, ebx; Status
0x14028abc9  mov     rdx, r14; Irp
0x14028abcc  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14028abcf  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14028abd4  lea     rsi, WPP_GLOBAL_Control
0x14028abdb  mov     rcx, cs:WPP_GLOBAL_Control
0x14028abe2  cmp     rcx, rsi
0x14028abe5  jz      short loc_14028AC0E
0x14028abe7  test    dword ptr [rcx+2Ch], 100h
0x14028abee  jz      short loc_14028AC0E
0x14028abf0  cmp     byte ptr [rcx+29h], 4
0x14028abf4  jb      short loc_14028AC0E
0x14028abf6  mov     edx, 30h ; '0'
0x14028abfb  mov     r9d, ebx
0x14028abfe  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x14028ac05  mov     rcx, [rcx+18h]
0x14028ac09  call    WPP_SF_d
0x14028ac0e  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028ac14  test    cl, cl
0x14028ac16  jz      short loc_14028AC2E
0x14028ac18  mov     r9d, 926h; unsigned int
0x14028ac1e  lea     r8, aEfssupC; "Efssup.c"
0x14028ac25  xor     edx, edx; struct _IRP_CONTEXT *
0x14028ac27  mov     ecx, ebx; Status
0x14028ac29  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14028ac2e  mov     eax, ebx
0x14028ac30  jmp     loc_14028C186
0x14028ac35  mov     rdx, qword ptr [rsp+518h+var_430]; unsigned int
0x14028ac3d  movzx   r8d, word ptr [rdx+58h]
0x14028ac42  test    r8b, 9
0x14028ac46  jnz     loc_14028AD51
0x14028ac4c  lea     rsi, WPP_GLOBAL_Control
0x14028ac53  mov     rcx, cs:WPP_GLOBAL_Control
0x14028ac5a  cmp     rcx, rsi
0x14028ac5d  jz      loc_14028ACF2
0x14028ac63  test    dword ptr [rcx+2Ch], 10000h
0x14028ac6a  jz      loc_14028ACF2
0x14028ac70  cmp     byte ptr [rcx+29h], 2
0x14028ac74  jb      short loc_14028ACF2
0x14028ac76  mov     rbx, [rsp+518h+var_440]
0x14028ac7e  mov     r10, [rbx+58h]
0x14028ac82  mov     r9, gs:188h
0x14028ac8b  mov     eax, r8d
0x14028ac8e  lea     rcx, [rdx+10h]
0x14028ac92  mov     r11, [rsp+518h+var_480]
0x14028ac9a  lea     r8, [r11+1808h]
0x14028aca1  mov     edx, 31h ; '1'
0x14028aca6  mov     [rsp+518h+var_4C0], eax
0x14028acaa  mov     [rsp+518h+var_4C8], rcx
0x14028acaf  mov     rax, [rbx+150h]
0x14028acb6  mov     [rsp+518h+var_4D0], rax
0x14028acbb  mov     rax, [r10+0F8h]
0x14028acc2  mov     [rsp+518h+var_4D8], rax
0x14028acc7  mov     rax, [r10+100h]
0x14028acce  mov     [rsp+518h+var_4E0], rax
0x14028acd3  mov     [rsp+518h+var_4E8], rbx
0x14028acd8  mov     [rsp+518h+IoStatusBlock], r8
0x14028acdd  mov     [rsp+518h+StartingOffset], r11
0x14028ace2  mov     rcx, cs:WPP_GLOBAL_Control
0x14028ace9  mov     rcx, [rcx+18h]
0x14028aced  call    WPP_SF_qqZqiiiZD
0x14028acf2  mov     ebx, 0C0000022h
0x14028acf7  mov     r8d, ebx; Status
0x14028acfa  mov     rdx, r14; Irp
0x14028acfd  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14028ad00  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x14028ad05  mov     rcx, cs:WPP_GLOBAL_Control
0x14028ad0c  cmp     rcx, rsi
0x14028ad0f  jz      short loc_14028AD38
0x14028ad11  test    dword ptr [rcx+2Ch], 100h
0x14028ad18  jz      short loc_14028AD38
0x14028ad1a  cmp     byte ptr [rcx+29h], 4
0x14028ad1e  jb      short loc_14028AD38
0x14028ad20  mov     edx, 32h ; '2'
0x14028ad25  mov     r9d, ebx
0x14028ad28  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x14028ad2f  mov     rcx, [rcx+18h]
0x14028ad33  call    WPP_SF_d
0x14028ad38  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14028ad3e  test    cl, cl
0x14028ad40  jz      loc_14028AC2E
0x14028ad46  mov     r9d, 93Eh
0x14028ad4c  jmp     loc_14028AC1E
0x14028ad51  mov     rsi, [rbx+20h]
0x14028ad55  mov     r12d, [rbx+10h]
0x14028ad59  mov     rcx, r14; struct _IRP *
0x14028ad5c  call    ?RefsMapUserBuffer@@YAPEAXPEAU_IRP@@K@Z; RefsMapUserBuffer(_IRP *,ulong)
0x14028ad61  mov     r14, rax
0x14028ad64  cmp     r12d, 10h
0x14028ad68  jb      loc_14028C10D
0x14028ad6e  mov     r13, r15
0x14028ad71  mov     [rsp+518h+Irp], r15
0x14028ad79  mov     [rsp+518h+var_450], r15
0x14028ad81  mov     edi, r15d
0x14028ad84  mov     [rsp+518h+var_4B0], r15d
0x14028ad89  mov     [rsp+518h+var_4AC], r15d
0x14028ad8e  xor     ecx, ecx
0x14028ad90  mov     [rsp+518h+var_430], ecx
0x14028ad97  mov     eax, ecx
0x14028ad99  mov     qword ptr [rsp+518h+Length], rax
0x14028ada1  mov     [rsp+518h+var_49C], ecx
0x14028ada5  mov     dword ptr [rsp+518h+var_440], ecx
0x14028adac  mov     dword ptr [rsp+518h+Size+4], ecx
0x14028adb3  mov     [rsp+518h+var_4B6], cl
0x14028adb7  mov     [rsp+518h+var_4B8], cl
0x14028adbb  mov     [rsp+518h+var_4B5], cl
0x14028adbf  mov     [rsp+518h+var_4B7], cl
0x14028adc3  mov     [rsp+518h+var_4B3], cl
0x14028adc7  mov     ebx, [rbx+8]
0x14028adca  mov     dword ptr [rsp+518h+Size], ebx
0x14028add1  cmp     ebx, 30h ; '0'
0x14028add4  jb      loc_14028C10D
0x14028adda  mov     rdx, [rsp+518h+var_498]
0x14028ade2  cmp     [rdx+40h], cl
0x14028ade5  jz      short loc_14028AE14
0x14028ade7  mov     edx, r12d; Length
0x14028adea  lea     r12d, [rcx+1]
0x14028adee  mov     r8d, r12d; Alignment
0x14028adf1  mov     rcx, rsi; Address
0x14028adf4  call    cs:__imp_ProbeForRead
0x14028adfb  nop     dword ptr [rax+rax+00h]
0x14028ae00  mov     edx, ebx; Length
0x14028ae02  mov     r8d, r12d; Alignment
0x14028ae05  mov     rcx, r14; Address
0x14028ae08  call    cs:__imp_ProbeForWrite
0x14028ae0f  nop     dword ptr [rax+rax+00h]
0x14028ae14  mov     rbx, [rsi]
0x14028ae17  mov     [rsp+518h+var_3F8], rbx
0x14028ae1f  mov     esi, [rsi+8]
0x14028ae22  mov     [rsp+518h+var_468], esi
0x14028ae29  mov     r8d, dword ptr [rsp+518h+Size]; Size
0x14028ae31  xor     edx, edx; Val
0x14028ae33  mov     rcx, r14; void *
0x14028ae36  call    memset
0x14028ae3b  nop
0x14028ae3c  mov     r12, [rsp+518h+var_458]
0x14028ae44  bts     dword ptr [r12+4], 10h
0x14028ae4b  xor     r9d, r9d
0x14028ae4e  mov     rcx, [rsp+518h+var_438]
0x14028ae56  mov     r8, rcx
0x14028ae59  mov     rdx, [rcx+88h]
0x14028ae60  mov     rcx, r12
0x14028ae63  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x14028ae68  mov     r10, [rsp+518h+var_438]
0x14028ae70  movzx   edx, word ptr [r10+100h]
0x14028ae78  bt      dx, 0Eh
0x14028ae7d  jnb     loc_14028BF1C
0x14028ae83  cmp     rbx, [r10+20h]
0x14028ae87  jge     loc_14028BEC1
0x14028ae8d  cmp     rbx, [r10+18h]
0x14028ae91  jge     loc_14028BEC1
0x14028ae97  test    rbx, rbx
0x14028ae9a  js      loc_14028BE62
0x14028aea0  test    esi, esi
0x14028aea2  jz      loc_14028BE62
0x14028aea8  mov     r13, [rsp+518h+var_480]
0x14028aeb0  mov     ecx, [r13+114h]
0x14028aeb7  lea     r11d, [rcx-1]
0x14028aebb  mov     dword ptr [rsp+518h+var_480], r11d
0x14028aec3  mov     eax, r11d
0x14028aec6  mov     r9, [r10+28h]
0x14028aeca  add     r9, rax
0x14028aecd  not     rax
0x14028aed0  and     r9, rax
0x14028aed3  mov     [rsp+518h+var_3F8], r9
0x14028aedb  cmp     rbx, r9
0x14028aede  jl      loc_14028B110
0x14028aee4  xor     r11d, r11d
0x14028aee7  test    dx, dx
0x14028aeea  jns     short loc_14028AF04
0x14028aeec  mov     eax, [r13+220h]
0x14028aef3  test    ebx, eax
0x14028aef5  jnz     short loc_14028AF04
0x14028aef7  lea     r15d, [rax+rsi]
0x14028aefb  and     r15d, [r13+224h]
0x14028af02  jmp     short loc_14028AF10
0x14028af04  lea     r15d, [rcx-1]
0x14028af08  add     r15d, esi
0x14028af0b  neg     ecx
0x14028af0d  and     r15d, ecx
0x14028af10  mov     [rsp+518h+var_4AC], r15d
0x14028af15  mov     dl, r11b
0x14028af18  lea     eax, [r15-1]
0x14028af1c  mov     r8d, 1
0x14028af22  mov     [rsp+518h+var_490], eax
0x14028af29  movzx   ecx, dl
0x14028af2c  test    eax, eax
0x14028af2e  jz      short loc_14028AF37
0x14028af30  add     dl, r8b
0x14028af33  shr     eax, 1
0x14028af35  jmp     short loc_14028AF22
0x14028af37  mov     eax, r8d
0x14028af3a  shl     eax, cl
0x14028af3c  mov     r12d, eax
0x14028af3f  mov     [rsp+518h+var_468], r12d
0x14028af47  mov     [r14], rbx
0x14028af4a  mov     dword ptr [r14+8], 30h ; '0'
0x14028af52  mov     rcx, [r10+20h]
0x14028af56  sub     rcx, rbx
0x14028af59  cmp     r12, rcx
0x14028af5c  cmovge  eax, ecx
0x14028af5f  mov     [r14+0Ch], eax
0x14028af63  mov     [r14+10h], r11d
0x14028af67  mov     [r14+14h], r11w
0x14028af6c  mov     [r14+16h], dl
0x14028af70  mov     [r14+17h], dl
0x14028af74  mov     al, [r13+228h]
0x14028af7b  mov     [r14+18h], al
0x14028af7f  mov     [r14+19h], r8b
0x14028af83  mov     [r14+1Ah], r8w
0x14028af88  mov     eax, cs:dword_1402029C4
0x14028af8e  mov     [r14+20h], eax
0x14028af92  mov     dword ptr [r14+24h], 10h
0x14028af9a  cmp     [r10+100h], r11w
0x14028afa2  jge     short loc_14028AFDE
0x14028afa4  and     ebx, [r13+220h]
0x14028afab  neg     ebx
0x14028afad  sbb     eax, eax
0x14028afaf  and     eax, r12d
0x14028afb2  mov     r12d, eax
0x14028afb5  mov     [rsp+518h+var_468], eax
0x14028afbc  mov     [r14+28h], r8d
0x14028afc0  cmp     dword ptr [r13+228h], 0Ch
0x14028afc8  jnz     short loc_14028AFD9
0x14028afca  mov     dword ptr [r14+28h], 5
0x14028afd2  mov     byte ptr [r14+19h], 3
0x14028afd7  jmp     short loc_14028AFDE
0x14028afd9  mov     byte ptr [r14+19h], 2
0x14028afde  lea     eax, [r12+30h]
0x14028afe3  cmp     eax, dword ptr [rsp+518h+Size]
0x14028afea  jbe     short loc_14028B05E
0x14028afec  lea     rsi, WPP_GLOBAL_Control
0x14028aff3  mov     rcx, cs:WPP_GLOBAL_Control
0x14028affa  cmp     rcx, rsi
  ... truncated ...
```
