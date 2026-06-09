# CreateLinkFileExWorker(int,ushort const *,ushort const *,ushort const *,ushort const *,int,ushort const *,ushort,int,ushort const *,ushort const *,uint)

- ea: `0x180010810`
- end: `0x180010d53`
- name: `?CreateLinkFileExWorker@@YAHHPEBG000H0GH00I@Z`
- size: `1347`
- prototype: `__int64 __fastcall(int csidl, struct _SECURITY_ATTRIBUTES *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16, unsigned int, const unsigned __int16 *, const unsigned __int16 *pszResModule, int idsRes)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180002030`
- `0x180006400`
- `0x180010810`
- `0x180010d5c`
- `0x180012504`
- `0x18001b914`
- `0x1800222fc`
- `0x18002257c`
- `0x18002259c`
- `0x1800225dc`
- `0x180022610`
- `0x180022830`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x180010ad5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathUnquoteSpacesW` at `0x180010ad5`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x180010a89`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathGetArgsW` at `0x180010a89`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010ae8`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180010ae8`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180010d21`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180010d21`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010b19`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180010b19`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x180010947`
- `api-ms-win-shell-shellfolders-l1-1-0!SHGetSpecialFolderPathW` at `0x180010947`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180010cef`
- `ext-ms-win-shell-shell32-l1-2-0!SHChangeNotify` at `0x180010cef`
- `ext-ms-win-shell-shell32-l1-2-0!SHSetLocalizedName` at `0x180010c91`
- `ext-ms-win-shell-shell32-l1-2-0!SHSetLocalizedName` at `0x180010c91`

## string_xrefs

- `0x1800109e1`: `onecore\ds\security\gina\profile\profext\setup.cpp`
- `0x180010b5a`: `onecore\ds\security\gina\profile\profext\setup.cpp`
- `0x180010be6`: `%HOMEDRIVE%%HOMEPATH%`

## pseudocode

```c
__int64 __fastcall CreateLinkFileExWorker(
        int csidl,
        struct _SECURITY_ATTRIBUTES *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned __int16 *a5,
        unsigned int a6,
        const unsigned __int16 *a7,
        unsigned __int16 a8,
        unsigned int a9,
        const unsigned __int16 *a10,
        const unsigned __int16 *pszResModule,
        int idsRes)
{
  const unsigned __int16 *v15; // rbx
  const unsigned __int16 *p_lpSecurityDescriptor; // r8
  int v17; // ecx
  int v18; // ecx
  WCHAR v19; // ax
  unsigned int v20; // edi
  unsigned int v21; // r8d
  const char *v22; // r9
  unsigned __int16 *v23; // rcx
  unsigned int v24; // r8d
  __int64 v25; // rdx
  unsigned int v26; // eax
  HRESULT NestedDirectory; // eax
  __int64 v28; // rdx
  unsigned int v29; // edx
  unsigned __int16 *v30; // rax
  unsigned __int64 v31; // r10
  unsigned __int16 *v32; // r11
  const unsigned __int16 *ArgsW; // rax
  _WORD *v34; // r10
  HRESULT v35; // ebx
  int v36; // eax
  unsigned int v37; // r8d
  const wchar_t *v38; // rdx
  unsigned int v39; // r8d
  unsigned int v40; // r8d
  unsigned int v41; // eax
  unsigned int ppv; // [rsp+20h] [rbp-E0h]
  unsigned int v44[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPVOID v45; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v46; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v47; // [rsp+48h] [rbp-B8h]
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR sz[264]; // [rsp+260h] [rbp+160h] BYREF
  unsigned __int16 v50[264]; // [rsp+470h] [rbp+370h] BYREF
  unsigned __int16 v51[264]; // [rsp+680h] [rbp+580h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+8E8h] [rbp+7E8h]

  v47 = a5;
  v45 = 0;
  v15 = 0;
  v46 = 0;
  v44[0] = 0;
  if ( !a2 || !LOWORD(a2->nLength) )
    goto LABEL_20;
  if ( LOWORD(a2->nLength) != 58
    || HIWORD(a2->nLength) != 58
    || LOWORD(a2->bInheritHandle) != 58
    || HIWORD(a2->bInheritHandle) != 58 )
  {
    v15 = (const unsigned __int16 *)a2;
    goto LABEL_20;
  }
  p_lpSecurityDescriptor = (const unsigned __int16 *)&a2->lpSecurityDescriptor;
  v17 = 0;
  while ( 1 )
  {
    if ( ((*p_lpSecurityDescriptor - 88) & 0xFFDF) == 0 )
      goto LABEL_16;
    if ( (unsigned __int16)(*p_lpSecurityDescriptor - 48) > 9u )
      break;
    v18 = 16 * v17 - 48;
LABEL_15:
    v17 = *p_lpSecurityDescriptor + v18;
LABEL_16:
    ++p_lpSecurityDescriptor;
  }
  if ( (unsigned __int16)(*p_lpSecurityDescriptor - 97) <= 5u )
  {
    v18 = 16 * v17 - 87;
    goto LABEL_15;
  }
  if ( (unsigned __int16)(*p_lpSecurityDescriptor - 65) <= 5u )
  {
    v18 = 16 * v17 - 55;
    goto LABEL_15;
  }
  v15 = (const unsigned __int16 *)(&a2->bInheritHandle + 1);
  if ( v17 != -1 )
    csidl = v17;
LABEL_20:
  v19 = 0;
  v20 = 0;
  pszPath[0] = 0;
  if ( csidl )
  {
    if ( !SHGetSpecialFolderPathW(0, pszPath, csidl, 1) )
    {
      wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x25B, v21, v22);
      return v20;
    }
    v19 = pszPath[0];
  }
  if ( v15 && *v15 )
  {
    v23 = pszPath;
    if ( v19 )
    {
      v23 = CheckSlash(pszPath, (unsigned int)a2, v44);
      if ( !v23 )
      {
        v25 = 615;
LABEL_29:
        wil::details::in1diag3::Log_Hr(retaddr, (void *)v25, v24, (const char *)0x8000FFFFLL, ppv);
        return v20;
      }
      v26 = v44[0];
    }
    else
    {
      v26 = 260;
      v44[0] = 260;
    }
    NestedDirectory = StringCchCopyW(v23, v26, v15);
    if ( NestedDirectory < 0 )
    {
      v28 = 626;
LABEL_34:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v28,
        (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
        (const char *)(unsigned int)NestedDirectory,
        ppv);
      return v20;
    }
  }
  NestedDirectory = CreateNestedDirectory(pszPath, a2);
  if ( NestedDirectory < 0 )
  {
    v28 = 637;
    goto LABEL_34;
  }
  v30 = CheckSlash(pszPath, v29, v44);
  if ( !v30 )
  {
    v25 = 650;
    goto LABEL_29;
  }
  NestedDirectory = StringCchCopyW(v30, v44[0], a3);
  if ( NestedDirectory < 0 )
  {
    v28 = 655;
    goto LABEL_34;
  }
  NestedDirectory = StringCchCatW(v32, v31, L".lnk");
  if ( NestedDirectory < 0 )
  {
    v28 = 661;
    goto LABEL_34;
  }
  StringCchCopyW(sz, 0x104u, a4);
  ArgsW = PathGetArgsW(sz);
  if ( ArgsW && *ArgsW )
  {
    StringCchCopyW(v51, 0x104u, ArgsW);
    do
      --v34;
    while ( *v34 == 32 );
    v34[1] = 0;
  }
  else
  {
    v51[0] = 0;
  }
  PathUnquoteSpacesW(sz);
  v35 = CoInitializeEx(0, 2u);
  NestedDirectory = CoCreateInstance(&CLSID_ShellLink, 0, 1u, &IID_IShellLinkW, &v45);
  if ( NestedDirectory < 0 )
  {
    v28 = 703;
    goto LABEL_34;
  }
  v36 = (**(__int64 (__fastcall ***)(LPVOID, GUID *, __int64 *))v45)(v45, &IID_IPersistFile, &v46);
  if ( v36 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C9,
      (unsigned int)"onecore\\ds\\security\\gina\\profile\\profext\\setup.cpp",
      (const char *)(unsigned int)v36,
      ppv);
    goto LABEL_66;
  }
  if ( a10 )
    (*(void (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)v45 + 56LL))(v45, a10);
  PrependPath(sz, v50, v37);
  (*(void (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)v45 + 160LL))(v45, v50);
  (*(void (__fastcall **)(LPVOID, unsigned __int16 *))(*(_QWORD *)v45 + 88LL))(v45, v51);
  v38 = a7;
  if ( !a7 )
    v38 = L"%HOMEDRIVE%%HOMEPATH%";
  (*(void (__fastcall **)(LPVOID, const wchar_t *))(*(_QWORD *)v45 + 72LL))(v45, v38);
  PrependPath(v47, v50, v39);
  (*(void (__fastcall **)(LPVOID, unsigned __int16 *, _QWORD))(*(_QWORD *)v45 + 136LL))(v45, v50, a6);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v45 + 104LL))(v45, a8);
  (*(void (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v45 + 120LL))(v45, a9);
  if ( !pszResModule )
    goto LABEL_71;
  (*(void (__fastcall **)(__int64, WCHAR *, __int64))(*(_QWORD *)v46 + 48LL))(v46, pszPath, 1);
  if ( !(unsigned __int8)IsSHSetLocalizedNamePresent() )
  {
    v41 = 127;
    goto LABEL_61;
  }
  v41 = SHSetLocalizedName(pszPath, pszResModule, idsRes);
  if ( v41 )
  {
LABEL_61:
    wil::details::in1diag3::Log_Win32(retaddr, (void *)0x2FA, v40, (const char *)v41, ppv);
  }
  else
  {
LABEL_71:
    if ( (*(int (__fastcall **)(__int64, WCHAR *, __int64))(*(_QWORD *)v46 + 48LL))(v46, pszPath, 1) >= 0 )
    {
      v20 = 1;
      if ( (unsigned __int8)IsSHSetLocalizedNamePresent() )
        SHChangeNotify(2, 5u, pszPath, 0);
    }
  }
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
LABEL_66:
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v45 + 16LL))(v45);
  if ( v35 >= 0 )
    CoUninitialize();
  return v20;
}

