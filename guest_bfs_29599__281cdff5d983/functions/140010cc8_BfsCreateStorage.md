# BfsCreateStorage

- ea: `0x140010cc8`
- end: `0x14001118d`
- name: `BfsCreateStorage`
- size: `1221`
- prototype: ``
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x140007fec`
- `0x140008728`
- `0x14000ceb4`

## callees

- `0x140001008`
- `0x140010754`
- `0x140010cc8`
- `0x1400123fc`
- `0x1400125a8`
- `0x140012c40`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x140010e11`
- `ntoskrnl!ExInitializePushLock` at `0x140010f0d`
- `ntoskrnl!ExInitializePushLock` at `0x14001101a`
- `ntoskrnl!ExInitializePushLock` at `0x140010e11`
- `ntoskrnl!ExInitializePushLock` at `0x140010f0d`
- `ntoskrnl!ExInitializePushLock` at `0x14001101a`
- `ntoskrnl!ZwQueryInformationFile` at `0x140010e61`
- `ntoskrnl!ZwQueryInformationFile` at `0x140010e61`
- `ntoskrnl!RtlInitializeBitMap` at `0x140010eeb`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001100a`
- `ntoskrnl!RtlInitializeBitMap` at `0x140010eeb`
- `ntoskrnl!RtlInitializeBitMap` at `0x14001100a`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010f37`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140011044`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010f37`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140011044`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011162`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001117c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010f54`
- `ntoskrnl!ExFreePoolWithTag` at `0x140011162`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001117c`
- `ntoskrnl!ExAllocatePool2` at `0x140010dc8`
- `ntoskrnl!ExAllocatePool2` at `0x140010ea0`
- `ntoskrnl!ExAllocatePool2` at `0x140010f9d`
- `ntoskrnl!ExAllocatePool2` at `0x1400110a6`
- `ntoskrnl!ExAllocatePool2` at `0x140010dc8`
- `ntoskrnl!ExAllocatePool2` at `0x140010ea0`
- `ntoskrnl!ExAllocatePool2` at `0x140010f9d`
- `ntoskrnl!ExAllocatePool2` at `0x1400110a6`
- `FLTMGR!FltClose` at `0x14001114c`
- `FLTMGR!FltClose` at `0x14001114c`
- `FLTMGR!FltCreateFileEx2` at `0x140010d91`
- `FLTMGR!FltCreateFileEx2` at `0x140010d91`

## pseudocode

