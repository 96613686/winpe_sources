# SetVolumeLabelW

- ea: `0x180040b10`
- end: `0x180040e51`
- name: `SetVolumeLabelW`
- size: `833`
- prototype: `BOOL __stdcall(LPCWSTR lpRootPathName, LPCWSTR lpVolumeName)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006d2f0`

## callees

- `0x18000f920`
- `0x180040b10`
- `0x180051ca0`
- `0x18007a7d1`
- `0x18007a840`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180040c97`
- `ntdll!NtOpenFile` at `0x180040d63`
- `ntdll!NtOpenFile` at `0x180040c97`
- `ntdll!NtOpenFile` at `0x180040d63`
- `ntdll!NtClose` at `0x180040ced`
- `ntdll!NtClose` at `0x180040d02`
- `ntdll!NtClose` at `0x180040e27`
- `ntdll!NtClose` at `0x18007b28d`
- `ntdll!NtClose` at `0x180040ced`
- `ntdll!NtClose` at `0x180040d02`
- `ntdll!NtClose` at `0x180040e27`
- `ntdll!NtClose` at `0x18007b28d`
- `ntdll!RtlSetLastWin32Error` at `0x180040bdd`
- `ntdll!RtlSetLastWin32Error` at `0x180040bdd`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180040bce`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180040bce`
- `ntdll!NtSetVolumeInformationFile` at `0x180040e06`
- `ntdll!NtSetVolumeInformationFile` at `0x180040e06`
- `ntdll!RtlInitUnicodeString` at `0x180040b7a`
- `ntdll!RtlInitUnicodeString` at `0x180040b7a`
- `ntdll!RtlFreeHeap` at `0x180040c2f`
- `ntdll!RtlFreeHeap` at `0x180040cb5`
- `ntdll!RtlFreeHeap` at `0x180040ce2`
- `ntdll!RtlFreeHeap` at `0x180040d7d`
- `ntdll!RtlFreeHeap` at `0x180040e44`
- `ntdll!RtlFreeHeap` at `0x18007b2ab`
- `ntdll!RtlFreeHeap` at `0x180040c2f`
- `ntdll!RtlFreeHeap` at `0x180040cb5`
- `ntdll!RtlFreeHeap` at `0x180040ce2`
- `ntdll!RtlFreeHeap` at `0x180040d7d`
- `ntdll!RtlFreeHeap` at `0x180040e44`
- `ntdll!RtlFreeHeap` at `0x18007b2ab`
- `ntdll!RtlAllocateHeap` at `0x180040dbd`
- `ntdll!RtlAllocateHeap` at `0x180040dbd`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x180040b96`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x180040b96`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180040da5`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180040da5`

## pseudocode

```c
BOOL __stdcall SetVolumeLabelW(LPCWSTR lpRootPathName, LPCWSTR lpVolumeName)
{
  _BOOL8 VolumeNameForVolumeMountPointW; // rcx
  const WCHAR *v4; // rcx
  ULONG v5; // ecx
  PWSTR Buffer; // rbx
  __int64 v8; // rcx
  NTSTATUS v9; // edi
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r9
  BOOL v14; // esi
  ULONG v15; // edi
  ULONG *GlobalData; // rax
  _DWORD *Heap; // rax
  _DWORD *v18; // rbx
  NTSTATUS v19; // eax
  __int64 v20; // rcx
  void *FileHandle; // [rsp+30h] [rbp-2B8h] BYREF
  int v22; // [rsp+38h] [rbp-2B0h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-2A8h] BYREF
  _DWORD *v24; // [rsp+50h] [rbp-298h]
  struct _UNICODE_STRING DestinationString; // [rsp+58h] [rbp-290h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+68h] [rbp-280h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+98h] [rbp-250h] BYREF
  WCHAR szVolumeName[264]; // [rsp+B0h] [rbp-238h] BYREF

  memset(&ObjectAttributes, 0, 44);
  FileHandle = 0;
  NtPathName = 0;
  DestinationString = 0;
  IoStatusBlock = 0;
  v22 = 92;
  if ( lpVolumeName )
    RtlInitUnicodeString(&DestinationString, lpVolumeName);
  if ( lpRootPathName )
    VolumeNameForVolumeMountPointW = GetVolumeNameForVolumeMountPointW(lpRootPathName, szVolumeName, 0x104u);
  else
    LODWORD(VolumeNameForVolumeMountPointW) = 0;
  if ( VolumeNameForVolumeMountPointW )
  {
    v4 = szVolumeName;
  }
  else
  {
    v4 = (const WCHAR *)&v22;
    if ( lpRootPathName )
      v4 = lpRootPathName;
  }
  if ( !RtlDosPathNameToNtPathName_U(v4, &NtPathName, 0, 0) )
  {
    v5 = 3;
LABEL_12:
    RtlSetLastWin32Error(v5);
    return 0;
  }
  Buffer = NtPathName.Buffer;
  if ( NtPathName.Buffer[((unsigned __int64)NtPathName.Length >> 1) - 1] != 92 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
    v8 = 3221225523LL;
LABEL_16:
    BaseSetLastNTError(v8);
    return 0;
  }
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  if ( v9 < 0 )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
LABEL_19:
    v8 = (unsigned int)v9;
    goto LABEL_16;
  }
  if ( !(unsigned int)IsThisARootDirectory(FileHandle) )
  {
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    NtClose(FileHandle);
    v5 = 144;
    goto LABEL_12;
  }
  NtClose(FileHandle);
  NtPathName.Length -= 2;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &NtPathName;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v9 = NtOpenFile(&FileHandle, 0x100002u, &ObjectAttributes, &IoStatusBlock, 3u, 0x20u);
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  if ( v9 < 0 )
    goto LABEL_19;
  v24 = 0;
  v14 = 1;
  v15 = DestinationString.Length + 6;
  if ( !DestinationString.Length )
    v15 = 8;
  GlobalData = (ULONG *)KernelBaseGetGlobalData(v11, v10, v12, v13);
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, *GlobalData, v15);
  v18 = Heap;
  v24 = Heap;
  if ( !Heap )
  {
    v20 = 3221225495LL;
    goto LABEL_29;
  }
  memcpy_0(Heap + 1, DestinationString.Buffer, DestinationString.Length);
  *v18 = DestinationString.Length;
  v19 = NtSetVolumeInformationFile(FileHandle, &IoStatusBlock, v18, v15, FileFsLabelInformation);
  if ( v19 < 0 )
  {
    v20 = (unsigned int)v19;
LABEL_29:
    v14 = 0;
    BaseSetLastNTError(v20);
  }
  NtClose(FileHandle);
  if ( v18 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v18);
  return v14;
}

