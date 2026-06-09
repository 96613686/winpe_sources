# CiSetCatalogHintByFilePath

- ea: `0x18002be54`
- end: `0x18002c000`
- name: `CiSetCatalogHintByFilePath`
- size: `428`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002b8d0`

## callees

- `0x18002be54`

## import_xrefs

- `ntdll!NtWaitForSingleObject` at `0x18002bf91`
- `ntdll!NtWaitForSingleObject` at `0x18002bf91`
- `ntdll!NtCreateFile` at `0x18002bf49`
- `ntdll!NtCreateFile` at `0x18002bf49`
- `ntdll!RtlFreeHeap` at `0x18002bfd1`
- `ntdll!RtlFreeHeap` at `0x18002bfd1`
- `ntdll!NtClose` at `0x18002bfae`
- `ntdll!NtClose` at `0x18002bfae`
- `ntdll!RtlReleaseRelativeName` at `0x18002bfe1`
- `ntdll!RtlReleaseRelativeName` at `0x18002bfe1`
- `ntdll!NtSetEaFile` at `0x18002bf74`
- `ntdll!NtSetEaFile` at `0x18002bf74`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18002be9f`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U_WithStatus` at `0x18002be9f`

## pseudocode

```c
__int64 __fastcall CiSetCatalogHintByFilePath(__int64 a1, ULONG *a2)
{
  __int64 result; // rax
  PVOID v4; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS Status; // ebx
  void *v7; // rsi
  ULONG v8; // r9d
  PVOID P[2]; // [rsp+60h] [rbp-59h] BYREF
  struct _IO_STATUS_BLOCK v10; // [rsp+70h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-39h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+90h] [rbp-29h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+130h] [rbp+77h] BYREF

  FileHandle = 0;
  *(_OWORD *)P = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(&RelativeName, 0, sizeof(RelativeName));
  result = RtlDosPathNameToRelativeNtPathName_U_WithStatus(a1, P, 0, &RelativeName);
  if ( (int)result >= 0 )
  {
    v4 = P[1];
    if ( RelativeName.RelativeName.Length )
    {
      LOWORD(P[0]) = RelativeName.RelativeName.Length;
      *(_DWORD *)((char *)P + 2) = *(_DWORD *)&RelativeName.RelativeName.MaximumLength;
      HIWORD(P[0]) = *(&RelativeName.RelativeName.MaximumLength + 2);
      P[1] = RelativeName.RelativeName.Buffer;
      ContainingDirectory = RelativeName.ContainingDirectory;
    }
    else
    {
      ContainingDirectory = 0;
      RelativeName.ContainingDirectory = 0;
    }
    ObjectAttributes.RootDirectory = ContainingDirectory;
    ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)P;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    Status = NtCreateFile(&FileHandle, 0x100010u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x4060u, 0, 0);
    if ( Status >= 0 )
    {
      v7 = FileHandle;
      v8 = *a2;
      v10 = 0;
      Status = NtSetEaFile(FileHandle, &v10, a2 + 1, v8);
      if ( Status == 259 )
      {
        Status = NtWaitForSingleObject(v7, 0, 0);
        if ( Status >= 0 )
          Status = v10.Status;
      }
    }
    if ( FileHandle )
      NtClose(FileHandle);
    if ( v4 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v4);
    RtlReleaseRelativeName(&RelativeName);
    return (unsigned int)Status;
  }
  return result;
}

