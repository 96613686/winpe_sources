# CFavorite::SaveFile(IPersistFile *,ushort const *)

- ea: `0x180415bec`
- end: `0x18041605f`
- name: `?SaveFile@CFavorite@@AEAAJPEAUIPersistFile@@PEBG@Z`
- size: `1139`
- prototype: `__int64 __fastcall(CFavorite *__hidden this, struct IPersistFile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180415ae0`

## callees

- `0x18000f3d0`
- `0x180011230`
- `0x180018eb0`
- `0x180018f60`
- `0x18001b970`
- `0x1800906d4`
- `0x1800d2110`
- `0x1800d9190`
- `0x180415bec`
- `0x180416118`
- `0x18041b6bc`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x180415c9a`
- `KERNEL32!CompareStringW` at `0x180415e3c`
- `KERNEL32!CompareStringW` at `0x180415c9a`
- `KERNEL32!CompareStringW` at `0x180415e3c`
- `KERNEL32!GetFileAttributesW` at `0x180415d27`
- `KERNEL32!GetFileAttributesW` at `0x180415d27`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180415ead`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180415ead`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180415c73`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x180415c73`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x180415cc8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x180415e50`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x180415cc8`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x180415e50`
- `OLEAUT32!__imp_SysReAllocString` at `0x180415cd8`
- `OLEAUT32!__imp_SysReAllocString` at `0x180415cd8`
- `SHELL32!SHChangeNotify` at `0x180415d62`
- `SHELL32!SHChangeNotify` at `0x180415f3b`
- `SHELL32!SHChangeNotify` at `0x180416036`
- `SHELL32!SHChangeNotify` at `0x180415d62`
- `SHELL32!SHChangeNotify` at `0x180415f3b`
- `SHELL32!SHChangeNotify` at `0x180416036`
- `SHELL32!SHCreateDirectoryExW` at `0x180415c57`
- `SHELL32!SHCreateDirectoryExW` at `0x180415c57`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x180415f05`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x180415f05`
- `iertutil!__imp_IERegGetBool` at `0x180415f8d`
- `iertutil!__imp_IERegGetBool` at `0x180415f8d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180415f4b`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x180415f4b`

## pseudocode

```c
__int64 __fastcall CFavorite::SaveFile(CFavorite *this, struct IPersistFile *a2, const unsigned __int16 *a3)
{
  int ErrorError; // ebx
  int v6; // eax
  const unsigned __int16 **v7; // r14
  const WCHAR *ExtensionW; // rax
  ULONG v9; // r9d
  int v10; // ecx
  int v11; // ecx
  int v12; // ecx
  int v13; // ecx
  UINT v14; // edx
  size_t v15; // rdx
  unsigned int v16; // ebx
  unsigned __int16 *v17; // r8
  unsigned __int16 *v18; // r8
  const unsigned __int16 *v19; // rcx
  LPVOID v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v22; // [rsp+38h] [rbp-C8h] BYREF
  PCNZWCH lpString1[2]; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszPath[264]; // [rsp+260h] [rbp+160h] BYREF

  ErrorError = 1;
  if ( PathCchCombineEx(pszPathOut, 0x104u, a3, *((PCWSTR *)this + 4), 0) >= 0 )
  {
    v6 = SHCreateDirectoryExW(0, pszPathOut, 0);
    if ( !v6 || v6 == 183 )
    {
      v7 = (const unsigned __int16 **)((char *)this + 24);
      ExtensionW = PathFindExtensionW(*((LPCWSTR *)this + 3));
      if ( CompareStringW(0x7Fu, 1u, ExtensionW, -1, L".url", -1) == 2 )
      {
        ErrorError = StringCchCopyW(pszPath, 0x104u, *v7);
        if ( ErrorError < 0 )
          return (unsigned int)ErrorError;
        PathRemoveExtensionW(pszPath);
        if ( !SysReAllocString((BSTR *)this + 3, pszPath) )
          return (unsigned int)-2147467259;
      }
      if ( PathCchAppendEx(pszPathOut, 0x104u, *v7, v9) >= 0 )
      {
        ErrorError = StringCchCatW(pszPathOut, 0x104u, L".URL");
        if ( ErrorError >= 0 )
        {
          if ( GetFileAttributesW(pszPathOut) == -1 )
          {
            ErrorError = ((__int64 (__fastcall *)(struct IPersistFile *, WCHAR *, _QWORD))a2->lpVtbl->Save)(
                           a2,
                           pszPathOut,
                           0);
            if ( ErrorError < 0 )
              return (unsigned int)ErrorError;
            SHChangeNotify(2, 5u, pszPathOut, 0);
            goto LABEL_41;
          }
          lpString1[0] = 0;
          v21 = 0;
          v22 = 0;
          ErrorError = IECreateInstance(
                         &CLSID_InternetShortcut,
                         0,
                         1u,
                         &GUID_cabb0da0_da57_11cf_9974_0020afd79762,
                         &v21);
          if ( ErrorError < 0 )
            return (unsigned int)ErrorError;
          ErrorError = (**(__int64 (__fastcall ***)(LPVOID, GUID *, unsigned __int16 **))v21)(
                         v21,
                         &GUID_0000010b_0000_0000_c000_000000000046,
                         &v22);
          if ( ErrorError < 0 )
          {
LABEL_40:
            (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v21 + 16LL))(v21);
            if ( ErrorError < 0 )
              return (unsigned int)ErrorError;
LABEL_41:
            LODWORD(v21) = 0;
            IERegGetBool(12, &v21);
            if ( *((_QWORD *)this + 7) && !(_DWORD)v21 )
            {
              v16 = 0;
              WriteMonitoredItemPropertyToFavorite(pszPathOut, L"FeedUrl", *((unsigned __int16 **)this + 5));
              v17 = (unsigned __int16 *)*((_QWORD *)this + 9);
              if ( v17 )
              {
                v16 = 1;
                WriteMonitoredItemPropertyToFavorite(pszPathOut, L"IsLivePreview", v17);
                v18 = (unsigned __int16 *)*((_QWORD *)this + 8);
                if ( v18 )
                  WriteMonitoredItemPropertyToFavorite(pszPathOut, L"PreviewSize", v18);
              }
              ErrorError = EnsureSubscribedUrl(*((_QWORD *)this + 7), *v7, v16, 0);
            }
            if ( *((_QWORD *)this + 10) )
            {
              v19 = (const unsigned __int16 *)*((_QWORD *)this + 5);
              v22 = (unsigned __int16 *)*((_QWORD *)this + 10);
              UpdateFavoriteIcon(v19, pszPathOut, (const unsigned __int16 **)&v22, 1u);
              SHChangeNotify(2, 5u, pszPathOut, 0);
            }
            return (unsigned int)ErrorError;
          }
          ErrorError = (*(__int64 (__fastcall **)(unsigned __int16 *, WCHAR *, _QWORD))(*(_QWORD *)v22 + 40LL))(
                         v22,
                         pszPathOut,
                         0);
          if ( ErrorError < 0
            || (ErrorError = (*(__int64 (__fastcall **)(LPVOID, PCNZWCH *))(*(_QWORD *)v21 + 32LL))(v21, lpString1),
                ErrorError < 0) )
          {
LABEL_39:
            (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v22 + 16LL))(v22);
            goto LABEL_40;
          }
          if ( CompareStringW(0x7Fu, 1u, lpString1[0], -1, *((PCNZWCH *)this + 5), -1) != 2 )
          {
            PathRemoveExtensionW(pszPathOut);
            v10 = *((_DWORD *)this + 2);
            if ( v10 )
            {
              v11 = v10 - 1;
              if ( v11 )
              {
                v12 = v11 - 1;
                if ( v12 )
                {
                  v13 = v12 - 1;
                  if ( v13 )
                  {
                    if ( v13 != 1 )
                    {
                      ErrorError = -2147418113;
                      goto LABEL_38;
                    }
                    v14 = 18236;
                  }
                  else
                  {
                    v14 = 18234;
                  }
                }
                else
                {
                  v14 = 18233;
                }
              }
              else
              {
                v14 = 18232;
              }
            }
            else
            {
              v14 = 18235;
            }
            if ( !LoadStringW(g_hInstResources, v14, pszPath, 260) )
              ErrorError = HRESULTFromLastErrorError();
            if ( ErrorError >= 0 )
            {
              ErrorError = StringCchCatW(pszPathOut, 0x104u, pszPath);
              if ( ErrorError >= 0 && PathCchAddExtension(pszPathOut, v15, L".URL") >= 0 )
              {
                if ( PathYetAnotherMakeUniqueName(pszPathOut, pszPathOut, 0, 0) )
                {
                  ErrorError = ((__int64 (__fastcall *)(struct IPersistFile *, WCHAR *, _QWORD))a2->lpVtbl->Save)(
                                 a2,
                                 pszPathOut,
                                 0);
                  if ( ErrorError >= 0 )
                    SHChangeNotify(2, 5u, pszPathOut, 0);
                }
                else
                {
                  ErrorError = 1;
                }
              }
            }
          }
LABEL_38:
          CoTaskMemFree((LPVOID)lpString1[0]);
          goto LABEL_39;
        }
      }
    }
  }
  return (unsigned int)ErrorError;
}

