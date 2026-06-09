# NfsLdapRfc2307Enabled

- ea: `0x18002b7b4`
- end: `0x18002ba68`
- name: `NfsLdapRfc2307Enabled`
- size: `692`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002b368`

## callees

- `0x180001cc6`
- `0x180001cd2`
- `0x18002b7b4`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18002b820`
- `ADVAPI32!RegOpenKeyExW` at `0x18002b820`
- `ADVAPI32!RegCloseKey` at `0x18002ba48`
- `ADVAPI32!RegCloseKey` at `0x18002ba48`
- `ADVAPI32!RegQueryValueExW` at `0x18002b858`
- `ADVAPI32!RegQueryValueExW` at `0x18002b8b2`
- `ADVAPI32!RegQueryValueExW` at `0x18002b903`
- `ADVAPI32!RegQueryValueExW` at `0x18002b955`
- `ADVAPI32!RegQueryValueExW` at `0x18002b99f`
- `ADVAPI32!RegQueryValueExW` at `0x18002b9f3`
- `ADVAPI32!RegQueryValueExW` at `0x18002b858`
- `ADVAPI32!RegQueryValueExW` at `0x18002b8b2`
- `ADVAPI32!RegQueryValueExW` at `0x18002b903`
- `ADVAPI32!RegQueryValueExW` at `0x18002b955`
- `ADVAPI32!RegQueryValueExW` at `0x18002b99f`
- `ADVAPI32!RegQueryValueExW` at `0x18002b9f3`

## string_xrefs

- `0x18002b7f5`: `SOFTWARE\Microsoft\ServicesForNFS`

## pseudocode

```c
__int64 __fastcall NfsLdapRfc2307Enabled(_DWORD *a1, _DWORD *a2, BYTE *a3, __int64 a4, void **a5)
{
  unsigned int v9; // ebx
  void **v10; // r14
  HKEY v11; // rcx
  DWORD v12; // eax
  BYTE *v13; // rsi
  DWORD lpcbData; // [rsp+30h] [rbp-20h] BYREF
  DWORD cbData; // [rsp+38h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-10h] BYREF
  DWORD v17; // [rsp+90h] [rbp+40h] BYREF
  int Data; // [rsp+98h] [rbp+48h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+58h] BYREF

  lpcbData = 520;
  *a1 = 0;
  *a2 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 4;
  v17 = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SOFTWARE\\Microsoft\\ServicesForNFS", 0, 0x20019u, &hKey) )
    return 3221225473LL;
  if ( RegQueryValueExW(hKey, L"Rfc2307", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    goto LABEL_10;
  v9 = 0;
  if ( Data )
  {
    *a1 = 1;
    if ( !a3 || !lpcbData )
      goto LABEL_42;
    if ( !RegQueryValueExW(hKey, L"Rfc2307Domain", 0, &Type, a3, &lpcbData) )
    {
      if ( Type != 1 )
      {
LABEL_10:
        v9 = -1073741823;
        goto LABEL_13;
      }
      if ( *(_WORD *)a3 )
        *a2 = 1;
    }
  }
LABEL_13:
  if ( !*a1 )
  {
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"Rfc2307LdapLookup", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    {
      v9 = -1073741823;
    }
    else
    {
      v9 = 0;
      if ( Data )
      {
        *a1 = 1;
        if ( a3 && lpcbData && !RegQueryValueExW(hKey, L"Rfc2307LdapServer", 0, &Type, a3, &lpcbData) )
        {
          if ( Type == 1 )
          {
            if ( *(_WORD *)a3 )
              *a2 = 1;
          }
          else
          {
            v9 = -1073741823;
          }
        }
        v10 = a5;
        v11 = hKey;
        if ( !a5 )
          goto LABEL_43;
        if ( RegQueryValueExW(hKey, L"Rfc2307LdapNamingContext", 0, &Type, 0, &v17) || Type == 1 )
        {
          v12 = v17;
        }
        else
        {
          v12 = 0;
          v9 = -1073741823;
          v17 = 0;
        }
        if ( v12 )
        {
          v13 = (BYTE *)malloc_0(v12 + 2LL);
          if ( v13 )
          {
            if ( !RegQueryValueExW(hKey, L"Rfc2307LdapNamingContext", 0, &Type, v13, &v17) )
            {
              if ( Type == 1 )
              {
                if ( *(_WORD *)v13 )
                {
                  *(_WORD *)&v13[2 * ((unsigned __int64)v17 >> 1)] = 0;
                  if ( *v10 )
                    free_0(*v10);
                  *v10 = v13;
                  v13 = 0;
                }
              }
              else
              {
                v9 = -1073741823;
              }
            }
            if ( v13 )
              free_0(v13);
          }
          else
          {
            v9 = -1073741670;
          }
        }
      }
    }
  }
LABEL_42:
  v11 = hKey;
LABEL_43:
  if ( v11 )
    RegCloseKey(v11);
  return v9;
}

```

