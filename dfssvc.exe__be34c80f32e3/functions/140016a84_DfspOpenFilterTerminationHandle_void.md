# DfspOpenFilterTerminationHandle(void * *)

- ea: `0x140016a84`
- end: `0x140016b9d`
- name: `?DfspOpenFilterTerminationHandle@@YAKPEAPEAX@Z`
- size: `281`
- prototype: `unsigned int __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140016204`

## callees

- `0x140016a84`
- `0x14005ce70`

## import_xrefs

- `ntdll!NtOpenFile` at `0x140016b56`
- `ntdll!NtOpenFile` at `0x140016b56`
- `ntdll!RtlAppendUnicodeToString` at `0x140016ae5`
- `ntdll!RtlAppendUnicodeToString` at `0x140016afd`
- `ntdll!RtlAppendUnicodeToString` at `0x140016ae5`
- `ntdll!RtlAppendUnicodeToString` at `0x140016afd`
- `ntdll!RtlNtStatusToDosError` at `0x140016b68`
- `ntdll!RtlNtStatusToDosError` at `0x140016b68`

## string_xrefs

- `0x140016af1`: `\ProcessTermination\FilePath`

## pseudocode

```c
__int64 __fastcall DfspOpenFilterTerminationHandle(void **a1)
{
  unsigned int v1; // ecx
  void *FileHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-C8h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+78h] [rbp-88h] BYREF
  char v7; // [rsp+90h] [rbp-70h] BYREF

  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  FileHandle = 0;
  *(_QWORD *)&Destination.Length = 78643200;
  Destination.Buffer = (PWSTR)&v7;
  IoStatusBlock = 0;
  RtlAppendUnicodeToString(&Destination, L"\\DfsServer");
  RtlAppendUnicodeToString(&Destination, L"\\ProcessTermination\\FilePath");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = &Destination;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v1 = NtOpenFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 7u, 0x20u);
  if ( v1 )
    v1 = RtlNtStatusToDosError(v1);
  g_DfspTerminationHandle = FileHandle;
  return v1;
}

```

## disassembly

```asm
0x140016a84  push    rbp
0x140016a86  lea     rbp, [rsp-450h]
0x140016a8e  sub     rsp, 550h
0x140016a95  mov     rax, cs:__security_cookie
0x140016a9c  xor     rax, rsp
0x140016a9f  mov     [rbp+450h+var_10], rax
0x140016aa6  and     dword ptr [rsp+550h+ObjectAttributes+4], 0
0x140016aab  lea     rdx, Source; "\\DfsServer"
0x140016ab2  and     dword ptr [rsp+550h+ObjectAttributes+1Ch], 0
0x140016ab7  lea     rcx, [rsp+550h+Destination]; Destination
0x140016abc  and     [rsp+550h+FileHandle], 0
0x140016ac2  xorps   xmm1, xmm1
0x140016ac5  movups  xmmword ptr [rsp+550h+Destination.Length], xmm1
0x140016aca  mov     eax, 4B0h
0x140016acf  mov     [rsp+550h+Destination.MaximumLength], ax
0x140016ad4  xorps   xmm0, xmm0
0x140016ad7  lea     rax, [rbp+450h+var_4C0]
0x140016adb  mov     [rsp+550h+Destination.Buffer], rax
0x140016ae0  movups  xmmword ptr [rsp+550h+IoStatusBlock], xmm0
0x140016ae5  call    cs:__imp_RtlAppendUnicodeToString
0x140016aec  nop     dword ptr [rax+rax+00h]
0x140016af1  lea     rdx, aProcesstermina; "\\ProcessTermination\\FilePath"
0x140016af8  lea     rcx, [rsp+550h+Destination]; Destination
0x140016afd  call    cs:__imp_RtlAppendUnicodeToString
0x140016b04  nop     dword ptr [rax+rax+00h]
0x140016b09  and     [rsp+550h+ObjectAttributes.RootDirectory], 0
0x140016b0f  lea     rax, [rsp+550h+Destination]
0x140016b14  xorps   xmm0, xmm0
0x140016b17  mov     [rsp+550h+OpenOptions], 20h ; ' '; OpenOptions
0x140016b1f  lea     r9, [rsp+550h+IoStatusBlock]; IoStatusBlock
0x140016b24  mov     [rsp+550h+ObjectAttributes.ObjectName], rax
0x140016b29  lea     r8, [rsp+550h+ObjectAttributes]; ObjectAttributes
0x140016b2e  mov     [rsp+550h+ObjectAttributes.Length], 30h ; '0'
0x140016b36  mov     edx, 100002h; DesiredAccess
0x140016b3b  mov     [rsp+550h+ObjectAttributes.Attributes], 40h ; '@'
0x140016b43  lea     rcx, [rsp+550h+FileHandle]; FileHandle
0x140016b48  mov     [rsp+550h+ShareAccess], 7; ShareAccess
0x140016b50  movdqu  xmmword ptr [rsp+550h+ObjectAttributes.SecurityDescriptor], xmm0
0x140016b56  call    cs:__imp_NtOpenFile
0x140016b5d  nop     dword ptr [rax+rax+00h]
0x140016b62  mov     ecx, eax; Status
0x140016b64  test    eax, eax
0x140016b66  jz      short loc_140016B76
0x140016b68  call    cs:__imp_RtlNtStatusToDosError
0x140016b6f  nop     dword ptr [rax+rax+00h]
0x140016b74  mov     ecx, eax
0x140016b76  mov     rax, [rsp+550h+FileHandle]
0x140016b7b  mov     cs:?g_DfspTerminationHandle@@3PEAXEA, rax; void * g_DfspTerminationHandle
0x140016b82  mov     eax, ecx
0x140016b84  mov     rcx, [rbp+450h+var_10]
0x140016b8b  xor     rcx, rsp; StackCookie
0x140016b8e  call    __security_check_cookie
0x140016b93  add     rsp, 550h
0x140016b9a  pop     rbp
0x140016b9b  retn
```
