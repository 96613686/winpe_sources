# DeleteCrcsForSettingsGroupInternal(PackageContext *,_MVProvisionData *)

- ea: `0x180033fa0`
- end: `0x18003437a`
- name: `?DeleteCrcsForSettingsGroupInternal@@YAJPEAUPackageContext@@PEAU_MVProvisionData@@@Z`
- size: `986`
- prototype: `__int64 __fastcall(struct PackageContext *, struct _MVProvisionData *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180033ecc`

## callees

- `0x1800098dc`
- `0x180009900`
- `0x18000b030`
- `0x18000b31c`
- `0x180010ad8`
- `0x180021c5c`
- `0x180021f40`
- `0x180033fa0`
- `0x180034380`
- `0x180043750`

## import_xrefs

- `msvcrt!wcsstr` at `0x180034196`
- `msvcrt!wcsstr` at `0x180034196`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003425c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003426e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800342c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800342d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180034300`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003434a`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003425c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003426e`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800342c0`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800342d2`
- `msvcrt!??3@YAXPEAX@Z` at `0x180034300`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003434a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034049`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180034049`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180034173`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003421a`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180034173`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18003421a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800342ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034338`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800342ee`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180034338`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800342a2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x1800342a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800340b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800340b7`

## string_xrefs

- `0x180033ffe`: `onecoreuap\admin\prov\multivariant\common\src\crccache.cpp`
- `0x180034061`: `onecoreuap\admin\prov\multivariant\common\src\crccache.cpp`
- `0x180034237`: `onecoreuap\admin\prov\multivariant\common\src\crccache.cpp`
- `0x18003431d`: `onecoreuap\admin\prov\multivariant\common\src\crccache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeleteCrcsForSettingsGroupInternal(struct PackageContext *a1, struct _MVProvisionData *a2)
{
  int CachedSettingRegPath; // eax
  unsigned int v4; // ebx
  const WCHAR *v5; // rdx
  unsigned int v6; // eax
  __int64 v7; // rdx
  char *v8; // rdx
  unsigned __int64 v9; // r8
  WCHAR *v10; // rdi
  DWORD v11; // r14d
  char *v12; // rsi
  unsigned int v13; // eax
  WCHAR *v14; // rbx
  const wchar_t *v15; // rdx
  unsigned __int64 v16; // r8
  LPCWSTR i; // rdi
  const WCHAR *v18; // rdx
  int phkResult; // [rsp+20h] [rbp-99h]
  unsigned int phkResulta; // [rsp+20h] [rbp-99h]
  unsigned int phkResultb; // [rsp+20h] [rbp-99h]
  DWORD cbMaxValueNameLen; // [rsp+60h] [rbp-59h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-51h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-49h] BYREF
  LPCWSTR v26[2]; // [rsp+78h] [rbp-41h] BYREF
  WCHAR *v27; // [rsp+88h] [rbp-31h]
  LPWSTR lpValueName[2]; // [rsp+90h] [rbp-29h] BYREF
  __int64 v29; // [rsp+A0h] [rbp-19h]
  LPCWSTR lpSubKey[2]; // [rsp+A8h] [rbp-11h] BYREF
  __int64 v31; // [rsp+B8h] [rbp-1h]
  unsigned __int64 v32; // [rsp+C0h] [rbp+7h]
  wchar_t *SubStr[2]; // [rsp+C8h] [rbp+Fh] BYREF
  __int64 v34; // [rsp+D8h] [rbp+1Fh]
  unsigned __int64 v35; // [rsp+E0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v32 = 7;
  v31 = 0;
  LOWORD(lpSubKey[0]) = 0;
  CachedSettingRegPath = GetCachedSettingRegPath(a1, a2, lpSubKey, 0);
  v4 = CachedSettingRegPath;
  if ( CachedSettingRegPath < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\crccache.cpp",
      (const char *)(unsigned int)CachedSettingRegPath,
      phkResult);
LABEL_55:
    if ( v32 >= 8 )
      operator delete((void *)lpSubKey[0]);
    return v4;
  }
  if ( v31 )
  {
    hKey = 0;
    v5 = (const WCHAR *)lpSubKey;
    if ( v32 >= 8 )
      v5 = lpSubKey[0];
    v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v5, 0, 0x2001Bu, &hKey);
    if ( v6 != 2 )
    {
      if ( v6 )
      {
        v7 = 206;
LABEL_9:
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)v7,
               (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\crccache.cpp",
               (const char *)v6,
               phkResulta);
        goto LABEL_53;
      }
      cbMaxValueNameLen = 0;
      v6 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, 0, &cbMaxValueNameLen, 0, 0, 0);
      if ( v6 )
      {
        v7 = 211;
        goto LABEL_9;
      }
      if ( cbMaxValueNameLen + 1 < cbMaxValueNameLen )
      {
        cbMaxValueNameLen = -1;
        v4 = -2147024362;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD6,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\crccache.cpp",
          (const char *)0x80070216LL,
          phkResulta);
LABEL_53:
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_55;
      }
      ++cbMaxValueNameLen;
      v8 = (char *)*((_QWORD *)a2 + 5);
      v35 = 7;
      v34 = 0;
      LOWORD(SubStr[0]) = 0;
      if ( *(_WORD *)v8 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&v8[2 * v9] );
      }
      else
      {
        v9 = 0;
      }
      std::wstring::assign(SubStr, v8, v9);
      std::wstring::append((const void **)SubStr, (char *)L"--");
      *(_OWORD *)lpValueName = 0;
      v29 = 0;
      std::vector<unsigned short>::resize(lpValueName, cbMaxValueNameLen);
      *(_OWORD *)v26 = 0;
      v10 = 0;
      v27 = 0;
      v11 = 0;
      cchValueName = cbMaxValueNameLen;
      v12 = (char *)lpValueName[0];
      v13 = RegEnumValueW(hKey, 0, lpValueName[0], &cchValueName, 0, 0, 0, 0);
      v14 = (WCHAR *)v26[1];
      while ( !v13 )
      {
        v15 = (const wchar_t *)SubStr;
        if ( v35 >= 8 )
          v15 = SubStr[0];
        if ( wcsstr((const wchar_t *)v12, v15) )
        {
          if ( v14 == v10 )
          {
            std::vector<std::wstring>::_Reserve(v26);
            v10 = v27;
            v14 = (WCHAR *)v26[1];
          }
          *((_QWORD *)v14 + 3) = 7;
          *((_QWORD *)v14 + 2) = 0;
          *v14 = 0;
          if ( *(_WORD *)v12 )
          {
            v16 = -1;
            do
              ++v16;
            while ( *(_WORD *)&v12[2 * v16] );
          }
          else
          {
            v16 = 0;
          }
          std::wstring::assign(v14, v12, v16);
          v14 += 16;
          v26[1] = v14;
        }
        ++v11;
        cchValueName = cbMaxValueNameLen;
        v13 = RegEnumValueW(hKey, v11, (LPWSTR)v12, &cchValueName, 0, 0, 0, 0);
      }
      if ( v13 != 259 )
      {
        v4 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0xF3,
               (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\common\\src\\crccache.cpp",
               (const char *)v13,
               phkResultb);
        std::vector<std::wstring>::_Tidy((__int64)v26);
        if ( v12 )
          operator delete(v12);
        if ( v35 >= 8 )
          operator delete(SubStr[0]);
        v35 = 7;
        v34 = 0;
        LOWORD(SubStr[0]) = 0;
        goto LABEL_53;
      }
      for ( i = v26[0]; i != v14; i += 16 )
      {
        if ( *((_QWORD *)i + 3) < 8u )
          v18 = i;
        else
          v18 = *(const WCHAR **)i;
        RegDeleteValueW(hKey, v18);
      }
      std::vector<std::wstring>::_Tidy((__int64)v26);
      if ( v12 )
        operator delete(v12);
      if ( v35 >= 8 )
        operator delete(SubStr[0]);
      LOWORD(SubStr[0]) = 0;
      v34 = 0;
      v35 = 7;
    }
    if ( hKey )
      RegCloseKey(hKey);
  }
  if ( v32 >= 8 )
    operator delete((void *)lpSubKey[0]);
  return 0;
}

```

