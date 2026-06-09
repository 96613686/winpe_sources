# LSAddLicenseToStore(void *,ulong,tagLSINDEX *,uchar *,ulong)

- ea: `0x18048e694`
- end: `0x18048e9ae`
- name: `?LSAddLicenseToStore@@YAKPEAXKPEAUtagLSINDEX@@PEAEK@Z`
- size: `794`
- prototype: `unsigned int __usercall@<eax>(HKEY hKey@<rcx>, unsigned int@<edx>, struct tagLSINDEX *@<r8>, unsigned __int8 *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18019bebc`

## callees

- `0x180085e04`
- `0x18048e694`
- `0x18048e9b4`
- `0x18048e9d8`
- `0x180688fc0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18048e79d`
- `ADVAPI32!RegOpenKeyExW` at `0x18048e800`
- `ADVAPI32!RegOpenKeyExW` at `0x18048e79d`
- `ADVAPI32!RegOpenKeyExW` at `0x18048e800`
- `ADVAPI32!RegCloseKey` at `0x18048e7b1`
- `ADVAPI32!RegCloseKey` at `0x18048e97d`
- `ADVAPI32!RegCloseKey` at `0x18048e7b1`
- `ADVAPI32!RegCloseKey` at `0x18048e97d`
- `ADVAPI32!RegCreateKeyExW` at `0x18048e845`
- `ADVAPI32!RegCreateKeyExW` at `0x18048e845`
- `ADVAPI32!RegSetValueExW` at `0x18048e88f`
- `ADVAPI32!RegSetValueExW` at `0x18048e8c2`
- `ADVAPI32!RegSetValueExW` at `0x18048e8f5`
- `ADVAPI32!RegSetValueExW` at `0x18048e91c`
- `ADVAPI32!RegSetValueExW` at `0x18048e957`
- `ADVAPI32!RegSetValueExW` at `0x18048e88f`
- `ADVAPI32!RegSetValueExW` at `0x18048e8c2`
- `ADVAPI32!RegSetValueExW` at `0x18048e8f5`
- `ADVAPI32!RegSetValueExW` at `0x18048e91c`
- `ADVAPI32!RegSetValueExW` at `0x18048e957`
- `ADVAPI32!RegDeleteValueW` at `0x18048e934`
- `ADVAPI32!RegDeleteValueW` at `0x18048e934`

## string_xrefs

- `0x18048e8a0`: `CompanyName`

## pseudocode

```c
__int64 __fastcall LSAddLicenseToStore(HKEY hKey, __int64 a2, struct tagLSINDEX *a3, unsigned __int8 *a4, DWORD cbData)
{
  unsigned int v8; // eax
  unsigned int v9; // edx
  HKEY v10; // r14
  BOOL v11; // ebx
  unsigned int v12; // r14d
  DWORD v13; // eax
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v17; // [rsp+5Ch] [rbp-A4h]
  HKEY v18; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[256]; // [rsp+70h] [rbp-90h] BYREF

  v18 = 0;
  hKeya = 0;
  if ( !hKey || !a3 || !*((_QWORD *)a3 + 1) || !*((_QWORD *)a3 + 3) || !*((_QWORD *)a3 + 5) || !a4 || !cbData )
    return 5;
  v8 = LSOpenLicenseHandle(hKey, 0, a3, (void **)&v18);
  v10 = v18;
  v11 = v8;
  if ( v8 )
  {
    if ( v8 == 3 )
    {
      dwDisposition = 0;
      v17 = 0;
      v11 = 1;
      if ( (int)StringCchPrintfW(SubKey, 0x100u, L"LICENSE%03d", 0) >= 0 )
      {
        v12 = v17;
        do
        {
          if ( RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, &hKeya) )
            break;
          if ( hKeya )
          {
            RegCloseKey(hKeya);
            hKeya = 0;
          }
          ++v12;
        }
        while ( (int)StringCchPrintfW(SubKey, 0x100u, L"LICENSE%03d", v12) >= 0 );
        v10 = v18;
      }
      if ( !RegOpenKeyExW(hKey, SubKey, 0, 0x2001Fu, &hKeya) )
      {
        v13 = 2;
        dwDisposition = 2;
        goto LABEL_21;
      }
      if ( !RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKeya, &dwDisposition) )
      {
        v13 = dwDisposition;
LABEL_21:
        if ( v13 == 1
          && !RegSetValueExW(hKeya, L"LicenseScope", 0, 3u, *((const BYTE **)a3 + 1), *((_DWORD *)a3 + 1))
          && !RegSetValueExW(hKeya, L"CompanyName", 0, 3u, *((const BYTE **)a3 + 3), *((_DWORD *)a3 + 4))
          && !RegSetValueExW(hKeya, L"ProductID", 0, 3u, *((const BYTE **)a3 + 5), *((_DWORD *)a3 + 8))
          && !RegSetValueExW(hKeya, L"ClientLicense", 0, 3u, a4, cbData) )
        {
          v11 = 0;
        }
      }
    }
  }
  else
  {
    RegDeleteValueW(v18, L"ClientLicense");
    v11 = RegSetValueExW(v10, L"ClientLicense", 0, 3u, a4, cbData) != 0;
  }
  if ( v10 )
    LSCloseLicenseHandle(v10, v9);
  if ( hKeya )
    RegCloseKey(hKeya);
  return v11;
}

```

