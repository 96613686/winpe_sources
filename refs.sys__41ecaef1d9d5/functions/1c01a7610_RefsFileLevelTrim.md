# RefsFileLevelTrim

- ea: `0x1c01a7610`
- end: `0x1c01a8bf7`
- name: `RefsFileLevelTrim`
- size: `5607`
- prototype: `__int64 __fastcall(PVOID Context, PIRP Irp)`
- caller_count: `1`
- callee_count: `23`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1c015c128`

## callees

- `0x1c0004300`
- `0x1c00049a0`
- `0x1c0005768`
- `0x1c000f770`
- `0x1c0013f90`
- `0x1c003e428`
- `0x1c004d164`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c006af80`
- `0x1c0091438`
- `0x1c009166c`
- `0x1c0092f10`
- `0x1c0093c0c`
- `0x1c009620c`
- `0x1c0097858`
- `0x1c009871c`
- `0x1c00b1d60`
- `0x1c00b3f54`
- `0x1c014fe2c`
- `0x1c01632d4`
- `0x1c01634c8`
- `0x1c01a7610`

## import_xrefs

- `ntoskrnl!CcPurgeCacheSection` at `0x1c01a8526`
- `ntoskrnl!CcPurgeCacheSection` at `0x1c01a8526`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c01a7fac`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x1c01a7fac`
- `ntoskrnl!IoGetRequestorProcess` at `0x1c01a840a`
- `ntoskrnl!IoGetRequestorProcess` at `0x1c01a840a`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x1c01a844b`
- `ntoskrnl!FsRtlFastCheckLockForWrite` at `0x1c01a844b`

## pseudocode

```c
__int64 __fastcall RefsFileLevelTrim(struct CmsTransactionContext **Context, PIRP Irp)
{
  struct CmsTransactionContext **v3; // rdi
  struct _IO_STACK_LOCATION *v4; // rsi
  char v5; // bl
  unsigned int v6; // edi
  __int64 v7; // r13
  int v8; // ecx
  union _LARGE_INTEGER v10; // r14
  __int64 Options; // r8
  ULONG *MasterIrp; // r12
  ULONG v13; // eax
  int v14; // r9d
  unsigned __int64 v15; // rdx
  __int64 v16; // rdx
  char v17; // al
  __int64 v18; // rcx
  __int64 TrimContext; // rsi
  __int64 v20; // r9
  __int64 v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // r8
  PDEVICE_OBJECT *v24; // rbx
  int v25; // eax
  unsigned __int64 v26; // rcx
  NTSTATUS v27; // eax
  unsigned __int64 v28; // r9
  unsigned __int64 v29; // r8
  int v30; // eax
  unsigned __int64 v31; // r10
  unsigned __int64 v32; // rdx
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rcx
  unsigned __int64 v35; // rax
  char v36; // cl
  int v37; // eax
  __int64 v38; // rcx
  ULONG v39; // r12d
  __int64 v40; // rbx
  union _LARGE_INTEGER v41; // r9
  union _LARGE_INTEGER v42; // r8
  int v43; // eax
  unsigned __int64 v44; // r11
  unsigned __int64 v45; // rdx
  int v46; // eax
  unsigned __int64 v47; // rax
  PEPROCESS RequestorProcess; // rax
  union _LARGE_INTEGER v49; // rbx
  ULONG LowPart; // r12d
  char v51; // bl
  char v52; // cl
  union _LARGE_INTEGER v53; // rbx
  unsigned __int64 v54; // rdx
  __int64 v55; // rax
  union _LARGE_INTEGER v56; // rdx
  BOOL v57; // eax
  int v58; // [rsp+30h] [rbp-198h]
  int v59; // [rsp+38h] [rbp-190h]
  char v60; // [rsp+70h] [rbp-158h]
  unsigned int Status; // [rsp+74h] [rbp-154h]
  unsigned int Statusa; // [rsp+74h] [rbp-154h]
  union _LARGE_INTEGER Length; // [rsp+78h] [rbp-150h] BYREF
  union _LARGE_INTEGER StartingByte; // [rsp+80h] [rbp-148h] BYREF
  ULONG v65; // [rsp+88h] [rbp-140h]
  __int64 v66; // [rsp+90h] [rbp-138h] BYREF
  __int64 v67; // [rsp+98h] [rbp-130h] BYREF
  union _LARGE_INTEGER v68; // [rsp+A0h] [rbp-128h] BYREF
  ULONG *v69; // [rsp+A8h] [rbp-120h] BYREF
  __int64 v70; // [rsp+B0h] [rbp-118h]
  _QWORD v71[2]; // [rsp+B8h] [rbp-110h] BYREF
  union _LARGE_INTEGER FileOffset; // [rsp+C8h] [rbp-100h] BYREF
  __int64 v73; // [rsp+D0h] [rbp-F8h]
  __int64 v74; // [rsp+D8h] [rbp-F0h] BYREF
  struct _IO_STACK_LOCATION *CurrentStackLocation; // [rsp+E0h] [rbp-E8h]
  union _LARGE_INTEGER v76; // [rsp+E8h] [rbp-E0h]
  unsigned __int64 v77; // [rsp+F0h] [rbp-D8h]
  union _LARGE_INTEGER v78; // [rsp+F8h] [rbp-D0h]
  __int128 v79; // [rsp+100h] [rbp-C8h]
  __int128 v80; // [rsp+110h] [rbp-B8h]
  __int128 v81; // [rsp+120h] [rbp-A8h] BYREF
  _BYTE v82[152]; // [rsp+130h] [rbp-98h] BYREF
  struct CmsTransactionContext **v83; // [rsp+1D0h] [rbp+8h]
  char v84; // [rsp+1E0h] [rbp+18h] BYREF
  char v85; // [rsp+1E8h] [rbp+20h] BYREF

  v83 = Context;
  v3 = Context;
  v66 = 0;
  v67 = 0;
  v68.QuadPart = 0;
  v69 = 0;
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  v4 = CurrentStackLocation;
  v5 = (_BYTE)Context[1] & 1;
  v60 = 0;
  memset(v82, 0, 0x58u);
  if ( (unsigned int)RefsDecodeFileObject(
                       (_DWORD)v3,
                       CurrentStackLocation->FileObject,
                       (unsigned int)&v66,
                       (unsigned int)&v67,
                       (__int64)&v68,
                       (__int64)&v69,
                       0) != 2 )
  {
    v6 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 400, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_293;
  }
  v7 = v66;
  v8 = *(_DWORD *)(v66 + 4);
  if ( (v8 & 0xA000021) != 1 )
  {
    if ( (v8 & 0x20) != 0 )
    {
      v6 = -1073741431;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741431);
      RefsExtendedCompleteRequestInternal(v83, Irp, 3221225865LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 401, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225865LL);
      }
      if ( !RefsStatusDebugEnabled )
        return v6;
      goto LABEL_293;
    }
    if ( (v8 & 0x8000000) != 0 || (v8 & 1) == 0 )
    {
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741202);
      RefsExtendedCompleteRequestInternal(v83, Irp, 3221226094LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 402, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226094LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741202);
      return 3221226094LL;
    }
    if ( (v8 & 0x2000000) != 0 )
    {
      v6 = -1073741662;
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741662);
      RefsExtendedCompleteRequestInternal(v83, Irp, 3221225634LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 403, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225634LL);
      }
      if ( !RefsStatusDebugEnabled )
        return v6;
      goto LABEL_293;
    }
  }
  v10 = v68;
  if ( (*(_DWORD *)(v68.QuadPart + 304) & 0x1000000) != 0 )
  {
    v6 = -1073741816;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741816);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225480LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 404, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225480LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_293;
  }
  if ( v69 && (v69[1] & 0x2000) != 0 )
  {
    v6 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 405, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_293;
  }
  if ( (*(_WORD *)(v68.QuadPart + 252) & 0x40FF) != 0
    || *(_WORD *)(v68.QuadPart + 258)
    || (*(_DWORD *)(v68.QuadPart + 136) & 8) != 0 )
  {
    v6 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 406, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
LABEL_293:
    RefsStatusDebug(v6);
    return v6;
  }
  Options = v4->Parameters.Create.Options;
  if ( (unsigned int)Options < 0x18 )
  {
    v6 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 407, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_293;
  }
  MasterIrp = (ULONG *)Irp->AssociatedIrp.MasterIrp;
  v69 = MasterIrp;
  v13 = MasterIrp[1];
  v14 = 0;
  if ( !v13
    || (v15 = 16LL * (v13 - 1), v15 > 0xFFFFFFFF)
    || (int)v15 + 24 < (unsigned int)v15
    || (unsigned int)Options < (int)v15 + 24 )
  {
    v6 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 408, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_293;
  }
  v16 = v4->Parameters.Read.Length;
  if ( (unsigned int)(v16 - 1) <= 2 )
  {
    v6 = -1073741811;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225485LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 409, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_293;
  }
  v17 = 0;
  if ( (v8 & 0x8000821) == 1 )
  {
    v18 = *(_QWORD *)(v66 + 104);
    if ( v18 )
      v17 = MsIsDeleteNotificationDisabled(v18, v16, Options, 0);
  }
  if ( v17 )
  {
    v6 = -1073741637;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741637);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225659LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 410, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225659LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_293;
  }
  TrimContext = RefsCreateTrimContext(
                  v7,
                  (_DWORD)Irp,
                  0,
                  v14,
                  v14,
                  (unsigned __int64)MasterIrp & -(__int64)((_DWORD)v16 != 0));
  v71[1] = TrimContext;
  if ( !TrimContext )
  {
    v6 = -1073741670;
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741670);
    RefsExtendedCompleteRequestInternal(v83, Irp, 3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 411, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225626LL);
    }
    if ( !RefsStatusDebugEnabled )
      return v6;
    goto LABEL_293;
  }
  MsInitializeFastResourceOwnerEntry(v82);
  LOBYTE(v20) = v5;
  LODWORD(v24) = 0;
  if ( !(unsigned __int8)RefsAcquirePagingFastResourceExclusive(v21, v67, v82, v20) )
  {
    v24 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 412, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225688LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741608);
    RefsRaiseStatusInternal(v83, 3221225688LL);
  }
  *(_QWORD *)(TrimContext + 32) = *(_QWORD *)(v67 + 104);
  v25 = *(_DWORD *)(v10.QuadPart + 304);
  if ( (v25 & 0x10000) != 0 )
  {
    v26 = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 413, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226094LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741202);
    *(_DWORD *)(TrimContext + 148) = -1073741202;
