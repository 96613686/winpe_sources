# NtfsGetReparsePointValue

- ea: `0x14029c204`
- end: `0x14029caeb`
- name: `NtfsGetReparsePointValue`
- size: `2279`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int16, char)`
- caller_count: `3`
- callee_count: `25`
- tags: `reparse_path, authz_impersonation, installer_update`

## callers

- `0x1401a2d00`
- `0x1402195a0`
- `0x14029cb00`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000c450`
- `0x140012e70`
- `0x140021e60`
- `0x140030450`
- `0x140039e58`
- `0x1400410a8`
- `0x140044500`
- `0x140059440`
- `0x140059740`
- `0x140125100`
- `0x140125fc0`
- `0x140148f80`
- `0x140162110`
- `0x140166564`
- `0x14017f8c0`
- `0x140184220`
- `0x140185c50`
- `0x14019a768`
- `0x1401e06b0`
- `0x140207b80`
- `0x14022910c`
- `0x14029c204`
- `0x14029f090`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14029c705`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14029c705`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14029c53e`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14029c53e`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x14029c47c`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x14029c47c`
- `ntoskrnl!IoCheckRedirectionTrustLevel3` at `0x14029c771`
- `ntoskrnl!IoCheckRedirectionTrustLevel3` at `0x14029c771`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029c9e0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c0374`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029c9e0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c0374`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14029c901`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14029c901`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029c834`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029c988`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029c834`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029c988`
- `ntoskrnl!CcUnpinData` at `0x14029ca0f`
- `ntoskrnl!CcUnpinData` at `0x1402c03a7`
- `ntoskrnl!CcUnpinData` at `0x14029ca0f`
- `ntoskrnl!CcUnpinData` at `0x1402c03a7`

## pseudocode

