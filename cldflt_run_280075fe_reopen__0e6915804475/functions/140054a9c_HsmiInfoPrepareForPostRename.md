# HsmiInfoPrepareForPostRename

- ea: `0x140054a9c`
- end: `0x14005523b`
- name: `HsmiInfoPrepareForPostRename`
- size: `1951`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400536e0`

## callees

- `0x140001d00`
- `0x140002aec`
- `0x140003c50`
- `0x140006da0`
- `0x140007ddc`
- `0x14000abb8`
- `0x14000ac28`
- `0x14000d388`
- `0x14001afdc`
- `0x14001b07c`
- `0x140052454`
- `0x1400547b0`
- `0x140054a04`
- `0x140054a9c`
- `0x14005596c`
- `0x140058cbc`
- `0x14005e64c`
- `0x14005eb40`
- `0x14005f550`
- `0x140075dc4`
- `0x1400779f4`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x140054e71`
- `ntoskrnl!ObfDereferenceObject` at `0x140054e71`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055200`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005522a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055200`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005522a`
- `ntoskrnl!ExAllocatePool2` at `0x140054bc6`
- `ntoskrnl!ExAllocatePool2` at `0x140054bc6`
- `FLTMGR!FltClose` at `0x140054e5d`
- `FLTMGR!FltClose` at `0x140054e5d`
- `FLTMGR!FltReferenceContext` at `0x140054ff9`
- `FLTMGR!FltReferenceContext` at `0x140054ff9`
- `FLTMGR!FltGetRequestorProcess` at `0x140054c0a`
- `FLTMGR!FltGetRequestorProcess` at `0x1400551a5`
- `FLTMGR!FltGetRequestorProcess` at `0x140054c0a`
- `FLTMGR!FltGetRequestorProcess` at `0x1400551a5`
- `FLTMGR!FltReleaseContext` at `0x140055216`
- `FLTMGR!FltReleaseContext` at `0x140055216`

## pseudocode

```c
__int64 __fastcall HsmiInfoPrepareForPostRename(__int64 a1, int a2, __int64 *a3)
{
  __int64 SyncPolicy; // r14
  struct _FLT_CALLBACK_DATA *v4; // r13
  __int64 v5; // r9
  __int64 v6; // rsi
  char v7; // dl
  PFLT_IO_PARAMETER_BLOCK Iopb; // rax
  struct _FILE_OBJECT *TargetFileObject; // rcx
  __int64 v10; // rdi
  __int16 v11; // bx
  unsigned int v12; // r15d
  __int64 v13; // r12
  char IsPlaceholder; // al
  unsigned int v15; // eax
  __int64 Pool2; // rax
  __int64 v17; // rdx
  PEPROCESS RequestorProcess; // rax
  char v19; // bl
  PDEVICE_OBJECT v21; // r10
  __int64 v22; // rdx
  __int64 StreamSize; // rax
  __int64 v24; // r8
  PDEVICE_OBJECT v25; // r10
  __int64 v26; // rdx
  __int64 v27; // r12
  PFLT_IO_PARAMETER_BLOCK v28; // r8
  unsigned int v29; // eax
  unsigned int v30; // ebx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // r8
  PEPROCESS v34; // rax
  void *v35; // rcx
  void *v36; // rcx
  __int64 v37; // [rsp+20h] [rbp-89h]
  void *v38; // [rsp+30h] [rbp-79h]
  char v39; // [rsp+60h] [rbp-49h]
  __int64 v40; // [rsp+68h] [rbp-41h]
  struct _FILE_OBJECT *v41; // [rsp+70h] [rbp-39h]
  int v42; // [rsp+78h] [rbp-31h] BYREF
  PVOID Object; // [rsp+80h] [rbp-29h] BYREF
  HANDLE FileHandle; // [rsp+88h] [rbp-21h] BYREF
  int v45; // [rsp+90h] [rbp-19h]
  __int64 v46; // [rsp+98h] [rbp-11h]
  __int64 v47; // [rsp+A0h] [rbp-9h]
  int v48[2]; // [rsp+A8h] [rbp-1h]
  LARGE_INTEGER ByteOffset; // [rsp+B0h] [rbp+7h]
  char v51; // [rsp+118h] [rbp+6Fh]
  char v53; // [rsp+128h] [rbp+7Fh]

  LODWORD(SyncPolicy) = a2;
  v4 = *(struct _FLT_CALLBACK_DATA **)(a1 + 24);
  v5 = *(_QWORD *)(a1 + 32);
  v6 = *(_QWORD *)(a1 + 8);
  v7 = *(_BYTE *)(a1 + 53);
  v46 = *(_QWORD *)(a1 + 40);
  v40 = *(_QWORD *)a1;
  v45 = *(_DWORD *)(a1 + 48);
  v51 = *(_BYTE *)(a1 + 52);
  Iopb = v4->Iopb;
  v47 = v5;
  *(_QWORD *)v48 = v6;
  v53 = v7;
  TargetFileObject = Iopb->TargetFileObject;
  ByteOffset = Iopb->Parameters.Read.ByteOffset;
  v41 = TargetFileObject;
  v10 = 0;
  FileHandle = 0;
  Object = 0;
  v11 = 0;
  v42 = 0;
  *a3 = 0;
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
  if ( (int)SyncPolicy < 0 )
  {
    v6 = 0;
LABEL_26:
    v4->IoStatus.Status = SyncPolicy;
    v12 = 4;
    v4->IoStatus.Information = 0;
    goto LABEL_19;
  }
  v12 = 1;
  if ( v6 && (v6 = *(_QWORD *)(v6 + 16)) != 0 && (v27 = *(_QWORD *)(v6 + 16)) != 0 )
    v13 = *(_QWORD *)(v27 + 32);
  else
    v13 = 0;
  IsPlaceholder = HsmpIsPlaceholder(v6);
  v39 = IsPlaceholder;
  if ( !v51 && !IsPlaceholder )
    goto LABEL_20;
  if ( IsPlaceholder )
  {
    SyncPolicy = (unsigned int)HsmpCldGetSyncPolicy(v40, v6, (_DWORD)v41, 0, (__int64)&v42);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( (int)SyncPolicy < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_qqqd(
          WPP_GLOBAL_Control->AttachedDevice,
          24,
          WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
          v40,
          v6,
          v13,
          SyncPolicy);
      }
      goto LABEL_26;
    }
    v11 = v42;
  }
  if ( v51 )
  {
    v15 = v13
        ? HsmpOpenFileByIdEx(
            (const UNICODE_STRING *)v40,
            *(struct _FLT_INSTANCE **)(v40 + 32),
            v13,
            0x81u,
            v37,
            0x200000,
            0,
            &FileHandle,
            (PFILE_OBJECT *)&Object)
        : HsmpRelativeStreamOpen(v40, v41, 0, 0x81u, 1u, 0x200000, v38, &FileHandle, (PFILE_OBJECT *)&Object);
    LODWORD(SyncPolicy) = v15;
    HsmDbgBreakOnStatus(v15);
    if ( (int)SyncPolicy < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_26;
      }
      v26 = 25;
LABEL_64:
      WPP_SF_qiqiid(
        v25->AttachedDevice,
        v26,
        WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
        v4,
        v40,
        v41,
        v13,
        v6,
        SyncPolicy);
      goto LABEL_26;
    }
  }
  Pool2 = ExAllocatePool2(256, 48, 1668248392);
  v10 = Pool2;
  if ( !Pool2 )
  {
    LODWORD(SyncPolicy) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_26;
    }
    v22 = 26;
