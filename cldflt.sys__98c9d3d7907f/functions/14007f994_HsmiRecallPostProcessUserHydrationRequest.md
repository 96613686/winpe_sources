# HsmiRecallPostProcessUserHydrationRequest

- ea: `0x14007f994`
- end: `0x1400801ca`
- name: `HsmiRecallPostProcessUserHydrationRequest`
- size: `2102`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x140084eb0`

## callees

- `0x140001910`
- `0x140003c50`
- `0x140007ddc`
- `0x14000c180`
- `0x14000cd0c`
- `0x140017b78`
- `0x1400183c8`
- `0x14001846c`
- `0x14001851c`
- `0x14001e220`
- `0x140058cbc`
- `0x140059618`
- `0x140065194`
- `0x140067d04`
- `0x14006f16c`
- `0x14007038c`
- `0x14007446c`
- `0x14007f994`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x14007ff63`
- `ntoskrnl!IoBuildPartialMdl` at `0x14007ff63`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007ff38`
- `ntoskrnl!MmUnmapLockedPages` at `0x14007ff38`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007fdc8`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007fdc8`
- `ntoskrnl!IoFreeMdl` at `0x14007fd1e`
- `ntoskrnl!IoFreeMdl` at `0x14007fd1e`
- `ntoskrnl!IoAllocateMdl` at `0x14007feb1`
- `ntoskrnl!IoAllocateMdl` at `0x14007feb1`
- `ntoskrnl!KeSetEvent` at `0x14007fd93`
- `ntoskrnl!KeSetEvent` at `0x14007fd93`
- `FLTMGR!FltReadFileEx` at `0x140080008`
- `FLTMGR!FltReadFileEx` at `0x140080008`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400801a2`
- `FLTMGR!FltCompletePendedPreOperation` at `0x1400801a2`
- `FLTMGR!FltReleasePushLockEx` at `0x14007fc7b`
- `FLTMGR!FltReleasePushLockEx` at `0x14007fd06`
- `FLTMGR!FltReleasePushLockEx` at `0x14007fc7b`
- `FLTMGR!FltReleasePushLockEx` at `0x14007fd06`

## pseudocode

