# CMapiSupport::GetDllDetails(ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)

- ea: `0x18002f1d8`
- end: `0x18002f429`
- name: `?GetDllDetails@CMapiSupport@@CAJV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@AEAV23@1@Z`
- size: `593`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18002f430`

## callees

- `0x1800031c0`
- `0x180004058`
- `0x180004850`
- `0x1800048c0`
- `0x18000557c`
- `0x1800059ec`
- `0x180005b54`
- `0x180006270`
- `0x180018ea8`
- `0x18001cdfc`
- `0x18002f1d8`
- `0x18002f524`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f248`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002f248`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002f26e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18002f26e`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18002f2c2`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18002f377`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18002f2c2`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetFolderPathW` at `0x18002f377`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CMapiSupport::GetDllDetails(WCHAR *a1, __int64 a2, __int64 a3)
{
  HMODULE ModuleHandleW; // rax
  __int64 v6; // r8
  __int64 v7; // r9
  WCHAR *v8; // rdi
  WCHAR *pszPath; // rbx
  HRESULT v10; // edi
  unsigned int v11; // eax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned int DllDetailsFromPath; // edi
  unsigned int v19; // eax
  __int64 v20; // r8
  __int64 v21; // r9
  __int64 v22; // r8
  __int64 v23; // r9
  const WCHAR *v24; // rcx
  LPWSTR v26[2]; // [rsp+30h] [rbp-D0h] BYREF
  WCHAR Filename[264]; // [rsp+40h] [rbp-C0h] BYREF

  v26[1] = a1;
  ATL::CSimpleStringT<wchar_t,0>::SetString(a2, &lParam, 0);
  ATL::CSimpleStringT<wchar_t,0>::SetString(a3, &lParam, 0);
  ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(v26);
  ModuleHandleW = GetModuleHandleW(*(LPCWSTR *)a1);
  if ( ModuleHandleW )
  {
    v8 = Filename;
    if ( GetModuleFileNameW(ModuleHandleW, Filename, 0x104u) || !(unsigned int)ResultFromLastError() )
    {
      pszPath = v26[0];
      goto LABEL_11;
    }
  }
  pszPath = v26[0];
  if ( ((*((_DWORD *)v26[0] - 3) - 260) | (1 - *((_DWORD *)v26[0] - 2))) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v26, 260, v6, v7);
    pszPath = v26[0];
  }
  v10 = SHGetFolderPathW(0, 43, 0, 0, pszPath);
  v11 = ocslen(pszPath);
  ATL::CSimpleStringT<wchar_t,0>::SetLength(v26, v11, v12, v13);
  if ( !v10 )
  {
    ATL::CSimpleStringT<wchar_t,0>::Append(v26, L"\\System\\MSMAPI\\1033\\");
    ATL::CSimpleStringT<wchar_t,0>::Append((__int64 *)v26, *(const void **)a1, *(unsigned int *)(*(_QWORD *)a1 - 16LL));
    pszPath = v26[0];
    if ( ((*((_DWORD *)v26[0] - 3) - 260) | (1 - *((_DWORD *)v26[0] - 2))) < 0 )
    {
      ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v26, 260, v16, v17);
      pszPath = v26[0];
    }
    v8 = pszPath;
LABEL_11:
    DllDetailsFromPath = CMapiSupport::GetDllDetailsFromPath(v8);
    if ( !DllDetailsFromPath )
      goto LABEL_18;
  }
  if ( ((*((_DWORD *)pszPath - 3) - 260) | (1 - *((_DWORD *)pszPath - 2))) < 0 )
  {
    ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v26, 260, v14, v15);
    pszPath = v26[0];
  }
  DllDetailsFromPath = SHGetFolderPathW(0, 37, 0, 0, pszPath);
  v19 = ocslen(pszPath);
  ATL::CSimpleStringT<wchar_t,0>::SetLength(v26, v19, v20, v21);
  ATL::CSimpleStringT<wchar_t,0>::Append(v26, L"\\");
  ATL::CSimpleStringT<wchar_t,0>::Append((__int64 *)v26, *(const void **)a1, *(unsigned int *)(*(_QWORD *)a1 - 16LL));
  if ( !DllDetailsFromPath )
  {
    v24 = v26[0];
    if ( ((*((_DWORD *)v26[0] - 3) - 260) | (1 - *((_DWORD *)v26[0] - 2))) < 0 )
    {
      ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(v26, 260, v22, v23);
      v24 = v26[0];
    }
    DllDetailsFromPath = CMapiSupport::GetDllDetailsFromPath(v24);
  }
LABEL_18:
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(v26);
  ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(a1);
  return DllDetailsFromPath;
}

