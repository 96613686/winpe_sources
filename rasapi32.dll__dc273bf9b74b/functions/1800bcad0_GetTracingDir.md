# GetTracingDir

- ea: `0x1800bcad0`
- end: `0x1800bccc3`
- name: `GetTracingDir`
- size: `499`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bb588`
- `0x1800bc1dc`
- `0x1800bcccc`

## callees

- `0x1800203dc`
- `0x1800bc604`
- `0x1800bc6d8`
- `0x1800bca58`
- `0x1800bcad0`
- `0x1800ded06`
- `0x1800ded50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bcb4f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bcb4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bcc9b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bcc9b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bcb88`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bcb88`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bcbeb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800bcbeb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcc3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcc64`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcc3d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bcc64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bcc2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bcc7d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bcc2e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bcc7d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800bcbb5`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800bcbb5`

## string_xrefs

- `0x1800bcb6d`: `FileDirectory`

## pseudocode

```c
wchar_t *__fastcall GetTracingDir(__int64 *a1)
{
  __int64 v2; // rax
  bool v3; // zf
  DWORD v4; // eax
  wchar_t *v5; // rax
  wchar_t *v6; // rbx
  void *FolderHandle; // rax
  void *v8; // rsi
  wchar_t *v9; // rcx
  __int64 FileHandle; // rdi
  wchar_t *DefaultDir; // rax
  void *v12; // rax
  void *v13; // rsi
  wchar_t *v14; // rcx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR Data[264]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Dst[264]; // [rsp+250h] [rbp+150h] BYREF

  memset_0(Data, 0, 0x20Au);
  memset_0(Dst, 0, 0x20Au);
  hKey = 0;
  cbData = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\Tracing", 0, 0x20019u, &hKey)
    || (cbData = 522, RegQueryValueExW(hKey, L"FileDirectory", 0, 0, (LPBYTE)Data, &cbData)) )
  {
    StringCchCopyW(Data, 0x104u, L"%windir%\\tracing");
  }
  if ( ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
  {
    v2 = -1;
    do
      ++v2;
    while ( Dst[v2] );
    v3 = (_DWORD)v2 == -1;
    v4 = v2 + 1;
    cbData = v4;
    if ( !v3 )
    {
      v5 = (wchar_t *)LocalAlloc(0x40u, 2LL * v4);
      v6 = v5;
      if ( v5 )
      {
        StringCchCopyW(v5, cbData, Dst);
        FolderHandle = (void *)GetFolderHandle(v6);
        v8 = FolderHandle;
        v9 = v6;
        if ( FolderHandle != (void *)-1LL )
        {
          FileHandle = GetFileHandle((__int64)v6, FolderHandle);
          CloseHandle(v8);
          if ( FileHandle != -1 )
            goto LABEL_18;
          v9 = v6;
        }
        LocalFree(v9);
      }
    }
  }
  DefaultDir = (wchar_t *)GetDefaultDir();
  v6 = DefaultDir;
  if ( !DefaultDir )
    goto LABEL_19;
  v12 = (void *)GetFolderHandle(DefaultDir);
  v13 = v12;
  v14 = v6;
  if ( v12 == (void *)-1LL )
    goto LABEL_15;
  FileHandle = GetFileHandle((__int64)v6, v12);
  CloseHandle(v13);
  if ( FileHandle == -1 )
  {
    v14 = v6;
LABEL_15:
    LocalFree(v14);
    v6 = 0;
    goto LABEL_19;
  }
LABEL_18:
  *a1 = FileHandle;
LABEL_19:
  if ( hKey )
    RegCloseKey(hKey);
  return v6;
}

