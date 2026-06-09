# DsrHKeyUserHandle::Open(void)

- ea: `0x1800b9d78`
- end: `0x1800b9ee8`
- name: `?Open@DsrHKeyUserHandle@@QEAAJXZ`
- size: `368`
- prototype: `__int64 __fastcall(DsrHKeyUserHandle *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180029e68`

## callees

- `0x1800084f4`
- `0x180008530`
- `0x18000bac0`
- `0x1800b9908`
- `0x1800b9a34`
- `0x1800b9d78`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b9dc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b9e67`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b9dc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b9e67`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800b9e24`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800b9e24`

## string_xrefs

- `0x1800b9e80`: `RegOpenKeyExW`
- `0x1800b9df8`: `ElevatePrivileges`
- `0x1800b9dd8`: `DsrHKeyUserHandle::Open`
- `0x1800b9eb8`: `%s: ElevatePrivileges failed with error: 0x%08x..`

## pseudocode

```c
__int64 __fastcall DsrHKeyUserHandle::Open(DsrHKeyUserHandle *this)
{
  HKEY *phkResult; // rbp
  const WCHAR *v3; // rdi
  const WCHAR *v4; // rdx
  LSTATUS v5; // eax
  signed int v6; // ebx
  const wchar_t *v7; // r8
  const WCHAR *v8; // r8
  const WCHAR *v9; // rdx
  LSTATUS KeyW; // eax
  LSTATUS v11; // eax
  int v12; // eax

  phkResult = (HKEY *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
    DsrHKeyUserHandle::Close(this);
  v3 = (const WCHAR *)((char *)this + 16);
  if ( *((_QWORD *)this + 5) <= 7u )
    v4 = (const WCHAR *)((char *)this + 16);
  else
    v4 = *(const WCHAR **)v3;
  v5 = RegOpenKeyExW(HKEY_USERS, v4, 0, 0x20006u, phkResult);
  v6 = v5;
  if ( v5 > 0 )
    v6 = (unsigned __int16)v5 | 0x80070000;
  if ( v6 == -2147024894 )
  {
    v6 = DsrHKeyUserHandle::ElevatePrivileges(1);
    if ( v6 < 0 )
    {
      v7 = L"ElevatePrivileges";
      goto LABEL_26;
    }
    v8 = (const WCHAR *)((char *)this + 48);
    if ( *((_QWORD *)this + 9) > 7u )
      v8 = *(const WCHAR **)v8;
    if ( *((_QWORD *)this + 5) <= 7u )
      v9 = (const WCHAR *)((char *)this + 16);
    else
      v9 = *(const WCHAR **)v3;
    KeyW = RegLoadKeyW(HKEY_USERS, v9, v8);
    v6 = KeyW;
    if ( KeyW > 0 )
      v6 = (unsigned __int16)KeyW | 0x80070000;
    if ( v6 < 0 )
    {
      v7 = L"RegLoadKeyW";
      goto LABEL_26;
    }
    *(_BYTE *)this = 1;
    if ( *((_QWORD *)this + 5) > 7u )
      v3 = *(const WCHAR **)v3;
    v11 = RegOpenKeyExW(HKEY_USERS, v3, 0, 0x20006u, phkResult);
    v6 = v11;
    if ( v11 > 0 )
      v6 = (unsigned __int16)v11 | 0x80070000;
  }
  if ( v6 >= 0 )
    goto LABEL_28;
  v7 = L"RegOpenKeyExW";
LABEL_26:
  Logger::TraceError(L"%s: %s failed with error code: 0x%08x.", L"DsrHKeyUserHandle::Open", v7, (unsigned int)v6);
  DsrHKeyUserHandle::Close(this);
LABEL_28:
  if ( *(_BYTE *)this == 1 )
  {
    v12 = DsrHKeyUserHandle::ElevatePrivileges(0);
    if ( v12 < 0 )
      Logger::TraceWarning(
        (wchar_t *)L"%s: ElevatePrivileges failed with error: 0x%08x..",
        L"DsrHKeyUserHandle::Open",
        (unsigned int)v12);
  }
  Logger::TraceVerbose((wchar_t *)L"%s - hr: 0x%08x", L"DsrHKeyUserHandle::Open", (unsigned int)v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800b9d78  push    rbx
0x1800b9d7a  push    rbp
0x1800b9d7b  push    rsi
0x1800b9d7c  push    rdi
0x1800b9d7d  push    r12
0x1800b9d7f  push    r14
0x1800b9d81  sub     rsp, 38h
0x1800b9d85  lea     rbp, [rcx+8]
0x1800b9d89  mov     rsi, rcx
0x1800b9d8c  cmp     qword ptr [rbp+0], 0
0x1800b9d91  jz      short loc_1800B9D98
0x1800b9d93  call    ?Close@DsrHKeyUserHandle@@QEAAJXZ; DsrHKeyUserHandle::Close(void)
0x1800b9d98  lea     rdi, [rsi+10h]
0x1800b9d9c  cmp     qword ptr [rdi+18h], 7
0x1800b9da1  jbe     short loc_1800B9DA8
0x1800b9da3  mov     rdx, [rdi]
0x1800b9da6  jmp     short loc_1800B9DAB
0x1800b9da8  mov     rdx, rdi; lpSubKey
0x1800b9dab  mov     r12, 0FFFFFFFF80000003h
0x1800b9db2  mov     [rsp+68h+phkResult], rbp; phkResult
0x1800b9db7  mov     rcx, r12; hKey
0x1800b9dba  mov     r9d, 20006h; samDesired
0x1800b9dc0  xor     r8d, r8d; ulOptions
0x1800b9dc3  call    cs:__imp_RegOpenKeyExW
0x1800b9dc9  mov     ebx, eax
0x1800b9dcb  test    eax, eax
0x1800b9dcd  jle     short loc_1800B9DD8
0x1800b9dcf  movzx   ebx, ax
0x1800b9dd2  or      ebx, 80070000h
0x1800b9dd8  lea     r14, aDsrhkeyuserhan_2; "DsrHKeyUserHandle::Open"
0x1800b9ddf  cmp     ebx, 80070002h
0x1800b9de5  jnz     loc_1800B9E7C
0x1800b9deb  mov     cl, 1; bool
0x1800b9ded  call    ?ElevatePrivileges@DsrHKeyUserHandle@@CAJ_N@Z; DsrHKeyUserHandle::ElevatePrivileges(bool)
0x1800b9df2  mov     ebx, eax
0x1800b9df4  test    eax, eax
0x1800b9df6  jns     short loc_1800B9E04
0x1800b9df8  lea     r8, aElevateprivile; "ElevatePrivileges"
0x1800b9dff  jmp     loc_1800B9E87
0x1800b9e04  lea     r8, [rsi+30h]
0x1800b9e08  cmp     qword ptr [r8+18h], 7
0x1800b9e0d  jbe     short loc_1800B9E12
0x1800b9e0f  mov     r8, [r8]; lpFile
0x1800b9e12  cmp     qword ptr [rdi+18h], 7
0x1800b9e17  jbe     short loc_1800B9E1E
0x1800b9e19  mov     rdx, [rdi]
0x1800b9e1c  jmp     short loc_1800B9E21
0x1800b9e1e  mov     rdx, rdi; lpSubKey
0x1800b9e21  mov     rcx, r12; hKey
0x1800b9e24  call    cs:__imp_RegLoadKeyW
0x1800b9e2a  mov     ebx, eax
0x1800b9e2c  test    eax, eax
0x1800b9e2e  jle     short loc_1800B9E39
0x1800b9e30  movzx   ebx, ax
0x1800b9e33  or      ebx, 80070000h
0x1800b9e39  test    ebx, ebx
0x1800b9e3b  jns     short loc_1800B9E46
0x1800b9e3d  lea     r8, aRegloadkeyw; "RegLoadKeyW"
0x1800b9e44  jmp     short loc_1800B9E87
0x1800b9e46  mov     byte ptr [rsi], 1
0x1800b9e49  cmp     qword ptr [rdi+18h], 7
0x1800b9e4e  jbe     short loc_1800B9E53
0x1800b9e50  mov     rdi, [rdi]
0x1800b9e53  mov     r9d, 20006h; samDesired
0x1800b9e59  mov     [rsp+68h+phkResult], rbp; phkResult
0x1800b9e5e  xor     r8d, r8d; ulOptions
0x1800b9e61  mov     rdx, rdi; lpSubKey
0x1800b9e64  mov     rcx, r12; hKey
0x1800b9e67  call    cs:__imp_RegOpenKeyExW
0x1800b9e6d  mov     ebx, eax
0x1800b9e6f  test    eax, eax
0x1800b9e71  jle     short loc_1800B9E7C
0x1800b9e73  movzx   ebx, ax
0x1800b9e76  or      ebx, 80070000h
0x1800b9e7c  test    ebx, ebx
0x1800b9e7e  jns     short loc_1800B9EA5
0x1800b9e80  lea     r8, aRegopenkeyexw; "RegOpenKeyExW"
0x1800b9e87  mov     rdx, r14
0x1800b9e8a  lea     rcx, aSSFailedWithEr_2; "%s: %s failed with error code: 0x%08x."
0x1800b9e91  mov     r9d, ebx
0x1800b9e94  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800b9e99  test    ebx, ebx
0x1800b9e9b  jns     short loc_1800B9EA5
0x1800b9e9d  mov     rcx, rsi; this
0x1800b9ea0  call    ?Close@DsrHKeyUserHandle@@QEAAJXZ; DsrHKeyUserHandle::Close(void)
0x1800b9ea5  cmp     byte ptr [rsi], 1
0x1800b9ea8  jnz     short loc_1800B9EC7
0x1800b9eaa  xor     ecx, ecx; bool
0x1800b9eac  call    ?ElevatePrivileges@DsrHKeyUserHandle@@CAJ_N@Z; DsrHKeyUserHandle::ElevatePrivileges(bool)
0x1800b9eb1  test    eax, eax
0x1800b9eb3  jns     short loc_1800B9EC7
0x1800b9eb5  mov     r8d, eax
0x1800b9eb8  lea     rcx, aSElevateprivil; "%s: ElevatePrivileges failed with error"...
0x1800b9ebf  mov     rdx, r14
0x1800b9ec2  call    ?TraceWarning@Logger@@SAJPEBGZZ; Logger::TraceWarning(ushort const *,...)
0x1800b9ec7  mov     r8d, ebx
0x1800b9eca  lea     rcx, aSHr0x08x; "%s - hr: 0x%08x"
0x1800b9ed1  mov     rdx, r14
0x1800b9ed4  call    ?TraceVerbose@Logger@@SAJPEBGZZ; Logger::TraceVerbose(ushort const *,...)
0x1800b9ed9  mov     eax, ebx
0x1800b9edb  add     rsp, 38h
0x1800b9edf  pop     r14
0x1800b9ee1  pop     r12
0x1800b9ee3  pop     rdi
0x1800b9ee4  pop     rsi
0x1800b9ee5  pop     rbp
0x1800b9ee6  pop     rbx
0x1800b9ee7  retn
```
