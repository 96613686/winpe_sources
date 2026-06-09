# HsmiInfoPrepareForPostRename

- ea: `0x140054bbc`
- end: `0x14005535b`
- name: `HsmiInfoPrepareForPostRename`
- size: `1951`
- prototype: `__int64 __fastcall(__int64, int SyncPolicy, __int64 *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140053800`

## callees

- `0x140001d00`
- `0x140002aec`
- `0x140003c50`
- `0x140006da0`
- `0x140007ddc`
- `0x14000abb8`
- `0x14000ac28`
- `0x14000d388`
- `0x14001b05c`
- `0x14001b0fc`
- `0x140052574`
- `0x1400548d0`
- `0x140054b24`
- `0x140054bbc`
- `0x140055a8c`
- `0x140058ddc`
- `0x14005e76c`
- `0x14005ec60`
- `0x14005f670`
- `0x140075ee4`
- `0x140077b34`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140054f91`
- `ntoskrnl!ObfDereferenceObject` at `0x140054f91`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055320`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005534a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055320`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005534a`
- `ntoskrnl!ExAllocatePool2` at `0x140054ce6`
- `ntoskrnl!ExAllocatePool2` at `0x140054ce6`
- `FLTMGR!FltClose` at `0x140054f7d`
- `FLTMGR!FltClose` at `0x140054f7d`
- `FLTMGR!FltReferenceContext` at `0x140055119`
- `FLTMGR!FltReferenceContext` at `0x140055119`
- `FLTMGR!FltGetRequestorProcess` at `0x140054d2a`
- `FLTMGR!FltGetRequestorProcess` at `0x1400552c5`
- `FLTMGR!FltGetRequestorProcess` at `0x140054d2a`
- `FLTMGR!FltGetRequestorProcess` at `0x1400552c5`
- `FLTMGR!FltReleaseContext` at `0x140055336`
- `FLTMGR!FltReleaseContext` at `0x140055336`

## pseudocode

