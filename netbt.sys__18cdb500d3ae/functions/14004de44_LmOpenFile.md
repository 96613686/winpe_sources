# LmOpenFile

- ea: `0x14004de44`
- end: `0x14004e07e`
- name: `LmOpenFile`
- size: `570`
- prototype: `KSPIN_LOCK *__fastcall(__int64)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14004d4b0`
- `0x14004da30`

## callees

- `0x1400400a4`
- `0x14004de44`
- `0x14004e090`
- `0x14004e8bc`

## import_xrefs

- `ntoskrnl!RtlInitString` at `0x14004dea1`
- `ntoskrnl!RtlInitString` at `0x14004dea1`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14004deb8`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14004deb8`
- `ntoskrnl!ZwClose` at `0x14004e04f`
- `ntoskrnl!ZwClose` at `0x14004e04f`
- `ntoskrnl!ZwCreateFile` at `0x14004df3d`
- `ntoskrnl!ZwCreateFile` at `0x14004df3d`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004df54`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004e014`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004df54`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14004e014`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004dfd3`
- `ntoskrnl!KeInitializeSpinLock` at `0x14004dfd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004df73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e026`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e03f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004df73`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e026`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004e03f`
- `ntoskrnl!ExAllocatePool2` at `0x14004dfbc`
- `ntoskrnl!ExAllocatePool2` at `0x14004dfbc`

## pseudocode

```c
KSPIN_LOCK *__fastcall LmOpenFile(__int64 a1)
{
  NTSTATUS v1; // r14d
  void *v3; // rdi
  KSPIN_LOCK *Pool2; // rax
  KSPIN_LOCK *v5; // rbx
  struct _UNICODE_STRING UnicodeString; // [rsp+60h] [rbp-19h] BYREF
  struct _STRING DestinationString; // [rsp+70h] [rbp-9h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp+7h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp+17h] BYREF
  void *FileHandle; // [rsp+F0h] [rbp+77h] BYREF
  PCSZ SourceString; // [rsp+F8h] [rbp+7Fh] BYREF

  FileHandle = 0;
  SourceString = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  UnicodeString = 0;
  DestinationString = 0;
  if ( (int)LmGetFullPath(a1, &SourceString) < 0 )
    return 0;
  RtlInitString(&DestinationString, SourceString);
  if ( RtlAnsiStringToUnicodeString(&UnicodeString, &DestinationString, 1u) < 0 )
  {
LABEL_6:
    ExFreePoolWithTag((PVOID)SourceString, 0);
    return 0;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &UnicodeString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = ZwCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0x20u, 0, 0);
  if ( v1 < 0 )
  {
LABEL_4:
    RtlFreeUnicodeString(&UnicodeString);
    if ( SBYTE1(xmmword_140038420) < 0 )
      WPP_SF_d(1039, 13, WPP_1dea4ad0a30639a494f955885f716115_Traceguids, (unsigned int)v1);
    goto LABEL_6;
  }
  v3 = (void *)LmpMapFile(FileHandle);
  if ( !v3 )
  {
LABEL_12:
    ZwClose(FileHandle);
    goto LABEL_4;
  }
  Pool2 = (KSPIN_LOCK *)ExAllocatePool2(64, 64, 959537742);
  v5 = Pool2;
  if ( !Pool2 )
  {
    ExFreePoolWithTag(v3, 0);
    goto LABEL_12;
  }
  KeInitializeSpinLock(Pool2);
  *((_DWORD *)v5 + 2) = 1;
  v5[2] = (KSPIN_LOCK)FileHandle;
  *((_DWORD *)v5 + 6) = 0;
  v5[6] = (KSPIN_LOCK)v3;
  v5[4] = 0;
  v5[5] = (KSPIN_LOCK)v3;
  v5[7] = (KSPIN_LOCK)v3;
  RtlFreeUnicodeString(&UnicodeString);
  ExFreePoolWithTag((PVOID)SourceString, 0);
  return v5;
}

```

## disassembly