LABEL_257:
    v3 = v83;
    goto LABEL_258;
  }
  if ( (v25 & 0x40) != 0 || (*(_DWORD *)(v67 + 4) & 1) != 0 )
  {
    v26 = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 414, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225763LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741533);
    *(_DWORD *)(TrimContext + 148) = -1073741533;
    goto LABEL_257;
  }
  if ( !(unsigned __int8)RefsIsFileOpen(v67, v22, v23) )
  {
    v26 = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 415, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225768LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741528);
    *(_DWORD *)(TrimContext + 148) = -1073741528;
    goto LABEL_257;
  }
  if ( (*(_WORD *)(v10.QuadPart + 252) & 0x40FF) != 0
    || *(_WORD *)(v10.QuadPart + 258) != (_WORD)v24
    || (*(_DWORD *)(v10.QuadPart + 136) & 8) != 0 )
  {
    v26 = (unsigned __int64)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 416, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741811);
    *(_DWORD *)(TrimContext + 148) = -1073741811;
    goto LABEL_257;
  }
  v27 = FsRtlCheckOplockEx((POPLOCK)(v10.QuadPart + 88), Irp, 0, v3, RefsOplockComplete, RefsPrePostIrp);
  if ( v27 < 0 )
  {
    *(_DWORD *)(TrimContext + 148) = v27;
    goto LABEL_258;
  }
  if ( v27 == 259 )
  {
    *(_QWORD *)(TrimContext + 8) = 0;
    v3 = 0;
    v83 = 0;
    goto LABEL_258;
  }
  RefsBindMinstoreTransaction(v3);
  while ( 1 )
  {
    v65 = (unsigned int)v24;
    if ( (unsigned int)v24 >= MasterIrp[1] )
      break;
    v28 = *(_QWORD *)&MasterIrp[4 * (unsigned int)v24 + 2];
    v73 = v28;
    v29 = *(_QWORD *)&MasterIrp[4 * (unsigned int)v24 + 4];
    v70 = v29;
    v30 = 1 << *(_DWORD *)(v7 + 464);
    if ( v30 < 4096 )
      v30 = 4096;
    v31 = v30;
    v79 = 0;
    v32 = v28 % v30;
    if ( !v32 )
      goto LABEL_147;
    v33 = v30 - v32;
    v34 = v31 - v32 + v28;
    if ( v34 >= v28 )
    {
      v28 += v31 - v32;
      v73 = v34;
      if ( v29 < v33 )
      {
        v29 = 0;
        v70 = 0;
      }
      else
      {
        v29 += v32 - v31;
        v70 = v29;
      }
LABEL_147:
      v35 = *(_QWORD *)(v10.QuadPart + 24);
      if ( v28 >= v35 )
        goto LABEL_168;
      goto LABEL_157;
    }
    v7 = -1;
    v73 = -1;
    v24 = &WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 417, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225621LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741675);
    v35 = RefsRaiseStatusInternal(v83, 3221225621LL);
