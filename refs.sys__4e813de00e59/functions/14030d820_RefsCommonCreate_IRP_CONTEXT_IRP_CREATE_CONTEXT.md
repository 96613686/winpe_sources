# RefsCommonCreate(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)

- ea: `0x14030d820`
- end: `0x14031024b`
- name: `?RefsCommonCreate@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z`
- size: `10795`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp, struct _CREATE_CONTEXT *)`
- caller_count: `4`
- callee_count: `58`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400b9530`
- `0x140298510`
- `0x14030cd80`
- `0x14030d160`

## callees

- `0x14000c180`
- `0x14000e0e0`
- `0x14004ffc0`
- `0x140071ba0`
- `0x140076ad0`
- `0x140080070`
- `0x140085570`
- `0x1400862c0`
- `0x140089260`
- `0x14008cb50`
- `0x14008ec60`
- `0x140093bc0`
- `0x14009e670`
- `0x1400a8498`
- `0x1400d0fd8`
- `0x1400e6bb0`
- `0x1401153f8`
- `0x1401f3fc0`
- `0x1401f4100`
- `0x1401f4920`
- `0x14028debc`
- `0x140297cc8`
- `0x140297d10`
- `0x140298564`
- `0x1402986f0`
- `0x14029a0bc`
- `0x14029bf9c`
- `0x1402ff3f0`
- `0x1403025b0`
- `0x140302e10`
- `0x1403053a0`
- `0x140306290`
- `0x140309cb0`
- `0x14030a7c0`
- `0x14030d820`
- `0x140310260`
- `0x140310570`
- `0x140314110`
- `0x1403141f0`
- `0x140317da0`
- `0x14031def0`
- `0x14031f9c0`
- `0x140322310`
- `0x140322820`
- `0x140323140`
- `0x140327af0`
- `0x140327bf0`
- `0x140327d00`
- `0x140327d80`
- `0x140329c10`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14030d927`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14030d927`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030d960`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030ddc4`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030de05`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030d960`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030ddc4`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030de05`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x14030d978`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x14030dddc`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x14030d978`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x14030dddc`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14030e959`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14030f3aa`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14030e959`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14030f3aa`
- `ntoskrnl!DbgPrintEx` at `0x14030ec09`
- `ntoskrnl!DbgPrintEx` at `0x14030ec09`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14030fe0e`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140342af1`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14030fe0e`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x140342af1`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14030fdb8`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140342a93`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14030fdb8`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x140342a93`
- `ntoskrnl!KeWaitForSingleObject` at `0x14030de8b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14030de8b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030f712`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030f9fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030fa75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030ff59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034262e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403426d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342c4e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030f712`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030f9fa`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030fa75`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030ff59`
- `ntoskrnl!ExFreePoolWithTag` at `0x14034262e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1403426d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x140342c4e`

## string_xrefs

- `0x14030dcd4`: `Create.c`
- `0x14030df08`: `Create.c`
- `0x14030e0b9`: `Create.c`
- `0x14030e126`: `Create.c`
- `0x14030e197`: `Create.c`
- `0x14030e25c`: `Create.c`
- `0x14030e30a`: `Create.c`
- `0x14030e381`: `Create.c`
- `0x14030e495`: `Create.c`
- `0x14030e6c7`: `Create.c`
- `0x14030e758`: `Create.c`
- `0x14030e819`: `Create.c`
- `0x14030ead9`: `Create.c`
- `0x14030eda3`: `Create.c`
- `0x14030ee14`: `Create.c`
- `0x14030eeac`: `Create.c`
- `0x14030ef1d`: `Create.c`
- `0x14030f00b`: `Create.c`
- `0x14030f20e`: `Create.c`
- `0x14030f412`: `Create.c`
- `0x14030f4ac`: `Create.c`
- `0x14030f532`: `Create.c`
- `0x14030f5d7`: `Create.c`
- `0x14030f7ae`: `Create.c`
- `0x14030f844`: `Create.c`
- `0x14030f90f`: `Create.c`
- `0x14030fcc6`: `Create.c`
- `0x14031009a`: `Create.c`
- `0x140310120`: `Create.c`
- `0x140310186`: `Create.c`
- `0x1403101b8`: `Create.c`
- `0x140310228`: `Create.c`
- `0x140342987`: `Create.c`
- `0x14030ebf8`: `Opening reparse index.\n`

## pseudocode

