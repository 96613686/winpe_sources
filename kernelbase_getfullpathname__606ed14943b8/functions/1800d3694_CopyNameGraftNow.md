# CopyNameGraftNow

- ea: `0x1800d3694`
- end: `0x1800d3e4b`
- name: `CopyNameGraftNow`
- size: `1975`
- prototype: `__int64 __usercall@<rax>(HANDLE FileHandle@<rcx>, int, int, int, __int64, HANDLE Event)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f9650`

## callees

- `0x18004b9d0`
- `0x180053c30`
- `0x1800d3694`
- `0x1800d3eb0`
- `0x1801373a0`
- `0x180194f10`

## import_xrefs

- `ntdll!NtQueryInformationFile` at `0x1800d3a1f`
- `ntdll!NtQueryInformationFile` at `0x1800d3a1f`
- `ntdll!NtSetInformationFile` at `0x1800d3a71`
- `ntdll!NtSetInformationFile` at `0x1800d3b21`
- `ntdll!NtSetInformationFile` at `0x1800d3a71`
- `ntdll!NtSetInformationFile` at `0x1800d3b21`
- `ntdll!NtFsControlFile` at `0x1800d386d`
- `ntdll!NtFsControlFile` at `0x1800d39e3`
- `ntdll!NtFsControlFile` at `0x1800d386d`
- `ntdll!NtFsControlFile` at `0x1800d39e3`
- `ntdll!NtCreateFile` at `0x1800d395a`
- `ntdll!NtCreateFile` at `0x1800d3aee`
- `ntdll!NtCreateFile` at `0x1800d395a`
- `ntdll!NtCreateFile` at `0x1800d3aee`
- `ntdll!RtlSetLastWin32Error` at `0x1800d3c25`
- `ntdll!RtlSetLastWin32Error` at `0x1800d3c76`
- `ntdll!RtlSetLastWin32Error` at `0x1800d3c25`
- `ntdll!RtlSetLastWin32Error` at `0x1800d3c76`
- `ntdll!NtWaitForSingleObject` at `0x1800d3c9e`
- `ntdll!NtWaitForSingleObject` at `0x1800d3c9e`
- `ntdll!RtlEqualUnicodeString` at `0x1800d381a`
- `ntdll!RtlEqualUnicodeString` at `0x1800d381a`
- `ntdll!RtlReleasePrivilege` at `0x1800d3d95`
- `ntdll!RtlReleasePrivilege` at `0x1801978bb`
- `ntdll!RtlReleasePrivilege` at `0x1800d3d95`
- `ntdll!RtlReleasePrivilege` at `0x1801978bb`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800d37a9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800d37e3`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800d37a9`
- `ntdll!RtlDosPathNameToNtPathName_U_WithStatus` at `0x1800d37e3`
- `ntdll!RtlAcquirePrivilege` at `0x1800d3d01`
- `ntdll!RtlAcquirePrivilege` at `0x1800d3d01`
- `ntdll!RtlGetCurrentTransaction` at `0x1800d3bf6`
- `ntdll!RtlGetCurrentTransaction` at `0x1800d3bf6`
- `ntdll!RtlFreeHeap` at `0x1800d3dca`
- `ntdll!RtlFreeHeap` at `0x1800d3ded`
- `ntdll!RtlFreeHeap` at `0x1800d3e0b`
- `ntdll!RtlFreeHeap` at `0x1801978f7`
- `ntdll!RtlFreeHeap` at `0x180197919`
- `ntdll!RtlFreeHeap` at `0x18019793b`
- `ntdll!RtlFreeHeap` at `0x1800d3dca`
- `ntdll!RtlFreeHeap` at `0x1800d3ded`
- `ntdll!RtlFreeHeap` at `0x1800d3e0b`
- `ntdll!RtlFreeHeap` at `0x1801978f7`
- `ntdll!RtlFreeHeap` at `0x180197919`
- `ntdll!RtlFreeHeap` at `0x18019793b`
- `ntdll!RtlAllocateHeap` at `0x1800d3778`
- `ntdll!RtlAllocateHeap` at `0x1800d3778`
- `ext-ms-win-kernel32-file-l1-1-0!SetVolumeMountPointWStub` at `0x1800d3d51`
- `ext-ms-win-kernel32-file-l1-1-0!SetVolumeMountPointWStub` at `0x1800d3d51`

