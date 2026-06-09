# HsmpRelativeStreamOpen

- ea: `0x14005eb40`
- end: `0x14005eed7`
- name: `HsmpRelativeStreamOpen`
- size: `919`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, int, void *FileHandle, __int64, __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140035184`
- `0x140035610`
- `0x140054a9c`
- `0x14005cf90`
- `0x14005f74c`
- `0x14006037c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e2d0`
- `0x14005eb40`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005ec37`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005ec37`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eda8`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eeb5`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eda8`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eeb5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ecba`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ecba`
- `ntoskrnl!ExAllocatePool2` at `0x14005ebfc`
- `ntoskrnl!ExAllocatePool2` at `0x14005ebfc`
- `FLTMGR!FltCreateFileEx` at `0x14005ed5c`
- `FLTMGR!FltCreateFileEx` at `0x14005ed5c`
- `FLTMGR!FltClose` at `0x14005edbc`
- `FLTMGR!FltClose` at `0x14005eec6`
- `FLTMGR!FltClose` at `0x14005edbc`
- `FLTMGR!FltClose` at `0x14005eec6`
- `FLTMGR!FltQueryInformationFile` at `0x14005eb86`
- `FLTMGR!FltQueryInformationFile` at `0x14005eb86`

## pseudocode

```c
__int64 __fastcall HsmpRelativeStreamOpen(
        __int64 a1,
        struct _FILE_OBJECT *a2,
        struct _UNICODE_STRING *a3,
        ACCESS_MASK a4,
        ULONG CreateDisposition,
        int a6,
        void *FileHandle,
        _QWORD *a8,
        PFILE_OBJECT *a9)
{
  struct _FLT_INSTANCE *v11; // rcx
  unsigned int v12; // edi
  __int64 v13; // r13
  __int16 v14; // ax
  HANDLE v15; // rsi
  struct _FILE_OBJECT *v16; // r14
  struct _FLT_INSTANCE *v17; // rdx
  struct _FLT_INSTANCE *v18; // rdx
  __int64 FileInformationClass; // [rsp+20h] [rbp-C9h]
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-69h] BYREF
  HANDLE v22; // [rsp+90h] [rbp-59h] BYREF
  PVOID Object; // [rsp+98h] [rbp-51h] BYREF
  __int64 FileInformation; // [rsp+A0h] [rbp-49h] BYREF
  struct _FLT_INSTANCE *v25; // [rsp+A8h] [rbp-41h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E0h] [rbp-9h] BYREF
  PFILE_OBJECT FileObject; // [rsp+130h] [rbp+47h] BYREF
  ACCESS_MASK DesiredAccess; // [rsp+148h] [rbp+5Fh]

  DesiredAccess = a4;
  v11 = *(struct _FLT_INSTANCE **)(a1 + 32);
  FileInformation = 0;
  v12 = FltQueryInformationFile(v11, a2, &FileInformation, 8u, FileInternalInformation, 0);
  HsmDbgBreakOnStatus(v12);
  if ( (v12 & 0x80000000) != 0 )
    return v12;
  v13 = FileInformation;
  v22 = 0;
  v25 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v14 = *(_WORD *)(a1 + 64);
  v15 = 0;
  *(&DestinationString.MaximumLength + 2) = 0;
  Object = 0;
  v16 = 0;
  *(_DWORD *)&DestinationString.MaximumLength = (unsigned __int16)(v14 + 8);
  memset(&ObjectAttributes, 0, 44);
  FileHandle = 0;
  FileObject = 0;
  IoStatusBlock = 0;
  DestinationString.Length = 0;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, (unsigned __int16)(v14 + 8), 1934979912);
  v12 = DestinationString.Buffer == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus(v12);
  if ( DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1 + 64));
    v17 = v25;
    *(_QWORD *)((char *)DestinationString.Buffer + DestinationString.Length) = v13;
    DestinationString.Length += 8;
    v12 = HsmiOpenFile(
            a1,
            v17,
            &DestinationString,
            0x100080u,
            FileInformationClass,
            0x202100u,
            a3 == 0,
            &v22,
            (PFILE_OBJECT *)&Object);
    HsmDbgBreakOnStatus(v12);
    if ( (v12 & 0x80000000) != 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, v13);
    }
    v16 = (struct _FILE_OBJECT *)Object;
    v15 = v22;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, v13);
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
  HsmDbgBreakOnStatus(v12);
  if ( (v12 & 0x80000000) != 0 )
    goto LABEL_14;
  if ( a3 )
  {
    v18 = *(struct _FLT_INSTANCE **)(a1 + 32);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v15;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = a3;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v12 = FltCreateFileEx(
            Filter,
            v18,
            &FileHandle,
            &FileObject,
            DesiredAccess,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0,
            7u,
            CreateDisposition,
            a6 | 0x200000,
            0,
            0,
            0x840u);
    HsmDbgBreakOnStatus(v12);
    if ( (v12 & 0x80000000) == 0 )
    {
      if ( a9 )
      {
        *a9 = FileObject;
        FileObject = 0;
      }
      if ( a8 )
      {
        *a8 = FileHandle;
        FileHandle = 0;
      }
    }
LABEL_14:
    if ( v16 )
      ObfDereferenceObject(v16);
    if ( v15 )
      FltClose(v15);
    goto LABEL_18;
  }
  *a9 = v16;
  *a8 = v15;
LABEL_18:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  HsmDbgBreakOnStatus(v12);
  return v12;
}

```

