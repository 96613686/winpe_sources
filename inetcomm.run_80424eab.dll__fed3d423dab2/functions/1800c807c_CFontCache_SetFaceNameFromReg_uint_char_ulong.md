# CFontCache::SetFaceNameFromReg(uint,char *,ulong)

- ea: `0x1800c807c`
- end: `0x1800c81cd`
- name: `?SetFaceNameFromReg@CFontCache@@AEAAJIPEADK@Z`
- size: `337`
- prototype: `int(CFontCache *__hidden this, unsigned int, char *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800c81d4`

## callees

- `0x1800c807c`
- `0x1800cca00`

## import_xrefs

- `SHLWAPI!StrToIntA` at `0x1800c8130`
- `SHLWAPI!StrToIntA` at `0x1800c8130`
- `ADVAPI32!RegOpenKeyExA` at `0x1800c80d6`
- `ADVAPI32!RegOpenKeyExA` at `0x1800c8154`
- `ADVAPI32!RegOpenKeyExA` at `0x1800c80d6`
- `ADVAPI32!RegOpenKeyExA` at `0x1800c8154`
- `ADVAPI32!RegQueryValueExA` at `0x1800c8188`
- `ADVAPI32!RegQueryValueExA` at `0x1800c8188`
- `ADVAPI32!RegCloseKey` at `0x1800c8192`
- `ADVAPI32!RegCloseKey` at `0x1800c819c`
- `ADVAPI32!RegCloseKey` at `0x1800c8192`
- `ADVAPI32!RegCloseKey` at `0x1800c819c`
- `ADVAPI32!RegEnumKeyExA` at `0x1800c811f`
- `ADVAPI32!RegEnumKeyExA` at `0x1800c811f`

## pseudocode

```c
__int64 __fastcall CFontCache::SetFaceNameFromReg(CFontCache *this, int a2, BYTE *a3)
{
  const CHAR *v4; // rdx
  HKEY v5; // rcx
  DWORD i; // ebx
  __int64 result; // rax
  DWORD cchName; // [rsp+40h] [rbp-40h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-38h] BYREF
  HKEY phkResult; // [rsp+50h] [rbp-30h] BYREF
  CHAR Name[32]; // [rsp+58h] [rbp-28h] BYREF

  *a3 = 0;
  phkResult = 0;
  v4 = (char *)this + 80;
  hKey = 0;
  v5 = (HKEY)*((_QWORD *)this + 9);
  cchName = 0;
  if ( !RegOpenKeyExA(v5, v4, 0, 0x20019u, &hKey) )
  {
    for ( i = 0; ; ++i )
    {
      cchName = 32;
      if ( RegEnumKeyExA(hKey, i, Name, &cchName, 0, 0, 0, 0) == 259 )
        break;
      if ( StrToIntA(Name) == a2 && !RegOpenKeyExA(hKey, Name, 0, 0x20019u, &phkResult) )
      {
        cchName = 32;
        RegQueryValueExA(phkResult, "IEPropFontName", 0, 0, a3, &cchName);
        RegCloseKey(phkResult);
        break;
      }
    }
    RegCloseKey(hKey);
  }
  result = 0;
  if ( !*a3 )
    return 2147500037LL;
  return result;
}

```

## disassembly

