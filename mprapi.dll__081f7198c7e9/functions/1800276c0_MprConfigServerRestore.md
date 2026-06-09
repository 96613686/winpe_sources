# MprConfigServerRestore

- ea: `0x1800276c0`
- end: `0x180027b87`
- name: `MprConfigServerRestore`
- size: `1223`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, LPWSTR lpwsPath)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x1800097e8`
- `0x180017700`
- `0x180017df8`
- `0x180017f30`
- `0x1800276c0`
- `0x180027d5c`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002780e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027864`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b2d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002780e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027864`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180027b2d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027714`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180027714`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800277e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027841`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027aa3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b47`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800277e8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027841`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027aa3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b04`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b33`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180027b47`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800277f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002784f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027ab1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800277f6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002784f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180027ab1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b55`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b12`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b41`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180027b55`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyA` at `0x180027967`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyA` at `0x1800279b8`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyA` at `0x180027a0c`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyA` at `0x180027967`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyA` at `0x1800279b8`
- `api-ms-win-core-registry-l1-1-0!RegRestoreKeyA` at `0x180027a0c`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileA` at `0x180027afe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileA` at `0x180027afe`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180027723`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180027723`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180027749`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180027749`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800277c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800277d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002781c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002782b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027a6f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027a7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027a93`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800277c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800277d4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002781c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002782b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027a6f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027a7e`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180027a93`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800278ef`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x180027952`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800279a8`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800279fd`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x180027a5f`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800278ef`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x180027952`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800279a8`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x1800279fd`
- `api-ms-win-core-privateprofile-l1-1-0!GetPrivateProfileStringA` at `0x180027a5f`

## string_xrefs

- `0x180027a65`: `\ADMIN$\System32\RAS\Router.pbk`
- `0x1800278e8`: `MprConfig`
- `0x18002794b`: `MprConfig`
- `0x1800279a1`: `MprConfig`
- `0x1800279f6`: `MprConfig`
- `0x180027a58`: `MprConfig`
- `0x1800278ac`: `ConfigVersion`

## pseudocode

```c
DWORD __stdcall MprConfigServerRestore(HANDLE hMprConfig, LPWSTR lpwsPath)
{
  DWORD result; // eax
  DWORD v5; // ebx
  const WCHAR *v6; // rcx
  HKEY *v7; // r15
  int v8; // ebx
  size_t v9; // rbx
  HANDLE ProcessHeap; // rax
  char *lpFileName; // r14
  int v12; // ebx
  SIZE_T v13; // rbx
  HANDLE v14; // rax
  CHAR *v15; // rsi
  DWORD v16; // r13d
  int v17; // ebx
  int v18; // eax
  WCHAR *v19; // rcx
  int v20; // ebx
  size_t v21; // r15
  HANDLE v22; // rax
  char *v23; // rbx
  WCHAR *v24; // r9
  const char *v25; // r8
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE v28; // rax
  DWORD nSize; // [rsp+30h] [rbp-D0h] BYREF
  DWORD v30; // [rsp+34h] [rbp-CCh]
  size_t cbDest; // [rsp+38h] [rbp-C8h]
  char pszDest[64]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR Buffer[128]; // [rsp+80h] [rbp-80h] BYREF

  nSize = 128;
  result = MprConfigServerValidateCb(hMprConfig);
  if ( !result )
  {
    EnterCriticalSection(&CfgLock);
    if ( GetComputerNameW(Buffer, &nSize) )
    {
      v6 = (const WCHAR *)*((_QWORD *)hMprConfig + 1);
      if ( v6 && *v6 && lstrcmpiW(v6, Buffer) )
      {
        v5 = 50;
      }
      else
      {
        v7 = (HKEY *)((char *)hMprConfig + 56);
        if ( !*((_QWORD *)hMprConfig + 7) )
          AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"Interfaces", 1, (HKEY *)hMprConfig + 7);
        if ( !*((_QWORD *)hMprConfig + 5) )
          AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"RouterManagers", 1, (HKEY *)hMprConfig + 5);
        if ( !*((_QWORD *)hMprConfig + 3) )
          AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"Parameters", 1, (HKEY *)hMprConfig + 3);
        v8 = lstrlenW(lpwsPath);
        v9 = (unsigned int)(2 * (lstrlenW(L".mpr") + v8) + 2);
        cbDest = v9;
        ProcessHeap = GetProcessHeap();
        lpFileName = (char *)HeapAlloc(ProcessHeap, 0, (unsigned int)v9);
        if ( lpFileName )
        {
          v12 = lstrlenW(lpwsPath);
          v30 = 2 * (lstrlenW(L"RouterManagers") + v12) + 2;
          v13 = (int)v30;
          v14 = GetProcessHeap();
          v15 = (CHAR *)HeapAlloc(v14, 0, v13);
          if ( v15 )
          {
            v5 = EnableBackupPrivilege(1, 18);
            if ( !v5 )
            {
              StringCbPrintfA(lpFileName, cbDest, "%ls%ls", lpwsPath, L".mpr");
              StringCbPrintfA(pszDest, 0x40u, "%ls", L"ConfigVersion");
              v16 = v30;
              GetPrivateProfileStringA("MprConfig", pszDest, c_szEmptyA, v15, v30, lpFileName);
              if ( strcmp(v15, c_szEmptyA) )
              {
                StringCbPrintfA(pszDest, 0x40u, "%ls", L"Parameters");
                GetPrivateProfileStringA("MprConfig", pszDest, c_szEmptyA, v15, v16, lpFileName);
                RegRestoreKeyA(*((HKEY *)hMprConfig + 3), v15, 8u);
                StringCbPrintfA(pszDest, 0x40u, "%ls", L"RouterManagers");
                GetPrivateProfileStringA("MprConfig", pszDest, c_szEmptyA, v15, v16, lpFileName);
                RegRestoreKeyA(*((HKEY *)hMprConfig + 5), v15, 8u);
                StringCbPrintfA(pszDest, 0x40u, "%ls", L"Interfaces");
                GetPrivateProfileStringA("MprConfig", pszDest, c_szEmptyA, v15, v16, lpFileName);
                if ( !RegRestoreKeyA(*v7, v15, 8u) )
                  EnumLanInterfaces(hMprConfig, *v7);
                StringCbPrintfA(pszDest, 0x40u, "%ls", L"Phonebook");
                GetPrivateProfileStringA("MprConfig", pszDest, c_szEmptyA, v15, v16, lpFileName);
                v17 = lstrlenW(L"\\ADMIN$\\System32\\RAS\\Router.pbk");
                v18 = lstrlenW(L"\\\\");
                v19 = (WCHAR *)*((_QWORD *)hMprConfig + 1);
                v20 = v18 + v17;
                if ( !v19 )
                  v19 = Buffer;
                v21 = (unsigned int)(2 * (v20 + lstrlenW(v19)) + 2);
                v22 = GetProcessHeap();
                v23 = (char *)HeapAlloc(v22, 0, (unsigned int)v21);
                if ( v23 )
                {
                  v24 = (WCHAR *)*((_QWORD *)hMprConfig + 1);
                  v25 = "\\\\%ls%ls";
                  if ( v24 )
                  {
                    if ( *v24 == 92 )
                      v25 = "%ls%ls";
                  }
                  else
                  {
                    v24 = Buffer;
                  }
                  StringCbPrintfA(v23, v21, v25, v24, L"\\ADMIN$\\System32\\RAS\\Router.pbk");
                  CopyFileA(v15, v23, 0);
                  v26 = GetProcessHeap();
                  HeapFree(v26, 0, v23);
                }
              }
              v5 = EnableBackupPrivilege(0, 18);
            }
            LeaveCriticalSection(&CfgLock);
            v27 = GetProcessHeap();
            HeapFree(v27, 0, v15);
          }
          else
          {
            LeaveCriticalSection(&CfgLock);
            v5 = 8;
          }
          v28 = GetProcessHeap();
          HeapFree(v28, 0, lpFileName);
          return v5;
        }
        v5 = 8;
      }
    }
    else
    {
      v5 = 1003;
    }
    LeaveCriticalSection(&CfgLock);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800276c0  mov     [rsp-8+arg_10], rbx
