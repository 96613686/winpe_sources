# DrvGetProfileString(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t *,unsigned __int64)

- ea: `0x180133764`
- end: `0x1801339fb`
- name: `?DrvGetProfileString@@YA_KPEB_W00PEA_W_K@Z`
- size: `663`
- prototype: `unsigned __int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, const wchar_t *, wchar_t *, unsigned __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002fd30`
- `0x18013e7dc`
- `0x1801a6a70`

## callees

- `0x180003d80`
- `0x18000aaa0`
- `0x180133764`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x1801337dc`
- `ADVAPI32!RegOpenKeyExW` at `0x1801337dc`
- `ADVAPI32!RegEnumValueW` at `0x180133869`
- `ADVAPI32!RegEnumValueW` at `0x1801338d8`
- `ADVAPI32!RegEnumValueW` at `0x180133869`
- `ADVAPI32!RegEnumValueW` at `0x1801338d8`
- `ADVAPI32!RegQueryValueExW` at `0x180133946`
- `ADVAPI32!RegQueryValueExW` at `0x180133946`
- `ADVAPI32!RegCloseKey` at `0x1801339cd`
- `ADVAPI32!RegCloseKey` at `0x1801339cd`

## pseudocode

```c
unsigned __int64 __fastcall DrvGetProfileString(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        const wchar_t *a3,
        wchar_t *a4,
        unsigned __int64 a5)
{
  unsigned __int64 v5; // rdi
  unsigned __int64 v10; // rbx
  DWORD v11; // r14d
  DWORD v12; // r15d
  LSTATUS v13; // eax
  LSTATUS Value; // eax
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  unsigned __int64 v17; // rcx
  unsigned __int64 v18; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type[4]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR ValueName[136]; // [rsp+70h] [rbp-90h] BYREF

  v5 = a5;
  hKey = 0;
  cchValueName = 0;
  v18 = 0;
  Type[0] = 0;
  if ( a5 )
  {
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20019u, &hKey) )
    {
      if ( (int)StringCchCopyExW(a4, a5, a3, 0, &v18, 0) >= 0 )
        return a5 - v18;
      return 0;
    }
    if ( !lpValueName )
    {
      v10 = a5 - 1;
      *(_QWORD *)cbData = a4;
      v18 = a5 - 1;
      v11 = 0;
      if ( a5 != 1 )
      {
        while ( 1 )
        {
          v12 = v11;
          cchValueName = v10;
          v13 = RegEnumValueW(hKey, v11++, a4, &cchValueName, 0, 0, 0, 0);
          if ( v13 )
            break;
          if ( cchValueName )
          {
            a4 += cchValueName + 1;
            *(_QWORD *)cbData = a4;
            v10 += -1LL - cchValueName;
            v18 = v10;
          }
        }
        if ( v13 == 234 )
        {
          if ( v10 )
          {
            cchValueName = 129;
            if ( !RegEnumValueW(hKey, v12, ValueName, &cchValueName, 0, 0, 0, 0) )
            {
              StringCchCopyExW(a4, v10, ValueName, (wchar_t **)cbData, &v18, 0);
              a4 = (wchar_t *)(*(_QWORD *)cbData + 2LL);
              v10 = v18 - 1;
            }
          }
        }
      }
      *a4 = 0;
      v5 = a5 - v10;
      goto LABEL_17;
    }
    cbData[0] = 2 * a5;
    Value = RegQueryValueExW(hKey, lpValueName, 0, Type, (LPBYTE)a4, cbData);
    v15 = (unsigned __int64)cbData[0] >> 1;
    if ( Value == 234 )
    {
      a4[a5 - 1] = 0;
LABEL_17:
      v16 = v5 - 1;
LABEL_28:
      RegCloseKey(hKey);
      return v16;
    }
    if ( !Value )
    {
      if ( Type[0] == 1 )
      {
        if ( a4[v15 - 1] )
        {
          v17 = a5 - 1;
          if ( v15 < a5 )
            v17 = (unsigned __int64)cbData[0] >> 1;
          v16 = v17;
          a4[v17] = 0;
        }
        else
        {
          v16 = v15 - 1;
        }
      }
      else
      {
        v16 = 0;
        *a4 = 0;
      }
      goto LABEL_28;
    }
    if ( (int)StringCchCopyExW(a4, a5, a3, 0, &v18, 0) >= 0 )
    {
      v16 = a5 - v18;
      goto LABEL_28;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180133764  push    rbp
0x180133766  push    rbx
0x180133767  push    rsi
0x180133768  push    rdi
0x180133769  push    r12
0x18013376b  push    r14
0x18013376d  push    r15
0x18013376f  lea     rbp, [rsp-90h]
0x180133777  sub     rsp, 190h
0x18013377e  mov     rax, cs:__security_cookie
0x180133785  xor     rax, rsp
0x180133788  mov     [rbp+0C0h+var_40], rax
0x18013378f  mov     rdi, [rbp+0C0h+arg_20]
0x180133796  xor     r12d, r12d
0x180133799  mov     [rsp+1C0h+hKey], r12
0x18013379e  mov     rsi, r9
0x1801337a1  mov     [rsp+1C0h+cchValueName], r12d
0x1801337a6  mov     r14, r8
0x1801337a9  mov     [rsp+1C0h+var_180], r12
0x1801337ae  mov     rbx, rdx
0x1801337b1  mov     [rsp+1C0h+Type], r12d
0x1801337b6  test    rdi, rdi
0x1801337b9  jz      loc_1801339D8
0x1801337bf  lea     rax, [rsp+1C0h+hKey]
0x1801337c4  mov     rdx, rcx; lpSubKey
0x1801337c7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1801337ce  mov     [rsp+1C0h+phkResult], rax; phkResult
0x1801337d3  mov     r9d, 20019h; samDesired
0x1801337d9  xor     r8d, r8d; ulOptions
0x1801337dc  call    cs:__imp_RegOpenKeyExW
0x1801337e2  test    eax, eax
0x1801337e4  jz      short loc_18013381B
0x1801337e6  lea     rax, [rsp+1C0h+var_180]
0x1801337eb  mov     dword ptr [rsp+1C0h+lpType], r12d; unsigned int
0x1801337f0  xor     r9d, r9d; wchar_t **
0x1801337f3  mov     [rsp+1C0h+phkResult], rax; unsigned __int64 *
0x1801337f8  mov     r8, r14; wchar_t *
0x1801337fb  mov     rdx, rdi; unsigned __int64
0x1801337fe  mov     rcx, rsi; wchar_t *
0x180133801  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180133806  test    eax, eax
0x180133808  js      loc_1801339D8
0x18013380e  sub     rdi, [rsp+1C0h+var_180]
0x180133813  mov     rax, rdi
0x180133816  jmp     loc_1801339DA
0x18013381b  test    rbx, rbx
0x18013381e  jnz     loc_180133920
0x180133824  lea     rbx, [rdi-1]
0x180133828  mov     qword ptr [rsp+1C0h+cbData], rsi
0x18013382d  mov     [rsp+1C0h+var_180], rbx
0x180133832  mov     r14d, r12d
0x180133835  test    rbx, rbx
0x180133838  jz      loc_180133917
0x18013383e  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180133843  lea     r9, [rsp+1C0h+cchValueName]; lpcchValueName
0x180133848  mov     [rsp+1C0h+lpcbData], r12; lpcbData
0x18013384d  mov     r8, rsi; lpValueName
0x180133850  mov     [rsp+1C0h+lpData], r12; lpData
0x180133855  mov     edx, r14d; dwIndex
0x180133858  mov     [rsp+1C0h+lpType], r12; lpType
0x18013385d  mov     r15d, r14d
0x180133860  mov     [rsp+1C0h+phkResult], r12; lpReserved
0x180133865  mov     [rsp+1C0h+cchValueName], ebx
0x180133869  call    cs:__imp_RegEnumValueW
0x18013386f  inc     r14d
0x180133872  test    eax, eax
0x180133874  jnz     short loc_18013389E
0x180133876  mov     eax, [rsp+1C0h+cchValueName]
0x18013387a  test    eax, eax
0x18013387c  jz      short loc_18013383E
0x18013387e  lea     rsi, [rsi+rax*2]
0x180133882  mov     ecx, eax
0x180133884  or      rax, 0FFFFFFFFFFFFFFFFh
0x180133888  add     rsi, 2
0x18013388c  sub     rax, rcx
0x18013388f  mov     qword ptr [rsp+1C0h+cbData], rsi
0x180133894  add     rbx, rax
0x180133897  mov     [rsp+1C0h+var_180], rbx
0x18013389c  jmp     short loc_18013383E
0x18013389e  cmp     eax, 0EAh
0x1801338a3  jnz     short loc_180133917
0x1801338a5  test    rbx, rbx
0x1801338a8  jz      short loc_180133917
0x1801338aa  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1801338af  lea     r9, [rsp+1C0h+cchValueName]; lpcchValueName
0x1801338b4  mov     [rsp+1C0h+lpcbData], r12; lpcbData
0x1801338b9  lea     r8, [rsp+1C0h+ValueName]; lpValueName
0x1801338be  mov     [rsp+1C0h+lpData], r12; lpData
0x1801338c3  mov     edx, r15d; dwIndex
0x1801338c6  mov     [rsp+1C0h+lpType], r12; lpType
0x1801338cb  mov     [rsp+1C0h+phkResult], r12; lpReserved
0x1801338d0  mov     [rsp+1C0h+cchValueName], 81h
0x1801338d8  call    cs:__imp_RegEnumValueW
0x1801338de  test    eax, eax
0x1801338e0  jnz     short loc_180133917
0x1801338e2  lea     rax, [rsp+1C0h+var_180]
0x1801338e7  mov     dword ptr [rsp+1C0h+lpType], r12d; unsigned int
0x1801338ec  lea     r9, [rsp+1C0h+cbData]; wchar_t **
0x1801338f1  mov     [rsp+1C0h+phkResult], rax; unsigned __int64 *
0x1801338f6  lea     r8, [rsp+1C0h+ValueName]; wchar_t *
0x1801338fb  mov     rdx, rbx; unsigned __int64
0x1801338fe  mov     rcx, rsi; wchar_t *
0x180133901  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x180133906  mov     rsi, qword ptr [rsp+1C0h+cbData]
0x18013390b  mov     rbx, [rsp+1C0h+var_180]
0x180133910  add     rsi, 2
0x180133914  dec     rbx
0x180133917  mov     [rsi], r12w
0x18013391b  sub     rdi, rbx
0x18013391e  jmp     short loc_180133960
0x180133920  mov     rcx, [rsp+1C0h+hKey]; hKey
0x180133925  lea     eax, [rdi+rdi]
0x180133928  mov     [rsp+1C0h+cbData], eax
0x18013392c  lea     r9, [rsp+1C0h+Type]; lpType
0x180133931  lea     rax, [rsp+1C0h+cbData]
0x180133936  xor     r8d, r8d; lpReserved
0x180133939  mov     [rsp+1C0h+lpType], rax; lpcbData
0x18013393e  mov     rdx, rbx; lpValueName
0x180133941  mov     [rsp+1C0h+phkResult], rsi; lpData
0x180133946  call    cs:__imp_RegQueryValueExW
0x18013394c  mov     ebx, [rsp+1C0h+cbData]
0x180133950  shr     rbx, 1
0x180133953  cmp     eax, 0EAh
0x180133958  jnz     short loc_180133966
0x18013395a  mov     [rsi+rdi*2-2], r12w
0x180133960  lea     rbx, [rdi-1]
0x180133964  jmp     short loc_1801339C8
0x180133966  test    eax, eax
0x180133968  jz      short loc_180133998
0x18013396a  lea     rax, [rsp+1C0h+var_180]
0x18013396f  mov     dword ptr [rsp+1C0h+lpType], r12d; unsigned int
0x180133974  xor     r9d, r9d; wchar_t **
0x180133977  mov     [rsp+1C0h+phkResult], rax; unsigned __int64 *
0x18013397c  mov     r8, r14; wchar_t *
0x18013397f  mov     rdx, rdi; unsigned __int64
0x180133982  mov     rcx, rsi; wchar_t *
0x180133985  call    ?StringCchCopyExW@@YAJPEA_W_KPEB_WPEAPEA_WPEA_KK@Z; StringCchCopyExW(wchar_t *,unsigned __int64,wchar_t const *,wchar_t * *,unsigned __int64 *,ulong)
0x18013398a  test    eax, eax
0x18013398c  js      short loc_1801339D8
0x18013398e  mov     rbx, rdi
0x180133991  sub     rbx, [rsp+1C0h+var_180]
0x180133996  jmp     short loc_1801339C8
0x180133998  cmp     [rsp+1C0h+Type], 1
0x18013399d  jz      short loc_1801339A8
0x18013399f  mov     rbx, r12
0x1801339a2  mov     [rsi], r12w
0x1801339a6  jmp     short loc_1801339C8
0x1801339a8  cmp     [rsi+rbx*2-2], r12w
0x1801339ae  jnz     short loc_1801339B5
0x1801339b0  dec     rbx
0x1801339b3  jmp     short loc_1801339C8
0x1801339b5  cmp     rbx, rdi
0x1801339b8  lea     rcx, [rdi-1]
0x1801339bc  cmovb   rcx, rbx
0x1801339c0  mov     rbx, rcx
0x1801339c3  mov     [rsi+rcx*2], r12w
0x1801339c8  mov     rcx, [rsp+1C0h+hKey]; hKey
0x1801339cd  call    cs:__imp_RegCloseKey
0x1801339d3  mov     rax, rbx
0x1801339d6  jmp     short loc_1801339DA
0x1801339d8  xor     eax, eax
0x1801339da  mov     rcx, [rbp+0C0h+var_40]
0x1801339e1  xor     rcx, rsp; StackCookie
0x1801339e4  call    __security_check_cookie
0x1801339e9  add     rsp, 190h
0x1801339f0  pop     r15
0x1801339f2  pop     r14
0x1801339f4  pop     r12
0x1801339f6  pop     rdi
0x1801339f7  pop     rsi
0x1801339f8  pop     rbx
0x1801339f9  pop     rbp
0x1801339fa  retn
```
