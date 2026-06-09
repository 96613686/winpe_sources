# SetFileSecurityW

- ea: `0x1800f7db0`
- end: `0x1800f7f47`
- name: `SetFileSecurityW`
- size: `407`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x1800f7db0`
- `0x1800f7f50`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800f7e15`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800f7e15`
- `ntdll!RtlReleaseRelativeName` at `0x1800f7e93`
- `ntdll!RtlReleaseRelativeName` at `0x1800f7e93`
- `ntdll!NtOpenFile` at `0x1800f7e7c`
- `ntdll!NtOpenFile` at `0x1800f7f3a`
- `ntdll!NtOpenFile` at `0x1800f7e7c`
- `ntdll!NtOpenFile` at `0x1800f7f3a`
- `ntdll!NtClose` at `0x1800f7eca`
- `ntdll!NtClose` at `0x1800f7eca`
- `ntdll!NtSetSecurityObject` at `0x1800f7ebe`
- `ntdll!NtSetSecurityObject` at `0x1800f7ebe`
- `ntdll!RtlFreeHeap` at `0x1800f7eab`
- `ntdll!RtlFreeHeap` at `0x1800f7eab`

## pseudocode

```c
BOOL __stdcall SetFileSecurityW(
        LPCWSTR lpFileName,
        SECURITY_INFORMATION SecurityInformation,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  PWSTR Buffer; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v8; // ebx
  __int64 v10; // rcx
  HANDLE FileHandle; // [rsp+30h] [rbp-59h] BYREF
  struct _UNICODE_STRING NtName; // [rsp+38h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+48h] [rbp-41h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+58h] [rbp-31h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-11h] BYREF
  DWORD DesiredAccess; // [rsp+108h] [rbp+7Fh] BYREF

  FileHandle = 0;
  DesiredAccess = 0;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  IoStatusBlock = 0;
  SetSecurityAccessMask(SecurityInformation, &DesiredAccess);
  if ( RtlDosPathNameToRelativeNtPathName_U(lpFileName, &NtName, 0, &RelativeName) )
  {
    Buffer = NtName.Buffer;
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
    v8 = NtOpenFile(&FileHandle, DesiredAccess, &ObjectAttributes, &IoStatusBlock, 7u, 0x200000u);
    if ( v8 == -1073741811 )
      v8 = NtOpenFile(&FileHandle, DesiredAccess, &ObjectAttributes, &IoStatusBlock, 7u, 0);
    RtlReleaseRelativeName(&RelativeName);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( v8 >= 0 )
    {
      v8 = NtSetSecurityObject(FileHandle, SecurityInformation, pSecurityDescriptor);
      NtClose(FileHandle);
      if ( v8 >= 0 )
        return 1;
    }
    v10 = (unsigned int)v8;
  }
  else
  {
    v10 = 3221225523LL;
  }
  BaseSetLastNTError(v10);
  return 0;
}