```c
__int64 __fastcall NtfsGetReparsePointValue(__int64 a1, __int64 a2, IRP *a3, __int64 a4, __int16 a5, char a6)
{
  __int64 v7; // rsi
  __int64 v8; // rbx
  char v9; // r14
  __int64 v10; // rcx
  _DWORD *v11; // r13
  int v12; // r9d
  int *AuxiliaryBuffer; // rcx
  unsigned int v14; // r15d
  __int64 v15; // r8
  unsigned int *p_ReparseTag; // r15
  unsigned int *v17; // r9
  __int64 v18; // rdx
  bool v19; // r10
  char v20; // al
  IRP *v21; // r14
  __int64 v22; // r14
  BOOL v23; // esi
  __int64 v24; // rbx
  unsigned int v25; // edi
  __int64 v26; // rdx
  int v27; // eax
  int v28; // edi
  int v29; // ebx
  CHAR *v30; // rax
  unsigned int *v31; // rdi
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  PVOID v34; // rdi
  int Scb; // eax
  int v36; // r9d
  int v37; // r8d
  CHAR *PoolWithTag; // rax
  char v40; // [rsp+50h] [rbp-D8h]
  char v41; // [rsp+51h] [rbp-D7h]
  char v42; // [rsp+52h] [rbp-D6h]
  ULONG BufferLength; // [rsp+58h] [rbp-D0h] BYREF
  int v44; // [rsp+5Ch] [rbp-CCh]
  PVOID v45; // [rsp+60h] [rbp-C8h]
  PVOID Bcb; // [rsp+68h] [rbp-C0h] BYREF
  PREPARSE_DATA_BUFFER v47; // [rsp+70h] [rbp-B8h]
  _DWORD *v48; // [rsp+78h] [rbp-B0h]
  PREPARSE_DATA_BUFFER ReparseBuffer; // [rsp+80h] [rbp-A8h] BYREF
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+88h] [rbp-A0h] BYREF
  _QWORD v51[19]; // [rsp+90h] [rbp-98h] BYREF

  v7 = a2;
  v8 = a1;
  v41 = 0;
  if ( !a6 || (v9 = 1, (*(_DWORD *)(*(_QWORD *)(a2 + 176) + 16LL) & 0x200000) == 0) )
    v9 = 0;
  memset(v51, 0, 0x58u);
  ReparseBuffer = 0;
  BufferLength = 0;
  v48 = 0;
  Bcb = 0;
  v45 = 0;
  if ( !(unsigned int)TxfUseCurrentFileInfo(v8, a4, 1, *(_QWORD *)(v7 + 184)) )
  {
    v10 = *(_QWORD *)(a4 + 328);
    if ( (*(_DWORD *)(v10 + 4) & 0x40000) != 0 )
    {
      v11 = *(_DWORD **)(*(_QWORD *)(v10 + 48) + 8LL);
      v48 = v11;
      NtfsAcquireSharedFcb(v8, v11, 0, 1);
      v41 = 1;
      if ( (v11[44] & 0x400) != 0 )
        goto LABEL_9;
      NtfsReleaseFcbEx(v8, v11, 0);
      v41 = 0;
    }
  }
  v11 = (_DWORD *)a4;
  v48 = (_DWORD *)a4;
LABEL_9:
  if ( !(unsigned __int8)NtfsLookupInFileRecord(v8, v11, v11 + 2, 192, 0, 0, 0, 0, 0, v51) )
  {
    v28 = 678868;
    NtfsAttachCorruption_BadOrOrphanFRS(v8, 2, 678868, v12, (__int64)(v11 + 2), (__int64)v11, 0);
    NtfsAttachRepairInfoPriv(v8, 256, 0, 0x6B000A5BD4LL);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v8, 3221225730LL, 678868);
    NtfsRaiseStatusInternal(v8, -1073741566, (_DWORD)v11 + 8, (_DWORD)v11, 678868);
    goto LABEL_115;
  }
  NtfsMapAttributeValue(v8, v11, &ReparseBuffer, &BufferLength, &Bcb, v51);
  if ( BufferLength > 0x4000 )
  {
    if ( (unsigned __int8)NtfsTelemetryGuard(512) )
      NtfsTelemetryBadReparse(a4, 2147483653LL, BufferLength, 0);
    v14 = v9 == 0 ? 0xC0000278 : 0;
    v44 = v14;
    if ( !NtfsStatusDebugFlags
      || !v14
      || v14 == 294
      || v14 - 298 <= 1
      || v14 == -1073741802
      || v14 + 2147483643 <= 1
      || v14 == -1073741807
      || v14 == 259
      || v14 == -1073741608 )
    {
      goto LABEL_101;
    }
    v15 = 678920;
LABEL_23:
    NtfsStatusTraceAndDebugInternal(0, v14, v15);
LABEL_101:
    v34 = v45;
    goto LABEL_102;
  }
  v47 = ReparseBuffer;
  v14 = FsRtlValidateReparsePointBuffer(BufferLength, ReparseBuffer);
  v44 = v14;
  if ( (v14 & 0x80000000) != 0 )
  {
    if ( (unsigned __int8)NtfsTelemetryGuard(512) )
      NtfsTelemetryBadReparse(a4, v14, BufferLength, v47);
    if ( !v9 )
    {
      if ( !NtfsStatusDebugFlags
        || v14 >= 0xFFFFFFED
        || v14 == -1073741802
        || v14 + 2147483643 <= 1
        || v14 == -1073741807
        || v14 == -1073741608 )
      {
        goto LABEL_101;
      }
      v15 = 678960;
      goto LABEL_23;
    }
LABEL_100:
    v44 = 0;
    v14 = 0;
    goto LABEL_101;
  }
  v40 = 1;
  p_ReparseTag = &v47->ReparseTag;
  if ( (v11[44] & 0x10000000) == 0
    || (v42 = 1, !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(v47->ReparseTag)) )
  {
    v42 = 0;
  }
  if ( BufferLength < (unsigned int)*((unsigned __int16 *)p_ReparseTag + 2) + 24 )
    v17 = 0;
  else
    v17 = p_ReparseTag + 2;
  NtfsLookupOpenReparseEcp(v8, v7, *p_ReparseTag, v17);
  v18 = v7 + 216;
  v19 = v9 && (!*(_QWORD *)v18 || (*(_DWORD *)(*(_QWORD *)v18 + 20LL) & 0x40) == 0);
  if ( *(_QWORD *)v18 )
  {
    *(_DWORD *)(*(_QWORD *)v18 + 20LL) |= 1u;
    if ( a6 )
    {
      if ( v42 )
      {
        AuxiliaryBuffer = (int *)*(unsigned int *)(*(_QWORD *)v18 + 20LL);
        if ( ((unsigned __int8)AuxiliaryBuffer & 8) != 0 )
          goto LABEL_53;
        goto LABEL_52;
      }
      AuxiliaryBuffer = (int *)*(unsigned int *)(*(_QWORD *)v18 + 20LL);
      if ( ((unsigned __int8)AuxiliaryBuffer & 0x20) == 0 )
LABEL_52:
        v40 = 0;
    }
LABEL_53:
    v18 = v7 + 216;
    goto LABEL_54;
  }
  if ( a6 && v42 )
  {
    v20 = 0;
    goto LABEL_55;
  }
LABEL_54:
  v20 = v40;
LABEL_55:
  if ( !v20 || v19 )
  {
    if ( *(_QWORD *)v18 && (*(_DWORD *)(*(_QWORD *)v18 + 20LL) & 0x80u) != 0 && a6 )
    {
      PoolWithTag = (CHAR *)ExAllocatePoolWithTag((POOL_TYPE)528, BufferLength, 0x4346744Eu);
      a3->Tail.Overlay.AuxiliaryBuffer = PoolWithTag;
      memmove(PoolWithTag, ReparseBuffer, BufferLength);
      AuxiliaryBuffer = (int *)a3->Tail.Overlay.AuxiliaryBuffer;
      *((_WORD *)AuxiliaryBuffer + 3) = 0;
    }
    goto LABEL_100;
  }
  v14 = 260;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 260, 679022);
  v44 = 260;
  v21 = a3;
  if ( (a3->Tail.Overlay.CurrentStackLocation->Flags & 4) != 0 )
    a5 += *(_WORD *)(v7 + 68) - *(_WORD *)(v7 + 16);
  if ( !a5 && v47->ReparseTag == -1610612733 )
    NtfsAccessCheck(
      v8,
      v7,
      (_QWORD *)a4,
      0,
      (__int64)a3,
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 176) + 8LL) + 8LL) + 24LL),
      1u,
      0,
      0);
  Feature_JunctionRedirectionTrust__private_ReportDeviceUsage();
  if ( v47->ReparseTag == -1610612733 || v47->ReparseTag == -1610612724 )
  {
    if ( (*(_DWORD *)(a4 + 4) & 8) == 0 )
      NtfsUpdateFcbInfoFromDisk(v8, 0, 0);
    Feature_RedirectionGuardNonFixedDrive__private_IsEnabledPreCheck();
    Feature_RedirectionGuardForSMB__private_ReportDeviceUsage();
    ExtraCreateParameter = 0;
    IoGetIrpExtraCreateParameter(a3, &ExtraCreateParameter);
    v22 = v7 + 16;
    if ( (*(_DWORD *)(v7 + 156) & 0x40) != 0 )
      v22 = 0;
    v23 = v47->ReparseTag != -1610612733;
    v24 = *(_QWORD *)(a2 + 32);
    v25 = *(unsigned __int8 *)(a4 + 37);
    LOBYTE(v26) = NtfsEffectiveMode(a3);
    v27 = IoCheckRedirectionTrustLevel3((unsigned int)(v23 + 1), v26, 0, v25, v22, v24, ExtraCreateParameter);
    v28 = v27;
    if ( v27 < 0 )
    {
      if ( NtfsStatusDebugFlags
        && (unsigned int)v27 < 0xFFFFFFED
        && v27 != -1073741802
        && (unsigned int)(v27 + 2147483643) > 1
        && v27 != -1073741807
        && v27 != -1073741608 )
      {
        v29 = a1;
        NtfsStatusTraceAndDebugInternal(a1, (unsigned int)v27, 679214);
LABEL_116:
        NtfsRaiseStatusInternal(v29, v28, 0, 0, 679214);
        __debugbreak();
        JUMPOUT(0x14029CAEBLL);
      }
LABEL_115:
      v29 = a1;
      goto LABEL_116;
    }
    v8 = a1;
    v7 = a2;
    v21 = a3;
  }
  v30 = (CHAR *)ExAllocatePoolWithTag((POOL_TYPE)528, BufferLength, 0x4346744Eu);
  v21->Tail.Overlay.AuxiliaryBuffer = v30;
  memmove(v30, ReparseBuffer, BufferLength);
  v31 = (unsigned int *)v21->Tail.Overlay.AuxiliaryBuffer;
  *((_WORD *)v31 + 3) = a5;
  if ( !*(_BYTE *)(v8 + 32) && *v31 == -1610612724 )
  {
    v32 = v31[4];
    if ( (v11[44] & 0x10000000) != 0 )
      v33 = v32 | 0x80000000;
    else
      v33 = v32 | 0x40000000;
    v31[4] = v33;
    Feature_JunctionRedirectionTrust__private_ReportDeviceUsage();
    v31[4] |= *(unsigned __int8 *)(a4 + 37) << 28;
  }
  AuxiliaryBuffer = *(int **)(v7 + 216);
  if ( AuxiliaryBuffer && AuxiliaryBuffer[5] < 0 )
    *((_WORD *)AuxiliaryBuffer + 21) = a5;
  v21->IoStatus.Information = *v31;
  if ( v11[67] )
  {
    NtfsMoveFcbToDelayCloseTail(v11);
    goto LABEL_101;
  }
  if ( v11[5] )
    goto LABEL_101;
  v34 = ExAllocateFromLookasideListEx(&NtfsCloseEntryLookasideList);
  v45 = v34;
  if ( v34 )
  {
    Scb = (unsigned int)NtfsCreateScb(v8, (__int64)v11, 160, &NtfsFileNameIndex, 0, 0, 0);
    LOBYTE(v36) = 1;
    LOBYTE(v37) = 1;
    NtfsAddScbToFspClose(v8, Scb, v37, v36, v34);
    v34 = 0;
    v45 = 0;
  }
LABEL_102:
  if ( v34 )
    ExFreeToLookasideListEx(&NtfsCloseEntryLookasideList, v34);
  if ( v51[2] )
  {
    AuxiliaryBuffer = (int *)Bcb;
    if ( !Bcb )
      goto LABEL_109;
    CcUnpinData(Bcb);
  }
  else
  {
    v51[2] = Bcb;
  }
  Bcb = 0;
LABEL_109:
  NtfsCleanupAttributeContext(AuxiliaryBuffer, v51);
  if ( v41 )
    NtfsReleaseFcbEx(v8, v11, 0);
  return v14;
}

```

