# _ShellExecuteRunApp

- ea: `0x14000bd80`
- end: `0x14000c39c`
- name: `_ShellExecuteRunApp`
- size: `1564`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszPath@<rcx>, LPCWCH lpWideCharStr@<rdx>, int, int, IUnknown *punk, __int64)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x14000bbc4`
- `0x1401b4aac`

## callees

- `0x14000bd80`
- `0x14000c600`
- `0x140075130`
- `0x1401040e0`
- `0x1401044a0`
- `0x140104ce0`
- `0x140105c4d`
- `0x1401db010`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x14000c105`
- `api-ms-win-eventing-provider-l1-1-0!EventEnabled` at `0x14000c105`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000c23b`
- `api-ms-win-eventing-provider-l1-1-0!EventWrite` at `0x14000c23b`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000bed7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000befe`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000bed7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x14000befe`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x14000bfda`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x14000c37b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x14000bfda`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_Set` at `0x14000c37b`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000bfe8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000c24c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000c2d1`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000bfe8`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000c24c`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_SetSite` at `0x14000c2d1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c391`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14000c391`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000bf1e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14000bf1e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14000c07e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14000c07e`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x14000bf43`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x14000bf66`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x14000bf43`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHUnicodeToAnsi` at `0x14000bf66`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000c282`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x14000c282`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x14000bde2`
- `api-ms-win-shell-namespace-l1-1-0!SHParseDisplayName` at `0x14000bde2`
- `USER32!DestroyMenu` at `0x14000c267`
- `USER32!DestroyMenu` at `0x14000c267`
- `USER32!GetMenuDefaultItem` at `0x14000c02d`
- `USER32!GetMenuDefaultItem` at `0x14000c02d`
- `USER32!CreatePopupMenu` at `0x14000be74`
- `USER32!CreatePopupMenu` at `0x14000be74`

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
  _EVENT_DATA_DESCRIPTOR UserData; // [rsp+100h] [rbp+0h] BYREF
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
0x14000bd80  push    rbp
0x14000bd82  push    rbx
0x14000bd83  push    rsi
0x14000bd84  push    rdi
0x14000bd85  push    r12
0x14000bd87  push    r13
0x14000bd89  push    r14
0x14000bd8b  push    r15
0x14000bd8d  lea     rbp, [rsp-398h]
0x14000bd95  sub     rsp, 498h
0x14000bd9c  mov     rax, cs:__security_cookie
0x14000bda3  xor     rax, rsp
0x14000bda6  mov     [rbp+3D0h+var_50], rax
0x14000bdad  mov     r15, [rbp+3D0h+punk]
0x14000bdb4  lea     rax, [rsp+4D0h+var_460]
0x14000bdb9  mov     r14d, r9d
0x14000bdbc  mov     [rsp+4D0h+psfgaoOut], rax; psfgaoOut
0x14000bdc1  mov     rsi, r8
0x14000bdc4  mov     rdi, rdx
0x14000bdc7  xor     r12d, r12d
0x14000bdca  lea     r8, [rbp+3D0h+ppidl]; ppidl
0x14000bdce  mov     r9d, 70C58008h; sfgaoIn
0x14000bdd4  mov     [rbp+3D0h+ppidl], r12
0x14000bdd8  xor     edx, edx; pbc
0x14000bdda  mov     [rsp+4D0h+var_460], r12d
0x14000bddf  mov     r13, rcx
0x14000bde2  call    cs:__imp_SHParseDisplayName
0x14000bde8  mov     ebx, eax
0x14000bdea  test    eax, eax
0x14000bdec  js      loc_14000C288
0x14000bdf2  mov     rcx, [rbp+3D0h+ppidl]; pidl
0x14000bdf6  lea     r9, [rsp+4D0h+ppidlLast]; ppidlLast
0x14000bdfb  lea     r8, [rsp+4D0h+ppv]; ppv
0x14000be00  mov     [rsp+4D0h+var_488], r12
0x14000be05  lea     rdx, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x14000be0c  mov     [rsp+4D0h+ppidlLast], r12
0x14000be11  mov     [rsp+4D0h+ppv], r12
0x14000be16  call    SHBindToParent_0
0x14000be1b  mov     ebx, eax
0x14000be1d  test    eax, eax
0x14000be1f  js      short loc_14000BE6C
0x14000be21  mov     rcx, [rsp+4D0h+ppv]
0x14000be26  lea     rdx, [rsp+4D0h+var_488]
0x14000be2b  mov     [rsp+4D0h+lpDefaultChar], rdx
0x14000be30  lea     r9, [rsp+4D0h+ppidlLast]
0x14000be35  lea     rdx, _GUID_000214e4_0000_0000_c000_000000000046
0x14000be3c  mov     qword ptr [rsp+4D0h+cbMultiByte], r12
0x14000be41  mov     [rsp+4D0h+psfgaoOut], rdx
0x14000be46  lea     r8d, [r12+1]
0x14000be4b  mov     rax, [rcx]
0x14000be4e  xor     edx, edx
0x14000be50  mov     rax, [rax+50h]
0x14000be54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be59  mov     rcx, [rsp+4D0h+ppv]
0x14000be5e  mov     ebx, eax
0x14000be60  mov     rax, [rcx]
0x14000be63  mov     rax, [rax+10h]
0x14000be67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be6c  test    ebx, ebx
0x14000be6e  js      loc_14000C27E
0x14000be74  call    cs:__imp_CreatePopupMenu
0x14000be7a  mov     [rbp+3D0h+var_448], rax
0x14000be7e  mov     r12, rax
0x14000be81  test    rax, rax
0x14000be84  jz      loc_14000C26D
0x14000be8a  mov     ebx, 68h ; 'h'
0x14000be8f  lea     rcx, [rbp+3D0h+var_440]; void *
0x14000be93  mov     r8d, ebx; Size
0x14000be96  xor     edx, edx; Val
0x14000be98  call    memset_0
0x14000be9d  mov     [rbp+3D0h+lpWideCharStr], rsi
0x14000bea1  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000bea5  xor     esi, esi
0x14000bea7  mov     [rbp+3D0h+var_440], ebx
0x14000beaa  mov     [rsp+4D0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x14000beaf  mov     r8, rdi; lpWideCharStr
0x14000beb2  mov     [rsp+4D0h+lpDefaultChar], rsi; lpDefaultChar
0x14000beb7  xor     edx, edx; dwFlags
0x14000beb9  mov     [rsp+4D0h+cbMultiByte], esi; cbMultiByte
0x14000bebd  xor     ecx, ecx; CodePage
0x14000bebf  mov     [rsp+4D0h+psfgaoOut], rsi; lpMultiByteStr
0x14000bec4  mov     [rbp+3D0h+var_43C], 4500h
0x14000becb  mov     [rbp+3D0h+var_418], r14d
0x14000becf  mov     [rbp+3D0h+pwszSrc], rdi
0x14000bed3  mov     [rbp+3D0h+var_438], rsi
0x14000bed7  call    cs:__imp_WideCharToMultiByte
0x14000bedd  mov     r8, [rbp+3D0h+lpWideCharStr]; lpWideCharStr
0x14000bee1  or      r9d, 0FFFFFFFFh; cchWideChar
0x14000bee5  mov     [rsp+4D0h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x14000beea  xor     edx, edx; dwFlags
0x14000beec  mov     [rsp+4D0h+lpDefaultChar], rsi; lpDefaultChar
0x14000bef1  xor     ecx, ecx; CodePage
0x14000bef3  mov     [rsp+4D0h+cbMultiByte], esi; cbMultiByte
0x14000bef7  mov     [rsp+4D0h+psfgaoOut], rsi; lpMultiByteStr
0x14000befc  mov     ebx, eax
0x14000befe  call    cs:__imp_WideCharToMultiByte
0x14000bf04  mov     edi, eax
0x14000bf06  lea     ecx, [rax+rbx]
0x14000bf09  cmp     ecx, ebx
0x14000bf0b  jb      loc_14000C2B4
0x14000bf11  lea     r14d, [rsi+40h]
0x14000bf15  test    ecx, ecx
0x14000bf17  jz      short loc_14000BF70
0x14000bf19  mov     edx, ecx; uBytes
0x14000bf1b  mov     ecx, r14d; uFlags
0x14000bf1e  call    cs:__imp_LocalAlloc
0x14000bf24  mov     rsi, rax
0x14000bf27  test    rax, rax
0x14000bf2a  jz      loc_14000C2AD
0x14000bf30  mov     rcx, [rbp+3D0h+pwszSrc]; pwszSrc
0x14000bf34  test    rcx, rcx
0x14000bf37  jz      loc_14000C2BB
0x14000bf3d  mov     r8d, ebx; cchBuf
0x14000bf40  mov     rdx, rax; pszDst
0x14000bf43  call    cs:__imp_SHUnicodeToAnsi
0x14000bf49  mov     rax, rsi
0x14000bf4c  mov     rcx, [rbp+3D0h+lpWideCharStr]; pwszSrc
0x14000bf50  mov     [rbp+3D0h+var_428], rax
0x14000bf54  test    rcx, rcx
0x14000bf57  jz      loc_14000C2C2
0x14000bf5d  add     rbx, rsi
0x14000bf60  mov     r8d, edi; cchBuf
0x14000bf63  mov     rdx, rbx; pszDst
0x14000bf66  call    cs:__imp_SHUnicodeToAnsi
0x14000bf6c  mov     [rbp+3D0h+var_420], rbx
0x14000bf70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14000bf77  mov     ecx, 30h ; '0'; unsigned __int64
0x14000bf7c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14000bf81  mov     rdi, rax
0x14000bf84  test    rax, rax
0x14000bf87  jz      loc_14000C2C9
0x14000bf8d  lea     rcx, [rax+10h]; this
0x14000bf91  call    ??0CObjectWithSite@@QEAA@XZ; CObjectWithSite::CObjectWithSite(void)
0x14000bf96  lea     rax, ??_7CExecuteRunAppFilter@@6BICreatedProcess@@@; const CExecuteRunAppFilter::`vftable'{for `ICreatedProcess'}
0x14000bf9d  mov     dword ptr [rdi+20h], 1
0x14000bfa4  mov     [rdi+8], rax
0x14000bfa8  lea     rdx, ??_7CExecuteRunAppFilter@@6BIServiceProvider@@@; const CExecuteRunAppFilter::`vftable'{for `IServiceProvider'}
0x14000bfaf  lea     rax, ??_7CExecuteRunAppFilter@@6BCObjectWithSite@@@; const CExecuteRunAppFilter::`vftable'{for `CObjectWithSite'}
0x14000bfb6  mov     [rdi], rdx
0x14000bfb9  mov     [rcx], rax
0x14000bfbc  mov     rax, [rbp+3D0h+arg_38]
0x14000bfc3  mov     [rdi+28h], rax
0x14000bfc7  test    rax, rax
0x14000bfca  jz      short loc_14000BFD3
0x14000bfcc  mov     qword ptr [rax], 0
0x14000bfd3  lea     rcx, [rdi+18h]; ppunk
0x14000bfd7  mov     rdx, r15; punk
0x14000bfda  call    cs:__imp_IUnknown_Set
0x14000bfe0  mov     rcx, [rsp+4D0h+var_488]; punk
0x14000bfe5  mov     rdx, rdi; punkSite
0x14000bfe8  call    cs:__imp_IUnknown_SetSite
0x14000bfee  mov     rcx, [rsp+4D0h+var_488]
0x14000bff3  mov     r15d, 1
0x14000bff9  mov     [rsp+4D0h+cbMultiByte], r15d
0x14000bffe  mov     r9d, r15d
0x14000c001  xor     r8d, r8d
0x14000c004  mov     dword ptr [rsp+4D0h+psfgaoOut], 7FFFh
0x14000c00c  mov     rdx, r12
0x14000c00f  mov     rax, [rcx]
0x14000c012  mov     rax, [rax+18h]
0x14000c016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c01b  mov     ebx, eax
0x14000c01d  test    eax, eax
0x14000c01f  js      loc_14000C245
0x14000c025  xor     r8d, r8d; gmdiFlags
0x14000c028  xor     edx, edx; fByPos
0x14000c02a  mov     rcx, r12; hMenu
0x14000c02d  call    cs:__imp_GetMenuDefaultItem
0x14000c033  test    eax, eax
0x14000c035  jz      loc_14000C36B
0x14000c03b  mov     rcx, [rsp+4D0h+var_488]
0x14000c040  lea     rdx, [rbp+3D0h+var_440]
0x14000c044  sub     ax, r15w
0x14000c048  movzx   eax, ax
0x14000c04b  mov     [rbp+3D0h+var_430], rax
0x14000c04f  mov     rax, [rcx]
0x14000c052  mov     rax, [rax+20h]
0x14000c056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c05b  xor     edx, edx; Val
0x14000c05d  mov     [rbp+3D0h+var_1E0], 0
0x14000c067  mov     r8d, 188h; Size
0x14000c06d  lea     rcx, [rbp+3D0h+var_1DC]; void *
0x14000c074  mov     ebx, eax
0x14000c076  call    memset_0
0x14000c07b  mov     rcx, r13; pszPath
0x14000c07e  call    cs:__imp_PathFindFileNameW
0x14000c084  xor     r13d, r13d
0x14000c087  test    rax, rax
0x14000c08a  jnz     loc_14000C35C
0x14000c090  lea     rax, aNull; "(null)"
0x14000c097  lea     rcx, [rbp+3D0h+var_1DC]
0x14000c09e  movzx   edx, word ptr [rax]
0x14000c0a1  test    dx, dx
0x14000c0a4  jz      short loc_14000C0B9
0x14000c0a6  mov     [rcx], dx
0x14000c0a9  add     rax, 2
0x14000c0ad  add     rcx, 2
0x14000c0b1  dec     r14d
0x14000c0b4  cmp     r14d, r15d
0x14000c0b7  ja      short loc_14000C09E
0x14000c0b9  mov     [rcx], r13w
0x14000c0bd  lea     rdx, ShellTraceId_Explorer_StartupAppName_Info; EventDescriptor
0x14000c0c4  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x14000c0cb  mov     eax, r13d
0x14000c0ce  cmp     ebx, 800702E4h
0x14000c0d4  mov     [rbp+3D0h+var_1E0], 2
0x14000c0de  mov     [rbp+3D0h+var_15C], r15d
0x14000c0e5  setz    al
0x14000c0e8  mov     [rbp+3D0h+var_D8], r15
0x14000c0ef  mov     [rbp+3D0h+var_158], eax
0x14000c0f5  mov     [rsp+4D0h+var_480], 3
0x14000c0fd  mov     [rsp+4D0h+var_458], 74Dh
0x14000c105  call    cs:__imp_EventEnabled
0x14000c10b  test    al, al
0x14000c10d  jz      loc_14000C245
0x14000c113  xor     edx, edx; Val
0x14000c115  lea     rcx, [rbp+3D0h+UserData.Size]; void *
0x14000c119  mov     r8d, 1E8h; Size
0x14000c11f  call    memset_0
0x14000c124  mov     eax, dword ptr cs:a0; "0"
0x14000c12a  mov     r8d, r13d
0x14000c12d  mov     r15d, [rsp+4D0h+var_480]
0x14000c132  mov     r12d, 1
0x14000c138  mov     [rsp+4D0h+var_490], eax
0x14000c13c  lea     rax, ?g_SHSqmGlobalSession@@3U_GUID@@B; _GUID const g_SHSqmGlobalSession
0x14000c143  mov     [rbp+3D0h+UserData.Ptr], rax
0x14000c147  lea     rax, [rsp+4D0h+var_458]
0x14000c14c  mov     [rbp+3D0h+var_3C0], rax
0x14000c150  lea     rax, [rsp+4D0h+ppidlLast]
0x14000c155  mov     [rbp+3D0h+var_3B0], rax
0x14000c159  lea     rax, [rsp+4D0h+var_480]
0x14000c15e  mov     [rbp+3D0h+var_3A0], rax
0x14000c162  mov     dword ptr [rsp+4D0h+ppidlLast], 0Bh
0x14000c16a  mov     dword ptr [rsp+4D0h+ppv], r13d
0x14000c16f  mov     [rsp+4D0h+var_478], r13d
0x14000c174  mov     qword ptr [rbp+3D0h+UserData.Size], 10h
0x14000c17c  mov     [rbp+3D0h+var_3B8], 4
0x14000c184  mov     [rbp+3D0h+var_3A8], 4
0x14000c18c  mov     [rbp+3D0h+var_398], 4
0x14000c194  lea     r10d, [r8+r8*2]
0x14000c198  lea     ecx, [r10+4]
0x14000c19c  add     rcx, rcx
0x14000c19f  mov     qword ptr [rbp+rcx*8+3D0h+UserData.Size], 4
0x14000c1a8  cmp     r8d, r15d
0x14000c1ab  jb      loc_14000C2DE
0x14000c1b1  lea     rax, [rsp+4D0h+ppv]
0x14000c1b6  mov     [rbp+rcx*8+3D0h+UserData.Ptr], rax
0x14000c1bb  lea     rax, [rsp+4D0h+var_478]
0x14000c1c0  lea     ecx, [r10+5]
0x14000c1c4  add     rcx, rcx
0x14000c1c7  or      rdx, 0FFFFFFFFFFFFFFFFh
0x14000c1cb  mov     [rbp+rcx*8+3D0h+UserData.Ptr], rax
0x14000c1d0  lea     rax, [rsp+4D0h+var_490]
0x14000c1d5  mov     qword ptr [rbp+rcx*8+3D0h+UserData.Size], 4
0x14000c1de  inc     rdx
0x14000c1e1  cmp     [rax+rdx*2], r13w
0x14000c1e6  jnz     short loc_14000C1DE
0x14000c1e8  lea     r10, [rsp+4D0h+var_490]
0x14000c1ed  mov     ecx, r8d
0x14000c1f0  lea     r9, [rbp+3D0h+UserData]
0x14000c1f4  mov     eax, 6
0x14000c1f9  add     r8d, r12d
0x14000c1fc  lea     eax, [rax+rcx*2]
0x14000c1ff  add     ecx, eax
0x14000c201  lea     eax, ds:2[rdx*2]
0x14000c208  add     rcx, rcx
0x14000c20b  mov     [r9+rcx*8], r10
0x14000c20f  mov     [r9+rcx*8+8], eax
0x14000c214  mov     [r9+rcx*8+0Ch], r13d
0x14000c219  cmp     r8d, 9
0x14000c21d  jb      loc_14000C194
0x14000c223  mov     rcx, cs:Microsoft_Windows_Shell_Core_Provider_Context; RegHandle
0x14000c22a  lea     r9, [rbp+3D0h+UserData]; UserData
0x14000c22e  mov     r8d, 1Fh; UserDataCount
0x14000c234  lea     rdx, ShellTraceId_Explorer_StartupAppName_Info; EventDescriptor
0x14000c23b  call    cs:__imp_EventWrite
0x14000c241  mov     r12, [rbp+3D0h+var_448]
0x14000c245  mov     rcx, [rsp+4D0h+var_488]; punk
0x14000c24a  xor     edx, edx; punkSite
0x14000c24c  call    cs:__imp_IUnknown_SetSite
0x14000c252  test    rdi, rdi
0x14000c255  jnz     loc_14000C375
0x14000c25b  test    rsi, rsi
0x14000c25e  jnz     loc_14000C38E
0x14000c264  mov     rcx, r12; hMenu
0x14000c267  call    cs:__imp_DestroyMenu
0x14000c26d  mov     rcx, [rsp+4D0h+var_488]
0x14000c272  mov     rax, [rcx]
0x14000c275  mov     rax, [rax+10h]
0x14000c279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c27e  mov     rcx, [rbp+3D0h+ppidl]; pidl
0x14000c282  call    cs:__imp_ILFree
0x14000c288  mov     eax, ebx
0x14000c28a  mov     rcx, [rbp+3D0h+var_50]
0x14000c291  xor     rcx, rsp; StackCookie
0x14000c294  call    __security_check_cookie
0x14000c299  add     rsp, 498h
0x14000c2a0  pop     r15
0x14000c2a2  pop     r14
0x14000c2a4  pop     r13
  ... truncated ...
```
