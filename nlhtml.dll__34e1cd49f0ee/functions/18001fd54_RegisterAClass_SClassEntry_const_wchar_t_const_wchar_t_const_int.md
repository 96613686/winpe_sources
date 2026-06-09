# RegisterAClass(SClassEntry const &,wchar_t const *,wchar_t const *,int)

- ea: `0x18001fd54`
- end: `0x18002009c`
- name: `?RegisterAClass@@YAJAEBUSClassEntry@@PEB_W1H@Z`
- size: `840`
- prototype: `__int64 __fastcall(const struct SClassEntry *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800200a4`
- `0x18002107c`

## callees

- `0x1800112e0`
- `0x180011324`
- `0x180014130`
- `0x18001fafc`
- `0x18001fd54`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fe88`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020003`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001fe88`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020003`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ffb1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ffb1`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001feda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002002e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020069`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001feda`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002002e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180020069`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fe39`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ff74`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001fe39`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18001ff74`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fdef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ff32`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001fdef`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ff32`

## string_xrefs

- `0x18001fefe`: `\CLSID`

## pseudocode

```c
int __fastcall RegisterAClass(const struct SClassEntry *a1, const wchar_t *a2, const wchar_t *a3, int a4)
{
  LSTATUS v4; // ebx
  const wchar_t *v6; // rsi
  int result; // eax
  LSTATUS v9; // eax
  const BYTE *v10; // rcx
  __int64 v11; // rax
  LSTATUS v12; // eax
  const wchar_t *v13; // r8
  __int64 v14; // rax
  __int64 v15; // rax
  LSTATUS v16; // eax
  const wchar_t *v17; // rdx
  const BYTE *v18; // rcx
  __int64 v19; // rax
  LSTATUS v20; // eax
  WCHAR *v21; // r8
  int phkResult; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  DWORD cbData; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD Type[4]; // [rsp+60h] [rbp-A0h] BYREF
  wchar_t SubKey[264]; // [rsp+70h] [rbp-90h] BYREF

  v4 = 0;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  v6 = a3;
  if ( !a3 )
    a3 = (const wchar_t *)*((_QWORD *)a1 + 1);
  result = StringCchCopyW(SubKey, 0x104u, a3);
  if ( result >= 0 )
  {
    dwDisposition = 0;
    Type[0] = 0;
    cbData = 0;
    if ( a4 )
    {
      v9 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &hKey);
      if ( v9 )
        goto LABEL_6;
      dwDisposition = 2;
    }
    else
    {
      v4 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
      if ( v4 )
        goto LABEL_45;
      v4 = 0;
      if ( dwDisposition == 1 && !v6 )
      {
        v10 = (const BYTE *)*((_QWORD *)a1 + 2);
        v11 = -1;
        do
          ++v11;
        while ( *(_WORD *)&v10[2 * v11] );
        v12 = RegSetValueExW(hKey, 0, 0, 1u, v10, 2 * v11 + 2);
        v13 = (const wchar_t *)*((_QWORD *)a1 + 1);
        v4 = v12;
        v14 = -1;
        do
          ++v14;
        while ( v13[v14] );
        if ( (unsigned __int64)(v14 + 7) > 0x104 )
        {
          v4 = -2147024809;
          goto LABEL_45;
        }
        StringCchCopyW(SubKey, 0x104u, v13);
        if ( v4 )
          goto LABEL_45;
        v4 = 0;
      }
    }
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
    {
      RegCloseKey(hKey);
      hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
    }
    v15 = -1;
    do
      ++v15;
    while ( SubKey[v15] );
    StringCchCatW(SubKey, 260 - v15, L"\\CLSID");
    if ( a4 )
    {
      v9 = RegOpenKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0x2001Fu, &hKey);
      if ( v9 )
      {
LABEL_6:
        if ( v9 != 2 )
          v4 = v9;
        goto LABEL_45;
      }
      dwDisposition = 2;
    }
    else
    {
      v4 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition);
      if ( v4 )
        goto LABEL_45;
    }
    cbData = 520;
    v16 = RegQueryValueExW(hKey, 0, 0, Type, (LPBYTE)SubKey, &cbData);
    v4 = v16;
    if ( !v16 )
    {
      if ( Type[0] != 1 )
        v4 = -2147467259;
      goto LABEL_39;
    }
    if ( v16 == 2 )
    {
      if ( a4 )
      {
        v4 = 0;
        goto LABEL_45;
      }
      v18 = (const BYTE *)*((_QWORD *)a1 + 3);
      v19 = -1;
      do
        ++v19;
      while ( *(_WORD *)&v18[2 * v19] );
      v20 = RegSetValueExW(hKey, 0, 0, 1u, v18, 2 * v19 + 2);
      SubKey[0] = 0;
      v4 = v20;
      if ( !v20 )
      {
LABEL_39:
        if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
        {
          RegCloseKey(hKey);
          hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
        }
        if ( !v4 )
        {
          v21 = SubKey;
          if ( !SubKey[0] )
            v21 = 0;
          v4 = RegisterACLSID(a1, v17, v21, a4, phkResult);
        }
      }
    }
