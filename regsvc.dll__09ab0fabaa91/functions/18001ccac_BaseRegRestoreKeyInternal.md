# BaseRegRestoreKeyInternal

- ea: `0x18001ccac`
- end: `0x18001ce21`
- name: `BaseRegRestoreKeyInternal`
- size: `373`
- prototype: `ULONG __fastcall(HANDLE KeyHandle, __int16 *, ULONG)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180019d80`

## callees

- `0x18001ccac`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001cd33`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x18001cd33`
- `ntdll!RtlReleaseRelativeName` at `0x18001cdc4`
- `ntdll!RtlReleaseRelativeName` at `0x18001cdc4`
- `ntdll!NtRestoreKey` at `0x18001cdf0`
- `ntdll!NtRestoreKey` at `0x18001cdf0`
- `ntdll!NtOpenFile` at `0x18001cdb8`
- `ntdll!NtOpenFile` at `0x18001cdb8`
- `ntdll!RtlNtStatusToDosError` at `0x18001ce04`
- `ntdll!RtlNtStatusToDosError` at `0x18001ce04`
- `ntdll!NtClose` at `0x18001cdfc`
- `ntdll!NtClose` at `0x18001cdfc`
- `ntdll!RtlFreeHeap` at `0x18001cddc`
- `ntdll!RtlFreeHeap` at `0x18001cddc`

## pseudocode

```c
ULONG __fastcall BaseRegRestoreKeyInternal(HANDLE KeyHandle, __int16 *a2, ULONG a3)
{
  const WCHAR *v5; // rcx
  __int16 v6; // ax
  PWSTR Buffer; // rsi
  HANDLE ContainingDirectory; // rax
  int v9; // ebx
  struct _UNICODE_STRING NtName; // [rsp+30h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-39h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+50h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-9h] BYREF
  void *FileHandle; // [rsp+E0h] [rbp+67h] BYREF

  FileHandle = 0;
  NtName = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !KeyHandle )
    return 87;
  if ( !a2 )
    return 87;
  v5 = (const WCHAR *)*((_QWORD *)a2 + 1);
  if ( !v5 )
    return 87;
  v6 = *a2;
  if ( (*a2 & 1) != 0 )
    return 87;
  if ( v6 )
    *a2 = v6 - 2;
  if ( !RtlDosPathNameToRelativeNtPathName_U(v5, &NtName, 0, &RelativeName) )
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
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenFile(&FileHandle, 0x80100000, &ObjectAttributes, &IoStatusBlock, 1u, 0x20u);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v9 >= 0 )
  {
    v9 = NtRestoreKey(KeyHandle, FileHandle, a3);
    NtClose(FileHandle);
  }
  return RtlNtStatusToDosError(v9);
}

```

## disassembly

```asm
0x18001ccac  push    rbp
0x18001ccae  push    rbx
0x18001ccaf  push    rsi
0x18001ccb0  push    rdi
0x18001ccb1  push    r14
0x18001ccb3  push    r15
0x18001ccb5  lea     rbp, [rsp-2Fh]
0x18001ccba  sub     rsp, 0A8h
0x18001ccc1  xorps   xmm0, xmm0
0x18001ccc4  xor     r15d, r15d
0x18001ccc7  xorps   xmm1, xmm1
0x18001ccca  mov     [rbp+57h+FileHandle], r15
0x18001ccce  xor     eax, eax
0x18001ccd0  mov     r14d, r8d
0x18001ccd3  mov     rdi, rcx
0x18001ccd6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18001ccda  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18001ccde  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x18001cce2  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm1
0x18001cce6  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm1
0x18001ccea  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18001ccee  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18001ccf2  test    rcx, rcx
0x18001ccf5  jz      loc_18001CE0C
0x18001ccfb  test    rdx, rdx
0x18001ccfe  jz      loc_18001CE0C
0x18001cd04  mov     rcx, [rdx+8]; DosName
0x18001cd08  test    rcx, rcx
0x18001cd0b  jz      loc_18001CE0C
0x18001cd11  movzx   eax, word ptr [rdx]
0x18001cd14  test    al, 1
0x18001cd16  jnz     loc_18001CE0C
0x18001cd1c  test    ax, ax
0x18001cd1f  jz      short loc_18001CD28
0x18001cd21  sub     ax, 2
0x18001cd25  mov     [rdx], ax
0x18001cd28  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x18001cd2c  xor     r8d, r8d; PartName
0x18001cd2f  lea     rdx, [rbp+57h+NtName]; NtName
0x18001cd33  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x18001cd39  test    al, al
0x18001cd3b  jz      loc_18001CE0C
0x18001cd41  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x18001cd45  mov     rsi, [rbp+57h+NtName.Buffer]
0x18001cd49  test    ax, ax
0x18001cd4c  jz      short loc_18001CD6E
0x18001cd4e  mov     [rbp+57h+NtName.Length], ax
0x18001cd52  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x18001cd55  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x18001cd58  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x18001cd5c  mov     word ptr [rbp+57h+NtName+6], ax
0x18001cd60  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18001cd64  mov     [rbp+57h+NtName.Buffer], rax
0x18001cd68  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x18001cd6c  jmp     short loc_18001CD75
0x18001cd6e  mov     rax, r15
0x18001cd71  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x18001cd75  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18001cd79  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18001cd7d  lea     rax, [rbp+57h+NtName]
0x18001cd81  mov     [rsp+0D0h+OpenOptions], 20h ; ' '; OpenOptions
0x18001cd89  xorps   xmm0, xmm0
0x18001cd8c  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001cd90  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18001cd94  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18001cd9b  mov     edx, 80100000h; DesiredAccess
0x18001cda0  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18001cda7  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001cdab  mov     [rsp+0D0h+ShareAccess], 1; ShareAccess
0x18001cdb3  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001cdb8  call    cs:__imp_NtOpenFile
0x18001cdbe  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x18001cdc2  mov     ebx, eax
0x18001cdc4  call    cs:__imp_RtlReleaseRelativeName
0x18001cdca  mov     rcx, gs:60h
0x18001cdd3  mov     r8, rsi; P
0x18001cdd6  xor     edx, edx; Flags
0x18001cdd8  mov     rcx, [rcx+30h]; HeapHandle
0x18001cddc  call    cs:__imp_RtlFreeHeap
0x18001cde2  test    ebx, ebx
0x18001cde4  js      short loc_18001CE02
0x18001cde6  mov     rdx, [rbp+57h+FileHandle]; FileHandle
0x18001cdea  mov     r8d, r14d; RestoreFlags
0x18001cded  mov     rcx, rdi; KeyHandle
0x18001cdf0  call    cs:__imp_NtRestoreKey
0x18001cdf6  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18001cdfa  mov     ebx, eax
0x18001cdfc  call    cs:__imp_NtClose
0x18001ce02  mov     ecx, ebx; Status
0x18001ce04  call    cs:__imp_RtlNtStatusToDosError
0x18001ce0a  jmp     short loc_18001CE11
0x18001ce0c  mov     eax, 57h ; 'W'
0x18001ce11  add     rsp, 0A8h
0x18001ce18  pop     r15
0x18001ce1a  pop     r14
0x18001ce1c  pop     rdi
0x18001ce1d  pop     rsi
0x18001ce1e  pop     rbx
0x18001ce1f  pop     rbp
0x18001ce20  retn
```
