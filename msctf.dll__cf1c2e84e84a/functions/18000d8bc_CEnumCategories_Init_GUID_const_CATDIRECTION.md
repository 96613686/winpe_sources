# CEnumCategories::_Init(_GUID const &,CATDIRECTION)

- ea: `0x18000d8bc`
- end: `0x18000deee`
- name: `?_Init@CEnumCategories@@QEAAHAEBU_GUID@@W4CATDIRECTION@@@Z`
- size: `1586`
- prototype: `int __high(const struct _GUID *, enum CATDIRECTION)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18006802c`
- `0x18006c1e8`

## callees

- `0x18000d8bc`
- `0x18000fac0`
- `0x180024650`
- `0x1800250fc`
- `0x18002ba50`
- `0x18004e2b0`
- `0x1800539d8`
- `0x180078054`
- `0x1800935f0`
- `0x1800a18d4`
- `0x180106a60`

## import_xrefs

- `msvcrt!wcsnlen` at `0x18000dad6`
- `msvcrt!wcsnlen` at `0x18000daec`
- `msvcrt!wcsnlen` at `0x18000db3d`
- `msvcrt!wcsnlen` at `0x18000dd46`
- `msvcrt!wcsnlen` at `0x18000dad6`
- `msvcrt!wcsnlen` at `0x18000daec`
- `msvcrt!wcsnlen` at `0x18000db3d`
- `msvcrt!wcsnlen` at `0x18000dd46`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000deb4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000deb4`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d946`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d946`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000da17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dc5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000da17`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000dc5e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000da42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dc86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dca4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dec2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000da42`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dc86`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dca4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000dec2`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000dda3`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000dda3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000da96`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000dd18`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000da96`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000dd18`

## pseudocode

