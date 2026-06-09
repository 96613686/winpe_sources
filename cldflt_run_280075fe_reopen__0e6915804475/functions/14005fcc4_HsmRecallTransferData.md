# HsmRecallTransferData

- ea: `0x14005fcc4`
- end: `0x140060376`
- name: `HsmRecallTransferData`
- size: `1714`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x14006c5d0`

## callees

- `0x140003c50`
- `0x14000abb8`
- `0x140017d68`
- `0x140035a0c`
- `0x140043234`
- `0x140052454`
- `0x140058cbc`
- `0x140059618`
- `0x14005cd20`
- `0x14005e64c`
- `0x14005fcc4`
- `0x1400651c4`
- `0x140067d04`
- `0x140069828`
- `0x14006f16c`
- `0x14006fbd4`
- `0x14007446c`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x1400601d1`
- `ntoskrnl!IoGetTopLevelIrp` at `0x1400601d1`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400601e5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006022b`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1400601e5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14006022b`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140060218`
- `ntoskrnl!CcCoherencyFlushAndPurgeCache` at `0x140060218`
- `ntoskrnl!FsRtlReleaseFile` at `0x14006023a`
- `ntoskrnl!FsRtlReleaseFile` at `0x14006023a`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x1400601f7`
- `ntoskrnl!FsRtlAcquireFileExclusive` at `0x1400601f7`
- `ntoskrnl!ObfDereferenceObject` at `0x140060356`
- `ntoskrnl!ObfDereferenceObject` at `0x140060356`
- `FLTMGR!FltClose` at `0x140060341`
- `FLTMGR!FltClose` at `0x140060341`
- `FLTMGR!FltReleasePushLockEx` at `0x14006032c`
- `FLTMGR!FltReleasePushLockEx` at `0x14006032c`

## pseudocode

