# DeleteRememberedConnection

- ea: `0x18000cc98`
- end: `0x18000cf6d`
- name: `DeleteRememberedConnection`
- size: `725`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004720`

## callees

- `0x1800016c8`
- `0x18000cc98`
- `0x18000cf74`
- `0x18000d5d8`
- `0x180011b62`
- `0x180011ba0`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000ce34`
- `msvcrt!wcscat_s` at `0x18000ce34`
- `msvcrt!wcsncpy_s` at `0x18000cda5`
- `msvcrt!wcsncpy_s` at `0x18000cda5`
- `KERNEL32!GetCurrentProcess` at `0x18000cd0d`
- `KERNEL32!GetCurrentProcess` at `0x18000cd0d`
- `ADVAPI32!RegEnumKeyExW` at `0x18000cedf`
- `ADVAPI32!RegEnumKeyExW` at `0x18000cedf`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ce6f`
- `ADVAPI32!RegCreateKeyExW` at `0x18000ce6f`
- `ADVAPI32!EqualSid` at `0x18000cd64`
- `ADVAPI32!EqualSid` at `0x18000cd64`
- `ADVAPI32!GetSidSubAuthority` at `0x18000cd46`
- `ADVAPI32!GetSidSubAuthority` at `0x18000cd46`
- `ADVAPI32!InitializeSid` at `0x18000cd31`
- `ADVAPI32!InitializeSid` at `0x18000cd31`
- `ADVAPI32!RegDeleteKeyW` at `0x18000ce8e`
- `ADVAPI32!RegDeleteKeyW` at `0x18000cf0b`
- `ADVAPI32!RegDeleteKeyW` at `0x18000cf33`
- `ADVAPI32!RegDeleteKeyW` at `0x18000ce8e`
- `ADVAPI32!RegDeleteKeyW` at `0x18000cf0b`
- `ADVAPI32!RegDeleteKeyW` at `0x18000cf33`
- `ADVAPI32!RegCloseKey` at `0x18000ce99`
- `ADVAPI32!RegCloseKey` at `0x18000cf23`
- `ADVAPI32!RegCloseKey` at `0x18000ce99`
- `ADVAPI32!RegCloseKey` at `0x18000cf23`

## pseudocode

```c
LSTATUS __fastcall DeleteRememberedConnection(__int64 a1, __int64 a2)
{
  __int64 v3; // rcx
  PDWORD SidSubAuthority; // rax
  __int64 v5; // rcx
  __int64 v6; // rax
  unsigned __int64 v8; // rdx
  unsigned __int64 v9; // rcx
  DWORD v10; // ebx
  LSTATUS v11; // eax
  DWORD cchName; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+68h] [rbp-98h] BYREF
  _BYTE Sid[128]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE pSid1[128]; // [rsp+F0h] [rbp-10h] BYREF
  wchar_t Destination; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v20[516]; // [rsp+172h] [rbp+72h] BYREF
  __int16 v21; // [rsp+376h] [rbp+276h]
  wchar_t SubKey[264]; // [rsp+380h] [rbp+280h] BYREF
  WCHAR Name[264]; // [rsp+590h] [rbp+490h] BYREF

  Destination = 0;
  memset_0(v20, 0, 0x206u);
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  ftLastWriteTime = 0;
  hKey = 0;
  cchName = 0;
  dwDisposition = 0;
  v21 = 0;
  if ( !a2 )
    return -2147286787;
  GetCurrentProcess();
  if ( (unsigned int)DaGetProcessSid(v3, pSid1) )
    return -2147286787;
  if ( !InitializeSid(Sid, &pIdentifierAuthority, 1u) )
    return -2147286787;
  SidSubAuthority = GetSidSubAuthority(Sid, 0);
  if ( !SidSubAuthority )
    return -2147286787;
  *SidSubAuthority = 18;
  if ( EqualSid(pSid1, Sid) )
    return -2147286787;
  DaBuildRegistryPath(pSid1, L"Persistent\\", -2147483646, SubKey);
  wcsncpy_s(&Destination, 0x104u, *(const wchar_t **)(a2 + 8), 0x103u);
  v5 = -1;
  v6 = -1;
  do
    ++v6;
  while ( *(_WORD *)&v20[2 * v6 - 2] );
  if ( !v6 )
    return -2147286953;
  if ( *(_WORD *)&pSid1[2 * v6 + 126] == 92 || *(_WORD *)&pSid1[2 * v6 + 126] == 58 )
  {
    v8 = 2 * v6 - 2;
    if ( v8 >= 0x208 )
      goto LABEL_29;
    *(_WORD *)&v20[v8 - 2] = 0;
  }
  do
    ++v5;
  while ( *(_WORD *)&v20[2 * v5 - 2] );
  if ( *(_WORD *)&pSid1[2 * v5 + 126] == 58 )
  {
    v9 = 2 * v5 - 2;
    if ( v9 < 0x208 )
    {
      *(_WORD *)&v20[v9 - 2] = 0;
      goto LABEL_18;
    }
LABEL_29:
    _report_rangecheckfailure();
  }
