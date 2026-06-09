# RegistryPath::EnumKey(ulong)

- ea: `0x180095dfc`
- end: `0x180095f94`
- name: `?EnumKey@RegistryPath@@QEAAKK@Z`
- size: `408`
- prototype: `unsigned int __fastcall(RegistryPath *__hidden this, DWORD dwIndex)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180096ad4`
- `0x180096d08`

## callees

- `0x1800051d4`
- `0x180005ba0`
- `0x180006190`
- `0x1800084f4`
- `0x18001bd30`
- `0x18001c924`
- `0x180043e54`
- `0x180044300`
- `0x180095dfc`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180095e73`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x180095e73`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180095ee8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180095ee8`

## string_xrefs

- `0x180095f60`: `%s: This path object has not been properly initiliazed. Either root key or full path is NULL.`
- `0x180095e97`: `RegistryPath::OpenSubKey`
- `0x180095f38`: `RegistryPath::Append`
- `0x180095f49`: `RegistryPath::EnumKey`
- `0x180095f59`: `RegistryPath::EnumKey`
- `0x180095f19`: `%s: Cannot enumerate keys under registry key "%s". Win32 error code: 0x%08x.`

## pseudocode

```c
__int64 __fastcall RegistryPath::EnumKey(RegistryPath *this, DWORD dwIndex)
{
  __int64 v4; // rdx
  HKEY *v5; // rsi
  HKEY v6; // rax
  unsigned int v7; // eax
  unsigned int v8; // edi
  const wchar_t *v9; // r8
  LSTATUS v10; // eax
  DWORD cchName[4]; // [rsp+40h] [rbp-248h] BYREF
  WCHAR Name[264]; // [rsp+50h] [rbp-238h] BYREF

  cchName[0] = 260;
  Name[0] = 0;
  if ( *((_QWORD *)this + 4) && !(unsigned int)IsEmptyString(*(const unsigned __int16 **)this) )
  {
    v5 = (HKEY *)((char *)this + 48);
    if ( *((_QWORD *)this + 6) )
    {
      *(_WORD *)(v4 + 2LL * *((_QWORD *)this + 7)) = 0;
      RegistryPath::CloseSubKey(this);
    }
    else
    {
      v6 = (HKEY)*((_QWORD *)this + 5);
      if ( v6 )
      {
        *v5 = v6;
        *((_QWORD *)this + 5) = 0;
      }
      else
      {
        v7 = RegistryPath::OpenSubKey(this, 8u, (HKEY *)this + 6, 0);
        v8 = v7;
        if ( v7 )
        {
          v9 = L"RegistryPath::OpenSubKey";
          goto LABEL_16;
        }
      }
      *((_QWORD *)this + 7) = wcsnlen(*(const wchar_t **)this, *((_QWORD *)this + 1));
    }
    v10 = RegEnumKeyExW(*v5, dwIndex, Name, cchName, 0, 0, 0, 0);
    v8 = v10;
    if ( v10 == 259 )
    {
      RegistryPath::EndEnumKey(this);
      return v8;
    }
    if ( v10 )
    {
      Logger::WriteRegistryFailureEvent(v10, L"RegEnumKeyExW", *(const unsigned __int16 **)this);
      Logger::TraceError(
        L"%s: Cannot enumerate keys under registry key \"%s\". Win32 error code: 0x%08x.",
        L"RegistryPath::EnumKey",
        *(_QWORD *)this,
        v8);
      return v8;
    }
    v7 = RegistryPath::Append((const wchar_t **)this, Name);
    v8 = v7;
    if ( !v7 )
      return v8;
    v9 = L"RegistryPath::Append";
LABEL_16:
    Logger::TraceError(L"%s: %s failed with win32 error code: 0x%08x.", L"RegistryPath::EnumKey", v9, v7);
    return v8;
  }
  Logger::TraceError(
    L"%s: This path object has not been properly initiliazed. Either root key or full path is NULL.",
    L"RegistryPath::EnumKey");
  return 87;
}

