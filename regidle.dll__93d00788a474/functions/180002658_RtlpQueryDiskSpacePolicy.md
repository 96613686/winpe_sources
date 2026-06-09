# RtlpQueryDiskSpacePolicy

- ea: `0x180002658`
- end: `0x1800027b7`
- name: `RtlpQueryDiskSpacePolicy`
- size: `351`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800021c0`

## callees

- `0x180002658`
- `0x1800027c0`
- `0x180002888`
- `0x1800029d0`

## import_xrefs

- `ntdll!NtCreateFile` at `0x180002763`
- `ntdll!NtCreateFile` at `0x180002763`
- `ntdll!NtClose` at `0x18000278d`
- `ntdll!NtClose` at `0x18000278d`

## pseudocode

```c
__int64 __fastcall RtlpQueryDiskSpacePolicy(__int64 a1, __int64 a2)
{
  wchar_t *v3; // rax
  __int64 v4; // rcx
  NTSTATUS DiskSpacePolicyByHandle; // ebx
  void *FileHandle; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v8; // [rsp+68h] [rbp-98h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t pszDest[264]; // [rsp+C0h] [rbp-40h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, 44);
  StringCbPrintfW(pszDest, 0x208u, L"\\??\\%s", a1);
  v3 = pszDest;
  v8 = 0;
  v4 = 0x7FFF;
  while ( *v3 )
  {
    ++v3;
    if ( !--v4 )
      goto LABEL_6;
  }
  LOWORD(v8) = -2 - 2 * v4;
  WORD1(v8) = -2 * v4;
  *((_QWORD *)&v8 + 1) = pszDest;
LABEL_6:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v8;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  DiskSpacePolicyByHandle = NtCreateFile(
                              &FileHandle,
                              0x100080u,
                              &ObjectAttributes,
                              &IoStatusBlock,
                              0,
                              0,
                              7u,
                              1u,
                              0x20u,
                              0,
                              0);
  if ( DiskSpacePolicyByHandle >= 0 )
  {
    DiskSpacePolicyByHandle = RtlpQueryDiskSpacePolicyByHandle(FileHandle, a2);
    if ( DiskSpacePolicyByHandle >= 0 )
      DiskSpacePolicyByHandle = 0;
  }
  if ( FileHandle )
    NtClose(FileHandle);
  return (unsigned int)DiskSpacePolicyByHandle;
}

