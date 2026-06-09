# HsmiOpenFile

- ea: `0x14005e2d0`
- end: `0x14005e644`
- name: `HsmiOpenFile`
- size: `884`
- prototype: ``
- caller_count: `6`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14005cf90`
- `0x14005e64c`
- `0x14005e7e4`
- `0x14005eb40`
- `0x14005eee0`
- `0x14007f1a0`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14005e2d0`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14005e622`
- `ntoskrnl!ObfDereferenceObject` at `0x14005e622`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14005e4af`
- `FLTMGR!FltAllocateExtraCreateParameterList` at `0x14005e4af`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14005e46c`
- `FLTMGR!FltFreeExtraCreateParameterList` at `0x14005e46c`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14005e559`
- `FLTMGR!FltInsertExtraCreateParameter` at `0x14005e559`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14005e531`
- `FLTMGR!FltAllocateExtraCreateParameterFromLookasideList` at `0x14005e531`
- `FLTMGR!FltClose` at `0x14005e633`
- `FLTMGR!FltClose` at `0x14005e633`
- `FLTMGR!FltCreateFileEx2` at `0x14005e3cc`
- `FLTMGR!FltCreateFileEx2` at `0x14005e3cc`

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
  ACCESS_MASK DesiredAccess[2]; // [rsp+28h] [rbp-E0h]
  ACCESS_MASK DesiredAccessa[2]; // [rsp+28h] [rbp-E0h]
  PVOID EcpContext; // [rsp+88h] [rbp-80h] BYREF
  PECP_LIST EcpList; // [rsp+90h] [rbp-78h] BYREF
  PFILE_OBJECT FileObject; // [rsp+98h] [rbp-70h] BYREF
  void *FileHandle; // [rsp+A0h] [rbp-68h] BYREF
  __int128 v25; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v26; // [rsp+B8h] [rbp-50h]
  __int64 v27; // [rsp+C8h] [rbp-40h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+D0h] [rbp-38h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+100h] [rbp-8h] BYREF

  FileObject = 0;
  FileHandle = 0;
  v13 = 0;
  LOWORD(v27) = 0;
  v25 = 0;
  EcpList = 0;
  v26 = 0;
  EcpContext = 0;
  *a8 = 0;
  *a9 = 0;
  if ( a7 )
  {
    v15 = FltAllocateExtraCreateParameterList(Filter, 0, &EcpList);
    HsmDbgBreakOnStatus((unsigned int)v15);
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
      HsmDbgBreakOnStatus((unsigned int)v15);
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
    DesiredAccess[0] = v15;
    WPP_SF_qd(v17->AttachedDevice, v18, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids, a1, *(_QWORD *)DesiredAccess);
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
    *(_DWORD *)((char *)&v25 + 2) = 0;
    LOWORD(v25) = 40;
    v14 = (struct _IO_DRIVER_CREATE_CONTEXT *)&v25;
    WORD3(v25) = 0;
    v26 = 0;
    v27 = 1;
    *((_QWORD *)&v25 + 1) = v13;
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
  HsmDbgBreakOnStatus((unsigned int)v15);
  if ( v15 == -1073741738 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      DesiredAccessa[0] = -1073741738;
      WPP_SF_qd(
        WPP_GLOBAL_Control->AttachedDevice,
        12,
        WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids,
        a1,
        *(_QWORD *)DesiredAccessa);
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
0x14005e2d0  mov     rax, rsp
0x14005e2d3  push    rbp
0x14005e2d4  push    rbx
0x14005e2d5  lea     rbp, [rax-38h]
0x14005e2d9  sub     rsp, 128h
0x14005e2e0  mov     [rax+8], rsi
0x14005e2e4  xorps   xmm0, xmm0
0x14005e2e7  mov     rsi, [rbp+30h+arg_40]
0x14005e2ee  mov     [rax+10h], rdi
0x14005e2f2  mov     rdi, [rbp+30h+arg_38]
0x14005e2f6  mov     [rax+18h], r12
0x14005e2fa  mov     r12, rdx
0x14005e2fd  mov     [rax-18h], r13
0x14005e301  mov     r13, rcx
0x14005e304  xor     ecx, ecx
0x14005e306  mov     [rax-20h], r14
0x14005e30a  mov     [rax-28h], r15
0x14005e30e  mov     r14, r8
0x14005e311  xor     eax, eax
0x14005e313  mov     [rbp+30h+FileObject], rcx
0x14005e317  mov     r15d, r9d
0x14005e31a  mov     [rbp+30h+FileHandle], rcx
0x14005e31e  mov     edx, ecx; Flags
0x14005e320  mov     word ptr [rbp+30h+var_70], ax
0x14005e324  movups  [rbp+30h+var_90], xmm0
0x14005e328  mov     [rbp+30h+EcpList], rcx
0x14005e32c  movups  [rbp+30h+var_80], xmm0
0x14005e330  mov     [rbp+30h+EcpContext], rcx
0x14005e334  mov     [rdi], rcx
0x14005e337  mov     [rsi], rcx
0x14005e33a  cmp     [rbp+30h+arg_30], al
0x14005e33d  jnz     loc_14005E4A4
0x14005e343  mov     [rbp+30h+var_68.Length], 30h ; '0'
0x14005e34a  xorps   xmm0, xmm0
0x14005e34d  mov     [rbp+30h+var_68.RootDirectory], rcx
0x14005e351  mov     [rbp+30h+var_68.Attributes], 240h
0x14005e358  mov     [rbp+30h+var_68.ObjectName], r14
0x14005e35c  movdqu  xmmword ptr [rbp+30h+var_68.SecurityDescriptor], xmm0
0x14005e361  test    rdx, rdx
0x14005e364  jnz     loc_14005E47A
0x14005e36a  mov     rax, rcx
0x14005e36d  mov     [rsp+78h], rax; DriverContext
0x14005e372  lea     r9, [rbp+30h+FileObject]; FileObject
0x14005e376  mov     eax, [rbp+30h+arg_28]
0x14005e379  lea     r8, [rbp+30h+FileHandle]; FileHandle
0x14005e37d  mov     [rsp+130h+Flags], 800h; Flags
0x14005e385  mov     rdx, r12; Instance
0x14005e388  mov     [rsp+130h+EaLength], ecx; EaLength
0x14005e38c  mov     [rsp+130h+EaBuffer], rcx; EaBuffer
0x14005e391  mov     [rsp+130h+CreateOptions], eax; CreateOptions
0x14005e395  lea     rax, [rbp+30h+var_38]
0x14005e399  mov     [rsp+130h+CreateDisposition], 1; CreateDisposition
0x14005e3a1  mov     [rsp+130h+ShareAccess], 7; ShareAccess
0x14005e3a9  mov     [rsp+130h+FileAttributes], ecx; FileAttributes
0x14005e3ad  mov     [rsp+130h+AllocationSize], rcx; AllocationSize
0x14005e3b2  mov     rcx, cs:Filter; Filter
0x14005e3b9  mov     [rsp+130h+IoStatusBlock], rax; IoStatusBlock
0x14005e3be  lea     rax, [rbp+30h+var_68]
0x14005e3c2  mov     [rsp+130h+ObjectAttributes], rax; ObjectAttributes
0x14005e3c7  mov     [rsp+130h+DesiredAccess], r15d; DesiredAccess
0x14005e3cc  call    cs:__imp_FltCreateFileEx2
0x14005e3d3  nop     dword ptr [rax+rax+00h]
0x14005e3d8  mov     ecx, eax
0x14005e3da  mov     ebx, eax
0x14005e3dc  call    HsmDbgBreakOnStatus
0x14005e3e1  cmp     ebx, 0C0000056h
0x14005e3e7  jz      loc_14005E5D8
0x14005e3ed  mov     rax, [rbp+30h+FileHandle]
0x14005e3f1  xor     ecx, ecx
0x14005e3f3  mov     [rdi], rax
0x14005e3f6  mov     rax, [rbp+30h+FileObject]
0x14005e3fa  mov     [rsi], rax
0x14005e3fd  mov     [rbp+30h+FileHandle], rcx
0x14005e401  mov     [rbp+30h+FileObject], rcx
0x14005e405  mov     rdx, [rbp+30h+EcpList]; EcpList
0x14005e409  mov     r15, [rsp+130h+var_20]
0x14005e411  mov     r14, [rsp+130h+var_18]
0x14005e419  mov     r13, [rsp+120h]
0x14005e421  mov     r12, [rsp+130h+arg_10]
0x14005e429  mov     rdi, [rsp+130h+arg_8]
0x14005e431  mov     rsi, [rsp+130h+arg_0]
0x14005e439  test    rdx, rdx
0x14005e43c  jnz     short loc_14005E465
0x14005e43e  mov     rcx, [rbp+30h+FileObject]; Object
0x14005e442  test    rcx, rcx
0x14005e445  jnz     loc_14005E622
0x14005e44b  mov     rcx, [rbp+30h+FileHandle]; FileHandle
0x14005e44f  test    rcx, rcx
0x14005e452  jnz     loc_14005E633
0x14005e458  mov     eax, ebx
0x14005e45a  add     rsp, 128h
0x14005e461  pop     rbx
0x14005e462  pop     rbp
0x14005e463  retn
0x14005e465  mov     rcx, cs:Filter; Filter
0x14005e46c  call    cs:__imp_FltFreeExtraCreateParameterList
0x14005e473  nop     dword ptr [rax+rax+00h]
0x14005e478  jmp     short loc_14005E43E
0x14005e47a  mov     eax, 28h ; '('
0x14005e47f  mov     dword ptr [rbp+30h+var_90+2], ecx
0x14005e482  mov     word ptr [rbp+30h+var_90], ax
0x14005e486  lea     rax, [rbp+30h+var_90]
0x14005e48a  mov     word ptr [rbp+30h+var_90+6], cx
0x14005e48e  movdqu  [rbp+30h+var_80], xmm0
0x14005e493  mov     [rbp+30h+var_70], 1
0x14005e49b  mov     qword ptr [rbp+30h+var_90+8], rdx
0x14005e49f  jmp     loc_14005E36D
0x14005e4a4  mov     rcx, cs:Filter; Filter
0x14005e4ab  lea     r8, [rbp+30h+EcpList]; EcpList
0x14005e4af  call    cs:__imp_FltAllocateExtraCreateParameterList
0x14005e4b6  nop     dword ptr [rax+rax+00h]
0x14005e4bb  mov     ecx, eax
0x14005e4bd  mov     ebx, eax
0x14005e4bf  call    HsmDbgBreakOnStatus
0x14005e4c4  test    ebx, ebx
0x14005e4c6  jns     short loc_14005E4FE
0x14005e4c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e4cf  lea     rax, WPP_GLOBAL_Control
0x14005e4d6  cmp     rcx, rax
0x14005e4d9  jz      loc_14005E405
0x14005e4df  mov     eax, [rcx+2Ch]
0x14005e4e2  test    al, 1
0x14005e4e4  jz      loc_14005E405
0x14005e4ea  cmp     byte ptr [rcx+29h], 2
0x14005e4ee  jb      loc_14005E405
0x14005e4f4  mov     edx, 0Ah
0x14005e4f9  jmp     loc_14005E5BC
0x14005e4fe  xor     ecx, ecx
0x14005e500  lea     rax, [rbp+30h+EcpContext]
0x14005e504  mov     [rsp+130h+IoStatusBlock], rax; EcpContext
0x14005e509  lea     rdx, GUID_ECP_OPEN_PARAMETERS; EcpType
0x14005e510  lea     rax, qword_140029240
0x14005e517  xor     r9d, r9d; Flags
0x14005e51a  mov     [rsp+130h+ObjectAttributes], rax; LookasideList
0x14005e51f  mov     r8d, 8; SizeOfContext
0x14005e525  mov     qword ptr [rsp+130h+DesiredAccess], rcx; CleanupCallback
0x14005e52a  mov     rcx, cs:Filter; Filter
0x14005e531  call    cs:__imp_FltAllocateExtraCreateParameterFromLookasideList
0x14005e538  nop     dword ptr [rax+rax+00h]
0x14005e53d  mov     ecx, eax
0x14005e53f  mov     ebx, eax
0x14005e541  call    HsmDbgBreakOnStatus
0x14005e546  test    ebx, ebx
0x14005e548  js      short loc_14005E58B
0x14005e54a  mov     r8, [rbp+30h+EcpContext]; EcpContext
0x14005e54e  mov     rdx, [rbp+30h+EcpList]; EcpList
0x14005e552  mov     rcx, cs:Filter; Filter
0x14005e559  call    cs:__imp_FltInsertExtraCreateParameter
0x14005e560  nop     dword ptr [rax+rax+00h]
0x14005e565  mov     rax, [rbp+30h+EcpContext]
0x14005e569  xor     ecx, ecx
0x14005e56b  mov     [rax], rcx
0x14005e56e  mov     rax, [rbp+30h+EcpContext]
0x14005e572  mov     word ptr [rax], 8
0x14005e577  mov     rax, [rbp+30h+EcpContext]
0x14005e57b  mov     dword ptr [rax+4], 3
0x14005e582  mov     rdx, [rbp+30h+EcpList]
0x14005e586  jmp     loc_14005E343
0x14005e58b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e592  lea     rax, WPP_GLOBAL_Control
0x14005e599  cmp     rcx, rax
0x14005e59c  jz      loc_14005E405
0x14005e5a2  mov     eax, [rcx+2Ch]
0x14005e5a5  test    al, 1
0x14005e5a7  jz      loc_14005E405
0x14005e5ad  cmp     byte ptr [rcx+29h], 2
0x14005e5b1  jb      loc_14005E405
0x14005e5b7  mov     edx, 0Bh
0x14005e5bc  mov     rcx, [rcx+18h]
0x14005e5c0  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005e5c7  mov     r9, r13
0x14005e5ca  mov     [rsp+130h+DesiredAccess], ebx
0x14005e5ce  call    WPP_SF_qd
0x14005e5d3  jmp     loc_14005E405
0x14005e5d8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e5df  lea     rax, WPP_GLOBAL_Control
0x14005e5e6  cmp     rcx, rax
0x14005e5e9  jz      short loc_14005E618
0x14005e5eb  mov     eax, [rcx+2Ch]
0x14005e5ee  test    al, 1
0x14005e5f0  jz      short loc_14005E618
0x14005e5f2  cmp     byte ptr [rcx+29h], 2
0x14005e5f6  jb      short loc_14005E618
0x14005e5f8  mov     rcx, [rcx+18h]
0x14005e5fc  lea     r8, WPP_e04056f4b0da39b6a3bd8dcd61993cdf_Traceguids
0x14005e603  mov     edx, 0Ch
0x14005e608  mov     [rsp+130h+DesiredAccess], 0C0000056h
0x14005e610  mov     r9, r13
0x14005e613  call    WPP_SF_qd
0x14005e618  mov     ebx, 0C0000034h
0x14005e61d  jmp     loc_14005E3ED
0x14005e622  call    cs:__imp_ObfDereferenceObject
0x14005e629  nop     dword ptr [rax+rax+00h]
0x14005e62e  jmp     loc_14005E44B
0x14005e633  call    cs:__imp_FltClose
0x14005e63a  nop     dword ptr [rax+rax+00h]
0x14005e63f  jmp     loc_14005E458
```
