# OnlineMountedVolumes

- ea: `0x14000f680`
- end: `0x14000fcb9`
- name: `OnlineMountedVolumes`
- size: `1593`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140019140`

## callees

- `0x140001730`
- `0x140001ae0`
- `0x140001b30`
- `0x140002d70`
- `0x140002f80`
- `0x14000f680`
- `0x140010600`
- `0x140010970`
- `0x140012df0`
- `0x140012e60`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x14000f7e5`
- `ntoskrnl!KeReleaseMutex` at `0x14000f8f8`
- `ntoskrnl!KeReleaseMutex` at `0x14000fa75`
- `ntoskrnl!KeReleaseMutex` at `0x14000f7e5`
- `ntoskrnl!KeReleaseMutex` at `0x14000f8f8`
- `ntoskrnl!KeReleaseMutex` at `0x14000fa75`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000f945`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000facd`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000f945`
- `ntoskrnl!ZwQueryDirectoryFile` at `0x14000facd`
- `ntoskrnl!ExAllocatePool2` at `0x14000f717`
- `ntoskrnl!ExAllocatePool2` at `0x14000fa0c`
- `ntoskrnl!ExAllocatePool2` at `0x14000f717`
- `ntoskrnl!ExAllocatePool2` at `0x14000fa0c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f829`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fbbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc78`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000f829`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fbbe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000fc78`
- `ntoskrnl!ZwOpenFile` at `0x14000f813`
- `ntoskrnl!ZwOpenFile` at `0x14000f813`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f845`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f964`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000faf1`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f845`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000f964`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000faf1`

## pseudocode

