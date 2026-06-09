# HsmiOpUpdatePlaceholderDirectory

- ea: `0x14007af2c`
- end: `0x14007b5e5`
- name: `HsmiOpUpdatePlaceholderDirectory`
- size: `1721`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007a9c0`

## callees

- `0x140003c50`
- `0x140009ed4`
- `0x14000a048`
- `0x140015248`
- `0x14001d9a8`
- `0x14001e140`
- `0x14001e280`
- `0x140052454`
- `0x140058cbc`
- `0x140059618`
- `0x14005cd20`
- `0x140067d04`
- `0x140075cd0`
- `0x140075d4c`
- `0x140075eb8`
- `0x14007af2c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007b132`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b132`
- `ntoskrnl!ExAllocatePool2` at `0x14007b408`
- `ntoskrnl!ExAllocatePool2` at `0x14007b408`
- `FLTMGR!FltSetInformationFile` at `0x14007b393`
- `FLTMGR!FltSetInformationFile` at `0x14007b393`
- `FLTMGR!FltReleasePushLockEx` at `0x14007b10d`
- `FLTMGR!FltReleasePushLockEx` at `0x14007b4cf`
- `FLTMGR!FltReleasePushLockEx` at `0x14007b10d`
- `FLTMGR!FltReleasePushLockEx` at `0x14007b4cf`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b05e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b479`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b4a6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b4f1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b05e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b479`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b4a6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b4f1`

## pseudocode

```c
__int64 __fastcall HsmiOpUpdatePlaceholderDirectory(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        int a4,
        void *a5,
        int a6,
        _DWORD *a7,
        _QWORD *a8,
        _QWORD *a9,
        _QWORD *a10)
{
  __int64 v13; // rax
  __int64 v14; // rdi
  int SyncPolicy; // ebx
  char StreamSize; // al
  __int64 v17; // r10
  PDEVICE_OBJECT v18; // r8
  __int64 v19; // rdx
  char v20; // di
  char v22; // al
  __int64 v23; // r10
  int v24; // edx
  char v25; // di
  __int64 v26; // rdx
  PDEVICE_OBJECT v27; // r8
  __int64 v28; // rdx
  void *v29; // rdi
  size_t v30; // rbx
  void *Pool2; // rax
  PVOID v32; // rbx
  __int64 v33; // rcx
  int v34; // eax
  unsigned int v35; // eax
  char v36; // [rsp+41h] [rbp-88h]
  int v37; // [rsp+44h] [rbp-85h] BYREF
  __int64 v38; // [rsp+48h] [rbp-81h]
  size_t Size; // [rsp+50h] [rbp-79h]
  PVOID P; // [rsp+58h] [rbp-71h]
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp-69h]
  int v42; // [rsp+68h] [rbp-61h]
  _QWORD *v43; // [rsp+70h] [rbp-59h]
  _QWORD *v44; // [rsp+78h] [rbp-51h]
  _QWORD *v45; // [rsp+80h] [rbp-49h]
  _DWORD *v46; // [rsp+88h] [rbp-41h]
  void *Src; // [rsp+90h] [rbp-39h]
  __int128 FileInformation; // [rsp+98h] [rbp-31h] BYREF
  __int128 v49; // [rsp+A8h] [rbp-21h]
  __int64 v50; // [rsp+B8h] [rbp-11h]

  Src = a5;
  LODWORD(Size) = a6;
  v46 = a7;
  v44 = a8;
  v43 = a9;
  v13 = *(_QWORD *)(a2 + 16);
  v45 = a10;
  FileObject = a3;
  v37 = 0;
  v14 = *(_QWORD *)(v13 + 32);
  v50 = 0;
  v38 = v14;
  FileInformation = 0;
  v49 = 0;
  SyncPolicy = HsmpAcquireSyncOpRundownProtection((PFLT_CONTEXT)a2, 0);
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a2);
      WPP_SF_qLiid(
        *(_QWORD *)(v17 + 24),
        37,
        (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        *(_DWORD *)(a2 + 28),
        StreamSize,
        v14,
        SyncPolicy);
    }
    return (unsigned int)SyncPolicy;
  }
  P = 0;
  v36 = 0;
  if ( (a4 & 2) != 0 )
  {
    HsmpWaitForUserRequestRundownRelease(a2);
    v36 = 1;
  }
  FltAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
  SyncPolicy = HsmpCldGetSyncPolicy(a1, a2, (_DWORD)FileObject, 5, (__int64)&v37);
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_14;
    }
    v19 = 38;
    goto LABEL_13;
  }
  v42 = a4 & 0x20;
  if ( (v37 & 0xF0u) >= 0x40 && (a4 & 0x20) != 0 )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_14;
    }
    v22 = HsmpGetStreamSize(a2);
    v24 = 39;
    goto LABEL_28;
  }
  v37 = a4 & 0x80;
  if ( (a4 & 0x80) != 0 && ((a4 & 0x20) != 0 || (*(_DWORD *)(a2 + 28) & 0x100) == 0 && (a4 & 0x40) == 0) )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(3221278475LL);
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_14;
    }
    v22 = HsmpGetStreamSize(a2);
    v24 = 40;
