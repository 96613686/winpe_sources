# GetDiskFreeSpaceW

- ea: `0x1800ff080`
- end: `0x1800ff2ef`
- name: `GetDiskFreeSpaceW`
- size: `623`
- prototype: `BOOL __stdcall(LPCWSTR lpRootPathName, LPDWORD lpSectorsPerCluster, LPDWORD lpBytesPerSector, LPDWORD lpNumberOfFreeClusters, LPDWORD lpTotalNumberOfClusters)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800feff0`

## callees

- `0x18004b9d0`
- `0x1800ff080`
- `0x180194f10`

## import_xrefs

- `ntdll!NtOpenFile` at `0x1800ff156`
- `ntdll!NtOpenFile` at `0x1800ff156`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ff0f7`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800ff0f7`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800ff1a2`
- `ntdll!NtQueryVolumeInformationFile` at `0x1800ff1a2`
- `ntdll!RtlSetLastWin32Error` at `0x1800ff2cd`
- `ntdll!RtlSetLastWin32Error` at `0x1800ff2cd`
- `ntdll!NtClose` at `0x1800ff1b4`
- `ntdll!NtClose` at `0x1800ff1b4`
- `ntdll!RtlFreeHeap` at `0x1800ff17c`
- `ntdll!RtlFreeHeap` at `0x1800ff2aa`
- `ntdll!RtlFreeHeap` at `0x1800ff17c`
- `ntdll!RtlFreeHeap` at `0x1800ff2aa`

## pseudocode

```c
BOOL __stdcall GetDiskFreeSpaceW(
        LPCWSTR lpRootPathName,
        LPDWORD lpSectorsPerCluster,
        LPDWORD lpBytesPerSector,
        LPDWORD lpNumberOfFreeClusters,
        LPDWORD lpTotalNumberOfClusters)
{
  const WCHAR *v6; // rcx
  PWSTR Buffer; // rdi
  NTSTATUS v11; // eax
  NTSTATUS v12; // edi
  DWORD v13; // r10d
  DWORD v14; // edi
  unsigned __int64 v15; // r9
  ULONGLONG v16; // r11
  unsigned __int64 v17; // r8
  DWORD v18; // eax
  DWORD v19; // eax
  int v21; // [rsp+30h] [rbp-61h] BYREF
  HANDLE FileHandle; // [rsp+38h] [rbp-59h] BYREF
  struct _UNICODE_STRING NtPathName; // [rsp+40h] [rbp-51h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-41h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-11h] BYREF
  __int128 FsInformation; // [rsp+90h] [rbp-1h] BYREF
  __int64 v27; // [rsp+A0h] [rbp+Fh]

  v21 = 92;
  v6 = (const WCHAR *)&v21;
  FileHandle = 0;
  v27 = 0;
  if ( lpRootPathName )
    v6 = lpRootPathName;
  memset(&ObjectAttributes, 0, 44);
  NtPathName = 0;
  IoStatusBlock = 0;
  FsInformation = 0;
  if ( !RtlDosPathNameToNtPathName_U(v6, &NtPathName, 0, 0) )
  {
    RtlSetLastWin32Error(3u);
    return 0;
  }
  Buffer = NtPathName.Buffer;
  ObjectAttributes.ObjectName = &NtPathName;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenFile(&FileHandle, 0x100000u, &ObjectAttributes, &IoStatusBlock, 3u, 0x800021u);
  if ( v11 < 0 )
  {
    BaseSetLastNTError((unsigned int)v11);
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
    if ( lpBytesPerSector )
      *lpBytesPerSector = 0;
    return 0;
  }
  RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Buffer);
  v12 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, &FsInformation, 0x18u, FileFsSizeInformation);
  NtClose(FileHandle);
  if ( v12 < 0 )
  {
    BaseSetLastNTError((unsigned int)v12);
    return 0;
  }
  v13 = FsInformation;
  v14 = DWORD2(FsInformation);
  v15 = (unsigned int)v27;
  v16 = NtCurrentPeb()->AppCompatFlags.QuadPart & 8;
  if ( DWORD1(FsInformation) )
    v13 = -1;
  if ( HIDWORD(FsInformation) )
    v14 = -1;
  if ( lpSectorsPerCluster )
    *lpSectorsPerCluster = v27;
  v17 = HIDWORD(v27);
  if ( lpBytesPerSector )
    *lpBytesPerSector = HIDWORD(v27);
  if ( lpNumberOfFreeClusters )
  {
    if ( v16 && v15 <= 0xFFFFFFFFFFFFFFFFuLL / v17 && (v18 = 0x7FFFFFFFu / ((int)v15 * (int)v17), v18 < v14) )
      *lpNumberOfFreeClusters = v18;
    else
      *lpNumberOfFreeClusters = v14;
  }
  if ( lpTotalNumberOfClusters )
  {
    if ( v16 && v15 <= 0xFFFFFFFFFFFFFFFFuLL / v17 && (v19 = 0x7FFFFFFFu / ((int)v15 * (int)v17), v19 < v13) )
      *lpTotalNumberOfClusters = v19;
    else
      *lpTotalNumberOfClusters = v13;
  }
  return 1;
}

