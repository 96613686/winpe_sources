# HsmRecallRetrieveData

- ea: `0x14006f558`
- end: `0x14006fcee`
- name: `HsmRecallRetrieveData`
- size: `1942`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID Buffer)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x14006f2c8`

## callees

- `0x140003c50`
- `0x140017de8`
- `0x14001e300`
- `0x140058ddc`
- `0x140059738`
- `0x14005e76c`
- `0x140069948`
- `0x14006f558`
- `0x1400704ac`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14006f8c2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14006f8c2`
- `ntoskrnl!IoFreeMdl` at `0x14006f7e3`
- `ntoskrnl!IoFreeMdl` at `0x14006f7e3`
- `ntoskrnl!IoAllocateMdl` at `0x14006f85c`
- `ntoskrnl!IoAllocateMdl` at `0x14006f85c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006f829`
- `ntoskrnl!ObfDereferenceObject` at `0x14006f829`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f7fc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f7fc`
- `ntoskrnl!ExAllocatePool2` at `0x14006f720`
- `ntoskrnl!ExAllocatePool2` at `0x14006f720`
- `FLTMGR!FltReadFileEx` at `0x14006fbda`
- `FLTMGR!FltReadFileEx` at `0x14006fbda`
- `FLTMGR!FltReadFile` at `0x14006fad0`
- `FLTMGR!FltReadFile` at `0x14006fad0`
- `FLTMGR!FltClose` at `0x14006f815`
- `FLTMGR!FltClose` at `0x14006f815`
- `FLTMGR!FltReleasePushLockEx` at `0x14006f7cb`
- `FLTMGR!FltReleasePushLockEx` at `0x14006f7cb`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f691`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f6af`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f691`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f6af`

## pseudocode

```c
__int64 __fastcall HsmRecallRetrieveData(__int64 a1, __int64 a2, union _LARGE_INTEGER a3, ULONG *a4, char *Buffer)
{
  __int64 v5; // rax
  __int64 v8; // rdx
  __int64 v9; // r12
  __int64 v10; // rax
  int Range; // edi
  PFILE_OBJECT v12; // r13
  char StreamSize; // al
  __int64 v14; // r10
  ULONG v15; // esi
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  void *Pool2; // rax
  char v22; // al
  __int64 v23; // r10
  int v24; // edx
  PVOID v25; // r12
  struct _MDL *v27; // rax
  char v28; // al
  __int64 v29; // r10
  int v30; // edx
  __int64 v31; // rcx
  union _LARGE_INTEGER v32; // r15
  union _LARGE_INTEGER v33; // rax
  ULONG v34; // r12d
  char *v35; // r13
  char v36; // al
  char LowPart; // r8
  __int64 v38; // r10
  int v39; // edx
  char v40; // r9
  DWORD v41; // r15d
  char v42; // al
  __int64 v43; // r10
  char CallbackContext; // [rsp+40h] [rbp-51h]
  char v45; // [rsp+48h] [rbp-49h]
  char v46; // [rsp+48h] [rbp-49h]
  __int64 v47; // [rsp+60h] [rbp-31h] BYREF
  PVOID P; // [rsp+68h] [rbp-29h]
  union _LARGE_INTEGER ByteOffset; // [rsp+70h] [rbp-21h] BYREF
  __int64 v50; // [rsp+78h] [rbp-19h] BYREF
  PFILE_OBJECT FileObject; // [rsp+80h] [rbp-11h]
  PMDL Mdl; // [rsp+88h] [rbp-9h]
  __int64 v53; // [rsp+90h] [rbp-1h]
  HANDLE FileHandle; // [rsp+98h] [rbp+7h]
  bool v56; // [rsp+F8h] [rbp+67h] BYREF
  union _LARGE_INTEGER v57; // [rsp+100h] [rbp+6Fh] BYREF
  ULONG BytesRead; // [rsp+108h] [rbp+77h] BYREF

  v57 = a3;
  v5 = *(_QWORD *)(a2 + 16);
  FileHandle = 0;
  v8 = *(_QWORD *)(a1 + 32);
  Mdl = 0;
  v9 = *(_QWORD *)(v5 + 32);
  v10 = *a4;
  v53 = v9;
  v47 = a3.QuadPart + v10;
  ByteOffset.QuadPart = 0;
  BytesRead = 0;
  v56 = 0;
  v50 = 0;
  Range = HsmpOpenFileByIdEx(a1, v8, v9, 1048704);
  HsmDbgBreakOnStatus(Range);
  v12 = 0;
  FileObject = 0;
  if ( Range < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a2);
      WPP_SF_qLiiiid(
        *(_QWORD *)(v14 + 24),
        81,
        (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        StreamSize,
        v9,
        v57.QuadPart,
        v47,
        Range);
    }
    *a4 = 0;
    goto LABEL_30;
  }
  v15 = 0;
  v16 = *(_QWORD *)(a2 + 16) + 24LL;
  P = 0;
  Mdl = 0;
  FltAcquirePushLockSharedEx(v16, 0);
  v17 = *(_QWORD *)(a2 + 160);
  if ( v17 )
    FltAcquirePushLockSharedEx(v17 + 40, 0);
  if ( v47 < v57.QuadPart
    || (v18 = HsmpGetStreamSize(a2), v20 > v18)
    || (v20 & 0xFFF) != 0
    || (v19 & 0xFFF) != 0 && v19 < v18 )
  {
    Range = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v42 = HsmpGetStreamSize(a2);
      WPP_SF_qLiiiid(
        *(_QWORD *)(v43 + 24),
        82,
        (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        v42,
        v9,
        v57.QuadPart,
        v47,
        11);
      v25 = 0;
      goto LABEL_25;
    }
    goto LABEL_24;
  }
  if ( v19 >= v18 )
  {
    LOWORD(v19) = v18;
    v47 = v18;
  }
  if ( (v19 & 0xFFF) != 0 )
  {
    Pool2 = (void *)ExAllocatePool2(64, 4096, 2001892168);
    P = Pool2;
    if ( !Pool2 )
    {
      Range = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_23;
      }
      v22 = HsmpGetStreamSize(a2);
      v24 = 83;
LABEL_22:
      WPP_SF_qLiiiid(
        *(_QWORD *)(v23 + 24),
        v24,
        (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        v22,
        v9,
        v57.QuadPart,
        v47,
        154);
LABEL_23:
      v15 = 0;
      goto LABEL_24;
    }
    v27 = IoAllocateMdl(Pool2, 0x1000u, 0, 0, 0);
    Mdl = v27;
    if ( !v27 )
    {
      Range = -1073741670;
      HsmDbgBreakOnStatus(-1073741670);
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        goto LABEL_23;
      }
      v22 = HsmpGetStreamSize(a2);
      v24 = 84;
      goto LABEL_22;
    }
    MmBuildMdlForNonPagedPool(v27);
  }
  Range = HsmpValidateStreamContextNoLock(a2, 0);
  HsmDbgBreakOnStatus(Range);
  if ( Range < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_24;
    }
    v28 = HsmpGetStreamSize(a2);
    v30 = 85;
    goto LABEL_46;
  }
  v31 = *(_QWORD *)(*(_QWORD *)(a2 + 160) + 56LL);
  if ( v31 )
  {
    Range = HsmpBitmapQueryRange(v31, (unsigned int)&v57, (unsigned int)&v47, (unsigned int)&v56, (__int64)&v50);
    HsmDbgBreakOnStatus(Range);
  }
  else
  {
    v56 = (*(_DWORD *)(a2 + 28) & 0x40) != 0;
    Range = 0;
    v50 = v47;
  }
  HsmDbgBreakOnStatus(Range);
  if ( Range < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_24;
    }
    v28 = HsmpGetStreamSize(a2);
    v30 = 88;