LABEL_45:
    if ( hKey != HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
      RegCloseKey(hKey);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x18001fd54  mov     [rsp-8+arg_8], rbx
0x18001fd59  mov     [rsp-8+arg_18], rsi
0x18001fd5e  push    rbp
0x18001fd5f  push    rdi
0x18001fd60  push    r12
0x18001fd62  push    r13
0x18001fd64  push    r15
0x18001fd66  lea     rbp, [rsp-190h]
0x18001fd6e  sub     rsp, 290h
0x18001fd75  mov     rax, cs:__security_cookie
0x18001fd7c  xor     rax, rsp
0x18001fd7f  mov     [rbp+1B0h+var_30], rax
0x18001fd86  xor     ebx, ebx
0x18001fd88  mov     [rsp+2B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18001fd91  mov     edi, 104h
0x18001fd96  mov     r12d, r9d
0x18001fd99  mov     rsi, r8
0x18001fd9c  mov     r13, rcx
0x18001fd9f  mov     edx, edi; unsigned __int64
0x18001fda1  test    r8, r8
0x18001fda4  jnz     short loc_18001FDAA
0x18001fda6  mov     r8, [rcx+8]; wchar_t *
0x18001fdaa  lea     rcx, [rsp+2B0h+SubKey]; wchar_t *
0x18001fdaf  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001fdb4  test    eax, eax
0x18001fdb6  js      loc_180020071
0x18001fdbc  xor     r8d, r8d; Reserved
0x18001fdbf  mov     [rsp+2B0h+dwDisposition], ebx
0x18001fdc3  mov     [rsp+2B0h+Type], ebx
0x18001fdc7  mov     r15, 0FFFFFFFF80000000h
0x18001fdce  mov     [rsp+2B0h+cbData], ebx
0x18001fdd2  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18001fdd7  mov     rcx, r15; hKey
0x18001fdda  test    r12d, r12d
0x18001fddd  jz      short loc_18001FE11
0x18001fddf  lea     rax, [rsp+2B0h+hKey]
0x18001fde4  mov     r9d, 2001Fh; samDesired
0x18001fdea  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001fdef  call    cs:__imp_RegOpenKeyExW
0x18001fdf5  test    eax, eax
0x18001fdf7  jz      short loc_18001FE04
0x18001fdf9  cmp     eax, 2
0x18001fdfc  cmovnz  ebx, eax
0x18001fdff  jmp     loc_18002005E
0x18001fe04  mov     [rsp+2B0h+dwDisposition], 2
0x18001fe0c  jmp     loc_18001FECF
0x18001fe11  lea     rax, [rsp+2B0h+dwDisposition]
0x18001fe16  xor     r9d, r9d; lpClass
0x18001fe19  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x18001fe1e  lea     rax, [rsp+2B0h+hKey]
0x18001fe23  mov     [rsp+2B0h+var_278], rax; phkResult
0x18001fe28  mov     [rsp+2B0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18001fe2d  mov     [rsp+2B0h+samDesired], 2001Fh; samDesired
0x18001fe35  mov     dword ptr [rsp+2B0h+phkResult], ebx; dwOptions
0x18001fe39  call    cs:__imp_RegCreateKeyExW
0x18001fe3f  mov     ebx, eax
0x18001fe41  test    eax, eax
0x18001fe43  jnz     loc_18002005E
0x18001fe49  xor     ebx, ebx
0x18001fe4b  cmp     [rsp+2B0h+dwDisposition], 1
0x18001fe50  jnz     short loc_18001FECF
0x18001fe52  test    rsi, rsi
0x18001fe55  jnz     short loc_18001FECF
0x18001fe57  mov     rcx, [r13+10h]
0x18001fe5b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fe5f  inc     rax
0x18001fe62  cmp     [rcx+rax*2], bx
0x18001fe66  jnz     short loc_18001FE5F
0x18001fe68  lea     eax, ds:2[rax*2]
0x18001fe6f  mov     r9d, 1; dwType
0x18001fe75  mov     [rsp+2B0h+samDesired], eax; cbData
0x18001fe79  xor     r8d, r8d; Reserved
0x18001fe7c  mov     [rsp+2B0h+phkResult], rcx; lpData
0x18001fe81  xor     edx, edx; lpValueName
0x18001fe83  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001fe88  call    cs:__imp_RegSetValueExW
0x18001fe8e  mov     r8, [r13+8]; wchar_t *
0x18001fe92  mov     ebx, eax
0x18001fe94  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fe98  xor     r11d, r11d
0x18001fe9b  inc     rax
0x18001fe9e  cmp     [r8+rax*2], r11w
0x18001fea3  jnz     short loc_18001FE9B
0x18001fea5  add     rax, 7
0x18001fea9  cmp     rax, rdi
0x18001feac  jbe     short loc_18001FEB8
0x18001feae  mov     ebx, 80070057h
0x18001feb3  jmp     loc_18002005E
0x18001feb8  mov     rdx, rdi; unsigned __int64
0x18001febb  lea     rcx, [rsp+2B0h+SubKey]; wchar_t *
0x18001fec0  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001fec5  test    ebx, ebx
0x18001fec7  jnz     loc_18002005E
0x18001fecd  xor     ebx, ebx
0x18001fecf  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001fed4  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18001fed8  jz      short loc_18001FEE9
0x18001feda  call    cs:__imp_RegCloseKey
0x18001fee0  mov     [rsp+2B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18001fee9  lea     rcx, [rsp+2B0h+SubKey]
0x18001feee  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001fef2  inc     rax
0x18001fef5  cmp     [rcx+rax*2], bx
0x18001fef9  jnz     short loc_18001FEF2
0x18001fefb  sub     rdi, rax
0x18001fefe  lea     r8, aClsid_0; "\\CLSID"
0x18001ff05  mov     rdx, rdi; unsigned __int64
0x18001ff08  lea     rcx, [rsp+2B0h+SubKey]; wchar_t *
0x18001ff0d  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x18001ff12  xor     r8d, r8d; Reserved
0x18001ff15  lea     rdx, [rsp+2B0h+SubKey]; lpSubKey
0x18001ff1a  mov     rcx, r15; hKey
0x18001ff1d  test    r12d, r12d
0x18001ff20  jz      short loc_18001FF4C
0x18001ff22  lea     rax, [rsp+2B0h+hKey]
0x18001ff27  mov     r9d, 2001Fh; samDesired
0x18001ff2d  mov     [rsp+2B0h+phkResult], rax; phkResult
0x18001ff32  call    cs:__imp_RegOpenKeyExW
0x18001ff38  test    eax, eax
0x18001ff3a  jnz     loc_18001FDF9
0x18001ff40  mov     [rsp+2B0h+dwDisposition], 2
0x18001ff48  xor     edi, edi
0x18001ff4a  jmp     short loc_18001FF86
0x18001ff4c  lea     rax, [rsp+2B0h+dwDisposition]
0x18001ff51  xor     r9d, r9d; lpClass
0x18001ff54  mov     [rsp+2B0h+lpdwDisposition], rax; lpdwDisposition
0x18001ff59  lea     rax, [rsp+2B0h+hKey]
0x18001ff5e  mov     [rsp+2B0h+var_278], rax; phkResult
0x18001ff63  mov     [rsp+2B0h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18001ff68  mov     [rsp+2B0h+samDesired], 2001Fh; samDesired
0x18001ff70  mov     dword ptr [rsp+2B0h+phkResult], ebx; dwOptions
0x18001ff74  call    cs:__imp_RegCreateKeyExW
0x18001ff7a  xor     edi, edi
0x18001ff7c  mov     ebx, eax
0x18001ff7e  test    eax, eax
0x18001ff80  jnz     loc_18002005E
0x18001ff86  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001ff8b  lea     rax, [rsp+2B0h+cbData]
0x18001ff90  mov     qword ptr [rsp+2B0h+samDesired], rax; lpcbData
0x18001ff95  lea     r9, [rsp+2B0h+Type]; lpType
0x18001ff9a  lea     rax, [rsp+2B0h+SubKey]
0x18001ff9f  mov     [rsp+2B0h+cbData], 208h
0x18001ffa7  xor     r8d, r8d; lpReserved
0x18001ffaa  mov     [rsp+2B0h+phkResult], rax; int
0x18001ffaf  xor     edx, edx; lpValueName
0x18001ffb1  call    cs:__imp_RegQueryValueExW
0x18001ffb7  mov     ebx, eax
0x18001ffb9  test    eax, eax
0x18001ffbb  jz      short loc_180020016
0x18001ffbd  cmp     eax, 2
0x18001ffc0  jnz     loc_18002005E
0x18001ffc6  test    r12d, r12d
0x18001ffc9  jz      short loc_18001FFD2
0x18001ffcb  mov     ebx, edi
0x18001ffcd  jmp     loc_18002005E
0x18001ffd2  mov     rcx, [r13+18h]
0x18001ffd6  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ffda  inc     rax
0x18001ffdd  cmp     [rcx+rax*2], di
0x18001ffe1  jnz     short loc_18001FFDA
0x18001ffe3  lea     eax, ds:2[rax*2]
0x18001ffea  mov     r9d, 1; dwType
0x18001fff0  mov     [rsp+2B0h+samDesired], eax; cbData
0x18001fff4  xor     r8d, r8d; Reserved
0x18001fff7  mov     [rsp+2B0h+phkResult], rcx; lpData
0x18001fffc  xor     edx, edx; lpValueName
0x18001fffe  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180020003  call    cs:__imp_RegSetValueExW
0x180020009  mov     [rsp+2B0h+SubKey], di
0x18002000e  mov     ebx, eax
0x180020010  test    eax, eax
0x180020012  jnz     short loc_18002005E
0x180020014  jmp     short loc_180020023
0x180020016  cmp     [rsp+2B0h+Type], 1
0x18002001b  mov     eax, 80004005h
0x180020020  cmovnz  ebx, eax
0x180020023  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180020028  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18002002c  jz      short loc_18002003D
0x18002002e  call    cs:__imp_RegCloseKey
0x180020034  mov     [rsp+2B0h+hKey], 0FFFFFFFFFFFFFFFFh
0x18002003d  test    ebx, ebx
0x18002003f  jnz     short loc_18002005E
0x180020041  xor     ecx, ecx
0x180020043  lea     r8, [rsp+2B0h+SubKey]
0x180020048  cmp     cx, [rsp+2B0h+SubKey]
0x18002004d  mov     r9d, r12d; int
0x180020050  mov     rcx, r13; struct SClassEntry *
0x180020053  cmovz   r8, rdi; wchar_t *
0x180020057  call    ?RegisterACLSID@@YAJAEBUSClassEntry@@PEB_W1HH@Z; RegisterACLSID(SClassEntry const &,wchar_t const *,wchar_t const *,int,int)
0x18002005c  mov     ebx, eax
0x18002005e  mov     rcx, [rsp+2B0h+hKey]; hKey
0x180020063  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180020067  jz      short loc_18002006F
0x180020069  call    cs:__imp_RegCloseKey
0x18002006f  mov     eax, ebx
0x180020071  mov     rcx, [rbp+1B0h+var_30]
0x180020078  xor     rcx, rsp; StackCookie
0x18002007b  call    __security_check_cookie
0x180020080  lea     r11, [rsp+2B0h+var_20]
0x180020088  mov     rbx, [r11+38h]
0x18002008c  mov     rsi, [r11+48h]
0x180020090  mov     rsp, r11
0x180020093  pop     r15
0x180020095  pop     r13
0x180020097  pop     r12
0x180020099  pop     rdi
0x18002009a  pop     rbp
0x18002009b  retn
```
