# HsmiOpUpdateInSyncState

- ea: `0x140075998`
- end: `0x140075de7`
- name: `HsmiOpUpdateInSyncState`
- size: `1103`
- prototype: `__int64 __fastcall(__int64, struct _FILE_OBJECT *, __int64, __int64, char, __int64, _QWORD *)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140046bdc`
- `0x1400758b4`

## callees

- `0x140003c50`
- `0x140009300`
- `0x1400152c8`
- `0x14001da28`
- `0x14001e1c0`
- `0x140033e90`
- `0x140058ddc`
- `0x140059738`
- `0x14005ce40`
- `0x140067e24`
- `0x140075998`
- `0x140075df0`
- `0x140075e6c`
- `0x140075fd8`
- `0x140081d30`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x140075ba7`
- `FLTMGR!FltQueryInformationFile` at `0x140075ba7`
- `FLTMGR!FltReleasePushLockEx` at `0x140075ad1`
- `FLTMGR!FltReleasePushLockEx` at `0x140075ad1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140075b18`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140075b56`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140075b18`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140075b56`

## pseudocode

```c
__int64 __fastcall HsmiOpUpdateInSyncState(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        __int64 a3,
        __int64 a4,
        char a5,
        __int64 a6,
        _QWORD *a7)
{
  __int64 v7; // rbp
  __int64 v9; // r13
  NTSTATUS LastEffectiveUsn; // edi
  char StreamSize; // al
  __int64 v14; // r10
  int v15; // edx
  __int64 v16; // rdx
  int v17; // r9d
  __int64 v19; // rcx
  struct _FLT_INSTANCE *v20; // rcx
  __int64 v21; // r8
  char v22; // al
  __int64 v23; // r10
  char v24; // [rsp+40h] [rbp-78h]
  __int128 FileInformation; // [rsp+58h] [rbp-60h] BYREF
  __int64 v27; // [rsp+68h] [rbp-50h]

  v7 = a4;
  v9 = *(_QWORD *)(a4 + 32);
  v24 = 0;
  if ( a5 )
  {
    HsmpWaitForUserRequestRundownRelease(a3);
    v24 = 1;
    LastEffectiveUsn = HsmpPrepareForMgmtOperation(a1, a2, 8);
    HsmDbgBreakOnStatus(LastEffectiveUsn);
    if ( LastEffectiveUsn < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        StreamSize = HsmpGetStreamSize(a3);
        v15 = 30;
LABEL_26:
        WPP_SF_qLiid(
          *(_QWORD *)(v14 + 24),
          v15,
          (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          a3,
          *(_DWORD *)(a3 + 28),
          StreamSize,
          v9,
          LastEffectiveUsn);
        goto LABEL_11;
      }
      goto LABEL_11;
    }
  }
  FltAcquirePushLockExclusiveEx(*(_QWORD *)(a3 + 16) + 24LL, 0);
  if ( !a5 )
  {
LABEL_17:
    v19 = *(_QWORD *)(a3 + 160);
    if ( v19 )
      FltAcquirePushLockExclusiveEx(v19 + 40, 0);
    if ( (*(_DWORD *)(a3 + 28) & 2) == 0 && a5 )
    {
      v20 = *(struct _FLT_INSTANCE **)(a1 + 32);
      FileInformation = 0;
      v27 = 0;
      LastEffectiveUsn = FltQueryInformationFile(v20, a2, &FileInformation, 0x18u, FileStandardInformation, 0);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( LastEffectiveUsn < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqLid(WPP_GLOBAL_Control->AttachedDevice, 33, v21, a1, a3, *(_DWORD *)(a3 + 28), v9, LastEffectiveUsn);
        }
LABEL_10:
        HsmpReleaseBitmapLock(a3);
        goto LABEL_11;
      }
      HsmpUpdateBitmapSizesNoLock(a3, *((_QWORD *)&FileInformation + 1));
      **(_QWORD **)(a3 + 160) = *((_QWORD *)&FileInformation + 1);
    }
    LOBYTE(v16) = a5;
    HsmpSetInSyncNoLock(a3, v16);
    LOBYTE(v17) = a5;
    LastEffectiveUsn = HsmpRpCommitNoLock(a1, a3, (_DWORD)a2, v17, 0);
    HsmDbgBreakOnStatus(LastEffectiveUsn);
    if ( LastEffectiveUsn < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqd(
          WPP_GLOBAL_Control->AttachedDevice,
          34,
          WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          a1,
          *(_QWORD *)(v7 + 32),
          LastEffectiveUsn);
      }
    }
    else if ( a7 )
    {
      LastEffectiveUsn = HsmpQueryLastEffectiveUsn(*(PFLT_INSTANCE *)(a1 + 32), a2);
      HsmDbgBreakOnStatus(LastEffectiveUsn);
      if ( LastEffectiveUsn >= 0 )
      {
        *a7 = 0;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v22 = HsmpGetStreamSize(a3);
        WPP_SF_qLiid(
          *(_QWORD *)(v23 + 24),
          35,
          (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          a3,
          *(_DWORD *)(a3 + 28),
          v22,
          v9,
          LastEffectiveUsn);
      }
    }
    goto LABEL_10;
  }
  if ( !a6 )
  {
    v7 = a4;
    goto LABEL_17;
  }
  LastEffectiveUsn = HsmpQueryLastEffectiveUsn(*(PFLT_INSTANCE *)(a1 + 32), a2);
  HsmDbgBreakOnStatus(LastEffectiveUsn);
  if ( LastEffectiveUsn >= 0 )
  {
    LastEffectiveUsn = -1073688824;
    HsmDbgBreakOnStatus(-1073688824);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(a3);
      v15 = 32;
      goto LABEL_26;
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    StreamSize = HsmpGetStreamSize(a3);
    v15 = 31;
    goto LABEL_26;
  }
LABEL_11:
  FltReleasePushLockEx(*(_QWORD *)(a3 + 16) + 24LL, 0);
  if ( v24 )
    HsmpReInitializeUserRequestRundownProtection(a3);
  return (unsigned int)LastEffectiveUsn;
}

```

