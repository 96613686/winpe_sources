# MountMgrVolumeMountPointChanged

- ea: `0x14000db54`
- end: `0x14000e339`
- name: `MountMgrVolumeMountPointChanged`
- size: `2021`
- prototype: `__int64 __fastcall(struct _KMUTANT *, __int64, __int64, struct _UNICODE_STRING *, _WORD *, PUNICODE_STRING ObjectName)`
- caller_count: `2`
- callee_count: `11`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000e340`
- `0x14000ecbc`

## callees

- `0x1400019c0`
- `0x140001ae0`
- `0x140001b30`
- `0x140002178`
- `0x140002f80`
- `0x14000db54`
- `0x140010600`
- `0x140010970`
- `0x1400144a0`
- `0x140019140`
- `0x14001a3d0`

## import_xrefs

- `ntoskrnl!ObQueryNameString` at `0x14000e046`
- `ntoskrnl!ObQueryNameString` at `0x14000e17b`
- `ntoskrnl!ObQueryNameString` at `0x14000e046`
- `ntoskrnl!ObQueryNameString` at `0x14000e17b`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14000ddd4`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x14000ddd4`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e316`
- `ntoskrnl!ObfDereferenceObject` at `0x14000e316`
- `ntoskrnl!KeReleaseMutex` at `0x14000dc66`
- `ntoskrnl!KeReleaseMutex` at `0x14000dc66`
- `ntoskrnl!IoFileObjectType` at `0x14000de67`
- `ntoskrnl!ExAllocatePool2` at `0x14000dec4`
- `ntoskrnl!ExAllocatePool2` at `0x14000df66`
- `ntoskrnl!ExAllocatePool2` at `0x14000e06d`
- `ntoskrnl!ExAllocatePool2` at `0x14000dec4`
- `ntoskrnl!ExAllocatePool2` at `0x14000df66`
- `ntoskrnl!ExAllocatePool2` at `0x14000e06d`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000de8f`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14000de8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000df4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e302`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000df4c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e2ec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000e302`
- `ntoskrnl!ZwOpenFile` at `0x14000dd78`
- `ntoskrnl!ZwOpenFile` at `0x14000dd78`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000df2b`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000dfea`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000df2b`
- `ntoskrnl!ZwQueryInformationFile` at `0x14000dfea`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e10d`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000e10d`

## pseudocode

