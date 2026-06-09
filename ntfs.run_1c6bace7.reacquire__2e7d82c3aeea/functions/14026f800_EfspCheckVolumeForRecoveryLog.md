# EfspCheckVolumeForRecoveryLog

- ea: `0x14026f800`
- end: `0x14026f9b7`
- name: `EfspCheckVolumeForRecoveryLog`
- size: `439`
- prototype: `KSTART_ROUTINE`
- caller_count: `0`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x1400596c0`
- `0x1400b6d84`
- `0x14026f800`
- `0x140270e84`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x14026f8e8`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x14026f8e8`
- `ntoskrnl!ObfDereferenceObject` at `0x14026f893`
- `ntoskrnl!ObfDereferenceObject` at `0x14026f893`
- `ntoskrnl!ZwClose` at `0x14026f993`
- `ntoskrnl!ZwClose` at `0x14026f993`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1402d0ffc`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x1402d0ffc`
- `ntoskrnl!ZwOpenFile` at `0x14026f945`
- `ntoskrnl!ZwOpenFile` at `0x14026f945`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d0fb7`
- `ntoskrnl!RtlInitUnicodeString` at `0x1402d0fb7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14026f9a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d1018`
- `ntoskrnl!ExFreePoolWithTag` at `0x14026f9a6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402d1018`
- `ntoskrnl!ExAllocatePool2` at `0x14026f857`
- `ntoskrnl!ExAllocatePool2` at `0x14026f96a`
- `ntoskrnl!ExAllocatePool2` at `0x14026f857`
- `ntoskrnl!ExAllocatePool2` at `0x14026f96a`
- `ntoskrnl!PsTerminateSystemThread` at `0x14026f8a1`
- `ntoskrnl!PsTerminateSystemThread` at `0x14026f8a1`

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
0x14026f800  push    rbp
0x14026f802  push    rbx
0x14026f803  push    rsi
0x14026f804  push    rdi
0x14026f805  lea     rbp, [rsp-3Fh]
0x14026f80a  sub     rsp, 0C8h
0x14026f811  mov     [rbp+57h+FileHandle], 0
0x14026f819  xorps   xmm0, xmm0
0x14026f81c  xorps   xmm1, xmm1
0x14026f81f  mov     rdi, rcx
0x14026f822  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14026f826  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x14026f82a  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14026f82e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14026f832  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14026f836  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x14026f83a  test    rcx, rcx
0x14026f83d  jz      loc_14026F987
0x14026f843  mov     esi, 6D736645h
0x14026f848  mov     ebx, 400h
0x14026f84d  mov     r8d, esi
0x14026f850  mov     edx, ebx
0x14026f852  mov     ecx, 100h
0x14026f857  call    cs:__imp_ExAllocatePool2
0x14026f85e  nop     dword ptr [rax+rax+00h]
0x14026f863  mov     [rbp+57h+Destination.Buffer], rax
0x14026f867  test    rax, rax
0x14026f86a  jnz     short loc_14026F8BA
0x14026f86c  mov     ebx, 0C000009Ah
0x14026f871  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14026f875  test    rcx, rcx
0x14026f878  jnz     loc_14026F993
0x14026f87e  mov     rcx, [rbp+57h+Destination.Buffer]; P
0x14026f882  test    rcx, rcx
0x14026f885  jnz     loc_14026F9A4
0x14026f88b  test    rdi, rdi
0x14026f88e  jz      short loc_14026F89F
0x14026f890  mov     rcx, rdi; Object
0x14026f893  call    cs:__imp_ObfDereferenceObject
0x14026f89a  nop     dword ptr [rax+rax+00h]
0x14026f89f  mov     ecx, ebx; ExitStatus
0x14026f8a1  call    cs:__imp_PsTerminateSystemThread
0x14026f8a8  nop     dword ptr [rax+rax+00h]
0x14026f8ad  add     rsp, 0C8h
0x14026f8b4  pop     rdi
0x14026f8b5  pop     rsi
0x14026f8b6  pop     rbx
0x14026f8b7  pop     rbp
0x14026f8b8  retn
0x14026f8ba  mov     r8, rbx; Size
0x14026f8bd  xor     edx, edx; Val
0x14026f8bf  mov     rcx, rax; void *
0x14026f8c2  call    memset
0x14026f8c7  lea     rdx, [rbp+57h+Destination]
0x14026f8cb  mov     [rbp+57h+Destination.MaximumLength], bx
0x14026f8cf  mov     rcx, rdi
0x14026f8d2  call    EfspVolumeGetName
0x14026f8d7  mov     ebx, eax
0x14026f8d9  test    eax, eax
0x14026f8db  js      short loc_14026F871
0x14026f8dd  lea     rdx, aSystemVolumeIn; "\\System Volume Information"
0x14026f8e4  lea     rcx, [rbp+57h+Destination]; Destination
0x14026f8e8  call    cs:__imp_RtlAppendUnicodeToString
0x14026f8ef  nop     dword ptr [rax+rax+00h]
0x14026f8f4  mov     ebx, eax
0x14026f8f6  test    eax, eax
0x14026f8f8  js      loc_14026F871
0x14026f8fe  lea     rax, [rbp+57h+Destination]
0x14026f902  mov     [rsp+0E0h+OpenOptions], 20h ; ' '; OpenOptions
0x14026f90a  xorps   xmm0, xmm0
0x14026f90d  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14026f911  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14026f915  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14026f91c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14026f920  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14026f928  mov     edx, 100021h; DesiredAccess
0x14026f92d  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14026f934  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14026f938  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x14026f940  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14026f945  call    cs:__imp_ZwOpenFile
0x14026f94c  nop     dword ptr [rax+rax+00h]
0x14026f951  mov     ebx, eax
0x14026f953  test    eax, eax
0x14026f955  js      loc_14026F871
0x14026f95b  mov     ebx, 460h
0x14026f960  mov     r8d, esi
0x14026f963  mov     edx, ebx
0x14026f965  mov     ecx, 100h
0x14026f96a  call    cs:__imp_ExAllocatePool2
0x14026f971  nop     dword ptr [rax+rax+00h]
0x14026f976  mov     rsi, rax
0x14026f979  test    rax, rax
0x14026f97c  jz      loc_14026F86C
0x14026f982  jmp     loc_1402D0FAC
0x14026f987  xor     edi, edi
0x14026f989  mov     ebx, 0C000000Dh
0x14026f98e  jmp     loc_14026F87E
0x14026f993  call    cs:__imp_ZwClose
0x14026f99a  nop     dword ptr [rax+rax+00h]
0x14026f99f  jmp     loc_14026F87E
0x14026f9a4  xor     edx, edx; Tag
0x14026f9a6  call    cs:__imp_ExFreePoolWithTag
0x14026f9ad  nop     dword ptr [rax+rax+00h]
0x14026f9b2  jmp     loc_14026F88B
0x1402d0fac  lea     rdx, aEfsLog; "EFS*.LOG"
0x1402d0fb3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1402d0fb7  call    cs:__imp_RtlInitUnicodeString
0x1402d0fbe  nop     dword ptr [rax+rax+00h]
0x1402d0fc3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1402d0fc7  lea     rax, [rbp+57h+DestinationString]
0x1402d0fcb  mov     [rsp+0E0h+RestartScan], 1; RestartScan
0x1402d0fd0  xor     r9d, r9d; ApcContext
0x1402d0fd3  mov     [rsp+0E0h+FileName], rax; FileName
0x1402d0fd8  xor     r8d, r8d; ApcRoutine
0x1402d0fdb  mov     [rsp+0E0h+ReturnSingleEntry], 1; ReturnSingleEntry
0x1402d0fe0  lea     rax, [rbp+57h+IoStatusBlock]
0x1402d0fe4  mov     [rsp+0E0h+FileInformationClass], 3; FileInformationClass
0x1402d0fec  xor     edx, edx; Event
0x1402d0fee  mov     [rsp+0E0h+Length], ebx; Length
0x1402d0ff2  mov     qword ptr [rsp+0E0h+OpenOptions], rsi; FileInformation
0x1402d0ff7  mov     qword ptr [rsp+0E0h+ShareAccess], rax; IoStatusBlock
0x1402d0ffc  call    cs:__imp_ZwQueryDirectoryFile
0x1402d1003  nop     dword ptr [rax+rax+00h]
0x1402d1008  mov     ebx, eax
0x1402d100a  test    eax, eax
0x1402d100c  js      short loc_1402D1013
0x1402d100e  call    EfsTriggerServiceStart
0x1402d1013  xor     edx, edx; Tag
0x1402d1015  mov     rcx, rsi; P
0x1402d1018  call    cs:__imp_ExFreePoolWithTag
0x1402d101f  nop     dword ptr [rax+rax+00h]
0x1402d1024  nop
0x1402d1025  jmp     loc_14026F871
```
