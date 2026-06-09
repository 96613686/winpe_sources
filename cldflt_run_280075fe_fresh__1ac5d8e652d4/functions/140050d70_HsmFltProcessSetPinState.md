# HsmFltProcessSetPinState

- ea: `0x140050d70`
- end: `0x1400516e8`
- name: `HsmFltProcessSetPinState`
- size: `2424`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004ded0`

## callees

- `0x140003c50`
- `0x140006da0`
- `0x1400090b4`
- `0x140009300`
- `0x14000abb8`
- `0x14000ac28`
- `0x14000c12c`
- `0x14001e280`
- `0x140050ca0`
- `0x140050d70`
- `0x140051980`
- `0x14005f550`
- `0x1400779f4`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400514a9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400514a9`
- `ntoskrnl!ZwClose` at `0x140051689`
- `ntoskrnl!ZwClose` at `0x140051689`
- `ntoskrnl!IoFileObjectType` at `0x14005148d`
- `ntoskrnl!ObfDereferenceObject` at `0x14005169a`
- `ntoskrnl!ObfDereferenceObject` at `0x14005169a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400516c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400516d7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400516c1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400516d7`
- `ntoskrnl!ExAllocatePool2` at `0x140051195`
- `ntoskrnl!ExAllocatePool2` at `0x140051195`
- `FLTMGR!FltCreateFileEx` at `0x1400512fa`
- `FLTMGR!FltCreateFileEx` at `0x1400512fa`
- `FLTMGR!FltClose` at `0x1400516ab`
- `FLTMGR!FltClose` at `0x1400516ab`
- `FLTMGR!FltQueryInformationFile` at `0x140050e03`
- `FLTMGR!FltQueryInformationFile` at `0x140051367`
- `FLTMGR!FltQueryInformationFile` at `0x140050e03`
- `FLTMGR!FltQueryInformationFile` at `0x140051367`
- `FLTMGR!FltGetRequestorProcess` at `0x140050e4f`
- `FLTMGR!FltGetRequestorProcess` at `0x140050f6f`
- `FLTMGR!FltGetRequestorProcess` at `0x140050e4f`
- `FLTMGR!FltGetRequestorProcess` at `0x140050f6f`

## pseudocode

