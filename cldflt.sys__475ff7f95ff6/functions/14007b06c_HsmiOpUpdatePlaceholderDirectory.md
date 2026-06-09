# HsmiOpUpdatePlaceholderDirectory

- ea: `0x14007b06c`
- end: `0x14007b725`
- name: `HsmiOpUpdatePlaceholderDirectory`
- size: `1721`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FILE_OBJECT *, int, void *, int, _DWORD *, _QWORD *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14007ab00`

## callees

- `0x140003c50`
- `0x140009ed4`
- `0x14000a048`
- `0x1400152c8`
- `0x14001da28`
- `0x14001e1c0`
- `0x14001e300`
- `0x140052574`
- `0x140058ddc`
- `0x140059738`
- `0x14005ce40`
- `0x140067e24`
- `0x140075df0`
- `0x140075e6c`
- `0x140075fd8`
- `0x14007b06c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14007b272`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007b272`
- `ntoskrnl!ExAllocatePool2` at `0x14007b548`
- `ntoskrnl!ExAllocatePool2` at `0x14007b548`
- `FLTMGR!FltSetInformationFile` at `0x14007b4d3`
- `FLTMGR!FltSetInformationFile` at `0x14007b4d3`
- `FLTMGR!FltReleasePushLockEx` at `0x14007b24d`
- `FLTMGR!FltReleasePushLockEx` at `0x14007b60f`
- `FLTMGR!FltReleasePushLockEx` at `0x14007b24d`
- `FLTMGR!FltReleasePushLockEx` at `0x14007b60f`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b19e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b5b9`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b5e6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b631`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b19e`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b5b9`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b5e6`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14007b631`

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
  NTSTATUS SyncPolicy; // ebx
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
  int v27; // r9d
  PDEVICE_OBJECT v28; // r8
  __int64 v29; // rdx
  void *v30; // rdi
  size_t v31; // rbx
  void *Pool2; // rax
  PVOID v33; // rbx
  __int64 v34; // rcx
  int v35; // eax
  unsigned int v36; // eax
  char v37; // [rsp+41h] [rbp-88h]
  int v38; // [rsp+44h] [rbp-85h] BYREF
  __int64 v39; // [rsp+48h] [rbp-81h]
  size_t Size; // [rsp+50h] [rbp-79h]
  PVOID P; // [rsp+58h] [rbp-71h]
  PFILE_OBJECT FileObject; // [rsp+60h] [rbp-69h]
  int v43; // [rsp+68h] [rbp-61h]
  _QWORD *v44; // [rsp+70h] [rbp-59h]
  _QWORD *v45; // [rsp+78h] [rbp-51h]
  _QWORD *v46; // [rsp+80h] [rbp-49h]
  _DWORD *v47; // [rsp+88h] [rbp-41h]
  void *Src; // [rsp+90h] [rbp-39h]
  __int128 FileInformation; // [rsp+98h] [rbp-31h] BYREF
  __int128 v50; // [rsp+A8h] [rbp-21h]
  __int64 v51; // [rsp+B8h] [rbp-11h]

  Src = a5;
  LODWORD(Size) = a6;
  v47 = a7;
  v45 = a8;
  v44 = a9;
  v13 = *(_QWORD *)(a2 + 16);
  v46 = a10;
  FileObject = a3;
  v38 = 0;
  v14 = *(_QWORD *)(v13 + 32);
  v51 = 0;
  v39 = v14;
  FileInformation = 0;
  v50 = 0;
  SyncPolicy = HsmpAcquireSyncOpRundownProtection((PFLT_CONTEXT)a2, 0);
  HsmDbgBreakOnStatus(SyncPolicy);
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
  v37 = 0;
  if ( (a4 & 2) != 0 )
  {
    HsmpWaitForUserRequestRundownRelease(a2);
    v37 = 1;
  }
  FltAcquirePushLockExclusiveEx(*(_QWORD *)(a2 + 16) + 24LL, 0);
  SyncPolicy = HsmpCldGetSyncPolicy(a1, a2, (_DWORD)FileObject, 5, (__int64)&v38);
  HsmDbgBreakOnStatus(SyncPolicy);
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
  v43 = a4 & 0x20;
  if ( (v38 & 0xF0u) >= 0x40 && (a4 & 0x20) != 0 )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
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
  v38 = a4 & 0x80;
  if ( (a4 & 0x80) != 0 && ((a4 & 0x20) != 0 || (*(_DWORD *)(a2 + 28) & 0x100) == 0 && (a4 & 0x40) == 0) )
  {
    SyncPolicy = -1073688821;
    HsmDbgBreakOnStatus(-1073688821);
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
      v39,
      11);
    goto LABEL_14;
  }
  if ( (a4 & 8) == 0 || (*(_DWORD *)(a2 + 28) & 0x2000) != 0 )
  {
    v25 = 0;
    if ( v44 )
    {
      v25 = 1;
      *((_QWORD *)&v50 + 1) = *v44;
      *(_QWORD *)&v50 = *((_QWORD *)&v50 + 1);
    }
    if ( v45 )
    {
      v25 = 1;
      *(_QWORD *)&FileInformation = *v45;
    }
    if ( v46 )
    {
      v25 = 1;
      *((_QWORD *)&FileInformation + 1) = *v46;
    }
    if ( v47 )
    {
      v25 = 1;
      LODWORD(v51) = *v47;
    }
    SyncPolicy = HsmpPrepareForMgmtOperation(a1, FileObject, 8);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_14;
      }
      v29 = 42;
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
      HsmDbgBreakOnStatus(SyncPolicy);
      if ( SyncPolicy < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_14;
        }
        v29 = 43;
        goto LABEL_56;
      }
    }
    v30 = Src;
    if ( Src && (_DWORD)Size )
    {
      v31 = (unsigned int)Size;
      Pool2 = (void *)ExAllocatePool2(258, (unsigned int)Size, 1766224712);
      P = Pool2;
      if ( !Pool2 )
      {
        SyncPolicy = -1073741670;
        HsmDbgBreakOnStatus(-1073741670);
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_14;
        }
        v29 = 44;
LABEL_56:
        WPP_SF_qqLid(v28->AttachedDevice, v29, v28, a1, a2, *(_DWORD *)(a2 + 28), v39, SyncPolicy);
        goto LABEL_14;
      }
      memmove(Pool2, v30, v31);
      v33 = P;
      FltAcquirePushLockExclusiveEx(a2 + 64, 0);
      P = *(PVOID *)(a2 + 48);
      *(_DWORD *)(a2 + 56) = Size;
      *(_QWORD *)(a2 + 48) = v33;
    }
    else
    {
      if ( !v38 )
        goto LABEL_74;
      FltAcquirePushLockExclusiveEx(a2 + 64, 0);
      P = *(PVOID *)(a2 + 48);
      *(_QWORD *)(a2 + 48) = 0;
      *(_DWORD *)(a2 + 56) = 0;
    }
    FltReleasePushLockEx(a2 + 64, 0);
