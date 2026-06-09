# NfsLdapRfc2307Enabled

- ea: `0x140017fa8`
- end: `0x14001825c`
- name: `NfsLdapRfc2307Enabled`
- size: `692`
- prototype: `__int64 __fastcall(_DWORD *, _DWORD *, BYTE *, __int64, void **)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1400100f0`
- `0x140017b10`

## callees

- `0x1400016e2`
- `0x1400016ee`
- `0x140017fa8`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x140018014`
- `ADVAPI32!RegOpenKeyExW` at `0x140018014`
- `ADVAPI32!RegCloseKey` at `0x14001823c`
- `ADVAPI32!RegCloseKey` at `0x14001823c`
- `ADVAPI32!RegQueryValueExW` at `0x14001804c`
- `ADVAPI32!RegQueryValueExW` at `0x1400180a6`
- `ADVAPI32!RegQueryValueExW` at `0x1400180f7`
- `ADVAPI32!RegQueryValueExW` at `0x140018149`
- `ADVAPI32!RegQueryValueExW` at `0x140018193`
- `ADVAPI32!RegQueryValueExW` at `0x1400181e7`
- `ADVAPI32!RegQueryValueExW` at `0x14001804c`
- `ADVAPI32!RegQueryValueExW` at `0x1400180a6`
- `ADVAPI32!RegQueryValueExW` at `0x1400180f7`
- `ADVAPI32!RegQueryValueExW` at `0x140018149`
- `ADVAPI32!RegQueryValueExW` at `0x140018193`
- `ADVAPI32!RegQueryValueExW` at `0x1400181e7`

## string_xrefs

- `0x140017fe9`: `SOFTWARE\Microsoft\ServicesForNFS`

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
0x140017fa8  mov     [rsp-38h+arg_10], rbx
0x140017fad  mov     [rsp-38h+Type], r9d
0x140017fb2  push    rbp
0x140017fb3  push    rsi
0x140017fb4  push    rdi
0x140017fb5  push    r12
0x140017fb7  push    r13
0x140017fb9  push    r14
0x140017fbb  push    r15
0x140017fbd  mov     rbp, rsp
0x140017fc0  sub     rsp, 50h
0x140017fc4  xor     r12d, r12d
0x140017fc7  mov     [rbp+var_20], 208h
0x140017fce  mov     [rcx], r12d
0x140017fd1  lea     rax, [rbp+hKey]
0x140017fd5  mov     [rdx], r12d
0x140017fd8  mov     rsi, r8
0x140017fdb  mov     r15, rdx
0x140017fde  mov     [rbp+hKey], r12
0x140017fe2  mov     r14, rcx
0x140017fe5  mov     [rbp+Type], r12d
0x140017fe9  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\ServicesForNFS"
0x140017ff0  mov     [rbp+Data], r12d
0x140017ff4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140017ffb  mov     [rbp+cbData], 4
0x140018002  mov     r9d, 20019h; samDesired
0x140018008  mov     [rbp+arg_0], r12d
0x14001800c  xor     r8d, r8d; ulOptions
0x14001800f  mov     [rsp+50h+phkResult], rax; phkResult
0x140018014  call    cs:__imp_RegOpenKeyExW
0x14001801a  test    eax, eax
0x14001801c  jz      short loc_140018028
0x14001801e  mov     eax, 0C0000001h
0x140018023  jmp     loc_140018244
0x140018028  mov     rcx, [rbp+hKey]; hKey
0x14001802c  lea     rax, [rbp+cbData]
0x140018030  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140018035  lea     r9, [rbp+Type]; lpType
0x140018039  lea     rax, [rbp+Data]
0x14001803d  xor     r8d, r8d; lpReserved
0x140018040  lea     rdx, aRfc2307; "Rfc2307"
0x140018047  mov     [rsp+50h+phkResult], rax; lpData
0x14001804c  call    cs:__imp_RegQueryValueExW
0x140018052  mov     edi, 0C0000001h
0x140018057  mov     r13d, 1
0x14001805d  test    eax, eax
0x14001805f  jnz     short loc_1400180B6
0x140018061  cmp     [rbp+Type], 4
0x140018065  jnz     short loc_1400180B6
0x140018067  mov     ebx, r12d
0x14001806a  cmp     [rbp+Data], r12d
0x14001806e  jz      short loc_1400180C3
0x140018070  mov     [r14], r13d
0x140018073  test    rsi, rsi
0x140018076  jz      loc_140018233
0x14001807c  cmp     [rbp+var_20], r12d
0x140018080  jz      loc_140018233
0x140018086  mov     rcx, [rbp+hKey]; hKey
0x14001808a  lea     rax, [rbp+var_20]
0x14001808e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140018093  lea     r9, [rbp+Type]; lpType
0x140018097  xor     r8d, r8d; lpReserved
0x14001809a  mov     [rsp+50h+phkResult], rsi; lpData
0x14001809f  lea     rdx, aRfc2307domain; "Rfc2307Domain"
0x1400180a6  call    cs:__imp_RegQueryValueExW
0x1400180ac  test    eax, eax
0x1400180ae  jnz     short loc_1400180C3
0x1400180b0  cmp     [rbp+Type], r13d
0x1400180b4  jz      short loc_1400180BA
0x1400180b6  mov     ebx, edi
0x1400180b8  jmp     short loc_1400180C3
0x1400180ba  cmp     [rsi], r12w
0x1400180be  jz      short loc_1400180C3
0x1400180c0  mov     [r15], r13d
0x1400180c3  cmp     [r14], r12d
0x1400180c6  jnz     loc_140018233
0x1400180cc  mov     rcx, [rbp+hKey]; hKey
0x1400180d0  lea     rax, [rbp+cbData]
0x1400180d4  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1400180d9  lea     r9, [rbp+Type]; lpType
0x1400180dd  lea     rax, [rbp+Data]
0x1400180e1  mov     [rbp+cbData], 4
0x1400180e8  xor     r8d, r8d; lpReserved
0x1400180eb  mov     [rsp+50h+phkResult], rax; lpData
0x1400180f0  lea     rdx, aRfc2307ldaploo; "Rfc2307LdapLookup"
0x1400180f7  call    cs:__imp_RegQueryValueExW
0x1400180fd  test    eax, eax
0x1400180ff  jz      short loc_140018108
0x140018101  mov     ebx, edi
0x140018103  jmp     loc_140018233
0x140018108  cmp     [rbp+Type], 4
0x14001810c  jnz     short loc_140018101
0x14001810e  mov     ebx, r12d
0x140018111  cmp     [rbp+Data], r12d
0x140018115  jz      loc_140018233
0x14001811b  mov     [r14], r13d
0x14001811e  test    rsi, rsi
0x140018121  jz      short loc_140018166
0x140018123  cmp     [rbp+var_20], r12d
0x140018127  jz      short loc_140018166
0x140018129  mov     rcx, [rbp+hKey]; hKey
0x14001812d  lea     rax, [rbp+var_20]
0x140018131  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140018136  lea     r9, [rbp+Type]; lpType
0x14001813a  xor     r8d, r8d; lpReserved
0x14001813d  mov     [rsp+50h+phkResult], rsi; lpData
0x140018142  lea     rdx, aRfc2307ldapser; "Rfc2307LdapServer"
0x140018149  call    cs:__imp_RegQueryValueExW
0x14001814f  test    eax, eax
0x140018151  jnz     short loc_140018166
0x140018153  cmp     [rbp+Type], r13d
0x140018157  jz      short loc_14001815D
0x140018159  mov     ebx, edi
0x14001815b  jmp     short loc_140018166
0x14001815d  cmp     [rsi], r12w
0x140018161  jz      short loc_140018166
0x140018163  mov     [r15], r13d
0x140018166  mov     r14, [rbp+arg_20]
0x14001816a  mov     rcx, [rbp+hKey]; hKey
0x14001816e  test    r14, r14
0x140018171  jz      loc_140018237
0x140018177  lea     rax, [rbp+arg_0]
0x14001817b  xor     r8d, r8d; lpReserved
0x14001817e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x140018183  lea     r9, [rbp+Type]; lpType
0x140018187  lea     rdx, aRfc2307ldapnam; "Rfc2307LdapNamingContext"
0x14001818e  mov     [rsp+50h+phkResult], r12; lpData
0x140018193  call    cs:__imp_RegQueryValueExW
0x140018199  test    eax, eax
0x14001819b  jnz     short loc_1400181AD
0x14001819d  cmp     [rbp+Type], r13d
0x1400181a1  jz      short loc_1400181AD
0x1400181a3  mov     eax, r12d
0x1400181a6  mov     ebx, edi
0x1400181a8  mov     [rbp+arg_0], eax
0x1400181ab  jmp     short loc_1400181B0
0x1400181ad  mov     eax, [rbp+arg_0]
0x1400181b0  test    eax, eax
0x1400181b2  jz      short loc_140018233
0x1400181b4  mov     ecx, eax
0x1400181b6  add     rcx, 2; Size
0x1400181ba  call    malloc_0
0x1400181bf  mov     rsi, rax
0x1400181c2  test    rax, rax
0x1400181c5  jz      short loc_14001822E
0x1400181c7  mov     rcx, [rbp+hKey]; hKey
0x1400181cb  lea     rax, [rbp+arg_0]
0x1400181cf  mov     [rsp+50h+lpcbData], rax; lpcbData
0x1400181d4  lea     r9, [rbp+Type]; lpType
0x1400181d8  xor     r8d, r8d; lpReserved
0x1400181db  mov     [rsp+50h+phkResult], rsi; lpData
0x1400181e0  lea     rdx, aRfc2307ldapnam; "Rfc2307LdapNamingContext"
0x1400181e7  call    cs:__imp_RegQueryValueExW
0x1400181ed  test    eax, eax
0x1400181ef  jnz     short loc_14001821F
0x1400181f1  cmp     [rbp+Type], r13d
0x1400181f5  jz      short loc_1400181FB
0x1400181f7  mov     ebx, edi
0x1400181f9  jmp     short loc_14001821F
0x1400181fb  cmp     [rsi], r12w
0x1400181ff  jz      short loc_14001821F
0x140018201  mov     ecx, [rbp+arg_0]
0x140018204  shr     rcx, 1
0x140018207  mov     [rsi+rcx*2], r12w
0x14001820c  mov     rcx, [r14]; Block
0x14001820f  test    rcx, rcx
0x140018212  jz      short loc_140018219
0x140018214  call    free_0
0x140018219  mov     [r14], rsi
0x14001821c  mov     rsi, r12
0x14001821f  test    rsi, rsi
0x140018222  jz      short loc_140018233
0x140018224  mov     rcx, rsi; Block
0x140018227  call    free_0
0x14001822c  jmp     short loc_140018233
0x14001822e  mov     ebx, 0C000009Ah
0x140018233  mov     rcx, [rbp+hKey]; hKey
0x140018237  test    rcx, rcx
0x14001823a  jz      short loc_140018242
0x14001823c  call    cs:__imp_RegCloseKey
0x140018242  mov     eax, ebx
0x140018244  mov     rbx, [rsp+50h+arg_10]
0x14001824c  add     rsp, 50h
0x140018250  pop     r15
0x140018252  pop     r14
0x140018254  pop     r13
0x140018256  pop     r12
0x140018258  pop     rdi
0x140018259  pop     rsi
0x14001825a  pop     rbp
0x14001825b  retn
```
