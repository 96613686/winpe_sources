# BaseRegSaveKeyExInternal

- ea: `0x18010d584`
- end: `0x18010d7a3`
- name: `BaseRegSaveKeyExInternal`
- size: `543`
- prototype: `__int64 __fastcall(HANDLE KeyHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18010d3f0`
- `0x18014ab20`

## callees

- `0x18010d584`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18010d614`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18010d614`
- `ntdll!RtlReleaseRelativeName` at `0x18010d6d0`
- `ntdll!RtlReleaseRelativeName` at `0x18010d6d0`
- `ntdll!NtCreateFile` at `0x18010d6be`
- `ntdll!NtCreateFile` at `0x18010d6be`
- `ntdll!RtlNtStatusToDosError` at `0x18010d700`
- `ntdll!RtlNtStatusToDosError` at `0x18010d700`
- `ntdll!NtClose` at `0x18010d71f`
- `ntdll!NtClose` at `0x18010d71f`
- `ntdll!RtlFreeHeap` at `0x18010d6ee`
- `ntdll!RtlFreeHeap` at `0x18010d6ee`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18010d75a`
- `ntdll!RtlValidRelativeSecurityDescriptor` at `0x18010d75a`
- `ntdll!NtSaveKeyEx` at `0x18010d737`
- `ntdll!NtSaveKeyEx` at `0x18010d737`

## pseudocode

```c
ULONG __fastcall BaseRegSaveKeyExInternal(HANDLE KeyHandle, __int16 *a2, __int64 a3, ULONG a4)
{
  __int16 v8; // ax
  PWSTR Buffer; // r14
  HANDLE ContainingDirectory; // rax
  int v12; // ebx
  void *v13; // rcx
  struct _UNICODE_STRING NtName; // [rsp+60h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-49h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-39h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp-19h] BYREF
  HANDLE FileHandle; // [rsp+120h] [rbp+67h] BYREF

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
    v13 = *(void **)(a3 + 8);
    if ( !v13 || !RtlValidRelativeSecurityDescriptor(v13, *(_DWORD *)(a3 + 16), 0) )
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
    if ( ((unsigned __int8)KeyHandle & 2) != 0 )
      v12 = -1073741811;
    else
      v12 = NtSaveKeyEx(KeyHandle, FileHandle, a4);
    NtClose(FileHandle);
  }
  return RtlNtStatusToDosError(v12);
}

