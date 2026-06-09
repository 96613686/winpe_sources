# BaseRegSaveKeyInternal

- ea: `0x18001d008`
- end: `0x18001d1e8`
- name: `BaseRegSaveKeyInternal`
- size: `480`
- prototype: `ULONG __fastcall(HANDLE KeyHandle, __int16 *, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019e50`

## callees

- `0x18001d008`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001d0c6`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001d0c6`
- `ntdll!RtlReleaseRelativeName` at `0x18001d182`
- `ntdll!RtlReleaseRelativeName` at `0x18001d182`
- `ntdll!NtSaveKey` at `0x18001d1ab`
- `ntdll!NtSaveKey` at `0x18001d1ab`
- `ntdll!NtCreateFile` at `0x18001d176`
- `ntdll!NtCreateFile` at `0x18001d176`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001d0a9`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001d0a9`
- `ntdll!RtlNtStatusToDosError` at `0x18001d1bf`
- `ntdll!RtlNtStatusToDosError` at `0x18001d1bf`
- `ntdll!NtClose` at `0x18001d1b7`
- `ntdll!NtClose` at `0x18001d1b7`
- `ntdll!RtlFreeHeap` at `0x18001d19a`
- `ntdll!RtlFreeHeap` at `0x18001d19a`

## pseudocode

```c
ULONG __fastcall BaseRegSaveKeyInternal(HANDLE KeyHandle, __int16 *a2, __int64 a3)
{
  __int16 v6; // ax
  void *v7; // rcx
  PWSTR Buffer; // rsi
  HANDLE ContainingDirectory; // rax
  int v10; // ebx
  struct _UNICODE_STRING NtName; // [rsp+60h] [rbp-39h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-29h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-19h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+100h] [rbp+67h] BYREF

  FileHandle = 0;
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !KeyHandle )
    return 87;
  if ( !a2 )
    return 87;
  if ( !*((_QWORD *)a2 + 1) )
    return 87;
  v6 = *a2;
  if ( (*a2 & 1) != 0 )
    return 87;
  if ( v6 )
    *a2 = v6 - 2;
  if ( a3 )
  {
    v7 = *(void **)(a3 + 8);
    if ( !v7 || !RtlValidRelativeSecurityDescriptor(v7, *(_DWORD *)(a3 + 16), 0) )
      return 87;
  }
  if ( !RtlDosPathNameToRelativeNtPathName_U(*((PCWSTR *)a2 + 1), &NtName, 0, &RelativeName) )
    return 87;
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
  if ( a3 )
    ObjectAttributes.SecurityDescriptor = *(PVOID *)(a3 + 8);
  else
    ObjectAttributes.SecurityDescriptor = 0;
  ObjectAttributes.SecurityQualityOfService = 0;
  v10 = NtCreateFile(&FileHandle, 0x40100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 2u, 0x4020u, 0, 0);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v10 >= 0 )
  {
    v10 = NtSaveKey(KeyHandle, FileHandle);
    NtClose(FileHandle);
  }
  return RtlNtStatusToDosError(v10);
}

```

## disassembly

