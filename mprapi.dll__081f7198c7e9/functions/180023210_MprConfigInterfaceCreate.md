# MprConfigInterfaceCreate

- ea: `0x180023210`
- end: `0x1800236d9`
- name: `MprConfigInterfaceCreate`
- size: `1225`
- prototype: `DWORD __stdcall(HANDLE hMprConfig, DWORD dwLevel, LPBYTE lpbBuffer, HANDLE *phRouterInterface)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x180035f84`

## callees

- `0x180009868`
- `0x18000a070`
- `0x180017700`
- `0x180017960`
- `0x1800184d0`
- `0x180022324`
- `0x180023210`
- `0x180023e40`
- `0x180027d5c`
- `0x1800291b4`
- `0x18002998c`
- `0x18002ecc4`
- `0x180051112`
- `0x18005112a`
- `0x180051160`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800235a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800235a1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800232c5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800232c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800233db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180023327`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800233db`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002333a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800233e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18002333a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800233e9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800234e3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800234e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180023489`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180023489`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800235db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002360d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002363f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002367f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800235db`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002360d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002363f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002367f`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002353a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002353a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180023301`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180023301`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800235b1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x1800235b1`

## pseudocode

```c
DWORD __stdcall MprConfigInterfaceCreate(HANDLE hMprConfig, DWORD dwLevel, LPBYTE lpbBuffer, HANDLE *phRouterInterface)
{
  LPBYTE v7; // r12
  DWORD result; // eax
  LSTATUS v9; // ebx
  _QWORD *v10; // r14
  int v11; // eax
  LPCWSTR *v12; // rbx
  HANDLE ProcessHeap; // rax
  char *v14; // rax
  char *v15; // rdi
  __int64 v16; // rcx
  DWORD SizeOfMultiSz; // eax
  DWORD v18; // r12d
  HANDLE v19; // rax
  void *v20; // rax
  PWSTR v21; // rax
  HKEY *v22; // r12
  HKEY *v23; // r13
  LSTATUS i; // eax
  DWORD v25; // r9d
  _QWORD *v26; // rcx
  PWSTR v27; // rax
  int v28; // eax
  const BYTE *v29; // rax
  DWORD cSubKeys; // [rsp+60h] [rbp-19h] BYREF
  DWORD dwDisposition; // [rsp+64h] [rbp-15h] BYREF
  int v32; // [rsp+68h] [rbp-11h] BYREF
  LSTATUS Interfaces; // [rsp+6Ch] [rbp-Dh] BYREF
  DWORD v34; // [rsp+70h] [rbp-9h]
  DWORD cbData; // [rsp+74h] [rbp-5h]
  HANDLE *v36; // [rsp+78h] [rbp-1h]
  wchar_t pszDest[12]; // [rsp+80h] [rbp+7h] BYREF

  v36 = phRouterInterface;
  v34 = dwLevel;
  v32 = 0;
  if ( dwLevel > 1 || !lpbBuffer || !phRouterInterface )
    return 87;
  v7 = lpbBuffer + 532;
  if ( *((_DWORD *)lpbBuffer + 133) == 6 )
    return 0;
  *phRouterInterface = 0;
  result = MprConfigServerValidateCb(hMprConfig);
  if ( !result )
  {
    if ( (unsigned int)(*(_DWORD *)v7 - 3) > 2 )
    {
      result = CheckMultiTenancy(hMprConfig, &v32);
      if ( result )
        return result;
      if ( v32 )
        return 50;
    }
    EnterCriticalSection(&CfgLock);
    Interfaces = LoadInterfaces(0, hMprConfig);
    v9 = Interfaces;
    if ( Interfaces )
      goto LABEL_46;
    v10 = (_QWORD *)*((_QWORD *)hMprConfig + 13);
    v11 = 1;
    if ( v10 != (_QWORD *)((char *)hMprConfig + 104) )
    {
      do
      {
        v12 = (LPCWSTR *)(v10 - 8);
        if ( !*((_DWORD *)v10 - 2) )
        {
          v11 = lstrcmpiW(*v12, (LPCWSTR)lpbBuffer);
          if ( v11 >= 0 )
            break;
        }
        v10 = (_QWORD *)*v10;
      }
      while ( v10 != (_QWORD *)((char *)hMprConfig + 104) );
      if ( v12 && !v11 )
      {
        *phRouterInterface = v12;
LABEL_19:
        v9 = 0;
LABEL_46:
        LeaveCriticalSection(&CfgLock);
        return v9;
      }
    }
    ProcessHeap = GetProcessHeap();
    v14 = (char *)HeapAlloc(ProcessHeap, 0, 0x310u);
    v15 = v14;
    if ( !v14 )
    {
      v9 = 8;
      goto LABEL_46;
    }
    dwDisposition = 0;
    cSubKeys = 0;
    memset_0(v14, 0, 0x310u);
    *((_QWORD *)v15 + 11) = v15 + 80;
    *((_QWORD *)v15 + 10) = v15 + 80;
    *((_DWORD *)v15 + 6) = *(_DWORD *)v7;
    *((_DWORD *)v15 + 7) = *((_DWORD *)lpbBuffer + 132);
    if ( (unsigned int)(*(_DWORD *)v7 - 3) <= 1 && !*((_DWORD *)lpbBuffer + 132) )
    {
      v9 = 87;
      goto LABEL_25;
    }
    cbData = 0;
    if ( v34 == 1 )
    {
      v16 = *((_QWORD *)lpbBuffer + 69);
      if ( v16 )
      {
        SizeOfMultiSz = MprUtilGetSizeOfMultiSz(v16, 2000, &Interfaces);
        v9 = Interfaces;
        v18 = SizeOfMultiSz;
        cbData = SizeOfMultiSz;
        if ( Interfaces )
          goto LABEL_25;
        v19 = GetProcessHeap();
        v20 = HeapAlloc(v19, 0, v18);
        *((_QWORD *)v15 + 4) = v20;
        if ( !v20 )
          goto LABEL_32;
        memcpy_0(v20, *((const void **)lpbBuffer + 69), v18);
      }
    }
    v21 = StrDupW((PCWSTR)lpbBuffer);
    *(_QWORD *)v15 = v21;
    if ( v21 )
    {
      v22 = (HKEY *)((char *)hMprConfig + 56);
      if ( *((_QWORD *)hMprConfig + 7) || (v9 = AccessRouterSubkey(*((HKEY *)hMprConfig + 2), L"Interfaces")) == 0 )
      {
        v9 = RegQueryInfoKeyW(*v22, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
        if ( !v9 )
        {
          StringCbPrintfW(pszDest, 0x18u, L"%d", cSubKeys);
          v23 = (HKEY *)(v15 + 40);
          for ( i = RegCreateKeyExW(*v22, pszDest, 0, 0, 0, 0x3001Fu, 0, (PHKEY)v15 + 5, &dwDisposition);
                ;
                i = RegCreateKeyExW(*v22, pszDest, 0, 0, 0, 0x3001Fu, 0, (PHKEY)v15 + 5, &dwDisposition) )
          {
            v9 = i;
            if ( i )
              goto LABEL_25;
            if ( dwDisposition == 1 )
              break;
            RegCloseKey(*v23);
            v25 = cSubKeys + 1;
            *v23 = 0;
            cSubKeys = v25;
            StringCbPrintfW(pszDest, 0x18u, L"%d");
          }
          v26 = (_QWORD *)v10[1];
          if ( (_QWORD *)*v26 != v10 )
            __fastfail(3u);
          *((_QWORD *)v15 + 8) = v10;
          *((_QWORD *)v15 + 9) = v26;
          *v26 = v15 + 64;
          v10[1] = v15 + 64;
          UpdateTimeStamp(*v22, (PFILETIME)hMprConfig + 8);
          v27 = StrDupW(pszDest);
          *((_QWORD *)v15 + 2) = v27;
          if ( v27 )
          {
            v28 = lstrlenW((LPCWSTR)lpbBuffer);
            v9 = RegSetValueExW(*v23, L"InterfaceName", 0, 1u, lpbBuffer, 2 * v28 + 2);
            if ( !v9 )
            {
              v9 = RegSetValueExW(*v23, L"Type", 0, 4u, lpbBuffer + 532, 4u);
              if ( !v9 )
              {
                v9 = RegSetValueExW(*v23, L"Enabled", 0, 4u, lpbBuffer + 528, 4u);
                if ( !v9 )
                {
                  if ( v34 == 1 && (v29 = (const BYTE *)*((_QWORD *)lpbBuffer + 69)) != 0 )
                    v9 = RegSetValueExW(*v23, L"DialoutHours", 0, 7u, v29, cbData);
                  else
                    v9 = 0;
                  if ( !v9 )
                  {
                    GuidMapCleanup(*((LPVOID *)hMprConfig + 16));
                    *v36 = v15;
                    goto LABEL_19;
                  }
                }
              }
            }
          }
          else
          {
            v9 = 8;
          }
          MprConfigInterfaceDelete(hMprConfig, v15);
          goto LABEL_46;
        }
      }
LABEL_25:
      FreeInterface(v15);
      goto LABEL_46;
    }
LABEL_32:
    v9 = 8;
    goto LABEL_25;
  }
  return result;
}

```

## disassembly

```asm
0x180023210  mov     [rsp-8+arg_8], rbx
0x180023215  push    rbp
0x180023216  push    rsi
0x180023217  push    rdi
0x180023218  push    r12
0x18002321a  push    r13
0x18002321c  push    r14
0x18002321e  push    r15
0x180023220  lea     rbp, [rsp-27h]
0x180023225  sub     rsp, 0A0h
0x18002322c  mov     rax, cs:__security_cookie
0x180023233  xor     rax, rsp
0x180023236  mov     [rbp+57h+var_38], rax
0x18002323a  xor     edi, edi
0x18002323c  mov     [rbp+57h+var_58], r9
0x180023240  mov     [rbp+57h+var_60], edx
0x180023243  mov     r13, r9
0x180023246  mov     [rbp+57h+var_68], edi
0x180023249  mov     rsi, r8
0x18002324c  mov     r15, rcx
0x18002324f  cmp     edx, 1
0x180023252  ja      loc_1800236AD
0x180023258  test    r8, r8
0x18002325b  jz      loc_1800236AD
0x180023261  test    r9, r9
0x180023264  jz      loc_1800236AD
0x18002326a  lea     r12, [r8+214h]
0x180023271  cmp     dword ptr [r12], 6
0x180023276  jnz     short loc_18002327F
0x180023278  xor     eax, eax
0x18002327a  jmp     loc_1800236B2
0x18002327f  mov     [r9], rdi
0x180023282  call    MprConfigServerValidateCb
0x180023287  test    eax, eax
0x180023289  jnz     loc_1800236B2
0x18002328f  mov     eax, [r12]
0x180023293  sub     eax, 3
0x180023296  cmp     eax, 2
0x180023299  jbe     short loc_1800232BE
0x18002329b  lea     rdx, [rbp+57h+var_68]
0x18002329f  mov     rcx, r15
0x1800232a2  call    CheckMultiTenancy
0x1800232a7  test    eax, eax
0x1800232a9  jnz     loc_1800236B2
0x1800232af  cmp     [rbp+57h+var_68], edi
0x1800232b2  jz      short loc_1800232BE
0x1800232b4  mov     eax, 32h ; '2'
0x1800232b9  jmp     loc_1800236B2
0x1800232be  lea     rcx, CfgLock; lpCriticalSection
0x1800232c5  call    cs:__imp_EnterCriticalSection
0x1800232cb  mov     rdx, r15
0x1800232ce  xor     ecx, ecx
0x1800232d0  call    LoadInterfaces
0x1800232d5  mov     [rbp+57h+var_64], eax
0x1800232d8  mov     ebx, eax
0x1800232da  test    eax, eax
0x1800232dc  jnz     loc_18002359A
0x1800232e2  lea     rdi, [r15+68h]
0x1800232e6  mov     r14, [rdi]
0x1800232e9  lea     eax, [rbx+1]
0x1800232ec  cmp     r14, rdi
0x1800232ef  jz      short loc_180023327
0x1800232f1  lea     rbx, [r14-40h]
0x1800232f5  cmp     dword ptr [rbx+38h], 0
0x1800232f9  jnz     short loc_18002330B
0x1800232fb  mov     rcx, [rbx]; lpString1
0x1800232fe  mov     rdx, rsi; lpString2
0x180023301  call    cs:__imp_lstrcmpiW
0x180023307  test    eax, eax
0x180023309  jns     short loc_180023313
0x18002330b  mov     r14, [r14]
0x18002330e  cmp     r14, rdi
0x180023311  jnz     short loc_1800232F1
0x180023313  test    rbx, rbx
0x180023316  jz      short loc_180023327
0x180023318  test    eax, eax
0x18002331a  jnz     short loc_180023327
0x18002331c  mov     [r13+0], rbx
0x180023320  xor     ebx, ebx
0x180023322  jmp     loc_18002359A
0x180023327  call    cs:__imp_GetProcessHeap
0x18002332d  mov     ebx, 310h
0x180023332  xor     edx, edx; dwFlags
0x180023334  mov     rcx, rax; hHeap
0x180023337  mov     r8d, ebx; dwBytes
0x18002333a  call    cs:__imp_HeapAlloc
0x180023340  xor     r13d, r13d
0x180023343  mov     rdi, rax
0x180023346  test    rax, rax
0x180023349  jnz     short loc_180023353
0x18002334b  lea     ebx, [rax+8]
0x18002334e  jmp     loc_18002359A
0x180023353  mov     r8, rbx; Size
0x180023356  mov     [rbp+57h+dwDisposition], r13d
0x18002335a  xor     edx, edx; Val
0x18002335c  mov     [rbp+57h+cSubKeys], r13d
0x180023360  mov     rcx, rdi; void *
0x180023363  call    memset_0
0x180023368  lea     rax, [rdi+50h]
0x18002336c  mov     [rax+8], rax
0x180023370  lea     rcx, [rsi+210h]
0x180023377  mov     [rax], rax
0x18002337a  mov     eax, [r12]
0x18002337e  mov     [rdi+18h], eax
0x180023381  mov     eax, [rcx]
0x180023383  mov     [rdi+1Ch], eax
0x180023386  mov     eax, [r12]
0x18002338a  sub     eax, 3
0x18002338d  cmp     eax, 1
0x180023390  ja      short loc_1800233A9
0x180023392  cmp     [rcx], r13d
0x180023395  jnz     short loc_1800233A9
0x180023397  mov     ebx, 57h ; 'W'
0x18002339c  mov     rcx, rdi
0x18002339f  call    FreeInterface
0x1800233a4  jmp     loc_18002359A
0x1800233a9  cmp     [rbp+57h+var_60], 1
0x1800233ad  mov     [rbp+57h+cbData], r13d
0x1800233b1  jnz     short loc_18002340A
0x1800233b3  mov     rcx, [rsi+228h]
0x1800233ba  test    rcx, rcx
0x1800233bd  jz      short loc_18002340A
0x1800233bf  lea     r8, [rbp+57h+var_64]
0x1800233c3  mov     edx, 7D0h
0x1800233c8  call    MprUtilGetSizeOfMultiSz
0x1800233cd  mov     ebx, [rbp+57h+var_64]
0x1800233d0  mov     r12d, eax
0x1800233d3  mov     [rbp+57h+cbData], r12d
0x1800233d7  test    ebx, ebx
0x1800233d9  jnz     short loc_18002339C
0x1800233db  call    cs:__imp_GetProcessHeap
0x1800233e1  mov     r8d, r12d; dwBytes
0x1800233e4  xor     edx, edx; dwFlags
0x1800233e6  mov     rcx, rax; hHeap
0x1800233e9  call    cs:__imp_HeapAlloc
0x1800233ef  mov     [rdi+20h], rax
0x1800233f3  test    rax, rax
0x1800233f6  jz      short loc_18002341A
0x1800233f8  mov     rdx, [rsi+228h]; Src
0x1800233ff  mov     r8d, r12d; Size
0x180023402  mov     rcx, rax; void *
0x180023405  call    memcpy_0
0x18002340a  mov     rcx, rsi; pszSrch
0x18002340d  call    StrDupW
0x180023412  mov     [rdi], rax
0x180023415  test    rax, rax
0x180023418  jnz     short loc_180023424
0x18002341a  mov     ebx, 8
0x18002341f  jmp     loc_18002339C
0x180023424  lea     r12, [r15+38h]
0x180023428  cmp     [r12], r13
0x18002342c  jnz     short loc_180023451
0x18002342e  mov     rcx, [r15+10h]; hKey
0x180023432  lea     rdx, c_szInterfaces; "Interfaces"
0x180023439  mov     r9, r12
0x18002343c  mov     r8d, 1
0x180023442  call    AccessRouterSubkey
0x180023447  mov     ebx, eax
0x180023449  test    eax, eax
0x18002344b  jnz     loc_18002339C
0x180023451  mov     rcx, [r12]; hKey
0x180023455  lea     rax, [rbp+57h+cSubKeys]
0x180023459  mov     [rsp+0D0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18002345e  xor     r9d, r9d; lpReserved
0x180023461  mov     [rsp+0D0h+lpcbSecurityDescriptor], r13; lpcbSecurityDescriptor
0x180023466  xor     r8d, r8d; lpcchClass
0x180023469  mov     [rsp+0D0h+lpcbMaxValueLen], r13; lpcbMaxValueLen
0x18002346e  xor     edx, edx; lpClass
0x180023470  mov     [rsp+0D0h+lpcbMaxValueNameLen], r13; lpcbMaxValueNameLen
0x180023475  mov     [rsp+0D0h+lpcValues], r13; lpcValues
0x18002347a  mov     [rsp+0D0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x18002347f  mov     [rsp+0D0h+lpcbMaxSubKeyLen], r13; lpcbMaxSubKeyLen
0x180023484  mov     [rsp+0D0h+lpcSubKeys], rax; lpcSubKeys
0x180023489  call    cs:__imp_RegQueryInfoKeyW
0x18002348f  mov     ebx, eax
0x180023491  test    eax, eax
0x180023493  jnz     loc_18002339C
0x180023499  mov     r9d, [rbp+57h+cSubKeys]
0x18002349d  lea     r8, aD; "%d"
0x1800234a4  lea     edx, [rax+18h]; cbDest
0x1800234a7  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800234ab  call    StringCbPrintfW
0x1800234b0  lea     rax, [rbp+57h+dwDisposition]
0x1800234b4  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax
0x1800234b9  lea     r13, [rdi+28h]
0x1800234bd  mov     [rsp+0D0h+lpcValues], r13
0x1800234c2  mov     [rsp+0D0h+lpcbMaxClassLen], 0
0x1800234cb  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], 3001Fh
0x1800234d3  mov     dword ptr [rsp+0D0h+lpcSubKeys], ebx
0x1800234d7  jmp     short loc_18002352C
0x1800234d9  cmp     [rbp+57h+dwDisposition], 1
0x1800234dd  jz      short loc_18002354B
0x1800234df  mov     rcx, [r13+0]; hKey
0x1800234e3  call    cs:__imp_RegCloseKey
0x1800234e9  mov     r9d, [rbp+57h+cSubKeys]
0x1800234ed  lea     r8, aD; "%d"
0x1800234f4  xor     ebx, ebx
0x1800234f6  lea     rcx, [rbp+57h+pszDest]; pszDest
0x1800234fa  inc     r9d
0x1800234fd  mov     [r13+0], rbx
0x180023501  mov     [rbp+57h+cSubKeys], r9d
0x180023505  lea     edx, [rbx+18h]; cbDest
0x180023508  call    StringCbPrintfW
0x18002350d  lea     rax, [rbp+57h+dwDisposition]
0x180023511  mov     [rsp+0D0h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x180023516  mov     [rsp+0D0h+lpcValues], r13; phkResult
0x18002351b  mov     [rsp+0D0h+lpcbMaxClassLen], rbx; lpSecurityAttributes
0x180023520  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], 3001Fh; samDesired
0x180023528  mov     dword ptr [rsp+0D0h+lpcSubKeys], ebx; dwOptions
0x18002352c  mov     rcx, [r12]; hKey
0x180023530  lea     rdx, [rbp+57h+pszDest]; lpSubKey
0x180023534  xor     r9d, r9d; lpClass
0x180023537  xor     r8d, r8d; Reserved
0x18002353a  call    cs:__imp_RegCreateKeyExW
0x180023540  mov     ebx, eax
0x180023542  test    eax, eax
0x180023544  jz      short loc_1800234D9
0x180023546  jmp     loc_18002339C
0x18002354b  mov     rcx, [r14+8]
0x18002354f  cmp     [rcx], r14
0x180023552  jz      short loc_18002355B
0x180023554  mov     ecx, 3
0x180023559  int     29h; Win8: RtlFailFast(ecx)
0x18002355b  lea     rax, [rdi+40h]
0x18002355f  mov     [rax], r14
0x180023562  lea     rdx, [r15+40h]; lpftLastWriteTime
0x180023566  mov     [rax+8], rcx
0x18002356a  mov     [rcx], rax
0x18002356d  mov     [r14+8], rax
0x180023571  mov     rcx, [r12]; hKey
0x180023575  call    UpdateTimeStamp
0x18002357a  lea     rcx, [rbp+57h+pszDest]; pszSrch
0x18002357e  call    StrDupW
0x180023583  mov     [rdi+10h], rax
0x180023587  test    rax, rax
0x18002358a  jnz     short loc_1800235AE
0x18002358c  lea     ebx, [rax+8]
0x18002358f  mov     rdx, rdi; hRouterInterface
0x180023592  mov     rcx, r15; hMprConfig
0x180023595  call    MprConfigInterfaceDelete
0x18002359a  lea     rcx, CfgLock; lpCriticalSection
0x1800235a1  call    cs:__imp_LeaveCriticalSection
0x1800235a7  mov     eax, ebx
0x1800235a9  jmp     loc_1800236B2
0x1800235ae  mov     rcx, rsi; lpString
0x1800235b1  call    cs:__imp_lstrlenW
0x1800235b7  mov     rcx, [r13+0]; hKey
0x1800235bb  lea     rdx, c_szInterfaceName; "InterfaceName"
0x1800235c2  mov     r9d, 1; dwType
0x1800235c8  xor     r8d, r8d; Reserved
0x1800235cb  lea     eax, ds:2[rax*2]
0x1800235d2  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], eax; cbData
0x1800235d6  mov     [rsp+0D0h+lpcSubKeys], rsi; lpData
0x1800235db  call    cs:__imp_RegSetValueExW
0x1800235e1  mov     ebx, eax
0x1800235e3  test    eax, eax
0x1800235e5  jnz     short loc_18002358F
0x1800235e7  mov     rcx, [r13+0]; hKey
0x1800235eb  lea     r14d, [rax+4]
0x1800235ef  lea     rax, [rsi+214h]
0x1800235f6  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], r14d; cbData
0x1800235fb  mov     r9d, r14d; dwType
0x1800235fe  mov     [rsp+0D0h+lpcSubKeys], rax; lpData
0x180023603  xor     r8d, r8d; Reserved
0x180023606  lea     rdx, c_szType; "Type"
0x18002360d  call    cs:__imp_RegSetValueExW
0x180023613  mov     ebx, eax
0x180023615  test    eax, eax
0x180023617  jnz     loc_18002358F
0x18002361d  mov     rcx, [r13+0]; hKey
0x180023621  lea     rax, [rsi+210h]
0x180023628  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], r14d; cbData
0x18002362d  lea     rdx, c_szEnabled; "Enabled"
0x180023634  mov     r9d, r14d; dwType
0x180023637  mov     [rsp+0D0h+lpcSubKeys], rax; lpData
0x18002363c  xor     r8d, r8d; Reserved
0x18002363f  call    cs:__imp_RegSetValueExW
0x180023645  mov     ebx, eax
0x180023647  test    eax, eax
0x180023649  jnz     loc_18002358F
0x18002364f  cmp     [rbp+57h+var_60], 1
0x180023653  jnz     short loc_180023689
0x180023655  mov     rax, [rsi+228h]
0x18002365c  test    rax, rax
0x18002365f  jz      short loc_180023689
0x180023661  mov     ecx, [rbp+57h+cbData]
0x180023664  lea     r9d, [r14+3]; dwType
0x180023668  mov     dword ptr [rsp+0D0h+lpcbMaxSubKeyLen], ecx; cbData
0x18002366c  lea     rdx, c_szDialoutHours; "DialoutHours"
0x180023673  mov     rcx, [r13+0]; hKey
0x180023677  xor     r8d, r8d; Reserved
0x18002367a  mov     [rsp+0D0h+lpcSubKeys], rax; lpData
0x18002367f  call    cs:__imp_RegSetValueExW
0x180023685  mov     ebx, eax
0x180023687  jmp     short loc_18002368B
0x180023689  xor     ebx, ebx
0x18002368b  test    ebx, ebx
0x18002368d  jnz     loc_18002358F
0x180023693  mov     rcx, [r15+80h]; lpMem
0x18002369a  xor     edx, edx
  ... truncated ...
```
