# NetFindFirstMatchingFile(x,x,x,x)

- ea: `0x1000db20`
- end: `0x1000dd0b`
- name: `_NetFindFirstMatchingFile@16`
- size: `491`
- prototype: `int __stdcall(wchar_t *FullPath, int, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x1000b6d0`

## callees

- `0x1000ad60`
- `0x1000b070`
- `0x1000b200`
- `0x1000c2f0`
- `0x1000ca60`
- `0x1000db20`
- `0x1000ddd0`
- `0x1000e950`
- `0x1002b81a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000dc72`
- `KERNEL32!GetLastError` at `0x1000dc72`
- `KERNEL32!WideCharToMultiByte` at `0x1000dc0c`
- `KERNEL32!WideCharToMultiByte` at `0x1000dc55`
- `KERNEL32!WideCharToMultiByte` at `0x1000dbeb`
- `KERNEL32!MultiByteToWideChar` at `0x1000dcdf`
- `KERNEL32!MultiByteToWideChar` at `0x1000dcdf`

## pseudocode

```c
int __stdcall NetFindFirstMatchingFile(wchar_t *FullPath, WCHAR *a2, _DWORD *a3, int *a4)
{
  int result; // eax
  int v5; // ebp
  CHAR *v6; // edi
  void *v7; // ebp
  HINTERNET FirstFileA; // esi
  int InternetError; // esi
  HINTERNET v10; // [esp+1Ch] [ebp-548h] BYREF
  struct _WIN32_FIND_DATAA v11; // [esp+20h] [ebp-544h] BYREF
  wchar_t pszDest[256]; // [esp+160h] [ebp-404h] BYREF
  wchar_t pszSrc[256]; // [esp+360h] [ebp-204h] BYREF

  if ( !dword_10040FB8 && !NetInitializeInternetServices() )
    return -20163;
  result = SetupForFTP(FullPath, &v10);
  if ( result )
  {
    *a4 = result;
  }
  else
  {
    SplitPath(FullPath, 0, 0, 0, 0, pszDest, 0x100u, pszSrc, 0x100u);
    StringCchCatW(pszDest, 0x100u, pszSrc);
    v5 = WideCharToMultiByte(0, 0, pszDest, wcslen(pszDest), 0, 0, 0, 0);
    v6 = (CHAR *)MemAllocate(v5 + 1);
    if ( v6 )
    {
      WideCharToMultiByte(0, 0, pszDest, wcslen(pszDest), v6, v5, 0, 0);
      v7 = v10;
      FirstFileA = FtpFindFirstFileA(v10, v6, &v11, 0, 0);
      if ( FirstFileA )
      {
        MemFree(v6);
        MultiByteToWideChar(0, 0, v11.cFileName, strlen(v11.cFileName) + 1, a2, 255);
        *a3 = v7;
        a3[1] = FirstFileA;
        return 0;
      }
      else if ( GetLastError() == 18 )
      {
        MemFree(v6);
        InternetCloseHandle(v7);
        return -1305;
      }
      else
      {
        InternetError = GetInternetError();
        *a4 = InternetError;
        MemFree(v6);
        InternetCloseHandle(v7);
        return InternetError;
      }
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
0x1000db20  sub     esp, 550h
0x1000db26  mov     eax, ___security_cookie
0x1000db2b  xor     eax, esp
0x1000db2d  mov     [esp+550h+var_4], eax
0x1000db34  cmp     dword_10040FB8, 0
0x1000db3b  mov     eax, [esp+550h+arg_4]
0x1000db42  push    ebx
0x1000db43  mov     ebx, [esp+554h+arg_C]
0x1000db4a  mov     [esp+554h+lpWideCharStr], eax
0x1000db4e  mov     eax, [esp+554h+arg_8]
0x1000db55  push    esi
0x1000db56  mov     esi, [esp+558h+FullPath]
0x1000db5d  mov     [esp+558h+var_550], eax
0x1000db61  jnz     short loc_1000DB76
0x1000db63  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x1000db68  test    eax, eax
0x1000db6a  jnz     short loc_1000DB76
0x1000db6c  mov     eax, 0FFFFB13Dh
0x1000db71  jmp     loc_1000DCF2
0x1000db76  lea     eax, [esp+558h+var_548]
0x1000db7a  push    eax
0x1000db7b  push    esi
0x1000db7c  call    SetupForFTP
0x1000db81  test    eax, eax
0x1000db83  jz      short loc_1000DB8C
0x1000db85  mov     [ebx], eax
0x1000db87  jmp     loc_1000DCF2
0x1000db8c  push    100h; ExtCount
0x1000db91  lea     eax, [esp+55Ch+pszSrc]
0x1000db98  push    eax; Ext
0x1000db99  push    100h; FilenameCount
0x1000db9e  lea     eax, [esp+564h+pszDest]
0x1000dba5  push    eax; Filename
0x1000dba6  push    0; DirCount
0x1000dba8  push    0; Dir
0x1000dbaa  push    0; DriveCount
0x1000dbac  push    0; Drive
0x1000dbae  push    esi; FullPath
0x1000dbaf  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1000dbb4  lea     eax, [esp+558h+pszSrc]
0x1000dbbb  push    eax; pszSrc
0x1000dbbc  push    100h; cchDest
0x1000dbc1  lea     eax, [esp+560h+pszDest]
0x1000dbc8  push    eax; pszDest
0x1000dbc9  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000dbce  lea     ecx, [esp+558h+pszDest]
0x1000dbd5  lea     edx, [ecx+2]
0x1000dbd8  jmp     short loc_1000DBE0
0x1000dbe0  mov     ax, [ecx]
0x1000dbe3  add     ecx, 2
0x1000dbe6  test    ax, ax
0x1000dbe9  jnz     short loc_1000DBE0
0x1000dbeb  mov     esi, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000dbf1  lea     eax, [esp+558h+pszDest]
0x1000dbf8  push    ebp
0x1000dbf9  push    edi
0x1000dbfa  push    0; lpUsedDefaultChar
0x1000dbfc  push    0; lpDefaultChar
0x1000dbfe  push    0; cbMultiByte
0x1000dc00  push    0; lpMultiByteStr
0x1000dc02  sub     ecx, edx
0x1000dc04  sar     ecx, 1
0x1000dc06  push    ecx; cchWideChar
0x1000dc07  push    eax; lpWideCharStr
0x1000dc08  push    0; dwFlags
0x1000dc0a  push    0; CodePage
0x1000dc0c  call    esi ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000dc0e  mov     ebp, eax
0x1000dc10  lea     ecx, [ebp+1]
0x1000dc13  push    ecx; Size
0x1000dc14  call    _MemAllocate@4; MemAllocate(x)
0x1000dc19  mov     edi, eax
0x1000dc1b  test    edi, edi
0x1000dc1d  jnz     short loc_1000DC29
0x1000dc1f  mov     eax, 0FFFFFC0Dh
0x1000dc24  jmp     loc_1000DCF0
0x1000dc29  lea     ecx, [esp+560h+pszDest]
0x1000dc30  lea     edx, [ecx+2]
0x1000dc33  mov     ax, [ecx]
0x1000dc36  add     ecx, 2
0x1000dc39  test    ax, ax
0x1000dc3c  jnz     short loc_1000DC33
0x1000dc3e  push    0; lpUsedDefaultChar
0x1000dc40  push    0; lpDefaultChar
0x1000dc42  push    ebp; cbMultiByte
0x1000dc43  push    edi; lpMultiByteStr
0x1000dc44  sub     ecx, edx
0x1000dc46  lea     eax, [esp+570h+pszDest]
0x1000dc4d  sar     ecx, 1
0x1000dc4f  push    ecx; cchWideChar
0x1000dc50  push    eax; lpWideCharStr
0x1000dc51  push    0; dwFlags
0x1000dc53  push    0; CodePage
0x1000dc55  call    esi ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000dc57  mov     ebp, [esp+560h+var_548]
0x1000dc5b  lea     eax, [esp+560h+var_544]
0x1000dc5f  push    0
0x1000dc61  push    0
0x1000dc63  push    eax
0x1000dc64  push    edi
0x1000dc65  push    ebp
0x1000dc66  call    FtpFindFirstFileA
0x1000dc6c  mov     esi, eax
0x1000dc6e  test    esi, esi
0x1000dc70  jnz     short loc_1000DCAD
0x1000dc72  call    ds:__imp__GetLastError@0; GetLastError()
0x1000dc78  cmp     eax, 12h
0x1000dc7b  jz      short loc_1000DC97
0x1000dc7d  call    GetInternetError
0x1000dc82  mov     esi, eax
0x1000dc84  push    edi
0x1000dc85  mov     [ebx], esi
0x1000dc87  call    _MemFree@4; MemFree(x)
0x1000dc8c  push    ebp
0x1000dc8d  call    InternetCloseHandle
0x1000dc93  mov     eax, esi
0x1000dc95  jmp     short loc_1000DCF0
0x1000dc97  push    edi
0x1000dc98  mov     esi, 0FFFFFAE7h
0x1000dc9d  call    _MemFree@4; MemFree(x)
0x1000dca2  push    ebp
0x1000dca3  call    InternetCloseHandle
0x1000dca9  mov     eax, esi
0x1000dcab  jmp     short loc_1000DCF0
0x1000dcad  push    edi
0x1000dcae  call    _MemFree@4; MemFree(x)
0x1000dcb3  lea     ecx, [esp+560h+MultiByteStr]
0x1000dcb7  lea     edx, [ecx+1]
0x1000dcba  lea     ebx, [ebx+0]
0x1000dcc0  mov     al, [ecx]
0x1000dcc2  inc     ecx
0x1000dcc3  test    al, al
0x1000dcc5  jnz     short loc_1000DCC0
0x1000dcc7  push    0FFh; cchWideChar
0x1000dccc  push    [esp+564h+lpWideCharStr]; lpWideCharStr
0x1000dcd0  sub     ecx, edx
0x1000dcd2  lea     eax, [ecx+1]
0x1000dcd5  push    eax; cbMultiByte
0x1000dcd6  lea     eax, [esp+56Ch+MultiByteStr]
0x1000dcda  push    eax; lpMultiByteStr
0x1000dcdb  push    0; dwFlags
0x1000dcdd  push    0; CodePage
0x1000dcdf  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x1000dce5  mov     eax, [esp+560h+var_550]
0x1000dce9  mov     [eax], ebp
0x1000dceb  mov     [eax+4], esi
0x1000dcee  xor     eax, eax
0x1000dcf0  pop     edi
0x1000dcf1  pop     ebp
0x1000dcf2  mov     ecx, [esp+558h+var_4]
0x1000dcf9  pop     esi
0x1000dcfa  pop     ebx
0x1000dcfb  xor     ecx, esp; StackCookie
0x1000dcfd  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1000dd02  add     esp, 550h
0x1000dd08  retn    10h
```
