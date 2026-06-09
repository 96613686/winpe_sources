# NtfsEnumOnMountToDeleteWorker

- ea: `0x140255c20`
- end: `0x1402560f7`
- name: `NtfsEnumOnMountToDeleteWorker`
- size: `1239`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14003c184`
- `0x14004900c`
- `0x1400596c0`
- `0x140255c20`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeToString` at `0x140255cf6`
- `ntoskrnl!RtlAppendUnicodeToString` at `0x140255cf6`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140255cc8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140255cdf`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140255cc8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140255cdf`
- `ntoskrnl!ZwClose` at `0x140255ef6`
- `ntoskrnl!ZwClose` at `0x1402560a2`
- `ntoskrnl!ZwClose` at `0x140255ef6`
- `ntoskrnl!ZwClose` at `0x1402560a2`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x140255dc7`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x140256047`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x140255dc7`
- `ntoskrnl!IoCreateFileSpecifyDeviceObjectHint` at `0x140256047`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140255e66`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x140255e66`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140255fb6`
- `ntoskrnl!RtlPrefixUnicodeString` at `0x140255fb6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140255d0d`
- `ntoskrnl!RtlInitUnicodeString` at `0x140255d0d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255eb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255f40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255f56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255eb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255f40`
- `ntoskrnl!ExFreePoolWithTag` at `0x140255f56`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255ca8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255d2f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255eda`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255ca8`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255d2f`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140255eda`

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
  __int64 v9; // rcx
  int v10; // edi
  NTSTATUS v11; // eax
  __int64 v12; // rcx
  unsigned int *v13; // rdi
  NTSTATUS v14; // eax
  int v15; // r14d
  NTSTATUS v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rax
  PLARGE_INTEGER AllocationSize; // [rsp+20h] [rbp-E0h]
  PLARGE_INTEGER AllocationSizea; // [rsp+20h] [rbp-E0h]
  PLARGE_INTEGER AllocationSizeb; // [rsp+20h] [rbp-E0h]
  ULONG FileAttributes[2]; // [rsp+28h] [rbp-D8h]
  ULONG FileAttributesa[2]; // [rsp+28h] [rbp-D8h]
  struct _UNICODE_STRING Destination; // [rsp+80h] [rbp-80h] BYREF
  UNICODE_STRING String2; // [rsp+90h] [rbp-70h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES v28; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+110h] [rbp+10h] BYREF
  void *FileHandle; // [rsp+160h] [rbp+60h] BYREF
  HANDLE Handle; // [rsp+170h] [rbp+70h] BYREF
  __int64 v32; // [rsp+178h] [rbp+78h]

  v1 = *(const UNICODE_STRING **)(a1 + 104);
  *(_DWORD *)(a1 + 4) |= 0x200u;
  FileHandle = 0;
  Handle = 0;
  Destination = 0;
  PoolWithTag = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&v28, 0, 44);
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
    v32 = 320;
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
        FileAttributes[0] = Destination.Length >> 1;
        LODWORD(AllocationSize) = v6;
        McTemplateU0ppdw_EtwWriteTransfer(
          FileAttributes[0],
          (const EVENT_DESCRIPTOR *)fsctrl_c44128,
          v1,
          KeGetCurrentThread(),
          AllocationSize,
          *(_QWORD *)FileAttributes,
          Destination.Buffer);
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
            v9 = *(unsigned int *)(a1 + 16);
            v10 = v8;
            if ( (v9 & 0x100000) == 0
              && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
            {
              LODWORD(AllocationSizea) = v8;
              McTemplateU0ppd_EtwWriteTransfer(
                v9,
                (const EVENT_DESCRIPTOR *)fsctrl_c44164,
                v1,
                KeGetCurrentThread(),
                AllocationSizea);
            }
            if ( v10 != -2147483643 )
              break;
            ExFreePoolWithTag(PoolWithTag, 0);
            v5 = (unsigned int)(2 * v5);
            v32 = v5;
            PoolWithTag = (unsigned int *)ExAllocatePoolWithTag(PoolType, v5, 0x6646744Eu);
            if ( !PoolWithTag )
              goto LABEL_13;
          }
          if ( v10 < 0 )
            break;
          v7 = 0;
          v13 = PoolWithTag;
          do
          {
            String2.Buffer = (PWSTR)(v13 + 3);
            String2.MaximumLength = *((_WORD *)v13 + 4);
            String2.Length = *((_WORD *)v13 + 4);
            if ( !RtlPrefixUnicodeString(&DestinationString, &String2, 1u) )
            {
              v28.RootDirectory = FileHandle;
              v28.Length = 48;
              v28.Attributes = 576;
              v28.ObjectName = &String2;
              *(_OWORD *)&v28.SecurityDescriptor = 0;
              v14 = IoCreateFileSpecifyDeviceObjectHint(
                      &Handle,
                      0x10000u,
                      &v28,
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
              v15 = v14;
              if ( (*(_DWORD *)(a1 + 16) & 0x100000) == 0
                && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
              {
                FileAttributesa[0] = String2.Length >> 1;
                LODWORD(AllocationSizeb) = v14;
                McTemplateU0ppdw_EtwWriteTransfer(
                  (__int64)String2.Buffer,
                  (const EVENT_DESCRIPTOR *)fsctrl_c44240,
                  v1,
                  KeGetCurrentThread(),
                  AllocationSizeb,
                  *(_QWORD *)FileAttributesa,
                  String2.Buffer);
              }
              if ( v15 >= 0 )
              {
                v16 = ZwClose(Handle);
                v17 = *(unsigned int *)(a1 + 16);
                if ( (v17 & 0x100000) == 0
                  && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
                {
                  LODWORD(AllocationSizeb) = v16;
                  McTemplateU0ppd_EtwWriteTransfer(
                    v17,
                    (const EVENT_DESCRIPTOR *)fsctrl_c44253,
                    v1,
                    KeGetCurrentThread(),
                    AllocationSizeb);
                }
              }
            }
            v18 = *v13;
            v13 = (unsigned int *)((char *)v13 + v18);
          }
          while ( (_DWORD)v18 );
          LODWORD(v5) = v32;
        }
LABEL_13:
        v11 = ZwClose(FileHandle);
        v12 = *(unsigned int *)(a1 + 16);
        if ( (v12 & 0x100000) == 0
          && (Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits & 0x40000000) != 0 )
        {
          LODWORD(AllocationSizea) = v11;
          McTemplateU0ppd_EtwWriteTransfer(
            v12,
            (const EVENT_DESCRIPTOR *)fsctrl_c44271,
            v1,
            KeGetCurrentThread(),
            AllocationSizea);
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
0x140255c20  mov     [rsp-8+arg_8], rbx
0x140255c25  push    rbp
0x140255c26  push    rsi
0x140255c27  push    rdi
0x140255c28  push    r12
0x140255c2a  push    r13
0x140255c2c  push    r14
0x140255c2e  push    r15
0x140255c30  lea     rbp, [rsp-20h]
0x140255c35  sub     rsp, 120h
0x140255c3c  mov     rsi, [rcx+68h]
0x140255c40  xorps   xmm0, xmm0
0x140255c43  bts     dword ptr [rcx+4], 9
0x140255c48  xor     r14d, r14d
0x140255c4b  xorps   xmm1, xmm1
0x140255c4e  mov     [rbp+50h+FileHandle], r14
0x140255c52  xor     eax, eax
0x140255c54  mov     [rbp+50h+Handle], r14
0x140255c58  movups  xmmword ptr [rbp+50h+ObjectAttributes.ObjectName], xmm0
0x140255c5c  mov     r15, rcx
0x140255c5f  mov     ecx, cs:PoolType; PoolType
0x140255c65  movups  xmmword ptr [rbp+50h+var_70.ObjectName], xmm0
0x140255c69  lea     rdi, [rsi+1EB0h]
0x140255c70  mov     r12d, 6646744Eh
0x140255c76  movups  xmmword ptr [rbp+50h+Destination.Length], xmm1
0x140255c7a  mov     r8d, r12d; Tag
0x140255c7d  mov     ebx, r14d
0x140255c80  movups  xmmword ptr [rbp+50h+ObjectAttributes.Length], xmm0
0x140255c84  movups  xmmword ptr [rbp+50h+ObjectAttributes+1Ch], xmm0
0x140255c88  movups  xmmword ptr [rbp+50h+var_70.Length], xmm0
0x140255c8c  movups  xmmword ptr [rbp+50h+var_70+1Ch], xmm0
0x140255c90  movups  xmmword ptr [rbp+50h+IoStatusBlock], xmm0
0x140255c94  movups  xmmword ptr [rbp+50h+String2.Length], xmm0
0x140255c98  movups  xmmword ptr [rbp+50h+DestinationString.Length], xmm1
0x140255c9c  movzx   eax, word ptr [rdi]
0x140255c9f  add     eax, 24h ; '$'
0x140255ca2  mov     edx, eax; NumberOfBytes
0x140255ca4  mov     [rbp+50h+Destination.MaximumLength], ax
0x140255ca8  call    cs:__imp_ExAllocatePoolWithTag
0x140255caf  nop     dword ptr [rax+rax+00h]
0x140255cb4  mov     [rbp+50h+Destination.Buffer], rax
0x140255cb8  test    rax, rax
0x140255cbb  jz      loc_140255F4C
0x140255cc1  mov     rdx, rdi; Source
0x140255cc4  lea     rcx, [rbp+50h+Destination]; Destination
0x140255cc8  call    cs:__imp_RtlAppendUnicodeStringToString
0x140255ccf  nop     dword ptr [rax+rax+00h]
0x140255cd4  lea     rdx, stru_140062240; Source
0x140255cdb  lea     rcx, [rbp+50h+Destination]; Destination
0x140255cdf  call    cs:__imp_RtlAppendUnicodeStringToString
0x140255ce6  nop     dword ptr [rax+rax+00h]
0x140255ceb  lea     rdx, asc_140063E4C; "\\"
0x140255cf2  lea     rcx, [rbp+50h+Destination]; Destination
0x140255cf6  call    cs:__imp_RtlAppendUnicodeToString
0x140255cfd  nop     dword ptr [rax+rax+00h]
0x140255d02  lea     rdx, asc_140063858; "."
0x140255d09  lea     rcx, [rbp+50h+DestinationString]; DestinationString
0x140255d0d  call    cs:__imp_RtlInitUnicodeString
0x140255d14  nop     dword ptr [rax+rax+00h]
0x140255d19  mov     ecx, cs:PoolType; PoolType
0x140255d1f  mov     r8d, r12d; Tag
0x140255d22  mov     r12d, 140h
0x140255d28  mov     edx, r12d; NumberOfBytes
0x140255d2b  mov     [rbp+50h+arg_18], r12
0x140255d2f  call    cs:__imp_ExAllocatePoolWithTag
0x140255d36  nop     dword ptr [rax+rax+00h]
0x140255d3b  mov     rbx, rax
0x140255d3e  test    rax, rax
0x140255d41  jz      loc_140255F32
0x140255d47  lea     rax, [rsi-180h]
0x140255d4e  mov     [rbp+50h+ObjectAttributes.Length], 30h ; '0'
0x140255d55  mov     [rsp+150h+DeviceObject], rax; DeviceObject
0x140255d5a  lea     rcx, [rbp+50h+Destination]
0x140255d5e  mov     [rsp+150h+Options], 101h; Options
0x140255d66  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x140255d6a  mov     [rsp+150h+InternalParameters], r14; InternalParameters
0x140255d6f  lea     r8, [rbp+50h+ObjectAttributes]; ObjectAttributes
0x140255d73  mov     [rsp+150h+CreateFileType], r14d; CreateFileType
0x140255d78  xorps   xmm0, xmm0
0x140255d7b  mov     [rsp+150h+EaLength], r14d; EaLength
0x140255d80  mov     edx, 100001h; DesiredAccess
0x140255d85  mov     [rsp+150h+EaBuffer], r14; EaBuffer
0x140255d8a  mov     [rsp+150h+CreateOptions], 21h ; '!'; CreateOptions
0x140255d92  mov     [rsp+150h+Disposition], 1; Disposition
0x140255d9a  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x140255da2  mov     [rbp+50h+ObjectAttributes.ObjectName], rcx
0x140255da6  lea     rcx, [rbp+50h+FileHandle]; FileHandle
0x140255daa  mov     [rsp+150h+FileAttributes], 14h; FileAttributes
0x140255db2  mov     [rsp+150h+AllocationSize], r14; AllocationSize
0x140255db7  mov     [rbp+50h+ObjectAttributes.RootDirectory], r14
0x140255dbb  mov     [rbp+50h+ObjectAttributes.Attributes], 240h
0x140255dc2  movdqu  xmmword ptr [rbp+50h+ObjectAttributes.SecurityDescriptor], xmm0
0x140255dc7  call    cs:__imp_IoCreateFileSpecifyDeviceObjectHint
0x140255dce  nop     dword ptr [rax+rax+00h]
0x140255dd3  mov     ecx, [r15+10h]
0x140255dd7  mov     edi, eax
0x140255dd9  bt      rcx, 14h
0x140255dde  jb      short loc_140255E18
0x140255de0  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x140255de7  jz      short loc_140255E18
0x140255de9  movzx   ecx, [rbp+50h+Destination.Length]
0x140255ded  lea     rdx, fsctrl_c44128
0x140255df4  mov     r9, gs:188h
0x140255dfd  mov     r8, rsi
0x140255e00  mov     rax, [rbp+50h+Destination.Buffer]
0x140255e04  mov     qword ptr [rsp+150h+ShareAccess], rax
0x140255e09  shr     ecx, 1
0x140255e0b  mov     [rsp+150h+FileAttributes], ecx
0x140255e0f  mov     dword ptr [rsp+150h+AllocationSize], edi
0x140255e13  call    McTemplateU0ppdw_EtwWriteTransfer
0x140255e18  test    edi, edi
0x140255e1a  js      loc_140255F32
0x140255e20  mov     r13b, 1
0x140255e23  mov     r8d, r12d; Size
0x140255e26  xor     edx, edx; Val
0x140255e28  mov     rcx, rbx; void *
0x140255e2b  call    memset
0x140255e30  mov     rcx, [rbp+50h+FileHandle]; FileHandle
0x140255e34  lea     rax, [rbp+50h+IoStatusBlock]
0x140255e38  mov     byte ptr [rsp+150h+EaLength], r13b; RestartScan
0x140255e3d  xor     r9d, r9d; ApcContext
0x140255e40  mov     [rsp+150h+EaBuffer], r14; FileName
0x140255e45  xor     r8d, r8d; ApcRoutine
0x140255e48  mov     byte ptr [rsp+150h+CreateOptions], r14b; ReturnSingleEntry
0x140255e4d  xor     edx, edx; Event
0x140255e4f  mov     [rsp+150h+Disposition], 0Ch; FileInformationClass
0x140255e57  mov     [rsp+150h+ShareAccess], r12d; Length
0x140255e5c  mov     qword ptr [rsp+150h+FileAttributes], rbx; FileInformation
0x140255e61  mov     [rsp+150h+AllocationSize], rax; IoStatusBlock
0x140255e66  call    cs:__imp_ZwQueryDirectoryFile
0x140255e6d  nop     dword ptr [rax+rax+00h]
0x140255e72  mov     ecx, [r15+10h]
0x140255e76  mov     edi, eax
0x140255e78  bt      rcx, 14h
0x140255e7d  jb      short loc_140255EA4
0x140255e7f  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x140255e86  jz      short loc_140255EA4
0x140255e88  mov     r9, gs:188h
0x140255e91  lea     rdx, fsctrl_c44164
0x140255e98  mov     r8, rsi
0x140255e9b  mov     dword ptr [rsp+150h+AllocationSize], eax
0x140255e9f  call    McTemplateU0ppd_EtwWriteTransfer
0x140255ea4  cmp     edi, 80000005h
0x140255eaa  jnz     loc_140255F7E
0x140255eb0  xor     edx, edx; Tag
0x140255eb2  mov     rcx, rbx; P
0x140255eb5  call    cs:__imp_ExFreePoolWithTag
0x140255ebc  nop     dword ptr [rax+rax+00h]
0x140255ec1  mov     ecx, cs:PoolType; PoolType
0x140255ec7  lea     eax, [r12+r12]
0x140255ecb  mov     r12d, eax
0x140255ece  mov     r8d, 6646744Eh; Tag
0x140255ed4  mov     edx, eax; NumberOfBytes
0x140255ed6  mov     [rbp+50h+arg_18], r12
0x140255eda  call    cs:__imp_ExAllocatePoolWithTag
0x140255ee1  nop     dword ptr [rax+rax+00h]
0x140255ee6  mov     rbx, rax
0x140255ee9  test    rax, rax
0x140255eec  jnz     loc_140255E23
0x140255ef2  mov     rcx, [rbp+50h+FileHandle]; Handle
0x140255ef6  call    cs:__imp_ZwClose
0x140255efd  nop     dword ptr [rax+rax+00h]
0x140255f02  mov     ecx, [r15+10h]
0x140255f06  bt      rcx, 14h
0x140255f0b  jb      short loc_140255F32
0x140255f0d  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x140255f14  jz      short loc_140255F32
0x140255f16  mov     r9, gs:188h
0x140255f1f  lea     rdx, fsctrl_c44271
0x140255f26  mov     r8, rsi
0x140255f29  mov     dword ptr [rsp+150h+AllocationSize], eax
0x140255f2d  call    McTemplateU0ppd_EtwWriteTransfer
0x140255f32  mov     rax, [rbp+50h+Destination.Buffer]
0x140255f36  test    rax, rax
0x140255f39  jz      short loc_140255F4C
0x140255f3b  xor     edx, edx; Tag
0x140255f3d  mov     rcx, rax; P
0x140255f40  call    cs:__imp_ExFreePoolWithTag
0x140255f47  nop     dword ptr [rax+rax+00h]
0x140255f4c  test    rbx, rbx
0x140255f4f  jz      short loc_140255F62
0x140255f51  xor     edx, edx; Tag
0x140255f53  mov     rcx, rbx; P
0x140255f56  call    cs:__imp_ExFreePoolWithTag
0x140255f5d  nop     dword ptr [rax+rax+00h]
0x140255f62  mov     rbx, [rsp+150h+arg_8]
0x140255f6a  add     rsp, 120h
0x140255f71  pop     r15
0x140255f73  pop     r14
0x140255f75  pop     r13
0x140255f77  pop     r12
0x140255f79  pop     rdi
0x140255f7a  pop     rsi
0x140255f7b  pop     rbp
0x140255f7c  retn
0x140255f7e  test    edi, edi
0x140255f80  js      loc_140255EF2
0x140255f86  mov     r13b, r14b
0x140255f89  lea     r12, [rsi-180h]
0x140255f90  mov     rdi, rbx
0x140255f93  lea     rax, [rdi+0Ch]
0x140255f97  mov     r8b, 1; CaseInSensitive
0x140255f9a  mov     [rbp+50h+String2.Buffer], rax
0x140255f9e  lea     rdx, [rbp+50h+String2]; String2
0x140255fa2  movzx   eax, word ptr [rdi+8]
0x140255fa6  lea     rcx, [rbp+50h+DestinationString]; String1
0x140255faa  mov     [rbp+50h+String2.MaximumLength], ax
0x140255fae  movzx   eax, word ptr [rdi+8]
0x140255fb2  mov     [rbp+50h+String2.Length], ax
0x140255fb6  call    cs:__imp_RtlPrefixUnicodeString
0x140255fbd  nop     dword ptr [rax+rax+00h]
0x140255fc2  test    al, al
0x140255fc4  jnz     loc_1402560E1
0x140255fca  mov     rax, [rbp+50h+FileHandle]
0x140255fce  lea     r9, [rbp+50h+IoStatusBlock]; IoStatusBlock
0x140255fd2  mov     [rsp+150h+DeviceObject], r12; DeviceObject
0x140255fd7  lea     r8, [rbp+50h+var_70]; ObjectAttributes
0x140255fdb  mov     [rsp+150h+Options], 100h; Options
0x140255fe3  lea     rcx, [rbp+50h+Handle]; FileHandle
0x140255fe7  mov     [rsp+150h+InternalParameters], r14; InternalParameters
0x140255fec  xorps   xmm0, xmm0
0x140255fef  mov     [rsp+150h+CreateFileType], r14d; CreateFileType
0x140255ff4  mov     edx, 10000h; DesiredAccess
0x140255ff9  mov     [rsp+150h+EaLength], r14d; EaLength
0x140255ffe  mov     [rsp+150h+EaBuffer], r14; EaBuffer
0x140256003  mov     [rsp+150h+CreateOptions], 201020h; CreateOptions
0x14025600b  mov     [rsp+150h+Disposition], 1; Disposition
0x140256013  mov     [rbp+50h+var_70.RootDirectory], rax
0x140256017  lea     rax, [rbp+50h+String2]
0x14025601b  mov     [rsp+150h+ShareAccess], 7; ShareAccess
0x140256023  mov     [rsp+150h+FileAttributes], 80h; FileAttributes
0x14025602b  mov     [rsp+150h+AllocationSize], r14; AllocationSize
0x140256030  mov     [rbp+50h+var_70.Length], 30h ; '0'
0x140256037  mov     [rbp+50h+var_70.Attributes], 240h
0x14025603e  mov     [rbp+50h+var_70.ObjectName], rax
0x140256042  movdqu  xmmword ptr [rbp+50h+var_70.SecurityDescriptor], xmm0
0x140256047  call    cs:__imp_IoCreateFileSpecifyDeviceObjectHint
0x14025604e  nop     dword ptr [rax+rax+00h]
0x140256053  mov     ecx, [r15+10h]
0x140256057  mov     r14d, eax
0x14025605a  bt      rcx, 14h
0x14025605f  jb      short loc_140256099
0x140256061  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x140256068  jz      short loc_140256099
0x14025606a  movzx   edx, [rbp+50h+String2.Length]
0x14025606e  mov     r8, rsi
0x140256071  mov     r9, gs:188h
0x14025607a  mov     rcx, [rbp+50h+String2.Buffer]
0x14025607e  shr     edx, 1
0x140256080  mov     qword ptr [rsp+150h+ShareAccess], rcx
0x140256085  mov     [rsp+150h+FileAttributes], edx
0x140256089  lea     rdx, fsctrl_c44240
0x140256090  mov     dword ptr [rsp+150h+AllocationSize], eax
0x140256094  call    McTemplateU0ppdw_EtwWriteTransfer
0x140256099  test    r14d, r14d
0x14025609c  js      short loc_1402560DE
0x14025609e  mov     rcx, [rbp+50h+Handle]; Handle
0x1402560a2  call    cs:__imp_ZwClose
0x1402560a9  nop     dword ptr [rax+rax+00h]
0x1402560ae  mov     ecx, [r15+10h]
0x1402560b2  bt      rcx, 14h
0x1402560b7  jb      short loc_1402560DE
0x1402560b9  test    byte ptr cs:Microsoft_Windows_NtfsLog_43345c4f859f3d6790af3cfb07b93456EnableBits+3, 40h
0x1402560c0  jz      short loc_1402560DE
0x1402560c2  mov     r9, gs:188h
0x1402560cb  lea     rdx, fsctrl_c44253
0x1402560d2  mov     r8, rsi
0x1402560d5  mov     dword ptr [rsp+150h+AllocationSize], eax
0x1402560d9  call    McTemplateU0ppd_EtwWriteTransfer
0x1402560de  xor     r14d, r14d
0x1402560e1  mov     eax, [rdi]
0x1402560e3  add     rdi, rax
0x1402560e6  test    eax, eax
0x1402560e8  jnz     loc_140255F93
0x1402560ee  mov     r12, [rbp+50h+arg_18]
0x1402560f2  jmp     loc_140255E23
```
