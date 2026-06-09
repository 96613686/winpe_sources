# ImpExpUserDlg::ExternalDlg(HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x180431090`
- end: `0x180431769`
- name: `?ExternalDlg@ImpExpUserDlg@@CA_JPEAUHWND__@@I_K_J@Z`
- size: `1753`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `15`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callees

- `0x1800144d0`
- `0x1800bf938`
- `0x180430c04`
- `0x180431020`
- `0x180431090`
- `0x180431770`
- `0x18043181c`
- `0x180432ea0`
- `0x18043365c`
- `0x180448a0c`
- `0x1804549e4`
- `0x18047cbfc`
- `0x18047cc6c`
- `0x180591ef6`
- `0x180591f80`

## import_xrefs

- `SHLWAPI!PathIsDirectoryW` at `0x1804311fd`
- `SHLWAPI!PathIsDirectoryW` at `0x18043163a`
- `SHLWAPI!PathIsDirectoryW` at `0x1804311fd`
- `SHLWAPI!PathIsDirectoryW` at `0x18043163a`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1804312d3`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180431301`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18043132e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180431350`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x1804312d3`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180431301`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x18043132e`
- `api-ms-win-downlevel-user32-l1-1-0!LoadStringW` at `0x180431350`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsRelativeW` at `0x180431660`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsRelativeW` at `0x180431660`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1804316ea`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindExtensionW` at `0x1804316ea`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180431226`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180431673`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180431226`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathFindFileNameW` at `0x180431673`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x180431265`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x18043164d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x180431265`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsFileSpecW` at `0x18043164d`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsURLW` at `0x180431687`
- `api-ms-win-downlevel-shlwapi-l1-1-0!PathIsURLW` at `0x180431687`
- `USER32!SetDlgItemTextW` at `0x180431519`
- `USER32!SetDlgItemTextW` at `0x180431519`
- `USER32!SetWindowTextW` at `0x180431403`
- `USER32!SetWindowTextW` at `0x180431403`
- `USER32!GetDlgItemTextW` at `0x1804311e5`
- `USER32!GetDlgItemTextW` at `0x180431565`
- `USER32!GetDlgItemTextW` at `0x1804311e5`
- `USER32!GetDlgItemTextW` at `0x180431565`
- `USER32!SendMessageW` at `0x18043143b`
- `USER32!SendMessageW` at `0x180431466`
- `USER32!SendMessageW` at `0x18043143b`
- `USER32!SendMessageW` at `0x180431466`
- `USER32!SetWindowLongPtrW` at `0x1804316db`
- `USER32!SetWindowLongPtrW` at `0x1804316db`
- `USER32!GetDlgItem` at `0x1804313f0`
- `USER32!GetDlgItem` at `0x18043141f`
- `USER32!GetDlgItem` at `0x18043144f`
- `USER32!GetDlgItem` at `0x18043152d`
- `USER32!GetDlgItem` at `0x1804313f0`
- `USER32!GetDlgItem` at `0x18043141f`
- `USER32!GetDlgItem` at `0x18043144f`
- `USER32!GetDlgItem` at `0x18043152d`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1804312a6`
- `SHELL32!SHGetSpecialFolderPathW` at `0x1804312a6`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1804313b2`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x1804313b2`

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
0x180431090  mov     [rsp-8+arg_8], rbx
0x180431095  push    rbp
0x180431096  push    rsi
0x180431097  push    rdi
0x180431098  push    r14
0x18043109a  push    r15
0x18043109c  lea     rbp, [rsp-850h]
0x1804310a4  sub     rsp, 950h
0x1804310ab  mov     rax, cs:__security_cookie
0x1804310b2  xor     rax, rsp
0x1804310b5  mov     [rbp+870h+var_30], rax
0x1804310bc  xor     r15d, r15d
0x1804310bf  lea     rax, [rsp+970h+var_920]
0x1804310c4  mov     [rsp+970h+var_940], rax; struct ReturnValue *
0x1804310c9  mov     rsi, r9
0x1804310cc  lea     rax, [rsp+970h+var_930]
0x1804310d1  mov     [rsp+970h+var_920], r15
0x1804310d6  mov     [rsp+970h+var_948], rax; unsigned int *
0x1804310db  mov     rdi, r8
0x1804310de  lea     rax, [rsp+970h+lpString]
0x1804310e3  mov     [rsp+970h+lpString], r15
0x1804310e8  mov     [rsp+970h+var_950], rax; unsigned int
0x1804310ed  mov     ebx, edx
0x1804310ef  mov     r14, rcx
0x1804310f2  mov     [rsp+970h+var_930], r15d
0x1804310f7  call    ?CommonDialogProc@ImpExpUserDlg@@CAKPEAUHWND__@@I_K_JPEAPEAVImpExpUserProcess@@PEAKAEAVReturnValue@@@Z; ImpExpUserDlg::CommonDialogProc(HWND__ *,uint,unsigned __int64,__int64,ImpExpUserProcess * *,ulong *,ReturnValue &)
0x1804310fc  test    eax, eax
0x1804310fe  jz      loc_18043173A
0x180431104  cmp     ebx, 4Eh ; 'N'
0x180431107  jz      loc_180431477
0x18043110d  cmp     ebx, 111h
0x180431113  jnz     loc_18043173A
0x180431119  mov     rax, rdi
0x18043111c  shr     rax, 10h
0x180431120  test    ax, ax
0x180431123  jnz     loc_18043173A
0x180431129  mov     eax, 4262h
0x18043112e  cmp     di, ax
0x180431131  jnz     loc_18043173A
0x180431137  mov     ebx, 98h
0x18043113c  lea     rcx, [rsp+970h+var_910]; void *
0x180431141  mov     r8d, ebx; Size
0x180431144  xor     edx, edx; Val
0x180431146  call    memset_0
0x18043114b  mov     rax, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstResources
0x180431152  mov     rdi, [rsp+970h+lpString]
0x180431157  mov     [rsp+970h+var_910.hInstance], rax
0x18043115c  lea     rax, [rbp+870h+var_450]
0x180431163  mov     [rsp+970h+var_910.lpstrFilter], rax
0x180431168  lea     rax, [rbp+870h+var_660]
0x18043116f  mov     [rbp+870h+var_910.lpstrFile], rax
0x180431173  lea     rax, [rbp+870h+String]
0x180431177  mov     [rbp+870h+var_910.lpstrInitialDir], rax
0x18043117b  lea     rax, [rbp+870h+Buffer]
0x180431182  mov     [rsp+970h+var_910.lStructSize], ebx
0x180431186  lea     ebx, [r15+1]
0x18043118a  mov     [rbp+870h+var_910.lpstrTitle], rax
0x18043118e  mov     [rsp+970h+var_910.hwndOwner], r14
0x180431193  mov     [rbp+870h+var_910.nFilterIndex], ebx
0x180431196  mov     [rbp+870h+var_910.lpstrCustomFilter], r15
0x18043119a  mov     [rbp+870h+var_910.nMaxFile], 208h
0x1804311a1  mov     [rbp+870h+var_910.lpstrFileTitle], r15
0x1804311a5  mov     ecx, [rdi+0C38h]
0x1804311ab  cmp     ecx, ebx
0x1804311ad  jnz     short loc_1804311B8
0x1804311af  lea     rax, aTxt_0; "txt"
0x1804311b6  jmp     short loc_1804311CD
0x1804311b8  cmp     ecx, 3
0x1804311bb  lea     rax, aOpml_0; "opml"
0x1804311c2  lea     rdx, aHtm_1; "htm"
0x1804311c9  cmovnz  rax, rdx
0x1804311cd  mov     esi, 104h
0x1804311d2  mov     [rbp+870h+var_910.lpstrDefExt], rax
0x1804311d6  mov     r9d, esi; cchMax
0x1804311d9  lea     r8, [rbp+870h+String]; lpString
0x1804311dd  mov     edx, 4275h; nIDDlgItem
0x1804311e2  mov     rcx, r14; hDlg
0x1804311e5  call    cs:__imp_GetDlgItemTextW
0x1804311ec  nop     dword ptr [rax+rax+00h]
0x1804311f1  lea     rcx, [rbp+870h+String]; pszPath
0x1804311f5  mov     [rbp+870h+var_660], r15w
0x1804311fd  call    cs:__imp_PathIsDirectoryW
0x180431204  nop     dword ptr [rax+rax+00h]
0x180431209  test    eax, eax
0x18043120b  jz      short loc_180431222
0x18043120d  lea     rax, [rbp+870h+String]
0x180431211  mov     [rbp+870h+var_660], r15w
0x180431219  mov     [rbp+870h+var_910.lpstrInitialDir], rax
0x18043121d  jmp     loc_1804312B2
0x180431222  lea     rcx, [rbp+870h+String]; pszPath
0x180431226  call    cs:__imp_PathFindFileNameW
0x18043122d  nop     dword ptr [rax+rax+00h]
0x180431232  lea     rcx, [rbp+870h+String]
0x180431236  cmp     rax, rcx
0x180431239  jz      short loc_180431261
0x18043123b  test    rax, rax
0x18043123e  jz      short loc_180431261
0x180431240  lea     rcx, [rbp+870h+String]
0x180431244  mov     [rax-2], r15w
0x180431249  mov     [rbp+870h+var_910.lpstrInitialDir], rcx
0x18043124d  mov     r8, rax; unsigned __int16 *
0x180431250  lea     rcx, [rbp+870h+var_660]; unsigned __int16 *
0x180431257  mov     rdx, rsi; unsigned __int64
0x18043125a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18043125f  jmp     short loc_1804312B2
0x180431261  lea     rcx, [rbp+870h+String]; pszPath
0x180431265  call    cs:__imp_PathIsFileSpecW
0x18043126c  nop     dword ptr [rax+rax+00h]
0x180431271  test    eax, eax
0x180431273  jz      short loc_18043128A
0x180431275  lea     r8, [rbp+870h+String]; unsigned __int16 *
0x180431279  mov     rdx, rsi; unsigned __int64
0x18043127c  lea     rcx, [rbp+870h+var_660]; unsigned __int16 *
0x180431283  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180431288  jmp     short loc_180431292
0x18043128a  mov     [rbp+870h+var_660], r15w
0x180431292  lea     rax, [rbp+870h+String]
0x180431296  xor     r9d, r9d; fCreate
0x180431299  xor     r8d, r8d; csidl
0x18043129c  mov     [rbp+870h+var_910.lpstrInitialDir], rax
0x1804312a0  lea     rdx, [rbp+870h+String]; pszPath
0x1804312a4  xor     ecx, ecx; hwnd
0x1804312a6  call    cs:__imp_SHGetSpecialFolderPathW
0x1804312ad  nop     dword ptr [rax+rax+00h]
0x1804312b2  mov     eax, [rdi+0C38h]
0x1804312b8  cmp     eax, 2
0x1804312bb  jnz     short loc_1804312E6
0x1804312bd  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x1804312c4  lea     r8, [rbp+870h+Buffer]; lpBuffer
0x1804312cb  mov     r9d, esi; cchBufferMax
0x1804312ce  mov     edx, 4221h; uID
0x1804312d3  call    cs:__imp_LoadStringW
0x1804312da  nop     dword ptr [rax+rax+00h]
0x1804312df  mov     edx, 4223h
0x1804312e4  jmp     short loc_18043133F
0x1804312e6  cmp     eax, 3
0x1804312e9  jnz     short loc_180431314
0x1804312eb  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x1804312f2  lea     r8, [rbp+870h+Buffer]; lpBuffer
0x1804312f9  mov     r9d, esi; cchBufferMax
0x1804312fc  mov     edx, 4230h; uID
0x180431301  call    cs:__imp_LoadStringW
0x180431308  nop     dword ptr [rax+rax+00h]
0x18043130d  mov     edx, 4231h
0x180431312  jmp     short loc_18043133F
0x180431314  cmp     eax, ebx
0x180431316  jnz     short loc_18043135C
0x180431318  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x18043131f  lea     r8, [rbp+870h+Buffer]; lpBuffer
0x180431326  mov     r9d, esi; cchBufferMax
0x180431329  mov     edx, 4222h; uID
0x18043132e  call    cs:__imp_LoadStringW
0x180431335  nop     dword ptr [rax+rax+00h]
0x18043133a  mov     edx, 4224h; uID
0x18043133f  mov     rcx, cs:?g_hInstResources@@3PEAUHINSTANCE__@@EA; hInstance
0x180431346  lea     r8, [rbp+870h+var_450]; lpBuffer
0x18043134d  mov     r9d, esi; cchBufferMax
0x180431350  call    cs:__imp_LoadStringW
0x180431357  nop     dword ptr [rax+rax+00h]
0x18043135c  mov     ecx, r15d
0x18043135f  cmp     ecx, esi
0x180431361  jnb     short loc_180431399
0x180431363  movsxd  rax, ecx
0x180431366  lea     rdx, [rax+rax]
0x18043136a  movzx   eax, [rbp+rdx+870h+var_450]
0x180431372  test    ax, ax
0x180431375  jz      short loc_180431399
0x180431377  cmp     ax, 40h ; '@'
0x18043137b  jnz     short loc_18043138F
0x18043137d  cmp     rdx, 208h
0x180431384  jnb     short loc_180431393
0x180431386  mov     [rbp+rdx+870h+var_450], r15w
0x18043138f  add     ecx, ebx
0x180431391  jmp     short loc_18043135F
0x180431393  call    __report_rangecheckfailure
0x180431399  mov     eax, 90004h
0x18043139e  mov     ecx, 91804h
0x1804313a3  mov     [rbp+870h+var_910.Flags], eax
0x1804313a6  cmp     [rdi+0C3Ch], ebx
0x1804313ac  cmovz   eax, ecx
0x1804313af  mov     [rbp+870h+var_910.Flags], eax
0x1804313b2  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x1804313b9  nop     dword ptr [rax+rax+00h]
0x1804313be  test    al, al
0x1804313c0  jz      short loc_1804313C7
0x1804313c2  bts     [rbp+870h+var_910.Flags], 19h
0x1804313c7  lea     rcx, [rsp+970h+var_910]; LPOPENFILENAMEW
0x1804313cc  cmp     [rdi+0C3Ch], ebx
0x1804313d2  jnz     short loc_1804313DB
0x1804313d4  call    GetOpenFileNameW
0x1804313d9  jmp     short loc_1804313E0
0x1804313db  call    GetSaveFileNameW
0x1804313e0  test    eax, eax
0x1804313e2  jz      loc_18043173F
0x1804313e8  mov     edx, 4275h; nIDDlgItem
0x1804313ed  mov     rcx, r14; hDlg
0x1804313f0  call    cs:__imp_GetDlgItem
0x1804313f7  nop     dword ptr [rax+rax+00h]
0x1804313fc  mov     rdx, [rbp+870h+var_910.lpstrFile]; lpString
0x180431400  mov     rcx, rax; hWnd
0x180431403  call    cs:__imp_SetWindowTextW
0x18043140a  nop     dword ptr [rax+rax+00h]
0x18043140f  test    eax, eax
0x180431411  jz      loc_18043173F
0x180431417  mov     edx, 4287h; nIDDlgItem
0x18043141c  mov     rcx, r14; hDlg
0x18043141f  call    cs:__imp_GetDlgItem
0x180431426  nop     dword ptr [rax+rax+00h]
0x18043142b  mov     edi, 0F1h
0x180431430  xor     r9d, r9d; lParam
0x180431433  mov     rcx, rax; hWnd
0x180431436  mov     edx, edi; Msg
0x180431438  mov     r8, rbx; wParam
0x18043143b  call    cs:__imp_SendMessageW
0x180431442  nop     dword ptr [rax+rax+00h]
0x180431447  mov     edx, 4276h; nIDDlgItem
0x18043144c  mov     rcx, r14; hDlg
0x18043144f  call    cs:__imp_GetDlgItem
0x180431456  nop     dword ptr [rax+rax+00h]
0x18043145b  xor     r9d, r9d; lParam
0x18043145e  xor     r8d, r8d; wParam
0x180431461  mov     rcx, rax; hWnd
0x180431464  mov     edx, edi; Msg
0x180431466  call    cs:__imp_SendMessageW
0x18043146d  nop     dword ptr [rax+rax+00h]
0x180431472  jmp     loc_18043173F
0x180431477  cmp     dword ptr [rsi+10h], 0FFFFFF2Fh
0x18043147e  jz      loc_18043172E
0x180431484  cmp     dword ptr [rsi+10h], 0FFFFFF31h
0x18043148b  jz      loc_180431548
0x180431491  cmp     dword ptr [rsi+10h], 0FFFFFF38h
0x180431498  jnz     loc_18043173A
0x18043149e  mov     eax, [rsp+970h+var_930]
0x1804314a2  mov     esi, 104h
0x1804314a7  mov     rdi, [rsp+970h+lpString]
0x1804314ac  mov     ebx, 1
0x1804314b1  mov     [rsp+970h+var_918], esi
0x1804314b5  cmp     eax, 4266h
0x1804314ba  jz      short loc_1804314E5
0x1804314bc  cmp     eax, 4269h
0x1804314c1  jz      short loc_1804314E5
0x1804314c3  cmp     eax, 4382h
0x1804314c8  jz      short loc_1804314DE
0x1804314ca  cmp     eax, 4489h
0x1804314cf  jz      short loc_1804314DE
0x1804314d1  add     eax, 0FFFFBD90h
0x1804314d6  cmp     eax, ebx
0x1804314d8  ja      short loc_1804314F2
0x1804314da  mov     edx, ebx
0x1804314dc  jmp     short loc_1804314EA
0x1804314de  mov     edx, 3
0x1804314e3  jmp     short loc_1804314EA
0x1804314e5  mov     edx, 2
0x1804314ea  mov     rcx, rdi
0x1804314ed  call    ?SelectExternalType@ImpExpUserProcess@@QEAAXW4ExternalType@@@Z; ImpExpUserProcess::SelectExternalType(ExternalType)
0x1804314f2  lea     r8, [rsp+970h+var_918]; unsigned int *
0x1804314f7  mov     rcx, rdi; this
0x1804314fa  lea     rdx, [rbp+870h+Buffer]; unsigned __int16 *
0x180431501  call    ?GetExternalManualDefault@ImpExpUserProcess@@QEAAHPEAGPEAK@Z; ImpExpUserProcess::GetExternalManualDefault(ushort *,ulong *)
0x180431506  test    eax, eax
0x180431508  jz      short loc_180431525
0x18043150a  lea     r8, [rbp+870h+Buffer]; lpString
0x180431511  mov     edx, 4275h; nIDDlgItem
0x180431516  mov     rcx, r14; hDlg
0x180431519  call    cs:__imp_SetDlgItemTextW
0x180431520  nop     dword ptr [rax+rax+00h]
0x180431525  mov     edx, 4275h; nIDDlgItem
0x18043152a  mov     rcx, r14; hDlg
0x18043152d  call    cs:__imp_GetDlgItem
0x180431534  nop     dword ptr [rax+rax+00h]
0x180431539  mov     rcx, rax; HWND
0x18043153c  mov     edx, ebx; unsigned int
0x18043153e  call    ?IESHAutoComplete@@YAJPEAUHWND__@@K@Z; IESHAutoComplete(HWND__ *,ulong)
0x180431543  jmp     loc_18043173A
0x180431548  mov     rdi, [rsp+970h+lpString]
0x18043154d  mov     esi, 104h
0x180431552  mov     r9d, esi; cchMax
0x180431555  mov     r8, rdi; lpString
0x180431558  mov     edx, 4275h; nIDDlgItem
0x18043155d  mov     rcx, r14; hDlg
0x180431560  mov     ebx, 1
0x180431565  call    cs:__imp_GetDlgItemTextW
0x18043156c  nop     dword ptr [rax+rax+00h]
0x180431571  mov     eax, [rsp+970h+var_930]
0x180431575  cmp     eax, 4266h
0x18043157a  jz      short loc_1804315BE
0x18043157c  cmp     eax, 4269h
0x180431581  jz      short loc_1804315BE
0x180431583  cmp     eax, 4382h
0x180431588  jz      short loc_1804315A3
0x18043158a  cmp     eax, 4489h
0x18043158f  jz      short loc_1804315A3
0x180431591  add     eax, 0FFFFBD90h
0x180431596  cmp     eax, ebx
0x180431598  ja      short loc_1804315D0
0x18043159a  lea     rcx, [rdi+618h]
0x1804315a1  jmp     short loc_1804315C5
0x1804315a3  lea     rcx, [rdi+820h]; unsigned __int16 *
0x1804315aa  mov     r8, rdi; unsigned __int16 *
0x1804315ad  mov     rdx, rsi; unsigned __int64
  ... truncated ...
```
