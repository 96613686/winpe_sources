# HTTPDownloadFile

- ea: `0x10022920`
- end: `0x10022df0`
- name: `HTTPDownloadFile`
- size: `1232`
- prototype: `int __thiscall(wchar_t *FullPath, const WCHAR *, int)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x100234fb`

## callees

- `0x10006400`
- `0x10018b80`
- `0x100224b6`
- `0x10022920`
- `0x1002580a`
- `0x10025ab7`
- `0x100268d8`
- `0x100269a4`
- `0x10032ea8`
- `0x10035510`
- `0x10035b40`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1002299b`
- `api-ms-win-crt-private-l1-1-0!_o__wsplitpath_s` at `0x1002299b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022a19`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022a6b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022b22`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022b7a`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022a19`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022a6b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022b22`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x10022b7a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10022dd8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10022dd8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10022d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10022db1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10022d36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x10022db1`

## pseudocode

```c
int __fastcall HTTPDownloadFile(wchar_t *FullPath, _WORD *a2, WCHAR *a3, int a4)
{
  _DWORD *v6; // ebx
  int v7; // edi
  _DWORD *v8; // esi
  int v9; // edi
  WCHAR *p_WideCharStr; // ecx
  __int16 v11; // ax
  const CHAR *v12; // edi
  CHAR i; // al
  void *v14; // eax
  int InternetError; // eax
  _DWORD *v16; // ecx
  int v17; // edi
  _DWORD *v18; // esi
  const WCHAR *v19; // edx
  LPCWCH v20; // ecx
  __int16 v21; // ax
  void *v22; // edi
  int v23; // eax
  int v24; // ecx
  bool v25; // zf
  DWORD LastError; // eax
  void *v28; // [esp+Ch] [ebp-850h]
  int v29; // [esp+10h] [ebp-84Ch] BYREF
  DWORD v30; // [esp+14h] [ebp-848h] BYREF
  DWORD v31; // [esp+18h] [ebp-844h] BYREF
  _DWORD *v32; // [esp+1Ch] [ebp-840h]
  _DWORD *v33; // [esp+20h] [ebp-83Ch]
  HINTERNET v34; // [esp+24h] [ebp-838h]
  int v35; // [esp+28h] [ebp-834h]
  LPCWSTR lpFileName; // [esp+2Ch] [ebp-830h]
  DWORD nNumberOfBytesToWrite; // [esp+30h] [ebp-82Ch] BYREF
  LPCWCH lpWideCharStr; // [esp+34h] [ebp-828h]
  _DWORD *v39; // [esp+38h] [ebp-824h]
  HANDLE hObject; // [esp+3Ch] [ebp-820h]
  CHAR v41[524]; // [esp+40h] [ebp-81Ch] BYREF
  wchar_t Ext[256]; // [esp+24Ch] [ebp-610h] BYREF
  wchar_t Filename[256]; // [esp+44Ch] [ebp-410h] BYREF
  WCHAR WideCharStr; // [esp+64Ch] [ebp-210h] BYREF
  __int16 v45; // [esp+64Eh] [ebp-20Eh] BYREF

  lpFileName = a3;
  lpWideCharStr = FullPath;
  v30 = 4;
  v31 = 521;
  v35 = 0;
  v6 = 0;
  v34 = 0;
  hObject = 0;
  v32 = 0;
  v33 = 0;
  __wsplitpath_s(FullPath, 0, 0, 0, 0, Filename, 0x100u, Ext, 0x100u);
  WCSCPY2(a3, a2, 0x105u);
  WCSCAT2(a3, Filename, 0x105u);
  WCSCAT2(a3, Ext, 0x105u);
  WCSCPY2(&WideCharStr, FullPath + 7, 0x105u);
  v7 = WideCharToMultiByte(0, 0, &WideCharStr, wcslen(&WideCharStr), 0, 0, 0, 0);
  v8 = (_DWORD *)MemAllocate(v7 + 1);
  v39 = v8;
  if ( v8 )
  {
    p_WideCharStr = &WideCharStr;
    do
      v11 = *p_WideCharStr++;
    while ( v11 != (_WORD)v35 );
    WideCharToMultiByte(0, 0, &WideCharStr, ((char *)p_WideCharStr - (char *)&v45) >> 1, (LPSTR)v8, v7, 0, 0);
    *((_BYTE *)v8 + v7) = 0;
    v12 = (const CHAR *)v8;
    for ( i = *(_BYTE *)v8; i; i = *v12 )
    {
      if ( i == 92 || *v12 == 47 )
      {
        *v12++ = 0;
        break;
      }
      ++v12;
    }
    v14 = InternetConnectA((HINTERNET)dword_1003AE18, (LPCSTR)v8, 0, 0, 0, 1u, 0, 0);
    v28 = v14;
    if ( !v14 )
    {
      InternetError = GetInternetError();
      v16 = v39;
      v9 = InternetError;
LABEL_47:
      MemFree(v16);
LABEL_48:
      if ( v33 )
        MemFree(v33);
      if ( v6 )
        MemFree(v6);
      if ( v32 )
      {
        if ( v6 != v32 )
          MemFree(v32);
      }
      return v9;
    }
    if ( FtpSetCurrentDirectoryA(v14, v12) )
    {
      v9 = -20158;
      goto LABEL_42;
    }
    MemFree(v39);
    v39 = 0;
    v17 = WideCharToMultiByte(0, 0, lpWideCharStr, wcslen(lpWideCharStr), 0, 0, 0, 0);
    v18 = (_DWORD *)MemAllocate(v17 + 1);
    v33 = v18;
    if ( !v18 )
      goto LABEL_17;
    v19 = lpWideCharStr;
    v20 = lpWideCharStr++;
    do
      v21 = *v20++;
    while ( v21 != (_WORD)v35 );
    WideCharToMultiByte(0, 0, v19, v20 - lpWideCharStr, (LPSTR)v18, v17, 0, 0);
    *((_BYTE *)v18 + v17) = 0;
    if ( InternetCanonicalizeUrlA((LPCSTR)v18, v41, &v31, 0) )
    {
      v22 = InternetOpenUrlA((HINTERNET)dword_1003AE18, v41, "Accept: */*", 0xFFFFFFFF, 0, 0);
      v34 = v22;
      if ( v22 )
      {
        if ( HttpQueryInfoA(v22, 0x20000013u, &v29, &v30, 0) )
        {
          if ( v29 != 200 )
          {
            switch ( v29 )
            {
              case 401:
                v9 = -1907;
                break;
              case 404:
                v9 = -1305;
                break;
              case 408:
                v9 = -20157;
                break;
              default:
                v9 = -20161;
                break;
            }
            goto LABEL_42;
          }
          v23 = DOSCreateFile(lpFileName);
          if ( v23 )
          {
            v9 = -1807;
            v24 = -5036;
            v25 = v23 == -4;
LABEL_33:
            if ( !v25 )
              v9 = v24;
LABEL_42:
            InternetCloseHandle(v28);
            if ( v34 )
              InternetCloseHandle(v34);
            if ( hObject )
            {
              CloseHandle(hObject);
              JetDeleteFileW(lpFileName);
            }
            v16 = v39;
            if ( !v39 )
              goto LABEL_48;
            goto LABEL_47;
          }
          v6 = (_DWORD *)MemAllocate(4096);
          if ( !v6 )
          {
LABEL_17:
            v9 = -1011;
            goto LABEL_42;
          }
          v32 = v6;
          while ( InternetReadFile(v22, v6, 0x1000u, &nNumberOfBytesToWrite) )
          {
            if ( !nNumberOfBytesToWrite )
            {
              InternetCloseHandle(v22);
              if ( CloseHandle(hObject) )
              {
                MemFree(v6);
                InternetCloseHandle(v22);
                return 0;
              }
LABEL_58:
              LastError = GetLastError();
              v9 = -1808;
              v24 = -1022;
              v25 = LastError == 112;
              goto LABEL_33;
            }
            if ( DOSWriteFile(hObject, v6, nNumberOfBytesToWrite) == 0xFFFF )
              goto LABEL_58;
          }
        }
      }
    }
    v9 = GetInternetError();
    goto LABEL_42;
  }
  return -1011;
}

```

