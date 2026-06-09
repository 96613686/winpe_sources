# SecEnableJournaling

- ea: `0x1400283a0`
- end: `0x140028640`
- name: `SecEnableJournaling`
- size: `672`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140029ac0`

## callees

- `0x140009b80`
- `0x140011610`
- `0x140011650`
- `0x1400283a0`

## import_xrefs

- `ntoskrnl!PsInitialSystemProcess` at `0x1400284e3`
- `ntoskrnl!ZwFsControlFile` at `0x1400285a1`
- `ntoskrnl!ZwFsControlFile` at `0x1400285a1`
- `ntoskrnl!ObQueryNameString` at `0x140028454`
- `ntoskrnl!ObQueryNameString` at `0x1400284cd`
- `ntoskrnl!ObQueryNameString` at `0x140028454`
- `ntoskrnl!ObQueryNameString` at `0x1400284cd`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x140028431`
- `ntoskrnl!IoGetDiskDeviceObject` at `0x140028431`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14002841b`
- `ntoskrnl!IoGetDeviceAttachmentBaseRef` at `0x14002841b`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400285cd`
- `ntoskrnl!KeUnstackDetachProcess` at `0x1400285cd`
- `ntoskrnl!KeStackAttachProcess` at `0x1400284f1`
- `ntoskrnl!KeStackAttachProcess` at `0x1400284f1`
- `ntoskrnl!ZwCreateFile` at `0x140028557`
- `ntoskrnl!ZwCreateFile` at `0x140028557`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002840c`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14002840c`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400284a0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x1400284a0`
- `ntoskrnl!ZwClose` at `0x1400285b8`
- `ntoskrnl!ZwClose` at `0x1400285b8`
- `ntoskrnl!ObfDereferenceObject` at `0x1400285e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400285f6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400285e2`
- `ntoskrnl!ObfDereferenceObject` at `0x1400285f6`

## pseudocode

```c
__int64 __fastcall SecEnableJournaling(struct _FILE_OBJECT *a1)
{
  struct _UNICODE_STRING *p_Name; // rdi
  char v2; // r14
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rax
  struct _DEVICE_OBJECT *DeviceAttachmentBaseRef; // rsi
  NTSTATUS v5; // ebx
  struct _OBJECT_NAME_INFORMATION *PoolWithTag; // rax
  ULONG ReturnLength; // [rsp+68h] [rbp-59h] BYREF
  PDEVICE_OBJECT DiskDeviceObject; // [rsp+70h] [rbp-51h] BYREF
  void *FileHandle; // [rsp+78h] [rbp-49h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-41h] BYREF
  _QWORD InputBuffer[2]; // [rsp+B0h] [rbp-11h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C0h] [rbp-1h] BYREF
  struct _KAPC_STATE ApcState; // [rsp+D0h] [rbp+Fh] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  DiskDeviceObject = 0;
  p_Name = 0;
  memset(&ApcState, 0, sizeof(ApcState));
  ReturnLength = 0;
  v2 = 0;
  InputBuffer[0] = 0;
  InputBuffer[1] = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RelatedDeviceObject = IoGetRelatedDeviceObject(a1);
  DeviceAttachmentBaseRef = IoGetDeviceAttachmentBaseRef(RelatedDeviceObject);
  v5 = IoGetDiskDeviceObject(DeviceAttachmentBaseRef, &DiskDeviceObject);
  if ( v5 >= 0 )
  {
    v5 = ObQueryNameString(DiskDeviceObject, 0, 0, &ReturnLength);
    if ( (int)(v5 + 0x80000000) < 0 || v5 == -1073741820 )
    {
      if ( qword_140020008 )
        PoolWithTag = (struct _OBJECT_NAME_INFORMATION *)qword_140020008(256, ReturnLength, 1853252435);
      else
        PoolWithTag = (struct _OBJECT_NAME_INFORMATION *)ExAllocatePoolWithTag(PagedPool, ReturnLength, 0x6E766353u);
      p_Name = &PoolWithTag->Name;
      if ( PoolWithTag )
      {
        v5 = ObQueryNameString(DiskDeviceObject, PoolWithTag, ReturnLength, &ReturnLength);
        if ( v5 >= 0 )
        {
          KeStackAttachProcess(PsInitialSystemProcess, &ApcState);
          v2 = 1;
          ObjectAttributes.Length = 48;
          ObjectAttributes.RootDirectory = 0;
          ObjectAttributes.Attributes = 512;
          ObjectAttributes.ObjectName = p_Name;
          *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
          v5 = ZwCreateFile(&FileHandle, 3u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0, 0, 0);
          if ( v5 >= 0 )
            v5 = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900E7u, InputBuffer, 0x10u, 0, 0);
        }
      }
      else
      {
        v5 = -1073741801;
      }
    }
  }
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( v2 )
    KeUnstackDetachProcess(&ApcState);
  if ( DiskDeviceObject )
    ObfDereferenceObject(DiskDeviceObject);
  if ( DeviceAttachmentBaseRef )
    ObfDereferenceObject(DeviceAttachmentBaseRef);
  if ( p_Name )
    SecFreePool(p_Name, 0x6E766353u);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1400283a0  mov     rax, rsp