LABEL_46:
    v45 = Range;
LABEL_47:
    WPP_SF_qLiiiid(
      *(_QWORD *)(v29 + 24),
      v30,
      (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v28,
      v9,
      v57.QuadPart,
      v47,
      v45);
    goto LABEL_24;
  }
  if ( !v56 )
  {
    Range = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_24;
    }
    v28 = HsmpGetStreamSize(a2);
    v30 = 89;
    v45 = 11;
    goto LABEL_47;
  }
  v32.QuadPart = v47;
  if ( v47 >= v50 )
  {
    v32.QuadPart = v50;
    v47 = v50;
  }
  v33 = v57;
  ByteOffset = v57;
  v34 = (v32.LowPart - v57.LowPart) & 0xFFFFF000;
  if ( v34 > *a4 )
  {
    Range = -1073741595;
    HsmDbgBreakOnStatus(-1073741595);
    goto LABEL_24;
  }
  v35 = Buffer;
  if ( v34 )
  {
    Range = FltReadFile(*(PFLT_INSTANCE *)(a1 + 32), FileObject, &ByteOffset, v34, Buffer, 0xAu, &BytesRead, 0, 0);
    HsmDbgBreakOnStatus(Range);
    if ( Range < 0 )
      goto LABEL_70;
    if ( BytesRead != v34 )
    {
      Range = -1073741595;
      HsmDbgBreakOnStatus(-1073741595);
LABEL_70:
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_24;
      }
      v36 = HsmpGetStreamSize(a2);
      v46 = Range;
      v39 = 90;
      CallbackContext = v40;
      goto LABEL_74;
    }
    v15 = v34;
    v32.QuadPart = v47;
    v35 += v34;
    v33.QuadPart = v34 + ByteOffset.QuadPart;
    ByteOffset = v33;
  }
  if ( v33.QuadPart < v32.QuadPart )
  {
    v41 = v32.LowPart - v33.LowPart;
    if ( v41 )
    {
      Range = FltReadFileEx(*(_QWORD *)(a1 + 32), FileObject, &ByteOffset, 4096, 0, 10, &BytesRead, 0, 0, 0, Mdl);
      HsmDbgBreakOnStatus(Range);
      if ( Range >= 0 )
      {
        v25 = P;
        memmove(v35, P, v41);
        v15 += v41;
        goto LABEL_25;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v36 = HsmpGetStreamSize(a2);
        v39 = 91;
        v46 = Range;
        CallbackContext = v47;
        LowPart = ByteOffset.LowPart;
LABEL_74:
        WPP_SF_qLiiiid(
          *(_QWORD *)(v38 + 24),
          v39,
          (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
          a2,
          *(_DWORD *)(a2 + 28),
          v36,
          v53,
          LowPart,
          CallbackContext,
          v46);
      }
    }
  }
LABEL_24:
  v25 = P;
LABEL_25:
  *a4 = v15;
  HsmpReleaseBitmapLock(a2);
  FltReleasePushLockEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
  if ( Mdl )
    IoFreeMdl(Mdl);
  if ( v25 )
    ExFreePoolWithTag(v25, 0x77527348u);
  v12 = FileObject;
LABEL_30:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v12 )
    ObfDereferenceObject(v12);
  return (unsigned int)Range;
}