```c
__int64 __fastcall HsmiInfoPrepareForPostRename(__int64 a1, int SyncPolicy, __int64 *a3)
{
  struct _FLT_CALLBACK_DATA *v4; // r13
  __int64 v5; // r9
  __int64 v6; // rsi
  char v7; // dl
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  PFILE_OBJECT TargetFileObject; // rcx
  __int64 v10; // rdi
  __int16 v11; // bx
  __int64 v12; // rdx
  unsigned int v13; // r15d
  __int64 v14; // r12
  char IsPlaceholder; // al
  int v16; // eax
  __int64 Pool2; // rax
  __int64 v18; // rdx
  PEPROCESS RequestorProcess; // rax
  char v20; // bl
  PDEVICE_OBJECT v22; // r10
  __int64 v23; // rdx
  __int64 StreamSize; // rax
  __int64 v25; // r8
  PDEVICE_OBJECT v26; // r10
  __int64 v27; // rdx
  __int64 v28; // r12
  PFLT_IO_PARAMETER_BLOCK v29; // r8
  unsigned int v30; // eax
  unsigned int v31; // ebx
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 v34; // r8
  PEPROCESS v35; // rax
  void *v36; // rcx
  void *v37; // rcx
  int v38; // [rsp+20h] [rbp-89h]
  void *v39; // [rsp+30h] [rbp-79h]
  char v40; // [rsp+60h] [rbp-49h]
  int v41[2]; // [rsp+68h] [rbp-41h]
  int v42[2]; // [rsp+70h] [rbp-39h]
  int v43; // [rsp+78h] [rbp-31h] BYREF
  PVOID Object; // [rsp+80h] [rbp-29h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-21h] BYREF
  int v46; // [rsp+90h] [rbp-19h]
  __int64 v47; // [rsp+98h] [rbp-11h]
  __int64 v48; // [rsp+A0h] [rbp-9h]
  int v49[2]; // [rsp+A8h] [rbp-1h]
  LARGE_INTEGER ByteOffset; // [rsp+B0h] [rbp+7h]
  char v52; // [rsp+118h] [rbp+6Fh]
  char v54; // [rsp+128h] [rbp+7Fh]

  v4 = *(struct _FLT_CALLBACK_DATA **)(a1 + 24);
  v5 = *(_QWORD *)(a1 + 32);
  v6 = *(_QWORD *)(a1 + 8);
  v7 = *(_BYTE *)(a1 + 53);
  v47 = *(_QWORD *)(a1 + 40);
  *(_QWORD *)v41 = *(_QWORD *)a1;
  v46 = *(_DWORD *)(a1 + 48);
  v52 = *(_BYTE *)(a1 + 52);
  Iopb = v4->Iopb;
  v48 = v5;
  *(_QWORD *)v49 = v6;
  v54 = v7;
  TargetFileObject = Iopb->TargetFileObject;
  ByteOffset = Iopb->Parameters.Read.ByteOffset;
  *(_QWORD *)v42 = TargetFileObject;
  v10 = 0;
  FileHandle = 0;
  Object = 0;
  v11 = 0;
  v43 = 0;
  *a3 = 0;
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    v6 = 0;
LABEL_26:
    v4->IoStatus.Status = SyncPolicy;
    v13 = 4;
    v4->IoStatus.Information = 0;
    goto LABEL_19;
  }
  v13 = 1;
  if ( v6 && (v6 = *(_QWORD *)(v6 + 16)) != 0 && (v28 = *(_QWORD *)(v6 + 16)) != 0 )
    v14 = *(_QWORD *)(v28 + 32);
  else
    v14 = 0;
  IsPlaceholder = HsmpIsPlaceholder(v6, v12);
  v40 = IsPlaceholder;
  if ( !v52 && !IsPlaceholder )
    goto LABEL_20;
  if ( IsPlaceholder )
  {
    SyncPolicy = HsmpCldGetSyncPolicy(v41[0], v6, v42[0], 0, (__int64)&v43);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
          *(_QWORD *)v41,
          v6,
          v14,
          SyncPolicy);
      }
      goto LABEL_26;
    }
    v11 = v43;
  }
  if ( v52 )
  {
    v16 = v14
        ? HsmpOpenFileByIdEx(
            v41[0],
            *(_QWORD *)(*(_QWORD *)v41 + 32LL),
            v14,
            129,
            v38,
            0x200000,
            0,
            (__int64)&FileHandle,
            (__int64)&Object)
        : HsmpRelativeStreamOpen(v41[0], v42[0], 0, 129, 1u, 0x200000, v39, (__int64)&FileHandle, (__int64)&Object);
    SyncPolicy = v16;
    HsmDbgBreakOnStatus(v16);
    if ( SyncPolicy < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_26;
      }
      v27 = 25;
LABEL_64:
      WPP_SF_qiqiid(
        v26->AttachedDevice,
        v27,
        WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
        v4,
        *(_QWORD *)v41,
        *(_QWORD *)v42,
        v14,
        v6,
        SyncPolicy);
      goto LABEL_26;
    }
  }
  Pool2 = ExAllocatePool2(256, 48, 1668248392);
  v10 = Pool2;
  if ( !Pool2 )
  {
    SyncPolicy = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_26;
    }
    v23 = 26;
LABEL_44:
    WPP_SF_qqiqd(
      v22->AttachedDevice,
      v23,
      WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
      v4,
      *(_QWORD *)v41,
      *(_QWORD *)v42,
      v14,
      SyncPolicy);
    goto LABEL_26;
  }
  *(_DWORD *)Pool2 = 1668248392;
  if ( v6 )
  {
    *(_QWORD *)(Pool2 + 8) = v6;
    FltReferenceContext((PFLT_CONTEXT)v6);
  }
  if ( (unsigned __int8)HsmpCldIsCallbackRequested(5, v6, v4) )
  {
    SyncPolicy = HsmiQueryFullFilePath(*(_QWORD *)(*(_QWORD *)v41 + 32LL), v18, *(_QWORD *)v42, 257, v10 + 24);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_26;
      }
      v23 = 27;
      goto LABEL_44;
    }
  }
  RequestorProcess = FltGetRequestorProcess(v4);
  if ( (unsigned __int8)HsmOsIsSyncProviderProcess(RequestorProcess) || !v48 || v47 == v48 )
  {
LABEL_16:
    if ( !v40
      || (v11 & 0x400) != 0 && (v35 = FltGetRequestorProcess(v4), (unsigned __int8)HsmOsIsSyncProviderProcess(v35)) )
    {
      v20 = 0;
      if ( !v52 && !(unsigned __int8)HsmpCldIsCallbackRequested(5, v6, v4) )
        goto LABEL_19;
    }
    else
    {
      HsmpPersistInSync(v6, *(_QWORD *)v42);
      v20 = 1;
    }
    *(_BYTE *)(v10 + 44) = 0;
    *(_QWORD *)(v10 + 16) = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a1 + 16) = 0;
    if ( !v52 || !ByteOffset.QuadPart )
      LOBYTE(v13) = 0;
    *(_DWORD *)(v10 + 40) = v46;
    *(_BYTE *)(v10 + 45) = v13;
    v13 = 0;
    *(_BYTE *)(v10 + 46) = v20;
    *a3 = v10;
    v10 = 0;
LABEL_19:
    if ( !v10 )
      goto LABEL_20;
    goto LABEL_80;
  }
  if ( v52 )
  {
    SyncPolicy = HsmpRecurseDirectory(
                   v41[0],
                   (_DWORD)FileHandle,
                   (_DWORD)Object,
                   v40 != 0 ? 1040 : 16,
                   1,
                   0,
                   (__int64)HsmiInfoPopulatePlaceholderOnRename,
                   (__int64)HsmiInfoHydratePlaceholderOnRename,
                   (__int64)v4);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( SyncPolicy < 0 )
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_26;
      }
      v27 = 30;
      goto LABEL_64;
    }
    goto LABEL_16;
  }
  SyncPolicy = HsmpAcquireUserRequestRundownProtection((PFLT_CONTEXT)v6, v4);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(v6);
      WPP_SF_qqLiiqd(
        *(_QWORD *)(v25 + 24),
        28,
        v25,
        *(_QWORD *)v41,
        v6,
        *(_DWORD *)(v6 + 28),
        StreamSize,
        v14,
        v4,
        SyncPolicy);
    }
    goto LABEL_26;
  }
  *(_BYTE *)(v10 + 44) = 1;
  *(_QWORD *)(v10 + 16) = *(_QWORD *)(a1 + 16);
  v29 = v4->Iopb;
  *(_QWORD *)(a1 + 16) = 0;
  v30 = HsmpRecallInitiateHydrationEx(
          v49[0],
          v6,
          (int)v29->TargetFileObject,
          65543,
          v4,
          0,
          -1,
          0,
          (unsigned __int64)&HsmiInfoRecallForRenameCompletion & -(__int64)(v54 != 0));
  SyncPolicy = v4->IoStatus.Status;
  v31 = v30;
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v32 = HsmpGetStreamSize(v6);
      WPP_SF_qqLiiqiid(
        *(_QWORD *)(v33 + 24),
        v33,
        v34,
        *(_QWORD *)v41,
        v6,
        *(_DWORD *)(v6 + 28),
        v32,
        v14,
        v4,
        v48,
        v47,
        SyncPolicy);
    }
    goto LABEL_26;
  }
  v13 = v31;
  if ( !v31 )
  {
    *a3 = v10;
    v10 = 0;
    goto LABEL_19;
  }
LABEL_80:
  v36 = *(void **)(v10 + 16);
  if ( v36 )
    HsmpReleaseFileNameLock(v36);
  if ( *(_BYTE *)(v10 + 44) )
    HsmpReleaseUserRequestRundownProtection(*(PFLT_CONTEXT *)(v10 + 8));
  v37 = *(void **)(v10 + 32);
  if ( v37 )
    ExFreePoolWithTag(v37, 0x73557348u);
  if ( *(_QWORD *)(v10 + 8) )
    FltReleaseContext((PFLT_CONTEXT)v6);
  ExFreePoolWithTag((PVOID)v10, 0x636F7348u);
LABEL_20:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return v13;
}

```

