# FindHighestVersion(_GUID const &,int,AssemblyVersion *,ushort * *,int *,int *)

- ea: `0x180009350`
- end: `0x1800099aa`
- name: `?FindHighestVersion@@YAJAEBU_GUID@@HPEAVAssemblyVersion@@PEAPEAGPEAH3@Z`
- size: `1626`
- prototype: `__int64 __fastcall(const struct _GUID *, __int64, struct AssemblyVersion *, unsigned __int16 **, int *, int *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180009028`

## callees

- `0x180003740`
- `0x180003840`
- `0x180009350`
- `0x18000c1a8`
- `0x18000d614`
- `0x18000dc90`
- `0x18000e118`
- `0x18000f06c`
- `0x180039620`
- `0x18004037c`
- `0x180041ac0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180009471`
- `ADVAPI32!RegOpenKeyExW` at `0x180009564`
- `ADVAPI32!RegOpenKeyExW` at `0x180009471`
- `ADVAPI32!RegOpenKeyExW` at `0x180009564`
- `ADVAPI32!RegQueryValueExW` at `0x180009599`
- `ADVAPI32!RegQueryValueExW` at `0x1800095d5`
- `ADVAPI32!RegQueryValueExW` at `0x18000961b`
- `ADVAPI32!RegQueryValueExW` at `0x180009661`
- `ADVAPI32!RegQueryValueExW` at `0x180009777`
- `ADVAPI32!RegQueryValueExW` at `0x1800097be`
- `ADVAPI32!RegQueryValueExW` at `0x1800097e7`
- `ADVAPI32!RegQueryValueExW` at `0x180009856`
- `ADVAPI32!RegQueryValueExW` at `0x180009599`
- `ADVAPI32!RegQueryValueExW` at `0x1800095d5`
- `ADVAPI32!RegQueryValueExW` at `0x18000961b`
- `ADVAPI32!RegQueryValueExW` at `0x180009661`
- `ADVAPI32!RegQueryValueExW` at `0x180009777`
- `ADVAPI32!RegQueryValueExW` at `0x1800097be`
- `ADVAPI32!RegQueryValueExW` at `0x1800097e7`
- `ADVAPI32!RegQueryValueExW` at `0x180009856`
- `ADVAPI32!RegCloseKey` at `0x180009689`
- `ADVAPI32!RegCloseKey` at `0x18000972a`
- `ADVAPI32!RegCloseKey` at `0x18000995b`
- `ADVAPI32!RegCloseKey` at `0x18000996b`
- `ADVAPI32!RegCloseKey` at `0x180009689`
- `ADVAPI32!RegCloseKey` at `0x18000972a`
- `ADVAPI32!RegCloseKey` at `0x18000995b`
- `ADVAPI32!RegCloseKey` at `0x18000996b`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800094ca`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800094ca`
- `ADVAPI32!RegEnumKeyExW` at `0x18000950d`
- `ADVAPI32!RegEnumKeyExW` at `0x18000950d`

## string_xrefs