LABEL_74:
    *(_DWORD *)(a2 + 28) |= 1u;
    v34 = *(_QWORD *)(a2 + 160);
    if ( v34 )
      FltAcquirePushLockExclusiveEx(v34 + 40, 0);
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
    v35 = *(_DWORD *)(a2 + 28);
    if ( v43 )
    {
      v36 = v35 & 0xFFFFFEBF;
    }
    else
    {
      if ( (a4 & 0x40) == 0 )
      {
LABEL_89:
        LOBYTE(v27) = 1;
        SyncPolicy = HsmpRpCommitNoLock(a1, a2, (_DWORD)FileObject, v27, 0);
        HsmDbgBreakOnStatus(SyncPolicy);
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
            v39,
            SyncPolicy);
        }
        goto LABEL_15;
      }
      v36 = v35 | 0x140;
    }
    *(_DWORD *)(a2 + 28) = v36;
    goto LABEL_89;
  }
  SyncPolicy = -1073688824;
  HsmDbgBreakOnStatus(-1073688824);
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
  if ( v37 )
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
0x14007b06c  mov     [rsp-8+arg_18], rbx
0x14007b071  push    rbp
0x14007b072  push    rsi
0x14007b073  push    rdi
0x14007b074  push    r12
0x14007b076  push    r13
0x14007b078  lea     rbp, [rsp-7]
0x14007b07d  sub     rsp, 0D0h
0x14007b084  mov     rax, cs:__security_cookie
0x14007b08b  xor     rax, rsp
0x14007b08e  mov     [rbp+27h+var_30], rax
0x14007b092  mov     rax, [rbp+27h+arg_20]
0x14007b096  mov     r13, rcx
0x14007b099  mov     rcx, [rbp+27h+arg_48]
0x14007b09d  mov     rsi, rdx
0x14007b0a0  mov     [rbp+27h+Src], rax
0x14007b0a4  xorps   xmm0, xmm0
0x14007b0a7  mov     eax, [rbp+27h+arg_28]
0x14007b0aa  mov     r12d, r9d
0x14007b0ad  mov     dword ptr [rbp+27h+Size], eax
0x14007b0b0  mov     rax, [rbp+27h+arg_30]
0x14007b0b4  mov     [rbp+27h+var_68], rax
0x14007b0b8  mov     rax, [rbp+27h+arg_38]
0x14007b0bc  mov     [rbp+27h+var_78], rax
0x14007b0c0  mov     rax, [rbp+27h+arg_40]
0x14007b0c4  mov     [rbp+27h+var_80], rax
0x14007b0c8  mov     rax, [rdx+10h]
0x14007b0cc  xor     edx, edx; CallbackData
0x14007b0ce  mov     [rbp+27h+var_70], rcx
0x14007b0d2  mov     rcx, rsi; Context
0x14007b0d5  mov     [rbp+27h+FileObject], r8
0x14007b0d9  mov     [rsp+0F0h+var_AC], 0
0x14007b0e1  mov     rdi, [rax+20h]
0x14007b0e5  xor     eax, eax
0x14007b0e7  mov     [rbp+27h+var_38], rax
0x14007b0eb  mov     [rsp+0F0h+var_A8], rdi
0x14007b0f0  movups  [rbp+27h+FileInformation], xmm0
0x14007b0f4  movups  [rbp+27h+var_48], xmm0
0x14007b0f8  call    HsmpAcquireSyncOpRundownProtection
0x14007b0fd  mov     ecx, eax
0x14007b0ff  mov     ebx, eax
0x14007b101  call    HsmDbgBreakOnStatus
0x14007b106  test    ebx, ebx
0x14007b108  jns     short loc_14007B173
0x14007b10a  mov     r10, cs:WPP_GLOBAL_Control
0x14007b111  lea     rcx, WPP_GLOBAL_Control
0x14007b118  cmp     r10, rcx
0x14007b11b  jz      loc_14007B27E
0x14007b121  mov     ecx, [r10+2Ch]
0x14007b125  test    cl, 1
0x14007b128  jz      loc_14007B27E
0x14007b12e  cmp     byte ptr [r10+29h], 2
0x14007b133  jb      loc_14007B27E
0x14007b139  mov     rcx, rsi
0x14007b13c  call    HsmpGetStreamSize
0x14007b141  mov     rcx, [r10+18h]
0x14007b145  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007b14c  mov     [rsp+0F0h+var_B8], ebx
0x14007b150  mov     edx, 25h ; '%'
0x14007b155  mov     [rsp+0F0h+var_C0], rdi
0x14007b15a  mov     r9, rsi
0x14007b15d  mov     [rsp+0F0h+var_C8], rax
0x14007b162  mov     eax, [rsi+1Ch]
0x14007b165  mov     [rsp+0F0h+FileInformationClass], eax
0x14007b169  call    WPP_SF_qLiid
0x14007b16e  jmp     loc_14007B27E
0x14007b173  xor     eax, eax
0x14007b175  mov     [rbp+27h+P], rax
0x14007b179  mov     [rsp+0F0h+var_B0], al
0x14007b17d  mov     [rsp+0F0h+var_AF], al
0x14007b181  test    r12b, 2
0x14007b185  jz      short loc_14007B194
0x14007b187  mov     rcx, rsi
0x14007b18a  call    HsmpWaitForUserRequestRundownRelease
0x14007b18f  mov     [rsp+0F0h+var_AF], 1
0x14007b194  mov     rcx, [rsi+10h]
0x14007b198  xor     edx, edx
0x14007b19a  add     rcx, 18h
0x14007b19e  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x14007b1a5  nop     dword ptr [rax+rax+00h]
0x14007b1aa  mov     r8, [rbp+27h+FileObject]
0x14007b1ae  lea     rax, [rsp+0F0h+var_AC]
0x14007b1b3  mov     r9d, 5
0x14007b1b9  mov     qword ptr [rsp+0F0h+FileInformationClass], rax
0x14007b1be  mov     rdx, rsi
0x14007b1c1  mov     rcx, r13
0x14007b1c4  call    HsmpCldGetSyncPolicy
0x14007b1c9  mov     ecx, eax
0x14007b1cb  mov     ebx, eax
0x14007b1cd  call    HsmDbgBreakOnStatus
0x14007b1d2  test    ebx, ebx
0x14007b1d4  jns     loc_14007B2A4
0x14007b1da  mov     r8, cs:WPP_GLOBAL_Control
0x14007b1e1  lea     rcx, WPP_GLOBAL_Control
0x14007b1e8  cmp     r8, rcx
0x14007b1eb  jz      short loc_14007B222
0x14007b1ed  mov     eax, [r8+2Ch]
0x14007b1f1  test    al, 1
0x14007b1f3  jz      short loc_14007B222
0x14007b1f5  cmp     byte ptr [r8+29h], 2
0x14007b1fa  jb      short loc_14007B222
0x14007b1fc  mov     edx, 26h ; '&'
0x14007b201  mov     [rsp+0F0h+var_B8], ebx
0x14007b205  mov     [rsp+0F0h+var_C0], rdi
0x14007b20a  mov     eax, [rsi+1Ch]
0x14007b20d  mov     r9, r13
0x14007b210  mov     rcx, [r8+18h]
0x14007b214  mov     dword ptr [rsp+0F0h+var_C8], eax
0x14007b218  mov     qword ptr [rsp+0F0h+FileInformationClass], rsi
0x14007b21d  call    WPP_SF_qqLid
0x14007b222  mov     dil, [rsp+0F0h+var_B0]
0x14007b227  cmp     [rsp+0F0h+var_AF], 0
0x14007b22c  jz      short loc_14007B236
0x14007b22e  mov     rcx, rsi
0x14007b231  call    HsmpReInitializeUserRequestRundownProtection
0x14007b236  test    dil, dil
0x14007b239  jz      short loc_14007B243
0x14007b23b  mov     rcx, rsi
0x14007b23e  call    HsmpReleaseBitmapLock
0x14007b243  mov     rcx, [rsi+10h]
0x14007b247  xor     edx, edx
0x14007b249  add     rcx, 18h
0x14007b24d  call    cs:__imp_FltReleasePushLockEx
0x14007b254  nop     dword ptr [rax+rax+00h]
0x14007b259  mov     rcx, rsi; Context
0x14007b25c  call    HsmpReleaseSyncOpRundownProtection
0x14007b261  mov     rax, [rbp+27h+P]
0x14007b265  test    rax, rax
0x14007b268  jz      short loc_14007B27E
0x14007b26a  mov     edx, 69467348h; Tag
0x14007b26f  mov     rcx, rax; P
0x14007b272  call    cs:__imp_ExFreePoolWithTag
0x14007b279  nop     dword ptr [rax+rax+00h]
0x14007b27e  mov     eax, ebx
0x14007b280  mov     rcx, [rbp+27h+var_30]
0x14007b284  xor     rcx, rsp; StackCookie
0x14007b287  call    __security_check_cookie
0x14007b28c  mov     rbx, [rsp+0F0h+arg_18]
0x14007b294  add     rsp, 0D0h
0x14007b29b  pop     r13
0x14007b29d  pop     r12
0x14007b29f  pop     rdi
0x14007b2a0  pop     rsi
0x14007b2a1  pop     rbp
0x14007b2a2  retn
0x14007b2a4  mov     eax, [rsp+0F0h+var_AC]
0x14007b2a8  mov     ecx, r12d
0x14007b2ab  and     ecx, 20h
0x14007b2ae  and     eax, 0F0h
0x14007b2b3  mov     [rbp+27h+var_88], ecx
0x14007b2b6  cmp     eax, 40h ; '@'
0x14007b2b9  jb      short loc_14007B33A
0x14007b2bb  test    ecx, ecx
0x14007b2bd  jz      short loc_14007B33A
0x14007b2bf  mov     edi, 0C000CF0Bh
0x14007b2c4  mov     ecx, edi
0x14007b2c6  mov     ebx, edi
0x14007b2c8  call    HsmDbgBreakOnStatus
0x14007b2cd  mov     r10, cs:WPP_GLOBAL_Control
0x14007b2d4  lea     rcx, WPP_GLOBAL_Control
0x14007b2db  cmp     r10, rcx
0x14007b2de  jz      loc_14007B222
0x14007b2e4  mov     eax, [r10+2Ch]
0x14007b2e8  test    al, 1
0x14007b2ea  jz      loc_14007B222
0x14007b2f0  cmp     byte ptr [r10+29h], 2
0x14007b2f5  jb      loc_14007B222
0x14007b2fb  mov     rcx, rsi
0x14007b2fe  call    HsmpGetStreamSize
0x14007b303  mov     edx, 27h ; '''
0x14007b308  mov     rcx, [rsp+0F0h+var_A8]
0x14007b30d  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14007b314  mov     [rsp+0F0h+var_B8], edi
0x14007b318  mov     r9, rsi
0x14007b31b  mov     [rsp+0F0h+var_C0], rcx
0x14007b320  mov     rcx, [r10+18h]
0x14007b324  mov     [rsp+0F0h+var_C8], rax
0x14007b329  mov     eax, [rsi+1Ch]
0x14007b32c  mov     [rsp+0F0h+FileInformationClass], eax
0x14007b330  call    WPP_SF_qLiid
0x14007b335  jmp     loc_14007B222
0x14007b33a  mov     eax, r12d
0x14007b33d  and     eax, 80h
0x14007b342  mov     [rsp+0F0h+var_AC], eax
0x14007b346  jz      short loc_14007B3A9
0x14007b348  test    ecx, ecx
0x14007b34a  jnz     short loc_14007B35B
0x14007b34c  test    dword ptr [rsi+1Ch], 100h
0x14007b353  jnz     short loc_14007B3A9
0x14007b355  test    r12b, 40h
0x14007b359  jnz     short loc_14007B3A9
0x14007b35b  mov     edi, 0C000CF0Bh
0x14007b360  mov     ecx, edi
0x14007b362  mov     ebx, edi
0x14007b364  call    HsmDbgBreakOnStatus
0x14007b369  mov     r10, cs:WPP_GLOBAL_Control
0x14007b370  lea     rcx, WPP_GLOBAL_Control
0x14007b377  cmp     r10, rcx
0x14007b37a  jz      loc_14007B222
0x14007b380  mov     eax, [r10+2Ch]
0x14007b384  test    al, 1
0x14007b386  jz      loc_14007B222
0x14007b38c  cmp     byte ptr [r10+29h], 2
0x14007b391  jb      loc_14007B222
0x14007b397  mov     rcx, rsi
0x14007b39a  call    HsmpGetStreamSize
0x14007b39f  mov     edx, 28h ; '('
0x14007b3a4  jmp     loc_14007B308
0x14007b3a9  mov     r8d, 8
0x14007b3af  test    r8b, r12b
0x14007b3b2  jz      short loc_14007B401
0x14007b3b4  test    dword ptr [rsi+1Ch], 2000h
0x14007b3bb  jnz     short loc_14007B401
0x14007b3bd  mov     ebx, 0C000CF08h
0x14007b3c2  mov     ecx, ebx
0x14007b3c4  call    HsmDbgBreakOnStatus
0x14007b3c9  mov     r8, cs:WPP_GLOBAL_Control
0x14007b3d0  lea     rcx, WPP_GLOBAL_Control
0x14007b3d7  cmp     r8, rcx
0x14007b3da  jz      loc_14007B222
0x14007b3e0  mov     eax, [r8+2Ch]
0x14007b3e4  test    al, 1
0x14007b3e6  jz      loc_14007B222
0x14007b3ec  cmp     byte ptr [r8+29h], 2
0x14007b3f1  jb      loc_14007B222
0x14007b3f7  mov     edx, 29h ; ')'
0x14007b3fc  jmp     loc_14007B201
0x14007b401  mov     rax, [rbp+27h+var_80]
0x14007b405  xor     dil, dil
0x14007b408  test    rax, rax
0x14007b40b  jz      short loc_14007B41B
0x14007b40d  mov     rax, [rax]
0x14007b410  mov     dil, 1
0x14007b413  mov     qword ptr [rbp+27h+var_48+8], rax
0x14007b417  mov     qword ptr [rbp+27h+var_48], rax
0x14007b41b  mov     rax, [rbp+27h+var_78]
0x14007b41f  test    rax, rax
0x14007b422  jz      short loc_14007B42E
0x14007b424  mov     rax, [rax]
0x14007b427  mov     dil, 1
0x14007b42a  mov     qword ptr [rbp+27h+FileInformation], rax
0x14007b42e  mov     rax, [rbp+27h+var_70]
0x14007b432  test    rax, rax
0x14007b435  jz      short loc_14007B441
0x14007b437  mov     rax, [rax]
0x14007b43a  mov     dil, 1
0x14007b43d  mov     qword ptr [rbp+27h+FileInformation+8], rax
0x14007b441  mov     rax, [rbp+27h+var_68]
0x14007b445  test    rax, rax
0x14007b448  jz      short loc_14007B452
0x14007b44a  mov     eax, [rax]
0x14007b44c  mov     dil, 1
0x14007b44f  mov     dword ptr [rbp+27h+var_38], eax
0x14007b452  mov     rdx, [rbp+27h+FileObject]
0x14007b456  xor     r9d, r9d
0x14007b459  mov     rcx, r13
0x14007b45c  call    HsmpPrepareForMgmtOperation
0x14007b461  mov     ecx, eax
0x14007b463  mov     ebx, eax
0x14007b465  call    HsmDbgBreakOnStatus
0x14007b46a  test    ebx, ebx
0x14007b46c  jns     short loc_14007B4B4
0x14007b46e  mov     r8, cs:WPP_GLOBAL_Control
0x14007b475  lea     rcx, WPP_GLOBAL_Control
0x14007b47c  cmp     r8, rcx
0x14007b47f  jz      loc_14007B222
0x14007b485  mov     eax, [r8+2Ch]
0x14007b489  test    al, 1
0x14007b48b  jz      loc_14007B222
0x14007b491  cmp     byte ptr [r8+29h], 2
0x14007b496  jb      loc_14007B222
0x14007b49c  mov     edx, 2Ah ; '*'
0x14007b4a1  mov     rcx, [rsp+0F0h+var_A8]
0x14007b4a6  mov     [rsp+0F0h+var_B8], ebx
0x14007b4aa  mov     [rsp+0F0h+var_C0], rcx
0x14007b4af  jmp     loc_14007B20A
0x14007b4b4  test    dil, dil
0x14007b4b7  jz      short loc_14007B521
0x14007b4b9  mov     rdx, [rbp+27h+FileObject]; FileObject
0x14007b4bd  lea     r8, [rbp+27h+FileInformation]; FileInformation
0x14007b4c1  mov     rcx, [r13+20h]; Instance
0x14007b4c5  mov     r9d, 28h ; '('; Length
0x14007b4cb  mov     [rsp+0F0h+FileInformationClass], 4; FileInformationClass
0x14007b4d3  call    cs:__imp_FltSetInformationFile
0x14007b4da  nop     dword ptr [rax+rax+00h]
0x14007b4df  mov     ecx, eax
0x14007b4e1  mov     ebx, eax
0x14007b4e3  call    HsmDbgBreakOnStatus
0x14007b4e8  test    ebx, ebx
0x14007b4ea  jns     short loc_14007B521
0x14007b4ec  mov     r8, cs:WPP_GLOBAL_Control
0x14007b4f3  lea     rcx, WPP_GLOBAL_Control
0x14007b4fa  cmp     r8, rcx
0x14007b4fd  jz      loc_14007B222
0x14007b503  mov     eax, [r8+2Ch]
0x14007b507  test    al, 1
0x14007b509  jz      loc_14007B222
0x14007b50f  cmp     byte ptr [r8+29h], 2
0x14007b514  jb      loc_14007B222
0x14007b51a  mov     edx, 2Bh ; '+'
  ... truncated ...
```
