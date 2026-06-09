# CSystemMetrics::EnsureValidRegistry(void)

- ea: `0x180073d0c`
- end: `0x180073fdf`
- name: `?EnsureValidRegistry@CSystemMetrics@@AEAAXXZ`
- size: `723`
- prototype: `void __fastcall(CSystemMetrics *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007370c`
- `0x180074a68`
- `0x1800b6310`

## callees

- `0x180073d0c`
- `0x180074950`
- `0x180114520`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180073d6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenCurrentUser` at `0x180073d6c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073dc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073e5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073f52`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073dc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073e5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180073f52`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073df7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073e96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073ec6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073ef5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073f8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073fbb`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073df7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073e96`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073ec6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073ef5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073f8e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180073fbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073e01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073f18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073fc5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073e01`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073f09`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073f18`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180073fc5`
- `USER32!GetSystemMetrics` at `0x180073d77`
- `USER32!GetSystemMetrics` at `0x180073d77`

## pseudocode

```c
void __fastcall CSystemMetrics::EnsureValidRegistry(CSystemMetrics *this)
{
  BOOL v1; // ebx
  BOOL v2; // edi
  HKEY hKey; // [rsp+30h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+38h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+40h] [rbp-18h] BYREF

  if ( !HIBYTE(g_systemMetrics) )
  {
    phkResult = 0;
    HIBYTE(g_systemMetrics) = 1;
    RegOpenCurrentUser(0x20019u, &phkResult);
    if ( GetSystemMetrics(4096) )
    {
      *(_DWORD *)&Data = 0;
    }
    else
    {
      *(_DWORD *)&Data = 1;
      if ( !(unsigned int)IsSystemProcess() )
      {
        if ( phkResult )
        {
          hKey = 0;
          if ( !RegOpenKeyExW(phkResult, L"Control Panel\\Desktop", 0, 0x20019u, &hKey) )
          {
            cbData = 4;
            RegQueryValueExW(hKey, L"SmoothScroll", 0, 0, &Data, &cbData);
            RegCloseKey(hKey);
          }
        }
      }
    }
    *(_DWORD *)&dword_180210E90 = 1;
    v1 = 0;
    *(_DWORD *)&dword_180210E7C = 1;
    v2 = 0;
    *(_DWORD *)&dword_180210E78 = 1;
    if ( !(unsigned int)IsSystemProcess() )
    {
      if ( !phkResult )
        return;
      hKey = 0;
      if ( !RegOpenKeyExW(
              phkResult,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
              0,
              0x20019u,
              &hKey) )
      {
        cbData = 4;
        RegQueryValueExW(hKey, L"EnableBalloonTips", 0, 0, &dword_180210E90, &cbData);
        cbData = 4;
        v2 = (unsigned int)(RegQueryValueExW(hKey, L"ListviewAlphaSelect", 0, 0, &dword_180210E78, &cbData) - 2) <= 1;
        v1 = (unsigned int)(RegQueryValueExW(hKey, L"ListviewShadow", 0, 0, &dword_180210E7C, &cbData) - 2) <= 1;
        RegCloseKey(hKey);
      }
    }
    if ( phkResult )
      RegCloseKey(phkResult);
    if ( v1 || v2 )
    {
      hKey = 0;
      if ( !RegOpenKeyExW(
              HKEY_LOCAL_MACHINE,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
              0,
              0x20019u,
              &hKey) )
      {
        if ( v2 )
        {
          cbData = 4;
          RegQueryValueExW(hKey, L"ListviewAlphaSelect", 0, 0, &dword_180210E78, &cbData);
        }
        if ( v1 )
        {
          cbData = 4;
          RegQueryValueExW(hKey, L"ListviewShadow", 0, 0, &dword_180210E7C, &cbData);
        }
        RegCloseKey(hKey);
      }
    }
  }
}

```

## disassembly

