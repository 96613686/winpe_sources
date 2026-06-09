# CipGetFullImagePathAndMacros

- ea: `0x1800a38fc`
- end: `0x1800a3e04`
- name: `CipGetFullImagePathAndMacros`
- size: `1288`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a3828`

## callees

- `0x18002bf20`
- `0x18002c080`
- `0x18002c380`
- `0x1800a38fc`
- `0x1800dea34`
- `0x1800dec04`
- `0x1800dff0c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a3dad`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a3dad`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3b8f`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a3b8f`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3a71`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3ad4`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3b4d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3cd9`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3a71`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3ad4`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3b4d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3cd9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3abd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3cfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3d6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3dc4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3abd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3cfa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3d27`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3d6c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3dc4`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3a31`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3a31`
- `ntoskrnl!ZwClose` at `0x1800a3d96`
- `ntoskrnl!ZwClose` at `0x1800a3d96`
- `ntoskrnl!IoFileObjectType` at `0x1800a395c`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a3a9b`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a3b08`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a3a9b`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a3b08`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800a399d`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800a399d`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800a39fa`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800a39fa`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800a3d81`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800a3d81`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a39cd`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a3c4c`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a39cd`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a3c4c`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1800a3bcb`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1800a3bcb`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1800a3cad`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1800a3cad`

## pseudocode

```c
__int64 __fastcall CipGetFullImagePathAndMacros(PVOID *Object, __int64 a2)
{
  unsigned __int8 v3; // si
  int MacroPaths; // ebx
  _DWORD *v6; // rdi
  _DWORD *Pool2; // rax
  ULONG v8; // ebx
  _DWORD *v9; // rax
  bool v10; // zf
  struct _UNICODE_STRING v11; // xmm0
  NTSTATUS v12; // eax
  void *v13; // rsi
  NTSTATUS v14; // eax
  __int64 v15; // rbx
  ULONG LengthNeeded; // [rsp+44h] [rbp-55h] BYREF
  HANDLE FileHandle; // [rsp+48h] [rbp-51h] BYREF
  struct _UNICODE_STRING StringOut; // [rsp+50h] [rbp-49h] BYREF
  __int64 FsInformation; // [rsp+60h] [rbp-39h] BYREF
  __int64 v21; // [rsp+68h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-19h] BYREF
  struct _UNICODE_STRING DosName; // [rsp+90h] [rbp-9h] BYREF
  UNICODE_STRING StringIn; // [rsp+A0h] [rbp+7h] BYREF
  __int128 v26; // [rsp+B0h] [rbp+17h] BYREF

  v21 = 0;
  FsInformation = 0;
  FileHandle = 0;
  LengthNeeded = 0;
  v3 = 0;
  IoStatusBlock = 0;
  StringIn = 0;
  DosName = 0;
  StringOut = 0;
  DestinationString = 0;
  v26 = 0;
  MacroPaths = ObOpenObjectByPointer(Object, 0x240u, 0, 0, (POBJECT_TYPE)IoFileObjectType, 0, &FileHandle);
  if ( MacroPaths < 0 )
    goto LABEL_46;
  MacroPaths = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation);
  if ( MacroPaths < 0 )
    goto LABEL_46;
  if ( (FsInformation & 0x1000000000LL) != 0
    || (MacroPaths = FsRtlGetFileNameInformation(Object, 1024, &StringIn, &v21), (FsInformation & 0x1000000000LL) != 0)
    || MacroPaths == -1073741822
    || MacroPaths == -1071906811 )
  {
    Pool2 = (_DWORD *)ExAllocatePool2(256, 528, 1668499779);
    v6 = Pool2;
    if ( Pool2 )
    {
      MacroPaths = ZwQueryInformationFile(FileHandle, &IoStatusBlock, Pool2, 0x210u, FileNameInformation);
      if ( MacroPaths == -2147483643 )
      {
        v8 = *v6 + 8;
        ExFreePoolWithTag(v6, 0x63734943u);
        v9 = (_DWORD *)ExAllocatePool2(256, v8, 1668499779);
        v6 = v9;
        if ( !v9 )
          goto LABEL_13;
        MacroPaths = ZwQueryInformationFile(FileHandle, &IoStatusBlock, v9, v8, FileNameInformation);
      }
      if ( MacroPaths < 0 )
      {
LABEL_45:
        ExFreePoolWithTag(v6, 0x63734943u);
        goto LABEL_46;
      }
      if ( *v6 > 0xFFFDu )
      {
        MacroPaths = -1073741823;
        goto LABEL_44;
      }
      StringOut.Length = *(_WORD *)v6 + 2;
      StringOut.MaximumLength = StringOut.Length;
      StringOut.Buffer = (PWSTR)ExAllocatePool2(258, StringOut.Length, 1919109443);
      if ( !StringOut.Buffer )
      {
        MacroPaths = -1073741801;
        goto LABEL_44;
      }
      *StringOut.Buffer = 92;
      memmove(StringOut.Buffer + 1, v6 + 1, (unsigned int)*v6);
      RtlInitUnicodeString(&DestinationString, 0);
LABEL_21:
      v10 = DestinationString.Buffer == 0;
      v11 = StringOut;
      StringOut.Buffer = 0;
      *(struct _UNICODE_STRING *)(a2 + 944) = v11;
      *(struct _UNICODE_STRING *)(a2 + 808) = v11;
      if ( !v10
        && ((MacroPaths = IoVolumeDeviceToDosName(Object[1], &DosName), MacroPaths < 0)
         || (MacroPaths = SIPolicyPathMacroReplace(
                            (PCUNICODE_STRING)(a2 + 944),
                            &DestinationString,
                            &DosName,
                            (PUNICODE_STRING)(a2 + 864)),
             (int)(MacroPaths + 0x80000000) >= 0)
         && MacroPaths != -1073741811)
        || *(_QWORD *)(a2 + 872) && (MacroPaths = SIPolicyGetMacroPaths((PCUNICODE_STRING)(a2 + 864)), MacroPaths < 0) )
      {
LABEL_44:
        if ( !v6 )
          goto LABEL_46;
        goto LABEL_45;
      }
      v12 = ZwQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &v26, 0x10u, FileFsAttributeInformation);
      if ( v12 >= 0 || v12 == -2147483643 && IoStatusBlock.Information >= 0xC )
      {
        MacroPaths = 0;
        if ( (v26 & 8) == 0 )
        {
LABEL_42:
          v3 = 1;
          goto LABEL_43;
        }
        if ( (FsInformation & 0x1000000000LL) != 0 )
        {
LABEL_43:
          *(_DWORD *)(a2 + 2360) ^= ((unsigned __int16)*(_DWORD *)(a2 + 2360) ^ (unsigned __int16)(v3 << 9)) & 0x200;
          goto LABEL_44;
        }
        v13 = 0;
        while ( 1 )
        {
          memset(v13, 0, (unsigned int)MacroPaths);
          v14 = ZwQuerySecurityObject(FileHandle, 5u, v13, MacroPaths, &LengthNeeded);
          if ( v14 >= 0 )
            break;
          if ( v14 != -2147483643 && v14 != -1073741789 )
            goto LABEL_41;
          v15 = ExAllocatePool2(258, LengthNeeded, 1668499779);
          if ( !v15 )
            goto LABEL_41;
          if ( v13 )
            ExFreePoolWithTag(v13, 0x63734943u);
          v13 = (void *)v15;
          MacroPaths = LengthNeeded;
        }
        MacroPaths = SIPolicyIsSecurityDescriptorUserWriteable(v13);
        ExFreePoolWithTag(v13, 0x63734943u);
        if ( MacroPaths >= 0 )
        {
          v3 = 0;
          goto LABEL_43;
        }
      }
LABEL_41:
      MacroPaths = 0;
      goto LABEL_42;
    }
