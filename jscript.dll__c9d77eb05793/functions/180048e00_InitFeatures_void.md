# InitFeatures(void)

- ea: `0x180048e00`
- end: `0x180048f68`
- name: `?InitFeatures@@YAXXZ`
- size: `360`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180048d00`

## callees

- `0x180048e00`
- `0x180048f70`
- `0x1800942d0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExA` at `0x180048e76`
- `ADVAPI32!RegOpenKeyExA` at `0x180048ea1`
- `ADVAPI32!RegOpenKeyExA` at `0x180048e76`
- `ADVAPI32!RegOpenKeyExA` at `0x180048ea1`
- `ADVAPI32!RegCloseKey` at `0x180048f28`
- `ADVAPI32!RegCloseKey` at `0x180048f41`
- `ADVAPI32!RegCloseKey` at `0x180048f28`
- `ADVAPI32!RegCloseKey` at `0x180048f41`
- `ADVAPI32!RegQueryValueExA` at `0x180048f00`
- `ADVAPI32!RegQueryValueExA` at `0x180048f00`

## pseudocode

```c
void InitFeatures(void)
{
  struct FeatureEntry near **v0; // rbx
  int v1; // edi
  bool v2; // zf
  HKEY v3; // rcx
  int v4; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  HKEY phkResult; // [rsp+48h] [rbp-B8h] BYREF
  CHAR SubKey[272]; // [rsp+50h] [rbp-B0h] BYREF

  if ( (unsigned int)GetModuleNameA(SubKey) )
    return;
  Type = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  hKey = 0;
  phkResult = 0;
  if ( RegOpenKeyExA(HKEY_LOCAL_MACHINE, "SOFTWARE\\Microsoft\\Windows Script\\Features", 0, 1u, &hKey) )
    return;
  RegOpenKeyExA(hKey, SubKey, 0, 1u, &phkResult);
  v0 = &g_arFeatures;
  v1 = 5;
  do
  {
    v2 = (*(_BYTE *)v0 & 1) == 0;
    *(_DWORD *)Data = *((_DWORD *)v0 + 5);
    Type = 4;
    cbData = 4;
    if ( v2 )
    {
      v3 = hKey;
    }
    else
    {
      v3 = phkResult;
      if ( !phkResult )
        goto LABEL_10;
    }
    if ( !RegQueryValueExA(v3, (LPCSTR)v0[1], 0, &Type, Data, &cbData) )
    {
      v4 = *(_DWORD *)Data;
      *(_DWORD *)v0 |= 0x1000000u;
      *((_DWORD *)v0 + 4) = v4;
    }
LABEL_10:
    v0 += 3;
    --v1;
  }
  while ( v1 );
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( phkResult )
    RegCloseKey(phkResult);
}

```

## disassembly

```asm
0x180048e00  mov     [rsp-8+arg_0], rbx
0x180048e05  mov     [rsp-8+arg_8], rdi
0x180048e0a  push    rbp
0x180048e0b  lea     rbp, [rsp-70h]
0x180048e10  sub     rsp, 170h
0x180048e17  mov     rax, cs:__security_cookie
0x180048e1e  xor     rax, rsp
0x180048e21  mov     [rbp+70h+var_10], rax
0x180048e25  lea     rcx, [rsp+170h+SubKey]; Filename
0x180048e2a  call    GetModuleNameA
0x180048e2f  test    eax, eax
0x180048e31  jnz     loc_180048F47
0x180048e37  mov     [rsp+170h+Type], eax
0x180048e3b  lea     rdx, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows Script\\Fe"...
0x180048e42  mov     dword ptr [rsp+170h+Data], eax
0x180048e46  mov     r9d, 1; samDesired
0x180048e4c  mov     [rsp+170h+cbData], eax
0x180048e50  xor     r8d, r8d; ulOptions
0x180048e53  lea     rax, [rsp+170h+hKey]
0x180048e58  mov     [rsp+170h+hKey], 0
0x180048e61  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180048e68  mov     [rsp+170h+phkResult], rax; phkResult
0x180048e6d  mov     [rsp+170h+var_128], 0
0x180048e76  call    cs:__imp_RegOpenKeyExA
0x180048e7c  test    eax, eax
0x180048e7e  jnz     loc_180048F47
0x180048e84  mov     rcx, [rsp+170h+hKey]; hKey
0x180048e89  lea     rax, [rsp+170h+var_128]
0x180048e8e  mov     r9d, 1; samDesired
0x180048e94  mov     [rsp+170h+phkResult], rax; phkResult
0x180048e99  xor     r8d, r8d; ulOptions
0x180048e9c  lea     rdx, [rsp+170h+SubKey]; lpSubKey
0x180048ea1  call    cs:__imp_RegOpenKeyExA
0x180048ea7  lea     rbx, ?g_arFeatures@@3PAUFeatureEntry@@A; FeatureEntry near * g_arFeatures
0x180048eae  mov     edi, 5
0x180048eb3  test    byte ptr [rbx], 1
0x180048eb6  mov     eax, [rbx+14h]
0x180048eb9  mov     dword ptr [rsp+170h+Data], eax
0x180048ebd  mov     [rsp+170h+Type], 4
0x180048ec5  mov     [rsp+170h+cbData], 4
0x180048ecd  jz      short loc_180048EDB
0x180048ecf  mov     rcx, [rsp+170h+var_128]
0x180048ed4  test    rcx, rcx
0x180048ed7  jnz     short loc_180048EE0
0x180048ed9  jmp     short loc_180048F15
0x180048edb  mov     rcx, [rsp+170h+hKey]; hKey
0x180048ee0  mov     rdx, [rbx+8]; lpValueName
0x180048ee4  lea     rax, [rsp+170h+cbData]
0x180048ee9  mov     [rsp+170h+lpcbData], rax; lpcbData
0x180048eee  lea     r9, [rsp+170h+Type]; lpType
0x180048ef3  lea     rax, [rsp+170h+Data]
0x180048ef8  xor     r8d, r8d; lpReserved
0x180048efb  mov     [rsp+170h+phkResult], rax; lpData
0x180048f00  call    cs:__imp_RegQueryValueExA
0x180048f06  test    eax, eax
0x180048f08  jnz     short loc_180048F15
0x180048f0a  mov     eax, dword ptr [rsp+170h+Data]
0x180048f0e  bts     dword ptr [rbx], 18h
0x180048f12  mov     [rbx+10h], eax
0x180048f15  add     rbx, 18h
0x180048f19  sub     edi, 1
0x180048f1c  jnz     short loc_180048EB3
0x180048f1e  mov     rcx, [rsp+170h+hKey]; hKey
0x180048f23  test    rcx, rcx
0x180048f26  jz      short loc_180048F37
0x180048f28  call    cs:__imp_RegCloseKey
0x180048f2e  mov     [rsp+170h+hKey], 0
0x180048f37  mov     rcx, [rsp+170h+var_128]; hKey
0x180048f3c  test    rcx, rcx
0x180048f3f  jz      short loc_180048F47
0x180048f41  call    cs:__imp_RegCloseKey
0x180048f47  mov     rcx, [rbp+70h+var_10]
0x180048f4b  xor     rcx, rsp; StackCookie
0x180048f4e  call    __security_check_cookie
0x180048f53  lea     r11, [rsp+170h+var_s0]
0x180048f5b  mov     rbx, [r11+10h]
0x180048f5f  mov     rdi, [r11+18h]
0x180048f63  mov     rsp, r11
0x180048f66  pop     rbp
0x180048f67  retn
```