## disassembly

```asm
0x18002b7b4  mov     [rsp-38h+arg_10], rbx
0x18002b7b9  mov     [rsp-38h+Type], r9d
0x18002b7be  push    rbp
0x18002b7bf  push    rsi
0x18002b7c0  push    rdi
0x18002b7c1  push    r12
0x18002b7c3  push    r13
0x18002b7c5  push    r14
0x18002b7c7  push    r15
0x18002b7c9  mov     rbp, rsp
0x18002b7cc  sub     rsp, 50h
0x18002b7d0  xor     r12d, r12d
0x18002b7d3  mov     [rbp+var_20], 208h
0x18002b7da  mov     [rcx], r12d
0x18002b7dd  lea     rax, [rbp+hKey]
0x18002b7e1  mov     [rdx], r12d
0x18002b7e4  mov     rsi, r8
0x18002b7e7  mov     r15, rdx
0x18002b7ea  mov     [rbp+hKey], r12
0x18002b7ee  mov     r14, rcx
0x18002b7f1  mov     [rbp+Type], r12d
0x18002b7f5  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\ServicesForNFS"
0x18002b7fc  mov     [rbp+Data], r12d
0x18002b800  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002b807  mov     [rbp+cbData], 4
0x18002b80e  mov     r9d, 20019h; samDesired
0x18002b814  mov     [rbp+arg_0], r12d
0x18002b818  xor     r8d, r8d; ulOptions
0x18002b81b  mov     [rsp+50h+phkResult], rax; phkResult
0x18002b820  call    cs:__imp_RegOpenKeyExW
0x18002b826  test    eax, eax
0x18002b828  jz      short loc_18002B834
0x18002b82a  mov     eax, 0C0000001h
0x18002b82f  jmp     loc_18002BA50
0x18002b834  mov     rcx, [rbp+hKey]; hKey
0x18002b838  lea     rax, [rbp+cbData]
0x18002b83c  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002b841  lea     r9, [rbp+Type]; lpType
0x18002b845  lea     rax, [rbp+Data]
0x18002b849  xor     r8d, r8d; lpReserved
0x18002b84c  lea     rdx, aRfc2307; "Rfc2307"
0x18002b853  mov     [rsp+50h+phkResult], rax; lpData
0x18002b858  call    cs:__imp_RegQueryValueExW
0x18002b85e  mov     edi, 0C0000001h
0x18002b863  mov     r13d, 1
0x18002b869  test    eax, eax
0x18002b86b  jnz     short loc_18002B8C2
0x18002b86d  cmp     [rbp+Type], 4
0x18002b871  jnz     short loc_18002B8C2
0x18002b873  mov     ebx, r12d
0x18002b876  cmp     [rbp+Data], r12d
0x18002b87a  jz      short loc_18002B8CF
0x18002b87c  mov     [r14], r13d
0x18002b87f  test    rsi, rsi
0x18002b882  jz      loc_18002BA3F
0x18002b888  cmp     [rbp+var_20], r12d
0x18002b88c  jz      loc_18002BA3F
0x18002b892  mov     rcx, [rbp+hKey]; hKey
0x18002b896  lea     rax, [rbp+var_20]
0x18002b89a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002b89f  lea     r9, [rbp+Type]; lpType
0x18002b8a3  xor     r8d, r8d; lpReserved
0x18002b8a6  mov     [rsp+50h+phkResult], rsi; lpData
0x18002b8ab  lea     rdx, aRfc2307domain; "Rfc2307Domain"
0x18002b8b2  call    cs:__imp_RegQueryValueExW
0x18002b8b8  test    eax, eax
0x18002b8ba  jnz     short loc_18002B8CF
0x18002b8bc  cmp     [rbp+Type], r13d
0x18002b8c0  jz      short loc_18002B8C6
0x18002b8c2  mov     ebx, edi
0x18002b8c4  jmp     short loc_18002B8CF
0x18002b8c6  cmp     [rsi], r12w
0x18002b8ca  jz      short loc_18002B8CF
0x18002b8cc  mov     [r15], r13d
0x18002b8cf  cmp     [r14], r12d
0x18002b8d2  jnz     loc_18002BA3F
0x18002b8d8  mov     rcx, [rbp+hKey]; hKey
0x18002b8dc  lea     rax, [rbp+cbData]
0x18002b8e0  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002b8e5  lea     r9, [rbp+Type]; lpType
0x18002b8e9  lea     rax, [rbp+Data]
0x18002b8ed  mov     [rbp+cbData], 4
0x18002b8f4  xor     r8d, r8d; lpReserved
0x18002b8f7  mov     [rsp+50h+phkResult], rax; lpData
0x18002b8fc  lea     rdx, aRfc2307ldaploo; "Rfc2307LdapLookup"
0x18002b903  call    cs:__imp_RegQueryValueExW
0x18002b909  test    eax, eax
0x18002b90b  jz      short loc_18002B914
0x18002b90d  mov     ebx, edi
0x18002b90f  jmp     loc_18002BA3F
0x18002b914  cmp     [rbp+Type], 4
0x18002b918  jnz     short loc_18002B90D
0x18002b91a  mov     ebx, r12d
0x18002b91d  cmp     [rbp+Data], r12d
0x18002b921  jz      loc_18002BA3F
0x18002b927  mov     [r14], r13d
0x18002b92a  test    rsi, rsi
0x18002b92d  jz      short loc_18002B972
0x18002b92f  cmp     [rbp+var_20], r12d
0x18002b933  jz      short loc_18002B972
0x18002b935  mov     rcx, [rbp+hKey]; hKey
0x18002b939  lea     rax, [rbp+var_20]
0x18002b93d  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002b942  lea     r9, [rbp+Type]; lpType
0x18002b946  xor     r8d, r8d; lpReserved
0x18002b949  mov     [rsp+50h+phkResult], rsi; lpData
0x18002b94e  lea     rdx, aRfc2307ldapser; "Rfc2307LdapServer"
0x18002b955  call    cs:__imp_RegQueryValueExW
0x18002b95b  test    eax, eax
0x18002b95d  jnz     short loc_18002B972
0x18002b95f  cmp     [rbp+Type], r13d
0x18002b963  jz      short loc_18002B969
0x18002b965  mov     ebx, edi
0x18002b967  jmp     short loc_18002B972
0x18002b969  cmp     [rsi], r12w
0x18002b96d  jz      short loc_18002B972
0x18002b96f  mov     [r15], r13d
0x18002b972  mov     r14, [rbp+arg_20]
0x18002b976  mov     rcx, [rbp+hKey]; hKey
0x18002b97a  test    r14, r14
0x18002b97d  jz      loc_18002BA43
0x18002b983  lea     rax, [rbp+arg_0]
0x18002b987  xor     r8d, r8d; lpReserved
0x18002b98a  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002b98f  lea     r9, [rbp+Type]; lpType
0x18002b993  lea     rdx, aRfc2307ldapnam; "Rfc2307LdapNamingContext"
0x18002b99a  mov     [rsp+50h+phkResult], r12; lpData
0x18002b99f  call    cs:__imp_RegQueryValueExW
0x18002b9a5  test    eax, eax
0x18002b9a7  jnz     short loc_18002B9B9
0x18002b9a9  cmp     [rbp+Type], r13d
0x18002b9ad  jz      short loc_18002B9B9
0x18002b9af  mov     eax, r12d
0x18002b9b2  mov     ebx, edi
0x18002b9b4  mov     [rbp+arg_0], eax
0x18002b9b7  jmp     short loc_18002B9BC
0x18002b9b9  mov     eax, [rbp+arg_0]
0x18002b9bc  test    eax, eax
0x18002b9be  jz      short loc_18002BA3F
0x18002b9c0  mov     ecx, eax
0x18002b9c2  add     rcx, 2; Size
0x18002b9c6  call    malloc_0
0x18002b9cb  mov     rsi, rax
0x18002b9ce  test    rax, rax
0x18002b9d1  jz      short loc_18002BA3A
0x18002b9d3  mov     rcx, [rbp+hKey]; hKey
0x18002b9d7  lea     rax, [rbp+arg_0]
0x18002b9db  mov     [rsp+50h+lpcbData], rax; lpcbData
0x18002b9e0  lea     r9, [rbp+Type]; lpType
0x18002b9e4  xor     r8d, r8d; lpReserved
0x18002b9e7  mov     [rsp+50h+phkResult], rsi; lpData
0x18002b9ec  lea     rdx, aRfc2307ldapnam; "Rfc2307LdapNamingContext"
0x18002b9f3  call    cs:__imp_RegQueryValueExW
0x18002b9f9  test    eax, eax
0x18002b9fb  jnz     short loc_18002BA2B
0x18002b9fd  cmp     [rbp+Type], r13d
0x18002ba01  jz      short loc_18002BA07
0x18002ba03  mov     ebx, edi
0x18002ba05  jmp     short loc_18002BA2B
0x18002ba07  cmp     [rsi], r12w
0x18002ba0b  jz      short loc_18002BA2B
0x18002ba0d  mov     ecx, [rbp+arg_0]
0x18002ba10  shr     rcx, 1
0x18002ba13  mov     [rsi+rcx*2], r12w
0x18002ba18  mov     rcx, [r14]; Block
0x18002ba1b  test    rcx, rcx
0x18002ba1e  jz      short loc_18002BA25
0x18002ba20  call    free_0
0x18002ba25  mov     [r14], rsi
0x18002ba28  mov     rsi, r12
0x18002ba2b  test    rsi, rsi
0x18002ba2e  jz      short loc_18002BA3F
0x18002ba30  mov     rcx, rsi; Block
0x18002ba33  call    free_0
0x18002ba38  jmp     short loc_18002BA3F
0x18002ba3a  mov     ebx, 0C000009Ah
0x18002ba3f  mov     rcx, [rbp+hKey]; hKey
0x18002ba43  test    rcx, rcx
0x18002ba46  jz      short loc_18002BA4E
0x18002ba48  call    cs:__imp_RegCloseKey
0x18002ba4e  mov     eax, ebx
0x18002ba50  mov     rbx, [rsp+50h+arg_10]
0x18002ba58  add     rsp, 50h
0x18002ba5c  pop     r15
0x18002ba5e  pop     r14
0x18002ba60  pop     r13
0x18002ba62  pop     r12
0x18002ba64  pop     rdi
0x18002ba65  pop     rsi
0x18002ba66  pop     rbp
0x18002ba67  retn
```
