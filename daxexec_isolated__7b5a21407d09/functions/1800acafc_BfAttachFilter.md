# BfAttachFilter

- ea: `0x1800acafc`
- end: `0x1800acc37`
- name: `BfAttachFilter`
- size: `315`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002eacc`

## callees

- `0x1800acafc`
- `0x1800ad510`
- `0x1800ae2f8`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800acb2c`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800acb2c`
- `ntdll!NtClose` at `0x1800acbf1`
- `ntdll!NtClose` at `0x1800acbf1`
- `ntdll!RtlFreeHeap` at `0x1800acc17`
- `ntdll!RtlFreeHeap` at `0x1800acc17`
- `ntdll!NtCreateFile` at `0x1800acbb8`
- `ntdll!NtCreateFile` at `0x1800acbb8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall BfAttachFilter(const WCHAR *a1)
{
  unsigned int v1; // ebx
  unsigned int v2; // eax
  unsigned int v3; // eax
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+C8h] [rbp+6Fh] BYREF

  FileHandle = (void *)-1LL;
  NtPathName = 0;
  if ( RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    ObjectAttributes.RootDirectory = 0;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &NtPathName;
    *(_QWORD *)&ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    IoStatusBlock = 0;
    v2 = NtCreateFile(&FileHandle, 0x120089u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 1u, 1u, 0x204000u, 0, 0);
    if ( FileHandle == (void *)-1LL )
      v3 = FilterHResultFromNtStatus(v2);
    else
      v3 = WcpAttachFilterInstance(L"bindflt");
    v1 = v3;
  }
  else
  {
    v1 = -2147024893;
  }
  if ( FileHandle != (void *)-1LL )
    NtClose(FileHandle);
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  return v1;
}

```

## disassembly

```asm
0x1800acafc  mov     [rsp-8+arg_0], rbx
0x1800acb01  mov     [rsp-8+FileHandle], rdx
0x1800acb06  push    rbp
0x1800acb07  lea     rbp, [rsp-57h]
0x1800acb0c  sub     rsp, 0B0h
0x1800acb13  xorps   xmm0, xmm0
0x1800acb16  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800acb1e  xor     r9d, r9d; DirectoryInfo
0x1800acb21  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800acb25  xor     r8d, r8d; NtFileNamePart
0x1800acb28  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x1800acb2c  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800acb33  nop     dword ptr [rax+rax+00h]
0x1800acb38  test    al, al
0x1800acb3a  jnz     short loc_1800ACB46
0x1800acb3c  mov     ebx, 80070003h
0x1800acb41  jmp     loc_1800ACBE7
0x1800acb46  mov     [rsp+0B0h+EaLength], 0; EaLength
0x1800acb4e  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800acb52  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x1800acb5b  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800acb5f  xor     eax, eax
0x1800acb61  mov     [rsp+0B0h+CreateOptions], 204000h; CreateOptions
0x1800acb69  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800acb6d  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800acb71  lea     rax, [rbp+57h+NtPathName]
0x1800acb75  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800acb7d  xorps   xmm0, xmm0
0x1800acb80  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800acb84  mov     eax, 1
0x1800acb89  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800acb91  mov     [rsp+0B0h+CreateDisposition], eax; CreateDisposition
0x1800acb95  mov     edx, 120089h; DesiredAccess
0x1800acb9a  mov     [rsp+0B0h+ShareAccess], eax; ShareAccess
0x1800acb9e  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x1800acba6  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x1800acbaf  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800acbb4  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800acbb8  call    cs:__imp_NtCreateFile
0x1800acbbf  nop     dword ptr [rax+rax+00h]
0x1800acbc4  mov     r8, [rbp+57h+FileHandle]
0x1800acbc8  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800acbcc  jnz     short loc_1800ACBD7
0x1800acbce  mov     ecx, eax
0x1800acbd0  call    FilterHResultFromNtStatus
0x1800acbd5  jmp     short loc_1800ACBE5
0x1800acbd7  xor     edx, edx
0x1800acbd9  lea     rcx, aBindflt; "bindflt"
0x1800acbe0  call    WcpAttachFilterInstance
0x1800acbe5  mov     ebx, eax
0x1800acbe7  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800acbeb  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800acbef  jz      short loc_1800ACBFD
0x1800acbf1  call    cs:__imp_NtClose
0x1800acbf8  nop     dword ptr [rax+rax+00h]
0x1800acbfd  cmp     [rbp+57h+NtPathName.Buffer], 0
0x1800acc02  jz      short loc_1800ACC23
0x1800acc04  mov     rcx, gs:60h
0x1800acc0d  xor     edx, edx; Flags
0x1800acc0f  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x1800acc13  mov     rcx, [rcx+30h]; HeapHandle
0x1800acc17  call    cs:__imp_RtlFreeHeap
0x1800acc1e  nop     dword ptr [rax+rax+00h]
0x1800acc23  mov     eax, ebx
0x1800acc25  mov     rbx, [rsp+0B0h+arg_0]
0x1800acc2d  add     rsp, 0B0h
0x1800acc34  pop     rbp
0x1800acc35  retn
```
