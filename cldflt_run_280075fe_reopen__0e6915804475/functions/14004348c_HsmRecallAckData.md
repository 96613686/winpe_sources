# HsmRecallAckData

- ea: `0x14004348c`
- end: `0x140043ba4`
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
- `0x140017d68`
- `0x140043234`
- `0x14004348c`
- `0x140052454`
- `0x140058cbc`
- `0x140059618`
- `0x14005cd20`
- `0x14005e64c`
- `0x1400651c4`
- `0x140067d04`
- `0x140069828`
- `0x14006f16c`
- `0x1400702c4`
- `0x14007446c`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140043924`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140043924`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140043938`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004397e`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140043938`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14004397e`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004396b`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x14004396b`
- `ntoskrnl!FsRtlReleaseFile` at `0x14004398d`
- `ntoskrnl!FsRtlReleaseFile` at `0x14004398d`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x14004394a`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x14004394a`
- `ntoskrnl!ObfDereferenceObject` at `0x140043b83`
- `ntoskrnl!ObfDereferenceObject` at `0x140043b83`
- `FLTMGR!FltClose` at `0x140043b6f`
- `FLTMGR!FltClose` at `0x140043b6f`
- `FLTMGR!FltReleasePushLockEx` at `0x140043b5a`
- `FLTMGR!FltReleasePushLockEx` at `0x140043b5a`

## pseudocode

