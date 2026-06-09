# NdisOpenFile

- ea: `0x1400da2b0`
- end: `0x1400da75c`
- name: `NdisOpenFile`
- size: `1196`
- prototype: `void __stdcall(PNDIS_STATUS Status, PNDIS_HANDLE FileHandle, PUINT FileLength, PNDIS_STRING FileName, NDIS_PHYSICAL_ADDRESS HighestAcceptableAddress)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x14001cf60`
- `0x14002ab60`
- `0x140059c80`
- `0x14005b490`
- `0x1400da2b0`
- `0x1400eb380`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400da3c3`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400da3c3`
- `ntoskrnl!ZwClose` at `0x1400da51a`
- `ntoskrnl!ZwClose` at `0x1400da615`
- `ntoskrnl!ZwClose` at `0x1400da51a`
- `ntoskrnl!ZwClose` at `0x1400da615`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400da475`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400da659`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400da6e7`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400da475`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400da659`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400da6e7`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400da67f`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400da67f`
- `ntoskrnl!ExAllocatePool2` at `0x1400da368`
- `ntoskrnl!ExAllocatePool2` at `0x1400da587`
- `ntoskrnl!ExAllocatePool2` at `0x1400da63a`
- `ntoskrnl!ExAllocatePool2` at `0x1400da368`
- `ntoskrnl!ExAllocatePool2` at `0x1400da587`
- `ntoskrnl!ExAllocatePool2` at `0x1400da63a`
- `ntoskrnl!ZwReadFile` at `0x1400da602`
- `ntoskrnl!ZwReadFile` at `0x1400da602`
- `ntoskrnl!ZwCreateFile` at `0x1400da461`
- `ntoskrnl!ZwCreateFile` at `0x1400da461`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400da4d8`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400da4d8`

## string_xrefs

- `0x1400da388`: `\SystemRoot\system32\drivers\`

## pseudocode

```c
void __stdcall NdisOpenFile(
        PNDIS_STATUS Status,
        PNDIS_HANDLE FileHandle,
        PUINT FileLength,
        PNDIS_STRING FileName,
        NDIS_PHYSICAL_ADDRESS HighestAcceptableAddress)
{
  PNDIS_HANDLE v7; // r12
  unsigned __int16 v9; // ax
  __int64 Pool2; // rax
  int v11; // edx
  NTSTATUS v12; // edi
  NTSTATUS v13; // eax
  int v14; // edx
  __int64 v15; // rsi
  void *v16; // rax
  int v17; // edx
  void *v18; // r14
  NTSTATUS v19; // r15d
  int v20; // edx
  _QWORD *v21; // rax
  _BYTE *v22; // rdi
  void *FileHandlea; // [rsp+60h] [rbp-71h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+68h] [rbp-69h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+88h] [rbp-49h] BYREF
  __int128 FileInformation; // [rsp+B8h] [rbp-19h] BYREF
  __int64 v28; // [rsp+C8h] [rbp-9h]

  FileHandlea = 0;
  v28 = 0;
  v7 = FileHandle;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  Destination = 0;
  FileInformation = 0;
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(FileHandle) = 4;
    WPP_RECORDER_SF_(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)FileHandle,
      1,
      10,
      (struct _GUID *)&WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids);
  }
  v9 = FileName->MaximumLength + 60;
  if ( v9 < 0x3Cu )
  {
    *Status = -2147483643;
    Destination.MaximumLength = -1;
    goto LABEL_33;
  }
  Destination.MaximumLength = FileName->MaximumLength + 60;
  Pool2 = ExAllocatePool2(66, v9, 1852195918);
  Destination.Buffer = (wchar_t *)Pool2;
  if ( !Pool2 )
  {
    *Status = -1073741670;
    goto LABEL_33;
  }
  Destination.Length = 58;
  *(_OWORD *)Pool2 = *(_OWORD *)L"\\SystemRoot\\system32\\drivers\\";
  *(_OWORD *)(Pool2 + 16) = *(_OWORD *)L"oot\\system32\\drivers\\";
  *(_OWORD *)(Pool2 + 32) = *(_OWORD *)L"em32\\drivers\\";
  *(_OWORD *)(Pool2 + 44) = *(_OWORD *)L"rivers\\";
  RtlAppendUnicodeStringToString(&Destination, FileName);
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v11) = 4;
    WPP_RECORDER_SF_Z(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      v11,
      1,
      11,
      (struct _GUID *)&WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids,
      (__int64)&Destination);
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &Destination;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v12 = ZwCreateFile(&FileHandlea, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 0, 1u, 1u, 0x20u, 0, 0);
  ExFreePoolWithTag(Destination.Buffer, 0);
  if ( v12 < 0 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(FileHandle) = 2;
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        (int)FileHandle,
        1,
        12,
        (struct _GUID *)&WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids,
        v12);
    }
    *Status = -1073676261;
    goto LABEL_33;
  }
  v13 = ZwQueryInformationFile(FileHandlea, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
  if ( v13 < 0 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v14,
        1,
        13,
        (struct _GUID *)&WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids,
        v13);
    }
