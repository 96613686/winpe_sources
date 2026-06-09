# HTTPDownloadFile

- ea: `0x1000cbf0`
- end: `0x1000d01c`
- name: `HTTPDownloadFile`
- size: `1068`
- prototype: `int __stdcall(wchar_t *FullPath, STRSAFE_LPCWSTR pszSrc, int, size_t cchDest)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1000d720`

## callees

- `0x1000ad60`
- `0x1000ae20`
- `0x1000b070`
- `0x1000b200`
- `0x1000b3f0`
- `0x1000b410`
- `0x1000b5f0`
- `0x1000bd80`
- `0x1000c2f0`
- `0x1000ca20`
- `0x1000ca60`
- `0x1000cbf0`
- `0x1002b81a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000cff0`
- `KERNEL32!GetLastError` at `0x1000cff0`
- `KERNEL32!WideCharToMultiByte` at `0x1000cd02`
- `KERNEL32!WideCharToMultiByte` at `0x1000cd4f`
- `KERNEL32!WideCharToMultiByte` at `0x1000cded`
- `KERNEL32!WideCharToMultiByte` at `0x1000ce39`
- `KERNEL32!WideCharToMultiByte` at `0x1000cd02`
- `KERNEL32!WideCharToMultiByte` at `0x1000cd4f`
- `KERNEL32!WideCharToMultiByte` at `0x1000cded`
- `KERNEL32!WideCharToMultiByte` at `0x1000ce39`

## pseudocode

