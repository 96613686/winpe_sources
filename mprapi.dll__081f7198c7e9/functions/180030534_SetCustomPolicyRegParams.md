# SetCustomPolicyRegParams

- ea: `0x180030534`
- end: `0x180030641`
- name: `SetCustomPolicyRegParams`
- size: `269`
- prototype: `__int64 __fastcall(HKEY hKey, BYTE *lpData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180030b7c`
- `0x180031178`

## callees

- `0x180030534`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030568`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003058f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800305ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800305e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030608`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003062b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030568`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003058f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800305ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800305e1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180030608`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003062b`

## pseudocode

```c
LSTATUS __fastcall SetCustomPolicyRegParams(HKEY hKey, BYTE *lpData)
{
  LSTATUS result; // eax

  result = RegSetValueExW(hKey, L"EncryptionMethod", 0, 4u, lpData + 4, 4u);
  if ( !result )
  {
    result = RegSetValueExW(hKey, L"IntegrityMethod", 0, 4u, lpData, 4u);
    if ( !result )
    {
      result = RegSetValueExW(hKey, L"CipherTransformConstant", 0, 4u, lpData + 8, 4u);
      if ( !result )
      {
        result = RegSetValueExW(hKey, L"AuthTransformConstant", 0, 4u, lpData + 12, 4u);
        if ( !result )
        {
          RegSetValueExW(hKey, L"PfsGroup", 0, 4u, lpData + 16, 4u);
          return RegSetValueExW(hKey, L"DHGroup", 0, 4u, lpData + 20, 4u);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180030534  mov     [rsp+arg_0], rbx
0x180030539  mov     [rsp+arg_8], rsi
0x18003053e  push    rdi
0x18003053f  sub     rsp, 30h
0x180030543  lea     rax, [rdx+4]
0x180030547  mov     esi, 4
0x18003054c  mov     rbx, rdx
0x18003054f  mov     [rsp+38h+cbData], esi; cbData
0x180030553  mov     r9d, esi; dwType
0x180030556  mov     [rsp+38h+lpData], rax; lpData
0x18003055b  xor     r8d, r8d; Reserved
0x18003055e  lea     rdx, aEncryptionmeth; "EncryptionMethod"
0x180030565  mov     rdi, rcx
0x180030568  call    cs:__imp_RegSetValueExW
0x18003056e  test    eax, eax
0x180030570  jnz     loc_180030631
0x180030576  mov     [rsp+38h+cbData], esi; cbData
0x18003057a  lea     rdx, aIntegritymetho; "IntegrityMethod"
0x180030581  mov     r9d, esi; dwType
0x180030584  mov     [rsp+38h+lpData], rbx; lpData
0x180030589  xor     r8d, r8d; Reserved
0x18003058c  mov     rcx, rdi; hKey
0x18003058f  call    cs:__imp_RegSetValueExW
0x180030595  test    eax, eax
0x180030597  jnz     loc_180030631
0x18003059d  lea     rax, [rbx+8]
0x1800305a1  mov     [rsp+38h+cbData], esi; cbData
0x1800305a5  mov     r9d, esi; dwType
0x1800305a8  mov     [rsp+38h+lpData], rax; lpData
0x1800305ad  xor     r8d, r8d; Reserved
0x1800305b0  lea     rdx, aCiphertransfor; "CipherTransformConstant"
0x1800305b7  mov     rcx, rdi; hKey
0x1800305ba  call    cs:__imp_RegSetValueExW
0x1800305c0  test    eax, eax
0x1800305c2  jnz     short loc_180030631
0x1800305c4  lea     rax, [rbx+0Ch]
0x1800305c8  mov     [rsp+38h+cbData], esi; cbData
0x1800305cc  mov     r9d, esi; dwType
0x1800305cf  mov     [rsp+38h+lpData], rax; lpData
0x1800305d4  xor     r8d, r8d; Reserved
0x1800305d7  lea     rdx, aAuthtransformc; "AuthTransformConstant"
0x1800305de  mov     rcx, rdi; hKey
0x1800305e1  call    cs:__imp_RegSetValueExW
0x1800305e7  test    eax, eax
0x1800305e9  jnz     short loc_180030631
0x1800305eb  lea     rax, [rbx+10h]
0x1800305ef  mov     [rsp+38h+cbData], esi; cbData
0x1800305f3  mov     r9d, esi; dwType
0x1800305f6  mov     [rsp+38h+lpData], rax; lpData
0x1800305fb  xor     r8d, r8d; Reserved
0x1800305fe  lea     rdx, aPfsgroup; "PfsGroup"
0x180030605  mov     rcx, rdi; hKey
0x180030608  call    cs:__imp_RegSetValueExW
0x18003060e  lea     rax, [rbx+14h]
0x180030612  mov     [rsp+38h+cbData], esi; cbData
0x180030616  mov     r9d, esi; dwType
0x180030619  mov     [rsp+38h+lpData], rax; lpData
0x18003061e  xor     r8d, r8d; Reserved
0x180030621  lea     rdx, aDhgroup; "DHGroup"
0x180030628  mov     rcx, rdi; hKey
0x18003062b  call    cs:__imp_RegSetValueExW
0x180030631  mov     rbx, [rsp+38h+arg_0]
0x180030636  mov     rsi, [rsp+38h+arg_8]
0x18003063b  add     rsp, 30h
0x18003063f  pop     rdi
0x180030640  retn
```
