# CInternetShortcut::_SetUrlProp(ushort const *,ulong)

- ea: `0x18002b7d0`
- end: `0x18002be22`
- name: `?_SetUrlProp@CInternetShortcut@@AEAAJPEBGK@Z`
- size: `1618`
- prototype: `int(CInternetShortcut *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002a5c0`
- `0x1800d15f0`

## callees

- `0x180011230`
- `0x18002acf8`
- `0x18002b7d0`
- `0x18002d100`
- `0x18002d6f8`
- `0x18005c3e0`
- `0x180067f44`
- `0x1800b83c8`
- `0x1803f69b4`
- `0x18054e27a`
- `0x18054e286`
- `0x18054e310`
- `0x180550010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002b81d`
- `KERNEL32!GetProcessHeap` at `0x18002b81d`
- `KERNEL32!HeapAlloc` at `0x18002b82e`
- `KERNEL32!HeapAlloc` at `0x18002b82e`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x18002bb78`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x18002bb78`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002b9bc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002ba92`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002bb1a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002b9bc`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002ba92`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002bb1a`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18002baf2`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18002baf2`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bdee`
- `OLEAUT32!__imp_SysFreeString` at `0x18002bdee`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetMalloc` at `0x18002ba1f`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetMalloc` at `0x18002ba1f`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002b8d6`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002b8d6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18002b9ff`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18002b9ff`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002b95e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002b991`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002bb8a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002bb9d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002bddd`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002b95e`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002b991`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002bb8a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002bb9d`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002bddd`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002b9d2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002bb43`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002b9d2`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002bb43`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002bd14`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002bd14`
- `PROPSYS!PropVariantToBSTR` at `0x18002b8cb`
- `PROPSYS!PropVariantToBSTR` at `0x18002b8cb`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x18002bd2c`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x18002bd2c`

## pseudocode

```c
__int64 __fastcall CInternetShortcut::_SetUrlProp(CInternetShortcut *this, const unsigned __int16 *a2, char a3)
{
  _DWORD *v3; // rax
  HANDLE ProcessHeap; // rax
  HRESULT v8; // ebx
  CInternetShortcutPropertyStore *v9; // rcx
  CInternetShortcutPropertyStore *v10; // rcx
  _QWORD *v11; // r15
  unsigned int v12; // r12d
  LPWSTR v13; // rdi
  size_t v14; // rbx
  int v15; // eax
  LPWSTR v16; // rcx
  GUID v17; // xmm6
  __int64 v18; // rsi
  BOOL v19; // ebx
  __int64 (**v20)[3]; // r11
  unsigned int v21; // r10d
  __int64 (**v22)[3]; // r9
  unsigned int i; // ecx
  __int64 *v24; // r8
  __int64 v25; // rax
  __int64 *v26; // rax
  __int64 *v27; // rbx
  __int64 v28; // rcx
  struct tagPROPVARIANT *p_Buf1; // rdx
  CInternetShortcutPropertyStore *v30; // rcx
  const WCHAR *propvar; // [rsp+48h] [rbp-89h] BYREF
  PARSEDURLW propvar_8; // [rsp+50h] [rbp-81h] BYREF
  void *ppv; // [rsp+78h] [rbp-59h] BYREF
  BSTR pbstrOut; // [rsp+80h] [rbp-51h] BYREF
  PARSEDURLW ppu; // [rsp+88h] [rbp-49h] BYREF
  struct _tagpropertykey Buf1; // [rsp+B0h] [rbp-21h] BYREF
  struct tagPROPVARIANT v38; // [rsp+C8h] [rbp-9h] BYREF

  v3 = (_DWORD *)*((_QWORD *)this + 35);
  if ( !v3 )
  {
    ProcessHeap = GetProcessHeap();
    v3 = HeapAlloc(ProcessHeap, 8u, 0x50u);
    if ( !v3 )
      std::_Xbad_alloc();
    v3[8] = 1;
    *(_QWORD *)v3 = &CInternetShortcutPropertyStore::`vftable'{for `IPropertyStore'};
    *((_QWORD *)v3 + 1) = &CInternetShortcutPropertyStore::`vftable'{for `IPersistFile'};
    *((_QWORD *)v3 + 2) = &CInternetShortcutPropertyStore::`vftable'{for `IPersistStream'};
    *((_QWORD *)v3 + 3) = &CInternetShortcutPropertyStore::`vftable'{for `IObjectProvider'};
    *((_QWORD *)v3 + 6) = 0;
    *((_QWORD *)v3 + 7) = 0;
    *((_QWORD *)v3 + 8) = 0;
    *((_QWORD *)v3 + 9) = 0;
    *((_QWORD *)this + 35) = v3;
  }
  pbstrOut = 0;
  Buf1.pid = 2;
  Buf1.fmtid = FMTID_Intshcut;
  v8 = 0;
  memset(&propvar_8, 0, 24);
  if ( (int)CInternetShortcutPropertyStore::GetValue(
              (CInternetShortcutPropertyStore *)v3,
              &Buf1,
              (struct tagPROPVARIANT *)&propvar_8) >= 0 )
  {
    PropVariantToBSTR((const PROPVARIANT *const)&propvar_8, &pbstrOut);
    PropVariantClear((PROPVARIANT *)&propvar_8);
  }
  if ( !a2 )
  {
    v9 = (CInternetShortcutPropertyStore *)*((_QWORD *)this + 35);
    Buf1.pid = 2;
    Buf1.fmtid = FMTID_Intshcut;
    memset(&v38, 0, sizeof(v38));
    v8 = CInternetShortcutPropertyStore::SetValue(v9, &Buf1, &v38);
    if ( v8 >= 0 )
    {
      v10 = (CInternetShortcutPropertyStore *)*((_QWORD *)this + 35);
      Buf1.pid = 3;
      memset(&propvar_8, 0, 24);
      LOWORD(propvar_8.cbSize) = 19;
      LODWORD(propvar_8.pszProtocol) = 0;
      v8 = CInternetShortcutPropertyStore::SetValue(v10, &Buf1, (const struct tagPROPVARIANT *)&propvar_8);
    }
    CoTaskMemFree(*((LPVOID *)this + 182));
    *((_QWORD *)this + 182) = 0;
    goto LABEL_79;
  }
  v11 = (_QWORD *)((char *)this + 1456);
  v12 = ((a3 & 1) + 8) | 2;
  if ( (a3 & 2) == 0 )
    v12 = (a3 & 1) + 8;
  CoTaskMemFree(*((LPVOID *)this + 182));
  *v11 = 0;
  memset(&propvar_8, 0, sizeof(propvar_8));
  propvar_8.cbSize = 40;
  if ( ParseURLW(a2, &propvar_8) >= 0 && propvar_8.nScheme == 15 )
    v8 = SHStrDupW(a2, (LPWSTR *)this + 182);
  if ( v8 >= 0 )
  {
    ppv = 0;
    if ( !is_mul_ok(0x824u, 2u) )
    {
      v8 = -2147024362;
      goto LABEL_79;
    }
    v13 = (LPWSTR)CoTaskMemAlloc(0x1048u);
    if ( v13 )
    {
      propvar = 0;
      v14 = 0;
      if ( CoGetMalloc(1u, (LPMALLOC *)&propvar) >= 0 )
      {
        v14 = (*(__int64 (__fastcall **)(const WCHAR *, LPWSTR))(*(_QWORD *)propvar + 48LL))(propvar, v13);
        (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)propvar + 16LL))(propvar);
      }
      memset_0(v13, 0, v14);
      v8 = 0;
    }
    else
    {
      v8 = -2147024882;
    }
    if ( v8 >= 0 )
    {
      memset(&propvar_8, 0, sizeof(propvar_8));
      propvar_8.cbSize = 40;
      if ( ParseURLW(a2, &propvar_8) >= 0 && propvar_8.nScheme == 15 && *v11 )
      {
        StringCchCopyW(v13, 0x824u, a2);
      }
      else
      {
        v8 = IURLQualifyLib(a2, v12, 0x824u, v13, 0, 0, 0);
        if ( v8 < 0 )
          goto LABEL_77;
      }
      if ( pbstrOut && !StrCmpW(v13, pbstrOut) )
        goto LABEL_77;
      *(_QWORD *)&ppu.cbSize = 40;
      memset(&ppu.pszProtocol, 0, 32);
      v8 = ParseURLW(v13, &ppu);
      if ( v8 )
        goto LABEL_77;
      if ( (unsigned int)IsSpecialUrl(v13) )
      {
        propvar = 0;
        if ( SHStrDupW(v13, (LPWSTR *)&propvar) >= 0 )
        {
          v15 = DetectSpecialUrlHacks(propvar);
          v16 = (LPWSTR)propvar;
          if ( v15 == -2147024891 )
          {
            if ( propvar )
            {
              while ( *v16 )
              {
                if ( *v16 == 1 )
                {
                  *v16 = 0;
                  break;
                }
                v16 = CharNextW(v16);
              }
            }
            CoTaskMemFree(v13);
            v13 = (LPWSTR)propvar;
            v16 = 0;
            propvar = 0;
          }
          CoTaskMemFree(v16);
        }
      }
      v17 = FMTID_Intshcut;
      v18 = *((_QWORD *)this + 35);
      Buf1.pid = 2;
      *(_QWORD *)&propvar_8.cchProtocol = 0;
      *(_QWORD *)&propvar_8.cbSize = 31;
      Buf1.fmtid = FMTID_Intshcut;
      propvar_8.pszProtocol = v13;
      memset(&v38, 0, 20);
      v19 = memcmp_0(&Buf1, &FMTID_InternetSite, 0x10u) == 0;
      if ( !memcmp_0(&Buf1, &FMTID_InternetSite, 0x10u) )
      {
        v20 = off_180555E60;
        v21 = 28;
        v22 = off_180555E68;
        goto LABEL_46;
      }
      if ( !memcmp_0(&Buf1, &FMTID_Intshcut, 0x10u) )
      {
        v20 = &off_180555D40;
        v21 = 18;
        v22 = (__int64 (**)[3])&off_180555D48;
LABEL_46:
        for ( i = 0; i < v21; ++i )
        {
          v24 = (__int64 *)v20[2 * i];
          if ( *((_DWORD *)v24 + 4) == 2 )
          {
            v25 = *v24 - *(_QWORD *)&Buf1.fmtid.Data1;
            if ( *v24 == *(_QWORD *)&Buf1.fmtid.Data1 )
              v25 = v24[1] - *(_QWORD *)Buf1.fmtid.Data4;
            if ( !v25 )
            {
              _mm_lfence();
              v26 = (__int64 *)v22[2 * i];
              *(_OWORD *)&v38.vt = *(_OWORD *)v26;
              *((_DWORD *)&v38.decVal + 4) = *((_DWORD *)v26 + 4);
              goto LABEL_56;
            }
          }
        }
        v8 = -2147467259;
        goto LABEL_74;
      }
      *(GUID *)&v38.vt = FMTID_Intshcut;
      *((_DWORD *)&v38.decVal + 4) = 2;
LABEL_56:
      if ( !v19 )
      {
        v27 = (__int64 *)(v18 + 64);
        if ( *(_QWORD *)(v18 + 64) )
          goto LABEL_67;
        if ( !*(_QWORD *)(v18 + 72) )
        {
          ppv = 0;
          if ( PSCreateMemoryPropertyStore(&GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99, &ppv) >= 0 )
            PSCreateAdapterFromPropertyStore(
              (IPropertyStore *)ppv,
              &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
              (void **)(v18 + 64));
          if ( ppv )
            (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        if ( *v27 )
        {
LABEL_67:
          v28 = *v27;
        }
        else
        {
          v28 = *(_QWORD *)(v18 + 72);
          if ( !v28 )
          {
            v8 = -2147418113;
            goto LABEL_77;
          }
        }
        p_Buf1 = &v38;
        if ( !*v27 )
          p_Buf1 = (struct tagPROPVARIANT *)&Buf1;
        v8 = (*(__int64 (__fastcall **)(__int64, struct tagPROPVARIANT *, PARSEDURLW *))(*(_QWORD *)v28 + 48LL))(
               v28,
               p_Buf1,
               &propvar_8);
        if ( v8 < 0 )
          goto LABEL_77;
        *(_DWORD *)(v18 + 40) = 1;
        goto LABEL_73;
      }
      v8 = CInternetShortcutPropertyStore::_EnsureHistoryStore((CInternetShortcutPropertyStore *)v18);
      if ( v8 >= 0 )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, struct tagPROPVARIANT *, PARSEDURLW *))(**(_QWORD **)(v18 + 48) + 48LL))(
               *(_QWORD *)(v18 + 48),
               &v38,
               &propvar_8);
        if ( v8 >= 0 )
        {
          *(_DWORD *)(v18 + 36) = 1;
LABEL_73:
          v17 = FMTID_Intshcut;
LABEL_74:
          if ( v8 >= 0 )
          {
            v30 = (CInternetShortcutPropertyStore *)*((_QWORD *)this + 35);
            Buf1.pid = 3;
            memset(&propvar_8, 0, 24);
            LOWORD(propvar_8.cbSize) = 19;
            LODWORD(propvar_8.pszProtocol) = ppu.nScheme;
            Buf1.fmtid = v17;
            v8 = CInternetShortcutPropertyStore::SetValue(v30, &Buf1, (const struct tagPROPVARIANT *)&propvar_8);
          }
        }
      }
