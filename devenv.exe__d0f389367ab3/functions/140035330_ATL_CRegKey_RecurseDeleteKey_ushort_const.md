# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x140035330`
- end: `0x140035485`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `341`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140035330`
- `0x140035738`
- `0x14004c620`
- `0x1400515c0`
- `0x1400528a0`

## callees

- `0x140001020`
- `0x140035330`
- `0x140035488`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1400353ae`
- `ADVAPI32!RegCloseKey` at `0x140035430`
- `ADVAPI32!RegCloseKey` at `0x140035457`
- `ADVAPI32!RegCloseKey` at `0x1400353ae`
- `ADVAPI32!RegCloseKey` at `0x140035430`
- `ADVAPI32!RegCloseKey` at `0x140035457`
- `ADVAPI32!RegOpenKeyExW` at `0x140035395`
- `ADVAPI32!RegOpenKeyExW` at `0x140035395`
- `ADVAPI32!RegEnumKeyExW` at `0x14003541c`
- `ADVAPI32!RegEnumKeyExW` at `0x14003541c`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(ATL::CRegKey *this, const unsigned __int16 *a2)
{
  int v2; // edi
  HKEY v4; // rcx
  REGSAM v5; // edi
  LSTATUS v7; // eax
  HKEY v8; // rcx
  unsigned int v9; // ebx
  unsigned int v10; // eax
  LSTATUS v11; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v15; // [rsp+50h] [rbp-B0h]
  __int64 v16; // [rsp+58h] [rbp-A8h]
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  v2 = *((_DWORD *)this + 2);
  hKey = 0;
  v4 = *(HKEY *)this;
  v5 = v2 | 0x2001F;
  v15 = 0;
  v16 = 0;
  phkResult = 0;
  v7 = RegOpenKeyExW(v4, a2, 0, v5, &phkResult);
  v8 = 0;
  v9 = v7;
  if ( !v7 )
  {
    v9 = 0;
    v8 = phkResult;
    hKey = phkResult;
    v15 = v5 & 0x300;
  }
  if ( !v9 )
  {
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v8, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v10 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)&hKey, Name);
      v8 = hKey;
      v9 = v10;
      if ( v10 )
        goto LABEL_10;
    }
    if ( hKey )
    {
      RegCloseKey(hKey);
      hKey = 0;
    }
    v15 = 0;
    v11 = ATL::CRegKey::DeleteSubKey(this, a2);
    v8 = hKey;
    v9 = v11;
  }
LABEL_10:
  if ( v8 )
    RegCloseKey(v8);
  return v9;
}

```

## disassembly

```asm
0x140035330  mov     [rsp-8+arg_10], rbx
0x140035335  push    rbp
0x140035336  push    rsi
0x140035337  push    rdi
0x140035338  push    r14
0x14003533a  push    r15
0x14003533c  lea     rbp, [rsp-180h]
0x140035344  sub     rsp, 280h
0x14003534b  mov     rax, cs:__security_cookie
0x140035352  xor     rax, rsp
0x140035355  mov     [rbp+1A0h+var_30], rax
0x14003535c  mov     edi, [rcx+8]
0x14003535f  lea     rax, [rsp+2A0h+var_240]
0x140035364  xor     r15d, r15d
0x140035367  mov     [rsp+2A0h+phkResult], rax; phkResult
0x14003536c  mov     rsi, rcx
0x14003536f  mov     [rsp+2A0h+hKey], r15
0x140035374  mov     rcx, [rcx]; hKey
0x140035377  or      edi, 2001Fh
0x14003537d  mov     r9d, edi; samDesired
0x140035380  mov     [rsp+2A0h+var_250], r15d
0x140035385  xor     r8d, r8d; ulOptions
0x140035388  mov     [rsp+2A0h+var_248], r15
0x14003538d  mov     r14, rdx
0x140035390  mov     [rsp+2A0h+var_240], r15
0x140035395  call    cs:__imp_RegOpenKeyExW
0x14003539b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1400353a0  mov     ebx, eax
0x1400353a2  test    eax, eax
0x1400353a4  jnz     short loc_1400353CA
0x1400353a6  mov     ebx, r15d
0x1400353a9  test    rcx, rcx
0x1400353ac  jz      short loc_1400353B6
0x1400353ae  call    cs:__imp_RegCloseKey
0x1400353b4  mov     ebx, eax
0x1400353b6  mov     rcx, [rsp+2A0h+var_240]
0x1400353bb  and     edi, 300h
0x1400353c1  mov     [rsp+2A0h+hKey], rcx
0x1400353c6  mov     [rsp+2A0h+var_250], edi
0x1400353ca  test    ebx, ebx
0x1400353cc  jnz     loc_140035452
0x1400353d2  mov     edi, 100h
0x1400353d7  jmp     short loc_1400353F3
0x1400353d9  lea     rdx, [rsp+2A0h+Name]; unsigned __int16 *
0x1400353de  lea     rcx, [rsp+2A0h+hKey]; this
0x1400353e3  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z
0x1400353e8  mov     rcx, [rsp+2A0h+hKey]; hKey
0x1400353ed  mov     ebx, eax
0x1400353ef  test    eax, eax
0x1400353f1  jnz     short loc_140035452
0x1400353f3  lea     rax, [rsp+2A0h+ftLastWriteTime]
0x1400353f8  mov     [rsp+2A0h+cchName], edi
0x1400353fc  mov     [rsp+2A0h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140035401  lea     r9, [rsp+2A0h+cchName]; lpcchName
0x140035406  mov     [rsp+2A0h+lpcchClass], r15; lpcchClass
0x14003540b  lea     r8, [rsp+2A0h+Name]; lpName
0x140035410  mov     [rsp+2A0h+lpClass], r15; lpClass
0x140035415  xor     edx, edx; dwIndex
0x140035417  mov     [rsp+2A0h+phkResult], r15; lpReserved
0x14003541c  call    cs:__imp_RegEnumKeyExW
0x140035422  test    eax, eax
0x140035424  jz      short loc_1400353D9
0x140035426  mov     rcx, [rsp+2A0h+hKey]; hKey
0x14003542b  test    rcx, rcx
0x14003542e  jz      short loc_14003543B
0x140035430  call    cs:__imp_RegCloseKey
0x140035436  mov     [rsp+2A0h+hKey], r15
0x14003543b  mov     rdx, r14; unsigned __int16 *
0x14003543e  mov     [rsp+2A0h+var_250], r15d
0x140035443  mov     rcx, rsi; this
0x140035446  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z
0x14003544b  mov     rcx, [rsp+2A0h+hKey]; hKey
0x140035450  mov     ebx, eax
0x140035452  test    rcx, rcx
0x140035455  jz      short loc_14003545D
0x140035457  call    cs:__imp_RegCloseKey
0x14003545d  mov     eax, ebx
0x14003545f  mov     rcx, [rbp+1A0h+var_30]
0x140035466  xor     rcx, rsp; StackCookie
0x140035469  call    __security_check_cookie
0x14003546e  mov     rbx, [rsp+2A0h+arg_10]
0x140035476  add     rsp, 280h
0x14003547d  pop     r15
0x14003547f  pop     r14
0x140035481  pop     rdi
0x140035482  pop     rsi
0x140035483  pop     rbp
0x140035484  retn
```
