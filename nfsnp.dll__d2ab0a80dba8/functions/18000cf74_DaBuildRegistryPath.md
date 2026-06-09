# DaBuildRegistryPath

- ea: `0x18000cf74`
- end: `0x18000d471`
- name: `DaBuildRegistryPath`
- size: `1277`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000be24`
- `0x18000ca9c`
- `0x18000cc98`
- `0x18000fc20`

## callees

- `0x18000cf74`
- `0x18000d478`
- `0x18000d5d8`
- `0x180011b62`
- `0x180011ba0`
- `0x180011c30`

## import_xrefs

- `msvcrt!wcsncat_s` at `0x18000d332`
- `msvcrt!wcsncat_s` at `0x18000d362`
- `msvcrt!wcsncat_s` at `0x18000d332`
- `msvcrt!wcsncat_s` at `0x18000d362`
- `msvcrt!_snwprintf_s` at `0x18000d0a1`
- `msvcrt!_snwprintf_s` at `0x18000d0a1`
- `msvcrt!wcscpy_s` at `0x18000d3e6`
- `msvcrt!wcscpy_s` at `0x18000d3e6`
- `msvcrt!wcsncpy_s` at `0x18000d41d`
- `msvcrt!wcsncpy_s` at `0x18000d43e`
- `msvcrt!wcsncpy_s` at `0x18000d41d`
- `msvcrt!wcsncpy_s` at `0x18000d43e`
- `KERNEL32!GetCurrentProcess` at `0x18000d03d`
- `KERNEL32!GetCurrentProcess` at `0x18000d03d`
- `KERNEL32!GetLastError` at `0x18000d171`
- `KERNEL32!GetLastError` at `0x18000d1be`
- `KERNEL32!GetLastError` at `0x18000d248`
- `KERNEL32!GetLastError` at `0x18000d3b3`
- `KERNEL32!GetLastError` at `0x18000d171`
- `KERNEL32!GetLastError` at `0x18000d1be`
- `KERNEL32!GetLastError` at `0x18000d248`
- `KERNEL32!GetLastError` at `0x18000d3b3`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000d29c`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000d29c`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000d270`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000d270`
- `ADVAPI32!AddAce` at `0x18000d23e`
- `ADVAPI32!AddAce` at `0x18000d23e`
- `ADVAPI32!GetLengthSid` at `0x18000d1f7`
- `ADVAPI32!GetLengthSid` at `0x18000d1f7`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18000d136`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18000d136`
- `ADVAPI32!InitializeAcl` at `0x18000d11d`
- `ADVAPI32!InitializeAcl` at `0x18000d11d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000d0ff`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000d0ff`
- `ADVAPI32!CopySid` at `0x18000d150`
- `ADVAPI32!CopySid` at `0x18000d218`
- `ADVAPI32!CopySid` at `0x18000d150`
- `ADVAPI32!CopySid` at `0x18000d218`
- `ADVAPI32!RegCreateKeyExW` at `0x18000d0de`
- `ADVAPI32!RegCreateKeyExW` at `0x18000d0de`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d182`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d19a`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d1cf`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d182`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d19a`
- `ADVAPI32!GetSidSubAuthority` at `0x18000d1cf`
- `ADVAPI32!InitializeSid` at `0x18000d164`
- `ADVAPI32!InitializeSid` at `0x18000d1b4`
- `ADVAPI32!InitializeSid` at `0x18000d164`
- `ADVAPI32!InitializeSid` at `0x18000d1b4`
- `ADVAPI32!LookupAccountSidW` at `0x18000d2fa`
- `ADVAPI32!LookupAccountSidW` at `0x18000d2fa`
- `ADVAPI32!RegSetValueExW` at `0x18000d3ab`
- `ADVAPI32!RegSetValueExW` at `0x18000d3ab`
- `ADVAPI32!RegCloseKey` at `0x18000d3cd`
- `ADVAPI32!RegCloseKey` at `0x18000d3cd`
- `ADVAPI32!RegSetKeySecurity` at `0x18000d2bb`
- `ADVAPI32!RegSetKeySecurity` at `0x18000d2bb`

## pseudocode

```c
__int64 __fastcall DaBuildRegistryPath(_BYTE *a1, wchar_t *a2, __int64 a3, void *a4)
{
  wchar_t *v5; // r13
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 result; // rax
  __int64 v11; // rax
  _BYTE *v12; // rbx
  __int16 LengthSid; // ax
  BOOL v14; // eax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rcx
  DWORD dwBufferLength; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+54h] [rbp-ACh] BYREF
  DWORD cchReferencedDomainName; // [rsp+58h] [rbp-A8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *Source; // [rsp+70h] [rbp-90h]
  _OWORD pSecurityDescriptor[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v26; // [rsp+98h] [rbp-68h]
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp-60h] BYREF
  __int16 pAceList; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 v29; // [rsp+B2h] [rbp-4Eh]
  int v30; // [rsp+B4h] [rbp-4Ch]
  _BYTE v31[120]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE pDestinationSid[128]; // [rsp+130h] [rbp+30h] BYREF
  _BYTE Sid[128]; // [rsp+1B0h] [rbp+B0h] BYREF
  _BYTE pSid[128]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v35[128]; // [rsp+2B0h] [rbp+1B0h] BYREF
  _ACL pAcl; // [rsp+330h] [rbp+230h] BYREF
  _BYTE pSelfRelativeSecurityDescriptor[8192]; // [rsp+1330h] [rbp+1230h] BYREF
  wchar_t ReferencedDomainName[264]; // [rsp+3330h] [rbp+3230h] BYREF
  WCHAR Name[264]; // [rsp+3540h] [rbp+3440h] BYREF
  wchar_t Buffer[1024]; // [rsp+3750h] [rbp+3650h] BYREF

  Source = a2;
  v5 = a2;
  memset_0(Name, 0, 0x208u);
  memset_0(ReferencedDomainName, 0, 0x208u);
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  dwDisposition = 0;
  dwBufferLength = 0;
  v8 = -1;
  v26 = 0;
  cchReferencedDomainName = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  peUse = 0;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  memset_0(a4, 0, 0x208u);
  if ( a3 != -2147483646 )
  {
    wcscpy_s((wchar_t *)a4, 0x104u, L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion");
LABEL_37:
    if ( v5 )
    {
      if ( *v5 != 92 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)a4 + v18) );
        wcsncpy_s((wchar_t *)a4 + (unsigned int)v18, (unsigned int)(260 - v18), L"\\", (unsigned int)(260 - v18 - 1));
      }
      do
        ++v8;
      while ( *((_WORD *)a4 + v8) );
      wcsncpy_s((wchar_t *)a4 + (unsigned int)v8, (unsigned int)(260 - v8), v5, (unsigned int)(260 - v8 - 1));
    }
    return 0;
  }
  if ( !a1 )
  {
    GetCurrentProcess();
    result = DaGetProcessSid(v9, v35);
    if ( (_DWORD)result )
      return result;
    a1 = v35;
  }
  result = DaConvertSidToString(a1, Buffer, 0x400u);
  if ( !(_DWORD)result )
  {
    _snwprintf_s(
      (wchar_t *const)a4,
      0x104u,
      0x103u,
      L"SOFTWARE\\Microsoft\\ClientForNFS\\CurrentVersion\\Users\\%s",
      Buffer);
    if ( RegCreateKeyExW(HKEY_LOCAL_MACHINE, (LPCWSTR)a4, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition) )
    {
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    else if ( dwDisposition == 1 )
    {
      if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u)
        || !InitializeAcl(&pAcl, 0x1000u, 2u)
        || !SetSecurityDescriptorOwner(pSecurityDescriptor, a1, 0) )
      {
        goto LABEL_32;
      }
      CopySid(0x80u, pDestinationSid, a1);
      if ( InitializeSid(Sid, &pIdentifierAuthority, 2u) )
      {
        *GetSidSubAuthority(Sid, 0) = 32;
        *GetSidSubAuthority(Sid, 1u) = 544;
      }
      else
      {
        GetLastError();
      }
      if ( InitializeSid(pSid, &pIdentifierAuthority, 1u) )
        *GetSidSubAuthority(pSid, 0) = 18;
      else
        GetLastError();
      dwBufferLength = 0;
      v11 = 0;
      do
      {
        v12 = &pDestinationSid[128 * v11];
        pAceList = 768;
        LengthSid = GetLengthSid(v12);
        v30 = 0x10000000;
        v29 = LengthSid + 8;
        if ( !CopySid(0x7Cu, v31, v12) || !AddAce(&pAcl, 2u, 0xFFFFFFFF, &pAceList, v29) )
          GetLastError();
        v11 = dwBufferLength + 1;
        dwBufferLength = v11;
      }
      while ( (unsigned int)v11 < 3 );
      v14 = SetSecurityDescriptorDacl(pSecurityDescriptor, 1, &pAcl, 0);
      v5 = Source;
      if ( v14
        && (dwBufferLength = 0x2000,
            MakeSelfRelativeSD(pSecurityDescriptor, pSelfRelativeSecurityDescriptor, &dwBufferLength))
        && (RegSetKeySecurity(hKey, 4u, pSelfRelativeSecurityDescriptor),
            dwBufferLength = 260,
            cchReferencedDomainName = 260,
            LookupAccountSidW(0, a1, Name, &dwBufferLength, ReferencedDomainName, &cchReferencedDomainName, &peUse)) )
      {
        v15 = -1;
        do
          ++v15;
        while ( ReferencedDomainName[v15] );
        wcsncat_s(ReferencedDomainName, 0x104u, L"\\", 259 - v15);
        v16 = -1;
        do
          ++v16;
        while ( ReferencedDomainName[v16] );
        wcsncat_s(ReferencedDomainName, 0x104u, Name, 259 - v16);
        v17 = -1;
        do
          ++v17;
        while ( ReferencedDomainName[v17] );
        RegSetValueExW(hKey, L"Name", 0, 1u, (const BYTE *)ReferencedDomainName, 2 * v17 + 2);
      }
      else
      {
LABEL_32:
        GetLastError();
      }
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
    goto LABEL_37;
  }
  return result;
}