LABEL_28:
    WPP_SF_qLiid(
      *(_QWORD *)(v23 + 24),
      v24,
      (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
      a2,
      *(_DWORD *)(a2 + 28),
      v22,
      v38,
      11);
    goto LABEL_14;
  }
  if ( (a4 & 8) == 0 || (*(_DWORD *)(a2 + 28) & 0x2000) != 0 )
  {
    v25 = 0;
    if ( v43 )
    {
      v25 = 1;
      *((_QWORD *)&v49 + 1) = *v43;
      *(_QWORD *)&v49 = *((_QWORD *)&v49 + 1);
    }
    if ( v44 )
    {
      v25 = 1;
      *(_QWORD *)&FileInformation = *v44;
    }
    if ( v45 )
    {
      v25 = 1;
      *((_QWORD *)&FileInformation + 1) = *v45;
    }
    if ( v46 )
    {
      v25 = 1;
      LODWORD(v50) = *v46;
    }
    SyncPolicy = HsmpPrepareForMgmtOperation(a1, FileObject, 8, 0);
    HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_14;
      }
      v28 = 42;
      goto LABEL_56;
    }
    if ( v25 )
    {
      SyncPolicy = FltSetInformationFile(
                     *(PFLT_INSTANCE *)(a1 + 32),
                     FileObject,
                     &FileInformation,
                     0x28u,
                     FileBasicInformation);
      HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_14;
        }
        v28 = 43;
        goto LABEL_56;
      }
    }
    v29 = Src;
    if ( Src && (_DWORD)Size )
    {
      v30 = (unsigned int)Size;
      Pool2 = (void *)ExAllocatePool2(258, (unsigned int)Size, 1766224712);
      P = Pool2;
      if ( !Pool2 )
      {
        SyncPolicy = -1073741670;
        HsmDbgBreakOnStatus(3221225626LL);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_14;
        }
        v28 = 44;
LABEL_56:
        WPP_SF_qqLid(v27->AttachedDevice, v28, v27, a1, a2, *(_DWORD *)(a2 + 28), v38, SyncPolicy);
        goto LABEL_14;
      }
      memmove(Pool2, v29, v30);
      v32 = P;
      FltAcquirePushLockExclusiveEx(a2 + 64, 0);
      P = *(PVOID *)(a2 + 48);
      *(_DWORD *)(a2 + 56) = Size;
      *(_QWORD *)(a2 + 48) = v32;
    }
    else
    {
      if ( !v37 )
        goto LABEL_74;
      FltAcquirePushLockExclusiveEx(a2 + 64, 0);
      P = *(PVOID *)(a2 + 48);
      *(_QWORD *)(a2 + 48) = 0;
      *(_DWORD *)(a2 + 56) = 0;
    }
    FltReleasePushLockEx(a2 + 64, 0);
