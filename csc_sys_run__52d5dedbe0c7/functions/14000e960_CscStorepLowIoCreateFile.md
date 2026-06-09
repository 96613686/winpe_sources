# CscStorepLowIoCreateFile

- ea: `0x14000e960`
- end: `0x14000eca5`
- name: `CscStorepLowIoCreateFile`
- size: `837`
- prototype: `__int64 __fastcall(void **, void *, struct _UNICODE_STRING *, ACCESS_MASK, PLARGE_INTEGER AllocationSize, ULONG FileAttributes, ULONG ShareAccess, ULONG CreateDisposition, ULONG, PVOID EaBuffer, ULONG EaLength, void *, ULONG_PTR *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1400104ec`
- `0x140054e88`

## callees

- `0x14000e960`
- `0x140018fd0`
- `0x14002a078`
- `0x14002a3e4`
- `0x14002f140`

## import_xrefs

- `ntoskrnl!ZwCreateFile` at `0x14000eaae`
- `ntoskrnl!ZwCreateFile` at `0x14000eaae`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000e9d4`
- `ntoskrnl!IoGetTopLevelIrp` at `0x14000e9d4`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000e9e5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000eabf`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000e9e5`
- `ntoskrnl!IoSetTopLevelIrp` at `0x14000eabf`

## pseudocode

```c
__int64 __fastcall CscStorepLowIoCreateFile(
        void **a1,
        void *a2,
        struct _UNICODE_STRING *a3,
        ACCESS_MASK a4,
        PLARGE_INTEGER AllocationSize,
        ULONG FileAttributes,
        ULONG ShareAccess,
        ULONG CreateDisposition,
        ULONG a9,
        PVOID EaBuffer,
        ULONG EaLength,
        void *a12,
        ULONG_PTR *a13)
{
  ULONG CreateOptions; // edi
  ULONG_PTR *v14; // r14
  PDEVICE_OBJECT v19; // rbx
  IRP *TopLevelIrp; // rbx
  ULONG_PTR Information; // rbp
  NTSTATUS v22; // edi
  int v23; // r8d
  void *v24; // r9
  unsigned int Length; // eax
  size_t v27; // r8
  int v28; // r8d
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-78h] BYREF
  void *FileHandle; // [rsp+110h] [rbp+8h] BYREF

  CreateOptions = a9;
  v14 = a13;
  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (a9 & 0x2000) != 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    {
      Length = a3->Length;
      v27 = 8;
      a13 = 0;
      LOWORD(a9) = Length;
      if ( (unsigned __int16)Length <= 8u )
        v27 = Length;
      memmove(&a13, a3->Buffer, v27);
      WPP_SF_qiDDDDDDqDqq(
        v19->AttachedDevice,
        FileAttributes,
        v28,
        (_DWORD)a2,
        (char)a13,
        a9,
        a4,
        FileAttributes,
        ShareAccess,
        CreateDisposition,
        CreateOptions,
        (char)EaBuffer,
        EaLength,
        (char)a12,
        (char)v14);
    }
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
  {
    WPP_SF_qZDDDDDqDqq(
      WPP_GLOBAL_Control->AttachedDevice,
      FileAttributes,
      (_DWORD)a3,
      (_DWORD)a2,
      (__int64)a3,
      a4,
      FileAttributes,
      ShareAccess,
      CreateDisposition,
      a9,
      (char)EaBuffer,
      EaLength,
      (char)a12,
      (char)a13);
  }
  TopLevelIrp = IoGetTopLevelIrp();
  IoSetTopLevelIrp(0);
  ObjectAttributes.SecurityDescriptor = a12;
  ObjectAttributes.ObjectName = a3;
  Information = -1;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = a2;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  IoStatusBlock.Status = -1;
  IoStatusBlock.Information = -1;
  v22 = ZwCreateFile(
          &FileHandle,
          a4,
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
  if ( v22 >= 0 )
  {
    Information = IoStatusBlock.Information;
    v23 = 0;
  }
  else
  {
    v23 = 923;
  }
  if ( v14 )
    *v14 = Information;
  v24 = FileHandle;
  *a1 = FileHandle;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_0d06f681978d342119bb40210e69c50f_Traceguids, v24, v22, v23);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x14000e960  mov     r11, rsp