```c
__int64 __fastcall BfsCreateStorage(
        struct _FLT_FILTER *a1,
        struct _FLT_INSTANCE *a2,
        void *a3,
        struct _UNICODE_STRING *a4,
        unsigned __int64 **a5)
{
  _DWORD *v5; // rsi
  _DWORD *v6; // r15
  __int64 v7; // rcx
  NTSTATUS Block; // ebx
  __int64 v9; // r8
  __int64 v10; // r9
  unsigned __int64 *v11; // rdi
  unsigned __int64 *Pool2; // rax
  struct _EVENT_DATA_DESCRIPTOR *p_FileInformation; // rax
  ULONG_PTR Information; // rax
  __int64 v15; // rax
  bool v16; // cc
  _DWORD *v18; // rax
  unsigned int v19; // eax
  unsigned int v20; // r13d
  __int64 v21; // rax
  __int64 v22; // rdx
  int DesiredAccess; // [rsp+20h] [rbp-E0h]
  int v24; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v25; // [rsp+84h] [rbp-7Ch] BYREF
  void *FileHandle; // [rsp+88h] [rbp-78h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 **v28; // [rsp+A0h] [rbp-60h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK v30; // [rsp+D8h] [rbp-28h] BYREF
  char v31; // [rsp+E8h] [rbp-18h] BYREF
  int *v32; // [rsp+108h] [rbp+8h]
  __int64 v33; // [rsp+110h] [rbp+10h]
  __int128 FileInformation; // [rsp+118h] [rbp+18h] BYREF
  __int64 v35; // [rsp+128h] [rbp+28h]
  int *v36; // [rsp+138h] [rbp+38h]
  __int64 v37; // [rsp+140h] [rbp+40h]

  v28 = a5;
  v5 = 0;
  v6 = 0;
  *a5 = 0;
  ObjectAttributes.SecurityDescriptor = gBfsPolicyStorageFileDescriptor;
  ObjectAttributes.RootDirectory = a3;
  ObjectAttributes.ObjectName = a4;
  IoStatusBlock = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 576;
  FileHandle = 0;
  ObjectAttributes.SecurityQualityOfService = 0;
  Block = FltCreateFileEx2(
            a1,
            a2,
            &FileHandle,
            0,
            0xC0110000,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x80u,
            0,
            3u,
            0x860u,
            0,
            0,
            0x100u,
            0);
  if ( Block < 0 )
  {
    v11 = 0;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v24 = Block;
LABEL_7:
      v37 = 4;
      v36 = &v24;
      p_FileInformation = (struct _EVENT_DATA_DESCRIPTOR *)&FileInformation;
LABEL_37:
      tlgWriteTransfer_EtwWriteTransfer(
        v7,
        (unsigned __int8 *)&byte_140016D91,
        v9,
        v10,
        DesiredAccess,
        p_FileInformation);
      goto LABEL_38;
    }
    goto LABEL_38;
  }
  Pool2 = (unsigned __int64 *)ExAllocatePool2(256, 200, 1936942658);
  v11 = Pool2;
  if ( Pool2 )
  {
    ExInitializePushLock(Pool2);
    v11[1] = (unsigned __int64)FileHandle;
    if ( IoStatusBlock.Information == 2 )
      goto LABEL_22;
    v30 = 0;
    v35 = 0;
    FileInformation = 0;
    Block = ZwQueryInformationFile(FileHandle, &v30, &FileInformation, 0x18u, FileStandardInformation);
    if ( Block < 0 )
      goto LABEL_34;
    Information = IoStatusBlock.Information;
    if ( !*((_QWORD *)&FileInformation + 1) )
      Information = 2;
    IoStatusBlock.Information = Information;
    if ( Information == 2 )
    {
LABEL_22:
      v25 = 0;
      v24 = 0;
      v18 = (_DWORD *)ExAllocatePool2(256, 0x4000, 1668507202);
      v5 = v18;
      if ( !v18 )
        goto LABEL_23;
      memset(v18, 0, 0x4000u);
      v19 = v5[1] & 0xFF000001;
      *v5 = 1131636290;
      v5[2] = 0x4000;
      v5[1] = v19 | 1;
      *((_BYTE *)v5 + 7) = 0;
      v11[2] = (unsigned __int64)v5;
      RtlInitializeBitMap((PRTL_BITMAP)(v11 + 3), v5 + 6, 0x1FF40u);
      ExInitializePushLock(v11 + 9);
      RtlInitializeGenericTableAvl(
        (PRTL_AVL_TABLE)(v11 + 10),
        BfsCompareTableEntries,
        BfsAllocateTableEntry,
        BfsFreeTableEntry,
        0);
      Block = BfsAllocateBlock(v11, &v25);
      if ( Block < 0 )
        goto LABEL_34;
      if ( v25 )
      {
        Block = -1073741774;
        goto LABEL_34;
      }
      Block = BfsAllocateBlock(v11, &v24);
      if ( Block < 0 )
        goto LABEL_34;
      v20 = v24;
      *(_DWORD *)(v11[2] + 12) = v24;
      v21 = ExAllocatePool2(256, 0x4000, 1651729986);
      v6 = (_DWORD *)v21;
      if ( !v21 )
      {
LABEL_23:
        v16 = (unsigned int)dword_140019000 <= 3;
        goto LABEL_24;
      }
      memset((void *)(v21 + 4), 0, 0x3FFCu);
      v22 = v25;
      *v6 = 1148413506;
      Block = BfsWriteBlock(v11, v22, v5);
      if ( Block >= 0 )
      {
        Block = BfsWriteBlock(v11, v20, v6);
        if ( Block >= 0 )
        {
          Block = BfsOpenRootDirectory(v11);
          if ( Block >= 0 )
            goto LABEL_18;
        }
      }
    }
    else
    {
      v15 = ExAllocatePool2(256, 0x4000, 1668507202);
      v5 = (_DWORD *)v15;
      if ( !v15 )
      {
        v7 = (unsigned int)dword_140019000;
        v16 = (unsigned int)dword_140019000 <= 3;
LABEL_24:
        Block = -1073741801;
        if ( v16 )
          goto LABEL_38;
        v24 = -1073741801;
LABEL_36:
        v33 = 4;
        v32 = &v24;
        p_FileInformation = (struct _EVENT_DATA_DESCRIPTOR *)&v31;
        goto LABEL_37;
      }
      Block = BfsReadBlock(v11, 0, v15);
      if ( Block >= 0 )
      {
        v11[2] = (unsigned __int64)v5;
        RtlInitializeBitMap((PRTL_BITMAP)(v11 + 3), v5 + 6, 0x1FF40u);
        Block = BfsOpenRootDirectory(v11);
        if ( Block >= 0 )
        {
          ExInitializePushLock(v11 + 9);
          RtlInitializeGenericTableAvl(
            (PRTL_AVL_TABLE)(v11 + 10),
            BfsCompareTableEntries,
            BfsAllocateTableEntry,
            BfsFreeTableEntry,
            0);
LABEL_18:
          *v28 = v11;
          goto LABEL_19;
        }
      }
    }
LABEL_34:
    if ( (unsigned int)dword_140019000 <= 3 )
      goto LABEL_38;
    v24 = Block;
    goto LABEL_36;
  }
  Block = -1073741801;
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v24 = -1073741801;
    goto LABEL_7;
  }
LABEL_38:
  if ( FileHandle )
    FltClose(FileHandle);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  if ( v5 )
    ExFreePoolWithTag(v5, 0);
LABEL_19:
  if ( v6 )
    ExFreePoolWithTag(v6, 0);
  return (unsigned int)Block;
}

```

