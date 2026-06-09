# CClfsRequest::ReserveAndAppendLog(void)

- ea: `0x1400420fc`
- end: `0x140042cae`
- name: `?ReserveAndAppendLog@CClfsRequest@@AEAAJXZ`
- size: `2994`
- prototype: `__int64 __fastcall(CClfsRequest *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x14006c874`

## callees

- `0x14000bc14`
- `0x14000f3d4`
- `0x14000fdd8`
- `0x14000ff98`
- `0x1400104f4`
- `0x140010d88`
- `0x140014cec`
- `0x140014d00`
- `0x140017e22`
- `0x140017e70`
- `0x140017f20`
- `0x140018280`
- `0x140035904`
- `0x140035940`
- `0x140041098`
- `0x1400420fc`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140042586`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140042657`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140042797`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400429c8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140042586`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140042657`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140042797`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x1400429c8`
- `ntoskrnl!IoAllocateMdl` at `0x140042502`
- `ntoskrnl!IoAllocateMdl` at `0x1400425ec`
- `ntoskrnl!IoAllocateMdl` at `0x14004271f`
- `ntoskrnl!IoAllocateMdl` at `0x140042502`
- `ntoskrnl!IoAllocateMdl` at `0x1400425ec`
- `ntoskrnl!IoAllocateMdl` at `0x14004271f`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004254f`
- `ntoskrnl!MmProbeAndLockPages` at `0x140042626`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004275f`
- `ntoskrnl!MmProbeAndLockPages` at `0x140042997`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004254f`
- `ntoskrnl!MmProbeAndLockPages` at `0x140042626`
- `ntoskrnl!MmProbeAndLockPages` at `0x14004275f`
- `ntoskrnl!MmProbeAndLockPages` at `0x140042997`
- `ntoskrnl!IoFreeMdl` at `0x140042953`
- `ntoskrnl!IoFreeMdl` at `0x140042c5f`
- `ntoskrnl!IoFreeMdl` at `0x14007f01c`
- `ntoskrnl!IoFreeMdl` at `0x140042953`
- `ntoskrnl!IoFreeMdl` at `0x140042c5f`
- `ntoskrnl!IoFreeMdl` at `0x14007f01c`
- `ntoskrnl!MmUnlockPages` at `0x140042c50`
- `ntoskrnl!MmUnlockPages` at `0x14007f00c`
- `ntoskrnl!MmUnlockPages` at `0x140042c50`
- `ntoskrnl!MmUnlockPages` at `0x14007f00c`
- `ntoskrnl!IoIs32bitProcess` at `0x140042211`
- `ntoskrnl!IoIs32bitProcess` at `0x140042211`
- `ntoskrnl!ProbeForRead` at `0x14004224d`
- `ntoskrnl!ProbeForRead` at `0x140042320`
- `ntoskrnl!ProbeForRead` at `0x14004224d`
- `ntoskrnl!ProbeForRead` at `0x140042320`
- `ntoskrnl!ProbeForWrite` at `0x140042408`
- `ntoskrnl!ProbeForWrite` at `0x140042422`
- `ntoskrnl!ProbeForWrite` at `0x14004243c`
- `ntoskrnl!ProbeForWrite` at `0x140042408`
- `ntoskrnl!ProbeForWrite` at `0x140042422`
- `ntoskrnl!ProbeForWrite` at `0x14004243c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004290d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14004290d`

## pseudocode

