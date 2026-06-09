# CFavorite::SaveFile(IPersistFile *,ushort const *)

- ea: `0x18044e808`
- end: `0x18044ecd6`
- name: `?SaveFile@CFavorite@@AEAAJPEAUIPersistFile@@PEBG@Z`
- size: `1230`
- prototype: `__int64 __fastcall(CFavorite *__hidden this, struct IPersistFile *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18044e6f0`

## callees

- `0x180005b3c`
- `0x180005bf0`
- `0x1800123f0`
- `0x1800144d0`
- `0x18001d0b0`
- `0x180097100`
- `0x1800da420`
- `0x1800e1d90`
- `0x18044e808`
- `0x18044ed9c`
- `0x1804545e4`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!CompareStringW` at `0x18044e8c2`
- `KERNEL32!CompareStringW` at `0x18044ea82`
- `KERNEL32!CompareStringW` at `0x18044e8c2`
- `KERNEL32!CompareStringW` at `0x18044ea82`
- `KERNEL32!GetFileAttributesW` at `0x18044e961`
- `KERNEL32!GetFileAttributesW` at `0x18044e961`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18044eaff`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18044eaff`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x18044e895`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x18044e895`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x18044e8f6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x18044ea9c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x18044e8f6`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathRemoveExtensionW` at `0x18044ea9c`
- `OLEAUT32!__imp_SysReAllocString` at `0x18044e90c`
- `OLEAUT32!__imp_SysReAllocString` at `0x18044e90c`
- `SHELL32!SHChangeNotify` at `0x18044e9a2`
- `SHELL32!SHChangeNotify` at `0x18044eb99`
- `SHELL32!SHChangeNotify` at `0x18044eca6`
- `SHELL32!SHChangeNotify` at `0x18044e9a2`
- `SHELL32!SHChangeNotify` at `0x18044eb99`
- `SHELL32!SHChangeNotify` at `0x18044eca6`
- `SHELL32!SHCreateDirectoryExW` at `0x18044e873`
- `SHELL32!SHCreateDirectoryExW` at `0x18044e873`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x18044eb5d`
- `SHELL32!__imp_PathYetAnotherMakeUniqueName` at `0x18044eb5d`
- `iertutil!__imp_IERegGetBool` at `0x18044ebf7`
- `iertutil!__imp_IERegGetBool` at `0x18044ebf7`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18044ebaf`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18044ebaf`

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
0x18044e808  push    rbp
0x18044e80a  push    rbx
0x18044e80b  push    rsi
0x18044e80c  push    rdi
0x18044e80d  push    r12
0x18044e80f  push    r13
0x18044e811  push    r14
0x18044e813  lea     rbp, [rsp-380h]
0x18044e81b  sub     rsp, 480h
0x18044e822  mov     rax, cs:__security_cookie
0x18044e829  xor     rax, rsp
0x18044e82c  mov     [rbp+3B0h+var_40], rax
0x18044e833  mov     r9, [rcx+20h]; pszMore
0x18044e837  mov     rsi, rdx
0x18044e83a  mov     rdi, rcx
0x18044e83d  mov     [rsp+4B0h+dwFlags], 0; dwFlags
0x18044e845  mov     r13d, 104h
0x18044e84b  lea     rcx, [rsp+4B0h+pszPathOut]; pszPathOut
0x18044e850  mov     r12d, 1
0x18044e856  mov     edx, r13d; cchPathOut
0x18044e859  mov     ebx, r12d
0x18044e85c  call    PathCchCombineEx
0x18044e861  test    eax, eax
0x18044e863  js      loc_18044ECB2
0x18044e869  xor     r8d, r8d; psa
0x18044e86c  lea     rdx, [rsp+4B0h+pszPathOut]; pszPath
0x18044e871  xor     ecx, ecx; hwnd
0x18044e873  call    cs:__imp_SHCreateDirectoryExW
0x18044e87a  nop     dword ptr [rax+rax+00h]
0x18044e87f  test    eax, eax
0x18044e881  jz      short loc_18044E88E
0x18044e883  cmp     eax, 0B7h
0x18044e888  jnz     loc_18044ECB2
0x18044e88e  lea     r14, [rdi+18h]
0x18044e892  mov     rcx, [r14]; pszPath
0x18044e895  call    cs:__imp_PathFindExtensionW
0x18044e89c  nop     dword ptr [rax+rax+00h]
0x18044e8a1  or      edx, 0FFFFFFFFh
0x18044e8a4  lea     rcx, aUrl_7; ".url"
0x18044e8ab  mov     [rsp+4B0h+cchCount2], edx; cchCount2
0x18044e8af  mov     r9d, edx; cchCount1
0x18044e8b2  mov     qword ptr [rsp+4B0h+dwFlags], rcx; lpString2
0x18044e8b7  mov     r8, rax; lpString1
0x18044e8ba  mov     ecx, 7Fh; Locale
0x18044e8bf  mov     edx, r12d; dwCmpFlags
0x18044e8c2  call    cs:__imp_CompareStringW
0x18044e8c9  nop     dword ptr [rax+rax+00h]
0x18044e8ce  cmp     eax, 2
0x18044e8d1  jnz     short loc_18044E926
0x18044e8d3  mov     r8, [r14]; unsigned __int16 *
0x18044e8d6  lea     rcx, [rbp+3B0h+pszPath]; unsigned __int16 *
0x18044e8dd  mov     rdx, r13; unsigned __int64
0x18044e8e0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18044e8e5  mov     ebx, eax
0x18044e8e7  test    eax, eax
0x18044e8e9  js      loc_18044ECB2
0x18044e8ef  lea     rcx, [rbp+3B0h+pszPath]; pszPath
0x18044e8f6  call    cs:__imp_PathRemoveExtensionW
0x18044e8fd  nop     dword ptr [rax+rax+00h]
0x18044e902  lea     rdx, [rbp+3B0h+pszPath]; psz
0x18044e909  mov     rcx, r14; pbstr
0x18044e90c  call    cs:__imp_SysReAllocString
0x18044e913  nop     dword ptr [rax+rax+00h]
0x18044e918  test    eax, eax
0x18044e91a  jnz     short loc_18044E926
0x18044e91c  mov     ebx, 80004005h
0x18044e921  jmp     loc_18044ECB2
0x18044e926  mov     r8, [r14]; pszMore
0x18044e929  lea     rcx, [rsp+4B0h+pszPathOut]; pszPath
0x18044e92e  mov     rdx, r13; cchPath
0x18044e931  call    PathCchAppendEx
0x18044e936  test    eax, eax
0x18044e938  js      loc_18044ECB2
0x18044e93e  lea     r8, aUrl_3; ".URL"
0x18044e945  mov     rdx, r13; unsigned __int64
0x18044e948  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x18044e94d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18044e952  mov     ebx, eax
0x18044e954  test    eax, eax
0x18044e956  js      loc_18044ECB2
0x18044e95c  lea     rcx, [rsp+4B0h+pszPathOut]; lpFileName
0x18044e961  call    cs:__imp_GetFileAttributesW
0x18044e968  nop     dword ptr [rax+rax+00h]
0x18044e96d  cmp     eax, 0FFFFFFFFh
0x18044e970  jnz     short loc_18044E9B3
0x18044e972  mov     rax, [rsi]
0x18044e975  lea     rdx, [rsp+4B0h+pszPathOut]
0x18044e97a  xor     r8d, r8d
0x18044e97d  mov     rcx, rsi
0x18044e980  mov     rax, [rax+30h]
0x18044e984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18044e989  mov     ebx, eax
0x18044e98b  test    eax, eax
0x18044e98d  js      loc_18044ECB2
0x18044e993  xor     r9d, r9d; dwItem2
0x18044e996  lea     r8, [rsp+4B0h+pszPathOut]; dwItem1
0x18044e99b  lea     edx, [r9+5]; uFlags
0x18044e99f  lea     ecx, [rdx-3]; wEventId
0x18044e9a2  call    cs:__imp_SHChangeNotify
0x18044e9a9  nop     dword ptr [rax+rax+00h]
0x18044e9ae  jmp     loc_18044EBE5
0x18044e9b3  lea     rax, [rsp+4B0h+var_480]
0x18044e9b8  mov     [rsp+4B0h+lpString1], 0
0x18044e9c1  lea     r9, _GUID_cabb0da0_da57_11cf_9974_0020afd79762; riid
0x18044e9c8  mov     qword ptr [rsp+4B0h+dwFlags], rax; LPVOID *
0x18044e9cd  mov     r8d, r12d; dwClsContext
0x18044e9d0  mov     [rsp+4B0h+var_480], 0
0x18044e9d9  xor     edx, edx; pUnkOuter
0x18044e9db  mov     [rsp+4B0h+var_478], 0
0x18044e9e4  lea     rcx, CLSID_InternetShortcut; rclsid
0x18044e9eb  call    IECreateInstance
0x18044e9f0  mov     ebx, eax
0x18044e9f2  test    eax, eax
0x18044e9f4  js      loc_18044ECB2
0x18044e9fa  mov     rcx, [rsp+4B0h+var_480]
0x18044e9ff  lea     r8, [rsp+4B0h+var_478]
0x18044ea04  lea     rdx, _GUID_0000010b_0000_0000_c000_000000000046
0x18044ea0b  mov     rax, [rcx]
0x18044ea0e  mov     rax, [rax]
0x18044ea11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18044ea16  mov     ebx, eax
0x18044ea18  test    eax, eax
0x18044ea1a  js      loc_18044EBCC
0x18044ea20  mov     rcx, [rsp+4B0h+var_478]
0x18044ea25  lea     rdx, [rsp+4B0h+pszPathOut]
0x18044ea2a  xor     r8d, r8d
0x18044ea2d  mov     rax, [rcx]
0x18044ea30  mov     rax, [rax+28h]
0x18044ea34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18044ea39  mov     ebx, eax
0x18044ea3b  test    eax, eax
0x18044ea3d  js      loc_18044EBBB
0x18044ea43  mov     rcx, [rsp+4B0h+var_480]
0x18044ea48  lea     rdx, [rsp+4B0h+lpString1]
0x18044ea4d  mov     rax, [rcx]
0x18044ea50  mov     rax, [rax+20h]
0x18044ea54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18044ea59  mov     ebx, eax
0x18044ea5b  test    eax, eax
0x18044ea5d  js      loc_18044EBBB
0x18044ea63  mov     rax, [rdi+28h]
0x18044ea67  or      r9d, 0FFFFFFFFh; cchCount1
0x18044ea6b  mov     r8, [rsp+4B0h+lpString1]; lpString1
0x18044ea70  mov     edx, r12d; dwCmpFlags
0x18044ea73  mov     [rsp+4B0h+cchCount2], r9d; cchCount2
0x18044ea78  mov     ecx, 7Fh; Locale
0x18044ea7d  mov     qword ptr [rsp+4B0h+dwFlags], rax; lpString2
0x18044ea82  call    cs:__imp_CompareStringW
0x18044ea89  nop     dword ptr [rax+rax+00h]
0x18044ea8e  cmp     eax, 2
0x18044ea91  jz      loc_18044EBAA
0x18044ea97  lea     rcx, [rsp+4B0h+pszPathOut]; pszPath
0x18044ea9c  call    cs:__imp_PathRemoveExtensionW
0x18044eaa3  nop     dword ptr [rax+rax+00h]
0x18044eaa8  mov     ecx, [rdi+8]
0x18044eaab  test    ecx, ecx
0x18044eaad  jz      short loc_18044EAE9
0x18044eaaf  sub     ecx, r12d
0x18044eab2  jz      short loc_18044EAE2
0x18044eab4  sub     ecx, r12d
0x18044eab7  jz      short loc_18044EADB
0x18044eab9  sub     ecx, r12d
0x18044eabc  jz      short loc_18044EAD4
0x18044eabe  cmp     ecx, r12d
0x18044eac1  jz      short loc_18044EACD
0x18044eac3  mov     ebx, 8000FFFFh
0x18044eac8  jmp     loc_18044EBAA
0x18044eacd  mov     edx, 473Ch
0x18044ead2  jmp     short loc_18044EAEE
0x18044ead4  mov     edx, 473Ah
0x18044ead9  jmp     short loc_18044EAEE
0x18044eadb  mov     edx, 4739h
0x18044eae0  jmp     short loc_18044EAEE
0x18044eae2  mov     edx, 4738h
0x18044eae7  jmp     short loc_18044EAEE
0x18044eae9  mov     edx, 473Bh; uID
0x18044eaee  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x18044eaf5  lea     r8, [rbp+3B0h+pszPath]; lpBuffer
0x18044eafc  mov     r9d, r13d; cchBufferMax
0x18044eaff  call    cs:__imp_LoadStringW
0x18044eb06  nop     dword ptr [rax+rax+00h]
0x18044eb0b  test    eax, eax
0x18044eb0d  jnz     short loc_18044EB16
0x18044eb0f  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18044eb14  mov     ebx, eax
0x18044eb16  test    ebx, ebx
0x18044eb18  js      loc_18044EBAA
0x18044eb1e  lea     r8, [rbp+3B0h+pszPath]; unsigned __int16 *
0x18044eb25  mov     rdx, r13; unsigned __int64
0x18044eb28  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x18044eb2d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18044eb32  mov     ebx, eax
0x18044eb34  test    eax, eax
0x18044eb36  js      short loc_18044EBAA
0x18044eb38  lea     r8, aUrl_3; ".URL"
0x18044eb3f  lea     rcx, [rsp+4B0h+pszPathOut]; pszPath
0x18044eb44  call    PathCchAddExtension
0x18044eb49  test    eax, eax
0x18044eb4b  js      short loc_18044EBAA
0x18044eb4d  xor     r9d, r9d; pszFileSpec
0x18044eb50  lea     rdx, [rsp+4B0h+pszPathOut]; pszPath
0x18044eb55  xor     r8d, r8d; pszShort
0x18044eb58  lea     rcx, [rsp+4B0h+pszPathOut]; pszUniqueName
0x18044eb5d  call    cs:__imp_PathYetAnotherMakeUniqueName
0x18044eb64  nop     dword ptr [rax+rax+00h]
0x18044eb69  test    eax, eax
0x18044eb6b  jz      short loc_18044EBA7
0x18044eb6d  mov     rax, [rsi]
0x18044eb70  lea     rdx, [rsp+4B0h+pszPathOut]
0x18044eb75  xor     r8d, r8d
0x18044eb78  mov     rcx, rsi
0x18044eb7b  mov     rax, [rax+30h]
0x18044eb7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18044eb84  mov     ebx, eax
0x18044eb86  test    eax, eax
0x18044eb88  js      short loc_18044EBAA
0x18044eb8a  xor     r9d, r9d; dwItem2
0x18044eb8d  lea     r8, [rsp+4B0h+pszPathOut]; dwItem1
0x18044eb92  lea     edx, [r9+5]; uFlags
0x18044eb96  lea     ecx, [rdx-3]; wEventId
0x18044eb99  call    cs:__imp_SHChangeNotify
0x18044eba0  nop     dword ptr [rax+rax+00h]
0x18044eba5  jmp     short loc_18044EBAA
0x18044eba7  mov     ebx, r12d
0x18044ebaa  mov     rcx, [rsp+4B0h+lpString1]; pv
0x18044ebaf  call    cs:__imp_CoTaskMemFree
0x18044ebb6  nop     dword ptr [rax+rax+00h]
0x18044ebbb  mov     rcx, [rsp+4B0h+var_478]
0x18044ebc0  mov     rax, [rcx]
0x18044ebc3  mov     rax, [rax+10h]
0x18044ebc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18044ebcc  mov     rcx, [rsp+4B0h+var_480]
0x18044ebd1  mov     rax, [rcx]
0x18044ebd4  mov     rax, [rax+10h]
0x18044ebd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18044ebdd  test    ebx, ebx
0x18044ebdf  js      loc_18044ECB2
0x18044ebe5  lea     rdx, [rsp+4B0h+var_480]
0x18044ebea  mov     dword ptr [rsp+4B0h+var_480], 0
0x18044ebf2  mov     ecx, 0Ch
0x18044ebf7  call    cs:__imp_IERegGetBool
0x18044ebfe  nop     dword ptr [rax+rax+00h]
0x18044ec03  cmp     qword ptr [rdi+38h], 0
0x18044ec08  jz      short loc_18044EC73
0x18044ec0a  cmp     dword ptr [rsp+4B0h+var_480], 0
0x18044ec0f  jnz     short loc_18044EC73
0x18044ec11  mov     r8, [rdi+28h]; unsigned __int16 *
0x18044ec15  lea     rdx, aFeedurl_0; "FeedUrl"
0x18044ec1c  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x18044ec21  xor     ebx, ebx
0x18044ec23  call    ?WriteMonitoredItemPropertyToFavorite@@YAJPEBG0PEAG@Z; WriteMonitoredItemPropertyToFavorite(ushort const *,ushort const *,ushort *)
0x18044ec28  mov     r8, [rdi+48h]; unsigned __int16 *
0x18044ec2c  test    r8, r8
0x18044ec2f  jz      short loc_18044EC5F
0x18044ec31  lea     rdx, aIslivepreview_0; "IsLivePreview"
0x18044ec38  mov     ebx, r12d
0x18044ec3b  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x18044ec40  call    ?WriteMonitoredItemPropertyToFavorite@@YAJPEBG0PEAG@Z; WriteMonitoredItemPropertyToFavorite(ushort const *,ushort const *,ushort *)
0x18044ec45  mov     r8, [rdi+40h]; unsigned __int16 *
0x18044ec49  test    r8, r8
0x18044ec4c  jz      short loc_18044EC5F
0x18044ec4e  lea     rdx, aPreviewsize; "PreviewSize"
0x18044ec55  lea     rcx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x18044ec5a  call    ?WriteMonitoredItemPropertyToFavorite@@YAJPEBG0PEAG@Z; WriteMonitoredItemPropertyToFavorite(ushort const *,ushort const *,ushort *)
0x18044ec5f  mov     rdx, [r14]
0x18044ec62  xor     r9d, r9d
0x18044ec65  mov     rcx, [rdi+38h]
0x18044ec69  mov     r8d, ebx
0x18044ec6c  call    EnsureSubscribedUrl
0x18044ec71  mov     ebx, eax
0x18044ec73  mov     rax, [rdi+50h]
0x18044ec77  test    rax, rax
0x18044ec7a  jz      short loc_18044ECB2
0x18044ec7c  mov     rcx, [rdi+28h]; unsigned __int16 *
0x18044ec80  lea     r8, [rsp+4B0h+var_478]; unsigned __int16 **
0x18044ec85  mov     r9d, r12d; unsigned int
0x18044ec88  mov     [rsp+4B0h+var_478], rax
0x18044ec8d  lea     rdx, [rsp+4B0h+pszPathOut]; unsigned __int16 *
0x18044ec92  call    ?UpdateFavoriteIcon@@YAJPEBG0PEAPEBGK@Z; UpdateFavoriteIcon(ushort const *,ushort const *,ushort const * *,ulong)
0x18044ec97  xor     r9d, r9d; dwItem2
0x18044ec9a  lea     r8, [rsp+4B0h+pszPathOut]; dwItem1
0x18044ec9f  lea     edx, [r9+5]; uFlags
0x18044eca3  lea     ecx, [rdx-3]; wEventId
0x18044eca6  call    cs:__imp_SHChangeNotify
0x18044ecad  nop     dword ptr [rax+rax+00h]
0x18044ecb2  mov     eax, ebx
0x18044ecb4  mov     rcx, [rbp+3B0h+var_40]
0x18044ecbb  xor     rcx, rsp; StackCookie
0x18044ecbe  call    __security_check_cookie
0x18044ecc3  add     rsp, 480h
0x18044ecca  pop     r14
0x18044eccc  pop     r13
0x18044ecce  pop     r12
0x18044ecd0  pop     rdi
0x18044ecd1  pop     rsi
0x18044ecd2  pop     rbx
0x18044ecd3  pop     rbp
0x18044ecd4  retn
```