## disassembly

```asm
0x140010cc8  push    rbp
0x140010cca  push    rbx
0x140010ccb  push    rsi
0x140010ccc  push    rdi
0x140010ccd  push    r13
0x140010ccf  push    r14
0x140010cd1  push    r15
0x140010cd3  lea     rbp, [rsp-50h]
0x140010cd8  sub     rsp, 150h
0x140010cdf  mov     rax, cs:__security_cookie
0x140010ce6  xor     rax, rsp
0x140010ce9  mov     [rbp+80h+var_38], rax
0x140010ced  mov     rax, [rbp+80h+arg_20]
0x140010cf4  xor     r13d, r13d
0x140010cf7  mov     [rsp+180h+DriverContext], r13; DriverContext
0x140010cfc  xorps   xmm0, xmm0
0x140010cff  mov     [rbp+80h+var_E0], rax
0x140010d03  mov     edi, 100h
0x140010d08  mov     [rsp+180h+Flags], edi; Flags
0x140010d0c  mov     esi, r13d
0x140010d0f  mov     [rsp+180h+EaLength], r13d; EaLength
0x140010d14  mov     r15d, r13d
0x140010d17  mov     [rsp+180h+EaBuffer], r13; EaBuffer
0x140010d1c  mov     [rsp+180h+CreateOptions], 860h; CreateOptions
0x140010d24  mov     [rsp+180h+CreateDisposition], 3; CreateDisposition
0x140010d2c  mov     [rsp+180h+ShareAccess], r13d; ShareAccess
0x140010d31  mov     [rax], r13
0x140010d34  lea     rax, gBfsPolicyStorageFileDescriptor
0x140010d3b  mov     [rsp+180h+FileAttributes], 80h; FileAttributes
0x140010d43  mov     [rbp+80h+var_D8.SecurityDescriptor], rax
0x140010d47  lea     rax, [rbp+80h+var_F0]
0x140010d4b  mov     [rsp+180h+AllocationSize], r13; AllocationSize
0x140010d50  mov     [rsp+180h+IoStatusBlock], rax; IoStatusBlock
0x140010d55  lea     rax, [rbp+80h+var_D8]
0x140010d59  mov     [rbp+80h+var_D8.RootDirectory], r8
0x140010d5d  lea     r8, [rbp+80h+FileHandle]; FileHandle
0x140010d61  mov     [rbp+80h+var_D8.ObjectName], r9
0x140010d65  xor     r9d, r9d; FileObject
0x140010d68  mov     [rsp+180h+ObjectAttributes], rax; ObjectAttributes
0x140010d6d  mov     [rsp+180h+DesiredAccess], 0C0110000h; DesiredAccess
0x140010d75  movups  xmmword ptr [rbp+80h+var_F0], xmm0
0x140010d79  mov     qword ptr [rbp+80h+var_D8.Length], 30h ; '0'
0x140010d81  mov     qword ptr [rbp+80h+var_D8.Attributes], 240h
0x140010d89  mov     [rbp+80h+FileHandle], r13
0x140010d8d  mov     [rbp+80h+var_D8.SecurityQualityOfService], r13
0x140010d91  call    cs:__imp_FltCreateFileEx2
0x140010d98  nop     dword ptr [rax+rax+00h]
0x140010d9d  mov     ebx, eax
0x140010d9f  test    eax, eax
0x140010da1  jns     short loc_140010DBA
0x140010da3  mov     eax, cs:dword_140019000
0x140010da9  mov     edi, r13d
0x140010dac  cmp     eax, 3
0x140010daf  jbe     loc_140011143
0x140010db5  mov     [rbp+80h+var_100], ebx
0x140010db8  jmp     short loc_140010DF5
0x140010dba  mov     edx, 0C8h
0x140010dbf  mov     r8d, 73736642h
0x140010dc5  mov     rcx, rdi
0x140010dc8  call    cs:__imp_ExAllocatePool2
0x140010dcf  nop     dword ptr [rax+rax+00h]
0x140010dd4  mov     rdi, rax
0x140010dd7  test    rax, rax
0x140010dda  jnz     short loc_140010E0E
0x140010ddc  mov     eax, cs:dword_140019000
0x140010de2  mov     edx, 0C0000017h
0x140010de7  mov     ebx, edx
0x140010de9  cmp     eax, 3
0x140010dec  jbe     loc_140011143
0x140010df2  mov     [rbp+80h+var_100], edx
0x140010df5  lea     rax, [rbp+80h+var_100]
0x140010df9  mov     [rbp+80h+var_40], 4
0x140010e01  mov     [rbp+80h+var_48], rax
0x140010e05  lea     rax, [rbp+80h+FileInformation]
0x140010e09  jmp     loc_140011132
0x140010e0e  mov     rcx, rdi; PushLock
0x140010e11  call    cs:__imp_ExInitializePushLock
0x140010e18  nop     dword ptr [rax+rax+00h]
0x140010e1d  mov     rax, [rbp+80h+FileHandle]
0x140010e21  mov     r14d, 2
0x140010e27  mov     [rdi+8], rax
0x140010e2b  cmp     [rbp+80h+var_F0.Information], r14
0x140010e2f  jz      loc_140010F81
0x140010e35  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140010e39  lea     r9d, [r14+16h]; Length
0x140010e3d  xorps   xmm0, xmm0
0x140010e40  mov     [rsp+180h+DesiredAccess], 5; FileInformationClass
0x140010e48  xorps   xmm1, xmm1
0x140010e4b  lea     r8, [rbp+80h+FileInformation]; FileInformation
0x140010e4f  xor     eax, eax
0x140010e51  lea     rdx, [rbp+80h+var_A8]; IoStatusBlock
0x140010e55  movups  xmmword ptr [rbp+80h+var_A8], xmm0
0x140010e59  mov     [rbp+80h+var_58], rax
0x140010e5d  movups  [rbp+80h+FileInformation], xmm1
0x140010e61  call    cs:__imp_ZwQueryInformationFile
0x140010e68  nop     dword ptr [rax+rax+00h]
0x140010e6d  mov     ebx, eax
0x140010e6f  test    eax, eax
0x140010e71  js      loc_140011110
0x140010e77  cmp     qword ptr [rbp+80h+FileInformation+8], r13
0x140010e7b  mov     rax, [rbp+80h+var_F0.Information]
0x140010e7f  cmovz   rax, r14
0x140010e83  mov     [rbp+80h+var_F0.Information], rax
0x140010e87  cmp     rax, r14
0x140010e8a  jz      loc_140010F81
0x140010e90  mov     edx, 4000h
0x140010e95  mov     ecx, 100h
0x140010e9a  mov     r8d, 63736642h
0x140010ea0  call    cs:__imp_ExAllocatePool2
0x140010ea7  nop     dword ptr [rax+rax+00h]
0x140010eac  mov     rsi, rax
0x140010eaf  test    rax, rax
0x140010eb2  jnz     short loc_140010EC2
0x140010eb4  mov     ecx, cs:dword_140019000
0x140010eba  cmp     ecx, 3
0x140010ebd  jmp     loc_140010FBA
0x140010ec2  mov     r8, rsi
0x140010ec5  xor     edx, edx
0x140010ec7  mov     rcx, rdi
0x140010eca  call    BfsReadBlock
0x140010ecf  mov     ebx, eax
0x140010ed1  test    eax, eax
0x140010ed3  js      loc_140011110
0x140010ed9  lea     rdx, [rsi+18h]; BitMapBuffer
0x140010edd  mov     [rdi+10h], rsi
0x140010ee1  lea     rcx, [rdi+18h]; BitMapHeader
0x140010ee5  mov     r8d, 1FF40h; SizeOfBitMap
0x140010eeb  call    cs:__imp_RtlInitializeBitMap
0x140010ef2  nop     dword ptr [rax+rax+00h]
0x140010ef7  mov     rcx, rdi
0x140010efa  call    BfsOpenRootDirectory
0x140010eff  mov     ebx, eax
0x140010f01  test    eax, eax
0x140010f03  js      loc_140011110
0x140010f09  lea     rcx, [rdi+48h]; PushLock
0x140010f0d  call    cs:__imp_ExInitializePushLock
0x140010f14  nop     dword ptr [rax+rax+00h]
0x140010f19  lea     rcx, [rdi+50h]; Table
0x140010f1d  mov     qword ptr [rsp+180h+DesiredAccess], r13; TableContext
0x140010f22  lea     r9, BfsFreeTableEntry; FreeRoutine
0x140010f29  lea     r8, BfsAllocateTableEntry; AllocateRoutine
0x140010f30  lea     rdx, BfsCompareTableEntries; CompareRoutine
0x140010f37  call    cs:__imp_RtlInitializeGenericTableAvl
0x140010f3e  nop     dword ptr [rax+rax+00h]
0x140010f43  mov     rax, [rbp+80h+var_E0]
0x140010f47  mov     [rax], rdi
0x140010f4a  test    r15, r15
0x140010f4d  jz      short loc_140010F60
0x140010f4f  xor     edx, edx; Tag
0x140010f51  mov     rcx, r15; P
0x140010f54  call    cs:__imp_ExFreePoolWithTag
0x140010f5b  nop     dword ptr [rax+rax+00h]
0x140010f60  mov     eax, ebx
0x140010f62  mov     rcx, [rbp+80h+var_38]
0x140010f66  xor     rcx, rsp; StackCookie
0x140010f69  call    __security_check_cookie
0x140010f6e  add     rsp, 150h
0x140010f75  pop     r15
0x140010f77  pop     r14
0x140010f79  pop     r13
0x140010f7b  pop     rdi
0x140010f7c  pop     rsi
0x140010f7d  pop     rbx
0x140010f7e  pop     rbp
0x140010f7f  retn
0x140010f81  mov     r14d, 4000h
0x140010f87  mov     [rbp+80h+var_FC], r13d
0x140010f8b  mov     edx, r14d
0x140010f8e  mov     [rbp+80h+var_100], r13d
0x140010f92  mov     r8d, 63736642h
0x140010f98  mov     ecx, 100h
0x140010f9d  call    cs:__imp_ExAllocatePool2
0x140010fa4  nop     dword ptr [rax+rax+00h]
0x140010fa9  mov     rsi, rax
0x140010fac  test    rax, rax
0x140010faf  jnz     short loc_140010FCF
0x140010fb1  mov     eax, cs:dword_140019000
0x140010fb7  cmp     eax, 3
0x140010fba  mov     edx, 0C0000017h
0x140010fbf  mov     ebx, edx
0x140010fc1  jbe     loc_140011143
0x140010fc7  mov     [rbp+80h+var_100], edx
0x140010fca  jmp     loc_14001111E
0x140010fcf  mov     r8, r14; Size
0x140010fd2  xor     edx, edx; Val
0x140010fd4  mov     rcx, rsi; void *
0x140010fd7  call    memset
0x140010fdc  mov     eax, [rsi+4]
0x140010fdf  lea     rdx, [rsi+18h]; BitMapBuffer
0x140010fe3  and     eax, 0FF000001h
0x140010fe8  mov     dword ptr [rsi], 43736642h
0x140010fee  or      eax, 1
0x140010ff1  mov     [rsi+8], r14d
0x140010ff5  mov     [rsi+4], eax
0x140010ff8  lea     rcx, [rdi+18h]; BitMapHeader
0x140010ffc  mov     [rsi+7], r13b
0x140011000  mov     r8d, 1FF40h; SizeOfBitMap
0x140011006  mov     [rdi+10h], rsi
0x14001100a  call    cs:__imp_RtlInitializeBitMap
0x140011011  nop     dword ptr [rax+rax+00h]
0x140011016  lea     rcx, [rdi+48h]; PushLock
0x14001101a  call    cs:__imp_ExInitializePushLock
0x140011021  nop     dword ptr [rax+rax+00h]
0x140011026  lea     rcx, [rdi+50h]; Table
0x14001102a  mov     qword ptr [rsp+180h+DesiredAccess], r13; int
0x14001102f  lea     r9, BfsFreeTableEntry; FreeRoutine
0x140011036  lea     r8, BfsAllocateTableEntry; AllocateRoutine
0x14001103d  lea     rdx, BfsCompareTableEntries; CompareRoutine
0x140011044  call    cs:__imp_RtlInitializeGenericTableAvl
0x14001104b  nop     dword ptr [rax+rax+00h]
0x140011050  lea     rdx, [rbp+80h+var_FC]
0x140011054  mov     rcx, rdi
0x140011057  call    BfsAllocateBlock
0x14001105c  mov     ebx, eax
0x14001105e  test    eax, eax
0x140011060  js      loc_140011110
0x140011066  cmp     [rbp+80h+var_FC], r13d
0x14001106a  jz      short loc_140011076
0x14001106c  mov     ebx, 0C0000032h
0x140011071  jmp     loc_140011110
0x140011076  lea     rdx, [rbp+80h+var_100]
0x14001107a  mov     rcx, rdi
0x14001107d  call    BfsAllocateBlock
0x140011082  mov     ebx, eax
0x140011084  test    eax, eax
0x140011086  js      loc_140011110
0x14001108c  mov     rax, [rdi+10h]
0x140011090  mov     r8d, 62736642h
0x140011096  mov     r13d, [rbp+80h+var_100]
0x14001109a  mov     rdx, r14
0x14001109d  mov     ecx, 100h
0x1400110a2  mov     [rax+0Ch], r13d
0x1400110a6  call    cs:__imp_ExAllocatePool2
0x1400110ad  nop     dword ptr [rax+rax+00h]
0x1400110b2  mov     r15, rax
0x1400110b5  test    rax, rax
0x1400110b8  jz      loc_140010FB1
0x1400110be  lea     rcx, [rax+4]; void *
0x1400110c2  xor     edx, edx; Val
0x1400110c4  mov     r8d, 3FFCh; Size
0x1400110ca  call    memset
0x1400110cf  mov     edx, [rbp+80h+var_FC]
0x1400110d2  mov     r8, rsi
0x1400110d5  mov     rcx, rdi
0x1400110d8  mov     dword ptr [r15], 44736642h
0x1400110df  call    BfsWriteBlock
0x1400110e4  mov     ebx, eax
0x1400110e6  test    eax, eax
0x1400110e8  js      short loc_140011110
0x1400110ea  mov     r8, r15
0x1400110ed  mov     edx, r13d
0x1400110f0  mov     rcx, rdi
0x1400110f3  call    BfsWriteBlock
0x1400110f8  mov     ebx, eax
0x1400110fa  test    eax, eax
0x1400110fc  js      short loc_140011110
0x1400110fe  mov     rcx, rdi
0x140011101  call    BfsOpenRootDirectory
0x140011106  mov     ebx, eax
0x140011108  test    eax, eax
0x14001110a  jns     loc_140010F43
0x140011110  mov     eax, cs:dword_140019000
0x140011116  cmp     eax, 3
0x140011119  jbe     short loc_140011143
0x14001111b  mov     [rbp+80h+var_100], ebx
0x14001111e  lea     rax, [rbp+80h+var_100]
0x140011122  mov     [rbp+80h+var_70], 4
0x14001112a  mov     [rbp+80h+var_78], rax
0x14001112e  lea     rax, [rbp+80h+var_98]
0x140011132  lea     rdx, byte_140016D91; int
0x140011139  mov     [rsp+180h+ObjectAttributes], rax; PEVENT_DATA_DESCRIPTOR
0x14001113e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140011143  mov     rcx, [rbp+80h+FileHandle]; FileHandle
0x140011147  test    rcx, rcx
0x14001114a  jz      short loc_140011158
0x14001114c  call    cs:__imp_FltClose
0x140011153  nop     dword ptr [rax+rax+00h]
0x140011158  test    rdi, rdi
0x14001115b  jz      short loc_14001116E
0x14001115d  xor     edx, edx; Tag
0x14001115f  mov     rcx, rdi; P
0x140011162  call    cs:__imp_ExFreePoolWithTag
0x140011169  nop     dword ptr [rax+rax+00h]
0x14001116e  test    rsi, rsi
0x140011171  jz      loc_140010F4A
0x140011177  xor     edx, edx; Tag
0x140011179  mov     rcx, rsi; P
0x14001117c  call    cs:__imp_ExFreePoolWithTag
0x140011183  nop     dword ptr [rax+rax+00h]
0x140011188  jmp     loc_140010F4A
```
