# FatOpenExistingFcb

- ea: `0x14002adec`
- end: `0x14002b78a`
- name: `FatOpenExistingFcb`
- size: `2462`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _DWORD, _QWORD)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1400268c0`

## callees

- `0x140002ed8`
- `0x1400201f4`
- `0x14002023c`
- `0x1400267dc`
- `0x140026864`
- `0x140028aa8`
- `0x14002adec`
- `0x14002cbe4`
- `0x1400319bc`
- `0x1400364fc`
- `0x14003db44`
- `0x1400465f4`
- `0x1400475e8`
- `0x14004814c`
- `0x140048184`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x14002ae90`
- `ntoskrnl!KeClearEvent` at `0x14002ae90`
- `ntoskrnl!CcFlushCache` at `0x14002b302`
- `ntoskrnl!CcFlushCache` at `0x14002b302`
- `ntoskrnl!CcPurgeCacheSection` at `0x14002b33d`
- `ntoskrnl!CcPurgeCacheSection` at `0x14002b33d`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14002b07c`
- `ntoskrnl!IoSetHardErrorOrVerifyDevice` at `0x14002b07c`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002aedf`
- `ntoskrnl!FsRtlCheckOplockEx` at `0x14002aedf`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005c7d3`
- `ntoskrnl!IoRemoveShareAccess` at `0x14005c7d3`
- `ntoskrnl!FsRtlCheckOplock` at `0x14002af2e`
- `ntoskrnl!FsRtlCheckOplock` at `0x14002b195`
- `ntoskrnl!FsRtlCheckOplock` at `0x14002af2e`
- `ntoskrnl!FsRtlCheckOplock` at `0x14002b195`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14002b1ff`
- `ntoskrnl!FsRtlOplockIsFastIoPossible` at `0x14002b1ff`
- `ntoskrnl!IoCheckShareAccess` at `0x14002b529`
- `ntoskrnl!IoCheckShareAccess` at `0x14002b529`
- `ntoskrnl!FsRtlOplockBreakH2` at `0x14002b133`
- `ntoskrnl!FsRtlOplockBreakH2` at `0x14002b133`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14002b1cc`
- `ntoskrnl!FsRtlOplockFsctrl` at `0x14002b1cc`
- `ntoskrnl!IoUpdateShareAccess` at `0x14002b541`
- `ntoskrnl!IoUpdateShareAccess` at `0x14002b541`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14002aef9`
- `ntoskrnl!FsRtlCurrentBatchOplock` at `0x14002aef9`
- `ntoskrnl!MmFlushImageSection` at `0x14002b27b`
- `ntoskrnl!MmFlushImageSection` at `0x14002b27b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002b315`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14002b315`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002b325`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002b767`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c847`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002b325`
- `ntoskrnl!ExReleaseResourceLite` at `0x14002b767`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005c847`
- `ntoskrnl!CcUnpinData` at `0x14002b498`
- `ntoskrnl!CcUnpinData` at `0x14002b706`
- `ntoskrnl!CcUnpinData` at `0x14005c787`
- `ntoskrnl!CcUnpinData` at `0x14002b498`
- `ntoskrnl!CcUnpinData` at `0x14002b706`
- `ntoskrnl!CcUnpinData` at `0x14005c787`
- `ntoskrnl!KeBugCheckEx` at `0x14002b425`
- `ntoskrnl!KeBugCheckEx` at `0x14002b425`
- `ntoskrnl!ExRaiseStatus` at `0x14002aea4`
- `ntoskrnl!ExRaiseStatus` at `0x14002b09f`
- `ntoskrnl!ExRaiseStatus` at `0x14002b6ad`
- `ntoskrnl!ExRaiseStatus` at `0x14002b6ef`
- `ntoskrnl!ExRaiseStatus` at `0x14002aea4`
- `ntoskrnl!ExRaiseStatus` at `0x14002b09f`
- `ntoskrnl!ExRaiseStatus` at `0x14002b6ad`
- `ntoskrnl!ExRaiseStatus` at `0x14002b6ef`

## pseudocode

