# GetCallbackList

- ea: `0x18003ed18`
- end: `0x18003ef0c`
- name: `GetCallbackList`
- size: `500`
- prototype: `void *__fastcall(HKEY hKey, __int64 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18003f408`

## callees

- `0x18003b57c`
- `0x18003b5bc`
- `0x18003b6b8`
- `0x18003b898`
- `0x18003e89c`
- `0x18003ed18`
- `0x18004146c`
- `0x1800416b0`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003ee61`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003ee77`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003ee82`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003ee61`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003ee77`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18003ee82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eda0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003edf9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eda0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003edf9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eecd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003ee6c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003eecd`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003eeb7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18003eeb7`

## pseudocode

```c
void *__fastcall GetCallbackList(HKEY hKey, __int64 **a2)
{
  void *result; // rax
  __int64 v5; // rbx
  DWORD v6; // esi
  DWORD i; // edx
  _QWORD *CallbackNode; // rax
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
  result = DtlCreateList();
  v5 = (__int64)result;
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
              CallbackNode = (_QWORD *)CreateCallbackNode(
                                         (STRSAFE_LPCWSTR)v16,
                                         (STRSAFE_LPCWSTR)v15,
                                         (STRSAFE_LPCWSTR)hMem,
                                         v11);
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
    result = DtlDestroyList(*a2, (void (__fastcall *)(__int64))DestroyCallbackNode);
    *a2 = (__int64 *)v5;
  }
  return result;
}

