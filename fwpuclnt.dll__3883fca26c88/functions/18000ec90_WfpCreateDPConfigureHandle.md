# WfpCreateDPConfigureHandle

- ea: `0x18000ec90`
- end: `0x18000ed8a`
- name: `WfpCreateDPConfigureHandle`
- size: `250`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, reparse_path, registry_config, loader_planting`

## callees

- `0x180012bd0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x18000ecdd`
- `ntdll!RtlInitUnicodeString` at `0x18000ecdd`
- `ntdll!NtCreateFile` at `0x18000ed5a`
- `ntdll!NtCreateFile` at `0x18000ed5a`

## string_xrefs

- `0x18000ecb3`: `\Device\WfpL2DPConfig`

## pseudocode

```c
void *__fastcall WfpCreateDPConfigureHandle(NTSTATUS *a1)
{
  void *FileHandle; // [rsp+60h] [rbp-9h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-1h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+98h] [rbp+2Fh] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp+3Fh] BYREF

  *a1 = 0;
  FileHandle = 0;
  DestinationString = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  memset(&ObjectAttributes.Attributes + 1, 0, 20);
  IoStatusBlock = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\WfpL2DPConfig");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  *a1 = NtCreateFile(&FileHandle, 0xC0000000, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 3u, 0, 0, 0);
  return FileHandle;
}

```

## disassembly

```asm
0x18000ec90  mov     [rsp-8+arg_8], rbx
0x18000ec95  push    rbp
0x18000ec96  lea     rbp, [rsp-57h]
0x18000ec9b  sub     rsp, 0C0h
0x18000eca2  mov     rax, cs:__security_cookie
0x18000eca9  xor     rax, rsp
0x18000ecac  mov     [rbp+57h+var_8], rax
0x18000ecb0  xorps   xmm0, xmm0
0x18000ecb3  lea     rdx, SourceString; "\\Device\\WfpL2DPConfig"
0x18000ecba  xor     eax, eax
0x18000ecbc  mov     rbx, rcx
0x18000ecbf  mov     [rcx], eax
0x18000ecc1  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000ecc5  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000ecc9  mov     [rbp+57h+FileHandle], rax
0x18000eccd  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000ecd1  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x18000ecd5  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x18000ecd9  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x18000ecdd  call    cs:__imp_RtlInitUnicodeString
0x18000ece4  nop     dword ptr [rax+rax+00h]
0x18000ece9  mov     [rsp+0C0h+EaLength], 0; EaLength
0x18000ecf1  lea     rax, [rbp+57h+DestinationString]
0x18000ecf5  mov     [rsp+0C0h+EaBuffer], 0; EaBuffer
0x18000ecfe  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18000ed02  mov     [rsp+0C0h+CreateOptions], 0; CreateOptions
0x18000ed0a  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18000ed0e  mov     [rsp+0C0h+CreateDisposition], 3; CreateDisposition
0x18000ed16  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18000ed1a  mov     [rsp+0C0h+ShareAccess], 0; ShareAccess
0x18000ed22  xorps   xmm0, xmm0
0x18000ed25  mov     [rsp+0C0h+FileAttributes], 0; FileAttributes
0x18000ed2d  mov     edx, 0C0000000h; DesiredAccess
0x18000ed32  mov     [rsp+0C0h+AllocationSize], 0; AllocationSize
0x18000ed3b  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18000ed42  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x18000ed4a  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x18000ed51  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x18000ed55  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000ed5a  call    cs:__imp_NtCreateFile
0x18000ed61  nop     dword ptr [rax+rax+00h]
0x18000ed66  mov     [rbx], eax
0x18000ed68  mov     rax, [rbp+57h+FileHandle]
0x18000ed6c  mov     rcx, [rbp+57h+var_8]
0x18000ed70  xor     rcx, rsp; StackCookie
0x18000ed73  call    __security_check_cookie
0x18000ed78  mov     rbx, [rsp+0C0h+arg_8]
0x18000ed80  add     rsp, 0C0h
0x18000ed87  pop     rbp
0x18000ed88  retn
```
