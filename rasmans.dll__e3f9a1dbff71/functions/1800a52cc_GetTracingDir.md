# GetTracingDir

- ea: `0x1800a52cc`
- end: `0x1800a54f2`
- name: `GetTracingDir`
- size: `550`
- prototype: `wchar_t *__fastcall(__int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a49ec`
- `0x1800a54f8`

## callees

- `0x18000e4f0`
- `0x1800a4de0`
- `0x1800a4ed4`
- `0x1800a5254`
- `0x1800a52cc`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a545d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a54ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a545d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a54ac`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5384`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5384`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a534b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a534b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a54ca`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a54ca`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a541a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800a541a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a546c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5493`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a546c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a5493`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a53e4`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800a53e4`

## string_xrefs

- `0x1800a5369`: `FileDirectory`

## pseudocode

```c
wchar_t *__fastcall GetTracingDir(__int64 *a1)
{
  __int64 v2; // rcx
  const wchar_t *v3; // r9
  __int64 v4; // rdx
  BYTE *v5; // rax
  BYTE *v6; // rcx
  __int64 v7; // rax
  bool v8; // zf
  DWORD v9; // eax
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  void *FolderHandle; // rax
  void *v13; // rsi
  wchar_t *v14; // rcx
  __int64 FileHandle; // rdi
  wchar_t *DefaultDir; // rax
  void *v17; // rax
  void *v18; // rsi
  wchar_t *v19; // rcx
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
    v2 = 2147483646;
    v3 = L"%windir%\\tracing";
    v4 = 260;
    v5 = (BYTE *)Data;
    do
    {
      if ( !v2 )
        break;
      if ( !*v3 )
        break;
      *(_WORD *)v5 = *v3++;
      v5 += 2;
      --v2;
      --v4;
    }
    while ( v4 );
    v6 = v5 - 2;
    if ( v4 )
      v6 = v5;
    *(_WORD *)v6 = 0;
  }
  if ( ExpandEnvironmentStringsW(Data, Dst, 0x104u) )
  {
    v7 = -1;
    do
      ++v7;
    while ( Dst[v7] );
    v8 = (_DWORD)v7 == -1;
    v9 = v7 + 1;
    cbData = v9;
    if ( !v8 )
    {
      v10 = (wchar_t *)LocalAlloc(0x40u, 2LL * v9);
      v11 = v10;
      if ( v10 )
      {
        StringCchCopyW(v10, cbData, Dst);
        FolderHandle = (void *)GetFolderHandle(v11);
        v13 = FolderHandle;
        v14 = v11;
        if ( FolderHandle != (void *)-1LL )
        {
          FileHandle = GetFileHandle((__int64)v11, FolderHandle);
          CloseHandle(v13);
          if ( FileHandle != -1 )
            goto LABEL_24;
          v14 = v11;
        }
        LocalFree(v14);
      }
    }
  }
  DefaultDir = (wchar_t *)GetDefaultDir();
  v11 = DefaultDir;
  if ( !DefaultDir )
    goto LABEL_25;
  v17 = (void *)GetFolderHandle(DefaultDir);
  v18 = v17;
  v19 = v11;
  if ( v17 == (void *)-1LL )
    goto LABEL_21;
  FileHandle = GetFileHandle((__int64)v11, v17);
  CloseHandle(v18);
  if ( FileHandle == -1 )
  {
    v19 = v11;
LABEL_21:
    LocalFree(v19);
    v11 = 0;
    goto LABEL_25;
  }
LABEL_24:
  *a1 = FileHandle;
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  return v11;
}

