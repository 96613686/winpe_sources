# NtfsGetReparsePointValue

- ea: `0x14029c1b4`
- end: `0x14029ca9b`
- name: `NtfsGetReparsePointValue`
- size: `2279`
- prototype: `__int64 __fastcall(__int64, __int64, IRP *, __int64, __int16, char)`
- caller_count: `3`
- callee_count: `25`
- tags: `reparse_path, authz_impersonation, installer_update`

## callers

- `0x1401a2cb0`
- `0x140219550`
- `0x14029cab0`

## callees

- `0x140007ea0`
- `0x14000c290`
- `0x14000c450`
- `0x140012e70`
- `0x140021e60`
- `0x140030450`
- `0x140039e58`
- `0x1400410a8`
- `0x140044490`
- `0x1400593c0`
- `0x1400596c0`
- `0x1401250b0`
- `0x140125f70`
- `0x140148f30`
- `0x1401620c0`
- `0x140166514`
- `0x14017f870`
- `0x1401841d0`
- `0x140185c00`
- `0x14019a718`
- `0x1401e0660`
- `0x140207b30`
- `0x1402290bc`
- `0x14029c1b4`
- `0x14029f040`

## import_xrefs

- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14029c6b5`
- `ntoskrnl!IoGetIrpExtraCreateParameter` at `0x14029c6b5`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14029c4ee`
- `ntoskrnl!FsRtlIsNonEmptyDirectoryReparsePointAllowed` at `0x14029c4ee`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x14029c42c`
- `ntoskrnl!FsRtlValidateReparsePointBuffer` at `0x14029c42c`
- `ntoskrnl!IoCheckRedirectionTrustLevel3` at `0x14029c721`
- `ntoskrnl!IoCheckRedirectionTrustLevel3` at `0x14029c721`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029c990`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c0324`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14029c990`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402c0324`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14029c8b1`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14029c8b1`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029c7e4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029c938`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029c7e4`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14029c938`
- `ntoskrnl!CcUnpinData` at `0x14029c9bf`
- `ntoskrnl!CcUnpinData` at `0x1402c0357`
- `ntoskrnl!CcUnpinData` at `0x14029c9bf`
- `ntoskrnl!CcUnpinData` at `0x1402c0357`

## pseudocode

