# CBody::TranslateUrl(ulong,ushort *,ushort * *)

- ea: `0x18007f2c0`
- end: `0x18007fa61`
- name: `?TranslateUrl@CBody@@UEAAJKPEAGPEAPEAG@Z`
- size: `1953`
- prototype: `__int64 __fastcall(CBody *this, unsigned int, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002098`
- `0x1800055bc`
- `0x180005748`
- `0x18000910c`
- `0x180021a14`
- `0x180021ccc`
- `0x180022784`
- `0x1800227b0`
- `0x1800737b4`
- `0x1800738d0`
- `0x18007f2c0`
- `0x18008e2f0`
- `0x1800cc9ba`
- `0x1800cca00`
- `0x1800cd010`

## import_xrefs

- `MSOERT2!PszAllocW` at `0x18007f662`
- `MSOERT2!PszAllocW` at `0x18007f7d3`
- `MSOERT2!PszAllocW` at `0x18007f662`
- `MSOERT2!PszAllocW` at `0x18007f7d3`
- `MSOERT2!CreateTempFileW` at `0x18007f5ef`
- `MSOERT2!CreateTempFileW` at `0x18007f73f`
- `MSOERT2!CreateTempFileW` at `0x18007f5ef`
- `MSOERT2!CreateTempFileW` at `0x18007f73f`
- `MSOERT2!AppendTempFileList` at `0x18007f80d`
- `MSOERT2!AppendTempFileList` at `0x18007f80d`
- `MSOERT2!WriteStreamToFileHandle` at `0x18007f60e`
- `MSOERT2!WriteStreamToFileHandle` at `0x18007f75e`
- `MSOERT2!WriteStreamToFileHandle` at `0x18007f60e`
- `MSOERT2!WriteStreamToFileHandle` at `0x18007f75e`
- `MSOERT2!ReplaceCharsW` at `0x18007f8ec`
- `MSOERT2!ReplaceCharsW` at `0x18007f8ec`
- `SHLWAPI!PathFindFileNameW` at `0x18007f9b3`
- `SHLWAPI!PathFindFileNameW` at `0x18007f9b3`
- `SHLWAPI!StrCmpIW` at `0x18007f95f`
- `SHLWAPI!StrCmpIW` at `0x18007f95f`
- `SHLWAPI!PathCreateFromUrlW` at `0x18007f722`
- `SHLWAPI!PathCreateFromUrlW` at `0x18007f722`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18007f434`
- `SHLWAPI!PathRemoveFileSpecW` at `0x18007f434`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18007f706`
- `SHLWAPI!__imp_StrCmpNICW` at `0x18007f706`
- `KERNEL32!RemoveDirectoryW` at `0x18007f443`
- `KERNEL32!RemoveDirectoryW` at `0x18007f443`
- `KERNEL32!DeleteFileW` at `0x18007f429`
- `KERNEL32!DeleteFileW` at `0x18007f429`
- `KERNEL32!CloseHandle` at `0x18007f410`
- `KERNEL32!CloseHandle` at `0x18007f822`
- `KERNEL32!CloseHandle` at `0x18007f410`
- `KERNEL32!CloseHandle` at `0x18007f822`
- `KERNEL32!CopyFileW` at `0x18007f9a3`
- `KERNEL32!CopyFileW` at `0x18007f9a3`
- `USER32!LoadStringW` at `0x18007f8d8`
- `USER32!LoadStringW` at `0x18007f928`
- `USER32!LoadStringW` at `0x18007f8d8`
- `USER32!LoadStringW` at `0x18007f928`
- `SHELL32!ShellExecuteExW` at `0x18007f9fa`
- `SHELL32!ShellExecuteExW` at `0x18007f9fa`

## pseudocode