```c
__int64 __fastcall MountMgrVolumeMountPointChanged(
        struct _KMUTANT *a1,
        __int64 a2,
        __int64 a3,
        struct _UNICODE_STRING *a4,
        _WORD *a5,
        PUNICODE_STRING ObjectName)
{
  USHORT *v6; // r10
  __int64 v7; // rax
  _DWORD *v8; // r14
  char v9; // si
  unsigned int v10; // r13d
  USHORT *v11; // rdi
  USHORT *v12; // r15
  unsigned int v13; // r9d
  unsigned __int16 *v14; // r12
  unsigned int v15; // edx
  NTSTATUS DeviceName; // ebx
  ULONG v17; // edx
  __int64 v18; // rdi
  ULONG v19; // edx
  __int64 v20; // r8
  __int64 v21; // r11
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  NTSTATUS v25; // eax
  _DWORD *Pool2; // rax
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r8
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  __int64 v32; // r8
  struct _OBJECT_NAME_INFORMATION *v33; // rdi
  __int64 v34; // r8
  PVOID *v35; // r13
  __int64 v36; // r8
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  ULONG v39; // r8d
  __int64 v40; // r8
  PUNICODE_STRING v41; // rcx
  _WORD *v42; // rcx
  size_t v43; // r8
  __int64 v44; // r8
  __int64 v45; // r8
  PVOID *v47; // [rsp+38h] [rbp-B9h]
  void *FileHandle; // [rsp+40h] [rbp-B1h] BYREF
  struct _OBJECT_NAME_INFORMATION *v49; // [rsp+48h] [rbp-A9h]
  __int64 FsInformation; // [rsp+50h] [rbp-A1h] BYREF
  UNICODE_STRING v51; // [rsp+58h] [rbp-99h] BYREF
  USHORT *v52; // [rsp+68h] [rbp-89h]
  __int64 v53; // [rsp+70h] [rbp-81h] BYREF
  UNICODE_STRING SourceString; // [rsp+78h] [rbp-79h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+88h] [rbp-69h] BYREF
  struct _UNICODE_STRING v56; // [rsp+98h] [rbp-59h] BYREF
  PVOID Object; // [rsp+A8h] [rbp-49h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-41h] BYREF
  _OBJECT_NAME_INFORMATION ObjectNameInfo; // [rsp+E0h] [rbp-11h] BYREF
  ULONG ReturnLength; // [rsp+150h] [rbp+5Fh] BYREF
  int v62; // [rsp+158h] [rbp+67h]
  PUNICODE_STRING StringOut; // [rsp+160h] [rbp+6Fh]

  StringOut = a4;
  v62 = a3;
  v6 = *(USHORT **)(a2 + 24);
  FileHandle = 0;
  ReturnLength = 0;
  v7 = *(_QWORD *)(a2 + 184);
  *(_QWORD *)&v56.Length = 0;
  v8 = 0;
  memset(&ObjectAttributes, 0, 44);
  FsInformation = 0;
  v9 = 0;
  v56.Buffer = 0;
  v10 = 0;
  IoStatusBlock = 0;
  v52 = v6;
  v11 = v6 + 1;
  SourceString = 0;
  v47 = 0;
  v12 = v6 + 3;
  ObjectNameInfo = 0;
  v13 = *(_DWORD *)(v7 + 16);
  v14 = v6 + 2;
  v49 = 0;
  v53 = 0;
  *(_DWORD *)(&v51.MaximumLength + 1) = 0;
  if ( v13 < 8 )
    goto LABEL_5;
  a3 = *v14 + (unsigned int)*v12;
  v15 = *v6 + *v11;
  if ( v15 <= (unsigned int)a3 )
    v15 = *v14 + *v12;
  if ( v13 >= v15 )
  {
    DeviceName = 0;
  }
  else
  {
LABEL_5:
    DeviceName = -1073741811;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 237, a3, 3221225485LL);
  }
  Object = &a1[1];
  KeReleaseMutex(a1 + 1, 0);
  if ( DeviceName < 0 )
  {
    v18 = 0;
    goto LABEL_56;
  }
  SourceString.Length = *v11;
  SourceString.MaximumLength = *v11;
  SourceString.Buffer = (USHORT *)((char *)v52 + *v52);
  v18 = 0;
  DeviceName = RtlUnicodeStringValidateEx(&SourceString, v17);
  if ( DeviceName < 0 )
  {
    v22 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v23 = 238;
LABEL_26:
      v24 = (unsigned int)DeviceName;
LABEL_27:
      WPP_SF_L(v22->AttachedDevice, v23, v20, v24);
      goto LABEL_56;
    }
    goto LABEL_56;
  }
  v51.Length = *v12;
  v51.MaximumLength = v51.Length;
  v51.Buffer = (PWSTR)(v21 + *v14);
  DeviceName = RtlUnicodeStringValidateEx(&v51, v19);
  if ( DeviceName >= 0 )
  {
    ObjectAttributes.ObjectName = &SourceString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    DeviceName = ZwOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x200020u);
    if ( DeviceName < 0 )
    {
      FileHandle = 0;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v23 = 240;
        goto LABEL_26;
      }
      goto LABEL_56;
    }
    DeviceName = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
    if ( DeviceName < 0 )
    {
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v23 = 241;
        goto LABEL_26;
      }
      goto LABEL_56;
    }
    if ( (_DWORD)FsInformation != 7 && (_DWORD)FsInformation != 36 || (FsInformation & 0x1100000000LL) != 0 )
    {
      DeviceName = -1073741811;
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v23 = 242;
        v24 = 3221225485LL;
        goto LABEL_27;
      }
      goto LABEL_56;
    }
    *(_QWORD *)&v51.Length = 0;
    v25 = ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, (PVOID *)&v51, 0);
    v18 = *(_QWORD *)&v51.Length;
    DeviceName = v25;
    v47 = *(PVOID **)&v51.Length;
    if ( v25 < 0 )
      goto LABEL_56;
    v10 = 8;
    Pool2 = (_DWORD *)ExAllocatePool2(258, 8, 1098149453);
    v8 = Pool2;
    if ( !Pool2 )
    {
      DeviceName = -1073741670;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
        goto LABEL_50;
      v28 = 243;
      goto LABEL_39;
    }
    DeviceName = ZwQueryInformationFile(FileHandle, &IoStatusBlock, Pool2, 8u, FileNameInformation);
    if ( DeviceName == -2147483643 )
    {
      v10 = *v8 + 8;
      ExFreePoolWithTag(v8, 0);
      v8 = (_DWORD *)ExAllocatePool2(258, v10, 1098149453);
      if ( !v8 )
      {
        DeviceName = -1073741670;
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
          goto LABEL_50;
        v28 = 244;
LABEL_39:
        WPP_SF_(v27->AttachedDevice, v28);
LABEL_50:
        v9 = 1;
        goto LABEL_56;
      }
    }
    else if ( DeviceName < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_50;
      v31 = 245;
LABEL_49:
      WPP_SF_L(v30->AttachedDevice, v31, v29, (unsigned int)DeviceName);
      goto LABEL_50;
    }
    DeviceName = ZwQueryInformationFile(FileHandle, &IoStatusBlock, v8, v10, FileNameInformation);
    if ( DeviceName >= 0 )
      goto LABEL_50;
    v30 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
      goto LABEL_50;
    v31 = 246;
    goto LABEL_49;
  }
  v22 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v23 = 239;
    goto LABEL_26;
  }
LABEL_56:
  CloseFileHandleOutsideExtensionMutexLock(0);
  if ( DeviceName < 0 )
    goto LABEL_66;
  DeviceName = ObQueryNameString(*(PVOID *)(v18 + 8), &ObjectNameInfo, 0x10u, &ReturnLength);
  if ( DeviceName != -1073741820 )
  {
    if ( DeviceName >= 0 )
    {
      v33 = v49;
      goto LABEL_74;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 248, v32, (unsigned int)DeviceName);
LABEL_66:
    v33 = v49;
LABEL_67:
    v35 = v47;
    goto LABEL_68;
  }
  v10 = ReturnLength;
  v33 = (struct _OBJECT_NAME_INFORMATION *)ExAllocatePool2(258, ReturnLength, 1098149453);
  if ( !v33 )
  {
    DeviceName = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 247, v34, 3221225626LL);
    goto LABEL_67;
  }
LABEL_74:
  v39 = v10;
  v35 = v47;
  DeviceName = ObQueryNameString(v47[1], v33, v39, &ReturnLength);
  if ( DeviceName < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 249, v40, (unsigned int)DeviceName);
  }
LABEL_68:
  KeWaitForSingleObject(Object, Executive, 0, 0, 0);
  if ( DeviceName < 0 )
    goto LABEL_90;
  DeviceName = QueryDeviceName(&v33->Name, StringOut);
  if ( DeviceName >= 0 )
  {
    v41 = ObjectName;
    ObjectName->Length = *v12;
    v41->MaximumLength = *v12;
    v41->Buffer = (USHORT *)((char *)v52 + *v14);
    DeviceName = QueryDeviceName(v41, &v56);
    if ( DeviceName >= 0 )
    {
      v42 = a5;
      v43 = *(unsigned __int16 *)v8;
      *a5 = v43;
      v42[1] = *(_WORD *)v8;
      *((_QWORD *)v42 + 1) = v8;
      memmove(v8, v8 + 1, v43);
      v8 = 0;
      MountMgrNotify(a1);
      LOBYTE(v44) = 1;
      MountMgrNotifyNameChange(a1, &v56, v44);
      if ( v62 >= 0 )
        goto LABEL_90;
      DeviceName = FindDeviceInfo(a1, StringOut, v45, &v53);
      if ( DeviceName >= 0 )
      {
        ReconcileThisDatabaseWithMaster(a1);
        DeviceName = 259;
        goto LABEL_90;
      }
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v38 = 252;
        goto LABEL_89;
      }
    }
    else
    {
      v37 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v38 = 251;
        goto LABEL_89;
      }
    }
  }
  else
  {
    v37 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v38 = 250;
LABEL_89:
      WPP_SF_L(v37->AttachedDevice, v38, v36, (unsigned int)DeviceName);
    }
  }
LABEL_90:
  if ( v56.Buffer )
    ExFreePoolWithTag(v56.Buffer, 0);
  if ( v33 )
    ExFreePoolWithTag(v33, 0);
  if ( v8 )
    ExFreePoolWithTag(v8, 0);
  if ( v9 )
    ObfDereferenceObject(v35);
  return (unsigned int)DeviceName;
}

```

