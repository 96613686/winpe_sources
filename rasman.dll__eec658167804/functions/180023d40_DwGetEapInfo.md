# DwGetEapInfo

- ea: `0x180023d40`
- end: `0x180023ecd`
- name: `DwGetEapInfo`
- size: `397`
- prototype: `__int64 __fastcall(__int64, int, BYTE **, DWORD *, HKEY *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180023ed4`
- `0x180024358`

## callees

- `0x180023d40`
- `0x1800245e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023e88`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180023e88`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023dee`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180023dee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023e1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023e68`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023e1a`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180023e68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ea0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023ea0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023e2c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e3a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180023e3a`

## pseudocode

```c
__int64 __fastcall DwGetEapInfo(__int64 a1, int a2, BYTE **a3, DWORD *a4, HKEY *a5)
{
  BYTE *v8; // rdi
  HKEY v9; // rcx
  LSTATUS EapKeyFromToken; // eax
  const WCHAR *v12; // rdx
  unsigned int v13; // ebx
  DWORD LastError; // eax
  __int64 result; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-10h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+90h] [rbp+30h] BYREF
  DWORD Type; // [rsp+98h] [rbp+38h] BYREF

  v8 = 0;
  v9 = 0;
  hKey = 0;
  dwDisposition = 0;
  cbData = 0;
  Type = 0;
  if ( a3 && a4 )
  {
    if ( (unsigned __int64)(a1 - 1) > 0xFFFFFFFFFFFFFFFDuLL || a2 )
    {
      v12 = L"Software\\Microsoft\\Router EAP\\IfEapInfo";
      if ( !a2 )
        v12 = L"Software\\Microsoft\\RAS EAP\\UserEapInfo";
      EapKeyFromToken = RegCreateKeyExW(
                          (HKEY)((a2 != 0) - 0x7FFFFFFFLL),
                          v12,
                          0,
                          0,
                          0,
                          0xF003Fu,
                          0,
                          &hKey,
                          &dwDisposition);
    }
    else
    {
      EapKeyFromToken = lrGetEapKeyFromToken(a1, &hKey, 0);
    }
    v13 = EapKeyFromToken;
    if ( !EapKeyFromToken )
    {
      v13 = RegQueryValueExW(hKey, L"EapInfo", 0, &Type, 0, &cbData);
      if ( !v13 )
      {
        v8 = (BYTE *)LocalAlloc(0x40u, cbData);
        if ( v8 )
          LastError = RegQueryValueExW(hKey, L"EapInfo", 0, &Type, v8, &cbData);
        else
          LastError = GetLastError();
        v13 = LastError;
      }
    }
    v9 = hKey;
  }
  else
  {
    v13 = -2147024809;
  }
  if ( a5 )
  {
    *a5 = v9;
  }
  else if ( v9 )
  {
    RegCloseKey(v9);
  }
  if ( a3 )
  {
    *a3 = v8;
  }
  else if ( v8 )
  {
    LocalFree(v8);
  }
  if ( a4 )
    *a4 = cbData;
  result = 0;
  if ( v13 != 2 )
    return v13;
  return result;
}