```c
__int64 __fastcall CBody::TranslateUrl(CBody *this, unsigned int a2, unsigned __int16 *a3, unsigned __int16 **a4)
{
  const WCHAR *v8; // rsi
  __int64 v9; // r14
  __int64 v10; // rcx
  unsigned int v11; // edi
  int MhtmlPrefixW; // ebx
  __int64 v13; // r12
  int v14; // r13d
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 v19; // r12
  WCHAR *v20; // rcx
  __int64 v21; // rbx
  unsigned int v22; // ebx
  HWND v23; // rcx
  __int64 v24; // r8
  int v25; // eax
  HWND v26; // rax
  const WCHAR *v27; // rbx
  const WCHAR *FileNameW; // rax
  __int64 v29; // [rsp+40h] [rbp-C0h]
  LPCWSTR lpFileName[2]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  DWORD pcchPath; // [rsp+60h] [rbp-A0h] BYREF
  int v33; // [rsp+64h] [rbp-9Ch] BYREF
  __int64 v34; // [rsp+68h] [rbp-98h] BYREF
  __int64 v35; // [rsp+70h] [rbp-90h] BYREF
  LPCWSTR pszStr1; // [rsp+78h] [rbp-88h]
  __int64 v37; // [rsp+80h] [rbp-80h] BYREF
  __int64 v38; // [rsp+88h] [rbp-78h] BYREF
  __int64 v39; // [rsp+90h] [rbp-70h] BYREF
  __int128 v40; // [rsp+98h] [rbp-68h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h]
  struct tagOFNW v42; // [rsp+B0h] [rbp-50h] BYREF
  SHELLEXECUTEINFOW pExecInfo; // [rsp+150h] [rbp+50h] BYREF
  WCHAR psz2[264]; // [rsp+1C0h] [rbp+C0h] BYREF
  WCHAR Buffer[512]; // [rsp+3D0h] [rbp+2D0h] BYREF
  WCHAR v46[512]; // [rsp+7D0h] [rbp+6D0h] BYREF
  WCHAR pszPath[520]; // [rsp+BD0h] [rbp+AD0h] BYREF

  hObject = (HANDLE)-1LL;
  pszStr1 = 0;
  lpFileName[0] = 0;
  v29 = 0;
  v39 = 0;
  v38 = 0;
  v34 = 0;
  v35 = 0;
  v41 = 0;
  v33 = 0;
  v8 = 0;
  pcchPath = 0;
  v9 = 0;
  v40 = 0;
  memset_0(&pExecInfo, 0, sizeof(pExecInfo));
  v10 = *((_QWORD *)this + 20);
  v37 = 0;
  v11 = 1;
  if ( v10 )
  {
    MhtmlPrefixW = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int16 *, unsigned __int16 **))(*(_QWORD *)v10 + 128LL))(
                     v10,
                     a2,
                     a3,
                     a4);
    if ( MhtmlPrefixW != -2146691327 )
      goto LABEL_5;
  }
  if ( !a4 || (*a4 = 0, !a3) )
  {
    MhtmlPrefixW = -2147024809;
LABEL_5:
    v13 = 0;
    v14 = 0;
    goto LABEL_6;
  }
  if ( !*((_QWORD *)this + 13) || !*((_QWORD *)this + 14) || !(unsigned int)IsMHTMLUrlW(a3) )
  {
    MhtmlPrefixW = 1;
    goto LABEL_5;
  }
  v16 = MimeOleParseMhtmlUrlW(a3);
  v13 = 0;
  MhtmlPrefixW = v16;
  if ( v16 < 0
    || (MhtmlPrefixW = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 13))(
                         *((_QWORD *)this + 13),
                         &GUID_f90adfef_d01f_11d2_a004_00a0c90c9bb6,
                         &v37),
        MhtmlPrefixW < 0) )
  {
    v8 = pszStr1;
LABEL_78:
    v14 = 0;
    goto LABEL_6;
  }
  v8 = pszStr1;
  MhtmlPrefixW = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, LPCWSTR, _DWORD, __int64 *))(*(_QWORD *)v37 + 504LL))(
                   v37,
                   0,
                   0,
                   pszStr1,
                   0,
                   &v38);
  if ( MhtmlPrefixW < 0 )
    goto LABEL_78;
  MhtmlPrefixW = (*(__int64 (__fastcall **)(_QWORD, __int64, GUID *, __int64 *))(**((_QWORD **)this + 13) + 128LL))(
                   *((_QWORD *)this + 13),
                   v38,
                   &GUID_c558834c_7f86_11d0_8252_00c04fd85ab4,
                   &v34);
  if ( MhtmlPrefixW < 0 )
    goto LABEL_78;
  v14 = 1;
  if ( (*(unsigned int (__fastcall **)(__int64, const CHAR *, const CHAR *))(*(_QWORD *)v34 + 176LL))(
         v34,
         "text",
         "html") )
  {
    MhtmlPrefixW = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v34 + 288LL))(v34, 6, &v35);
    if ( MhtmlPrefixW < 0 )
      goto LABEL_6;
    pcchPath = 520;
    if ( StrCmpNICW(v8, L"cid:", 4) && PathCreateFromUrlW(v8, pszPath, &pcchPath, 0) >= 0 )
    {
      v20 = pszPath;
    }
    else
    {
      LOWORD(v40) = 31;
      MhtmlPrefixW = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v34 + 88LL))(
                       v34,
                       46,
                       0,
                       &v40);
      if ( MhtmlPrefixW < 0 )
        goto LABEL_6;
      v13 = *((_QWORD *)&v40 + 1);
      v29 = *((_QWORD *)&v40 + 1);
      v20 = (WCHAR *)*((_QWORD *)&v40 + 1);
    }
    MhtmlPrefixW = CreateTempFileW(v20, 0, lpFileName, &hObject);
    if ( MhtmlPrefixW >= 0 )
    {
      MhtmlPrefixW = WriteStreamToFileHandle(v35, hObject, &v33);
      if ( MhtmlPrefixW >= 0 )
      {
        if ( lpFileName[0] )
        {
          v21 = -1;
          do
            ++v21;
          while ( lpFileName[0][v21] );
        }
        else
        {
          LODWORD(v21) = 0;
        }
        v22 = v21 + 8;
        v9 = PszAllocW(v22);
        StringCchPrintfW((unsigned __int16 *)v9, v22, L"%s%s", L"file://", lpFileName[0]);
        goto LABEL_63;
      }
    }
  }
  else
  {
    MhtmlPrefixW = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(**((_QWORD **)this + 13) + 72LL))(
                     *((_QWORD *)this + 13),
                     &v35,
                     0);
    if ( MhtmlPrefixW >= 0 )
    {
      v17 = *((_QWORD *)this + 13);
      LOWORD(v40) = 31;
      MhtmlPrefixW = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, __int128 *))(*(_QWORD *)v17 + 312LL))(
                       v17,
                       46,
                       0,
                       &v40);
      if ( MhtmlPrefixW >= 0 )
      {
        v13 = *((_QWORD *)&v40 + 1);
        v29 = *((_QWORD *)&v40 + 1);
        MhtmlPrefixW = CreateTempFileW(*((_QWORD *)&v40 + 1), L".mhtml", lpFileName, &hObject);
        if ( MhtmlPrefixW >= 0 )
        {
          MhtmlPrefixW = WriteStreamToFileHandle(v35, hObject, &v33);
          if ( MhtmlPrefixW >= 0 )
          {
            if ( lpFileName[0] )
            {
              v9 = -1;
              do
                ++v9;
              while ( lpFileName[0][v9] );
            }
            if ( v8 )
            {
              v18 = -1;
              do
                ++v18;
              while ( v8[v18] );
            }
            else
            {
              LODWORD(v18) = 0;
            }
            v19 = (_DWORD)v9 + 9 + (unsigned int)v18 + (unsigned int)GetMhtmlPrefixLength();
            v9 = PszAllocW(v19);
            if ( !v9 )
            {
              MhtmlPrefixW = -2147024882;
LABEL_76:
              v13 = v29;
              goto LABEL_6;
            }
            MhtmlPrefixW = GetMhtmlPrefixW(&v39);
            if ( MhtmlPrefixW < 0 )
              goto LABEL_76;
            StringCchPrintfW(
              (unsigned __int16 *)v9,
              (unsigned int)v19,
              L"%s%s%s!%s",
              v39,
              L"file://",
              lpFileName[0],
              v8);
LABEL_63:
            MhtmlPrefixW = AppendTempFileList((char *)this + 136, lpFileName[0], 1);
            if ( MhtmlPrefixW >= 0 )
            {
              CloseHandle(hObject);
              hObject = (HANDLE)-1LL;
              v25 = IsSafeToRun(v23, lpFileName[0], v24, 0);
              MhtmlPrefixW = v25;
              if ( v25 >= 0 )
              {
                if ( v25 == 792400 )
                {
                  memset_0(&v42, 0, sizeof(v42));
                  psz2[0] = 0;
                  Buffer[0] = 0;
                  v46[0] = 0;
                  MhtmlPrefixW = StringCchCopyW(psz2, 0x104u, lpFileName[0]);
                  if ( MhtmlPrefixW >= 0 )
                  {
                    memset_0(&v42, 0, sizeof(v42));
                    v26 = (HWND)*((_QWORD *)this - 9);
                    v42.lStructSize = 152;
                    v42.hwndOwner = v26;
                    LoadStringW(g_hLocRes, 0x494u, Buffer, 512);
                    ReplaceCharsW(Buffer, 124);
                    v42.lpstrFilter = Buffer;
                    v42.nFilterIndex = 1;
                    v42.lpstrFile = psz2;
                    v42.nMaxFile = 520;
                    LoadStringW(g_hLocRes, 0x493u, v46, 512);
                    v42.Flags = 34830;
                    v42.lpstrTitle = v46;
                    if ( !(unsigned int)HrAthGetFileNameW(&v42) )
                    {
                      if ( StrCmpIW(lpFileName[0], psz2) )
                      {
                        CopyFileW(lpFileName[0], psz2, 0);
                      }
                      else if ( lpFileName[0] )
                      {
                        ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                        lpFileName[0] = 0;
                      }
                    }
                  }
                }
                else
                {
                  v27 = lpFileName[0];
                  FileNameW = PathFindFileNameW(lpFileName[0]);
                  MhtmlPrefixW = VerifyTrust(*((HWND *)this - 9), FileNameW, v27);
                  if ( MhtmlPrefixW >= 0 )
                  {
                    memset_0(&pExecInfo, 0, sizeof(pExecInfo));
                    pExecInfo.hwnd = (HWND)*((_QWORD *)this - 9);
                    pExecInfo.cbSize = 112;
                    pExecInfo.nShow = 1;
                    pExecInfo.lpFile = (LPCWSTR)v9;
                    ShellExecuteExW(&pExecInfo);
                    if ( lpFileName[0] )
                    {
                      ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
                      lpFileName[0] = 0;
                    }
                    MhtmlPrefixW = 0;
                  }
                }
              }
            }
            goto LABEL_76;
          }
        }
      }
    }
  }
LABEL_6:
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v34);
  OE_SafeReleaseAndNullPtr<IStream>(&v35);
  if ( v8 )
    ((void (__fastcall *)(LPMALLOC, const WCHAR *))g_pMalloc->lpVtbl->Free)(g_pMalloc, v8);
  if ( v13 )
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v13);
  if ( v9 )
    ((void (__fastcall *)(LPMALLOC, __int64))g_pMalloc->lpVtbl->Free)(g_pMalloc, v9);
  OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(&v37);
  if ( hObject != (HANDLE)-1LL )
  {
    CloseHandle(hObject);
    hObject = (HANDLE)-1LL;
  }
  if ( lpFileName[0] )
  {
    DeleteFileW(lpFileName[0]);
    if ( PathRemoveFileSpecW((LPWSTR)lpFileName[0]) )
      RemoveDirectoryW(lpFileName[0]);
    if ( lpFileName[0] )
      ((void (__fastcall *)(LPMALLOC))g_pMalloc->lpVtbl->Free)(g_pMalloc);
  }
  if ( MhtmlPrefixW < 0 )
    return (unsigned int)MhtmlPrefixW;
  if ( v14 == 1 )
    return (unsigned int)-2147467260;
  return v11;
}

```

