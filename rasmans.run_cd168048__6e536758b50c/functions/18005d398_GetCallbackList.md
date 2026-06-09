# GetCallbackList

- ea: `0x18005d398`
- end: `0x18005d5bd`
- name: `GetCallbackList`
- size: `549`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18005d988`

## callees

- `0x18005cef4`
- `0x18005d398`
- `0x18005eba8`
- `0x1800606cc`
- `0x18006070c`
- `0x180060830`
- `0x180060954`
- `0x180060b20`
- `0x1800e8ef0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d420`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d47f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d420`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005d47f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d4fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d577`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d4fe`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005d577`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005d55b`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005d55b`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d4ed`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d50f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d520`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d4ed`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d50f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005d520`

## pseudocode

```c
__int64 __fastcall GetCallbackList(HKEY hKey, HGLOBAL *a2)
{
  __int64 result; // rax
  __int64 v5; // rbx
  DWORD v6; // esi
  DWORD i; // edx
  __int64 CallbackNode; // rax
  LSTATUS v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  int v11; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKeya; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-B0h] BYREF
  HGLOBAL hMem; // [rsp+58h] [rbp-A8h]
  HGLOBAL v15; // [rsp+60h] [rbp-A0h] BYREF
  HGLOBAL v16; // [rsp+68h] [rbp-98h] BYREF
  WCHAR SubKey[152]; // [rsp+70h] [rbp-90h] BYREF

  v15 = 0;
  v16 = 0;
  hMem = 0;
  v11 = 0;
  cchName = 0;
  hKeya = 0;
  phkResult = 0;
  result = DtlCreateList(hKey);
  v5 = result;
  if ( result )
  {
    if ( !RegOpenKeyExW(hKey, L"Callback", 0, 0x20019u, &hKeya) )
    {
      v6 = 0;
      for ( i = 0; ; i = v6 )
      {
        cchName = 148;
        v9 = RegEnumKeyExW(hKeya, i, SubKey, &cchName, 0, 0, 0, 0);
        if ( v9 == 259 )
          break;
        if ( !v9 && (unsigned int)DeviceAndPortFromPsz(SubKey, &v15, &v16) )
        {
          if ( !RegOpenKeyExW(hKeya, SubKey, 0, 0x20019u, &phkResult) )
          {
            GetRegDword(phkResult, L"DeviceType", &v11);
            if ( !(unsigned int)GetRegSz(phkResult, L"Number") )
            {
              CallbackNode = CreateCallbackNode((STRSAFE_LPCWSTR)v16, (STRSAFE_LPCWSTR)v15, (STRSAFE_LPCWSTR)hMem);
              if ( CallbackNode )
                DtlAddNodeLast(v5, CallbackNode);
              GlobalFree(hMem);
            }
            RegCloseKey(phkResult);
          }
          GlobalFree(v15);
          GlobalFree(v16);
        }
        ++v6;
      }
      RegCloseKey(hKeya);
    }
    result = DtlDestroyList(*a2);
    *a2 = (HGLOBAL)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18005d398  mov     [rsp-8+arg_10], rbx
0x18005d39d  mov     [rsp-8+arg_18], rsi
0x18005d3a2  push    rbp
0x18005d3a3  push    rdi
0x18005d3a4  push    r14
0x18005d3a6  lea     rbp, [rsp-0B0h]
0x18005d3ae  sub     rsp, 1B0h
0x18005d3b5  mov     rax, cs:__security_cookie
0x18005d3bc  xor     rax, rsp
0x18005d3bf  mov     [rbp+0C0h+var_20], rax
0x18005d3c6  xor     r14d, r14d
0x18005d3c9  mov     rdi, rdx
0x18005d3cc  mov     [rsp+1C0h+var_160], r14
0x18005d3d1  mov     rsi, rcx
0x18005d3d4  mov     [rsp+1C0h+var_158], r14
0x18005d3d9  mov     [rsp+1C0h+hMem], r14
0x18005d3de  mov     [rsp+1C0h+var_17C], r14d
0x18005d3e3  mov     [rsp+1C0h+cchName], r14d
0x18005d3e8  mov     [rsp+1C0h+hKey], r14
0x18005d3ed  mov     [rsp+1C0h+var_170], r14
0x18005d3f2  call    DtlCreateList
0x18005d3f7  mov     rbx, rax
0x18005d3fa  test    rax, rax
0x18005d3fd  jz      loc_18005D595
0x18005d403  lea     rax, [rsp+1C0h+hKey]
0x18005d408  mov     r9d, 20019h; samDesired
0x18005d40e  xor     r8d, r8d; ulOptions
0x18005d411  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18005d416  lea     rdx, aCallback; "Callback"
0x18005d41d  mov     rcx, rsi; hKey
0x18005d420  call    cs:__imp_RegOpenKeyExW
0x18005d427  nop     dword ptr [rax+rax+00h]
0x18005d42c  test    eax, eax
0x18005d42e  jnz     loc_18005D583
0x18005d434  mov     esi, r14d
0x18005d437  xor     edx, edx
0x18005d439  jmp     loc_18005D530
0x18005d43e  test    eax, eax
0x18005d440  jnz     loc_18005D52C
0x18005d446  lea     r8, [rsp+1C0h+var_158]
0x18005d44b  lea     rdx, [rsp+1C0h+var_160]
0x18005d450  lea     rcx, [rsp+1C0h+SubKey]
0x18005d455  call    DeviceAndPortFromPsz
0x18005d45a  test    eax, eax
0x18005d45c  jz      loc_18005D52C
0x18005d462  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18005d467  lea     rax, [rsp+1C0h+var_170]
0x18005d46c  mov     r9d, 20019h; samDesired
0x18005d472  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18005d477  xor     r8d, r8d; ulOptions
0x18005d47a  lea     rdx, [rsp+1C0h+SubKey]; lpSubKey
0x18005d47f  call    cs:__imp_RegOpenKeyExW
0x18005d486  nop     dword ptr [rax+rax+00h]
0x18005d48b  test    eax, eax
0x18005d48d  jnz     short loc_18005D50A
0x18005d48f  mov     rcx, [rsp+1C0h+var_170]
0x18005d494  lea     r8, [rsp+1C0h+var_17C]
0x18005d499  lea     rdx, aDevicetype; "DeviceType"
0x18005d4a0  call    GetRegDword
0x18005d4a5  mov     rcx, [rsp+1C0h+var_170]; hKey
0x18005d4aa  lea     r8, [rsp+1C0h+hMem]
0x18005d4af  lea     rdx, aNumber; "Number"
0x18005d4b6  call    GetRegSz
0x18005d4bb  test    eax, eax
0x18005d4bd  jnz     short loc_18005D4F9
0x18005d4bf  mov     r9d, [rsp+1C0h+var_17C]
0x18005d4c4  mov     r8, [rsp+1C0h+hMem]; STRSAFE_LPCWSTR
0x18005d4c9  mov     rdx, [rsp+1C0h+var_160]; STRSAFE_LPCWSTR
0x18005d4ce  mov     rcx, [rsp+1C0h+var_158]; pszSrc
0x18005d4d3  call    CreateCallbackNode
0x18005d4d8  test    rax, rax
0x18005d4db  jz      short loc_18005D4E8
0x18005d4dd  mov     rdx, rax
0x18005d4e0  mov     rcx, rbx
0x18005d4e3  call    DtlAddNodeLast
0x18005d4e8  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18005d4ed  call    cs:__imp_GlobalFree
0x18005d4f4  nop     dword ptr [rax+rax+00h]
0x18005d4f9  mov     rcx, [rsp+1C0h+var_170]; hKey
0x18005d4fe  call    cs:__imp_RegCloseKey
0x18005d505  nop     dword ptr [rax+rax+00h]
0x18005d50a  mov     rcx, [rsp+1C0h+var_160]; hMem
0x18005d50f  call    cs:__imp_GlobalFree
0x18005d516  nop     dword ptr [rax+rax+00h]
0x18005d51b  mov     rcx, [rsp+1C0h+var_158]; hMem
0x18005d520  call    cs:__imp_GlobalFree
0x18005d527  nop     dword ptr [rax+rax+00h]
0x18005d52c  inc     esi
0x18005d52e  mov     edx, esi; dwIndex
0x18005d530  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18005d535  lea     r9, [rsp+1C0h+cchName]; lpcchName
0x18005d53a  mov     [rsp+1C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18005d53f  lea     r8, [rsp+1C0h+SubKey]; lpName
0x18005d544  mov     [rsp+1C0h+lpcchClass], r14; lpcchClass
0x18005d549  mov     [rsp+1C0h+lpClass], r14; lpClass
0x18005d54e  mov     [rsp+1C0h+phkResult], r14; lpReserved
0x18005d553  mov     [rsp+1C0h+cchName], 94h
0x18005d55b  call    cs:__imp_RegEnumKeyExW
0x18005d562  nop     dword ptr [rax+rax+00h]
0x18005d567  cmp     eax, 103h
0x18005d56c  jnz     loc_18005D43E
0x18005d572  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18005d577  call    cs:__imp_RegCloseKey
0x18005d57e  nop     dword ptr [rax+rax+00h]
0x18005d583  mov     rcx, [rdi]; hMem
0x18005d586  lea     rdx, DestroyCallbackNode
0x18005d58d  call    DtlDestroyList
0x18005d592  mov     [rdi], rbx
0x18005d595  mov     rcx, [rbp+0C0h+var_20]
0x18005d59c  xor     rcx, rsp; StackCookie
0x18005d59f  call    __security_check_cookie
0x18005d5a4  lea     r11, [rsp+1C0h+var_10]
0x18005d5ac  mov     rbx, [r11+30h]
0x18005d5b0  mov     rsi, [r11+38h]
0x18005d5b4  mov     rsp, r11
0x18005d5b7  pop     r14
0x18005d5b9  pop     rdi
0x18005d5ba  pop     rbp
0x18005d5bb  retn
```
