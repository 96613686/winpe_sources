# REGUTIL::GetConfigInteger(ushort const *,unsigned __int64,unsigned __int64 *,int,REGUTIL::CORConfigLevel,int,int)

- ea: `0x18007abac`
- end: `0x18007ad7a`
- name: `?GetConfigInteger@REGUTIL@@CAJPEBG_KPEA_KHW4CORConfigLevel@1@HH@Z`
- size: `462`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180078a98`
- `0x18007ab74`

## callees

- `0x180072664`
- `0x18007aa1c`
- `0x18007abac`
- `0x18007ad7c`
- `0x1800f9a7c`
- `0x1800fa5d0`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18007acc0`
- `ADVAPI32!RegQueryValueExW` at `0x18007ad2f`
- `ADVAPI32!RegQueryValueExW` at `0x18007acc0`
- `ADVAPI32!RegQueryValueExW` at `0x18007ad2f`
- `ADVAPI32!RegCloseKey` at `0x18007accd`
- `ADVAPI32!RegCloseKey` at `0x18007ad3c`
- `ADVAPI32!RegCloseKey` at `0x18007accd`
- `ADVAPI32!RegCloseKey` at `0x18007ad3c`
- `ADVAPI32!RegOpenKeyExW` at `0x18007ac96`
- `ADVAPI32!RegOpenKeyExW` at `0x18007ad05`
- `ADVAPI32!RegOpenKeyExW` at `0x18007ac96`
- `ADVAPI32!RegOpenKeyExW` at `0x18007ad05`

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
      *errno() = 0;
      v14 = wcstoul(String, &EndPtr, v12 + 16);
      if ( *errno() == 34 || EndPtr == String )
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
0x18007abac  mov     [rsp-28h+arg_0], rbx
0x18007abb1  mov     [rsp-28h+arg_8], rsi
0x18007abb6  mov     [rsp-28h+Type], r9d
0x18007abbb  push    rbp
0x18007abbc  push    rdi
0x18007abbd  push    r12
0x18007abbf  push    r13
0x18007abc1  push    r15
0x18007abc3  mov     rbp, rsp
0x18007abc6  sub     rsp, 60h
0x18007abca  and     qword ptr [rbp+Data], 0
0x18007abcf  mov     r15d, 1
0x18007abd5  and     [rbp+Type], 0
0x18007abd9  mov     rdi, r8
0x18007abdc  neg     [rbp+arg_30]
0x18007abdf  mov     r13, rdx
0x18007abe2  mov     r12, rcx
0x18007abe5  mov     [rbp+cbData], 4
0x18007abec  sbb     esi, esi
0x18007abee  and     esi, 0FFFFFFFAh
0x18007abf1  test    [rbp+arg_20], r15b
0x18007abf5  jz      short loc_18007AC4B
0x18007abf7  mov     edx, [rbp+arg_28]; int
0x18007abfa  call    ?EnvGetString@REGUTIL@@SAPEAGPEBGH@Z; REGUTIL::EnvGetString(ushort const *,int)
0x18007abff  mov     rbx, rax
0x18007ac02  test    rax, rax
0x18007ac05  jz      short loc_18007AC4B
0x18007ac07  call    _errno
0x18007ac0c  lea     r8d, [rsi+10h]; Radix
0x18007ac10  mov     rcx, rbx; String
0x18007ac13  lea     rdx, [rbp+EndPtr]; EndPtr
0x18007ac17  and     dword ptr [rax], 0
0x18007ac1a  call    wcstoul
0x18007ac1f  mov     esi, eax
0x18007ac21  call    _errno
0x18007ac26  cmp     dword ptr [rax], 22h ; '"'
0x18007ac29  jz      short loc_18007AC31
0x18007ac2b  cmp     [rbp+EndPtr], rbx
0x18007ac2f  jnz     short loc_18007AC34
0x18007ac31  xor     r15d, r15d
0x18007ac34  mov     rcx, rbx; lpMem
0x18007ac37  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18007ac3c  test    r15d, r15d
0x18007ac3f  jz      short loc_18007AC4B
0x18007ac41  mov     [rdi], rsi
0x18007ac44  xor     eax, eax
0x18007ac46  jmp     loc_18007AD61
0x18007ac4b  test    [rbp+arg_20], 0Eh
0x18007ac4f  jz      loc_18007AD59
0x18007ac55  mov     rcx, r12; unsigned __int16 *
0x18007ac58  call    ?RegCacheValueNameSeenPerhaps@REGUTIL@@CAHPEBG@Z; REGUTIL::RegCacheValueNameSeenPerhaps(ushort const *)
0x18007ac5d  test    eax, eax
0x18007ac5f  jz      loc_18007AD59
0x18007ac65  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18007ac69  mov     r15d, 20019h
0x18007ac6f  test    [rbp+arg_20], 2
0x18007ac73  jz      short loc_18007ACDE
0x18007ac75  lea     rax, [rbp+hKey]
0x18007ac79  mov     [rbp+hKey], rsi
0x18007ac7d  mov     r9d, r15d; samDesired
0x18007ac80  mov     [rsp+60h+phkResult], rax; phkResult
0x18007ac85  xor     r8d, r8d; ulOptions
0x18007ac88  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework"
0x18007ac8f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18007ac96  call    cs:__imp_RegOpenKeyExW
0x18007ac9c  test    eax, eax
0x18007ac9e  jnz     short loc_18007ACDE
0x18007aca0  mov     rcx, [rbp+hKey]; hKey
0x18007aca4  lea     rax, [rbp+cbData]
0x18007aca8  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18007acad  lea     r9, [rbp+Type]; lpType
0x18007acb1  lea     rax, [rbp+Data]
0x18007acb5  xor     r8d, r8d; lpReserved
0x18007acb8  mov     rdx, r12; lpValueName
0x18007acbb  mov     [rsp+60h+phkResult], rax; lpData
0x18007acc0  call    cs:__imp_RegQueryValueExW
0x18007acc6  mov     rcx, [rbp+hKey]; hKey
0x18007acca  movsxd  rbx, eax
0x18007accd  call    cs:__imp_RegCloseKey
0x18007acd3  test    rbx, rbx
0x18007acd6  jnz     short loc_18007ACDE
0x18007acd8  cmp     [rbp+Type], 4
0x18007acdc  jz      short loc_18007AD4D
0x18007acde  test    [rbp+arg_20], 4
0x18007ace2  jz      short loc_18007AD59
0x18007ace4  lea     rax, [rbp+var_20]
0x18007ace8  mov     [rbp+var_20], rsi
0x18007acec  mov     r9d, r15d; samDesired
0x18007acef  mov     [rsp+60h+phkResult], rax; phkResult
0x18007acf4  xor     r8d, r8d; ulOptions
0x18007acf7  lea     rdx, SubKey; "Software\\Microsoft\\.NETFramework"
0x18007acfe  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18007ad05  call    cs:__imp_RegOpenKeyExW
0x18007ad0b  test    eax, eax
0x18007ad0d  jnz     short loc_18007AD59
0x18007ad0f  mov     rcx, [rbp+var_20]; hKey
0x18007ad13  lea     rax, [rbp+cbData]
0x18007ad17  mov     [rsp+60h+lpcbData], rax; lpcbData
0x18007ad1c  lea     r9, [rbp+Type]; lpType
0x18007ad20  lea     rax, [rbp+Data]
0x18007ad24  xor     r8d, r8d; lpReserved
0x18007ad27  mov     rdx, r12; lpValueName
0x18007ad2a  mov     [rsp+60h+phkResult], rax; lpData
0x18007ad2f  call    cs:__imp_RegQueryValueExW
0x18007ad35  mov     rcx, [rbp+var_20]; hKey
0x18007ad39  movsxd  rbx, eax
0x18007ad3c  call    cs:__imp_RegCloseKey
0x18007ad42  test    rbx, rbx
0x18007ad45  jnz     short loc_18007AD59
0x18007ad47  cmp     [rbp+Type], 4
0x18007ad4b  jnz     short loc_18007AD59
0x18007ad4d  mov     rax, qword ptr [rbp+Data]
0x18007ad51  mov     [rdi], rax
0x18007ad54  jmp     loc_18007AC44
0x18007ad59  mov     [rdi], r13
0x18007ad5c  mov     eax, 80004005h
0x18007ad61  lea     r11, [rsp+60h+var_s0]
0x18007ad66  mov     rbx, [r11+30h]
0x18007ad6a  mov     rsi, [r11+38h]
0x18007ad6e  mov     rsp, r11
0x18007ad71  pop     r15
0x18007ad73  pop     r13
0x18007ad75  pop     r12
0x18007ad77  pop     rdi
0x18007ad78  pop     rbp
0x18007ad79  retn
```