## disassembly

```asm
0x14000db54  mov     rax, rsp
0x14000db57  mov     [rax+20h], r9
0x14000db5b  mov     [rax+18h], r8d
0x14000db5f  mov     [rax+8], rcx
0x14000db63  push    rbp
0x14000db64  push    rbx
0x14000db65  push    rsi
0x14000db66  push    rdi
0x14000db67  push    r12
0x14000db69  push    r13
0x14000db6b  push    r14
0x14000db6d  push    r15
0x14000db6f  lea     rbp, [rax-4Fh]
0x14000db73  sub     rsp, 0F8h
0x14000db7a  mov     r10, [rdx+18h]
0x14000db7e  xor     r11d, r11d
0x14000db81  xorps   xmm0, xmm0
0x14000db84  mov     [rsp+130h+FileHandle], r11
0x14000db89  xor     eax, eax
0x14000db8b  mov     [rbp+47h+ReturnLength], r11d
0x14000db8f  mov     rax, [rdx+0B8h]
0x14000db96  xorps   xmm1, xmm1
0x14000db99  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x14000db9d  mov     qword ptr [rbp+47h+var_A0.Length], r11
0x14000dba1  mov     r14d, r11d
0x14000dba4  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x14000dba8  mov     [rsp+130h+FsInformation], r11
0x14000dbad  mov     sil, r11b
0x14000dbb0  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x14000dbb4  mov     [rbp+47h+var_A0.Buffer], r11
0x14000dbb8  mov     r13d, r11d
0x14000dbbb  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x14000dbbf  mov     [rsp+130h+var_D0], r10
0x14000dbc4  lea     rdi, [r10+2]
0x14000dbc8  movups  xmmword ptr [rbp+47h+SourceString.Length], xmm1
0x14000dbcc  mov     [rsp+130h+var_100], r11
0x14000dbd1  lea     r15, [r10+6]
0x14000dbd5  movups  xmmword ptr [rbp+47h+ObjectNameInfo.Name.Length], xmm0
0x14000dbd9  mov     r9d, [rax+10h]
0x14000dbdd  lea     r12, [r10+4]
0x14000dbe1  mov     [rsp+130h+var_F0], r11
0x14000dbe6  lea     rax, WPP_GLOBAL_Control
0x14000dbed  mov     [rsp+130h+var_C8], r11
0x14000dbf2  mov     dword ptr [rsp+130h+var_E0+4], r11d
0x14000dbf7  cmp     r9d, 8
0x14000dbfb  jb      short loc_14000DC29
0x14000dbfd  movzx   eax, word ptr [r12]
0x14000dc02  movzx   r8d, word ptr [r15]
0x14000dc06  movzx   edx, word ptr [rdi]
0x14000dc09  add     r8d, eax
0x14000dc0c  movzx   eax, word ptr [r10]
0x14000dc10  add     edx, eax
0x14000dc12  cmp     edx, r8d
0x14000dc15  cmovbe  edx, r8d
0x14000dc19  cmp     r9d, edx
0x14000dc1c  jnb     loc_14000DCD5
0x14000dc22  lea     rax, WPP_GLOBAL_Control
0x14000dc29  mov     ebx, 0C000000Dh
0x14000dc2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dc35  cmp     rcx, rax
0x14000dc38  jz      short loc_14000DC55
0x14000dc3a  mov     eax, [rcx+2Ch]
0x14000dc3d  test    al, 1
0x14000dc3f  jz      short loc_14000DC55
0x14000dc41  mov     rcx, [rcx+18h]
0x14000dc45  mov     edx, 0EDh
0x14000dc4a  mov     r9d, 0C000000Dh
0x14000dc50  call    WPP_SF_L
0x14000dc55  mov     rax, [rbp+47h+Context]
0x14000dc59  xor     edx, edx; Wait
0x14000dc5b  add     rax, 38h ; '8'
0x14000dc5f  mov     rcx, rax; Mutex
0x14000dc62  mov     [rbp+47h+Object], rax
0x14000dc66  call    cs:__imp_KeReleaseMutex
0x14000dc6d  nop     dword ptr [rax+rax+00h]
0x14000dc72  test    ebx, ebx
0x14000dc74  js      loc_14000E01D
0x14000dc7a  movzx   eax, word ptr [rdi]
0x14000dc7d  lea     rcx, [rbp+47h+SourceString]; SourceString
0x14000dc81  mov     r11, [rsp+130h+var_D0]
0x14000dc86  mov     [rbp+47h+SourceString.Length], ax
0x14000dc8a  movzx   eax, word ptr [rdi]
0x14000dc8d  mov     [rbp+47h+SourceString.MaximumLength], ax
0x14000dc91  movzx   eax, word ptr [r11]
0x14000dc95  add     rax, r11
0x14000dc98  mov     [rbp+47h+SourceString.Buffer], rax
0x14000dc9c  call    RtlUnicodeStringValidateEx
0x14000dca1  xor     edi, edi
0x14000dca3  mov     ebx, eax
0x14000dca5  test    eax, eax
0x14000dca7  jns     short loc_14000DCDD
0x14000dca9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dcb0  lea     rax, WPP_GLOBAL_Control
0x14000dcb7  cmp     rcx, rax
0x14000dcba  jz      loc_14000E020
0x14000dcc0  mov     eax, [rcx+2Ch]
0x14000dcc3  test    al, 1
0x14000dcc5  jz      loc_14000E020
0x14000dccb  mov     edx, 0EEh
0x14000dcd0  jmp     loc_14000DE0D
0x14000dcd5  mov     ebx, r11d
0x14000dcd8  jmp     loc_14000DC55
0x14000dcdd  movzx   eax, word ptr [r15]
0x14000dce1  lea     rcx, [rsp+130h+var_E0]; SourceString
0x14000dce6  mov     [rsp+130h+var_E0.Length], ax
0x14000dceb  mov     [rsp+130h+var_E0.MaximumLength], ax
0x14000dcf0  movzx   eax, word ptr [r12]
0x14000dcf5  add     rax, r11
0x14000dcf8  mov     [rsp+130h+var_E0.Buffer], rax
0x14000dcfd  call    RtlUnicodeStringValidateEx
0x14000dd02  mov     ebx, eax
0x14000dd04  test    eax, eax
0x14000dd06  jns     short loc_14000DD34
0x14000dd08  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd0f  lea     rax, WPP_GLOBAL_Control
0x14000dd16  cmp     rcx, rax
0x14000dd19  jz      loc_14000E020
0x14000dd1f  mov     eax, [rcx+2Ch]
0x14000dd22  test    al, 1
0x14000dd24  jz      loc_14000E020
0x14000dd2a  mov     edx, 0EFh
0x14000dd2f  jmp     loc_14000DE0D
0x14000dd34  lea     rax, [rbp+47h+SourceString]
0x14000dd38  mov     [rsp+130h+OpenOptions], 200020h; OpenOptions
0x14000dd40  xorps   xmm0, xmm0
0x14000dd43  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x14000dd47  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x14000dd4b  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14000dd52  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14000dd56  mov     [rbp+47h+ObjectAttributes.RootDirectory], rdi
0x14000dd5a  mov     edx, 100080h; DesiredAccess
0x14000dd5f  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x14000dd66  lea     rcx, [rsp+130h+FileHandle]; FileHandle
0x14000dd6b  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14000dd73  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000dd78  call    cs:__imp_ZwOpenFile
0x14000dd7f  nop     dword ptr [rax+rax+00h]
0x14000dd84  mov     ebx, eax
0x14000dd86  test    eax, eax
0x14000dd88  jns     short loc_14000DDB8
0x14000dd8a  mov     [rsp+130h+FileHandle], rdi
0x14000dd8f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dd96  lea     rax, WPP_GLOBAL_Control
0x14000dd9d  cmp     rcx, rax
0x14000dda0  jz      loc_14000E020
0x14000dda6  mov     eax, [rcx+2Ch]
0x14000dda9  test    al, 1
0x14000ddab  jz      loc_14000E020
0x14000ddb1  mov     edx, 0F0h
0x14000ddb6  jmp     short loc_14000DE0D
0x14000ddb8  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x14000ddbd  lea     r8, [rsp+130h+FsInformation]; FsInformation
0x14000ddc2  mov     r9d, 8; Length
0x14000ddc8  mov     [rsp+130h+ShareAccess], 4; FsInformationClass
0x14000ddd0  lea     rdx, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x14000ddd4  call    cs:__imp_ZwQueryVolumeInformationFile
0x14000dddb  nop     dword ptr [rax+rax+00h]
0x14000dde0  mov     ebx, eax
0x14000dde2  test    eax, eax
0x14000dde4  jns     short loc_14000DE1E
0x14000dde6  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dded  lea     rax, WPP_GLOBAL_Control
0x14000ddf4  cmp     rcx, rax
0x14000ddf7  jz      loc_14000E020
0x14000ddfd  mov     eax, [rcx+2Ch]
0x14000de00  test    al, 1
0x14000de02  jz      loc_14000E020
0x14000de08  mov     edx, 0F1h
0x14000de0d  mov     r9d, ebx
0x14000de10  mov     rcx, [rcx+18h]
0x14000de14  call    WPP_SF_L
0x14000de19  jmp     loc_14000E020
0x14000de1e  cmp     dword ptr [rsp+130h+FsInformation], 7
0x14000de23  jz      short loc_14000DE2C
0x14000de25  cmp     dword ptr [rsp+130h+FsInformation], 24h ; '$'
0x14000de2a  jnz     short loc_14000DE33
0x14000de2c  test    byte ptr [rsp+130h+FsInformation+4], 11h
0x14000de31  jz      short loc_14000DE67
0x14000de33  mov     ebx, 0C000000Dh
0x14000de38  mov     rcx, cs:WPP_GLOBAL_Control
0x14000de3f  lea     rax, WPP_GLOBAL_Control
0x14000de46  cmp     rcx, rax
0x14000de49  jz      loc_14000E020
0x14000de4f  mov     eax, [rcx+2Ch]
0x14000de52  test    al, 1
0x14000de54  jz      loc_14000E020
0x14000de5a  mov     edx, 0F2h
0x14000de5f  mov     r9d, 0C000000Dh
0x14000de65  jmp     short loc_14000DE10
0x14000de67  mov     r8, cs:__imp_IoFileObjectType
0x14000de6e  lea     rax, [rsp+130h+var_E0]
0x14000de73  mov     rcx, [rsp+130h+FileHandle]; Handle
0x14000de78  xor     r9d, r9d; AccessMode
0x14000de7b  mov     qword ptr [rsp+130h+OpenOptions], rdi; HandleInformation
0x14000de80  xor     edx, edx; DesiredAccess
0x14000de82  mov     qword ptr [rsp+130h+var_E0.Length], rdi
0x14000de87  mov     r8, [r8]; ObjectType
0x14000de8a  mov     qword ptr [rsp+130h+ShareAccess], rax; Object
0x14000de8f  call    cs:__imp_ObReferenceObjectByHandle
0x14000de96  nop     dword ptr [rax+rax+00h]
0x14000de9b  mov     rdi, qword ptr [rsp+130h+var_E0.Length]
0x14000dea0  mov     ebx, eax
0x14000dea2  mov     [rsp+130h+var_100], rdi
0x14000dea7  test    eax, eax
0x14000dea9  js      loc_14000E020
0x14000deaf  mov     ebx, 8
0x14000deb4  mov     r8d, 41746E4Dh
0x14000deba  mov     edx, ebx
0x14000debc  mov     ecx, 102h
0x14000dec1  mov     r13d, ebx
0x14000dec4  call    cs:__imp_ExAllocatePool2
0x14000decb  nop     dword ptr [rax+rax+00h]
0x14000ded0  mov     r14, rax
0x14000ded3  test    rax, rax
0x14000ded6  jnz     short loc_14000DF13
0x14000ded8  mov     ebx, 0C000009Ah
0x14000dedd  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dee4  lea     rax, WPP_GLOBAL_Control
0x14000deeb  cmp     rcx, rax
0x14000deee  jz      loc_14000DFD2
0x14000def4  mov     edx, [rcx+2Ch]
0x14000def7  test    dl, 4
0x14000defa  jz      loc_14000DFD2
0x14000df00  mov     edx, 0F3h
0x14000df05  mov     rcx, [rcx+18h]
0x14000df09  call    WPP_SF_
0x14000df0e  jmp     loc_14000DFD2
0x14000df13  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x14000df18  lea     rdx, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x14000df1c  mov     esi, 9
0x14000df21  mov     r9d, ebx; Length
0x14000df24  mov     r8, r14; FileInformation
0x14000df27  mov     [rsp+130h+ShareAccess], esi; FileInformationClass
0x14000df2b  call    cs:__imp_ZwQueryInformationFile
0x14000df32  nop     dword ptr [rax+rax+00h]
0x14000df37  mov     ebx, eax
0x14000df39  cmp     eax, 80000005h
0x14000df3e  jnz     short loc_14000DFA3
0x14000df40  mov     r13d, [r14]
0x14000df43  xor     edx, edx; Tag
0x14000df45  mov     rcx, r14; P
0x14000df48  add     r13d, 8
0x14000df4c  call    cs:__imp_ExFreePoolWithTag
0x14000df53  nop     dword ptr [rax+rax+00h]
0x14000df58  mov     edx, r13d
0x14000df5b  mov     ecx, 102h
0x14000df60  mov     r8d, 41746E4Dh
0x14000df66  call    cs:__imp_ExAllocatePool2
0x14000df6d  nop     dword ptr [rax+rax+00h]
0x14000df72  mov     r14, rax
0x14000df75  test    rax, rax
0x14000df78  jnz     short loc_14000DFD7
0x14000df7a  mov     ebx, 0C000009Ah
0x14000df7f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000df86  lea     rax, WPP_GLOBAL_Control
0x14000df8d  cmp     rcx, rax
0x14000df90  jz      short loc_14000DFD2
0x14000df92  mov     eax, [rcx+2Ch]
0x14000df95  test    al, 4
0x14000df97  jz      short loc_14000DFD2
0x14000df99  mov     edx, 0F4h
0x14000df9e  jmp     loc_14000DF05
0x14000dfa3  test    ebx, ebx
0x14000dfa5  jns     short loc_14000DFD7
0x14000dfa7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000dfae  lea     rax, WPP_GLOBAL_Control
0x14000dfb5  cmp     rcx, rax
0x14000dfb8  jz      short loc_14000DFD2
0x14000dfba  mov     eax, [rcx+2Ch]
0x14000dfbd  test    al, 1
0x14000dfbf  jz      short loc_14000DFD2
0x14000dfc1  mov     edx, 0F5h
0x14000dfc6  mov     rcx, [rcx+18h]
0x14000dfca  mov     r9d, ebx
0x14000dfcd  call    WPP_SF_L
0x14000dfd2  mov     sil, 1
0x14000dfd5  jmp     short loc_14000E020
0x14000dfd7  mov     rcx, [rsp+130h+FileHandle]; FileHandle
0x14000dfdc  lea     rdx, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x14000dfe0  mov     r9d, r13d; Length
0x14000dfe3  mov     [rsp+130h+ShareAccess], esi; FileInformationClass
0x14000dfe7  mov     r8, r14; FileInformation
0x14000dfea  call    cs:__imp_ZwQueryInformationFile
0x14000dff1  nop     dword ptr [rax+rax+00h]
0x14000dff6  mov     ebx, eax
0x14000dff8  test    eax, eax
0x14000dffa  jns     short loc_14000DFD2
0x14000dffc  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e003  lea     rax, WPP_GLOBAL_Control
0x14000e00a  cmp     rcx, rax
0x14000e00d  jz      short loc_14000DFD2
0x14000e00f  mov     eax, [rcx+2Ch]
0x14000e012  test    al, 1
0x14000e014  jz      short loc_14000DFD2
0x14000e016  mov     edx, 0F6h
0x14000e01b  jmp     short loc_14000DFC6
0x14000e01d  mov     rdi, r13
0x14000e020  mov     rdx, [rsp+130h+FileHandle]
0x14000e025  xor     ecx, ecx
0x14000e027  call    CloseFileHandleOutsideExtensionMutexLock
  ... truncated ...
```