```c
__int64 __fastcall RefsCommonCreate(struct _IRP_CONTEXT *a1, PIRP Irp, struct _CREATE_CONTEXT *a3)
{
  struct _CREATE_CONTEXT *v3; // rdi
  PIRP v4; // rsi
  struct _IRP_CONTEXT *v5; // r13
  NTSTATUS v6; // r14d
  __int64 v7; // r15
  __int64 v8; // rdx
  char **v9; // rbx
  char *v10; // rdx
  unsigned __int16 v11; // r10
  __int16 v12; // r9
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 *v15; // rax
  NTSTATUS NewFile; // ebx
  unsigned int v17; // r9d
  int v18; // eax
  int v19; // eax
  int v20; // eax
  KPROCESSOR_MODE v21; // al
  char *v23; // rcx
  int v24; // eax
  void *v25; // rcx
  __int64 QuadPart; // rax
  __int64 v27; // rdx
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // rcx
  __int128 v31; // xmm0
  int v32; // eax
  __int64 v33; // rdx
  unsigned int v34; // r15d
  NTSTATUS v35; // r14d
  __int64 v36; // rcx
  __int64 v37; // rax
  __int16 v38; // cx
  __int128 *v39; // rcx
  __int128 v40; // xmm0
  unsigned __int64 *v41; // rcx
  NTSTATUS v42; // eax
  struct _IRP_CONTEXT *v43; // rcx
  __int64 v44; // rdx
  unsigned __int16 v45; // ax
  _WORD *v46; // rcx
  unsigned __int64 v47; // r9
  __int64 v48; // rax
  unsigned __int64 v49; // rcx
  int v50; // edx
  unsigned int v51; // edx
  int StartingNode; // eax
  struct _LCB *v53; // rcx
  unsigned int v54; // edx
  struct _UNICODE_STRING v55; // xmm6
  char v56; // bl
  __int64 v57; // rcx
  __int64 v58; // rcx
  bool v59; // zf
  int v60; // edx
  struct _FCB *v61; // r8
  PMRX_NET_ROOT pNetRoot; // rax
  __int16 v63; // ax
  __int16 v64; // dx
  __int16 v65; // cx
  int ReparsePointValue; // eax
  __int64 v67; // rcx
  struct _VCB *v68; // rbx
  struct _VCB *v69; // r15
  __int64 v70; // rcx
  _QWORD **v71; // rcx
  _QWORD *v72; // rax
  int v73; // eax
  __int64 v74; // rdx
  __int64 Scb; // rsi
  int v76; // eax
  NTSTATUS v77; // ebx
  __int64 v78; // rax
  IndexSCB *v80; // rcx
  __int64 v81; // rdx
  struct _LCB *v82; // rdx
  IndexSCB *v83; // rbx
  __int64 v84; // rdx
  int v85; // eax
  char v86; // al
  int v87; // ecx
  unsigned int v88; // ecx
  int v89; // eax
  int v90; // ebx
  __int64 v91; // rcx
  _DIR_INDEX_ENTRY *v92; // r14
  int v93; // edx
  unsigned int v94; // r9d
  bool v95; // sf
  struct _FILE_NETWORK_OPEN_INFORMATION *v96; // rdx
  IRP *v97; // r15
  unsigned __int8 v98; // r9
  void *v99; // rcx
  struct _LCB *v100; // rcx
  __int64 v101; // rcx
  __int64 v102; // rax
  __int64 v103; // rcx
  __int16 v104; // dx
  int v105; // edx
  ULONG v106; // r11d
  ULONG v107; // r10d
  struct _UNICODE_STRING *v108; // rdx
  struct _UNICODE_STRING *v109; // r8
  PWSTR Buffer; // rax
  __int64 v111; // rax
  struct _UNICODE_STRING *v112; // rax
  __int64 v113; // rcx
  __int64 v114; // rcx
  __int64 v115; // rsi
  __int16 v116; // cx
  __int64 v117; // rsi
  __int64 v118; // r15
  char v119; // cl
  __int64 v120; // rax
  __int64 v121; // rdx
  __int64 v122; // rsi
  void *v123; // rcx
  struct _CREATE_CONTEXT *v124; // r14
  __int64 v125; // rax
  __int64 v126; // rax
  IRP *v127; // rdx
  int v128; // [rsp+BCh] [rbp-184h]
  PIRP v129; // [rsp+C0h] [rbp-180h]
  unsigned __int16 v130; // [rsp+C8h] [rbp-178h] BYREF
  char v131; // [rsp+CCh] [rbp-174h]
  struct _LCB *ComponentInPath; // [rsp+D0h] [rbp-170h] BYREF
  PVOID P[2]; // [rsp+D8h] [rbp-168h] BYREF
  struct _UNICODE_STRING v134; // [rsp+E8h] [rbp-158h] BYREF
  struct _VCB *v135; // [rsp+F8h] [rbp-148h]
  __int64 v136; // [rsp+100h] [rbp-140h] BYREF
  __int64 v137; // [rsp+108h] [rbp-138h]
  struct _CREATE_CONTEXT *v138; // [rsp+110h] [rbp-130h]
  struct _UNICODE_STRING v139; // [rsp+118h] [rbp-128h] BYREF
  PECP_LIST EcpList; // [rsp+128h] [rbp-118h] BYREF
  struct _IRP_CONTEXT *v141; // [rsp+130h] [rbp-110h]
  PIRP v142; // [rsp+138h] [rbp-108h]
  struct _CREATE_CONTEXT *v143; // [rsp+140h] [rbp-100h]
  __int64 v144; // [rsp+148h] [rbp-F8h]
  __int64 v145[2]; // [rsp+150h] [rbp-F0h] BYREF
  struct _UNICODE_STRING v146; // [rsp+160h] [rbp-E0h] BYREF
  int v147; // [rsp+170h] [rbp-D0h]
  int v148; // [rsp+174h] [rbp-CCh]
  __int64 v149; // [rsp+178h] [rbp-C8h]
  __int64 v150; // [rsp+180h] [rbp-C0h]
  __int128 v151; // [rsp+188h] [rbp-B8h] BYREF
  _QWORD *v152; // [rsp+198h] [rbp-A8h]
  __int128 v153; // [rsp+1A8h] [rbp-98h]
  struct _UNICODE_STRING v154; // [rsp+1B8h] [rbp-88h]
  __int128 v155; // [rsp+1C8h] [rbp-78h] BYREF
  __int128 CompletionRoutine; // [rsp+1D8h] [rbp-68h]
  ULONG v157; // [rsp+1E8h] [rbp-58h]

  v3 = a3;
  v4 = Irp;
  v129 = Irp;
  v5 = a1;
  v141 = a1;
  v142 = Irp;
  v143 = a3;
  *(_OWORD *)v145 = 0;
  v6 = 0;
  v130 = 0;
  v7 = *((_QWORD *)a1 + 8);
  v135 = (struct _VCB *)v7;
  v144 = v7;
  v136 = 0;
  ComponentInPath = 0;
  v155 = 0;
  CompletionRoutine = 0;
  v157 = 0;
  P[0] = 0;
  v151 = 0;
  v134 = 0;
  v139 = 0;
  EcpList = 0;
  v8 = *((_QWORD *)a3 + 20);
  *((_QWORD *)a3 + 4) = *(_QWORD *)(v8 + 48);
  *((_DWORD *)a3 + 10) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL) + 16LL);
  *((_DWORD *)a3 + 11) = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(v8 + 8) + 8LL) + 20LL);
  *((_DWORD *)a3 + 12) = *(_DWORD *)(*(_QWORD *)(v8 + 8) + 16LL);
  *((_DWORD *)a3 + 16) = 0;
  *((_QWORD *)a3 + 16) = 0;
  if ( IoGetIrpExtraCreateParameter(v4, &EcpList) < 0 || !EcpList )
    goto LABEL_90;
  v9 = (char **)((char *)v3 + 200);
  FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_ATOMIC_CREATE, (PVOID *)v3 + 25, 0);
  if ( *((_QWORD *)v3 + 25) )
  {
    FsRtlAcknowledgeEcp(*((PVOID *)v3 + 25));
    v10 = *v9;
    v11 = *(_WORD *)*v9;
    if ( v11 >= 6u )
    {
      v12 = *((_WORD *)v10 + 1);
      if ( (v12 & 2) == 0 || v11 >= 0x10u )
      {
        if ( (v12 & 4) == 0 || v11 >= 0x18u && (v13 = *((_QWORD *)v10 + 2), v13 >= 0) && v13 <= *(_QWORD *)(v7 + 480) )
        {
          if ( (v12 & 8) == 0
            || v11 >= 0x20u && (v14 = *((_QWORD *)v10 + 3), v14 >= 0) && (v12 & 4) != 0 && v14 <= *((_QWORD *)v10 + 2) )
          {
            if ( (v12 & 0x10) == 0
              || v11 >= 0x28u
              && (v15 = (__int64 *)*((_QWORD *)v10 + 4), *v15 >= -1)
              && v15[1] >= -1
              && v15[2] >= -1
              && v15[3] >= -1 )
            {
              if ( (v12 & 0x80) != 0 && (v11 < 0x44u || (*((_DWORD *)v10 + 15) & 1) != 0 && v11 < 0x58u) )
              {
                NewFile = -1073741811;
                RefsCompleteCreateRequest(v5, v3, v129, 3221225485LL);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    20,
                    WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                    3221225485LL);
                }
                if ( !(_BYTE)RefsStatusDebugEnabled )
                  return (unsigned int)NewFile;
                v17 = 2222;
                goto LABEL_649;
              }
              if ( (v12 & 0x100) == 0 )
              {
                if ( (v12 & 0x60) != 0
                  || ((v12 & 0x80) == 0 ? (v18 = 0) : (v18 = *((_DWORD *)v10 + 15)),
                      (v18 & 0xFFFFFFFE) != 0
                   || ((v12 & 0x80) == 0 ? (LOBYTE(v19) = 0) : (v19 = *((_DWORD *)v10 + 15)),
                       (v19 & 1) == 0 ? (LOBYTE(v20) = 0) : (v20 = *((_DWORD *)v10 + 19)),
                       (v20 & 1) != 0 && (*((_DWORD *)v10 + 20) & 1) != 0 && (dword_14026887C & 1) == 0)) )
                {
                  NewFile = -1073741637;
                  RefsCompleteCreateRequest(v5, v3, v129, 3221225659LL);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      21,
                      WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                      3221225659LL);
                  }
                  if ( !(_BYTE)RefsStatusDebugEnabled )
                    return (unsigned int)NewFile;
                  v17 = 2251;
                  goto LABEL_649;
                }
              }
              if ( (v12 & 0x101) == 0 && (v12 & 4) != 0 )
              {
                NewFile = -1073741637;
                RefsCompleteCreateRequest(v5, v3, v129, 3221225659LL);
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    22,
                    WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                    3221225659LL);
                }
                if ( !(_BYTE)RefsStatusDebugEnabled )
                  return (unsigned int)NewFile;
                v17 = 2267;
                goto LABEL_649;
              }
              if ( (v12 & 8) == 0 || *((__int64 *)v10 + 3) <= 0 || (v12 & 1) != 0 )
              {
                v4 = v129;
              }
              else
              {
                v4 = v129;
                v21 = RefsEffectiveMode(v129, *((struct _IO_STACK_LOCATION **)v3 + 20));
                if ( !RefsPrivilegeCheck(
                        28,
                        (struct _SECURITY_SUBJECT_CONTEXT *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 20) + 8LL) + 8LL)
                                                           + 32LL),
                        v21) )
                {
                  RefsCompleteCreateRequest(v5, v3, v129, 3221225569LL);
                  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                  {
                    WPP_SF_d(
                      WPP_GLOBAL_Control->AttachedDevice,
                      23,
                      WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                      3221225569LL);
                  }
                  if ( (_BYTE)RefsStatusDebugEnabled )
                    RefsStatusDebug(-1073741727, 0, "Create.c", 0x8EBu);
                  return 3221225569LL;
                }
              }
              if ( (*v9)[2] < 0 )
                *((_WORD *)*v9 + 2) |= 0x80u;
              v23 = *v9;
              if ( (*v9)[2] >= 0 )
                LOBYTE(v24) = 0;
              else
                v24 = *((_DWORD *)v23 + 15);
              if ( (v24 & 1) != 0 )
              {
                *((_DWORD *)v23 + 16) |= 1u;
                *((_DWORD *)*v9 + 21) = 0;
              }
              goto LABEL_87;
            }
          }
        }
        v4 = v129;
      }
    }
    NewFile = -1073741811;
    RefsCompleteCreateRequest(v5, v3, v4, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return (unsigned int)NewFile;
    v17 = 2204;
LABEL_649:
    RefsStatusDebug(NewFile, 0, "Create.c", v17);
    return (unsigned int)NewFile;
  }
LABEL_87:
  FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_OPEN_PARAMETERS, (PVOID *)v3 + 26, 0);
  v25 = (void *)*((_QWORD *)v3 + 26);
  if ( v25 )
    FsRtlAcknowledgeEcp(v25);
  FsRtlFindExtraCreateParameter(EcpList, &GUID_ECP_QUERY_ON_CREATE, (PVOID *)v3 + 23, (ULONG *)v3 + 45);
  v6 = 0;
LABEL_90:
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 20) + 16LL) & 0x41) == 0x41
    || (QuadPart = v4->Overlay.AllocationSize.QuadPart, QuadPart > *(_QWORD *)(v7 + 480))
    || QuadPart < 0 )
  {
    v126 = *((_QWORD *)v5 + 1);
    if ( (v126 & 2) != 0 || *((_QWORD *)v3 + 17) )
    {
      NewFile = -1073741811;
      v127 = 0;
    }
    else
    {
      NewFile = -1073741811;
      if ( (v126 & 0x100000000LL) != 0 )
      {
        *((_QWORD *)v5 + 1) = v126 | 0x200000000LL;
        goto LABEL_643;
      }
      v127 = v4;
    }
    RefsCompleteRequest(v5, v127, -1073741811);
LABEL_643:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225485LL);
    }
    if ( !(_BYTE)RefsStatusDebugEnabled )
      return (unsigned int)NewFile;
    v17 = 2350;
    goto LABEL_649;
  }
  v27 = *((_QWORD *)v5 + 1);
  if ( (v27 & 1) == 0 )
    return RefsPostRequest(v5, v4, 1u, 0);
  if ( (v27 & 0x200000) != 0 )
  {
    KeWaitForSingleObject(&RefsEncryptionPendingEvent, Executive, 0, 0, 0);
    *((_QWORD *)v5 + 1) &= ~0x200000uLL;
    v27 = *((_QWORD *)v5 + 1);
  }
  if ( v4->Cancel )
  {
    RefsCompleteCreateRequest(v5, v3, v4, 3221225760LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225760LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741536, 0, "Create.c", 0x959u);
    return 3221225760LL;
  }
  v128 = 0;
  v138 = v3;
  v137 = (__int64)v3 + 16;
  LOWORD(v145[0]) = 0;
  *((_QWORD *)v5 + 18) = v3;
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 20) + 2LL) & 2) != 0 )
  {
    v27 |= 0x100uLL;
    *((_QWORD *)v5 + 1) = v27;
  }
  v28 = *((_QWORD *)v3 + 26);
  if ( v28 && *(_WORD *)v28 >= 8u && (*(_DWORD *)(v28 + 4) & 8) != 0 )
    *((_DWORD *)v3 + 36) |= 0x80u;
  if ( *(_DWORD *)(v7 + 3556) > RefsThrottleCreates )
    RefsProcessAsyncCloses(v7, 0, 2);
  if ( (*(_BYTE *)(*((_QWORD *)v3 + 20) + 2LL) & 2) != 0 )
  {
    LOBYTE(v27) = 1;
    RefsProcessAsyncCloses(v7, v27, 2);
    CLOSE_QUEUE::WaitForWorkers((CLOSE_QUEUE *)(v7 + 3512));
  }
  if ( (*((_DWORD *)v5 + 2) & 0x100LL) != 0 )
    RefsAcquireExclusiveVcb(v5, (struct _VCB *)v7, 1u);
  else
    RefsAcquireSharedVcb(v5, (struct _VCB *)v7, 1u);
  *((_DWORD *)v3 + 36) |= 0x800u;
  v30 = *((unsigned int *)v3 + 36);
  v31 = *(_OWORD *)(*((_QWORD *)v3 + 4) + 88LL);
  *(_OWORD *)v3 = v31;
  *(_OWORD *)v137 = v31;
  v32 = *(_DWORD *)(v7 + 24);
  if ( (v32 & 0x802) != 0 )
  {
    if ( (v32 & 0x800) != 0 && (*((_DWORD *)v5 + 2) & 0x100LL) == 0 )
    {
      RefsReleaseVcb(v5, (struct _VCB *)v7);
      *((_DWORD *)v3 + 36) &= ~0x800u;
      *((_QWORD *)v5 + 1) |= 0x100uLL;
      RefsAcquireExclusiveVcb(v5, (struct _VCB *)v7, 1u);
      *((_DWORD *)v3 + 36) |= 0x800u;
    }
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      NewFile = -1073741790;
    }
    else
    {
      NewFile = -1073741790;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225506LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741790, 0, "Create.c", 0x9D5u);
    if ( (*(_DWORD *)(v7 + 24) & 1) == 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741202;
      }
      else
      {
        NewFile = -1073741202;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221226094LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741202, 0, "Create.c", 0x9D8u);
      goto LABEL_221;
    }
    goto LABEL_215;
  }
  if ( (v32 & 0x20) != 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      NewFile = -1073741431;
    }
    else
    {
      NewFile = -1073741431;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225865LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741431, 0, "Create.c", 0x9E3u);
    goto LABEL_221;
  }
  v33 = *((_QWORD *)v3 + 20);
  if ( *(char *)(v33 + 2) >= 0 )
  {
    v30 = (unsigned int)v30 | 0x20;
    *((_DWORD *)v3 + 36) = v30;
  }
  if ( (*(_DWORD *)(v33 + 16) & 0x2000) != 0 )
  {
    v30 = (unsigned int)v30 | 0x40;
    *((_DWORD *)v3 + 36) = v30;
  }
  v34 = *(unsigned __int8 *)(v33 + 19);
  if ( (*((_DWORD *)v135 + 6) & 0x2000000) != 0 && (unsigned __int8)v34 <= 5u )
  {
    v35 = 53;
    if ( _bittest(&v35, v34) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741662;
      }
      else
      {
        NewFile = -1073741662;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225634LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741662, 0, "Create.c", 0xA09u);
      goto LABEL_221;
    }
  }
  else
  {
    v35 = 53;
  }
  if ( !*((_QWORD *)v3 + 25) )
    goto LABEL_180;
  if ( (_BYTE)v34 == 1 )
  {
    if ( !(unsigned int)Feature_TimestampsOnCreate__private_IsEnabledDeviceUsageNoInline(v30)
      || *(_WORD *)(*((_QWORD *)v3 + 25) + 2LL) != 0x2000 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741811;
      }
      else
      {
        NewFile = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225485LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741811, 0, "Create.c", 0xA20u);
      goto LABEL_221;
    }
    goto LABEL_180;
  }
  if ( (_BYTE)v34 != 2 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    {
      NewFile = -1073741637;
    }
    else
    {
      NewFile = -1073741637;
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225659LL);
    }
    if ( (_BYTE)RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741637, 0, "Create.c", 0xA26u);
LABEL_221:
    *((_DWORD *)v3 + 36) |= 0x100u;
    v43 = (struct _IRP_CONTEXT *)*((_QWORD *)v5 + 13);
    v35 = *((_DWORD *)v43 + 4);
    if ( v35 >= 0 )
    {
      if ( NewFile < 0 && RefsIsTransactionActive(v43) )
      {
        v35 = NewFile;
      }
      else
      {
        v35 = 0;
        RefsCheckpointCurrentTransaction(v5);
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( v35 >= 0 )
      {
LABEL_522:
        v95 = NewFile < 0;
        if ( !NewFile )
        {
          v96 = (struct _FILE_NETWORK_OPEN_INFORMATION *)*((_QWORD *)v3 + 17);
          if ( v96 )
            RefsFillNetworkOpenInfo(v5, v96, *((struct _SCB **)v3 + 13));
          if ( *((_QWORD *)v3 + 23) )
            RefsQueryInformationForCreate(v5, v3);
          RefsCheckpointCurrentTransaction(v5);
          v95 = 0;
        }
        if ( !v95 )
          RefsFlushForWriteThrough(v5, *((_QWORD *)v3 + 12), 0);
        v97 = v129;
        goto LABEL_532;
      }
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          54,
          WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
          (unsigned int)v35);
    }
    if ( v35 < 0 )
      goto LABEL_665;
    goto LABEL_522;
  }
LABEL_180:
  if ( (*((_DWORD *)v135 + 6) & 1) == 0 || !RefsPingVolume(v5, v135, 0) )
    goto LABEL_668;
  if ( (v34 & 0xFA) == 0 && (_BYTE)v34 != 1 || (*(_DWORD *)(*((_QWORD *)v3 + 20) + 16LL) & 8) != 0 )
    *((_DWORD *)v5 + 1) |= 0x10000u;
  v36 = *((_QWORD *)v3 + 4);
  v37 = *(_QWORD *)(v36 + 64);
  if ( v37 )
  {
    *(_QWORD *)(v36 + 16) = *(_QWORD *)(v37 + 16);
    if ( *(_WORD *)v3 )
    {
      if ( **((_WORD **)v3 + 1) == 58 && (unsigned __int8)(v34 - 2) <= 1u )
        *((_DWORD *)v5 + 1) |= 0x10000u;
    }
  }
  if ( (*((_DWORD *)v3 + 36) & 0x40) != 0 )
  {
    v38 = *(_WORD *)v3;
    if ( ((*(_WORD *)v3 - 8) & 0xFFFD) != 0 )
    {
      if ( ((v38 - 16) & 0xFFFD) != 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          NewFile = -1073741811;
        }
        else
        {
          NewFile = -1073741811;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            33,
            WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225485LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741811, 0, "Create.c", 0xAA0u);
        goto LABEL_221;
      }
      v59 = v38 == 16;
      v39 = *(__int128 **)(*((_QWORD *)v3 + 4) + 96LL);
      if ( v59 )
        v40 = *v39;
      else
        v40 = *(__int128 *)((char *)v39 + 2);
    }
    else
    {
      v59 = v38 == 8;
      v41 = *(unsigned __int64 **)(*((_QWORD *)v3 + 4) + 96LL);
      if ( !v59 )
        v41 = (unsigned __int64 *)((char *)v41 + 2);
      NewFile = RefsUnpackFileId(*v41, (struct _REFS_FILE_REFERENCE *)&v151);
      if ( NewFile < 0 )
        goto LABEL_214;
      v40 = v151;
    }
    *(_QWORD *)(*((_QWORD *)v3 + 4) + 96LL) = 0;
    *(_WORD *)(*((_QWORD *)v3 + 4) + 88LL) = 0;
    v153 = v40;
    v42 = RefsOpenFcbById(v5, (__int64)&RefsEmptyString, 0, (__int64)v3);
    NewFile = v42;
    if ( v42 != 259 && v42 != 871 )
    {
      if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 20) + 8LL) + 8LL) + 12LL) & 1) != 0 )
        *((_DWORD *)v3 + 36) &= ~0x10u;
      else
        *((_DWORD *)v3 + 36) |= 0x10u;
      *(_QWORD *)(*((_QWORD *)v3 + 4) + 96LL) = *((_QWORD *)v3 + 1);
      *(_WORD *)(*((_QWORD *)v3 + 4) + 88LL) = *(_WORD *)v3;
    }
    goto LABEL_214;
  }
  v44 = *((_QWORD *)v3 + 4);
  v45 = *(_WORD *)(v44 + 88);
  if ( v45 > 2u )
  {
    v46 = *(_WORD **)(v44 + 96);
    if ( v46[1] == 92 && *v46 == 92 )
    {
      *(_WORD *)(v44 + 88) = v45 - 2;
      memmove(
        *(void **)(*((_QWORD *)v3 + 4) + 96LL),
        (const void *)(*(_QWORD *)(*((_QWORD *)v3 + 4) + 96LL) + 2LL),
        *(unsigned __int16 *)(*((_QWORD *)v3 + 4) + 88LL));
      v44 = *((_QWORD *)v3 + 4);
      if ( *(_WORD *)(v44 + 88) > 2u && *(_WORD *)(*(_QWORD *)(v44 + 96) + 2LL) == 92 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
        {
          NewFile = -1073741773;
        }
        else
        {
          NewFile = -1073741773;
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            34,
            WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
            3221225523LL);
        }
        if ( (_BYTE)RefsStatusDebugEnabled )
          RefsStatusDebug(-1073741773, 0, "Create.c", 0xAE7u);
        goto LABEL_221;
      }
    }
  }
  v47 = *(unsigned __int16 *)(v44 + 88);
  if ( (_WORD)v47 )
  {
    if ( *(_QWORD *)(v44 + 64) && **(_WORD **)(v44 + 96) == 92 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741811;
      }
      else
      {
        NewFile = -1073741811;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225485LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741811, 0, "Create.c", 0xAF7u);
      goto LABEL_221;
    }
    if ( *(_WORD *)(*(_QWORD *)(v44 + 96) + 2 * (v47 >> 1) - 2) == 92 && (unsigned int)v47 > 2 )
    {
      *((_DWORD *)v3 + 36) |= 8u;
      *(_WORD *)(v44 + 88) -= 2;
      v48 = *((_QWORD *)v3 + 4);
      v49 = *(unsigned __int16 *)(v48 + 88);
      if ( (_WORD)v49 )
      {
        if ( *(_WORD *)(*(_QWORD *)(v48 + 96) + 2 * (v49 >> 1) - 2) == 92 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            NewFile = -1073741773;
          }
          else
          {
            NewFile = -1073741773;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              36,
              WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
              3221225523LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741773, 0, "Create.c", 0xB0Du);
          goto LABEL_221;
        }
      }
    }
  }
  v50 = *((_DWORD *)v3 + 36);
  if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 20) + 8LL) + 8LL) + 12LL) & 1) != 0 )
    v51 = v50 & 0xFFFFFFEF;
  else
    v51 = v50 | 0x10;
  *((_DWORD *)v3 + 36) = v51;
  StartingNode = RefsFindStartingNode(v5, (__int64)&v130, (__int64)&ComponentInPath, (__int64)&v136, v3);
  NewFile = StartingNode;
  if ( StartingNode < 0 || !v134.Length )
    goto LABEL_214;
  v128 = StartingNode;
  v147 = StartingNode;
  *((_DWORD *)v3 + 36) |= 0x2000u;
  v54 = *((_DWORD *)v3 + 36);
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        v55 = 0;
        LODWORD(v29) = v54 & 0x80000;
        if ( (v54 & 0x80000) == 0 && ((v54 & 0x200) == 0 || (*(_DWORD *)(*((_QWORD *)v3 + 12) + 152LL) & 0x400) == 0) )
          goto LABEL_312;
        v56 = 1;
        v131 = 1;
        if ( !(_DWORD)v29 )
        {
          RefsLookupOpenReparseEcp(v53, v4, v3, *(unsigned int *)(*((_QWORD *)v3 + 12) + 156LL), 0);
          v57 = *(_QWORD *)(*((_QWORD *)v3 + 12) + 88LL);
          if ( !*(_QWORD *)(v57 + 248)
            && *(_QWORD *)(v57 + 256)
            && (unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*((unsigned int *)v3 + 44)) )
          {
            LODWORD(v29) = 1;
            v58 = *((_QWORD *)v3 + 24);
            if ( !v58 )
            {
LABEL_276:
              *((_DWORD *)v3 + 36) |= 0x20000u;
              goto LABEL_278;
            }
            v59 = (*(_DWORD *)(v58 + 20) & 2) == 0;
          }
          else
          {
            LOBYTE(v29) = 0;
            v58 = *((_QWORD *)v3 + 24);
            if ( !v58 )
              goto LABEL_277;
            v59 = (*(_DWORD *)(v58 + 20) & 0x10) == 0;
          }
          if ( v59 )
            goto LABEL_276;
LABEL_277:
          *((_DWORD *)v3 + 36) &= ~0x20000u;
LABEL_278:
          v60 = *((_DWORD *)v3 + 36);
          if ( (_BYTE)v29 )
          {
            if ( !v58 || (*(_DWORD *)(v58 + 20) & 4) == 0 )
              goto LABEL_285;
          }
          else if ( v58 && (*(_DWORD *)(v58 + 20) & 0x10) == 0 )
          {
LABEL_285:
            v54 = v60 | 0x40000;
            goto LABEL_286;
          }
          v54 = v60 & 0xFFFBFFFF;
LABEL_286:
          *((_DWORD *)v3 + 36) = v54;
          if ( (v54 & 0x60000) != 0 )
          {
            v56 = 0;
            v131 = 0;
            if ( (v54 & 0x20000) == 0 || (v54 & 0x40000) == 0 )
            {
              v54 |= 0x80000u;
              *((_DWORD *)v3 + 36) = v54;
              v55 = v134;
              v154 = v134;
            }
          }
        }
        if ( v56 )
        {
          if ( (v54 & 0x10) != 0 )
          {
            v61 = (struct _FCB *)*((_QWORD *)v3 + 12);
            pNetRoot = v61->pNetRoot;
            if ( pNetRoot[2].pSrvCall || !pNetRoot[2].Context )
              RefsAccessCheck(v5, v3, v61, 0, v4, 0x120089u, 1u, 0, 0);
            else
              RefsAccessCheck(v5, v3, v61, 0, v4, 0x20u, 1u, 0, 1u);
          }
          if ( *((_QWORD *)v3 + 17) )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 260);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(260, 0, "Create.c", 0xC28u);
            NewFile = 260;
            goto LABEL_221;
          }
          v63 = *((_WORD *)v3 + 33);
          v64 = *((_WORD *)v3 + 32);
          v65 = v63 + v64;
          if ( v63 )
          {
            v65 += 4;
          }
          else if ( v64 )
          {
            v65 += 2;
          }
          if ( v134.Length )
            v65 += 2;
          ReparsePointValue = RefsGetReparsePointValue(v5, v134.Length + v65, 0);
          NewFile = ReparsePointValue;
          if ( ReparsePointValue < 0 || ReparsePointValue == 260 )
            goto LABEL_214;
        }
LABEL_312:
        v67 = *(_QWORD *)(*((_QWORD *)v3 + 12) + 88LL);
        if ( *(_QWORD *)(v67 + 248) || !*(_QWORD *)(v67 + 256) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            NewFile = -1073741766;
          }
          else
          {
            NewFile = -1073741766;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              38,
              WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
              3221225530LL);
          }
          if ( !(_BYTE)RefsStatusDebugEnabled )
            goto LABEL_221;
          v94 = 3171;
LABEL_514:
          RefsStatusDebug(-1073741766, 0, "Create.c", v94);
          goto LABEL_221;
        }
        NewFile = RefsDissectName(&v134, &v139, &v134);
        if ( NewFile < 0 )
          goto LABEL_214;
        v68 = v135;
        if ( (unsigned __int8)RefsIsOpeningReparseIndex(v135, (char *)v3 + 16, v145, v130) && *((_QWORD *)v68 + 6) )
        {
          *(_QWORD *)&v146.Length = 0;
          v146.Buffer = 0;
          DbgPrintEx(0x95u, 3u, "Opening reparse index.\n");
          RefsReleaseFcbWithPaging(v5, *((struct _FCB **)v3 + 12));
          v69 = v135;
          *((_QWORD *)v3 + 12) = *(_QWORD *)(*((_QWORD *)v135 + 6) + 136LL);
          *((_DWORD *)v3 + 36) &= ~0x400u;
          RefsAcquireFcbWithPaging(v5, *(_QWORD *)(*((_QWORD *)v69 + 6) + 136LL), 0, 1);
          *(_DWORD *)(*((_QWORD *)v69 + 6) + 300LL) |= 0x80u;
          v70 = *((_QWORD *)v3 + 12);
          v148 = 0;
          v71 = (_QWORD **)(v70 + 32);
          v72 = *v71;
          v152 = *v71;
          while ( v72 != v71 && (*((_DWORD *)v72 - 7) & 2) != 0 )
            v72 = (_QWORD *)*v72;
          v73 = RefsOpenAttributeInExistingFile(v5, &v146, 128, 131074, v3);
          NewFile = v73;
          if ( v73 > -1 && (unsigned int)(v73 - 259) > 1 && v73 != 871 )
          {
            v74 = *((_QWORD *)v3 + 13);
            *((_DWORD *)v3 + 36) |= 0x100u;
            if ( (*(_DWORD *)(v74 + 152) & 0x20) == 0 )
              RefsUpdateScbFromAttribute(v5, (struct _SCB *)v74, 0);
          }
          goto LABEL_214;
        }
        if ( v139.Length > 0x1FEu )
        {
          if ( v134.Length )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              NewFile = -1073741766;
            }
            else
            {
              NewFile = -1073741766;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                40,
                WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                3221225530LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741766, 0, "Create.c", 0xCC0u);
          }
          else
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              NewFile = -1073741773;
            }
            else
            {
              NewFile = -1073741773;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                39,
                WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                3221225523LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741773, 0, "Create.c", 0xCBCu);
          }
          goto LABEL_221;
        }
        if ( v139.Length == 2 && *v139.Buffer == 46 )
        {
          if ( v134.Length )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              NewFile = -1073741766;
            }
            else
            {
              NewFile = -1073741766;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                41,
                WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                3221225530LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741766, 0, "Create.c", 0xCCEu);
          }
          else
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              NewFile = -1073741773;
            }
            else
            {
              NewFile = -1073741773;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                42,
                WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                3221225523LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741773, 0, "Create.c", 0xCD6u);
          }
          goto LABEL_221;
        }
        Scb = RefsCreateScb(v5, *((_QWORD *)v3 + 12), 160, 0, 0, 0);
        v76 = RefsInitializeFileFromDisk(v5, Scb, 2, 0);
        v77 = v76;
        if ( v76 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              43,
              WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
              (unsigned int)v76);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v77, v5, "Create.c", 0xCF3u);
          RefsRaiseStatusInternal(v5, v77, v29);
LABEL_658:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              52,
              WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
              3221225688LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741608, v5, "Create.c", 0xE7Bu);
          RefsRaiseStatusInternal(v5, -1073741608, v29);
LABEL_665:
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(v35, v5, "Create.c", 0xEE8u);
          RefsRaiseStatusInternal(v5, v35, v29);
LABEL_668:
          *((_DWORD *)v5 + 1) |= 0x200000u;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              32,
              WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
              3221225688LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741608, v5, "Create.c", 0xA3Au);
          RefsRaiseStatusInternal(v5, -1073741608, v29);
          __debugbreak();
          JUMPOUT(0x14031024BLL);
        }
        if ( (*(_DWORD *)(*(_QWORD *)(Scb + 136) + 8LL) & 0x400000) != 0 )
        {
          v78 = *((_QWORD *)v3 + 26);
          if ( v78 && *(_WORD *)v78 >= 8u && (*(_DWORD *)(v78 + 4) & 0x10) != 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
            {
              NewFile = -1073740614;
            }
            else
            {
              NewFile = -1073740614;
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                44,
                WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
                3221226682LL);
            }
            if ( (_BYTE)RefsStatusDebugEnabled )
              RefsStatusDebug(-1073740614, 0, "Create.c", 0xD09u);
            goto LABEL_221;
          }
        }
        v80 = (IndexSCB *)*((_QWORD *)v3 + 16);
        if ( v80 && (*(_DWORD *)(*((_QWORD *)v80 + 17) + 8LL) & 0x100LL) == 0 && !v134.Length && *((_DWORD *)v3 + 21) )
          IndexSCB::EnsureDirectoryNormalizedName(v80, v5);
        v81 = *((_QWORD *)v3 + 16);
        if ( v81 && *(_WORD *)(v81 + 392) && !*(_WORD *)(Scb + 392) )
        {
          RefsUpdateNormalizedName(v5, v81, Scb, 0);
LABEL_387:
          v82 = ComponentInPath;
          goto LABEL_388;
        }
        v82 = ComponentInPath;
        if ( !ComponentInPath )
          goto LABEL_397;
        if ( (*(_DWORD *)(*((_QWORD *)ComponentInPath + 6) + 8LL) & 0x100LL) == 0 && !v134.Length )
        {
          IndexSCB::EnsureDirectoryNormalizedName((IndexSCB *)Scb, v5);
          goto LABEL_387;
        }
LABEL_388:
        if ( v82 )
        {
          if ( (*((_DWORD *)v82 + 1) & 0x10) == 0 && (*(_DWORD *)(*((_QWORD *)v82 + 6) + 8LL) & 0x100LL) == 0 )
          {
            if ( *((_DWORD *)v3 + 21) )
            {
              if ( !v134.Length )
              {
                v83 = (IndexSCB *)*((_QWORD *)v82 + 3);
                if ( v83 )
                {
                  IndexSCB::EnsureDirectoryNormalizedName(v83, v5);
                  if ( !*(_WORD *)(Scb + 392) )
                    RefsUpdateNormalizedName(v5, v83, Scb, 0);
                  RefsInsertPrefixHashEntry(v5, ComponentInPath, *((_DWORD *)v3 + 21), *((_DWORD *)v3 + 20));
                }
              }
            }
          }
        }
LABEL_397:
        v84 = *((_QWORD *)v3 + 16);
        if ( v84 )
          *((_DWORD *)v3 + 36) &= ~0x400u;
        if ( (*((_DWORD *)v3 + 36) & 0x2000) == 0 )
        {
          RefsReleaseFcbWithPaging(v5, *(struct _FCB **)(v84 + 136));
          *((_QWORD *)v3 + 16) = 0;
        }
        if ( (*((_DWORD *)v3 + 36) & 0x10) != 0 )
          RefsAccessCheck(v5, v3, *((struct _FCB **)v3 + 12), 0, v129, 0x20u, 1u, 0, 1u);
        if ( !RefsIsFileNameValid(&v139, 0) )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
          {
            NewFile = -1073741773;
          }
          else
          {
            NewFile = -1073741773;
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              45,
              WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
              3221225523LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741773, 0, "Create.c", 0xD8Eu);
          goto LABEL_221;
        }
        v85 = *((_DWORD *)v3 + 36);
        LOBYTE(v29) = (v85 & 0x20) != 0
                   && ((v85 & 0x80u) != 0 || (*(_DWORD *)(*(_QWORD *)(Scb + 136) + 8LL) & 0x400000) == 0);
        v86 = RefsLookupEntry(v5, Scb, v29, &v139, &v155, P);
        v87 = *((_DWORD *)v3 + 36);
        if ( v86 )
          v88 = v87 | 0x4000;
        else
          v88 = v87 & 0xFFFFBFFF;
        *((_DWORD *)v3 + 36) = v88;
        if ( RefsIsTransactionActive(v5) )
        {
          RefsCheckpointCurrentTransaction(v53);
          if ( *((_QWORD *)v5 + 6) )
            RefsReleaseSharedResources(v5);
        }
        v54 = *((_DWORD *)v3 + 36);
        v89 = v54 & 0x80000;
        if ( (v54 & 0x4000) == 0 )
          break;
        if ( !v89 || (v54 & 0x20000) != 0 )
        {
          if ( (v54 & 0x20) != 0 )
            memmove(v139.Buffer, *(const void **)((char *)P[0] + 84), v139.Length);
          goto LABEL_428;
        }
        v134 = v55;
        v4 = v129;
      }
      if ( !v89 || (v54 & 0x40000) != 0 )
        break;
      v134 = v55;
      v4 = v129;
    }
    if ( v134.Length || (*(_BYTE *)(*((_QWORD *)v3 + 20) + 2LL) & 4) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741766;
      }
      else
      {
        NewFile = -1073741766;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225530LL);
      }
      if ( !(_BYTE)RefsStatusDebugEnabled )
        goto LABEL_221;
      v94 = 3582;
      goto LABEL_514;
    }
    v91 = *((_QWORD *)v3 + 12);
    if ( (*(_DWORD *)(v91 + 152) & 0x400) != 0
      && !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(*(unsigned int *)(v91 + 156)) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741183;
      }
      else
      {
        NewFile = -1073741183;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221226113LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741183, 0, "Create.c", 0xE0Bu);
      goto LABEL_221;
    }
    if ( (_BYTE)v34 == 1 || (_BYTE)v34 == 4 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741772;
      }
      else
      {
        NewFile = -1073741772;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225524LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741772, 0, "Create.c", 0xE10u);
      goto LABEL_221;
    }
    v53 = (struct _LCB *)*(unsigned int *)(*((_QWORD *)v3 + 20) + 16LL);
    if ( ((unsigned __int8)v53 & 1) != 0 && (_BYTE)v34 == 5 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741773;
      }
      else
      {
        NewFile = -1073741773;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225523LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741773, 0, "Create.c", 0xE18u);
      goto LABEL_221;
    }
    if ( (*((_DWORD *)v135 + 6) & 0x2000000) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741662;
      }
      else
      {
        NewFile = -1073741662;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225634LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741662, 0, "Create.c", 0xE1Du);
      goto LABEL_221;
    }
LABEL_428:
    *((_DWORD *)v3 + 36) &= ~0x80000u;
    v90 = *((_DWORD *)v3 + 36);
    if ( !v134.Length )
      break;
    v92 = (_DIR_INDEX_ENTRY *)P[0];
    v151 = *(_OWORD *)P[0];
    *((_QWORD *)v3 + 16) = Scb;
    ComponentInPath = (struct _LCB *)RefsOpenNextComponentInPath(
                                       v5,
                                       (struct _SCB *)Scb,
                                       v92,
                                       (__int64)v3,
                                       (__int64)&v136);
    ExFreePoolWithTag(v92, 0);
    P[0] = 0;
    *((_DWORD *)v3 + 36) |= 0x200u;
    v93 = *((_DWORD *)v3 + 36);
    v53 = ComponentInPath;
    if ( ComponentInPath && (*((_DWORD *)ComponentInPath + 1) & 1) != 0 || !*(_DWORD *)(*((_QWORD *)v3 + 12) + 176LL) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741738;
      }
      else
      {
        NewFile = -1073741738;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225558LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741738, 0, "Create.c", 0xE5Cu);
      goto LABEL_221;
    }
    if ( ComponentInPath )
      v54 = v93 & 0xFFFFDFFF;
    else
      v54 = v93 | 0x2000;
    *((_DWORD *)v3 + 36) = v54;
    v35 = 53;
    v4 = v129;
  }
  if ( (v90 & 0x10000) != 0 && !(unsigned __int8)RefsCommonCreate_::_517_::_lambda_1_::operator()(v53, v3, Scb, &v139) )
    goto LABEL_658;
  if ( (v90 & 0x4000) != 0 )
  {
    *((_QWORD *)v3 + 16) = Scb;
    NewFile = RefsOpenFileHighLevel(v5, (__int64)&v139, (__int64)v145, v130, v3, (__int64)&v136);
  }
  else
  {
    if ( (v90 & 0x400) != 0 )
      RefsConvertSharedFcbToExclusiveInCreate(v5, v3, ComponentInPath, v139.Length);
    *((_QWORD *)v3 + 16) = Scb;
    if ( *((_QWORD *)v3 + 17) )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        NewFile = -1073741772;
      }
      else
      {
        NewFile = -1073741772;
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids, 3221225524LL);
      }
      if ( (_BYTE)RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741772, 0, "Create.c", 0xE9Au);
      *((_DWORD *)v3 + 36) |= 2u;
    }
    else
    {
      NewFile = RefsCreateNewFile(v5, v137, (__int64)&v139, (__int64)v145, v130, (__int64)v3, (__int64)&v136);
      *((_DWORD *)v3 + 36) |= 2u;
    }
  }
LABEL_214:
  v6 = v128;
LABEL_215:
  if ( !NewFile && (!v6 || v6 == 264) )
    NewFile = v6;
  if ( NewFile != 259 && NewFile != 871 )
    goto LABEL_221;
  v5 = 0;
  v141 = 0;
  v97 = 0;
  v129 = 0;
  v142 = 0;
  v3 = 0;
  v143 = 0;
LABEL_532:
  if ( P[0] )
    ExFreePoolWithTag(P[0], 0);
  _FILE_NAME::CleanupFileName((_FILE_NAME *)&v155);
  if ( NewFile != 259 )
  {
    if ( NewFile != 871 )
    {
      RefsReleaseSharedParentFcb(v5, v3);
      if ( NewFile >= 0 && NewFile != 260 )
      {
        v99 = (void *)*((_QWORD *)v138 + 1);
        if ( v99 && v99 != *(void **)(v137 + 8) && v99 != *(void **)(*((_QWORD *)v3 + 4) + 96LL) )
          ExFreePoolWithTag(v99, 0);
        if ( *((_QWORD *)v3 + 17) )
        {
          v114 = *((_QWORD *)v3 + 13);
          if ( !*(_DWORD *)(v114 + 160) )
            RefsAddScbToDelayedClose((struct _SCB *)v114);
          v97->IoStatus.Information = 56;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              55,
              WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids,
              (unsigned int)NewFile);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(NewFile, 0, "Create.c", 0x100Bu);
          v97->IoStatus.Status = NewFile;
        }
        else
        {
          v100 = *(struct _LCB **)(*((_QWORD *)v3 + 14) + 72LL);
          ComponentInPath = v100;
          if ( (*(_BYTE *)(*((_QWORD *)v3 + 20) + 2LL) & 2) != 0 )
            RefsDeleteInternalAttributeStream(v5, *((struct _SCB **)v3 + 13), 1u, v98);
          if ( (*((_DWORD *)v3 + 36) & 0x20) != 0 )
            *(_DWORD *)(*((_QWORD *)v3 + 14) + 4LL) |= 1u;
          if ( (*((_DWORD *)v3 + 36) & 0x80u) != 0 )
            *(_DWORD *)(*((_QWORD *)v3 + 14) + 4LL) |= 0x4000000u;
          if ( (*((_DWORD *)v3 + 36) & 0x10) != 0 )
            *(_DWORD *)(*((_QWORD *)v3 + 14) + 4LL) |= 0x80u;
          RefsSetCcbAccessFlags((__int64)v100, (__int64)v97, (__int64)v3);
          if ( (*(_DWORD *)(*((_QWORD *)v3 + 20) + 16LL) & 0x1000) != 0 )
          {
            v101 = *((_QWORD *)v3 + 14);
            if ( (*(_BYTE *)(v101 + 4) & 0xA) != 0xA )
            {
              *((_DWORD *)v3 + 36) |= 4u;
              *(_DWORD *)(v101 + 4) |= 0x40000u;
            }
          }
          if ( (*(_DWORD *)(*((_QWORD *)v3 + 14) + 4LL) & 8) == 0
            && ((v102 = *((_QWORD *)v3 + 25)) == 0 || !_bittest16((const signed __int16 *)(v102 + 2), 0xAu))
            && (v103 = *((_QWORD *)v3 + 13), *(_WORD *)(v103 + 224))
            && ((v104 = *(_WORD *)(v103 + 216), v104 == 128) || v104 == 176)
            && (*(_DWORD *)(v103 + 300) & 0xA00) != 0
            || (v103 = *((_QWORD *)v3 + 13), (*(_DWORD *)(v103 + 152) & 0x4000) != 0) )
          {
            v105 = *(_DWORD *)(v103 + 300);
            v106 = 512;
            if ( (v105 & 0x200) != 0 )
            {
              v107 = 6;
            }
            else
            {
              v107 = 8;
              v106 = (*(_DWORD *)(v103 + 152) >> 4) & 0x400 | 0x800;
              if ( (v105 & 0x800) == 0 )
                v106 = (*(_DWORD *)(v103 + 152) >> 4) & 0x400;
            }
            v108 = 0;
            v109 = (struct _UNICODE_STRING *)*((_QWORD *)v3 + 14);
            Buffer = v109[4].Buffer;
            if ( Buffer )
            {
              v111 = *((_QWORD *)Buffer + 3);
              if ( v111 )
              {
                v112 = (struct _UNICODE_STRING *)(v111 + 392);
                if ( v112->Length )
                  v108 = v112;
              }
            }
            RefsReportDirNotify(
              (struct _IRP_CONTEXT *)v103,
              v135,
              v109 + 1,
              v109[2].Length,
              (struct _UNICODE_STRING *)(v103 + 224),
              v108,
              v106,
              v107,
              0);
          }
          *(_DWORD *)(*((_QWORD *)v3 + 13) + 300LL) &= 0xFFFFF1FF;
          v113 = *((_QWORD *)v3 + 13);
          if ( (*(_DWORD *)(v113 + 152) & 0x4000) != 0 )
            _InterlockedAnd((volatile signed __int32 *)(v113 + 152), 0xFFFFBFFF);
        }
        goto LABEL_626;
      }
      if ( (*(_DWORD *)(*((_QWORD *)v3 + 20) + 16LL) & 0x10000) != 0 && NewFile != -1073739511 )
      {
        v115 = *((_QWORD *)v3 + 13);
        if ( v115 )
        {
          if ( ((v116 = *(_WORD *)(v115 + 216), v116 == 128) || v116 == 176)
            && *(_WORD *)v115 == 2053
            && *(_QWORD *)(*(_QWORD *)(v115 + 144) + 72LL) != v115
            || v116 == 160
            && *(_WORD *)(v115 + 224) == 8
            && !memcmp(*(const void **)(v115 + 232), L"$I30", 8u)
            && (unsigned __int16)(*(_WORD *)v115 - 2051) <= 1u )
          {
            FsRtlCheckOplockEx((POPLOCK)(v115 + 88), *((PIRP *)v5 + 9), 4u, 0, 0, 0);
            v117 = *((_QWORD *)v3 + 13);
            v118 = *(_QWORD *)(v117 + 144);
            if ( (*(_DWORD *)(v118 + 24) & 0x4000005) != 1
              || *(_WORD *)v117 != 2053
              || (*(_DWORD *)(v117 + 300) & 0x40) != 0
              || *(char *)(*(_QWORD *)(v117 + 136) + 8LL) < 0 )
            {
              goto LABEL_606;
            }
            if ( (*(_DWORD *)(v117 + 152) & 0x20) == 0 )
              goto LABEL_598;
            if ( FsRtlOplockIsFastIoPossible((POPLOCK)(v117 + 88)) )
            {
              if ( *(__int16 *)(v117 + 256) < 0
                || (v120 = *(_QWORD *)(v117 + 384)) != 0 && *(_BYTE *)(v120 + 16)
                || (*(_DWORD *)(v118 + 24) & 0x2000000) != 0
                || (*(_BYTE *)(*(_QWORD *)(v117 + 136) + 8LL) & 0x20) != 0 )
              {
LABEL_598:
                v119 = 2;
              }
              else
              {
                v119 = 1;
              }
            }
            else
            {
LABEL_606:
              v119 = 0;
            }
            *(_BYTE *)(*((_QWORD *)v3 + 13) + 5LL) = v119;
          }
        }
      }
      if ( (*((_DWORD *)v3 + 36) & 0x100) != 0 )
        RefsBackoutFailedOpens(
          v5,
          *(PFILE_OBJECT *)(*((_QWORD *)v3 + 20) + 48LL),
          *((struct _FCB **)v3 + 12),
          *((struct _SCB **)v3 + 13),
          (__int64)v3 + 112);
      if ( *((_QWORD *)v3 + 12) )
      {
        if ( !RefsIsTriagePending(v5) )
        {
          v121 = *((_QWORD *)v3 + 13);
          if ( v121 )
          {
            v149 = *((_QWORD *)v3 + 13);
          }
          else
          {
            v121 = *((_QWORD *)v3 + 12);
            v150 = v121;
          }
          RefsTeardownStructures(v5, v121, v136);
        }
        *((_QWORD *)v3 + 13) = 0;
        *((_QWORD *)v3 + 12) = 0;
      }
      if ( NewFile == -1073741432 || NewFile == -1073741400 || NewFile == -1073741608 || NewFile == 260 )
      {
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 20) + 8LL) + 8LL) + 16LL) = *((_DWORD *)v3 + 10);
        *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 20) + 8LL) + 8LL) + 20LL) = *((_DWORD *)v3 + 11);
        *(_DWORD *)(*(_QWORD *)(*((_QWORD *)v3 + 20) + 8LL) + 16LL) = *((_DWORD *)v3 + 12);
      }
      v122 = v137;
      v123 = *(void **)(v137 + 8);
      v124 = v138;
      if ( v123 && *((void **)v138 + 1) != v123 )
      {
        ExFreePoolWithTag(v123, 0);
        *(_QWORD *)(v122 + 8) = 0;
      }
      *(_OWORD *)(*((_QWORD *)v3 + 4) + 88LL) = *(_OWORD *)v124;
      v97 = v129;
LABEL_626:
      if ( (*((_DWORD *)v3 + 36) & 0x800) != 0 && !_bittest64((const signed __int64 *)v5 + 1, 0x25u) )
        RefsReleaseVcb(v5, v135);
    }
    if ( NewFile != 871 )
    {
      v125 = *((_QWORD *)v5 + 1);
      if ( (v125 & 2) != 0 || *((_QWORD *)v3 + 17) )
      {
        RefsCompleteRequest(v5, 0, NewFile);
      }
      else if ( (v125 & 0x100000000LL) != 0 )
      {
        *((_QWORD *)v5 + 1) = v125 | 0x200000000LL;
      }
      else
      {
        RefsCompleteRequest(v5, v97, NewFile);
      }
    }
  }
  return (unsigned int)NewFile;
}

```

