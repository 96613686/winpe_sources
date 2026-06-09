# TrustLabelAceHelpers::CheckForRemovableMediaEfsEncryption(void *,bool *)

- ea: `0x1800afc18`
- end: `0x1800afe0d`
- name: `?CheckForRemovableMediaEfsEncryption@TrustLabelAceHelpers@@CAJPEAXPEA_N@Z`
- size: `501`
- prototype: `__int64 __fastcall(HANDLE hFile, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800afe14`

## callees

- `0x1800053a0`
- `0x180005794`
- `0x180009338`
- `0x18000e214`
- `0x18001e32c`
- `0x18003fa14`
- `0x1800afc18`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800afdc7`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800afdc7`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800afd2e`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800afd2e`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageVolumeSisPath` at `0x1800afc5d`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageVolumeSisPath` at `0x1800afcd4`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageVolumeSisPath` at `0x1800afc5d`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageVolumeSisPath` at `0x1800afcd4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall TrustLabelAceHelpers::CheckForRemovableMediaEfsEncryption(HANDLE hFile, bool *a2)
{
  int PackageVolumeSisPath; // eax
  unsigned __int64 v5; // rdx
  unsigned int LastError; // ebx
  _WORD *v7; // rdi
  unsigned __int64 v8; // rdx
  unsigned int v9; // eax
  unsigned __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  const char *v12; // r9
  unsigned __int64 v13; // rdx
  const char *v15; // r9
  unsigned int lpMaximumComponentLength; // [rsp+20h] [rbp-39h]
  unsigned int v17; // [rsp+40h] [rbp-19h] BYREF
  DWORD VolumeSerialNumber; // [rsp+44h] [rbp-15h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a2 = 0;
  VolumeSerialNumber = 0;
  v17 = 0;
  PackageVolumeSisPath = GetPackageVolumeSisPath(1, &v17, 0);
  LastError = PackageVolumeSisPath;
  if ( !PackageVolumeSisPath )
  {
    operator delete(0, v5);
    LastError = -2147418113;
LABEL_12:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x90,
      (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelacehelpers.cpp",
      (const char *)LastError,
      lpMaximumComponentLength);
    return LastError;
  }
  if ( PackageVolumeSisPath == 122 )
  {
    v7 = operator new(saturated_mul(v17, 2u));
    operator delete(0, v8);
    v9 = GetPackageVolumeSisPath(1, &v17, v7);
    if ( v9 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xB7,
                    (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelacehelpers.cpp",
                    (const char *)v9,
                    lpMaximumComponentLength);
      operator delete(v7, v10);
    }
    else
    {
      v7[3] = 0;
      if ( GetVolumeInformationW(v7, 0, 0, &VolumeSerialNumber, 0, 0, 0, 0) )
      {
        operator delete(v7, v11);
        LastError = 0;
        goto LABEL_15;
      }
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xBF,
                    (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelacehelpers.cpp",
                    v12);
      operator delete(v7, v13);
    }
  }
  else
  {
    if ( PackageVolumeSisPath > 0 )
      LastError = (unsigned __int16)PackageVolumeSisPath | 0x80070000;
    operator delete(0, v5);
  }
  if ( (LastError & 0x80000000) != 0 )
    goto LABEL_12;
LABEL_15:
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(hFile, &FileInformation) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x93,
             (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelacehelpers.cpp",
             v15);
  if ( FileInformation.dwVolumeSerialNumber == VolumeSerialNumber || (FileInformation.dwFileAttributes & 0x4000) == 0 )
    return LastError;
  *a2 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800afc18  mov     [rsp-8+arg_10], rbx
0x1800afc1d  push    rbp
0x1800afc1e  push    rsi
0x1800afc1f  push    rdi
0x1800afc20  push    r14
0x1800afc22  push    r15
0x1800afc24  lea     rbp, [rsp-37h]
0x1800afc29  sub     rsp, 90h
0x1800afc30  mov     rax, cs:__security_cookie
0x1800afc37  xor     rax, rsp
0x1800afc3a  mov     [rbp+57h+var_30], rax
0x1800afc3e  mov     rsi, rdx
0x1800afc41  mov     r14, rcx
0x1800afc44  xor     r15d, r15d
0x1800afc47  mov     [rdx], r15b
0x1800afc4a  mov     [rbp+57h+VolumeSerialNumber], r15d
0x1800afc4e  mov     [rbp+57h+var_70], r15d
0x1800afc52  xor     r8d, r8d
0x1800afc55  lea     rdx, [rbp+57h+var_70]
0x1800afc59  lea     ecx, [r15+1]
0x1800afc5d  call    cs:__imp_GetPackageVolumeSisPath
0x1800afc64  nop     dword ptr [rax+rax+00h]
0x1800afc69  mov     ebx, eax
0x1800afc6b  test    eax, eax
0x1800afc6d  jnz     short loc_1800AFC81
0x1800afc6f  xor     ecx, ecx; void *
0x1800afc71  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800afc76  nop
0x1800afc77  mov     ebx, 8000FFFFh
0x1800afc7c  jmp     loc_1800AFD62
0x1800afc81  cmp     eax, 7Ah ; 'z'
0x1800afc84  jz      short loc_1800AFCA0
0x1800afc86  test    eax, eax
0x1800afc88  jle     short loc_1800AFC93
0x1800afc8a  movzx   ebx, ax
0x1800afc8d  or      ebx, 80070000h
0x1800afc93  xor     ecx, ecx; void *
0x1800afc95  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800afc9a  nop
0x1800afc9b  jmp     loc_1800AFD5E
0x1800afca0  mov     ecx, [rbp+57h+var_70]
0x1800afca3  mov     eax, 2
0x1800afca8  mul     rcx
0x1800afcab  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800afcb2  cmovo   rax, rcx
0x1800afcb6  mov     rcx, rax; Size
0x1800afcb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800afcbe  mov     rdi, rax
0x1800afcc1  xor     ecx, ecx; void *
0x1800afcc3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800afcc8  mov     r8, rdi
0x1800afccb  lea     rdx, [rbp+57h+var_70]
0x1800afccf  mov     ecx, 1
0x1800afcd4  call    cs:__imp_GetPackageVolumeSisPath
0x1800afcdb  nop     dword ptr [rax+rax+00h]
0x1800afce0  test    eax, eax
0x1800afce2  jz      short loc_1800AFD09
0x1800afce4  mov     rcx, [rbp+5Fh]; this
0x1800afce8  mov     r9d, eax; char *
0x1800afceb  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800afcf2  mov     edx, 0B7h; void *
0x1800afcf7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800afcfc  mov     ebx, eax
0x1800afcfe  mov     rcx, rdi; void *
0x1800afd01  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800afd06  nop
0x1800afd07  jmp     short loc_1800AFD5E
0x1800afd09  mov     [rdi+6], r15w
0x1800afd0e  mov     [rsp+0B0h+nFileSystemNameSize], r15d; nFileSystemNameSize
0x1800afd13  mov     [rsp+0B0h+lpFileSystemNameBuffer], r15; lpFileSystemNameBuffer
0x1800afd18  mov     [rsp+0B0h+lpFileSystemFlags], r15; lpFileSystemFlags
0x1800afd1d  mov     [rsp+0B0h+lpMaximumComponentLength], r15; int
0x1800afd22  lea     r9, [rbp+57h+VolumeSerialNumber]; lpVolumeSerialNumber
0x1800afd26  xor     r8d, r8d; nVolumeNameSize
0x1800afd29  xor     edx, edx; lpVolumeNameBuffer
0x1800afd2b  mov     rcx, rdi; lpRootPathName
0x1800afd2e  call    cs:__imp_GetVolumeInformationW
0x1800afd35  nop     dword ptr [rax+rax+00h]
0x1800afd3a  test    eax, eax
0x1800afd3c  jnz     short loc_1800AFDA0
0x1800afd3e  mov     rcx, [rbp+5Fh]; this
0x1800afd42  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800afd49  mov     edx, 0BFh; void *
0x1800afd4e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800afd53  mov     ebx, eax
0x1800afd55  mov     rcx, rdi; void *
0x1800afd58  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800afd5d  nop
0x1800afd5e  test    ebx, ebx
0x1800afd60  jns     short loc_1800AFDAC
0x1800afd62  mov     rcx, [rbp+5Fh]; this
0x1800afd66  mov     r9d, ebx; char *
0x1800afd69  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800afd70  mov     edx, 90h; void *
0x1800afd75  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800afd7a  mov     eax, ebx
0x1800afd7c  mov     rcx, [rbp+57h+var_30]
0x1800afd80  xor     rcx, rsp; StackCookie
0x1800afd83  call    __security_check_cookie
0x1800afd88  mov     rbx, [rsp+0B0h+arg_10]
0x1800afd90  add     rsp, 90h
0x1800afd97  pop     r15
0x1800afd99  pop     r14
0x1800afd9b  pop     rdi
0x1800afd9c  pop     rsi
0x1800afd9d  pop     rbp
0x1800afd9e  retn
0x1800afda0  mov     rcx, rdi; void *
0x1800afda3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800afda8  nop
0x1800afda9  mov     ebx, r15d
0x1800afdac  xorps   xmm0, xmm0
0x1800afdaf  xor     eax, eax
0x1800afdb1  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1800afdb5  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800afdb9  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1800afdbd  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800afdc0  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1800afdc4  mov     rcx, r14; hFile
0x1800afdc7  call    cs:__imp_GetFileInformationByHandle
0x1800afdce  nop     dword ptr [rax+rax+00h]
0x1800afdd3  test    eax, eax
0x1800afdd5  jnz     short loc_1800AFDEE
0x1800afdd7  mov     rcx, [rbp+5Fh]; this
0x1800afddb  lea     r8, aOnecoreBaseApp_50; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800afde2  mov     edx, 93h; void *
0x1800afde7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800afdec  jmp     short loc_1800AFD7C
0x1800afdee  mov     eax, [rbp+57h+VolumeSerialNumber]
0x1800afdf1  cmp     [rbp+57h+FileInformation.dwVolumeSerialNumber], eax
0x1800afdf4  jz      short loc_1800AFD7A
0x1800afdf6  test    [rbp+57h+FileInformation.dwFileAttributes], 4000h
0x1800afdfd  jz      loc_1800AFD7A
0x1800afe03  mov     byte ptr [rsi], 1
0x1800afe06  xor     eax, eax
0x1800afe08  jmp     loc_1800AFD7C
```
