# CInternetShortcut::_SetUrlProp(ushort const *,ulong)

- ea: `0x18002d784`
- end: `0x18002de94`
- name: `?_SetUrlProp@CInternetShortcut@@AEAAJPEBGK@Z`
- size: `1808`
- prototype: `int(CInternetShortcut *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002cf40`
- `0x1800d98a0`

## callees

- `0x1800144d0`
- `0x18002d784`
- `0x18002f290`
- `0x18002f8d8`
- `0x180060770`
- `0x18006c894`
- `0x1800bf0d8`
- `0x18042cfb8`
- `0x180591eea`
- `0x180591ef6`
- `0x180591f80`
- `0x180594010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x18002d7d1`
- `KERNEL32!GetProcessHeap` at `0x18002d7d1`
- `KERNEL32!HeapAlloc` at `0x18002d7e8`
- `KERNEL32!HeapAlloc` at `0x18002d7e8`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x18002dbbe`
- `api-ms-win-downlevel-user32-l1-1-0!CharNextW` at `0x18002dbbe`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002d993`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002da81`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002db16`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002db53`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002d993`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002da81`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002db16`
- `api-ms-win-downlevel-shlwapi-l1-1-0!ParseURLW` at `0x18002db53`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18002dae7`
- `api-ms-win-downlevel-shlwapi-l1-1-0!StrCmpW` at `0x18002dae7`
- `OLEAUT32!__imp_SysFreeString` at `0x18002de59`
- `OLEAUT32!__imp_SysFreeString` at `0x18002de59`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetMalloc` at `0x18002da08`
- `api-ms-win-downlevel-ole32-l1-1-0!CoGetMalloc` at `0x18002da08`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002d89c`
- `api-ms-win-downlevel-ole32-l1-1-0!PropVariantClear` at `0x18002d89c`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18002d9e2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemAlloc` at `0x18002d9e2`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002d92a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002d962`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002dbd6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002dbef`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002de42`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002d92a`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002d962`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002dbd6`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002dbef`
- `api-ms-win-downlevel-ole32-l1-1-0!CoTaskMemFree` at `0x18002de42`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002d9af`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002db83`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002d9af`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHStrDupW` at `0x18002db83`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002dd6d`
- `PROPSYS!PSCreateMemoryPropertyStore` at `0x18002dd6d`
- `PROPSYS!PropVariantToBSTR` at `0x18002d88b`
- `PROPSYS!PropVariantToBSTR` at `0x18002d88b`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x18002dd8b`
- `PROPSYS!PSCreateAdapterFromPropertyStore` at `0x18002dd8b`

## pseudocode

```c
__int64 __fastcall CInternetShortcut::_SetUrlProp(CInternetShortcut *this, const unsigned __int16 *a2, char a3)
{
  _DWORD *v3; // rax
  HANDLE ProcessHeap; // rax
  HRESULT v8; // edi
  CInternetShortcutPropertyStore *v9; // rcx
  CInternetShortcutPropertyStore *v10; // rcx
  _QWORD *v11; // r15
  unsigned int v12; // r12d
  LPWSTR v13; // rbx
  size_t v14; // rdi
  int v15; // eax
  LPWSTR v16; // rcx
  GUID v17; // xmm6
  __int64 v18; // rsi
  BOOL v19; // edi
  __int64 (**v20)[3]; // r11
  unsigned int v21; // r10d
  __int64 (**v22)[3]; // r9
  unsigned int i; // ecx
  __int64 *v24; // r8
  __int64 v25; // rax
  __int64 *v26; // rax
  __int64 *v27; // rdi
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
    goto LABEL_81;
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
      goto LABEL_81;
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
          goto LABEL_79;
      }
      if ( pbstrOut && !StrCmpW(v13, pbstrOut) )
        goto LABEL_79;
      *(_QWORD *)&ppu.cbSize = 40;
      memset(&ppu.pszProtocol, 0, 32);
      v8 = ParseURLW(v13, &ppu);
      if ( v8 )
        goto LABEL_79;
      if ( v13 )
      {
        memset(&propvar_8, 0, sizeof(propvar_8));
        propvar_8.cbSize = 40;
        if ( ParseURLW(v13, &propvar_8) >= 0 && propvar_8.nScheme - 15 <= 2 )
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
        v20 = off_180599E10;
        v21 = 28;
        v22 = off_180599E18;
        goto LABEL_48;
      }
      if ( !memcmp_0(&Buf1, &FMTID_Intshcut, 0x10u) )
      {
        v20 = &off_180599CF0;
        v21 = 18;
        v22 = (__int64 (**)[3])&off_180599CF8;
LABEL_48:
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
              goto LABEL_58;
            }
          }
        }
        v8 = -2147467259;
        goto LABEL_76;
      }
      *(GUID *)&v38.vt = FMTID_Intshcut;
      *((_DWORD *)&v38.decVal + 4) = 2;