## disassembly

```asm
0x14029c204  mov     rax, rsp
0x14029c207  mov     [rax+20h], r9
0x14029c20b  mov     [rax+18h], r8
0x14029c20f  mov     [rax+10h], rdx
0x14029c213  mov     [rax+8], rcx
0x14029c217  push    rbx
0x14029c218  push    rsi
0x14029c219  push    rdi
0x14029c21a  push    r13
0x14029c21c  push    r14
0x14029c21e  push    r15
0x14029c220  sub     rsp, 0F8h
0x14029c227  mov     rdi, r9
0x14029c22a  mov     rsi, rdx
0x14029c22d  mov     rbx, rcx
0x14029c230  xor     r15d, r15d
0x14029c233  mov     [rsp+128h+var_D7], r15b
0x14029c238  mov     [rsp+128h+var_D4], r15b
0x14029c23d  mov     [rsp+128h+var_D5], r15b
0x14029c242  cmp     [rsp+128h+arg_28], r15b
0x14029c24a  jz      short loc_14029C25F
0x14029c24c  mov     rax, [rdx+0B0h]
0x14029c253  test    dword ptr [rax+10h], 200000h
0x14029c25a  mov     r14b, 1
0x14029c25d  jnz     short loc_14029C262
0x14029c25f  mov     r14b, r15b
0x14029c262  xor     edx, edx; Val
0x14029c264  lea     r8d, [rdx+58h]; Size
0x14029c268  lea     rcx, [rsp+128h+var_98]; void *
0x14029c270  call    memset
0x14029c275  mov     [rsp+128h+ReparseBuffer], r15
0x14029c27d  mov     [rsp+128h+BufferLength], r15d
0x14029c282  mov     [rsp+128h+var_B0], r15
0x14029c287  mov     [rsp+128h+Bcb], r15
0x14029c28c  mov     [rsp+128h+var_C8], r15
0x14029c291  mov     [rsp+128h+var_D4], 1
0x14029c296  mov     r9, [rsi+0B8h]
0x14029c29d  mov     r8d, 1
0x14029c2a3  mov     rdx, rdi
0x14029c2a6  mov     rcx, rbx
0x14029c2a9  call    TxfUseCurrentFileInfo
0x14029c2ae  test    eax, eax
0x14029c2b0  jnz     short loc_14029C308
0x14029c2b2  mov     rcx, [rdi+148h]
0x14029c2b9  test    dword ptr [rcx+4], 40000h
0x14029c2c0  jz      short loc_14029C308
0x14029c2c2  mov     rax, [rcx+30h]
0x14029c2c6  mov     r13, [rax+8]
0x14029c2ca  mov     [rsp+128h+var_B0], r13
0x14029c2cf  mov     r9d, 1
0x14029c2d5  xor     r8d, r8d
0x14029c2d8  mov     rdx, r13
0x14029c2db  mov     rcx, rbx
0x14029c2de  call    NtfsAcquireSharedFcb
0x14029c2e3  mov     [rsp+128h+var_D7], 1
0x14029c2e8  test    dword ptr [r13+0B0h], 400h
0x14029c2f3  jnz     short loc_14029C310
0x14029c2f5  xor     r8d, r8d
0x14029c2f8  mov     rdx, r13
0x14029c2fb  mov     rcx, rbx
0x14029c2fe  call    NtfsReleaseFcbEx
0x14029c303  mov     [rsp+128h+var_D7], r15b
0x14029c308  mov     r13, rdi
0x14029c30b  mov     [rsp+128h+var_B0], rdi
0x14029c310  lea     r15, [r13+8]
0x14029c314  lea     rax, [rsp+128h+var_98]
0x14029c31c  mov     [rsp+128h+var_E0], rax
0x14029c321  xor     eax, eax
0x14029c323  mov     [rsp+128h+var_E8], eax
0x14029c327  mov     [rsp+128h+var_F0], rax
0x14029c32c  mov     byte ptr [rsp+128h+var_F8], al
0x14029c330  mov     [rsp+128h+var_100], rax
0x14029c335  mov     [rsp+128h+var_108], rax
0x14029c33a  mov     r9d, 0C0h
0x14029c340  mov     r8, r15
0x14029c343  mov     rdx, r13
0x14029c346  mov     rcx, rbx
0x14029c349  call    NtfsLookupInFileRecord
0x14029c34e  mov     rcx, rbx
0x14029c351  test    al, al
0x14029c353  jz      loc_14029CA57
0x14029c359  lea     rax, [rsp+128h+var_98]
0x14029c361  mov     [rsp+128h+var_100], rax
0x14029c366  lea     rax, [rsp+128h+Bcb]
0x14029c36b  mov     [rsp+128h+var_108], rax
0x14029c370  lea     r9, [rsp+128h+BufferLength]
0x14029c375  lea     r8, [rsp+128h+ReparseBuffer]
0x14029c37d  mov     rdx, r13
0x14029c380  call    NtfsMapAttributeValue
0x14029c385  mov     [rsp+128h+var_D5], 1
0x14029c38a  mov     ecx, [rsp+128h+BufferLength]; BufferLength
0x14029c38e  cmp     ecx, 4000h
0x14029c394  jbe     loc_14029C46C
0x14029c39a  mov     ecx, 200h
0x14029c39f  call    NtfsTelemetryGuard
0x14029c3a4  test    al, al
0x14029c3a6  jz      short loc_14029C3BD
0x14029c3a8  xor     r9d, r9d
0x14029c3ab  mov     r8d, [rsp+128h+BufferLength]
0x14029c3b0  mov     edx, 80000005h
0x14029c3b5  mov     rcx, rdi
0x14029c3b8  call    NtfsTelemetryBadReparse
0x14029c3bd  neg     r14b
0x14029c3c0  sbb     r15d, r15d
0x14029c3c3  not     r15d
0x14029c3c6  and     r15d, 0C0000278h
0x14029c3cd  mov     [rsp+128h+var_CC], r15d
0x14029c3d2  mov     al, cs:NtfsStatusDebugFlags
0x14029c3d8  xor     r14d, r14d
0x14029c3db  test    al, al
0x14029c3dd  jz      loc_14029C9CC
0x14029c3e3  test    r15d, r15d
0x14029c3e6  jz      loc_14029C9CC
0x14029c3ec  cmp     r15d, 126h
0x14029c3f3  jz      loc_14029C9CC
0x14029c3f9  lea     eax, [r15-12Ah]
0x14029c400  cmp     eax, 1
0x14029c403  jbe     loc_14029C9CC
0x14029c409  cmp     r15d, 0FFFFFFEDh
0x14029c40d  jnb     loc_14029C9CC
0x14029c413  cmp     r15d, 0C0000016h
0x14029c41a  jz      loc_14029C9CC
0x14029c420  lea     eax, [r15+7FFFFFFBh]
0x14029c427  cmp     eax, 1
0x14029c42a  jbe     loc_14029C9CC
0x14029c430  cmp     r15d, 0C0000011h
0x14029c437  jz      loc_14029C9CC
0x14029c43d  cmp     r15d, 103h
0x14029c444  jz      loc_14029C9CC
0x14029c44a  cmp     r15d, 0C00000D8h
0x14029c451  jz      loc_14029C9CC
0x14029c457  mov     r8d, 0A5C08h
0x14029c45d  mov     edx, r15d
0x14029c460  xor     ecx, ecx
0x14029c462  call    NtfsStatusTraceAndDebugInternal
0x14029c467  jmp     loc_14029C9CC
0x14029c46c  mov     rax, [rsp+128h+ReparseBuffer]
0x14029c474  mov     [rsp+128h+var_B8], rax
0x14029c479  mov     rdx, rax; ReparseBuffer
0x14029c47c  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x14029c483  nop     dword ptr [rax+rax+00h]
0x14029c488  mov     r15d, eax
0x14029c48b  mov     [rsp+128h+var_CC], eax
0x14029c48f  test    eax, eax
0x14029c491  jns     loc_14029C524
0x14029c497  mov     ecx, 200h
0x14029c49c  call    NtfsTelemetryGuard
0x14029c4a1  test    al, al
0x14029c4a3  jz      short loc_14029C4BA
0x14029c4a5  mov     r9, [rsp+128h+var_B8]
0x14029c4aa  mov     r8d, [rsp+128h+BufferLength]
0x14029c4af  mov     edx, r15d
0x14029c4b2  mov     rcx, rdi
0x14029c4b5  call    NtfsTelemetryBadReparse
0x14029c4ba  test    r14b, r14b
0x14029c4bd  jz      short loc_14029C4C7
0x14029c4bf  xor     r14d, r14d
0x14029c4c2  jmp     loc_14029C9C4
0x14029c4c7  mov     al, cs:NtfsStatusDebugFlags
0x14029c4cd  xor     r14d, r14d
0x14029c4d0  test    al, al
0x14029c4d2  jz      loc_14029C9CC
0x14029c4d8  cmp     r15d, 0FFFFFFEDh
0x14029c4dc  jnb     loc_14029C9CC
0x14029c4e2  cmp     r15d, 0C0000016h
0x14029c4e9  jz      loc_14029C9CC
0x14029c4ef  lea     eax, [r15+7FFFFFFBh]
0x14029c4f6  cmp     eax, 1
0x14029c4f9  jbe     loc_14029C9CC
0x14029c4ff  cmp     r15d, 0C0000011h
0x14029c506  jz      loc_14029C9CC
0x14029c50c  cmp     r15d, 0C00000D8h
0x14029c513  jz      loc_14029C9CC
0x14029c519  mov     r8d, 0A5C30h
0x14029c51f  jmp     loc_14029C45D
0x14029c524  mov     [rsp+128h+var_D8], 1
0x14029c529  mov     r15, [rsp+128h+var_B8]
0x14029c52e  test    dword ptr [r13+0B0h], 10000000h
0x14029c539  jz      short loc_14029C553
0x14029c53b  mov     ecx, [r15]
0x14029c53e  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x14029c545  nop     dword ptr [rax+rax+00h]
0x14029c54a  test    al, al
0x14029c54c  mov     [rsp+128h+var_D6], 1
0x14029c551  jnz     short loc_14029C558
0x14029c553  mov     [rsp+128h+var_D6], 0
0x14029c558  movzx   eax, word ptr [r15+4]
0x14029c55d  add     eax, 18h
0x14029c560  cmp     [rsp+128h+BufferLength], eax
0x14029c564  jb      short loc_14029C56C
0x14029c566  lea     r9, [r15+8]
0x14029c56a  jmp     short loc_14029C56F
0x14029c56c  xor     r9d, r9d
0x14029c56f  mov     r8d, [r15]
0x14029c572  mov     rdx, rsi
0x14029c575  mov     rcx, rbx
0x14029c578  call    NtfsLookupOpenReparseEcp
0x14029c57d  lea     rdx, [rsi+0D8h]
0x14029c584  test    r14b, r14b
0x14029c587  jz      short loc_14029C5A0
0x14029c589  mov     rax, [rdx]
0x14029c58c  xor     r14d, r14d
0x14029c58f  test    rax, rax
0x14029c592  jz      short loc_14029C59B
0x14029c594  mov     eax, [rax+14h]
0x14029c597  test    al, 40h
0x14029c599  jnz     short loc_14029C5A3
0x14029c59b  mov     r10b, 1
0x14029c59e  jmp     short loc_14029C5A6
0x14029c5a0  xor     r14d, r14d
0x14029c5a3  mov     r10b, r14b
0x14029c5a6  mov     rax, [rdx]
0x14029c5a9  mov     r9b, [rsp+128h+arg_28]
0x14029c5b1  test    rax, rax
0x14029c5b4  jz      loc_14029C7ED
0x14029c5ba  or      dword ptr [rax+14h], 1
0x14029c5be  test    r9b, r9b
0x14029c5c1  jz      short loc_14029C5ED
0x14029c5c3  mov     r8b, [rsp+128h+var_D6]
0x14029c5c8  test    r8b, r8b
0x14029c5cb  jz      short loc_14029C5DD
0x14029c5cd  mov     rax, [rdx]
0x14029c5d0  mov     ecx, [rax+14h]
0x14029c5d3  test    cl, 8
0x14029c5d6  jz      short loc_14029C5E8
0x14029c5d8  test    r8b, r8b
0x14029c5db  jnz     short loc_14029C5ED
0x14029c5dd  mov     rax, [rdx]
0x14029c5e0  mov     ecx, [rax+14h]
0x14029c5e3  test    cl, 20h
0x14029c5e6  jnz     short loc_14029C5ED
0x14029c5e8  mov     [rsp+128h+var_D8], r14b
0x14029c5ed  lea     rdx, [rsi+0D8h]
0x14029c5f4  mov     al, [rsp+128h+var_D8]
0x14029c5f8  test    al, al
0x14029c5fa  jz      loc_14029C965
0x14029c600  test    r10b, r10b
0x14029c603  jnz     loc_14029C965
0x14029c609  mov     al, cs:NtfsStatusDebugFlags
0x14029c60f  mov     r15d, 104h
0x14029c615  test    al, al
0x14029c617  jz      short loc_14029C629
0x14029c619  mov     r8d, 0A5C6Eh
0x14029c61f  mov     edx, r15d
0x14029c622  xor     ecx, ecx
0x14029c624  call    NtfsStatusTraceAndDebugInternal
0x14029c629  mov     [rsp+128h+var_CC], r15d
0x14029c62e  mov     r14, [rsp+128h+Irp]
0x14029c636  mov     rax, [r14+0B8h]
0x14029c63d  test    byte ptr [rax+2], 4
0x14029c641  jz      short loc_14029C653
0x14029c643  movzx   ecx, word ptr [rsi+44h]
0x14029c647  sub     cx, [rsi+10h]
0x14029c64b  add     [rsp+128h+arg_20], cx
0x14029c653  xor     edx, edx
0x14029c655  cmp     [rsp+128h+arg_20], dx
0x14029c65d  jnz     short loc_14029C6A5
0x14029c65f  mov     rax, [rsp+128h+var_B8]
0x14029c664  cmp     dword ptr [rax], 0A0000003h
0x14029c66a  jnz     short loc_14029C6A5
0x14029c66c  mov     rax, [rsi+0B0h]
0x14029c673  mov     rcx, [rax+8]
0x14029c677  mov     rax, [rcx+8]
0x14029c67b  mov     byte ptr [rsp+128h+var_E8], dl
0x14029c67f  mov     byte ptr [rsp+128h+var_F0], dl
0x14029c683  mov     byte ptr [rsp+128h+var_F8], 1
0x14029c688  mov     eax, [rax+18h]
0x14029c68b  mov     dword ptr [rsp+128h+var_100], eax
0x14029c68f  mov     [rsp+128h+var_108], r14
0x14029c694  xor     r9d, r9d
0x14029c697  mov     r8, rdi
0x14029c69a  mov     rdx, rsi
0x14029c69d  mov     rcx, rbx
0x14029c6a0  call    NtfsAccessCheck
0x14029c6a5  call    Feature_JunctionRedirectionTrust__private_ReportDeviceUsage
0x14029c6aa  mov     rax, [rsp+128h+var_B8]
0x14029c6af  mov     eax, [rax]
0x14029c6b1  cmp     eax, 0A0000003h
0x14029c6b6  jz      short loc_14029C6C3
0x14029c6b8  cmp     eax, 0A000000Ch
0x14029c6bd  jnz     loc_14029C825
0x14029c6c3  mov     eax, [rdi+4]
0x14029c6c6  test    al, 8
0x14029c6c8  jnz     short loc_14029C6E6
0x14029c6ca  xor     eax, eax
0x14029c6cc  mov     [rsp+128h+var_100], rax; __int64
0x14029c6d1  mov     [rsp+128h+var_108], rax; __int64
0x14029c6d6  mov     r9, rdi
0x14029c6d9  xor     r8d, r8d
0x14029c6dc  xor     edx, edx
0x14029c6de  mov     rcx, rbx; int
0x14029c6e1  call    NtfsUpdateFcbInfoFromDisk
0x14029c6e6  call    Feature_RedirectionGuardNonFixedDrive__private_IsEnabledPreCheck
0x14029c6eb  call    Feature_RedirectionGuardForSMB__private_ReportDeviceUsage
0x14029c6f0  xor     ebx, ebx
0x14029c6f2  mov     [rsp+128h+ExtraCreateParameter], rbx
0x14029c6fa  lea     rdx, [rsp+128h+ExtraCreateParameter]; ExtraCreateParameter
0x14029c702  mov     rcx, r14; Irp
0x14029c705  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14029c70c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
