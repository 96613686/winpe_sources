# NetUploadToNet(x,x,x)

- ea: `0x10024042`
- end: `0x1002427c`
- name: `_NetUploadToNet@12`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, installer_update`

## callers

- `0x100278d3`

## callees

- `0x10006400`
- `0x10018b80`
- `0x100224b6`
- `0x10022628`
- `0x10022e8a`
- `0x10024042`
- `0x1002580a`
- `0x10025ab7`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100240be`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x100240be`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10024119`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10024165`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002418f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100241e2`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10024119`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10024165`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1002418f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x100241e2`

## pseudocode

```c
int __thiscall NetUploadToNet(wchar_t *this, int a2)
{
  int result; // eax
  wchar_t *v3; // esi
  int v4; // edi
  CHAR *v5; // ebx
  int InternetError; // edi
  CHAR *v7; // edi
  BOOL (__stdcall *v8)(HINTERNET, LPCSTR, LPCSTR, DWORD, DWORD_PTR); // esi
  HINTERNET v9; // [esp-14h] [ebp-850h]
  CHAR *v10; // [esp+10h] [ebp-82Ch]
  HINTERNET v11; // [esp+18h] [ebp-824h] BYREF
  wchar_t *FullPath; // [esp+1Ch] [ebp-820h]
  wchar_t Dir[256]; // [esp+20h] [ebp-81Ch] BYREF
  wchar_t Ext[256]; // [esp+220h] [ebp-61Ch] BYREF
  wchar_t Filename[256]; // [esp+420h] [ebp-41Ch] BYREF
  WCHAR WideCharStr[256]; // [esp+620h] [ebp-21Ch] BYREF
  wchar_t Drive[10]; // [esp+820h] [ebp-1Ch] BYREF

  FullPath = this;
  if ( !dword_1003AE18 && !NetInitializeInternetServices() )
    return -20163;
  result = SetupForFTP(a2, &v11);
  if ( !result )
  {
    v3 = FullPath;
    __wsplitpath_s(FullPath, Drive, 9u, Dir, 0x100u, Filename, 0x100u, Ext, 0x100u);
    WCSCPY2(WideCharStr, Filename, 0x100u);
    WCSCAT2(WideCharStr, Ext, 0x100u);
    v4 = WideCharToMultiByte(0, 0, WideCharStr, wcslen(WideCharStr), 0, 0, 0, 0);
    v5 = (CHAR *)MemAllocate(v4 + 1);
    if ( !v5 )
    {
LABEL_6:
      InternetError = -1011;
LABEL_11:
      InternetCloseHandle(v11);
      return InternetError;
    }
    WideCharToMultiByte(0, 0, WideCharStr, wcslen(WideCharStr), v5, v4, 0, 0);
    v5[v4] = 0;
    FullPath = (wchar_t *)WideCharToMultiByte(0, 0, v3, wcslen(v3), 0, 0, 0, 0);
    v7 = (CHAR *)MemAllocate((signed int)FullPath + 1);
    v10 = v7;
    if ( !v7 )
    {
      MemFree(v5);
      goto LABEL_6;
    }
    WideCharToMultiByte(0, 0, v3, wcslen(v3), v7, (int)FullPath, 0, 0);
    v8 = FtpPutFileA;
    v9 = v11;
    *((_BYTE *)FullPath + (_DWORD)v7) = 0;
    if ( !((int (__thiscall *)(BOOL (__stdcall *)(HINTERNET, LPCSTR, LPCSTR, DWORD, DWORD_PTR), HINTERNET, CHAR *, CHAR *, int, _DWORD))v8)(
            v8,
            v9,
            v7,
            v5,
            2,
            0) )
    {
      InternetError = GetInternetError();
      MemFree(v10);
      MemFree(v5);
      goto LABEL_11;
    }
    MemFree(v7);
    MemFree(v5);
    InternetCloseHandle(v11);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x10024042  mov     edi, edi
0x10024044  push    ebp
0x10024045  mov     ebp, esp
0x10024047  sub     esp, 830h
0x1002404d  mov     eax, ___security_cookie
0x10024052  xor     eax, ebp
0x10024054  mov     [ebp+var_8], eax
0x10024057  cmp     dword_1003AE18, 0
0x1002405e  push    ebx
0x1002405f  push    esi
0x10024060  mov     esi, [ebp+arg_0]
0x10024063  push    edi
0x10024064  mov     [ebp+FullPath], ecx
0x1002406a  jnz     short loc_1002407F
0x1002406c  call    _NetInitializeInternetServices@0; NetInitializeInternetServices()
0x10024071  test    eax, eax
0x10024073  jnz     short loc_1002407F
0x10024075  mov     eax, 0FFFFB13Dh
0x1002407a  jmp     loc_1002426B
0x1002407f  lea     edx, [ebp+var_824]
0x10024085  mov     ecx, esi
0x10024087  call    SetupForFTP
0x1002408c  test    eax, eax
0x1002408e  jnz     loc_1002426B
0x10024094  mov     esi, [ebp+FullPath]
0x1002409a  lea     eax, [ebp+Ext]
0x100240a0  mov     edi, 100h
0x100240a5  push    edi; ExtCount
0x100240a6  push    eax; Ext
0x100240a7  push    edi; FilenameCount
0x100240a8  lea     eax, [ebp+Filename]
0x100240ae  push    eax; Filename
0x100240af  push    edi; DirCount
0x100240b0  lea     eax, [ebp+Dir]
0x100240b6  push    eax; Dir
0x100240b7  push    9; DriveCount
0x100240b9  lea     eax, [ebp+Drive]
0x100240bc  push    eax; Drive
0x100240bd  push    esi; FullPath
0x100240be  call    ds:__imp___wsplitpath_s
0x100240c4  add     esp, 24h
0x100240c7  lea     edx, [ebp+Filename]
0x100240cd  lea     ecx, [ebp+WideCharStr]
0x100240d3  push    edi
0x100240d4  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100240d9  push    edi
0x100240da  lea     edx, [ebp+Ext]
0x100240e0  lea     ecx, [ebp+WideCharStr]
0x100240e6  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100240eb  lea     ecx, [ebp+WideCharStr]
0x100240f1  xor     ebx, ebx
0x100240f3  lea     edx, [ecx+2]
0x100240f6  mov     [ebp+var_828], ebx
0x100240fc  mov     ax, [ecx]
0x100240ff  add     ecx, 2
0x10024102  cmp     ax, bx
0x10024105  jnz     short loc_100240FC
0x10024107  push    ebx; lpUsedDefaultChar
0x10024108  push    ebx; lpDefaultChar
0x10024109  push    ebx; cbMultiByte
0x1002410a  push    ebx; lpMultiByteStr
0x1002410b  sub     ecx, edx
0x1002410d  lea     eax, [ebp+WideCharStr]
0x10024113  sar     ecx, 1
0x10024115  push    ecx; cchWideChar
0x10024116  push    eax; lpWideCharStr
0x10024117  push    ebx; dwFlags
0x10024118  push    ebx; CodePage
0x10024119  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1002411f  mov     edi, eax
0x10024121  lea     ecx, [edi+1]
0x10024124  call    _MemAllocate@4; MemAllocate(x)
0x10024129  mov     ebx, eax
0x1002412b  test    ebx, ebx
0x1002412d  jnz     short loc_10024139
0x1002412f  mov     edi, 0FFFFFC0Dh
0x10024134  jmp     loc_1002422B
0x10024139  lea     ecx, [ebp+WideCharStr]
0x1002413f  lea     edx, [ecx+2]
0x10024142  mov     ax, [ecx]
0x10024145  add     ecx, 2
0x10024148  cmp     ax, word ptr [ebp+var_828]
0x1002414f  jnz     short loc_10024142
0x10024151  sub     ecx, edx
0x10024153  lea     eax, [ebp+WideCharStr]
0x10024159  xor     edx, edx
0x1002415b  sar     ecx, 1
0x1002415d  push    edx; lpUsedDefaultChar
0x1002415e  push    edx; lpDefaultChar
0x1002415f  push    edi; cbMultiByte
0x10024160  push    ebx; lpMultiByteStr
0x10024161  push    ecx; cchWideChar
0x10024162  push    eax; lpWideCharStr
0x10024163  push    edx; dwFlags
0x10024164  push    edx; CodePage
0x10024165  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x1002416b  mov     ecx, esi
0x1002416d  mov     byte ptr [ebx+edi], 0
0x10024171  xor     edi, edi
0x10024173  lea     edx, [ecx+2]
0x10024176  mov     ax, [ecx]
0x10024179  add     ecx, 2
0x1002417c  cmp     ax, di
0x1002417f  jnz     short loc_10024176
0x10024181  xor     eax, eax
0x10024183  sub     ecx, edx
0x10024185  push    eax; lpUsedDefaultChar
0x10024186  push    eax; lpDefaultChar
0x10024187  push    eax; cbMultiByte
0x10024188  push    eax; lpMultiByteStr
0x10024189  sar     ecx, 1
0x1002418b  push    ecx; cchWideChar
0x1002418c  push    esi; lpWideCharStr
0x1002418d  push    eax; dwFlags
0x1002418e  push    eax; CodePage
0x1002418f  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10024195  mov     [ebp+FullPath], eax
0x1002419b  lea     ecx, [eax+1]
0x1002419e  call    _MemAllocate@4; MemAllocate(x)
0x100241a3  mov     edi, eax
0x100241a5  mov     [ebp+var_82C], edi
0x100241ab  test    edi, edi
0x100241ad  jnz     short loc_100241BB
0x100241af  mov     ecx, ebx
0x100241b1  call    _MemFree@4; MemFree(x)
0x100241b6  jmp     loc_1002412F
0x100241bb  mov     ecx, esi
0x100241bd  lea     edx, [ecx+2]
0x100241c0  mov     ax, [ecx]
0x100241c3  add     ecx, 2
0x100241c6  cmp     ax, word ptr [ebp+var_828]
0x100241cd  jnz     short loc_100241C0
0x100241cf  xor     eax, eax
0x100241d1  sub     ecx, edx
0x100241d3  push    eax; lpUsedDefaultChar
0x100241d4  push    eax; lpDefaultChar
0x100241d5  push    [ebp+FullPath]; cbMultiByte
0x100241db  sar     ecx, 1
0x100241dd  push    edi; lpMultiByteStr
0x100241de  push    ecx; cchWideChar
0x100241df  push    esi; lpWideCharStr
0x100241e0  push    eax; dwFlags
0x100241e1  push    eax; CodePage
0x100241e2  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x100241e8  mov     eax, [ebp+FullPath]
0x100241ee  xor     ecx, ecx
0x100241f0  mov     esi, FtpPutFileA
0x100241f6  push    ecx
0x100241f7  push    2
0x100241f9  push    ebx
0x100241fa  push    edi
0x100241fb  push    [ebp+var_824]
0x10024201  mov     [edi+eax], cl
0x10024204  mov     ecx, esi
0x10024206  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002420c  call    esi ; FtpPutFileA
0x1002420e  test    eax, eax
0x10024210  jnz     short loc_10024245
0x10024212  call    GetInternetError
0x10024217  mov     ecx, [ebp+var_82C]
0x1002421d  mov     edi, eax
0x1002421f  call    _MemFree@4; MemFree(x)
0x10024224  mov     ecx, ebx
0x10024226  call    _MemFree@4; MemFree(x)
0x1002422b  push    [ebp+var_824]
0x10024231  mov     esi, InternetCloseHandle
0x10024237  mov     ecx, esi
0x10024239  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1002423f  call    esi ; InternetCloseHandle
0x10024241  mov     eax, edi
0x10024243  jmp     short loc_1002426B
0x10024245  mov     ecx, edi
0x10024247  call    _MemFree@4; MemFree(x)
0x1002424c  mov     ecx, ebx
0x1002424e  call    _MemFree@4; MemFree(x)
0x10024253  push    [ebp+var_824]
0x10024259  mov     esi, InternetCloseHandle
0x1002425f  mov     ecx, esi
0x10024261  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10024267  call    esi ; InternetCloseHandle
0x10024269  xor     eax, eax
0x1002426b  mov     ecx, [ebp+var_8]
0x1002426e  pop     edi
0x1002426f  pop     esi
0x10024270  xor     ecx, ebp; StackCookie
0x10024272  pop     ebx
0x10024273  call    @__security_check_cookie@4; __security_check_cookie(x)
0x10024278  leave
0x10024279  retn    4
```
