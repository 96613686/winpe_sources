# ReadDH2048_AES256RegValue

- ea: `0x180081b84`
- end: `0x180081c31`
- name: `ReadDH2048_AES256RegValue`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18007dedc`

## callees

- `0x180081b84`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180081c22`
- `ADVAPI32!RegCloseKey` at `0x180081c22`
- `ADVAPI32!RegOpenKeyExA` at `0x180081bca`
- `ADVAPI32!RegOpenKeyExA` at `0x180081bca`
- `ADVAPI32!RegQueryValueExA` at `0x180081bf8`
- `ADVAPI32!RegQueryValueExA` at `0x180081bf8`

## string_xrefs

- `0x180081bae`: `System\CurrentControlSet\Services\rasman\parameters`

## pseudocode

```c
__int64 ReadDH2048_AES256RegValue()
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD Type; // [rsp+48h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 4;
  Data = 0;
  if ( !RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\parameters", 0, 1u, &hKey)
    && (RegQueryValueExA(hKey, "NegotiateDH2048_AES256", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 || Data - 1 > 1) )
  {
    Data = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x180081b84  push    rbp
0x180081b86  mov     rbp, rsp
0x180081b89  sub     rsp, 30h
0x180081b8d  lea     rax, [rbp+hKey]
0x180081b91  mov     [rbp+hKey], 0
0x180081b99  mov     r9d, 1; samDesired
0x180081b9f  mov     [rsp+30h+phkResult], rax; phkResult
0x180081ba4  xor     r8d, r8d; ulOptions
0x180081ba7  mov     [rbp+Type], 0
0x180081bae  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Services\\ra"...
0x180081bb5  mov     [rbp+cbData], 4
0x180081bbc  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180081bc3  mov     [rbp+Data], 0
0x180081bca  call    cs:__imp_RegOpenKeyExA
0x180081bd0  test    eax, eax
0x180081bd2  jnz     short loc_180081C19
0x180081bd4  mov     rcx, [rbp+hKey]; hKey
0x180081bd8  lea     rax, [rbp+cbData]
0x180081bdc  mov     [rsp+30h+lpcbData], rax; lpcbData
0x180081be1  lea     r9, [rbp+Type]; lpType
0x180081be5  lea     rax, [rbp+Data]
0x180081be9  xor     r8d, r8d; lpReserved
0x180081bec  lea     rdx, aNegotiatedh204; "NegotiateDH2048_AES256"
0x180081bf3  mov     [rsp+30h+phkResult], rax; lpData
0x180081bf8  call    cs:__imp_RegQueryValueExA
0x180081bfe  test    eax, eax
0x180081c00  jnz     short loc_180081C12
0x180081c02  cmp     [rbp+Type], 4
0x180081c06  jnz     short loc_180081C12
0x180081c08  mov     eax, [rbp+Data]
0x180081c0b  dec     eax
0x180081c0d  cmp     eax, 1
0x180081c10  jbe     short loc_180081C19
0x180081c12  mov     [rbp+Data], 0
0x180081c19  mov     rcx, [rbp+hKey]; hKey
0x180081c1d  test    rcx, rcx
0x180081c20  jz      short loc_180081C28
0x180081c22  call    cs:__imp_RegCloseKey
0x180081c28  mov     eax, [rbp+Data]
0x180081c2b  add     rsp, 30h
0x180081c2f  pop     rbp
0x180081c30  retn
```