LABEL_74:
    *(_DWORD *)(a2 + 28) |= 1u;
    v33 = *(_QWORD *)(a2 + 160);
    if ( v33 )
      FltAcquirePushLockExclusiveEx(v33 + 40, 0);
    v20 = 1;
    if ( (a4 & 1) != 0 )
    {
      LOBYTE(v26) = 1;
      HsmpSetInSyncNoLock(a2, v26);
    }
    if ( (a4 & 0x100) != 0 )
      HsmpSetInSyncNoLock(a2, 0);
    if ( (a4 & 0x400) != 0 )
      *(_DWORD *)(a2 + 28) |= 0x8000u;
    if ( (a4 & 0x800000) != 0 )
      *(_DWORD *)(a2 + 28) &= ~0x8000u;
    *(_DWORD *)(a2 + 28) |= 0x280u;
    v34 = *(_DWORD *)(a2 + 28);
    if ( v42 )
    {
      v35 = v34 & 0xFFFFFEBF;
    }
    else
    {
      if ( (a4 & 0x40) == 0 )
      {
LABEL_89:
        SyncPolicy = HsmpRpCommitNoLock(a1, a2, FileObject, 1, 0);
        HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
        if ( SyncPolicy < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqLid(
            WPP_GLOBAL_Control->AttachedDevice,
            45,
            WPP_GLOBAL_Control,
            a1,
            a2,
            *(_DWORD *)(a2 + 28),
            v38,
            SyncPolicy);
        }
        goto LABEL_15;
      }
      v35 = v34 | 0x140;
    }
    *(_DWORD *)(a2 + 28) = v35;
    goto LABEL_89;
  }
  SyncPolicy = -1073688824;
  HsmDbgBreakOnStatus(3221278472LL);
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
  {
    goto LABEL_14;
  }
  v19 = 41;
LABEL_13:
  WPP_SF_qqLid(v18->AttachedDevice, v19, v18, a1, a2, *(_DWORD *)(a2 + 28), v14, SyncPolicy);
LABEL_14:
  v20 = 0;
LABEL_15:
  if ( v36 )
    HsmpReInitializeUserRequestRundownProtection(a2);
  if ( v20 )
    HsmpReleaseBitmapLock(a2);
  FltReleasePushLockEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
  HsmpReleaseSyncOpRundownProtection((PFLT_CONTEXT)a2);
  if ( P )
    ExFreePoolWithTag(P, 0x69467348u);
  return (unsigned int)SyncPolicy;
}