0x1800276c5  push    rbp
0x1800276c6  push    rsi
0x1800276c7  push    rdi
0x1800276c8  push    r12
0x1800276ca  push    r13
0x1800276cc  push    r14
0x1800276ce  push    r15
0x1800276d0  lea     rbp, [rsp-90h]
0x1800276d8  sub     rsp, 190h
0x1800276df  mov     rax, cs:__security_cookie
0x1800276e6  xor     rax, rsp
0x1800276e9  mov     [rbp+0C0h+var_40], rax
0x1800276f0  mov     r13, rdx
0x1800276f3  mov     [rsp+1C0h+nSize], 80h
0x1800276fb  mov     rdi, rcx
0x1800276fe  call    MprConfigServerValidateCb
0x180027703  xor     esi, esi
0x180027705  test    eax, eax
0x180027707  jnz     loc_180027B5D
0x18002770d  lea     rcx, CfgLock; lpCriticalSection
0x180027714  call    cs:__imp_EnterCriticalSection
0x18002771a  lea     rdx, [rsp+1C0h+nSize]; nSize
0x18002771f  lea     rcx, [rbp+0C0h+Buffer]; lpBuffer
0x180027723  call    cs:__imp_GetComputerNameW
0x180027729  test    eax, eax
0x18002772b  jnz     short loc_180027737
0x18002772d  mov     ebx, 3EBh
0x180027732  jmp     loc_180027807
0x180027737  mov     rcx, [rdi+8]; lpString1
0x18002773b  test    rcx, rcx
0x18002773e  jz      short loc_18002775D
0x180027740  cmp     [rcx], si
0x180027743  jz      short loc_18002775D
0x180027745  lea     rdx, [rbp+0C0h+Buffer]; lpString2
0x180027749  call    cs:__imp_lstrcmpiW
0x18002774f  test    eax, eax
0x180027751  jz      short loc_18002775D
0x180027753  mov     ebx, 32h ; '2'
0x180027758  jmp     loc_180027807
0x18002775d  lea     r15, [rdi+38h]
0x180027761  cmp     [r15], rsi
0x180027764  jnz     short loc_18002777F
0x180027766  mov     rcx, [rdi+10h]; hKey
0x18002776a  lea     rdx, c_szInterfaces; "Interfaces"
0x180027771  mov     r9, r15
0x180027774  mov     r8d, 1
0x18002777a  call    AccessRouterSubkey
0x18002777f  lea     r12, [rdi+28h]
0x180027783  cmp     [r12], rsi
0x180027787  jnz     short loc_1800277A2
0x180027789  mov     rcx, [rdi+10h]; hKey
0x18002778d  lea     rdx, c_szRouterManagers; "RouterManagers"
0x180027794  mov     r9, r12
0x180027797  mov     r8d, 1
0x18002779d  call    AccessRouterSubkey
0x1800277a2  cmp     [rdi+18h], rsi
0x1800277a6  jnz     short loc_1800277C2
0x1800277a8  mov     rcx, [rdi+10h]; hKey
0x1800277ac  lea     r9, [rdi+18h]
0x1800277b0  mov     r8d, 1
0x1800277b6  lea     rdx, c_szParameters; "Parameters"
0x1800277bd  call    AccessRouterSubkey
0x1800277c2  mov     rcx, r13; lpString
0x1800277c5  call    cs:__imp_lstrlenW
0x1800277cb  lea     rcx, c_szMpr; ".mpr"
0x1800277d2  mov     ebx, eax
0x1800277d4  call    cs:__imp_lstrlenW
0x1800277da  add     ebx, eax
0x1800277dc  lea     ebx, ds:2[rbx*2]
0x1800277e3  mov     [rsp+1C0h+cbDest], rbx
0x1800277e8  call    cs:__imp_GetProcessHeap
0x1800277ee  mov     r8d, ebx; dwBytes
0x1800277f1  xor     edx, edx; dwFlags
0x1800277f3  mov     rcx, rax; hHeap
0x1800277f6  call    cs:__imp_HeapAlloc
0x1800277fc  mov     r14, rax
0x1800277ff  test    rax, rax
0x180027802  jnz     short loc_180027819
0x180027804  lea     ebx, [rax+8]
0x180027807  lea     rcx, CfgLock; lpCriticalSection
0x18002780e  call    cs:__imp_LeaveCriticalSection
0x180027814  jmp     loc_180027B5B
0x180027819  mov     rcx, r13; lpString
0x18002781c  call    cs:__imp_lstrlenW
0x180027822  lea     rcx, c_szRouterManagers; "RouterManagers"
0x180027829  mov     ebx, eax
0x18002782b  call    cs:__imp_lstrlenW
0x180027831  add     ebx, eax
0x180027833  lea     ebx, ds:2[rbx*2]
0x18002783a  mov     [rsp+1C0h+var_18C], ebx
0x18002783e  movsxd  rbx, ebx
0x180027841  call    cs:__imp_GetProcessHeap
0x180027847  mov     r8, rbx; dwBytes
0x18002784a  xor     edx, edx; dwFlags
0x18002784c  mov     rcx, rax; hHeap
0x18002784f  call    cs:__imp_HeapAlloc
0x180027855  mov     rsi, rax
0x180027858  test    rax, rax
0x18002785b  jnz     short loc_180027872
0x18002785d  lea     rcx, CfgLock; lpCriticalSection
0x180027864  call    cs:__imp_LeaveCriticalSection
0x18002786a  lea     ebx, [rsi+8]
0x18002786d  jmp     loc_180027B47
0x180027872  mov     edx, 12h
0x180027877  lea     ecx, [rdx-11h]
0x18002787a  call    EnableBackupPrivilege
0x18002787f  mov     ebx, eax
0x180027881  test    eax, eax
0x180027883  jnz     loc_180027B26
0x180027889  mov     rdx, [rsp+1C0h+cbDest]; cbDest
0x18002788e  lea     rax, c_szMpr; ".mpr"
0x180027895  mov     r9, r13
0x180027898  mov     qword ptr [rsp+1C0h+var_1A0], rax
0x18002789d  lea     r8, aLsLs; "%ls%ls"
0x1800278a4  mov     rcx, r14; pszDest
0x1800278a7  call    StringCbPrintfA
0x1800278ac  lea     r9, c_szConfigVersion; "ConfigVersion"
0x1800278b3  lea     r8, aLs; "%ls"
0x1800278ba  lea     edx, [rbx+40h]; cbDest
0x1800278bd  lea     rcx, [rsp+1C0h+pszDest]; pszDest
0x1800278c2  call    StringCbPrintfA
0x1800278c7  mov     r13d, [rsp+1C0h+var_18C]
0x1800278cc  lea     rbx, c_szEmptyA
0x1800278d3  mov     r8, rbx; lpDefault
0x1800278d6  mov     [rsp+1C0h+lpFileName], r14; lpFileName
0x1800278db  mov     r9, rsi; lpReturnedString
0x1800278de  mov     [rsp+1C0h+var_1A0], r13d; nSize
0x1800278e3  lea     rdx, [rsp+1C0h+pszDest]; lpKeyName
0x1800278e8  lea     rcx, c_szMprConfigA; "MprConfig"
0x1800278ef  call    cs:__imp_GetPrivateProfileStringA
0x1800278f5  mov     r8, rbx
0x1800278f8  mov     rax, rsi
0x1800278fb  sub     r8, rsi
0x1800278fe  movzx   edx, byte ptr [rax]
0x180027901  movzx   ecx, byte ptr [rax+r8]
0x180027906  sub     edx, ecx
0x180027908  jnz     short loc_180027911
0x18002790a  inc     rax
0x18002790d  test    ecx, ecx
0x18002790f  jnz     short loc_1800278FE
0x180027911  test    edx, edx
0x180027913  jz      loc_180027B18
0x180027919  lea     r9, c_szParameters; "Parameters"
0x180027920  mov     edx, 40h ; '@'; cbDest
0x180027925  lea     r8, aLs; "%ls"
0x18002792c  lea     rcx, [rsp+1C0h+pszDest]; pszDest
0x180027931  call    StringCbPrintfA
0x180027936  mov     r9, rsi; lpReturnedString
0x180027939  mov     [rsp+1C0h+lpFileName], r14; lpFileName
0x18002793e  mov     r8, rbx; lpDefault
0x180027941  mov     [rsp+1C0h+var_1A0], r13d; nSize
0x180027946  lea     rdx, [rsp+1C0h+pszDest]; lpKeyName
0x18002794b  lea     rcx, c_szMprConfigA; "MprConfig"
0x180027952  call    cs:__imp_GetPrivateProfileStringA
0x180027958  mov     rcx, [rdi+18h]; hKey
0x18002795c  mov     ebx, 8
0x180027961  mov     r8d, ebx; dwFlags
0x180027964  mov     rdx, rsi; lpFile
0x180027967  call    cs:__imp_RegRestoreKeyA
0x18002796d  lea     r9, c_szRouterManagers; "RouterManagers"
0x180027974  lea     r8, aLs; "%ls"
0x18002797b  lea     edx, [rbx+38h]; cbDest
0x18002797e  lea     rcx, [rsp+1C0h+pszDest]; pszDest
0x180027983  call    StringCbPrintfA
0x180027988  mov     r9, rsi; lpReturnedString
0x18002798b  mov     [rsp+1C0h+lpFileName], r14; lpFileName
0x180027990  lea     r8, c_szEmptyA; lpDefault
0x180027997  mov     [rsp+1C0h+var_1A0], r13d; nSize
0x18002799c  lea     rdx, [rsp+1C0h+pszDest]; lpKeyName
0x1800279a1  lea     rcx, c_szMprConfigA; "MprConfig"
0x1800279a8  call    cs:__imp_GetPrivateProfileStringA
0x1800279ae  mov     rcx, [r12]; hKey
0x1800279b2  mov     r8d, ebx; dwFlags
0x1800279b5  mov     rdx, rsi; lpFile
0x1800279b8  call    cs:__imp_RegRestoreKeyA
0x1800279be  lea     r12d, [rbx+38h]
0x1800279c2  mov     edx, r12d; cbDest
0x1800279c5  lea     r9, c_szInterfaces; "Interfaces"
0x1800279cc  lea     r8, aLs; "%ls"
0x1800279d3  lea     rcx, [rsp+1C0h+pszDest]; pszDest
0x1800279d8  call    StringCbPrintfA
0x1800279dd  mov     r9, rsi; lpReturnedString
0x1800279e0  mov     [rsp+1C0h+lpFileName], r14; lpFileName
0x1800279e5  lea     r8, c_szEmptyA; lpDefault
0x1800279ec  mov     [rsp+1C0h+var_1A0], r13d; nSize
0x1800279f1  lea     rdx, [rsp+1C0h+pszDest]; lpKeyName
0x1800279f6  lea     rcx, c_szMprConfigA; "MprConfig"
0x1800279fd  call    cs:__imp_GetPrivateProfileStringA
0x180027a03  mov     rcx, [r15]; hKey
0x180027a06  mov     r8d, ebx; dwFlags
0x180027a09  mov     rdx, rsi; lpFile
0x180027a0c  call    cs:__imp_RegRestoreKeyA
0x180027a12  test    eax, eax
0x180027a14  jnz     short loc_180027A24
0x180027a16  mov     rdx, [r15]; hKey
0x180027a19  xor     r9d, r9d
0x180027a1c  mov     rcx, rdi; hMprConfig
0x180027a1f  call    EnumLanInterfaces
0x180027a24  lea     r9, c_szPhonebook; "Phonebook"
0x180027a2b  mov     rdx, r12; cbDest
0x180027a2e  lea     r8, aLs; "%ls"
0x180027a35  lea     rcx, [rsp+1C0h+pszDest]; pszDest
0x180027a3a  call    StringCbPrintfA
0x180027a3f  mov     r9, rsi; lpReturnedString
0x180027a42  mov     [rsp+1C0h+lpFileName], r14; lpFileName
0x180027a47  lea     r8, c_szEmptyA; lpDefault
0x180027a4e  mov     [rsp+1C0h+var_1A0], r13d; nSize
0x180027a53  lea     rdx, [rsp+1C0h+pszDest]; lpKeyName
0x180027a58  lea     rcx, c_szMprConfigA; "MprConfig"
0x180027a5f  call    cs:__imp_GetPrivateProfileStringA
0x180027a65  lea     r12, c_szRouterPbkPath; "\\ADMIN$\\System32\\RAS\\Router.pbk"
0x180027a6c  mov     rcx, r12; lpString
0x180027a6f  call    cs:__imp_lstrlenW
0x180027a75  lea     rcx, c_szUncPrefix; "\\\\"
0x180027a7c  mov     ebx, eax
0x180027a7e  call    cs:__imp_lstrlenW
0x180027a84  mov     rcx, [rdi+8]
0x180027a88  add     ebx, eax
0x180027a8a  test    rcx, rcx
0x180027a8d  jnz     short loc_180027A93
0x180027a8f  lea     rcx, [rbp+0C0h+Buffer]; lpString
0x180027a93  call    cs:__imp_lstrlenW
0x180027a99  add     eax, ebx
0x180027a9b  lea     r15d, ds:2[rax*2]
0x180027aa3  call    cs:__imp_GetProcessHeap
0x180027aa9  mov     r8d, r15d; dwBytes
0x180027aac  xor     edx, edx; dwFlags
0x180027aae  mov     rcx, rax; hHeap
0x180027ab1  call    cs:__imp_HeapAlloc
0x180027ab7  mov     rbx, rax
0x180027aba  test    rax, rax
0x180027abd  jz      short loc_180027B18
0x180027abf  mov     r9, [rdi+8]
0x180027ac3  lea     r8, aLsLs_0; "\\\\%ls%ls"
0x180027aca  test    r9, r9
0x180027acd  jz      short loc_180027AE1
0x180027acf  cmp     word ptr [r9], 5Ch ; '\'
0x180027ad4  lea     rax, aLsLs; "%ls%ls"
0x180027adb  cmovz   r8, rax
0x180027adf  jmp     short loc_180027AE5
0x180027ae1  lea     r9, [rbp+0C0h+Buffer]
0x180027ae5  mov     rdx, r15; cbDest
0x180027ae8  mov     qword ptr [rsp+1C0h+var_1A0], r12
0x180027aed  mov     rcx, rbx; pszDest
0x180027af0  call    StringCbPrintfA
0x180027af5  xor     r8d, r8d; bFailIfExists
0x180027af8  mov     rdx, rbx; lpNewFileName
0x180027afb  mov     rcx, rsi; lpExistingFileName
0x180027afe  call    cs:__imp_CopyFileA
0x180027b04  call    cs:__imp_GetProcessHeap
0x180027b0a  mov     r8, rbx; lpMem
0x180027b0d  xor     edx, edx; dwFlags
0x180027b0f  mov     rcx, rax; hHeap
0x180027b12  call    cs:__imp_HeapFree
0x180027b18  mov     edx, 12h
0x180027b1d  xor     ecx, ecx
0x180027b1f  call    EnableBackupPrivilege
0x180027b24  mov     ebx, eax
0x180027b26  lea     rcx, CfgLock; lpCriticalSection
0x180027b2d  call    cs:__imp_LeaveCriticalSection
0x180027b33  call    cs:__imp_GetProcessHeap
0x180027b39  mov     r8, rsi; lpMem
0x180027b3c  xor     edx, edx; dwFlags
0x180027b3e  mov     rcx, rax; hHeap
0x180027b41  call    cs:__imp_HeapFree
0x180027b47  call    cs:__imp_GetProcessHeap
0x180027b4d  mov     r8, r14; lpMem
0x180027b50  xor     edx, edx; dwFlags
0x180027b52  mov     rcx, rax; hHeap
0x180027b55  call    cs:__imp_HeapFree
0x180027b5b  mov     eax, ebx
0x180027b5d  mov     rcx, [rbp+0C0h+var_40]
0x180027b64  xor     rcx, rsp; StackCookie
0x180027b67  call    __security_check_cookie
0x180027b6c  mov     rbx, [rsp+1C0h+arg_10]
0x180027b74  add     rsp, 190h
0x180027b7b  pop     r15
0x180027b7d  pop     r14
0x180027b7f  pop     r13
0x180027b81  pop     r12
0x180027b83  pop     rdi
0x180027b84  pop     rsi
0x180027b85  pop     rbp
0x180027b86  retn
```
