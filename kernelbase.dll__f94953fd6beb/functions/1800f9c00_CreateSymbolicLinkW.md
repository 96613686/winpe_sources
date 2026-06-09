# CreateSymbolicLinkW

- ea: `0x1800f9c00`
- end: `0x1800f9ff8`
- name: `CreateSymbolicLinkW`
- size: `1016`
- prototype: `BOOLEAN __stdcall(LPCWSTR lpSymlinkFileName, LPCWSTR lpTargetFileName, DWORD dwFlags)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x1800134a0`
- `0x1800f9c00`
- `0x180124148`
- `0x18012d119`
- `0x180188eb9`

## import_xrefs

- `ntdll!wcslen` at `0x1800f9cff`
- `ntdll!wcslen` at `0x1800f9d68`
- `ntdll!wcslen` at `0x1800f9f34`
- `ntdll!wcslen` at `0x1800f9cff`
- `ntdll!wcslen` at `0x1800f9d68`
- `ntdll!wcslen` at `0x1800f9f34`
- `ntdll!NtSetInformationFile` at `0x1800f9fc6`
- `ntdll!NtSetInformationFile` at `0x1800f9fc6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f9ce7`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f9db2`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f9ce7`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800f9db2`
- `ntdll!NtFsControlFile` at `0x1800f9e6a`
- `ntdll!NtFsControlFile` at `0x1800f9e6a`
- `ntdll!NtCreateFile` at `0x1800f9e2c`
- `ntdll!NtCreateFile` at `0x1800f9e2c`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9c79`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9f4f`
- `ntdll!RtlSetLastWin32Error` at `0x18019529c`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9c79`
- `ntdll!RtlSetLastWin32Error` at `0x1800f9f4f`
- `ntdll!RtlSetLastWin32Error` at `0x18019529c`
- `ntdll!RtlReleasePrivilege` at `0x1800f9e81`
- `ntdll!RtlReleasePrivilege` at `0x1800f9e81`
- `ntdll!RtlAcquirePrivilege` at `0x1800f9c94`
- `ntdll!RtlAcquirePrivilege` at `0x1800f9c94`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x1800f9ca5`
- `ntdll!RtlDetermineDosPathNameType_U` at `0x1800f9ca5`
- `ntdll!NtClose` at `0x1800f9edb`
- `ntdll!NtClose` at `0x1800f9edb`
- `ntdll!RtlFreeHeap` at `0x1800f9ea7`
- `ntdll!RtlFreeHeap` at `0x1800f9ecb`
- `ntdll!RtlFreeHeap` at `0x1800f9f22`
- `ntdll!RtlFreeHeap` at `0x1800f9fed`
- `ntdll!RtlFreeHeap` at `0x1800f9ea7`
- `ntdll!RtlFreeHeap` at `0x1800f9ecb`
- `ntdll!RtlFreeHeap` at `0x1800f9f22`
- `ntdll!RtlFreeHeap` at `0x1800f9fed`
- `ntdll!RtlAllocateHeap` at `0x1800f9d25`
- `ntdll!RtlAllocateHeap` at `0x1800f9d25`

## pseudocode

```c
BOOLEAN __stdcall CreateSymbolicLinkW(LPCWSTR lpSymlinkFileName, LPCWSTR lpTargetFileName, DWORD dwFlags)
{
  char v3; // r12
  WCHAR *v4; // rsi
  _DWORD *v5; // rdi
  char v6; // r14
  void *v7; // r15
  NTSTATUS v8; // eax
  RTL_PATH_TYPE v9; // ecx
  __int32 v10; // ecx
  __int32 v11; // ecx
  __int32 v12; // ecx
  USHORT Length; // ax
  ULONG v14; // ebx
  _DWORD *Heap; // rax
  unsigned __int16 v16; // ax
  __int64 v17; // rcx
  unsigned int v18; // eax
  NTSTATUS v19; // eax
  __int64 FullPath; // rax
  ULONG v22; // ecx
  struct _UNICODE_STRING NtPathName; // [rsp+60h] [rbp-59h] BYREF
  HANDLE FileHandle; // [rsp+70h] [rbp-49h] BYREF
  ULONG Privilege; // [rsp+78h] [rbp-41h] BYREF
  struct _UNICODE_STRING v26; // [rsp+80h] [rbp-39h] BYREF
  PVOID ReturnedState; // [rsp+90h] [rbp-29h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+A8h] [rbp-11h] BYREF
  char FileInformation; // [rsp+138h] [rbp+7Fh] BYREF

  FileHandle = (HANDLE)-1LL;
  *(_QWORD *)&v26.Length = 0;
  v26.Buffer = 0;
  *(_QWORD *)&NtPathName.Length = 0;
  v3 = dwFlags;
  NtPathName.Buffer = 0;
  v4 = (WCHAR *)lpTargetFileName;
  FileInformation = 0;
  v5 = 0;
  ReturnedState = 0;
  v6 = 0;
  v7 = 0;
  memset(&ObjectAttributes, 0, 44);
  IoStatusBlock = 0;
  if ( !lpSymlinkFileName || !lpTargetFileName )
    goto LABEL_39;
  RtlSetLastWin32Error(0);
  Privilege = 35;
  v8 = RtlAcquirePrivilege(&Privilege, 1u, 0, &ReturnedState);
  if ( v8 < 0 && (v3 & 2) == 0 )
    goto LABEL_35;
  v9 = RtlDetermineDosPathNameType_U(v4);
  if ( v9 == RtlPathTypeUnknown )
    goto LABEL_32;
  v10 = v9 - 1;
  if ( !v10 || (v11 = v10 - 1) == 0 )
  {
LABEL_9:
    if ( RtlDosPathNameToNtPathName_U(v4, &NtPathName, 0, 0) )
    {
      Length = NtPathName.Length;
      goto LABEL_11;
    }
LABEL_39:
    v22 = 87;
    goto LABEL_40;
  }
  v12 = v11 - 1;
  if ( !v12 )
  {
    FullPath = GetFullPath(v4);
    v7 = (void *)FullPath;
    if ( !FullPath )
      goto LABEL_18;
    v4 = (WCHAR *)FullPath;
    goto LABEL_9;
  }
  if ( (unsigned int)(v12 - 1) >= 2 )
    goto LABEL_9;
LABEL_32:
  NtPathName.Buffer = v4;
  v6 = 1;
  Length = 2 * wcslen(v4);
  NtPathName.MaximumLength = Length;
  NtPathName.Length = Length;
LABEL_11:
  v14 = Length + 2 * (wcslen(v4) + 10);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, v14);
  v5 = Heap;
  if ( !Heap )
  {
    RtlSetLastWin32Error(8u);
    goto LABEL_18;
  }
  memset_0(Heap, 0, v14);
  if ( v6 )
    v5[4] |= 1u;
  *v5 = -1610612724;
  *((_WORD *)v5 + 2) = v14 - 8;
  *((_WORD *)v5 + 6) = 0;
  v16 = 2 * wcslen(v4);
  *((_WORD *)v5 + 7) = v16;
  memcpy_0(v5 + 5, v4, v16);
  v17 = *((unsigned __int16 *)v5 + 7);
  *((_WORD *)v5 + 4) = v17;
  v18 = NtPathName.Length;
  *((_WORD *)v5 + 5) = NtPathName.Length;
  memcpy_0((char *)v5 + v17 + 20, NtPathName.Buffer, v18);
  if ( !RtlDosPathNameToNtPathName_U(lpSymlinkFileName, &v26, 0, 0) )
  {
    v22 = 3;
LABEL_40:
    RtlSetLastWin32Error(v22);
    goto LABEL_18;
  }
  ObjectAttributes.ObjectName = &v26;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v8 = NtCreateFile(
         &FileHandle,
         0x110100u,
         &ObjectAttributes,
         &IoStatusBlock,
         0,
         0x80u,
         0,
         2u,
         (v3 & 1) != 0 ? 2097185 : 2097248,
         0,
         0);
  if ( v8 < 0 )
  {
LABEL_35:
    BaseSetLastNTError((unsigned int)v8);
    goto LABEL_18;
  }
  v19 = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x900A4u, v5, v14, 0, 0);
  if ( v19 < 0 )
  {
    BaseSetLastNTError((unsigned int)v19);
    FileInformation = 1;
    NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 1u, FileDispositionInformation);
  }
