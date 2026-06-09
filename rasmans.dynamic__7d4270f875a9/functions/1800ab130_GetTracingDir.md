# GetTracingDir

- ea: `0x1800ab130`
- end: `0x1800ab38d`
- name: `GetTracingDir`
- size: `605`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800aa728`
- `0x1800ab394`

## callees

- `0x18000eae0`
- `0x1800aab94`
- `0x1800aac9c`
- `0x1800ab0ac`
- `0x1800ab130`
- `0x1800e8e96`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab2d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab33a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab2d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab33a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab1af`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800ab1af`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab35e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800ab35e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab1ee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800ab1ee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ab290`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800ab290`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab2ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab31b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab2ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ab31b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ab254`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ab254`

## string_xrefs

- `0x1800ab1d3`: `FileDirectory`

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
0x1800ab130  push    rbp
0x1800ab132  push    rbx
0x1800ab133  push    rsi
0x1800ab134  push    rdi
0x1800ab135  push    r14
0x1800ab137  push    r15
0x1800ab139  lea     rbp, [rsp-378h]
0x1800ab141  sub     rsp, 478h
0x1800ab148  mov     rax, cs:__security_cookie
0x1800ab14f  xor     rax, rsp
0x1800ab152  mov     [rbp+3A0h+var_40], rax
0x1800ab159  mov     r14, rcx
0x1800ab15c  mov     edi, 20Ah
0x1800ab161  mov     r8d, edi; Size
0x1800ab164  lea     rcx, [rsp+4A0h+Data]; void *
0x1800ab169  xor     edx, edx; Val
0x1800ab16b  call    memset_0
0x1800ab170  mov     r8d, edi; Size
0x1800ab173  lea     rcx, [rbp+3A0h+Dst]; void *
0x1800ab17a  xor     edx, edx; Val
0x1800ab17c  call    memset_0
0x1800ab181  lea     rax, [rsp+4A0h+hKey]
0x1800ab186  xor     r15d, r15d
0x1800ab189  mov     r9d, 20019h; samDesired
0x1800ab18f  mov     [rsp+4A0h+phkResult], rax; phkResult
0x1800ab194  xor     r8d, r8d; ulOptions
0x1800ab197  mov     [rsp+4A0h+hKey], r15
0x1800ab19c  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Tracing"
0x1800ab1a3  mov     [rsp+4A0h+cbData], r15d
0x1800ab1a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800ab1af  call    cs:__imp_RegOpenKeyExW
0x1800ab1b6  nop     dword ptr [rax+rax+00h]
0x1800ab1bb  mov     ebx, 104h
0x1800ab1c0  test    eax, eax
0x1800ab1c2  jnz     short loc_1800AB1FE
0x1800ab1c4  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800ab1c9  lea     rax, [rsp+4A0h+cbData]
0x1800ab1ce  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x1800ab1d3  lea     rdx, aFiledirectory; "FileDirectory"
0x1800ab1da  lea     rax, [rsp+4A0h+Data]
0x1800ab1df  mov     [rsp+4A0h+cbData], edi
0x1800ab1e3  xor     r9d, r9d; lpType
0x1800ab1e6  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800ab1eb  xor     r8d, r8d; lpReserved
0x1800ab1ee  call    cs:__imp_RegQueryValueExW
0x1800ab1f5  nop     dword ptr [rax+rax+00h]
0x1800ab1fa  test    eax, eax
0x1800ab1fc  jz      short loc_1800AB245
0x1800ab1fe  mov     ecx, 7FFFFFFEh
0x1800ab203  lea     r9, aWindirTracing; "%windir%\\tracing"
0x1800ab20a  mov     rdx, rbx
0x1800ab20d  lea     rax, [rsp+4A0h+Data]
0x1800ab212  test    rcx, rcx
0x1800ab215  jz      short loc_1800AB236
0x1800ab217  movzx   r8d, word ptr [r9]
0x1800ab21b  test    r8w, r8w
0x1800ab21f  jz      short loc_1800AB236
0x1800ab221  mov     [rax], r8w
0x1800ab225  add     r9, 2
0x1800ab229  add     rax, 2
0x1800ab22d  dec     rcx
0x1800ab230  sub     rdx, 1
0x1800ab234  jnz     short loc_1800AB212
0x1800ab236  test    rdx, rdx
0x1800ab239  lea     rcx, [rax-2]
0x1800ab23d  cmovnz  rcx, rax
0x1800ab241  mov     [rcx], r15w
0x1800ab245  mov     r8d, ebx; nSize
0x1800ab248  lea     rdx, [rbp+3A0h+Dst]; lpDst
0x1800ab24f  lea     rcx, [rsp+4A0h+Data]; lpSrc
0x1800ab254  call    cs:__imp_ExpandEnvironmentStringsW
0x1800ab25b  nop     dword ptr [rax+rax+00h]
0x1800ab260  test    eax, eax
0x1800ab262  jz      loc_1800AB2FA
0x1800ab268  lea     rcx, [rbp+3A0h+Dst]
0x1800ab26f  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800ab273  inc     rax
0x1800ab276  cmp     [rcx+rax*2], r15w
0x1800ab27b  jnz     short loc_1800AB273
0x1800ab27d  add     eax, 1
0x1800ab280  mov     [rsp+4A0h+cbData], eax
0x1800ab284  jz      short loc_1800AB2FA
0x1800ab286  mov     edx, eax
0x1800ab288  mov     ecx, 40h ; '@'; uFlags
0x1800ab28d  add     rdx, rdx; uBytes
0x1800ab290  call    cs:__imp_LocalAlloc
0x1800ab297  nop     dword ptr [rax+rax+00h]
0x1800ab29c  mov     rbx, rax
0x1800ab29f  test    rax, rax
0x1800ab2a2  jz      short loc_1800AB2FA
0x1800ab2a4  mov     edx, [rsp+4A0h+cbData]; cchDest
0x1800ab2a8  lea     r8, [rbp+3A0h+Dst]; pszSrc
0x1800ab2af  mov     rcx, rax; pszDest
0x1800ab2b2  call    StringCchCopyW
0x1800ab2b7  mov     rcx, rbx; String1
0x1800ab2ba  call    GetFolderHandle
0x1800ab2bf  mov     rsi, rax
0x1800ab2c2  mov     rcx, rbx
0x1800ab2c5  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ab2c9  jz      short loc_1800AB2EE
0x1800ab2cb  mov     rdx, rax
0x1800ab2ce  call    GetFileHandle
0x1800ab2d3  mov     rcx, rsi; hObject
0x1800ab2d6  mov     rdi, rax
0x1800ab2d9  call    cs:__imp_CloseHandle
0x1800ab2e0  nop     dword ptr [rax+rax+00h]
0x1800ab2e5  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ab2e9  jnz     short loc_1800AB351
0x1800ab2eb  mov     rcx, rbx; hMem
0x1800ab2ee  call    cs:__imp_LocalFree
0x1800ab2f5  nop     dword ptr [rax+rax+00h]
0x1800ab2fa  call    GetDefaultDir
0x1800ab2ff  mov     rbx, rax
0x1800ab302  test    rax, rax
0x1800ab305  jz      short loc_1800AB354
0x1800ab307  mov     rcx, rax; String1
0x1800ab30a  call    GetFolderHandle
0x1800ab30f  mov     rsi, rax
0x1800ab312  mov     rcx, rbx; hMem
0x1800ab315  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ab319  jnz     short loc_1800AB32C
0x1800ab31b  call    cs:__imp_LocalFree
0x1800ab322  nop     dword ptr [rax+rax+00h]
0x1800ab327  mov     rbx, r15
0x1800ab32a  jmp     short loc_1800AB354
0x1800ab32c  mov     rdx, rsi
0x1800ab32f  call    GetFileHandle
0x1800ab334  mov     rcx, rsi; hObject
0x1800ab337  mov     rdi, rax
0x1800ab33a  call    cs:__imp_CloseHandle
0x1800ab341  nop     dword ptr [rax+rax+00h]
0x1800ab346  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1800ab34a  jnz     short loc_1800AB351
0x1800ab34c  mov     rcx, rbx
0x1800ab34f  jmp     short loc_1800AB31B
0x1800ab351  mov     [r14], rdi
0x1800ab354  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800ab359  test    rcx, rcx
0x1800ab35c  jz      short loc_1800AB36A
0x1800ab35e  call    cs:__imp_RegCloseKey
0x1800ab365  nop     dword ptr [rax+rax+00h]
0x1800ab36a  mov     rax, rbx
0x1800ab36d  mov     rcx, [rbp+3A0h+var_40]
0x1800ab374  xor     rcx, rsp; StackCookie
0x1800ab377  call    __security_check_cookie
0x1800ab37c  add     rsp, 478h
0x1800ab383  pop     r15
0x1800ab385  pop     r14
0x1800ab387  pop     rdi
0x1800ab388  pop     rsi
0x1800ab389  pop     rbx
0x1800ab38a  pop     rbp
0x1800ab38b  retn
```