```c
__int64 __fastcall HsmRecallTransferData(__int64 a1, __int64 a2, char a3, __int64 a4, ULONG a5, __int64 a6)
{
  _QWORD *v6; // r14
  int v7; // esi
  struct _FLT_INSTANCE *v10; // rdx
  __int64 v11; // r15
  __int64 v12; // r13
  __int64 v13; // rdi
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
  LODWORD(v13) = HsmpOpenFileByIdEx(
                   (const UNICODE_STRING *)a1,
                   v10,
                   v12,
                   0x100180u,
                   Flags,
                   2097256,
                   1,
                   &FileHandle,
                   &FileObject);
  HsmDbgBreakOnStatus((unsigned int)v13);
  if ( (int)v13 < 0 )
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
        v13);
    }
    goto LABEL_75;
  }
  v16 = FileObject;
  LODWORD(v13) = HsmpPrepareForMgmtOperation(v6[2], FileObject, 0, 0);
  HsmDbgBreakOnStatus((unsigned int)v13);
  if ( (int)v13 >= 0 )
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
      LODWORD(v13) = -1073688821;
      HsmDbgBreakOnStatus(3221278475LL);
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
      v13 = (unsigned int)HsmpValidateStreamContextNoLock(a2, v16);
      HsmDbgBreakOnStatus(v13);
      if ( (int)v13 < 0 )
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
      v13 = (unsigned int)HsmiRecallWriteFileNoLock(a2, (__int64)v16, a6, a4, *(_QWORD *)Flagsa);
      HsmDbgBreakOnStatus(v13);
      if ( (int)v13 < 0 )
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
      LODWORD(v13) = HsmiExpandBitmapNoLock(a2, 16964);
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 < 0 )
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
      LODWORD(v13) = HsmiMarkFileRangeNoLock(a2, 16964, a4, v11, 1);
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 < 0 )
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
        LODWORD(v13) = HsmiMarkFileRangeNoLock(a2, 16982, a4, v11, 1);
        HsmDbgBreakOnStatus((unsigned int)v13);
        if ( (int)v13 < 0 )
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
        HsmDbgBreakOnStatus((unsigned int)v29);
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
        LODWORD(v13) = HsmpCldGetSyncPolicy(a1, a2, (_DWORD)v28, 1, (__int64)&a5);
        HsmDbgBreakOnStatus((unsigned int)v13);
        if ( (int)v13 < 0 )
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
              v13);
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
          LODWORD(v13) = IoStatus.Status;
          if ( IoStatus.Status < 0 )
            goto LABEL_74;
        }
      }
      LODWORD(v13) = HsmpRpCommitNoLock(a1, a2, v28, 0, 1);
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 >= 0
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
      v13);
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
      v13);
  }
LABEL_75:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14005fcc4  mov     r11, rsp
0x14005fcc7  mov     [r11+18h], r8b
0x14005fccb  mov     [r11+8], rcx
0x14005fccf  push    rbp
0x14005fcd0  push    rbx
0x14005fcd1  push    rsi
0x14005fcd2  push    rdi
0x14005fcd3  push    r12
0x14005fcd5  push    r13
0x14005fcd7  push    r14
0x14005fcd9  push    r15
0x14005fcdb  mov     rbp, rsp
0x14005fcde  sub     rsp, 78h
0x14005fce2  mov     r14, [rdx+10h]
0x14005fce6  lea     rax, [rbp+FileObject]
0x14005fcea  mov     esi, [rdx+1Ch]
0x14005fced  mov     r12, r9
0x14005fcf0  mov     r15d, [rbp+arg_20]
0x14005fcf4  mov     rbx, rdx
0x14005fcf7  mov     rdx, [rcx+20h]
0x14005fcfb  add     r15, r9
0x14005fcfe  mov     r13, [r14+20h]
0x14005fd02  mov     r9d, 100180h
0x14005fd08  mov     [r11-78h], rax
0x14005fd0c  mov     r8, r13
0x14005fd0f  lea     rax, [rbp+FileHandle]
0x14005fd13  mov     qword ptr [rbp+IoStatus], r14
0x14005fd17  mov     [r11-80h], rax
0x14005fd1b  mov     byte ptr [rsp+78h+var_48], 1
0x14005fd20  mov     [rbp+arg_8], r13
0x14005fd24  mov     [rbp+FileHandle], 0
0x14005fd2c  mov     [rbp+FileObject], 0
0x14005fd34  mov     dword ptr [rsp+78h+var_50], 200068h
0x14005fd3c  call    HsmpOpenFileByIdEx
0x14005fd41  mov     ecx, eax
0x14005fd43  mov     edi, eax
0x14005fd45  call    HsmDbgBreakOnStatus
0x14005fd4a  test    edi, edi
0x14005fd4c  jns     short loc_14005FDC3
0x14005fd4e  mov     r10, cs:WPP_GLOBAL_Control
0x14005fd55  lea     rsi, WPP_GLOBAL_Control
0x14005fd5c  cmp     r10, rsi
0x14005fd5f  jz      loc_140060338
0x14005fd65  mov     ecx, [r10+2Ch]
0x14005fd69  test    cl, 1
0x14005fd6c  jz      loc_140060338
0x14005fd72  mov     r14b, 2
0x14005fd75  cmp     [r10+29h], r14b
0x14005fd79  jb      loc_140060338
0x14005fd7f  mov     rcx, rbx
0x14005fd82  call    HsmpGetStreamSize
0x14005fd87  mov     [rsp+78h+var_30], edi
0x14005fd8b  mov     edx, 5Ch ; '\'
0x14005fd90  mov     [rsp+78h+var_38], r15
0x14005fd95  mov     [rsp+78h+var_40], r12
0x14005fd9a  mov     [rsp+78h+var_48], r13
0x14005fd9f  mov     rcx, [r10+18h]
0x14005fda3  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14005fdaa  mov     [rsp+78h+var_50], rax
0x14005fdaf  mov     r9, rbx
0x14005fdb2  mov     eax, [rbx+1Ch]
0x14005fdb5  mov     [rsp+78h+Flags], eax
0x14005fdb9  call    WPP_SF_qLiiiid
0x14005fdbe  jmp     loc_140060338
0x14005fdc3  mov     r13, [rbp+FileObject]
0x14005fdc7  xor     r9d, r9d
0x14005fdca  mov     rcx, [r14+10h]
0x14005fdce  mov     rdx, r13
0x14005fdd1  xor     r8d, r8d
0x14005fdd4  call    HsmpPrepareForMgmtOperation
0x14005fdd9  mov     ecx, eax
0x14005fddb  mov     edi, eax
0x14005fddd  call    HsmDbgBreakOnStatus
0x14005fde2  test    edi, edi
0x14005fde4  jns     short loc_14005FE3F
0x14005fde6  mov     r10, cs:WPP_GLOBAL_Control
0x14005fded  lea     rsi, WPP_GLOBAL_Control
0x14005fdf4  cmp     r10, rsi
0x14005fdf7  jz      loc_140060338
0x14005fdfd  mov     eax, [r10+2Ch]
0x14005fe01  test    al, 1
0x14005fe03  jz      loc_140060338
0x14005fe09  mov     r14b, 2
0x14005fe0c  cmp     [r10+29h], r14b
0x14005fe10  jb      loc_140060338
0x14005fe16  mov     rcx, rbx
0x14005fe19  call    HsmpGetStreamSize
0x14005fe1e  mov     rcx, [rbp+arg_8]
0x14005fe22  mov     edx, 5Eh ; '^'
0x14005fe27  mov     [rsp+78h+var_30], edi
0x14005fe2b  mov     [rsp+78h+var_38], r15
0x14005fe30  mov     [rsp+78h+var_40], r12
0x14005fe35  mov     [rsp+78h+var_48], rcx
0x14005fe3a  jmp     loc_14005FD9F
0x14005fe3f  mov     dl, 1
0x14005fe41  mov     rcx, rbx
0x14005fe44  call    HsmpAcquireReparseUpdateLock
0x14005fe49  mov     dl, 1
0x14005fe4b  mov     rcx, rbx
0x14005fe4e  call    HsmpAcquireBitmapLock
0x14005fe53  mov     r14b, 2
0x14005fe56  cmp     r15, r12
0x14005fe59  jl      loc_1400602AA
0x14005fe5f  mov     rcx, rbx
0x14005fe62  call    HsmpGetStreamSize
0x14005fe67  cmp     r15, rax
0x14005fe6a  jg      loc_1400602AA
0x14005fe70  and     sil, r14b
0x14005fe73  neg     sil
0x14005fe76  sbb     eax, eax
0x14005fe78  and     eax, 0FFFFF000h
0x14005fe7d  lea     ecx, [rax+0FFFh]
0x14005fe83  test    r12, rcx
0x14005fe86  jnz     loc_1400602AA
0x14005fe8c  mov     esi, [rbp+arg_20]
0x14005fe8f  test    esi, ecx
0x14005fe91  jz      short loc_14005FEA4
0x14005fe93  mov     rcx, rbx
0x14005fe96  call    HsmpGetStreamSize
0x14005fe9b  cmp     r15, rax
0x14005fe9e  jnz     loc_1400602AA
0x14005fea4  mov     rdx, r13
0x14005fea7  mov     rcx, rbx
0x14005feaa  call    HsmpValidateStreamContextNoLock
0x14005feaf  mov     ecx, eax
0x14005feb1  mov     edi, eax
0x14005feb3  call    HsmDbgBreakOnStatus
0x14005feb8  test    edi, edi
0x14005feba  jns     short loc_14005FEFB
0x14005febc  mov     r10, cs:WPP_GLOBAL_Control
0x14005fec3  lea     rsi, WPP_GLOBAL_Control
0x14005feca  cmp     r10, rsi
0x14005fecd  jz      loc_14006031A
0x14005fed3  mov     eax, [r10+2Ch]
0x14005fed7  test    al, 1
0x14005fed9  jz      loc_14006031A
0x14005fedf  cmp     [r10+29h], r14b
0x14005fee3  jb      loc_14006031A
0x14005fee9  mov     rcx, rbx
0x14005feec  call    HsmpGetStreamSize
0x14005fef1  mov     edx, 60h ; '`'
0x14005fef6  jmp     loc_1400602E4
0x14005fefb  mov     r8, [rbp+arg_28]
0x14005feff  mov     r9, r12
0x14005ff02  mov     rdx, r13
0x14005ff05  mov     [rsp+78h+Flags], esi
0x14005ff09  mov     rcx, rbx
0x14005ff0c  call    HsmiRecallWriteFileNoLock
0x14005ff11  mov     ecx, eax
0x14005ff13  mov     edi, eax
0x14005ff15  call    HsmDbgBreakOnStatus
0x14005ff1a  test    edi, edi
0x14005ff1c  jns     short loc_14005FF5D
0x14005ff1e  mov     r10, cs:WPP_GLOBAL_Control
0x14005ff25  lea     rsi, WPP_GLOBAL_Control
0x14005ff2c  cmp     r10, rsi
0x14005ff2f  jz      loc_14006031A
0x14005ff35  mov     eax, [r10+2Ch]
0x14005ff39  test    al, 1
0x14005ff3b  jz      loc_14006031A
0x14005ff41  cmp     [r10+29h], r14b
0x14005ff45  jb      loc_14006031A
0x14005ff4b  mov     rcx, rbx
0x14005ff4e  call    HsmpGetStreamSize
0x14005ff53  mov     edx, 61h ; 'a'
0x14005ff58  jmp     loc_1400602E4
0x14005ff5d  mov     esi, 4244h
0x14005ff62  mov     rcx, rbx
0x14005ff65  mov     edx, esi
0x14005ff67  call    HsmiExpandBitmapNoLock
0x14005ff6c  mov     ecx, eax
0x14005ff6e  mov     edi, eax
0x14005ff70  call    HsmDbgBreakOnStatus
0x14005ff75  test    edi, edi
0x14005ff77  jns     short loc_14005FFB8
0x14005ff79  mov     r10, cs:WPP_GLOBAL_Control
0x14005ff80  lea     rsi, WPP_GLOBAL_Control
0x14005ff87  cmp     r10, rsi
0x14005ff8a  jz      loc_14006031A
0x14005ff90  mov     eax, [r10+2Ch]
0x14005ff94  test    al, 1
0x14005ff96  jz      loc_14006031A
0x14005ff9c  cmp     [r10+29h], r14b
0x14005ffa0  jb      loc_14006031A
0x14005ffa6  mov     rcx, rbx
0x14005ffa9  call    HsmpGetStreamSize
0x14005ffae  mov     edx, 62h ; 'b'
0x14005ffb3  jmp     loc_1400602E4
0x14005ffb8  mov     r9, r15
0x14005ffbb  mov     byte ptr [rsp+78h+Flags], 1
0x14005ffc0  mov     r8, r12
0x14005ffc3  mov     edx, esi
0x14005ffc5  mov     rcx, rbx
0x14005ffc8  call    HsmiMarkFileRangeNoLock
0x14005ffcd  mov     ecx, eax
0x14005ffcf  mov     edi, eax
0x14005ffd1  call    HsmDbgBreakOnStatus
0x14005ffd6  test    edi, edi
0x14005ffd8  jns     short loc_140060019
0x14005ffda  mov     r10, cs:WPP_GLOBAL_Control
0x14005ffe1  lea     rsi, WPP_GLOBAL_Control
0x14005ffe8  cmp     r10, rsi
0x14005ffeb  jz      loc_14006031A
0x14005fff1  mov     eax, [r10+2Ch]
0x14005fff5  test    al, 1
0x14005fff7  jz      loc_14006031A
0x14005fffd  cmp     [r10+29h], r14b
0x140060001  jb      loc_14006031A
0x140060007  mov     rcx, rbx
0x14006000a  call    HsmpGetStreamSize
0x14006000f  mov     edx, 63h ; 'c'
0x140060014  jmp     loc_1400602E4
0x140060019  mov     ecx, [rbx+1Ch]
0x14006001c  mov     r13d, ecx
0x14006001f  and     r13d, 100h
0x140060026  cmp     [rbp+arg_10], 0
0x14006002a  jnz     short loc_140060093
0x14006002c  mov     r9, r15
0x14006002f  mov     byte ptr [rsp+78h+Flags], 1
0x140060034  mov     r8, r12
0x140060037  mov     edx, 4256h
0x14006003c  mov     rcx, rbx
0x14006003f  call    HsmiMarkFileRangeNoLock
0x140060044  mov     ecx, eax
0x140060046  mov     edi, eax
0x140060048  call    HsmDbgBreakOnStatus
0x14006004d  test    edi, edi
0x14006004f  jns     short loc_140060090
0x140060051  mov     r10, cs:WPP_GLOBAL_Control
0x140060058  lea     rsi, WPP_GLOBAL_Control
0x14006005f  cmp     r10, rsi
0x140060062  jz      loc_14006031A
0x140060068  mov     eax, [r10+2Ch]
0x14006006c  test    al, 1
0x14006006e  jz      loc_14006031A
0x140060074  cmp     [r10+29h], r14b
0x140060078  jb      loc_14006031A
0x14006007e  mov     rcx, rbx
0x140060081  call    HsmpGetStreamSize
0x140060086  mov     edx, 64h ; 'd'
0x14006008b  jmp     loc_1400602E4
0x140060090  mov     ecx, [rbx+1Ch]
0x140060093  test    r13d, r13d
0x140060096  lea     rsi, WPP_GLOBAL_Control
0x14006009d  mov     r13, [rbp+FileObject]
0x1400600a1  jnz     loc_140060128
0x1400600a7  mov     edx, 10100h
0x1400600ac  mov     eax, ecx
0x1400600ae  and     eax, edx
0x1400600b0  cmp     eax, edx
0x1400600b2  jnz     short loc_140060128
0x1400600b4  mov     r9, [rbp+arg_8]
0x1400600b8  mov     r8d, 1
0x1400600be  mov     rcx, [rbp+arg_0]
0x1400600c2  mov     rdx, r13
0x1400600c5  call    HsmpSetCompressionNoLock
0x1400600ca  mov     ecx, eax
0x1400600cc  mov     edi, eax
0x1400600ce  call    HsmDbgBreakOnStatus
0x1400600d3  test    edi, edi
0x1400600d5  jns     short loc_140060120
0x1400600d7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400600de  cmp     rcx, rsi
0x1400600e1  jz      short loc_140060120
0x1400600e3  mov     edx, [rcx+2Ch]
0x1400600e6  test    dl, 10h
0x1400600e9  jz      short loc_140060120
0x1400600eb  cmp     byte ptr [rcx+29h], 3
0x1400600ef  jb      short loc_140060120
0x1400600f1  mov     rax, qword ptr [rbp+IoStatus]
0x1400600f5  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x1400600fc  mov     r9, [rbp+arg_0]
0x140060100  mov     edx, 65h ; 'e'
0x140060105  mov     rcx, [rcx+18h]
0x140060109  mov     dword ptr [rsp+78h+var_48], edi
0x14006010d  mov     rax, [rax+20h]
0x140060111  mov     [rsp+78h+var_50], rax
0x140060116  mov     qword ptr [rsp+78h+Flags], rbx
0x14006011b  call    WPP_SF_qqqd
0x140060120  btr     dword ptr [rbx+1Ch], 10h
0x140060125  mov     ecx, [rbx+1Ch]
0x140060128  bt      ecx, 8
0x14006012c  jnb     loc_140060251
0x140060132  mov     rcx, [rbp+arg_0]
0x140060136  lea     rax, [rbp+arg_20]
0x14006013a  mov     r9d, 1
0x140060140  mov     qword ptr [rsp+78h+Flags], rax
0x140060145  mov     r8, r13
0x140060148  mov     [rbp+arg_20], 0
0x14006014f  mov     rdx, rbx
0x140060152  call    HsmpCldGetSyncPolicy
0x140060157  mov     ecx, eax
0x140060159  mov     edi, eax
0x14006015b  call    HsmDbgBreakOnStatus
0x140060160  test    edi, edi
0x140060162  jns     short loc_1400601B9
0x140060164  mov     rcx, cs:WPP_GLOBAL_Control
0x14006016b  cmp     rcx, rsi
0x14006016e  jz      loc_14006031A
0x140060174  mov     eax, [rcx+2Ch]
  ... truncated ...
```