```

## disassembly

```asm
0x1800ff080  push    rbp
0x1800ff082  push    rbx
0x1800ff083  push    rsi
0x1800ff084  push    rdi
0x1800ff085  push    r14
0x1800ff087  push    r15
0x1800ff089  lea     rbp, [rsp-27h]
0x1800ff08e  sub     rsp, 0B8h
0x1800ff095  mov     rax, cs:__security_cookie
0x1800ff09c  xor     rax, rsp
0x1800ff09f  mov     [rbp+4Fh+var_38], rax
0x1800ff0a3  mov     rsi, [rbp+4Fh+lpTotalNumberOfClusters]
0x1800ff0a7  xorps   xmm0, xmm0
0x1800ff0aa  mov     r10, rcx
0x1800ff0ad  mov     [rbp+4Fh+var_B0], 5Ch ; '\'
0x1800ff0b4  xor     eax, eax
0x1800ff0b6  lea     rcx, [rbp+4Fh+var_B0]
0x1800ff0ba  test    r10, r10
0x1800ff0bd  mov     [rbp+4Fh+FileHandle], rax
0x1800ff0c1  mov     r14, r9
0x1800ff0c4  mov     [rbp+4Fh+var_40], rax
0x1800ff0c8  cmovnz  rcx, r10; DosPathName
0x1800ff0cc  mov     rbx, r8
0x1800ff0cf  mov     r15, rdx
0x1800ff0d2  xorps   xmm1, xmm1
0x1800ff0d5  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800ff0d9  xor     r9d, r9d; DirectoryInfo
0x1800ff0dc  lea     rdx, [rbp+4Fh+NtPathName]; NtPathName
0x1800ff0e0  xor     r8d, r8d; NtFileNamePart
0x1800ff0e3  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800ff0e7  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800ff0eb  movups  xmmword ptr [rbp+4Fh+NtPathName.Length], xmm0
0x1800ff0ef  movups  xmmword ptr [rbp+4Fh+IoStatusBlock], xmm1
0x1800ff0f3  movups  [rbp+4Fh+FsInformation], xmm0
0x1800ff0f7  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800ff0fe  nop     dword ptr [rax+rax+00h]
0x1800ff103  test    al, al
0x1800ff105  jz      loc_1800FF2C8
0x1800ff10b  mov     rdi, [rbp+4Fh+NtPathName.Buffer]
0x1800ff10f  lea     rax, [rbp+4Fh+NtPathName]
0x1800ff113  xorps   xmm0, xmm0
0x1800ff116  mov     [rsp+0E0h+OpenOptions], 800021h; OpenOptions
0x1800ff11e  lea     r9, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800ff122  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rax
0x1800ff126  lea     r8, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800ff12a  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800ff131  mov     edx, 100000h; DesiredAccess
0x1800ff136  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], 0
0x1800ff13e  lea     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800ff142  mov     [rbp+4Fh+ObjectAttributes.Attributes], 40h ; '@'
0x1800ff149  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800ff14e  mov     [rsp+0E0h+ShareAccess], 3; ShareAccess
0x1800ff156  call    cs:__imp_NtOpenFile
0x1800ff15d  nop     dword ptr [rax+rax+00h]
0x1800ff162  test    eax, eax
0x1800ff164  js      loc_1800FF291
0x1800ff16a  mov     rcx, gs:60h
0x1800ff173  mov     r8, rdi; P
0x1800ff176  xor     edx, edx; Flags
0x1800ff178  mov     rcx, [rcx+30h]; HeapHandle
0x1800ff17c  call    cs:__imp_RtlFreeHeap
0x1800ff183  nop     dword ptr [rax+rax+00h]
0x1800ff188  mov     rcx, [rbp+4Fh+FileHandle]; FileHandle
0x1800ff18c  lea     r8, [rbp+4Fh+FsInformation]; FsInformation
0x1800ff190  mov     r9d, 18h; Length
0x1800ff196  mov     [rsp+0E0h+ShareAccess], 3; FsInformationClass
0x1800ff19e  lea     rdx, [rbp+4Fh+IoStatusBlock]; IoStatusBlock
0x1800ff1a2  call    cs:__imp_NtQueryVolumeInformationFile
0x1800ff1a9  nop     dword ptr [rax+rax+00h]
0x1800ff1ae  mov     rcx, [rbp+4Fh+FileHandle]; Handle
0x1800ff1b2  mov     edi, eax
0x1800ff1b4  call    cs:__imp_NtClose
0x1800ff1bb  nop     dword ptr [rax+rax+00h]
0x1800ff1c0  test    edi, edi
0x1800ff1c2  js      loc_1800FF2BF
0x1800ff1c8  mov     rax, gs:60h
0x1800ff1d1  mov     r10d, dword ptr [rbp+4Fh+FsInformation]
0x1800ff1d5  mov     edi, dword ptr [rbp+4Fh+FsInformation+8]
0x1800ff1d8  mov     r9d, dword ptr [rbp+4Fh+var_40]
0x1800ff1dc  mov     r11, [rax+2C8h]
0x1800ff1e3  or      eax, 0FFFFFFFFh
0x1800ff1e6  and     r11d, 8
0x1800ff1ea  cmp     dword ptr [rbp+4Fh+FsInformation+4], 0
0x1800ff1ee  cmovnz  r10d, eax
0x1800ff1f2  cmp     dword ptr [rbp+4Fh+FsInformation+0Ch], 0
0x1800ff1f6  cmovnz  edi, eax
0x1800ff1f9  test    r15, r15
0x1800ff1fc  jz      short loc_1800FF201
0x1800ff1fe  mov     [r15], r9d
0x1800ff201  mov     r8d, dword ptr [rbp+4Fh+var_40+4]
0x1800ff205  test    rbx, rbx
0x1800ff208  jz      short loc_1800FF20D
0x1800ff20a  mov     [rbx], r8d
0x1800ff20d  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800ff211  mov     ebx, 7FFFFFFFh
0x1800ff216  test    r14, r14
0x1800ff219  jz      short loc_1800FF245
0x1800ff21b  test    r11, r11
0x1800ff21e  jz      short loc_1800FF242
0x1800ff220  xor     edx, edx
0x1800ff222  mov     rax, r15
0x1800ff225  div     r8
0x1800ff228  cmp     r9, rax
0x1800ff22b  ja      short loc_1800FF242
0x1800ff22d  xor     edx, edx
0x1800ff22f  mov     ecx, r8d
0x1800ff232  imul    ecx, r9d
0x1800ff236  mov     eax, ebx
0x1800ff238  div     ecx
0x1800ff23a  cmp     eax, edi
0x1800ff23c  jb      loc_1800FF2E3
0x1800ff242  mov     [r14], edi
0x1800ff245  test    rsi, rsi
0x1800ff248  jz      short loc_1800FF26F
0x1800ff24a  test    r11, r11
0x1800ff24d  jz      short loc_1800FF26C
0x1800ff24f  xor     edx, edx
0x1800ff251  mov     rax, r15
0x1800ff254  div     r8
0x1800ff257  cmp     r9, rax
0x1800ff25a  ja      short loc_1800FF26C
0x1800ff25c  imul    r8d, r9d
0x1800ff260  xor     edx, edx
0x1800ff262  mov     eax, ebx
0x1800ff264  div     r8d
0x1800ff267  cmp     eax, r10d
0x1800ff26a  jb      short loc_1800FF2EB
0x1800ff26c  mov     [rsi], r10d
0x1800ff26f  mov     eax, 1
0x1800ff274  mov     rcx, [rbp+4Fh+var_38]
0x1800ff278  xor     rcx, rsp; StackCookie
0x1800ff27b  call    __security_check_cookie
0x1800ff280  add     rsp, 0B8h
0x1800ff287  pop     r15
0x1800ff289  pop     r14
0x1800ff28b  pop     rdi
0x1800ff28c  pop     rsi
0x1800ff28d  pop     rbx
0x1800ff28e  pop     rbp
0x1800ff28f  retn
0x1800ff291  mov     ecx, eax
0x1800ff293  call    BaseSetLastNTError
0x1800ff298  mov     rcx, gs:60h
0x1800ff2a1  mov     r8, rdi; P
0x1800ff2a4  xor     edx, edx; Flags
0x1800ff2a6  mov     rcx, [rcx+30h]; HeapHandle
0x1800ff2aa  call    cs:__imp_RtlFreeHeap
0x1800ff2b1  nop     dword ptr [rax+rax+00h]
0x1800ff2b6  test    rbx, rbx
0x1800ff2b9  jnz     short loc_1800FF2DB
0x1800ff2bb  xor     eax, eax
0x1800ff2bd  jmp     short loc_1800FF274
0x1800ff2bf  mov     ecx, edi
0x1800ff2c1  call    BaseSetLastNTError
0x1800ff2c6  jmp     short loc_1800FF2BB
0x1800ff2c8  mov     ecx, 3; LastError
0x1800ff2cd  call    cs:__imp_RtlSetLastWin32Error
0x1800ff2d4  nop     dword ptr [rax+rax+00h]
0x1800ff2d9  jmp     short loc_1800FF2BB
0x1800ff2db  mov     dword ptr [rbx], 0
0x1800ff2e1  jmp     short loc_1800FF2BB
0x1800ff2e3  mov     [r14], eax
0x1800ff2e6  jmp     loc_1800FF245
0x1800ff2eb  mov     [rsi], eax
0x1800ff2ed  jmp     short loc_1800FF26F
```
