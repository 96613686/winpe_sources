# NetFileInfo(x,x)

- ea: `0x10023815`
- end: `0x10023a87`
- name: `_NetFileInfo@8`
- size: `626`
- prototype: `int __thiscall(wchar_t *FullPath)`
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x10011280`

## callees

- `0x10018b80`
- `0x100224b6`
- `0x10022628`
- `0x10022e8a`
- `0x10023815`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x10035b40`
- `0x10035f40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10023884`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10023884`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100238c7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002391b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100238c7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002391b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10023a1e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10023a50`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10023a1e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x10023a50`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1002395a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1002395a`

## pseudocode

```c
int __fastcall NetFileInfo(wchar_t *FullPath, int a2)
{
  int result; // eax
  int v5; // esi
  CHAR *v6; // ebx
  void *FirstFileA; // eax
  int InternetError; // ebx
  DWORD dwHighDateTime; // ecx
  DWORD nFileSizeHigh; // eax
  DWORD v11; // ecx
  DWORD nFileSizeLow; // eax
  DWORD v13; // ecx
  DWORD dwReserved0; // eax
  int v15; // eax
  BOOL (__stdcall *v16)(HINTERNET); // esi
  HINTERNET v17; // [esp-4h] [ebp-564h]
  CHAR *v18; // [esp+Ch] [ebp-554h]
  HINTERNET v19; // [esp+14h] [ebp-54Ch] BYREF
  struct _WIN32_FIND_DATAA v20; // [esp+18h] [ebp-548h] BYREF
  wchar_t Ext[256]; // [esp+158h] [ebp-408h] BYREF
  wchar_t Filename[258]; // [esp+358h] [ebp-208h] BYREF

  if ( !dword_1003AE18 && !NetInitializeInternetServices() )
    return -20163;
  result = SetupForFTP((int)FullPath, &v19);
  if ( !result )
  {
    __wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
    WCSCAT2(Filename, Ext, 0x100u);
    v5 = WideCharToMultiByte(0, 0, Filename, wcslen(Filename), 0, 0, 0, 0);
    v6 = (CHAR *)MemAllocate(v5 + 1);
    v18 = v6;
    if ( v6 )
    {
      WideCharToMultiByte(0, 0, Filename, wcslen(Filename), v6, v5, 0, 0);
      memset(&v20, 0, sizeof(v20));
      FirstFileA = FtpFindFirstFileA(v19, v6, &v20, 0, 0);
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
      MemFree(v18);
      dwHighDateTime = v20.ftCreationTime.dwHighDateTime;
      *(_DWORD *)a2 = v20.dwFileAttributes;
      *(_DWORD *)(a2 + 4) = v20.ftCreationTime.dwLowDateTime;
      *(_DWORD *)(a2 + 12) = v20.ftLastAccessTime.dwLowDateTime;
      *(_DWORD *)(a2 + 20) = v20.ftLastWriteTime.dwLowDateTime;
      nFileSizeHigh = v20.nFileSizeHigh;
      *(_DWORD *)(a2 + 8) = dwHighDateTime;
      v11 = v20.ftLastAccessTime.dwHighDateTime;
      *(_DWORD *)(a2 + 28) = nFileSizeHigh;
      nFileSizeLow = v20.nFileSizeLow;
      *(_DWORD *)(a2 + 16) = v11;
      v13 = v20.ftLastWriteTime.dwHighDateTime;
      *(_DWORD *)(a2 + 32) = nFileSizeLow;
      dwReserved0 = v20.dwReserved0;
      *(_DWORD *)(a2 + 24) = v13;
      *(_DWORD *)(a2 + 36) = dwReserved0;
      *(_DWORD *)(a2 + 40) = v20.dwReserved1;
      *(_WORD *)(a2 + 2 * MultiByteToWideChar(0, 0, v20.cFileName, strlen(v20.cFileName), (LPWSTR)(a2 + 44), 260) + 44) = 0;
      v15 = MultiByteToWideChar(0, 0, v20.cAlternateFileName, strlen(v20.cAlternateFileName), (LPWSTR)(a2 + 564), 14);
      v17 = v19;
      v16 = InternetCloseHandle;
      *(_WORD *)(a2 + 2 * v15 + 564) = 0;
      ((void (__thiscall *)(BOOL (__stdcall *)(HINTERNET), HINTERNET))v16)(v16, v17);
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
0x10023815  mov     edi, edi
0x10023817  push    ebp
0x10023818  mov     ebp, esp
0x1002381a  sub     esp, 554h
0x10023820  mov     eax, ___security_cookie
0x10023825  xor     eax, ebp
0x10023827  mov     [ebp+var_4], eax
0x1002382a  cmp     dword_1003AE18, 0
0x10023831  push    ebx
0x10023832  push    esi
0x10023833  push    edi
0x10023834  mov     edi, edx
0x10023836  mov     esi, ecx
0x10023838  jnz     short loc_1002384D
0x1002383a  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x1002383f  test    eax, eax
0x10023841  jnz     short loc_1002384D
0x10023843  mov     eax, 0FFFFB13Dh
0x10023848  jmp     loc_10023A78
0x1002384d  lea     edx, [ebp+var_54C]
0x10023853  mov     ecx, esi
0x10023855  call    SetupForFTP
0x1002385a  test    eax, eax
0x1002385c  jnz     loc_10023A78
0x10023862  mov     ebx, 100h
0x10023867  lea     eax, [ebp+Ext]
0x1002386d  push    ebx; ExtCount
0x1002386e  push    eax; Ext
0x1002386f  push    ebx; FilenameCount
0x10023870  lea     eax, [ebp+Filename]
0x10023876  push    eax; Filename
0x10023877  xor     eax, eax
0x10023879  push    eax; DirCount
0x1002387a  push    eax; Dir
0x1002387b  push    eax; DriveCount
0x1002387c  push    eax; Drive
0x1002387d  push    esi; FullPath
0x1002387e  mov     [ebp+var_550], eax
0x10023884  call    ds:__imp___wsplitpath_s
0x1002388a  add     esp, 24h
0x1002388d  lea     edx, [ebp+Ext]
0x10023893  lea     ecx, [ebp+Filename]
0x10023899  push    ebx
0x1002389a  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002389f  lea     ecx, [ebp+Filename]
0x100238a5  xor     ebx, ebx
0x100238a7  lea     edx, [ecx+2]
0x100238aa  mov     ax, [ecx]
0x100238ad  add     ecx, 2
0x100238b0  cmp     ax, bx
0x100238b3  jnz     short loc_100238AA
0x100238b5  push    ebx; lpUsedDefaultChar
0x100238b6  push    ebx; lpDefaultChar
0x100238b7  push    ebx; cbMultiByte
0x100238b8  push    ebx; lpMultiByteStr
0x100238b9  sub     ecx, edx
0x100238bb  lea     eax, [ebp+Filename]
0x100238c1  sar     ecx, 1
0x100238c3  push    ecx; cchWideChar
0x100238c4  push    eax; lpWideCharStr
0x100238c5  push    ebx; dwFlags
0x100238c6  push    ebx; CodePage
0x100238c7  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x100238cd  mov     esi, eax
0x100238cf  lea     ecx, [esi+1]
0x100238d2  call    _MemAllocate@4; MemAllocate(x)
0x100238d7  mov     ebx, eax
0x100238d9  mov     [ebp+var_554], ebx
0x100238df  test    ebx, ebx
0x100238e1  jnz     short loc_100238ED
0x100238e3  mov     eax, 0FFFFFC0Dh
0x100238e8  jmp     loc_10023A78
0x100238ed  lea     ecx, [ebp+Filename]
0x100238f3  lea     edx, [ecx+2]
0x100238f6  mov     ax, [ecx]
0x100238f9  add     ecx, 2
0x100238fc  cmp     ax, word ptr [ebp+var_550]
0x10023903  jnz     short loc_100238F6
0x10023905  xor     eax, eax
0x10023907  sub     ecx, edx
0x10023909  push    eax; lpUsedDefaultChar
0x1002390a  push    eax; lpDefaultChar
0x1002390b  push    esi; cbMultiByte
0x1002390c  push    ebx; lpMultiByteStr
0x1002390d  sar     ecx, 1
0x1002390f  lea     eax, [ebp+Filename]
0x10023915  push    ecx; cchWideChar
0x10023916  push    eax; lpWideCharStr
0x10023917  xor     esi, esi
0x10023919  push    esi; dwFlags
0x1002391a  push    esi; CodePage
0x1002391b  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023921  push    140h; Size
0x10023926  lea     eax, [ebp+var_548]
0x1002392c  push    esi; Val
0x1002392d  push    eax; void *
0x1002392e  call    _memset
0x10023933  add     esp, 0Ch
0x10023936  lea     eax, [ebp+var_548]
0x1002393c  push    esi
0x1002393d  push    esi
0x1002393e  mov     esi, FtpFindFirstFileA
0x10023944  mov     ecx, esi
0x10023946  push    eax
0x10023947  push    ebx
0x10023948  push    [ebp+var_54C]
0x1002394e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023954  call    esi ; FtpFindFirstFileA
0x10023956  test    eax, eax
0x10023958  jnz     short loc_10023977
0x1002395a  call    ds:__imp__GetLastError@0; GetLastError()
0x10023960  cmp     eax, 12h
0x10023963  jz      short loc_1002396E
0x10023965  call    GetInternetError
0x1002396a  mov     ebx, eax
0x1002396c  jmp     short loc_10023973
0x1002396e  mov     ebx, 0FFFFFAE7h
0x10023973  xor     esi, esi
0x10023975  jmp     short loc_1002398C
0x10023977  mov     esi, InternetCloseHandle
0x1002397d  mov     ecx, esi
0x1002397f  push    eax
0x10023980  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023986  call    esi ; InternetCloseHandle
0x10023988  xor     esi, esi
0x1002398a  mov     ebx, esi
0x1002398c  mov     ecx, [ebp+var_554]
0x10023992  call    _MemFree@4; MemFree(x)
0x10023997  mov     eax, [ebp+var_548]
0x1002399d  mov     ecx, [ebp+var_540]
0x100239a3  mov     [edi], eax
0x100239a5  mov     eax, [ebp+var_544]
0x100239ab  mov     [edi+4], eax
0x100239ae  mov     eax, [ebp+var_53C]
0x100239b4  mov     [edi+0Ch], eax
0x100239b7  mov     eax, [ebp+var_534]
0x100239bd  mov     [edi+14h], eax
0x100239c0  mov     eax, [ebp+var_52C]
0x100239c6  mov     [edi+8], ecx
0x100239c9  mov     ecx, [ebp+var_538]
0x100239cf  mov     [edi+1Ch], eax
0x100239d2  mov     eax, [ebp+var_528]
0x100239d8  mov     [edi+10h], ecx
0x100239db  mov     ecx, [ebp+var_530]
0x100239e1  mov     [edi+20h], eax
0x100239e4  mov     eax, [ebp+var_524]
0x100239ea  mov     [edi+18h], ecx
0x100239ed  lea     ecx, [ebp+MultiByteStr]
0x100239f3  mov     [edi+24h], eax
0x100239f6  lea     edx, [ecx+1]
0x100239f9  mov     eax, [ebp+var_520]
0x100239ff  mov     [edi+28h], eax
0x10023a02  mov     al, [ecx]
0x10023a04  inc     ecx
0x10023a05  test    al, al
0x10023a07  jnz     short loc_10023A02
0x10023a09  push    104h; cchWideChar
0x10023a0e  lea     eax, [edi+2Ch]
0x10023a11  sub     ecx, edx
0x10023a13  push    eax; lpWideCharStr
0x10023a14  push    ecx; cbMultiByte
0x10023a15  lea     eax, [ebp+MultiByteStr]
0x10023a1b  push    eax; lpMultiByteStr
0x10023a1c  push    esi; dwFlags
0x10023a1d  push    esi; CodePage
0x10023a1e  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x10023a24  xor     ecx, ecx
0x10023a26  mov     [edi+eax*2+2Ch], cx
0x10023a2b  lea     ecx, [ebp+var_418]
0x10023a31  lea     edx, [ecx+1]
0x10023a34  mov     al, [ecx]
0x10023a36  inc     ecx
0x10023a37  test    al, al
0x10023a39  jnz     short loc_10023A34
0x10023a3b  push    0Eh; cchWideChar
0x10023a3d  lea     eax, [edi+234h]
0x10023a43  sub     ecx, edx
0x10023a45  push    eax; lpWideCharStr
0x10023a46  push    ecx; cbMultiByte
0x10023a47  lea     eax, [ebp+var_418]
0x10023a4d  push    eax; lpMultiByteStr
0x10023a4e  push    esi; dwFlags
0x10023a4f  push    esi; CodePage
0x10023a50  call    ds:__imp__MultiByteToWideChar@24; MultiByteToWideChar(x,x,x,x,x,x)
0x10023a56  push    [ebp+var_54C]
0x10023a5c  mov     esi, InternetCloseHandle
0x10023a62  xor     ecx, ecx
0x10023a64  mov     [edi+eax*2+234h], cx
0x10023a6c  mov     ecx, esi
0x10023a6e  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023a74  call    esi ; InternetCloseHandle
0x10023a76  mov     eax, ebx
0x10023a78  mov     ecx, [ebp+var_4]
0x10023a7b  pop     edi
0x10023a7c  pop     esi
0x10023a7d  xor     ecx, ebp; StackCookie
0x10023a7f  pop     ebx
0x10023a80  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10023a85  leave
0x10023a86  retn
```
