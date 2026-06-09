# CipEnableJournalingAlways

- ea: `0x180060da8`
- end: `0x180061069`
- name: `CipEnableJournalingAlways`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18009e068`

## callees

- `0x18002bf20`
- `0x180060da8`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x180060f24`
- `ntoskrnl!KeStackAttachProcess` at `0x180060f24`
- `ntoskrnl!ExAllocatePool2` at `0x180060e93`
- `ntoskrnl!ExAllocatePool2` at `0x180060e93`
- `ntoskrnl!ExFreePoolWithTag` at `0x180061032`
- `ntoskrnl!ExFreePoolWithTag` at `0x180061032`
- `ntoskrnl!ZwClose` at `0x180060fcc`
- `ntoskrnl!ZwClose` at `0x180060fcc`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180060fe1`
- `ntoskrnl!KeUnstackDetachProcess` at `0x180060fe1`
- `ntoskrnl!ObfDereferenceObject` at `0x180061005`
- `ntoskrnl!ObfDereferenceObject` at `0x180061019`
- `ntoskrnl!ObfDereferenceObject` at `0x180061005`
- `ntoskrnl!ObfDereferenceObject` at `0x180061019`
- `ntoskrnl!ZwCreateFile` at `0x180060f6b`
- `ntoskrnl!ZwCreateFile` at `0x180060f6b`
- `ntoskrnl!ZwFsControlFile` at `0x180060fb5`
- `ntoskrnl!ZwFsControlFile` at `0x180060fb5`
- `ntoskrnl!PsGetProcessServerSilo` at `0x180060efb`
- `ntoskrnl!PsGetProcessServerSilo` at `0x180060efb`
- `ntoskrnl!ObQueryNameString` at `0x180060e60`
- `ntoskrnl!ObQueryNameString` at `0x180060ec0`
- `ntoskrnl!ObQueryNameString` at `0x180060e60`
- `ntoskrnl!ObQueryNameString` at `0x180060ec0`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180060e18`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180060e18`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180060f0a`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180060f0a`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180060e27`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180060e27`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180060e3d`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180060e3d`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180060ff0`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x180060ff0`

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
0x180060da8  mov     [rsp-8+arg_8], rbx
0x180060dad  mov     [rsp-8+arg_10], rsi
0x180060db2  push    rbp
0x180060db3  push    rdi
0x180060db4  push    r12
0x180060db6  push    r14
0x180060db8  push    r15
0x180060dba  lea     rbp, [rsp-37h]
0x180060dbf  sub     rsp, 100h
0x180060dc6  mov     rax, cs:__security_cookie
0x180060dcd  xor     rax, rsp
0x180060dd0  mov     [rbp+57h+var_28], rax
0x180060dd4  xor     r12d, r12d
0x180060dd7  xorps   xmm0, xmm0
0x180060dda  xorps   xmm1, xmm1
0x180060ddd  mov     [rbp+57h+FileHandle], r12
0x180060de1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180060de5  xor     eax, eax
0x180060de7  mov     [rbp+57h+DiskDeviceObject], r12
0x180060deb  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180060def  mov     edi, r12d
0x180060df2  mov     [rbp+57h+ReturnLength], r12d
0x180060df6  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180060dfa  mov     r15d, r12d
0x180060dfd  mov     r14d, r12d
0x180060e00  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm1
0x180060e04  mov     [rbp+57h+InputBuffer], r12
0x180060e08  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm1
0x180060e0c  mov     [rbp+57h+var_60], r12
0x180060e10  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm1
0x180060e14  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180060e18  call    cs:__imp_IoGetRelatedDeviceObject
0x180060e1f  nop     dword ptr [rax+rax+00h]
0x180060e24  mov     rcx, rax; DeviceObject
0x180060e27  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x180060e2e  nop     dword ptr [rax+rax+00h]
0x180060e33  mov     rcx, rax; FileSystemDeviceObject
0x180060e36  lea     rdx, [rbp+57h+DiskDeviceObject]; DiskDeviceObject
0x180060e3a  mov     rsi, rax
0x180060e3d  call    cs:__imp_IoGetDiskDeviceObject
0x180060e44  nop     dword ptr [rax+rax+00h]
0x180060e49  mov     ebx, eax
0x180060e4b  test    eax, eax
0x180060e4d  js      loc_180060FC3
0x180060e53  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x180060e57  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x180060e5b  xor     r8d, r8d; Length
0x180060e5e  xor     edx, edx; ObjectNameInfo
0x180060e60  call    cs:__imp_ObQueryNameString
0x180060e67  nop     dword ptr [rax+rax+00h]
0x180060e6c  mov     ecx, 80000000h
0x180060e71  mov     ebx, eax
0x180060e73  add     eax, ecx
0x180060e75  test    ecx, eax
0x180060e77  jnz     short loc_180060E85
0x180060e79  cmp     ebx, 0C0000004h
0x180060e7f  jnz     loc_180060FC3
0x180060e85  mov     edx, [rbp+57h+ReturnLength]
0x180060e88  mov     ecx, 100h
0x180060e8d  mov     r8d, 63734943h
0x180060e93  call    cs:__imp_ExAllocatePool2
0x180060e9a  nop     dword ptr [rax+rax+00h]
0x180060e9f  mov     rdi, rax
0x180060ea2  test    rax, rax
0x180060ea5  jnz     short loc_180060EB1
0x180060ea7  mov     ebx, 0C0000017h
0x180060eac  jmp     loc_180060FC3
0x180060eb1  mov     r8d, [rbp+57h+ReturnLength]; Length
0x180060eb5  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x180060eb9  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x180060ebd  mov     rdx, rdi; ObjectNameInfo
0x180060ec0  call    cs:__imp_ObQueryNameString
0x180060ec7  nop     dword ptr [rax+rax+00h]
0x180060ecc  mov     ebx, eax
0x180060ece  test    eax, eax
0x180060ed0  js      loc_180060FC3
0x180060ed6  mov     rcx, cs:g_CiSystemProcess
0x180060edd  xorps   xmm0, xmm0
0x180060ee0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180060ee5  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180060eec  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x180060ef0  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x180060ef7  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x180060efb  call    cs:__imp_PsGetProcessServerSilo
0x180060f02  nop     dword ptr [rax+rax+00h]
0x180060f07  mov     rcx, rax
0x180060f0a  call    cs:__imp_PsAttachSiloToCurrentThread
0x180060f11  nop     dword ptr [rax+rax+00h]
0x180060f16  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180060f1d  lea     rdx, [rbp+57h+ApcState]; ApcState
0x180060f21  mov     r15, rax
0x180060f24  call    cs:__imp_KeStackAttachProcess
0x180060f2b  nop     dword ptr [rax+rax+00h]
0x180060f30  mov     [rsp+120h+EaLength], r12d; EaLength
0x180060f35  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180060f39  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x180060f3e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180060f42  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x180060f47  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180060f4b  mov     r14d, 1
0x180060f51  mov     [rsp+120h+CreateDisposition], r14d; CreateDisposition
0x180060f56  lea     edx, [r14+2]; DesiredAccess
0x180060f5a  mov     [rsp+120h+ShareAccess], edx; ShareAccess
0x180060f5e  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x180060f66  mov     [rsp+120h+AllocationSize], r12; AllocationSize
0x180060f6b  call    cs:__imp_ZwCreateFile
0x180060f72  nop     dword ptr [rax+rax+00h]
0x180060f77  mov     ebx, eax
0x180060f79  test    eax, eax
0x180060f7b  js      short loc_180060FC3
0x180060f7d  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180060f81  lea     rax, [rbp+57h+InputBuffer]
0x180060f85  mov     dword ptr [rsp+120h+EaBuffer], r12d; OutputBufferLength
0x180060f8a  xor     r9d, r9d; ApcContext
0x180060f8d  mov     qword ptr [rsp+120h+CreateOptions], r12; OutputBuffer
0x180060f92  xor     r8d, r8d; ApcRoutine
0x180060f95  mov     [rsp+120h+CreateDisposition], 10h; InputBufferLength
0x180060f9d  xor     edx, edx; Event
0x180060f9f  mov     qword ptr [rsp+120h+ShareAccess], rax; InputBuffer
0x180060fa4  lea     rax, [rbp+57h+IoStatusBlock]
0x180060fa8  mov     [rsp+120h+FileAttributes], 900E7h; FsControlCode
0x180060fb0  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x180060fb5  call    cs:__imp_ZwFsControlFile
0x180060fbc  nop     dword ptr [rax+rax+00h]
0x180060fc1  mov     ebx, eax
0x180060fc3  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180060fc7  test    rcx, rcx
0x180060fca  jz      short loc_180060FD8
0x180060fcc  call    cs:__imp_ZwClose
0x180060fd3  nop     dword ptr [rax+rax+00h]
0x180060fd8  test    r14d, r14d
0x180060fdb  jz      short loc_180060FFC
0x180060fdd  lea     rcx, [rbp+57h+ApcState]; ApcState
0x180060fe1  call    cs:__imp_KeUnstackDetachProcess
0x180060fe8  nop     dword ptr [rax+rax+00h]
0x180060fed  mov     rcx, r15
0x180060ff0  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180060ff7  nop     dword ptr [rax+rax+00h]
0x180060ffc  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x180061000  test    rcx, rcx
0x180061003  jz      short loc_180061011
0x180061005  call    cs:__imp_ObfDereferenceObject
0x18006100c  nop     dword ptr [rax+rax+00h]
0x180061011  test    rsi, rsi
0x180061014  jz      short loc_180061025
0x180061016  mov     rcx, rsi; Object
0x180061019  call    cs:__imp_ObfDereferenceObject
0x180061020  nop     dword ptr [rax+rax+00h]
0x180061025  test    rdi, rdi
0x180061028  jz      short loc_18006103E
0x18006102a  mov     edx, 63734943h; Tag
0x18006102f  mov     rcx, rdi; P
0x180061032  call    cs:__imp_ExFreePoolWithTag
0x180061039  nop     dword ptr [rax+rax+00h]
0x18006103e  mov     eax, ebx
0x180061040  mov     rcx, [rbp+57h+var_28]
0x180061044  xor     rcx, rsp; StackCookie
0x180061047  call    __security_check_cookie
0x18006104c  lea     r11, [rsp+120h+var_20]
0x180061054  mov     rbx, [r11+38h]
0x180061058  mov     rsi, [r11+40h]
0x18006105c  mov     rsp, r11
0x18006105f  pop     r15
0x180061061  pop     r14
0x180061063  pop     r12
0x180061065  pop     rdi
0x180061066  pop     rbp
0x180061067  retn
```