LABEL_15:
    ZwClose(FileHandlea);
    *Status = -1073676260;
    goto LABEL_33;
  }
  v15 = DWORD2(FileInformation);
  if ( !DWORD2(FileInformation) )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v14,
        1,
        14,
        (struct _GUID *)&WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids,
        SBYTE8(FileInformation));
    }
    goto LABEL_15;
  }
  v16 = (void *)ExAllocatePool2(66, DWORD2(FileInformation), 1768309838);
  v18 = v16;
  if ( !v16 )
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v17) = 2;
      WPP_RECORDER_SF_(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v17,
        1,
        15,
        (struct _GUID *)&WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids);
    }
    goto LABEL_15;
  }
  v19 = ZwReadFile(FileHandlea, 0, 0, 0, &IoStatusBlock, v16, v15, 0, 0);
  ZwClose(FileHandlea);
  if ( v19 >= 0 && IoStatusBlock.Information == v15 )
  {
    v21 = (_QWORD *)ExAllocatePool2(64, 24, 1684423758);
    v22 = v21;
    if ( v21 )
    {
      *v21 = v18;
      KeInitializeSpinLock(v21 + 1);
      *v7 = v22;
      *FileLength = v15;
      *Status = 0;
      v22[16] = 0;
    }
    else
    {
      *Status = -1073741670;
      ExFreePoolWithTag(v18, 0);
    }
  }
  else
  {
    if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v20) = 2;
      WPP_RECORDER_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 8),
        v20,
        1,
        16,
        (struct _GUID *)&WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids,
        v19);
    }
    *Status = -1073676260;
    ExFreePoolWithTag(v18, 0);
  }
LABEL_33:
  if ( *(enum Ndis::ReadBindingsOptions::Flags **)&WPP_RECORDER_INITIALIZED != &WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(FileHandle) = 4;
    WPP_RECORDER_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 8),
      (int)FileHandle,
      1,
      17,
      (struct _GUID *)&WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids,
      *Status);
  }
}

