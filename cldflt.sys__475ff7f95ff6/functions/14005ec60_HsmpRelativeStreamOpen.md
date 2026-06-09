# HsmpRelativeStreamOpen

- ea: `0x14005ec60`
- end: `0x14005eff7`
- name: `HsmpRelativeStreamOpen`
- size: `919`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, int, void *FileHandle, __int64, __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140035184`
- `0x140035610`
- `0x140054bbc`
- `0x14005d0b0`
- `0x14005f86c`
- `0x14006049c`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e3f0`
- `0x14005ec60`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005ed57`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005ed57`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eec8`
- `ntoskrnl!ObfDereferenceObject` at `0x14005efd5`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eec8`
- `ntoskrnl!ObfDereferenceObject` at `0x14005efd5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005edda`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005edda`
- `ntoskrnl!ExAllocatePool2` at `0x14005ed1c`
- `ntoskrnl!ExAllocatePool2` at `0x14005ed1c`
- `FLTMGR!FltCreateFileEx` at `0x14005ee7c`
- `FLTMGR!FltCreateFileEx` at `0x14005ee7c`
- `FLTMGR!FltClose` at `0x14005eedc`
- `FLTMGR!FltClose` at `0x14005efe6`
- `FLTMGR!FltClose` at `0x14005eedc`
- `FLTMGR!FltClose` at `0x14005efe6`
- `FLTMGR!FltQueryInformationFile` at `0x14005eca6`
- `FLTMGR!FltQueryInformationFile` at `0x14005eca6`

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
  int v12; // edi
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
  if ( v12 < 0 )
    return (unsigned int)v12;
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
    if ( v12 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, v13, v12);
    }
    v16 = (struct _FILE_OBJECT *)Object;
    v15 = v22;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, v13, v12);
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
  HsmDbgBreakOnStatus(v12);
  if ( v12 < 0 )
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
    if ( v12 >= 0 )
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
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14005ec60  mov     [rsp-8+arg_8], rbx
0x14005ec65  mov     [rsp-8+DesiredAccess], r9d
0x14005ec6a  push    rbp
0x14005ec6b  push    rsi
0x14005ec6c  push    rdi
0x14005ec6d  push    r12
0x14005ec6f  push    r13
0x14005ec71  push    r14
0x14005ec73  push    r15
0x14005ec75  lea     rbp, [rsp-7]
0x14005ec7a  sub     rsp, 0F0h
0x14005ec81  xor     ebx, ebx
0x14005ec83  mov     r12, r8
0x14005ec86  mov     r15, rcx
0x14005ec89  mov     [rsp+120h+LengthReturned], rbx; LengthReturned
0x14005ec8e  mov     rcx, [rcx+20h]; Instance
0x14005ec92  lea     r8, [rbp+37h+FileInformation]; FileInformation
0x14005ec96  mov     [rbp+37h+FileInformation], rbx
0x14005ec9a  lea     r9d, [rbx+8]; Length
0x14005ec9e  mov     [rsp+120h+FileInformationClass], 6; FileInformationClass
0x14005eca6  call    cs:__imp_FltQueryInformationFile
0x14005ecad  nop     dword ptr [rax+rax+00h]
0x14005ecb2  mov     ecx, eax
0x14005ecb4  mov     edi, eax
0x14005ecb6  call    HsmDbgBreakOnStatus
0x14005ecbb  test    edi, edi
0x14005ecbd  js      loc_14005EF09
0x14005ecc3  mov     r13, [rbp+37h+FileInformation]
0x14005ecc7  xorps   xmm0, xmm0
0x14005ecca  xor     eax, eax
0x14005eccc  mov     [rbp+37h+var_90], rbx
0x14005ecd0  mov     rax, [r15+20h]
0x14005ecd4  mov     ecx, 100h
0x14005ecd9  mov     [rbp+37h+var_78], rax
0x14005ecdd  mov     r8d, 73557348h
0x14005ece3  movzx   eax, word ptr [r15+40h]
0x14005ece8  mov     esi, ebx
0x14005ecea  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x14005ecee  add     ax, 8
0x14005ecf2  mov     [rbp+37h+Object], rbx
0x14005ecf6  movzx   edx, ax
0x14005ecf9  mov     r14d, ebx
0x14005ecfc  movups  xmmword ptr [rbp+37h+ObjectAttributes.ObjectName], xmm0
0x14005ed00  mov     [rbp+37h+DestinationString.MaximumLength], dx
0x14005ed04  movups  xmmword ptr [rbp+37h+ObjectAttributes.Length], xmm0
0x14005ed08  mov     [rbp+37h+FileHandle], rbx
0x14005ed0c  movups  xmmword ptr [rbp+37h+ObjectAttributes+1Ch], xmm0
0x14005ed10  mov     [rbp+37h+FileObject], rbx
0x14005ed14  movups  xmmword ptr [rbp+37h+var_40], xmm0
0x14005ed18  mov     [rbp+37h+DestinationString.Length], bx
0x14005ed1c  call    cs:__imp_ExAllocatePool2
0x14005ed23  nop     dword ptr [rax+rax+00h]
0x14005ed28  mov     rcx, rax
0x14005ed2b  mov     [rbp+37h+DestinationString.Buffer], rax
0x14005ed2f  neg     rcx
0x14005ed32  mov     rbx, rax
0x14005ed35  sbb     edi, edi
0x14005ed37  not     edi
0x14005ed39  and     edi, 0C000009Ah
0x14005ed3f  mov     ecx, edi
0x14005ed41  call    HsmDbgBreakOnStatus
0x14005ed46  test    rbx, rbx
0x14005ed49  jz      loc_14005EF3A
0x14005ed4f  lea     rdx, [r15+40h]; SourceString
0x14005ed53  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x14005ed57  call    cs:__imp_RtlCopyUnicodeString
0x14005ed5e  nop     dword ptr [rax+rax+00h]
0x14005ed63  movzx   ecx, [rbp+37h+DestinationString.Length]
0x14005ed67  lea     esi, [r14+8]
0x14005ed6b  mov     rax, [rbp+37h+DestinationString.Buffer]
0x14005ed6f  lea     r8, [rbp+37h+DestinationString]
0x14005ed73  mov     rdx, [rbp+37h+var_78]
0x14005ed77  xor     ebx, ebx
0x14005ed79  mov     r9d, 100080h
0x14005ed7f  mov     [rcx+rax], r13
0x14005ed83  lea     rcx, [rbp+37h+Object]
0x14005ed87  add     [rbp+37h+DestinationString.Length], si
0x14005ed8b  mov     qword ptr [rsp+120h+FileAttributes], rcx
0x14005ed90  test    r12, r12
0x14005ed93  lea     rcx, [rbp+37h+var_90]
0x14005ed97  mov     [rsp+120h+AllocationSize], rcx
0x14005ed9c  setz    al
0x14005ed9f  mov     byte ptr [rsp+120h+IoStatusBlock], al
0x14005eda3  mov     rcx, r15
0x14005eda6  mov     dword ptr [rsp+120h+LengthReturned], 202100h
0x14005edae  call    HsmiOpenFile
0x14005edb3  mov     ecx, eax
0x14005edb5  mov     edi, eax
0x14005edb7  call    HsmDbgBreakOnStatus
0x14005edbc  test    edi, edi
0x14005edbe  js      loc_14005EF82
0x14005edc4  mov     r14, [rbp+37h+Object]
0x14005edc8  mov     rsi, [rbp+37h+var_90]
0x14005edcc  mov     rcx, [rbp+37h+DestinationString.Buffer]; P
0x14005edd0  test    rcx, rcx
0x14005edd3  jz      short loc_14005EDE6
0x14005edd5  mov     edx, 73557348h; Tag
0x14005edda  call    cs:__imp_ExFreePoolWithTag
0x14005ede1  nop     dword ptr [rax+rax+00h]
0x14005ede6  mov     ecx, edi
0x14005ede8  call    HsmDbgBreakOnStatus
0x14005eded  test    edi, edi
0x14005edef  js      loc_14005EEC0
0x14005edf5  test    r12, r12
0x14005edf8  jz      loc_14005EF27
0x14005edfe  mov     eax, [rbp+37h+arg_28]
0x14005ee01  lea     r9, [rbp+37h+FileObject]; FileObject
0x14005ee05  mov     rdx, [r15+20h]; Instance
0x14005ee09  lea     r8, [rbp+37h+FileHandle]; FileHandle
0x14005ee0d  mov     rcx, cs:Filter; Filter
0x14005ee14  bts     eax, 15h
0x14005ee18  mov     [rsp+120h+Flags], 840h; Flags
0x14005ee20  xorps   xmm0, xmm0
0x14005ee23  mov     [rsp+120h+EaLength], ebx; EaLength
0x14005ee27  mov     [rsp+120h+EaBuffer], rbx; EaBuffer
0x14005ee2c  mov     [rsp+120h+CreateOptions], eax; CreateOptions
0x14005ee30  mov     eax, [rbp+37h+arg_20]
0x14005ee33  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x14005ee37  lea     rax, [rbp+37h+var_40]
0x14005ee3b  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14005ee43  mov     [rsp+120h+FileAttributes], ebx; FileAttributes
0x14005ee47  mov     [rsp+120h+AllocationSize], rbx; AllocationSize
0x14005ee4c  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14005ee51  lea     rax, [rbp+37h+ObjectAttributes]
0x14005ee55  mov     [rsp+120h+LengthReturned], rax; ObjectAttributes
0x14005ee5a  mov     eax, [rbp+37h+DesiredAccess]
0x14005ee5d  mov     [rsp+120h+FileInformationClass], eax; DesiredAccess
0x14005ee61  mov     [rbp+37h+ObjectAttributes.Length], 30h ; '0'
0x14005ee68  mov     [rbp+37h+ObjectAttributes.RootDirectory], rsi
0x14005ee6c  mov     [rbp+37h+ObjectAttributes.Attributes], 200h
0x14005ee73  mov     [rbp+37h+ObjectAttributes.ObjectName], r12
0x14005ee77  movdqu  xmmword ptr [rbp+37h+ObjectAttributes.SecurityDescriptor], xmm0
0x14005ee7c  call    cs:__imp_FltCreateFileEx
0x14005ee83  nop     dword ptr [rax+rax+00h]
0x14005ee88  mov     ecx, eax
0x14005ee8a  mov     edi, eax
0x14005ee8c  call    HsmDbgBreakOnStatus
0x14005ee91  test    edi, edi
0x14005ee93  js      short loc_14005EEC0
0x14005ee95  mov     rcx, [rbp+37h+arg_40]
0x14005ee9c  test    rcx, rcx
0x14005ee9f  jz      short loc_14005EEAC
0x14005eea1  mov     rax, [rbp+37h+FileObject]
0x14005eea5  mov     [rcx], rax
0x14005eea8  mov     [rbp+37h+FileObject], rbx
0x14005eeac  mov     rcx, [rbp+37h+arg_38]
0x14005eeb0  test    rcx, rcx
0x14005eeb3  jz      short loc_14005EEC0
0x14005eeb5  mov     rax, [rbp+37h+FileHandle]
0x14005eeb9  mov     [rcx], rax
0x14005eebc  mov     [rbp+37h+FileHandle], rbx
0x14005eec0  test    r14, r14
0x14005eec3  jz      short loc_14005EED4
0x14005eec5  mov     rcx, r14; Object
0x14005eec8  call    cs:__imp_ObfDereferenceObject
0x14005eecf  nop     dword ptr [rax+rax+00h]
0x14005eed4  test    rsi, rsi
0x14005eed7  jz      short loc_14005EEE8
0x14005eed9  mov     rcx, rsi; FileHandle
0x14005eedc  call    cs:__imp_FltClose
0x14005eee3  nop     dword ptr [rax+rax+00h]
0x14005eee8  mov     rcx, [rbp+37h+FileObject]; Object
0x14005eeec  test    rcx, rcx
0x14005eeef  jnz     loc_14005EFD5
0x14005eef5  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x14005eef9  test    rcx, rcx
0x14005eefc  jnz     loc_14005EFE6
0x14005ef02  mov     ecx, edi
0x14005ef04  call    HsmDbgBreakOnStatus
0x14005ef09  mov     rbx, [rsp+120h+arg_8]
0x14005ef11  mov     eax, edi
0x14005ef13  add     rsp, 0F0h
0x14005ef1a  pop     r15
0x14005ef1c  pop     r14
0x14005ef1e  pop     r13
0x14005ef20  pop     r12
0x14005ef22  pop     rdi
0x14005ef23  pop     rsi
0x14005ef24  pop     rbp
0x14005ef25  retn
0x14005ef27  mov     rax, [rbp+37h+arg_40]
0x14005ef2e  mov     [rax], r14
0x14005ef31  mov     rax, [rbp+37h+arg_38]
0x14005ef35  mov     [rax], rsi
0x14005ef38  jmp     short loc_14005EEE8
0x14005ef3a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ef41  lea     rax, WPP_GLOBAL_Control
0x14005ef48  cmp     rcx, rax
0x14005ef4b  jz      short loc_14005EF7B
0x14005ef4d  mov     eax, [rcx+2Ch]
0x14005ef50  test    al, 8
0x14005ef52  jz      short loc_14005EF7B
0x14005ef54  cmp     byte ptr [rcx+29h], 2
0x14005ef58  jb      short loc_14005EF7B
0x14005ef5a  mov     rcx, [rcx+18h]
0x14005ef5e  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005ef65  mov     edx, 1Bh
0x14005ef6a  mov     dword ptr [rsp+120h+LengthReturned], edi
0x14005ef6e  mov     r9, r15
0x14005ef71  mov     qword ptr [rsp+120h+FileInformationClass], r13
0x14005ef76  call    WPP_SF_qqd
0x14005ef7b  xor     ebx, ebx
0x14005ef7d  jmp     loc_14005EDCC
0x14005ef82  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ef89  lea     rax, WPP_GLOBAL_Control
0x14005ef90  cmp     rcx, rax
0x14005ef93  jz      loc_14005EDC4
0x14005ef99  mov     eax, [rcx+2Ch]
0x14005ef9c  test    sil, al
0x14005ef9f  jz      loc_14005EDC4
0x14005efa5  cmp     byte ptr [rcx+29h], 2
0x14005efa9  jb      loc_14005EDC4
0x14005efaf  mov     rcx, [rcx+18h]
0x14005efb3  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005efba  mov     edx, 1Ch
0x14005efbf  mov     dword ptr [rsp+120h+LengthReturned], edi
0x14005efc3  mov     r9, r15
0x14005efc6  mov     qword ptr [rsp+120h+FileInformationClass], r13
0x14005efcb  call    WPP_SF_qqd
0x14005efd0  jmp     loc_14005EDC4
0x14005efd5  call    cs:__imp_ObfDereferenceObject
0x14005efdc  nop     dword ptr [rax+rax+00h]
0x14005efe1  jmp     loc_14005EEF5
0x14005efe6  call    cs:__imp_FltClose
0x14005efed  nop     dword ptr [rax+rax+00h]
0x14005eff2  jmp     loc_14005EF02
```
