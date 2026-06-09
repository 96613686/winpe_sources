# Viewer::savePromptFileName(ushort *,int,void * *,ushort * *)

- ea: `0x1800e1ba8`
- end: `0x1800e1fbd`
- name: `?savePromptFileName@Viewer@@AEAAJPEAGHPEAPEAXPEAPEAG@Z`
- size: `1045`
- prototype: `__int64 __usercall@<rax>(Viewer *__hidden this@<rcx>, unsigned __int16 *@<rdx>, int@<r8d>, void **@<r9>, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800dfee4`

## callees

- `0x18000a5cc`
- `0x18001f080`
- `0x18002d8d0`
- `0x180037454`
- `0x180046640`
- `0x18004d878`
- `0x1800e198c`
- `0x1800e1ba8`
- `0x180102cde`
- `0x180107010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e1d40`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e1f14`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e1d40`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800e1f14`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e1f8c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e1f9a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e1f8c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800e1f9a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1d58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1d6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1f2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1d58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1d6b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800e1f2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1e0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e1e63`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e1f7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800e1f7e`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800e1e00`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800e1e59`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800e1e00`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x1800e1e59`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800e1c45`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800e1c45`

## string_xrefs

- `0x1800e1d30`: `IEFRAME.DLL`
- `0x1800e1eda`: `COMDLG32.DLL`

## pseudocode

```c
__int64 __fastcall Viewer::savePromptFileName(
        Viewer *this,
        unsigned __int16 *a2,
        __int64 a3,
        void **a4,
        unsigned __int16 **a5)
{
  WCHAR *v5; // r13
  WCHAR *v9; // r14
  _WORD *v10; // r12
  LPWSTR ExtensionW; // rax
  const unsigned __int16 *v12; // rsi
  unsigned __int64 v13; // rdx
  int v14; // eax
  unsigned __int64 v15; // r9
  int v16; // r8d
  int v17; // eax
  __int16 v18; // cx
  signed __int64 v19; // r15
  _WORD *v20; // rdx
  __int16 *v21; // rdi
  signed int v22; // ebx
  BOOL v23; // r14d
  int v24; // r13d
  HMODULE Library; // rax
  HMODULE v26; // r15
  FARPROC ProcAddress; // rdi
  FARPROC v28; // rax
  int v29; // eax
  HMODULE v30; // rsi
  DWORD TempPathW; // eax
  DWORD v32; // ecx
  signed int LastError; // eax
  unsigned int v34; // eax
  __int64 v35; // rbx
  DWORD v36; // eax
  __int16 v37; // ax
  _WORD *v38; // rcx
  HMODULE v39; // rax
  FARPROC v40; // rax
  void *v41; // rcx
  __int64 v42; // [rsp+58h] [rbp-B0h] BYREF
  __int64 (__fastcall *v43)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD); // [rsp+60h] [rbp-A8h]
  HWND HWND; // [rsp+68h] [rbp-A0h]
  LPVOID pv; // [rsp+70h] [rbp-98h] BYREF
  WCHAR *v46; // [rsp+78h] [rbp-90h]
  struct String *v47; // [rsp+80h] [rbp-88h]
  int v48; // [rsp+88h] [rbp-80h] BYREF
  HWND v49; // [rsp+90h] [rbp-78h]
  _WORD *v50; // [rsp+A0h] [rbp-68h]
  int v51; // [rsp+B4h] [rbp-54h]
  WCHAR *v52; // [rsp+B8h] [rbp-50h]
  int v53; // [rsp+C0h] [rbp-48h]
  int v54; // [rsp+E8h] [rbp-20h]
  const unsigned __int16 *v55; // [rsp+F0h] [rbp-18h]
  int v57; // [rsp+178h] [rbp+70h]

  v5 = a2;
  memset_0(&v48, 0, 0x98u);
  pv = 0;
  *a4 = 0;
  HWND = Viewer::saveGetHWND(this);
  if ( !HWND )
    return 1;
  v43 = 0;
  v46 = 0;
  v57 = 0;
  v9 = 0;
  v47 = Resources::formatMessage(839681, 0, 0, 0, 0);
  v10 = (_WORD *)*((_QWORD *)v47 + 3);
  ExtensionW = PathFindExtensionW(v5);
  v12 = ExtensionW;
  if ( !ExtensionW || !*ExtensionW )
  {
    v12 = L".xml";
    xstrlenw(v5, 0x7FFFFFFFu);
    v14 = xstrlenw(L".xml", v13);
    if ( v14 + v16 < (int)v15 )
      StringCchCatW(v5, v15, L".xml");
  }
  v17 = xstrlenw(v12, 0x7FFFFFFFu);
  v18 = *v10;
  v19 = v17;
  v20 = v10;
  v21 = v10;
  v22 = 1;
  if ( *v10 )
  {
    v23 = 0;
    v24 = 0;
    while ( 1 )
    {
      if ( v18 == 124 )
      {
        if ( v23 )
        {
          ++v24;
          if ( (_DWORD)v19 )
          {
            if ( v19 < v21 - v20 && !(unsigned int)fastcmpni(v12, (const unsigned __int16 *)&v21[-v19], v19) )
            {
LABEL_17:
              v9 = v46;
              v57 = v24;
              v5 = a2;
              break;
            }
          }
        }
        v20 = ++v21;
        v23 = !v23;
      }
      else
      {
        ++v21;
      }
      v18 = *v21;
      if ( !*v21 )
        goto LABEL_17;
    }
  }
  LODWORD(v42) = 0;
  Library = LoadLibraryExW(L"IEFRAME.DLL", 0, 0);
  v26 = Library;
  if ( Library
    && (ProcAddress = GetProcAddress(Library, "IEIsProtectedModeProcess"),
        v28 = GetProcAddress(v26, "IEShowSaveFileDialog"),
        v43 = (__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD))v28,
        ProcAddress)
    && v28
    && ((int (__fastcall *)(__int64 *))ProcAddress)(&v42) < 0 )
  {
    v29 = 0;
    LODWORD(v42) = 0;
  }
  else
  {
    v29 = v42;
  }
  if ( !v29 )
  {
    v37 = *v10;
    if ( *v10 )
    {
      v38 = v10;
      do
      {
        if ( v37 == 124 )
          *v38 = 0;
        v37 = *++v38;
      }
      while ( *v38 );
    }
    memset_0(&v48, 0, 0x98u);
    v49 = HWND;
    v48 = 152;
    v55 = L"xml";
    v51 = v57;
    v54 = 559110;
    v50 = v10;
    v52 = v5;
    v53 = 261;
    v39 = LoadLibraryExW(L"COMDLG32.DLL", 0, 0);
    v30 = v39;
    if ( v39 )
    {
      v40 = GetProcAddress(v39, "GetSaveFileNameW");
      if ( v40 )
      {
        if ( ((unsigned int (__fastcall *)(int *))v40)(&v48) )
          v22 = 0;
      }
    }
    goto LABEL_47;
  }
  v30 = 0;
  v22 = v43(HWND, v5, 0, v10, L"xml", v57, 34822, &pv, a4);
  if ( !v22 )
  {
    TempPathW = GetTempPathW(0, 0);
    v32 = TempPathW;
    if ( !TempPathW )
      goto LABEL_27;
    v34 = TempPathW + 261;
    if ( v34 < v32 || (v35 = v34 + 1, (unsigned int)v35 < v34) )
    {
      v22 = -2147024362;
    }
    else if ( (unsigned __int64)(2 * v35) > 0xFFFFFFFF )
    {
      v22 = -2147024362;
    }
    else
    {
      v9 = (WCHAR *)new_array<unsigned short>((unsigned int)v35);
      v36 = GetTempPathW(v35, v9);
      if ( !v36 )
      {
LABEL_27:
        LastError = GetLastError();
        v22 = LastError;
        if ( LastError > 0 )
          v22 = (unsigned __int16)LastError | 0x80070000;
        goto LABEL_47;
      }
      if ( v36 <= (unsigned int)v35 )
        v22 = StringCchCatW(v9, (unsigned int)v35, v5);
      else
        v22 = -2147467259;
    }
  }
