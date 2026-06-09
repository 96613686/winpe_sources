# RdlsSecretsRegCache::CopyRegistryKeyRecursively(HKEY__ *,ushort const *,HKEY__ *,ushort const *)

- ea: `0x1800801f8`
- end: `0x180080598`
- name: `?CopyRegistryKeyRecursively@RdlsSecretsRegCache@@AEAAKPEAUHKEY__@@PEBG01@Z`
- size: `928`
- prototype: `unsigned int __fastcall(RdlsSecretsRegCache *__hidden this, HKEY, const unsigned __int16 *, HKEY, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800801f8`
- `0x180080d90`

## callees

- `0x180005665`
- `0x1800801f8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800804f7`
- `ADVAPI32!RegSetValueExW` at `0x1800804f7`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800802d9`
- `ADVAPI32!RegQueryInfoKeyW` at `0x1800802d9`
- `ADVAPI32!RegEnumValueW` at `0x1800804cb`
- `ADVAPI32!RegEnumValueW` at `0x1800804cb`
- `ADVAPI32!RegEnumKeyExW` at `0x1800803bf`
- `ADVAPI32!RegEnumKeyExW` at `0x1800803bf`
- `ADVAPI32!RegCreateKeyExW` at `0x18008031d`
- `ADVAPI32!RegCreateKeyExW` at `0x18008031d`
- `ADVAPI32!RegOpenKeyExW` at `0x180080277`
- `ADVAPI32!RegOpenKeyExW` at `0x180080277`
- `ADVAPI32!RegCloseKey` at `0x18008052b`
- `ADVAPI32!RegCloseKey` at `0x180080540`
- `ADVAPI32!RegCloseKey` at `0x18008052b`
- `ADVAPI32!RegCloseKey` at `0x180080540`
- `KERNEL32!GetLastError` at `0x180080371`
- `KERNEL32!GetLastError` at `0x180080371`
- `KERNEL32!LocalAlloc` at `0x18008035d`
- `KERNEL32!LocalAlloc` at `0x18008043e`
- `KERNEL32!LocalAlloc` at `0x180080466`
- `KERNEL32!LocalAlloc` at `0x18008035d`
- `KERNEL32!LocalAlloc` at `0x18008043e`
- `KERNEL32!LocalAlloc` at `0x180080466`
- `KERNEL32!LocalFree` at `0x1800803f8`
- `KERNEL32!LocalFree` at `0x180080554`
- `KERNEL32!LocalFree` at `0x180080568`
- `KERNEL32!LocalFree` at `0x1800803f8`
- `KERNEL32!LocalFree` at `0x180080554`
- `KERNEL32!LocalFree` at `0x180080568`

## pseudocode

```c
__int64 __fastcall RdlsSecretsRegCache::CopyRegistryKeyRecursively(
        RdlsSecretsRegCache *this,
        HKEY a2,
        const unsigned __int16 *a3,
        HKEY a4,
        LPCWSTR lpSubKey)
{
  HLOCAL v7; // rdi
  BYTE *v8; // rsi
  DWORD LastError; // ebx
  unsigned __int64 v10; // rcx
  HLOCAL v11; // rbx
  DWORD v12; // r15d
  LSTATUS v13; // r14d
  unsigned __int64 v14; // rcx
  DWORD v15; // r14d
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-11h] BYREF
  DWORD cbMaxValueLen; // [rsp+6Ch] [rbp-Dh] BYREF
  DWORD cbMaxValueNameLen; // [rsp+70h] [rbp-9h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-1h] BYREF
  DWORD cSubKeys; // [rsp+80h] [rbp+7h] BYREF
  DWORD cchName; // [rsp+84h] [rbp+Bh] BYREF
  DWORD cValues; // [rsp+88h] [rbp+Fh] BYREF
  DWORD cchValueName; // [rsp+8Ch] [rbp+13h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+17h] BYREF
  DWORD Type; // [rsp+94h] [rbp+1Bh] BYREF
  HKEY v27; // [rsp+98h] [rbp+1Fh] BYREF
  DWORD cbSecurityDescriptor; // [rsp+A0h] [rbp+27h] BYREF
  DWORD dwDisposition; // [rsp+A4h] [rbp+2Bh] BYREF

  hKey = 0;
  v27 = 0;
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  cchName = 0;
  cbMaxValueNameLen = 0;
  cchValueName = 0;
  cValues = 0;
  v7 = 0;
  cbMaxValueLen = 0;
  v8 = 0;
  dwDisposition = 0;
  cbSecurityDescriptor = 0;
  LastError = RegOpenKeyExW(a2, a3, 0, 0xF003Fu, &hKey);
  if ( LastError )
    goto LABEL_25;
  LastError = RegQueryInfoKeyW(
                hKey,
                0,
                0,
                0,
                &cSubKeys,
                &cbMaxSubKeyLen,
                0,
                &cValues,
                &cbMaxValueNameLen,
                &cbMaxValueLen,
                &cbSecurityDescriptor,
                0);
  if ( LastError )
    goto LABEL_25;
  LastError = RegCreateKeyExW(a4, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &v27, &dwDisposition);
  if ( LastError )
    goto LABEL_25;
  if ( cSubKeys )
  {
    v10 = 2LL * ++cbMaxSubKeyLen;
    if ( v10 > 0xFFFFFFFF )
    {
LABEL_24:
      LastError = 534;
      goto LABEL_25;
    }
    v11 = LocalAlloc(0x40u, (unsigned int)v10);
    if ( !v11 )
    {
LABEL_7:
      LastError = GetLastError();
      goto LABEL_25;
    }
    v12 = 0;
    do
    {
      cchName = cbMaxSubKeyLen;
      memset_0(v11, 0, 2LL * cbMaxSubKeyLen);
      v13 = RegEnumKeyExW(hKey, v12, (LPWSTR)v11, &cchName, 0, 0, 0, 0);
      if ( !v13 )
        v13 = RdlsSecretsRegCache::CopyRegistryKeyRecursively(
                this,
                hKey,
                (const unsigned __int16 *)v11,
                v27,
                (LPCWSTR)v11);
      ++v12;
    }
    while ( !v13 );
    LocalFree(v11);
    LastError = 0;
    if ( v13 != 259 )
      LastError = v13;
  }
  if ( !cValues )
    goto LABEL_25;
  v14 = 2LL * ++cbMaxValueNameLen;
  if ( v14 > 0xFFFFFFFF )
    goto LABEL_24;
  v7 = LocalAlloc(0x40u, (unsigned int)v14);
  if ( !v7 )
    goto LABEL_7;
  cbMaxValueLen += 4;
  v8 = (BYTE *)LocalAlloc(0x40u, cbMaxValueLen);
  if ( !v8 )
    goto LABEL_7;
  v15 = 0;
  do
  {
    cbData = cbMaxValueLen;
    Type = 0;
    cchValueName = cbMaxValueNameLen;
    memset_0(v7, 0, 2LL * cbMaxValueNameLen);
    LastError = RegEnumValueW(hKey, v15, (LPWSTR)v7, &cchValueName, 0, &Type, v8, &cbData);
    if ( !LastError )
      LastError = RegSetValueExW(v27, (LPCWSTR)v7, 0, Type, v8, cbData);
    ++v15;
  }
  while ( !LastError );
  if ( LastError == 259 )
    LastError = 0;