## disassembly

```asm
0x18007f2c0  push    rbp
0x18007f2c2  push    rbx
0x18007f2c3  push    rsi
0x18007f2c4  push    rdi
0x18007f2c5  push    r12
0x18007f2c7  push    r13
0x18007f2c9  push    r14
0x18007f2cb  push    r15
0x18007f2cd  lea     rbp, [rsp-0EF8h]
0x18007f2d5  sub     rsp, 0FF8h
0x18007f2dc  mov     rax, cs:__security_cookie
0x18007f2e3  xor     rax, rsp
0x18007f2e6  mov     [rbp+0F30h+var_50], rax
0x18007f2ed  xor     edi, edi
0x18007f2ef  mov     [rsp+1030h+hObject], 0FFFFFFFFFFFFFFFFh
0x18007f2f8  mov     r12, r8
0x18007f2fb  mov     [rsp+1030h+pszStr1], rdi
0x18007f300  mov     ebx, edx
0x18007f302  mov     [rsp+1030h+lpFileName], rdi
0x18007f307  mov     r15, rcx
0x18007f30a  mov     [rsp+1030h+var_FF0], rdi
0x18007f30f  xorps   xmm0, xmm0
0x18007f312  mov     [rbp+0F30h+var_FA0], rdi
0x18007f316  xor     eax, eax
0x18007f318  mov     [rbp+0F30h+var_FA8], rdi
0x18007f31c  lea     r8d, [rdi+70h]; Size
0x18007f320  mov     [rsp+1030h+var_FC8], rdi
0x18007f325  xor     edx, edx; Val
0x18007f327  mov     [rsp+1030h+var_FC0], rdi
0x18007f32c  lea     rcx, [rbp+0F30h+pExecInfo]; void *
0x18007f330  mov     [rbp+0F30h+var_F88], rax
0x18007f334  mov     r13, r9
0x18007f337  mov     [rsp+1030h+var_FCC], edi
0x18007f33b  mov     esi, edi
0x18007f33d  mov     [rsp+1030h+pcchPath], edi
0x18007f341  mov     r14d, edi
0x18007f344  movups  [rbp+0F30h+var_F98], xmm0
0x18007f348  call    memset_0
0x18007f34d  mov     rcx, [r15+0A0h]
0x18007f354  mov     [rbp+0F30h+var_FB0], rdi
0x18007f358  lea     edi, [r14+1]
0x18007f35c  test    rcx, rcx
0x18007f35f  jz      short loc_18007F381
0x18007f361  mov     rax, [rcx]
0x18007f364  mov     r9, r13
0x18007f367  mov     r8, r12
0x18007f36a  mov     edx, ebx
0x18007f36c  mov     rax, [rax+80h]
0x18007f373  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f378  mov     ebx, eax
0x18007f37a  cmp     eax, 800C1701h
0x18007f37f  jnz     short loc_18007F391
0x18007f381  xor     ebx, ebx
0x18007f383  test    r13, r13
0x18007f386  jnz     loc_18007F480
0x18007f38c  mov     ebx, 80070057h
0x18007f391  mov     r12, rsi
0x18007f394  mov     r13d, esi
0x18007f397  lea     rcx, [rsp+1030h+var_FC8]
0x18007f39c  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007f3a1  lea     rcx, [rsp+1030h+var_FC0]
0x18007f3a6  call    ??$OE_SafeReleaseAndNullPtr@UIStream@@@@YAXAEAPEAUIStream@@@Z; OE_SafeReleaseAndNullPtr<IStream>(IStream * &)
0x18007f3ab  test    rsi, rsi
0x18007f3ae  jz      short loc_18007F3C6
0x18007f3b0  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007f3b7  mov     rdx, rsi
0x18007f3ba  mov     rax, [rcx]
0x18007f3bd  mov     rax, [rax+28h]
0x18007f3c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3c6  test    r12, r12
0x18007f3c9  jz      short loc_18007F3E1
0x18007f3cb  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007f3d2  mov     rdx, r12
0x18007f3d5  mov     rax, [rcx]
0x18007f3d8  mov     rax, [rax+28h]
0x18007f3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3e1  test    r14, r14
0x18007f3e4  jz      short loc_18007F3FC
0x18007f3e6  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007f3ed  mov     rdx, r14
0x18007f3f0  mov     rax, [rcx]
0x18007f3f3  mov     rax, [rax+28h]
0x18007f3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f3fc  lea     rcx, [rbp+0F30h+var_FB0]
0x18007f400  call    ??$OE_SafeReleaseAndNullPtr@UIOleInPlaceActiveObject@@@@YAXAEAPEAUIOleInPlaceActiveObject@@@Z; OE_SafeReleaseAndNullPtr<IOleInPlaceActiveObject>(IOleInPlaceActiveObject * &)
0x18007f405  mov     rcx, [rsp+1030h+hObject]; hObject
0x18007f40a  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18007f40e  jz      short loc_18007F41F
0x18007f410  call    cs:__imp_CloseHandle
0x18007f416  mov     [rsp+1030h+hObject], 0FFFFFFFFFFFFFFFFh
0x18007f41f  mov     rcx, [rsp+1030h+lpFileName]; lpFileName
0x18007f424  test    rcx, rcx
0x18007f427  jz      short loc_18007F466
0x18007f429  call    cs:__imp_DeleteFileW
0x18007f42f  mov     rcx, [rsp+1030h+lpFileName]; pszPath
0x18007f434  call    cs:__imp_PathRemoveFileSpecW
0x18007f43a  test    eax, eax
0x18007f43c  jz      short loc_18007F449
0x18007f43e  mov     rcx, [rsp+1030h+lpFileName]; lpPathName
0x18007f443  call    cs:__imp_RemoveDirectoryW
0x18007f449  mov     rdx, [rsp+1030h+lpFileName]
0x18007f44e  test    rdx, rdx
0x18007f451  jz      short loc_18007F466
0x18007f453  mov     rcx, cs:?g_pMalloc@@3PEAUIMalloc@@EA; IMalloc * g_pMalloc
0x18007f45a  mov     rax, [rcx]
0x18007f45d  mov     rax, [rax+28h]
0x18007f461  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f466  test    ebx, ebx
0x18007f468  js      loc_18007FA3C
0x18007f46e  mov     eax, 80004004h
0x18007f473  cmp     r13d, edi
0x18007f476  cmovz   edi, eax
0x18007f479  mov     eax, edi
0x18007f47b  jmp     loc_18007FA3E
0x18007f480  mov     [r13+0], rbx
0x18007f484  test    r12, r12
0x18007f487  jz      loc_18007F38C
0x18007f48d  cmp     [r15+68h], rbx
0x18007f491  jz      short loc_18007F4A5
0x18007f493  cmp     [r15+70h], rbx
0x18007f497  jz      short loc_18007F4A5
0x18007f499  mov     rcx, r12; psz1
0x18007f49c  call    ?IsMHTMLUrlW@@YAHPEBG@Z; IsMHTMLUrlW(ushort const *)
0x18007f4a1  test    eax, eax
0x18007f4a3  jnz     short loc_18007F4AC
0x18007f4a5  mov     ebx, edi
0x18007f4a7  jmp     loc_18007F391
0x18007f4ac  lea     r8, [rsp+1030h+pszStr1]
0x18007f4b1  xor     edx, edx
0x18007f4b3  mov     rcx, r12; psz1
0x18007f4b6  call    MimeOleParseMhtmlUrlW
0x18007f4bb  xor     r12d, r12d
0x18007f4be  mov     ebx, eax
0x18007f4c0  test    eax, eax
0x18007f4c2  js      loc_18007FA2F
0x18007f4c8  mov     rcx, [r15+68h]
0x18007f4cc  lea     r8, [rbp+0F30h+var_FB0]
0x18007f4d0  lea     rdx, _GUID_f90adfef_d01f_11d2_a004_00a0c90c9bb6
0x18007f4d7  mov     rax, [rcx]
0x18007f4da  mov     rax, [rax]
0x18007f4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f4e2  mov     ebx, eax
0x18007f4e4  test    eax, eax
0x18007f4e6  js      loc_18007FA2F
0x18007f4ec  mov     rcx, [rbp+0F30h+var_FB0]
0x18007f4f0  lea     rdx, [rbp+0F30h+var_FA8]
0x18007f4f4  mov     rsi, [rsp+1030h+pszStr1]
0x18007f4f9  xor     r8d, r8d
0x18007f4fc  mov     [rsp+1030h+var_1008], rdx
0x18007f501  mov     r9, rsi
0x18007f504  xor     edx, edx
0x18007f506  mov     [rsp+1030h+var_1010], r12d
0x18007f50b  mov     rax, [rcx]
0x18007f50e  mov     rax, [rax+1F8h]
0x18007f515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f51a  mov     ebx, eax
0x18007f51c  test    eax, eax
0x18007f51e  js      loc_18007FA34
0x18007f524  mov     rcx, [r15+68h]
0x18007f528  lea     r9, [rsp+1030h+var_FC8]
0x18007f52d  mov     rdx, [rbp+0F30h+var_FA8]
0x18007f531  lea     r8, _GUID_c558834c_7f86_11d0_8252_00c04fd85ab4
0x18007f538  mov     rax, [rcx]
0x18007f53b  mov     rax, [rax+80h]
0x18007f542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f547  mov     ebx, eax
0x18007f549  test    eax, eax
0x18007f54b  js      loc_18007FA34
0x18007f551  mov     rcx, [rsp+1030h+var_FC8]
0x18007f556  lea     r8, STR_SUB_HTML; "html"
0x18007f55d  lea     rdx, STR_CNT_TEXT; "text"
0x18007f564  mov     r13d, edi
0x18007f567  mov     rax, [rcx]
0x18007f56a  mov     rax, [rax+0B0h]
0x18007f571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f576  test    eax, eax
0x18007f578  jnz     loc_18007F6C6
0x18007f57e  mov     rcx, [r15+68h]
0x18007f582  lea     rdx, [rsp+1030h+var_FC0]
0x18007f587  xor     r8d, r8d
0x18007f58a  mov     rax, [rcx]
0x18007f58d  mov     rax, [rax+48h]
0x18007f591  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f596  mov     ebx, eax
0x18007f598  test    eax, eax
0x18007f59a  js      loc_18007F397
0x18007f5a0  mov     rcx, [r15+68h]
0x18007f5a4  lea     eax, [r12+1Fh]
0x18007f5a9  mov     word ptr [rbp+0F30h+var_F98], ax
0x18007f5ad  lea     r9, [rbp+0F30h+var_F98]
0x18007f5b1  xor     r8d, r8d
0x18007f5b4  lea     edx, [r12+2Eh]
0x18007f5b9  mov     rax, [rcx]
0x18007f5bc  mov     rax, [rax+138h]
0x18007f5c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f5c8  mov     ebx, eax
0x18007f5ca  test    eax, eax
0x18007f5cc  js      loc_18007F397
0x18007f5d2  mov     r12, qword ptr [rbp+0F30h+var_F98+8]
0x18007f5d6  lea     r9, [rsp+1030h+hObject]
0x18007f5db  mov     rcx, r12
0x18007f5de  mov     [rsp+1030h+var_FF0], r12
0x18007f5e3  lea     r8, [rsp+1030h+lpFileName]
0x18007f5e8  lea     rdx, c_wszMHTMLExt; ".mhtml"
0x18007f5ef  call    cs:__imp_CreateTempFileW
0x18007f5f5  mov     ebx, eax
0x18007f5f7  test    eax, eax
0x18007f5f9  js      loc_18007F397
0x18007f5ff  mov     rdx, [rsp+1030h+hObject]
0x18007f604  lea     r8, [rsp+1030h+var_FCC]
0x18007f609  mov     rcx, [rsp+1030h+var_FC0]
0x18007f60e  call    cs:__imp_WriteStreamToFileHandle
0x18007f614  xor     ecx, ecx
0x18007f616  mov     ebx, eax
0x18007f618  test    eax, eax
0x18007f61a  js      loc_18007F397
0x18007f620  mov     rax, [rsp+1030h+lpFileName]
0x18007f625  test    rax, rax
0x18007f628  jz      short loc_18007F638
0x18007f62a  or      r14, 0FFFFFFFFFFFFFFFFh
0x18007f62e  inc     r14
0x18007f631  cmp     [rax+r14*2], cx
0x18007f636  jnz     short loc_18007F62E
0x18007f638  test    rsi, rsi
0x18007f63b  jz      short loc_18007F64C
0x18007f63d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18007f641  inc     rbx
0x18007f644  cmp     [rsi+rbx*2], cx
0x18007f648  jnz     short loc_18007F641
0x18007f64a  jmp     short loc_18007F64F
0x18007f64c  mov     rbx, rcx
0x18007f64f  call    ?GetMhtmlPrefixLength@@YA_KXZ; GetMhtmlPrefixLength(void)
0x18007f654  add     r14d, 9
0x18007f658  lea     r12d, [rbx+rax]
0x18007f65c  add     r12d, r14d
0x18007f65f  mov     ecx, r12d
0x18007f662  call    cs:__imp_PszAllocW
0x18007f668  mov     r14, rax
0x18007f66b  test    rax, rax
0x18007f66e  jnz     short loc_18007F67A
0x18007f670  mov     ebx, 8007000Eh
0x18007f675  jmp     loc_18007FA25
0x18007f67a  lea     rcx, [rbp+0F30h+var_FA0]
0x18007f67e  call    GetMhtmlPrefixW
0x18007f683  mov     ebx, eax
0x18007f685  test    eax, eax
0x18007f687  js      loc_18007FA25
0x18007f68d  mov     rax, [rsp+1030h+lpFileName]
0x18007f692  lea     r9, c_wszFileUrl; "file://"
0x18007f699  mov     [rsp+1030h+var_1000], rsi
0x18007f69e  lea     r8, aSSSS; "%s%s%s!%s"
0x18007f6a5  mov     [rsp+1030h+var_1008], rax
0x18007f6aa  mov     rcx, r14; unsigned __int16 *
0x18007f6ad  mov     qword ptr [rsp+1030h+var_1010], r9
0x18007f6b2  mov     r9, [rbp+0F30h+var_FA0]
0x18007f6b6  mov     edx, r12d; unsigned __int64
0x18007f6b9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18007f6be  xor     r12d, r12d
0x18007f6c1  jmp     loc_18007F7FE
0x18007f6c6  mov     rcx, [rsp+1030h+var_FC8]
0x18007f6cb  lea     r8, [rsp+1030h+var_FC0]
0x18007f6d0  mov     edx, 6
0x18007f6d5  mov     rax, [rcx]
0x18007f6d8  mov     rax, [rax+120h]
0x18007f6df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007f6e4  mov     ebx, eax
0x18007f6e6  test    eax, eax
0x18007f6e8  js      loc_18007F397
0x18007f6ee  mov     r8d, 4; nChar
0x18007f6f4  mov     [rsp+1030h+pcchPath], 208h
0x18007f6fc  lea     rdx, aCid_0; "cid:"
0x18007f703  mov     rcx, rsi; pszStr1
0x18007f706  call    cs:__imp_StrCmpNICW
0x18007f70c  test    eax, eax
0x18007f70e  jz      short loc_18007F78B
0x18007f710  xor     r9d, r9d; dwFlags
0x18007f713  lea     r8, [rsp+1030h+pcchPath]; pcchPath
0x18007f718  lea     rdx, [rbp+0F30h+pszPath]; pszPath
0x18007f71f  mov     rcx, rsi; pszUrl
0x18007f722  call    cs:__imp_PathCreateFromUrlW
0x18007f728  test    eax, eax
0x18007f72a  js      short loc_18007F78B
0x18007f72c  lea     rcx, [rbp+0F30h+pszPath]
0x18007f733  lea     r9, [rsp+1030h+hObject]
0x18007f738  xor     edx, edx
0x18007f73a  lea     r8, [rsp+1030h+lpFileName]
0x18007f73f  call    cs:__imp_CreateTempFileW
0x18007f745  mov     ebx, eax
0x18007f747  test    eax, eax
0x18007f749  js      loc_18007F397
0x18007f74f  mov     rdx, [rsp+1030h+hObject]
0x18007f754  lea     r8, [rsp+1030h+var_FCC]
0x18007f759  mov     rcx, [rsp+1030h+var_FC0]
0x18007f75e  call    cs:__imp_WriteStreamToFileHandle
0x18007f764  mov     ebx, eax
0x18007f766  test    eax, eax
0x18007f768  js      loc_18007F397
0x18007f76e  mov     rax, [rsp+1030h+lpFileName]
0x18007f773  xor     r12d, r12d
0x18007f776  test    rax, rax
  ... truncated ...
```