```

## disassembly

```asm
0x18002f1d8  mov     [rsp-8+arg_18], rbx
0x18002f1dd  push    rbp
0x18002f1de  push    rsi
0x18002f1df  push    rdi
0x18002f1e0  push    r12
0x18002f1e2  push    r13
0x18002f1e4  push    r14
0x18002f1e6  push    r15
0x18002f1e8  lea     rbp, [rsp-160h]
0x18002f1f0  sub     rsp, 260h
0x18002f1f7  mov     rax, cs:__security_cookie
0x18002f1fe  xor     rax, rsp
0x18002f201  mov     [rbp+190h+var_40], rax
0x18002f208  mov     r12, r8
0x18002f20b  mov     r15, rdx
0x18002f20e  mov     r14, rcx
0x18002f211  mov     [rsp+290h+var_258], rcx
0x18002f216  xor     r8d, r8d
0x18002f219  lea     rdx, lParam
0x18002f220  mov     rcx, r15
0x18002f223  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002f228  xor     r8d, r8d
0x18002f22b  lea     rdx, lParam
0x18002f232  mov     rcx, r12
0x18002f235  call    ?SetString@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::SetString(wchar_t const *,int)
0x18002f23a  lea     rcx, [rsp+290h+var_260]
0x18002f23f  call    ??0?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>(void)
0x18002f244  nop
0x18002f245  mov     rcx, [r14]; lpModuleName
0x18002f248  call    cs:__imp_GetModuleHandleW
0x18002f24e  mov     esi, 1
0x18002f253  mov     r13d, 104h
0x18002f259  test    rax, rax
0x18002f25c  jz      short loc_18002F28B
0x18002f25e  lea     rdi, [rsp+290h+Filename]
0x18002f263  mov     r8d, r13d; nSize
0x18002f266  lea     rdx, [rsp+290h+Filename]; lpFilename
0x18002f26b  mov     rcx, rax; hModule
0x18002f26e  call    cs:__imp_GetModuleFileNameW
0x18002f274  test    eax, eax
0x18002f276  jnz     short loc_18002F281
0x18002f278  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18002f27d  test    eax, eax
0x18002f27f  jnz     short loc_18002F28B
0x18002f281  mov     rbx, [rsp+290h+var_260]
0x18002f286  jmp     loc_18002F32D
0x18002f28b  mov     rbx, [rsp+290h+var_260]
0x18002f290  mov     ecx, esi
0x18002f292  sub     ecx, [rbx-8]
0x18002f295  mov     eax, [rbx-0Ch]
0x18002f298  sub     eax, r13d
0x18002f29b  or      ecx, eax
0x18002f29d  jge     short loc_18002F2B1
0x18002f29f  mov     edx, r13d
0x18002f2a2  lea     rcx, [rsp+290h+var_260]
0x18002f2a7  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x18002f2ac  mov     rbx, [rsp+290h+var_260]
0x18002f2b1  mov     [rsp+290h+pszPath], rbx; pszPath
0x18002f2b6  xor     r9d, r9d; dwFlags
0x18002f2b9  xor     r8d, r8d; hToken
0x18002f2bc  lea     edx, [r9+2Bh]; csidl
0x18002f2c0  xor     ecx, ecx; hwnd
0x18002f2c2  call    cs:__imp_SHGetFolderPathW
0x18002f2c8  mov     edi, eax
0x18002f2ca  mov     rcx, rbx; wchar_t *
0x18002f2cd  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18002f2d2  mov     edx, eax
0x18002f2d4  lea     rcx, [rsp+290h+var_260]
0x18002f2d9  call    ?SetLength@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::SetLength(int)
0x18002f2de  test    edi, edi
0x18002f2e0  jnz     short loc_18002F345
0x18002f2e2  lea     rdx, aSystemMsmapi10; "\\System\\MSMAPI\\1033\\"
0x18002f2e9  lea     rcx, [rsp+290h+var_260]
0x18002f2ee  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x18002f2f3  mov     rdx, [r14]
0x18002f2f6  mov     r8d, [rdx-10h]
0x18002f2fa  lea     rcx, [rsp+290h+var_260]
0x18002f2ff  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x18002f304  mov     rbx, [rsp+290h+var_260]
0x18002f309  mov     ecx, esi
0x18002f30b  sub     ecx, [rbx-8]
0x18002f30e  mov     eax, [rbx-0Ch]
0x18002f311  sub     eax, r13d
0x18002f314  or      ecx, eax
0x18002f316  jge     short loc_18002F32A
0x18002f318  mov     edx, r13d
0x18002f31b  lea     rcx, [rsp+290h+var_260]
0x18002f320  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x18002f325  mov     rbx, [rsp+290h+var_260]
0x18002f32a  mov     rdi, rbx
0x18002f32d  mov     r8, r12
0x18002f330  mov     rdx, r15
0x18002f333  mov     rcx, rdi; lpwstrFilename
0x18002f336  call    ?GetDllDetailsFromPath@CMapiSupport@@CAJPEA_WAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@1@Z; CMapiSupport::GetDllDetailsFromPath(wchar_t *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002f33b  mov     edi, eax
0x18002f33d  test    eax, eax
0x18002f33f  jz      loc_18002F3EA
0x18002f345  mov     ecx, esi
0x18002f347  sub     ecx, [rbx-8]
0x18002f34a  mov     eax, [rbx-0Ch]
0x18002f34d  sub     eax, r13d
0x18002f350  or      ecx, eax
0x18002f352  jge     short loc_18002F366
0x18002f354  mov     edx, r13d
0x18002f357  lea     rcx, [rsp+290h+var_260]
0x18002f35c  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x18002f361  mov     rbx, [rsp+290h+var_260]
0x18002f366  mov     [rsp+290h+pszPath], rbx; pszPath
0x18002f36b  xor     r9d, r9d; dwFlags
0x18002f36e  xor     r8d, r8d; hToken
0x18002f371  lea     edx, [r9+25h]; csidl
0x18002f375  xor     ecx, ecx; hwnd
0x18002f377  call    cs:__imp_SHGetFolderPathW
0x18002f37d  mov     edi, eax
0x18002f37f  mov     rcx, rbx; wchar_t *
0x18002f382  call    ?ocslen@@YAHPEB_W@Z; ocslen(wchar_t const *)
0x18002f387  mov     edx, eax
0x18002f389  lea     rcx, [rsp+290h+var_260]
0x18002f38e  call    ?SetLength@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::SetLength(int)
0x18002f393  lea     rdx, asc_180043CA8; "\\"
0x18002f39a  lea     rcx, [rsp+290h+var_260]
0x18002f39f  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_W@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *)
0x18002f3a4  mov     rdx, [r14]
0x18002f3a7  mov     r8d, [rdx-10h]
0x18002f3ab  lea     rcx, [rsp+290h+var_260]
0x18002f3b0  call    ?Append@?$CSimpleStringT@_W$0A@@ATL@@QEAAXPEB_WH@Z; ATL::CSimpleStringT<wchar_t,0>::Append(wchar_t const *,int)
0x18002f3b5  test    edi, edi
0x18002f3b7  jnz     short loc_18002F3EA
0x18002f3b9  mov     rcx, [rsp+290h+var_260]
0x18002f3be  sub     esi, [rcx-8]
0x18002f3c1  mov     eax, [rcx-0Ch]
0x18002f3c4  sub     eax, r13d
0x18002f3c7  or      esi, eax
0x18002f3c9  jge     short loc_18002F3DD
0x18002f3cb  mov     edx, r13d
0x18002f3ce  lea     rcx, [rsp+290h+var_260]
0x18002f3d3  call    ?PrepareWrite2@?$CSimpleStringT@_W$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<wchar_t,0>::PrepareWrite2(int)
0x18002f3d8  mov     rcx, [rsp+290h+var_260]; lpwstrFilename
0x18002f3dd  mov     r8, r12
0x18002f3e0  mov     rdx, r15
0x18002f3e3  call    ?GetDllDetailsFromPath@CMapiSupport@@CAJPEA_WAEAV?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@1@Z; CMapiSupport::GetDllDetailsFromPath(wchar_t *,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &,ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>> &)
0x18002f3e8  mov     edi, eax
0x18002f3ea  lea     rcx, [rsp+290h+var_260]
0x18002f3ef  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002f3f4  nop
0x18002f3f5  mov     rcx, r14
0x18002f3f8  call    ??1?$CSimpleStringT@_W$0A@@ATL@@QEAA@XZ; ATL::CSimpleStringT<wchar_t,0>::~CSimpleStringT<wchar_t,0>(void)
0x18002f3fd  mov     eax, edi
0x18002f3ff  mov     rcx, [rbp+190h+var_40]
0x18002f406  xor     rcx, rsp; StackCookie
0x18002f409  call    __security_check_cookie
0x18002f40e  mov     rbx, [rsp+290h+arg_18]
0x18002f416  add     rsp, 260h
0x18002f41d  pop     r15
0x18002f41f  pop     r14
0x18002f421  pop     r13
0x18002f423  pop     r12
0x18002f425  pop     rdi
0x18002f426  pop     rsi
0x18002f427  pop     rbp
0x18002f428  retn
```
