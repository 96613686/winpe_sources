# CVSSDeletingWriter::DeleteFilesFromSnapshot(IVssWMFiledesc *)

- ea: `0x18014626c`
- end: `0x180146553`
- name: `?DeleteFilesFromSnapshot@CVSSDeletingWriter@@AEAAXPEAVIVssWMFiledesc@@@Z`
- size: `743`
- prototype: `void __fastcall(CVSSDeletingWriter *__hidden this, struct IVssWMFiledesc *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path`

## callers

- `0x18014655c`

## callees

- `0x18000c4cc`
- `0x180082390`
- `0x1801244c0`
- `0x18012540e`
- `0x18014626c`
- `0x180241010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180146381`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180146381`
- `OLEAUT32!__imp_SysFreeString` at `0x18014651b`
- `OLEAUT32!__imp_SysFreeString` at `0x180146527`
- `OLEAUT32!__imp_SysFreeString` at `0x18014651b`
- `OLEAUT32!__imp_SysFreeString` at `0x180146527`
- `OLEAUT32!__imp_SysStringLen` at `0x1801462d4`
- `OLEAUT32!__imp_SysStringLen` at `0x18014634c`
- `OLEAUT32!__imp_SysStringLen` at `0x1801462d4`
- `OLEAUT32!__imp_SysStringLen` at `0x18014634c`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180146339`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180146339`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18014650f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18014650f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180146502`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180146502`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801464f4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1801464f4`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801464ad`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1801464ad`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801463a0`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x1801463a0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CVSSDeletingWriter::DeleteFilesFromSnapshot(CVSSDeletingWriter *this, struct IVssWMFiledesc *a2)
{
  int v4; // eax
  __int64 v5; // rcx
  UINT v6; // eax
  unsigned __int64 v7; // r8
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rax
  HANDLE FirstFileW; // rbx
  BSTR pbstr; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v14; // [rsp+40h] [rbp-C0h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  wchar_t v16[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR FileName[264]; // [rsp+6C0h] [rbp+5C0h] BYREF
  WCHAR szVolumeName[264]; // [rsp+8D0h] [rbp+7D0h] BYREF

  pbstr = 0;
  bstrString = 0;
  v4 = (*(__int64 (__fastcall **)(struct IVssWMFiledesc *, BSTR *))(*(_QWORD *)a2 + 24LL))(a2, &pbstr);
  if ( v4 >= 0 && v4 != 1 )
  {
    if ( SysStringLen(pbstr) )
    {
      v5 = *((_QWORD *)this + 1);
      if ( v5 )
      {
        if ( (*(unsigned __int8 (__fastcall **)(__int64, BSTR))(*(_QWORD *)v5 + 104LL))(v5, pbstr) )
        {
          if ( (*(int (__fastcall **)(struct IVssWMFiledesc *, BSTR *))(*(_QWORD *)a2 + 32LL))(a2, &bstrString) >= 0 )
          {
            if ( GetVolumePathNameW(pbstr, szVolumePathName, 0x104u) )
            {
              v6 = SysStringLen(pbstr);
              v7 = -1;
              do
                ++v7;
              while ( szVolumePathName[v7] );
              if ( v7 <= v6 && !(unsigned int)_o__wcsnicmp(pbstr, szVolumePathName, v7) )
              {
                if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, szVolumeName, 0x104u) )
                {
                  v14 = 0;
                  v8 = *((_QWORD *)this + 1);
                  if ( v8 )
                  {
                    if ( (*(int (__fastcall **)(__int64, WCHAR *, __int64 *))(*(_QWORD *)v8 + 72LL))(
                           v8,
                           szVolumeName,
                           &v14) >= 0 )
                    {
                      v9 = -1;
                      do
                        ++v9;
                      while ( szVolumePathName[v9] );
                      if ( (int)StringCchPrintfW(v16, 0x104u, L"%s\\%s", v14, &pbstr[v9]) >= 0 )
                      {
                        v10 = -1;
                        do
                          ++v10;
                        while ( v16[v10] );
                        if ( (FindFileData.cAlternateFileName[v10 + 13] == 92
                           || (int)StringCchCatW(v16, 0x104u, L"\\") >= 0)
                          && (int)StringCchPrintfW(FileName, 0x104u, L"%s%s", v16, bstrString) >= 0 )
                        {
                          memset_0(&FindFileData, 0, sizeof(FindFileData));
                          FirstFileW = FindFirstFileW(FileName, &FindFileData);
                          if ( FirstFileW != (HANDLE)-1LL )
                          {
                            do
                            {
                              if ( (FindFileData.dwFileAttributes & 0x10) == 0
                                && (int)StringCchPrintfW(FileName, 0x104u, L"%s%s", v16, FindFileData.cFileName) >= 0 )
                              {
                                DeleteFileW(FileName);
                              }
                            }
                            while ( FindNextFileW(FirstFileW, &FindFileData) );
                            FindClose(FirstFileW);
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  SysFreeString(bstrString);
  SysFreeString(pbstr);
}

```

