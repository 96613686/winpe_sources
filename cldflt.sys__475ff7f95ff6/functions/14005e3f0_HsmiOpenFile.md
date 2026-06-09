# HsmiOpenFile

- ea: `0x14005e3f0`
- end: `0x14005e764`
- name: `HsmiOpenFile`
- size: `884`
- prototype: `__int64 __fastcall(__int64, struct _FLT_INSTANCE *, struct _UNICODE_STRING *, ACCESS_MASK, __int64, ULONG CreateOptions, char, void **, PFILE_OBJECT *)`
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005d0b0`
- `0x14005e76c`
- `0x14005e904`
- `0x14005ec60`
- `0x14005f000`
- `0x14007f338`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14005e3f0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14005e742`
- `ntoskrnl!ObfDereferenceObject` at `0x14005e742`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14005e5cf`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14005e5cf`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14005e58c`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14005e58c`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14005e679`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14005e679`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14005e651`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14005e651`
- `FLTMGR!FltClose` at `0x14005e753`
- `FLTMGR!FltClose` at `0x14005e753`
- `FLTMGR!FltCreateFileEx2` at `0x14005e4ec`
- `FLTMGR!FltCreateFileEx2` at `0x14005e4ec`

## pseudocode

```c
__int64 __fastcall HsmiOpenFile(
        __int64 a1,
        struct _FLT_INSTANCE *a2,
        struct _UNICODE_STRING *a3,
        ACCESS_MASK a4,
        __int64 a5,
        ULONG CreateOptions,
        char a7,
        void **a8,
        PFILE_OBJECT *a9)
{
  PECP_LIST v13; // rdx
  struct _IO_DRIVER_CREATE_CONTEXT *v14; // rax
  NTSTATUS v15; // ebx
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  PVOID EcpContext; // [rsp+88h] [rbp-80h] BYREF
  PECP_LIST EcpList; // [rsp+90h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-70h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v23; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v24; // [rsp+B8h] [rbp-50h]
  __int64 v25; // [rsp+C8h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp-8h] BYREF

  FileObject = 0;
  FileHandle = 0;
  v13 = 0;
  LOWORD(v25) = 0;
  v23 = 0;
  EcpList = 0;
  v24 = 0;
  EcpContext = 0;
  *a8 = 0;
  *a9 = 0;
  if ( a7 )
  {
    v15 = FltAllocateExtraCreateParameterList(Filter, 0, &EcpList);
    HsmDbgBreakOnStatus(v15);
    if ( v15 >= 0 )
    {
      v15 = FltAllocateExtraCreateParameterFromLookasideList(
              Filter,
              &GUID_ECP_OPEN_PARAMETERS,
              8u,
              0,
              0,
              qword_140029240,
              &EcpContext);
      HsmDbgBreakOnStatus(v15);
      if ( v15 >= 0 )
      {
        FltInsertExtraCreateParameter(Filter, EcpList, EcpContext);
        *(_QWORD *)EcpContext = 0;
        *(_WORD *)EcpContext = 8;
        *((_DWORD *)EcpContext + 1) = 3;
        v13 = EcpList;
        goto LABEL_2;
      }
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_6;
      }
      v18 = 11;
    }
    else
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_6;
      }
      v18 = 10;
    }
    WPP_SF_qd(v17->AttachedDevice, v18, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, v15);
    goto LABEL_6;
  }
LABEL_2:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = a3;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( v13 )
  {
    *(_DWORD *)((char *)&v23 + 2) = 0;
    LOWORD(v23) = 40;
    v14 = (struct _IO_DRIVER_CREATE_CONTEXT *)&v23;
    WORD3(v23) = 0;
    v24 = 0;
    v25 = 1;
    *((_QWORD *)&v23 + 1) = v13;
  }
  else
  {
    v14 = 0;
  }
  v15 = FltCreateFileEx2(
          Filter,
          a2,
          &FileHandle,
          &FileObject,
          a4,
          &ObjectAttributes,
          &IoStatusBlock,
          0,
          0,
          7u,
          1u,
          CreateOptions,
          0,
          0,
          0x800u,
          v14);
  HsmDbgBreakOnStatus(v15);
  if ( v15 == -1073741738 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
        a1,
        -1073741738);
    }
    v15 = -1073741772;
  }
  *a8 = FileHandle;
  *a9 = FileObject;
  FileHandle = 0;
  FileObject = 0;
LABEL_6:
  if ( EcpList )
    FltFreeExtraCreateParameterList(Filter, EcpList);
  if ( FileObject )
    ObfDereferenceObject(FileObject);
  if ( FileHandle )
    FltClose(FileHandle);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x14005e3f0  mov     rax, rsp
0x14005e3f3  push    rbp
0x14005e3f4  push    rbx
0x14005e3f5  lea     rbp, [rax-38h]
0x14005e3f9  sub     rsp, 128h
0x14005e400  mov     [rax+8], rsi
0x14005e404  xorps   xmm0, xmm0
0x14005e407  mov     rsi, [rbp+30h+arg_40]
0x14005e40e  mov     [rax+10h], rdi
0x14005e412  mov     rdi, [rbp+30h+arg_38]
0x14005e416  mov     [rax+18h], r12
0x14005e41a  mov     r12, rdx
0x14005e41d  mov     [rax-18h], r13
0x14005e421  mov     r13, rcx
0x14005e424  xor     ecx, ecx
0x14005e426  mov     [rax-20h], r14
0x14005e42a  mov     [rax-28h], r15
0x14005e42e  mov     r14, r8
0x14005e431  xor     eax, eax
0x14005e433  mov     [rbp+30h+FileObject], rcx
0x14005e437  mov     r15d, r9d
0x14005e43a  mov     [rbp+30h+FileHandle], rcx
0x14005e43e  mov     edx, ecx; Flags
0x14005e440  mov     word ptr [rbp+30h+var_70], ax
0x14005e444  movups  [rbp+30h+var_90], xmm0
0x14005e448  mov     [rbp+30h+EcpList], rcx
0x14005e44c  movups  [rbp+30h+var_80], xmm0
0x14005e450  mov     [rbp+30h+EcpContext], rcx
0x14005e454  mov     [rdi], rcx
0x14005e457  mov     [rsi], rcx
0x14005e45a  cmp     [rbp+30h+arg_30], al
0x14005e45d  jnz     loc_14005E5C4
0x14005e463  mov     [rbp+30h+var_68.Length], 30h ; '0'
0x14005e46a  xorps   xmm0, xmm0
0x14005e46d  mov     [rbp+30h+var_68.RootDirectory], rcx
0x14005e471  mov     [rbp+30h+var_68.Attributes], 240h
0x14005e478  mov     [rbp+30h+var_68.ObjectName], r14
0x14005e47c  movdqu  xmmword ptr [rbp+30h+var_68.SecurityDescriptor], xmm0
0x14005e481  test    rdx, rdx
0x14005e484  jnz     loc_14005E59A
0x14005e48a  mov     rax, rcx
0x14005e48d  mov     [rsp+78h], rax; DriverContext
0x14005e492  lea     r9, [rbp+30h+FileObject]; FileObject
0x14005e496  mov     eax, [rbp+30h+arg_28]
0x14005e499  lea     r8, [rbp+30h+FileHandle]; FileHandle
0x14005e49d  mov     [rsp+130h+Flags], 800h; Flags
0x14005e4a5  mov     rdx, r12; Instance
0x14005e4a8  mov     [rsp+130h+EaLength], ecx; EaLength
0x14005e4ac  mov     [rsp+130h+EaBuffer], rcx; EaBuffer
0x14005e4b1  mov     [rsp+130h+CreateOptions], eax; CreateOptions
0x14005e4b5  lea     rax, [rbp+30h+var_38]
0x14005e4b9  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x14005e4c1  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14005e4c9  mov     [rsp+130h+FileAttributes], ecx; FileAttributes
0x14005e4cd  mov     [rsp+130h+AllocationSize], rcx; AllocationSize
0x14005e4d2  mov     rcx, cs:Filter; Filter
0x14005e4d9  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14005e4de  lea     rax, [rbp+30h+var_68]
0x14005e4e2  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x14005e4e7  mov     [rsp+130h+DesiredAccess], r15d; DesiredAccess
0x14005e4ec  call    cs:__imp_FltCreateFileEx2
0x14005e4f3  nop     dword ptr [rax+rax+00h]
0x14005e4f8  mov     ecx, eax
0x14005e4fa  mov     ebx, eax
0x14005e4fc  call    HsmDbgBreakOnStatus
0x14005e501  cmp     ebx, 0C0000056h
0x14005e507  jz      loc_14005E6F8
0x14005e50d  mov     rax, [rbp+30h+FileHandle]
0x14005e511  xor     ecx, ecx
0x14005e513  mov     [rdi], rax
0x14005e516  mov     rax, [rbp+30h+FileObject]
0x14005e51a  mov     [rsi], rax
0x14005e51d  mov     [rbp+30h+FileHandle], rcx
0x14005e521  mov     [rbp+30h+FileObject], rcx
0x14005e525  mov     rdx, [rbp+30h+EcpList]; EcpList
0x14005e529  mov     r15, [rsp+130h+var_20]
0x14005e531  mov     r14, [rsp+130h+var_18]
0x14005e539  mov     r13, [rsp+120h]
0x14005e541  mov     r12, [rsp+130h+arg_10]
0x14005e549  mov     rdi, [rsp+130h+arg_8]
0x14005e551  mov     rsi, [rsp+130h+arg_0]
0x14005e559  test    rdx, rdx
0x14005e55c  jnz     short loc_14005E585
0x14005e55e  mov     rcx, [rbp+30h+FileObject]; Object
0x14005e562  test    rcx, rcx
0x14005e565  jnz     loc_14005E742
0x14005e56b  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x14005e56f  test    rcx, rcx
0x14005e572  jnz     loc_14005E753
0x14005e578  mov     eax, ebx
0x14005e57a  add     rsp, 128h
0x14005e581  pop     rbx
0x14005e582  pop     rbp
0x14005e583  retn
0x14005e585  mov     rcx, cs:Filter; Filter
0x14005e58c  call    cs:__imp_FltFreeExtraCreateParameterList
0x14005e593  nop     dword ptr [rax+rax+00h]
0x14005e598  jmp     short loc_14005E55E
0x14005e59a  mov     eax, 28h ; '('
0x14005e59f  mov     dword ptr [rbp+30h+var_90+2], ecx
0x14005e5a2  mov     word ptr [rbp+30h+var_90], ax
0x14005e5a6  lea     rax, [rbp+30h+var_90]
0x14005e5aa  mov     word ptr [rbp+30h+var_90+6], cx
0x14005e5ae  movdqu  [rbp+30h+var_80], xmm0
0x14005e5b3  mov     [rbp+30h+var_70], 1
0x14005e5bb  mov     qword ptr [rbp+30h+var_90+8], rdx
0x14005e5bf  jmp     loc_14005E48D
0x14005e5c4  mov     rcx, cs:Filter; Filter
0x14005e5cb  lea     r8, [rbp+30h+EcpList]; EcpList
0x14005e5cf  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14005e5d6  nop     dword ptr [rax+rax+00h]
0x14005e5db  mov     ecx, eax
0x14005e5dd  mov     ebx, eax
0x14005e5df  call    HsmDbgBreakOnStatus
0x14005e5e4  test    ebx, ebx
0x14005e5e6  jns     short loc_14005E61E
0x14005e5e8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e5ef  lea     rax, WPP_GLOBAL_Control
0x14005e5f6  cmp     rcx, rax
0x14005e5f9  jz      loc_14005E525
0x14005e5ff  mov     eax, [rcx+2Ch]
0x14005e602  test    al, 1
0x14005e604  jz      loc_14005E525
0x14005e60a  cmp     byte ptr [rcx+29h], 2
0x14005e60e  jb      loc_14005E525
0x14005e614  mov     edx, 0Ah
0x14005e619  jmp     loc_14005E6DC
0x14005e61e  xor     ecx, ecx
0x14005e620  lea     rax, [rbp+30h+EcpContext]
0x14005e624  mov     [rsp+130h+IoStatusBlock], rax; EcpContext
0x14005e629  lea     rdx, GUID_ECP_OPEN_PARAMETERS; EcpType
0x14005e630  lea     rax, qword_140029240
0x14005e637  xor     r9d, r9d; Flags
0x14005e63a  mov     [rsp+130h+ObjectAttributes], rax; LookasideList
0x14005e63f  mov     r8d, 8; SizeOfContext
0x14005e645  mov     qword ptr [rsp+130h+DesiredAccess], rcx; CleanupCallback
0x14005e64a  mov     rcx, cs:Filter; Filter
0x14005e651  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14005e658  nop     dword ptr [rax+rax+00h]
0x14005e65d  mov     ecx, eax
0x14005e65f  mov     ebx, eax
0x14005e661  call    HsmDbgBreakOnStatus
0x14005e666  test    ebx, ebx
0x14005e668  js      short loc_14005E6AB
0x14005e66a  mov     r8, [rbp+30h+EcpContext]; EcpContext
0x14005e66e  mov     rdx, [rbp+30h+EcpList]; EcpList
0x14005e672  mov     rcx, cs:Filter; Filter
0x14005e679  call    cs:__imp_FltInsertExtraCreateParameter
0x14005e680  nop     dword ptr [rax+rax+00h]
0x14005e685  mov     rax, [rbp+30h+EcpContext]
0x14005e689  xor     ecx, ecx
0x14005e68b  mov     [rax], rcx
0x14005e68e  mov     rax, [rbp+30h+EcpContext]
0x14005e692  mov     word ptr [rax], 8
0x14005e697  mov     rax, [rbp+30h+EcpContext]
0x14005e69b  mov     dword ptr [rax+4], 3
0x14005e6a2  mov     rdx, [rbp+30h+EcpList]
0x14005e6a6  jmp     loc_14005E463
0x14005e6ab  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e6b2  lea     rax, WPP_GLOBAL_Control
0x14005e6b9  cmp     rcx, rax
0x14005e6bc  jz      loc_14005E525
0x14005e6c2  mov     eax, [rcx+2Ch]
0x14005e6c5  test    al, 1
0x14005e6c7  jz      loc_14005E525
0x14005e6cd  cmp     byte ptr [rcx+29h], 2
0x14005e6d1  jb      loc_14005E525
0x14005e6d7  mov     edx, 0Bh
0x14005e6dc  mov     rcx, [rcx+18h]
0x14005e6e0  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005e6e7  mov     r9, r13
0x14005e6ea  mov     [rsp+130h+DesiredAccess], ebx
0x14005e6ee  call    WPP_SF_qd
0x14005e6f3  jmp     loc_14005E525
0x14005e6f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e6ff  lea     rax, WPP_GLOBAL_Control
0x14005e706  cmp     rcx, rax
0x14005e709  jz      short loc_14005E738
0x14005e70b  mov     eax, [rcx+2Ch]
0x14005e70e  test    al, 1
0x14005e710  jz      short loc_14005E738
0x14005e712  cmp     byte ptr [rcx+29h], 2
0x14005e716  jb      short loc_14005E738
0x14005e718  mov     rcx, [rcx+18h]
0x14005e71c  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005e723  mov     edx, 0Ch
0x14005e728  mov     [rsp+130h+DesiredAccess], 0C0000056h
0x14005e730  mov     r9, r13
0x14005e733  call    WPP_SF_qd
0x14005e738  mov     ebx, 0C0000034h
0x14005e73d  jmp     loc_14005E50D
0x14005e742  call    cs:__imp_ObfDereferenceObject
0x14005e749  nop     dword ptr [rax+rax+00h]
0x14005e74e  jmp     loc_14005E56B
0x14005e753  call    cs:__imp_FltClose
0x14005e75a  nop     dword ptr [rax+rax+00h]
0x14005e75f  jmp     loc_14005E578
```
