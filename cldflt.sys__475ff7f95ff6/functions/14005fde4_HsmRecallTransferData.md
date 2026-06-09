# HsmRecallTransferData

- ea: `0x14005fde4`
- end: `0x140060496`
- name: `HsmRecallTransferData`
- size: `1714`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x14006c6f0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140017de8`
- `0x140035a0c`
- `0x140043324`
- `0x140052574`
- `0x140058ddc`
- `0x140059738`
- `0x14005ce40`
- `0x14005e76c`
- `0x14005fde4`
- `0x1400652e4`
- `0x140067e24`
- `0x140069948`
- `0x14006f28c`
- `0x14006fcf4`
- `0x14007458c`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400602f1`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400602f1`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140060305`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006034b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140060305`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006034b`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140060338`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140060338`
- `ntoskrnl!FsRtlReleaseFile` at `0x14006035a`
- `ntoskrnl!FsRtlReleaseFile` at `0x14006035a`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x140060317`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x140060317`
- `ntoskrnl!ObfDereferenceObject` at `0x140060476`
- `ntoskrnl!ObfDereferenceObject` at `0x140060476`
- `FLTMGR!FltClose` at `0x140060461`
- `FLTMGR!FltClose` at `0x140060461`
- `FLTMGR!FltReleasePushLockEx` at `0x14006044c`
- `FLTMGR!FltReleasePushLockEx` at `0x14006044c`

## pseudocode

