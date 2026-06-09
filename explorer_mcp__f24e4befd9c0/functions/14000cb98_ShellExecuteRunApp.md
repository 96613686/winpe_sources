# _ShellExecuteRunApp

- ea: `0x14000cb98`
- end: `0x14000d227`
- name: `_ShellExecuteRunApp`
- size: `1679`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszPath@<rcx>, LPCWCH lpWideCharStr@<rdx>, int, int, IUnknown *punk, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c9a8`
- `0x1401b2d10`

## callees

- `0x14000cb98`
- `0x14000d4e0`
- `0x140079b10`
- `0x14010e160`
- `0x14010e520`
- `0x14010ed90`
- `0x14010fca9`
- `0x1401d9010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000d09b`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000d09b`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x14000cf5f`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x14000cf5f`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000ccfb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000cd28`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000ccfb`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000cd28`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000ce30`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000d0b2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000d14a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000ce30`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000d0b2`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000d14a`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x14000ce1c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x14000d1fa`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x14000ce1c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x14000d1fa`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000cd4e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000cd4e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000d216`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000d216`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14000ced2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14000ced2`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x14000cd79`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x14000cda2`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x14000cd79`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x14000cda2`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000d0f4`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000d0f4`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x14000cbfa`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x14000cbfa`
- `USER32!DestroyMenu` at `0x14000d0d3`
- `USER32!DestroyMenu` at `0x14000d0d3`
- `USER32!GetMenuDefaultItem` at `0x14000ce7b`
- `USER32!GetMenuDefaultItem` at `0x14000ce7b`
- `USER32!CreatePopupMenu` at `0x14000cc92`
- `USER32!CreatePopupMenu` at `0x14000cc92`

## pseudocode

