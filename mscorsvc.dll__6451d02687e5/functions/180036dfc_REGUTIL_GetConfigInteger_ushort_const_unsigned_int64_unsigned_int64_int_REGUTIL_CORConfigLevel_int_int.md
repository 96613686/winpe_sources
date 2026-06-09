# REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)

- ea: `0x180036dfc`
- end: `0x180036fcd`
- name: `?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z`
- size: `465`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180002e24`
- `0x180002eb4`
- `0x1800053a0`
- `0x1800366a8`

## callees

- `0x180030568`
- `0x180036ca0`
- `0x180036dfc`
- `0x180037470`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180036f20`
- `ADVAPI32!RegCloseKey` at `0x180036f8f`
- `ADVAPI32!RegCloseKey` at `0x180036f20`
- `ADVAPI32!RegCloseKey` at `0x180036f8f`
- `ADVAPI32!RegQueryValueExW` at `0x180036f13`
- `ADVAPI32!RegQueryValueExW` at `0x180036f82`
- `ADVAPI32!RegQueryValueExW` at `0x180036f13`
- `ADVAPI32!RegQueryValueExW` at `0x180036f82`
- `ADVAPI32!RegOpenKeyExW` at `0x180036ee9`
- `ADVAPI32!RegOpenKeyExW` at `0x180036f58`
- `ADVAPI32!RegOpenKeyExW` at `0x180036ee9`
- `ADVAPI32!RegOpenKeyExW` at `0x180036f58`
- `ucrtbase_clr0400!wcstoul` at `0x180036e6b`
- `ucrtbase_clr0400!wcstoul` at `0x180036e6b`
- `ucrtbase_clr0400!_errno` at `0x180036e57`
- `ucrtbase_clr0400!_errno` at `0x180036e73`
- `ucrtbase_clr0400!_errno` at `0x180036e57`
- `ucrtbase_clr0400!_errno` at `0x180036e73`

## pseudocode

```c
__int64 __fastcall REGUTIL::GetConfigInteger(wchar_t *a1, __int64 a2, _QWORD *a3, __int64 a4, char a5, int a6, int a7)
{
  int v7; // r15d
  bool v9; // cf
  unsigned int v12; // esi
  wchar_t *String; // rbx
  __int64 v14; // rsi
  __int64 v16; // rbx
  __int64 v17; // rbx
  DWORD cbData; // [rsp+30h] [rbp-30h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-28h] BYREF
  HKEY phkResult; // [rsp+40h] [rbp-20h] BYREF
  BYTE Data[8]; // [rsp+48h] [rbp-18h] BYREF
  wchar_t *EndPtr; // [rsp+50h] [rbp-10h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  *(_QWORD *)Data = 0;
  v7 = 1;
  Type = 0;
  v9 = a7 != 0;
  a7 = -a7;
  cbData = 4;
  v12 = v9 ? 0xFFFFFFFA : 0;
  if ( (a5 & 1) != 0 )
  {
    String = REGUTIL::EnvGetString(a1, a6);
    if ( String )
    {
      *_errno() = 0;
      v14 = wcstoul(String, &EndPtr, v12 + 16);
      if ( *_errno() == 34 || EndPtr == String )
        v7 = 0;
      operator delete(String);
      if ( v7 )
      {
        *a3 = v14;
        return 0;
      }
    }
  }
  if ( (a5 & 0xE) != 0 && (unsigned int)REGUTIL::RegCacheValueNameSeenPerhaps(a1) )
  {
    if ( (a5 & 2) != 0
      && (hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL,
          !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, &hKey))
      && (v16 = RegQueryValueExW(hKey, a1, 0, &Type, Data, &cbData), RegCloseKey(hKey), !v16)
      && Type == 4
      || (a5 & 4) != 0
      && (phkResult = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL,
          !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, 0x20019u, &phkResult))
      && (v17 = RegQueryValueExW(phkResult, a1, 0, &Type, Data, &cbData), RegCloseKey(phkResult), !v17)
      && Type == 4 )
    {
      *a3 = *(_QWORD *)Data;
      return 0;
    }
  }
  *a3 = a2;
  return 2147500037LL;
}

```

## disassembly

