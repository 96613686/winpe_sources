# RtlFileMapInitializeByNtPath

- ea: `0x18006340c`
- end: `0x1800634e2`
- name: `RtlFileMapInitializeByNtPath`
- size: `214`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800614b8`

## callees

- `0x18006340c`

## import_xrefs

- `ntdll!ZwCreateFile` at `0x18006349b`
- `ntdll!ZwCreateFile` at `0x18006349b`
- `ntdll!ZwClose` at `0x1800634c5`
- `ntdll!ZwClose` at `0x1800634c5`

## pseudocode

```c
__int64 __fastcall RtlFileMapInitializeByNtPath(__int64 a1, struct _UNICODE_STRING *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rcx
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+68h] [rbp+17h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp+27h] BYREF
  void *FileHandle; // [rsp+C0h] [rbp+6Fh] BYREF

  ObjectAttributes.ObjectName = a2;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  IoStatusBlock = 0;
  FileHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = ZwCreateFile(&FileHandle, 0x80100080, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 5u, 1u, 0x60u, 0, 0);
  if ( v3 < 0 )
  {
    v4 = FileHandle;
  }
  else
  {
    v4 = 0;
    *(_QWORD *)a1 = FileHandle;
    v3 = 0;
    FileHandle = 0;
    *(_BYTE *)(a1 + 40) = 1;
  }
  if ( v4 )
    ZwClose(v4);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18006340c  mov     rax, rsp
0x18006340f  mov     [rax+8], rbx
0x180063413  mov     [rax+18h], rdi
0x180063417  push    rbp
0x180063418  lea     rbp, [rax-5Fh]
0x18006341c  sub     rsp, 0A0h
0x180063423  mov     dword ptr [rax-58h], 0
0x18006342a  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x18006342e  mov     qword ptr [rax-60h], 0
0x180063436  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x18006343a  mov     dword ptr [rax-68h], 60h ; '`'
0x180063441  xorps   xmm0, xmm0
0x180063444  mov     dword ptr [rax-70h], 1
0x18006344b  mov     rdi, rcx
0x18006344e  mov     dword ptr [rax-78h], 5
0x180063455  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180063459  mov     [rbp+57h+ObjectAttributes.ObjectName], rdx
0x18006345d  mov     edx, 80100080h; DesiredAccess
0x180063462  mov     dword ptr [rax-80h], 80h
0x180063469  mov     [rsp+0A0h+AllocationSize], 0; AllocationSize
0x180063472  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x18006347a  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180063482  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x180063486  mov     [rbp+57h+FileHandle], 0
0x18006348e  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x180063496  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x18006349b  call    cs:__imp_ZwCreateFile
0x1800634a1  mov     ebx, eax
0x1800634a3  test    eax, eax
0x1800634a5  js      short loc_1800634BC
0x1800634a7  mov     rax, [rbp+57h+FileHandle]
0x1800634ab  xor     ecx, ecx
0x1800634ad  mov     [rdi], rax
0x1800634b0  xor     ebx, ebx
0x1800634b2  mov     [rbp+57h+FileHandle], rcx
0x1800634b6  mov     byte ptr [rdi+28h], 1
0x1800634ba  jmp     short loc_1800634C0
0x1800634bc  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800634c0  test    rcx, rcx
0x1800634c3  jz      short loc_1800634CB
0x1800634c5  call    cs:__imp_ZwClose
0x1800634cb  lea     r11, [rsp+0A0h+var_s0]
0x1800634d3  mov     eax, ebx
0x1800634d5  mov     rbx, [r11+10h]
0x1800634d9  mov     rdi, [r11+20h]
0x1800634dd  mov     rsp, r11
0x1800634e0  pop     rbp
0x1800634e1  retn
```
