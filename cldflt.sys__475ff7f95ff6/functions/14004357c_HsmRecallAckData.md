# HsmRecallAckData

- ea: `0x14004357c`
- end: `0x140043c94`
- name: `HsmRecallAckData`
- size: `1816`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x140034268`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140017de8`
- `0x140043324`
- `0x14004357c`
- `0x140052574`
- `0x140058ddc`
- `0x140059738`
- `0x14005ce40`
- `0x14005e76c`
- `0x1400652e4`
- `0x140067e24`
- `0x140069948`
- `0x14006f28c`
- `0x1400703e4`
- `0x14007458c`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140043a14`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140043a14`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140043a28`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140043a6e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140043a28`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140043a6e`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140043a5b`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140043a5b`
- `ntoskrnl!FsRtlReleaseFile` at `0x140043a7d`
- `ntoskrnl!FsRtlReleaseFile` at `0x140043a7d`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x140043a3a`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x140043a3a`
- `ntoskrnl!ObfDereferenceObject` at `0x140043c73`
- `ntoskrnl!ObfDereferenceObject` at `0x140043c73`
- `FLTMGR!FltClose` at `0x140043c5f`
- `FLTMGR!FltClose` at `0x140043c5f`
- `FLTMGR!FltReleasePushLockEx` at `0x140043c4a`
- `FLTMGR!FltReleasePushLockEx` at `0x140043c4a`

## pseudocode

```c
__int64 HsmRecallAckData(__int64 a1, __int64 a2, int a3, ...)
{
  int v4; // esi
  __int64 v6; // rax
  struct _FLT_INSTANCE *v8; // rdx
  int FileRangeNoLock; // edi
  PFILE_OBJECT v10; // r13
  char StreamSize; // al
  __int64 v12; // r10
  int v13; // edx
  __int64 v14; // rdx
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rdx
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // rax
  __int64 v23; // rax
  __int64 v24; // rdx
  char v25; // al
  __int64 v26; // r10
  int v27; // edx
  int v28; // r12d
  bool v29; // cf
  __int64 v30; // r12
  int v31; // edi
  char v32; // di
  char v33; // al
  __int64 v34; // r10
  int v35; // edx
  __int64 Flags; // [rsp+20h] [rbp-60h]
  __int64 v38; // [rsp+50h] [rbp-30h] BYREF
  __int64 v39; // [rsp+58h] [rbp-28h]
  __int64 v40; // [rsp+60h] [rbp-20h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+70h] [rbp-10h] BYREF
  __int64 v43; // [rsp+C0h] [rbp+40h] BYREF
  PFILE_OBJECT FileObject; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v45; // [rsp+D8h] [rbp+58h] BYREF
  va_list va; // [rsp+D8h] [rbp+58h]
  __int64 v47; // [rsp+E0h] [rbp+60h]
  va_list va1; // [rsp+E8h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v45 = va_arg(va1, _QWORD);
  v47 = va_arg(va1, _QWORD);
  v43 = a1;
  v4 = *(_DWORD *)(a2 + 28);
  IoStatus.Pointer = *(PVOID *)(a2 + 16);
  v6 = *((_QWORD *)IoStatus.Pointer + 4);
  v38 = 0;
  FileHandle = 0;
  FileObject = 0;
  v8 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v39 = v6;
  FileRangeNoLock = HsmpOpenFileByIdEx(
                      (const UNICODE_STRING *)a1,
                      v8,
                      v6,
                      0x100180u,
                      Flags,
                      2097256,
                      0,
                      &FileHandle,
                      &FileObject);
  HsmDbgBreakOnStatus(FileRangeNoLock);
  v10 = FileObject;
  if ( FileRangeNoLock < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a2);
      v13 = 69;
LABEL_6:
      WPP_SF_qLiiiid(
        *(_QWORD *)(v12 + 24),
        v13,
        (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        StreamSize,
        v39,
        v45,
        v47,
        FileRangeNoLock);
      goto LABEL_82;
    }
    goto LABEL_82;
  }
  FileRangeNoLock = HsmpPrepareForMgmtOperation(a1, FileObject, 0);
  HsmDbgBreakOnStatus(FileRangeNoLock);
  if ( FileRangeNoLock >= 0 )
  {
    LOBYTE(v14) = 1;
    HsmpAcquireReparseUpdateLock(a2, v14);
    LOBYTE(v15) = 1;
    HsmpAcquireBitmapLock(a2, v15);
    v16 = HsmpGetStreamSize(a2);
    v17 = v45;
    if ( v47 <= v16 )
      v18 = v45 + v47;
    else
      v18 = HsmpGetStreamSize(a2);
    v38 = v18;
    if ( v18 < v17
      || (v19 = HsmpGetStreamSize(a2), v21 > v19)
      || (v22 = (-(__int64)((v4 & 2) != 0) & 0xFFFFF000LL) + 4095, (v22 & v21) != 0)
      || (v22 & v20) != 0 && (v23 = HsmpGetStreamSize(a2), v24 != v23) )
    {
      FileRangeNoLock = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_81;
      }
      v33 = HsmpGetStreamSize(a2);
      v35 = 72;
    }
    else
    {
      FileRangeNoLock = HsmpValidateStreamContextNoLock(a2, v10);
      HsmDbgBreakOnStatus(FileRangeNoLock);
      if ( FileRangeNoLock < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_81;
        }
        v25 = HsmpGetStreamSize(a2);
        v27 = 73;
        goto LABEL_25;
      }
      if ( a3 < 0 )
      {
        if ( a3 == -1073688818 )
        {
          FileRangeNoLock = HsmiMarkFileRangeNoLock(a2, 16964, v45, v38, 0);
          HsmDbgBreakOnStatus(FileRangeNoLock);
          if ( FileRangeNoLock < 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_81;
            }
            v25 = HsmpGetStreamSize(a2);
            v27 = 79;
LABEL_25:
            WPP_SF_qLiiiid(
              *(_QWORD *)(v26 + 24),
              v27,
              (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
              a2,
              *(_DWORD *)(a2 + 28),
              v25,
              v39,
              v45,
              v38,
              FileRangeNoLock);
LABEL_81:
            HsmpReleaseBitmapLock(a2);
            FltReleasePushLockEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
            goto LABEL_82;
          }
        }
        v30 = v43;
LABEL_71:
        FileRangeNoLock = HsmpRpCommitNoLock(v30, a2, v10, 0, 1);
        HsmDbgBreakOnStatus(FileRangeNoLock);
        if ( FileRangeNoLock >= 0
          || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_81;
        }
        v25 = HsmpGetStreamSize(a2);
        v27 = 80;
        goto LABEL_25;
      }
      LOBYTE(FileObject) = 0;
      v40 = 0;
      FileRangeNoLock = HsmiQueryFileRangeNoLock(
                          a2,
                          16964,
                          (unsigned int)va,
                          (unsigned int)&v38,
                          (__int64)&FileObject,
                          (__int64)&v40);
      HsmDbgBreakOnStatus(FileRangeNoLock);
      if ( FileRangeNoLock < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_81;
        }
        v25 = HsmpGetStreamSize(a2);
        v27 = 74;
        goto LABEL_25;
      }
      if ( (_BYTE)FileObject && v40 >= v38 )
      {
        v28 = *(_DWORD *)(a2 + 28);
        FileRangeNoLock = HsmiMarkFileRangeNoLock(a2, 16982, v45, v38, 1);
        HsmDbgBreakOnStatus(FileRangeNoLock);
        if ( FileRangeNoLock < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_81;
          }
          v25 = HsmpGetStreamSize(a2);
          v27 = 76;
          goto LABEL_25;
        }
        v29 = (v28 & 0x100) != 0;
        v30 = v43;
        if ( !v29 && (*(_DWORD *)(a2 + 28) & 0x10100) == 0x10100 )
        {
          v31 = HsmpSetCompressionNoLock(v43, v10, 1, v39);
          HsmDbgBreakOnStatus(v31);
          if ( v31 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              77,
              WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
              v30,
              a2,
              *((_QWORD *)IoStatus.Pointer + 4),
              v31);
          }
          *(_DWORD *)(a2 + 28) &= ~0x10000u;
        }
        if ( (*(_DWORD *)(a2 + 28) & 0x100) != 0 )
        {
          LODWORD(v43) = 0;
          FileRangeNoLock = HsmpCldGetSyncPolicy(v30, a2, (_DWORD)v10, 1, (__int64)&v43);
          HsmDbgBreakOnStatus(FileRangeNoLock);
          if ( FileRangeNoLock < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qqqd(
                WPP_GLOBAL_Control->AttachedDevice,
                78,
                WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
                v30,
                a2,
                v39,
                FileRangeNoLock);
            }
            goto LABEL_81;
          }
          if ( ((unsigned __int8)v43 & 0xFu) >= 3 )
          {
            v32 = 0;
            IoStatus = 0;
            if ( !IoGetTopLevelIrp() )
            {
              IoSetTopLevelIrp((PIRP)1);
              v32 = 1;
            }
            FsRtlAcquireFileExclusive(v10);
            CcCoherencyFlushAndPurgeCache(v10->SectionObjectPointer, 0, 0, &IoStatus, 0);
            if ( v32 )
              IoSetTopLevelIrp(0);
            FsRtlReleaseFile(v10);
            FileRangeNoLock = IoStatus.Status;
            if ( IoStatus.Status < 0 )
              goto LABEL_81;
          }
        }
        goto LABEL_71;
      }
      FileRangeNoLock = -1073688821;
      HsmDbgBreakOnStatus(-1073688821);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_81;
      }
      v33 = HsmpGetStreamSize(a2);
      v35 = 75;
    }
    WPP_SF_qLiiiid(
      *(_QWORD *)(v34 + 24),
      v35,
      (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v33,
      v39,
      v45,
      v38,
      11);
    goto LABEL_81;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    StreamSize = HsmpGetStreamSize(a2);
    v13 = 70;
    goto LABEL_6;
  }