```asm
0x180073d0c  push    rbp
0x180073d0e  push    rbx
0x180073d0f  push    rdi
0x180073d10  push    r12
0x180073d12  push    r13
0x180073d14  push    r14
0x180073d16  mov     rbp, rsp
0x180073d19  sub     rsp, 58h
0x180073d1d  mov     rax, cs:__security_cookie
0x180073d24  xor     rax, rsp
0x180073d27  mov     [rbp+var_10], rax
0x180073d2b  cmp     byte ptr cs:?g_systemMetrics@@3VCSystemMetrics@@A+1, 0; CSystemMetrics g_systemMetrics
0x180073d32  jz      short loc_180073D4E
0x180073d34  mov     rcx, [rbp+var_10]
0x180073d38  xor     rcx, rsp; StackCookie
0x180073d3b  call    __security_check_cookie
0x180073d40  add     rsp, 58h
0x180073d44  pop     r14
0x180073d46  pop     r13
0x180073d48  pop     r12
0x180073d4a  pop     rdi
0x180073d4b  pop     rbx
0x180073d4c  pop     rbp
0x180073d4d  retn
0x180073d4e  mov     r14d, 1
0x180073d54  mov     [rbp+phkResult], 0
0x180073d5c  lea     rdx, [rbp+phkResult]; phkResult
0x180073d60  mov     byte ptr cs:?g_systemMetrics@@3VCSystemMetrics@@A+1, r14b; CSystemMetrics g_systemMetrics
0x180073d67  mov     ecx, 20019h; samDesired
0x180073d6c  call    cs:__imp_RegOpenCurrentUser
0x180073d72  mov     ecx, 1000h; nIndex
0x180073d77  call    cs:__imp_GetSystemMetrics
0x180073d7d  lea     r12d, [r14+3]
0x180073d81  test    eax, eax
0x180073d83  jnz     loc_180073FD0
0x180073d89  mov     cs:Data, r14d
0x180073d90  call    ?IsSystemProcess@@YAHXZ; IsSystemProcess(void)
0x180073d95  test    eax, eax
0x180073d97  jnz     short loc_180073E07
0x180073d99  mov     rcx, [rbp+phkResult]; hKey
0x180073d9d  test    rcx, rcx
0x180073da0  jz      short loc_180073E07
0x180073da2  lea     rax, [rbp+hKey]
0x180073da6  mov     [rbp+hKey], 0
0x180073dae  mov     r9d, 20019h; samDesired
0x180073db4  mov     [rsp+58h+var_38], rax; phkResult
0x180073db9  xor     r8d, r8d; ulOptions
0x180073dbc  lea     rdx, aControlPanelDe; "Control Panel\\Desktop"
0x180073dc3  call    cs:__imp_RegOpenKeyExW
0x180073dc9  test    eax, eax
0x180073dcb  jnz     short loc_180073E07
0x180073dcd  mov     rcx, [rbp+hKey]; hKey
0x180073dd1  lea     rax, [rbp+cbData]
0x180073dd5  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180073dda  lea     rdx, pszValue; "SmoothScroll"
0x180073de1  lea     rax, Data
0x180073de8  mov     [rbp+cbData], r12d
0x180073dec  xor     r9d, r9d; lpType
0x180073def  mov     [rsp+58h+var_38], rax; lpData
0x180073df4  xor     r8d, r8d; lpReserved
0x180073df7  call    cs:__imp_RegQueryValueExW
0x180073dfd  mov     rcx, [rbp+hKey]; hKey
0x180073e01  call    cs:__imp_RegCloseKey
0x180073e07  mov     cs:dword_180210E90, r14d
0x180073e0e  xor     ebx, ebx
0x180073e10  mov     cs:dword_180210E7C, r14d
0x180073e17  xor     edi, edi
0x180073e19  mov     cs:dword_180210E78, r14d
0x180073e20  call    ?IsSystemProcess@@YAHXZ; IsSystemProcess(void)
0x180073e25  lea     r13, dword_180210E7C
0x180073e2c  test    eax, eax
0x180073e2e  jnz     loc_180073F0F
0x180073e34  mov     rcx, [rbp+phkResult]; hKey
0x180073e38  test    rcx, rcx
0x180073e3b  jz      loc_180073D34
0x180073e41  lea     rax, [rbp+hKey]
0x180073e45  mov     [rbp+hKey], rbx
0x180073e49  mov     r9d, 20019h; samDesired
0x180073e4f  mov     [rsp+58h+var_38], rax; phkResult
0x180073e54  xor     r8d, r8d; ulOptions
0x180073e57  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180073e5e  call    cs:__imp_RegOpenKeyExW
0x180073e64  test    eax, eax
0x180073e66  jnz     loc_180073F0F
0x180073e6c  mov     rcx, [rbp+hKey]; hKey
0x180073e70  lea     rax, [rbp+cbData]
0x180073e74  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180073e79  lea     rdx, aEnableballoont; "EnableBalloonTips"
0x180073e80  lea     rax, dword_180210E90
0x180073e87  mov     [rbp+cbData], r12d
0x180073e8b  xor     r9d, r9d; lpType
0x180073e8e  mov     [rsp+58h+var_38], rax; lpData
0x180073e93  xor     r8d, r8d; lpReserved
0x180073e96  call    cs:__imp_RegQueryValueExW
0x180073e9c  mov     rcx, [rbp+hKey]; hKey
0x180073ea0  lea     rax, [rbp+cbData]
0x180073ea4  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180073ea9  lea     rdx, aListviewalphas; "ListviewAlphaSelect"
0x180073eb0  lea     rax, dword_180210E78
0x180073eb7  mov     [rbp+cbData], r12d
0x180073ebb  xor     r9d, r9d; lpType
0x180073ebe  mov     [rsp+58h+var_38], rax; lpData
0x180073ec3  xor     r8d, r8d; lpReserved
0x180073ec6  call    cs:__imp_RegQueryValueExW
0x180073ecc  mov     rcx, [rbp+hKey]; hKey
0x180073ed0  lea     rdx, aListviewshadow; "ListviewShadow"
0x180073ed7  add     eax, 0FFFFFFFEh
0x180073eda  cmp     eax, r14d
0x180073edd  lea     rax, [rbp+cbData]
0x180073ee1  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180073ee6  cmovbe  edi, r14d
0x180073eea  mov     [rsp+58h+var_38], r13; lpData
0x180073eef  xor     r9d, r9d; lpType
0x180073ef2  xor     r8d, r8d; lpReserved
0x180073ef5  call    cs:__imp_RegQueryValueExW
0x180073efb  mov     rcx, [rbp+hKey]; hKey
0x180073eff  add     eax, 0FFFFFFFEh
0x180073f02  cmp     eax, r14d
0x180073f05  cmovbe  ebx, r14d
0x180073f09  call    cs:__imp_RegCloseKey
0x180073f0f  mov     rcx, [rbp+phkResult]; hKey
0x180073f13  test    rcx, rcx
0x180073f16  jz      short loc_180073F1E
0x180073f18  call    cs:__imp_RegCloseKey
0x180073f1e  test    ebx, ebx
0x180073f20  jnz     short loc_180073F2A
0x180073f22  test    edi, edi
0x180073f24  jz      loc_180073D34
0x180073f2a  lea     rax, [rbp+hKey]
0x180073f2e  mov     [rbp+hKey], 0
0x180073f36  mov     r9d, 20019h; samDesired
0x180073f3c  mov     [rsp+58h+var_38], rax; phkResult
0x180073f41  xor     r8d, r8d; ulOptions
0x180073f44  lea     rdx, aSoftwareMicros_6; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180073f4b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180073f52  call    cs:__imp_RegOpenKeyExW
0x180073f58  test    eax, eax
0x180073f5a  jnz     loc_180073D34
0x180073f60  test    edi, edi
0x180073f62  jz      short loc_180073F94
0x180073f64  mov     rcx, [rbp+hKey]; hKey
0x180073f68  lea     rax, [rbp+cbData]
0x180073f6c  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180073f71  lea     rdx, aListviewalphas; "ListviewAlphaSelect"
0x180073f78  lea     rax, dword_180210E78
0x180073f7f  mov     [rbp+cbData], r12d
0x180073f83  xor     r9d, r9d; lpType
0x180073f86  mov     [rsp+58h+var_38], rax; lpData
0x180073f8b  xor     r8d, r8d; lpReserved
0x180073f8e  call    cs:__imp_RegQueryValueExW
0x180073f94  test    ebx, ebx
0x180073f96  jz      short loc_180073FC1
0x180073f98  mov     rcx, [rbp+hKey]; hKey
0x180073f9c  lea     rax, [rbp+cbData]
0x180073fa0  mov     [rsp+58h+lpcbData], rax; lpcbData
0x180073fa5  lea     rdx, aListviewshadow; "ListviewShadow"
0x180073fac  xor     r9d, r9d; lpType
0x180073faf  mov     [rsp+58h+var_38], r13; lpData
0x180073fb4  xor     r8d, r8d; lpReserved
0x180073fb7  mov     [rbp+cbData], r12d
0x180073fbb  call    cs:__imp_RegQueryValueExW
0x180073fc1  mov     rcx, [rbp+hKey]; hKey
0x180073fc5  call    cs:__imp_RegCloseKey
0x180073fcb  jmp     loc_180073D34
0x180073fd0  mov     cs:Data, 0
0x180073fda  jmp     loc_180073E07
```