```

## disassembly

```asm
0x180002658  mov     [rsp-8+arg_10], rbx
0x18000265d  push    rbp
0x18000265e  push    rsi
0x18000265f  push    rdi
0x180002660  lea     rbp, [rsp-1E0h]
0x180002668  sub     rsp, 2E0h
0x18000266f  mov     rax, cs:__security_cookie
0x180002676  xor     rax, rsp
0x180002679  mov     [rbp+1F0h+var_20], rax
0x180002680  xorps   xmm0, xmm0
0x180002683  lea     r8, aS; "\\??\\%s"
0x18000268a  mov     rdi, rdx
0x18000268d  xor     esi, esi
0x18000268f  mov     r9, rcx
0x180002692  mov     [rsp+2F0h+FileHandle], rsi
0x180002697  movups  xmmword ptr [rbp+1F0h+ObjectAttributes.ObjectName], xmm0
0x18000269b  xor     eax, eax
0x18000269d  lea     rcx, [rbp+1F0h+pszDest]; pszDest
0x1800026a1  mov     edx, 208h; cbDest
0x1800026a6  movups  xmmword ptr [rbp+1F0h+ObjectAttributes+1Ch], xmm0
0x1800026aa  movups  xmmword ptr [rbp+1F0h+IoStatusBlock], xmm0
0x1800026ae  movups  xmmword ptr [rsp+2F0h+ObjectAttributes.Length], xmm0
0x1800026b3  movups  [rsp+2F0h+var_288], xmm0
0x1800026b8  call    StringCbPrintfW
0x1800026bd  xorps   xmm0, xmm0
0x1800026c0  lea     rax, [rbp+1F0h+pszDest]
0x1800026c4  movups  [rsp+2F0h+var_288], xmm0
0x1800026c9  mov     ecx, 7FFFh
0x1800026ce  lea     edx, [rsi+2]
0x1800026d1  cmp     [rax], si
0x1800026d4  jz      short loc_1800026E1
0x1800026d6  add     rax, rdx
0x1800026d9  sub     rcx, 1
0x1800026dd  jnz     short loc_1800026D1
0x1800026df  jmp     short loc_180002702
0x1800026e1  add     cx, cx
0x1800026e4  mov     eax, 0FFFEh
0x1800026e9  sub     ax, cx
0x1800026ec  mov     word ptr [rsp+2F0h+var_288], ax
0x1800026f1  add     ax, dx
0x1800026f4  mov     word ptr [rsp+2F0h+var_288+2], ax
0x1800026f9  lea     rax, [rbp+1F0h+pszDest]
0x1800026fd  mov     qword ptr [rsp+2F0h+var_288+8], rax
0x180002702  mov     [rsp+2F0h+EaLength], esi; EaLength
0x180002706  lea     rax, [rsp+2F0h+var_288]
0x18000270b  mov     [rsp+2F0h+EaBuffer], rsi; EaBuffer
0x180002710  lea     r9, [rbp+1F0h+IoStatusBlock]; IoStatusBlock
0x180002714  mov     [rsp+2F0h+CreateOptions], 20h ; ' '; CreateOptions
0x18000271c  lea     r8, [rsp+2F0h+ObjectAttributes]; ObjectAttributes
0x180002721  mov     [rsp+2F0h+CreateDisposition], 1; CreateDisposition
0x180002729  lea     rcx, [rsp+2F0h+FileHandle]; FileHandle
0x18000272e  mov     [rsp+2F0h+ShareAccess], 7; ShareAccess
0x180002736  xorps   xmm0, xmm0
0x180002739  mov     [rsp+2F0h+FileAttributes], esi; FileAttributes
0x18000273d  mov     edx, 100080h; DesiredAccess
0x180002742  mov     [rsp+2F0h+AllocationSize], rsi; AllocationSize
0x180002747  mov     [rsp+2F0h+ObjectAttributes.Length], 30h ; '0'
0x18000274f  mov     [rbp+1F0h+ObjectAttributes.RootDirectory], rsi
0x180002753  mov     [rbp+1F0h+ObjectAttributes.Attributes], 40h ; '@'
0x18000275a  mov     [rbp+1F0h+ObjectAttributes.ObjectName], rax
0x18000275e  movdqu  xmmword ptr [rbp+1F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180002763  call    cs:__imp_NtCreateFile
0x180002769  mov     ebx, eax
0x18000276b  test    eax, eax
0x18000276d  js      short loc_180002783
0x18000276f  mov     rcx, [rsp+2F0h+FileHandle]
0x180002774  mov     rdx, rdi
0x180002777  call    RtlpQueryDiskSpacePolicyByHandle
0x18000277c  test    eax, eax
0x18000277e  mov     ebx, eax
0x180002780  cmovns  ebx, esi
0x180002783  mov     rcx, [rsp+2F0h+FileHandle]; Handle
0x180002788  test    rcx, rcx
0x18000278b  jz      short loc_180002793
0x18000278d  call    cs:__imp_NtClose
0x180002793  mov     eax, ebx
0x180002795  mov     rcx, [rbp+1F0h+var_20]
0x18000279c  xor     rcx, rsp; StackCookie
0x18000279f  call    __security_check_cookie
0x1800027a4  mov     rbx, [rsp+2F0h+arg_10]
0x1800027ac  add     rsp, 2E0h
0x1800027b3  pop     rdi
0x1800027b4  pop     rsi
0x1800027b5  pop     rbp
0x1800027b6  retn
```
