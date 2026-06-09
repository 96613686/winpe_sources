# HsmiOpUpdateInSyncState

- ea: `0x140075878`
- end: `0x140075cc7`
- name: `HsmiOpUpdateInSyncState`
- size: `1103`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140046aec`
- `0x140075794`

## callees

- `0x140003c50`
- `0x140009300`
- `0x140015248`
- `0x14001d9a8`
- `0x14001e140`
- `0x140033e90`
- `0x140058cbc`
- `0x140059618`
- `0x14005cd20`
- `0x140067d04`
- `0x140075878`
- `0x140075cd0`
- `0x140075d4c`
- `0x140075eb8`
- `0x140081b90`

## import_xrefs

- `FLTMGR!FltQueryInformationFile` at `0x140075a87`
- `FLTMGR!FltQueryInformationFile` at `0x140075a87`
- `FLTMGR!FltReleasePushLockEx` at `0x1400759b1`
- `FLTMGR!FltReleasePushLockEx` at `0x1400759b1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400759f8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140075a36`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x1400759f8`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x140075a36`

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
  __int64 v12; // rdi
  char StreamSize; // al
  __int64 v14; // r10
  int v15; // edx
  __int64 v16; // rdx
  __int64 v18; // rcx
  struct _FLT_INSTANCE *v19; // rcx
  __int64 v20; // r8
  char v21; // al
  __int64 v22; // r10
  char v23; // [rsp+40h] [rbp-78h]
  __int64 v24; // [rsp+48h] [rbp-70h] BYREF
  __int64 v25; // [rsp+50h] [rbp-68h]
  __int128 FileInformation; // [rsp+58h] [rbp-60h] BYREF
  __int64 v27; // [rsp+68h] [rbp-50h]

  v7 = a4;
  v9 = *(_QWORD *)(a4 + 32);
  v25 = a4;
  v23 = 0;
  v24 = 0;
  if ( a5 )
  {
    HsmpWaitForUserRequestRundownRelease(a3);
    v23 = 1;
    LODWORD(v12) = HsmpPrepareForMgmtOperation(a1, a2, 8, 0);
    HsmDbgBreakOnStatus((unsigned int)v12);
    if ( (int)v12 < 0 )
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
          v12);
        goto LABEL_11;
      }
      goto LABEL_11;
    }
  }
  FltAcquirePushLockExclusiveEx(*(_QWORD *)(a3 + 16) + 24LL, 0);
  if ( !a5 )
  {
LABEL_17:
    v18 = *(_QWORD *)(a3 + 160);
    if ( v18 )
      FltAcquirePushLockExclusiveEx(v18 + 40, 0);
    if ( (*(_DWORD *)(a3 + 28) & 2) == 0 && a5 )
    {
      v19 = *(struct _FLT_INSTANCE **)(a1 + 32);
      FileInformation = 0;
      v27 = 0;
      v12 = (unsigned int)FltQueryInformationFile(v19, a2, &FileInformation, 0x18u, FileStandardInformation, 0);
      HsmDbgBreakOnStatus(v12);
      if ( (int)v12 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_qqLid(WPP_GLOBAL_Control->AttachedDevice, 33, v20, a1, a3, *(_DWORD *)(a3 + 28), v9, v12);
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
    LODWORD(v12) = HsmpRpCommitNoLock(a1, a3, a2, a5, 0);
    HsmDbgBreakOnStatus((unsigned int)v12);
    if ( (int)v12 < 0 )
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
          v12);
      }
    }
    else if ( a7 )
    {
      LODWORD(v12) = HsmpQueryLastEffectiveUsn(*(PFLT_INSTANCE *)(a1 + 32), a2, &v24);
      HsmDbgBreakOnStatus((unsigned int)v12);
      if ( (int)v12 >= 0 )
      {
        *a7 = v24;
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
             && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v21 = HsmpGetStreamSize(a3);
        WPP_SF_qLiid(
          *(_QWORD *)(v22 + 24),
          35,
          (unsigned int)WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
          a3,
          *(_DWORD *)(a3 + 28),
          v21,
          v9,
          v12);
      }
    }
    goto LABEL_10;
  }
  if ( !a6 )
  {
LABEL_16:
    v7 = v25;
    goto LABEL_17;
  }
  LODWORD(v12) = HsmpQueryLastEffectiveUsn(*(PFLT_INSTANCE *)(a1 + 32), a2, &v24);
  HsmDbgBreakOnStatus((unsigned int)v12);
  if ( (int)v12 >= 0 )
  {
    if ( a6 != v24 )
    {
      LODWORD(v12) = -1073688824;
      HsmDbgBreakOnStatus(3221278472LL);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        StreamSize = HsmpGetStreamSize(a3);
        v15 = 32;
        goto LABEL_26;
      }
      goto LABEL_11;
    }
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    StreamSize = HsmpGetStreamSize(a3);
    v15 = 31;
    goto LABEL_26;
  }
LABEL_11:
  FltReleasePushLockEx(*(_QWORD *)(a3 + 16) + 24LL, 0);
  if ( v23 )
    HsmpReInitializeUserRequestRundownProtection(a3);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140075878  push    rbx
0x14007587a  push    rbp
0x14007587b  push    rsi
0x14007587c  push    rdi
0x14007587d  push    r12
0x14007587f  push    r13
0x140075881  push    r15
0x140075883  sub     rsp, 80h
0x14007588a  mov     rax, cs:__security_cookie
0x140075891  xor     rax, rsp
0x140075894  mov     [rsp+0B8h+var_48], rax
0x140075899  cmp     [rsp+0B8h+arg_20], 0
0x1400758a1  mov     rbp, r9
0x1400758a4  mov     r12, [rsp+0B8h+arg_30]
0x1400758ac  mov     rbx, r8
0x1400758af  mov     r13, [r9+20h]
0x1400758b3  mov     r15, rdx
0x1400758b6  mov     [rsp+0B8h+var_68], r9
0x1400758bb  mov     rsi, rcx
0x1400758be  mov     [rsp+0B8h+var_78], 0
0x1400758c3  mov     [rsp+0B8h+var_70], 0
0x1400758cc  jz      loc_1400759EE
0x1400758d2  mov     rcx, rbx
0x1400758d5  call    HsmpWaitForUserRequestRundownRelease
0x1400758da  xor     r9d, r9d
0x1400758dd  mov     [rsp+0B8h+var_78], 1
0x1400758e2  mov     rdx, r15
0x1400758e5  mov     rcx, rsi
0x1400758e8  lea     r8d, [r9+8]
0x1400758ec  call    HsmpPrepareForMgmtOperation
0x1400758f1  mov     ecx, eax
0x1400758f3  mov     edi, eax
0x1400758f5  call    HsmDbgBreakOnStatus
0x1400758fa  test    edi, edi
0x1400758fc  jns     loc_1400759EE
0x140075902  mov     r10, cs:WPP_GLOBAL_Control
0x140075909  lea     rax, WPP_GLOBAL_Control
0x140075910  cmp     r10, rax
0x140075913  jz      loc_1400759A7
0x140075919  mov     ecx, [r10+2Ch]
0x14007591d  test    cl, 1
0x140075920  jz      loc_1400759A7
0x140075926  cmp     byte ptr [r10+29h], 2
0x14007592b  jb      short loc_1400759A7
0x14007592d  mov     rcx, rbx
0x140075930  call    HsmpGetStreamSize
0x140075935  mov     edx, 1Eh
0x14007593a  jmp     loc_140075B08
0x14007593f  mov     rdx, qword ptr [rsp+0B8h+FileInformation+8]
0x140075944  mov     rcx, rbx
0x140075947  call    HsmpUpdateBitmapSizesNoLock
0x14007594c  mov     rcx, [rbx+0A0h]
0x140075953  mov     rax, qword ptr [rsp+0B8h+FileInformation+8]
0x140075958  mov     [rcx], rax
0x14007595b  mov     dl, [rsp+0B8h+arg_20]
0x140075962  mov     rcx, rbx
0x140075965  call    HsmpSetInSyncNoLock
0x14007596a  mov     r9b, [rsp+0B8h+arg_20]
0x140075972  mov     r8, r15
0x140075975  mov     rdx, rbx
0x140075978  mov     byte ptr [rsp+0B8h+FileInformationClass], 0
0x14007597d  mov     rcx, rsi
0x140075980  call    HsmpRpCommitNoLock
0x140075985  mov     ecx, eax
0x140075987  mov     edi, eax
0x140075989  call    HsmDbgBreakOnStatus
0x14007598e  test    edi, edi
0x140075990  js      loc_140075BDD
0x140075996  test    r12, r12
0x140075999  jnz     loc_140075C33
0x14007599f  mov     rcx, rbx
0x1400759a2  call    HsmpReleaseBitmapLock
0x1400759a7  mov     rcx, [rbx+10h]
0x1400759ab  xor     edx, edx
0x1400759ad  add     rcx, 18h
0x1400759b1  call    cs:__imp_FltReleasePushLockEx
0x1400759b8  nop     dword ptr [rax+rax+00h]
0x1400759bd  cmp     [rsp+0B8h+var_78], 0
0x1400759c2  jz      short loc_1400759CC
0x1400759c4  mov     rcx, rbx
0x1400759c7  call    HsmpReInitializeUserRequestRundownProtection
0x1400759cc  mov     eax, edi
0x1400759ce  mov     rcx, [rsp+0B8h+var_48]
0x1400759d3  xor     rcx, rsp; StackCookie
0x1400759d6  call    __security_check_cookie
0x1400759db  add     rsp, 80h
0x1400759e2  pop     r15
0x1400759e4  pop     r13
0x1400759e6  pop     r12
0x1400759e8  pop     rdi
0x1400759e9  pop     rsi
0x1400759ea  pop     rbp
0x1400759eb  pop     rbx
0x1400759ec  retn
0x1400759ee  mov     rcx, [rbx+10h]
0x1400759f2  xor     edx, edx
0x1400759f4  add     rcx, 18h
0x1400759f8  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x1400759ff  nop     dword ptr [rax+rax+00h]
0x140075a04  cmp     [rsp+0B8h+arg_20], 0
0x140075a0c  jz      short loc_140075A24
0x140075a0e  mov     rbp, [rsp+0B8h+arg_28]
0x140075a16  test    rbp, rbp
0x140075a19  jnz     loc_140075B35
0x140075a1f  mov     rbp, [rsp+0B8h+var_68]
0x140075a24  mov     rcx, [rbx+0A0h]
0x140075a2b  test    rcx, rcx
0x140075a2e  jz      short loc_140075A42
0x140075a30  add     rcx, 28h ; '('
0x140075a34  xor     edx, edx
0x140075a36  call    cs:__imp_FltAcquirePushLockExclusiveEx
0x140075a3d  nop     dword ptr [rax+rax+00h]
0x140075a42  mov     eax, [rbx+1Ch]
0x140075a45  test    al, 2
0x140075a47  jnz     loc_14007595B
0x140075a4d  cmp     [rsp+0B8h+arg_20], 0
0x140075a55  jz      loc_14007595B
0x140075a5b  mov     rcx, [rsi+20h]; Instance
0x140075a5f  lea     r8, [rsp+0B8h+FileInformation]; FileInformation
0x140075a64  xor     eax, eax
0x140075a66  xorps   xmm0, xmm0
0x140075a69  mov     [rsp+0B8h+LengthReturned], rax; LengthReturned
0x140075a6e  mov     rdx, r15; FileObject
0x140075a71  movups  [rsp+0B8h+FileInformation], xmm0
0x140075a76  mov     [rsp+0B8h+var_50], rax
0x140075a7b  lea     r9d, [rax+18h]; Length
0x140075a7f  mov     [rsp+0B8h+FileInformationClass], 5; FileInformationClass
0x140075a87  call    cs:__imp_FltQueryInformationFile
0x140075a8e  nop     dword ptr [rax+rax+00h]
0x140075a93  mov     ecx, eax
0x140075a95  mov     edi, eax
0x140075a97  call    HsmDbgBreakOnStatus
0x140075a9c  test    edi, edi
0x140075a9e  jns     loc_14007593F
0x140075aa4  mov     rcx, cs:WPP_GLOBAL_Control
0x140075aab  lea     rax, WPP_GLOBAL_Control
0x140075ab2  cmp     rcx, rax
0x140075ab5  jz      loc_14007599F
0x140075abb  mov     eax, [rcx+2Ch]
0x140075abe  test    al, 1
0x140075ac0  jz      loc_14007599F
0x140075ac6  cmp     byte ptr [rcx+29h], 2
0x140075aca  jb      loc_14007599F
0x140075ad0  mov     eax, [rbx+1Ch]
0x140075ad3  mov     edx, 21h ; '!'
0x140075ad8  mov     rcx, [rcx+18h]
0x140075adc  mov     r9, rsi
0x140075adf  mov     [rsp+0B8h+var_80], edi
0x140075ae3  mov     [rsp+0B8h+var_88], r13
0x140075ae8  mov     dword ptr [rsp+0B8h+LengthReturned], eax
0x140075aec  mov     qword ptr [rsp+0B8h+FileInformationClass], rbx
0x140075af1  call    WPP_SF_qqLid
0x140075af6  jmp     loc_14007599F
0x140075afb  mov     rcx, rbx
0x140075afe  call    HsmpGetStreamSize
0x140075b03  mov     edx, 20h ; ' '
0x140075b08  mov     rcx, [r10+18h]
0x140075b0c  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140075b13  mov     [rsp+0B8h+var_80], edi
0x140075b17  mov     r9, rbx
0x140075b1a  mov     [rsp+0B8h+var_88], r13
0x140075b1f  mov     [rsp+0B8h+LengthReturned], rax
0x140075b24  mov     eax, [rbx+1Ch]
0x140075b27  mov     [rsp+0B8h+FileInformationClass], eax
0x140075b2b  call    WPP_SF_qLiid
0x140075b30  jmp     loc_1400759A7
0x140075b35  mov     rcx, [rsi+20h]; Instance
0x140075b39  lea     r8, [rsp+0B8h+var_70]
0x140075b3e  mov     rdx, r15; FileObject
0x140075b41  call    HsmpQueryLastEffectiveUsn
0x140075b46  mov     ecx, eax
0x140075b48  mov     edi, eax
0x140075b4a  call    HsmDbgBreakOnStatus
0x140075b4f  test    edi, edi
0x140075b51  jns     short loc_140075B93
0x140075b53  mov     r10, cs:WPP_GLOBAL_Control
0x140075b5a  lea     rax, WPP_GLOBAL_Control
0x140075b61  cmp     r10, rax
0x140075b64  jz      loc_1400759A7
0x140075b6a  mov     eax, [r10+2Ch]
0x140075b6e  test    al, 1
0x140075b70  jz      loc_1400759A7
0x140075b76  cmp     byte ptr [r10+29h], 2
0x140075b7b  jb      loc_1400759A7
0x140075b81  mov     rcx, rbx
0x140075b84  call    HsmpGetStreamSize
0x140075b89  mov     edx, 1Fh
0x140075b8e  jmp     loc_140075B08
0x140075b93  cmp     rbp, [rsp+0B8h+var_70]
0x140075b98  jz      loc_140075A1F
0x140075b9e  mov     edi, 0C000CF08h
0x140075ba3  mov     ecx, edi
0x140075ba5  call    HsmDbgBreakOnStatus
0x140075baa  mov     r10, cs:WPP_GLOBAL_Control
0x140075bb1  lea     rax, WPP_GLOBAL_Control
0x140075bb8  cmp     r10, rax
0x140075bbb  jz      loc_1400759A7
0x140075bc1  mov     eax, [r10+2Ch]
0x140075bc5  test    al, 1
0x140075bc7  jz      loc_1400759A7
0x140075bcd  cmp     byte ptr [r10+29h], 2
0x140075bd2  jb      loc_1400759A7
0x140075bd8  jmp     loc_140075AFB
0x140075bdd  mov     rcx, cs:WPP_GLOBAL_Control
0x140075be4  lea     rax, WPP_GLOBAL_Control
0x140075beb  cmp     rcx, rax
0x140075bee  jz      loc_14007599F
0x140075bf4  mov     eax, [rcx+2Ch]
0x140075bf7  test    al, 1
0x140075bf9  jz      loc_14007599F
0x140075bff  cmp     byte ptr [rcx+29h], 2
0x140075c03  jb      loc_14007599F
0x140075c09  mov     rax, [rbp+20h]
0x140075c0d  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140075c14  mov     rcx, [rcx+18h]
0x140075c18  mov     edx, 22h ; '"'
0x140075c1d  mov     dword ptr [rsp+0B8h+LengthReturned], edi
0x140075c21  mov     r9, rsi
0x140075c24  mov     qword ptr [rsp+0B8h+FileInformationClass], rax
0x140075c29  call    WPP_SF_qqd
0x140075c2e  jmp     loc_14007599F
0x140075c33  mov     rcx, [rsi+20h]; Instance
0x140075c37  lea     r8, [rsp+0B8h+var_70]
0x140075c3c  mov     rdx, r15; FileObject
0x140075c3f  call    HsmpQueryLastEffectiveUsn
0x140075c44  mov     ecx, eax
0x140075c46  mov     edi, eax
0x140075c48  call    HsmDbgBreakOnStatus
0x140075c4d  test    edi, edi
0x140075c4f  jns     short loc_140075CB9
0x140075c51  mov     r10, cs:WPP_GLOBAL_Control
0x140075c58  lea     rax, WPP_GLOBAL_Control
0x140075c5f  cmp     r10, rax
0x140075c62  jz      loc_14007599F
0x140075c68  mov     eax, [r10+2Ch]
0x140075c6c  test    al, 1
0x140075c6e  jz      loc_14007599F
0x140075c74  cmp     byte ptr [r10+29h], 2
0x140075c79  jb      loc_14007599F
0x140075c7f  mov     rcx, rbx
0x140075c82  call    HsmpGetStreamSize
0x140075c87  mov     rcx, [r10+18h]
0x140075c8b  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140075c92  mov     [rsp+0B8h+var_80], edi
0x140075c96  mov     edx, 23h ; '#'
0x140075c9b  mov     [rsp+0B8h+var_88], r13
0x140075ca0  mov     r9, rbx
0x140075ca3  mov     [rsp+0B8h+LengthReturned], rax
0x140075ca8  mov     eax, [rbx+1Ch]
0x140075cab  mov     [rsp+0B8h+FileInformationClass], eax
0x140075caf  call    WPP_SF_qLiid
0x140075cb4  jmp     loc_14007599F
0x140075cb9  mov     rax, [rsp+0B8h+var_70]
0x140075cbe  mov     [r12], rax
0x140075cc2  jmp     loc_14007599F
```