```c
__int64 __fastcall HsmFltProcessSetPinState(
        __int64 a1,
        __int64 a2,
        struct _FILE_OBJECT *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        PFLT_CALLBACK_DATA CallbackData,
        void *Handle,
        unsigned int a10,
        int a11,
        void *FileHandle)
{
  struct _FILE_OBJECT *v13; // rbx
  int v14; // r15d
  struct _FLT_INSTANCE *v15; // rcx
  __int64 v16; // rdi
  struct _FLT_CALLBACK_DATA *v17; // r13
  int v18; // edi
  PEPROCESS v19; // rax
  __int64 v20; // rdx
  unsigned int v21; // r12d
  __int64 v22; // r8
  int v23; // r12d
  struct _FILE_OBJECT *v24; // rbx
  PFLT_CALLBACK_DATA v26; // r9
  __int64 v27; // rdx
  struct _DEVICE_OBJECT *AttachedDevice; // rcx
  unsigned int RequestorProcess; // eax
  __int64 v30; // r12
  int v31; // ebx
  int v32; // eax
  int v33; // eax
  __int64 v34; // rcx
  PDEVICE_OBJECT v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rbx
  USHORT v38; // cx
  struct _FLT_INSTANCE *v39; // rdx
  int v40; // edx
  unsigned int v41; // ecx
  PDEVICE_OBJECT v42; // rcx
  int v43; // ecx
  int v44; // r15d
  USHORT pusResult[8]; // [rsp+88h] [rbp-80h] BYREF
  void *Src[2]; // [rsp+98h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v48; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v49; // [rsp+C8h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-38h] BYREF
  __int64 FileInformation; // [rsp+158h] [rbp+50h] BYREF
  PFILE_OBJECT FileObject; // [rsp+160h] [rbp+58h] BYREF
  PVOID Object; // [rsp+168h] [rbp+60h]
  ULONG LengthReturned; // [rsp+170h] [rbp+68h] BYREF
  int v55; // [rsp+174h] [rbp+6Ch]

  v55 = HIDWORD(a4);
  Object = a3;
  FileInformation = 0;
  LengthReturned = 0;
  v13 = a3;
  v49 = 0;
  v14 = *((_DWORD *)Handle + 2);
  v15 = *(struct _FLT_INSTANCE **)(a2 + 32);
  a11 = *((_DWORD *)Handle + 4);
  *(_OWORD *)Src = 0;
  Handle = 0;
  *(_OWORD *)pusResult = 0;
  FileHandle = 0;
  FileObject = 0;
  v48 = 0;
  LODWORD(v16) = FltQueryInformationFile(v15, a3, &FileInformation, 8u, FileAttributeTagInformation, &LengthReturned);
  HsmDbgBreakOnStatus((unsigned int)v16);
  if ( (int)v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v26 = CallbackData;
      v27 = 223;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
LABEL_106:
      WPP_SF_qqiqd(AttachedDevice, v27, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, v26, a2, a5, a7, v16);
      goto LABEL_10;
    }
    goto LABEL_10;
  }
  v17 = CallbackData;
  if ( (FileInformation & 0x80000) != 0 && (FileInformation & 0x100000) != 0 || (v18 = a11, a11 == 3) )
  {
    LOBYTE(a10) = 0;
    if ( CallbackData )
      RequestorProcess = (unsigned int)FltGetRequestorProcess(CallbackData);
    else
      RequestorProcess = 0;
    v30 = a5;
    v31 = HsmpCldCheckSyncProviderAccess(a2, a5, (_DWORD)v13, RequestorProcess, (__int64)&a10);
    HsmDbgBreakOnStatus((unsigned int)v31);
    LODWORD(v16) = -1073688808;
    if ( v31 >= 0 )
    {
      if ( (_BYTE)a10 )
      {
        v13 = (struct _FILE_OBJECT *)Object;
        v18 = a11;
        goto LABEL_4;
      }
      HsmDbgBreakOnStatus(3221278488LL);
    }
    HsmDbgBreakOnStatus(3221278488LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqiqd(
        WPP_GLOBAL_Control->AttachedDevice,
        224,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        v17,
        a2,
        v30,
        a7,
        -1073688808);
    }
    goto LABEL_10;
  }
LABEL_4:
  if ( v17 )
    v19 = FltGetRequestorProcess(v17);
  else
    v19 = 0;
  v21 = (unsigned __int8)HsmOsIsSyncProviderProcess(v19) != 0 ? 0x80000000 : 0;
  if ( v18 != 4 )
  {
    v22 = FileInformation;
    v23 = v18 | v21;
    v24 = (struct _FILE_OBJECT *)Object;
    goto LABEL_8;
  }
  v34 = *(_QWORD *)(a2 + 32);
  a10 = FileInformation;
  a6 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  LODWORD(v16) = HsmiQueryFullFilePath(v34, v20, v13, 0x101u, Src);
  HsmDbgBreakOnStatus((unsigned int)v16);
  if ( (int)v16 < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_10;
    }
    v36 = 225;
    goto LABEL_48;
  }
  pusResult[1] = *(_WORD *)(a2 + 64);
  LODWORD(v16) = RtlUShortAdd(pusResult[1], (USHORT)Src[0], &pusResult[1]);
  if ( (int)v16 < 0 )
  {
    v35 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_10;
    }
    v36 = 226;
LABEL_48:
    WPP_SF_qqd(v35->AttachedDevice, v36, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a2, v13, v16);
    goto LABEL_10;
  }
  pusResult[0] = 0;
  *(_QWORD *)&pusResult[4] = ExAllocatePool2(256, pusResult[1], 1934979912);
  v37 = *(_QWORD *)&pusResult[4];
  LODWORD(v16) = *(_QWORD *)&pusResult[4] == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus((unsigned int)v16);
  if ( !v37 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 227, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a2, v16);
    }
    goto LABEL_10;
  }
  memmove(*(void **)&pusResult[4], *(const void **)(a2 + 72), *(unsigned __int16 *)(a2 + 64));
  pusResult[0] = *(_WORD *)(a2 + 64) - 2;
  memmove((void *)(*(_QWORD *)&pusResult[4] + pusResult[0]), Src[1], LOWORD(Src[0]));
  v38 = LOWORD(Src[0]) + pusResult[0];
  for ( pusResult[0] = v38; v38 >= 2u; pusResult[0] = v38 )
  {
    if ( *(_WORD *)(*(_QWORD *)&pusResult[4] + 2 * ((unsigned __int64)v38 >> 1) - 2) == 92 )
      break;
    v38 -= 2;
  }
  v39 = *(struct _FLT_INSTANCE **)(a2 + 32);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)pusResult;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  LODWORD(v16) = FltCreateFileEx(
                   Filter,
                   v39,
                   &FileHandle,
                   &FileObject,
                   0x100080u,
                   &ObjectAttributes,
                   &IoStatusBlock,
                   0,
                   0,
                   7u,
                   1u,
                   0,
                   0,
                   0,
                   0x800u);
  HsmDbgBreakOnStatus((unsigned int)v16);
  if ( (int)v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(
        WPP_GLOBAL_Control->AttachedDevice,
        228,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        *(_QWORD *)(a2 + 32),
        a2,
        v16);
    }
    goto LABEL_10;
  }
  v16 = (unsigned int)FltQueryInformationFile(
                        *(PFLT_INSTANCE *)(a2 + 32),
                        FileObject,
                        &a6,
                        8u,
                        FileAttributeTagInformation,
                        &LengthReturned);
  HsmDbgBreakOnStatus(v16);
  if ( (int)v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqqd(
        WPP_GLOBAL_Control->AttachedDevice,
        229,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        v17,
        a2,
        a7,
        v16);
    }
    goto LABEL_10;
  }
  v22 = FileInformation;
  v40 = a6 & 0x180000;
  if ( (a6 & 0x180000) == 0x180000 )
  {
    v32 = 0x100000;
LABEL_35:
    v33 = v32 != 0 ? 3 : 1;
    goto LABEL_36;
  }
  v41 = a10 & 0xFFE7FFFF;
  if ( (a10 & 0x180000) != 0x180000 )
    v41 = a10;
  if ( (v41 & 0x180000) == 0 && ((FileInformation & 0x10) != 0 || v40 != 0x100000) )
    v41 |= v40;
  v32 = v41 & 0x100000;
  if ( (v41 & 0x80000) != 0 )
    goto LABEL_35;
  v33 = v32 != 0 ? 2 : 0;
LABEL_36:
  v24 = (struct _FILE_OBJECT *)Object;
  v23 = v33 | v21;
  if ( (v14 & 2) != 0 )
  {
    *(_QWORD *)&v48 = Object;
  }
  else
  {
    *(_QWORD *)&v48 = 0;
    BYTE8(v48) = 0;
    if ( (FileInformation & 0x180000) != 0 )
      goto LABEL_82;
  }
  BYTE8(v48) = 1;
LABEL_82:
  HIDWORD(v48) = v23;
  LODWORD(v49) = 0;
  if ( (v14 & 2) != 0 )
    LOBYTE(v14) = v14 & 0xFC | 1;
LABEL_8:
  if ( (v22 & 0x10) != 0 && (v14 & 3) != 0 )
  {
    LODWORD(v16) = ObOpenObjectByPointer(v24, 0x200u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Handle);
    HsmDbgBreakOnStatus((unsigned int)v16);
    if ( (int)v16 >= 0 )
    {
      v43 = v14 & 2;
      v44 = v14 & 4;
      if ( a11 == 4 )
      {
        LODWORD(v16) = HsmpRecurseDirectory(
                         a2,
                         Handle,
                         v24,
                         FileInformation,
                         v44 != 0,
                         v43 != 0,
                         (__int64 (__fastcall *)(__int64, struct _FILE_OBJECT *, _QWORD, __int64))HsmiOpInheritPinStatePre,
                         (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))HsmiInfoUpdatePlaceholderStatesOnRenamePost,
                         (__int64)&v48);
        HsmDbgBreakOnStatus((unsigned int)v16);
        if ( (int)v16 < 0 )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v27 = 231;
            goto LABEL_105;
          }
        }
      }
      else
      {
        LODWORD(v16) = HsmpRecurseDirectory(
                         a2,
                         Handle,
                         v24,
                         FileInformation,
                         v44 != 0,
                         v43 != 0,
                         0,
                         HsmiOpSetPinStateInternal,
                         v23);
        HsmDbgBreakOnStatus((unsigned int)v16);
        if ( (int)v16 < 0 )
        {
          v42 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v27 = 232;
            goto LABEL_105;
          }
        }
      }
    }
    else
    {
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v27 = 230;
LABEL_105:
        AttachedDevice = v42->AttachedDevice;
        v26 = v17;
        goto LABEL_106;
      }
    }
  }
  else
  {
    LODWORD(v16) = HsmiOpSetPinStateInternal(a2, v24, v22, v23);
    HsmDbgBreakOnStatus((unsigned int)v16);
    if ( (int)v16 < 0 )
    {
      v42 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v27 = 233;
        goto LABEL_105;
      }
    }
  }
LABEL_10:
  if ( Handle )
    ZwClose(Handle);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  if ( Src[1] )
    ExFreePoolWithTag(Src[1], 0x73557348u);
  if ( *(_QWORD *)&pusResult[4] )
    ExFreePoolWithTag(*(PVOID *)&pusResult[4], 0x73557348u);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x140050d70  mov     rax, rsp
0x140050d73  mov     [rax+20h], r9
0x140050d77  mov     [rax+18h], r8
0x140050d7b  mov     [rax+8], rcx
0x140050d7f  push    rbp
0x140050d80  push    rbx
0x140050d81  push    rsi
0x140050d82  push    rdi
0x140050d83  push    r12
0x140050d85  push    r13
0x140050d87  push    r14
0x140050d89  push    r15
0x140050d8b  lea     rbp, [rax-48h]
0x140050d8f  sub     rsp, 108h
0x140050d96  mov     rax, [rbp+40h+Handle]
0x140050d9d  xor     esi, esi
0x140050d9f  mov     r14, rdx
0x140050da2  mov     [rbp+40h+FileInformation], rsi
0x140050da6  xor     ecx, ecx
0x140050da8  mov     [rbp+40h+arg_18], esi
0x140050dab  mov     rbx, r8
0x140050dae  mov     [rbp+40h+var_80], rcx
0x140050db2  mov     edx, [rax+10h]
0x140050db5  lea     r9d, [rsi+8]; Length
0x140050db9  mov     r15d, [rax+8]
0x140050dbd  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140050dc1  mov     rcx, [r14+20h]; Instance
0x140050dc5  lea     rax, [rbp+40h+arg_18]
0x140050dc9  xorps   xmm0, xmm0
0x140050dcc  mov     [rbp+40h+arg_50], edx
0x140050dd2  xorps   xmm1, xmm1
0x140050dd5  mov     [rsp+140h+LengthReturned], rax; LengthReturned
0x140050dda  mov     rdx, rbx; FileObject
0x140050ddd  mov     [rsp+140h+FileInformationClass], 23h ; '#'; FileInformationClass
0x140050de5  movups  xmmword ptr [rbp+40h+Src], xmm0
0x140050de9  mov     [rbp+40h+Handle], rsi
0x140050df0  movups  xmmword ptr [rbp+40h+pusResult], xmm1
0x140050df4  mov     [rbp+40h+FileHandle], rsi
0x140050dfb  mov     [rbp+40h+FileObject], rsi
0x140050dff  movups  [rbp+40h+var_90], xmm0
0x140050e03  call    cs:__imp_FltQueryInformationFile
0x140050e0a  nop     dword ptr [rax+rax+00h]
0x140050e0f  mov     ecx, eax
0x140050e11  mov     edi, eax
0x140050e13  call    HsmDbgBreakOnStatus
0x140050e18  test    edi, edi
0x140050e1a  js      loc_140050F0F
0x140050e20  test    dword ptr [rbp+40h+FileInformation], 80000h
0x140050e27  mov     r13, [rbp+40h+CallbackData]
0x140050e2e  jnz     loc_140050F4F
0x140050e34  mov     edi, [rbp+40h+arg_50]
0x140050e3a  cmp     edi, 3
0x140050e3d  jz      loc_140050F5C
0x140050e43  test    r13, r13
0x140050e46  jz      loc_140051074
0x140050e4c  mov     rcx, r13; CallbackData
0x140050e4f  call    cs:__imp_FltGetRequestorProcess
0x140050e56  nop     dword ptr [rax+rax+00h]
0x140050e5b  mov     rcx, rax
0x140050e5e  call    HsmOsIsSyncProviderProcess
0x140050e63  neg     al
0x140050e65  mov     esi, 2
0x140050e6a  sbb     r12d, r12d
0x140050e6d  and     r12d, 80000000h
0x140050e74  cmp     edi, 4
0x140050e77  jz      loc_14005107C
0x140050e7d  mov     r8, [rbp+40h+FileInformation]
0x140050e81  or      r12d, edi
0x140050e84  mov     rbx, [rbp+40h+Object]
0x140050e88  test    r8b, 10h
0x140050e8c  jnz     loc_140051471
0x140050e92  movsxd  r9, r12d
0x140050e95  mov     rdx, rbx
0x140050e98  mov     rcx, r14
0x140050e9b  call    HsmiOpSetPinStateInternal
0x140050ea0  mov     ecx, eax
0x140050ea2  mov     edi, eax
0x140050ea4  call    HsmDbgBreakOnStatus
0x140050ea9  test    edi, edi
0x140050eab  js      loc_140051622
0x140050eb1  mov     rcx, [rbp+40h+Handle]; Handle
0x140050eb8  test    rcx, rcx
0x140050ebb  jnz     loc_140051689
0x140050ec1  mov     rcx, [rbp+40h+FileObject]; Object
0x140050ec5  test    rcx, rcx
0x140050ec8  jnz     loc_14005169A
0x140050ece  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x140050ed5  test    rcx, rcx
0x140050ed8  jnz     loc_1400516AB
0x140050ede  mov     rcx, [rbp+40h+Src+8]; P
0x140050ee2  test    rcx, rcx
0x140050ee5  jnz     loc_1400516BC
0x140050eeb  mov     rcx, qword ptr [rbp+40h+pusResult+8]; P
0x140050eef  test    rcx, rcx
0x140050ef2  jnz     loc_1400516D2
0x140050ef8  mov     eax, edi
0x140050efa  add     rsp, 108h
0x140050f01  pop     r15
0x140050f03  pop     r14
0x140050f05  pop     r13
0x140050f07  pop     r12
0x140050f09  pop     rdi
0x140050f0a  pop     rsi
0x140050f0b  pop     rbx
0x140050f0c  pop     rbp
0x140050f0d  retn
0x140050f0f  mov     r10, cs:WPP_GLOBAL_Control
0x140050f16  lea     rax, WPP_GLOBAL_Control
0x140050f1d  cmp     r10, rax
0x140050f20  jz      short loc_140050EB1
0x140050f22  mov     ecx, [r10+2Ch]
0x140050f26  test    cl, 1
0x140050f29  jz      short loc_140050EB1
0x140050f2b  mov     esi, 2
0x140050f30  cmp     [r10+29h], sil
0x140050f34  jb      loc_140050EB1
0x140050f3a  mov     r9, [rbp+40h+CallbackData]
0x140050f41  mov     edx, 0DFh
0x140050f46  mov     rcx, [r10+18h]
0x140050f4a  jmp     loc_14005165A
0x140050f4f  test    dword ptr [rbp+40h+FileInformation], 100000h
0x140050f56  jz      loc_140050E34
0x140050f5c  mov     byte ptr [rbp+40h+arg_48], sil
0x140050f63  test    r13, r13
0x140050f66  jz      loc_140051010
0x140050f6c  mov     rcx, r13; CallbackData
0x140050f6f  call    cs:__imp_FltGetRequestorProcess
0x140050f76  nop     dword ptr [rax+rax+00h]
0x140050f7b  mov     r12, [rbp+40h+arg_20]
0x140050f7f  lea     rcx, [rbp+40h+arg_48]
0x140050f86  mov     qword ptr [rsp+140h+FileInformationClass], rcx
0x140050f8b  mov     r9, rax
0x140050f8e  mov     rcx, r14
0x140050f91  mov     r8, rbx
0x140050f94  mov     rdx, r12
0x140050f97  call    HsmpCldCheckSyncProviderAccess
0x140050f9c  mov     ecx, eax
0x140050f9e  mov     ebx, eax
0x140050fa0  call    HsmDbgBreakOnStatus
0x140050fa5  mov     edi, 0C000CF18h
0x140050faa  test    ebx, ebx
0x140050fac  jns     loc_140051050
0x140050fb2  mov     ecx, edi
0x140050fb4  call    HsmDbgBreakOnStatus
0x140050fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140050fc0  lea     rax, WPP_GLOBAL_Control
0x140050fc7  cmp     rcx, rax
0x140050fca  jz      loc_140050EB1
0x140050fd0  mov     eax, [rcx+2Ch]
0x140050fd3  test    al, 1
0x140050fd5  jz      loc_140050EB1
0x140050fdb  mov     esi, 2
0x140050fe0  cmp     [rcx+29h], sil
0x140050fe4  jb      loc_140050EB1
0x140050fea  mov     rax, [rbp+40h+arg_30]
0x140050ff1  mov     edx, 0E0h
0x140050ff6  mov     rcx, [rcx+18h]
0x140050ffa  mov     r9, r13
0x140050ffd  mov     dword ptr [rsp+140h+AllocationSize], edi
0x140051001  mov     [rsp+140h+IoStatusBlock], rax
0x140051006  mov     [rsp+140h+LengthReturned], r12
0x14005100b  jmp     loc_140051673
0x140051010  mov     rax, rsi
0x140051013  jmp     loc_140050F7B
0x140051018  mov     eax, ecx
0x14005101a  and     eax, 100000h
0x14005101f  bt      ecx, 13h
0x140051023  jnb     short loc_140051048
0x140051025  neg     eax
0x140051027  sbb     eax, eax
0x140051029  and     eax, esi
0x14005102b  inc     eax
0x14005102d  mov     rbx, [rbp+40h+Object]
0x140051031  or      r12d, eax
0x140051034  mov     eax, r15d
0x140051037  and     eax, esi
0x140051039  jz      loc_14005143C
0x14005103f  mov     qword ptr [rbp+40h+var_90], rbx
0x140051043  jmp     loc_14005144D
0x140051048  neg     eax
0x14005104a  sbb     eax, eax
0x14005104c  and     eax, esi
0x14005104e  jmp     short loc_14005102D
0x140051050  cmp     byte ptr [rbp+40h+arg_48], sil
0x140051057  jnz     short loc_140051065
0x140051059  mov     ecx, edi
0x14005105b  call    HsmDbgBreakOnStatus
0x140051060  jmp     loc_140050FB2
0x140051065  mov     rbx, [rbp+40h+Object]
0x140051069  mov     edi, [rbp+40h+arg_50]
0x14005106f  jmp     loc_140050E43
0x140051074  mov     rax, rsi
0x140051077  jmp     loc_140050E5B
0x14005107c  mov     eax, dword ptr [rbp+40h+FileInformation]
0x14005107f  xorps   xmm0, xmm0
0x140051082  mov     rcx, [r14+20h]
0x140051086  mov     r9d, 101h
0x14005108c  mov     [rbp+40h+arg_48], eax
0x140051092  mov     r8, rbx
0x140051095  xor     eax, eax
0x140051097  mov     [rbp+40h+arg_28], rax
0x14005109b  lea     rax, [rbp+40h+Src]
0x14005109f  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1400510a3  mov     qword ptr [rsp+140h+FileInformationClass], rax
0x1400510a8  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1400510ac  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1400510b0  movups  xmmword ptr [rbp+40h+var_A0], xmm0
0x1400510b4  call    HsmiQueryFullFilePath
0x1400510b9  mov     ecx, eax
0x1400510bb  mov     edi, eax
0x1400510bd  call    HsmDbgBreakOnStatus
0x1400510c2  test    edi, edi
0x1400510c4  jns     short loc_140051133
0x1400510c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400510cd  lea     rax, WPP_GLOBAL_Control
0x1400510d4  cmp     rcx, rax
0x1400510d7  jz      loc_140050EB1
0x1400510dd  mov     eax, [rcx+2Ch]
0x1400510e0  test    al, 1
0x1400510e2  jz      loc_140050EB1
0x1400510e8  cmp     [rcx+29h], sil
0x1400510ec  jb      loc_140050EB1
0x1400510f2  mov     edx, 0E1h
0x1400510f7  jmp     short loc_1400510FE
0x1400510f9  mov     edx, 0E2h
0x1400510fe  mov     dword ptr [rsp+140h+LengthReturned], edi
0x140051102  mov     r9, r14
0x140051105  mov     qword ptr [rsp+140h+FileInformationClass], rbx
0x14005110a  jmp     short loc_14005111E
0x14005110c  mov     r9, [r14+20h]
0x140051110  mov     edx, 0E4h
0x140051115  mov     dword ptr [rsp+140h+LengthReturned], edi
0x140051119  mov     qword ptr [rsp+140h+FileInformationClass], r14
0x14005111e  mov     rcx, [rcx+18h]
0x140051122  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140051129  call    WPP_SF_qqd
0x14005112e  jmp     loc_140050EB1
0x140051133  movzx   ecx, word ptr [r14+40h]; usAugend
0x140051138  lea     r8, [rbp+40h+pusResult+2]; pusResult
0x14005113c  movzx   edx, word ptr [rbp+40h+Src]; usAddend
0x140051140  mov     [rbp+40h+pusResult+2], cx
0x140051144  call    RtlUShortAdd
0x140051149  mov     edi, eax
0x14005114b  test    eax, eax
0x14005114d  jns     short loc_140051180
0x14005114f  mov     rcx, cs:WPP_GLOBAL_Control
0x140051156  lea     rax, WPP_GLOBAL_Control
0x14005115d  cmp     rcx, rax
0x140051160  jz      loc_140050EB1
0x140051166  mov     eax, [rcx+2Ch]
0x140051169  test    al, 1
0x14005116b  jz      loc_140050EB1
0x140051171  cmp     [rcx+29h], sil
0x140051175  jb      loc_140050EB1
0x14005117b  jmp     loc_1400510F9
0x140051180  movzx   edx, [rbp+40h+pusResult+2]
0x140051184  xor     eax, eax
0x140051186  mov     ecx, 100h
0x14005118b  mov     [rbp+40h+pusResult], ax
0x14005118f  mov     r8d, 73557348h
0x140051195  call    cs:__imp_ExAllocatePool2
0x14005119c  nop     dword ptr [rax+rax+00h]
0x1400511a1  mov     rcx, rax
0x1400511a4  mov     qword ptr [rbp+40h+pusResult+8], rax
0x1400511a8  neg     rcx
0x1400511ab  mov     rbx, rax
0x1400511ae  sbb     edi, edi
0x1400511b0  not     edi
0x1400511b2  and     edi, 0C000009Ah
0x1400511b8  mov     ecx, edi
0x1400511ba  call    HsmDbgBreakOnStatus
0x1400511bf  test    rbx, rbx
0x1400511c2  jnz     short loc_140051211
0x1400511c4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400511cb  lea     rax, WPP_GLOBAL_Control
0x1400511d2  cmp     rcx, rax
0x1400511d5  jz      loc_140050EB1
0x1400511db  mov     eax, [rcx+2Ch]
0x1400511de  test    al, 1
0x1400511e0  jz      loc_140050EB1
0x1400511e6  cmp     [rcx+29h], sil
0x1400511ea  jb      loc_140050EB1
0x1400511f0  mov     rcx, [rcx+18h]
0x1400511f4  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x1400511fb  mov     edx, 0E3h
0x140051200  mov     [rsp+140h+FileInformationClass], edi
0x140051204  mov     r9, r14
0x140051207  call    WPP_SF_qd
0x14005120c  jmp     loc_140050EB1
0x140051211  movzx   r8d, word ptr [r14+40h]; Size
0x140051216  mov     rdx, [r14+48h]; Src
0x14005121a  mov     rcx, qword ptr [rbp+40h+pusResult+8]; void *
0x14005121e  call    memmove
0x140051223  movzx   eax, word ptr [r14+40h]
0x140051228  movzx   r8d, word ptr [rbp+40h+Src]; Size
0x14005122d  sub     ax, si
0x140051230  mov     rdx, [rbp+40h+Src+8]; Src
0x140051234  movzx   ecx, ax
0x140051237  mov     [rbp+40h+pusResult], cx
0x14005123b  add     rcx, qword ptr [rbp+40h+pusResult+8]; void *
  ... truncated ...
```
