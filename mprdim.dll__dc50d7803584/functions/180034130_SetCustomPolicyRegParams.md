# SetCustomPolicyRegParams

- ea: `0x180034130`
- end: `0x18003423d`
- name: `SetCustomPolicyRegParams`
- size: `269`
- prototype: `__int64 __fastcall(HKEY hKey, BYTE *lpData)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003472c`

## callees

- `0x180034130`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180034164`
- `ADVAPI32!RegSetValueExW` at `0x18003418b`
- `ADVAPI32!RegSetValueExW` at `0x1800341b6`
- `ADVAPI32!RegSetValueExW` at `0x1800341dd`
- `ADVAPI32!RegSetValueExW` at `0x180034204`
- `ADVAPI32!RegSetValueExW` at `0x180034227`
- `ADVAPI32!RegSetValueExW` at `0x180034164`
- `ADVAPI32!RegSetValueExW` at `0x18003418b`
- `ADVAPI32!RegSetValueExW` at `0x1800341b6`
- `ADVAPI32!RegSetValueExW` at `0x1800341dd`
- `ADVAPI32!RegSetValueExW` at `0x180034204`
- `ADVAPI32!RegSetValueExW` at `0x180034227`

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
0x180034130  mov     [rsp+arg_0], rbx
0x180034135  mov     [rsp+arg_8], rsi
0x18003413a  push    rdi
0x18003413b  sub     rsp, 30h
0x18003413f  lea     rax, [rdx+4]
0x180034143  mov     esi, 4
0x180034148  mov     rbx, rdx
0x18003414b  mov     [rsp+38h+cbData], esi; cbData
0x18003414f  mov     r9d, esi; dwType
0x180034152  mov     [rsp+38h+lpData], rax; lpData
0x180034157  xor     r8d, r8d; Reserved
0x18003415a  lea     rdx, aEncryptionmeth; "EncryptionMethod"
0x180034161  mov     rdi, rcx
0x180034164  call    cs:__imp_RegSetValueExW
0x18003416a  test    eax, eax
0x18003416c  jnz     loc_18003422D
0x180034172  mov     [rsp+38h+cbData], esi; cbData
0x180034176  lea     rdx, aIntegritymetho; "IntegrityMethod"
0x18003417d  mov     r9d, esi; dwType
0x180034180  mov     [rsp+38h+lpData], rbx; lpData
0x180034185  xor     r8d, r8d; Reserved
0x180034188  mov     rcx, rdi; hKey
0x18003418b  call    cs:__imp_RegSetValueExW
0x180034191  test    eax, eax
0x180034193  jnz     loc_18003422D
0x180034199  lea     rax, [rbx+8]
0x18003419d  mov     [rsp+38h+cbData], esi; cbData
0x1800341a1  mov     r9d, esi; dwType
0x1800341a4  mov     [rsp+38h+lpData], rax; lpData
0x1800341a9  xor     r8d, r8d; Reserved
0x1800341ac  lea     rdx, aCiphertransfor; "CipherTransformConstant"
0x1800341b3  mov     rcx, rdi; hKey
0x1800341b6  call    cs:__imp_RegSetValueExW
0x1800341bc  test    eax, eax
0x1800341be  jnz     short loc_18003422D
0x1800341c0  lea     rax, [rbx+0Ch]
0x1800341c4  mov     [rsp+38h+cbData], esi; cbData
0x1800341c8  mov     r9d, esi; dwType
0x1800341cb  mov     [rsp+38h+lpData], rax; lpData
0x1800341d0  xor     r8d, r8d; Reserved
0x1800341d3  lea     rdx, aAuthtransformc; "AuthTransformConstant"
0x1800341da  mov     rcx, rdi; hKey
0x1800341dd  call    cs:__imp_RegSetValueExW
0x1800341e3  test    eax, eax
0x1800341e5  jnz     short loc_18003422D
0x1800341e7  lea     rax, [rbx+10h]
0x1800341eb  mov     [rsp+38h+cbData], esi; cbData
0x1800341ef  mov     r9d, esi; dwType
0x1800341f2  mov     [rsp+38h+lpData], rax; lpData
0x1800341f7  xor     r8d, r8d; Reserved
0x1800341fa  lea     rdx, aPfsgroup; "PfsGroup"
0x180034201  mov     rcx, rdi; hKey
0x180034204  call    cs:__imp_RegSetValueExW
0x18003420a  lea     rax, [rbx+14h]
0x18003420e  mov     [rsp+38h+cbData], esi; cbData
0x180034212  mov     r9d, esi; dwType
0x180034215  mov     [rsp+38h+lpData], rax; lpData
0x18003421a  xor     r8d, r8d; Reserved
0x18003421d  lea     rdx, aDhgroup; "DHGroup"
0x180034224  mov     rcx, rdi; hKey
0x180034227  call    cs:__imp_RegSetValueExW
0x18003422d  mov     rbx, [rsp+38h+arg_0]
0x180034232  mov     rsi, [rsp+38h+arg_8]
0x180034237  add     rsp, 30h
0x18003423b  pop     rdi
0x18003423c  retn
```
