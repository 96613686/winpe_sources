# SetCustomPolicyRegParams

- ea: `0x18007392c`
- end: `0x180073a39`
- name: `SetCustomPolicyRegParams`
- size: `269`
- prototype: `__int64 __fastcall(HKEY hKey, BYTE *lpData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073f74`
- `0x18007419c`

## callees

- `0x18007392c`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180073960`
- `ADVAPI32!RegSetValueExW` at `0x180073987`
- `ADVAPI32!RegSetValueExW` at `0x1800739b2`
- `ADVAPI32!RegSetValueExW` at `0x1800739d9`
- `ADVAPI32!RegSetValueExW` at `0x180073a00`
- `ADVAPI32!RegSetValueExW` at `0x180073a23`
- `ADVAPI32!RegSetValueExW` at `0x180073960`
- `ADVAPI32!RegSetValueExW` at `0x180073987`
- `ADVAPI32!RegSetValueExW` at `0x1800739b2`
- `ADVAPI32!RegSetValueExW` at `0x1800739d9`
- `ADVAPI32!RegSetValueExW` at `0x180073a00`
- `ADVAPI32!RegSetValueExW` at `0x180073a23`

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
0x18007392c  mov     [rsp+arg_0], rbx
0x180073931  mov     [rsp+arg_8], rsi
0x180073936  push    rdi
0x180073937  sub     rsp, 30h
0x18007393b  lea     rax, [rdx+4]
0x18007393f  mov     esi, 4
0x180073944  mov     rbx, rdx
0x180073947  mov     [rsp+38h+cbData], esi; cbData
0x18007394b  mov     r9d, esi; dwType
0x18007394e  mov     [rsp+38h+lpData], rax; lpData
0x180073953  xor     r8d, r8d; Reserved
0x180073956  lea     rdx, aEncryptionmeth; "EncryptionMethod"
0x18007395d  mov     rdi, rcx
0x180073960  call    cs:__imp_RegSetValueExW
0x180073966  test    eax, eax
0x180073968  jnz     loc_180073A29
0x18007396e  mov     [rsp+38h+cbData], esi; cbData
0x180073972  lea     rdx, aIntegritymetho; "IntegrityMethod"
0x180073979  mov     r9d, esi; dwType
0x18007397c  mov     [rsp+38h+lpData], rbx; lpData
0x180073981  xor     r8d, r8d; Reserved
0x180073984  mov     rcx, rdi; hKey
0x180073987  call    cs:__imp_RegSetValueExW
0x18007398d  test    eax, eax
0x18007398f  jnz     loc_180073A29
0x180073995  lea     rax, [rbx+8]
0x180073999  mov     [rsp+38h+cbData], esi; cbData
0x18007399d  mov     r9d, esi; dwType
0x1800739a0  mov     [rsp+38h+lpData], rax; lpData
0x1800739a5  xor     r8d, r8d; Reserved
0x1800739a8  lea     rdx, aCiphertransfor; "CipherTransformConstant"
0x1800739af  mov     rcx, rdi; hKey
0x1800739b2  call    cs:__imp_RegSetValueExW
0x1800739b8  test    eax, eax
0x1800739ba  jnz     short loc_180073A29
0x1800739bc  lea     rax, [rbx+0Ch]
0x1800739c0  mov     [rsp+38h+cbData], esi; cbData
0x1800739c4  mov     r9d, esi; dwType
0x1800739c7  mov     [rsp+38h+lpData], rax; lpData
0x1800739cc  xor     r8d, r8d; Reserved
0x1800739cf  lea     rdx, aAuthtransformc; "AuthTransformConstant"
0x1800739d6  mov     rcx, rdi; hKey
0x1800739d9  call    cs:__imp_RegSetValueExW
0x1800739df  test    eax, eax
0x1800739e1  jnz     short loc_180073A29
0x1800739e3  lea     rax, [rbx+10h]
0x1800739e7  mov     [rsp+38h+cbData], esi; cbData
0x1800739eb  mov     r9d, esi; dwType
0x1800739ee  mov     [rsp+38h+lpData], rax; lpData
0x1800739f3  xor     r8d, r8d; Reserved
0x1800739f6  lea     rdx, aPfsgroup; "PfsGroup"
0x1800739fd  mov     rcx, rdi; hKey
0x180073a00  call    cs:__imp_RegSetValueExW
0x180073a06  lea     rax, [rbx+14h]
0x180073a0a  mov     [rsp+38h+cbData], esi; cbData
0x180073a0e  mov     r9d, esi; dwType
0x180073a11  mov     [rsp+38h+lpData], rax; lpData
0x180073a16  xor     r8d, r8d; Reserved
0x180073a19  lea     rdx, aDhgroup; "DHGroup"
0x180073a20  mov     rcx, rdi; hKey
0x180073a23  call    cs:__imp_RegSetValueExW
0x180073a29  mov     rbx, [rsp+38h+arg_0]
0x180073a2e  mov     rsi, [rsp+38h+arg_8]
0x180073a33  add     rsp, 30h
0x180073a37  pop     rdi
0x180073a38  retn
```
