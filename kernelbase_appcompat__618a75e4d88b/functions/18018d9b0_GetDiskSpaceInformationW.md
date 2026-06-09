# GetDiskSpaceInformationW

- ea: `0x18018d9b0`
- end: `0x18018db72`
- name: `GetDiskSpaceInformationW`
- size: `450`
- prototype: `HRESULT __stdcall(LPCWSTR rootPath, DISK_SPACE_INFORMATION *diskSpaceInfo)`
- caller_count: `2`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18018d930`
- `0x18018db80`

## callees

- `0x18004b9d0`
- `0x18018d9b0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x18018da7a`
- `ntdll!NtOpenFile` at `0x18018da7a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18018da04`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18018da04`
- `ntdll!NtQueryVolumeInformationFile` at `0x18018db2e`
- `ntdll!NtQueryVolumeInformationFile` at `0x18018db2e`
- `ntdll!RtlSetLastWin32Error` at `0x18018da19`
- `ntdll!RtlSetLastWin32Error` at `0x18018daa5`
- `ntdll!RtlSetLastWin32Error` at `0x18018db02`
- `ntdll!RtlSetLastWin32Error` at `0x18018da19`
- `ntdll!RtlSetLastWin32Error` at `0x18018daa5`
- `ntdll!RtlSetLastWin32Error` at `0x18018db02`
- `ntdll!NtClose` at `0x18018db40`
- `ntdll!NtClose` at `0x18018db40`
- `ntdll!RtlFreeHeap` at `0x18018dac3`
- `ntdll!RtlFreeHeap` at `0x18018daec`
- `ntdll!RtlFreeHeap` at `0x18018dac3`
- `ntdll!RtlFreeHeap` at `0x18018daec`

## pseudocode

```c
HRESULT __stdcall GetDiskSpaceInformationW(LPCWSTR rootPath, DISK_SPACE_INFORMATION *diskSpaceInfo)
{
  const WCHAR *v3; // rcx
  PWSTR Buffer; // rdi
  NTSTATUS v7; // eax
  NTSTATUS v8; // ebx
  struct _UNICODE_STRING NtPathName; // [rsp+30h] [rbp-50h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  int v12; // [rsp+B0h] [rbp+30h] BYREF
  HANDLE FileHandle; // [rsp+B8h] [rbp+38h] BYREF

  v12 = 92;
  v3 = (const WCHAR *)&v12;
  FileHandle = 0;
  if ( rootPath )
    v3 = rootPath;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  if ( !RtlDosPathNameToNtPathName_U(v3, &NtPathName, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    return -2147024893;
  }
  Buffer = NtPathName.Buffer;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0x800021u);
  v8 = v7;
  if ( v7 < 0 )
  {
    BaseSetLastNTError((unsigned int)v7);
    if ( NtCurrentTeb()->LastErrorValue == 2 )
      RtlSetLastWin32Error(3u);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    return v8 | 0x10000000;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( diskSpaceInfo )
  {
    v8 = NtQueryVolumeInformationFile(
           FileHandle,
           &IoStatusBlock,
           diskSpaceInfo,
           0x60u,
           FileFsMaximumInformation|FileFsDeviceInformation);
    NtClose(FileHandle);
    if ( v8 < 0 )
    {
      BaseSetLastNTError((unsigned int)v8);
      return v8 | 0x10000000;
    }
    return 0;
  }
  else
  {
    RtlSetLastWin32Error(0xC000000D);
    return -805306355;
  }
}

```

## disassembly

