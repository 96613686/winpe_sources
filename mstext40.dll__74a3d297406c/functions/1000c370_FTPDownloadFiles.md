# FTPDownloadFiles

- ea: `0x1000c370`
- end: `0x1000c961`
- name: `FTPDownloadFiles`
- size: `1521`
- prototype: `int __stdcall(wchar_t *FullPath, int, int, STRSAFE_LPWSTR, size_t cchDest)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1000d720`

## callees

- `0x1000ad60`
- `0x1000ae20`
- `0x1000b070`
- `0x1000b200`
- `0x1000c2f0`
- `0x1000c370`
- `0x1000ca60`
- `0x1000d020`
- `0x1000e950`
- `0x1002b81a`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000c715`
- `KERNEL32!GetLastError` at `0x1000c937`
- `KERNEL32!GetLastError` at `0x1000c715`
- `KERNEL32!GetLastError` at `0x1000c937`
- `KERNEL32!WideCharToMultiByte` at `0x1000c50b`
- `KERNEL32!WideCharToMultiByte` at `0x1000c546`
- `KERNEL32!WideCharToMultiByte` at `0x1000c57a`
- `KERNEL32!WideCharToMultiByte` at `0x1000c5ba`
- `KERNEL32!WideCharToMultiByte` at `0x1000c6a1`
- `KERNEL32!WideCharToMultiByte` at `0x1000c6f2`
- `KERNEL32!WideCharToMultiByte` at `0x1000c830`
- `KERNEL32!WideCharToMultiByte` at `0x1000c873`
- `KERNEL32!WideCharToMultiByte` at `0x1000c4ec`
- `KERNEL32!WideCharToMultiByte` at `0x1000c5b1`
- `KERNEL32!WideCharToMultiByte` at `0x1000c682`
- `KERNEL32!WideCharToMultiByte` at `0x1000c827`
- `KERNEL32!WideCharToMultiByte` at `0x1000c873`
- `KERNEL32!MultiByteToWideChar` at `0x1000c795`
- `KERNEL32!MultiByteToWideChar` at `0x1000c795`

## pseudocode

```c
int __stdcall FTPDownloadFiles(wchar_t *FullPath, void *a2, int a3, STRSAFE_LPWSTR a4, size_t cchDest)
{
  int result; // eax
  CHAR *v6; // ecx
  int v7; // edx
  __int16 v8; // ax
  wchar_t *p_WideCharStr; // ecx
  int v10; // edx
  int v11; // esi
  wchar_t v12; // ax
  int v13; // edi
  CHAR *v14; // ebx
  int v15; // ebp
  CHAR *v16; // edi
  void *v17; // ebp
  int InternetError; // esi
  int v19; // edx
  wchar_t *v20; // ecx
  wchar_t v21; // ax
  int v22; // edi
  CHAR *v23; // esi
  void *FirstFileA; // ebx
  WCHAR *v25; // edi
  int v26; // kr1C_4
  int v27; // edx
  wchar_t *v28; // ecx
  wchar_t v29; // ax
  int v30; // ebx
  CHAR *v31; // esi
  void *v32; // [esp+48h] [ebp-96Ch]
  HINTERNET v33; // [esp+58h] [ebp-95Ch] BYREF
  HINTERNET v34; // [esp+5Ch] [ebp-958h]
  HINTERNET v35; // [esp+60h] [ebp-954h]
  int v36; // [esp+64h] [ebp-950h]
  struct _WIN32_FIND_DATAA v37; // [esp+68h] [ebp-94Ch] BYREF
  wchar_t v38[260]; // [esp+1A8h] [ebp-80Ch] BYREF
  wchar_t WideCharStr; // [esp+3B0h] [ebp-604h] BYREF
  wchar_t v40[254]; // [esp+3B4h] [ebp-600h] BYREF
  wchar_t pszSrc[256]; // [esp+5B0h] [ebp-404h] BYREF
  wchar_t Ext[256]; // [esp+7B0h] [ebp-204h] BYREF

  v35 = a2;
  result = SetupForFTP(FullPath, &v33);
  if ( !result )
  {
    SplitPath(FullPath, 0, 0, 0, 0, pszSrc, 0x100u, Ext, 0x100u);
    v6 = &v37.cAlternateFileName[12];
    v7 = 261;
    while ( v7 != -2147483385 )
    {
      v8 = *(_WORD *)&v6[a3 - (_DWORD)&v37.cAlternateFileName[12]];
      if ( !v8 )
        break;
      *(_WORD *)v6 = v8;
      v6 += 2;
      if ( !--v7 )
      {
        v6 -= 2;
        break;
      }
    }
    *(_WORD *)v6 = 0;
    StringCchCatW((STRSAFE_LPWSTR)&v37.cAlternateFileName[12], 0x105u, pszSrc);
    StringCchCatW((STRSAFE_LPWSTR)&v37.cAlternateFileName[12], 0x105u, Ext);
    StringCchCopyW(a4, cchDest, (STRSAFE_LPCWSTR)&v37.cAlternateFileName[12]);
    p_WideCharStr = &WideCharStr;
    v10 = 256;
    v11 = (char *)pszSrc - (char *)&WideCharStr;
    while ( v10 != -2147483390 )
    {
      v12 = *(wchar_t *)((char *)p_WideCharStr + v11);
      if ( !v12 )
        break;
      *p_WideCharStr++ = v12;
      if ( !--v10 )
      {
        --p_WideCharStr;
        break;
      }
    }
    *p_WideCharStr = 0;
    StringCchCatW(&WideCharStr, 0x100u, Ext);
    v13 = WideCharToMultiByte(0, 0, &WideCharStr, wcslen(&WideCharStr), 0, 0, 0, 0);
    v14 = (CHAR *)MemAllocate(v13 + 1);
    WideCharToMultiByte(0, 0, &WideCharStr, wcslen(&WideCharStr), v14, v13, 0, 0);
    v14[v13] = 0;
    v15 = WideCharToMultiByte(
            0,
            0,
            (LPCWCH)&v37.cAlternateFileName[12],
            wcslen((const unsigned __int16 *)&v37.cAlternateFileName[12]),
            0,
            0,
            0,
            0);
    v16 = (CHAR *)MemAllocate(v15 + 1);
    WideCharToMultiByte(
      0,
      0,
      (LPCWCH)&v37.cAlternateFileName[12],
      wcslen((const unsigned __int16 *)&v37.cAlternateFileName[12]),
      v16,
      v15,
      0,
      0);
    v16[v15] = 0;
    v17 = v33;
    if ( FtpGetFileA(v33, v14, v16, 0, 0, 2u, 0) )
    {
      if ( !v36 )
      {
        InternetCloseHandle(v17);
        MemFree(v16);
        MemFree(v14);
        return 0;
      }
      v19 = 256;
      v20 = v40;
      while ( v19 != -2147483390 )
      {
        v21 = *(wchar_t *)((char *)v20 + v11);
        if ( !v21 )
          break;
        *v20++ = v21;
        if ( !--v19 )
        {
          --v20;
          break;
        }
      }
      *v20 = 0;
      StringCchCatW(v40, 0x100u, L".*");
      MemFree(v14);
      MemFree(v16);
      v22 = WideCharToMultiByte(0, 0, v40, wcslen(v40), 0, 0, 0, 0);
      v23 = (CHAR *)MemAllocate(v22 + 1);
      if ( v23 )
      {
        WideCharToMultiByte(0, 0, v40, wcslen(v40), v23, v22, 0, 0);
        FirstFileA = FtpFindFirstFileA(v17, v23, &v37, 0, 0);
        v35 = FirstFileA;
        MemFree(v23);
        if ( FirstFileA )
        {
          v25 = (WCHAR *)MemAllocate(2 * strlen(v37.cFileName) + 2);
          if ( !v25 )
          {
LABEL_39:
            v32 = FirstFileA;
LABEL_40:
            InternetError = -1011;
            InternetCloseHandle(v32);
            goto LABEL_41;
          }
          while ( 1 )
          {
            v26 = strlen(v37.cFileName);
            MultiByteToWideChar(0, 0, v37.cFileName, v26, v25, v26);
            if ( IsFamilyFile(v25, v36) )
            {
              v27 = 261;
              v28 = v38;
              while ( v27 != -2147483385 )
              {
                v29 = *(STRSAFE_LPWSTR)((char *)a4 + (_DWORD)v28);
                if ( !v29 )
                  break;
                *v28++ = v29;
                if ( !--v27 )
                {
                  --v28;
                  break;
                }
              }
              *v28 = 0;
              StringCchCatW(v38, 0x105u, v25);
              v30 = WideCharToMultiByte(0, 0, v38, wcslen(v38), 0, 0, 0, 0);
              v31 = (CHAR *)MemAllocate(v30 + 1);
              if ( !v31 )
              {
                MemFree(v25);
                v32 = v35;
                goto LABEL_40;
              }
              WideCharToMultiByte(0, 0, v38, wcslen(v38), v31, v30, 0, 0);
              v31[v30] = 0;
              if ( !FtpGetFileA(v34, v37.cFileName, v31, 0, 0, 2u, 0) )
              {
                MemFree(v31);
                MemFree(v25);
                InternetError = GetInternetError();
                InternetCloseHandle(v35);
                goto LABEL_41;
              }
              MemFree(v31);
              FirstFileA = v35;
            }
            MemFree(v25);
            if ( !InternetFindNextFileA(FirstFileA, &v37) )
              break;
            v25 = (WCHAR *)MemAllocate(2 * strlen(v37.cFileName) + 2);
            if ( !v25 )
              goto LABEL_39;
          }
          if ( GetLastError() != 18 )
          {
            InternetError = GetInternetError();
            goto LABEL_41;
          }
          InternetCloseHandle(FirstFileA);
          v17 = v34;
        }
        else if ( GetLastError() != 18 )
        {
          InternetError = GetInternetError();
          if ( InternetError != -1305 )
            goto LABEL_41;
        }
        InternetCloseHandle(v17);
        return 0;
      }
      InternetError = -1011;
    }
    else
    {
      InternetError = GetInternetError();
      MemFree(v16);
      MemFree(v14);
    }
LABEL_41:
    InternetCloseHandle(v34);
    return InternetError;
  }
  return result;
}