## pseudocode

```c
__int64 __fastcall CopyNameGraftNow(
        HANDLE FileHandle,
        __int64 a2,
        __int64 a3,
        int a4,
        int a5,
        int a6,
        int a7,
        _BYTE *a8,
        HANDLE Event)
{
  NTSTATUS Status; // ebx
  int Information; // r12d
  unsigned __int16 *OutputBuffer; // r14
  int v15; // eax
  const WCHAR *v16; // rsi
  int v17; // eax
  ULONG v18; // eax
  NTSTATUS v19; // eax
  unsigned int v20; // edi
  PWSTR v21; // rax
  __int64 v22; // rcx
  NTSTATUS v23; // eax
  int v24; // eax
  HANDLE FileHandlea; // [rsp+68h] [rbp-120h] BYREF
  int v27; // [rsp+70h] [rbp-118h]
  ULONG Privilege[2]; // [rsp+78h] [rbp-110h] BYREF
  PVOID ReturnedState; // [rsp+80h] [rbp-108h] BYREF
  PVOID P; // [rsp+88h] [rbp-100h]
  PVOID Buffer; // [rsp+90h] [rbp-F8h]
  UNICODE_STRING String1; // [rsp+98h] [rbp-F0h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-E0h] BYREF
  UNICODE_STRING String2; // [rsp+B8h] [rbp-D0h] BYREF
  struct _IO_STATUS_BLOCK v35; // [rsp+C8h] [rbp-C0h] BYREF
  int v36; // [rsp+D8h] [rbp-B0h]
  __int64 v37; // [rsp+E0h] [rbp-A8h]
  unsigned __int16 *v38; // [rsp+E8h] [rbp-A0h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F0h] [rbp-98h] BYREF
  _OWORD FileInformation[2]; // [rsp+120h] [rbp-68h] BYREF
  __int64 v41; // [rsp+140h] [rbp-48h]

  *(_QWORD *)Privilege = a3;
  v37 = a3;
  Status = 0;
  FileHandlea = (HANDLE)-1LL;
  IoStatusBlock = 0;
  memset(FileInformation, 0, sizeof(FileInformation));
  v41 = 0;
  v36 = 0;
  String1 = 0;
  String2 = 0;
  P = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  v35 = 0;
  Information = 0;
  v27 = 0;
  ReturnedState = 0;
  OutputBuffer = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, KernelBaseGlobalData, 0x4000u);
  v38 = OutputBuffer;
  if ( !OutputBuffer )
  {
    BaseSetLastNTError(3221225495LL);
    return 0;
  }
  v15 = RtlDosPathNameToNtPathName_U_WithStatus(a2, &String1, 0, 0);
  if ( v15 < 0 )
  {
    if ( v15 == -1073741801 || v15 == -1073741670 )
      BaseSetLastNTError((unsigned int)v15);
    else
      RtlSetLastWin32Error(3u);
    FileHandlea = (HANDLE)-1LL;
    v16 = *(const WCHAR **)Privilege;
    goto LABEL_48;
  }
  P = String1.Buffer;
  v16 = *(const WCHAR **)Privilege;
  v17 = RtlDosPathNameToNtPathName_U_WithStatus(*(_QWORD *)Privilege, &String2, 0, 0);
  if ( v17 < 0 )
  {
    if ( v17 == -1073741801 || v17 == -1073741670 )
      BaseSetLastNTError((unsigned int)v17);
    else
      RtlSetLastWin32Error(3u);
    goto LABEL_53;
  }
  Buffer = String2.Buffer;
  if ( RtlEqualUnicodeString(&String1, &String2, 1u) )
  {
LABEL_53:
    FileHandlea = (HANDLE)-1LL;
    goto LABEL_48;
  }
  Status = NtFsControlFile(FileHandle, Event, 0, 0, &IoStatusBlock, 0x900A8u, 0, 0, OutputBuffer, 0x4000u);
  if ( Status == 259 )
  {
    do
    {
      v23 = NtWaitForSingleObject(Event, 1u, 0);
      Status = v23;
      if ( v23 >= 0 && v23 != 257 )
        Status = IoStatusBlock.Status;
    }
    while ( Status == 257 );
  }
  if ( Status < 0 )
    goto LABEL_46;
  if ( *(_DWORD *)OutputBuffer == -1610612733 )
  {
    if ( *(_DWORD *)OutputBuffer != -1610612724 )
      goto LABEL_9;
  }
  else if ( *(_DWORD *)OutputBuffer != -1610612724 )
  {
    v22 = 3221225523LL;
    goto LABEL_47;
  }
  Privilege[0] = 35;
  v19 = RtlAcquirePrivilege(Privilege, 1u, 0, &ReturnedState);
  Status = v19;
  if ( v19 < 0 )
    goto LABEL_62;
LABEL_9:
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &String2;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( (a4 & 1) != 0 )
    v18 = !(*a8 & 1) + 2;
  else
    v18 = 2 * (*(_DWORD *)a8 & 1);
  Status = NtCreateFile(&FileHandlea, 0xC0000000, &ObjectAttributes, &v35, 0, 0, 3u, v18, a4 | 0x200000, 0, 0);
  if ( Status < 0 )
  {
    FileHandlea = (HANDLE)-1LL;
LABEL_46:
    v22 = (unsigned int)Status;
    goto LABEL_47;
  }
  Information = v35.Information;
  v27 = v35.Information;
  if ( String1.Length == 96 )
  {
    v21 = String1.Buffer;
  }
  else
  {
    if ( String1.Length != 98 )
      goto LABEL_14;
    v21 = String1.Buffer;
    if ( String1.Buffer[48] != 92 )
      goto LABEL_14;
  }
  if ( *v21 != 92
    || v21[1] != 63 && v21[1] != 92
    || v21[2] != 63
    || v21[3] != 92
    || v21[4] != 86
    || v21[5] != 111
    || v21[6] != 108
    || v21[7] != 117
    || v21[8] != 109
    || v21[9] != 101
    || v21[10] != 123
    || v21[19] != 45
    || v21[24] != 45
    || v21[29] != 45
    || v21[34] != 45
    || v21[47] != 125 )
  {
LABEL_14:
    v19 = NtFsControlFile(FileHandlea, 0, 0, 0, &IoStatusBlock, 0x900A4u, OutputBuffer, OutputBuffer[2] + 8, 0, 0);
    Status = v19;
    if ( v19 >= 0 )
    {
LABEL_15:
      v19 = NtQueryInformationFile(FileHandle, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
      Status = v19;
      if ( v19 >= 0 )
      {
        FileInformation[0] = 0;
        LODWORD(v41) = 0;
        Status = NtSetInformationFile(FileHandlea, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
        if ( Status == -1073741757 )
        {
          CloseHandle(FileHandlea);
          Status = NtCreateFile(&FileHandlea, 0x100u, &ObjectAttributes, &v35, 0, 0, 0, 1u, a4 | 0x200000, 0, 0);
          if ( Status >= 0 )
            Status = NtSetInformationFile(FileHandlea, &IoStatusBlock, FileInformation, 0x28u, FileBasicInformation);
        }
        v20 = 1;
        goto LABEL_71;
      }
    }
LABEL_62:
    v22 = (unsigned int)v19;
    goto LABEL_47;
  }
  if ( !RtlGetCurrentTransaction() )
  {
    if ( (unsigned __int8)IsBasepGetComputerNameFromNtPathPresent() )
    {
      v24 = SetVolumeMountPointWStub(v16, OutputBuffer + 8);
    }
    else
    {
      BaseSetLastNTError(3221225659LL);
      v24 = 0;
    }
    if ( !v24 )
      goto LABEL_48;
    goto LABEL_15;
  }
  v22 = 3221225659LL;
LABEL_47:
  BaseSetLastNTError(v22);
LABEL_48:
  v20 = 0;
LABEL_71:
  if ( FileHandlea != (HANDLE)-1LL )
    CloseHandle(FileHandlea);
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  if ( Status < 0 && Information == 2 )
    DeleteFileW(v16);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, OutputBuffer);
  return v20;
}

```

