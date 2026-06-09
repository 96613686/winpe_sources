# CreateVmSharedMemorySection

- ea: `0x18001e248`
- end: `0x18001e405`
- name: `CreateVmSharedMemorySection`
- size: `445`
- prototype: `__int64 __fastcall(void **, __int64, __int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180013210`

## callees

- `0x180003cd6`
- `0x180003ce2`
- `0x18001e248`

## import_xrefs

- `ntdll!NtCreateFile` at `0x18001e38a`
- `ntdll!NtCreateFile` at `0x18001e38a`
- `ntdll!RtlStringFromGUIDEx` at `0x18001e2f5`
- `ntdll!RtlStringFromGUIDEx` at `0x18001e2f5`
- `ntdll!NtClose` at `0x18001e3d9`
- `ntdll!NtClose` at `0x18001e3d9`
- `ntdll!RtlFreeUnicodeString` at `0x18001e3f1`
- `ntdll!RtlFreeUnicodeString` at `0x18001e3f1`
- `ntdll!RtlAppendUnicodeToString` at `0x18001e2db`
- `ntdll!RtlAppendUnicodeToString` at `0x18001e2db`
- `ntdll!NtCreateSection` at `0x18001e3bd`
- `ntdll!NtCreateSection` at `0x18001e3bd`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001e30d`
- `ntdll!RtlAppendUnicodeStringToString` at `0x18001e30d`

## pseudocode

```c
__int64 __fastcall CreateVmSharedMemorySection(void **a1, __int64 a2, __int64 a3, __int64 *a4)
{
  __int64 v5; // rcx
  NTSTATUS appended; // ebx
  __int64 v8; // r8
  void *FileHandle; // [rsp+60h] [rbp-59h] BYREF
  _UNICODE_STRING Destination; // [rsp+68h] [rbp-51h] BYREF
  void *SectionHandle; // [rsp+78h] [rbp-41h] BYREF
  union _LARGE_INTEGER AllocationSize; // [rsp+80h] [rbp-39h] BYREF
  UNICODE_STRING Source; // [rsp+88h] [rbp-31h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-21h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp+Fh] BYREF

  FileHandle = 0;
  v5 = *a4;
  SectionHandle = 0;
  AllocationSize.QuadPart = (v5 + 4095) & 0xFFFFFFFFFFFFF000uLL;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  Source = 0;
  Destination = 0;
  if ( v5 > 0 )
  {
    Destination.MaximumLength = 224;
    Destination.Buffer = (PWSTR)LocalAlloc_0(0x40u, 0xE0u);
    if ( Destination.Buffer )
    {
      appended = RtlAppendUnicodeToString(
                   &Destination,
                   L"\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d07-847c-3493609c0870}\\SharedMemory$\\");
      if ( appended >= 0 )
      {
        LOBYTE(v8) = 1;
        appended = RtlStringFromGUIDEx(a2, &Source, v8);
        if ( appended >= 0 )
        {
          appended = RtlAppendUnicodeStringToString(&Destination, &Source);
          if ( appended >= 0 )
          {
            ObjectAttributes.ObjectName = &Destination;
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            appended = NtCreateFile(
                         &FileHandle,
                         3u,
                         &ObjectAttributes,
                         &IoStatusBlock,
                         &AllocationSize,
                         0x80u,
                         0,
                         3u,
                         0,
                         0,
                         0);
            if ( appended >= 0 )
            {
              appended = NtCreateSection(&SectionHandle, 6u, 0, 0, 4u, 0x8000000u, FileHandle);
              if ( appended >= 0 )
                *a1 = SectionHandle;
            }
          }
        }
      }
    }
    else
    {
      appended = -1073741670;
    }
    if ( FileHandle )
      NtClose(FileHandle);
  }
  else
  {
    appended = -1073741582;
  }
  if ( Destination.Buffer )
    LocalFree_0(Destination.Buffer);
  RtlFreeUnicodeString(&Source);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18001e248  push    rbp
0x18001e24a  push    rbx
0x18001e24b  push    rsi
0x18001e24c  push    rdi
0x18001e24d  lea     rbp, [rsp-2Fh]
0x18001e252  sub     rsp, 0E8h
0x18001e259  xor     eax, eax
0x18001e25b  xorps   xmm0, xmm0
0x18001e25e  mov     [rbp+47h+FileHandle], rax
0x18001e262  mov     rdi, rcx
0x18001e265  mov     rcx, [r9]
0x18001e268  xorps   xmm1, xmm1
0x18001e26b  mov     [rbp+47h+SectionHandle], rax
0x18001e26f  mov     rsi, rdx
0x18001e272  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x18001e276  lea     rax, [rcx+0FFFh]
0x18001e27d  and     rax, 0FFFFFFFFFFFFF000h
0x18001e283  mov     qword ptr [rbp+47h+var_80], rax
0x18001e287  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x18001e28b  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x18001e28f  movups  xmmword ptr [rbp+47h+IoStatusBlock], xmm0
0x18001e293  movups  xmmword ptr [rbp+47h+Source.Length], xmm1
0x18001e297  movups  xmmword ptr [rbp+47h+Destination.Length], xmm0
0x18001e29b  test    rcx, rcx
0x18001e29e  jg      short loc_18001E2AA
0x18001e2a0  mov     ebx, 0C00000F2h
0x18001e2a5  jmp     loc_18001E3DF
0x18001e2aa  mov     edx, 0E0h; uBytes
0x18001e2af  mov     ecx, 40h ; '@'; uFlags
0x18001e2b4  mov     [rbp+47h+Destination.MaximumLength], dx
0x18001e2b8  call    LocalAlloc_0
0x18001e2bd  mov     [rbp+47h+Destination.Buffer], rax
0x18001e2c1  test    rax, rax
0x18001e2c4  jnz     short loc_18001E2D0
0x18001e2c6  mov     ebx, 0C000009Ah
0x18001e2cb  jmp     loc_18001E3D0
0x18001e2d0  lea     rdx, Source; "\\Device\\vmsmb\\VSMB-{dcc079ae-60ba-4d"...
0x18001e2d7  lea     rcx, [rbp+47h+Destination]; Destination
0x18001e2db  call    cs:__imp_RtlAppendUnicodeToString
0x18001e2e1  mov     ebx, eax
0x18001e2e3  test    eax, eax
0x18001e2e5  js      loc_18001E3D0
0x18001e2eb  mov     r8b, 1
0x18001e2ee  lea     rdx, [rbp+47h+Source]
0x18001e2f2  mov     rcx, rsi
0x18001e2f5  call    cs:__imp_RtlStringFromGUIDEx
0x18001e2fb  mov     ebx, eax
0x18001e2fd  test    eax, eax
0x18001e2ff  js      loc_18001E3D0
0x18001e305  lea     rdx, [rbp+47h+Source]; Source
0x18001e309  lea     rcx, [rbp+47h+Destination]; Destination
0x18001e30d  call    cs:__imp_RtlAppendUnicodeStringToString
0x18001e313  mov     ebx, eax
0x18001e315  test    eax, eax
0x18001e317  js      loc_18001E3D0
0x18001e31d  mov     [rsp+100h+EaLength], 0; EaLength
0x18001e325  lea     rax, [rbp+47h+Destination]
0x18001e329  mov     [rsp+100h+EaBuffer], 0; EaBuffer
0x18001e332  lea     r9, [rbp+47h+IoStatusBlock]; IoStatusBlock
0x18001e336  mov     [rsp+100h+CreateOptions], 0; CreateOptions
0x18001e33e  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x18001e342  mov     edx, 3; DesiredAccess
0x18001e347  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x18001e34b  mov     [rsp+100h+CreateDisposition], edx; CreateDisposition
0x18001e34f  lea     rax, [rbp+47h+var_80]
0x18001e353  mov     [rsp+100h+ShareAccess], 0; ShareAccess
0x18001e35b  lea     rcx, [rbp+47h+FileHandle]; FileHandle
0x18001e35f  xorps   xmm0, xmm0
0x18001e362  mov     [rsp+100h+FileAttributes], 80h; FileAttributes
0x18001e36a  mov     [rsp+100h+AllocationSize], rax; AllocationSize
0x18001e36f  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x18001e376  mov     [rbp+47h+ObjectAttributes.RootDirectory], 0
0x18001e37e  mov     [rbp+47h+ObjectAttributes.Attributes], 40h ; '@'
0x18001e385  movdqu  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001e38a  call    cs:__imp_NtCreateFile
0x18001e390  mov     ebx, eax
0x18001e392  test    eax, eax
0x18001e394  js      short loc_18001E3D0
0x18001e396  mov     rax, [rbp+47h+FileHandle]
0x18001e39a  lea     rcx, [rbp+47h+SectionHandle]; SectionHandle
0x18001e39e  mov     qword ptr [rsp+100h+ShareAccess], rax; FileHandle
0x18001e3a3  xor     r9d, r9d; MaximumSize
0x18001e3a6  mov     [rsp+100h+FileAttributes], 8000000h; AllocationAttributes
0x18001e3ae  xor     r8d, r8d; ObjectAttributes
0x18001e3b1  mov     dword ptr [rsp+100h+AllocationSize], 4; SectionPageProtection
0x18001e3b9  lea     edx, [r9+6]; DesiredAccess
0x18001e3bd  call    cs:__imp_NtCreateSection
0x18001e3c3  mov     ebx, eax
0x18001e3c5  test    eax, eax
0x18001e3c7  js      short loc_18001E3D0
0x18001e3c9  mov     rax, [rbp+47h+SectionHandle]
0x18001e3cd  mov     [rdi], rax
0x18001e3d0  mov     rcx, [rbp+47h+FileHandle]; Handle
0x18001e3d4  test    rcx, rcx
0x18001e3d7  jz      short loc_18001E3DF
0x18001e3d9  call    cs:__imp_NtClose
0x18001e3df  mov     rcx, [rbp+47h+Destination.Buffer]; hMem
0x18001e3e3  test    rcx, rcx
0x18001e3e6  jz      short loc_18001E3ED
0x18001e3e8  call    LocalFree_0
0x18001e3ed  lea     rcx, [rbp+47h+Source]; UnicodeString
0x18001e3f1  call    cs:__imp_RtlFreeUnicodeString
0x18001e3f7  mov     eax, ebx
0x18001e3f9  add     rsp, 0E8h
0x18001e400  pop     rdi
0x18001e401  pop     rsi
0x18001e402  pop     rbx
0x18001e403  pop     rbp
0x18001e404  retn
```