LABEL_13:
    MacroPaths = -1073741801;
    goto LABEL_46;
  }
  if ( MacroPaths >= 0 )
  {
    MacroPaths = RtlDuplicateUnicodeString(0, &StringIn, &StringOut);
    if ( MacroPaths >= 0 )
    {
      v6 = 0;
      DestinationString = *(struct _UNICODE_STRING *)(v21 + 24);
      goto LABEL_21;
    }
  }
LABEL_46:
  if ( v21 )
    FsRtlReleaseFileNameInformation();
  if ( FileHandle )
    ZwClose(FileHandle);
  if ( StringOut.Buffer )
    RtlFreeUnicodeString(&StringOut);
  if ( DosName.Buffer )
    ExFreePoolWithTag(DosName.Buffer, 0);
  return (unsigned int)MacroPaths;
}

```

## disassembly

```asm
0x1800a38fc  mov     [rsp-8+arg_10], rbx
0x1800a3901  mov     [rsp-8+arg_18], rsi
0x1800a3906  push    rbp
0x1800a3907  push    rdi
0x1800a3908  push    r13
0x1800a390a  push    r14
0x1800a390c  push    r15
0x1800a390e  lea     rbp, [rsp-37h]
0x1800a3913  sub     rsp, 0D0h
0x1800a391a  mov     rax, cs:__security_cookie
0x1800a3921  xor     rax, rsp
0x1800a3924  mov     [rbp+57h+var_30], rax
0x1800a3928  xorps   xmm0, xmm0
0x1800a392b  mov     [rbp+57h+var_88], 0
0x1800a3933  mov     r13, rcx
0x1800a3936  mov     [rbp+57h+FsInformation], 0
0x1800a393e  xorps   xmm1, xmm1
0x1800a3941  mov     [rbp+57h+FileHandle], 0
0x1800a3949  lea     rax, [rbp+57h+FileHandle]
0x1800a394d  mov     [rbp+57h+LengthNeeded], 0
0x1800a3954  mov     [rsp+0F0h+Handle], rax; Handle
0x1800a3959  xor     sil, sil
0x1800a395c  mov     rax, cs:__imp_IoFileObjectType
0x1800a3963  mov     r14, rdx
0x1800a3966  mov     [rsp+0F0h+AccessMode], sil; AccessMode
0x1800a396b  xor     r9d, r9d; DesiredAccess
0x1800a396e  xor     r8d, r8d; PassedAccessState
0x1800a3971  mov     [rbp+57h+var_B0], sil
0x1800a3975  mov     edx, 240h; HandleAttributes
0x1800a397a  mov     rcx, [rax]
0x1800a397d  mov     [rsp+0F0h+ObjectType], rcx; ObjectType
0x1800a3982  mov     rcx, r13; Object
0x1800a3985  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800a3989  movups  xmmword ptr [rbp+57h+StringIn.Length], xmm0
0x1800a398d  movups  xmmword ptr [rbp+57h+DosName.Length], xmm1
0x1800a3991  movups  xmmword ptr [rbp+57h+StringOut.Length], xmm0
0x1800a3995  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800a3999  movups  [rbp+57h+var_40], xmm0
0x1800a399d  call    cs:__imp_ObOpenObjectByPointer
0x1800a39a4  nop     dword ptr [rax+rax+00h]
0x1800a39a9  mov     ebx, eax
0x1800a39ab  test    eax, eax
0x1800a39ad  js      loc_1800A3D78
0x1800a39b3  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a39b7  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x1800a39bb  mov     r9d, 8; Length
0x1800a39c1  mov     dword ptr [rsp+0F0h+ObjectType], 4; FsInformationClass
0x1800a39c9  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a39cd  call    cs:__imp_ZwQueryVolumeInformationFile
0x1800a39d4  nop     dword ptr [rax+rax+00h]
0x1800a39d9  mov     ebx, eax
0x1800a39db  test    eax, eax
0x1800a39dd  js      loc_1800A3D78
0x1800a39e3  mov     eax, dword ptr [rbp+57h+FsInformation+4]
0x1800a39e6  test    al, 10h
0x1800a39e8  jnz     short loc_1800A3A5B
0x1800a39ea  lea     r9, [rbp+57h+var_88]
0x1800a39ee  mov     edx, 400h
0x1800a39f3  lea     r8, [rbp+57h+StringIn]
0x1800a39f7  mov     rcx, r13
0x1800a39fa  call    cs:__imp_FsRtlGetFileNameInformation
0x1800a3a01  nop     dword ptr [rax+rax+00h]
0x1800a3a06  mov     ebx, eax
0x1800a3a08  mov     eax, dword ptr [rbp+57h+FsInformation+4]
0x1800a3a0b  test    al, 10h
0x1800a3a0d  jnz     short loc_1800A3A5B
0x1800a3a0f  cmp     ebx, 0C0000002h
0x1800a3a15  jz      short loc_1800A3A5B
0x1800a3a17  cmp     ebx, 0C01C0005h
0x1800a3a1d  jz      short loc_1800A3A5B
0x1800a3a1f  test    ebx, ebx
0x1800a3a21  js      loc_1800A3D78
0x1800a3a27  lea     r8, [rbp+57h+StringOut]; StringOut
0x1800a3a2b  xor     ecx, ecx; Flags
0x1800a3a2d  lea     rdx, [rbp+57h+StringIn]; StringIn
0x1800a3a31  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a3a38  nop     dword ptr [rax+rax+00h]
0x1800a3a3d  mov     ebx, eax
0x1800a3a3f  test    eax, eax
0x1800a3a41  js      loc_1800A3D78
0x1800a3a47  mov     rax, [rbp+57h+var_88]
0x1800a3a4b  xor     edi, edi
0x1800a3a4d  movups  xmm0, xmmword ptr [rax+18h]
0x1800a3a51  movdqu  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800a3a56  jmp     loc_1800A3B9B
0x1800a3a5b  mov     ebx, 210h
0x1800a3a60  mov     r15d, 100h
0x1800a3a66  mov     edx, ebx
0x1800a3a68  mov     ecx, r15d
0x1800a3a6b  mov     r8d, 63734943h
0x1800a3a71  call    cs:__imp_ExAllocatePool2
0x1800a3a78  nop     dword ptr [rax+rax+00h]
0x1800a3a7d  mov     rdi, rax
0x1800a3a80  test    rax, rax
0x1800a3a83  jz      short loc_1800A3AE8
0x1800a3a85  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a3a89  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a3a8d  mov     r9d, ebx; Length
0x1800a3a90  mov     dword ptr [rsp+0F0h+ObjectType], 9; FileInformationClass
0x1800a3a98  mov     r8, rax; FileInformation
0x1800a3a9b  call    cs:__imp_ZwQueryInformationFile
0x1800a3aa2  nop     dword ptr [rax+rax+00h]
0x1800a3aa7  mov     ebx, eax
0x1800a3aa9  cmp     eax, 80000005h
0x1800a3aae  jnz     short loc_1800A3B16
0x1800a3ab0  mov     ebx, [rdi]
0x1800a3ab2  mov     edx, 63734943h; Tag
0x1800a3ab7  mov     rcx, rdi; P
0x1800a3aba  add     ebx, 8
0x1800a3abd  call    cs:__imp_ExFreePoolWithTag
0x1800a3ac4  nop     dword ptr [rax+rax+00h]
0x1800a3ac9  mov     edx, ebx
0x1800a3acb  mov     r8d, 63734943h
0x1800a3ad1  mov     ecx, r15d
0x1800a3ad4  call    cs:__imp_ExAllocatePool2
0x1800a3adb  nop     dword ptr [rax+rax+00h]
0x1800a3ae0  mov     rdi, rax
0x1800a3ae3  test    rax, rax
0x1800a3ae6  jnz     short loc_1800A3AF2
0x1800a3ae8  mov     ebx, 0C0000017h
0x1800a3aed  jmp     loc_1800A3D78
0x1800a3af2  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a3af6  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a3afa  mov     r9d, ebx; Length
0x1800a3afd  mov     dword ptr [rsp+0F0h+ObjectType], 9; FileInformationClass
0x1800a3b05  mov     r8, rax; FileInformation
0x1800a3b08  call    cs:__imp_ZwQueryInformationFile
0x1800a3b0f  nop     dword ptr [rax+rax+00h]
0x1800a3b14  mov     ebx, eax
0x1800a3b16  test    ebx, ebx
0x1800a3b18  js      loc_1800A3D64
0x1800a3b1e  cmp     dword ptr [rdi], 0FFFDh
0x1800a3b24  jbe     short loc_1800A3B30
0x1800a3b26  mov     ebx, 0C0000001h
0x1800a3b2b  jmp     loc_1800A3D5F
0x1800a3b30  movzx   eax, word ptr [rdi]
0x1800a3b33  mov     ecx, 102h
0x1800a3b38  add     ax, 2
0x1800a3b3c  mov     r8d, 72634943h
0x1800a3b42  movzx   edx, ax
0x1800a3b45  mov     [rbp+57h+StringOut.Length], dx
0x1800a3b49  mov     [rbp+57h+StringOut.MaximumLength], dx
0x1800a3b4d  call    cs:__imp_ExAllocatePool2
0x1800a3b54  nop     dword ptr [rax+rax+00h]
0x1800a3b59  mov     [rbp+57h+StringOut.Buffer], rax
0x1800a3b5d  test    rax, rax
0x1800a3b60  jnz     short loc_1800A3B6C
0x1800a3b62  mov     ebx, 0C0000017h
0x1800a3b67  jmp     loc_1800A3D5F
0x1800a3b6c  mov     rax, [rbp+57h+StringOut.Buffer]
0x1800a3b70  lea     rdx, [rdi+4]; Src
0x1800a3b74  mov     word ptr [rax], 5Ch ; '\'
0x1800a3b79  mov     rcx, [rbp+57h+StringOut.Buffer]
0x1800a3b7d  mov     r8d, [rdi]; Size
0x1800a3b80  add     rcx, 2; void *
0x1800a3b84  call    memmove
0x1800a3b89  xor     edx, edx; SourceString
0x1800a3b8b  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800a3b8f  call    cs:__imp_RtlInitUnicodeString
0x1800a3b96  nop     dword ptr [rax+rax+00h]
0x1800a3b9b  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800a3ba0  lea     r15, [r14+3B0h]
0x1800a3ba7  movups  xmm0, xmmword ptr [rbp+57h+StringOut.Length]
0x1800a3bab  mov     [rbp+57h+StringOut.Buffer], 0
0x1800a3bb3  movdqu  xmmword ptr [r15], xmm0
0x1800a3bb8  movdqu  xmmword ptr [r14+328h], xmm0
0x1800a3bc1  jz      short loc_1800A3C11
0x1800a3bc3  mov     rcx, [r13+8]; VolumeDeviceObject
0x1800a3bc7  lea     rdx, [rbp+57h+DosName]; DosName
0x1800a3bcb  call    cs:__imp_IoVolumeDeviceToDosName
0x1800a3bd2  nop     dword ptr [rax+rax+00h]
0x1800a3bd7  mov     ebx, eax
0x1800a3bd9  test    eax, eax
0x1800a3bdb  js      loc_1800A3D5F
0x1800a3be1  lea     r9, [r14+360h]; Destination
0x1800a3be8  mov     rcx, r15; String2
0x1800a3beb  lea     r8, [rbp+57h+DosName]; SourceString
0x1800a3bef  lea     rdx, [rbp+57h+DestinationString]; String1
0x1800a3bf3  call    SIPolicyPathMacroReplace
0x1800a3bf8  mov     ecx, 80000000h
0x1800a3bfd  mov     ebx, eax
0x1800a3bff  add     eax, ecx
0x1800a3c01  test    ecx, eax
0x1800a3c03  jnz     short loc_1800A3C11
0x1800a3c05  cmp     ebx, 0C000000Dh
0x1800a3c0b  jnz     loc_1800A3D5F
0x1800a3c11  cmp     qword ptr [r14+368h], 0
0x1800a3c19  jz      short loc_1800A3C31
0x1800a3c1b  lea     rcx, [r14+360h]; String2
0x1800a3c22  call    SIPolicyGetMacroPaths
0x1800a3c27  mov     ebx, eax
0x1800a3c29  test    eax, eax
0x1800a3c2b  js      loc_1800A3D5F
0x1800a3c31  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a3c35  lea     r8, [rbp+57h+var_40]; FsInformation
0x1800a3c39  mov     r15d, 5
0x1800a3c3f  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a3c43  mov     dword ptr [rsp+0F0h+ObjectType], r15d; FsInformationClass
0x1800a3c48  lea     r9d, [r15+0Bh]; Length
0x1800a3c4c  call    cs:__imp_ZwQueryVolumeInformationFile
0x1800a3c53  nop     dword ptr [rax+rax+00h]
0x1800a3c58  test    eax, eax
0x1800a3c5a  jns     short loc_1800A3C72
0x1800a3c5c  cmp     eax, 80000005h
0x1800a3c61  jnz     loc_1800A3D3B
0x1800a3c67  cmp     [rbp+57h+IoStatusBlock.Information], 0Ch
0x1800a3c6c  jb      loc_1800A3D3B
0x1800a3c72  xor     ebx, ebx
0x1800a3c74  test    byte ptr [rbp+57h+var_40], 8
0x1800a3c78  jz      loc_1800A3D3D
0x1800a3c7e  test    byte ptr [rbp+57h+FsInformation+4], 10h
0x1800a3c82  jnz     loc_1800A3D40
0x1800a3c88  xor     esi, esi
0x1800a3c8a  mov     r8d, ebx; Size
0x1800a3c8d  xor     edx, edx; Val
0x1800a3c8f  mov     rcx, rsi; void *
0x1800a3c92  call    memset
0x1800a3c97  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800a3c9b  lea     rax, [rbp+57h+LengthNeeded]
0x1800a3c9f  mov     r9d, ebx; Length
0x1800a3ca2  mov     [rsp+0F0h+ObjectType], rax; LengthNeeded
0x1800a3ca7  mov     r8, rsi; SecurityDescriptor
0x1800a3caa  mov     edx, r15d; SecurityInformation
0x1800a3cad  call    cs:__imp_ZwQuerySecurityObject
0x1800a3cb4  nop     dword ptr [rax+rax+00h]
0x1800a3cb9  test    eax, eax
0x1800a3cbb  jns     short loc_1800A3D11
0x1800a3cbd  cmp     eax, 80000005h
0x1800a3cc2  jz      short loc_1800A3CCB
0x1800a3cc4  cmp     eax, 0C0000023h
0x1800a3cc9  jnz     short loc_1800A3D3B
0x1800a3ccb  mov     edx, [rbp+57h+LengthNeeded]
0x1800a3cce  mov     ecx, 102h
0x1800a3cd3  mov     r8d, 63734943h
0x1800a3cd9  call    cs:__imp_ExAllocatePool2
0x1800a3ce0  nop     dword ptr [rax+rax+00h]
0x1800a3ce5  mov     rbx, rax
0x1800a3ce8  test    rax, rax
0x1800a3ceb  jz      short loc_1800A3D3B
0x1800a3ced  test    rsi, rsi
0x1800a3cf0  jz      short loc_1800A3D06
0x1800a3cf2  mov     edx, 63734943h; Tag
0x1800a3cf7  mov     rcx, rsi; P
0x1800a3cfa  call    cs:__imp_ExFreePoolWithTag
0x1800a3d01  nop     dword ptr [rax+rax+00h]
0x1800a3d06  mov     rsi, rbx
0x1800a3d09  mov     ebx, [rbp+57h+LengthNeeded]
0x1800a3d0c  jmp     loc_1800A3C8A
0x1800a3d11  lea     rdx, [rbp+57h+var_B0]
0x1800a3d15  mov     rcx, rsi; SecurityDescriptor
0x1800a3d18  call    SIPolicyIsSecurityDescriptorUserWriteable
0x1800a3d1d  mov     edx, 63734943h; Tag
0x1800a3d22  mov     rcx, rsi; P
0x1800a3d25  mov     ebx, eax
0x1800a3d27  call    cs:__imp_ExFreePoolWithTag
0x1800a3d2e  nop     dword ptr [rax+rax+00h]
0x1800a3d33  test    ebx, ebx
0x1800a3d35  jns     loc_1800A3DFB
0x1800a3d3b  xor     ebx, ebx
0x1800a3d3d  mov     sil, 1
0x1800a3d40  mov     eax, [r14+938h]
0x1800a3d47  movzx   ecx, sil
0x1800a3d4b  shl     ecx, 9
0x1800a3d4e  xor     ecx, eax
0x1800a3d50  and     ecx, 200h
0x1800a3d56  xor     ecx, eax
0x1800a3d58  mov     [r14+938h], ecx
0x1800a3d5f  test    rdi, rdi
0x1800a3d62  jz      short loc_1800A3D78
0x1800a3d64  mov     edx, 63734943h; Tag
0x1800a3d69  mov     rcx, rdi; P
0x1800a3d6c  call    cs:__imp_ExFreePoolWithTag
0x1800a3d73  nop     dword ptr [rax+rax+00h]
0x1800a3d78  mov     rcx, [rbp+57h+var_88]
0x1800a3d7c  test    rcx, rcx
0x1800a3d7f  jz      short loc_1800A3D8D
0x1800a3d81  call    cs:__imp_FsRtlReleaseFileNameInformation
0x1800a3d88  nop     dword ptr [rax+rax+00h]
0x1800a3d8d  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800a3d91  test    rcx, rcx
0x1800a3d94  jz      short loc_1800A3DA2
0x1800a3d96  call    cs:__imp_ZwClose
0x1800a3d9d  nop     dword ptr [rax+rax+00h]
0x1800a3da2  cmp     [rbp+57h+StringOut.Buffer], 0
0x1800a3da7  jz      short loc_1800A3DB9
0x1800a3da9  lea     rcx, [rbp+57h+StringOut]; UnicodeString
0x1800a3dad  call    cs:__imp_RtlFreeUnicodeString
0x1800a3db4  nop     dword ptr [rax+rax+00h]
0x1800a3db9  mov     rcx, [rbp+57h+DosName.Buffer]; P
0x1800a3dbd  test    rcx, rcx
0x1800a3dc0  jz      short loc_1800A3DD0
0x1800a3dc2  xor     edx, edx; Tag
0x1800a3dc4  call    cs:__imp_ExFreePoolWithTag
0x1800a3dcb  nop     dword ptr [rax+rax+00h]
0x1800a3dd0  mov     eax, ebx
0x1800a3dd2  mov     rcx, [rbp+57h+var_30]
0x1800a3dd6  xor     rcx, rsp; StackCookie
0x1800a3dd9  call    __security_check_cookie
0x1800a3dde  lea     r11, [rsp+0F0h+var_20]
0x1800a3de6  mov     rbx, [r11+40h]
  ... truncated ...
```