```

## disassembly

```asm
0x1800a52cc  push    rbp
0x1800a52ce  push    rbx
0x1800a52cf  push    rsi
0x1800a52d0  push    rdi
0x1800a52d1  push    r14
0x1800a52d3  push    r15
0x1800a52d5  lea     rbp, [rsp-378h]
0x1800a52dd  sub     rsp, 478h
0x1800a52e4  mov     rax, cs:__security_cookie
0x1800a52eb  xor     rax, rsp
0x1800a52ee  mov     [rbp+3A0h+var_40], rax
0x1800a52f5  mov     r14, rcx
0x1800a52f8  mov     edi, 20Ah
0x1800a52fd  mov     r8d, edi; Size
0x1800a5300  lea     rcx, [rsp+4A0h+Data]; void *
0x1800a5305  xor     edx, edx; Val
0x1800a5307  call    memset_0
0x1800a530c  mov     r8d, edi; Size
0x1800a530f  lea     rcx, [rbp+3A0h+Dst]; void *
0x1800a5316  xor     edx, edx; Val
0x1800a5318  call    memset_0
0x1800a531d  lea     rax, [rsp+4A0h+hKey]
0x1800a5322  xor     r15d, r15d
0x1800a5325  mov     r9d, 20019h; samDesired
0x1800a532b  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800a5330  xor     r8d, r8d; ulOptions
0x1800a5333  mov     [rsp+4A0h+hKey], r15
0x1800a5338  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Tracing"
0x1800a533f  mov     [rsp+4A0h+cbData], r15d
0x1800a5344  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a534b  call    cs:__imp_RegOpenKeyExW
0x1800a5351  mov     ebx, 104h
0x1800a5356  test    eax, eax
0x1800a5358  jnz     short loc_1800A538E
0x1800a535a  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800a535f  lea     rax, [rsp+4A0h+cbData]
0x1800a5364  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x1800a5369  lea     rdx, aFiledirectory; "FileDirectory"
0x1800a5370  lea     rax, [rsp+4A0h+Data]
0x1800a5375  mov     [rsp+4A0h+cbData], edi
0x1800a5379  xor     r9d, r9d; lpType
0x1800a537c  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800a5381  xor     r8d, r8d; lpReserved
0x1800a5384  call    cs:__imp_RegQueryValueExW
0x1800a538a  test    eax, eax
0x1800a538c  jz      short loc_1800A53D5
0x1800a538e  mov     ecx, 7FFFFFFEh
0x1800a5393  lea     r9, aWindirTracing; "%windir%\\tracing"
0x1800a539a  mov     rdx, rbx
0x1800a539d  lea     rax, [rsp+4A0h+Data]
0x1800a53a2  test    rcx, rcx
0x1800a53a5  jz      short loc_1800A53C6
0x1800a53a7  movzx   r8d, word ptr [r9]
0x1800a53ab  test    r8w, r8w
0x1800a53af  jz      short loc_1800A53C6
0x1800a53b1  mov     [rax], r8w
0x1800a53b5  add     r9, 2
0x1800a53b9  add     rax, 2
0x1800a53bd  dec     rcx
0x1800a53c0  sub     rdx, 1
0x1800a53c4  jnz     short loc_1800A53A2
0x1800a53c6  test    rdx, rdx
0x1800a53c9  lea     rcx, [rax-2]
0x1800a53cd  cmovnz  rcx, rax
0x1800a53d1  mov     [rcx], r15w
0x1800a53d5  mov     r8d, ebx; nSize
0x1800a53d8  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x1800a53df  lea     rcx, [rsp+4A0h+Data]; lpSrc
0x1800a53e4  call    cs:__imp_ExpandEnvironmentStringsW
0x1800a53ea  test    eax, eax
0x1800a53ec  jz      loc_1800A5472
0x1800a53f2  lea     rcx, [rbp+3A0h+Dst]
0x1800a53f9  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800a53fd  inc     rax
0x1800a5400  cmp     [rcx+rax*2], r15w
0x1800a5405  jnz     short loc_1800A53FD
0x1800a5407  add     eax, 1
0x1800a540a  mov     [rsp+4A0h+cbData], eax
0x1800a540e  jz      short loc_1800A5472
0x1800a5410  mov     edx, eax
0x1800a5412  mov     ecx, 40h ; '@'; uFlags
0x1800a5417  add     rdx, rdx; uBytes
0x1800a541a  call    cs:__imp_LocalAlloc
0x1800a5420  mov     rbx, rax
0x1800a5423  test    rax, rax
0x1800a5426  jz      short loc_1800A5472
0x1800a5428  mov     edx, [rsp+4A0h+cbData]; cchDest
0x1800a542c  lea     r8, [rbp+3A0h+Dst]; pszSrc
0x1800a5433  mov     rcx, rax; pszDest
0x1800a5436  call    StringCchCopyW
0x1800a543b  mov     rcx, rbx; String1
0x1800a543e  call    GetFolderHandle
0x1800a5443  mov     rsi, rax
0x1800a5446  mov     rcx, rbx
0x1800a5449  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a544d  jz      short loc_1800A546C
0x1800a544f  mov     rdx, rax
0x1800a5452  call    GetFileHandle
0x1800a5457  mov     rcx, rsi; hObject
0x1800a545a  mov     rdi, rax
0x1800a545d  call    cs:__imp_CloseHandle
0x1800a5463  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a5467  jnz     short loc_1800A54BD
0x1800a5469  mov     rcx, rbx; hMem
0x1800a546c  call    cs:__imp_LocalFree
0x1800a5472  call    GetDefaultDir
0x1800a5477  mov     rbx, rax
0x1800a547a  test    rax, rax
0x1800a547d  jz      short loc_1800A54C0
0x1800a547f  mov     rcx, rax; String1
0x1800a5482  call    GetFolderHandle
0x1800a5487  mov     rsi, rax
0x1800a548a  mov     rcx, rbx; hMem
0x1800a548d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a5491  jnz     short loc_1800A549E
0x1800a5493  call    cs:__imp_LocalFree
0x1800a5499  mov     rbx, r15
0x1800a549c  jmp     short loc_1800A54C0
0x1800a549e  mov     rdx, rsi
0x1800a54a1  call    GetFileHandle
0x1800a54a6  mov     rcx, rsi; hObject
0x1800a54a9  mov     rdi, rax
0x1800a54ac  call    cs:__imp_CloseHandle
0x1800a54b2  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800a54b6  jnz     short loc_1800A54BD
0x1800a54b8  mov     rcx, rbx
0x1800a54bb  jmp     short loc_1800A5493
0x1800a54bd  mov     [r14], rdi
0x1800a54c0  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800a54c5  test    rcx, rcx
0x1800a54c8  jz      short loc_1800A54D0
0x1800a54ca  call    cs:__imp_RegCloseKey
0x1800a54d0  mov     rax, rbx
0x1800a54d3  mov     rcx, [rbp+3A0h+var_40]
0x1800a54da  xor     rcx, rsp; StackCookie
0x1800a54dd  call    __security_check_cookie
0x1800a54e2  add     rsp, 478h
0x1800a54e9  pop     r15
0x1800a54eb  pop     r14
0x1800a54ed  pop     rdi
0x1800a54ee  pop     rsi
0x1800a54ef  pop     rbx
0x1800a54f0  pop     rbp
0x1800a54f1  retn
```