```

## disassembly

```asm
0x18002be54  push    rbp
0x18002be56  push    rbx
0x18002be57  push    rsi
0x18002be58  push    rdi
0x18002be59  push    r14
0x18002be5b  push    r15
0x18002be5d  lea     rbp, [rsp-2Fh]
0x18002be62  sub     rsp, 0E8h
0x18002be69  xorps   xmm0, xmm0
0x18002be6c  lea     r9, [rbp+57h+RelativeName]
0x18002be70  mov     r14, rdx
0x18002be73  xor     r15d, r15d
0x18002be76  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18002be7a  xor     eax, eax
0x18002be7c  mov     [rbp+57h+FileHandle], r15
0x18002be80  xor     r8d, r8d
0x18002be83  lea     rdx, [rbp+57h+P]
0x18002be87  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18002be8b  movups  xmmword ptr [rbp+57h+P], xmm0
0x18002be8f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18002be93  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18002be97  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x18002be9b  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x18002be9f  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U_WithStatus
0x18002bea6  nop     dword ptr [rax+rax+00h]
0x18002beab  test    eax, eax
0x18002bead  js      loc_18002BFEF
0x18002beb3  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18002beb7  mov     rdi, [rbp+57h+P+8]
0x18002bebb  test    ax, ax
0x18002bebe  jz      short loc_18002BEE0
0x18002bec0  mov     word ptr [rbp+57h+P], ax
0x18002bec4  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18002bec7  mov     dword ptr [rbp+57h+P+2], eax
0x18002beca  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18002bece  mov     word ptr [rbp+57h+P+6], ax
0x18002bed2  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18002bed6  mov     [rbp+57h+P+8], rax
0x18002beda  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18002bede  jmp     short loc_18002BEE7
0x18002bee0  mov     rax, r15
0x18002bee3  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18002bee7  mov     [rsp+110h+EaLength], r15d; EaLength
0x18002beec  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18002bef0  mov     [rsp+110h+EaBuffer], r15; EaBuffer
0x18002bef5  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18002bef9  mov     [rsp+110h+CreateOptions], 4060h; CreateOptions
0x18002bf01  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002bf05  mov     [rsp+110h+CreateDisposition], 1; CreateDisposition
0x18002bf0d  xorps   xmm0, xmm0
0x18002bf10  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18002bf14  mov     edx, 100010h; DesiredAccess
0x18002bf19  mov     [rsp+110h+ShareAccess], 7; ShareAccess
0x18002bf21  lea     rax, [rbp+57h+P]
0x18002bf25  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x18002bf2d  mov     [rsp+110h+AllocationSize], r15; AllocationSize
0x18002bf32  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18002bf39  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18002bf40  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18002bf44  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18002bf49  call    cs:__imp_NtCreateFile
0x18002bf50  nop     dword ptr [rax+rax+00h]
0x18002bf55  mov     ebx, eax
0x18002bf57  test    eax, eax
0x18002bf59  js      short loc_18002BFA5
0x18002bf5b  mov     rsi, [rbp+57h+FileHandle]
0x18002bf5f  lea     r8, [r14+4]; EaBuffer
0x18002bf63  mov     r9d, [r14]; EaBufferSize
0x18002bf66  lea     rdx, [rbp+57h+var_A0]; IoStatusBlock
0x18002bf6a  xorps   xmm0, xmm0
0x18002bf6d  mov     rcx, rsi; FileHandle
0x18002bf70  movups  xmmword ptr [rbp+57h+var_A0], xmm0
0x18002bf74  call    cs:__imp_NtSetEaFile
0x18002bf7b  nop     dword ptr [rax+rax+00h]
0x18002bf80  mov     ebx, eax
0x18002bf82  cmp     eax, 103h
0x18002bf87  jnz     short loc_18002BFA5
0x18002bf89  xor     r8d, r8d; Timeout
0x18002bf8c  xor     edx, edx; Alertable
0x18002bf8e  mov     rcx, rsi; Handle
0x18002bf91  call    cs:__imp_NtWaitForSingleObject
0x18002bf98  nop     dword ptr [rax+rax+00h]
0x18002bf9d  test    eax, eax
0x18002bf9f  mov     ebx, eax
0x18002bfa1  cmovns  ebx, dword ptr [rbp+57h+var_A0]
0x18002bfa5  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18002bfa9  test    rcx, rcx
0x18002bfac  jz      short loc_18002BFBA
0x18002bfae  call    cs:__imp_NtClose
0x18002bfb5  nop     dword ptr [rax+rax+00h]
0x18002bfba  test    rdi, rdi
0x18002bfbd  jz      short loc_18002BFDD
0x18002bfbf  mov     rcx, gs:60h
0x18002bfc8  mov     r8, rdi; P
0x18002bfcb  xor     edx, edx; Flags
0x18002bfcd  mov     rcx, [rcx+30h]; HeapHandle
0x18002bfd1  call    cs:__imp_RtlFreeHeap
0x18002bfd8  nop     dword ptr [rax+rax+00h]
0x18002bfdd  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18002bfe1  call    cs:__imp_RtlReleaseRelativeName
0x18002bfe8  nop     dword ptr [rax+rax+00h]
0x18002bfed  mov     eax, ebx
0x18002bfef  add     rsp, 0E8h
0x18002bff6  pop     r15
0x18002bff8  pop     r14
0x18002bffa  pop     rdi
0x18002bffb  pop     rsi
0x18002bffc  pop     rbx
0x18002bffd  pop     rbp
0x18002bffe  retn
```
