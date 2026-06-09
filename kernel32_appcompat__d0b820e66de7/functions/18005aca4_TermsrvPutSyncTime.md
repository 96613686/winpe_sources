# TermsrvPutSyncTime

- ea: `0x18005aca4`
- end: `0x18005b1ab`
- name: `TermsrvPutSyncTime`
- size: `1287`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800532f0`

## callees

- `0x180036654`
- `0x18005aca4`
- `0x180061d70`
- `0x1800827c0`

## import_xrefs

- `ntdll!RtlAppendUnicodeToString` at `0x18005ad79`
- `ntdll!RtlAppendUnicodeToString` at `0x18005ad79`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005ad5a`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18005ad5a`
- `ntdll!NtWaitForSingleObject` at `0x18005af3e`
- `ntdll!NtWaitForSingleObject` at `0x18005b0f5`
- `ntdll!NtWaitForSingleObject` at `0x18005af3e`
- `ntdll!NtWaitForSingleObject` at `0x18005b0f5`
- `ntdll!NtClose` at `0x18005b170`
- `ntdll!NtClose` at `0x18005b170`
- `ntdll!wcslen` at `0x18005af8d`
- `ntdll!wcslen` at `0x18005afb2`
- `ntdll!wcslen` at `0x18005af8d`
- `ntdll!wcslen` at `0x18005afb2`
- `ntdll!NtQueryInformationFile` at `0x18005ae25`
- `ntdll!NtQueryInformationFile` at `0x18005ae25`
- `ntdll!NtSetInformationFile` at `0x18005b096`
- `ntdll!NtSetInformationFile` at `0x18005b131`
- `ntdll!NtSetInformationFile` at `0x18005b096`
- `ntdll!NtSetInformationFile` at `0x18005b131`
- `ntdll!NtCreateFile` at `0x18005adf4`
- `ntdll!NtCreateFile` at `0x18005adf4`
- `ntdll!NtFreeVirtualMemory` at `0x18005b15a`
- `ntdll!NtFreeVirtualMemory` at `0x18005b15a`
- `ntdll!NtWriteFile` at `0x18005b0d6`
- `ntdll!NtWriteFile` at `0x18005b0d6`
- `ntdll!NtReadFile` at `0x18005af1f`
- `ntdll!NtReadFile` at `0x18005af1f`
- `ntdll!NtAllocateVirtualMemory` at `0x18005aea1`
- `ntdll!NtAllocateVirtualMemory` at `0x18005aed4`
- `ntdll!NtAllocateVirtualMemory` at `0x18005b013`
- `ntdll!NtAllocateVirtualMemory` at `0x18005aea1`
- `ntdll!NtAllocateVirtualMemory` at `0x18005aed4`
- `ntdll!NtAllocateVirtualMemory` at `0x18005b013`
- `ntdll!_wcsicmp` at `0x18005af78`
- `ntdll!_wcsicmp` at `0x18005af78`

## pseudocode

```c
int __fastcall TermsrvPutSyncTime(const wchar_t **a1, const UNICODE_STRING *a2, _DWORD *a3)
{
  int result; // eax
  NTSTATUS Status; // ebx
  NTSTATUS v7; // eax
  unsigned int v8; // eax
  wchar_t *v9; // rdi
  wchar_t *v10; // rsi
  int v11; // ebx
  size_t v12; // rax
  unsigned __int64 v13; // r14
  unsigned __int64 v14; // r11
  PVOID BaseAddress; // [rsp+60h] [rbp-A0h] BYREF
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG_PTR v17; // [rsp+70h] [rbp-90h] BYREF
  ULONG_PTR RegionSize; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-80h] BYREF
  __int64 v20; // [rsp+90h] [rbp-70h] BYREF
  __int64 v21; // [rsp+98h] [rbp-68h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+A0h] [rbp-60h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  __int128 FileInformation; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v25; // [rsp+F0h] [rbp-10h]
  char v26; // [rsp+100h] [rbp+0h] BYREF

  *(_QWORD *)&Destination.Length = 34209792;
  FileHandle = 0;
  BaseAddress = 0;
  v25 = 0;
  Destination.Buffer = (PWSTR)&v26;
  v17 = 0;
  RegionSize = 0;
  v21 = 0;
  v20 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( !a1 )
    return -1073741585;
  if ( !a2 )
    return -1073741584;
  if ( !a3 )
    return -1073741583;
  result = RtlAppendUnicodeStringToString(&Destination, a2);
  if ( result >= 0 )
  {
    result = RtlAppendUnicodeToString(&Destination, L"\\inifile.upd");
    if ( result >= 0 )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &Destination;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      IoStatusBlock.Status = 0;
      Status = NtCreateFile(&FileHandle, 0x100083u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 2u, 3u, 0x60u, 0, 0);
      if ( Status < 0 )
        goto LABEL_39;
      v7 = NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
      Status = v7;
      if ( v7 != -2147483643 && v7 < 0 )
        goto LABEL_39;
      v17 = DWORD2(FileInformation);
      if ( (unsigned __int64)DWORD2(FileInformation) + 8 <= DWORD2(FileInformation) )
        goto LABEL_13;
      v17 = DWORD2(FileInformation) + 8LL;
      RegionSize = v17;
      if ( (unsigned __int64)DWORD2(FileInformation) + 4104 < v17 )
        goto LABEL_13;
      RegionSize = DWORD2(FileInformation) + 4104LL;
      Status = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &RegionSize, 0x2000u, 4u);
      if ( Status < 0 )
        goto LABEL_39;
      Status = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &v17, 0x1000u, 4u);
      if ( Status < 0 )
        goto LABEL_39;
      v8 = DWORD2(FileInformation);
      if ( DWORD2(FileInformation) )
      {
        Status = NtReadFile(FileHandle, 0, 0, 0, &IoStatusBlock, BaseAddress, DWORD2(FileInformation), 0, 0);
        if ( Status == 259 )
          Status = NtWaitForSingleObject(FileHandle, 0, 0);
        if ( Status < 0 )
          goto LABEL_39;
        Status = IoStatusBlock.Status;
        if ( IoStatusBlock.Status < 0 )
          goto LABEL_39;
        v8 = DWORD2(FileInformation);
      }
      v9 = (wchar_t *)BaseAddress;
      v10 = (wchar_t *)((char *)BaseAddress + v8);
      if ( BaseAddress < v10 )
      {
        do
        {
          v11 = _wcsicmp(v9, a1[1]);
          if ( v11 >= 0 )
            break;
          v9 += wcslen(v9) + 5;
        }
        while ( v9 < v10 );
        if ( v9 < v10 && !v11 )
        {
          v12 = wcslen(v9);
          *(_DWORD *)&v9[v12 + 1] = *a3;
          *(_DWORD *)&v9[v12 + 3] = a3[1];
LABEL_34:
          v20 = 0;
          NtSetInformationFile(FileHandle, &IoStatusBlock, &v20, 8u, FilePositionInformation);
          Status = NtWriteFile(
                     FileHandle,
                     0,
                     0,
                     0,
                     &IoStatusBlock,
                     BaseAddress,
                     (_DWORD)v10 - (_DWORD)BaseAddress + 1,
                     0,
                     0);
          if ( Status == 259 )
            Status = NtWaitForSingleObject(FileHandle, 0, 0);
          if ( Status >= 0 )
          {
            Status = IoStatusBlock.Status;
            if ( IoStatusBlock.Status >= 0 )
            {
              v21 = (unsigned int)((_DWORD)v10 - (_DWORD)BaseAddress);
              Status = NtSetInformationFile(FileHandle, &IoStatusBlock, &v21, 8u, FileEndOfFileInformation);
            }
          }
          goto LABEL_39;
        }
      }
      v13 = *(unsigned __int16 *)a1 + 10LL;
      if ( v13 + v17 < v17 )
      {
LABEL_13:
        Status = -1073741582;
      }
      else
      {
        v17 += v13;
        Status = NtAllocateVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, 0, &v17, 0x1000u, 4u);
        if ( Status >= 0 )
        {
          if ( v9 < v10 )
            memmove_0(&v9[v13 >> 1], v9, (char *)v10 - (char *)v9);
          LODWORD(v10) = v13 + (_DWORD)v10;
          StringCbCopyW(v9, v13 - 8, a1[1]);
          v14 = ((unsigned __int64)*(unsigned __int16 *)a1 + 2) >> 1;
          *(_DWORD *)&v9[v14] = *a3;
          *(_DWORD *)&v9[v14 + 2] = a3[1];
          goto LABEL_34;
        }
      }
