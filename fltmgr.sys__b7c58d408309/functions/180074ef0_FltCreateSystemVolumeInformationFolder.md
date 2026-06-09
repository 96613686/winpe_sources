# FltCreateSystemVolumeInformationFolder

- ea: `0x180074ef0`
- end: `0x18007510f`
- name: `FltCreateSystemVolumeInformationFolder`
- size: `543`
- prototype: `NTSTATUS __stdcall(PFLT_INSTANCE Instance)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180083330`

## callees

- `0x180009f20`
- `0x18005d2b0`
- `0x180074ef0`
- `0x180075120`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1800750ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800750d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800750ba`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800750d3`
- `ntoskrnl!ExAllocatePool2` at `0x180074fa8`
- `ntoskrnl!ExAllocatePool2` at `0x180074fa8`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180074fcf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x180074fcf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180074ff9`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x180074ff9`
- `ntoskrnl!ZwClose` at `0x1800750e9`
- `ntoskrnl!ZwClose` at `0x1800750e9`

## pseudocode

```c
NTSTATUS __stdcall FltCreateSystemVolumeInformationFolder(PFLT_INSTANCE Instance)
{
  _FLT_VOLUME *Volume; // r14
  NTSTATUS v3; // ebx
  int v4; // eax
  PVOID v5; // rdi
  wchar_t *Pool2; // rax
  struct _FLT_FILTER *Filter; // rcx
  UNICODE_STRING DestinationString; // [rsp+80h] [rbp-29h] BYREF
  UNICODE_STRING Source; // [rsp+90h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-9h] BYREF
  OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp+7h] BYREF
  PVOID P; // [rsp+110h] [rbp+67h] BYREF
  void *FileHandle; // [rsp+118h] [rbp+6Fh] BYREF
  __int64 v15; // [rsp+120h] [rbp+77h] BYREF

  Volume = Instance->Volume;
  Source.Buffer = L"System Volume Information";
  *(_QWORD *)&Source.Length = 3407922;
  P = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  FileHandle = (void *)-1LL;
  memset(&ObjectAttributes, 0, 44);
  v15 = 0;
  IoStatusBlock = 0;
  v3 = FltpSysVolCreateSecurityDescriptor(&P, &v15);
  v4 = FltpDbgStatus(v3);
  v5 = P;
  if ( v4 >= 0 )
  {
    DestinationString.Length = 0;
    DestinationString.MaximumLength = Volume->DeviceName.Length + Source.Length + 2;
    Pool2 = (wchar_t *)ExAllocatePool2(256, DestinationString.MaximumLength, 1853115718);
    DestinationString.Buffer = Pool2;
    if ( !Pool2 )
    {
      v3 = -1073741670;
      goto LABEL_6;
    }
    RtlCopyUnicodeString(&DestinationString, &Volume->DeviceName);
    DestinationString.Buffer[(unsigned __int64)DestinationString.Length >> 1] = 92;
    DestinationString.Length += 2;
    RtlAppendUnicodeStringToString(&DestinationString, &Source);
    Filter = Instance->Filter;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityDescriptor = v5;
    ObjectAttributes.SecurityQualityOfService = 0;
    v3 = FltCreateFileEx2(
           Filter,
           Instance,
           &FileHandle,
           0,
           0x1E0000u,
           &ObjectAttributes,
           &IoStatusBlock,
           0,
           6u,
           7u,
           3u,
           0x21u,
           0,
           0,
           0x800u,
           0);
    FltpDbgStatus(v3);
  }
  Pool2 = DestinationString.Buffer;
LABEL_6:
  if ( Pool2 )
    ExFreePoolWithTag(Pool2, 0x6E744D46u);
  if ( v5 )
    ExFreePoolWithTag(v5, 0x64734D46u);
  if ( FileHandle != (void *)-1LL )
    ZwClose(FileHandle);
  return v3;
}

```

## disassembly

