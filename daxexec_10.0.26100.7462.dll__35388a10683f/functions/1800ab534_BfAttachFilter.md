# BfAttachFilter

- ea: `0x1800ab534`
- end: `0x1800ab669`
- name: `BfAttachFilter`
- size: `309`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18002df0c`

## callees

- `0x1800ab534`
- `0x1800abf80`
- `0x1800acdc0`

## import_xrefs

- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ab561`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ab561`
- `ntdll!NtClose` at `0x1800ab623`
- `ntdll!NtClose` at `0x1800ab623`
- `ntdll!RtlFreeHeap` at `0x1800ab649`
- `ntdll!RtlFreeHeap` at `0x1800ab649`
- `ntdll!NtCreateFile` at `0x1800ab5ea`
- `ntdll!NtCreateFile` at `0x1800ab5ea`

## pseudocode

```c
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
    memset(&ObjectAttributes.Attributes + 1, 0, 20);
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.ObjectName = &NtPathName;
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.Attributes = 64;
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
0x1800ab534  mov     [rsp-8+arg_0], rbx
0x1800ab539  mov     [rsp-8+FileHandle], rdx
0x1800ab53e  push    rbp
0x1800ab53f  lea     rbp, [rsp-57h]
0x1800ab544  sub     rsp, 0B0h
0x1800ab54b  or      [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800ab550  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800ab554  xorps   xmm0, xmm0
0x1800ab557  xor     r9d, r9d; DirectoryInfo
0x1800ab55a  xor     r8d, r8d; NtFileNamePart
0x1800ab55d  movups  xmmword ptr [rbp+57h+NtPathName.Length], xmm0
0x1800ab561  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ab568  nop     dword ptr [rax+rax+00h]
0x1800ab56d  test    al, al
0x1800ab56f  jnz     short loc_1800AB57B
0x1800ab571  mov     ebx, 80070003h
0x1800ab576  jmp     loc_1800AB619
0x1800ab57b  and     [rsp+0B0h+var_60], 0
0x1800ab580  lea     rax, [rbp+57h+NtPathName]
0x1800ab584  and     [rsp+0B0h+var_68], 0
0x1800ab58a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800ab58e  and     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x1800ab592  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800ab596  and     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800ab59b  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800ab59f  mov     [rsp+0B0h+CreateOptions], 204000h; CreateOptions
0x1800ab5a7  xorps   xmm0, xmm0
0x1800ab5aa  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800ab5ae  mov     edx, 120089h; DesiredAccess
0x1800ab5b3  mov     eax, 1
0x1800ab5b8  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800ab5c0  and     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x1800ab5c4  mov     [rsp+0B0h+CreateDisposition], eax; CreateDisposition
0x1800ab5c8  mov     [rsp+0B0h+ShareAccess], eax; ShareAccess
0x1800ab5cc  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x1800ab5d4  and     [rsp+0B0h+var_90], 0
0x1800ab5da  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800ab5e1  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ab5e6  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800ab5ea  call    cs:__imp_NtCreateFile
0x1800ab5f1  nop     dword ptr [rax+rax+00h]
0x1800ab5f6  mov     r8, [rbp+57h+FileHandle]
0x1800ab5fa  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1800ab5fe  jnz     short loc_1800AB609
0x1800ab600  mov     ecx, eax
0x1800ab602  call    FilterHResultFromNtStatus
0x1800ab607  jmp     short loc_1800AB617
0x1800ab609  xor     edx, edx
0x1800ab60b  lea     rcx, aBindflt; "bindflt"
0x1800ab612  call    WcpAttachFilterInstance
0x1800ab617  mov     ebx, eax
0x1800ab619  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800ab61d  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800ab621  jz      short loc_1800AB62F
0x1800ab623  call    cs:__imp_NtClose
0x1800ab62a  nop     dword ptr [rax+rax+00h]
0x1800ab62f  cmp     [rbp+57h+NtPathName.Buffer], 0
0x1800ab634  jz      short loc_1800AB655
0x1800ab636  mov     rcx, gs:60h
0x1800ab63f  xor     edx, edx; Flags
0x1800ab641  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x1800ab645  mov     rcx, [rcx+30h]; HeapHandle
0x1800ab649  call    cs:__imp_RtlFreeHeap
0x1800ab650  nop     dword ptr [rax+rax+00h]
0x1800ab655  mov     eax, ebx
0x1800ab657  mov     rbx, [rsp+0B0h+arg_0]
0x1800ab65f  add     rsp, 0B0h
0x1800ab666  pop     rbp
0x1800ab667  retn
```
