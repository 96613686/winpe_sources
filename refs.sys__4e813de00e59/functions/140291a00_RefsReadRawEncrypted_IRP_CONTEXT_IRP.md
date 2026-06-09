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
- `0x1401f3fc0`
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
