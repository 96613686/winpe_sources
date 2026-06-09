# CscStorepLowIoRenameFile_WithOwnIrp

- ea: `0x14008a6bc`
- end: `0x14008aa2a`
- name: `CscStorepLowIoRenameFile_WithOwnIrp`
- size: `878`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, char)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x140029cb0`

## callees

- `0x1400081b0`
- `0x140010e20`
- `0x140012ed0`
- `0x140017968`
- `0x1400190ec`
- `0x140029aac`
- `0x14002a4d8`
- `0x14002f010`
- `0x14008a6bc`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14008a814`
- `ntoskrnl!ObfDereferenceObject` at `0x14008a940`
- `ntoskrnl!ObfDereferenceObject` at `0x14008a814`
- `ntoskrnl!ObfDereferenceObject` at `0x14008a940`
- `ntoskrnl!IoFileObjectType` at `0x14008a7d2`
- `ntoskrnl!IoFileObjectType` at `0x14008a909`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008a7f3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008a92a`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008a7f3`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14008a92a`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14008a84e`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14008a84e`
- `ntoskrnl!IoCreateFile` at `0x14008a8c3`
- `ntoskrnl!IoCreateFile` at `0x14008a8c3`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008a85f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008a8d4`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008a85f`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14008a8d4`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14008a951`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14008a964`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14008a951`
- `ntoskrnl!IoGetRelatedDeviceObject` at `0x14008a964`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoRenameFile_WithOwnIrp(
        HANDLE FileHandle,
        __int64 a2,
        void *a3,
        struct _UNICODE_STRING *a4,
        char a5)
{
  NTSTATUS InformationFile; // edi
  int v9; // ebx
  int v10; // edi
  char v11; // cl
  IRP *TopLevelIrp; // rbx
  struct _DEVICE_OBJECT *RelatedDeviceObject; // rbx
  int v15; // [rsp+70h] [rbp-90h] BYREF
  PVOID Object; // [rsp+78h] [rbp-88h] BYREF
  PVOID v17; // [rsp+80h] [rbp-80h] BYREF
  __int64 v18; // [rsp+88h] [rbp-78h] BYREF
  void *FileHandlea; // [rsp+90h] [rbp-70h] BYREF
  __int64 v20; // [rsp+98h] [rbp-68h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-60h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D0h] [rbp-30h] BYREF
  _OWORD FileInformation[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v24; // [rsp+100h] [rbp+0h]

  FileHandlea = 0;
  IoStatusBlock = 0;
  v17 = 0;
  memset(&ObjectAttributes, 0, 44);
  v20 = 0;
  v15 = 0;
  Object = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qqZc(
      WPP_GLOBAL_Control->AttachedDevice,
      32,
      (_DWORD)WPP_GLOBAL_Control,
      (_DWORD)FileHandle,
      (char)a3,
      (__int64)a4,
      a5 != 0 ? 89 : 78);
  LODWORD(v18) = 0;
  v24 = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  InformationFile = CscStorepLowIoQueryInformationFile(
                      FileHandle,
                      FileInformation,
                      0x28u,
                      FileBasicInformation,
                      (__int64)&v18);
  if ( InformationFile >= 0 )
  {
    InformationFile = CscStorepLowIoAllocateAndInitializeRenameInformation(
                        (unsigned int)&v20,
                        (unsigned int)&v15,
                        (_DWORD)a3,
                        (_DWORD)a4,
                        a5);
    if ( InformationFile >= 0 )
    {
      InformationFile = ObReferenceObjectByHandle(FileHandle, 0, (POBJECT_TYPE)IoFileObjectType, 0, &Object, 0);
      if ( InformationFile < 0 )
      {
        v9 = 2514;
      }
      else
      {
        v10 = v24 & 0x10;
        ObfDereferenceObject(Object);
        ObjectAttributes.Length = 48;
        ObjectAttributes.RootDirectory = a3;
        v11 = ~(unsigned __int8)(*((_DWORD *)Object + 20) >> 11);
        ObjectAttributes.ObjectName = a4;
        ObjectAttributes.Attributes = v11 & 0x40 | 0x200;
        *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
        TopLevelIrp = IoGetTopLevelIrp();
        IoSetTopLevelIrp(0);
        InformationFile = IoCreateFile(
                            &FileHandlea,
                            (v10 != 0 ? 4 : 2) | 0x100000,
                            &ObjectAttributes,
                            &IoStatusBlock,
                            0,
                            0,
                            7u,
                            1u,
                            0x4000u,
                            0,
                            0,
                            CreateFileTypeNone,
                            0,
                            0x104u);
        IoSetTopLevelIrp(TopLevelIrp);
        if ( InformationFile >= 0 )
        {
          if ( a5 || IoStatusBlock.Information != 4 )
          {
            InformationFile = ObReferenceObjectByHandle(FileHandlea, 0, (POBJECT_TYPE)IoFileObjectType, 0, &v17, 0);
            if ( InformationFile < 0 )
            {
              v9 = 2582;
            }
            else
            {
              ObfDereferenceObject(v17);
              RelatedDeviceObject = IoGetRelatedDeviceObject((PFILE_OBJECT)Object);
              if ( IoGetRelatedDeviceObject((PFILE_OBJECT)v17) == RelatedDeviceObject )
              {
                InformationFile = CscStorepLowIoRenameFileIrp((PFILE_OBJECT)Object);
                v9 = 0;
                if ( InformationFile < 0 )
                  v9 = 2606;
              }
              else
              {
                InformationFile = -1073741612;
                v9 = 2593;
              }
            }
          }
          else
          {
            InformationFile = -1073741771;
            v9 = 2571;
          }
        }
        else
        {
          v9 = 2556;
        }
      }
    }
    else
    {
      v9 = 2510;
    }
  }
  else
  {
    v9 = 2500;
  }
  if ( FileHandlea )
    CscStorepLowIoClose(FileHandlea);
  if ( v20 )
    CscStorepLowIoFreeRenameInformation();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Dd(
      WPP_GLOBAL_Control->AttachedDevice,
      33,
      WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
      (unsigned int)InformationFile,
      v9);
  return (unsigned int)InformationFile;
}

```

