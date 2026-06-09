# NetFindFirstMatchingFile(x,x,x,x)

- ea: `0x10023563`
- end: `0x10023734`
- name: `_NetFindFirstMatchingFile@16`
- size: `465`
- prototype: `int __thiscall(wchar_t *FullPath, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update`

## callers

- `0x10026772`

## callees

- `0x10018b80`
- `0x100224b6`
- `0x10022628`
- `0x10022e8a`
- `0x10023563`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100235e5`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100235e5`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023628`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002366e`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023628`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002366e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10023710`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10023710`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1002369b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1002369b`

## pseudocode

```c
int __fastcall NetFindFirstMatchingFile(wchar_t *FullPath, WCHAR *a2, _DWORD *a3, int *a4)
{
  int result; // eax
  int v6; // esi
  CHAR *v7; // ebx
  HINTERNET v8; // edi
  HINTERNET FirstFileA; // esi
  int InternetError; // edi
  HINTERNET v12; // [esp+1Ch] [ebp-54Ch] BYREF
  struct _WIN32_FIND_DATAA v13; // [esp+20h] [ebp-548h] BYREF
  wchar_t Ext[256]; // [esp+160h] [ebp-408h] BYREF
  wchar_t Filename[258]; // [esp+360h] [ebp-208h] BYREF

  if ( !dword_1003AE18 && !NetInitializeInternetServices() )
    return -20163;
  result = SetupForFTP((int)FullPath, &v12);
  if ( result )
  {
    *a4 = result;
  }
  else
  {
    __wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
    WCSCAT2(Filename, Ext, 0x100u);
    v6 = WideCharToMultiByte(0, 0, Filename, wcslen(Filename), 0, 0, 0, 0);
    v7 = (CHAR *)MemAllocate(v6 + 1);
    if ( v7 )
    {
      WideCharToMultiByte(0, 0, Filename, wcslen(Filename), v7, v6, 0, 0);
      v8 = v12;
      FirstFileA = FtpFindFirstFileA(v12, v7, &v13, 0, 0);
      if ( FirstFileA )
      {
        MemFree(v7);
        MultiByteToWideChar(0, 0, v13.cFileName, strlen(v13.cFileName) + 1, a2, 255);
        *a3 = v8;
        a3[1] = FirstFileA;
        return 0;
      }
      else
      {
        if ( GetLastError() == 18 )
        {
          InternetError = -1305;
        }
        else
        {
          InternetError = GetInternetError();
          *a4 = InternetError;
        }
        MemFree(v7);
        InternetCloseHandle(v12);
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
0x10023563  mov     edi, edi
0x10023565  push    ebp
0x10023566  mov     ebp, esp
0x10023568  sub     esp, 55Ch
0x1002356e  mov     eax, ___security_cookie
0x10023573  xor     eax, ebp
0x10023575  mov     [ebp+var_4], eax
0x10023578  cmp     dword_1003AE18, 0
0x1002357f  mov     eax, [ebp+arg_0]
0x10023582  push    ebx
0x10023583  mov     ebx, [ebp+arg_4]
0x10023586  push    esi
0x10023587  push    edi
0x10023588  mov     [ebp+lpWideCharStr], edx
0x1002358e  mov     esi, ecx
0x10023590  mov     [ebp+var_558], eax
0x10023596  mov     [ebp+var_550], ebx
0x1002359c  jnz     short loc_100235B1
0x1002359e  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x100235a3  test    eax, eax
0x100235a5  jnz     short loc_100235B1
0x100235a7  mov     eax, 0FFFFB13Dh
0x100235ac  jmp     loc_10023723
0x100235b1  lea     edx, [ebp+var_54C]
0x100235b7  mov     ecx, esi
0x100235b9  call    SetupForFTP
0x100235be  test    eax, eax
0x100235c0  jz      short loc_100235C9
0x100235c2  mov     [ebx], eax
0x100235c4  jmp     loc_10023723
0x100235c9  mov     edi, 100h
0x100235ce  lea     eax, [ebp+Ext]
0x100235d4  push    edi; ExtCount
0x100235d5  push    eax; Ext
0x100235d6  push    edi; FilenameCount
0x100235d7  lea     eax, [ebp+Filename]
0x100235dd  push    eax; Filename
0x100235de  xor     eax, eax
0x100235e0  push    eax; DirCount
0x100235e1  push    eax; Dir
0x100235e2  push    eax; DriveCount
0x100235e3  push    eax; Drive
0x100235e4  push    esi; FullPath
0x100235e5  call    ds:__imp___wsplitpath_s
0x100235eb  add     esp, 24h
0x100235ee  lea     edx, [ebp+Ext]
0x100235f4  lea     ecx, [ebp+Filename]
0x100235fa  push    edi
0x100235fb  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10023600  lea     ecx, [ebp+Filename]
0x10023606  xor     edi, edi
0x10023608  lea     edx, [ecx+2]
0x1002360b  mov     ax, [ecx]
0x1002360e  add     ecx, 2
0x10023611  cmp     ax, di
0x10023614  jnz     short loc_1002360B
0x10023616  push    edi; lpUsedDefaultChar
0x10023617  push    edi; lpDefaultChar
0x10023618  push    edi; cbMultiByte
0x10023619  push    edi; lpMultiByteStr
0x1002361a  sub     ecx, edx
0x1002361c  lea     eax, [ebp+Filename]
0x10023622  sar     ecx, 1
0x10023624  push    ecx; cchWideChar
0x10023625  push    eax; lpWideCharStr
0x10023626  push    edi; dwFlags
0x10023627  push    edi; CodePage
0x10023628  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1002362e  mov     esi, eax
0x10023630  lea     ecx, [esi+1]
0x10023633  call    _MemAllocate@4; MemAllocate(x)
0x10023638  mov     ebx, eax
0x1002363a  test    ebx, ebx
0x1002363c  jnz     short loc_10023648
0x1002363e  mov     eax, 0FFFFFC0Dh
0x10023643  jmp     loc_10023723
0x10023648  lea     ecx, [ebp+Filename]
0x1002364e  lea     edx, [ecx+2]
0x10023651  mov     ax, [ecx]
0x10023654  add     ecx, 2
0x10023657  cmp     ax, di
0x1002365a  jnz     short loc_10023651
0x1002365c  push    edi; lpUsedDefaultChar
0x1002365d  push    edi; lpDefaultChar
0x1002365e  push    esi; cbMultiByte
0x1002365f  push    ebx; lpMultiByteStr
0x10023660  sub     ecx, edx
0x10023662  lea     eax, [ebp+Filename]
0x10023668  sar     ecx, 1
0x1002366a  push    ecx; cchWideChar
0x1002366b  push    eax; lpWideCharStr
0x1002366c  push    edi; dwFlags
0x1002366d  push    edi; CodePage
0x1002366e  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023674  mov     esi, FtpFindFirstFileA
0x1002367a  lea     eax, [ebp+var_548]
0x10023680  push    edi
0x10023681  push    edi
0x10023682  mov     edi, [ebp+var_54C]
0x10023688  mov     ecx, esi
0x1002368a  push    eax
0x1002368b  push    ebx
0x1002368c  push    edi
0x1002368d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023693  call    esi ; FtpFindFirstFileA
0x10023695  mov     esi, eax
0x10023697  test    esi, esi
0x10023699  jnz     short loc_100236DD
0x1002369b  call    ds:__imp__GetLastError@0; GetLastError()
0x100236a1  cmp     eax, 12h
0x100236a4  jz      short loc_100236B7
0x100236a6  call    GetInternetError
0x100236ab  mov     edi, eax
0x100236ad  mov     eax, [ebp+var_550]
0x100236b3  mov     [eax], edi
0x100236b5  jmp     short loc_100236BC
0x100236b7  mov     edi, 0FFFFFAE7h
0x100236bc  mov     ecx, ebx
0x100236be  call    _MemFree@4; MemFree(x)
0x100236c3  push    [ebp+var_54C]
0x100236c9  mov     esi, InternetCloseHandle
0x100236cf  mov     ecx, esi
0x100236d1  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100236d7  call    esi ; InternetCloseHandle
0x100236d9  mov     eax, edi
0x100236db  jmp     short loc_10023723
0x100236dd  mov     ecx, ebx
0x100236df  call    _MemFree@4; MemFree(x)
0x100236e4  lea     ecx, [ebp+MultiByteStr]
0x100236ea  lea     edx, [ecx+1]
0x100236ed  mov     al, [ecx]
0x100236ef  inc     ecx
0x100236f0  test    al, al
0x100236f2  jnz     short loc_100236ED
0x100236f4  push    0FFh; cchWideChar
0x100236f9  push    [ebp+lpWideCharStr]; lpWideCharStr
0x100236ff  sub     ecx, edx
0x10023701  lea     eax, [ecx+1]
0x10023704  push    eax; cbMultiByte
0x10023705  lea     eax, [ebp+MultiByteStr]
0x1002370b  push    eax; lpMultiByteStr
0x1002370c  xor     eax, eax
0x1002370e  push    eax; dwFlags
0x1002370f  push    eax; CodePage
0x10023710  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x10023716  mov     eax, [ebp+var_558]
0x1002371c  mov     [eax], edi
0x1002371e  mov     [eax+4], esi
0x10023721  xor     eax, eax
0x10023723  mov     ecx, [ebp+var_4]
0x10023726  pop     edi
0x10023727  pop     esi
0x10023728  xor     ecx, ebp; StackCookie
0x1002372a  pop     ebx
0x1002372b  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10023730  leave
0x10023731  retn    8
```
