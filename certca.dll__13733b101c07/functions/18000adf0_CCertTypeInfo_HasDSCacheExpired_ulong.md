# CCertTypeInfo::_HasDSCacheExpired(ulong)

- ea: `0x18000adf0`
- end: `0x18000af8e`
- name: `?_HasDSCacheExpired@CCertTypeInfo@@KAJK@Z`
- size: `414`
- prototype: `__int64 __fastcall(__int16)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a630`
- `0x18000a920`

## callees

- `0x180008610`
- `0x18000adf0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000af2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000af2c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000af3a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000af61`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000af3a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000af61`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aeb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af7e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000aeb9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000af7e`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000ae40`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x18000ae40`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000af02`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000af02`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ae8d`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18000ae8d`

## string_xrefs

- `0x18000ae75`: `Software\Microsoft\Cryptography\CertificateTemplateCache`
- `0x18000ae9e`: `Software\Microsoft\Cryptography\CertificateTemplateCache`

## pseudocode

```c
__int64 __fastcall CCertTypeInfo::_HasDSCacheExpired(__int16 a1)
{
  HKEY v2; // rcx
  LSTATUS v3; // eax
  signed int v4; // ebx
  unsigned int v5; // edx
  const unsigned __int16 *v6; // rcx
  LSTATUS v7; // eax
  LONG v8; // eax
  int v9; // ecx
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+58h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-10h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+20h] BYREF
  DWORD Type; // [rsp+98h] [rbp+28h] BYREF
  DWORD dwDisposition; // [rsp+A0h] [rbp+30h] BYREF
  FILETIME Data; // [rsp+A8h] [rbp+38h] BYREF

  hKey = 0;
  dwDisposition = 0;
  cbData = 0;
  Type = 0;
  Data = 0;
  SystemTimeAsFileTime = 0;
  if ( (a1 & 0x400) != 0 )
    return 2147500037LL;
  phkResult = 0;
  if ( (a1 & 0x20) != 0 )
  {
    v2 = HKEY_LOCAL_MACHINE;
  }
  else
  {
    v3 = RegOpenCurrentUser(0x20019u, &phkResult);
    v4 = v3;
    if ( v3 )
    {
      v5 = 20906792;
      v6 = 0;
LABEL_10:
      CSPrintErrorLineFileData2(v6, v5, v3, 0);
      goto LABEL_11;
    }
    v2 = phkResult;
  }
  v3 = RegCreateKeyExW(
         v2,
         L"Software\\Microsoft\\Cryptography\\CertificateTemplateCache",
         0,
         (LPWSTR)&Class,
         0,
         0x20019u,
         0,
         &hKey,
         &dwDisposition);
  v4 = v3;
  if ( v3 )
  {
    v5 = 21889832;
    v6 = L"Software\\Microsoft\\Cryptography\\CertificateTemplateCache";
    goto LABEL_10;
  }
LABEL_11:
  if ( phkResult )
    RegCloseKey(phkResult);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
  }
  else
  {
    cbData = 8;
    v7 = RegQueryValueExW(hKey, L"Timestamp", 0, &Type, (LPBYTE)&Data, &cbData);
    v4 = v7;
    if ( v7 )
    {
      if ( v7 > 0 )
        v4 = (unsigned __int16)v7 | 0x80070000;
    }
    else if ( Type == 3 )
    {
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      if ( CompareFileTime(&SystemTimeAsFileTime, &Data) >= 0 )
      {
        *(_QWORD *)&Data += 6000000000LL;
        v8 = CompareFileTime(&SystemTimeAsFileTime, &Data);
        v9 = 0;
        if ( v8 > 0 )
          v9 = -2147467259;
        v4 = v9;
      }
      else
      {
        v4 = -2147467259;
      }
    }
    else
    {
      v4 = -2147024883;
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000adf0  push    rbp
0x18000adf2  push    rbx
0x18000adf3  push    rdi
0x18000adf4  mov     rbp, rsp
0x18000adf7  sub     rsp, 70h
0x18000adfb  xor     edi, edi
0x18000adfd  mov     [rbp+hKey], rdi
0x18000ae01  mov     [rbp+dwDisposition], edi
0x18000ae04  mov     [rbp+cbData], edi
0x18000ae07  mov     [rbp+Type], edi
0x18000ae0a  mov     [rbp+Data], rdi
0x18000ae0e  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rdi
0x18000ae12  bt      ecx, 0Ah
0x18000ae16  jnb     short loc_18000AE25
0x18000ae18  mov     eax, 80004005h
0x18000ae1d  add     rsp, 70h
0x18000ae21  pop     rdi
0x18000ae22  pop     rbx
0x18000ae23  pop     rbp
0x18000ae24  retn
0x18000ae25  mov     [rbp+phkResult], rdi
0x18000ae29  test    cl, 20h
0x18000ae2c  jz      short loc_18000AE37
0x18000ae2e  mov     rcx, 0FFFFFFFF80000002h
0x18000ae35  jmp     short loc_18000AE59
0x18000ae37  lea     rdx, [rbp+phkResult]; phkResult
0x18000ae3b  mov     ecx, 20019h; samDesired
0x18000ae40  call    cs:__imp_RegOpenCurrentUser
0x18000ae46  mov     ebx, eax
0x18000ae48  test    eax, eax
0x18000ae4a  jz      short loc_18000AE55
0x18000ae4c  mov     edx, 13F0328h
0x18000ae51  xor     ecx, ecx
0x18000ae53  jmp     short loc_18000AEA5
0x18000ae55  mov     rcx, [rbp+phkResult]; hKey
0x18000ae59  lea     rax, [rbp+dwDisposition]
0x18000ae5d  xor     r8d, r8d; Reserved
0x18000ae60  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18000ae65  lea     r9, Class; lpClass
0x18000ae6c  lea     rax, [rbp+hKey]
0x18000ae70  mov     [rsp+70h+var_38], rax; phkResult
0x18000ae75  lea     rdx, SubKey; "Software\\Microsoft\\Cryptography\\Cert"...
0x18000ae7c  mov     [rsp+70h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000ae81  mov     [rsp+70h+samDesired], 20019h; samDesired
0x18000ae89  mov     [rsp+70h+dwOptions], edi; dwOptions
0x18000ae8d  call    cs:__imp_RegCreateKeyExW
0x18000ae93  mov     ebx, eax
0x18000ae95  test    eax, eax
0x18000ae97  jz      short loc_18000AEB0
0x18000ae99  mov     edx, 14E0328h; unsigned int
0x18000ae9e  lea     rcx, SubKey; "Software\\Microsoft\\Cryptography\\Cert"...
0x18000aea5  xor     r9d, r9d; int
0x18000aea8  mov     r8d, eax; int
0x18000aeab  call    ?CSPrintErrorLineFileData2@@YAXPEBGKJJ@Z; CSPrintErrorLineFileData2(ushort const *,ulong,long,long)
0x18000aeb0  mov     rcx, [rbp+phkResult]; hKey
0x18000aeb4  test    rcx, rcx
0x18000aeb7  jz      short loc_18000AEBF
0x18000aeb9  call    cs:__imp_RegCloseKey
0x18000aebf  test    ebx, ebx
0x18000aec1  jz      short loc_18000AED7
0x18000aec3  jle     loc_18000AF75
0x18000aec9  movzx   ebx, bx
0x18000aecc  or      ebx, 80070000h
0x18000aed2  jmp     loc_18000AF75
0x18000aed7  mov     rcx, [rbp+hKey]; hKey
0x18000aedb  lea     rax, [rbp+cbData]
0x18000aedf  mov     qword ptr [rsp+70h+samDesired], rax; lpcbData
0x18000aee4  lea     r9, [rbp+Type]; lpType
0x18000aee8  lea     rax, [rbp+Data]
0x18000aeec  mov     [rbp+cbData], 8
0x18000aef3  xor     r8d, r8d; lpReserved
0x18000aef6  mov     qword ptr [rsp+70h+dwOptions], rax; lpData
0x18000aefb  lea     rdx, aTimestamp; "Timestamp"
0x18000af02  call    cs:__imp_RegQueryValueExW
0x18000af08  mov     ebx, eax
0x18000af0a  test    eax, eax
0x18000af0c  jz      short loc_18000AF1B
0x18000af0e  jle     short loc_18000AF75
0x18000af10  movzx   ebx, ax
0x18000af13  or      ebx, 80070000h
0x18000af19  jmp     short loc_18000AF75
0x18000af1b  cmp     [rbp+Type], 3
0x18000af1f  jz      short loc_18000AF28
0x18000af21  mov     ebx, 8007000Dh
0x18000af26  jmp     short loc_18000AF75
0x18000af28  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000af2c  call    cs:__imp_GetSystemTimeAsFileTime
0x18000af32  lea     rdx, [rbp+Data]; lpFileTime2
0x18000af36  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x18000af3a  call    cs:__imp_CompareFileTime
0x18000af40  test    eax, eax
0x18000af42  jns     short loc_18000AF4B
0x18000af44  mov     ebx, 80004005h
0x18000af49  jmp     short loc_18000AF75
0x18000af4b  mov     rax, 165A0BC00h
0x18000af55  lea     rdx, [rbp+Data]; lpFileTime2
0x18000af59  add     [rbp+Data], rax
0x18000af5d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpFileTime1
0x18000af61  call    cs:__imp_CompareFileTime
0x18000af67  mov     ebx, 80004005h
0x18000af6c  mov     ecx, edi
0x18000af6e  test    eax, eax
0x18000af70  cmovg   ecx, ebx
0x18000af73  mov     ebx, ecx
0x18000af75  mov     rcx, [rbp+hKey]; hKey
0x18000af79  test    rcx, rcx
0x18000af7c  jz      short loc_18000AF84
0x18000af7e  call    cs:__imp_RegCloseKey
0x18000af84  mov     eax, ebx
0x18000af86  add     rsp, 70h
0x18000af8a  pop     rdi
0x18000af8b  pop     rbx
0x18000af8c  pop     rbp
0x18000af8d  retn
```