```c
int *__fastcall FatOpenExistingFcb(
        NTSTATUS *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        ACCESS_MASK *a7,
        unsigned __int16 a8,
        int a9,
        __int64 a10,
        int a11,
        __int16 a12,
        ULONG_PTR BugCheckParameter2,
        char a14,
        char a15,
        char a16,
        char a17,
        _BYTE *a18)
{
  __int64 v21; // rbx
  char v22; // si
  _DWORD *v23; // r12
  NTSTATUS v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  NTSTATUS v27; // eax
  ULONG_PTR v28; // r12
  ACCESS_MASK v29; // eax
  __int64 v30; // rcx
  char v31; // al
  ACCESS_MASK *v32; // r15
  NTSTATUS v33; // eax
  __int64 v34; // rdx
  int v35; // eax
  char v36; // al
  PVOID v37; // rcx
  NTSTATUS v38; // r15d
  int v39; // eax
  __int64 v40; // rdx
  ACCESS_MASK *v41; // r15
  __int64 v42; // r8
  __int64 v43; // r15
  __int64 v44; // rcx
  int v45; // eax
  NTSTATUS Callback; // eax
  NTSTATUS EncryptOnCloseProcessing; // eax
  PVOID v48; // rcx
  unsigned __int16 *v51; // [rsp+38h] [rbp-A0h]
  char v52; // [rsp+60h] [rbp-78h]
  int v53; // [rsp+64h] [rbp-74h]
  PVOID Bcb; // [rsp+68h] [rbp-70h] BYREF
  int v55; // [rsp+70h] [rbp-68h]
  int v56; // [rsp+74h] [rbp-64h]
  unsigned int v57; // [rsp+78h] [rbp-60h]
  __int64 Ccb; // [rsp+80h] [rbp-58h]
  __int64 v59; // [rsp+88h] [rbp-50h] BYREF
  char v60[72]; // [rsp+90h] [rbp-48h] BYREF

  *(_OWORD *)a1 = 0;
  Bcb = 0;
  v59 = 0;
  v53 = 0;
  Ccb = 0;
  v52 = 0;
  v56 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 12LL) & 0x40000;
  v21 = a6;
  FatAcquireExclusiveFcb(a2, a6);
  v22 = 1;
  v23 = (_DWORD *)a5;
  if ( (*(_DWORD *)(a5 + 200) & 0x400000) != 0 && (*(_DWORD *)(v21 + 192) & 0x100000) != 0 )
  {
    *(_DWORD *)(a2 + 68) |= 0x80000u;
    KeClearEvent(&Event);
    *(_DWORD *)(a2 + 72) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  *a18 = 0;
  v24 = FsRtlCheckOplockEx((POPLOCK)(v21 + 88), *(PIRP *)(a2 + 40), 2u, 0, 0, 0);
  *a1 = v24;
  if ( v24 )
    goto LABEL_84;
  if ( FsRtlCurrentBatchOplock((POPLOCK)(v21 + 88)) )
  {
    *((_QWORD *)a1 + 1) = 9;
    v27 = FsRtlCheckOplock((POPLOCK)(v21 + 88), *(PIRP *)(a2 + 40), (PVOID)a2, FatOplockComplete, FatPrePostIrp);
    *a1 = v27;
    if ( v27 == 259 )
    {
      *a18 = 1;
      goto LABEL_84;
    }
  }
  v28 = (unsigned int)BugCheckParameter2;
  if ( (_DWORD)BugCheckParameter2 == 2 )
  {
    *a1 = -1073741771;
LABEL_10:
    v23 = (_DWORD *)a5;
    goto LABEL_84;
  }
  if ( (_DWORD)BugCheckParameter2 )
  {
    if ( (unsigned int)(BugCheckParameter2 - 4) > 1 )
      goto LABEL_16;
    v25 = 274;
  }
  else
  {
    v25 = 0x10000;
  }
  v29 = *a7;
  v57 = v25 & ~*a7;
  v26 = v57;
  *a7 = v25 | v29;
  v53 = v26;
LABEL_16:
  LOBYTE(v25) = *(_BYTE *)(v21 + 546);
  if ( !(unsigned __int8)FatCheckFileAccess(v26, v25, a7) )
  {
    *a1 = -1073741790;
    goto LABEL_10;
  }
  if ( (*(_DWORD *)(a5 + 200) & 0x400000) != 0 )
  {
    if ( v56 )
    {
      v30 = *a7;
      if ( (v30 & 0x27) != 0 && (*(_DWORD *)(v21 + 192) & 0x60000) == 0 )
        goto LABEL_22;
    }
  }
  if ( a15 && (*(_BYTE *)(v21 + 546) & 1) != 0 )
  {
    *a1 = -1073741535;
    goto LABEL_23;
  }
  if ( (v28 & 0xFFFFFFFA) == 0 && (_DWORD)v28 != 1 )
  {
    v31 = *(_BYTE *)(v21 + 546);
    if ( (v31 & 2) != 0 && (a12 & 2) == 0 || (v31 & 4) != 0 && (a12 & 4) == 0 )
    {
LABEL_22:
      *a1 = -1073741790;
LABEL_23:
      v23 = (_DWORD *)a5;
      goto LABEL_84;
    }
    if ( (*(_DWORD *)(a5 + 200) & 0x4000) != 0 )
    {
      IoSetHardErrorOrVerifyDevice(*(PIRP *)(a2 + 40), *(PDEVICE_OBJECT *)(*(_QWORD *)(a5 + 192) + 16LL));
      *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a5 + 192) + 16LL) + 48LL) |= 2u;
      *(_DWORD *)(a2 + 72) = -1073741662;
      ExRaiseStatus(-1073741662);
    }
  }
  v32 = a7;
  v33 = FatCheckShareAccess(v30, a4, v21, a7, a8);
  *a1 = v33;
  if ( v33 < 0 )
  {
    if ( v33 != -1073741757 || (*(_DWORD *)(a3 + 16) & 0x100) != 0 )
      goto LABEL_10;
    v51 = &a8;
    v35 = FsRtlOplockBreakH2(v21 + 88, *(_QWORD *)(a2 + 40), 128, a2, FatOplockComplete, FatPrePostIrp, v32);
    if ( v35 != 259 )
    {
      if ( v35 < 0 )
        *a1 = v35;
      goto LABEL_10;
    }
    *a1 = 259;
    goto LABEL_40;
  }
  if ( *(_DWORD *)(v21 + 228) )
  {
    v33 = FsRtlCheckOplock((POPLOCK)(v21 + 88), *(PIRP *)(a2 + 40), (PVOID)a2, FatOplockComplete, FatPrePostIrp);
    *a1 = v33;
  }
  if ( v33 == 259 )
  {
LABEL_40:
    *a18 = 1;
    goto LABEL_10;
  }
  if ( a16 )
  {
    if ( v33 )
      goto LABEL_50;
    v33 = FsRtlOplockFsctrl((POPLOCK)(v21 + 88), *(PIRP *)(a2 + 40), *(_DWORD *)(v21 + 228) + 1);
    *a1 = v33;
  }
  if ( v33 )
  {
LABEL_50:
    if ( v33 != 264 )
      goto LABEL_10;
  }
  if ( *(_DWORD *)(v21 + 196) == 1 && *(_WORD *)v21 == 1282 && FsRtlOplockIsFastIoPossible((POPLOCK)(v21 + 88)) )
  {
    if ( *(_BYTE *)(v21 + 336)
      || *(_DWORD *)(*(_QWORD *)(v21 + 120) + 24LL)
      || (*(_DWORD *)(*(_QWORD *)(v21 + 184) + 200LL) & 0x4000) != 0
      || (*(_DWORD *)(v21 + 192) & 0x8000) != 0 )
    {
      v36 = 2;
    }
    else
    {
      v36 = 1;
    }
  }
  else
  {
    v36 = 0;
  }
  *(_BYTE *)(v21 + 5) = v36;
  v37 = (PVOID)*a7;
  if ( ((unsigned __int8)v37 & 2) != 0 || a15 )
  {
    ++*(_DWORD *)(v21 + 232);
    v52 = 1;
    if ( !MmFlushImageSection(*(PSECTION_OBJECT_POINTERS *)(v21 + 120), MmFlushForWrite) )
    {
      *a1 = a15 != 0 ? -1073741535 : -1073741757;
      goto LABEL_10;
    }
  }
  if ( (*(_DWORD *)(a4 + 80) & 8) != 0
    && *(_DWORD *)(v21 + 228) == *(_DWORD *)(v21 + 236)
    && **(_QWORD **)(v21 + 120)
    && (*(_DWORD *)(v21 + 192) & 4) == 0 )
  {
    _InterlockedOr((volatile signed __int32 *)(*(_QWORD *)(v21 + 184) + 200LL), 0x200u);
    CcFlushCache(*(PSECTION_OBJECT_POINTERS *)(v21 + 120), 0, 0, 0);
    ExAcquireResourceExclusiveLite(*(PERESOURCE *)(v21 + 16), 1u);
    ExReleaseResourceLite(*(PERESOURCE *)(v21 + 16));
    CcPurgeCacheSection(*(PSECTION_OBJECT_POINTERS *)(v21 + 120), 0, 0, 0);
    _InterlockedAnd((volatile signed __int32 *)(*(_QWORD *)(v21 + 184) + 200LL), 0xFFFFFDFF);
  }
  if ( (((_DWORD)v28 - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( (v28 & 0xFFFFFFFA) != 0 || (_DWORD)v28 == 1 )
      KeBugCheckEx(0x23u, 0x610D0u, v28, 0, 0);
    v38 = *a1;
    v39 = FatCheckSystemSecurityAccess(a2);
    *a1 = v39;
    if ( v39 < 0 )
      goto LABEL_10;
    LOWORD(v51) = a12;
    *(_OWORD *)a1 = *(_OWORD *)FatSupersedeOrOverwriteFile(v60, a2, a4, v21, a9, a10, a11);
    v23 = (_DWORD *)a5;
    if ( !*a1 )
      *a1 = v38;
  }
  else
  {
    v23 = (_DWORD *)a5;
    if ( !a14 || *(_BYTE *)(a5 + 376) == 32 )
      goto LABEL_83;
    v55 = 0;
    FatGetDirentFromFcbOrDcb(a2, v21, 0, (unsigned int)&v59, (__int64)&Bcb);
    FatGetNeedEaCount(a2, a5);
    v37 = Bcb;
    if ( Bcb )
    {
      CcUnpinData(Bcb);
      Bcb = 0;
    }
    if ( v55 )
    {
      *a1 = -1073741790;
    }
    else
    {
LABEL_83:
      Ccb = FatCreateCcb(v37, v34);
      FatSetFileObject(a4, v40, v21, Ccb);
      *(_QWORD *)(a4 + 40) = *(_QWORD *)(v21 + 120);
      *((_QWORD *)a1 + 1) = 1;
    }
  }
LABEL_84:
  if ( *a1 >= 0 && *a1 != 259 )
  {
    if ( v53 )
    {
      v41 = a7;
      *a7 &= ~v53;
      IoCheckShareAccess(*v41, a8, (PFILE_OBJECT)a4, (PSHARE_ACCESS)(v21 + 200), 1u);
    }
    else
    {
      IoUpdateShareAccess((PFILE_OBJECT)a4, (PSHARE_ACCESS)(v21 + 200));
    }
    *(_DWORD *)(v21 + 192) &= ~0x800u;
    ++*(_DWORD *)(v21 + 228);
    ++*(_DWORD *)(v21 + 232);
    if ( (*(_DWORD *)(a4 + 80) & 8) != 0 )
      ++*(_DWORD *)(v21 + 236);
    ++v23[68];
    if ( !*(_WORD *)(a4 + 75) )
      ++v23[69];
    v43 = *(_QWORD *)(a4 + 32);
    if ( a15 )
      *(_DWORD *)(v43 + 4) |= 0x400u;
    if ( a17 )
      *(_DWORD *)(v43 + 4) |= 0x800u;
    if ( (*(_BYTE *)(a3 + 2) & 1) != 0 )
      LOBYTE(v42) = 1;
    else
      LOBYTE(v42) = *(_BYTE *)(*(_QWORD *)(a2 + 40) + 64LL);
    if ( (unsigned __int8)FatCheckManageVolumeAccess(a3, *(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL), v42) )
      *(_DWORD *)(v43 + 4) |= 0x20000u;
    if ( (v23[50] & 0x400000) != 0 )
    {
      v44 = *(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL);
      v45 = *(_DWORD *)(v44 + 16);
      if ( (*(_DWORD *)(v21 + 192) & 0x60000) != 0 )
      {
        *(_DWORD *)(v44 + 20) |= v45;
        if ( (*(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 8) + 8LL) + 20LL) & 0x27) != 0 )
        {
          *(_DWORD *)(a2 + 136) = 131090;
          if ( v56 )
            *(_DWORD *)(a2 + 136) = 131346;
          Callback = EfsFileCreateCallback(
                       v21,
                       *(_QWORD *)(v21 + 176),
                       a3,
                       *(_DWORD *)(a2 + 136),
                       (v23[50] >> 14) & 1,
                       a2,
                       (__int64)(v23 - 104),
                       (_DWORD)v51,
                       v21 + 144,
                       a2 + 128);
          if ( Callback < 0 )
          {
            *a1 = Callback;
            *(_DWORD *)(a2 + 72) = Callback;
            ExRaiseStatus(Callback);
          }
          *(_DWORD *)(a2 + 68) |= 0x8000u;
        }
      }
      else
      {
        *(_DWORD *)(v44 + 20) |= v45;
        EncryptOnCloseProcessing = FatCreateEncryptOnCloseProcessing(
                                     a2,
                                     *(_QWORD *)(a2 + 40),
                                     a3,
                                     (_DWORD)v23,
                                     v21,
                                     *(_QWORD *)(a4 + 32));
        if ( EncryptOnCloseProcessing < 0 )
        {
          *a1 = EncryptOnCloseProcessing;
          *(_DWORD *)(a2 + 72) = EncryptOnCloseProcessing;
          ExRaiseStatus(EncryptOnCloseProcessing);
        }
      }
    }
  }
  v48 = Bcb;
  if ( Bcb )
  {
    CcUnpinData(Bcb);
    Bcb = 0;
  }
  if ( v52 )
  {
    if ( (*(_DWORD *)(v21 + 232))-- == 1 )
    {
      if ( a4 )
      {
        *(_QWORD *)(a4 + 40) = 0;
        if ( *(_QWORD *)(a4 + 24) == v21 )
          *(_QWORD *)(a4 + 24) = 0;
      }
      FatDeleteFcb(v48, &a6);
      v22 = 0;
      v21 = a6;
    }
  }
  if ( v22 )
    ExReleaseResourceLite(*(PERESOURCE *)(v21 + 8));
  return a1;
}

```