```asm
0x1800c807c  mov     [rsp-18h+arg_8], rbx
0x1800c8081  push    rbp
0x1800c8082  push    rsi
0x1800c8083  push    rdi
0x1800c8084  mov     rbp, rsp
0x1800c8087  sub     rsp, 80h
0x1800c808e  mov     rax, cs:__security_cookie
0x1800c8095  xor     rax, rsp
0x1800c8098  mov     [rbp+var_8], rax
0x1800c809c  mov     byte ptr [r8], 0
0x1800c80a0  lea     rax, [rbp+hKey]
0x1800c80a4  mov     esi, edx
0x1800c80a6  mov     [rbp+var_30], 0
0x1800c80ae  lea     rdx, [rcx+50h]; lpSubKey
0x1800c80b2  mov     [rbp+hKey], 0
0x1800c80ba  mov     rcx, [rcx+48h]; hKey
0x1800c80be  mov     rdi, r8
0x1800c80c1  mov     r9d, 20019h; samDesired
0x1800c80c7  mov     [rbp+cchName], 0
0x1800c80ce  xor     r8d, r8d; ulOptions
0x1800c80d1  mov     [rsp+80h+phkResult], rax; phkResult
0x1800c80d6  call    cs:__imp_RegOpenKeyExA
0x1800c80dc  test    eax, eax
0x1800c80de  jnz     loc_1800C81A2
0x1800c80e4  xor     ebx, ebx
0x1800c80e6  mov     rcx, [rbp+hKey]; hKey
0x1800c80ea  lea     r9, [rbp+cchName]; lpcchName
0x1800c80ee  mov     [rsp+80h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800c80f7  lea     r8, [rbp+Name]; lpName
0x1800c80fb  mov     [rsp+80h+lpcchClass], 0; lpcchClass
0x1800c8104  mov     edx, ebx; dwIndex
0x1800c8106  mov     [rsp+80h+lpClass], 0; lpClass
0x1800c810f  mov     [rsp+80h+phkResult], 0; lpReserved
0x1800c8118  mov     [rbp+cchName], 20h ; ' '
0x1800c811f  call    cs:__imp_RegEnumKeyExA
0x1800c8125  cmp     eax, 103h
0x1800c812a  jz      short loc_1800C8198
0x1800c812c  lea     rcx, [rbp+Name]; pszSrc
0x1800c8130  call    cs:__imp_StrToIntA
0x1800c8136  cmp     eax, esi
0x1800c8138  jnz     short loc_1800C815E
0x1800c813a  mov     rcx, [rbp+hKey]; hKey
0x1800c813e  lea     rax, [rbp+var_30]
0x1800c8142  mov     r9d, 20019h; samDesired
0x1800c8148  mov     [rsp+80h+phkResult], rax; phkResult
0x1800c814d  xor     r8d, r8d; ulOptions
0x1800c8150  lea     rdx, [rbp+Name]; lpSubKey
0x1800c8154  call    cs:__imp_RegOpenKeyExA
0x1800c815a  test    eax, eax
0x1800c815c  jz      short loc_1800C8162
0x1800c815e  inc     ebx
0x1800c8160  jmp     short loc_1800C80E6
0x1800c8162  mov     rcx, [rbp+var_30]; hKey
0x1800c8166  lea     rax, [rbp+cchName]
0x1800c816a  mov     [rsp+80h+lpClass], rax; lpcbData
0x1800c816f  lea     rdx, aIepropfontname; "IEPropFontName"
0x1800c8176  xor     r9d, r9d; lpType
0x1800c8179  mov     [rsp+80h+phkResult], rdi; lpData
0x1800c817e  xor     r8d, r8d; lpReserved
0x1800c8181  mov     [rbp+cchName], 20h ; ' '
0x1800c8188  call    cs:__imp_RegQueryValueExA
0x1800c818e  mov     rcx, [rbp+var_30]; hKey
0x1800c8192  call    cs:__imp_RegCloseKey
0x1800c8198  mov     rcx, [rbp+hKey]; hKey
0x1800c819c  call    cs:__imp_RegCloseKey
0x1800c81a2  xor     eax, eax
0x1800c81a4  mov     ecx, 80004005h
0x1800c81a9  cmp     [rdi], al
0x1800c81ab  cmovz   eax, ecx
0x1800c81ae  mov     rcx, [rbp+var_8]
0x1800c81b2  xor     rcx, rsp; StackCookie
0x1800c81b5  call    __security_check_cookie
0x1800c81ba  mov     rbx, [rsp+80h+arg_8]
0x1800c81c2  add     rsp, 80h
0x1800c81c9  pop     rdi
0x1800c81ca  pop     rsi
0x1800c81cb  pop     rbp
0x1800c81cc  retn
```