```c
int __stdcall HTTPDownloadFile(wchar_t *FullPath, STRSAFE_LPCWSTR pszSrc, wchar_t *a3, size_t cchDest)
{
  void *v4; // ebx
  void *v5; // edi
  WCHAR *v6; // ecx
  int v7; // edx
  WCHAR v8; // ax
  int v9; // esi
  CHAR *v10; // ebp
  int InternetError; // esi
  const CHAR *v12; // esi
  void *v13; // eax
  int v14; // esi
  int HTTPError; // eax
  int v16; // eax
  void *v17; // ecx
  CHAR *lpMultiByteStr; // [esp+90h] [ebp-840h]
  HANDLE hObject; // [esp+94h] [ebp-83Ch] BYREF
  LPCWCH lpWideCharStr; // [esp+98h] [ebp-838h]
  DWORD nNumberOfBytesToWrite; // [esp+9Ch] [ebp-834h] BYREF
  void *v23; // [esp+A0h] [ebp-830h]
  DWORD v24; // [esp+A4h] [ebp-82Ch] BYREF
  int v25; // [esp+A8h] [ebp-828h] BYREF
  HINTERNET v26; // [esp+ACh] [ebp-824h]
  DWORD v27; // [esp+B0h] [ebp-820h] BYREF
  WCHAR WideCharStr[262]; // [esp+B4h] [ebp-81Ch] BYREF
  wchar_t Filename[256]; // [esp+2C0h] [ebp-610h] BYREF
  CHAR v30[524]; // [esp+4C0h] [ebp-410h] BYREF
  wchar_t Ext[256]; // [esp+6CCh] [ebp-204h] BYREF

  v4 = 0;
  v5 = 0;
  lpWideCharStr = FullPath;
  v23 = 0;
  lpMultiByteStr = 0;
  hObject = 0;
  v27 = 4;
  v24 = 521;
  SplitPath(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
  StringCchCopyW(a3, cchDest, pszSrc);
  StringCchCatW(a3, cchDest, Filename);
  StringCchCatW(a3, cchDest, Ext);
  v6 = WideCharStr;
  v7 = 261;
  while ( v7 != -2147483385 )
  {
    v8 = *(WCHAR *)((char *)v6 + (char *)(FullPath + 7) - (char *)WideCharStr);
    if ( !v8 )
      break;
    *v6++ = v8;
    if ( !--v7 )
    {
      --v6;
      break;
    }
  }
  *v6 = 0;
  v9 = WideCharToMultiByte(0, 0, WideCharStr, wcslen(WideCharStr), 0, 0, 0, 0);
  v10 = (CHAR *)MemAllocate(v9 + 1);
  if ( v10 )
  {
    WideCharToMultiByte(0, 0, WideCharStr, wcslen(WideCharStr), v10, v9, 0, 0);
    v10[v9] = 0;
    v12 = v10;
    if ( *v10 )
    {
      while ( *v12 != 92 && *v12 != 47 )
      {
        if ( !*++v12 )
          goto LABEL_14;
      }
      *v12++ = 0;
    }
LABEL_14:
    v13 = InternetConnectA((HINTERNET)dword_10040FB8, v10, 0, 0, 0, 1u, 0, 0);
    v26 = v13;
    if ( !v13 )
    {
      InternetError = GetInternetError();
      goto LABEL_39;
    }
    if ( FtpSetCurrentDirectoryA(v13, v12) )
    {
      InternetError = -20158;
      goto LABEL_37;
    }
    MemFree(v10);
    v10 = 0;
    v14 = WideCharToMultiByte(0, 0, lpWideCharStr, wcslen(lpWideCharStr), 0, 0, 0, 0);
    lpMultiByteStr = (CHAR *)MemAllocate(v14 + 1);
    if ( !lpMultiByteStr )
    {
      InternetError = -1011;
      goto LABEL_37;
    }
    WideCharToMultiByte(0, 0, lpWideCharStr, wcslen(lpWideCharStr), lpMultiByteStr, v14, 0, 0);
    lpMultiByteStr[v14] = 0;
    if ( InternetCanonicalizeUrlA(lpMultiByteStr, v30, &v24, 0) )
    {
      v4 = InternetOpenUrlA((HINTERNET)dword_10040FB8, v30, "Accept: */*", 0xFFFFFFFF, 0, 0);
      if ( v4 )
      {
        if ( HttpQueryInfoA(v4, 0x20000013u, &v25, &v27, 0) )
        {
          if ( v25 != 200 )
          {
            HTTPError = GetHTTPError(v25);
LABEL_36:
            InternetError = HTTPError;
LABEL_37:
            InternetCloseHandle(v26);
            if ( v4 )
              InternetCloseHandle(v4);
            goto LABEL_39;
          }
          v16 = DOSCreateFile(a3, (int)&hObject);
          if ( v16 )
          {
            InternetError = -5036;
            if ( v16 == -4 )
              InternetError = -1807;
            goto LABEL_37;
          }
          v5 = (void *)MemAllocate(0x1000u);
          if ( !v5 )
          {
            InternetError = -1011;
            goto LABEL_37;
          }
          v23 = v5;
          if ( InternetReadFile(v4, v5, 0x1000u, &nNumberOfBytesToWrite) )
          {
            while ( nNumberOfBytesToWrite )
            {
              if ( DOSWriteFile(v17, hObject, v5, nNumberOfBytesToWrite) == 0xFFFF )
                goto LABEL_52;
              if ( !InternetReadFile(v4, v5, 0x1000u, &nNumberOfBytesToWrite) )
                goto LABEL_35;
            }
            InternetCloseHandle(v4);
            if ( !DOSCloseFile(hObject) )
            {
              MemFree(v5);
              InternetCloseHandle(v4);
              return 0;
            }
LABEL_52:
            InternetError = -1022;
            if ( GetLastError() == 112 )
              InternetError = -1808;
            goto LABEL_37;
          }
        }
      }
    }
LABEL_35:
    HTTPError = GetInternetError();
    goto LABEL_36;
  }
  InternetError = -1011;
LABEL_39:
  if ( hObject )
  {
    DOSCloseFile(hObject);
    DOSFileDelete(a3);
  }
  if ( v10 )
    MemFree(v10);
  if ( lpMultiByteStr )
    MemFree(lpMultiByteStr);
  if ( v5 )
    MemFree(v5);
  if ( v23 )
  {
    if ( v5 != v23 )
      MemFree(v23);
  }
  return InternetError;
}

```