LABEL_58:
      if ( !v19 )
      {
        v27 = (__int64 *)(v18 + 64);
        if ( *(_QWORD *)(v18 + 64) )
          goto LABEL_69;
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
LABEL_69:
          v28 = *v27;
        }
        else
        {
          v28 = *(_QWORD *)(v18 + 72);
          if ( !v28 )
          {
            v8 = -2147418113;
            goto LABEL_79;
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
          goto LABEL_79;
        *(_DWORD *)(v18 + 40) = 1;
        goto LABEL_75;
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
LABEL_75:
          v17 = FMTID_Intshcut;
LABEL_76:
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
LABEL_79:
      CoTaskMemFree(v13);
    }
  }
LABEL_81:
  SysFreeString(pbstrOut);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002d784  mov     rax, rsp
0x18002d787  mov     [rax+18h], rbx
0x18002d78b  push    rbp
0x18002d78c  push    rsi
0x18002d78d  push    rdi
0x18002d78e  push    r12
0x18002d790  push    r13
0x18002d792  push    r14
0x18002d794  push    r15
0x18002d796  lea     rbp, [rax-5Fh]
0x18002d79a  sub     rsp, 0F0h
0x18002d7a1  movaps  xmmword ptr [rax-48h], xmm6
0x18002d7a5  mov     rax, cs:__security_cookie
0x18002d7ac  xor     rax, rsp
0x18002d7af  mov     [rbp+57h+var_48], rax
0x18002d7b3  mov     rax, [rcx+118h]
0x18002d7ba  xor     r13d, r13d
0x18002d7bd  mov     ebx, r8d
0x18002d7c0  mov     rsi, rdx
0x18002d7c3  mov     r14, rcx
0x18002d7c6  mov     r15d, 1
0x18002d7cc  test    rax, rax
0x18002d7cf  jnz     short loc_18002D845
0x18002d7d1  call    cs:__imp_GetProcessHeap
0x18002d7d8  nop     dword ptr [rax+rax+00h]
0x18002d7dd  mov     rcx, rax; hHeap
0x18002d7e0  lea     edx, [r15+7]; dwFlags
0x18002d7e4  lea     r8d, [r15+4Fh]; dwBytes
0x18002d7e8  call    cs:__imp_HeapAlloc
0x18002d7ef  nop     dword ptr [rax+rax+00h]
0x18002d7f4  test    rax, rax
0x18002d7f7  jnz     short loc_18002D7FF
0x18002d7f9  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x18002d7ff  lea     rcx, ??_7CInternetShortcutPropertyStore@@6BIPropertyStore@@@; const CInternetShortcutPropertyStore::`vftable'{for `IPropertyStore'}
0x18002d806  mov     [rax+20h], r15d
0x18002d80a  mov     [rax], rcx
0x18002d80d  lea     rcx, ??_7CInternetShortcutPropertyStore@@6BIPersistFile@@@; const CInternetShortcutPropertyStore::`vftable'{for `IPersistFile'}
0x18002d814  mov     [rax+8], rcx
0x18002d818  lea     rcx, ??_7CInternetShortcutPropertyStore@@6BIPersistStream@@@; const CInternetShortcutPropertyStore::`vftable'{for `IPersistStream'}
0x18002d81f  mov     [rax+10h], rcx
0x18002d823  lea     rcx, ??_7CInternetShortcutPropertyStore@@6BIObjectProvider@@@; const CInternetShortcutPropertyStore::`vftable'{for `IObjectProvider'}
0x18002d82a  mov     [rax+18h], rcx
0x18002d82e  mov     [rax+30h], r13
0x18002d832  mov     [rax+38h], r13
0x18002d836  mov     [rax+40h], r13
0x18002d83a  mov     [rax+48h], r13
0x18002d83e  mov     [r14+118h], rax
0x18002d845  movups  xmm1, xmmword ptr cs:FMTID_Intshcut.Data1
0x18002d84c  xor     ecx, ecx
0x18002d84e  mov     [rbp+57h+pbstrOut], r13
0x18002d852  mov     qword ptr [rbp+57h+var_C8], rcx
0x18002d856  lea     r8, [rsp+120h+propvar+8]; struct tagPROPVARIANT *
0x18002d85b  xorps   xmm0, xmm0
0x18002d85e  mov     [rbp+57h+var_68], 2
0x18002d865  mov     rcx, rax; this
0x18002d868  lea     rdx, [rbp+57h+Buf1]; struct _tagpropertykey *
0x18002d86c  movdqu  [rbp+57h+Buf1], xmm1
0x18002d871  mov     edi, r13d
0x18002d874  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002d879  call    ?GetValue@CInternetShortcutPropertyStore@@UEAAJAEBU_tagpropertykey@@PEAUtagPROPVARIANT@@@Z; CInternetShortcutPropertyStore::GetValue(_tagpropertykey const &,tagPROPVARIANT *)
0x18002d87e  test    eax, eax
0x18002d880  js      short loc_18002D8A8
0x18002d882  lea     rdx, [rbp+57h+pbstrOut]; pbstrOut
0x18002d886  lea     rcx, [rsp+120h+propvar+8]; propvar
0x18002d88b  call    cs:__imp_PropVariantToBSTR
0x18002d892  nop     dword ptr [rax+rax+00h]
0x18002d897  lea     rcx, [rsp+120h+propvar+8]; pvar
0x18002d89c  call    cs:__imp_PropVariantClear
0x18002d8a3  nop     dword ptr [rax+rax+00h]
0x18002d8a8  test    rsi, rsi
0x18002d8ab  jnz     loc_18002D942
0x18002d8b1  movups  xmm1, xmmword ptr cs:FMTID_Intshcut.Data1
0x18002d8b8  mov     rcx, [r14+118h]; this
0x18002d8bf  lea     r8, [rbp+57h+var_60]; struct tagPROPVARIANT *
0x18002d8c3  xorps   xmm0, xmm0
0x18002d8c6  mov     [rbp+57h+var_68], 2
0x18002d8cd  xor     eax, eax
0x18002d8cf  lea     rdx, [rbp+57h+Buf1]; struct _tagpropertykey *
0x18002d8d3  movdqu  [rbp+57h+Buf1], xmm1
0x18002d8d8  mov     qword ptr [rbp+57h+var_60+10h], rax
0x18002d8dc  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002d8e0  call    ?SetValue@CInternetShortcutPropertyStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CInternetShortcutPropertyStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)
0x18002d8e5  mov     edi, eax
0x18002d8e7  test    eax, eax
0x18002d8e9  js      short loc_18002D923
0x18002d8eb  mov     rcx, [r14+118h]; this
0x18002d8f2  lea     r8, [rsp+120h+propvar+8]; struct tagPROPVARIANT *
0x18002d8f7  xor     eax, eax
0x18002d8f9  mov     [rbp+57h+var_68], 3
0x18002d900  mov     qword ptr [rbp+57h+var_C8], rax
0x18002d904  lea     rdx, [rbp+57h+Buf1]; struct _tagpropertykey *
0x18002d908  xorps   xmm0, xmm0
0x18002d90b  lea     eax, [rsi+13h]
0x18002d90e  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002d913  mov     word ptr [rsp+120h+propvar+8], ax
0x18002d918  mov     dword ptr [rbp+57h+var_D0], r13d
0x18002d91c  call    ?SetValue@CInternetShortcutPropertyStore@@UEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@@Z; CInternetShortcutPropertyStore::SetValue(_tagpropertykey const &,tagPROPVARIANT const &)
0x18002d921  mov     edi, eax
0x18002d923  mov     rcx, [r14+5B0h]; pv
0x18002d92a  call    cs:__imp_CoTaskMemFree
0x18002d931  nop     dword ptr [rax+rax+00h]
0x18002d936  mov     [r14+5B0h], r13
0x18002d93d  jmp     loc_18002DE55
0x18002d942  mov     eax, ebx
0x18002d944  and     eax, r15d
0x18002d947  lea     r15, [r14+5B0h]
0x18002d94e  mov     rcx, [r15]; pv
0x18002d951  add     eax, 8
0x18002d954  mov     r12d, eax
0x18002d957  or      r12d, 2
0x18002d95b  test    bl, 2
0x18002d95e  cmovz   r12d, eax
0x18002d962  call    cs:__imp_CoTaskMemFree
0x18002d969  nop     dword ptr [rax+rax+00h]
0x18002d96e  xorps   xmm0, xmm0
0x18002d971  mov     [r15], r13
0x18002d974  xor     eax, eax
0x18002d976  lea     rdx, [rsp+120h+propvar+8]; ppu
0x18002d97b  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002d980  mov     rcx, rsi; pcszURL
0x18002d983  mov     dword ptr [rsp+120h+propvar+8], 28h ; '('
0x18002d98b  movups  [rbp+57h+var_C8], xmm0
0x18002d98f  mov     [rbp+57h+var_B8], rax
0x18002d993  call    cs:__imp_ParseURLW
0x18002d99a  nop     dword ptr [rax+rax+00h]
0x18002d99f  test    eax, eax
0x18002d9a1  js      short loc_18002D9BD
0x18002d9a3  cmp     dword ptr [rbp+57h+var_B8+4], 0Fh
0x18002d9a7  jnz     short loc_18002D9BD
0x18002d9a9  mov     rdx, r15; ppwsz
0x18002d9ac  mov     rcx, rsi; psz
0x18002d9af  call    cs:__imp_SHStrDupW
0x18002d9b6  nop     dword ptr [rax+rax+00h]
0x18002d9bb  mov     edi, eax
0x18002d9bd  test    edi, edi
0x18002d9bf  js      loc_18002DE55
0x18002d9c5  mov     ecx, 824h
0x18002d9ca  mov     [rbp+57h+ppv], r13
0x18002d9ce  mov     eax, 2
0x18002d9d3  mul     rcx
0x18002d9d6  test    rdx, rdx
0x18002d9d9  jnz     loc_18002DE50
0x18002d9df  mov     rcx, rax; cb
0x18002d9e2  call    cs:__imp_CoTaskMemAlloc
0x18002d9e9  nop     dword ptr [rax+rax+00h]
0x18002d9ee  mov     rbx, rax
0x18002d9f1  test    rax, rax
0x18002d9f4  jz      short loc_18002DA52
0x18002d9f6  lea     rdx, [rsp+120h+propvar]; ppMalloc
0x18002d9fb  mov     [rsp+120h+propvar], r13
0x18002da00  mov     ecx, 1; dwMemContext
0x18002da05  mov     rdi, r13
0x18002da08  call    cs:__imp_CoGetMalloc
0x18002da0f  nop     dword ptr [rax+rax+00h]
0x18002da14  test    eax, eax
0x18002da16  js      short loc_18002DA40
0x18002da18  mov     rcx, [rsp+120h+propvar]
0x18002da1d  mov     rdx, rbx
0x18002da20  mov     rax, [rcx]
0x18002da23  mov     rax, [rax+30h]
0x18002da27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da2c  mov     rcx, [rsp+120h+propvar]
0x18002da31  mov     rdi, rax
0x18002da34  mov     rdx, [rcx]
0x18002da37  mov     rax, [rdx+10h]
0x18002da3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002da40  mov     r8, rdi; Size
0x18002da43  xor     edx, edx; Val
0x18002da45  mov     rcx, rbx; void *
0x18002da48  call    memset_0
0x18002da4d  mov     edi, r13d
0x18002da50  jmp     short loc_18002DA57
0x18002da52  mov     edi, 8007000Eh
0x18002da57  test    edi, edi
0x18002da59  js      loc_18002DE55
0x18002da5f  xorps   xmm0, xmm0
0x18002da62  lea     rdx, [rsp+120h+propvar+8]; ppu
0x18002da67  xor     eax, eax
0x18002da69  mov     rcx, rsi; pcszURL
0x18002da6c  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002da71  mov     dword ptr [rsp+120h+propvar+8], 28h ; '('
0x18002da79  movups  [rbp+57h+var_C8], xmm0
0x18002da7d  mov     [rbp+57h+var_B8], rax
0x18002da81  call    cs:__imp_ParseURLW
0x18002da88  nop     dword ptr [rax+rax+00h]
0x18002da8d  test    eax, eax
0x18002da8f  js      short loc_18002DAAE
0x18002da91  cmp     dword ptr [rbp+57h+var_B8+4], 0Fh
0x18002da95  jnz     short loc_18002DAAE
0x18002da97  cmp     [r15], r13
0x18002da9a  jz      short loc_18002DAAE
0x18002da9c  mov     r8, rsi; unsigned __int16 *
0x18002da9f  mov     edx, 824h; unsigned __int64
0x18002daa4  mov     rcx, rbx; unsigned __int16 *
0x18002daa7  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002daac  jmp     short loc_18002DADB
0x18002daae  mov     [rsp+120h+var_F0], r13; int *
0x18002dab3  mov     r9, rbx; unsigned __int16 *
0x18002dab6  mov     [rsp+120h+var_F8], r13; int *
0x18002dabb  mov     r8d, 824h; unsigned int
0x18002dac1  mov     edx, r12d; unsigned int
0x18002dac4  mov     [rsp+120h+var_100], r13; struct IUnknown *
0x18002dac9  mov     rcx, rsi; unsigned __int16 *
0x18002dacc  call    ?IURLQualifyLib@@YAJPEBGKKPEAGPEAUIUnknown@@PEAH3@Z; IURLQualifyLib(ushort const *,ulong,ulong,ushort *,IUnknown *,int *,int *)
0x18002dad1  mov     edi, eax
0x18002dad3  test    eax, eax
0x18002dad5  js      loc_18002DE3F
0x18002dadb  mov     rdx, [rbp+57h+pbstrOut]; psz2
0x18002dadf  test    rdx, rdx
0x18002dae2  jz      short loc_18002DAFB
0x18002dae4  mov     rcx, rbx; psz1
0x18002dae7  call    cs:__imp_StrCmpW
0x18002daee  nop     dword ptr [rax+rax+00h]
0x18002daf3  test    eax, eax
0x18002daf5  jz      loc_18002DE3F
0x18002dafb  xorps   xmm0, xmm0
0x18002dafe  lea     rdx, [rbp+57h+ppu]; ppu
0x18002db02  mov     esi, 28h ; '('
0x18002db07  mov     rcx, rbx; pcszURL
0x18002db0a  mov     qword ptr [rbp+57h+ppu.cbSize], rsi
0x18002db0e  movups  xmmword ptr [rbp+57h+ppu.pszProtocol], xmm0
0x18002db12  movups  xmmword ptr [rbp+57h+ppu.pszSuffix], xmm0
0x18002db16  call    cs:__imp_ParseURLW
0x18002db1d  nop     dword ptr [rax+rax+00h]
0x18002db22  mov     edi, eax
0x18002db24  test    eax, eax
0x18002db26  jnz     loc_18002DE3F
0x18002db2c  test    rbx, rbx
0x18002db2f  jz      loc_18002DBFB
0x18002db35  xorps   xmm0, xmm0
0x18002db38  lea     rdx, [rsp+120h+propvar+8]; ppu
0x18002db3d  xor     eax, eax
0x18002db3f  mov     rcx, rbx; pcszURL
0x18002db42  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002db47  mov     dword ptr [rsp+120h+propvar+8], esi
0x18002db4b  movups  [rbp+57h+var_C8], xmm0
0x18002db4f  mov     [rbp+57h+var_B8], rax
0x18002db53  call    cs:__imp_ParseURLW
0x18002db5a  nop     dword ptr [rax+rax+00h]
0x18002db5f  test    eax, eax
0x18002db61  js      loc_18002DBFB
0x18002db67  mov     eax, dword ptr [rbp+57h+var_B8+4]
0x18002db6a  add     eax, 0FFFFFFF1h
0x18002db6d  cmp     eax, 2
0x18002db70  ja      loc_18002DBFB
0x18002db76  lea     rdx, [rsp+120h+propvar]; ppwsz
0x18002db7b  mov     [rsp+120h+propvar], r13
0x18002db80  mov     rcx, rbx; psz
0x18002db83  call    cs:__imp_SHStrDupW
0x18002db8a  nop     dword ptr [rax+rax+00h]
0x18002db8f  test    eax, eax
0x18002db91  js      short loc_18002DBFB
0x18002db93  mov     rcx, [rsp+120h+propvar]; pszFirst
0x18002db98  call    ?DetectSpecialUrlHacks@@YAJPEBG@Z; DetectSpecialUrlHacks(ushort const *)
0x18002db9d  mov     rcx, [rsp+120h+propvar]; lpsz
0x18002dba2  cmp     eax, 80070005h
0x18002dba7  jnz     short loc_18002DBEF
0x18002dba9  test    rcx, rcx
0x18002dbac  jz      short loc_18002DBD3
0x18002dbae  cmp     r13w, [rcx]
0x18002dbb2  jz      short loc_18002DBD3
0x18002dbb4  mov     eax, 1
0x18002dbb9  cmp     ax, [rcx]
0x18002dbbc  jz      short loc_18002DBCF
0x18002dbbe  call    cs:__imp_CharNextW
0x18002dbc5  nop     dword ptr [rax+rax+00h]
0x18002dbca  mov     rcx, rax
0x18002dbcd  jmp     short loc_18002DBAE
0x18002dbcf  mov     [rcx], r13w
0x18002dbd3  mov     rcx, rbx; pv
0x18002dbd6  call    cs:__imp_CoTaskMemFree
0x18002dbdd  nop     dword ptr [rax+rax+00h]
0x18002dbe2  mov     rbx, [rsp+120h+propvar]
0x18002dbe7  mov     rcx, r13; pv
0x18002dbea  mov     [rsp+120h+propvar], rcx
0x18002dbef  call    cs:__imp_CoTaskMemFree
0x18002dbf6  nop     dword ptr [rax+rax+00h]
0x18002dbfb  movups  xmm6, xmmword ptr cs:FMTID_Intshcut.Data1
0x18002dc02  mov     rsi, [r14+118h]
0x18002dc09  lea     rdx, FMTID_InternetSite; Buf2
0x18002dc10  xor     eax, eax
0x18002dc12  mov     [rbp+57h+var_68], 2
0x18002dc19  mov     qword ptr [rbp+57h+var_C8], rax
0x18002dc1d  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18002dc21  xorps   xmm0, xmm0
0x18002dc24  mov     eax, 1Fh
0x18002dc29  movups  xmmword ptr [rsp+120h+propvar+8], xmm0
0x18002dc2e  mov     word ptr [rsp+120h+propvar+8], ax
0x18002dc33  xor     eax, eax
0x18002dc35  movups  [rbp+57h+Buf1], xmm6
0x18002dc39  mov     [rbp+57h+var_D0], rbx
0x18002dc3d  movups  xmmword ptr [rbp+57h+var_60], xmm0
0x18002dc41  lea     r15d, [rax+10h]
0x18002dc45  mov     dword ptr [rbp+57h+var_60+10h], eax
0x18002dc48  mov     r8d, r15d; Size
0x18002dc4b  call    memcmp_0
0x18002dc50  test    eax, eax
0x18002dc52  lea     rdx, FMTID_InternetSite; Buf2
0x18002dc59  mov     edi, r13d
0x18002dc5c  lea     rcx, [rbp+57h+Buf1]; Buf1
  ... truncated ...
```