```c
void __fastcall HsmiRecallPostProcessUserHydrationRequest(__int64 a1, struct _FLT_CALLBACK_DATA *a2, unsigned int a3)
{
  __int64 v3; // rbx
  int v5; // r13d
  __int64 v6; // rdi
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // r12
  __int64 v11; // rax
  __int64 v12; // rdx
  int v13; // r9d
  PDEVICE_OBJECT v14; // r13
  __int64 StreamSize; // rax
  __int64 v16; // r8
  __int64 v17; // r11
  ULONG_PTR v18; // r15
  __int64 v19; // r13
  FLT_PREOP_CALLBACK_STATUS v20; // r12d
  int v21; // eax
  int v22; // r8d
  PFLT_IO_PARAMETER_BLOCK v23; // rax
  LARGE_INTEGER v24; // rdi
  __int64 v25; // rdx
  __int64 v26; // rax
  unsigned __int64 v27; // rdi
  __int64 v28; // rax
  __int64 v29; // r15
  __int64 v30; // r9
  char v31; // al
  __int64 v32; // r10
  int v33; // edx
  PFLT_IO_PARAMETER_BLOCK Iopb; // rcx
  LARGE_INTEGER ByteOffset; // rdx
  __int64 Length; // r15
  __int64 v37; // r15
  __int64 v38; // rdx
  __int64 v39; // rcx
  __int64 (__fastcall *v40)(__int64, __int64, __int64, __int64, struct _FLT_CALLBACK_DATA *, _DWORD); // rax
  int v41; // eax
  struct _KEVENT *v42; // rcx
  struct _MDL *MdlAddress; // rcx
  PFLT_IO_PARAMETER_BLOCK v44; // rax
  LARGE_INTEGER v45; // rcx
  __int64 v46; // rcx
  PFLT_IO_PARAMETER_BLOCK v47; // r8
  LARGE_INTEGER v48; // rcx
  LARGE_INTEGER v49; // rdx
  ULONG v50; // r13d
  __int64 v51; // rax
  __int64 v52; // r8
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r8
  PFLT_IO_PARAMETER_BLOCK v56; // rax
  __int64 v57; // rax
  __int64 v58; // r8
  PFLT_IO_PARAMETER_BLOCK v59; // rax
  void *v60; // rdi
  __int64 v61; // [rsp+30h] [rbp-69h]
  __int64 v62; // [rsp+50h] [rbp-49h]
  ULONG v63; // [rsp+50h] [rbp-49h]
  __int64 v64; // [rsp+70h] [rbp-29h]
  LARGE_INTEGER v65; // [rsp+80h] [rbp-19h] BYREF
  PMDL Mdl; // [rsp+88h] [rbp-11h]
  __int64 v67; // [rsp+90h] [rbp-9h]
  __int64 v68; // [rsp+98h] [rbp-1h]
  LARGE_INTEGER v69; // [rsp+A0h] [rbp+7h] BYREF
  LARGE_INTEGER v70; // [rsp+A8h] [rbp+Fh] BYREF
  LARGE_INTEGER v71; // [rsp+B0h] [rbp+17h] BYREF
  PMDL SourceMdl; // [rsp+B8h] [rbp+1Fh]
  char v73; // [rsp+100h] [rbp+67h] BYREF
  char v74; // [rsp+110h] [rbp+77h]
  DWORD v75; // [rsp+118h] [rbp+7Fh]

  v3 = *(_QWORD *)(a1 + 120);
  v5 = *(_DWORD *)(a1 + 40);
  LODWORD(v6) = a3;
  v8 = *(_QWORD *)(v3 + 16);
  v9 = *(_QWORD *)(v8 + 16);
  v10 = *(_QWORD *)(v8 + 32);
  v11 = *(_QWORD *)(a1 + 16);
  v68 = v9;
  v64 = v10;
  v67 = v11;
  HsmDbgBreakOnStatus(a3);
  if ( (int)v6 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(v3);
      WPP_SF_qliiqqLiid(
        v14->AttachedDevice,
        24,
        v16,
        a1,
        (*(_DWORD *)(a1 + 48) >> 6) & 7,
        v17,
        v17 + *(_QWORD *)(a1 + 80),
        a2,
        v3,
        *(_DWORD *)(v3 + 28),
        StreamSize,
        v10,
        v6);
    }
    v18 = 0;
    v19 = v10;
LABEL_7:
    v20 = FLT_PREOP_COMPLETE;
LABEL_51:
    a2->IoStatus.Status = v6;
    a2->IoStatus.Information = v18;
    goto LABEL_52;
  }
  v20 = FLT_PREOP_COMPLETE;
  v21 = *(_DWORD *)(a1 + 48) & 0x1F;
  Mdl = 0;
  v74 = 0;
  if ( (unsigned int)(v21 - 9) > 1
    || (*(_DWORD *)(v3 + 28) & 0x400) != 0
    || (LOBYTE(v12) = 1, HsmpAcquireReparseUpdateLock(v3, v12), v22 = *(_DWORD *)(v3 + 28), v74 = 1, (v22 & 0x400) != 0) )
  {
LABEL_33:
    Iopb = a2->Iopb;
    if ( Iopb->MajorFunction != 3 || (v5 & 0xFu) >= 3 || (v5 & 0x100) != 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
      {
        v19 = v64;
      }
      else
      {
        v57 = HsmpGetStreamSize(v3);
        v19 = v64;
        WPP_SF_qqqLiidD(
          *(_QWORD *)(v58 + 24),
          (unsigned int)a2->IoStatus.Status,
          v58,
          a1,
          a2,
          v3,
          *(_DWORD *)(v3 + 28),
          v57,
          v64,
          a2->IoStatus.Status,
          a2->IoStatus.Information);
      }
      v59 = a2->Iopb;
      if ( v59->MajorFunction != 13 || v59->Parameters.Read.ByteOffset.LowPart != 590780 )
        v20 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
      if ( (*(_DWORD *)(a1 + 48) & 0x1F) == 4 )
        v18 = 0;
      else
        v18 = *(_QWORD *)(a1 + 80);
      goto LABEL_45;
    }
    if ( !*(_QWORD *)(a1 + 128) )
    {
      if ( (*(_DWORD *)(a1 + 48) & 0x20) == 0 )
      {
        v20 = FLT_PREOP_SUCCESS_WITH_CALLBACK;
        goto LABEL_43;
      }
      ByteOffset = Iopb->Parameters.Read.ByteOffset;
      Length = Iopb->Parameters.Read.Length;
LABEL_39:
      v37 = ByteOffset.QuadPart + Length;
      if ( v37 >= HsmpGetStreamSize(v3) )
        v37 = HsmpGetStreamSize(v39);
      v18 = v37 - v38;
LABEL_44:
      v19 = v64;
LABEL_45:
      if ( !v74 )
        goto LABEL_47;
      goto LABEL_46;
    }
    MdlAddress = Iopb->Parameters.Read.MdlAddress;
    SourceMdl = MdlAddress;
    if ( (MdlAddress->MdlFlags & 5) == 0 )
      MmMapLockedPagesSpecifyCache(MdlAddress, 0, MmCached, 0, 0, 0x40000010u);
    v44 = a2->Iopb;
    v70.QuadPart = 0;
    v45 = v44->Parameters.Read.ByteOffset;
    v65 = v45;
    v71.QuadPart = v45.QuadPart + v44->Parameters.Read.Length;
    while ( 1 )
    {
      while ( 1 )
      {
        if ( v45.QuadPart >= v71.QuadPart )
        {
          v56 = a2->Iopb;
          ByteOffset = v56->Parameters.Read.ByteOffset;
          Length = v56->Parameters.Read.Length;
          goto LABEL_39;
        }
        v46 = *(_QWORD *)(a1 + 128);
        v73 = 0;
        v69.QuadPart = 0;
        HsmpBitmapQueryRange(v46, (unsigned int)&v65, (unsigned int)&v71, (unsigned int)&v73, (__int64)&v70);
        if ( v73 )
          break;
        v45 = v70;
        v65 = v70;
      }
      v47 = a2->Iopb;
      v48 = v65;
      v49 = v47->Parameters.Read.ByteOffset;
      if ( v65.QuadPart < v49.QuadPart
        || v65.QuadPart - v49.QuadPart >= 0xFFFFFFFFLL
        || v70.QuadPart <= v65.QuadPart
        || v70.QuadPart - v65.QuadPart >= 0xFFFFFFFFLL )
      {
        LODWORD(v6) = -1073741595;
        HsmDbgBreakOnStatus(3221225701LL);
        goto LABEL_43;
      }
      v50 = v70.LowPart - v65.LowPart;
      v75 = v65.LowPart - v47->Parameters.Read.ByteOffset.LowPart;
      if ( !Mdl )
        break;
      if ( (Mdl->MdlFlags & 0x20) != 0 )
      {
        MmUnmapLockedPages(Mdl->MappedSystemVa, Mdl);
        goto LABEL_71;
      }
LABEL_72:
      v69 = v48;
      IoBuildPartialMdl(SourceMdl, Mdl, (char *)SourceMdl->StartVa + v75 + SourceMdl->ByteOffset, v50);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        v51 = HsmpGetStreamSize(v3);
        LODWORD(v62) = v6;
        LODWORD(v61) = *(_DWORD *)(v3 + 28);
        ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_iqqLiiid)(
          *(_QWORD *)(v52 + 24),
          (LARGE_INTEGER)v65.QuadPart,
          v52,
          v64,
          a2,
          v3,
          v61,
          v51,
          (LARGE_INTEGER)v65.QuadPart,
          v53,
          v62);
      }
      v6 = (unsigned int)FltReadFileEx(*(_QWORD *)(v68 + 32), v67, &v69, v50, 0, 10, 0, 0, 0, 0, Mdl);
      HsmDbgBreakOnStatus(v6);
      if ( (int)v6 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          v54 = HsmpGetStreamSize(v3);
          v63 = v50;
          v19 = v64;
          ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD))WPP_SF_qqqLiiiDd)(
            *(_QWORD *)(v55 + 24),
            (LARGE_INTEGER)v69.QuadPart,
            v55,
            a1,
            a2,
            v3,
            *(_DWORD *)(v3 + 28),
            v54,
            v64,
            (LARGE_INTEGER)v69.QuadPart,
            v63,
            v6);
          v18 = 0;
          goto LABEL_45;
        }
LABEL_43:
        v18 = 0;
        goto LABEL_44;
      }
      v45.QuadPart = v69.QuadPart + v50;
      v65 = v45;
    }
    Mdl = IoAllocateMdl(0, SourceMdl->ByteCount, 0, 0, 0);
LABEL_71:
    v48 = v65;
    goto LABEL_72;
  }
  if ( (*(_BYTE *)(a1 + 48) & 0x1F) == 9 )
  {
    v23 = a2->Iopb;
    if ( v23->MajorFunction == 4 )
    {
      v24 = v23->Parameters.Read.ByteOffset;
      v25 = v24.QuadPart + v23->Parameters.Read.Length;
    }
    else
    {
      v26 = *(_QWORD *)(a1 + 64);
      v24 = *(LARGE_INTEGER *)(a1 + 56);
      if ( v26 == -1 )
        v25 = HsmpGetStreamSize(v3);
      else
        v25 = v26 + v24.QuadPart;
    }
    v27 = -(__int64)((v22 & 2) == 0) & 0xFFFFFFFFFFFFF000uLL & v24.QuadPart;
    v28 = (v22 & 2) == 0 ? 0x1000 : 0;
    v29 = -v28 & (v25 + v28 - 1);
  }
  else
  {
    v27 = 0;
    v29 = HsmpGetStreamSize(v3);
  }
  LOBYTE(v25) = 1;
  HsmpAcquireBitmapLock(v3, v25);
  LOBYTE(v30) = 1;
  v6 = (unsigned int)HsmpMarkModificationBitmapNoLock(v3, v27, v29, v30);
  HsmDbgBreakOnStatus(v6);
  if ( (int)v6 >= 0 )
  {
    v6 = (unsigned int)HsmpRpCommitNoLock(v68, v3, v67, 0, 0);
    HsmDbgBreakOnStatus(v6);
    if ( (int)v6 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v31 = HsmpGetStreamSize(v3);
        v33 = 26;
        goto LABEL_24;
      }
LABEL_30:
      v19 = v64;
      goto LABEL_31;
    }
    HsmpReleaseBitmapLock(v3);
    FltReleasePushLockEx(*(_QWORD *)(v3 + 16) + 24LL, 0);
    v74 = 0;
    goto LABEL_33;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_30;
  }
  v31 = HsmpGetStreamSize(v3);
  v33 = 25;
LABEL_24:
  v19 = v64;
  WPP_SF_qqLiqiqd(
    *(_QWORD *)(v32 + 24),
    v33,
    (unsigned int)WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids,
    v68,
    v3,
    *(_DWORD *)(v3 + 28),
    v31,
    v67,
    v64,
    a2,
    v6);
LABEL_31:
  HsmpReleaseBitmapLock(v3);
  v18 = 0;
LABEL_46:
  FltReleasePushLockEx(*(_QWORD *)(v3 + 16) + 24LL, 0);
LABEL_47:
  if ( Mdl )
    IoFreeMdl(Mdl);
  if ( (int)v6 < 0 )
    goto LABEL_7;
  if ( v20 == FLT_PREOP_COMPLETE )
    goto LABEL_51;
LABEL_52:
  v40 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, struct _FLT_CALLBACK_DATA *, _DWORD))(a1 + 144);
  if ( v40 )
  {
    v41 = v40(v68, v3, v67, v19, a2, v6);
    if ( v41 < 0 )
    {
      a2->IoStatus.Status = v41;
      v20 = FLT_PREOP_COMPLETE;
      a2->IoStatus.Information = 0;
    }
  }
  v42 = *(struct _KEVENT **)(a1 + 136);
  if ( v42 )
  {
    KeSetEvent(v42, 0, 0);
  }
  else
  {
    v60 = 0;
    if ( v20 == FLT_PREOP_COMPLETE )
    {
      HsmpReleaseUserRequestRundownProtection((PFLT_CONTEXT)v3);
    }
    else
    {
      v60 = (void *)v3;
      if ( *(_QWORD *)(a1 + 32) )
        v60 = *(void **)(a1 + 32);
    }
    LOBYTE(v13) = 1;
    HsmpTracePreCallbackExit(v20, (_DWORD)a2, (_DWORD)v60, v13, 0);
    FltCompletePendedPreOperation(a2, v20, v60);
  }
}

```

