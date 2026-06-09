# IDriverAdd

- ea: `0x180004b70`
- end: `0x1800050f0`
- name: `IDriverAdd`
- size: `1408`
- prototype: `__int64 __fastcall(__int64, __int64 *, HMODULE, HWND, unsigned int, unsigned int)`
- caller_count: `4`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800012a0`
- `0x180005e70`
- `0x180005f60`
- `0x180008c00`

## callees

- `0x180001c40`
- `0x1800040a0`
- `0x180004b70`
- `0x180005100`
- `0x1800054a0`
- `0x180005700`
- `0x180005760`
- `0x180007380`
- `0x180009270`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004fbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005009`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000505e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180004fbd`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005009`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000505e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004db7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004db7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ec3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000507e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ec3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180005035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000507e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e54`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e54`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180004e42`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180004f74`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180004e42`
- `api-ms-win-core-string-l2-1-0!CharLowerBuffW` at `0x180004f74`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004e19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004f4b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004e19`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x180004f4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005099`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180004ef8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180005099`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004edf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005022`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180004edf`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005022`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004f1e`
- `ext-ms-win-ntuser-window-l1-1-0!IsWindow` at `0x180004f1e`

## pseudocode

```c
__int64 __fastcall IDriverAdd(__int64 a1, __int64 *a2, HMODULE a3, HWND a4, unsigned int a5, unsigned int a6)
{
  int v9; // r14d
  __int64 v10; // rbx
  __int64 v11; // rdi
  WCHAR *v12; // r8
  WCHAR *v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r9
  WCHAR *v16; // rcx
  __int64 v17; // rax
  __int64 v18; // rsi
  WCHAR *v19; // rcx
  unsigned int v20; // r12d
  _WORD *v21; // rdx
  _WORD *v22; // rcx
  const WCHAR *v23; // rax
  int v24; // r14d
  int v25; // r14d
  __int64 v26; // rdi
  __int64 v27; // rax
  __int64 *v28; // rcx
  _DWORD *v29; // rax
  LSTATUS v31; // ebx
  __int64 v32; // rdx
  DWORD CurrentThreadId; // eax
  unsigned int v34; // ebx
  DWORD v35; // ebx
  wchar_t *v36; // rax
  wchar_t *v37; // rdi
  BYTE *v38; // rax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD lpcbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+44h] [rbp-BCh]
  __int64 v44; // [rsp+48h] [rbp-B8h]
  __int64 *v45; // [rsp+50h] [rbp-B0h]
  WCHAR Filename[144]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t pszDest[200]; // [rsp+180h] [rbp+80h] BYREF

  v45 = a2;
  v44 = a1;
  if ( !a2 )
    return 11;
  *a2 = 0;
  if ( (a6 & 0x3FFFFFF0) != 0 )
    return 10;
  v9 = a6 & 7;
  v43 = a6 & 8;
  v10 = 2147483646;
  if ( v9 != 1 )
  {
    if ( v9 != 2 )
    {
      if ( v9 != 3 )
      {
        if ( v9 != 4 || (a6 & 8) != 0 )
          return 11;
        if ( !IsWindow(a4) )
          return 5;
        if ( !a3 )
          return 11;
        v11 = 144;
        if ( !GetModuleFileNameW(a3, Filename, 0x90u) )
          return 11;
        v32 = -1;
        do
          ++v32;
        while ( Filename[v32] );
        goto LABEL_47;
      }
      if ( a5 )
        return 11;
    }
    if ( !a4 )
      return 11;
    if ( !a3 )
      return 11;
    v11 = 144;
    if ( !GetModuleFileNameW(a3, Filename, 0x90u) )
      return 11;
    v32 = -1;
    do
      ++v32;
    while ( Filename[v32] );
LABEL_47:
    CharLowerBuffW(Filename, v32);
    goto LABEL_12;
  }
  if ( !a4 )
    return 11;
  v11 = 144;
  v12 = Filename;
  v13 = (WCHAR *)a4;
  v14 = 2147483646;
  v15 = 144;
  do
  {
    if ( !v14 )
      break;
    if ( !*v13 )
      break;
    *v12++ = *v13++;
    --v14;
    --v15;
  }
  while ( v15 );
  v16 = v12 - 1;
  if ( v15 )
    v16 = v12;
  *v16 = 0;
LABEL_12:
  if ( IDriverFind(a1, a4, a6) )
    return 1;
  v17 = NewHandle(420);
  v18 = v17;
  if ( !v17 )
    return 7;
  *(_QWORD *)(v17 + 4) = a1;
  v19 = Filename;
  v20 = 1;
  *(_QWORD *)(v17 + 44) = a4;
  *(_DWORD *)v17 = 1;
  *(_DWORD *)(v17 + 16) = 0;
  v21 = (_WORD *)(v17 + 120);
  *(_DWORD *)(v17 + 52) = a6;
  do
  {
    if ( !v10 )
      break;
    if ( !*v19 )
      break;
    *v21++ = *v19++;
    --v10;
    --v11;
  }
  while ( v11 );
  v22 = v21 - 1;
  v23 = 0;
  if ( v11 )
    v22 = v21;
  *v22 = 0;
  if ( (a6 & 0x40000000) == 0 )
    v23 = L"Drivers32";
  *(_QWORD *)(v18 + 112) = v23;
  if ( (a6 & 0x40000000) != 0 )
  {
    cbData = 0;
    Type = 0;
    lpcbData = 0;
    hKey = 0;
    *(_QWORD *)(v18 + 408) = 0;
    StringCchPrintfW(pszDest, 0xC4u, L"%s\\%s", L"System\\CurrentControlSet\\Control\\MediaResources\\acm", Filename);
    v31 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 1u, &hKey);
    if ( !v31 )
    {
      cbData = 4;
      v37 = 0;
      v31 = RegQueryValueExW(hKey, L"DevNode", 0, &Type, (LPBYTE)(v18 + 416), &cbData);
      if ( !v31 )
      {
        if ( Type - 3 > 1 || cbData != 4 )
          goto LABEL_75;
        v31 = RegQueryValueExW(hKey, L"Driver", 0, 0, 0, &lpcbData);
        if ( !v31 )
        {
          v38 = (BYTE *)LocalAlloc(0x40u, lpcbData);
          v37 = (wchar_t *)v38;
          if ( !v38 )
          {
            RegCloseKey(hKey);
            return 7;
          }
          v31 = RegQueryValueExW(hKey, L"Driver", 0, &Type, v38, &lpcbData);
          if ( !v31 && Type != 1 )
          {
LABEL_75:
            RegCloseKey(hKey);
            return v20;
          }
        }
      }
      RegCloseKey(hKey);
      if ( !v31 )
      {
        v35 = lpcbData >> 1;
        v36 = (wchar_t *)LocalAlloc(0x40u, 2 * (lpcbData >> 1));
        *(_QWORD *)(v18 + 408) = v36;
        if ( v36 )
        {
          StringCchCopyW(v36, v35, v37);
          LocalFree(v37);
          goto LABEL_23;
        }
        LocalFree(v37);
        return 7;
      }
    }
    if ( v31 != 14 )
      return v20;
    return 7;
  }
LABEL_23:
  v24 = v9 - 2;
  if ( !v24 )
  {
    *(_DWORD *)(v18 + 56) |= 0x10000000u;
    *(_QWORD *)(v18 + 104) = a5;
    goto LABEL_78;
  }
  v25 = v24 - 1;
  if ( !v25 )
  {
LABEL_78:
    *(_QWORD *)(v18 + 96) = a4;
    goto LABEL_27;
  }
  if ( v25 == 1 )
  {
    *(_DWORD *)(v18 + 56) |= 0x10000000u;
    *(_QWORD *)(v18 + 104) = a5;
    *(_QWORD *)(v18 + 96) = -1;
  }
LABEL_27:
  if ( v43 )
  {
    v26 = v44;
    *(_QWORD *)(v18 + 36) = 0;
    v27 = *(_QWORD *)(v26 + 96);
    if ( v27 )
    {
      do
      {
        v28 = (__int64 *)(v27 + 20);
        v27 = *(_QWORD *)(v27 + 20);
      }
      while ( v27 );
      *v28 = v18;
      goto LABEL_31;
    }
  }
  else
  {
    *(_DWORD *)(v18 + 56) |= 0x40000000u;
    CurrentThreadId = GetCurrentThreadId();
    v26 = v44;
    *(_QWORD *)(v18 + 36) = CurrentThreadId;
    *(_QWORD *)(v18 + 20) = *(_QWORD *)(v26 + 96);
  }
  *(_QWORD *)(v26 + 96) = v18;
LABEL_31:
  if ( (unsigned int)IDriverReadRegistryData(v18) && (v34 = IDriverLoad(v18)) != 0 )
  {
    IDriverRemove(v18, 0);
    return v34;
  }
  else
  {
    *v45 = v18;
    v29 = *(_DWORD **)(v26 + 80);
    if ( v29 )
      ++*v29;
    return 0;
  }
}

```

