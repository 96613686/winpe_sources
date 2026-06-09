# BaseRegSaveKeyExInternal

- ea: `0x18001ce28`
- end: `0x18001d002`
- name: `BaseRegSaveKeyExInternal`
- size: `474`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180019f20`

## callees

- `0x18001ce28`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001cee5`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001cee5`
- `ntdll!RtlReleaseRelativeName` at `0x18001cfa1`
- `ntdll!RtlReleaseRelativeName` at `0x18001cfa1`
- `ntdll!NtSaveKeyEx` at `0x18001cfcd`
- `ntdll!NtSaveKeyEx` at `0x18001cfcd`
- `ntdll!NtCreateFile` at `0x18001cf95`
- `ntdll!NtCreateFile` at `0x18001cf95`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001cec8`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18001cec8`
- `ntdll!RtlNtStatusToDosError` at `0x18001cfe1`
- `ntdll!RtlNtStatusToDosError` at `0x18001cfe1`
- `ntdll!NtClose` at `0x18001cfd9`
- `ntdll!NtClose` at `0x18001cfd9`
- `ntdll!RtlFreeHeap` at `0x18001cfb9`
- `ntdll!RtlFreeHeap` at `0x18001cfb9`

## pseudocode

```c
ULONG __fastcall BaseRegSaveKeyExInternal(HANDLE KeyHandle, __int16 *a2, __int64 a3, ULONG a4)
{
  __int16 v8; // ax
  void *v9; // rcx
  PWSTR Buffer; // rsi
  HANDLE ContainingDirectory; // rax
  int v12; // ebx
  struct _UNICODE_STRING NtName; // [rsp+60h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-49h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-19h] BYREF
  void *FileHandle; // [rsp+120h] [rbp+67h] BYREF

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
  v8 = *a2;
  if ( (*a2 & 1) != 0 )
    return 87;
  if ( v8 )
    *a2 = v8 - 2;
  if ( a3 )
  {
    v9 = *(void **)(a3 + 8);
    if ( !v9 || !RtlValidRelativeSecurityDescriptor(v9, *(_DWORD *)(a3 + 16), 0) )
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
  v12 = NtCreateFile(&FileHandle, 0x40100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 2u, 0x4020u, 0, 0);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v12 >= 0 )
  {
    v12 = NtSaveKeyEx(KeyHandle, FileHandle, a4);
    NtClose(FileHandle);
  }
  return RtlNtStatusToDosError(v12);
}

