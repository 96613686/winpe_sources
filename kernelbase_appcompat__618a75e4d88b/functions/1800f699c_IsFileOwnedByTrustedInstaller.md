# IsFileOwnedByTrustedInstaller

- ea: `0x1800f699c`
- end: `0x1800f6bda`
- name: `IsFileOwnedByTrustedInstaller`
- size: `574`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800b4680`

## callees

- `0x180037920`
- `0x1800391f0`
- `0x1800f699c`
- `0x1800f6be0`
- `0x180194f10`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800f6a0e`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800f6a0e`
- `ntdll!RtlReleaseRelativeName` at `0x1800f6a95`
- `ntdll!RtlReleaseRelativeName` at `0x1800f6a95`
- `ntdll!NtQueryInformationFile` at `0x1800f6ae0`
- `ntdll!NtQueryInformationFile` at `0x1800f6ae0`
- `ntdll!NtQuerySecurityObject` at `0x1800f6b0a`
- `ntdll!NtQuerySecurityObject` at `0x1800f6b48`
- `ntdll!NtQuerySecurityObject` at `0x1800f6b0a`
- `ntdll!NtQuerySecurityObject` at `0x1800f6b48`
- `ntdll!NtOpenFile` at `0x1800f6a83`
- `ntdll!NtOpenFile` at `0x1800f6a83`
- `ntdll!NtClose` at `0x1800f6b6f`
- `ntdll!NtClose` at `0x1800f6b6f`
- `ntdll!RtlFreeHeap` at `0x1800f6ab3`
- `ntdll!RtlFreeHeap` at `0x1800f6ab3`

## pseudocode

```c
__int64 __fastcall IsFileOwnedByTrustedInstaller(const WCHAR *a1)
{
  unsigned int v1; // esi
  PWSTR Buffer; // r14
  HLOCAL v3; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v5; // ebx
  ULONG LengthNeeded; // [rsp+30h] [rbp-79h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-71h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+40h] [rbp-69h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+50h] [rbp-59h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A0h] [rbp-9h] BYREF
  _OWORD FileInformation[2]; // [rsp+B0h] [rbp+7h] BYREF
  __int64 v14; // [rsp+D0h] [rbp+27h]

  FileHandle = 0;
  v14 = 0;
  memset(&ObjectAttributes, 0, 44);
  LengthNeeded = 0;
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  if ( !RtlDosPathNameToRelativeNtPathName_U(a1, &NtName, 0, &RelativeName) )
    return 0;
  v1 = 0;
  Buffer = NtName.Buffer;
  v3 = 0;
  if ( RelativeName.RelativeName.Length )
  {
    NtName = RelativeName.RelativeName;
    ContainingDirectory = RelativeName.ContainingDirectory;
  }
  else
  {
    ContainingDirectory = 0;
    RelativeName.ContainingDirectory = 0;
  }
  ObjectAttributes.RootDirectory = ContainingDirectory;
  ObjectAttributes.ObjectName = &NtName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = NtOpenFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 1u, 0);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v5 >= 0
    && NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation) >= 0
    && (NtQuerySecurityObject(FileHandle, 7u, 0, 0, &LengthNeeded) >= 0
     || LengthNeeded
     && (v3 = LocalAlloc(0, LengthNeeded)) != 0
     && NtQuerySecurityObject(FileHandle, 7u, v3, LengthNeeded, &LengthNeeded) >= 0) )
  {
    if ( (unsigned int)IsTIFileDescriptor(v3) )
      v1 = 1;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  if ( v3 )
    LocalFree(v3);
  return v1;
}

