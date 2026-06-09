# HsmpRelativeStreamOpenById

- ea: `0x14005e904`
- end: `0x14005ec58`
- name: `HsmpRelativeStreamOpenById`
- size: `852`
- prototype: `__int64 __fastcall(int, int, int, int, ULONG, int, PLARGE_INTEGER, __int64, __int64)`
- caller_count: `3`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140044c68`
- `0x140058364`
- `0x14005fcf8`

## callees

- `0x140003c50`
- `0x140009300`
- `0x14005e3f0`
- `0x14005e904`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14005e9bf`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14005e9bf`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eb31`
- `ntoskrnl!ObfDereferenceObject` at `0x14005ec36`
- `ntoskrnl!ObfDereferenceObject` at `0x14005eb31`
- `ntoskrnl!ObfDereferenceObject` at `0x14005ec36`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ea3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ea3f`
- `ntoskrnl!ExAllocatePool2` at `0x14005e984`
- `ntoskrnl!ExAllocatePool2` at `0x14005e984`
- `FLTMGR!FltCreateFileEx` at `0x14005eae5`
- `FLTMGR!FltCreateFileEx` at `0x14005eae5`
- `FLTMGR!FltClose` at `0x14005eb45`
- `FLTMGR!FltClose` at `0x14005ec47`
- `FLTMGR!FltClose` at `0x14005eb45`
- `FLTMGR!FltClose` at `0x14005ec47`

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
  int v15; // edi
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
  HsmDbgBreakOnStatus(v15);
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
    HsmDbgBreakOnStatus(v15);
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
  HsmDbgBreakOnStatus(v15);
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
    HsmDbgBreakOnStatus(v15);
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
0x14005e904  mov     [rsp-8+arg_8], rbx
0x14005e909  mov     [rsp-8+arg_18], r9d
0x14005e90e  push    rbp
0x14005e90f  push    rsi
0x14005e910  push    rdi
0x14005e911  push    r12
0x14005e913  push    r13
0x14005e915  push    r14
0x14005e917  push    r15
0x14005e919  lea     rbp, [rsp-7]
0x14005e91e  sub     rsp, 0F0h
0x14005e925  xor     eax, eax
0x14005e927  xorps   xmm0, xmm0
0x14005e92a  mov     [rbp+37h+FileHandle], rax
0x14005e92e  mov     r12, rdx
0x14005e931  mov     [rbp+37h+FileObject], rax
0x14005e935  mov     r13, r8
0x14005e938  mov     rax, [rcx+20h]
0x14005e93c  mov     r15, rcx
0x14005e93f  mov     [rbp+37h+var_90], rax
0x14005e943  xor     esi, esi
0x14005e945  movzx   eax, word ptr [rcx+40h]
0x14005e949  xor     r14d, r14d
0x14005e94c  add     ax, 8
0x14005e950  mov     [rbp+37h+var_A0], rsi
0x14005e954  movzx   edx, ax
0x14005e957  mov     ecx, 100h
0x14005e95c  movups  xmmword ptr [rbp+37h+DestinationString.Length], xmm0
0x14005e960  xor     eax, eax
0x14005e962  mov     [rbp+37h+Object], r14
0x14005e966  movups  xmmword ptr [rbp+37h+var_68.ObjectName], xmm0
0x14005e96a  mov     r8d, 73557348h
0x14005e970  mov     [rbp+37h+DestinationString.Length], ax
0x14005e974  movups  xmmword ptr [rbp+37h+var_68.Length], xmm0
0x14005e978  mov     [rbp+37h+DestinationString.MaximumLength], dx
0x14005e97c  movups  xmmword ptr [rbp+37h+var_68+1Ch], xmm0
0x14005e980  movups  xmmword ptr [rbp+37h+var_78], xmm0
0x14005e984  call    cs:__imp_ExAllocatePool2
0x14005e98b  nop     dword ptr [rax+rax+00h]
0x14005e990  mov     rcx, rax
0x14005e993  mov     [rbp+37h+DestinationString.Buffer], rax
0x14005e997  neg     rcx
0x14005e99a  mov     rbx, rax
0x14005e99d  sbb     edi, edi
0x14005e99f  not     edi
0x14005e9a1  and     edi, 0C000009Ah
0x14005e9a7  mov     ecx, edi
0x14005e9a9  call    HsmDbgBreakOnStatus
0x14005e9ae  test    rbx, rbx
0x14005e9b1  jz      loc_14005EB9C
0x14005e9b7  lea     rdx, [r15+40h]; SourceString
0x14005e9bb  lea     rcx, [rbp+37h+DestinationString]; DestinationString
0x14005e9bf  call    cs:__imp_RtlCopyUnicodeString
0x14005e9c6  nop     dword ptr [rax+rax+00h]
0x14005e9cb  movzx   ecx, [rbp+37h+DestinationString.Length]
0x14005e9cf  lea     r8, [rbp+37h+DestinationString]
0x14005e9d3  mov     rax, [rbp+37h+DestinationString.Buffer]
0x14005e9d7  xor     ebx, ebx
0x14005e9d9  mov     rdx, [rbp+37h+var_90]
0x14005e9dd  mov     r9d, 100080h
0x14005e9e3  mov     [rcx+rax], r12
0x14005e9e7  lea     rcx, [rbp+37h+Object]
0x14005e9eb  add     [rbp+37h+DestinationString.Length], 8
0x14005e9f0  mov     qword ptr [rsp+120h+FileAttributes], rcx
0x14005e9f5  test    r13, r13
0x14005e9f8  lea     rcx, [rbp+37h+var_A0]
0x14005e9fc  mov     [rsp+120h+AllocationSize], rcx
0x14005ea01  setz    al
0x14005ea04  mov     byte ptr [rsp+120h+IoStatusBlock], al
0x14005ea08  mov     rcx, r15
0x14005ea0b  mov     dword ptr [rsp+120h+ObjectAttributes], 202100h
0x14005ea13  call    HsmiOpenFile
0x14005ea18  mov     ecx, eax
0x14005ea1a  mov     edi, eax
0x14005ea1c  call    HsmDbgBreakOnStatus
0x14005ea21  test    edi, edi
0x14005ea23  js      loc_14005EBE4
0x14005ea29  mov     r14, [rbp+37h+Object]
0x14005ea2d  mov     rsi, [rbp+37h+var_A0]
0x14005ea31  mov     rcx, [rbp+37h+DestinationString.Buffer]; P
0x14005ea35  test    rcx, rcx
0x14005ea38  jz      short loc_14005EA4B
0x14005ea3a  mov     edx, 73557348h; Tag
0x14005ea3f  call    cs:__imp_ExFreePoolWithTag
0x14005ea46  nop     dword ptr [rax+rax+00h]
0x14005ea4b  mov     ecx, edi
0x14005ea4d  call    HsmDbgBreakOnStatus
0x14005ea52  test    edi, edi
0x14005ea54  js      loc_14005EB29
0x14005ea5a  test    r13, r13
0x14005ea5d  jz      loc_14005EB89
0x14005ea63  mov     eax, [rbp+37h+arg_28]
0x14005ea66  lea     r9, [rbp+37h+FileObject]; FileObject
0x14005ea6a  mov     rdx, [r15+20h]; Instance
0x14005ea6e  lea     r8, [rbp+37h+FileHandle]; FileHandle
0x14005ea72  mov     rcx, cs:Filter; Filter
0x14005ea79  bts     eax, 15h
0x14005ea7d  mov     [rsp+120h+Flags], 840h; Flags
0x14005ea85  xorps   xmm0, xmm0
0x14005ea88  mov     [rsp+120h+EaLength], ebx; EaLength
0x14005ea8c  mov     [rsp+120h+EaBuffer], rbx; EaBuffer
0x14005ea91  mov     [rsp+120h+CreateOptions], eax; CreateOptions
0x14005ea95  mov     eax, [rbp+37h+arg_20]
0x14005ea98  mov     [rsp+120h+CreateDisposition], eax; CreateDisposition
0x14005ea9c  mov     rax, [rbp+37h+arg_30]
0x14005eaa0  mov     [rsp+120h+ShareAccess], 7; ShareAccess
0x14005eaa8  mov     [rsp+120h+FileAttributes], ebx; FileAttributes
0x14005eaac  mov     [rsp+120h+AllocationSize], rax; AllocationSize
0x14005eab1  lea     rax, [rbp+37h+var_78]
0x14005eab5  mov     [rsp+120h+IoStatusBlock], rax; IoStatusBlock
0x14005eaba  lea     rax, [rbp+37h+var_68]
0x14005eabe  mov     [rsp+120h+ObjectAttributes], rax; ObjectAttributes
0x14005eac3  mov     eax, [rbp+37h+arg_18]
0x14005eac6  mov     [rsp+120h+DesiredAccess], eax; DesiredAccess
0x14005eaca  mov     [rbp+37h+var_68.Length], 30h ; '0'
0x14005ead1  mov     [rbp+37h+var_68.RootDirectory], rsi
0x14005ead5  mov     [rbp+37h+var_68.Attributes], 200h
0x14005eadc  mov     [rbp+37h+var_68.ObjectName], r13
0x14005eae0  movdqu  xmmword ptr [rbp+37h+var_68.SecurityDescriptor], xmm0
0x14005eae5  call    cs:__imp_FltCreateFileEx
0x14005eaec  nop     dword ptr [rax+rax+00h]
0x14005eaf1  mov     ecx, eax
0x14005eaf3  mov     edi, eax
0x14005eaf5  call    HsmDbgBreakOnStatus
0x14005eafa  test    edi, edi
0x14005eafc  js      short loc_14005EB29
0x14005eafe  mov     rax, [rbp+37h+arg_40]
0x14005eb05  test    rax, rax
0x14005eb08  jz      short loc_14005EB15
0x14005eb0a  mov     rcx, [rbp+37h+FileObject]
0x14005eb0e  mov     [rax], rcx
0x14005eb11  mov     [rbp+37h+FileObject], rbx
0x14005eb15  mov     rcx, [rbp+37h+arg_38]
0x14005eb19  test    rcx, rcx
0x14005eb1c  jz      short loc_14005EB29
0x14005eb1e  mov     rax, [rbp+37h+FileHandle]
0x14005eb22  mov     [rcx], rax
0x14005eb25  mov     [rbp+37h+FileHandle], rbx
0x14005eb29  test    r14, r14
0x14005eb2c  jz      short loc_14005EB3D
0x14005eb2e  mov     rcx, r14; Object
0x14005eb31  call    cs:__imp_ObfDereferenceObject
0x14005eb38  nop     dword ptr [rax+rax+00h]
0x14005eb3d  test    rsi, rsi
0x14005eb40  jz      short loc_14005EB51
0x14005eb42  mov     rcx, rsi; FileHandle
0x14005eb45  call    cs:__imp_FltClose
0x14005eb4c  nop     dword ptr [rax+rax+00h]
0x14005eb51  mov     rcx, [rbp+37h+FileObject]; Object
0x14005eb55  test    rcx, rcx
0x14005eb58  jnz     loc_14005EC36
0x14005eb5e  mov     rcx, [rbp+37h+FileHandle]; FileHandle
0x14005eb62  test    rcx, rcx
0x14005eb65  jnz     loc_14005EC47
0x14005eb6b  mov     rbx, [rsp+120h+arg_8]
0x14005eb73  mov     eax, edi
0x14005eb75  add     rsp, 0F0h
0x14005eb7c  pop     r15
0x14005eb7e  pop     r14
0x14005eb80  pop     r13
0x14005eb82  pop     r12
0x14005eb84  pop     rdi
0x14005eb85  pop     rsi
0x14005eb86  pop     rbp
0x14005eb87  retn
0x14005eb89  mov     rax, [rbp+37h+arg_40]
0x14005eb90  mov     [rax], r14
0x14005eb93  mov     rax, [rbp+37h+arg_38]
0x14005eb97  mov     [rax], rsi
0x14005eb9a  jmp     short loc_14005EB51
0x14005eb9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005eba3  lea     rax, WPP_GLOBAL_Control
0x14005ebaa  cmp     rcx, rax
0x14005ebad  jz      short loc_14005EBDD
0x14005ebaf  mov     eax, [rcx+2Ch]
0x14005ebb2  test    al, 8
0x14005ebb4  jz      short loc_14005EBDD
0x14005ebb6  cmp     byte ptr [rcx+29h], 2
0x14005ebba  jb      short loc_14005EBDD
0x14005ebbc  mov     rcx, [rcx+18h]
0x14005ebc0  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005ebc7  mov     edx, 1Bh
0x14005ebcc  mov     dword ptr [rsp+120h+ObjectAttributes], edi
0x14005ebd0  mov     r9, r15
0x14005ebd3  mov     qword ptr [rsp+120h+DesiredAccess], r12
0x14005ebd8  call    WPP_SF_qqd
0x14005ebdd  xor     ebx, ebx
0x14005ebdf  jmp     loc_14005EA31
0x14005ebe4  mov     rcx, cs:WPP_GLOBAL_Control
0x14005ebeb  lea     rax, WPP_GLOBAL_Control
0x14005ebf2  cmp     rcx, rax
0x14005ebf5  jz      loc_14005EA29
0x14005ebfb  mov     eax, [rcx+2Ch]
0x14005ebfe  test    al, 8
0x14005ec00  jz      loc_14005EA29
0x14005ec06  cmp     byte ptr [rcx+29h], 2
0x14005ec0a  jb      loc_14005EA29
0x14005ec10  mov     rcx, [rcx+18h]
0x14005ec14  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005ec1b  mov     edx, 1Ch
0x14005ec20  mov     dword ptr [rsp+120h+ObjectAttributes], edi
0x14005ec24  mov     r9, r15
0x14005ec27  mov     qword ptr [rsp+120h+DesiredAccess], r12
0x14005ec2c  call    WPP_SF_qqd
0x14005ec31  jmp     loc_14005EA29
0x14005ec36  call    cs:__imp_ObfDereferenceObject
0x14005ec3d  nop     dword ptr [rax+rax+00h]
0x14005ec42  jmp     loc_14005EB5E
0x14005ec47  call    cs:__imp_FltClose
0x14005ec4e  nop     dword ptr [rax+rax+00h]
0x14005ec53  jmp     loc_14005EB6B
```
