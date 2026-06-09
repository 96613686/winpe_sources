# UDF_SA::VerifyAndFix(FIX_LEVEL,MESSAGE *,ulong,ulong,ushort,ulong *,WSTRING const *)

- ea: `0x18006b540`
- end: `0x18006bfcc`
- name: `?VerifyAndFix@UDF_SA@@UEAAEW4FIX_LEVEL@@PEAVMESSAGE@@KKGPEAKPEBVWSTRING@@@Z`
- size: `2700`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180004ab0`
- `0x180005040`
- `0x180028568`
- `0x180036dbc`
- `0x18005fae0`
- `0x18006699c`
- `0x180067aec`
- `0x180067bf8`
- `0x180067cb8`
- `0x18006821c`
- `0x1800698f0`
- `0x18006a0c8`
- `0x18006a190`
- `0x18006a34c`
- `0x18006a3c0`
- `0x18006a7d4`
- `0x18006a84c`
- `0x18006b540`
- `0x18006bfd4`
- `0x18006f1ec`
- `0x18006f488`
- `0x180074ba8`
- `0x180075364`
- `0x18007578c`
- `0x18007d0e4`
- `0x18007e684`
- `0x18007f394`
- `0x18007f3c0`
- `0x18007f774`
- `0x18007fbe0`
- `0x180080248`
- `0x1800803d8`
- `0x18008079c`
- `0x180080b0c`
- `0x180081750`
- `0x180088010`

## import_xrefs

- `ntdll!DbgPrint` at `0x18006ba48`
- `ntdll!DbgPrint` at `0x18006bc41`
- `ntdll!DbgPrint` at `0x18006bf51`
- `ntdll!DbgPrint` at `0x18006ba48`
- `ntdll!DbgPrint` at `0x18006bc41`
- `ntdll!DbgPrint` at `0x18006bf51`

## string_xrefs

- `0x18006ba41`: `	UDF_SA::VerifyAndFix() : Cannot read any AVDP\n`

## pseudocode

```c
char __fastcall UDF_SA::VerifyAndFix(
        __int64 a1,
        unsigned int a2,
        MESSAGE *a3,
        int a4,
        __int64 a5,
        unsigned __int16 a6,
        _DWORD *a7,
        struct WSTRING *a8)
{
  void **v11; // r13
  int v12; // ecx
  READ_MODIFY_WRITE_CACHE *v13; // rax
  READ_MODIFY_WRITE_CACHE *v14; // rax
  unsigned int v15; // r8d
  unsigned int v16; // r9d
  struct DRIVE_CACHE *v17; // rbx
  int v18; // ecx
  char v19; // bl
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  unsigned int v22; // eax
  unsigned int v23; // r8d
  struct MESSAGE *v24; // rdx
  unsigned int v25; // edx
  unsigned int *v26; // rsi
  unsigned int *v27; // r14
  DP_DRIVE *v28; // rcx
  BIG_INT *v29; // rax
  unsigned int LowPart; // eax
  BIG_INT *v31; // rax
  _QWORD *v32; // rbx
  unsigned int SectorSize; // eax
  unsigned int v34; // ebx
  unsigned int v35; // esi
  unsigned int v36; // ebx
  unsigned int v37; // r8d
  unsigned int v38; // r9d
  unsigned __int8 v39; // dl
  void (__fastcall ***v40)(_QWORD, __int64); // rcx
  _QWORD *v41; // r14
  _QWORD *v42; // rsi
  UDF_LVOL *v43; // rax
  UDF_LVOL *v44; // rax
  __int64 v45; // rbx
  __int64 v46; // rbx
  _QWORD *v47; // rcx
  void (__fastcall **v48)(_QWORD *, __int64); // rax
  __int64 v49; // rbx
  UDF_LVOL *v50; // rcx
  unsigned int v52; // ebx
  struct MESSAGE *v53; // rdx
  UDF_LVOL *v54; // rcx
  unsigned int *v55; // [rsp+20h] [rbp-99h]
  unsigned __int8 v56; // [rsp+28h] [rbp-91h]
  unsigned __int8 v57; // [rsp+28h] [rbp-91h]
  int v58; // [rsp+28h] [rbp-91h]
  char v59; // [rsp+40h] [rbp-79h]
  unsigned __int8 v60; // [rsp+41h] [rbp-78h] BYREF
  unsigned __int8 v61[2]; // [rsp+42h] [rbp-77h] BYREF
  unsigned int v62; // [rsp+44h] [rbp-75h] BYREF
  unsigned int v63; // [rsp+48h] [rbp-71h] BYREF
  unsigned int v64; // [rsp+50h] [rbp-69h] BYREF
  unsigned int v65; // [rsp+58h] [rbp-61h] BYREF
  unsigned int v66; // [rsp+5Ch] [rbp-5Dh] BYREF
  unsigned int v67; // [rsp+60h] [rbp-59h]
  READ_MODIFY_WRITE_CACHE *v68; // [rsp+68h] [rbp-51h]
  int v69; // [rsp+70h] [rbp-49h]
  struct WSTRING *v70; // [rsp+78h] [rbp-41h]
  _OWORD v71[3]; // [rsp+80h] [rbp-39h] BYREF
  __int64 v72; // [rsp+B0h] [rbp-9h]

