# ATL::CRegParser::RegisterSubkeys(ushort *,HKEY__ *,int,int)

- ea: `0x140035738`
- end: `0x14003601a`
- name: `?RegisterSubkeys@CRegParser@ATL@@IEAAJPEAGPEAUHKEY__@@HH@Z`
- size: `2274`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *, HKEY, int, int)`
- caller_count: `2`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140035738`
- `0x14003601c`

## callees

- `0x140001020`
- `0x1400020d0`
- `0x140033ab0`
- `0x140034a70`
- `0x140034c7c`
- `0x140035280`
- `0x140035330`
- `0x140035584`
- `0x140035594`
- `0x140035738`
- `0x140036788`

## import_xrefs

- `ADVAPI32!RegDeleteKeyW` at `0x140035fae`
- `ADVAPI32!RegDeleteKeyW` at `0x140035fae`
- `ADVAPI32!RegDeleteValueW` at `0x1400359cb`
- `ADVAPI32!RegDeleteValueW` at `0x1400359cb`
- `ADVAPI32!RegCloseKey` at `0x1400359e4`
- `ADVAPI32!RegCloseKey` at `0x140035a9d`
- `ADVAPI32!RegCloseKey` at `0x140035b11`
- `ADVAPI32!RegCloseKey` at `0x140035baf`
- `ADVAPI32!RegCloseKey` at `0x140035bd8`
- `ADVAPI32!RegCloseKey` at `0x140035cfe`
- `ADVAPI32!RegCloseKey` at `0x140035f28`
- `ADVAPI32!RegCloseKey` at `0x140035fe4`
- `ADVAPI32!RegCloseKey` at `0x1400359e4`
- `ADVAPI32!RegCloseKey` at `0x140035a9d`
- `ADVAPI32!RegCloseKey` at `0x140035b11`
- `ADVAPI32!RegCloseKey` at `0x140035baf`
- `ADVAPI32!RegCloseKey` at `0x140035bd8`
- `ADVAPI32!RegCloseKey` at `0x140035cfe`
- `ADVAPI32!RegCloseKey` at `0x140035f28`
- `ADVAPI32!RegCloseKey` at `0x140035fe4`
- `ADVAPI32!RegCreateKeyExW` at `0x140035b9a`
- `ADVAPI32!RegCreateKeyExW` at `0x140035b9a`
- `ADVAPI32!RegOpenKeyExW` at `0x1400359ae`
- `ADVAPI32!RegOpenKeyExW` at `0x140035a88`
- `ADVAPI32!RegOpenKeyExW` at `0x140035afc`
- `ADVAPI32!RegOpenKeyExW` at `0x140035ce6`
- `ADVAPI32!RegOpenKeyExW` at `0x1400359ae`
- `ADVAPI32!RegOpenKeyExW` at `0x140035a88`
- `ADVAPI32!RegOpenKeyExW` at `0x140035afc`
- `ADVAPI32!RegOpenKeyExW` at `0x140035ce6`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140035e64`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140035f07`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140035e64`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140035f07`
- `KERNEL32!lstrcmpiW` at `0x1400357bb`
- `KERNEL32!lstrcmpiW` at `0x1400357cd`
- `KERNEL32!lstrcmpiW` at `0x140035847`
- `KERNEL32!lstrcmpiW` at `0x1400358d0`
- `KERNEL32!lstrcmpiW` at `0x1400358fc`
- `KERNEL32!lstrcmpiW` at `0x140035e8b`
- `KERNEL32!lstrcmpiW` at `0x1400357bb`
- `KERNEL32!lstrcmpiW` at `0x1400357cd`
- `KERNEL32!lstrcmpiW` at `0x140035847`
- `KERNEL32!lstrcmpiW` at `0x1400358d0`
- `KERNEL32!lstrcmpiW` at `0x1400358fc`
- `KERNEL32!lstrcmpiW` at `0x140035e8b`
- `KERNEL32!GetModuleHandleW` at `0x140035f5b`
- `KERNEL32!GetModuleHandleW` at `0x140035f5b`
- `KERNEL32!GetProcAddress` at `0x140035f70`
- `KERNEL32!GetProcAddress` at `0x140035f70`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x140035d38`
- `api-ms-win-crt-string-l1-1-0!wcsncpy_s` at `0x140035d38`
- `USER32!CharNextW` at `0x14003581e`
- `USER32!CharNextW` at `0x140035a15`
- `USER32!CharNextW` at `0x14003581e`
- `USER32!CharNextW` at `0x140035a15`

## string_xrefs

- `0x140035f66`: `RegDeleteKeyExW`
- `0x1400357b1`: `Delete`
- `0x1400357c3`: `ForceRemove`
- `0x1400358c6`: `NoRemove`
- `0x140035f54`: `Advapi32.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::RegisterSubkeys(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        HKEY a3,
        int a4,
        int a5)
{
  HKEY v7; // r14
  ATL::CAtlTransactionManager *v8; // r15
  int Token; // ebx
  int v10; // r12d
  int v11; // esi
  LPWSTR v12; // rcx
  WCHAR i; // ax
  LPCWSTR *v14; // rbx
  int v15; // esi
  int v16; // eax
  LSTATUS v17; // eax
  HKEY v18; // rsi
  LSTATUS v19; // eax
  int v20; // eax
  LPWSTR v21; // rcx
  WCHAR j; // ax
  HKEY v23; // rbx
  LSTATUS v24; // eax
  LSTATUS v25; // eax
  unsigned int v27; // r9d
  LSTATUS v28; // eax
  unsigned int v29; // ecx
  __int64 v31; // rax
  LSTATUS v32; // eax
  LSTATUS v33; // esi
  int v34; // r15d
  errno_t v35; // eax
  __int64 v36; // rax
  LPCWSTR *v37; // rsi
  int v38; // esi
  HMODULE ModuleHandleW; // rax
  FARPROC ProcAddress; // rax
  unsigned __int16 *phkResult; // [rsp+20h] [rbp-E0h]
  struct _SECURITY_ATTRIBUTES *v42; // [rsp+38h] [rbp-C8h]
  HKEY v43; // [rsp+60h] [rbp-A0h] BYREF
  int v44; // [rsp+68h] [rbp-98h]
  HKEY hKey; // [rsp+70h] [rbp-90h]
  HKEY v46; // [rsp+78h] [rbp-88h] BYREF
  int v47; // [rsp+80h] [rbp-80h]
  ATL::CAtlTransactionManager *v48; // [rsp+88h] [rbp-78h]
  DWORD dwDisposition; // [rsp+90h] [rbp-70h] BYREF
  HKEY v50; // [rsp+98h] [rbp-68h] BYREF
  int v51; // [rsp+A0h] [rbp-60h]
  __int64 v52; // [rsp+A8h] [rbp-58h]
  wchar_t Destination[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR ValueName[4096]; // [rsp+2C0h] [rbp+1C0h] BYREF

  v44 = a4;
  hKey = a3;
  v7 = 0;
  v46 = 0;
  v47 = 0;
  v8 = 0;
  v48 = 0;
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
    goto LABEL_68;
  _mm_lfence();
  if ( *a2 == 125 )
    goto LABEL_68;
  while ( 1 )
  {
    v10 = 1;
    v11 = lstrcmpiW(a2, L"Delete");
    if ( !lstrcmpiW(a2, L"ForceRemove") || !v11 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_68;
      _mm_lfence();
      if ( v44 )
      {
        v50 = 0;
        v51 = 0;
        v52 = 0;
        v12 = a2;
        for ( i = *a2; i; i = *v12 )
        {
          if ( i == 92 )
          {
            if ( v12 )
              goto LABEL_139;
            break;
          }
          v12 = CharNextW(v12);
        }
        v14 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
        while ( lstrcmpiW(a2, *v14) )
        {
          if ( (__int64)++v14 >= (__int64)L"AppID" )
          {
            _mm_lfence();
            v50 = hKey;
            v51 = 0;
            v52 = 0;
            ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v50, a2);
            break;
          }
        }
        if ( !v11 )
        {
          _mm_lfence();
          Token = ATL::CRegParser::NextToken(this, a2);
          if ( Token < 0 )
            goto LABEL_68;
          _mm_lfence();
          Token = ATL::CRegParser::SkipAssignment(this, a2);
          if ( Token < 0 )
            goto LABEL_68;
          v15 = v44;
          goto LABEL_75;
        }
      }
    }
    if ( !lstrcmpiW(a2, L"NoRemove") )
    {
      v10 = 0;
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_68;
    }
    if ( !lstrcmpiW(a2, L"Val") )
      break;
    v21 = a2;
    for ( j = *a2; j; j = *v21 )
    {
      if ( j == 92 )
      {
        if ( v21 )
          goto LABEL_139;
        break;
      }
      v21 = CharNextW(v21);
    }
    v15 = v44;
    if ( v44 )
    {
      v43 = 0;
      v23 = hKey;
      if ( v8 )
        v24 = ATL::CAtlTransactionManager::RegOpenKeyExW(v8, hKey, a2, 0, 0x2001Fu, &v43);
      else
        v24 = RegOpenKeyExW(hKey, a2, 0, 0x2001Fu, &v43);
      if ( v24 )
        goto LABEL_145;
      v25 = 0;
      if ( v7 )
        v25 = RegCloseKey(v7);
      v7 = v43;
      v46 = v43;
      v47 = 0;
      if ( v25 )
      {
LABEL_145:
        v43 = 0;
        if ( v8
           ? ATL::CAtlTransactionManager::RegOpenKeyExW(v8, v23, a2, 0, 0x20019u, &v43)
           : RegOpenKeyExW(v23, a2, 0, 0x20019u, &v43) )
        {
          goto LABEL_146;
        }
        v28 = 0;
        if ( v7 )
          v28 = RegCloseKey(v7);
        v7 = v43;
        v46 = v43;
        v47 = 0;
        if ( v28 )
        {
LABEL_146:
          v43 = 0;
          v17 = v8
              ? ATL::CAtlTransactionManager::RegCreateKeyExW(
                  v8,
                  v23,
                  a2,
                  v27,
                  phkResult,
                  0,
                  0x2001Fu,
                  v42,
                  &v43,
                  &dwDisposition)
              : RegCreateKeyExW(v23, a2, 0, 0, 0, 0x2001Fu, 0, &v43, &dwDisposition);
          if ( v17 )
            goto LABEL_66;
          v17 = 0;
          if ( v7 )
            v17 = RegCloseKey(v7);
          v7 = v43;
          v46 = v43;
          v47 = 0;
          if ( v17 )
            goto LABEL_66;
        }
      }
      Token = ATL::CRegParser::NextToken(this, a2);
      if ( Token < 0 )
        goto LABEL_68;
      if ( *a2 == 61 )
      {
        _mm_lfence();
        v16 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v46, 0, a2);
        Token = v16;
        v7 = v46;
        goto LABEL_74;
      }
LABEL_75:
      if ( *a2 != 123 )
        goto LABEL_135;
      v31 = -1;
      do
        ++v31;
      while ( a2[v31] );
      if ( v31 != 1 )
        goto LABEL_135;
      Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, v15, 0);
      if ( Token < 0 )
        goto LABEL_68;
      _mm_lfence();
      v20 = ATL::CRegParser::NextToken(this, a2);
LABEL_36:
      Token = v20;
      if ( v20 < 0 )
        goto LABEL_68;
      goto LABEL_135;
    }
    if ( a5 )
    {
      v33 = 2;
    }
    else
    {
      v43 = 0;
      if ( v8 )
        v32 = ATL::CAtlTransactionManager::RegOpenKeyExW(v8, hKey, a2, 0, 0x20019u, &v43);
      else
        v32 = RegOpenKeyExW(hKey, a2, 0, 0x20019u, &v43);
      v33 = v32;
      if ( !v32 )
      {
        v33 = 0;
        if ( v7 )
          v33 = RegCloseKey(v7);
        v7 = v43;
        v46 = v43;
        v47 = 0;
      }
    }
    v34 = 1;
    if ( !v33 )
      v34 = a5;
    v35 = wcsncpy_s(Destination, 0x104u, a2, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v35 )
    {
      if ( v35 == 12 )
        ATL::AtlThrowImpl(-2147024882);
      if ( v35 == 22 || v35 == 34 )
        ATL::AtlThrowImpl(-2147024809);
      if ( v35 != 80 )
        ATL::AtlThrowImpl(-2147467259);
    }
    Token = ATL::CRegParser::NextToken(this, a2);
    if ( Token < 0 )
      goto LABEL_68;
    _mm_lfence();
    Token = ATL::CRegParser::SkipAssignment(this, a2);
    if ( Token < 0 )
      goto LABEL_68;
    if ( *a2 == 123 )
    {
      _mm_lfence();
      v36 = -1;
      do
        ++v36;
      while ( a2[v36] );
      if ( v36 == 1 )
      {
        _mm_lfence();
        Token = ATL::CRegParser::RegisterSubkeys(this, a2, v7, 0, v34);
        if ( Token < 0 && !v34 )
          goto LABEL_68;
        _mm_lfence();
        Token = ATL::CRegParser::NextToken(this, a2);
        if ( Token < 0 )
          goto LABEL_68;
      }
    }
    if ( v33 != 2 )
    {
      if ( v33 )
      {
        if ( a5 )
          goto LABEL_135;
        v29 = v33;
      }
      else
      {
        if ( a5 )
        {
          LODWORD(v43) = 0;
          if ( !RegQueryInfoKeyW(v7, 0, 0, 0, (LPDWORD)&v43, 0, 0, 0, 0, 0, 0, 0) )
          {
            if ( (_DWORD)v43 )
            {
              v37 = (LPCWSTR *)&ATL::CRegParser::rgszNeverDelete;
              while ( lstrcmpiW(Destination, *v37) )
              {
                if ( (__int64)++v37 >= (__int64)L"AppID" )
                {
                  if ( v10 )
                  {
                    ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&v46, Destination);
                    v7 = v46;
                  }
                  goto LABEL_135;
                }
              }
              goto LABEL_135;
            }
          }
        }
        LODWORD(v43) = 0;
        v38 = 0;
        if ( !RegQueryInfoKeyW(v7, 0, 0, 0, (LPDWORD)&v43, 0, 0, 0, 0, 0, 0, 0) )
          LOBYTE(v38) = (_DWORD)v43 != 0;
        v17 = 0;
        if ( v7 )
        {
          v17 = RegCloseKey(v7);
          v7 = 0;
          v46 = 0;
        }
        v47 = 0;
        if ( !v17 )
        {
          if ( !v10 || v38 )
            goto LABEL_135;
          if ( `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized )
          {
            ProcAddress = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
          }
          else
          {
            ModuleHandleW = GetModuleHandleW(L"Advapi32.dll");
            if ( ModuleHandleW )
            {
              ProcAddress = GetProcAddress(ModuleHandleW, "RegDeleteKeyExW");
              `ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx = (__int64)ProcAddress;
            }
            else
            {
              ProcAddress = (FARPROC)`ATL::CRegKey::DeleteSubKey'::`2'::pfnRegDeleteKeyEx;
            }
            `ATL::CRegKey::DeleteSubKey'::`2'::bInitialized = 1;
          }
          v17 = ProcAddress
              ? ((__int64 (__fastcall *)(HKEY, wchar_t *, _QWORD, _QWORD))ProcAddress)(hKey, Destination, 0, 0)
              : RegDeleteKeyW(hKey, Destination);
          if ( !v17 )
            goto LABEL_135;
        }