0x1400283a3  mov     [rax+10h], rbx
0x1400283a7  mov     [rax+18h], rsi
0x1400283ab  mov     [rax+20h], rdi
0x1400283af  push    rbp
0x1400283b0  push    r14
0x1400283b2  push    r15
0x1400283b4  lea     rbp, [rax-5Fh]
0x1400283b8  sub     rsp, 100h
0x1400283bf  mov     rax, cs:__security_cookie
0x1400283c6  xor     rax, rsp
0x1400283c9  mov     [rbp+57h+var_18], rax
0x1400283cd  xor     r15d, r15d
0x1400283d0  xorps   xmm0, xmm0
0x1400283d3  xorps   xmm1, xmm1
0x1400283d6  mov     [rbp+57h+FileHandle], r15
0x1400283da  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1400283de  mov     [rbp+57h+DiskDeviceObject], r15
0x1400283e2  mov     edi, r15d
0x1400283e5  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink], xmm1
0x1400283e9  mov     [rbp+57h+ReturnLength], r15d
0x1400283ed  mov     r14b, r15b
0x1400283f0  movups  xmmword ptr [rbp+57h+ApcState.ApcListHead.Flink+10h], xmm1
0x1400283f4  mov     [rbp+57h+InputBuffer], r15
0x1400283f8  movups  xmmword ptr [rbp+57h+ApcState.Process], xmm1
0x1400283fc  mov     [rbp+57h+var_60], r15
0x140028400  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x140028404  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x140028408  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002840c  call    cs:__imp_IoGetRelatedDeviceObject
0x140028413  nop     dword ptr [rax+rax+00h]
0x140028418  mov     rcx, rax; DeviceObject
0x14002841b  call    cs:__imp_IoGetDeviceAttachmentBaseRef
0x140028422  nop     dword ptr [rax+rax+00h]
0x140028427  mov     rcx, rax; FileSystemDeviceObject
0x14002842a  lea     rdx, [rbp+57h+DiskDeviceObject]; DiskDeviceObject
0x14002842e  mov     rsi, rax
0x140028431  call    cs:__imp_IoGetDiskDeviceObject
0x140028438  nop     dword ptr [rax+rax+00h]
0x14002843d  mov     ebx, eax
0x14002843f  test    eax, eax
0x140028441  js      loc_1400285AF
0x140028447  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x14002844b  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x14002844f  xor     r8d, r8d; Length
0x140028452  xor     edx, edx; ObjectNameInfo
0x140028454  call    cs:__imp_ObQueryNameString
0x14002845b  nop     dword ptr [rax+rax+00h]
0x140028460  mov     ecx, 80000000h
0x140028465  mov     ebx, eax
0x140028467  add     eax, ecx
0x140028469  test    ecx, eax
0x14002846b  jnz     short loc_140028479
0x14002846d  cmp     ebx, 0C0000004h
0x140028473  jnz     loc_1400285AF
0x140028479  mov     rax, cs:qword_140020008
0x140028480  mov     r8d, 6E766353h; Tag
0x140028486  mov     edx, [rbp+57h+ReturnLength]; NumberOfBytes
0x140028489  test    rax, rax
0x14002848c  jz      short loc_14002849B
0x14002848e  mov     ecx, 100h
0x140028493  call    cs:__guard_dispatch_icall_fptr
0x140028499  jmp     short loc_1400284AC
0x14002849b  mov     ecx, 1; PoolType
0x1400284a0  call    cs:__imp_ExAllocatePoolWithTag
0x1400284a7  nop     dword ptr [rax+rax+00h]
0x1400284ac  mov     rdi, rax
0x1400284af  test    rax, rax
0x1400284b2  jnz     short loc_1400284BE
0x1400284b4  mov     ebx, 0C0000017h
0x1400284b9  jmp     loc_1400285AF
0x1400284be  mov     r8d, [rbp+57h+ReturnLength]; Length
0x1400284c2  lea     r9, [rbp+57h+ReturnLength]; ReturnLength
0x1400284c6  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x1400284ca  mov     rdx, rdi; ObjectNameInfo
0x1400284cd  call    cs:__imp_ObQueryNameString
0x1400284d4  nop     dword ptr [rax+rax+00h]
0x1400284d9  mov     ebx, eax
0x1400284db  test    eax, eax
0x1400284dd  js      loc_1400285AF
0x1400284e3  mov     rcx, cs:__imp_PsInitialSystemProcess
0x1400284ea  lea     rdx, [rbp+57h+ApcState]; ApcState
0x1400284ee  mov     rcx, [rcx]; PROCESS
0x1400284f1  call    cs:__imp_KeStackAttachProcess
0x1400284f8  nop     dword ptr [rax+rax+00h]
0x1400284fd  mov     [rsp+110h+EaLength], r15d; EaLength
0x140028502  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140028506  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x14002850b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002850f  mov     [rsp+110h+CreateOptions], r15d; CreateOptions
0x140028514  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140028518  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x140028520  mov     edx, 3; DesiredAccess
0x140028525  mov     [rsp+110h+ShareAccess], edx; ShareAccess
0x140028529  xorps   xmm0, xmm0
0x14002852c  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x140028534  mov     r14b, 1
0x140028537  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x14002853c  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140028543  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x140028547  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14002854e  mov     [rbp+57h+ObjectAttributes.ObjectName], rdi
0x140028552  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140028557  call    cs:__imp_ZwCreateFile
0x14002855e  nop     dword ptr [rax+rax+00h]
0x140028563  mov     ebx, eax
0x140028565  test    eax, eax
0x140028567  js      short loc_1400285AF
0x140028569  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002856d  lea     rax, [rbp+57h+InputBuffer]
0x140028571  mov     dword ptr [rsp+110h+EaBuffer], r15d; OutputBufferLength
0x140028576  xor     r9d, r9d; ApcContext
0x140028579  mov     qword ptr [rsp+110h+CreateOptions], r15; OutputBuffer
0x14002857e  xor     r8d, r8d; ApcRoutine
0x140028581  mov     [rsp+110h+CreateDisposition], 10h; InputBufferLength
0x140028589  xor     edx, edx; Event
0x14002858b  mov     qword ptr [rsp+110h+ShareAccess], rax; InputBuffer
0x140028590  lea     rax, [rbp+57h+IoStatusBlock]
0x140028594  mov     [rsp+110h+FileAttributes], 900E7h; FsControlCode
0x14002859c  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x1400285a1  call    cs:__imp_ZwFsControlFile
0x1400285a8  nop     dword ptr [rax+rax+00h]
0x1400285ad  mov     ebx, eax
0x1400285af  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1400285b3  test    rcx, rcx
0x1400285b6  jz      short loc_1400285C4
0x1400285b8  call    cs:__imp_ZwClose
0x1400285bf  nop     dword ptr [rax+rax+00h]
0x1400285c4  test    r14b, r14b
0x1400285c7  jz      short loc_1400285D9
0x1400285c9  lea     rcx, [rbp+57h+ApcState]; ApcState
0x1400285cd  call    cs:__imp_KeUnstackDetachProcess
0x1400285d4  nop     dword ptr [rax+rax+00h]
0x1400285d9  mov     rcx, [rbp+57h+DiskDeviceObject]; Object
0x1400285dd  test    rcx, rcx
0x1400285e0  jz      short loc_1400285EE
0x1400285e2  call    cs:__imp_ObfDereferenceObject
0x1400285e9  nop     dword ptr [rax+rax+00h]
0x1400285ee  test    rsi, rsi
0x1400285f1  jz      short loc_140028602
0x1400285f3  mov     rcx, rsi; Object
0x1400285f6  call    cs:__imp_ObfDereferenceObject
0x1400285fd  nop     dword ptr [rax+rax+00h]
0x140028602  test    rdi, rdi
0x140028605  jz      short loc_140028614
0x140028607  mov     edx, 6E766353h; Tag
0x14002860c  mov     rcx, rdi; P
0x14002860f  call    SecFreePool
0x140028614  mov     eax, ebx
0x140028616  mov     rcx, [rbp+57h+var_18]
0x14002861a  xor     rcx, rsp; StackCookie
0x14002861d  call    __security_check_cookie
0x140028622  lea     r11, [rsp+110h+var_10]
0x14002862a  mov     rbx, [r11+28h]
0x14002862e  mov     rsi, [r11+30h]
0x140028632  mov     rdi, [r11+38h]
0x140028636  mov     rsp, r11
0x140028639  pop     r15
0x14002863b  pop     r14
0x14002863d  pop     rbp
0x14002863e  retn
```
