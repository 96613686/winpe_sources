# RdCentralDbUtils::DecryptCredsData(ushort *,ushort * *,ushort *)

- ea: `0x18009f6b4`
- end: `0x18009fcf1`
- name: `?DecryptCredsData@RdCentralDbUtils@@CAJPEAGPEAPEAG0@Z`
- size: `1597`
- prototype: `__int64 __fastcall(wchar_t *String1, unsigned __int16 **, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task`

## callers

- `0x18009fd9c`

## callees

- `0x180005665`
- `0x18001ad74`
- `0x18001ec04`
- `0x180077e9c`
- `0x180088e68`
- `0x18009f6b4`
- `0x1800a0f7e`
- `0x1800a0fb0`

## import_xrefs

- `CRYPT32!CryptUnprotectData` at `0x18009facd`
- `CRYPT32!CryptUnprotectData` at `0x18009facd`
- `ADVAPI32!RegQueryValueExW` at `0x18009f80d`
- `ADVAPI32!RegQueryValueExW` at `0x18009f8a7`
- `ADVAPI32!RegQueryValueExW` at `0x18009f9b2`
- `ADVAPI32!RegQueryValueExW` at `0x18009fa49`
- `ADVAPI32!RegQueryValueExW` at `0x18009f80d`
- `ADVAPI32!RegQueryValueExW` at `0x18009f8a7`
- `ADVAPI32!RegQueryValueExW` at `0x18009f9b2`
- `ADVAPI32!RegQueryValueExW` at `0x18009fa49`
- `ADVAPI32!RegOpenKeyExW` at `0x18009f74a`
- `ADVAPI32!RegOpenKeyExW` at `0x18009f74a`
- `ADVAPI32!RegCloseKey` at `0x18009fcb6`
- `ADVAPI32!RegCloseKey` at `0x18009fcb6`
- `OLEAUT32!__imp_SysAllocString` at `0x18009fc41`
- `OLEAUT32!__imp_SysAllocString` at `0x18009fc41`
- `KERNEL32!GetLastError` at `0x18009fadd`
- `KERNEL32!GetLastError` at `0x18009fadd`
- `KERNEL32!LocalAlloc` at `0x18009f913`
- `KERNEL32!LocalAlloc` at `0x18009f913`
- `KERNEL32!LocalFree` at `0x18009fc5a`
- `KERNEL32!LocalFree` at `0x18009fc7d`
- `KERNEL32!LocalFree` at `0x18009fca0`
- `KERNEL32!LocalFree` at `0x18009fc5a`
- `KERNEL32!LocalFree` at `0x18009fc7d`
- `KERNEL32!LocalFree` at `0x18009fca0`

## string_xrefs

- `0x18009f73c`: `System\CurrentControlSet\Services\Tssdis\Parameters\Secrets`
- `0x18009f7a7`: `RegOpenKeyEx failed`

## pseudocode

