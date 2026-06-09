# CCatalogServer::DeleteRecursive(ushort const *)

- ea: `0x18000e468`
- end: `0x18000e7d8`
- name: `?DeleteRecursive@CCatalogServer@@AEAAJPEBG@Z`
- size: `880`
- prototype: `__int64 __fastcall(CCatalogServer *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18000a310`
- `0x18000ab10`
- `0x18000e468`

## callees

- `0x180009098`
- `0x18000a01c`
- `0x18000e468`
- `0x18001a6c8`
- `0x18001ec1c`
- `0x18005551a`
- `0x180055550`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000e5be`
- `msvcrt!_wcsicmp` at `0x18000e5d8`
- `msvcrt!_wcsicmp` at `0x18000e5be`
- `msvcrt!_wcsicmp` at `0x18000e5d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e53b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e70e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e53b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e6f7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e70e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000e794`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000e794`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000e6e9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18000e6e9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000e52c`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000e52c`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000e6a6`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x18000e6a6`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e6d7`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18000e6d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e79d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e5e9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e79d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000e7a6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e4d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e625`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e4d6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e625`

## string_xrefs

- `0x18000e57e`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000e758`: `com\complus\src\comcat\catsrv\reputil.cpp`
- `0x18000e723`: `'DeleteRecursive:DeleteFile'`
- `0x18000e742`: `'DeleteRecursive:FindNextFile'`
- `0x18000e6c5`: `'DeleteRecursive:RemoveDirectory'`
- `0x18000e567`: `'DeleteRecursive:FindFirstFile'`

## pseudocode