```

## disassembly

```asm
0x1800bcad0  push    rbp
0x1800bcad2  push    rbx
0x1800bcad3  push    rsi
0x1800bcad4  push    rdi
0x1800bcad5  push    r14
0x1800bcad7  push    r15
0x1800bcad9  lea     rbp, [rsp-378h]
0x1800bcae1  sub     rsp, 478h
0x1800bcae8  mov     rax, cs:__security_cookie
0x1800bcaef  xor     rax, rsp
0x1800bcaf2  mov     [rbp+3A0h+var_40], rax
0x1800bcaf9  mov     r14, rcx
0x1800bcafc  mov     edi, 20Ah
0x1800bcb01  mov     r8d, edi; Size
0x1800bcb04  lea     rcx, [rsp+4A0h+Data]; void *
0x1800bcb09  xor     edx, edx; Val
0x1800bcb0b  call    memset_0
0x1800bcb10  mov     r8d, edi; Size
0x1800bcb13  lea     rcx, [rbp+3A0h+Dst]; void *
0x1800bcb1a  xor     edx, edx; Val
0x1800bcb1c  call    memset_0
0x1800bcb21  lea     rax, [rsp+4A0h+hKey]
0x1800bcb26  xor     r15d, r15d
0x1800bcb29  mov     r9d, 20019h; samDesired
0x1800bcb2f  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800bcb34  xor     r8d, r8d; ulOptions
0x1800bcb37  mov     [rsp+4A0h+hKey], r15
0x1800bcb3c  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Tracing"
0x1800bcb43  mov     [rsp+4A0h+cbData], r15d
0x1800bcb48  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bcb4f  call    cs:__imp_RegOpenKeyExW
0x1800bcb55  mov     ebx, 104h
0x1800bcb5a  test    eax, eax
0x1800bcb5c  jnz     short loc_1800BCB92
0x1800bcb5e  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800bcb63  lea     rax, [rsp+4A0h+cbData]
0x1800bcb68  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x1800bcb6d  lea     rdx, aFiledirectory; "FileDirectory"
0x1800bcb74  lea     rax, [rsp+4A0h+Data]
0x1800bcb79  mov     [rsp+4A0h+cbData], edi
0x1800bcb7d  xor     r9d, r9d; lpType
0x1800bcb80  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800bcb85  xor     r8d, r8d; lpReserved
0x1800bcb88  call    cs:__imp_RegQueryValueExW
0x1800bcb8e  test    eax, eax
0x1800bcb90  jz      short loc_1800BCBA6
0x1800bcb92  lea     r8, aWindirTracing; "%windir%\\tracing"
0x1800bcb99  mov     rdx, rbx; cchDest
0x1800bcb9c  lea     rcx, [rsp+4A0h+Data]; pszDest
0x1800bcba1  call    StringCchCopyW
0x1800bcba6  mov     r8d, ebx; nSize
0x1800bcba9  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x1800bcbb0  lea     rcx, [rsp+4A0h+Data]; lpSrc
0x1800bcbb5  call    cs:__imp_ExpandEnvironmentStringsW
0x1800bcbbb  test    eax, eax
0x1800bcbbd  jz      loc_1800BCC43
0x1800bcbc3  lea     rcx, [rbp+3A0h+Dst]
0x1800bcbca  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800bcbce  inc     rax
0x1800bcbd1  cmp     [rcx+rax*2], r15w
0x1800bcbd6  jnz     short loc_1800BCBCE
0x1800bcbd8  add     eax, 1
0x1800bcbdb  mov     [rsp+4A0h+cbData], eax
0x1800bcbdf  jz      short loc_1800BCC43
0x1800bcbe1  mov     edx, eax
0x1800bcbe3  mov     ecx, 40h ; '@'; uFlags
0x1800bcbe8  add     rdx, rdx; uBytes
0x1800bcbeb  call    cs:__imp_LocalAlloc
0x1800bcbf1  mov     rbx, rax
0x1800bcbf4  test    rax, rax
0x1800bcbf7  jz      short loc_1800BCC43
0x1800bcbf9  mov     edx, [rsp+4A0h+cbData]; cchDest
0x1800bcbfd  lea     r8, [rbp+3A0h+Dst]; pszSrc
0x1800bcc04  mov     rcx, rax; pszDest
0x1800bcc07  call    StringCchCopyW
0x1800bcc0c  mov     rcx, rbx; String1
0x1800bcc0f  call    GetFolderHandle
0x1800bcc14  mov     rsi, rax
0x1800bcc17  mov     rcx, rbx
0x1800bcc1a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bcc1e  jz      short loc_1800BCC3D
0x1800bcc20  mov     rdx, rax
0x1800bcc23  call    GetFileHandle
0x1800bcc28  mov     rcx, rsi; hObject
0x1800bcc2b  mov     rdi, rax
0x1800bcc2e  call    cs:__imp_CloseHandle
0x1800bcc34  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800bcc38  jnz     short loc_1800BCC8E
0x1800bcc3a  mov     rcx, rbx; hMem
0x1800bcc3d  call    cs:__imp_LocalFree
0x1800bcc43  call    GetDefaultDir
0x1800bcc48  mov     rbx, rax
0x1800bcc4b  test    rax, rax
0x1800bcc4e  jz      short loc_1800BCC91
0x1800bcc50  mov     rcx, rax; String1
0x1800bcc53  call    GetFolderHandle
0x1800bcc58  mov     rsi, rax
0x1800bcc5b  mov     rcx, rbx; hMem
0x1800bcc5e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bcc62  jnz     short loc_1800BCC6F
0x1800bcc64  call    cs:__imp_LocalFree
0x1800bcc6a  mov     rbx, r15
0x1800bcc6d  jmp     short loc_1800BCC91
0x1800bcc6f  mov     rdx, rsi
0x1800bcc72  call    GetFileHandle
0x1800bcc77  mov     rcx, rsi; hObject
0x1800bcc7a  mov     rdi, rax
0x1800bcc7d  call    cs:__imp_CloseHandle
0x1800bcc83  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800bcc87  jnz     short loc_1800BCC8E
0x1800bcc89  mov     rcx, rbx
0x1800bcc8c  jmp     short loc_1800BCC64
0x1800bcc8e  mov     [r14], rdi
0x1800bcc91  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800bcc96  test    rcx, rcx
0x1800bcc99  jz      short loc_1800BCCA1
0x1800bcc9b  call    cs:__imp_RegCloseKey
0x1800bcca1  mov     rax, rbx
0x1800bcca4  mov     rcx, [rbp+3A0h+var_40]
0x1800bccab  xor     rcx, rsp; StackCookie
0x1800bccae  call    __security_check_cookie
0x1800bccb3  add     rsp, 478h
0x1800bccba  pop     r15
0x1800bccbc  pop     r14
0x1800bccbe  pop     rdi
0x1800bccbf  pop     rsi
0x1800bccc0  pop     rbx
0x1800bccc1  pop     rbp
0x1800bccc2  retn
```