```asm
0x180036dfc  mov     [rsp-28h+arg_0], rbx
0x180036e01  mov     [rsp-28h+arg_8], rsi
0x180036e06  mov     [rsp-28h+Type], r9d
0x180036e0b  push    rbp
0x180036e0c  push    rdi
0x180036e0d  push    r12
0x180036e0f  push    r13
0x180036e11  push    r15
0x180036e13  mov     rbp, rsp
0x180036e16  sub     rsp, 60h
0x180036e1a  and     qword ptr [rbp+Data], 0
0x180036e1f  mov     r15d, 1
0x180036e25  and     [rbp+Type], 0
0x180036e29  mov     rdi, r8
0x180036e2c  neg     [rbp+arg_30]
0x180036e2f  mov     r13, rdx
0x180036e32  mov     r12, rcx
0x180036e35  mov     [rbp+cbData], 4
0x180036e3c  sbb     esi, esi
0x180036e3e  and     esi, 0FFFFFFFAh
0x180036e41  test    [rbp+arg_20], r15b
0x180036e45  jz      short loc_180036E9E
0x180036e47  mov     edx, [rbp+arg_28]; int
0x180036e4a  call    ?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z; REGUTIL::EnvGetString(ushort const *,int)
0x180036e4f  mov     rbx, rax
0x180036e52  test    rax, rax
0x180036e55  jz      short loc_180036E9E
0x180036e57  call    cs:__imp__errno
0x180036e5d  lea     r8d, [rsi+10h]; Radix
0x180036e61  mov     rcx, rbx; String
0x180036e64  lea     rdx, [rbp+EndPtr]; EndPtr
0x180036e68  and     dword ptr [rax], 0
0x180036e6b  call    cs:__imp_wcstoul
0x180036e71  mov     esi, eax
0x180036e73  call    cs:__imp__errno
0x180036e79  cmp     dword ptr [rax], 22h ; '"'
0x180036e7c  jz      short loc_180036E84
0x180036e7e  cmp     [rbp+EndPtr], rbx
0x180036e82  jnz     short loc_180036E87
0x180036e84  xor     r15d, r15d
0x180036e87  mov     rcx, rbx; lpMem
0x180036e8a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180036e8f  test    r15d, r15d
0x180036e92  jz      short loc_180036E9E
0x180036e94  mov     [rdi], rsi
0x180036e97  xor     eax, eax
0x180036e99  jmp     loc_180036FB4
0x180036e9e  test    [rbp+arg_20], 0Eh
0x180036ea2  jz      loc_180036FAC
0x180036ea8  mov     rcx, r12; unsigned __int16 *
0x180036eab  call    ?RegCacheValueNameSeenPerhaps@REGUTIL@@CAHPEBG@Z; REGUTIL::RegCacheValueNameSeenPerhaps(ushort const *)
0x180036eb0  test    eax, eax
0x180036eb2  jz      loc_180036FAC
0x180036eb8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180036ebc  mov     r15d, 20019h
0x180036ec2  test    [rbp+arg_20], 2
0x180036ec6  jz      short loc_180036F31
0x180036ec8  lea     rax, [rbp+hKey]
0x180036ecc  mov     [rbp+hKey], rsi
0x180036ed0  mov     r9d, r15d; samDesired
0x180036ed3  mov     [rsp+60h+phkResult], rax; phkResult
0x180036ed8  xor     r8d, r8d; ulOptions
0x180036edb  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\.NETFramework"
0x180036ee2  mov     rcx, 0FFFFFFFF80000001h; hKey
0x180036ee9  call    cs:__imp_RegOpenKeyExW
0x180036eef  test    eax, eax
0x180036ef1  jnz     short loc_180036F31
0x180036ef3  mov     rcx, [rbp+hKey]; hKey
0x180036ef7  lea     rax, [rbp+cbData]
0x180036efb  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180036f00  lea     r9, [rbp+Type]; lpType
0x180036f04  lea     rax, [rbp+Data]
0x180036f08  xor     r8d, r8d; lpReserved
0x180036f0b  mov     rdx, r12; lpValueName
0x180036f0e  mov     [rsp+60h+phkResult], rax; lpData
0x180036f13  call    cs:__imp_RegQueryValueExW
0x180036f19  mov     rcx, [rbp+hKey]; hKey
0x180036f1d  movsxd  rbx, eax
0x180036f20  call    cs:__imp_RegCloseKey
0x180036f26  test    rbx, rbx
0x180036f29  jnz     short loc_180036F31
0x180036f2b  cmp     [rbp+Type], 4
0x180036f2f  jz      short loc_180036FA0
0x180036f31  test    [rbp+arg_20], 4
0x180036f35  jz      short loc_180036FAC
0x180036f37  lea     rax, [rbp+var_20]
0x180036f3b  mov     [rbp+var_20], rsi
0x180036f3f  mov     r9d, r15d; samDesired
0x180036f42  mov     [rsp+60h+phkResult], rax; phkResult
0x180036f47  xor     r8d, r8d; ulOptions
0x180036f4a  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\.NETFramework"
0x180036f51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180036f58  call    cs:__imp_RegOpenKeyExW
0x180036f5e  test    eax, eax
0x180036f60  jnz     short loc_180036FAC
0x180036f62  mov     rcx, [rbp+var_20]; hKey
0x180036f66  lea     rax, [rbp+cbData]
0x180036f6a  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180036f6f  lea     r9, [rbp+Type]; lpType
0x180036f73  lea     rax, [rbp+Data]
0x180036f77  xor     r8d, r8d; lpReserved
0x180036f7a  mov     rdx, r12; lpValueName
0x180036f7d  mov     [rsp+60h+phkResult], rax; lpData
0x180036f82  call    cs:__imp_RegQueryValueExW
0x180036f88  mov     rcx, [rbp+var_20]; hKey
0x180036f8c  movsxd  rbx, eax
0x180036f8f  call    cs:__imp_RegCloseKey
0x180036f95  test    rbx, rbx
0x180036f98  jnz     short loc_180036FAC
0x180036f9a  cmp     [rbp+Type], 4
0x180036f9e  jnz     short loc_180036FAC
0x180036fa0  mov     rax, qword ptr [rbp+Data]
0x180036fa4  mov     [rdi], rax
0x180036fa7  jmp     loc_180036E97
0x180036fac  mov     [rdi], r13
0x180036faf  mov     eax, 80004005h
0x180036fb4  lea     r11, [rsp+60h+var_s0]
0x180036fb9  mov     rbx, [r11+30h]
0x180036fbd  mov     rsi, [r11+38h]
0x180036fc1  mov     rsp, r11
0x180036fc4  pop     r15
0x180036fc6  pop     r13
0x180036fc8  pop     r12
0x180036fca  pop     rdi
0x180036fcb  pop     rbp
0x180036fcc  retn
```