## disassembly

```asm
0x10022920  mov     edi, edi
0x10022922  push    ebp
0x10022923  mov     ebp, esp
0x10022925  sub     esp, 850h
0x1002292b  mov     eax, ___security_cookie
0x10022930  xor     eax, ebp
0x10022932  mov     [ebp+var_4], eax
0x10022935  mov     eax, [ebp+arg_0]
0x10022938  push    ebx
0x10022939  push    esi
0x1002293a  push    edi
0x1002293b  mov     edi, ecx
0x1002293d  mov     [ebp+lpFileName], eax
0x10022943  mov     ecx, 100h
0x10022948  mov     [ebp+lpWideCharStr], edi
0x1002294e  push    ecx; ExtCount
0x1002294f  lea     eax, [ebp+Ext]
0x10022955  mov     [ebp+var_848], 4
0x1002295f  push    eax; Ext
0x10022960  push    ecx; FilenameCount
0x10022961  lea     eax, [ebp+Filename]
0x10022967  mov     [ebp+var_844], 209h
0x10022971  push    eax; Filename
0x10022972  mov     esi, edx
0x10022974  xor     edx, edx
0x10022976  push    edx; DirCount
0x10022977  push    edx; Dir
0x10022978  push    edx; DriveCount
0x10022979  push    edx; Drive
0x1002297a  push    edi; FullPath
0x1002297b  mov     [ebp+var_834], edx
0x10022981  mov     ebx, edx
0x10022983  mov     [ebp+var_838], edx
0x10022989  mov     [ebp+hObject], edx
0x1002298f  mov     [ebp+var_840], edx
0x10022995  mov     [ebp+var_83C], edx
0x1002299b  call    ds:__imp___wsplitpath_s
0x100229a1  add     esp, 24h
0x100229a4  mov     edx, esi
0x100229a6  mov     esi, [ebp+lpFileName]
0x100229ac  mov     ecx, esi
0x100229ae  push    105h
0x100229b3  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100229b8  push    105h
0x100229bd  lea     edx, [ebp+Filename]
0x100229c3  mov     ecx, esi
0x100229c5  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100229ca  push    105h
0x100229cf  lea     edx, [ebp+Ext]
0x100229d5  mov     ecx, esi
0x100229d7  call    _WCSCAT2@12; WCSCAT2(x,x,x)
0x100229dc  push    105h
0x100229e1  lea     edx, [edi+0Eh]
0x100229e4  lea     ecx, [ebp+WideCharStr]
0x100229ea  call    _WCSCPY2@12; WCSCPY2(x,x,x)
0x100229ef  lea     ecx, [ebp+WideCharStr]
0x100229f5  xor     esi, esi
0x100229f7  lea     edx, [ecx+2]
0x100229fa  mov     ax, [ecx]
0x100229fd  add     ecx, 2
0x10022a00  cmp     ax, si
0x10022a03  jnz     short loc_100229FA
0x10022a05  sub     ecx, edx
0x10022a07  lea     eax, [ebp+WideCharStr]
0x10022a0d  xor     edx, edx
0x10022a0f  sar     ecx, 1
0x10022a11  push    edx; lpUsedDefaultChar
0x10022a12  push    edx; lpDefaultChar
0x10022a13  push    edx; cbMultiByte
0x10022a14  push    edx; lpMultiByteStr
0x10022a15  push    ecx; cchWideChar
0x10022a16  push    eax; lpWideCharStr
0x10022a17  push    edx; dwFlags
0x10022a18  push    edx; CodePage
0x10022a19  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10022a1f  mov     edi, eax
0x10022a21  lea     ecx, [edi+1]
0x10022a24  call    _MemAllocate@4; MemAllocate(x)
0x10022a29  mov     esi, eax
0x10022a2b  mov     [ebp+var_824], esi
0x10022a31  test    esi, esi
0x10022a33  jnz     short loc_10022A3F
0x10022a35  mov     edi, 0FFFFFC0Dh
0x10022a3a  jmp     loc_10022D87
0x10022a3f  lea     ecx, [ebp+WideCharStr]
0x10022a45  lea     edx, [ecx+2]
0x10022a48  mov     ax, [ecx]
0x10022a4b  add     ecx, 2
0x10022a4e  cmp     ax, word ptr [ebp+var_834]
0x10022a55  jnz     short loc_10022A48
0x10022a57  sub     ecx, edx
0x10022a59  lea     eax, [ebp+WideCharStr]
0x10022a5f  xor     edx, edx
0x10022a61  sar     ecx, 1
0x10022a63  push    edx; lpUsedDefaultChar
0x10022a64  push    edx; lpDefaultChar
0x10022a65  push    edi; cbMultiByte
0x10022a66  push    esi; lpMultiByteStr
0x10022a67  push    ecx; cchWideChar
0x10022a68  push    eax; lpWideCharStr
0x10022a69  push    edx; dwFlags
0x10022a6a  push    edx; CodePage
0x10022a6b  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10022a71  xor     ecx, ecx
0x10022a73  mov     [esi+edi], cl
0x10022a76  mov     edi, esi
0x10022a78  mov     al, [esi]
0x10022a7a  jmp     short loc_10022A88
0x10022a7c  cmp     al, 5Ch ; '\'
0x10022a7e  jz      short loc_10022A8E
0x10022a80  cmp     byte ptr [edi], 2Fh ; '/'
0x10022a83  jz      short loc_10022A8E
0x10022a85  inc     edi
0x10022a86  mov     al, [edi]
0x10022a88  test    al, al
0x10022a8a  jnz     short loc_10022A7C
0x10022a8c  jmp     short loc_10022A91
0x10022a8e  mov     [edi], cl
0x10022a90  inc     edi
0x10022a91  push    ecx
0x10022a92  push    ecx
0x10022a93  push    1
0x10022a95  push    ecx
0x10022a96  push    ecx
0x10022a97  push    ecx
0x10022a98  push    esi
0x10022a99  push    dword_1003AE18
0x10022a9f  mov     esi, InternetConnectA
0x10022aa5  mov     ecx, esi
0x10022aa7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10022aad  call    esi ; InternetConnectA
0x10022aaf  mov     [ebp+var_850], eax
0x10022ab5  test    eax, eax
0x10022ab7  jnz     short loc_10022ACB
0x10022ab9  call    GetInternetError
0x10022abe  mov     ecx, [ebp+var_824]
0x10022ac4  mov     edi, eax
0x10022ac6  jmp     loc_10022D51
0x10022acb  mov     esi, FtpSetCurrentDirectoryA
0x10022ad1  mov     ecx, esi
0x10022ad3  push    edi
0x10022ad4  push    eax
0x10022ad5  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10022adb  call    esi ; FtpSetCurrentDirectoryA
0x10022add  test    eax, eax
0x10022adf  jz      short loc_10022AEB
0x10022ae1  mov     edi, 0FFFFB142h
0x10022ae6  jmp     loc_10022CFA
0x10022aeb  mov     ecx, [ebp+var_824]
0x10022af1  call    _MemFree@4; MemFree(x)
0x10022af6  mov     edx, [ebp+lpWideCharStr]
0x10022afc  xor     edi, edi
0x10022afe  mov     ecx, edx
0x10022b00  mov     [ebp+var_824], edi
0x10022b06  lea     esi, [ecx+2]
0x10022b09  mov     ax, [ecx]
0x10022b0c  add     ecx, 2
0x10022b0f  cmp     ax, di
0x10022b12  jnz     short loc_10022B09
0x10022b14  xor     eax, eax
0x10022b16  sub     ecx, esi
0x10022b18  push    eax; lpUsedDefaultChar
0x10022b19  push    eax; lpDefaultChar
0x10022b1a  push    eax; cbMultiByte
0x10022b1b  push    eax; lpMultiByteStr
0x10022b1c  sar     ecx, 1
0x10022b1e  push    ecx; cchWideChar
0x10022b1f  push    edx; lpWideCharStr
0x10022b20  push    eax; dwFlags
0x10022b21  push    eax; CodePage
0x10022b22  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10022b28  mov     edi, eax
0x10022b2a  lea     ecx, [edi+1]
0x10022b2d  call    _MemAllocate@4; MemAllocate(x)
0x10022b32  mov     esi, eax
0x10022b34  mov     [ebp+var_83C], esi
0x10022b3a  test    esi, esi
0x10022b3c  jnz     short loc_10022B48
0x10022b3e  mov     edi, 0FFFFFC0Dh
0x10022b43  jmp     loc_10022CFA
0x10022b48  mov     edx, [ebp+lpWideCharStr]
0x10022b4e  mov     ecx, edx
0x10022b50  lea     eax, [ecx+2]
0x10022b53  mov     [ebp+lpWideCharStr], eax
0x10022b59  mov     ax, [ecx]
0x10022b5c  add     ecx, 2
0x10022b5f  cmp     ax, word ptr [ebp+var_834]
0x10022b66  jnz     short loc_10022B59
0x10022b68  sub     ecx, [ebp+lpWideCharStr]
0x10022b6e  xor     eax, eax
0x10022b70  push    eax; lpUsedDefaultChar
0x10022b71  push    eax; lpDefaultChar
0x10022b72  push    edi; cbMultiByte
0x10022b73  push    esi; lpMultiByteStr
0x10022b74  sar     ecx, 1
0x10022b76  push    ecx; cchWideChar
0x10022b77  push    edx; lpWideCharStr
0x10022b78  push    eax; dwFlags
0x10022b79  push    eax; CodePage
0x10022b7a  call    ds:__imp__WideCharToMultiByte@32; WideCharToMultiByte(x,x,x,x,x,x,x,x)
0x10022b80  xor     eax, eax
0x10022b82  push    eax
0x10022b83  mov     [edi+esi], al
0x10022b86  lea     eax, [ebp+var_844]
0x10022b8c  push    eax
0x10022b8d  lea     eax, [ebp+var_81C]
0x10022b93  push    eax
0x10022b94  push    esi
0x10022b95  mov     esi, InternetCanonicalizeUrlA
0x10022b9b  mov     ecx, esi
0x10022b9d  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10022ba3  call    esi ; InternetCanonicalizeUrlA
0x10022ba5  test    eax, eax
0x10022ba7  jz      loc_10022CF3
0x10022bad  mov     esi, InternetOpenUrlA
0x10022bb3  xor     eax, eax
0x10022bb5  push    eax
0x10022bb6  push    eax
0x10022bb7  push    0FFFFFFFFh
0x10022bb9  push    offset aAccept; "Accept: */*"
0x10022bbe  lea     eax, [ebp+var_81C]
0x10022bc4  mov     ecx, esi
0x10022bc6  push    eax
0x10022bc7  push    dword_1003AE18
0x10022bcd  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10022bd3  call    esi ; InternetOpenUrlA
0x10022bd5  mov     edi, eax
0x10022bd7  mov     [ebp+var_838], edi
0x10022bdd  test    edi, edi
0x10022bdf  jz      loc_10022CF3
0x10022be5  mov     esi, HttpQueryInfoA
0x10022beb  lea     eax, [ebp+var_848]
0x10022bf1  push    0
0x10022bf3  push    eax
0x10022bf4  lea     eax, [ebp+var_84C]
0x10022bfa  mov     ecx, esi
0x10022bfc  push    eax
0x10022bfd  push    20000013h
0x10022c02  push    edi
0x10022c03  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10022c09  call    esi ; HttpQueryInfoA
0x10022c0b  test    eax, eax
0x10022c0d  jz      loc_10022CF3
0x10022c13  mov     eax, [ebp+var_84C]
0x10022c19  cmp     eax, 0C8h
0x10022c1e  jz      short loc_10022C59
0x10022c20  sub     eax, 191h
0x10022c25  jz      short loc_10022C4F
0x10022c27  sub     eax, 3
0x10022c2a  jz      short loc_10022C45
0x10022c2c  sub     eax, 4
0x10022c2f  jz      short loc_10022C3B
0x10022c31  mov     edi, 0FFFFB13Fh
0x10022c36  jmp     loc_10022CFA
0x10022c3b  mov     edi, 0FFFFB143h
0x10022c40  jmp     loc_10022CFA
0x10022c45  mov     edi, 0FFFFFAE7h
0x10022c4a  jmp     loc_10022CFA
0x10022c4f  mov     edi, 0FFFFF88Dh
0x10022c54  jmp     loc_10022CFA
0x10022c59  mov     ecx, [ebp+lpFileName]; lpFileName
0x10022c5f  lea     edx, [ebp+hObject]
0x10022c65  call    _DOSCreateFile@8; DOSCreateFile(x,x)
0x10022c6a  test    eax, eax
0x10022c6c  jz      short loc_10022C80
0x10022c6e  mov     edi, 0FFFFF8F1h
0x10022c73  mov     ecx, 0FFFFEC54h
0x10022c78  cmp     eax, 0FFFFFFFCh
0x10022c7b  cmovnz  edi, ecx
0x10022c7e  jmp     short loc_10022CFA
0x10022c80  mov     esi, 1000h
0x10022c85  mov     ecx, esi
0x10022c87  call    _MemAllocate@4; MemAllocate(x)
0x10022c8c  mov     ebx, eax
0x10022c8e  test    ebx, ebx
0x10022c90  jz      loc_10022B3E
0x10022c96  lea     eax, [ebp+nNumberOfBytesToWrite]
0x10022c9c  mov     [ebp+var_840], ebx
0x10022ca2  push    eax
0x10022ca3  push    esi
0x10022ca4  jmp     short loc_10022CDD
0x10022ca6  cmp     [ebp+nNumberOfBytesToWrite], 0
0x10022cad  jz      loc_10022D9A
0x10022cb3  push    [ebp+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x10022cb9  mov     ecx, [ebp+hObject]; hFile
0x10022cbf  mov     edx, ebx; lpBuffer
0x10022cc1  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x10022cc6  cmp     eax, 0FFFFh
0x10022ccb  jz      loc_10022DD8
0x10022cd1  lea     eax, [ebp+nNumberOfBytesToWrite]
0x10022cd7  push    eax
0x10022cd8  push    1000h
0x10022cdd  mov     esi, InternetReadFile
0x10022ce3  mov     ecx, esi
0x10022ce5  push    ebx
0x10022ce6  push    edi
0x10022ce7  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10022ced  call    esi ; InternetReadFile
0x10022cef  test    eax, eax
0x10022cf1  jnz     short loc_10022CA6
  ... truncated ...
```
