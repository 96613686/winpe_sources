# RegisterACLSID(SClassEntry const &,wchar_t const *,wchar_t const *,int,int)

- ea: `0x18001fafc`
- end: `0x18001fd4b`
- name: `?RegisterACLSID@@YAJAEBUSClassEntry@@PEB_W1HH@Z`
- size: `591`
- prototype: `int(const struct SClassEntry *, const wchar_t *, const wchar_t *, int, int)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001fd54`
- `0x18002107c`

## callees

- `0x1800112e0`
- `0x180011324`
- `0x180014130`
- `0x18001fafc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fc51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fd05`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fc51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fd05`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd17`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fc6b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001fd17`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fc04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fcd7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fc04`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fcd7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fbb6`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fbb6`

## string_xrefs

- `0x18001fb3b`: `CLSID\`

## pseudocode

```c
__int64 __fastcall RegisterACLSID(const struct SClassEntry *a1, const wchar_t *a2, const wchar_t *a3, int a4)
{
  __int64 v7; // rax
  const wchar_t *v8; // r8
  LSTATUS v9; // eax
  unsigned int v10; // ebx
  const BYTE *v11; // rcx
  __int64 v12; // rax
  __int64 v13; // rax
  DWORD dwDisposition; // [rsp+50h] [rbp-B0h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t SubKey[264]; // [rsp+60h] [rbp-A0h] BYREF

  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  StringCchCopyW(SubKey, 0x104u, L"CLSID\\");
  v7 = -1;
  do
    ++v7;
  while ( SubKey[v7] );
  if ( a3 )
    v8 = a3;
  else
    v8 = (const wchar_t *)*((_QWORD *)a1 + 3);
  StringCchCatW(SubKey, 260 - v7, v8);
  dwDisposition = 0;
  if ( a4 )
  {
    v9 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &hKey);
    if ( v9 )
    {
      v10 = 0;
      if ( v9 != 2 )
        v10 = v9;
      goto LABEL_24;
    }
    dwDisposition = 2;
  }
  else
  {
    v10 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
    if ( v10 )
      goto LABEL_24;
    if ( dwDisposition == 1 && !a3 )
    {
      v11 = (const BYTE *)*((_QWORD *)a1 + 4);
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)&v11[2 * v12] );
      v10 = RegSetValueExW(hKey, 0, 0, 1u, v11, 2 * v12 + 2);
      if ( v10 )
        goto LABEL_24;
    }
  }
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    RegCloseKey(hKey);
    hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  }
  v13 = -1;
  do
    ++v13;
  while ( SubKey[v13] );
  StringCchCatW(SubKey, 260 - v13, L"\\PersistentHandler");
  v10 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
  if ( !v10 )
    v10 = RegSetValueExW(hKey, 0, 0, 1u, L"{eec97550-47a9-11cf-b952-00aa0051fe20}", 0x4Eu);
LABEL_24:
  if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    RegCloseKey(hKey);
  return v10;
}

