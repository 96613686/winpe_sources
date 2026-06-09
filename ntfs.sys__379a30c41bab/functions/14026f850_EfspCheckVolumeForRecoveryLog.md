# EfspCheckVolumeForRecoveryLog

- ea: `0x14026f850`
- end: `0x14026fa07`
- name: `EfspCheckVolumeForRecoveryLog`
- size: `439`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x140059740`
- `0x1400b6d84`
- `0x14026f850`
- `0x140270ed4`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14026f938`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14026f938`
- `ntoskrnl!ObfDereferenceObject` at `0x14026f8e3`
- `ntoskrnl!ObfDereferenceObject` at `0x14026f8e3`
- `ntoskrnl!ZwClose` at `0x14026f9e3`
- `ntoskrnl!ZwClose` at `0x14026f9e3`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1402d104c`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1402d104c`
- `ntoskrnl!ZwOpenFile` at `0x14026f995`
- `ntoskrnl!ZwOpenFile` at `0x14026f995`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d1007`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d1007`
- `ntoskrnl!ExFreePoolWithTag` at `0x14026f9f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d1068`
- `ntoskrnl!ExFreePoolWithTag` at `0x14026f9f6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d1068`
- `ntoskrnl!ExAllocatePool2` at `0x14026f8a7`
- `ntoskrnl!ExAllocatePool2` at `0x14026f9ba`
- `ntoskrnl!ExAllocatePool2` at `0x14026f8a7`
- `ntoskrnl!ExAllocatePool2` at `0x14026f9ba`
- `ntoskrnl!PsTerminateSystemThread` at `0x14026f8f1`
- `ntoskrnl!PsTerminateSystemThread` at `0x14026f8f1`

## pseudocode

```c
void __fastcall EfspCheckVolumeForRecoveryLog(PVOID StartContext)
{
  PVOID v1; // rdi
  WCHAR *Pool2; // rax
  int Name; // ebx
  void *v4; // rsi
  NTSTATUS v5; // eax
  struct _UNICODE_STRING Destination; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+67h] BYREF

  FileHandle = 0;
  v1 = StartContext;
  DestinationString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Destination = 0;
  if ( !StartContext )
  {
    v1 = 0;
    Name = -1073741811;
    goto LABEL_6;
  }
  Pool2 = (WCHAR *)ExAllocatePool2(256, 1024, 1836279365);
  Destination.Buffer = Pool2;
  if ( !Pool2 )
  {
LABEL_3:
    Name = -1073741670;
    goto LABEL_4;
  }
  memset(Pool2, 0, 0x400u);
  Destination.MaximumLength = 1024;
  Name = EfspVolumeGetName(v1, &Destination);
  if ( Name >= 0 )
  {
    Name = RtlAppendUnicodeToString(&Destination, L"\\System Volume Information");
    if ( Name >= 0 )
    {
      ObjectAttributes.ObjectName = &Destination;
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      Name = ZwOpenFile(&FileHandle, 0x100021u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
      if ( Name >= 0 )
      {
        v4 = (void *)ExAllocatePool2(256, 1120, 1836279365);
        if ( v4 )
        {
          RtlInitUnicodeString(&DestinationString, L"EFS*.LOG");
          v5 = ZwQueryDirectoryFile(
                 FileHandle,
                 0,
                 0,
                 0,
                 &IoStatusBlock,
                 v4,
                 0x460u,
                 FileBothDirectoryInformation,
                 1u,
                 &DestinationString,
                 1u);
          Name = v5;
          if ( v5 >= 0 )
            EfsTriggerServiceStart();
          ExFreePoolWithTag(v4, 0);
          goto LABEL_4;
        }
        goto LABEL_3;
      }
    }
  }
LABEL_4:
  if ( FileHandle )
    ZwClose(FileHandle);
LABEL_6:
  if ( Destination.Buffer )
    ExFreePoolWithTag(Destination.Buffer, 0);
  if ( v1 )
    ObfDereferenceObject(v1);
  PsTerminateSystemThread(Name);
}