## disassembly

```asm
0x180033fa0  mov     [rsp-8+arg_10], rbx
0x180033fa5  mov     [rsp-8+arg_18], rsi
0x180033faa  push    rbp
0x180033fab  push    rdi
0x180033fac  push    r12
0x180033fae  push    r14
0x180033fb0  push    r15
0x180033fb2  lea     rbp, [rsp-37h]
0x180033fb7  sub     rsp, 0F0h
0x180033fbe  mov     rax, cs:__security_cookie
0x180033fc5  xor     rax, rsp
0x180033fc8  mov     [rbp+57h+var_28], rax
0x180033fcc  mov     rdi, rdx
0x180033fcf  mov     r12d, 7
0x180033fd5  mov     [rbp+57h+var_50], r12
0x180033fd9  xor     r15d, r15d
0x180033fdc  mov     [rbp+57h+var_58], r15
0x180033fe0  mov     word ptr [rbp+57h+lpSubKey], r15w
0x180033fe5  xor     r9d, r9d
0x180033fe8  lea     r8, [rbp+57h+lpSubKey]
0x180033fec  call    ?GetCachedSettingRegPath@@YAJPEAUPackageContext@@PEAU_MVProvisionData@@PEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@2@Z; GetCachedSettingRegPath(PackageContext *,_MVProvisionData *,std::wstring *,std::wstring *)
0x180033ff1  mov     ebx, eax
0x180033ff3  test    eax, eax
0x180033ff5  jns     short loc_180034014
0x180033ff7  mov     rcx, [rbp+5Fh]; this
0x180033ffb  mov     r9d, eax; char *
0x180033ffe  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034005  mov     edx, 0C8h; void *
0x18003400a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003400f  jmp     loc_18003433F
0x180034014  cmp     [rbp+57h+var_58], r15
0x180034018  jz      loc_1800342F5
0x18003401e  mov     [rbp+57h+hKey], r15
0x180034022  lea     rdx, [rbp+57h+lpSubKey]
0x180034026  cmp     [rbp+57h+var_50], 8
0x18003402b  cmovnb  rdx, [rbp+57h+lpSubKey]; lpSubKey
0x180034030  lea     rax, [rbp+57h+hKey]
0x180034034  mov     [rsp+110h+phkResult], rax; unsigned int
0x180034039  mov     r9d, 2001Bh; samDesired
0x18003403f  xor     r8d, r8d; ulOptions
0x180034042  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180034049  call    cs:__imp_RegOpenKeyExW
0x18003404f  cmp     eax, 2
0x180034052  jz      loc_1800342E5
0x180034058  test    eax, eax
0x18003405a  jz      short loc_18003407B
0x18003405c  mov     edx, 0CEh; void *
0x180034061  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034068  mov     r9d, eax; char *
0x18003406b  mov     rcx, [rbp+5Fh]; this
0x18003406f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034074  mov     ebx, eax
0x180034076  jmp     loc_18003432F
0x18003407b  mov     [rbp+57h+cbMaxValueNameLen], r15d
0x18003407f  mov     [rsp+110h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180034084  mov     [rsp+110h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x180034089  mov     [rsp+110h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18003408e  lea     rax, [rbp+57h+cbMaxValueNameLen]
0x180034092  mov     [rsp+110h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x180034097  mov     [rsp+110h+lpcValues], r15; lpcValues
0x18003409c  mov     [rsp+110h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800340a1  mov     [rsp+110h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800340a6  mov     [rsp+110h+phkResult], r15; int
0x1800340ab  xor     r9d, r9d; lpReserved
0x1800340ae  xor     r8d, r8d; lpcchClass
0x1800340b1  xor     edx, edx; lpClass
0x1800340b3  mov     rcx, [rbp+57h+hKey]; hKey
0x1800340b7  call    cs:__imp_RegQueryInfoKeyW
0x1800340bd  test    eax, eax
0x1800340bf  jz      short loc_1800340C8
0x1800340c1  mov     edx, 0D3h
0x1800340c6  jmp     short loc_180034061
0x1800340c8  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800340cb  lea     ecx, [rax+1]
0x1800340ce  cmp     ecx, eax
0x1800340d0  jb      loc_18003430A
0x1800340d6  mov     [rbp+57h+cbMaxValueNameLen], ecx
0x1800340d9  mov     rdx, [rdi+28h]; Src
0x1800340dd  mov     [rbp+57h+var_30], r12
0x1800340e1  mov     [rbp+57h+var_38], r15
0x1800340e5  mov     word ptr [rbp+57h+SubStr], r15w
0x1800340ea  cmp     [rdx], r15w
0x1800340ee  jnz     short loc_1800340F5
0x1800340f0  mov     r8, r15
0x1800340f3  jmp     short loc_180034103
0x1800340f5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800340f9  inc     r8
0x1800340fc  cmp     [rdx+r8*2], r15w
0x180034101  jnz     short loc_1800340F9
0x180034103  lea     rcx, [rbp+57h+SubStr]; void *
0x180034107  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x18003410c  nop
0x18003410d  lea     rdx, asc_18004C91C; "--"
0x180034114  lea     rcx, [rbp+57h+SubStr]; Src
0x180034118  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x18003411d  xorps   xmm0, xmm0
0x180034120  movdqu  xmmword ptr [rbp+57h+lpValueName], xmm0
0x180034125  mov     [rbp+57h+var_70], r15
0x180034129  mov     edx, [rbp+57h+cbMaxValueNameLen]
0x18003412c  lea     rcx, [rbp+57h+lpValueName]
0x180034130  call    ?resize@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::resize(unsigned __int64)
0x180034135  nop
0x180034136  xorps   xmm0, xmm0
0x180034139  movdqu  xmmword ptr [rbp+57h+var_98], xmm0
0x18003413e  mov     rdi, r15
0x180034141  mov     [rbp+57h+var_88], r15
0x180034145  mov     r14d, r15d
0x180034148  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x18003414b  mov     [rbp+57h+cchValueName], eax
0x18003414e  mov     [rsp+110h+lpcValues], r15; lpcbData
0x180034153  mov     [rsp+110h+lpcbMaxClassLen], r15; lpData
0x180034158  mov     [rsp+110h+lpcbMaxSubKeyLen], r15; lpType
0x18003415d  mov     [rsp+110h+phkResult], r15; unsigned int
0x180034162  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180034166  mov     rsi, [rbp+57h+lpValueName]
0x18003416a  mov     r8, rsi; lpValueName
0x18003416d  xor     edx, edx; dwIndex
0x18003416f  mov     rcx, [rbp+57h+hKey]; hKey
0x180034173  call    cs:__imp_RegEnumValueW
0x180034179  mov     rbx, [rbp+57h+var_98+8]
0x18003417d  test    eax, eax
0x18003417f  jnz     loc_180034225
0x180034185  lea     rdx, [rbp+57h+SubStr]
0x180034189  cmp     [rbp+57h+var_30], 8
0x18003418e  cmovnb  rdx, [rbp+57h+SubStr]; SubStr
0x180034193  mov     rcx, rsi; Str
0x180034196  call    cs:__imp_wcsstr
0x18003419c  test    rax, rax
0x18003419f  jz      short loc_1800341EF
0x1800341a1  cmp     rbx, rdi
0x1800341a4  jnz     short loc_1800341B7
0x1800341a6  lea     rcx, [rbp+57h+var_98]
0x1800341aa  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800341af  mov     rdi, [rbp+57h+var_88]
0x1800341b3  mov     rbx, [rbp+57h+var_98+8]
0x1800341b7  mov     [rbx+18h], r12
0x1800341bb  mov     [rbx+10h], r15
0x1800341bf  mov     [rbx], r15w
0x1800341c3  cmp     [rsi], r15w
0x1800341c7  jnz     short loc_1800341CE
0x1800341c9  mov     r8, r15
0x1800341cc  jmp     short loc_1800341DC
0x1800341ce  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800341d2  inc     r8
0x1800341d5  cmp     [rsi+r8*2], r15w
0x1800341da  jnz     short loc_1800341D2
0x1800341dc  mov     rdx, rsi; Src
0x1800341df  mov     rcx, rbx; void *
0x1800341e2  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800341e7  add     rbx, 20h ; ' '
0x1800341eb  mov     [rbp+57h+var_98+8], rbx
0x1800341ef  inc     r14d
0x1800341f2  mov     eax, [rbp+57h+cbMaxValueNameLen]
0x1800341f5  mov     [rbp+57h+cchValueName], eax
0x1800341f8  mov     [rsp+110h+lpcValues], r15; lpcbData
0x1800341fd  mov     [rsp+110h+lpcbMaxClassLen], r15; lpData
0x180034202  mov     [rsp+110h+lpcbMaxSubKeyLen], r15; lpType
0x180034207  mov     [rsp+110h+phkResult], r15; lpReserved
0x18003420c  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x180034210  mov     r8, rsi; lpValueName
0x180034213  mov     edx, r14d; dwIndex
0x180034216  mov     rcx, [rbp+57h+hKey]; hKey
0x18003421a  call    cs:__imp_RegEnumValueW
0x180034220  jmp     loc_18003417D
0x180034225  cmp     eax, 103h
0x18003422a  jz      short loc_180034286
0x18003422c  test    eax, eax
0x18003422e  jz      short loc_1800342AE
0x180034230  mov     rcx, [rbp+5Fh]; this
0x180034234  mov     r9d, eax; char *
0x180034237  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18003423e  mov     edx, 0F3h; void *
0x180034243  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180034248  mov     ebx, eax
0x18003424a  lea     rcx, [rbp+57h+var_98]
0x18003424e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180034253  nop
0x180034254  test    rsi, rsi
0x180034257  jz      short loc_180034263
0x180034259  mov     rcx, rsi
0x18003425c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180034262  nop
0x180034263  cmp     [rbp+57h+var_30], 8
0x180034268  jb      short loc_180034274
0x18003426a  mov     rcx, [rbp+57h+SubStr]
0x18003426e  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180034274  mov     [rbp+57h+var_30], r12
0x180034278  mov     [rbp+57h+var_38], r15
0x18003427c  mov     word ptr [rbp+57h+SubStr], r15w
0x180034281  jmp     loc_18003432F
0x180034286  mov     rdi, [rbp+57h+var_98]
0x18003428a  cmp     rdi, rbx
0x18003428d  jz      short loc_1800342AE
0x18003428f  cmp     qword ptr [rdi+18h], 8
0x180034294  jb      short loc_18003429B
0x180034296  mov     rdx, [rdi]
0x180034299  jmp     short loc_18003429E
0x18003429b  mov     rdx, rdi; lpValueName
0x18003429e  mov     rcx, [rbp+57h+hKey]; hKey
0x1800342a2  call    cs:__imp_RegDeleteValueW
0x1800342a8  add     rdi, 20h ; ' '
0x1800342ac  jmp     short loc_18003428A
0x1800342ae  lea     rcx, [rbp+57h+var_98]
0x1800342b2  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x1800342b7  nop
0x1800342b8  test    rsi, rsi
0x1800342bb  jz      short loc_1800342C7
0x1800342bd  mov     rcx, rsi
0x1800342c0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800342c6  nop
0x1800342c7  cmp     [rbp+57h+var_30], 8
0x1800342cc  jb      short loc_1800342D8
0x1800342ce  mov     rcx, [rbp+57h+SubStr]
0x1800342d2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800342d8  mov     word ptr [rbp+57h+SubStr], r15w
0x1800342dd  mov     [rbp+57h+var_38], r15
0x1800342e1  mov     [rbp+57h+var_30], r12
0x1800342e5  mov     rcx, [rbp+57h+hKey]; hKey
0x1800342e9  test    rcx, rcx
0x1800342ec  jz      short loc_1800342F5
0x1800342ee  call    cs:__imp_RegCloseKey
0x1800342f4  nop
0x1800342f5  cmp     [rbp+57h+var_50], 8
0x1800342fa  jb      short loc_180034306
0x1800342fc  mov     rcx, [rbp+57h+lpSubKey]
0x180034300  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180034306  xor     eax, eax
0x180034308  jmp     short loc_180034352
0x18003430a  mov     [rbp+57h+cbMaxValueNameLen], 0FFFFFFFFh
0x180034311  mov     rcx, [rbp+5Fh]; this
0x180034315  mov     ebx, 80070216h
0x18003431a  mov     r9d, ebx; char *
0x18003431d  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180034324  mov     edx, 0D6h; void *
0x180034329  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003432e  nop
0x18003432f  mov     rcx, [rbp+57h+hKey]; hKey
0x180034333  test    rcx, rcx
0x180034336  jz      short loc_18003433F
0x180034338  call    cs:__imp_RegCloseKey
0x18003433e  nop
0x18003433f  cmp     [rbp+57h+var_50], 8
0x180034344  jb      short loc_180034350
0x180034346  mov     rcx, [rbp+57h+lpSubKey]
0x18003434a  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180034350  mov     eax, ebx
0x180034352  mov     rcx, [rbp+57h+var_28]
0x180034356  xor     rcx, rsp; StackCookie
0x180034359  call    __security_check_cookie
0x18003435e  lea     r11, [rsp+110h+var_20]
0x180034366  mov     rbx, [r11+40h]
0x18003436a  mov     rsi, [r11+48h]
0x18003436e  mov     rsp, r11
0x180034371  pop     r15
0x180034373  pop     r14
0x180034375  pop     r12
0x180034377  pop     rdi
0x180034378  pop     rbp
0x180034379  retn
```
