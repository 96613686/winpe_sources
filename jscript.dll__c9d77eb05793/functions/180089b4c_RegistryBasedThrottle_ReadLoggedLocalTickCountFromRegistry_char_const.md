# RegistryBasedThrottle::ReadLoggedLocalTickCountFromRegistry(char const *)

- ea: `0x180089b4c`
- end: `0x180089c1e`
- name: `?ReadLoggedLocalTickCountFromRegistry@RegistryBasedThrottle@@AEAAJPEBD@Z`
- size: `210`
- prototype: `__int64 __fastcall(RegistryBasedThrottle *__hidden this, LPCSTR lpValueName)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180051880`
- `0x18007b250`
- `0x18007b384`
- `0x18007b6f0`

## callees

- `0x180088fc0`
- `0x180089b4c`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180089bb8`
- `ADVAPI32!RegOpenKeyExA` at `0x180089bb8`
- `ADVAPI32!RegCloseKey` at `0x180089bff`
- `ADVAPI32!RegCloseKey` at `0x180089c09`
- `ADVAPI32!RegCloseKey` at `0x180089bff`
- `ADVAPI32!RegCloseKey` at `0x180089c09`
- `ADVAPI32!RegQueryValueExA` at `0x180089be5`
- `ADVAPI32!RegQueryValueExA` at `0x180089be5`
- `ADVAPI32!RegOpenCurrentUser` at `0x180089b8d`
- `ADVAPI32!RegOpenCurrentUser` at `0x180089b8d`

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
0x180089b4c  mov     [rsp-18h+arg_0], rbx
0x180089b51  push    rbp
0x180089b52  push    rsi
0x180089b53  push    rdi
0x180089b54  mov     rbp, rsp
0x180089b57  sub     rsp, 40h
0x180089b5b  mov     rsi, rdx
0x180089b5e  mov     [rbp+phkResult], 0
0x180089b66  mov     rdi, rcx
0x180089b69  mov     [rbp+hKey], 0
0x180089b71  lea     rdx, [rbp+phkResult]; phkResult
0x180089b75  mov     [rbp+cbData], 8
0x180089b7c  mov     ecx, 20119h; samDesired
0x180089b81  mov     [rbp+Type], 0Bh
0x180089b88  mov     ebx, 80004005h
0x180089b8d  call    cs:__imp_RegOpenCurrentUser
0x180089b93  test    eax, eax
0x180089b95  jnz     short loc_180089C0F
0x180089b97  mov     rcx, rdi; this
0x180089b9a  call    ?GetCurrentProcessTickCountRegistryKey@RegistryBasedThrottle@@AEAAPEADXZ; RegistryBasedThrottle::GetCurrentProcessTickCountRegistryKey(void)
0x180089b9f  lea     rcx, [rbp+hKey]
0x180089ba3  mov     r9d, 20119h; samDesired
0x180089ba9  mov     [rsp+40h+var_20], rcx; phkResult
0x180089bae  xor     r8d, r8d; ulOptions
0x180089bb1  mov     rcx, [rbp+phkResult]; hKey
0x180089bb5  mov     rdx, rax; lpSubKey
0x180089bb8  call    cs:__imp_RegOpenKeyExA
0x180089bbe  test    eax, eax
0x180089bc0  jnz     short loc_180089C05
0x180089bc2  lea     rcx, [rbp+cbData]
0x180089bc6  xor     r8d, r8d; lpReserved
0x180089bc9  mov     [rsp+40h+lpcbData], rcx; lpcbData
0x180089bce  lea     rax, [rdi+128h]
0x180089bd5  mov     rcx, [rbp+hKey]; hKey
0x180089bd9  lea     r9, [rbp+Type]; lpType
0x180089bdd  mov     rdx, rsi; lpValueName
0x180089be0  mov     [rsp+40h+var_20], rax; lpData
0x180089be5  call    cs:__imp_RegQueryValueExA
0x180089beb  test    eax, eax
0x180089bed  jnz     short loc_180089BFB
0x180089bef  mov     dword ptr [rdi+130h], 1
0x180089bf9  xor     ebx, ebx
0x180089bfb  mov     rcx, [rbp+hKey]; hKey
0x180089bff  call    cs:__imp_RegCloseKey
0x180089c05  mov     rcx, [rbp+phkResult]; hKey
0x180089c09  call    cs:__imp_RegCloseKey
0x180089c0f  mov     eax, ebx
0x180089c11  mov     rbx, [rsp+40h+arg_0]
0x180089c16  add     rsp, 40h
0x180089c1a  pop     rdi
0x180089c1b  pop     rsi
0x180089c1c  pop     rbp
0x180089c1d  retn
```