## disassembly

```asm
0x1000cbf0  sub     esp, 844h
0x1000cbf6  mov     eax, ___security_cookie
0x1000cbfb  xor     eax, esp
0x1000cbfd  mov     [esp+844h+var_4], eax
0x1000cc04  mov     eax, [esp+844h+arg_8]
0x1000cc0b  push    ebx
0x1000cc0c  push    ebp
0x1000cc0d  mov     ebp, [esp+84Ch+FullPath]
0x1000cc14  xor     ebx, ebx
0x1000cc16  push    esi
0x1000cc17  push    edi
0x1000cc18  push    100h; ExtCount
0x1000cc1d  mov     [esp+858h+pszDest], eax
0x1000cc21  xor     edi, edi
0x1000cc23  xor     eax, eax
0x1000cc25  mov     [esp+858h+lpWideCharStr], ebp
0x1000cc29  mov     [esp+858h+var_830], eax
0x1000cc2d  mov     [esp+858h+lpMultiByteStr], eax
0x1000cc31  lea     eax, [esp+858h+Ext]
0x1000cc38  push    eax; Ext
0x1000cc39  push    100h; FilenameCount
0x1000cc3e  lea     eax, [esp+860h+Filename]
0x1000cc45  mov     [esp+860h+hObject], ebx
0x1000cc49  push    eax; Filename
0x1000cc4a  push    edi; DirCount
0x1000cc4b  push    edi; Dir
0x1000cc4c  push    edi; DriveCount
0x1000cc4d  push    edi; Drive
0x1000cc4e  push    ebp; FullPath
0x1000cc4f  mov     [esp+878h+var_820], 4
0x1000cc57  mov     [esp+878h+var_82C], 209h
0x1000cc5f  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1000cc64  push    [esp+854h+pszSrc]; pszSrc
0x1000cc6b  mov     esi, [esp+858h+cchDest]
0x1000cc72  push    esi; cchDest
0x1000cc73  push    [esp+85Ch+pszDest]; pszDest
0x1000cc77  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000cc7c  lea     eax, [esp+854h+Filename]
0x1000cc83  push    eax; pszSrc
0x1000cc84  push    esi; cchDest
0x1000cc85  push    [esp+85Ch+pszDest]; pszDest
0x1000cc89  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000cc8e  lea     eax, [esp+854h+Ext]
0x1000cc95  push    eax; pszSrc
0x1000cc96  push    esi; cchDest
0x1000cc97  push    [esp+85Ch+pszDest]; pszDest
0x1000cc9b  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000cca0  lea     ecx, [esp+854h+WideCharStr]
0x1000cca4  mov     edx, 105h
0x1000cca9  lea     esi, [ebp+0Eh]
0x1000ccac  mov     eax, ecx
0x1000ccae  sub     esi, eax
0x1000ccb0  lea     eax, [edx+7FFFFEF9h]
0x1000ccb6  test    eax, eax
0x1000ccb8  jz      short loc_1000CCCE
0x1000ccba  movzx   eax, word ptr [esi+ecx]
0x1000ccbe  test    ax, ax
0x1000ccc1  jz      short loc_1000CCCE
0x1000ccc3  mov     [ecx], ax
0x1000ccc6  add     ecx, 2
0x1000ccc9  dec     edx
0x1000ccca  jnz     short loc_1000CCB0
0x1000cccc  jmp     short loc_1000CCD2
0x1000ccce  test    edx, edx
0x1000ccd0  jnz     short loc_1000CCD5
0x1000ccd2  sub     ecx, 2
0x1000ccd5  xor     eax, eax
0x1000ccd7  mov     [ecx], ax
0x1000ccda  lea     ecx, [esp+854h+WideCharStr]
0x1000ccde  lea     edx, [ecx+2]
0x1000cce1  mov     ax, [ecx]
0x1000cce4  add     ecx, 2
0x1000cce7  test    ax, ax
0x1000ccea  jnz     short loc_1000CCE1
0x1000ccec  push    0; lpUsedDefaultChar
0x1000ccee  push    0; lpDefaultChar
0x1000ccf0  push    0; cbMultiByte
0x1000ccf2  push    0; lpMultiByteStr
0x1000ccf4  sub     ecx, edx
0x1000ccf6  lea     eax, [esp+864h+WideCharStr]
0x1000ccfa  sar     ecx, 1
0x1000ccfc  push    ecx; cchWideChar
0x1000ccfd  push    eax; lpWideCharStr
0x1000ccfe  push    0; dwFlags
0x1000cd00  push    0; CodePage
0x1000cd02  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000cd08  mov     esi, eax
0x1000cd0a  lea     eax, [esi+1]
0x1000cd0d  push    eax; Size
0x1000cd0e  call    _MemAllocate@4; MemAllocate(x)
0x1000cd13  mov     ebp, eax
0x1000cd15  test    ebp, ebp
0x1000cd17  jnz     short loc_1000CD23
0x1000cd19  mov     esi, 0FFFFFC0Dh
0x1000cd1e  jmp     loc_1000CF74
0x1000cd23  lea     ecx, [esp+854h+WideCharStr]
0x1000cd27  lea     edx, [ecx+2]
0x1000cd2a  lea     ebx, [ebx+0]
0x1000cd30  mov     ax, [ecx]
0x1000cd33  add     ecx, 2
0x1000cd36  test    ax, ax
0x1000cd39  jnz     short loc_1000CD30
0x1000cd3b  push    0; lpUsedDefaultChar
0x1000cd3d  push    0; lpDefaultChar
0x1000cd3f  push    esi; cbMultiByte
0x1000cd40  push    ebp; lpMultiByteStr
0x1000cd41  sub     ecx, edx
0x1000cd43  lea     eax, [esp+864h+WideCharStr]
0x1000cd47  sar     ecx, 1
0x1000cd49  push    ecx; cchWideChar
0x1000cd4a  push    eax; lpWideCharStr
0x1000cd4b  push    0; dwFlags
0x1000cd4d  push    0; CodePage
0x1000cd4f  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000cd55  mov     [esi+ebp], bl
0x1000cd58  mov     esi, ebp
0x1000cd5a  cmp     [ebp+0], bl
0x1000cd5d  jz      short loc_1000CD74
0x1000cd5f  nop
0x1000cd60  mov     al, [esi]
0x1000cd62  cmp     al, 5Ch ; '\'
0x1000cd64  jz      short loc_1000CD71
0x1000cd66  cmp     al, 2Fh ; '/'
0x1000cd68  jz      short loc_1000CD71
0x1000cd6a  inc     esi
0x1000cd6b  cmp     [esi], bl
0x1000cd6d  jnz     short loc_1000CD60
0x1000cd6f  jmp     short loc_1000CD74
0x1000cd71  mov     [esi], bl
0x1000cd73  inc     esi
0x1000cd74  push    0
0x1000cd76  push    0
0x1000cd78  push    1
0x1000cd7a  push    0
0x1000cd7c  push    0
0x1000cd7e  push    0
0x1000cd80  push    ebp
0x1000cd81  push    dword_10040FB8
0x1000cd87  call    InternetConnectA
0x1000cd8d  mov     [esp+854h+var_824], eax
0x1000cd91  test    eax, eax
0x1000cd93  jnz     short loc_1000CDA1
0x1000cd95  call    GetInternetError
0x1000cd9a  mov     esi, eax
0x1000cd9c  jmp     loc_1000CF74
0x1000cda1  push    esi
0x1000cda2  push    eax
0x1000cda3  call    FtpSetCurrentDirectoryA
0x1000cda9  test    eax, eax
0x1000cdab  jz      short loc_1000CDB7
0x1000cdad  mov     esi, 0FFFFB142h
0x1000cdb2  jmp     loc_1000CF5F
0x1000cdb7  push    ebp
0x1000cdb8  call    _MemFree@4; MemFree(x)
0x1000cdbd  mov     esi, [esp+854h+lpWideCharStr]
0x1000cdc1  xor     ebp, ebp
0x1000cdc3  mov     ecx, esi
0x1000cdc5  lea     edx, [ecx+2]
0x1000cdc8  jmp     short loc_1000CDD0
0x1000cdd0  mov     ax, [ecx]
0x1000cdd3  add     ecx, 2
0x1000cdd6  test    ax, ax
0x1000cdd9  jnz     short loc_1000CDD0
0x1000cddb  push    0; lpUsedDefaultChar
0x1000cddd  push    0; lpDefaultChar
0x1000cddf  push    0; cbMultiByte
0x1000cde1  push    0; lpMultiByteStr
0x1000cde3  sub     ecx, edx
0x1000cde5  sar     ecx, 1
0x1000cde7  push    ecx; cchWideChar
0x1000cde8  push    esi; lpWideCharStr
0x1000cde9  push    0; dwFlags
0x1000cdeb  push    0; CodePage
0x1000cded  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000cdf3  mov     esi, eax
0x1000cdf5  lea     eax, [esi+1]
0x1000cdf8  push    eax; Size
0x1000cdf9  call    _MemAllocate@4; MemAllocate(x)
0x1000cdfe  mov     [esp+854h+lpMultiByteStr], eax
0x1000ce02  test    eax, eax
0x1000ce04  jnz     short loc_1000CE10
0x1000ce06  mov     esi, 0FFFFFC0Dh
0x1000ce0b  jmp     loc_1000CF5F
0x1000ce10  mov     ecx, [esp+854h+lpWideCharStr]
0x1000ce14  lea     edx, [ecx+2]
0x1000ce17  mov     ax, [ecx]
0x1000ce1a  add     ecx, 2
0x1000ce1d  test    ax, ax
0x1000ce20  jnz     short loc_1000CE17
0x1000ce22  mov     eax, [esp+854h+lpMultiByteStr]
0x1000ce26  sub     ecx, edx
0x1000ce28  push    0; lpUsedDefaultChar
0x1000ce2a  push    0; lpDefaultChar
0x1000ce2c  push    esi; cbMultiByte
0x1000ce2d  push    eax; lpMultiByteStr
0x1000ce2e  sar     ecx, 1
0x1000ce30  push    ecx; cchWideChar
0x1000ce31  push    [esp+868h+lpWideCharStr]; lpWideCharStr
0x1000ce35  push    0; dwFlags
0x1000ce37  push    0; CodePage
0x1000ce39  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000ce3f  mov     eax, [esp+854h+lpMultiByteStr]
0x1000ce43  lea     ecx, [esp+854h+var_82C]
0x1000ce47  push    0
0x1000ce49  push    ecx
0x1000ce4a  lea     ecx, [esp+85Ch+var_410]
0x1000ce51  push    ecx
0x1000ce52  push    eax
0x1000ce53  mov     [esi+eax], bl
0x1000ce56  call    InternetCanonicalizeUrlA
0x1000ce5c  test    eax, eax
0x1000ce5e  jz      loc_1000CF58
0x1000ce64  push    0
0x1000ce66  push    0
0x1000ce68  push    0FFFFFFFFh
0x1000ce6a  push    offset aAccept; "Accept: */*"
0x1000ce6f  lea     eax, [esp+864h+var_410]
0x1000ce76  push    eax
0x1000ce77  push    dword_10040FB8
0x1000ce7d  call    InternetOpenUrlA
0x1000ce83  mov     ebx, eax
0x1000ce85  test    ebx, ebx
0x1000ce87  jz      loc_1000CF58
0x1000ce8d  push    0
0x1000ce8f  lea     eax, [esp+858h+var_820]
0x1000ce93  push    eax
0x1000ce94  lea     eax, [esp+85Ch+var_828]
0x1000ce98  push    eax
0x1000ce99  push    20000013h
0x1000ce9e  push    ebx
0x1000ce9f  call    HttpQueryInfoA
0x1000cea5  test    eax, eax
0x1000cea7  jz      loc_1000CF58
0x1000cead  mov     eax, [esp+854h+var_828]
0x1000ceb1  cmp     eax, 0C8h
0x1000ceb6  jz      short loc_1000CEC3
0x1000ceb8  push    eax
0x1000ceb9  call    GetHTTPError
0x1000cebe  jmp     loc_1000CF5D
0x1000cec3  lea     eax, [esp+854h+hObject]
0x1000cec7  push    eax; int
0x1000cec8  push    [esp+858h+pszDest]; lpFileName
0x1000cecc  call    _DOSCreateFile@8; DOSCreateFile(x,x)
0x1000ced1  test    eax, eax
0x1000ced3  jz      short loc_1000CEE7
0x1000ced5  cmp     eax, 0FFFFFFFCh
0x1000ced8  mov     esi, 0FFFFEC54h
0x1000cedd  mov     ecx, 0FFFFF8F1h
0x1000cee2  cmovz   esi, ecx
0x1000cee5  jmp     short loc_1000CF5F
0x1000cee7  push    1000h; Size
0x1000ceec  call    _MemAllocate@4; MemAllocate(x)
0x1000cef1  mov     edi, eax
0x1000cef3  test    edi, edi
0x1000cef5  jnz     short loc_1000CEFE
0x1000cef7  mov     esi, 0FFFFFC0Dh
0x1000cefc  jmp     short loc_1000CF5F
0x1000cefe  lea     eax, [esp+854h+nNumberOfBytesToWrite]
0x1000cf02  mov     [esp+854h+var_830], edi
0x1000cf06  push    eax
0x1000cf07  push    1000h
0x1000cf0c  push    edi
0x1000cf0d  push    ebx
0x1000cf0e  call    InternetReadFile
0x1000cf14  test    eax, eax
0x1000cf16  jz      short loc_1000CF58
0x1000cf18  jmp     short loc_1000CF20
0x1000cf20  mov     eax, [esp+854h+nNumberOfBytesToWrite]
0x1000cf24  test    eax, eax
0x1000cf26  jz      loc_1000CFDC
0x1000cf2c  push    eax; nNumberOfBytesToWrite
0x1000cf2d  push    edi; lpBuffer
0x1000cf2e  push    [esp+85Ch+hObject]; hFile
0x1000cf32  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1000cf37  cmp     eax, 0FFFFh
0x1000cf3c  jz      loc_1000CFF0
0x1000cf42  lea     eax, [esp+854h+nNumberOfBytesToWrite]
0x1000cf46  push    eax
0x1000cf47  push    1000h
0x1000cf4c  push    edi
0x1000cf4d  push    ebx
0x1000cf4e  call    InternetReadFile
0x1000cf54  test    eax, eax
0x1000cf56  jnz     short loc_1000CF20
0x1000cf58  call    GetInternetError
0x1000cf5d  mov     esi, eax
0x1000cf5f  push    [esp+854h+var_824]
0x1000cf63  call    InternetCloseHandle
0x1000cf69  test    ebx, ebx
0x1000cf6b  jz      short loc_1000CF74
0x1000cf6d  push    ebx
0x1000cf6e  call    InternetCloseHandle
0x1000cf74  mov     eax, [esp+854h+hObject]
0x1000cf78  test    eax, eax
0x1000cf7a  jz      short loc_1000CF8B
0x1000cf7c  push    eax; hObject
0x1000cf7d  call    _DOSCloseFile@4; DOSCloseFile(x)
0x1000cf82  push    [esp+854h+pszDest]
0x1000cf86  call    _DOSFileDelete@4; DOSFileDelete(x)
0x1000cf8b  test    ebp, ebp
  ... truncated ...
```