```c
__int64 __fastcall CEnumCategories::_Init(__int64 a1, const struct _GUID *a2, int a3)
{
  __int64 v3; // rbx
  unsigned int v6; // r15d
  HKEY v7; // r12
  const wchar_t *v8; // rax
  CCatGUIDTbl *v9; // rcx
  unsigned int Guid; // edx
  unsigned int v11; // eax
  struct _SHARED_GUID_ARRAY *v12; // rax
  LSTATUS v13; // ebx
  DWORD v14; // edx
  LSTATUS v15; // eax
  HKEY v16; // r14
  size_t v17; // rbx
  size_t v18; // rax
  int v19; // eax
  WCHAR *v20; // r9
  int v21; // edx
  int i; // r8d
  __int64 v23; // r10
  __int64 v24; // rcx
  const struct _GUID *v25; // r11
  HKEY v26; // rbx
  LSTATUS v27; // ebx
  DWORD v28; // ebx
  DWORD v29; // edx
  LSTATUS v30; // eax
  unsigned int v31; // ecx
  _DWORD *v32; // rax
  CCatGUIDTbl *v33; // rcx
  unsigned int v34; // eax
  signed int v35; // edx
  __int64 v36; // r14
  _DWORD *v37; // rax
  unsigned int v39; // [rsp+44h] [rbp-344h]
  DWORD dwIndex; // [rsp+4Ch] [rbp-33Ch]
  unsigned int v41; // [rsp+54h] [rbp-334h]
  void **v42; // [rsp+58h] [rbp-330h] BYREF
  HKEY v43; // [rsp+60h] [rbp-328h]
  DWORD cchName; // [rsp+68h] [rbp-320h] BYREF
  DWORD v45; // [rsp+70h] [rbp-318h]
  DWORD v46; // [rsp+78h] [rbp-310h] BYREF
  HKEY v47; // [rsp+80h] [rbp-308h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-300h] BYREF
  HKEY v49; // [rsp+90h] [rbp-2F8h] BYREF
  __int64 v50; // [rsp+98h] [rbp-2F0h]
  DWORD v51; // [rsp+A0h] [rbp-2E8h]
  unsigned int v52; // [rsp+A4h] [rbp-2E4h]
  unsigned int v53; // [rsp+A8h] [rbp-2E0h]
  HKEY hKey; // [rsp+B0h] [rbp-2D8h]
  const wchar_t *v55; // [rsp+B8h] [rbp-2D0h]
  const struct _GUID *v56; // [rsp+C0h] [rbp-2C8h]
  HKEY v57; // [rsp+C8h] [rbp-2C0h]
  __int64 v58; // [rsp+D0h] [rbp-2B8h]
  HKEY v59; // [rsp+E0h] [rbp-2A8h]
  __int64 v60; // [rsp+E8h] [rbp-2A0h]
  WCHAR Source[40]; // [rsp+F0h] [rbp-298h] BYREF
  wchar_t Name[256]; // [rsp+140h] [rbp-248h] BYREF

  v3 = a3;
  v56 = a2;
  v6 = 0;
  v7 = 0;
  v59 = 0;
  v8 = L"Category\\";
  if ( a3 )
    v8 = (const wchar_t *)L"Item\\";
  v55 = v8;
  dwIndex = 0;
  v41 = 64;
  v39 = 0;
  if ( dword_180140688 )
  {
    EnterCriticalSection(&g_cs);
    if ( (unsigned int)CCategoryMgr::InitGlobal() )
    {
      Guid = CCatGUIDTbl::FindGuid(v9, a2);
      if ( Guid || (Guid = CCatGUIDTbl::Add(v33, a2)) != 0 )
      {
        v34 = (Guid & 0x1F) - 1;
        if ( v34 < 0x1F )
        {
          if ( *((_QWORD *)CCategoryMgr::_pCatGUIDTbl + v34)
            && (v35 = Guid >> 5, _mm_lfence(), v35 < *(_DWORD *)(*((_QWORD *)CCategoryMgr::_pCatGUIDTbl + v34) + 16LL)) )
          {
            _mm_lfence();
            v36 = *(_QWORD *)(*((_QWORD *)CCategoryMgr::_pCatGUIDTbl + v34) + 8LL)
                + *(_DWORD *)(*((_QWORD *)CCategoryMgr::_pCatGUIDTbl + v34) + 20LL) * v35;
            v50 = v36;
          }
          else
          {
            v36 = 0;
            v50 = 0;
          }
          if ( v36 )
          {
            v58 = v3;
            v37 = *(_DWORD **)(v36 + 8 * v3 + 16);
            *(_QWORD *)(a1 + 32) = v37;
            if ( v37 )
            {
              ++*v37;
              v6 = 1;
            }
            else
            {
              v12 = SGA_Alloc(0x40u);
              *(_QWORD *)(a1 + 32) = v12;
              if ( v12 )
              {
                *(_DWORD *)v12 = 1;
                v60 = -2147483646;
                phkResult = 0;
                hKey = 0;
                v13 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\CTF\\TIP\\", 0, 0x20019u, &phkResult);
                if ( !v13 )
                {
                  v13 = 0;
                  v7 = phkResult;
                  v59 = phkResult;
                }
                if ( hKey )
                  RegCloseKey(hKey);
                if ( !v13 )
                {
                  while ( 1 )
                  {
                    v14 = dwIndex++;
                    v51 = dwIndex;
                    cchName = 256;
                    v15 = RegEnumKeyExW(v7, v14, Name, &cchName, 0, 0, 0, 0);
                    *(wchar_t *)((char *)Name + (v15 == 0 ? 0x1FE : 0)) = 0;
                    if ( v15 )
                      break;
                    v42 = &CPreloadRegKey::`vftable';
                    v16 = 0;
                    v43 = 0;
                    v17 = wcsnlen(Name, 0x100u);
                    v18 = wcsnlen(Name, 0x100u);
                    if ( (unsigned int)StringCchPrintfW(&Name[v18], 256 - v17, L"\\%s%s", L"Category\\", v55)
                      || (v19 = wcsnlen(Name, 0x100u), (unsigned int)(v19 + 39) > 0x100) )
                    {
                      v42 = &CPreloadRegKey::`vftable';
                    }
                    else
                    {
                      v20 = &Name[v19];
                      *v20 = 123;
                      v21 = 1;
                      for ( i = 0; ; ++i )
                      {
                        v23 = v21;
                        if ( (unsigned __int64)i >= 0x14 || v21 >= 36 )
                          break;
                        ++v21;
                        v24 = *((unsigned __int8 *)qword_18011F820 + i);
                        if ( (_BYTE)v24 == 45 )
                        {
                          v20[v23] = 45;
                        }
                        else
                        {
                          v25 = v56;
                          v20[v23] = word_18011F7F0[(unsigned __int64)*((unsigned __int8 *)&v56->Data1 + v24) >> 4];
                          v20[v21++] = word_18011F7F0[*((_BYTE *)&v25->Data1 + v24) & 0xF];
                        }
                      }
                      v20[v21] = 125;
                      v20[v21 + 1] = 0;
                      v26 = v7;
                      v57 = v7;
                      v49 = 0;
                      v47 = 0;
                      if ( v7 == HKEY_CURRENT_USER )
                      {
                        if ( !RegOpenCurrentUser(0x20019u, &v47) )
                          v26 = v47;
                        v57 = v26;
                      }
                      v27 = RegOpenKeyExW(v26, Name, 0, 0x20019u, &v49);
                      if ( !v27 )
                      {
                        v27 = 0;
                        v16 = v49;
                        v43 = v49;
                      }
                      if ( v47 )
                        RegCloseKey(v47);
                      if ( !v27 )
                      {
                        v28 = 0;
                        v45 = 0;
                        while ( 1 )
                        {
                          v29 = v28++;
                          v45 = v28;
                          v46 = 39;
                          v30 = RegEnumKeyExW(v16, v29, Source, &v46, 0, 0, 0, 0);
                          *(WCHAR *)((char *)Source + (v30 == 0 ? 0x4C : 0)) = 0;
                          if ( v30 )
                            break;
                          if ( wcsnlen(Source, 0x27u) == 38 )
                          {
                            v11 = v39;
                            v31 = v41;
                            if ( v39 >= v41 )
                            {
                              v41 += 64;
                              v52 = v31 + 64;
                              if ( !(unsigned int)SGA_ReAlloc((struct _SHARED_GUID_ARRAY **)(a1 + 32), v31 + 64) )
                              {
                                v42 = &CPreloadRegKey::`vftable';
                                CInputDllRegKey::Close((CInputDllRegKey *)&v42);
                                goto LABEL_60;
                              }
                              v11 = v39;
                            }
                            StringToCLSID(Source, (struct _GUID *)(16LL * v11 + *(_QWORD *)(a1 + 32) + 8LL));
                            v53 = ++v39;
                          }
                        }
                      }
                      v42 = &CPreloadRegKey::`vftable';
                      if ( v16 )
                      {
                        RegCloseKey(v16);
                        v43 = 0;
                      }
                    }
                  }
                  if ( (unsigned int)SGA_ReAlloc((struct _SHARED_GUID_ARRAY **)(a1 + 32), v39) )
                  {
                    v6 = 1;
                    *(_DWORD *)(*(_QWORD *)(a1 + 32) + 4LL) = v39;
                    v32 = *(_DWORD **)(a1 + 32);
                    *(_QWORD *)(v50 + 8 * v58 + 16) = v32;
                    ++*v32;
                  }
                }
              }
            }
          }
        }
      }
    }
LABEL_60:
    if ( dword_180140688 )
      LeaveCriticalSection(&g_cs);
  }
  if ( v7 )
    RegCloseKey(v7);
  return v6;
}

```