```c
__int64 __fastcall OnlineMountedVolumes(__int64 a1, __int64 a2)
{
  __int16 v4; // ax
  __int64 result; // rax
  PDEVICE_OBJECT v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // rbx
  __int64 v9; // rdi
  NTSTATUS v10; // r12d
  __int64 v11; // r8
  unsigned int v12; // r14d
  PDEVICE_OBJECT v13; // rcx
  __int64 v14; // rdx
  NTSTATUS v15; // r12d
  __int64 v16; // r8
  BOOLEAN RestartScan; // r14
  __int64 v18; // r13
  NTSTATUS v19; // r12d
  int v20; // eax
  __int64 v21; // r8
  __int64 v22; // r9
  int VolumeName; // eax
  __int64 v24; // r8
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // r9
  __int64 v28; // r8
  int DeviceInfo; // r12d
  PDEVICE_OBJECT v30; // rcx
  __int64 v31; // rdx
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  PVOID P[2]; // [rsp+68h] [rbp-98h] BYREF
  int v34; // [rsp+78h] [rbp-88h]
  PVOID v35[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v36; // [rsp+90h] [rbp-70h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING FileName; // [rsp+A8h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+B8h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C8h] [rbp-38h] BYREF
  PVOID v42[2]; // [rsp+F8h] [rbp-8h] BYREF
  __int128 FileInformation; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v44[2]; // [rsp+118h] [rbp+18h] BYREF

  memset(v44, 0, 12);
  v4 = *(_WORD *)(a2 + 80) + word_140007000;
  HIWORD(P[0]) = 0;
  LOWORD(P[0]) = v4;
  v38 = 0;
  *(_DWORD *)((char *)P + 2) = (unsigned __int16)(v4 + 2);
  FileHandle = 0;
  *(_OWORD *)v42 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  *(_OWORD *)v35 = 0;
  FileName = 0;
  result = ExAllocatePool2(258, (unsigned __int16)(v4 + 2), 1098149453);
  P[1] = (PVOID)result;
  if ( !result )
  {
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return result;
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) == 0 )
      return result;
    v7 = 153;
    return WPP_SF_(v6->AttachedDevice, v7);
  }
  memmove((void *)result, *(const void **)(a2 + 88), *(unsigned __int16 *)(a2 + 80));
  memmove((char *)P[1] + *(unsigned __int16 *)(a2 + 80), off_140007008, (unsigned __int16)word_140007000);
  *((_WORD *)P[1] + ((unsigned __int64)LOWORD(P[0]) >> 1)) = 0;
  v8 = *(_QWORD *)(a1 + 336);
  v9 = *(_QWORD *)(a2 + 176);
  ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
  v37 = v8;
  v36 = v9;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  KeReleaseMutex((PRKMUTEX)(a1 + 56), 0);
  v10 = ZwOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  ExFreePoolWithTag(P[1], 0);
  KeWaitForSingleObject((PVOID)(a1 + 56), Executive, 0, 0, 0);
  result = VerifyEpoch(a1, v8, v9);
  v12 = result;
  if ( (int)result < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      result = HIDWORD(WPP_GLOBAL_Control->Timer);
      if ( (result & 1) != 0 )
        result = WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 154, v11, v12);
    }
    goto LABEL_12;
  }
  if ( v10 < 0 )
  {
    v12 = v10;
LABEL_12:
    *(_BYTE *)(a2 + 132) = 0;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return result;
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) == 0 )
      return result;
    v14 = 155;
    return WPP_SF_L(v13->AttachedDevice, v14, v11, v12);
  }
  *(_QWORD *)((char *)v44 + 4) = 0;
  FileName.Buffer = (PWSTR)v44;
  LODWORD(v44[0]) = -1610612733;
  *(_DWORD *)&FileName.Length = 786444;
  KeReleaseMutex((PRKMUTEX)(a1 + 56), 0);
  v15 = ZwQueryDirectoryFile(
          FileHandle,
          0,
          0,
          0,
          &IoStatusBlock,
          &FileInformation,
          0x10u,
          FileReparsePointInformation,
          1u,
          &FileName,
          0);
  KeWaitForSingleObject((PVOID)(a1 + 56), Executive, 0, 0, 0);
  v12 = VerifyEpoch(a1, v37, v36);
  if ( (v12 & 0x80000000) != 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 156, v16, v12);
    goto LABEL_22;
  }
  if ( v15 < 0 )
  {
    v12 = v15;
LABEL_22:
    result = CloseFileHandleOutsideExtensionMutexLock(a1);
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return result;
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 1) == 0 || !BYTE1(WPP_GLOBAL_Control->Timer) )
      return result;
    v14 = 157;
    return WPP_SF_L(v13->AttachedDevice, v14, v11, v12);
  }
  LODWORD(v35[0]) = 13107200;
  v35[1] = (PVOID)ExAllocatePool2(258, 200, 1098149453);
  if ( !v35[1] )
  {
    result = CloseFileHandleOutsideExtensionMutexLock(a1);
    v6 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return result;
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 4) == 0 )
      return result;
    v7 = 158;
    return WPP_SF_(v6->AttachedDevice, v7);
  }
  RestartScan = 1;
  while ( 1 )
  {
    v18 = FileInformation;
    v34 = DWORD2(FileInformation);
    KeReleaseMutex((PRKMUTEX)(a1 + 56), 0);
    v19 = ZwQueryDirectoryFile(
            FileHandle,
            0,
            0,
            0,
            &IoStatusBlock,
            &FileInformation,
            0x10u,
            FileReparsePointInformation,
            1u,
            (PUNICODE_STRING)((unsigned __int64)&FileName & -(__int64)(RestartScan != 0)),
            RestartScan);
    KeWaitForSingleObject((PVOID)(a1 + 56), Executive, 0, 0, 0);
    v20 = VerifyEpoch(a1, v37, v36);
    v22 = (unsigned int)v20;
    if ( v20 < 0 )
      break;
    if ( RestartScan )
    {
      RestartScan = 0;
    }
    else if ( v18 == (_QWORD)FileInformation && v34 == DWORD2(FileInformation) )
    {
      goto LABEL_59;
    }
    if ( v19 < 0 )
    {
      v30 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        v31 = 160;
        v22 = (unsigned int)v19;
LABEL_58:
        WPP_SF_L(v30->AttachedDevice, v31, v21, v22);
        goto LABEL_59;
      }
      goto LABEL_59;
    }
    if ( DWORD2(FileInformation) != -1610612733 )
      goto LABEL_59;
    VolumeName = QueryVolumeName(
                   a1,
                   a2,
                   FileHandle,
                   (__int64)&FileInformation,
                   0,
                   (unsigned __int16 *)v35,
                   (unsigned __int16 *)v42);
    if ( VolumeName >= 0 )
    {
      ExFreePoolWithTag(v42[1], 0);
      DeviceInfo = FindDeviceInfo(a1, v35, v28, &v38);
      if ( DeviceInfo < 0 )
      {
        *(_BYTE *)(a2 + 132) = 1;
      }
      else
      {
        if ( !*(_BYTE *)(v38 + 133) )
          PostOnlineNotification(a1, v38 + 64);
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          v26 = 162;
          v27 = (unsigned int)DeviceInfo;
LABEL_43:
          WPP_SF_L(v25->AttachedDevice, v26, v24, v27);
        }
      }
    }
    else
    {
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v26 = 161;
        v27 = (unsigned int)VolumeName;
        goto LABEL_43;
      }
    }
  }
  v30 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
  {
    v31 = 159;
    goto LABEL_58;
  }
LABEL_59:
  ExFreePoolWithTag(v35[1], 0);
  return CloseFileHandleOutsideExtensionMutexLock(a1);
}

```