```

## disassembly

```asm
0x1000c370  sub     esp, 95Ch
0x1000c376  mov     eax, ___security_cookie
0x1000c37b  xor     eax, esp
0x1000c37d  mov     [esp+95Ch+var_4], eax
0x1000c384  mov     eax, [esp+95Ch+arg_4]
0x1000c38b  push    esi
0x1000c38c  mov     esi, [esp+960h+FullPath]
0x1000c393  push    edi
0x1000c394  mov     edi, [esp+964h+arg_C]
0x1000c39b  mov     [esp+964h+var_954], eax
0x1000c39f  lea     eax, [esp+964h+var_95C]
0x1000c3a3  push    eax
0x1000c3a4  push    esi
0x1000c3a5  call    SetupForFTP
0x1000c3aa  test    eax, eax
0x1000c3ac  jnz     loc_1000C8FA
0x1000c3b2  push    ebx
0x1000c3b3  push    100h; ExtCount
0x1000c3b8  lea     eax, [esp+96Ch+Ext]
0x1000c3bf  push    eax; Ext
0x1000c3c0  push    100h; FilenameCount
0x1000c3c5  lea     eax, [esp+974h+pszSrc]
0x1000c3cc  push    eax; Filename
0x1000c3cd  push    0; DirCount
0x1000c3cf  push    0; Dir
0x1000c3d1  push    0; DriveCount
0x1000c3d3  push    0; Drive
0x1000c3d5  push    esi; FullPath
0x1000c3d6  call    _SplitPath@36; SplitPath(x,x,x,x,x,x,x,x,x)
0x1000c3db  mov     ebx, [esp+968h+arg_8]
0x1000c3e2  lea     ecx, [esp+968h+pszDest]
0x1000c3e9  mov     eax, ecx
0x1000c3eb  mov     edx, 105h
0x1000c3f0  sub     ebx, eax
0x1000c3f2  mov     [esp+968h+arg_8], ebx
0x1000c3f9  lea     esp, [esp+0]
0x1000c400  lea     eax, [edx+7FFFFEF9h]
0x1000c406  test    eax, eax
0x1000c408  jz      short loc_1000C41E
0x1000c40a  movzx   eax, word ptr [ebx+ecx]
0x1000c40e  test    ax, ax
0x1000c411  jz      short loc_1000C41E
0x1000c413  mov     [ecx], ax
0x1000c416  add     ecx, 2
0x1000c419  dec     edx
0x1000c41a  jnz     short loc_1000C400
0x1000c41c  jmp     short loc_1000C422
0x1000c41e  test    edx, edx
0x1000c420  jnz     short loc_1000C425
0x1000c422  sub     ecx, 2
0x1000c425  xor     eax, eax
0x1000c427  mov     [ecx], ax
0x1000c42a  lea     eax, [esp+968h+pszSrc]
0x1000c431  push    eax; pszSrc
0x1000c432  push    105h; cchDest
0x1000c437  lea     eax, [esp+970h+pszDest]
0x1000c43e  push    eax; pszDest
0x1000c43f  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000c444  lea     eax, [esp+968h+Ext]
0x1000c44b  push    eax; pszSrc
0x1000c44c  push    105h; cchDest
0x1000c451  lea     eax, [esp+970h+pszDest]
0x1000c458  push    eax; pszDest
0x1000c459  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000c45e  lea     eax, [esp+968h+pszDest]
0x1000c465  push    eax; pszSrc
0x1000c466  push    [esp+96Ch+cchDest]; cchDest
0x1000c46d  push    edi; pszDest
0x1000c46e  call    _StringCchCopyW@12; StringCchCopyW(x,x,x)
0x1000c473  lea     ecx, [esp+968h+WideCharStr]
0x1000c47a  mov     edx, 100h
0x1000c47f  lea     esi, [esp+968h+pszSrc]
0x1000c486  mov     eax, ecx
0x1000c488  sub     esi, eax
0x1000c48a  lea     ebx, [ebx+0]
0x1000c490  lea     eax, [edx+7FFFFEFEh]
0x1000c496  test    eax, eax
0x1000c498  jz      short loc_1000C4AE
0x1000c49a  movzx   eax, word ptr [esi+ecx]
0x1000c49e  test    ax, ax
0x1000c4a1  jz      short loc_1000C4AE
0x1000c4a3  mov     [ecx], ax
0x1000c4a6  add     ecx, 2
0x1000c4a9  dec     edx
0x1000c4aa  jnz     short loc_1000C490
0x1000c4ac  jmp     short loc_1000C4B2
0x1000c4ae  test    edx, edx
0x1000c4b0  jnz     short loc_1000C4B5
0x1000c4b2  sub     ecx, 2
0x1000c4b5  xor     eax, eax
0x1000c4b7  mov     [ecx], ax
0x1000c4ba  lea     eax, [esp+968h+Ext]
0x1000c4c1  push    eax; pszSrc
0x1000c4c2  push    100h; cchDest
0x1000c4c7  lea     eax, [esp+970h+WideCharStr]
0x1000c4ce  push    eax; pszDest
0x1000c4cf  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000c4d4  lea     ecx, [esp+968h+WideCharStr]
0x1000c4db  lea     edx, [ecx+2]
0x1000c4de  mov     edi, edi
0x1000c4e0  mov     ax, [ecx]
0x1000c4e3  add     ecx, 2
0x1000c4e6  test    ax, ax
0x1000c4e9  jnz     short loc_1000C4E0
0x1000c4eb  push    ebp
0x1000c4ec  mov     ebp, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c4f2  lea     eax, [esp+96Ch+WideCharStr]
0x1000c4f9  push    0; lpUsedDefaultChar
0x1000c4fb  push    0; lpDefaultChar
0x1000c4fd  push    0; cbMultiByte
0x1000c4ff  push    0; lpMultiByteStr
0x1000c501  sub     ecx, edx
0x1000c503  sar     ecx, 1
0x1000c505  push    ecx; cchWideChar
0x1000c506  push    eax; lpWideCharStr
0x1000c507  push    0; dwFlags
0x1000c509  push    0; CodePage
0x1000c50b  call    ebp ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c50d  mov     edi, eax
0x1000c50f  lea     ecx, [edi+1]
0x1000c512  push    ecx; Size
0x1000c513  call    _MemAllocate@4; MemAllocate(x)
0x1000c518  lea     ecx, [esp+96Ch+WideCharStr]
0x1000c51f  mov     ebx, eax
0x1000c521  lea     edx, [ecx+2]
0x1000c524  mov     ax, [ecx]
0x1000c527  add     ecx, 2
0x1000c52a  test    ax, ax
0x1000c52d  jnz     short loc_1000C524
0x1000c52f  push    0; lpUsedDefaultChar
0x1000c531  push    0; lpDefaultChar
0x1000c533  push    edi; cbMultiByte
0x1000c534  push    ebx; lpMultiByteStr
0x1000c535  sub     ecx, edx
0x1000c537  lea     eax, [esp+97Ch+WideCharStr]
0x1000c53e  sar     ecx, 1
0x1000c540  push    ecx; cchWideChar
0x1000c541  push    eax; lpWideCharStr
0x1000c542  push    0; dwFlags
0x1000c544  push    0; CodePage
0x1000c546  call    ebp ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c548  lea     ecx, [esp+96Ch+pszDest]
0x1000c54f  mov     byte ptr [ebx+edi], 0
0x1000c553  lea     edx, [ecx+2]
0x1000c556  mov     ax, [ecx]
0x1000c559  add     ecx, 2
0x1000c55c  test    ax, ax
0x1000c55f  jnz     short loc_1000C556
0x1000c561  push    0; lpUsedDefaultChar
0x1000c563  push    0; lpDefaultChar
0x1000c565  push    0; cbMultiByte
0x1000c567  push    0; lpMultiByteStr
0x1000c569  sub     ecx, edx
0x1000c56b  lea     eax, [esp+97Ch+pszDest]
0x1000c572  sar     ecx, 1
0x1000c574  push    ecx; cchWideChar
0x1000c575  push    eax; lpWideCharStr
0x1000c576  push    0; dwFlags
0x1000c578  push    0; CodePage
0x1000c57a  call    ebp ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c57c  mov     ebp, eax
0x1000c57e  lea     ecx, [ebp+1]
0x1000c581  push    ecx; Size
0x1000c582  call    _MemAllocate@4; MemAllocate(x)
0x1000c587  lea     ecx, [esp+96Ch+pszDest]
0x1000c58e  mov     edi, eax
0x1000c590  lea     edx, [ecx+2]
0x1000c593  mov     ax, [ecx]
0x1000c596  add     ecx, 2
0x1000c599  test    ax, ax
0x1000c59c  jnz     short loc_1000C593
0x1000c59e  push    0; lpUsedDefaultChar
0x1000c5a0  push    0; lpDefaultChar
0x1000c5a2  push    ebp; cbMultiByte
0x1000c5a3  push    edi; lpMultiByteStr
0x1000c5a4  sub     ecx, edx
0x1000c5a6  lea     eax, [esp+97Ch+pszDest]
0x1000c5ad  sar     ecx, 1
0x1000c5af  push    ecx; cchWideChar
0x1000c5b0  push    eax; lpWideCharStr
0x1000c5b1  mov     eax, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c5b6  push    0; dwFlags
0x1000c5b8  push    0; CodePage
0x1000c5ba  call    eax ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c5bc  push    0
0x1000c5be  push    2
0x1000c5c0  push    0
0x1000c5c2  push    0
0x1000c5c4  push    edi
0x1000c5c5  mov     byte ptr [edi+ebp], 0
0x1000c5c9  mov     ebp, [esp+980h+var_95C]
0x1000c5cd  push    ebx
0x1000c5ce  push    ebp
0x1000c5cf  call    FtpGetFileA
0x1000c5d5  test    eax, eax
0x1000c5d7  jnz     short loc_1000C5F1
0x1000c5d9  call    GetInternetError
0x1000c5de  push    edi
0x1000c5df  mov     esi, eax
0x1000c5e1  call    _MemFree@4; MemFree(x)
0x1000c5e6  push    ebx
0x1000c5e7  call    _MemFree@4; MemFree(x)
0x1000c5ec  jmp     loc_1000C8EC
0x1000c5f1  cmp     [esp+968h+var_950], 0
0x1000c5f6  jnz     short loc_1000C612
0x1000c5f8  push    ebp
0x1000c5f9  call    InternetCloseHandle
0x1000c5ff  push    edi
0x1000c600  call    _MemFree@4; MemFree(x)
0x1000c605  push    ebx
0x1000c606  call    _MemFree@4; MemFree(x)
0x1000c60b  xor     eax, eax
0x1000c60d  jmp     loc_1000C8F8
0x1000c612  mov     edx, 100h
0x1000c617  lea     ecx, [esp+968h+var_600]
0x1000c61e  mov     edi, edi
0x1000c620  lea     eax, [edx+7FFFFEFEh]
0x1000c626  test    eax, eax
0x1000c628  jz      short loc_1000C63E
0x1000c62a  movzx   eax, word ptr [esi+ecx]
0x1000c62e  test    ax, ax
0x1000c631  jz      short loc_1000C63E
0x1000c633  mov     [ecx], ax
0x1000c636  add     ecx, 2
0x1000c639  dec     edx
0x1000c63a  jnz     short loc_1000C620
0x1000c63c  jmp     short loc_1000C642
0x1000c63e  test    edx, edx
0x1000c640  jnz     short loc_1000C645
0x1000c642  sub     ecx, 2
0x1000c645  xor     eax, eax
0x1000c647  push    offset asc_100013E8; ".*"
0x1000c64c  mov     [ecx], ax
0x1000c64f  lea     eax, [esp+96Ch+var_600]
0x1000c656  push    100h; cchDest
0x1000c65b  push    eax; pszDest
0x1000c65c  call    _StringCchCatW@12; StringCchCatW(x,x,x)
0x1000c661  push    ebx
0x1000c662  call    _MemFree@4; MemFree(x)
0x1000c667  push    edi
0x1000c668  call    _MemFree@4; MemFree(x)
0x1000c66d  lea     ecx, [esp+968h+var_600]
0x1000c674  lea     edx, [ecx+2]
0x1000c677  mov     ax, [ecx]
0x1000c67a  add     ecx, 2
0x1000c67d  test    ax, ax
0x1000c680  jnz     short loc_1000C677
0x1000c682  mov     ebx, ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c688  lea     eax, [esp+968h+var_600]
0x1000c68f  push    0; lpUsedDefaultChar
0x1000c691  push    0; lpDefaultChar
0x1000c693  push    0; cbMultiByte
0x1000c695  push    0; lpMultiByteStr
0x1000c697  sub     ecx, edx
0x1000c699  sar     ecx, 1
0x1000c69b  push    ecx; cchWideChar
0x1000c69c  push    eax; lpWideCharStr
0x1000c69d  push    0; dwFlags
0x1000c69f  push    0; CodePage
0x1000c6a1  call    ebx ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c6a3  mov     edi, eax
0x1000c6a5  lea     ecx, [edi+1]
0x1000c6a8  push    ecx; Size
0x1000c6a9  call    _MemAllocate@4; MemAllocate(x)
0x1000c6ae  mov     esi, eax
0x1000c6b0  test    esi, esi
0x1000c6b2  jnz     short loc_1000C6BE
0x1000c6b4  mov     esi, 0FFFFFC0Dh
0x1000c6b9  jmp     loc_1000C8EC
0x1000c6be  lea     ecx, [esp+968h+var_600]
0x1000c6c5  lea     edx, [ecx+2]
0x1000c6c8  jmp     short loc_1000C6D0
0x1000c6d0  mov     ax, [ecx]
0x1000c6d3  add     ecx, 2
0x1000c6d6  test    ax, ax
0x1000c6d9  jnz     short loc_1000C6D0
0x1000c6db  push    0; lpUsedDefaultChar
0x1000c6dd  push    0; lpDefaultChar
0x1000c6df  push    edi; cbMultiByte
0x1000c6e0  push    esi; lpMultiByteStr
0x1000c6e1  sub     ecx, edx
0x1000c6e3  lea     eax, [esp+978h+var_600]
0x1000c6ea  sar     ecx, 1
0x1000c6ec  push    ecx; cchWideChar
0x1000c6ed  push    eax; lpWideCharStr
0x1000c6ee  push    0; dwFlags
0x1000c6f0  push    0; CodePage
0x1000c6f2  call    ebx ; WideCharToMultiByte(x,x,x,x,x,x,x,x); WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1000c6f4  push    0
0x1000c6f6  push    0
0x1000c6f8  lea     eax, [esp+970h+var_94C]
0x1000c6fc  push    eax
0x1000c6fd  push    esi
0x1000c6fe  push    ebp
0x1000c6ff  call    FtpFindFirstFileA
0x1000c705  mov     ebx, eax
0x1000c707  push    esi
0x1000c708  mov     [esp+96Ch+var_954], ebx
0x1000c70c  call    _MemFree@4; MemFree(x)
0x1000c711  test    ebx, ebx
  ... truncated ...
```
