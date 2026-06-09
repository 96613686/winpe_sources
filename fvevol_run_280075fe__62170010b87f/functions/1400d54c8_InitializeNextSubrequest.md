# InitializeNextSubrequest

- ea: `0x1400d54c8`
- end: `0x1400d5ef5`
- name: `InitializeNextSubrequest`
- size: `2605`
- prototype: ``
- caller_count: `3`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400d3a70`
- `0x1400d51f0`
- `0x1400d5310`

## callees

- `0x140001b10`
- `0x140001efc`
- `0x1400066a0`
- `0x140006720`
- `0x140006fec`
- `0x140008288`
- `0x140008ca8`
- `0x140009bf4`
- `0x14000c094`
- `0x1400218c0`
- `0x1400d54c8`
- `0x1400d5f00`
- `0x1400d5f8c`
- `0x1400d5fc0`

## import_xrefs

- `ntoskrnl!IoReuseIrp` at `0x1400d55a1`
- `ntoskrnl!IoReuseIrp` at `0x1400d55a1`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1400d5742`
- `ntoskrnl!IoSetIoPriorityHint` at `0x1400d5742`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400d56b6`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400d56b6`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400d5731`
- `ntoskrnl!IoGetIoPriorityHint` at `0x1400d5731`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400d5700`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400d5dd5`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400d5700`
- `ntoskrnl!IoPropagateIrpExtensionEx` at `0x1400d5dd5`
- `ntoskrnl!KeBugCheckEx` at `0x1400d58b0`
- `ntoskrnl!KeBugCheckEx` at `0x1400d58d3`
- `ntoskrnl!KeBugCheckEx` at `0x1400d58f6`
- `ntoskrnl!KeBugCheckEx` at `0x1400d5a16`
- `ntoskrnl!KeBugCheckEx` at `0x1400d5dff`
- `ntoskrnl!KeBugCheckEx` at `0x1400d58b0`
- `ntoskrnl!KeBugCheckEx` at `0x1400d58d3`
- `ntoskrnl!KeBugCheckEx` at `0x1400d58f6`
- `ntoskrnl!KeBugCheckEx` at `0x1400d5a16`
- `ntoskrnl!KeBugCheckEx` at `0x1400d5dff`

## pseudocode

