# DisableAutoTracingForSubkeys

- ea: `0x1800aa31c`
- end: `0x1800aa58d`
- name: `DisableAutoTracingForSubkeys`
- size: `625`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800aa18c`

## callees

- `0x180056178`
- `0x1800aa31c`
- `0x1800ab634`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa38c`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800aa38c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa378`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800aa378`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa47f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800aa47f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa500`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa531`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa500`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800aa531`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa542`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800aa542`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800aa3d9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800aa3d9`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa4be`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800aa4be`

## pseudocode

```c
__int64 __fastcall DisableAutoTracingForSubkeys(DWORD a1, DWORD a2, HKEY a3)
{
  unsigned int v3; // ebx
  HANDLE ProcessHeap; // rax
  wchar_t *v8; // rdi
  DWORD i; // ebx
  const WCHAR *v11; // r8
  __int64 v12; // rdx
  wchar_t *v13; // rax
  __int64 v14; // rcx
  wchar_t *v15; // rcx
  BYTE Data[8]; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData; // [rsp+54h] [rbp-ACh] BYREF
  BYTE v20[8]; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[264]; // [rsp+60h] [rbp-A0h] BYREF

  v3 = 2 * a2;
  cchName = 0;
  *(_DWORD *)v20 = 0;
  *(_DWORD *)Data = 0;
  phkResult = 0;
  cbData = 4;
  ProcessHeap = GetProcessHeap();
  v8 = (wchar_t *)HeapAlloc(ProcessHeap, 0, v3);
  if ( !v8 )
    return 8;
  for ( i = 0; i < a1; ++i )
  {
    cchName = a2;
    if ( !RegEnumKeyExW(a3, i, v8, &cchName, 0, 0, 0, 0) )
    {
      v11 = L"SOFTWARE\\Microsoft\\Tracing";
      v12 = 261;
      v13 = pszDest;
      v14 = 2147483646;
      do
      {
        if ( !v14 )
          break;
        if ( !*v11 )
          break;
        *v13++ = *v11++;
        --v14;
        --v12;
      }
      while ( v12 );
      v15 = v13 - 1;
      if ( v12 )
        v15 = v13;
      *v15 = 0;
      StringCchCatW(pszDest, 0x105u, L"\\");
      StringCchCatW(pszDest, 0x105u, v8);
      if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x2011Fu, &phkResult) )
      {
        cbData = 4;
        if ( !RegQueryValueExW(phkResult, L"EnableAutoFileTracing", 0, 0, Data, &cbData) && *(_DWORD *)Data == 1 )
        {
          *(_DWORD *)v20 = 0;
          *(_DWORD *)Data = 0;
          if ( !RegSetValueExW(phkResult, L"EnableAutoFileTracing", 0, 4u, Data, 4u) )
            RegSetValueExW(phkResult, L"EnableFileTracing", 0, 4u, v20, 4u);
        }
        RegCloseKey(phkResult);
      }
    }
  }
  MprCommonFree(v8);
  return 0;
}