```c
__int64 __fastcall NtfsGetReparsePointValue(__int64 a1, __int64 a2, IRP *a3, __int64 a4, __int16 a5, char a6)
{
  __int64 v7; // rsi
  __int64 v8; // rbx
  char v9; // r14
  __int64 v10; // rcx
  _DWORD *v11; // r13
  __int64 v12; // r9
  __int64 AuxiliaryBuffer; // rcx
  unsigned int v14; // r15d
  unsigned int v15; // r8d
  PREPARSE_DATA_BUFFER v16; // r15
  union _REPARSE_DATA_BUFFER::$EDE85F431271D6DB35F60DFE09C35EC8 *p_SymbolicLinkReparseBuffer; // r9
  __int64 v18; // rdx
  bool v19; // r10
  char v20; // al
  IRP *v21; // r14
  __int64 v22; // r14
  BOOL v23; // esi
  __int64 v24; // rbx
  unsigned int v25; // edi
  __int64 v26; // rdx
  signed int v27; // eax
  int v28; // edi
  __int64 v29; // rbx
  CHAR *v30; // rax
  unsigned int *v31; // rdi
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  _QWORD *v34; // rdi
  __int16 *Scb; // rax
  CHAR *PoolWithTag; // rax
  char v38; // [rsp+50h] [rbp-D8h]
  char v39; // [rsp+51h] [rbp-D7h]
  char v40; // [rsp+52h] [rbp-D6h]
  ULONG BufferLength; // [rsp+58h] [rbp-D0h] BYREF
  int v42; // [rsp+5Ch] [rbp-CCh]
  _QWORD *v43; // [rsp+60h] [rbp-C8h]
  PVOID Bcb; // [rsp+68h] [rbp-C0h] BYREF
  PREPARSE_DATA_BUFFER v45; // [rsp+70h] [rbp-B8h]
  _DWORD *v46; // [rsp+78h] [rbp-B0h]
  PREPARSE_DATA_BUFFER ReparseBuffer; // [rsp+80h] [rbp-A8h] BYREF
  struct _ECP_LIST *ExtraCreateParameter; // [rsp+88h] [rbp-A0h] BYREF
  _QWORD v49[19]; // [rsp+90h] [rbp-98h] BYREF

  v7 = a2;
  v8 = a1;
  v39 = 0;
  if ( !a6 || (v9 = 1, (*(_DWORD *)(*(_QWORD *)(a2 + 176) + 16LL) & 0x200000) == 0) )
    v9 = 0;
  memset(v49, 0, 0x58u);
  ReparseBuffer = 0;
  BufferLength = 0;
  v46 = 0;
  Bcb = 0;
  v43 = 0;
  if ( !TxfUseCurrentFileInfo(v8, a4, 1, *(_QWORD *)(v7 + 184)) )
  {
    v10 = *(_QWORD *)(a4 + 328);
    if ( (*(_DWORD *)(v10 + 4) & 0x40000) != 0 )
    {
      v11 = *(_DWORD **)(*(_QWORD *)(v10 + 48) + 8LL);
      v46 = v11;
      NtfsAcquireSharedFcb(v8, (__int64)v11, 0, 1);
      v39 = 1;
      if ( (v11[44] & 0x400) != 0 )
        goto LABEL_9;
      NtfsReleaseFcbEx(v8, (__int64)v11, 0);
      v39 = 0;
    }
  }
  v11 = (_DWORD *)a4;
  v46 = (_DWORD *)a4;
LABEL_9:
  if ( !NtfsLookupInFileRecord(v8, (__int64)v11, v11 + 2, 192, 0, 0, 0, 0, 0, (__int64)v49) )
  {
    NtfsAttachCorruption_BadOrOrphanFRS(v8, 2, 678868, v12, v11 + 2, (__int64)v11, 0);
    NtfsAttachRepairInfoPriv(v8, 256, 0, (struct _LIST_ENTRY *)0x6B000A5BD4LL);
    if ( NtfsStatusDebugFlags )
      NtfsStatusTraceAndDebugInternal(v8, 0xC0000102, 0xA5BD4u);
    NtfsRaiseStatusInternal(v8, -1073741566, (_DWORD)v11 + 8, (int)v11, 678868);
  }
  NtfsMapAttributeValue(v8, (__int64)v11, (PVOID *)&ReparseBuffer, &BufferLength, &Bcb, (union _LARGE_INTEGER)v49);
  if ( BufferLength > 0x4000 )
  {
    if ( NtfsTelemetryGuard(0x200u) )
      NtfsTelemetryBadReparse(a4, 2147483653LL, BufferLength, 0);
    v14 = v9 == 0 ? 0xC0000278 : 0;
    v42 = v14;
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
    v34 = v43;
    goto LABEL_102;
  }
  v45 = ReparseBuffer;
  v14 = FsRtlValidateReparsePointBuffer(BufferLength, ReparseBuffer);
  v42 = v14;
  if ( (v14 & 0x80000000) != 0 )
  {
    if ( NtfsTelemetryGuard(0x200u) )
      NtfsTelemetryBadReparse(a4, v14, BufferLength, v45);
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
    v42 = 0;
    v14 = 0;
    goto LABEL_101;
  }
  v38 = 1;
  v16 = v45;
  if ( (v11[44] & 0x10000000) == 0
    || (v40 = 1, !(unsigned __int8)FsRtlIsNonEmptyDirectoryReparsePointAllowed(v45->ReparseTag)) )
  {
    v40 = 0;
  }
  if ( BufferLength < (unsigned int)v16->ReparseDataLength + 24 )
    p_SymbolicLinkReparseBuffer = 0;
  else
    p_SymbolicLinkReparseBuffer = (union _REPARSE_DATA_BUFFER::$EDE85F431271D6DB35F60DFE09C35EC8 *)&v16->SymbolicLinkReparseBuffer;
  NtfsLookupOpenReparseEcp(v8, v7, v16->ReparseTag, p_SymbolicLinkReparseBuffer);
  v18 = v7 + 216;
  v19 = v9 && (!*(_QWORD *)v18 || (*(_DWORD *)(*(_QWORD *)v18 + 20LL) & 0x40) == 0);
  if ( *(_QWORD *)v18 )
  {
    *(_DWORD *)(*(_QWORD *)v18 + 20LL) |= 1u;
    if ( a6 )
    {
      if ( v40 )
      {
        AuxiliaryBuffer = *(unsigned int *)(*(_QWORD *)v18 + 20LL);
        if ( (AuxiliaryBuffer & 8) != 0 )
          goto LABEL_53;
        goto LABEL_52;
      }
      AuxiliaryBuffer = *(unsigned int *)(*(_QWORD *)v18 + 20LL);
      if ( (AuxiliaryBuffer & 0x20) == 0 )
LABEL_52:
        v38 = 0;
    }
LABEL_53:
    v18 = v7 + 216;
    goto LABEL_54;
  }
  if ( a6 && v40 )
  {
    v20 = 0;
    goto LABEL_55;
  }
LABEL_54:
  v20 = v38;
LABEL_55:
  if ( !v20 || v19 )
  {
    if ( *(_QWORD *)v18 && (*(_DWORD *)(*(_QWORD *)v18 + 20LL) & 0x80u) != 0 && a6 )
    {
      PoolWithTag = (CHAR *)ExAllocatePoolWithTag((POOL_TYPE)528, BufferLength, 0x4346744Eu);
      a3->Tail.Overlay.AuxiliaryBuffer = PoolWithTag;
      memmove(PoolWithTag, ReparseBuffer, BufferLength);
      AuxiliaryBuffer = (__int64)a3->Tail.Overlay.AuxiliaryBuffer;
      *(_WORD *)(AuxiliaryBuffer + 6) = 0;
    }
    goto LABEL_100;
  }
  v14 = 260;
  if ( NtfsStatusDebugFlags )
    NtfsStatusTraceAndDebugInternal(0, 0x104u, 0xA5C6Eu);
  v42 = 260;
  v21 = a3;
  if ( (a3->Tail.Overlay.CurrentStackLocation->Flags & 4) != 0 )
    a5 += *(_WORD *)(v7 + 68) - *(_WORD *)(v7 + 16);
  if ( !a5 && v45->ReparseTag == -1610612733 )
    NtfsAccessCheck(
      v8,
      v7,
      (_QWORD *)a4,
      0,
      (__int64)a3,
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v7 + 176) + 8LL) + 8LL) + 24LL),
      1,
      0,
      0);
  Feature_JunctionRedirectionTrust__private_ReportDeviceUsage();
  if ( v45->ReparseTag == -1610612733 || v45->ReparseTag == -1610612724 )
  {
    if ( (*(_DWORD *)(a4 + 4) & 8) == 0 )
      NtfsUpdateFcbInfoFromDisk(v8, 0, 0, a4, 0, 0);
    Feature_RedirectionGuardNonFixedDrive__private_IsEnabledPreCheck();
    Feature_RedirectionGuardForSMB__private_ReportDeviceUsage();
    ExtraCreateParameter = 0;
    IoGetIrpExtraCreateParameter(a3, &ExtraCreateParameter);
    v22 = v7 + 16;
    if ( (*(_DWORD *)(v7 + 156) & 0x40) != 0 )
      v22 = 0;
    v23 = v45->ReparseTag != -1610612733;
    v24 = *(_QWORD *)(a2 + 32);
    v25 = *(unsigned __int8 *)(a4 + 37);
    LOBYTE(v26) = NtfsEffectiveMode((__int64)a3);
    v27 = IoCheckRedirectionTrustLevel3((unsigned int)(v23 + 1), v26, 0, v25, v22, v24, ExtraCreateParameter);
    v28 = v27;
    if ( v27 < 0 )
    {
      if ( !NtfsStatusDebugFlags
        || (unsigned int)v27 >= 0xFFFFFFED
        || v27 == -1073741802
        || (unsigned int)(v27 + 2147483643) <= 1
        || v27 == -1073741807
        || v27 == -1073741608 )
      {
        v29 = a1;
      }
      else
      {
        v29 = a1;
        NtfsStatusTraceAndDebugInternal(a1, v27, 0xA5D2Eu);
      }
      NtfsRaiseStatusInternal(v29, v28, 0, 0, 679214);
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
  AuxiliaryBuffer = *(_QWORD *)(v7 + 216);
  if ( AuxiliaryBuffer && *(int *)(AuxiliaryBuffer + 20) < 0 )
    *(_WORD *)(AuxiliaryBuffer + 42) = a5;
  v21->IoStatus.Information = *v31;
  if ( v11[67] )
  {
    NtfsMoveFcbToDelayCloseTail((__int64)v11);
    goto LABEL_101;
  }
  if ( v11[5] )
    goto LABEL_101;
  v34 = ExAllocateFromLookasideListEx(&NtfsCloseEntryLookasideList);
  v43 = v34;
  if ( v34 )
  {
    Scb = NtfsCreateScb(v8, (__int64)v11, 160, &NtfsFileNameIndex, 0, 0, 0);
    NtfsAddScbToFspClose(v8, Scb, 1, 1, v34);
    v34 = 0;
    v43 = 0;
  }
LABEL_102:
  if ( v34 )
    ExFreeToLookasideListEx(&NtfsCloseEntryLookasideList, v34);
  if ( v49[2] )
  {
    AuxiliaryBuffer = (__int64)Bcb;
    if ( !Bcb )
      goto LABEL_109;
    CcUnpinData(Bcb);
  }
  else
  {
    v49[2] = Bcb;
  }
  Bcb = 0;
LABEL_109:
  NtfsCleanupAttributeContext(AuxiliaryBuffer, v49);
  if ( v39 )
    NtfsReleaseFcbEx(v8, (__int64)v11, 0);
  return v14;
}

```