LABEL_47:
  (*(void (__fastcall **)(struct String *))(*(_QWORD *)v47 + 104LL))(v47);
  if ( v22 < 0 && v9 )
  {
    MemFreeObject(v9);
    v9 = 0;
  }
  v41 = pv;
  *a5 = v9;
  if ( v41 )
    CoTaskMemFree(v41);
  if ( v26 )
    FreeLibrary(v26);
  if ( v30 )
    FreeLibrary(v30);
  return (unsigned int)v22;
}

```

## disassembly

```asm
0x1800e1ba8  mov     rax, rsp
0x1800e1bab  mov     [rax+8], rbx
0x1800e1baf  mov     [rax+20h], r9
0x1800e1bb3  mov     [rax+18h], r8d
0x1800e1bb7  mov     [rax+10h], rdx
0x1800e1bbb  push    rbp
0x1800e1bbc  push    rsi
0x1800e1bbd  push    rdi
0x1800e1bbe  push    r12
0x1800e1bc0  push    r13
0x1800e1bc2  push    r14
0x1800e1bc4  push    r15
0x1800e1bc6  lea     rbp, [rax-58h]
0x1800e1bca  sub     rsp, 120h
0x1800e1bd1  mov     r13, rdx
0x1800e1bd4  mov     rbx, rcx
0x1800e1bd7  xor     edx, edx; Val
0x1800e1bd9  lea     rcx, [rbp+50h+var_D0]; void *
0x1800e1bdd  mov     r8d, 98h; Size
0x1800e1be3  mov     rdi, r9
0x1800e1be6  call    memset_0
0x1800e1beb  xor     r15d, r15d
0x1800e1bee  mov     rcx, rbx; this
0x1800e1bf1  mov     [rsp+150h+pv], r15
0x1800e1bf6  mov     [rdi], r15
0x1800e1bf9  call    ?saveGetHWND@Viewer@@AEAAPEAUHWND__@@XZ; Viewer::saveGetHWND(void)
0x1800e1bfe  mov     [rsp+150h+var_F0], rax
0x1800e1c03  test    rax, rax
0x1800e1c06  jnz     short loc_1800E1C11
0x1800e1c08  lea     eax, [r15+1]
0x1800e1c0c  jmp     loc_1800E1FA2
0x1800e1c11  xor     r9d, r9d; struct String *
0x1800e1c14  mov     [rsp+150h+var_F8], r15
0x1800e1c19  xor     r8d, r8d; struct String *
0x1800e1c1c  mov     [rsp+150h+var_E0], r15
0x1800e1c21  xor     edx, edx; struct String *
0x1800e1c23  mov     [rbp+50h+arg_10], r15d
0x1800e1c27  mov     ecx, 0CD001h; int
0x1800e1c2c  mov     [rsp+150h+var_130], r15; struct String *
0x1800e1c31  mov     r14, r15
0x1800e1c34  call    ?formatMessage@Resources@@SAPEAVString@@JPEAV2@000@Z; Resources::formatMessage(long,String *,String *,String *,String *)
0x1800e1c39  mov     rcx, r13; pszPath
0x1800e1c3c  mov     [rsp+150h+var_D8], rax
0x1800e1c41  mov     r12, [rax+18h]
0x1800e1c45  call    cs:__imp_PathFindExtensionW
0x1800e1c4b  mov     ebx, 7FFFFFFFh
0x1800e1c50  mov     r9d, 105h
0x1800e1c56  mov     rsi, rax
0x1800e1c59  test    rax, rax
0x1800e1c5c  jz      short loc_1800E1C64
0x1800e1c5e  cmp     r15w, [rax]
0x1800e1c62  jnz     short loc_1800E1C97
0x1800e1c64  mov     rdx, rbx; unsigned __int64
0x1800e1c67  lea     rsi, aXml_2; ".xml"
0x1800e1c6e  mov     rcx, r13; unsigned __int16 *
0x1800e1c71  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800e1c76  mov     rcx, rsi; unsigned __int16 *
0x1800e1c79  mov     r8d, eax
0x1800e1c7c  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800e1c81  add     r8d, eax
0x1800e1c84  cmp     r8d, r9d
0x1800e1c87  jge     short loc_1800E1C97
0x1800e1c89  mov     r8, rsi; unsigned __int16 *
0x1800e1c8c  mov     rdx, r9; unsigned __int64
0x1800e1c8f  mov     rcx, r13; unsigned __int16 *
0x1800e1c92  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e1c97  mov     rdx, rbx; unsigned __int64
0x1800e1c9a  mov     rcx, rsi; unsigned __int16 *
0x1800e1c9d  call    ?xstrlenw@@YAHPEBG_K@Z; xstrlenw(ushort const *,unsigned __int64)
0x1800e1ca2  movzx   ecx, word ptr [r12]
0x1800e1ca7  xor     r9d, r9d
0x1800e1caa  movsxd  r15, eax
0x1800e1cad  mov     rdx, r12
0x1800e1cb0  mov     rdi, r12
0x1800e1cb3  mov     ebx, 1
0x1800e1cb8  test    cx, cx
0x1800e1cbb  jz      short loc_1800E1D2E
0x1800e1cbd  mov     r14d, r9d
0x1800e1cc0  mov     r13d, r9d
0x1800e1cc3  cmp     cx, 7Ch ; '|'
0x1800e1cc7  jnz     short loc_1800E1D15
0x1800e1cc9  test    r14d, r14d
0x1800e1ccc  jz      short loc_1800E1D00
0x1800e1cce  add     r13d, ebx
0x1800e1cd1  test    r15d, r15d
0x1800e1cd4  jz      short loc_1800E1D00
0x1800e1cd6  mov     rax, rdi
0x1800e1cd9  mov     r8, r15; unsigned __int64
0x1800e1cdc  sub     rax, rdx
0x1800e1cdf  sar     rax, 1
0x1800e1ce2  cmp     r15, rax
0x1800e1ce5  jge     short loc_1800E1D00
0x1800e1ce7  lea     rax, [r15+r15]
0x1800e1ceb  mov     rdx, rdi
0x1800e1cee  sub     rdx, rax; unsigned __int16 *
0x1800e1cf1  mov     rcx, rsi; unsigned __int16 *
0x1800e1cf4  call    ?fastcmpni@@YAHPEBG0_K@Z; fastcmpni(ushort const *,ushort const *,unsigned __int64)
0x1800e1cf9  xor     r9d, r9d
0x1800e1cfc  test    eax, eax
0x1800e1cfe  jz      short loc_1800E1D21
0x1800e1d00  test    r14d, r14d
0x1800e1d03  lea     rdx, [rdi+2]
0x1800e1d07  mov     eax, r9d
0x1800e1d0a  mov     rdi, rdx
0x1800e1d0d  setz    al
0x1800e1d10  mov     r14d, eax
0x1800e1d13  jmp     short loc_1800E1D19
0x1800e1d15  add     rdi, 2
0x1800e1d19  movzx   ecx, word ptr [rdi]
0x1800e1d1c  test    cx, cx
0x1800e1d1f  jnz     short loc_1800E1CC3
0x1800e1d21  mov     r14, [rsp+150h+var_E0]
0x1800e1d26  mov     [rbp+50h+arg_10], r13d
0x1800e1d2a  mov     r13, [rbp+50h+arg_8]
0x1800e1d2e  xor     edi, edi
0x1800e1d30  lea     rcx, LibFileName; "IEFRAME.DLL"
0x1800e1d37  xor     r8d, r8d; dwFlags
0x1800e1d3a  mov     dword ptr [rsp+150h+var_100], edi
0x1800e1d3e  xor     edx, edx; hFile
0x1800e1d40  call    cs:__imp_LoadLibraryExW
0x1800e1d46  mov     r15, rax
0x1800e1d49  test    rax, rax
0x1800e1d4c  jz      short loc_1800E1D9D
0x1800e1d4e  lea     rdx, aIeisprotectedm; "IEIsProtectedModeProcess"
0x1800e1d55  mov     rcx, rax; hModule
0x1800e1d58  call    cs:__imp_GetProcAddress
0x1800e1d5e  lea     rdx, aIeshowsavefile; "IEShowSaveFileDialog"
0x1800e1d65  mov     rcx, r15; hModule
0x1800e1d68  mov     rdi, rax
0x1800e1d6b  call    cs:__imp_GetProcAddress
0x1800e1d71  mov     [rsp+150h+var_F8], rax
0x1800e1d76  test    rdi, rdi
0x1800e1d79  jz      short loc_1800E1D9B
0x1800e1d7b  test    rax, rax
0x1800e1d7e  jz      short loc_1800E1D9B
0x1800e1d80  lea     rcx, [rsp+150h+var_100]
0x1800e1d85  mov     rax, rdi
0x1800e1d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1d8d  xor     edi, edi
0x1800e1d8f  test    eax, eax
0x1800e1d91  jns     short loc_1800E1D9D
0x1800e1d93  mov     eax, edi
0x1800e1d95  mov     dword ptr [rsp+150h+var_100], eax
0x1800e1d99  jmp     short loc_1800E1DA1
0x1800e1d9b  xor     edi, edi
0x1800e1d9d  mov     eax, dword ptr [rsp+150h+var_100]
0x1800e1da1  test    eax, eax
0x1800e1da3  jz      loc_1800E1EA0
0x1800e1da9  mov     rax, [rbp+50h+arg_18]
0x1800e1dad  mov     r9, r12
0x1800e1db0  mov     rcx, [rsp+150h+var_F0]
0x1800e1db5  xor     r8d, r8d
0x1800e1db8  mov     [rsp+40h], rax
0x1800e1dbd  mov     rdx, r13
0x1800e1dc0  lea     rax, [rsp+150h+pv]
0x1800e1dc5  mov     rsi, rdi
0x1800e1dc8  mov     [rsp+150h+var_118], rax
0x1800e1dcd  mov     eax, [rbp+50h+arg_10]
0x1800e1dd0  mov     dword ptr [rsp+150h+var_120], 8806h
0x1800e1dd8  mov     [rsp+150h+var_128], eax
0x1800e1ddc  lea     rax, aXml_2+2; "xml"
0x1800e1de3  mov     [rsp+150h+var_130], rax
0x1800e1de8  mov     rax, [rsp+150h+var_F8]
0x1800e1ded  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1df2  mov     ebx, eax
0x1800e1df4  test    eax, eax
0x1800e1df6  jnz     loc_1800E1F45
0x1800e1dfc  xor     edx, edx; lpBuffer
0x1800e1dfe  xor     ecx, ecx; nBufferLength
0x1800e1e00  call    cs:__imp_GetTempPathW
0x1800e1e06  mov     ecx, eax
0x1800e1e08  test    eax, eax
0x1800e1e0a  jnz     short loc_1800E1E2A
0x1800e1e0c  call    cs:__imp_GetLastError
0x1800e1e12  mov     ebx, eax
0x1800e1e14  test    eax, eax
0x1800e1e16  jle     loc_1800E1F45
0x1800e1e1c  movzx   ebx, ax
0x1800e1e1f  or      ebx, 80070000h
0x1800e1e25  jmp     loc_1800E1F45
0x1800e1e2a  add     eax, 105h
0x1800e1e2f  cmp     eax, ecx
0x1800e1e31  jb      short loc_1800E1E96
0x1800e1e33  lea     ebx, [rax+1]
0x1800e1e36  cmp     ebx, eax
0x1800e1e38  jb      short loc_1800E1E96
0x1800e1e3a  lea     rax, [rbx+rbx]
0x1800e1e3e  mov     edi, ebx
0x1800e1e40  mov     ecx, 0FFFFFFFFh
0x1800e1e45  cmp     rax, rcx
0x1800e1e48  ja      short loc_1800E1E8F
0x1800e1e4a  mov     ecx, edi
0x1800e1e4c  call    ??$new_array@G@@YAPEAG_J@Z; new_array<ushort>(__int64)
0x1800e1e51  mov     rdx, rax; lpBuffer
0x1800e1e54  mov     ecx, ebx; nBufferLength
0x1800e1e56  mov     r14, rax
0x1800e1e59  call    cs:__imp_GetTempPathW
0x1800e1e5f  test    eax, eax
0x1800e1e61  jnz     short loc_1800E1E6D
0x1800e1e63  call    cs:__imp_GetLastError
0x1800e1e69  xor     edi, edi
0x1800e1e6b  jmp     short loc_1800E1E12
0x1800e1e6d  cmp     eax, ebx
0x1800e1e6f  jbe     short loc_1800E1E7D
0x1800e1e71  mov     ebx, 80004005h
0x1800e1e76  xor     edi, edi
0x1800e1e78  jmp     loc_1800E1F45
0x1800e1e7d  mov     r8, r13; unsigned __int16 *
0x1800e1e80  mov     rdx, rdi; unsigned __int64
0x1800e1e83  mov     rcx, r14; unsigned __int16 *
0x1800e1e86  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800e1e8b  mov     ebx, eax
0x1800e1e8d  jmp     short loc_1800E1E76
0x1800e1e8f  mov     ebx, 80070216h
0x1800e1e94  jmp     short loc_1800E1E76
0x1800e1e96  mov     ebx, 80070216h
0x1800e1e9b  jmp     loc_1800E1F45
0x1800e1ea0  movzx   eax, word ptr [r12]
0x1800e1ea5  test    ax, ax
0x1800e1ea8  jz      short loc_1800E1EC2
0x1800e1eaa  mov     rcx, r12
0x1800e1ead  cmp     ax, 7Ch ; '|'
0x1800e1eb1  jnz     short loc_1800E1EB6
0x1800e1eb3  mov     [rcx], di
0x1800e1eb6  add     rcx, 2
0x1800e1eba  movzx   eax, word ptr [rcx]
0x1800e1ebd  test    ax, ax
0x1800e1ec0  jnz     short loc_1800E1EAD
0x1800e1ec2  mov     esi, 98h
0x1800e1ec7  lea     rcx, [rbp+50h+var_D0]; void *
0x1800e1ecb  mov     r8d, esi; Size
0x1800e1ece  xor     edx, edx; Val
0x1800e1ed0  call    memset_0
0x1800e1ed5  mov     rax, [rsp+150h+var_F0]
0x1800e1eda  lea     rcx, aComdlg32Dll; "COMDLG32.DLL"
0x1800e1ee1  mov     [rbp+50h+var_C8], rax
0x1800e1ee5  xor     r8d, r8d; dwFlags
0x1800e1ee8  lea     rax, aXml_2+2; "xml"
0x1800e1eef  mov     [rbp+50h+var_D0], esi
0x1800e1ef2  mov     [rbp+50h+var_68], rax
0x1800e1ef6  xor     edx, edx; hFile
0x1800e1ef8  mov     eax, [rbp+50h+arg_10]
0x1800e1efb  mov     [rbp+50h+var_A4], eax
0x1800e1efe  mov     [rbp+50h+var_70], 88806h
0x1800e1f05  mov     [rbp+50h+var_B8], r12
0x1800e1f09  mov     [rbp+50h+var_A0], r13
0x1800e1f0d  mov     [rbp+50h+var_98], 105h
0x1800e1f14  call    cs:__imp_LoadLibraryExW
0x1800e1f1a  mov     rsi, rax
0x1800e1f1d  test    rax, rax
0x1800e1f20  jz      short loc_1800E1F45
0x1800e1f22  lea     rdx, aGetsavefilenam; "GetSaveFileNameW"
0x1800e1f29  mov     rcx, rax; hModule
0x1800e1f2c  call    cs:__imp_GetProcAddress
0x1800e1f32  test    rax, rax
0x1800e1f35  jz      short loc_1800E1F45
0x1800e1f37  lea     rcx, [rbp+50h+var_D0]
0x1800e1f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1f40  test    eax, eax
0x1800e1f42  cmovnz  ebx, edi
0x1800e1f45  mov     rcx, [rsp+150h+var_D8]
0x1800e1f4a  mov     rax, [rcx]
0x1800e1f4d  mov     rax, [rax+68h]
0x1800e1f51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e1f56  test    ebx, ebx
0x1800e1f58  jns     short loc_1800E1F6A
0x1800e1f5a  test    r14, r14
0x1800e1f5d  jz      short loc_1800E1F6A
0x1800e1f5f  mov     rcx, r14; void *
0x1800e1f62  call    ?MemFreeObject@@YAXPEAX@Z; MemFreeObject(void *)
0x1800e1f67  mov     r14, rdi
0x1800e1f6a  mov     rax, [rbp+50h+arg_20]
0x1800e1f71  mov     rcx, [rsp+150h+pv]; pv
0x1800e1f76  mov     [rax], r14
0x1800e1f79  test    rcx, rcx
0x1800e1f7c  jz      short loc_1800E1F84
0x1800e1f7e  call    cs:__imp_CoTaskMemFree
0x1800e1f84  test    r15, r15
0x1800e1f87  jz      short loc_1800E1F92
0x1800e1f89  mov     rcx, r15; hLibModule
0x1800e1f8c  call    cs:__imp_FreeLibrary
0x1800e1f92  test    rsi, rsi
0x1800e1f95  jz      short loc_1800E1FA0
0x1800e1f97  mov     rcx, rsi; hLibModule
0x1800e1f9a  call    cs:__imp_FreeLibrary
0x1800e1fa0  mov     eax, ebx
0x1800e1fa2  mov     rbx, [rsp+150h+arg_0]
0x1800e1faa  add     rsp, 120h
0x1800e1fb1  pop     r15
0x1800e1fb3  pop     r14
0x1800e1fb5  pop     r13
0x1800e1fb7  pop     r12
0x1800e1fb9  pop     rdi
0x1800e1fba  pop     rsi
0x1800e1fbb  pop     rbp
0x1800e1fbc  retn
```
