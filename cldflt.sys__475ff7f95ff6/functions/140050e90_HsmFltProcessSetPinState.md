# HsmFltProcessSetPinState

- ea: `0x140050e90`
- end: `0x140051808`
- name: `HsmFltProcessSetPinState`
- size: `2424`
- prototype: `__int64 __fastcall(__int64, __int64, struct _FILE_OBJECT *, __int64, __int64, __int64, __int64, PFLT_CALLBACK_DATA CallbackData, void *Handle, unsigned int, int, void *FileHandle)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x14004dff0`

## callees

- `0x140003c50`
- `0x140006da0`
- `0x1400090b4`
- `0x140009300`
- `0x14000abb8`
- `0x14000ac28`
- `0x14000c12c`
- `0x14001e300`
- `0x140050dc0`
- `0x140050e90`
- `0x140051aa0`
- `0x14005f670`
- `0x140077b34`

## import_xrefs

- `ntoskrnl!ObOpenObjectByPointer` at `0x1400515c9`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1400515c9`
- `ntoskrnl!ZwClose` at `0x1400517a9`
- `ntoskrnl!ZwClose` at `0x1400517a9`
- `ntoskrnl!IoFileObjectType` at `0x1400515ad`
- `ntoskrnl!ObfDereferenceObject` at `0x1400517ba`
- `ntoskrnl!ObfDereferenceObject` at `0x1400517ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400517e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400517f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400517e1`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400517f7`
- `ntoskrnl!ExAllocatePool2` at `0x1400512b5`
- `ntoskrnl!ExAllocatePool2` at `0x1400512b5`
- `FLTMGR!FltCreateFileEx` at `0x14005141a`
- `FLTMGR!FltCreateFileEx` at `0x14005141a`
- `FLTMGR!FltClose` at `0x1400517cb`
- `FLTMGR!FltClose` at `0x1400517cb`
- `FLTMGR!FltQueryInformationFile` at `0x140050f23`
- `FLTMGR!FltQueryInformationFile` at `0x140051487`
- `FLTMGR!FltQueryInformationFile` at `0x140050f23`
- `FLTMGR!FltQueryInformationFile` at `0x140051487`
- `FLTMGR!FltGetRequestorProcess` at `0x140050f6f`
- `FLTMGR!FltGetRequestorProcess` at `0x14005108f`
- `FLTMGR!FltGetRequestorProcess` at `0x140050f6f`
- `FLTMGR!FltGetRequestorProcess` at `0x14005108f`

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
  PVOID v13; // rbx
  int v14; // r15d
  struct _FLT_INSTANCE *v15; // rcx
  NTSTATUS FullFilePath; // edi
  struct _FLT_CALLBACK_DATA *v17; // r13
  int v18; // edi
  PEPROCESS v19; // rax
  __int64 v20; // rdx
  unsigned int v21; // r12d
  __int64 v22; // r8
  int v23; // r12d
  PVOID v24; // rbx
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
  FullFilePath = FltQueryInformationFile(v15, a3, &FileInformation, 8u, FileAttributeTagInformation, &LengthReturned);
  HsmDbgBreakOnStatus(FullFilePath);
  if ( FullFilePath < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v26 = CallbackData;
      v27 = 223;
      AttachedDevice = WPP_GLOBAL_Control->AttachedDevice;
LABEL_106:
      WPP_SF_qqiqd(AttachedDevice, v27, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, v26, a2, a5, a7, FullFilePath);
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
    HsmDbgBreakOnStatus(v31);
    FullFilePath = -1073688808;
    if ( v31 >= 0 )
    {
      if ( (_BYTE)a10 )
      {
        v13 = Object;
        v18 = a11;
        goto LABEL_4;
      }
      HsmDbgBreakOnStatus(-1073688808);
    }
    HsmDbgBreakOnStatus(-1073688808);
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
    v24 = Object;
    goto LABEL_8;
  }
  v34 = *(_QWORD *)(a2 + 32);
  a10 = FileInformation;
  a6 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FullFilePath = HsmiQueryFullFilePath(v34, v20, v13, 257, Src);
  HsmDbgBreakOnStatus(FullFilePath);
  if ( FullFilePath < 0 )
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
  FullFilePath = RtlUShortAdd(pusResult[1], (USHORT)Src[0], &pusResult[1]);
  if ( FullFilePath < 0 )
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
    WPP_SF_qqd(v35->AttachedDevice, v36, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids, a2, v13, FullFilePath);
    goto LABEL_10;
  }
  pusResult[0] = 0;
  *(_QWORD *)&pusResult[4] = ExAllocatePool2(256, pusResult[1], 1934979912);
  v37 = *(_QWORD *)&pusResult[4];
  FullFilePath = *(_QWORD *)&pusResult[4] == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(FullFilePath);
  if ( !v37 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        227,
        WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids,
        a2,
        FullFilePath);
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
  FullFilePath = FltCreateFileEx(
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
  HsmDbgBreakOnStatus(FullFilePath);
  if ( FullFilePath < 0 )
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
        FullFilePath);
    }
    goto LABEL_10;
  }
  FullFilePath = FltQueryInformationFile(
                   *(PFLT_INSTANCE *)(a2 + 32),
                   FileObject,
                   &a6,
                   8u,
                   FileAttributeTagInformation,
                   &LengthReturned);
  HsmDbgBreakOnStatus(FullFilePath);
  if ( FullFilePath < 0 )
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
        FullFilePath);
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
  v24 = Object;
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
    FullFilePath = ObOpenObjectByPointer(v24, 0x200u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Handle);
    HsmDbgBreakOnStatus(FullFilePath);
    if ( FullFilePath >= 0 )
    {
      v43 = v14 & 2;
      v44 = v14 & 4;
      if ( a11 == 4 )
      {
        FullFilePath = HsmpRecurseDirectory(
                         a2,
                         (_DWORD)Handle,
                         (_DWORD)v24,
                         FileInformation,
                         v44 != 0,
                         v43 != 0,
                         (__int64)HsmiOpInheritPinStatePre,
                         (__int64)HsmiInfoUpdatePlaceholderStatesOnRenamePost,
                         (__int64)&v48);
        HsmDbgBreakOnStatus(FullFilePath);
        if ( FullFilePath < 0 )
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
        FullFilePath = HsmpRecurseDirectory(
                         a2,
                         (_DWORD)Handle,
                         (_DWORD)v24,
                         FileInformation,
                         v44 != 0,
                         v43 != 0,
                         0,
                         (__int64)HsmiOpSetPinStateInternal,
                         v23);
        HsmDbgBreakOnStatus(FullFilePath);
        if ( FullFilePath < 0 )
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
    FullFilePath = HsmiOpSetPinStateInternal(a2, v24, v22, v23);
    HsmDbgBreakOnStatus(FullFilePath);
    if ( FullFilePath < 0 )
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
  return (unsigned int)FullFilePath;
}

```

## disassembly

```asm
0x140050e90  mov     rax, rsp
0x140050e93  mov     [rax+20h], r9
0x140050e97  mov     [rax+18h], r8
0x140050e9b  mov     [rax+8], rcx
0x140050e9f  push    rbp
0x140050ea0  push    rbx
0x140050ea1  push    rsi
0x140050ea2  push    rdi
0x140050ea3  push    r12
0x140050ea5  push    r13
0x140050ea7  push    r14
0x140050ea9  push    r15
0x140050eab  lea     rbp, [rax-48h]
0x140050eaf  sub     rsp, 108h
0x140050eb6  mov     rax, [rbp+40h+Handle]
0x140050ebd  xor     esi, esi
0x140050ebf  mov     r14, rdx
0x140050ec2  mov     [rbp+40h+FileInformation], rsi
0x140050ec6  xor     ecx, ecx
0x140050ec8  mov     [rbp+40h+arg_18], esi
0x140050ecb  mov     rbx, r8
0x140050ece  mov     [rbp+40h+var_80], rcx
0x140050ed2  mov     edx, [rax+10h]
0x140050ed5  lea     r9d, [rsi+8]; Length
0x140050ed9  mov     r15d, [rax+8]
0x140050edd  lea     r8, [rbp+40h+FileInformation]; FileInformation
0x140050ee1  mov     rcx, [r14+20h]; Instance
0x140050ee5  lea     rax, [rbp+40h+arg_18]
0x140050ee9  xorps   xmm0, xmm0
0x140050eec  mov     [rbp+40h+arg_50], edx
0x140050ef2  xorps   xmm1, xmm1
0x140050ef5  mov     [rsp+140h+LengthReturned], rax; LengthReturned
0x140050efa  mov     rdx, rbx; FileObject
0x140050efd  mov     [rsp+140h+FileInformationClass], 23h ; '#'; FileInformationClass
0x140050f05  movups  xmmword ptr [rbp+40h+Src], xmm0
0x140050f09  mov     [rbp+40h+Handle], rsi
0x140050f10  movups  xmmword ptr [rbp+40h+pusResult], xmm1
0x140050f14  mov     [rbp+40h+FileHandle], rsi
0x140050f1b  mov     [rbp+40h+FileObject], rsi
0x140050f1f  movups  [rbp+40h+var_90], xmm0
0x140050f23  call    cs:__imp_FltQueryInformationFile
0x140050f2a  nop     dword ptr [rax+rax+00h]
0x140050f2f  mov     ecx, eax
0x140050f31  mov     edi, eax
0x140050f33  call    HsmDbgBreakOnStatus
0x140050f38  test    edi, edi
0x140050f3a  js      loc_14005102F
0x140050f40  test    dword ptr [rbp+40h+FileInformation], 80000h
0x140050f47  mov     r13, [rbp+40h+CallbackData]
0x140050f4e  jnz     loc_14005106F
0x140050f54  mov     edi, [rbp+40h+arg_50]
0x140050f5a  cmp     edi, 3
0x140050f5d  jz      loc_14005107C
0x140050f63  test    r13, r13
0x140050f66  jz      loc_140051194
0x140050f6c  mov     rcx, r13; CallbackData
0x140050f6f  call    cs:__imp_FltGetRequestorProcess
0x140050f76  nop     dword ptr [rax+rax+00h]
0x140050f7b  mov     rcx, rax
0x140050f7e  call    HsmOsIsSyncProviderProcess
0x140050f83  neg     al
0x140050f85  mov     esi, 2
0x140050f8a  sbb     r12d, r12d
0x140050f8d  and     r12d, 80000000h
0x140050f94  cmp     edi, 4
0x140050f97  jz      loc_14005119C
0x140050f9d  mov     r8, [rbp+40h+FileInformation]
0x140050fa1  or      r12d, edi
0x140050fa4  mov     rbx, [rbp+40h+Object]
0x140050fa8  test    r8b, 10h
0x140050fac  jnz     loc_140051591
0x140050fb2  movsxd  r9, r12d
0x140050fb5  mov     rdx, rbx
0x140050fb8  mov     rcx, r14
0x140050fbb  call    HsmiOpSetPinStateInternal
0x140050fc0  mov     ecx, eax
0x140050fc2  mov     edi, eax
0x140050fc4  call    HsmDbgBreakOnStatus
0x140050fc9  test    edi, edi
0x140050fcb  js      loc_140051742
0x140050fd1  mov     rcx, [rbp+40h+Handle]; Handle
0x140050fd8  test    rcx, rcx
0x140050fdb  jnz     loc_1400517A9
0x140050fe1  mov     rcx, [rbp+40h+FileObject]; Object
0x140050fe5  test    rcx, rcx
0x140050fe8  jnz     loc_1400517BA
0x140050fee  mov     rcx, [rbp+40h+FileHandle]; FileHandle
0x140050ff5  test    rcx, rcx
0x140050ff8  jnz     loc_1400517CB
0x140050ffe  mov     rcx, [rbp+40h+Src+8]; P
0x140051002  test    rcx, rcx
0x140051005  jnz     loc_1400517DC
0x14005100b  mov     rcx, qword ptr [rbp+40h+pusResult+8]; P
0x14005100f  test    rcx, rcx
0x140051012  jnz     loc_1400517F2
0x140051018  mov     eax, edi
0x14005101a  add     rsp, 108h
0x140051021  pop     r15
0x140051023  pop     r14
0x140051025  pop     r13
0x140051027  pop     r12
0x140051029  pop     rdi
0x14005102a  pop     rsi
0x14005102b  pop     rbx
0x14005102c  pop     rbp
0x14005102d  retn
0x14005102f  mov     r10, cs:WPP_GLOBAL_Control
0x140051036  lea     rax, WPP_GLOBAL_Control
0x14005103d  cmp     r10, rax
0x140051040  jz      short loc_140050FD1
0x140051042  mov     ecx, [r10+2Ch]
0x140051046  test    cl, 1
0x140051049  jz      short loc_140050FD1
0x14005104b  mov     esi, 2
0x140051050  cmp     [r10+29h], sil
0x140051054  jb      loc_140050FD1
0x14005105a  mov     r9, [rbp+40h+CallbackData]
0x140051061  mov     edx, 0DFh
0x140051066  mov     rcx, [r10+18h]
0x14005106a  jmp     loc_14005177A
0x14005106f  test    dword ptr [rbp+40h+FileInformation], 100000h
0x140051076  jz      loc_140050F54
0x14005107c  mov     byte ptr [rbp+40h+arg_48], sil
0x140051083  test    r13, r13
0x140051086  jz      loc_140051130
0x14005108c  mov     rcx, r13; CallbackData
0x14005108f  call    cs:__imp_FltGetRequestorProcess
0x140051096  nop     dword ptr [rax+rax+00h]
0x14005109b  mov     r12, [rbp+40h+arg_20]
0x14005109f  lea     rcx, [rbp+40h+arg_48]
0x1400510a6  mov     qword ptr [rsp+140h+FileInformationClass], rcx
0x1400510ab  mov     r9, rax
0x1400510ae  mov     rcx, r14
0x1400510b1  mov     r8, rbx
0x1400510b4  mov     rdx, r12
0x1400510b7  call    HsmpCldCheckSyncProviderAccess
0x1400510bc  mov     ecx, eax
0x1400510be  mov     ebx, eax
0x1400510c0  call    HsmDbgBreakOnStatus
0x1400510c5  mov     edi, 0C000CF18h
0x1400510ca  test    ebx, ebx
0x1400510cc  jns     loc_140051170
0x1400510d2  mov     ecx, edi
0x1400510d4  call    HsmDbgBreakOnStatus
0x1400510d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400510e0  lea     rax, WPP_GLOBAL_Control
0x1400510e7  cmp     rcx, rax
0x1400510ea  jz      loc_140050FD1
0x1400510f0  mov     eax, [rcx+2Ch]
0x1400510f3  test    al, 1
0x1400510f5  jz      loc_140050FD1
0x1400510fb  mov     esi, 2
0x140051100  cmp     [rcx+29h], sil
0x140051104  jb      loc_140050FD1
0x14005110a  mov     rax, [rbp+40h+arg_30]
0x140051111  mov     edx, 0E0h
0x140051116  mov     rcx, [rcx+18h]
0x14005111a  mov     r9, r13
0x14005111d  mov     dword ptr [rsp+140h+AllocationSize], edi
0x140051121  mov     [rsp+140h+IoStatusBlock], rax
0x140051126  mov     [rsp+140h+LengthReturned], r12
0x14005112b  jmp     loc_140051793
0x140051130  mov     rax, rsi
0x140051133  jmp     loc_14005109B
0x140051138  mov     eax, ecx
0x14005113a  and     eax, 100000h
0x14005113f  bt      ecx, 13h
0x140051143  jnb     short loc_140051168
0x140051145  neg     eax
0x140051147  sbb     eax, eax
0x140051149  and     eax, esi
0x14005114b  inc     eax
0x14005114d  mov     rbx, [rbp+40h+Object]
0x140051151  or      r12d, eax
0x140051154  mov     eax, r15d
0x140051157  and     eax, esi
0x140051159  jz      loc_14005155C
0x14005115f  mov     qword ptr [rbp+40h+var_90], rbx
0x140051163  jmp     loc_14005156D
0x140051168  neg     eax
0x14005116a  sbb     eax, eax
0x14005116c  and     eax, esi
0x14005116e  jmp     short loc_14005114D
0x140051170  cmp     byte ptr [rbp+40h+arg_48], sil
0x140051177  jnz     short loc_140051185
0x140051179  mov     ecx, edi
0x14005117b  call    HsmDbgBreakOnStatus
0x140051180  jmp     loc_1400510D2
0x140051185  mov     rbx, [rbp+40h+Object]
0x140051189  mov     edi, [rbp+40h+arg_50]
0x14005118f  jmp     loc_140050F63
0x140051194  mov     rax, rsi
0x140051197  jmp     loc_140050F7B
0x14005119c  mov     eax, dword ptr [rbp+40h+FileInformation]
0x14005119f  xorps   xmm0, xmm0
0x1400511a2  mov     rcx, [r14+20h]
0x1400511a6  mov     r9d, 101h
0x1400511ac  mov     [rbp+40h+arg_48], eax
0x1400511b2  mov     r8, rbx
0x1400511b5  xor     eax, eax
0x1400511b7  mov     [rbp+40h+arg_28], rax
0x1400511bb  lea     rax, [rbp+40h+Src]
0x1400511bf  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x1400511c3  mov     qword ptr [rsp+140h+FileInformationClass], rax
0x1400511c8  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x1400511cc  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x1400511d0  movups  xmmword ptr [rbp+40h+var_A0], xmm0
0x1400511d4  call    HsmiQueryFullFilePath
0x1400511d9  mov     ecx, eax
0x1400511db  mov     edi, eax
0x1400511dd  call    HsmDbgBreakOnStatus
0x1400511e2  test    edi, edi
0x1400511e4  jns     short loc_140051253
0x1400511e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400511ed  lea     rax, WPP_GLOBAL_Control
0x1400511f4  cmp     rcx, rax
0x1400511f7  jz      loc_140050FD1
0x1400511fd  mov     eax, [rcx+2Ch]
0x140051200  test    al, 1
0x140051202  jz      loc_140050FD1
0x140051208  cmp     [rcx+29h], sil
0x14005120c  jb      loc_140050FD1
0x140051212  mov     edx, 0E1h
0x140051217  jmp     short loc_14005121E
0x140051219  mov     edx, 0E2h
0x14005121e  mov     dword ptr [rsp+140h+LengthReturned], edi
0x140051222  mov     r9, r14
0x140051225  mov     qword ptr [rsp+140h+FileInformationClass], rbx
0x14005122a  jmp     short loc_14005123E
0x14005122c  mov     r9, [r14+20h]
0x140051230  mov     edx, 0E4h
0x140051235  mov     dword ptr [rsp+140h+LengthReturned], edi
0x140051239  mov     qword ptr [rsp+140h+FileInformationClass], r14
0x14005123e  mov     rcx, [rcx+18h]
0x140051242  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x140051249  call    WPP_SF_qqd
0x14005124e  jmp     loc_140050FD1
0x140051253  movzx   ecx, word ptr [r14+40h]; usAugend
0x140051258  lea     r8, [rbp+40h+pusResult+2]; pusResult
0x14005125c  movzx   edx, word ptr [rbp+40h+Src]; usAddend
0x140051260  mov     [rbp+40h+pusResult+2], cx
0x140051264  call    RtlUShortAdd
0x140051269  mov     edi, eax
0x14005126b  test    eax, eax
0x14005126d  jns     short loc_1400512A0
0x14005126f  mov     rcx, cs:WPP_GLOBAL_Control
0x140051276  lea     rax, WPP_GLOBAL_Control
0x14005127d  cmp     rcx, rax
0x140051280  jz      loc_140050FD1
0x140051286  mov     eax, [rcx+2Ch]
0x140051289  test    al, 1
0x14005128b  jz      loc_140050FD1
0x140051291  cmp     [rcx+29h], sil
0x140051295  jb      loc_140050FD1
0x14005129b  jmp     loc_140051219
0x1400512a0  movzx   edx, [rbp+40h+pusResult+2]
0x1400512a4  xor     eax, eax
0x1400512a6  mov     ecx, 100h
0x1400512ab  mov     [rbp+40h+pusResult], ax
0x1400512af  mov     r8d, 73557348h
0x1400512b5  call    cs:__imp_ExAllocatePool2
0x1400512bc  nop     dword ptr [rax+rax+00h]
0x1400512c1  mov     rcx, rax
0x1400512c4  mov     qword ptr [rbp+40h+pusResult+8], rax
0x1400512c8  neg     rcx
0x1400512cb  mov     rbx, rax
0x1400512ce  sbb     edi, edi
0x1400512d0  not     edi
0x1400512d2  and     edi, 0C000009Ah
0x1400512d8  mov     ecx, edi
0x1400512da  call    HsmDbgBreakOnStatus
0x1400512df  test    rbx, rbx
0x1400512e2  jnz     short loc_140051331
0x1400512e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400512eb  lea     rax, WPP_GLOBAL_Control
0x1400512f2  cmp     rcx, rax
0x1400512f5  jz      loc_140050FD1
0x1400512fb  mov     eax, [rcx+2Ch]
0x1400512fe  test    al, 1
0x140051300  jz      loc_140050FD1
0x140051306  cmp     [rcx+29h], sil
0x14005130a  jb      loc_140050FD1
0x140051310  mov     rcx, [rcx+18h]
0x140051314  lea     r8, WPP_33ec725460ef35358c23d43b6a8f1999_Traceguids
0x14005131b  mov     edx, 0E3h
0x140051320  mov     [rsp+140h+FileInformationClass], edi
0x140051324  mov     r9, r14
0x140051327  call    WPP_SF_qd
0x14005132c  jmp     loc_140050FD1
0x140051331  movzx   r8d, word ptr [r14+40h]; Size
0x140051336  mov     rdx, [r14+48h]; Src
0x14005133a  mov     rcx, qword ptr [rbp+40h+pusResult+8]; void *
0x14005133e  call    memmove
0x140051343  movzx   eax, word ptr [r14+40h]
0x140051348  movzx   r8d, word ptr [rbp+40h+Src]; Size
0x14005134d  sub     ax, si
0x140051350  mov     rdx, [rbp+40h+Src+8]; Src
0x140051354  movzx   ecx, ax
0x140051357  mov     [rbp+40h+pusResult], cx
0x14005135b  add     rcx, qword ptr [rbp+40h+pusResult+8]; void *
  ... truncated ...
```
