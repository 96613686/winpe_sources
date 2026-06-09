# container::RegistryProvider::OpenRegistryDriver(void)

- ea: `0x18002993c`
- end: `0x180029a13`
- name: `?OpenRegistryDriver@RegistryProvider@container@@YAPEAXXZ`
- size: `215`
- prototype: `void *__fastcall(container::RegistryProvider *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, reparse_path, registry_config, loader_planting`

## callers

- `0x180028eb4`
- `0x180028f54`
- `0x1800296a8`
- `0x1800297b4`
- `0x180029a1c`

## callees

- `0x18000b4bc`
- `0x18002993c`

## import_xrefs

- `ntdll!NtCreateFile` at `0x1800299dc`
- `ntdll!NtCreateFile` at `0x1800299dc`

## string_xrefs

- `0x1800299fe`: `onecore\base\gendrv\silos\container\registry_provider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void *__fastcall container::RegistryProvider::OpenRegistryDriver(container::RegistryProvider *this)
{
  NTSTATUS v1; // eax
  int AllocationSize; // [rsp+20h] [rbp-39h]
  _QWORD v4[2]; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]
  void *FileHandle; // [rsp+C0h] [rbp+67h] BYREF

  v4[1] = L"\\Device\\VRegDriver";
  FileHandle = 0;
  IoStatusBlock = 0;
  v4[0] = 2490404;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)v4;
  memset(&ObjectAttributes.Attributes, 0, 24);
  v1 = NtCreateFile(&FileHandle, 0x100003u, &ObjectAttributes, &IoStatusBlock, 0, 0, 0, 3u, 0x10u, 0, 0);
  if ( v1 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x18A,
      (unsigned int)"onecore\\base\\gendrv\\silos\\container\\registry_provider.cpp",
      (const char *)(unsigned int)v1,
      AllocationSize);
  return FileHandle;
}

```

## disassembly

```asm
0x18002993c  push    rbp
0x18002993e  lea     rbp, [rsp-57h]
0x180029943  sub     rsp, 0B0h
0x18002994a  mov     [rsp+0B0h+EaLength], 0; EaLength
0x180029952  lea     rax, aDeviceVregdriv; "\\Device\\VRegDriver"
0x180029959  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x180029962  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180029966  mov     [rsp+0B0h+CreateOptions], 10h; CreateOptions
0x18002996e  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180029972  mov     [rsp+0B0h+CreateDisposition], 3; CreateDisposition
0x18002997a  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x18002997e  xorps   xmm0, xmm0
0x180029981  mov     [rbp+57h+var_48], rax
0x180029985  mov     [rsp+0B0h+ShareAccess], 0; ShareAccess
0x18002998d  lea     rax, [rbp+57h+var_50]
0x180029991  mov     [rsp+0B0h+FileAttributes], 0; FileAttributes
0x180029999  mov     edx, 100003h; DesiredAccess
0x18002999e  mov     [rsp+0B0h+AllocationSize], 0; int
0x1800299a7  mov     [rbp+57h+FileHandle], 0
0x1800299af  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800299b3  mov     [rbp+57h+var_50], 260024h
0x1800299bb  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800299c3  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x1800299cb  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800299cf  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 0
0x1800299d7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800299dc  call    cs:__imp_NtCreateFile
0x1800299e3  nop     dword ptr [rax+rax+00h]
0x1800299e8  test    eax, eax
0x1800299ea  js      short loc_1800299FA
0x1800299ec  mov     rax, [rbp+57h+FileHandle]
0x1800299f0  add     rsp, 0B0h
0x1800299f7  pop     rbp
0x1800299f8  retn
0x1800299fa  mov     rcx, [rbp+5Fh]; this
0x1800299fe  lea     r8, aOnecoreBaseGen_4; "onecore\\base\\gendrv\\silos\\container"...
0x180029a05  mov     r9d, eax; char *
0x180029a08  mov     edx, 18Ah; void *
0x180029a0d  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
```
