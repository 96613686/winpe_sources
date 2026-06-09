# ReadDH2048_AES256RegValue

- ea: `0x18008769c`
- end: `0x180087750`
- name: `ReadDH2048_AES256RegValue`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x1800830ec`

## callees

- `0x18008769c`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18008773a`
- `ADVAPI32!RegCloseKey` at `0x18008773a`
- `ADVAPI32!RegOpenKeyExA` at `0x1800876d9`
- `ADVAPI32!RegOpenKeyExA` at `0x1800876d9`
- `ADVAPI32!RegQueryValueExA` at `0x18008770d`
- `ADVAPI32!RegQueryValueExA` at `0x18008770d`

## string_xrefs

- `0x1800876b2`: `System\CurrentControlSet\Services\rasman\parameters`

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
  Data = 0;
  cbData = 4;
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
0x18008769c  push    rbp
0x18008769e  mov     rbp, rsp
0x1800876a1  sub     rsp, 30h
0x1800876a5  and     [rbp+hKey], 0
0x1800876aa  lea     rax, [rbp+hKey]
0x1800876ae  and     [rbp+Type], 0
0x1800876b2  lea     rdx, aSystemCurrentc_16; "System\\CurrentControlSet\\Services\\ra"...
0x1800876b9  and     [rbp+Data], 0
0x1800876bd  mov     r9d, 1; samDesired
0x1800876c3  xor     r8d, r8d; ulOptions
0x1800876c6  mov     [rsp+30h+phkResult], rax; phkResult
0x1800876cb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800876d2  mov     [rbp+cbData], 4
0x1800876d9  call    cs:__imp_RegOpenKeyExA
0x1800876e0  nop     dword ptr [rax+rax+00h]
0x1800876e5  test    eax, eax
0x1800876e7  jnz     short loc_180087731
0x1800876e9  mov     rcx, [rbp+hKey]; hKey
0x1800876ed  lea     rax, [rbp+cbData]
0x1800876f1  mov     [rsp+30h+lpcbData], rax; lpcbData
0x1800876f6  lea     r9, [rbp+Type]; lpType
0x1800876fa  lea     rax, [rbp+Data]
0x1800876fe  xor     r8d, r8d; lpReserved
0x180087701  lea     rdx, aNegotiatedh204; "NegotiateDH2048_AES256"
0x180087708  mov     [rsp+30h+phkResult], rax; lpData
0x18008770d  call    cs:__imp_RegQueryValueExA
0x180087714  nop     dword ptr [rax+rax+00h]
0x180087719  test    eax, eax
0x18008771b  jnz     short loc_18008772D
0x18008771d  cmp     [rbp+Type], 4
0x180087721  jnz     short loc_18008772D
0x180087723  mov     eax, [rbp+Data]
0x180087726  dec     eax
0x180087728  cmp     eax, 1
0x18008772b  jbe     short loc_180087731
0x18008772d  and     [rbp+Data], 0
0x180087731  mov     rcx, [rbp+hKey]; hKey
0x180087735  test    rcx, rcx
0x180087738  jz      short loc_180087746
0x18008773a  call    cs:__imp_RegCloseKey
0x180087741  nop     dword ptr [rax+rax+00h]
0x180087746  mov     eax, [rbp+Data]
0x180087749  add     rsp, 30h
0x18008774d  pop     rbp
0x18008774e  retn
```