- `0x18000940c`: `CLSID\`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall FindHighestVersion(
        const struct _GUID *a1,
        __int64 a2,
        struct AssemblyVersion *a3,
        unsigned __int16 **a4,
        int *a5,
        int *a6)
{
  int v6; // r14d
  unsigned __int16 Data1; // r15
  unsigned __int16 Data1_high; // r12
  unsigned __int16 Data2; // r13
  BYTE *v10; // rsi
  unsigned int v11; // ebx
  LSTATUS v12; // eax
  bool v13; // cc
  DWORD i; // edi
  int v15; // edi
  unsigned __int128 v16; // rax
  wchar_t *v17; // rax
  wint_t *v18; // rdi
  wint_t *v19; // rbx
  wint_t j; // ax
  __int64 v21; // rbx
  unsigned __int64 v22; // rbx
  unsigned __int128 v23; // rax
  wchar_t *v24; // rax
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD Type; // [rsp+64h] [rbp-9Ch] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  __int64 v29; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  int Data3; // [rsp+80h] [rbp-80h]
  struct _GUID v32; // [rsp+90h] [rbp-70h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp-60h] BYREF
  DWORD cchName; // [rsp+A4h] [rbp-5Ch] BYREF
  int *v35; // [rsp+A8h] [rbp-58h]
  unsigned __int16 **v36; // [rsp+B0h] [rbp-50h]
  int *v37; // [rsp+B8h] [rbp-48h]
  wchar_t v38[32]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Name[32]; // [rsp+100h] [rbp+0h] BYREF
  wchar_t v40[32]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t Source[64]; // [rsp+180h] [rbp+80h] BYREF
  wchar_t Destination[128]; // [rsp+200h] [rbp+100h] BYREF

  v36 = a4;
  v37 = a5;
  v35 = a6;
  v6 = 0;
  cchName = 0;
  hKey = 0;
  phkResult = 0;
  Type = 0;
  cbData = 0;
  cSubKeys = 0;
  Data1 = 0;
  Data1_high = 0;
  Data2 = 0;
  Data3 = 0;
  v29 = 0;
  *a6 = 0;
  if ( !a4 || !a5 )
    return (unsigned int)-2147024809;
  v10 = 0;
  *a4 = 0;
  *a5 = 0;
  v32 = *a1;
  if ( !(unsigned int)GuidToLPWSTR(&v32, Source, (unsigned int)a5) )
  {
    v11 = -2147024809;
    goto LABEL_63;
  }
  wcscpy_s(Destination, 0x80u, L"CLSID\\");
  wcscat_s(Destination, 0x80u, Source);
  wcscat_s(Destination, 0x80u, L"\\InprocServer32");
  v12 = RegOpenKeyExW(HKEY_CLASSES_ROOT, Destination, 0, 0x20019u, &hKey);
  v11 = v12;
  v13 = v12 <= 0;
  if ( v12 )
    goto LABEL_6;
  v12 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  v11 = v12;
  v13 = v12 <= 0;
  if ( v12 )
    goto LABEL_6;
  for ( i = 0; i < cSubKeys; ++i )
  {
    cchName = 32;
    v12 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    v11 = v12;
    v13 = v12 <= 0;
    if ( v12 )
      goto LABEL_6;
    if ( AssemblyVersion::Init((AssemblyVersion *)&v29, Name, 0) >= 0 )
    {
      wcscpy_s(v40, 0x20u, Name);
      v12 = RegOpenKeyExW(hKey, Name, 0, 0x20019u, &phkResult);
      v11 = v12;
      v13 = v12 <= 0;
      if ( v12 )
        goto LABEL_6;
      if ( RegQueryValueExW(phkResult, L"ImplementedInThisVersion", 0, &Type, 0, &cbData) )
      {
        if ( RegQueryValueExW(phkResult, L"Assembly", 0, &Type, 0, &cbData)
          || Type != 1
          || !cbData
          || RegQueryValueExW(phkResult, L"Class", 0, &Type, 0, &cbData)
          || Type != 1
          || !cbData
          || RegQueryValueExW(phkResult, L"RuntimeVersion", 0, &Type, 0, &cbData)
          || Type != 1
          || !cbData )
        {
          RegCloseKey(phkResult);
          phkResult = 0;
          continue;
        }
      }
      else
      {
        *v35 = 1;
      }
      RegCloseKey(phkResult);
      phkResult = 0;
      if ( !v6
        || (HIWORD(v29) | ((WORD2(v29) | ((WORD1(v29) | ((unsigned __int64)(unsigned __int16)v29 << 16)) << 16)) << 16)) >= ((unsigned __int16)Data3 | ((Data2 | ((Data1_high | ((unsigned __int64)Data1 << 16)) << 16)) << 16)) )
      {
        *(_QWORD *)&v32.Data1 = v29;
        wcscpy_s(v38, 0x20u, v40);
        Data1 = v32.Data1;
        Data1_high = HIWORD(v32.Data1);
        Data2 = v32.Data2;
        Data3 = v32.Data3;
      }
      v6 = 1;
    }
  }
  v15 = 0;
  if ( v6 )
  {
LABEL_58:
    v21 = -1;
    do
      ++v21;
    while ( v38[v21] );
    v22 = v21 + 1;
    v23 = v22 * (unsigned __int128)2uLL;
    if ( !is_mul_ok(v22, 2u) )
      *(_QWORD *)&v23 = -1;
    v24 = (wchar_t *)operator new(v23, *((const struct NoThrow **)&v23 + 1));
    *v36 = v24;
    wcscpy_s(v24, v22, v38);
    *v37 = v15;
    v11 = 0;
    goto LABEL_63;
  }
  if ( RegQueryValueExW(hKey, L"Class", 0, &Type, 0, &cbData) )
    goto LABEL_57;
  if ( Type != 1 )
    goto LABEL_57;
  if ( !cbData )
    goto LABEL_57;
  RegQueryValueExW(hKey, L"RuntimeVersion", 0, &Type, 0, &cbData);
  if ( RegQueryValueExW(hKey, L"Assembly", 0, &Type, 0, &cbData) || Type != 1 || !cbData )
    goto LABEL_57;
  v16 = (cbData + 1) * (unsigned __int128)2u;
  if ( !is_mul_ok(cbData + 1, 2u) )
    *(_QWORD *)&v16 = -1;
  v10 = (BYTE *)operator new(v16, *((const struct NoThrow **)&v16 + 1));
  if ( !v10 )
  {
    v11 = -2147024882;
    goto LABEL_63;
  }
  v12 = RegQueryValueExW(hKey, L"Assembly", 0, &Type, v10, &cbData);
  v11 = v12;
  v13 = v12 <= 0;
  if ( v12 )
  {
LABEL_6:
    if ( !v13 )
      v11 = (unsigned __int16)v12 | 0x80070000;
    goto LABEL_63;
  }
  wcslwr_s((wchar_t *)v10, cbData + 1);
  v17 = wcsstr((const wchar_t *)v10, L"version=");
  if ( v17 )
  {
    v18 = v17 + 8;
    v19 = v17 + 8;
    for ( j = v17[8]; j != 44 && j; j = *v19 )
      ++v19;
    *v19 = 0;
    while ( iswspace(*v18) )
      ++v18;
    while ( iswspace(*--v19) && v19 > v18 )
      *v19 = 0;
    if ( AssemblyVersion::Init((AssemblyVersion *)&v32, v18, 0) >= 0 )
    {
      wcscpy_s(v38, 0x20u, v18);
      v15 = 1;
      goto LABEL_58;
    }
  }
LABEL_57:
  v11 = -2147221164;
LABEL_63:
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v10 )
    operator delete(v10);
  return v11;
}

```

