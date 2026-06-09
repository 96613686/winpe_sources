# GetRegisteredLocation

- ea: `0x1800115ac`
- end: `0x1800116cb`
- name: `GetRegisteredLocation`
- size: `287`
- prototype: `__int64 __fastcall(LPSTR lpDst)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800116d4`

## callees

- `0x1800115ac`
- `0x180014ae0`

## import_xrefs

- `KERNEL32!ExpandEnvironmentStringsA` at `0x18001165c`
- `KERNEL32!ExpandEnvironmentStringsA` at `0x18001165c`
- `ADVAPI32!RegQueryValueExA` at `0x18001163c`
- `ADVAPI32!RegQueryValueExA` at `0x18001163c`
- `ADVAPI32!RegCloseKey` at `0x1800116a7`
- `ADVAPI32!RegCloseKey` at `0x1800116a7`
- `ADVAPI32!RegOpenKeyExA` at `0x1800115f8`
- `ADVAPI32!RegOpenKeyExA` at `0x1800115f8`

## string_xrefs

- `0x1800115f1`: `CLSID\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\InprocServer32`

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
0x1800115ac  push    rbp
0x1800115ae  push    rbx
0x1800115af  push    rsi
0x1800115b0  push    rdi
0x1800115b1  lea     rbp, [rsp-68h]
0x1800115b6  sub     rsp, 168h
0x1800115bd  mov     rax, cs:__security_cookie
0x1800115c4  xor     rax, rsp
0x1800115c7  mov     [rbp+80h+var_30], rax
0x1800115cb  mov     rdi, rcx
0x1800115ce  mov     [rsp+180h+hKey], 0
0x1800115d7  lea     rax, [rsp+180h+hKey]
0x1800115dc  mov     rcx, 0FFFFFFFF80000000h; hKey
0x1800115e3  mov     r9d, 20019h; samDesired
0x1800115e9  mov     [rsp+180h+phkResult], rax; phkResult
0x1800115ee  xor     r8d, r8d; ulOptions
0x1800115f1  lea     rdx, aClsidAdb880a6D; "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003"...
0x1800115f8  call    cs:__imp_RegOpenKeyExA
0x1800115fe  test    eax, eax
0x180011600  jnz     loc_1800116B1
0x180011606  mov     rcx, [rsp+180h+hKey]; hKey
0x18001160b  lea     rax, [rsp+180h+cbData]
0x180011610  mov     [rsp+180h+lpcbData], rax; lpcbData
0x180011615  lea     r9, [rsp+180h+Type]; lpType
0x18001161a  lea     rax, [rsp+180h+Data]
0x18001161f  mov     [rsp+180h+Type], 1
0x180011627  mov     ebx, 104h
0x18001162c  mov     [rsp+180h+phkResult], rax; lpData
0x180011631  xor     r8d, r8d; lpReserved
0x180011634  mov     [rsp+180h+cbData], ebx
0x180011638  xor     edx, edx; lpValueName
0x18001163a  xor     esi, esi
0x18001163c  call    cs:__imp_RegQueryValueExA
0x180011642  test    eax, eax
0x180011644  jnz     short loc_1800116A2
0x180011646  cmp     [rsp+180h+Type], 2
0x18001164b  lea     rcx, [rsp+180h+Data]; lpSrc
0x180011650  mov     [rbp+80h+var_3D], sil
0x180011654  jnz     short loc_18001166F
0x180011656  mov     r8d, ebx; nSize
0x180011659  mov     rdx, rdi; lpDst
0x18001165c  call    cs:__imp_ExpandEnvironmentStringsA
0x180011662  dec     eax
0x180011664  cmp     eax, 103h
0x180011669  setbe   sil
0x18001166d  jmp     short loc_1800116A2
0x18001166f  mov     eax, 7FFFFFFEh
0x180011674  test    rax, rax
0x180011677  jz      short loc_180011690
0x180011679  mov     dl, [rcx]
0x18001167b  test    dl, dl
0x18001167d  jz      short loc_180011690
0x18001167f  mov     [rdi], dl
0x180011681  inc     rcx
0x180011684  inc     rdi
0x180011687  dec     rax
0x18001168a  sub     rbx, 1
0x18001168e  jnz     short loc_180011674
0x180011690  test    rbx, rbx
0x180011693  lea     rax, [rdi-1]
0x180011697  cmovnz  rax, rdi
0x18001169b  mov     [rax], sil
0x18001169e  setnz   sil
0x1800116a2  mov     rcx, [rsp+180h+hKey]; hKey
0x1800116a7  call    cs:__imp_RegCloseKey
0x1800116ad  mov     eax, esi
0x1800116af  jmp     short loc_1800116B3
0x1800116b1  xor     eax, eax
0x1800116b3  mov     rcx, [rbp+80h+var_30]
0x1800116b7  xor     rcx, rsp; StackCookie
0x1800116ba  call    __security_check_cookie
0x1800116bf  add     rsp, 168h
0x1800116c6  pop     rdi
0x1800116c7  pop     rsi
0x1800116c8  pop     rbx
0x1800116c9  pop     rbp
0x1800116ca  retn
```