## disassembly

```asm
0x140054bbc  mov     [rsp-8+arg_10], r8
0x140054bc1  mov     [rsp-8+arg_0], rcx
0x140054bc6  push    rbp
0x140054bc7  push    rbx
0x140054bc8  push    rsi
0x140054bc9  push    rdi
0x140054bca  push    r12
0x140054bcc  push    r13
0x140054bce  push    r14
0x140054bd0  push    r15
0x140054bd2  lea     rbp, [rsp-1Fh]
0x140054bd7  sub     rsp, 0C8h
0x140054bde  mov     rax, [rcx+28h]
0x140054be2  mov     r14d, edx
0x140054be5  mov     r13, [rcx+18h]
0x140054be9  mov     r9, [rcx+20h]
0x140054bed  mov     rsi, [rcx+8]
0x140054bf1  mov     dl, [rcx+35h]
0x140054bf4  mov     [rbp+57h+var_68], rax
0x140054bf8  mov     rax, [rcx]
0x140054bfb  mov     qword ptr [rbp+57h+var_98], rax
0x140054bff  mov     eax, [rcx+30h]
0x140054c02  mov     [rbp+57h+var_70], eax
0x140054c05  mov     al, [rcx+34h]
0x140054c08  mov     [rbp+57h+arg_8], al
0x140054c0b  mov     rax, [r13+10h]
0x140054c0f  mov     [rbp+57h+var_60], r9
0x140054c13  mov     qword ptr [rbp+57h+var_58], rsi
0x140054c17  mov     [rbp+57h+arg_18], dl
0x140054c1a  mov     rcx, [rax+8]
0x140054c1e  mov     rax, [rax+28h]
0x140054c22  mov     [rbp+57h+var_50], rax
0x140054c26  xor     eax, eax
0x140054c28  mov     qword ptr [rbp+57h+var_90], rcx
0x140054c2c  mov     edi, eax
0x140054c2e  mov     ecx, r14d
0x140054c31  mov     [rbp+57h+FileHandle], rax
0x140054c35  mov     [rbp+57h+Object], rax
0x140054c39  mov     ebx, eax
0x140054c3b  mov     [rbp+57h+var_88], eax
0x140054c3e  mov     [r8], rax
0x140054c41  call    HsmDbgBreakOnStatus
0x140054c46  test    r14d, r14d
0x140054c49  js      loc_140054DBA
0x140054c4f  lea     r15d, [rdi+1]
0x140054c53  test    rsi, rsi
0x140054c56  jnz     loc_14005501F
0x140054c5c  xor     r12d, r12d
0x140054c5f  mov     rcx, rsi
0x140054c62  call    HsmpIsPlaceholder
0x140054c67  mov     [rbp+57h+var_A0], al
0x140054c6a  cmp     [rbp+57h+arg_8], bl
0x140054c6d  jnz     short loc_140054C77
0x140054c6f  test    al, al
0x140054c71  jz      loc_140054D88
0x140054c77  test    al, al
0x140054c79  jnz     loc_140055043
0x140054c7f  cmp     [rbp+57h+arg_8], dil
0x140054c83  jz      short loc_140054CD6
0x140054c85  lea     rax, [rbp+57h+Object]
0x140054c89  mov     r9d, 81h; int
0x140054c8f  mov     [rsp+100h+var_C0], rax; __int64
0x140054c94  lea     rax, [rbp+57h+FileHandle]
0x140054c98  mov     [rsp+100h+var_C8], rax; __int64
0x140054c9d  test    r12, r12
0x140054ca0  jnz     loc_140054F55
0x140054ca6  mov     rdx, qword ptr [rbp+57h+var_90]; int
0x140054caa  xor     r8d, r8d; int
0x140054cad  mov     rcx, qword ptr [rbp+57h+var_98]; int
0x140054cb1  mov     dword ptr [rsp+100h+var_D8], 200000h; int
0x140054cb9  mov     [rsp+100h+var_E0], r15d; ULONG
0x140054cbe  call    HsmpRelativeStreamOpen
0x140054cc3  mov     ecx, eax
0x140054cc5  mov     r14d, eax
0x140054cc8  call    HsmDbgBreakOnStatus
0x140054ccd  test    r14d, r14d
0x140054cd0  js      loc_140054FDE
0x140054cd6  mov     edx, 30h ; '0'
0x140054cdb  mov     ecx, 100h
0x140054ce0  mov     r8d, 636F7348h
0x140054ce6  call    cs:__imp_ExAllocatePool2
0x140054ced  nop     dword ptr [rax+rax+00h]
0x140054cf2  mov     rdi, rax
0x140054cf5  test    rax, rax
0x140054cf8  jz      loc_140054DD0
0x140054cfe  mov     dword ptr [rax], 636F7348h
0x140054d04  test    rsi, rsi
0x140054d07  jnz     loc_140055112
0x140054d0d  xor     r9d, r9d
0x140054d10  mov     r8, r13
0x140054d13  mov     rdx, rsi
0x140054d16  lea     ecx, [r9+5]
0x140054d1a  call    HsmpCldIsCallbackRequested
0x140054d1f  test    al, al
0x140054d21  jnz     loc_140054EBA
0x140054d27  mov     rcx, r13; CallbackData
0x140054d2a  call    cs:__imp_FltGetRequestorProcess
0x140054d31  nop     dword ptr [rax+rax+00h]
0x140054d36  mov     rcx, rax
0x140054d39  call    HsmOsIsSyncProviderProcess
0x140054d3e  test    al, al
0x140054d40  jz      loc_140054E0B
0x140054d46  xor     r12d, r12d
0x140054d49  cmp     [rbp+57h+var_A0], r12b
0x140054d4d  jnz     loc_1400552BC
0x140054d53  mov     bl, r12b
0x140054d56  cmp     [rbp+57h+arg_8], r12b
0x140054d5a  jnz     loc_140054FA2
0x140054d60  xor     r9d, r9d
0x140054d63  mov     r8, r13
0x140054d66  mov     rdx, rsi
0x140054d69  lea     ecx, [r9+5]
0x140054d6d  call    HsmpCldIsCallbackRequested
0x140054d72  test    al, al
0x140054d74  jnz     loc_140054FA2
0x140054d7a  test    r14d, r14d
0x140054d7d  js      short loc_140054DBC
0x140054d7f  test    rdi, rdi
0x140054d82  jnz     loc_1400552F5
0x140054d88  mov     rax, [rbp+57h+Object]
0x140054d8c  test    rax, rax
0x140054d8f  jnz     loc_140054F8E
0x140054d95  mov     rax, [rbp+57h+FileHandle]
0x140054d99  test    rax, rax
0x140054d9c  jnz     loc_140054F7A
0x140054da2  mov     eax, r15d
0x140054da5  add     rsp, 0C8h
0x140054dac  pop     r15
0x140054dae  pop     r14
0x140054db0  pop     r13
0x140054db2  pop     r12
0x140054db4  pop     rdi
0x140054db5  pop     rsi
0x140054db6  pop     rbx
0x140054db7  pop     rbp
0x140054db8  retn
0x140054dba  xor     esi, esi
0x140054dbc  mov     [r13+18h], r14d
0x140054dc0  mov     r15d, 4
0x140054dc6  mov     qword ptr [r13+20h], 0
0x140054dce  jmp     short loc_140054D7F
0x140054dd0  mov     r14d, 0C000009Ah
0x140054dd6  mov     ecx, r14d
0x140054dd9  call    HsmDbgBreakOnStatus
0x140054dde  mov     r10, cs:WPP_GLOBAL_Control
0x140054de5  lea     rcx, WPP_GLOBAL_Control
0x140054dec  cmp     r10, rcx
0x140054def  jz      short loc_140054DBC
0x140054df1  mov     eax, [r10+2Ch]
0x140054df5  test    r15b, al
0x140054df8  jz      short loc_140054DBC
0x140054dfa  cmp     byte ptr [r10+29h], 2
0x140054dff  jb      short loc_140054DBC
0x140054e01  mov     edx, 1Ah
0x140054e06  jmp     loc_140054F21
0x140054e0b  mov     rax, [rbp+57h+var_60]
0x140054e0f  test    rax, rax
0x140054e12  jz      loc_140054D46
0x140054e18  cmp     [rbp+57h+var_68], rax
0x140054e1c  jz      loc_140054D46
0x140054e22  cmp     [rbp+57h+arg_8], 0
0x140054e26  jnz     loc_14005522A
0x140054e2c  mov     rdx, r13; CallbackData
0x140054e2f  mov     rcx, rsi; Context
0x140054e32  call    HsmpAcquireUserRequestRundownProtection
0x140054e37  mov     ecx, eax
0x140054e39  mov     r14d, eax
0x140054e3c  call    HsmDbgBreakOnStatus
0x140054e41  xor     edx, edx
0x140054e43  test    r14d, r14d
0x140054e46  jns     loc_14005512A
0x140054e4c  mov     r8, cs:WPP_GLOBAL_Control
0x140054e53  lea     rcx, WPP_GLOBAL_Control
0x140054e5a  cmp     r8, rcx
0x140054e5d  jz      loc_140054DBC
0x140054e63  mov     eax, [r8+2Ch]
0x140054e67  test    r15b, al
0x140054e6a  jz      loc_140054DBC
0x140054e70  cmp     byte ptr [r8+29h], 2
0x140054e75  jb      loc_140054DBC
0x140054e7b  mov     rcx, rsi
0x140054e7e  call    HsmpGetStreamSize
0x140054e83  mov     r9, qword ptr [rbp+57h+var_98]
0x140054e87  mov     edx, 1Ch
0x140054e8c  mov     rcx, [r8+18h]
0x140054e90  mov     dword ptr [rsp+100h+var_B8], r14d
0x140054e95  mov     [rsp+100h+var_C0], r13
0x140054e9a  mov     [rsp+100h+var_C8], r12
0x140054e9f  mov     [rsp+100h+var_D0], rax
0x140054ea4  mov     eax, [rsi+1Ch]
0x140054ea7  mov     dword ptr [rsp+100h+var_D8], eax
0x140054eab  mov     qword ptr [rsp+100h+var_E0], rsi
0x140054eb0  call    WPP_SF_qqLiiqd
0x140054eb5  jmp     loc_140054DBC
0x140054eba  mov     r8, qword ptr [rbp+57h+var_90]
0x140054ebe  lea     rax, [rdi+18h]
0x140054ec2  mov     qword ptr [rsp+100h+var_E0], rax
0x140054ec7  mov     r9d, 101h
0x140054ecd  mov     rax, qword ptr [rbp+57h+var_98]
0x140054ed1  mov     rcx, [rax+20h]
0x140054ed5  call    HsmiQueryFullFilePath
0x140054eda  mov     ecx, eax
0x140054edc  mov     r14d, eax
0x140054edf  call    HsmDbgBreakOnStatus
0x140054ee4  test    r14d, r14d
0x140054ee7  jns     loc_140054D27
0x140054eed  mov     r10, cs:WPP_GLOBAL_Control
0x140054ef4  lea     rcx, WPP_GLOBAL_Control
0x140054efb  cmp     r10, rcx
0x140054efe  jz      loc_140054DBC
0x140054f04  mov     eax, [r10+2Ch]
0x140054f08  test    r15b, al
0x140054f0b  jz      loc_140054DBC
0x140054f11  cmp     byte ptr [r10+29h], 2
0x140054f16  jb      loc_140054DBC
0x140054f1c  mov     edx, 1Bh
0x140054f21  mov     rax, qword ptr [rbp+57h+var_90]
0x140054f25  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140054f2c  mov     rcx, [r10+18h]
0x140054f30  mov     r9, r13
0x140054f33  mov     dword ptr [rsp+100h+var_C8], r14d
0x140054f38  mov     [rsp+100h+var_D0], r12
0x140054f3d  mov     [rsp+100h+var_D8], rax
0x140054f42  mov     rax, qword ptr [rbp+57h+var_98]
0x140054f46  mov     qword ptr [rsp+100h+var_E0], rax
0x140054f4b  call    WPP_SF_qqiqd
0x140054f50  jmp     loc_140054DBC
0x140054f55  mov     rax, qword ptr [rbp+57h+var_98]
0x140054f59  mov     r8, r12
0x140054f5c  mov     byte ptr [rsp+100h+var_D0], dil
0x140054f61  mov     rcx, rax
0x140054f64  mov     dword ptr [rsp+100h+var_D8], 200000h
0x140054f6c  mov     rdx, [rax+20h]
0x140054f70  call    HsmpOpenFileByIdEx
0x140054f75  jmp     loc_140054CC3
0x140054f7a  mov     rcx, rax; FileHandle
0x140054f7d  call    cs:__imp_FltClose
0x140054f84  nop     dword ptr [rax+rax+00h]
0x140054f89  jmp     loc_140054DA2
0x140054f8e  mov     rcx, rax; Object
0x140054f91  call    cs:__imp_ObfDereferenceObject
0x140054f98  nop     dword ptr [rax+rax+00h]
0x140054f9d  jmp     loc_140054D95
0x140054fa2  mov     rcx, [rbp+57h+arg_0]
0x140054fa6  mov     [rdi+2Ch], r12b
0x140054faa  mov     rax, [rcx+10h]
0x140054fae  mov     [rdi+10h], rax
0x140054fb2  mov     [rcx+10h], r12
0x140054fb6  cmp     [rbp+57h+arg_8], r12b
0x140054fba  jnz     short loc_140055017
0x140054fbc  mov     r15b, r12b
0x140054fbf  mov     eax, [rbp+57h+var_70]
0x140054fc2  mov     [rdi+28h], eax
0x140054fc5  mov     rax, [rbp+57h+arg_10]
0x140054fc9  mov     [rdi+2Dh], r15b
0x140054fcd  mov     r15d, r12d
0x140054fd0  mov     [rdi+2Eh], bl
0x140054fd3  mov     [rax], rdi
0x140054fd6  mov     rdi, r12
0x140054fd9  jmp     loc_140054D7A
0x140054fde  mov     r10, cs:WPP_GLOBAL_Control
0x140054fe5  lea     rcx, WPP_GLOBAL_Control
0x140054fec  cmp     r10, rcx
0x140054fef  jz      loc_140054DBC
0x140054ff5  mov     eax, [r10+2Ch]
0x140054ff9  test    r15b, al
0x140054ffc  jz      loc_140054DBC
0x140055002  cmp     byte ptr [r10+29h], 2
0x140055007  jb      loc_140054DBC
0x14005500d  mov     edx, 19h
0x140055012  jmp     loc_1400550D9
0x140055017  cmp     [rbp+57h+var_50], r12
0x14005501b  jnz     short loc_140054FBF
0x14005501d  jmp     short loc_140054FBC
0x14005501f  mov     rsi, [rsi+10h]
0x140055023  test    rsi, rsi
0x140055026  jz      loc_140054C5C
0x14005502c  mov     r12, [rsi+10h]
0x140055030  test    r12, r12
0x140055033  jz      loc_140054C5C
0x140055039  mov     r12, [r12+20h]
0x14005503e  jmp     loc_140054C5F
0x140055043  mov     rbx, qword ptr [rbp+57h+var_98]
0x140055047  lea     rax, [rbp+57h+var_88]
0x14005504b  mov     r8, qword ptr [rbp+57h+var_90]
0x14005504f  mov     rcx, rbx
0x140055052  xor     r9d, r9d
0x140055055  mov     qword ptr [rsp+100h+var_E0], rax
0x14005505a  mov     rdx, rsi
0x14005505d  call    HsmpCldGetSyncPolicy
0x140055062  mov     ecx, eax
0x140055064  mov     r14d, eax
0x140055067  call    HsmDbgBreakOnStatus
0x14005506c  test    r14d, r14d
0x14005506f  jns     short loc_1400550CC
0x140055071  mov     r10, cs:WPP_GLOBAL_Control
0x140055078  lea     rcx, WPP_GLOBAL_Control
0x14005507f  cmp     r10, rcx
0x140055082  jz      loc_140054DBC
0x140055088  mov     edx, [r10+2Ch]
  ... truncated ...
```
