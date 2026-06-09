# TrustLabelAceHelpers::CheckForRemovableMediaEfsEncryption(void *,bool *)

- ea: `0x1800b1e3c`
- end: `0x1800b2036`
- name: `?CheckForRemovableMediaEfsEncryption@TrustLabelAceHelpers@@CAJPEAXPEA_N@Z`
- size: `506`
- prototype: `__int64 __fastcall(HANDLE hFile, bool *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800b203c`

## callees

- `0x180004f70`
- `0x180005340`
- `0x18000ae88`
- `0x18000ff04`
- `0x18001eeb8`
- `0x1800417a8`
- `0x1800b1e3c`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800b1f57`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x1800b1f57`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800b1ff0`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x1800b1ff0`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageVolumeSisPath` at `0x1800b1e86`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageVolumeSisPath` at `0x1800b1efd`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageVolumeSisPath` at `0x1800b1e86`
- `api-ms-win-appmodel-runtime-internal-l1-1-1!GetPackageVolumeSisPath` at `0x1800b1efd`

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
  unsigned int lpMaximumComponentLength; // [rsp+20h] [rbp-29h]
  unsigned int v17; // [rsp+40h] [rbp-9h] BYREF
  DWORD VolumeSerialNumber; // [rsp+44h] [rbp-5h] BYREF
  struct _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+48h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *a2 = 0;
  VolumeSerialNumber = 0;
  v17 = 0;
  PackageVolumeSisPath = GetPackageVolumeSisPath(1, &v17);
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
    v9 = GetPackageVolumeSisPath(1, &v17);
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
0x1800b1e3c  mov     [rsp-8+arg_10], rbx
0x1800b1e41  mov     [rsp-8+arg_18], rsi
0x1800b1e46  push    rbp
0x1800b1e47  push    rdi
0x1800b1e48  push    r14
0x1800b1e4a  lea     rbp, [rsp-47h]
0x1800b1e4f  sub     rsp, 90h
0x1800b1e56  mov     rax, cs:__security_cookie
0x1800b1e5d  xor     rax, rsp
0x1800b1e60  mov     [rbp+57h+var_20], rax
0x1800b1e64  mov     rsi, rdx
0x1800b1e67  mov     r14, rcx
0x1800b1e6a  mov     byte ptr [rdx], 0
0x1800b1e6d  mov     [rbp+57h+VolumeSerialNumber], 0
0x1800b1e74  mov     [rbp+57h+var_60], 0
0x1800b1e7b  xor     r8d, r8d
0x1800b1e7e  lea     rdx, [rbp+57h+var_60]
0x1800b1e82  lea     ecx, [r8+1]
0x1800b1e86  call    cs:__imp_GetPackageVolumeSisPath
0x1800b1e8d  nop     dword ptr [rax+rax+00h]
0x1800b1e92  mov     ebx, eax
0x1800b1e94  test    eax, eax
0x1800b1e96  jnz     short loc_1800B1EAA
0x1800b1e98  xor     ecx, ecx; void *
0x1800b1e9a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b1e9f  nop
0x1800b1ea0  mov     ebx, 8000FFFFh
0x1800b1ea5  jmp     loc_1800B1F8B
0x1800b1eaa  cmp     eax, 7Ah ; 'z'
0x1800b1ead  jz      short loc_1800B1EC9
0x1800b1eaf  test    eax, eax
0x1800b1eb1  jle     short loc_1800B1EBC
0x1800b1eb3  movzx   ebx, ax
0x1800b1eb6  or      ebx, 80070000h
0x1800b1ebc  xor     ecx, ecx; void *
0x1800b1ebe  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b1ec3  nop
0x1800b1ec4  jmp     loc_1800B1F87
0x1800b1ec9  mov     ecx, [rbp+57h+var_60]
0x1800b1ecc  mov     eax, 2
0x1800b1ed1  mul     rcx
0x1800b1ed4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800b1edb  cmovb   rax, rcx
0x1800b1edf  mov     rcx, rax; Size
0x1800b1ee2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b1ee7  mov     rdi, rax
0x1800b1eea  xor     ecx, ecx; void *
0x1800b1eec  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b1ef1  mov     r8, rdi
0x1800b1ef4  lea     rdx, [rbp+57h+var_60]
0x1800b1ef8  mov     ecx, 1
0x1800b1efd  call    cs:__imp_GetPackageVolumeSisPath
0x1800b1f04  nop     dword ptr [rax+rax+00h]
0x1800b1f09  test    eax, eax
0x1800b1f0b  jz      short loc_1800B1F32
0x1800b1f0d  mov     rcx, [rbp+5Fh]; this
0x1800b1f11  mov     r9d, eax; char *
0x1800b1f14  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800b1f1b  mov     edx, 0B7h; void *
0x1800b1f20  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800b1f25  mov     ebx, eax
0x1800b1f27  mov     rcx, rdi; void *
0x1800b1f2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b1f2f  nop
0x1800b1f30  jmp     short loc_1800B1F87
0x1800b1f32  xor     eax, eax
0x1800b1f34  mov     [rdi+6], ax
0x1800b1f38  mov     [rsp+0A0h+nFileSystemNameSize], eax; nFileSystemNameSize
0x1800b1f3c  mov     [rsp+0A0h+lpFileSystemNameBuffer], rax; lpFileSystemNameBuffer
0x1800b1f41  mov     [rsp+0A0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x1800b1f46  mov     [rsp+0A0h+lpMaximumComponentLength], rax; int
0x1800b1f4b  lea     r9, [rbp+57h+VolumeSerialNumber]; lpVolumeSerialNumber
0x1800b1f4f  xor     r8d, r8d; nVolumeNameSize
0x1800b1f52  xor     edx, edx; lpVolumeNameBuffer
0x1800b1f54  mov     rcx, rdi; lpRootPathName
0x1800b1f57  call    cs:__imp_GetVolumeInformationW
0x1800b1f5e  nop     dword ptr [rax+rax+00h]
0x1800b1f63  test    eax, eax
0x1800b1f65  jnz     short loc_1800B1FCA
0x1800b1f67  mov     rcx, [rbp+5Fh]; this
0x1800b1f6b  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800b1f72  mov     edx, 0BFh; void *
0x1800b1f77  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b1f7c  mov     ebx, eax
0x1800b1f7e  mov     rcx, rdi; void *
0x1800b1f81  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b1f86  nop
0x1800b1f87  test    ebx, ebx
0x1800b1f89  jns     short loc_1800B1FD5
0x1800b1f8b  mov     rcx, [rbp+5Fh]; this
0x1800b1f8f  mov     r9d, ebx; char *
0x1800b1f92  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800b1f99  mov     edx, 90h; void *
0x1800b1f9e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800b1fa3  mov     eax, ebx
0x1800b1fa5  mov     rcx, [rbp+57h+var_20]
0x1800b1fa9  xor     rcx, rsp; StackCookie
0x1800b1fac  call    __security_check_cookie
0x1800b1fb1  lea     r11, [rsp+0A0h+var_10]
0x1800b1fb9  mov     rbx, [r11+30h]
0x1800b1fbd  mov     rsi, [r11+38h]
0x1800b1fc1  mov     rsp, r11
0x1800b1fc4  pop     r14
0x1800b1fc6  pop     rdi
0x1800b1fc7  pop     rbp
0x1800b1fc8  retn
0x1800b1fca  mov     rcx, rdi; void *
0x1800b1fcd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b1fd2  nop
0x1800b1fd3  xor     ebx, ebx
0x1800b1fd5  xorps   xmm0, xmm0
0x1800b1fd8  xor     eax, eax
0x1800b1fda  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x1800b1fde  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x1800b1fe2  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x1800b1fe6  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x1800b1fe9  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x1800b1fed  mov     rcx, r14; hFile
0x1800b1ff0  call    cs:__imp_GetFileInformationByHandle
0x1800b1ff7  nop     dword ptr [rax+rax+00h]
0x1800b1ffc  test    eax, eax
0x1800b1ffe  jnz     short loc_1800B2017
0x1800b2000  mov     rcx, [rbp+5Fh]; this
0x1800b2004  lea     r8, aOnecoreBaseApp_51; "onecore\\base\\appmodel\\trust\\trustla"...
0x1800b200b  mov     edx, 93h; void *
0x1800b2010  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800b2015  jmp     short loc_1800B1FA5
0x1800b2017  mov     eax, [rbp+57h+VolumeSerialNumber]
0x1800b201a  cmp     [rbp+57h+FileInformation.dwVolumeSerialNumber], eax
0x1800b201d  jz      short loc_1800B1FA3
0x1800b201f  test    [rbp+57h+FileInformation.dwFileAttributes], 4000h
0x1800b2026  jz      loc_1800B1FA3
0x1800b202c  mov     byte ptr [rsi], 1
0x1800b202f  xor     eax, eax
0x1800b2031  jmp     loc_1800B1FA5
```