```c
__int64 __fastcall CCatalogServer::DeleteRecursive(CCatalogServer *this, const unsigned __int16 *a2)
{
  unsigned __int16 *v4; // rdi
  unsigned __int64 v5; // rsi
  unsigned __int16 *v6; // rax
  unsigned __int16 *v7; // r15
  signed int v8; // ebx
  HANDLE FirstFileW; // r14
  signed int LastError; // eax
  __int64 v11; // r8
  int v12; // eax
  SIZE_T v13; // r9
  int v14; // r8d
  unsigned __int64 v15; // rsi
  SIZE_T v16; // rax
  unsigned __int16 *v17; // rax
  signed int v18; // eax
  const unsigned __int16 *v19; // r9
  unsigned int v20; // r8d
  signed int v21; // eax
  signed int v22; // eax
  signed int v24; // [rsp+20h] [rbp-E0h] BYREF
  __int16 v25; // [rsp+24h] [rbp-DCh]
  int v26; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v27; // [rsp+30h] [rbp-D0h]
  __int64 v28; // [rsp+38h] [rbp-C8h]
  __int64 v29; // [rsp+40h] [rbp-C0h]
  int v30; // [rsp+48h] [rbp-B8h]
  int v31; // [rsp+4Ch] [rbp-B4h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF

  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v4 = 0;
  v5 = (int)(safe_lstrlenW(a2) + 5);
  v6 = (unsigned __int16 *)CoTaskMemAlloc(saturated_mul(v5, 2u));
  v7 = v6;
  if ( v6 )
  {
    v8 = StringCchCopyW(v6, v5, a2);
    if ( v8 >= 0 )
    {
      v8 = StringCchCatW(v7, v5, L"\\*.*");
      if ( v8 >= 0 )
      {
        FirstFileW = FindFirstFileW(v7, &FindFileData);
        if ( FirstFileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          if ( (unsigned int)(LastError - 2) > 1 )
          {
            if ( LastError > 0 )
              v8 = (unsigned __int16)LastError | 0x80070000;
            else
              v8 = LastError;
            v24 = v8;
            v25 = 22;
            v27 = L"'DeleteRecursive:FindFirstFile'";
            v26 = -1073737001;
            v28 = 0;
            v29 = 0;
            v30 = 0;
            v31 = 1;
            CError::WriteToLog(
              (CError *)&v24,
              L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp",
              0x31Au,
              L"'DeleteRecursive:FindFirstFile'");
          }
        }
        else
        {
          do
          {
            if ( _wcsicmp(FindFileData.cFileName, L".") && _wcsicmp(FindFileData.cFileName, L"..") )
            {
              CoTaskMemFree(v4);
              v11 = -1;
              do
                ++v11;
              while ( FindFileData.cFileName[v11] );
              v12 = safe_lstrlenW(a2);
              v15 = v14 + v12 + 2;
              v16 = 2 * v15;
              if ( !is_mul_ok(v15, 2u) )
                v16 = v13;
              v17 = (unsigned __int16 *)CoTaskMemAlloc(v16);
              v4 = v17;
              if ( !v17 )
              {
                v8 = -2147024882;
                goto LABEL_39;
              }
              v8 = StringCchCopyW(v17, v15, a2);
              if ( v8 < 0 )
                goto LABEL_39;
              v8 = StringCchCatW(v4, v15, L"\\");
              if ( v8 < 0 )
                goto LABEL_39;
              v8 = StringCchCatW(v4, v15, FindFileData.cFileName);
              if ( v8 < 0 )
                goto LABEL_39;
              if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
              {
                v8 = CCatalogServer::DeleteRecursive(this, v4);
                if ( v8 < 0 )
                  goto LABEL_39;
                if ( !RemoveDirectoryW(v4) )
                {
                  v18 = GetLastError();
                  v8 = v18;
                  if ( v18 > 0 )
                    v8 = (unsigned __int16)v18 | 0x80070000;
                  v19 = L"'DeleteRecursive:RemoveDirectory'";
                  v20 = 829;
                  goto LABEL_38;
                }
              }
              else if ( !DeleteFileW(v4) )
              {
                v22 = GetLastError();
                v8 = v22;
                if ( v22 > 0 )
                  v8 = (unsigned __int16)v22 | 0x80070000;
                v19 = L"'DeleteRecursive:DeleteFile'";
                v20 = 839;
                goto LABEL_38;
              }
            }
          }
          while ( FindNextFileW(FirstFileW, &FindFileData) );
          v21 = GetLastError();
          if ( v21 == 18 )
            goto LABEL_39;
          if ( v21 > 0 )
            v8 = (unsigned __int16)v21 | 0x80070000;
          else
            v8 = v21;
          v19 = L"'DeleteRecursive:FindNextFile'";
          v20 = 850;
LABEL_38:
          v24 = v8;
          v25 = 22;
          v26 = -1073737001;
          v27 = v19;
          v28 = 0;
          v29 = 0;
          v30 = 0;
          v31 = 1;
          CError::WriteToLog((CError *)&v24, L"com\\complus\\src\\comcat\\catsrv\\reputil.cpp", v20, v19);
LABEL_39:
          FindClose(FirstFileW);
        }
      }
    }
  }
  else
  {
    v8 = -2147024882;
  }
  CoTaskMemFree(v4);
  CoTaskMemFree(v7);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18000e468  mov     [rsp-8+arg_10], rbx
0x18000e46d  push    rbp
0x18000e46e  push    rsi
0x18000e46f  push    rdi
0x18000e470  push    r12
0x18000e472  push    r13
0x18000e474  push    r14
0x18000e476  push    r15
0x18000e478  lea     rbp, [rsp-1B0h]
0x18000e480  sub     rsp, 2B0h
0x18000e487  mov     rax, cs:__security_cookie
0x18000e48e  xor     rax, rsp
0x18000e491  mov     [rbp+1E0h+var_40], rax
0x18000e498  mov     r12, rdx
0x18000e49b  mov     r13, rcx
0x18000e49e  xor     edx, edx; Val
0x18000e4a0  lea     rcx, [rsp+2E0h+FindFileData]; void *
0x18000e4a5  mov     r8d, 250h; Size
0x18000e4ab  call    memset_0
0x18000e4b0  xor     r14d, r14d
0x18000e4b3  mov     rcx, r12; unsigned __int16 *
0x18000e4b6  mov     edi, r14d
0x18000e4b9  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000e4be  add     eax, 5
0x18000e4c1  lea     rcx, [r14-1]
0x18000e4c5  movsxd  rsi, eax
0x18000e4c8  lea     eax, [r14+2]
0x18000e4cc  mul     rsi
0x18000e4cf  cmovb   rax, rcx
0x18000e4d3  mov     rcx, rax; cb
0x18000e4d6  call    cs:__imp_CoTaskMemAlloc
0x18000e4dc  mov     r15, rax
0x18000e4df  test    rax, rax
0x18000e4e2  jnz     short loc_18000E4EE
0x18000e4e4  mov     ebx, 8007000Eh
0x18000e4e9  jmp     loc_18000E79A
0x18000e4ee  mov     r8, r12; unsigned __int16 *
0x18000e4f1  mov     rdx, rsi; unsigned __int64
0x18000e4f4  mov     rcx, r15; unsigned __int16 *
0x18000e4f7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e4fc  mov     ebx, eax
0x18000e4fe  test    eax, eax
0x18000e500  js      loc_18000E79A
0x18000e506  lea     r8, asc_18005EA88; "\\*.*"
0x18000e50d  mov     rdx, rsi; unsigned __int64
0x18000e510  mov     rcx, r15; unsigned __int16 *
0x18000e513  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e518  xor     esi, esi
0x18000e51a  mov     ebx, eax
0x18000e51c  test    eax, eax
0x18000e51e  js      loc_18000E79A
0x18000e524  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18000e529  mov     rcx, r15; lpFileName
0x18000e52c  call    cs:__imp_FindFirstFileW
0x18000e532  mov     r14, rax
0x18000e535  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000e539  jnz     short loc_18000E5B2
0x18000e53b  call    cs:__imp_GetLastError
0x18000e541  lea     ecx, [rax-2]
0x18000e544  cmp     ecx, 1
0x18000e547  jbe     loc_18000E79A
0x18000e54d  test    eax, eax
0x18000e54f  jg      short loc_18000E555
0x18000e551  mov     ebx, eax
0x18000e553  jmp     short loc_18000E55E
0x18000e555  movzx   ebx, ax
0x18000e558  or      ebx, 80070000h
0x18000e55e  mov     eax, 16h
0x18000e563  mov     [rsp+2E0h+var_2C0], ebx
0x18000e567  lea     r9, aDeleterecursiv_2; "'DeleteRecursive:FindFirstFile'"
0x18000e56e  mov     [rsp+2E0h+var_2BC], ax
0x18000e573  mov     r8d, 31Ah; unsigned int
0x18000e579  mov     [rsp+2E0h+var_2B0], r9
0x18000e57e  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000e585  mov     [rsp+2E0h+var_2B8], 0C00012D7h
0x18000e58d  lea     rcx, [rsp+2E0h+var_2C0]; this
0x18000e592  mov     [rsp+2E0h+var_2A8], rsi
0x18000e597  mov     [rsp+2E0h+var_2A0], rsi
0x18000e59c  mov     [rsp+2E0h+var_298], esi
0x18000e5a0  mov     [rsp+2E0h+var_294], 1
0x18000e5a8  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000e5ad  jmp     loc_18000E79A
0x18000e5b2  lea     rdx, asc_18005EA94; "."
0x18000e5b9  lea     rcx, [rsp+2E0h+FindFileData.cFileName]; String1
0x18000e5be  call    cs:__imp__wcsicmp
0x18000e5c4  test    eax, eax
0x18000e5c6  jz      loc_18000E6E1
0x18000e5cc  lea     rdx, asc_18005EA98; ".."
0x18000e5d3  lea     rcx, [rsp+2E0h+FindFileData.cFileName]; String1
0x18000e5d8  call    cs:__imp__wcsicmp
0x18000e5de  test    eax, eax
0x18000e5e0  jz      loc_18000E6E1
0x18000e5e6  mov     rcx, rdi; pv
0x18000e5e9  call    cs:__imp_CoTaskMemFree
0x18000e5ef  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000e5f3  lea     rax, [rsp+2E0h+FindFileData.cFileName]
0x18000e5f8  mov     r8, r9
0x18000e5fb  inc     r8
0x18000e5fe  cmp     [rax+r8*2], si
0x18000e603  jnz     short loc_18000E5FB
0x18000e605  mov     rcx, r12; unsigned __int16 *
0x18000e608  call    ?safe_lstrlenW@@YAHPEBG@Z; safe_lstrlenW(ushort const *)
0x18000e60d  lea     ecx, [rax+2]
0x18000e610  mov     eax, 2
0x18000e615  add     ecx, r8d
0x18000e618  movsxd  rsi, ecx
0x18000e61b  mul     rsi
0x18000e61e  cmovb   rax, r9
0x18000e622  mov     rcx, rax; cb
0x18000e625  call    cs:__imp_CoTaskMemAlloc
0x18000e62b  mov     rdi, rax
0x18000e62e  test    rax, rax
0x18000e631  jz      loc_18000E732
0x18000e637  mov     r8, r12; unsigned __int16 *
0x18000e63a  mov     rdx, rsi; unsigned __int64
0x18000e63d  mov     rcx, rax; unsigned __int16 *
0x18000e640  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e645  mov     ebx, eax
0x18000e647  test    eax, eax
0x18000e649  js      loc_18000E791
0x18000e64f  lea     r8, asc_18005D30C; "\\"
0x18000e656  mov     rdx, rsi; unsigned __int64
0x18000e659  mov     rcx, rdi; unsigned __int16 *
0x18000e65c  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e661  mov     ebx, eax
0x18000e663  test    eax, eax
0x18000e665  js      loc_18000E791
0x18000e66b  lea     r8, [rsp+2E0h+FindFileData.cFileName]; unsigned __int16 *
0x18000e670  mov     rdx, rsi; unsigned __int64
0x18000e673  mov     rcx, rdi; unsigned __int16 *
0x18000e676  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000e67b  xor     esi, esi
0x18000e67d  mov     ebx, eax
0x18000e67f  test    eax, eax
0x18000e681  js      loc_18000E791
0x18000e687  test    byte ptr [rsp+2E0h+FindFileData.dwFileAttributes], 10h
0x18000e68c  jz      short loc_18000E6D4
0x18000e68e  mov     rdx, rdi; unsigned __int16 *
0x18000e691  mov     rcx, r13; this
0x18000e694  call    ?DeleteRecursive@CCatalogServer@@AEAAJPEBG@Z; CCatalogServer::DeleteRecursive(ushort const *)
0x18000e699  mov     ebx, eax
0x18000e69b  test    eax, eax
0x18000e69d  js      loc_18000E791
0x18000e6a3  mov     rcx, rdi; lpPathName
0x18000e6a6  call    cs:__imp_RemoveDirectoryW
0x18000e6ac  test    eax, eax
0x18000e6ae  jnz     short loc_18000E6E1
0x18000e6b0  call    cs:__imp_GetLastError
0x18000e6b6  mov     ebx, eax
0x18000e6b8  test    eax, eax
0x18000e6ba  jle     short loc_18000E6C5
0x18000e6bc  movzx   ebx, ax
0x18000e6bf  or      ebx, 80070000h
0x18000e6c5  lea     r9, aDeleterecursiv; "'DeleteRecursive:RemoveDirectory'"
0x18000e6cc  mov     r8d, 33Dh
0x18000e6d2  jmp     short loc_18000E74F
0x18000e6d4  mov     rcx, rdi; lpFileName
0x18000e6d7  call    cs:__imp_DeleteFileW
0x18000e6dd  test    eax, eax
0x18000e6df  jz      short loc_18000E70E
0x18000e6e1  lea     rdx, [rsp+2E0h+FindFileData]; lpFindFileData
0x18000e6e6  mov     rcx, r14; hFindFile
0x18000e6e9  call    cs:__imp_FindNextFileW
0x18000e6ef  test    eax, eax
0x18000e6f1  jnz     loc_18000E5B2
0x18000e6f7  call    cs:__imp_GetLastError
0x18000e6fd  cmp     eax, 12h
0x18000e700  jz      loc_18000E791
0x18000e706  test    eax, eax
0x18000e708  jg      short loc_18000E739
0x18000e70a  mov     ebx, eax
0x18000e70c  jmp     short loc_18000E742
0x18000e70e  call    cs:__imp_GetLastError
0x18000e714  mov     ebx, eax
0x18000e716  test    eax, eax
0x18000e718  jle     short loc_18000E723
0x18000e71a  movzx   ebx, ax
0x18000e71d  or      ebx, 80070000h
0x18000e723  lea     r9, aDeleterecursiv_0; "'DeleteRecursive:DeleteFile'"
0x18000e72a  mov     r8d, 347h
0x18000e730  jmp     short loc_18000E74F
0x18000e732  mov     ebx, 8007000Eh
0x18000e737  jmp     short loc_18000E791
0x18000e739  movzx   ebx, ax
0x18000e73c  or      ebx, 80070000h
0x18000e742  lea     r9, aDeleterecursiv_1; "'DeleteRecursive:FindNextFile'"
0x18000e749  mov     r8d, 352h; unsigned int
0x18000e74f  mov     eax, 16h
0x18000e754  mov     [rsp+2E0h+var_2C0], ebx
0x18000e758  lea     rdx, aComComplusSrcC_0; "com\\complus\\src\\comcat\\catsrv\\repu"...
0x18000e75f  mov     [rsp+2E0h+var_2BC], ax
0x18000e764  lea     rcx, [rsp+2E0h+var_2C0]; this
0x18000e769  mov     [rsp+2E0h+var_2B8], 0C00012D7h
0x18000e771  mov     [rsp+2E0h+var_2B0], r9
0x18000e776  mov     [rsp+2E0h+var_2A8], rsi
0x18000e77b  mov     [rsp+2E0h+var_2A0], rsi
0x18000e780  mov     [rsp+2E0h+var_298], esi
0x18000e784  mov     [rsp+2E0h+var_294], 1
0x18000e78c  call    ?WriteToLog@CError@@QEAAXPEBGI0ZZ; CError::WriteToLog(ushort const *,uint,ushort const *,...)
0x18000e791  mov     rcx, r14; hFindFile
0x18000e794  call    cs:__imp_FindClose
0x18000e79a  mov     rcx, rdi; pv
0x18000e79d  call    cs:__imp_CoTaskMemFree
0x18000e7a3  mov     rcx, r15; pv
0x18000e7a6  call    cs:__imp_CoTaskMemFree
0x18000e7ac  mov     eax, ebx
0x18000e7ae  mov     rcx, [rbp+1E0h+var_40]
0x18000e7b5  xor     rcx, rsp; StackCookie
0x18000e7b8  call    __security_check_cookie
0x18000e7bd  mov     rbx, [rsp+2E0h+arg_10]
0x18000e7c5  add     rsp, 2B0h
0x18000e7cc  pop     r15
0x18000e7ce  pop     r14
0x18000e7d0  pop     r13
0x18000e7d2  pop     r12
0x18000e7d4  pop     rdi
0x18000e7d5  pop     rsi
0x18000e7d6  pop     rbp
0x18000e7d7  retn
```
