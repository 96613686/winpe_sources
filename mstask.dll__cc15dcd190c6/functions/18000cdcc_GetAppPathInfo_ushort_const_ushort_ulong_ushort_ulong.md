# GetAppPathInfo(ushort const *,ushort *,ulong,ushort *,ulong)

- ea: `0x18000cdcc`
- end: `0x18000cf2a`
- name: `?GetAppPathInfo@@YAXPEBGPEAGK1K@Z`
- size: `350`
- prototype: `void __fastcall(const unsigned __int16 *, LPBYTE lpData, unsigned int, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180001840`
- `0x180006f90`
- `0x18000cdcc`
- `0x18001aa9a`
- `0x18001aac0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cf07`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000cf07`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cec1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cef7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cec1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000cef7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ce88`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000ce88`

## string_xrefs

- `0x18000ce31`: `Software\Microsoft\Windows\CurrentVersion\App Paths`

## pseudocode

```c
void __fastcall GetAppPathInfo(const unsigned __int16 *a1, LPBYTE lpData, __int64 a3, BYTE *a4)
{
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  WCHAR SubKey[312]; // [rsp+40h] [rbp-C0h] BYREF

  hKey = 0;
  memset_0(SubKey, 0, sizeof(SubKey));
  if ( lpData )
    *(_WORD *)lpData = 0;
  if ( a4 )
    *(_WORD *)a4 = 0;
  StringCchCopyW(SubKey, 0x138u, L"Software\\Microsoft\\Windows\\CurrentVersion\\App Paths");
  StringCchCatW(SubKey, 0x138u, L"\\");
  StringCchCatW(SubKey, 0x138u, a1);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &hKey) )
  {
    Type = 0;
    if ( lpData )
    {
      cbData = 522;
      RegQueryValueExW(hKey, 0, 0, &Type, lpData, &cbData);
    }
    if ( a4 )
    {
      cbData = 2048;
      RegQueryValueExW(hKey, L"Path", 0, &Type, a4, &cbData);
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
}

```

## disassembly

```asm
0x18000cdcc  push    rbp
0x18000cdce  push    rbx
0x18000cdcf  push    rsi
0x18000cdd0  push    rdi
0x18000cdd1  push    r14
0x18000cdd3  lea     rbp, [rsp-1C0h]
0x18000cddb  sub     rsp, 2C0h
0x18000cde2  mov     rax, cs:__security_cookie
0x18000cde9  xor     rax, rsp
0x18000cdec  mov     [rbp+1E0h+var_30], rax
0x18000cdf3  mov     rdi, rdx
0x18000cdf6  mov     [rsp+2E0h+hKey], 0
0x18000cdff  mov     rsi, rcx
0x18000ce02  xor     edx, edx; Val
0x18000ce04  lea     rcx, [rsp+2E0h+SubKey]; void *
0x18000ce09  mov     r8d, 270h; Size
0x18000ce0f  mov     rbx, r9
0x18000ce12  call    memset_0
0x18000ce17  test    rdi, rdi
0x18000ce1a  jz      short loc_18000CE21
0x18000ce1c  xor     eax, eax
0x18000ce1e  mov     [rdi], ax
0x18000ce21  test    rbx, rbx
0x18000ce24  jz      short loc_18000CE2B
0x18000ce26  xor     eax, eax
0x18000ce28  mov     [rbx], ax
0x18000ce2b  mov     r14d, 138h
0x18000ce31  lea     r8, aSoftwareMicros_0; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18000ce38  mov     edx, r14d; unsigned __int64
0x18000ce3b  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18000ce40  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000ce45  lea     r8, asc_18001D98C; "\\"
0x18000ce4c  mov     edx, r14d; unsigned __int64
0x18000ce4f  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18000ce54  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ce59  mov     r8, rsi; unsigned __int16 *
0x18000ce5c  lea     rcx, [rsp+2E0h+SubKey]; unsigned __int16 *
0x18000ce61  mov     edx, r14d; unsigned __int64
0x18000ce64  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18000ce69  lea     rax, [rsp+2E0h+hKey]
0x18000ce6e  mov     r9d, 1; samDesired
0x18000ce74  xor     r8d, r8d; ulOptions
0x18000ce77  mov     [rsp+2E0h+phkResult], rax; phkResult
0x18000ce7c  lea     rdx, [rsp+2E0h+SubKey]; lpSubKey
0x18000ce81  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000ce88  call    cs:__imp_RegOpenKeyExW
0x18000ce8e  test    eax, eax
0x18000ce90  jnz     short loc_18000CEFD
0x18000ce92  mov     [rsp+2E0h+Type], eax
0x18000ce96  test    rdi, rdi
0x18000ce99  jz      short loc_18000CEC7
0x18000ce9b  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000cea0  lea     rax, [rsp+2E0h+cbData]
0x18000cea5  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18000ceaa  lea     r9, [rsp+2E0h+Type]; lpType
0x18000ceaf  xor     r8d, r8d; lpReserved
0x18000ceb2  mov     [rsp+2E0h+phkResult], rdi; lpData
0x18000ceb7  xor     edx, edx; lpValueName
0x18000ceb9  mov     [rsp+2E0h+cbData], 20Ah
0x18000cec1  call    cs:__imp_RegQueryValueExW
0x18000cec7  test    rbx, rbx
0x18000ceca  jz      short loc_18000CEFD
0x18000cecc  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000ced1  lea     rax, [rsp+2E0h+cbData]
0x18000ced6  mov     [rsp+2E0h+lpcbData], rax; lpcbData
0x18000cedb  lea     r9, [rsp+2E0h+Type]; lpType
0x18000cee0  xor     r8d, r8d; lpReserved
0x18000cee3  mov     [rsp+2E0h+phkResult], rbx; lpData
0x18000cee8  lea     rdx, Name; "Path"
0x18000ceef  mov     [rsp+2E0h+cbData], 800h
0x18000cef7  call    cs:__imp_RegQueryValueExW
0x18000cefd  mov     rcx, [rsp+2E0h+hKey]; hKey
0x18000cf02  test    rcx, rcx
0x18000cf05  jz      short loc_18000CF0D
0x18000cf07  call    cs:__imp_RegCloseKey
0x18000cf0d  mov     rcx, [rbp+1E0h+var_30]
0x18000cf14  xor     rcx, rsp; StackCookie
0x18000cf17  call    __security_check_cookie
0x18000cf1c  add     rsp, 2C0h
0x18000cf23  pop     r14
0x18000cf25  pop     rdi
0x18000cf26  pop     rsi
0x18000cf27  pop     rbx
0x18000cf28  pop     rbp
0x18000cf29  retn
```
