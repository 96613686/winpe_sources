# GetRegisteredLocation

- ea: `0x180039a10`
- end: `0x180039b2f`
- name: `GetRegisteredLocation`
- size: `287`
- prototype: `__int64 __fastcall(LPSTR lpDst)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180039b38`

## callees

- `0x180039a10`
- `0x18004d110`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180039ac0`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsA` at `0x180039ac0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180039aa0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180039aa0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180039a5c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180039a5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039b0b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180039b0b`

## string_xrefs

- `0x180039a55`: `CLSID\{ADB880A6-D8FF-11CF-9377-00AA003B7A11}\InprocServer32`

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
0x180039a10  push    rbp
0x180039a12  push    rbx
0x180039a13  push    rsi
0x180039a14  push    rdi
0x180039a15  lea     rbp, [rsp-68h]
0x180039a1a  sub     rsp, 168h
0x180039a21  mov     rax, cs:__security_cookie
0x180039a28  xor     rax, rsp
0x180039a2b  mov     [rbp+80h+var_30], rax
0x180039a2f  mov     rdi, rcx
0x180039a32  mov     [rsp+180h+hKey], 0
0x180039a3b  lea     rax, [rsp+180h+hKey]
0x180039a40  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180039a47  mov     r9d, 20019h; samDesired
0x180039a4d  mov     [rsp+180h+phkResult], rax; phkResult
0x180039a52  xor     r8d, r8d; ulOptions
0x180039a55  lea     rdx, SubKey; "CLSID\\{ADB880A6-D8FF-11CF-9377-00AA003"...
0x180039a5c  call    cs:__imp_RegOpenKeyExA
0x180039a62  test    eax, eax
0x180039a64  jnz     loc_180039B15
0x180039a6a  mov     rcx, [rsp+180h+hKey]; hKey
0x180039a6f  lea     rax, [rsp+180h+cbData]
0x180039a74  mov     [rsp+180h+lpcbData], rax; lpcbData
0x180039a79  lea     r9, [rsp+180h+Type]; lpType
0x180039a7e  lea     rax, [rsp+180h+Data]
0x180039a83  mov     [rsp+180h+Type], 1
0x180039a8b  mov     ebx, 104h
0x180039a90  mov     [rsp+180h+phkResult], rax; lpData
0x180039a95  xor     r8d, r8d; lpReserved
0x180039a98  mov     [rsp+180h+cbData], ebx
0x180039a9c  xor     edx, edx; lpValueName
0x180039a9e  xor     esi, esi
0x180039aa0  call    cs:__imp_RegQueryValueExA
0x180039aa6  test    eax, eax
0x180039aa8  jnz     short loc_180039B06
0x180039aaa  cmp     [rsp+180h+Type], 2
0x180039aaf  lea     rcx, [rsp+180h+Data]; lpSrc
0x180039ab4  mov     [rbp+80h+var_3D], sil
0x180039ab8  jnz     short loc_180039AD3
0x180039aba  mov     r8d, ebx; nSize
0x180039abd  mov     rdx, rdi; lpDst
0x180039ac0  call    cs:__imp_ExpandEnvironmentStringsA
0x180039ac6  dec     eax
0x180039ac8  cmp     eax, 103h
0x180039acd  setbe   sil
0x180039ad1  jmp     short loc_180039B06
0x180039ad3  mov     eax, 7FFFFFFEh
0x180039ad8  test    rax, rax
0x180039adb  jz      short loc_180039AF4
0x180039add  mov     dl, [rcx]
0x180039adf  test    dl, dl
0x180039ae1  jz      short loc_180039AF4
0x180039ae3  mov     [rdi], dl
0x180039ae5  inc     rcx
0x180039ae8  inc     rdi
0x180039aeb  dec     rax
0x180039aee  sub     rbx, 1
0x180039af2  jnz     short loc_180039AD8
0x180039af4  test    rbx, rbx
0x180039af7  lea     rax, [rdi-1]
0x180039afb  cmovnz  rax, rdi
0x180039aff  mov     [rax], sil
0x180039b02  setnz   sil
0x180039b06  mov     rcx, [rsp+180h+hKey]; hKey
0x180039b0b  call    cs:__imp_RegCloseKey
0x180039b11  mov     eax, esi
0x180039b13  jmp     short loc_180039B17
0x180039b15  xor     eax, eax
0x180039b17  mov     rcx, [rbp+80h+var_30]
0x180039b1b  xor     rcx, rsp; StackCookie
0x180039b1e  call    __security_check_cookie
0x180039b23  add     rsp, 168h
0x180039b2a  pop     rdi
0x180039b2b  pop     rsi
0x180039b2c  pop     rbx
0x180039b2d  pop     rbp
0x180039b2e  retn
```