## disassembly

```asm
0x18000d8bc  push    rbx
0x18000d8be  push    rsi
0x18000d8bf  push    rdi
0x18000d8c0  push    r12
0x18000d8c2  push    r13
0x18000d8c4  push    r14
0x18000d8c6  push    r15
0x18000d8c8  sub     rsp, 350h
0x18000d8cf  mov     rax, cs:__security_cookie
0x18000d8d6  xor     rax, rsp
0x18000d8d9  mov     [rsp+388h+var_48], rax
0x18000d8e1  movsxd  rbx, r8d
0x18000d8e4  mov     rsi, rdx
0x18000d8e7  mov     [rsp+388h+var_2C8], rdx
0x18000d8ef  mov     r13, rcx
0x18000d8f2  xor     edi, edi
0x18000d8f4  mov     r15d, edi
0x18000d8f7  mov     [rsp+388h+var_340], edi
0x18000d8fb  mov     r12d, edi
0x18000d8fe  mov     [rsp+388h+var_2A8], rdi
0x18000d906  lea     rcx, dwDisposition; "Item\\"
0x18000d90d  lea     rax, aCategory; "Category\\"
0x18000d914  test    r8d, r8d
0x18000d917  cmovnz  rax, rcx
0x18000d91b  mov     [rsp+388h+var_2D0], rax
0x18000d923  mov     [rsp+388h+dwIndex], edi
0x18000d927  mov     [rsp+388h+var_334], 40h ; '@'
0x18000d92f  mov     [rsp+388h+var_344], edi
0x18000d933  cmp     cs:dword_180140688, edi
0x18000d939  jz      loc_18000DEBA
0x18000d93f  lea     rcx, ?g_cs@@3VCCicCriticalSectionStatic@@A; lpCriticalSection
0x18000d946  call    cs:__imp_EnterCriticalSection
0x18000d94c  nop
0x18000d94d  call    ?InitGlobal@CCategoryMgr@@SAHXZ; CCategoryMgr::InitGlobal(void)
0x18000d952  test    eax, eax
0x18000d954  jnz     loc_18000DDEF
0x18000d95a  jmp     loc_18000DEA5
0x18000d95f  mov     rdx, rsi; struct _GUID *
0x18000d962  call    ?Add@CCatGUIDTbl@@QEAAKAEBU_GUID@@@Z; CCatGUIDTbl::Add(_GUID const &)
0x18000d967  mov     edx, eax
0x18000d969  test    eax, eax
0x18000d96b  jnz     loc_18000DE01
0x18000d971  jmp     loc_18000DEA5
0x18000d976  jmp     loc_18000DEA5
0x18000d97b  jmp     loc_18000DEA5
0x18000d980  add     ecx, 40h ; '@'
0x18000d983  mov     [rsp+388h+var_334], ecx
0x18000d987  mov     [rsp+388h+var_2E4], ecx
0x18000d98e  mov     edx, ecx; unsigned int
0x18000d990  lea     rcx, [r13+20h]; struct _SHARED_GUID_ARRAY **
0x18000d994  call    ?SGA_ReAlloc@@YAHPEAPEAU_SHARED_GUID_ARRAY@@K@Z; SGA_ReAlloc(_SHARED_GUID_ARRAY * *,ulong)
0x18000d999  test    eax, eax
0x18000d99b  jnz     short loc_18000D9B8
0x18000d99d  lea     rax, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x18000d9a4  mov     [rsp+388h+var_330], rax
0x18000d9a9  lea     rcx, [rsp+388h+var_330]; this
0x18000d9ae  call    ?Close@CInputDllRegKey@@QEAAJXZ; CInputDllRegKey::Close(void)
0x18000d9b3  jmp     loc_18000DEA5
0x18000d9b8  mov     eax, [rsp+388h+var_344]
0x18000d9bc  jmp     loc_18000DD62
0x18000d9c1  mov     ecx, 40h ; '@'; unsigned int
0x18000d9c6  call    ?SGA_Alloc@@YAPEAU_SHARED_GUID_ARRAY@@K@Z; SGA_Alloc(ulong)
0x18000d9cb  mov     [r13+20h], rax
0x18000d9cf  test    rax, rax
0x18000d9d2  jz      short loc_18000D976
0x18000d9d4  mov     esi, 1
0x18000d9d9  mov     [rax], esi
0x18000d9db  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d9e2  mov     [rsp+388h+var_2A0], rcx
0x18000d9ea  mov     [rsp+388h+var_300], rdi
0x18000d9f2  mov     [rsp+388h+hKey], rdi
0x18000d9fa  lea     rax, [rsp+388h+var_300]
0x18000da02  mov     [rsp+388h+phkResult], rax; phkResult
0x18000da07  mov     r9d, 20019h; samDesired
0x18000da0d  xor     r8d, r8d; ulOptions
0x18000da10  lea     rdx, ?c_szCTFTIPKey@@3QBGB; "SOFTWARE\\Microsoft\\CTF\\TIP\\"
0x18000da17  call    cs:__imp_RegOpenKeyExW
0x18000da1d  mov     ebx, eax
0x18000da1f  test    eax, eax
0x18000da21  jnz     short loc_18000DA35
0x18000da23  mov     ebx, edi
0x18000da25  mov     r12, [rsp+388h+var_300]
0x18000da2d  mov     [rsp+388h+var_2A8], r12
0x18000da35  mov     rcx, [rsp+388h+hKey]; hKey
0x18000da3d  test    rcx, rcx
0x18000da40  jz      short loc_18000DA48
0x18000da42  call    cs:__imp_RegCloseKey
0x18000da48  test    ebx, ebx
0x18000da4a  jnz     loc_18000D97B
0x18000da50  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x18000da57  mov     eax, [rsp+388h+dwIndex]
0x18000da5b  mov     edx, eax; dwIndex
0x18000da5d  add     eax, esi
0x18000da5f  mov     [rsp+388h+dwIndex], eax
0x18000da63  mov     [rsp+388h+var_2E8], eax
0x18000da6a  mov     [rsp+388h+cchName], 100h
0x18000da72  mov     [rsp+388h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18000da77  mov     [rsp+388h+lpcchClass], rdi; lpcchClass
0x18000da7c  mov     [rsp+388h+lpClass], rdi; lpClass
0x18000da81  mov     [rsp+388h+phkResult], rdi; lpReserved
0x18000da86  lea     r9, [rsp+388h+cchName]; lpcchName
0x18000da8b  lea     r8, [rsp+388h+Name]; lpName
0x18000da93  mov     rcx, r12; hKey
0x18000da96  call    cs:__imp_RegEnumKeyExW
0x18000da9c  mov     ecx, eax
0x18000da9e  neg     ecx
0x18000daa0  sbb     rdx, rdx
0x18000daa3  not     rdx
0x18000daa6  and     edx, 1FEh
0x18000daac  mov     [rsp+rdx+388h+Name], di
0x18000dab4  test    eax, eax
0x18000dab6  jnz     loc_18000DCC2
0x18000dabc  mov     [rsp+388h+var_330], rbx
0x18000dac1  mov     r14, rdi
0x18000dac4  mov     [rsp+388h+var_328], rdi
0x18000dac9  mov     edx, 100h; MaxCount
0x18000dace  lea     rcx, [rsp+388h+Name]; Source
0x18000dad6  call    cs:__imp_wcsnlen
0x18000dadc  mov     rbx, rax
0x18000dadf  mov     edx, 100h; MaxCount
0x18000dae4  lea     rcx, [rsp+388h+Name]; Source
0x18000daec  call    cs:__imp_wcsnlen
0x18000daf2  mov     edx, 100h
0x18000daf7  sub     rdx, rbx; unsigned __int64
0x18000dafa  lea     rcx, [rsp+388h+Name]
0x18000db02  lea     rcx, [rcx+rax*2]; unsigned __int16 *
0x18000db06  mov     rax, [rsp+388h+var_2D0]
0x18000db0e  mov     [rsp+388h+phkResult], rax
0x18000db13  lea     r9, Source; "Category\\"
0x18000db1a  lea     r8, aSS_1; "\\%s%s"
0x18000db21  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000db26  test    eax, eax
0x18000db28  jnz     loc_18000DCB4
0x18000db2e  mov     ebx, 100h
0x18000db33  mov     edx, ebx; MaxCount
0x18000db35  lea     rcx, [rsp+388h+Name]; Source
0x18000db3d  call    cs:__imp_wcsnlen
0x18000db43  lea     ecx, [rax+27h]
0x18000db46  cmp     ecx, ebx
0x18000db48  ja      loc_18000DCB4
0x18000db4e  mov     [rsp+388h+var_338], edi
0x18000db52  mov     [rsp+388h+var_348], edi
0x18000db56  cdqe
0x18000db58  lea     r9, [rsp+388h+Name]
0x18000db60  lea     r9, [r9+rax*2]
0x18000db64  mov     [rsp+388h+var_348], edi
0x18000db68  mov     eax, 7Bh ; '{'
0x18000db6d  mov     [r9], ax
0x18000db71  mov     edx, esi
0x18000db73  mov     [rsp+388h+var_348], edx
0x18000db77  mov     r8d, edi
0x18000db7a  mov     [rsp+388h+var_338], edi
0x18000db7e  lea     rbx, __ImageBase
0x18000db85  movsxd  r10, edx
0x18000db88  movsxd  rax, r8d
0x18000db8b  cmp     rax, 14h
0x18000db8f  jnb     short loc_18000DBFA
0x18000db91  cmp     edx, 24h ; '$'
0x18000db94  jge     short loc_18000DBFA
0x18000db96  inc     edx
0x18000db98  movzx   ecx, byte ptr [rax+rbx+11F820h]
0x18000dba0  mov     eax, 2Dh ; '-'
0x18000dba5  mov     [rsp+388h+var_348], edx
0x18000dba9  cmp     cl, al
0x18000dbab  jz      short loc_18000DBF3
0x18000dbad  mov     r11, [rsp+388h+var_2C8]
0x18000dbb5  movzx   eax, byte ptr [rcx+r11]
0x18000dbba  shr     rax, 4
0x18000dbbe  movzx   eax, ds:rva word_18011F7F0[rbx+rax*2]
0x18000dbc6  mov     [r9+r10*2], ax
0x18000dbcb  movzx   eax, byte ptr [rcx+r11]
0x18000dbd0  and     eax, 0Fh
0x18000dbd3  movsxd  rcx, edx
0x18000dbd6  movzx   eax, ds:rva word_18011F7F0[rbx+rax*2]
0x18000dbde  mov     [r9+rcx*2], ax
0x18000dbe3  inc     edx
0x18000dbe5  mov     [rsp+388h+var_348], edx
0x18000dbe9  add     r8d, esi
0x18000dbec  mov     [rsp+388h+var_338], r8d
0x18000dbf1  jmp     short loc_18000DB85
0x18000dbf3  mov     [r9+r10*2], ax
0x18000dbf8  jmp     short loc_18000DBE9
0x18000dbfa  movsxd  rax, edx
0x18000dbfd  mov     ecx, 7Dh ; '}'
0x18000dc02  mov     [r9+rax*2], cx
0x18000dc07  add     edx, esi
0x18000dc09  mov     [rsp+388h+var_348], edx
0x18000dc0d  movsxd  rax, edx
0x18000dc10  mov     [r9+rax*2], di
0x18000dc15  mov     rbx, r12
0x18000dc18  mov     [rsp+388h+var_2C0], rbx
0x18000dc20  mov     [rsp+388h+var_2F8], rdi
0x18000dc28  mov     [rsp+388h+var_308], rdi
0x18000dc30  cmp     r12, 0FFFFFFFF80000001h
0x18000dc37  jz      loc_18000DD96
0x18000dc3d  lea     rax, [rsp+388h+var_2F8]
0x18000dc45  mov     [rsp+388h+phkResult], rax; phkResult
0x18000dc4a  mov     r9d, 20019h; samDesired
0x18000dc50  xor     r8d, r8d; ulOptions
0x18000dc53  lea     rdx, [rsp+388h+Name]; lpSubKey
0x18000dc5b  mov     rcx, rbx; hKey
0x18000dc5e  call    cs:__imp_RegOpenKeyExW
0x18000dc64  mov     ebx, eax
0x18000dc66  test    eax, eax
0x18000dc68  jnz     short loc_18000DC79
0x18000dc6a  mov     ebx, edi
0x18000dc6c  mov     r14, [rsp+388h+var_2F8]
0x18000dc74  mov     [rsp+388h+var_328], r14
0x18000dc79  mov     rcx, [rsp+388h+var_308]; hKey
0x18000dc81  test    rcx, rcx
0x18000dc84  jz      short loc_18000DC8C
0x18000dc86  call    cs:__imp_RegCloseKey
0x18000dc8c  test    ebx, ebx
0x18000dc8e  jz      short loc_18000DCDE
0x18000dc90  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x18000dc97  mov     [rsp+388h+var_330], rbx
0x18000dc9c  test    r14, r14
0x18000dc9f  jz      short loc_18000DCAF
0x18000dca1  mov     rcx, r14; hKey
0x18000dca4  call    cs:__imp_RegCloseKey
0x18000dcaa  mov     [rsp+388h+var_328], rdi
0x18000dcaf  jmp     loc_18000DA57
0x18000dcb4  lea     rbx, ??_7CPreloadRegKey@@6B@; const CPreloadRegKey::`vftable'
0x18000dcbb  mov     [rsp+388h+var_330], rbx
0x18000dcc0  jmp     short loc_18000DCAF
0x18000dcc2  mov     ebx, [rsp+388h+var_344]
0x18000dcc6  mov     edx, ebx; unsigned int
0x18000dcc8  lea     rcx, [r13+20h]; struct _SHARED_GUID_ARRAY **
0x18000dccc  call    ?SGA_ReAlloc@@YAHPEAPEAU_SHARED_GUID_ARRAY@@K@Z; SGA_ReAlloc(_SHARED_GUID_ARRAY * *,ulong)
0x18000dcd1  test    eax, eax
0x18000dcd3  jnz     loc_18000DDC1
0x18000dcd9  jmp     loc_18000DEA5
0x18000dcde  mov     ebx, edi
0x18000dce0  mov     [rsp+388h+var_318], ebx
0x18000dce4  mov     edx, ebx; dwIndex
0x18000dce6  add     ebx, esi
0x18000dce8  mov     [rsp+388h+var_318], ebx
0x18000dcec  mov     [rsp+388h+var_310], 27h ; '''
0x18000dcf4  mov     [rsp+388h+lpftLastWriteTime], rdi; lpftLastWriteTime
0x18000dcf9  mov     [rsp+388h+lpcchClass], rdi; lpcchClass
0x18000dcfe  mov     [rsp+388h+lpClass], rdi; lpClass
0x18000dd03  mov     [rsp+388h+phkResult], rdi; lpReserved
0x18000dd08  lea     r9, [rsp+388h+var_310]; lpcchName
0x18000dd0d  lea     r8, [rsp+388h+Source]; lpName
0x18000dd15  mov     rcx, r14; hKey
0x18000dd18  call    cs:__imp_RegEnumKeyExW
0x18000dd1e  mov     ecx, eax
0x18000dd20  neg     ecx
0x18000dd22  sbb     rdx, rdx
0x18000dd25  not     rdx
0x18000dd28  and     edx, 4Ch
0x18000dd2b  mov     [rsp+rdx+388h+Source], di
0x18000dd33  test    eax, eax
0x18000dd35  jnz     loc_18000DC90
0x18000dd3b  lea     edx, [rax+27h]; MaxCount
0x18000dd3e  lea     rcx, [rsp+388h+Source]; Source
0x18000dd46  call    cs:__imp_wcsnlen
0x18000dd4c  cmp     rax, 26h ; '&'
0x18000dd50  jnz     short loc_18000DD91
0x18000dd52  mov     eax, [rsp+388h+var_344]
0x18000dd56  mov     ecx, [rsp+388h+var_334]
0x18000dd5a  cmp     eax, ecx
0x18000dd5c  jnb     loc_18000D980
0x18000dd62  mov     ecx, eax
0x18000dd64  shl     rcx, 4
0x18000dd68  mov     rdx, [r13+20h]
0x18000dd6c  add     rdx, 8
0x18000dd70  add     rdx, rcx; struct _GUID *
0x18000dd73  lea     rcx, [rsp+388h+Source]; unsigned __int16 *
0x18000dd7b  call    ?StringToCLSID@@YAHPEBGPEAU_GUID@@@Z; StringToCLSID(ushort const *,_GUID *)
0x18000dd80  mov     eax, [rsp+388h+var_344]
0x18000dd84  add     eax, esi
0x18000dd86  mov     [rsp+388h+var_344], eax
0x18000dd8a  mov     [rsp+388h+var_2E0], eax
0x18000dd91  jmp     loc_18000DCE4
0x18000dd96  lea     rdx, [rsp+388h+var_308]; phkResult
0x18000dd9e  mov     ecx, 20019h; samDesired
0x18000dda3  call    cs:__imp_RegOpenCurrentUser
0x18000dda9  test    eax, eax
0x18000ddab  cmovz   rbx, [rsp+388h+var_308]
0x18000ddb4  mov     [rsp+388h+var_2C0], rbx
0x18000ddbc  jmp     loc_18000DC3D
0x18000ddc1  mov     r15d, esi
0x18000ddc4  mov     [rsp+388h+var_340], esi
0x18000ddc8  mov     rax, [r13+20h]
0x18000ddcc  mov     [rax+4], ebx
0x18000ddcf  mov     rax, [r13+20h]
0x18000ddd3  mov     rcx, [rsp+388h+var_2F0]
0x18000dddb  mov     rdx, [rsp+388h+var_2B8]
0x18000dde3  mov     [rcx+rdx*8+10h], rax
0x18000dde8  add     [rax], esi
0x18000ddea  jmp     loc_18000DEA5
0x18000ddef  mov     rdx, rsi; struct _GUID *
0x18000ddf2  call    ?FindGuid@CCatGUIDTbl@@QEAAKAEBU_GUID@@@Z; CCatGUIDTbl::FindGuid(_GUID const &)
0x18000ddf7  mov     edx, eax
0x18000ddf9  test    eax, eax
0x18000ddfb  jz      loc_18000D95F
0x18000de01  mov     eax, edx
0x18000de03  and     eax, 1Fh
0x18000de06  dec     eax
  ... truncated ...
```