LABEL_66:
        v29 = v17;
      }
      Token = ATL::AtlHresultFromWin32(v29);
      goto LABEL_68;
    }
LABEL_135:
    if ( *a2 == 125 )
      goto LABEL_68;
    v8 = v48;
  }
  Token = ATL::CRegParser::NextToken(this, ValueName);
  if ( Token < 0 )
    goto LABEL_68;
  _mm_lfence();
  Token = ATL::CRegParser::NextToken(this, a2);
  if ( Token < 0 )
    goto LABEL_68;
  if ( *a2 != 61 )
  {
LABEL_139:
    Token = -2147352567;
    goto LABEL_68;
  }
  v15 = v44;
  if ( v44 )
  {
    _mm_lfence();
    v50 = hKey;
    v51 = 0;
    v52 = 0;
    v16 = ATL::CRegParser::AddValue(this, (struct ATL::CRegKey *)&v50, ValueName, a2);
    Token = v16;
LABEL_74:
    if ( v16 < 0 )
      goto LABEL_68;
    goto LABEL_75;
  }
  if ( a5 || !v10 )
  {
LABEL_35:
    _mm_lfence();
    v20 = ATL::CRegParser::SkipAssignment(this, a2);
    goto LABEL_36;
  }
  v43 = 0;
  v17 = RegOpenKeyExW(hKey, 0, 0, 0x20006u, &v43);
  if ( v17 )
    goto LABEL_66;
  v18 = v43;
  v19 = RegDeleteValueW(v43, ValueName);
  if ( (v19 & 0xFFFFFFFD) == 0 )
  {
    if ( v18 )
      RegCloseKey(v18);
    goto LABEL_35;
  }
  Token = ATL::AtlHresultFromWin32(v19);
  if ( v18 )
    RegCloseKey(v18);
