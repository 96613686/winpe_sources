# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x1400154e0`
- end: `0x14001564a`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400154e0`
- `0x140015bdc`

## callees

- `0x1400100a4`
- `0x1400154e0`
- `0x14004ad80`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140015564`
- `ADVAPI32!RegCloseKey` at `0x1400155ec`
- `ADVAPI32!RegCloseKey` at `0x140015614`
- `ADVAPI32!RegCloseKey` at `0x140015564`
- `ADVAPI32!RegCloseKey` at `0x1400155ec`
- `ADVAPI32!RegCloseKey` at `0x140015614`
- `ADVAPI32!RegEnumKeyExW` at `0x1400155d2`
- `ADVAPI32!RegEnumKeyExW` at `0x1400155d2`
- `ADVAPI32!RegOpenKeyExW` at `0x140015541`
- `ADVAPI32!RegOpenKeyExW` at `0x140015541`

## pseudocode

```c
__int64 __fastcall ATL::CRegKey::RecurseDeleteKey(HKEY *this, const unsigned __int16 *a2)
{
  HKEY v3; // rcx
  LSTATUS v5; // eax
  HKEY v6; // rcx
  DWORD v7; // ebx
  DWORD v8; // eax
  DWORD v9; // eax
  DWORD cchName; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey[3]; // [rsp+48h] [rbp-B8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[256]; // [rsp+70h] [rbp-90h] BYREF

  memset(hKey, 0, sizeof(hKey));
  v3 = *this;
  phkResult = 0;
  v5 = RegOpenKeyExW(v3, a2, 0, 0x2001Fu, &phkResult);
  v6 = 0;
  v7 = v5;
  if ( !v5 )
  {
    v6 = phkResult;
    hKey[0] = phkResult;
    ftLastWriteTime = 0;
    while ( 1 )
    {
      cchName = 256;
      if ( RegEnumKeyExW(v6, 0, Name, &cchName, 0, 0, 0, &ftLastWriteTime) )
        break;
      v8 = ATL::CRegKey::RecurseDeleteKey((ATL::CRegKey *)hKey, Name);
      v6 = hKey[0];
      v7 = v8;
      if ( v8 )
        goto LABEL_8;
    }
    if ( hKey[0] )
    {
      RegCloseKey(hKey[0]);
      hKey[0] = 0;
    }
    v9 = ATL::CRegKey::DeleteSubKey((ATL::CRegKey *)this, a2);
    v6 = hKey[0];
    v7 = v9;
  }
LABEL_8:
  if ( v6 )
    RegCloseKey(v6);
  return v7;
}

```

## disassembly

```asm
0x1400154e0  mov     [rsp-8+arg_10], rbx
0x1400154e5  mov     [rsp-8+arg_18], rsi
0x1400154ea  push    rbp
0x1400154eb  push    rdi
0x1400154ec  push    r14
0x1400154ee  lea     rbp, [rsp-180h]
0x1400154f6  sub     rsp, 280h
0x1400154fd  mov     rax, cs:__security_cookie
0x140015504  xor     rax, rsp
0x140015507  mov     [rbp+190h+var_20], rax
0x14001550e  xor     r14d, r14d
0x140015511  lea     rax, [rsp+290h+var_230]
0x140015516  mov     rdi, rcx
0x140015519  mov     [rsp+290h+hKey], r14
0x14001551e  mov     rcx, [rcx]; hKey
0x140015521  mov     r9d, 2001Fh; samDesired
0x140015527  xor     r8d, r8d; ulOptions
0x14001552a  mov     [rsp+290h+var_240], r14
0x14001552f  mov     [rsp+290h+var_238], r14
0x140015534  mov     rsi, rdx
0x140015537  mov     [rsp+290h+var_230], r14
0x14001553c  mov     [rsp+290h+phkResult], rax; phkResult
0x140015541  call    cs:__imp_RegOpenKeyExW
0x140015548  nop     dword ptr [rax+rax+00h]
0x14001554d  mov     rcx, [rsp+290h+hKey]; hKey
0x140015552  mov     ebx, eax
0x140015554  test    eax, eax
0x140015556  jnz     loc_14001560F
0x14001555c  mov     ebx, r14d
0x14001555f  test    rcx, rcx
0x140015562  jz      short loc_140015572
0x140015564  call    cs:__imp_RegCloseKey
0x14001556b  nop     dword ptr [rax+rax+00h]
0x140015570  mov     ebx, eax
0x140015572  mov     rcx, [rsp+290h+var_230]
0x140015577  mov     [rsp+290h+hKey], rcx
0x14001557c  test    ebx, ebx
0x14001557e  jnz     loc_14001560F
0x140015584  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x140015589  jmp     short loc_1400155A5
0x14001558b  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x140015590  lea     rcx, [rsp+290h+hKey]; this
0x140015595  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x14001559a  mov     rcx, [rsp+290h+hKey]; hKey
0x14001559f  mov     ebx, eax
0x1400155a1  test    eax, eax
0x1400155a3  jnz     short loc_14001560F
0x1400155a5  lea     rax, [rsp+290h+ftLastWriteTime]
0x1400155aa  mov     [rsp+290h+cchName], 100h
0x1400155b2  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1400155b7  lea     r9, [rsp+290h+cchName]; lpcchName
0x1400155bc  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x1400155c1  lea     r8, [rsp+290h+Name]; lpName
0x1400155c6  mov     [rsp+290h+lpClass], r14; lpClass
0x1400155cb  xor     edx, edx; dwIndex
0x1400155cd  mov     [rsp+290h+phkResult], r14; lpReserved
0x1400155d2  call    cs:__imp_RegEnumKeyExW
0x1400155d9  nop     dword ptr [rax+rax+00h]
0x1400155de  test    eax, eax
0x1400155e0  jz      short loc_14001558B
0x1400155e2  mov     rcx, [rsp+290h+hKey]; hKey
0x1400155e7  test    rcx, rcx
0x1400155ea  jz      short loc_1400155FD
0x1400155ec  call    cs:__imp_RegCloseKey
0x1400155f3  nop     dword ptr [rax+rax+00h]
0x1400155f8  mov     [rsp+290h+hKey], r14
0x1400155fd  mov     rdx, rsi; unsigned __int16 *
0x140015600  mov     rcx, rdi; this
0x140015603  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140015608  mov     rcx, [rsp+290h+hKey]; hKey
0x14001560d  mov     ebx, eax
0x14001560f  test    rcx, rcx
0x140015612  jz      short loc_140015620
0x140015614  call    cs:__imp_RegCloseKey
0x14001561b  nop     dword ptr [rax+rax+00h]
0x140015620  mov     eax, ebx
0x140015622  mov     rcx, [rbp+190h+var_20]
0x140015629  xor     rcx, rsp; StackCookie
0x14001562c  call    __security_check_cookie
0x140015631  lea     r11, [rsp+290h+var_10]
0x140015639  mov     rbx, [r11+30h]
0x14001563d  mov     rsi, [r11+38h]
0x140015641  mov     rsp, r11
0x140015644  pop     r14
0x140015646  pop     rdi
0x140015647  pop     rbp
0x140015648  retn
```