```

## disassembly

```asm
0x1800f699c  mov     [rsp-8+arg_8], rbx
0x1800f69a1  mov     [rsp-8+arg_10], rsi
0x1800f69a6  push    rbp
0x1800f69a7  push    rdi
0x1800f69a8  push    r12
0x1800f69aa  push    r14
0x1800f69ac  push    r15
0x1800f69ae  lea     rbp, [rsp-37h]
0x1800f69b3  sub     rsp, 0E0h
0x1800f69ba  mov     rax, cs:__security_cookie
0x1800f69c1  xor     rax, rsp
0x1800f69c4  mov     [rbp+57h+var_28], rax
0x1800f69c8  xorps   xmm0, xmm0
0x1800f69cb  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800f69cf  xorps   xmm1, xmm1
0x1800f69d2  lea     rdx, [rbp+57h+NtName]; NtName
0x1800f69d6  xor     r15d, r15d
0x1800f69d9  xor     eax, eax
0x1800f69db  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800f69df  xor     r8d, r8d; PartName
0x1800f69e2  mov     [rbp+57h+FileHandle], r15
0x1800f69e6  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800f69ea  mov     [rbp+57h+var_30], rax
0x1800f69ee  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800f69f2  mov     [rbp+57h+LengthNeeded], r15d
0x1800f69f6  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800f69fa  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x1800f69fe  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x1800f6a02  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800f6a06  movups  [rbp+57h+FileInformation], xmm1
0x1800f6a0a  movups  [rbp+57h+var_40], xmm1
0x1800f6a0e  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800f6a15  nop     dword ptr [rax+rax+00h]
0x1800f6a1a  test    al, al
0x1800f6a1c  jz      loc_1800F6BD6
0x1800f6a22  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800f6a26  mov     esi, r15d
0x1800f6a29  mov     r14, [rbp+57h+NtName.Buffer]
0x1800f6a2d  mov     edi, r15d
0x1800f6a30  test    ax, ax
0x1800f6a33  jnz     loc_1800F6BB3
0x1800f6a39  mov     eax, r15d
0x1800f6a3c  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800f6a40  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800f6a44  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f6a48  lea     rax, [rbp+57h+NtName]
0x1800f6a4c  mov     [rsp+100h+OpenOptions], r15d; OpenOptions
0x1800f6a51  xorps   xmm0, xmm0
0x1800f6a54  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f6a58  mov     r12d, 1
0x1800f6a5e  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f6a65  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f6a69  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f6a70  mov     edx, 120089h; DesiredAccess
0x1800f6a75  mov     [rsp+100h+ShareAccess], r12d; ShareAccess
0x1800f6a7a  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f6a7e  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f6a83  call    cs:__imp_NtOpenFile
0x1800f6a8a  nop     dword ptr [rax+rax+00h]
0x1800f6a8f  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800f6a93  mov     ebx, eax
0x1800f6a95  call    cs:__imp_RtlReleaseRelativeName
0x1800f6a9c  nop     dword ptr [rax+rax+00h]
0x1800f6aa1  mov     rcx, gs:60h
0x1800f6aaa  mov     r8, r14; P
0x1800f6aad  xor     edx, edx; Flags
0x1800f6aaf  mov     rcx, [rcx+30h]; HeapHandle
0x1800f6ab3  call    cs:__imp_RtlFreeHeap
0x1800f6aba  nop     dword ptr [rax+rax+00h]
0x1800f6abf  test    ebx, ebx
0x1800f6ac1  js      loc_1800F6B66
0x1800f6ac7  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f6acb  lea     r9d, [r12+27h]; Length
0x1800f6ad0  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800f6ad4  mov     [rsp+100h+ShareAccess], 4; FileInformationClass
0x1800f6adc  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f6ae0  call    cs:__imp_NtQueryInformationFile
0x1800f6ae7  nop     dword ptr [rax+rax+00h]
0x1800f6aec  test    eax, eax
0x1800f6aee  js      short loc_1800F6B66
0x1800f6af0  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f6af4  lea     rax, [rbp+57h+LengthNeeded]
0x1800f6af8  lea     ebx, [r12+6]
0x1800f6afd  mov     qword ptr [rsp+100h+ShareAccess], rax; LengthNeeded
0x1800f6b02  mov     edx, ebx; SecurityInformation
0x1800f6b04  xor     r9d, r9d; Length
0x1800f6b07  xor     r8d, r8d; SecurityDescriptor
0x1800f6b0a  call    cs:__imp_NtQuerySecurityObject
0x1800f6b11  nop     dword ptr [rax+rax+00h]
0x1800f6b16  test    eax, eax
0x1800f6b18  jns     short loc_1800F6B58
0x1800f6b1a  mov     eax, [rbp+57h+LengthNeeded]
0x1800f6b1d  test    eax, eax
0x1800f6b1f  jz      short loc_1800F6B66
0x1800f6b21  mov     edx, eax; uBytes
0x1800f6b23  xor     ecx, ecx; uFlags
0x1800f6b25  call    LocalAlloc
0x1800f6b2a  mov     rdi, rax
0x1800f6b2d  test    rax, rax
0x1800f6b30  jz      short loc_1800F6B66
0x1800f6b32  mov     r9d, [rbp+57h+LengthNeeded]; Length
0x1800f6b36  lea     rax, [rbp+57h+LengthNeeded]
0x1800f6b3a  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f6b3e  mov     r8, rdi; SecurityDescriptor
0x1800f6b41  mov     edx, ebx; SecurityInformation
0x1800f6b43  mov     qword ptr [rsp+100h+ShareAccess], rax; LengthNeeded
0x1800f6b48  call    cs:__imp_NtQuerySecurityObject
0x1800f6b4f  nop     dword ptr [rax+rax+00h]
0x1800f6b54  test    eax, eax
0x1800f6b56  js      short loc_1800F6B66
0x1800f6b58  mov     rcx, rdi; SecurityDescriptor
0x1800f6b5b  call    IsTIFileDescriptor
0x1800f6b60  test    eax, eax
0x1800f6b62  cmovnz  esi, r12d
0x1800f6b66  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f6b6a  test    rcx, rcx
0x1800f6b6d  jz      short loc_1800F6B7B
0x1800f6b6f  call    cs:__imp_NtClose
0x1800f6b76  nop     dword ptr [rax+rax+00h]
0x1800f6b7b  test    rdi, rdi
0x1800f6b7e  jz      short loc_1800F6B88
0x1800f6b80  mov     rcx, rdi; hMem
0x1800f6b83  call    LocalFree
0x1800f6b88  mov     eax, esi
0x1800f6b8a  mov     rcx, [rbp+57h+var_28]
0x1800f6b8e  xor     rcx, rsp; StackCookie
0x1800f6b91  call    __security_check_cookie
0x1800f6b96  lea     r11, [rsp+100h+var_20]
0x1800f6b9e  mov     rbx, [r11+38h]
0x1800f6ba2  mov     rsi, [r11+40h]
0x1800f6ba6  mov     rsp, r11
0x1800f6ba9  pop     r15
0x1800f6bab  pop     r14
0x1800f6bad  pop     r12
0x1800f6baf  pop     rdi
0x1800f6bb0  pop     rbp
0x1800f6bb1  retn
0x1800f6bb3  mov     [rbp+57h+NtName.Length], ax
0x1800f6bb7  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800f6bba  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1800f6bbd  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800f6bc1  mov     word ptr [rbp+57h+NtName+6], ax
0x1800f6bc5  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800f6bc9  mov     [rbp+57h+NtName.Buffer], rax
0x1800f6bcd  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800f6bd1  jmp     loc_1800F6A40
0x1800f6bd6  xor     eax, eax
0x1800f6bd8  jmp     short loc_1800F6B8A
```