```

## disassembly

```asm
0x18001fafc  mov     [rsp-8+arg_8], rbx
0x18001fb01  mov     [rsp-8+arg_18], rdi
0x18001fb06  push    rbp
0x18001fb07  push    r12
0x18001fb09  push    r13
0x18001fb0b  push    r14
0x18001fb0d  push    r15
0x18001fb0f  lea     rbp, [rsp-180h]
0x18001fb17  sub     rsp, 280h
0x18001fb1e  mov     rax, cs:__security_cookie
0x18001fb25  xor     rax, rsp
0x18001fb28  mov     [rbp+1A0h+var_30], rax
0x18001fb2f  mov     rdi, r8
0x18001fb32  mov     r14, rcx
0x18001fb35  mov     r15d, 104h
0x18001fb3b  lea     r8, aClsid; "CLSID\\"
0x18001fb42  or      r13, 0FFFFFFFFFFFFFFFFh
0x18001fb46  lea     rcx, [rsp+2A0h+SubKey]; wchar_t *
0x18001fb4b  mov     edx, r15d; unsigned __int64
0x18001fb4e  mov     [rsp+2A0h+hKey], r13
0x18001fb53  mov     ebx, r9d
0x18001fb56  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001fb5b  mov     rax, r13
0x18001fb5e  lea     r11, [rsp+2A0h+SubKey]
0x18001fb63  xor     r12d, r12d
0x18001fb66  inc     rax
0x18001fb69  cmp     [r11+rax*2], r12w
0x18001fb6e  jnz     short loc_18001FB66
0x18001fb70  mov     rdx, r15
0x18001fb73  sub     rdx, rax; unsigned __int64
0x18001fb76  test    rdi, rdi
0x18001fb79  jnz     short loc_18001FB81
0x18001fb7b  mov     r8, [r14+18h]
0x18001fb7f  jmp     short loc_18001FB84
0x18001fb81  mov     r8, rdi; wchar_t *
0x18001fb84  lea     rcx, [rsp+2A0h+SubKey]; wchar_t *
0x18001fb89  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001fb8e  xor     r8d, r8d; Reserved
0x18001fb91  mov     [rsp+2A0h+dwDisposition], r12d
0x18001fb96  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18001fb9b  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001fba2  test    ebx, ebx
0x18001fba4  jz      short loc_18001FBDB
0x18001fba6  lea     rax, [rsp+2A0h+hKey]
0x18001fbab  mov     r9d, 2001Fh; samDesired
0x18001fbb1  mov     [rsp+2A0h+phkResult], rax; phkResult
0x18001fbb6  call    cs:__imp_RegOpenKeyExW
0x18001fbbc  test    eax, eax
0x18001fbbe  jz      short loc_18001FBCE
0x18001fbc0  cmp     eax, 2
0x18001fbc3  mov     ebx, r12d
0x18001fbc6  cmovnz  ebx, eax
0x18001fbc9  jmp     loc_18001FD0D
0x18001fbce  mov     [rsp+2A0h+dwDisposition], 2
0x18001fbd6  jmp     loc_18001FC61
0x18001fbdb  lea     rax, [rsp+2A0h+dwDisposition]
0x18001fbe0  xor     r9d, r9d; lpClass
0x18001fbe3  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x18001fbe8  lea     rax, [rsp+2A0h+hKey]
0x18001fbed  mov     [rsp+2A0h+var_268], rax; phkResult
0x18001fbf2  mov     [rsp+2A0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18001fbf7  mov     [rsp+2A0h+samDesired], 2001Fh; samDesired
0x18001fbff  mov     dword ptr [rsp+2A0h+phkResult], r12d; dwOptions
0x18001fc04  call    cs:__imp_RegCreateKeyExW
0x18001fc0a  mov     ebx, eax
0x18001fc0c  test    eax, eax
0x18001fc0e  jnz     loc_18001FD0D
0x18001fc14  cmp     [rsp+2A0h+dwDisposition], 1
0x18001fc19  jnz     short loc_18001FC61
0x18001fc1b  test    rdi, rdi
0x18001fc1e  jnz     short loc_18001FC61
0x18001fc20  mov     rcx, [r14+20h]
0x18001fc24  mov     rax, r13
0x18001fc27  inc     rax
0x18001fc2a  cmp     [rcx+rax*2], r12w
0x18001fc2f  jnz     short loc_18001FC27
0x18001fc31  lea     eax, ds:2[rax*2]
0x18001fc38  mov     r9d, 1; dwType
0x18001fc3e  mov     [rsp+2A0h+samDesired], eax; cbData
0x18001fc42  xor     r8d, r8d; Reserved
0x18001fc45  mov     [rsp+2A0h+phkResult], rcx; lpData
0x18001fc4a  xor     edx, edx; lpValueName
0x18001fc4c  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001fc51  call    cs:__imp_RegSetValueExW
0x18001fc57  mov     ebx, eax
0x18001fc59  test    eax, eax
0x18001fc5b  jnz     loc_18001FD0D
0x18001fc61  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001fc66  cmp     rcx, r13
0x18001fc69  jz      short loc_18001FC76
0x18001fc6b  call    cs:__imp_RegCloseKey
0x18001fc71  mov     [rsp+2A0h+hKey], r13
0x18001fc76  lea     rcx, [rsp+2A0h+SubKey]
0x18001fc7b  mov     rax, r13
0x18001fc7e  inc     rax
0x18001fc81  cmp     [rcx+rax*2], r12w
0x18001fc86  jnz     short loc_18001FC7E
0x18001fc88  sub     r15, rax
0x18001fc8b  lea     r8, aPersistenthand; "\\PersistentHandler"
0x18001fc92  mov     rdx, r15; unsigned __int64
0x18001fc95  lea     rcx, [rsp+2A0h+SubKey]; wchar_t *
0x18001fc9a  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001fc9f  lea     rax, [rsp+2A0h+dwDisposition]
0x18001fca4  xor     r9d, r9d; lpClass
0x18001fca7  mov     [rsp+2A0h+lpdwDisposition], rax; lpdwDisposition
0x18001fcac  lea     rdx, [rsp+2A0h+SubKey]; lpSubKey
0x18001fcb1  lea     rax, [rsp+2A0h+hKey]
0x18001fcb6  xor     r8d, r8d; Reserved
0x18001fcb9  mov     [rsp+2A0h+var_268], rax; phkResult
0x18001fcbe  mov     rcx, 0FFFFFFFF80000000h; hKey
0x18001fcc5  mov     [rsp+2A0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18001fcca  mov     [rsp+2A0h+samDesired], 2001Fh; samDesired
0x18001fcd2  mov     dword ptr [rsp+2A0h+phkResult], r12d; dwOptions
0x18001fcd7  call    cs:__imp_RegCreateKeyExW
0x18001fcdd  mov     ebx, eax
0x18001fcdf  test    eax, eax
0x18001fce1  jnz     short loc_18001FD0D
0x18001fce3  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001fce8  lea     rax, Data; "{eec97550-47a9-11cf-b952-00aa0051fe20}"
0x18001fcef  mov     [rsp+2A0h+samDesired], 4Eh ; 'N'; cbData
0x18001fcf7  lea     r9d, [rbx+1]; dwType
0x18001fcfb  xor     r8d, r8d; Reserved
0x18001fcfe  mov     [rsp+2A0h+phkResult], rax; lpData
0x18001fd03  xor     edx, edx; lpValueName
0x18001fd05  call    cs:__imp_RegSetValueExW
0x18001fd0b  mov     ebx, eax
0x18001fd0d  mov     rcx, [rsp+2A0h+hKey]; hKey
0x18001fd12  cmp     rcx, r13
0x18001fd15  jz      short loc_18001FD1D
0x18001fd17  call    cs:__imp_RegCloseKey
0x18001fd1d  mov     eax, ebx
0x18001fd1f  mov     rcx, [rbp+1A0h+var_30]
0x18001fd26  xor     rcx, rsp; StackCookie
0x18001fd29  call    __security_check_cookie
0x18001fd2e  lea     r11, [rsp+2A0h+var_20]
0x18001fd36  mov     rbx, [r11+38h]
0x18001fd3a  mov     rdi, [r11+48h]
0x18001fd3e  mov     rsp, r11
0x18001fd41  pop     r15
0x18001fd43  pop     r14
0x18001fd45  pop     r13
0x18001fd47  pop     r12
0x18001fd49  pop     rbp
0x18001fd4a  retn
```