```

## disassembly

```asm
0x1800f7db0  push    rbp
0x1800f7db2  push    rbx
0x1800f7db3  push    rsi
0x1800f7db4  push    rdi
0x1800f7db5  push    r14
0x1800f7db7  push    r15
0x1800f7db9  lea     rbp, [rsp-2Fh]
0x1800f7dbe  sub     rsp, 0B8h
0x1800f7dc5  xorps   xmm0, xmm0
0x1800f7dc8  mov     esi, edx
0x1800f7dca  xorps   xmm1, xmm1
0x1800f7dcd  lea     rdx, [rbp+57h+DesiredAccess]; DesiredAccess
0x1800f7dd1  mov     rbx, rcx
0x1800f7dd4  xor     r15d, r15d
0x1800f7dd7  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800f7ddb  mov     ecx, esi; SecurityInformation
0x1800f7ddd  mov     [rbp+57h+FileHandle], r15
0x1800f7de1  xor     eax, eax
0x1800f7de3  mov     [rbp+57h+DesiredAccess], r15d
0x1800f7de7  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800f7deb  mov     r14, r8
0x1800f7dee  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800f7df2  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800f7df6  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x1800f7dfa  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x1800f7dfe  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800f7e02  call    SetSecurityAccessMask
0x1800f7e07  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800f7e0b  xor     r8d, r8d; PartName
0x1800f7e0e  lea     rdx, [rbp+57h+NtName]; NtName
0x1800f7e12  mov     rcx, rbx; DosName
0x1800f7e15  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800f7e1b  test    al, al
0x1800f7e1d  jz      loc_1800F7F17
0x1800f7e23  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800f7e27  mov     rdi, [rbp+57h+NtName.Buffer]
0x1800f7e2b  test    ax, ax
0x1800f7e2e  jnz     loc_1800F7EF4
0x1800f7e34  mov     eax, r15d
0x1800f7e37  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800f7e3b  mov     edx, [rbp+57h+DesiredAccess]; DesiredAccess
0x1800f7e3e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f7e42  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800f7e46  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f7e4a  lea     rax, [rbp+57h+NtName]
0x1800f7e4e  mov     [rsp+0E0h+OpenOptions], 200000h; OpenOptions
0x1800f7e56  xorps   xmm0, xmm0
0x1800f7e59  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f7e5d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f7e61  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f7e68  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f7e6f  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f7e74  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1800f7e7c  call    cs:__imp_NtOpenFile
0x1800f7e82  mov     ebx, eax
0x1800f7e84  cmp     eax, 0C000000Dh
0x1800f7e89  jz      loc_1800F7F1E
0x1800f7e8f  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800f7e93  call    cs:__imp_RtlReleaseRelativeName
0x1800f7e99  mov     rcx, gs:60h
0x1800f7ea2  mov     r8, rdi; P
0x1800f7ea5  xor     edx, edx; Flags
0x1800f7ea7  mov     rcx, [rcx+30h]; HeapHandle
0x1800f7eab  call    cs:__imp_RtlFreeHeap
0x1800f7eb1  test    ebx, ebx
0x1800f7eb3  js      short loc_1800F7EE9
0x1800f7eb5  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f7eb9  mov     r8, r14; SecurityDescriptor
0x1800f7ebc  mov     edx, esi; SecurityInformation
0x1800f7ebe  call    cs:__imp_NtSetSecurityObject
0x1800f7ec4  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f7ec8  mov     ebx, eax
0x1800f7eca  call    cs:__imp_NtClose
0x1800f7ed0  test    ebx, ebx
0x1800f7ed2  js      short loc_1800F7EE9
0x1800f7ed4  mov     eax, 1
0x1800f7ed9  add     rsp, 0B8h
0x1800f7ee0  pop     r15
0x1800f7ee2  pop     r14
0x1800f7ee4  pop     rdi
0x1800f7ee5  pop     rsi
0x1800f7ee6  pop     rbx
0x1800f7ee7  pop     rbp
0x1800f7ee8  retn
0x1800f7ee9  mov     ecx, ebx
0x1800f7eeb  call    BaseSetLastNTError
0x1800f7ef0  xor     eax, eax
0x1800f7ef2  jmp     short loc_1800F7ED9
0x1800f7ef4  mov     [rbp+57h+NtName.Length], ax
0x1800f7ef8  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800f7efb  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1800f7efe  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800f7f02  mov     word ptr [rbp+57h+NtName+6], ax
0x1800f7f06  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800f7f0a  mov     [rbp+57h+NtName.Buffer], rax
0x1800f7f0e  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800f7f12  jmp     loc_1800F7E3B
0x1800f7f17  mov     ecx, 0C0000033h
0x1800f7f1c  jmp     short loc_1800F7EEB
0x1800f7f1e  mov     edx, [rbp+57h+DesiredAccess]; DesiredAccess
0x1800f7f21  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f7f25  mov     [rsp+0E0h+OpenOptions], r15d; OpenOptions
0x1800f7f2a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f7f2e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f7f32  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1800f7f3a  call    cs:__imp_NtOpenFile
0x1800f7f40  mov     ebx, eax
0x1800f7f42  jmp     loc_1800F7E8F
```
