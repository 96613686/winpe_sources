# GetKeyFromClsid

- ea: `0x1800568c8`
- end: `0x180056a5d`
- name: `GetKeyFromClsid`
- size: `405`
- prototype: `__int64 __fastcall(IID *rclsid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18009150c`

## callees

- `0x1800568c8`
- `0x1800966e0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18005692f`
- `ADVAPI32!RegOpenKeyExA` at `0x1800569c4`
- `ADVAPI32!RegOpenKeyExA` at `0x18005692f`
- `ADVAPI32!RegOpenKeyExA` at `0x1800569c4`
- `ADVAPI32!RegCloseKey` at `0x180056a12`
- `ADVAPI32!RegCloseKey` at `0x180056a2f`
- `ADVAPI32!RegCloseKey` at `0x180056a12`
- `ADVAPI32!RegCloseKey` at `0x180056a2f`
- `KERNEL32!WideCharToMultiByte` at `0x18005699e`
- `KERNEL32!WideCharToMultiByte` at `0x18005699e`
- `ole32!CoTaskMemFree` at `0x1800569fd`
- `ole32!CoTaskMemFree` at `0x1800569fd`
- `ole32!StringFromCLSID` at `0x180056959`
- `ole32!StringFromCLSID` at `0x180056959`

## string_xrefs

- `0x18005690b`: `CLSID`

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
0x1800568c8  mov     [rsp-8+arg_10], rbx
0x1800568cd  push    rbp
0x1800568ce  push    rsi
0x1800568cf  push    rdi
0x1800568d0  lea     rbp, [rsp-47h]
0x1800568d5  sub     rsp, 90h
0x1800568dc  mov     rax, cs:__security_cookie
0x1800568e3  xor     rax, rsp
0x1800568e6  mov     [rbp+57h+var_18], rax
0x1800568ea  mov     rdi, rdx
0x1800568ed  mov     qword ptr [rdx], 0
0x1800568f4  mov     rsi, rcx
0x1800568f7  mov     [rbp+57h+lpsz], 0
0x1800568ff  lea     rax, [rbp+57h+hKey]
0x180056903  mov     [rbp+57h+hKey], 0
0x18005690b  lea     rdx, aClsid; "CLSID"
0x180056912  mov     [rsp+0A0h+phkResult], rax; phkResult
0x180056917  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18005691e  mov     [rbp+57h+var_60], 0
0x180056926  mov     r9d, 20019h; samDesired
0x18005692c  xor     r8d, r8d; ulOptions
0x18005692f  call    cs:__imp_RegOpenKeyExA
0x180056936  nop     dword ptr [rax+rax+00h]
0x18005693b  mov     ebx, eax
0x18005693d  test    eax, eax
0x18005693f  jle     short loc_18005694A
0x180056941  movzx   ebx, ax
0x180056944  or      ebx, 80070000h
0x18005694a  test    ebx, ebx
0x18005694c  js      loc_1800569F4
0x180056952  lea     rdx, [rbp+57h+lpsz]; lplpsz
0x180056956  mov     rcx, rsi; rclsid
0x180056959  call    cs:__imp_StringFromCLSID
0x180056960  nop     dword ptr [rax+rax+00h]
0x180056965  mov     ebx, eax
0x180056967  test    eax, eax
0x180056969  js      loc_1800569F4
0x18005696f  mov     r8, [rbp+57h+lpsz]; lpWideCharStr
0x180056973  lea     rax, [rbp+57h+MultiByteStr]
0x180056977  mov     [rsp+0A0h+lpUsedDefaultChar], 0; lpUsedDefaultChar
0x180056980  or      r9d, 0FFFFFFFFh; cchWideChar
0x180056984  mov     [rsp+0A0h+lpDefaultChar], 0; lpDefaultChar
0x18005698d  xor     edx, edx; dwFlags
0x18005698f  mov     [rsp+0A0h+cbMultiByte], 30h ; '0'; cbMultiByte
0x180056997  xor     ecx, ecx; CodePage
0x180056999  mov     [rsp+0A0h+phkResult], rax; lpMultiByteStr
0x18005699e  call    cs:__imp_WideCharToMultiByte
0x1800569a5  nop     dword ptr [rax+rax+00h]
0x1800569aa  mov     rcx, [rbp+57h+hKey]; hKey
0x1800569ae  lea     rax, [rbp+57h+var_60]
0x1800569b2  mov     r9d, 20019h; samDesired
0x1800569b8  mov     [rsp+0A0h+phkResult], rax; phkResult
0x1800569bd  xor     r8d, r8d; ulOptions
0x1800569c0  lea     rdx, [rbp+57h+MultiByteStr]; lpSubKey
0x1800569c4  call    cs:__imp_RegOpenKeyExA
0x1800569cb  nop     dword ptr [rax+rax+00h]
0x1800569d0  mov     ebx, eax
0x1800569d2  test    eax, eax
0x1800569d4  jle     short loc_1800569DF
0x1800569d6  movzx   ebx, ax
0x1800569d9  or      ebx, 80070000h
0x1800569df  test    ebx, ebx
0x1800569e1  js      short loc_1800569F4
0x1800569e3  mov     rax, [rbp+57h+var_60]
0x1800569e7  xor     ebx, ebx
0x1800569e9  mov     [rdi], rax
0x1800569ec  mov     [rbp+57h+var_60], 0
0x1800569f4  mov     rcx, [rbp+57h+lpsz]; pv
0x1800569f8  test    rcx, rcx
0x1800569fb  jz      short loc_180056A09
0x1800569fd  call    cs:__imp_CoTaskMemFree
0x180056a04  nop     dword ptr [rax+rax+00h]
0x180056a09  mov     rcx, [rbp+57h+var_60]; hKey
0x180056a0d  test    rcx, rcx
0x180056a10  jz      short loc_180056A26
0x180056a12  call    cs:__imp_RegCloseKey
0x180056a19  nop     dword ptr [rax+rax+00h]
0x180056a1e  mov     [rbp+57h+var_60], 0
0x180056a26  mov     rcx, [rbp+57h+hKey]; hKey
0x180056a2a  test    rcx, rcx
0x180056a2d  jz      short loc_180056A3B
0x180056a2f  call    cs:__imp_RegCloseKey
0x180056a36  nop     dword ptr [rax+rax+00h]
0x180056a3b  mov     eax, ebx
0x180056a3d  mov     rcx, [rbp+57h+var_18]
0x180056a41  xor     rcx, rsp; StackCookie
0x180056a44  call    __security_check_cookie
0x180056a49  mov     rbx, [rsp+0A0h+arg_10]
0x180056a51  add     rsp, 90h
0x180056a58  pop     rdi
0x180056a59  pop     rsi
0x180056a5a  pop     rbp
0x180056a5b  retn
```
