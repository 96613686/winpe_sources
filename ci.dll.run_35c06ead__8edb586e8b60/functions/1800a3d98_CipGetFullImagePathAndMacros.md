# CipGetFullImagePathAndMacros

- ea: `0x1800a3d98`
- end: `0x1800a42a0`
- name: `CipGetFullImagePathAndMacros`
- size: `1288`
- prototype: `__int64 __fastcall(PVOID Object)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800a3cc4`

## callees

- `0x18002c0d0`
- `0x18002c200`
- `0x18002c500`
- `0x1800a3d98`
- `0x1800dea44`
- `0x1800dec14`
- `0x1800dff1c`

## import_xrefs

- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a4249`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1800a4249`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a402b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1800a402b`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3f0d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3f70`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3fe9`
- `ntoskrnl!ExAllocatePool2` at `0x1800a4175`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3f0d`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3f70`
- `ntoskrnl!ExAllocatePool2` at `0x1800a3fe9`
- `ntoskrnl!ExAllocatePool2` at `0x1800a4175`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3f59`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a4196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a41c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a4208`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a4260`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a3f59`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a4196`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a41c3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a4208`
- `ntoskrnl!ExFreePoolWithTag` at `0x1800a4260`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3ecd`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x1800a3ecd`
- `ntoskrnl!ZwClose` at `0x1800a4232`
- `ntoskrnl!ZwClose` at `0x1800a4232`
- `ntoskrnl!IoFileObjectType` at `0x1800a3df8`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a3f37`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a3fa4`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a3f37`
- `ntoskrnl!ZwQueryInformationFile` at `0x1800a3fa4`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800a3e39`
- `ntoskrnl!ObOpenObjectByPointer` at `0x1800a3e39`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800a3e96`
- `ntoskrnl!FsRtlGetFileNameInformation` at `0x1800a3e96`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800a421d`
- `ntoskrnl!FsRtlReleaseFileNameInformation` at `0x1800a421d`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a3e69`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a40e8`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a3e69`
- `ntoskrnl!ZwQueryVolumeInformationFile` at `0x1800a40e8`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1800a4067`
- `ntoskrnl!IoVolumeDeviceToDosName` at `0x1800a4067`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1800a4149`
- `ntoskrnl!ZwQuerySecurityObject` at `0x1800a4149`

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
          *(_DWORD *)(a2 + 2368) ^= ((unsigned __int16)*(_DWORD *)(a2 + 2368) ^ (unsigned __int16)(v3 << 9)) & 0x200;
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
0x1800a3d98  mov     [rsp-8+arg_10], rbx
0x1800a3d9d  mov     [rsp-8+arg_18], rsi
0x1800a3da2  push    rbp
0x1800a3da3  push    rdi
0x1800a3da4  push    r13
0x1800a3da6  push    r14
0x1800a3da8  push    r15
0x1800a3daa  lea     rbp, [rsp-37h]
0x1800a3daf  sub     rsp, 0D0h
0x1800a3db6  mov     rax, cs:__security_cookie
0x1800a3dbd  xor     rax, rsp
0x1800a3dc0  mov     [rbp+57h+var_30], rax
0x1800a3dc4  xorps   xmm0, xmm0
0x1800a3dc7  mov     [rbp+57h+var_88], 0
0x1800a3dcf  mov     r13, rcx
0x1800a3dd2  mov     [rbp+57h+FsInformation], 0
0x1800a3dda  xorps   xmm1, xmm1
0x1800a3ddd  mov     [rbp+57h+FileHandle], 0
0x1800a3de5  lea     rax, [rbp+57h+FileHandle]
0x1800a3de9  mov     [rbp+57h+LengthNeeded], 0
0x1800a3df0  mov     [rsp+0F0h+Handle], rax; Handle
0x1800a3df5  xor     sil, sil
0x1800a3df8  mov     rax, cs:__imp_IoFileObjectType
0x1800a3dff  mov     r14, rdx
0x1800a3e02  mov     [rsp+0F0h+AccessMode], sil; AccessMode
0x1800a3e07  xor     r9d, r9d; DesiredAccess
0x1800a3e0a  xor     r8d, r8d; PassedAccessState
0x1800a3e0d  mov     [rbp+57h+var_B0], sil
0x1800a3e11  mov     edx, 240h; HandleAttributes
0x1800a3e16  mov     rcx, [rax]
0x1800a3e19  mov     [rsp+0F0h+ObjectType], rcx; ObjectType
0x1800a3e1e  mov     rcx, r13; Object
0x1800a3e21  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800a3e25  movups  xmmword ptr [rbp+57h+StringIn.Length], xmm0
0x1800a3e29  movups  xmmword ptr [rbp+57h+DosName.Length], xmm1
0x1800a3e2d  movups  xmmword ptr [rbp+57h+StringOut.Length], xmm0
0x1800a3e31  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x1800a3e35  movups  [rbp+57h+var_40], xmm0
0x1800a3e39  call    cs:__imp_ObOpenObjectByPointer
0x1800a3e40  nop     dword ptr [rax+rax+00h]
0x1800a3e45  mov     ebx, eax
0x1800a3e47  test    eax, eax
0x1800a3e49  js      loc_1800A4214
0x1800a3e4f  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a3e53  lea     r8, [rbp+57h+FsInformation]; FsInformation
0x1800a3e57  mov     r9d, 8; Length
0x1800a3e5d  mov     dword ptr [rsp+0F0h+ObjectType], 4; FsInformationClass
0x1800a3e65  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a3e69  call    cs:__imp_ZwQueryVolumeInformationFile
0x1800a3e70  nop     dword ptr [rax+rax+00h]
0x1800a3e75  mov     ebx, eax
0x1800a3e77  test    eax, eax
0x1800a3e79  js      loc_1800A4214
0x1800a3e7f  mov     eax, dword ptr [rbp+57h+FsInformation+4]
0x1800a3e82  test    al, 10h
0x1800a3e84  jnz     short loc_1800A3EF7
0x1800a3e86  lea     r9, [rbp+57h+var_88]
0x1800a3e8a  mov     edx, 400h
0x1800a3e8f  lea     r8, [rbp+57h+StringIn]
0x1800a3e93  mov     rcx, r13
0x1800a3e96  call    cs:__imp_FsRtlGetFileNameInformation
0x1800a3e9d  nop     dword ptr [rax+rax+00h]
0x1800a3ea2  mov     ebx, eax
0x1800a3ea4  mov     eax, dword ptr [rbp+57h+FsInformation+4]
0x1800a3ea7  test    al, 10h
0x1800a3ea9  jnz     short loc_1800A3EF7
0x1800a3eab  cmp     ebx, 0C0000002h
0x1800a3eb1  jz      short loc_1800A3EF7
0x1800a3eb3  cmp     ebx, 0C01C0005h
0x1800a3eb9  jz      short loc_1800A3EF7
0x1800a3ebb  test    ebx, ebx
0x1800a3ebd  js      loc_1800A4214
0x1800a3ec3  lea     r8, [rbp+57h+StringOut]; StringOut
0x1800a3ec7  xor     ecx, ecx; Flags
0x1800a3ec9  lea     rdx, [rbp+57h+StringIn]; StringIn
0x1800a3ecd  call    cs:__imp_RtlDuplicateUnicodeString
0x1800a3ed4  nop     dword ptr [rax+rax+00h]
0x1800a3ed9  mov     ebx, eax
0x1800a3edb  test    eax, eax
0x1800a3edd  js      loc_1800A4214
0x1800a3ee3  mov     rax, [rbp+57h+var_88]
0x1800a3ee7  xor     edi, edi
0x1800a3ee9  movups  xmm0, xmmword ptr [rax+18h]
0x1800a3eed  movdqu  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1800a3ef2  jmp     loc_1800A4037
0x1800a3ef7  mov     ebx, 210h
0x1800a3efc  mov     r15d, 100h
0x1800a3f02  mov     edx, ebx
0x1800a3f04  mov     ecx, r15d
0x1800a3f07  mov     r8d, 63734943h
0x1800a3f0d  call    cs:__imp_ExAllocatePool2
0x1800a3f14  nop     dword ptr [rax+rax+00h]
0x1800a3f19  mov     rdi, rax
0x1800a3f1c  test    rax, rax
0x1800a3f1f  jz      short loc_1800A3F84
0x1800a3f21  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a3f25  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a3f29  mov     r9d, ebx; Length
0x1800a3f2c  mov     dword ptr [rsp+0F0h+ObjectType], 9; FileInformationClass
0x1800a3f34  mov     r8, rax; FileInformation
0x1800a3f37  call    cs:__imp_ZwQueryInformationFile
0x1800a3f3e  nop     dword ptr [rax+rax+00h]
0x1800a3f43  mov     ebx, eax
0x1800a3f45  cmp     eax, 80000005h
0x1800a3f4a  jnz     short loc_1800A3FB2
0x1800a3f4c  mov     ebx, [rdi]
0x1800a3f4e  mov     edx, 63734943h; Tag
0x1800a3f53  mov     rcx, rdi; P
0x1800a3f56  add     ebx, 8
0x1800a3f59  call    cs:__imp_ExFreePoolWithTag
0x1800a3f60  nop     dword ptr [rax+rax+00h]
0x1800a3f65  mov     edx, ebx
0x1800a3f67  mov     r8d, 63734943h
0x1800a3f6d  mov     ecx, r15d
0x1800a3f70  call    cs:__imp_ExAllocatePool2
0x1800a3f77  nop     dword ptr [rax+rax+00h]
0x1800a3f7c  mov     rdi, rax
0x1800a3f7f  test    rax, rax
0x1800a3f82  jnz     short loc_1800A3F8E
0x1800a3f84  mov     ebx, 0C0000017h
0x1800a3f89  jmp     loc_1800A4214
0x1800a3f8e  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a3f92  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a3f96  mov     r9d, ebx; Length
0x1800a3f99  mov     dword ptr [rsp+0F0h+ObjectType], 9; FileInformationClass
0x1800a3fa1  mov     r8, rax; FileInformation
0x1800a3fa4  call    cs:__imp_ZwQueryInformationFile
0x1800a3fab  nop     dword ptr [rax+rax+00h]
0x1800a3fb0  mov     ebx, eax
0x1800a3fb2  test    ebx, ebx
0x1800a3fb4  js      loc_1800A4200
0x1800a3fba  cmp     dword ptr [rdi], 0FFFDh
0x1800a3fc0  jbe     short loc_1800A3FCC
0x1800a3fc2  mov     ebx, 0C0000001h
0x1800a3fc7  jmp     loc_1800A41FB
0x1800a3fcc  movzx   eax, word ptr [rdi]
0x1800a3fcf  mov     ecx, 102h
0x1800a3fd4  add     ax, 2
0x1800a3fd8  mov     r8d, 72634943h
0x1800a3fde  movzx   edx, ax
0x1800a3fe1  mov     [rbp+57h+StringOut.Length], dx
0x1800a3fe5  mov     [rbp+57h+StringOut.MaximumLength], dx
0x1800a3fe9  call    cs:__imp_ExAllocatePool2
0x1800a3ff0  nop     dword ptr [rax+rax+00h]
0x1800a3ff5  mov     [rbp+57h+StringOut.Buffer], rax
0x1800a3ff9  test    rax, rax
0x1800a3ffc  jnz     short loc_1800A4008
0x1800a3ffe  mov     ebx, 0C0000017h
0x1800a4003  jmp     loc_1800A41FB
0x1800a4008  mov     rax, [rbp+57h+StringOut.Buffer]
0x1800a400c  lea     rdx, [rdi+4]; Src
0x1800a4010  mov     word ptr [rax], 5Ch ; '\'
0x1800a4015  mov     rcx, [rbp+57h+StringOut.Buffer]
0x1800a4019  mov     r8d, [rdi]; Size
0x1800a401c  add     rcx, 2; void *
0x1800a4020  call    memmove
0x1800a4025  xor     edx, edx; SourceString
0x1800a4027  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800a402b  call    cs:__imp_RtlInitUnicodeString
0x1800a4032  nop     dword ptr [rax+rax+00h]
0x1800a4037  cmp     [rbp+57h+DestinationString.Buffer], 0
0x1800a403c  lea     r15, [r14+3B0h]
0x1800a4043  movups  xmm0, xmmword ptr [rbp+57h+StringOut.Length]
0x1800a4047  mov     [rbp+57h+StringOut.Buffer], 0
0x1800a404f  movdqu  xmmword ptr [r15], xmm0
0x1800a4054  movdqu  xmmword ptr [r14+328h], xmm0
0x1800a405d  jz      short loc_1800A40AD
0x1800a405f  mov     rcx, [r13+8]; VolumeDeviceObject
0x1800a4063  lea     rdx, [rbp+57h+DosName]; DosName
0x1800a4067  call    cs:__imp_IoVolumeDeviceToDosName
0x1800a406e  nop     dword ptr [rax+rax+00h]
0x1800a4073  mov     ebx, eax
0x1800a4075  test    eax, eax
0x1800a4077  js      loc_1800A41FB
0x1800a407d  lea     r9, [r14+360h]; Destination
0x1800a4084  mov     rcx, r15; String2
0x1800a4087  lea     r8, [rbp+57h+DosName]; SourceString
0x1800a408b  lea     rdx, [rbp+57h+DestinationString]; String1
0x1800a408f  call    SIPolicyPathMacroReplace
0x1800a4094  mov     ecx, 80000000h
0x1800a4099  mov     ebx, eax
0x1800a409b  add     eax, ecx
0x1800a409d  test    ecx, eax
0x1800a409f  jnz     short loc_1800A40AD
0x1800a40a1  cmp     ebx, 0C000000Dh
0x1800a40a7  jnz     loc_1800A41FB
0x1800a40ad  cmp     qword ptr [r14+368h], 0
0x1800a40b5  jz      short loc_1800A40CD
0x1800a40b7  lea     rcx, [r14+360h]; String2
0x1800a40be  call    SIPolicyGetMacroPaths
0x1800a40c3  mov     ebx, eax
0x1800a40c5  test    eax, eax
0x1800a40c7  js      loc_1800A41FB
0x1800a40cd  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800a40d1  lea     r8, [rbp+57h+var_40]; FsInformation
0x1800a40d5  mov     r15d, 5
0x1800a40db  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800a40df  mov     dword ptr [rsp+0F0h+ObjectType], r15d; FsInformationClass
0x1800a40e4  lea     r9d, [r15+0Bh]; Length
0x1800a40e8  call    cs:__imp_ZwQueryVolumeInformationFile
0x1800a40ef  nop     dword ptr [rax+rax+00h]
0x1800a40f4  test    eax, eax
0x1800a40f6  jns     short loc_1800A410E
0x1800a40f8  cmp     eax, 80000005h
0x1800a40fd  jnz     loc_1800A41D7
0x1800a4103  cmp     [rbp+57h+IoStatusBlock.Information], 0Ch
0x1800a4108  jb      loc_1800A41D7
0x1800a410e  xor     ebx, ebx
0x1800a4110  test    byte ptr [rbp+57h+var_40], 8
0x1800a4114  jz      loc_1800A41D9
0x1800a411a  test    byte ptr [rbp+57h+FsInformation+4], 10h
0x1800a411e  jnz     loc_1800A41DC
0x1800a4124  xor     esi, esi
0x1800a4126  mov     r8d, ebx; Size
0x1800a4129  xor     edx, edx; Val
0x1800a412b  mov     rcx, rsi; void *
0x1800a412e  call    memset
0x1800a4133  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800a4137  lea     rax, [rbp+57h+LengthNeeded]
0x1800a413b  mov     r9d, ebx; Length
0x1800a413e  mov     [rsp+0F0h+ObjectType], rax; LengthNeeded
0x1800a4143  mov     r8, rsi; SecurityDescriptor
0x1800a4146  mov     edx, r15d; SecurityInformation
0x1800a4149  call    cs:__imp_ZwQuerySecurityObject
0x1800a4150  nop     dword ptr [rax+rax+00h]
0x1800a4155  test    eax, eax
0x1800a4157  jns     short loc_1800A41AD
0x1800a4159  cmp     eax, 80000005h
0x1800a415e  jz      short loc_1800A4167
0x1800a4160  cmp     eax, 0C0000023h
0x1800a4165  jnz     short loc_1800A41D7
0x1800a4167  mov     edx, [rbp+57h+LengthNeeded]
0x1800a416a  mov     ecx, 102h
0x1800a416f  mov     r8d, 63734943h
0x1800a4175  call    cs:__imp_ExAllocatePool2
0x1800a417c  nop     dword ptr [rax+rax+00h]
0x1800a4181  mov     rbx, rax
0x1800a4184  test    rax, rax
0x1800a4187  jz      short loc_1800A41D7
0x1800a4189  test    rsi, rsi
0x1800a418c  jz      short loc_1800A41A2
0x1800a418e  mov     edx, 63734943h; Tag
0x1800a4193  mov     rcx, rsi; P
0x1800a4196  call    cs:__imp_ExFreePoolWithTag
0x1800a419d  nop     dword ptr [rax+rax+00h]
0x1800a41a2  mov     rsi, rbx
0x1800a41a5  mov     ebx, [rbp+57h+LengthNeeded]
0x1800a41a8  jmp     loc_1800A4126
0x1800a41ad  lea     rdx, [rbp+57h+var_B0]
0x1800a41b1  mov     rcx, rsi; SecurityDescriptor
0x1800a41b4  call    SIPolicyIsSecurityDescriptorUserWriteable
0x1800a41b9  mov     edx, 63734943h; Tag
0x1800a41be  mov     rcx, rsi; P
0x1800a41c1  mov     ebx, eax
0x1800a41c3  call    cs:__imp_ExFreePoolWithTag
0x1800a41ca  nop     dword ptr [rax+rax+00h]
0x1800a41cf  test    ebx, ebx
0x1800a41d1  jns     loc_1800A4297
0x1800a41d7  xor     ebx, ebx
0x1800a41d9  mov     sil, 1
0x1800a41dc  mov     eax, [r14+940h]
0x1800a41e3  movzx   ecx, sil
0x1800a41e7  shl     ecx, 9
0x1800a41ea  xor     ecx, eax
0x1800a41ec  and     ecx, 200h
0x1800a41f2  xor     ecx, eax
0x1800a41f4  mov     [r14+940h], ecx
0x1800a41fb  test    rdi, rdi
0x1800a41fe  jz      short loc_1800A4214
0x1800a4200  mov     edx, 63734943h; Tag
0x1800a4205  mov     rcx, rdi; P
0x1800a4208  call    cs:__imp_ExFreePoolWithTag
0x1800a420f  nop     dword ptr [rax+rax+00h]
0x1800a4214  mov     rcx, [rbp+57h+var_88]
0x1800a4218  test    rcx, rcx
0x1800a421b  jz      short loc_1800A4229
0x1800a421d  call    cs:__imp_FsRtlReleaseFileNameInformation
0x1800a4224  nop     dword ptr [rax+rax+00h]
0x1800a4229  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800a422d  test    rcx, rcx
0x1800a4230  jz      short loc_1800A423E
0x1800a4232  call    cs:__imp_ZwClose
0x1800a4239  nop     dword ptr [rax+rax+00h]
0x1800a423e  cmp     [rbp+57h+StringOut.Buffer], 0
0x1800a4243  jz      short loc_1800A4255
0x1800a4245  lea     rcx, [rbp+57h+StringOut]; UnicodeString
0x1800a4249  call    cs:__imp_RtlFreeUnicodeString
0x1800a4250  nop     dword ptr [rax+rax+00h]
0x1800a4255  mov     rcx, [rbp+57h+DosName.Buffer]; P
0x1800a4259  test    rcx, rcx
0x1800a425c  jz      short loc_1800A426C
0x1800a425e  xor     edx, edx; Tag
0x1800a4260  call    cs:__imp_ExFreePoolWithTag
0x1800a4267  nop     dword ptr [rax+rax+00h]
0x1800a426c  mov     eax, ebx
0x1800a426e  mov     rcx, [rbp+57h+var_30]
0x1800a4272  xor     rcx, rsp; StackCookie
0x1800a4275  call    __security_check_cookie
0x1800a427a  lea     r11, [rsp+0F0h+var_20]
0x1800a4282  mov     rbx, [r11+40h]
  ... truncated ...
```