```

## disassembly

```asm
0x1800aa31c  mov     [rsp-8+arg_0], rbx
0x1800aa321  push    rbp
0x1800aa322  push    rsi
0x1800aa323  push    rdi
0x1800aa324  push    r12
0x1800aa326  push    r13
0x1800aa328  push    r14
0x1800aa32a  push    r15
0x1800aa32c  lea     rbp, [rsp-180h]
0x1800aa334  sub     rsp, 280h
0x1800aa33b  mov     rax, cs:__security_cookie
0x1800aa342  xor     rax, rsp
0x1800aa345  mov     [rbp+1B0h+var_40], rax
0x1800aa34c  xor     r12d, r12d
0x1800aa34f  lea     ebx, [rdx+rdx]
0x1800aa352  mov     r15, r8
0x1800aa355  mov     [rsp+2B0h+cchName], r12d
0x1800aa35a  mov     r14d, edx
0x1800aa35d  mov     dword ptr [rsp+2B0h+var_258], r12d
0x1800aa362  mov     esi, ecx
0x1800aa364  mov     dword ptr [rsp+2B0h+Data], r12d
0x1800aa369  lea     r13d, [r12+4]
0x1800aa36e  mov     [rsp+2B0h+phkResult], r12
0x1800aa373  mov     [rsp+2B0h+cbData], r13d
0x1800aa378  call    cs:__imp_GetProcessHeap
0x1800aa37f  nop     dword ptr [rax+rax+00h]
0x1800aa384  mov     r8d, ebx; dwBytes
0x1800aa387  xor     edx, edx; dwFlags
0x1800aa389  mov     rcx, rax; hHeap
0x1800aa38c  call    cs:__imp_HeapAlloc
0x1800aa393  nop     dword ptr [rax+rax+00h]
0x1800aa398  mov     rdi, rax
0x1800aa39b  test    rax, rax
0x1800aa39e  jnz     short loc_1800AA3A8
0x1800aa3a0  lea     eax, [rdi+8]
0x1800aa3a3  jmp     loc_1800AA562
0x1800aa3a8  mov     ebx, r12d
0x1800aa3ab  test    esi, esi
0x1800aa3ad  jz      loc_1800AA558
0x1800aa3b3  mov     [rsp+2B0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x1800aa3b8  lea     r9, [rsp+2B0h+cchName]; lpcchName
0x1800aa3bd  mov     [rsp+2B0h+lpcchClass], r12; lpcchClass
0x1800aa3c2  mov     r8, rdi; lpName
0x1800aa3c5  mov     [rsp+2B0h+lpClass], r12; lpClass
0x1800aa3ca  mov     edx, ebx; dwIndex
0x1800aa3cc  mov     rcx, r15; hKey
0x1800aa3cf  mov     [rsp+2B0h+lpReserved], r12; lpReserved
0x1800aa3d4  mov     [rsp+2B0h+cchName], r14d
0x1800aa3d9  call    cs:__imp_RegEnumKeyExW
0x1800aa3e0  nop     dword ptr [rax+rax+00h]
0x1800aa3e5  test    eax, eax
0x1800aa3e7  jnz     loc_1800AA54E
0x1800aa3ed  mov     r10d, 105h
0x1800aa3f3  lea     r8, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Tracing"
0x1800aa3fa  mov     edx, r10d
0x1800aa3fd  lea     rax, [rsp+2B0h+pszDest]
0x1800aa402  mov     ecx, 7FFFFFFEh
0x1800aa407  test    rcx, rcx
0x1800aa40a  jz      short loc_1800AA42B
0x1800aa40c  movzx   r9d, word ptr [r8]
0x1800aa410  test    r9w, r9w
0x1800aa414  jz      short loc_1800AA42B
0x1800aa416  mov     [rax], r9w
0x1800aa41a  add     r8, 2
0x1800aa41e  add     rax, 2
0x1800aa422  dec     rcx
0x1800aa425  sub     rdx, 1
0x1800aa429  jnz     short loc_1800AA407
0x1800aa42b  test    rdx, rdx
0x1800aa42e  lea     rcx, [rax-2]
0x1800aa432  lea     r8, Source; "\\"
0x1800aa439  mov     rdx, r10; cchDest
0x1800aa43c  cmovnz  rcx, rax
0x1800aa440  mov     [rcx], r12w
0x1800aa444  lea     rcx, [rsp+2B0h+pszDest]; pszDest
0x1800aa449  call    StringCchCatW
0x1800aa44e  mov     r8, rdi; pszSrc
0x1800aa451  lea     rcx, [rsp+2B0h+pszDest]; pszDest
0x1800aa456  mov     edx, 105h; cchDest
0x1800aa45b  call    StringCchCatW
0x1800aa460  lea     rax, [rsp+2B0h+phkResult]
0x1800aa465  mov     r9d, 2011Fh; samDesired
0x1800aa46b  xor     r8d, r8d; ulOptions
0x1800aa46e  mov     [rsp+2B0h+lpReserved], rax; phkResult
0x1800aa473  lea     rdx, [rsp+2B0h+pszDest]; lpSubKey
0x1800aa478  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800aa47f  call    cs:__imp_RegOpenKeyExW
0x1800aa486  nop     dword ptr [rax+rax+00h]
0x1800aa48b  test    eax, eax
0x1800aa48d  jnz     loc_1800AA54E
0x1800aa493  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x1800aa498  lea     rax, [rsp+2B0h+cbData]
0x1800aa49d  mov     [rsp+2B0h+lpClass], rax; lpcbData
0x1800aa4a2  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800aa4a9  lea     rax, [rsp+2B0h+Data]
0x1800aa4ae  mov     [rsp+2B0h+cbData], r13d
0x1800aa4b3  xor     r9d, r9d; lpType
0x1800aa4b6  mov     [rsp+2B0h+lpReserved], rax; lpData
0x1800aa4bb  xor     r8d, r8d; lpReserved
0x1800aa4be  call    cs:__imp_RegQueryValueExW
0x1800aa4c5  nop     dword ptr [rax+rax+00h]
0x1800aa4ca  test    eax, eax
0x1800aa4cc  jnz     short loc_1800AA53D
0x1800aa4ce  cmp     dword ptr [rsp+2B0h+Data], 1
0x1800aa4d3  jnz     short loc_1800AA53D
0x1800aa4d5  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x1800aa4da  lea     rax, [rsp+2B0h+Data]
0x1800aa4df  mov     dword ptr [rsp+2B0h+lpClass], r13d; cbData
0x1800aa4e4  lea     rdx, aEnableautofile; "EnableAutoFileTracing"
0x1800aa4eb  mov     r9d, r13d; dwType
0x1800aa4ee  mov     [rsp+2B0h+lpReserved], rax; lpData
0x1800aa4f3  xor     r8d, r8d; Reserved
0x1800aa4f6  mov     dword ptr [rsp+2B0h+var_258], r12d
0x1800aa4fb  mov     dword ptr [rsp+2B0h+Data], r12d
0x1800aa500  call    cs:__imp_RegSetValueExW
0x1800aa507  nop     dword ptr [rax+rax+00h]
0x1800aa50c  test    eax, eax
0x1800aa50e  jnz     short loc_1800AA53D
0x1800aa510  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x1800aa515  lea     rax, [rsp+2B0h+var_258]
0x1800aa51a  mov     dword ptr [rsp+2B0h+lpClass], r13d; cbData
0x1800aa51f  lea     rdx, aEnablefiletrac; "EnableFileTracing"
0x1800aa526  mov     r9d, r13d; dwType
0x1800aa529  mov     [rsp+2B0h+lpReserved], rax; lpData
0x1800aa52e  xor     r8d, r8d; Reserved
0x1800aa531  call    cs:__imp_RegSetValueExW
0x1800aa538  nop     dword ptr [rax+rax+00h]
0x1800aa53d  mov     rcx, [rsp+2B0h+phkResult]; hKey
0x1800aa542  call    cs:__imp_RegCloseKey
0x1800aa549  nop     dword ptr [rax+rax+00h]
0x1800aa54e  inc     ebx
0x1800aa550  cmp     ebx, esi
0x1800aa552  jb      loc_1800AA3B3
0x1800aa558  mov     rcx, rdi; lpMem
0x1800aa55b  call    MprCommonFree
0x1800aa560  xor     eax, eax
0x1800aa562  mov     rcx, [rbp+1B0h+var_40]
0x1800aa569  xor     rcx, rsp; StackCookie
0x1800aa56c  call    __security_check_cookie
0x1800aa571  mov     rbx, [rsp+2B0h+arg_0]
0x1800aa579  add     rsp, 280h
0x1800aa580  pop     r15
0x1800aa582  pop     r14
0x1800aa584  pop     r13
0x1800aa586  pop     r12
0x1800aa588  pop     rdi
0x1800aa589  pop     rsi
0x1800aa58a  pop     rbp
0x1800aa58b  retn
```
