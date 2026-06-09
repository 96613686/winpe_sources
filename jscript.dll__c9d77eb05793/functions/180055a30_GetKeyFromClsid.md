# GetKeyFromClsid

- ea: `0x180055a30`
- end: `0x180055b96`
- name: `GetKeyFromClsid`
- size: `358`
- prototype: `__int64 __fastcall(IID *rclsid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18008f30c`

## callees

- `0x180055a30`
- `0x1800942d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180055a97`
- `ADVAPI32!RegOpenKeyExA` at `0x180055b16`
- `ADVAPI32!RegOpenKeyExA` at `0x180055a97`
- `ADVAPI32!RegOpenKeyExA` at `0x180055b16`
- `ADVAPI32!RegCloseKey` at `0x180055b58`
- `ADVAPI32!RegCloseKey` at `0x180055b6f`
- `ADVAPI32!RegCloseKey` at `0x180055b58`
- `ADVAPI32!RegCloseKey` at `0x180055b6f`
- `KERNEL32!WideCharToMultiByte` at `0x180055af6`
- `KERNEL32!WideCharToMultiByte` at `0x180055af6`
- `ole32!CoTaskMemFree` at `0x180055b49`
- `ole32!CoTaskMemFree` at `0x180055b49`
- `ole32!StringFromCLSID` at `0x180055abb`
- `ole32!StringFromCLSID` at `0x180055abb`

## string_xrefs

- `0x180055a73`: `CLSID`

## pseudocode

```c
__int64 __fastcall GetKeyFromClsid(IID *rclsid, HKEY *a2)
{
  LSTATUS v4; // eax
  int v5; // ebx
  LSTATUS v6; // eax
  HKEY phkResult; // [rsp+40h] [rbp-9h] BYREF
  LPOLESTR lpsz; // [rsp+48h] [rbp-1h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+7h] BYREF
  CHAR MultiByteStr[48]; // [rsp+58h] [rbp+Fh] BYREF

  *a2 = 0;
  lpsz = 0;
  hKey = 0;
  phkResult = 0;
  v4 = RegOpenKeyExA(HKEY_CLASSES_ROOT, "CLSID", 0, 0x20019u, &hKey);
  v5 = v4;
  if ( v4 > 0 )
    v5 = (unsigned __int16)v4 | 0x80070000;
  if ( v5 >= 0 )
  {
    v5 = StringFromCLSID(rclsid, &lpsz);
    if ( v5 >= 0 )
    {
      WideCharToMultiByte(0, 0, lpsz, -1, MultiByteStr, 48, 0, 0);
      v6 = RegOpenKeyExA(hKey, MultiByteStr, 0, 0x20019u, &phkResult);
      v5 = v6;
      if ( v6 > 0 )
        v5 = (unsigned __int16)v6 | 0x80070000;
      if ( v5 >= 0 )
      {
        v5 = 0;
        *a2 = phkResult;
        phkResult = 0;
      }
    }
  }
  if ( lpsz )
    CoTaskMemFree(lpsz);
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180055a30  mov     [rsp-8+arg_10], rbx
0x180055a35  push    rbp
0x180055a36  push    rsi
0x180055a37  push    rdi
0x180055a38  lea     rbp, [rsp-47h]
0x180055a3d  sub     rsp, 90h
0x180055a44  mov     rax, cs:__security_cookie
0x180055a4b  xor     rax, rsp
0x180055a4e  mov     [rbp+57h+var_18], rax
0x180055a52  mov     rdi, rdx
0x180055a55  mov     qword ptr [rdx], 0
0x180055a5c  mov     rsi, rcx
0x180055a5f  mov     [rbp+57h+lpsz], 0
0x180055a67  lea     rax, [rbp+57h+hKey]
0x180055a6b  mov     [rbp+57h+hKey], 0
0x180055a73  lea     rdx, aClsid; "CLSID"
0x180055a7a  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180055a7f  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180055a86  mov     [rbp+57h+var_60], 0
0x180055a8e  mov     r9d, 20019h; samDesired
0x180055a94  xor     r8d, r8d; ulOptions
0x180055a97  call    cs:__imp_RegOpenKeyExA
0x180055a9d  mov     ebx, eax
0x180055a9f  test    eax, eax
0x180055aa1  jle     short loc_180055AAC
0x180055aa3  movzx   ebx, ax
0x180055aa6  or      ebx, 80070000h
0x180055aac  test    ebx, ebx
0x180055aae  js      loc_180055B40
0x180055ab4  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180055ab8  mov     rcx, rsi; rclsid
0x180055abb  call    cs:__imp_StringFromCLSID
0x180055ac1  mov     ebx, eax
0x180055ac3  test    eax, eax
0x180055ac5  js      short loc_180055B40
0x180055ac7  mov     r8, [rbp+57h+lpsz]; lpWideCharStr
0x180055acb  lea     rax, [rbp+57h+MultiByteStr]
0x180055acf  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180055ad8  or      r9d, 0FFFFFFFFh; cchWideChar
0x180055adc  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x180055ae5  xor     edx, edx; dwFlags
0x180055ae7  mov     [rsp+0A0h+cbMultiByte], 30h ; '0'; cbMultiByte
0x180055aef  xor     ecx, ecx; CodePage
0x180055af1  mov     [rsp+0A0h+phkResult], rax; lpMultiByteStr
0x180055af6  call    cs:__imp_WideCharToMultiByte
0x180055afc  mov     rcx, [rbp+57h+hKey]; hKey
0x180055b00  lea     rax, [rbp+57h+var_60]
0x180055b04  mov     r9d, 20019h; samDesired
0x180055b0a  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180055b0f  xor     r8d, r8d; ulOptions
0x180055b12  lea     rdx, [rbp+57h+MultiByteStr]; lpSubKey
0x180055b16  call    cs:__imp_RegOpenKeyExA
0x180055b1c  mov     ebx, eax
0x180055b1e  test    eax, eax
0x180055b20  jle     short loc_180055B2B
0x180055b22  movzx   ebx, ax
0x180055b25  or      ebx, 80070000h
0x180055b2b  test    ebx, ebx
0x180055b2d  js      short loc_180055B40
0x180055b2f  mov     rax, [rbp+57h+var_60]
0x180055b33  xor     ebx, ebx
0x180055b35  mov     [rdi], rax
0x180055b38  mov     [rbp+57h+var_60], 0
0x180055b40  mov     rcx, [rbp+57h+lpsz]; pv
0x180055b44  test    rcx, rcx
0x180055b47  jz      short loc_180055B4F
0x180055b49  call    cs:__imp_CoTaskMemFree
0x180055b4f  mov     rcx, [rbp+57h+var_60]; hKey
0x180055b53  test    rcx, rcx
0x180055b56  jz      short loc_180055B66
0x180055b58  call    cs:__imp_RegCloseKey
0x180055b5e  mov     [rbp+57h+var_60], 0
0x180055b66  mov     rcx, [rbp+57h+hKey]; hKey
0x180055b6a  test    rcx, rcx
0x180055b6d  jz      short loc_180055B75
0x180055b6f  call    cs:__imp_RegCloseKey
0x180055b75  mov     eax, ebx
0x180055b77  mov     rcx, [rbp+57h+var_18]
0x180055b7b  xor     rcx, rsp; StackCookie
0x180055b7e  call    __security_check_cookie
0x180055b83  mov     rbx, [rsp+0A0h+arg_10]
0x180055b8b  add     rsp, 90h
0x180055b92  pop     rdi
0x180055b93  pop     rsi
0x180055b94  pop     rbp
0x180055b95  retn
```
