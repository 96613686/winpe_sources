# CreateSystemDirectory(ushort const *)

- ea: `0x1800140a0`
- end: `0x180014200`
- name: `?CreateSystemDirectory@@YAKPEBG@Z`
- size: `352`
- prototype: `ULONG __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180008a44`

## callees

- `0x1800140a0`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800140e4`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800140e4`
- `ntdll!RtlReleaseRelativeName` at `0x1800141a3`
- `ntdll!RtlReleaseRelativeName` at `0x1800141a3`
- `ntdll!RtlFreeHeap` at `0x1800141c1`
- `ntdll!RtlFreeHeap` at `0x1800141c1`
- `ntdll!NtCreateFile` at `0x180014191`
- `ntdll!NtCreateFile` at `0x180014191`
- `ntdll!RtlNtStatusToDosError` at `0x1800141e7`
- `ntdll!RtlNtStatusToDosError` at `0x1800141e7`
- `ntdll!NtClose` at `0x1800141d5`
- `ntdll!NtClose` at `0x1800141d5`

## pseudocode

```c
ULONG __fastcall CreateSystemDirectory(const unsigned __int16 *a1)
{
  PWSTR Buffer; // rdi
  HANDLE ContainingDirectory; // rax
  int v4; // ebx
  struct _UNICODE_STRING NtName; // [rsp+60h] [rbp-39h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp-29h] BYREF
  _RTL_RELATIVE_NAME_U RelativeName; // [rsp+80h] [rbp-19h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A0h] [rbp+7h] BYREF
  void *FileHandle; // [rsp+108h] [rbp+6Fh] BYREF

  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  FileHandle = 0;
  NtName = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( !RtlDosPathNameToRelativeNtPathName_U(a1, &NtName, 0, &RelativeName) )
    return 3;
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
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtCreateFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 0, 4u, 3u, 2u, 0x4021u, 0, 0);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v4 < 0 )
    return RtlNtStatusToDosError(v4);
  NtClose(FileHandle);
  return 0;
}

```

## disassembly

```asm
0x1800140a0  push    rbp
0x1800140a2  push    rbx
0x1800140a3  push    rsi
0x1800140a4  push    rdi
0x1800140a5  lea     rbp, [rsp-3Fh]
0x1800140aa  sub     rsp, 0D8h
0x1800140b1  xorps   xmm0, xmm0
0x1800140b4  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800140b8  xorps   xmm1, xmm1
0x1800140bb  lea     rdx, [rbp+57h+NtName]; NtName
0x1800140bf  xor     esi, esi
0x1800140c1  xor     r8d, r8d; PartName
0x1800140c4  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800140c8  mov     [rbp+57h+FileHandle], rsi
0x1800140cc  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800140d0  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800140d4  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800140d8  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800140dc  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800140e0  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800140e4  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800140eb  nop     dword ptr [rax+rax+00h]
0x1800140f0  test    al, al
0x1800140f2  jnz     short loc_1800140FC
0x1800140f4  lea     eax, [rsi+3]
0x1800140f7  jmp     loc_1800141F3
0x1800140fc  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x180014100  mov     rdi, [rbp+57h+NtName.Buffer]
0x180014104  test    ax, ax
0x180014107  jz      short loc_180014129
0x180014109  mov     [rbp+57h+NtName.Length], ax
0x18001410d  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x180014110  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x180014113  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x180014117  mov     word ptr [rbp+57h+NtName+6], ax
0x18001411b  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x18001411f  mov     [rbp+57h+NtName.Buffer], rax
0x180014123  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x180014127  jmp     short loc_180014130
0x180014129  mov     rax, rsi
0x18001412c  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x180014130  mov     [rsp+0F0h+EaLength], esi; EaLength
0x180014134  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180014138  mov     [rsp+0F0h+EaBuffer], rsi; EaBuffer
0x18001413d  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180014141  mov     [rsp+0F0h+CreateOptions], 4021h; CreateOptions
0x180014149  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18001414d  mov     [rsp+0F0h+CreateDisposition], 2; CreateDisposition
0x180014155  xorps   xmm0, xmm0
0x180014158  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x18001415c  mov     edx, 100001h; DesiredAccess
0x180014161  mov     [rsp+0F0h+ShareAccess], 3; ShareAccess
0x180014169  lea     rax, [rbp+57h+NtName]
0x18001416d  mov     [rsp+0F0h+FileAttributes], 4; FileAttributes
0x180014175  mov     [rsp+0F0h+AllocationSize], rsi; AllocationSize
0x18001417a  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180014181  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180014188  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18001418c  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180014191  call    cs:__imp_NtCreateFile
0x180014198  nop     dword ptr [rax+rax+00h]
0x18001419d  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800141a1  mov     ebx, eax
0x1800141a3  call    cs:__imp_RtlReleaseRelativeName
0x1800141aa  nop     dword ptr [rax+rax+00h]
0x1800141af  mov     rcx, gs:60h
0x1800141b8  mov     r8, rdi; P
0x1800141bb  xor     edx, edx; Flags
0x1800141bd  mov     rcx, [rcx+30h]; HeapHandle
0x1800141c1  call    cs:__imp_RtlFreeHeap
0x1800141c8  nop     dword ptr [rax+rax+00h]
0x1800141cd  test    ebx, ebx
0x1800141cf  js      short loc_1800141E5
0x1800141d1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800141d5  call    cs:__imp_NtClose
0x1800141dc  nop     dword ptr [rax+rax+00h]
0x1800141e1  xor     eax, eax
0x1800141e3  jmp     short loc_1800141F3
0x1800141e5  mov     ecx, ebx; Status
0x1800141e7  call    cs:__imp_RtlNtStatusToDosError
0x1800141ee  nop     dword ptr [rax+rax+00h]
0x1800141f3  add     rsp, 0D8h
0x1800141fa  pop     rdi
0x1800141fb  pop     rsi
0x1800141fc  pop     rbx
0x1800141fd  pop     rbp
0x1800141fe  retn
```
