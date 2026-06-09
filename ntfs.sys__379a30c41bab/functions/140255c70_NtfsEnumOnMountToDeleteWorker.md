# NtfsEnumOnMountToDeleteWorker

- ea: `0x140255c70`
- end: `0x140256147`
- name: `NtfsEnumOnMountToDeleteWorker`
- size: `1239`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14003c184`
- `0x14004907c`
- `0x140059740`
- `0x140255c70`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140255d46`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140255d46`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140255d18`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140255d2f`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140255d18`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140255d2f`
- `ntoskrnl!ZwClose` at `0x140255f46`
- `ntoskrnl!ZwClose` at `0x1402560f2`
- `ntoskrnl!ZwClose` at `0x140255f46`
- `ntoskrnl!ZwClose` at `0x1402560f2`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x140255e17`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x140256097`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x140255e17`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x140256097`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140255eb6`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140255eb6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140256006`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140256006`
- `ntoskrnl!RtlInitUnicodeString` at `0x140255d5d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140255d5d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255f05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255f90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255fa6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255f05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255f90`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255fa6`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255cf8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255d7f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255f2a`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255cf8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255d7f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255f2a`

## pseudocode

```c
void __fastcall NtfsEnumOnMountToDeleteWorker(__int64 a1)
{
  const UNICODE_STRING *v1; // rsi
  unsigned int *PoolWithTag; // rbx
  unsigned int v4; // eax
  SIZE_T v5; // r12
  NTSTATUS v6; // edi
  BOOLEAN v7; // r13
  NTSTATUS v8; // eax
  int v9; // edi
  char v10; // al
  unsigned int *v11; // rdi
  NTSTATUS v12; // eax
  int v13; // r14d
  char v14; // al
  __int64 v15; // rax
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING String2; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES v20; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+110h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+160h] [rbp+60h] BYREF
  HANDLE Handle; // [rsp+170h] [rbp+70h] BYREF
  __int64 v24; // [rsp+178h] [rbp+78h]

  v1 = *(const UNICODE_STRING **)(a1 + 104);
  *(_DWORD *)(a1 + 4) |= 0x200u;
  FileHandle = 0;
  Handle = 0;
  Destination = 0;
  PoolWithTag = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v20, 0, 44);
  IoStatusBlock = 0;
  String2 = 0;
  DestinationString = 0;
  v4 = v1[491].Length + 36;
  Destination.MaximumLength = v1[491].Length + 36;
  Destination.Buffer = (PWSTR)ExAllocatePoolWithTag(PoolType, v4, 0x6646744Eu);
  if ( Destination.Buffer )
  {
    RtlAppendUnicodeStringToString(&Destination, v1 + 491);
    RtlAppendUnicodeStringToString(&Destination, &stru_140062240);
    RtlAppendUnicodeToString(&Destination, L"\\");
    RtlInitUnicodeString(&DestinationString, L".");
    LODWORD(v5) = 320;
    v24 = 320;
    PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PoolType, 0x140u, 0x6646744Eu);
    if ( PoolWithTag )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &Destination;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v6 = IoCreateFileSpecifyDeviceObjectHint(
             &FileHandle,
             0x100001u,
             &ObjectAttributes,
             &IoStatusBlock,
             0,
             0x14u,
             7u,
             1u,
             0x21u,
             0,
             0,
             CreateFileTypeNone,
             0,
             0x101u,
             (PVOID)&v1[-24]);
      if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
        && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
      {
        McTemplateU0ppdw_EtwWriteTransfer(
          Destination.Length >> 1,
          (unsigned int)fsctrl_c44128,
          (_DWORD)v1,
          (unsigned int)KeGetCurrentThread(),
          v6,
          Destination.Length >> 1,
          (__int64)Destination.Buffer);
      }
      if ( v6 >= 0 )
      {
        v7 = 1;
        while ( 1 )
        {
          while ( 1 )
          {
            memset(PoolWithTag, 0, (unsigned int)v5);
            v8 = ZwQueryDirectoryFile(
                   FileHandle,
                   0,
                   0,
                   0,
                   &IoStatusBlock,
                   PoolWithTag,
                   v5,
                   FileNamesInformation,
                   0,
                   0,
                   v7);
            v9 = v8;
            if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
            {
              McTemplateU0ppd_EtwWriteTransfer(
                *(_DWORD *)(a1 + 16),
                (unsigned int)fsctrl_c44164,
                (_DWORD)v1,
                (unsigned int)KeGetCurrentThread(),
                v8);
            }
            if ( v9 != -2147483643 )
              break;
            ExFreePoolWithTag(PoolWithTag, 0);
            v5 = (unsigned int)(2 * v5);
            v24 = v5;
            PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PoolType, v5, 0x6646744Eu);
            if ( !PoolWithTag )
              goto LABEL_13;
          }
          if ( v9 < 0 )
            break;
          v7 = 0;
          v11 = PoolWithTag;
          do
          {
            String2.Buffer = (PWSTR)(v11 + 3);
            String2.MaximumLength = *((_WORD *)v11 + 4);
            String2.Length = *((_WORD *)v11 + 4);
            if ( !RtlPrefixUnicodeString(&DestinationString, &String2, 1u) )
            {
              v20.RootDirectory = FileHandle;
              v20.Length = 48;
              v20.Attributes = 576;
              v20.ObjectName = &String2;
              *(_OWORD *)&v20.SecurityDescriptor = 0;
              v12 = IoCreateFileSpecifyDeviceObjectHint(
                      &Handle,
                      0x10000u,
                      &v20,
                      &IoStatusBlock,
                      0,
                      0x80u,
                      7u,
                      1u,
                      0x201020u,
                      0,
                      0,
                      CreateFileTypeNone,
                      0,
                      0x100u,
                      (PVOID)&v1[-24]);
              v13 = v12;
              if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
              {
                McTemplateU0ppdw_EtwWriteTransfer(
                  String2.Buffer,
                  (unsigned int)fsctrl_c44240,
                  (_DWORD)v1,
                  (unsigned int)KeGetCurrentThread(),
                  v12,
                  String2.Length >> 1,
                  (__int64)String2.Buffer);
              }
              if ( v13 >= 0 )
              {
                v14 = ZwClose(Handle);
                if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
                {
                  McTemplateU0ppd_EtwWriteTransfer(
                    *(_DWORD *)(a1 + 16),
                    (unsigned int)fsctrl_c44253,
                    (_DWORD)v1,
                    (unsigned int)KeGetCurrentThread(),
                    v14);
                }
              }
            }
            v15 = *v11;
            v11 = (unsigned int *)((char *)v11 + v15);
          }
          while ( (_DWORD)v15 );
          LODWORD(v5) = v24;
        }