```

## disassembly

```asm
0x18010d584  push    rbp
0x18010d586  push    rbx
0x18010d587  push    rsi
0x18010d588  push    rdi
0x18010d589  push    r12
0x18010d58b  push    r13
0x18010d58d  push    r14
0x18010d58f  push    r15
0x18010d591  lea     rbp, [rsp-1Fh]
0x18010d596  sub     rsp, 0D8h
0x18010d59d  xorps   xmm0, xmm0
0x18010d5a0  xor     r12d, r12d
0x18010d5a3  xorps   xmm1, xmm1
0x18010d5a6  mov     [rbp+57h+FileHandle], r12
0x18010d5aa  xor     eax, eax
0x18010d5ac  mov     r15d, r9d
0x18010d5af  mov     rdi, r8
0x18010d5b2  mov     rbx, rdx
0x18010d5b5  mov     rsi, rcx
0x18010d5b8  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18010d5bc  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18010d5c0  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x18010d5c4  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x18010d5c8  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x18010d5cc  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18010d5d0  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18010d5d4  test    rcx, rcx
0x18010d5d7  jz      short loc_18010D624
0x18010d5d9  test    rdx, rdx
0x18010d5dc  jz      short loc_18010D624
0x18010d5de  cmp     [rdx+8], r12
0x18010d5e2  jz      short loc_18010D624
0x18010d5e4  movzx   eax, word ptr [rdx]
0x18010d5e7  test    al, 1
0x18010d5e9  jnz     short loc_18010D624
0x18010d5eb  lea     r13d, [r12+2]
0x18010d5f0  test    ax, ax
0x18010d5f3  jz      short loc_18010D5FC
0x18010d5f5  sub     ax, r13w
0x18010d5f9  mov     [rdx], ax
0x18010d5fc  test    rdi, rdi
0x18010d5ff  jnz     loc_18010D747
0x18010d605  mov     rcx, [rbx+8]; DosName
0x18010d609  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18010d60d  xor     r8d, r8d; PartName
0x18010d610  lea     rdx, [rbp+57h+NtName]; NtName
0x18010d614  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18010d61b  nop     dword ptr [rax+rax+00h]
0x18010d620  test    al, al
0x18010d622  jnz     short loc_18010D63E
0x18010d624  mov     eax, 57h ; 'W'
0x18010d629  add     rsp, 0D8h
0x18010d630  pop     r15
0x18010d632  pop     r14
0x18010d634  pop     r13
0x18010d636  pop     r12
0x18010d638  pop     rdi
0x18010d639  pop     rsi
0x18010d63a  pop     rbx
0x18010d63b  pop     rbp
0x18010d63c  retn
0x18010d63e  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18010d642  mov     r14, [rbp+57h+NtName.Buffer]
0x18010d646  test    ax, ax
0x18010d649  jnz     loc_18010D773
0x18010d64f  mov     rax, r12
0x18010d652  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18010d656  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18010d65a  lea     rax, [rbp+57h+NtName]
0x18010d65e  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18010d662  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18010d669  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18010d670  test    rdi, rdi
0x18010d673  jnz     loc_18010D796
0x18010d679  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], r12
0x18010d67d  mov     [rsp+110h+EaLength], r12d; EaLength
0x18010d682  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18010d686  mov     [rsp+110h+EaBuffer], r12; EaBuffer
0x18010d68b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18010d68f  mov     [rsp+110h+CreateOptions], 4020h; CreateOptions
0x18010d697  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18010d69b  mov     [rsp+110h+CreateDisposition], r13d; CreateDisposition
0x18010d6a0  mov     edx, 40100000h; DesiredAccess
0x18010d6a5  mov     [rsp+110h+ShareAccess], 1; ShareAccess
0x18010d6ad  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x18010d6b5  mov     [rsp+110h+AllocationSize], r12; AllocationSize
0x18010d6ba  mov     [rbp+57h+ObjectAttributes.SecurityQualityOfService], r12
0x18010d6be  call    cs:__imp_NtCreateFile
0x18010d6c5  nop     dword ptr [rax+rax+00h]
0x18010d6ca  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18010d6ce  mov     ebx, eax
0x18010d6d0  call    cs:__imp_RtlReleaseRelativeName
0x18010d6d7  nop     dword ptr [rax+rax+00h]
0x18010d6dc  mov     rcx, gs:60h
0x18010d6e5  mov     r8, r14; P
0x18010d6e8  xor     edx, edx; Flags
0x18010d6ea  mov     rcx, [rcx+30h]; HeapHandle
0x18010d6ee  call    cs:__imp_RtlFreeHeap
0x18010d6f5  nop     dword ptr [rax+rax+00h]
0x18010d6fa  test    ebx, ebx
0x18010d6fc  jns     short loc_18010D711
0x18010d6fe  mov     ecx, ebx; Status
0x18010d700  call    cs:__imp_RtlNtStatusToDosError
0x18010d707  nop     dword ptr [rax+rax+00h]
0x18010d70c  jmp     loc_18010D629
0x18010d711  test    r13b, sil
0x18010d714  jz      short loc_18010D72D
0x18010d716  mov     ebx, 0C000000Dh
0x18010d71b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18010d71f  call    cs:__imp_NtClose
0x18010d726  nop     dword ptr [rax+rax+00h]
0x18010d72b  jmp     short loc_18010D6FE
0x18010d72d  mov     rdx, [rbp+57h+FileHandle]; FileHandle
0x18010d731  mov     r8d, r15d; Flags
0x18010d734  mov     rcx, rsi; KeyHandle
0x18010d737  call    cs:__imp_NtSaveKeyEx
0x18010d73e  nop     dword ptr [rax+rax+00h]
0x18010d743  mov     ebx, eax
0x18010d745  jmp     short loc_18010D71B
0x18010d747  mov     rcx, [r8+8]; SecurityDescriptorInput
0x18010d74b  test    rcx, rcx
0x18010d74e  jz      loc_18010D624
0x18010d754  mov     edx, [rdi+10h]; SecurityDescriptorLength
0x18010d757  xor     r8d, r8d; RequiredInformation
0x18010d75a  call    cs:__imp_RtlValidRelativeSecurityDescriptor
0x18010d761  nop     dword ptr [rax+rax+00h]
0x18010d766  test    al, al
0x18010d768  jz      loc_18010D624
0x18010d76e  jmp     loc_18010D605
0x18010d773  mov     [rbp+57h+NtName.Length], ax
0x18010d777  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18010d77a  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x18010d77d  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18010d781  mov     word ptr [rbp+57h+NtName+6], ax
0x18010d785  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18010d789  mov     [rbp+57h+NtName.Buffer], rax
0x18010d78d  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18010d791  jmp     loc_18010D656
0x18010d796  mov     rax, [rdi+8]
0x18010d79a  mov     [rbp+57h+ObjectAttributes.SecurityDescriptor], rax
0x18010d79e  jmp     loc_18010D67D
```
