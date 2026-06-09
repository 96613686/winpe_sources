# ClearFiles

- ea: `0x1800bb588`
- end: `0x1800bb892`
- name: `ClearFiles`
- size: `778`
- prototype: `__int64 __fastcall(DWORD, DWORD, HKEY)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x1800bbcf8`

## callees

- `0x1800203dc`
- `0x18008d814`
- `0x1800bb588`
- `0x1800bcad0`
- `0x1800bcecc`
- `0x1800bcf04`
- `0x1800ded50`

## import_xrefs

- `msvcrt!fclose` at `0x1800bb7f5`
- `msvcrt!fclose` at `0x1800bb839`
- `msvcrt!fclose` at `0x1800bb7f5`
- `msvcrt!fclose` at `0x1800bb839`
- `msvcrt!_wfopen_s` at `0x1800bb7e5`
- `msvcrt!_wfopen_s` at `0x1800bb829`
- `msvcrt!_wfopen_s` at `0x1800bb7e5`
- `msvcrt!_wfopen_s` at `0x1800bb829`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bb67b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800bb67b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bb6e8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800bb6e8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb731`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800bb731`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb724`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800bb724`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb858`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bb858`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb84f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb627`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800bb84f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800bb7c0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800bb802`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800bb7c0`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800bb802`

## pseudocode

```c
__int64 __fastcall ClearFiles(DWORD a1, DWORD a2, HKEY a3)
{
  wchar_t *TracingDir; // r14
  wchar_t *v8; // rdi
  DWORD i; // esi
  LSTATUS v10; // ebx
  FILE *Stream; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+4Ch] [rbp-B4h] BYREF
  BYTE Data[8]; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  HANDLE hObject[2]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszSrc[264]; // [rsp+70h] [rbp-90h] BYREF
  wchar_t pszDest[264]; // [rsp+280h] [rbp+180h] BYREF
  wchar_t FileName[264]; // [rsp+490h] [rbp+390h] BYREF

  Stream = 0;
  cchName = 0;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  cbData = 4;
  hObject[0] = (HANDLE)-1LL;
  TracingDir = (wchar_t *)GetTracingDir(hObject);
  if ( !TracingDir )
    return 3;
  v8 = (wchar_t *)MemoryAlloc(2 * a2, 0);
  if ( v8 )
  {
    for ( i = 0; i < a1; ++i )
    {
      cchName = a2;
      if ( !RegEnumKeyExW(a3, i, v8, &cchName, 0, 0, 0, 0) )
      {
        StringCchCopyW(pszDest, 0x105u, L"SOFTWARE\\Microsoft\\Tracing");
        StringCchCatW(pszDest, 0x105u, L"\\");
        StringCchCatW(pszDest, 0x105u, v8);
        if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20019u, &phkResult) )
        {
          cbData = 4;
          v10 = RegQueryValueExW(phkResult, L"EnableFileTracing", 0, 0, Data, &cbData);
          RegCloseKey(phkResult);
          if ( !v10 && *(_DWORD *)Data != 1 )
          {
            StringCchCopyW(pszSrc, 0x105u, TracingDir);
            StringCchCatW(pszSrc, 0x105u, L"\\");
            StringCchCatW(pszSrc, 0x105u, v8);
            StringCchCopyW(FileName, 0x105u, pszSrc);
            StringCchCatW(pszSrc, 0x105u, L".LOG");
            StringCchCatW(FileName, 0x105u, L".OLD");
            if ( GetFileAttributesW(pszSrc) != -1 )
            {
              Stream = 0;
              _wfopen_s(&Stream, pszSrc, L"w");
              if ( Stream )
                fclose(Stream);
            }
            if ( GetFileAttributesW(FileName) != -1 )
            {
              Stream = 0;
              _wfopen_s(&Stream, FileName, L"w");
              if ( Stream )
                fclose(Stream);
            }
          }
        }
      }
    }
    CloseHandle(hObject[0]);
    LocalFree(TracingDir);
    MemoryFree(v8);
    return 0;
  }
  else
  {
    CloseHandle(hObject[0]);
    return 8;
  }
}

```

## disassembly