## disassembly

```asm
0x14007f994  mov     [rsp-8+arg_8], rbx
0x14007f999  push    rbp
0x14007f99a  push    rsi
0x14007f99b  push    rdi
0x14007f99c  push    r12
0x14007f99e  push    r13
0x14007f9a0  push    r14
0x14007f9a2  push    r15
0x14007f9a4  lea     rbp, [rsp-27h]
0x14007f9a9  sub     rsp, 0C0h
0x14007f9b0  mov     rbx, [rcx+78h]
0x14007f9b4  mov     rsi, rcx
0x14007f9b7  mov     r13d, [rcx+28h]
0x14007f9bb  xor     r15d, r15d
0x14007f9be  mov     edi, r8d
0x14007f9c1  mov     [rbp+57h+var_78], r15
0x14007f9c5  mov     r14, rdx
0x14007f9c8  mov     rax, [rbx+10h]
0x14007f9cc  mov     rcx, [rax+10h]
0x14007f9d0  mov     r12, [rax+20h]
0x14007f9d4  mov     rax, [rsi+10h]
0x14007f9d8  mov     [rbp+57h+var_58], rcx
0x14007f9dc  mov     ecx, r8d
0x14007f9df  mov     [rbp+57h+var_80], r12
0x14007f9e3  mov     [rbp+57h+var_60], rax
0x14007f9e7  call    HsmDbgBreakOnStatus
0x14007f9ec  test    edi, edi
0x14007f9ee  jns     loc_14007FA86
0x14007f9f4  mov     r13, cs:WPP_GLOBAL_Control
0x14007f9fb  lea     r15, WPP_GLOBAL_Control
0x14007fa02  cmp     r13, r15
0x14007fa05  jz      short loc_14007FA74
0x14007fa07  mov     eax, [r13+2Ch]
0x14007fa0b  test    al, 1
0x14007fa0d  jz      short loc_14007FA74
0x14007fa0f  cmp     byte ptr [r13+29h], 2
0x14007fa14  jb      short loc_14007FA74
0x14007fa16  mov     r11, [rsi+48h]
0x14007fa1a  mov     rcx, rbx
0x14007fa1d  call    HsmpGetStreamSize
0x14007fa22  mov     r9, [rsi+50h]
0x14007fa26  mov     edx, 18h
0x14007fa2b  mov     r10d, [rsi+30h]
0x14007fa2f  add     r9, r11
0x14007fa32  mov     rcx, [r13+18h]
0x14007fa36  mov     [rsp+0F0h+var_90], edi
0x14007fa3a  mov     [rsp+0F0h+var_98], r12
0x14007fa3f  mov     [rsp+0F0h+var_A0], rax
0x14007fa44  mov     eax, [rbx+1Ch]
0x14007fa47  mov     dword ptr [rsp+0F0h+var_A8], eax
0x14007fa4b  mov     [rsp+0F0h+var_B0], rbx
0x14007fa50  mov     [rsp+0F0h+var_B8], r14
0x14007fa55  mov     [rsp+0F0h+var_C0], r9
0x14007fa5a  mov     r9, rsi
0x14007fa5d  shr     r10d, 6
0x14007fa61  and     r10d, 7
0x14007fa65  mov     qword ptr [rsp+0F0h+Priority], r11
0x14007fa6a  mov     [rsp+0F0h+BugCheckOnFailure], r10d
0x14007fa6f  call    WPP_SF_qliiqqLiid
0x14007fa74  mov     r15, [rbp+57h+var_78]
0x14007fa78  mov     r13, r12
0x14007fa7b  mov     r12d, 4
0x14007fa81  jmp     loc_14007FD38
0x14007fa86  mov     eax, [rsi+30h]
0x14007fa89  mov     r12d, 4
0x14007fa8f  and     eax, 1Fh
0x14007fa92  mov     [rbp+57h+Mdl], r15
0x14007fa96  sub     eax, 9
0x14007fa99  mov     [rbp+57h+arg_10], r15b
0x14007fa9d  cmp     eax, 1
0x14007faa0  ja      loc_14007FC8B
0x14007faa6  test    dword ptr [rbx+1Ch], 400h
0x14007faad  jnz     loc_14007FC8B
0x14007fab3  mov     dl, 1
0x14007fab5  mov     rcx, rbx
0x14007fab8  call    HsmpAcquireReparseUpdateLock
0x14007fabd  mov     r8d, [rbx+1Ch]
0x14007fac1  mov     [rbp+57h+arg_10], 1
0x14007fac5  bt      r8d, 0Ah
0x14007faca  jb      loc_14007FC8B
0x14007fad0  mov     eax, [rsi+30h]
0x14007fad3  and     eax, 1Fh
0x14007fad6  cmp     al, 9
0x14007fad8  jnz     short loc_14007FB45
0x14007fada  mov     rax, [r14+10h]
0x14007fade  cmp     [rax+4], r12b
0x14007fae2  jnz     short loc_14007FAF0
0x14007fae4  mov     rdi, [rax+28h]
0x14007fae8  mov     edx, [rax+18h]
0x14007faeb  add     rdx, rdi
0x14007faee  jmp     short loc_14007FB0F
0x14007faf0  mov     rax, [rsi+40h]
0x14007faf4  mov     rdi, [rsi+38h]
0x14007faf8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007fafc  jnz     short loc_14007FB0B
0x14007fafe  mov     rcx, rbx
0x14007fb01  call    HsmpGetStreamSize
0x14007fb06  mov     rdx, rax
0x14007fb09  jmp     short loc_14007FB0F
0x14007fb0b  lea     rdx, [rax+rdi]
0x14007fb0f  and     r8d, 2
0x14007fb13  mov     eax, r8d
0x14007fb16  neg     eax
0x14007fb18  sbb     rcx, rcx
0x14007fb1b  not     rcx
0x14007fb1e  and     rcx, 0FFFFFFFFFFFFF000h
0x14007fb25  and     rdi, rcx
0x14007fb28  neg     r8d
0x14007fb2b  sbb     rax, rax
0x14007fb2e  not     rax
0x14007fb31  and     eax, 1000h
0x14007fb36  lea     r15, [rax-1]
0x14007fb3a  neg     rax
0x14007fb3d  add     r15, rdx
0x14007fb40  and     r15, rax
0x14007fb43  jmp     short loc_14007FB53
0x14007fb45  mov     rcx, rbx
0x14007fb48  mov     rdi, r15
0x14007fb4b  call    HsmpGetStreamSize
0x14007fb50  mov     r15, rax
0x14007fb53  mov     dl, 1
0x14007fb55  mov     rcx, rbx
0x14007fb58  call    HsmpAcquireBitmapLock
0x14007fb5d  mov     r9b, 1
0x14007fb60  mov     r8, r15
0x14007fb63  mov     rdx, rdi
0x14007fb66  mov     rcx, rbx
0x14007fb69  call    HsmpMarkModificationBitmapNoLock
0x14007fb6e  mov     ecx, eax
0x14007fb70  mov     edi, eax
0x14007fb72  call    HsmDbgBreakOnStatus
0x14007fb77  xor     r15d, r15d
0x14007fb7a  test    edi, edi
0x14007fb7c  jns     short loc_14007FBFB
0x14007fb7e  mov     r10, cs:WPP_GLOBAL_Control
0x14007fb85  lea     r15, WPP_GLOBAL_Control
0x14007fb8c  cmp     r10, r15
0x14007fb8f  jz      loc_14007FC54
0x14007fb95  mov     eax, [r10+2Ch]
0x14007fb99  test    al, 1
0x14007fb9b  jz      loc_14007FC54
0x14007fba1  cmp     byte ptr [r10+29h], 2
0x14007fba6  jb      loc_14007FC54
0x14007fbac  mov     rcx, rbx
0x14007fbaf  call    HsmpGetStreamSize
0x14007fbb4  mov     edx, 19h
0x14007fbb9  mov     rcx, [rbp+57h+var_60]
0x14007fbbd  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14007fbc4  mov     r13, [rbp+57h+var_80]
0x14007fbc8  mov     r9, [rbp+57h+var_58]
0x14007fbcc  mov     dword ptr [rsp+0F0h+var_A0], edi
0x14007fbd0  mov     [rsp+0F0h+var_A8], r14
0x14007fbd5  mov     [rsp+0F0h+var_B0], r13
0x14007fbda  mov     [rsp+0F0h+var_B8], rcx
0x14007fbdf  mov     rcx, [r10+18h]
0x14007fbe3  mov     [rsp+0F0h+var_C0], rax
0x14007fbe8  mov     eax, [rbx+1Ch]
0x14007fbeb  mov     [rsp+0F0h+Priority], eax
0x14007fbef  mov     qword ptr [rsp+0F0h+BugCheckOnFailure], rbx
0x14007fbf4  call    WPP_SF_qqLiqiqd
0x14007fbf9  jmp     short loc_14007FC58
0x14007fbfb  mov     r8, [rbp+57h+var_60]
0x14007fbff  xor     r9d, r9d
0x14007fc02  mov     rcx, [rbp+57h+var_58]
0x14007fc06  mov     rdx, rbx
0x14007fc09  mov     byte ptr [rsp+0F0h+BugCheckOnFailure], r15b
0x14007fc0e  call    HsmpRpCommitNoLock
0x14007fc13  mov     ecx, eax
0x14007fc15  mov     edi, eax
0x14007fc17  call    HsmDbgBreakOnStatus
0x14007fc1c  test    edi, edi
0x14007fc1e  jns     short loc_14007FC69
0x14007fc20  mov     r10, cs:WPP_GLOBAL_Control
0x14007fc27  lea     r15, WPP_GLOBAL_Control
0x14007fc2e  cmp     r10, r15
0x14007fc31  jz      short loc_14007FC54
0x14007fc33  mov     eax, [r10+2Ch]
0x14007fc37  test    al, 1
0x14007fc39  jz      short loc_14007FC54
0x14007fc3b  cmp     byte ptr [r10+29h], 2
0x14007fc40  jb      short loc_14007FC54
0x14007fc42  mov     rcx, rbx
0x14007fc45  call    HsmpGetStreamSize
0x14007fc4a  mov     edx, 1Ah
0x14007fc4f  jmp     loc_14007FBB9
0x14007fc54  mov     r13, [rbp+57h+var_80]
0x14007fc58  mov     rcx, rbx
0x14007fc5b  call    HsmpReleaseBitmapLock
0x14007fc60  mov     r15, [rbp+57h+var_78]
0x14007fc64  jmp     loc_14007FCFC
0x14007fc69  mov     rcx, rbx
0x14007fc6c  call    HsmpReleaseBitmapLock
0x14007fc71  mov     rcx, [rbx+10h]
0x14007fc75  xor     edx, edx
0x14007fc77  add     rcx, 18h
0x14007fc7b  call    cs:__imp_FltReleasePushLockEx
0x14007fc82  nop     dword ptr [rax+rax+00h]
0x14007fc87  mov     [rbp+57h+arg_10], r15b
0x14007fc8b  mov     rcx, [r14+10h]
0x14007fc8f  cmp     byte ptr [rcx+4], 3
0x14007fc93  jnz     loc_1400800C4
0x14007fc99  mov     eax, r13d
0x14007fc9c  and     eax, 0Fh
0x14007fc9f  cmp     al, 3
0x14007fca1  jnb     loc_1400800C4
0x14007fca7  bt      r13d, 8
0x14007fcac  jb      loc_1400800C4
0x14007fcb2  cmp     [rsi+80h], r15
0x14007fcb9  jnz     loc_14007FDA4
0x14007fcbf  mov     eax, [rsi+30h]
0x14007fcc2  test    al, 20h
0x14007fcc4  jz      short loc_14007FCEB
0x14007fcc6  mov     rdx, [rcx+28h]
0x14007fcca  mov     r15d, [rcx+18h]
0x14007fcce  mov     rcx, rbx
0x14007fcd1  add     r15, rdx
0x14007fcd4  call    HsmpGetStreamSize
0x14007fcd9  cmp     r15, rax
0x14007fcdc  jl      short loc_14007FCE6
0x14007fcde  call    HsmpGetStreamSize
0x14007fce3  mov     r15, rax
0x14007fce6  sub     r15, rdx
0x14007fce9  jmp     short loc_14007FCF2
0x14007fceb  mov     r12d, r15d
0x14007fcee  mov     r15, [rbp+57h+var_78]
0x14007fcf2  mov     r13, [rbp+57h+var_80]
0x14007fcf6  cmp     [rbp+57h+arg_10], 0
0x14007fcfa  jz      short loc_14007FD12
0x14007fcfc  mov     rcx, [rbx+10h]
0x14007fd00  xor     edx, edx
0x14007fd02  add     rcx, 18h
0x14007fd06  call    cs:__imp_FltReleasePushLockEx
0x14007fd0d  nop     dword ptr [rax+rax+00h]
0x14007fd12  mov     rax, [rbp+57h+Mdl]
0x14007fd16  test    rax, rax
0x14007fd19  jz      short loc_14007FD2A
0x14007fd1b  mov     rcx, rax; Mdl
0x14007fd1e  call    cs:__imp_IoFreeMdl
0x14007fd25  nop     dword ptr [rax+rax+00h]
0x14007fd2a  test    edi, edi
0x14007fd2c  js      loc_14007FA7B
0x14007fd32  cmp     r12d, 4
0x14007fd36  jnz     short loc_14007FD40
0x14007fd38  mov     [r14+18h], edi
0x14007fd3c  mov     [r14+20h], r15
0x14007fd40  mov     rax, [rsi+90h]
0x14007fd47  test    rax, rax
0x14007fd4a  jz      short loc_14007FD7E
0x14007fd4c  mov     r8, [rbp+57h+var_60]
0x14007fd50  mov     r9, r13
0x14007fd53  mov     rcx, [rbp+57h+var_58]
0x14007fd57  mov     rdx, rbx
0x14007fd5a  mov     [rsp+0F0h+Priority], edi
0x14007fd5e  mov     qword ptr [rsp+0F0h+BugCheckOnFailure], r14
0x14007fd63  call    _guard_dispatch_icall
0x14007fd68  test    eax, eax
0x14007fd6a  jns     short loc_14007FD7E
0x14007fd6c  mov     [r14+18h], eax
0x14007fd70  mov     r12d, 4
0x14007fd76  mov     qword ptr [r14+20h], 0
0x14007fd7e  mov     rcx, [rsi+88h]; Event
0x14007fd85  test    rcx, rcx
0x14007fd88  jz      loc_14008015E
0x14007fd8e  xor     r8d, r8d; Wait
0x14007fd91  xor     edx, edx; Increment
0x14007fd93  call    cs:__imp_KeSetEvent
0x14007fd9a  nop     dword ptr [rax+rax+00h]
0x14007fd9f  jmp     loc_1400801AE
0x14007fda4  mov     rcx, [rcx+38h]; MemoryDescriptorList
0x14007fda8  mov     [rbp+57h+SourceMdl], rcx
0x14007fdac  test    byte ptr [rcx+0Ah], 5
0x14007fdb0  jnz     short loc_14007FDD4
0x14007fdb2  xor     r9d, r9d; RequestedAddress
0x14007fdb5  mov     [rsp+0F0h+Priority], 40000010h; Priority
0x14007fdbd  xor     edx, edx; AccessMode
0x14007fdbf  mov     [rsp+0F0h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x14007fdc4  lea     r8d, [r9+1]; CacheType
0x14007fdc8  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007fdcf  nop     dword ptr [rax+rax+00h]
0x14007fdd4  mov     rax, [r14+10h]
0x14007fdd8  mov     [rbp+57h+var_48], r15
0x14007fddc  lea     r15, WPP_GLOBAL_Control
0x14007fde3  mov     rcx, [rax+28h]
0x14007fde7  mov     [rbp+57h+var_70], rcx
0x14007fdeb  mov     eax, [rax+18h]
0x14007fdee  add     rax, rcx
0x14007fdf1  mov     [rbp+57h+var_40], rax
0x14007fdf5  mov     r13d, 0FFFFFFFFh
0x14007fdfb  cmp     rcx, [rbp+57h+var_40]
0x14007fdff  jge     loc_1400800B3
0x14007fe05  mov     rcx, [rsi+80h]
0x14007fe0c  lea     rax, [rbp+57h+var_48]
0x14007fe10  lea     r9, [rbp+57h+arg_0]
0x14007fe14  mov     qword ptr [rsp+0F0h+BugCheckOnFailure], rax
0x14007fe19  lea     r8, [rbp+57h+var_40]
0x14007fe1d  mov     [rbp+57h+arg_0], 0
0x14007fe21  lea     rdx, [rbp+57h+var_70]
0x14007fe25  mov     [rbp+57h+var_50], 0
0x14007fe2d  call    HsmpBitmapQueryRange
0x14007fe32  cmp     [rbp+57h+arg_0], 0
  ... truncated ...
```