  v70 = a8;
  v69 = a4;
  v72 = 0;
  *a7 = 0;
  v11 = *(void ***)(a1 + 48);
  memset(v71, 0, sizeof(v71));
  v67 = a2;
  v61[0] = 0;
  v12 = *((_DWORD *)v11 + 90);
  v60 = 0;
  v63 = 0;
  v62 = 0;
  v66 = 0;
  v65 = 0;
  v68 = 0;
  if ( (v12 & 0x388) != v12 && (*((unsigned int (__fastcall **)(void **))*v11 + 4))(v11) != 1 )
  {
    v13 = (READ_MODIFY_WRITE_CACHE *)operator new(0x88u);
    if ( v13 )
    {
      v14 = READ_MODIFY_WRITE_CACHE::READ_MODIFY_WRITE_CACHE(v13);
      v68 = v14;
      v17 = v14;
      if ( v14
        && READ_MODIFY_WRITE_CACHE::Initialize(
             v14,
             *(struct IO_DP_DRIVE **)(a1 + 48),
             v15,
             v16,
             (unsigned __int8)v55,
             v56) )
      {
        IO_DP_DRIVE::SetCache(*(IO_DP_DRIVE **)(a1 + 48), v17);
      }
      else
      {
        v68 = v17;
      }
    }
    else
    {
      v68 = 0;
    }
  }
  v18 = *((_DWORD *)v11 + 90);
  if ( (v18 & 0x388) == v18 )
  {
LABEL_30:
    v19 = 1;
LABEL_31:
    v59 = v19;
    goto LABEL_32;
  }
  v19 = 0;
  v59 = 0;
  if ( (v18 & 0x1000000) != 0 )
  {
    if ( !DP_DRIVE::QueryDiscStatus((DP_DRIVE *)v11, &v62, &v63) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v21 = 10;
LABEL_43:
      WPP_SF_(v20[2], v21, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids);
LABEL_44:
      v25 = 30706;
LABEL_126:
      MESSAGE::DisplayMsg(a3, v25, MultiByteStr);
      goto LABEL_127;
    }
    if ( a2 && v63 == 1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, &WPP_d2f6b5aa954831b95bcb5f73fc975419_Traceguids);
      v22 = (*((__int64 (__fastcall **)(void **))*v11 + 3))(v11);
      if ( !SendFormatCommand(v11[8], *((_DWORD *)v11 + 90), v23, v22, (unsigned __int8)v55)
        || !WaitForUnitAndReportProgressWorker(v11[8], v24) )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids);
        v25 = 30707;
        goto LABEL_126;
      }
    }
    else if ( v63 == 3 )
    {
      goto LABEL_32;
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids);
    goto LABEL_30;
  }
  if ( DP_DRIVE::QueryUdfMediaSupportsQuickGrow((DP_DRIVE *)v11) )
  {
    v64 = 0;
    if ( !DP_DRIVE::QueryDiscStatus(v28, &v62, &v63) )
    {
      v20 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_44;
      v21 = 13;
      goto LABEL_43;
    }
    v19 = 1;
    v59 = 1;
    if ( v62 == 2 && (!DP_DRIVE::ReadFormattableCapacity((DP_DRIVE *)v11, 0x13u, &v64, 0, v55) || !v64) )
    {
      v19 = 0;
      goto LABEL_31;
    }
  }
LABEL_32:
  v26 = (unsigned int *)(a1 + 676);
  if ( *((_DWORD *)v11 + 89) == 4 )
  {
    v27 = (unsigned int *)(a1 + 672);
    if ( !DP_DRIVE::QueryVolumeBounds((DP_DRIVE *)v11, (unsigned int *)(a1 + 672), (unsigned int *)(a1 + 676)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids);
      v25 = 30708;
      goto LABEL_126;
    }
    if ( !v19 || !DP_DRIVE::QueryUdfMediaSupportsQuickGrow((DP_DRIVE *)v11) )
      goto LABEL_54;
    v29 = (BIG_INT *)(*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 48) + 40LL))(
                       *(_QWORD *)(a1 + 48),
                       &v64);
    LowPart = BIG_INT::GetLowPart(v29);
  }
  else
  {
    v31 = (BIG_INT *)(*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)(a1 + 48) + 40LL))(
                       *(_QWORD *)(a1 + 48),
                       &v64);
    LowPart = BIG_INT::GetLowPart(v31);
    v27 = (unsigned int *)(a1 + 672);
  }
  *v26 = LowPart - 1;