LABEL_25:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v27 )
    RegCloseKey(v27);
  if ( v7 )
    LocalFree(v7);
  if ( v8 )
    LocalFree(v8);
  return LastError;
}

```

## disassembly

```asm
0x1800801f8  mov     rax, rsp
0x1800801fb  mov     [rax+8], rbx
0x1800801ff  mov     [rax+10h], rsi
0x180080203  mov     [rax+18h], rdi
0x180080207  push    rbp
0x180080208  push    r12
0x18008020a  push    r13
0x18008020c  push    r14
0x18008020e  push    r15
0x180080210  lea     rbp, [rax-57h]
0x180080214  sub     rsp, 0A0h
0x18008021b  xor     r13d, r13d
0x18008021e  mov     r12, rcx
0x180080221  mov     rax, r8
0x180080224  mov     [rbp+4Fh+hKey], r13
0x180080228  mov     r10, rdx
0x18008022b  mov     [rbp+4Fh+var_30], r13
0x18008022f  lea     rcx, [rbp+4Fh+hKey]
0x180080233  mov     [rbp+4Fh+cSubKeys], r13d
0x180080237  mov     [rsp+0C0h+phkResult], rcx; phkResult
0x18008023c  mov     r14, r9
0x18008023f  mov     r15d, 0F003Fh
0x180080245  mov     [rbp+4Fh+cbMaxSubKeyLen], r13d
0x180080249  mov     rcx, r10; hKey
0x18008024c  mov     [rbp+4Fh+cchName], r13d
0x180080250  mov     r9d, r15d; samDesired
0x180080253  mov     [rbp+4Fh+cbMaxValueNameLen], r13d
0x180080257  xor     r8d, r8d; ulOptions
0x18008025a  mov     [rbp+4Fh+cchValueName], r13d
0x18008025e  mov     rdx, rax; lpSubKey
0x180080261  mov     [rbp+4Fh+cValues], r13d
0x180080265  mov     edi, r13d
0x180080268  mov     [rbp+4Fh+cbMaxValueLen], r13d
0x18008026c  mov     esi, r13d
0x18008026f  mov     [rbp+4Fh+dwDisposition], r13d
0x180080273  mov     [rbp+4Fh+cbSecurityDescriptor], r13d
0x180080277  call    cs:__imp_RegOpenKeyExW
0x18008027e  nop     dword ptr [rax+rax+00h]
0x180080283  mov     ebx, eax
0x180080285  test    eax, eax
0x180080287  jnz     loc_180080522
0x18008028d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180080291  lea     rax, [rbp+4Fh+cbSecurityDescriptor]
0x180080295  mov     [rsp+0C0h+lpftLastWriteTime], r13; lpftLastWriteTime
0x18008029a  xor     r9d, r9d; lpReserved
0x18008029d  mov     [rsp+0C0h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800802a2  xor     r8d, r8d; lpcchClass
0x1800802a5  lea     rax, [rbp+4Fh+cbMaxValueLen]
0x1800802a9  xor     edx, edx; lpClass
0x1800802ab  mov     [rsp+0C0h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800802b0  lea     rax, [rbp+4Fh+cbMaxValueNameLen]
0x1800802b4  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800802b9  lea     rax, [rbp+4Fh+cValues]
0x1800802bd  mov     [rsp+0C0h+lpcValues], rax; lpcValues
0x1800802c2  lea     rax, [rbp+4Fh+cbMaxSubKeyLen]
0x1800802c6  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcbMaxClassLen
0x1800802cb  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800802d0  lea     rax, [rbp+4Fh+cSubKeys]
0x1800802d4  mov     [rsp+0C0h+phkResult], rax; lpcSubKeys
0x1800802d9  call    cs:__imp_RegQueryInfoKeyW
0x1800802e0  nop     dword ptr [rax+rax+00h]
0x1800802e5  mov     ebx, eax
0x1800802e7  test    eax, eax
0x1800802e9  jnz     loc_180080522
0x1800802ef  mov     rdx, [rbp+4Fh+lpSubKey]; lpSubKey
0x1800802f3  lea     rax, [rbp+4Fh+dwDisposition]
0x1800802f7  mov     [rsp+0C0h+lpcbMaxValueNameLen], rax; lpdwDisposition
0x1800802fc  xor     r9d, r9d; lpClass
0x1800802ff  lea     rax, [rbp+4Fh+var_30]
0x180080303  xor     r8d, r8d; Reserved
0x180080306  mov     [rsp+0C0h+lpcValues], rax; phkResult
0x18008030b  mov     rcx, r14; hKey
0x18008030e  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpSecurityAttributes
0x180080313  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], r15d; samDesired
0x180080318  mov     dword ptr [rsp+0C0h+phkResult], r13d; dwOptions
0x18008031d  call    cs:__imp_RegCreateKeyExW
0x180080324  nop     dword ptr [rax+rax+00h]
0x180080329  mov     ebx, eax
0x18008032b  test    eax, eax
0x18008032d  jnz     loc_180080522
0x180080333  mov     edx, 0FFFFFFFFh
0x180080338  cmp     [rbp+4Fh+cSubKeys], r13d
0x18008033c  jbe     loc_180080417
0x180080342  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x180080345  inc     eax
0x180080347  mov     ecx, eax
0x180080349  add     rcx, rcx
0x18008034c  mov     [rbp+4Fh+cbMaxSubKeyLen], eax
0x18008034f  cmp     rcx, rdx
0x180080352  ja      loc_18008051D
0x180080358  mov     edx, ecx; uBytes
0x18008035a  lea     ecx, [rbx+40h]; uFlags
0x18008035d  call    cs:__imp_LocalAlloc
0x180080364  nop     dword ptr [rax+rax+00h]
0x180080369  mov     rbx, rax
0x18008036c  test    rax, rax
0x18008036f  jnz     short loc_180080384
0x180080371  call    cs:__imp_GetLastError
0x180080378  nop     dword ptr [rax+rax+00h]
0x18008037d  mov     ebx, eax
0x18008037f  jmp     loc_180080522
0x180080384  mov     r15d, r13d
0x180080387  mov     eax, [rbp+4Fh+cbMaxSubKeyLen]
0x18008038a  xor     edx, edx; Val
0x18008038c  mov     r8d, eax
0x18008038f  mov     [rbp+4Fh+cchName], eax
0x180080392  add     r8, r8; Size
0x180080395  mov     rcx, rbx; void *
0x180080398  call    memset_0
0x18008039d  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800803a1  lea     r9, [rbp+4Fh+cchName]; lpcchName
0x1800803a5  mov     [rsp+0C0h+lpcValues], r13; lpftLastWriteTime
0x1800803aa  mov     r8, rbx; lpName
0x1800803ad  mov     [rsp+0C0h+lpcbMaxClassLen], r13; lpcchClass
0x1800803b2  mov     edx, r15d; dwIndex
0x1800803b5  mov     [rsp+0C0h+lpcbMaxSubKeyLen], r13; lpClass
0x1800803ba  mov     [rsp+0C0h+phkResult], r13; lpReserved
0x1800803bf  call    cs:__imp_RegEnumKeyExW
0x1800803c6  nop     dword ptr [rax+rax+00h]
0x1800803cb  mov     r14d, eax
0x1800803ce  test    eax, eax
0x1800803d0  jnz     short loc_1800803ED
0x1800803d2  mov     r9, [rbp+4Fh+var_30]; HKEY
0x1800803d6  mov     r8, rbx; unsigned __int16 *
0x1800803d9  mov     rdx, [rbp+4Fh+hKey]; HKEY
0x1800803dd  mov     rcx, r12; this
0x1800803e0  mov     [rsp+0C0h+phkResult], rbx; lpSubKey
0x1800803e5  call    ?CopyRegistryKeyRecursively@RdlsSecretsRegCache@@AEAAKPEAUHKEY__@@PEBG01@Z; RdlsSecretsRegCache::CopyRegistryKeyRecursively(HKEY__ *,ushort const *,HKEY__ *,ushort const *)
0x1800803ea  mov     r14d, eax
0x1800803ed  inc     r15d
0x1800803f0  test    r14d, r14d
0x1800803f3  jz      short loc_180080387
0x1800803f5  mov     rcx, rbx; hMem
0x1800803f8  call    cs:__imp_LocalFree
0x1800803ff  nop     dword ptr [rax+rax+00h]
0x180080404  cmp     r14d, 103h
0x18008040b  mov     ebx, r13d
0x18008040e  mov     edx, 0FFFFFFFFh
0x180080413  cmovnz  ebx, r14d
0x180080417  cmp     [rbp+4Fh+cValues], r13d
0x18008041b  jbe     loc_180080522
0x180080421  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x180080424  inc     eax
0x180080426  mov     ecx, eax
0x180080428  add     rcx, rcx
0x18008042b  mov     [rbp+4Fh+cbMaxValueNameLen], eax
0x18008042e  cmp     rcx, rdx
0x180080431  ja      loc_18008051D
0x180080437  mov     edx, ecx; uBytes
0x180080439  mov     ecx, 40h ; '@'; uFlags
0x18008043e  call    cs:__imp_LocalAlloc
0x180080445  nop     dword ptr [rax+rax+00h]
0x18008044a  mov     rdi, rax
0x18008044d  test    rax, rax
0x180080450  jz      loc_180080371
0x180080456  mov     eax, [rbp+4Fh+cbMaxValueLen]
0x180080459  mov     ecx, 40h ; '@'; uFlags
0x18008045e  add     eax, 4
0x180080461  mov     edx, eax; uBytes
0x180080463  mov     [rbp+4Fh+cbMaxValueLen], eax
0x180080466  call    cs:__imp_LocalAlloc
0x18008046d  nop     dword ptr [rax+rax+00h]
0x180080472  mov     rsi, rax
0x180080475  test    rax, rax
0x180080478  jz      loc_180080371
0x18008047e  mov     r14d, r13d
0x180080481  mov     eax, [rbp+4Fh+cbMaxValueLen]
0x180080484  xor     edx, edx; Val
0x180080486  mov     [rbp+4Fh+cbData], eax
0x180080489  mov     rcx, rdi; void *
0x18008048c  mov     eax, [rbp+4Fh+cbMaxValueNameLen]
0x18008048f  mov     r8d, eax
0x180080492  mov     [rbp+4Fh+Type], r13d
0x180080496  add     r8, r8; Size
0x180080499  mov     [rbp+4Fh+cchValueName], eax
0x18008049c  call    memset_0
0x1800804a1  mov     rcx, [rbp+4Fh+hKey]; hKey
0x1800804a5  lea     rax, [rbp+4Fh+cbData]
0x1800804a9  mov     [rsp+0C0h+lpcValues], rax; lpcbData
0x1800804ae  lea     r9, [rbp+4Fh+cchValueName]; lpcchValueName
0x1800804b2  lea     rax, [rbp+4Fh+Type]
0x1800804b6  mov     [rsp+0C0h+lpcbMaxClassLen], rsi; lpData
0x1800804bb  mov     [rsp+0C0h+lpcbMaxSubKeyLen], rax; lpType
0x1800804c0  mov     r8, rdi; lpValueName
0x1800804c3  mov     edx, r14d; dwIndex
0x1800804c6  mov     [rsp+0C0h+phkResult], r13; lpReserved
0x1800804cb  call    cs:__imp_RegEnumValueW
0x1800804d2  nop     dword ptr [rax+rax+00h]
0x1800804d7  mov     ebx, eax
0x1800804d9  test    eax, eax
0x1800804db  jnz     short loc_180080505
0x1800804dd  mov     eax, [rbp+4Fh+cbData]
0x1800804e0  xor     r8d, r8d; Reserved
0x1800804e3  mov     r9d, [rbp+4Fh+Type]; dwType
0x1800804e7  mov     rdx, rdi; lpValueName
0x1800804ea  mov     rcx, [rbp+4Fh+var_30]; hKey
0x1800804ee  mov     dword ptr [rsp+0C0h+lpcbMaxSubKeyLen], eax; cbData
0x1800804f2  mov     [rsp+0C0h+phkResult], rsi; lpData
0x1800804f7  call    cs:__imp_RegSetValueExW
0x1800804fe  nop     dword ptr [rax+rax+00h]
0x180080503  mov     ebx, eax
0x180080505  inc     r14d
0x180080508  test    ebx, ebx
0x18008050a  jz      loc_180080481
0x180080510  cmp     ebx, 103h
0x180080516  jnz     short loc_180080522
0x180080518  mov     ebx, r13d
0x18008051b  jmp     short loc_180080522
0x18008051d  mov     ebx, 216h
0x180080522  mov     rcx, [rbp+4Fh+hKey]; hKey
0x180080526  test    rcx, rcx
0x180080529  jz      short loc_180080537
0x18008052b  call    cs:__imp_RegCloseKey
0x180080532  nop     dword ptr [rax+rax+00h]
0x180080537  mov     rcx, [rbp+4Fh+var_30]; hKey
0x18008053b  test    rcx, rcx
0x18008053e  jz      short loc_18008054C
0x180080540  call    cs:__imp_RegCloseKey
0x180080547  nop     dword ptr [rax+rax+00h]
0x18008054c  test    rdi, rdi
0x18008054f  jz      short loc_180080560
0x180080551  mov     rcx, rdi; hMem
0x180080554  call    cs:__imp_LocalFree
0x18008055b  nop     dword ptr [rax+rax+00h]
0x180080560  test    rsi, rsi
0x180080563  jz      short loc_180080574
0x180080565  mov     rcx, rsi; hMem
0x180080568  call    cs:__imp_LocalFree
0x18008056f  nop     dword ptr [rax+rax+00h]
0x180080574  lea     r11, [rsp+0C0h+var_20]
0x18008057c  mov     eax, ebx
0x18008057e  mov     rbx, [r11+30h]
0x180080582  mov     rsi, [r11+38h]
0x180080586  mov     rdi, [r11+40h]
0x18008058a  mov     rsp, r11
0x18008058d  pop     r15
0x18008058f  pop     r14
0x180080591  pop     r13
0x180080593  pop     r12
0x180080595  pop     rbp
0x180080596  retn
```