LABEL_39:
      if ( BaseAddress )
        NtFreeVirtualMemory((HANDLE)0xFFFFFFFFFFFFFFFFLL, &BaseAddress, &RegionSize, 0x8000u);
      if ( FileHandle )
        return NtClose(FileHandle);
      return Status;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18005aca4  mov     [rsp-8+arg_10], rbx
0x18005aca9  push    rbp
0x18005acaa  push    rsi
0x18005acab  push    rdi
0x18005acac  push    r12
0x18005acae  push    r13
0x18005acb0  push    r14
0x18005acb2  push    r15
0x18005acb4  lea     rbp, [rsp-220h]
0x18005acbc  sub     rsp, 320h
0x18005acc3  mov     rax, cs:__security_cookie
0x18005acca  xor     rax, rsp
0x18005accd  mov     [rbp+250h+var_40], rax
0x18005acd4  xor     r12d, r12d
0x18005acd7  mov     qword ptr [rbp+250h+Destination.Length], 20A0000h
0x18005acdf  xorps   xmm0, xmm0
0x18005ace2  mov     [rsp+350h+FileHandle], r12
0x18005ace7  xor     eax, eax
0x18005ace9  mov     [rsp+350h+BaseAddress], r12
0x18005acee  mov     [rbp+250h+var_260], rax
0x18005acf2  lea     rax, [rbp+250h+var_250]
0x18005acf6  mov     [rbp+250h+Destination.Buffer], rax
0x18005acfa  xorps   xmm1, xmm1
0x18005acfd  mov     [rsp+350h+var_2E0], r12
0x18005ad02  mov     r15, r8
0x18005ad05  mov     [rsp+350h+RegionSize], r12
0x18005ad0a  mov     r13, rcx
0x18005ad0d  mov     [rbp+250h+var_2B8], r12
0x18005ad11  mov     [rbp+250h+var_2C0], r12
0x18005ad15  movups  xmmword ptr [rbp+250h+ObjectAttributes.ObjectName], xmm0
0x18005ad19  movups  xmmword ptr [rbp+250h+ObjectAttributes.Length], xmm0
0x18005ad1d  movups  xmmword ptr [rbp+250h+ObjectAttributes+1Ch], xmm0
0x18005ad21  movups  xmmword ptr [rbp+250h+IoStatusBlock], xmm0
0x18005ad25  movups  [rbp+250h+FileInformation], xmm1
0x18005ad29  test    rcx, rcx
0x18005ad2c  jnz     short loc_18005AD38
0x18005ad2e  mov     eax, 0C00000EFh
0x18005ad33  jmp     loc_18005B180
0x18005ad38  test    rdx, rdx
0x18005ad3b  jnz     short loc_18005AD47
0x18005ad3d  mov     eax, 0C00000F0h
0x18005ad42  jmp     loc_18005B180
0x18005ad47  test    r15, r15
0x18005ad4a  jnz     short loc_18005AD56
0x18005ad4c  mov     eax, 0C00000F1h
0x18005ad51  jmp     loc_18005B180
0x18005ad56  lea     rcx, [rbp+250h+Destination]; Destination
0x18005ad5a  call    cs:__imp_RtlAppendUnicodeStringToString
0x18005ad61  nop     dword ptr [rax+rax+00h]
0x18005ad66  test    eax, eax
0x18005ad68  js      loc_18005B180
0x18005ad6e  lea     rdx, aInifileUpd; "\\inifile.upd"
0x18005ad75  lea     rcx, [rbp+250h+Destination]; Destination
0x18005ad79  call    cs:__imp_RtlAppendUnicodeToString
0x18005ad80  nop     dword ptr [rax+rax+00h]
0x18005ad85  test    eax, eax
0x18005ad87  js      loc_18005B180
0x18005ad8d  mov     [rsp+350h+EaLength], r12d; EaLength
0x18005ad92  lea     rax, [rbp+250h+Destination]
0x18005ad96  mov     [rsp+350h+EaBuffer], r12; EaBuffer
0x18005ad9b  lea     r9, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x18005ad9f  mov     [rsp+350h+CreateOptions], 60h ; '`'; CreateOptions
0x18005ada7  lea     r8, [rbp+250h+ObjectAttributes]; ObjectAttributes
0x18005adab  mov     [rsp+350h+CreateDisposition], 3; CreateDisposition
0x18005adb3  lea     rcx, [rsp+350h+FileHandle]; FileHandle
0x18005adb8  mov     [rsp+350h+ShareAccess], 2; ShareAccess
0x18005adc0  xorps   xmm0, xmm0
0x18005adc3  mov     [rsp+350h+FileAttributes], 80h; FileAttributes
0x18005adcb  mov     edx, 100083h; DesiredAccess
0x18005add0  mov     [rsp+350h+AllocationSize], r12; AllocationSize
0x18005add5  mov     [rbp+250h+ObjectAttributes.Length], 30h ; '0'
0x18005addc  mov     [rbp+250h+ObjectAttributes.RootDirectory], r12
0x18005ade0  mov     [rbp+250h+ObjectAttributes.Attributes], 40h ; '@'
0x18005ade7  mov     [rbp+250h+ObjectAttributes.ObjectName], rax
0x18005adeb  movdqu  xmmword ptr [rbp+250h+ObjectAttributes.SecurityDescriptor], xmm0
0x18005adf0  mov     dword ptr [rbp+250h+IoStatusBlock], r12d
0x18005adf4  call    cs:__imp_NtCreateFile
0x18005adfb  nop     dword ptr [rax+rax+00h]
0x18005ae00  mov     ebx, eax
0x18005ae02  test    eax, eax
0x18005ae04  js      loc_18005B13F
0x18005ae0a  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x18005ae0f  lea     r8, [rbp+250h+FileInformation]; FileInformation
0x18005ae13  mov     r9d, 18h; Length
0x18005ae19  mov     dword ptr [rsp+350h+AllocationSize], 5; FileInformationClass
0x18005ae21  lea     rdx, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x18005ae25  call    cs:__imp_NtQueryInformationFile
0x18005ae2c  nop     dword ptr [rax+rax+00h]
0x18005ae31  mov     ebx, eax
0x18005ae33  cmp     eax, 80000005h
0x18005ae38  jz      short loc_18005AE42
0x18005ae3a  test    eax, eax
0x18005ae3c  js      loc_18005B13F
0x18005ae42  mov     eax, dword ptr [rbp+250h+FileInformation+8]
0x18005ae45  mov     [rsp+350h+var_2E0], rax
0x18005ae4a  lea     rcx, [rax+8]
0x18005ae4e  cmp     rcx, rax
0x18005ae51  ja      short loc_18005AE5D
0x18005ae53  mov     ebx, 0C00000F2h
0x18005ae58  jmp     loc_18005B13F
0x18005ae5d  lea     rax, [rcx+1000h]
0x18005ae64  mov     [rsp+350h+var_2E0], rcx
0x18005ae69  mov     [rsp+350h+RegionSize], rcx
0x18005ae6e  cmp     rax, rcx
0x18005ae71  jbe     short loc_18005AE53
0x18005ae73  lea     rax, [rcx+1000h]
0x18005ae7a  mov     edi, 4
0x18005ae7f  mov     [rsp+350h+FileAttributes], edi; Protect
0x18005ae83  lea     r9, [rsp+350h+RegionSize]; RegionSize
0x18005ae88  xor     r8d, r8d; ZeroBits
0x18005ae8b  mov     dword ptr [rsp+350h+AllocationSize], 2000h; AllocationType
0x18005ae93  lea     rdx, [rsp+350h+BaseAddress]; BaseAddress
0x18005ae98  mov     [rsp+350h+RegionSize], rax
0x18005ae9d  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005aea1  call    cs:__imp_NtAllocateVirtualMemory
0x18005aea8  nop     dword ptr [rax+rax+00h]
0x18005aead  mov     ebx, eax
0x18005aeaf  test    eax, eax
0x18005aeb1  js      loc_18005B13F
0x18005aeb7  mov     [rsp+350h+FileAttributes], edi; Protect
0x18005aebb  lea     r9, [rsp+350h+var_2E0]; RegionSize
0x18005aec0  xor     r8d, r8d; ZeroBits
0x18005aec3  mov     dword ptr [rsp+350h+AllocationSize], 1000h; AllocationType
0x18005aecb  lea     rdx, [rsp+350h+BaseAddress]; BaseAddress
0x18005aed0  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005aed4  call    cs:__imp_NtAllocateVirtualMemory
0x18005aedb  nop     dword ptr [rax+rax+00h]
0x18005aee0  mov     ebx, eax
0x18005aee2  test    eax, eax
0x18005aee4  js      loc_18005B13F
0x18005aeea  mov     eax, dword ptr [rbp+250h+FileInformation+8]
0x18005aeed  test    eax, eax
0x18005aeef  jz      short loc_18005AF62
0x18005aef1  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x18005aef6  xor     r9d, r9d; ApcContext
0x18005aef9  mov     qword ptr [rsp+350h+CreateOptions], r12; Key
0x18005aefe  xor     r8d, r8d; ApcRoutine
0x18005af01  mov     qword ptr [rsp+350h+CreateDisposition], r12; ByteOffset
0x18005af06  xor     edx, edx; Event
0x18005af08  mov     [rsp+350h+ShareAccess], eax; Length
0x18005af0c  mov     rax, [rsp+350h+BaseAddress]
0x18005af11  mov     qword ptr [rsp+350h+FileAttributes], rax; Buffer
0x18005af16  lea     rax, [rbp+250h+IoStatusBlock]
0x18005af1a  mov     [rsp+350h+AllocationSize], rax; IoStatusBlock
0x18005af1f  call    cs:__imp_NtReadFile
0x18005af26  nop     dword ptr [rax+rax+00h]
0x18005af2b  mov     ebx, eax
0x18005af2d  cmp     eax, 103h
0x18005af32  jnz     short loc_18005AF4C
0x18005af34  mov     rcx, [rsp+350h+FileHandle]; Handle
0x18005af39  xor     r8d, r8d; Timeout
0x18005af3c  xor     edx, edx; Alertable
0x18005af3e  call    cs:__imp_NtWaitForSingleObject
0x18005af45  nop     dword ptr [rax+rax+00h]
0x18005af4a  mov     ebx, eax
0x18005af4c  test    ebx, ebx
0x18005af4e  js      loc_18005B13F
0x18005af54  mov     ebx, dword ptr [rbp+250h+IoStatusBlock]
0x18005af57  test    ebx, ebx
0x18005af59  js      loc_18005B13F
0x18005af5f  mov     eax, dword ptr [rbp+250h+FileInformation+8]
0x18005af62  mov     rdi, [rsp+350h+BaseAddress]
0x18005af67  mov     esi, eax
0x18005af69  add     rsi, rdi
0x18005af6c  cmp     rdi, rsi
0x18005af6f  jnb     short loc_18005AFD2
0x18005af71  mov     rdx, [r13+8]; String2
0x18005af75  mov     rcx, rdi; String1
0x18005af78  call    cs:__imp__wcsicmp
0x18005af7f  nop     dword ptr [rax+rax+00h]
0x18005af84  mov     ebx, eax
0x18005af86  test    eax, eax
0x18005af88  jns     short loc_18005AFA6
0x18005af8a  mov     rcx, rdi; String
0x18005af8d  call    cs:__imp_wcslen
0x18005af94  nop     dword ptr [rax+rax+00h]
0x18005af99  lea     rdi, [rdi+rax*2]
0x18005af9d  add     rdi, 0Ah
0x18005afa1  cmp     rdi, rsi
0x18005afa4  jb      short loc_18005AF71
0x18005afa6  cmp     rdi, rsi
0x18005afa9  jnb     short loc_18005AFD2
0x18005afab  test    ebx, ebx
0x18005afad  jnz     short loc_18005AFD2
0x18005afaf  mov     rcx, rdi; String
0x18005afb2  call    cs:__imp_wcslen
0x18005afb9  nop     dword ptr [rax+rax+00h]
0x18005afbe  mov     ecx, [r15]
0x18005afc1  mov     [rdi+rax*2+2], ecx
0x18005afc5  mov     ecx, [r15+4]
0x18005afc9  mov     [rdi+rax*2+6], ecx
0x18005afcd  jmp     loc_18005B075
0x18005afd2  mov     rax, [rsp+350h+var_2E0]
0x18005afd7  movzx   r14d, word ptr [r13+0]
0x18005afdc  add     r14, 0Ah
0x18005afe0  lea     rcx, [r14+rax]
0x18005afe4  cmp     rcx, rax
0x18005afe7  jb      loc_18005AE53
0x18005afed  mov     [rsp+350h+var_2E0], rcx
0x18005aff2  lea     r9, [rsp+350h+var_2E0]; RegionSize
0x18005aff7  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005affb  mov     [rsp+350h+FileAttributes], 4; Protect
0x18005b003  xor     r8d, r8d; ZeroBits
0x18005b006  mov     dword ptr [rsp+350h+AllocationSize], 1000h; AllocationType
0x18005b00e  lea     rdx, [rsp+350h+BaseAddress]; BaseAddress
0x18005b013  call    cs:__imp_NtAllocateVirtualMemory
0x18005b01a  nop     dword ptr [rax+rax+00h]
0x18005b01f  mov     ebx, eax
0x18005b021  test    eax, eax
0x18005b023  js      loc_18005B13F
0x18005b029  cmp     rdi, rsi
0x18005b02c  jnb     short loc_18005B046
0x18005b02e  mov     rax, r14
0x18005b031  mov     r8, rsi
0x18005b034  shr     rax, 1
0x18005b037  sub     r8, rdi; Size
0x18005b03a  mov     rdx, rdi; Src
0x18005b03d  lea     rcx, [rdi+rax*2]; void *
0x18005b041  call    memmove_0
0x18005b046  mov     r8, [r13+8]; pszSrc
0x18005b04a  lea     rdx, [r14-8]; cbDest
0x18005b04e  mov     rcx, rdi; pszDest
0x18005b051  add     rsi, r14
0x18005b054  call    StringCbCopyW
0x18005b059  movzx   r11d, word ptr [r13+0]
0x18005b05e  mov     eax, [r15]
0x18005b061  add     r11, 2
0x18005b065  shr     r11, 1
0x18005b068  mov     [rdi+r11*2], eax
0x18005b06c  mov     eax, [r15+4]
0x18005b070  mov     [rdi+r11*2+4], eax
0x18005b075  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x18005b07a  lea     r8, [rbp+250h+var_2C0]; FileInformation
0x18005b07e  mov     edi, 8
0x18005b083  mov     [rbp+250h+var_2C0], r12
0x18005b087  mov     r9d, edi; Length
0x18005b08a  mov     dword ptr [rsp+350h+AllocationSize], 0Eh; FileInformationClass
0x18005b092  lea     rdx, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x18005b096  call    cs:__imp_NtSetInformationFile
0x18005b09d  nop     dword ptr [rax+rax+00h]
0x18005b0a2  mov     rax, [rsp+350h+BaseAddress]
0x18005b0a7  mov     ecx, esi
0x18005b0a9  sub     ecx, eax
0x18005b0ab  mov     qword ptr [rsp+350h+CreateOptions], r12; Key
0x18005b0b0  inc     ecx
0x18005b0b2  mov     qword ptr [rsp+350h+CreateDisposition], r12; ByteOffset
0x18005b0b7  mov     [rsp+350h+ShareAccess], ecx; Length
0x18005b0bb  xor     r9d, r9d; ApcContext
0x18005b0be  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x18005b0c3  xor     r8d, r8d; ApcRoutine
0x18005b0c6  mov     qword ptr [rsp+350h+FileAttributes], rax; Buffer
0x18005b0cb  xor     edx, edx; Event
0x18005b0cd  lea     rax, [rbp+250h+IoStatusBlock]
0x18005b0d1  mov     [rsp+350h+AllocationSize], rax; IoStatusBlock
0x18005b0d6  call    cs:__imp_NtWriteFile
0x18005b0dd  nop     dword ptr [rax+rax+00h]
0x18005b0e2  mov     ebx, eax
0x18005b0e4  cmp     eax, 103h
0x18005b0e9  jnz     short loc_18005B103
0x18005b0eb  mov     rcx, [rsp+350h+FileHandle]; Handle
0x18005b0f0  xor     r8d, r8d; Timeout
0x18005b0f3  xor     edx, edx; Alertable
0x18005b0f5  call    cs:__imp_NtWaitForSingleObject
0x18005b0fc  nop     dword ptr [rax+rax+00h]
0x18005b101  mov     ebx, eax
0x18005b103  test    ebx, ebx
0x18005b105  js      short loc_18005B13F
0x18005b107  mov     ebx, dword ptr [rbp+250h+IoStatusBlock]
0x18005b10a  test    ebx, ebx
0x18005b10c  js      short loc_18005B13F
0x18005b10e  sub     esi, dword ptr [rsp+350h+BaseAddress]
0x18005b112  lea     r8, [rbp+250h+var_2B8]; FileInformation
0x18005b116  mov     rcx, [rsp+350h+FileHandle]; FileHandle
0x18005b11b  lea     rdx, [rbp+250h+IoStatusBlock]; IoStatusBlock
0x18005b11f  mov     r9d, edi; Length
0x18005b122  mov     dword ptr [rbp+250h+var_2B8], esi
0x18005b125  mov     dword ptr [rbp+250h+var_2B8+4], r12d
0x18005b129  mov     dword ptr [rsp+350h+AllocationSize], 14h; FileInformationClass
0x18005b131  call    cs:__imp_NtSetInformationFile
0x18005b138  nop     dword ptr [rax+rax+00h]
0x18005b13d  mov     ebx, eax
0x18005b13f  cmp     [rsp+350h+BaseAddress], r12
0x18005b144  jz      short loc_18005B166
0x18005b146  mov     r9d, 8000h; FreeType
0x18005b14c  lea     r8, [rsp+350h+RegionSize]; RegionSize
0x18005b151  lea     rdx, [rsp+350h+BaseAddress]; BaseAddress
0x18005b156  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18005b15a  call    cs:__imp_NtFreeVirtualMemory
0x18005b161  nop     dword ptr [rax+rax+00h]
0x18005b166  mov     rcx, [rsp+350h+FileHandle]; Handle
0x18005b16b  test    rcx, rcx
0x18005b16e  jz      short loc_18005B17E
0x18005b170  call    cs:__imp_NtClose
0x18005b177  nop     dword ptr [rax+rax+00h]
0x18005b17c  mov     ebx, eax
0x18005b17e  mov     eax, ebx
0x18005b180  mov     rcx, [rbp+250h+var_40]
0x18005b187  xor     rcx, rsp; StackCookie
0x18005b18a  call    __security_check_cookie
0x18005b18f  mov     rbx, [rsp+350h+arg_10]
  ... truncated ...
```