## disassembly

```asm
0x14000f680  mov     [rsp-8+arg_10], rbx
0x14000f685  push    rbp
0x14000f686  push    rsi
0x14000f687  push    rdi
0x14000f688  push    r12
0x14000f68a  push    r13
0x14000f68c  push    r14
0x14000f68e  push    r15
0x14000f690  lea     rbp, [rsp-30h]
0x14000f695  sub     rsp, 130h
0x14000f69c  mov     rax, cs:__security_cookie
0x14000f6a3  xor     rax, rsp
0x14000f6a6  mov     [rbp+60h+var_38], rax
0x14000f6aa  xorps   xmm0, xmm0
0x14000f6ad  xor     eax, eax
0x14000f6af  mov     [rbp+60h+var_48], rax
0x14000f6b3  xorps   xmm1, xmm1
0x14000f6b6  mov     [rbp+60h+var_40], eax
0x14000f6b9  mov     r15, rdx
0x14000f6bc  movzx   eax, cs:word_140007000
0x14000f6c3  mov     rsi, rcx
0x14000f6c6  add     ax, [rdx+50h]
0x14000f6ca  xor     r14d, r14d
0x14000f6cd  movups  xmmword ptr [rsp+160h+P], xmm0
0x14000f6d2  mov     word ptr [rsp+160h+P], ax
0x14000f6d7  mov     ecx, 102h
0x14000f6dc  add     ax, 2
0x14000f6e0  mov     [rbp+60h+var_C0], r14
0x14000f6e4  movzx   edx, ax
0x14000f6e7  mov     r8d, 41746E4Dh
0x14000f6ed  movups  xmmword ptr [rbp+60h+ObjectAttributes.ObjectName], xmm0
0x14000f6f1  mov     word ptr [rsp+160h+P+2], dx
0x14000f6f6  mov     [rsp+160h+FileHandle], r14
0x14000f6fb  movups  xmmword ptr [rbp+60h+var_68], xmm1
0x14000f6ff  movups  xmmword ptr [rbp+60h+ObjectAttributes.Length], xmm0
0x14000f703  movups  xmmword ptr [rbp+60h+ObjectAttributes+1Ch], xmm0
0x14000f707  movups  xmmword ptr [rbp+60h+IoStatusBlock], xmm0
0x14000f70b  movups  [rbp+60h+FileInformation], xmm1
0x14000f70f  movups  xmmword ptr [rbp+60h+var_E0], xmm0
0x14000f713  movups  xmmword ptr [rbp+60h+var_B8.Length], xmm0
0x14000f717  call    cs:__imp_ExAllocatePool2
0x14000f71e  nop     dword ptr [rax+rax+00h]
0x14000f723  mov     [rsp+160h+P+8], rax
0x14000f728  test    rax, rax
0x14000f72b  jnz     short loc_14000F762
0x14000f72d  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f734  lea     rdi, WPP_GLOBAL_Control
0x14000f73b  cmp     rcx, rdi
0x14000f73e  jz      loc_14000FC91
0x14000f744  mov     eax, [rcx+2Ch]
0x14000f747  test    al, 4
0x14000f749  jz      loc_14000FC91
0x14000f74f  mov     edx, 99h
0x14000f754  mov     rcx, [rcx+18h]
0x14000f758  call    WPP_SF_
0x14000f75d  jmp     loc_14000FC91
0x14000f762  movzx   r8d, word ptr [r15+50h]; Size
0x14000f767  mov     rcx, rax; void *
0x14000f76a  mov     rdx, [r15+58h]; Src
0x14000f76e  call    memmove
0x14000f773  movzx   ecx, word ptr [r15+50h]
0x14000f778  add     rcx, [rsp+160h+P+8]; void *
0x14000f77d  movzx   r8d, cs:word_140007000; Size
0x14000f785  mov     rdx, cs:off_140007008; Src
0x14000f78c  call    memmove
0x14000f791  movzx   edx, word ptr [rsp+160h+P]
0x14000f796  lea     r13, [rsi+38h]
0x14000f79a  mov     rax, [rsp+160h+P+8]
0x14000f79f  xorps   xmm0, xmm0
0x14000f7a2  shr     rdx, 1
0x14000f7a5  mov     rcx, r13; Mutex
0x14000f7a8  mov     [rax+rdx*2], r14w
0x14000f7ad  lea     rax, [rsp+160h+P]
0x14000f7b2  mov     rbx, [rsi+150h]
0x14000f7b9  xor     edx, edx; Wait
0x14000f7bb  mov     rdi, [r15+0B0h]
0x14000f7c2  mov     [rbp+60h+ObjectAttributes.ObjectName], rax
0x14000f7c6  mov     [rbp+60h+var_C8], rbx
0x14000f7ca  mov     [rbp+60h+var_D0], rdi
0x14000f7ce  mov     [rbp+60h+ObjectAttributes.Length], 30h ; '0'
0x14000f7d5  mov     [rbp+60h+ObjectAttributes.RootDirectory], r14
0x14000f7d9  mov     [rbp+60h+ObjectAttributes.Attributes], 240h
0x14000f7e0  movdqu  xmmword ptr [rbp+60h+ObjectAttributes.SecurityDescriptor], xmm0
0x14000f7e5  call    cs:__imp_KeReleaseMutex
0x14000f7ec  nop     dword ptr [rax+rax+00h]
0x14000f7f1  lea     r9, [rbp+60h+IoStatusBlock]; IoStatusBlock
0x14000f7f5  mov     [rsp+160h+OpenOptions], 20h ; ' '; OpenOptions
0x14000f7fd  lea     r8, [rbp+60h+ObjectAttributes]; ObjectAttributes
0x14000f801  mov     [rsp+160h+ShareAccess], 3; ShareAccess
0x14000f809  mov     edx, 120089h; DesiredAccess
0x14000f80e  lea     rcx, [rsp+160h+FileHandle]; FileHandle
0x14000f813  call    cs:__imp_ZwOpenFile
0x14000f81a  nop     dword ptr [rax+rax+00h]
0x14000f81f  mov     rcx, [rsp+160h+P+8]; P
0x14000f824  xor     edx, edx; Tag
0x14000f826  mov     r12d, eax
0x14000f829  call    cs:__imp_ExFreePoolWithTag
0x14000f830  nop     dword ptr [rax+rax+00h]
0x14000f835  xor     r9d, r9d; Alertable
0x14000f838  mov     qword ptr [rsp+160h+ShareAccess], r14; Timeout
0x14000f83d  xor     r8d, r8d; WaitMode
0x14000f840  xor     edx, edx; WaitReason
0x14000f842  mov     rcx, r13; Object
0x14000f845  call    cs:__imp_KeWaitForSingleObject
0x14000f84c  nop     dword ptr [rax+rax+00h]
0x14000f851  mov     r8, rdi
0x14000f854  mov     rdx, rbx
0x14000f857  mov     rcx, rsi
0x14000f85a  call    VerifyEpoch
0x14000f85f  lea     rdi, WPP_GLOBAL_Control
0x14000f866  mov     r14d, eax
0x14000f869  mov     bl, 1
0x14000f86b  test    eax, eax
0x14000f86d  jns     short loc_14000F895
0x14000f86f  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f876  cmp     rcx, rdi
0x14000f879  jz      short loc_14000F8A0
0x14000f87b  mov     eax, [rcx+2Ch]
0x14000f87e  test    bl, al
0x14000f880  jz      short loc_14000F8A0
0x14000f882  mov     rcx, [rcx+18h]
0x14000f886  mov     edx, 9Ah
0x14000f88b  mov     r9d, r14d
0x14000f88e  call    WPP_SF_L
0x14000f893  jmp     short loc_14000F8A0
0x14000f895  xor     r14d, r14d
0x14000f898  test    r12d, r12d
0x14000f89b  jns     short loc_14000F8D9
0x14000f89d  mov     r14d, r12d
0x14000f8a0  mov     byte ptr [r15+84h], 0
0x14000f8a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8af  cmp     rcx, rdi
0x14000f8b2  jz      loc_14000FC91
0x14000f8b8  mov     eax, [rcx+2Ch]
0x14000f8bb  test    bl, al
0x14000f8bd  jz      loc_14000FC91
0x14000f8c3  mov     edx, 9Bh
0x14000f8c8  mov     rcx, [rcx+18h]
0x14000f8cc  mov     r9d, r14d
0x14000f8cf  call    WPP_SF_L
0x14000f8d4  jmp     loc_14000FC91
0x14000f8d9  lea     rax, [rbp+60h+var_48]
0x14000f8dd  mov     [rbp+60h+var_48+4], r14
0x14000f8e1  xor     edx, edx; Wait
0x14000f8e3  mov     [rbp+60h+var_B8.Buffer], rax
0x14000f8e7  mov     rcx, r13; Mutex
0x14000f8ea  mov     dword ptr [rbp+60h+var_48], 0A0000003h
0x14000f8f1  mov     dword ptr [rbp+60h+var_B8.Length], 0C000Ch
0x14000f8f8  call    cs:__imp_KeReleaseMutex
0x14000f8ff  nop     dword ptr [rax+rax+00h]
0x14000f904  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x14000f909  lea     rax, [rbp+60h+var_B8]
0x14000f90d  mov     [rsp+160h+RestartScan], r14b; RestartScan
0x14000f912  xor     r9d, r9d; ApcContext
0x14000f915  mov     [rsp+160h+FileName], rax; FileName
0x14000f91a  xor     r8d, r8d; ApcRoutine
0x14000f91d  mov     [rsp+160h+ReturnSingleEntry], bl; ReturnSingleEntry
0x14000f921  lea     rax, [rbp+60h+FileInformation]
0x14000f925  mov     [rsp+160h+FileInformationClass], 21h ; '!'; FileInformationClass
0x14000f92d  xor     edx, edx; Event
0x14000f92f  mov     [rsp+160h+Length], 10h; Length
0x14000f937  mov     qword ptr [rsp+160h+OpenOptions], rax; FileInformation
0x14000f93c  lea     rax, [rbp+60h+IoStatusBlock]
0x14000f940  mov     qword ptr [rsp+160h+ShareAccess], rax; IoStatusBlock
0x14000f945  call    cs:__imp_ZwQueryDirectoryFile
0x14000f94c  nop     dword ptr [rax+rax+00h]
0x14000f951  xor     r9d, r9d; Alertable
0x14000f954  mov     qword ptr [rsp+160h+ShareAccess], r14; Timeout
0x14000f959  xor     r8d, r8d; WaitMode
0x14000f95c  xor     edx, edx; WaitReason
0x14000f95e  mov     rcx, r13; Object
0x14000f961  mov     r12d, eax
0x14000f964  call    cs:__imp_KeWaitForSingleObject
0x14000f96b  nop     dword ptr [rax+rax+00h]
0x14000f970  mov     r8, [rbp+60h+var_D0]
0x14000f974  mov     rcx, rsi
0x14000f977  mov     rdx, [rbp+60h+var_C8]
0x14000f97b  call    VerifyEpoch
0x14000f980  lea     rdi, WPP_GLOBAL_Control
0x14000f987  mov     r14d, eax
0x14000f98a  test    eax, eax
0x14000f98c  jns     short loc_14000F9B4
0x14000f98e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f995  cmp     rcx, rdi
0x14000f998  jz      short loc_14000F9BC
0x14000f99a  mov     eax, [rcx+2Ch]
0x14000f99d  test    bl, al
0x14000f99f  jz      short loc_14000F9BC
0x14000f9a1  mov     rcx, [rcx+18h]
0x14000f9a5  mov     edx, 9Ch
0x14000f9aa  mov     r9d, r14d
0x14000f9ad  call    WPP_SF_L
0x14000f9b2  jmp     short loc_14000F9BC
0x14000f9b4  test    r12d, r12d
0x14000f9b7  jns     short loc_14000F9F7
0x14000f9b9  mov     r14d, r12d
0x14000f9bc  mov     rdx, [rsp+160h+FileHandle]
0x14000f9c1  mov     rcx, rsi
0x14000f9c4  call    CloseFileHandleOutsideExtensionMutexLock
0x14000f9c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9d0  cmp     rcx, rdi
0x14000f9d3  jz      loc_14000FC91
0x14000f9d9  mov     eax, [rcx+2Ch]
0x14000f9dc  test    bl, al
0x14000f9de  jz      loc_14000FC91
0x14000f9e4  cmp     [rcx+29h], bl
0x14000f9e7  jb      loc_14000FC91
0x14000f9ed  mov     edx, 9Dh
0x14000f9f2  jmp     loc_14000F8C8
0x14000f9f7  mov     edx, 0C8h
0x14000f9fc  mov     dword ptr [rbp+60h+var_E0], 0C80000h
0x14000fa03  mov     r8d, 41746E4Dh
0x14000fa09  lea     ecx, [rdx+3Ah]
0x14000fa0c  call    cs:__imp_ExAllocatePool2
0x14000fa13  nop     dword ptr [rax+rax+00h]
0x14000fa18  mov     [rbp+60h+var_E0+8], rax
0x14000fa1c  test    rax, rax
0x14000fa1f  jnz     short loc_14000FA5A
0x14000fa21  mov     rdx, [rsp+160h+FileHandle]
0x14000fa26  mov     rcx, rsi
0x14000fa29  call    CloseFileHandleOutsideExtensionMutexLock
0x14000fa2e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fa35  lea     rdi, WPP_GLOBAL_Control
0x14000fa3c  cmp     rcx, rdi
0x14000fa3f  jz      loc_14000FC91
0x14000fa45  mov     eax, [rcx+2Ch]
0x14000fa48  test    al, 4
0x14000fa4a  jz      loc_14000FC91
0x14000fa50  mov     edx, 9Eh
0x14000fa55  jmp     loc_14000F754
0x14000fa5a  mov     r14b, bl
0x14000fa5d  lea     rdi, WPP_GLOBAL_Control
0x14000fa64  mov     eax, dword ptr [rbp+60h+FileInformation+8]
0x14000fa67  lea     rcx, [rsi+38h]; Mutex
0x14000fa6b  mov     r13, qword ptr [rbp+60h+FileInformation]
0x14000fa6f  xor     edx, edx; Wait
0x14000fa71  mov     [rsp+160h+var_E8], eax
0x14000fa75  call    cs:__imp_KeReleaseMutex
0x14000fa7c  nop     dword ptr [rax+rax+00h]
0x14000fa81  mov     [rsp+160h+RestartScan], r14b; RestartScan
0x14000fa86  mov     al, r14b
0x14000fa89  neg     al
0x14000fa8b  lea     rax, [rbp+60h+var_B8]
0x14000fa8f  sbb     rcx, rcx
0x14000fa92  xor     r9d, r9d; ApcContext
0x14000fa95  and     rcx, rax
0x14000fa98  xor     r8d, r8d; ApcRoutine
0x14000fa9b  mov     [rsp+160h+FileName], rcx; FileName
0x14000faa0  lea     rax, [rbp+60h+FileInformation]
0x14000faa4  mov     rcx, [rsp+160h+FileHandle]; FileHandle
0x14000faa9  xor     edx, edx; Event
0x14000faab  mov     [rsp+160h+ReturnSingleEntry], bl; ReturnSingleEntry
0x14000faaf  mov     [rsp+160h+FileInformationClass], 21h ; '!'; FileInformationClass
0x14000fab7  mov     [rsp+160h+Length], 10h; Length
0x14000fabf  mov     qword ptr [rsp+160h+OpenOptions], rax; FileInformation
0x14000fac4  lea     rax, [rbp+60h+IoStatusBlock]
0x14000fac8  mov     qword ptr [rsp+160h+ShareAccess], rax; IoStatusBlock
0x14000facd  call    cs:__imp_ZwQueryDirectoryFile
0x14000fad4  nop     dword ptr [rax+rax+00h]
0x14000fad9  xor     r9d, r9d; Alertable
0x14000fadc  mov     qword ptr [rsp+160h+ShareAccess], 0; Timeout
0x14000fae5  xor     r8d, r8d; WaitMode
0x14000fae8  lea     rcx, [rsi+38h]; Object
0x14000faec  xor     edx, edx; WaitReason
0x14000faee  mov     r12d, eax
0x14000faf1  call    cs:__imp_KeWaitForSingleObject
0x14000faf8  nop     dword ptr [rax+rax+00h]
0x14000fafd  mov     r8, [rbp+60h+var_D0]
0x14000fb01  mov     rcx, rsi
0x14000fb04  mov     rdx, [rbp+60h+var_C8]
0x14000fb08  call    VerifyEpoch
0x14000fb0d  mov     r9d, eax
0x14000fb10  test    eax, eax
0x14000fb12  js      loc_14000FC51
0x14000fb18  test    r14b, r14b
0x14000fb1b  jz      short loc_14000FB22
0x14000fb1d  xor     r14b, r14b
0x14000fb20  jmp     short loc_14000FB35
0x14000fb22  cmp     r13, qword ptr [rbp+60h+FileInformation]
0x14000fb26  jnz     short loc_14000FB35
0x14000fb28  mov     eax, [rsp+160h+var_E8]
0x14000fb2c  cmp     eax, dword ptr [rbp+60h+FileInformation+8]
0x14000fb2f  jz      loc_14000FC72
0x14000fb35  test    r12d, r12d
0x14000fb38  js      loc_14000FC34
0x14000fb3e  cmp     dword ptr [rbp+60h+FileInformation+8], 0A0000003h
0x14000fb45  jnz     loc_14000FC72
0x14000fb4b  mov     r8, [rsp+160h+FileHandle]
0x14000fb50  lea     rax, [rbp+60h+var_68]
0x14000fb54  mov     qword ptr [rsp+160h+Length], rax
0x14000fb59  lea     r9, [rbp+60h+FileInformation]
0x14000fb5d  lea     rax, [rbp+60h+var_E0]
0x14000fb61  mov     rdx, r15
0x14000fb64  mov     qword ptr [rsp+160h+OpenOptions], rax
0x14000fb69  mov     rcx, rsi
0x14000fb6c  mov     qword ptr [rsp+160h+ShareAccess], 0
0x14000fb75  call    QueryVolumeName
0x14000fb7a  test    eax, eax
0x14000fb7c  jns     short loc_14000FBB8
0x14000fb7e  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
