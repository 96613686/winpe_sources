# DaBuildRegistryPath

- ea: `0x18000da44`
- end: `0x18000dffa`
- name: `DaBuildRegistryPath`
- size: `1462`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000c738`
- `0x18000d4e0`
- `0x18000d710`
- `0x180010bec`

## callees

- `0x18000da44`
- `0x18000e000`
- `0x18000e198`
- `0x180012e32`
- `0x180012e70`
- `0x180012f00`

## import_xrefs

- `msvcrt!wcsncat_s` at `0x18000de8a`
- `msvcrt!wcsncat_s` at `0x18000dec0`
- `msvcrt!wcsncat_s` at `0x18000de8a`
- `msvcrt!wcsncat_s` at `0x18000dec0`
- `msvcrt!_snwprintf_s` at `0x18000db77`
- `msvcrt!_snwprintf_s` at `0x18000db77`
- `msvcrt!wcscpy_s` at `0x18000df5c`
- `msvcrt!wcscpy_s` at `0x18000df5c`
- `msvcrt!wcsncpy_s` at `0x18000df99`
- `msvcrt!wcsncpy_s` at `0x18000dfc0`
- `msvcrt!wcsncpy_s` at `0x18000df99`
- `msvcrt!wcsncpy_s` at `0x18000dfc0`
- `KERNEL32!GetCurrentProcess` at `0x18000db0d`
- `KERNEL32!GetCurrentProcess` at `0x18000db0d`
- `KERNEL32!GetLastError` at `0x18000dc71`
- `KERNEL32!GetLastError` at `0x18000dcd6`
- `KERNEL32!GetLastError` at `0x18000dd7e`
- `KERNEL32!GetLastError` at `0x18000df1d`
- `KERNEL32!GetLastError` at `0x18000dc71`
- `KERNEL32!GetLastError` at `0x18000dcd6`
- `KERNEL32!GetLastError` at `0x18000dd7e`
- `KERNEL32!GetLastError` at `0x18000df1d`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000dde2`
- `ADVAPI32!MakeSelfRelativeSD` at `0x18000dde2`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000ddb0`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000ddb0`
- `ADVAPI32!AddAce` at `0x18000dd6e`
- `ADVAPI32!AddAce` at `0x18000dd6e`
- `ADVAPI32!GetLengthSid` at `0x18000dd1b`
- `ADVAPI32!GetLengthSid` at `0x18000dd1b`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18000dc24`
- `ADVAPI32!SetSecurityDescriptorOwner` at `0x18000dc24`
- `ADVAPI32!InitializeAcl` at `0x18000dc05`
- `ADVAPI32!InitializeAcl` at `0x18000dc05`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000dbe1`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18000dbe1`
- `ADVAPI32!CopySid` at `0x18000dc44`
- `ADVAPI32!CopySid` at `0x18000dd42`
- `ADVAPI32!CopySid` at `0x18000dc44`
- `ADVAPI32!CopySid` at `0x18000dd42`
- `ADVAPI32!RegCreateKeyExW` at `0x18000dbba`
- `ADVAPI32!RegCreateKeyExW` at `0x18000dbba`
- `ADVAPI32!GetSidSubAuthority` at `0x18000dc88`
- `ADVAPI32!GetSidSubAuthority` at `0x18000dca6`
- `ADVAPI32!GetSidSubAuthority` at `0x18000dced`
- `ADVAPI32!GetSidSubAuthority` at `0x18000dc88`
- `ADVAPI32!GetSidSubAuthority` at `0x18000dca6`
- `ADVAPI32!GetSidSubAuthority` at `0x18000dced`
- `ADVAPI32!InitializeSid` at `0x18000dc5e`
- `ADVAPI32!InitializeSid` at `0x18000dcc6`
- `ADVAPI32!InitializeSid` at `0x18000dc5e`
- `ADVAPI32!InitializeSid` at `0x18000dcc6`
- `ADVAPI32!LookupAccountSidW` at `0x18000de4c`
- `ADVAPI32!LookupAccountSidW` at `0x18000de4c`
- `ADVAPI32!RegSetValueExW` at `0x18000df0f`
- `ADVAPI32!RegSetValueExW` at `0x18000df0f`
- `ADVAPI32!RegCloseKey` at `0x18000df3d`
- `ADVAPI32!RegCloseKey` at `0x18000df3d`
- `ADVAPI32!RegSetKeySecurity` at `0x18000de07`
- `ADVAPI32!RegSetKeySecurity` at `0x18000de07`

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
0x18000da44  mov     [rsp-8+arg_10], rbx
0x18000da49  push    rbp
0x18000da4a  push    rsi
0x18000da4b  push    rdi
0x18000da4c  push    r12
0x18000da4e  push    r13
0x18000da50  push    r14
0x18000da52  push    r15
0x18000da54  lea     rbp, [rsp-3E60h]
0x18000da5c  mov     eax, 3F60h
0x18000da61  call    _alloca_probe
0x18000da66  sub     rsp, rax
0x18000da69  mov     rax, cs:__security_cookie
0x18000da70  xor     rax, rsp
0x18000da73  mov     [rbp+3E90h+var_40], rax
0x18000da7a  mov     rbx, r8
0x18000da7d  mov     [rsp+3F90h+Source], rdx
0x18000da82  mov     r13, rdx
0x18000da85  mov     r14, rcx
0x18000da88  mov     esi, 208h
0x18000da8d  lea     rcx, [rbp+3E90h+Name]; void *
0x18000da94  mov     r8d, esi; Size
0x18000da97  xor     edx, edx; Val
0x18000da99  mov     r15, r9
0x18000da9c  call    memset_0
0x18000daa1  mov     r8d, esi; Size
0x18000daa4  lea     rcx, [rbp+3E90h+ReferencedDomainName]; void *
0x18000daab  xor     edx, edx; Val
0x18000daad  call    memset_0
0x18000dab2  xor     r12d, r12d
0x18000dab5  mov     word ptr [rbp+3E90h+pIdentifierAuthority.Value+4], 500h
0x18000dabb  xorps   xmm0, xmm0
0x18000dabe  mov     [rsp+3F90h+dwDisposition], r12d
0x18000dac3  xor     eax, eax
0x18000dac5  mov     [rsp+3F90h+dwBufferLength], r12d
0x18000daca  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000dace  mov     [rbp+3E90h+var_3EF8], rax
0x18000dad2  mov     r8d, esi; Size
0x18000dad5  mov     [rsp+3F90h+cchReferencedDomainName], r12d
0x18000dada  xor     edx, edx; Val
0x18000dadc  mov     [rsp+3F90h+hKey], rdi
0x18000dae1  mov     rcx, r15; void *
0x18000dae4  mov     [rsp+3F90h+peUse], r12d
0x18000dae9  movups  [rsp+3F90h+pSecurityDescriptor], xmm0
0x18000daee  mov     dword ptr [rbp+3E90h+pIdentifierAuthority.Value], r12d
0x18000daf2  movups  [rbp+3E90h+var_3F08], xmm0
0x18000daf6  call    memset_0
0x18000dafb  cmp     rbx, 0FFFFFFFF80000002h
0x18000db02  jnz     loc_18000DF4B
0x18000db08  test    r14, r14
0x18000db0b  jnz     short loc_18000DB34
0x18000db0d  call    cs:__imp_GetCurrentProcess
0x18000db14  nop     dword ptr [rax+rax+00h]
0x18000db19  lea     rdx, [rbp+3E90h+var_3CE0]
0x18000db20  call    DaGetProcessSid
0x18000db25  test    eax, eax
0x18000db27  jnz     loc_18000DFCF
0x18000db2d  lea     r14, [rbp+3E90h+var_3CE0]
0x18000db34  mov     r8d, 400h; BufferCount
0x18000db3a  lea     rdx, [rbp+3E90h+Buffer]; Buffer
0x18000db41  mov     rcx, r14; pSid
0x18000db44  call    DaConvertSidToString
0x18000db49  test    eax, eax
0x18000db4b  jnz     loc_18000DFCF
0x18000db51  mov     r12d, 103h
0x18000db57  lea     rax, [rbp+3E90h+Buffer]
0x18000db5e  lea     r9, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000db65  mov     qword ptr [rsp+3F90h+dwOptions], rax
0x18000db6a  mov     r8d, r12d; MaxCount
0x18000db6d  mov     rcx, r15; Buffer
0x18000db70  lea     esi, [r12+1]
0x18000db75  mov     edx, esi; BufferCount
0x18000db77  call    cs:__imp__snwprintf_s
0x18000db7e  nop     dword ptr [rax+rax+00h]
0x18000db83  lea     rax, [rsp+3F90h+dwDisposition]
0x18000db88  xor     ebx, ebx
0x18000db8a  mov     [rsp+3F90h+lpdwDisposition], rax; lpdwDisposition
0x18000db8f  xor     r9d, r9d; lpClass
0x18000db92  lea     rax, [rsp+3F90h+hKey]
0x18000db97  xor     r8d, r8d; Reserved
0x18000db9a  mov     [rsp+3F90h+phkResult], rax; phkResult
0x18000db9f  mov     rdx, r15; lpSubKey
0x18000dba2  mov     [rsp+3F90h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000dba7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000dbae  mov     [rsp+3F90h+samDesired], 0F003Fh; samDesired
0x18000dbb6  mov     [rsp+3F90h+dwOptions], ebx; dwOptions
0x18000dbba  call    cs:__imp_RegCreateKeyExW
0x18000dbc1  nop     dword ptr [rax+rax+00h]
0x18000dbc6  test    eax, eax
0x18000dbc8  jnz     loc_18000DF2B
0x18000dbce  cmp     [rsp+3F90h+dwDisposition], 1
0x18000dbd3  jnz     loc_18000DF30
0x18000dbd9  lea     edx, [rbx+1]; dwRevision
0x18000dbdc  lea     rcx, [rsp+3F90h+pSecurityDescriptor]; pSecurityDescriptor
0x18000dbe1  call    cs:__imp_InitializeSecurityDescriptor
0x18000dbe8  nop     dword ptr [rax+rax+00h]
0x18000dbed  test    eax, eax
0x18000dbef  jz      loc_18000DF1D
0x18000dbf5  mov     edx, 1000h; nAclLength
0x18000dbfa  lea     r8d, [rbx+2]; dwAclRevision
0x18000dbfe  lea     rcx, [rbp+3E90h+pAcl]; pAcl
0x18000dc05  call    cs:__imp_InitializeAcl
0x18000dc0c  nop     dword ptr [rax+rax+00h]
0x18000dc11  test    eax, eax
0x18000dc13  jz      loc_18000DF1D
0x18000dc19  xor     r8d, r8d; bOwnerDefaulted
0x18000dc1c  lea     rcx, [rsp+3F90h+pSecurityDescriptor]; pSecurityDescriptor
0x18000dc21  mov     rdx, r14; pOwner
0x18000dc24  call    cs:__imp_SetSecurityDescriptorOwner
0x18000dc2b  nop     dword ptr [rax+rax+00h]
0x18000dc30  test    eax, eax
0x18000dc32  jz      loc_18000DF1D
0x18000dc38  mov     r8, r14; pSourceSid
0x18000dc3b  lea     rdx, [rbp+3E90h+pDestinationSid]; pDestinationSid
0x18000dc3f  mov     ecx, 80h; nDestinationSidLength
0x18000dc44  call    cs:__imp_CopySid
0x18000dc4b  nop     dword ptr [rax+rax+00h]
0x18000dc50  mov     r8b, 2; nSubAuthorityCount
0x18000dc53  lea     rdx, [rbp+3E90h+pIdentifierAuthority]; pIdentifierAuthority
0x18000dc57  lea     rcx, [rbp+3E90h+Sid]; Sid
0x18000dc5e  call    cs:__imp_InitializeSid
0x18000dc65  nop     dword ptr [rax+rax+00h]
0x18000dc6a  xor     r13d, r13d
0x18000dc6d  test    eax, eax
0x18000dc6f  jnz     short loc_18000DC7F
0x18000dc71  call    cs:__imp_GetLastError
0x18000dc78  nop     dword ptr [rax+rax+00h]
0x18000dc7d  jmp     short loc_18000DCB8
0x18000dc7f  xor     edx, edx; nSubAuthority
0x18000dc81  lea     rcx, [rbp+3E90h+Sid]; pSid
0x18000dc88  call    cs:__imp_GetSidSubAuthority
0x18000dc8f  nop     dword ptr [rax+rax+00h]
0x18000dc94  mov     edx, 1; nSubAuthority
0x18000dc99  lea     rcx, [rbp+3E90h+Sid]; pSid
0x18000dca0  mov     dword ptr [rax], 20h ; ' '
0x18000dca6  call    cs:__imp_GetSidSubAuthority
0x18000dcad  nop     dword ptr [rax+rax+00h]
0x18000dcb2  mov     dword ptr [rax], 220h
0x18000dcb8  mov     r8b, 1; nSubAuthorityCount
0x18000dcbb  lea     rdx, [rbp+3E90h+pIdentifierAuthority]; pIdentifierAuthority
0x18000dcbf  lea     rcx, [rbp+3E90h+pSid]; Sid
0x18000dcc6  call    cs:__imp_InitializeSid
0x18000dccd  nop     dword ptr [rax+rax+00h]
0x18000dcd2  test    eax, eax
0x18000dcd4  jnz     short loc_18000DCE4
0x18000dcd6  call    cs:__imp_GetLastError
0x18000dcdd  nop     dword ptr [rax+rax+00h]
0x18000dce2  jmp     short loc_18000DCFF
0x18000dce4  xor     edx, edx; nSubAuthority
0x18000dce6  lea     rcx, [rbp+3E90h+pSid]; pSid
0x18000dced  call    cs:__imp_GetSidSubAuthority
0x18000dcf4  nop     dword ptr [rax+rax+00h]
0x18000dcf9  mov     dword ptr [rax], 12h
0x18000dcff  mov     [rsp+3F90h+dwBufferLength], r13d
0x18000dd04  mov     eax, r13d
0x18000dd07  shl     rax, 7
0x18000dd0b  lea     rbx, [rbp+3E90h+pDestinationSid]
0x18000dd0f  add     rbx, rax
0x18000dd12  mov     [rbp+3E90h+pAceList], 300h
0x18000dd18  mov     rcx, rbx; pSid
0x18000dd1b  call    cs:__imp_GetLengthSid
0x18000dd22  nop     dword ptr [rax+rax+00h]
0x18000dd27  mov     r8, rbx; pSourceSid
0x18000dd2a  mov     [rbp+3E90h+var_3EDC], 10000000h
0x18000dd31  add     ax, 8
0x18000dd35  lea     rdx, [rbp+3E90h+var_3ED8]; pDestinationSid
0x18000dd39  mov     ecx, 7Ch ; '|'; nDestinationSidLength
0x18000dd3e  mov     [rbp+3E90h+var_3EDE], ax
0x18000dd42  call    cs:__imp_CopySid
0x18000dd49  nop     dword ptr [rax+rax+00h]
0x18000dd4e  test    eax, eax
0x18000dd50  jz      short loc_18000DD7E
0x18000dd52  movzx   eax, [rbp+3E90h+var_3EDE]
0x18000dd56  lea     r9, [rbp+3E90h+pAceList]; pAceList
0x18000dd5a  or      r8d, 0FFFFFFFFh; dwStartingAceIndex
0x18000dd5e  mov     [rsp+3F90h+dwOptions], eax; nAceListLength
0x18000dd62  mov     edx, 2; dwAceRevision
0x18000dd67  lea     rcx, [rbp+3E90h+pAcl]; pAcl
0x18000dd6e  call    cs:__imp_AddAce
0x18000dd75  nop     dword ptr [rax+rax+00h]
0x18000dd7a  test    eax, eax
0x18000dd7c  jnz     short loc_18000DD8A
0x18000dd7e  call    cs:__imp_GetLastError
0x18000dd85  nop     dword ptr [rax+rax+00h]
0x18000dd8a  mov     eax, [rsp+3F90h+dwBufferLength]
0x18000dd8e  inc     eax
0x18000dd90  mov     [rsp+3F90h+dwBufferLength], eax
0x18000dd94  cmp     eax, 3
0x18000dd97  jb      loc_18000DD07
0x18000dd9d  xor     r9d, r9d; bDaclDefaulted
0x18000dda0  lea     r8, [rbp+3E90h+pAcl]; pDacl
0x18000dda7  lea     rcx, [rsp+3F90h+pSecurityDescriptor]; pSecurityDescriptor
0x18000ddac  lea     edx, [r9+1]; bDaclPresent
0x18000ddb0  call    cs:__imp_SetSecurityDescriptorDacl
0x18000ddb7  nop     dword ptr [rax+rax+00h]
0x18000ddbc  mov     r13, [rsp+3F90h+Source]
0x18000ddc1  test    eax, eax
0x18000ddc3  jz      loc_18000DF1D
0x18000ddc9  lea     r8, [rsp+3F90h+dwBufferLength]; lpdwBufferLength
0x18000ddce  mov     [rsp+3F90h+dwBufferLength], 2000h
0x18000ddd6  lea     rdx, [rbp+3E90h+pSelfRelativeSecurityDescriptor]; pSelfRelativeSecurityDescriptor
0x18000dddd  lea     rcx, [rsp+3F90h+pSecurityDescriptor]; pAbsoluteSecurityDescriptor
0x18000dde2  call    cs:__imp_MakeSelfRelativeSD
0x18000dde9  nop     dword ptr [rax+rax+00h]
0x18000ddee  xor     ebx, ebx
0x18000ddf0  test    eax, eax
0x18000ddf2  jz      loc_18000DF1D
0x18000ddf8  mov     rcx, [rsp+3F90h+hKey]; hKey
0x18000ddfd  lea     r8, [rbp+3E90h+pSelfRelativeSecurityDescriptor]; pSecurityDescriptor
0x18000de04  lea     edx, [rbx+4]; SecurityInformation
0x18000de07  call    cs:__imp_RegSetKeySecurity
0x18000de0e  nop     dword ptr [rax+rax+00h]
0x18000de13  lea     rax, [rsp+3F90h+peUse]
0x18000de18  mov     [rsp+3F90h+dwBufferLength], esi
0x18000de1c  mov     [rsp+3F90h+lpSecurityAttributes], rax; peUse
0x18000de21  lea     r9, [rsp+3F90h+dwBufferLength]; cchName
0x18000de26  lea     rax, [rsp+3F90h+cchReferencedDomainName]
0x18000de2b  mov     [rsp+3F90h+cchReferencedDomainName], esi
0x18000de2f  mov     qword ptr [rsp+3F90h+samDesired], rax; cchReferencedDomainName
0x18000de34  lea     r8, [rbp+3E90h+Name]; Name
0x18000de3b  lea     rax, [rbp+3E90h+ReferencedDomainName]
0x18000de42  mov     rdx, r14; Sid
0x18000de45  xor     ecx, ecx; lpSystemName
0x18000de47  mov     qword ptr [rsp+3F90h+dwOptions], rax; ReferencedDomainName
0x18000de4c  call    cs:__imp_LookupAccountSidW
0x18000de53  nop     dword ptr [rax+rax+00h]
0x18000de58  test    eax, eax
0x18000de5a  jz      loc_18000DF1D
0x18000de60  lea     rcx, [rbp+3E90h+ReferencedDomainName]
0x18000de67  mov     rax, rdi
0x18000de6a  inc     rax
0x18000de6d  cmp     [rcx+rax*2], bx
0x18000de71  jnz     short loc_18000DE6A
0x18000de73  mov     r9, r12
0x18000de76  lea     r8, SubStr; "\\"
0x18000de7d  sub     r9, rax; MaxCount
0x18000de80  lea     rcx, [rbp+3E90h+ReferencedDomainName]; Destination
0x18000de87  mov     rdx, rsi; SizeInWords
0x18000de8a  call    cs:__imp_wcsncat_s
0x18000de91  nop     dword ptr [rax+rax+00h]
0x18000de96  lea     rcx, [rbp+3E90h+ReferencedDomainName]
0x18000de9d  mov     rax, rdi
0x18000dea0  inc     rax
0x18000dea3  cmp     [rcx+rax*2], bx
0x18000dea7  jnz     short loc_18000DEA0
0x18000dea9  sub     r12, rax
0x18000deac  lea     r8, [rbp+3E90h+Name]; Source
0x18000deb3  mov     r9, r12; MaxCount
0x18000deb6  lea     rcx, [rbp+3E90h+ReferencedDomainName]; Destination
0x18000debd  mov     rdx, rsi; SizeInWords
0x18000dec0  call    cs:__imp_wcsncat_s
0x18000dec7  nop     dword ptr [rax+rax+00h]
0x18000decc  lea     rcx, [rbp+3E90h+ReferencedDomainName]
0x18000ded3  mov     rax, rdi
0x18000ded6  xor     r12d, r12d
0x18000ded9  inc     rax
0x18000dedc  cmp     [rcx+rax*2], r12w
0x18000dee1  jnz     short loc_18000DED9
0x18000dee3  mov     rcx, [rsp+3F90h+hKey]; hKey
0x18000dee8  lea     eax, ds:2[rax*2]
0x18000deef  mov     [rsp+3F90h+samDesired], eax; cbData
0x18000def3  lea     rdx, aName; "Name"
0x18000defa  lea     rax, [rbp+3E90h+ReferencedDomainName]
0x18000df01  mov     r9d, 1; dwType
0x18000df07  xor     r8d, r8d; Reserved
0x18000df0a  mov     qword ptr [rsp+3F90h+dwOptions], rax; lpData
0x18000df0f  call    cs:__imp_RegSetValueExW
0x18000df16  nop     dword ptr [rax+rax+00h]
0x18000df1b  jmp     short loc_18000DF33
0x18000df1d  call    cs:__imp_GetLastError
0x18000df24  nop     dword ptr [rax+rax+00h]
0x18000df29  jmp     short loc_18000DF30
0x18000df2b  mov     [rsp+3F90h+hKey], rdi
0x18000df30  xor     r12d, r12d
0x18000df33  mov     rcx, [rsp+3F90h+hKey]; hKey
0x18000df38  cmp     rcx, rdi
0x18000df3b  jz      short loc_18000DF68
0x18000df3d  call    cs:__imp_RegCloseKey
0x18000df44  nop     dword ptr [rax+rax+00h]
0x18000df49  jmp     short loc_18000DF68
0x18000df4b  mov     esi, 104h
0x18000df50  lea     r8, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\ClientForNFS\\Curr"...
0x18000df57  mov     edx, esi; SizeInWords
0x18000df59  mov     rcx, r15; Destination
0x18000df5c  call    cs:__imp_wcscpy_s
0x18000df63  nop     dword ptr [rax+rax+00h]
0x18000df68  test    r13, r13
0x18000df6b  jz      short loc_18000DFCC
0x18000df6d  cmp     word ptr [r13+0], 5Ch ; '\'
0x18000df73  jz      short loc_18000DFA5
0x18000df75  mov     rcx, rdi
0x18000df78  inc     rcx
0x18000df7b  cmp     [r15+rcx*2], r12w
0x18000df80  jnz     short loc_18000DF78
0x18000df82  mov     eax, esi
0x18000df84  lea     r8, SubStr; "\\"
0x18000df8b  sub     eax, ecx
0x18000df8d  mov     edx, eax; SizeInWords
0x18000df8f  lea     r9d, [rax-1]; MaxCount
0x18000df93  mov     eax, ecx
  ... truncated ...
```