```

## disassembly

```asm
0x180023d40  mov     [rsp-18h+arg_0], rbx
0x180023d45  mov     [rsp-18h+arg_8], rsi
0x180023d4a  push    rbp
0x180023d4b  push    rdi
0x180023d4c  push    r14
0x180023d4e  mov     rbp, rsp
0x180023d51  sub     rsp, 60h
0x180023d55  mov     r14, r8
0x180023d58  mov     rsi, r9
0x180023d5b  mov     r9, rcx
0x180023d5e  xor     edi, edi
0x180023d60  xor     ecx, ecx; hKey
0x180023d62  mov     r8d, edx
0x180023d65  mov     [rbp+hKey], rcx
0x180023d69  mov     [rbp+dwDisposition], ecx
0x180023d6c  mov     [rbp+cbData], ecx
0x180023d6f  mov     [rbp+Type], ecx
0x180023d72  test    r14, r14
0x180023d75  jz      loc_180023E70
0x180023d7b  test    rsi, rsi
0x180023d7e  jz      loc_180023E70
0x180023d84  lea     rax, [r9-1]
0x180023d88  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180023d8c  ja      short loc_180023DA0
0x180023d8e  test    edx, edx
0x180023d90  jnz     short loc_180023DA0
0x180023d92  lea     rdx, [rbp+hKey]
0x180023d96  mov     rcx, r9
0x180023d99  call    lrGetEapKeyFromToken
0x180023d9e  jmp     short loc_180023DF4
0x180023da0  test    r8d, r8d
0x180023da3  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\RAS EAP\\UserEapIn"...
0x180023daa  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Router EAP\\IfEapI"...
0x180023db1  cmovz   rdx, rax; lpSubKey
0x180023db5  neg     r8d
0x180023db8  lea     rax, [rbp+dwDisposition]
0x180023dbc  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180023dc1  sbb     rcx, rcx
0x180023dc4  lea     rax, [rbp+hKey]
0x180023dc8  neg     rcx
0x180023dcb  mov     [rsp+60h+phkResult], rax; phkResult
0x180023dd0  add     rcx, 0FFFFFFFF80000001h; hKey
0x180023dd7  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180023ddc  xor     r9d, r9d; lpClass
0x180023ddf  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180023de7  xor     r8d, r8d; Reserved
0x180023dea  mov     [rsp+60h+dwOptions], edi; dwOptions
0x180023dee  call    cs:__imp_RegCreateKeyExW
0x180023df4  mov     ebx, eax
0x180023df6  test    eax, eax
0x180023df8  jnz     short loc_180023E42
0x180023dfa  mov     rcx, [rbp+hKey]; hKey
0x180023dfe  lea     rax, [rbp+cbData]
0x180023e02  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180023e07  lea     r9, [rbp+Type]; lpType
0x180023e0b  xor     r8d, r8d; lpReserved
0x180023e0e  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x180023e13  lea     rdx, aEapinfo; "EapInfo"
0x180023e1a  call    cs:__imp_RegQueryValueExW
0x180023e20  mov     ebx, eax
0x180023e22  test    eax, eax
0x180023e24  jnz     short loc_180023E42
0x180023e26  mov     edx, [rbp+cbData]; uBytes
0x180023e29  lea     ecx, [rax+40h]; uFlags
0x180023e2c  call    cs:__imp_LocalAlloc
0x180023e32  mov     rdi, rax
0x180023e35  test    rax, rax
0x180023e38  jnz     short loc_180023E48
0x180023e3a  call    cs:__imp_GetLastError
0x180023e40  mov     ebx, eax
0x180023e42  mov     rcx, [rbp+hKey]
0x180023e46  jmp     short loc_180023E75
0x180023e48  mov     rcx, [rbp+hKey]; hKey
0x180023e4c  lea     rax, [rbp+cbData]
0x180023e50  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180023e55  lea     r9, [rbp+Type]; lpType
0x180023e59  xor     r8d, r8d; lpReserved
0x180023e5c  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x180023e61  lea     rdx, aEapinfo; "EapInfo"
0x180023e68  call    cs:__imp_RegQueryValueExW
0x180023e6e  jmp     short loc_180023E40
0x180023e70  mov     ebx, 80070057h
0x180023e75  mov     rax, [rbp+arg_20]
0x180023e79  test    rax, rax
0x180023e7c  jz      short loc_180023E83
0x180023e7e  mov     [rax], rcx
0x180023e81  jmp     short loc_180023E8E
0x180023e83  test    rcx, rcx
0x180023e86  jz      short loc_180023E8E
0x180023e88  call    cs:__imp_RegCloseKey
0x180023e8e  test    r14, r14
0x180023e91  jz      short loc_180023E98
0x180023e93  mov     [r14], rdi
0x180023e96  jmp     short loc_180023EA6
0x180023e98  test    rdi, rdi
0x180023e9b  jz      short loc_180023EA6
0x180023e9d  mov     rcx, rdi; hMem
0x180023ea0  call    cs:__imp_LocalFree
0x180023ea6  test    rsi, rsi
0x180023ea9  jz      short loc_180023EB0
0x180023eab  mov     eax, [rbp+cbData]
0x180023eae  mov     [rsi], eax
0x180023eb0  xor     eax, eax
0x180023eb2  lea     r11, [rsp+60h+var_s0]
0x180023eb7  mov     rsi, [r11+28h]
0x180023ebb  cmp     ebx, 2
0x180023ebe  cmovnz  eax, ebx
0x180023ec1  mov     rbx, [r11+20h]
0x180023ec5  mov     rsp, r11
0x180023ec8  pop     r14
0x180023eca  pop     rdi
0x180023ecb  pop     rbp
0x180023ecc  retn
```
