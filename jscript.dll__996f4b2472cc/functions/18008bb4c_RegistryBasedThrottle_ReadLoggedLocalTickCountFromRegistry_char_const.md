# RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)

- ea: `0x18008bb4c`
- end: `0x18008bc41`
- name: `?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z`
- size: `245`
- prototype: `__int64 __fastcall(RegistryBasedThrottle *__hidden this, LPCSTR lpValueName)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800525d0`
- `0x18007ca60`
- `0x18007cba0`
- `0x18007cf28`

## callees

- `0x18008ae94`
- `0x18008bb4c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x18008bbc2`
- `ADVAPI32!RegOpenKeyExA` at `0x18008bbc2`
- `ADVAPI32!RegCloseKey` at `0x18008bc15`
- `ADVAPI32!RegCloseKey` at `0x18008bc25`
- `ADVAPI32!RegCloseKey` at `0x18008bc15`
- `ADVAPI32!RegCloseKey` at `0x18008bc25`
- `ADVAPI32!RegQueryValueExA` at `0x18008bbf5`
- `ADVAPI32!RegQueryValueExA` at `0x18008bbf5`
- `ADVAPI32!RegOpenCurrentUser` at `0x18008bb8d`
- `ADVAPI32!RegOpenCurrentUser` at `0x18008bb8d`

## pseudocode

```c
__int64 __fastcall RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(BYTE *this, LPCSTR lpValueName)
{
  unsigned int v4; // ebx
  const CHAR *CurrentProcessTickCountRegistryKey; // rax
  HKEY hKey; // [rsp+30h] [rbp-10h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-8h] BYREF
  DWORD cbData; // [rsp+70h] [rbp+30h] BYREF
  DWORD Type; // [rsp+78h] [rbp+38h] BYREF

  phkResult = 0;
  hKey = 0;
  cbData = 8;
  Type = 11;
  v4 = -2147467259;
  if ( !RegOpenCurrentUser(0x20119u, &phkResult) )
  {
    CurrentProcessTickCountRegistryKey = RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey((RegistryBasedThrottle *)this);
    if ( !RegOpenKeyExA(phkResult, CurrentProcessTickCountRegistryKey, 0, 0x20119u, &hKey) )
    {
      if ( !RegQueryValueExA(hKey, lpValueName, 0, &Type, this + 296, &cbData) )
      {
        *((_DWORD *)this + 76) = 1;
        v4 = 0;
      }
      RegCloseKey(hKey);
    }
    RegCloseKey(phkResult);
  }
  return v4;
}

```

## disassembly

```asm
0x18008bb4c  mov     [rsp-18h+arg_0], rbx
0x18008bb51  push    rbp
0x18008bb52  push    rsi
0x18008bb53  push    rdi
0x18008bb54  mov     rbp, rsp
0x18008bb57  sub     rsp, 40h
0x18008bb5b  mov     rsi, rdx
0x18008bb5e  mov     [rbp+phkResult], 0
0x18008bb66  mov     rdi, rcx
0x18008bb69  mov     [rbp+hKey], 0
0x18008bb71  lea     rdx, [rbp+phkResult]; phkResult
0x18008bb75  mov     [rbp+cbData], 8
0x18008bb7c  mov     ecx, 20119h; samDesired
0x18008bb81  mov     [rbp+Type], 0Bh
0x18008bb88  mov     ebx, 80004005h
0x18008bb8d  call    cs:__imp_RegOpenCurrentUser
0x18008bb94  nop     dword ptr [rax+rax+00h]
0x18008bb99  test    eax, eax
0x18008bb9b  jnz     loc_18008BC31
0x18008bba1  mov     rcx, rdi; this
0x18008bba4  call    ?GetCurrentProcessTickCountRegistryKey@RegistryBasedThrottle@@AEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(void)
0x18008bba9  lea     rcx, [rbp+hKey]
0x18008bbad  mov     r9d, 20119h; samDesired
0x18008bbb3  mov     [rsp+40h+var_20], rcx; phkResult
0x18008bbb8  xor     r8d, r8d; ulOptions
0x18008bbbb  mov     rcx, [rbp+phkResult]; hKey
0x18008bbbf  mov     rdx, rax; lpSubKey
0x18008bbc2  call    cs:__imp_RegOpenKeyExA
0x18008bbc9  nop     dword ptr [rax+rax+00h]
0x18008bbce  test    eax, eax
0x18008bbd0  jnz     short loc_18008BC21
0x18008bbd2  lea     rcx, [rbp+cbData]
0x18008bbd6  xor     r8d, r8d; lpReserved
0x18008bbd9  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x18008bbde  lea     rax, [rdi+128h]
0x18008bbe5  mov     rcx, [rbp+hKey]; hKey
0x18008bbe9  lea     r9, [rbp+Type]; lpType
0x18008bbed  mov     rdx, rsi; lpValueName
0x18008bbf0  mov     [rsp+40h+var_20], rax; lpData
0x18008bbf5  call    cs:__imp_RegQueryValueExA
0x18008bbfc  nop     dword ptr [rax+rax+00h]
0x18008bc01  test    eax, eax
0x18008bc03  jnz     short loc_18008BC11
0x18008bc05  mov     dword ptr [rdi+130h], 1
0x18008bc0f  xor     ebx, ebx
0x18008bc11  mov     rcx, [rbp+hKey]; hKey
0x18008bc15  call    cs:__imp_RegCloseKey
0x18008bc1c  nop     dword ptr [rax+rax+00h]
0x18008bc21  mov     rcx, [rbp+phkResult]; hKey
0x18008bc25  call    cs:__imp_RegCloseKey
0x18008bc2c  nop     dword ptr [rax+rax+00h]
0x18008bc31  mov     eax, ebx
0x18008bc33  mov     rbx, [rsp+40h+arg_0]
0x18008bc38  add     rsp, 40h
0x18008bc3c  pop     rdi
0x18008bc3d  pop     rsi
0x18008bc3e  pop     rbp
0x18008bc3f  retn
```