```

## disassembly

```asm
0x180415bec  push    rbp
0x180415bee  push    rbx
0x180415bef  push    rsi
0x180415bf0  push    rdi
0x180415bf1  push    r12
0x180415bf3  push    r13
0x180415bf5  push    r14
0x180415bf7  lea     rbp, [rsp-380h]
0x180415bff  sub     rsp, 480h
0x180415c06  mov     rax, cs:__security_cookie
0x180415c0d  xor     rax, rsp
0x180415c10  mov     [rbp+3B0h+var_40], rax
0x180415c17  mov     r9, [rcx+20h]; pszMore
0x180415c1b  mov     rsi, rdx
0x180415c1e  mov     rdi, rcx
0x180415c21  mov     [rsp+4B0h+dwFlags], 0; dwFlags
0x180415c29  mov     r13d, 104h
0x180415c2f  lea     rcx, [rsp+4B0h+pszPathOut]; pszPathOut
0x180415c34  mov     r12d, 1
0x180415c3a  mov     edx, r13d; cchPathOut
0x180415c3d  mov     ebx, r12d
0x180415c40  call    PathCchCombineEx
0x180415c45  test    eax, eax
0x180415c47  js      loc_18041603C
0x180415c4d  xor     r8d, r8d; psa
0x180415c50  lea     rdx, [rsp+4B0h+pszPathOut]; pszPath
0x180415c55  xor     ecx, ecx; hwnd
0x180415c57  call    cs:__imp_SHCreateDirectoryExW
0x180415c5d  test    eax, eax
0x180415c5f  jz      short loc_180415C6C
0x180415c61  cmp     eax, 0B7h
0x180415c66  jnz     loc_18041603C
0x180415c6c  lea     r14, [rdi+18h]
0x180415c70  mov     rcx, [r14]; pszPath
0x180415c73  call    cs:__imp_PathFindExtensionW
0x180415c79  or      edx, 0FFFFFFFFh
0x180415c7c  lea     rcx, aUrl_7; ".url"
0x180415c83  mov     [rsp+4B0h+cchCount2], edx; cchCount2
0x180415c87  mov     r9d, edx; cchCount1
0x180415c8a  mov     qword ptr [rsp+4B0h+dwFlags], rcx; lpString2
0x180415c8f  mov     r8, rax; lpString1
0x180415c92  mov     ecx, 7Fh; Locale
0x180415c97  mov     edx, r12d; dwCmpFlags
0x180415c9a  call    cs:__imp_CompareStringW
0x180415ca0  cmp     eax, 2
0x180415ca3  jnz     short loc_180415CEC
0x180415ca5  mov     r8, [r14]; unsigned __int16 *
0x180415ca8  lea     rcx, [rbp+3B0h+pszPath]; unsigned __int16 *
0x180415caf  mov     rdx, r13; unsigned __int64
0x180415cb2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180415cb7  mov     ebx, eax
0x180415cb9  test    eax, eax
0x180415cbb  js      loc_18041603C
0x180415cc1  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x180415cc8  call    cs:__imp_PathRemoveExtensionW
0x180415cce  lea     rdx, [rbp+3B0h+pszPath]; psz
0x180415cd5  mov     rcx, r14; pbstr
0x180415cd8  call    cs:__imp_SysReAllocString
0x180415cde  test    eax, eax
0x180415ce0  jnz     short loc_180415CEC
0x180415ce2  mov     ebx, 80004005h
0x180415ce7  jmp     loc_18041603C
0x180415cec  mov     r8, [r14]; pszMore
0x180415cef  lea     rcx, [rsp+4B0h+pszPathOut]; pszPath
0x180415cf4  mov     rdx, r13; cchPath
0x180415cf7  call    PathCchAppendEx
0x180415cfc  test    eax, eax
0x180415cfe  js      loc_18041603C
0x180415d04  lea     r8, aUrl_3; ".URL"
0x180415d0b  mov     rdx, r13; unsigned __int64
0x180415d0e  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x180415d13  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180415d18  mov     ebx, eax
0x180415d1a  test    eax, eax
0x180415d1c  js      loc_18041603C
0x180415d22  lea     rcx, [rsp+4B0h+pszPathOut]; lpFileName
0x180415d27  call    cs:__imp_GetFileAttributesW
0x180415d2d  cmp     eax, 0FFFFFFFFh
0x180415d30  jnz     short loc_180415D6D
0x180415d32  mov     rax, [rsi]
0x180415d35  lea     rdx, [rsp+4B0h+pszPathOut]
0x180415d3a  xor     r8d, r8d
0x180415d3d  mov     rcx, rsi
0x180415d40  mov     rax, [rax+30h]
0x180415d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180415d49  mov     ebx, eax
0x180415d4b  test    eax, eax
0x180415d4d  js      loc_18041603C
0x180415d53  xor     r9d, r9d; dwItem2
0x180415d56  lea     r8, [rsp+4B0h+pszPathOut]; dwItem1
0x180415d5b  lea     edx, [r9+5]; uFlags
0x180415d5f  lea     ecx, [rdx-3]; wEventId
0x180415d62  call    cs:__imp_SHChangeNotify
0x180415d68  jmp     loc_180415F7B
0x180415d6d  lea     rax, [rsp+4B0h+var_480]
0x180415d72  mov     [rsp+4B0h+lpString1], 0
0x180415d7b  lea     r9, _GUID_cabb0da0_da57_11cf_9974_0020afd79762; riid
0x180415d82  mov     qword ptr [rsp+4B0h+dwFlags], rax; LPVOID *
0x180415d87  mov     r8d, r12d; dwClsContext
0x180415d8a  mov     [rsp+4B0h+var_480], 0
0x180415d93  xor     edx, edx; pUnkOuter
0x180415d95  mov     [rsp+4B0h+var_478], 0
0x180415d9e  lea     rcx, CLSID_InternetShortcut; rclsid
0x180415da5  call    IECreateInstance
0x180415daa  mov     ebx, eax
0x180415dac  test    eax, eax
0x180415dae  js      loc_18041603C
0x180415db4  mov     rcx, [rsp+4B0h+var_480]
0x180415db9  lea     r8, [rsp+4B0h+var_478]
0x180415dbe  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x180415dc5  mov     rax, [rcx]
0x180415dc8  mov     rax, [rax]
0x180415dcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180415dd0  mov     ebx, eax
0x180415dd2  test    eax, eax
0x180415dd4  js      loc_180415F62
0x180415dda  mov     rcx, [rsp+4B0h+var_478]
0x180415ddf  lea     rdx, [rsp+4B0h+pszPathOut]
0x180415de4  xor     r8d, r8d
0x180415de7  mov     rax, [rcx]
0x180415dea  mov     rax, [rax+28h]
0x180415dee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180415df3  mov     ebx, eax
0x180415df5  test    eax, eax
0x180415df7  js      loc_180415F51
0x180415dfd  mov     rcx, [rsp+4B0h+var_480]
0x180415e02  lea     rdx, [rsp+4B0h+lpString1]
0x180415e07  mov     rax, [rcx]
0x180415e0a  mov     rax, [rax+20h]
0x180415e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180415e13  mov     ebx, eax
0x180415e15  test    eax, eax
0x180415e17  js      loc_180415F51
0x180415e1d  mov     rax, [rdi+28h]
0x180415e21  or      r9d, 0FFFFFFFFh; cchCount1
0x180415e25  mov     r8, [rsp+4B0h+lpString1]; lpString1
0x180415e2a  mov     edx, r12d; dwCmpFlags
0x180415e2d  mov     [rsp+4B0h+cchCount2], r9d; cchCount2
0x180415e32  mov     ecx, 7Fh; Locale
0x180415e37  mov     qword ptr [rsp+4B0h+dwFlags], rax; lpString2
0x180415e3c  call    cs:__imp_CompareStringW
0x180415e42  cmp     eax, 2
0x180415e45  jz      loc_180415F46
0x180415e4b  lea     rcx, [rsp+4B0h+pszPathOut]; pszPath
0x180415e50  call    cs:__imp_PathRemoveExtensionW
0x180415e56  mov     ecx, [rdi+8]
0x180415e59  test    ecx, ecx
0x180415e5b  jz      short loc_180415E97
0x180415e5d  sub     ecx, r12d
0x180415e60  jz      short loc_180415E90
0x180415e62  sub     ecx, r12d
0x180415e65  jz      short loc_180415E89
0x180415e67  sub     ecx, r12d
0x180415e6a  jz      short loc_180415E82
0x180415e6c  cmp     ecx, r12d
0x180415e6f  jz      short loc_180415E7B
0x180415e71  mov     ebx, 8000FFFFh
0x180415e76  jmp     loc_180415F46
0x180415e7b  mov     edx, 473Ch
0x180415e80  jmp     short loc_180415E9C
0x180415e82  mov     edx, 473Ah
0x180415e87  jmp     short loc_180415E9C
0x180415e89  mov     edx, 4739h
0x180415e8e  jmp     short loc_180415E9C
0x180415e90  mov     edx, 4738h
0x180415e95  jmp     short loc_180415E9C
0x180415e97  mov     edx, 473Bh; uID
0x180415e9c  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x180415ea3  lea     r8, [rbp+3B0h+pszPath]; lpBuffer
0x180415eaa  mov     r9d, r13d; cchBufferMax
0x180415ead  call    cs:__imp_LoadStringW
0x180415eb3  test    eax, eax
0x180415eb5  jnz     short loc_180415EBE
0x180415eb7  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x180415ebc  mov     ebx, eax
0x180415ebe  test    ebx, ebx
0x180415ec0  js      loc_180415F46
0x180415ec6  lea     r8, [rbp+3B0h+pszPath]; unsigned __int16 *
0x180415ecd  mov     rdx, r13; unsigned __int64
0x180415ed0  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x180415ed5  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180415eda  mov     ebx, eax
0x180415edc  test    eax, eax
0x180415ede  js      short loc_180415F46
0x180415ee0  lea     r8, aUrl_3; ".URL"
0x180415ee7  lea     rcx, [rsp+4B0h+pszPathOut]; pszPath
0x180415eec  call    PathCchAddExtension
0x180415ef1  test    eax, eax
0x180415ef3  js      short loc_180415F46
0x180415ef5  xor     r9d, r9d; pszFileSpec
0x180415ef8  lea     rdx, [rsp+4B0h+pszPathOut]; pszPath
0x180415efd  xor     r8d, r8d; pszShort
0x180415f00  lea     rcx, [rsp+4B0h+pszPathOut]; pszUniqueName
0x180415f05  call    cs:__imp_PathYetAnotherMakeUniqueName
0x180415f0b  test    eax, eax
0x180415f0d  jz      short loc_180415F43
0x180415f0f  mov     rax, [rsi]
0x180415f12  lea     rdx, [rsp+4B0h+pszPathOut]
0x180415f17  xor     r8d, r8d
0x180415f1a  mov     rcx, rsi
0x180415f1d  mov     rax, [rax+30h]
0x180415f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180415f26  mov     ebx, eax
0x180415f28  test    eax, eax
0x180415f2a  js      short loc_180415F46
0x180415f2c  xor     r9d, r9d; dwItem2
0x180415f2f  lea     r8, [rsp+4B0h+pszPathOut]; dwItem1
0x180415f34  lea     edx, [r9+5]; uFlags
0x180415f38  lea     ecx, [rdx-3]; wEventId
0x180415f3b  call    cs:__imp_SHChangeNotify
0x180415f41  jmp     short loc_180415F46
0x180415f43  mov     ebx, r12d
0x180415f46  mov     rcx, [rsp+4B0h+lpString1]; pv
0x180415f4b  call    cs:__imp_CoTaskMemFree
0x180415f51  mov     rcx, [rsp+4B0h+var_478]
0x180415f56  mov     rax, [rcx]
0x180415f59  mov     rax, [rax+10h]
0x180415f5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180415f62  mov     rcx, [rsp+4B0h+var_480]
0x180415f67  mov     rax, [rcx]
0x180415f6a  mov     rax, [rax+10h]
0x180415f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180415f73  test    ebx, ebx
0x180415f75  js      loc_18041603C
0x180415f7b  lea     rdx, [rsp+4B0h+var_480]
0x180415f80  mov     dword ptr [rsp+4B0h+var_480], 0
0x180415f88  mov     ecx, 0Ch
0x180415f8d  call    cs:__imp_IERegGetBool
0x180415f93  cmp     qword ptr [rdi+38h], 0
0x180415f98  jz      short loc_180416003
0x180415f9a  cmp     dword ptr [rsp+4B0h+var_480], 0
0x180415f9f  jnz     short loc_180416003
0x180415fa1  mov     r8, [rdi+28h]; unsigned __int16 *
0x180415fa5  lea     rdx, aFeedurl_0; "FeedUrl"
0x180415fac  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x180415fb1  xor     ebx, ebx
0x180415fb3  call    ?WriteMonitoredItemPropertyToFavorite@@YAJPEBG0PEAG@Z; WriteMonitoredItemPropertyToFavorite(ushort const *,ushort const *,ushort *)
0x180415fb8  mov     r8, [rdi+48h]; unsigned __int16 *
0x180415fbc  test    r8, r8
0x180415fbf  jz      short loc_180415FEF
0x180415fc1  lea     rdx, aIslivepreview_0; "IsLivePreview"
0x180415fc8  mov     ebx, r12d
0x180415fcb  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x180415fd0  call    ?WriteMonitoredItemPropertyToFavorite@@YAJPEBG0PEAG@Z; WriteMonitoredItemPropertyToFavorite(ushort const *,ushort const *,ushort *)
0x180415fd5  mov     r8, [rdi+40h]; unsigned __int16 *
0x180415fd9  test    r8, r8
0x180415fdc  jz      short loc_180415FEF
0x180415fde  lea     rdx, aPreviewsize; "PreviewSize"
0x180415fe5  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x180415fea  call    ?WriteMonitoredItemPropertyToFavorite@@YAJPEBG0PEAG@Z; WriteMonitoredItemPropertyToFavorite(ushort const *,ushort const *,ushort *)
0x180415fef  mov     rdx, [r14]
0x180415ff2  xor     r9d, r9d
0x180415ff5  mov     rcx, [rdi+38h]
0x180415ff9  mov     r8d, ebx
0x180415ffc  call    EnsureSubscribedUrl
0x180416001  mov     ebx, eax
0x180416003  mov     rax, [rdi+50h]
0x180416007  test    rax, rax
0x18041600a  jz      short loc_18041603C
0x18041600c  mov     rcx, [rdi+28h]; unsigned __int16 *
0x180416010  lea     r8, [rsp+4B0h+var_478]; unsigned __int16 **
0x180416015  mov     r9d, r12d; unsigned int
0x180416018  mov     [rsp+4B0h+var_478], rax
0x18041601d  lea     rdx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x180416022  call    ?UpdateFavoriteIcon@@YAJPEBG0PEAPEBGK@Z; UpdateFavoriteIcon(ushort const *,ushort const *,ushort const * *,ulong)
0x180416027  xor     r9d, r9d; dwItem2
0x18041602a  lea     r8, [rsp+4B0h+pszPathOut]; dwItem1
0x18041602f  lea     edx, [r9+5]; uFlags
0x180416033  lea     ecx, [rdx-3]; wEventId
0x180416036  call    cs:__imp_SHChangeNotify
0x18041603c  mov     eax, ebx
0x18041603e  mov     rcx, [rbp+3B0h+var_40]
0x180416045  xor     rcx, rsp; StackCookie
0x180416048  call    __security_check_cookie
0x18041604d  add     rsp, 480h
0x180416054  pop     r14
0x180416056  pop     r13
0x180416058  pop     r12
0x18041605a  pop     rdi
0x18041605b  pop     rsi
0x18041605c  pop     rbx
0x18041605d  pop     rbp
0x18041605e  retn
```