LABEL_157:
    if ( v29 + v28 < v28 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 418, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225621LL);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(-1073741675);
      RefsRaiseStatusInternal(v83, 3221225621LL);
      break;
    }
    if ( v29 + v28 > v35 )
    {
      v29 = v35 - v28;
      v70 = v35 - v28;
    }
    v70 = v29 - v29 % v31;
    v36 = *(_BYTE *)(v7 + 464);
    *(_QWORD *)&v79 = (__int64)v28 >> v36;
    *((_QWORD *)&v79 + 1) = v70 >> v36;
    v37 = MsFileLevelTrim(v3[3], *(CmsStream **)(v10.QuadPart + 360));
    Status = v37;
    if ( v37 < 0 )
    {
      v24 = &WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          419,
          WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
          (unsigned int)v37);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Status);
      RefsRaiseStatusInternal(v83, Status);
    }
LABEL_168:
    LODWORD(v24) = (_DWORD)v24 + 1;
  }
  RefsCheckpointCurrentTransaction(v3);
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))RefsPostUsnChangeWithOverrideOption)(
    v3,
    (union _LARGE_INTEGER)v10.QuadPart,
    1);
  RefsCheckpointCurrentTransaction(v3);
  ((void (__fastcall *)(_QWORD, _QWORD))RefsFlushForWriteThrough)(v3, (union _LARGE_INTEGER)v10.QuadPart);
  RefsTransferResourceToTrimContext(v38, TrimContext, *(_QWORD *)(v67 + 104), v82);
  v60 = 1;
  v39 = 0;
  v65 = 0;
  v40 = v66;
  while ( 1 )
  {
    v26 = (unsigned __int64)v69;
    if ( v39 >= v69[1] )
      break;
    v41 = *(union _LARGE_INTEGER *)&v69[4 * v39 + 2];
    StartingByte = v41;
    v42 = *(union _LARGE_INTEGER *)&v69[4 * v39 + 4];
    Length = v42;
    v43 = 1 << *(_DWORD *)(v40 + 464);
    if ( v43 < 4096 )
      v43 = 4096;
    v44 = v43;
    v45 = v41.QuadPart % (unsigned __int64)v43;
    if ( v45 )
    {
      v26 = v43 - v45;
      if ( v26 + v41.QuadPart < v41.QuadPart )
      {
        StartingByte.QuadPart = -1;
        v46 = -1073741675;
        v41.QuadPart = -1;
      }
      else
      {
        StartingByte.QuadPart = v43 - v45 + v41.QuadPart;
        v46 = 0;
        v41.QuadPart += v44 - v45;
      }
      if ( v46 < 0 )
      {
        if ( *(int *)(TrimContext + 148) >= 0 )
          *(_DWORD *)(TrimContext + 148) = v46;
        break;
      }
      if ( v42.QuadPart < v26 )
      {
        Length.QuadPart = 0;
        v42.QuadPart = 0;
      }
      else
      {
        v42.QuadPart += v45 - v44;
        Length = v42;
      }
    }
    v47 = *(_QWORD *)(v10.QuadPart + 24);
    if ( v41.QuadPart < v47 )
    {
      v26 = v42.QuadPart + v41.QuadPart;
      if ( v42.QuadPart + v41.QuadPart < (unsigned __int64)v41.QuadPart )
      {
        if ( *(int *)(TrimContext + 148) >= 0 )
          *(_DWORD *)(TrimContext + 148) = -1073741675;
        break;
      }
      if ( v26 > v47 )
      {
        v42.QuadPart = v47 - v41.QuadPart;
        Length.QuadPart = v47 - v41.QuadPart;
      }
      Length.QuadPart = v42.QuadPart - v42.QuadPart % v44;
      if ( Length.QuadPart )
      {
        if ( *(_QWORD *)(v10.QuadPart + 336) )
        {
          RequestorProcess = IoGetRequestorProcess(Irp);
          if ( !FsRtlFastCheckLockForWrite(
                  *(PFILE_LOCK *)(v10.QuadPart + 336),
                  &StartingByte,
                  &Length,
                  *v69,
                  CurrentStackLocation->FileObject,
                  RequestorProcess) )
          {
            v26 = (unsigned __int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                420,
                WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
                3221225556LL);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-1073741740);
            if ( *(int *)(TrimContext + 148) >= 0 )
              *(_DWORD *)(TrimContext + 148) = -1073741740;
            goto LABEL_257;
          }
        }
        FileOffset = StartingByte;
        v49 = Length;
        v76 = Length;
        while ( v49.QuadPart )
        {
          LowPart = v49.LowPart;
          if ( v49.QuadPart > 0xFFFFF000uLL )
            LowPart = -4096;
          if ( !CcPurgeCacheSection(
                  (PSECTION_OBJECT_POINTERS)(*(_QWORD *)(v10.QuadPart + 240) + 8LL),
                  &FileOffset,
                  LowPart,
                  2u) )
          {
            v26 = (unsigned __int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_D(
                WPP_GLOBAL_Control->AttachedDevice,
                421,
                WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
                3221226549LL);
            }
            if ( RefsStatusDebugEnabled )
              RefsStatusDebug(-1073740747);
            if ( *(int *)(TrimContext + 148) >= 0 )
              *(_DWORD *)(TrimContext + 148) = -1073740747;
            goto LABEL_257;
          }
          FileOffset.QuadPart += LowPart;
          v49.QuadPart -= LowPart;
          v76 = v49;
        }
        while ( Length.QuadPart )
        {
          v74 = 0;
          v71[0] = 0;
          v85 = 0;
          v51 = RefsLookupAllocationEx(
                  (_DWORD)v3,
                  v10.LowPart,
                  StartingByte.QuadPart >> *(_BYTE *)(v66 + 464),
                  1,
                  (__int64)&v74,
                  (__int64)v71,
                  v58,
                  v59,
                  0,
                  (__int64)&v85,
                  0,
                  0,
                  0x40000);
          RefsCheckpointCurrentTransaction(v3);
          if ( !v51 || v74 == -1 )
          {
            v55 = v71[0];
            v56.QuadPart = v71[0] << *(_BYTE *)(v66 + 464);
            if ( !v71[0] )
              v55 = 1;
            v71[0] = v55;
            if ( v56.QuadPart >= (unsigned __int64)Length.QuadPart )
            {
              StartingByte.QuadPart += Length.QuadPart;
              Length.QuadPart = 0;
              break;
            }
            Length.QuadPart -= v56.QuadPart;
            StartingByte.QuadPart += v56.QuadPart;
          }
          else
          {
            v52 = *(_BYTE *)(v66 + 464);
            v77 = v74 << v52;
            v53.QuadPart = v71[0] << v52;
            v78.QuadPart = v71[0] << v52;
            v54 = StartingByte.QuadPart % (unsigned __int64)*(unsigned int *)(v66 + 272);
            v68.QuadPart = 0;
            v80 = 0;
            v84 = 0;
            if ( v54 )
            {
              v77 = v54 + (v74 << v52);
              v53.QuadPart -= v54;
              v78 = v53;
            }
            if ( v53.QuadPart >= (unsigned __int64)Length.QuadPart )
            {
              v53 = Length;
              v68 = Length;
              Length.QuadPart = 0;
            }
            else
            {
              v68 = v53;
              Length.QuadPart -= v53.QuadPart;
            }
            *(_QWORD *)&v80 = StartingByte.QuadPart >> *(_BYTE *)(v66 + 464);
            *((_QWORD *)&v80 + 1) = v71[0];
            v81 = v80;
            ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))RefsIsRangeSharedOrCompacted)(
              v3,
              (union _LARGE_INTEGER)v10.QuadPart,
              &v81,
              &v84);
            StartingByte.QuadPart += v53.QuadPart;
            if ( v53.QuadPart && !v84 && (int)RefsAddExtentToTrimRequest(TrimContext) < 0 )
              goto LABEL_258;
          }
        }
        v39 = v65;
        v40 = v66;
      }
    }
    v65 = ++v39;
  }