LABEL_68:
  if ( v7 )
    RegCloseKey(v7);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x140035738  push    rbp
0x14003573a  push    rbx
0x14003573b  push    rsi
0x14003573c  push    rdi
0x14003573d  push    r12
0x14003573f  push    r13
0x140035741  push    r14
0x140035743  push    r15
0x140035745  lea     rbp, [rsp-21D8h]
0x14003574d  mov     eax, 22D8h
0x140035752  call    _alloca_probe
0x140035757  sub     rsp, rax
0x14003575a  mov     rax, cs:__security_cookie
0x140035761  xor     rax, rsp
0x140035764  mov     [rbp+2210h+var_50], rax
0x14003576b  mov     [rsp+2310h+var_22A8], r9d
0x140035770  mov     [rsp+2310h+hKey], r8
0x140035775  mov     rdi, rdx
0x140035778  mov     r13, rcx
0x14003577b  xor     esi, esi
0x14003577d  mov     r14d, esi
0x140035780  mov     [rsp+2310h+var_2298], rsi
0x140035785  mov     [rbp+2210h+var_2290], esi
0x140035788  mov     r15d, esi
0x14003578b  mov     [rbp+2210h+var_2288], rsi
0x14003578f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140035794  mov     ebx, eax
0x140035796  test    eax, eax
0x140035798  js      loc_140035BD0
0x14003579e  lfence
0x1400357a1  cmp     word ptr [rdi], 7Dh ; '}'
0x1400357a5  jz      loc_140035BD0
0x1400357ab  mov     r12d, 1
0x1400357b1  lea     rdx, aDelete; "Delete"
0x1400357b8  mov     rcx, rdi; lpString1
0x1400357bb  call    cs:__imp_lstrcmpiW
0x1400357c1  mov     esi, eax
0x1400357c3  lea     rdx, aForceremove; "ForceRemove"
0x1400357ca  mov     rcx, rdi; lpString1
0x1400357cd  call    cs:__imp_lstrcmpiW
0x1400357d3  xor     ebx, ebx
0x1400357d5  test    eax, eax
0x1400357d7  jz      short loc_1400357E1
0x1400357d9  test    esi, esi
0x1400357db  jnz     loc_1400358C6
0x1400357e1  mov     rdx, rdi; unsigned __int16 *
0x1400357e4  mov     rcx, r13; this
0x1400357e7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400357ec  mov     ebx, eax
0x1400357ee  test    eax, eax
0x1400357f0  js      loc_140035BD0
0x1400357f6  lfence
0x1400357f9  xor     ebx, ebx
0x1400357fb  cmp     [rsp+2310h+var_22A8], ebx
0x1400357ff  jz      loc_1400358C6
0x140035805  mov     [rbp+2210h+var_2278], rbx
0x140035809  mov     [rbp+2210h+var_2270], ebx
0x14003580c  mov     [rbp+2210h+var_2268], rbx
0x140035810  mov     rcx, rdi
0x140035813  movzx   eax, word ptr [rdi]
0x140035816  jmp     short loc_14003582A
0x140035818  cmp     ax, 5Ch ; '\'
0x14003581c  jz      short loc_140035831
0x14003581e  call    cs:__imp_CharNextW
0x140035824  mov     rcx, rax; lpsz
0x140035827  movzx   eax, word ptr [rax]
0x14003582a  test    ax, ax
0x14003582d  jnz     short loc_140035818
0x14003582f  jmp     short loc_14003583A
0x140035831  test    rcx, rcx
0x140035834  jnz     loc_140035FEF
0x14003583a  lea     rbx, ?rgszNeverDelete@CRegParser@ATL@@1QBQEBGB; ushort const * const near * const ATL::CRegParser::rgszNeverDelete
0x140035841  mov     rdx, [rbx]; lpString2
0x140035844  mov     rcx, rdi; lpString1
0x140035847  call    cs:__imp_lstrcmpiW
0x14003584d  test    eax, eax
0x14003584f  jz      short loc_140035884
0x140035851  add     rbx, 8
0x140035855  lea     rax, aAppid_0; "AppID"
0x14003585c  cmp     rbx, rax
0x14003585f  jl      short loc_140035841
0x140035861  lfence
0x140035864  mov     rax, [rsp+2310h+hKey]
0x140035869  mov     [rbp+2210h+var_2278], rax
0x14003586d  xor     ebx, ebx
0x14003586f  mov     [rbp+2210h+var_2270], ebx
0x140035872  mov     [rbp+2210h+var_2268], rbx
0x140035876  mov     rdx, rdi; unsigned __int16 *
0x140035879  lea     rcx, [rbp+2210h+var_2278]; this
0x14003587d  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140035882  jmp     short loc_140035886
0x140035884  xor     ebx, ebx
0x140035886  test    esi, esi
0x140035888  jnz     short loc_1400358C6
0x14003588a  lfence
0x14003588d  mov     rdx, rdi; unsigned __int16 *
0x140035890  mov     rcx, r13; this
0x140035893  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140035898  mov     ebx, eax
0x14003589a  xor     r15d, r15d
0x14003589d  test    eax, eax
0x14003589f  js      loc_140035BD0
0x1400358a5  lfence
0x1400358a8  mov     rdx, rdi; unsigned __int16 *
0x1400358ab  mov     rcx, r13; this
0x1400358ae  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1400358b3  mov     ebx, eax
0x1400358b5  test    eax, eax
0x1400358b7  js      loc_140035BD0
0x1400358bd  mov     esi, [rsp+2310h+var_22A8]
0x1400358c1  jmp     loc_140035C3E
0x1400358c6  lea     rdx, aNoremove; "NoRemove"
0x1400358cd  mov     rcx, rdi; lpString1
0x1400358d0  call    cs:__imp_lstrcmpiW
0x1400358d6  test    eax, eax
0x1400358d8  jnz     short loc_1400358F2
0x1400358da  mov     r12d, ebx
0x1400358dd  mov     rdx, rdi; unsigned __int16 *
0x1400358e0  mov     rcx, r13; this
0x1400358e3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1400358e8  mov     ebx, eax
0x1400358ea  test    eax, eax
0x1400358ec  js      loc_140035BD0
0x1400358f2  lea     rdx, aVal; "Val"
0x1400358f9  mov     rcx, rdi; lpString1
0x1400358fc  call    cs:__imp_lstrcmpiW
0x140035902  test    eax, eax
0x140035904  jnz     loc_140035A07
0x14003590a  lea     rdx, [rbp+2210h+ValueName]; unsigned __int16 *
0x140035911  mov     rcx, r13; this
0x140035914  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140035919  mov     ebx, eax
0x14003591b  xor     r15d, r15d
0x14003591e  test    eax, eax
0x140035920  js      loc_140035BD0
0x140035926  lfence
0x140035929  mov     rdx, rdi; unsigned __int16 *
0x14003592c  mov     rcx, r13; this
0x14003592f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140035934  mov     ebx, eax
0x140035936  test    eax, eax
0x140035938  js      loc_140035BD0
0x14003593e  cmp     word ptr [rdi], 3Dh ; '='
0x140035942  jnz     loc_140035FEF
0x140035948  mov     esi, [rsp+2310h+var_22A8]
0x14003594c  test    esi, esi
0x14003594e  jz      short loc_140035981
0x140035950  lfence
0x140035953  mov     rax, [rsp+2310h+hKey]
0x140035958  mov     [rbp+2210h+var_2278], rax
0x14003595c  mov     [rbp+2210h+var_2270], r15d
0x140035960  mov     [rbp+2210h+var_2268], r15
0x140035964  mov     r9, rdi; unsigned __int16 *
0x140035967  lea     r8, [rbp+2210h+ValueName]; unsigned __int16 *
0x14003596e  lea     rdx, [rbp+2210h+var_2278]; struct ATL::CRegKey *
0x140035972  mov     rcx, r13; this
0x140035975  call    ?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z; ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)
0x14003597a  mov     ebx, eax
0x14003597c  jmp     loc_140035C3A
0x140035981  cmp     [rbp+2210h+arg_20], r15d
0x140035988  jnz     short loc_1400359EA
0x14003598a  test    r12d, r12d
0x14003598d  jz      short loc_1400359EA
0x14003598f  mov     [rsp+2310h+var_22B0], r15
0x140035994  lea     rax, [rsp+2310h+var_22B0]
0x140035999  mov     [rsp+2310h+phkResult], rax; phkResult
0x14003599e  mov     r9d, 20006h; samDesired
0x1400359a4  xor     r8d, r8d; ulOptions
0x1400359a7  xor     edx, edx; lpSubKey
0x1400359a9  mov     rcx, [rsp+2310h+hKey]; hKey
0x1400359ae  call    cs:__imp_RegOpenKeyExW
0x1400359b4  test    eax, eax
0x1400359b6  jnz     loc_140035BC7
0x1400359bc  mov     rsi, [rsp+2310h+var_22B0]
0x1400359c1  lea     rdx, [rbp+2210h+ValueName]; lpValueName
0x1400359c8  mov     rcx, rsi; hKey
0x1400359cb  call    cs:__imp_RegDeleteValueW
0x1400359d1  test    eax, 0FFFFFFFDh
0x1400359d6  jnz     loc_140035FCF
0x1400359dc  test    rsi, rsi
0x1400359df  jz      short loc_1400359EA
0x1400359e1  mov     rcx, rsi; hKey
0x1400359e4  call    cs:__imp_RegCloseKey
0x1400359ea  lfence
0x1400359ed  mov     rdx, rdi; unsigned __int16 *
0x1400359f0  mov     rcx, r13; this
0x1400359f3  call    ?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::SkipAssignment(ushort *)
0x1400359f8  mov     ebx, eax
0x1400359fa  test    eax, eax
0x1400359fc  js      loc_140035BD0
0x140035a02  jmp     loc_140035FBC
0x140035a07  mov     rcx, rdi
0x140035a0a  movzx   eax, word ptr [rdi]
0x140035a0d  jmp     short loc_140035A21
0x140035a0f  cmp     ax, 5Ch ; '\'
0x140035a13  jz      short loc_140035A28
0x140035a15  call    cs:__imp_CharNextW
0x140035a1b  mov     rcx, rax; lpsz
0x140035a1e  movzx   eax, word ptr [rax]
0x140035a21  test    ax, ax
0x140035a24  jnz     short loc_140035A0F
0x140035a26  jmp     short loc_140035A31
0x140035a28  test    rcx, rcx
0x140035a2b  jnz     loc_140035FEF
0x140035a31  mov     esi, [rsp+2310h+var_22A8]
0x140035a35  test    esi, esi
0x140035a37  jz      loc_140035C93
0x140035a3d  xor     r12d, r12d
0x140035a40  mov     [rsp+2310h+var_22B0], r12
0x140035a45  lea     rax, [rsp+2310h+var_22B0]
0x140035a4a  mov     rbx, [rsp+2310h+hKey]
0x140035a4f  test    r15, r15
0x140035a52  jz      short loc_140035A74
0x140035a54  mov     qword ptr [rsp+2310h+samDesired], rax; HKEY *
0x140035a59  mov     dword ptr [rsp+2310h+phkResult], 2001Fh; unsigned int
0x140035a61  xor     r9d, r9d; unsigned int
0x140035a64  mov     r8, rdi; unsigned __int16 *
0x140035a67  mov     rdx, rbx; HKEY
0x140035a6a  mov     rcx, r15; this
0x140035a6d  call    ?RegOpenKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKKPEAPEAU3@@Z; ATL::CAtlTransactionManager::RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140035a72  jmp     short loc_140035A8E
0x140035a74  mov     [rsp+2310h+phkResult], rax; phkResult
0x140035a79  mov     r9d, 2001Fh; samDesired
0x140035a7f  xor     r8d, r8d; ulOptions
0x140035a82  mov     rdx, rdi; lpSubKey
0x140035a85  mov     rcx, rbx; hKey
0x140035a88  call    cs:__imp_RegOpenKeyExW
0x140035a8e  test    eax, eax
0x140035a90  jnz     short loc_140035AB9
0x140035a92  mov     eax, r12d
0x140035a95  test    r14, r14
0x140035a98  jz      short loc_140035AA3
0x140035a9a  mov     rcx, r14; hKey
0x140035a9d  call    cs:__imp_RegCloseKey
0x140035aa3  mov     r14, [rsp+2310h+var_22B0]
0x140035aa8  mov     [rsp+2310h+var_2298], r14
0x140035aad  mov     [rbp+2210h+var_2290], r12d
0x140035ab1  test    eax, eax
0x140035ab3  jz      loc_140035C03
0x140035ab9  mov     [rsp+2310h+var_22B0], r12
0x140035abe  lea     rax, [rsp+2310h+var_22B0]
0x140035ac3  test    r15, r15
0x140035ac6  jz      short loc_140035AE8
0x140035ac8  mov     qword ptr [rsp+2310h+samDesired], rax; HKEY *
0x140035acd  mov     dword ptr [rsp+2310h+phkResult], 20019h; unsigned int
0x140035ad5  xor     r9d, r9d; unsigned int
0x140035ad8  mov     r8, rdi; unsigned __int16 *
0x140035adb  mov     rdx, rbx; HKEY
0x140035ade  mov     rcx, r15; this
0x140035ae1  call    ?RegOpenKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKKPEAPEAU3@@Z; ATL::CAtlTransactionManager::RegOpenKeyExW(HKEY__ *,ushort const *,ulong,ulong,HKEY__ * *)
0x140035ae6  jmp     short loc_140035B02
0x140035ae8  mov     [rsp+2310h+phkResult], rax; unsigned __int16 *
0x140035aed  mov     r9d, 20019h; samDesired
0x140035af3  xor     r8d, r8d; ulOptions
0x140035af6  mov     rdx, rdi; lpSubKey
0x140035af9  mov     rcx, rbx; hKey
0x140035afc  call    cs:__imp_RegOpenKeyExW
0x140035b02  test    eax, eax
0x140035b04  jnz     short loc_140035B2D
0x140035b06  mov     eax, r12d
0x140035b09  test    r14, r14
0x140035b0c  jz      short loc_140035B17
0x140035b0e  mov     rcx, r14; hKey
0x140035b11  call    cs:__imp_RegCloseKey
0x140035b17  mov     r14, [rsp+2310h+var_22B0]
0x140035b1c  mov     [rsp+2310h+var_2298], r14
0x140035b21  mov     [rbp+2210h+var_2290], r12d
0x140035b25  test    eax, eax
0x140035b27  jz      loc_140035C03
0x140035b2d  mov     [rsp+2310h+var_22B0], r12
0x140035b32  lea     rax, [rbp+2210h+dwDisposition]
0x140035b36  test    r15, r15
0x140035b39  jz      short loc_140035B6A
0x140035b3b  mov     [rsp+2310h+lpcbMaxValueLen], rax; unsigned int *
0x140035b40  lea     rax, [rsp+2310h+var_22B0]
0x140035b45  mov     [rsp+2310h+lpdwDisposition], rax; HKEY *
0x140035b4a  mov     dword ptr [rsp+2310h+lpSecurityAttributes], 2001Fh; unsigned int
0x140035b52  mov     [rsp+2310h+samDesired], r12d; unsigned int
0x140035b57  mov     r8, rdi; unsigned __int16 *
0x140035b5a  mov     rdx, rbx; HKEY
0x140035b5d  mov     rcx, r15; this
0x140035b60  call    ?RegCreateKeyExW@CAtlTransactionManager@ATL@@QEAAJPEAUHKEY__@@PEBGKPEAGKKQEAU_SECURITY_ATTRIBUTES@@PEAPEAU3@PEAK@Z; ATL::CAtlTransactionManager::RegCreateKeyExW(HKEY__ *,ushort const *,ulong,ushort *,ulong,ulong,_SECURITY_ATTRIBUTES * const,HKEY__ * *,ulong *)
0x140035b65  xor     r15d, r15d
0x140035b68  jmp     short loc_140035BA0
0x140035b6a  mov     [rsp+2310h+lpdwDisposition], rax; lpdwDisposition
0x140035b6f  lea     rax, [rsp+2310h+var_22B0]
0x140035b74  mov     [rsp+2310h+var_22D8], rax; phkResult
0x140035b79  xor     r15d, r15d
0x140035b7c  mov     [rsp+2310h+lpSecurityAttributes], r15; lpSecurityAttributes
0x140035b81  mov     [rsp+2310h+samDesired], 2001Fh; samDesired
0x140035b89  mov     dword ptr [rsp+2310h+phkResult], r15d; dwOptions
0x140035b8e  xor     r9d, r9d; lpClass
0x140035b91  xor     r8d, r8d; Reserved
0x140035b94  mov     rdx, rdi; lpSubKey
0x140035b97  mov     rcx, rbx; hKey
0x140035b9a  call    cs:__imp_RegCreateKeyExW
0x140035ba0  test    eax, eax
0x140035ba2  jnz     short loc_140035BC7
0x140035ba4  mov     eax, r15d
0x140035ba7  test    r14, r14
  ... truncated ...
```
