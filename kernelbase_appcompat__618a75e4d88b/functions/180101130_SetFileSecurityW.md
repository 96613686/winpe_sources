# SetFileSecurityW

- ea: `0x180101130`
- end: `0x1801012f2`
- name: `SetFileSecurityW`
- size: `450`
- prototype: `BOOL __stdcall(LPCWSTR lpFileName, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18004b9d0`
- `0x180101130`
- `0x180101300`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180101195`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x180101195`
- `ntdll!RtlReleaseRelativeName` at `0x18010121f`
- `ntdll!RtlReleaseRelativeName` at `0x18010121f`
- `ntdll!NtOpenFile` at `0x180101202`
- `ntdll!NtOpenFile` at `0x1801012df`
- `ntdll!NtOpenFile` at `0x180101202`
- `ntdll!NtOpenFile` at `0x1801012df`
- `ntdll!NtClose` at `0x180101268`
- `ntdll!NtClose` at `0x180101268`
- `ntdll!NtSetSecurityObject` at `0x180101256`
- `ntdll!NtSetSecurityObject` at `0x180101256`
- `ntdll!RtlFreeHeap` at `0x18010123d`
- `ntdll!RtlFreeHeap` at `0x18010123d`

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
0x180101130  push    rbp
0x180101132  push    rbx
0x180101133  push    rsi
0x180101134  push    rdi
0x180101135  push    r14
0x180101137  push    r15
0x180101139  lea     rbp, [rsp-2Fh]
0x18010113e  sub     rsp, 0B8h
0x180101145  xorps   xmm0, xmm0
0x180101148  mov     esi, edx
0x18010114a  xorps   xmm1, xmm1
0x18010114d  lea     rdx, [rbp+57h+DesiredAccess]; DesiredAccess
0x180101151  mov     rbx, rcx
0x180101154  xor     r15d, r15d
0x180101157  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18010115b  mov     ecx, esi; SecurityInformation
0x18010115d  mov     [rbp+57h+FileHandle], r15
0x180101161  xor     eax, eax
0x180101163  mov     [rbp+57h+DesiredAccess], r15d
0x180101167  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18010116b  mov     r14, r8
0x18010116e  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180101172  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x180101176  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x18010117a  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x18010117e  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180101182  call    SetSecurityAccessMask
0x180101187  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18010118b  xor     r8d, r8d; PartName
0x18010118e  lea     rdx, [rbp+57h+NtName]; NtName
0x180101192  mov     rcx, rbx; DosName
0x180101195  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18010119c  nop     dword ptr [rax+rax+00h]
0x1801011a1  test    al, al
0x1801011a3  jz      loc_1801012BC
0x1801011a9  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1801011ad  mov     rdi, [rbp+57h+NtName.Buffer]
0x1801011b1  test    ax, ax
0x1801011b4  jnz     loc_180101299
0x1801011ba  mov     eax, r15d
0x1801011bd  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1801011c1  mov     edx, [rbp+57h+DesiredAccess]; DesiredAccess
0x1801011c4  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1801011c8  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1801011cc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1801011d0  lea     rax, [rbp+57h+NtName]
0x1801011d4  mov     [rsp+0E0h+OpenOptions], 200000h; OpenOptions
0x1801011dc  xorps   xmm0, xmm0
0x1801011df  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1801011e3  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1801011e7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1801011ee  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1801011f5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1801011fa  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x180101202  call    cs:__imp_NtOpenFile
0x180101209  nop     dword ptr [rax+rax+00h]
0x18010120e  mov     ebx, eax
0x180101210  cmp     eax, 0C000000Dh
0x180101215  jz      loc_1801012C3
0x18010121b  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18010121f  call    cs:__imp_RtlReleaseRelativeName
0x180101226  nop     dword ptr [rax+rax+00h]
0x18010122b  mov     rcx, gs:60h
0x180101234  mov     r8, rdi; P
0x180101237  xor     edx, edx; Flags
0x180101239  mov     rcx, [rcx+30h]; HeapHandle
0x18010123d  call    cs:__imp_RtlFreeHeap
0x180101244  nop     dword ptr [rax+rax+00h]
0x180101249  test    ebx, ebx
0x18010124b  js      short loc_18010128E
0x18010124d  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180101251  mov     r8, r14; SecurityDescriptor
0x180101254  mov     edx, esi; SecurityInformation
0x180101256  call    cs:__imp_NtSetSecurityObject
0x18010125d  nop     dword ptr [rax+rax+00h]
0x180101262  mov     rcx, [rbp+57h+FileHandle]; Handle
0x180101266  mov     ebx, eax
0x180101268  call    cs:__imp_NtClose
0x18010126f  nop     dword ptr [rax+rax+00h]
0x180101274  test    ebx, ebx
0x180101276  js      short loc_18010128E
0x180101278  mov     eax, 1
0x18010127d  add     rsp, 0B8h
0x180101284  pop     r15
0x180101286  pop     r14
0x180101288  pop     rdi
0x180101289  pop     rsi
0x18010128a  pop     rbx
0x18010128b  pop     rbp
0x18010128c  retn
0x18010128e  mov     ecx, ebx
0x180101290  call    BaseSetLastNTError
0x180101295  xor     eax, eax
0x180101297  jmp     short loc_18010127D
0x180101299  mov     [rbp+57h+NtName.Length], ax
0x18010129d  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1801012a0  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1801012a3  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1801012a7  mov     word ptr [rbp+57h+NtName+6], ax
0x1801012ab  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1801012af  mov     [rbp+57h+NtName.Buffer], rax
0x1801012b3  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1801012b7  jmp     loc_1801011C1
0x1801012bc  mov     ecx, 0C0000033h
0x1801012c1  jmp     short loc_180101290
0x1801012c3  mov     edx, [rbp+57h+DesiredAccess]; DesiredAccess
0x1801012c6  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1801012ca  mov     [rsp+0E0h+OpenOptions], r15d; OpenOptions
0x1801012cf  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1801012d3  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1801012d7  mov     [rsp+0E0h+ShareAccess], 7; ShareAccess
0x1801012df  call    cs:__imp_NtOpenFile
0x1801012e6  nop     dword ptr [rax+rax+00h]
0x1801012eb  mov     ebx, eax
0x1801012ed  jmp     loc_18010121B
```
