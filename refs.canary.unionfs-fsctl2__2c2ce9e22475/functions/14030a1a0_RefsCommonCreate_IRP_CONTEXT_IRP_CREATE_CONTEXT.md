# RefsCommonCreate(_IRP_CONTEXT *,_IRP *,_CREATE_CONTEXT *)

- ea: `0x14030a1a0`
- end: `0x14030cbcb`
- name: `?RefsCommonCreate@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@PEAU_CREATE_CONTEXT@@@Z`
- size: `10795`
- prototype: `__int64 __fastcall(struct _IRP_CONTEXT *, PIRP Irp, struct _CREATE_CONTEXT *)`
- caller_count: `4`
- callee_count: `58`
- tags: `reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400bc440`
- `0x140291580`
- `0x140309700`
- `0x140309ae0`

## callees

- `0x140038f80`
- `0x14003fbe0`
- `0x140041b40`
- `0x14007b700`
- `0x140081670`
- `0x14008a300`
- `0x14008c400`
- `0x14008dbd0`
- `0x14008f870`
- `0x140093080`
- `0x140094fc0`
- `0x140099960`
- `0x1400a3da0`
- `0x1400ad0c8`
- `0x1400ca788`
- `0x1400e1bc0`
- `0x140110c88`
- `0x1401e9ce0`
- `0x1401e9e40`
- `0x1401ea660`
- `0x140286ebc`
- `0x140290d34`
- `0x140290d80`
- `0x1402915d4`
- `0x140291760`
- `0x140293194`
- `0x140295074`
- `0x1402fb270`
- `0x1402fe430`
- `0x1402fec90`
- `0x1403012f0`
- `0x1403021e0`
- `0x140306630`
- `0x140307140`
- `0x14030a1a0`
- `0x14030fee0`
- `0x14030ffc0`
- `0x140313b70`
- `0x1403185c0`
- `0x14031ac80`
- `0x14031c8e0`
- `0x14031f1f0`
- `0x14031f700`
- `0x140320020`
- `0x140323c60`
- `0x140323f70`
- `0x140324070`
- `0x140324180`
- `0x140324200`
- `0x140325110`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14030a2a7`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14030a2a7`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030a2e0`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030a744`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030a785`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030a2e0`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030a744`
- `ntoskrnl!FsRtlFindExtraCreateParameter` at `0x14030a785`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x14030a2f8`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x14030a75c`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x14030a2f8`
- `ntoskrnl!FsRtlAcknowledgeEcp` at `0x14030a75c`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14030b2d9`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14030bd2a`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14030b2d9`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14030bd2a`
- `ntoskrnl!DbgPrintEx` at `0x14030b589`
- `ntoskrnl!DbgPrintEx` at `0x14030b589`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14030c78e`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14033fc21`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14030c78e`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14033fc21`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14030c738`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14033fbc3`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14030c738`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14033fbc3`
- `ntoskrnl!KeWaitForSingleObject` at `0x14030a80b`
- `ntoskrnl!KeWaitForSingleObject` at `0x14030a80b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c092`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c37a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c3f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c8d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f75e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f801`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fd7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c092`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c37a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c3f5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14030c8d9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f75e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033f801`
- `ntoskrnl!ExFreePoolWithTag` at `0x14033fd7e`

## string_xrefs

- `0x14030a654`: `Create.c`
- `0x14030a888`: `Create.c`
- `0x14030aa39`: `Create.c`
- `0x14030aaa6`: `Create.c`
- `0x14030ab17`: `Create.c`
- `0x14030abdc`: `Create.c`
- `0x14030ac8a`: `Create.c`
- `0x14030ad01`: `Create.c`
- `0x14030ae15`: `Create.c`
- `0x14030b047`: `Create.c`
- `0x14030b0d8`: `Create.c`
- `0x14030b199`: `Create.c`
- `0x14030b459`: `Create.c`
- `0x14030b723`: `Create.c`
- `0x14030b794`: `Create.c`
- `0x14030b82c`: `Create.c`
- `0x14030b89d`: `Create.c`
- `0x14030b98b`: `Create.c`
- `0x14030bb8e`: `Create.c`
- `0x14030bd92`: `Create.c`
- `0x14030be2c`: `Create.c`
- `0x14030beb2`: `Create.c`
- `0x14030bf57`: `Create.c`
- `0x14030c12e`: `Create.c`
- `0x14030c1c4`: `Create.c`
- `0x14030c28f`: `Create.c`
- `0x14030c646`: `Create.c`
- `0x14030ca1a`: `Create.c`
- `0x14030caa0`: `Create.c`
- `0x14030cb06`: `Create.c`
- `0x14030cb38`: `Create.c`
- `0x14030cba8`: `Create.c`
- `0x14033fab7`: `Create.c`
- `0x14030b578`: `Opening reparse index.\n`

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
                    WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
                       (v20 & 1) != 0 && (*((_DWORD *)v10 + 20) & 1) != 0 && (dword_14026188C & 1) == 0)) )
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
                      WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
                    WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
                      WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225485LL);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225485LL);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225760LL);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225506LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221226094LL);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225865LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225634LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225485LL);
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
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225659LL);
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
          WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
            WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225485LL);
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
              WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 260);
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
              WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
                WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
                WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
                WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
                WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
              WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
              WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
              WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
              3221225688LL);
          }
          if ( (_BYTE)RefsStatusDebugEnabled )
            RefsStatusDebug(-1073741608, v5, "Create.c", 0xA3Au);
          RefsRaiseStatusInternal(v5, -1073741608, v29);
          __debugbreak();
          JUMPOUT(0x14030CBCBLL);
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
                WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
              WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225530LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221226113LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225524LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225523LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 50, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225634LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 51, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225558LL);
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
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids, 3221225524LL);
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
              WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids,
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
0x14030a1a0  mov     r11, rsp
0x14030a1a3  push    rbx
0x14030a1a4  push    rsi
0x14030a1a5  push    rdi
0x14030a1a6  push    r12
0x14030a1a8  push    r13
0x14030a1aa  push    r14
0x14030a1ac  push    r15
0x14030a1ae  sub     rsp, 1A0h
0x14030a1b5  movaps  xmmword ptr [r11-48h], xmm6
0x14030a1ba  mov     rax, cs:__security_cookie
0x14030a1c1  xor     rax, rsp
0x14030a1c4  mov     qword ptr [rsp+1D8h+var_50], rax
0x14030a1cc  mov     rdi, r8
0x14030a1cf  mov     rsi, rdx
0x14030a1d2  mov     [rsp+1D8h+var_180], rdx
0x14030a1d7  mov     r13, rcx
0x14030a1da  mov     [r11-110h], rcx
0x14030a1e1  mov     [r11-108h], rdx
0x14030a1e8  mov     [r11-100h], r8
0x14030a1ef  xorps   xmm0, xmm0
0x14030a1f2  movups  xmmword ptr [rsp+1D8h+var_F0], xmm0
0x14030a1fa  xor     r14d, r14d
0x14030a1fd  mov     word ptr [rsp+1D8h+var_178], r14w
0x14030a203  mov     r15, [rcx+40h]
0x14030a207  mov     [rsp+1D8h+var_148], r15
0x14030a20f  mov     [rsp+1D8h+var_F8], r15
0x14030a217  mov     [r11-140h], r14
0x14030a21e  mov     [rsp+1D8h+var_170], r14
0x14030a223  xor     eax, eax
0x14030a225  movups  xmmword ptr [r11-78h], xmm0
0x14030a22a  movups  xmmword ptr [r11-68h], xmm0
0x14030a22f  mov     [r11-58h], eax
0x14030a233  mov     [rsp+1D8h+P], r14
0x14030a238  movups  [rsp+1D8h+var_B8], xmm0
0x14030a240  xorps   xmm1, xmm1
0x14030a243  movups  xmmword ptr [rsp+1D8h+var_158.Length], xmm1
0x14030a24b  movups  xmmword ptr [rsp+1D8h+var_128.Length], xmm0
0x14030a253  mov     [r11-118h], r14
0x14030a25a  mov     rdx, [r8+0A0h]
0x14030a261  mov     rax, [rdx+30h]
0x14030a265  mov     [r8+20h], rax
0x14030a269  mov     rax, [rdx+8]
0x14030a26d  mov     rcx, [rax+8]
0x14030a271  mov     eax, [rcx+10h]
0x14030a274  mov     [r8+28h], eax
0x14030a278  mov     rax, [rdx+8]
0x14030a27c  mov     rcx, [rax+8]
0x14030a280  mov     eax, [rcx+14h]
0x14030a283  mov     [r8+2Ch], eax
0x14030a287  mov     rax, [rdx+8]
0x14030a28b  mov     ecx, [rax+10h]
0x14030a28e  mov     [r8+30h], ecx
0x14030a292  mov     [r8+40h], r14d
0x14030a296  mov     [r8+80h], r14
0x14030a29d  lea     rdx, [r11-118h]; ExtraCreateParameter
0x14030a2a4  mov     rcx, rsi; Irp
0x14030a2a7  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14030a2ae  nop     dword ptr [rax+rax+00h]
0x14030a2b3  test    eax, eax
0x14030a2b5  js      loc_14030A796
0x14030a2bb  mov     rcx, [rsp+1D8h+EcpList]; EcpList
0x14030a2c3  test    rcx, rcx
0x14030a2c6  jz      loc_14030A796
0x14030a2cc  lea     rbx, [rdi+0C8h]
0x14030a2d3  xor     r9d, r9d; EcpContextSize
0x14030a2d6  mov     r8, rbx; EcpContext
0x14030a2d9  lea     rdx, GUID_ECP_ATOMIC_CREATE; EcpType
0x14030a2e0  call    cs:__imp_FsRtlFindExtraCreateParameter
0x14030a2e7  nop     dword ptr [rax+rax+00h]
0x14030a2ec  mov     rcx, [rbx]; EcpContext
0x14030a2ef  test    rcx, rcx
0x14030a2f2  jz      loc_14030A725
0x14030a2f8  call    cs:__imp_FsRtlAcknowledgeEcp
0x14030a2ff  nop     dword ptr [rax+rax+00h]
0x14030a304  mov     rdx, [rbx]
0x14030a307  movzx   r10d, word ptr [rdx]
0x14030a30b  cmp     r10w, 6
0x14030a310  jb      loc_14030A6BD
0x14030a316  movzx   r9d, word ptr [rdx+2]
0x14030a31b  test    r9b, 2
0x14030a31f  jz      short loc_14030A32C
0x14030a321  cmp     r10w, 10h
0x14030a326  jb      loc_14030A6BD
0x14030a32c  movzx   esi, r9w
0x14030a330  and     si, 4
0x14030a334  jz      short loc_14030A35B
0x14030a336  cmp     r10w, 18h
0x14030a33b  jb      loc_14030A6B8
0x14030a341  mov     rax, [rdx+10h]
0x14030a345  test    rax, rax
0x14030a348  js      loc_14030A6B8
0x14030a34e  cmp     rax, [r15+1E0h]
0x14030a355  jg      loc_14030A6B8
0x14030a35b  movzx   r14d, r9w
0x14030a35f  and     r14w, 8
0x14030a364  jz      short loc_14030A391
0x14030a366  cmp     r10w, 20h ; ' '
0x14030a36b  jb      loc_14030A6B8
0x14030a371  mov     rax, [rdx+18h]
0x14030a375  test    rax, rax
0x14030a378  js      loc_14030A6B8
0x14030a37e  test    si, si
0x14030a381  jz      loc_14030A6B8
0x14030a387  cmp     rax, [rdx+10h]
0x14030a38b  jg      loc_14030A6B8
0x14030a391  test    r9b, 10h
0x14030a395  jz      short loc_14030A3D1
0x14030a397  cmp     r10w, 28h ; '('
0x14030a39c  jb      loc_14030A6B8
0x14030a3a2  mov     rax, [rdx+20h]
0x14030a3a6  cmp     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x14030a3aa  jl      loc_14030A6B8
0x14030a3b0  cmp     qword ptr [rax+8], 0FFFFFFFFFFFFFFFFh
0x14030a3b5  jl      loc_14030A6B8
0x14030a3bb  cmp     qword ptr [rax+10h], 0FFFFFFFFFFFFFFFFh
0x14030a3c0  jl      loc_14030A6B8
0x14030a3c6  cmp     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x14030a3cb  jl      loc_14030A6B8
0x14030a3d1  mov     r8d, 80h
0x14030a3d7  movzx   r11d, r9w
0x14030a3db  and     r11w, r8w
0x14030a3df  jz      short loc_14030A460
0x14030a3e1  cmp     r10w, 44h ; 'D'
0x14030a3e6  jb      short loc_14030A3F6
0x14030a3e8  mov     eax, [rdx+3Ch]
0x14030a3eb  test    al, 1
0x14030a3ed  jz      short loc_14030A460
0x14030a3ef  cmp     r10w, 58h ; 'X'
0x14030a3f4  jnb     short loc_14030A460
0x14030a3f6  mov     ebx, 0C000000Dh
0x14030a3fb  mov     r9d, ebx
0x14030a3fe  mov     r8, [rsp+1D8h+var_180]
0x14030a403  mov     rdx, rdi
0x14030a406  mov     rcx, r13
0x14030a409  call    RefsCompleteCreateRequest
0x14030a40e  lea     rsi, WPP_GLOBAL_Control
0x14030a415  mov     rcx, cs:WPP_GLOBAL_Control
0x14030a41c  cmp     rcx, rsi
0x14030a41f  jz      short loc_14030A446
0x14030a421  bt      dword ptr [rcx+2Ch], 8
0x14030a426  jnb     short loc_14030A446
0x14030a428  cmp     byte ptr [rcx+29h], 4
0x14030a42c  jb      short loc_14030A446
0x14030a42e  mov     edx, 14h
0x14030a433  mov     r9d, ebx
0x14030a436  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x14030a43d  mov     rcx, [rcx+18h]
0x14030a441  call    WPP_SF_d
0x14030a446  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030a44d  test    al, al
0x14030a44f  jz      loc_14030CA2A
0x14030a455  mov     r9d, 8AEh
0x14030a45b  jmp     loc_14030CA1A
0x14030a460  mov     r12d, 100h
0x14030a466  test    r12w, r9w
0x14030a46a  jnz     loc_14030A520
0x14030a470  test    r9b, 60h
0x14030a474  jnz     short loc_14030A4B7
0x14030a476  test    r11w, r11w
0x14030a47a  jz      short loc_14030A481
0x14030a47c  mov     eax, [rdx+3Ch]
0x14030a47f  jmp     short loc_14030A483
0x14030a481  xor     eax, eax
0x14030a483  test    eax, 0FFFFFFFEh
0x14030a488  jnz     short loc_14030A4B7
0x14030a48a  test    r11w, r11w
0x14030a48e  jz      short loc_14030A495
0x14030a490  mov     eax, [rdx+3Ch]
0x14030a493  jmp     short loc_14030A497
0x14030a495  xor     eax, eax
0x14030a497  test    al, 1
0x14030a499  jz      short loc_14030A4A0
0x14030a49b  mov     eax, [rdx+4Ch]
0x14030a49e  jmp     short loc_14030A4A2
0x14030a4a0  xor     eax, eax
0x14030a4a2  test    al, 1
0x14030a4a4  jz      short loc_14030A520
0x14030a4a6  mov     eax, [rdx+50h]
0x14030a4a9  test    al, 1
0x14030a4ab  jz      short loc_14030A520
0x14030a4ad  mov     eax, cs:dword_14026188C
0x14030a4b3  test    al, 1
0x14030a4b5  jnz     short loc_14030A520
0x14030a4b7  mov     ebx, 0C00000BBh
0x14030a4bc  mov     r9d, ebx
0x14030a4bf  mov     r8, [rsp+1D8h+var_180]
0x14030a4c4  mov     rdx, rdi
0x14030a4c7  mov     rcx, r13
0x14030a4ca  call    RefsCompleteCreateRequest
0x14030a4cf  lea     rsi, WPP_GLOBAL_Control
0x14030a4d6  mov     rcx, cs:WPP_GLOBAL_Control
0x14030a4dd  cmp     rcx, rsi
0x14030a4e0  jz      short loc_14030A506
0x14030a4e2  test    [rcx+2Ch], r12d
0x14030a4e6  jz      short loc_14030A506
0x14030a4e8  cmp     byte ptr [rcx+29h], 4
0x14030a4ec  jb      short loc_14030A506
0x14030a4ee  mov     edx, 15h
0x14030a4f3  mov     r9d, ebx
0x14030a4f6  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x14030a4fd  mov     rcx, [rcx+18h]
0x14030a501  call    WPP_SF_d
0x14030a506  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030a50d  test    al, al
0x14030a50f  jz      loc_14030CA2A
0x14030a515  mov     r9d, 8CBh
0x14030a51b  jmp     loc_14030CA1A
0x14030a520  mov     eax, 101h
0x14030a525  test    ax, r9w
0x14030a529  jnz     short loc_14030A599
0x14030a52b  test    si, si
0x14030a52e  jz      short loc_14030A599
0x14030a530  mov     ebx, 0C00000BBh
0x14030a535  mov     r9d, ebx
0x14030a538  mov     r8, [rsp+1D8h+var_180]
0x14030a53d  mov     rdx, rdi
0x14030a540  mov     rcx, r13
0x14030a543  call    RefsCompleteCreateRequest
0x14030a548  lea     rsi, WPP_GLOBAL_Control
0x14030a54f  mov     rcx, cs:WPP_GLOBAL_Control
0x14030a556  cmp     rcx, rsi
0x14030a559  jz      short loc_14030A57F
0x14030a55b  test    [rcx+2Ch], r12d
0x14030a55f  jz      short loc_14030A57F
0x14030a561  cmp     byte ptr [rcx+29h], 4
0x14030a565  jb      short loc_14030A57F
0x14030a567  mov     edx, 16h
0x14030a56c  mov     r9d, ebx
0x14030a56f  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x14030a576  mov     rcx, [rcx+18h]
0x14030a57a  call    WPP_SF_d
0x14030a57f  movzx   eax, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030a586  test    al, al
0x14030a588  jz      loc_14030CA2A
0x14030a58e  mov     r9d, 8DBh
0x14030a594  jmp     loc_14030CA1A
0x14030a599  test    r14w, r14w
0x14030a59d  jz      loc_14030A671
0x14030a5a3  cmp     qword ptr [rdx+18h], 0
0x14030a5a8  jle     loc_14030A671
0x14030a5ae  test    r9b, 1
0x14030a5b2  jnz     loc_14030A671
0x14030a5b8  mov     rdx, [rdi+0A0h]; struct _IO_STACK_LOCATION *
0x14030a5bf  mov     rsi, [rsp+1D8h+var_180]
0x14030a5c4  mov     rcx, rsi; struct _IRP *
0x14030a5c7  call    ?RefsEffectiveMode@@YADPEAU_IRP@@PEAU_IO_STACK_LOCATION@@@Z; RefsEffectiveMode(_IRP *,_IO_STACK_LOCATION *)
0x14030a5cc  mov     rcx, [rdi+0A0h]
0x14030a5d3  mov     rdx, [rcx+8]
0x14030a5d7  mov     rdx, [rdx+8]
0x14030a5db  add     rdx, 20h ; ' '; struct _SECURITY_SUBJECT_CONTEXT *
0x14030a5df  movzx   r8d, al; char
0x14030a5e3  mov     ecx, 1Ch; unsigned int
0x14030a5e8  call    ?RefsPrivilegeCheck@@YAEKPEAU_SECURITY_SUBJECT_CONTEXT@@D@Z; RefsPrivilegeCheck(ulong,_SECURITY_SUBJECT_CONTEXT *,char)
0x14030a5ed  test    al, al
0x14030a5ef  jnz     loc_14030A678
0x14030a5f5  mov     r9d, 0C0000061h
0x14030a5fb  mov     r8, rsi
0x14030a5fe  mov     rdx, rdi
0x14030a601  mov     rcx, r13
0x14030a604  call    RefsCompleteCreateRequest
0x14030a609  lea     rsi, WPP_GLOBAL_Control
0x14030a610  mov     rcx, cs:WPP_GLOBAL_Control
0x14030a617  cmp     rcx, rsi
0x14030a61a  jz      short loc_14030A643
0x14030a61c  test    [rcx+2Ch], r12d
0x14030a620  jz      short loc_14030A643
0x14030a622  cmp     byte ptr [rcx+29h], 4
0x14030a626  jb      short loc_14030A643
0x14030a628  mov     edx, 17h
0x14030a62d  mov     r9d, 0C0000061h
0x14030a633  lea     r8, WPP_7fd866a51baf3c9804583670ee7ed8f5_Traceguids
0x14030a63a  mov     rcx, [rcx+18h]
0x14030a63e  call    WPP_SF_d
0x14030a643  movzx   ecx, cs:?RefsStatusDebugEnabled@@3EC; uchar volatile RefsStatusDebugEnabled
0x14030a64a  test    cl, cl
0x14030a64c  jz      short loc_14030A667
0x14030a64e  mov     r9d, 8EBh; unsigned int
0x14030a654  lea     r8, aCreateC; "Create.c"
0x14030a65b  xor     edx, edx; struct _IRP_CONTEXT *
0x14030a65d  mov     ecx, 0C0000061h; Status
0x14030a662  call    ?RefsStatusDebug@@YAXJPEAU_IRP_CONTEXT@@PEBDK@Z; RefsStatusDebug(long,_IRP_CONTEXT *,char const *,ulong)
0x14030a667  mov     eax, 0C0000061h
0x14030a66c  jmp     loc_14030CA2C
0x14030a671  mov     rsi, [rsp+1D8h+var_180]
0x14030a676  jmp     short loc_14030A67E
0x14030a678  mov     r8d, 80h
0x14030a67e  mov     rcx, [rbx]
0x14030a681  movzx   eax, byte ptr [rcx+2]
0x14030a685  test    al, al
0x14030a687  jns     short loc_14030A68E
0x14030a689  or      [rcx+4], r8w
0x14030a68e  mov     rcx, [rbx]
0x14030a691  movzx   eax, byte ptr [rcx+2]
0x14030a695  test    al, al
0x14030a697  jns     short loc_14030A69E
0x14030a699  mov     eax, [rcx+3Ch]
0x14030a69c  jmp     short loc_14030A6A0
0x14030a69e  xor     eax, eax
0x14030a6a0  test    al, 1
  ... truncated ...
```
