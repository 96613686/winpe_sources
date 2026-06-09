# HsmRecallRetrieveData

- ea: `0x14006f438`
- end: `0x14006fbce`
- name: `HsmRecallRetrieveData`
- size: `1942`
- prototype: `__int64 __fastcall(int, int, int, int, PVOID Buffer)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, installer_update`

## callers

- `0x14006f1a8`

## callees

- `0x140003c50`
- `0x140017d68`
- `0x14001e280`
- `0x140058cbc`
- `0x140059618`
- `0x14005e64c`
- `0x140069828`
- `0x14006f438`
- `0x14007038c`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14006f7a2`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14006f7a2`
- `ntoskrnl!IoFreeMdl` at `0x14006f6c3`
- `ntoskrnl!IoFreeMdl` at `0x14006f6c3`
- `ntoskrnl!IoAllocateMdl` at `0x14006f73c`
- `ntoskrnl!IoAllocateMdl` at `0x14006f73c`
- `ntoskrnl!ObfDereferenceObject` at `0x14006f709`
- `ntoskrnl!ObfDereferenceObject` at `0x14006f709`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f6dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006f6dc`
- `ntoskrnl!ExAllocatePool2` at `0x14006f600`
- `ntoskrnl!ExAllocatePool2` at `0x14006f600`
- `FLTMGR!FltReadFileEx` at `0x14006faba`
- `FLTMGR!FltReadFileEx` at `0x14006faba`
- `FLTMGR!FltReadFile` at `0x14006f9b0`
- `FLTMGR!FltReadFile` at `0x14006f9b0`
- `FLTMGR!FltClose` at `0x14006f6f5`
- `FLTMGR!FltClose` at `0x14006f6f5`
- `FLTMGR!FltReleasePushLockEx` at `0x14006f6ab`
- `FLTMGR!FltReleasePushLockEx` at `0x14006f6ab`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f571`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f58f`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f571`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14006f58f`

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
  HsmDbgBreakOnStatus((unsigned int)Range);
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
    HsmDbgBreakOnStatus(3221278475LL);
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
      HsmDbgBreakOnStatus(3221225626LL);
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
      HsmDbgBreakOnStatus(3221225626LL);
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
  HsmDbgBreakOnStatus((unsigned int)Range);
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
    HsmDbgBreakOnStatus((unsigned int)Range);
  }
  else
  {
    v56 = (*(_DWORD *)(a2 + 28) & 0x40) != 0;
    Range = 0;
    v50 = v47;
  }
  HsmDbgBreakOnStatus((unsigned int)Range);
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
    HsmDbgBreakOnStatus(3221278475LL);
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
    HsmDbgBreakOnStatus(3221225701LL);
    goto LABEL_24;
  }
  v35 = Buffer;
  if ( v34 )
  {
    Range = FltReadFile(*(PFLT_INSTANCE *)(a1 + 32), FileObject, &ByteOffset, v34, Buffer, 0xAu, &BytesRead, 0, 0);
    HsmDbgBreakOnStatus((unsigned int)Range);
    if ( Range < 0 )
      goto LABEL_70;
    if ( BytesRead != v34 )
    {
      Range = -1073741595;
      HsmDbgBreakOnStatus(3221225701LL);
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
      HsmDbgBreakOnStatus((unsigned int)Range);
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
0x14006f438  mov     [rsp-8+arg_10], r8
0x14006f43d  mov     [rsp-8+arg_0], rcx
0x14006f442  push    rbp
0x14006f443  push    rbx
0x14006f444  push    rsi
0x14006f445  push    rdi
0x14006f446  push    r12
0x14006f448  push    r13
0x14006f44a  push    r14
0x14006f44c  push    r15
0x14006f44e  lea     rbp, [rsp-17h]
0x14006f453  sub     rsp, 0A8h
0x14006f45a  mov     rax, [rdx+10h]
0x14006f45e  mov     rbx, r9
0x14006f461  mov     r14, rdx
0x14006f464  mov     [rbp+4Fh+FileHandle], 0
0x14006f46c  mov     rdx, [rcx+20h]
0x14006f470  mov     [rbp+4Fh+Mdl], 0
0x14006f478  mov     r12, [rax+20h]
0x14006f47c  mov     eax, [r9]
0x14006f47f  mov     r9d, 100080h
0x14006f485  add     rax, r8
0x14006f488  mov     [rbp+4Fh+var_50], r12
0x14006f48c  mov     [rbp+4Fh+var_80], rax
0x14006f490  mov     r8, r12
0x14006f493  lea     rax, [rbp+4Fh+Mdl]
0x14006f497  mov     qword ptr [rbp+4Fh+ByteOffset], 0
0x14006f49f  mov     [rsp+0E0h+CallbackContext], rax
0x14006f4a4  lea     rax, [rbp+4Fh+FileHandle]
0x14006f4a8  mov     [rsp+0E0h+CallbackRoutine], rax
0x14006f4ad  mov     byte ptr [rsp+0E0h+BytesRead], 1
0x14006f4b2  mov     [rsp+0E0h+Flags], 200068h
0x14006f4ba  mov     [rbp+4Fh+arg_18], 0
0x14006f4c1  mov     [rbp+4Fh+arg_8], 0
0x14006f4c5  mov     [rbp+4Fh+var_68], 0
0x14006f4cd  call    HsmpOpenFileByIdEx
0x14006f4d2  mov     ecx, eax
0x14006f4d4  mov     edi, eax
0x14006f4d6  call    HsmDbgBreakOnStatus
0x14006f4db  mov     r13, [rbp+4Fh+Mdl]
0x14006f4df  mov     [rbp+4Fh+FileObject], r13
0x14006f4e3  test    edi, edi
0x14006f4e5  jns     short loc_14006F55D
0x14006f4e7  mov     r10, cs:WPP_GLOBAL_Control
0x14006f4ee  lea     rcx, WPP_GLOBAL_Control
0x14006f4f5  cmp     r10, rcx
0x14006f4f8  jz      short loc_14006F552
0x14006f4fa  mov     ecx, [r10+2Ch]
0x14006f4fe  test    cl, 1
0x14006f501  jz      short loc_14006F552
0x14006f503  cmp     byte ptr [r10+29h], 2
0x14006f508  jb      short loc_14006F552
0x14006f50a  mov     rcx, r14
0x14006f50d  call    HsmpGetStreamSize
0x14006f512  mov     r8, [rbp+4Fh+var_80]
0x14006f516  mov     edx, 51h ; 'Q'
0x14006f51b  mov     rcx, [r10+18h]
0x14006f51f  mov     r9, r14
0x14006f522  mov     dword ptr [rsp+0E0h+var_98], edi
0x14006f526  mov     [rsp+0E0h+CallbackContext], r8
0x14006f52b  mov     r8, [rbp+4Fh+arg_10]
0x14006f52f  mov     [rsp+0E0h+CallbackRoutine], r8
0x14006f534  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14006f53b  mov     [rsp+0E0h+BytesRead], r12
0x14006f540  mov     qword ptr [rsp+0E0h+Flags], rax
0x14006f545  mov     eax, [r14+1Ch]
0x14006f549  mov     dword ptr [rsp+0E0h+Irp], eax
0x14006f54d  call    WPP_SF_qLiiiid
0x14006f552  mov     dword ptr [rbx], 0
0x14006f558  jmp     loc_14006F6EC
0x14006f55d  mov     rcx, [r14+10h]
0x14006f561  xor     esi, esi
0x14006f563  add     rcx, 18h
0x14006f567  mov     [rbp+4Fh+P], rsi
0x14006f56b  xor     edx, edx
0x14006f56d  mov     [rbp+4Fh+Mdl], rsi
0x14006f571  call    cs:__imp_FltAcquirePushLockSharedEx
0x14006f578  nop     dword ptr [rax+rax+00h]
0x14006f57d  mov     rcx, [r14+0A0h]
0x14006f584  test    rcx, rcx
0x14006f587  jz      short loc_14006F59B
0x14006f589  add     rcx, 28h ; '('
0x14006f58d  xor     edx, edx
0x14006f58f  call    cs:__imp_FltAcquirePushLockSharedEx
0x14006f596  nop     dword ptr [rax+rax+00h]
0x14006f59b  mov     rdx, [rbp+4Fh+var_80]
0x14006f59f  mov     r8, [rbp+4Fh+arg_10]
0x14006f5a3  cmp     rdx, r8
0x14006f5a6  jl      loc_14006FB3E
0x14006f5ac  mov     rcx, r14
0x14006f5af  call    HsmpGetStreamSize
0x14006f5b4  cmp     r8, rax
0x14006f5b7  jg      loc_14006FB3E
0x14006f5bd  mov     ecx, 0FFFh
0x14006f5c2  test    rcx, r8
0x14006f5c5  jnz     loc_14006FB3E
0x14006f5cb  test    rcx, rdx
0x14006f5ce  jz      short loc_14006F5D9
0x14006f5d0  cmp     rdx, rax
0x14006f5d3  jl      loc_14006FB3E
0x14006f5d9  cmp     rdx, rax
0x14006f5dc  jl      short loc_14006F5E5
0x14006f5de  mov     rdx, rax
0x14006f5e1  mov     [rbp+4Fh+var_80], rax
0x14006f5e5  mov     edi, 1000h
0x14006f5ea  test    rcx, rdx
0x14006f5ed  jz      loc_14006F7AE
0x14006f5f3  mov     r8d, 77527348h
0x14006f5f9  mov     edx, edi
0x14006f5fb  mov     ecx, 40h ; '@'
0x14006f600  call    cs:__imp_ExAllocatePool2
0x14006f607  nop     dword ptr [rax+rax+00h]
0x14006f60c  mov     [rbp+4Fh+P], rax
0x14006f610  test    rax, rax
0x14006f613  jnz     loc_14006F72C
0x14006f619  mov     esi, 0C000009Ah
0x14006f61e  mov     ecx, esi
0x14006f620  mov     edi, esi
0x14006f622  call    HsmDbgBreakOnStatus
0x14006f627  mov     r10, cs:WPP_GLOBAL_Control
0x14006f62e  lea     rcx, WPP_GLOBAL_Control
0x14006f635  cmp     r10, rcx
0x14006f638  jz      short loc_14006F691
0x14006f63a  mov     eax, [r10+2Ch]
0x14006f63e  test    al, 1
0x14006f640  jz      short loc_14006F691
0x14006f642  cmp     byte ptr [r10+29h], 4
0x14006f647  jb      short loc_14006F691
0x14006f649  mov     rcx, r14
0x14006f64c  call    HsmpGetStreamSize
0x14006f651  mov     edx, 53h ; 'S'
0x14006f656  mov     r8, [rbp+4Fh+var_80]
0x14006f65a  mov     r9, r14
0x14006f65d  mov     rcx, [r10+18h]
0x14006f661  mov     dword ptr [rsp+0E0h+var_98], esi
0x14006f665  mov     [rsp+0E0h+CallbackContext], r8
0x14006f66a  mov     r8, [rbp+4Fh+arg_10]
0x14006f66e  mov     [rsp+0E0h+CallbackRoutine], r8
0x14006f673  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14006f67a  mov     [rsp+0E0h+BytesRead], r12
0x14006f67f  mov     qword ptr [rsp+0E0h+Flags], rax
0x14006f684  mov     eax, [r14+1Ch]
0x14006f688  mov     dword ptr [rsp+0E0h+Irp], eax
0x14006f68c  call    WPP_SF_qLiiiid
0x14006f691  xor     esi, esi
0x14006f693  mov     r12, [rbp+4Fh+P]
0x14006f697  mov     rcx, r14
0x14006f69a  mov     [rbx], esi
0x14006f69c  call    HsmpReleaseBitmapLock
0x14006f6a1  mov     rcx, [r14+10h]
0x14006f6a5  xor     edx, edx
0x14006f6a7  add     rcx, 18h
0x14006f6ab  call    cs:__imp_FltReleasePushLockEx
0x14006f6b2  nop     dword ptr [rax+rax+00h]
0x14006f6b7  mov     rax, [rbp+4Fh+Mdl]
0x14006f6bb  test    rax, rax
0x14006f6be  jz      short loc_14006F6CF
0x14006f6c0  mov     rcx, rax; Mdl
0x14006f6c3  call    cs:__imp_IoFreeMdl
0x14006f6ca  nop     dword ptr [rax+rax+00h]
0x14006f6cf  test    r12, r12
0x14006f6d2  jz      short loc_14006F6E8
0x14006f6d4  mov     edx, 77527348h; Tag
0x14006f6d9  mov     rcx, r12; P
0x14006f6dc  call    cs:__imp_ExFreePoolWithTag
0x14006f6e3  nop     dword ptr [rax+rax+00h]
0x14006f6e8  mov     r13, [rbp+4Fh+FileObject]
0x14006f6ec  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x14006f6f0  test    rcx, rcx
0x14006f6f3  jz      short loc_14006F701
0x14006f6f5  call    cs:__imp_FltClose
0x14006f6fc  nop     dword ptr [rax+rax+00h]
0x14006f701  test    r13, r13
0x14006f704  jz      short loc_14006F715
0x14006f706  mov     rcx, r13; Object
0x14006f709  call    cs:__imp_ObfDereferenceObject
0x14006f710  nop     dword ptr [rax+rax+00h]
0x14006f715  mov     eax, edi
0x14006f717  add     rsp, 0A8h
0x14006f71e  pop     r15
0x14006f720  pop     r14
0x14006f722  pop     r13
0x14006f724  pop     r12
0x14006f726  pop     rdi
0x14006f727  pop     rsi
0x14006f728  pop     rbx
0x14006f729  pop     rbp
0x14006f72a  retn
0x14006f72c  xor     r9d, r9d; ChargeQuota
0x14006f72f  mov     [rsp+0E0h+Irp], rsi; Irp
0x14006f734  xor     r8d, r8d; SecondaryBuffer
0x14006f737  mov     edx, edi; Length
0x14006f739  mov     rcx, rax; VirtualAddress
0x14006f73c  call    cs:__imp_IoAllocateMdl
0x14006f743  nop     dword ptr [rax+rax+00h]
0x14006f748  mov     [rbp+4Fh+Mdl], rax
0x14006f74c  test    rax, rax
0x14006f74f  jnz     short loc_14006F79F
0x14006f751  mov     esi, 0C000009Ah
0x14006f756  mov     ecx, esi
0x14006f758  mov     edi, esi
0x14006f75a  call    HsmDbgBreakOnStatus
0x14006f75f  mov     r10, cs:WPP_GLOBAL_Control
0x14006f766  lea     rcx, WPP_GLOBAL_Control
0x14006f76d  cmp     r10, rcx
0x14006f770  jz      loc_14006F691
0x14006f776  mov     eax, [r10+2Ch]
0x14006f77a  test    al, 1
0x14006f77c  jz      loc_14006F691
0x14006f782  cmp     byte ptr [r10+29h], 4
0x14006f787  jb      loc_14006F691
0x14006f78d  mov     rcx, r14
0x14006f790  call    HsmpGetStreamSize
0x14006f795  mov     edx, 54h ; 'T'
0x14006f79a  jmp     loc_14006F656
0x14006f79f  mov     rcx, rax; MemoryDescriptorList
0x14006f7a2  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14006f7a9  nop     dword ptr [rax+rax+00h]
0x14006f7ae  mov     rdx, r13
0x14006f7b1  mov     rcx, r14
0x14006f7b4  call    HsmpValidateStreamContextNoLock
0x14006f7b9  mov     ecx, eax
0x14006f7bb  mov     edi, eax
0x14006f7bd  call    HsmDbgBreakOnStatus
0x14006f7c2  test    edi, edi
0x14006f7c4  jns     short loc_14006F841
0x14006f7c6  mov     r10, cs:WPP_GLOBAL_Control
0x14006f7cd  lea     rcx, WPP_GLOBAL_Control
0x14006f7d4  cmp     r10, rcx
0x14006f7d7  jz      loc_14006F693
0x14006f7dd  mov     eax, [r10+2Ch]
0x14006f7e1  test    al, 1
0x14006f7e3  jz      loc_14006F693
0x14006f7e9  cmp     byte ptr [r10+29h], 2
0x14006f7ee  jb      loc_14006F693
0x14006f7f4  mov     rcx, r14
0x14006f7f7  call    HsmpGetStreamSize
0x14006f7fc  mov     edx, 55h ; 'U'
0x14006f801  mov     dword ptr [rsp+0E0h+var_98], edi
0x14006f805  mov     r8, [rbp+4Fh+var_80]
0x14006f809  mov     [rsp+0E0h+CallbackContext], r8
0x14006f80e  mov     r8, [rbp+4Fh+arg_10]
0x14006f812  mov     [rsp+0E0h+CallbackRoutine], r8
0x14006f817  mov     [rsp+0E0h+BytesRead], r12
0x14006f81c  mov     rcx, [r10+18h]
0x14006f820  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14006f827  mov     qword ptr [rsp+0E0h+Flags], rax
0x14006f82c  mov     r9, r14
0x14006f82f  mov     eax, [r14+1Ch]
0x14006f833  mov     dword ptr [rsp+0E0h+Irp], eax
0x14006f837  call    WPP_SF_qLiiiid
0x14006f83c  jmp     loc_14006F693
0x14006f841  mov     rax, [r14+0A0h]
0x14006f848  mov     rcx, [rax+38h]
0x14006f84c  mov     eax, [r14+1Ch]
0x14006f850  shr     eax, 6
0x14006f853  and     al, 1
0x14006f855  test    rcx, rcx
0x14006f858  jz      short loc_14006F87F
0x14006f85a  lea     rax, [rbp+4Fh+var_68]
0x14006f85e  lea     r9, [rbp+4Fh+arg_8]
0x14006f862  mov     [rsp+0E0h+Irp], rax
0x14006f867  lea     r8, [rbp+4Fh+var_80]
0x14006f86b  lea     rdx, [rbp+4Fh+arg_10]
0x14006f86f  call    HsmpBitmapQueryRange
0x14006f874  mov     ecx, eax
0x14006f876  mov     edi, eax
0x14006f878  call    HsmDbgBreakOnStatus
0x14006f87d  jmp     short loc_14006F88C
0x14006f87f  mov     [rbp+4Fh+arg_8], al
0x14006f882  xor     edi, edi
0x14006f884  mov     rax, [rbp+4Fh+var_80]
0x14006f888  mov     [rbp+4Fh+var_68], rax
0x14006f88c  mov     ecx, edi
0x14006f88e  call    HsmDbgBreakOnStatus
0x14006f893  test    edi, edi
0x14006f895  jns     short loc_14006F8D7
0x14006f897  mov     r10, cs:WPP_GLOBAL_Control
0x14006f89e  lea     rcx, WPP_GLOBAL_Control
0x14006f8a5  cmp     r10, rcx
0x14006f8a8  jz      loc_14006F693
0x14006f8ae  mov     eax, [r10+2Ch]
0x14006f8b2  test    al, 1
0x14006f8b4  jz      loc_14006F693
0x14006f8ba  cmp     byte ptr [r10+29h], 2
0x14006f8bf  jb      loc_14006F693
0x14006f8c5  mov     rcx, r14
0x14006f8c8  call    HsmpGetStreamSize
0x14006f8cd  mov     edx, 58h ; 'X'
0x14006f8d2  jmp     loc_14006F801
0x14006f8d7  cmp     [rbp+4Fh+arg_8], sil
0x14006f8db  jnz     short loc_14006F933
0x14006f8dd  mov     r15d, 0C000CF0Bh
0x14006f8e3  mov     ecx, r15d
0x14006f8e6  mov     edi, r15d
0x14006f8e9  call    HsmDbgBreakOnStatus
0x14006f8ee  mov     r10, cs:WPP_GLOBAL_Control
0x14006f8f5  lea     rcx, WPP_GLOBAL_Control
0x14006f8fc  cmp     r10, rcx
0x14006f8ff  jz      loc_14006F693
  ... truncated ...
```