LABEL_44:
    WPP_SF_qqiqd(
      v21->AttachedDevice,
      v22,
      WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids,
      v4,
      v40,
      v41,
      v13,
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
    SyncPolicy = (unsigned int)HsmiQueryFullFilePath(*(_QWORD *)(v40 + 32), v17, v41, 257, v10 + 24);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( (int)SyncPolicy < 0 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_26;
      }
      v22 = 27;
      goto LABEL_44;
    }
  }
  RequestorProcess = FltGetRequestorProcess(v4);
  if ( (unsigned __int8)HsmOsIsSyncProviderProcess(RequestorProcess) || !v47 || v46 == v47 )
  {
LABEL_16:
    if ( !v39
      || (v11 & 0x400) != 0 && (v34 = FltGetRequestorProcess(v4), (unsigned __int8)HsmOsIsSyncProviderProcess(v34)) )
    {
      v19 = 0;
      if ( !v51 && !(unsigned __int8)HsmpCldIsCallbackRequested(5, v6, v4) )
        goto LABEL_19;
    }
    else
    {
      HsmpPersistInSync(v6, v41);
      v19 = 1;
    }
    *(_BYTE *)(v10 + 44) = 0;
    *(_QWORD *)(v10 + 16) = *(_QWORD *)(a1 + 16);
    *(_QWORD *)(a1 + 16) = 0;
    if ( !v51 || !ByteOffset.QuadPart )
      LOBYTE(v12) = 0;
    *(_DWORD *)(v10 + 40) = v45;
    *(_BYTE *)(v10 + 45) = v12;
    v12 = 0;
    *(_BYTE *)(v10 + 46) = v19;
    *a3 = v10;
    v10 = 0;
LABEL_19:
    if ( !v10 )
      goto LABEL_20;
    goto LABEL_80;
  }
  if ( v51 )
  {
    SyncPolicy = (unsigned int)HsmpRecurseDirectory(
                                 v40,
                                 FileHandle,
                                 (struct _FILE_OBJECT *)Object,
                                 v39 != 0 ? 1040 : 16,
                                 1,
                                 0,
                                 (__int64 (__fastcall *)(__int64, struct _FILE_OBJECT *, _QWORD, __int64))&HsmiInfoPopulatePlaceholderOnRename,
                                 (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))&HsmiInfoHydratePlaceholderOnRename,
                                 (__int64)v4);
    HsmDbgBreakOnStatus(SyncPolicy);
    if ( (int)SyncPolicy < 0 )
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_26;
      }
      v26 = 30;
      goto LABEL_64;
    }
    goto LABEL_16;
  }
  SyncPolicy = (unsigned int)HsmpAcquireUserRequestRundownProtection((PFLT_CONTEXT)v6, v4);
  HsmDbgBreakOnStatus(SyncPolicy);
  if ( (int)SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      StreamSize = HsmpGetStreamSize(v6);
      WPP_SF_qqLiiqd(*(_QWORD *)(v24 + 24), 28, v24, v40, v6, *(_DWORD *)(v6 + 28), StreamSize, v13, v4, SyncPolicy);
    }
    goto LABEL_26;
  }
  *(_BYTE *)(v10 + 44) = 1;
  *(_QWORD *)(v10 + 16) = *(_QWORD *)(a1 + 16);
  v28 = v4->Iopb;
  *(_QWORD *)(a1 + 16) = 0;
  v29 = HsmpRecallInitiateHydrationEx(
          v48[0],
          v6,
          (int)v28->TargetFileObject,
          65543,
          v4,
          0,
          -1,
          0,
          (unsigned __int64)&HsmiInfoRecallForRenameCompletion & -(__int64)(v53 != 0));
  LODWORD(SyncPolicy) = v4->IoStatus.Status;
  v30 = v29;
  HsmDbgBreakOnStatus((unsigned int)SyncPolicy);
  if ( (int)SyncPolicy < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v31 = HsmpGetStreamSize(v6);
      WPP_SF_qqLiiqiid(
        *(_QWORD *)(v32 + 24),
        v32,
        v33,
        v40,
        v6,
        *(_DWORD *)(v6 + 28),
        v31,
        v13,
        v4,
        v47,
        v46,
        SyncPolicy);
    }
    goto LABEL_26;
  }
  v12 = v30;
  if ( !v30 )
  {
    *a3 = v10;
    v10 = 0;
    goto LABEL_19;
  }
