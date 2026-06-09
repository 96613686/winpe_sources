# CipEnableJournalingAlways

- ea: `0x180060d48`
- end: `0x180061009`
- name: `CipEnableJournalingAlways`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18008f2f4`

## callees

- `0x18002c0d0`
- `0x180060d48`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x180060ec4`
- `ntoskrnl!KeStackAttachProcess` at `0x180060ec4`
- `ntoskrnl!ExAllocatePool2` at `0x180060e33`
- `ntoskrnl!ExAllocatePool2` at `0x180060e33`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060fd2`
- `ntoskrnl!ExFreePoolWithTag` at `0x180060fd2`
- `ntoskrnl!ZwClose` at `0x180060f6c`
- `ntoskrnl!ZwClose` at `0x180060f6c`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180060f81`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180060f81`
- `ntoskrnl!ObfDereferenceObject` at `0x180060fa5`
- `ntoskrnl!ObfDereferenceObject` at `0x180060fb9`
- `ntoskrnl!ObfDereferenceObject` at `0x180060fa5`
- `ntoskrnl!ObfDereferenceObject` at `0x180060fb9`
- `ntoskrnl!ZwCreateFile` at `0x180060f0b`
- `ntoskrnl!ZwCreateFile` at `0x180060f0b`
- `ntoskrnl!ZwFsControlFile` at `0x180060f55`
- `ntoskrnl!ZwFsControlFile` at `0x180060f55`
- `ntoskrnl!PsGetProcessServerSilo` at `0x180060e9b`
- `ntoskrnl!PsGetProcessServerSilo` at `0x180060e9b`
- `ntoskrnl!ObQueryNameString` at `0x180060e00`
- `ntoskrnl!ObQueryNameString` at `0x180060e60`
- `ntoskrnl!ObQueryNameString` at `0x180060e00`
- `ntoskrnl!ObQueryNameString` at `0x180060e60`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180060db8`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180060db8`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180060eaa`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180060eaa`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180060dc7`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180060dc7`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180060ddd`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180060ddd`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180060f90`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180060f90`

## pseudocode

```c
__int64 __fastcall CipEnableJournalingAlways(struct _FILE_OBJECT *a1)
{
  struct _UNICODE_STRING *p_Name; // rdi
  __int64 v2; // r15
  int v3; // r14d
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  struct _DEVICE_OBJECT *DeviceAttachmentBaseRef; // rsi
  NTSTATUS v6; // ebx
  struct _OBJECT_NAME_INFORMATION *Pool2; // rax
  __int64 ProcessServerSilo; // rax
  ULONG ReturnLength; // [rsp+60h] [rbp-69h] BYREF
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+68h] [rbp-61h] BYREF
  void *FileHandle; // [rsp+70h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-21h] BYREF
  _QWORD InputBuffer[2]; // [rsp+B8h] [rbp-11h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+C8h] [rbp-1h] BYREF

  FileHandle = 0;
  DiskDeviceObject = 0;
  p_Name = 0;
  ReturnLength = 0;
  IoStatusBlock = 0;
  v2 = 0;
  v3 = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  InputBuffer[0] = 0;
  InputBuffer[1] = 0;
  memset(&ObjectAttributes, 0, 44);
  RelatedDeviceObject = IoGetRelatedDeviceObject(a1);
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(RelatedDeviceObject);
  v6 = IoGetDiskDeviceObject(DeviceAttachmentBaseRef, &DiskDeviceObject);
  if ( v6 >= 0 )
  {
    v6 = ObQueryNameString(DiskDeviceObject, 0, 0, &ReturnLength);
    if ( (int)(v6 + 0x80000000) < 0 || v6 == -1073741820 )
    {
      Pool2 = (struct _OBJECT_NAME_INFORMATION *)ExAllocatePool2(256, ReturnLength, 1668499779);
      p_Name = &Pool2->Name;
      if ( Pool2 )
      {
        v6 = ObQueryNameString(DiskDeviceObject, Pool2, ReturnLength, &ReturnLength);
        if ( v6 >= 0 )
        {
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 512;
          ObjectAttributes.ObjectName = p_Name;
          ProcessServerSilo = PsGetProcessServerSilo(g_CiSystemProcess);
          v2 = PsAttachSiloToCurrentThread(ProcessServerSilo);
          KeStackAttachProcess(g_CiSystemProcess, &ApcState);
          v3 = 1;
          v6 = ZwCreateFile(&FileHandle, 3u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
          if ( v6 >= 0 )
            v6 = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900E7u, InputBuffer, 0x10u, 0, 0);
        }
      }
      else
      {
        v6 = -1073741801;
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v3 )
  {
    KeUnstackDetachProcess(&ApcState);
    PsDetachSiloFromCurrentThread(v2);
  }
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
  if ( DeviceAttachmentBaseRef )
    ObfDereferenceObject(DeviceAttachmentBaseRef);
  if ( p_Name )
    ExFreePoolWithTag(p_Name, 0x63734943u);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180060d48  mov     [rsp-8+arg_8], rbx
0x180060d4d  mov     [rsp-8+arg_10], rsi
0x180060d52  push    rbp
0x180060d53  push    rdi
0x180060d54  push    r12
0x180060d56  push    r14
0x180060d58  push    r15
0x180060d5a  lea     rbp, [rsp-37h]
0x180060d5f  sub     rsp, 100h
0x180060d66  mov     rax, cs:__security_cookie
0x180060d6d  xor     rax, rsp
0x180060d70  mov     [rbp+57h+var_28], rax
0x180060d74  xor     r12d, r12d
0x180060d77  xorps   xmm0, xmm0
0x180060d7a  xorps   xmm1, xmm1
0x180060d7d  mov     [rbp+57h+FileHandle], r12
0x180060d81  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180060d85  xor     eax, eax
0x180060d87  mov     [rbp+57h+DiskDeviceObject], r12
0x180060d8b  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180060d8f  mov     edi, r12d
0x180060d92  mov     [rbp+57h+ReturnLength], r12d
0x180060d96  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180060d9a  mov     r15d, r12d
0x180060d9d  mov     r14d, r12d
0x180060da0  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm1
0x180060da4  mov     [rbp+57h+InputBuffer], r12
0x180060da8  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm1
0x180060dac  mov     [rbp+57h+var_60], r12
0x180060db0  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm1
0x180060db4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180060db8  call    cs:__imp_IoGetRelatedDeviceObject
0x180060dbf  nop     dword ptr [rax+rax+00h]
0x180060dc4  mov     rcx, rax; DeviceObject
0x180060dc7  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x180060dce  nop     dword ptr [rax+rax+00h]
0x180060dd3  mov     rcx, rax; FileSystemDeviceObject
0x180060dd6  lea     rdx, [rbp+57h+DiskDeviceObject]; DiskDeviceObject
0x180060dda  mov     rsi, rax
0x180060ddd  call    cs:__imp_IoGetDiskDeviceObject
0x180060de4  nop     dword ptr [rax+rax+00h]
0x180060de9  mov     ebx, eax
0x180060deb  test    eax, eax
0x180060ded  js      loc_180060F63
0x180060df3  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x180060df7  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x180060dfb  xor     r8d, r8d; Length
0x180060dfe  xor     edx, edx; ObjectNameInfo
0x180060e00  call    cs:__imp_ObQueryNameString
0x180060e07  nop     dword ptr [rax+rax+00h]
0x180060e0c  mov     ecx, 80000000h
0x180060e11  mov     ebx, eax
0x180060e13  add     eax, ecx
0x180060e15  test    ecx, eax
0x180060e17  jnz     short loc_180060E25
0x180060e19  cmp     ebx, 0C0000004h
0x180060e1f  jnz     loc_180060F63
0x180060e25  mov     edx, [rbp+57h+ReturnLength]
0x180060e28  mov     ecx, 100h
0x180060e2d  mov     r8d, 63734943h
0x180060e33  call    cs:__imp_ExAllocatePool2
0x180060e3a  nop     dword ptr [rax+rax+00h]
0x180060e3f  mov     rdi, rax
0x180060e42  test    rax, rax
0x180060e45  jnz     short loc_180060E51
0x180060e47  mov     ebx, 0C0000017h
0x180060e4c  jmp     loc_180060F63
0x180060e51  mov     r8d, [rbp+57h+ReturnLength]; Length
0x180060e55  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x180060e59  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x180060e5d  mov     rdx, rdi; ObjectNameInfo
0x180060e60  call    cs:__imp_ObQueryNameString
0x180060e67  nop     dword ptr [rax+rax+00h]
0x180060e6c  mov     ebx, eax
0x180060e6e  test    eax, eax
0x180060e70  js      loc_180060F63
0x180060e76  mov     rcx, cs:g_CiSystemProcess
0x180060e7d  xorps   xmm0, xmm0
0x180060e80  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180060e85  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180060e8c  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180060e90  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x180060e97  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x180060e9b  call    cs:__imp_PsGetProcessServerSilo
0x180060ea2  nop     dword ptr [rax+rax+00h]
0x180060ea7  mov     rcx, rax
0x180060eaa  call    cs:__imp_PsAttachSiloToCurrentThread
0x180060eb1  nop     dword ptr [rax+rax+00h]
0x180060eb6  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180060ebd  lea     rdx, [rbp+57h+ApcState]; ApcState
0x180060ec1  mov     r15, rax
0x180060ec4  call    cs:__imp_KeStackAttachProcess
0x180060ecb  nop     dword ptr [rax+rax+00h]
0x180060ed0  mov     [rsp+120h+EaLength], r12d; EaLength
0x180060ed5  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180060ed9  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x180060ede  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180060ee2  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x180060ee7  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180060eeb  mov     r14d, 1
0x180060ef1  mov     [rsp+120h+CreateDisposition], r14d; CreateDisposition
0x180060ef6  lea     edx, [r14+2]; DesiredAccess
0x180060efa  mov     [rsp+120h+ShareAccess], edx; ShareAccess
0x180060efe  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x180060f06  mov     [rsp+120h+AllocationSize], r12; AllocationSize
0x180060f0b  call    cs:__imp_ZwCreateFile
0x180060f12  nop     dword ptr [rax+rax+00h]
0x180060f17  mov     ebx, eax
0x180060f19  test    eax, eax
0x180060f1b  js      short loc_180060F63
0x180060f1d  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180060f21  lea     rax, [rbp+57h+InputBuffer]
0x180060f25  mov     dword ptr [rsp+120h+EaBuffer], r12d; OutputBufferLength
0x180060f2a  xor     r9d, r9d; ApcContext
0x180060f2d  mov     qword ptr [rsp+120h+CreateOptions], r12; OutputBuffer
0x180060f32  xor     r8d, r8d; ApcRoutine
0x180060f35  mov     [rsp+120h+CreateDisposition], 10h; InputBufferLength
0x180060f3d  xor     edx, edx; Event
0x180060f3f  mov     qword ptr [rsp+120h+ShareAccess], rax; InputBuffer
0x180060f44  lea     rax, [rbp+57h+IoStatusBlock]
0x180060f48  mov     [rsp+120h+FileAttributes], 900E7h; FsControlCode
0x180060f50  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x180060f55  call    cs:__imp_ZwFsControlFile
0x180060f5c  nop     dword ptr [rax+rax+00h]
0x180060f61  mov     ebx, eax
0x180060f63  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180060f67  test    rcx, rcx
0x180060f6a  jz      short loc_180060F78
0x180060f6c  call    cs:__imp_ZwClose
0x180060f73  nop     dword ptr [rax+rax+00h]
0x180060f78  test    r14d, r14d
0x180060f7b  jz      short loc_180060F9C
0x180060f7d  lea     rcx, [rbp+57h+ApcState]; ApcState
0x180060f81  call    cs:__imp_KeUnstackDetachProcess
0x180060f88  nop     dword ptr [rax+rax+00h]
0x180060f8d  mov     rcx, r15
0x180060f90  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180060f97  nop     dword ptr [rax+rax+00h]
0x180060f9c  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x180060fa0  test    rcx, rcx
0x180060fa3  jz      short loc_180060FB1
0x180060fa5  call    cs:__imp_ObfDereferenceObject
0x180060fac  nop     dword ptr [rax+rax+00h]
0x180060fb1  test    rsi, rsi
0x180060fb4  jz      short loc_180060FC5
0x180060fb6  mov     rcx, rsi; Object
0x180060fb9  call    cs:__imp_ObfDereferenceObject
0x180060fc0  nop     dword ptr [rax+rax+00h]
0x180060fc5  test    rdi, rdi
0x180060fc8  jz      short loc_180060FDE
0x180060fca  mov     edx, 63734943h; Tag
0x180060fcf  mov     rcx, rdi; P
0x180060fd2  call    cs:__imp_ExFreePoolWithTag
0x180060fd9  nop     dword ptr [rax+rax+00h]
0x180060fde  mov     eax, ebx
0x180060fe0  mov     rcx, [rbp+57h+var_28]
0x180060fe4  xor     rcx, rsp; StackCookie
0x180060fe7  call    __security_check_cookie
0x180060fec  lea     r11, [rsp+120h+var_20]
0x180060ff4  mov     rbx, [r11+38h]
0x180060ff8  mov     rsi, [r11+40h]
0x180060ffc  mov     rsp, r11
0x180060fff  pop     r15
0x180061001  pop     r14
0x180061003  pop     r12
0x180061005  pop     rdi
0x180061006  pop     rbp
0x180061007  retn
```
