# bMapFileUNICODEClideSide

- ea: `0x180045548`
- end: `0x1800457d6`
- name: `bMapFileUNICODEClideSide`
- size: `654`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PHANDLE FileHandle)`
- caller_count: `6`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180038f0c`
- `0x1800451f0`
- `0x180084b3c`
- `0x180085150`
- `0x180091700`
- `0x180092c20`

## callees

- `0x180045548`
- `0x180046018`
- `0x18007f800`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180045786`
- `ntdll!RtlFreeHeap` at `0x180045786`
- `ntdll!RtlInitUnicodeString` at `0x1800455c1`
- `ntdll!RtlInitUnicodeString` at `0x1800455c1`
- `ntdll!NtClose` at `0x1800456f2`
- `ntdll!NtClose` at `0x180045701`
- `ntdll!NtClose` at `0x180045758`
- `ntdll!NtClose` at `0x1800456f2`
- `ntdll!NtClose` at `0x180045701`
- `ntdll!NtClose` at `0x180045758`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180045744`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180045744`
- `ntdll!NtOpenFile` at `0x18004560f`
- `ntdll!NtOpenFile` at `0x18004560f`
- `ntdll!NtQueryInformationFile` at `0x180045651`
- `ntdll!NtQueryInformationFile` at `0x180045651`
- `ntdll!NtCreateSection` at `0x180045692`
- `ntdll!NtCreateSection` at `0x180045692`
- `ntdll!NtMapViewOfSection` at `0x1800456db`
- `ntdll!NtMapViewOfSection` at `0x1800456db`

## pseudocode

```c
__int64 __fastcall bMapFileUNICODEClideSide(PCWSTR SourceString, PHANDLE FileHandle, int a3)
{
  void **v3; // rdi
  NTSTATUS v6; // esi
  NTSTATUS v7; // eax
  void *v8; // rcx
  void *v10; // rcx
  ULONG_PTR ViewSize; // [rsp+50h] [rbp-49h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-41h] BYREF
  PCWSTR NtFileNamePart; // [rsp+68h] [rbp-31h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
  __int128 FileInformation; // [rsp+B0h] [rbp+17h] BYREF
  __int64 v17; // [rsp+C0h] [rbp+27h]

  v3 = FileHandle + 1;
  *(_QWORD *)&DestinationString.Length = 0;
  NtFileNamePart = 0;
  v17 = 0;
  ViewSize = 0;
  *FileHandle = 0;
  FileHandle[1] = 0;
  DestinationString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  FileInformation = 0;
  if ( a3 )
    RtlInitUnicodeString(&DestinationString, SourceString);
  else
    RtlDosPathNameToNtPathName_U(SourceString, &DestinationString, &NtFileNamePart, 0);
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v6 = NtOpenFile(FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 1u, 0x20u);
  if ( !a3 && DestinationString.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, DestinationString.Buffer);
  if ( v6 < 0 || IoStatusBlock.Status < 0 )
    return 0;
  v7 = NtQueryInformationFile(*FileHandle, &IoStatusBlock, &FileInformation, 0x18u, FileStandardInformation);
  *((_DWORD *)FileHandle + 6) = DWORD2(FileInformation);
  if ( v7 < 0 )
  {
    v10 = *FileHandle;
    goto LABEL_13;
  }
  if ( NtCreateSection(v3, 4u, 0, 0, 2u, 0x8000000u, *FileHandle) < 0 )
  {
    v10 = *FileHandle;
LABEL_13:
    NtClose(v10);
    *FileHandle = 0;
    return 0;
  }
  v8 = *v3;
  FileHandle[2] = 0;
  ViewSize = 0;
  if ( NtMapViewOfSection(v8, (HANDLE)0xFFFFFFFFFFFFFFFFLL, FileHandle + 2, 0, 0, 0, &ViewSize, ViewUnmap, 0, 2u) < 0 )
  {
    NtClose(*v3);
    NtClose(*FileHandle);
    *FileHandle = 0;
    *v3 = 0;
    return 0;
  }
  if ( HIDWORD(FileInformation)
    || ((DWORD2(FileInformation) + 4095) & 0xFFFFF000) > ViewSize
    || !*((_DWORD *)FileHandle + 6) )
  {
    vUnmapFileClideSide(FileHandle);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x180045548  mov     [rsp-8+arg_10], rbx
0x18004554d  push    rbp
0x18004554e  push    rsi
0x18004554f  push    rdi
0x180045550  push    r14
0x180045552  push    r15
0x180045554  lea     rbp, [rsp-37h]
0x180045559  sub     rsp, 0D0h
0x180045560  mov     rax, cs:__security_cookie
0x180045567  xor     rax, rsp
0x18004556a  mov     [rbp+57h+var_28], rax
0x18004556e  xor     r15d, r15d
0x180045571  lea     rdi, [rdx+8]
0x180045575  xorps   xmm0, xmm0
0x180045578  mov     qword ptr [rbp+57h+DestinationString.Length], r15
0x18004557c  xor     eax, eax
0x18004557e  mov     [rbp+57h+NtFileNamePart], r15
0x180045582  mov     [rbp+57h+var_30], rax
0x180045586  xorps   xmm1, xmm1
0x180045589  mov     [rbp+57h+ViewSize], r15
0x18004558d  mov     r14d, r8d
0x180045590  mov     [rdx], r15
0x180045593  mov     rbx, rdx
0x180045596  mov     [rdi], r15
0x180045599  mov     [rbp+57h+DestinationString.Buffer], r15
0x18004559d  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800455a1  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800455a5  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800455a9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800455ad  movups  [rbp+57h+FileInformation], xmm1
0x1800455b1  test    r8d, r8d
0x1800455b4  jz      loc_180045739
0x1800455ba  mov     rdx, rcx; SourceString
0x1800455bd  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1800455c1  call    cs:__imp_RtlInitUnicodeString
0x1800455c8  nop     dword ptr [rax+rax+00h]
0x1800455cd  lea     rax, [rbp+57h+DestinationString]
0x1800455d1  mov     [rsp+0F0h+OpenOptions], 20h ; ' '; OpenOptions
0x1800455d9  xorps   xmm0, xmm0
0x1800455dc  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800455e0  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800455e4  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800455eb  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800455ef  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x1800455f3  mov     edx, 100001h; DesiredAccess
0x1800455f8  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800455ff  mov     rcx, rbx; FileHandle
0x180045602  mov     [rsp+0F0h+ShareAccess], 1; ShareAccess
0x18004560a  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004560f  call    cs:__imp_NtOpenFile
0x180045616  nop     dword ptr [rax+rax+00h]
0x18004561b  mov     esi, eax
0x18004561d  test    r14d, r14d
0x180045620  jz      loc_180045769
0x180045626  test    esi, esi
0x180045628  js      loc_180045713
0x18004562e  cmp     dword ptr [rbp+57h+IoStatusBlock], r15d
0x180045632  jl      loc_180045713
0x180045638  mov     rcx, [rbx]; FileHandle
0x18004563b  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x18004563f  mov     r9d, 18h; Length
0x180045645  mov     [rsp+0F0h+ShareAccess], 5; FileInformationClass
0x18004564d  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180045651  call    cs:__imp_NtQueryInformationFile
0x180045658  nop     dword ptr [rax+rax+00h]
0x18004565d  mov     edx, eax
0x18004565f  mov     eax, dword ptr [rbp+57h+FileInformation+8]
0x180045662  mov     [rbx+18h], eax
0x180045665  mov     rax, [rbx]
0x180045668  test    edx, edx
0x18004566a  js      loc_180045797
0x180045670  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x180045675  mov     esi, 2
0x18004567a  mov     [rsp+0F0h+OpenOptions], 8000000h; AllocationAttributes
0x180045682  xor     r9d, r9d; MaximumSize
0x180045685  xor     r8d, r8d; ObjectAttributes
0x180045688  mov     [rsp+0F0h+ShareAccess], esi; SectionPageProtection
0x18004568c  mov     rcx, rdi; SectionHandle
0x18004568f  lea     edx, [rsi+2]; DesiredAccess
0x180045692  call    cs:__imp_NtCreateSection
0x180045699  nop     dword ptr [rax+rax+00h]
0x18004569e  test    eax, eax
0x1800456a0  js      loc_180045755
0x1800456a6  mov     rcx, [rdi]; SectionHandle
0x1800456a9  lea     rax, [rbp+57h+ViewSize]
0x1800456ad  mov     [rsp+0F0h+AccessProtection], esi; AccessProtection
0x1800456b1  lea     r8, [rbx+10h]; BaseAddress
0x1800456b5  mov     [rsp+0F0h+AllocationType], r15d; AllocationType
0x1800456ba  xor     r9d, r9d; ZeroBits
0x1800456bd  mov     [rsp+0F0h+InheritDisposition], esi; InheritDisposition
0x1800456c1  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x1800456c5  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x1800456ca  mov     qword ptr [rsp+0F0h+OpenOptions], r15; SectionOffset
0x1800456cf  mov     qword ptr [rsp+0F0h+ShareAccess], r15; CommitSize
0x1800456d4  mov     [r8], r15
0x1800456d7  mov     [rbp+57h+ViewSize], r15
0x1800456db  call    cs:__imp_NtMapViewOfSection
0x1800456e2  nop     dword ptr [rax+rax+00h]
0x1800456e7  test    eax, eax
0x1800456e9  jns     loc_18004579C
0x1800456ef  mov     rcx, [rdi]; Handle
0x1800456f2  call    cs:__imp_NtClose
0x1800456f9  nop     dword ptr [rax+rax+00h]
0x1800456fe  mov     rcx, [rbx]; Handle
0x180045701  call    cs:__imp_NtClose
0x180045708  nop     dword ptr [rax+rax+00h]
0x18004570d  mov     [rbx], r15
0x180045710  mov     [rdi], r15
0x180045713  xor     eax, eax
0x180045715  mov     rcx, [rbp+57h+var_28]
0x180045719  xor     rcx, rsp; StackCookie
0x18004571c  call    __security_check_cookie
0x180045721  mov     rbx, [rsp+0F0h+arg_10]
0x180045729  add     rsp, 0D0h
0x180045730  pop     r15
0x180045732  pop     r14
0x180045734  pop     rdi
0x180045735  pop     rsi
0x180045736  pop     rbp
0x180045737  retn
0x180045739  xor     r9d, r9d; DirectoryInfo
0x18004573c  lea     r8, [rbp+57h+NtFileNamePart]; NtFileNamePart
0x180045740  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x180045744  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18004574b  nop     dword ptr [rax+rax+00h]
0x180045750  jmp     loc_1800455CD
0x180045755  mov     rcx, [rbx]; Handle
0x180045758  call    cs:__imp_NtClose
0x18004575f  nop     dword ptr [rax+rax+00h]
0x180045764  mov     [rbx], r15
0x180045767  jmp     short loc_180045713
0x180045769  cmp     [rbp+57h+DestinationString.Buffer], r15
0x18004576d  jz      loc_180045626
0x180045773  mov     rcx, gs:60h
0x18004577c  xor     edx, edx; Flags
0x18004577e  mov     r8, [rbp+57h+DestinationString.Buffer]; P
0x180045782  mov     rcx, [rcx+30h]; HeapHandle
0x180045786  call    cs:__imp_RtlFreeHeap
0x18004578d  nop     dword ptr [rax+rax+00h]
0x180045792  jmp     loc_180045626
0x180045797  mov     rcx, rax
0x18004579a  jmp     short loc_180045758
0x18004579c  cmp     dword ptr [rbp+57h+FileInformation+0Ch], r15d
0x1800457a0  jnz     short loc_1800457C9
0x1800457a2  mov     ecx, dword ptr [rbp+57h+FileInformation+8]
0x1800457a5  mov     edx, 0FFFFF000h
0x1800457aa  add     ecx, 0FFFh
0x1800457b0  and     rcx, rdx
0x1800457b3  cmp     rcx, [rbp+57h+ViewSize]
0x1800457b7  ja      short loc_1800457C9
0x1800457b9  cmp     [rbx+18h], r15d
0x1800457bd  jz      short loc_1800457C9
0x1800457bf  mov     eax, 1
0x1800457c4  jmp     loc_180045715
0x1800457c9  mov     rcx, rbx
0x1800457cc  call    vUnmapFileClideSide
0x1800457d1  jmp     loc_180045713
```
