# ATL::CRegKey::RecurseDeleteKey(ushort const *)

- ea: `0x14000756c`
- end: `0x1400076d6`
- name: `?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z`
- size: `362`
- prototype: `__int64 __fastcall(ATL::CRegKey *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000756c`
- `0x140007a88`

## callees

- `0x140001500`
- `0x140006d28`
- `0x14000756c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000765e`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x14000765e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400075f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007678`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400076a0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400075f0`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140007678`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400076a0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400075cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400075cd`

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
0x14000756c  mov     [rsp-8+arg_10], rbx
0x140007571  mov     [rsp-8+arg_18], rsi
0x140007576  push    rbp
0x140007577  push    rdi
0x140007578  push    r14
0x14000757a  lea     rbp, [rsp-180h]
0x140007582  sub     rsp, 280h
0x140007589  mov     rax, cs:__security_cookie
0x140007590  xor     rax, rsp
0x140007593  mov     [rbp+190h+var_20], rax
0x14000759a  xor     r14d, r14d
0x14000759d  lea     rax, [rsp+290h+var_230]
0x1400075a2  mov     rdi, rcx
0x1400075a5  mov     [rsp+290h+hKey], r14
0x1400075aa  mov     rcx, [rcx]; hKey
0x1400075ad  mov     r9d, 2001Fh; samDesired
0x1400075b3  xor     r8d, r8d; ulOptions
0x1400075b6  mov     [rsp+290h+var_240], r14
0x1400075bb  mov     [rsp+290h+var_238], r14
0x1400075c0  mov     rsi, rdx
0x1400075c3  mov     [rsp+290h+var_230], r14
0x1400075c8  mov     [rsp+290h+phkResult], rax; phkResult
0x1400075cd  call    cs:__imp_RegOpenKeyExW
0x1400075d4  nop     dword ptr [rax+rax+00h]
0x1400075d9  mov     rcx, [rsp+290h+hKey]; hKey
0x1400075de  mov     ebx, eax
0x1400075e0  test    eax, eax
0x1400075e2  jnz     loc_14000769B
0x1400075e8  mov     ebx, r14d
0x1400075eb  test    rcx, rcx
0x1400075ee  jz      short loc_1400075FE
0x1400075f0  call    cs:__imp_RegCloseKey
0x1400075f7  nop     dword ptr [rax+rax+00h]
0x1400075fc  mov     ebx, eax
0x1400075fe  mov     rcx, [rsp+290h+var_230]
0x140007603  mov     [rsp+290h+hKey], rcx
0x140007608  test    ebx, ebx
0x14000760a  jnz     loc_14000769B
0x140007610  mov     qword ptr [rsp+290h+ftLastWriteTime.dwLowDateTime], r14
0x140007615  jmp     short loc_140007631
0x140007617  lea     rdx, [rsp+290h+Name]; unsigned __int16 *
0x14000761c  lea     rcx, [rsp+290h+hKey]; this
0x140007621  call    ?RecurseDeleteKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::RecurseDeleteKey(ushort const *)
0x140007626  mov     rcx, [rsp+290h+hKey]; hKey
0x14000762b  mov     ebx, eax
0x14000762d  test    eax, eax
0x14000762f  jnz     short loc_14000769B
0x140007631  lea     rax, [rsp+290h+ftLastWriteTime]
0x140007636  mov     [rsp+290h+cchName], 100h
0x14000763e  mov     [rsp+290h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140007643  lea     r9, [rsp+290h+cchName]; lpcchName
0x140007648  mov     [rsp+290h+lpcchClass], r14; lpcchClass
0x14000764d  lea     r8, [rsp+290h+Name]; lpName
0x140007652  mov     [rsp+290h+lpClass], r14; lpClass
0x140007657  xor     edx, edx; dwIndex
0x140007659  mov     [rsp+290h+phkResult], r14; lpReserved
0x14000765e  call    cs:__imp_RegEnumKeyExW
0x140007665  nop     dword ptr [rax+rax+00h]
0x14000766a  test    eax, eax
0x14000766c  jz      short loc_140007617
0x14000766e  mov     rcx, [rsp+290h+hKey]; hKey
0x140007673  test    rcx, rcx
0x140007676  jz      short loc_140007689
0x140007678  call    cs:__imp_RegCloseKey
0x14000767f  nop     dword ptr [rax+rax+00h]
0x140007684  mov     [rsp+290h+hKey], r14
0x140007689  mov     rdx, rsi; unsigned __int16 *
0x14000768c  mov     rcx, rdi; this
0x14000768f  call    ?DeleteSubKey@CRegKey@ATL@@QEAAJPEBG@Z; ATL::CRegKey::DeleteSubKey(ushort const *)
0x140007694  mov     rcx, [rsp+290h+hKey]; hKey
0x140007699  mov     ebx, eax
0x14000769b  test    rcx, rcx
0x14000769e  jz      short loc_1400076AC
0x1400076a0  call    cs:__imp_RegCloseKey
0x1400076a7  nop     dword ptr [rax+rax+00h]
0x1400076ac  mov     eax, ebx
0x1400076ae  mov     rcx, [rbp+190h+var_20]
0x1400076b5  xor     rcx, rsp; StackCookie
0x1400076b8  call    __security_check_cookie
0x1400076bd  lea     r11, [rsp+290h+var_10]
0x1400076c5  mov     rbx, [r11+30h]
0x1400076c9  mov     rsi, [r11+38h]
0x1400076cd  mov     rsp, r11
0x1400076d0  pop     r14
0x1400076d2  pop     rdi
0x1400076d3  pop     rbp
0x1400076d4  retn
```
