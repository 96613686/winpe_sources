# acmBootPnpDrivers

- ea: `0x1800012a0`
- end: `0x180001560`
- name: `acmBootPnpDrivers`
- size: `704`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x180003f40`

## callees

- `0x1800012a0`
- `0x180001ad0`
- `0x180002220`
- `0x180004b70`
- `0x180005760`
- `0x180007380`
- `0x180008dd8`
- `0x180009270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001481`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001481`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000130b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001395`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000145b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000130b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001395`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000145b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800013d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000148e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001509`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800013d7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000148e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001509`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180001433`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800014f6`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180001433`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800014f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000151f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000151f`

## pseudocode

```c
__int64 __fastcall acmBootPnpDrivers(__int64 a1)
{
  BOOL v2; // ebx
  __int64 v3; // rdi
  __int64 v4; // r14
  DWORD v5; // r14d
  LSTATUS Value; // edi
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v11; // [rsp+58h] [rbp-A8h] BYREF
  struct HWND__ Name[72]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[144]; // [rsp+180h] [rbp+80h] BYREF

  hKey = 0;
  cchName = 0;
  v11 = 0;
  v2 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\MediaResources\\acm", 0, 9u, &hKey) )
    hKey = 0;
  v3 = 0;
  while ( !(unsigned int)IDriverGetNext(a1, &v11, v3, 2684354560LL) )
  {
    v4 = v11;
    phkResult = 0;
    if ( (*(_DWORD *)(v11 + 52) & 0x40000000) != 0 )
    {
      StringCchCopyW(pszDest, 0x90u, (STRSAFE_LPCWSTR)(v11 + 120));
      if ( *(_DWORD *)(v4 + 12) || !hKey || RegOpenKeyExW(hKey, pszDest, 0, 1u, &phkResult) )
      {
        if ( !(unsigned int)IDriverRemove(v4, 0) )
        {
          v2 = v2 || (*(_DWORD *)(v4 + 56) & 0x40000000) == 0;
          continue;
        }
        *(_DWORD *)(v4 + 12) = 1;
        --*(_DWORD *)(a1 + 64);
      }
      if ( !*(_DWORD *)(v4 + 12) )
        RegCloseKey(phkResult);
    }
    v3 = v4;
  }
  v5 = 0;
  phkResult = 0;
  cchName = 144;
  if ( !RegEnumKeyExW(hKey, 0, (LPWSTR)Name, &cchName, 0, 0, 0, 0) )
  {
    do
    {
      if ( !RegOpenKeyExW(hKey, (LPCWSTR)Name, 0, 1u, &phkResult) )
      {
        Value = RegQueryValueExW(phkResult, L"DevNode", 0, 0, 0, 0);
        RegCloseKey(phkResult);
        if ( !Value && !(unsigned int)IDriverAdd(a1, &v11, 0, Name, 0, 0x40000009u) )
          v2 = 1;
      }
      ++v5;
      phkResult = 0;
      cchName = 144;
    }
    while ( !RegEnumKeyExW(hKey, v5, (LPWSTR)Name, &cchName, 0, 0, 0, 0) );
  }
  RegCloseKey(hKey);
  if ( v2 )
  {
    if ( (unsigned int)IDriverPrioritiesRestore(a1) )
    {
      GetCurrentThreadId();
      if ( !*(_QWORD *)(a1 + 120) )
        IDriverBroadcastNotify(a1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800012a0  mov     [rsp-8+arg_8], rbx
0x1800012a5  mov     [rsp-8+arg_10], rsi
0x1800012aa  push    rbp
0x1800012ab  push    rdi
0x1800012ac  push    r12
0x1800012ae  push    r14
0x1800012b0  push    r15
0x1800012b2  lea     rbp, [rsp-1B0h]
0x1800012ba  sub     rsp, 2B0h
0x1800012c1  mov     rax, cs:__security_cookie
0x1800012c8  xor     rax, rsp
0x1800012cb  mov     [rbp+1D0h+var_30], rax
0x1800012d2  xor     r15d, r15d
0x1800012d5  lea     rax, [rsp+2D0h+hKey]
0x1800012da  mov     rsi, rcx
0x1800012dd  mov     [rsp+2D0h+hKey], r15
0x1800012e2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800012e9  mov     [rsp+2D0h+cchName], r15d
0x1800012ee  mov     r9d, 9; samDesired
0x1800012f4  mov     [rsp+2D0h+var_278], r15
0x1800012f9  xor     r8d, r8d; ulOptions
0x1800012fc  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180001301  lea     rdx, gszKeyDrivers; "System\\CurrentControlSet\\Control\\Med"...
0x180001308  mov     ebx, r15d
0x18000130b  call    cs:__imp_RegOpenKeyExW
0x180001311  test    eax, eax
0x180001313  jz      short loc_18000131A
0x180001315  mov     [rsp+2D0h+hKey], r15
0x18000131a  mov     r9d, 0A0000000h
0x180001320  lea     rdx, [rsp+2D0h+var_278]
0x180001325  xor     r8d, r8d
0x180001328  mov     rcx, rsi
0x18000132b  mov     rdi, r15
0x18000132e  call    IDriverGetNext
0x180001333  mov     r12d, 1
0x180001339  test    eax, eax
0x18000133b  jnz     loc_1800013FE
0x180001341  mov     r14, [rsp+2D0h+var_278]
0x180001346  mov     [rsp+2D0h+var_280], r15
0x18000134b  test    dword ptr [r14+34h], 40000000h
0x180001353  jz      loc_1800013DD
0x180001359  lea     r8, [r14+78h]; pszSrc
0x18000135d  mov     edx, 90h; cchDest
0x180001362  lea     rcx, [rbp+1D0h+pszDest]; pszDest
0x180001369  call    StringCchCopyW
0x18000136e  cmp     [r14+0Ch], r15d
0x180001372  jnz     short loc_18000139F
0x180001374  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180001379  test    rcx, rcx
0x18000137c  jz      short loc_18000139F
0x18000137e  lea     rax, [rsp+2D0h+var_280]
0x180001383  mov     r9d, r12d; samDesired
0x180001386  xor     r8d, r8d; ulOptions
0x180001389  mov     [rsp+2D0h+phkResult], rax; phkResult
0x18000138e  lea     rdx, [rbp+1D0h+pszDest]; lpSubKey
0x180001395  call    cs:__imp_RegOpenKeyExW
0x18000139b  test    eax, eax
0x18000139d  jz      short loc_1800013CC
0x18000139f  xor     edx, edx
0x1800013a1  mov     rcx, r14
0x1800013a4  call    IDriverRemove
0x1800013a9  test    eax, eax
0x1800013ab  jnz     short loc_1800013C5
0x1800013ad  test    ebx, ebx
0x1800013af  jnz     short loc_1800013C0
0x1800013b1  test    dword ptr [r14+38h], 40000000h
0x1800013b9  jz      short loc_1800013C0
0x1800013bb  mov     ebx, r15d
0x1800013be  jmp     short loc_1800013E0
0x1800013c0  mov     ebx, r12d
0x1800013c3  jmp     short loc_1800013E0
0x1800013c5  mov     [r14+0Ch], r12d
0x1800013c9  dec     dword ptr [rsi+40h]
0x1800013cc  cmp     [r14+0Ch], r15d
0x1800013d0  jnz     short loc_1800013DD
0x1800013d2  mov     rcx, [rsp+2D0h+var_280]; hKey
0x1800013d7  call    cs:__imp_RegCloseKey
0x1800013dd  mov     rdi, r14
0x1800013e0  mov     r9d, 0A0000000h
0x1800013e6  lea     rdx, [rsp+2D0h+var_278]
0x1800013eb  mov     r8, rdi
0x1800013ee  mov     rcx, rsi
0x1800013f1  call    IDriverGetNext
0x1800013f6  test    eax, eax
0x1800013f8  jz      loc_180001341
0x1800013fe  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180001403  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x180001408  mov     [rsp+2D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x18000140d  lea     r8, [rsp+2D0h+Name]; lpName
0x180001412  mov     [rsp+2D0h+lpcchClass], r15; lpcchClass
0x180001417  xor     edx, edx; dwIndex
0x180001419  mov     [rsp+2D0h+lpClass], r15; lpClass
0x18000141e  mov     r14d, r15d
0x180001421  mov     [rsp+2D0h+phkResult], r15; lpReserved
0x180001426  mov     [rsp+2D0h+var_280], r15
0x18000142b  mov     [rsp+2D0h+cchName], 90h
0x180001433  call    cs:__imp_RegEnumKeyExW
0x180001439  test    eax, eax
0x18000143b  jnz     loc_180001504
0x180001441  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180001446  lea     rax, [rsp+2D0h+var_280]
0x18000144b  mov     r9d, r12d; samDesired
0x18000144e  mov     [rsp+2D0h+phkResult], rax; phkResult
0x180001453  xor     r8d, r8d; ulOptions
0x180001456  lea     rdx, [rsp+2D0h+Name]; lpSubKey
0x18000145b  call    cs:__imp_RegOpenKeyExW
0x180001461  test    eax, eax
0x180001463  jnz     short loc_1800014C0
0x180001465  mov     rcx, [rsp+2D0h+var_280]; hKey
0x18000146a  lea     rdx, gszDevNode; "DevNode"
0x180001471  mov     [rsp+2D0h+lpClass], r15; lpcbData
0x180001476  xor     r9d, r9d; lpType
0x180001479  xor     r8d, r8d; lpReserved
0x18000147c  mov     [rsp+2D0h+phkResult], r15; lpData
0x180001481  call    cs:__imp_RegQueryValueExW
0x180001487  mov     rcx, [rsp+2D0h+var_280]; hKey
0x18000148c  mov     edi, eax
0x18000148e  call    cs:__imp_RegCloseKey
0x180001494  test    edi, edi
0x180001496  jnz     short loc_1800014C0
0x180001498  mov     dword ptr [rsp+2D0h+lpClass], 40000009h
0x1800014a0  lea     r9, [rsp+2D0h+Name]
0x1800014a5  xor     r8d, r8d
0x1800014a8  mov     dword ptr [rsp+2D0h+phkResult], r15d
0x1800014ad  lea     rdx, [rsp+2D0h+var_278]
0x1800014b2  mov     rcx, rsi
0x1800014b5  call    IDriverAdd
0x1800014ba  test    eax, eax
0x1800014bc  cmovz   ebx, r12d
0x1800014c0  mov     rcx, [rsp+2D0h+hKey]; hKey
0x1800014c5  lea     r9, [rsp+2D0h+cchName]; lpcchName
0x1800014ca  mov     [rsp+2D0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800014cf  lea     r8, [rsp+2D0h+Name]; lpName
0x1800014d4  mov     [rsp+2D0h+lpcchClass], r15; lpcchClass
0x1800014d9  inc     r14d
0x1800014dc  mov     [rsp+2D0h+lpClass], r15; lpClass
0x1800014e1  mov     edx, r14d; dwIndex
0x1800014e4  mov     [rsp+2D0h+phkResult], r15; lpReserved
0x1800014e9  mov     [rsp+2D0h+var_280], r15
0x1800014ee  mov     [rsp+2D0h+cchName], 90h
0x1800014f6  call    cs:__imp_RegEnumKeyExW
0x1800014fc  test    eax, eax
0x1800014fe  jz      loc_180001441
0x180001504  mov     rcx, [rsp+2D0h+hKey]; hKey
0x180001509  call    cs:__imp_RegCloseKey
0x18000150f  test    ebx, ebx
0x180001511  jz      short loc_180001533
0x180001513  mov     rcx, rsi
0x180001516  call    IDriverPrioritiesRestore
0x18000151b  test    eax, eax
0x18000151d  jz      short loc_180001533
0x18000151f  call    cs:__imp_GetCurrentThreadId
0x180001525  cmp     [rsi+78h], r15
0x180001529  jnz     short loc_180001533
0x18000152b  mov     rcx, rsi
0x18000152e  call    IDriverBroadcastNotify
0x180001533  xor     eax, eax
0x180001535  mov     rcx, [rbp+1D0h+var_30]
0x18000153c  xor     rcx, rsp; StackCookie
0x18000153f  call    __security_check_cookie
0x180001544  lea     r11, [rsp+2D0h+var_20]
0x18000154c  mov     rbx, [r11+38h]
0x180001550  mov     rsi, [r11+40h]
0x180001554  mov     rsp, r11
0x180001557  pop     r15
0x180001559  pop     r14
0x18000155b  pop     r12
0x18000155d  pop     rdi
0x18000155e  pop     rbp
0x18000155f  retn
```
