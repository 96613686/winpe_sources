# ShowDownloadDialog(HWND__ *,ushort *,ulong)

- ea: `0x18000eb7c`
- end: `0x18000ed5d`
- name: `?ShowDownloadDialog@@YAJPEAUHWND__@@PEAGK@Z`
- size: `481`
- prototype: `__int64 __fastcall(HWND, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f9f4`

## callees

- `0x180002240`
- `0x18000ea20`
- `0x18000eb7c`
- `0x1800271f0`
- `0x180028010`

## import_xrefs

- `SHELL32!SHBrowseForFolderW` at `0x18000ec8f`
- `SHELL32!SHBrowseForFolderW` at `0x18000ec8f`
- `SHELL32!__imp_ILSaveToStream` at `0x18000ecdf`
- `SHELL32!__imp_ILSaveToStream` at `0x18000ecdf`
- `SHELL32!__imp_ILFree` at `0x18000ed20`
- `SHELL32!__imp_ILFree` at `0x18000ed2e`
- `SHELL32!__imp_ILFree` at `0x18000ed20`
- `SHELL32!__imp_ILFree` at `0x18000ed2e`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x18000ec22`
- `SHELL32!__imp_ILLoadFromStreamEx` at `0x18000ec22`
- `SHLWAPI!SHOpenRegStream2W` at `0x18000ec0c`
- `SHLWAPI!SHOpenRegStream2W` at `0x18000ec0c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ec3e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18000ec3e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed10`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ed10`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ebeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ebeb`

## string_xrefs

- `0x18000ebfe`: `Download Directory`

## pseudocode

```c
__int64 __fastcall ShowDownloadDialog(HWND a1, unsigned __int16 *a2)
{
  IStream *v4; // rdi
  IStream *v5; // rax
  LPITEMIDLIST v6; // rax
  unsigned int v7; // edx
  unsigned int v8; // r9d
  ITEMIDLIST *v9; // rbx
  unsigned int v10; // esi
  __int64 v11; // rax
  unsigned int *phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+30h] [rbp-D0h] BYREF
  LPITEMIDLIST pidl; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v16[2]; // [rsp+40h] [rbp-C0h] BYREF
  _browseinfoW bi; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[2088]; // [rsp+90h] [rbp-70h] BYREF

  pidl = 0;
  hkey = 0;
  v4 = 0;
  if ( !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft", 0, 0x2001Fu, &hkey) )
  {
    v5 = SHOpenRegStream2W(hkey, L"ftp", L"Download Directory", 2u);
    v4 = v5;
    if ( v5 )
      ILLoadFromStreamEx(v5, &pidl);
  }
  LoadStringW(g_hinst, 0x1F4u, Buffer, 2084);
  bi.pidlRoot = 0;
  bi.lpszTitle = Buffer;
  bi.pszDisplayName = 0;
  bi.lpfn = (BFFCALLBACK)BrowseCallback;
  bi.lParam = (LPARAM)pidl;
  *(_QWORD *)&bi.ulFlags = 121;
  *(_QWORD *)&bi.iImage = 0;
  bi.hwndOwner = a1;
  v6 = SHBrowseForFolderW(&bi);
  v9 = v6;
  v10 = v6 == 0;
  if ( v4 )
  {
    if ( v6 )
    {
      v11 = *(_QWORD *)v4;
      v16[1] = 0;
      v16[0] = 0;
      (*(void (__fastcall **)(IStream *, _QWORD, _QWORD, _QWORD *))(v11 + 40))(v4, 0, 0, v16);
      ILSaveToStream(v4, v9);
    }
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v4 + 16LL))(v4);
  }
  if ( v9 )
    v10 = SHGetNameAndFlagsW(v9, v7, a2, v8, phkResult);
  if ( hkey )
    RegCloseKey(hkey);
  if ( pidl )
    ILFree(pidl);
  if ( v9 )
    ILFree(v9);
  return v10;
}

