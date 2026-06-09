# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x180004be8`
- end: `0x180004d35`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `333`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180004be8`
- `0x180005130`

## callees

- `0x180004008`
- `0x180004be8`
- `0x18000a5b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004c49`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180004c49`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004cce`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180004cce`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ce2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d06`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004c66`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004ce2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180004d06`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  unsigned int v4; // ebx
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
0x180004be8  mov     [rsp-8+arg_10], rbx
0x180004bed  mov     [rsp-8+arg_18], rsi
0x180004bf2  push    rbp
0x180004bf3  push    rdi
0x180004bf4  push    r14
0x180004bf6  lea     rbp, [rsp-180h]
0x180004bfe  sub     rsp, 280h
0x180004c05  mov     rax, cs:__security_cookie
0x180004c0c  xor     rax, rsp
0x180004c0f  mov     [rbp+190h+var_20], rax
0x180004c16  mov     rsi, rdx
0x180004c19  mov     rdi, rcx
0x180004c1c  xor     r14d, r14d
0x180004c1f  mov     [rsp+290h+hKey], r14
0x180004c24  mov     [rsp+290h+var_240], r14
0x180004c29  mov     [rsp+290h+var_238], r14
0x180004c2e  mov     [rsp+290h+var_230], r14
0x180004c33  lea     rax, [rsp+290h+var_230]
0x180004c38  mov     [rsp+290h+phkResult], rax; phkResult
0x180004c3d  mov     r9d, 2001Fh; samDesired
0x180004c43  xor     r8d, r8d; ulOptions
0x180004c46  mov     rcx, [rcx]; hKey
0x180004c49  call    cs:__imp_RegOpenKeyExW
0x180004c4f  mov     ebx, eax
0x180004c51  mov     rcx, [rsp+290h+hKey]; hKey
0x180004c56  test    eax, eax
0x180004c58  jnz     loc_180004D01
0x180004c5e  mov     ebx, r14d
0x180004c61  test    rcx, rcx
0x180004c64  jz      short loc_180004C6E
0x180004c66  call    cs:__imp_RegCloseKey
0x180004c6c  mov     ebx, eax
0x180004c6e  mov     rcx, [rsp+290h+var_230]
0x180004c73  mov     [rsp+290h+hKey], rcx
0x180004c78  test    ebx, ebx
0x180004c7a  jnz     loc_180004D01
0x180004c80  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x180004c85  jmp     short loc_180004CA1
0x180004c87  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x180004c8c  lea     rcx, [rsp+290h+hKey]; this
0x180004c91  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x180004c96  mov     ebx, eax
0x180004c98  test    eax, eax
0x180004c9a  jnz     short loc_180004CFA
0x180004c9c  mov     rcx, [rsp+290h+hKey]; hKey
0x180004ca1  lea     rax, [rsp+290h+ftLastWriteTime]
0x180004ca6  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180004cab  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x180004cb0  mov     [rsp+290h+lpClass], r14; lpClass
0x180004cb5  mov     [rsp+290h+phkResult], r14; lpReserved
0x180004cba  mov     [rsp+290h+cchName], 100h
0x180004cc2  lea     r9, [rsp+290h+cchName]; lpcchName
0x180004cc7  lea     r8, [rsp+290h+Name]; lpName
0x180004ccc  xor     edx, edx; dwIndex
0x180004cce  call    cs:__imp_RegEnumKeyExW
0x180004cd4  test    eax, eax
0x180004cd6  jz      short loc_180004C87
0x180004cd8  mov     rcx, [rsp+290h+hKey]; hKey
0x180004cdd  test    rcx, rcx
0x180004ce0  jz      short loc_180004CED
0x180004ce2  call    cs:__imp_RegCloseKey
0x180004ce8  mov     [rsp+290h+hKey], r14
0x180004ced  mov     rdx, rsi; unsigned __int16 *
0x180004cf0  mov     rcx, rdi; this
0x180004cf3  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x180004cf8  mov     ebx, eax
0x180004cfa  mov     rcx, [rsp+290h+hKey]
0x180004cff  jmp     short $+2
0x180004d01  test    rcx, rcx
0x180004d04  jz      short loc_180004D0C
0x180004d06  call    cs:__imp_RegCloseKey
0x180004d0c  mov     eax, ebx
0x180004d0e  mov     rcx, [rbp+190h+var_20]
0x180004d15  xor     rcx, rsp; StackCookie
0x180004d18  call    __security_check_cookie
0x180004d1d  lea     r11, [rsp+290h+var_10]
0x180004d25  mov     rbx, [r11+30h]
0x180004d29  mov     rsi, [r11+38h]
0x180004d2d  mov     rsp, r11
0x180004d30  pop     r14
0x180004d32  pop     rdi
0x180004d33  pop     rbp
0x180004d34  retn
```
