# bMapFileUNICODEClideSide

- ea: `0x180039ae4`
- end: `0x180039d35`
- name: `bMapFileUNICODEClideSide`
- size: `593`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PHANDLE FileHandle)`
- caller_count: `6`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180033000`
- `0x180039770`
- `0x18007fd0c`
- `0x1800802e0`
- `0x18008bf28`
- `0x18008d38c`

## callees

- `0x180039ae4`
- `0x18006b00c`
- `0x18007ac50`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180039ceb`
- `ntdll!RtlFreeHeap` at `0x180039ceb`
- `ntdll!RtlInitUnicodeString` at `0x180039b5d`
- `ntdll!RtlInitUnicodeString` at `0x180039b5d`
- `ntdll!NtClose` at `0x180039c70`
- `ntdll!NtClose` at `0x180039c79`
- `ntdll!NtClose` at `0x180039cc3`
- `ntdll!NtClose` at `0x180039c70`
- `ntdll!NtClose` at `0x180039c79`
- `ntdll!NtClose` at `0x180039cc3`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180039cb5`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180039cb5`
- `ntdll!NtOpenFile` at `0x180039ba5`
- `ntdll!NtOpenFile` at `0x180039ba5`
- `ntdll!NtQueryInformationFile` at `0x180039be1`
- `ntdll!NtQueryInformationFile` at `0x180039be1`
- `ntdll!NtCreateSection` at `0x180039c1c`
- `ntdll!NtCreateSection` at `0x180039c1c`
- `ntdll!NtMapViewOfSection` at `0x180039c5f`
- `ntdll!NtMapViewOfSection` at `0x180039c5f`

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
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp-19h] BYREF
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
0x180039ae4  mov     [rsp-8+arg_10], rbx
0x180039ae9  push    rbp
0x180039aea  push    rsi
0x180039aeb  push    rdi
0x180039aec  push    r14
0x180039aee  push    r15
0x180039af0  lea     rbp, [rsp-37h]
0x180039af5  sub     rsp, 0D0h
0x180039afc  mov     rax, cs:__security_cookie
0x180039b03  xor     rax, rsp
0x180039b06  mov     [rbp+57h+var_28], rax
0x180039b0a  xor     r15d, r15d
0x180039b0d  lea     rdi, [rdx+8]
0x180039b11  xorps   xmm0, xmm0
0x180039b14  mov     qword ptr [rbp+57h+DestinationString.Length], r15
0x180039b18  xor     eax, eax
0x180039b1a  mov     [rbp+57h+NtFileNamePart], r15
0x180039b1e  mov     [rbp+57h+var_30], rax
0x180039b22  xorps   xmm1, xmm1
0x180039b25  mov     [rbp+57h+ViewSize], r15
0x180039b29  mov     r14d, r8d
0x180039b2c  mov     [rdx], r15
0x180039b2f  mov     rbx, rdx
0x180039b32  mov     [rdi], r15
0x180039b35  mov     [rbp+57h+DestinationString.Buffer], r15
0x180039b39  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x180039b3d  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180039b41  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180039b45  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180039b49  movups  [rbp+57h+FileInformation], xmm1
0x180039b4d  test    r8d, r8d
0x180039b50  jz      loc_180039CAA
0x180039b56  mov     rdx, rcx; SourceString
0x180039b59  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180039b5d  call    cs:__imp_RtlInitUnicodeString
0x180039b63  lea     rax, [rbp+57h+DestinationString]
0x180039b67  mov     [rsp+0F0h+OpenOptions], 20h ; ' '; OpenOptions
0x180039b6f  xorps   xmm0, xmm0
0x180039b72  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180039b76  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180039b7a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180039b81  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180039b85  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x180039b89  mov     edx, 100001h; DesiredAccess
0x180039b8e  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180039b95  mov     rcx, rbx; FileHandle
0x180039b98  mov     [rsp+0F0h+ShareAccess], 1; ShareAccess
0x180039ba0  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180039ba5  call    cs:__imp_NtOpenFile
0x180039bab  mov     esi, eax
0x180039bad  test    r14d, r14d
0x180039bb0  jz      loc_180039CCE
0x180039bb6  test    esi, esi
0x180039bb8  js      loc_180039C85
0x180039bbe  cmp     dword ptr [rbp+57h+IoStatusBlock], r15d
0x180039bc2  jl      loc_180039C85
0x180039bc8  mov     rcx, [rbx]; FileHandle
0x180039bcb  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x180039bcf  mov     r9d, 18h; Length
0x180039bd5  mov     [rsp+0F0h+ShareAccess], 5; FileInformationClass
0x180039bdd  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180039be1  call    cs:__imp_NtQueryInformationFile
0x180039be7  mov     edx, eax
0x180039be9  mov     eax, dword ptr [rbp+57h+FileInformation+8]
0x180039bec  mov     [rbx+18h], eax
0x180039bef  mov     rax, [rbx]
0x180039bf2  test    edx, edx
0x180039bf4  js      loc_180039CF6
0x180039bfa  mov     [rsp+0F0h+FileHandle], rax; FileHandle
0x180039bff  mov     esi, 2
0x180039c04  mov     [rsp+0F0h+OpenOptions], 8000000h; AllocationAttributes
0x180039c0c  xor     r9d, r9d; MaximumSize
0x180039c0f  xor     r8d, r8d; ObjectAttributes
0x180039c12  mov     [rsp+0F0h+ShareAccess], esi; SectionPageProtection
0x180039c16  mov     rcx, rdi; SectionHandle
0x180039c19  lea     edx, [rsi+2]; DesiredAccess
0x180039c1c  call    cs:__imp_NtCreateSection
0x180039c22  test    eax, eax
0x180039c24  js      loc_180039CC0
0x180039c2a  mov     rcx, [rdi]; SectionHandle
0x180039c2d  lea     rax, [rbp+57h+ViewSize]
0x180039c31  mov     [rsp+0F0h+AccessProtection], esi; AccessProtection
0x180039c35  lea     r8, [rbx+10h]; BaseAddress
0x180039c39  mov     [rsp+0F0h+AllocationType], r15d; AllocationType
0x180039c3e  xor     r9d, r9d; ZeroBits
0x180039c41  mov     [rsp+0F0h+InheritDisposition], esi; InheritDisposition
0x180039c45  or      rdx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180039c49  mov     [rsp+0F0h+FileHandle], rax; ViewSize
0x180039c4e  mov     qword ptr [rsp+0F0h+OpenOptions], r15; SectionOffset
0x180039c53  mov     qword ptr [rsp+0F0h+ShareAccess], r15; CommitSize
0x180039c58  mov     [r8], r15
0x180039c5b  mov     [rbp+57h+ViewSize], r15
0x180039c5f  call    cs:__imp_NtMapViewOfSection
0x180039c65  test    eax, eax
0x180039c67  jns     loc_180039CFB
0x180039c6d  mov     rcx, [rdi]; Handle
0x180039c70  call    cs:__imp_NtClose
0x180039c76  mov     rcx, [rbx]; Handle
0x180039c79  call    cs:__imp_NtClose
0x180039c7f  mov     [rbx], r15
0x180039c82  mov     [rdi], r15
0x180039c85  xor     eax, eax
0x180039c87  mov     rcx, [rbp+57h+var_28]
0x180039c8b  xor     rcx, rsp; StackCookie
0x180039c8e  call    __security_check_cookie
0x180039c93  mov     rbx, [rsp+0F0h+arg_10]
0x180039c9b  add     rsp, 0D0h
0x180039ca2  pop     r15
0x180039ca4  pop     r14
0x180039ca6  pop     rdi
0x180039ca7  pop     rsi
0x180039ca8  pop     rbp
0x180039ca9  retn
0x180039caa  xor     r9d, r9d; DirectoryInfo
0x180039cad  lea     r8, [rbp+57h+NtFileNamePart]; NtFileNamePart
0x180039cb1  lea     rdx, [rbp+57h+DestinationString]; NtPathName
0x180039cb5  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180039cbb  jmp     loc_180039B63
0x180039cc0  mov     rcx, [rbx]; Handle
0x180039cc3  call    cs:__imp_NtClose
0x180039cc9  mov     [rbx], r15
0x180039ccc  jmp     short loc_180039C85
0x180039cce  cmp     [rbp+57h+DestinationString.Buffer], r15
0x180039cd2  jz      loc_180039BB6
0x180039cd8  mov     rcx, gs:60h
0x180039ce1  xor     edx, edx; Flags
0x180039ce3  mov     r8, [rbp+57h+DestinationString.Buffer]; P
0x180039ce7  mov     rcx, [rcx+30h]; HeapHandle
0x180039ceb  call    cs:__imp_RtlFreeHeap
0x180039cf1  jmp     loc_180039BB6
0x180039cf6  mov     rcx, rax
0x180039cf9  jmp     short loc_180039CC3
0x180039cfb  cmp     dword ptr [rbp+57h+FileInformation+0Ch], r15d
0x180039cff  jnz     short loc_180039D28
0x180039d01  mov     ecx, dword ptr [rbp+57h+FileInformation+8]
0x180039d04  mov     edx, 0FFFFF000h
0x180039d09  add     ecx, 0FFFh
0x180039d0f  and     rcx, rdx
0x180039d12  cmp     rcx, [rbp+57h+ViewSize]
0x180039d16  ja      short loc_180039D28
0x180039d18  cmp     [rbx+18h], r15d
0x180039d1c  jz      short loc_180039D28
0x180039d1e  mov     eax, 1
0x180039d23  jmp     loc_180039C87
0x180039d28  mov     rcx, rbx
0x180039d2b  call    vUnmapFileClideSide
0x180039d30  jmp     loc_180039C85
```