```

## disassembly

```asm
0x1400da2b0  push    rbp
0x1400da2b2  push    rbx
0x1400da2b3  push    rsi
0x1400da2b4  push    rdi
0x1400da2b5  push    r12
0x1400da2b7  push    r13
0x1400da2b9  push    r14
0x1400da2bb  push    r15
0x1400da2bd  lea     rbp, [rsp-17h]
0x1400da2c2  sub     rsp, 0E8h
0x1400da2c9  mov     rax, cs:__security_cookie
0x1400da2d0  xor     rax, rsp
0x1400da2d3  mov     [rbp+4Fh+var_50], rax
0x1400da2d7  xorps   xmm0, xmm0
0x1400da2da  xor     r15d, r15d
0x1400da2dd  xor     eax, eax
0x1400da2df  mov     [rbp+4Fh+FileHandle], r15
0x1400da2e3  xorps   xmm1, xmm1
0x1400da2e6  mov     [rbp+4Fh+var_58], rax
0x1400da2ea  mov     rdi, r9
0x1400da2ed  mov     r13, r8
0x1400da2f0  mov     r12, rdx
0x1400da2f3  mov     rbx, rcx
0x1400da2f6  movups  xmmword ptr [rbp+4Fh+IoStatusBlock.___u0], xmm0
0x1400da2fa  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400da2fe  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400da302  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400da306  movups  xmmword ptr [rbp+4Fh+Destination.Length], xmm0
0x1400da30a  movups  [rbp+4Fh+FileInformation], xmm1
0x1400da30e  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400da315  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400da31c  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400da323  jz      short loc_1400DA344
0x1400da325  mov     rcx, cs:WPP_GLOBAL_Control
0x1400da32c  lea     r9d, [r15+0Ah]; int
0x1400da330  lea     r8d, [r15+1]; int
0x1400da334  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400da339  mov     dl, 4; int
0x1400da33b  mov     rcx, [rcx+40h]; int
0x1400da33f  call    WPP_RECORDER_SF_
0x1400da344  movzx   eax, word ptr [rdi+2]
0x1400da348  add     ax, 3Ch ; '<'
0x1400da34c  cmp     ax, 3Ch ; '<'
0x1400da350  jb      loc_1400DA6FC
0x1400da356  movzx   edx, ax
0x1400da359  mov     ecx, 42h ; 'B'
0x1400da35e  mov     r8d, 6E66444Eh
0x1400da364  mov     [rbp+4Fh+Destination.MaximumLength], ax
0x1400da368  call    cs:__imp_ExAllocatePool2
0x1400da36f  nop     dword ptr [rax+rax+00h]
0x1400da374  mov     [rbp+4Fh+Destination.Buffer], rax
0x1400da378  test    rax, rax
0x1400da37b  jnz     short loc_1400DA388
0x1400da37d  mov     dword ptr [rbx], 0C000009Ah
0x1400da383  jmp     loc_1400DA70B
0x1400da388  movups  xmm0, xmmword ptr cs:aSystemrootSyst; "\\SystemRoot\\system32\\drivers\\"
0x1400da38f  mov     ecx, 3Ah ; ':'
0x1400da394  mov     rdx, rdi; Source
0x1400da397  mov     [rbp+4Fh+Destination.Length], cx
0x1400da39b  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1400da39f  movups  xmmword ptr [rax], xmm0
0x1400da3a2  movups  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot\\system32\\drivers\\"
0x1400da3a9  movups  xmmword ptr [rax+10h], xmm1
0x1400da3ad  movups  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "em32\\drivers\\"
0x1400da3b4  movups  xmmword ptr [rax+20h], xmm0
0x1400da3b8  movups  xmm1, xmmword ptr cs:aSystemrootSyst+2Ch; "rivers\\"
0x1400da3bf  movups  xmmword ptr [rax+2Ch], xmm1
0x1400da3c3  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400da3ca  nop     dword ptr [rax+rax+00h]
0x1400da3cf  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400da3d6  jz      short loc_1400DA402
0x1400da3d8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400da3df  lea     rax, [rbp+4Fh+Destination]
0x1400da3e3  mov     r9d, 0Bh; int
0x1400da3e9  mov     qword ptr [rsp+120h+FileAttributes], rax; __int64
0x1400da3ee  mov     dl, 4; int
0x1400da3f0  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400da3f5  mov     rcx, [rcx+40h]; int
0x1400da3f9  lea     r8d, [r9-0Ah]; int
0x1400da3fd  call    WPP_RECORDER_SF_Z
0x1400da402  mov     [rsp+120h+EaLength], r15d; EaLength
0x1400da407  lea     rax, [rbp+4Fh+Destination]
0x1400da40b  mov     [rsp+120h+EaBuffer], r15; EaBuffer
0x1400da410  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1400da414  mov     [rsp+120h+CreateOptions], 20h ; ' '; CreateOptions
0x1400da41c  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400da420  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x1400da428  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400da42c  mov     [rsp+120h+ShareAccess], 1; ShareAccess
0x1400da434  xorps   xmm0, xmm0
0x1400da437  mov     [rsp+120h+FileAttributes], r15d; FileAttributes
0x1400da43c  mov     edx, 100001h; DesiredAccess
0x1400da441  mov     [rsp+120h+AllocationSize], r15; AllocationSize
0x1400da446  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400da44d  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r15
0x1400da451  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1400da458  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400da45c  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400da461  call    cs:__imp_ZwCreateFile
0x1400da468  nop     dword ptr [rax+rax+00h]
0x1400da46d  mov     rcx, [rbp+4Fh+Destination.Buffer]; P
0x1400da471  xor     edx, edx; Tag
0x1400da473  mov     edi, eax
0x1400da475  call    cs:__imp_ExFreePoolWithTag
0x1400da47c  nop     dword ptr [rax+rax+00h]
0x1400da481  test    edi, edi
0x1400da483  jns     short loc_1400DA4BE
0x1400da485  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400da48c  jz      short loc_1400DA4B3
0x1400da48e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400da495  mov     r9d, 0Ch; int
0x1400da49b  mov     [rsp+120h+FileAttributes], edi; char
0x1400da49f  mov     dl, 2; int
0x1400da4a1  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400da4a6  mov     rcx, [rcx+40h]; int
0x1400da4aa  lea     r8d, [r9-0Bh]; int
0x1400da4ae  call    WPP_RECORDER_SF_D
0x1400da4b3  mov     dword ptr [rbx], 0C001001Bh
0x1400da4b9  jmp     loc_1400DA70B
0x1400da4be  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400da4c2  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x1400da4c6  mov     r9d, 18h; Length
0x1400da4cc  mov     dword ptr [rsp+120h+AllocationSize], 5; FileInformationClass
0x1400da4d4  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1400da4d8  call    cs:__imp_ZwQueryInformationFile
0x1400da4df  nop     dword ptr [rax+rax+00h]
0x1400da4e4  test    eax, eax
0x1400da4e6  jns     short loc_1400DA531
0x1400da4e8  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400da4ef  jz      short loc_1400DA516
0x1400da4f1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400da4f8  mov     r9d, 0Dh; int
0x1400da4fe  mov     [rsp+120h+FileAttributes], eax; char
0x1400da502  mov     dl, 2; int
0x1400da504  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400da509  mov     rcx, [rcx+40h]; int
0x1400da50d  lea     r8d, [r9-0Ch]; int
0x1400da511  call    WPP_RECORDER_SF_D
0x1400da516  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1400da51a  call    cs:__imp_ZwClose
0x1400da521  nop     dword ptr [rax+rax+00h]
0x1400da526  mov     dword ptr [rbx], 0C001001Ch
0x1400da52c  jmp     loc_1400DA70B
0x1400da531  mov     esi, dword ptr [rbp+4Fh+FileInformation+8]
0x1400da534  cmp     esi, 1
0x1400da537  jnb     short loc_1400DA579
0x1400da539  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400da540  jz      short loc_1400DA570
0x1400da542  mov     rcx, cs:WPP_GLOBAL_Control
0x1400da549  mov     r9d, 0Eh; int
0x1400da54f  mov     [rsp+120h+FileAttributes], esi; char
0x1400da553  mov     dl, 2; int
0x1400da555  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400da55c  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400da561  mov     rcx, [rcx+40h]; int
0x1400da565  lea     r8d, [r9-0Dh]; int
0x1400da569  call    WPP_RECORDER_SF_d
0x1400da56e  jmp     short loc_1400DA516
0x1400da570  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400da577  jmp     short loc_1400DA516
0x1400da579  mov     r8d, 6966444Eh
0x1400da57f  mov     rdx, rsi
0x1400da582  mov     ecx, 42h ; 'B'
0x1400da587  call    cs:__imp_ExAllocatePool2
0x1400da58e  nop     dword ptr [rax+rax+00h]
0x1400da593  mov     r14, rax
0x1400da596  test    rax, rax
0x1400da599  jnz     short loc_1400DA5DA
0x1400da59b  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400da5a2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400da5a9  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400da5b0  jz      loc_1400DA516
0x1400da5b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400da5bd  lea     r9d, [rax+0Fh]; int
0x1400da5c1  lea     r8d, [rax+1]; int
0x1400da5c5  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400da5ca  mov     dl, 2; int
0x1400da5cc  mov     rcx, [rcx+40h]; int
0x1400da5d0  call    WPP_RECORDER_SF_
0x1400da5d5  jmp     loc_1400DA516
0x1400da5da  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400da5de  lea     rax, [rbp+4Fh+IoStatusBlock]
0x1400da5e2  mov     qword ptr [rsp+120h+CreateOptions], r15; Key
0x1400da5e7  xor     r9d, r9d; ApcContext
0x1400da5ea  mov     qword ptr [rsp+120h+CreateDisposition], r15; ByteOffset
0x1400da5ef  xor     r8d, r8d; ApcRoutine
0x1400da5f2  mov     [rsp+120h+ShareAccess], esi; Length
0x1400da5f6  xor     edx, edx; Event
0x1400da5f8  mov     qword ptr [rsp+120h+FileAttributes], r14; Buffer
0x1400da5fd  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x1400da602  call    cs:__imp_ZwReadFile
0x1400da609  nop     dword ptr [rax+rax+00h]
0x1400da60e  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1400da612  mov     r15d, eax
0x1400da615  call    cs:__imp_ZwClose
0x1400da61c  nop     dword ptr [rax+rax+00h]
0x1400da621  test    r15d, r15d
0x1400da624  js      short loc_1400DA69F
0x1400da626  cmp     [rbp+4Fh+IoStatusBlock.Information], rsi
0x1400da62a  jnz     short loc_1400DA69F
0x1400da62c  mov     edx, 18h
0x1400da631  mov     r8d, 6466444Eh
0x1400da637  lea     ecx, [rdx+28h]
0x1400da63a  call    cs:__imp_ExAllocatePool2
0x1400da641  nop     dword ptr [rax+rax+00h]
0x1400da646  mov     rdi, rax
0x1400da649  test    rax, rax
0x1400da64c  jnz     short loc_1400DA678
0x1400da64e  xor     edx, edx; Tag
0x1400da650  mov     dword ptr [rbx], 0C000009Ah
0x1400da656  mov     rcx, r14; P
0x1400da659  call    cs:__imp_ExFreePoolWithTag
0x1400da660  nop     dword ptr [rax+rax+00h]
0x1400da665  lea     r14, WPP_RECORDER_INITIALIZED
0x1400da66c  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400da673  jmp     loc_1400DA70B
0x1400da678  lea     rcx, [rax+8]; SpinLock
0x1400da67c  mov     [rax], r14
0x1400da67f  call    cs:__imp_KeInitializeSpinLock
0x1400da686  nop     dword ptr [rax+rax+00h]
0x1400da68b  mov     [r12], rdi
0x1400da68f  mov     [r13+0], esi
0x1400da693  mov     dword ptr [rbx], 0
0x1400da699  mov     byte ptr [rdi+10h], 0
0x1400da69d  jmp     short loc_1400DA665
0x1400da69f  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400da6a6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400da6ad  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400da6b4  jz      short loc_1400DA6DC
0x1400da6b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400da6bd  mov     r9d, 10h; int
0x1400da6c3  mov     [rsp+120h+FileAttributes], r15d; char
0x1400da6c8  mov     dl, 2; int
0x1400da6ca  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400da6cf  mov     rcx, [rcx+40h]; int
0x1400da6d3  lea     r8d, [r9-0Fh]; int
0x1400da6d7  call    WPP_RECORDER_SF_D
0x1400da6dc  xor     edx, edx; Tag
0x1400da6de  mov     dword ptr [rbx], 0C001001Ch
0x1400da6e4  mov     rcx, r14; P
0x1400da6e7  call    cs:__imp_ExFreePoolWithTag
0x1400da6ee  nop     dword ptr [rax+rax+00h]
0x1400da6f3  lea     r14, WPP_RECORDER_INITIALIZED
0x1400da6fa  jmp     short loc_1400DA70B
0x1400da6fc  mov     eax, 0FFFFh
0x1400da701  mov     dword ptr [rbx], 80000005h
0x1400da707  mov     [rbp+4Fh+Destination.MaximumLength], ax
0x1400da70b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400da712  jz      short loc_1400DA73B
0x1400da714  mov     rcx, cs:WPP_GLOBAL_Control
0x1400da71b  mov     r9d, 11h; int
0x1400da721  mov     eax, [rbx]
0x1400da723  mov     dl, 4; int
0x1400da725  mov     [rsp+120h+FileAttributes], eax; char
0x1400da729  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400da72e  mov     rcx, [rcx+40h]; int
0x1400da732  lea     r8d, [r9-10h]; int
0x1400da736  call    WPP_RECORDER_SF_D
0x1400da73b  mov     rcx, [rbp+4Fh+var_50]
0x1400da73f  xor     rcx, rsp; StackCookie
0x1400da742  call    __security_check_cookie
0x1400da747  add     rsp, 0E8h
0x1400da74e  pop     r15
0x1400da750  pop     r14
0x1400da752  pop     r13
0x1400da754  pop     r12
0x1400da756  pop     rdi
0x1400da757  pop     rsi
0x1400da758  pop     rbx
0x1400da759  pop     rbp
0x1400da75a  retn
```