```

## disassembly

```asm
0x18000cf74  mov     [rsp-8+arg_10], rbx
0x18000cf79  push    rbp
0x18000cf7a  push    rsi
0x18000cf7b  push    rdi
0x18000cf7c  push    r12
0x18000cf7e  push    r13
0x18000cf80  push    r14
0x18000cf82  push    r15
0x18000cf84  lea     rbp, [rsp-3E60h]
0x18000cf8c  mov     eax, 3F60h
0x18000cf91  call    _alloca_probe
0x18000cf96  sub     rsp, rax
0x18000cf99  mov     rax, cs:__security_cookie
0x18000cfa0  xor     rax, rsp
0x18000cfa3  mov     [rbp+3E90h+var_40], rax
0x18000cfaa  mov     rbx, r8
0x18000cfad  mov     [rsp+3F90h+Source], rdx
0x18000cfb2  mov     r13, rdx
0x18000cfb5  mov     r14, rcx
0x18000cfb8  mov     esi, 208h
0x18000cfbd  lea     rcx, [rbp+3E90h+Name]; void *
0x18000cfc4  mov     r8d, esi; Size
0x18000cfc7  xor     edx, edx; Val
0x18000cfc9  mov     r15, r9
0x18000cfcc  call    memset_0
0x18000cfd1  mov     r8d, esi; Size
0x18000cfd4  lea     rcx, [rbp+3E90h+ReferencedDomainName]; void *
0x18000cfdb  xor     edx, edx; Val
0x18000cfdd  call    memset_0
0x18000cfe2  xor     r12d, r12d
0x18000cfe5  mov     word ptr [rbp+3E90h+pIdentifierAuthority.Value+4], 500h
0x18000cfeb  xorps   xmm0, xmm0
0x18000cfee  mov     [rsp+3F90h+dwDisposition], r12d
0x18000cff3  xor     eax, eax
0x18000cff5  mov     [rsp+3F90h+dwBufferLength], r12d
0x18000cffa  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000cffe  mov     [rbp+3E90h+var_3EF8], rax
0x18000d002  mov     r8d, esi; Size
0x18000d005  mov     [rsp+3F90h+cchReferencedDomainName], r12d
0x18000d00a  xor     edx, edx; Val
0x18000d00c  mov     [rsp+3F90h+hKey], rdi
0x18000d011  mov     rcx, r15; void *
0x18000d014  mov     [rsp+3F90h+peUse], r12d
0x18000d019  movups  [rsp+3F90h+pSecurityDescriptor], xmm0
0x18000d01e  mov     dword ptr [rbp+3E90h+pIdentifierAuthority.Value], r12d
0x18000d022  movups  [rbp+3E90h+var_3F08], xmm0
0x18000d026  call    memset_0
0x18000d02b  cmp     rbx, 0FFFFFFFF80000002h
0x18000d032  jnz     loc_18000D3D5
0x18000d038  test    r14, r14
0x18000d03b  jnz     short loc_18000D05E
0x18000d03d  call    cs:__imp_GetCurrentProcess
0x18000d043  lea     rdx, [rbp+3E90h+var_3CE0]
0x18000d04a  call    DaGetProcessSid
0x18000d04f  test    eax, eax
0x18000d051  jnz     loc_18000D447
0x18000d057  lea     r14, [rbp+3E90h+var_3CE0]
0x18000d05e  mov     r8d, 400h; BufferCount
0x18000d064  lea     rdx, [rbp+3E90h+Buffer]; Buffer
0x18000d06b  mov     rcx, r14; pSid
0x18000d06e  call    DaConvertSidToString
0x18000d073  test    eax, eax
0x18000d075  jnz     loc_18000D447
0x18000d07b  mov     r12d, 103h
0x18000d081  lea     rax, [rbp+3E90h+Buffer]
0x18000d088  lea     r9, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000d08f  mov     qword ptr [rsp+3F90h+dwOptions], rax
0x18000d094  mov     r8d, r12d; MaxCount
0x18000d097  mov     rcx, r15; Buffer
0x18000d09a  lea     esi, [r12+1]
0x18000d09f  mov     edx, esi; BufferCount
0x18000d0a1  call    cs:__imp__snwprintf_s
0x18000d0a7  lea     rax, [rsp+3F90h+dwDisposition]
0x18000d0ac  xor     ebx, ebx
0x18000d0ae  mov     [rsp+3F90h+lpdwDisposition], rax; lpdwDisposition
0x18000d0b3  xor     r9d, r9d; lpClass
0x18000d0b6  lea     rax, [rsp+3F90h+hKey]
0x18000d0bb  xor     r8d, r8d; Reserved
0x18000d0be  mov     [rsp+3F90h+phkResult], rax; phkResult
0x18000d0c3  mov     rdx, r15; lpSubKey
0x18000d0c6  mov     [rsp+3F90h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000d0cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000d0d2  mov     [rsp+3F90h+samDesired], 0F003Fh; samDesired
0x18000d0da  mov     [rsp+3F90h+dwOptions], ebx; dwOptions
0x18000d0de  call    cs:__imp_RegCreateKeyExW
0x18000d0e4  test    eax, eax
0x18000d0e6  jnz     loc_18000D3BB
0x18000d0ec  cmp     [rsp+3F90h+dwDisposition], 1
0x18000d0f1  jnz     loc_18000D3C0
0x18000d0f7  lea     edx, [rbx+1]; dwRevision
0x18000d0fa  lea     rcx, [rsp+3F90h+pSecurityDescriptor]; pSecurityDescriptor
0x18000d0ff  call    cs:__imp_InitializeSecurityDescriptor
0x18000d105  test    eax, eax
0x18000d107  jz      loc_18000D3B3
0x18000d10d  mov     edx, 1000h; nAclLength
0x18000d112  lea     r8d, [rbx+2]; dwAclRevision
0x18000d116  lea     rcx, [rbp+3E90h+pAcl]; pAcl
0x18000d11d  call    cs:__imp_InitializeAcl
0x18000d123  test    eax, eax
0x18000d125  jz      loc_18000D3B3
0x18000d12b  xor     r8d, r8d; bOwnerDefaulted
0x18000d12e  lea     rcx, [rsp+3F90h+pSecurityDescriptor]; pSecurityDescriptor
0x18000d133  mov     rdx, r14; pOwner
0x18000d136  call    cs:__imp_SetSecurityDescriptorOwner
0x18000d13c  test    eax, eax
0x18000d13e  jz      loc_18000D3B3
0x18000d144  mov     r8, r14; pSourceSid
0x18000d147  lea     rdx, [rbp+3E90h+pDestinationSid]; pDestinationSid
0x18000d14b  mov     ecx, 80h; nDestinationSidLength
0x18000d150  call    cs:__imp_CopySid
0x18000d156  mov     r8b, 2; nSubAuthorityCount
0x18000d159  lea     rdx, [rbp+3E90h+pIdentifierAuthority]; pIdentifierAuthority
0x18000d15d  lea     rcx, [rbp+3E90h+Sid]; Sid
0x18000d164  call    cs:__imp_InitializeSid
0x18000d16a  xor     r13d, r13d
0x18000d16d  test    eax, eax
0x18000d16f  jnz     short loc_18000D179
0x18000d171  call    cs:__imp_GetLastError
0x18000d177  jmp     short loc_18000D1A6
0x18000d179  xor     edx, edx; nSubAuthority
0x18000d17b  lea     rcx, [rbp+3E90h+Sid]; pSid
0x18000d182  call    cs:__imp_GetSidSubAuthority
0x18000d188  mov     edx, 1; nSubAuthority
0x18000d18d  lea     rcx, [rbp+3E90h+Sid]; pSid
0x18000d194  mov     dword ptr [rax], 20h ; ' '
0x18000d19a  call    cs:__imp_GetSidSubAuthority
0x18000d1a0  mov     dword ptr [rax], 220h
0x18000d1a6  mov     r8b, 1; nSubAuthorityCount
0x18000d1a9  lea     rdx, [rbp+3E90h+pIdentifierAuthority]; pIdentifierAuthority
0x18000d1ad  lea     rcx, [rbp+3E90h+pSid]; Sid
0x18000d1b4  call    cs:__imp_InitializeSid
0x18000d1ba  test    eax, eax
0x18000d1bc  jnz     short loc_18000D1C6
0x18000d1be  call    cs:__imp_GetLastError
0x18000d1c4  jmp     short loc_18000D1DB
0x18000d1c6  xor     edx, edx; nSubAuthority
0x18000d1c8  lea     rcx, [rbp+3E90h+pSid]; pSid
0x18000d1cf  call    cs:__imp_GetSidSubAuthority
0x18000d1d5  mov     dword ptr [rax], 12h
0x18000d1db  mov     [rsp+3F90h+dwBufferLength], r13d
0x18000d1e0  mov     eax, r13d
0x18000d1e3  shl     rax, 7
0x18000d1e7  lea     rbx, [rbp+3E90h+pDestinationSid]
0x18000d1eb  add     rbx, rax
0x18000d1ee  mov     [rbp+3E90h+pAceList], 300h
0x18000d1f4  mov     rcx, rbx; pSid
0x18000d1f7  call    cs:__imp_GetLengthSid
0x18000d1fd  mov     r8, rbx; pSourceSid
0x18000d200  mov     [rbp+3E90h+var_3EDC], 10000000h
0x18000d207  add     ax, 8
0x18000d20b  lea     rdx, [rbp+3E90h+var_3ED8]; pDestinationSid
0x18000d20f  mov     ecx, 7Ch ; '|'; nDestinationSidLength
0x18000d214  mov     [rbp+3E90h+var_3EDE], ax
0x18000d218  call    cs:__imp_CopySid
0x18000d21e  test    eax, eax
0x18000d220  jz      short loc_18000D248
0x18000d222  movzx   eax, [rbp+3E90h+var_3EDE]
0x18000d226  lea     r9, [rbp+3E90h+pAceList]; pAceList
0x18000d22a  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18000d22e  mov     [rsp+3F90h+dwOptions], eax; nAceListLength
0x18000d232  mov     edx, 2; dwAceRevision
0x18000d237  lea     rcx, [rbp+3E90h+pAcl]; pAcl
0x18000d23e  call    cs:__imp_AddAce
0x18000d244  test    eax, eax
0x18000d246  jnz     short loc_18000D24E
0x18000d248  call    cs:__imp_GetLastError
0x18000d24e  mov     eax, [rsp+3F90h+dwBufferLength]
0x18000d252  inc     eax
0x18000d254  mov     [rsp+3F90h+dwBufferLength], eax
0x18000d258  cmp     eax, 3
0x18000d25b  jb      short loc_18000D1E3
0x18000d25d  xor     r9d, r9d; bDaclDefaulted
0x18000d260  lea     r8, [rbp+3E90h+pAcl]; pDacl
0x18000d267  lea     rcx, [rsp+3F90h+pSecurityDescriptor]; pSecurityDescriptor
0x18000d26c  lea     edx, [r9+1]; bDaclPresent
0x18000d270  call    cs:__imp_SetSecurityDescriptorDacl
0x18000d276  mov     r13, [rsp+3F90h+Source]
0x18000d27b  test    eax, eax
0x18000d27d  jz      loc_18000D3B3
0x18000d283  lea     r8, [rsp+3F90h+dwBufferLength]; lpdwBufferLength
0x18000d288  mov     [rsp+3F90h+dwBufferLength], 2000h
0x18000d290  lea     rdx, [rbp+3E90h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18000d297  lea     rcx, [rsp+3F90h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18000d29c  call    cs:__imp_MakeSelfRelativeSD
0x18000d2a2  xor     ebx, ebx
0x18000d2a4  test    eax, eax
0x18000d2a6  jz      loc_18000D3B3
0x18000d2ac  mov     rcx, [rsp+3F90h+hKey]; hKey
0x18000d2b1  lea     r8, [rbp+3E90h+pSelfRelativeSecurityDescriptor]; pSecurityDescriptor
0x18000d2b8  lea     edx, [rbx+4]; SecurityInformation
0x18000d2bb  call    cs:__imp_RegSetKeySecurity
0x18000d2c1  lea     rax, [rsp+3F90h+peUse]
0x18000d2c6  mov     [rsp+3F90h+dwBufferLength], esi
0x18000d2ca  mov     [rsp+3F90h+lpSecurityAttributes], rax; peUse
0x18000d2cf  lea     r9, [rsp+3F90h+dwBufferLength]; cchName
0x18000d2d4  lea     rax, [rsp+3F90h+cchReferencedDomainName]
0x18000d2d9  mov     [rsp+3F90h+cchReferencedDomainName], esi
0x18000d2dd  mov     qword ptr [rsp+3F90h+samDesired], rax; cchReferencedDomainName
0x18000d2e2  lea     r8, [rbp+3E90h+Name]; Name
0x18000d2e9  lea     rax, [rbp+3E90h+ReferencedDomainName]
0x18000d2f0  mov     rdx, r14; Sid
0x18000d2f3  xor     ecx, ecx; lpSystemName
0x18000d2f5  mov     qword ptr [rsp+3F90h+dwOptions], rax; ReferencedDomainName
0x18000d2fa  call    cs:__imp_LookupAccountSidW
0x18000d300  test    eax, eax
0x18000d302  jz      loc_18000D3B3
0x18000d308  lea     rcx, [rbp+3E90h+ReferencedDomainName]
0x18000d30f  mov     rax, rdi
0x18000d312  inc     rax
0x18000d315  cmp     [rcx+rax*2], bx
0x18000d319  jnz     short loc_18000D312
0x18000d31b  mov     r9, r12
0x18000d31e  lea     r8, SubStr; "\\"
0x18000d325  sub     r9, rax; MaxCount
0x18000d328  lea     rcx, [rbp+3E90h+ReferencedDomainName]; Destination
0x18000d32f  mov     rdx, rsi; SizeInWords
0x18000d332  call    cs:__imp_wcsncat_s
0x18000d338  lea     rcx, [rbp+3E90h+ReferencedDomainName]
0x18000d33f  mov     rax, rdi
0x18000d342  inc     rax
0x18000d345  cmp     [rcx+rax*2], bx
0x18000d349  jnz     short loc_18000D342
0x18000d34b  sub     r12, rax
0x18000d34e  lea     r8, [rbp+3E90h+Name]; Source
0x18000d355  mov     r9, r12; MaxCount
0x18000d358  lea     rcx, [rbp+3E90h+ReferencedDomainName]; Destination
0x18000d35f  mov     rdx, rsi; SizeInWords
0x18000d362  call    cs:__imp_wcsncat_s
0x18000d368  lea     rcx, [rbp+3E90h+ReferencedDomainName]
0x18000d36f  mov     rax, rdi
0x18000d372  xor     r12d, r12d
0x18000d375  inc     rax
0x18000d378  cmp     [rcx+rax*2], r12w
0x18000d37d  jnz     short loc_18000D375
0x18000d37f  mov     rcx, [rsp+3F90h+hKey]; hKey
0x18000d384  lea     eax, ds:2[rax*2]
0x18000d38b  mov     [rsp+3F90h+samDesired], eax; cbData
0x18000d38f  lea     rdx, aName; "Name"
0x18000d396  lea     rax, [rbp+3E90h+ReferencedDomainName]
0x18000d39d  mov     r9d, 1; dwType
0x18000d3a3  xor     r8d, r8d; Reserved
0x18000d3a6  mov     qword ptr [rsp+3F90h+dwOptions], rax; lpData
0x18000d3ab  call    cs:__imp_RegSetValueExW
0x18000d3b1  jmp     short loc_18000D3C3
0x18000d3b3  call    cs:__imp_GetLastError
0x18000d3b9  jmp     short loc_18000D3C0
0x18000d3bb  mov     [rsp+3F90h+hKey], rdi
0x18000d3c0  xor     r12d, r12d
0x18000d3c3  mov     rcx, [rsp+3F90h+hKey]; hKey
0x18000d3c8  cmp     rcx, rdi
0x18000d3cb  jz      short loc_18000D3EC
0x18000d3cd  call    cs:__imp_RegCloseKey
0x18000d3d3  jmp     short loc_18000D3EC
0x18000d3d5  mov     esi, 104h
0x18000d3da  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000d3e1  mov     edx, esi; SizeInWords
0x18000d3e3  mov     rcx, r15; Destination
0x18000d3e6  call    cs:__imp_wcscpy_s
0x18000d3ec  test    r13, r13
0x18000d3ef  jz      short loc_18000D444
0x18000d3f1  cmp     word ptr [r13+0], 5Ch ; '\'
0x18000d3f7  jz      short loc_18000D423
0x18000d3f9  mov     rcx, rdi
0x18000d3fc  inc     rcx
0x18000d3ff  cmp     [r15+rcx*2], r12w
0x18000d404  jnz     short loc_18000D3FC
0x18000d406  mov     eax, esi
0x18000d408  lea     r8, SubStr; "\\"
0x18000d40f  sub     eax, ecx
0x18000d411  mov     edx, eax; SizeInWords
0x18000d413  lea     r9d, [rax-1]; MaxCount
0x18000d417  mov     eax, ecx
0x18000d419  lea     rcx, [r15+rax*2]; Destination
0x18000d41d  call    cs:__imp_wcsncpy_s
0x18000d423  inc     rdi
0x18000d426  cmp     [r15+rdi*2], r12w
0x18000d42b  jnz     short loc_18000D423
0x18000d42d  sub     esi, edi
0x18000d42f  mov     eax, edi
0x18000d431  mov     edx, esi; SizeInWords
0x18000d433  mov     r8, r13; Source
0x18000d436  lea     r9d, [rsi-1]; MaxCount
0x18000d43a  lea     rcx, [r15+rax*2]; Destination
0x18000d43e  call    cs:__imp_wcsncpy_s
0x18000d444  mov     eax, r12d
0x18000d447  mov     rcx, [rbp+3E90h+var_40]
0x18000d44e  xor     rcx, rsp; StackCookie
0x18000d451  call    __security_check_cookie
0x18000d456  mov     rbx, [rsp+3F90h+arg_10]
0x18000d45e  add     rsp, 3F60h
0x18000d465  pop     r15
0x18000d467  pop     r14
0x18000d469  pop     r13
0x18000d46b  pop     r12
0x18000d46d  pop     rdi
0x18000d46e  pop     rsi
0x18000d46f  pop     rbp
0x18000d470  retn
```