LABEL_82:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v10 )
    ObfDereferenceObject(v10);
  return (unsigned int)FileRangeNoLock;
}

```

## disassembly

```asm
0x14004357c  mov     r11, rsp
0x14004357f  mov     [r11+20h], r9
0x140043583  mov     [r11+8], rcx
0x140043587  push    rbp
0x140043588  push    rbx
0x140043589  push    rsi
0x14004358a  push    rdi
0x14004358b  push    r12
0x14004358d  push    r13
0x14004358f  push    r15
0x140043591  mov     rbp, rsp
0x140043594  sub     rsp, 80h
0x14004359b  mov     rax, [rdx+10h]
0x14004359f  mov     r15, rcx
0x1400435a2  mov     esi, [rdx+1Ch]
0x1400435a5  lea     rcx, [rbp+FileObject]
0x1400435a9  mov     [r11-78h], rcx
0x1400435ad  mov     rbx, rdx
0x1400435b0  xor     edx, edx
0x1400435b2  mov     qword ptr [rbp+IoStatus], rax
0x1400435b6  mov     rax, [rax+20h]
0x1400435ba  lea     rcx, [rbp+FileHandle]
0x1400435be  mov     [r11-80h], rcx
0x1400435c2  mov     r12d, r8d
0x1400435c5  mov     byte ptr [rsp+80h+var_50], dl
0x1400435c9  mov     r9d, 100180h
0x1400435cf  mov     [rbp+var_30], rdx
0x1400435d3  mov     r8, rax
0x1400435d6  mov     [rbp+FileHandle], rdx
0x1400435da  mov     rcx, r15
0x1400435dd  mov     [rbp+FileObject], rdx
0x1400435e1  mov     rdx, [r15+20h]
0x1400435e5  mov     [rbp+var_28], rax
0x1400435e9  mov     dword ptr [rsp+80h+var_58], 200068h
0x1400435f1  call    HsmpOpenFileByIdEx
0x1400435f6  mov     ecx, eax
0x1400435f8  mov     edi, eax
0x1400435fa  call    HsmDbgBreakOnStatus
0x1400435ff  mov     r13, [rbp+FileObject]
0x140043603  test    edi, edi
0x140043605  jns     loc_14004368C
0x14004360b  mov     r10, cs:WPP_GLOBAL_Control
0x140043612  lea     rsi, WPP_GLOBAL_Control
0x140043619  cmp     r10, rsi
0x14004361c  jz      loc_140043C56
0x140043622  mov     ecx, [r10+2Ch]
0x140043626  test    cl, 1
0x140043629  jz      loc_140043C56
0x14004362f  mov     r15b, 2
0x140043632  cmp     [r10+29h], r15b
0x140043636  jb      loc_140043C56
0x14004363c  mov     rcx, rbx
0x14004363f  call    HsmpGetStreamSize
0x140043644  mov     edx, 45h ; 'E'
0x140043649  mov     r8, [rbp+arg_20]
0x14004364d  mov     r9, rbx
0x140043650  mov     rcx, [rbp+var_28]
0x140043654  mov     [rsp+80h+var_38], edi
0x140043658  mov     [rsp+80h+var_40], r8
0x14004365d  mov     r8, [rbp+arg_18]
0x140043661  mov     [rsp+80h+var_48], r8
0x140043666  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14004366d  mov     [rsp+80h+var_50], rcx
0x140043672  mov     rcx, [r10+18h]
0x140043676  mov     [rsp+80h+var_58], rax
0x14004367b  mov     eax, [rbx+1Ch]
0x14004367e  mov     [rsp+80h+Flags], eax
0x140043682  call    WPP_SF_qLiiiid
0x140043687  jmp     loc_140043C56
0x14004368c  mov     r9b, 1
0x14004368f  xor     r8d, r8d
0x140043692  mov     rdx, r13
0x140043695  mov     rcx, r15
0x140043698  call    HsmpPrepareForMgmtOperation
0x14004369d  mov     ecx, eax
0x14004369f  mov     edi, eax
0x1400436a1  call    HsmDbgBreakOnStatus
0x1400436a6  test    edi, edi
0x1400436a8  jns     short loc_1400436EC
0x1400436aa  mov     r10, cs:WPP_GLOBAL_Control
0x1400436b1  lea     rsi, WPP_GLOBAL_Control
0x1400436b8  cmp     r10, rsi
0x1400436bb  jz      loc_140043C56
0x1400436c1  mov     eax, [r10+2Ch]
0x1400436c5  test    al, 1
0x1400436c7  jz      loc_140043C56
0x1400436cd  mov     r15b, 2
0x1400436d0  cmp     [r10+29h], r15b
0x1400436d4  jb      loc_140043C56
0x1400436da  mov     rcx, rbx
0x1400436dd  call    HsmpGetStreamSize
0x1400436e2  mov     edx, 46h ; 'F'
0x1400436e7  jmp     loc_140043649
0x1400436ec  mov     dl, 1
0x1400436ee  mov     rcx, rbx
0x1400436f1  call    HsmpAcquireReparseUpdateLock
0x1400436f6  mov     dl, 1
0x1400436f8  mov     rcx, rbx
0x1400436fb  call    HsmpAcquireBitmapLock
0x140043700  mov     rcx, rbx
0x140043703  call    HsmpGetStreamSize
0x140043708  mov     rcx, [rbp+arg_20]
0x14004370c  mov     r8, [rbp+arg_18]
0x140043710  cmp     rcx, rax
0x140043713  jle     short loc_140043722
0x140043715  mov     rcx, rbx
0x140043718  call    HsmpGetStreamSize
0x14004371d  mov     rdx, rax
0x140043720  jmp     short loc_140043726
0x140043722  lea     rdx, [r8+rcx]
0x140043726  mov     [rbp+var_30], rdx
0x14004372a  mov     r15b, 2
0x14004372d  cmp     rdx, r8
0x140043730  jl      loc_140043BBA
0x140043736  mov     rcx, rbx
0x140043739  call    HsmpGetStreamSize
0x14004373e  cmp     r8, rax
0x140043741  jg      loc_140043BBA
0x140043747  and     sil, r15b
0x14004374a  mov     ecx, 0FFFFF000h
0x14004374f  neg     sil
0x140043752  sbb     rax, rax
0x140043755  and     rax, rcx
0x140043758  add     rax, 0FFFh
0x14004375e  test    r8, rax
0x140043761  jnz     loc_140043BBA
0x140043767  test    rdx, rax
0x14004376a  jz      short loc_14004377D
0x14004376c  mov     rcx, rbx
0x14004376f  call    HsmpGetStreamSize
0x140043774  cmp     rdx, rax
0x140043777  jnz     loc_140043BBA
0x14004377d  mov     rdx, r13
0x140043780  mov     rcx, rbx
0x140043783  call    HsmpValidateStreamContextNoLock
0x140043788  mov     ecx, eax
0x14004378a  mov     edi, eax
0x14004378c  call    HsmDbgBreakOnStatus
0x140043791  xor     eax, eax
0x140043793  test    edi, edi
0x140043795  jns     short loc_1400437DA
0x140043797  mov     r10, cs:WPP_GLOBAL_Control
0x14004379e  lea     rsi, WPP_GLOBAL_Control
0x1400437a5  cmp     r10, rsi
0x1400437a8  jz      loc_140043C38
0x1400437ae  mov     eax, [r10+2Ch]
0x1400437b2  test    al, 1
0x1400437b4  jz      loc_140043C38
0x1400437ba  cmp     [r10+29h], r15b
0x1400437be  jb      loc_140043C38
0x1400437c4  mov     rcx, rbx
0x1400437c7  call    HsmpGetStreamSize
0x1400437cc  mov     edx, 49h ; 'I'
0x1400437d1  mov     [rsp+80h+var_38], edi
0x1400437d5  jmp     loc_140043BFE
0x1400437da  lea     rsi, WPP_GLOBAL_Control
0x1400437e1  test    r12d, r12d
0x1400437e4  js      loc_140043AE9
0x1400437ea  mov     byte ptr [rbp+FileObject], al
0x1400437ed  lea     r9, [rbp+var_30]
0x1400437f1  mov     [rbp+var_20], rax
0x1400437f5  lea     r8, [rbp+arg_18]
0x1400437f9  lea     rax, [rbp+var_20]
0x1400437fd  mov     edx, 4244h
0x140043802  mov     [rsp+80h+var_58], rax
0x140043807  mov     rcx, rbx
0x14004380a  lea     rax, [rbp+FileObject]
0x14004380e  mov     qword ptr [rsp+80h+Flags], rax
0x140043813  call    HsmiQueryFileRangeNoLock
0x140043818  mov     ecx, eax
0x14004381a  mov     edi, eax
0x14004381c  call    HsmDbgBreakOnStatus
0x140043821  test    edi, edi
0x140043823  jns     short loc_140043864
0x140043825  mov     r10, cs:WPP_GLOBAL_Control
0x14004382c  lea     rsi, WPP_GLOBAL_Control
0x140043833  cmp     r10, rsi
0x140043836  jz      loc_140043C38
0x14004383c  mov     eax, [r10+2Ch]
0x140043840  test    al, 1
0x140043842  jz      loc_140043C38
0x140043848  cmp     [r10+29h], r15b
0x14004384c  jb      loc_140043C38
0x140043852  mov     rcx, rbx
0x140043855  call    HsmpGetStreamSize
0x14004385a  mov     edx, 4Ah ; 'J'
0x14004385f  jmp     loc_1400437D1
0x140043864  cmp     byte ptr [rbp+FileObject], 0
0x140043868  jz      loc_140043A99
0x14004386e  mov     r9, [rbp+var_30]
0x140043872  cmp     [rbp+var_20], r9
0x140043876  jl      loc_140043A99
0x14004387c  mov     r8, [rbp+arg_18]
0x140043880  mov     edx, 4256h
0x140043885  mov     r12d, [rbx+1Ch]
0x140043889  mov     rcx, rbx
0x14004388c  mov     byte ptr [rsp+80h+Flags], 1
0x140043891  call    HsmiMarkFileRangeNoLock
0x140043896  mov     ecx, eax
0x140043898  mov     edi, eax
0x14004389a  call    HsmDbgBreakOnStatus
0x14004389f  test    edi, edi
0x1400438a1  jns     short loc_1400438E2
0x1400438a3  mov     r10, cs:WPP_GLOBAL_Control
0x1400438aa  lea     rsi, WPP_GLOBAL_Control
0x1400438b1  cmp     r10, rsi
0x1400438b4  jz      loc_140043C38
0x1400438ba  mov     eax, [r10+2Ch]
0x1400438be  test    al, 1
0x1400438c0  jz      loc_140043C38
0x1400438c6  cmp     [r10+29h], r15b
0x1400438ca  jb      loc_140043C38
0x1400438d0  mov     rcx, rbx
0x1400438d3  call    HsmpGetStreamSize
0x1400438d8  mov     edx, 4Ch ; 'L'
0x1400438dd  jmp     loc_1400437D1
0x1400438e2  bt      r12d, 8
0x1400438e7  mov     r12, [rbp+arg_0]
0x1400438eb  jb      short loc_14004396A
0x1400438ed  mov     eax, [rbx+1Ch]
0x1400438f0  mov     ecx, 10100h
0x1400438f5  and     eax, ecx
0x1400438f7  cmp     eax, ecx
0x1400438f9  jnz     short loc_14004396A
0x1400438fb  mov     r9, [rbp+var_28]
0x1400438ff  mov     r8d, 1
0x140043905  mov     rdx, r13
0x140043908  mov     rcx, r12
0x14004390b  call    HsmpSetCompressionNoLock
0x140043910  mov     ecx, eax
0x140043912  mov     edi, eax
0x140043914  call    HsmDbgBreakOnStatus
0x140043919  test    edi, edi
0x14004391b  jns     short loc_140043965
0x14004391d  mov     rcx, cs:WPP_GLOBAL_Control
0x140043924  cmp     rcx, rsi
0x140043927  jz      short loc_140043965
0x140043929  mov     edx, [rcx+2Ch]
0x14004392c  test    dl, 10h
0x14004392f  jz      short loc_140043965
0x140043931  cmp     byte ptr [rcx+29h], 3
0x140043935  jb      short loc_140043965
0x140043937  mov     rax, qword ptr [rbp+IoStatus]
0x14004393b  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x140043942  mov     rcx, [rcx+18h]
0x140043946  mov     edx, 4Dh ; 'M'
0x14004394b  mov     dword ptr [rsp+80h+var_50], edi
0x14004394f  mov     r9, r12
0x140043952  mov     rax, [rax+20h]
0x140043956  mov     [rsp+80h+var_58], rax
0x14004395b  mov     qword ptr [rsp+80h+Flags], rbx
0x140043960  call    WPP_SF_qqqd
0x140043965  btr     dword ptr [rbx+1Ch], 10h
0x14004396a  test    dword ptr [rbx+1Ch], 100h
0x140043971  jz      loc_140043B5B
0x140043977  lea     rax, [rbp+arg_0]
0x14004397b  mov     dword ptr [rbp+arg_0], 0
0x140043982  mov     r9d, 1
0x140043988  mov     qword ptr [rsp+80h+Flags], rax
0x14004398d  mov     r8, r13
0x140043990  mov     rdx, rbx
0x140043993  mov     rcx, r12
0x140043996  call    HsmpCldGetSyncPolicy
0x14004399b  mov     ecx, eax
0x14004399d  mov     edi, eax
0x14004399f  call    HsmDbgBreakOnStatus
0x1400439a4  test    edi, edi
0x1400439a6  jns     short loc_1400439FC
0x1400439a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400439af  cmp     rcx, rsi
0x1400439b2  jz      loc_140043C38
0x1400439b8  mov     eax, [rcx+2Ch]
0x1400439bb  test    al, 1
0x1400439bd  jz      loc_140043C38
0x1400439c3  cmp     [rcx+29h], r15b
0x1400439c7  jb      loc_140043C38
0x1400439cd  mov     rax, [rbp+var_28]
0x1400439d1  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x1400439d8  mov     rcx, [rcx+18h]
0x1400439dc  mov     edx, 4Eh ; 'N'
0x1400439e1  mov     dword ptr [rsp+80h+var_50], edi
0x1400439e5  mov     r9, r12
0x1400439e8  mov     [rsp+80h+var_58], rax
0x1400439ed  mov     qword ptr [rsp+80h+Flags], rbx
0x1400439f2  call    WPP_SF_qqqd
0x1400439f7  jmp     loc_140043C38
0x1400439fc  mov     eax, dword ptr [rbp+arg_0]
0x1400439ff  and     eax, 0Fh
0x140043a02  cmp     al, 3
0x140043a04  jb      loc_140043B5B
0x140043a0a  xorps   xmm0, xmm0
0x140043a0d  xor     dil, dil
0x140043a10  movups  xmmword ptr [rbp+IoStatus], xmm0
0x140043a14  call    cs:__imp_IoGetTopLevelIrp
0x140043a1b  nop     dword ptr [rax+rax+00h]
0x140043a20  test    rax, rax
0x140043a23  jnz     short loc_140043A37
0x140043a25  lea     ecx, [rax+1]; Irp
0x140043a28  call    cs:__imp_IoSetTopLevelIrp
0x140043a2f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