```c
__int64 __fastcall InitializeNextSubrequest(__int64 a1, __int64 a2, char a3)
{
  BOOL v3; // r15d
  __int64 v4; // rbx
  __int64 v6; // rcx
  __int64 v7; // r9
  unsigned __int64 v8; // rsi
  unsigned __int64 v9; // r12
  unsigned int v10; // r14d
  __int64 v11; // rax
  int v12; // ecx
  char v13; // r15
  __int64 v14; // rdx
  IRP *v15; // r13
  int RedirectedBlockSize; // eax
  __int64 v17; // rcx
  unsigned __int64 v18; // rcx
  ULONG v19; // r14d
  int RedirectedBlockOffset; // eax
  __int64 v21; // rcx
  __int64 v22; // r8
  ULONG v23; // eax
  int v24; // r15d
  __int64 v25; // rcx
  unsigned __int64 v26; // r12
  char v27; // si
  unsigned __int64 v28; // rax
  unsigned __int64 v29; // rcx
  __int64 v30; // rcx
  PIRP v31; // r15
  IRP *v32; // rcx
  IO_PRIORITY_HINT IoPriorityHint; // eax
  struct _IO_STACK_LOCATION *v34; // rcx
  struct _IO_STACK_LOCATION *v35; // r9
  char v36; // cl
  char v37; // al
  __int64 *v38; // rdx
  __int64 v40; // rcx
  __int64 v41; // rax
  unsigned __int64 v42; // r8
  __int64 v43; // rdx
  unsigned int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // rax
  unsigned int v47; // eax
  struct _IRP *MasterIrp; // rax
  __int64 v49; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v51; // rdx
  __int64 v52; // rcx
  __int64 v53; // rax
  unsigned int v54; // r8d
  unsigned __int8 v55; // dl
  unsigned __int8 v56; // al
  unsigned int v57; // edx
  __int64 v58; // r10
  unsigned int v59; // r8d
  __int64 v60; // r9
  __int64 v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // rax
  __int64 v64; // rax
  __int64 v65; // r9
  int v66; // edx
  unsigned __int64 v67; // rcx
  __int64 v68; // rax
  __int64 v69; // rcx
  _QWORD *v70; // rcx
  __int64 v71; // rdx
  __int64 Bitmap; // rax
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rax
  __int64 v77; // rdx
  char v78; // al
  int v79; // eax
  int v80; // eax
  __int64 v81; // rcx
  __int64 *v82; // rdx
  __int64 v83; // rcx
  __int64 v84; // r8
  __int64 v85; // rdx
  int v86; // eax
  __int64 v87; // r8
  unsigned __int64 v88; // rax
  __int64 v89; // rdx
  CHAR i; // dl
  struct _FILE_OBJECT *FileObject; // rax
  char v92; // [rsp+70h] [rbp-90h]
  char v93; // [rsp+74h] [rbp-8Ch]
  ULONG v95; // [rsp+78h] [rbp-88h] BYREF
  __int64 v96; // [rsp+80h] [rbp-80h] BYREF
  BOOL v97; // [rsp+88h] [rbp-78h]
  PMDL TargetMdl; // [rsp+90h] [rbp-70h]
  PMDL SourceMdl; // [rsp+98h] [rbp-68h]
  PIRP Irp; // [rsp+A0h] [rbp-60h]
  unsigned __int64 v101; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v102; // [rsp+B0h] [rbp-50h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+B8h] [rbp-48h]
  _QWORD v104[10]; // [rsp+C0h] [rbp-40h] BYREF

  v4 = a2;
  v6 = *(_QWORD *)(a1 + 48);
  LOBYTE(a2) = a3;
  v101 = 0;
  FvePerfReportSubRequest(v6, a2);
  v8 = (unsigned int)v7;
  Irp = *(PIRP *)a1;
  v9 = (unsigned int)v7;
  v95 = v7;
  v10 = v7;
  v96 = v7;
  SourceMdl = Irp->MdlAddress;
  v11 = *(_QWORD *)(a1 + 48);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v12 = *(_DWORD *)(v11 + 808);
  if ( (v12 & 0x17F) == 0 || (v12 & 0x40) != 0 )
  {
    v13 = v7;
    v93 = v7;
  }
  else
  {
    v13 = 1;
    v93 = 1;
  }
  v14 = *(_QWORD *)(v4 + 48);
  v102 = v7;
  if ( v14 )
  {
    v40 = *(_QWORD *)(v4 + 16);
    v41 = *(_QWORD *)(v4 + 56);
    v42 = MEMORY[0xFFFFF78000000008] - v14;
    if ( v41 )
    {
      v43 = *(_QWORD *)(v4 + 64);
      if ( v43 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(v40 + 32), v43 - v41);
        v44 = *(_DWORD *)(v4 + 88);
        if ( v44 )
          _InterlockedAdd((volatile signed __int32 *)(v40 + 40), v44);
      }
    }
    v45 = *(_QWORD *)(v4 + 72);
    if ( v45 )
    {
      v46 = *(_QWORD *)(v4 + 80);
      if ( v46 )
      {
        _InterlockedAdd64((volatile signed __int64 *)(v40 + 24), v46 - v45);
        v47 = *(_DWORD *)(v4 + 92);
        if ( v47 )
          _InterlockedAdd((volatile signed __int32 *)(v40 + 44), v47);
      }
    }
    _InterlockedAdd64((volatile signed __int64 *)(v40 + 16), v42);
    *(_QWORD *)(v4 + 48) = v7;
    *(_QWORD *)(v4 + 56) = v7;
    *(_QWORD *)(v4 + 64) = v7;
    *(_QWORD *)(v4 + 72) = v7;
    *(_QWORD *)(v4 + 80) = v7;
    *(_QWORD *)(v4 + 88) = v7;
  }
  v15 = *(IRP **)(v4 + 40);
  *(_QWORD *)(v4 + 48) = MEMORY[0xFFFFF78000000008];
  *(_QWORD *)(v4 + 56) = v7;
  *(_QWORD *)(v4 + 64) = v7;
  *(_QWORD *)(v4 + 72) = v7;
  *(_QWORD *)(v4 + 80) = v7;
  *(_QWORD *)(v4 + 88) = v7;
  TargetMdl = v15->MdlAddress;
  IoReuseIrp(v15, -1073741637);
  v15->MdlAddress = TargetMdl;
  if ( v13 )
  {
    v49 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 976LL);
    if ( *(_WORD *)(v49 + 10) > 1u )
    {
      IsEnabledDeviceUsageNoInline = Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v49);
      v51 = *(_QWORD *)(a1 + 48);
      v52 = *(_QWORD *)(v51 + 976);
      if ( IsEnabledDeviceUsageNoInline && (*(_BYTE *)(v51 + 4403) & 8) != 0 || *(_WORD *)(v52 + 10) == 1 )
      {
        v53 = 0;
      }
      else
      {
        v53 = *(unsigned int *)(v52 + 28);
        if ( !(_DWORD)v53 )
          v53 = 1;
      }
      v8 = v53 * *(unsigned int *)(v51 + 1308);
      if ( v8 > 0xFFFFFFFF )
        goto LABEL_48;
      v9 = *(_QWORD *)(v52 + 56);
    }
    v10 = v8;
    if ( v9 < v8 )
      goto LABEL_29;
  }
  RedirectedBlockSize = FveGetRedirectedBlockSize(*(_QWORD *)(a1 + 112));
  if ( RedirectedBlockSize < 0 )
    KeBugCheckEx(0x120u, 0xCu, 0, 0, RedirectedBlockSize);
  v17 = *(_QWORD *)(a1 + 112);
  LOBYTE(v3) = 0;
  v97 = v3;
  IntersectRegion(v17, &v95, v9, v10);
  v18 = *(_QWORD *)(a1 + 112);
  v19 = v95;
  if ( v18 >= v9 + v8 || v18 + v95 <= v9 )
  {
    RedirectedBlockOffset = FveGetRedirectedBlockOffset(v18, v8, v9, &v96);
    if ( RedirectedBlockOffset < 0 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, RedirectedBlockOffset);
    LODWORD(v22) = v96;
    v97 = v21 != v96;
  }
  else
  {
    v22 = *(_QWORD *)(a1 + 112);
    v96 = v22;
  }
  if ( !v19 )
    goto LABEL_29;
  v23 = *(_DWORD *)(v4 + 120);
  v24 = 0;
  *(_QWORD *)(v4 + 24) = 0;
  v25 = *(_QWORD *)(a1 + 48);
  if ( v19 > v23 )
    v19 = v23;
  v92 = 0;
  v95 = v19;
  if ( (*(_DWORD *)(v25 + 808) & 0x100) != 0 )
  {
    v70 = *(_QWORD **)(v25 + 736);
    if ( v70 )
    {
      if ( *v70 )
      {
        v71 = *(_QWORD *)(a1 + 56);
        if ( v71 )
        {
          Bitmap = FveEowFindBitmap((_DWORD)v70, *(_DWORD *)(v71 + 80), v22, v19, (__int64)&v95);
          v19 = v95;
          *(_QWORD *)(v4 + 24) = Bitmap;
        }
      }
    }
  }
  if ( !v93 || !a3 && !*(_QWORD *)(*(_QWORD *)(a1 + 48) + 4736LL) )
  {
    v26 = v96;
    goto LABEL_15;
  }
  v58 = *(_QWORD *)(a1 + 48);
  v59 = 0;
  v60 = 0;
  do
  {
    v61 = *(_QWORD *)(v58 + 24 * v60 + 1056);
    v62 = 2 * v60;
    v63 = 3 * v60;
    ++v59;
    ++v60;
    v104[v62] = v61;
    v104[v62 + 1] = *(unsigned int *)(v58 + 8 * v63 + 1064);
  }
  while ( v59 < 3 );
  if ( !v97 && v8 && v59 < 5 )
  {
    v73 = 2LL * v59++;
    v104[v73] = v9;
    v104[v73 + 1] = v8;
  }
  v64 = *(_QWORD *)(v58 + 976);
  if ( *(_WORD *)(v64 + 12) == 2 )
  {
    v74 = *(unsigned int *)(v64 + 24);
    if ( (_DWORD)v74 )
    {
      if ( v59 < 5 )
      {
        v75 = 2LL * v59++;
        v104[v75] = *(_QWORD *)(v64 + 16);
        v104[v75 + 1] = v74;
      }
    }
  }
  v65 = *(_QWORD *)(v58 + 736);
  v66 = a3 != 0 ? 3 : 5;
  if ( v65 )
  {
    v66 |= 8u;
    if ( (*(_BYTE *)(*(_QWORD *)v65 + 48LL) & 1) != 0 )
      v66 |= 0x10u;
  }
  v26 = v96;
  v24 = FveLibIdentifyCurrentRegionTypeAndEnd(
          v96,
          v19,
          *(_QWORD *)(v58 + 1048),
          *(_DWORD *)(v58 + 1308),
          v59,
          (__int64)v104,
          *(_QWORD *)(v58 + 1040),
          1,
          *(_QWORD *)(v58 + 1008),
          v65,
          *(_QWORD *)(a1 + 56),
          (__int64)&v102,
          v66,
          (__int64)&v101);
  v67 = v26 + v19;
  if ( v67 > v101 )
  {
    v67 = v101 - v26;
    if ( v101 - v26 >= 0xFFFFFFFF )
      goto LABEL_29;
    v19 = v101 - v26;
  }
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v67) )
  {
    if ( !v24 || v24 == 3 )
    {
      v76 = *(_QWORD *)(a1 + 48);
      v77 = *(_QWORD *)(v76 + 4736);
      if ( v77 && ((*(_DWORD *)(*(_QWORD *)(v76 + 8) + 9680LL) & 0x10) == 0 || *(_DWORD *)(v77 + 88)) )
      {
        v78 = 1;
        v92 = 1;
      }
      else
      {
        v78 = 0;
      }
      if ( v24 == 3 && v77 && *(_DWORD *)(v77 + 88) && !v78 )
        goto LABEL_29;
    }
    goto LABEL_15;
  }
  if ( v24 && v24 != 3 )
  {
LABEL_15:
    v27 = v92;
    goto LABEL_16;
  }
  v68 = *(_QWORD *)(a1 + 48);
  v27 = 0;
  if ( *(_QWORD *)(v68 + 4736) )
    v27 = (*(_BYTE *)(*(_QWORD *)(v68 + 8) + 9680LL) & 0x10) == 0;
LABEL_16:
  v28 = *(_QWORD *)(a1 + 64);
  v29 = *(_QWORD *)(a1 + 112);
  if ( v29 < v28 )
    goto LABEL_29;
  IoBuildPartialMdl(SourceMdl, TargetMdl, (char *)SourceMdl->StartVa + SourceMdl->ByteOffset - v28 + v29, v19);
  if ( (int)IoPropagateIrpExtensionEx(
              Irp,
              v15,
              (char *)TargetMdl->StartVa
            + TargetMdl->ByteOffset
            - (unsigned __int64)SourceMdl->ByteOffset
            - (unsigned __int64)SourceMdl->StartVa,
              *(_QWORD *)(*(_QWORD *)(a1 + 48) + 4736LL) != 0 ? -5 : -1) < 0 )
  {
    v79 = IoPropagateIrpExtensionEx(
            Irp,
            v15,
            (char *)TargetMdl->StartVa
          + TargetMdl->ByteOffset
          - (unsigned __int64)SourceMdl->ByteOffset
          - (unsigned __int64)SourceMdl->StartVa,
            1);
    if ( v79 < 0 )
      KeBugCheckEx(0x120u, 0xCu, 0, 0, v79);
  }
  if ( !v27 )
    goto LABEL_19;
  v80 = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v30);
  v81 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 8LL);
  if ( v80 )
  {
    if ( !(unsigned __int8)FveSimulateResourceStress(v81) || *v82 && *(_DWORD *)(*v82 + 88) )
    {
      if ( v24 == 3 )
        v85 = *v82;
      else
        v85 = 0;
      v86 = FveIceSetIrpExtensionSteelix(v15, v85, v26, v84);
      goto LABEL_120;
    }
  }
  else if ( !(unsigned __int8)FveSimulateResourceStress(v81) )
  {
    if ( v24 == 3 )
    {
      v88 = v26 / *(unsigned int *)(v87 + 1308);
      v89 = *(_QWORD *)(v87 + 4736);
    }
    else
    {
      v88 = 0;
      v89 = 0;
    }
    v86 = FveIceSetIrpExtension(v15, v89, v88);
LABEL_120:
    if ( v86 >= 0 )
      goto LABEL_19;
  }
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v83) )
  {
    if ( v24 == 3 )
    {
      v69 = *(_QWORD *)(*(_QWORD *)(a1 + 48) + 4736LL);
      if ( v69 )
      {
        if ( *(_DWORD *)(v69 + 88) )
          goto LABEL_29;
      }
    }
  }
  v27 = 0;
LABEL_19:
  v31 = Irp;
  v32 = Irp;
  v15->Flags = Irp->Flags & 0x343;
  IoPriorityHint = IoGetIoPriorityHint(v32);
  IoSetIoPriorityHint(v15, IoPriorityHint);
  v15->RequestorMode = v31->RequestorMode;
  v15->Tail.Overlay.Thread = v31->Tail.Overlay.Thread;
  v15->Tail.Overlay.OriginalFileObject = v31->Tail.Overlay.OriginalFileObject;
  if ( (v31->Flags & 8) != 0 )
  {
    MasterIrp = v31->AssociatedIrp.MasterIrp;
    if ( MasterIrp )
      v15->Tail.Overlay.OriginalFileObject = MasterIrp->Tail.Overlay.OriginalFileObject;
  }
  v34 = v15->Tail.Overlay.CurrentStackLocation;
  v35 = CurrentStackLocation;
  *(_OWORD *)&v34[-1].MajorFunction = *(_OWORD *)&CurrentStackLocation->MajorFunction;
  *(_OWORD *)&v34[-1].Parameters.NotifyDirectoryEx.CompletionFilter = *(_OWORD *)&v35->Parameters.NotifyDirectoryEx.CompletionFilter;
  *(_OWORD *)(&v34[-1].Parameters.SetQuota + 6) = *(_OWORD *)(&v35->Parameters.SetQuota + 6);
  v34[-1].FileObject = v35->FileObject;
  v34[-1].Control = 0;
  if ( !v15->Tail.Overlay.OriginalFileObject && !v34[-1].FileObject )
  {
    for ( i = v31->CurrentLocation; (unsigned __int8)i <= v31->StackCount; ++i )
    {
      FileObject = v35->FileObject;
      if ( FileObject )
      {
        v34[-1].FileObject = FileObject;
        break;
      }
      ++v35;
    }
  }
  *(_QWORD *)v4 = *(_QWORD *)(a1 + 112);
  v36 = *(_BYTE *)(v4 + 136) & 0x7F | (v27 << 7);
  *(_QWORD *)(v4 + 8) = v26;
  *(_DWORD *)(v4 + 124) = v19;
  *(_DWORD *)(v4 + 132) = 1;
  *(_QWORD *)(v4 + 104) = 0;
  *(_DWORD *)(v4 + 128) = 0;
  *(_BYTE *)(v4 + 136) = v36;
  if ( !v27 || *(_BYTE *)(a1 + 276) )
    v37 = 64;
  else
    v37 = 0;
  *(_BYTE *)(v4 + 144) &= 0xFCu;
  *(_BYTE *)(v4 + 136) = v37 | v36 & 0xBF;
  *(_DWORD *)(a1 + 120) -= v19;
  *(_QWORD *)(a1 + 112) += v19;
  if ( *(_QWORD *)(a1 + 184) )
  {
    v54 = *(unsigned __int8 *)(a1 + 92);
    v55 = *(_BYTE *)(a1 + 265);
    if ( v55 >= (unsigned __int8)v54 )
      goto LABEL_29;
    v56 = *(_BYTE *)(a1 + 264);
    if ( (unsigned __int8)(v55 + v56) >= v56 )
    {
      v57 = (unsigned __int8)(v55 + v56) % v54;
      if ( *(_BYTE *)((unsigned __int8)v57 + a1 + 232) == 0xFF )
      {
        *(_BYTE *)((unsigned __int8)v57 + a1 + 232) = *(_BYTE *)(v4 + 136) & 0x3F;
        ++*(_BYTE *)(a1 + 265);
        goto LABEL_24;
      }
LABEL_29:
      KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
    }
LABEL_48:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0xFFFFFFFFC0000095uLL);
  }
LABEL_24:
  v38 = FVE_PERF_WRITE_SUBREQUEST_INIT;
  if ( !a3 )
    v38 = FVE_PERF_READ_SUBREQUEST_INIT;
  return FvePerfTraceDevPtrPtr(*(_QWORD *)(a1 + 48), v38, v31, v15);
}

```

