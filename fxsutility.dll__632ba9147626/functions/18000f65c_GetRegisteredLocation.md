# GetRegisteredLocation

- ea: `0x18000f65c`
- end: `0x18000f77b`
- name: `GetRegisteredLocation`
- size: `287`
- prototype: `__int64 __fastcall(LPSTR lpDst)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000f784`

## callees

- `0x18000f65c`
- `0x180015cf0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsA` at `0x18000f70c`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18000f70c`
- `ADVAPI32!RegCloseKey` at `0x18000f757`
- `ADVAPI32!RegCloseKey` at `0x18000f757`
- `ADVAPI32!RegQueryValueExA` at `0x18000f6ec`
- `ADVAPI32!RegQueryValueExA` at `0x18000f6ec`
- `ADVAPI32!RegOpenKeyExA` at `0x18000f6a8`
- `ADVAPI32!RegOpenKeyExA` at `0x18000f6a8`

## string_xrefs

- `0x18000f6a1`: `CLSID\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\InprocServer32`

## pseudocode

```c
__int64 __fastcall GetRegisteredLocation(LPSTR lpDst)
{
  __int64 v2; // rbx
  unsigned int v3; // esi
  CHAR *v4; // rcx
  __int64 v5; // rax
  LPSTR v6; // rax
  DWORD Type; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbData; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[272]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  if ( RegOpenKeyExA(
         HKEY_CLASSES_ROOT,
         "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\\InprocServer32",
         0,
         0x20019u,
         &hKey) )
  {
    return 0;
  }
  Type = 1;
  v2 = 260;
  cbData = 260;
  v3 = 0;
  if ( !RegQueryValueExA(hKey, 0, 0, &Type, Data, &cbData) )
  {
    v4 = (CHAR *)Data;
    Data[259] = 0;
    if ( Type == 2 )
    {
      LOBYTE(v3) = ExpandEnvironmentStringsA((LPCSTR)Data, lpDst, 0x104u) - 1 <= 0x103;
    }
    else
    {
      v5 = 2147483646;
      do
      {
        if ( !v5 )
          break;
        if ( !*v4 )
          break;
        *lpDst++ = *v4++;
        --v5;
        --v2;
      }
      while ( v2 );
      v6 = lpDst - 1;
      if ( v2 )
        v6 = lpDst;
      *v6 = 0;
      LOBYTE(v3) = v2 != 0;
    }
  }
  RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x18000f65c  push    rbp
0x18000f65e  push    rbx
0x18000f65f  push    rsi
0x18000f660  push    rdi
0x18000f661  lea     rbp, [rsp-68h]
0x18000f666  sub     rsp, 168h
0x18000f66d  mov     rax, cs:__security_cookie
0x18000f674  xor     rax, rsp
0x18000f677  mov     [rbp+80h+var_30], rax
0x18000f67b  mov     rdi, rcx
0x18000f67e  mov     [rsp+180h+hKey], 0
0x18000f687  lea     rax, [rsp+180h+hKey]
0x18000f68c  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18000f693  mov     r9d, 20019h; samDesired
0x18000f699  mov     [rsp+180h+phkResult], rax; phkResult
0x18000f69e  xor     r8d, r8d; ulOptions
0x18000f6a1  lea     rdx, aClsidAdb880a6D; "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003"...
0x18000f6a8  call    cs:__imp_RegOpenKeyExA
0x18000f6ae  test    eax, eax
0x18000f6b0  jnz     loc_18000F761
0x18000f6b6  mov     rcx, [rsp+180h+hKey]; hKey
0x18000f6bb  lea     rax, [rsp+180h+cbData]
0x18000f6c0  mov     [rsp+180h+lpcbData], rax; lpcbData
0x18000f6c5  lea     r9, [rsp+180h+Type]; lpType
0x18000f6ca  lea     rax, [rsp+180h+Data]
0x18000f6cf  mov     [rsp+180h+Type], 1
0x18000f6d7  mov     ebx, 104h
0x18000f6dc  mov     [rsp+180h+phkResult], rax; lpData
0x18000f6e1  xor     r8d, r8d; lpReserved
0x18000f6e4  mov     [rsp+180h+cbData], ebx
0x18000f6e8  xor     edx, edx; lpValueName
0x18000f6ea  xor     esi, esi
0x18000f6ec  call    cs:__imp_RegQueryValueExA
0x18000f6f2  test    eax, eax
0x18000f6f4  jnz     short loc_18000F752
0x18000f6f6  cmp     [rsp+180h+Type], 2
0x18000f6fb  lea     rcx, [rsp+180h+Data]; lpSrc
0x18000f700  mov     [rbp+80h+var_3D], sil
0x18000f704  jnz     short loc_18000F71F
0x18000f706  mov     r8d, ebx; nSize
0x18000f709  mov     rdx, rdi; lpDst
0x18000f70c  call    cs:__imp_ExpandEnvironmentStringsA
0x18000f712  dec     eax
0x18000f714  cmp     eax, 103h
0x18000f719  setbe   sil
0x18000f71d  jmp     short loc_18000F752
0x18000f71f  mov     eax, 7FFFFFFEh
0x18000f724  test    rax, rax
0x18000f727  jz      short loc_18000F740
0x18000f729  mov     dl, [rcx]
0x18000f72b  test    dl, dl
0x18000f72d  jz      short loc_18000F740
0x18000f72f  mov     [rdi], dl
0x18000f731  inc     rcx
0x18000f734  inc     rdi
0x18000f737  dec     rax
0x18000f73a  sub     rbx, 1
0x18000f73e  jnz     short loc_18000F724
0x18000f740  test    rbx, rbx
0x18000f743  lea     rax, [rdi-1]
0x18000f747  cmovnz  rax, rdi
0x18000f74b  mov     [rax], sil
0x18000f74e  setnz   sil
0x18000f752  mov     rcx, [rsp+180h+hKey]; hKey
0x18000f757  call    cs:__imp_RegCloseKey
0x18000f75d  mov     eax, esi
0x18000f75f  jmp     short loc_18000F763
0x18000f761  xor     eax, eax
0x18000f763  mov     rcx, [rbp+80h+var_30]
0x18000f767  xor     rcx, rsp; StackCookie
0x18000f76a  call    __security_check_cookie
0x18000f76f  add     rsp, 168h
0x18000f776  pop     rdi
0x18000f777  pop     rsi
0x18000f778  pop     rbx
0x18000f779  pop     rbp
0x18000f77a  retn
```
