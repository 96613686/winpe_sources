# RefsReadRawEncrypted(_IRP_CONTEXT *,_IRP *)

- ea: `0x140291a00`
- end: `0x140293150`
- name: `?RefsReadRawEncrypted@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z`
- size: `5968`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp)`
- caller_count: `1`
- callee_count: `22`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x140323dd8`

## callees

- `0x14000cf40`
- `0x14000e0e0`
- `0x14004ffc0`
- `0x140075ff0`
- `0x140076060`
- `0x140076ad0`
- `0x14007cdb0`
- `0x1400862c0`
- `0x1400892a0`
- `0x140089680`
- `0x140090c50`
- `0x1400a73b4`
- `0x1400d0fd8`
- `0x1400e6374`
- `0x1400e7a10`
- `0x1400e7c94`
- `0x1400f5020`
- `0x1400fe714`
- `0x1401f3fb0`
- `0x1401f4400`
- `0x140291a00`
- `0x14033e290`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140292c90`
- `ntoskrnl!IoFreeIrp` at `0x140292fde`
- `ntoskrnl!IoFreeIrp` at `0x140345480`
- `ntoskrnl!IoFreeIrp` at `0x140292c90`
- `ntoskrnl!IoFreeIrp` at `0x140292fde`
- `ntoskrnl!IoFreeIrp` at `0x140345480`
- `ntoskrnl!IoFreeMdl` at `0x140292c71`
- `ntoskrnl!IoFreeMdl` at `0x140292fcf`
- `ntoskrnl!IoFreeMdl` at `0x140345470`
- `ntoskrnl!IoFreeMdl` at `0x140292c71`
- `ntoskrnl!IoFreeMdl` at `0x140292fcf`
- `ntoskrnl!IoFreeMdl` at `0x140345470`
- `ntoskrnl!MmUnlockPages` at `0x140292c54`
- `ntoskrnl!MmUnlockPages` at `0x140292fbf`
- `ntoskrnl!MmUnlockPages` at `0x14034545f`
- `ntoskrnl!MmUnlockPages` at `0x140292c54`
- `ntoskrnl!MmUnlockPages` at `0x140292fbf`
- `ntoskrnl!MmUnlockPages` at `0x14034545f`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14029288f`
- `ntoskrnl!IoBuildAsynchronousFsdRequest` at `0x14029288f`
- `ntoskrnl!ProbeForRead` at `0x140291d90`
- `ntoskrnl!ProbeForRead` at `0x140291d90`
- `ntoskrnl!ProbeForWrite` at `0x140291da4`
- `ntoskrnl!ProbeForWrite` at `0x140291da4`
- `ntoskrnl!CcFlushCache` at `0x1402925c2`
- `ntoskrnl!CcFlushCache` at `0x1402925c2`

## pseudocode

