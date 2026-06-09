# ImpExpUserDlg::ExternalDlg(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x1803fa740`
- end: `0x1803fad79`
- name: `?ExternalDlg@ImpExpUserDlg@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1593`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180011230`
- `0x1800b8c28`
- `0x1803fa304`
- `0x1803fa6d4`
- `0x1803fa740`
- `0x1803fad80`
- `0x1803fae1c`
- `0x1803fc2c0`
- `0x1803fc984`
- `0x1804105e4`
- `0x18041baa4`
- `0x180441ff4`
- `0x180442060`
- `0x18054e286`
- `0x18054e310`

## import_xrefs

- `SHLWAPI!PathIsDirectoryW` at `0x1803fa8a7`
- `SHLWAPI!PathIsDirectoryW` at `0x1803fac75`
- `SHLWAPI!PathIsDirectoryW` at `0x1803fa8a7`
- `SHLWAPI!PathIsDirectoryW` at `0x1803fac75`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803fa962`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803fa98a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803fa9b1`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803fa9cd`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803fa962`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803fa98a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803fa9b1`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1803fa9cd`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsRelativeW` at `0x1803fac8f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsRelativeW` at `0x1803fac8f`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1803fad01`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1803fad01`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1803fa8c7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1803fac9c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1803fa8c7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x1803fac9c`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x1803fa900`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x1803fac82`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x1803fa900`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x1803fac82`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsURLW` at `0x1803facaa`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsURLW` at `0x1803facaa`
- `USER32!SetDlgItemTextW` at `0x1803fab66`
- `USER32!SetDlgItemTextW` at `0x1803fab66`
- `USER32!SetWindowTextW` at `0x1803faa6e`
- `USER32!SetWindowTextW` at `0x1803faa6e`
- `USER32!GetDlgItemTextW` at `0x1803fa895`
- `USER32!GetDlgItemTextW` at `0x1803faba6`
- `USER32!GetDlgItemTextW` at `0x1803fa895`
- `USER32!GetDlgItemTextW` at `0x1803faba6`
- `USER32!SendMessageW` at `0x1803faa9a`
- `USER32!SendMessageW` at `0x1803faab9`
- `USER32!SendMessageW` at `0x1803faa9a`
- `USER32!SendMessageW` at `0x1803faab9`
- `USER32!SetWindowLongPtrW` at `0x1803facf8`
- `USER32!SetWindowLongPtrW` at `0x1803facf8`
- `USER32!GetDlgItem` at `0x1803faa61`
- `USER32!GetDlgItem` at `0x1803faa84`
- `USER32!GetDlgItem` at `0x1803faaa8`
- `USER32!GetDlgItem` at `0x1803fab74`
- `USER32!GetDlgItem` at `0x1803faa61`
- `USER32!GetDlgItem` at `0x1803faa84`
- `USER32!GetDlgItem` at `0x1803faaa8`
- `USER32!GetDlgItem` at `0x1803fab74`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1803fa93b`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1803fa93b`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1803faa29`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1803faa29`

## pseudocode

```c
__int64 __fastcall ImpExpUserDlg::ExternalDlg(HWND a1, unsigned int a2, unsigned __int64 a3, __int64 a4)
{
  int v5; // edi
  LPWSTR v8; // rdi
  __int64 v9; // rbx
  int v10; // ecx
  const WCHAR *v11; // rax
  const unsigned __int16 *FileNameW; // rax
  int v13; // eax
  UINT v14; // edx
  unsigned int i; // ecx
  WCHAR v16; // ax
  DWORD v17; // eax
  BOOL OpenFileNameW; // eax
  HWND DlgItem; // rax
  HWND v20; // rax
  HWND v21; // rax
  ImpExpUserProcess *v22; // rdi
  __int64 v23; // rdx
  HWND v24; // rax
  LPWSTR v25; // rdi
  unsigned __int16 *v26; // rcx
  int v27; // eax
  unsigned int v28; // esi
  unsigned int v29; // r8d
  LONG_PTR v30; // r8
  unsigned int v31; // edx
  int v32; // eax
  size_t v33; // rdx
  int v34; // eax
  const WCHAR *v35; // r8
  unsigned int v37; // [rsp+20h] [rbp-E0h]
  unsigned int v38; // [rsp+40h] [rbp-C0h] BYREF
  LPWSTR lpString; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v40; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v41; // [rsp+58h] [rbp-A8h] BYREF
  struct tagOFNW v42; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String[264]; // [rsp+100h] [rbp+0h] BYREF
  unsigned __int16 v44[264]; // [rsp+310h] [rbp+210h] BYREF
  WCHAR v45[264]; // [rsp+520h] [rbp+420h] BYREF
  WCHAR Buffer[264]; // [rsp+730h] [rbp+630h] BYREF

  v40 = 0;
  v5 = a3;
  lpString = 0;
  v38 = 0;
  if ( !ImpExpUserDlg::CommonDialogProc(
          a1,
          a2,
          a3,
          a4,
          (struct ImpExpUserProcess **)&lpString,
          &v38,
          (struct ReturnValue *)&v40) )
    return v40;
  if ( a2 != 78 )
  {
    if ( a2 == 273 && v5 == 16994 )
    {
      memset_0(&v42, 0, sizeof(v42));
      v8 = lpString;
      v42.hInstance = g_hInstResources;
      v42.lpstrFilter = v45;
      v42.lpstrFile = v44;
      v42.lpstrInitialDir = String;
      v42.lStructSize = 152;
      v9 = 1;
      v42.lpstrTitle = Buffer;
      v42.hwndOwner = a1;
      v42.nFilterIndex = 1;
      v42.lpstrCustomFilter = 0;
      v42.nMaxFile = 520;
      v42.lpstrFileTitle = 0;
      v10 = *((_DWORD *)lpString + 782);
      if ( v10 == 1 )
      {
        v11 = L"txt";
      }
      else
      {
        v11 = L"opml";
        if ( v10 != 3 )
          v11 = L"htm";
      }
      v42.lpstrDefExt = v11;
      GetDlgItemTextW(a1, 17013, String, 260);
      v44[0] = 0;
      if ( PathIsDirectoryW(String) )
      {
        v44[0] = 0;
        v42.lpstrInitialDir = String;
      }
      else
      {
        FileNameW = PathFindFileNameW(String);
        if ( FileNameW == String || !FileNameW )
        {
          if ( PathIsFileSpecW(String) )
            StringCchCopyW(v44, 0x104u, String);
          else
            v44[0] = 0;
          v42.lpstrInitialDir = String;
          SHGetSpecialFolderPathW(0, String, 0, 0);
        }
        else
        {
          *((_WORD *)FileNameW - 1) = 0;
          v42.lpstrInitialDir = String;
          StringCchCopyW(v44, 0x104u, FileNameW);
        }
      }
      v13 = *((_DWORD *)v8 + 782);
      switch ( v13 )
      {
        case 2:
          LoadStringW(g_hInstResources, 0x4221u, Buffer, 260);
          v14 = 16931;
          break;
        case 3:
          LoadStringW(g_hInstResources, 0x4230u, Buffer, 260);
          v14 = 16945;
          break;
        case 1:
          LoadStringW(g_hInstResources, 0x4222u, Buffer, 260);
          v14 = 16932;
          break;
        default:
          goto LABEL_25;
      }
      LoadStringW(g_hInstResources, v14, v45, 260);
LABEL_25:
      for ( i = 0; i < 0x104; ++i )
      {
        v16 = v45[i];
        if ( !v16 )
          break;
        if ( v16 == 64 )
        {
          if ( (unsigned __int64)(2LL * (int)i) >= 0x208 )
            _report_rangecheckfailure();
          v45[i] = 0;
        }
      }
      v17 = 589828;
      v42.Flags = 589828;
      if ( *((_DWORD *)v8 + 783) == 1 )
        v17 = 595972;
      v42.Flags = v17;
      if ( LCIEIsCurrentProcessInPrivate() )
        v42.Flags |= 0x2000000u;
      if ( *((_DWORD *)v8 + 783) == 1 )
        OpenFileNameW = GetOpenFileNameW(&v42);
      else
        OpenFileNameW = GetSaveFileNameW(&v42);
      if ( OpenFileNameW )
      {
        DlgItem = GetDlgItem(a1, 17013);
        if ( SetWindowTextW(DlgItem, v42.lpstrFile) )
        {
          v20 = GetDlgItem(a1, 17031);
          SendMessageW(v20, 0xF1u, 1u, 0);
          v21 = GetDlgItem(a1, 17014);
          SendMessageW(v21, 0xF1u, 0, 0);
        }
      }
      return v9;
    }
    return v40;
  }
  if ( *(_DWORD *)(a4 + 16) == -209 )
  {
    *((_QWORD *)lpString + 391) = 0;
    return v40;
  }
  if ( *(_DWORD *)(a4 + 16) != -207 )
  {
    if ( *(_DWORD *)(a4 + 16) != -200 )
      return v40;
    v22 = (ImpExpUserProcess *)lpString;
    v41 = 260;
    if ( v38 == 16998 || v38 == 17001 )
    {
      v23 = 2;
    }
    else if ( v38 == 17282 || v38 == 17545 )
    {
      v23 = 3;
    }
    else
    {
      if ( v38 - 17008 > 1 )
      {
LABEL_55:
        if ( ImpExpUserProcess::GetExternalManualDefault(v22, Buffer, &v41) )
          SetDlgItemTextW(a1, 17013, Buffer);
        v24 = GetDlgItem(a1, 17013);
        IESHAutoComplete(v24, 1u);
        return v40;
      }
      v23 = 1;
    }
    ImpExpUserProcess::SelectExternalType(lpString, v23);
    goto LABEL_55;
  }
  v25 = lpString;
  v9 = 1;
  GetDlgItemTextW(a1, 17013, lpString, 260);
  if ( v38 == 16998 || v38 == 17001 )
  {
    v26 = v25 + 520;
  }
  else if ( v38 == 17282 || v38 == 17545 )
  {
    StringCchCopyW(v25 + 1040, 0x104u, v25);
    v26 = v25 + 1593;
  }
  else
  {
    if ( v38 - 17008 > 1 )
      goto LABEL_67;
    v26 = v25 + 780;
  }
  StringCchCopyW(v26, 0x104u, v25);
LABEL_67:
  v27 = *((_DWORD *)v25 + 783);
  if ( v27 == 2 )
  {
    switch ( *((_DWORD *)v25 + 782) )
    {
      case 1:
        v28 = 16903;
        break;
      case 2:
        v28 = 16899;
        break;
      case 3:
        v28 = 16966;
        break;
      default:
        goto LABEL_91;
    }
    if ( (unsigned int)DoesFileExist(v25) )
    {
      v30 = -(__int64)((unsigned int)WarningMessageBox(a1, v28, v29, v25, v37) != 6);
LABEL_90:
      SetWindowLongPtrW(a1, 0, v30);
      goto LABEL_91;
    }
    if ( !v25
      || PathIsDirectoryW(v25)
      || PathIsFileSpecW(v25)
      || PathIsRelativeW(v25)
      || PathFindFileNameW(v25) == v25
      || PathIsURLW(v25) )
    {
      v31 = v28;
LABEL_89:
      FileNotFoundMessageBox(a1, v31, v29);
      v30 = -1;
      goto LABEL_90;
    }
  }
  else if ( v27 == 1 && !(unsigned int)DoesFileExist(v25) )
  {
    v32 = *((_DWORD *)v25 + 782);
    if ( v32 == 1 )
    {
      v31 = 16901;
    }
    else
    {
      v31 = 16976;
      if ( v32 == 2 )
        v31 = 16897;
    }
    goto LABEL_89;
  }
LABEL_91:
  if ( !*PathFindExtensionW(v25) )
  {
    v34 = *((_DWORD *)v25 + 782);
    if ( v34 == 1 )
    {
      v35 = L".txt";
    }
    else
    {
      v35 = L".opml";
      if ( v34 != 3 )
        v35 = L".htm";
    }
    PathCchRenameExtension(v25, v33, v35);
  }
  return v9;
}

