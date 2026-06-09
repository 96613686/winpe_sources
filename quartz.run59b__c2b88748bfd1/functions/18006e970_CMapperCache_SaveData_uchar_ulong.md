# CMapperCache::SaveData(uchar *,ulong)

- ea: `0x18006e970`
- end: `0x18006ebc0`
- name: `?SaveData@CMapperCache@@QEAAJPEAEK@Z`
- size: `592`
- prototype: `int(CMapperCache *__hidden this, unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011ff0`

## callees

- `0x180004924`
- `0x1800388a0`
- `0x18006e970`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x18006ea33`
- `ADVAPI32!RegCreateKeyExW` at `0x18006ea81`
- `ADVAPI32!RegCreateKeyExW` at `0x18006ea33`
- `ADVAPI32!RegCreateKeyExW` at `0x18006ea81`
- `ADVAPI32!RegSetValueExW` at `0x18006eaeb`
- `ADVAPI32!RegSetValueExW` at `0x18006eaeb`
- `ADVAPI32!RegDeleteValueW` at `0x18006eb3e`
- `ADVAPI32!RegDeleteValueW` at `0x18006eb3e`
- `ADVAPI32!RegOpenKeyExW` at `0x18006e9d5`
- `ADVAPI32!RegOpenKeyExW` at `0x18006e9d5`
- `ADVAPI32!RegDeleteKeyW` at `0x18006eb7c`
- `ADVAPI32!RegDeleteKeyW` at `0x18006eb7c`
- `ADVAPI32!RegCloseKey` at `0x18006ea93`
- `ADVAPI32!RegCloseKey` at `0x18006eb4e`
- `ADVAPI32!RegCloseKey` at `0x18006eb62`
- `ADVAPI32!RegCloseKey` at `0x18006ea93`
- `ADVAPI32!RegCloseKey` at `0x18006eb4e`
- `ADVAPI32!RegCloseKey` at `0x18006eb62`

## string_xrefs

- `0x18006e9c8`: `Software\Microsoft\Multimedia\ActiveMovie\Filter Cache64`
- `0x18006eb6e`: `Software\Microsoft\Multimedia\ActiveMovie\Filter Cache64`
- `0x18006ea56`: `Filter Cache64`

## pseudocode

```c
__int64 __fastcall CMapperCache::SaveData(CMapperCache *this, unsigned __int8 *a2, DWORD a3)
{
  const BYTE *v4; // r13
  LSTATUS v5; // ebx
  bool v6; // cc
  unsigned int v7; // edi
  unsigned int v8; // esi
  DWORD v9; // r14d
  HKEY phkResult; // [rsp+50h] [rbp-30h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-28h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-20h] BYREF
  WCHAR ValueName[8]; // [rsp+68h] [rbp-18h] BYREF

  *((_QWORD *)a2 + 1) = 0;
  v4 = a2;
  phkResult = 0;
  if ( !RegOpenKeyExW(
          HKEY_CURRENT_USER,
          L"Software\\Microsoft\\Multimedia\\ActiveMovie\\Filter Cache64",
          0,
          0x20006u,
          &phkResult) )
    goto LABEL_4;
  dwDisposition = 0;
  hKey = 0;
  v5 = RegCreateKeyExW(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Multimedia\\ActiveMovie",
         0,
         0,
         0,
         4u,
         0,
         &hKey,
         &dwDisposition);
  if ( v5 )
  {
LABEL_16:
    v6 = v5 <= 0;
    goto LABEL_17;
  }
  v5 = RegCreateKeyExW(hKey, L"Filter Cache64", 0, 0, 1u, 0x20006u, 0, &phkResult, &dwDisposition);
  RegCloseKey(hKey);
  v6 = v5 <= 0;
  if ( v5 )
  {
LABEL_17:
    if ( !v6 )
      return (unsigned __int16)v5 | 0x80070000;
    return (unsigned int)v5;
  }
LABEL_4:
  v7 = 0x8000;
  v8 = 0;
  while ( 2 )
  {
    StringCchPrintfW(ValueName, 8u, L"%d", v8);
    while ( 1 )
    {
      v9 = a3;
      if ( a3 >= v7 )
        v9 = v7;
      v5 = RegSetValueExW(phkResult, ValueName, 0, 3u, v4, v9);
      if ( v5 != 87 )
        break;
      if ( v7 <= 0x800 )
        goto LABEL_15;
      v7 >>= 1;
    }
    if ( v5 )
    {
LABEL_15:
      RegCloseKey(phkResult);
      RegDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Multimedia\\ActiveMovie\\Filter Cache64");
      goto LABEL_16;
    }
    ++v8;
    a3 -= v9;
    if ( a3 )
    {
      v4 += v9;
      continue;
    }
    break;
  }
  StringCchPrintfW(ValueName, 8u, L"%d", v8);
  RegDeleteValueW(phkResult, ValueName);
  RegCloseKey(phkResult);
  return 0;
}

