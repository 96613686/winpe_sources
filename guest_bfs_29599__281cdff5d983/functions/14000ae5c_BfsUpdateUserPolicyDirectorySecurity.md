# BfsUpdateUserPolicyDirectorySecurity

- ea: `0x14000ae5c`
- end: `0x14000b0ca`
- name: `BfsUpdateUserPolicyDirectorySecurity`
- size: `622`
- prototype: `__int64 __fastcall(HANDLE Handle, PUNICODE_STRING FileName)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x14000abe0`

## callees

- `0x140001008`
- `0x14000ae5c`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000af47`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000af47`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000afd6`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000b06f`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000afd6`
- `ntoskrnl!ZwSetSecurityObject` at `0x14000b06f`
- `ntoskrnl!ZwOpenFile` at `0x14000afb4`
- `ntoskrnl!ZwOpenFile` at `0x14000afb4`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000af65`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000af65`
- `ntoskrnl!ZwClose` at `0x14000afec`
- `ntoskrnl!ZwClose` at `0x14000b097`
- `ntoskrnl!ZwClose` at `0x14000afec`
- `ntoskrnl!ZwClose` at `0x14000b097`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b082`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b082`
- `ntoskrnl!ExAllocatePool2` at `0x14000aeb9`
- `ntoskrnl!ExAllocatePool2` at `0x14000aeb9`

## pseudocode

```c
__int64 __fastcall BfsUpdateUserPolicyDirectorySecurity(HANDLE Handle, PUNICODE_STRING FileName)
{
  int v4; // ecx
  WCHAR *FileInformation; // rdi
  int v6; // r8d
  int v7; // r9d
  NTSTATUS v8; // ebx
  BOOLEAN RestartScan; // al
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  int IoStatusBlock; // [rsp+20h] [rbp-99h]
  int IoStatusBlocka; // [rsp+20h] [rbp-99h]
  int v16; // [rsp+60h] [rbp-59h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+A0h] [rbp-19h] BYREF
  struct _IO_STATUS_BLOCK v20; // [rsp+B0h] [rbp-9h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v21; // [rsp+C0h] [rbp+7h] BYREF
  int *v22; // [rsp+E0h] [rbp+27h]
  __int64 v23; // [rsp+E8h] [rbp+2Fh]

  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  v20 = 0;
  FileInformation = (WCHAR *)ExAllocatePool2(256, 272, 1316185666);
  if ( !FileInformation )
  {
    v8 = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v16 = -1073741801;
      v22 = &v16;
      v23 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v4, (int)&byte_140016D91, v6, v7, IoStatusBlock, &v21);
    }
    goto LABEL_17;
  }
  for ( RestartScan = 1; ; RestartScan = 0 )
  {
    v8 = ZwQueryDirectoryFile(
           Handle,
           0,
           0,
           0,
           &v20,
           FileInformation,
           0x110u,
           FileNamesInformation,
           1u,
           FileName,
           RestartScan);
    if ( v8 < 0 )
      goto LABEL_9;
    RtlInitUnicodeString(&DestinationString, FileInformation + 6);
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Attributes = 512;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v8 = ZwOpenFile(&FileHandle, 0x1F01FFu, &ObjectAttributes, &v20, 3u, 0x60u);
    if ( v8 < 0 )
      break;
    v8 = ZwSetSecurityObject(FileHandle, 0x17u, gBfsPolicyStorageFileDescriptor);
    if ( v8 < 0 )
      break;
    ZwClose(FileHandle);
    FileHandle = 0;
LABEL_9:
    memset(FileInformation, 0, 0x110u);
    if ( v8 < 0 )
    {
      if ( v8 == -1073741809 || v8 == -2147483642 )
        v8 = ZwSetSecurityObject(Handle, 0x17u, gBfsPolicyStorageDirectoryDescriptor);
      goto LABEL_16;
    }
  }
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v16 = v8;
    v22 = &v16;
    v23 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v10, (int)&byte_140016D91, v11, v12, IoStatusBlocka, &v21);
  }
LABEL_16:
  ExFreePoolWithTag(FileInformation, 0);