## disassembly

```asm
0x14005eb40  mov     [rsp-8+arg_8], rbx
0x14005eb45  mov     [rsp-8+DesiredAccess], r9d
0x14005eb4a  push    rbp
0x14005eb4b  push    rsi
0x14005eb4c  push    rdi
0x14005eb4d  push    r12
0x14005eb4f  push    r13
0x14005eb51  push    r14
0x14005eb53  push    r15
0x14005eb55  lea     rbp, [rsp-7]
0x14005eb5a  sub     rsp, 0F0h
0x14005eb61  xor     ebx, ebx
0x14005eb63  mov     r12, r8
0x14005eb66  mov     r15, rcx
0x14005eb69  mov     [rsp+120h+LengthReturned], rbx; LengthReturned
0x14005eb6e  mov     rcx, [rcx+20h]; Instance
0x14005eb72  lea     r8, [rbp+37h+FileInformation]; FileInformation
0x14005eb76  mov     [rbp+37h+FileInformation], rbx
0x14005eb7a  lea     r9d, [rbx+8]; Length
0x14005eb7e  mov     [rsp+120h+FileInformationClass], 6; FileInformationClass
0x14005eb86  call    cs:__imp_FltQueryInformationFile
0x14005eb8d  nop     dword ptr [rax+rax+00h]
0x14005eb92  mov     ecx, eax
0x14005eb94  mov     edi, eax
0x14005eb96  call    HsmDbgBreakOnStatus
0x14005eb9b  test    edi, edi
0x14005eb9d  js      loc_14005EDE9
0x14005eba3  mov     r13, [rbp+37h+FileInformation]
0x14005eba7  xorps   xmm0, xmm0
0x14005ebaa  xor     eax, eax
0x14005ebac  mov     [rbp+37h+var_90], rbx
0x14005ebb0  mov     rax, [r15+20h]
0x14005ebb4  mov     ecx, 100h
0x14005ebb9  mov     [rbp+37h+var_78], rax
0x14005ebbd  mov     r8d, 73557348h
0x14005ebc3  movzx   eax, word ptr [r15+40h]
0x14005ebc8  mov     esi, ebx
0x14005ebca  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x14005ebce  add     ax, 8
0x14005ebd2  mov     [rbp+37h+Object], rbx
0x14005ebd6  movzx   edx, ax
0x14005ebd9  mov     r14d, ebx
0x14005ebdc  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x14005ebe0  mov     [rbp+37h+DestinationString.MaximumLength], dx
0x14005ebe4  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x14005ebe8  mov     [rbp+37h+FileHandle], rbx
0x14005ebec  movups  xmmword ptr [rbp+37h+ObjectAttributes+1Ch], xmm0
0x14005ebf0  mov     [rbp+37h+FileObject], rbx
0x14005ebf4  movups  xmmword ptr [rbp+37h+var_40], xmm0
0x14005ebf8  mov     [rbp+37h+DestinationString.Length], bx
0x14005ebfc  call    cs:__imp_ExAllocatePool2
0x14005ec03  nop     dword ptr [rax+rax+00h]
0x14005ec08  mov     rcx, rax
0x14005ec0b  mov     [rbp+37h+DestinationString.Buffer], rax
0x14005ec0f  neg     rcx
0x14005ec12  mov     rbx, rax
0x14005ec15  sbb     edi, edi
0x14005ec17  not     edi
0x14005ec19  and     edi, 0C000009Ah
0x14005ec1f  mov     ecx, edi
0x14005ec21  call    HsmDbgBreakOnStatus
0x14005ec26  test    rbx, rbx
0x14005ec29  jz      loc_14005EE1A
0x14005ec2f  lea     rdx, [r15+40h]; SourceString
0x14005ec33  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x14005ec37  call    cs:__imp_RtlCopyUnicodeString
0x14005ec3e  nop     dword ptr [rax+rax+00h]
0x14005ec43  movzx   ecx, [rbp+37h+DestinationString.Length]
0x14005ec47  lea     esi, [r14+8]
0x14005ec4b  mov     rax, [rbp+37h+DestinationString.Buffer]
0x14005ec4f  lea     r8, [rbp+37h+DestinationString]
0x14005ec53  mov     rdx, [rbp+37h+var_78]
0x14005ec57  xor     ebx, ebx
0x14005ec59  mov     r9d, 100080h
0x14005ec5f  mov     [rcx+rax], r13
0x14005ec63  lea     rcx, [rbp+37h+Object]
0x14005ec67  add     [rbp+37h+DestinationString.Length], si
0x14005ec6b  mov     qword ptr [rsp+120h+FileAttributes], rcx
0x14005ec70  test    r12, r12
0x14005ec73  lea     rcx, [rbp+37h+var_90]
0x14005ec77  mov     [rsp+120h+AllocationSize], rcx
0x14005ec7c  setz    al
0x14005ec7f  mov     byte ptr [rsp+120h+IoStatusBlock], al
0x14005ec83  mov     rcx, r15
0x14005ec86  mov     dword ptr [rsp+120h+LengthReturned], 202100h
0x14005ec8e  call    HsmiOpenFile
0x14005ec93  mov     ecx, eax
0x14005ec95  mov     edi, eax
0x14005ec97  call    HsmDbgBreakOnStatus
0x14005ec9c  test    edi, edi
0x14005ec9e  js      loc_14005EE62
0x14005eca4  mov     r14, [rbp+37h+Object]
0x14005eca8  mov     rsi, [rbp+37h+var_90]
0x14005ecac  mov     rcx, [rbp+37h+DestinationString.Buffer]; P
0x14005ecb0  test    rcx, rcx
0x14005ecb3  jz      short loc_14005ECC6
0x14005ecb5  mov     edx, 73557348h; Tag
0x14005ecba  call    cs:__imp_ExFreePoolWithTag
0x14005ecc1  nop     dword ptr [rax+rax+00h]
0x14005ecc6  mov     ecx, edi
0x14005ecc8  call    HsmDbgBreakOnStatus
0x14005eccd  test    edi, edi
0x14005eccf  js      loc_14005EDA0
0x14005ecd5  test    r12, r12
0x14005ecd8  jz      loc_14005EE07
0x14005ecde  mov     eax, [rbp+37h+arg_28]
0x14005ece1  lea     r9, [rbp+37h+FileObject]; FileObject
0x14005ece5  mov     rdx, [r15+20h]; Instance
0x14005ece9  lea     r8, [rbp+37h+FileHandle]; FileHandle
0x14005eced  mov     rcx, cs:Filter; Filter
0x14005ecf4  bts     eax, 15h
0x14005ecf8  mov     [rsp+120h+Flags], 840h; Flags
0x14005ed00  xorps   xmm0, xmm0
0x14005ed03  mov     [rsp+120h+EaLength], ebx; EaLength
0x14005ed07  mov     [rsp+120h+EaBuffer], rbx; EaBuffer
0x14005ed0c  mov     [rsp+120h+CreateOptions], eax; CreateOptions
0x14005ed10  mov     eax, [rbp+37h+arg_20]
0x14005ed13  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x14005ed17  lea     rax, [rbp+37h+var_40]
0x14005ed1b  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14005ed23  mov     [rsp+120h+FileAttributes], ebx; FileAttributes
0x14005ed27  mov     [rsp+120h+AllocationSize], rbx; AllocationSize
0x14005ed2c  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14005ed31  lea     rax, [rbp+37h+ObjectAttributes]
0x14005ed35  mov     [rsp+120h+LengthReturned], rax; ObjectAttributes
0x14005ed3a  mov     eax, [rbp+37h+DesiredAccess]
0x14005ed3d  mov     [rsp+120h+FileInformationClass], eax; DesiredAccess
0x14005ed41  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x14005ed48  mov     [rbp+37h+ObjectAttributes.RootDirectory], rsi
0x14005ed4c  mov     [rbp+37h+ObjectAttributes.Attributes], 200h
0x14005ed53  mov     [rbp+37h+ObjectAttributes.ObjectName], r12
0x14005ed57  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005ed5c  call    cs:__imp_FltCreateFileEx
0x14005ed63  nop     dword ptr [rax+rax+00h]
0x14005ed68  mov     ecx, eax
0x14005ed6a  mov     edi, eax
0x14005ed6c  call    HsmDbgBreakOnStatus
0x14005ed71  test    edi, edi
0x14005ed73  js      short loc_14005EDA0
0x14005ed75  mov     rcx, [rbp+37h+arg_40]
0x14005ed7c  test    rcx, rcx
0x14005ed7f  jz      short loc_14005ED8C
0x14005ed81  mov     rax, [rbp+37h+FileObject]
0x14005ed85  mov     [rcx], rax
0x14005ed88  mov     [rbp+37h+FileObject], rbx
0x14005ed8c  mov     rcx, [rbp+37h+arg_38]
0x14005ed90  test    rcx, rcx
0x14005ed93  jz      short loc_14005EDA0
0x14005ed95  mov     rax, [rbp+37h+FileHandle]
0x14005ed99  mov     [rcx], rax
0x14005ed9c  mov     [rbp+37h+FileHandle], rbx
0x14005eda0  test    r14, r14
0x14005eda3  jz      short loc_14005EDB4
0x14005eda5  mov     rcx, r14; Object
0x14005eda8  call    cs:__imp_ObfDereferenceObject
0x14005edaf  nop     dword ptr [rax+rax+00h]
0x14005edb4  test    rsi, rsi
0x14005edb7  jz      short loc_14005EDC8
0x14005edb9  mov     rcx, rsi; FileHandle
0x14005edbc  call    cs:__imp_FltClose
0x14005edc3  nop     dword ptr [rax+rax+00h]
0x14005edc8  mov     rcx, [rbp+37h+FileObject]; Object
0x14005edcc  test    rcx, rcx
0x14005edcf  jnz     loc_14005EEB5
0x14005edd5  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x14005edd9  test    rcx, rcx
0x14005eddc  jnz     loc_14005EEC6
0x14005ede2  mov     ecx, edi
0x14005ede4  call    HsmDbgBreakOnStatus
0x14005ede9  mov     rbx, [rsp+120h+arg_8]
0x14005edf1  mov     eax, edi
0x14005edf3  add     rsp, 0F0h
0x14005edfa  pop     r15
0x14005edfc  pop     r14
0x14005edfe  pop     r13
0x14005ee00  pop     r12
0x14005ee02  pop     rdi
0x14005ee03  pop     rsi
0x14005ee04  pop     rbp
0x14005ee05  retn
0x14005ee07  mov     rax, [rbp+37h+arg_40]
0x14005ee0e  mov     [rax], r14
0x14005ee11  mov     rax, [rbp+37h+arg_38]
0x14005ee15  mov     [rax], rsi
0x14005ee18  jmp     short loc_14005EDC8
0x14005ee1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ee21  lea     rax, WPP_GLOBAL_Control
0x14005ee28  cmp     rcx, rax
0x14005ee2b  jz      short loc_14005EE5B
0x14005ee2d  mov     eax, [rcx+2Ch]
0x14005ee30  test    al, 8
0x14005ee32  jz      short loc_14005EE5B
0x14005ee34  cmp     byte ptr [rcx+29h], 2
0x14005ee38  jb      short loc_14005EE5B
0x14005ee3a  mov     rcx, [rcx+18h]
0x14005ee3e  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005ee45  mov     edx, 1Bh
0x14005ee4a  mov     dword ptr [rsp+120h+LengthReturned], edi
0x14005ee4e  mov     r9, r15
0x14005ee51  mov     qword ptr [rsp+120h+FileInformationClass], r13
0x14005ee56  call    WPP_SF_qqd
0x14005ee5b  xor     ebx, ebx
0x14005ee5d  jmp     loc_14005ECAC
0x14005ee62  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ee69  lea     rax, WPP_GLOBAL_Control
0x14005ee70  cmp     rcx, rax
0x14005ee73  jz      loc_14005ECA4
0x14005ee79  mov     eax, [rcx+2Ch]
0x14005ee7c  test    sil, al
0x14005ee7f  jz      loc_14005ECA4
0x14005ee85  cmp     byte ptr [rcx+29h], 2
0x14005ee89  jb      loc_14005ECA4
0x14005ee8f  mov     rcx, [rcx+18h]
0x14005ee93  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005ee9a  mov     edx, 1Ch
0x14005ee9f  mov     dword ptr [rsp+120h+LengthReturned], edi
0x14005eea3  mov     r9, r15
0x14005eea6  mov     qword ptr [rsp+120h+FileInformationClass], r13
0x14005eeab  call    WPP_SF_qqd
0x14005eeb0  jmp     loc_14005ECA4
0x14005eeb5  call    cs:__imp_ObfDereferenceObject
0x14005eebc  nop     dword ptr [rax+rax+00h]
0x14005eec1  jmp     loc_14005EDD5
0x14005eec6  call    cs:__imp_FltClose
0x14005eecd  nop     dword ptr [rax+rax+00h]
0x14005eed2  jmp     loc_14005EDE2
```