```asm
0x1800bb588  mov     [rsp-8+arg_0], rbx
0x1800bb58d  push    rbp
0x1800bb58e  push    rsi
0x1800bb58f  push    rdi
0x1800bb590  push    r12
0x1800bb592  push    r13
0x1800bb594  push    r14
0x1800bb596  push    r15
0x1800bb598  lea     rbp, [rsp-5B0h]
0x1800bb5a0  sub     rsp, 6B0h
0x1800bb5a7  mov     rax, cs:__security_cookie
0x1800bb5ae  xor     rax, rsp
0x1800bb5b1  mov     [rbp+5E0h+var_40], rax
0x1800bb5b8  mov     r13, r8
0x1800bb5bb  mov     [rsp+6E0h+Stream], 0
0x1800bb5c4  mov     r12d, edx
0x1800bb5c7  mov     [rsp+6E0h+cchName], 0
0x1800bb5cf  mov     r15d, ecx
0x1800bb5d2  mov     dword ptr [rsp+6E0h+Data], 0
0x1800bb5da  mov     [rsp+6E0h+phkResult], 0
0x1800bb5e3  mov     [rsp+6E0h+cbData], 4
0x1800bb5eb  mov     [rsp+6E0h+hObject], 0FFFFFFFFFFFFFFFFh
0x1800bb5f4  lea     rcx, [rsp+6E0h+hObject]
0x1800bb5f9  call    GetTracingDir
0x1800bb5fe  mov     r14, rax
0x1800bb601  test    rax, rax
0x1800bb604  jnz     short loc_1800BB60F
0x1800bb606  lea     eax, [r14+3]
0x1800bb60a  jmp     loc_1800BB868
0x1800bb60f  lea     ecx, [r12+r12]
0x1800bb613  xor     edx, edx
0x1800bb615  call    MemoryAlloc
0x1800bb61a  mov     rdi, rax
0x1800bb61d  test    rax, rax
0x1800bb620  jnz     short loc_1800BB635
0x1800bb622  mov     rcx, [rsp+6E0h+hObject]; hObject
0x1800bb627  call    cs:__imp_CloseHandle
0x1800bb62d  lea     eax, [rdi+8]
0x1800bb630  jmp     loc_1800BB868
0x1800bb635  xor     esi, esi
0x1800bb637  test    r15d, r15d
0x1800bb63a  jz      loc_1800BB84A
0x1800bb640  mov     ebx, 105h
0x1800bb645  mov     [rsp+6E0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800bb64e  lea     r9, [rsp+6E0h+cchName]; lpcchName
0x1800bb653  mov     [rsp+6E0h+lpcchClass], 0; lpcchClass
0x1800bb65c  mov     r8, rdi; lpName
0x1800bb65f  mov     [rsp+6E0h+lpClass], 0; lpClass
0x1800bb668  mov     edx, esi; dwIndex
0x1800bb66a  mov     rcx, r13; hKey
0x1800bb66d  mov     [rsp+6E0h+lpReserved], 0; lpReserved
0x1800bb676  mov     [rsp+6E0h+cchName], r12d
0x1800bb67b  call    cs:__imp_RegEnumKeyExW
0x1800bb681  test    eax, eax
0x1800bb683  jnz     loc_1800BB83F
0x1800bb689  lea     r8, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\Tracing"
0x1800bb690  mov     rdx, rbx; cchDest
0x1800bb693  lea     rcx, [rbp+5E0h+pszDest]; pszDest
0x1800bb69a  call    StringCchCopyW
0x1800bb69f  lea     r8, asc_1800E75F8; "\\"
0x1800bb6a6  mov     rdx, rbx; cchDest
0x1800bb6a9  lea     rcx, [rbp+5E0h+pszDest]; pszDest
0x1800bb6b0  call    StringCchCatW
0x1800bb6b5  mov     r8, rdi; pszSrc
0x1800bb6b8  lea     rcx, [rbp+5E0h+pszDest]; pszDest
0x1800bb6bf  mov     rdx, rbx; cchDest
0x1800bb6c2  call    StringCchCatW
0x1800bb6c7  lea     rax, [rsp+6E0h+phkResult]
0x1800bb6cc  mov     r9d, 20019h; samDesired
0x1800bb6d2  xor     r8d, r8d; ulOptions
0x1800bb6d5  mov     [rsp+6E0h+lpReserved], rax; phkResult
0x1800bb6da  lea     rdx, [rbp+5E0h+pszDest]; lpSubKey
0x1800bb6e1  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800bb6e8  call    cs:__imp_RegOpenKeyExW
0x1800bb6ee  test    eax, eax
0x1800bb6f0  jnz     loc_1800BB83F
0x1800bb6f6  mov     rcx, [rsp+6E0h+phkResult]; hKey
0x1800bb6fb  lea     rax, [rsp+6E0h+cbData]
0x1800bb700  mov     [rsp+6E0h+lpClass], rax; lpcbData
0x1800bb705  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800bb70c  lea     rax, [rsp+6E0h+Data]
0x1800bb711  mov     [rsp+6E0h+cbData], 4
0x1800bb719  xor     r9d, r9d; lpType
0x1800bb71c  mov     [rsp+6E0h+lpReserved], rax; lpData
0x1800bb721  xor     r8d, r8d; lpReserved
0x1800bb724  call    cs:__imp_RegQueryValueExW
0x1800bb72a  mov     rcx, [rsp+6E0h+phkResult]; hKey
0x1800bb72f  mov     ebx, eax
0x1800bb731  call    cs:__imp_RegCloseKey
0x1800bb737  test    ebx, ebx
0x1800bb739  mov     ebx, 105h
0x1800bb73e  jnz     loc_1800BB83F
0x1800bb744  cmp     dword ptr [rsp+6E0h+Data], 1
0x1800bb749  jz      loc_1800BB83F
0x1800bb74f  mov     r8, r14; pszSrc
0x1800bb752  lea     rcx, [rsp+6E0h+pszSrc]; pszDest
0x1800bb757  mov     edx, ebx; cchDest
0x1800bb759  call    StringCchCopyW
0x1800bb75e  lea     r8, asc_1800E75F8; "\\"
0x1800bb765  mov     edx, ebx; cchDest
0x1800bb767  lea     rcx, [rsp+6E0h+pszSrc]; pszDest
0x1800bb76c  call    StringCchCatW
0x1800bb771  mov     r8, rdi; pszSrc
0x1800bb774  lea     rcx, [rsp+6E0h+pszSrc]; pszDest
0x1800bb779  mov     edx, ebx; cchDest
0x1800bb77b  call    StringCchCatW
0x1800bb780  lea     r8, [rsp+6E0h+pszSrc]; pszSrc
0x1800bb785  mov     edx, ebx; cchDest
0x1800bb787  lea     rcx, [rbp+5E0h+FileName]; pszDest
0x1800bb78e  call    StringCchCopyW
0x1800bb793  lea     r8, aLog; ".LOG"
0x1800bb79a  mov     edx, ebx; cchDest
0x1800bb79c  lea     rcx, [rsp+6E0h+pszSrc]; pszDest
0x1800bb7a1  call    StringCchCatW
0x1800bb7a6  lea     r8, aOld_0; ".OLD"
0x1800bb7ad  mov     edx, ebx; cchDest
0x1800bb7af  lea     rcx, [rbp+5E0h+FileName]; pszDest
0x1800bb7b6  call    StringCchCatW
0x1800bb7bb  lea     rcx, [rsp+6E0h+pszSrc]; lpFileName
0x1800bb7c0  call    cs:__imp_GetFileAttributesW
0x1800bb7c6  cmp     eax, 0FFFFFFFFh
0x1800bb7c9  jz      short loc_1800BB7FB
0x1800bb7cb  lea     r8, aW; "w"
0x1800bb7d2  mov     [rsp+6E0h+Stream], 0
0x1800bb7db  lea     rdx, [rsp+6E0h+pszSrc]; FileName
0x1800bb7e0  lea     rcx, [rsp+6E0h+Stream]; Stream
0x1800bb7e5  call    cs:__imp__wfopen_s
0x1800bb7eb  mov     rcx, [rsp+6E0h+Stream]; Stream
0x1800bb7f0  test    rcx, rcx
0x1800bb7f3  jz      short loc_1800BB7FB
0x1800bb7f5  call    cs:__imp_fclose
0x1800bb7fb  lea     rcx, [rbp+5E0h+FileName]; lpFileName
0x1800bb802  call    cs:__imp_GetFileAttributesW
0x1800bb808  cmp     eax, 0FFFFFFFFh
0x1800bb80b  jz      short loc_1800BB83F
0x1800bb80d  lea     r8, aW; "w"
0x1800bb814  mov     [rsp+6E0h+Stream], 0
0x1800bb81d  lea     rdx, [rbp+5E0h+FileName]; FileName
0x1800bb824  lea     rcx, [rsp+6E0h+Stream]; Stream
0x1800bb829  call    cs:__imp__wfopen_s
0x1800bb82f  mov     rcx, [rsp+6E0h+Stream]; Stream
0x1800bb834  test    rcx, rcx
0x1800bb837  jz      short loc_1800BB83F
0x1800bb839  call    cs:__imp_fclose
0x1800bb83f  inc     esi
0x1800bb841  cmp     esi, r15d
0x1800bb844  jb      loc_1800BB645
0x1800bb84a  mov     rcx, [rsp+6E0h+hObject]; hObject
0x1800bb84f  call    cs:__imp_CloseHandle
0x1800bb855  mov     rcx, r14; hMem
0x1800bb858  call    cs:__imp_LocalFree
0x1800bb85e  mov     rcx, rdi; lpMem
0x1800bb861  call    MemoryFree
0x1800bb866  xor     eax, eax
0x1800bb868  mov     rcx, [rbp+5E0h+var_40]
0x1800bb86f  xor     rcx, rsp; StackCookie
0x1800bb872  call    __security_check_cookie
0x1800bb877  mov     rbx, [rsp+6E0h+arg_0]
0x1800bb87f  add     rsp, 6B0h
0x1800bb886  pop     r15
0x1800bb888  pop     r14
0x1800bb88a  pop     r13
0x1800bb88c  pop     r12
0x1800bb88e  pop     rdi
0x1800bb88f  pop     rsi
0x1800bb890  pop     rbp
0x1800bb891  retn
```