## disassembly

```asm
0x14029c1b4  mov     rax, rsp
0x14029c1b7  mov     [rax+20h], r9
0x14029c1bb  mov     [rax+18h], r8
0x14029c1bf  mov     [rax+10h], rdx
0x14029c1c3  mov     [rax+8], rcx
0x14029c1c7  push    rbx
0x14029c1c8  push    rsi
0x14029c1c9  push    rdi
0x14029c1ca  push    r13
0x14029c1cc  push    r14
0x14029c1ce  push    r15
0x14029c1d0  sub     rsp, 0F8h
0x14029c1d7  mov     rdi, r9
0x14029c1da  mov     rsi, rdx
0x14029c1dd  mov     rbx, rcx
0x14029c1e0  xor     r15d, r15d
0x14029c1e3  mov     [rsp+128h+var_D7], r15b
0x14029c1e8  mov     [rsp+128h+var_D4], r15b
0x14029c1ed  mov     [rsp+128h+var_D5], r15b
0x14029c1f2  cmp     [rsp+128h+arg_28], r15b
0x14029c1fa  jz      short loc_14029C20F
0x14029c1fc  mov     rax, [rdx+0B0h]
0x14029c203  test    dword ptr [rax+10h], 200000h
0x14029c20a  mov     r14b, 1
0x14029c20d  jnz     short loc_14029C212
0x14029c20f  mov     r14b, r15b
0x14029c212  xor     edx, edx; Val
0x14029c214  lea     r8d, [rdx+58h]; Size
0x14029c218  lea     rcx, [rsp+128h+var_98]; void *
0x14029c220  call    memset
0x14029c225  mov     [rsp+128h+ReparseBuffer], r15
0x14029c22d  mov     [rsp+128h+BufferLength], r15d
0x14029c232  mov     [rsp+128h+var_B0], r15
0x14029c237  mov     [rsp+128h+Bcb], r15
0x14029c23c  mov     [rsp+128h+var_C8], r15
0x14029c241  mov     [rsp+128h+var_D4], 1
0x14029c246  mov     r9, [rsi+0B8h]
0x14029c24d  mov     r8d, 1
0x14029c253  mov     rdx, rdi
0x14029c256  mov     rcx, rbx
0x14029c259  call    TxfUseCurrentFileInfo
0x14029c25e  test    eax, eax
0x14029c260  jnz     short loc_14029C2B8
0x14029c262  mov     rcx, [rdi+148h]
0x14029c269  test    dword ptr [rcx+4], 40000h
0x14029c270  jz      short loc_14029C2B8
0x14029c272  mov     rax, [rcx+30h]
0x14029c276  mov     r13, [rax+8]
0x14029c27a  mov     [rsp+128h+var_B0], r13
0x14029c27f  mov     r9d, 1
0x14029c285  xor     r8d, r8d
0x14029c288  mov     rdx, r13
0x14029c28b  mov     rcx, rbx
0x14029c28e  call    NtfsAcquireSharedFcb
0x14029c293  mov     [rsp+128h+var_D7], 1
0x14029c298  test    dword ptr [r13+0B0h], 400h
0x14029c2a3  jnz     short loc_14029C2C0
0x14029c2a5  xor     r8d, r8d
0x14029c2a8  mov     rdx, r13
0x14029c2ab  mov     rcx, rbx
0x14029c2ae  call    NtfsReleaseFcbEx
0x14029c2b3  mov     [rsp+128h+var_D7], r15b
0x14029c2b8  mov     r13, rdi
0x14029c2bb  mov     [rsp+128h+var_B0], rdi
0x14029c2c0  lea     r15, [r13+8]
0x14029c2c4  lea     rax, [rsp+128h+var_98]
0x14029c2cc  mov     [rsp+128h+var_E0], rax
0x14029c2d1  xor     eax, eax
0x14029c2d3  mov     [rsp+128h+var_E8], eax
0x14029c2d7  mov     [rsp+128h+var_F0], rax
0x14029c2dc  mov     byte ptr [rsp+128h+var_F8], al
0x14029c2e0  mov     [rsp+128h+var_100], rax
0x14029c2e5  mov     [rsp+128h+var_108], rax
0x14029c2ea  mov     r9d, 0C0h
0x14029c2f0  mov     r8, r15
0x14029c2f3  mov     rdx, r13
0x14029c2f6  mov     rcx, rbx
0x14029c2f9  call    NtfsLookupInFileRecord
0x14029c2fe  mov     rcx, rbx
0x14029c301  test    al, al
0x14029c303  jz      loc_14029CA07
0x14029c309  lea     rax, [rsp+128h+var_98]
0x14029c311  mov     [rsp+128h+var_100], rax
0x14029c316  lea     rax, [rsp+128h+Bcb]
0x14029c31b  mov     [rsp+128h+var_108], rax
0x14029c320  lea     r9, [rsp+128h+BufferLength]
0x14029c325  lea     r8, [rsp+128h+ReparseBuffer]
0x14029c32d  mov     rdx, r13
0x14029c330  call    NtfsMapAttributeValue
0x14029c335  mov     [rsp+128h+var_D5], 1
0x14029c33a  mov     ecx, [rsp+128h+BufferLength]; BufferLength
0x14029c33e  cmp     ecx, 4000h
0x14029c344  jbe     loc_14029C41C
0x14029c34a  mov     ecx, 200h
0x14029c34f  call    NtfsTelemetryGuard
0x14029c354  test    al, al
0x14029c356  jz      short loc_14029C36D
0x14029c358  xor     r9d, r9d
0x14029c35b  mov     r8d, [rsp+128h+BufferLength]
0x14029c360  mov     edx, 80000005h
0x14029c365  mov     rcx, rdi
0x14029c368  call    NtfsTelemetryBadReparse
0x14029c36d  neg     r14b
0x14029c370  sbb     r15d, r15d
0x14029c373  not     r15d
0x14029c376  and     r15d, 0C0000278h
0x14029c37d  mov     [rsp+128h+var_CC], r15d
0x14029c382  mov     al, cs:NtfsStatusDebugFlags
0x14029c388  xor     r14d, r14d
0x14029c38b  test    al, al
0x14029c38d  jz      loc_14029C97C
0x14029c393  test    r15d, r15d
0x14029c396  jz      loc_14029C97C
0x14029c39c  cmp     r15d, 126h
0x14029c3a3  jz      loc_14029C97C
0x14029c3a9  lea     eax, [r15-12Ah]
0x14029c3b0  cmp     eax, 1
0x14029c3b3  jbe     loc_14029C97C
0x14029c3b9  cmp     r15d, 0FFFFFFEDh
0x14029c3bd  jnb     loc_14029C97C
0x14029c3c3  cmp     r15d, 0C0000016h
0x14029c3ca  jz      loc_14029C97C
0x14029c3d0  lea     eax, [r15+7FFFFFFBh]
0x14029c3d7  cmp     eax, 1
0x14029c3da  jbe     loc_14029C97C
0x14029c3e0  cmp     r15d, 0C0000011h
0x14029c3e7  jz      loc_14029C97C
0x14029c3ed  cmp     r15d, 103h
0x14029c3f4  jz      loc_14029C97C
0x14029c3fa  cmp     r15d, 0C00000D8h
0x14029c401  jz      loc_14029C97C
0x14029c407  mov     r8d, 0A5C08h
0x14029c40d  mov     edx, r15d
0x14029c410  xor     ecx, ecx
0x14029c412  call    NtfsStatusTraceAndDebugInternal
0x14029c417  jmp     loc_14029C97C
0x14029c41c  mov     rax, [rsp+128h+ReparseBuffer]
0x14029c424  mov     [rsp+128h+var_B8], rax
0x14029c429  mov     rdx, rax; ReparseBuffer
0x14029c42c  call    cs:__imp_FsRtlValidateReparsePointBuffer
0x14029c433  nop     dword ptr [rax+rax+00h]
0x14029c438  mov     r15d, eax
0x14029c43b  mov     [rsp+128h+var_CC], eax
0x14029c43f  test    eax, eax
0x14029c441  jns     loc_14029C4D4
0x14029c447  mov     ecx, 200h
0x14029c44c  call    NtfsTelemetryGuard
0x14029c451  test    al, al
0x14029c453  jz      short loc_14029C46A
0x14029c455  mov     r9, [rsp+128h+var_B8]
0x14029c45a  mov     r8d, [rsp+128h+BufferLength]
0x14029c45f  mov     edx, r15d
0x14029c462  mov     rcx, rdi
0x14029c465  call    NtfsTelemetryBadReparse
0x14029c46a  test    r14b, r14b
0x14029c46d  jz      short loc_14029C477
0x14029c46f  xor     r14d, r14d
0x14029c472  jmp     loc_14029C974
0x14029c477  mov     al, cs:NtfsStatusDebugFlags
0x14029c47d  xor     r14d, r14d
0x14029c480  test    al, al
0x14029c482  jz      loc_14029C97C
0x14029c488  cmp     r15d, 0FFFFFFEDh
0x14029c48c  jnb     loc_14029C97C
0x14029c492  cmp     r15d, 0C0000016h
0x14029c499  jz      loc_14029C97C
0x14029c49f  lea     eax, [r15+7FFFFFFBh]
0x14029c4a6  cmp     eax, 1
0x14029c4a9  jbe     loc_14029C97C
0x14029c4af  cmp     r15d, 0C0000011h
0x14029c4b6  jz      loc_14029C97C
0x14029c4bc  cmp     r15d, 0C00000D8h
0x14029c4c3  jz      loc_14029C97C
0x14029c4c9  mov     r8d, 0A5C30h
0x14029c4cf  jmp     loc_14029C40D
0x14029c4d4  mov     [rsp+128h+var_D8], 1
0x14029c4d9  mov     r15, [rsp+128h+var_B8]
0x14029c4de  test    dword ptr [r13+0B0h], 10000000h
0x14029c4e9  jz      short loc_14029C503
0x14029c4eb  mov     ecx, [r15]
0x14029c4ee  call    cs:__imp_FsRtlIsNonEmptyDirectoryReparsePointAllowed
0x14029c4f5  nop     dword ptr [rax+rax+00h]
0x14029c4fa  test    al, al
0x14029c4fc  mov     [rsp+128h+var_D6], 1
0x14029c501  jnz     short loc_14029C508
0x14029c503  mov     [rsp+128h+var_D6], 0
0x14029c508  movzx   eax, word ptr [r15+4]
0x14029c50d  add     eax, 18h
0x14029c510  cmp     [rsp+128h+BufferLength], eax
0x14029c514  jb      short loc_14029C51C
0x14029c516  lea     r9, [r15+8]
0x14029c51a  jmp     short loc_14029C51F
0x14029c51c  xor     r9d, r9d
0x14029c51f  mov     r8d, [r15]
0x14029c522  mov     rdx, rsi
0x14029c525  mov     rcx, rbx
0x14029c528  call    NtfsLookupOpenReparseEcp
0x14029c52d  lea     rdx, [rsi+0D8h]
0x14029c534  test    r14b, r14b
0x14029c537  jz      short loc_14029C550
0x14029c539  mov     rax, [rdx]
0x14029c53c  xor     r14d, r14d
0x14029c53f  test    rax, rax
0x14029c542  jz      short loc_14029C54B
0x14029c544  mov     eax, [rax+14h]
0x14029c547  test    al, 40h
0x14029c549  jnz     short loc_14029C553
0x14029c54b  mov     r10b, 1
0x14029c54e  jmp     short loc_14029C556
0x14029c550  xor     r14d, r14d
0x14029c553  mov     r10b, r14b
0x14029c556  mov     rax, [rdx]
0x14029c559  mov     r9b, [rsp+128h+arg_28]
0x14029c561  test    rax, rax
0x14029c564  jz      loc_14029C79D
0x14029c56a  or      dword ptr [rax+14h], 1
0x14029c56e  test    r9b, r9b
0x14029c571  jz      short loc_14029C59D
0x14029c573  mov     r8b, [rsp+128h+var_D6]
0x14029c578  test    r8b, r8b
0x14029c57b  jz      short loc_14029C58D
0x14029c57d  mov     rax, [rdx]
0x14029c580  mov     ecx, [rax+14h]
0x14029c583  test    cl, 8
0x14029c586  jz      short loc_14029C598
0x14029c588  test    r8b, r8b
0x14029c58b  jnz     short loc_14029C59D
0x14029c58d  mov     rax, [rdx]
0x14029c590  mov     ecx, [rax+14h]
0x14029c593  test    cl, 20h
0x14029c596  jnz     short loc_14029C59D
0x14029c598  mov     [rsp+128h+var_D8], r14b
0x14029c59d  lea     rdx, [rsi+0D8h]
0x14029c5a4  mov     al, [rsp+128h+var_D8]
0x14029c5a8  test    al, al
0x14029c5aa  jz      loc_14029C915
0x14029c5b0  test    r10b, r10b
0x14029c5b3  jnz     loc_14029C915
0x14029c5b9  mov     al, cs:NtfsStatusDebugFlags
0x14029c5bf  mov     r15d, 104h
0x14029c5c5  test    al, al
0x14029c5c7  jz      short loc_14029C5D9
0x14029c5c9  mov     r8d, 0A5C6Eh
0x14029c5cf  mov     edx, r15d
0x14029c5d2  xor     ecx, ecx
0x14029c5d4  call    NtfsStatusTraceAndDebugInternal
0x14029c5d9  mov     [rsp+128h+var_CC], r15d
0x14029c5de  mov     r14, [rsp+128h+Irp]
0x14029c5e6  mov     rax, [r14+0B8h]
0x14029c5ed  test    byte ptr [rax+2], 4
0x14029c5f1  jz      short loc_14029C603
0x14029c5f3  movzx   ecx, word ptr [rsi+44h]
0x14029c5f7  sub     cx, [rsi+10h]
0x14029c5fb  add     [rsp+128h+arg_20], cx
0x14029c603  xor     edx, edx
0x14029c605  cmp     [rsp+128h+arg_20], dx
0x14029c60d  jnz     short loc_14029C655
0x14029c60f  mov     rax, [rsp+128h+var_B8]
0x14029c614  cmp     dword ptr [rax], 0A0000003h
0x14029c61a  jnz     short loc_14029C655
0x14029c61c  mov     rax, [rsi+0B0h]
0x14029c623  mov     rcx, [rax+8]
0x14029c627  mov     rax, [rcx+8]
0x14029c62b  mov     byte ptr [rsp+128h+var_E8], dl
0x14029c62f  mov     byte ptr [rsp+128h+var_F0], dl
0x14029c633  mov     byte ptr [rsp+128h+var_F8], 1
0x14029c638  mov     eax, [rax+18h]
0x14029c63b  mov     dword ptr [rsp+128h+var_100], eax
0x14029c63f  mov     [rsp+128h+var_108], r14
0x14029c644  xor     r9d, r9d
0x14029c647  mov     r8, rdi
0x14029c64a  mov     rdx, rsi
0x14029c64d  mov     rcx, rbx
0x14029c650  call    NtfsAccessCheck
0x14029c655  call    Feature_JunctionRedirectionTrust__private_ReportDeviceUsage
0x14029c65a  mov     rax, [rsp+128h+var_B8]
0x14029c65f  mov     eax, [rax]
0x14029c661  cmp     eax, 0A0000003h
0x14029c666  jz      short loc_14029C673
0x14029c668  cmp     eax, 0A000000Ch
0x14029c66d  jnz     loc_14029C7D5
0x14029c673  mov     eax, [rdi+4]
0x14029c676  test    al, 8
0x14029c678  jnz     short loc_14029C696
0x14029c67a  xor     eax, eax
0x14029c67c  mov     [rsp+128h+var_100], rax; __int64
0x14029c681  mov     [rsp+128h+var_108], rax; __int64
0x14029c686  mov     r9, rdi
0x14029c689  xor     r8d, r8d
0x14029c68c  xor     edx, edx
0x14029c68e  mov     rcx, rbx; int
0x14029c691  call    NtfsUpdateFcbInfoFromDisk
0x14029c696  call    Feature_RedirectionGuardNonFixedDrive__private_IsEnabledPreCheck
0x14029c69b  call    Feature_RedirectionGuardForSMB__private_ReportDeviceUsage
0x14029c6a0  xor     ebx, ebx
0x14029c6a2  mov     [rsp+128h+ExtraCreateParameter], rbx
0x14029c6aa  lea     rdx, [rsp+128h+ExtraCreateParameter]; ExtraCreateParameter
0x14029c6b2  mov     rcx, r14; Irp
0x14029c6b5  call    cs:__imp_IoGetIrpExtraCreateParameter
0x14029c6bc  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