```c
__int64 __fastcall CClfsRequest::ReserveAndAppendLog(CClfsRequest *this)
{
  struct _MDL *v2; // r15
  int v3; // ebx
  __int64 v4; // rax
  __int64 v5; // r13
  __int64 v6; // rcx
  _QWORD *v7; // rsi
  BOOLEAN v8; // al
  unsigned int v9; // ecx
  __int64 v10; // rsi
  __int64 ULong64FromUser; // rax
  struct _MDL *v12; // rax
  unsigned int v13; // ecx
  int v14; // edx
  __int64 v15; // rcx
  PVOID v16; // rax
  struct _MDL *v17; // rax
  __int64 v18; // rcx
  PVOID v19; // rax
  struct _MDL *v20; // rax
  PVOID MappedSystemVa; // rdx
  unsigned int v22; // ebx
  unsigned int AlignedBufferSize; // eax
  __int64 v24; // rdx
  PMDL *p_Mdl; // rcx
  int v26; // eax
  _DWORD *PoolWithTag; // rcx
  PMDL v28; // r13
  PVOID v29; // r13
  CClfsLogCcb *v30; // r12
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r10
  __int64 (__fastcall *v34)(__int64, __int64, PVOID, _QWORD, __int64 *, __int64 *, __int64 *, int, CClfsRequest *, CLFS_LSN *, __int64, __int64 *, CLFS_LSN *, _QWORD *, CLFS_LSN *); // rax
  _QWORD *v35; // rax
  __int64 v36; // rcx
  __int64 v38; // [rsp+0h] [rbp-218h] BYREF
  PMDL *v39; // [rsp+30h] [rbp-1E8h]
  int v40; // [rsp+38h] [rbp-1E0h]
  int v41; // [rsp+80h] [rbp-198h]
  struct _MDL *v42; // [rsp+88h] [rbp-190h]
  char v43; // [rsp+90h] [rbp-188h]
  ULONG v44; // [rsp+94h] [rbp-184h] BYREF
  unsigned int v45; // [rsp+98h] [rbp-180h]
  PVOID v46; // [rsp+A0h] [rbp-178h]
  PVOID v47; // [rsp+A8h] [rbp-170h]
  PMDL Mdl; // [rsp+B0h] [rbp-168h] BYREF
  __int64 v49; // [rsp+B8h] [rbp-160h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-158h] BYREF
  ULONG v51; // [rsp+C8h] [rbp-150h]
  CLFS_LSN v52; // [rsp+D0h] [rbp-148h] BYREF
  PVOID VirtualAddress; // [rsp+D8h] [rbp-140h]
  CLFS_LSN v54; // [rsp+E0h] [rbp-138h] BYREF
  volatile void *v55; // [rsp+E8h] [rbp-130h]
  CLFS_LSN v56; // [rsp+F0h] [rbp-128h] BYREF
  __int64 v57; // [rsp+F8h] [rbp-120h] BYREF
  __int64 v58; // [rsp+100h] [rbp-118h]
  __int64 v59; // [rsp+108h] [rbp-110h] BYREF
  _QWORD *v60; // [rsp+110h] [rbp-108h]
  PVOID v61; // [rsp+118h] [rbp-100h]
  CClfsLogCcb *v62; // [rsp+120h] [rbp-F8h]
  _QWORD v63[2]; // [rsp+128h] [rbp-F0h] BYREF
  _QWORD v64[8]; // [rsp+138h] [rbp-E0h] BYREF
  _QWORD Src[20]; // [rsp+178h] [rbp-A0h] BYREF
  KPROCESSOR_MODE AccessMode; // [rsp+228h] [rbp+10h]
  char v67; // [rsp+230h] [rbp+18h]
  ULONG Length; // [rsp+238h] [rbp+20h]

  v63[1] = &v38;
  v52 = CLFS_LSN_NULL;
  v63[0] = CLFS_LSN_INVALID.ullOffset;
  v54 = CLFS_LSN_INVALID;
  v56 = CLFS_LSN_NULL;
  v49 = 0;
  v50 = 0;
  v57 = 0;
  v59 = 0;
  memset(v64, 0, sizeof(v64));
  v2 = 0;
  v42 = 0;
  Mdl = 0;
  v3 = 0;
  v41 = 0;
  v44 = 0;
  memset(Src, 0, 0x40u);
  v60 = (_QWORD *)((char *)this + 48);
  v4 = *((_QWORD *)this + 6);
  AccessMode = *(_BYTE *)(v4 + 64);
  v5 = *(_QWORD *)(v4 + 184);
  v58 = *(_QWORD *)(v5 + 48);
  v6 = *(_QWORD *)(*(_QWORD *)(v58 + 24) + 120LL);
  *((_QWORD *)this + 18) = v6;
  v62 = *(CClfsLogCcb **)(*(_QWORD *)(v5 + 48) + 32LL);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 64LL))(v6);
  v7 = *(_QWORD **)(v5 + 32);
  v8 = IoIs32bitProcess(*((PIRP *)this + 6));
  v9 = *(_DWORD *)(v5 + 16);
  if ( v8 )
  {
    if ( v9 < 0x38 )
    {
LABEL_3:
      v3 = -1073741306;
LABEL_4:
      v41 = v3;
      goto LABEL_88;
    }
    ProbeForRead(v7, 0x38u, 8u);
    LODWORD(Src[7]) = *((_DWORD *)v7 + 11);
    Src[2] = v7[2];
    Src[0] = *v7;
    BYTE4(Src[7]) = *((_BYTE *)v7 + 48);
    Src[1] = *((unsigned int *)v7 + 2);
    Src[6] = *((unsigned int *)v7 + 10);
    Src[3] = *((unsigned int *)v7 + 6);
    Src[4] = *((unsigned int *)v7 + 7);
    v7 = Src;
  }
  else
  {
    if ( v9 < 0x40 )
      goto LABEL_3;
    ProbeForRead(v7, 0x40u, 8u);
  }
  v45 = *(_DWORD *)(v5 + 8);
  if ( v45 && !*(_QWORD *)(*((_QWORD *)this + 6) + 112LL) )
  {
    v3 = -1073741592;
    goto LABEL_4;
  }
  if ( AccessMode )
    RtlCopyFromUser(v64, v7, 0x40u);
  else
    RtlCopyVolatileMemory(v64, v7, 0x40u);
  v10 = v64[3];
  VirtualAddress = (PVOID)v64[3];
  Src[8] = v64[3];
  v46 = (PVOID)v64[4];
  Src[9] = v64[4];
  v55 = (volatile void *)v64[1];
  Src[10] = v64[1];
  Length = v64[7];
  v51 = v64[7];
  v47 = (PVOID)v64[6];
  v61 = (PVOID)v64[6];
  v56 = (CLFS_LSN)v64[5];
  ProbeForWrite((volatile void *)v64[3], 8u, 8u);
  ProbeForWrite(v46, 8u, 8u);
  ProbeForWrite(v55, 8u, 8u);
  if ( AccessMode )
    ULong64FromUser = RtlReadULong64FromUser(v64[1]);
  else
    ULong64FromUser = *(_QWORD *)v64[1];
  v50 = ULong64FromUser;
  v67 = BYTE4(v64[7]);
  v43 = BYTE4(v64[7]);
  v57 = v64[2];
  v49 = v64[0];
  *((_QWORD *)this + 15) = v10;
  if ( AccessMode )
    *((_QWORD *)this + 26) = RtlReadULong64FromUser(v64[3]);
  else
    RtlCopyVolatileMemory((char *)this + 208, (const void *)v64[3], 8u);
  *((_QWORD *)this + 16) = v46;
  if ( v67 )
  {
    v12 = IoAllocateMdl(VirtualAddress, 8u, 0, 1u, 0);
    *((_QWORD *)this + 11) = v12;
    if ( !v12 )
    {
      CClfsLogFcbCommon::ReportFlushFailure(5, 3221225473LL);
      v13 = 16;
LABEL_23:
      v3 = -1073741670;
      v14 = -1073741670;
      v41 = -1073741670;
LABEL_24:
      CClfsLogFcbCommon::SetGlobalFlushFailureTag(v13, v14);
      goto LABEL_88;
    }
    MmProbeAndLockPages(v12, AccessMode, IoWriteAccess);
    v15 = *((_QWORD *)this + 11);
    if ( (*(_BYTE *)(v15 + 10) & 5) != 0 )
      v16 = *(PVOID *)(v15 + 24);
    else
      v16 = MmMapLockedPagesSpecifyCache((PMDL)v15, 0, MmCached, 0, 0, 0x40000010u);
    if ( v16 )
    {
      *((_QWORD *)this + 15) = v16;
    }
    else
    {
      CClfsLogFcbCommon::ReportFlushFailure(8, 3221225473LL);
      v3 = -1073741670;
      v41 = -1073741670;
      CClfsLogFcbCommon::SetGlobalFlushFailureTag(0x11u, -1073741670);
    }
    if ( v3 < 0 )
      goto LABEL_88;
    v17 = IoAllocateMdl(v46, 8u, 0, 1u, 0);
    *((_QWORD *)this + 12) = v17;
    if ( !v17 )
    {
      CClfsLogFcbCommon::ReportFlushFailure(5, 3221225473LL);
      v13 = 18;
      goto LABEL_23;
    }
    MmProbeAndLockPages(v17, AccessMode, IoWriteAccess);
    v18 = *((_QWORD *)this + 12);
    if ( (*(_BYTE *)(v18 + 10) & 5) != 0 )
      v19 = *(PVOID *)(v18 + 24);
    else
      v19 = MmMapLockedPagesSpecifyCache((PMDL)v18, 0, MmCached, 0, 0, 0x40000010u);
    if ( v19 )
    {
      *((_QWORD *)this + 16) = v19;
    }
    else
    {
      CClfsLogFcbCommon::ReportFlushFailure(8, 3221225473LL);
      v3 = -1073741670;
      v41 = -1073741670;
      CClfsLogFcbCommon::SetGlobalFlushFailureTag(0x13u, -1073741670);
    }
  }
  if ( v3 < 0 )
    goto LABEL_88;
  if ( Length )
  {
    if ( !v47 )
    {
      v3 = -1073741811;
      goto LABEL_4;
    }
    v20 = IoAllocateMdl(v47, Length, 0, 1u, 0);
    v2 = v20;
    v42 = v20;
    if ( !v20 )
    {
      CClfsLogFcbCommon::ReportFlushFailure(5, 3221225473LL);
      v13 = 20;
      goto LABEL_23;
    }
    MmProbeAndLockPages(v20, AccessMode, IoWriteAccess);
    if ( (v2->MdlFlags & 5) != 0 )
      MappedSystemVa = v2->MappedSystemVa;
    else
      MappedSystemVa = MmMapLockedPagesSpecifyCache(v2, 0, MmCached, 0, 0, 0x40000010u);
    v47 = MappedSystemVa;
    v61 = MappedSystemVa;
    if ( !MappedSystemVa )
    {
      CClfsLogFcbCommon::ReportFlushFailure(8, 3221225473LL);
      v3 = -1073741670;
      v41 = -1073741670;
      CClfsLogFcbCommon::SetGlobalFlushFailureTag(0x15u, -1073741670);
      MappedSystemVa = v47;
    }
    if ( v3 < 0 )
      goto LABEL_88;
    v44 = Length;
    v3 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _DWORD, PVOID, ULONG *))(**((_QWORD **)this + 18)
                                                                                            + 240LL))(
           *((_QWORD *)this + 18),
           v58,
           0,
           0,
           0,
           MappedSystemVa,
           &v44);
    if ( v3 < 0 )
    {
      memset(v47, 0, Length);
      v51 = v44;
      if ( !v45 && !v49 )
        goto LABEL_4;
    }
  }
  v22 = v45;
  if ( !v45 )
  {
    v29 = 0;
LABEL_73:
    v30 = v62;
    v31 = *((_QWORD *)v62 + 13);
    if ( v31 + v49 < 0 || v31 - v50 < 0 )
    {
      v3 = -1072037872;
      goto LABEL_4;
    }
    CClfsRequest_State::Change_State_AppendPendingFlush(*((CClfsRequest_State **)this + 13), this);
    v32 = *((_QWORD *)this + 18);
    v33 = *((_QWORD *)this + 6) + 48LL;
    v34 = *(__int64 (__fastcall **)(__int64, __int64, PVOID, _QWORD, __int64 *, __int64 *, __int64 *, int, CClfsRequest *, CLFS_LSN *, __int64, __int64 *, CLFS_LSN *, _QWORD *, CLFS_LSN *))(*(_QWORD *)v32 + 120LL);
    LOBYTE(v40) = v67;
    v3 = v34(v32, v58, v29, v22, &v49, &v50, &v57, v40, this, &v56, v33, &v59, &v52, v63, &v54);
    v41 = v3;
    if ( v3 >= 0 )
    {
      *((_QWORD *)v30 + 13) += v59;
      if ( AccessMode )
        ((void (__fastcall *)(_QWORD, _QWORD))RtlWriteULong64ToUser)(VirtualAddress, (CLFS_LSN)v52.ullOffset);
      else
        RtlCopyVolatileMemory(VirtualAddress, &v52, 8u);
      if ( v3 != 259 )
      {
        if ( AccessMode )
          ((void (__fastcall *)(_QWORD, _QWORD))RtlWriteULong64ToUser)(v46, (CLFS_LSN)v54.ullOffset);
        else
          RtlCopyVolatileMemory(v46, &v54, 8u);
      }
      if ( AccessMode )
        RtlWriteULong64ToUser(v55, v50);
      else
        *(_QWORD *)v55 = v50;
      CClfsLogCcb::MarkAccessed(v30);
    }
    goto LABEL_88;
  }
  AlignedBufferSize = CClfsRequest::GetAlignedBufferSize(this, v45);
  v24 = *((_QWORD *)this + 6);
  p_Mdl = &Mdl;
  v39 = &Mdl;
  LOBYTE(p_Mdl) = AccessMode;
  v26 = ClfsProbeAndAllocateMdl(p_Mdl, *(_QWORD *)(v24 + 112), AlignedBufferSize);
  v3 = v26;
  v41 = v26;
  if ( v26 < 0 )
  {
    if ( v26 == -1073741670 )
      CClfsLogFcbCommon::ReportFlushFailure(5, 3221225473LL);
    v14 = v3;
    v13 = 22;
    goto LABEL_24;
  }
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x18u, 0x4A666C43u);
  if ( PoolWithTag )
  {
    *(_QWORD *)PoolWithTag = &CClfsMdlReference::`vftable';
    PoolWithTag[2] = 0;
    v28 = Mdl;
    *((_QWORD *)PoolWithTag + 2) = Mdl;
  }
  else
  {
    PoolWithTag = 0;
    v28 = Mdl;
  }
  *((_QWORD *)this + 10) = PoolWithTag;
  if ( !PoolWithTag )
  {
    IoFreeMdl(v28);
    Mdl = 0;
    CClfsLogFcbCommon::ReportFlushFailure(5, 3221225473LL);
    v13 = 23;
    goto LABEL_23;
  }
  (**(void (__fastcall ***)(PVOID))PoolWithTag)(PoolWithTag);
  MmProbeAndLockPages(v28, AccessMode, IoReadAccess);
  if ( (v28->MdlFlags & 5) != 0 )
    v29 = v28->MappedSystemVa;
  else
    v29 = MmMapLockedPagesSpecifyCache(v28, 0, MmCached, 0, 0, 0x40000010u);
  Src[11] = v29;
  if ( !v29 )
  {
    CClfsLogFcbCommon::ReportFlushFailure(8, 3221225473LL);
    v3 = -1073741670;
    v41 = -1073741670;
    CClfsLogFcbCommon::SetGlobalFlushFailureTag(0x18u, -1073741670);
  }
  if ( v3 >= 0 )
  {
    v22 = v45;
    goto LABEL_73;
  }