```c
__int64 __fastcall RefsReadRawEncrypted(struct _IRP_CONTEXT *a1, PIRP Irp)
{
  ULONG v4; // r15d
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rbx
  unsigned int v6; // ebx
  unsigned int v7; // r9d
  __int16 v9; // r8
  unsigned int *p_NamedPipeType; // rsi
  unsigned int Options; // r12d
  union _LARGE_INTEGER *v12; // r14
  PIRP v13; // r13
  unsigned int v14; // edi
  unsigned int v15; // ebx
  __int64 v16; // rbx
  __int64 v17; // rsi
  struct _IRP_CONTEXT *v18; // r12
  __int64 v19; // r10
  __int16 v20; // dx
  __int64 v21; // r13
  int v22; // ecx
  int v23; // r11d
  signed __int64 v24; // r9
  int v25; // eax
  char v26; // dl
  ULONG i; // eax
  int v28; // eax
  __int64 v29; // r12
  IRP *v30; // rbx
  char v31; // cl
  __int64 v32; // r8
  char v33; // r12
  ULONG j; // eax
  __int64 v35; // rax
  char v36; // cl
  __int64 v37; // rdx
  LONGLONG v38; // r9
  char v39; // r8
  union _LARGE_INTEGER v40; // r8
  int v41; // edx
  union _LARGE_INTEGER v42; // r9
  unsigned int v43; // r12d
  unsigned int v44; // eax
  unsigned int v45; // r9d
  LONGLONG v46; // rcx
  LONGLONG v47; // r8
  __int16 v48; // r9
  __int64 v49; // rcx
  unsigned int v50; // r12d
  LONG *v51; // rsi
  PIRP v52; // rbx
  unsigned __int8 v53; // r8
  int v54; // r9d
  bool v55; // r8
  __int64 v56; // rbx
  int v57; // r10d
  __int64 v58; // rdx
  ULONG v59; // esi
  __int16 v60; // cx
  char *v61; // r11
  char v62; // al
  signed __int64 v63; // rsi
  char v64; // dl
  ULONG k; // r15d
  __int64 v66; // rcx
  LONGLONG v67; // r8
  PIRP v68; // rax
  struct _IRP_CONTEXT *v69; // rcx
  struct _IRP_CONTEXT *v70; // rcx
  __int64 Information_low; // r8
  __int64 v72; // r9
  char v73; // r11
  LONGLONG v74; // r9
  union _LARGE_INTEGER v75; // rcx
  union _LARGE_INTEGER v76; // rdx
  PIRP v77; // rcx
  ULONG_PTR Information; // rdx
  signed __int64 v79; // rcx
  int v80; // eax
  PIRP v81; // rax
  struct _MDL *MdlAddress; // rcx
  unsigned int v83; // r9d
  int v84; // eax
  bool v85; // cf
  struct _MDL *v86; // rcx
  PLARGE_INTEGER StartingOffset; // [rsp+50h] [rbp-4F8h]
  PIO_STATUS_BLOCK IoStatusBlock; // [rsp+58h] [rbp-4F0h]
  int v89; // [rsp+60h] [rbp-4E8h]
  char v90; // [rsp+91h] [rbp-4B7h]
  char v91; // [rsp+92h] [rbp-4B6h]
  char v92; // [rsp+93h] [rbp-4B5h]
  char v93; // [rsp+94h] [rbp-4B4h] BYREF
  char v94; // [rsp+95h] [rbp-4B3h]
  int v95; // [rsp+98h] [rbp-4B0h]
  int v96; // [rsp+9Ch] [rbp-4ACh]
  union _LARGE_INTEGER FileOffset; // [rsp+A0h] [rbp-4A8h] BYREF
  char v98; // [rsp+A8h] [rbp-4A0h]
  int v99; // [rsp+ACh] [rbp-49Ch]
  PIRP v100; // [rsp+B0h] [rbp-498h]
  ULONG v101; // [rsp+B8h] [rbp-490h]
  size_t Size; // [rsp+BCh] [rbp-48Ch]
  __int64 v103; // [rsp+C8h] [rbp-480h] BYREF
  PIRP Irpa; // [rsp+D0h] [rbp-478h]
  struct _IRP_CONTEXT *v105; // [rsp+D8h] [rbp-470h]
  int v106; // [rsp+E0h] [rbp-468h]
  unsigned int v107; // [rsp+E4h] [rbp-464h]
  int v108; // [rsp+E8h] [rbp-460h]
  struct _IRP_CONTEXT *v109; // [rsp+F0h] [rbp-458h]
  signed __int64 v110; // [rsp+F8h] [rbp-450h]
  ULONG Length[2]; // [rsp+100h] [rbp-448h]
  __int64 v112; // [rsp+108h] [rbp-440h] BYREF
  __int64 v113; // [rsp+110h] [rbp-438h] BYREF
  unsigned int v114[2]; // [rsp+118h] [rbp-430h] BYREF
  LONGLONG QuadPart; // [rsp+120h] [rbp-428h]
  int v116; // [rsp+128h] [rbp-420h]
  union _LARGE_INTEGER v117; // [rsp+130h] [rbp-418h]
  LONGLONG v118; // [rsp+138h] [rbp-410h]
  signed __int64 v119; // [rsp+140h] [rbp-408h]
  int v120; // [rsp+148h] [rbp-400h]
  signed __int64 v121; // [rsp+150h] [rbp-3F8h]
  __int128 v122; // [rsp+160h] [rbp-3E8h]
  __int128 v123; // [rsp+170h] [rbp-3D8h] BYREF
  __int128 v124; // [rsp+180h] [rbp-3C8h] BYREF
  __int128 v125; // [rsp+190h] [rbp-3B8h]
  __int128 v126; // [rsp+1A0h] [rbp-3A8h] BYREF
  _BYTE v127[128]; // [rsp+1B0h] [rbp-398h] BYREF
  __int128 v128; // [rsp+230h] [rbp-318h]

  v100 = Irp;
  v109 = a1;
  v105 = a1;
  v4 = 0;
  v103 = 0;
  v112 = 0;
  v113 = 0;
  *(_QWORD *)v114 = 0;
  FileOffset.QuadPart = 0;
  v117.QuadPart = 0;
  QuadPart = 0;
  v106 = 0;
  v128 = 0;
  *(_QWORD *)&v123 = 1;
  v93 = 1;
  v124 = 0;
  Length[1] = 0;
  Length[0] = Feature_ReFS_EFS__private_featureState;
  if ( (Feature_ReFS_EFS__private_featureState & 0x10) == 0 )
  {
    HIDWORD(v110) = Length[1];
    LODWORD(v110) = Feature_ReFS_EFS__private_featureState | 1;
    wil_details_FeatureReporting_ReportUsageToService(Feature_ReFS_EFS__private_descriptor, v110, 3);
    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath(v110, 3, Feature_ReFS_EFS__private_descriptor);
  }
  *((_QWORD *)a1 + 1) |= 1uLL;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  *(_QWORD *)&v122 = CurrentStackLocation->FileObject;
  LOBYTE(v89) = 1;
  if ( (unsigned __int8)RefsDecodeFileObject(a1, v122, &v103, &v112) != 2 )
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
  v9 = *(_WORD *)(*(_QWORD *)v114 + 88LL);
  if ( (v9 & 9) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqZqiiiZD(
        WPP_GLOBAL_Control->AttachedDevice,
        49,
        v103 + 6152,
        (unsigned int)KeGetCurrentThread(),
        v103,
        v103 + 6152,
        v112,
        *(_QWORD *)(*(_QWORD *)(v112 + 88) + 256LL),
        *(_QWORD *)(*(_QWORD *)(v112 + 88) + 248LL),
        *(_QWORD *)(v112 + 336),
        *(_QWORD *)v114 + 16LL,
        v9);
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
  v12 = (union _LARGE_INTEGER *)RefsMapUserBuffer(Irp, v114[0]);
  if ( Options < 0x10 )
    goto LABEL_228;
  v13 = 0;
  Irpa = 0;
  v110 = 0;
  v14 = 0;
  v95 = 0;
  v96 = 0;
  v114[0] = 0;
  *(_QWORD *)Length = 0;
  v99 = 0;
  LODWORD(v112) = 0;
  v91 = 0;
  v92 = 0;
  v90 = 0;
  v94 = 0;
  v15 = CurrentStackLocation->Parameters.Read.Length;
  Size = v15;
  if ( v15 < 0x30 )
  {
LABEL_228:
    v14 = -1073741789;
    RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v109, v100, -1073741789);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225507LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789, 0, "Efssup.c", 0x954u);
    return v14;
  }
  if ( v100->RequestorMode )
  {
    ProbeForRead(p_NamedPipeType, Options, 1u);
    ProbeForWrite(v12, v15, 1u);
  }
  v16 = *(_QWORD *)p_NamedPipeType;
  v121 = *(_QWORD *)p_NamedPipeType;
  v17 = p_NamedPipeType[2];
  v106 = v17;
  memset(v12, 0, (unsigned int)Size);
  v18 = v109;
  *((_DWORD *)v109 + 1) |= 0x10000u;
  RefsAcquireFcbWithPaging(v18, *(_QWORD *)(v113 + 136), v113, 0);
  v19 = v113;
  v20 = *(_WORD *)(v113 + 256);
  if ( (v20 & 0x4000) == 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v14 = -1073740633;
    }
    else
    {
      v14 = -1073740633;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226663LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_209;
    v83 = 2434;
    goto LABEL_208;
  }
  if ( v16 >= *(_QWORD *)(v113 + 32) || v16 >= *(_QWORD *)(v113 + 24) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
    {
      v14 = -1073741807;
    }
    else
    {
      v14 = -1073741807;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 54, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221225489LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      goto LABEL_209;
    v83 = 2446;
    goto LABEL_208;
  }
  if ( v16 >= 0 && (_DWORD)v17 )
  {
    v21 = v103;
    v22 = *(_DWORD *)(v103 + 276);
    v23 = v22 - 1;
    LODWORD(v103) = v22 - 1;
    v24 = ~(unsigned __int64)(unsigned int)(v22 - 1) & ((unsigned int)(v22 - 1) + *(_QWORD *)(v113 + 40));
    v121 = v24;
    if ( v16 >= v24 )
    {
      if ( v20 >= 0 || (v25 = *(_DWORD *)(v21 + 544), (v25 & (unsigned int)v16) != 0) )
        v4 = -v22 & (v17 + v22 - 1);
      else
        v4 = *(_DWORD *)(v21 + 548) & (v25 + v17);
      v96 = v4;
      v26 = 0;
      for ( i = v4 - 1; ; i >>= 1 )
      {
        v101 = i;
        if ( !i )
          break;
        ++v26;
      }
      v28 = 1 << v26;
      v29 = (unsigned int)(1 << v26);
      v106 = 1 << v26;
      v12->QuadPart = v16;
      v12[1].LowPart = 48;
      if ( v29 >= *(_QWORD *)(v19 + 32) - v16 )
        v28 = *(_DWORD *)(v19 + 32) - v16;
      v12[1].HighPart = v28;
      v12[2].LowPart = 0;
      WORD2(v12[2].QuadPart) = 0;
      BYTE6(v12[2].QuadPart) = v26;
      HIBYTE(v12[2].QuadPart) = v26;
      LOBYTE(v12[3].LowPart) = *(_BYTE *)(v21 + 552);
      BYTE1(v12[3].LowPart) = 1;
      HIWORD(v12[3].u.LowPart) = 1;
      v12[4].LowPart = 1146378309;
      v12[4].HighPart = 16;
      if ( *(__int16 *)(v19 + 256) < 0 )
      {
        LODWORD(v29) = (*(_DWORD *)(v21 + 544) & (unsigned int)v16) != 0 ? v29 : 0;
        v106 = v29;
        v12[5].LowPart = 1;
        if ( *(_DWORD *)(v21 + 552) == 12 )
        {
          v12[5].LowPart = 5;
          BYTE1(v12[3].LowPart) = 3;
        }
        else
        {
          BYTE1(v12[3].LowPart) = 2;
        }
      }
      if ( (int)v29 + 48 > (unsigned int)Size )
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
        v95 = -1073741789;
      }
      v12[3].HighPart = v29;
      v30 = v100;
      v100->IoStatus.Information = (unsigned int)(v29 + 48);
      v14 = 0;
      v95 = 0;
      v13 = Irpa;
      v18 = v109;
      goto LABEL_210;
    }
    if ( v16 + v17 <= v24 )
    {
      v31 = 0;
    }
    else
    {
      LODWORD(v17) = v24 - v16;
      v106 = v24 - v16;
      v31 = 1;
      v91 = 1;
      v98 = 1;
    }
    if ( *(__int16 *)(v113 + 256) >= 0 )
    {
      WORD2(v12[2].QuadPart) = 0;
      v32 = v16 & -(__int64)*(int *)(v21 + 276);
      FileOffset.QuadPart = v32;
      v4 = ~(*(_DWORD *)(v21 + 276) - 1) & (v17 + v16 + *(_DWORD *)(v21 + 276) - 1 - v32);
      v96 = v4;
      v33 = 0;
      for ( j = v4 - 1; ; j >>= 1 )
      {
        v101 = j;
        if ( !j )
          break;
        ++v33;
      }
      if ( !v31 )
      {
        v4 = 1 << v33;
        v96 = 1 << v33;
        if ( v32 + (unsigned int)(1 << v33) > v24 )
        {
          v4 = v24 - v32;
          v96 = v24 - v32;
          v91 = 1;
          v98 = 1;
        }
      }
      v35 = *(_QWORD *)(v19 + 144);
      v36 = *(_BYTE *)(v35 + 552);
      v37 = *(unsigned int *)(v35 + 544);
      *(_QWORD *)&v125 = v32 >> v36;
      *((_QWORD *)&v125 + 1) = (v4 + v37) >> v36;
      v126 = v125;
      RefsIsRangeValid(v109, v19, &v126, &v93, &v113, v114, 1);
      if ( !v93 )
      {
        v39 = 1;
        v90 = 1;
        v19 = v113;
        v23 = v103;
        goto LABEL_70;
      }
      LOWORD(v99) = 1;
      *(_QWORD *)Length = v4;
      v108 = v4;
      v19 = v113;
      v38 = FileOffset.QuadPart + (1LL << v33);
      if ( v38 >= *(_QWORD *)(v113 + 32) )
        v38 = *(_QWORD *)(v113 + 32);
      QuadPart = v38;
      v118 = v38;
      v110 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v21 + 276) - 1)
           & ((unsigned int)(*(_DWORD *)(v21 + 276) - 1) + v38);
      v119 = v110;
      BYTE6(v12[2].QuadPart) = v33;
      HIBYTE(v12[2].QuadPart) = v33;
      v23 = v103;
    }
    v39 = 0;
LABEL_70:
    if ( !v39 && *(__int16 *)(v19 + 256) >= 0 )
      goto LABEL_90;
    WORD2(v12[2].QuadPart) = 0;
    v40.QuadPart = v16 & -(__int64)*(int *)(v21 + 276);
    FileOffset = v40;
    v4 = ~(*(_DWORD *)(v21 + 276) - 1) & (v16 + *(_DWORD *)(v21 + 276) - 1 + v17 - v40.LowPart);
    v96 = v4;
    v41 = *(_DWORD *)(v21 + 548);
    v42.QuadPart = (unsigned int)v16 & v41;
    v117 = v42;
    QuadPart = v42.QuadPart;
    v43 = v41 & (v17 + v16 + *(_DWORD *)(v21 + 544) - v42.LowPart);
    v114[0] = v43;
    v44 = v43 >> *(_DWORD *)(v21 + 552);
    if ( !(_WORD)v44 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
      {
        v14 = -1073740631;
      }
      else
      {
        v14 = -1073740631;
        if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            58,
            WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
            3221226665LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
      {
        v45 = 2807;
LABEL_184:
        RefsStatusDebug(v14, 0, "Efssup.c", v45);
        goto LABEL_185;
      }
      goto LABEL_185;
    }
    LOWORD(v99) = v43 >> *(_DWORD *)(v21 + 552);
    if ( (unsigned __int16)v44 > (unsigned __int16)v123 )
      goto LABEL_84;
    if ( v91 )
    {
      v107 = (~v23 & (v23 + (_DWORD)v12 + 32)) - (_DWORD)v12;
      if ( v107 + v43 <= (unsigned int)Size )
      {
LABEL_84:
        FileOffset.QuadPart = (unsigned int)v16 & v41;
        v4 = v43;
        v96 = v43;
        v40 = FileOffset;
LABEL_87:
        v46 = v40.QuadPart + v4;
        v47 = v4 + v42.QuadPart;
        if ( v46 >= *(_QWORD *)(v19 + 32) )
          v47 = *(_QWORD *)(v19 + 32);
        QuadPart = v47;
        v118 = v47;
        v110 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v21 + 276) - 1)
             & (v47 + (unsigned int)(*(_DWORD *)(v21 + 276) - 1));
        v119 = v110;
        BYTE6(v12[2].QuadPart) = *(_BYTE *)(v21 + 552);
        HIBYTE(v12[2].QuadPart) = *(_BYTE *)(v21 + 552);
        v39 = v90;
LABEL_90:
        v48 = v99;
        v49 = (unsigned __int16)v99;
        v50 = (~v23 & (v23 + 4 * (unsigned __int16)v99 + 44 + (_DWORD)v12)) - (_DWORD)v12;
        v107 = v50;
        if ( v50 <= (unsigned int)Size
          && (*(__int16 *)(v19 + 256) < 0 || v4 + v50 >= v50 && v4 + v50 <= (unsigned int)Size) )
        {
          *(&v12[3].HighPart + (unsigned __int16)v99) = 1146378309;
          *(&v12[4].LowPart + v49) = 16;
          v51 = &v12[4].HighPart + v49;
          if ( *(__int16 *)(v19 + 256) < 0 )
          {
            *v51 = 1;
            if ( *(_DWORD *)(v21 + 552) == 12 )
              *v51 = 5;
          }
          if ( v39 )
            *v51 |= 2u;
          v12[1].LowPart = v50;
          HIWORD(v12[3].u.LowPart) = v48;
          if ( (*(_DWORD *)(v19 + 300) & 0x4000) == 0 )
          {
            v52 = v100;
            CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(v122 + 40), &FileOffset, v4, &v100->IoStatus);
            RefsNormalizeAndCleanupTransaction(v109, (int *)&v52->IoStatus.0, v53, v54);
            *v12 = FileOffset;
            LOBYTE(v12[3].LowPart) = *(_BYTE *)(v21 + 552);
            BYTE1(v12[3].LowPart) = (*v51 & 6) != 0 ? 3 : 1;
            v52->IoStatus.Information = v12[1].LowPart;
            RefsInitializeIoContext(v109, (struct REFS_IO_CONTEXT *)v127, v55, 0);
            v56 = v113;
            RefsAcquireRangeLock(
              v109,
              *(struct _SCB_NONPAGED **)(v113 + 248),
              FileOffset.QuadPart,
              v4,
              0,
              (struct _RANGE_LOCK_STATE *)&v124);
            v94 = 1;
            LOWORD(v57) = 0;
            LODWORD(v103) = 0;
            v58 = FileOffset.QuadPart;
            v59 = Length[0];
            while ( 1 )
            {
              v60 = v99;
              if ( (unsigned __int16)v57 >= (unsigned __int16)v99 )
              {
                v12[1].HighPart = QuadPart - v12->LowPart;
                v12[2].LowPart = v112;
                goto LABEL_186;
              }
              v61 = (char *)v12 + v50;
              *(_QWORD *)Length = v61;
              if ( *(__int16 *)(v56 + 256) < 0 || (v62 = v90) != 0 )
              {
                v63 = v58 + *(unsigned int *)(v21 + 272);
                if ( v110 < v63 )
                  LODWORD(v63) = v110;
                v59 = v63 - v58;
                v108 = v59;
                *(_QWORD *)&v122 = v58 >> *(_BYTE *)(v21 + 552);
                *((_QWORD *)&v122 + 1) = 1;
                v123 = v122;
                RefsIsRangeValid(v109, v56, &v123, &v93, StartingOffset, IoStatusBlock, v89);
                v58 = FileOffset.QuadPart;
                LOWORD(v57) = v103;
                v61 = *(char **)Length;
                v60 = v99;
                v62 = v90;
              }
              if ( v93 )
              {
                if ( *(__int16 *)(v56 + 256) < 0 || v62 )
                {
                  if ( v60 == 1 && (v58 != v117.QuadPart || v4 != v114[0]) )
                  {
                    v64 = 0;
                    for ( k = v4 - 1; ; k >>= 1 )
                    {
                      v101 = k;
                      if ( !k )
                        break;
                      ++v64;
                    }
                    v66 = (unsigned int)(1 << v64);
                    v4 = 1 << v64;
                    v96 = 1 << v64;
                    v59 = 1 << v64;
                    v108 = 1 << v64;
                    BYTE6(v12[2].QuadPart) = v64;
                    HIBYTE(v12[2].QuadPart) = v64;
                    v58 = FileOffset.QuadPart;
                    v67 = v66 + FileOffset.QuadPart;
                    if ( v66 + FileOffset.QuadPart >= *(_QWORD *)(v56 + 32) )
                      v67 = *(_QWORD *)(v56 + 32);
                    QuadPart = v67;
                    v118 = v67;
                    v110 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v21 + 276) - 1)
                         & (v67 + (unsigned int)(*(_DWORD *)(v21 + 276) - 1));
                    v119 = v110;
                  }
                  if ( v58 + v59 > v121 )
                  {
                    v59 = v121 - v58;
                    v108 = v121 - v58;
                  }
                  if ( v59 + v50 < v50 || v59 + v50 > (unsigned int)Size )
                  {
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
                    {
                      v14 = -1073741789;
                    }
                    else
                    {
                      v14 = -1073741789;
                      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                        WPP_SF_d(
                          WPP_GLOBAL_Control->AttachedDevice,
                          61,
                          WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
                          3221225507LL);
                    }
                    if ( (_BYTE)RefsStatusDebugEnabled )
                    {
                      v45 = 3140;
                      goto LABEL_184;
                    }
                    goto LABEL_185;
                  }
                }
                v68 = IoBuildAsynchronousFsdRequest(
                        3u,
                        *(PDEVICE_OBJECT *)(*(_QWORD *)(v21 + 208) + 8LL),
                        v61,
                        v59,
                        &FileOffset,
                        0);
                Irpa = v68;
                if ( !v68 )
                {
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
                  {
                    v14 = -1073741670;
                  }
                  else
                  {
                    v14 = -1073741670;
                    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                      WPP_SF_d(
                        WPP_GLOBAL_Control->AttachedDevice,
                        62,
                        WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
                        3221225626LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                  {
                    v45 = 3161;
                    goto LABEL_184;
                  }
                  goto LABEL_185;
                }
                --v68->CurrentLocation;
                --v68->Tail.Overlay.CurrentStackLocation;
                v69 = *(struct _IRP_CONTEXT **)(*(_QWORD *)(v21 + 208) + 8LL);
                v68->Tail.Overlay.CurrentStackLocation->DeviceObject = (PDEVICE_OBJECT)v69;
                v68->UserBuffer = *(PVOID *)Length;
                RefsLockUserBuffer(v69, v68, IoWriteAccess, v59);
                v92 = 1;
                v70 = v109;
                *((_BYTE *)v109 + 40) = 3;
                RefsNonCachedIo((__int64)v70, (__int64)v127, Irpa, v56, FileOffset.QuadPart, v59, 2u);
                Information_low = LODWORD(Irpa->IoStatus.Information);
                v100->IoStatus.Information += Information_low;
                v72 = 4LL * (unsigned __int16)v103 + 28;
                *(DWORD *)((char *)&v12->LowPart + v72) = Information_low;
                v50 += Information_low;
                v107 = v50;
                v73 = 0;
              }
              else
              {
                LODWORD(Information_low) = *(_DWORD *)(v21 + 272);
                v59 = Information_low;
                v108 = Information_low;
                v73 = 1;
                if ( v60 == 1 && (v58 != v117.QuadPart || v4 != v114[0]) )
                {
                  FileOffset = v117;
                  *v12 = v117;
                  v4 = v114[0];
                  v96 = v114[0];
                  v74 = FileOffset.QuadPart + v114[0];
                  if ( v74 >= *(_QWORD *)(v56 + 32) )
                    v74 = *(_QWORD *)(v56 + 32);
                  QuadPart = v74;
                  v118 = v74;
                  v110 = ~(unsigned __int64)(unsigned int)(*(_DWORD *)(v21 + 276) - 1)
                       & (v74 + (unsigned int)(*(_DWORD *)(v21 + 276) - 1));
                  v119 = v110;
                }
                v72 = 4LL * (unsigned __int16)v57 + 28;
                *(DWORD *)((char *)&v12->LowPart + v72) = 0;
              }
              v75 = *(union _LARGE_INTEGER *)(v56 + 32);
              v76 = FileOffset;
              if ( (unsigned int)Information_low + FileOffset.QuadPart <= v75.QuadPart )
              {
                HIDWORD(Size) += Information_low;
                v120 = HIDWORD(Size);
              }
              else
              {
                if ( FileOffset.QuadPart < v75.QuadPart )
                {
                  HIDWORD(Size) += v75.LowPart - FileOffset.LowPart;
                  v120 = HIDWORD(Size);
                }
                if ( *(__int16 *)(v56 + 256) >= 0 && !v90 )
                {
                  v77 = v100;
                  v100->IoStatus.Information -= *(unsigned int *)((char *)&v12->LowPart + v72);
                  Information = v77->IoStatus.Information;
                  LODWORD(v77) = ~(*(_DWORD *)(v21 + 276) - 1) & (*(_DWORD *)(v21 + 276) - 1 + HIDWORD(Size));
                  v100->IoStatus.Information = Information + (unsigned int)v77;
                  *(DWORD *)((char *)&v12->LowPart + v72) = (unsigned int)v77;
                  v76 = FileOffset;
                }
              }
              v79 = *(_QWORD *)(v56 + 40);
              if ( (unsigned int)Information_low + v76.QuadPart <= v79 )
              {
                LODWORD(v112) = Information_low + v112;
                v116 = v112;
              }
              else if ( v79 > v76.QuadPart )
              {
                if ( (_WORD)v99 == 1 && !v73 )
                {
                  v80 = ((v79 + 511) & 0xFFFFFE00) - v76.LowPart;
                  if ( v80 > 0 && v80 < (unsigned int)Information_low )
                  {
                    memset((void *)(*(_QWORD *)Length + v80), 0, (unsigned int)(Information_low - v80));
                    v76 = FileOffset;
                  }
                }
                LODWORD(v112) = *(_DWORD *)(v56 + 40) - v76.LowPart + v112;
                v116 = v112;
              }
              v58 = v59 + v76.QuadPart;
              FileOffset.QuadPart = v58;
              v81 = Irpa;
              if ( Irpa )
              {
                MdlAddress = Irpa->MdlAddress;
                if ( MdlAddress )
                {
                  if ( v92 )
                  {
                    MmUnlockPages(MdlAddress);
                    v92 = 0;
                    v81 = Irpa;
                  }
                  IoFreeMdl(v81->MdlAddress);
                  v81 = Irpa;
                  Irpa->MdlAddress = 0;
                }
                IoFreeIrp(v81);
                Irpa = 0;
                v58 = FileOffset.QuadPart;
              }
              HIWORD(v57) = WORD1(v103);
              LOWORD(v57) = v103 + 1;
              LODWORD(v103) = v57;
            }
          }
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
          {
            v14 = -1073741202;
          }
          else
          {
            v14 = -1073741202;
            if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                60,
                WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
                3221226094LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_185;
          v45 = 2976;
          goto LABEL_184;
        }
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
        {
          v14 = -1073741789;
        }
        else
        {
          v14 = -1073741789;
          if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              59,
              WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids,
              3221225507LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
        {
          v45 = 2926;
          goto LABEL_184;
        }
LABEL_185:
        v95 = v14;
LABEL_186:
        v13 = Irpa;
        v18 = v109;
        v30 = v100;
        goto LABEL_210;
      }
      v40.QuadPart = v16 & v41;
      FileOffset = v40;
      v4 = *(_DWORD *)(v21 + 548) & (v16 + *(_DWORD *)(v21 + 544) + v17 - v40.LowPart);
      v96 = v4;
    }
    v42 = v40;
    goto LABEL_87;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0 )
  {
    v14 = -1073740631;
  }
  else
  {
    v14 = -1073740631;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 55, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, 3221226665LL);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
  {
    v83 = 2456;
LABEL_208:
    RefsStatusDebug(v14, 0, "Efssup.c", v83);
  }
LABEL_209:
  v95 = v14;
  v30 = v100;
LABEL_210:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    v84 = 0;
    v85 = (v14 & 0x80000000) != 0 ? BYTE1(WPP_GLOBAL_Control->Timer) < 4u : BYTE1(WPP_GLOBAL_Control->Timer) < 5u;
    LOBYTE(v84) = !v85;
    if ( v84 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids, v14);
  }
  if ( (_BYTE)RefsStatusDebugEnabled )
    RefsStatusDebug(v14, 0, "Efssup.c", 0xD4Du);
  RefsCleanupIoContext(v18, (struct REFS_IO_CONTEXT *)v127, v14);
  if ( v13 )
  {
    v86 = v13->MdlAddress;
    if ( v86 )
    {
      if ( v92 )
        MmUnlockPages(v86);
      IoFreeMdl(v13->MdlAddress);
    }
    IoFreeIrp(v13);
  }
  if ( v94 )
    RefsReleaseRangeLock(
      *(struct _SCB_NONPAGED **)(v113 + 248),
      FileOffset.QuadPart,
      v4,
      0,
      (struct _RANGE_LOCK_STATE *)&v124);
  RefsCompleteRequest((PSECURITY_SUBJECT_CONTEXT *)v18, v30, v14);
  return v14;
}

```