LABEL_18:
  wcscat_s(SubKey, 0x104u, &Destination);
  if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition) )
    return -2147286787;
  if ( dwDisposition == 2 )
  {
    v10 = 0;
    do
    {
      cchName = 260;
      v11 = RegEnumKeyExW(hKey, v10, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
      if ( !v11 )
      {
        if ( 2 * (unsigned __int64)(cchName - 1) >= 0x208 )
          goto LABEL_29;
        Name[cchName - 1] = 0;
        v11 = RegDeleteKeyW(hKey, Name);
      }
      ++v10;
    }
    while ( !v11 || v11 == 234 );
    RegCloseKey(hKey);
    return RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
  }
  else
  {
    RegDeleteKeyW(HKEY_LOCAL_MACHINE, SubKey);
    RegCloseKey(hKey);
    return 20;
  }
}

```

## disassembly

```asm
0x18000cc98  mov     [rsp-8+arg_0], rbx
0x18000cc9d  mov     [rsp-8+arg_10], rsi
0x18000cca2  push    rbp
0x18000cca3  push    rdi
0x18000cca4  push    r14
0x18000cca6  lea     rbp, [rsp-6B0h]
0x18000ccae  sub     rsp, 7B0h
0x18000ccb5  mov     rax, cs:__security_cookie
0x18000ccbc  xor     rax, rsp
0x18000ccbf  mov     [rbp+6C0h+var_20], rax
0x18000ccc6  mov     rbx, rdx
0x18000ccc9  lea     rcx, [rbp+6C0h+var_64E]; void *
0x18000cccd  xor     edi, edi
0x18000cccf  xor     edx, edx; Val
0x18000ccd1  mov     r8d, 206h; Size
0x18000ccd7  mov     [rbp+6C0h+Destination], di
0x18000ccdb  call    memset_0
0x18000cce0  mov     dword ptr [rsp+7C0h+pIdentifierAuthority.Value], edi
0x18000cce4  mov     word ptr [rsp+7C0h+pIdentifierAuthority.Value+4], 500h
0x18000cceb  mov     qword ptr [rsp+7C0h+ftLastWriteTime.dwLowDateTime], rdi
0x18000ccf0  mov     [rsp+7C0h+hKey], rdi
0x18000ccf5  mov     [rsp+7C0h+cchName], edi
0x18000ccf9  mov     [rsp+7C0h+dwDisposition], edi
0x18000ccfd  mov     [rbp+6C0h+var_44A], di
0x18000cd04  test    rbx, rbx
0x18000cd07  jz      loc_18000CF3B
0x18000cd0d  call    cs:__imp_GetCurrentProcess
0x18000cd13  lea     rdx, [rbp+6C0h+pSid1]
0x18000cd17  call    DaGetProcessSid
0x18000cd1c  test    eax, eax
0x18000cd1e  jnz     loc_18000CF3B
0x18000cd24  mov     r8b, 1; nSubAuthorityCount
0x18000cd27  lea     rdx, [rsp+7C0h+pIdentifierAuthority]; pIdentifierAuthority
0x18000cd2c  lea     rcx, [rsp+7C0h+Sid]; Sid
0x18000cd31  call    cs:__imp_InitializeSid
0x18000cd37  test    eax, eax
0x18000cd39  jz      loc_18000CF3B
0x18000cd3f  xor     edx, edx; nSubAuthority
0x18000cd41  lea     rcx, [rsp+7C0h+Sid]; pSid
0x18000cd46  call    cs:__imp_GetSidSubAuthority
0x18000cd4c  test    rax, rax
0x18000cd4f  jz      loc_18000CF3B
0x18000cd55  lea     rdx, [rsp+7C0h+Sid]; pSid2
0x18000cd5a  mov     dword ptr [rax], 12h
0x18000cd60  lea     rcx, [rbp+6C0h+pSid1]; pSid1
0x18000cd64  call    cs:__imp_EqualSid
0x18000cd6a  test    eax, eax
0x18000cd6c  jnz     loc_18000CF3B
0x18000cd72  mov     r14, 0FFFFFFFF80000002h
0x18000cd79  lea     r9, [rbp+6C0h+SubKey]
0x18000cd80  mov     r8, r14
0x18000cd83  lea     rdx, aPersistent_0; "Persistent\\"
0x18000cd8a  lea     rcx, [rbp+6C0h+pSid1]
0x18000cd8e  call    DaBuildRegistryPath
0x18000cd93  mov     r8, [rbx+8]; Source
0x18000cd97  lea     rcx, [rbp+6C0h+Destination]; Destination
0x18000cd9b  mov     r9d, 103h; MaxCount
0x18000cda1  lea     edx, [r9+1]; SizeInWords
0x18000cda5  call    cs:__imp_wcsncpy_s
0x18000cdab  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000cdaf  lea     rdx, [rbp+6C0h+Destination]
0x18000cdb3  mov     rax, rcx
0x18000cdb6  inc     rax
0x18000cdb9  cmp     [rdx+rax*2], di
0x18000cdbd  jnz     short loc_18000CDB6
0x18000cdbf  test    rax, rax
0x18000cdc2  jnz     short loc_18000CDCE
0x18000cdc4  mov     eax, 80030057h
0x18000cdc9  jmp     loc_18000CF40
0x18000cdce  cmp     [rbp+rax*2+6C0h+var_652], 5Ch ; '\'
0x18000cdd4  mov     esi, 208h
0x18000cdd9  jz      short loc_18000CDE3
0x18000cddb  cmp     [rbp+rax*2+6C0h+var_652], 3Ah ; ':'
0x18000cde1  jnz     short loc_18000CDF9
0x18000cde3  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000cdeb  cmp     rdx, rsi
0x18000cdee  jnb     loc_18000CF67
0x18000cdf4  mov     [rbp+rdx+6C0h+Destination], di
0x18000cdf9  lea     rax, [rbp+6C0h+Destination]
0x18000cdfd  inc     rcx
0x18000ce00  cmp     [rax+rcx*2], di
0x18000ce04  jnz     short loc_18000CDFD
0x18000ce06  cmp     [rbp+rcx*2+6C0h+var_652], 3Ah ; ':'
0x18000ce0c  jnz     short loc_18000CE24
0x18000ce0e  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x18000ce16  cmp     rcx, rsi
0x18000ce19  jnb     loc_18000CF67
0x18000ce1f  mov     [rbp+rcx+6C0h+Destination], di
0x18000ce24  lea     r8, [rbp+6C0h+Destination]; Source
0x18000ce28  mov     edx, 104h; SizeInWords
0x18000ce2d  lea     rcx, [rbp+6C0h+SubKey]; Destination
0x18000ce34  call    cs:__imp_wcscat_s
0x18000ce3a  lea     rax, [rsp+7C0h+dwDisposition]
0x18000ce3f  xor     r9d, r9d; lpClass
0x18000ce42  mov     [rsp+7C0h+lpdwDisposition], rax; lpdwDisposition
0x18000ce47  lea     rdx, [rbp+6C0h+SubKey]; lpSubKey
0x18000ce4e  lea     rax, [rsp+7C0h+hKey]
0x18000ce53  xor     r8d, r8d; Reserved
0x18000ce56  mov     [rsp+7C0h+phkResult], rax; phkResult
0x18000ce5b  mov     rcx, r14; hKey
0x18000ce5e  mov     [rsp+7C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000ce63  mov     [rsp+7C0h+samDesired], 0F003Fh; samDesired
0x18000ce6b  mov     [rsp+7C0h+dwOptions], edi; dwOptions
0x18000ce6f  call    cs:__imp_RegCreateKeyExW
0x18000ce75  test    eax, eax
0x18000ce77  jnz     loc_18000CF3B
0x18000ce7d  cmp     [rsp+7C0h+dwDisposition], 2
0x18000ce82  jz      short loc_18000CEA9
0x18000ce84  lea     rdx, [rbp+6C0h+SubKey]; lpSubKey
0x18000ce8b  mov     rcx, r14; hKey
0x18000ce8e  call    cs:__imp_RegDeleteKeyW
0x18000ce94  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18000ce99  call    cs:__imp_RegCloseKey
0x18000ce9f  mov     eax, 14h
0x18000cea4  jmp     loc_18000CF40
0x18000cea9  mov     ebx, edi
0x18000ceab  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18000ceb0  lea     rax, [rsp+7C0h+ftLastWriteTime]
0x18000ceb5  mov     [rsp+7C0h+phkResult], rax; lpftLastWriteTime
0x18000ceba  lea     r9, [rsp+7C0h+cchName]; lpcchName
0x18000cebf  mov     [rsp+7C0h+lpSecurityAttributes], rdi; lpcchClass
0x18000cec4  lea     r8, [rbp+6C0h+Name]; lpName
0x18000cecb  mov     qword ptr [rsp+7C0h+samDesired], rdi; lpClass
0x18000ced0  mov     edx, ebx; dwIndex
0x18000ced2  mov     qword ptr [rsp+7C0h+dwOptions], rdi; lpReserved
0x18000ced7  mov     [rsp+7C0h+cchName], 104h
0x18000cedf  call    cs:__imp_RegEnumKeyExW
0x18000cee5  test    eax, eax
0x18000cee7  jnz     short loc_18000CF11
0x18000cee9  mov     ecx, [rsp+7C0h+cchName]
0x18000ceed  dec     ecx
0x18000ceef  add     rcx, rcx
0x18000cef2  cmp     rcx, rsi
0x18000cef5  jnb     short loc_18000CF67
0x18000cef7  mov     [rbp+rcx+6C0h+Name], di
0x18000ceff  lea     rdx, [rbp+6C0h+Name]; lpSubKey
0x18000cf06  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18000cf0b  call    cs:__imp_RegDeleteKeyW
0x18000cf11  inc     ebx
0x18000cf13  test    eax, eax
0x18000cf15  jz      short loc_18000CEAB
0x18000cf17  cmp     eax, 0EAh
0x18000cf1c  jz      short loc_18000CEAB
0x18000cf1e  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18000cf23  call    cs:__imp_RegCloseKey
0x18000cf29  lea     rdx, [rbp+6C0h+SubKey]; lpSubKey
0x18000cf30  mov     rcx, r14; hKey
0x18000cf33  call    cs:__imp_RegDeleteKeyW
0x18000cf39  jmp     short loc_18000CF40
0x18000cf3b  mov     eax, 800300FDh
0x18000cf40  mov     rcx, [rbp+6C0h+var_20]
0x18000cf47  xor     rcx, rsp; StackCookie
0x18000cf4a  call    __security_check_cookie
0x18000cf4f  lea     r11, [rsp+7C0h+var_10]
0x18000cf57  mov     rbx, [r11+20h]
0x18000cf5b  mov     rsi, [r11+30h]
0x18000cf5f  mov     rsp, r11
0x18000cf62  pop     r14
0x18000cf64  pop     rdi
0x18000cf65  pop     rbp
0x18000cf66  retn
0x18000cf67  call    __report_rangecheckfailure
```
