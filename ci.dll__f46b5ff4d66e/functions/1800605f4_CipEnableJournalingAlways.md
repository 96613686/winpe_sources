# CipEnableJournalingAlways

- ea: `0x1800605f4`
- end: `0x1800608b5`
- name: `CipEnableJournalingAlways`
- size: `705`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x18009ca38`

## callees

- `0x18002bef0`
- `0x1800605f4`

## import_xrefs

- `ntoskrnl!KeStackAttachProcess` at `0x180060770`
- `ntoskrnl!KeStackAttachProcess` at `0x180060770`
- `ntoskrnl!ExAllocatePool2` at `0x1800606df`
- `ntoskrnl!ExAllocatePool2` at `0x1800606df`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006087e`
- `ntoskrnl!ExFreePoolWithTag` at `0x18006087e`
- `ntoskrnl!ZwClose` at `0x180060818`
- `ntoskrnl!ZwClose` at `0x180060818`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18006082d`
- `ntoskrnl!KeUnstackDetachProcess` at `0x18006082d`
- `ntoskrnl!ObfDereferenceObject` at `0x180060851`
- `ntoskrnl!ObfDereferenceObject` at `0x180060865`
- `ntoskrnl!ObfDereferenceObject` at `0x180060851`
- `ntoskrnl!ObfDereferenceObject` at `0x180060865`
- `ntoskrnl!ZwCreateFile` at `0x1800607b7`
- `ntoskrnl!ZwCreateFile` at `0x1800607b7`
- `ntoskrnl!ZwFsControlFile` at `0x180060801`
- `ntoskrnl!ZwFsControlFile` at `0x180060801`
- `ntoskrnl!PsGetProcessServerSilo` at `0x180060747`
- `ntoskrnl!PsGetProcessServerSilo` at `0x180060747`
- `ntoskrnl!ObQueryNameString` at `0x1800606ac`
- `ntoskrnl!ObQueryNameString` at `0x18006070c`
- `ntoskrnl!ObQueryNameString` at `0x1800606ac`
- `ntoskrnl!ObQueryNameString` at `0x18006070c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180060664`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x180060664`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180060756`
- `ntoskrnl!PsAttachSiloToCurrentThread` at `0x180060756`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180060673`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x180060673`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180060689`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x180060689`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18006083c`
- `ntoskrnl!PsDetachSiloFromCurrentThread` at `0x18006083c`

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
0x1800605f4  mov     [rsp-8+arg_8], rbx
0x1800605f9  mov     [rsp-8+arg_10], rsi
0x1800605fe  push    rbp
0x1800605ff  push    rdi
0x180060600  push    r12
0x180060602  push    r14
0x180060604  push    r15
0x180060606  lea     rbp, [rsp-37h]
0x18006060b  sub     rsp, 100h
0x180060612  mov     rax, cs:__security_cookie
0x180060619  xor     rax, rsp
0x18006061c  mov     [rbp+57h+var_28], rax
0x180060620  xor     r12d, r12d
0x180060623  xorps   xmm0, xmm0
0x180060626  xorps   xmm1, xmm1
0x180060629  mov     [rbp+57h+FileHandle], r12
0x18006062d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180060631  xor     eax, eax
0x180060633  mov     [rbp+57h+DiskDeviceObject], r12
0x180060637  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18006063b  mov     edi, r12d
0x18006063e  mov     [rbp+57h+ReturnLength], r12d
0x180060642  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180060646  mov     r15d, r12d
0x180060649  mov     r14d, r12d
0x18006064c  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm1
0x180060650  mov     [rbp+57h+InputBuffer], r12
0x180060654  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm1
0x180060658  mov     [rbp+57h+var_60], r12
0x18006065c  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm1
0x180060660  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180060664  call    cs:__imp_IoGetRelatedDeviceObject
0x18006066b  nop     dword ptr [rax+rax+00h]
0x180060670  mov     rcx, rax; DeviceObject
0x180060673  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x18006067a  nop     dword ptr [rax+rax+00h]
0x18006067f  mov     rcx, rax; FileSystemDeviceObject
0x180060682  lea     rdx, [rbp+57h+DiskDeviceObject]; DiskDeviceObject
0x180060686  mov     rsi, rax
0x180060689  call    cs:__imp_IoGetDiskDeviceObject
0x180060690  nop     dword ptr [rax+rax+00h]
0x180060695  mov     ebx, eax
0x180060697  test    eax, eax
0x180060699  js      loc_18006080F
0x18006069f  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x1800606a3  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x1800606a7  xor     r8d, r8d; Length
0x1800606aa  xor     edx, edx; ObjectNameInfo
0x1800606ac  call    cs:__imp_ObQueryNameString
0x1800606b3  nop     dword ptr [rax+rax+00h]
0x1800606b8  mov     ecx, 80000000h
0x1800606bd  mov     ebx, eax
0x1800606bf  add     eax, ecx
0x1800606c1  test    ecx, eax
0x1800606c3  jnz     short loc_1800606D1
0x1800606c5  cmp     ebx, 0C0000004h
0x1800606cb  jnz     loc_18006080F
0x1800606d1  mov     edx, [rbp+57h+ReturnLength]
0x1800606d4  mov     ecx, 100h
0x1800606d9  mov     r8d, 63734943h
0x1800606df  call    cs:__imp_ExAllocatePool2
0x1800606e6  nop     dword ptr [rax+rax+00h]
0x1800606eb  mov     rdi, rax
0x1800606ee  test    rax, rax
0x1800606f1  jnz     short loc_1800606FD
0x1800606f3  mov     ebx, 0C0000017h
0x1800606f8  jmp     loc_18006080F
0x1800606fd  mov     r8d, [rbp+57h+ReturnLength]; Length
0x180060701  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x180060705  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x180060709  mov     rdx, rdi; ObjectNameInfo
0x18006070c  call    cs:__imp_ObQueryNameString
0x180060713  nop     dword ptr [rax+rax+00h]
0x180060718  mov     ebx, eax
0x18006071a  test    eax, eax
0x18006071c  js      loc_18006080F
0x180060722  mov     rcx, cs:g_CiSystemProcess
0x180060729  xorps   xmm0, xmm0
0x18006072c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180060731  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180060738  mov     [rbp+57h+ObjectAttributes.RootDirectory], r12
0x18006073c  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x180060743  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x180060747  call    cs:__imp_PsGetProcessServerSilo
0x18006074e  nop     dword ptr [rax+rax+00h]
0x180060753  mov     rcx, rax
0x180060756  call    cs:__imp_PsAttachSiloToCurrentThread
0x18006075d  nop     dword ptr [rax+rax+00h]
0x180060762  mov     rcx, cs:g_CiSystemProcess; PROCESS
0x180060769  lea     rdx, [rbp+57h+ApcState]; ApcState
0x18006076d  mov     r15, rax
0x180060770  call    cs:__imp_KeStackAttachProcess
0x180060777  nop     dword ptr [rax+rax+00h]
0x18006077c  mov     [rsp+120h+EaLength], r12d; EaLength
0x180060781  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180060785  mov     [rsp+120h+EaBuffer], r12; EaBuffer
0x18006078a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006078e  mov     [rsp+120h+CreateOptions], r12d; CreateOptions
0x180060793  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180060797  mov     r14d, 1
0x18006079d  mov     [rsp+120h+CreateDisposition], r14d; CreateDisposition
0x1800607a2  lea     edx, [r14+2]; DesiredAccess
0x1800607a6  mov     [rsp+120h+ShareAccess], edx; ShareAccess
0x1800607aa  mov     [rsp+120h+FileAttributes], 80h; FileAttributes
0x1800607b2  mov     [rsp+120h+AllocationSize], r12; AllocationSize
0x1800607b7  call    cs:__imp_ZwCreateFile
0x1800607be  nop     dword ptr [rax+rax+00h]
0x1800607c3  mov     ebx, eax
0x1800607c5  test    eax, eax
0x1800607c7  js      short loc_18006080F
0x1800607c9  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800607cd  lea     rax, [rbp+57h+InputBuffer]
0x1800607d1  mov     dword ptr [rsp+120h+EaBuffer], r12d; OutputBufferLength
0x1800607d6  xor     r9d, r9d; ApcContext
0x1800607d9  mov     qword ptr [rsp+120h+CreateOptions], r12; OutputBuffer
0x1800607de  xor     r8d, r8d; ApcRoutine
0x1800607e1  mov     [rsp+120h+CreateDisposition], 10h; InputBufferLength
0x1800607e9  xor     edx, edx; Event
0x1800607eb  mov     qword ptr [rsp+120h+ShareAccess], rax; InputBuffer
0x1800607f0  lea     rax, [rbp+57h+IoStatusBlock]
0x1800607f4  mov     [rsp+120h+FileAttributes], 900E7h; FsControlCode
0x1800607fc  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x180060801  call    cs:__imp_ZwFsControlFile
0x180060808  nop     dword ptr [rax+rax+00h]
0x18006080d  mov     ebx, eax
0x18006080f  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180060813  test    rcx, rcx
0x180060816  jz      short loc_180060824
0x180060818  call    cs:__imp_ZwClose
0x18006081f  nop     dword ptr [rax+rax+00h]
0x180060824  test    r14d, r14d
0x180060827  jz      short loc_180060848
0x180060829  lea     rcx, [rbp+57h+ApcState]; ApcState
0x18006082d  call    cs:__imp_KeUnstackDetachProcess
0x180060834  nop     dword ptr [rax+rax+00h]
0x180060839  mov     rcx, r15
0x18006083c  call    cs:__imp_PsDetachSiloFromCurrentThread
0x180060843  nop     dword ptr [rax+rax+00h]
0x180060848  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x18006084c  test    rcx, rcx
0x18006084f  jz      short loc_18006085D
0x180060851  call    cs:__imp_ObfDereferenceObject
0x180060858  nop     dword ptr [rax+rax+00h]
0x18006085d  test    rsi, rsi
0x180060860  jz      short loc_180060871
0x180060862  mov     rcx, rsi; Object
0x180060865  call    cs:__imp_ObfDereferenceObject
0x18006086c  nop     dword ptr [rax+rax+00h]
0x180060871  test    rdi, rdi
0x180060874  jz      short loc_18006088A
0x180060876  mov     edx, 63734943h; Tag
0x18006087b  mov     rcx, rdi; P
0x18006087e  call    cs:__imp_ExFreePoolWithTag
0x180060885  nop     dword ptr [rax+rax+00h]
0x18006088a  mov     eax, ebx
0x18006088c  mov     rcx, [rbp+57h+var_28]
0x180060890  xor     rcx, rsp; StackCookie
0x180060893  call    __security_check_cookie
0x180060898  lea     r11, [rsp+120h+var_20]
0x1800608a0  mov     rbx, [r11+38h]
0x1800608a4  mov     rsi, [r11+40h]
0x1800608a8  mov     rsp, r11
0x1800608ab  pop     r15
0x1800608ad  pop     r14
0x1800608af  pop     r12
0x1800608b1  pop     rdi
0x1800608b2  pop     rbp
0x1800608b3  retn
```