```asm
0x180074ef0  mov     [rsp-8+arg_18], rbx
0x180074ef5  push    rbp
0x180074ef6  push    rsi
0x180074ef7  push    rdi
0x180074ef8  push    r14
0x180074efa  push    r15
0x180074efc  lea     rbp, [rsp-37h]
0x180074f01  sub     rsp, 0E0h
0x180074f08  mov     r14, [rcx+40h]
0x180074f0c  lea     rax, aSystemVolumeIn; "System Volume Information"
0x180074f13  xorps   xmm0, xmm0
0x180074f16  mov     [rbp+57h+Source.Buffer], rax
0x180074f1a  xor     r15d, r15d
0x180074f1d  mov     qword ptr [rbp+57h+Source.Length], 340032h
0x180074f25  mov     rsi, rcx
0x180074f28  mov     [rbp+57h+P], r15
0x180074f2c  movups  xmmword ptr [rbp+57h+var_50.ObjectName], xmm0
0x180074f30  xor     eax, eax
0x180074f32  mov     qword ptr [rbp+57h+DestinationString.Length], r15
0x180074f36  lea     rdx, [rbp+57h+arg_10]
0x180074f3a  mov     [rbp+57h+DestinationString.Buffer], r15
0x180074f3e  lea     rcx, [rbp+57h+P]
0x180074f42  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x180074f4a  movups  xmmword ptr [rbp+57h+var_50.Length], xmm0
0x180074f4e  mov     [rbp+57h+arg_10], r15
0x180074f52  movups  xmmword ptr [rbp+57h+var_50+1Ch], xmm0
0x180074f56  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x180074f5a  call    FltpSysVolCreateSecurityDescriptor
0x180074f5f  mov     r8d, 79h ; 'y'
0x180074f65  lea     rdx, aMinkernelFsFil_18; "minkernel\\fs\\filtermgr\\filter\\sysvo"...
0x180074f6c  xor     r9d, r9d
0x180074f6f  mov     ecx, eax
0x180074f71  mov     ebx, eax
0x180074f73  call    FltpDbgStatus
0x180074f78  mov     rdi, [rbp+57h+P]
0x180074f7c  test    eax, eax
0x180074f7e  js      loc_1800750A9
0x180074f84  movzx   eax, [rbp+57h+Source.Length]
0x180074f88  mov     ecx, 100h
0x180074f8d  add     ax, 2
0x180074f91  mov     [rbp+57h+DestinationString.Length], r15w
0x180074f96  add     ax, [r14+70h]
0x180074f9b  mov     r8d, 6E744D46h
0x180074fa1  movzx   edx, ax
0x180074fa4  mov     [rbp+57h+DestinationString.MaximumLength], dx
0x180074fa8  call    cs:__imp_ExAllocatePool2
0x180074faf  nop     dword ptr [rax+rax+00h]
0x180074fb4  mov     [rbp+57h+DestinationString.Buffer], rax
0x180074fb8  test    rax, rax
0x180074fbb  jnz     short loc_180074FC7
0x180074fbd  mov     ebx, 0C000009Ah
0x180074fc2  jmp     loc_1800750AD
0x180074fc7  lea     rdx, [r14+70h]; SourceString
0x180074fcb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180074fcf  call    cs:__imp_RtlCopyUnicodeString
0x180074fd6  nop     dword ptr [rax+rax+00h]
0x180074fdb  movzx   ecx, [rbp+57h+DestinationString.Length]
0x180074fdf  lea     rdx, [rbp+57h+Source]; Source
0x180074fe3  mov     rax, [rbp+57h+DestinationString.Buffer]
0x180074fe7  shr     rcx, 1
0x180074fea  mov     word ptr [rax+rcx*2], 5Ch ; '\'
0x180074ff0  lea     rcx, [rbp+57h+DestinationString]; Destination
0x180074ff4  add     [rbp+57h+DestinationString.Length], 2
0x180074ff9  call    cs:__imp_RtlAppendUnicodeStringToString
0x180075000  nop     dword ptr [rax+rax+00h]
0x180075005  mov     rcx, [rsi+48h]; Filter
0x180075009  lea     rax, [rbp+57h+DestinationString]
0x18007500d  mov     [rsp+100h+DriverContext], r15; DriverContext
0x180075012  lea     r8, [rbp+57h+FileHandle]; FileHandle
0x180075016  mov     [rsp+100h+Flags], 800h; Flags
0x18007501e  xor     r9d, r9d; FileObject
0x180075021  mov     [rsp+100h+EaLength], r15d; EaLength
0x180075026  mov     rdx, rsi; Instance
0x180075029  mov     [rsp+100h+EaBuffer], r15; EaBuffer
0x18007502e  mov     [rsp+100h+CreateOptions], 21h ; '!'; CreateOptions
0x180075036  mov     [rsp+100h+CreateDisposition], 3; CreateDisposition
0x18007503e  mov     [rsp+100h+ShareAccess], 7; ShareAccess
0x180075046  mov     [rsp+100h+FileAttributes], 6; FileAttributes
0x18007504e  mov     [rbp+57h+var_50.ObjectName], rax
0x180075052  lea     rax, [rbp+57h+var_60]
0x180075056  mov     [rsp+100h+AllocationSize], r15; AllocationSize
0x18007505b  mov     [rsp+100h+IoStatusBlock], rax; IoStatusBlock
0x180075060  lea     rax, [rbp+57h+var_50]
0x180075064  mov     [rsp+100h+ObjectAttributes], rax; ObjectAttributes
0x180075069  mov     [rsp+100h+DesiredAccess], 1E0000h; DesiredAccess
0x180075071  mov     [rbp+57h+var_50.Length], 30h ; '0'
0x180075078  mov     [rbp+57h+var_50.RootDirectory], r15
0x18007507c  mov     [rbp+57h+var_50.Attributes], 240h
0x180075083  mov     [rbp+57h+var_50.SecurityDescriptor], rdi
0x180075087  mov     [rbp+57h+var_50.SecurityQualityOfService], r15
0x18007508b  call    FltCreateFileEx2
0x180075090  mov     r8d, 0B5h
0x180075096  lea     rdx, aMinkernelFsFil_18; "minkernel\\fs\\filtermgr\\filter\\sysvo"...
0x18007509d  xor     r9d, r9d
0x1800750a0  mov     ecx, eax
0x1800750a2  mov     ebx, eax
0x1800750a4  call    FltpDbgStatus
0x1800750a9  mov     rax, [rbp+57h+DestinationString.Buffer]
0x1800750ad  test    rax, rax
0x1800750b0  jz      short loc_1800750C6
0x1800750b2  mov     edx, 6E744D46h; Tag
0x1800750b7  mov     rcx, rax; P
0x1800750ba  call    cs:__imp_ExFreePoolWithTag
0x1800750c1  nop     dword ptr [rax+rax+00h]
0x1800750c6  test    rdi, rdi
0x1800750c9  jz      short loc_1800750DF
0x1800750cb  mov     edx, 64734D46h; Tag
0x1800750d0  mov     rcx, rdi; P
0x1800750d3  call    cs:__imp_ExFreePoolWithTag
0x1800750da  nop     dword ptr [rax+rax+00h]
0x1800750df  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800750e3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800750e7  jz      short loc_1800750F5
0x1800750e9  call    cs:__imp_ZwClose
0x1800750f0  nop     dword ptr [rax+rax+00h]
0x1800750f5  mov     eax, ebx
0x1800750f7  mov     rbx, [rsp+100h+arg_18]
0x1800750ff  add     rsp, 0E0h
0x180075106  pop     r15
0x180075108  pop     r14
0x18007510a  pop     rdi
0x18007510b  pop     rsi
0x18007510c  pop     rbp
0x18007510d  retn
```