```c
__int64 __fastcall ShellExecuteRunApp(
        LPCWSTR pszPath,
        LPCWCH lpWideCharStr,
        const WCHAR *a3,
        int a4,
        int a5,
        int a6,
        IUnknown *punk,
        _QWORD *a8)
{
  HRESULT v12; // ebx
  HMENU v13; // r12
  CHAR *v14; // rsi
  __int64 v15; // rbx
  int v16; // edi
  unsigned int v17; // ecx
  unsigned int v18; // r14d
  CHAR *v19; // rax
  CHAR *v20; // rax
  CHAR *v21; // rbx
  char *v22; // rax
  void *v23; // rdi
  _QWORD *v24; // rcx
  UINT MenuDefaultItem; // eax
  HRESULT v26; // eax
  LPWSTR FileNameW; // rax
  _WORD *v28; // rcx
  unsigned int v29; // r8d
  unsigned int v30; // r15d
  int v31; // r10d
  __int64 v32; // rcx
  __int64 v33; // rdx
  _DWORD *v34; // r10
  unsigned int v35; // ecx
  __int64 v36; // rcx
  __int64 v38; // rdx
  int v39; // r11d
  int *v40; // r9
  _BYTE *v41; // r14
  _BYTE *v42; // rax
  _DWORD v43[2]; // [rsp+40h] [rbp-C0h] BYREF
  IUnknown *v44; // [rsp+48h] [rbp-B8h] BYREF
  int v45; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  void *ppv; // [rsp+60h] [rbp-A0h] BYREF
  LPCITEMIDLIST ppidlLast; // [rsp+68h] [rbp-98h] BYREF
  SFGAOF psfgaoOut; // [rsp+70h] [rbp-90h] BYREF
  int v50; // [rsp+78h] [rbp-88h] BYREF
  LPITEMIDLIST ppidl; // [rsp+80h] [rbp-80h] BYREF
  HMENU PopupMenu; // [rsp+88h] [rbp-78h]
  _DWORD v53[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h]
  __int64 v55; // [rsp+A0h] [rbp-60h]
  CHAR *v56; // [rsp+A8h] [rbp-58h]
  CHAR *v57; // [rsp+B0h] [rbp-50h]
  int v58; // [rsp+B8h] [rbp-48h]
  PCWSTR pwszSrc; // [rsp+D8h] [rbp-28h]
  LPCWCH lpWideCharStra; // [rsp+E0h] [rbp-20h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp+0h] BYREF
  int *v62; // [rsp+110h] [rbp+10h]
  __int64 v63; // [rsp+118h] [rbp+18h]
  LPCITEMIDLIST *p_ppidlLast; // [rsp+120h] [rbp+20h]
  __int64 v65; // [rsp+128h] [rbp+28h]
  int *v66; // [rsp+130h] [rbp+30h]
  __int64 v67; // [rsp+138h] [rbp+38h]
  int v68; // [rsp+2F0h] [rbp+1F0h] BYREF
  _BYTE v69[128]; // [rsp+2F4h] [rbp+1F4h] BYREF
  int v70; // [rsp+374h] [rbp+274h]
  BOOL v71; // [rsp+378h] [rbp+278h]
  __int64 v72; // [rsp+3F8h] [rbp+2F8h]

  ppidl = 0;
  psfgaoOut = 0;
  v12 = SHParseDisplayName(pszPath, 0, &ppidl, 0x70C58008u, &psfgaoOut);
  if ( v12 >= 0 )
  {
    v44 = 0;
    ppidlLast = 0;
    ppv = 0;
    v12 = SHBindToParent_0(ppidl, &GUID_000214e6_0000_0000_c000_000000000046, &ppv, &ppidlLast);
    if ( v12 >= 0 )
    {
      v12 = (*(__int64 (__fastcall **)(void *, _QWORD, __int64, LPCITEMIDLIST *, GUID *, _QWORD, IUnknown **))(*(_QWORD *)ppv + 80LL))(
              ppv,
              0,
              1,
              &ppidlLast,
              &GUID_000214e4_0000_0000_c000_000000000046,
              0,
              &v44);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    if ( v12 < 0 )
      goto LABEL_39;
    PopupMenu = CreatePopupMenu();
    v13 = PopupMenu;
    if ( !PopupMenu )
    {
LABEL_38:
      ((void (__fastcall *)(IUnknown *))v44->lpVtbl->Release)(v44);
LABEL_39:
      ILFree(ppidl);
      return (unsigned int)v12;
    }
    memset_0(v53, 0, 0x68u);
    lpWideCharStra = a3;
    v14 = 0;
    v53[0] = 104;
    v53[1] = 17664;
    v58 = a4;
    pwszSrc = lpWideCharStr;
    v54 = 0;
    v15 = (unsigned int)WideCharToMultiByte(0, 0, lpWideCharStr, -1, 0, 0, 0, 0);
    v16 = WideCharToMultiByte(0, 0, lpWideCharStra, -1, 0, 0, 0, 0);
    v17 = v16 + v15;
    if ( v16 + (int)v15 < (unsigned int)v15 )
    {
      v12 = -2147024362;
    }
    else
    {
      v18 = 64;
      if ( !v17 )
      {
LABEL_14:
        v22 = (char *)operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
        v23 = v22;
        if ( v22 )
        {
          CObjectWithSite::CObjectWithSite((CObjectWithSite *)(v22 + 16));
          *((_DWORD *)v23 + 8) = 1;
          *((_QWORD *)v23 + 1) = &CExecuteRunAppFilter::`vftable'{for `ICreatedProcess'};
          *(_QWORD *)v23 = &CExecuteRunAppFilter::`vftable'{for `IServiceProvider'};
          *v24 = &CExecuteRunAppFilter::`vftable'{for `CObjectWithSite'};
          *((_QWORD *)v23 + 5) = a8;
          if ( a8 )
            *a8 = 0;
          IUnknown_Set((IUnknown **)v23 + 3, punk);
          IUnknown_SetSite(v44, (IUnknown *)v23);
        }
        else
        {
          IUnknown_SetSite(v44, punk);
          v23 = 0;
        }
        v12 = ((__int64 (__fastcall *)(IUnknown *, HMENU, _QWORD, __int64, int, int))v44->lpVtbl[1].QueryInterface)(
                v44,
                v13,
                0,
                1,
                0x7FFF,
                1);
        if ( v12 >= 0 )
        {
          MenuDefaultItem = GetMenuDefaultItem(v13, 0, 0);
          if ( MenuDefaultItem )
          {
            v55 = (unsigned __int16)(MenuDefaultItem - 1);
            v26 = ((__int64 (__fastcall *)(IUnknown *, _DWORD *))v44->lpVtbl[1].AddRef)(v44, v53);
            v68 = 0;
            v12 = v26;
            memset_0(v69, 0, 0x188u);
            FileNameW = PathFindFileNameW(pszPath);
            if ( !FileNameW || !*FileNameW )
              FileNameW = L"(null)";
            v28 = v69;
            do
            {
              if ( !*FileNameW )
                break;
              *v28++ = *FileNameW++;
              --v18;
            }
            while ( v18 > 1 );
            *v28 = 0;
            v68 = 2;
            v70 = 1;
            v72 = 1;
            v71 = v12 == -2147024156;
            v45 = 3;
            v50 = 1869;
            if ( EventEnabled(Microsoft_Windows_Shell_Core_Provider_Context, &ShellTraceId_Explorer_StartupAppName_Info) )
            {
              memset_0(&UserData.Size, 0, 0x1E8u);
              v29 = 0;
              v30 = v45;
              v43[0] = *(_DWORD *)L"0";
              UserData.Ptr = (ULONGLONG)&g_SHSqmGlobalSession;
              v62 = &v50;
              p_ppidlLast = &ppidlLast;
              v66 = &v45;
              LODWORD(ppidlLast) = 11;
              LODWORD(ppv) = 0;
              v46 = 0;
              *(_QWORD *)&UserData.Size = 16;
              v63 = 4;
              v65 = 4;
              v67 = 4;
              do
              {
                v31 = 3 * v29;
                *((_QWORD *)&UserData + 6 * v29 + 9) = 4;
                if ( v29 < v30 )
                {
                  v38 = 132LL * v29;
                  *(&UserData.Ptr + 2 * (unsigned int)(v31 + 4)) = (ULONGLONG)&v69[v38 - 4];
                  v39 = *(_DWORD *)&v69[v38 - 4];
                  if ( v39 == 1 )
                    v40 = (int *)&v69[v38];
                  else
                    v40 = &v46;
                  v41 = &v69[v38];
                  v42 = v43;
                  if ( v39 == 2 )
                    v42 = &v69[v38];
                  v33 = -1;
                  *(&UserData.Ptr + 2 * (unsigned int)(v31 + 5)) = (ULONGLONG)v40;
                  *((_QWORD *)&UserData.Size + 2 * (unsigned int)(v31 + 5)) = 4;
                  do
                    ++v33;
                  while ( *(_WORD *)&v42[2 * v33] );
                  v34 = v43;
                  if ( v39 == 2 )
                    v34 = v41;
                }
                else
                {
                  *(&UserData.Ptr + 2 * (unsigned int)(v31 + 4)) = (ULONGLONG)&ppv;
                  v32 = 2LL * (unsigned int)(v31 + 5);
                  v33 = -1;
                  *(&UserData.Ptr + v32) = (ULONGLONG)&v46;
                  *((_QWORD *)&UserData.Size + v32) = 4;
                  do
                    ++v33;
                  while ( *((_WORD *)v43 + v33) );
                  v34 = v43;
                }
                v35 = v29++;
                v36 = 2LL * (2 * v35 + 6 + v35);
                *(&UserData.Ptr + v36) = (ULONGLONG)v34;
                *(&UserData.Size + 2 * v36) = 2 * v33 + 2;
                *(&UserData.Reserved + 2 * v36) = 0;
              }
              while ( v29 < 9 );
              EventWrite(
                Microsoft_Windows_Shell_Core_Provider_Context,
                &ShellTraceId_Explorer_StartupAppName_Info,
                0x1Fu,
                &UserData);
              v13 = PopupMenu;
            }
          }
          else
          {
            v12 = -2147418113;
          }
        }
        IUnknown_SetSite(v44, 0);
        if ( v23 )
        {
          IUnknown_Set((IUnknown **)v23 + 3, 0);
          CExecuteRunAppFilter::Release((CExecuteRunAppFilter *)v23);
        }
        if ( v14 )
          LocalFree(v14);
        goto LABEL_37;
      }
      v19 = (CHAR *)LocalAlloc(0x40u, v17);
      v14 = v19;
      if ( v19 )
      {
        if ( pwszSrc )
        {
          SHUnicodeToAnsi(pwszSrc, v19, v15);
          v20 = v14;
        }
        else
        {
          v20 = 0;
        }
        v56 = v20;
        if ( lpWideCharStra )
        {
          v21 = &v14[v15];
          SHUnicodeToAnsi(lpWideCharStra, v21, v16);
        }
        else
        {
          v21 = 0;
        }
        v57 = v21;
        goto LABEL_14;
      }
      v12 = -2147024882;
    }
