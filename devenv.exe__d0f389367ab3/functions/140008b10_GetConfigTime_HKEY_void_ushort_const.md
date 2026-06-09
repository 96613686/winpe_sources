# GetConfigTime(HKEY__ *,void *,ushort const *)

- ea: `0x140008b10`
- end: `0x140008bf3`
- name: `?GetConfigTime@@YA?AU_FILETIME@@PEAUHKEY__@@PEAXPEBG@Z`
- size: `227`
- prototype: `struct _FILETIME __fastcall(HKEY hKey, HANDLE hToken, LPCWSTR lpSubKey)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, registry_config`

## callers

- `0x140008970`
- `0x14004bd64`

## callees

- `0x140001020`
- `0x140008b10`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x140008bc3`
- `ADVAPI32!RegCloseKey` at `0x140008bc3`
- `ADVAPI32!RegOpenKeyExW` at `0x140008b5a`
- `ADVAPI32!RegOpenKeyExW` at `0x140008b5a`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140008baa`
- `ADVAPI32!RegQueryInfoKeyW` at `0x140008baa`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140008b39`
- `ADVAPI32!ImpersonateLoggedOnUser` at `0x140008b39`
- `ADVAPI32!RevertToSelf` at `0x140008bd2`
- `ADVAPI32!RevertToSelf` at `0x140008bd2`

## pseudocode

```c
struct _FILETIME __fastcall GetConfigTime(HKEY hKey, HANDLE hToken, LPCWSTR lpSubKey)
{
  BOOL v5; // esi
  struct _FILETIME v6; // rbx
  HKEY hKeya; // [rsp+60h] [rbp-38h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+68h] [rbp-30h] BYREF

  ftLastWriteTime = 0;
  v5 = ImpersonateLoggedOnUser(hToken);
  if ( !RegOpenKeyExW(hKey, lpSubKey, 0, 0x20019u, &hKeya) && hKeya )
  {
    if ( RegQueryInfoKeyW(hKeya, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, &ftLastWriteTime) )
    {
      ftLastWriteTime.dwLowDateTime = 0;
      ftLastWriteTime.dwHighDateTime = 0;
    }
    RegCloseKey(hKeya);
  }
  v6 = ftLastWriteTime;
  if ( v5 )
    RevertToSelf();
  return v6;
}

```

## disassembly

```asm
0x140008b10  push    rbx
0x140008b12  push    rsi
0x140008b13  push    rdi
0x140008b14  sub     rsp, 80h
0x140008b1b  mov     rax, cs:__security_cookie
0x140008b22  xor     rax, rsp
0x140008b25  mov     [rsp+98h+var_28], rax
0x140008b2a  and     qword ptr [rsp+98h+ftLastWriteTime.dwLowDateTime], 0
0x140008b30  mov     rbx, rcx
0x140008b33  mov     rcx, rdx; hToken
0x140008b36  mov     rdi, r8
0x140008b39  call    cs:__imp_ImpersonateLoggedOnUser
0x140008b3f  mov     r9d, 20019h; samDesired
0x140008b45  xor     r8d, r8d; ulOptions
0x140008b48  mov     esi, eax
0x140008b4a  mov     rdx, rdi; lpSubKey
0x140008b4d  lea     rax, [rsp+98h+hKey]
0x140008b52  mov     rcx, rbx; hKey
0x140008b55  mov     [rsp+98h+phkResult], rax; lpcSubKeys
0x140008b5a  call    cs:__imp_RegOpenKeyExW
0x140008b60  test    eax, eax
0x140008b62  jnz     short loc_140008BC9
0x140008b64  mov     rcx, [rsp+98h+hKey]; hKey
0x140008b69  test    rcx, rcx
0x140008b6c  jz      short loc_140008BC9
0x140008b6e  lea     rax, [rsp+98h+ftLastWriteTime]
0x140008b73  xor     r9d, r9d; lpReserved
0x140008b76  mov     [rsp+98h+lpftLastWriteTime], rax; lpftLastWriteTime
0x140008b7b  xor     r8d, r8d; lpcchClass
0x140008b7e  and     [rsp+98h+var_48], 0
0x140008b84  xor     edx, edx; lpClass
0x140008b86  and     [rsp+98h+var_50], 0
0x140008b8c  and     [rsp+98h+var_58], 0
0x140008b92  and     [rsp+98h+var_60], 0
0x140008b98  and     [rsp+98h+var_68], 0
0x140008b9e  and     [rsp+98h+var_70], 0
0x140008ba4  and     [rsp+98h+phkResult], 0
0x140008baa  call    cs:__imp_RegQueryInfoKeyW
0x140008bb0  test    eax, eax
0x140008bb2  jz      short loc_140008BBE
0x140008bb4  and     [rsp+98h+ftLastWriteTime.dwLowDateTime], 0
0x140008bb9  and     [rsp+98h+ftLastWriteTime.dwHighDateTime], 0
0x140008bbe  mov     rcx, [rsp+98h+hKey]; hKey
0x140008bc3  call    cs:__imp_RegCloseKey
0x140008bc9  mov     rbx, qword ptr [rsp+98h+ftLastWriteTime.dwLowDateTime]
0x140008bce  test    esi, esi
0x140008bd0  jz      short loc_140008BD8
0x140008bd2  call    cs:__imp_RevertToSelf
0x140008bd8  mov     rax, rbx
0x140008bdb  mov     rcx, [rsp+98h+var_28]
0x140008be0  xor     rcx, rsp; StackCookie
0x140008be3  call    __security_check_cookie
0x140008be8  add     rsp, 80h
0x140008bef  pop     rdi
0x140008bf0  pop     rsi
0x140008bf1  pop     rbx
0x140008bf2  retn
```
