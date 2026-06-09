# Intl_GetUserUILanguage(HKEY__ *,ushort *,int)

- ea: `0x1800258c8`
- end: `0x180025a14`
- name: `?Intl_GetUserUILanguage@@YAHPEAUHKEY__@@PEAGH@Z`
- size: `332`
- prototype: `__int64 __fastcall(HKEY hKey, unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000849c`
- `0x180026304`
- `0x180026994`

## callees

- `0x18000626c`
- `0x1800258c8`
- `0x18002a112`
- `0x18002a150`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025947`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180025947`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025985`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800259bf`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180025985`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800259bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259ef`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800259ef`

## pseudocode

```c
__int64 __fastcall Intl_GetUserUILanguage(HKEY hKey, unsigned __int16 *a2, int a3)
{
  unsigned __int64 v3; // r14
  unsigned int v6; // edi
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKeya; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 Data[352]; // [rsp+40h] [rbp-C0h] BYREF

  v3 = a3;
  hKeya = 0;
  Type = 0;
  cbData = 0;
  memset_0(Data, 0, 0x2BCu);
  *a2 = 0;
  v6 = 0;
  if ( !RegOpenKeyExW(hKey, L"Control Panel\\Desktop", 0, 0x20019u, &hKeya) )
  {
    cbData = 700;
    if ( !RegQueryValueExW(hKeya, L"PreferredUILanguagesPending", 0, &Type, (LPBYTE)Data, &cbData)
      || (cbData = 700, !RegQueryValueExW(hKeya, L"PreferredUILanguages", 0, &Type, (LPBYTE)Data, &cbData)) )
    {
      if ( Type == 7 && StringCchCopyW(a2, v3, Data) >= 0 )
        v6 = 1;
    }
    RegCloseKey(hKeya);
  }
  return v6;
}

```

## disassembly

```asm
0x1800258c8  push    rbp
0x1800258ca  push    rbx
0x1800258cb  push    rsi
0x1800258cc  push    rdi
0x1800258cd  push    r14
0x1800258cf  lea     rbp, [rsp-210h]
0x1800258d7  sub     rsp, 310h
0x1800258de  mov     rax, cs:__security_cookie
0x1800258e5  xor     rax, rsp
0x1800258e8  mov     [rbp+230h+var_30], rax
0x1800258ef  movsxd  r14, r8d
0x1800258f2  mov     rsi, rdx
0x1800258f5  mov     rbx, rcx
0x1800258f8  mov     [rsp+330h+hKey], 0
0x180025901  xor     edx, edx; Val
0x180025903  mov     [rsp+330h+Type], 0
0x18002590b  mov     r8d, 2BCh; Size
0x180025911  mov     [rsp+330h+cbData], 0
0x180025919  lea     rcx, [rsp+330h+Data]; void *
0x18002591e  call    memset_0
0x180025923  xor     eax, eax
0x180025925  lea     rdx, aControlPanelDe_0; "Control Panel\\Desktop"
0x18002592c  mov     [rsi], ax
0x18002592f  mov     r9d, 20019h; samDesired
0x180025935  lea     rax, [rsp+330h+hKey]
0x18002593a  xor     r8d, r8d; ulOptions
0x18002593d  mov     rcx, rbx; hKey
0x180025940  mov     [rsp+330h+phkResult], rax; phkResult
0x180025945  xor     edi, edi
0x180025947  call    cs:__imp_RegOpenKeyExW
0x18002594d  test    eax, eax
0x18002594f  jnz     loc_1800259F5
0x180025955  mov     rcx, [rsp+330h+hKey]; hKey
0x18002595a  lea     rax, [rsp+330h+cbData]
0x18002595f  mov     [rsp+330h+lpcbData], rax; lpcbData
0x180025964  lea     r9, [rsp+330h+Type]; lpType
0x180025969  lea     rax, [rsp+330h+Data]
0x18002596e  mov     [rsp+330h+cbData], 2BCh
0x180025976  xor     r8d, r8d; lpReserved
0x180025979  mov     [rsp+330h+phkResult], rax; lpData
0x18002597e  lea     rdx, aPreferreduilan; "PreferredUILanguagesPending"
0x180025985  call    cs:__imp_RegQueryValueExW
0x18002598b  test    eax, eax
0x18002598d  jz      short loc_1800259C9
0x18002598f  mov     rcx, [rsp+330h+hKey]; hKey
0x180025994  lea     rax, [rsp+330h+cbData]
0x180025999  mov     [rsp+330h+lpcbData], rax; lpcbData
0x18002599e  lea     r9, [rsp+330h+Type]; lpType
0x1800259a3  lea     rax, [rsp+330h+Data]
0x1800259a8  mov     [rsp+330h+cbData], 2BCh
0x1800259b0  xor     r8d, r8d; lpReserved
0x1800259b3  mov     [rsp+330h+phkResult], rax; lpData
0x1800259b8  lea     rdx, ?c_szUIPreferredLang@@3QBGB; "PreferredUILanguages"
0x1800259bf  call    cs:__imp_RegQueryValueExW
0x1800259c5  test    eax, eax
0x1800259c7  jnz     short loc_1800259EA
0x1800259c9  cmp     [rsp+330h+Type], 7
0x1800259ce  jnz     short loc_1800259EA
0x1800259d0  mov     rdx, r14; unsigned __int64
0x1800259d3  lea     r8, [rsp+330h+Data]; unsigned __int16 *
0x1800259d8  mov     rcx, rsi; unsigned __int16 *
0x1800259db  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800259e0  test    eax, eax
0x1800259e2  mov     ecx, 1
0x1800259e7  cmovns  edi, ecx
0x1800259ea  mov     rcx, [rsp+330h+hKey]; hKey
0x1800259ef  call    cs:__imp_RegCloseKey
0x1800259f5  mov     eax, edi
0x1800259f7  mov     rcx, [rbp+230h+var_30]
0x1800259fe  xor     rcx, rsp; StackCookie
0x180025a01  call    __security_check_cookie
0x180025a06  add     rsp, 310h
0x180025a0d  pop     r14
0x180025a0f  pop     rdi
0x180025a10  pop     rsi
0x180025a11  pop     rbx
0x180025a12  pop     rbp
0x180025a13  retn
```