## disassembly

```asm
0x1800d3694  mov     r11, rsp
0x1800d3697  push    rbx
0x1800d3698  push    rsi
0x1800d3699  push    rdi
0x1800d369a  push    r12
0x1800d369c  push    r13
0x1800d369e  push    r14
0x1800d36a0  push    r15
0x1800d36a2  sub     rsp, 150h
0x1800d36a9  mov     rax, cs:__security_cookie
0x1800d36b0  xor     rax, rsp
0x1800d36b3  mov     [rsp+188h+var_40], rax
0x1800d36bb  mov     r15d, r9d
0x1800d36be  mov     rax, r8
0x1800d36c1  mov     qword ptr [rsp+188h+Privilege], rax
0x1800d36c6  mov     rsi, rdx
0x1800d36c9  mov     r13, rcx
0x1800d36cc  mov     [rsp+188h+var_A8], rax
0x1800d36d4  mov     rdi, [rsp+188h+Event]
0x1800d36dc  xor     ecx, ecx
0x1800d36de  mov     ebx, ecx
0x1800d36e0  mov     [rsp+188h+var_128], ecx
0x1800d36e4  mov     [rsp+188h+var_124], ecx
0x1800d36e8  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800d36f1  xorps   xmm0, xmm0
0x1800d36f4  movups  xmmword ptr [rsp+188h+var_E0], xmm0
0x1800d36fc  xorps   xmm1, xmm1
0x1800d36ff  xor     eax, eax
0x1800d3701  movups  xmmword ptr [r11-68h], xmm1
0x1800d3706  movups  xmmword ptr [r11-58h], xmm1
0x1800d370b  mov     [r11-48h], rax
0x1800d370f  mov     [rsp+188h+var_B0], ecx
0x1800d3716  movups  xmmword ptr [rsp+188h+String1.Length], xmm0
0x1800d371e  movups  xmmword ptr [rsp+188h+String2.Length], xmm1
0x1800d3726  mov     [r11-100h], rcx
0x1800d372d  mov     [r11-0F8h], rcx
0x1800d3734  movups  xmmword ptr [rsp+188h+ObjectAttributes.Length], xmm0
0x1800d373c  movups  xmmword ptr [rsp+188h+ObjectAttributes.ObjectName], xmm0
0x1800d3744  movups  xmmword ptr [r11-7Ch], xmm0
0x1800d3749  movups  xmmword ptr [rsp+188h+var_C0], xmm0
0x1800d3751  mov     r12d, ecx
0x1800d3754  mov     [rsp+188h+var_118], ecx
0x1800d3758  mov     [r11-108h], rcx
0x1800d375f  mov     rcx, gs:60h
0x1800d3768  mov     r8d, 4000h; Size
0x1800d376e  mov     edx, cs:KernelBaseGlobalData; Flags
0x1800d3774  mov     rcx, [rcx+30h]; HeapHandle
0x1800d3778  call    cs:__imp_RtlAllocateHeap
0x1800d377f  nop     dword ptr [rax+rax+00h]
0x1800d3784  mov     r14, rax
0x1800d3787  mov     [rsp+188h+var_A0], rax
0x1800d378f  test    rax, rax
0x1800d3792  jz      loc_1800D3E3D
0x1800d3798  xor     r9d, r9d
0x1800d379b  xor     r8d, r8d
0x1800d379e  lea     rdx, [rsp+188h+String1]
0x1800d37a6  mov     rcx, rsi
0x1800d37a9  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800d37b0  nop     dword ptr [rax+rax+00h]
0x1800d37b5  test    eax, eax
0x1800d37b7  js      loc_1800D3C12
0x1800d37bd  mov     rax, [rsp+188h+String1.Buffer]
0x1800d37c5  mov     [rsp+188h+P], rax
0x1800d37cd  xor     r9d, r9d
0x1800d37d0  xor     r8d, r8d
0x1800d37d3  lea     rdx, [rsp+188h+String2]
0x1800d37db  mov     rsi, qword ptr [rsp+188h+Privilege]
0x1800d37e0  mov     rcx, rsi
0x1800d37e3  call    cs:__imp_RtlDosPathNameToNtPathName_U_WithStatus
0x1800d37ea  nop     dword ptr [rax+rax+00h]
0x1800d37ef  test    eax, eax
0x1800d37f1  js      loc_1800D3C63
0x1800d37f7  mov     rax, [rsp+188h+String2.Buffer]
0x1800d37ff  mov     [rsp+188h+var_F8], rax
0x1800d3807  mov     r8b, 1; CaseInsensitive
0x1800d380a  lea     rdx, [rsp+188h+String2]; String2
0x1800d3812  lea     rcx, [rsp+188h+String1]; String1
0x1800d381a  call    cs:__imp_RtlEqualUnicodeString
0x1800d3821  nop     dword ptr [rax+rax+00h]
0x1800d3826  test    al, al
0x1800d3828  jnz     loc_1800D3C8B
0x1800d382e  mov     [rsp+188h+OutputBufferLength], 4000h; OutputBufferLength
0x1800d3836  mov     [rsp+188h+OutputBuffer], r14; OutputBuffer
0x1800d383b  mov     [rsp+188h+InputBufferLength], 0; InputBufferLength
0x1800d3843  mov     [rsp+188h+InputBuffer], 0; InputBuffer
0x1800d384c  mov     [rsp+188h+FsControlCode], 900A8h; FsControlCode
0x1800d3854  lea     rax, [rsp+188h+var_E0]
0x1800d385c  mov     [rsp+188h+IoStatusBlock], rax; IoStatusBlock
0x1800d3861  xor     r9d, r9d; ApcContext
0x1800d3864  xor     r8d, r8d; ApcRoutine
0x1800d3867  mov     rdx, rdi; Event
0x1800d386a  mov     rcx, r13; FileHandle
0x1800d386d  call    cs:__imp_NtFsControlFile
0x1800d3874  nop     dword ptr [rax+rax+00h]
0x1800d3879  mov     ebx, eax
0x1800d387b  mov     [rsp+188h+var_128], eax
0x1800d387f  cmp     eax, 103h
0x1800d3884  jz      loc_1800D3C96
0x1800d388a  test    ebx, ebx
0x1800d388c  js      loc_1800D3C53
0x1800d3892  cmp     dword ptr [r14], 0A0000003h
0x1800d3899  jnz     loc_1800D3CD2
0x1800d389f  cmp     dword ptr [r14], 0A000000Ch
0x1800d38a6  jz      loc_1800D3CE5
0x1800d38ac  mov     [rsp+188h+ObjectAttributes.Length], 30h ; '0'
0x1800d38b7  mov     [rsp+188h+ObjectAttributes.RootDirectory], 0
0x1800d38c3  mov     [rsp+188h+ObjectAttributes.Attributes], 40h ; '@'
0x1800d38ce  lea     rax, [rsp+188h+String2]
0x1800d38d6  mov     [rsp+188h+ObjectAttributes.ObjectName], rax
0x1800d38de  xorps   xmm0, xmm0
0x1800d38e1  movdqu  xmmword ptr [rsp+188h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d38ea  mov     rax, [rsp+188h+arg_38]
0x1800d38f2  mov     eax, [rax]
0x1800d38f4  and     eax, 1
0x1800d38f7  mov     edi, r15d
0x1800d38fa  bts     edi, 15h
0x1800d38fe  mov     [rsp+188h+EaLength], 0; EaLength
0x1800d3906  lea     r9, [rsp+188h+var_C0]; IoStatusBlock
0x1800d390e  lea     r8, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x1800d3916  mov     edx, 0C0000000h; DesiredAccess
0x1800d391b  lea     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800d3920  mov     qword ptr [rsp+188h+OutputBufferLength], 0; EaBuffer
0x1800d3929  mov     dword ptr [rsp+188h+OutputBuffer], edi; CreateOptions
0x1800d392d  test    r15b, 1
0x1800d3931  jz      loc_1800D3D22
0x1800d3937  xor     eax, 1
0x1800d393a  add     eax, 2
0x1800d393d  mov     [rsp+188h+InputBufferLength], eax; CreateDisposition
0x1800d3941  mov     dword ptr [rsp+188h+InputBuffer], 3; ShareAccess
0x1800d3949  mov     [rsp+188h+FsControlCode], 0; FileAttributes
0x1800d3951  mov     [rsp+188h+IoStatusBlock], 0; AllocationSize
0x1800d395a  call    cs:__imp_NtCreateFile
0x1800d3961  nop     dword ptr [rax+rax+00h]
0x1800d3966  mov     [rsp+188h+var_128], eax
0x1800d396a  mov     ebx, eax
0x1800d396c  test    eax, eax
0x1800d396e  js      loc_1800D3C4A
0x1800d3974  mov     r12, [rsp+188h+var_C0.Information]
0x1800d397c  mov     [rsp+188h+var_118], r12d
0x1800d3981  cmp     [rsp+188h+String1.Length], 60h ; '`'
0x1800d398a  jz      loc_1800D3B38
0x1800d3990  cmp     [rsp+188h+String1.Length], 62h ; 'b'
0x1800d3999  jz      loc_1800D3D29
0x1800d399f  movzx   eax, word ptr [r14+4]
0x1800d39a4  add     eax, 8
0x1800d39a7  mov     [rsp+188h+OutputBufferLength], 0; OutputBufferLength
0x1800d39af  mov     [rsp+188h+OutputBuffer], 0; OutputBuffer
0x1800d39b8  mov     [rsp+188h+InputBufferLength], eax; InputBufferLength
0x1800d39bc  mov     [rsp+188h+InputBuffer], r14; InputBuffer
0x1800d39c1  mov     [rsp+188h+FsControlCode], 900A4h; FsControlCode
0x1800d39c9  lea     rax, [rsp+188h+var_E0]
0x1800d39d1  mov     [rsp+188h+IoStatusBlock], rax; IoStatusBlock
0x1800d39d6  xor     r9d, r9d; ApcContext
0x1800d39d9  xor     r8d, r8d; ApcRoutine
0x1800d39dc  xor     edx, edx; Event
0x1800d39de  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800d39e3  call    cs:__imp_NtFsControlFile
0x1800d39ea  nop     dword ptr [rax+rax+00h]
0x1800d39ef  mov     ebx, eax
0x1800d39f1  mov     [rsp+188h+var_128], eax
0x1800d39f5  test    eax, eax
0x1800d39f7  js      loc_1800D3D1B
0x1800d39fd  mov     r15d, 4
0x1800d3a03  mov     dword ptr [rsp+188h+IoStatusBlock], r15d; FileInformationClass
0x1800d3a08  lea     r9d, [r15+24h]; Length
0x1800d3a0c  lea     r8, [rsp+188h+FileInformation]; FileInformation
0x1800d3a14  lea     rdx, [rsp+188h+var_E0]; IoStatusBlock
0x1800d3a1c  mov     rcx, r13; FileHandle
0x1800d3a1f  call    cs:__imp_NtQueryInformationFile
0x1800d3a26  nop     dword ptr [rax+rax+00h]
0x1800d3a2b  mov     ebx, eax
0x1800d3a2d  mov     [rsp+188h+var_128], eax
0x1800d3a31  test    eax, eax
0x1800d3a33  js      loc_1800D3D1B
0x1800d3a39  xorps   xmm0, xmm0
0x1800d3a3c  movdqu  [rsp+188h+FileInformation], xmm0
0x1800d3a45  mov     dword ptr [rsp+188h+var_48], 0
0x1800d3a50  mov     dword ptr [rsp+188h+IoStatusBlock], r15d; FileInformationClass
0x1800d3a55  lea     r13d, [r15+24h]
0x1800d3a59  mov     r9d, r13d; Length
0x1800d3a5c  lea     r8, [rsp+188h+FileInformation]; FileInformation
0x1800d3a64  lea     rdx, [rsp+188h+var_E0]; IoStatusBlock
0x1800d3a6c  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800d3a71  call    cs:__imp_NtSetInformationFile
0x1800d3a78  nop     dword ptr [rax+rax+00h]
0x1800d3a7d  mov     ebx, eax
0x1800d3a7f  mov     [rsp+188h+var_128], eax
0x1800d3a83  cmp     eax, 0C0000043h
0x1800d3a88  jz      short loc_1800D3A94
0x1800d3a8a  mov     edi, 1
0x1800d3a8f  jmp     loc_1800D3D78
0x1800d3a94  mov     rcx, [rsp+188h+FileHandle]; hObject
0x1800d3a99  call    CloseHandle
0x1800d3a9e  mov     [rsp+188h+EaLength], 0; EaLength
0x1800d3aa6  mov     qword ptr [rsp+188h+OutputBufferLength], 0; EaBuffer
0x1800d3aaf  mov     dword ptr [rsp+188h+OutputBuffer], edi; CreateOptions
0x1800d3ab3  mov     [rsp+188h+InputBufferLength], 1; CreateDisposition
0x1800d3abb  mov     dword ptr [rsp+188h+InputBuffer], 0; ShareAccess
0x1800d3ac3  mov     [rsp+188h+FsControlCode], 0; FileAttributes
0x1800d3acb  mov     [rsp+188h+IoStatusBlock], 0; AllocationSize
0x1800d3ad4  lea     r9, [rsp+188h+var_C0]; IoStatusBlock
0x1800d3adc  lea     r8, [rsp+188h+ObjectAttributes]; ObjectAttributes
0x1800d3ae4  mov     edx, 100h; DesiredAccess
0x1800d3ae9  lea     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800d3aee  call    cs:__imp_NtCreateFile
0x1800d3af5  nop     dword ptr [rax+rax+00h]
0x1800d3afa  mov     ebx, eax
0x1800d3afc  mov     [rsp+188h+var_128], eax
0x1800d3b00  test    eax, eax
0x1800d3b02  js      short loc_1800D3A8A
0x1800d3b04  mov     dword ptr [rsp+188h+IoStatusBlock], r15d; FileInformationClass
0x1800d3b09  mov     r9d, r13d; Length
0x1800d3b0c  lea     r8, [rsp+188h+FileInformation]; FileInformation
0x1800d3b14  lea     rdx, [rsp+188h+var_E0]; IoStatusBlock
0x1800d3b1c  mov     rcx, [rsp+188h+FileHandle]; FileHandle
0x1800d3b21  call    cs:__imp_NtSetInformationFile
0x1800d3b28  nop     dword ptr [rax+rax+00h]
0x1800d3b2d  mov     ebx, eax
0x1800d3b2f  mov     [rsp+188h+var_128], eax
0x1800d3b33  jmp     loc_1800D3A8A
0x1800d3b38  mov     rax, [rsp+188h+String1.Buffer]
0x1800d3b40  cmp     word ptr [rax], 5Ch ; '\'
0x1800d3b44  jnz     loc_1800D399F
0x1800d3b4a  cmp     word ptr [rax+2], 3Fh ; '?'
0x1800d3b4f  jz      short loc_1800D3B5C
0x1800d3b51  cmp     word ptr [rax+2], 5Ch ; '\'
0x1800d3b56  jnz     loc_1800D399F
0x1800d3b5c  cmp     word ptr [rax+4], 3Fh ; '?'
0x1800d3b61  jnz     loc_1800D399F
0x1800d3b67  cmp     word ptr [rax+6], 5Ch ; '\'
0x1800d3b6c  jnz     loc_1800D399F
0x1800d3b72  cmp     word ptr [rax+8], 56h ; 'V'
0x1800d3b77  jnz     loc_1800D399F
0x1800d3b7d  cmp     word ptr [rax+0Ah], 6Fh ; 'o'
0x1800d3b82  jnz     loc_1800D399F
0x1800d3b88  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x1800d3b8d  jnz     loc_1800D399F
0x1800d3b93  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x1800d3b98  jnz     loc_1800D399F
0x1800d3b9e  cmp     word ptr [rax+10h], 6Dh ; 'm'
0x1800d3ba3  jnz     loc_1800D399F
0x1800d3ba9  cmp     word ptr [rax+12h], 65h ; 'e'
0x1800d3bae  jnz     loc_1800D399F
0x1800d3bb4  cmp     word ptr [rax+14h], 7Bh ; '{'
0x1800d3bb9  jnz     loc_1800D399F
0x1800d3bbf  mov     cx, 2Dh ; '-'
0x1800d3bc3  cmp     [rax+26h], cx
0x1800d3bc7  jnz     loc_1800D399F
0x1800d3bcd  cmp     [rax+30h], cx
0x1800d3bd1  jnz     loc_1800D399F
0x1800d3bd7  cmp     [rax+3Ah], cx
0x1800d3bdb  jnz     loc_1800D399F
0x1800d3be1  cmp     [rax+44h], cx
0x1800d3be5  jnz     loc_1800D399F
0x1800d3beb  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x1800d3bf0  jnz     loc_1800D399F
0x1800d3bf6  call    cs:__imp_RtlGetCurrentTransaction
0x1800d3bfd  nop     dword ptr [rax+rax+00h]
0x1800d3c02  test    rax, rax
0x1800d3c05  jz      loc_1800D3D41
0x1800d3c0b  mov     ecx, 0C00000BBh
0x1800d3c10  jmp     short loc_1800D3C55
0x1800d3c12  cmp     eax, 0C0000017h
0x1800d3c17  jz      short loc_1800D3C33
0x1800d3c19  cmp     eax, 0C000009Ah
0x1800d3c1e  jz      short loc_1800D3C33
0x1800d3c20  mov     ecx, 3; LastError
0x1800d3c25  call    cs:__imp_RtlSetLastWin32Error
0x1800d3c2c  nop     dword ptr [rax+rax+00h]
0x1800d3c31  jmp     short loc_1800D3C3A
0x1800d3c33  mov     ecx, eax
0x1800d3c35  call    BaseSetLastNTError
0x1800d3c3a  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800d3c43  mov     rsi, qword ptr [rsp+188h+Privilege]
0x1800d3c48  jmp     short loc_1800D3C5A
0x1800d3c4a  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800d3c53  mov     ecx, ebx
0x1800d3c55  call    BaseSetLastNTError
0x1800d3c5a  mov     edi, [rsp+188h+var_124]
0x1800d3c5e  jmp     loc_1800D3D78
0x1800d3c63  cmp     eax, 0C0000017h
0x1800d3c68  jz      short loc_1800D3C84
0x1800d3c6a  cmp     eax, 0C000009Ah
0x1800d3c6f  jz      short loc_1800D3C84
0x1800d3c71  mov     ecx, 3; LastError
0x1800d3c76  call    cs:__imp_RtlSetLastWin32Error
0x1800d3c7d  nop     dword ptr [rax+rax+00h]
0x1800d3c82  jmp     short loc_1800D3C8B
0x1800d3c84  mov     ecx, eax
0x1800d3c86  call    BaseSetLastNTError
0x1800d3c8b  mov     [rsp+188h+FileHandle], 0FFFFFFFFFFFFFFFFh
0x1800d3c94  jmp     short loc_1800D3C5A
0x1800d3c96  xor     r8d, r8d; Timeout
0x1800d3c99  mov     dl, 1; Alertable
0x1800d3c9b  mov     rcx, rdi; Handle
0x1800d3c9e  call    cs:__imp_NtWaitForSingleObject
0x1800d3ca5  nop     dword ptr [rax+rax+00h]
0x1800d3caa  mov     ebx, eax
0x1800d3cac  mov     [rsp+188h+var_128], eax
0x1800d3cb0  test    eax, eax
  ... truncated ...
```