```c
__int64 __fastcall RdCentralDbUtils::DecryptCredsData(wchar_t *String1, unsigned __int16 **a2, unsigned __int16 *a3)
{
  LSTATUS v5; // eax
  LSTATUS v6; // edi
  signed int v7; // ebx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  unsigned int v11; // eax
  signed int LastError; // eax
  signed __int64 v13; // rdx
  int v14; // eax
  int v15; // ecx
  PVOID *v16; // rax
  unsigned int v17; // eax
  unsigned int v18; // eax
  LPDWORD lpcbData; // [rsp+30h] [rbp-D8h]
  DWORD Type; // [rsp+48h] [rbp-C0h] BYREF
  DATA_BLOB cbData; // [rsp+50h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A8h] BYREF
  DATA_BLOB pDataOut; // [rsp+68h] [rbp-A0h] BYREF
  LPWSTR ppszDataDescr; // [rsp+78h] [rbp-90h] BYREF
  OLECHAR psz[264]; // [rsp+88h] [rbp-80h] BYREF

  pDataOut.cbData = 0;
  pDataOut.pbData = 0;
  cbData.cbData = 0;
  cbData.pbData = 0;
  ppszDataDescr = 0;
  hKey = 0;
  Type = 0;
  *(&pDataOut.cbData + 1) = 0;
  *(&cbData.cbData + 1) = 0;
  memset_0(psz, 0, 0x208u);
  v5 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"System\\CurrentControlSet\\Services\\Tssdis\\Parameters\\Secrets",
         0,
         0x20019u,
         &hKey);
  v6 = v5;
  if ( !v5 )
  {
    if ( !wcscmp_0(String1, L"PrimaryConnectionString") )
      v6 = RegQueryValueExW(hKey, L"PrimarySecret", 0, &Type, 0, &cbData.cbData);
    if ( v6 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      else
        v7 = v6;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 12;
      goto LABEL_20;
    }
    if ( !wcscmp_0(String1, L"SecondaryConnectionString") )
      v6 = RegQueryValueExW(hKey, L"SecondarySecret", 0, &Type, 0, &cbData.cbData);
    if ( v6 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      else
        v7 = v6;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 13;
      goto LABEL_31;
    }
    cbData.pbData = (BYTE *)LocalAlloc(0x40u, cbData.cbData);
    if ( !cbData.pbData )
    {
      v7 = -2147467261;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v11 = RdpWppGetCurrentThreadActivityIdPrefix();
        LODWORD(lpcbData) = -2147467261;
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
          v11,
          (__int64)"memory allocation failed secondary failed!",
          lpcbData);
      }
      goto LABEL_85;
    }
    if ( !wcscmp_0(String1, L"PrimaryConnectionString") )
      v6 = RegQueryValueExW(hKey, L"PrimarySecret", 0, &Type, cbData.pbData, &cbData.cbData);
    if ( v6 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      else
        v7 = v6;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 15;
LABEL_20:
      v10 = "RegQueryValueEx primary failed!";
      goto LABEL_9;
    }
    if ( !wcscmp_0(String1, L"SecondaryConnectionString") )
      v6 = RegQueryValueExW(hKey, L"SecondarySecret", 0, &Type, cbData.pbData, &cbData.cbData);
    if ( v6 )
    {
      if ( v6 > 0 )
        v7 = (unsigned __int16)v6 | 0x80070000;
      else
        v7 = v6;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_85;
      }
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 16;
LABEL_31:
      v10 = "RegQueryValueEx secondary failed!";
      goto LABEL_9;
    }
    if ( !CryptUnprotectData(&cbData, &ppszDataDescr, 0, 0, 0, 5u, &pDataOut) )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( v7 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 17;
          v10 = "CryptUnprotectData failed 0x%x";
          goto LABEL_9;
        }
        goto LABEL_85;
      }
    }
    v13 = (char *)ppszDataDescr - (char *)String1;
    do
    {
      v14 = *(wchar_t *)((char *)String1 + v13);
      v15 = *String1 - v14;
      if ( v15 )
        break;
      ++String1;
    }
    while ( v14 );
    if ( v15 )
    {
      v16 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
      {
LABEL_74:
        if ( pDataOut.cbData >> 1 )
        {
          v7 = StringCchCopyNW(psz, 0x104u, (const unsigned __int16 *)pDataOut.pbData, pDataOut.cbData >> 1);
          if ( v7 >= 0 )
          {
            *a2 = SysAllocString(psz);
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v9 = 20;
            v10 = "populating creds failed";
            goto LABEL_9;
          }
        }
        else
        {
          v7 = -2147467259;
          if ( v16 != &WPP_GLOBAL_Control && (*((_BYTE *)v16 + 28) & 1) != 0 && *((_BYTE *)v16 + 25) >= 2u )
          {
            v18 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids, v18);
          }
        }
        goto LABEL_85;
      }
      v17 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids, v17);
    }
    v16 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_74;
  }
  if ( v5 > 0 )
    v7 = (unsigned __int16)v5 | 0x80070000;
  else
    v7 = v5;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v9 = 11;
    v10 = "RegOpenKeyEx failed";
LABEL_9:
    LODWORD(lpcbData) = v7;
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      (unsigned int)WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v10,
      lpcbData);
  }
LABEL_85:
  if ( ppszDataDescr )
    LocalFree(ppszDataDescr);
  if ( pDataOut.pbData )
  {
    memset(pDataOut.pbData, 0, pDataOut.cbData);
    LocalFree(pDataOut.pbData);
  }
  if ( cbData.pbData )
  {
    memset(cbData.pbData, 0, cbData.cbData);
    LocalFree(cbData.pbData);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18009f6b4  mov     rax, rsp
0x18009f6b7  mov     [rax+8], rbx
0x18009f6bb  mov     [rax+18h], rsi
0x18009f6bf  mov     [rax+20h], rdi
0x18009f6c3  push    rbp
0x18009f6c4  push    r12
0x18009f6c6  push    r14
0x18009f6c8  lea     rbp, [rax-1B8h]
0x18009f6cf  sub     rsp, 2A0h
0x18009f6d6  mov     rax, cs:__security_cookie
0x18009f6dd  xor     rax, rsp
0x18009f6e0  mov     [rbp+1B0h+var_20], rax
0x18009f6e7  and     [rsp+2B0h+var_250.cbData], 0
0x18009f6ec  xor     eax, eax
0x18009f6ee  and     [rsp+2B0h+var_250.pbData], rax
0x18009f6f3  mov     r14, rdx
0x18009f6f6  and     [rsp+2B0h+cbData], eax
0x18009f6fa  mov     rsi, rcx
0x18009f6fd  and     [rsp+2B0h+lpData], rax
0x18009f702  lea     rcx, [rbp+1B0h+psz]; void *
0x18009f706  and     [rsp+2B0h+ppszDataDescr], rax
0x18009f70b  xor     edx, edx; Val
0x18009f70d  and     [rsp+2B0h+hKey], rax
0x18009f712  mov     r8d, 208h; Size
0x18009f718  and     [rsp+2B0h+Type], eax
0x18009f71c  mov     dword ptr [rsp+2B0h+var_250+4], eax
0x18009f720  mov     [rsp+2B0h+cbData+4], eax
0x18009f724  call    memset_0
0x18009f729  lea     rax, [rsp+2B0h+hKey]
0x18009f72e  mov     r9d, 20019h; samDesired
0x18009f734  xor     r8d, r8d; ulOptions
0x18009f737  mov     [rsp+2B0h+phkResult], rax; lpData
0x18009f73c  lea     rdx, aSystemCurrentc_3; "System\\CurrentControlSet\\Services\\Ts"...
0x18009f743  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18009f74a  call    cs:__imp_RegOpenKeyExW
0x18009f751  nop     dword ptr [rax+rax+00h]
0x18009f756  mov     edi, eax
0x18009f758  mov     r12d, 80070000h
0x18009f75e  test    eax, eax
0x18009f760  jz      short loc_18009F7D6
0x18009f762  jg      short loc_18009F768
0x18009f764  mov     ebx, eax
0x18009f766  jmp     short loc_18009F76E
0x18009f768  movzx   ebx, ax
0x18009f76b  or      ebx, r12d
0x18009f76e  test    ebx, ebx
0x18009f770  jns     short loc_18009F7D6
0x18009f772  mov     rax, cs:WPP_GLOBAL_Control
0x18009f779  lea     rdi, WPP_GLOBAL_Control
0x18009f780  cmp     rax, rdi
0x18009f783  jz      loc_18009FC50
0x18009f789  test    byte ptr [rax+1Ch], 8
0x18009f78d  jz      loc_18009FC50
0x18009f793  cmp     byte ptr [rax+19h], 2
0x18009f797  jb      loc_18009FC50
0x18009f79d  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f7a2  mov     edx, 0Bh
0x18009f7a7  lea     rcx, aRegopenkeyexFa; "RegOpenKeyEx failed"
0x18009f7ae  mov     dword ptr [rsp+2B0h+lpcbData], ebx
0x18009f7b2  mov     [rsp+2B0h+phkResult], rcx
0x18009f7b7  lea     r8, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids
0x18009f7be  mov     rcx, cs:WPP_GLOBAL_Control
0x18009f7c5  mov     r9d, eax
0x18009f7c8  mov     rcx, [rcx+10h]
0x18009f7cc  call    WPP_SF_DsD
0x18009f7d1  jmp     loc_18009FC50
0x18009f7d6  lea     rdx, aPrimaryconnect; "PrimaryConnectionString"
0x18009f7dd  mov     rcx, rsi; String1
0x18009f7e0  call    wcscmp_0
0x18009f7e5  test    eax, eax
0x18009f7e7  jnz     short loc_18009F81B
0x18009f7e9  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18009f7ee  lea     rax, [rsp+2B0h+cbData]
0x18009f7f3  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18009f7f8  lea     r9, [rsp+2B0h+Type]; lpType
0x18009f7fd  and     [rsp+2B0h+phkResult], 0
0x18009f803  lea     rdx, aPrimarysecret; "PrimarySecret"
0x18009f80a  xor     r8d, r8d; lpReserved
0x18009f80d  call    cs:__imp_RegQueryValueExW
0x18009f814  nop     dword ptr [rax+rax+00h]
0x18009f819  mov     edi, eax
0x18009f81b  test    edi, edi
0x18009f81d  jz      short loc_18009F870
0x18009f81f  jg      short loc_18009F825
0x18009f821  mov     ebx, edi
0x18009f823  jmp     short loc_18009F82B
0x18009f825  movzx   ebx, di
0x18009f828  or      ebx, r12d
0x18009f82b  test    ebx, ebx
0x18009f82d  jns     short loc_18009F870
0x18009f82f  mov     rax, cs:WPP_GLOBAL_Control
0x18009f836  lea     rdi, WPP_GLOBAL_Control
0x18009f83d  cmp     rax, rdi
0x18009f840  jz      loc_18009FC50
0x18009f846  test    byte ptr [rax+1Ch], 8
0x18009f84a  jz      loc_18009FC50
0x18009f850  cmp     byte ptr [rax+19h], 2
0x18009f854  jb      loc_18009FC50
0x18009f85a  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f85f  mov     edx, 0Ch
0x18009f864  lea     rcx, aRegqueryvaluee_1; "RegQueryValueEx primary failed!"
0x18009f86b  jmp     loc_18009F7AE
0x18009f870  lea     rdx, aSecondaryconne; "SecondaryConnectionString"
0x18009f877  mov     rcx, rsi; String1
0x18009f87a  call    wcscmp_0
0x18009f87f  test    eax, eax
0x18009f881  jnz     short loc_18009F8B5
0x18009f883  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18009f888  lea     rax, [rsp+2B0h+cbData]
0x18009f88d  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18009f892  lea     r9, [rsp+2B0h+Type]; lpType
0x18009f897  and     [rsp+2B0h+phkResult], 0
0x18009f89d  lea     rdx, aSecondarysecre; "SecondarySecret"
0x18009f8a4  xor     r8d, r8d; lpReserved
0x18009f8a7  call    cs:__imp_RegQueryValueExW
0x18009f8ae  nop     dword ptr [rax+rax+00h]
0x18009f8b3  mov     edi, eax
0x18009f8b5  test    edi, edi
0x18009f8b7  jz      short loc_18009F90A
0x18009f8b9  jg      short loc_18009F8BF
0x18009f8bb  mov     ebx, edi
0x18009f8bd  jmp     short loc_18009F8C5
0x18009f8bf  movzx   ebx, di
0x18009f8c2  or      ebx, r12d
0x18009f8c5  test    ebx, ebx
0x18009f8c7  jns     short loc_18009F90A
0x18009f8c9  mov     rax, cs:WPP_GLOBAL_Control
0x18009f8d0  lea     rdi, WPP_GLOBAL_Control
0x18009f8d7  cmp     rax, rdi
0x18009f8da  jz      loc_18009FC50
0x18009f8e0  test    byte ptr [rax+1Ch], 8
0x18009f8e4  jz      loc_18009FC50
0x18009f8ea  cmp     byte ptr [rax+19h], 2
0x18009f8ee  jb      loc_18009FC50
0x18009f8f4  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f8f9  mov     edx, 0Dh
0x18009f8fe  lea     rcx, aRegqueryvaluee; "RegQueryValueEx secondary failed!"
0x18009f905  jmp     loc_18009F7AE
0x18009f90a  mov     edx, [rsp+2B0h+cbData]; uBytes
0x18009f90e  mov     ecx, 40h ; '@'; uFlags
0x18009f913  call    cs:__imp_LocalAlloc
0x18009f91a  nop     dword ptr [rax+rax+00h]
0x18009f91f  mov     [rsp+2B0h+lpData], rax
0x18009f924  test    rax, rax
0x18009f927  jnz     short loc_18009F977
0x18009f929  mov     ebx, 80004003h
0x18009f92e  mov     rax, cs:WPP_GLOBAL_Control
0x18009f935  lea     rdi, WPP_GLOBAL_Control
0x18009f93c  cmp     rax, rdi
0x18009f93f  jz      loc_18009FC50
0x18009f945  test    byte ptr [rax+1Ch], 8
0x18009f949  jz      loc_18009FC50
0x18009f94f  cmp     byte ptr [rax+19h], 2
0x18009f953  jb      loc_18009FC50
0x18009f959  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009f95e  mov     edx, 0Eh
0x18009f963  mov     dword ptr [rsp+2B0h+lpcbData], 80004003h
0x18009f96b  lea     rcx, aMemoryAllocati; "memory allocation failed secondary fail"...
0x18009f972  jmp     loc_18009F7B2
0x18009f977  lea     rdx, aPrimaryconnect; "PrimaryConnectionString"
0x18009f97e  mov     rcx, rsi; String1
0x18009f981  call    wcscmp_0
0x18009f986  test    eax, eax
0x18009f988  jnz     short loc_18009F9C0
0x18009f98a  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18009f98f  lea     rax, [rsp+2B0h+cbData]
0x18009f994  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18009f999  lea     r9, [rsp+2B0h+Type]; lpType
0x18009f99e  mov     rax, [rsp+2B0h+lpData]
0x18009f9a3  lea     rdx, aPrimarysecret; "PrimarySecret"
0x18009f9aa  xor     r8d, r8d; lpReserved
0x18009f9ad  mov     [rsp+2B0h+phkResult], rax; lpData
0x18009f9b2  call    cs:__imp_RegQueryValueExW
0x18009f9b9  nop     dword ptr [rax+rax+00h]
0x18009f9be  mov     edi, eax
0x18009f9c0  test    edi, edi
0x18009f9c2  jz      short loc_18009FA0E
0x18009f9c4  jg      short loc_18009F9CA
0x18009f9c6  mov     ebx, edi
0x18009f9c8  jmp     short loc_18009F9D0
0x18009f9ca  movzx   ebx, di
0x18009f9cd  or      ebx, r12d
0x18009f9d0  test    ebx, ebx
0x18009f9d2  jns     short loc_18009FA0E
0x18009f9d4  mov     rax, cs:WPP_GLOBAL_Control
0x18009f9db  lea     rdi, WPP_GLOBAL_Control
0x18009f9e2  cmp     rax, rdi
0x18009f9e5  jz      loc_18009FC50
0x18009f9eb  test    byte ptr [rax+1Ch], 8
0x18009f9ef  jz      loc_18009FC50
0x18009f9f5  cmp     byte ptr [rax+19h], 2
0x18009f9f9  jb      loc_18009FC50
0x18009f9ff  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009fa04  mov     edx, 0Fh
0x18009fa09  jmp     loc_18009F864
0x18009fa0e  lea     rdx, aSecondaryconne; "SecondaryConnectionString"
0x18009fa15  mov     rcx, rsi; String1
0x18009fa18  call    wcscmp_0
0x18009fa1d  test    eax, eax
0x18009fa1f  jnz     short loc_18009FA57
0x18009fa21  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18009fa26  lea     rax, [rsp+2B0h+cbData]
0x18009fa2b  mov     [rsp+2B0h+lpcbData], rax; lpcbData
0x18009fa30  lea     r9, [rsp+2B0h+Type]; lpType
0x18009fa35  mov     rax, [rsp+2B0h+lpData]
0x18009fa3a  lea     rdx, aSecondarysecre; "SecondarySecret"
0x18009fa41  xor     r8d, r8d; lpReserved
0x18009fa44  mov     [rsp+2B0h+phkResult], rax; pPromptStruct
0x18009fa49  call    cs:__imp_RegQueryValueExW
0x18009fa50  nop     dword ptr [rax+rax+00h]
0x18009fa55  mov     edi, eax
0x18009fa57  test    edi, edi
0x18009fa59  jz      short loc_18009FAA5
0x18009fa5b  jg      short loc_18009FA61
0x18009fa5d  mov     ebx, edi
0x18009fa5f  jmp     short loc_18009FA67
0x18009fa61  movzx   ebx, di
0x18009fa64  or      ebx, r12d
0x18009fa67  test    ebx, ebx
0x18009fa69  jns     short loc_18009FAA5
0x18009fa6b  mov     rax, cs:WPP_GLOBAL_Control
0x18009fa72  lea     rdi, WPP_GLOBAL_Control
0x18009fa79  cmp     rax, rdi
0x18009fa7c  jz      loc_18009FC50
0x18009fa82  test    byte ptr [rax+1Ch], 8
0x18009fa86  jz      loc_18009FC50
0x18009fa8c  cmp     byte ptr [rax+19h], 2
0x18009fa90  jb      loc_18009FC50
0x18009fa96  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009fa9b  mov     edx, 10h
0x18009faa0  jmp     loc_18009F8FE
0x18009faa5  lea     rax, [rsp+2B0h+var_250]
0x18009faaa  xor     r9d, r9d; pvReserved
0x18009faad  mov     [rsp+2B0h+pDataOut], rax; pDataOut
0x18009fab2  lea     rdx, [rsp+2B0h+ppszDataDescr]; ppszDataDescr
0x18009fab7  mov     dword ptr [rsp+2B0h+lpcbData], 5; dwFlags
0x18009fabf  lea     rcx, [rsp+2B0h+cbData]; pDataIn
0x18009fac4  and     [rsp+2B0h+phkResult], 0
0x18009faca  xor     r8d, r8d; pOptionalEntropy
0x18009facd  call    cs:__imp_CryptUnprotectData
0x18009fad4  nop     dword ptr [rax+rax+00h]
0x18009fad9  test    eax, eax
0x18009fadb  jnz     short loc_18009FB3A
0x18009fadd  call    cs:__imp_GetLastError
0x18009fae4  nop     dword ptr [rax+rax+00h]
0x18009fae9  mov     ebx, eax
0x18009faeb  test    eax, eax
0x18009faed  jle     short loc_18009FAF5
0x18009faef  movzx   ebx, ax
0x18009faf2  or      ebx, r12d
0x18009faf5  test    ebx, ebx
0x18009faf7  jns     short loc_18009FB3A
0x18009faf9  mov     rax, cs:WPP_GLOBAL_Control
0x18009fb00  lea     rdi, WPP_GLOBAL_Control
0x18009fb07  cmp     rax, rdi
0x18009fb0a  jz      loc_18009FC50
0x18009fb10  test    byte ptr [rax+1Ch], 8
0x18009fb14  jz      loc_18009FC50
0x18009fb1a  cmp     byte ptr [rax+19h], 2
0x18009fb1e  jb      loc_18009FC50
0x18009fb24  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009fb29  mov     edx, 11h
0x18009fb2e  lea     rcx, aCryptunprotect; "CryptUnprotectData failed 0x%x"
0x18009fb35  jmp     loc_18009F7AE
0x18009fb3a  mov     rdx, [rsp+2B0h+ppszDataDescr]
0x18009fb3f  sub     rdx, rsi
0x18009fb42  movzx   ecx, word ptr [rsi]
0x18009fb45  movzx   eax, word ptr [rsi+rdx]
0x18009fb49  sub     ecx, eax
0x18009fb4b  jnz     short loc_18009FB55
0x18009fb4d  add     rsi, 2
0x18009fb51  test    eax, eax
0x18009fb53  jnz     short loc_18009FB42
0x18009fb55  lea     rdi, WPP_GLOBAL_Control
0x18009fb5c  test    ecx, ecx
0x18009fb5e  jz      short loc_18009FB9C
0x18009fb60  mov     rax, cs:WPP_GLOBAL_Control
0x18009fb67  cmp     rax, rdi
0x18009fb6a  jz      short loc_18009FBA3
0x18009fb6c  test    byte ptr [rax+1Ch], 1
0x18009fb70  jz      short loc_18009FBA3
0x18009fb72  cmp     byte ptr [rax+19h], 4
0x18009fb76  jb      short loc_18009FBA3
0x18009fb78  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18009fb7d  mov     rcx, cs:WPP_GLOBAL_Control
0x18009fb84  lea     r8, WPP_5c640882e6c13d67d94d4d82c5094b20_Traceguids
0x18009fb8b  mov     edx, 12h
0x18009fb90  mov     r9d, eax
0x18009fb93  mov     rcx, [rcx+10h]
0x18009fb97  call    WPP_SF_D
0x18009fb9c  mov     rax, cs:WPP_GLOBAL_Control
0x18009fba3  mov     ecx, [rsp+2B0h+var_250.cbData]
0x18009fba7  shr     ecx, 1
0x18009fba9  jnz     short loc_18009FBF3
0x18009fbab  mov     ebx, 80004005h
0x18009fbb0  cmp     rax, rdi
0x18009fbb3  jz      loc_18009FC50
0x18009fbb9  test    byte ptr [rax+1Ch], 1
0x18009fbbd  jz      loc_18009FC50
0x18009fbc3  cmp     byte ptr [rax+19h], 2
  ... truncated ...
```
