# CscStorepLowIoCreateFilePostedRoutine

- ea: `0x14000e260`
- end: `0x14000e6d8`
- name: `CscStorepLowIoCreateFilePostedRoutine`
- size: `1144`
- prototype: `NTSTATUS __fastcall(__int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callees

- `0x14000e260`
- `0x140018930`
- `0x140018fd0`
- `0x14002a078`
- `0x14002a3e4`
- `0x14002f140`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x14000e459`
- `ntoskrnl!ZwCreateFile` at `0x14000e459`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000e379`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000e379`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000e38a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000e46a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000e38a`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000e46a`
- `ntoskrnl!SeImpersonateClientEx` at `0x14000e62f`
- `ntoskrnl!SeImpersonateClientEx` at `0x14000e62f`
- `ntoskrnl!PsRevertToSelf` at `0x14000e6c7`
- `ntoskrnl!PsRevertToSelf` at `0x14000e6c7`

## pseudocode

```c
NTSTATUS __fastcall CscStorepLowIoCreateFilePostedRoutine(__int64 a1)
{
  char v2; // di
  struct _SECURITY_CLIENT_CONTEXT *v3; // rcx
  __int64 v4; // rcx
  void *v5; // r8
  ULONG v6; // edx
  ULONG v7; // r9d
  ULONG v8; // r10d
  ULONG v9; // r11d
  union _LARGE_INTEGER *AllocationSize; // rsi
  ULONG CreateOptions; // r12d
  struct _UNICODE_STRING *v12; // r13
  ULONG_PTR *v13; // r14
  void **v14; // r15
  PDEVICE_OBJECT v15; // rbx
  IRP *TopLevelIrp; // rbx
  ULONG_PTR Information; // r13
  NTSTATUS v18; // esi
  int v19; // r8d
  void *v20; // r9
  NTSTATUS result; // eax
  size_t v22; // r8
  int v23; // r8d
  NTSTATUS v24; // edi
  ULONG ShareAccess; // [rsp+80h] [rbp-B8h]
  ULONG FileAttributes; // [rsp+84h] [rbp-B4h]
  void *v27; // [rsp+88h] [rbp-B0h]
  __int64 v28; // [rsp+90h] [rbp-A8h] BYREF
  void *v29; // [rsp+98h] [rbp-A0h]
  PVOID EaBuffer; // [rsp+A0h] [rbp-98h]
  void *FileHandle; // [rsp+A8h] [rbp-90h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B0h] [rbp-88h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-78h] BYREF
  USHORT Length; // [rsp+140h] [rbp+8h]
  ACCESS_MASK DesiredAccess; // [rsp+148h] [rbp+10h]
  ULONG EaLength; // [rsp+150h] [rbp+18h]
  ULONG CreateDisposition; // [rsp+158h] [rbp+20h]

  v2 = 0;
  v3 = *(struct _SECURITY_CLIENT_CONTEXT **)(a1 + 136);
  if ( !v3 )
    goto LABEL_2;
  result = SeImpersonateClientEx(v3, 0);
  v24 = result;
  if ( result >= 0 )
  {
    v2 = 1;
LABEL_2:
    v4 = *(_QWORD *)(a1 + 120);
    v5 = *(void **)(a1 + 104);
    v6 = *(_DWORD *)(a1 + 112);
    v7 = *(_DWORD *)(a1 + 96);
    v8 = *(_DWORD *)(a1 + 92);
    v9 = *(_DWORD *)(a1 + 88);
    AllocationSize = (union _LARGE_INTEGER *)(a1 + 80);
    if ( !*(_QWORD *)(a1 + 80) )
      AllocationSize = 0;
    CreateOptions = *(_DWORD *)(a1 + 100);
    v12 = *(struct _UNICODE_STRING **)(a1 + 64);
    DesiredAccess = *(_DWORD *)(a1 + 72);
    v13 = *(ULONG_PTR **)(a1 + 128);
    v27 = *(void **)(a1 + 56);
    v14 = *(void ***)(a1 + 40);
    v29 = *(void **)(a1 + 120);
    EaLength = v6;
    EaBuffer = v5;
    CreateDisposition = v7;
    ShareAccess = v8;
    FileAttributes = v9;
    FileHandle = 0;
    IoStatusBlock = 0;
    memset(&ObjectAttributes, 0, 44);
    if ( (CreateOptions & 0x2000) != 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
      {
        v28 = 0;
        v22 = 8;
        Length = v12->Length;
        if ( v12->Length <= 8u )
          v22 = v12->Length;
        memmove(&v28, v12->Buffer, v22);
        WPP_SF_qiDDDDDDqDqq(
          v15->AttachedDevice,
          DesiredAccess,
          v23,
          (_DWORD)v27,
          v28,
          Length,
          DesiredAccess,
          FileAttributes,
          ShareAccess,
          CreateDisposition,
          CreateOptions,
          (char)EaBuffer,
          EaLength,
          (char)v29,
          (char)v13);
      }
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_qZDDDDDqDqq(
        WPP_GLOBAL_Control->AttachedDevice,
        DesiredAccess,
        (_DWORD)v5,
        (_DWORD)v27,
        (__int64)v12,
        DesiredAccess,
        v9,
        v8,
        v7,
        CreateOptions,
        (char)v5,
        v6,
        v4,
        (char)v13);
    }
    TopLevelIrp = IoGetTopLevelIrp();
    IoSetTopLevelIrp(0);
    ObjectAttributes.RootDirectory = v27;
    ObjectAttributes.SecurityDescriptor = v29;
    ObjectAttributes.ObjectName = v12;
    Information = -1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.SecurityQualityOfService = 0;
    IoStatusBlock.Status = -1;
    IoStatusBlock.Information = -1;
    v18 = ZwCreateFile(
            &FileHandle,
            DesiredAccess,
            &ObjectAttributes,
            &IoStatusBlock,
            AllocationSize,
            FileAttributes,
            ShareAccess,
            CreateDisposition,
            CreateOptions,
            EaBuffer,
            EaLength);
    IoSetTopLevelIrp(TopLevelIrp);
    if ( v18 >= 0 )
    {
      Information = IoStatusBlock.Information;
      v19 = 0;
    }
    else
    {
      v19 = 923;
    }
    if ( v13 )
      *v13 = Information;
    v20 = FileHandle;
    *v14 = FileHandle;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_0d06f681978d342119bb40210e69c50f_Traceguids, v20, v18, v19);
    }
    if ( v2 )
      PsRevertToSelf();
    return v18;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20000) != 0 )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      16,
      WPP_0d06f681978d342119bb40210e69c50f_Traceguids,
      (unsigned int)result);
    return v24;
  }
  return result;
}

```