```

## disassembly

```asm
0x1803fa740  mov     [rsp-8+arg_8], rbx
0x1803fa745  push    rbp
0x1803fa746  push    rsi
0x1803fa747  push    rdi
0x1803fa748  push    r14
0x1803fa74a  push    r15
0x1803fa74c  lea     rbp, [rsp-850h]
0x1803fa754  sub     rsp, 950h
0x1803fa75b  mov     rax, cs:__security_cookie
0x1803fa762  xor     rax, rsp
0x1803fa765  mov     [rbp+870h+var_30], rax
0x1803fa76c  xor     r15d, r15d
0x1803fa76f  lea     rax, [rsp+970h+var_920]
0x1803fa774  mov     [rsp+970h+var_940], rax; struct ReturnValue *
0x1803fa779  mov     rsi, r9
0x1803fa77c  lea     rax, [rsp+970h+var_930]
0x1803fa781  mov     [rsp+970h+var_920], r15
0x1803fa786  mov     [rsp+970h+var_948], rax; unsigned int *
0x1803fa78b  mov     rdi, r8
0x1803fa78e  lea     rax, [rsp+970h+lpString]
0x1803fa793  mov     [rsp+970h+lpString], r15
0x1803fa798  mov     [rsp+970h+var_950], rax; unsigned int
0x1803fa79d  mov     ebx, edx
0x1803fa79f  mov     r14, rcx
0x1803fa7a2  mov     [rsp+970h+var_930], r15d
0x1803fa7a7  call    ?CommonDialogProc@ImpExpUserDlg@@CAKPEAUHWND__@@I_K_JPEAPEAVImpExpUserProcess@@PEAKAEAVReturnValue@@@Z; ImpExpUserDlg::CommonDialogProc(HWND__ *,uint,unsigned __int64,__int64,ImpExpUserProcess * *,ulong *,ReturnValue &)
0x1803fa7ac  test    eax, eax
0x1803fa7ae  jz      loc_1803FAD4B
0x1803fa7b4  cmp     ebx, 4Eh ; 'N'
0x1803fa7b7  jz      loc_1803FAAC4
0x1803fa7bd  cmp     ebx, 111h
0x1803fa7c3  jnz     loc_1803FAD4B
0x1803fa7c9  mov     rax, rdi
0x1803fa7cc  shr     rax, 10h
0x1803fa7d0  test    ax, ax
0x1803fa7d3  jnz     loc_1803FAD4B
0x1803fa7d9  mov     eax, 4262h
0x1803fa7de  cmp     di, ax
0x1803fa7e1  jnz     loc_1803FAD4B
0x1803fa7e7  mov     ebx, 98h
0x1803fa7ec  lea     rcx, [rsp+970h+var_910]; void *
0x1803fa7f1  mov     r8d, ebx; Size
0x1803fa7f4  xor     edx, edx; Val
0x1803fa7f6  call    memset_0
0x1803fa7fb  mov     rax, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstResources
0x1803fa802  mov     rdi, [rsp+970h+lpString]
0x1803fa807  mov     [rsp+970h+var_910.hInstance], rax
0x1803fa80c  lea     rax, [rbp+870h+var_450]
0x1803fa813  mov     [rsp+970h+var_910.lpstrFilter], rax
0x1803fa818  lea     rax, [rbp+870h+var_660]
0x1803fa81f  mov     [rbp+870h+var_910.lpstrFile], rax
0x1803fa823  lea     rax, [rbp+870h+String]
0x1803fa827  mov     [rbp+870h+var_910.lpstrInitialDir], rax
0x1803fa82b  lea     rax, [rbp+870h+Buffer]
0x1803fa832  mov     [rsp+970h+var_910.lStructSize], ebx
0x1803fa836  lea     ebx, [r15+1]
0x1803fa83a  mov     [rbp+870h+var_910.lpstrTitle], rax
0x1803fa83e  mov     [rsp+970h+var_910.hwndOwner], r14
0x1803fa843  mov     [rbp+870h+var_910.nFilterIndex], ebx
0x1803fa846  mov     [rbp+870h+var_910.lpstrCustomFilter], r15
0x1803fa84a  mov     [rbp+870h+var_910.nMaxFile], 208h
0x1803fa851  mov     [rbp+870h+var_910.lpstrFileTitle], r15
0x1803fa855  mov     ecx, [rdi+0C38h]
0x1803fa85b  cmp     ecx, ebx
0x1803fa85d  jnz     short loc_1803FA868
0x1803fa85f  lea     rax, aTxt_0; "txt"
0x1803fa866  jmp     short loc_1803FA87D
0x1803fa868  cmp     ecx, 3
0x1803fa86b  lea     rax, aOpml_0; "opml"
0x1803fa872  lea     rdx, aHtm_1; "htm"
0x1803fa879  cmovnz  rax, rdx
0x1803fa87d  mov     esi, 104h
0x1803fa882  mov     [rbp+870h+var_910.lpstrDefExt], rax
0x1803fa886  mov     r9d, esi; cchMax
0x1803fa889  lea     r8, [rbp+870h+String]; lpString
0x1803fa88d  mov     edx, 4275h; nIDDlgItem
0x1803fa892  mov     rcx, r14; hDlg
0x1803fa895  call    cs:__imp_GetDlgItemTextW
0x1803fa89b  lea     rcx, [rbp+870h+String]; pszPath
0x1803fa89f  mov     [rbp+870h+var_660], r15w
0x1803fa8a7  call    cs:__imp_PathIsDirectoryW
0x1803fa8ad  test    eax, eax
0x1803fa8af  jz      short loc_1803FA8C3
0x1803fa8b1  lea     rax, [rbp+870h+String]
0x1803fa8b5  mov     [rbp+870h+var_660], r15w
0x1803fa8bd  mov     [rbp+870h+var_910.lpstrInitialDir], rax
0x1803fa8c1  jmp     short loc_1803FA941
0x1803fa8c3  lea     rcx, [rbp+870h+String]; pszPath
0x1803fa8c7  call    cs:__imp_PathFindFileNameW
0x1803fa8cd  lea     rcx, [rbp+870h+String]
0x1803fa8d1  cmp     rax, rcx
0x1803fa8d4  jz      short loc_1803FA8FC
0x1803fa8d6  test    rax, rax
0x1803fa8d9  jz      short loc_1803FA8FC
0x1803fa8db  lea     rcx, [rbp+870h+String]
0x1803fa8df  mov     [rax-2], r15w
0x1803fa8e4  mov     [rbp+870h+var_910.lpstrInitialDir], rcx
0x1803fa8e8  mov     r8, rax; unsigned __int16 *
0x1803fa8eb  lea     rcx, [rbp+870h+var_660]; unsigned __int16 *
0x1803fa8f2  mov     rdx, rsi; unsigned __int64
0x1803fa8f5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1803fa8fa  jmp     short loc_1803FA941
0x1803fa8fc  lea     rcx, [rbp+870h+String]; pszPath
0x1803fa900  call    cs:__imp_PathIsFileSpecW
0x1803fa906  test    eax, eax
0x1803fa908  jz      short loc_1803FA91F
0x1803fa90a  lea     r8, [rbp+870h+String]; unsigned __int16 *
0x1803fa90e  mov     rdx, rsi; unsigned __int64
0x1803fa911  lea     rcx, [rbp+870h+var_660]; unsigned __int16 *
0x1803fa918  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1803fa91d  jmp     short loc_1803FA927
0x1803fa91f  mov     [rbp+870h+var_660], r15w
0x1803fa927  lea     rax, [rbp+870h+String]
0x1803fa92b  xor     r9d, r9d; fCreate
0x1803fa92e  xor     r8d, r8d; csidl
0x1803fa931  mov     [rbp+870h+var_910.lpstrInitialDir], rax
0x1803fa935  lea     rdx, [rbp+870h+String]; pszPath
0x1803fa939  xor     ecx, ecx; hwnd
0x1803fa93b  call    cs:__imp_SHGetSpecialFolderPathW
0x1803fa941  mov     eax, [rdi+0C38h]
0x1803fa947  cmp     eax, 2
0x1803fa94a  jnz     short loc_1803FA96F
0x1803fa94c  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x1803fa953  lea     r8, [rbp+870h+Buffer]; lpBuffer
0x1803fa95a  mov     r9d, esi; cchBufferMax
0x1803fa95d  mov     edx, 4221h; uID
0x1803fa962  call    cs:__imp_LoadStringW
0x1803fa968  mov     edx, 4223h
0x1803fa96d  jmp     short loc_1803FA9BC
0x1803fa96f  cmp     eax, 3
0x1803fa972  jnz     short loc_1803FA997
0x1803fa974  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x1803fa97b  lea     r8, [rbp+870h+Buffer]; lpBuffer
0x1803fa982  mov     r9d, esi; cchBufferMax
0x1803fa985  mov     edx, 4230h; uID
0x1803fa98a  call    cs:__imp_LoadStringW
0x1803fa990  mov     edx, 4231h
0x1803fa995  jmp     short loc_1803FA9BC
0x1803fa997  cmp     eax, ebx
0x1803fa999  jnz     short loc_1803FA9D3
0x1803fa99b  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x1803fa9a2  lea     r8, [rbp+870h+Buffer]; lpBuffer
0x1803fa9a9  mov     r9d, esi; cchBufferMax
0x1803fa9ac  mov     edx, 4222h; uID
0x1803fa9b1  call    cs:__imp_LoadStringW
0x1803fa9b7  mov     edx, 4224h; uID
0x1803fa9bc  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x1803fa9c3  lea     r8, [rbp+870h+var_450]; lpBuffer
0x1803fa9ca  mov     r9d, esi; cchBufferMax
0x1803fa9cd  call    cs:__imp_LoadStringW
0x1803fa9d3  mov     ecx, r15d
0x1803fa9d6  cmp     ecx, esi
0x1803fa9d8  jnb     short loc_1803FAA10
0x1803fa9da  movsxd  rax, ecx
0x1803fa9dd  lea     rdx, [rax+rax]
0x1803fa9e1  movzx   eax, [rbp+rdx+870h+var_450]
0x1803fa9e9  test    ax, ax
0x1803fa9ec  jz      short loc_1803FAA10
0x1803fa9ee  cmp     ax, 40h ; '@'
0x1803fa9f2  jnz     short loc_1803FAA06
0x1803fa9f4  cmp     rdx, 208h
0x1803fa9fb  jnb     short loc_1803FAA0A
0x1803fa9fd  mov     [rbp+rdx+870h+var_450], r15w
0x1803faa06  add     ecx, ebx
0x1803faa08  jmp     short loc_1803FA9D6
0x1803faa0a  call    __report_rangecheckfailure
0x1803faa10  mov     eax, 90004h
0x1803faa15  mov     ecx, 91804h
0x1803faa1a  mov     [rbp+870h+var_910.Flags], eax
0x1803faa1d  cmp     [rdi+0C3Ch], ebx
0x1803faa23  cmovz   eax, ecx
0x1803faa26  mov     [rbp+870h+var_910.Flags], eax
0x1803faa29  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1803faa2f  test    al, al
0x1803faa31  jz      short loc_1803FAA38
0x1803faa33  bts     [rbp+870h+var_910.Flags], 19h
0x1803faa38  lea     rcx, [rsp+970h+var_910]; LPOPENFILENAMEW
0x1803faa3d  cmp     [rdi+0C3Ch], ebx
0x1803faa43  jnz     short loc_1803FAA4C
0x1803faa45  call    GetOpenFileNameW
0x1803faa4a  jmp     short loc_1803FAA51
0x1803faa4c  call    GetSaveFileNameW
0x1803faa51  test    eax, eax
0x1803faa53  jz      loc_1803FAD50
0x1803faa59  mov     edx, 4275h; nIDDlgItem
0x1803faa5e  mov     rcx, r14; hDlg
0x1803faa61  call    cs:__imp_GetDlgItem
0x1803faa67  mov     rdx, [rbp+870h+var_910.lpstrFile]; lpString
0x1803faa6b  mov     rcx, rax; hWnd
0x1803faa6e  call    cs:__imp_SetWindowTextW
0x1803faa74  test    eax, eax
0x1803faa76  jz      loc_1803FAD50
0x1803faa7c  mov     edx, 4287h; nIDDlgItem
0x1803faa81  mov     rcx, r14; hDlg
0x1803faa84  call    cs:__imp_GetDlgItem
0x1803faa8a  mov     edi, 0F1h
0x1803faa8f  xor     r9d, r9d; lParam
0x1803faa92  mov     rcx, rax; hWnd
0x1803faa95  mov     edx, edi; Msg
0x1803faa97  mov     r8, rbx; wParam
0x1803faa9a  call    cs:__imp_SendMessageW
0x1803faaa0  mov     edx, 4276h; nIDDlgItem
0x1803faaa5  mov     rcx, r14; hDlg
0x1803faaa8  call    cs:__imp_GetDlgItem
0x1803faaae  xor     r9d, r9d; lParam
0x1803faab1  xor     r8d, r8d; wParam
0x1803faab4  mov     rcx, rax; hWnd
0x1803faab7  mov     edx, edi; Msg
0x1803faab9  call    cs:__imp_SendMessageW
0x1803faabf  jmp     loc_1803FAD50
0x1803faac4  cmp     dword ptr [rsi+10h], 0FFFFFF2Fh
0x1803faacb  jz      loc_1803FAD3F
0x1803faad1  cmp     dword ptr [rsi+10h], 0FFFFFF31h
0x1803faad8  jz      loc_1803FAB89
0x1803faade  cmp     dword ptr [rsi+10h], 0FFFFFF38h
0x1803faae5  jnz     loc_1803FAD4B
0x1803faaeb  mov     eax, [rsp+970h+var_930]
0x1803faaef  mov     esi, 104h
0x1803faaf4  mov     rdi, [rsp+970h+lpString]
0x1803faaf9  mov     ebx, 1
0x1803faafe  mov     [rsp+970h+var_918], esi
0x1803fab02  cmp     eax, 4266h
0x1803fab07  jz      short loc_1803FAB32
0x1803fab09  cmp     eax, 4269h
0x1803fab0e  jz      short loc_1803FAB32
0x1803fab10  cmp     eax, 4382h
0x1803fab15  jz      short loc_1803FAB2B
0x1803fab17  cmp     eax, 4489h
0x1803fab1c  jz      short loc_1803FAB2B
0x1803fab1e  add     eax, 0FFFFBD90h
0x1803fab23  cmp     eax, ebx
0x1803fab25  ja      short loc_1803FAB3F
0x1803fab27  mov     edx, ebx
0x1803fab29  jmp     short loc_1803FAB37
0x1803fab2b  mov     edx, 3
0x1803fab30  jmp     short loc_1803FAB37
0x1803fab32  mov     edx, 2
0x1803fab37  mov     rcx, rdi
0x1803fab3a  call    ?SelectExternalType@ImpExpUserProcess@@QEAAXW4ExternalType@@@Z; ImpExpUserProcess::SelectExternalType(ExternalType)
0x1803fab3f  lea     r8, [rsp+970h+var_918]; unsigned int *
0x1803fab44  mov     rcx, rdi; this
0x1803fab47  lea     rdx, [rbp+870h+Buffer]; unsigned __int16 *
0x1803fab4e  call    ?GetExternalManualDefault@ImpExpUserProcess@@QEAAHPEAGPEAK@Z; ImpExpUserProcess::GetExternalManualDefault(ushort *,ulong *)
0x1803fab53  test    eax, eax
0x1803fab55  jz      short loc_1803FAB6C
0x1803fab57  lea     r8, [rbp+870h+Buffer]; lpString
0x1803fab5e  mov     edx, 4275h; nIDDlgItem
0x1803fab63  mov     rcx, r14; hDlg
0x1803fab66  call    cs:__imp_SetDlgItemTextW
0x1803fab6c  mov     edx, 4275h; nIDDlgItem
0x1803fab71  mov     rcx, r14; hDlg
0x1803fab74  call    cs:__imp_GetDlgItem
0x1803fab7a  mov     rcx, rax; HWND
0x1803fab7d  mov     edx, ebx; unsigned int
0x1803fab7f  call    ?IESHAutoComplete@@YAJPEAUHWND__@@K@Z; IESHAutoComplete(HWND__ *,ulong)
0x1803fab84  jmp     loc_1803FAD4B
0x1803fab89  mov     rdi, [rsp+970h+lpString]
0x1803fab8e  mov     esi, 104h
0x1803fab93  mov     r9d, esi; cchMax
0x1803fab96  mov     r8, rdi; lpString
0x1803fab99  mov     edx, 4275h; nIDDlgItem
0x1803fab9e  mov     rcx, r14; hDlg
0x1803faba1  mov     ebx, 1
0x1803faba6  call    cs:__imp_GetDlgItemTextW
0x1803fabac  mov     eax, [rsp+970h+var_930]
0x1803fabb0  cmp     eax, 4266h
0x1803fabb5  jz      short loc_1803FABF9
0x1803fabb7  cmp     eax, 4269h
0x1803fabbc  jz      short loc_1803FABF9
0x1803fabbe  cmp     eax, 4382h
0x1803fabc3  jz      short loc_1803FABDE
0x1803fabc5  cmp     eax, 4489h
0x1803fabca  jz      short loc_1803FABDE
0x1803fabcc  add     eax, 0FFFFBD90h
0x1803fabd1  cmp     eax, ebx
0x1803fabd3  ja      short loc_1803FAC0B
0x1803fabd5  lea     rcx, [rdi+618h]
0x1803fabdc  jmp     short loc_1803FAC00
0x1803fabde  lea     rcx, [rdi+820h]; unsigned __int16 *
0x1803fabe5  mov     r8, rdi; unsigned __int16 *
0x1803fabe8  mov     rdx, rsi; unsigned __int64
0x1803fabeb  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1803fabf0  lea     rcx, [rdi+0C72h]
0x1803fabf7  jmp     short loc_1803FAC00
0x1803fabf9  lea     rcx, [rdi+410h]; unsigned __int16 *
0x1803fac00  mov     r8, rdi; unsigned __int16 *
0x1803fac03  mov     rdx, rsi; unsigned __int64
0x1803fac06  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1803fac0b  mov     eax, [rdi+0C3Ch]
0x1803fac11  cmp     eax, 2
0x1803fac14  jnz     loc_1803FACB8
0x1803fac1a  mov     ecx, [rdi+0C38h]
0x1803fac20  sub     ecx, ebx
0x1803fac22  jz      short loc_1803FAC3E
0x1803fac24  sub     ecx, ebx
0x1803fac26  jz      short loc_1803FAC37
0x1803fac28  cmp     ecx, ebx
0x1803fac2a  jnz     loc_1803FACFE
0x1803fac30  mov     esi, 4246h
0x1803fac35  jmp     short loc_1803FAC43
  ... truncated ...
```