0x14000e963  push    rbx
0x14000e964  push    rbp
0x14000e965  push    rsi
0x14000e966  push    rdi
0x14000e967  push    r12
0x14000e969  push    r13
0x14000e96b  push    r14
0x14000e96d  push    r15
0x14000e96f  sub     rsp, 0C8h
0x14000e976  mov     edi, [rsp+108h+arg_40]
0x14000e97d  xorps   xmm0, xmm0
0x14000e980  mov     r14, [rsp+108h+arg_60]
0x14000e988  mov     r15, rcx
0x14000e98b  xor     ecx, ecx
0x14000e98d  xor     eax, eax
0x14000e98f  mov     [r11+8], rcx
0x14000e993  mov     r12d, r9d
0x14000e996  mov     rbp, r8
0x14000e999  mov     r13, rdx
0x14000e99c  movups  xmmword ptr [r11-68h], xmm0
0x14000e9a1  movups  xmmword ptr [rsp+108h+IoStatusBlock], xmm0
0x14000e9a9  movups  xmmword ptr [r11-78h], xmm0
0x14000e9ae  movups  xmmword ptr [r11-5Ch], xmm0
0x14000e9b3  bt      edi, 0Dh
0x14000e9b7  jnb     loc_14000EB1D
0x14000e9bd  mov     rbx, cs:WPP_GLOBAL_Control
0x14000e9c4  lea     rsi, WPP_GLOBAL_Control
0x14000e9cb  cmp     rbx, rsi
0x14000e9ce  jnz     loc_14000EBAB
0x14000e9d4  call    cs:__imp_IoGetTopLevelIrp
0x14000e9db  nop     dword ptr [rax+rax+00h]
0x14000e9e0  xor     ecx, ecx; Irp
0x14000e9e2  mov     rbx, rax
0x14000e9e5  call    cs:__imp_IoSetTopLevelIrp
0x14000e9ec  nop     dword ptr [rax+rax+00h]
0x14000e9f1  mov     rax, [rsp+108h+arg_58]
0x14000e9f9  lea     r9, [rsp+108h+IoStatusBlock]; IoStatusBlock
0x14000ea01  mov     [rsp+108h+ObjectAttributes.SecurityDescriptor], rax
0x14000ea09  lea     r8, [rsp+108h+ObjectAttributes]; ObjectAttributes
0x14000ea11  mov     eax, [rsp+108h+arg_50]
0x14000ea18  lea     rcx, [rsp+108h+FileHandle]; FileHandle
0x14000ea20  mov     [rsp+108h+EaLength], eax; EaLength
0x14000ea24  mov     edx, r12d; DesiredAccess
0x14000ea27  mov     rax, [rsp+108h+arg_48]
0x14000ea2f  mov     [rsp+108h+EaBuffer], rax; EaBuffer
0x14000ea34  mov     eax, [rsp+108h+arg_38]
0x14000ea3b  mov     [rsp+108h+CreateOptions], edi; CreateOptions
0x14000ea3f  mov     [rsp+108h+CreateDisposition], eax; CreateDisposition
0x14000ea43  mov     eax, [rsp+108h+arg_30]
0x14000ea4a  mov     [rsp+108h+ShareAccess], eax; ShareAccess
0x14000ea4e  mov     eax, [rsp+108h+arg_28]
0x14000ea55  mov     [rsp+108h+FileAttributes], eax; FileAttributes
0x14000ea59  mov     rax, [rsp+108h+arg_20]
0x14000ea61  mov     [rsp+108h+ObjectAttributes.ObjectName], rbp
0x14000ea69  mov     rbp, 0FFFFFFFFFFFFFFFFh
0x14000ea70  mov     [rsp+108h+AllocationSize], rax; AllocationSize
0x14000ea75  mov     [rsp+108h+ObjectAttributes.Length], 30h ; '0'
0x14000ea80  mov     [rsp+108h+ObjectAttributes.RootDirectory], r13
0x14000ea88  mov     [rsp+108h+ObjectAttributes.Attributes], 240h
0x14000ea93  mov     [rsp+108h+ObjectAttributes.SecurityQualityOfService], 0
0x14000ea9f  mov     dword ptr [rsp+108h+IoStatusBlock], ebp
0x14000eaa6  mov     [rsp+108h+IoStatusBlock.Information], rbp
0x14000eaae  call    cs:__imp_ZwCreateFile
0x14000eab5  nop     dword ptr [rax+rax+00h]
0x14000eaba  mov     rcx, rbx; Irp
0x14000eabd  mov     edi, eax
0x14000eabf  call    cs:__imp_IoSetTopLevelIrp
0x14000eac6  nop     dword ptr [rax+rax+00h]
0x14000eacb  test    edi, edi
0x14000eacd  jns     loc_14000EC6A
0x14000ead3  mov     r8d, 39Bh
0x14000ead9  test    r14, r14
0x14000eadc  jnz     loc_14000EC7A
0x14000eae2  mov     r9, [rsp+108h+FileHandle]
0x14000eaea  mov     [r15], r9
0x14000eaed  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eaf4  cmp     rcx, rsi
0x14000eaf7  jz      short loc_14000EB06
0x14000eaf9  test    dword ptr [rcx+2Ch], 40000h
0x14000eb00  jnz     loc_14000EC82
0x14000eb06  mov     eax, edi
0x14000eb08  add     rsp, 0C8h
0x14000eb0f  pop     r15
0x14000eb11  pop     r14
0x14000eb13  pop     r13
0x14000eb15  pop     r12
0x14000eb17  pop     rdi
0x14000eb18  pop     rsi
0x14000eb19  pop     rbp
0x14000eb1a  pop     rbx
0x14000eb1b  retn
0x14000eb1d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000eb24  lea     rsi, WPP_GLOBAL_Control
0x14000eb2b  cmp     rcx, rsi
0x14000eb2e  jz      loc_14000E9D4
0x14000eb34  test    dword ptr [rcx+2Ch], 40000h
0x14000eb3b  jz      loc_14000E9D4
0x14000eb41  mov     rdx, [rsp+108h+arg_58]
0x14000eb49  mov     r9, r13
0x14000eb4c  mov     rcx, [rcx+18h]
0x14000eb50  mov     [rsp+108h+var_A0], r14
0x14000eb55  mov     [rsp+108h+var_A8], rdx
0x14000eb5a  mov     edx, [rsp+108h+arg_50]
0x14000eb61  mov     dword ptr [rsp+108h+var_B0], edx
0x14000eb65  mov     rdx, [rsp+108h+arg_48]
0x14000eb6d  mov     qword ptr [rsp+108h+EaLength], rdx
0x14000eb72  mov     edx, [rsp+108h+arg_38]
0x14000eb79  mov     dword ptr [rsp+108h+EaBuffer], edi
0x14000eb7d  mov     [rsp+108h+CreateOptions], edx
0x14000eb81  mov     edx, [rsp+108h+arg_30]
0x14000eb88  mov     [rsp+108h+CreateDisposition], edx
0x14000eb8c  mov     edx, [rsp+108h+arg_28]
0x14000eb93  mov     [rsp+108h+ShareAccess], edx
0x14000eb97  mov     [rsp+108h+FileAttributes], r12d
0x14000eb9c  mov     [rsp+108h+AllocationSize], rbp
0x14000eba1  call    WPP_SF_qZDDDDDqDqq
0x14000eba6  jmp     loc_14000E9D4
0x14000ebab  test    dword ptr [rbx+2Ch], 40000h
0x14000ebb2  jz      loc_14000E9D4
0x14000ebb8  movzx   eax, word ptr [r8]
0x14000ebbc  mov     r8d, 8
0x14000ebc2  mov     [rsp+108h+arg_60], rcx
0x14000ebca  mov     word ptr [rsp+108h+arg_40], ax
0x14000ebd2  cmp     r8w, ax
0x14000ebd6  jb      short loc_14000EBDB
0x14000ebd8  mov     r8d, eax; Size
0x14000ebdb  mov     rdx, [rbp+8]; Src
0x14000ebdf  lea     rcx, [rsp+108h+arg_60]; void *
0x14000ebe7  call    memmove
0x14000ebec  mov     rdx, [rsp+108h+arg_58]
0x14000ebf4  mov     r9, r13
0x14000ebf7  movzx   eax, word ptr [rsp+108h+arg_40]
0x14000ebff  mov     rcx, [rbx+18h]
0x14000ec03  mov     [rsp+108h+var_98], r14
0x14000ec08  mov     [rsp+108h+var_A0], rdx
0x14000ec0d  mov     edx, [rsp+108h+arg_50]
0x14000ec14  mov     dword ptr [rsp+108h+var_A8], edx
0x14000ec18  mov     rdx, [rsp+108h+arg_48]
0x14000ec20  mov     [rsp+108h+var_B0], rdx
0x14000ec25  mov     edx, [rsp+108h+arg_38]
0x14000ec2c  mov     [rsp+108h+EaLength], edi
0x14000ec30  mov     dword ptr [rsp+108h+EaBuffer], edx
0x14000ec34  mov     edx, [rsp+108h+arg_30]
0x14000ec3b  mov     [rsp+108h+CreateOptions], edx
0x14000ec3f  mov     edx, [rsp+108h+arg_28]
0x14000ec46  mov     [rsp+108h+CreateDisposition], edx
0x14000ec4a  mov     [rsp+108h+ShareAccess], r12d
0x14000ec4f  mov     [rsp+108h+FileAttributes], eax
0x14000ec53  mov     rax, [rsp+108h+arg_60]
0x14000ec5b  mov     [rsp+108h+AllocationSize], rax
0x14000ec60  call    WPP_SF_qiDDDDDDqDqq
0x14000ec65  jmp     loc_14000E9D4
0x14000ec6a  mov     rbp, [rsp+108h+IoStatusBlock.Information]
0x14000ec72  xor     r8d, r8d
0x14000ec75  jmp     loc_14000EAD9
0x14000ec7a  mov     [r14], rbp
0x14000ec7d  jmp     loc_14000EAE2
0x14000ec82  mov     rcx, [rcx+18h]
0x14000ec86  mov     edx, 0Fh
0x14000ec8b  mov     [rsp+108h+FileAttributes], r8d
0x14000ec90  lea     r8, WPP_0d06f681978d342119bb40210e69c50f_Traceguids
0x14000ec97  mov     dword ptr [rsp+108h+AllocationSize], edi
0x14000ec9b  call    WPP_SF_qDD
0x14000eca0  jmp     loc_14000EB06
```