```

## disassembly

```asm
0x18006e970  mov     [rsp-28h+arg_0], rbx
0x18006e975  mov     [rsp-28h+arg_18], rsi
0x18006e97a  push    rbp
0x18006e97b  push    rdi
0x18006e97c  push    r13
0x18006e97e  push    r14
0x18006e980  push    r15
0x18006e982  mov     rbp, rsp
0x18006e985  sub     rsp, 80h
0x18006e98c  mov     rax, cs:__security_cookie
0x18006e993  xor     rax, rsp
0x18006e996  mov     [rbp+var_8], rax
0x18006e99a  mov     r15d, r8d
0x18006e99d  mov     qword ptr [rdx+8], 0
0x18006e9a5  mov     r13, rdx
0x18006e9a8  mov     [rbp+var_30], 0
0x18006e9b0  lea     rax, [rbp+var_30]
0x18006e9b4  mov     edi, 20006h
0x18006e9b9  mov     rbx, 0FFFFFFFF80000001h
0x18006e9c0  mov     [rsp+80h+phkResult], rax; phkResult
0x18006e9c5  mov     r9d, edi; samDesired
0x18006e9c8  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Multimedia\\Active"...
0x18006e9cf  mov     rcx, rbx; hKey
0x18006e9d2  xor     r8d, r8d; ulOptions
0x18006e9d5  call    cs:__imp_RegOpenKeyExW
0x18006e9dc  nop     dword ptr [rax+rax+00h]
0x18006e9e1  test    eax, eax
0x18006e9e3  jz      loc_18006EAA7
0x18006e9e9  lea     rax, [rbp+dwDisposition]
0x18006e9ed  mov     [rbp+dwDisposition], 0
0x18006e9f4  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x18006e9f9  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Multimedia\\Active"...
0x18006ea00  lea     rax, [rbp+hKey]
0x18006ea04  mov     [rbp+hKey], 0
0x18006ea0c  mov     [rsp+80h+var_48], rax; phkResult
0x18006ea11  xor     r9d, r9d; lpClass
0x18006ea14  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006ea1d  xor     r8d, r8d; Reserved
0x18006ea20  mov     [rsp+80h+samDesired], 4; samDesired
0x18006ea28  mov     rcx, rbx; hKey
0x18006ea2b  mov     dword ptr [rsp+80h+phkResult], 0; dwOptions
0x18006ea33  call    cs:__imp_RegCreateKeyExW
0x18006ea3a  nop     dword ptr [rax+rax+00h]
0x18006ea3f  mov     ebx, eax
0x18006ea41  test    eax, eax
0x18006ea43  jnz     loc_18006EB88
0x18006ea49  mov     rcx, [rbp+hKey]; hKey
0x18006ea4d  lea     rax, [rbp+dwDisposition]
0x18006ea51  mov     [rsp+80h+lpdwDisposition], rax; lpdwDisposition
0x18006ea56  lea     rdx, aFilterCache64; "Filter Cache64"
0x18006ea5d  lea     rax, [rbp+var_30]
0x18006ea61  xor     r9d, r9d; lpClass
0x18006ea64  mov     [rsp+80h+var_48], rax; phkResult
0x18006ea69  xor     r8d, r8d; Reserved
0x18006ea6c  mov     [rsp+80h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18006ea75  mov     [rsp+80h+samDesired], edi; samDesired
0x18006ea79  mov     dword ptr [rsp+80h+phkResult], 1; dwOptions
0x18006ea81  call    cs:__imp_RegCreateKeyExW
0x18006ea88  nop     dword ptr [rax+rax+00h]
0x18006ea8d  mov     rcx, [rbp+hKey]; hKey
0x18006ea91  mov     ebx, eax
0x18006ea93  call    cs:__imp_RegCloseKey
0x18006ea9a  nop     dword ptr [rax+rax+00h]
0x18006ea9f  test    ebx, ebx
0x18006eaa1  jnz     loc_18006EB8A
0x18006eaa7  mov     edi, 8000h
0x18006eaac  xor     esi, esi
0x18006eaae  mov     r9d, esi
0x18006eab1  lea     r8, aD; "%d"
0x18006eab8  mov     edx, 8; unsigned __int64
0x18006eabd  lea     rcx, [rbp+ValueName]; Buffer
0x18006eac1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006eac6  mov     rcx, [rbp+var_30]; hKey
0x18006eaca  lea     rdx, [rbp+ValueName]; lpValueName
0x18006eace  cmp     r15d, edi
0x18006ead1  mov     r14d, r15d
0x18006ead4  mov     r9d, 3; dwType
0x18006eada  cmovnb  r14d, edi
0x18006eade  xor     r8d, r8d; Reserved
0x18006eae1  mov     [rsp+80h+samDesired], r14d; cbData
0x18006eae6  mov     [rsp+80h+phkResult], r13; lpData
0x18006eaeb  call    cs:__imp_RegSetValueExW
0x18006eaf2  nop     dword ptr [rax+rax+00h]
0x18006eaf7  mov     ebx, eax
0x18006eaf9  cmp     eax, 57h ; 'W'
0x18006eafc  jnz     short loc_18006EB0A
0x18006eafe  cmp     edi, 800h
0x18006eb04  jbe     short loc_18006EB5E
0x18006eb06  shr     edi, 1
0x18006eb08  jmp     short loc_18006EAC6
0x18006eb0a  test    ebx, ebx
0x18006eb0c  jnz     short loc_18006EB5E
0x18006eb0e  lea     esi, [rsi+1]
0x18006eb11  sub     r15d, r14d
0x18006eb14  jz      short loc_18006EB1E
0x18006eb16  mov     eax, r14d
0x18006eb19  add     r13, rax
0x18006eb1c  jmp     short loc_18006EAAE
0x18006eb1e  mov     r9d, esi
0x18006eb21  lea     r8, aD; "%d"
0x18006eb28  mov     edx, 8; unsigned __int64
0x18006eb2d  lea     rcx, [rbp+ValueName]; Buffer
0x18006eb31  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006eb36  mov     rcx, [rbp+var_30]; hKey
0x18006eb3a  lea     rdx, [rbp+ValueName]; lpValueName
0x18006eb3e  call    cs:__imp_RegDeleteValueW
0x18006eb45  nop     dword ptr [rax+rax+00h]
0x18006eb4a  mov     rcx, [rbp+var_30]; hKey
0x18006eb4e  call    cs:__imp_RegCloseKey
0x18006eb55  nop     dword ptr [rax+rax+00h]
0x18006eb5a  xor     eax, eax
0x18006eb5c  jmp     short loc_18006EB97
0x18006eb5e  mov     rcx, [rbp+var_30]; hKey
0x18006eb62  call    cs:__imp_RegCloseKey
0x18006eb69  nop     dword ptr [rax+rax+00h]
0x18006eb6e  lea     rdx, aSoftwareMicros_7; "Software\\Microsoft\\Multimedia\\Active"...
0x18006eb75  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18006eb7c  call    cs:__imp_RegDeleteKeyW
0x18006eb83  nop     dword ptr [rax+rax+00h]
0x18006eb88  test    ebx, ebx
0x18006eb8a  jle     short loc_18006EB95
0x18006eb8c  movzx   ebx, bx
0x18006eb8f  or      ebx, 80070000h
0x18006eb95  mov     eax, ebx
0x18006eb97  mov     rcx, [rbp+var_8]
0x18006eb9b  xor     rcx, rsp; StackCookie
0x18006eb9e  call    __security_check_cookie
0x18006eba3  lea     r11, [rsp+80h+var_s0]
0x18006ebab  mov     rbx, [r11+30h]
0x18006ebaf  mov     rsi, [r11+48h]
0x18006ebb3  mov     rsp, r11
0x18006ebb6  pop     r15
0x18006ebb8  pop     r14
0x18006ebba  pop     r13
0x18006ebbc  pop     rdi
0x18006ebbd  pop     rbp
0x18006ebbe  retn
```
