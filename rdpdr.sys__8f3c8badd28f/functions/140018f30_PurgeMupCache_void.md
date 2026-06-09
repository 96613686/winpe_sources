# PurgeMupCache(void)

- ea: `0x140018f30`
- end: `0x1400190e0`
- name: `?PurgeMupCache@@YAJXZ`
- size: `432`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14001a950`

## callees

- `0x14000327c`
- `0x140018f30`

## import_xrefs

- `ntoskrnl!RtlInitUnicodeString` at `0x140018f6f`
- `ntoskrnl!RtlInitUnicodeString` at `0x140018f6f`
- `ntoskrnl!ZwClose` at `0x14001908b`
- `ntoskrnl!ZwClose` at `0x14001908b`
- `ntoskrnl!ZwCreateFile` at `0x140018fec`
- `ntoskrnl!ZwCreateFile` at `0x140018fec`
- `ntoskrnl!ZwFsControlFile` at `0x140019079`
- `ntoskrnl!ZwFsControlFile` at `0x140019079`

## pseudocode

```c
__int64 PurgeMupCache(void)
{
  NTSTATUS v0; // ebx
  PDEVICE_OBJECT v1; // rcx
  __int64 v2; // rdx
  struct _UNICODE_STRING DestinationString; // [rsp+60h] [rbp+7h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+70h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+80h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp+67h] BYREF

  FileHandle = 0;
  IoStatusBlock = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\Device\\Mup");
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = ZwCreateFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 3u, 0xA0u, 0, 0);
  if ( v0 == -1073741772 )
    return 0;
  if ( v0 >= 0 )
  {
    v0 = ZwFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x108028u, L"*", 2u, 0, 0);
    ZwClose(FileHandle);
    if ( v0 < 0 )
    {
      v1 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v2 = 11;
        goto LABEL_11;
      }
    }
  }
  else
  {
    v1 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v2 = 10;
LABEL_11:
      WPP_SF_d(v1->AttachedDevice, v2, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids, (unsigned int)v0);
    }
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140018f30  mov     [rsp-8+arg_8], rbx
0x140018f35  push    rbp
0x140018f36  lea     rbp, [rsp-57h]
0x140018f3b  sub     rsp, 0B0h
0x140018f42  xorps   xmm1, xmm1
0x140018f45  mov     [rbp+57h+FileHandle], 0
0x140018f4d  xorps   xmm0, xmm0
0x140018f50  lea     rdx, aDeviceMup; "\\Device\\Mup"
0x140018f57  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140018f5b  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x140018f5f  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm1
0x140018f63  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm1
0x140018f67  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm1
0x140018f6b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140018f6f  call    cs:__imp_RtlInitUnicodeString
0x140018f76  nop     dword ptr [rax+rax+00h]
0x140018f7b  mov     [rsp+0B0h+EaLength], 0; EaLength
0x140018f83  lea     rax, [rbp+57h+DestinationString]
0x140018f87  mov     [rsp+0B0h+EaBuffer], 0; EaBuffer
0x140018f90  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x140018f94  mov     [rsp+0B0h+CreateOptions], 0A0h; CreateOptions
0x140018f9c  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140018fa0  mov     [rsp+0B0h+CreateDisposition], 3; CreateDisposition
0x140018fa8  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x140018fac  mov     [rsp+0B0h+ShareAccess], 7; ShareAccess
0x140018fb4  xorps   xmm0, xmm0
0x140018fb7  mov     [rsp+0B0h+FileAttributes], 80h; FileAttributes
0x140018fbf  mov     edx, 100002h; DesiredAccess
0x140018fc4  mov     [rsp+0B0h+AllocationSize], 0; AllocationSize
0x140018fcd  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140018fd4  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140018fdc  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x140018fe3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140018fe7  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140018fec  call    cs:__imp_ZwCreateFile
0x140018ff3  nop     dword ptr [rax+rax+00h]
0x140018ff8  mov     ebx, eax
0x140018ffa  cmp     eax, 0C0000034h
0x140018fff  jnz     short loc_140019008
0x140019001  xor     ebx, ebx
0x140019003  jmp     loc_1400190CC
0x140019008  test    ebx, ebx
0x14001900a  jns     short loc_140019037
0x14001900c  mov     rcx, cs:WPP_GLOBAL_Control
0x140019013  lea     rax, WPP_GLOBAL_Control
0x14001901a  cmp     rcx, rax
0x14001901d  jz      loc_1400190CC
0x140019023  cmp     byte ptr [rcx+29h], 2
0x140019027  jb      loc_1400190CC
0x14001902d  mov     edx, 0Ah
0x140019032  jmp     loc_1400190B9
0x140019037  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x14001903b  lea     rax, asc_1400090B8; "*"
0x140019042  mov     dword ptr [rsp+0B0h+EaBuffer], 0; OutputBufferLength
0x14001904a  xor     r9d, r9d; ApcContext
0x14001904d  mov     qword ptr [rsp+0B0h+CreateOptions], 0; OutputBuffer
0x140019056  xor     r8d, r8d; ApcRoutine
0x140019059  mov     [rsp+0B0h+CreateDisposition], 2; InputBufferLength
0x140019061  xor     edx, edx; Event
0x140019063  mov     qword ptr [rsp+0B0h+ShareAccess], rax; InputBuffer
0x140019068  lea     rax, [rbp+57h+IoStatusBlock]
0x14001906c  mov     [rsp+0B0h+FileAttributes], 108028h; FsControlCode
0x140019074  mov     [rsp+0B0h+AllocationSize], rax; IoStatusBlock
0x140019079  call    cs:__imp_ZwFsControlFile
0x140019080  nop     dword ptr [rax+rax+00h]
0x140019085  mov     rcx, [rbp+57h+FileHandle]; Handle
0x140019089  mov     ebx, eax
0x14001908b  call    cs:__imp_ZwClose
0x140019092  nop     dword ptr [rax+rax+00h]
0x140019097  test    ebx, ebx
0x140019099  jns     short loc_1400190CC
0x14001909b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400190a2  lea     rax, WPP_GLOBAL_Control
0x1400190a9  cmp     rcx, rax
0x1400190ac  jz      short loc_1400190CC
0x1400190ae  cmp     byte ptr [rcx+29h], 2
0x1400190b2  jb      short loc_1400190CC
0x1400190b4  mov     edx, 0Bh
0x1400190b9  mov     rcx, [rcx+18h]
0x1400190bd  lea     r8, WPP_458e6ddd1c6a36f0c9ab48076d5b03cb_Traceguids
0x1400190c4  mov     r9d, ebx
0x1400190c7  call    WPP_SF_d
0x1400190cc  mov     eax, ebx
0x1400190ce  mov     rbx, [rsp+0B0h+arg_8]
0x1400190d6  add     rsp, 0B0h
0x1400190dd  pop     rbp
0x1400190de  retn
```