## disassembly

```asm
0x1400d54c8  mov     [rsp-8+arg_10], rbx
0x1400d54cd  push    rbp
0x1400d54ce  push    rsi
0x1400d54cf  push    rdi
0x1400d54d0  push    r12
0x1400d54d2  push    r13
0x1400d54d4  push    r14
0x1400d54d6  push    r15
0x1400d54d8  lea     rbp, [rsp-20h]
0x1400d54dd  sub     rsp, 120h
0x1400d54e4  mov     rax, cs:__security_cookie
0x1400d54eb  xor     rax, rsp
0x1400d54ee  mov     [rbp+50h+var_40], rax
0x1400d54f2  mov     rbx, rdx
0x1400d54f5  mov     [rsp+150h+var_DB], r8b
0x1400d54fa  mov     rdi, rcx
0x1400d54fd  xor     r9d, r9d
0x1400d5500  mov     rcx, [rcx+30h]
0x1400d5504  mov     dl, r8b
0x1400d5507  mov     [rbp+50h+var_A8], r9
0x1400d550b  call    FvePerfReportSubRequest
0x1400d5510  mov     rax, [rdi]
0x1400d5513  mov     esi, r9d
0x1400d5516  mov     [rbp+50h+Irp], rax
0x1400d551a  mov     r12d, r9d
0x1400d551d  mov     [rsp+150h+var_D8], r9d
0x1400d5522  mov     r14d, r9d
0x1400d5525  mov     [rbp+50h+var_D0], r9
0x1400d5529  mov     rcx, [rax+8]
0x1400d552d  mov     [rbp+50h+SourceMdl], rcx
0x1400d5531  mov     rcx, [rax+0B8h]
0x1400d5538  mov     rax, [rdi+30h]
0x1400d553c  mov     [rbp+50h+var_98], rcx
0x1400d5540  mov     ecx, [rax+328h]
0x1400d5546  test    ecx, 17Fh
0x1400d554c  jnz     loc_1400D5C20
0x1400d5552  mov     r15b, r9b
0x1400d5555  mov     [rsp+150h+var_DC], r9b
0x1400d555a  mov     rdx, [rbx+30h]
0x1400d555e  mov     [rbp+50h+var_A0], r9
0x1400d5562  test    rdx, rdx
0x1400d5565  jnz     loc_1400D5903
0x1400d556b  mov     rax, ds:0FFFFF78000000008h
0x1400d5575  mov     edx, 0C00000BBh; Iostatus
0x1400d557a  mov     r13, [rbx+28h]
0x1400d557e  mov     [rbx+30h], rax
0x1400d5582  mov     rcx, r13; Irp
0x1400d5585  mov     [rbx+38h], r9
0x1400d5589  mov     [rbx+40h], r9
0x1400d558d  mov     [rbx+48h], r9
0x1400d5591  mov     [rbx+50h], r9
0x1400d5595  mov     [rbx+58h], r9
0x1400d5599  mov     rax, [r13+8]
0x1400d559d  mov     [rbp+50h+TargetMdl], rax
0x1400d55a1  call    cs:__imp_IoReuseIrp
0x1400d55a8  nop     dword ptr [rax+rax+00h]
0x1400d55ad  mov     rax, [rbp+50h+TargetMdl]
0x1400d55b1  mov     [r13+8], rax
0x1400d55b5  test    r15b, r15b
0x1400d55b8  jnz     loc_1400D59A3
0x1400d55be  mov     edx, [rdi+78h]
0x1400d55c1  lea     r9, [rsp+150h+var_D8]
0x1400d55c6  mov     rcx, [rdi+70h]; ullSubtrahend
0x1400d55ca  mov     r8, rsi
0x1400d55cd  call    FveGetRedirectedBlockSize
0x1400d55d2  test    eax, eax
0x1400d55d4  js      loc_1400D58BD
0x1400d55da  mov     rcx, [rdi+70h]
0x1400d55de  lea     rdx, [rsp+150h+var_D8]
0x1400d55e3  xor     r15b, r15b
0x1400d55e6  mov     r9d, r14d
0x1400d55e9  mov     r8, r12
0x1400d55ec  mov     [rbp+50h+var_C8], r15d
0x1400d55f0  call    IntersectRegion
0x1400d55f5  mov     rcx, [rdi+70h]
0x1400d55f9  lea     rax, [r12+rsi]
0x1400d55fd  mov     r14d, [rsp+150h+var_D8]
0x1400d5602  cmp     rcx, rax
0x1400d5605  jb      loc_1400D5C36
0x1400d560b  lea     r9, [rbp+50h+var_D0]
0x1400d560f  mov     r8, r12
0x1400d5612  mov     rdx, rsi
0x1400d5615  call    FveGetRedirectedBlockOffset
0x1400d561a  test    eax, eax
0x1400d561c  js      loc_1400D58E0
0x1400d5622  mov     r8, [rbp+50h+var_D0]
0x1400d5626  mov     eax, 1
0x1400d562b  cmp     rcx, r8
0x1400d562e  movzx   r15d, r15b
0x1400d5632  mov     [rbp+50h+var_D0], r8
0x1400d5636  cmovnz  r15d, eax
0x1400d563a  mov     [rbp+50h+var_C8], r15d
0x1400d563e  test    r14d, r14d
0x1400d5641  jz      loc_1400D5898
0x1400d5647  mov     eax, [rbx+78h]
0x1400d564a  xor     r15d, r15d
0x1400d564d  mov     [rbx+18h], r15
0x1400d5651  cmp     r14d, eax
0x1400d5654  mov     rcx, [rdi+30h]
0x1400d5658  cmova   r14d, eax
0x1400d565c  mov     byte ptr [rsp+150h+var_E0], r15b
0x1400d5661  mov     [rsp+150h+var_D8], r14d
0x1400d5666  test    dword ptr [rcx+328h], 100h
0x1400d5670  jnz     loc_1400D5C4F
0x1400d5676  cmp     [rsp+150h+var_DC], r15b
0x1400d567b  jnz     loc_1400D5A96
0x1400d5681  mov     r12, [rbp+50h+var_D0]
0x1400d5685  mov     esi, [rsp+150h+var_E0]
0x1400d5689  mov     rax, [rdi+40h]
0x1400d568d  mov     rcx, [rdi+70h]
0x1400d5691  cmp     rcx, rax
0x1400d5694  jb      loc_1400D5898
0x1400d569a  mov     r10, [rbp+50h+SourceMdl]
0x1400d569e  mov     r9d, r14d; Length
0x1400d56a1  mov     rdx, [rbp+50h+TargetMdl]; TargetMdl
0x1400d56a5  mov     r8d, [r10+2Ch]
0x1400d56a9  sub     r8, rax
0x1400d56ac  add     r8, [r10+20h]
0x1400d56b0  add     r8, rcx; VirtualAddress
0x1400d56b3  mov     rcx, r10; SourceMdl
0x1400d56b6  call    cs:__imp_IoBuildPartialMdl
0x1400d56bd  nop     dword ptr [rax+rax+00h]
0x1400d56c2  mov     rax, [rdi+30h]
0x1400d56c6  mov     rdx, [rbp+50h+SourceMdl]
0x1400d56ca  mov     rcx, [rax+1280h]
0x1400d56d1  mov     eax, 0FFFFFFFFh
0x1400d56d6  neg     rcx
0x1400d56d9  mov     rcx, [rbp+50h+TargetMdl]
0x1400d56dd  sbb     r9d, r9d
0x1400d56e0  and     r9d, 0FFFFFFFCh
0x1400d56e4  add     r9d, eax
0x1400d56e7  mov     eax, [rdx+2Ch]
0x1400d56ea  mov     r8d, [rcx+2Ch]
0x1400d56ee  sub     r8, rax
0x1400d56f1  sub     r8, [rdx+20h]
0x1400d56f5  mov     rdx, r13
0x1400d56f8  add     r8, [rcx+20h]
0x1400d56fc  mov     rcx, [rbp+50h+Irp]
0x1400d5700  call    cs:__imp_IoPropagateIrpExtensionEx
0x1400d5707  nop     dword ptr [rax+rax+00h]
0x1400d570c  test    eax, eax
0x1400d570e  js      loc_1400D5DAE
0x1400d5714  test    sil, sil
0x1400d5717  jnz     loc_1400D5E0C
0x1400d571d  mov     r15, [rbp+50h+Irp]
0x1400d5721  mov     rcx, r15; Irp
0x1400d5724  mov     eax, [r15+10h]
0x1400d5728  and     eax, 343h
0x1400d572d  mov     [r13+10h], eax
0x1400d5731  call    cs:__imp_IoGetIoPriorityHint
0x1400d5738  nop     dword ptr [rax+rax+00h]
0x1400d573d  mov     edx, eax; PriorityHint
0x1400d573f  mov     rcx, r13; Irp
0x1400d5742  call    cs:__imp_IoSetIoPriorityHint
0x1400d5749  nop     dword ptr [rax+rax+00h]
0x1400d574e  mov     al, [r15+40h]
0x1400d5752  mov     [r13+40h], al
0x1400d5756  mov     rax, [r15+98h]
0x1400d575d  mov     [r13+98h], rax
0x1400d5764  mov     rax, [r15+0C0h]
0x1400d576b  mov     [r13+0C0h], rax
0x1400d5772  mov     eax, [r15+10h]
0x1400d5776  test    al, 8
0x1400d5778  jnz     loc_1400D5983
0x1400d577e  mov     rcx, [r13+0B8h]
0x1400d5785  mov     r9, [rbp+50h+var_98]
0x1400d5789  movups  xmm0, xmmword ptr [r9]
0x1400d578d  movups  xmmword ptr [rcx-48h], xmm0
0x1400d5791  movups  xmm1, xmmword ptr [r9+10h]
0x1400d5796  movups  xmmword ptr [rcx-38h], xmm1
0x1400d579a  movups  xmm0, xmmword ptr [r9+20h]
0x1400d579f  movups  xmmword ptr [rcx-28h], xmm0
0x1400d57a3  movsd   xmm1, qword ptr [r9+30h]
0x1400d57a9  movsd   qword ptr [rcx-18h], xmm1
0x1400d57ae  mov     byte ptr [rcx-45h], 0
0x1400d57b2  cmp     qword ptr [r13+0C0h], 0
0x1400d57ba  jz      loc_1400D5EA7
0x1400d57c0  mov     rax, [rdi+70h]
0x1400d57c4  mov     cl, sil
0x1400d57c7  mov     [rbx], rax
0x1400d57ca  mov     r9d, 1
0x1400d57d0  mov     al, [rbx+88h]
0x1400d57d6  and     al, 7Fh
0x1400d57d8  shl     cl, 7
0x1400d57db  or      cl, al
0x1400d57dd  mov     [rbx+8], r12
0x1400d57e1  mov     [rbx+7Ch], r14d
0x1400d57e5  mov     [rbx+84h], r9d
0x1400d57ec  mov     qword ptr [rbx+68h], 0
0x1400d57f4  mov     dword ptr [rbx+80h], 0
0x1400d57fe  mov     [rbx+88h], cl
0x1400d5804  test    sil, sil
0x1400d5807  jnz     loc_1400D5EE1
0x1400d580d  mov     al, 40h ; '@'
0x1400d580f  and     byte ptr [rbx+90h], 0FCh
0x1400d5816  and     cl, 0BFh
0x1400d5819  or      cl, al
0x1400d581b  mov     eax, r14d
0x1400d581e  mov     [rbx+88h], cl
0x1400d5824  sub     [rdi+78h], r14d
0x1400d5828  add     [rdi+70h], rax
0x1400d582c  cmp     qword ptr [rdi+0B8h], 0
0x1400d5834  jnz     loc_1400D5A23
0x1400d583a  cmp     [rsp+150h+var_DB], 0
0x1400d583f  lea     rax, FVE_PERF_READ_SUBREQUEST_INIT
0x1400d5846  mov     rcx, [rdi+30h]
0x1400d584a  lea     rdx, FVE_PERF_WRITE_SUBREQUEST_INIT
0x1400d5851  cmovz   rdx, rax
0x1400d5855  mov     r9, r13
0x1400d5858  mov     r8, r15
0x1400d585b  call    FvePerfTraceDevPtrPtr
0x1400d5860  mov     rcx, [rbp+50h+var_40]
0x1400d5864  xor     rcx, rsp; StackCookie
0x1400d5867  call    __security_check_cookie
0x1400d586c  mov     rbx, [rsp+150h+arg_10]
0x1400d5874  add     rsp, 120h
0x1400d587b  pop     r15
0x1400d587d  pop     r14
0x1400d587f  pop     r13
0x1400d5881  pop     r12
0x1400d5883  pop     rdi
0x1400d5884  pop     rsi
0x1400d5885  pop     rbp
0x1400d5886  retn
0x1400d5888  mov     r12, [rcx+38h]
0x1400d588c  mov     r14d, esi
0x1400d588f  cmp     r12, rsi
0x1400d5892  jnb     loc_1400D55BE
0x1400d5898  xor     r9d, r9d; BugCheckParameter3
0x1400d589b  mov     [rsp+150h+BugCheckParameter4], 0; BugCheckParameter4
0x1400d58a4  xor     r8d, r8d; BugCheckParameter2
0x1400d58a7  mov     ecx, 120h; BugCheckCode
0x1400d58ac  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d58b0  call    cs:__imp_KeBugCheckEx
0x1400d58bd  xor     r9d, r9d; BugCheckParameter3
0x1400d58c0  cdqe
0x1400d58c2  xor     r8d, r8d; BugCheckParameter2
0x1400d58c5  mov     [rsp+150h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d58ca  mov     ecx, 120h; BugCheckCode
0x1400d58cf  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d58d3  call    cs:__imp_KeBugCheckEx
0x1400d58e0  xor     r9d, r9d; BugCheckParameter3
0x1400d58e3  cdqe
0x1400d58e5  xor     r8d, r8d; BugCheckParameter2
0x1400d58e8  mov     [rsp+150h+BugCheckParameter4], rax; BugCheckParameter4
0x1400d58ed  mov     ecx, 120h; BugCheckCode
0x1400d58f2  lea     edx, [r9+0Ch]; BugCheckParameter1
0x1400d58f6  call    cs:__imp_KeBugCheckEx
0x1400d5903  mov     rax, ds:0FFFFF78000000008h
0x1400d590d  mov     rcx, [rbx+10h]
0x1400d5911  mov     r8, rax
0x1400d5914  mov     rax, [rbx+38h]
0x1400d5918  sub     r8, rdx
0x1400d591b  test    rax, rax
0x1400d591e  jz      short loc_1400D593C
0x1400d5920  mov     rdx, [rbx+40h]
0x1400d5924  test    rdx, rdx
0x1400d5927  jz      short loc_1400D593C
0x1400d5929  sub     rdx, rax
0x1400d592c  lock add [rcx+20h], rdx
0x1400d5931  mov     eax, [rbx+58h]
0x1400d5934  test    eax, eax
0x1400d5936  jz      short loc_1400D593C
0x1400d5938  lock add [rcx+28h], eax
0x1400d593c  mov     rdx, [rbx+48h]
0x1400d5940  test    rdx, rdx
0x1400d5943  jz      short loc_1400D5961
0x1400d5945  mov     rax, [rbx+50h]
0x1400d5949  test    rax, rax
0x1400d594c  jz      short loc_1400D5961
0x1400d594e  sub     rax, rdx
0x1400d5951  lock add [rcx+18h], rax
0x1400d5956  mov     eax, [rbx+5Ch]
0x1400d5959  test    eax, eax
0x1400d595b  jz      short loc_1400D5961
0x1400d595d  lock add [rcx+2Ch], eax
0x1400d5961  lock add [rcx+10h], r8
0x1400d5966  mov     [rbx+30h], r9
0x1400d596a  mov     [rbx+38h], r9
0x1400d596e  mov     [rbx+40h], r9
0x1400d5972  mov     [rbx+48h], r9
0x1400d5976  mov     [rbx+50h], r9
0x1400d597a  mov     [rbx+58h], r9
0x1400d597e  jmp     loc_1400D556B
0x1400d5983  mov     rax, [r15+18h]
0x1400d5987  test    rax, rax
0x1400d598a  jz      loc_1400D577E
0x1400d5990  mov     rax, [rax+0C0h]
0x1400d5997  mov     [r13+0C0h], rax
0x1400d599e  jmp     loc_1400D577E
0x1400d59a3  mov     rax, [rdi+30h]
0x1400d59a7  mov     r14d, 1
0x1400d59ad  mov     rcx, [rax+3D0h]
0x1400d59b4  cmp     [rcx+0Ah], r14w
0x1400d59b9  jbe     loc_1400D588C
0x1400d59bf  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400d59c4  mov     rdx, [rdi+30h]
0x1400d59c8  mov     rcx, [rdx+3D0h]
0x1400d59cf  test    eax, eax
0x1400d59d1  jz      loc_1400D5A78
  ... truncated ...
```