## disassembly

```asm
0x180009350  push    rbp
0x180009352  push    rbx
0x180009353  push    rsi
0x180009354  push    rdi
0x180009355  push    r12
0x180009357  push    r13
0x180009359  push    r14
0x18000935b  push    r15
0x18000935d  lea     rbp, [rsp-218h]
0x180009365  sub     rsp, 318h
0x18000936c  mov     rax, cs:__security_cookie
0x180009373  xor     rax, rsp
0x180009376  mov     [rbp+250h+var_50], rax
0x18000937d  mov     [rbp+250h+var_2A0], r9
0x180009381  mov     r8, [rbp+250h+arg_20]; unsigned int
0x180009388  mov     [rbp+250h+var_298], r8
0x18000938c  mov     rdx, [rbp+250h+arg_28]
0x180009393  mov     [rbp+250h+var_2A8], rdx
0x180009397  xor     r14d, r14d
0x18000939a  mov     [rbp+250h+cchName], r14d
0x18000939e  mov     [rsp+350h+hKey], r14
0x1800093a3  mov     [rsp+350h+var_2E8], r14
0x1800093a8  mov     [rsp+350h+Type], r14d
0x1800093ad  mov     [rsp+350h+cbData], r14d
0x1800093b2  mov     [rbp+250h+cSubKeys], r14d
0x1800093b6  mov     r15d, r14d
0x1800093b9  mov     r12d, r14d
0x1800093bc  mov     r13d, r14d
0x1800093bf  mov     [rbp+250h+var_2D0], r14d
0x1800093c3  mov     [rsp+350h+var_2E0], r14
0x1800093c8  mov     [rdx], r14d
0x1800093cb  test    r9, r9
0x1800093ce  jz      loc_180009980
0x1800093d4  test    r8, r8
0x1800093d7  jz      loc_180009980
0x1800093dd  mov     esi, r14d
0x1800093e0  mov     [r9], r14
0x1800093e3  mov     [r8], r14d
0x1800093e6  movups  xmm0, xmmword ptr [rcx]
0x1800093e9  movdqu  xmmword ptr [rbp+250h+var_2C0.Data1], xmm0
0x1800093ee  lea     rdx, [rbp+250h+Source]; unsigned __int16 *
0x1800093f5  lea     rcx, [rbp+250h+var_2C0]; struct _GUID
0x1800093f9  call    ?GuidToLPWSTR@@YAHU_GUID@@PEAGK@Z; GuidToLPWSTR(_GUID,ushort *,ulong)
0x1800093fe  test    eax, eax
0x180009400  jnz     short loc_18000940C
0x180009402  mov     ebx, 80070057h
0x180009407  jmp     loc_180009951
0x18000940c  lea     r8, aClsid; "CLSID\\"
0x180009413  mov     ebx, 80h
0x180009418  mov     edx, ebx; SizeInWords
0x18000941a  lea     rcx, [rbp+250h+Destination]; Destination
0x180009421  call    wcscpy_s
0x180009426  lea     r8, [rbp+250h+Source]; Source
0x18000942d  mov     edx, ebx; SizeInWords
0x18000942f  lea     rcx, [rbp+250h+Destination]; Destination
0x180009436  call    wcscat_s
0x18000943b  lea     r8, aInprocserver32; "\\InprocServer32"
0x180009442  mov     edx, ebx; SizeInWords
0x180009444  lea     rcx, [rbp+250h+Destination]; Destination
0x18000944b  call    wcscat_s
0x180009450  lea     rax, [rsp+350h+hKey]
0x180009455  mov     [rsp+350h+phkResult], rax; phkResult
0x18000945a  mov     r9d, 20019h; samDesired
0x180009460  xor     r8d, r8d; ulOptions
0x180009463  lea     rdx, [rbp+250h+Destination]; lpSubKey
0x18000946a  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180009471  call    cs:__imp_RegOpenKeyExW
0x180009477  mov     ebx, eax
0x180009479  test    eax, eax
0x18000947b  jz      short loc_180009491
0x18000947d  jle     loc_180009951
0x180009483  movzx   ebx, ax
0x180009486  or      ebx, 80070000h
0x18000948c  jmp     loc_180009951
0x180009491  mov     [rsp+350h+lpftLastWriteTime], r14; lpftLastWriteTime
0x180009496  mov     [rsp+350h+lpcbSecurityDescriptor], r14; lpcbSecurityDescriptor
0x18000949b  mov     [rsp+350h+lpcbMaxValueLen], r14; lpcbMaxValueLen
0x1800094a0  mov     [rsp+350h+lpcbMaxValueNameLen], r14; lpcbMaxValueNameLen
0x1800094a5  mov     [rsp+350h+lpcValues], r14; lpcValues
0x1800094aa  mov     [rsp+350h+lpcbMaxClassLen], r14; lpcbMaxClassLen
0x1800094af  mov     [rsp+350h+lpcbMaxSubKeyLen], r14; lpcbMaxSubKeyLen
0x1800094b4  lea     rax, [rbp+250h+cSubKeys]
0x1800094b8  mov     [rsp+350h+phkResult], rax; lpcSubKeys
0x1800094bd  xor     r9d, r9d; lpReserved
0x1800094c0  xor     r8d, r8d; lpcchClass
0x1800094c3  xor     edx, edx; lpClass
0x1800094c5  mov     rcx, [rsp+350h+hKey]; hKey
0x1800094ca  call    cs:__imp_RegQueryInfoKeyW
0x1800094d0  mov     ebx, eax
0x1800094d2  test    eax, eax
0x1800094d4  jnz     short loc_18000947D
0x1800094d6  xor     ebx, ebx
0x1800094d8  mov     edi, ebx
0x1800094da  cmp     edi, [rbp+250h+cSubKeys]
0x1800094dd  jnb     loc_18000973C
0x1800094e3  mov     [rbp+250h+cchName], 20h ; ' '
0x1800094ea  mov     [rsp+350h+lpcValues], rbx; lpftLastWriteTime
0x1800094ef  mov     [rsp+350h+lpcbMaxClassLen], rbx; lpcchClass
0x1800094f4  mov     [rsp+350h+lpcbMaxSubKeyLen], rbx; lpClass
0x1800094f9  mov     [rsp+350h+phkResult], rbx; lpReserved
0x1800094fe  lea     r9, [rbp+250h+cchName]; lpcchName
0x180009502  lea     r8, [rbp+250h+Name]; lpName
0x180009506  mov     edx, edi; dwIndex
0x180009508  mov     rcx, [rsp+350h+hKey]; hKey
0x18000950d  call    cs:__imp_RegEnumKeyExW
0x180009513  mov     ebx, eax
0x180009515  test    eax, eax
0x180009517  jnz     loc_18000947D
0x18000951d  xor     r8d, r8d; int
0x180009520  lea     rdx, [rbp+250h+Name]; unsigned __int16 *
0x180009524  lea     rcx, [rsp+350h+var_2E0]; this
0x180009529  call    ?Init@AssemblyVersion@@QEAAJPEBGH@Z; AssemblyVersion::Init(ushort const *,int)
0x18000952e  xor     ebx, ebx
0x180009530  test    eax, eax
0x180009532  js      loc_180009735
0x180009538  lea     r8, [rbp+250h+Name]; Source
0x18000953c  lea     edx, [rbx+20h]; SizeInWords
0x18000953f  lea     rcx, [rbp+250h+var_210]; Destination
0x180009543  call    wcscpy_s
0x180009548  lea     rax, [rsp+350h+var_2E8]
0x18000954d  mov     [rsp+350h+phkResult], rax; phkResult
0x180009552  mov     r9d, 20019h; samDesired
0x180009558  xor     r8d, r8d; ulOptions
0x18000955b  lea     rdx, [rbp+250h+Name]; lpSubKey
0x18000955f  mov     rcx, [rsp+350h+hKey]; hKey
0x180009564  call    cs:__imp_RegOpenKeyExW
0x18000956a  mov     ebx, eax
0x18000956c  test    eax, eax
0x18000956e  jnz     loc_18000947D
0x180009574  lea     rax, [rsp+350h+cbData]
0x180009579  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000957e  xor     ebx, ebx
0x180009580  mov     [rsp+350h+phkResult], rbx; lpData
0x180009585  lea     r9, [rsp+350h+Type]; lpType
0x18000958a  xor     r8d, r8d; lpReserved
0x18000958d  lea     rdx, aImplementedint; "ImplementedInThisVersion"
0x180009594  mov     rcx, [rsp+350h+var_2E8]; hKey
0x180009599  call    cs:__imp_RegQueryValueExW
0x18000959f  test    eax, eax
0x1800095a1  jnz     short loc_1800095B2
0x1800095a3  mov     rax, [rbp+250h+var_2A8]
0x1800095a7  mov     dword ptr [rax], 1
0x1800095ad  jmp     loc_180009684
0x1800095b2  lea     rax, [rsp+350h+cbData]
0x1800095b7  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800095bc  mov     [rsp+350h+phkResult], rbx; lpData
0x1800095c1  lea     r9, [rsp+350h+Type]; lpType
0x1800095c6  xor     r8d, r8d; lpReserved
0x1800095c9  lea     rdx, aAssembly; "Assembly"
0x1800095d0  mov     rcx, [rsp+350h+var_2E8]; hKey
0x1800095d5  call    cs:__imp_RegQueryValueExW
0x1800095db  test    eax, eax
0x1800095dd  jnz     loc_180009725
0x1800095e3  cmp     [rsp+350h+Type], 1
0x1800095e8  jnz     loc_180009725
0x1800095ee  cmp     [rsp+350h+cbData], ebx
0x1800095f2  jbe     loc_180009725
0x1800095f8  lea     rax, [rsp+350h+cbData]
0x1800095fd  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x180009602  mov     [rsp+350h+phkResult], rbx; lpData
0x180009607  lea     r9, [rsp+350h+Type]; lpType
0x18000960c  xor     r8d, r8d; lpReserved
0x18000960f  lea     rdx, aClass; "Class"
0x180009616  mov     rcx, [rsp+350h+var_2E8]; hKey
0x18000961b  call    cs:__imp_RegQueryValueExW
0x180009621  test    eax, eax
0x180009623  jnz     loc_180009725
0x180009629  cmp     [rsp+350h+Type], 1
0x18000962e  jnz     loc_180009725
0x180009634  cmp     [rsp+350h+cbData], ebx
0x180009638  jbe     loc_180009725
0x18000963e  lea     rax, [rsp+350h+cbData]
0x180009643  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x180009648  mov     [rsp+350h+phkResult], rbx; lpData
0x18000964d  lea     r9, [rsp+350h+Type]; lpType
0x180009652  xor     r8d, r8d; lpReserved
0x180009655  lea     rdx, aRuntimeversion; "RuntimeVersion"
0x18000965c  mov     rcx, [rsp+350h+var_2E8]; hKey
0x180009661  call    cs:__imp_RegQueryValueExW
0x180009667  test    eax, eax
0x180009669  jnz     loc_180009725
0x18000966f  cmp     [rsp+350h+Type], 1
0x180009674  jnz     loc_180009725
0x18000967a  cmp     [rsp+350h+cbData], ebx
0x18000967e  jbe     loc_180009725
0x180009684  mov     rcx, [rsp+350h+var_2E8]; hKey
0x180009689  call    cs:__imp_RegCloseKey
0x18000968f  mov     [rsp+350h+var_2E8], rbx
0x180009694  test    r14d, r14d
0x180009697  jz      short loc_1800096EC
0x180009699  movzx   edx, r15w
0x18000969d  shl     rdx, 10h
0x1800096a1  movzx   eax, r12w
0x1800096a5  or      rdx, rax
0x1800096a8  shl     rdx, 10h
0x1800096ac  movzx   eax, r13w
0x1800096b0  or      rdx, rax
0x1800096b3  shl     rdx, 10h
0x1800096b7  movzx   eax, word ptr [rbp+250h+var_2D0]
0x1800096bb  or      rdx, rax
0x1800096be  movzx   ecx, word ptr [rsp+350h+var_2E0]
0x1800096c3  shl     rcx, 10h
0x1800096c7  movzx   eax, word ptr [rsp+350h+var_2E0+2]
0x1800096cc  or      rcx, rax
0x1800096cf  shl     rcx, 10h
0x1800096d3  movzx   eax, word ptr [rsp+350h+var_2E0+4]
0x1800096d8  or      rcx, rax
0x1800096db  shl     rcx, 10h
0x1800096df  movzx   eax, word ptr [rsp+350h+var_2E0+6]
0x1800096e4  or      rcx, rax
0x1800096e7  cmp     rcx, rdx
0x1800096ea  jb      short loc_18000971D
0x1800096ec  mov     rax, [rsp+350h+var_2E0]
0x1800096f1  mov     qword ptr [rbp+250h+var_2C0.Data1], rax
0x1800096f5  lea     r8, [rbp+250h+var_210]; Source
0x1800096f9  mov     edx, 20h ; ' '; SizeInWords
0x1800096fe  lea     rcx, [rbp+250h+var_290]; Destination
0x180009702  call    wcscpy_s
0x180009707  movzx   eax, [rbp+250h+var_2C0.Data3]
0x18000970b  movzx   r15d, word ptr [rbp+250h+var_2C0.Data1]
0x180009710  movzx   r12d, word ptr [rbp+250h+var_2C0.Data1+2]
0x180009715  movzx   r13d, [rbp+250h+var_2C0.Data2]
0x18000971a  mov     [rbp+250h+var_2D0], eax
0x18000971d  mov     r14d, 1
0x180009723  jmp     short loc_180009735
0x180009725  mov     rcx, [rsp+350h+var_2E8]; hKey
0x18000972a  call    cs:__imp_RegCloseKey
0x180009730  mov     [rsp+350h+var_2E8], rbx
0x180009735  inc     edi
0x180009737  jmp     loc_1800094DA
0x18000973c  mov     edi, ebx
0x18000973e  mov     r15d, 2
0x180009744  or      r12, 0FFFFFFFFFFFFFFFFh
0x180009748  test    r14d, r14d
0x18000974b  jnz     loc_180009909
0x180009751  lea     rax, [rsp+350h+cbData]
0x180009756  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000975b  xor     r14d, r14d
0x18000975e  mov     [rsp+350h+phkResult], r14; lpData
0x180009763  lea     r9, [rsp+350h+Type]; lpType
0x180009768  xor     r8d, r8d; lpReserved
0x18000976b  lea     rdx, aClass; "Class"
0x180009772  mov     rcx, [rsp+350h+hKey]; hKey
0x180009777  call    cs:__imp_RegQueryValueExW
0x18000977d  test    eax, eax
0x18000977f  jnz     loc_180009902
0x180009785  cmp     [rsp+350h+Type], 1
0x18000978a  jnz     loc_180009902
0x180009790  cmp     [rsp+350h+cbData], r14d
0x180009795  jbe     loc_180009902
0x18000979b  lea     rax, [rsp+350h+cbData]
0x1800097a0  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800097a5  mov     [rsp+350h+phkResult], r14; lpData
0x1800097aa  lea     r9, [rsp+350h+Type]; lpType
0x1800097af  xor     r8d, r8d; lpReserved
0x1800097b2  lea     rdx, aRuntimeversion; "RuntimeVersion"
0x1800097b9  mov     rcx, [rsp+350h+hKey]; hKey
0x1800097be  call    cs:__imp_RegQueryValueExW
0x1800097c4  lea     rax, [rsp+350h+cbData]
0x1800097c9  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x1800097ce  mov     [rsp+350h+phkResult], r14; lpData
0x1800097d3  lea     r9, [rsp+350h+Type]; lpType
0x1800097d8  xor     r8d, r8d; lpReserved
0x1800097db  lea     rdx, aAssembly; "Assembly"
0x1800097e2  mov     rcx, [rsp+350h+hKey]; hKey
0x1800097e7  call    cs:__imp_RegQueryValueExW
0x1800097ed  test    eax, eax
0x1800097ef  jnz     loc_180009902
0x1800097f5  cmp     [rsp+350h+Type], 1
0x1800097fa  jnz     loc_180009902
0x180009800  mov     eax, [rsp+350h+cbData]
0x180009804  test    eax, eax
0x180009806  jz      loc_180009902
0x18000980c  lea     ecx, [rax+1]
0x18000980f  mov     eax, r15d
0x180009812  mul     rcx
0x180009815  cmovb   rax, r12
0x180009819  mov     rcx, rax; unsigned __int64
0x18000981c  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180009821  mov     rsi, rax
0x180009824  test    rax, rax
0x180009827  jnz     short loc_180009833
0x180009829  mov     ebx, 8007000Eh
0x18000982e  jmp     loc_180009951
0x180009833  lea     rax, [rsp+350h+cbData]
0x180009838  mov     [rsp+350h+lpcbMaxSubKeyLen], rax; lpcbData
0x18000983d  mov     [rsp+350h+phkResult], rsi; lpData
0x180009842  lea     r9, [rsp+350h+Type]; lpType
0x180009847  xor     r8d, r8d; lpReserved
0x18000984a  lea     rdx, aAssembly; "Assembly"
0x180009851  mov     rcx, [rsp+350h+hKey]; hKey
0x180009856  call    cs:__imp_RegQueryValueExW
0x18000985c  mov     ebx, eax
0x18000985e  test    eax, eax
0x180009860  jnz     loc_18000947D
0x180009866  mov     edx, [rsp+350h+cbData]
0x18000986a  inc     edx; SizeInWords
0x18000986c  mov     rcx, rsi; String
0x18000986f  call    _wcslwr_s
0x180009874  lea     rdx, aVersion_0; "version="
  ... truncated ...
```