## disassembly

```asm
0x180004b70  push    rbp
0x180004b72  push    rbx
0x180004b73  push    rsi
0x180004b74  push    rdi
0x180004b75  push    r12
0x180004b77  push    r13
0x180004b79  push    r14
0x180004b7b  push    r15
0x180004b7d  lea     rbp, [rsp-228h]
0x180004b85  sub     rsp, 328h
0x180004b8c  mov     rax, cs:__security_cookie
0x180004b93  xor     rax, rsp
0x180004b96  mov     [rbp+260h+var_50], rax
0x180004b9d  mov     r15d, [rbp+260h+arg_28]
0x180004ba4  mov     r13, r9
0x180004ba7  mov     [rsp+360h+var_310], rdx
0x180004bac  mov     rsi, r8
0x180004baf  mov     [rsp+360h+var_318], rcx
0x180004bb4  mov     r12, rcx
0x180004bb7  test    rdx, rdx
0x180004bba  jz      loc_1800050E6
0x180004bc0  mov     qword ptr [rdx], 0
0x180004bc7  test    r15d, 3FFFFFF0h
0x180004bce  jnz     loc_180004F03
0x180004bd4  mov     ecx, r15d
0x180004bd7  mov     r14d, r15d
0x180004bda  and     ecx, 8
0x180004bdd  and     r14d, 7
0x180004be1  mov     [rsp+360h+var_31C], ecx
0x180004be5  mov     ebx, 7FFFFFFEh
0x180004bea  cmp     r14d, 1
0x180004bee  jnz     loc_180004DDA
0x180004bf4  test    r9, r9
0x180004bf7  jz      loc_1800050E6
0x180004bfd  mov     edi, 90h
0x180004c02  lea     r8, [rsp+360h+Filename]
0x180004c07  mov     rdx, r9
0x180004c0a  mov     ecx, ebx
0x180004c0c  mov     r9d, edi
0x180004c0f  nop
0x180004c10  test    rcx, rcx
0x180004c13  jz      short loc_180004C32
0x180004c15  movzx   eax, word ptr [rdx]
0x180004c18  test    ax, ax
0x180004c1b  jz      short loc_180004C32
0x180004c1d  mov     [r8], ax
0x180004c21  add     rdx, 2
0x180004c25  add     r8, 2
0x180004c29  dec     rcx
0x180004c2c  sub     r9, 1
0x180004c30  jnz     short loc_180004C10
0x180004c32  test    r9, r9
0x180004c35  lea     rcx, [r8-2]
0x180004c39  cmovnz  rcx, r8
0x180004c3d  xor     eax, eax
0x180004c3f  mov     [rcx], ax
0x180004c42  mov     r8d, r15d
0x180004c45  mov     rdx, r13
0x180004c48  mov     rcx, r12
0x180004c4b  call    IDriverFind
0x180004c50  test    rax, rax
0x180004c53  jnz     loc_180004EB7
0x180004c59  mov     ecx, 1A4h
0x180004c5e  call    NewHandle
0x180004c63  mov     rsi, rax
0x180004c66  test    rax, rax
0x180004c69  jz      loc_180004F7F
0x180004c6f  mov     [rax+4], r12
0x180004c73  lea     rcx, [rsp+360h+Filename]
0x180004c78  mov     r12d, 1
0x180004c7e  mov     [rax+2Ch], r13
0x180004c82  xor     r8d, r8d
0x180004c85  mov     [rax], r12d
0x180004c88  mov     [rax+10h], r8d
0x180004c8c  lea     rdx, [rax+78h]
0x180004c90  mov     [rax+34h], r15d
0x180004c94  test    rbx, rbx
0x180004c97  jz      short loc_180004CB4
0x180004c99  movzx   eax, word ptr [rcx]
0x180004c9c  test    ax, ax
0x180004c9f  jz      short loc_180004CB4
0x180004ca1  mov     [rdx], ax
0x180004ca4  add     rcx, 2
0x180004ca8  add     rdx, 2
0x180004cac  dec     rbx
0x180004caf  sub     rdi, r12
0x180004cb2  jnz     short loc_180004C94
0x180004cb4  test    rdi, rdi
0x180004cb7  lea     rcx, [rdx-2]
0x180004cbb  mov     rax, r8
0x180004cbe  cmovnz  rcx, rdx
0x180004cc2  bt      r15d, 1Eh
0x180004cc7  mov     [rcx], r8w
0x180004ccb  lea     rcx, gszSecDriversW; "Drivers32"
0x180004cd2  cmovnb  rax, rcx
0x180004cd6  mov     [rsi+70h], rax
0x180004cda  jb      short loc_180004D55
0x180004cdc  sub     r14d, 2
0x180004ce0  jz      loc_1800050C5
0x180004ce6  sub     r14d, r12d
0x180004ce9  jz      loc_1800050D6
0x180004cef  cmp     r14d, r12d
0x180004cf2  jz      loc_1800050A7
0x180004cf8  cmp     [rsp+360h+var_31C], 0
0x180004cfd  jz      loc_180004E4D
0x180004d03  mov     rdi, [rsp+360h+var_318]
0x180004d08  mov     [rsi+24h], r8
0x180004d0c  mov     rax, [rdi+60h]
0x180004d10  test    rax, rax
0x180004d13  jz      loc_180004E6D
0x180004d19  lea     rcx, [rax+14h]
0x180004d1d  mov     rax, [rax+14h]
0x180004d21  test    rax, rax
0x180004d24  jnz     short loc_180004D19
0x180004d26  mov     [rcx], rsi
0x180004d29  mov     rcx, rsi
0x180004d2c  call    IDriverReadRegistryData
0x180004d31  test    eax, eax
0x180004d33  jnz     loc_180004E76
0x180004d39  mov     rax, [rsp+360h+var_310]
0x180004d3e  mov     [rax], rsi
0x180004d41  mov     rax, [rdi+50h]
0x180004d45  test    rax, rax
0x180004d48  jnz     loc_1800050DF
0x180004d4e  xor     eax, eax
0x180004d50  jmp     loc_180004E94
0x180004d55  mov     [rsp+360h+cbData], r8d
0x180004d5a  lea     rax, [rsp+360h+Filename]
0x180004d5f  mov     [rsp+360h+Type], r8d
0x180004d64  lea     r9, gszKeyDrivers; "System\\CurrentControlSet\\Control\\Med"...
0x180004d6b  mov     [rsp+360h+var_32C], r8d
0x180004d70  lea     rcx, [rbp+260h+pszDest]; pszDest
0x180004d77  mov     [rsp+360h+hKey], r8
0x180004d7c  mov     edx, 0C4h; cchDest
0x180004d81  mov     [rsi+198h], r8
0x180004d88  lea     r8, gszFormatDriverKey; "%s\\%s"
0x180004d8f  mov     [rsp+360h+phkResult], rax
0x180004d94  call    StringCchPrintfW
0x180004d99  lea     rax, [rsp+360h+hKey]
0x180004d9e  mov     r9d, r12d; samDesired
0x180004da1  xor     r8d, r8d; ulOptions
0x180004da4  mov     [rsp+360h+phkResult], rax; phkResult
0x180004da9  lea     rdx, [rbp+260h+pszDest]; lpSubKey
0x180004db0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004db7  call    cs:__imp_RegOpenKeyExW
0x180004dbd  mov     ebx, eax
0x180004dbf  test    eax, eax
0x180004dc1  jz      loc_180004F89
0x180004dc7  cmp     ebx, 0Eh
0x180004dca  jnz     short loc_180004DD2
0x180004dcc  mov     r12d, 7
0x180004dd2  mov     eax, r12d
0x180004dd5  jmp     loc_180004E94
0x180004dda  mov     eax, r14d
0x180004ddd  sub     eax, 2
0x180004de0  jz      short loc_180004DF7
0x180004de2  sub     eax, 1
0x180004de5  jnz     loc_180004F0A
0x180004deb  cmp     [rbp+260h+arg_20], eax
0x180004df1  jnz     loc_1800050E6
0x180004df7  test    r13, r13
0x180004dfa  jz      loc_1800050E6
0x180004e00  test    rsi, rsi
0x180004e03  jz      loc_1800050E6
0x180004e09  mov     edi, 90h
0x180004e0e  lea     rdx, [rsp+360h+Filename]; lpFilename
0x180004e13  mov     r8d, edi; nSize
0x180004e16  mov     rcx, rsi; hModule
0x180004e19  call    cs:__imp_GetModuleFileNameW
0x180004e1f  test    eax, eax
0x180004e21  jz      loc_1800050E6
0x180004e27  lea     rax, [rsp+360h+Filename]
0x180004e2c  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180004e33  inc     rdx; cchLength
0x180004e36  cmp     word ptr [rax+rdx*2], 0
0x180004e3b  jnz     short loc_180004E33
0x180004e3d  lea     rcx, [rsp+360h+Filename]; lpsz
0x180004e42  call    cs:__imp_CharLowerBuffW
0x180004e48  jmp     loc_180004C42
0x180004e4d  or      dword ptr [rsi+38h], 40000000h
0x180004e54  call    cs:__imp_GetCurrentThreadId
0x180004e5a  mov     rdi, [rsp+360h+var_318]
0x180004e5f  mov     eax, eax
0x180004e61  mov     [rsi+24h], rax
0x180004e65  mov     rax, [rdi+60h]
0x180004e69  mov     [rsi+14h], rax
0x180004e6d  mov     [rdi+60h], rsi
0x180004e71  jmp     loc_180004D29
0x180004e76  mov     rcx, rsi
0x180004e79  call    IDriverLoad
0x180004e7e  mov     ebx, eax
0x180004e80  test    eax, eax
0x180004e82  jz      loc_180004D39
0x180004e88  xor     edx, edx
0x180004e8a  mov     rcx, rsi
0x180004e8d  call    IDriverRemove
0x180004e92  mov     eax, ebx
0x180004e94  mov     rcx, [rbp+260h+var_50]
0x180004e9b  xor     rcx, rsp; StackCookie
0x180004e9e  call    __security_check_cookie
0x180004ea3  add     rsp, 328h
0x180004eaa  pop     r15
0x180004eac  pop     r14
0x180004eae  pop     r13
0x180004eb0  pop     r12
0x180004eb2  pop     rdi
0x180004eb3  pop     rsi
0x180004eb4  pop     rbx
0x180004eb5  pop     rbp
0x180004eb6  retn
0x180004eb7  mov     eax, 1
0x180004ebc  jmp     short loc_180004E94
0x180004ebe  mov     rcx, [rsp+360h+hKey]; hKey
0x180004ec3  call    cs:__imp_RegCloseKey
0x180004ec9  test    ebx, ebx
0x180004ecb  jnz     loc_180004DC7
0x180004ed1  mov     ebx, [rsp+360h+var_32C]
0x180004ed5  mov     ecx, 40h ; '@'; uFlags
0x180004eda  shr     ebx, 1
0x180004edc  lea     edx, [rbx+rbx]; uBytes
0x180004edf  call    cs:__imp_LocalAlloc
0x180004ee5  mov     [rsi+198h], rax
0x180004eec  test    rax, rax
0x180004eef  jnz     loc_180005089
0x180004ef5  mov     rcx, rdi; hMem
0x180004ef8  call    cs:__imp_LocalFree
0x180004efe  jmp     loc_180004DCC
0x180004f03  mov     eax, 0Ah
0x180004f08  jmp     short loc_180004E94
0x180004f0a  cmp     eax, 1
0x180004f0d  jnz     loc_1800050E6
0x180004f13  test    ecx, ecx
0x180004f15  jnz     loc_1800050E6
0x180004f1b  mov     rcx, r13; hWnd
0x180004f1e  call    cs:__imp_IsWindow
0x180004f24  test    eax, eax
0x180004f26  jnz     short loc_180004F32
0x180004f28  mov     eax, 5
0x180004f2d  jmp     loc_180004E94
0x180004f32  test    rsi, rsi
0x180004f35  jz      loc_1800050E6
0x180004f3b  mov     edi, 90h
0x180004f40  lea     rdx, [rsp+360h+Filename]; lpFilename
0x180004f45  mov     r8d, edi; nSize
0x180004f48  mov     rcx, rsi; hModule
0x180004f4b  call    cs:__imp_GetModuleFileNameW
0x180004f51  test    eax, eax
0x180004f53  jz      loc_1800050E6
0x180004f59  lea     rax, [rsp+360h+Filename]
0x180004f5e  mov     rdx, 0FFFFFFFFFFFFFFFFh
0x180004f65  inc     rdx; cchLength
0x180004f68  cmp     word ptr [rax+rdx*2], 0
0x180004f6d  jnz     short loc_180004F65
0x180004f6f  lea     rcx, [rsp+360h+Filename]; lpsz
0x180004f74  call    cs:__imp_CharLowerBuffW
0x180004f7a  jmp     loc_180004C42
0x180004f7f  mov     eax, 7
0x180004f84  jmp     loc_180004E94
0x180004f89  lea     rcx, [rsp+360h+cbData]
0x180004f8e  mov     [rsp+360h+cbData], 4
0x180004f96  mov     [rsp+360h+lpcbData], rcx; lpcbData
0x180004f9b  lea     rax, [rsi+1A0h]
0x180004fa2  mov     rcx, [rsp+360h+hKey]; hKey
0x180004fa7  lea     r9, [rsp+360h+Type]; lpType
0x180004fac  xor     r8d, r8d; lpReserved
0x180004faf  mov     [rsp+360h+phkResult], rax; lpData
0x180004fb4  lea     rdx, gszDevNode; "DevNode"
0x180004fbb  xor     edi, edi
0x180004fbd  call    cs:__imp_RegQueryValueExW
0x180004fc3  mov     ebx, eax
0x180004fc5  test    eax, eax
0x180004fc7  jnz     loc_180004EBE
0x180004fcd  mov     eax, [rsp+360h+Type]
0x180004fd1  add     eax, 0FFFFFFFDh
0x180004fd4  cmp     eax, r12d
0x180004fd7  ja      loc_180005079
0x180004fdd  cmp     [rsp+360h+cbData], 4
0x180004fe2  jnz     loc_180005079
0x180004fe8  mov     rcx, [rsp+360h+hKey]; hKey
0x180004fed  lea     rax, [rsp+360h+var_32C]
0x180004ff2  mov     [rsp+360h+lpcbData], rax; lpcbData
0x180004ff7  lea     rdx, gszDriver; "Driver"
0x180004ffe  xor     r9d, r9d; lpType
0x180005001  mov     [rsp+360h+phkResult], rdi; lpData
0x180005006  xor     r8d, r8d; lpReserved
0x180005009  call    cs:__imp_RegQueryValueExW
0x18000500f  mov     ebx, eax
0x180005011  test    eax, eax
0x180005013  jnz     loc_180004EBE
0x180005019  mov     edx, [rsp+360h+var_32C]; uBytes
0x18000501d  mov     ecx, 40h ; '@'; uFlags
0x180005022  call    cs:__imp_LocalAlloc
0x180005028  mov     rcx, [rsp+360h+hKey]; hKey
0x18000502d  mov     rdi, rax
0x180005030  test    rax, rax
0x180005033  jnz     short loc_180005040
0x180005035  call    cs:__imp_RegCloseKey
0x18000503b  jmp     loc_180004DCC
0x180005040  lea     rax, [rsp+360h+var_32C]
0x180005045  xor     r8d, r8d; lpReserved
  ... truncated ...
```