```

## disassembly

```asm
0x180095dfc  mov     [rsp+arg_10], rbx
0x180095e01  push    rbp
0x180095e02  push    rsi
0x180095e03  push    rdi
0x180095e04  sub     rsp, 270h
0x180095e0b  mov     rax, cs:__security_cookie
0x180095e12  xor     rax, rsp
0x180095e15  mov     [rsp+288h+var_28], rax
0x180095e1d  xor     eax, eax
0x180095e1f  mov     [rsp+288h+cchName], 104h
0x180095e27  mov     ebp, edx
0x180095e29  mov     rbx, rcx
0x180095e2c  mov     [rsp+288h+Name], ax
0x180095e31  cmp     [rcx+20h], rax
0x180095e35  jz      loc_180095F59
0x180095e3b  mov     rdx, [rcx]
0x180095e3e  mov     rcx, rdx; unsigned __int16 *
0x180095e41  call    ?IsEmptyString@@YAHPEBG@Z; IsEmptyString(ushort const *)
0x180095e46  test    eax, eax
0x180095e48  jnz     loc_180095F59
0x180095e4e  lea     rsi, [rbx+30h]
0x180095e52  cmp     qword ptr [rsi], 0
0x180095e56  jnz     short loc_180095EA3
0x180095e58  mov     rax, [rbx+28h]
0x180095e5c  test    rax, rax
0x180095e5f  jz      short loc_180095E7F
0x180095e61  mov     [rsi], rax
0x180095e64  mov     qword ptr [rbx+28h], 0
0x180095e6c  mov     rdx, [rbx+8]; MaxCount
0x180095e70  mov     rcx, [rbx]; Source
0x180095e73  call    cs:__imp_wcsnlen
0x180095e79  mov     [rbx+38h], rax
0x180095e7d  jmp     short loc_180095EB5
0x180095e7f  xor     r9d, r9d; int
0x180095e82  mov     r8, rsi; HKEY *
0x180095e85  mov     rcx, rbx; this
0x180095e88  lea     edx, [r9+8]; unsigned int
0x180095e8c  call    ?OpenSubKey@RegistryPath@@QEBAKKPEAPEAUHKEY__@@H@Z; RegistryPath::OpenSubKey(ulong,HKEY__ * *,int)
0x180095e91  mov     edi, eax
0x180095e93  test    eax, eax
0x180095e95  jz      short loc_180095E6C
0x180095e97  lea     r8, aRegistrypathOp; "RegistryPath::OpenSubKey"
0x180095e9e  jmp     loc_180095F3F
0x180095ea3  mov     rcx, [rbx+38h]
0x180095ea7  xor     eax, eax
0x180095ea9  mov     [rdx+rcx*2], ax
0x180095ead  mov     rcx, rbx; this
0x180095eb0  call    ?CloseSubKey@RegistryPath@@QEAAXXZ; RegistryPath::CloseSubKey(void)
0x180095eb5  mov     rcx, [rsi]; hKey
0x180095eb8  lea     r9, [rsp+288h+cchName]; lpcchName
0x180095ebd  mov     [rsp+288h+lpftLastWriteTime], 0; lpftLastWriteTime
0x180095ec6  lea     r8, [rsp+288h+Name]; lpName
0x180095ecb  mov     [rsp+288h+lpcchClass], 0; lpcchClass
0x180095ed4  mov     edx, ebp; dwIndex
0x180095ed6  mov     [rsp+288h+lpClass], 0; lpClass
0x180095edf  mov     [rsp+288h+lpReserved], 0; lpReserved
0x180095ee8  call    cs:__imp_RegEnumKeyExW
0x180095eee  mov     edi, eax
0x180095ef0  cmp     eax, 103h
0x180095ef5  jnz     short loc_180095F01
0x180095ef7  mov     rcx, rbx; this
0x180095efa  call    ?EndEnumKey@RegistryPath@@QEAAXXZ; RegistryPath::EndEnumKey(void)
0x180095eff  jmp     short loc_180095F55
0x180095f01  test    edi, edi
0x180095f03  jz      short loc_180095F25
0x180095f05  mov     r8, [rbx]; unsigned __int16 *
0x180095f08  lea     rdx, aRegenumkeyexw; "RegEnumKeyExW"
0x180095f0f  mov     ecx, edi; unsigned int
0x180095f11  call    ?WriteRegistryFailureEvent@Logger@@SAJKPEBG0@Z; Logger::WriteRegistryFailureEvent(ulong,ushort const *,ushort const *)
0x180095f16  mov     r8, [rbx]
0x180095f19  lea     rcx, aSCannotEnumera_2; "%s: Cannot enumerate keys under registr"...
0x180095f20  mov     r9d, edi
0x180095f23  jmp     short loc_180095F49
0x180095f25  lea     rdx, [rsp+288h+Name]; unsigned __int16 *
0x180095f2a  mov     rcx, rbx; this
0x180095f2d  call    ?Append@RegistryPath@@QEAAKPEBG@Z; RegistryPath::Append(ushort const *)
0x180095f32  mov     edi, eax
0x180095f34  test    eax, eax
0x180095f36  jz      short loc_180095F55
0x180095f38  lea     r8, aRegistrypathAp; "RegistryPath::Append"
0x180095f3f  mov     r9d, eax
0x180095f42  lea     rcx, Str; "%s: %s failed with win32 error code: 0x"...
0x180095f49  lea     rdx, aRegistrypathEn; "RegistryPath::EnumKey"
0x180095f50  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095f55  mov     eax, edi
0x180095f57  jmp     short loc_180095F71
0x180095f59  lea     rdx, aRegistrypathEn; "RegistryPath::EnumKey"
0x180095f60  lea     rcx, aSThisPathObjec; "%s: This path object has not been prope"...
0x180095f67  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180095f6c  mov     eax, 57h ; 'W'
0x180095f71  mov     rcx, [rsp+288h+var_28]
0x180095f79  xor     rcx, rsp; StackCookie
0x180095f7c  call    __security_check_cookie
0x180095f81  mov     rbx, [rsp+288h+arg_10]
0x180095f89  add     rsp, 270h
0x180095f90  pop     rdi
0x180095f91  pop     rsi
0x180095f92  pop     rbp
0x180095f93  retn
```