```c
__int64 HsmRecallAckData(__int64 a1, __int64 a2, int a3, ...)
{
  int v4; // esi
  __int64 v6; // rax
  struct _FLT_INSTANCE *v8; // rdx
  int FileRangeNoLock; // edi
  __int64 v10; // r9
  PFILE_OBJECT v11; // r13
  char StreamSize; // al
  __int64 v13; // r10
  int v14; // edx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // r8
  __int64 v19; // rdx
  __int64 v20; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // rax
  __int64 v25; // rdx
  char v26; // al
  __int64 v27; // r10
  int v28; // edx
  int v29; // r12d
  bool v30; // cf
  __int64 v31; // r12
  int v32; // edi
  char v33; // di
  char v34; // al
  __int64 v35; // r10
  int v36; // edx
  __int64 Flags; // [rsp+20h] [rbp-60h]
  __int64 v39; // [rsp+50h] [rbp-30h] BYREF
  __int64 v40; // [rsp+58h] [rbp-28h]
  __int64 v41; // [rsp+60h] [rbp-20h] BYREF
  HANDLE FileHandle; // [rsp+68h] [rbp-18h] BYREF
  struct _IO_STATUS_BLOCK IoStatus; // [rsp+70h] [rbp-10h] BYREF
  __int64 v44; // [rsp+C0h] [rbp+40h] BYREF
  PFILE_OBJECT FileObject; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v46; // [rsp+D8h] [rbp+58h] BYREF
  va_list va; // [rsp+D8h] [rbp+58h]
  __int64 v48; // [rsp+E0h] [rbp+60h]
  va_list va1; // [rsp+E8h] [rbp+68h] BYREF

  va_start(va1, a3);
  va_start(va, a3);
  v46 = va_arg(va1, _QWORD);
  v48 = va_arg(va1, _QWORD);
  v44 = a1;
  v4 = *(_DWORD *)(a2 + 28);
  IoStatus.Pointer = *(PVOID *)(a2 + 16);
  v6 = *((_QWORD *)IoStatus.Pointer + 4);
  v39 = 0;
  FileHandle = 0;
  FileObject = 0;
  v8 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v40 = v6;
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
  HsmDbgBreakOnStatus((unsigned int)FileRangeNoLock);
  v11 = FileObject;
  if ( FileRangeNoLock < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a2);
      v14 = 69;
LABEL_6:
      WPP_SF_qLiiiid(
        *(_QWORD *)(v13 + 24),
        v14,
        (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        StreamSize,
        v40,
        v46,
        v48,
        FileRangeNoLock);
      goto LABEL_82;
    }
    goto LABEL_82;
  }
  LOBYTE(v10) = 1;
  FileRangeNoLock = HsmpPrepareForMgmtOperation(a1, FileObject, 0, v10);
  HsmDbgBreakOnStatus((unsigned int)FileRangeNoLock);
  if ( FileRangeNoLock >= 0 )
  {
    LOBYTE(v15) = 1;
    HsmpAcquireReparseUpdateLock(a2, v15);
    LOBYTE(v16) = 1;
    HsmpAcquireBitmapLock(a2, v16);
    v17 = HsmpGetStreamSize(a2);
    v18 = v46;
    if ( v48 <= v17 )
      v19 = v46 + v48;
    else
      v19 = HsmpGetStreamSize(a2);
    v39 = v19;
    if ( v19 < v18
      || (v20 = HsmpGetStreamSize(a2), v22 > v20)
      || (v23 = (-(__int64)((v4 & 2) != 0) & 0xFFFFF000LL) + 4095, (v23 & v22) != 0)
      || (v23 & v21) != 0 && (v24 = HsmpGetStreamSize(a2), v25 != v24) )
    {
      FileRangeNoLock = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_81;
      }
      v34 = HsmpGetStreamSize(a2);
      v36 = 72;
    }
    else
    {
      FileRangeNoLock = HsmpValidateStreamContextNoLock(a2, v11);
      HsmDbgBreakOnStatus((unsigned int)FileRangeNoLock);
      if ( FileRangeNoLock < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_81;
        }
        v26 = HsmpGetStreamSize(a2);
        v28 = 73;
        goto LABEL_25;
      }
      if ( a3 < 0 )
      {
        if ( a3 == -1073688818 )
        {
          FileRangeNoLock = HsmiMarkFileRangeNoLock(a2, 16964, v46, v39, 0);
          HsmDbgBreakOnStatus((unsigned int)FileRangeNoLock);
          if ( FileRangeNoLock < 0 )
          {
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              goto LABEL_81;
            }
            v26 = HsmpGetStreamSize(a2);
            v28 = 79;
LABEL_25:
            WPP_SF_qLiiiid(
              *(_QWORD *)(v27 + 24),
              v28,
              (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
              a2,
              *(_DWORD *)(a2 + 28),
              v26,
              v40,
              v46,
              v39,
              FileRangeNoLock);
LABEL_81:
            HsmpReleaseBitmapLock(a2);
            FltReleasePushLockEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
            goto LABEL_82;
          }
        }
        v31 = v44;
LABEL_71:
        FileRangeNoLock = HsmpRpCommitNoLock(v31, a2, v11, 0, 1);
        HsmDbgBreakOnStatus((unsigned int)FileRangeNoLock);
        if ( FileRangeNoLock >= 0
          || WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_81;
        }
        v26 = HsmpGetStreamSize(a2);
        v28 = 80;
        goto LABEL_25;
      }
      LOBYTE(FileObject) = 0;
      v41 = 0;
      FileRangeNoLock = HsmiQueryFileRangeNoLock(
                          a2,
                          16964,
                          (unsigned int)va,
                          (unsigned int)&v39,
                          (__int64)&FileObject,
                          (__int64)&v41);
      HsmDbgBreakOnStatus((unsigned int)FileRangeNoLock);
      if ( FileRangeNoLock < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_81;
        }
        v26 = HsmpGetStreamSize(a2);
        v28 = 74;
        goto LABEL_25;
      }
      if ( (_BYTE)FileObject && v41 >= v39 )
      {
        v29 = *(_DWORD *)(a2 + 28);
        FileRangeNoLock = HsmiMarkFileRangeNoLock(a2, 16982, v46, v39, 1);
        HsmDbgBreakOnStatus((unsigned int)FileRangeNoLock);
        if ( FileRangeNoLock < 0 )
        {
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_81;
          }
          v26 = HsmpGetStreamSize(a2);
          v28 = 76;
          goto LABEL_25;
        }
        v30 = (v29 & 0x100) != 0;
        v31 = v44;
        if ( !v30 && (*(_DWORD *)(a2 + 28) & 0x10100) == 0x10100 )
        {
          v32 = HsmpSetCompressionNoLock(v44, v11, 1, v40);
          HsmDbgBreakOnStatus((unsigned int)v32);
          if ( v32 < 0
            && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
          {
            WPP_SF_qqqd(
              WPP_GLOBAL_Control->AttachedDevice,
              77,
              WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
              v31,
              a2,
              *((_QWORD *)IoStatus.Pointer + 4),
              v32);
          }
          *(_DWORD *)(a2 + 28) &= ~0x10000u;
        }
        if ( (*(_DWORD *)(a2 + 28) & 0x100) != 0 )
        {
          LODWORD(v44) = 0;
          FileRangeNoLock = HsmpCldGetSyncPolicy(v31, a2, (_DWORD)v11, 1, (__int64)&v44);
          HsmDbgBreakOnStatus((unsigned int)FileRangeNoLock);
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
                v31,
                a2,
                v40,
                FileRangeNoLock);
            }
            goto LABEL_81;
          }
          if ( ((unsigned __int8)v44 & 0xFu) >= 3 )
          {
            v33 = 0;
            IoStatus = 0;
            if ( !IoGetTopLevelIrp() )
            {
              IoSetTopLevelIrp((PIRP)1);
              v33 = 1;
            }
            FsRtlAcquireFileExclusive(v11);
            CcCoherencyFlushAndPurgeCache(v11->SectionObjectPointer, 0, 0, &IoStatus, 0);
            if ( v33 )
              IoSetTopLevelIrp(0);
            FsRtlReleaseFile(v11);
            FileRangeNoLock = IoStatus.Status;
            if ( IoStatus.Status < 0 )
              goto LABEL_81;
          }
        }
        goto LABEL_71;
      }
      FileRangeNoLock = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_81;
      }
      v34 = HsmpGetStreamSize(a2);
      v36 = 75;
    }
    WPP_SF_qLiiiid(
      *(_QWORD *)(v35 + 24),
      v36,
      (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v34,
      v40,
      v46,
      v39,
      11);
    goto LABEL_81;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    StreamSize = HsmpGetStreamSize(a2);
    v14 = 70;
    goto LABEL_6;
  }
LABEL_82:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v11 )
    ObfDereferenceObject(v11);
  return (unsigned int)FileRangeNoLock;
}

```