```

## disassembly

```asm
0x180040b10  mov     [rsp+arg_10], rbx
0x180040b15  push    rsi
0x180040b16  push    rdi
0x180040b17  push    r14
0x180040b19  sub     rsp, 2D0h
0x180040b20  mov     rax, cs:__security_cookie
0x180040b27  xor     rax, rsp
0x180040b2a  mov     [rsp+2E8h+var_28], rax
0x180040b32  mov     rbx, rcx
0x180040b35  xor     eax, eax
0x180040b37  xorps   xmm0, xmm0
0x180040b3a  movups  xmmword ptr [rsp+2E8h+ObjectAttributes.Length], xmm0
0x180040b3f  movups  xmmword ptr [rsp+2E8h+ObjectAttributes.ObjectName], xmm0
0x180040b44  movups  xmmword ptr [rsp+2E8h+ObjectAttributes+1Ch], xmm0
0x180040b4c  xor     r14d, r14d
0x180040b4f  mov     [rsp+2E8h+FileHandle], r14
0x180040b54  movups  xmmword ptr [rsp+2E8h+NtPathName.Length], xmm0
0x180040b59  xorps   xmm1, xmm1
0x180040b5c  movups  xmmword ptr [rsp+2E8h+DestinationString.Length], xmm1
0x180040b61  movups  xmmword ptr [rsp+2E8h+IoStatusBlock], xmm0
0x180040b69  lea     edi, [rax+5Ch]
0x180040b6c  mov     [rsp+2E8h+var_2B0], edi
0x180040b70  test    rdx, rdx
0x180040b73  jz      short loc_180040B80
0x180040b75  lea     rcx, [rsp+2E8h+DestinationString]; DestinationString
0x180040b7a  call    cs:__imp_RtlInitUnicodeString
0x180040b80  test    rbx, rbx
0x180040b83  jz      short loc_180040BA6
0x180040b85  mov     r8d, 104h; cchBufferLength
0x180040b8b  lea     rdx, [rsp+2E8h+szVolumeName]; lpszVolumeName
0x180040b93  mov     rcx, rbx; lpszVolumeMountPoint
0x180040b96  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180040b9c  mov     ecx, r14d
0x180040b9f  test    eax, eax
0x180040ba1  setnz   cl
0x180040ba4  jmp     short loc_180040BA9
0x180040ba6  mov     ecx, r14d
0x180040ba9  test    ecx, ecx
0x180040bab  jz      short loc_180040BB7
0x180040bad  lea     rcx, [rsp+2E8h+szVolumeName]
0x180040bb5  jmp     short loc_180040BC3
0x180040bb7  lea     rcx, [rsp+2E8h+var_2B0]
0x180040bbc  test    rbx, rbx
0x180040bbf  cmovnz  rcx, rbx; DosPathName
0x180040bc3  xor     r9d, r9d; DirectoryInfo
0x180040bc6  xor     r8d, r8d; NtFileNamePart
0x180040bc9  lea     rdx, [rsp+2E8h+NtPathName]; NtPathName
0x180040bce  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180040bd4  test    al, al
0x180040bd6  jnz     short loc_180040C09
0x180040bd8  mov     ecx, 3; LastError
0x180040bdd  call    cs:__imp_RtlSetLastWin32Error
0x180040be3  xor     eax, eax
0x180040be5  mov     rcx, [rsp+2E8h+var_28]
0x180040bed  xor     rcx, rsp; StackCookie
0x180040bf0  call    __security_check_cookie
0x180040bf5  mov     rbx, [rsp+2E8h+arg_10]
0x180040bfd  add     rsp, 2D0h
0x180040c04  pop     r14
0x180040c06  pop     rdi
0x180040c07  pop     rsi
0x180040c08  retn
0x180040c09  mov     rbx, [rsp+2E8h+NtPathName.Buffer]
0x180040c0e  movzx   eax, [rsp+2E8h+NtPathName.Length]
0x180040c13  shr     rax, 1
0x180040c16  cmp     [rbx+rax*2-2], di
0x180040c1b  jz      short loc_180040C41
0x180040c1d  mov     rcx, gs:60h
0x180040c26  mov     r8, rbx; P
0x180040c29  xor     edx, edx; Flags
0x180040c2b  mov     rcx, [rcx+30h]; HeapHandle
0x180040c2f  call    cs:__imp_RtlFreeHeap
0x180040c35  mov     ecx, 0C0000033h
0x180040c3a  call    BaseSetLastNTError
0x180040c3f  jmp     short loc_180040BE3
0x180040c41  mov     esi, 30h ; '0'
0x180040c46  mov     [rsp+2E8h+ObjectAttributes.Length], esi
0x180040c4a  mov     [rsp+2E8h+ObjectAttributes.RootDirectory], r14
0x180040c4f  mov     [rsp+2E8h+ObjectAttributes.Attributes], 40h ; '@'
0x180040c5a  lea     rax, [rsp+2E8h+NtPathName]
0x180040c5f  mov     [rsp+2E8h+ObjectAttributes.ObjectName], rax
0x180040c64  xorps   xmm0, xmm0
0x180040c67  movdqu  xmmword ptr [rsp+2E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180040c70  mov     [rsp+2E8h+OpenOptions], 20h ; ' '; OpenOptions
0x180040c78  mov     [rsp+2E8h+ShareAccess], 3; ShareAccess
0x180040c80  lea     r9, [rsp+2E8h+IoStatusBlock]; IoStatusBlock
0x180040c88  lea     r8, [rsp+2E8h+ObjectAttributes]; ObjectAttributes
0x180040c8d  mov     edx, 100002h; DesiredAccess
0x180040c92  lea     rcx, [rsp+2E8h+FileHandle]; FileHandle
0x180040c97  call    cs:__imp_NtOpenFile
0x180040c9d  mov     edi, eax
0x180040c9f  test    eax, eax
0x180040ca1  jns     short loc_180040CC2
0x180040ca3  mov     rcx, gs:60h
0x180040cac  mov     r8, rbx; P
0x180040caf  xor     edx, edx; Flags
0x180040cb1  mov     rcx, [rcx+30h]; HeapHandle
0x180040cb5  call    cs:__imp_RtlFreeHeap
0x180040cbb  mov     ecx, edi
0x180040cbd  jmp     loc_180040C3A
0x180040cc2  mov     rcx, [rsp+2E8h+FileHandle]
0x180040cc7  call    IsThisARootDirectory
0x180040ccc  test    eax, eax
0x180040cce  jnz     short loc_180040CFD
0x180040cd0  mov     rcx, gs:60h
0x180040cd9  mov     r8, rbx; P
0x180040cdc  xor     edx, edx; Flags
0x180040cde  mov     rcx, [rcx+30h]; HeapHandle
0x180040ce2  call    cs:__imp_RtlFreeHeap
0x180040ce8  mov     rcx, [rsp+2E8h+FileHandle]; Handle
0x180040ced  call    cs:__imp_NtClose
0x180040cf3  mov     ecx, 90h
0x180040cf8  jmp     loc_180040BDD
0x180040cfd  mov     rcx, [rsp+2E8h+FileHandle]; Handle
0x180040d02  call    cs:__imp_NtClose
0x180040d08  mov     eax, 0FFFEh
0x180040d0d  add     [rsp+2E8h+NtPathName.Length], ax
0x180040d12  mov     [rsp+2E8h+ObjectAttributes.Length], esi
0x180040d16  mov     [rsp+2E8h+ObjectAttributes.RootDirectory], r14
0x180040d1b  mov     [rsp+2E8h+ObjectAttributes.Attributes], 40h ; '@'
0x180040d26  lea     rax, [rsp+2E8h+NtPathName]
0x180040d2b  mov     [rsp+2E8h+ObjectAttributes.ObjectName], rax
0x180040d30  xorps   xmm0, xmm0
0x180040d33  movdqu  xmmword ptr [rsp+2E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x180040d3c  mov     [rsp+2E8h+OpenOptions], 20h ; ' '; OpenOptions
0x180040d44  mov     [rsp+2E8h+ShareAccess], 3; ShareAccess
0x180040d4c  lea     r9, [rsp+2E8h+IoStatusBlock]; IoStatusBlock
0x180040d54  lea     r8, [rsp+2E8h+ObjectAttributes]; ObjectAttributes
0x180040d59  mov     edx, 100002h; DesiredAccess
0x180040d5e  lea     rcx, [rsp+2E8h+FileHandle]; FileHandle
0x180040d63  call    cs:__imp_NtOpenFile
0x180040d69  mov     edi, eax
0x180040d6b  mov     rcx, gs:60h
0x180040d74  mov     r8, rbx; P
0x180040d77  xor     edx, edx; Flags
0x180040d79  mov     rcx, [rcx+30h]; HeapHandle
0x180040d7d  call    cs:__imp_RtlFreeHeap
0x180040d83  test    edi, edi
0x180040d85  js      loc_180040CBB
0x180040d8b  mov     [rsp+2E8h+var_298], r14
0x180040d90  mov     esi, 1
0x180040d95  movzx   eax, [rsp+2E8h+DestinationString.Length]
0x180040d9a  test    ax, ax
0x180040d9d  lea     edi, [rax+6]
0x180040da0  jnz     short loc_180040DA5
0x180040da2  lea     edi, [rsi+7]
0x180040da5  call    cs:__imp_KernelBaseGetGlobalData
0x180040dab  mov     r8d, edi; Size
0x180040dae  mov     rcx, gs:60h
0x180040db7  mov     edx, [rax]; Flags
0x180040db9  mov     rcx, [rcx+30h]; HeapHandle
0x180040dbd  call    cs:__imp_RtlAllocateHeap
0x180040dc3  mov     rbx, rax
0x180040dc6  mov     [rsp+2E8h+var_298], rax
0x180040dcb  test    rax, rax
0x180040dce  jz      short loc_180040E14
0x180040dd0  movzx   r8d, [rsp+2E8h+DestinationString.Length]; Size
0x180040dd6  lea     rcx, [rax+4]; void *
0x180040dda  mov     rdx, [rsp+2E8h+DestinationString.Buffer]; Src
0x180040ddf  call    memcpy_0
0x180040de4  movzx   ecx, [rsp+2E8h+DestinationString.Length]
0x180040de9  mov     [rbx], ecx
0x180040deb  mov     [rsp+2E8h+ShareAccess], 2; FsInformationClass
0x180040df3  mov     r9d, edi; Length
0x180040df6  mov     r8, rbx; FsInformation
0x180040df9  lea     rdx, [rsp+2E8h+IoStatusBlock]; IoStatusBlock
0x180040e01  mov     rcx, [rsp+2E8h+FileHandle]; FileHandle
0x180040e06  call    cs:__imp_NtSetVolumeInformationFile
0x180040e0c  test    eax, eax
0x180040e0e  jns     short loc_180040E22
0x180040e10  mov     ecx, eax
0x180040e12  jmp     short loc_180040E19
0x180040e14  mov     ecx, 0C0000017h
0x180040e19  mov     esi, r14d
0x180040e1c  call    BaseSetLastNTError
0x180040e21  nop
0x180040e22  mov     rcx, [rsp+2E8h+FileHandle]; Handle
0x180040e27  call    cs:__imp_NtClose
0x180040e2d  test    rbx, rbx
0x180040e30  jz      short loc_180040E4A
0x180040e32  mov     rcx, gs:60h
0x180040e3b  mov     r8, rbx; P
0x180040e3e  xor     edx, edx; Flags
0x180040e40  mov     rcx, [rcx+30h]; HeapHandle
0x180040e44  call    cs:__imp_RtlFreeHeap
0x180040e4a  mov     eax, esi
0x180040e4c  jmp     loc_180040BE5
0x18007b280  push    rbp
0x18007b282  sub     rsp, 30h
0x18007b286  mov     rbp, rdx
0x18007b289  mov     rcx, [rbp+30h]; Handle
0x18007b28d  call    cs:__imp_NtClose
0x18007b293  mov     r8, [rbp+50h]; P
0x18007b297  test    r8, r8
0x18007b29a  jz      short loc_18007B2B2
0x18007b29c  mov     rcx, gs:60h
0x18007b2a5  xor     edx, edx; Flags
0x18007b2a7  mov     rcx, [rcx+30h]; HeapHandle
0x18007b2ab  call    cs:__imp_RtlFreeHeap
0x18007b2b1  nop
0x18007b2b2  add     rsp, 30h
0x18007b2b6  pop     rbp
0x18007b2b7  retn
```
