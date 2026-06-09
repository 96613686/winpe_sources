# DeleteRememberedConnection

- ea: `0x18000d710`
- end: `0x18000da3c`
- name: `DeleteRememberedConnection`
- size: `812`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180004a40`

## callees

- `0x1800016c8`
- `0x18000d710`
- `0x18000da44`
- `0x18000e198`
- `0x180012e32`
- `0x180012e70`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000d8ca`
- `msvcrt!wcscat_s` at `0x18000d8ca`
- `msvcrt!wcsncpy_s` at `0x18000d835`
- `msvcrt!wcsncpy_s` at `0x18000d835`
- `KERNEL32!GetCurrentProcess` at `0x18000d785`
- `KERNEL32!GetCurrentProcess` at `0x18000d785`
- `ADVAPI32!RegEnumKeyExW` at `0x18000d98d`
- `ADVAPI32!RegEnumKeyExW` at `0x18000d98d`
- `ADVAPI32!RegCreateKeyExW` at `0x18000d90b`
- `ADVAPI32!RegCreateKeyExW` at `0x18000d90b`
- `ADVAPI32!EqualSid` at `0x18000d7ee`
- `ADVAPI32!EqualSid` at `0x18000d7ee`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d7ca`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d7ca`
- `ADVAPI32!InitializeSid` at `0x18000d7af`
- `ADVAPI32!InitializeSid` at `0x18000d7af`
- `ADVAPI32!RegDeleteKeyW` at `0x18000d930`
- `ADVAPI32!RegDeleteKeyW` at `0x18000d9c3`
- `ADVAPI32!RegDeleteKeyW` at `0x18000d9fb`
- `ADVAPI32!RegDeleteKeyW` at `0x18000d930`
- `ADVAPI32!RegDeleteKeyW` at `0x18000d9c3`
- `ADVAPI32!RegDeleteKeyW` at `0x18000d9fb`
- `ADVAPI32!RegCloseKey` at `0x18000d941`
- `ADVAPI32!RegCloseKey` at `0x18000d9e5`
- `ADVAPI32!RegCloseKey` at `0x18000d941`
- `ADVAPI32!RegCloseKey` at `0x18000d9e5`

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
0x18000d710  mov     [rsp-8+arg_0], rbx
0x18000d715  mov     [rsp-8+arg_10], rsi
0x18000d71a  push    rbp
0x18000d71b  push    rdi
0x18000d71c  push    r14
0x18000d71e  lea     rbp, [rsp-6B0h]
0x18000d726  sub     rsp, 7B0h
0x18000d72d  mov     rax, cs:__security_cookie
0x18000d734  xor     rax, rsp
0x18000d737  mov     [rbp+6C0h+var_20], rax
0x18000d73e  mov     rbx, rdx
0x18000d741  lea     rcx, [rbp+6C0h+var_64E]; void *
0x18000d745  xor     edi, edi
0x18000d747  xor     edx, edx; Val
0x18000d749  mov     r8d, 206h; Size
0x18000d74f  mov     [rbp+6C0h+Destination], di
0x18000d753  call    memset_0
0x18000d758  mov     dword ptr [rsp+7C0h+pIdentifierAuthority.Value], edi
0x18000d75c  mov     word ptr [rsp+7C0h+pIdentifierAuthority.Value+4], 500h
0x18000d763  mov     qword ptr [rsp+7C0h+ftLastWriteTime.dwLowDateTime], rdi
0x18000d768  mov     [rsp+7C0h+hKey], rdi
0x18000d76d  mov     [rsp+7C0h+cchName], edi
0x18000d771  mov     [rsp+7C0h+dwDisposition], edi
0x18000d775  mov     [rbp+6C0h+var_44A], di
0x18000d77c  test    rbx, rbx
0x18000d77f  jz      loc_18000DA09
0x18000d785  call    cs:__imp_GetCurrentProcess
0x18000d78c  nop     dword ptr [rax+rax+00h]
0x18000d791  lea     rdx, [rbp+6C0h+pSid1]
0x18000d795  call    DaGetProcessSid
0x18000d79a  test    eax, eax
0x18000d79c  jnz     loc_18000DA09
0x18000d7a2  mov     r8b, 1; nSubAuthorityCount
0x18000d7a5  lea     rdx, [rsp+7C0h+pIdentifierAuthority]; pIdentifierAuthority
0x18000d7aa  lea     rcx, [rsp+7C0h+Sid]; Sid
0x18000d7af  call    cs:__imp_InitializeSid
0x18000d7b6  nop     dword ptr [rax+rax+00h]
0x18000d7bb  test    eax, eax
0x18000d7bd  jz      loc_18000DA09
0x18000d7c3  xor     edx, edx; nSubAuthority
0x18000d7c5  lea     rcx, [rsp+7C0h+Sid]; pSid
0x18000d7ca  call    cs:__imp_GetSidSubAuthority
0x18000d7d1  nop     dword ptr [rax+rax+00h]
0x18000d7d6  test    rax, rax
0x18000d7d9  jz      loc_18000DA09
0x18000d7df  lea     rdx, [rsp+7C0h+Sid]; pSid2
0x18000d7e4  mov     dword ptr [rax], 12h
0x18000d7ea  lea     rcx, [rbp+6C0h+pSid1]; pSid1
0x18000d7ee  call    cs:__imp_EqualSid
0x18000d7f5  nop     dword ptr [rax+rax+00h]
0x18000d7fa  test    eax, eax
0x18000d7fc  jnz     loc_18000DA09
0x18000d802  mov     r14, 0FFFFFFFF80000002h
0x18000d809  lea     r9, [rbp+6C0h+SubKey]
0x18000d810  mov     r8, r14
0x18000d813  lea     rdx, aPersistent_0; "Persistent\\"
0x18000d81a  lea     rcx, [rbp+6C0h+pSid1]
0x18000d81e  call    DaBuildRegistryPath
0x18000d823  mov     r8, [rbx+8]; Source
0x18000d827  lea     rcx, [rbp+6C0h+Destination]; Destination
0x18000d82b  mov     r9d, 103h; MaxCount
0x18000d831  lea     edx, [r9+1]; SizeInWords
0x18000d835  call    cs:__imp_wcsncpy_s
0x18000d83c  nop     dword ptr [rax+rax+00h]
0x18000d841  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000d845  lea     rdx, [rbp+6C0h+Destination]
0x18000d849  mov     rax, rcx
0x18000d84c  inc     rax
0x18000d84f  cmp     [rdx+rax*2], di
0x18000d853  jnz     short loc_18000D84C
0x18000d855  test    rax, rax
0x18000d858  jnz     short loc_18000D864
0x18000d85a  mov     eax, 80030057h
0x18000d85f  jmp     loc_18000DA0E
0x18000d864  cmp     [rbp+rax*2+6C0h+var_652], 5Ch ; '\'
0x18000d86a  mov     esi, 208h
0x18000d86f  jz      short loc_18000D879
0x18000d871  cmp     [rbp+rax*2+6C0h+var_652], 3Ah ; ':'
0x18000d877  jnz     short loc_18000D88F
0x18000d879  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rax*2]
0x18000d881  cmp     rdx, rsi
0x18000d884  jnb     loc_18000DA36
0x18000d88a  mov     [rbp+rdx+6C0h+Destination], di
0x18000d88f  lea     rax, [rbp+6C0h+Destination]
0x18000d893  inc     rcx
0x18000d896  cmp     [rax+rcx*2], di
0x18000d89a  jnz     short loc_18000D893
0x18000d89c  cmp     [rbp+rcx*2+6C0h+var_652], 3Ah ; ':'
0x18000d8a2  jnz     short loc_18000D8BA
0x18000d8a4  lea     rcx, ds:0FFFFFFFFFFFFFFFEh[rcx*2]
0x18000d8ac  cmp     rcx, rsi
0x18000d8af  jnb     loc_18000DA36
0x18000d8b5  mov     [rbp+rcx+6C0h+Destination], di
0x18000d8ba  lea     r8, [rbp+6C0h+Destination]; Source
0x18000d8be  mov     edx, 104h; SizeInWords
0x18000d8c3  lea     rcx, [rbp+6C0h+SubKey]; Destination
0x18000d8ca  call    cs:__imp_wcscat_s
0x18000d8d1  nop     dword ptr [rax+rax+00h]
0x18000d8d6  lea     rax, [rsp+7C0h+dwDisposition]
0x18000d8db  xor     r9d, r9d; lpClass
0x18000d8de  mov     [rsp+7C0h+lpdwDisposition], rax; lpdwDisposition
0x18000d8e3  lea     rdx, [rbp+6C0h+SubKey]; lpSubKey
0x18000d8ea  lea     rax, [rsp+7C0h+hKey]
0x18000d8ef  xor     r8d, r8d; Reserved
0x18000d8f2  mov     [rsp+7C0h+phkResult], rax; phkResult
0x18000d8f7  mov     rcx, r14; hKey
0x18000d8fa  mov     [rsp+7C0h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000d8ff  mov     [rsp+7C0h+samDesired], 0F003Fh; samDesired
0x18000d907  mov     [rsp+7C0h+dwOptions], edi; dwOptions
0x18000d90b  call    cs:__imp_RegCreateKeyExW
0x18000d912  nop     dword ptr [rax+rax+00h]
0x18000d917  test    eax, eax
0x18000d919  jnz     loc_18000DA09
0x18000d91f  cmp     [rsp+7C0h+dwDisposition], 2
0x18000d924  jz      short loc_18000D957
0x18000d926  lea     rdx, [rbp+6C0h+SubKey]; lpSubKey
0x18000d92d  mov     rcx, r14; hKey
0x18000d930  call    cs:__imp_RegDeleteKeyW
0x18000d937  nop     dword ptr [rax+rax+00h]
0x18000d93c  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18000d941  call    cs:__imp_RegCloseKey
0x18000d948  nop     dword ptr [rax+rax+00h]
0x18000d94d  mov     eax, 14h
0x18000d952  jmp     loc_18000DA0E
0x18000d957  mov     ebx, edi
0x18000d959  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18000d95e  lea     rax, [rsp+7C0h+ftLastWriteTime]
0x18000d963  mov     [rsp+7C0h+phkResult], rax; lpftLastWriteTime
0x18000d968  lea     r9, [rsp+7C0h+cchName]; lpcchName
0x18000d96d  mov     [rsp+7C0h+lpSecurityAttributes], rdi; lpcchClass
0x18000d972  lea     r8, [rbp+6C0h+Name]; lpName
0x18000d979  mov     qword ptr [rsp+7C0h+samDesired], rdi; lpClass
0x18000d97e  mov     edx, ebx; dwIndex
0x18000d980  mov     qword ptr [rsp+7C0h+dwOptions], rdi; lpReserved
0x18000d985  mov     [rsp+7C0h+cchName], 104h
0x18000d98d  call    cs:__imp_RegEnumKeyExW
0x18000d994  nop     dword ptr [rax+rax+00h]
0x18000d999  test    eax, eax
0x18000d99b  jnz     short loc_18000D9CF
0x18000d99d  mov     ecx, [rsp+7C0h+cchName]
0x18000d9a1  dec     ecx
0x18000d9a3  add     rcx, rcx
0x18000d9a6  cmp     rcx, rsi
0x18000d9a9  jnb     loc_18000DA36
0x18000d9af  mov     [rbp+rcx+6C0h+Name], di
0x18000d9b7  lea     rdx, [rbp+6C0h+Name]; lpSubKey
0x18000d9be  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18000d9c3  call    cs:__imp_RegDeleteKeyW
0x18000d9ca  nop     dword ptr [rax+rax+00h]
0x18000d9cf  inc     ebx
0x18000d9d1  test    eax, eax
0x18000d9d3  jz      short loc_18000D959
0x18000d9d5  cmp     eax, 0EAh
0x18000d9da  jz      loc_18000D959
0x18000d9e0  mov     rcx, [rsp+7C0h+hKey]; hKey
0x18000d9e5  call    cs:__imp_RegCloseKey
0x18000d9ec  nop     dword ptr [rax+rax+00h]
0x18000d9f1  lea     rdx, [rbp+6C0h+SubKey]; lpSubKey
0x18000d9f8  mov     rcx, r14; hKey
0x18000d9fb  call    cs:__imp_RegDeleteKeyW
0x18000da02  nop     dword ptr [rax+rax+00h]
0x18000da07  jmp     short loc_18000DA0E
0x18000da09  mov     eax, 800300FDh
0x18000da0e  mov     rcx, [rbp+6C0h+var_20]
0x18000da15  xor     rcx, rsp; StackCookie
0x18000da18  call    __security_check_cookie
0x18000da1d  lea     r11, [rsp+7C0h+var_10]
0x18000da25  mov     rbx, [r11+20h]
0x18000da29  mov     rsi, [r11+30h]
0x18000da2d  mov     rsp, r11
0x18000da30  pop     r14
0x18000da32  pop     rdi
0x18000da33  pop     rbp
0x18000da34  retn
0x18000da36  call    __report_rangecheckfailure
```