LABEL_258:
  if ( *(_QWORD *)(TrimContext + 8) )
  {
    v26 = 1;
    Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  }
  if ( *(_QWORD *)(TrimContext + 32) && !v60 )
    RefsTransferResourceToTrimContext(v26, TrimContext, *(_QWORD *)(v67 + 104), v82);
  Statusa = RefsFinishTrimRequestAsync(TrimContext);
  MsCleanupFastResourceOwnerEntry(v82);
  if ( v3 )
  {
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(Statusa);
    RefsExtendedCompleteRequestInternal(v83, 0, Statusa);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
  {
    if ( (Statusa & 0x80000000) == 0 )
    {
      v57 = BYTE1(WPP_GLOBAL_Control->Timer) >= 5u;
      goto LABEL_273;
    }
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      goto LABEL_274;
    v57 = 0;
LABEL_273:
    if ( v57 )
LABEL_274:
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 422, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, Statusa);
  }
  if ( RefsStatusDebugEnabled )
    RefsStatusDebug(Statusa);
  return Statusa;
}

```

## disassembly

```asm
0x1c01a7610  mov     rax, rsp
0x1c01a7613  mov     [rax+10h], rdx
0x1c01a7617  mov     [rax+8], rcx
0x1c01a761b  push    rbx
0x1c01a761c  push    rsi
0x1c01a761d  push    rdi
0x1c01a761e  push    r12
0x1c01a7620  push    r13
0x1c01a7622  push    r14
0x1c01a7624  push    r15
0x1c01a7626  sub     rsp, 190h
0x1c01a762d  mov     r15, rdx
0x1c01a7630  mov     rdi, rcx
0x1c01a7633  xor     r12d, r12d
0x1c01a7636  mov     [rax-138h], r12
0x1c01a763d  mov     [rax-130h], r12
0x1c01a7644  mov     [rax-128h], r12
0x1c01a764b  mov     [rax-120h], r12
0x1c01a7652  mov     rsi, [rdx+0B8h]
0x1c01a7659  mov     [rsp+1C8h+var_E8], rsi
0x1c01a7661  mov     bl, [rcx+8]
0x1c01a7664  lea     r14d, [r12+1]
0x1c01a7669  and     bl, r14b
0x1c01a766c  mov     [rsp+1C8h+var_158], r12b
0x1c01a7671  xor     edx, edx; Val
0x1c01a7673  lea     r8d, [r12+58h]; Size
0x1c01a7678  lea     rcx, [rax-98h]; void *
0x1c01a767f  call    memset
0x1c01a7684  mov     [rsp+1C8h+var_198], r12b
0x1c01a7689  lea     rax, [rsp+1C8h+var_120]
0x1c01a7691  mov     [rsp+1C8h+PostIrpRoutine], rax
0x1c01a7696  lea     rax, [rsp+1C8h+var_128]
0x1c01a769e  mov     [rsp+1C8h+CompletionRoutine], rax
0x1c01a76a3  lea     r9, [rsp+1C8h+var_130]
0x1c01a76ab  lea     r8, [rsp+1C8h+var_138]
0x1c01a76b3  mov     rdx, [rsi+30h]
0x1c01a76b7  mov     rcx, rdi
0x1c01a76ba  call    RefsDecodeFileObject
0x1c01a76bf  cmp     eax, 2
0x1c01a76c2  jz      loc_1C01A7751
0x1c01a76c8  mov     al, cs:RefsStatusDebugEnabled
0x1c01a76ce  mov     edi, 0C000000Dh
0x1c01a76d3  test    al, al
0x1c01a76d5  jz      short loc_1C01A76EB
0x1c01a76d7  mov     r8d, 386Eh
0x1c01a76dd  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01a76e4  mov     ecx, edi; Status
0x1c01a76e6  call    RefsStatusDebug
0x1c01a76eb  mov     r8d, edi
0x1c01a76ee  mov     rdx, r15
0x1c01a76f1  mov     rcx, [rsp+1C8h+arg_0]
0x1c01a76f9  call    RefsExtendedCompleteRequestInternal
0x1c01a76fe  lea     rbx, WPP_GLOBAL_Control
0x1c01a7705  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01a770c  cmp     rcx, rbx
0x1c01a770f  jz      short loc_1C01A7738
0x1c01a7711  test    dword ptr [rcx+2Ch], 100h
0x1c01a7718  jz      short loc_1C01A7738
0x1c01a771a  cmp     byte ptr [rcx+29h], 4
0x1c01a771e  jb      short loc_1C01A7738
0x1c01a7720  mov     edx, 190h
0x1c01a7725  mov     r9d, edi
0x1c01a7728  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01a772f  mov     rcx, [rcx+18h]
0x1c01a7733  call    WPP_SF_D
0x1c01a7738  mov     al, cs:RefsStatusDebugEnabled
0x1c01a773e  test    al, al
0x1c01a7740  jz      loc_1C01A8B5C
0x1c01a7746  mov     r8d, 386Fh
0x1c01a774c  jmp     loc_1C01A8B4E
0x1c01a7751  mov     r13, [rsp+1C8h+var_138]
0x1c01a7759  mov     ecx, [r13+4]
0x1c01a775d  mov     eax, ecx
0x1c01a775f  and     eax, 0A000021h
0x1c01a7764  cmp     eax, r14d
0x1c01a7767  jz      loc_1C01A7944
0x1c01a776d  test    cl, 20h
0x1c01a7770  jz      loc_1C01A77FF
0x1c01a7776  mov     al, cs:RefsStatusDebugEnabled
0x1c01a777c  mov     edi, 0C0000189h
0x1c01a7781  test    al, al
0x1c01a7783  jz      short loc_1C01A7799
0x1c01a7785  mov     r8d, 3884h
0x1c01a778b  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01a7792  mov     ecx, edi; Status
0x1c01a7794  call    RefsStatusDebug
0x1c01a7799  mov     r8d, edi
0x1c01a779c  mov     rdx, r15
0x1c01a779f  mov     rcx, [rsp+1C8h+arg_0]
0x1c01a77a7  call    RefsExtendedCompleteRequestInternal
0x1c01a77ac  lea     rbx, WPP_GLOBAL_Control
0x1c01a77b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01a77ba  cmp     rcx, rbx
0x1c01a77bd  jz      short loc_1C01A77E6
0x1c01a77bf  test    dword ptr [rcx+2Ch], 100h
0x1c01a77c6  jz      short loc_1C01A77E6
0x1c01a77c8  cmp     byte ptr [rcx+29h], 4
0x1c01a77cc  jb      short loc_1C01A77E6
0x1c01a77ce  mov     edx, 191h
0x1c01a77d3  mov     r9d, edi
0x1c01a77d6  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01a77dd  mov     rcx, [rcx+18h]
0x1c01a77e1  call    WPP_SF_D
0x1c01a77e6  mov     cl, cs:RefsStatusDebugEnabled
0x1c01a77ec  test    cl, cl
0x1c01a77ee  jz      loc_1C01A8B5C
0x1c01a77f4  mov     r8d, 3885h
0x1c01a77fa  jmp     loc_1C01A8B4E
0x1c01a77ff  bt      ecx, 1Bh
0x1c01a7803  jb      loc_1C01A78A5
0x1c01a7809  test    r14b, cl
0x1c01a780c  jz      loc_1C01A78A5
0x1c01a7812  bt      ecx, 19h
0x1c01a7816  jnb     loc_1C01A7944
0x1c01a781c  mov     al, cs:RefsStatusDebugEnabled
0x1c01a7822  mov     edi, 0C00000A2h
0x1c01a7827  test    al, al
0x1c01a7829  jz      short loc_1C01A783F
0x1c01a782b  mov     r8d, 389Ah
0x1c01a7831  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01a7838  mov     ecx, edi; Status
0x1c01a783a  call    RefsStatusDebug
0x1c01a783f  mov     r8d, edi
0x1c01a7842  mov     rdx, r15
0x1c01a7845  mov     rcx, [rsp+1C8h+arg_0]
0x1c01a784d  call    RefsExtendedCompleteRequestInternal
0x1c01a7852  lea     rbx, WPP_GLOBAL_Control
0x1c01a7859  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01a7860  cmp     rcx, rbx
0x1c01a7863  jz      short loc_1C01A788C
0x1c01a7865  test    dword ptr [rcx+2Ch], 100h
0x1c01a786c  jz      short loc_1C01A788C
0x1c01a786e  cmp     byte ptr [rcx+29h], 4
0x1c01a7872  jb      short loc_1C01A788C
0x1c01a7874  mov     edx, 193h
0x1c01a7879  mov     r9d, edi
0x1c01a787c  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01a7883  mov     rcx, [rcx+18h]
0x1c01a7887  call    WPP_SF_D
0x1c01a788c  mov     cl, cs:RefsStatusDebugEnabled
0x1c01a7892  test    cl, cl
0x1c01a7894  jz      loc_1C01A8B5C
0x1c01a789a  mov     r8d, 389Bh
0x1c01a78a0  jmp     loc_1C01A8B4E
0x1c01a78a5  mov     al, cs:RefsStatusDebugEnabled
0x1c01a78ab  test    al, al
0x1c01a78ad  jz      short loc_1C01A78C6
0x1c01a78af  mov     r8d, 3890h
0x1c01a78b5  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01a78bc  mov     ecx, 0C000026Eh; Status
0x1c01a78c1  call    RefsStatusDebug
0x1c01a78c6  mov     r8d, 0C000026Eh
0x1c01a78cc  mov     rdx, r15
0x1c01a78cf  mov     rcx, [rsp+1C8h+arg_0]
0x1c01a78d7  call    RefsExtendedCompleteRequestInternal
0x1c01a78dc  lea     rbx, WPP_GLOBAL_Control
0x1c01a78e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01a78ea  cmp     rcx, rbx
0x1c01a78ed  jz      short loc_1C01A7919
0x1c01a78ef  test    dword ptr [rcx+2Ch], 100h
0x1c01a78f6  jz      short loc_1C01A7919
0x1c01a78f8  cmp     byte ptr [rcx+29h], 4
0x1c01a78fc  jb      short loc_1C01A7919
0x1c01a78fe  mov     edx, 192h
0x1c01a7903  mov     r9d, 0C000026Eh
0x1c01a7909  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01a7910  mov     rcx, [rcx+18h]
0x1c01a7914  call    WPP_SF_D
0x1c01a7919  mov     cl, cs:RefsStatusDebugEnabled
0x1c01a791f  test    cl, cl
0x1c01a7921  jz      short loc_1C01A793A
0x1c01a7923  mov     r8d, 3891h
0x1c01a7929  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01a7930  mov     ecx, 0C000026Eh; Status
0x1c01a7935  call    RefsStatusDebug
0x1c01a793a  mov     eax, 0C000026Eh
0x1c01a793f  jmp     loc_1C01A8B5E
0x1c01a7944  mov     r14, [rsp+1C8h+var_128]
0x1c01a794c  test    dword ptr [r14+130h], 1000000h
0x1c01a7957  jz      loc_1C01A79E6
0x1c01a795d  mov     al, cs:RefsStatusDebugEnabled
0x1c01a7963  mov     edi, 0C0000008h
0x1c01a7968  test    al, al
0x1c01a796a  jz      short loc_1C01A7980
0x1c01a796c  mov     r8d, 38A1h
0x1c01a7972  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01a7979  mov     ecx, edi; Status
0x1c01a797b  call    RefsStatusDebug
0x1c01a7980  mov     r8d, edi
0x1c01a7983  mov     rdx, r15
0x1c01a7986  mov     rcx, [rsp+1C8h+arg_0]
0x1c01a798e  call    RefsExtendedCompleteRequestInternal
0x1c01a7993  lea     rbx, WPP_GLOBAL_Control
0x1c01a799a  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01a79a1  cmp     rcx, rbx
0x1c01a79a4  jz      short loc_1C01A79CD
0x1c01a79a6  test    dword ptr [rcx+2Ch], 100h
0x1c01a79ad  jz      short loc_1C01A79CD
0x1c01a79af  cmp     byte ptr [rcx+29h], 4
0x1c01a79b3  jb      short loc_1C01A79CD
0x1c01a79b5  mov     edx, 194h
0x1c01a79ba  mov     r9d, edi
0x1c01a79bd  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01a79c4  mov     rcx, [rcx+18h]
0x1c01a79c8  call    WPP_SF_D
0x1c01a79cd  mov     cl, cs:RefsStatusDebugEnabled
0x1c01a79d3  test    cl, cl
0x1c01a79d5  jz      loc_1C01A8B5C
0x1c01a79db  mov     r8d, 38A2h
0x1c01a79e1  jmp     loc_1C01A8B4E
0x1c01a79e6  mov     rax, [rsp+1C8h+var_120]
0x1c01a79ee  test    rax, rax
0x1c01a79f1  jz      loc_1C01A7A8D
0x1c01a79f7  mov     eax, [rax+4]
0x1c01a79fa  bt      eax, 0Dh
0x1c01a79fe  jnb     loc_1C01A7A8D
0x1c01a7a04  mov     al, cs:RefsStatusDebugEnabled
0x1c01a7a0a  mov     edi, 0C000000Dh
0x1c01a7a0f  test    al, al
0x1c01a7a11  jz      short loc_1C01A7A27
0x1c01a7a13  mov     r8d, 38ADh
0x1c01a7a19  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01a7a20  mov     ecx, edi; Status
0x1c01a7a22  call    RefsStatusDebug
0x1c01a7a27  mov     r8d, edi
0x1c01a7a2a  mov     rdx, r15
0x1c01a7a2d  mov     rcx, [rsp+1C8h+arg_0]
0x1c01a7a35  call    RefsExtendedCompleteRequestInternal
0x1c01a7a3a  lea     rbx, WPP_GLOBAL_Control
0x1c01a7a41  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01a7a48  cmp     rcx, rbx
0x1c01a7a4b  jz      short loc_1C01A7A74
0x1c01a7a4d  test    dword ptr [rcx+2Ch], 100h
0x1c01a7a54  jz      short loc_1C01A7A74
0x1c01a7a56  cmp     byte ptr [rcx+29h], 4
0x1c01a7a5a  jb      short loc_1C01A7A74
0x1c01a7a5c  mov     edx, 195h
0x1c01a7a61  mov     r9d, edi
0x1c01a7a64  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01a7a6b  mov     rcx, [rcx+18h]
0x1c01a7a6f  call    WPP_SF_D
0x1c01a7a74  mov     al, cs:RefsStatusDebugEnabled
0x1c01a7a7a  test    al, al
0x1c01a7a7c  jz      loc_1C01A8B5C
0x1c01a7a82  mov     r8d, 38AEh
0x1c01a7a88  jmp     loc_1C01A8B4E
0x1c01a7a8d  mov     edx, 40FFh
0x1c01a7a92  test    [r14+0FCh], dx
0x1c01a7a9a  jnz     loc_1C01A8ACE
0x1c01a7aa0  cmp     [r14+102h], r12w
0x1c01a7aa8  jnz     loc_1C01A8ACE
0x1c01a7aae  mov     eax, [r14+88h]
0x1c01a7ab5  test    al, 8
0x1c01a7ab7  jnz     loc_1C01A8ACE
0x1c01a7abd  mov     r8d, [rsi+10h]
0x1c01a7ac1  cmp     r8d, 18h
0x1c01a7ac5  jnb     loc_1C01A7B54
0x1c01a7acb  mov     al, cs:RefsStatusDebugEnabled
0x1c01a7ad1  mov     edi, 0C000000Dh
0x1c01a7ad6  test    al, al
0x1c01a7ad8  jz      short loc_1C01A7AEE
0x1c01a7ada  mov     r8d, 38C3h
0x1c01a7ae0  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01a7ae7  mov     ecx, edi; Status
0x1c01a7ae9  call    RefsStatusDebug
0x1c01a7aee  mov     r8d, edi
0x1c01a7af1  mov     rdx, r15
0x1c01a7af4  mov     rcx, [rsp+1C8h+arg_0]
0x1c01a7afc  call    RefsExtendedCompleteRequestInternal
0x1c01a7b01  lea     rbx, WPP_GLOBAL_Control
0x1c01a7b08  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01a7b0f  cmp     rcx, rbx
0x1c01a7b12  jz      short loc_1C01A7B3B
0x1c01a7b14  test    dword ptr [rcx+2Ch], 100h
0x1c01a7b1b  jz      short loc_1C01A7B3B
0x1c01a7b1d  cmp     byte ptr [rcx+29h], 4
0x1c01a7b21  jb      short loc_1C01A7B3B
0x1c01a7b23  mov     edx, 197h
0x1c01a7b28  mov     r9d, edi
0x1c01a7b2b  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01a7b32  mov     rcx, [rcx+18h]
0x1c01a7b36  call    WPP_SF_D
0x1c01a7b3b  mov     al, cs:RefsStatusDebugEnabled
0x1c01a7b41  test    al, al
0x1c01a7b43  jz      loc_1C01A8B5C
0x1c01a7b49  mov     r8d, 38C4h
0x1c01a7b4f  jmp     loc_1C01A8B4E
0x1c01a7b54  mov     r12, [r15+18h]
0x1c01a7b58  mov     [rsp+1C8h+var_120], r12
0x1c01a7b60  mov     eax, [r12+4]
0x1c01a7b65  xor     r9d, r9d
0x1c01a7b68  test    eax, eax
0x1c01a7b6a  jz      loc_1C01A8A45
0x1c01a7b70  lea     edx, [rax-1]
0x1c01a7b73  shl     rdx, 4
0x1c01a7b77  mov     eax, 0FFFFFFFFh
0x1c01a7b7c  cmp     rdx, rax
0x1c01a7b7f  ja      loc_1C01A8A45
0x1c01a7b85  lea     eax, [rdx+18h]
0x1c01a7b88  cmp     eax, edx
  ... truncated ...
```
