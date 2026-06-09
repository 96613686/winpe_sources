# SetCustomPolicyRegParams

- ea: `0x1800774b8`
- end: `0x1800775ea`
- name: `SetCustomPolicyRegParams`
- size: `306`
- prototype: `__int64 __fastcall(HKEY hKey, BYTE *lpData)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180077bb8`
- `0x180077e2c`

## callees

- `0x1800774b8`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x1800774ec`
- `ADVAPI32!RegSetValueExW` at `0x180077519`
- `ADVAPI32!RegSetValueExW` at `0x18007754a`
- `ADVAPI32!RegSetValueExW` at `0x180077577`
- `ADVAPI32!RegSetValueExW` at `0x1800775a4`
- `ADVAPI32!RegSetValueExW` at `0x1800775cd`
- `ADVAPI32!RegSetValueExW` at `0x1800774ec`
- `ADVAPI32!RegSetValueExW` at `0x180077519`
- `ADVAPI32!RegSetValueExW` at `0x18007754a`
- `ADVAPI32!RegSetValueExW` at `0x180077577`
- `ADVAPI32!RegSetValueExW` at `0x1800775a4`
- `ADVAPI32!RegSetValueExW` at `0x1800775cd`

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
0x1800774b8  mov     [rsp+arg_0], rbx
0x1800774bd  mov     [rsp+arg_8], rsi
0x1800774c2  push    rdi
0x1800774c3  sub     rsp, 30h
0x1800774c7  lea     rax, [rdx+4]
0x1800774cb  mov     esi, 4
0x1800774d0  mov     rbx, rdx
0x1800774d3  mov     [rsp+38h+cbData], esi; cbData
0x1800774d7  mov     r9d, esi; dwType
0x1800774da  mov     [rsp+38h+lpData], rax; lpData
0x1800774df  xor     r8d, r8d; Reserved
0x1800774e2  lea     rdx, aEncryptionmeth; "EncryptionMethod"
0x1800774e9  mov     rdi, rcx
0x1800774ec  call    cs:__imp_RegSetValueExW
0x1800774f3  nop     dword ptr [rax+rax+00h]
0x1800774f8  test    eax, eax
0x1800774fa  jnz     loc_1800775D9
0x180077500  mov     [rsp+38h+cbData], esi; cbData
0x180077504  lea     rdx, aIntegritymetho; "IntegrityMethod"
0x18007750b  mov     r9d, esi; dwType
0x18007750e  mov     [rsp+38h+lpData], rbx; lpData
0x180077513  xor     r8d, r8d; Reserved
0x180077516  mov     rcx, rdi; hKey
0x180077519  call    cs:__imp_RegSetValueExW
0x180077520  nop     dword ptr [rax+rax+00h]
0x180077525  test    eax, eax
0x180077527  jnz     loc_1800775D9
0x18007752d  lea     rax, [rbx+8]
0x180077531  mov     [rsp+38h+cbData], esi; cbData
0x180077535  mov     r9d, esi; dwType
0x180077538  mov     [rsp+38h+lpData], rax; lpData
0x18007753d  xor     r8d, r8d; Reserved
0x180077540  lea     rdx, aCiphertransfor; "CipherTransformConstant"
0x180077547  mov     rcx, rdi; hKey
0x18007754a  call    cs:__imp_RegSetValueExW
0x180077551  nop     dword ptr [rax+rax+00h]
0x180077556  test    eax, eax
0x180077558  jnz     short loc_1800775D9
0x18007755a  lea     rax, [rbx+0Ch]
0x18007755e  mov     [rsp+38h+cbData], esi; cbData
0x180077562  mov     r9d, esi; dwType
0x180077565  mov     [rsp+38h+lpData], rax; lpData
0x18007756a  xor     r8d, r8d; Reserved
0x18007756d  lea     rdx, aAuthtransformc; "AuthTransformConstant"
0x180077574  mov     rcx, rdi; hKey
0x180077577  call    cs:__imp_RegSetValueExW
0x18007757e  nop     dword ptr [rax+rax+00h]
0x180077583  test    eax, eax
0x180077585  jnz     short loc_1800775D9
0x180077587  lea     rax, [rbx+10h]
0x18007758b  mov     [rsp+38h+cbData], esi; cbData
0x18007758f  mov     r9d, esi; dwType
0x180077592  mov     [rsp+38h+lpData], rax; lpData
0x180077597  xor     r8d, r8d; Reserved
0x18007759a  lea     rdx, aPfsgroup; "PfsGroup"
0x1800775a1  mov     rcx, rdi; hKey
0x1800775a4  call    cs:__imp_RegSetValueExW
0x1800775ab  nop     dword ptr [rax+rax+00h]
0x1800775b0  lea     rax, [rbx+14h]
0x1800775b4  mov     [rsp+38h+cbData], esi; cbData
0x1800775b8  mov     r9d, esi; dwType
0x1800775bb  mov     [rsp+38h+lpData], rax; lpData
0x1800775c0  xor     r8d, r8d; Reserved
0x1800775c3  lea     rdx, aDhgroup; "DHGroup"
0x1800775ca  mov     rcx, rdi; hKey
0x1800775cd  call    cs:__imp_RegSetValueExW
0x1800775d4  nop     dword ptr [rax+rax+00h]
0x1800775d9  mov     rbx, [rsp+38h+arg_0]
0x1800775de  mov     rsi, [rsp+38h+arg_8]
0x1800775e3  add     rsp, 30h
0x1800775e7  pop     rdi
0x1800775e8  retn
```