LABEL_80:
  v35 = *(void **)(v10 + 16);
  if ( v35 )
    HsmpReleaseFileNameLock(v35);
  if ( *(_BYTE *)(v10 + 44) )
    HsmpReleaseUserRequestRundownProtection(*(PFLT_CONTEXT *)(v10 + 8));
  v36 = *(void **)(v10 + 32);
  if ( v36 )
    ExFreePoolWithTag(v36, 0x73557348u);
  if ( *(_QWORD *)(v10 + 8) )
    FltReleaseContext((PFLT_CONTEXT)v6);
  ExFreePoolWithTag((PVOID)v10, 0x636F7348u);
LABEL_20:
  if ( Object )
    ObfDereferenceObject(Object);
  if ( FileHandle )
    FltClose(FileHandle);
  return v12;
}

```

## disassembly

```asm
0x140054a9c  mov     [rsp-8+arg_10], r8
0x140054aa1  mov     [rsp-8+arg_0], rcx
0x140054aa6  push    rbp
0x140054aa7  push    rbx
0x140054aa8  push    rsi
0x140054aa9  push    rdi
0x140054aaa  push    r12
0x140054aac  push    r13
0x140054aae  push    r14
0x140054ab0  push    r15
0x140054ab2  lea     rbp, [rsp-1Fh]
0x140054ab7  sub     rsp, 0C8h
0x140054abe  mov     rax, [rcx+28h]
0x140054ac2  mov     r14d, edx
0x140054ac5  mov     r13, [rcx+18h]
0x140054ac9  mov     r9, [rcx+20h]
0x140054acd  mov     rsi, [rcx+8]
0x140054ad1  mov     dl, [rcx+35h]
0x140054ad4  mov     [rbp+57h+var_68], rax
0x140054ad8  mov     rax, [rcx]
0x140054adb  mov     qword ptr [rbp+57h+var_98], rax
0x140054adf  mov     eax, [rcx+30h]
0x140054ae2  mov     [rbp+57h+var_70], eax
0x140054ae5  mov     al, [rcx+34h]
0x140054ae8  mov     [rbp+57h+arg_8], al
0x140054aeb  mov     rax, [r13+10h]
0x140054aef  mov     [rbp+57h+var_60], r9
0x140054af3  mov     qword ptr [rbp+57h+var_58], rsi
0x140054af7  mov     [rbp+57h+arg_18], dl
0x140054afa  mov     rcx, [rax+8]
0x140054afe  mov     rax, [rax+28h]
0x140054b02  mov     [rbp+57h+var_50], rax
0x140054b06  xor     eax, eax
0x140054b08  mov     qword ptr [rbp+57h+var_90], rcx
0x140054b0c  mov     edi, eax
0x140054b0e  mov     ecx, r14d
0x140054b11  mov     [rbp+57h+FileHandle], rax
0x140054b15  mov     [rbp+57h+Object], rax
0x140054b19  mov     ebx, eax
0x140054b1b  mov     [rbp+57h+var_88], eax
0x140054b1e  mov     [r8], rax
0x140054b21  call    HsmDbgBreakOnStatus
0x140054b26  test    r14d, r14d
0x140054b29  js      loc_140054C9A
0x140054b2f  lea     r15d, [rdi+1]
0x140054b33  test    rsi, rsi
0x140054b36  jnz     loc_140054EFF
0x140054b3c  xor     r12d, r12d
0x140054b3f  mov     rcx, rsi
0x140054b42  call    HsmpIsPlaceholder
0x140054b47  mov     [rbp+57h+var_A0], al
0x140054b4a  cmp     [rbp+57h+arg_8], bl
0x140054b4d  jnz     short loc_140054B57
0x140054b4f  test    al, al
0x140054b51  jz      loc_140054C68
0x140054b57  test    al, al
0x140054b59  jnz     loc_140054F23
0x140054b5f  cmp     [rbp+57h+arg_8], dil
0x140054b63  jz      short loc_140054BB6
0x140054b65  lea     rax, [rbp+57h+Object]
0x140054b69  mov     r9d, 81h; int
0x140054b6f  mov     [rsp+100h+var_C0], rax; __int64
0x140054b74  lea     rax, [rbp+57h+FileHandle]
0x140054b78  mov     [rsp+100h+var_C8], rax; __int64
0x140054b7d  test    r12, r12
0x140054b80  jnz     loc_140054E35
0x140054b86  mov     rdx, qword ptr [rbp+57h+var_90]; int
0x140054b8a  xor     r8d, r8d; int
0x140054b8d  mov     rcx, qword ptr [rbp+57h+var_98]; int
0x140054b91  mov     dword ptr [rsp+100h+var_D8], 200000h; int
0x140054b99  mov     [rsp+100h+var_E0], r15d; ULONG
0x140054b9e  call    HsmpRelativeStreamOpen
0x140054ba3  mov     ecx, eax
0x140054ba5  mov     r14d, eax
0x140054ba8  call    HsmDbgBreakOnStatus
0x140054bad  test    r14d, r14d
0x140054bb0  js      loc_140054EBE
0x140054bb6  mov     edx, 30h ; '0'
0x140054bbb  mov     ecx, 100h
0x140054bc0  mov     r8d, 636F7348h
0x140054bc6  call    cs:__imp_ExAllocatePool2
0x140054bcd  nop     dword ptr [rax+rax+00h]
0x140054bd2  mov     rdi, rax
0x140054bd5  test    rax, rax
0x140054bd8  jz      loc_140054CB0
0x140054bde  mov     dword ptr [rax], 636F7348h
0x140054be4  test    rsi, rsi
0x140054be7  jnz     loc_140054FF2
0x140054bed  xor     r9d, r9d
0x140054bf0  mov     r8, r13
0x140054bf3  mov     rdx, rsi
0x140054bf6  lea     ecx, [r9+5]
0x140054bfa  call    HsmpCldIsCallbackRequested
0x140054bff  test    al, al
0x140054c01  jnz     loc_140054D9A
0x140054c07  mov     rcx, r13; CallbackData
0x140054c0a  call    cs:__imp_FltGetRequestorProcess
0x140054c11  nop     dword ptr [rax+rax+00h]
0x140054c16  mov     rcx, rax
0x140054c19  call    HsmOsIsSyncProviderProcess
0x140054c1e  test    al, al
0x140054c20  jz      loc_140054CEB
0x140054c26  xor     r12d, r12d
0x140054c29  cmp     [rbp+57h+var_A0], r12b
0x140054c2d  jnz     loc_14005519C
0x140054c33  mov     bl, r12b
0x140054c36  cmp     [rbp+57h+arg_8], r12b
0x140054c3a  jnz     loc_140054E82
0x140054c40  xor     r9d, r9d
0x140054c43  mov     r8, r13
0x140054c46  mov     rdx, rsi
0x140054c49  lea     ecx, [r9+5]
0x140054c4d  call    HsmpCldIsCallbackRequested
0x140054c52  test    al, al
0x140054c54  jnz     loc_140054E82
0x140054c5a  test    r14d, r14d
0x140054c5d  js      short loc_140054C9C
0x140054c5f  test    rdi, rdi
0x140054c62  jnz     loc_1400551D5
0x140054c68  mov     rax, [rbp+57h+Object]
0x140054c6c  test    rax, rax
0x140054c6f  jnz     loc_140054E6E
0x140054c75  mov     rax, [rbp+57h+FileHandle]
0x140054c79  test    rax, rax
0x140054c7c  jnz     loc_140054E5A
0x140054c82  mov     eax, r15d
0x140054c85  add     rsp, 0C8h
0x140054c8c  pop     r15
0x140054c8e  pop     r14
0x140054c90  pop     r13
0x140054c92  pop     r12
0x140054c94  pop     rdi
0x140054c95  pop     rsi
0x140054c96  pop     rbx
0x140054c97  pop     rbp
0x140054c98  retn
0x140054c9a  xor     esi, esi
0x140054c9c  mov     [r13+18h], r14d
0x140054ca0  mov     r15d, 4
0x140054ca6  mov     qword ptr [r13+20h], 0
0x140054cae  jmp     short loc_140054C5F
0x140054cb0  mov     r14d, 0C000009Ah
0x140054cb6  mov     ecx, r14d
0x140054cb9  call    HsmDbgBreakOnStatus
0x140054cbe  mov     r10, cs:WPP_GLOBAL_Control
0x140054cc5  lea     rcx, WPP_GLOBAL_Control
0x140054ccc  cmp     r10, rcx
0x140054ccf  jz      short loc_140054C9C
0x140054cd1  mov     eax, [r10+2Ch]
0x140054cd5  test    r15b, al
0x140054cd8  jz      short loc_140054C9C
0x140054cda  cmp     byte ptr [r10+29h], 2
0x140054cdf  jb      short loc_140054C9C
0x140054ce1  mov     edx, 1Ah
0x140054ce6  jmp     loc_140054E01
0x140054ceb  mov     rax, [rbp+57h+var_60]
0x140054cef  test    rax, rax
0x140054cf2  jz      loc_140054C26
0x140054cf8  cmp     [rbp+57h+var_68], rax
0x140054cfc  jz      loc_140054C26
0x140054d02  cmp     [rbp+57h+arg_8], 0
0x140054d06  jnz     loc_14005510A
0x140054d0c  mov     rdx, r13; CallbackData
0x140054d0f  mov     rcx, rsi; Context
0x140054d12  call    HsmpAcquireUserRequestRundownProtection
0x140054d17  mov     ecx, eax
0x140054d19  mov     r14d, eax
0x140054d1c  call    HsmDbgBreakOnStatus
0x140054d21  xor     edx, edx
0x140054d23  test    r14d, r14d
0x140054d26  jns     loc_14005500A
0x140054d2c  mov     r8, cs:WPP_GLOBAL_Control
0x140054d33  lea     rcx, WPP_GLOBAL_Control
0x140054d3a  cmp     r8, rcx
0x140054d3d  jz      loc_140054C9C
0x140054d43  mov     eax, [r8+2Ch]
0x140054d47  test    r15b, al
0x140054d4a  jz      loc_140054C9C
0x140054d50  cmp     byte ptr [r8+29h], 2
0x140054d55  jb      loc_140054C9C
0x140054d5b  mov     rcx, rsi
0x140054d5e  call    HsmpGetStreamSize
0x140054d63  mov     r9, qword ptr [rbp+57h+var_98]
0x140054d67  mov     edx, 1Ch
0x140054d6c  mov     rcx, [r8+18h]
0x140054d70  mov     dword ptr [rsp+100h+var_B8], r14d
0x140054d75  mov     [rsp+100h+var_C0], r13
0x140054d7a  mov     [rsp+100h+var_C8], r12
0x140054d7f  mov     [rsp+100h+var_D0], rax
0x140054d84  mov     eax, [rsi+1Ch]
0x140054d87  mov     dword ptr [rsp+100h+var_D8], eax
0x140054d8b  mov     qword ptr [rsp+100h+var_E0], rsi
0x140054d90  call    WPP_SF_qqLiiqd
0x140054d95  jmp     loc_140054C9C
0x140054d9a  mov     r8, qword ptr [rbp+57h+var_90]
0x140054d9e  lea     rax, [rdi+18h]
0x140054da2  mov     qword ptr [rsp+100h+var_E0], rax
0x140054da7  mov     r9d, 101h
0x140054dad  mov     rax, qword ptr [rbp+57h+var_98]
0x140054db1  mov     rcx, [rax+20h]
0x140054db5  call    HsmiQueryFullFilePath
0x140054dba  mov     ecx, eax
0x140054dbc  mov     r14d, eax
0x140054dbf  call    HsmDbgBreakOnStatus
0x140054dc4  test    r14d, r14d
0x140054dc7  jns     loc_140054C07
0x140054dcd  mov     r10, cs:WPP_GLOBAL_Control
0x140054dd4  lea     rcx, WPP_GLOBAL_Control
0x140054ddb  cmp     r10, rcx
0x140054dde  jz      loc_140054C9C
0x140054de4  mov     eax, [r10+2Ch]
0x140054de8  test    r15b, al
0x140054deb  jz      loc_140054C9C
0x140054df1  cmp     byte ptr [r10+29h], 2
0x140054df6  jb      loc_140054C9C
0x140054dfc  mov     edx, 1Bh
0x140054e01  mov     rax, qword ptr [rbp+57h+var_90]
0x140054e05  lea     r8, WPP_e26ac64b2c40307be864d687cc32cd5d_Traceguids
0x140054e0c  mov     rcx, [r10+18h]
0x140054e10  mov     r9, r13
0x140054e13  mov     dword ptr [rsp+100h+var_C8], r14d
0x140054e18  mov     [rsp+100h+var_D0], r12
0x140054e1d  mov     [rsp+100h+var_D8], rax
0x140054e22  mov     rax, qword ptr [rbp+57h+var_98]
0x140054e26  mov     qword ptr [rsp+100h+var_E0], rax
0x140054e2b  call    WPP_SF_qqiqd
0x140054e30  jmp     loc_140054C9C
0x140054e35  mov     rax, qword ptr [rbp+57h+var_98]
0x140054e39  mov     r8, r12
0x140054e3c  mov     byte ptr [rsp+100h+var_D0], dil
0x140054e41  mov     rcx, rax
0x140054e44  mov     dword ptr [rsp+100h+var_D8], 200000h
0x140054e4c  mov     rdx, [rax+20h]
0x140054e50  call    HsmpOpenFileByIdEx
0x140054e55  jmp     loc_140054BA3
0x140054e5a  mov     rcx, rax; FileHandle
0x140054e5d  call    cs:__imp_FltClose
0x140054e64  nop     dword ptr [rax+rax+00h]
0x140054e69  jmp     loc_140054C82
0x140054e6e  mov     rcx, rax; Object
0x140054e71  call    cs:__imp_ObfDereferenceObject
0x140054e78  nop     dword ptr [rax+rax+00h]
0x140054e7d  jmp     loc_140054C75
0x140054e82  mov     rcx, [rbp+57h+arg_0]
0x140054e86  mov     [rdi+2Ch], r12b
0x140054e8a  mov     rax, [rcx+10h]
0x140054e8e  mov     [rdi+10h], rax
0x140054e92  mov     [rcx+10h], r12
0x140054e96  cmp     [rbp+57h+arg_8], r12b
0x140054e9a  jnz     short loc_140054EF7
0x140054e9c  mov     r15b, r12b
0x140054e9f  mov     eax, [rbp+57h+var_70]
0x140054ea2  mov     [rdi+28h], eax
0x140054ea5  mov     rax, [rbp+57h+arg_10]
0x140054ea9  mov     [rdi+2Dh], r15b
0x140054ead  mov     r15d, r12d
0x140054eb0  mov     [rdi+2Eh], bl
0x140054eb3  mov     [rax], rdi
0x140054eb6  mov     rdi, r12
0x140054eb9  jmp     loc_140054C5A
0x140054ebe  mov     r10, cs:WPP_GLOBAL_Control
0x140054ec5  lea     rcx, WPP_GLOBAL_Control
0x140054ecc  cmp     r10, rcx
0x140054ecf  jz      loc_140054C9C
0x140054ed5  mov     eax, [r10+2Ch]
0x140054ed9  test    r15b, al
0x140054edc  jz      loc_140054C9C
0x140054ee2  cmp     byte ptr [r10+29h], 2
0x140054ee7  jb      loc_140054C9C
0x140054eed  mov     edx, 19h
0x140054ef2  jmp     loc_140054FB9
0x140054ef7  cmp     [rbp+57h+var_50], r12
0x140054efb  jnz     short loc_140054E9F
0x140054efd  jmp     short loc_140054E9C
0x140054eff  mov     rsi, [rsi+10h]
0x140054f03  test    rsi, rsi
0x140054f06  jz      loc_140054B3C
0x140054f0c  mov     r12, [rsi+10h]
0x140054f10  test    r12, r12
0x140054f13  jz      loc_140054B3C
0x140054f19  mov     r12, [r12+20h]
0x140054f1e  jmp     loc_140054B3F
0x140054f23  mov     rbx, qword ptr [rbp+57h+var_98]
0x140054f27  lea     rax, [rbp+57h+var_88]
0x140054f2b  mov     r8, qword ptr [rbp+57h+var_90]
0x140054f2f  mov     rcx, rbx
0x140054f32  xor     r9d, r9d
0x140054f35  mov     qword ptr [rsp+100h+var_E0], rax
0x140054f3a  mov     rdx, rsi
0x140054f3d  call    HsmpCldGetSyncPolicy
0x140054f42  mov     ecx, eax
0x140054f44  mov     r14d, eax
0x140054f47  call    HsmDbgBreakOnStatus
0x140054f4c  test    r14d, r14d
0x140054f4f  jns     short loc_140054FAC
0x140054f51  mov     r10, cs:WPP_GLOBAL_Control
0x140054f58  lea     rcx, WPP_GLOBAL_Control
0x140054f5f  cmp     r10, rcx
0x140054f62  jz      loc_140054C9C
0x140054f68  mov     edx, [r10+2Ch]
  ... truncated ...
```