LABEL_54:
  v32 = operator new(0x20u);
  if ( !v32 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids);
    v25 = 1062;
    goto LABEL_126;
  }
  v32[1] = VRS_cd;
  *v32 = &VRS::`vftable';
  v32[2] = 0;
  *((_BYTE *)v32 + 24) = 0;
  v32[2] = *(_QWORD *)(a1 + 48);
  *((_BYTE *)v32 + 24) = 0;
  if ( !VRS::ReadAndVerify((VRS *)v32, *v27, &v66, &v65) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids);
    (*(void (__fastcall **)(_QWORD *, __int64))*v32)(v32, 1);
    v25 = 30709;
    goto LABEL_126;
  }
  if ( !*((_BYTE *)v32 + 24) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids);
    (*(void (__fastcall **)(_QWORD *, __int64))*v32)(v32, 1);
    v25 = 30710;
    goto LABEL_126;
  }
  (*(void (__fastcall **)(_QWORD *, __int64))*v32)(v32, 1);
  SectorSize = UDF_SA::QuerySectorSize((UDF_SA *)a1);
  v34 = *v27;
  v35 = *v26;
  v64 = v35;
  v36 = ((unsigned __int64)SectorSize + 0x7FFF) / SectorSize + v34;
  v62 = v36;
  LODWORD(v55) = UDF_SA::QuerySectorSize((UDF_SA *)a1);
  *(_QWORD *)(a1 + 608) = UNALLOCATED_SPACE_DESCRIPTOR::Create(
                            3 - (*(_WORD *)(a1 + 584) < 0x200u),
                            *(_WORD *)(a1 + 78),
                            v37,
                            v38,
                            (SIZE_T)v55,
                            v36,
                            v35);
  if ( !UDF_SA::GetAnchorVolumeDescriptorPointer((UDF_SA *)a1, v39, &v60, v61, (struct MESSAGE *)a3, v57) )
  {
    DbgPrint("\tUDF_SA::VerifyAndFix() : Cannot read any AVDP\n");
    MESSAGE::DisplayMsg(a3, 0x77B8u, MultiByteStr);
    *a7 = 3;
    return 0;
  }
  if ( v60 )
    *(_BYTE *)(a1 + 657) = 1;
  if ( !UNALLOCATED_SPACE_DESCRIPTOR::MarkInUse(*(UNALLOCATED_SPACE_DESCRIPTOR **)(a1 + 608), v66, v65) )
    goto LABEL_84;
  v40 = *(void (__fastcall ****)(_QWORD, __int64))(a1 + 600);
  if ( v40 )
  {
    (**v40)(v40, 1);
    *(_QWORD *)(a1 + 600) = 0;
  }
  v41 = operator new(0x58u);
  if ( !v41 )
    goto LABEL_121;
  v41[1] = VDS_cd;
  *v41 = &VDS::`vftable';
  v41[2] = 0;
  v41[5] = 0;
  v41[6] = 0;
  v41[7] = 0;
  v41[8] = 0;
  v41[9] = 0;
  *((_BYTE *)v41 + 32) = 0;
  v41[10] = 0;
  v42 = operator new(0x58u);
  if ( !v42 )
    goto LABEL_121;
  v42[1] = VDS_cd;
  *v42 = &VDS::`vftable';
  v42[2] = 0;
  v42[5] = 0;
  v42[6] = 0;
  v42[7] = 0;
  v42[8] = 0;
  v42[9] = 0;
  *((_BYTE *)v42 + 32) = 0;
  v42[10] = 0;
  v43 = (UDF_LVOL *)operator new(0x288u);
  if ( !v43 )
  {
    *(_QWORD *)(a1 + 600) = 0;
    goto LABEL_121;
  }
  v44 = UDF_LVOL::UDF_LVOL(v43);
  *(_QWORD *)(a1 + 600) = v44;
  if ( !v44 )
  {
LABEL_121:
    MESSAGE::DisplayMsg(a3, 0x426u, MultiByteStr);
    DbgPrint("\tUDF_SA::VerifyAndFix() : Out of memory.\n");
LABEL_127:
    *a7 = 3;
    return 0;
  }
  *((_BYTE *)v44 + 150) = v59;
  v45 = *(_QWORD *)(a1 + 88);
  VDS::Destroy((VDS *)v41);
  v41[2] = a1;
  v41[3] = v45;
  if ( VDS::Read((VDS *)v41)
    && VDS::Verify((VDS *)v41, (struct MESSAGE *)a3)
    && UDF_LVOL::ReadFromDisk(
         *(UDF_SA ***)(a1 + 600),
         (struct UDF_SA *)a1,
         (struct MESSAGE *)a3,
         (UNALLOCATED_SPACE_DESCRIPTOR **)v41) )
  {
    if ( !VDS::MarkSpaceInUasd((VDS *)v41, *(struct UNALLOCATED_SPACE_DESCRIPTOR **)(a1 + 608)) )
      goto LABEL_84;
    v46 = *(_QWORD *)(a1 + 96);
    VDS::Destroy((VDS *)v42);
    v42[2] = a1;
    v42[3] = v46;
    if ( VDS::Read((VDS *)v42)
      && VDS::Verify((VDS *)v42, (struct MESSAGE *)a3)
      && VDS::Compare((VDS *)v42, (struct VDS *)v41) )
    {
      if ( !VDS::MarkSpaceInUasd((VDS *)v42, *(struct UNALLOCATED_SPACE_DESCRIPTOR **)(a1 + 608)) )
        goto LABEL_84;
    }
    else if ( !v59 )
    {
      MESSAGE::DisplayMsg(a3, 0x7795u, MultiByteStr);
      *(_DWORD *)(a1 + 96) = 0;
    }
    *(_QWORD *)(a1 + 592) = v41;
    v47 = v42;
    v48 = (void (__fastcall **)(_QWORD *, __int64))*v42;
  }
  else
  {
    if ( !MESSAGE::DisplayMsg(a3, 0x7794u, MultiByteStr)
      || (v49 = *(_QWORD *)(a1 + 96), VDS::Destroy((VDS *)v42), v42[2] = a1, v42[3] = v49, !VDS::Read((VDS *)v42))
      || !VDS::Verify((VDS *)v42, (struct MESSAGE *)a3)
      || VDS::Verify((VDS *)v41, 0) && VDS::Compare((VDS *)v42, (struct VDS *)v41)
      || !UDF_LVOL::ReadFromDisk(
            *(UDF_SA ***)(a1 + 600),
            (struct UDF_SA *)a1,
            (struct MESSAGE *)a3,
            (UNALLOCATED_SPACE_DESCRIPTOR **)v42) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids);
      MESSAGE::DisplayMsg(a3, 0x7799u, MultiByteStr);
      (*(void (__fastcall **)(_QWORD *, __int64))*v41)(v41, 1);
      (*(void (__fastcall **)(_QWORD *, __int64))*v42)(v42, 1);
      goto LABEL_127;
    }
    if ( !VDS::MarkSpaceInUasd((VDS *)v42, *(struct UNALLOCATED_SPACE_DESCRIPTOR **)(a1 + 608)) )
      goto LABEL_84;
    *(_DWORD *)(a1 + 88) = 0;
    v47 = v41;
    *(_QWORD *)(a1 + 592) = v42;
    v48 = (void (__fastcall **)(_QWORD *, __int64))*v41;
  }
  (*v48)(v47, 1);
  if ( !VDS::VerifyAndPrintVersion(*(VDS **)(a1 + 592), (struct MESSAGE *)a3, v70) )
    return 0;
  v50 = *(UDF_LVOL **)(a1 + 600);
  if ( *((_BYTE *)v50 + 146) )
    return UDF_SA::VerifyAndFixIncrementalWriteMedia(a1, v67, a3, a7);
  if ( !UDF_LVOL::MarkUsedSpaceInUasd(v50, *(struct UNALLOCATED_SPACE_DESCRIPTOR **)(a1 + 608)) )
  {
LABEL_84:
    DbgPrint("\tUDF_SA::VerifyAndFix() : Failure to mark space used in the UASD.\n");
    v25 = 30711;
    goto LABEL_126;
  }
  if ( !*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 600) + 80LL) + 28LL) )
    MESSAGE::DisplayMsg(a3, 0x7764u, MultiByteStr);
  if ( v69 < 0 )
    return 1;
  v52 = v67;
  if ( (unsigned __int8)UDF_LVOL::VerifyAndFix(*(_QWORD *)(a1 + 600), v67, (unsigned int)v69, a6, a7, v71) )
  {
    LOBYTE(v58) = v59;
    if ( (unsigned __int8)UDF_SA::CleanUp(a1, v52, a3, v62, v64, v58, a7) )
    {
      if ( v52 )
      {
        v54 = *(UDF_LVOL **)(a1 + 600);
        if ( !*(_DWORD *)(*((_QWORD *)v54 + 10) + 28LL) )
        {
          if ( !UDF_LVOL::MarkLvidType(v54, (unsigned int)v53) )
            return 0;
          *a7 = 1;
        }
        if ( *a7 )
        {
          if ( v68 && !(*(unsigned __int8 (__fastcall **)(READ_MODIFY_WRITE_CACHE *))(*(_QWORD *)v68 + 40LL))(v68) )
            return 0;
          DP_DRIVE::WaitForWriteCompletion((DP_DRIVE *)v11, v53);
        }
      }
      return (unsigned __int8)UDF_LVOL::PrintReport(*(_QWORD *)(a1 + 600), v52, v71, (unsigned int)*a7) != 0;
    }
  }
  else
  {
    MESSAGE::DisplayMsg(*(MESSAGE **)(*(_QWORD *)(a1 + 600) + 24LL), v52 != 0 ? 1128 : 26068, MultiByteStr);
  }
  return 0;
}

```