## disassembly

```asm
0x14030d820  mov     r11, rsp
0x14030d823  push    rbx
0x14030d824  push    rsi
0x14030d825  push    rdi
0x14030d826  push    r12
0x14030d828  push    r13
0x14030d82a  push    r14
0x14030d82c  push    r15
0x14030d82e  sub     rsp, 1A0h
0x14030d835  movaps  xmmword ptr [r11-48h], xmm6
0x14030d83a  mov     rax, cs:__security_cookie
0x14030d841  xor     rax, rsp
0x14030d844  mov     qword ptr [rsp+1D8h+var_50], rax
0x14030d84c  mov     rdi, r8
0x14030d84f  mov     rsi, rdx
0x14030d852  mov     [rsp+1D8h+var_180], rdx
0x14030d857  mov     r13, rcx
0x14030d85a  mov     [r11-110h], rcx
0x14030d861  mov     [r11-108h], rdx
0x14030d868  mov     [r11-100h], r8
0x14030d86f  xorps   xmm0, xmm0
0x14030d872  movups  xmmword ptr [rsp+1D8h+var_F0], xmm0
0x14030d87a  xor     r14d, r14d
0x14030d87d  mov     word ptr [rsp+1D8h+var_178], r14w
0x14030d883  mov     r15, [rcx+40h]
0x14030d887  mov     [rsp+1D8h+var_148], r15
0x14030d88f  mov     [rsp+1D8h+var_F8], r15
0x14030d897  mov     [r11-140h], r14
0x14030d89e  mov     [rsp+1D8h+var_170], r14
0x14030d8a3  xor     eax, eax
0x14030d8a5  movups  xmmword ptr [r11-78h], xmm0
0x14030d8aa  movups  xmmword ptr [r11-68h], xmm0
0x14030d8af  mov     [r11-58h], eax
0x14030d8b3  mov     [rsp+1D8h+P], r14
0x14030d8b8  movups  [rsp+1D8h+var_B8], xmm0
0x14030d8c0  xorps   xmm1, xmm1
0x14030d8c3  movups  xmmword ptr [rsp+1D8h+var_158.Length], xmm1
0x14030d8cb  movups  xmmword ptr [rsp+1D8h+var_128.Length], xmm0
0x14030d8d3  mov     [r11-118h], r14
0x14030d8da  mov     rdx, [r8+0A0h]
0x14030d8e1  mov     rax, [rdx+30h]
0x14030d8e5  mov     [r8+20h], rax
0x14030d8e9  mov     rax, [rdx+8]
0x14030d8ed  mov     rcx, [rax+8]
0x14030d8f1  mov     eax, [rcx+10h]
0x14030d8f4  mov     [r8+28h], eax
0x14030d8f8  mov     rax, [rdx+8]
0x14030d8fc  mov     rcx, [rax+8]
0x14030d900  mov     eax, [rcx+14h]
0x14030d903  mov     [r8+2Ch], eax
0x14030d907  mov     rax, [rdx+8]
0x14030d90b  mov     ecx, [rax+10h]
0x14030d90e  mov     [r8+30h], ecx
0x14030d912  mov     [r8+40h], r14d
0x14030d916  mov     [r8+80h], r14
0x14030d91d  lea     rdx, [r11-118h]; ExtraCreateParameter
0x14030d924  mov     rcx, rsi; Irp
0x14030d927  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14030d92e  nop     dword ptr [rax+rax+00h]
0x14030d933  test    eax, eax
0x14030d935  js      loc_14030DE16
0x14030d93b  mov     rcx, [rsp+1D8h+EcpList]; EcpList
0x14030d943  test    rcx, rcx
0x14030d946  jz      loc_14030DE16
0x14030d94c  lea     rbx, [rdi+0C8h]
0x14030d953  xor     r9d, r9d; EcpContextSize
0x14030d956  mov     r8, rbx; EcpContext
0x14030d959  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x14030d960  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14030d967  nop     dword ptr [rax+rax+00h]
0x14030d96c  mov     rcx, [rbx]; EcpContext
0x14030d96f  test    rcx, rcx
0x14030d972  jz      loc_14030DDA5
0x14030d978  call    cs:__imp_FsRtlAcknowledgeEcp
0x14030d97f  nop     dword ptr [rax+rax+00h]
0x14030d984  mov     rdx, [rbx]
0x14030d987  movzx   r10d, word ptr [rdx]
0x14030d98b  cmp     r10w, 6
0x14030d990  jb      loc_14030DD3D
0x14030d996  movzx   r9d, word ptr [rdx+2]
0x14030d99b  test    r9b, 2
0x14030d99f  jz      short loc_14030D9AC
0x14030d9a1  cmp     r10w, 10h
0x14030d9a6  jb      loc_14030DD3D
0x14030d9ac  movzx   esi, r9w
0x14030d9b0  and     si, 4
0x14030d9b4  jz      short loc_14030D9DB
0x14030d9b6  cmp     r10w, 18h
0x14030d9bb  jb      loc_14030DD38
0x14030d9c1  mov     rax, [rdx+10h]
0x14030d9c5  test    rax, rax
0x14030d9c8  js      loc_14030DD38
0x14030d9ce  cmp     rax, [r15+1E0h]
0x14030d9d5  jg      loc_14030DD38
0x14030d9db  movzx   r14d, r9w
0x14030d9df  and     r14w, 8
0x14030d9e4  jz      short loc_14030DA11
0x14030d9e6  cmp     r10w, 20h ; ' '
0x14030d9eb  jb      loc_14030DD38
0x14030d9f1  mov     rax, [rdx+18h]
0x14030d9f5  test    rax, rax
0x14030d9f8  js      loc_14030DD38
0x14030d9fe  test    si, si
0x14030da01  jz      loc_14030DD38
0x14030da07  cmp     rax, [rdx+10h]
0x14030da0b  jg      loc_14030DD38
0x14030da11  test    r9b, 10h
0x14030da15  jz      short loc_14030DA51
0x14030da17  cmp     r10w, 28h ; '('
0x14030da1c  jb      loc_14030DD38
0x14030da22  mov     rax, [rdx+20h]
0x14030da26  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x14030da2a  jl      loc_14030DD38
0x14030da30  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x14030da35  jl      loc_14030DD38
0x14030da3b  cmp     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x14030da40  jl      loc_14030DD38
0x14030da46  cmp     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x14030da4b  jl      loc_14030DD38
0x14030da51  mov     r8d, 80h
0x14030da57  movzx   r11d, r9w
0x14030da5b  and     r11w, r8w
0x14030da5f  jz      short loc_14030DAE0
0x14030da61  cmp     r10w, 44h ; 'D'
0x14030da66  jb      short loc_14030DA76
0x14030da68  mov     eax, [rdx+3Ch]
0x14030da6b  test    al, 1
0x14030da6d  jz      short loc_14030DAE0
0x14030da6f  cmp     r10w, 58h ; 'X'
0x14030da74  jnb     short loc_14030DAE0
0x14030da76  mov     ebx, 0C000000Dh
0x14030da7b  mov     r9d, ebx
0x14030da7e  mov     r8, [rsp+1D8h+var_180]
0x14030da83  mov     rdx, rdi
0x14030da86  mov     rcx, r13
0x14030da89  call    RefsCompleteCreateRequest
0x14030da8e  lea     rsi, WPP_GLOBAL_Control
0x14030da95  mov     rcx, cs:WPP_GLOBAL_Control
0x14030da9c  cmp     rcx, rsi
0x14030da9f  jz      short loc_14030DAC6
0x14030daa1  bt      dword ptr [rcx+2Ch], 8
0x14030daa6  jnb     short loc_14030DAC6
0x14030daa8  cmp     byte ptr [rcx+29h], 4
0x14030daac  jb      short loc_14030DAC6
0x14030daae  mov     edx, 14h
0x14030dab3  mov     r9d, ebx
0x14030dab6  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14030dabd  mov     rcx, [rcx+18h]
0x14030dac1  call    WPP_SF_d
0x14030dac6  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030dacd  test    al, al
0x14030dacf  jz      loc_1403100AA
0x14030dad5  mov     r9d, 8AEh
0x14030dadb  jmp     loc_14031009A
0x14030dae0  mov     r12d, 100h
0x14030dae6  test    r12w, r9w
0x14030daea  jnz     loc_14030DBA0
0x14030daf0  test    r9b, 60h
0x14030daf4  jnz     short loc_14030DB37
0x14030daf6  test    r11w, r11w
0x14030dafa  jz      short loc_14030DB01
0x14030dafc  mov     eax, [rdx+3Ch]
0x14030daff  jmp     short loc_14030DB03
0x14030db01  xor     eax, eax
0x14030db03  test    eax, 0FFFFFFFEh
0x14030db08  jnz     short loc_14030DB37
0x14030db0a  test    r11w, r11w
0x14030db0e  jz      short loc_14030DB15
0x14030db10  mov     eax, [rdx+3Ch]
0x14030db13  jmp     short loc_14030DB17
0x14030db15  xor     eax, eax
0x14030db17  test    al, 1
0x14030db19  jz      short loc_14030DB20
0x14030db1b  mov     eax, [rdx+4Ch]
0x14030db1e  jmp     short loc_14030DB22
0x14030db20  xor     eax, eax
0x14030db22  test    al, 1
0x14030db24  jz      short loc_14030DBA0
0x14030db26  mov     eax, [rdx+50h]
0x14030db29  test    al, 1
0x14030db2b  jz      short loc_14030DBA0
0x14030db2d  mov     eax, cs:dword_14026887C
0x14030db33  test    al, 1
0x14030db35  jnz     short loc_14030DBA0
0x14030db37  mov     ebx, 0C00000BBh
0x14030db3c  mov     r9d, ebx
0x14030db3f  mov     r8, [rsp+1D8h+var_180]
0x14030db44  mov     rdx, rdi
0x14030db47  mov     rcx, r13
0x14030db4a  call    RefsCompleteCreateRequest
0x14030db4f  lea     rsi, WPP_GLOBAL_Control
0x14030db56  mov     rcx, cs:WPP_GLOBAL_Control
0x14030db5d  cmp     rcx, rsi
0x14030db60  jz      short loc_14030DB86
0x14030db62  test    [rcx+2Ch], r12d
0x14030db66  jz      short loc_14030DB86
0x14030db68  cmp     byte ptr [rcx+29h], 4
0x14030db6c  jb      short loc_14030DB86
0x14030db6e  mov     edx, 15h
0x14030db73  mov     r9d, ebx
0x14030db76  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14030db7d  mov     rcx, [rcx+18h]
0x14030db81  call    WPP_SF_d
0x14030db86  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030db8d  test    al, al
0x14030db8f  jz      loc_1403100AA
0x14030db95  mov     r9d, 8CBh
0x14030db9b  jmp     loc_14031009A
0x14030dba0  mov     eax, 101h
0x14030dba5  test    ax, r9w
0x14030dba9  jnz     short loc_14030DC19
0x14030dbab  test    si, si
0x14030dbae  jz      short loc_14030DC19
0x14030dbb0  mov     ebx, 0C00000BBh
0x14030dbb5  mov     r9d, ebx
0x14030dbb8  mov     r8, [rsp+1D8h+var_180]
0x14030dbbd  mov     rdx, rdi
0x14030dbc0  mov     rcx, r13
0x14030dbc3  call    RefsCompleteCreateRequest
0x14030dbc8  lea     rsi, WPP_GLOBAL_Control
0x14030dbcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14030dbd6  cmp     rcx, rsi
0x14030dbd9  jz      short loc_14030DBFF
0x14030dbdb  test    [rcx+2Ch], r12d
0x14030dbdf  jz      short loc_14030DBFF
0x14030dbe1  cmp     byte ptr [rcx+29h], 4
0x14030dbe5  jb      short loc_14030DBFF
0x14030dbe7  mov     edx, 16h
0x14030dbec  mov     r9d, ebx
0x14030dbef  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14030dbf6  mov     rcx, [rcx+18h]
0x14030dbfa  call    WPP_SF_d
0x14030dbff  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030dc06  test    al, al
0x14030dc08  jz      loc_1403100AA
0x14030dc0e  mov     r9d, 8DBh
0x14030dc14  jmp     loc_14031009A
0x14030dc19  test    r14w, r14w
0x14030dc1d  jz      loc_14030DCF1
0x14030dc23  cmp     qword ptr [rdx+18h], 0
0x14030dc28  jle     loc_14030DCF1
0x14030dc2e  test    r9b, 1
0x14030dc32  jnz     loc_14030DCF1
0x14030dc38  mov     rdx, [rdi+0A0h]; struct _IO_STACK_LOCATION *
0x14030dc3f  mov     rsi, [rsp+1D8h+var_180]
0x14030dc44  mov     rcx, rsi; struct _IRP *
0x14030dc47  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x14030dc4c  mov     rcx, [rdi+0A0h]
0x14030dc53  mov     rdx, [rcx+8]
0x14030dc57  mov     rdx, [rdx+8]
0x14030dc5b  add     rdx, 20h ; ' '; struct _SECURITY_SUBJECT_CONTEXT *
0x14030dc5f  movzx   r8d, al; char
0x14030dc63  mov     ecx, 1Ch; unsigned int
0x14030dc68  call    ?RefsPrivilegeCheck@@YAEKPEAU_SECURITY_SUBJECT_CONTEXT@@D@Z; RefsPrivilegeCheck(ulong,_SECURITY_SUBJECT_CONTEXT *,char)
0x14030dc6d  test    al, al
0x14030dc6f  jnz     loc_14030DCF8
0x14030dc75  mov     r9d, 0C0000061h
0x14030dc7b  mov     r8, rsi
0x14030dc7e  mov     rdx, rdi
0x14030dc81  mov     rcx, r13
0x14030dc84  call    RefsCompleteCreateRequest
0x14030dc89  lea     rsi, WPP_GLOBAL_Control
0x14030dc90  mov     rcx, cs:WPP_GLOBAL_Control
0x14030dc97  cmp     rcx, rsi
0x14030dc9a  jz      short loc_14030DCC3
0x14030dc9c  test    [rcx+2Ch], r12d
0x14030dca0  jz      short loc_14030DCC3
0x14030dca2  cmp     byte ptr [rcx+29h], 4
0x14030dca6  jb      short loc_14030DCC3
0x14030dca8  mov     edx, 17h
0x14030dcad  mov     r9d, 0C0000061h
0x14030dcb3  lea     r8, WPP_acbf0c98c70c3622cf9c2d7b56bc83fa_Traceguids
0x14030dcba  mov     rcx, [rcx+18h]
0x14030dcbe  call    WPP_SF_d
0x14030dcc3  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030dcca  test    cl, cl
0x14030dccc  jz      short loc_14030DCE7
0x14030dcce  mov     r9d, 8EBh; unsigned int
0x14030dcd4  lea     r8, aCreateC; "Create.c"
0x14030dcdb  xor     edx, edx; struct _IRP_CONTEXT *
0x14030dcdd  mov     ecx, 0C0000061h; Status
0x14030dce2  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14030dce7  mov     eax, 0C0000061h
0x14030dcec  jmp     loc_1403100AC
0x14030dcf1  mov     rsi, [rsp+1D8h+var_180]
0x14030dcf6  jmp     short loc_14030DCFE
0x14030dcf8  mov     r8d, 80h
0x14030dcfe  mov     rcx, [rbx]
0x14030dd01  movzx   eax, byte ptr [rcx+2]
0x14030dd05  test    al, al
0x14030dd07  jns     short loc_14030DD0E
0x14030dd09  or      [rcx+4], r8w
0x14030dd0e  mov     rcx, [rbx]
0x14030dd11  movzx   eax, byte ptr [rcx+2]
0x14030dd15  test    al, al
0x14030dd17  jns     short loc_14030DD1E
0x14030dd19  mov     eax, [rcx+3Ch]
0x14030dd1c  jmp     short loc_14030DD20
0x14030dd1e  xor     eax, eax
0x14030dd20  test    al, 1
  ... truncated ...
```