LABEL_77:
      CoTaskMemFree(v13);
    }
  }
LABEL_79:
  SysFreeString(pbstrOut);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002b7d0  mov     rax, rsp
0x18002b7d3  mov     [rax+18h], rbx
0x18002b7d7  push    rbp
0x18002b7d8  push    rsi
0x18002b7d9  push    rdi
0x18002b7da  push    r12
0x18002b7dc  push    r13
0x18002b7de  push    r14
0x18002b7e0  push    r15
0x18002b7e2  lea     rbp, [rax-5Fh]
0x18002b7e6  sub     rsp, 0F0h
0x18002b7ed  movaps  xmmword ptr [rax-48h], xmm6
0x18002b7f1  mov     rax, cs:__security_cookie
0x18002b7f8  xor     rax, rsp
0x18002b7fb  mov     [rbp+57h+var_48], rax
0x18002b7ff  mov     rax, [rcx+118h]
0x18002b806  xor     r13d, r13d
0x18002b809  mov     edi, r8d
0x18002b80c  mov     rsi, rdx
0x18002b80f  mov     r14, rcx
0x18002b812  mov     r15d, 1
0x18002b818  test    rax, rax
0x18002b81b  jnz     short loc_18002B885
0x18002b81d  call    cs:__imp_GetProcessHeap
0x18002b823  mov     rcx, rax; hHeap
0x18002b826  lea     edx, [r15+7]; dwFlags
0x18002b82a  lea     r8d, [r15+4Fh]; dwBytes
0x18002b82e  call    cs:__imp_HeapAlloc
0x18002b834  test    rax, rax
0x18002b837  jnz     short loc_18002B83F
0x18002b839  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002b83f  lea     rcx, ??_7CInternetShortcutPropertyStore@@6BIPropertyStore@@@; const CInternetShortcutPropertyStore::`vftable'{for `IPropertyStore'}
0x18002b846  mov     [rax+20h], r15d
0x18002b84a  mov     [rax], rcx
0x18002b84d  lea     rcx, ??_7CInternetShortcutPropertyStore@@6BIPersistFile@@@; const CInternetShortcutPropertyStore::`vftable'{for `IPersistFile'}
0x18002b854  mov     [rax+8], rcx
0x18002b858  lea     rcx, ??_7CInternetShortcutPropertyStore@@6BIPersistStream@@@; const CInternetShortcutPropertyStore::`vftable'{for `IPersistStream'}
0x18002b85f  mov     [rax+10h], rcx
0x18002b863  lea     rcx, ??_7CInternetShortcutPropertyStore@@6BIObjectProvider@@@; const CInternetShortcutPropertyStore::`vftable'{for `IObjectProvider'}
0x18002b86a  mov     [rax+18h], rcx
0x18002b86e  mov     [rax+30h], r13
0x18002b872  mov     [rax+38h], r13
0x18002b876  mov     [rax+40h], r13
0x18002b87a  mov     [rax+48h], r13
0x18002b87e  mov     [r14+118h], rax
0x18002b885  movups  xmm1, xmmword ptr cs:FMTID_Intshcut.Data1
0x18002b88c  xor     ecx, ecx
0x18002b88e  mov     [rbp+57h+pbstrOut], r13
0x18002b892  mov     qword ptr [rbp+57h+var_C8], rcx
0x18002b896  lea     r8, [rsp+120h+propvar+8]; struct tagPROPVARIANT *
0x18002b89b  xorps   xmm0, xmm0
0x18002b89e  mov     [rbp+57h+var_68], 2
0x18002b8a5  mov     rcx, rax; this
0x18002b8a8  lea     rdx, [rbp+57h+Buf1]; struct _tagpropertykey *
0x18002b8ac  movdqu  [rbp+57h+Buf1], xmm1
0x18002b8b1  mov     ebx, r13d
0x18002b8b4  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002b8b9  call    ?GetValue@CInternetShortcutPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CInternetShortcutPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)
0x18002b8be  test    eax, eax
0x18002b8c0  js      short loc_18002B8DC
0x18002b8c2  lea     rdx, [rbp+57h+pbstrOut]; pbstrOut
0x18002b8c6  lea     rcx, [rsp+120h+propvar+8]; propvar
0x18002b8cb  call    cs:__imp_PropVariantToBSTR
0x18002b8d1  lea     rcx, [rsp+120h+propvar+8]; pvar
0x18002b8d6  call    cs:__imp_PropVariantClear
0x18002b8dc  test    rsi, rsi
0x18002b8df  jnz     loc_18002B970
0x18002b8e5  movups  xmm1, xmmword ptr cs:FMTID_Intshcut.Data1
0x18002b8ec  mov     rcx, [r14+118h]; this
0x18002b8f3  lea     r8, [rbp+57h+var_60]; struct tagPROPVARIANT *
0x18002b8f7  xorps   xmm0, xmm0
0x18002b8fa  mov     [rbp+57h+var_68], 2
0x18002b901  xor     eax, eax
0x18002b903  lea     rdx, [rbp+57h+Buf1]; struct _tagpropertykey *
0x18002b907  movdqu  [rbp+57h+Buf1], xmm1
0x18002b90c  mov     qword ptr [rbp+57h+var_60+10h], rax
0x18002b910  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002b914  call    ?SetValue@CInternetShortcutPropertyStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CInternetShortcutPropertyStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)
0x18002b919  mov     ebx, eax
0x18002b91b  test    eax, eax
0x18002b91d  js      short loc_18002B957
0x18002b91f  mov     rcx, [r14+118h]; this
0x18002b926  lea     r8, [rsp+120h+propvar+8]; struct tagPROPVARIANT *
0x18002b92b  xor     eax, eax
0x18002b92d  mov     [rbp+57h+var_68], 3
0x18002b934  mov     qword ptr [rbp+57h+var_C8], rax
0x18002b938  lea     rdx, [rbp+57h+Buf1]; struct _tagpropertykey *
0x18002b93c  xorps   xmm0, xmm0
0x18002b93f  lea     eax, [rsi+13h]
0x18002b942  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002b947  mov     word ptr [rsp+120h+propvar+8], ax
0x18002b94c  mov     dword ptr [rbp+57h+var_D0], r13d
0x18002b950  call    ?SetValue@CInternetShortcutPropertyStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CInternetShortcutPropertyStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)
0x18002b955  mov     ebx, eax
0x18002b957  mov     rcx, [r14+5B0h]; pv
0x18002b95e  call    cs:__imp_CoTaskMemFree
0x18002b964  mov     [r14+5B0h], r13
0x18002b96b  jmp     loc_18002BDEA
0x18002b970  mov     eax, edi
0x18002b972  and     eax, r15d
0x18002b975  lea     r15, [r14+5B0h]
0x18002b97c  mov     rcx, [r15]; pv
0x18002b97f  add     eax, 8
0x18002b982  mov     r12d, eax
0x18002b985  or      r12d, 2
0x18002b989  test    dil, 2
0x18002b98d  cmovz   r12d, eax
0x18002b991  call    cs:__imp_CoTaskMemFree
0x18002b997  xorps   xmm0, xmm0
0x18002b99a  mov     [r15], r13
0x18002b99d  xor     eax, eax
0x18002b99f  lea     rdx, [rsp+120h+propvar+8]; ppu
0x18002b9a4  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002b9a9  mov     rcx, rsi; pcszURL
0x18002b9ac  mov     dword ptr [rsp+120h+propvar+8], 28h ; '('
0x18002b9b4  movups  [rbp+57h+var_C8], xmm0
0x18002b9b8  mov     [rbp+57h+var_B8], rax
0x18002b9bc  call    cs:__imp_ParseURLW
0x18002b9c2  test    eax, eax
0x18002b9c4  js      short loc_18002B9DA
0x18002b9c6  cmp     dword ptr [rbp+57h+var_B8+4], 0Fh
0x18002b9ca  jnz     short loc_18002B9DA
0x18002b9cc  mov     rdx, r15; ppwsz
0x18002b9cf  mov     rcx, rsi; psz
0x18002b9d2  call    cs:__imp_SHStrDupW
0x18002b9d8  mov     ebx, eax
0x18002b9da  test    ebx, ebx
0x18002b9dc  js      loc_18002BDEA
0x18002b9e2  mov     ecx, 824h
0x18002b9e7  mov     [rbp+57h+ppv], r13
0x18002b9eb  mov     eax, 2
0x18002b9f0  mul     rcx
0x18002b9f3  test    rdx, rdx
0x18002b9f6  jnz     loc_18002BDE5
0x18002b9fc  mov     rcx, rax; cb
0x18002b9ff  call    cs:__imp_CoTaskMemAlloc
0x18002ba05  mov     rdi, rax
0x18002ba08  test    rax, rax
0x18002ba0b  jz      short loc_18002BA63
0x18002ba0d  lea     rdx, [rsp+120h+propvar]; ppMalloc
0x18002ba12  mov     [rsp+120h+propvar], r13
0x18002ba17  mov     ecx, 1; dwMemContext
0x18002ba1c  mov     rbx, r13
0x18002ba1f  call    cs:__imp_CoGetMalloc
0x18002ba25  test    eax, eax
0x18002ba27  js      short loc_18002BA51
0x18002ba29  mov     rcx, [rsp+120h+propvar]
0x18002ba2e  mov     rdx, rdi
0x18002ba31  mov     rax, [rcx]
0x18002ba34  mov     rax, [rax+30h]
0x18002ba38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba3d  mov     rcx, [rsp+120h+propvar]
0x18002ba42  mov     rbx, rax
0x18002ba45  mov     rdx, [rcx]
0x18002ba48  mov     rax, [rdx+10h]
0x18002ba4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ba51  mov     r8, rbx; Size
0x18002ba54  xor     edx, edx; Val
0x18002ba56  mov     rcx, rdi; void *
0x18002ba59  call    memset_0
0x18002ba5e  mov     ebx, r13d
0x18002ba61  jmp     short loc_18002BA68
0x18002ba63  mov     ebx, 8007000Eh
0x18002ba68  test    ebx, ebx
0x18002ba6a  js      loc_18002BDEA
0x18002ba70  xorps   xmm0, xmm0
0x18002ba73  lea     rdx, [rsp+120h+propvar+8]; ppu
0x18002ba78  xor     eax, eax
0x18002ba7a  mov     rcx, rsi; pcszURL
0x18002ba7d  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002ba82  mov     dword ptr [rsp+120h+propvar+8], 28h ; '('
0x18002ba8a  movups  [rbp+57h+var_C8], xmm0
0x18002ba8e  mov     [rbp+57h+var_B8], rax
0x18002ba92  call    cs:__imp_ParseURLW
0x18002ba98  test    eax, eax
0x18002ba9a  js      short loc_18002BAB9
0x18002ba9c  cmp     dword ptr [rbp+57h+var_B8+4], 0Fh
0x18002baa0  jnz     short loc_18002BAB9
0x18002baa2  cmp     [r15], r13
0x18002baa5  jz      short loc_18002BAB9
0x18002baa7  mov     r8, rsi; unsigned __int16 *
0x18002baaa  mov     edx, 824h; unsigned __int64
0x18002baaf  mov     rcx, rdi; unsigned __int16 *
0x18002bab2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002bab7  jmp     short loc_18002BAE6
0x18002bab9  mov     [rsp+120h+var_F0], r13; int *
0x18002babe  mov     r9, rdi; unsigned __int16 *
0x18002bac1  mov     [rsp+120h+var_F8], r13; int *
0x18002bac6  mov     r8d, 824h; unsigned int
0x18002bacc  mov     edx, r12d; unsigned int
0x18002bacf  mov     [rsp+120h+var_100], r13; struct IUnknown *
0x18002bad4  mov     rcx, rsi; unsigned __int16 *
0x18002bad7  call    ?IURLQualifyLib@@YAJPEBGKKPEAGPEAUIUnknown@@PEAH3@Z; IURLQualifyLib(ushort const *,ulong,ulong,ushort *,IUnknown *,int *,int *)
0x18002badc  mov     ebx, eax
0x18002bade  test    eax, eax
0x18002bae0  js      loc_18002BDDA
0x18002bae6  mov     rdx, [rbp+57h+pbstrOut]; psz2
0x18002baea  test    rdx, rdx
0x18002baed  jz      short loc_18002BB00
0x18002baef  mov     rcx, rdi; psz1
0x18002baf2  call    cs:__imp_StrCmpW
0x18002baf8  test    eax, eax
0x18002bafa  jz      loc_18002BDDA
0x18002bb00  xorps   xmm0, xmm0
0x18002bb03  mov     qword ptr [rbp+57h+ppu.cbSize], 28h ; '('
0x18002bb0b  lea     rdx, [rbp+57h+ppu]; ppu
0x18002bb0f  mov     rcx, rdi; pcszURL
0x18002bb12  movups  xmmword ptr [rbp+57h+ppu.pszProtocol], xmm0
0x18002bb16  movups  xmmword ptr [rbp+57h+ppu.pszSuffix], xmm0
0x18002bb1a  call    cs:__imp_ParseURLW
0x18002bb20  mov     ebx, eax
0x18002bb22  test    eax, eax
0x18002bb24  jnz     loc_18002BDDA
0x18002bb2a  mov     rcx, rdi
0x18002bb2d  call    IsSpecialUrl
0x18002bb32  test    eax, eax
0x18002bb34  jz      short loc_18002BBA3
0x18002bb36  lea     rdx, [rsp+120h+propvar]; ppwsz
0x18002bb3b  mov     [rsp+120h+propvar], r13
0x18002bb40  mov     rcx, rdi; psz
0x18002bb43  call    cs:__imp_SHStrDupW
0x18002bb49  test    eax, eax
0x18002bb4b  js      short loc_18002BBA3
0x18002bb4d  mov     rcx, [rsp+120h+propvar]; pszFirst
0x18002bb52  call    ?DetectSpecialUrlHacks@@YAJPEBG@Z; DetectSpecialUrlHacks(ushort const *)
0x18002bb57  mov     rcx, [rsp+120h+propvar]; lpsz
0x18002bb5c  cmp     eax, 80070005h
0x18002bb61  jnz     short loc_18002BB9D
0x18002bb63  test    rcx, rcx
0x18002bb66  jz      short loc_18002BB87
0x18002bb68  cmp     r13w, [rcx]
0x18002bb6c  jz      short loc_18002BB87
0x18002bb6e  mov     eax, 1
0x18002bb73  cmp     ax, [rcx]
0x18002bb76  jz      short loc_18002BB83
0x18002bb78  call    cs:__imp_CharNextW
0x18002bb7e  mov     rcx, rax
0x18002bb81  jmp     short loc_18002BB68
0x18002bb83  mov     [rcx], r13w
0x18002bb87  mov     rcx, rdi; pv
0x18002bb8a  call    cs:__imp_CoTaskMemFree
0x18002bb90  mov     rdi, [rsp+120h+propvar]
0x18002bb95  mov     rcx, r13; pv
0x18002bb98  mov     [rsp+120h+propvar], rcx
0x18002bb9d  call    cs:__imp_CoTaskMemFree
0x18002bba3  movups  xmm6, xmmword ptr cs:FMTID_Intshcut.Data1
0x18002bbaa  mov     rsi, [r14+118h]
0x18002bbb1  lea     rdx, FMTID_InternetSite; Buf2
0x18002bbb8  xor     eax, eax
0x18002bbba  mov     [rbp+57h+var_68], 2
0x18002bbc1  mov     qword ptr [rbp+57h+var_C8], rax
0x18002bbc5  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002bbc9  xorps   xmm0, xmm0
0x18002bbcc  mov     eax, 1Fh
0x18002bbd1  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002bbd6  mov     word ptr [rsp+120h+propvar+8], ax
0x18002bbdb  xor     eax, eax
0x18002bbdd  movups  [rbp+57h+Buf1], xmm6
0x18002bbe1  mov     [rbp+57h+var_D0], rdi
0x18002bbe5  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002bbe9  lea     r15d, [rax+10h]
0x18002bbed  mov     dword ptr [rbp+57h+var_60+10h], eax
0x18002bbf0  mov     r8d, r15d; Size
0x18002bbf3  call    memcmp_0
0x18002bbf8  test    eax, eax
0x18002bbfa  lea     rdx, FMTID_InternetSite; Buf2
0x18002bc01  mov     ebx, r13d
0x18002bc04  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002bc08  mov     r8d, r15d; Size
0x18002bc0b  setz    bl
0x18002bc0e  call    memcmp_0
0x18002bc13  test    eax, eax
0x18002bc15  jnz     short loc_18002BC2B
0x18002bc17  lea     r11, off_180555E60
0x18002bc1e  lea     r10d, [r15+0Ch]
0x18002bc22  lea     r9, off_180555E68
0x18002bc29  jmp     short loc_18002BC54
0x18002bc2b  mov     r8, r15; Size
0x18002bc2e  lea     rdx, FMTID_Intshcut; Buf2
0x18002bc35  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002bc39  call    memcmp_0
0x18002bc3e  test    eax, eax
0x18002bc40  jnz     short loc_18002BCA6
0x18002bc42  lea     r11, off_180555D40
0x18002bc49  lea     r10d, [rax+12h]
0x18002bc4d  lea     r9, off_180555D48
0x18002bc54  mov     ecx, r13d
0x18002bc57  cmp     ecx, r10d
0x18002bc5a  jnb     short loc_18002BC9C
0x18002bc5c  mov     edx, ecx
0x18002bc5e  add     rdx, rdx
0x18002bc61  mov     r8, [r11+rdx*8]
0x18002bc65  cmp     dword ptr [r8+10h], 2
0x18002bc6a  jnz     short loc_18002BC82
0x18002bc6c  mov     rax, [r8]
0x18002bc6f  sub     rax, qword ptr [rbp+57h+Buf1]
0x18002bc73  jnz     short loc_18002BC7D
0x18002bc75  mov     rax, [r8+8]
0x18002bc79  sub     rax, qword ptr [rbp+57h+Buf1+8]
0x18002bc7d  test    rax, rax
  ... truncated ...
```