```asm
0x18001d008  mov     [rsp-8+arg_8], rbx
0x18001d00d  mov     [rsp-8+arg_10], rsi
0x18001d012  push    rbp
0x18001d013  push    rdi
0x18001d014  push    r12
0x18001d016  push    r14
0x18001d018  push    r15
0x18001d01a  lea     rbp, [rsp-37h]
0x18001d01f  sub     rsp, 0D0h
0x18001d026  xorps   xmm0, xmm0
0x18001d029  xor     r15d, r15d
0x18001d02c  xorps   xmm1, xmm1
0x18001d02f  mov     [rbp+57h+FileHandle], r15
0x18001d033  xor     eax, eax
0x18001d035  mov     rdi, r8
0x18001d038  mov     rbx, rdx
0x18001d03b  mov     r14, rcx
0x18001d03e  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001d042  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001d046  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x18001d04a  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x18001d04e  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x18001d052  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001d056  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001d05a  test    rcx, rcx
0x18001d05d  jz      loc_18001D1C7
0x18001d063  test    rdx, rdx
0x18001d066  jz      loc_18001D1C7
0x18001d06c  cmp     [rdx+8], r15
0x18001d070  jz      loc_18001D1C7
0x18001d076  movzx   eax, word ptr [rdx]
0x18001d079  test    al, 1
0x18001d07b  jnz     loc_18001D1C7
0x18001d081  lea     r12d, [r15+2]
0x18001d085  test    ax, ax
0x18001d088  jz      short loc_18001D091
0x18001d08a  sub     ax, r12w
0x18001d08e  mov     [rdx], ax
0x18001d091  test    rdi, rdi
0x18001d094  jz      short loc_18001D0B7
0x18001d096  mov     rcx, [r8+8]; SecurityDescriptorInput
0x18001d09a  test    rcx, rcx
0x18001d09d  jz      loc_18001D1C7
0x18001d0a3  mov     edx, [rdi+10h]; SecurityDescriptorLength
0x18001d0a6  xor     r8d, r8d; RequiredInformation
0x18001d0a9  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18001d0af  test    al, al
0x18001d0b1  jz      loc_18001D1C7
0x18001d0b7  mov     rcx, [rbx+8]; DosName
0x18001d0bb  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18001d0bf  xor     r8d, r8d; PartName
0x18001d0c2  lea     rdx, [rbp+57h+NtName]; NtName
0x18001d0c6  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18001d0cc  test    al, al
0x18001d0ce  jz      loc_18001D1C7
0x18001d0d4  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18001d0d8  mov     rsi, [rbp+57h+NtName.Buffer]
0x18001d0dc  test    ax, ax
0x18001d0df  jz      short loc_18001D101
0x18001d0e1  mov     [rbp+57h+NtName.Length], ax
0x18001d0e5  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18001d0e8  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x18001d0eb  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18001d0ef  mov     word ptr [rbp+57h+NtName+6], ax
0x18001d0f3  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18001d0f7  mov     [rbp+57h+NtName.Buffer], rax
0x18001d0fb  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18001d0ff  jmp     short loc_18001D108
0x18001d101  mov     rax, r15
0x18001d104  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18001d108  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18001d10c  lea     rax, [rbp+57h+NtName]
0x18001d110  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001d114  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001d11b  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001d122  test    rdi, rdi
0x18001d125  jz      short loc_18001D131
0x18001d127  mov     rax, [rdi+8]
0x18001d12b  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18001d12f  jmp     short loc_18001D135
0x18001d131  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r15
0x18001d135  mov     [rsp+0F0h+EaLength], r15d; EaLength
0x18001d13a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001d13e  mov     [rsp+0F0h+EaBuffer], r15; EaBuffer
0x18001d143  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001d147  mov     [rsp+0F0h+CreateOptions], 4020h; CreateOptions
0x18001d14f  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001d153  mov     [rsp+0F0h+CreateDisposition], r12d; CreateDisposition
0x18001d158  mov     edx, 40100000h; DesiredAccess
0x18001d15d  mov     [rsp+0F0h+ShareAccess], 1; ShareAccess
0x18001d165  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x18001d16d  mov     [rsp+0F0h+AllocationSize], r15; AllocationSize
0x18001d172  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r15
0x18001d176  call    cs:__imp_NtCreateFile
0x18001d17c  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18001d180  mov     ebx, eax
0x18001d182  call    cs:__imp_RtlReleaseRelativeName
0x18001d188  mov     rcx, gs:60h
0x18001d191  mov     r8, rsi; P
0x18001d194  xor     edx, edx; Flags
0x18001d196  mov     rcx, [rcx+30h]; HeapHandle
0x18001d19a  call    cs:__imp_RtlFreeHeap
0x18001d1a0  test    ebx, ebx
0x18001d1a2  js      short loc_18001D1BD
0x18001d1a4  mov     rdx, [rbp+57h+FileHandle]; FileHandle
0x18001d1a8  mov     rcx, r14; KeyHandle
0x18001d1ab  call    cs:__imp_NtSaveKey
0x18001d1b1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18001d1b5  mov     ebx, eax
0x18001d1b7  call    cs:__imp_NtClose
0x18001d1bd  mov     ecx, ebx; Status
0x18001d1bf  call    cs:__imp_RtlNtStatusToDosError
0x18001d1c5  jmp     short loc_18001D1CC
0x18001d1c7  mov     eax, 57h ; 'W'
0x18001d1cc  lea     r11, [rsp+0F0h+var_20]
0x18001d1d4  mov     rbx, [r11+38h]
0x18001d1d8  mov     rsi, [r11+40h]
0x18001d1dc  mov     rsp, r11
0x18001d1df  pop     r15
0x18001d1e1  pop     r14
0x18001d1e3  pop     r12
0x18001d1e5  pop     rdi
0x18001d1e6  pop     rbp
0x18001d1e7  retn
```