```asm
0x14004de44  mov     [rsp-8+arg_0], rbx
0x14004de49  push    rbp
0x14004de4a  push    rdi
0x14004de4b  push    r14
0x14004de4d  lea     rbp, [rsp-47h]
0x14004de52  sub     rsp, 0C0h
0x14004de59  xorps   xmm0, xmm0
0x14004de5c  mov     [rbp+57h+FileHandle], 0
0x14004de64  xor     eax, eax
0x14004de66  lea     rdx, [rbp+57h+SourceString]
0x14004de6a  xorps   xmm1, xmm1
0x14004de6d  mov     [rbp+57h+arg_8], eax
0x14004de70  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x14004de74  mov     [rbp+57h+SourceString], rax
0x14004de78  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x14004de7c  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14004de80  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x14004de84  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x14004de88  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x14004de8c  call    LmGetFullPath
0x14004de91  test    eax, eax
0x14004de93  js      loc_14004DF7F
0x14004de99  mov     rdx, [rbp+57h+SourceString]; SourceString
0x14004de9d  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14004dea1  call    cs:__imp_RtlInitString
0x14004dea8  nop     dword ptr [rax+rax+00h]
0x14004dead  mov     r8b, 1; AllocateDestinationString
0x14004deb0  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x14004deb4  lea     rcx, [rbp+57h+UnicodeString]; DestinationString
0x14004deb8  call    cs:__imp_RtlAnsiStringToUnicodeString
0x14004debf  nop     dword ptr [rax+rax+00h]
0x14004dec4  test    eax, eax
0x14004dec6  js      loc_14004DF6D
0x14004decc  mov     [rsp+0D0h+EaLength], 0; EaLength
0x14004ded4  lea     rax, [rbp+57h+UnicodeString]
0x14004ded8  mov     [rsp+0D0h+EaBuffer], 0; EaBuffer
0x14004dee1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14004dee5  mov     [rsp+0D0h+CreateOptions], 20h ; ' '; CreateOptions
0x14004deed  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14004def1  mov     [rsp+0D0h+CreateDisposition], 1; CreateDisposition
0x14004def9  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14004defd  mov     [rsp+0D0h+ShareAccess], 3; ShareAccess
0x14004df05  xorps   xmm0, xmm0
0x14004df08  mov     [rsp+0D0h+FileAttributes], 80h; FileAttributes
0x14004df10  mov     edx, 100001h; DesiredAccess
0x14004df15  mov     [rsp+0D0h+AllocationSize], 0; AllocationSize
0x14004df1e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14004df25  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14004df2d  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14004df34  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14004df38  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14004df3d  call    cs:__imp_ZwCreateFile
0x14004df44  nop     dword ptr [rax+rax+00h]
0x14004df49  mov     r14d, eax
0x14004df4c  test    eax, eax
0x14004df4e  jns     short loc_14004DF96
0x14004df50  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x14004df54  call    cs:__imp_RtlFreeUnicodeString
0x14004df5b  nop     dword ptr [rax+rax+00h]
0x14004df60  cmp     byte ptr cs:xmmword_140038420+1, 0
0x14004df67  jl      loc_14004E060
0x14004df6d  mov     rcx, [rbp+57h+SourceString]; P
0x14004df71  xor     edx, edx; Tag
0x14004df73  call    cs:__imp_ExFreePoolWithTag
0x14004df7a  nop     dword ptr [rax+rax+00h]
0x14004df7f  xor     eax, eax
0x14004df81  mov     rbx, [rsp+0D0h+arg_0]
0x14004df89  add     rsp, 0C0h
0x14004df90  pop     r14
0x14004df92  pop     rdi
0x14004df93  pop     rbp
0x14004df94  retn
0x14004df96  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14004df9a  lea     rdx, [rbp+57h+arg_8]
0x14004df9e  call    LmpMapFile
0x14004dfa3  mov     rdi, rax
0x14004dfa6  test    rax, rax
0x14004dfa9  jz      loc_14004E04B
0x14004dfaf  mov     ecx, 40h ; '@'
0x14004dfb4  mov     r8d, 3931624Eh
0x14004dfba  mov     edx, ecx
0x14004dfbc  call    cs:__imp_ExAllocatePool2
0x14004dfc3  nop     dword ptr [rax+rax+00h]
0x14004dfc8  mov     rbx, rax
0x14004dfcb  test    rax, rax
0x14004dfce  jz      short loc_14004E03A
0x14004dfd0  mov     rcx, rax; SpinLock
0x14004dfd3  call    cs:__imp_KeInitializeSpinLock
0x14004dfda  nop     dword ptr [rax+rax+00h]
0x14004dfdf  mov     dword ptr [rbx+8], 1
0x14004dfe6  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x14004dfea  mov     rdx, [rbp+57h+FileHandle]
0x14004dfee  mov     [rbx+10h], rdx
0x14004dff2  movsxd  rdx, [rbp+57h+arg_8]
0x14004dff6  add     rdx, rdi
0x14004dff9  mov     dword ptr [rbx+18h], 0
0x14004e000  mov     [rbx+30h], rdx
0x14004e004  mov     qword ptr [rbx+20h], 0
0x14004e00c  mov     [rbx+28h], rdi
0x14004e010  mov     [rbx+38h], rdi
0x14004e014  call    cs:__imp_RtlFreeUnicodeString
0x14004e01b  nop     dword ptr [rax+rax+00h]
0x14004e020  mov     rcx, [rbp+57h+SourceString]; P
0x14004e024  xor     edx, edx; Tag
0x14004e026  call    cs:__imp_ExFreePoolWithTag
0x14004e02d  nop     dword ptr [rax+rax+00h]
0x14004e032  mov     rax, rbx
0x14004e035  jmp     loc_14004DF81
0x14004e03a  xor     edx, edx; Tag
0x14004e03c  mov     rcx, rdi; P
0x14004e03f  call    cs:__imp_ExFreePoolWithTag
0x14004e046  nop     dword ptr [rax+rax+00h]
0x14004e04b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14004e04f  call    cs:__imp_ZwClose
0x14004e056  nop     dword ptr [rax+rax+00h]
0x14004e05b  jmp     loc_14004DF50
0x14004e060  mov     edx, 0Dh
0x14004e065  lea     r8, WPP_1dea4ad0a30639a494f955885f716115_Traceguids
0x14004e06c  mov     ecx, 40Fh
0x14004e071  mov     r9d, r14d
0x14004e074  call    WPP_SF_d
0x14004e079  jmp     loc_14004DF6D
```
