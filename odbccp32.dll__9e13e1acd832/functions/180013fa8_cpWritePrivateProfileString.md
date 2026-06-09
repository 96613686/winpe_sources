# cpWritePrivateProfileString

- ea: `0x180013fa8`
- end: `0x180014186`
- name: `cpWritePrivateProfileString`
- size: `478`
- prototype: `__int64 __fastcall(HKEY hKey, __int64, const WCHAR *, DWORD, BYTE *lpData, __int64)`
- caller_count: `9`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180006184`
- `0x180006afc`
- `0x180006db8`
- `0x180007200`
- `0x180007628`
- `0x1800085c8`
- `0x18000a1b4`
- `0x18000dc70`
- `0x1800134d4`

## callees

- `0x180002e4c`
- `0x180004bac`
- `0x180004bdc`
- `0x1800137e4`
- `0x180013fa8`
- `0x180014ae0`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x180014139`
- `ADVAPI32!RegCloseKey` at `0x180014139`
- `ADVAPI32!RegDeleteValueW` at `0x1800140e0`
- `ADVAPI32!RegDeleteValueW` at `0x1800140e0`
- `ADVAPI32!RegCreateKeyExW` at `0x1800140c4`
- `ADVAPI32!RegCreateKeyExW` at `0x1800140c4`
- `ADVAPI32!RegSetValueExW` at `0x18001412c`
- `ADVAPI32!RegSetValueExW` at `0x18001412c`
- `ADVAPI32!RegOpenKeyExW` at `0x18001407a`
- `ADVAPI32!RegOpenKeyExW` at `0x18001407a`

## pseudocode

```c
__int64 __fastcall cpWritePrivateProfileString(
        HKEY hKey,
        __int64 a2,
        const WCHAR *a3,
        DWORD a4,
        BYTE *lpData,
        __int64 a6)
{
  __int64 v6; // rdi
  __int64 v9; // rcx
  __int64 v11; // rax
  unsigned int v12; // ebx
  LSTATUS v13; // eax
  LSTATUS v14; // edi
  DWORD v15; // edi
  HKEY hKeya; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t pszDest[272]; // [rsp+60h] [rbp-A0h] BYREF

  v6 = -1;
  hKeya = 0;
  dwDisposition = 0;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(a2 + 2 * v9) );
  v11 = -1;
  do
    ++v11;
  while ( *(_WORD *)(a6 + 2 * v11) );
  if ( (unsigned int)(v9 + 16 + v11) < 0x10E )
  {
    StringCchPrintfW(pszDest, 0x10Eu, L"%s%s\\%s", L"SOFTWARE\\ODBC\\", a6, a2);
    if ( !a3 )
    {
      CPRegDeleteKey(hKey, pszDest);
      return 1;
    }
    v13 = RegOpenKeyExW(hKey, pszDest, 0, 0x20006u, &hKeya);
    if ( !v13 )
      goto LABEL_13;
    if ( !lpData && v13 == 1168 )
      return 1;
    if ( !RegCreateKeyExW(hKey, pszDest, 0, 0, 0, 0x20006u, 0, &hKeya, &dwDisposition) )
    {
LABEL_13:
      v12 = 1;
      if ( lpData )
      {
        if ( a4 == 1 )
        {
          do
            ++v6;
          while ( *(_WORD *)&lpData[2 * v6] );
          v15 = 2 * v6 + 2;
        }
        else
        {
          v15 = 4;
        }
        v14 = RegSetValueExW(hKeya, a3, 0, a4, lpData, v15);
      }
      else
      {
        v14 = RegDeleteValueW(hKeya, a3);
        if ( v14 == 2 )
          PostInstError(6);
      }
      RegCloseKey(hKeya);
      if ( !v14 )
        return v12;
    }
    PostInstError(19);
    return 0;
  }
  PostInstErrorMsgId(1, 1416);
  return 0;
}

```

## disassembly