LABEL_17:
  if ( FileHandle )
    ZwClose(FileHandle);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000ae5c  mov     [rsp-8+arg_10], rbx
0x14000ae61  mov     [rsp-8+arg_18], rsi
0x14000ae66  push    rbp
0x14000ae67  push    rdi
0x14000ae68  push    r14
0x14000ae6a  lea     rbp, [rsp-47h]
0x14000ae6f  sub     rsp, 100h
0x14000ae76  mov     rax, cs:__security_cookie
0x14000ae7d  xor     rax, rsp
0x14000ae80  mov     [rbp+57h+var_20], rax
0x14000ae84  xorps   xmm0, xmm0
0x14000ae87  mov     [rbp+57h+FileHandle], 0
0x14000ae8f  mov     r14, rdx
0x14000ae92  mov     rsi, rcx
0x14000ae95  mov     edx, 110h
0x14000ae9a  xor     eax, eax
0x14000ae9c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14000aea0  mov     r8d, 4E736642h
0x14000aea6  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14000aeaa  lea     ecx, [rdx-10h]
0x14000aead  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14000aeb1  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14000aeb5  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x14000aeb9  call    cs:__imp_ExAllocatePool2
0x14000aec0  nop     dword ptr [rax+rax+00h]
0x14000aec5  mov     rdi, rax
0x14000aec8  test    rax, rax
0x14000aecb  jnz     short loc_14000AF0E
0x14000aecd  mov     eax, cs:dword_140019000
0x14000aed3  mov     ebx, 0C0000017h
0x14000aed8  cmp     eax, 3
0x14000aedb  jbe     loc_14000B08E
0x14000aee1  lea     rax, [rbp+57h+var_B0]
0x14000aee5  mov     [rbp+57h+var_B0], ebx
0x14000aee8  mov     [rbp+57h+var_30], rax
0x14000aeec  lea     rdx, byte_140016D91; int
0x14000aef3  lea     rax, [rbp+57h+var_50]
0x14000aef7  mov     [rbp+57h+var_28], 4
0x14000aeff  mov     [rsp+110h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000af04  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000af09  jmp     loc_14000B08E
0x14000af0e  mov     al, 1
0x14000af10  mov     [rsp+110h+RestartScan], al; RestartScan
0x14000af14  xor     r9d, r9d; ApcContext
0x14000af17  mov     [rsp+110h+FileName], r14; FileName
0x14000af1c  lea     rax, [rbp+57h+var_60]
0x14000af20  mov     [rsp+110h+ReturnSingleEntry], 1; ReturnSingleEntry
0x14000af25  xor     r8d, r8d; ApcRoutine
0x14000af28  mov     [rsp+110h+FileInformationClass], 0Ch; FileInformationClass
0x14000af30  xor     edx, edx; Event
0x14000af32  mov     [rsp+110h+Length], 110h; Length
0x14000af3a  mov     rcx, rsi; FileHandle
0x14000af3d  mov     [rsp+110h+FileInformation], rdi; FileInformation
0x14000af42  mov     [rsp+110h+IoStatusBlock], rax; IoStatusBlock
0x14000af47  call    cs:__imp_ZwQueryDirectoryFile
0x14000af4e  nop     dword ptr [rax+rax+00h]
0x14000af53  mov     ebx, eax
0x14000af55  test    eax, eax
0x14000af57  js      loc_14000B000
0x14000af5d  lea     rdx, [rdi+0Ch]; SourceString
0x14000af61  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14000af65  call    cs:__imp_RtlInitUnicodeString
0x14000af6c  nop     dword ptr [rax+rax+00h]
0x14000af71  lea     rax, [rbp+57h+DestinationString]
0x14000af75  mov     dword ptr [rsp+110h+FileInformation], 60h ; '`'; OpenOptions
0x14000af7d  xorps   xmm0, xmm0
0x14000af80  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14000af84  lea     r9, [rbp+57h+var_60]; IoStatusBlock
0x14000af88  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14000af8f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14000af93  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x14000af97  mov     edx, 1F01FFh; DesiredAccess
0x14000af9c  mov     [rbp+57h+ObjectAttributes.Attributes], 200h
0x14000afa3  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14000afa7  mov     dword ptr [rsp+110h+IoStatusBlock], 3; int
0x14000afaf  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000afb4  call    cs:__imp_ZwOpenFile
0x14000afbb  nop     dword ptr [rax+rax+00h]
0x14000afc0  mov     ebx, eax
0x14000afc2  test    eax, eax
0x14000afc4  js      short loc_14000B01B
0x14000afc6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000afca  lea     r8, gBfsPolicyStorageFileDescriptor; SecurityDescriptor
0x14000afd1  mov     edx, 17h; SecurityInformation
0x14000afd6  call    cs:__imp_ZwSetSecurityObject
0x14000afdd  nop     dword ptr [rax+rax+00h]
0x14000afe2  mov     ebx, eax
0x14000afe4  test    eax, eax
0x14000afe6  js      short loc_14000B01B
0x14000afe8  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000afec  call    cs:__imp_ZwClose
0x14000aff3  nop     dword ptr [rax+rax+00h]
0x14000aff8  mov     [rbp+57h+FileHandle], 0
0x14000b000  xor     edx, edx; Val
0x14000b002  mov     r8d, 110h; Size
0x14000b008  mov     rcx, rdi; void *
0x14000b00b  call    memset
0x14000b010  test    ebx, ebx
0x14000b012  js      short loc_14000B050
0x14000b014  xor     al, al
0x14000b016  jmp     loc_14000AF10
0x14000b01b  mov     eax, cs:dword_140019000
0x14000b021  cmp     eax, 3
0x14000b024  jbe     short loc_14000B07D
0x14000b026  lea     rax, [rbp+57h+var_B0]
0x14000b02a  mov     [rbp+57h+var_B0], ebx
0x14000b02d  mov     [rbp+57h+var_30], rax
0x14000b031  lea     rdx, byte_140016D91; int
0x14000b038  lea     rax, [rbp+57h+var_50]
0x14000b03c  mov     [rbp+57h+var_28], 4
0x14000b044  mov     [rsp+110h+FileInformation], rax; PEVENT_DATA_DESCRIPTOR
0x14000b049  call    _tlgWriteTransfer_EtwWriteTransfer
0x14000b04e  jmp     short loc_14000B07D
0x14000b050  cmp     ebx, 0C000000Fh
0x14000b056  jz      short loc_14000B060
0x14000b058  cmp     ebx, 80000006h
0x14000b05e  jnz     short loc_14000B07D
0x14000b060  lea     r8, gBfsPolicyStorageDirectoryDescriptor; SecurityDescriptor
0x14000b067  mov     edx, 17h; SecurityInformation
0x14000b06c  mov     rcx, rsi; Handle
0x14000b06f  call    cs:__imp_ZwSetSecurityObject
0x14000b076  nop     dword ptr [rax+rax+00h]
0x14000b07b  mov     ebx, eax
0x14000b07d  xor     edx, edx; Tag
0x14000b07f  mov     rcx, rdi; P
0x14000b082  call    cs:__imp_ExFreePoolWithTag
0x14000b089  nop     dword ptr [rax+rax+00h]
0x14000b08e  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14000b092  test    rcx, rcx
0x14000b095  jz      short loc_14000B0A3
0x14000b097  call    cs:__imp_ZwClose
0x14000b09e  nop     dword ptr [rax+rax+00h]
0x14000b0a3  mov     eax, ebx
0x14000b0a5  mov     rcx, [rbp+57h+var_20]
0x14000b0a9  xor     rcx, rsp; StackCookie
0x14000b0ac  call    __security_check_cookie
0x14000b0b1  lea     r11, [rsp+110h+var_10]
0x14000b0b9  mov     rbx, [r11+30h]
0x14000b0bd  mov     rsi, [r11+38h]
0x14000b0c1  mov     rsp, r11
0x14000b0c4  pop     r14
0x14000b0c6  pop     rdi
0x14000b0c7  pop     rbp
0x14000b0c8  retn
```