```

## disassembly

```asm
0x180010810  push    rbp
0x180010812  push    rbx
0x180010813  push    rsi
0x180010814  push    rdi
0x180010815  push    r12
0x180010817  push    r13
0x180010819  push    r14
0x18001081b  push    r15
0x18001081d  lea     rbp, [rsp-7A8h]
0x180010825  sub     rsp, 8A8h
0x18001082c  mov     rax, cs:__security_cookie
0x180010833  xor     rax, rsp
0x180010836  mov     [rbp+7E0h+var_50], rax
0x18001083d  mov     rax, [rbp+7E0h+arg_20]
0x180010844  xor     r11d, r11d
0x180010847  mov     r12, [rbp+7E0h+arg_30]
0x18001084e  mov     r15, r9
0x180010851  mov     rsi, [rbp+7E0h+arg_48]
0x180010858  mov     r14, r8
0x18001085b  mov     r13, [rbp+7E0h+pszResModule]
0x180010862  mov     r10d, ecx
0x180010865  mov     [rsp+8E0h+var_898], rax
0x18001086a  lea     edi, [r11+5]
0x18001086e  mov     [rsp+8E0h+var_8A8], r11
0x180010873  mov     ebx, r11d
0x180010876  mov     [rsp+8E0h+var_8A0], r11
0x18001087b  mov     [rsp+8E0h+var_8B0], r11d
0x180010880  test    rdx, rdx
0x180010883  jz      loc_180010927
0x180010889  cmp     [rdx], r11w
0x18001088d  jz      loc_180010927
0x180010893  lea     eax, [rdi+35h]
0x180010896  cmp     ax, [rdx]
0x180010899  jnz     loc_180010924
0x18001089f  cmp     ax, [rdx+2]
0x1800108a3  jnz     short loc_180010924
0x1800108a5  cmp     ax, [rdx+10h]
0x1800108a9  jnz     short loc_180010924
0x1800108ab  cmp     ax, [rdx+12h]
0x1800108af  jnz     short loc_180010924
0x1800108b1  lea     r8, [rdx+8]
0x1800108b5  mov     ecx, r11d
0x1800108b8  movzx   eax, word ptr [r8]
0x1800108bc  mov     r9d, 0FFDFh
0x1800108c2  sub     ax, 58h ; 'X'
0x1800108c6  test    r9w, ax
0x1800108ca  jz      short loc_180010910
0x1800108cc  movzx   eax, word ptr [r8]
0x1800108d0  sub     ax, 30h ; '0'
0x1800108d4  cmp     ax, 9
0x1800108d8  ja      short loc_1800108E2
0x1800108da  shl     ecx, 4
0x1800108dd  add     ecx, 0FFFFFFD0h
0x1800108e0  jmp     short loc_18001090A
0x1800108e2  movzx   eax, word ptr [r8]
0x1800108e6  sub     ax, 61h ; 'a'
0x1800108ea  cmp     ax, di
0x1800108ed  ja      short loc_1800108F7
0x1800108ef  shl     ecx, 4
0x1800108f2  add     ecx, 0FFFFFFA9h
0x1800108f5  jmp     short loc_18001090A
0x1800108f7  movzx   eax, word ptr [r8]
0x1800108fb  sub     ax, 41h ; 'A'
0x1800108ff  cmp     ax, di
0x180010902  ja      short loc_180010916
0x180010904  shl     ecx, 4
0x180010907  add     ecx, 0FFFFFFC9h
0x18001090a  movzx   eax, word ptr [r8]
0x18001090e  add     ecx, eax
0x180010910  add     r8, 2
0x180010914  jmp     short loc_1800108B8
0x180010916  lea     rbx, [rdx+14h]
0x18001091a  cmp     ecx, 0FFFFFFFFh
0x18001091d  jz      short loc_180010927
0x18001091f  mov     r10d, ecx
0x180010922  jmp     short loc_180010927
0x180010924  mov     rbx, rdx
0x180010927  mov     eax, r11d
0x18001092a  mov     edi, r11d
0x18001092d  mov     [rsp+8E0h+pszPath], ax
0x180010932  test    r10d, r10d
0x180010935  jz      short loc_180010975
0x180010937  mov     r9d, 1; fCreate
0x18001093d  lea     rdx, [rsp+8E0h+pszPath]; pszPath
0x180010942  mov     r8d, r10d; csidl
0x180010945  xor     ecx, ecx; hwnd
0x180010947  call    cs:__imp_SHGetSpecialFolderPathW
0x18001094e  nop     dword ptr [rax+rax+00h]
0x180010953  xor     r11d, r11d
0x180010956  test    eax, eax
0x180010958  jnz     short loc_180010970
0x18001095a  mov     rcx, [rbp+7E8h]; this
0x180010961  mov     edx, 25Bh; void *
0x180010966  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18001096b  jmp     loc_180010D2D
0x180010970  movzx   eax, [rsp+8E0h+pszPath]
0x180010975  test    rbx, rbx
0x180010978  jz      short loc_1800109F5
0x18001097a  cmp     [rbx], r11w
0x18001097e  jz      short loc_1800109F5
0x180010980  lea     rcx, [rsp+8E0h+pszPath]; unsigned __int16 *
0x180010985  test    ax, ax
0x180010988  jz      short loc_1800109BE
0x18001098a  lea     r8, [rsp+8E0h+var_8B0]; unsigned int *
0x18001098f  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x180010994  mov     rcx, rax
0x180010997  test    rax, rax
0x18001099a  jnz     short loc_1800109B8
0x18001099c  mov     edx, 267h; void *
0x1800109a1  mov     rcx, [rbp+7E8h]; this
0x1800109a8  mov     r9d, 8000FFFFh; char *
0x1800109ae  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1800109b3  jmp     loc_180010D2D
0x1800109b8  mov     eax, [rsp+8E0h+var_8B0]
0x1800109bc  jmp     short loc_1800109C7
0x1800109be  mov     eax, 104h
0x1800109c3  mov     [rsp+8E0h+var_8B0], eax
0x1800109c7  mov     edx, eax; unsigned __int64
0x1800109c9  mov     r8, rbx; unsigned __int16 *
0x1800109cc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800109d1  test    eax, eax
0x1800109d3  jns     short loc_1800109F5
0x1800109d5  mov     edx, 272h; void *
0x1800109da  mov     rcx, [rbp+7E8h]; this
0x1800109e1  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x1800109e8  mov     r9d, eax; char *
0x1800109eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800109f0  jmp     loc_180010D2D
0x1800109f5  lea     rcx, [rsp+8E0h+pszPath]; unsigned __int16 *
0x1800109fa  call    ?CreateNestedDirectory@@YAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CreateNestedDirectory(ushort const *,_SECURITY_ATTRIBUTES *)
0x1800109ff  test    eax, eax
0x180010a01  jns     short loc_180010A0A
0x180010a03  mov     edx, 27Dh
0x180010a08  jmp     short loc_1800109DA
0x180010a0a  lea     r8, [rsp+8E0h+var_8B0]; unsigned int *
0x180010a0f  lea     rcx, [rsp+8E0h+pszPath]; unsigned __int16 *
0x180010a14  call    ?CheckSlash@@YAPEAGPEAGIPEAI@Z; CheckSlash(ushort *,uint,uint *)
0x180010a19  mov     r11, rax
0x180010a1c  test    rax, rax
0x180010a1f  jnz     short loc_180010A2B
0x180010a21  mov     edx, 28Ah
0x180010a26  jmp     loc_1800109A1
0x180010a2b  mov     r10d, [rsp+8E0h+var_8B0]
0x180010a30  mov     r8, r14; unsigned __int16 *
0x180010a33  mov     edx, r10d; unsigned __int64
0x180010a36  mov     rcx, r11; unsigned __int16 *
0x180010a39  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010a3e  xor     r14d, r14d
0x180010a41  test    eax, eax
0x180010a43  jns     short loc_180010A4C
0x180010a45  mov     edx, 28Fh
0x180010a4a  jmp     short loc_1800109DA
0x180010a4c  lea     r8, aLnk; ".lnk"
0x180010a53  mov     rdx, r10; unsigned __int64
0x180010a56  mov     rcx, r11; unsigned __int16 *
0x180010a59  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180010a5e  test    eax, eax
0x180010a60  jns     short loc_180010A6C
0x180010a62  mov     edx, 295h
0x180010a67  jmp     loc_1800109DA
0x180010a6c  mov     ebx, 104h
0x180010a71  lea     rcx, [rbp+7E0h+sz]; unsigned __int16 *
0x180010a78  mov     edx, ebx; unsigned __int64
0x180010a7a  mov     r8, r15; unsigned __int16 *
0x180010a7d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010a82  lea     rcx, [rbp+7E0h+sz]; pszPath
0x180010a89  call    cs:__imp_PathGetArgsW
0x180010a90  nop     dword ptr [rax+rax+00h]
0x180010a95  mov     r10, rax
0x180010a98  test    rax, rax
0x180010a9b  jz      short loc_180010AC6
0x180010a9d  cmp     [rax], r14w
0x180010aa1  jz      short loc_180010AC6
0x180010aa3  mov     r8, rax; unsigned __int16 *
0x180010aa6  lea     rcx, [rbp+7E0h+var_260]; unsigned __int16 *
0x180010aad  mov     edx, ebx; unsigned __int64
0x180010aaf  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180010ab4  sub     r10, 2
0x180010ab8  cmp     word ptr [r10], 20h ; ' '
0x180010abd  jz      short loc_180010AB4
0x180010abf  mov     [r10+2], r14w
0x180010ac4  jmp     short loc_180010ACE
0x180010ac6  mov     [rbp+7E0h+var_260], r14w
0x180010ace  lea     rcx, [rbp+7E0h+sz]; lpsz
0x180010ad5  call    cs:__imp_PathUnquoteSpacesW
0x180010adc  nop     dword ptr [rax+rax+00h]
0x180010ae1  mov     edx, 2; dwCoInit
0x180010ae6  xor     ecx, ecx; pvReserved
0x180010ae8  call    cs:__imp_CoInitializeEx
0x180010aef  nop     dword ptr [rax+rax+00h]
0x180010af4  mov     r15d, 1
0x180010afa  lea     r9, IID_IShellLinkW; riid
0x180010b01  mov     ebx, eax
0x180010b03  lea     rcx, CLSID_ShellLink; rclsid
0x180010b0a  lea     rax, [rsp+8E0h+var_8A8]
0x180010b0f  mov     r8d, r15d; dwClsContext
0x180010b12  xor     edx, edx; pUnkOuter
0x180010b14  mov     qword ptr [rsp+8E0h+ppv], rax; unsigned int
0x180010b19  call    cs:__imp_CoCreateInstance
0x180010b20  nop     dword ptr [rax+rax+00h]
0x180010b25  test    eax, eax
0x180010b27  jns     short loc_180010B33
0x180010b29  mov     edx, 2BFh
0x180010b2e  jmp     loc_1800109DA
0x180010b33  mov     rcx, [rsp+8E0h+var_8A8]
0x180010b38  lea     r8, [rsp+8E0h+var_8A0]
0x180010b3d  lea     rdx, IID_IPersistFile
0x180010b44  mov     rax, [rcx]
0x180010b47  mov     rax, [rax]
0x180010b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b4f  test    eax, eax
0x180010b51  jns     short loc_180010B73
0x180010b53  mov     rcx, [rbp+7E8h]; this
0x180010b5a  lea     r8, aOnecoreDsSecur_5; "onecore\\ds\\security\\gina\\profile\\p"...
0x180010b61  mov     r9d, eax; char *
0x180010b64  mov     edx, 2C9h; void *
0x180010b69  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180010b6e  jmp     loc_180010D0C
0x180010b73  test    rsi, rsi
0x180010b76  jz      short loc_180010B8C
0x180010b78  mov     rcx, [rsp+8E0h+var_8A8]
0x180010b7d  mov     rdx, rsi
0x180010b80  mov     rax, [rcx]
0x180010b83  mov     rax, [rax+38h]
0x180010b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b8c  lea     rdx, [rbp+7E0h+var_470]; unsigned __int16 *
0x180010b93  lea     rcx, [rbp+7E0h+sz]; unsigned __int16 *
0x180010b9a  call    ?PrependPath@@YAHPEBGPEAGI@Z; PrependPath(ushort const *,ushort *,uint)
0x180010b9f  mov     rcx, [rsp+8E0h+var_8A8]
0x180010ba4  lea     rdx, [rbp+7E0h+var_470]
0x180010bab  mov     rax, [rcx]
0x180010bae  mov     rax, [rax+0A0h]
0x180010bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bba  mov     rcx, [rsp+8E0h+var_8A8]
0x180010bbf  lea     rdx, [rbp+7E0h+var_260]
0x180010bc6  mov     rax, [rcx]
0x180010bc9  mov     rax, [rax+58h]
0x180010bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bd2  mov     rcx, [rsp+8E0h+var_8A8]
0x180010bd7  mov     rdx, r12
0x180010bda  mov     rax, [rcx]
0x180010bdd  mov     rax, [rax+48h]
0x180010be1  test    r12, r12
0x180010be4  jnz     short loc_180010BED
0x180010be6  lea     rdx, aHomedriveHomep; "%HOMEDRIVE%%HOMEPATH%"
0x180010bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010bf2  mov     rcx, [rsp+8E0h+var_898]; unsigned __int16 *
0x180010bf7  lea     rdx, [rbp+7E0h+var_470]; unsigned __int16 *
0x180010bfe  call    ?PrependPath@@YAHPEBGPEAGI@Z; PrependPath(ushort const *,ushort *,uint)
0x180010c03  mov     rcx, [rsp+8E0h+var_8A8]
0x180010c08  lea     rdx, [rbp+7E0h+var_470]
0x180010c0f  mov     r8d, [rbp+7E0h+arg_28]
0x180010c16  mov     rax, [rcx]
0x180010c19  mov     rax, [rax+88h]
0x180010c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c25  mov     rcx, [rsp+8E0h+var_8A8]
0x180010c2a  movzx   edx, [rbp+7E0h+arg_38]
0x180010c31  mov     rax, [rcx]
0x180010c34  mov     rax, [rax+68h]
0x180010c38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c3d  mov     rcx, [rsp+8E0h+var_8A8]
0x180010c42  mov     edx, [rbp+7E0h+arg_40]
0x180010c48  mov     rax, [rcx]
0x180010c4b  mov     rax, [rax+78h]
0x180010c4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c54  test    r13, r13
0x180010c57  jz      short loc_180010CB7
0x180010c59  mov     rcx, [rsp+8E0h+var_8A0]
0x180010c5e  lea     rdx, [rsp+8E0h+pszPath]
0x180010c63  mov     r8d, r15d
0x180010c66  mov     rax, [rcx]
0x180010c69  mov     rax, [rax+30h]
0x180010c6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c72  call    IsSHSetLocalizedNamePresent
0x180010c77  test    al, al
0x180010c79  jnz     short loc_180010C82
0x180010c7b  mov     eax, 7Fh
0x180010c80  jmp     short loc_180010CA1
0x180010c82  mov     r8d, [rbp+7E0h+idsRes]; idsRes
0x180010c89  lea     rcx, [rsp+8E0h+pszPath]; pszPath
0x180010c8e  mov     rdx, r13; pszResModule
0x180010c91  call    cs:__imp_SHSetLocalizedName
0x180010c98  nop     dword ptr [rax+rax+00h]
0x180010c9d  test    eax, eax
0x180010c9f  jz      short loc_180010CB7
0x180010ca1  mov     rcx, [rbp+7E8h]; this
0x180010ca8  mov     r9d, eax; char *
0x180010cab  mov     edx, 2FAh; void *
0x180010cb0  call    ?Log_Win32@in1diag3@details@wil@@YAKPEAXIPEBDK@Z; wil::details::in1diag3::Log_Win32(void *,uint,char const *,ulong)
0x180010cb5  jmp     short loc_180010CFB
0x180010cb7  mov     rcx, [rsp+8E0h+var_8A0]
0x180010cbc  lea     rdx, [rsp+8E0h+pszPath]
0x180010cc1  mov     r8d, r15d
0x180010cc4  mov     rax, [rcx]
0x180010cc7  mov     rax, [rax+30h]
0x180010ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cd0  test    eax, eax
0x180010cd2  js      short loc_180010CFB
0x180010cd4  mov     edi, r15d
0x180010cd7  call    IsSHSetLocalizedNamePresent
  ... truncated ...
```