LABEL_18:
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  if ( v7 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  if ( v5 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
  if ( !v6 && NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v26.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v26.Buffer);
  if ( FileHandle != (HANDLE)-1LL )
    NtClose(FileHandle);
  return NtCurrentTeb()->LastErrorValue == 0;
}

```

## disassembly

```asm
0x1800f9c00  mov     [rsp-8+arg_8], rbx
0x1800f9c05  mov     [rsp-8+DosPathName], rcx
0x1800f9c0a  push    rbp
0x1800f9c0b  push    rsi
0x1800f9c0c  push    rdi
0x1800f9c0d  push    r12
0x1800f9c0f  push    r13
0x1800f9c11  push    r14
0x1800f9c13  push    r15
0x1800f9c15  lea     rbp, [rsp-27h]
0x1800f9c1a  sub     rsp, 0E0h
0x1800f9c21  xor     ebx, ebx
0x1800f9c23  mov     [rbp+57h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800f9c2b  xorps   xmm0, xmm0
0x1800f9c2e  mov     qword ptr [rbp+57h+var_90.Length], rbx
0x1800f9c32  xor     eax, eax
0x1800f9c34  mov     [rbp+57h+var_90.Buffer], rbx
0x1800f9c38  mov     qword ptr [rbp+57h+NtPathName.Length], rbx
0x1800f9c3c  mov     r12d, r8d
0x1800f9c3f  mov     [rbp+57h+NtPathName.Buffer], rbx
0x1800f9c43  mov     rsi, rdx
0x1800f9c46  mov     [rbp+57h+FileInformation], bl
0x1800f9c49  mov     edi, ebx
0x1800f9c4b  mov     [rbp+57h+ReturnedState], rbx
0x1800f9c4f  mov     r14b, bl
0x1800f9c52  mov     r15d, ebx
0x1800f9c55  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800f9c59  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1800f9c5d  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800f9c61  movups  xmmword ptr [rbp+57h+IoStatusBlock], xmm0
0x1800f9c65  test    rcx, rcx
0x1800f9c68  jz      loc_1800F9FD1
0x1800f9c6e  test    rdx, rdx
0x1800f9c71  jz      loc_1800F9FD1
0x1800f9c77  xor     ecx, ecx; LastError
0x1800f9c79  call    cs:__imp_RtlSetLastWin32Error
0x1800f9c7f  lea     r9, [rbp+57h+ReturnedState]; ReturnedState
0x1800f9c83  mov     [rbp+57h+Privilege], 23h ; '#'
0x1800f9c8a  xor     r8d, r8d; Flags
0x1800f9c8d  lea     edx, [rbx+1]; NumPriv
0x1800f9c90  lea     rcx, [rbp+57h+Privilege]; Privilege
0x1800f9c94  call    cs:__imp_RtlAcquirePrivilege
0x1800f9c9a  test    eax, eax
0x1800f9c9c  js      loc_1800F9F5C
0x1800f9ca2  mov     rcx, rsi; Path
0x1800f9ca5  call    cs:__imp_RtlDetermineDosPathNameType_U
0x1800f9cab  mov     ecx, eax
0x1800f9cad  test    eax, eax
0x1800f9caf  jz      loc_1800F9F2A
0x1800f9cb5  sub     ecx, 1
0x1800f9cb8  jz      short loc_1800F9CDA
0x1800f9cba  sub     ecx, 1
0x1800f9cbd  jz      short loc_1800F9CDA
0x1800f9cbf  sub     ecx, 1
0x1800f9cc2  jz      loc_1800F9F72
0x1800f9cc8  sub     ecx, 1
0x1800f9ccb  jz      loc_1800F9F2A
0x1800f9cd1  sub     ecx, 1
0x1800f9cd4  jz      loc_1800F9F2A
0x1800f9cda  xor     r9d, r9d; DirectoryInfo
0x1800f9cdd  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x1800f9ce1  xor     r8d, r8d; NtFileNamePart
0x1800f9ce4  mov     rcx, rsi; DosPathName
0x1800f9ce7  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800f9ced  test    al, al
0x1800f9cef  jz      loc_1800F9FD1
0x1800f9cf5  movzx   eax, [rbp+57h+NtPathName.Length]
0x1800f9cf9  mov     rcx, rsi; String
0x1800f9cfc  movzx   ebx, ax
0x1800f9cff  call    cs:__imp_wcslen
0x1800f9d05  mov     rcx, gs:60h
0x1800f9d0e  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800f9d14  lea     eax, [rax+0Ah]
0x1800f9d17  mov     rcx, [rcx+30h]; HeapHandle
0x1800f9d1b  lea     r13d, [rbx+rax*2]
0x1800f9d1f  mov     r8d, r13d; Size
0x1800f9d22  mov     ebx, r13d
0x1800f9d25  call    cs:__imp_RtlAllocateHeap
0x1800f9d2b  mov     rdi, rax
0x1800f9d2e  test    rax, rax
0x1800f9d31  jz      loc_1800F9F4A
0x1800f9d37  mov     r8d, ebx; Size
0x1800f9d3a  xor     edx, edx; Val
0x1800f9d3c  mov     rcx, rax; void *
0x1800f9d3f  call    memset_0
0x1800f9d44  test    r14b, r14b
0x1800f9d47  jnz     loc_1800F9F8E
0x1800f9d4d  lea     eax, [r13-8]
0x1800f9d51  mov     dword ptr [rdi], 0A000000Ch
0x1800f9d57  mov     [rdi+4], ax
0x1800f9d5b  lea     rbx, [rdi+14h]
0x1800f9d5f  xor     eax, eax
0x1800f9d61  mov     rcx, rsi; String
0x1800f9d64  mov     [rdi+0Ch], ax
0x1800f9d68  call    cs:__imp_wcslen
0x1800f9d6e  mov     rdx, rsi; Src
0x1800f9d71  mov     rcx, rbx; void *
0x1800f9d74  add     ax, ax
0x1800f9d77  movzx   r8d, ax; Size
0x1800f9d7b  mov     [rdi+0Eh], r8w
0x1800f9d80  call    memcpy_0
0x1800f9d85  movzx   ecx, word ptr [rdi+0Eh]
0x1800f9d89  mov     [rdi+8], cx
0x1800f9d8d  add     rcx, rbx; void *
0x1800f9d90  movzx   eax, [rbp+57h+NtPathName.Length]
0x1800f9d94  mov     [rdi+0Ah], ax
0x1800f9d98  mov     r8d, eax; Size
0x1800f9d9b  mov     rdx, [rbp+57h+NtPathName.Buffer]; Src
0x1800f9d9f  call    memcpy_0
0x1800f9da4  mov     rcx, [rbp+57h+DosPathName]; DosPathName
0x1800f9da8  lea     rdx, [rbp+57h+var_90]; NtPathName
0x1800f9dac  xor     r9d, r9d; DirectoryInfo
0x1800f9daf  xor     r8d, r8d; NtFileNamePart
0x1800f9db2  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800f9db8  xor     ebx, ebx
0x1800f9dba  test    al, al
0x1800f9dbc  jz      loc_1800F9F97
0x1800f9dc2  mov     [rsp+110h+EaLength], ebx; EaLength
0x1800f9dc6  lea     rax, [rbp+57h+var_90]
0x1800f9dca  mov     [rsp+110h+EaBuffer], rbx; EaBuffer
0x1800f9dcf  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f9dd3  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800f9dd7  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800f9ddb  xorps   xmm0, xmm0
0x1800f9dde  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800f9de5  and     r12b, 1
0x1800f9de9  mov     [rbp+57h+ObjectAttributes.RootDirectory], rbx
0x1800f9ded  neg     r12b
0x1800f9df0  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800f9df7  mov     edx, 110100h; DesiredAccess
0x1800f9dfc  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f9e00  sbb     eax, eax
0x1800f9e02  and     eax, 0FFFFFFC1h
0x1800f9e05  add     eax, 200060h
0x1800f9e0a  mov     [rsp+110h+CreateOptions], eax; CreateOptions
0x1800f9e0e  mov     [rsp+110h+CreateDisposition], 2; CreateDisposition
0x1800f9e16  mov     [rsp+110h+ShareAccess], ebx; ShareAccess
0x1800f9e1a  mov     [rsp+110h+FileAttributes], 80h; FileAttributes
0x1800f9e22  mov     [rsp+110h+AllocationSize], rbx; AllocationSize
0x1800f9e27  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800f9e2c  call    cs:__imp_NtCreateFile
0x1800f9e32  test    eax, eax
0x1800f9e34  js      loc_1800F9F66
0x1800f9e3a  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f9e3e  lea     rax, [rbp+57h+IoStatusBlock]
0x1800f9e42  mov     dword ptr [rsp+110h+EaBuffer], ebx; OutputBufferLength
0x1800f9e46  xor     r9d, r9d; ApcContext
0x1800f9e49  mov     qword ptr [rsp+110h+CreateOptions], rbx; OutputBuffer
0x1800f9e4e  xor     r8d, r8d; ApcRoutine
0x1800f9e51  mov     [rsp+110h+CreateDisposition], r13d; InputBufferLength
0x1800f9e56  xor     edx, edx; Event
0x1800f9e58  mov     qword ptr [rsp+110h+ShareAccess], rdi; InputBuffer
0x1800f9e5d  mov     [rsp+110h+FileAttributes], 900A4h; FsControlCode
0x1800f9e65  mov     [rsp+110h+AllocationSize], rax; IoStatusBlock
0x1800f9e6a  call    cs:__imp_NtFsControlFile
0x1800f9e70  test    eax, eax
0x1800f9e72  js      loc_1800F9FA1
0x1800f9e78  mov     rcx, [rbp+57h+ReturnedState]; ReturnedState
0x1800f9e7c  test    rcx, rcx
0x1800f9e7f  jz      short loc_1800F9E87
0x1800f9e81  call    cs:__imp_RtlReleasePrivilege
0x1800f9e87  test    r15, r15
0x1800f9e8a  jnz     loc_1800F9FDB
0x1800f9e90  test    rdi, rdi
0x1800f9e93  jz      short loc_1800F9EAD
0x1800f9e95  mov     rcx, gs:60h
0x1800f9e9e  mov     r8, rdi; P
0x1800f9ea1  xor     edx, edx; Flags
0x1800f9ea3  mov     rcx, [rcx+30h]; HeapHandle
0x1800f9ea7  call    cs:__imp_RtlFreeHeap
0x1800f9ead  test    r14b, r14b
0x1800f9eb0  jz      short loc_1800F9F09
0x1800f9eb2  cmp     [rbp+57h+var_90.Buffer], rbx
0x1800f9eb6  jz      short loc_1800F9ED1
0x1800f9eb8  mov     rcx, gs:60h
0x1800f9ec1  xor     edx, edx; Flags
0x1800f9ec3  mov     r8, [rbp+57h+var_90.Buffer]; P
0x1800f9ec7  mov     rcx, [rcx+30h]; HeapHandle
0x1800f9ecb  call    cs:__imp_RtlFreeHeap
0x1800f9ed1  mov     rcx, [rbp+57h+FileHandle]; Handle
0x1800f9ed5  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f9ed9  jz      short loc_1800F9EE1
0x1800f9edb  call    cs:__imp_NtClose
0x1800f9ee1  mov     eax, gs:68h
0x1800f9ee9  test    eax, eax
0x1800f9eeb  mov     rbx, [rsp+110h+arg_8]
0x1800f9ef3  setz    al
0x1800f9ef6  add     rsp, 0E0h
0x1800f9efd  pop     r15
0x1800f9eff  pop     r14
0x1800f9f01  pop     r13
0x1800f9f03  pop     r12
0x1800f9f05  pop     rdi
0x1800f9f06  pop     rsi
0x1800f9f07  pop     rbp
0x1800f9f08  retn
0x1800f9f09  cmp     [rbp+57h+NtPathName.Buffer], rbx
0x1800f9f0d  jz      short loc_1800F9EB2
0x1800f9f0f  mov     rcx, gs:60h
0x1800f9f18  xor     edx, edx; Flags
0x1800f9f1a  mov     r8, [rbp+57h+NtPathName.Buffer]; P
0x1800f9f1e  mov     rcx, [rcx+30h]; HeapHandle
0x1800f9f22  call    cs:__imp_RtlFreeHeap
0x1800f9f28  jmp     short loc_1800F9EB2
0x1800f9f2a  mov     rcx, rsi; String
0x1800f9f2d  mov     [rbp+57h+NtPathName.Buffer], rsi
0x1800f9f31  mov     r14b, 1
0x1800f9f34  call    cs:__imp_wcslen
0x1800f9f3a  add     ax, ax
0x1800f9f3d  mov     [rbp+57h+NtPathName.MaximumLength], ax
0x1800f9f41  mov     [rbp+57h+NtPathName.Length], ax
0x1800f9f45  jmp     loc_1800F9CF9
0x1800f9f4a  mov     ecx, 8; LastError
0x1800f9f4f  call    cs:__imp_RtlSetLastWin32Error
0x1800f9f55  xor     ebx, ebx
0x1800f9f57  jmp     loc_1800F9E78
0x1800f9f5c  test    r12b, 2
0x1800f9f60  jnz     loc_1800F9CA2
0x1800f9f66  mov     ecx, eax
0x1800f9f68  call    BaseSetLastNTError
0x1800f9f6d  jmp     loc_1800F9E78
0x1800f9f72  mov     rcx, rsi; lpFileName
0x1800f9f75  call    GetFullPath
0x1800f9f7a  mov     r15, rax
0x1800f9f7d  test    rax, rax
0x1800f9f80  jz      loc_1800F9E78
0x1800f9f86  mov     rsi, rax
0x1800f9f89  jmp     loc_1800F9CDA
0x1800f9f8e  or      dword ptr [rdi+10h], 1
0x1800f9f92  jmp     loc_1800F9D4D
0x1800f9f97  mov     ecx, 3; LastError
0x1800f9f9c  jmp     loc_18019529C
0x1800f9fa1  mov     ecx, eax
0x1800f9fa3  call    BaseSetLastNTError
0x1800f9fa8  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x1800f9fac  lea     r8, [rbp+57h+FileInformation]; FileInformation
0x1800f9fb0  mov     r9d, 1; Length
0x1800f9fb6  mov     [rbp+57h+FileInformation], 1
0x1800f9fba  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x1800f9fbe  mov     dword ptr [rsp+110h+AllocationSize], 0Dh; FileInformationClass
0x1800f9fc6  call    cs:__imp_NtSetInformationFile
0x1800f9fcc  jmp     loc_1800F9E78
0x1800f9fd1  mov     ecx, 57h ; 'W'
0x1800f9fd6  jmp     loc_18019529C
0x1800f9fdb  mov     rcx, gs:60h
0x1800f9fe4  mov     r8, r15; P
0x1800f9fe7  xor     edx, edx; Flags
0x1800f9fe9  mov     rcx, [rcx+30h]; HeapHandle
0x1800f9fed  call    cs:__imp_RtlFreeHeap
0x1800f9ff3  jmp     loc_1800F9E90
0x18019529c  call    cs:__imp_RtlSetLastWin32Error
0x1801952a2  nop
0x1801952a3  jmp     loc_1800F9E78
```
