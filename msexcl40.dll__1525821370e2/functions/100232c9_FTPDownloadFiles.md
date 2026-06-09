# FTPDownloadFiles

- ea: `0x100232c9`
- end: `0x100234f5`
- name: `FTPDownloadFiles`
- size: `556`
- prototype: `int __thiscall(wchar_t *FullPath, int, int, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x100234fb`

## callees

- `0x10006400`
- `0x10018b80`
- `0x100224b6`
- `0x10022e8a`
- `0x100232c9`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10023323`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x10023323`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100233c0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100233fe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023429`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023461`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100233c0`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100233fe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023429`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10023461`

## pseudocode

```c
int __thiscall FTPDownloadFiles(wchar_t *FullPath, _WORD *a2, _WORD *a3, int a4)
{
  int result; // eax
  int v6; // esi
  _DWORD *v7; // edi
  int v8; // esi
  int v9; // eax
  WCHAR *v10; // ecx
  CHAR *v11; // ebx
  __int16 v12; // ax
  int InternetError; // edi
  void *v14; // [esp-Ch] [ebp-84Ch]
  HINTERNET v15; // [esp+1Ch] [ebp-824h] BYREF
  int v16; // [esp+20h] [ebp-820h]
  _DWORD *v17; // [esp+24h] [ebp-81Ch]
  WCHAR v18; // [esp+28h] [ebp-818h] BYREF
  __int16 v19; // [esp+2Ah] [ebp-816h] BYREF
  WCHAR WideCharStr[256]; // [esp+238h] [ebp-608h] BYREF
  wchar_t Filename[256]; // [esp+438h] [ebp-408h] BYREF
  wchar_t Ext[258]; // [esp+638h] [ebp-208h] BYREF

  result = SetupForFTP((int)FullPath, &v15);
  if ( !result )
  {
    v16 = 0;
    __wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
    WCSCPY2(&v18, a2, 0x105u);
    WCSCAT2(&v18, Filename, 0x105u);
    WCSCAT2(&v18, Ext, 0x105u);
    WCSCPY2(a3, &v18, 0x105u);
    WCSCPY2(WideCharStr, Filename, 0x100u);
    WCSCAT2(WideCharStr, Ext, 0x100u);
    v6 = WideCharToMultiByte(0, 0, WideCharStr, wcslen(WideCharStr), 0, 0, 0, 0);
    v7 = (_DWORD *)MemAllocate(v6 + 1);
    v17 = v7;
    WideCharToMultiByte(0, 0, WideCharStr, wcslen(WideCharStr), (LPSTR)v7, v6, 0, 0);
    *((_BYTE *)v7 + v6) = 0;
    v8 = WideCharToMultiByte(0, 0, &v18, wcslen(&v18), 0, 0, 0, 0);
    v9 = MemAllocate(v8 + 1);
    v10 = &v18;
    v11 = (CHAR *)v9;
    do
      v12 = *v10++;
    while ( v12 != (_WORD)v16 );
    WideCharToMultiByte(0, 0, &v18, ((char *)v10 - (char *)&v19) >> 1, v11, v8, 0, 0);
    v14 = v15;
    v11[v8] = 0;
    if ( FtpGetFileA(v14, (LPCSTR)v7, v11, 0, 0, 2u, 0) )
    {
      InternetCloseHandle(v15);
      MemFree(v11);
      MemFree(v7);
      return 0;
    }
    else
    {
      InternetError = GetInternetError();
      MemFree(v11);
      MemFree(v17);
      InternetCloseHandle(v15);
      return InternetError;
    }
  }
  return result;
}

