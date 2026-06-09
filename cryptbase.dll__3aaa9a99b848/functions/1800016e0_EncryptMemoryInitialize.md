# EncryptMemoryInitialize

- ea: `0x1800016e0`
- end: `0x1800017c7`
- name: `EncryptMemoryInitialize`
- size: `231`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001040`
- `0x180001110`
- `0x180001220`

## callees

- `0x1800016e0`

## import_xrefs

- `ntdll!NtClose` at `0x1800017b9`
- `ntdll!NtClose` at `0x1800017b9`
- `ntdll!NtOpenFile` at `0x180001774`
- `ntdll!NtOpenFile` at `0x180001774`
- `ntdll!RtlInitUnicodeString` at `0x18000171d`
- `ntdll!RtlInitUnicodeString` at `0x18000171d`

## pseudocode

```c
char EncryptMemoryInitialize()
{
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-58h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-48h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-38h] BYREF
  void *FileHandle; // [rsp+90h] [rbp+8h] BYREF

  FileHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\KsecDD");
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenFile(&FileHandle, 0x100001u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u) < 0 )
    return 0;
  if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hKsecDD, (signed __int64)FileHandle, 0) )
    NtClose(FileHandle);
  return 1;
}

```

## disassembly

```asm
0x1800016e0  push    rbx
0x1800016e2  sub     rsp, 80h
0x1800016e9  xorps   xmm0, xmm0
0x1800016ec  lea     rdx, SourceString; "\\Device\\KsecDD"
0x1800016f3  movups  xmmword ptr [rsp+88h+ObjectAttributes.ObjectName], xmm0
0x1800016f8  xor     ebx, ebx
0x1800016fa  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x1800016ff  xor     eax, eax
0x180001701  mov     [rsp+88h+FileHandle], rbx
0x180001709  movups  xmmword ptr [rsp+88h+ObjectAttributes+1Ch], xmm0
0x18000170e  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x180001713  movups  xmmword ptr [rsp+88h+ObjectAttributes.Length], xmm0
0x180001718  movups  xmmword ptr [rsp+88h+IoStatusBlock], xmm0
0x18000171d  call    cs:__imp_RtlInitUnicodeString
0x180001724  nop     dword ptr [rax+rax+00h]
0x180001729  lea     rax, [rsp+88h+DestinationString]
0x18000172e  mov     [rsp+88h+OpenOptions], 20h ; ' '; OpenOptions
0x180001736  xorps   xmm0, xmm0
0x180001739  mov     [rsp+88h+ObjectAttributes.ObjectName], rax
0x18000173e  lea     r9, [rsp+88h+IoStatusBlock]; IoStatusBlock
0x180001743  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x18000174b  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x180001750  mov     [rsp+88h+ObjectAttributes.RootDirectory], rbx
0x180001755  mov     edx, 100001h; DesiredAccess
0x18000175a  mov     [rsp+88h+ObjectAttributes.Attributes], ebx
0x18000175e  lea     rcx, [rsp+88h+FileHandle]; FileHandle
0x180001766  mov     [rsp+88h+ShareAccess], 7; ShareAccess
0x18000176e  movdqu  xmmword ptr [rsp+88h+ObjectAttributes.SecurityDescriptor], xmm0
0x180001774  call    cs:__imp_NtOpenFile
0x18000177b  nop     dword ptr [rax+rax+00h]
0x180001780  test    eax, eax
0x180001782  js      short loc_1800017A5
0x180001784  mov     rcx, [rsp+88h+FileHandle]
0x18000178c  xor     eax, eax
0x18000178e  lock cmpxchg cs:g_hKsecDD, rcx
0x180001797  jnz     short loc_1800017B1
0x180001799  mov     al, 1
0x18000179b  add     rsp, 80h
0x1800017a2  pop     rbx
0x1800017a3  retn
0x1800017a5  xor     al, al
0x1800017a7  add     rsp, 80h
0x1800017ae  pop     rbx
0x1800017af  retn
0x1800017b1  mov     rcx, [rsp+88h+FileHandle]; Handle
0x1800017b9  call    cs:__imp_NtClose
0x1800017c0  nop     dword ptr [rax+rax+00h]
0x1800017c5  jmp     short loc_180001799
```