## disassembly

```asm
0x140075998  push    rbx
0x14007599a  push    rbp
0x14007599b  push    rsi
0x14007599c  push    rdi
0x14007599d  push    r12
0x14007599f  push    r13
0x1400759a1  push    r15
0x1400759a3  sub     rsp, 80h
0x1400759aa  mov     rax, cs:__security_cookie
0x1400759b1  xor     rax, rsp
0x1400759b4  mov     [rsp+0B8h+var_48], rax
0x1400759b9  cmp     [rsp+0B8h+arg_20], 0
0x1400759c1  mov     rbp, r9
0x1400759c4  mov     r12, [rsp+0B8h+arg_30]
0x1400759cc  mov     rbx, r8
0x1400759cf  mov     r13, [r9+20h]
0x1400759d3  mov     r15, rdx
0x1400759d6  mov     [rsp+0B8h+var_68], r9
0x1400759db  mov     rsi, rcx
0x1400759de  mov     [rsp+0B8h+var_78], 0
0x1400759e3  mov     [rsp+0B8h+var_70], 0
0x1400759ec  jz      loc_140075B0E
0x1400759f2  mov     rcx, rbx
0x1400759f5  call    HsmpWaitForUserRequestRundownRelease
0x1400759fa  xor     r9d, r9d
0x1400759fd  mov     [rsp+0B8h+var_78], 1
0x140075a02  mov     rdx, r15
0x140075a05  mov     rcx, rsi
0x140075a08  lea     r8d, [r9+8]
0x140075a0c  call    HsmpPrepareForMgmtOperation
0x140075a11  mov     ecx, eax
0x140075a13  mov     edi, eax
0x140075a15  call    HsmDbgBreakOnStatus
0x140075a1a  test    edi, edi
0x140075a1c  jns     loc_140075B0E
0x140075a22  mov     r10, cs:WPP_GLOBAL_Control
0x140075a29  lea     rax, WPP_GLOBAL_Control
0x140075a30  cmp     r10, rax
0x140075a33  jz      loc_140075AC7
0x140075a39  mov     ecx, [r10+2Ch]
0x140075a3d  test    cl, 1
0x140075a40  jz      loc_140075AC7
0x140075a46  cmp     byte ptr [r10+29h], 2
0x140075a4b  jb      short loc_140075AC7
0x140075a4d  mov     rcx, rbx
0x140075a50  call    HsmpGetStreamSize
0x140075a55  mov     edx, 1Eh
0x140075a5a  jmp     loc_140075C28
0x140075a5f  mov     rdx, qword ptr [rsp+0B8h+FileInformation+8]
0x140075a64  mov     rcx, rbx
0x140075a67  call    HsmpUpdateBitmapSizesNoLock
0x140075a6c  mov     rcx, [rbx+0A0h]
0x140075a73  mov     rax, qword ptr [rsp+0B8h+FileInformation+8]
0x140075a78  mov     [rcx], rax
0x140075a7b  mov     dl, [rsp+0B8h+arg_20]
0x140075a82  mov     rcx, rbx
0x140075a85  call    HsmpSetInSyncNoLock
0x140075a8a  mov     r9b, [rsp+0B8h+arg_20]
0x140075a92  mov     r8, r15
0x140075a95  mov     rdx, rbx
0x140075a98  mov     byte ptr [rsp+0B8h+FileInformationClass], 0
0x140075a9d  mov     rcx, rsi
0x140075aa0  call    HsmpRpCommitNoLock
0x140075aa5  mov     ecx, eax
0x140075aa7  mov     edi, eax
0x140075aa9  call    HsmDbgBreakOnStatus
0x140075aae  test    edi, edi
0x140075ab0  js      loc_140075CFD
0x140075ab6  test    r12, r12
0x140075ab9  jnz     loc_140075D53
0x140075abf  mov     rcx, rbx
0x140075ac2  call    HsmpReleaseBitmapLock
0x140075ac7  mov     rcx, [rbx+10h]
0x140075acb  xor     edx, edx
0x140075acd  add     rcx, 18h
0x140075ad1  call    cs:__imp_FltReleasePushLockEx
0x140075ad8  nop     dword ptr [rax+rax+00h]
0x140075add  cmp     [rsp+0B8h+var_78], 0
0x140075ae2  jz      short loc_140075AEC
0x140075ae4  mov     rcx, rbx
0x140075ae7  call    HsmpReInitializeUserRequestRundownProtection
0x140075aec  mov     eax, edi
0x140075aee  mov     rcx, [rsp+0B8h+var_48]
0x140075af3  xor     rcx, rsp; StackCookie
0x140075af6  call    __security_check_cookie
0x140075afb  add     rsp, 80h
0x140075b02  pop     r15
0x140075b04  pop     r13
0x140075b06  pop     r12
0x140075b08  pop     rdi
0x140075b09  pop     rsi
0x140075b0a  pop     rbp
0x140075b0b  pop     rbx
0x140075b0c  retn
0x140075b0e  mov     rcx, [rbx+10h]
0x140075b12  xor     edx, edx
0x140075b14  add     rcx, 18h
0x140075b18  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140075b1f  nop     dword ptr [rax+rax+00h]
0x140075b24  cmp     [rsp+0B8h+arg_20], 0
0x140075b2c  jz      short loc_140075B44
0x140075b2e  mov     rbp, [rsp+0B8h+arg_28]
0x140075b36  test    rbp, rbp
0x140075b39  jnz     loc_140075C55
0x140075b3f  mov     rbp, [rsp+0B8h+var_68]
0x140075b44  mov     rcx, [rbx+0A0h]
0x140075b4b  test    rcx, rcx
0x140075b4e  jz      short loc_140075B62
0x140075b50  add     rcx, 28h ; '('
0x140075b54  xor     edx, edx
0x140075b56  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140075b5d  nop     dword ptr [rax+rax+00h]
0x140075b62  mov     eax, [rbx+1Ch]
0x140075b65  test    al, 2
0x140075b67  jnz     loc_140075A7B
0x140075b6d  cmp     [rsp+0B8h+arg_20], 0
0x140075b75  jz      loc_140075A7B
0x140075b7b  mov     rcx, [rsi+20h]; Instance
0x140075b7f  lea     r8, [rsp+0B8h+FileInformation]; FileInformation
0x140075b84  xor     eax, eax
0x140075b86  xorps   xmm0, xmm0
0x140075b89  mov     [rsp+0B8h+LengthReturned], rax; LengthReturned
0x140075b8e  mov     rdx, r15; FileObject
0x140075b91  movups  [rsp+0B8h+FileInformation], xmm0
0x140075b96  mov     [rsp+0B8h+var_50], rax
0x140075b9b  lea     r9d, [rax+18h]; Length
0x140075b9f  mov     [rsp+0B8h+FileInformationClass], 5; FileInformationClass
0x140075ba7  call    cs:__imp_FltQueryInformationFile
0x140075bae  nop     dword ptr [rax+rax+00h]
0x140075bb3  mov     ecx, eax
0x140075bb5  mov     edi, eax
0x140075bb7  call    HsmDbgBreakOnStatus
0x140075bbc  test    edi, edi
0x140075bbe  jns     loc_140075A5F
0x140075bc4  mov     rcx, cs:WPP_GLOBAL_Control
0x140075bcb  lea     rax, WPP_GLOBAL_Control
0x140075bd2  cmp     rcx, rax
0x140075bd5  jz      loc_140075ABF
0x140075bdb  mov     eax, [rcx+2Ch]
0x140075bde  test    al, 1
0x140075be0  jz      loc_140075ABF
0x140075be6  cmp     byte ptr [rcx+29h], 2
0x140075bea  jb      loc_140075ABF
0x140075bf0  mov     eax, [rbx+1Ch]
0x140075bf3  mov     edx, 21h ; '!'
0x140075bf8  mov     rcx, [rcx+18h]
0x140075bfc  mov     r9, rsi
0x140075bff  mov     [rsp+0B8h+var_80], edi
0x140075c03  mov     [rsp+0B8h+var_88], r13
0x140075c08  mov     dword ptr [rsp+0B8h+LengthReturned], eax
0x140075c0c  mov     qword ptr [rsp+0B8h+FileInformationClass], rbx
0x140075c11  call    WPP_SF_qqLid
0x140075c16  jmp     loc_140075ABF
0x140075c1b  mov     rcx, rbx
0x140075c1e  call    HsmpGetStreamSize
0x140075c23  mov     edx, 20h ; ' '
0x140075c28  mov     rcx, [r10+18h]
0x140075c2c  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140075c33  mov     [rsp+0B8h+var_80], edi
0x140075c37  mov     r9, rbx
0x140075c3a  mov     [rsp+0B8h+var_88], r13
0x140075c3f  mov     [rsp+0B8h+LengthReturned], rax
0x140075c44  mov     eax, [rbx+1Ch]
0x140075c47  mov     [rsp+0B8h+FileInformationClass], eax
0x140075c4b  call    WPP_SF_qLiid
0x140075c50  jmp     loc_140075AC7
0x140075c55  mov     rcx, [rsi+20h]; Instance
0x140075c59  lea     r8, [rsp+0B8h+var_70]
0x140075c5e  mov     rdx, r15; FileObject
0x140075c61  call    HsmpQueryLastEffectiveUsn
0x140075c66  mov     ecx, eax
0x140075c68  mov     edi, eax
0x140075c6a  call    HsmDbgBreakOnStatus
0x140075c6f  test    edi, edi
0x140075c71  jns     short loc_140075CB3
0x140075c73  mov     r10, cs:WPP_GLOBAL_Control
0x140075c7a  lea     rax, WPP_GLOBAL_Control
0x140075c81  cmp     r10, rax
0x140075c84  jz      loc_140075AC7
0x140075c8a  mov     eax, [r10+2Ch]
0x140075c8e  test    al, 1
0x140075c90  jz      loc_140075AC7
0x140075c96  cmp     byte ptr [r10+29h], 2
0x140075c9b  jb      loc_140075AC7
0x140075ca1  mov     rcx, rbx
0x140075ca4  call    HsmpGetStreamSize
0x140075ca9  mov     edx, 1Fh
0x140075cae  jmp     loc_140075C28
0x140075cb3  cmp     rbp, [rsp+0B8h+var_70]
0x140075cb8  jz      loc_140075B3F
0x140075cbe  mov     edi, 0C000CF08h
0x140075cc3  mov     ecx, edi
0x140075cc5  call    HsmDbgBreakOnStatus
0x140075cca  mov     r10, cs:WPP_GLOBAL_Control
0x140075cd1  lea     rax, WPP_GLOBAL_Control
0x140075cd8  cmp     r10, rax
0x140075cdb  jz      loc_140075AC7
0x140075ce1  mov     eax, [r10+2Ch]
0x140075ce5  test    al, 1
0x140075ce7  jz      loc_140075AC7
0x140075ced  cmp     byte ptr [r10+29h], 2
0x140075cf2  jb      loc_140075AC7
0x140075cf8  jmp     loc_140075C1B
0x140075cfd  mov     rcx, cs:WPP_GLOBAL_Control
0x140075d04  lea     rax, WPP_GLOBAL_Control
0x140075d0b  cmp     rcx, rax
0x140075d0e  jz      loc_140075ABF
0x140075d14  mov     eax, [rcx+2Ch]
0x140075d17  test    al, 1
0x140075d19  jz      loc_140075ABF
0x140075d1f  cmp     byte ptr [rcx+29h], 2
0x140075d23  jb      loc_140075ABF
0x140075d29  mov     rax, [rbp+20h]
0x140075d2d  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140075d34  mov     rcx, [rcx+18h]
0x140075d38  mov     edx, 22h ; '"'
0x140075d3d  mov     dword ptr [rsp+0B8h+LengthReturned], edi
0x140075d41  mov     r9, rsi
0x140075d44  mov     qword ptr [rsp+0B8h+FileInformationClass], rax
0x140075d49  call    WPP_SF_qqd
0x140075d4e  jmp     loc_140075ABF
0x140075d53  mov     rcx, [rsi+20h]; Instance
0x140075d57  lea     r8, [rsp+0B8h+var_70]
0x140075d5c  mov     rdx, r15; FileObject
0x140075d5f  call    HsmpQueryLastEffectiveUsn
0x140075d64  mov     ecx, eax
0x140075d66  mov     edi, eax
0x140075d68  call    HsmDbgBreakOnStatus
0x140075d6d  test    edi, edi
0x140075d6f  jns     short loc_140075DD9
0x140075d71  mov     r10, cs:WPP_GLOBAL_Control
0x140075d78  lea     rax, WPP_GLOBAL_Control
0x140075d7f  cmp     r10, rax
0x140075d82  jz      loc_140075ABF
0x140075d88  mov     eax, [r10+2Ch]
0x140075d8c  test    al, 1
0x140075d8e  jz      loc_140075ABF
0x140075d94  cmp     byte ptr [r10+29h], 2
0x140075d99  jb      loc_140075ABF
0x140075d9f  mov     rcx, rbx
0x140075da2  call    HsmpGetStreamSize
0x140075da7  mov     rcx, [r10+18h]
0x140075dab  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140075db2  mov     [rsp+0B8h+var_80], edi
0x140075db6  mov     edx, 23h ; '#'
0x140075dbb  mov     [rsp+0B8h+var_88], r13
0x140075dc0  mov     r9, rbx
0x140075dc3  mov     [rsp+0B8h+LengthReturned], rax
0x140075dc8  mov     eax, [rbx+1Ch]
0x140075dcb  mov     [rsp+0B8h+FileInformationClass], eax
0x140075dcf  call    WPP_SF_qLiid
0x140075dd4  jmp     loc_140075ABF
0x140075dd9  mov     rax, [rsp+0B8h+var_70]
0x140075dde  mov     [r12], rax
0x140075de2  jmp     loc_140075ABF
```