```asm
0x18018d9b0  mov     [rsp-18h+arg_0], rbx
0x18018d9b5  push    rbp
0x18018d9b6  push    rsi
0x18018d9b7  push    rdi
0x18018d9b8  mov     rbp, rsp
0x18018d9bb  sub     rsp, 80h
0x18018d9c2  mov     r8, rcx
0x18018d9c5  mov     [rbp+arg_10], 5Ch ; '\'
0x18018d9cc  xorps   xmm0, xmm0
0x18018d9cf  lea     rcx, [rbp+arg_10]
0x18018d9d3  xor     eax, eax
0x18018d9d5  mov     rsi, rdx
0x18018d9d8  test    r8, r8
0x18018d9db  mov     [rbp+FileHandle], rax
0x18018d9df  xorps   xmm1, xmm1
0x18018d9e2  lea     rdx, [rbp+NtPathName]; NtPathName
0x18018d9e6  cmovnz  rcx, r8; DosPathName
0x18018d9ea  xor     r9d, r9d; DirectoryInfo
0x18018d9ed  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18018d9f1  xor     r8d, r8d; NtFileNamePart
0x18018d9f4  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18018d9f8  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x18018d9fc  movups  xmmword ptr [rbp+NtPathName.Length], xmm0
0x18018da00  movups  xmmword ptr [rbp+IoStatusBlock], xmm1
0x18018da04  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x18018da0b  nop     dword ptr [rax+rax+00h]
0x18018da10  test    al, al
0x18018da12  jnz     short loc_18018DA2F
0x18018da14  mov     ecx, 3; LastError
0x18018da19  call    cs:__imp_RtlSetLastWin32Error
0x18018da20  nop     dword ptr [rax+rax+00h]
0x18018da25  mov     eax, 80070003h
0x18018da2a  jmp     loc_18018DB5E
0x18018da2f  mov     rdi, [rbp+NtPathName.Buffer]
0x18018da33  lea     rax, [rbp+NtPathName]
0x18018da37  xorps   xmm0, xmm0
0x18018da3a  mov     [rsp+80h+OpenOptions], 800021h; OpenOptions
0x18018da42  lea     r9, [rbp+IoStatusBlock]; IoStatusBlock
0x18018da46  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18018da4a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18018da4e  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18018da55  mov     edx, 100000h; DesiredAccess
0x18018da5a  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18018da62  lea     rcx, [rbp+FileHandle]; FileHandle
0x18018da66  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18018da6d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18018da72  mov     [rsp+80h+ShareAccess], 0; ShareAccess
0x18018da7a  call    cs:__imp_NtOpenFile
0x18018da81  nop     dword ptr [rax+rax+00h]
0x18018da86  mov     ebx, eax
0x18018da88  test    eax, eax
0x18018da8a  jns     short loc_18018DADA
0x18018da8c  mov     ecx, eax
0x18018da8e  call    BaseSetLastNTError
0x18018da93  mov     ecx, gs:68h
0x18018da9b  cmp     ecx, 2
0x18018da9e  jnz     short loc_18018DAB1
0x18018daa0  mov     ecx, 3; LastError
0x18018daa5  call    cs:__imp_RtlSetLastWin32Error
0x18018daac  nop     dword ptr [rax+rax+00h]
0x18018dab1  mov     rcx, gs:60h
0x18018daba  mov     r8, rdi; P
0x18018dabd  xor     edx, edx; Flags
0x18018dabf  mov     rcx, [rcx+30h]; HeapHandle
0x18018dac3  call    cs:__imp_RtlFreeHeap
0x18018daca  nop     dword ptr [rax+rax+00h]
0x18018dacf  bts     ebx, 1Ch
0x18018dad3  mov     eax, ebx
0x18018dad5  jmp     loc_18018DB5E
0x18018dada  mov     rcx, gs:60h
0x18018dae3  mov     r8, rdi; P
0x18018dae6  xor     edx, edx; Flags
0x18018dae8  mov     rcx, [rcx+30h]; HeapHandle
0x18018daec  call    cs:__imp_RtlFreeHeap
0x18018daf3  nop     dword ptr [rax+rax+00h]
0x18018daf8  test    rsi, rsi
0x18018dafb  jnz     short loc_18018DB15
0x18018dafd  mov     ecx, 0C000000Dh; LastError
0x18018db02  call    cs:__imp_RtlSetLastWin32Error
0x18018db09  nop     dword ptr [rax+rax+00h]
0x18018db0e  mov     eax, 0D000000Dh
0x18018db13  jmp     short loc_18018DB5E
0x18018db15  mov     rcx, [rbp+FileHandle]; FileHandle
0x18018db19  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x18018db1d  mov     r9d, 60h ; '`'; Length
0x18018db23  mov     [rsp+80h+ShareAccess], 0Eh; FsInformationClass
0x18018db2b  mov     r8, rsi; FsInformation
0x18018db2e  call    cs:__imp_NtQueryVolumeInformationFile
0x18018db35  nop     dword ptr [rax+rax+00h]
0x18018db3a  mov     rcx, [rbp+FileHandle]; Handle
0x18018db3e  mov     ebx, eax
0x18018db40  call    cs:__imp_NtClose
0x18018db47  nop     dword ptr [rax+rax+00h]
0x18018db4c  test    ebx, ebx
0x18018db4e  jns     short loc_18018DB5C
0x18018db50  mov     ecx, ebx
0x18018db52  call    BaseSetLastNTError
0x18018db57  jmp     loc_18018DACF
0x18018db5c  xor     eax, eax
0x18018db5e  mov     rbx, [rsp+80h+arg_0]
0x18018db66  add     rsp, 80h
0x18018db6d  pop     rdi
0x18018db6e  pop     rsi
0x18018db6f  pop     rbp
0x18018db70  retn
```