```

## disassembly

```asm
0x18000eb7c  mov     [rsp-8+arg_10], rbx
0x18000eb81  mov     [rsp-8+arg_18], rsi
0x18000eb86  push    rbp
0x18000eb87  push    rdi
0x18000eb88  push    r14
0x18000eb8a  lea     rbp, [rsp-0FF0h]
0x18000eb92  mov     eax, 10F0h
0x18000eb97  call    _alloca_probe
0x18000eb9c  sub     rsp, rax
0x18000eb9f  mov     rax, cs:__security_cookie
0x18000eba6  xor     rax, rsp
0x18000eba9  mov     [rbp+1000h+var_20], rax
0x18000ebb0  mov     r14, rdx
0x18000ebb3  mov     [rsp+1100h+pidl], 0
0x18000ebbc  mov     rbx, rcx
0x18000ebbf  mov     [rsp+1100h+hkey], 0
0x18000ebc8  lea     rax, [rsp+1100h+hkey]
0x18000ebcd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000ebd4  lea     rdx, SubKey; "Software\\Microsoft"
0x18000ebdb  mov     [rsp+1100h+phkResult], rax; unsigned int *
0x18000ebe0  mov     r9d, 2001Fh; samDesired
0x18000ebe6  xor     r8d, r8d; ulOptions
0x18000ebe9  xor     edi, edi
0x18000ebeb  call    cs:__imp_RegOpenKeyExW
0x18000ebf1  test    eax, eax
0x18000ebf3  jnz     short loc_18000EC28
0x18000ebf5  mov     rcx, [rsp+1100h+hkey]; hkey
0x18000ebfa  lea     r9d, [rdi+2]; grfMode
0x18000ebfe  lea     r8, aDownloadDirect; "Download Directory"
0x18000ec05  lea     rdx, pszSubkey; "ftp"
0x18000ec0c  call    cs:__imp_SHOpenRegStream2W
0x18000ec12  mov     rdi, rax
0x18000ec15  test    rax, rax
0x18000ec18  jz      short loc_18000EC28
0x18000ec1a  lea     rdx, [rsp+1100h+pidl]; pidl
0x18000ec1f  mov     rcx, rax; pstm
0x18000ec22  call    cs:__imp_ILLoadFromStreamEx
0x18000ec28  mov     rcx, cs:?g_hinst@@3PEAUHINSTANCE__@@EA; hInstance
0x18000ec2f  lea     r8, [rbp+1000h+Buffer]; lpBuffer
0x18000ec33  mov     r9d, 824h; cchBufferMax
0x18000ec39  mov     edx, 1F4h; uID
0x18000ec3e  call    cs:__imp_LoadStringW
0x18000ec44  lea     rax, [rbp+1000h+Buffer]
0x18000ec48  mov     [rsp+1100h+bi.pidlRoot], 0
0x18000ec51  mov     [rsp+1100h+bi.lpszTitle], rax
0x18000ec56  lea     rcx, [rsp+1100h+bi]; lpbi
0x18000ec5b  lea     rax, ?BrowseCallback@@YAHPEAUHWND__@@I_J1@Z; BrowseCallback(HWND__ *,uint,__int64,__int64)
0x18000ec62  mov     [rsp+1100h+bi.pszDisplayName], 0
0x18000ec6b  mov     [rsp+1100h+bi.lpfn], rax
0x18000ec70  mov     rax, [rsp+1100h+pidl]
0x18000ec75  mov     [rbp+1000h+bi.lParam], rax
0x18000ec79  mov     qword ptr [rsp+1100h+bi.ulFlags], 79h ; 'y'
0x18000ec82  mov     qword ptr [rbp+1000h+bi.iImage], 0
0x18000ec8a  mov     [rsp+1100h+bi.hwndOwner], rbx
0x18000ec8f  call    cs:__imp_SHBrowseForFolderW
0x18000ec95  xor     esi, esi
0x18000ec97  mov     rbx, rax
0x18000ec9a  test    rax, rax
0x18000ec9d  setz    sil
0x18000eca1  test    rdi, rdi
0x18000eca4  jz      short loc_18000ECF4
0x18000eca6  test    rax, rax
0x18000eca9  jz      short loc_18000ECE5
0x18000ecab  mov     rax, [rdi]
0x18000ecae  lea     r9, [rsp+1100h+var_10C0]
0x18000ecb3  mov     [rsp+1100h+var_10B8], 0
0x18000ecbc  xor     r8d, r8d
0x18000ecbf  mov     rdx, [rsp+1100h+var_10B8]
0x18000ecc4  mov     rcx, rdi
0x18000ecc7  mov     [rsp+1100h+var_10C0], 0
0x18000ecd0  mov     rax, [rax+28h]
0x18000ecd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd9  mov     rdx, rbx; pidl
0x18000ecdc  mov     rcx, rdi; pstm
0x18000ecdf  call    cs:__imp_ILSaveToStream
0x18000ece5  mov     rax, [rdi]
0x18000ece8  mov     rcx, rdi
0x18000eceb  mov     rax, [rax+10h]
0x18000ecef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecf4  test    rbx, rbx
0x18000ecf7  jz      short loc_18000ED06
0x18000ecf9  mov     r8, r14; unsigned __int16 *
0x18000ecfc  mov     rcx, rbx; pidl
0x18000ecff  call    ?SHGetNameAndFlagsW@@YAJPEFBU_ITEMIDLIST@@KPEAGIPEAK@Z; SHGetNameAndFlagsW(_ITEMIDLIST const *,ulong,ushort *,uint,ulong *)
0x18000ed04  mov     esi, eax
0x18000ed06  mov     rcx, [rsp+1100h+hkey]; hKey
0x18000ed0b  test    rcx, rcx
0x18000ed0e  jz      short loc_18000ED16
0x18000ed10  call    cs:__imp_RegCloseKey
0x18000ed16  mov     rcx, [rsp+1100h+pidl]; pidl
0x18000ed1b  test    rcx, rcx
0x18000ed1e  jz      short loc_18000ED26
0x18000ed20  call    cs:__imp_ILFree
0x18000ed26  test    rbx, rbx
0x18000ed29  jz      short loc_18000ED34
0x18000ed2b  mov     rcx, rbx; pidl
0x18000ed2e  call    cs:__imp_ILFree
0x18000ed34  mov     eax, esi
0x18000ed36  mov     rcx, [rbp+1000h+var_20]
0x18000ed3d  xor     rcx, rsp; StackCookie
0x18000ed40  call    __security_check_cookie
0x18000ed45  lea     r11, [rsp+1100h+var_10]
0x18000ed4d  mov     rbx, [r11+30h]
0x18000ed51  mov     rsi, [r11+38h]
0x18000ed55  mov     rsp, r11
0x18000ed58  pop     r14
0x18000ed5a  pop     rdi
0x18000ed5b  pop     rbp
0x18000ed5c  retn
```
