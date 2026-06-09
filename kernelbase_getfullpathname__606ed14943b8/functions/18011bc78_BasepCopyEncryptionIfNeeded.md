# BasepCopyEncryptionIfNeeded

- ea: `0x18011bc78`
- end: `0x18011c27f`
- name: `BasepCopyEncryptionIfNeeded`
- size: `1543`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d770c`

## callees

- `0x18004b9d0`
- `0x1800d6840`
- `0x1800d6a90`
- `0x1800eb878`
- `0x18011bc48`
- `0x18011bc78`
- `0x1801373a0`
- `0x18013c160`
- `0x18013c510`
- `0x180194f10`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x18011be09`
- `ntdll!NtSetInformationFile` at `0x18011bf83`
- `ntdll!NtSetInformationFile` at `0x18011be09`
- `ntdll!NtSetInformationFile` at `0x18011bf83`
- `ntdll!NtQueryVolumeInformationFile` at `0x18011c059`
- `ntdll!NtQueryVolumeInformationFile` at `0x18011c059`
- `ntdll!NtCreateFile` at `0x18011bf33`
- `ntdll!NtCreateFile` at `0x18011bf33`
- `ntdll!RtlSetLastWin32Error` at `0x18011bfd0`
- `ntdll!RtlSetLastWin32Error` at `0x18011bfd0`
- `ntdll!NtClose` at `0x18011be3e`
- `ntdll!NtClose` at `0x18011be3e`
- `ext-ms-win-kernel32-file-l1-1-0!BasepCopyEncryption` at `0x18011bec9`
- `ext-ms-win-kernel32-file-l1-1-0!BasepCopyEncryption` at `0x18011bec9`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x18011be6d`
- `ext-ms-win-feclient-encryptedfile-l1-1-0!EfsClientDecryptFile` at `0x18011be6d`
- `ext-ms-win-security-efswrt-l1-1-0!ProtectFileToIdentity` at `0x18011be9c`
- `ext-ms-win-security-efswrt-l1-1-0!ProtectFileToIdentity` at `0x18011be9c`

## pseudocode

```c
__int64 __fastcall BasepCopyEncryptionIfNeeded(
        __int64 a1,
        __int64 a2,
        HANDLE *a3,
        struct _OBJECT_ATTRIBUTES *a4,
        ACCESS_MASK DesiredAccess,
        ULONG ShareAccess,
        ULONG CreateOptions,
        int a8,
        int a9,
        _BYTE *a10,
        int a11,
        __int16 a12,
        int a13,
        __int64 a14,
        int a15,
        __int64 *a16,
        int a17,
        GUID *a18)
{
  _DWORD *v19; // r15
  unsigned int v20; // ebx
  int v21; // r8d
  int v22; // ecx
  __int64 v23; // r13
  int v24; // r10d
  int v25; // r9d
  int v26; // eax
  int v27; // eax
  NTSTATUS v28; // r15d
  __int64 v29; // rcx
  int v30; // eax
  NTSTATUS v31; // eax
  _BYTE *v32; // r15
  unsigned int v33; // eax
  int v35; // [rsp+60h] [rbp-158h]
  int v36; // [rsp+64h] [rbp-154h]
  int v37; // [rsp+6Ch] [rbp-14Ch] BYREF
  int v38; // [rsp+70h] [rbp-148h] BYREF
  int v39; // [rsp+74h] [rbp-144h] BYREF
  int v40; // [rsp+78h] [rbp-140h] BYREF
  unsigned int v41; // [rsp+7Ch] [rbp-13Ch] BYREF
  __int64 FsInformation; // [rsp+80h] [rbp-138h] BYREF
  unsigned int v43; // [rsp+88h] [rbp-130h]
  int v44; // [rsp+8Ch] [rbp-12Ch]
  int v45; // [rsp+90h] [rbp-128h]
  _DWORD *v46; // [rsp+98h] [rbp-120h]
  int v47; // [rsp+A0h] [rbp-118h]
  __int64 v48; // [rsp+A8h] [rbp-110h]
  POBJECT_ATTRIBUTES ObjectAttributes[2]; // [rsp+B0h] [rbp-108h] BYREF
  __int64 v50; // [rsp+C0h] [rbp-F8h]
  LPGUID ActivityId; // [rsp+C8h] [rbp-F0h]
  GUID *v52; // [rsp+D0h] [rbp-E8h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+D8h] [rbp-E0h] BYREF
  _OWORD FileInformation[2]; // [rsp+E8h] [rbp-D0h] BYREF
  __int64 v55; // [rsp+108h] [rbp-B0h]
  char v56[32]; // [rsp+110h] [rbp-A8h] BYREF
  int *v57; // [rsp+130h] [rbp-88h]
  __int64 v58; // [rsp+138h] [rbp-80h]
  int *v59; // [rsp+140h] [rbp-78h]
  __int64 v60; // [rsp+148h] [rbp-70h]
  int *v61; // [rsp+150h] [rbp-68h]
  __int64 v62; // [rsp+158h] [rbp-60h]
  int *v63; // [rsp+160h] [rbp-58h]
  __int64 v64; // [rsp+168h] [rbp-50h]
  unsigned int *v65; // [rsp+170h] [rbp-48h]
  __int64 v66; // [rsp+178h] [rbp-40h]

  ObjectAttributes[0] = a4;
  FsInformation = a2;
  v50 = a1;
  v19 = a10;
  v46 = a10;
  v48 = a14;
  ActivityId = a18;
  v52 = a18;
  v20 = 0;
  v21 = 0;
  v43 = 0;
  v22 = 0;
  v44 = 0;
  IoStatusBlock = 0;
  v23 = *a16;
  memset(FileInformation, 0, sizeof(FileInformation));
  v55 = 0;
  v24 = 0;
  v35 = 0;
  v25 = 0;
  v36 = 0;
  v26 = a8 & 0x4000;
  v45 = v26;
  if ( (a8 & 0x4000) != 0 && (a9 & 0x4000) != 0 && (*(_DWORD *)a10 & 0x4000) == 0 )
  {
    if ( (a8 & 0x10) != 0 && (*a10 & 4) == 0 )
    {
      v21 = 1;
      v43 = 1;
    }
  }
  else if ( (a8 & 0x4000) == 0 && (*(_DWORD *)a10 & 0x4000) != 0 && (a12 & 0x200) != 0 )
  {
    v22 = 1;
  }
  if ( a13 == 3 || v22 || v21 )
  {
    v27 = *(_DWORD *)a10;
    if ( (*(_DWORD *)a10 & 1) != 0 )
    {
      v44 = 1;
      LODWORD(v55) = v27 & 0xFFFFFFFE;
      v28 = NtSetInformationFile(*a3, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      if ( v28 < 0 )
        goto LABEL_16;
      v19 = v46;
    }
    NtClose(*a3);
    *a3 = (HANDLE)-1LL;
    if ( a13 == 3 )
    {
      if ( (*v19 & 0x4000) != 0 )
      {
        v30 = EfsClientDecryptFile(FsInformation, 0);
        v36 = v30;
        v47 = v30;
      }
      else
      {
        v30 = 0;
      }
      if ( !v30 )
        v35 = ProtectFileToIdentity(FsInformation, v48, 1);
    }
    else if ( (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() )
    {
      BasepCopyEncryption(FsInformation, v43, v19);
    }
    v31 = NtCreateFile(
            a3,
            DesiredAccess,
            ObjectAttributes[0],
            &IoStatusBlock,
            0,
            a9 & a8 & 0xDAFFB7,
            ShareAccess,
            1u,
            CreateOptions,
            0,
            0);
    if ( v31 < 0 )
    {
      *a3 = (HANDLE)-1LL;
      v29 = (unsigned int)v31;
      goto LABEL_17;
    }
    if ( v44 )
    {
      LODWORD(v55) = v55 | 1;
      v28 = NtSetInformationFile(*a3, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      if ( v28 < 0 )
      {
LABEL_16:
        BaseMarkFileForDelete(*a3);
        v29 = (unsigned int)v28;
LABEL_17:
        BaseSetLastNTError(v29);
        goto LABEL_57;
      }
    }
    v24 = v35;
    v25 = v36;
    v26 = v45;
  }
  if ( a13 == 3 && (v25 || v24 < 0) )
    goto LABEL_35;
  if ( a13 )
    goto LABEL_56;
  if ( !v26 )
    goto LABEL_56;
  v32 = v46;
  if ( (*v46 & 0x4000) != 0 || (a12 & 8) != 0 )
    goto LABEL_56;
  if ( (unsigned int)CheckAllowDecryptedRemoteDestinationPolicy() )
  {
    *(_OWORD *)ObjectAttributes = 0;
    FsInformation = 0;
    if ( NtQueryVolumeInformationFile(
           *a3,
           (PIO_STATUS_BLOCK)ObjectAttributes,
           &FsInformation,
           8u,
           FileFsDeviceInformation) >= 0
      && (FsInformation & 0x1000000000LL) != 0 )
    {
      v20 = 1;
    }
  }
  if ( v20 )
    goto LABEL_56;
  if ( v23 && *(_QWORD *)(v23 + 144) && (a12 & 0x10) != 0 )
  {
    if ( (a11 & 0x20000) != 0 )
      v33 = (a9 & 0x4000) != 0 ? ((*v32 & 4) != 0 ? 21 : 12) : 12;
    else
      v33 = 11;
    *(_DWORD *)(v23 + 20) = 0;
    *(_DWORD *)(v23 + 24) = 6000;
    *(_QWORD *)(v23 + 64) = 0;
    *(_QWORD *)(v23 + 32) = v50;
    *(_QWORD *)(v23 + 40) = a3;
    if ( (unsigned int)BasepCopyFileCallback(v33) )
      v20 = 1;
  }
  if ( v20 )
  {
LABEL_56:
    v20 = 1;
  }
  else
  {
LABEL_35:
    BaseMarkFileForDelete(*a3);
    RtlSetLastWin32Error(0x1770u);
  }
LABEL_57:
  if ( (unsigned int)(a13 - 2) <= 1 || a15 )
  {
    if ( ActivityId && !ActivityId[2].Data1 )
      BasepBaseCopyStreamStartActivity(ActivityId);
    if ( (unsigned int)dword_1803A4C08 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1803A4C08, 0x400000000000LL) )
    {
      v37 = a13;
      v57 = &v37;
      v58 = 4;
      v38 = v35;
      v59 = &v38;
      v60 = 4;
      v39 = a17;
      v61 = &v39;
      v62 = 4;
      v40 = a15;
      v63 = &v40;
      v64 = 4;
      v41 = v20;
      v65 = &v41;
      v66 = 4;
      tlgWriteTransfer_EventWriteTransfer(&dword_1803A4C08, &word_1803609AE, 0, 0, 7, v56);
    }
  }
  return v20;
}

```

## disassembly

```asm
0x18011bc78  mov     [rsp+arg_0], rbx
0x18011bc7d  push    rdi
0x18011bc7e  push    r12
0x18011bc80  push    r13
0x18011bc82  push    r14
0x18011bc84  push    r15
0x18011bc86  sub     rsp, 190h
0x18011bc8d  mov     rax, cs:__security_cookie
0x18011bc94  xor     rax, rsp
0x18011bc97  mov     [rsp+1B8h+var_38], rax
0x18011bc9f  mov     [rsp+1B8h+ObjectAttributes], r9
0x18011bca7  mov     r14, r8
0x18011bcaa  mov     [rsp+1B8h+FsInformation], rdx
0x18011bcb2  mov     [rsp+1B8h+var_F8], rcx
0x18011bcba  mov     r15, [rsp+1B8h+arg_48]
0x18011bcc2  mov     [rsp+1B8h+var_120], r15
0x18011bcca  mov     rax, [rsp+1B8h+arg_68]
0x18011bcd2  mov     [rsp+1B8h+var_110], rax
0x18011bcda  mov     rax, [rsp+1B8h+arg_78]
0x18011bce2  mov     rcx, [rsp+1B8h+arg_88]
0x18011bcea  mov     [rsp+1B8h+ActivityId], rcx
0x18011bcf2  mov     [rsp+1B8h+var_E8], rcx
0x18011bcfa  xor     ebx, ebx
0x18011bcfc  mov     [rsp+1B8h+var_150], ebx
0x18011bd00  xor     r8d, r8d
0x18011bd03  mov     [rsp+1B8h+var_130], r8d
0x18011bd0b  xor     ecx, ecx
0x18011bd0d  mov     [rsp+1B8h+var_12C], ecx
0x18011bd14  xorps   xmm0, xmm0
0x18011bd17  movups  xmmword ptr [rsp+1B8h+IoStatusBlock], xmm0
0x18011bd1f  mov     r13, [rax]
0x18011bd22  xorps   xmm1, xmm1
0x18011bd25  xor     eax, eax
0x18011bd27  movups  [rsp+1B8h+FileInformation], xmm1
0x18011bd2f  movups  [rsp+1B8h+var_C0], xmm1
0x18011bd37  mov     [rsp+1B8h+var_B0], rax
0x18011bd3f  xor     r10d, r10d
0x18011bd42  mov     [rsp+1B8h+var_158], r10d
0x18011bd47  xor     r9d, r9d
0x18011bd4a  mov     [rsp+1B8h+var_154], r9d
0x18011bd4f  mov     edx, [rsp+1B8h+arg_38]
0x18011bd56  mov     eax, edx
0x18011bd58  mov     r11d, 4000h
0x18011bd5e  and     eax, r11d
0x18011bd61  mov     [rsp+1B8h+var_128], eax
0x18011bd68  jz      short loc_18011BD93
0x18011bd6a  test    [rsp+1B8h+arg_40], r11d
0x18011bd72  jz      short loc_18011BD93
0x18011bd74  test    [r15], r11d
0x18011bd77  jnz     short loc_18011BD93
0x18011bd79  lea     edi, [rbx+1]
0x18011bd7c  test    dl, 10h
0x18011bd7f  jz      short loc_18011BDB4
0x18011bd81  test    byte ptr [r15], 4
0x18011bd85  jnz     short loc_18011BDB4
0x18011bd87  mov     r8d, edi
0x18011bd8a  mov     [rsp+1B8h+var_130], edi
0x18011bd91  jmp     short loc_18011BDB4
0x18011bd93  test    eax, eax
0x18011bd95  jnz     short loc_18011BDAF
0x18011bd97  test    [r15], r11d
0x18011bd9a  jz      short loc_18011BDAF
0x18011bd9c  test    dword ptr [rsp+1B8h+arg_58], 200h
0x18011bda7  lea     edi, [rax+1]
0x18011bdaa  cmovnz  ecx, edi
0x18011bdad  jmp     short loc_18011BDB4
0x18011bdaf  mov     edi, 1
0x18011bdb4  mov     r12d, [rsp+1B8h+arg_60]
0x18011bdbc  cmp     r12d, 3
0x18011bdc0  jz      short loc_18011BDCF
0x18011bdc2  test    ecx, ecx
0x18011bdc4  jnz     short loc_18011BDCF
0x18011bdc6  test    r8d, r8d
0x18011bdc9  jz      loc_18011BFB1
0x18011bdcf  mov     eax, [r15]
0x18011bdd2  test    dil, al
0x18011bdd5  jz      short loc_18011BE3B
0x18011bdd7  mov     [rsp+1B8h+var_12C], edi
0x18011bdde  and     eax, 0FFFFFFFEh
0x18011bde1  mov     dword ptr [rsp+1B8h+var_B0], eax
0x18011bde8  mov     [rsp+1B8h+FileInformationClass], 4; FileInformationClass
0x18011bdf0  mov     r9d, 28h ; '('; Length
0x18011bdf6  lea     r8, [rsp+1B8h+FileInformation]; FileInformation
0x18011bdfe  lea     rdx, [rsp+1B8h+IoStatusBlock]; IoStatusBlock
0x18011be06  mov     rcx, [r14]; FileHandle
0x18011be09  call    cs:__imp_NtSetInformationFile
0x18011be10  nop     dword ptr [rax+rax+00h]
0x18011be15  mov     r15d, eax
0x18011be18  test    eax, eax
0x18011be1a  jns     short loc_18011BE33
0x18011be1c  xor     edx, edx
0x18011be1e  mov     rcx, [r14]; FileHandle
0x18011be21  call    BaseMarkFileForDelete
0x18011be26  mov     ecx, r15d
0x18011be29  call    BaseSetLastNTError
0x18011be2e  jmp     loc_18011C11F
0x18011be33  mov     r15, [rsp+1B8h+var_120]
0x18011be3b  mov     rcx, [r14]; Handle
0x18011be3e  call    cs:__imp_NtClose
0x18011be45  nop     dword ptr [rax+rax+00h]
0x18011be4a  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18011be51  cmp     r12d, 3
0x18011be55  jnz     short loc_18011BEAE
0x18011be57  test    dword ptr [r15], 4000h
0x18011be5e  mov     r15, [rsp+1B8h+FsInformation]
0x18011be66  jz      short loc_18011BE86
0x18011be68  xor     edx, edx
0x18011be6a  mov     rcx, r15
0x18011be6d  call    cs:__imp_EfsClientDecryptFile
0x18011be74  nop     dword ptr [rax+rax+00h]
0x18011be79  mov     [rsp+1B8h+var_154], eax
0x18011be7d  mov     [rsp+1B8h+var_118], eax
0x18011be84  jmp     short loc_18011BE8A
0x18011be86  mov     eax, [rsp+1B8h+var_154]
0x18011be8a  test    eax, eax
0x18011be8c  jnz     short loc_18011BED5
0x18011be8e  mov     r8d, edi
0x18011be91  mov     rdx, [rsp+1B8h+var_110]
0x18011be99  mov     rcx, r15
0x18011be9c  call    cs:__imp_ProtectFileToIdentity
0x18011bea3  nop     dword ptr [rax+rax+00h]
0x18011bea8  mov     [rsp+1B8h+var_158], eax
0x18011beac  jmp     short loc_18011BED5
0x18011beae  call    IsBasepGetComputerNameFromNtPathPresent
0x18011beb3  test    al, al
0x18011beb5  jz      short loc_18011BED5
0x18011beb7  mov     r8, r15
0x18011beba  mov     edx, [rsp+1B8h+var_130]
0x18011bec1  mov     rcx, [rsp+1B8h+FsInformation]
0x18011bec9  call    cs:__imp_BasepCopyEncryption
0x18011bed0  nop     dword ptr [rax+rax+00h]
0x18011bed5  mov     ecx, [rsp+1B8h+arg_38]
0x18011bedc  and     ecx, [rsp+1B8h+arg_40]
0x18011bee3  and     ecx, 0DAFFB7h
0x18011bee9  xor     r15d, r15d
0x18011beec  mov     [rsp+1B8h+EaLength], r15d; EaLength
0x18011bef1  mov     [rsp+1B8h+EaBuffer], r15; EaBuffer
0x18011bef6  mov     eax, [rsp+1B8h+arg_30]
0x18011befd  mov     [rsp+1B8h+CreateOptions], eax; CreateOptions
0x18011bf01  mov     [rsp+1B8h+CreateDisposition], edi; CreateDisposition
0x18011bf05  mov     eax, [rsp+1B8h+arg_28]
0x18011bf0c  mov     [rsp+1B8h+ShareAccess], eax; ShareAccess
0x18011bf10  mov     [rsp+1B8h+FileAttributes], ecx; FileAttributes
0x18011bf14  mov     qword ptr [rsp+1B8h+FileInformationClass], r15; AllocationSize
0x18011bf19  lea     r9, [rsp+1B8h+IoStatusBlock]; IoStatusBlock
0x18011bf21  mov     r8, [rsp+1B8h+ObjectAttributes]; ObjectAttributes
0x18011bf29  mov     edx, [rsp+1B8h+DesiredAccess]; DesiredAccess
0x18011bf30  mov     rcx, r14; FileHandle
0x18011bf33  call    cs:__imp_NtCreateFile
0x18011bf3a  nop     dword ptr [rax+rax+00h]
0x18011bf3f  test    eax, eax
0x18011bf41  jns     short loc_18011BF51
0x18011bf43  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x18011bf4a  mov     ecx, eax
0x18011bf4c  jmp     loc_18011BE29
0x18011bf51  cmp     [rsp+1B8h+var_12C], r15d
0x18011bf59  jz      short loc_18011BF9A
0x18011bf5b  or      dword ptr [rsp+1B8h+var_B0], edi
0x18011bf62  mov     [rsp+1B8h+FileInformationClass], 4; FileInformationClass
0x18011bf6a  mov     r9d, 28h ; '('; Length
0x18011bf70  lea     r8, [rsp+1B8h+FileInformation]; FileInformation
0x18011bf78  lea     rdx, [rsp+1B8h+IoStatusBlock]; IoStatusBlock
0x18011bf80  mov     rcx, [r14]; FileHandle
0x18011bf83  call    cs:__imp_NtSetInformationFile
0x18011bf8a  nop     dword ptr [rax+rax+00h]
0x18011bf8f  mov     r15d, eax
0x18011bf92  test    eax, eax
0x18011bf94  js      loc_18011BE1C
0x18011bf9a  mov     r11d, 4000h
0x18011bfa0  mov     r10d, [rsp+1B8h+var_158]
0x18011bfa5  mov     r9d, [rsp+1B8h+var_154]
0x18011bfaa  mov     eax, [rsp+1B8h+var_128]
0x18011bfb1  cmp     r12d, 3
0x18011bfb5  jnz     short loc_18011BFE1
0x18011bfb7  test    r9d, r9d
0x18011bfba  jnz     short loc_18011BFC1
0x18011bfbc  test    r10d, r10d
0x18011bfbf  jns     short loc_18011BFE1
0x18011bfc1  xor     edx, edx
0x18011bfc3  mov     rcx, [r14]; FileHandle
0x18011bfc6  call    BaseMarkFileForDelete
0x18011bfcb  mov     ecx, 1770h; LastError
0x18011bfd0  call    cs:__imp_RtlSetLastWin32Error
0x18011bfd7  nop     dword ptr [rax+rax+00h]
0x18011bfdc  jmp     loc_18011C11F
0x18011bfe1  test    r12d, r12d
0x18011bfe4  jnz     loc_18011C119
0x18011bfea  test    eax, eax
0x18011bfec  jz      loc_18011C119
0x18011bff2  mov     r15, [rsp+1B8h+var_120]
0x18011bffa  test    [r15], r11d
0x18011bffd  jnz     loc_18011C119
0x18011c003  test    byte ptr [rsp+1B8h+arg_58], 8
0x18011c00b  jnz     loc_18011C119
0x18011c011  call    CheckAllowDecryptedRemoteDestinationPolicy
0x18011c016  test    eax, eax
0x18011c018  jz      short loc_18011C078
0x18011c01a  xorps   xmm0, xmm0
0x18011c01d  movups  xmmword ptr [rsp+1B8h+ObjectAttributes], xmm0
0x18011c025  mov     [rsp+1B8h+FsInformation], 0
0x18011c031  mov     dword ptr [rsp+1B8h+FsInformation+4], r12d
0x18011c039  mov     [rsp+1B8h+FileInformationClass], 4; FsInformationClass
0x18011c041  lea     r9d, [r12+8]; Length
0x18011c046  lea     r8, [rsp+1B8h+FsInformation]; FsInformation
0x18011c04e  lea     rdx, [rsp+1B8h+ObjectAttributes]; IoStatusBlock
0x18011c056  mov     rcx, [r14]; FileHandle
0x18011c059  call    cs:__imp_NtQueryVolumeInformationFile
0x18011c060  nop     dword ptr [rax+rax+00h]
0x18011c065  test    eax, eax
0x18011c067  js      short loc_18011C078
0x18011c069  test    byte ptr [rsp+1B8h+FsInformation+4], 10h
0x18011c071  cmovnz  ebx, edi
0x18011c074  mov     [rsp+1B8h+var_150], ebx
0x18011c078  test    ebx, ebx
0x18011c07a  jnz     loc_18011C119
0x18011c080  test    r13, r13
0x18011c083  jz      loc_18011C111
0x18011c089  cmp     qword ptr [r13+90h], 0
0x18011c091  jz      short loc_18011C111
0x18011c093  test    byte ptr [rsp+1B8h+arg_58], 10h
0x18011c09b  jz      short loc_18011C111
0x18011c09d  test    [rsp+1B8h+arg_50], 20000h
0x18011c0a8  jz      short loc_18011C0D1
0x18011c0aa  test    [rsp+1B8h+arg_40], 4000h
0x18011c0b5  jnz     short loc_18011C0BC
0x18011c0b7  lea     eax, [rbx+0Ch]
0x18011c0ba  jmp     short loc_18011C0D6
0x18011c0bc  mov     al, [r15]
0x18011c0bf  and     al, 4
0x18011c0c1  neg     al
0x18011c0c3  sbb     ecx, ecx
0x18011c0c5  and     ecx, 9
0x18011c0c8  mov     eax, 0Ch
0x18011c0cd  add     eax, ecx
0x18011c0cf  jmp     short loc_18011C0D6
0x18011c0d1  mov     eax, 0Bh
0x18011c0d6  mov     dword ptr [r13+14h], 0
0x18011c0de  mov     dword ptr [r13+18h], 1770h
0x18011c0e6  mov     qword ptr [r13+40h], 0
0x18011c0ee  mov     rcx, [rsp+1B8h+var_F8]
0x18011c0f6  mov     [r13+20h], rcx
0x18011c0fa  mov     [r13+28h], r14
0x18011c0fe  mov     rdx, r13
0x18011c101  mov     ecx, eax
0x18011c103  call    BasepCopyFileCallback
0x18011c108  test    eax, eax
0x18011c10a  cmovnz  ebx, edi
0x18011c10d  mov     [rsp+1B8h+var_150], ebx
0x18011c111  test    ebx, ebx
0x18011c113  jz      loc_18011BFC1
0x18011c119  mov     ebx, edi
0x18011c11b  mov     [rsp+1B8h+var_150], ebx
0x18011c11f  lea     eax, [r12-2]
0x18011c124  xor     r8d, r8d
0x18011c127  cmp     eax, edi
0x18011c129  jbe     short loc_18011C139
0x18011c12b  cmp     [rsp+1B8h+arg_70], r8d
0x18011c133  jz      loc_18011C253
0x18011c139  mov     rax, [rsp+1B8h+ActivityId]
0x18011c141  test    rax, rax
0x18011c144  jz      short loc_18011C154
0x18011c146  cmp     [rax+20h], r8d
0x18011c14a  jnz     short loc_18011C154
0x18011c14c  mov     rcx, rax; ActivityId
0x18011c14f  call    BasepBaseCopyStreamStartActivity
0x18011c154  mov     eax, cs:dword_1803A4C08
0x18011c15a  cmp     eax, 5
0x18011c15d  jbe     loc_18011C253
0x18011c163  mov     rdx, 400000000000h
0x18011c16d  lea     rcx, dword_1803A4C08
0x18011c174  call    _tlgKeywordOn
0x18011c179  test    al, al
0x18011c17b  jz      loc_18011C253
0x18011c181  mov     [rsp+1B8h+var_14C], r12d
0x18011c186  lea     rax, [rsp+1B8h+var_14C]
0x18011c18b  mov     [rsp+1B8h+var_88], rax
0x18011c193  mov     [rsp+1B8h+var_80], 4
0x18011c19f  mov     eax, [rsp+1B8h+var_158]
0x18011c1a3  mov     [rsp+1B8h+var_148], eax
0x18011c1a7  lea     rax, [rsp+1B8h+var_148]
0x18011c1ac  mov     [rsp+1B8h+var_78], rax
0x18011c1b4  mov     [rsp+1B8h+var_70], 4
0x18011c1c0  mov     eax, [rsp+1B8h+arg_80]
0x18011c1c7  mov     [rsp+1B8h+var_144], eax
0x18011c1cb  lea     rax, [rsp+1B8h+var_144]
0x18011c1d0  mov     [rsp+1B8h+var_68], rax
0x18011c1d8  mov     [rsp+1B8h+var_60], 4
0x18011c1e4  mov     eax, [rsp+1B8h+arg_70]
0x18011c1eb  mov     [rsp+1B8h+var_140], eax
0x18011c1ef  lea     rax, [rsp+1B8h+var_140]
0x18011c1f4  mov     [rsp+1B8h+var_58], rax
0x18011c1fc  mov     [rsp+1B8h+var_50], 4
0x18011c208  mov     [rsp+1B8h+var_13C], ebx
0x18011c20c  lea     rax, [rsp+1B8h+var_13C]
0x18011c211  mov     [rsp+1B8h+var_48], rax
0x18011c219  mov     [rsp+1B8h+var_40], 4
0x18011c225  lea     rax, [rsp+1B8h+var_A8]
0x18011c22d  mov     qword ptr [rsp+1B8h+FileAttributes], rax
0x18011c232  mov     [rsp+1B8h+FileInformationClass], 7
0x18011c23a  xor     r9d, r9d
  ... truncated ...
```
