# FindFirstChangeNotificationW

- ea: `0x1800fcc40`
- end: `0x1800fcdf9`
- name: `FindFirstChangeNotificationW`
- size: `441`
- prototype: `HANDLE __stdcall(LPCWSTR lpPathName, BOOL bWatchSubtree, DWORD dwNotifyFilter)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18018d1f0`

## callees

- `0x18004b9d0`
- `0x1800fcc40`

## import_xrefs

- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800fcc91`
- `ntdll!RtlDosPathNameToRelativeNtPathName_U` at `0x1800fcc91`
- `ntdll!RtlReleaseRelativeName` at `0x1800fcd12`
- `ntdll!RtlReleaseRelativeName` at `0x1800fcd12`
- `ntdll!NtOpenFile` at `0x1800fcd00`
- `ntdll!NtOpenFile` at `0x1800fcd00`
- `ntdll!RtlSetLastWin32Error` at `0x1800fcdac`
- `ntdll!RtlSetLastWin32Error` at `0x1800fcdac`
- `ntdll!NtClose` at `0x1800fcde8`
- `ntdll!NtClose` at `0x1800fcde8`
- `ntdll!RtlFreeHeap` at `0x1800fcd30`
- `ntdll!RtlFreeHeap` at `0x1800fcd30`
- `ntdll!NtNotifyChangeDirectoryFile` at `0x1800fcd91`
- `ntdll!NtNotifyChangeDirectoryFile` at `0x1800fcd91`

## pseudocode

```c
HANDLE __stdcall FindFirstChangeNotificationW(LPCWSTR lpPathName, BOOL bWatchSubtree, DWORD dwNotifyFilter)
{
  BOOLEAN WatchTree; // r14
  PWSTR Buffer; // rdi
  HANDLE ContainingDirectory; // rax
  NTSTATUS v7; // ebx
  NTSTATUS v9; // eax
  struct _UNICODE_STRING NtName; // [rsp+50h] [rbp-49h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+60h] [rbp-39h] BYREF
  struct _RTL_RELATIVE_NAME_U RelativeName; // [rsp+70h] [rbp-29h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-9h] BYREF
  HANDLE FileHandle; // [rsp+118h] [rbp+7Fh] BYREF

  WatchTree = bWatchSubtree;
  FileHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  NtName = 0;
  IoStatusBlock = 0;
  memset(&RelativeName, 0, sizeof(RelativeName));
  if ( !RtlDosPathNameToRelativeNtPathName_U(lpPathName, &NtName, 0, &RelativeName) )
  {
    RtlSetLastWin32Error(3u);
    return (HANDLE)-1LL;
  }
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
  v7 = NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x4001u);
  RtlReleaseRelativeName(&RelativeName);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v7 < 0 )
  {
    BaseSetLastNTError((unsigned int)v7);
    return (HANDLE)-1LL;
  }
  v9 = NtNotifyChangeDirectoryFile(
         FileHandle,
         0,
         0,
         0,
         &staticIoStatusBlock,
         staticchangebuff,
         0x20u,
         dwNotifyFilter,
         WatchTree);
  if ( v9 < 0 )
  {
    BaseSetLastNTError((unsigned int)v9);
    NtClose(FileHandle);
    return (HANDLE)-1LL;
  }
  return FileHandle;
}

