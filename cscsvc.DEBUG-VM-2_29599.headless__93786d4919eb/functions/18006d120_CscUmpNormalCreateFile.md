# CscUmpNormalCreateFile

- ea: `0x18006d120`
- end: `0x18006d22e`
- name: `CscUmpNormalCreateFile`
- size: `270`
- prototype: `__int64 __fastcall(PHANDLE FileHandle, ACCESS_MASK DesiredAccess, PCUNICODE_STRING SourceString)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006cf48`

## callees

- `0x18006d120`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x18006d210`
- `ntdll!RtlFreeUnicodeString` at `0x18006d21a`
- `ntdll!RtlFreeUnicodeString` at `0x18006d210`
- `ntdll!RtlFreeUnicodeString` at `0x18006d21a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18006d186`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18006d186`
- `ntdll!RtlDuplicateUnicodeString` at `0x18006d168`
- `ntdll!RtlDuplicateUnicodeString` at `0x18006d168`
- `ntdll!NtCreateFile` at `0x18006d204`
- `ntdll!NtCreateFile` at `0x18006d204`

## pseudocode

```c
__int64 __fastcall CscUmpNormalCreateFile(PHANDLE FileHandle, ACCESS_MASK DesiredAccess, PCUNICODE_STRING SourceString)
{
  NTSTATUS v5; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-61h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-51h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-41h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-31h] BYREF

  *FileHandle = 0;
  NtPathName = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  v5 = RtlDuplicateUnicodeString(1u, SourceString, &DestinationString);
  if ( v5 >= 0 )
  {
    if ( RtlDosPathNameToNtPathName_U(DestinationString.Buffer, &NtPathName, 0, 0) )
    {
      ObjectAttributes.Length = 48;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 64;
      ObjectAttributes.ObjectName = &NtPathName;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      v5 = NtCreateFile(FileHandle, DesiredAccess, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x20u, 0, 0);
    }
    else
    {
      v5 = -1073741811;
    }
  }
  RtlFreeUnicodeString(&NtPathName);
  RtlFreeUnicodeString(&DestinationString);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18006d120  push    rbp
0x18006d122  push    rbx
0x18006d123  push    rsi
0x18006d124  push    rdi
0x18006d125  lea     rbp, [rsp-7]
0x18006d12a  sub     rsp, 0C8h
0x18006d131  xorps   xmm0, xmm0
0x18006d134  mov     rdi, rcx
0x18006d137  xor     ecx, ecx
0x18006d139  mov     rax, r8
0x18006d13c  mov     esi, edx
0x18006d13e  lea     r8, [rbp+1Fh+DestinationString]; DestinationString
0x18006d142  xorps   xmm1, xmm1
0x18006d145  mov     rdx, rax; SourceString
0x18006d148  mov     [rdi], rcx
0x18006d14b  mov     ecx, 1; Flags
0x18006d150  movups  xmmword ptr [rbp+1Fh+ObjectAttributes.ObjectName], xmm0
0x18006d154  movups  xmmword ptr [rbp+1Fh+NtPathName.Length], xmm0
0x18006d158  movups  xmmword ptr [rbp+1Fh+DestinationString.Length], xmm1
0x18006d15c  movups  xmmword ptr [rbp+1Fh+ObjectAttributes.Length], xmm0
0x18006d160  movups  xmmword ptr [rbp+1Fh+ObjectAttributes+1Ch], xmm0
0x18006d164  movups  xmmword ptr [rbp+1Fh+IoStatusBlock], xmm0
0x18006d168  call    cs:__imp_RtlDuplicateUnicodeString
0x18006d16e  mov     ebx, eax
0x18006d170  test    eax, eax
0x18006d172  js      loc_18006D20C
0x18006d178  mov     rcx, [rbp+1Fh+DestinationString.Buffer]; DosPathName
0x18006d17c  lea     rdx, [rbp+1Fh+NtPathName]; NtPathName
0x18006d180  xor     r9d, r9d; DirectoryInfo
0x18006d183  xor     r8d, r8d; NtFileNamePart
0x18006d186  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18006d18c  test    al, al
0x18006d18e  jnz     short loc_18006D197
0x18006d190  mov     ebx, 0C000000Dh
0x18006d195  jmp     short loc_18006D20C
0x18006d197  mov     [rsp+0E0h+EaLength], 0; EaLength
0x18006d19f  lea     rax, [rbp+1Fh+NtPathName]
0x18006d1a3  mov     [rsp+0E0h+EaBuffer], 0; EaBuffer
0x18006d1ac  lea     r9, [rbp+1Fh+IoStatusBlock]; IoStatusBlock
0x18006d1b0  mov     [rsp+0E0h+CreateOptions], 20h ; ' '; CreateOptions
0x18006d1b8  lea     r8, [rbp+1Fh+ObjectAttributes]; ObjectAttributes
0x18006d1bc  mov     [rsp+0E0h+CreateDisposition], 1; CreateDisposition
0x18006d1c4  xorps   xmm0, xmm0
0x18006d1c7  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x18006d1cf  mov     edx, esi; DesiredAccess
0x18006d1d1  mov     [rsp+0E0h+FileAttributes], 80h; FileAttributes
0x18006d1d9  mov     rcx, rdi; FileHandle
0x18006d1dc  mov     [rsp+0E0h+AllocationSize], 0; AllocationSize
0x18006d1e5  mov     [rbp+1Fh+ObjectAttributes.Length], 30h ; '0'
0x18006d1ec  mov     [rbp+1Fh+ObjectAttributes.RootDirectory], 0
0x18006d1f4  mov     [rbp+1Fh+ObjectAttributes.Attributes], 40h ; '@'
0x18006d1fb  mov     [rbp+1Fh+ObjectAttributes.ObjectName], rax
0x18006d1ff  movdqu  xmmword ptr [rbp+1Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x18006d204  call    cs:__imp_NtCreateFile
0x18006d20a  mov     ebx, eax
0x18006d20c  lea     rcx, [rbp+1Fh+NtPathName]; UnicodeString
0x18006d210  call    cs:__imp_RtlFreeUnicodeString
0x18006d216  lea     rcx, [rbp+1Fh+DestinationString]; UnicodeString
0x18006d21a  call    cs:__imp_RtlFreeUnicodeString
0x18006d220  mov     eax, ebx
0x18006d222  add     rsp, 0C8h
0x18006d229  pop     rdi
0x18006d22a  pop     rsi
0x18006d22b  pop     rbx
0x18006d22c  pop     rbp
0x18006d22d  retn
```
