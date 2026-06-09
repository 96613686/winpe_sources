# NetFileInfo(x,x)

- ea: `0x1000d8d0`
- end: `0x1000db15`
- name: `_NetFileInfo@8`
- size: `581`
- prototype: `int __stdcall(wchar_t *FullPath, int)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x1000b470`

## callees

- `0x1000ad60`
- `0x1000b070`
- `0x1000b200`
- `0x1000c2f0`
- `0x1000ca60`
- `0x1000d8d0`
- `0x1000ddd0`
- `0x1000e950`
- `0x1002b81a`
- `0x1002c490`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000da14`
- `KERNEL32!GetLastError` at `0x1000da14`
- `KERNEL32!WideCharToMultiByte` at `0x1000d99c`
- `KERNEL32!WideCharToMultiByte` at `0x1000d9e5`
- `KERNEL32!WideCharToMultiByte` at `0x1000d97b`
- `KERNEL32!MultiByteToWideChar` at `0x1000dab3`
- `KERNEL32!MultiByteToWideChar` at `0x1000dae5`
- `KERNEL32!MultiByteToWideChar` at `0x1000da98`

## pseudocode

```c
int __stdcall NetFileInfo(wchar_t *FullPath, int a2)
{
  int result; // eax
  int v3; // ebp
  CHAR *v4; // ebx
  void *v5; // ebp
  void *FirstFileA; // eax
  int InternetError; // edi
  HINTERNET v8; // [esp+14h] [ebp-548h] BYREF
  struct _WIN32_FIND_DATAA v9; // [esp+18h] [ebp-544h] BYREF
  wchar_t pszDest[256]; // [esp+158h] [ebp-404h] BYREF
  wchar_t pszSrc[256]; // [esp+358h] [ebp-204h] BYREF

  if ( !dword_10040FB8 && !NetInitializeInternetServices() )
    return -20163;
  result = SetupForFTP(FullPath, &v8);
  if ( !result )
  {
    SplitPath(FullPath, 0, 0, 0, 0, pszDest, 0x100u, pszSrc, 0x100u);
    StringCchCatW(pszDest, 0x100u, pszSrc);
    v3 = WideCharToMultiByte(0, 0, pszDest, wcslen(pszDest), 0, 0, 0, 0);
    v4 = (CHAR *)MemAllocate(v3 + 1);
    if ( v4 )
    {
      WideCharToMultiByte(0, 0, pszDest, wcslen(pszDest), v4, v3, 0, 0);
      memset(&v9, 0, sizeof(v9));
      v5 = v8;
      FirstFileA = FtpFindFirstFileA(v8, v4, &v9, 0, 0);
      if ( FirstFileA )
      {
        InternetCloseHandle(FirstFileA);
        InternetError = 0;
      }
      else if ( GetLastError() == 18 )
      {
        InternetError = -1305;
      }
      else
      {
        InternetError = GetInternetError();
      }
      MemFree(v4);
      *(FILETIME *)a2 = v9.ftCreationTime;
      *(FILETIME *)(a2 + 8) = v9.ftLastAccessTime;
      *(FILETIME *)(a2 + 16) = v9.ftLastWriteTime;
      *(_DWORD *)(a2 + 24) = v9.nFileSizeHigh;
      *(_DWORD *)(a2 + 28) = v9.nFileSizeLow;
      *(_DWORD *)(a2 + 32) = v9.dwReserved0;
      *(_DWORD *)(a2 + 36) = v9.dwReserved1;
      *(_DWORD *)(a2 + 40) = *(_DWORD *)v9.cFileName;
      *(_WORD *)(a2
               + 2 * MultiByteToWideChar(0, 0, &v9.cFileName[4], strlen(&v9.cFileName[4]), (LPWSTR)(a2 + 44), 260)
               + 44) = 0;
      *(_WORD *)(a2
               + 2
               * MultiByteToWideChar(
                   0,
                   0,
                   &v9.cAlternateFileName[4],
                   strlen(&v9.cAlternateFileName[4]),
                   (LPWSTR)(a2 + 564),
                   14)
               + 564) = 0;
      InternetCloseHandle(v5);
      return InternetError;
    }
    else
    {
      return -1011;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000d8d0  sub     esp, 548h
0x1000d8d6  mov     eax, ___security_cookie
0x1000d8db  xor     eax, esp
0x1000d8dd  mov     [esp+548h+var_4], eax
0x1000d8e4  cmp     dword_10040FB8, 0
0x1000d8eb  push    esi
0x1000d8ec  mov     esi, [esp+54Ch+arg_4]
0x1000d8f3  push    edi
0x1000d8f4  mov     edi, [esp+550h+FullPath]
0x1000d8fb  jnz     short loc_1000D910
0x1000d8fd  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x1000d902  test    eax, eax
0x1000d904  jnz     short loc_1000D910
0x1000d906  mov     eax, 0FFFFB13Dh
0x1000d90b  jmp     loc_1000DAFC
0x1000d910  lea     eax, [esp+550h+var_548]
0x1000d914  push    eax
0x1000d915  push    edi
0x1000d916  call    SetupForFTP
0x1000d91b  test    eax, eax
0x1000d91d  jnz     loc_1000DAFC
0x1000d923  push    100h; ExtCount
0x1000d928  lea     eax, [esp+554h+pszSrc]
0x1000d92f  push    eax; Ext
0x1000d930  push    100h; FilenameCount
0x1000d935  lea     eax, [esp+55Ch+pszDest]
0x1000d93c  push    eax; Filename
0x1000d93d  push    0; DirCount
0x1000d93f  push    0; Dir
0x1000d941  push    0; DriveCount
0x1000d943  push    0; Drive
0x1000d945  push    edi; FullPath
0x1000d946  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1000d94b  lea     eax, [esp+550h+pszSrc]
0x1000d952  push    eax; pszSrc
0x1000d953  push    100h; cchDest
0x1000d958  lea     eax, [esp+558h+pszDest]
0x1000d95f  push    eax; pszDest
0x1000d960  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000d965  lea     ecx, [esp+550h+pszDest]
0x1000d96c  lea     edx, [ecx+2]
0x1000d96f  nop
0x1000d970  mov     ax, [ecx]
0x1000d973  add     ecx, 2
0x1000d976  test    ax, ax
0x1000d979  jnz     short loc_1000D970
0x1000d97b  mov     edi, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d981  lea     eax, [esp+550h+pszDest]
0x1000d988  push    ebx
0x1000d989  push    ebp
0x1000d98a  push    0; lpUsedDefaultChar
0x1000d98c  push    0; lpDefaultChar
0x1000d98e  push    0; cbMultiByte
0x1000d990  push    0; lpMultiByteStr
0x1000d992  sub     ecx, edx
0x1000d994  sar     ecx, 1
0x1000d996  push    ecx; cchWideChar
0x1000d997  push    eax; lpWideCharStr
0x1000d998  push    0; dwFlags
0x1000d99a  push    0; CodePage
0x1000d99c  call    edi ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d99e  mov     ebp, eax
0x1000d9a0  lea     ecx, [ebp+1]
0x1000d9a3  push    ecx; Size
0x1000d9a4  call    _MemAllocate@4; MemAllocate(x)
0x1000d9a9  mov     ebx, eax
0x1000d9ab  test    ebx, ebx
0x1000d9ad  jnz     short loc_1000D9B9
0x1000d9af  mov     eax, 0FFFFFC0Dh
0x1000d9b4  jmp     loc_1000DAFA
0x1000d9b9  lea     ecx, [esp+558h+pszDest]
0x1000d9c0  lea     edx, [ecx+2]
0x1000d9c3  mov     ax, [ecx]
0x1000d9c6  add     ecx, 2
0x1000d9c9  test    ax, ax
0x1000d9cc  jnz     short loc_1000D9C3
0x1000d9ce  push    0; lpUsedDefaultChar
0x1000d9d0  push    0; lpDefaultChar
0x1000d9d2  push    ebp; cbMultiByte
0x1000d9d3  push    ebx; lpMultiByteStr
0x1000d9d4  sub     ecx, edx
0x1000d9d6  lea     eax, [esp+568h+pszDest]
0x1000d9dd  sar     ecx, 1
0x1000d9df  push    ecx; cchWideChar
0x1000d9e0  push    eax; lpWideCharStr
0x1000d9e1  push    0; dwFlags
0x1000d9e3  push    0; CodePage
0x1000d9e5  call    edi ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000d9e7  push    140h; Size
0x1000d9ec  lea     eax, [esp+55Ch+var_544]
0x1000d9f0  push    0; Val
0x1000d9f2  push    eax; void *
0x1000d9f3  call    _memset
0x1000d9f8  mov     ebp, [esp+564h+var_548]
0x1000d9fc  lea     eax, [esp+564h+var_544]
0x1000da00  add     esp, 0Ch
0x1000da03  push    0
0x1000da05  push    0
0x1000da07  push    eax
0x1000da08  push    ebx
0x1000da09  push    ebp
0x1000da0a  call    FtpFindFirstFileA
0x1000da10  test    eax, eax
0x1000da12  jnz     short loc_1000DA2F
0x1000da14  call    ds:__imp__GetLastError@0; GetLastError()
0x1000da1a  cmp     eax, 12h
0x1000da1d  jz      short loc_1000DA28
0x1000da1f  call    GetInternetError
0x1000da24  mov     edi, eax
0x1000da26  jmp     short loc_1000DA38
0x1000da28  mov     edi, 0FFFFFAE7h
0x1000da2d  jmp     short loc_1000DA38
0x1000da2f  push    eax
0x1000da30  call    InternetCloseHandle
0x1000da36  xor     edi, edi
0x1000da38  push    ebx
0x1000da39  call    _MemFree@4; MemFree(x)
0x1000da3e  mov     eax, [esp+554h+var_540]
0x1000da42  lea     ecx, [esp+554h+MultiByteStr]
0x1000da46  mov     [esi], eax
0x1000da48  lea     edx, [ecx+1]
0x1000da4b  mov     eax, [esp+554h+var_53C]
0x1000da4f  mov     [esi+4], eax
0x1000da52  mov     eax, [esp+554h+var_538]
0x1000da56  mov     [esi+8], eax
0x1000da59  mov     eax, [esp+554h+var_534]
0x1000da5d  mov     [esi+0Ch], eax
0x1000da60  mov     eax, dword ptr [esp+554h+var_530]
0x1000da64  mov     [esi+10h], eax
0x1000da67  mov     eax, [esp+554h+var_52C]
0x1000da6b  mov     [esi+14h], eax
0x1000da6e  mov     eax, [esp+554h+var_528]
0x1000da72  mov     [esi+18h], eax
0x1000da75  mov     eax, [esp+554h+var_524]
0x1000da79  mov     [esi+1Ch], eax
0x1000da7c  mov     eax, [esp+554h+var_520]
0x1000da80  mov     [esi+20h], eax
0x1000da83  mov     eax, [esp+554h+var_51C]
0x1000da87  mov     [esi+24h], eax
0x1000da8a  mov     eax, [esp+554h+var_518]
0x1000da8e  mov     [esi+28h], eax
0x1000da91  mov     al, [ecx]
0x1000da93  inc     ecx
0x1000da94  test    al, al
0x1000da96  jnz     short loc_1000DA91
0x1000da98  mov     ebx, ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1000da9e  lea     eax, [esi+2Ch]
0x1000daa1  push    104h; cchWideChar
0x1000daa6  push    eax; lpWideCharStr
0x1000daa7  sub     ecx, edx
0x1000daa9  lea     eax, [esp+55Ch+MultiByteStr]
0x1000daad  push    ecx; cbMultiByte
0x1000daae  push    eax; lpMultiByteStr
0x1000daaf  push    0; dwFlags
0x1000dab1  push    0; CodePage
0x1000dab3  call    ebx ; MultiByteToWideChar(x,x,x,x,x,x); MultiByteToWideChar(x,x,x,x,x,x)
0x1000dab5  xor     ecx, ecx
0x1000dab7  mov     [esi+eax*2+2Ch], cx
0x1000dabc  lea     ecx, [esp+554h+var_410]
0x1000dac3  lea     edx, [ecx+1]
0x1000dac6  mov     al, [ecx]
0x1000dac8  inc     ecx
0x1000dac9  test    al, al
0x1000dacb  jnz     short loc_1000DAC6
0x1000dacd  push    0Eh; cchWideChar
0x1000dacf  lea     eax, [esi+234h]
0x1000dad5  sub     ecx, edx
0x1000dad7  push    eax; lpWideCharStr
0x1000dad8  push    ecx; cbMultiByte
0x1000dad9  lea     eax, [esp+560h+var_410]
0x1000dae0  push    eax; lpMultiByteStr
0x1000dae1  push    0; dwFlags
0x1000dae3  push    0; CodePage
0x1000dae5  call    ebx ; MultiByteToWideChar(x,x,x,x,x,x); MultiByteToWideChar(x,x,x,x,x,x)
0x1000dae7  xor     ecx, ecx
0x1000dae9  push    ebp
0x1000daea  mov     [esi+eax*2+234h], cx
0x1000daf2  call    InternetCloseHandle
0x1000daf8  mov     eax, edi
0x1000dafa  pop     ebp
0x1000dafb  pop     ebx
0x1000dafc  mov     ecx, [esp+550h+var_4]
0x1000db03  pop     edi
0x1000db04  pop     esi
0x1000db05  xor     ecx, esp; StackCookie
0x1000db07  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000db0c  add     esp, 548h
0x1000db12  retn    8
```