```c
__int64 __fastcall HsmRecallTransferData(__int64 a1, __int64 a2, char a3, __int64 a4, ULONG a5, __int64 a6)
{
  _QWORD *v6; // r14
  int v7; // esi
  struct _FLT_INSTANCE *v10; // rdx
  __int64 v11; // r15
  __int64 v12; // r13
  int SyncPolicy; // edi
  char StreamSize; // al
  __int64 v15; // r10
  PFILE_OBJECT v16; // r13
  __int64 v17; // rdx
  char v18; // al
  __int64 v19; // rdx
  __int64 v20; // rcx
  ULONG v21; // esi
  char v22; // al
  __int64 v23; // r10
  int v24; // edx
  int v25; // ecx
  int v26; // r13d
  bool v27; // zf
  PFILE_OBJECT v28; // r13
  int v29; // edi
  char v30; // di
  __int64 Flags; // [rsp+20h] [rbp-58h]
  ULONG Flagsa[2]; // [rsp+20h] [rbp-58h]
  HANDLE FileHandle; // [rsp+50h] [rbp-28h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+58h] [rbp-20h] BYREF
  __int64 v37; // [rsp+C8h] [rbp+50h]
  PFILE_OBJECT FileObject; // [rsp+D8h] [rbp+60h] BYREF

  v6 = *(_QWORD **)(a2 + 16);
  v7 = *(_DWORD *)(a2 + 28);
  v10 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v11 = a4 + a5;
  v12 = v6[4];
  IoStatus.Pointer = v6;
  v37 = v12;
  FileHandle = 0;
  FileObject = 0;
  SyncPolicy = HsmpOpenFileByIdEx(
                 (const UNICODE_STRING *)a1,
                 v10,
                 v12,
                 0x100180u,
                 Flags,
                 2097256,
                 1,
                 &FileHandle,
                 &FileObject);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a2);
      WPP_SF_qLiiiid(
        *(_QWORD *)(v15 + 24),
        92,
        (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        StreamSize,
        v12,
        a4,
        v11,
        SyncPolicy);
    }
    goto LABEL_75;
  }
  v16 = FileObject;
  SyncPolicy = HsmpPrepareForMgmtOperation(v6[2], FileObject, 0);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy >= 0 )
  {
    LOBYTE(v17) = 1;
    HsmpAcquireReparseUpdateLock(a2, v17);
    LOBYTE(v19) = 1;
    HsmpAcquireBitmapLock(a2, v19);
    if ( v11 < a4
      || v11 > HsmpGetStreamSize(a2)
      || (v20 = (v7 & 2) != 0 ? -1 : 4095, (v20 & a4) != 0)
      || (v21 = a5, ((unsigned int)v20 & a5) != 0) && v11 != HsmpGetStreamSize(a2) )
    {
      SyncPolicy = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_74;
      }
      v22 = HsmpGetStreamSize(a2);
      v24 = 95;
    }
    else
    {
      SyncPolicy = HsmpValidateStreamContextNoLock(a2, v16);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_74;
        }
        v22 = HsmpGetStreamSize(a2);
        v24 = 96;
        goto LABEL_73;
      }
      Flagsa[0] = v21;
      SyncPolicy = HsmiRecallWriteFileNoLock(a2, (__int64)v16, a6, a4, *(_QWORD *)Flagsa);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_74;
        }
        v22 = HsmpGetStreamSize(a2);
        v24 = 97;
        goto LABEL_73;
      }
      SyncPolicy = HsmiExpandBitmapNoLock(a2, 16964);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_74;
        }
        v22 = HsmpGetStreamSize(a2);
        v24 = 98;
        goto LABEL_73;
      }
      SyncPolicy = HsmiMarkFileRangeNoLock(a2, 16964, a4, v11, 1);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_74;
        }
        v22 = HsmpGetStreamSize(a2);
        v24 = 99;
        goto LABEL_73;
      }
      v25 = *(_DWORD *)(a2 + 28);
      v26 = v25 & 0x100;
      if ( !a3 )
      {
        SyncPolicy = HsmiMarkFileRangeNoLock(a2, 16982, a4, v11, 1);
        HsmDbgBreakOnStatus(SyncPolicy);
        if ( SyncPolicy < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_74;
          }
          v22 = HsmpGetStreamSize(a2);
          v24 = 100;
          goto LABEL_73;
        }
        v25 = *(_DWORD *)(a2 + 28);
      }
      v27 = v26 == 0;
      v28 = FileObject;
      if ( v27 && (v25 & 0x10100) == 0x10100 )
      {
        v29 = HsmpSetCompressionNoLock(a1, FileObject, 1, v37);
        HsmDbgBreakOnStatus(v29);
        if ( v29 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_qqqd(
            WPP_GLOBAL_Control->AttachedDevice,
            101,
            WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
            a1,
            a2,
            *((_QWORD *)IoStatus.Pointer + 4),
            v29);
        }
        *(_DWORD *)(a2 + 28) &= ~0x10000u;
        v25 = *(_DWORD *)(a2 + 28);
      }
      if ( (v25 & 0x100) != 0 )
      {
        a5 = 0;
        SyncPolicy = HsmpCldGetSyncPolicy(a1, a2, (_DWORD)v28, 1, (__int64)&a5);
        HsmDbgBreakOnStatus(SyncPolicy);
        if ( SyncPolicy < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              102,
              WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
              a1,
              a2,
              v37,
              SyncPolicy);
          }
          goto LABEL_74;
        }
        if ( (a5 & 0xF) >= 3 )
        {
          v30 = 0;
          IoStatus = 0;
          if ( !IoGetTopLevelIrp() )
          {
            IoSetTopLevelIrp((PIRP)1);
            v30 = 1;
          }
          FsRtlAcquireFileExclusive(v28);
          CcCoherencyFlushAndPurgeCache(v28->SectionObjectPointer, 0, 0, &IoStatus, 0);
          if ( v30 )
            IoSetTopLevelIrp(0);
          FsRtlReleaseFile(v28);
          SyncPolicy = IoStatus.Status;
          if ( IoStatus.Status < 0 )
            goto LABEL_74;
        }
      }
      SyncPolicy = HsmpRpCommitNoLock(a1, a2, v28, 0, 1);
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy >= 0
        || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
LABEL_74:
        HsmpReleaseBitmapLock(a2);
        FltReleasePushLockEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
        goto LABEL_75;
      }
      v22 = HsmpGetStreamSize(a2);
      v24 = 103;
    }
LABEL_73:
    WPP_SF_qLiiiid(
      *(_QWORD *)(v23 + 24),
      v24,
      (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v22,
      v37,
      a4,
      v11,
      SyncPolicy);
    goto LABEL_74;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v18 = HsmpGetStreamSize(a2);
    WPP_SF_qLiiiid(
      *(_QWORD *)(v15 + 24),
      94,
      (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v18,
      v37,
      a4,
      v11,
      SyncPolicy);
  }
LABEL_75:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)SyncPolicy;
}

```