```

## disassembly

```asm
0x14006f558  mov     [rsp-8+arg_10], r8
0x14006f55d  mov     [rsp-8+arg_0], rcx
0x14006f562  push    rbp
0x14006f563  push    rbx
0x14006f564  push    rsi
0x14006f565  push    rdi
0x14006f566  push    r12
0x14006f568  push    r13
0x14006f56a  push    r14
0x14006f56c  push    r15
0x14006f56e  lea     rbp, [rsp-17h]
0x14006f573  sub     rsp, 0A8h
0x14006f57a  mov     rax, [rdx+10h]
0x14006f57e  mov     rbx, r9
0x14006f581  mov     r14, rdx
0x14006f584  mov     [rbp+4Fh+FileHandle], 0
0x14006f58c  mov     rdx, [rcx+20h]
0x14006f590  mov     [rbp+4Fh+Mdl], 0
0x14006f598  mov     r12, [rax+20h]
0x14006f59c  mov     eax, [r9]
0x14006f59f  mov     r9d, 100080h
0x14006f5a5  add     rax, r8
0x14006f5a8  mov     [rbp+4Fh+var_50], r12
0x14006f5ac  mov     [rbp+4Fh+var_80], rax
0x14006f5b0  mov     r8, r12
0x14006f5b3  lea     rax, [rbp+4Fh+Mdl]
0x14006f5b7  mov     qword ptr [rbp+4Fh+ByteOffset], 0
0x14006f5bf  mov     [rsp+0E0h+CallbackContext], rax
0x14006f5c4  lea     rax, [rbp+4Fh+FileHandle]
0x14006f5c8  mov     [rsp+0E0h+CallbackRoutine], rax
0x14006f5cd  mov     byte ptr [rsp+0E0h+BytesRead], 1
0x14006f5d2  mov     [rsp+0E0h+Flags], 200068h
0x14006f5da  mov     [rbp+4Fh+arg_18], 0
0x14006f5e1  mov     [rbp+4Fh+arg_8], 0
0x14006f5e5  mov     [rbp+4Fh+var_68], 0
0x14006f5ed  call    HsmpOpenFileByIdEx
0x14006f5f2  mov     ecx, eax
0x14006f5f4  mov     edi, eax
0x14006f5f6  call    HsmDbgBreakOnStatus
0x14006f5fb  mov     r13, [rbp+4Fh+Mdl]
0x14006f5ff  mov     [rbp+4Fh+FileObject], r13
0x14006f603  test    edi, edi
0x14006f605  jns     short loc_14006F67D
0x14006f607  mov     r10, cs:WPP_GLOBAL_Control
0x14006f60e  lea     rcx, WPP_GLOBAL_Control
0x14006f615  cmp     r10, rcx
0x14006f618  jz      short loc_14006F672
0x14006f61a  mov     ecx, [r10+2Ch]
0x14006f61e  test    cl, 1
0x14006f621  jz      short loc_14006F672
0x14006f623  cmp     byte ptr [r10+29h], 2
0x14006f628  jb      short loc_14006F672
0x14006f62a  mov     rcx, r14
0x14006f62d  call    HsmpGetStreamSize
0x14006f632  mov     r8, [rbp+4Fh+var_80]
0x14006f636  mov     edx, 51h ; 'Q'
0x14006f63b  mov     rcx, [r10+18h]
0x14006f63f  mov     r9, r14
0x14006f642  mov     dword ptr [rsp+0E0h+var_98], edi
0x14006f646  mov     [rsp+0E0h+CallbackContext], r8
0x14006f64b  mov     r8, [rbp+4Fh+arg_10]
0x14006f64f  mov     [rsp+0E0h+CallbackRoutine], r8
0x14006f654  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14006f65b  mov     [rsp+0E0h+BytesRead], r12
0x14006f660  mov     qword ptr [rsp+0E0h+Flags], rax
0x14006f665  mov     eax, [r14+1Ch]
0x14006f669  mov     dword ptr [rsp+0E0h+Irp], eax
0x14006f66d  call    WPP_SF_qLiiiid
0x14006f672  mov     dword ptr [rbx], 0
0x14006f678  jmp     loc_14006F80C
0x14006f67d  mov     rcx, [r14+10h]
0x14006f681  xor     esi, esi
0x14006f683  add     rcx, 18h
0x14006f687  mov     [rbp+4Fh+P], rsi
0x14006f68b  xor     edx, edx
0x14006f68d  mov     [rbp+4Fh+Mdl], rsi
0x14006f691  call    cs:__imp_FltAcquirePushLockSharedEx
0x14006f698  nop     dword ptr [rax+rax+00h]
0x14006f69d  mov     rcx, [r14+0A0h]
0x14006f6a4  test    rcx, rcx
0x14006f6a7  jz      short loc_14006F6BB
0x14006f6a9  add     rcx, 28h ; '('
0x14006f6ad  xor     edx, edx
0x14006f6af  call    cs:__imp_FltAcquirePushLockSharedEx
0x14006f6b6  nop     dword ptr [rax+rax+00h]
0x14006f6bb  mov     rdx, [rbp+4Fh+var_80]
0x14006f6bf  mov     r8, [rbp+4Fh+arg_10]
0x14006f6c3  cmp     rdx, r8
0x14006f6c6  jl      loc_14006FC5E
0x14006f6cc  mov     rcx, r14
0x14006f6cf  call    HsmpGetStreamSize
0x14006f6d4  cmp     r8, rax
0x14006f6d7  jg      loc_14006FC5E
0x14006f6dd  mov     ecx, 0FFFh
0x14006f6e2  test    rcx, r8
0x14006f6e5  jnz     loc_14006FC5E
0x14006f6eb  test    rcx, rdx
0x14006f6ee  jz      short loc_14006F6F9
0x14006f6f0  cmp     rdx, rax
0x14006f6f3  jl      loc_14006FC5E
0x14006f6f9  cmp     rdx, rax
0x14006f6fc  jl      short loc_14006F705
0x14006f6fe  mov     rdx, rax
0x14006f701  mov     [rbp+4Fh+var_80], rax
0x14006f705  mov     edi, 1000h
0x14006f70a  test    rcx, rdx
0x14006f70d  jz      loc_14006F8CE
0x14006f713  mov     r8d, 77527348h
0x14006f719  mov     edx, edi
0x14006f71b  mov     ecx, 40h ; '@'
0x14006f720  call    cs:__imp_ExAllocatePool2
0x14006f727  nop     dword ptr [rax+rax+00h]
0x14006f72c  mov     [rbp+4Fh+P], rax
0x14006f730  test    rax, rax
0x14006f733  jnz     loc_14006F84C
0x14006f739  mov     esi, 0C000009Ah
0x14006f73e  mov     ecx, esi
0x14006f740  mov     edi, esi
0x14006f742  call    HsmDbgBreakOnStatus
0x14006f747  mov     r10, cs:WPP_GLOBAL_Control
0x14006f74e  lea     rcx, WPP_GLOBAL_Control
0x14006f755  cmp     r10, rcx
0x14006f758  jz      short loc_14006F7B1
0x14006f75a  mov     eax, [r10+2Ch]
0x14006f75e  test    al, 1
0x14006f760  jz      short loc_14006F7B1
0x14006f762  cmp     byte ptr [r10+29h], 4
0x14006f767  jb      short loc_14006F7B1
0x14006f769  mov     rcx, r14
0x14006f76c  call    HsmpGetStreamSize
0x14006f771  mov     edx, 53h ; 'S'
0x14006f776  mov     r8, [rbp+4Fh+var_80]
0x14006f77a  mov     r9, r14
0x14006f77d  mov     rcx, [r10+18h]
0x14006f781  mov     dword ptr [rsp+0E0h+var_98], esi
0x14006f785  mov     [rsp+0E0h+CallbackContext], r8
0x14006f78a  mov     r8, [rbp+4Fh+arg_10]
0x14006f78e  mov     [rsp+0E0h+CallbackRoutine], r8
0x14006f793  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14006f79a  mov     [rsp+0E0h+BytesRead], r12
0x14006f79f  mov     qword ptr [rsp+0E0h+Flags], rax
0x14006f7a4  mov     eax, [r14+1Ch]
0x14006f7a8  mov     dword ptr [rsp+0E0h+Irp], eax
0x14006f7ac  call    WPP_SF_qLiiiid
0x14006f7b1  xor     esi, esi
0x14006f7b3  mov     r12, [rbp+4Fh+P]
0x14006f7b7  mov     rcx, r14
0x14006f7ba  mov     [rbx], esi
0x14006f7bc  call    HsmpReleaseBitmapLock
0x14006f7c1  mov     rcx, [r14+10h]
0x14006f7c5  xor     edx, edx
0x14006f7c7  add     rcx, 18h
0x14006f7cb  call    cs:__imp_FltReleasePushLockEx
0x14006f7d2  nop     dword ptr [rax+rax+00h]
0x14006f7d7  mov     rax, [rbp+4Fh+Mdl]
0x14006f7db  test    rax, rax
0x14006f7de  jz      short loc_14006F7EF
0x14006f7e0  mov     rcx, rax; Mdl
0x14006f7e3  call    cs:__imp_IoFreeMdl
0x14006f7ea  nop     dword ptr [rax+rax+00h]
0x14006f7ef  test    r12, r12
0x14006f7f2  jz      short loc_14006F808
0x14006f7f4  mov     edx, 77527348h; Tag
0x14006f7f9  mov     rcx, r12; P
0x14006f7fc  call    cs:__imp_ExFreePoolWithTag
0x14006f803  nop     dword ptr [rax+rax+00h]
0x14006f808  mov     r13, [rbp+4Fh+FileObject]
0x14006f80c  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14006f810  test    rcx, rcx
0x14006f813  jz      short loc_14006F821
0x14006f815  call    cs:__imp_FltClose
0x14006f81c  nop     dword ptr [rax+rax+00h]
0x14006f821  test    r13, r13
0x14006f824  jz      short loc_14006F835
0x14006f826  mov     rcx, r13; Object
0x14006f829  call    cs:__imp_ObfDereferenceObject
0x14006f830  nop     dword ptr [rax+rax+00h]
0x14006f835  mov     eax, edi
0x14006f837  add     rsp, 0A8h
0x14006f83e  pop     r15
0x14006f840  pop     r14
0x14006f842  pop     r13
0x14006f844  pop     r12
0x14006f846  pop     rdi
0x14006f847  pop     rsi
0x14006f848  pop     rbx
0x14006f849  pop     rbp
0x14006f84a  retn
0x14006f84c  xor     r9d, r9d; ChargeQuota
0x14006f84f  mov     [rsp+0E0h+Irp], rsi; Irp
0x14006f854  xor     r8d, r8d; SecondaryBuffer
0x14006f857  mov     edx, edi; Length
0x14006f859  mov     rcx, rax; VirtualAddress
0x14006f85c  call    cs:__imp_IoAllocateMdl
0x14006f863  nop     dword ptr [rax+rax+00h]
0x14006f868  mov     [rbp+4Fh+Mdl], rax
0x14006f86c  test    rax, rax
0x14006f86f  jnz     short loc_14006F8BF
0x14006f871  mov     esi, 0C000009Ah
0x14006f876  mov     ecx, esi
0x14006f878  mov     edi, esi
0x14006f87a  call    HsmDbgBreakOnStatus
0x14006f87f  mov     r10, cs:WPP_GLOBAL_Control
0x14006f886  lea     rcx, WPP_GLOBAL_Control
0x14006f88d  cmp     r10, rcx
0x14006f890  jz      loc_14006F7B1
0x14006f896  mov     eax, [r10+2Ch]
0x14006f89a  test    al, 1
0x14006f89c  jz      loc_14006F7B1
0x14006f8a2  cmp     byte ptr [r10+29h], 4
0x14006f8a7  jb      loc_14006F7B1
0x14006f8ad  mov     rcx, r14
0x14006f8b0  call    HsmpGetStreamSize
0x14006f8b5  mov     edx, 54h ; 'T'
0x14006f8ba  jmp     loc_14006F776
0x14006f8bf  mov     rcx, rax; MemoryDescriptorList
0x14006f8c2  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14006f8c9  nop     dword ptr [rax+rax+00h]
0x14006f8ce  mov     rdx, r13
0x14006f8d1  mov     rcx, r14
0x14006f8d4  call    HsmpValidateStreamContextNoLock
0x14006f8d9  mov     ecx, eax
0x14006f8db  mov     edi, eax
0x14006f8dd  call    HsmDbgBreakOnStatus
0x14006f8e2  test    edi, edi
0x14006f8e4  jns     short loc_14006F961
0x14006f8e6  mov     r10, cs:WPP_GLOBAL_Control
0x14006f8ed  lea     rcx, WPP_GLOBAL_Control
0x14006f8f4  cmp     r10, rcx
0x14006f8f7  jz      loc_14006F7B3
0x14006f8fd  mov     eax, [r10+2Ch]
0x14006f901  test    al, 1
0x14006f903  jz      loc_14006F7B3
0x14006f909  cmp     byte ptr [r10+29h], 2
0x14006f90e  jb      loc_14006F7B3
0x14006f914  mov     rcx, r14
0x14006f917  call    HsmpGetStreamSize
0x14006f91c  mov     edx, 55h ; 'U'
0x14006f921  mov     dword ptr [rsp+0E0h+var_98], edi
0x14006f925  mov     r8, [rbp+4Fh+var_80]
0x14006f929  mov     [rsp+0E0h+CallbackContext], r8
0x14006f92e  mov     r8, [rbp+4Fh+arg_10]
0x14006f932  mov     [rsp+0E0h+CallbackRoutine], r8
0x14006f937  mov     [rsp+0E0h+BytesRead], r12
0x14006f93c  mov     rcx, [r10+18h]
0x14006f940  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14006f947  mov     qword ptr [rsp+0E0h+Flags], rax
0x14006f94c  mov     r9, r14
0x14006f94f  mov     eax, [r14+1Ch]
0x14006f953  mov     dword ptr [rsp+0E0h+Irp], eax
0x14006f957  call    WPP_SF_qLiiiid
0x14006f95c  jmp     loc_14006F7B3
0x14006f961  mov     rax, [r14+0A0h]
0x14006f968  mov     rcx, [rax+38h]
0x14006f96c  mov     eax, [r14+1Ch]
0x14006f970  shr     eax, 6
0x14006f973  and     al, 1
0x14006f975  test    rcx, rcx
0x14006f978  jz      short loc_14006F99F
0x14006f97a  lea     rax, [rbp+4Fh+var_68]
0x14006f97e  lea     r9, [rbp+4Fh+arg_8]
0x14006f982  mov     [rsp+0E0h+Irp], rax
0x14006f987  lea     r8, [rbp+4Fh+var_80]
0x14006f98b  lea     rdx, [rbp+4Fh+arg_10]
0x14006f98f  call    HsmpBitmapQueryRange
0x14006f994  mov     ecx, eax
0x14006f996  mov     edi, eax
0x14006f998  call    HsmDbgBreakOnStatus
0x14006f99d  jmp     short loc_14006F9AC
0x14006f99f  mov     [rbp+4Fh+arg_8], al
0x14006f9a2  xor     edi, edi
0x14006f9a4  mov     rax, [rbp+4Fh+var_80]
0x14006f9a8  mov     [rbp+4Fh+var_68], rax
0x14006f9ac  mov     ecx, edi
0x14006f9ae  call    HsmDbgBreakOnStatus
0x14006f9b3  test    edi, edi
0x14006f9b5  jns     short loc_14006F9F7
0x14006f9b7  mov     r10, cs:WPP_GLOBAL_Control
0x14006f9be  lea     rcx, WPP_GLOBAL_Control
0x14006f9c5  cmp     r10, rcx
0x14006f9c8  jz      loc_14006F7B3
0x14006f9ce  mov     eax, [r10+2Ch]
0x14006f9d2  test    al, 1
0x14006f9d4  jz      loc_14006F7B3
0x14006f9da  cmp     byte ptr [r10+29h], 2
0x14006f9df  jb      loc_14006F7B3
0x14006f9e5  mov     rcx, r14
0x14006f9e8  call    HsmpGetStreamSize
0x14006f9ed  mov     edx, 58h ; 'X'
0x14006f9f2  jmp     loc_14006F921
0x14006f9f7  cmp     [rbp+4Fh+arg_8], sil
0x14006f9fb  jnz     short loc_14006FA53
0x14006f9fd  mov     r15d, 0C000CF0Bh
0x14006fa03  mov     ecx, r15d
0x14006fa06  mov     edi, r15d
0x14006fa09  call    HsmDbgBreakOnStatus
0x14006fa0e  mov     r10, cs:WPP_GLOBAL_Control
0x14006fa15  lea     rcx, WPP_GLOBAL_Control
0x14006fa1c  cmp     r10, rcx
0x14006fa1f  jz      loc_14006F7B3
  ... truncated ...
```
