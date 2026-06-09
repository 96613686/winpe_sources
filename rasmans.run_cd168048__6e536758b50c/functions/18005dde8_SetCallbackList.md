# SetCallbackList

- ea: `0x18005dde8`
- end: `0x18005e0d2`
- name: `SetCallbackList`
- size: `746`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18005e4dc`

## callees

- `0x18005dde8`
- `0x180060014`
- `0x180060d1c`
- `0x180060e90`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e099`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e035`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005e099`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005de69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005dfec`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005de69`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005dfec`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005decd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005decd`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005de94`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18005de94`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005e044`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005e06d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005e07e`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005e044`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005e06d`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005e07e`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005df66`
- `api-ms-win-core-heap-l2-1-0!GlobalAlloc` at `0x18005df66`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005df28`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005df39`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005df4a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005df28`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005df39`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18005df4a`

## pseudocode

```c
LSTATUS __fastcall SetCallbackList(HKEY a1, __int64 *a2)
{
  LSTATUS result; // eax
  LSTATUS v4; // eax
  LSTATUS v5; // ebx
  __int64 v6; // rdi
  __int64 v7; // r14
  const WCHAR *v8; // r15
  const WCHAR *v9; // r12
  int v10; // ebx
  int v11; // ebx
  __int64 v12; // rbx
  HGLOBAL v13; // rsi
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[152]; // [rsp+70h] [rbp-90h] BYREF

  cchName = 0;
  dwDisposition = 0;
  hKey = 0;
  phkResult = 0;
  result = RegCreateKeyExW(a1, L"Callback", 0, (LPWSTR)&Class, 0, 0x2000Eu, 0, &hKey, &dwDisposition);
  if ( !result )
  {
    do
    {
      cchName = 148;
      v4 = RegEnumKeyExW(hKey, 0, SubKey, &cchName, 0, 0, 0, 0);
      if ( v4 )
        break;
      v4 = RegDeleteKeyExW(hKey, SubKey, 0, 0);
    }
    while ( !v4 );
    v5 = 0;
    if ( v4 != 259 )
      v5 = v4;
    if ( !v5 )
    {
      v6 = *a2;
      if ( v6 )
      {
        while ( 1 )
        {
          v7 = *(_QWORD *)(v6 + 16);
          v8 = &Class;
          v9 = &Class;
          if ( *(_QWORD *)(v7 + 8) )
            v8 = *(const WCHAR **)(v7 + 8);
          if ( *(_QWORD *)v7 )
            v9 = *(const WCHAR **)v7;
          v10 = lstrlenW(v9);
          v11 = lstrlenW(v8) + v10;
          v12 = (unsigned int)(lstrlenW(L"%s (%s)") + v11 + 1);
          v13 = GlobalAlloc(0x40u, 2 * v12);
          if ( !v13 )
            break;
          if ( StringCchPrintfExW((STRSAFE_LPWSTR)v13, (unsigned int)v12, 0, 0, 0x100u, L"%s (%s)", v8, v9) < 0 )
          {
            GlobalFree(v13);
            break;
          }
          v5 = RegCreateKeyExW(hKey, (LPCWSTR)v13, 0, (LPWSTR)&Class, 0, 0x20006u, 0, &phkResult, &dwDisposition);
          if ( v5 )
          {
            GlobalFree(v13);
            goto LABEL_25;
          }
          v5 = SetRegDword(phkResult, L"DeviceType", *(unsigned int *)(v7 + 24));
          if ( !v5 )
            v5 = SetRegSz(phkResult, L"Number");
          RegCloseKey(phkResult);
          GlobalFree(v13);
          if ( !v5 )
          {
            v6 = *(_QWORD *)(v6 + 8);
            if ( v6 )
              continue;
          }
          goto LABEL_25;
        }
        v5 = 8;
      }
      else
      {
        v5 = 0;
      }
    }
LABEL_25:
    RegCloseKey(hKey);
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x18005dde8  mov     [rsp-8+arg_10], rbx
0x18005dded  push    rbp
0x18005ddee  push    rsi
0x18005ddef  push    rdi
0x18005ddf0  push    r12
0x18005ddf2  push    r13
0x18005ddf4  push    r14
0x18005ddf6  push    r15
0x18005ddf8  lea     rbp, [rsp-0B0h]
0x18005de00  sub     rsp, 1B0h
0x18005de07  mov     rax, cs:__security_cookie
0x18005de0e  xor     rax, rsp
0x18005de11  mov     [rbp+0E0h+var_40], rax
0x18005de18  xor     r13d, r13d
0x18005de1b  lea     rax, [rsp+1E0h+dwDisposition]
0x18005de20  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18005de25  lea     r9, Class; lpClass
0x18005de2c  lea     rax, [rsp+1E0h+hKey]
0x18005de31  mov     [rsp+1E0h+cchName], r13d
0x18005de36  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18005de3b  mov     rdi, rdx
0x18005de3e  mov     [rsp+1E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18005de43  lea     rdx, aCallback; "Callback"
0x18005de4a  mov     [rsp+1E0h+samDesired], 2000Eh; samDesired
0x18005de52  xor     r8d, r8d; Reserved
0x18005de55  mov     [rsp+1E0h+dwOptions], r13d; dwOptions
0x18005de5a  mov     [rsp+1E0h+dwDisposition], r13d
0x18005de5f  mov     [rsp+1E0h+hKey], r13
0x18005de64  mov     [rsp+1E0h+var_178], r13
0x18005de69  call    cs:__imp_RegCreateKeyExW
0x18005de70  nop     dword ptr [rax+rax+00h]
0x18005de75  test    eax, eax
0x18005de77  jnz     loc_18005E0A7
0x18005de7d  mov     ebx, 94h
0x18005de82  jmp     short loc_18005DEA4
0x18005de84  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18005de89  lea     rdx, [rsp+1E0h+SubKey]; lpSubKey
0x18005de8e  xor     r9d, r9d; Reserved
0x18005de91  xor     r8d, r8d; samDesired
0x18005de94  call    cs:__imp_RegDeleteKeyExW
0x18005de9b  nop     dword ptr [rax+rax+00h]
0x18005dea0  test    eax, eax
0x18005dea2  jnz     short loc_18005DEDD
0x18005dea4  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18005dea9  lea     r9, [rsp+1E0h+cchName]; lpcchName
0x18005deae  mov     [rsp+1E0h+phkResult], r13; lpftLastWriteTime
0x18005deb3  lea     r8, [rsp+1E0h+SubKey]; lpName
0x18005deb8  mov     [rsp+1E0h+lpSecurityAttributes], r13; lpcchClass
0x18005debd  xor     edx, edx; dwIndex
0x18005debf  mov     qword ptr [rsp+1E0h+samDesired], r13; lpClass
0x18005dec4  mov     qword ptr [rsp+1E0h+dwOptions], r13; lpReserved
0x18005dec9  mov     [rsp+1E0h+cchName], ebx
0x18005decd  call    cs:__imp_RegEnumKeyExW
0x18005ded4  nop     dword ptr [rax+rax+00h]
0x18005ded9  test    eax, eax
0x18005dedb  jz      short loc_18005DE84
0x18005dedd  cmp     eax, 103h
0x18005dee2  mov     ebx, r13d
0x18005dee5  cmovnz  ebx, eax
0x18005dee8  test    ebx, ebx
0x18005deea  jnz     loc_18005E094
0x18005def0  mov     rdi, [rdi]
0x18005def3  test    rdi, rdi
0x18005def6  jz      loc_18005E091
0x18005defc  lea     rsi, aSS_0; "%s (%s)"
0x18005df03  mov     r14, [rdi+10h]
0x18005df07  lea     r15, Class
0x18005df0e  lea     r12, Class
0x18005df15  cmp     [r14+8], r13
0x18005df19  cmovnz  r15, [r14+8]
0x18005df1e  cmp     [r14], r13
0x18005df21  cmovnz  r12, [r14]
0x18005df25  mov     rcx, r12; lpString
0x18005df28  call    cs:__imp_lstrlenW
0x18005df2f  nop     dword ptr [rax+rax+00h]
0x18005df34  mov     rcx, r15; lpString
0x18005df37  mov     ebx, eax
0x18005df39  call    cs:__imp_lstrlenW
0x18005df40  nop     dword ptr [rax+rax+00h]
0x18005df45  mov     rcx, rsi; lpString
0x18005df48  add     ebx, eax
0x18005df4a  call    cs:__imp_lstrlenW
0x18005df51  nop     dword ptr [rax+rax+00h]
0x18005df56  lea     ecx, [rbx+1]
0x18005df59  add     ecx, eax
0x18005df5b  mov     ebx, ecx
0x18005df5d  lea     rdx, [rcx+rcx]; dwBytes
0x18005df61  mov     ecx, 40h ; '@'; uFlags
0x18005df66  call    cs:__imp_GlobalAlloc
0x18005df6d  nop     dword ptr [rax+rax+00h]
0x18005df72  mov     rsi, rax
0x18005df75  test    rax, rax
0x18005df78  jz      loc_18005E08A
0x18005df7e  mov     [rsp+1E0h+phkResult], r12
0x18005df83  lea     rax, aSS_0; "%s (%s)"
0x18005df8a  mov     [rsp+1E0h+lpSecurityAttributes], r15
0x18005df8f  xor     r9d, r9d; pcchRemaining
0x18005df92  mov     qword ptr [rsp+1E0h+samDesired], rax; pszFormat
0x18005df97  xor     r8d, r8d; ppszDestEnd
0x18005df9a  mov     edx, ebx; cchDest
0x18005df9c  mov     [rsp+1E0h+dwOptions], 100h; dwFlags
0x18005dfa4  mov     rcx, rsi; pszDest
0x18005dfa7  call    StringCchPrintfExW
0x18005dfac  test    eax, eax
0x18005dfae  js      loc_18005E07B
0x18005dfb4  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18005dfb9  lea     rax, [rsp+1E0h+dwDisposition]
0x18005dfbe  mov     [rsp+1E0h+lpdwDisposition], rax; lpdwDisposition
0x18005dfc3  lea     r9, Class; lpClass
0x18005dfca  lea     rax, [rsp+1E0h+var_178]
0x18005dfcf  xor     r8d, r8d; Reserved
0x18005dfd2  mov     [rsp+1E0h+phkResult], rax; phkResult
0x18005dfd7  mov     rdx, rsi; lpSubKey
0x18005dfda  mov     [rsp+1E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18005dfdf  mov     [rsp+1E0h+samDesired], 20006h; samDesired
0x18005dfe7  mov     [rsp+1E0h+dwOptions], r13d; dwOptions
0x18005dfec  call    cs:__imp_RegCreateKeyExW
0x18005dff3  nop     dword ptr [rax+rax+00h]
0x18005dff8  mov     ebx, eax
0x18005dffa  test    eax, eax
0x18005dffc  jnz     short loc_18005E06A
0x18005dffe  mov     r8d, [r14+18h]
0x18005e002  lea     rdx, aDevicetype; "DeviceType"
0x18005e009  mov     rcx, [rsp+1E0h+var_178]
0x18005e00e  call    SetRegDword
0x18005e013  mov     ebx, eax
0x18005e015  test    eax, eax
0x18005e017  jnz     short loc_18005E030
0x18005e019  mov     r8, [r14+10h]
0x18005e01d  lea     rdx, aNumber; "Number"
0x18005e024  mov     rcx, [rsp+1E0h+var_178]; hKey
0x18005e029  call    SetRegSz
0x18005e02e  mov     ebx, eax
0x18005e030  mov     rcx, [rsp+1E0h+var_178]; hKey
0x18005e035  call    cs:__imp_RegCloseKey
0x18005e03c  nop     dword ptr [rax+rax+00h]
0x18005e041  mov     rcx, rsi; hMem
0x18005e044  call    cs:__imp_GlobalFree
0x18005e04b  nop     dword ptr [rax+rax+00h]
0x18005e050  test    ebx, ebx
0x18005e052  jnz     short loc_18005E094
0x18005e054  mov     rdi, [rdi+8]
0x18005e058  lea     rsi, aSS_0; "%s (%s)"
0x18005e05f  test    rdi, rdi
0x18005e062  jnz     loc_18005DF03
0x18005e068  jmp     short loc_18005E094
0x18005e06a  mov     rcx, rsi; hMem
0x18005e06d  call    cs:__imp_GlobalFree
0x18005e074  nop     dword ptr [rax+rax+00h]
0x18005e079  jmp     short loc_18005E094
0x18005e07b  mov     rcx, rsi; hMem
0x18005e07e  call    cs:__imp_GlobalFree
0x18005e085  nop     dword ptr [rax+rax+00h]
0x18005e08a  mov     ebx, 8
0x18005e08f  jmp     short loc_18005E094
0x18005e091  mov     ebx, r13d
0x18005e094  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18005e099  call    cs:__imp_RegCloseKey
0x18005e0a0  nop     dword ptr [rax+rax+00h]
0x18005e0a5  mov     eax, ebx
0x18005e0a7  mov     rcx, [rbp+0E0h+var_40]
0x18005e0ae  xor     rcx, rsp; StackCookie
0x18005e0b1  call    __security_check_cookie
0x18005e0b6  mov     rbx, [rsp+1E0h+arg_10]
0x18005e0be  add     rsp, 1B0h
0x18005e0c5  pop     r15
0x18005e0c7  pop     r14
0x18005e0c9  pop     r13
0x18005e0cb  pop     r12
0x18005e0cd  pop     rdi
0x18005e0ce  pop     rsi
0x18005e0cf  pop     rbp
0x18005e0d0  retn
```