LABEL_13:
        v10 = ZwClose(FileHandle);
        if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
        {
          McTemplateU0ppd_EtwWriteTransfer(
            *(_DWORD *)(a1 + 16),
            (unsigned int)fsctrl_c44271,
            (_DWORD)v1,
            (unsigned int)KeGetCurrentThread(),
            v10);
        }
      }
    }
    if ( Destination.Buffer )
      ExFreePoolWithTag(Destination.Buffer, 0);
  }
  if ( PoolWithTag )
    ExFreePoolWithTag(PoolWithTag, 0);
}

```

## disassembly

```asm
0x140255c70  mov     [rsp-8+arg_8], rbx
0x140255c75  push    rbp
0x140255c76  push    rsi
0x140255c77  push    rdi
0x140255c78  push    r12
0x140255c7a  push    r13
0x140255c7c  push    r14
0x140255c7e  push    r15
0x140255c80  lea     rbp, [rsp-20h]
0x140255c85  sub     rsp, 120h
0x140255c8c  mov     rsi, [rcx+68h]
0x140255c90  xorps   xmm0, xmm0
0x140255c93  bts     dword ptr [rcx+4], 9
0x140255c98  xor     r14d, r14d
0x140255c9b  xorps   xmm1, xmm1
0x140255c9e  mov     [rbp+50h+FileHandle], r14
0x140255ca2  xor     eax, eax
0x140255ca4  mov     [rbp+50h+Handle], r14
0x140255ca8  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x140255cac  mov     r15, rcx
0x140255caf  mov     ecx, cs:PoolType; PoolType
0x140255cb5  movups  xmmword ptr [rbp+50h+var_70.ObjectName], xmm0
0x140255cb9  lea     rdi, [rsi+1EB0h]
0x140255cc0  mov     r12d, 6646744Eh
0x140255cc6  movups  xmmword ptr [rbp+50h+Destination.Length], xmm1
0x140255cca  mov     r8d, r12d; Tag
0x140255ccd  mov     ebx, r14d
0x140255cd0  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x140255cd4  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x140255cd8  movups  xmmword ptr [rbp+50h+var_70.Length], xmm0
0x140255cdc  movups  xmmword ptr [rbp+50h+var_70+1Ch], xmm0
0x140255ce0  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x140255ce4  movups  xmmword ptr [rbp+50h+String2.Length], xmm0
0x140255ce8  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm1
0x140255cec  movzx   eax, word ptr [rdi]
0x140255cef  add     eax, 24h ; '$'
0x140255cf2  mov     edx, eax; NumberOfBytes
0x140255cf4  mov     [rbp+50h+Destination.MaximumLength], ax
0x140255cf8  call    cs:__imp_ExAllocatePoolWithTag
0x140255cff  nop     dword ptr [rax+rax+00h]
0x140255d04  mov     [rbp+50h+Destination.Buffer], rax
0x140255d08  test    rax, rax
0x140255d0b  jz      loc_140255F9C
0x140255d11  mov     rdx, rdi; Source
0x140255d14  lea     rcx, [rbp+50h+Destination]; Destination
0x140255d18  call    cs:__imp_RtlAppendUnicodeStringToString
0x140255d1f  nop     dword ptr [rax+rax+00h]
0x140255d24  lea     rdx, stru_140062240; Source
0x140255d2b  lea     rcx, [rbp+50h+Destination]; Destination
0x140255d2f  call    cs:__imp_RtlAppendUnicodeStringToString
0x140255d36  nop     dword ptr [rax+rax+00h]
0x140255d3b  lea     rdx, asc_140063E4C; "\\"
0x140255d42  lea     rcx, [rbp+50h+Destination]; Destination
0x140255d46  call    cs:__imp_RtlAppendUnicodeToString
0x140255d4d  nop     dword ptr [rax+rax+00h]
0x140255d52  lea     rdx, asc_140063858; "."
0x140255d59  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140255d5d  call    cs:__imp_RtlInitUnicodeString
0x140255d64  nop     dword ptr [rax+rax+00h]
0x140255d69  mov     ecx, cs:PoolType; PoolType
0x140255d6f  mov     r8d, r12d; Tag
0x140255d72  mov     r12d, 140h
0x140255d78  mov     edx, r12d; NumberOfBytes
0x140255d7b  mov     [rbp+50h+arg_18], r12
0x140255d7f  call    cs:__imp_ExAllocatePoolWithTag
0x140255d86  nop     dword ptr [rax+rax+00h]
0x140255d8b  mov     rbx, rax
0x140255d8e  test    rax, rax
0x140255d91  jz      loc_140255F82
0x140255d97  lea     rax, [rsi-180h]
0x140255d9e  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x140255da5  mov     [rsp+150h+DeviceObject], rax; DeviceObject
0x140255daa  lea     rcx, [rbp+50h+Destination]
0x140255dae  mov     [rsp+150h+Options], 101h; Options
0x140255db6  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x140255dba  mov     [rsp+150h+InternalParameters], r14; InternalParameters
0x140255dbf  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x140255dc3  mov     [rsp+150h+CreateFileType], r14d; CreateFileType
0x140255dc8  xorps   xmm0, xmm0
0x140255dcb  mov     [rsp+150h+EaLength], r14d; EaLength
0x140255dd0  mov     edx, 100001h; DesiredAccess
0x140255dd5  mov     [rsp+150h+EaBuffer], r14; EaBuffer
0x140255dda  mov     [rsp+150h+CreateOptions], 21h ; '!'; CreateOptions
0x140255de2  mov     [rsp+150h+Disposition], 1; Disposition
0x140255dea  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x140255df2  mov     [rbp+50h+ObjectAttributes.ObjectName], rcx
0x140255df6  lea     rcx, [rbp+50h+FileHandle]; FileHandle
0x140255dfa  mov     [rsp+150h+FileAttributes], 14h; FileAttributes
0x140255e02  mov     [rsp+150h+AllocationSize], r14; AllocationSize
0x140255e07  mov     [rbp+50h+ObjectAttributes.RootDirectory], r14
0x140255e0b  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x140255e12  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x140255e17  call    cs:__imp_IoCreateFileSpecifyDeviceObjectHint
0x140255e1e  nop     dword ptr [rax+rax+00h]
0x140255e23  mov     ecx, [r15+10h]
0x140255e27  mov     edi, eax
0x140255e29  bt      rcx, 14h
0x140255e2e  jb      short loc_140255E68
0x140255e30  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x140255e37  jz      short loc_140255E68
0x140255e39  movzx   ecx, [rbp+50h+Destination.Length]
0x140255e3d  lea     rdx, fsctrl_c44128
0x140255e44  mov     r9, gs:188h
0x140255e4d  mov     r8, rsi
0x140255e50  mov     rax, [rbp+50h+Destination.Buffer]
0x140255e54  mov     qword ptr [rsp+150h+ShareAccess], rax
0x140255e59  shr     ecx, 1
0x140255e5b  mov     [rsp+150h+FileAttributes], ecx
0x140255e5f  mov     dword ptr [rsp+150h+AllocationSize], edi
0x140255e63  call    McTemplateU0ppdw_EtwWriteTransfer
0x140255e68  test    edi, edi
0x140255e6a  js      loc_140255F82
0x140255e70  mov     r13b, 1
0x140255e73  mov     r8d, r12d; Size
0x140255e76  xor     edx, edx; Val
0x140255e78  mov     rcx, rbx; void *
0x140255e7b  call    memset
0x140255e80  mov     rcx, [rbp+50h+FileHandle]; FileHandle
0x140255e84  lea     rax, [rbp+50h+IoStatusBlock]
0x140255e88  mov     byte ptr [rsp+150h+EaLength], r13b; RestartScan
0x140255e8d  xor     r9d, r9d; ApcContext
0x140255e90  mov     [rsp+150h+EaBuffer], r14; FileName
0x140255e95  xor     r8d, r8d; ApcRoutine
0x140255e98  mov     byte ptr [rsp+150h+CreateOptions], r14b; ReturnSingleEntry
0x140255e9d  xor     edx, edx; Event
0x140255e9f  mov     [rsp+150h+Disposition], 0Ch; FileInformationClass
0x140255ea7  mov     [rsp+150h+ShareAccess], r12d; Length
0x140255eac  mov     qword ptr [rsp+150h+FileAttributes], rbx; FileInformation
0x140255eb1  mov     [rsp+150h+AllocationSize], rax; IoStatusBlock
0x140255eb6  call    cs:__imp_ZwQueryDirectoryFile
0x140255ebd  nop     dword ptr [rax+rax+00h]
0x140255ec2  mov     ecx, [r15+10h]
0x140255ec6  mov     edi, eax
0x140255ec8  bt      rcx, 14h
0x140255ecd  jb      short loc_140255EF4
0x140255ecf  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x140255ed6  jz      short loc_140255EF4
0x140255ed8  mov     r9, gs:188h
0x140255ee1  lea     rdx, fsctrl_c44164
0x140255ee8  mov     r8, rsi
0x140255eeb  mov     dword ptr [rsp+150h+AllocationSize], eax
0x140255eef  call    McTemplateU0ppd_EtwWriteTransfer
0x140255ef4  cmp     edi, 80000005h
0x140255efa  jnz     loc_140255FCE
0x140255f00  xor     edx, edx; Tag
0x140255f02  mov     rcx, rbx; P
0x140255f05  call    cs:__imp_ExFreePoolWithTag
0x140255f0c  nop     dword ptr [rax+rax+00h]
0x140255f11  mov     ecx, cs:PoolType; PoolType
0x140255f17  lea     eax, [r12+r12]
0x140255f1b  mov     r12d, eax
0x140255f1e  mov     r8d, 6646744Eh; Tag
0x140255f24  mov     edx, eax; NumberOfBytes
0x140255f26  mov     [rbp+50h+arg_18], r12
0x140255f2a  call    cs:__imp_ExAllocatePoolWithTag
0x140255f31  nop     dword ptr [rax+rax+00h]
0x140255f36  mov     rbx, rax
0x140255f39  test    rax, rax
0x140255f3c  jnz     loc_140255E73
0x140255f42  mov     rcx, [rbp+50h+FileHandle]; Handle
0x140255f46  call    cs:__imp_ZwClose
0x140255f4d  nop     dword ptr [rax+rax+00h]
0x140255f52  mov     ecx, [r15+10h]
0x140255f56  bt      rcx, 14h
0x140255f5b  jb      short loc_140255F82
0x140255f5d  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x140255f64  jz      short loc_140255F82
0x140255f66  mov     r9, gs:188h
0x140255f6f  lea     rdx, fsctrl_c44271
0x140255f76  mov     r8, rsi
0x140255f79  mov     dword ptr [rsp+150h+AllocationSize], eax
0x140255f7d  call    McTemplateU0ppd_EtwWriteTransfer
0x140255f82  mov     rax, [rbp+50h+Destination.Buffer]
0x140255f86  test    rax, rax
0x140255f89  jz      short loc_140255F9C
0x140255f8b  xor     edx, edx; Tag
0x140255f8d  mov     rcx, rax; P
0x140255f90  call    cs:__imp_ExFreePoolWithTag
0x140255f97  nop     dword ptr [rax+rax+00h]
0x140255f9c  test    rbx, rbx
0x140255f9f  jz      short loc_140255FB2
0x140255fa1  xor     edx, edx; Tag
0x140255fa3  mov     rcx, rbx; P
0x140255fa6  call    cs:__imp_ExFreePoolWithTag
0x140255fad  nop     dword ptr [rax+rax+00h]
0x140255fb2  mov     rbx, [rsp+150h+arg_8]
0x140255fba  add     rsp, 120h
0x140255fc1  pop     r15
0x140255fc3  pop     r14
0x140255fc5  pop     r13
0x140255fc7  pop     r12
0x140255fc9  pop     rdi
0x140255fca  pop     rsi
0x140255fcb  pop     rbp
0x140255fcc  retn
0x140255fce  test    edi, edi
0x140255fd0  js      loc_140255F42
0x140255fd6  mov     r13b, r14b
0x140255fd9  lea     r12, [rsi-180h]
0x140255fe0  mov     rdi, rbx
0x140255fe3  lea     rax, [rdi+0Ch]
0x140255fe7  mov     r8b, 1; CaseInSensitive
0x140255fea  mov     [rbp+50h+String2.Buffer], rax
0x140255fee  lea     rdx, [rbp+50h+String2]; String2
0x140255ff2  movzx   eax, word ptr [rdi+8]
0x140255ff6  lea     rcx, [rbp+50h+DestinationString]; String1
0x140255ffa  mov     [rbp+50h+String2.MaximumLength], ax
0x140255ffe  movzx   eax, word ptr [rdi+8]
0x140256002  mov     [rbp+50h+String2.Length], ax
0x140256006  call    cs:__imp_RtlPrefixUnicodeString
0x14025600d  nop     dword ptr [rax+rax+00h]
0x140256012  test    al, al
0x140256014  jnz     loc_140256131
0x14025601a  mov     rax, [rbp+50h+FileHandle]
0x14025601e  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x140256022  mov     [rsp+150h+DeviceObject], r12; DeviceObject
0x140256027  lea     r8, [rbp+50h+var_70]; ObjectAttributes
0x14025602b  mov     [rsp+150h+Options], 100h; Options
0x140256033  lea     rcx, [rbp+50h+Handle]; FileHandle
0x140256037  mov     [rsp+150h+InternalParameters], r14; InternalParameters
0x14025603c  xorps   xmm0, xmm0
0x14025603f  mov     [rsp+150h+CreateFileType], r14d; CreateFileType
0x140256044  mov     edx, 10000h; DesiredAccess
0x140256049  mov     [rsp+150h+EaLength], r14d; EaLength
0x14025604e  mov     [rsp+150h+EaBuffer], r14; EaBuffer
0x140256053  mov     [rsp+150h+CreateOptions], 201020h; CreateOptions
0x14025605b  mov     [rsp+150h+Disposition], 1; Disposition
0x140256063  mov     [rbp+50h+var_70.RootDirectory], rax
0x140256067  lea     rax, [rbp+50h+String2]
0x14025606b  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x140256073  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x14025607b  mov     [rsp+150h+AllocationSize], r14; AllocationSize
0x140256080  mov     [rbp+50h+var_70.Length], 30h ; '0'
0x140256087  mov     [rbp+50h+var_70.Attributes], 240h
0x14025608e  mov     [rbp+50h+var_70.ObjectName], rax
0x140256092  movdqu  xmmword ptr [rbp+50h+var_70.SecurityDescriptor], xmm0
0x140256097  call    cs:__imp_IoCreateFileSpecifyDeviceObjectHint
0x14025609e  nop     dword ptr [rax+rax+00h]
0x1402560a3  mov     ecx, [r15+10h]
0x1402560a7  mov     r14d, eax
0x1402560aa  bt      rcx, 14h
0x1402560af  jb      short loc_1402560E9
0x1402560b1  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x1402560b8  jz      short loc_1402560E9
0x1402560ba  movzx   edx, [rbp+50h+String2.Length]
0x1402560be  mov     r8, rsi
0x1402560c1  mov     r9, gs:188h
0x1402560ca  mov     rcx, [rbp+50h+String2.Buffer]
0x1402560ce  shr     edx, 1
0x1402560d0  mov     qword ptr [rsp+150h+ShareAccess], rcx
0x1402560d5  mov     [rsp+150h+FileAttributes], edx
0x1402560d9  lea     rdx, fsctrl_c44240
0x1402560e0  mov     dword ptr [rsp+150h+AllocationSize], eax
0x1402560e4  call    McTemplateU0ppdw_EtwWriteTransfer
0x1402560e9  test    r14d, r14d
0x1402560ec  js      short loc_14025612E
0x1402560ee  mov     rcx, [rbp+50h+Handle]; Handle
0x1402560f2  call    cs:__imp_ZwClose
0x1402560f9  nop     dword ptr [rax+rax+00h]
0x1402560fe  mov     ecx, [r15+10h]
0x140256102  bt      rcx, 14h
0x140256107  jb      short loc_14025612E
0x140256109  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x140256110  jz      short loc_14025612E
0x140256112  mov     r9, gs:188h
0x14025611b  lea     rdx, fsctrl_c44253
0x140256122  mov     r8, rsi
0x140256125  mov     dword ptr [rsp+150h+AllocationSize], eax
0x140256129  call    McTemplateU0ppd_EtwWriteTransfer
0x14025612e  xor     r14d, r14d
0x140256131  mov     eax, [rdi]
0x140256133  add     rdi, rax
0x140256136  test    eax, eax
0x140256138  jnz     loc_140255FE3
0x14025613e  mov     r12, [rbp+50h+arg_18]
0x140256142  jmp     loc_140255E73
```