```

## disassembly

```asm
0x100232c9  mov     edi, edi
0x100232cb  push    ebp
0x100232cc  mov     ebp, esp
0x100232ce  and     esp, 0FFFFFFF8h
0x100232d1  sub     esp, 824h
0x100232d7  mov     eax, ___security_cookie
0x100232dc  xor     eax, esp
0x100232de  mov     [esp+824h+var_4], eax
0x100232e5  push    ebx
0x100232e6  mov     ebx, [ebp+arg_4]
0x100232e9  lea     edx, [esp+828h+var_824]
0x100232ed  push    esi
0x100232ee  push    edi
0x100232ef  mov     edi, [ebp+arg_0]
0x100232f2  mov     esi, ecx
0x100232f4  call    SetupForFTP
0x100232f9  test    eax, eax
0x100232fb  jnz     loc_100234DE
0x10023301  mov     ecx, 100h
0x10023306  lea     eax, [esp+830h+Ext]
0x1002330d  push    ecx; ExtCount
0x1002330e  push    eax; Ext
0x1002330f  push    ecx; FilenameCount
0x10023310  lea     eax, [esp+83Ch+Filename]
0x10023317  push    eax; Filename
0x10023318  xor     eax, eax
0x1002331a  push    eax; DirCount
0x1002331b  push    eax; Dir
0x1002331c  push    eax; DriveCount
0x1002331d  push    eax; Drive
0x1002331e  push    esi; FullPath
0x1002331f  mov     [esp+854h+var_820], eax
0x10023323  call    ds:__imp___wsplitpath_s
0x10023329  add     esp, 24h
0x1002332c  lea     ecx, [esp+830h+var_818]
0x10023330  mov     esi, 105h
0x10023335  mov     edx, edi
0x10023337  push    esi
0x10023338  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002333d  push    esi
0x1002333e  lea     edx, [esp+834h+Filename]
0x10023345  lea     ecx, [esp+834h+var_818]
0x10023349  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002334e  push    esi
0x1002334f  lea     edx, [esp+834h+Ext]
0x10023356  lea     ecx, [esp+834h+var_818]
0x1002335a  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x1002335f  push    esi
0x10023360  lea     edx, [esp+834h+var_818]
0x10023364  mov     ecx, ebx
0x10023366  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x1002336b  add     esi, 0FFFFFFFBh
0x1002336e  lea     edx, [esp+830h+Filename]
0x10023375  push    esi
0x10023376  lea     ecx, [esp+834h+WideCharStr]
0x1002337d  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x10023382  push    esi
0x10023383  lea     edx, [esp+834h+Ext]
0x1002338a  lea     ecx, [esp+834h+WideCharStr]
0x10023391  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x10023396  lea     ecx, [esp+830h+WideCharStr]
0x1002339d  xor     ebx, ebx
0x1002339f  lea     edx, [ecx+2]
0x100233a2  mov     ax, [ecx]
0x100233a5  add     ecx, 2
0x100233a8  cmp     ax, bx
0x100233ab  jnz     short loc_100233A2
0x100233ad  push    ebx; lpUsedDefaultChar
0x100233ae  push    ebx; lpDefaultChar
0x100233af  push    ebx; cbMultiByte
0x100233b0  push    ebx; lpMultiByteStr
0x100233b1  sub     ecx, edx
0x100233b3  lea     eax, [esp+840h+WideCharStr]
0x100233ba  sar     ecx, 1
0x100233bc  push    ecx; cchWideChar
0x100233bd  push    eax; lpWideCharStr
0x100233be  push    ebx; dwFlags
0x100233bf  push    ebx; CodePage
0x100233c0  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x100233c6  mov     esi, eax
0x100233c8  lea     ecx, [esi+1]
0x100233cb  call    _MemAllocate@4; MemAllocate(x)
0x100233d0  mov     edi, eax
0x100233d2  lea     ecx, [esp+830h+WideCharStr]
0x100233d9  mov     [esp+830h+var_81C], edi
0x100233dd  lea     edx, [ecx+2]
0x100233e0  mov     ax, [ecx]
0x100233e3  add     ecx, 2
0x100233e6  cmp     ax, bx
0x100233e9  jnz     short loc_100233E0
0x100233eb  push    ebx; lpUsedDefaultChar
0x100233ec  push    ebx; lpDefaultChar
0x100233ed  push    esi; cbMultiByte
0x100233ee  push    edi; lpMultiByteStr
0x100233ef  sub     ecx, edx
0x100233f1  lea     eax, [esp+840h+WideCharStr]
0x100233f8  sar     ecx, 1
0x100233fa  push    ecx; cchWideChar
0x100233fb  push    eax; lpWideCharStr
0x100233fc  push    ebx; dwFlags
0x100233fd  push    ebx; CodePage
0x100233fe  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023404  lea     ecx, [esp+830h+var_818]
0x10023408  mov     [edi+esi], bl
0x1002340b  lea     edx, [ecx+2]
0x1002340e  mov     ax, [ecx]
0x10023411  add     ecx, 2
0x10023414  cmp     ax, bx
0x10023417  jnz     short loc_1002340E
0x10023419  push    ebx; lpUsedDefaultChar
0x1002341a  push    ebx; lpDefaultChar
0x1002341b  push    ebx; cbMultiByte
0x1002341c  push    ebx; lpMultiByteStr
0x1002341d  sub     ecx, edx
0x1002341f  lea     eax, [esp+840h+var_818]
0x10023423  sar     ecx, 1
0x10023425  push    ecx; cchWideChar
0x10023426  push    eax; lpWideCharStr
0x10023427  push    ebx; dwFlags
0x10023428  push    ebx; CodePage
0x10023429  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1002342f  mov     esi, eax
0x10023431  lea     ecx, [esi+1]
0x10023434  call    _MemAllocate@4; MemAllocate(x)
0x10023439  lea     ecx, [esp+830h+var_818]
0x1002343d  mov     ebx, eax
0x1002343f  lea     edx, [ecx+2]
0x10023442  mov     ax, [ecx]
0x10023445  add     ecx, 2
0x10023448  cmp     ax, word ptr [esp+830h+var_820]
0x1002344d  jnz     short loc_10023442
0x1002344f  sub     ecx, edx
0x10023451  lea     eax, [esp+830h+var_818]
0x10023455  xor     edx, edx
0x10023457  sar     ecx, 1
0x10023459  push    edx; lpUsedDefaultChar
0x1002345a  push    edx; lpDefaultChar
0x1002345b  push    esi; cbMultiByte
0x1002345c  push    ebx; lpMultiByteStr
0x1002345d  push    ecx; cchWideChar
0x1002345e  push    eax; lpWideCharStr
0x1002345f  push    edx; dwFlags
0x10023460  push    edx; CodePage
0x10023461  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10023467  xor     eax, eax
0x10023469  push    eax
0x1002346a  push    2
0x1002346c  push    eax
0x1002346d  push    eax
0x1002346e  push    ebx
0x1002346f  push    edi
0x10023470  push    [esp+848h+var_824]
0x10023474  mov     [ebx+esi], al
0x10023477  mov     esi, FtpGetFileA
0x1002347d  mov     ecx, esi
0x1002347f  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10023485  call    esi ; FtpGetFileA
0x10023487  test    eax, eax
0x10023489  jnz     short loc_100234BA
0x1002348b  call    GetInternetError
0x10023490  mov     ecx, ebx
0x10023492  mov     edi, eax
0x10023494  call    _MemFree@4; MemFree(x)
0x10023499  mov     ecx, [esp+830h+var_81C]
0x1002349d  call    _MemFree@4; MemFree(x)
0x100234a2  push    [esp+830h+var_824]
0x100234a6  mov     esi, InternetCloseHandle
0x100234ac  mov     ecx, esi
0x100234ae  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100234b4  call    esi ; InternetCloseHandle
0x100234b6  mov     eax, edi
0x100234b8  jmp     short loc_100234DE
0x100234ba  push    [esp+830h+var_824]
0x100234be  mov     esi, InternetCloseHandle
0x100234c4  mov     ecx, esi
0x100234c6  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x100234cc  call    esi ; InternetCloseHandle
0x100234ce  mov     ecx, ebx
0x100234d0  call    _MemFree@4; MemFree(x)
0x100234d5  mov     ecx, edi
0x100234d7  call    _MemFree@4; MemFree(x)
0x100234dc  xor     eax, eax
0x100234de  mov     ecx, [esp+830h+var_4]
0x100234e5  pop     edi
0x100234e6  pop     esi
0x100234e7  pop     ebx
0x100234e8  xor     ecx, esp; StackCookie
0x100234ea  call    @__security_check_cookie@4; __security_check_cookie(x)
0x100234ef  mov     esp, ebp
0x100234f1  pop     ebp
0x100234f2  retn    0Ch
```