## disassembly

```asm
0x140291a00  mov     r11, rsp
0x140291a03  mov     [r11+18h], rbx
0x140291a07  mov     [r11+20h], rsi
0x140291a0b  push    rdi
0x140291a0c  push    r12
0x140291a0e  push    r13
0x140291a10  push    r14
0x140291a12  push    r15
0x140291a14  sub     rsp, 4F0h
0x140291a1b  mov     rax, cs:__security_cookie
0x140291a22  xor     rax, rsp
0x140291a25  mov     [rsp+518h+var_38], rax
0x140291a2d  mov     r14, rdx
0x140291a30  mov     [rsp+518h+var_498], rdx
0x140291a38  mov     rdi, rcx
0x140291a3b  mov     [rsp+518h+var_458], rcx
0x140291a43  mov     [rsp+518h+var_470], rcx
0x140291a4b  xor     r15d, r15d
0x140291a4e  mov     [r11-480h], r15
0x140291a55  mov     [r11-440h], r15
0x140291a5c  mov     [r11-438h], r15
0x140291a63  mov     [r11-430h], r15
0x140291a6a  mov     qword ptr [rsp+518h+FileOffset], r15
0x140291a6f  mov     [r11-418h], r15
0x140291a76  mov     [r11-428h], r15
0x140291a7d  mov     [r11-468h], r15d
0x140291a84  xorps   xmm0, xmm0
0x140291a87  movdqu  [rsp+518h+var_318], xmm0
0x140291a90  lea     esi, [r15+1]
0x140291a94  mov     qword ptr [rsp+518h+var_3D8], rsi
0x140291a9c  mov     [rsp+518h+var_4B4], sil
0x140291aa1  movups  [rsp+518h+var_3C8], xmm0
0x140291aa9  mov     [r11-448h], r15
0x140291ab0  mov     ecx, cs:Feature_ReFS_EFS__private_featureState
0x140291ab6  mov     [rsp+518h+Length], ecx
0x140291abd  test    cl, 10h
0x140291ac0  jnz     short loc_140291B08
0x140291ac2  mov     rax, qword ptr [rsp+518h+Length]
0x140291aca  mov     [r11-450h], rax
0x140291ad1  or      ecx, esi
0x140291ad3  mov     dword ptr [rsp+518h+var_450], ecx
0x140291ada  lea     r8d, [r15+3]
0x140291ade  mov     rdx, [r11-450h]
0x140291ae5  lea     rcx, Feature_ReFS_EFS__private_descriptor
0x140291aec  call    wil_details_FeatureReporting_ReportUsageToService
0x140291af1  lea     r8, Feature_ReFS_EFS__private_descriptor
0x140291af8  lea     edx, [rsi+2]
0x140291afb  mov     rcx, [rsp+518h+var_450]
0x140291b03  call    wil_details_FeatureStateCache_TryEnableDeviceUsageFastPath
0x140291b08  or      [rdi+8], rsi
0x140291b0c  mov     rbx, [r14+0B8h]
0x140291b13  mov     rax, [rbx+30h]
0x140291b17  mov     qword ptr [rsp+518h+var_3E8], rax
0x140291b1f  mov     byte ptr [rsp+518h+var_4E8], sil
0x140291b24  lea     rcx, [rsp+518h+var_430]
0x140291b2c  mov     [rsp+518h+IoStatusBlock], rcx
0x140291b31  lea     rcx, [rsp+518h+var_438]
0x140291b39  mov     [rsp+518h+StartingOffset], rcx
0x140291b3e  lea     r9, [rsp+518h+var_440]
0x140291b46  lea     r8, [rsp+518h+var_480]
0x140291b4e  mov     rdx, rax
0x140291b51  mov     rcx, rdi
0x140291b54  call    ?RefsDecodeFileObject@@YA?AW4_TYPE_OF_OPEN@@PEAU_IRP_CONTEXT@@PEAU_FILE_OBJECT@@PEAPEAU_VCB@@PEAPEAU_FCB@@PEAPEAU_SCB@@PEAPEAU_CCB@@E@Z; RefsDecodeFileObject(_IRP_CONTEXT *,_FILE_OBJECT *,_VCB * *,_FCB * *,_SCB * *,_CCB * *,uchar)
0x140291b59  cmp     al, 2
0x140291b5b  jz      short loc_140291BD1
0x140291b5d  mov     ebx, 0C000000Dh
0x140291b62  mov     r8d, ebx; Status
0x140291b65  mov     rdx, r14; Irp
0x140291b68  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140291b6b  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140291b70  lea     rsi, WPP_GLOBAL_Control
0x140291b77  mov     rcx, cs:WPP_GLOBAL_Control
0x140291b7e  cmp     rcx, rsi
0x140291b81  jz      short loc_140291BAA
0x140291b83  test    dword ptr [rcx+2Ch], 100h
0x140291b8a  jz      short loc_140291BAA
0x140291b8c  cmp     byte ptr [rcx+29h], 4
0x140291b90  jb      short loc_140291BAA
0x140291b92  mov     edx, 30h ; '0'
0x140291b97  mov     r9d, ebx
0x140291b9a  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x140291ba1  mov     rcx, [rcx+18h]
0x140291ba5  call    WPP_SF_d
0x140291baa  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140291bb0  test    cl, cl
0x140291bb2  jz      short loc_140291BCA
0x140291bb4  mov     r9d, 926h; unsigned int
0x140291bba  lea     r8, aEfssupC; "Efssup.c"
0x140291bc1  xor     edx, edx; struct _IRP_CONTEXT *
0x140291bc3  mov     ecx, ebx; Status
0x140291bc5  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x140291bca  mov     eax, ebx
0x140291bcc  jmp     loc_140293122
0x140291bd1  mov     rdx, qword ptr [rsp+518h+var_430]; unsigned int
0x140291bd9  movzx   r8d, word ptr [rdx+58h]
0x140291bde  test    r8b, 9
0x140291be2  jnz     loc_140291CED
0x140291be8  lea     rsi, WPP_GLOBAL_Control
0x140291bef  mov     rcx, cs:WPP_GLOBAL_Control
0x140291bf6  cmp     rcx, rsi
0x140291bf9  jz      loc_140291C8E
0x140291bff  test    dword ptr [rcx+2Ch], 10000h
0x140291c06  jz      loc_140291C8E
0x140291c0c  cmp     byte ptr [rcx+29h], 2
0x140291c10  jb      short loc_140291C8E
0x140291c12  mov     rbx, [rsp+518h+var_440]
0x140291c1a  mov     r10, [rbx+58h]
0x140291c1e  mov     r9, gs:188h
0x140291c27  mov     eax, r8d
0x140291c2a  lea     rcx, [rdx+10h]
0x140291c2e  mov     r11, [rsp+518h+var_480]
0x140291c36  lea     r8, [r11+1808h]
0x140291c3d  mov     edx, 31h ; '1'
0x140291c42  mov     [rsp+518h+var_4C0], eax
0x140291c46  mov     [rsp+518h+var_4C8], rcx
0x140291c4b  mov     rax, [rbx+150h]
0x140291c52  mov     [rsp+518h+var_4D0], rax
0x140291c57  mov     rax, [r10+0F8h]
0x140291c5e  mov     [rsp+518h+var_4D8], rax
0x140291c63  mov     rax, [r10+100h]
0x140291c6a  mov     [rsp+518h+var_4E0], rax
0x140291c6f  mov     [rsp+518h+var_4E8], rbx
0x140291c74  mov     [rsp+518h+IoStatusBlock], r8
0x140291c79  mov     [rsp+518h+StartingOffset], r11
0x140291c7e  mov     rcx, cs:WPP_GLOBAL_Control
0x140291c85  mov     rcx, [rcx+18h]
0x140291c89  call    WPP_SF_qqZqiiiZD
0x140291c8e  mov     ebx, 0C0000022h
0x140291c93  mov     r8d, ebx; Status
0x140291c96  mov     rdx, r14; Irp
0x140291c99  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140291c9c  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140291ca1  mov     rcx, cs:WPP_GLOBAL_Control
0x140291ca8  cmp     rcx, rsi
0x140291cab  jz      short loc_140291CD4
0x140291cad  test    dword ptr [rcx+2Ch], 100h
0x140291cb4  jz      short loc_140291CD4
0x140291cb6  cmp     byte ptr [rcx+29h], 4
0x140291cba  jb      short loc_140291CD4
0x140291cbc  mov     edx, 32h ; '2'
0x140291cc1  mov     r9d, ebx
0x140291cc4  lea     r8, WPP_8c0c253854d439cf9d5b2a702284c2b5_Traceguids
0x140291ccb  mov     rcx, [rcx+18h]
0x140291ccf  call    WPP_SF_d
0x140291cd4  mov     cl, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x140291cda  test    cl, cl
0x140291cdc  jz      loc_140291BCA
0x140291ce2  mov     r9d, 93Eh
0x140291ce8  jmp     loc_140291BBA
0x140291ced  mov     rsi, [rbx+20h]
0x140291cf1  mov     r12d, [rbx+10h]
0x140291cf5  mov     rcx, r14; struct _IRP *
0x140291cf8  call    ?RefsMapUserBuffer@@YAPEAXPEAU_IRP@@K@Z; RefsMapUserBuffer(_IRP *,ulong)
0x140291cfd  mov     r14, rax
0x140291d00  cmp     r12d, 10h
0x140291d04  jb      loc_1402930A9
0x140291d0a  mov     r13, r15
0x140291d0d  mov     [rsp+518h+Irp], r15
0x140291d15  mov     [rsp+518h+var_450], r15
0x140291d1d  mov     edi, r15d
0x140291d20  mov     [rsp+518h+var_4B0], r15d
0x140291d25  mov     [rsp+518h+var_4AC], r15d
0x140291d2a  xor     ecx, ecx
0x140291d2c  mov     [rsp+518h+var_430], ecx
0x140291d33  mov     eax, ecx
0x140291d35  mov     qword ptr [rsp+518h+Length], rax
0x140291d3d  mov     [rsp+518h+var_49C], ecx
0x140291d41  mov     dword ptr [rsp+518h+var_440], ecx
0x140291d48  mov     dword ptr [rsp+518h+Size+4], ecx
0x140291d4f  mov     [rsp+518h+var_4B6], cl
0x140291d53  mov     [rsp+518h+var_4B8], cl
0x140291d57  mov     [rsp+518h+var_4B5], cl
0x140291d5b  mov     [rsp+518h+var_4B7], cl
0x140291d5f  mov     [rsp+518h+var_4B3], cl
0x140291d63  mov     ebx, [rbx+8]
0x140291d66  mov     dword ptr [rsp+518h+Size], ebx
0x140291d6d  cmp     ebx, 30h ; '0'
0x140291d70  jb      loc_1402930A9
0x140291d76  mov     rdx, [rsp+518h+var_498]
0x140291d7e  cmp     [rdx+40h], cl
0x140291d81  jz      short loc_140291DB0
0x140291d83  mov     edx, r12d; Length
0x140291d86  lea     r12d, [rcx+1]
0x140291d8a  mov     r8d, r12d; Alignment
0x140291d8d  mov     rcx, rsi; Address
0x140291d90  call    cs:__imp_ProbeForRead
0x140291d97  nop     dword ptr [rax+rax+00h]
0x140291d9c  mov     edx, ebx; Length
0x140291d9e  mov     r8d, r12d; Alignment
0x140291da1  mov     rcx, r14; Address
0x140291da4  call    cs:__imp_ProbeForWrite
0x140291dab  nop     dword ptr [rax+rax+00h]
0x140291db0  mov     rbx, [rsi]
0x140291db3  mov     [rsp+518h+var_3F8], rbx
0x140291dbb  mov     esi, [rsi+8]
0x140291dbe  mov     [rsp+518h+var_468], esi
0x140291dc5  mov     r8d, dword ptr [rsp+518h+Size]; Size
0x140291dcd  xor     edx, edx; Val
0x140291dcf  mov     rcx, r14; void *
0x140291dd2  call    memset
0x140291dd7  nop
0x140291dd8  mov     r12, [rsp+518h+var_458]
0x140291de0  bts     dword ptr [r12+4], 10h
0x140291de7  xor     r9d, r9d
0x140291dea  mov     rcx, [rsp+518h+var_438]
0x140291df2  mov     r8, rcx
0x140291df5  mov     rdx, [rcx+88h]
0x140291dfc  mov     rcx, r12
0x140291dff  call    ?RefsAcquireFcbWithPaging@@YAEPEAU_IRP_CONTEXT@@PEAU_FCB@@PEAU_SCB@@W4_REFS_ACQUIRE_FLAGS@@@Z; RefsAcquireFcbWithPaging(_IRP_CONTEXT *,_FCB *,_SCB *,_REFS_ACQUIRE_FLAGS)
0x140291e04  mov     r10, [rsp+518h+var_438]
0x140291e0c  movzx   edx, word ptr [r10+100h]
0x140291e14  bt      dx, 0Eh
0x140291e19  jnb     loc_140292EB8
0x140291e1f  cmp     rbx, [r10+20h]
0x140291e23  jge     loc_140292E5D
0x140291e29  cmp     rbx, [r10+18h]
0x140291e2d  jge     loc_140292E5D
0x140291e33  test    rbx, rbx
0x140291e36  js      loc_140292DFE
0x140291e3c  test    esi, esi
0x140291e3e  jz      loc_140292DFE
0x140291e44  mov     r13, [rsp+518h+var_480]
0x140291e4c  mov     ecx, [r13+114h]
0x140291e53  lea     r11d, [rcx-1]
0x140291e57  mov     dword ptr [rsp+518h+var_480], r11d
0x140291e5f  mov     eax, r11d
0x140291e62  mov     r9, [r10+28h]
0x140291e66  add     r9, rax
0x140291e69  not     rax
0x140291e6c  and     r9, rax
0x140291e6f  mov     [rsp+518h+var_3F8], r9
0x140291e77  cmp     rbx, r9
0x140291e7a  jl      loc_1402920AC
0x140291e80  xor     r11d, r11d
0x140291e83  test    dx, dx
0x140291e86  jns     short loc_140291EA0
0x140291e88  mov     eax, [r13+220h]
0x140291e8f  test    ebx, eax
0x140291e91  jnz     short loc_140291EA0
0x140291e93  lea     r15d, [rax+rsi]
0x140291e97  and     r15d, [r13+224h]
0x140291e9e  jmp     short loc_140291EAC
0x140291ea0  lea     r15d, [rcx-1]
0x140291ea4  add     r15d, esi
0x140291ea7  neg     ecx
0x140291ea9  and     r15d, ecx
0x140291eac  mov     [rsp+518h+var_4AC], r15d
0x140291eb1  mov     dl, r11b
0x140291eb4  lea     eax, [r15-1]
0x140291eb8  mov     r8d, 1
0x140291ebe  mov     [rsp+518h+var_490], eax
0x140291ec5  movzx   ecx, dl
0x140291ec8  test    eax, eax
0x140291eca  jz      short loc_140291ED3
0x140291ecc  add     dl, r8b
0x140291ecf  shr     eax, 1
0x140291ed1  jmp     short loc_140291EBE
0x140291ed3  mov     eax, r8d
0x140291ed6  shl     eax, cl
0x140291ed8  mov     r12d, eax
0x140291edb  mov     [rsp+518h+var_468], r12d
0x140291ee3  mov     [r14], rbx
0x140291ee6  mov     dword ptr [r14+8], 30h ; '0'
0x140291eee  mov     rcx, [r10+20h]
0x140291ef2  sub     rcx, rbx
0x140291ef5  cmp     r12, rcx
0x140291ef8  cmovge  eax, ecx
0x140291efb  mov     [r14+0Ch], eax
0x140291eff  mov     [r14+10h], r11d
0x140291f03  mov     [r14+14h], r11w
0x140291f08  mov     [r14+16h], dl
0x140291f0c  mov     [r14+17h], dl
0x140291f10  mov     al, [r13+228h]
0x140291f17  mov     [r14+18h], al
0x140291f1b  mov     [r14+19h], r8b
0x140291f1f  mov     [r14+1Ah], r8w
0x140291f24  mov     eax, cs:dword_140209944
0x140291f2a  mov     [r14+20h], eax
0x140291f2e  mov     dword ptr [r14+24h], 10h
0x140291f36  cmp     [r10+100h], r11w
0x140291f3e  jge     short loc_140291F7A
0x140291f40  and     ebx, [r13+220h]
0x140291f47  neg     ebx
0x140291f49  sbb     eax, eax
0x140291f4b  and     eax, r12d
0x140291f4e  mov     r12d, eax
0x140291f51  mov     [rsp+518h+var_468], eax
0x140291f58  mov     [r14+28h], r8d
0x140291f5c  cmp     dword ptr [r13+228h], 0Ch
0x140291f64  jnz     short loc_140291F75
0x140291f66  mov     dword ptr [r14+28h], 5
0x140291f6e  mov     byte ptr [r14+19h], 3
0x140291f73  jmp     short loc_140291F7A
0x140291f75  mov     byte ptr [r14+19h], 2
0x140291f7a  lea     eax, [r12+30h]
0x140291f7f  cmp     eax, dword ptr [rsp+518h+Size]
0x140291f86  jbe     short loc_140291FFA
0x140291f88  lea     rsi, WPP_GLOBAL_Control
0x140291f8f  mov     rcx, cs:WPP_GLOBAL_Control
0x140291f96  cmp     rcx, rsi
  ... truncated ...
```
