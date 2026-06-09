# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1800034a8`
- end: `0x1800035f5`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `333`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800034a8`
- `0x1800039f4`

## callees

- `0x180002e08`
- `0x1800034a8`
- `0x180015cf0`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180003509`
- `ADVAPI32!RegOpenKeyExW` at `0x180003509`
- `ADVAPI32!RegEnumKeyExW` at `0x18000358e`
- `ADVAPI32!RegEnumKeyExW` at `0x18000358e`
- `ADVAPI32!RegCloseKey` at `0x180003526`
- `ADVAPI32!RegCloseKey` at `0x1800035a2`
- `ADVAPI32!RegCloseKey` at `0x1800035c6`
- `ADVAPI32!RegCloseKey` at `0x180003526`
- `ADVAPI32!RegCloseKey` at `0x1800035a2`
- `ADVAPI32!RegCloseKey` at `0x1800035c6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  DWORD v4; // ebx
  HKEY v5; // rcx
  HKEY v6; // rcx
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  phkResult = 0;
  v4 = RegOpenKeyExW(*this, a2, 0, 0x2001Fu, &phkResult);
  v5 = 0;
  if ( !v4 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v4 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      if ( v4 )
        goto LABEL_9;
      v6 = hKey[0];
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v4 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
LABEL_9:
    v5 = hKey[0];
  }
  if ( v5 )
    RegCloseKey(v5);
  return v4;
}

```

## disassembly

```asm
0x1800034a8  mov     [rsp-8+arg_10], rbx
0x1800034ad  mov     [rsp-8+arg_18], rsi
0x1800034b2  push    rbp
0x1800034b3  push    rdi
0x1800034b4  push    r14
0x1800034b6  lea     rbp, [rsp-180h]
0x1800034be  sub     rsp, 280h
0x1800034c5  mov     rax, cs:__security_cookie
0x1800034cc  xor     rax, rsp
0x1800034cf  mov     [rbp+190h+var_20], rax
0x1800034d6  mov     rsi, rdx
0x1800034d9  mov     rdi, rcx
0x1800034dc  xor     r14d, r14d
0x1800034df  mov     [rsp+290h+hKey], r14
0x1800034e4  mov     [rsp+290h+var_240], r14
0x1800034e9  mov     [rsp+290h+var_238], r14
0x1800034ee  mov     [rsp+290h+var_230], r14
0x1800034f3  lea     rax, [rsp+290h+var_230]
0x1800034f8  mov     [rsp+290h+phkResult], rax; phkResult
0x1800034fd  mov     r9d, 2001Fh; samDesired
0x180003503  xor     r8d, r8d; ulOptions
0x180003506  mov     rcx, [rcx]; hKey
0x180003509  call    cs:__imp_RegOpenKeyExW
0x18000350f  mov     ebx, eax
0x180003511  mov     rcx, [rsp+290h+hKey]; hKey
0x180003516  test    eax, eax
0x180003518  jnz     loc_1800035C1
0x18000351e  mov     ebx, r14d
0x180003521  test    rcx, rcx
0x180003524  jz      short loc_18000352E
0x180003526  call    cs:__imp_RegCloseKey
0x18000352c  mov     ebx, eax
0x18000352e  mov     rcx, [rsp+290h+var_230]
0x180003533  mov     [rsp+290h+hKey], rcx
0x180003538  test    ebx, ebx
0x18000353a  jnz     loc_1800035C1
0x180003540  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180003545  jmp     short loc_180003561
0x180003547  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x18000354c  lea     rcx, [rsp+290h+hKey]; this
0x180003551  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180003556  mov     ebx, eax
0x180003558  test    eax, eax
0x18000355a  jnz     short loc_1800035BA
0x18000355c  mov     rcx, [rsp+290h+hKey]; hKey
0x180003561  lea     rax, [rsp+290h+ftLastWriteTime]
0x180003566  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x18000356b  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180003570  mov     [rsp+290h+lpClass], r14; lpClass
0x180003575  mov     [rsp+290h+phkResult], r14; lpReserved
0x18000357a  mov     [rsp+290h+cchName], 100h
0x180003582  lea     r9, [rsp+290h+cchName]; lpcchName
0x180003587  lea     r8, [rsp+290h+Name]; lpName
0x18000358c  xor     edx, edx; dwIndex
0x18000358e  call    cs:__imp_RegEnumKeyExW
0x180003594  test    eax, eax
0x180003596  jz      short loc_180003547
0x180003598  mov     rcx, [rsp+290h+hKey]; hKey
0x18000359d  test    rcx, rcx
0x1800035a0  jz      short loc_1800035AD
0x1800035a2  call    cs:__imp_RegCloseKey
0x1800035a8  mov     [rsp+290h+hKey], r14
0x1800035ad  mov     rdx, rsi; unsigned __int16 *
0x1800035b0  mov     rcx, rdi; this
0x1800035b3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x1800035b8  mov     ebx, eax
0x1800035ba  mov     rcx, [rsp+290h+hKey]
0x1800035bf  jmp     short $+2
0x1800035c1  test    rcx, rcx
0x1800035c4  jz      short loc_1800035CC
0x1800035c6  call    cs:__imp_RegCloseKey
0x1800035cc  mov     eax, ebx
0x1800035ce  mov     rcx, [rbp+190h+var_20]
0x1800035d5  xor     rcx, rsp; StackCookie
0x1800035d8  call    __security_check_cookie
0x1800035dd  lea     r11, [rsp+290h+var_10]
0x1800035e5  mov     rbx, [r11+30h]
0x1800035e9  mov     rsi, [r11+38h]
0x1800035ed  mov     rsp, r11
0x1800035f0  pop     r14
0x1800035f2  pop     rdi
0x1800035f3  pop     rbp
0x1800035f4  retn
```