## disassembly

```asm
0x18014626c  mov     [rsp-8+arg_10], rbx
0x180146271  push    rbp
0x180146272  push    rsi
0x180146273  push    rdi
0x180146274  push    r14
0x180146276  push    r15
0x180146278  lea     rbp, [rsp-9F0h]
0x180146280  sub     rsp, 0AF0h
0x180146287  mov     rax, cs:__security_cookie
0x18014628e  xor     rax, rsp
0x180146291  mov     [rbp+0A10h+var_30], rax
0x180146298  mov     rbx, rdx
0x18014629b  mov     rdi, rcx
0x18014629e  xor     esi, esi
0x1801462a0  mov     [rsp+0B10h+pbstr], rsi
0x1801462a5  mov     [rsp+0B10h+bstrString], rsi
0x1801462aa  mov     rax, [rdx]
0x1801462ad  lea     rdx, [rsp+0B10h+pbstr]
0x1801462b2  mov     rcx, rbx
0x1801462b5  mov     rax, [rax+18h]
0x1801462b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801462be  test    eax, eax
0x1801462c0  js      loc_180146516
0x1801462c6  cmp     eax, 1
0x1801462c9  jz      loc_180146516
0x1801462cf  mov     rcx, [rsp+0B10h+pbstr]; pbstr
0x1801462d4  call    cs:__imp_SysStringLen
0x1801462da  test    eax, eax
0x1801462dc  jz      loc_180146516
0x1801462e2  mov     rcx, [rdi+8]
0x1801462e6  test    rcx, rcx
0x1801462e9  jz      loc_180146516
0x1801462ef  mov     rax, [rcx]
0x1801462f2  mov     rdx, [rsp+0B10h+pbstr]
0x1801462f7  mov     rax, [rax+68h]
0x1801462fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180146300  test    al, al
0x180146302  jz      loc_180146516
0x180146308  mov     rax, [rbx]
0x18014630b  lea     rdx, [rsp+0B10h+bstrString]
0x180146310  mov     rcx, rbx
0x180146313  mov     rax, [rax+20h]
0x180146317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014631c  test    eax, eax
0x18014631e  js      loc_180146516
0x180146324  mov     r14d, 104h
0x18014632a  mov     r8d, r14d; cchBufferLength
0x18014632d  lea     rdx, [rbp+0A10h+szVolumePathName]; lpszVolumePathName
0x180146334  mov     rcx, [rsp+0B10h+pbstr]; lpszFileName
0x180146339  call    cs:__imp_GetVolumePathNameW
0x18014633f  test    eax, eax
0x180146341  jz      loc_180146516
0x180146347  mov     rcx, [rsp+0B10h+pbstr]; pbstr
0x18014634c  call    cs:__imp_SysStringLen
0x180146352  lea     rcx, [rbp+0A10h+szVolumePathName]
0x180146359  or      r15, 0FFFFFFFFFFFFFFFFh
0x18014635d  mov     r8, r15
0x180146360  inc     r8
0x180146363  cmp     [rcx+r8*2], si
0x180146368  jnz     short loc_180146360
0x18014636a  mov     eax, eax
0x18014636c  cmp     r8, rax
0x18014636f  ja      loc_180146516
0x180146375  lea     rdx, [rbp+0A10h+szVolumePathName]
0x18014637c  mov     rcx, [rsp+0B10h+pbstr]
0x180146381  call    cs:__imp__o__wcsnicmp
0x180146387  test    eax, eax
0x180146389  jnz     loc_180146516
0x18014638f  mov     r8d, r14d; cchBufferLength
0x180146392  lea     rdx, [rbp+0A10h+szVolumeName]; lpszVolumeName
0x180146399  lea     rcx, [rbp+0A10h+szVolumePathName]; lpszVolumeMountPoint
0x1801463a0  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x1801463a6  test    eax, eax
0x1801463a8  jz      loc_180146516
0x1801463ae  mov     [rsp+0B10h+var_AD0], rsi
0x1801463b3  mov     rcx, [rdi+8]
0x1801463b7  test    rcx, rcx
0x1801463ba  jz      loc_180146516
0x1801463c0  mov     rax, [rcx]
0x1801463c3  lea     r8, [rsp+0B10h+var_AD0]
0x1801463c8  lea     rdx, [rbp+0A10h+szVolumeName]
0x1801463cf  mov     rax, [rax+48h]
0x1801463d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801463d8  test    eax, eax
0x1801463da  js      loc_180146516
0x1801463e0  lea     rax, [rbp+0A10h+szVolumePathName]
0x1801463e7  mov     rcx, r15
0x1801463ea  inc     rcx
0x1801463ed  cmp     [rax+rcx*2], si
0x1801463f1  jnz     short loc_1801463EA
0x1801463f3  mov     rax, [rsp+0B10h+pbstr]
0x1801463f8  lea     rcx, [rax+rcx*2]
0x1801463fc  mov     [rsp+0B10h+var_AF0], rcx
0x180146401  mov     r9, [rsp+0B10h+var_AD0]
0x180146406  lea     r8, aSS_0; "%s\\%s"
0x18014640d  mov     rdx, r14; unsigned __int64
0x180146410  lea     rcx, [rbp+0A10h+var_870]; wchar_t *
0x180146417  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x18014641c  test    eax, eax
0x18014641e  js      loc_180146516
0x180146424  lea     rcx, [rbp+0A10h+var_870]
0x18014642b  mov     rax, r15
0x18014642e  inc     rax
0x180146431  cmp     [rcx+rax*2], si
0x180146435  jnz     short loc_18014642E
0x180146437  cmp     [rbp+rax*2+0A10h+FindFileData.cAlternateFileName+1Ah], 5Ch ; '\'
0x180146440  jz      short loc_180146460
0x180146442  lea     r8, StringValue; "\\"
0x180146449  mov     rdx, r14; unsigned __int64
0x18014644c  lea     rcx, [rbp+0A10h+var_870]; wchar_t *
0x180146453  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180146458  test    eax, eax
0x18014645a  js      loc_180146516
0x180146460  mov     rax, [rsp+0B10h+bstrString]
0x180146465  mov     [rsp+0B10h+var_AF0], rax
0x18014646a  lea     r9, [rbp+0A10h+var_870]
0x180146471  lea     r8, aSS_1; "%s%s"
0x180146478  mov     rdx, r14; unsigned __int64
0x18014647b  lea     rcx, [rbp+0A10h+FileName]; wchar_t *
0x180146482  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x180146487  test    eax, eax
0x180146489  js      loc_180146516
0x18014648f  xor     edx, edx; Val
0x180146491  mov     r8d, 250h; Size
0x180146497  lea     rcx, [rsp+0B10h+FindFileData]; void *
0x18014649c  call    memset_0
0x1801464a1  lea     rdx, [rsp+0B10h+FindFileData]; lpFindFileData
0x1801464a6  lea     rcx, [rbp+0A10h+FileName]; lpFileName
0x1801464ad  call    cs:__imp_FindFirstFileW
0x1801464b3  mov     rbx, rax
0x1801464b6  cmp     rax, r15
0x1801464b9  jz      short loc_180146516
0x1801464bb  test    byte ptr [rsp+0B10h+FindFileData.dwFileAttributes], 10h
0x1801464c0  jnz     short loc_1801464FA
0x1801464c2  lea     rax, [rsp+0B10h+FindFileData.cFileName]
0x1801464c7  mov     [rsp+0B10h+var_AF0], rax
0x1801464cc  lea     r9, [rbp+0A10h+var_870]
0x1801464d3  lea     r8, aSS_1; "%s%s"
0x1801464da  mov     rdx, r14; unsigned __int64
0x1801464dd  lea     rcx, [rbp+0A10h+FileName]; wchar_t *
0x1801464e4  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1801464e9  test    eax, eax
0x1801464eb  js      short loc_1801464FA
0x1801464ed  lea     rcx, [rbp+0A10h+FileName]; lpFileName
0x1801464f4  call    cs:__imp_DeleteFileW
0x1801464fa  lea     rdx, [rsp+0B10h+FindFileData]; lpFindFileData
0x1801464ff  mov     rcx, rbx; hFindFile
0x180146502  call    cs:__imp_FindNextFileW
0x180146508  test    eax, eax
0x18014650a  jnz     short loc_1801464BB
0x18014650c  mov     rcx, rbx; hFindFile
0x18014650f  call    cs:__imp_FindClose
0x180146515  nop
0x180146516  mov     rcx, [rsp+0B10h+bstrString]; bstrString
0x18014651b  call    cs:__imp_SysFreeString
0x180146521  nop
0x180146522  mov     rcx, [rsp+0B10h+pbstr]; bstrString
0x180146527  call    cs:__imp_SysFreeString
0x18014652d  mov     rcx, [rbp+0A10h+var_30]
0x180146534  xor     rcx, rsp; StackCookie
0x180146537  call    __security_check_cookie
0x18014653c  mov     rbx, [rsp+0B10h+arg_10]
0x180146544  add     rsp, 0AF0h
0x18014654b  pop     r15
0x18014654d  pop     r14
0x18014654f  pop     rdi
0x180146550  pop     rsi
0x180146551  pop     rbp
0x180146552  retn
```
