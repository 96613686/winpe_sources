# HsmpRelativeStreamOpenById

- ea: `0x14005e7e4`
- end: `0x14005eb38`
- name: `HsmpRelativeStreamOpenById`
- size: `852`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, int, PLARGE_INTEGER, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140044b78`
- `0x140058244`
- `0x14005fbd8`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e2d0`
- `0x14005e7e4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005e89f`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005e89f`
- `ntoskrnl!ObfDereferenceObject` at `0x14005ea11`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eb16`
- `ntoskrnl!ObfDereferenceObject` at `0x14005ea11`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eb16`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e91f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005e91f`
- `ntoskrnl!ExAllocatePool2` at `0x14005e864`
- `ntoskrnl!ExAllocatePool2` at `0x14005e864`
- `FLTMGR!FltCreateFileEx` at `0x14005e9c5`
- `FLTMGR!FltCreateFileEx` at `0x14005e9c5`
- `FLTMGR!FltClose` at `0x14005ea25`
- `FLTMGR!FltClose` at `0x14005eb27`
- `FLTMGR!FltClose` at `0x14005ea25`
- `FLTMGR!FltClose` at `0x14005eb27`

## pseudocode

```c
__int64 __fastcall HsmpRelativeStreamOpenById(
        __int64 a1,
        __int64 a2,
        struct _UNICODE_STRING *a3,
        ACCESS_MASK a4,
        ULONG CreateDisposition,
        int a6,
        PLARGE_INTEGER AllocationSize,
        void **a8,
        PFILE_OBJECT *a9)
{
  HANDLE v12; // rsi
  struct _FILE_OBJECT *v13; // r14
  USHORT v14; // ax
  signed int v15; // edi
  struct _FLT_INSTANCE *v16; // rdx
  struct _FLT_INSTANCE *v17; // rdx
  __int64 DesiredAccess; // [rsp+20h] [rbp-C9h]
  HANDLE v20; // [rsp+80h] [rbp-69h] BYREF
  PVOID Object; // [rsp+88h] [rbp-61h] BYREF
  struct _FLT_INSTANCE *v22; // [rsp+90h] [rbp-59h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B8h] [rbp-31h] BYREF
  PFILE_OBJECT FileObject; // [rsp+130h] [rbp+47h] BYREF
  void *FileHandle; // [rsp+140h] [rbp+57h] BYREF
  ACCESS_MASK v28; // [rsp+148h] [rbp+5Fh]

  v28 = a4;
  FileHandle = 0;
  FileObject = 0;
  v22 = *(struct _FLT_INSTANCE **)(a1 + 32);
  v12 = 0;
  v13 = 0;
  v14 = *(_WORD *)(a1 + 64) + 8;
  v20 = 0;
  *(_DWORD *)(&DestinationString.MaximumLength + 1) = 0;
  Object = 0;
  DestinationString.Length = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString.MaximumLength = v14;
  IoStatusBlock = 0;
  DestinationString.Buffer = (PWSTR)ExAllocatePool2(256, v14, 1934979912);
  v15 = DestinationString.Buffer == 0 ? 0xC000009A : 0;
  HsmDbgBreakOnStatus((unsigned int)v15);
  if ( DestinationString.Buffer )
  {
    RtlCopyUnicodeString(&DestinationString, (PCUNICODE_STRING)(a1 + 64));
    v16 = v22;
    *(_QWORD *)((char *)DestinationString.Buffer + DestinationString.Length) = a2;
    DestinationString.Length += 8;
    v15 = HsmiOpenFile(
            a1,
            v16,
            &DestinationString,
            0x100080u,
            DesiredAccess,
            0x202100u,
            a3 == 0,
            &v20,
            (PFILE_OBJECT *)&Object);
    HsmDbgBreakOnStatus((unsigned int)v15);
    if ( v15 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a2, v15);
    }
    v13 = (struct _FILE_OBJECT *)Object;
    v12 = v20;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_qqd(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, a2, v15);
  }
  if ( DestinationString.Buffer )
    ExFreePoolWithTag(DestinationString.Buffer, 0x73557348u);
  HsmDbgBreakOnStatus((unsigned int)v15);
  if ( v15 >= 0 )
  {
    if ( !a3 )
    {
      *a9 = v13;
      *a8 = v12;
      goto LABEL_17;
    }
    v17 = *(struct _FLT_INSTANCE **)(a1 + 32);
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = v12;
    ObjectAttributes.Attributes = 512;
    ObjectAttributes.ObjectName = a3;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v15 = FltCreateFileEx(
            Filter,
            v17,
            &FileHandle,
            &FileObject,
            v28,
            &ObjectAttributes,
            &IoStatusBlock,
            AllocationSize,
            0,
            7u,
            CreateDisposition,
            a6 | 0x200000,
            0,
            0,
            0x840u);
    HsmDbgBreakOnStatus((unsigned int)v15);
    if ( v15 >= 0 )
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
  }
  if ( v13 )
    ObfDereferenceObject(v13);
  if ( v12 )
    FltClose(v12);
LABEL_17:
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14005e7e4  mov     [rsp-8+arg_8], rbx
0x14005e7e9  mov     [rsp-8+arg_18], r9d
0x14005e7ee  push    rbp
0x14005e7ef  push    rsi
0x14005e7f0  push    rdi
0x14005e7f1  push    r12
0x14005e7f3  push    r13
0x14005e7f5  push    r14
0x14005e7f7  push    r15
0x14005e7f9  lea     rbp, [rsp-7]
0x14005e7fe  sub     rsp, 0F0h
0x14005e805  xor     eax, eax
0x14005e807  xorps   xmm0, xmm0
0x14005e80a  mov     [rbp+37h+FileHandle], rax
0x14005e80e  mov     r12, rdx
0x14005e811  mov     [rbp+37h+FileObject], rax
0x14005e815  mov     r13, r8
0x14005e818  mov     rax, [rcx+20h]
0x14005e81c  mov     r15, rcx
0x14005e81f  mov     [rbp+37h+var_90], rax
0x14005e823  xor     esi, esi
0x14005e825  movzx   eax, word ptr [rcx+40h]
0x14005e829  xor     r14d, r14d
0x14005e82c  add     ax, 8
0x14005e830  mov     [rbp+37h+var_A0], rsi
0x14005e834  movzx   edx, ax
0x14005e837  mov     ecx, 100h
0x14005e83c  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x14005e840  xor     eax, eax
0x14005e842  mov     [rbp+37h+Object], r14
0x14005e846  movups  xmmword ptr [rbp+37h+var_68.ObjectName], xmm0
0x14005e84a  mov     r8d, 73557348h
0x14005e850  mov     [rbp+37h+DestinationString.Length], ax
0x14005e854  movups  xmmword ptr [rbp+37h+var_68.Length], xmm0
0x14005e858  mov     [rbp+37h+DestinationString.MaximumLength], dx
0x14005e85c  movups  xmmword ptr [rbp+37h+var_68+1Ch], xmm0
0x14005e860  movups  xmmword ptr [rbp+37h+var_78], xmm0
0x14005e864  call    cs:__imp_ExAllocatePool2
0x14005e86b  nop     dword ptr [rax+rax+00h]
0x14005e870  mov     rcx, rax
0x14005e873  mov     [rbp+37h+DestinationString.Buffer], rax
0x14005e877  neg     rcx
0x14005e87a  mov     rbx, rax
0x14005e87d  sbb     edi, edi
0x14005e87f  not     edi
0x14005e881  and     edi, 0C000009Ah
0x14005e887  mov     ecx, edi
0x14005e889  call    HsmDbgBreakOnStatus
0x14005e88e  test    rbx, rbx
0x14005e891  jz      loc_14005EA7C
0x14005e897  lea     rdx, [r15+40h]; SourceString
0x14005e89b  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x14005e89f  call    cs:__imp_RtlCopyUnicodeString
0x14005e8a6  nop     dword ptr [rax+rax+00h]
0x14005e8ab  movzx   ecx, [rbp+37h+DestinationString.Length]
0x14005e8af  lea     r8, [rbp+37h+DestinationString]
0x14005e8b3  mov     rax, [rbp+37h+DestinationString.Buffer]
0x14005e8b7  xor     ebx, ebx
0x14005e8b9  mov     rdx, [rbp+37h+var_90]
0x14005e8bd  mov     r9d, 100080h
0x14005e8c3  mov     [rcx+rax], r12
0x14005e8c7  lea     rcx, [rbp+37h+Object]
0x14005e8cb  add     [rbp+37h+DestinationString.Length], 8
0x14005e8d0  mov     qword ptr [rsp+120h+FileAttributes], rcx
0x14005e8d5  test    r13, r13
0x14005e8d8  lea     rcx, [rbp+37h+var_A0]
0x14005e8dc  mov     [rsp+120h+AllocationSize], rcx
0x14005e8e1  setz    al
0x14005e8e4  mov     byte ptr [rsp+120h+IoStatusBlock], al
0x14005e8e8  mov     rcx, r15
0x14005e8eb  mov     dword ptr [rsp+120h+ObjectAttributes], 202100h
0x14005e8f3  call    HsmiOpenFile
0x14005e8f8  mov     ecx, eax
0x14005e8fa  mov     edi, eax
0x14005e8fc  call    HsmDbgBreakOnStatus
0x14005e901  test    edi, edi
0x14005e903  js      loc_14005EAC4
0x14005e909  mov     r14, [rbp+37h+Object]
0x14005e90d  mov     rsi, [rbp+37h+var_A0]
0x14005e911  mov     rcx, [rbp+37h+DestinationString.Buffer]; P
0x14005e915  test    rcx, rcx
0x14005e918  jz      short loc_14005E92B
0x14005e91a  mov     edx, 73557348h; Tag
0x14005e91f  call    cs:__imp_ExFreePoolWithTag
0x14005e926  nop     dword ptr [rax+rax+00h]
0x14005e92b  mov     ecx, edi
0x14005e92d  call    HsmDbgBreakOnStatus
0x14005e932  test    edi, edi
0x14005e934  js      loc_14005EA09
0x14005e93a  test    r13, r13
0x14005e93d  jz      loc_14005EA69
0x14005e943  mov     eax, [rbp+37h+arg_28]
0x14005e946  lea     r9, [rbp+37h+FileObject]; FileObject
0x14005e94a  mov     rdx, [r15+20h]; Instance
0x14005e94e  lea     r8, [rbp+37h+FileHandle]; FileHandle
0x14005e952  mov     rcx, cs:Filter; Filter
0x14005e959  bts     eax, 15h
0x14005e95d  mov     [rsp+120h+Flags], 840h; Flags
0x14005e965  xorps   xmm0, xmm0
0x14005e968  mov     [rsp+120h+EaLength], ebx; EaLength
0x14005e96c  mov     [rsp+120h+EaBuffer], rbx; EaBuffer
0x14005e971  mov     [rsp+120h+CreateOptions], eax; CreateOptions
0x14005e975  mov     eax, [rbp+37h+arg_20]
0x14005e978  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x14005e97c  mov     rax, [rbp+37h+arg_30]
0x14005e980  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14005e988  mov     [rsp+120h+FileAttributes], ebx; FileAttributes
0x14005e98c  mov     [rsp+120h+AllocationSize], rax; AllocationSize
0x14005e991  lea     rax, [rbp+37h+var_78]
0x14005e995  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14005e99a  lea     rax, [rbp+37h+var_68]
0x14005e99e  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14005e9a3  mov     eax, [rbp+37h+arg_18]
0x14005e9a6  mov     [rsp+120h+DesiredAccess], eax; DesiredAccess
0x14005e9aa  mov     [rbp+37h+var_68.Length], 30h ; '0'
0x14005e9b1  mov     [rbp+37h+var_68.RootDirectory], rsi
0x14005e9b5  mov     [rbp+37h+var_68.Attributes], 200h
0x14005e9bc  mov     [rbp+37h+var_68.ObjectName], r13
0x14005e9c0  movdqu  xmmword ptr [rbp+37h+var_68.SecurityDescriptor], xmm0
0x14005e9c5  call    cs:__imp_FltCreateFileEx
0x14005e9cc  nop     dword ptr [rax+rax+00h]
0x14005e9d1  mov     ecx, eax
0x14005e9d3  mov     edi, eax
0x14005e9d5  call    HsmDbgBreakOnStatus
0x14005e9da  test    edi, edi
0x14005e9dc  js      short loc_14005EA09
0x14005e9de  mov     rax, [rbp+37h+arg_40]
0x14005e9e5  test    rax, rax
0x14005e9e8  jz      short loc_14005E9F5
0x14005e9ea  mov     rcx, [rbp+37h+FileObject]
0x14005e9ee  mov     [rax], rcx
0x14005e9f1  mov     [rbp+37h+FileObject], rbx
0x14005e9f5  mov     rcx, [rbp+37h+arg_38]
0x14005e9f9  test    rcx, rcx
0x14005e9fc  jz      short loc_14005EA09
0x14005e9fe  mov     rax, [rbp+37h+FileHandle]
0x14005ea02  mov     [rcx], rax
0x14005ea05  mov     [rbp+37h+FileHandle], rbx
0x14005ea09  test    r14, r14
0x14005ea0c  jz      short loc_14005EA1D
0x14005ea0e  mov     rcx, r14; Object
0x14005ea11  call    cs:__imp_ObfDereferenceObject
0x14005ea18  nop     dword ptr [rax+rax+00h]
0x14005ea1d  test    rsi, rsi
0x14005ea20  jz      short loc_14005EA31
0x14005ea22  mov     rcx, rsi; FileHandle
0x14005ea25  call    cs:__imp_FltClose
0x14005ea2c  nop     dword ptr [rax+rax+00h]
0x14005ea31  mov     rcx, [rbp+37h+FileObject]; Object
0x14005ea35  test    rcx, rcx
0x14005ea38  jnz     loc_14005EB16
0x14005ea3e  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x14005ea42  test    rcx, rcx
0x14005ea45  jnz     loc_14005EB27
0x14005ea4b  mov     rbx, [rsp+120h+arg_8]
0x14005ea53  mov     eax, edi
0x14005ea55  add     rsp, 0F0h
0x14005ea5c  pop     r15
0x14005ea5e  pop     r14
0x14005ea60  pop     r13
0x14005ea62  pop     r12
0x14005ea64  pop     rdi
0x14005ea65  pop     rsi
0x14005ea66  pop     rbp
0x14005ea67  retn
0x14005ea69  mov     rax, [rbp+37h+arg_40]
0x14005ea70  mov     [rax], r14
0x14005ea73  mov     rax, [rbp+37h+arg_38]
0x14005ea77  mov     [rax], rsi
0x14005ea7a  jmp     short loc_14005EA31
0x14005ea7c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ea83  lea     rax, WPP_GLOBAL_Control
0x14005ea8a  cmp     rcx, rax
0x14005ea8d  jz      short loc_14005EABD
0x14005ea8f  mov     eax, [rcx+2Ch]
0x14005ea92  test    al, 8
0x14005ea94  jz      short loc_14005EABD
0x14005ea96  cmp     byte ptr [rcx+29h], 2
0x14005ea9a  jb      short loc_14005EABD
0x14005ea9c  mov     rcx, [rcx+18h]
0x14005eaa0  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005eaa7  mov     edx, 1Bh
0x14005eaac  mov     dword ptr [rsp+120h+ObjectAttributes], edi
0x14005eab0  mov     r9, r15
0x14005eab3  mov     qword ptr [rsp+120h+DesiredAccess], r12
0x14005eab8  call    WPP_SF_qqd
0x14005eabd  xor     ebx, ebx
0x14005eabf  jmp     loc_14005E911
0x14005eac4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005eacb  lea     rax, WPP_GLOBAL_Control
0x14005ead2  cmp     rcx, rax
0x14005ead5  jz      loc_14005E909
0x14005eadb  mov     eax, [rcx+2Ch]
0x14005eade  test    al, 8
0x14005eae0  jz      loc_14005E909
0x14005eae6  cmp     byte ptr [rcx+29h], 2
0x14005eaea  jb      loc_14005E909
0x14005eaf0  mov     rcx, [rcx+18h]
0x14005eaf4  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005eafb  mov     edx, 1Ch
0x14005eb00  mov     dword ptr [rsp+120h+ObjectAttributes], edi
0x14005eb04  mov     r9, r15
0x14005eb07  mov     qword ptr [rsp+120h+DesiredAccess], r12
0x14005eb0c  call    WPP_SF_qqd
0x14005eb11  jmp     loc_14005E909
0x14005eb16  call    cs:__imp_ObfDereferenceObject
0x14005eb1d  nop     dword ptr [rax+rax+00h]
0x14005eb22  jmp     loc_14005EA3E
0x14005eb27  call    cs:__imp_FltClose
0x14005eb2e  nop     dword ptr [rax+rax+00h]
0x14005eb33  jmp     loc_14005EA4B
```