LABEL_37:
    DestroyMenu(v13);
    goto LABEL_38;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14000cb98  push    rbp
0x14000cb9a  push    rbx
0x14000cb9b  push    rsi
0x14000cb9c  push    rdi
0x14000cb9d  push    r12
0x14000cb9f  push    r13
0x14000cba1  push    r14
0x14000cba3  push    r15
0x14000cba5  lea     rbp, [rsp-398h]
0x14000cbad  sub     rsp, 498h
0x14000cbb4  mov     rax, cs:__security_cookie
0x14000cbbb  xor     rax, rsp
0x14000cbbe  mov     [rbp+3D0h+var_50], rax
0x14000cbc5  mov     r15, [rbp+3D0h+punk]
0x14000cbcc  lea     rax, [rsp+4D0h+var_460]
0x14000cbd1  mov     r14d, r9d
0x14000cbd4  mov     [rsp+4D0h+psfgaoOut], rax; psfgaoOut
0x14000cbd9  mov     rsi, r8
0x14000cbdc  mov     rdi, rdx
0x14000cbdf  xor     r12d, r12d
0x14000cbe2  lea     r8, [rbp+3D0h+ppidl]; ppidl
0x14000cbe6  mov     r9d, 70C58008h; sfgaoIn
0x14000cbec  mov     [rbp+3D0h+ppidl], r12
0x14000cbf0  xor     edx, edx; pbc
0x14000cbf2  mov     [rsp+4D0h+var_460], r12d
0x14000cbf7  mov     r13, rcx
0x14000cbfa  call    cs:__imp_SHParseDisplayName
0x14000cc01  nop     dword ptr [rax+rax+00h]
0x14000cc06  mov     ebx, eax
0x14000cc08  test    eax, eax
0x14000cc0a  js      loc_14000D100
0x14000cc10  mov     rcx, [rbp+3D0h+ppidl]; pidl
0x14000cc14  lea     r9, [rsp+4D0h+ppidlLast]; ppidlLast
0x14000cc19  lea     r8, [rsp+4D0h+ppv]; ppv
0x14000cc1e  mov     [rsp+4D0h+var_488], r12
0x14000cc23  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x14000cc2a  mov     [rsp+4D0h+ppidlLast], r12
0x14000cc2f  mov     [rsp+4D0h+ppv], r12
0x14000cc34  call    SHBindToParent_0
0x14000cc39  mov     ebx, eax
0x14000cc3b  test    eax, eax
0x14000cc3d  js      short loc_14000CC8A
0x14000cc3f  mov     rcx, [rsp+4D0h+ppv]
0x14000cc44  lea     rdx, [rsp+4D0h+var_488]
0x14000cc49  mov     [rsp+4D0h+lpDefaultChar], rdx
0x14000cc4e  lea     r9, [rsp+4D0h+ppidlLast]
0x14000cc53  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x14000cc5a  mov     qword ptr [rsp+4D0h+cbMultiByte], r12
0x14000cc5f  mov     [rsp+4D0h+psfgaoOut], rdx
0x14000cc64  lea     r8d, [r12+1]
0x14000cc69  mov     rax, [rcx]
0x14000cc6c  xor     edx, edx
0x14000cc6e  mov     rax, [rax+50h]
0x14000cc72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc77  mov     rcx, [rsp+4D0h+ppv]
0x14000cc7c  mov     ebx, eax
0x14000cc7e  mov     rax, [rcx]
0x14000cc81  mov     rax, [rax+10h]
0x14000cc85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc8a  test    ebx, ebx
0x14000cc8c  js      loc_14000D0F0
0x14000cc92  call    cs:__imp_CreatePopupMenu
0x14000cc99  nop     dword ptr [rax+rax+00h]
0x14000cc9e  mov     [rbp+3D0h+var_448], rax
0x14000cca2  mov     r12, rax
0x14000cca5  test    rax, rax
0x14000cca8  jz      loc_14000D0DF
0x14000ccae  mov     ebx, 68h ; 'h'
0x14000ccb3  lea     rcx, [rbp+3D0h+var_440]; void *
0x14000ccb7  mov     r8d, ebx; Size
0x14000ccba  xor     edx, edx; Val
0x14000ccbc  call    memset_0
0x14000ccc1  mov     [rbp+3D0h+lpWideCharStr], rsi
0x14000ccc5  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000ccc9  xor     esi, esi
0x14000cccb  mov     [rbp+3D0h+var_440], ebx
0x14000ccce  mov     [rsp+4D0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x14000ccd3  mov     r8, rdi; lpWideCharStr
0x14000ccd6  mov     [rsp+4D0h+lpDefaultChar], rsi; lpDefaultChar
0x14000ccdb  xor     edx, edx; dwFlags
0x14000ccdd  mov     [rsp+4D0h+cbMultiByte], esi; cbMultiByte
0x14000cce1  xor     ecx, ecx; CodePage
0x14000cce3  mov     [rsp+4D0h+psfgaoOut], rsi; lpMultiByteStr
0x14000cce8  mov     [rbp+3D0h+var_43C], 4500h
0x14000ccef  mov     [rbp+3D0h+var_418], r14d
0x14000ccf3  mov     [rbp+3D0h+pwszSrc], rdi
0x14000ccf7  mov     [rbp+3D0h+var_438], rsi
0x14000ccfb  call    cs:__imp_WideCharToMultiByte
0x14000cd02  nop     dword ptr [rax+rax+00h]
0x14000cd07  mov     r8, [rbp+3D0h+lpWideCharStr]; lpWideCharStr
0x14000cd0b  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000cd0f  mov     [rsp+4D0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x14000cd14  xor     edx, edx; dwFlags
0x14000cd16  mov     [rsp+4D0h+lpDefaultChar], rsi; lpDefaultChar
0x14000cd1b  xor     ecx, ecx; CodePage
0x14000cd1d  mov     [rsp+4D0h+cbMultiByte], esi; cbMultiByte
0x14000cd21  mov     [rsp+4D0h+psfgaoOut], rsi; lpMultiByteStr
0x14000cd26  mov     ebx, eax
0x14000cd28  call    cs:__imp_WideCharToMultiByte
0x14000cd2f  nop     dword ptr [rax+rax+00h]
0x14000cd34  mov     edi, eax
0x14000cd36  lea     ecx, [rax+rbx]
0x14000cd39  cmp     ecx, ebx
0x14000cd3b  jb      loc_14000D12D
0x14000cd41  lea     r14d, [rsi+40h]
0x14000cd45  test    ecx, ecx
0x14000cd47  jz      short loc_14000CDB2
0x14000cd49  mov     edx, ecx; uBytes
0x14000cd4b  mov     ecx, r14d; uFlags
0x14000cd4e  call    cs:__imp_LocalAlloc
0x14000cd55  nop     dword ptr [rax+rax+00h]
0x14000cd5a  mov     rsi, rax
0x14000cd5d  test    rax, rax
0x14000cd60  jz      loc_14000D126
0x14000cd66  mov     rcx, [rbp+3D0h+pwszSrc]; pwszSrc
0x14000cd6a  test    rcx, rcx
0x14000cd6d  jz      loc_14000D134
0x14000cd73  mov     r8d, ebx; cchBuf
0x14000cd76  mov     rdx, rax; pszDst
0x14000cd79  call    cs:__imp_SHUnicodeToAnsi
0x14000cd80  nop     dword ptr [rax+rax+00h]
0x14000cd85  mov     rax, rsi
0x14000cd88  mov     rcx, [rbp+3D0h+lpWideCharStr]; pwszSrc
0x14000cd8c  mov     [rbp+3D0h+var_428], rax
0x14000cd90  test    rcx, rcx
0x14000cd93  jz      loc_14000D13B
0x14000cd99  add     rbx, rsi
0x14000cd9c  mov     r8d, edi; cchBuf
0x14000cd9f  mov     rdx, rbx; pszDst
0x14000cda2  call    cs:__imp_SHUnicodeToAnsi
0x14000cda9  nop     dword ptr [rax+rax+00h]
0x14000cdae  mov     [rbp+3D0h+var_420], rbx
0x14000cdb2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000cdb9  mov     ecx, 30h ; '0'; unsigned __int64
0x14000cdbe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000cdc3  mov     rdi, rax
0x14000cdc6  test    rax, rax
0x14000cdc9  jz      loc_14000D142
0x14000cdcf  lea     rcx, [rax+10h]; this
0x14000cdd3  call    ??0CObjectWithSite@@QEAA@XZ; CObjectWithSite::CObjectWithSite(void)
0x14000cdd8  lea     rax, ??_7CExecuteRunAppFilter@@6BICreatedProcess@@@; const CExecuteRunAppFilter::`vftable'{for `ICreatedProcess'}
0x14000cddf  mov     dword ptr [rdi+20h], 1
0x14000cde6  mov     [rdi+8], rax
0x14000cdea  lea     rdx, ??_7CExecuteRunAppFilter@@6BIServiceProvider@@@; const CExecuteRunAppFilter::`vftable'{for `IServiceProvider'}
0x14000cdf1  lea     rax, ??_7CExecuteRunAppFilter@@6BCObjectWithSite@@@; const CExecuteRunAppFilter::`vftable'{for `CObjectWithSite'}
0x14000cdf8  mov     [rdi], rdx
0x14000cdfb  mov     [rcx], rax
0x14000cdfe  mov     rax, [rbp+3D0h+arg_38]
0x14000ce05  mov     [rdi+28h], rax
0x14000ce09  test    rax, rax
0x14000ce0c  jz      short loc_14000CE15
0x14000ce0e  mov     qword ptr [rax], 0
0x14000ce15  lea     rcx, [rdi+18h]; ppunk
0x14000ce19  mov     rdx, r15; punk
0x14000ce1c  call    cs:__imp_IUnknown_Set
0x14000ce23  nop     dword ptr [rax+rax+00h]
0x14000ce28  mov     rcx, [rsp+4D0h+var_488]; punk
0x14000ce2d  mov     rdx, rdi; punkSite
0x14000ce30  call    cs:__imp_IUnknown_SetSite
0x14000ce37  nop     dword ptr [rax+rax+00h]
0x14000ce3c  mov     rcx, [rsp+4D0h+var_488]
0x14000ce41  mov     r15d, 1
0x14000ce47  mov     [rsp+4D0h+cbMultiByte], r15d
0x14000ce4c  mov     r9d, r15d
0x14000ce4f  xor     r8d, r8d
0x14000ce52  mov     dword ptr [rsp+4D0h+psfgaoOut], 7FFFh
0x14000ce5a  mov     rdx, r12
0x14000ce5d  mov     rax, [rcx]
0x14000ce60  mov     rax, [rax+18h]
0x14000ce64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce69  mov     ebx, eax
0x14000ce6b  test    eax, eax
0x14000ce6d  js      loc_14000D0AB
0x14000ce73  xor     r8d, r8d; gmdiFlags
0x14000ce76  xor     edx, edx; fByPos
0x14000ce78  mov     rcx, r12; hMenu
0x14000ce7b  call    cs:__imp_GetMenuDefaultItem
0x14000ce82  nop     dword ptr [rax+rax+00h]
0x14000ce87  test    eax, eax
0x14000ce89  jz      loc_14000D1EA
0x14000ce8f  mov     rcx, [rsp+4D0h+var_488]
0x14000ce94  lea     rdx, [rbp+3D0h+var_440]
0x14000ce98  sub     ax, r15w
0x14000ce9c  movzx   eax, ax
0x14000ce9f  mov     [rbp+3D0h+var_430], rax
0x14000cea3  mov     rax, [rcx]
0x14000cea6  mov     rax, [rax+20h]
0x14000ceaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ceaf  xor     edx, edx; Val
0x14000ceb1  mov     [rbp+3D0h+var_1E0], 0
0x14000cebb  mov     r8d, 188h; Size
0x14000cec1  lea     rcx, [rbp+3D0h+var_1DC]; void *
0x14000cec8  mov     ebx, eax
0x14000ceca  call    memset_0
0x14000cecf  mov     rcx, r13; pszPath
0x14000ced2  call    cs:__imp_PathFindFileNameW
0x14000ced9  nop     dword ptr [rax+rax+00h]
0x14000cede  xor     r13d, r13d
0x14000cee1  test    rax, rax
0x14000cee4  jnz     loc_14000D1DB
0x14000ceea  lea     rax, aNull; "(null)"
0x14000cef1  lea     rcx, [rbp+3D0h+var_1DC]
0x14000cef8  movzx   edx, word ptr [rax]
0x14000cefb  test    dx, dx
0x14000cefe  jz      short loc_14000CF13
0x14000cf00  mov     [rcx], dx
0x14000cf03  add     rax, 2
0x14000cf07  add     rcx, 2
0x14000cf0b  dec     r14d
0x14000cf0e  cmp     r14d, r15d
0x14000cf11  ja      short loc_14000CEF8
0x14000cf13  mov     [rcx], r13w
0x14000cf17  lea     rdx, ShellTraceId_Explorer_StartupAppName_Info; EventDescriptor
0x14000cf1e  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x14000cf25  mov     eax, r13d
0x14000cf28  cmp     ebx, 800702E4h
0x14000cf2e  mov     [rbp+3D0h+var_1E0], 2
0x14000cf38  mov     [rbp+3D0h+var_15C], r15d
0x14000cf3f  setz    al
0x14000cf42  mov     [rbp+3D0h+var_D8], r15
0x14000cf49  mov     [rbp+3D0h+var_158], eax
0x14000cf4f  mov     [rsp+4D0h+var_480], 3
0x14000cf57  mov     [rsp+4D0h+var_458], 74Dh
0x14000cf5f  call    cs:__imp_EventEnabled
0x14000cf66  nop     dword ptr [rax+rax+00h]
0x14000cf6b  test    al, al
0x14000cf6d  jz      loc_14000D0AB
0x14000cf73  xor     edx, edx; Val
0x14000cf75  lea     rcx, [rbp+3D0h+UserData.Size]; void *
0x14000cf79  mov     r8d, 1E8h; Size
0x14000cf7f  call    memset_0
0x14000cf84  mov     eax, dword ptr cs:a0; "0"
0x14000cf8a  mov     r8d, r13d
0x14000cf8d  mov     r15d, [rsp+4D0h+var_480]
0x14000cf92  mov     r12d, 1
0x14000cf98  mov     [rsp+4D0h+var_490], eax
0x14000cf9c  lea     rax, ?g_SHSqmGlobalSession@@3U_GUID@@B; _GUID const g_SHSqmGlobalSession
0x14000cfa3  mov     [rbp+3D0h+UserData.Ptr], rax
0x14000cfa7  lea     rax, [rsp+4D0h+var_458]
0x14000cfac  mov     [rbp+3D0h+var_3C0], rax
0x14000cfb0  lea     rax, [rsp+4D0h+ppidlLast]
0x14000cfb5  mov     [rbp+3D0h+var_3B0], rax
0x14000cfb9  lea     rax, [rsp+4D0h+var_480]
0x14000cfbe  mov     [rbp+3D0h+var_3A0], rax
0x14000cfc2  mov     dword ptr [rsp+4D0h+ppidlLast], 0Bh
0x14000cfca  mov     dword ptr [rsp+4D0h+ppv], r13d
0x14000cfcf  mov     [rsp+4D0h+var_478], r13d
0x14000cfd4  mov     qword ptr [rbp+3D0h+UserData.Size], 10h
0x14000cfdc  mov     [rbp+3D0h+var_3B8], 4
0x14000cfe4  mov     [rbp+3D0h+var_3A8], 4
0x14000cfec  mov     [rbp+3D0h+var_398], 4
0x14000cff4  lea     r10d, [r8+r8*2]
0x14000cff8  lea     ecx, [r10+4]
0x14000cffc  add     rcx, rcx
0x14000cfff  mov     qword ptr [rbp+rcx*8+3D0h+UserData.Size], 4
0x14000d008  cmp     r8d, r15d
0x14000d00b  jb      loc_14000D15D
0x14000d011  lea     rax, [rsp+4D0h+ppv]
0x14000d016  mov     [rbp+rcx*8+3D0h+UserData.Ptr], rax
0x14000d01b  lea     rax, [rsp+4D0h+var_478]
0x14000d020  lea     ecx, [r10+5]
0x14000d024  add     rcx, rcx
0x14000d027  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000d02b  mov     [rbp+rcx*8+3D0h+UserData.Ptr], rax
0x14000d030  lea     rax, [rsp+4D0h+var_490]
0x14000d035  mov     qword ptr [rbp+rcx*8+3D0h+UserData.Size], 4
0x14000d03e  inc     rdx
0x14000d041  cmp     [rax+rdx*2], r13w
0x14000d046  jnz     short loc_14000D03E
0x14000d048  lea     r10, [rsp+4D0h+var_490]
0x14000d04d  mov     ecx, r8d
0x14000d050  lea     r9, [rbp+3D0h+UserData]
0x14000d054  mov     eax, 6
0x14000d059  add     r8d, r12d
0x14000d05c  lea     eax, [rax+rcx*2]
0x14000d05f  add     ecx, eax
0x14000d061  lea     eax, ds:2[rdx*2]
0x14000d068  add     rcx, rcx
0x14000d06b  mov     [r9+rcx*8], r10
0x14000d06f  mov     [r9+rcx*8+8], eax
0x14000d074  mov     [r9+rcx*8+0Ch], r13d
0x14000d079  cmp     r8d, 9
0x14000d07d  jb      loc_14000CFF4
0x14000d083  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x14000d08a  lea     r9, [rbp+3D0h+UserData]; UserData
0x14000d08e  mov     r8d, 1Fh; UserDataCount
0x14000d094  lea     rdx, ShellTraceId_Explorer_StartupAppName_Info; EventDescriptor
0x14000d09b  call    cs:__imp_EventWrite
0x14000d0a2  nop     dword ptr [rax+rax+00h]
0x14000d0a7  mov     r12, [rbp+3D0h+var_448]
0x14000d0ab  mov     rcx, [rsp+4D0h+var_488]; punk
0x14000d0b0  xor     edx, edx; punkSite
0x14000d0b2  call    cs:__imp_IUnknown_SetSite
0x14000d0b9  nop     dword ptr [rax+rax+00h]
0x14000d0be  test    rdi, rdi
0x14000d0c1  jnz     loc_14000D1F4
0x14000d0c7  test    rsi, rsi
0x14000d0ca  jnz     loc_14000D213
0x14000d0d0  mov     rcx, r12; hMenu
0x14000d0d3  call    cs:__imp_DestroyMenu
  ... truncated ...
```