## disassembly

```asm
0x14000e260  push    rbx
0x14000e262  push    rbp
0x14000e263  push    rdi
0x14000e264  sub     rsp, 120h
0x14000e26b  mov     rbx, rcx
0x14000e26e  xor     dil, dil
0x14000e271  mov     rcx, [rcx+88h]; ClientContext
0x14000e278  test    rcx, rcx
0x14000e27b  jnz     loc_14000E62D
0x14000e281  mov     rcx, [rbx+78h]
0x14000e285  xor     eax, eax
0x14000e287  cmp     [rbx+50h], rax
0x14000e28b  xorps   xmm0, xmm0
0x14000e28e  mov     r8, [rbx+68h]
0x14000e292  mov     edx, [rbx+70h]
0x14000e295  mov     r9d, [rbx+60h]
0x14000e299  mov     r10d, [rbx+5Ch]
0x14000e29d  mov     r11d, [rbx+58h]
0x14000e2a1  mov     [rsp+138h+var_20], rsi
0x14000e2a9  lea     rsi, [rbx+50h]
0x14000e2ad  cmovz   rsi, rax
0x14000e2b1  mov     [rsp+138h+var_28], r12
0x14000e2b9  mov     eax, [rbx+48h]
0x14000e2bc  mov     r12d, [rbx+64h]
0x14000e2c0  mov     [rsp+138h+var_30], r13
0x14000e2c8  mov     r13, [rbx+40h]
0x14000e2cc  mov     [rsp+138h+DesiredAccess], eax
0x14000e2d3  mov     rax, [rbx+38h]
0x14000e2d7  mov     [rsp+138h+var_38], r14
0x14000e2df  mov     r14, [rbx+80h]
0x14000e2e6  mov     [rsp+138h+var_B0], rax
0x14000e2ee  xor     eax, eax
0x14000e2f0  mov     [rsp+138h+var_40], r15
0x14000e2f8  mov     r15, [rbx+28h]
0x14000e2fc  mov     [rsp+138h+var_A0], rcx
0x14000e304  mov     [rsp+138h+arg_10], edx
0x14000e30b  mov     [rsp+138h+var_98], r8
0x14000e313  mov     [rsp+138h+arg_18], r9d
0x14000e31b  mov     [rsp+138h+var_B8], r10d
0x14000e323  mov     [rsp+138h+var_B4], r11d
0x14000e32b  mov     [rsp+138h+FileHandle], 0
0x14000e337  movups  xmmword ptr [rsp+138h+ObjectAttributes.ObjectName], xmm0
0x14000e33f  movups  xmmword ptr [rsp+138h+IoStatusBlock], xmm0
0x14000e347  movups  xmmword ptr [rsp+138h+ObjectAttributes.Length], xmm0
0x14000e34f  movups  xmmword ptr [rsp+138h+ObjectAttributes+1Ch], xmm0
0x14000e357  bt      r12d, 0Dh
0x14000e35c  jnb     loc_14000E4F0
0x14000e362  mov     rbx, cs:WPP_GLOBAL_Control
0x14000e369  lea     rbp, WPP_GLOBAL_Control
0x14000e370  cmp     rbx, rbp
0x14000e373  jnz     loc_14000E561
0x14000e379  call    cs:__imp_IoGetTopLevelIrp
0x14000e380  nop     dword ptr [rax+rax+00h]
0x14000e385  xor     ecx, ecx; Irp
0x14000e387  mov     rbx, rax
0x14000e38a  call    cs:__imp_IoSetTopLevelIrp
0x14000e391  nop     dword ptr [rax+rax+00h]
0x14000e396  mov     rax, [rsp+138h+var_B0]
0x14000e39e  lea     r9, [rsp+138h+IoStatusBlock]; IoStatusBlock
0x14000e3a6  mov     edx, [rsp+138h+DesiredAccess]; DesiredAccess
0x14000e3ad  lea     r8, [rsp+138h+ObjectAttributes]; ObjectAttributes
0x14000e3b5  mov     [rsp+138h+ObjectAttributes.RootDirectory], rax
0x14000e3bd  lea     rcx, [rsp+138h+FileHandle]; FileHandle
0x14000e3c5  mov     rax, [rsp+138h+var_A0]
0x14000e3cd  mov     [rsp+138h+ObjectAttributes.SecurityDescriptor], rax
0x14000e3d5  mov     eax, [rsp+138h+arg_10]
0x14000e3dc  mov     [rsp+138h+EaLength], eax; EaLength
0x14000e3e0  mov     rax, [rsp+138h+var_98]
0x14000e3e8  mov     [rsp+138h+EaBuffer], rax; EaBuffer
0x14000e3ed  mov     eax, [rsp+138h+arg_18]
0x14000e3f4  mov     [rsp+138h+CreateOptions], r12d; CreateOptions
0x14000e3f9  mov     [rsp+138h+CreateDisposition], eax; CreateDisposition
0x14000e3fd  mov     eax, [rsp+138h+var_B8]
0x14000e404  mov     [rsp+138h+ShareAccess], eax; ShareAccess
0x14000e408  mov     eax, [rsp+138h+var_B4]
0x14000e40f  mov     [rsp+138h+ObjectAttributes.ObjectName], r13
0x14000e417  mov     r13, 0FFFFFFFFFFFFFFFFh
0x14000e41e  mov     [rsp+138h+FileAttributes], eax; FileAttributes
0x14000e422  mov     [rsp+138h+AllocationSize], rsi; AllocationSize
0x14000e427  mov     [rsp+138h+ObjectAttributes.Length], 30h ; '0'
0x14000e432  mov     [rsp+138h+ObjectAttributes.Attributes], 240h
0x14000e43d  mov     [rsp+138h+ObjectAttributes.SecurityQualityOfService], 0
0x14000e449  mov     dword ptr [rsp+138h+IoStatusBlock], r13d
0x14000e451  mov     [rsp+138h+IoStatusBlock.Information], r13
0x14000e459  call    cs:__imp_ZwCreateFile
0x14000e460  nop     dword ptr [rax+rax+00h]
0x14000e465  mov     rcx, rbx; Irp
0x14000e468  mov     esi, eax
0x14000e46a  call    cs:__imp_IoSetTopLevelIrp
0x14000e471  nop     dword ptr [rax+rax+00h]
0x14000e476  mov     r12, [rsp+138h+var_28]
0x14000e47e  test    esi, esi
0x14000e480  jns     loc_14000E68C
0x14000e486  mov     r8d, 39Bh
0x14000e48c  test    r14, r14
0x14000e48f  jnz     loc_14000E69C
0x14000e495  mov     r9, [rsp+138h+FileHandle]
0x14000e49d  mov     [r15], r9
0x14000e4a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e4a7  mov     r15, [rsp+138h+var_40]
0x14000e4af  mov     r14, [rsp+138h+var_38]
0x14000e4b7  mov     r13, [rsp+138h+var_30]
0x14000e4bf  cmp     rcx, rbp
0x14000e4c2  jz      short loc_14000E4D1
0x14000e4c4  test    dword ptr [rcx+2Ch], 40000h
0x14000e4cb  jnz     loc_14000E6A4
0x14000e4d1  test    dil, dil
0x14000e4d4  jnz     loc_14000E6C7
0x14000e4da  mov     eax, esi
0x14000e4dc  mov     rsi, [rsp+138h+var_20]
0x14000e4e4  add     rsp, 120h
0x14000e4eb  pop     rdi
0x14000e4ec  pop     rbp
0x14000e4ed  pop     rbx
0x14000e4ee  retn
0x14000e4f0  mov     rbx, cs:WPP_GLOBAL_Control
0x14000e4f7  lea     rbp, WPP_GLOBAL_Control
0x14000e4fe  cmp     rbx, rbp
0x14000e501  jz      loc_14000E379
0x14000e507  test    dword ptr [rbx+2Ch], 40000h
0x14000e50e  jz      loc_14000E379
0x14000e514  mov     [rsp+138h+var_D0], r14
0x14000e519  mov     [rsp+138h+var_D8], rcx
0x14000e51e  mov     rcx, [rbx+18h]
0x14000e522  mov     dword ptr [rsp+138h+var_E0], edx
0x14000e526  mov     edx, [rsp+138h+DesiredAccess]
0x14000e52d  mov     qword ptr [rsp+138h+EaLength], r8
0x14000e532  mov     dword ptr [rsp+138h+EaBuffer], r12d
0x14000e537  mov     [rsp+138h+CreateOptions], r9d
0x14000e53c  mov     r9, [rsp+138h+var_B0]
0x14000e544  mov     [rsp+138h+CreateDisposition], r10d
0x14000e549  mov     [rsp+138h+ShareAccess], r11d
0x14000e54e  mov     [rsp+138h+FileAttributes], edx
0x14000e552  mov     [rsp+138h+AllocationSize], r13
0x14000e557  call    WPP_SF_qZDDDDDqDqq
0x14000e55c  jmp     loc_14000E379
0x14000e561  test    dword ptr [rbx+2Ch], 40000h
0x14000e568  jz      loc_14000E379
0x14000e56e  mov     [rsp+138h+var_A8], rax
0x14000e576  mov     r8d, 8
0x14000e57c  movzx   eax, word ptr [r13+0]
0x14000e581  mov     [rsp+138h+arg_0], ax
0x14000e589  cmp     r8w, ax
0x14000e58d  jb      short loc_14000E592
0x14000e58f  mov     r8d, eax; Size
0x14000e592  mov     rdx, [r13+8]; Src
0x14000e596  lea     rcx, [rsp+138h+var_A8]; void *
0x14000e59e  call    memmove
0x14000e5a3  mov     rdx, [rsp+138h+var_A0]
0x14000e5ab  movzx   eax, [rsp+138h+arg_0]
0x14000e5b3  mov     r9, [rsp+138h+var_B0]
0x14000e5bb  mov     rcx, [rbx+18h]
0x14000e5bf  mov     [rsp+138h+var_C8], r14
0x14000e5c4  mov     [rsp+138h+var_D0], rdx
0x14000e5c9  mov     edx, [rsp+138h+arg_10]
0x14000e5d0  mov     dword ptr [rsp+138h+var_D8], edx
0x14000e5d4  mov     rdx, [rsp+138h+var_98]
0x14000e5dc  mov     [rsp+138h+var_E0], rdx
0x14000e5e1  mov     edx, [rsp+138h+arg_18]
0x14000e5e8  mov     [rsp+138h+EaLength], r12d
0x14000e5ed  mov     dword ptr [rsp+138h+EaBuffer], edx
0x14000e5f1  mov     edx, [rsp+138h+var_B8]
0x14000e5f8  mov     [rsp+138h+CreateOptions], edx
0x14000e5fc  mov     edx, [rsp+138h+var_B4]
0x14000e603  mov     [rsp+138h+CreateDisposition], edx
0x14000e607  mov     edx, [rsp+138h+DesiredAccess]
0x14000e60e  mov     [rsp+138h+ShareAccess], edx
0x14000e612  mov     [rsp+138h+FileAttributes], eax
0x14000e616  mov     rax, [rsp+138h+var_A8]
0x14000e61e  mov     [rsp+138h+AllocationSize], rax
0x14000e623  call    WPP_SF_qiDDDDDDqDqq
0x14000e628  jmp     loc_14000E379
0x14000e62d  xor     edx, edx; ServerThread
0x14000e62f  call    cs:__imp_SeImpersonateClientEx
0x14000e636  nop     dword ptr [rax+rax+00h]
0x14000e63b  mov     edi, eax
0x14000e63d  test    eax, eax
0x14000e63f  jns     short loc_14000E684
0x14000e641  mov     rcx, cs:WPP_GLOBAL_Control
0x14000e648  lea     rbp, WPP_GLOBAL_Control
0x14000e64f  cmp     rcx, rbp
0x14000e652  jz      loc_14000E4E4
0x14000e658  test    dword ptr [rcx+2Ch], 20000h
0x14000e65f  jz      loc_14000E4E4
0x14000e665  mov     rcx, [rcx+18h]
0x14000e669  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000e670  mov     edx, 10h
0x14000e675  mov     r9d, eax
0x14000e678  call    WPP_SF_d
0x14000e67d  mov     eax, edi
0x14000e67f  jmp     loc_14000E4E4
0x14000e684  mov     dil, 1
0x14000e687  jmp     loc_14000E281
0x14000e68c  mov     r13, [rsp+138h+IoStatusBlock.Information]
0x14000e694  xor     r8d, r8d
0x14000e697  jmp     loc_14000E48C
0x14000e69c  mov     [r14], r13
0x14000e69f  jmp     loc_14000E495
0x14000e6a4  mov     rcx, [rcx+18h]
0x14000e6a8  mov     edx, 0Fh
0x14000e6ad  mov     [rsp+138h+FileAttributes], r8d
0x14000e6b2  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000e6b9  mov     dword ptr [rsp+138h+AllocationSize], esi
0x14000e6bd  call    WPP_SF_qDD
0x14000e6c2  jmp     loc_14000E4D1
0x14000e6c7  call    cs:__imp_PsRevertToSelf
0x14000e6ce  nop     dword ptr [rax+rax+00h]
0x14000e6d3  jmp     loc_14000E4DA
```