```

## disassembly

```asm
0x18003ed18  mov     [rsp-8+arg_10], rbx
0x18003ed1d  mov     [rsp-8+arg_18], rsi
0x18003ed22  push    rbp
0x18003ed23  push    rdi
0x18003ed24  push    r14
0x18003ed26  lea     rbp, [rsp-0B0h]
0x18003ed2e  sub     rsp, 1B0h
0x18003ed35  mov     rax, cs:__security_cookie
0x18003ed3c  xor     rax, rsp
0x18003ed3f  mov     [rbp+0C0h+var_20], rax
0x18003ed46  xor     r14d, r14d
0x18003ed49  mov     rdi, rdx
0x18003ed4c  mov     [rsp+1C0h+var_160], r14
0x18003ed51  mov     rsi, rcx
0x18003ed54  mov     [rsp+1C0h+var_158], r14
0x18003ed59  mov     [rsp+1C0h+hMem], r14
0x18003ed5e  mov     [rsp+1C0h+var_17C], r14d
0x18003ed63  mov     [rsp+1C0h+cchName], r14d
0x18003ed68  mov     [rsp+1C0h+hKey], r14
0x18003ed6d  mov     [rsp+1C0h+var_170], r14
0x18003ed72  call    DtlCreateList
0x18003ed77  mov     rbx, rax
0x18003ed7a  test    rax, rax
0x18003ed7d  jz      loc_18003EEE5
0x18003ed83  lea     rax, [rsp+1C0h+hKey]
0x18003ed88  mov     r9d, 20019h; samDesired
0x18003ed8e  xor     r8d, r8d; ulOptions
0x18003ed91  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18003ed96  lea     rdx, aCallback; "Callback"
0x18003ed9d  mov     rcx, rsi; hKey
0x18003eda0  call    cs:__imp_RegOpenKeyExW
0x18003eda6  test    eax, eax
0x18003eda8  jnz     loc_18003EED3
0x18003edae  mov     esi, r14d
0x18003edb1  xor     edx, edx
0x18003edb3  jmp     loc_18003EE8C
0x18003edb8  test    eax, eax
0x18003edba  jnz     loc_18003EE88
0x18003edc0  lea     r8, [rsp+1C0h+var_158]
0x18003edc5  lea     rdx, [rsp+1C0h+var_160]
0x18003edca  lea     rcx, [rsp+1C0h+SubKey]
0x18003edcf  call    DeviceAndPortFromPsz
0x18003edd4  test    eax, eax
0x18003edd6  jz      loc_18003EE88
0x18003eddc  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18003ede1  lea     rax, [rsp+1C0h+var_170]
0x18003ede6  mov     r9d, 20019h; samDesired
0x18003edec  mov     [rsp+1C0h+phkResult], rax; phkResult
0x18003edf1  xor     r8d, r8d; ulOptions
0x18003edf4  lea     rdx, [rsp+1C0h+SubKey]; lpSubKey
0x18003edf9  call    cs:__imp_RegOpenKeyExW
0x18003edff  test    eax, eax
0x18003ee01  jnz     short loc_18003EE72
0x18003ee03  mov     rcx, [rsp+1C0h+var_170]
0x18003ee08  lea     r8, [rsp+1C0h+var_17C]
0x18003ee0d  lea     rdx, aDevicetype; "DeviceType"
0x18003ee14  call    GetRegDword
0x18003ee19  mov     rcx, [rsp+1C0h+var_170]; hKey
0x18003ee1e  lea     r8, [rsp+1C0h+hMem]
0x18003ee23  lea     rdx, aNumber; "Number"
0x18003ee2a  call    GetRegSz
0x18003ee2f  test    eax, eax
0x18003ee31  jnz     short loc_18003EE67
0x18003ee33  mov     r9d, [rsp+1C0h+var_17C]
0x18003ee38  mov     r8, [rsp+1C0h+hMem]; STRSAFE_LPCWSTR
0x18003ee3d  mov     rdx, [rsp+1C0h+var_160]; STRSAFE_LPCWSTR
0x18003ee42  mov     rcx, [rsp+1C0h+var_158]; pszSrc
0x18003ee47  call    CreateCallbackNode
0x18003ee4c  test    rax, rax
0x18003ee4f  jz      short loc_18003EE5C
0x18003ee51  mov     rdx, rax
0x18003ee54  mov     rcx, rbx
0x18003ee57  call    DtlAddNodeLast
0x18003ee5c  mov     rcx, [rsp+1C0h+hMem]; hMem
0x18003ee61  call    cs:__imp_GlobalFree
0x18003ee67  mov     rcx, [rsp+1C0h+var_170]; hKey
0x18003ee6c  call    cs:__imp_RegCloseKey
0x18003ee72  mov     rcx, [rsp+1C0h+var_160]; hMem
0x18003ee77  call    cs:__imp_GlobalFree
0x18003ee7d  mov     rcx, [rsp+1C0h+var_158]; hMem
0x18003ee82  call    cs:__imp_GlobalFree
0x18003ee88  inc     esi
0x18003ee8a  mov     edx, esi; dwIndex
0x18003ee8c  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18003ee91  lea     r9, [rsp+1C0h+cchName]; lpcchName
0x18003ee96  mov     [rsp+1C0h+lpftLastWriteTime], r14; lpftLastWriteTime
0x18003ee9b  lea     r8, [rsp+1C0h+SubKey]; lpName
0x18003eea0  mov     [rsp+1C0h+lpcchClass], r14; lpcchClass
0x18003eea5  mov     [rsp+1C0h+lpClass], r14; lpClass
0x18003eeaa  mov     [rsp+1C0h+phkResult], r14; lpReserved
0x18003eeaf  mov     [rsp+1C0h+cchName], 94h
0x18003eeb7  call    cs:__imp_RegEnumKeyExW
0x18003eebd  cmp     eax, 103h
0x18003eec2  jnz     loc_18003EDB8
0x18003eec8  mov     rcx, [rsp+1C0h+hKey]; hKey
0x18003eecd  call    cs:__imp_RegCloseKey
0x18003eed3  mov     rcx, [rdi]; hMem
0x18003eed6  lea     rdx, DestroyCallbackNode
0x18003eedd  call    DtlDestroyList
0x18003eee2  mov     [rdi], rbx
0x18003eee5  mov     rcx, [rbp+0C0h+var_20]
0x18003eeec  xor     rcx, rsp; StackCookie
0x18003eeef  call    __security_check_cookie
0x18003eef4  lea     r11, [rsp+1C0h+var_10]
0x18003eefc  mov     rbx, [r11+30h]
0x18003ef00  mov     rsi, [r11+38h]
0x18003ef04  mov     rsp, r11
0x18003ef07  pop     r14
0x18003ef09  pop     rdi
0x18003ef0a  pop     rbp
0x18003ef0b  retn
```