## disassembly

```asm
0x14008a6bc  push    rbp
0x14008a6be  push    rbx
0x14008a6bf  push    rsi
0x14008a6c0  push    rdi
0x14008a6c1  push    r12
0x14008a6c3  push    r14
0x14008a6c5  push    r15
0x14008a6c7  lea     rbp, [rsp-10h]
0x14008a6cc  sub     rsp, 110h
0x14008a6d3  mov     rax, cs:__security_cookie
0x14008a6da  xor     rax, rsp
0x14008a6dd  mov     [rbp+40h+var_38], rax
0x14008a6e1  xor     r12d, r12d
0x14008a6e4  xorps   xmm0, xmm0
0x14008a6e7  movups  xmmword ptr [rbp+40h+ObjectAttributes.ObjectName], xmm0
0x14008a6eb  mov     r15, r9
0x14008a6ee  mov     r14, r8
0x14008a6f1  movups  xmmword ptr [rbp+40h+ObjectAttributes+1Ch], xmm0
0x14008a6f5  mov     rbx, rcx
0x14008a6f8  mov     [rbp+40h+FileHandle], r12
0x14008a6fc  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x14008a700  xor     eax, eax
0x14008a702  mov     [rbp+40h+var_C0], r12
0x14008a706  movups  xmmword ptr [rbp+40h+ObjectAttributes.Length], xmm0
0x14008a70a  mov     [rbp+40h+var_A8], r12
0x14008a70e  mov     [rsp+140h+var_D0], r12d
0x14008a713  mov     [rsp+140h+var_C8], r12
0x14008a718  mov     r8, cs:WPP_GLOBAL_Control
0x14008a71f  lea     rax, WPP_GLOBAL_Control
0x14008a726  mov     sil, [rbp+40h+arg_20]
0x14008a72a  cmp     r8, rax
0x14008a72d  jz      short loc_14008A765
0x14008a72f  test    dword ptr [r8+2Ch], 40000h
0x14008a737  jz      short loc_14008A765
0x14008a739  mov     al, sil
0x14008a73c  lea     edx, [r12+20h]
0x14008a741  neg     al
0x14008a743  sbb     cl, cl
0x14008a745  and     cl, 0Bh
0x14008a748  add     cl, 4Eh ; 'N'
0x14008a74b  mov     byte ptr [rsp+140h+ShareAccess], cl
0x14008a74f  mov     rcx, [r8+18h]
0x14008a753  mov     [rsp+140h+HandleInformation], r9
0x14008a758  mov     r9, rbx
0x14008a75b  mov     [rsp+140h+Object], r14
0x14008a760  call    WPP_SF_qqZc
0x14008a765  xor     eax, eax
0x14008a767  mov     dword ptr [rbp+40h+var_B8], r12d
0x14008a76b  xorps   xmm0, xmm0
0x14008a76e  mov     [rbp+40h+var_40], rax
0x14008a772  mov     r9d, 4; FileInformationClass
0x14008a778  lea     rax, [rbp+40h+var_B8]
0x14008a77c  lea     rdx, [rbp+40h+FileInformation]; FileInformation
0x14008a780  mov     [rsp+140h+Object], rax; __int64
0x14008a785  mov     rcx, rbx; FileHandle
0x14008a788  movups  [rbp+40h+FileInformation], xmm0
0x14008a78c  lea     r8d, [r9+24h]; Length
0x14008a790  movups  [rbp+40h+var_50], xmm0
0x14008a794  call    CscStorepLowIoQueryInformationFile
0x14008a799  mov     edi, eax
0x14008a79b  test    eax, eax
0x14008a79d  jns     short loc_14008A7A9
0x14008a79f  mov     ebx, 9C4h
0x14008a7a4  jmp     loc_14008A9B5
0x14008a7a9  mov     r9, r15
0x14008a7ac  mov     byte ptr [rsp+140h+Object], sil
0x14008a7b1  mov     r8, r14
0x14008a7b4  lea     rdx, [rsp+140h+var_D0]
0x14008a7b9  lea     rcx, [rbp+40h+var_A8]
0x14008a7bd  call    CscStorepLowIoAllocateAndInitializeRenameInformation
0x14008a7c2  mov     edi, eax
0x14008a7c4  test    eax, eax
0x14008a7c6  jns     short loc_14008A7D2
0x14008a7c8  mov     ebx, 9CEh
0x14008a7cd  jmp     loc_14008A9B5
0x14008a7d2  mov     r8, cs:__imp_IoFileObjectType
0x14008a7d9  lea     rax, [rsp+140h+var_C8]
0x14008a7de  mov     [rsp+140h+HandleInformation], r12; HandleInformation
0x14008a7e3  xor     r9d, r9d; AccessMode
0x14008a7e6  xor     edx, edx; DesiredAccess
0x14008a7e8  mov     [rsp+140h+Object], rax; Object
0x14008a7ed  mov     rcx, rbx; Handle
0x14008a7f0  mov     r8, [r8]; ObjectType
0x14008a7f3  call    cs:__imp_ObReferenceObjectByHandle
0x14008a7fa  nop     dword ptr [rax+rax+00h]
0x14008a7ff  mov     edi, eax
0x14008a801  test    eax, eax
0x14008a803  js      loc_14008A9B0
0x14008a809  mov     edi, dword ptr [rbp+40h+var_40]
0x14008a80c  mov     rcx, [rsp+140h+var_C8]; Object
0x14008a811  and     edi, 10h
0x14008a814  call    cs:__imp_ObfDereferenceObject
0x14008a81b  nop     dword ptr [rax+rax+00h]
0x14008a820  mov     rax, [rsp+140h+var_C8]
0x14008a825  xorps   xmm0, xmm0
0x14008a828  mov     [rbp+40h+ObjectAttributes.Length], 30h ; '0'
0x14008a82f  mov     [rbp+40h+ObjectAttributes.RootDirectory], r14
0x14008a833  mov     ecx, [rax+50h]
0x14008a836  shr     ecx, 0Bh
0x14008a839  not     ecx
0x14008a83b  mov     [rbp+40h+ObjectAttributes.ObjectName], r15
0x14008a83f  and     ecx, 40h
0x14008a842  bts     ecx, 9
0x14008a846  mov     [rbp+40h+ObjectAttributes.Attributes], ecx
0x14008a849  movdqu  xmmword ptr [rbp+40h+ObjectAttributes.SecurityDescriptor], xmm0
0x14008a84e  call    cs:__imp_IoGetTopLevelIrp
0x14008a855  nop     dword ptr [rax+rax+00h]
0x14008a85a  xor     ecx, ecx; Irp
0x14008a85c  mov     rbx, rax
0x14008a85f  call    cs:__imp_IoSetTopLevelIrp
0x14008a866  nop     dword ptr [rax+rax+00h]
0x14008a86b  mov     [rsp+140h+Options], 104h; Options
0x14008a873  lea     r9, [rbp+40h+IoStatusBlock]; IoStatusBlock
0x14008a877  mov     [rsp+140h+InternalParameters], r12; InternalParameters
0x14008a87c  lea     r8, [rbp+40h+ObjectAttributes]; ObjectAttributes
0x14008a880  mov     [rsp+140h+CreateFileType], r12d; CreateFileType
0x14008a885  lea     rcx, [rbp+40h+FileHandle]; FileHandle
0x14008a889  mov     [rsp+140h+EaLength], r12d; EaLength
0x14008a88e  neg     edi
0x14008a890  mov     [rsp+140h+EaBuffer], r12; EaBuffer
0x14008a895  sbb     edx, edx
0x14008a897  mov     [rsp+140h+CreateOptions], 4000h; CreateOptions
0x14008a89f  and     edx, 2
0x14008a8a2  mov     [rsp+140h+Disposition], 1; Disposition
0x14008a8aa  add     edx, 2
0x14008a8ad  mov     [rsp+140h+ShareAccess], 7; ShareAccess
0x14008a8b5  bts     edx, 14h; DesiredAccess
0x14008a8b9  mov     dword ptr [rsp+140h+HandleInformation], r12d; FileAttributes
0x14008a8be  mov     [rsp+140h+Object], r12; AllocationSize
0x14008a8c3  call    cs:__imp_IoCreateFile
0x14008a8ca  nop     dword ptr [rax+rax+00h]
0x14008a8cf  mov     rcx, rbx; Irp
0x14008a8d2  mov     edi, eax
0x14008a8d4  call    cs:__imp_IoSetTopLevelIrp
0x14008a8db  nop     dword ptr [rax+rax+00h]
0x14008a8e0  test    edi, edi
0x14008a8e2  jns     short loc_14008A8EE
0x14008a8e4  mov     ebx, 9FCh
0x14008a8e9  jmp     loc_14008A9B5
0x14008a8ee  test    sil, sil
0x14008a8f1  jnz     short loc_14008A909
0x14008a8f3  cmp     [rbp+40h+IoStatusBlock.Information], 4
0x14008a8f8  jnz     short loc_14008A909
0x14008a8fa  mov     edi, 0C0000035h
0x14008a8ff  mov     ebx, 0A0Bh
0x14008a904  jmp     loc_14008A9B5
0x14008a909  mov     r8, cs:__imp_IoFileObjectType
0x14008a910  lea     rax, [rbp+40h+var_C0]
0x14008a914  mov     rcx, [rbp+40h+FileHandle]; Handle
0x14008a918  xor     r9d, r9d; AccessMode
0x14008a91b  mov     [rsp+140h+HandleInformation], r12; HandleInformation
0x14008a920  xor     edx, edx; DesiredAccess
0x14008a922  mov     [rsp+140h+Object], rax; Object
0x14008a927  mov     r8, [r8]; ObjectType
0x14008a92a  call    cs:__imp_ObReferenceObjectByHandle
0x14008a931  nop     dword ptr [rax+rax+00h]
0x14008a936  mov     edi, eax
0x14008a938  test    eax, eax
0x14008a93a  js      short loc_14008A9A9
0x14008a93c  mov     rcx, [rbp+40h+var_C0]; Object
0x14008a940  call    cs:__imp_ObfDereferenceObject
0x14008a947  nop     dword ptr [rax+rax+00h]
0x14008a94c  mov     rcx, [rsp+140h+var_C8]; FileObject
0x14008a951  call    cs:__imp_IoGetRelatedDeviceObject
0x14008a958  nop     dword ptr [rax+rax+00h]
0x14008a95d  mov     rcx, [rbp+40h+var_C0]; FileObject
0x14008a961  mov     rbx, rax
0x14008a964  call    cs:__imp_IoGetRelatedDeviceObject
0x14008a96b  nop     dword ptr [rax+rax+00h]
0x14008a970  cmp     rax, rbx
0x14008a973  jz      short loc_14008A981
0x14008a975  mov     edi, 0C00000D4h
0x14008a97a  mov     ebx, 0A21h
0x14008a97f  jmp     short loc_14008A9B5
0x14008a981  mov     r9d, [rsp+140h+var_D0]
0x14008a986  mov     r8, [rbp+40h+var_A8]
0x14008a98a  mov     rdx, [rbp+40h+var_C0]
0x14008a98e  mov     rcx, [rsp+140h+var_C8]; FileObject
0x14008a993  call    CscStorepLowIoRenameFileIrp
0x14008a998  mov     edi, eax
0x14008a99a  mov     ebx, r12d
0x14008a99d  test    edi, edi
0x14008a99f  mov     eax, 0A2Eh
0x14008a9a4  cmovs   ebx, eax
0x14008a9a7  jmp     short loc_14008A9B5
0x14008a9a9  mov     ebx, 0A16h
0x14008a9ae  jmp     short loc_14008A9B5
0x14008a9b0  mov     ebx, 9D2h
0x14008a9b5  mov     rcx, [rbp+40h+FileHandle]; Handle
0x14008a9b9  test    rcx, rcx
0x14008a9bc  jz      short loc_14008A9C3
0x14008a9be  call    CscStorepLowIoClose
0x14008a9c3  mov     rcx, [rbp+40h+var_A8]
0x14008a9c7  test    rcx, rcx
0x14008a9ca  jz      short loc_14008A9D1
0x14008a9cc  call    CscStorepLowIoFreeRenameInformation
0x14008a9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x14008a9d8  lea     rax, WPP_GLOBAL_Control
0x14008a9df  cmp     rcx, rax
0x14008a9e2  jz      short loc_14008AA09
0x14008a9e4  test    dword ptr [rcx+2Ch], 40000h
0x14008a9eb  jz      short loc_14008AA09
0x14008a9ed  mov     rcx, [rcx+18h]
0x14008a9f1  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14008a9f8  mov     edx, 21h ; '!'
0x14008a9fd  mov     dword ptr [rsp+140h+Object], ebx
0x14008aa01  mov     r9d, edi
0x14008aa04  call    WPP_SF_Dd
0x14008aa09  mov     eax, edi
0x14008aa0b  mov     rcx, [rbp+40h+var_38]
0x14008aa0f  xor     rcx, rsp; StackCookie
0x14008aa12  call    __security_check_cookie
0x14008aa17  add     rsp, 110h
0x14008aa1e  pop     r15
0x14008aa20  pop     r14
0x14008aa22  pop     r12
0x14008aa24  pop     rdi
0x14008aa25  pop     rsi
0x14008aa26  pop     rbx
0x14008aa27  pop     rbp
0x14008aa28  retn
```
