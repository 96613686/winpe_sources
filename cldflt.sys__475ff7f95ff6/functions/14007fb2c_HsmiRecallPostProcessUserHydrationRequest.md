# HsmiRecallPostProcessUserHydrationRequest

- ea: `0x14007fb2c`
- end: `0x140080362`
- name: `HsmiRecallPostProcessUserHydrationRequest`
- size: `2102`
- prototype: `void __fastcall(__int64, struct _FLT_CALLBACK_DATA *, int)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x14008506c`

## callees

- `0x140001910`
- `0x140003c50`
- `0x140007ddc`
- `0x14000c180`
- `0x14000cd0c`
- `0x140017bf8`
- `0x140018448`
- `0x1400184ec`
- `0x14001859c`
- `0x14001e2a0`
- `0x140058ddc`
- `0x140059738`
- `0x1400652b4`
- `0x140067e24`
- `0x14006f28c`
- `0x1400704ac`
- `0x14007458c`
- `0x14007fb2c`

## import_xrefs

- `ntoskrnl!IoBuildPartialMdl` at `0x1400800fb`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400800fb`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400800d0`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400800d0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ff60`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14007ff60`
- `ntoskrnl!IoFreeMdl` at `0x14007feb6`
- `ntoskrnl!IoFreeMdl` at `0x14007feb6`
- `ntoskrnl!IoAllocateMdl` at `0x140080049`
- `ntoskrnl!IoAllocateMdl` at `0x140080049`
- `ntoskrnl!KeSetEvent` at `0x14007ff2b`
- `ntoskrnl!KeSetEvent` at `0x14007ff2b`
- `FLTMGR!FltReadFileEx` at `0x1400801a0`
- `FLTMGR!FltReadFileEx` at `0x1400801a0`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14008033a`
- `FLTMGR!FltCompletePendedPreOperation` at `0x14008033a`
- `FLTMGR!FltReleasePushLockEx` at `0x14007fe13`
- `FLTMGR!FltReleasePushLockEx` at `0x14007fe9e`
- `FLTMGR!FltReleasePushLockEx` at `0x14007fe13`
- `FLTMGR!FltReleasePushLockEx` at `0x14007fe9e`

## pseudocode

```c
void __fastcall HsmiRecallPostProcessUserHydrationRequest(__int64 a1, struct _FLT_CALLBACK_DATA *a2, int a3)
{
  __int64 v3; // rbx
  int v5; // r13d
  int v6; // edi
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
  __int64 (__fastcall *v40)(__int64, __int64, __int64, __int64, struct _FLT_CALLBACK_DATA *, int); // rax
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
  v6 = a3;
  v8 = *(_QWORD *)(v3 + 16);
  v9 = *(_QWORD *)(v8 + 16);
  v10 = *(_QWORD *)(v8 + 32);
  v11 = *(_QWORD *)(a1 + 16);
  v68 = v9;
  v64 = v10;
  v67 = v11;
  HsmDbgBreakOnStatus(a3);
  if ( v6 < 0 )
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
        v6 = -1073741595;
        HsmDbgBreakOnStatus(-1073741595);
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
      v6 = FltReadFileEx(*(_QWORD *)(v68 + 32), v67, &v69, v50, 0, 10, 0, 0, 0, 0, Mdl);
      HsmDbgBreakOnStatus(v6);
      if ( v6 < 0 )
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
  v6 = HsmpMarkModificationBitmapNoLock(v3, v27, v29, v30);
  HsmDbgBreakOnStatus(v6);
  if ( v6 >= 0 )
  {
    v6 = HsmpRpCommitNoLock(v68, v3, v67, 0, 0);
    HsmDbgBreakOnStatus(v6);
    if ( v6 < 0 )
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
  if ( v6 < 0 )
    goto LABEL_7;
  if ( v20 == FLT_PREOP_COMPLETE )
    goto LABEL_51;
LABEL_52:
  v40 = *(__int64 (__fastcall **)(__int64, __int64, __int64, __int64, struct _FLT_CALLBACK_DATA *, int))(a1 + 144);
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
0x14007fb2c  mov     [rsp-8+arg_8], rbx
0x14007fb31  push    rbp
0x14007fb32  push    rsi
0x14007fb33  push    rdi
0x14007fb34  push    r12
0x14007fb36  push    r13
0x14007fb38  push    r14
0x14007fb3a  push    r15
0x14007fb3c  lea     rbp, [rsp-27h]
0x14007fb41  sub     rsp, 0C0h
0x14007fb48  mov     rbx, [rcx+78h]
0x14007fb4c  mov     rsi, rcx
0x14007fb4f  mov     r13d, [rcx+28h]
0x14007fb53  xor     r15d, r15d
0x14007fb56  mov     edi, r8d
0x14007fb59  mov     [rbp+57h+var_78], r15
0x14007fb5d  mov     r14, rdx
0x14007fb60  mov     rax, [rbx+10h]
0x14007fb64  mov     rcx, [rax+10h]
0x14007fb68  mov     r12, [rax+20h]
0x14007fb6c  mov     rax, [rsi+10h]
0x14007fb70  mov     [rbp+57h+var_58], rcx
0x14007fb74  mov     ecx, r8d
0x14007fb77  mov     [rbp+57h+var_80], r12
0x14007fb7b  mov     [rbp+57h+var_60], rax
0x14007fb7f  call    HsmDbgBreakOnStatus
0x14007fb84  test    edi, edi
0x14007fb86  jns     loc_14007FC1E
0x14007fb8c  mov     r13, cs:WPP_GLOBAL_Control
0x14007fb93  lea     r15, WPP_GLOBAL_Control
0x14007fb9a  cmp     r13, r15
0x14007fb9d  jz      short loc_14007FC0C
0x14007fb9f  mov     eax, [r13+2Ch]
0x14007fba3  test    al, 1
0x14007fba5  jz      short loc_14007FC0C
0x14007fba7  cmp     byte ptr [r13+29h], 2
0x14007fbac  jb      short loc_14007FC0C
0x14007fbae  mov     r11, [rsi+48h]
0x14007fbb2  mov     rcx, rbx
0x14007fbb5  call    HsmpGetStreamSize
0x14007fbba  mov     r9, [rsi+50h]
0x14007fbbe  mov     edx, 18h
0x14007fbc3  mov     r10d, [rsi+30h]
0x14007fbc7  add     r9, r11
0x14007fbca  mov     rcx, [r13+18h]
0x14007fbce  mov     [rsp+0F0h+var_90], edi
0x14007fbd2  mov     [rsp+0F0h+var_98], r12
0x14007fbd7  mov     [rsp+0F0h+var_A0], rax
0x14007fbdc  mov     eax, [rbx+1Ch]
0x14007fbdf  mov     dword ptr [rsp+0F0h+var_A8], eax
0x14007fbe3  mov     [rsp+0F0h+var_B0], rbx
0x14007fbe8  mov     [rsp+0F0h+var_B8], r14
0x14007fbed  mov     [rsp+0F0h+var_C0], r9
0x14007fbf2  mov     r9, rsi
0x14007fbf5  shr     r10d, 6
0x14007fbf9  and     r10d, 7
0x14007fbfd  mov     qword ptr [rsp+0F0h+Priority], r11
0x14007fc02  mov     [rsp+0F0h+BugCheckOnFailure], r10d
0x14007fc07  call    WPP_SF_qliiqqLiid
0x14007fc0c  mov     r15, [rbp+57h+var_78]
0x14007fc10  mov     r13, r12
0x14007fc13  mov     r12d, 4
0x14007fc19  jmp     loc_14007FED0
0x14007fc1e  mov     eax, [rsi+30h]
0x14007fc21  mov     r12d, 4
0x14007fc27  and     eax, 1Fh
0x14007fc2a  mov     [rbp+57h+Mdl], r15
0x14007fc2e  sub     eax, 9
0x14007fc31  mov     [rbp+57h+arg_10], r15b
0x14007fc35  cmp     eax, 1
0x14007fc38  ja      loc_14007FE23
0x14007fc3e  test    dword ptr [rbx+1Ch], 400h
0x14007fc45  jnz     loc_14007FE23
0x14007fc4b  mov     dl, 1
0x14007fc4d  mov     rcx, rbx
0x14007fc50  call    HsmpAcquireReparseUpdateLock
0x14007fc55  mov     r8d, [rbx+1Ch]
0x14007fc59  mov     [rbp+57h+arg_10], 1
0x14007fc5d  bt      r8d, 0Ah
0x14007fc62  jb      loc_14007FE23
0x14007fc68  mov     eax, [rsi+30h]
0x14007fc6b  and     eax, 1Fh
0x14007fc6e  cmp     al, 9
0x14007fc70  jnz     short loc_14007FCDD
0x14007fc72  mov     rax, [r14+10h]
0x14007fc76  cmp     [rax+4], r12b
0x14007fc7a  jnz     short loc_14007FC88
0x14007fc7c  mov     rdi, [rax+28h]
0x14007fc80  mov     edx, [rax+18h]
0x14007fc83  add     rdx, rdi
0x14007fc86  jmp     short loc_14007FCA7
0x14007fc88  mov     rax, [rsi+40h]
0x14007fc8c  mov     rdi, [rsi+38h]
0x14007fc90  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14007fc94  jnz     short loc_14007FCA3
0x14007fc96  mov     rcx, rbx
0x14007fc99  call    HsmpGetStreamSize
0x14007fc9e  mov     rdx, rax
0x14007fca1  jmp     short loc_14007FCA7
0x14007fca3  lea     rdx, [rax+rdi]
0x14007fca7  and     r8d, 2
0x14007fcab  mov     eax, r8d
0x14007fcae  neg     eax
0x14007fcb0  sbb     rcx, rcx
0x14007fcb3  not     rcx
0x14007fcb6  and     rcx, 0FFFFFFFFFFFFF000h
0x14007fcbd  and     rdi, rcx
0x14007fcc0  neg     r8d
0x14007fcc3  sbb     rax, rax
0x14007fcc6  not     rax
0x14007fcc9  and     eax, 1000h
0x14007fcce  lea     r15, [rax-1]
0x14007fcd2  neg     rax
0x14007fcd5  add     r15, rdx
0x14007fcd8  and     r15, rax
0x14007fcdb  jmp     short loc_14007FCEB
0x14007fcdd  mov     rcx, rbx
0x14007fce0  mov     rdi, r15
0x14007fce3  call    HsmpGetStreamSize
0x14007fce8  mov     r15, rax
0x14007fceb  mov     dl, 1
0x14007fced  mov     rcx, rbx
0x14007fcf0  call    HsmpAcquireBitmapLock
0x14007fcf5  mov     r9b, 1
0x14007fcf8  mov     r8, r15
0x14007fcfb  mov     rdx, rdi
0x14007fcfe  mov     rcx, rbx
0x14007fd01  call    HsmpMarkModificationBitmapNoLock
0x14007fd06  mov     ecx, eax
0x14007fd08  mov     edi, eax
0x14007fd0a  call    HsmDbgBreakOnStatus
0x14007fd0f  xor     r15d, r15d
0x14007fd12  test    edi, edi
0x14007fd14  jns     short loc_14007FD93
0x14007fd16  mov     r10, cs:WPP_GLOBAL_Control
0x14007fd1d  lea     r15, WPP_GLOBAL_Control
0x14007fd24  cmp     r10, r15
0x14007fd27  jz      loc_14007FDEC
0x14007fd2d  mov     eax, [r10+2Ch]
0x14007fd31  test    al, 1
0x14007fd33  jz      loc_14007FDEC
0x14007fd39  cmp     byte ptr [r10+29h], 2
0x14007fd3e  jb      loc_14007FDEC
0x14007fd44  mov     rcx, rbx
0x14007fd47  call    HsmpGetStreamSize
0x14007fd4c  mov     edx, 19h
0x14007fd51  mov     rcx, [rbp+57h+var_60]
0x14007fd55  lea     r8, WPP_44e2e78ba36e3b17695231a1688fe36a_Traceguids
0x14007fd5c  mov     r13, [rbp+57h+var_80]
0x14007fd60  mov     r9, [rbp+57h+var_58]
0x14007fd64  mov     dword ptr [rsp+0F0h+var_A0], edi
0x14007fd68  mov     [rsp+0F0h+var_A8], r14
0x14007fd6d  mov     [rsp+0F0h+var_B0], r13
0x14007fd72  mov     [rsp+0F0h+var_B8], rcx
0x14007fd77  mov     rcx, [r10+18h]
0x14007fd7b  mov     [rsp+0F0h+var_C0], rax
0x14007fd80  mov     eax, [rbx+1Ch]
0x14007fd83  mov     [rsp+0F0h+Priority], eax
0x14007fd87  mov     qword ptr [rsp+0F0h+BugCheckOnFailure], rbx
0x14007fd8c  call    WPP_SF_qqLiqiqd
0x14007fd91  jmp     short loc_14007FDF0
0x14007fd93  mov     r8, [rbp+57h+var_60]
0x14007fd97  xor     r9d, r9d
0x14007fd9a  mov     rcx, [rbp+57h+var_58]
0x14007fd9e  mov     rdx, rbx
0x14007fda1  mov     byte ptr [rsp+0F0h+BugCheckOnFailure], r15b
0x14007fda6  call    HsmpRpCommitNoLock
0x14007fdab  mov     ecx, eax
0x14007fdad  mov     edi, eax
0x14007fdaf  call    HsmDbgBreakOnStatus
0x14007fdb4  test    edi, edi
0x14007fdb6  jns     short loc_14007FE01
0x14007fdb8  mov     r10, cs:WPP_GLOBAL_Control
0x14007fdbf  lea     r15, WPP_GLOBAL_Control
0x14007fdc6  cmp     r10, r15
0x14007fdc9  jz      short loc_14007FDEC
0x14007fdcb  mov     eax, [r10+2Ch]
0x14007fdcf  test    al, 1
0x14007fdd1  jz      short loc_14007FDEC
0x14007fdd3  cmp     byte ptr [r10+29h], 2
0x14007fdd8  jb      short loc_14007FDEC
0x14007fdda  mov     rcx, rbx
0x14007fddd  call    HsmpGetStreamSize
0x14007fde2  mov     edx, 1Ah
0x14007fde7  jmp     loc_14007FD51
0x14007fdec  mov     r13, [rbp+57h+var_80]
0x14007fdf0  mov     rcx, rbx
0x14007fdf3  call    HsmpReleaseBitmapLock
0x14007fdf8  mov     r15, [rbp+57h+var_78]
0x14007fdfc  jmp     loc_14007FE94
0x14007fe01  mov     rcx, rbx
0x14007fe04  call    HsmpReleaseBitmapLock
0x14007fe09  mov     rcx, [rbx+10h]
0x14007fe0d  xor     edx, edx
0x14007fe0f  add     rcx, 18h
0x14007fe13  call    cs:__imp_FltReleasePushLockEx
0x14007fe1a  nop     dword ptr [rax+rax+00h]
0x14007fe1f  mov     [rbp+57h+arg_10], r15b
0x14007fe23  mov     rcx, [r14+10h]
0x14007fe27  cmp     byte ptr [rcx+4], 3
0x14007fe2b  jnz     loc_14008025C
0x14007fe31  mov     eax, r13d
0x14007fe34  and     eax, 0Fh
0x14007fe37  cmp     al, 3
0x14007fe39  jnb     loc_14008025C
0x14007fe3f  bt      r13d, 8
0x14007fe44  jb      loc_14008025C
0x14007fe4a  cmp     [rsi+80h], r15
0x14007fe51  jnz     loc_14007FF3C
0x14007fe57  mov     eax, [rsi+30h]
0x14007fe5a  test    al, 20h
0x14007fe5c  jz      short loc_14007FE83
0x14007fe5e  mov     rdx, [rcx+28h]
0x14007fe62  mov     r15d, [rcx+18h]
0x14007fe66  mov     rcx, rbx
0x14007fe69  add     r15, rdx
0x14007fe6c  call    HsmpGetStreamSize
0x14007fe71  cmp     r15, rax
0x14007fe74  jl      short loc_14007FE7E
0x14007fe76  call    HsmpGetStreamSize
0x14007fe7b  mov     r15, rax
0x14007fe7e  sub     r15, rdx
0x14007fe81  jmp     short loc_14007FE8A
0x14007fe83  mov     r12d, r15d
0x14007fe86  mov     r15, [rbp+57h+var_78]
0x14007fe8a  mov     r13, [rbp+57h+var_80]
0x14007fe8e  cmp     [rbp+57h+arg_10], 0
0x14007fe92  jz      short loc_14007FEAA
0x14007fe94  mov     rcx, [rbx+10h]
0x14007fe98  xor     edx, edx
0x14007fe9a  add     rcx, 18h
0x14007fe9e  call    cs:__imp_FltReleasePushLockEx
0x14007fea5  nop     dword ptr [rax+rax+00h]
0x14007feaa  mov     rax, [rbp+57h+Mdl]
0x14007feae  test    rax, rax
0x14007feb1  jz      short loc_14007FEC2
0x14007feb3  mov     rcx, rax; Mdl
0x14007feb6  call    cs:__imp_IoFreeMdl
0x14007febd  nop     dword ptr [rax+rax+00h]
0x14007fec2  test    edi, edi
0x14007fec4  js      loc_14007FC13
0x14007feca  cmp     r12d, 4
0x14007fece  jnz     short loc_14007FED8
0x14007fed0  mov     [r14+18h], edi
0x14007fed4  mov     [r14+20h], r15
0x14007fed8  mov     rax, [rsi+90h]
0x14007fedf  test    rax, rax
0x14007fee2  jz      short loc_14007FF16
0x14007fee4  mov     r8, [rbp+57h+var_60]
0x14007fee8  mov     r9, r13
0x14007feeb  mov     rcx, [rbp+57h+var_58]
0x14007feef  mov     rdx, rbx
0x14007fef2  mov     [rsp+0F0h+Priority], edi
0x14007fef6  mov     qword ptr [rsp+0F0h+BugCheckOnFailure], r14
0x14007fefb  call    _guard_dispatch_icall
0x14007ff00  test    eax, eax
0x14007ff02  jns     short loc_14007FF16
0x14007ff04  mov     [r14+18h], eax
0x14007ff08  mov     r12d, 4
0x14007ff0e  mov     qword ptr [r14+20h], 0
0x14007ff16  mov     rcx, [rsi+88h]; Event
0x14007ff1d  test    rcx, rcx
0x14007ff20  jz      loc_1400802F6
0x14007ff26  xor     r8d, r8d; Wait
0x14007ff29  xor     edx, edx; Increment
0x14007ff2b  call    cs:__imp_KeSetEvent
0x14007ff32  nop     dword ptr [rax+rax+00h]
0x14007ff37  jmp     loc_140080346
0x14007ff3c  mov     rcx, [rcx+38h]; MemoryDescriptorList
0x14007ff40  mov     [rbp+57h+SourceMdl], rcx
0x14007ff44  test    byte ptr [rcx+0Ah], 5
0x14007ff48  jnz     short loc_14007FF6C
0x14007ff4a  xor     r9d, r9d; RequestedAddress
0x14007ff4d  mov     [rsp+0F0h+Priority], 40000010h; Priority
0x14007ff55  xor     edx, edx; AccessMode
0x14007ff57  mov     [rsp+0F0h+BugCheckOnFailure], r15d; BugCheckOnFailure
0x14007ff5c  lea     r8d, [r9+1]; CacheType
0x14007ff60  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14007ff67  nop     dword ptr [rax+rax+00h]
0x14007ff6c  mov     rax, [r14+10h]
0x14007ff70  mov     [rbp+57h+var_48], r15
0x14007ff74  lea     r15, WPP_GLOBAL_Control
0x14007ff7b  mov     rcx, [rax+28h]
0x14007ff7f  mov     [rbp+57h+var_70], rcx
0x14007ff83  mov     eax, [rax+18h]
0x14007ff86  add     rax, rcx
0x14007ff89  mov     [rbp+57h+var_40], rax
0x14007ff8d  mov     r13d, 0FFFFFFFFh
0x14007ff93  cmp     rcx, [rbp+57h+var_40]
0x14007ff97  jge     loc_14008024B
0x14007ff9d  mov     rcx, [rsi+80h]
0x14007ffa4  lea     rax, [rbp+57h+var_48]
0x14007ffa8  lea     r9, [rbp+57h+arg_0]
0x14007ffac  mov     qword ptr [rsp+0F0h+BugCheckOnFailure], rax
0x14007ffb1  lea     r8, [rbp+57h+var_40]
0x14007ffb5  mov     [rbp+57h+arg_0], 0
0x14007ffb9  lea     rdx, [rbp+57h+var_70]
0x14007ffbd  mov     [rbp+57h+var_50], 0
0x14007ffc5  call    HsmpBitmapQueryRange
0x14007ffca  cmp     [rbp+57h+arg_0], 0
  ... truncated ...
```