LABEL_88:
  v35 = v60;
  v36 = *v60;
  if ( v3 == 259 )
  {
    *(_BYTE *)(*(_QWORD *)(v36 + 184) + 3LL) |= 1u;
  }
  else
  {
    *(_DWORD *)(v36 + 48) = v3;
    *(_QWORD *)(*v35 + 56LL) = 0;
    CClfsRequest_State::Change_State_Done(*((CClfsRequest_State **)this + 13), this);
  }
  if ( v2 )
  {
    if ( (v2->MdlFlags & 2) != 0 )
      MmUnlockPages(v2);
    IoFreeMdl(v2);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400420fc  mov     r11, rsp
0x1400420ff  mov     [r11+8], rcx
0x140042103  push    rbx
0x140042104  push    rsi
0x140042105  push    rdi
0x140042106  push    r12
0x140042108  push    r13
0x14004210a  push    r14
0x14004210c  push    r15
0x14004210e  sub     rsp, 1E0h
0x140042115  mov     [rsp+218h+var_E8], rsp
0x14004211d  mov     r14, rcx
0x140042120  mov     rdx, qword ptr cs:CLFS_LSN_NULL
0x140042127  mov     [r11-148h], rdx
0x14004212e  mov     rax, qword ptr cs:CLFS_LSN_INVALID
0x140042135  mov     [r11-0F0h], rax
0x14004213c  mov     [r11-138h], rax
0x140042143  mov     [r11-128h], rdx
0x14004214a  xor     edi, edi
0x14004214c  mov     [r11-160h], rdi
0x140042153  mov     [r11-158h], rdi
0x14004215a  mov     [r11-120h], rdi
0x140042161  mov     [r11-110h], rdi
0x140042168  lea     esi, [rdi+40h]
0x14004216b  mov     r8d, esi; Size
0x14004216e  xor     edx, edx; Val
0x140042170  lea     rcx, [r11-0E0h]; void *
0x140042177  call    memset
0x14004217c  mov     r15d, edi
0x14004217f  mov     [rsp+218h+var_190], rdi
0x140042187  mov     [rsp+218h+Mdl], rdi
0x14004218f  mov     ebx, edi
0x140042191  mov     [rsp+218h+var_198], ebx
0x140042198  mov     [rsp+218h+var_184], edi
0x14004219f  mov     r8d, esi; Size
0x1400421a2  xor     edx, edx; Val
0x1400421a4  lea     rcx, [rsp+218h+Src]; void *
0x1400421ac  call    memset
0x1400421b1  lea     r12, [r14+30h]
0x1400421b5  mov     [rsp+218h+var_108], r12
0x1400421bd  mov     rax, [r12]
0x1400421c1  mov     cl, [rax+40h]
0x1400421c4  mov     [rsp+218h+AccessMode], cl
0x1400421cb  mov     r13, [rax+0B8h]
0x1400421d2  mov     rax, [r13+30h]
0x1400421d6  mov     [rsp+218h+var_118], rax
0x1400421de  mov     rax, [rax+18h]
0x1400421e2  mov     rcx, [rax+78h]
0x1400421e6  mov     [r14+90h], rcx
0x1400421ed  mov     rax, [r13+30h]
0x1400421f1  mov     rdx, [rax+20h]
0x1400421f5  mov     [rsp+218h+var_F8], rdx
0x1400421fd  mov     rax, [rcx]
0x140042200  mov     rax, [rax+40h]
0x140042204  call    _guard_dispatch_icall
0x140042209  mov     rsi, [r13+20h]
0x14004220d  mov     rcx, [r12]; Irp
0x140042211  call    cs:__imp_IoIs32bitProcess
0x140042218  nop     dword ptr [rax+rax+00h]
0x14004221d  mov     ecx, [r13+10h]
0x140042221  test    al, al
0x140042223  jz      loc_140042306
0x140042229  lea     edx, [rdi+38h]; Length
0x14004222c  cmp     ecx, edx
0x14004222e  jnb     short loc_140042241
0x140042230  mov     ebx, 0C0000206h
0x140042235  mov     [rsp+218h+var_198], ebx
0x14004223c  jmp     loc_140042C0B
0x140042241  mov     r12d, 8
0x140042247  mov     r8d, r12d; Alignment
0x14004224a  mov     rcx, rsi; Address
0x14004224d  call    cs:__imp_ProbeForRead
0x140042254  nop     dword ptr [rax+rax+00h]
0x140042259  nop
0x14004225a  mov     eax, [rsi+2Ch]
0x14004225d  mov     [rsp+218h+var_68], eax
0x140042264  mov     rax, [rsi+10h]
0x140042268  mov     [rsp+218h+var_90], rax
0x140042270  mov     rax, [rsi]
0x140042273  mov     [rsp+218h+Src], rax
0x14004227b  mov     al, [rsi+30h]
0x14004227e  mov     [rsp+218h+var_64], al
0x140042285  mov     eax, [rsi+8]
0x140042288  mov     [rsp+218h+var_98], rax
0x140042290  mov     eax, [rsi+28h]
0x140042293  mov     [rsp+218h+var_70], rax
0x14004229b  mov     eax, [rsi+18h]
0x14004229e  mov     [rsp+218h+var_88], rax
0x1400422a6  mov     eax, [rsi+1Ch]
0x1400422a9  mov     [rsp+218h+var_80], rax
0x1400422b1  lea     rsi, [rsp+218h+Src]
0x1400422b9  jmp     short loc_14004232D
0x1400422bb  mov     [rsp+218h+var_198], eax
0x1400422c2  mov     ecx, 0C00000E8h
0x1400422c7  cmp     eax, 0C0000005h
0x1400422cc  cmovz   eax, ecx
0x1400422cf  mov     [rsp+218h+var_198], eax
0x1400422d6  lea     rdx, loc_1400422EB
0x1400422dd  mov     rcx, [rsp+218h+var_E8]
0x1400422e5  call    _local_unwind_0
0x1400422ea  nop
0x1400422eb  mov     eax, [rsp+218h+var_198]
0x1400422f2  add     rsp, 1E0h
0x1400422f9  pop     r15
0x1400422fb  pop     r14
0x1400422fd  pop     r13
0x1400422ff  pop     r12
0x140042301  pop     rdi
0x140042302  pop     rsi
0x140042303  pop     rbx
0x140042304  retn
0x140042306  cmp     ecx, 40h ; '@'
0x140042309  jb      loc_140042230
0x14004230f  mov     r12d, 8
0x140042315  mov     r8d, r12d; Alignment
0x140042318  lea     edx, [r12+38h]; Length
0x14004231d  mov     rcx, rsi; Address
0x140042320  call    cs:__imp_ProbeForRead
0x140042327  nop     dword ptr [rax+rax+00h]
0x14004232c  nop
0x14004232d  mov     eax, [r13+8]
0x140042331  mov     [rsp+218h+var_180], eax
0x140042338  test    eax, eax
0x14004233a  jz      short loc_140042350
0x14004233c  mov     rax, [r14+30h]
0x140042340  cmp     [rax+70h], rdi
0x140042344  jnz     short loc_140042350
0x140042346  mov     ebx, 0C00000E8h
0x14004234b  jmp     loc_140042235
0x140042350  mov     r13b, [rsp+218h+AccessMode]
0x140042358  mov     r8d, 40h ; '@'; Size
0x14004235e  mov     rdx, rsi; Src
0x140042361  lea     rcx, [rsp+218h+var_E0]; void *
0x140042369  test    r13b, r13b
0x14004236c  jz      short loc_140042375
0x14004236e  call    RtlCopyFromUser
0x140042373  jmp     short loc_14004237A
0x140042375  call    RtlCopyVolatileMemory
0x14004237a  mov     rsi, [rsp+218h+Address]
0x140042382  mov     [rsp+218h+VirtualAddress], rsi
0x14004238a  mov     [rsp+218h+var_60], rsi
0x140042392  mov     rax, [rsp+218h+var_C0]
0x14004239a  mov     [rsp+218h+var_178], rax
0x1400423a2  mov     [rsp+218h+var_58], rax
0x1400423aa  mov     rax, [rsp+218h+var_D8]
0x1400423b2  mov     [rsp+218h+var_130], rax
0x1400423ba  mov     [rsp+218h+var_50], rax
0x1400423c2  mov     eax, [rsp+218h+var_A8]
0x1400423c9  mov     [rsp+218h+Length], eax
0x1400423d0  mov     [rsp+218h+var_150], eax
0x1400423d7  mov     rax, [rsp+218h+var_B0]
0x1400423df  mov     [rsp+218h+var_170], rax
0x1400423e7  mov     [rsp+218h+var_100], rax
0x1400423ef  mov     rax, [rsp+218h+var_B8]
0x1400423f7  mov     [rsp+218h+var_128], rax
0x1400423ff  mov     r8d, r12d; Alignment
0x140042402  mov     rdx, r12; Length
0x140042405  mov     rcx, rsi; Address
0x140042408  call    cs:__imp_ProbeForWrite
0x14004240f  nop     dword ptr [rax+rax+00h]
0x140042414  mov     r8d, r12d; Alignment
0x140042417  mov     rdx, r12; Length
0x14004241a  mov     rcx, [rsp+218h+var_178]; Address
0x140042422  call    cs:__imp_ProbeForWrite
0x140042429  nop     dword ptr [rax+rax+00h]
0x14004242e  mov     r8d, r12d; Alignment
0x140042431  mov     rdx, r12; Length
0x140042434  mov     rcx, [rsp+218h+var_130]; Address
0x14004243c  call    cs:__imp_ProbeForWrite
0x140042443  nop     dword ptr [rax+rax+00h]
0x140042448  mov     rax, [rsp+218h+var_D8]
0x140042450  test    r13b, r13b
0x140042453  jz      short loc_14004245F
0x140042455  mov     rcx, rax
0x140042458  call    RtlReadULong64FromUser
0x14004245d  jmp     short loc_140042462
0x14004245f  mov     rax, [rax]
0x140042462  mov     [rsp+218h+var_158], rax
0x14004246a  mov     al, [rsp+218h+var_A4]
0x140042471  mov     [rsp+218h+arg_10], al
0x140042478  mov     [rsp+218h+var_188], al
0x14004247f  mov     rax, [rsp+218h+var_D0]
0x140042487  mov     [rsp+218h+var_120], rax
0x14004248f  mov     rax, [rsp+218h+var_E0]
0x140042497  mov     [rsp+218h+var_160], rax
0x14004249f  mov     [r14+78h], rsi
0x1400424a3  mov     rdx, [rsp+218h+Address]; Src
0x1400424ab  lea     rsi, [r14+0D0h]
0x1400424b2  test    r13b, r13b
0x1400424b5  jz      short loc_1400424C4
0x1400424b7  mov     rcx, rdx
0x1400424ba  call    RtlReadULong64FromUser
0x1400424bf  mov     [rsi], rax
0x1400424c2  jmp     short loc_1400424CF
0x1400424c4  mov     r8, r12; Size
0x1400424c7  mov     rcx, rsi; void *
0x1400424ca  call    RtlCopyVolatileMemory
0x1400424cf  mov     rax, [rsp+218h+var_178]
0x1400424d7  mov     [r14+80h], rax
0x1400424de  cmp     [rsp+218h+arg_10], dil
0x1400424e6  jz      loc_1400426D3
0x1400424ec  mov     [rsp+218h+Irp], rdi; Irp
0x1400424f1  mov     r9b, 1; ChargeQuota
0x1400424f4  xor     r8d, r8d; SecondaryBuffer
0x1400424f7  mov     edx, r12d; Length
0x1400424fa  mov     rcx, [rsp+218h+VirtualAddress]; VirtualAddress
0x140042502  call    cs:__imp_IoAllocateMdl
0x140042509  nop     dword ptr [rax+rax+00h]
0x14004250e  mov     [r14+58h], rax
0x140042512  test    rax, rax
0x140042515  jnz     short loc_140042543
0x140042517  mov     edx, 0C0000001h
0x14004251c  lea     ecx, [rax+5]
0x14004251f  call    ?ReportFlushFailure@CClfsLogFcbCommon@@SAXW4_CLFS_FLUSH_FAILURE@@J@Z; CClfsLogFcbCommon::ReportFlushFailure(_CLFS_FLUSH_FAILURE,long)
0x140042524  mov     esi, 0C000009Ah
0x140042529  mov     ecx, 10h; unsigned int
0x14004252e  mov     ebx, esi
0x140042530  mov     edx, esi; int
0x140042532  mov     [rsp+218h+var_198], ebx
0x140042539  call    ?SetGlobalFlushFailureTag@CClfsLogFcbCommon@@SAXKJ@Z; CClfsLogFcbCommon::SetGlobalFlushFailureTag(ulong,long)
0x14004253e  jmp     loc_140042C0B
0x140042543  mov     r8d, 1; Operation
0x140042549  mov     dl, r13b; AccessMode
0x14004254c  mov     rcx, rax; MemoryDescriptorList
0x14004254f  call    cs:__imp_MmProbeAndLockPages
0x140042556  nop     dword ptr [rax+rax+00h]
0x14004255b  mov     rcx, [r14+58h]; MemoryDescriptorList
0x14004255f  mov     r13d, 5
0x140042565  test    [rcx+0Ah], r13b
0x140042569  jz      short loc_140042571
0x14004256b  mov     rax, [rcx+18h]
0x14004256f  jmp     short loc_140042592
0x140042571  mov     [rsp+218h+Priority], 40000010h; Priority
0x140042579  mov     dword ptr [rsp+218h+Irp], edi; BugCheckOnFailure
0x14004257d  xor     r9d, r9d; RequestedAddress
0x140042580  xor     edx, edx; AccessMode
0x140042582  lea     r8d, [r9+1]; CacheType
0x140042586  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004258d  nop     dword ptr [rax+rax+00h]
0x140042592  mov     r12d, 0C0000001h
0x140042598  test    rax, rax
0x14004259b  jnz     short loc_1400425C4
0x14004259d  mov     edx, r12d
0x1400425a0  lea     ecx, [rax+8]
0x1400425a3  call    ?ReportFlushFailure@CClfsLogFcbCommon@@SAXW4_CLFS_FLUSH_FAILURE@@J@Z; CClfsLogFcbCommon::ReportFlushFailure(_CLFS_FLUSH_FAILURE,long)
0x1400425a8  mov     esi, 0C000009Ah
0x1400425ad  mov     ebx, esi
0x1400425af  mov     [rsp+218h+var_198], ebx
0x1400425b6  mov     edx, esi; int
0x1400425b8  mov     ecx, 11h; unsigned int
0x1400425bd  call    ?SetGlobalFlushFailureTag@CClfsLogFcbCommon@@SAXKJ@Z; CClfsLogFcbCommon::SetGlobalFlushFailureTag(ulong,long)
0x1400425c2  jmp     short loc_1400425CD
0x1400425c4  mov     [r14+78h], rax
0x1400425c8  mov     esi, 0C000009Ah
0x1400425cd  test    ebx, ebx
0x1400425cf  js      loc_140042C0B
0x1400425d5  mov     [rsp+218h+Irp], rdi; Irp
0x1400425da  mov     r9b, 1; ChargeQuota
0x1400425dd  xor     r8d, r8d; SecondaryBuffer
0x1400425e0  lea     edx, [r8+8]; Length
0x1400425e4  mov     rcx, [rsp+218h+var_178]; VirtualAddress
0x1400425ec  call    cs:__imp_IoAllocateMdl
0x1400425f3  nop     dword ptr [rax+rax+00h]
0x1400425f8  mov     [r14+60h], rax
0x1400425fc  test    rax, rax
0x1400425ff  jnz     short loc_140042616
0x140042601  mov     edx, r12d
0x140042604  mov     ecx, r13d
0x140042607  call    ?ReportFlushFailure@CClfsLogFcbCommon@@SAXW4_CLFS_FLUSH_FAILURE@@J@Z; CClfsLogFcbCommon::ReportFlushFailure(_CLFS_FLUSH_FAILURE,long)
0x14004260c  mov     ecx, 12h
0x140042611  jmp     loc_14004252E
0x140042616  mov     r8d, 1; Operation
0x14004261c  mov     dl, [rsp+218h+AccessMode]; AccessMode
0x140042623  mov     rcx, rax; MemoryDescriptorList
0x140042626  call    cs:__imp_MmProbeAndLockPages
0x14004262d  nop     dword ptr [rax+rax+00h]
0x140042632  mov     rcx, [r14+60h]; MemoryDescriptorList
0x140042636  test    [rcx+0Ah], r13b
0x14004263a  jz      short loc_140042642
0x14004263c  mov     rax, [rcx+18h]
0x140042640  jmp     short loc_140042663
0x140042642  mov     [rsp+218h+Priority], 40000010h; Priority
0x14004264a  mov     dword ptr [rsp+218h+Irp], edi; BugCheckOnFailure
0x14004264e  xor     r9d, r9d; RequestedAddress
0x140042651  xor     edx, edx; AccessMode
0x140042653  lea     r8d, [r9+1]; CacheType
0x140042657  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14004265e  nop     dword ptr [rax+rax+00h]
0x140042663  test    rax, rax
0x140042666  jnz     short loc_14004268A
0x140042668  mov     edx, r12d
0x14004266b  lea     ecx, [rax+8]
0x14004266e  call    ?ReportFlushFailure@CClfsLogFcbCommon@@SAXW4_CLFS_FLUSH_FAILURE@@J@Z; CClfsLogFcbCommon::ReportFlushFailure(_CLFS_FLUSH_FAILURE,long)
0x140042673  mov     ebx, esi
0x140042675  mov     [rsp+218h+var_198], ebx
0x14004267c  mov     edx, esi; int
0x14004267e  mov     ecx, 13h; unsigned int
0x140042683  call    ?SetGlobalFlushFailureTag@CClfsLogFcbCommon@@SAXKJ@Z; CClfsLogFcbCommon::SetGlobalFlushFailureTag(ulong,long)
0x140042688  jmp     short loc_140042691
0x14004268a  mov     [r14+80h], rax
  ... truncated ...
```
