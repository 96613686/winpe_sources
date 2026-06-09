# DwGetEapInfo

- ea: `0x180024a50`
- end: `0x180024c08`
- name: `DwGetEapInfo`
- size: `440`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024c10`
- `0x1800250d4`

## callees

- `0x180024a50`
- `0x180025398`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024bb6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180024bb6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024afe`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180024afe`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024b30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024b90`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024b30`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180024b90`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024bd4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180024bd4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024b48`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180024b48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b5c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024b5c`

## pseudocode

```c
__int64 __fastcall DwGetEapInfo(char *a1, int a2, BYTE **a3, DWORD *a4, HKEY *a5)
{
  BYTE *v8; // rdi
  HKEY v9; // rcx
  unsigned int EapKeyFromToken; // eax
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
      EapKeyFromToken = lrGetEapKeyFromToken(a1, &hKey);
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
0x180024a50  mov     [rsp-18h+arg_0], rbx
0x180024a55  mov     [rsp-18h+arg_8], rsi
0x180024a5a  push    rbp
0x180024a5b  push    rdi
0x180024a5c  push    r14
0x180024a5e  mov     rbp, rsp
0x180024a61  sub     rsp, 60h
0x180024a65  mov     r14, r8
0x180024a68  mov     rsi, r9
0x180024a6b  mov     r9, rcx
0x180024a6e  xor     edi, edi
0x180024a70  xor     ecx, ecx; hKey
0x180024a72  mov     r8d, edx
0x180024a75  mov     [rbp+hKey], rcx
0x180024a79  mov     [rbp+dwDisposition], ecx
0x180024a7c  mov     [rbp+cbData], ecx
0x180024a7f  mov     [rbp+Type], ecx
0x180024a82  test    r14, r14
0x180024a85  jz      loc_180024B9E
0x180024a8b  test    rsi, rsi
0x180024a8e  jz      loc_180024B9E
0x180024a94  lea     rax, [r9-1]
0x180024a98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180024a9c  ja      short loc_180024AB0
0x180024a9e  test    edx, edx
0x180024aa0  jnz     short loc_180024AB0
0x180024aa2  lea     rdx, [rbp+hKey]
0x180024aa6  mov     rcx, r9
0x180024aa9  call    lrGetEapKeyFromToken
0x180024aae  jmp     short loc_180024B0A
0x180024ab0  test    r8d, r8d
0x180024ab3  lea     rax, aSoftwareMicros_0; "Software\\Microsoft\\RAS EAP\\UserEapIn"...
0x180024aba  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Router EAP\\IfEapI"...
0x180024ac1  cmovz   rdx, rax; lpSubKey
0x180024ac5  neg     r8d
0x180024ac8  lea     rax, [rbp+dwDisposition]
0x180024acc  mov     [rsp+60h+lpdwDisposition], rax; lpdwDisposition
0x180024ad1  sbb     rcx, rcx
0x180024ad4  lea     rax, [rbp+hKey]
0x180024ad8  neg     rcx
0x180024adb  mov     [rsp+60h+phkResult], rax; phkResult
0x180024ae0  add     rcx, 0FFFFFFFF80000001h; hKey
0x180024ae7  mov     [rsp+60h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x180024aec  xor     r9d, r9d; lpClass
0x180024aef  mov     [rsp+60h+samDesired], 0F003Fh; samDesired
0x180024af7  xor     r8d, r8d; Reserved
0x180024afa  mov     [rsp+60h+dwOptions], edi; dwOptions
0x180024afe  call    cs:__imp_RegCreateKeyExW
0x180024b05  nop     dword ptr [rax+rax+00h]
0x180024b0a  mov     ebx, eax
0x180024b0c  test    eax, eax
0x180024b0e  jnz     short loc_180024B6A
0x180024b10  mov     rcx, [rbp+hKey]; hKey
0x180024b14  lea     rax, [rbp+cbData]
0x180024b18  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180024b1d  lea     r9, [rbp+Type]; lpType
0x180024b21  xor     r8d, r8d; lpReserved
0x180024b24  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x180024b29  lea     rdx, aEapinfo; "EapInfo"
0x180024b30  call    cs:__imp_RegQueryValueExW
0x180024b37  nop     dword ptr [rax+rax+00h]
0x180024b3c  mov     ebx, eax
0x180024b3e  test    eax, eax
0x180024b40  jnz     short loc_180024B6A
0x180024b42  mov     edx, [rbp+cbData]; uBytes
0x180024b45  lea     ecx, [rax+40h]; uFlags
0x180024b48  call    cs:__imp_LocalAlloc
0x180024b4f  nop     dword ptr [rax+rax+00h]
0x180024b54  mov     rdi, rax
0x180024b57  test    rax, rax
0x180024b5a  jnz     short loc_180024B70
0x180024b5c  call    cs:__imp_GetLastError
0x180024b63  nop     dword ptr [rax+rax+00h]
0x180024b68  mov     ebx, eax
0x180024b6a  mov     rcx, [rbp+hKey]
0x180024b6e  jmp     short loc_180024BA3
0x180024b70  mov     rcx, [rbp+hKey]; hKey
0x180024b74  lea     rax, [rbp+cbData]
0x180024b78  mov     qword ptr [rsp+60h+samDesired], rax; lpcbData
0x180024b7d  lea     r9, [rbp+Type]; lpType
0x180024b81  xor     r8d, r8d; lpReserved
0x180024b84  mov     qword ptr [rsp+60h+dwOptions], rdi; lpData
0x180024b89  lea     rdx, aEapinfo; "EapInfo"
0x180024b90  call    cs:__imp_RegQueryValueExW
0x180024b97  nop     dword ptr [rax+rax+00h]
0x180024b9c  jmp     short loc_180024B68
0x180024b9e  mov     ebx, 80070057h
0x180024ba3  mov     rax, [rbp+arg_20]
0x180024ba7  test    rax, rax
0x180024baa  jz      short loc_180024BB1
0x180024bac  mov     [rax], rcx
0x180024baf  jmp     short loc_180024BC2
0x180024bb1  test    rcx, rcx
0x180024bb4  jz      short loc_180024BC2
0x180024bb6  call    cs:__imp_RegCloseKey
0x180024bbd  nop     dword ptr [rax+rax+00h]
0x180024bc2  test    r14, r14
0x180024bc5  jz      short loc_180024BCC
0x180024bc7  mov     [r14], rdi
0x180024bca  jmp     short loc_180024BE0
0x180024bcc  test    rdi, rdi
0x180024bcf  jz      short loc_180024BE0
0x180024bd1  mov     rcx, rdi; hMem
0x180024bd4  call    cs:__imp_LocalFree
0x180024bdb  nop     dword ptr [rax+rax+00h]
0x180024be0  test    rsi, rsi
0x180024be3  jz      short loc_180024BEA
0x180024be5  mov     eax, [rbp+cbData]
0x180024be8  mov     [rsi], eax
0x180024bea  xor     eax, eax
0x180024bec  lea     r11, [rsp+60h+var_s0]
0x180024bf1  mov     rsi, [r11+28h]
0x180024bf5  cmp     ebx, 2
0x180024bf8  cmovnz  eax, ebx
0x180024bfb  mov     rbx, [r11+20h]
0x180024bff  mov     rsp, r11
0x180024c02  pop     r14
0x180024c04  pop     rdi
0x180024c05  pop     rbp
0x180024c06  retn
```