```

## disassembly

```asm
0x14007af2c  mov     [rsp-8+arg_18], rbx
0x14007af31  push    rbp
0x14007af32  push    rsi
0x14007af33  push    rdi
0x14007af34  push    r12
0x14007af36  push    r13
0x14007af38  lea     rbp, [rsp-7]
0x14007af3d  sub     rsp, 0D0h
0x14007af44  mov     rax, cs:__security_cookie
0x14007af4b  xor     rax, rsp
0x14007af4e  mov     [rbp+27h+var_30], rax
0x14007af52  mov     rax, [rbp+27h+arg_20]
0x14007af56  mov     r13, rcx
0x14007af59  mov     rcx, [rbp+27h+arg_48]
0x14007af5d  mov     rsi, rdx
0x14007af60  mov     [rbp+27h+Src], rax
0x14007af64  xorps   xmm0, xmm0
0x14007af67  mov     eax, [rbp+27h+arg_28]
0x14007af6a  mov     r12d, r9d
0x14007af6d  mov     dword ptr [rbp+27h+Size], eax
0x14007af70  mov     rax, [rbp+27h+arg_30]
0x14007af74  mov     [rbp+27h+var_68], rax
0x14007af78  mov     rax, [rbp+27h+arg_38]
0x14007af7c  mov     [rbp+27h+var_78], rax
0x14007af80  mov     rax, [rbp+27h+arg_40]
0x14007af84  mov     [rbp+27h+var_80], rax
0x14007af88  mov     rax, [rdx+10h]
0x14007af8c  xor     edx, edx; CallbackData
0x14007af8e  mov     [rbp+27h+var_70], rcx
0x14007af92  mov     rcx, rsi; Context
0x14007af95  mov     [rbp+27h+FileObject], r8
0x14007af99  mov     [rsp+0F0h+var_AC], 0
0x14007afa1  mov     rdi, [rax+20h]
0x14007afa5  xor     eax, eax
0x14007afa7  mov     [rbp+27h+var_38], rax
0x14007afab  mov     [rsp+0F0h+var_A8], rdi
0x14007afb0  movups  [rbp+27h+FileInformation], xmm0
0x14007afb4  movups  [rbp+27h+var_48], xmm0
0x14007afb8  call    HsmpAcquireSyncOpRundownProtection
0x14007afbd  mov     ecx, eax
0x14007afbf  mov     ebx, eax
0x14007afc1  call    HsmDbgBreakOnStatus
0x14007afc6  test    ebx, ebx
0x14007afc8  jns     short loc_14007B033
0x14007afca  mov     r10, cs:WPP_GLOBAL_Control
0x14007afd1  lea     rcx, WPP_GLOBAL_Control
0x14007afd8  cmp     r10, rcx
0x14007afdb  jz      loc_14007B13E
0x14007afe1  mov     ecx, [r10+2Ch]
0x14007afe5  test    cl, 1
0x14007afe8  jz      loc_14007B13E
0x14007afee  cmp     byte ptr [r10+29h], 2
0x14007aff3  jb      loc_14007B13E
0x14007aff9  mov     rcx, rsi
0x14007affc  call    HsmpGetStreamSize
0x14007b001  mov     rcx, [r10+18h]
0x14007b005  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007b00c  mov     [rsp+0F0h+var_B8], ebx
0x14007b010  mov     edx, 25h ; '%'
0x14007b015  mov     [rsp+0F0h+var_C0], rdi
0x14007b01a  mov     r9, rsi
0x14007b01d  mov     [rsp+0F0h+var_C8], rax
0x14007b022  mov     eax, [rsi+1Ch]
0x14007b025  mov     [rsp+0F0h+FileInformationClass], eax
0x14007b029  call    WPP_SF_qLiid
0x14007b02e  jmp     loc_14007B13E
0x14007b033  xor     eax, eax
0x14007b035  mov     [rbp+27h+P], rax
0x14007b039  mov     [rsp+0F0h+var_B0], al
0x14007b03d  mov     [rsp+0F0h+var_AF], al
0x14007b041  test    r12b, 2
0x14007b045  jz      short loc_14007B054
0x14007b047  mov     rcx, rsi
0x14007b04a  call    HsmpWaitForUserRequestRundownRelease
0x14007b04f  mov     [rsp+0F0h+var_AF], 1
0x14007b054  mov     rcx, [rsi+10h]
0x14007b058  xor     edx, edx
0x14007b05a  add     rcx, 18h
0x14007b05e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14007b065  nop     dword ptr [rax+rax+00h]
0x14007b06a  mov     r8, [rbp+27h+FileObject]
0x14007b06e  lea     rax, [rsp+0F0h+var_AC]
0x14007b073  mov     r9d, 5
0x14007b079  mov     qword ptr [rsp+0F0h+FileInformationClass], rax
0x14007b07e  mov     rdx, rsi
0x14007b081  mov     rcx, r13
0x14007b084  call    HsmpCldGetSyncPolicy
0x14007b089  mov     ecx, eax
0x14007b08b  mov     ebx, eax
0x14007b08d  call    HsmDbgBreakOnStatus
0x14007b092  test    ebx, ebx
0x14007b094  jns     loc_14007B164
0x14007b09a  mov     r8, cs:WPP_GLOBAL_Control
0x14007b0a1  lea     rcx, WPP_GLOBAL_Control
0x14007b0a8  cmp     r8, rcx
0x14007b0ab  jz      short loc_14007B0E2
0x14007b0ad  mov     eax, [r8+2Ch]
0x14007b0b1  test    al, 1
0x14007b0b3  jz      short loc_14007B0E2
0x14007b0b5  cmp     byte ptr [r8+29h], 2
0x14007b0ba  jb      short loc_14007B0E2
0x14007b0bc  mov     edx, 26h ; '&'
0x14007b0c1  mov     [rsp+0F0h+var_B8], ebx
0x14007b0c5  mov     [rsp+0F0h+var_C0], rdi
0x14007b0ca  mov     eax, [rsi+1Ch]
0x14007b0cd  mov     r9, r13
0x14007b0d0  mov     rcx, [r8+18h]
0x14007b0d4  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14007b0d8  mov     qword ptr [rsp+0F0h+FileInformationClass], rsi
0x14007b0dd  call    WPP_SF_qqLid
0x14007b0e2  mov     dil, [rsp+0F0h+var_B0]
0x14007b0e7  cmp     [rsp+0F0h+var_AF], 0
0x14007b0ec  jz      short loc_14007B0F6
0x14007b0ee  mov     rcx, rsi
0x14007b0f1  call    HsmpReInitializeUserRequestRundownProtection
0x14007b0f6  test    dil, dil
0x14007b0f9  jz      short loc_14007B103
0x14007b0fb  mov     rcx, rsi
0x14007b0fe  call    HsmpReleaseBitmapLock
0x14007b103  mov     rcx, [rsi+10h]
0x14007b107  xor     edx, edx
0x14007b109  add     rcx, 18h
0x14007b10d  call    cs:__imp_FltReleasePushLockEx
0x14007b114  nop     dword ptr [rax+rax+00h]
0x14007b119  mov     rcx, rsi; Context
0x14007b11c  call    HsmpReleaseSyncOpRundownProtection
0x14007b121  mov     rax, [rbp+27h+P]
0x14007b125  test    rax, rax
0x14007b128  jz      short loc_14007B13E
0x14007b12a  mov     edx, 69467348h; Tag
0x14007b12f  mov     rcx, rax; P
0x14007b132  call    cs:__imp_ExFreePoolWithTag
0x14007b139  nop     dword ptr [rax+rax+00h]
0x14007b13e  mov     eax, ebx
0x14007b140  mov     rcx, [rbp+27h+var_30]
0x14007b144  xor     rcx, rsp; StackCookie
0x14007b147  call    __security_check_cookie
0x14007b14c  mov     rbx, [rsp+0F0h+arg_18]
0x14007b154  add     rsp, 0D0h
0x14007b15b  pop     r13
0x14007b15d  pop     r12
0x14007b15f  pop     rdi
0x14007b160  pop     rsi
0x14007b161  pop     rbp
0x14007b162  retn
0x14007b164  mov     eax, [rsp+0F0h+var_AC]
0x14007b168  mov     ecx, r12d
0x14007b16b  and     ecx, 20h
0x14007b16e  and     eax, 0F0h
0x14007b173  mov     [rbp+27h+var_88], ecx
0x14007b176  cmp     eax, 40h ; '@'
0x14007b179  jb      short loc_14007B1FA
0x14007b17b  test    ecx, ecx
0x14007b17d  jz      short loc_14007B1FA
0x14007b17f  mov     edi, 0C000CF0Bh
0x14007b184  mov     ecx, edi
0x14007b186  mov     ebx, edi
0x14007b188  call    HsmDbgBreakOnStatus
0x14007b18d  mov     r10, cs:WPP_GLOBAL_Control
0x14007b194  lea     rcx, WPP_GLOBAL_Control
0x14007b19b  cmp     r10, rcx
0x14007b19e  jz      loc_14007B0E2
0x14007b1a4  mov     eax, [r10+2Ch]
0x14007b1a8  test    al, 1
0x14007b1aa  jz      loc_14007B0E2
0x14007b1b0  cmp     byte ptr [r10+29h], 2
0x14007b1b5  jb      loc_14007B0E2
0x14007b1bb  mov     rcx, rsi
0x14007b1be  call    HsmpGetStreamSize
0x14007b1c3  mov     edx, 27h ; '''
0x14007b1c8  mov     rcx, [rsp+0F0h+var_A8]
0x14007b1cd  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007b1d4  mov     [rsp+0F0h+var_B8], edi
0x14007b1d8  mov     r9, rsi
0x14007b1db  mov     [rsp+0F0h+var_C0], rcx
0x14007b1e0  mov     rcx, [r10+18h]
0x14007b1e4  mov     [rsp+0F0h+var_C8], rax
0x14007b1e9  mov     eax, [rsi+1Ch]
0x14007b1ec  mov     [rsp+0F0h+FileInformationClass], eax
0x14007b1f0  call    WPP_SF_qLiid
0x14007b1f5  jmp     loc_14007B0E2
0x14007b1fa  mov     eax, r12d
0x14007b1fd  and     eax, 80h
0x14007b202  mov     [rsp+0F0h+var_AC], eax
0x14007b206  jz      short loc_14007B269
0x14007b208  test    ecx, ecx
0x14007b20a  jnz     short loc_14007B21B
0x14007b20c  test    dword ptr [rsi+1Ch], 100h
0x14007b213  jnz     short loc_14007B269
0x14007b215  test    r12b, 40h
0x14007b219  jnz     short loc_14007B269
0x14007b21b  mov     edi, 0C000CF0Bh
0x14007b220  mov     ecx, edi
0x14007b222  mov     ebx, edi
0x14007b224  call    HsmDbgBreakOnStatus
0x14007b229  mov     r10, cs:WPP_GLOBAL_Control
0x14007b230  lea     rcx, WPP_GLOBAL_Control
0x14007b237  cmp     r10, rcx
0x14007b23a  jz      loc_14007B0E2
0x14007b240  mov     eax, [r10+2Ch]
0x14007b244  test    al, 1
0x14007b246  jz      loc_14007B0E2
0x14007b24c  cmp     byte ptr [r10+29h], 2
0x14007b251  jb      loc_14007B0E2
0x14007b257  mov     rcx, rsi
0x14007b25a  call    HsmpGetStreamSize
0x14007b25f  mov     edx, 28h ; '('
0x14007b264  jmp     loc_14007B1C8
0x14007b269  mov     r8d, 8
0x14007b26f  test    r8b, r12b
0x14007b272  jz      short loc_14007B2C1
0x14007b274  test    dword ptr [rsi+1Ch], 2000h
0x14007b27b  jnz     short loc_14007B2C1
0x14007b27d  mov     ebx, 0C000CF08h
0x14007b282  mov     ecx, ebx
0x14007b284  call    HsmDbgBreakOnStatus
0x14007b289  mov     r8, cs:WPP_GLOBAL_Control
0x14007b290  lea     rcx, WPP_GLOBAL_Control
0x14007b297  cmp     r8, rcx
0x14007b29a  jz      loc_14007B0E2
0x14007b2a0  mov     eax, [r8+2Ch]
0x14007b2a4  test    al, 1
0x14007b2a6  jz      loc_14007B0E2
0x14007b2ac  cmp     byte ptr [r8+29h], 2
0x14007b2b1  jb      loc_14007B0E2
0x14007b2b7  mov     edx, 29h ; ')'
0x14007b2bc  jmp     loc_14007B0C1
0x14007b2c1  mov     rax, [rbp+27h+var_80]
0x14007b2c5  xor     dil, dil
0x14007b2c8  test    rax, rax
0x14007b2cb  jz      short loc_14007B2DB
0x14007b2cd  mov     rax, [rax]
0x14007b2d0  mov     dil, 1
0x14007b2d3  mov     qword ptr [rbp+27h+var_48+8], rax
0x14007b2d7  mov     qword ptr [rbp+27h+var_48], rax
0x14007b2db  mov     rax, [rbp+27h+var_78]
0x14007b2df  test    rax, rax
0x14007b2e2  jz      short loc_14007B2EE
0x14007b2e4  mov     rax, [rax]
0x14007b2e7  mov     dil, 1
0x14007b2ea  mov     qword ptr [rbp+27h+FileInformation], rax
0x14007b2ee  mov     rax, [rbp+27h+var_70]
0x14007b2f2  test    rax, rax
0x14007b2f5  jz      short loc_14007B301
0x14007b2f7  mov     rax, [rax]
0x14007b2fa  mov     dil, 1
0x14007b2fd  mov     qword ptr [rbp+27h+FileInformation+8], rax
0x14007b301  mov     rax, [rbp+27h+var_68]
0x14007b305  test    rax, rax
0x14007b308  jz      short loc_14007B312
0x14007b30a  mov     eax, [rax]
0x14007b30c  mov     dil, 1
0x14007b30f  mov     dword ptr [rbp+27h+var_38], eax
0x14007b312  mov     rdx, [rbp+27h+FileObject]
0x14007b316  xor     r9d, r9d
0x14007b319  mov     rcx, r13
0x14007b31c  call    HsmpPrepareForMgmtOperation
0x14007b321  mov     ecx, eax
0x14007b323  mov     ebx, eax
0x14007b325  call    HsmDbgBreakOnStatus
0x14007b32a  test    ebx, ebx
0x14007b32c  jns     short loc_14007B374
0x14007b32e  mov     r8, cs:WPP_GLOBAL_Control
0x14007b335  lea     rcx, WPP_GLOBAL_Control
0x14007b33c  cmp     r8, rcx
0x14007b33f  jz      loc_14007B0E2
0x14007b345  mov     eax, [r8+2Ch]
0x14007b349  test    al, 1
0x14007b34b  jz      loc_14007B0E2
0x14007b351  cmp     byte ptr [r8+29h], 2
0x14007b356  jb      loc_14007B0E2
0x14007b35c  mov     edx, 2Ah ; '*'
0x14007b361  mov     rcx, [rsp+0F0h+var_A8]
0x14007b366  mov     [rsp+0F0h+var_B8], ebx
0x14007b36a  mov     [rsp+0F0h+var_C0], rcx
0x14007b36f  jmp     loc_14007B0CA
0x14007b374  test    dil, dil
0x14007b377  jz      short loc_14007B3E1
0x14007b379  mov     rdx, [rbp+27h+FileObject]; FileObject
0x14007b37d  lea     r8, [rbp+27h+FileInformation]; FileInformation
0x14007b381  mov     rcx, [r13+20h]; Instance
0x14007b385  mov     r9d, 28h ; '('; Length
0x14007b38b  mov     [rsp+0F0h+FileInformationClass], 4; FileInformationClass
0x14007b393  call    cs:__imp_FltSetInformationFile
0x14007b39a  nop     dword ptr [rax+rax+00h]
0x14007b39f  mov     ecx, eax
0x14007b3a1  mov     ebx, eax
0x14007b3a3  call    HsmDbgBreakOnStatus
0x14007b3a8  test    ebx, ebx
0x14007b3aa  jns     short loc_14007B3E1
0x14007b3ac  mov     r8, cs:WPP_GLOBAL_Control
0x14007b3b3  lea     rcx, WPP_GLOBAL_Control
0x14007b3ba  cmp     r8, rcx
0x14007b3bd  jz      loc_14007B0E2
0x14007b3c3  mov     eax, [r8+2Ch]
0x14007b3c7  test    al, 1
0x14007b3c9  jz      loc_14007B0E2
0x14007b3cf  cmp     byte ptr [r8+29h], 2
0x14007b3d4  jb      loc_14007B0E2
0x14007b3da  mov     edx, 2Bh ; '+'
  ... truncated ...
```