```

## disassembly

```asm
0x14026f850  push    rbp
0x14026f852  push    rbx
0x14026f853  push    rsi
0x14026f854  push    rdi
0x14026f855  lea     rbp, [rsp-3Fh]
0x14026f85a  sub     rsp, 0C8h
0x14026f861  mov     [rbp+57h+FileHandle], 0
0x14026f869  xorps   xmm0, xmm0
0x14026f86c  xorps   xmm1, xmm1
0x14026f86f  mov     rdi, rcx
0x14026f872  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14026f876  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x14026f87a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14026f87e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14026f882  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14026f886  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x14026f88a  test    rcx, rcx
0x14026f88d  jz      loc_14026F9D7
0x14026f893  mov     esi, 6D736645h
0x14026f898  mov     ebx, 400h
0x14026f89d  mov     r8d, esi
0x14026f8a0  mov     edx, ebx
0x14026f8a2  mov     ecx, 100h
0x14026f8a7  call    cs:__imp_ExAllocatePool2
0x14026f8ae  nop     dword ptr [rax+rax+00h]
0x14026f8b3  mov     [rbp+57h+Destination.Buffer], rax
0x14026f8b7  test    rax, rax
0x14026f8ba  jnz     short loc_14026F90A
0x14026f8bc  mov     ebx, 0C000009Ah
0x14026f8c1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14026f8c5  test    rcx, rcx
0x14026f8c8  jnz     loc_14026F9E3
0x14026f8ce  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x14026f8d2  test    rcx, rcx
0x14026f8d5  jnz     loc_14026F9F4
0x14026f8db  test    rdi, rdi
0x14026f8de  jz      short loc_14026F8EF
0x14026f8e0  mov     rcx, rdi; Object
0x14026f8e3  call    cs:__imp_ObfDereferenceObject
0x14026f8ea  nop     dword ptr [rax+rax+00h]
0x14026f8ef  mov     ecx, ebx; ExitStatus
0x14026f8f1  call    cs:__imp_PsTerminateSystemThread
0x14026f8f8  nop     dword ptr [rax+rax+00h]
0x14026f8fd  add     rsp, 0C8h
0x14026f904  pop     rdi
0x14026f905  pop     rsi
0x14026f906  pop     rbx
0x14026f907  pop     rbp
0x14026f908  retn
0x14026f90a  mov     r8, rbx; Size
0x14026f90d  xor     edx, edx; Val
0x14026f90f  mov     rcx, rax; void *
0x14026f912  call    memset
0x14026f917  lea     rdx, [rbp+57h+Destination]
0x14026f91b  mov     [rbp+57h+Destination.MaximumLength], bx
0x14026f91f  mov     rcx, rdi
0x14026f922  call    EfspVolumeGetName
0x14026f927  mov     ebx, eax
0x14026f929  test    eax, eax
0x14026f92b  js      short loc_14026F8C1
0x14026f92d  lea     rdx, aSystemVolumeIn; "\\System Volume Information"
0x14026f934  lea     rcx, [rbp+57h+Destination]; Destination
0x14026f938  call    cs:__imp_RtlAppendUnicodeToString
0x14026f93f  nop     dword ptr [rax+rax+00h]
0x14026f944  mov     ebx, eax
0x14026f946  test    eax, eax
0x14026f948  js      loc_14026F8C1
0x14026f94e  lea     rax, [rbp+57h+Destination]
0x14026f952  mov     [rsp+0E0h+OpenOptions], 20h ; ' '; OpenOptions
0x14026f95a  xorps   xmm0, xmm0
0x14026f95d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14026f961  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14026f965  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14026f96c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14026f970  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14026f978  mov     edx, 100021h; DesiredAccess
0x14026f97d  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14026f984  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14026f988  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x14026f990  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14026f995  call    cs:__imp_ZwOpenFile
0x14026f99c  nop     dword ptr [rax+rax+00h]
0x14026f9a1  mov     ebx, eax
0x14026f9a3  test    eax, eax
0x14026f9a5  js      loc_14026F8C1
0x14026f9ab  mov     ebx, 460h
0x14026f9b0  mov     r8d, esi
0x14026f9b3  mov     edx, ebx
0x14026f9b5  mov     ecx, 100h
0x14026f9ba  call    cs:__imp_ExAllocatePool2
0x14026f9c1  nop     dword ptr [rax+rax+00h]
0x14026f9c6  mov     rsi, rax
0x14026f9c9  test    rax, rax
0x14026f9cc  jz      loc_14026F8BC
0x14026f9d2  jmp     loc_1402D0FFC
0x14026f9d7  xor     edi, edi
0x14026f9d9  mov     ebx, 0C000000Dh
0x14026f9de  jmp     loc_14026F8CE
0x14026f9e3  call    cs:__imp_ZwClose
0x14026f9ea  nop     dword ptr [rax+rax+00h]
0x14026f9ef  jmp     loc_14026F8CE
0x14026f9f4  xor     edx, edx; Tag
0x14026f9f6  call    cs:__imp_ExFreePoolWithTag
0x14026f9fd  nop     dword ptr [rax+rax+00h]
0x14026fa02  jmp     loc_14026F8DB
0x1402d0ffc  lea     rdx, aEfsLog; "EFS*.LOG"
0x1402d1003  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1402d1007  call    cs:__imp_RtlInitUnicodeString
0x1402d100e  nop     dword ptr [rax+rax+00h]
0x1402d1013  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1402d1017  lea     rax, [rbp+57h+DestinationString]
0x1402d101b  mov     [rsp+0E0h+RestartScan], 1; RestartScan
0x1402d1020  xor     r9d, r9d; ApcContext
0x1402d1023  mov     [rsp+0E0h+FileName], rax; FileName
0x1402d1028  xor     r8d, r8d; ApcRoutine
0x1402d102b  mov     [rsp+0E0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x1402d1030  lea     rax, [rbp+57h+IoStatusBlock]
0x1402d1034  mov     [rsp+0E0h+FileInformationClass], 3; FileInformationClass
0x1402d103c  xor     edx, edx; Event
0x1402d103e  mov     [rsp+0E0h+Length], ebx; Length
0x1402d1042  mov     qword ptr [rsp+0E0h+OpenOptions], rsi; FileInformation
0x1402d1047  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x1402d104c  call    cs:__imp_ZwQueryDirectoryFile
0x1402d1053  nop     dword ptr [rax+rax+00h]
0x1402d1058  mov     ebx, eax
0x1402d105a  test    eax, eax
0x1402d105c  js      short loc_1402D1063
0x1402d105e  call    EfsTriggerServiceStart
0x1402d1063  xor     edx, edx; Tag
0x1402d1065  mov     rcx, rsi; P
0x1402d1068  call    cs:__imp_ExFreePoolWithTag
0x1402d106f  nop     dword ptr [rax+rax+00h]
0x1402d1074  nop
0x1402d1075  jmp     loc_14026F8C1
```