## disassembly

```asm
0x14004348c  mov     r11, rsp
0x14004348f  mov     [r11+20h], r9
0x140043493  mov     [r11+8], rcx
0x140043497  push    rbp
0x140043498  push    rbx
0x140043499  push    rsi
0x14004349a  push    rdi
0x14004349b  push    r12
0x14004349d  push    r13
0x14004349f  push    r15
0x1400434a1  mov     rbp, rsp
0x1400434a4  sub     rsp, 80h
0x1400434ab  mov     rax, [rdx+10h]
0x1400434af  mov     r15, rcx
0x1400434b2  mov     esi, [rdx+1Ch]
0x1400434b5  lea     rcx, [rbp+FileObject]
0x1400434b9  mov     [r11-78h], rcx
0x1400434bd  mov     rbx, rdx
0x1400434c0  xor     edx, edx
0x1400434c2  mov     qword ptr [rbp+IoStatus], rax
0x1400434c6  mov     rax, [rax+20h]
0x1400434ca  lea     rcx, [rbp+FileHandle]
0x1400434ce  mov     [r11-80h], rcx
0x1400434d2  mov     r12d, r8d
0x1400434d5  mov     byte ptr [rsp+80h+var_50], dl
0x1400434d9  mov     r9d, 100180h
0x1400434df  mov     [rbp+var_30], rdx
0x1400434e3  mov     r8, rax
0x1400434e6  mov     [rbp+FileHandle], rdx
0x1400434ea  mov     rcx, r15
0x1400434ed  mov     [rbp+FileObject], rdx
0x1400434f1  mov     rdx, [r15+20h]
0x1400434f5  mov     [rbp+var_28], rax
0x1400434f9  mov     dword ptr [rsp+80h+var_58], 200068h
0x140043501  call    HsmpOpenFileByIdEx
0x140043506  mov     ecx, eax
0x140043508  mov     edi, eax
0x14004350a  call    HsmDbgBreakOnStatus
0x14004350f  mov     r13, [rbp+FileObject]
0x140043513  test    edi, edi
0x140043515  jns     loc_14004359C
0x14004351b  mov     r10, cs:WPP_GLOBAL_Control
0x140043522  lea     rsi, WPP_GLOBAL_Control
0x140043529  cmp     r10, rsi
0x14004352c  jz      loc_140043B66
0x140043532  mov     ecx, [r10+2Ch]
0x140043536  test    cl, 1
0x140043539  jz      loc_140043B66
0x14004353f  mov     r15b, 2
0x140043542  cmp     [r10+29h], r15b
0x140043546  jb      loc_140043B66
0x14004354c  mov     rcx, rbx
0x14004354f  call    HsmpGetStreamSize
0x140043554  mov     edx, 45h ; 'E'
0x140043559  mov     r8, [rbp+arg_20]
0x14004355d  mov     r9, rbx
0x140043560  mov     rcx, [rbp+var_28]
0x140043564  mov     [rsp+80h+var_38], edi
0x140043568  mov     [rsp+80h+var_40], r8
0x14004356d  mov     r8, [rbp+arg_18]
0x140043571  mov     [rsp+80h+var_48], r8
0x140043576  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14004357d  mov     [rsp+80h+var_50], rcx
0x140043582  mov     rcx, [r10+18h]
0x140043586  mov     [rsp+80h+var_58], rax
0x14004358b  mov     eax, [rbx+1Ch]
0x14004358e  mov     [rsp+80h+Flags], eax
0x140043592  call    WPP_SF_qLiiiid
0x140043597  jmp     loc_140043B66
0x14004359c  mov     r9b, 1
0x14004359f  xor     r8d, r8d
0x1400435a2  mov     rdx, r13
0x1400435a5  mov     rcx, r15
0x1400435a8  call    HsmpPrepareForMgmtOperation
0x1400435ad  mov     ecx, eax
0x1400435af  mov     edi, eax
0x1400435b1  call    HsmDbgBreakOnStatus
0x1400435b6  test    edi, edi
0x1400435b8  jns     short loc_1400435FC
0x1400435ba  mov     r10, cs:WPP_GLOBAL_Control
0x1400435c1  lea     rsi, WPP_GLOBAL_Control
0x1400435c8  cmp     r10, rsi
0x1400435cb  jz      loc_140043B66
0x1400435d1  mov     eax, [r10+2Ch]
0x1400435d5  test    al, 1
0x1400435d7  jz      loc_140043B66
0x1400435dd  mov     r15b, 2
0x1400435e0  cmp     [r10+29h], r15b
0x1400435e4  jb      loc_140043B66
0x1400435ea  mov     rcx, rbx
0x1400435ed  call    HsmpGetStreamSize
0x1400435f2  mov     edx, 46h ; 'F'
0x1400435f7  jmp     loc_140043559
0x1400435fc  mov     dl, 1
0x1400435fe  mov     rcx, rbx
0x140043601  call    HsmpAcquireReparseUpdateLock
0x140043606  mov     dl, 1
0x140043608  mov     rcx, rbx
0x14004360b  call    HsmpAcquireBitmapLock
0x140043610  mov     rcx, rbx
0x140043613  call    HsmpGetStreamSize
0x140043618  mov     rcx, [rbp+arg_20]
0x14004361c  mov     r8, [rbp+arg_18]
0x140043620  cmp     rcx, rax
0x140043623  jle     short loc_140043632
0x140043625  mov     rcx, rbx
0x140043628  call    HsmpGetStreamSize
0x14004362d  mov     rdx, rax
0x140043630  jmp     short loc_140043636
0x140043632  lea     rdx, [r8+rcx]
0x140043636  mov     [rbp+var_30], rdx
0x14004363a  mov     r15b, 2
0x14004363d  cmp     rdx, r8
0x140043640  jl      loc_140043ACA
0x140043646  mov     rcx, rbx
0x140043649  call    HsmpGetStreamSize
0x14004364e  cmp     r8, rax
0x140043651  jg      loc_140043ACA
0x140043657  and     sil, r15b
0x14004365a  mov     ecx, 0FFFFF000h
0x14004365f  neg     sil
0x140043662  sbb     rax, rax
0x140043665  and     rax, rcx
0x140043668  add     rax, 0FFFh
0x14004366e  test    r8, rax
0x140043671  jnz     loc_140043ACA
0x140043677  test    rdx, rax
0x14004367a  jz      short loc_14004368D
0x14004367c  mov     rcx, rbx
0x14004367f  call    HsmpGetStreamSize
0x140043684  cmp     rdx, rax
0x140043687  jnz     loc_140043ACA
0x14004368d  mov     rdx, r13
0x140043690  mov     rcx, rbx
0x140043693  call    HsmpValidateStreamContextNoLock
0x140043698  mov     ecx, eax
0x14004369a  mov     edi, eax
0x14004369c  call    HsmDbgBreakOnStatus
0x1400436a1  xor     eax, eax
0x1400436a3  test    edi, edi
0x1400436a5  jns     short loc_1400436EA
0x1400436a7  mov     r10, cs:WPP_GLOBAL_Control
0x1400436ae  lea     rsi, WPP_GLOBAL_Control
0x1400436b5  cmp     r10, rsi
0x1400436b8  jz      loc_140043B48
0x1400436be  mov     eax, [r10+2Ch]
0x1400436c2  test    al, 1
0x1400436c4  jz      loc_140043B48
0x1400436ca  cmp     [r10+29h], r15b
0x1400436ce  jb      loc_140043B48
0x1400436d4  mov     rcx, rbx
0x1400436d7  call    HsmpGetStreamSize
0x1400436dc  mov     edx, 49h ; 'I'
0x1400436e1  mov     [rsp+80h+var_38], edi
0x1400436e5  jmp     loc_140043B0E
0x1400436ea  lea     rsi, WPP_GLOBAL_Control
0x1400436f1  test    r12d, r12d
0x1400436f4  js      loc_1400439F9
0x1400436fa  mov     byte ptr [rbp+FileObject], al
0x1400436fd  lea     r9, [rbp+var_30]
0x140043701  mov     [rbp+var_20], rax
0x140043705  lea     r8, [rbp+arg_18]
0x140043709  lea     rax, [rbp+var_20]
0x14004370d  mov     edx, 4244h
0x140043712  mov     [rsp+80h+var_58], rax
0x140043717  mov     rcx, rbx
0x14004371a  lea     rax, [rbp+FileObject]
0x14004371e  mov     qword ptr [rsp+80h+Flags], rax
0x140043723  call    HsmiQueryFileRangeNoLock
0x140043728  mov     ecx, eax
0x14004372a  mov     edi, eax
0x14004372c  call    HsmDbgBreakOnStatus
0x140043731  test    edi, edi
0x140043733  jns     short loc_140043774
0x140043735  mov     r10, cs:WPP_GLOBAL_Control
0x14004373c  lea     rsi, WPP_GLOBAL_Control
0x140043743  cmp     r10, rsi
0x140043746  jz      loc_140043B48
0x14004374c  mov     eax, [r10+2Ch]
0x140043750  test    al, 1
0x140043752  jz      loc_140043B48
0x140043758  cmp     [r10+29h], r15b
0x14004375c  jb      loc_140043B48
0x140043762  mov     rcx, rbx
0x140043765  call    HsmpGetStreamSize
0x14004376a  mov     edx, 4Ah ; 'J'
0x14004376f  jmp     loc_1400436E1
0x140043774  cmp     byte ptr [rbp+FileObject], 0
0x140043778  jz      loc_1400439A9
0x14004377e  mov     r9, [rbp+var_30]
0x140043782  cmp     [rbp+var_20], r9
0x140043786  jl      loc_1400439A9
0x14004378c  mov     r8, [rbp+arg_18]
0x140043790  mov     edx, 4256h
0x140043795  mov     r12d, [rbx+1Ch]
0x140043799  mov     rcx, rbx
0x14004379c  mov     byte ptr [rsp+80h+Flags], 1
0x1400437a1  call    HsmiMarkFileRangeNoLock
0x1400437a6  mov     ecx, eax
0x1400437a8  mov     edi, eax
0x1400437aa  call    HsmDbgBreakOnStatus
0x1400437af  test    edi, edi
0x1400437b1  jns     short loc_1400437F2
0x1400437b3  mov     r10, cs:WPP_GLOBAL_Control
0x1400437ba  lea     rsi, WPP_GLOBAL_Control
0x1400437c1  cmp     r10, rsi
0x1400437c4  jz      loc_140043B48
0x1400437ca  mov     eax, [r10+2Ch]
0x1400437ce  test    al, 1
0x1400437d0  jz      loc_140043B48
0x1400437d6  cmp     [r10+29h], r15b
0x1400437da  jb      loc_140043B48
0x1400437e0  mov     rcx, rbx
0x1400437e3  call    HsmpGetStreamSize
0x1400437e8  mov     edx, 4Ch ; 'L'
0x1400437ed  jmp     loc_1400436E1
0x1400437f2  bt      r12d, 8
0x1400437f7  mov     r12, [rbp+arg_0]
0x1400437fb  jb      short loc_14004387A
0x1400437fd  mov     eax, [rbx+1Ch]
0x140043800  mov     ecx, 10100h
0x140043805  and     eax, ecx
0x140043807  cmp     eax, ecx
0x140043809  jnz     short loc_14004387A
0x14004380b  mov     r9, [rbp+var_28]
0x14004380f  mov     r8d, 1
0x140043815  mov     rdx, r13
0x140043818  mov     rcx, r12
0x14004381b  call    HsmpSetCompressionNoLock
0x140043820  mov     ecx, eax
0x140043822  mov     edi, eax
0x140043824  call    HsmDbgBreakOnStatus
0x140043829  test    edi, edi
0x14004382b  jns     short loc_140043875
0x14004382d  mov     rcx, cs:WPP_GLOBAL_Control
0x140043834  cmp     rcx, rsi
0x140043837  jz      short loc_140043875
0x140043839  mov     edx, [rcx+2Ch]
0x14004383c  test    dl, 10h
0x14004383f  jz      short loc_140043875
0x140043841  cmp     byte ptr [rcx+29h], 3
0x140043845  jb      short loc_140043875
0x140043847  mov     rax, qword ptr [rbp+IoStatus]
0x14004384b  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x140043852  mov     rcx, [rcx+18h]
0x140043856  mov     edx, 4Dh ; 'M'
0x14004385b  mov     dword ptr [rsp+80h+var_50], edi
0x14004385f  mov     r9, r12
0x140043862  mov     rax, [rax+20h]
0x140043866  mov     [rsp+80h+var_58], rax
0x14004386b  mov     qword ptr [rsp+80h+Flags], rbx
0x140043870  call    WPP_SF_qqqd
0x140043875  btr     dword ptr [rbx+1Ch], 10h
0x14004387a  test    dword ptr [rbx+1Ch], 100h
0x140043881  jz      loc_140043A6B
0x140043887  lea     rax, [rbp+arg_0]
0x14004388b  mov     dword ptr [rbp+arg_0], 0
0x140043892  mov     r9d, 1
0x140043898  mov     qword ptr [rsp+80h+Flags], rax
0x14004389d  mov     r8, r13
0x1400438a0  mov     rdx, rbx
0x1400438a3  mov     rcx, r12
0x1400438a6  call    HsmpCldGetSyncPolicy
0x1400438ab  mov     ecx, eax
0x1400438ad  mov     edi, eax
0x1400438af  call    HsmDbgBreakOnStatus
0x1400438b4  test    edi, edi
0x1400438b6  jns     short loc_14004390C
0x1400438b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400438bf  cmp     rcx, rsi
0x1400438c2  jz      loc_140043B48
0x1400438c8  mov     eax, [rcx+2Ch]
0x1400438cb  test    al, 1
0x1400438cd  jz      loc_140043B48
0x1400438d3  cmp     [rcx+29h], r15b
0x1400438d7  jb      loc_140043B48
0x1400438dd  mov     rax, [rbp+var_28]
0x1400438e1  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x1400438e8  mov     rcx, [rcx+18h]
0x1400438ec  mov     edx, 4Eh ; 'N'
0x1400438f1  mov     dword ptr [rsp+80h+var_50], edi
0x1400438f5  mov     r9, r12
0x1400438f8  mov     [rsp+80h+var_58], rax
0x1400438fd  mov     qword ptr [rsp+80h+Flags], rbx
0x140043902  call    WPP_SF_qqqd
0x140043907  jmp     loc_140043B48
0x14004390c  mov     eax, dword ptr [rbp+arg_0]
0x14004390f  and     eax, 0Fh
0x140043912  cmp     al, 3
0x140043914  jb      loc_140043A6B
0x14004391a  xorps   xmm0, xmm0
0x14004391d  xor     dil, dil
0x140043920  movups  xmmword ptr [rbp+IoStatus], xmm0
0x140043924  call    cs:__imp_IoGetTopLevelIrp
0x14004392b  nop     dword ptr [rax+rax+00h]
0x140043930  test    rax, rax
0x140043933  jnz     short loc_140043947
0x140043935  lea     ecx, [rax+1]; Irp
0x140043938  call    cs:__imp_IoSetTopLevelIrp
0x14004393f  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
