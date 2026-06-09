# GetCallbackList

- ea: `0x18005a640`
- end: `0x18005a834`
- name: `GetCallbackList`
- size: `500`
- prototype: `__int64 __fastcall(HKEY hKey)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18005aa0c`

## callees

- `0x18005a220`
- `0x18005a640`
- `0x18005bcb0`
- `0x18005d5f8`
- `0x18005d638`
- `0x18005d748`
- `0x18005d85c`
- `0x18005da00`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005a7df`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18005a7df`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a6c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a721`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a6c8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005a721`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a7f5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a794`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18005a7f5`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005a789`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005a79f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005a7aa`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005a789`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005a79f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18005a7aa`

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
0x18005a640  mov     [rsp-8+arg_10], rbx
0x18005a645  mov     [rsp-8+arg_18], rsi
0x18005a64a  push    rbp
0x18005a64b  push    rdi
0x18005a64c  push    r14
0x18005a64e  lea     rbp, [rsp-0B0h]
0x18005a656  sub     rsp, 1B0h
0x18005a65d  mov     rax, cs:__security_cookie
0x18005a664  xor     rax, rsp
0x18005a667  mov     [rbp+0C0h+var_20], rax
0x18005a66e  xor     r14d, r14d
0x18005a671  mov     rdi, rdx
0x18005a674  mov     [rsp+1C0h+var_160], r14
0x18005a679  mov     rsi, rcx
0x18005a67c  mov     [rsp+1C0h+var_158], r14
0x18005a681  mov     [rsp+1C0h+hMem], r14
0x18005a686  mov     [rsp+1C0h+var_17C], r14d
0x18005a68b  mov     [rsp+1C0h+cchName], r14d
0x18005a690  mov     [rsp+1C0h+hKey], r14
0x18005a695  mov     [rsp+1C0h+var_170], r14
0x18005a69a  call    DtlCreateList
0x18005a69f  mov     rbx, rax
0x18005a6a2  test    rax, rax
0x18005a6a5  jz      loc_18005A80D
0x18005a6ab  lea     rax, [rsp+1C0h+hKey]
0x18005a6b0  mov     r9d, 20019h; samDesired
0x18005a6b6  xor     r8d, r8d; ulOptions
0x18005a6b9  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18005a6be  lea     rdx, aCallback; "Callback"
0x18005a6c5  mov     rcx, rsi; hKey
0x18005a6c8  call    cs:__imp_RegOpenKeyExW
0x18005a6ce  test    eax, eax
0x18005a6d0  jnz     loc_18005A7FB
0x18005a6d6  mov     esi, r14d
0x18005a6d9  xor     edx, edx
0x18005a6db  jmp     loc_18005A7B4
0x18005a6e0  test    eax, eax
0x18005a6e2  jnz     loc_18005A7B0
0x18005a6e8  lea     r8, [rsp+1C0h+var_158]
0x18005a6ed  lea     rdx, [rsp+1C0h+var_160]
0x18005a6f2  lea     rcx, [rsp+1C0h+SubKey]
0x18005a6f7  call    DeviceAndPortFromPsz
0x18005a6fc  test    eax, eax
0x18005a6fe  jz      loc_18005A7B0
0x18005a704  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18005a709  lea     rax, [rsp+1C0h+var_170]
0x18005a70e  mov     r9d, 20019h; samDesired
0x18005a714  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18005a719  xor     r8d, r8d; ulOptions
0x18005a71c  lea     rdx, [rsp+1C0h+SubKey]; lpSubKey
0x18005a721  call    cs:__imp_RegOpenKeyExW
0x18005a727  test    eax, eax
0x18005a729  jnz     short loc_18005A79A
0x18005a72b  mov     rcx, [rsp+1C0h+var_170]
0x18005a730  lea     r8, [rsp+1C0h+var_17C]
0x18005a735  lea     rdx, aDevicetype; "DeviceType"
0x18005a73c  call    GetRegDword
0x18005a741  mov     rcx, [rsp+1C0h+var_170]; hKey
0x18005a746  lea     r8, [rsp+1C0h+hMem]
0x18005a74b  lea     rdx, aNumber; "Number"
0x18005a752  call    GetRegSz
0x18005a757  test    eax, eax
0x18005a759  jnz     short loc_18005A78F
0x18005a75b  mov     r9d, [rsp+1C0h+var_17C]
0x18005a760  mov     r8, [rsp+1C0h+hMem]; STRSAFE_LPCWSTR
0x18005a765  mov     rdx, [rsp+1C0h+var_160]; STRSAFE_LPCWSTR
0x18005a76a  mov     rcx, [rsp+1C0h+var_158]; pszSrc
0x18005a76f  call    CreateCallbackNode
0x18005a774  test    rax, rax
0x18005a777  jz      short loc_18005A784
0x18005a779  mov     rdx, rax
0x18005a77c  mov     rcx, rbx
0x18005a77f  call    DtlAddNodeLast
0x18005a784  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18005a789  call    cs:__imp_GlobalFree
0x18005a78f  mov     rcx, [rsp+1C0h+var_170]; hKey
0x18005a794  call    cs:__imp_RegCloseKey
0x18005a79a  mov     rcx, [rsp+1C0h+var_160]; hMem
0x18005a79f  call    cs:__imp_GlobalFree
0x18005a7a5  mov     rcx, [rsp+1C0h+var_158]; hMem
0x18005a7aa  call    cs:__imp_GlobalFree
0x18005a7b0  inc     esi
0x18005a7b2  mov     edx, esi; dwIndex
0x18005a7b4  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18005a7b9  lea     r9, [rsp+1C0h+cchName]; lpcchName
0x18005a7be  mov     [rsp+1C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18005a7c3  lea     r8, [rsp+1C0h+SubKey]; lpName
0x18005a7c8  mov     [rsp+1C0h+lpcchClass], r14; lpcchClass
0x18005a7cd  mov     [rsp+1C0h+lpClass], r14; lpClass
0x18005a7d2  mov     [rsp+1C0h+phkResult], r14; lpReserved
0x18005a7d7  mov     [rsp+1C0h+cchName], 94h
0x18005a7df  call    cs:__imp_RegEnumKeyExW
0x18005a7e5  cmp     eax, 103h
0x18005a7ea  jnz     loc_18005A6E0
0x18005a7f0  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18005a7f5  call    cs:__imp_RegCloseKey
0x18005a7fb  mov     rcx, [rdi]; hMem
0x18005a7fe  lea     rdx, DestroyCallbackNode
0x18005a805  call    DtlDestroyList
0x18005a80a  mov     [rdi], rbx
0x18005a80d  mov     rcx, [rbp+0C0h+var_20]
0x18005a814  xor     rcx, rsp; StackCookie
0x18005a817  call    __security_check_cookie
0x18005a81c  lea     r11, [rsp+1C0h+var_10]
0x18005a824  mov     rbx, [r11+30h]
0x18005a828  mov     rsi, [r11+38h]
0x18005a82c  mov     rsp, r11
0x18005a82f  pop     r14
0x18005a831  pop     rdi
0x18005a832  pop     rbp
0x18005a833  retn
```