## disassembly

```asm
0x18006b540  mov     [rsp-8+arg_18], rbx
0x18006b545  push    rbp
0x18006b546  push    rsi
0x18006b547  push    rdi
0x18006b548  push    r12
0x18006b54a  push    r13
0x18006b54c  push    r14
0x18006b54e  push    r15
0x18006b550  lea     rbp, [rsp-7]
0x18006b555  sub     rsp, 0C0h
0x18006b55c  mov     rax, cs:__security_cookie
0x18006b563  xor     rax, rsp
0x18006b566  mov     [rbp+37h+var_38], rax
0x18006b56a  mov     rax, [rbp+37h+arg_38]
0x18006b56e  xor     r14d, r14d
0x18006b571  mov     r12, [rbp+37h+arg_30]
0x18006b575  xorps   xmm0, xmm0
0x18006b578  mov     [rbp+37h+var_78], rax
0x18006b57c  mov     rdi, rcx
0x18006b57f  xor     eax, eax
0x18006b581  mov     [rbp+37h+var_80], r9d
0x18006b585  mov     [rbp+37h+var_40], rax
0x18006b589  mov     r15, r8
0x18006b58c  mov     [r12], r14d
0x18006b590  mov     esi, edx
0x18006b592  mov     r13, [rcx+30h]
0x18006b596  movups  [rbp+37h+var_70], xmm0
0x18006b59a  mov     [rbp+37h+var_90], edx
0x18006b59d  movups  [rbp+37h+var_60], xmm0
0x18006b5a1  mov     [rbp+37h+var_AE], r14b
0x18006b5a5  movups  [rbp+37h+var_50], xmm0
0x18006b5a9  mov     ecx, [r13+168h]
0x18006b5b0  mov     eax, ecx
0x18006b5b2  and     eax, 388h
0x18006b5b7  mov     [rbp+37h+var_AF], r14b
0x18006b5bb  mov     [rbp+37h+var_A8], r14d
0x18006b5bf  mov     [rbp+37h+var_AC], r14d
0x18006b5c3  mov     [rbp+37h+var_94], r14d
0x18006b5c7  mov     [rbp+37h+var_98], r14d
0x18006b5cb  mov     [rbp+37h+var_88], r14
0x18006b5cf  cmp     eax, ecx
0x18006b5d1  jz      short loc_18006B633
0x18006b5d3  mov     rax, [r13+0]
0x18006b5d7  mov     rcx, r13
0x18006b5da  mov     rax, [rax+20h]
0x18006b5de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b5e3  cmp     eax, 1
0x18006b5e6  jz      short loc_18006B633
0x18006b5e8  mov     ecx, 88h; unsigned __int64
0x18006b5ed  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b5f2  test    rax, rax
0x18006b5f5  jz      short loc_18006B62F
0x18006b5f7  mov     rcx, rax; this
0x18006b5fa  call    ??0READ_MODIFY_WRITE_CACHE@@QEAA@XZ; READ_MODIFY_WRITE_CACHE::READ_MODIFY_WRITE_CACHE(void)
0x18006b5ff  mov     [rbp+37h+var_88], rax
0x18006b603  mov     rbx, rax
0x18006b606  test    rax, rax
0x18006b609  jz      short loc_18006B629
0x18006b60b  mov     rdx, [rdi+30h]; struct IO_DP_DRIVE *
0x18006b60f  mov     rcx, rax; this
0x18006b612  call    ?Initialize@READ_MODIFY_WRITE_CACHE@@QEAAEPEAVIO_DP_DRIVE@@KKEE@Z; READ_MODIFY_WRITE_CACHE::Initialize(IO_DP_DRIVE *,ulong,ulong,uchar,uchar)
0x18006b617  test    al, al
0x18006b619  jz      short loc_18006B629
0x18006b61b  mov     rcx, [rdi+30h]; this
0x18006b61f  mov     rdx, rbx; struct DRIVE_CACHE *
0x18006b622  call    ?SetCache@IO_DP_DRIVE@@QEAAXPEAVDRIVE_CACHE@@@Z; IO_DP_DRIVE::SetCache(DRIVE_CACHE *)
0x18006b627  jmp     short loc_18006B633
0x18006b629  mov     [rbp+37h+var_88], rbx
0x18006b62d  jmp     short loc_18006B633
0x18006b62f  mov     [rbp+37h+var_88], r14
0x18006b633  mov     ecx, [r13+168h]
0x18006b63a  mov     eax, ecx
0x18006b63c  and     eax, 388h
0x18006b641  cmp     eax, ecx
0x18006b643  jz      loc_18006B771
0x18006b649  mov     bl, r14b
0x18006b64c  bt      ecx, 18h
0x18006b650  mov     [rbp+37h+var_B0], bl
0x18006b653  mov     rcx, r13; this
0x18006b656  jnb     loc_18006B7E0
0x18006b65c  lea     r8, [rbp+37h+var_A8]; unsigned int *
0x18006b660  lea     rdx, [rbp+37h+var_AC]; unsigned int *
0x18006b664  call    ?QueryDiscStatus@DP_DRIVE@@QEAAEPEAK0@Z; DP_DRIVE::QueryDiscStatus(ulong *,ulong *)
0x18006b669  test    al, al
0x18006b66b  jnz     short loc_18006B698
0x18006b66d  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b674  lea     rax, WPP_GLOBAL_Control
0x18006b67b  cmp     rcx, rax
0x18006b67e  jz      loc_18006B82C
0x18006b684  test    byte ptr [rcx+1Ch], 1
0x18006b688  jz      loc_18006B82C
0x18006b68e  mov     edx, 0Ah
0x18006b693  jmp     loc_18006B81C
0x18006b698  test    esi, esi
0x18006b69a  jz      loc_18006B73D
0x18006b6a0  cmp     [rbp+37h+var_A8], 1
0x18006b6a4  jnz     loc_18006B73D
0x18006b6aa  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b6b1  lea     rbx, WPP_GLOBAL_Control
0x18006b6b8  cmp     rcx, rbx
0x18006b6bb  jz      short loc_18006B6D8
0x18006b6bd  test    byte ptr [rcx+1Ch], 1
0x18006b6c1  jz      short loc_18006B6D8
0x18006b6c3  mov     rcx, [rcx+10h]
0x18006b6c7  lea     r8, WPP_d2f6b5aa954831b95bcb5f73fc975419_Traceguids
0x18006b6ce  mov     edx, 29h ; ')'
0x18006b6d3  call    WPP_SF_
0x18006b6d8  mov     rax, [r13+0]
0x18006b6dc  mov     rcx, r13
0x18006b6df  mov     rax, [rax+18h]
0x18006b6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b6e8  mov     edx, [r13+168h]; unsigned int
0x18006b6ef  mov     r9d, eax; unsigned int
0x18006b6f2  mov     rcx, [r13+40h]; void *
0x18006b6f6  call    ?SendFormatCommand@@YAEPEAXKKKE@Z; SendFormatCommand(void *,ulong,ulong,ulong,uchar)
0x18006b6fb  test    al, al
0x18006b6fd  jz      short loc_18006B70C
0x18006b6ff  mov     rcx, [r13+40h]; void *
0x18006b703  call    ?WaitForUnitAndReportProgressWorker@@YAEPEAXPEAVMESSAGE@@@Z; WaitForUnitAndReportProgressWorker(void *,MESSAGE *)
0x18006b708  test    al, al
0x18006b70a  jnz     short loc_18006B74A
0x18006b70c  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b713  cmp     rcx, rbx
0x18006b716  jz      short loc_18006B733
0x18006b718  test    byte ptr [rcx+1Ch], 1
0x18006b71c  jz      short loc_18006B733
0x18006b71e  mov     rcx, [rcx+10h]
0x18006b722  lea     r8, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids
0x18006b729  mov     edx, 0Bh
0x18006b72e  call    WPP_SF_
0x18006b733  mov     edx, 77F3h
0x18006b738  jmp     loc_18006BF8C
0x18006b73d  cmp     [rbp+37h+var_A8], 3
0x18006b741  jz      short loc_18006B776
0x18006b743  lea     rbx, WPP_GLOBAL_Control
0x18006b74a  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b751  cmp     rcx, rbx
0x18006b754  jz      short loc_18006B771
0x18006b756  test    byte ptr [rcx+1Ch], 1
0x18006b75a  jz      short loc_18006B771
0x18006b75c  mov     rcx, [rcx+10h]
0x18006b760  lea     r8, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids
0x18006b767  mov     edx, 0Ch
0x18006b76c  call    WPP_SF_
0x18006b771  mov     bl, 1
0x18006b773  mov     [rbp+37h+var_B0], bl
0x18006b776  cmp     dword ptr [r13+164h], 4
0x18006b77e  lea     rsi, [rdi+2A4h]
0x18006b785  jnz     loc_18006B89A
0x18006b78b  lea     r14, [rdi+2A0h]
0x18006b792  mov     r8, rsi; unsigned int *
0x18006b795  mov     rdx, r14; unsigned int *
0x18006b798  mov     rcx, r13; this
0x18006b79b  call    ?QueryVolumeBounds@DP_DRIVE@@QEAAEPEAK0@Z; DP_DRIVE::QueryVolumeBounds(ulong *,ulong *)
0x18006b7a0  test    al, al
0x18006b7a2  jnz     loc_18006B86C
0x18006b7a8  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b7af  lea     rax, WPP_GLOBAL_Control
0x18006b7b6  cmp     rcx, rax
0x18006b7b9  jz      short loc_18006B7D6
0x18006b7bb  test    byte ptr [rcx+1Ch], 1
0x18006b7bf  jz      short loc_18006B7D6
0x18006b7c1  mov     rcx, [rcx+10h]
0x18006b7c5  lea     r8, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids
0x18006b7cc  mov     edx, 0Eh
0x18006b7d1  call    WPP_SF_
0x18006b7d6  mov     edx, 77F4h
0x18006b7db  jmp     loc_18006BF8C
0x18006b7e0  call    ?QueryUdfMediaSupportsQuickGrow@DP_DRIVE@@QEAAEXZ; DP_DRIVE::QueryUdfMediaSupportsQuickGrow(void)
0x18006b7e5  test    al, al
0x18006b7e7  jz      short loc_18006B776
0x18006b7e9  lea     r8, [rbp+37h+var_A8]; unsigned int *
0x18006b7ed  mov     [rbp+37h+var_A0], r14d
0x18006b7f1  lea     rdx, [rbp+37h+var_AC]; unsigned int *
0x18006b7f5  call    ?QueryDiscStatus@DP_DRIVE@@QEAAEPEAK0@Z; DP_DRIVE::QueryDiscStatus(ulong *,ulong *)
0x18006b7fa  test    al, al
0x18006b7fc  jnz     short loc_18006B836
0x18006b7fe  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b805  lea     rax, WPP_GLOBAL_Control
0x18006b80c  cmp     rcx, rax
0x18006b80f  jz      short loc_18006B82C
0x18006b811  test    byte ptr [rcx+1Ch], 1
0x18006b815  jz      short loc_18006B82C
0x18006b817  mov     edx, 0Dh
0x18006b81c  mov     rcx, [rcx+10h]
0x18006b820  lea     r8, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids
0x18006b827  call    WPP_SF_
0x18006b82c  mov     edx, 77F2h
0x18006b831  jmp     loc_18006BF8C
0x18006b836  cmp     [rbp+37h+var_AC], 2
0x18006b83a  mov     bl, 1
0x18006b83c  mov     [rbp+37h+var_B0], bl
0x18006b83f  jnz     loc_18006B776
0x18006b845  xor     r9d, r9d; unsigned __int8 *
0x18006b848  lea     r8, [rbp+37h+var_A0]; unsigned int *
0x18006b84c  mov     dl, 13h; unsigned __int8
0x18006b84e  mov     rcx, r13; this
0x18006b851  call    ?ReadFormattableCapacity@DP_DRIVE@@QEAAEEPEAKPEAE0@Z; DP_DRIVE::ReadFormattableCapacity(uchar,ulong *,uchar *,ulong *)
0x18006b856  test    al, al
0x18006b858  jz      short loc_18006B864
0x18006b85a  cmp     [rbp+37h+var_A0], r14d
0x18006b85e  jnz     loc_18006B776
0x18006b864  mov     bl, r14b
0x18006b867  jmp     loc_18006B773
0x18006b86c  test    bl, bl
0x18006b86e  jz      short loc_18006B8C1
0x18006b870  mov     rcx, r13; this
0x18006b873  call    ?QueryUdfMediaSupportsQuickGrow@DP_DRIVE@@QEAAEXZ; DP_DRIVE::QueryUdfMediaSupportsQuickGrow(void)
0x18006b878  test    al, al
0x18006b87a  jz      short loc_18006B8C1
0x18006b87c  mov     rcx, [rdi+30h]
0x18006b880  lea     rdx, [rbp+37h+var_A0]
0x18006b884  mov     rax, [rcx]
0x18006b887  mov     rax, [rax+28h]
0x18006b88b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b890  mov     rcx, rax; this
0x18006b893  call    ?GetLowPart@BIG_INT@@QEBAKXZ; BIG_INT::GetLowPart(void)
0x18006b898  jmp     short loc_18006B8BD
0x18006b89a  mov     rcx, [rdi+30h]
0x18006b89e  lea     rdx, [rbp+37h+var_A0]
0x18006b8a2  mov     rax, [rcx]
0x18006b8a5  mov     rax, [rax+28h]
0x18006b8a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b8ae  mov     rcx, rax; this
0x18006b8b1  call    ?GetLowPart@BIG_INT@@QEBAKXZ; BIG_INT::GetLowPart(void)
0x18006b8b6  lea     r14, [rdi+2A0h]
0x18006b8bd  dec     eax
0x18006b8bf  mov     [rsi], eax
0x18006b8c1  mov     ecx, 20h ; ' '; unsigned __int64
0x18006b8c6  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18006b8cb  xor     edx, edx
0x18006b8cd  mov     rbx, rax
0x18006b8d0  test    rax, rax
0x18006b8d3  jz      loc_18006BF59
0x18006b8d9  mov     rcx, cs:?VRS_cd@@3PEBVCLASS_DESCRIPTOR@@EB; CLASS_DESCRIPTOR const * const VRS_cd
0x18006b8e0  lea     rax, ??_7VRS@@6B@; const VRS::`vftable'
0x18006b8e7  mov     [rbx+8], rcx
0x18006b8eb  lea     r9, [rbp+37h+var_98]; unsigned int *
0x18006b8ef  mov     [rbx], rax
0x18006b8f2  lea     r8, [rbp+37h+var_94]; unsigned int *
0x18006b8f6  mov     [rbx+10h], rdx
0x18006b8fa  mov     [rbx+18h], dl
0x18006b8fd  mov     rcx, [rdi+30h]
0x18006b901  mov     [rbx+10h], rcx
0x18006b905  mov     rcx, rbx; this
0x18006b908  mov     [rbx+18h], dl
0x18006b90b  mov     edx, [r14]; unsigned int
0x18006b90e  call    ?ReadAndVerify@VRS@@QEAAEKPEAK0@Z; VRS::ReadAndVerify(ulong,ulong *,ulong *)
0x18006b913  test    al, al
0x18006b915  jnz     short loc_18006B962
0x18006b917  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b91e  lea     rax, WPP_GLOBAL_Control
0x18006b925  cmp     rcx, rax
0x18006b928  jz      short loc_18006B945
0x18006b92a  test    byte ptr [rcx+1Ch], 1
0x18006b92e  jz      short loc_18006B945
0x18006b930  mov     rcx, [rcx+10h]
0x18006b934  lea     r8, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids
0x18006b93b  mov     edx, 11h
0x18006b940  call    WPP_SF_
0x18006b945  mov     rax, [rbx]
0x18006b948  mov     edx, 1
0x18006b94d  mov     rcx, rbx
0x18006b950  mov     rax, [rax]
0x18006b953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b958  mov     edx, 77F5h
0x18006b95d  jmp     loc_18006BF8C
0x18006b962  cmp     byte ptr [rbx+18h], 0
0x18006b966  jnz     short loc_18006B9B3
0x18006b968  mov     rcx, cs:WPP_GLOBAL_Control
0x18006b96f  lea     rax, WPP_GLOBAL_Control
0x18006b976  cmp     rcx, rax
0x18006b979  jz      short loc_18006B996
0x18006b97b  test    byte ptr [rcx+1Ch], 1
0x18006b97f  jz      short loc_18006B996
0x18006b981  mov     rcx, [rcx+10h]
0x18006b985  lea     r8, WPP_a8486c89b0033acef3b1fdfe7e81df45_Traceguids
0x18006b98c  mov     edx, 12h
0x18006b991  call    WPP_SF_
0x18006b996  mov     rax, [rbx]
0x18006b999  mov     edx, 1
0x18006b99e  mov     rcx, rbx
0x18006b9a1  mov     rax, [rax]
0x18006b9a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9a9  mov     edx, 77F6h
0x18006b9ae  jmp     loc_18006BF8C
0x18006b9b3  mov     rax, [rbx]
0x18006b9b6  mov     edx, 1
0x18006b9bb  mov     rcx, rbx
0x18006b9be  mov     rax, [rax]
0x18006b9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006b9c6  mov     rcx, rdi; this
0x18006b9c9  call    ?QuerySectorSize@UDF_SA@@QEBAKXZ; UDF_SA::QuerySectorSize(void)
0x18006b9ce  mov     ebx, [r14]
0x18006b9d1  xor     edx, edx
0x18006b9d3  mov     esi, [rsi]
0x18006b9d5  mov     ecx, eax
0x18006b9d7  mov     [rbp+37h+var_A0], esi
0x18006b9da  lea     rax, [rcx+7FFFh]
0x18006b9e1  div     rcx
  ... truncated ...
```