```asm
0x180013fa8  push    rbp
0x180013faa  push    rbx
0x180013fab  push    rsi
0x180013fac  push    rdi
0x180013fad  push    r12
0x180013faf  push    r14
0x180013fb1  push    r15
0x180013fb3  lea     rbp, [rsp-190h]
0x180013fbb  sub     rsp, 290h
0x180013fc2  mov     rax, cs:__security_cookie
0x180013fc9  xor     rax, rsp
0x180013fcc  mov     [rbp+1C0h+var_40], rax
0x180013fd3  mov     rsi, [rbp+1C0h+lpData]
0x180013fda  xor     r12d, r12d
0x180013fdd  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013fe1  mov     [rsp+2C0h+hKey], r12
0x180013fe6  mov     r14, r8
0x180013fe9  mov     [rsp+2C0h+dwDisposition], r12d
0x180013fee  mov     r8, [rbp+1C0h+arg_28]
0x180013ff5  mov     rbx, rcx
0x180013ff8  mov     rcx, rdi
0x180013ffb  mov     r15d, r9d
0x180013ffe  inc     rcx
0x180014001  cmp     [rdx+rcx*2], r12w
0x180014006  jnz     short loc_180013FFE
0x180014008  mov     rax, rdi
0x18001400b  inc     rax
0x18001400e  cmp     [r8+rax*2], r12w
0x180014013  jnz     short loc_18001400B
0x180014015  add     ecx, 10h
0x180014018  add     eax, ecx
0x18001401a  mov     ecx, 10Eh
0x18001401f  cmp     eax, ecx
0x180014021  jnb     loc_180014154
0x180014027  mov     qword ptr [rsp+2C0h+samDesired], rdx
0x18001402c  lea     r9, aSoftwareOdbc; "SOFTWARE\\ODBC\\"
0x180014033  mov     [rsp+2C0h+phkResult], r8
0x180014038  mov     edx, ecx; cchDest
0x18001403a  lea     r8, aSSS; "%s%s\\%s"
0x180014041  lea     rcx, [rsp+2C0h+pszDest]; pszDest
0x180014046  call    StringCchPrintfW
0x18001404b  lea     rdx, [rsp+2C0h+pszDest]; lpSubKey
0x180014050  mov     rcx, rbx; hKey
0x180014053  test    r14, r14
0x180014056  jnz     short loc_180014067
0x180014058  call    CPRegDeleteKey
0x18001405d  mov     ebx, 1
0x180014062  jmp     loc_180014150
0x180014067  lea     rax, [rsp+2C0h+hKey]
0x18001406c  mov     r9d, 20006h; samDesired
0x180014072  xor     r8d, r8d; ulOptions
0x180014075  mov     [rsp+2C0h+phkResult], rax; phkResult
0x18001407a  call    cs:__imp_RegOpenKeyExW
0x180014080  test    eax, eax
0x180014082  jz      short loc_1800140CE
0x180014084  test    rsi, rsi
0x180014087  jnz     short loc_180014090
0x180014089  cmp     eax, 490h
0x18001408e  jz      short loc_18001405D
0x180014090  lea     rax, [rsp+2C0h+dwDisposition]
0x180014095  xor     r9d, r9d; lpClass
0x180014098  mov     [rsp+2C0h+lpdwDisposition], rax; lpdwDisposition
0x18001409d  lea     rdx, [rsp+2C0h+pszDest]; lpSubKey
0x1800140a2  lea     rax, [rsp+2C0h+hKey]
0x1800140a7  xor     r8d, r8d; Reserved
0x1800140aa  mov     [rsp+2C0h+var_288], rax; phkResult
0x1800140af  mov     rcx, rbx; hKey
0x1800140b2  mov     [rsp+2C0h+lpSecurityAttributes], r12; lpSecurityAttributes
0x1800140b7  mov     [rsp+2C0h+samDesired], 20006h; samDesired
0x1800140bf  mov     dword ptr [rsp+2C0h+phkResult], r12d; dwOptions
0x1800140c4  call    cs:__imp_RegCreateKeyExW
0x1800140ca  test    eax, eax
0x1800140cc  jnz     short loc_180014143
0x1800140ce  mov     ebx, 1
0x1800140d3  test    rsi, rsi
0x1800140d6  jnz     short loc_1800140F7
0x1800140d8  mov     rcx, [rsp+2C0h+hKey]; hKey
0x1800140dd  mov     rdx, r14; lpValueName
0x1800140e0  call    cs:__imp_RegDeleteValueW
0x1800140e6  mov     edi, eax
0x1800140e8  cmp     eax, 2
0x1800140eb  jnz     short loc_180014134
0x1800140ed  lea     ecx, [rbx+5]
0x1800140f0  call    PostInstError
0x1800140f5  jmp     short loc_180014134
0x1800140f7  cmp     r15d, ebx
0x1800140fa  jnz     short loc_180014110
0x1800140fc  inc     rdi
0x1800140ff  cmp     [rsi+rdi*2], r12w
0x180014104  jnz     short loc_1800140FC
0x180014106  lea     rdi, ds:2[rdi*2]
0x18001410e  jmp     short loc_180014115
0x180014110  mov     edi, 4
0x180014115  mov     rcx, [rsp+2C0h+hKey]; hKey
0x18001411a  mov     r9d, r15d; dwType
0x18001411d  mov     [rsp+2C0h+samDesired], edi; cbData
0x180014121  xor     r8d, r8d; Reserved
0x180014124  mov     rdx, r14; lpValueName
0x180014127  mov     [rsp+2C0h+phkResult], rsi; lpData
0x18001412c  call    cs:__imp_RegSetValueExW
0x180014132  mov     edi, eax
0x180014134  mov     rcx, [rsp+2C0h+hKey]; hKey
0x180014139  call    cs:__imp_RegCloseKey
0x18001413f  test    edi, edi
0x180014141  jz      short loc_180014150
0x180014143  mov     ecx, 13h
0x180014148  call    PostInstError
0x18001414d  mov     ebx, r12d
0x180014150  mov     eax, ebx
0x180014152  jmp     short loc_180014165
0x180014154  mov     edx, 588h
0x180014159  mov     ecx, 1
0x18001415e  call    PostInstErrorMsgId
0x180014163  xor     eax, eax
0x180014165  mov     rcx, [rbp+1C0h+var_40]
0x18001416c  xor     rcx, rsp; StackCookie
0x18001416f  call    __security_check_cookie
0x180014174  add     rsp, 290h
0x18001417b  pop     r15
0x18001417d  pop     r14
0x18001417f  pop     r12
0x180014181  pop     rdi
0x180014182  pop     rsi
0x180014183  pop     rbx
0x180014184  pop     rbp
0x180014185  retn
```