```

## disassembly

```asm
0x1800fcc40  push    rbp
0x1800fcc42  push    rbx
0x1800fcc43  push    rsi
0x1800fcc44  push    rdi
0x1800fcc45  push    r14
0x1800fcc47  push    r15
0x1800fcc49  lea     rbp, [rsp-2Fh]
0x1800fcc4e  sub     rsp, 0C8h
0x1800fcc55  xorps   xmm0, xmm0
0x1800fcc58  lea     r9, [rbp+57h+RelativeName]; RelativeName
0x1800fcc5c  mov     esi, r8d
0x1800fcc5f  mov     r14d, edx
0x1800fcc62  xorps   xmm1, xmm1
0x1800fcc65  lea     rdx, [rbp+57h+NtName]; NtName
0x1800fcc69  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800fcc6d  xor     r15d, r15d
0x1800fcc70  xor     eax, eax
0x1800fcc72  xor     r8d, r8d; PartName
0x1800fcc75  mov     [rbp+57h+FileHandle], r15
0x1800fcc79  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800fcc7d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800fcc81  movups  xmmword ptr [rbp+57h+NtName.Length], xmm0
0x1800fcc85  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm1
0x1800fcc89  movups  xmmword ptr [rbp+57h+RelativeName.RelativeName.Length], xmm0
0x1800fcc8d  movups  xmmword ptr [rbp+57h+RelativeName.ContainingDirectory], xmm0
0x1800fcc91  call    cs:__imp_RtlDosPathNameToRelativeNtPathName_U
0x1800fcc98  nop     dword ptr [rax+rax+00h]
0x1800fcc9d  test    al, al
0x1800fcc9f  jz      loc_1800FCDA7
0x1800fcca5  movzx   eax, [rbp+57h+RelativeName.RelativeName.Length]
0x1800fcca9  mov     rdi, [rbp+57h+NtName.Buffer]
0x1800fccad  test    ax, ax
0x1800fccb0  jnz     loc_1800FCDBA
0x1800fccb6  mov     eax, r15d
0x1800fccb9  mov     [rbp+57h+RelativeName.ContainingDirectory], rax
0x1800fccbd  mov     [rbp+57h+ObjectAttributes.RootDirectory], rax
0x1800fccc1  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800fccc5  lea     rax, [rbp+57h+NtName]
0x1800fccc9  mov     [rsp+0F0h+OpenOptions], 4001h; OpenOptions
0x1800fccd1  xorps   xmm0, xmm0
0x1800fccd4  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800fccd8  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800fccdc  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800fcce3  mov     edx, 100001h; DesiredAccess
0x1800fcce8  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800fccef  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800fccf3  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x1800fccfb  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800fcd00  call    cs:__imp_NtOpenFile
0x1800fcd07  nop     dword ptr [rax+rax+00h]
0x1800fcd0c  lea     rcx, [rbp+57h+RelativeName]; RelativeName
0x1800fcd10  mov     ebx, eax
0x1800fcd12  call    cs:__imp_RtlReleaseRelativeName
0x1800fcd19  nop     dword ptr [rax+rax+00h]
0x1800fcd1e  mov     rcx, gs:60h
0x1800fcd27  mov     r8, rdi; P
0x1800fcd2a  xor     edx, edx; Flags
0x1800fcd2c  mov     rcx, [rcx+30h]; HeapHandle
0x1800fcd30  call    cs:__imp_RtlFreeHeap
0x1800fcd37  nop     dword ptr [rax+rax+00h]
0x1800fcd3c  test    ebx, ebx
0x1800fcd3e  jns     short loc_1800FCD5C
0x1800fcd40  mov     ecx, ebx
0x1800fcd42  call    BaseSetLastNTError
0x1800fcd47  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800fcd4b  add     rsp, 0C8h
0x1800fcd52  pop     r15
0x1800fcd54  pop     r14
0x1800fcd56  pop     rdi
0x1800fcd57  pop     rsi
0x1800fcd58  pop     rbx
0x1800fcd59  pop     rbp
0x1800fcd5a  retn
0x1800fcd5c  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800fcd60  lea     rax, staticchangebuff
0x1800fcd67  mov     [rsp+0F0h+WatchTree], r14b; WatchTree
0x1800fcd6c  xor     r9d, r9d; ApcContext
0x1800fcd6f  mov     [rsp+0F0h+CompletionFilter], esi; CompletionFilter
0x1800fcd73  xor     r8d, r8d; ApcRoutine
0x1800fcd76  mov     [rsp+0F0h+BufferSize], 20h ; ' '; BufferSize
0x1800fcd7e  xor     edx, edx; Event
0x1800fcd80  mov     qword ptr [rsp+0F0h+OpenOptions], rax; Buffer
0x1800fcd85  lea     rax, staticIoStatusBlock
0x1800fcd8c  mov     qword ptr [rsp+0F0h+ShareAccess], rax; IoStatusBlock
0x1800fcd91  call    cs:__imp_NtNotifyChangeDirectoryFile
0x1800fcd98  nop     dword ptr [rax+rax+00h]
0x1800fcd9d  test    eax, eax
0x1800fcd9f  js      short loc_1800FCDDD
0x1800fcda1  mov     rax, [rbp+57h+FileHandle]
0x1800fcda5  jmp     short loc_1800FCD4B
0x1800fcda7  mov     ecx, 3; LastError
0x1800fcdac  call    cs:__imp_RtlSetLastWin32Error
0x1800fcdb3  nop     dword ptr [rax+rax+00h]
0x1800fcdb8  jmp     short loc_1800FCD47
0x1800fcdba  mov     [rbp+57h+NtName.Length], ax
0x1800fcdbe  mov     eax, dword ptr [rbp+57h+RelativeName.RelativeName.MaximumLength]
0x1800fcdc1  mov     dword ptr [rbp+57h+NtName.MaximumLength], eax
0x1800fcdc4  movzx   eax, word ptr [rbp+57h+RelativeName.RelativeName+6]
0x1800fcdc8  mov     word ptr [rbp+57h+NtName+6], ax
0x1800fcdcc  mov     rax, [rbp+57h+RelativeName.RelativeName.Buffer]
0x1800fcdd0  mov     [rbp+57h+NtName.Buffer], rax
0x1800fcdd4  mov     rax, [rbp+57h+RelativeName.ContainingDirectory]
0x1800fcdd8  jmp     loc_1800FCCBD
0x1800fcddd  mov     ecx, eax
0x1800fcddf  call    BaseSetLastNTError
0x1800fcde4  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800fcde8  call    cs:__imp_NtClose
0x1800fcdef  nop     dword ptr [rax+rax+00h]
0x1800fcdf4  jmp     loc_1800FCD47
```
