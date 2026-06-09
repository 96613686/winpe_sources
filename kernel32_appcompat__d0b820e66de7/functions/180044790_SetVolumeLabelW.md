# SetVolumeLabelW

- ea: `0x180044790`
- end: `0x180044b38`
- name: `SetVolumeLabelW`
- size: `936`
- prototype: `BOOL __stdcall(LPCWSTR lpRootPathName, LPCWSTR lpVolumeName)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180074ac0`

## callees

- `0x18000ccf0`
- `0x180044790`
- `0x180056eb8`
- `0x180082751`
- `0x1800827c0`

## import_xrefs

- `ntdll!NtOpenFile` at `0x180044936`
- `ntdll!NtOpenFile` at `0x180044a20`
- `ntdll!NtOpenFile` at `0x180044936`
- `ntdll!NtOpenFile` at `0x180044a20`
- `ntdll!NtClose` at `0x18004499e`
- `ntdll!NtClose` at `0x1800449b9`
- `ntdll!NtClose` at `0x180044b02`
- `ntdll!NtClose` at `0x18008331a`
- `ntdll!NtClose` at `0x18004499e`
- `ntdll!NtClose` at `0x1800449b9`
- `ntdll!NtClose` at `0x180044b02`
- `ntdll!NtClose` at `0x18008331a`
- `ntdll!RtlSetLastWin32Error` at `0x18004486f`
- `ntdll!RtlSetLastWin32Error` at `0x18004486f`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18004485a`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18004485a`
- `ntdll!NtSetVolumeInformationFile` at `0x180044adb`
- `ntdll!NtSetVolumeInformationFile` at `0x180044adb`
- `ntdll!RtlInitUnicodeString` at `0x1800447fa`
- `ntdll!RtlInitUnicodeString` at `0x1800447fa`
- `ntdll!RtlFreeHeap` at `0x1800448c8`
- `ntdll!RtlFreeHeap` at `0x18004495a`
- `ntdll!RtlFreeHeap` at `0x18004498d`
- `ntdll!RtlFreeHeap` at `0x180044a40`
- `ntdll!RtlFreeHeap` at `0x180044b25`
- `ntdll!RtlFreeHeap` at `0x18008333e`
- `ntdll!RtlFreeHeap` at `0x1800448c8`
- `ntdll!RtlFreeHeap` at `0x18004495a`
- `ntdll!RtlFreeHeap` at `0x18004498d`
- `ntdll!RtlFreeHeap` at `0x180044a40`
- `ntdll!RtlFreeHeap` at `0x180044b25`
- `ntdll!RtlFreeHeap` at `0x18008333e`
- `ntdll!RtlAllocateHeap` at `0x180044a8c`
- `ntdll!RtlAllocateHeap` at `0x180044a8c`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18004481c`
- `KERNELBASE!GetVolumeNameForVolumeMountPointW` at `0x18004481c`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180044a6e`
- `KERNELBASE!KernelBaseGetGlobalData` at `0x180044a6e`

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
0x180044790  mov     [rsp+arg_10], rbx
0x180044795  push    rsi
0x180044796  push    rdi
0x180044797  push    r14
0x180044799  sub     rsp, 2D0h
0x1800447a0  mov     rax, cs:__security_cookie
0x1800447a7  xor     rax, rsp
0x1800447aa  mov     [rsp+2E8h+var_28], rax
0x1800447b2  mov     rbx, rcx
0x1800447b5  xor     eax, eax
0x1800447b7  xorps   xmm0, xmm0
0x1800447ba  movups  xmmword ptr [rsp+2E8h+ObjectAttributes.Length], xmm0
0x1800447bf  movups  xmmword ptr [rsp+2E8h+ObjectAttributes.ObjectName], xmm0
0x1800447c4  movups  xmmword ptr [rsp+2E8h+ObjectAttributes+1Ch], xmm0
0x1800447cc  xor     r14d, r14d
0x1800447cf  mov     [rsp+2E8h+FileHandle], r14
0x1800447d4  movups  xmmword ptr [rsp+2E8h+NtPathName.Length], xmm0
0x1800447d9  xorps   xmm1, xmm1
0x1800447dc  movups  xmmword ptr [rsp+2E8h+DestinationString.Length], xmm1
0x1800447e1  movups  xmmword ptr [rsp+2E8h+IoStatusBlock], xmm0
0x1800447e9  lea     edi, [rax+5Ch]
0x1800447ec  mov     [rsp+2E8h+var_2B0], edi
0x1800447f0  test    rdx, rdx
0x1800447f3  jz      short loc_180044806
0x1800447f5  lea     rcx, [rsp+2E8h+DestinationString]; DestinationString
0x1800447fa  call    cs:__imp_RtlInitUnicodeString
0x180044801  nop     dword ptr [rax+rax+00h]
0x180044806  test    rbx, rbx
0x180044809  jz      short loc_180044832
0x18004480b  mov     r8d, 104h; cchBufferLength
0x180044811  lea     rdx, [rsp+2E8h+szVolumeName]; lpszVolumeName
0x180044819  mov     rcx, rbx; lpszVolumeMountPoint
0x18004481c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180044823  nop     dword ptr [rax+rax+00h]
0x180044828  mov     ecx, r14d
0x18004482b  test    eax, eax
0x18004482d  setnz   cl
0x180044830  jmp     short loc_180044835
0x180044832  mov     ecx, r14d
0x180044835  test    ecx, ecx
0x180044837  jz      short loc_180044843
0x180044839  lea     rcx, [rsp+2E8h+szVolumeName]
0x180044841  jmp     short loc_18004484F
0x180044843  lea     rcx, [rsp+2E8h+var_2B0]
0x180044848  test    rbx, rbx
0x18004484b  cmovnz  rcx, rbx; DosPathName
0x18004484f  xor     r9d, r9d; DirectoryInfo
0x180044852  xor     r8d, r8d; NtFileNamePart
0x180044855  lea     rdx, [rsp+2E8h+NtPathName]; NtPathName
0x18004485a  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180044861  nop     dword ptr [rax+rax+00h]
0x180044866  test    al, al
0x180044868  jnz     short loc_1800448A2
0x18004486a  mov     ecx, 3; LastError
0x18004486f  call    cs:__imp_RtlSetLastWin32Error
0x180044876  nop     dword ptr [rax+rax+00h]
0x18004487b  xor     eax, eax
0x18004487d  mov     rcx, [rsp+2E8h+var_28]
0x180044885  xor     rcx, rsp; StackCookie
0x180044888  call    __security_check_cookie
0x18004488d  mov     rbx, [rsp+2E8h+arg_10]
0x180044895  add     rsp, 2D0h
0x18004489c  pop     r14
0x18004489e  pop     rdi
0x18004489f  pop     rsi
0x1800448a0  retn
0x1800448a2  mov     rbx, [rsp+2E8h+NtPathName.Buffer]
0x1800448a7  movzx   eax, [rsp+2E8h+NtPathName.Length]
0x1800448ac  shr     rax, 1
0x1800448af  cmp     [rbx+rax*2-2], di
0x1800448b4  jz      short loc_1800448E0
0x1800448b6  mov     rcx, gs:60h
0x1800448bf  mov     r8, rbx; P
0x1800448c2  xor     edx, edx; Flags
0x1800448c4  mov     rcx, [rcx+30h]; HeapHandle
0x1800448c8  call    cs:__imp_RtlFreeHeap
0x1800448cf  nop     dword ptr [rax+rax+00h]
0x1800448d4  mov     ecx, 0C0000033h
0x1800448d9  call    BaseSetLastNTError
0x1800448de  jmp     short loc_18004487B
0x1800448e0  mov     esi, 30h ; '0'
0x1800448e5  mov     [rsp+2E8h+ObjectAttributes.Length], esi
0x1800448e9  mov     [rsp+2E8h+ObjectAttributes.RootDirectory], r14
0x1800448ee  mov     [rsp+2E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800448f9  lea     rax, [rsp+2E8h+NtPathName]
0x1800448fe  mov     [rsp+2E8h+ObjectAttributes.ObjectName], rax
0x180044903  xorps   xmm0, xmm0
0x180044906  movdqu  xmmword ptr [rsp+2E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18004490f  mov     [rsp+2E8h+OpenOptions], 20h ; ' '; OpenOptions
0x180044917  mov     [rsp+2E8h+ShareAccess], 3; ShareAccess
0x18004491f  lea     r9, [rsp+2E8h+IoStatusBlock]; IoStatusBlock
0x180044927  lea     r8, [rsp+2E8h+ObjectAttributes]; ObjectAttributes
0x18004492c  mov     edx, 100002h; DesiredAccess
0x180044931  lea     rcx, [rsp+2E8h+FileHandle]; FileHandle
0x180044936  call    cs:__imp_NtOpenFile
0x18004493d  nop     dword ptr [rax+rax+00h]
0x180044942  mov     edi, eax
0x180044944  test    eax, eax
0x180044946  jns     short loc_18004496D
0x180044948  mov     rcx, gs:60h
0x180044951  mov     r8, rbx; P
0x180044954  xor     edx, edx; Flags
0x180044956  mov     rcx, [rcx+30h]; HeapHandle
0x18004495a  call    cs:__imp_RtlFreeHeap
0x180044961  nop     dword ptr [rax+rax+00h]
0x180044966  mov     ecx, edi
0x180044968  jmp     loc_1800448D9
0x18004496d  mov     rcx, [rsp+2E8h+FileHandle]
0x180044972  call    IsThisARootDirectory
0x180044977  test    eax, eax
0x180044979  jnz     short loc_1800449B4
0x18004497b  mov     rcx, gs:60h
0x180044984  mov     r8, rbx; P
0x180044987  xor     edx, edx; Flags
0x180044989  mov     rcx, [rcx+30h]; HeapHandle
0x18004498d  call    cs:__imp_RtlFreeHeap
0x180044994  nop     dword ptr [rax+rax+00h]
0x180044999  mov     rcx, [rsp+2E8h+FileHandle]; Handle
0x18004499e  call    cs:__imp_NtClose
0x1800449a5  nop     dword ptr [rax+rax+00h]
0x1800449aa  mov     ecx, 90h
0x1800449af  jmp     loc_18004486F
0x1800449b4  mov     rcx, [rsp+2E8h+FileHandle]; Handle
0x1800449b9  call    cs:__imp_NtClose
0x1800449c0  nop     dword ptr [rax+rax+00h]
0x1800449c5  mov     eax, 0FFFEh
0x1800449ca  add     [rsp+2E8h+NtPathName.Length], ax
0x1800449cf  mov     [rsp+2E8h+ObjectAttributes.Length], esi
0x1800449d3  mov     [rsp+2E8h+ObjectAttributes.RootDirectory], r14
0x1800449d8  mov     [rsp+2E8h+ObjectAttributes.Attributes], 40h ; '@'
0x1800449e3  lea     rax, [rsp+2E8h+NtPathName]
0x1800449e8  mov     [rsp+2E8h+ObjectAttributes.ObjectName], rax
0x1800449ed  xorps   xmm0, xmm0
0x1800449f0  movdqu  xmmword ptr [rsp+2E8h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800449f9  mov     [rsp+2E8h+OpenOptions], 20h ; ' '; OpenOptions
0x180044a01  mov     [rsp+2E8h+ShareAccess], 3; ShareAccess
0x180044a09  lea     r9, [rsp+2E8h+IoStatusBlock]; IoStatusBlock
0x180044a11  lea     r8, [rsp+2E8h+ObjectAttributes]; ObjectAttributes
0x180044a16  mov     edx, 100002h; DesiredAccess
0x180044a1b  lea     rcx, [rsp+2E8h+FileHandle]; FileHandle
0x180044a20  call    cs:__imp_NtOpenFile
0x180044a27  nop     dword ptr [rax+rax+00h]
0x180044a2c  mov     edi, eax
0x180044a2e  mov     rcx, gs:60h
0x180044a37  mov     r8, rbx; P
0x180044a3a  xor     edx, edx; Flags
0x180044a3c  mov     rcx, [rcx+30h]; HeapHandle
0x180044a40  call    cs:__imp_RtlFreeHeap
0x180044a47  nop     dword ptr [rax+rax+00h]
0x180044a4c  test    edi, edi
0x180044a4e  js      loc_180044966
0x180044a54  mov     [rsp+2E8h+var_298], r14
0x180044a59  mov     esi, 1
0x180044a5e  movzx   eax, [rsp+2E8h+DestinationString.Length]
0x180044a63  test    ax, ax
0x180044a66  lea     edi, [rax+6]
0x180044a69  jnz     short loc_180044A6E
0x180044a6b  lea     edi, [rsi+7]
0x180044a6e  call    cs:__imp_KernelBaseGetGlobalData
0x180044a75  nop     dword ptr [rax+rax+00h]
0x180044a7a  mov     r8d, edi; Size
0x180044a7d  mov     rcx, gs:60h
0x180044a86  mov     edx, [rax]; Flags
0x180044a88  mov     rcx, [rcx+30h]; HeapHandle
0x180044a8c  call    cs:__imp_RtlAllocateHeap
0x180044a93  nop     dword ptr [rax+rax+00h]
0x180044a98  mov     rbx, rax
0x180044a9b  mov     [rsp+2E8h+var_298], rax
0x180044aa0  test    rax, rax
0x180044aa3  jz      short loc_180044AEF
0x180044aa5  movzx   r8d, [rsp+2E8h+DestinationString.Length]; Size
0x180044aab  lea     rcx, [rax+4]; void *
0x180044aaf  mov     rdx, [rsp+2E8h+DestinationString.Buffer]; Src
0x180044ab4  call    memcpy_0
0x180044ab9  movzx   ecx, [rsp+2E8h+DestinationString.Length]
0x180044abe  mov     [rbx], ecx
0x180044ac0  mov     [rsp+2E8h+ShareAccess], 2; FsInformationClass
0x180044ac8  mov     r9d, edi; Length
0x180044acb  mov     r8, rbx; FsInformation
0x180044ace  lea     rdx, [rsp+2E8h+IoStatusBlock]; IoStatusBlock
0x180044ad6  mov     rcx, [rsp+2E8h+FileHandle]; FileHandle
0x180044adb  call    cs:__imp_NtSetVolumeInformationFile
0x180044ae2  nop     dword ptr [rax+rax+00h]
0x180044ae7  test    eax, eax
0x180044ae9  jns     short loc_180044AFD
0x180044aeb  mov     ecx, eax
0x180044aed  jmp     short loc_180044AF4
0x180044aef  mov     ecx, 0C0000017h
0x180044af4  mov     esi, r14d
0x180044af7  call    BaseSetLastNTError
0x180044afc  nop
0x180044afd  mov     rcx, [rsp+2E8h+FileHandle]; Handle
0x180044b02  call    cs:__imp_NtClose
0x180044b09  nop     dword ptr [rax+rax+00h]
0x180044b0e  test    rbx, rbx
0x180044b11  jz      short loc_180044B31
0x180044b13  mov     rcx, gs:60h
0x180044b1c  mov     r8, rbx; P
0x180044b1f  xor     edx, edx; Flags
0x180044b21  mov     rcx, [rcx+30h]; HeapHandle
0x180044b25  call    cs:__imp_RtlFreeHeap
0x180044b2c  nop     dword ptr [rax+rax+00h]
0x180044b31  mov     eax, esi
0x180044b33  jmp     loc_18004487D
0x18008330d  push    rbp
0x18008330f  sub     rsp, 30h
0x180083313  mov     rbp, rdx
0x180083316  mov     rcx, [rbp+30h]; Handle
0x18008331a  call    cs:__imp_NtClose
0x180083321  nop     dword ptr [rax+rax+00h]
0x180083326  mov     r8, [rbp+50h]; P
0x18008332a  test    r8, r8
0x18008332d  jz      short loc_18008334B
0x18008332f  mov     rcx, gs:60h
0x180083338  xor     edx, edx; Flags
0x18008333a  mov     rcx, [rcx+30h]; HeapHandle
0x18008333e  call    cs:__imp_RtlFreeHeap
0x180083345  nop     dword ptr [rax+rax+00h]
0x18008334a  nop
0x18008334b  add     rsp, 30h
0x18008334f  pop     rbp
0x180083350  retn
```