## disassembly

```asm
0x14005fde4  mov     r11, rsp
0x14005fde7  mov     [r11+18h], r8b
0x14005fdeb  mov     [r11+8], rcx
0x14005fdef  push    rbp
0x14005fdf0  push    rbx
0x14005fdf1  push    rsi
0x14005fdf2  push    rdi
0x14005fdf3  push    r12
0x14005fdf5  push    r13
0x14005fdf7  push    r14
0x14005fdf9  push    r15
0x14005fdfb  mov     rbp, rsp
0x14005fdfe  sub     rsp, 78h
0x14005fe02  mov     r14, [rdx+10h]
0x14005fe06  lea     rax, [rbp+FileObject]
0x14005fe0a  mov     esi, [rdx+1Ch]
0x14005fe0d  mov     r12, r9
0x14005fe10  mov     r15d, [rbp+arg_20]
0x14005fe14  mov     rbx, rdx
0x14005fe17  mov     rdx, [rcx+20h]
0x14005fe1b  add     r15, r9
0x14005fe1e  mov     r13, [r14+20h]
0x14005fe22  mov     r9d, 100180h
0x14005fe28  mov     [r11-78h], rax
0x14005fe2c  mov     r8, r13
0x14005fe2f  lea     rax, [rbp+FileHandle]
0x14005fe33  mov     qword ptr [rbp+IoStatus], r14
0x14005fe37  mov     [r11-80h], rax
0x14005fe3b  mov     byte ptr [rsp+78h+var_48], 1
0x14005fe40  mov     [rbp+arg_8], r13
0x14005fe44  mov     [rbp+FileHandle], 0
0x14005fe4c  mov     [rbp+FileObject], 0
0x14005fe54  mov     dword ptr [rsp+78h+var_50], 200068h
0x14005fe5c  call    HsmpOpenFileByIdEx
0x14005fe61  mov     ecx, eax
0x14005fe63  mov     edi, eax
0x14005fe65  call    HsmDbgBreakOnStatus
0x14005fe6a  test    edi, edi
0x14005fe6c  jns     short loc_14005FEE3
0x14005fe6e  mov     r10, cs:WPP_GLOBAL_Control
0x14005fe75  lea     rsi, WPP_GLOBAL_Control
0x14005fe7c  cmp     r10, rsi
0x14005fe7f  jz      loc_140060458
0x14005fe85  mov     ecx, [r10+2Ch]
0x14005fe89  test    cl, 1
0x14005fe8c  jz      loc_140060458
0x14005fe92  mov     r14b, 2
0x14005fe95  cmp     [r10+29h], r14b
0x14005fe99  jb      loc_140060458
0x14005fe9f  mov     rcx, rbx
0x14005fea2  call    HsmpGetStreamSize
0x14005fea7  mov     [rsp+78h+var_30], edi
0x14005feab  mov     edx, 5Ch ; '\'
0x14005feb0  mov     [rsp+78h+var_38], r15
0x14005feb5  mov     [rsp+78h+var_40], r12
0x14005feba  mov     [rsp+78h+var_48], r13
0x14005febf  mov     rcx, [r10+18h]
0x14005fec3  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14005feca  mov     [rsp+78h+var_50], rax
0x14005fecf  mov     r9, rbx
0x14005fed2  mov     eax, [rbx+1Ch]
0x14005fed5  mov     [rsp+78h+Flags], eax
0x14005fed9  call    WPP_SF_qLiiiid
0x14005fede  jmp     loc_140060458
0x14005fee3  mov     r13, [rbp+FileObject]
0x14005fee7  xor     r9d, r9d
0x14005feea  mov     rcx, [r14+10h]
0x14005feee  mov     rdx, r13
0x14005fef1  xor     r8d, r8d
0x14005fef4  call    HsmpPrepareForMgmtOperation
0x14005fef9  mov     ecx, eax
0x14005fefb  mov     edi, eax
0x14005fefd  call    HsmDbgBreakOnStatus
0x14005ff02  test    edi, edi
0x14005ff04  jns     short loc_14005FF5F
0x14005ff06  mov     r10, cs:WPP_GLOBAL_Control
0x14005ff0d  lea     rsi, WPP_GLOBAL_Control
0x14005ff14  cmp     r10, rsi
0x14005ff17  jz      loc_140060458
0x14005ff1d  mov     eax, [r10+2Ch]
0x14005ff21  test    al, 1
0x14005ff23  jz      loc_140060458
0x14005ff29  mov     r14b, 2
0x14005ff2c  cmp     [r10+29h], r14b
0x14005ff30  jb      loc_140060458
0x14005ff36  mov     rcx, rbx
0x14005ff39  call    HsmpGetStreamSize
0x14005ff3e  mov     rcx, [rbp+arg_8]
0x14005ff42  mov     edx, 5Eh ; '^'
0x14005ff47  mov     [rsp+78h+var_30], edi
0x14005ff4b  mov     [rsp+78h+var_38], r15
0x14005ff50  mov     [rsp+78h+var_40], r12
0x14005ff55  mov     [rsp+78h+var_48], rcx
0x14005ff5a  jmp     loc_14005FEBF
0x14005ff5f  mov     dl, 1
0x14005ff61  mov     rcx, rbx
0x14005ff64  call    HsmpAcquireReparseUpdateLock
0x14005ff69  mov     dl, 1
0x14005ff6b  mov     rcx, rbx
0x14005ff6e  call    HsmpAcquireBitmapLock
0x14005ff73  mov     r14b, 2
0x14005ff76  cmp     r15, r12
0x14005ff79  jl      loc_1400603CA
0x14005ff7f  mov     rcx, rbx
0x14005ff82  call    HsmpGetStreamSize
0x14005ff87  cmp     r15, rax
0x14005ff8a  jg      loc_1400603CA
0x14005ff90  and     sil, r14b
0x14005ff93  neg     sil
0x14005ff96  sbb     eax, eax
0x14005ff98  and     eax, 0FFFFF000h
0x14005ff9d  lea     ecx, [rax+0FFFh]
0x14005ffa3  test    r12, rcx
0x14005ffa6  jnz     loc_1400603CA
0x14005ffac  mov     esi, [rbp+arg_20]
0x14005ffaf  test    esi, ecx
0x14005ffb1  jz      short loc_14005FFC4
0x14005ffb3  mov     rcx, rbx
0x14005ffb6  call    HsmpGetStreamSize
0x14005ffbb  cmp     r15, rax
0x14005ffbe  jnz     loc_1400603CA
0x14005ffc4  mov     rdx, r13
0x14005ffc7  mov     rcx, rbx
0x14005ffca  call    HsmpValidateStreamContextNoLock
0x14005ffcf  mov     ecx, eax
0x14005ffd1  mov     edi, eax
0x14005ffd3  call    HsmDbgBreakOnStatus
0x14005ffd8  test    edi, edi
0x14005ffda  jns     short loc_14006001B
0x14005ffdc  mov     r10, cs:WPP_GLOBAL_Control
0x14005ffe3  lea     rsi, WPP_GLOBAL_Control
0x14005ffea  cmp     r10, rsi
0x14005ffed  jz      loc_14006043A
0x14005fff3  mov     eax, [r10+2Ch]
0x14005fff7  test    al, 1
0x14005fff9  jz      loc_14006043A
0x14005ffff  cmp     [r10+29h], r14b
0x140060003  jb      loc_14006043A
0x140060009  mov     rcx, rbx
0x14006000c  call    HsmpGetStreamSize
0x140060011  mov     edx, 60h ; '`'
0x140060016  jmp     loc_140060404
0x14006001b  mov     r8, [rbp+arg_28]
0x14006001f  mov     r9, r12
0x140060022  mov     rdx, r13
0x140060025  mov     [rsp+78h+Flags], esi
0x140060029  mov     rcx, rbx
0x14006002c  call    HsmiRecallWriteFileNoLock
0x140060031  mov     ecx, eax
0x140060033  mov     edi, eax
0x140060035  call    HsmDbgBreakOnStatus
0x14006003a  test    edi, edi
0x14006003c  jns     short loc_14006007D
0x14006003e  mov     r10, cs:WPP_GLOBAL_Control
0x140060045  lea     rsi, WPP_GLOBAL_Control
0x14006004c  cmp     r10, rsi
0x14006004f  jz      loc_14006043A
0x140060055  mov     eax, [r10+2Ch]
0x140060059  test    al, 1
0x14006005b  jz      loc_14006043A
0x140060061  cmp     [r10+29h], r14b
0x140060065  jb      loc_14006043A
0x14006006b  mov     rcx, rbx
0x14006006e  call    HsmpGetStreamSize
0x140060073  mov     edx, 61h ; 'a'
0x140060078  jmp     loc_140060404
0x14006007d  mov     esi, 4244h
0x140060082  mov     rcx, rbx
0x140060085  mov     edx, esi
0x140060087  call    HsmiExpandBitmapNoLock
0x14006008c  mov     ecx, eax
0x14006008e  mov     edi, eax
0x140060090  call    HsmDbgBreakOnStatus
0x140060095  test    edi, edi
0x140060097  jns     short loc_1400600D8
0x140060099  mov     r10, cs:WPP_GLOBAL_Control
0x1400600a0  lea     rsi, WPP_GLOBAL_Control
0x1400600a7  cmp     r10, rsi
0x1400600aa  jz      loc_14006043A
0x1400600b0  mov     eax, [r10+2Ch]
0x1400600b4  test    al, 1
0x1400600b6  jz      loc_14006043A
0x1400600bc  cmp     [r10+29h], r14b
0x1400600c0  jb      loc_14006043A
0x1400600c6  mov     rcx, rbx
0x1400600c9  call    HsmpGetStreamSize
0x1400600ce  mov     edx, 62h ; 'b'
0x1400600d3  jmp     loc_140060404
0x1400600d8  mov     r9, r15
0x1400600db  mov     byte ptr [rsp+78h+Flags], 1
0x1400600e0  mov     r8, r12
0x1400600e3  mov     edx, esi
0x1400600e5  mov     rcx, rbx
0x1400600e8  call    HsmiMarkFileRangeNoLock
0x1400600ed  mov     ecx, eax
0x1400600ef  mov     edi, eax
0x1400600f1  call    HsmDbgBreakOnStatus
0x1400600f6  test    edi, edi
0x1400600f8  jns     short loc_140060139
0x1400600fa  mov     r10, cs:WPP_GLOBAL_Control
0x140060101  lea     rsi, WPP_GLOBAL_Control
0x140060108  cmp     r10, rsi
0x14006010b  jz      loc_14006043A
0x140060111  mov     eax, [r10+2Ch]
0x140060115  test    al, 1
0x140060117  jz      loc_14006043A
0x14006011d  cmp     [r10+29h], r14b
0x140060121  jb      loc_14006043A
0x140060127  mov     rcx, rbx
0x14006012a  call    HsmpGetStreamSize
0x14006012f  mov     edx, 63h ; 'c'
0x140060134  jmp     loc_140060404
0x140060139  mov     ecx, [rbx+1Ch]
0x14006013c  mov     r13d, ecx
0x14006013f  and     r13d, 100h
0x140060146  cmp     [rbp+arg_10], 0
0x14006014a  jnz     short loc_1400601B3
0x14006014c  mov     r9, r15
0x14006014f  mov     byte ptr [rsp+78h+Flags], 1
0x140060154  mov     r8, r12
0x140060157  mov     edx, 4256h
0x14006015c  mov     rcx, rbx
0x14006015f  call    HsmiMarkFileRangeNoLock
0x140060164  mov     ecx, eax
0x140060166  mov     edi, eax
0x140060168  call    HsmDbgBreakOnStatus
0x14006016d  test    edi, edi
0x14006016f  jns     short loc_1400601B0
0x140060171  mov     r10, cs:WPP_GLOBAL_Control
0x140060178  lea     rsi, WPP_GLOBAL_Control
0x14006017f  cmp     r10, rsi
0x140060182  jz      loc_14006043A
0x140060188  mov     eax, [r10+2Ch]
0x14006018c  test    al, 1
0x14006018e  jz      loc_14006043A
0x140060194  cmp     [r10+29h], r14b
0x140060198  jb      loc_14006043A
0x14006019e  mov     rcx, rbx
0x1400601a1  call    HsmpGetStreamSize
0x1400601a6  mov     edx, 64h ; 'd'
0x1400601ab  jmp     loc_140060404
0x1400601b0  mov     ecx, [rbx+1Ch]
0x1400601b3  test    r13d, r13d
0x1400601b6  lea     rsi, WPP_GLOBAL_Control
0x1400601bd  mov     r13, [rbp+FileObject]
0x1400601c1  jnz     loc_140060248
0x1400601c7  mov     edx, 10100h
0x1400601cc  mov     eax, ecx
0x1400601ce  and     eax, edx
0x1400601d0  cmp     eax, edx
0x1400601d2  jnz     short loc_140060248
0x1400601d4  mov     r9, [rbp+arg_8]
0x1400601d8  mov     r8d, 1
0x1400601de  mov     rcx, [rbp+arg_0]
0x1400601e2  mov     rdx, r13
0x1400601e5  call    HsmpSetCompressionNoLock
0x1400601ea  mov     ecx, eax
0x1400601ec  mov     edi, eax
0x1400601ee  call    HsmDbgBreakOnStatus
0x1400601f3  test    edi, edi
0x1400601f5  jns     short loc_140060240
0x1400601f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400601fe  cmp     rcx, rsi
0x140060201  jz      short loc_140060240
0x140060203  mov     edx, [rcx+2Ch]
0x140060206  test    dl, 10h
0x140060209  jz      short loc_140060240
0x14006020b  cmp     byte ptr [rcx+29h], 3
0x14006020f  jb      short loc_140060240
0x140060211  mov     rax, qword ptr [rbp+IoStatus]
0x140060215  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14006021c  mov     r9, [rbp+arg_0]
0x140060220  mov     edx, 65h ; 'e'
0x140060225  mov     rcx, [rcx+18h]
0x140060229  mov     dword ptr [rsp+78h+var_48], edi
0x14006022d  mov     rax, [rax+20h]
0x140060231  mov     [rsp+78h+var_50], rax
0x140060236  mov     qword ptr [rsp+78h+Flags], rbx
0x14006023b  call    WPP_SF_qqqd
0x140060240  btr     dword ptr [rbx+1Ch], 10h
0x140060245  mov     ecx, [rbx+1Ch]
0x140060248  bt      ecx, 8
0x14006024c  jnb     loc_140060371
0x140060252  mov     rcx, [rbp+arg_0]
0x140060256  lea     rax, [rbp+arg_20]
0x14006025a  mov     r9d, 1
0x140060260  mov     qword ptr [rsp+78h+Flags], rax
0x140060265  mov     r8, r13
0x140060268  mov     [rbp+arg_20], 0
0x14006026f  mov     rdx, rbx
0x140060272  call    HsmpCldGetSyncPolicy
0x140060277  mov     ecx, eax
0x140060279  mov     edi, eax
0x14006027b  call    HsmDbgBreakOnStatus
0x140060280  test    edi, edi
0x140060282  jns     short loc_1400602D9
0x140060284  mov     rcx, cs:WPP_GLOBAL_Control
0x14006028b  cmp     rcx, rsi
0x14006028e  jz      loc_14006043A
0x140060294  mov     eax, [rcx+2Ch]
  ... truncated ...
```
