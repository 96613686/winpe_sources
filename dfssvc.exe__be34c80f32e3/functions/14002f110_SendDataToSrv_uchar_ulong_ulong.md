# SendDataToSrv(uchar *,ulong,ulong)

- ea: `0x14002f110`
- end: `0x14002f213`
- name: `?SendDataToSrv@@YAJPEAEKK@Z`
- size: `259`
- prototype: `__int64 __fastcall(PVOID InputBuffer, ULONG InputBufferLength, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14002f21c`

## callees

- `0x14002f110`
- `0x1400586a8`

## import_xrefs

- `ntdll!NtClose` at `0x14002f1eb`
- `ntdll!NtClose` at `0x14002f1eb`
- `ntdll!NtOpenFile` at `0x14002f196`
- `ntdll!NtOpenFile` at `0x14002f196`
- `ntdll!NtFsControlFile` at `0x14002f1d9`
- `ntdll!NtFsControlFile` at `0x14002f1d9`

## pseudocode

```c
__int64 __fastcall SendDataToSrv(PVOID InputBuffer, ULONG InputBufferLength)
{
  NTSTATUS v4; // ebx
  __int128 v6; // [rsp+58h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp+7Fh] BYREF

  FileHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  v6 = 0;
  IoStatusBlock = 0;
  DfsRtlInitUnicodeStringEx(&v6, L"\\Device\\SrvAdmin");
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v6;
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v4 = NtOpenFile(&FileHandle, 3u, &ObjectAttributes, &IoStatusBlock, 0, 0);
  if ( v4 >= 0 )
  {
    v4 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x148088u, InputBuffer, InputBufferLength, 0, 0);
    NtClose(FileHandle);
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14002f110  mov     rax, rsp
0x14002f113  mov     [rax+8], rbx
0x14002f117  mov     [rax+10h], rsi
0x14002f11b  mov     [rax+18h], rdi
0x14002f11f  push    rbp
0x14002f120  lea     rbp, [rax-5Fh]
0x14002f124  sub     rsp, 0A0h
0x14002f12b  and     [rbp+57h+FileHandle], 0
0x14002f130  xorps   xmm0, xmm0
0x14002f133  and     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x14002f137  mov     edi, edx
0x14002f139  and     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x14002f13d  lea     rdx, aDeviceSrvadmin; "\\Device\\SrvAdmin"
0x14002f144  mov     rsi, rcx
0x14002f147  lea     rcx, [rbp+57h+var_50]
0x14002f14b  movups  [rbp+57h+var_50], xmm0
0x14002f14f  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x14002f153  call    DfsRtlInitUnicodeStringEx
0x14002f158  and     [rsp+0A0h+FsControlCode], 0
0x14002f15d  lea     rax, [rbp+57h+var_50]
0x14002f161  and     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x14002f166  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x14002f16a  and     dword ptr [rsp+0A0h+var_80], 0
0x14002f16f  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x14002f173  xorps   xmm0, xmm0
0x14002f176  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x14002f17a  mov     edx, 3; DesiredAccess
0x14002f17f  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x14002f186  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002f18a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x14002f191  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x14002f196  call    cs:__imp_NtOpenFile
0x14002f19d  nop     dword ptr [rax+rax+00h]
0x14002f1a2  mov     ebx, eax
0x14002f1a4  test    eax, eax
0x14002f1a6  js      short loc_14002F1F7
0x14002f1a8  and     [rsp+0A0h+var_58], 0
0x14002f1ad  lea     rax, [rbp+57h+IoStatusBlock]
0x14002f1b1  and     qword ptr [rsp+0A0h+var_60], 0
0x14002f1b7  xor     r9d, r9d; ApcContext
0x14002f1ba  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14002f1be  xor     r8d, r8d; ApcRoutine
0x14002f1c1  mov     [rsp+0A0h+InputBufferLength], edi; InputBufferLength
0x14002f1c5  xor     edx, edx; Event
0x14002f1c7  mov     [rsp+0A0h+InputBuffer], rsi; InputBuffer
0x14002f1cc  mov     [rsp+0A0h+FsControlCode], 148088h; FsControlCode
0x14002f1d4  mov     [rsp+0A0h+var_80], rax; IoStatusBlock
0x14002f1d9  call    cs:__imp_NtFsControlFile
0x14002f1e0  nop     dword ptr [rax+rax+00h]
0x14002f1e5  mov     rcx, [rbp+57h+FileHandle]; Handle
0x14002f1e9  mov     ebx, eax
0x14002f1eb  call    cs:__imp_NtClose
0x14002f1f2  nop     dword ptr [rax+rax+00h]
0x14002f1f7  lea     r11, [rsp+0A0h+var_s0]
0x14002f1ff  mov     eax, ebx
0x14002f201  mov     rbx, [r11+10h]
0x14002f205  mov     rsi, [r11+18h]
0x14002f209  mov     rdi, [r11+20h]
0x14002f20d  mov     rsp, r11
0x14002f210  pop     rbp
0x14002f211  retn
```