## disassembly

```asm
0x18048e694  push    rbp
0x18048e696  push    rbx
0x18048e697  push    rdi
0x18048e698  push    r12
0x18048e69a  push    r13
0x18048e69c  push    r14
0x18048e69e  push    r15
0x18048e6a0  lea     rbp, [rsp-180h]
0x18048e6a8  sub     rsp, 280h
0x18048e6af  mov     rax, cs:__security_cookie
0x18048e6b6  xor     rax, rsp
0x18048e6b9  mov     [rbp+1B0h+var_40], rax
0x18048e6c0  mov     [rsp+2B0h+var_250], 0
0x18048e6c9  mov     r13, r9
0x18048e6cc  mov     [rsp+2B0h+hKey], 0
0x18048e6d5  mov     rdi, r8
0x18048e6d8  mov     r15, rcx
0x18048e6db  test    rcx, rcx
0x18048e6de  jz      loc_18048E987
0x18048e6e4  test    r8, r8
0x18048e6e7  jz      loc_18048E987
0x18048e6ed  cmp     qword ptr [r8+8], 0
0x18048e6f2  jz      loc_18048E987
0x18048e6f8  cmp     qword ptr [r8+18h], 0
0x18048e6fd  jz      loc_18048E987
0x18048e703  cmp     qword ptr [r8+28h], 0
0x18048e708  jz      loc_18048E987
0x18048e70e  test    r9, r9
0x18048e711  jz      loc_18048E987
0x18048e717  mov     r12d, [rbp+1B0h+cbData]
0x18048e71e  test    r12d, r12d
0x18048e721  jz      loc_18048E987
0x18048e727  lea     r9, [rsp+2B0h+var_250]; void **
0x18048e72c  xor     edx, edx; int
0x18048e72e  call    ?LSOpenLicenseHandle@@YAKPEAXHPEAUtagLSINDEX@@PEAPEAX@Z; LSOpenLicenseHandle(void *,int,tagLSINDEX *,void * *)
0x18048e733  mov     r14, [rsp+2B0h+var_250]
0x18048e738  mov     ebx, eax
0x18048e73a  test    eax, eax
0x18048e73c  jz      loc_18048E92A
0x18048e742  cmp     eax, 3
0x18048e745  jnz     loc_18048E966
0x18048e74b  xor     r9d, r9d
0x18048e74e  mov     [rsp+2B0h+dwDisposition], 0
0x18048e756  lea     r8, aLicense03d; "LICENSE%03d"
0x18048e75d  mov     [rsp+2B0h+var_254], 0
0x18048e765  mov     edx, 100h; unsigned __int64
0x18048e76a  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x18048e76f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18048e774  mov     ebx, 1
0x18048e779  test    eax, eax
0x18048e77b  js      short loc_18048E7E5
0x18048e77d  mov     r14d, [rsp+2B0h+var_254]
0x18048e782  lea     rax, [rsp+2B0h+hKey]
0x18048e787  mov     r9d, 2001Fh; samDesired
0x18048e78d  xor     r8d, r8d; ulOptions
0x18048e790  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18048e795  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18048e79a  mov     rcx, r15; hKey
0x18048e79d  call    cs:__imp_RegOpenKeyExW
0x18048e7a3  test    eax, eax
0x18048e7a5  jnz     short loc_18048E7E0
0x18048e7a7  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18048e7ac  test    rcx, rcx
0x18048e7af  jz      short loc_18048E7C0
0x18048e7b1  call    cs:__imp_RegCloseKey
0x18048e7b7  mov     [rsp+2B0h+hKey], 0
0x18048e7c0  add     r14d, ebx
0x18048e7c3  lea     r8, aLicense03d; "LICENSE%03d"
0x18048e7ca  mov     r9d, r14d
0x18048e7cd  lea     rcx, [rsp+2B0h+SubKey]; unsigned __int16 *
0x18048e7d2  mov     edx, 100h; unsigned __int64
0x18048e7d7  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18048e7dc  test    eax, eax
0x18048e7de  jns     short loc_18048E782
0x18048e7e0  mov     r14, [rsp+2B0h+var_250]
0x18048e7e5  lea     rax, [rsp+2B0h+hKey]
0x18048e7ea  mov     r9d, 2001Fh; samDesired
0x18048e7f0  xor     r8d, r8d; ulOptions
0x18048e7f3  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18048e7f8  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18048e7fd  mov     rcx, r15; hKey
0x18048e800  call    cs:__imp_RegOpenKeyExW
0x18048e806  test    eax, eax
0x18048e808  jz      short loc_18048E859
0x18048e80a  lea     rax, [rsp+2B0h+dwDisposition]
0x18048e80f  xor     r9d, r9d; lpClass
0x18048e812  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x18048e817  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18048e81c  lea     rax, [rsp+2B0h+hKey]
0x18048e821  xor     r8d, r8d; Reserved
0x18048e824  mov     [rsp+2B0h+var_278], rax; phkResult
0x18048e829  mov     rcx, r15; hKey
0x18048e82c  mov     [rsp+2B0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18048e835  mov     [rsp+2B0h+samDesired], 2001Fh; samDesired
0x18048e83d  mov     dword ptr [rsp+2B0h+phkResult], 0; dwOptions
0x18048e845  call    cs:__imp_RegCreateKeyExW
0x18048e84b  test    eax, eax
0x18048e84d  jnz     loc_18048E966
0x18048e853  mov     eax, [rsp+2B0h+dwDisposition]
0x18048e857  jmp     short loc_18048E862
0x18048e859  mov     eax, 2
0x18048e85e  mov     [rsp+2B0h+dwDisposition], eax
0x18048e862  cmp     eax, ebx
0x18048e864  jnz     loc_18048E966
0x18048e86a  mov     eax, [rdi+4]
0x18048e86d  lea     rdx, aLicensescope; "LicenseScope"
0x18048e874  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18048e879  mov     r9d, 3; dwType
0x18048e87f  mov     [rsp+2B0h+samDesired], eax; cbData
0x18048e883  xor     r8d, r8d; Reserved
0x18048e886  mov     rax, [rdi+8]
0x18048e88a  mov     [rsp+2B0h+phkResult], rax; lpData
0x18048e88f  call    cs:__imp_RegSetValueExW
0x18048e895  test    eax, eax
0x18048e897  jnz     loc_18048E966
0x18048e89d  mov     eax, [rdi+10h]
0x18048e8a0  lea     rdx, aCompanyname; "CompanyName"
0x18048e8a7  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18048e8ac  mov     r9d, 3; dwType
0x18048e8b2  mov     [rsp+2B0h+samDesired], eax; cbData
0x18048e8b6  xor     r8d, r8d; Reserved
0x18048e8b9  mov     rax, [rdi+18h]
0x18048e8bd  mov     [rsp+2B0h+phkResult], rax; lpData
0x18048e8c2  call    cs:__imp_RegSetValueExW
0x18048e8c8  test    eax, eax
0x18048e8ca  jnz     loc_18048E966
0x18048e8d0  mov     eax, [rdi+20h]
0x18048e8d3  lea     rdx, aProductid; "ProductID"
0x18048e8da  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18048e8df  mov     r9d, 3; dwType
0x18048e8e5  mov     [rsp+2B0h+samDesired], eax; cbData
0x18048e8e9  xor     r8d, r8d; Reserved
0x18048e8ec  mov     rax, [rdi+28h]
0x18048e8f0  mov     [rsp+2B0h+phkResult], rax; lpData
0x18048e8f5  call    cs:__imp_RegSetValueExW
0x18048e8fb  test    eax, eax
0x18048e8fd  jnz     short loc_18048E966
0x18048e8ff  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18048e904  lea     r9d, [rax+3]; dwType
0x18048e908  mov     [rsp+2B0h+samDesired], r12d; cbData
0x18048e90d  lea     rdx, ValueName; "ClientLicense"
0x18048e914  xor     r8d, r8d; Reserved
0x18048e917  mov     [rsp+2B0h+phkResult], r13; lpData
0x18048e91c  call    cs:__imp_RegSetValueExW
0x18048e922  test    eax, eax
0x18048e924  jnz     short loc_18048E966
0x18048e926  xor     ebx, ebx
0x18048e928  jmp     short loc_18048E966
0x18048e92a  lea     rdx, ValueName; "ClientLicense"
0x18048e931  mov     rcx, r14; hKey
0x18048e934  call    cs:__imp_RegDeleteValueW
0x18048e93a  mov     r9d, 3; dwType
0x18048e940  mov     [rsp+2B0h+samDesired], r12d; cbData
0x18048e945  xor     r8d, r8d; Reserved
0x18048e948  mov     [rsp+2B0h+phkResult], r13; lpData
0x18048e94d  lea     rdx, ValueName; "ClientLicense"
0x18048e954  mov     rcx, r14; hKey
0x18048e957  call    cs:__imp_RegSetValueExW
0x18048e95d  test    eax, eax
0x18048e95f  jz      short loc_18048E966
0x18048e961  mov     ebx, 1
0x18048e966  test    r14, r14
0x18048e969  jz      short loc_18048E973
0x18048e96b  mov     rcx, r14; void *
0x18048e96e  call    ?LSCloseLicenseHandle@@YAKPEAXK@Z; LSCloseLicenseHandle(void *,ulong)
0x18048e973  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18048e978  test    rcx, rcx
0x18048e97b  jz      short loc_18048E983
0x18048e97d  call    cs:__imp_RegCloseKey
0x18048e983  mov     eax, ebx
0x18048e985  jmp     short loc_18048E98C
0x18048e987  mov     eax, 5
0x18048e98c  mov     rcx, [rbp+1B0h+var_40]
0x18048e993  xor     rcx, rsp; StackCookie
0x18048e996  call    __security_check_cookie
0x18048e99b  add     rsp, 280h
0x18048e9a2  pop     r15
0x18048e9a4  pop     r14
0x18048e9a6  pop     r13
0x18048e9a8  pop     r12
0x18048e9aa  pop     rdi
0x18048e9ab  pop     rbx
0x18048e9ac  pop     rbp
0x18048e9ad  retn
```
