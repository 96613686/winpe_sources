# NdisOpenFile

- ea: `0x1400d5100`
- end: `0x1400d55ac`
- name: `NdisOpenFile`
- size: `1196`
- prototype: `void __stdcall(PNDIS_STATUS Status, PNDIS_HANDLE FileHandle, PUINT FileLength, PNDIS_STRING FileName, NDIS_PHYSICAL_ADDRESS HighestAcceptableAddress)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callees

- `0x140028e00`
- `0x140029620`
- `0x140054b80`
- `0x140056c50`
- `0x1400d5100`
- `0x1400e6160`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400d5213`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400d5213`
- `ntoskrnl!ZwClose` at `0x1400d536a`
- `ntoskrnl!ZwClose` at `0x1400d5465`
- `ntoskrnl!ZwClose` at `0x1400d536a`
- `ntoskrnl!ZwClose` at `0x1400d5465`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d52c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d54a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5537`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d52c5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d54a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d5537`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d54cf`
- `ntoskrnl!KeInitializeSpinLock` at `0x1400d54cf`
- `ntoskrnl!ExAllocatePool2` at `0x1400d51b8`
- `ntoskrnl!ExAllocatePool2` at `0x1400d53d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400d548a`
- `ntoskrnl!ExAllocatePool2` at `0x1400d51b8`
- `ntoskrnl!ExAllocatePool2` at `0x1400d53d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400d548a`
- `ntoskrnl!ZwReadFile` at `0x1400d5452`
- `ntoskrnl!ZwReadFile` at `0x1400d5452`
- `ntoskrnl!ZwCreateFile` at `0x1400d52b1`
- `ntoskrnl!ZwCreateFile` at `0x1400d52b1`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400d5328`
- `ntoskrnl!ZwQueryInformationFile` at `0x1400d5328`

## string_xrefs

- `0x1400d51d8`: `\SystemRoot\system32\drivers\`

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
0x1400d5100  push    rbp
0x1400d5102  push    rbx
0x1400d5103  push    rsi
0x1400d5104  push    rdi
0x1400d5105  push    r12
0x1400d5107  push    r13
0x1400d5109  push    r14
0x1400d510b  push    r15
0x1400d510d  lea     rbp, [rsp-17h]
0x1400d5112  sub     rsp, 0E8h
0x1400d5119  mov     rax, cs:__security_cookie
0x1400d5120  xor     rax, rsp
0x1400d5123  mov     [rbp+4Fh+var_50], rax
0x1400d5127  xorps   xmm0, xmm0
0x1400d512a  xor     r15d, r15d
0x1400d512d  xor     eax, eax
0x1400d512f  mov     [rbp+4Fh+FileHandle], r15
0x1400d5133  xorps   xmm1, xmm1
0x1400d5136  mov     [rbp+4Fh+var_58], rax
0x1400d513a  mov     rdi, r9
0x1400d513d  mov     r13, r8
0x1400d5140  mov     r12, rdx
0x1400d5143  mov     rbx, rcx
0x1400d5146  movups  xmmword ptr [rbp+4Fh+IoStatusBlock.___u0], xmm0
0x1400d514a  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1400d514e  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1400d5152  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d5156  movups  xmmword ptr [rbp+4Fh+Destination.Length], xmm0
0x1400d515a  movups  [rbp+4Fh+FileInformation], xmm1
0x1400d515e  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d5165  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400d516c  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400d5173  jz      short loc_1400D5194
0x1400d5175  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d517c  lea     r9d, [r15+0Ah]; int
0x1400d5180  lea     r8d, [r15+1]; int
0x1400d5184  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400d5189  mov     dl, 4; int
0x1400d518b  mov     rcx, [rcx+40h]; int
0x1400d518f  call    WPP_RECORDER_SF_
0x1400d5194  movzx   eax, word ptr [rdi+2]
0x1400d5198  add     ax, 3Ch ; '<'
0x1400d519c  cmp     ax, 3Ch ; '<'
0x1400d51a0  jb      loc_1400D554C
0x1400d51a6  movzx   edx, ax
0x1400d51a9  mov     ecx, 42h ; 'B'
0x1400d51ae  mov     r8d, 6E66444Eh
0x1400d51b4  mov     [rbp+4Fh+Destination.MaximumLength], ax
0x1400d51b8  call    cs:__imp_ExAllocatePool2
0x1400d51bf  nop     dword ptr [rax+rax+00h]
0x1400d51c4  mov     [rbp+4Fh+Destination.Buffer], rax
0x1400d51c8  test    rax, rax
0x1400d51cb  jnz     short loc_1400D51D8
0x1400d51cd  mov     dword ptr [rbx], 0C000009Ah
0x1400d51d3  jmp     loc_1400D555B
0x1400d51d8  movups  xmm0, xmmword ptr cs:aSystemrootSyst; "\\SystemRoot\\system32\\drivers\\"
0x1400d51df  mov     ecx, 3Ah ; ':'
0x1400d51e4  mov     rdx, rdi; Source
0x1400d51e7  mov     [rbp+4Fh+Destination.Length], cx
0x1400d51eb  lea     rcx, [rbp+4Fh+Destination]; Destination
0x1400d51ef  movups  xmmword ptr [rax], xmm0
0x1400d51f2  movups  xmm1, xmmword ptr cs:aSystemrootSyst+10h; "oot\\system32\\drivers\\"
0x1400d51f9  movups  xmmword ptr [rax+10h], xmm1
0x1400d51fd  movups  xmm0, xmmword ptr cs:aSystemrootSyst+20h; "em32\\drivers\\"
0x1400d5204  movups  xmmword ptr [rax+20h], xmm0
0x1400d5208  movups  xmm1, xmmword ptr cs:aSystemrootSyst+2Ch; "rivers\\"
0x1400d520f  movups  xmmword ptr [rax+2Ch], xmm1
0x1400d5213  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400d521a  nop     dword ptr [rax+rax+00h]
0x1400d521f  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400d5226  jz      short loc_1400D5252
0x1400d5228  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d522f  lea     rax, [rbp+4Fh+Destination]
0x1400d5233  mov     r9d, 0Bh; int
0x1400d5239  mov     qword ptr [rsp+120h+FileAttributes], rax; __int64
0x1400d523e  mov     dl, 4; int
0x1400d5240  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400d5245  mov     rcx, [rcx+40h]; int
0x1400d5249  lea     r8d, [r9-0Ah]; int
0x1400d524d  call    WPP_RECORDER_SF_Z
0x1400d5252  mov     [rsp+120h+EaLength], r15d; EaLength
0x1400d5257  lea     rax, [rbp+4Fh+Destination]
0x1400d525b  mov     [rsp+120h+EaBuffer], r15; EaBuffer
0x1400d5260  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1400d5264  mov     [rsp+120h+CreateOptions], 20h ; ' '; CreateOptions
0x1400d526c  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1400d5270  mov     [rsp+120h+CreateDisposition], 1; CreateDisposition
0x1400d5278  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400d527c  mov     [rsp+120h+ShareAccess], 1; ShareAccess
0x1400d5284  xorps   xmm0, xmm0
0x1400d5287  mov     [rsp+120h+FileAttributes], r15d; FileAttributes
0x1400d528c  mov     edx, 100001h; DesiredAccess
0x1400d5291  mov     [rsp+120h+AllocationSize], r15; AllocationSize
0x1400d5296  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1400d529d  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], r15
0x1400d52a1  mov     [rbp+4Fh+ObjectAttributes.Attributes], 240h
0x1400d52a8  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1400d52ac  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1400d52b1  call    cs:__imp_ZwCreateFile
0x1400d52b8  nop     dword ptr [rax+rax+00h]
0x1400d52bd  mov     rcx, [rbp+4Fh+Destination.Buffer]; P
0x1400d52c1  xor     edx, edx; Tag
0x1400d52c3  mov     edi, eax
0x1400d52c5  call    cs:__imp_ExFreePoolWithTag
0x1400d52cc  nop     dword ptr [rax+rax+00h]
0x1400d52d1  test    edi, edi
0x1400d52d3  jns     short loc_1400D530E
0x1400d52d5  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400d52dc  jz      short loc_1400D5303
0x1400d52de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d52e5  mov     r9d, 0Ch; int
0x1400d52eb  mov     [rsp+120h+FileAttributes], edi; char
0x1400d52ef  mov     dl, 2; int
0x1400d52f1  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400d52f6  mov     rcx, [rcx+40h]; int
0x1400d52fa  lea     r8d, [r9-0Bh]; int
0x1400d52fe  call    WPP_RECORDER_SF_D
0x1400d5303  mov     dword ptr [rbx], 0C001001Bh
0x1400d5309  jmp     loc_1400D555B
0x1400d530e  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400d5312  lea     r8, [rbp+4Fh+FileInformation]; FileInformation
0x1400d5316  mov     r9d, 18h; Length
0x1400d531c  mov     dword ptr [rsp+120h+AllocationSize], 5; FileInformationClass
0x1400d5324  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1400d5328  call    cs:__imp_ZwQueryInformationFile
0x1400d532f  nop     dword ptr [rax+rax+00h]
0x1400d5334  test    eax, eax
0x1400d5336  jns     short loc_1400D5381
0x1400d5338  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400d533f  jz      short loc_1400D5366
0x1400d5341  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d5348  mov     r9d, 0Dh; int
0x1400d534e  mov     [rsp+120h+FileAttributes], eax; char
0x1400d5352  mov     dl, 2; int
0x1400d5354  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400d5359  mov     rcx, [rcx+40h]; int
0x1400d535d  lea     r8d, [r9-0Ch]; int
0x1400d5361  call    WPP_RECORDER_SF_D
0x1400d5366  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1400d536a  call    cs:__imp_ZwClose
0x1400d5371  nop     dword ptr [rax+rax+00h]
0x1400d5376  mov     dword ptr [rbx], 0C001001Ch
0x1400d537c  jmp     loc_1400D555B
0x1400d5381  mov     esi, dword ptr [rbp+4Fh+FileInformation+8]
0x1400d5384  cmp     esi, 1
0x1400d5387  jnb     short loc_1400D53C9
0x1400d5389  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400d5390  jz      short loc_1400D53C0
0x1400d5392  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d5399  mov     r9d, 0Eh; int
0x1400d539f  mov     [rsp+120h+FileAttributes], esi; char
0x1400d53a3  mov     dl, 2; int
0x1400d53a5  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400d53ac  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400d53b1  mov     rcx, [rcx+40h]; int
0x1400d53b5  lea     r8d, [r9-0Dh]; int
0x1400d53b9  call    WPP_RECORDER_SF_d
0x1400d53be  jmp     short loc_1400D5366
0x1400d53c0  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400d53c7  jmp     short loc_1400D5366
0x1400d53c9  mov     r8d, 6966444Eh
0x1400d53cf  mov     rdx, rsi
0x1400d53d2  mov     ecx, 42h ; 'B'
0x1400d53d7  call    cs:__imp_ExAllocatePool2
0x1400d53de  nop     dword ptr [rax+rax+00h]
0x1400d53e3  mov     r14, rax
0x1400d53e6  test    rax, rax
0x1400d53e9  jnz     short loc_1400D542A
0x1400d53eb  lea     r14, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d53f2  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400d53f9  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400d5400  jz      loc_1400D5366
0x1400d5406  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d540d  lea     r9d, [rax+0Fh]; int
0x1400d5411  lea     r8d, [rax+1]; int
0x1400d5415  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400d541a  mov     dl, 2; int
0x1400d541c  mov     rcx, [rcx+40h]; int
0x1400d5420  call    WPP_RECORDER_SF_
0x1400d5425  jmp     loc_1400D5366
0x1400d542a  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1400d542e  lea     rax, [rbp+4Fh+IoStatusBlock]
0x1400d5432  mov     qword ptr [rsp+120h+CreateOptions], r15; Key
0x1400d5437  xor     r9d, r9d; ApcContext
0x1400d543a  mov     qword ptr [rsp+120h+CreateDisposition], r15; ByteOffset
0x1400d543f  xor     r8d, r8d; ApcRoutine
0x1400d5442  mov     [rsp+120h+ShareAccess], esi; Length
0x1400d5446  xor     edx, edx; Event
0x1400d5448  mov     qword ptr [rsp+120h+FileAttributes], r14; Buffer
0x1400d544d  mov     [rsp+120h+AllocationSize], rax; IoStatusBlock
0x1400d5452  call    cs:__imp_ZwReadFile
0x1400d5459  nop     dword ptr [rax+rax+00h]
0x1400d545e  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1400d5462  mov     r15d, eax
0x1400d5465  call    cs:__imp_ZwClose
0x1400d546c  nop     dword ptr [rax+rax+00h]
0x1400d5471  test    r15d, r15d
0x1400d5474  js      short loc_1400D54EF
0x1400d5476  cmp     [rbp+4Fh+IoStatusBlock.Information], rsi
0x1400d547a  jnz     short loc_1400D54EF
0x1400d547c  mov     edx, 18h
0x1400d5481  mov     r8d, 6466444Eh
0x1400d5487  lea     ecx, [rdx+28h]
0x1400d548a  call    cs:__imp_ExAllocatePool2
0x1400d5491  nop     dword ptr [rax+rax+00h]
0x1400d5496  mov     rdi, rax
0x1400d5499  test    rax, rax
0x1400d549c  jnz     short loc_1400D54C8
0x1400d549e  xor     edx, edx; Tag
0x1400d54a0  mov     dword ptr [rbx], 0C000009Ah
0x1400d54a6  mov     rcx, r14; P
0x1400d54a9  call    cs:__imp_ExFreePoolWithTag
0x1400d54b0  nop     dword ptr [rax+rax+00h]
0x1400d54b5  lea     r14, WPP_RECORDER_INITIALIZED
0x1400d54bc  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400d54c3  jmp     loc_1400D555B
0x1400d54c8  lea     rcx, [rax+8]; SpinLock
0x1400d54cc  mov     [rax], r14
0x1400d54cf  call    cs:__imp_KeInitializeSpinLock
0x1400d54d6  nop     dword ptr [rax+rax+00h]
0x1400d54db  mov     [r12], rdi
0x1400d54df  mov     [r13+0], esi
0x1400d54e3  mov     dword ptr [rbx], 0
0x1400d54e9  mov     byte ptr [rdi+10h], 0
0x1400d54ed  jmp     short loc_1400D54B5
0x1400d54ef  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x1400d54f6  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400d54fd  lea     rsi, WPP_cdc05a73e2a7317b4d5b1bd183068846_Traceguids
0x1400d5504  jz      short loc_1400D552C
0x1400d5506  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d550d  mov     r9d, 10h; int
0x1400d5513  mov     [rsp+120h+FileAttributes], r15d; char
0x1400d5518  mov     dl, 2; int
0x1400d551a  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400d551f  mov     rcx, [rcx+40h]; int
0x1400d5523  lea     r8d, [r9-0Fh]; int
0x1400d5527  call    WPP_RECORDER_SF_D
0x1400d552c  xor     edx, edx; Tag
0x1400d552e  mov     dword ptr [rbx], 0C001001Ch
0x1400d5534  mov     rcx, r14; P
0x1400d5537  call    cs:__imp_ExFreePoolWithTag
0x1400d553e  nop     dword ptr [rax+rax+00h]
0x1400d5543  lea     r14, WPP_RECORDER_INITIALIZED
0x1400d554a  jmp     short loc_1400D555B
0x1400d554c  mov     eax, 0FFFFh
0x1400d5551  mov     dword ptr [rbx], 80000005h
0x1400d5557  mov     [rbp+4Fh+Destination.MaximumLength], ax
0x1400d555b  cmp     cs:WPP_RECORDER_INITIALIZED, r14; __annotation("TMF:",
0x1400d5562  jz      short loc_1400D558B
0x1400d5564  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d556b  mov     r9d, 11h; int
0x1400d5571  mov     eax, [rbx]
0x1400d5573  mov     dl, 4; int
0x1400d5575  mov     [rsp+120h+FileAttributes], eax; char
0x1400d5579  mov     [rsp+120h+AllocationSize], rsi; struct _GUID *
0x1400d557e  mov     rcx, [rcx+40h]; int
0x1400d5582  lea     r8d, [r9-10h]; int
0x1400d5586  call    WPP_RECORDER_SF_D
0x1400d558b  mov     rcx, [rbp+4Fh+var_50]
0x1400d558f  xor     rcx, rsp; StackCookie
0x1400d5592  call    __security_check_cookie
0x1400d5597  add     rsp, 0E8h
0x1400d559e  pop     r15
0x1400d55a0  pop     r14
0x1400d55a2  pop     r13
0x1400d55a4  pop     r12
0x1400d55a6  pop     rdi
0x1400d55a7  pop     rsi
0x1400d55a8  pop     rbx
0x1400d55a9  pop     rbp
0x1400d55aa  retn
```