```

## disassembly

```asm
0x18001ce28  push    rbp
0x18001ce2a  push    rbx
0x18001ce2b  push    rsi
0x18001ce2c  push    rdi
0x18001ce2d  push    r12
0x18001ce2f  push    r13
0x18001ce31  push    r14
0x18001ce33  push    r15
0x18001ce35  lea     rbp, [rsp-1Fh]
0x18001ce3a  sub     rsp, 0D8h
0x18001ce41  xorps   xmm0, xmm0
0x18001ce44  xor     r12d, r12d
0x18001ce47  xorps   xmm1, xmm1
0x18001ce4a  mov     [rbp+57h+FileHandle], r12
0x18001ce4e  xor     eax, eax
0x18001ce50  mov     r15d, r9d
0x18001ce53  mov     rdi, r8
0x18001ce56  mov     rbx, rdx
0x18001ce59  mov     r14, rcx
0x18001ce5c  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001ce60  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001ce64  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x18001ce68  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x18001ce6c  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x18001ce70  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001ce74  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001ce78  test    rcx, rcx
0x18001ce7b  jz      loc_18001CFE9
0x18001ce81  test    rdx, rdx
0x18001ce84  jz      loc_18001CFE9
0x18001ce8a  cmp     [rdx+8], r12
0x18001ce8e  jz      loc_18001CFE9
0x18001ce94  movzx   eax, word ptr [rdx]
0x18001ce97  test    al, 1
0x18001ce99  jnz     loc_18001CFE9
0x18001ce9f  lea     r13d, [r12+2]
0x18001cea4  test    ax, ax
0x18001cea7  jz      short loc_18001CEB0
0x18001cea9  sub     ax, r13w
0x18001cead  mov     [rdx], ax
0x18001ceb0  test    rdi, rdi
0x18001ceb3  jz      short loc_18001CED6
0x18001ceb5  mov     rcx, [r8+8]; SecurityDescriptorInput
0x18001ceb9  test    rcx, rcx
0x18001cebc  jz      loc_18001CFE9
0x18001cec2  mov     edx, [rdi+10h]; SecurityDescriptorLength
0x18001cec5  xor     r8d, r8d; RequiredInformation
0x18001cec8  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18001cece  test    al, al
0x18001ced0  jz      loc_18001CFE9
0x18001ced6  mov     rcx, [rbx+8]; DosName
0x18001ceda  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18001cede  xor     r8d, r8d; PartName
0x18001cee1  lea     rdx, [rbp+57h+NtName]; NtName
0x18001cee5  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18001ceeb  test    al, al
0x18001ceed  jz      loc_18001CFE9
0x18001cef3  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18001cef7  mov     rsi, [rbp+57h+NtName.Buffer]
0x18001cefb  test    ax, ax
0x18001cefe  jz      short loc_18001CF20
0x18001cf00  mov     [rbp+57h+NtName.Length], ax
0x18001cf04  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18001cf07  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x18001cf0a  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18001cf0e  mov     word ptr [rbp+57h+NtName+6], ax
0x18001cf12  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18001cf16  mov     [rbp+57h+NtName.Buffer], rax
0x18001cf1a  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18001cf1e  jmp     short loc_18001CF27
0x18001cf20  mov     rax, r12
0x18001cf23  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18001cf27  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18001cf2b  lea     rax, [rbp+57h+NtName]
0x18001cf2f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001cf33  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001cf3a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001cf41  test    rdi, rdi
0x18001cf44  jz      short loc_18001CF50
0x18001cf46  mov     rax, [rdi+8]
0x18001cf4a  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18001cf4e  jmp     short loc_18001CF54
0x18001cf50  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r12
0x18001cf54  mov     [rsp+110h+EaLength], r12d; EaLength
0x18001cf59  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001cf5d  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x18001cf62  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001cf66  mov     [rsp+110h+CreateOptions], 4020h; CreateOptions
0x18001cf6e  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001cf72  mov     [rsp+110h+CreateDisposition], r13d; CreateDisposition
0x18001cf77  mov     edx, 40100000h; DesiredAccess
0x18001cf7c  mov     [rsp+110h+ShareAccess], 1; ShareAccess
0x18001cf84  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x18001cf8c  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x18001cf91  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r12
0x18001cf95  call    cs:__imp_NtCreateFile
0x18001cf9b  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18001cf9f  mov     ebx, eax
0x18001cfa1  call    cs:__imp_RtlReleaseRelativeName
0x18001cfa7  mov     rcx, gs:60h
0x18001cfb0  mov     r8, rsi; P
0x18001cfb3  xor     edx, edx; Flags
0x18001cfb5  mov     rcx, [rcx+30h]; HeapHandle
0x18001cfb9  call    cs:__imp_RtlFreeHeap
0x18001cfbf  test    ebx, ebx
0x18001cfc1  js      short loc_18001CFDF
0x18001cfc3  mov     rdx, [rbp+57h+FileHandle]; FileHandle
0x18001cfc7  mov     r8d, r15d; Flags
0x18001cfca  mov     rcx, r14; KeyHandle
0x18001cfcd  call    cs:__imp_NtSaveKeyEx
0x18001cfd3  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18001cfd7  mov     ebx, eax
0x18001cfd9  call    cs:__imp_NtClose
0x18001cfdf  mov     ecx, ebx; Status
0x18001cfe1  call    cs:__imp_RtlNtStatusToDosError
0x18001cfe7  jmp     short loc_18001CFEE
0x18001cfe9  mov     eax, 57h ; 'W'
0x18001cfee  add     rsp, 0D8h
0x18001cff5  pop     r15
0x18001cff7  pop     r14
0x18001cff9  pop     r13
0x18001cffb  pop     r12
0x18001cffd  pop     rdi
0x18001cffe  pop     rsi
0x18001cfff  pop     rbx
0x18001d000  pop     rbp
0x18001d001  retn
```