## disassembly

```asm
0x14002adec  mov     r11, rsp
0x14002adef  mov     [r11+20h], r9
0x14002adf3  mov     [r11+18h], r8
0x14002adf7  push    rbx
0x14002adf8  push    rsi
0x14002adf9  push    rdi
0x14002adfa  push    r12
0x14002adfc  push    r13
0x14002adfe  push    r14
0x14002ae00  push    r15
0x14002ae02  sub     rsp, 0A0h
0x14002ae09  mov     r13, r9
0x14002ae0c  mov     rdi, rdx
0x14002ae0f  mov     r14, rcx
0x14002ae12  xorps   xmm0, xmm0
0x14002ae15  movups  xmmword ptr [rcx], xmm0
0x14002ae18  xor     r15d, r15d
0x14002ae1b  mov     [r11-70h], r15
0x14002ae1f  mov     [r11-50h], r15
0x14002ae23  mov     [r11-74h], r15d
0x14002ae27  mov     [r11-77h], r15b
0x14002ae2b  mov     [r11-58h], r15
0x14002ae2f  mov     [r11-78h], r15b
0x14002ae33  mov     rax, [r8+8]
0x14002ae37  mov     rcx, [rax+8]
0x14002ae3b  mov     eax, [rcx+0Ch]
0x14002ae3e  and     eax, 40000h
0x14002ae43  mov     [rsp+0D8h+var_64], eax
0x14002ae47  mov     rbx, [r11+30h]
0x14002ae4b  mov     rdx, rbx
0x14002ae4e  mov     rcx, rdi
0x14002ae51  call    FatAcquireExclusiveFcb
0x14002ae56  lea     esi, [r15+1]
0x14002ae5a  mov     [rsp+0D8h+arg_0], sil
0x14002ae62  mov     r12, [rsp+0D8h+arg_20]
0x14002ae6a  mov     eax, [r12+0C8h]
0x14002ae72  bt      eax, 16h
0x14002ae76  jnb     short loc_14002AEB0
0x14002ae78  test    dword ptr [rbx+0C0h], 100000h
0x14002ae82  jz      short loc_14002AEB0
0x14002ae84  bts     dword ptr [rdi+44h], 13h
0x14002ae89  lea     rcx, Event; Event
0x14002ae90  call    cs:__imp_KeClearEvent
0x14002ae97  nop     dword ptr [rax+rax+00h]
0x14002ae9c  mov     ecx, 0C00000D8h; Status
0x14002aea1  mov     [rdi+48h], ecx
0x14002aea4  call    cs:__imp_ExRaiseStatus
0x14002aeb0  mov     rax, [rsp+0D8h+arg_88]
0x14002aeb8  mov     [rax], r15b
0x14002aebb  lea     r15, [rbx+58h]
0x14002aebf  mov     [rsp+0D8h+PostIrpRoutine], 0; PostIrpRoutine
0x14002aec8  mov     [rsp+0D8h+CompletionRoutine], 0; CompletionRoutine
0x14002aed1  xor     r9d, r9d; Context
0x14002aed4  lea     r8d, [r9+2]; Flags
0x14002aed8  mov     rdx, [rdi+28h]; Irp
0x14002aedc  mov     rcx, r15; Oplock
0x14002aedf  call    cs:__imp_FsRtlCheckOplockEx
0x14002aee6  nop     dword ptr [rax+rax+00h]
0x14002aeeb  mov     [r14], eax
0x14002aeee  test    eax, eax
0x14002aef0  jnz     loc_14002B4E4
0x14002aef6  mov     rcx, r15; Oplock
0x14002aef9  call    cs:__imp_FsRtlCurrentBatchOplock
0x14002af00  nop     dword ptr [rax+rax+00h]
0x14002af05  test    al, al
0x14002af07  jz      short loc_14002AF54
0x14002af09  mov     qword ptr [r14+8], 9
0x14002af11  lea     rax, FatPrePostIrp
0x14002af18  mov     [rsp+0D8h+CompletionRoutine], rax; PostIrpRoutine
0x14002af1d  lea     r9, FatOplockComplete; CompletionRoutine
0x14002af24  mov     r8, rdi; Context
0x14002af27  mov     rdx, [rdi+28h]; Irp
0x14002af2b  mov     rcx, r15; Oplock
0x14002af2e  call    cs:__imp_FsRtlCheckOplock
0x14002af35  nop     dword ptr [rax+rax+00h]
0x14002af3a  mov     [r14], eax
0x14002af3d  cmp     eax, 103h
0x14002af42  jnz     short loc_14002AF54
0x14002af44  mov     rax, [rsp+0D8h+arg_88]
0x14002af4c  mov     [rax], sil
0x14002af4f  jmp     loc_14002B4E4
0x14002af54  mov     r12d, dword ptr [rsp+0D8h+BugCheckParameter2]
0x14002af5c  cmp     r12d, 2
0x14002af60  jnz     short loc_14002AF76
0x14002af62  mov     dword ptr [r14], 0C0000035h
0x14002af69  mov     r12, [rsp+0D8h+arg_20]
0x14002af71  jmp     loc_14002B4E4
0x14002af76  test    r12d, r12d
0x14002af79  jnz     short loc_14002AF82
0x14002af7b  mov     edx, 10000h
0x14002af80  jmp     short loc_14002AF90
0x14002af82  lea     eax, [r12-4]
0x14002af87  cmp     eax, esi
0x14002af89  ja      short loc_14002AFAE
0x14002af8b  mov     edx, 112h
0x14002af90  mov     r15, [rsp+0D8h+arg_30]
0x14002af98  mov     eax, [r15]
0x14002af9b  mov     ecx, eax
0x14002af9d  not     ecx
0x14002af9f  and     ecx, edx
0x14002afa1  mov     [rsp+0D8h+var_60], ecx
0x14002afa5  or      eax, edx
0x14002afa7  mov     [r15], eax
0x14002afaa  mov     [rsp+0D8h+var_74], ecx
0x14002afae  mov     r8, [rsp+0D8h+arg_30]
0x14002afb6  mov     dl, [rbx+222h]
0x14002afbc  call    FatCheckFileAccess
0x14002afc1  test    al, al
0x14002afc3  jnz     short loc_14002AFCE
0x14002afc5  mov     dword ptr [r14], 0C0000022h
0x14002afcc  jmp     short loc_14002AF69
0x14002afce  mov     r15, [rsp+0D8h+arg_20]
0x14002afd6  mov     eax, [r15+0C8h]
0x14002afdd  bt      eax, 16h
0x14002afe1  jnb     short loc_14002B014
0x14002afe3  cmp     [rsp+0D8h+var_64], 0
0x14002afe8  jz      short loc_14002B014
0x14002afea  mov     rax, [rsp+0D8h+arg_30]
0x14002aff2  mov     ecx, [rax]
0x14002aff4  test    cl, 27h
0x14002aff7  jz      short loc_14002B014
0x14002aff9  test    dword ptr [rbx+0C0h], 60000h
0x14002b003  jnz     short loc_14002B014
0x14002b005  mov     dword ptr [r14], 0C0000022h
0x14002b00c  mov     r12, r15
0x14002b00f  jmp     loc_14002B4E4
0x14002b014  cmp     [rsp+0D8h+arg_70], 0
0x14002b01c  jz      short loc_14002B030
0x14002b01e  test    [rbx+222h], sil
0x14002b025  jz      short loc_14002B030
0x14002b027  mov     dword ptr [r14], 0C0000121h
0x14002b02e  jmp     short loc_14002B00C
0x14002b030  test    r12d, 0FFFFFFFAh
0x14002b037  jnz     short loc_14002B0AB
0x14002b039  cmp     r12d, esi
0x14002b03c  jz      short loc_14002B0AB
0x14002b03e  mov     al, [rbx+222h]
0x14002b044  test    al, 2
0x14002b046  jz      short loc_14002B052
0x14002b048  test    byte ptr [rsp+0D8h+arg_58], 2
0x14002b050  jz      short loc_14002B005
0x14002b052  test    al, 4
0x14002b054  jz      short loc_14002B060
0x14002b056  test    byte ptr [rsp+0D8h+arg_58], 4
0x14002b05e  jz      short loc_14002B005
0x14002b060  mov     eax, [r15+0C8h]
0x14002b067  bt      eax, 0Eh
0x14002b06b  jnb     short loc_14002B0AB
0x14002b06d  mov     rdx, [r15+0C0h]
0x14002b074  mov     rdx, [rdx+10h]; DeviceObject
0x14002b078  mov     rcx, [rdi+28h]; Irp
0x14002b07c  call    cs:__imp_IoSetHardErrorOrVerifyDevice
0x14002b083  nop     dword ptr [rax+rax+00h]
0x14002b088  mov     rax, [r15+0C0h]
0x14002b08f  mov     rcx, [rax+10h]
0x14002b093  or      dword ptr [rcx+30h], 2
0x14002b097  mov     ecx, 0C00000A2h; Status
0x14002b09c  mov     [rdi+48h], ecx
0x14002b09f  call    cs:__imp_ExRaiseStatus
0x14002b0ab  movzx   eax, [rsp+0D8h+arg_38]
0x14002b0b3  mov     dword ptr [rsp+0D8h+CompletionRoutine], eax
0x14002b0b7  mov     r15, [rsp+0D8h+arg_30]
0x14002b0bf  mov     r9, r15
0x14002b0c2  mov     r8, rbx
0x14002b0c5  mov     rdx, r13
0x14002b0c8  call    FatCheckShareAccess
0x14002b0cd  mov     [r14], eax
0x14002b0d0  test    eax, eax
0x14002b0d2  jns     loc_14002B16B
0x14002b0d8  cmp     eax, 0C0000043h
0x14002b0dd  jnz     loc_14002AF69
0x14002b0e3  mov     rax, [rsp+0D8h+arg_10]
0x14002b0eb  test    dword ptr [rax+10h], 100h
0x14002b0f2  jnz     loc_14002AF69
0x14002b0f8  lea     rax, [rsp+0D8h+arg_38]
0x14002b100  mov     [rsp+0D8h+var_A0], rax
0x14002b105  mov     [rsp+0D8h+var_A8], r15
0x14002b10a  lea     rax, FatPrePostIrp
0x14002b111  mov     [rsp+0D8h+PostIrpRoutine], rax
0x14002b116  lea     r9, FatOplockComplete
0x14002b11d  mov     [rsp+0D8h+CompletionRoutine], r9
0x14002b122  mov     r9, rdi
0x14002b125  mov     r8d, 80h
0x14002b12b  mov     rdx, [rdi+28h]
0x14002b12f  lea     rcx, [rbx+58h]
0x14002b133  call    cs:__imp_FsRtlOplockBreakH2
0x14002b13a  nop     dword ptr [rax+rax+00h]
0x14002b13f  mov     ecx, 103h
0x14002b144  cmp     eax, ecx
0x14002b146  jnz     short loc_14002B15B
0x14002b148  mov     [r14], ecx
0x14002b14b  mov     rax, [rsp+0D8h+arg_88]
0x14002b153  mov     [rax], sil
0x14002b156  jmp     loc_14002AF69
0x14002b15b  test    eax, eax
0x14002b15d  jns     loc_14002AF69
0x14002b163  mov     [r14], eax
0x14002b166  jmp     loc_14002AF69
0x14002b16b  lea     r15, [rbx+58h]
0x14002b16f  cmp     dword ptr [rbx+0E4h], 0
0x14002b176  jz      short loc_14002B1A4
0x14002b178  lea     rax, FatPrePostIrp
0x14002b17f  mov     [rsp+0D8h+CompletionRoutine], rax; PostIrpRoutine
0x14002b184  lea     r9, FatOplockComplete; CompletionRoutine
0x14002b18b  mov     r8, rdi; Context
0x14002b18e  mov     rdx, [rdi+28h]; Irp
0x14002b192  mov     rcx, r15; Oplock
0x14002b195  call    cs:__imp_FsRtlCheckOplock
0x14002b19c  nop     dword ptr [rax+rax+00h]
0x14002b1a1  mov     [r14], eax
0x14002b1a4  mov     ecx, 103h
0x14002b1a9  cmp     eax, ecx
0x14002b1ab  jz      short loc_14002B14B
0x14002b1ad  cmp     [rsp+0D8h+arg_78], 0
0x14002b1b5  jz      short loc_14002B1DB
0x14002b1b7  test    eax, eax
0x14002b1b9  jnz     short loc_14002B1DF
0x14002b1bb  mov     r8d, [rbx+0E4h]
0x14002b1c2  add     r8d, esi; OpenCount
0x14002b1c5  mov     rdx, [rdi+28h]; Irp
0x14002b1c9  mov     rcx, r15; Oplock
0x14002b1cc  call    cs:__imp_FsRtlOplockFsctrl
0x14002b1d3  nop     dword ptr [rax+rax+00h]
0x14002b1d8  mov     [r14], eax
0x14002b1db  test    eax, eax
0x14002b1dd  jz      short loc_14002B1EA
0x14002b1df  cmp     eax, 108h
0x14002b1e4  jnz     loc_14002AF69
0x14002b1ea  cmp     [rbx+0C4h], esi
0x14002b1f0  jnz     short loc_14002B24C
0x14002b1f2  mov     eax, 502h
0x14002b1f7  cmp     [rbx], ax
0x14002b1fa  jnz     short loc_14002B24C
0x14002b1fc  mov     rcx, r15; Oplock
0x14002b1ff  call    cs:__imp_FsRtlOplockIsFastIoPossible
0x14002b206  nop     dword ptr [rax+rax+00h]
0x14002b20b  test    al, al
0x14002b20d  jz      short loc_14002B24C
0x14002b20f  cmp     byte ptr [rbx+150h], 0
0x14002b216  jnz     short loc_14002B245
0x14002b218  mov     rax, [rbx+78h]
0x14002b21c  cmp     dword ptr [rax+18h], 0
0x14002b220  jnz     short loc_14002B245
0x14002b222  mov     rax, [rbx+0B8h]
0x14002b229  mov     ecx, [rax+0C8h]
0x14002b22f  bt      ecx, 0Eh
0x14002b233  jb      short loc_14002B245
0x14002b235  test    dword ptr [rbx+0C0h], 8000h
0x14002b23f  jnz     short loc_14002B245
0x14002b241  mov     eax, esi
0x14002b243  jmp     short loc_14002B24E
0x14002b245  mov     eax, 2
0x14002b24a  jmp     short loc_14002B24E
0x14002b24c  xor     eax, eax
0x14002b24e  mov     [rbx+5], al
0x14002b251  mov     rax, [rsp+0D8h+arg_30]
0x14002b259  mov     ecx, [rax]
0x14002b25b  test    cl, 2
0x14002b25e  jnz     short loc_14002B26A
0x14002b260  cmp     [rsp+0D8h+arg_70], 0
0x14002b268  jz      short loc_14002B2AA
0x14002b26a  add     [rbx+0E8h], esi
0x14002b270  mov     [rsp+0D8h+var_78], sil
0x14002b275  mov     edx, esi; FlushType
0x14002b277  mov     rcx, [rbx+78h]; SectionObjectPointer
0x14002b27b  call    cs:__imp_MmFlushImageSection
0x14002b282  nop     dword ptr [rax+rax+00h]
0x14002b287  test    al, al
0x14002b289  jnz     short loc_14002B2AA
0x14002b28b  mov     al, [rsp+0D8h+arg_70]
0x14002b292  neg     al
0x14002b294  sbb     ecx, ecx
0x14002b296  and     ecx, 0DEh
0x14002b29c  add     ecx, 0C0000043h
0x14002b2a2  mov     [r14], ecx
0x14002b2a5  jmp     loc_14002AF69
0x14002b2aa  mov     eax, [r13+50h]
0x14002b2ae  test    al, 8
0x14002b2b0  jz      loc_14002B359
0x14002b2b6  mov     eax, [rbx+0ECh]
0x14002b2bc  cmp     [rbx+0E4h], eax
0x14002b2c2  jnz     loc_14002B359
0x14002b2c8  mov     rax, [rbx+78h]
0x14002b2cc  cmp     qword ptr [rax], 0
0x14002b2d0  jz      loc_14002B359
0x14002b2d6  mov     eax, [rbx+0C0h]
0x14002b2dc  test    al, 4
0x14002b2de  jnz     short loc_14002B359
0x14002b2e0  mov     rax, [rbx+0B8h]
0x14002b2e7  mov     r15d, 0C8h
0x14002b2ed  lock or dword ptr [rax+r15], 200h
0x14002b2f6  xor     r9d, r9d; IoStatus
0x14002b2f9  xor     r8d, r8d; Length
0x14002b2fc  xor     edx, edx; FileOffset
0x14002b2fe  mov     rcx, [rbx+78h]; SectionObjectPointer
0x14002b302  call    cs:__imp_CcFlushCache
0x14002b309  nop     dword ptr [rax+rax+00h]
0x14002b30e  mov     dl, sil; Wait
0x14002b311  mov     rcx, [rbx+10h]; Resource
0x14002b315  call    cs:__imp_ExAcquireResourceExclusiveLite
  ... truncated ...
```
