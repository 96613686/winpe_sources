# ADHasLicensingAttrs(ushort const *)

- ea: `0x180075980`
- end: `0x180075d63`
- name: `?ADHasLicensingAttrs@@YAHPEBG@Z`
- size: `995`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x180075e34`
- `0x1800762fc`
- `0x180076938`

## callees

- `0x18000d060`
- `0x180075980`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180075be9`
- `msvcrt!_wcsicmp` at `0x180075c0f`
- `msvcrt!_wcsicmp` at `0x180075c31`
- `msvcrt!_wcsicmp` at `0x180075c53`
- `msvcrt!_wcsicmp` at `0x180075c75`
- `msvcrt!_wcsicmp` at `0x180075be9`
- `msvcrt!_wcsicmp` at `0x180075c0f`
- `msvcrt!_wcsicmp` at `0x180075c31`
- `msvcrt!_wcsicmp` at `0x180075c53`
- `msvcrt!_wcsicmp` at `0x180075c75`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180075a3e`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180075ae2`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180075a3e`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x180075ae2`
- `OLEAUT32!__imp_SysAllocString` at `0x180075a59`
- `OLEAUT32!__imp_SysAllocString` at `0x180075a59`
- `OLEAUT32!__imp_SysFreeString` at `0x180075cf7`
- `OLEAUT32!__imp_SysFreeString` at `0x180075cf7`
- `OLEAUT32!__imp_VariantInit` at `0x1800759dd`
- `OLEAUT32!__imp_VariantInit` at `0x180075b07`
- `OLEAUT32!__imp_VariantInit` at `0x180075b71`
- `OLEAUT32!__imp_VariantInit` at `0x1800759dd`
- `OLEAUT32!__imp_VariantInit` at `0x180075b07`
- `OLEAUT32!__imp_VariantInit` at `0x180075b71`
- `OLEAUT32!__imp_VariantClear` at `0x180075c94`
- `OLEAUT32!__imp_VariantClear` at `0x180075cd2`
- `OLEAUT32!__imp_VariantClear` at `0x180075ce3`
- `OLEAUT32!__imp_VariantClear` at `0x180075c94`
- `OLEAUT32!__imp_VariantClear` at `0x180075cd2`
- `OLEAUT32!__imp_VariantClear` at `0x180075ce3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180075ba3`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x180075ba3`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180075b8a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x180075b8a`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180075bce`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x180075bce`

## pseudocode

```c
__int64 __fastcall ADHasLicensingAttrs(const unsigned __int16 *a1)
{
  unsigned int v2; // r14d
  OLECHAR *v3; // rsi
  char v4; // r15
  char v5; // di
  char v6; // r12
  char v7; // r13
  SAFEARRAY *parray; // rbx
  LONG v9; // eax
  IRecordInfo *pRecInfo; // rbx
  char v12; // [rsp+38h] [rbp-D0h]
  LONG rgIndices; // [rsp+3Ch] [rbp-CCh] BYREF
  LONG plLbound[2]; // [rsp+40h] [rbp-C8h] BYREF
  void *ppObject; // [rsp+48h] [rbp-C0h] BYREF
  VARIANTARG pvarg; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v17; // [rsp+68h] [rbp-A0h]
  VARIANTARG pv; // [rsp+70h] [rbp-98h] BYREF
  __int64 v19; // [rsp+88h] [rbp-80h]
  VARIANTARG v20; // [rsp+90h] [rbp-78h] BYREF
  WCHAR szPathName[264]; // [rsp+A8h] [rbp-60h] BYREF
  WCHAR v22[264]; // [rsp+2B8h] [rbp+1B0h] BYREF

  v2 = 0;
  ppObject = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v3 = 0;
  v17 = 0;
  VariantInit((VARIANTARG *)&pvarg.decVal.8);
  if ( a1 )
    StringCchPrintfW(szPathName, 0x104u, L"LDAP://%s/rootDSE", a1);
  else
    StringCchPrintfW(szPathName, 0x104u, L"LDAP://rootDSE");
  if ( ADsOpenObject(szPathName, 0, 0, 0xC5u, &IID_IADs, &ppObject) >= 0 )
  {
    v3 = SysAllocString(L"schemaNamingContext");
    if ( (*(int (__fastcall **)(void *, OLECHAR *, CY *))(*(_QWORD *)ppObject + 120LL))(ppObject, v3, &pvarg.cyVal) >= 0 )
    {
      if ( a1 )
        StringCchPrintfW(v22, 0x104u, L"LDAP://%s/cn=user,%s", a1, pvarg.pRecInfo);
      else
        StringCchPrintfW(v22, 0x104u, L"LDAP://cn=user,%s", pvarg.pRecInfo);
      if ( ADsOpenObject(v22, 0, 0, 0xC5u, &IID_IADs, (void **)&pvarg) >= 0 )
      {
        memset(&v20, 0, sizeof(v20));
        VariantInit(&v20);
        v12 = 0;
        v4 = 0;
        v5 = 0;
        v6 = 0;
        v7 = 0;
        if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**(_QWORD **)&pvarg.vt + 136LL))(
               *(_QWORD *)&pvarg.vt,
               L"systemMayContain",
               &v20) >= 0 )
        {
          parray = v20.parray;
          plLbound[0] = 0;
          plLbound[1] = 0;
          *(_QWORD *)&pv.vt = v20.llVal;
          *(_OWORD *)&pv.decVal.Lo32 = 0;
          v19 = 0;
          VariantInit((VARIANTARG *)&pv.decVal.8);
          SafeArrayGetLBound(parray, 1u, plLbound);
          SafeArrayGetUBound(parray, 1u, &plLbound[1]);
          v9 = plLbound[0];
          while ( 1 )
          {
            rgIndices = v9;
            if ( v9 > plLbound[1] )
              break;
            SafeArrayGetElement(parray, &rgIndices, &pv.decVal.8);
            pRecInfo = pv.pRecInfo;
            if ( _wcsicmp(L"msTSExpireDate", (const wchar_t *)pv.pRecInfo) )
            {
              if ( _wcsicmp(L"msTSLicenseVersion", (const wchar_t *)pRecInfo) )
              {
                if ( _wcsicmp(L"msTSLicenseVersion2", (const wchar_t *)pRecInfo) )
                {
                  if ( _wcsicmp(L"msTSLicenseVersion3", (const wchar_t *)pRecInfo) )
                  {
                    if ( !_wcsicmp(L"msTSManagingLS", (const wchar_t *)pRecInfo) )
                      v5 = 1;
                  }
                  else
                  {
                    v7 = 1;
                  }
                }
                else
                {
                  v6 = 1;
                }
              }
              else
              {
                v4 = 1;
              }
            }
            else
            {
              v12 = 1;
            }
            VariantClear((VARIANTARG *)&pv.decVal.8);
            if ( v12 && v4 && v5 && v6 && v7 )
            {
              v2 = 1;
              break;
            }
            v9 = rgIndices + 1;
            parray = *(SAFEARRAY **)&pv.vt;
          }
          VariantClear(&v20);
        }
      }
    }
  }
  VariantClear((VARIANTARG *)&pvarg.decVal.8);
  if ( v3 )
    SysFreeString(v3);
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  if ( *(_QWORD *)&pvarg.vt )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)&pvarg.vt + 16LL))(*(_QWORD *)&pvarg.vt);
  return v2;
}

```

## disassembly

```asm
0x180075980  mov     rax, rsp
0x180075983  mov     [rax+10h], rbx
0x180075987  mov     [rax+18h], rsi
0x18007598b  mov     [rax+20h], rdi
0x18007598f  push    rbp
0x180075990  push    r12
0x180075992  push    r13
0x180075994  push    r14
0x180075996  push    r15
0x180075998  lea     rbp, [rax-3F8h]
0x18007599f  sub     rsp, 4D0h
0x1800759a6  mov     rax, cs:__security_cookie
0x1800759ad  xor     rax, rsp
0x1800759b0  mov     [rbp+3F0h+var_30], rax
0x1800759b7  mov     rdi, rcx
0x1800759ba  xor     r14d, r14d
0x1800759bd  and     [rsp+4F0h+var_4B0], r14
0x1800759c2  lea     rcx, [rsp+4F0h+pvarg+8]; pvarg
0x1800759c7  and     qword ptr [rsp+4F0h+pvarg], r14
0x1800759cc  xorps   xmm0, xmm0
0x1800759cf  xor     eax, eax
0x1800759d1  xor     esi, esi
0x1800759d3  movups  xmmword ptr [rsp+4F0h+pvarg+8], xmm0
0x1800759d8  mov     [rsp+4F0h+var_490], rax
0x1800759dd  call    cs:__imp_VariantInit
0x1800759e4  nop     dword ptr [rax+rax+00h]
0x1800759e9  lea     rcx, [rbp+3F0h+szPathName]; unsigned __int16 *
0x1800759ed  mov     ebx, 104h
0x1800759f2  mov     edx, ebx; unsigned __int64
0x1800759f4  test    rdi, rdi
0x1800759f7  jnz     short loc_180075A07
0x1800759f9  lea     r8, aLdapRootdse_0; "LDAP://rootDSE"
0x180075a00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180075a05  jmp     short loc_180075A16
0x180075a07  mov     r9, rdi
0x180075a0a  lea     r8, aLdapSRootdse; "LDAP://%s/rootDSE"
0x180075a11  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180075a16  lea     rax, [rsp+4F0h+var_4B0]
0x180075a1b  mov     r15d, 0C5h
0x180075a21  mov     [rsp+4F0h+ppObject], rax; ppObject
0x180075a26  lea     r12, IID_IADs
0x180075a2d  mov     r9d, r15d; dwReserved
0x180075a30  mov     [rsp+4F0h+riid], r12; riid
0x180075a35  xor     r8d, r8d; lpszPassword
0x180075a38  lea     rcx, [rbp+3F0h+szPathName]; lpszPathName
0x180075a3c  xor     edx, edx; lpszUserName
0x180075a3e  call    cs:__imp_ADsOpenObject
0x180075a45  nop     dword ptr [rax+rax+00h]
0x180075a4a  test    eax, eax
0x180075a4c  js      loc_180075CDE
0x180075a52  lea     rcx, aSchemanamingco; "schemaNamingContext"
0x180075a59  call    cs:__imp_SysAllocString
0x180075a60  nop     dword ptr [rax+rax+00h]
0x180075a65  mov     rcx, [rsp+4F0h+var_4B0]
0x180075a6a  lea     r8, [rsp+4F0h+pvarg+8]
0x180075a6f  mov     rsi, rax
0x180075a72  mov     rdx, rsi
0x180075a75  mov     rax, [rcx]
0x180075a78  mov     rax, [rax+78h]
0x180075a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075a81  test    eax, eax
0x180075a83  js      loc_180075CDE
0x180075a89  lea     rcx, [rbp+3F0h+var_240]; unsigned __int16 *
0x180075a90  mov     rdx, rbx; unsigned __int64
0x180075a93  test    rdi, rdi
0x180075a96  jnz     short loc_180075AAB
0x180075a98  mov     r9, qword ptr [rsp+4F0h+pvarg+10h]
0x180075a9d  lea     r8, aLdapCnUserS; "LDAP://cn=user,%s"
0x180075aa4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180075aa9  jmp     short loc_180075AC4
0x180075aab  mov     rax, qword ptr [rsp+4F0h+pvarg+10h]
0x180075ab0  lea     r8, aLdapSCnUserS; "LDAP://%s/cn=user,%s"
0x180075ab7  mov     r9, rdi
0x180075aba  mov     [rsp+4F0h+riid], rax
0x180075abf  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180075ac4  lea     rax, [rsp+4F0h+pvarg]
0x180075ac9  mov     r9d, r15d; dwReserved
0x180075acc  mov     [rsp+4F0h+ppObject], rax; ppObject
0x180075ad1  lea     rcx, [rbp+3F0h+var_240]; lpszPathName
0x180075ad8  xor     r8d, r8d; lpszPassword
0x180075adb  mov     [rsp+4F0h+riid], r12; riid
0x180075ae0  xor     edx, edx; lpszUserName
0x180075ae2  call    cs:__imp_ADsOpenObject
0x180075ae9  nop     dword ptr [rax+rax+00h]
0x180075aee  test    eax, eax
0x180075af0  js      loc_180075CDE
0x180075af6  xorps   xmm0, xmm0
0x180075af9  lea     rcx, [rbp+3F0h+var_468]; pvarg
0x180075afd  xor     eax, eax
0x180075aff  movups  xmmword ptr [rbp+3F0h+var_468], xmm0
0x180075b03  mov     qword ptr [rbp+3F0h+var_468+10h], rax
0x180075b07  call    cs:__imp_VariantInit
0x180075b0e  nop     dword ptr [rax+rax+00h]
0x180075b13  mov     rcx, qword ptr [rsp+4F0h+pvarg]
0x180075b18  lea     r8, [rbp+3F0h+var_468]
0x180075b1c  lea     rdx, aSystemmayconta; "systemMayContain"
0x180075b23  mov     byte ptr [rsp+4F0h+var_4C0], r14b
0x180075b28  xor     r15b, r15b
0x180075b2b  xor     dil, dil
0x180075b2e  xor     r12b, r12b
0x180075b31  xor     r13b, r13b
0x180075b34  mov     rax, [rcx]
0x180075b37  mov     rax, [rax+88h]
0x180075b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075b43  test    eax, eax
0x180075b45  js      loc_180075CDE
0x180075b4b  mov     rbx, qword ptr [rbp+3F0h+var_468+8]
0x180075b4f  lea     rcx, [rsp+4F0h+pv+8]; pvarg
0x180075b54  and     [rsp+4F0h+plLbound], r14d
0x180075b59  xorps   xmm0, xmm0
0x180075b5c  and     [rsp+4F0h+plLbound+4], r14d
0x180075b61  xor     eax, eax
0x180075b63  mov     qword ptr [rsp+4F0h+pv], rbx
0x180075b68  movups  xmmword ptr [rsp+4F0h+pv+8], xmm0
0x180075b6d  mov     [rbp+3F0h+var_470], rax
0x180075b71  call    cs:__imp_VariantInit
0x180075b78  nop     dword ptr [rax+rax+00h]
0x180075b7d  lea     r8, [rsp+4F0h+plLbound]; plLbound
0x180075b82  mov     edx, 1; nDim
0x180075b87  mov     rcx, rbx; psa
0x180075b8a  call    cs:__imp_SafeArrayGetLBound
0x180075b91  nop     dword ptr [rax+rax+00h]
0x180075b96  lea     r8, [rsp+4F0h+plLbound+4]; plUbound
0x180075b9b  mov     edx, 1; nDim
0x180075ba0  mov     rcx, rbx; psa
0x180075ba3  call    cs:__imp_SafeArrayGetUBound
0x180075baa  nop     dword ptr [rax+rax+00h]
0x180075baf  mov     eax, [rsp+4F0h+plLbound]
0x180075bb3  mov     [rsp+4F0h+rgIndices], eax
0x180075bb7  cmp     eax, [rsp+4F0h+plLbound+4]
0x180075bbb  jg      loc_180075CCE
0x180075bc1  lea     r8, [rsp+4F0h+pv+8]; pv
0x180075bc6  mov     rcx, rbx; psa
0x180075bc9  lea     rdx, [rsp+4F0h+rgIndices]; rgIndices
0x180075bce  call    cs:__imp_SafeArrayGetElement
0x180075bd5  nop     dword ptr [rax+rax+00h]
0x180075bda  mov     rbx, qword ptr [rsp+4F0h+pv+10h]
0x180075bdf  lea     rcx, aMstsexpiredate; "msTSExpireDate"
0x180075be6  mov     rdx, rbx; String2
0x180075be9  call    cs:__imp__wcsicmp
0x180075bf0  nop     dword ptr [rax+rax+00h]
0x180075bf5  test    eax, eax
0x180075bf7  jnz     short loc_180075C05
0x180075bf9  lea     ebx, [rax+1]
0x180075bfc  mov     byte ptr [rsp+4F0h+var_4C0], bl
0x180075c00  jmp     loc_180075C8F
0x180075c05  mov     rdx, rbx; String2
0x180075c08  lea     rcx, aMstslicensever; "msTSLicenseVersion"
0x180075c0f  call    cs:__imp__wcsicmp
0x180075c16  nop     dword ptr [rax+rax+00h]
0x180075c1b  test    eax, eax
0x180075c1d  jnz     short loc_180075C27
0x180075c1f  lea     ebx, [rax+1]
0x180075c22  mov     r15b, bl
0x180075c25  jmp     short loc_180075C8F
0x180075c27  mov     rdx, rbx; String2
0x180075c2a  lea     rcx, aMstslicensever_0; "msTSLicenseVersion2"
0x180075c31  call    cs:__imp__wcsicmp
0x180075c38  nop     dword ptr [rax+rax+00h]
0x180075c3d  test    eax, eax
0x180075c3f  jnz     short loc_180075C49
0x180075c41  lea     ebx, [rax+1]
0x180075c44  mov     r12b, bl
0x180075c47  jmp     short loc_180075C8F
0x180075c49  mov     rdx, rbx; String2
0x180075c4c  lea     rcx, aMstslicensever_1; "msTSLicenseVersion3"
0x180075c53  call    cs:__imp__wcsicmp
0x180075c5a  nop     dword ptr [rax+rax+00h]
0x180075c5f  test    eax, eax
0x180075c61  jnz     short loc_180075C6B
0x180075c63  lea     ebx, [rax+1]
0x180075c66  mov     r13b, bl
0x180075c69  jmp     short loc_180075C8F
0x180075c6b  mov     rdx, rbx; String2
0x180075c6e  lea     rcx, aMstsmanagingls; "msTSManagingLS"
0x180075c75  call    cs:__imp__wcsicmp
0x180075c7c  nop     dword ptr [rax+rax+00h]
0x180075c81  movzx   edi, dil
0x180075c85  mov     ebx, 1
0x180075c8a  test    eax, eax
0x180075c8c  cmovz   edi, ebx
0x180075c8f  lea     rcx, [rsp+4F0h+pv+8]; pvarg
0x180075c94  call    cs:__imp_VariantClear
0x180075c9b  nop     dword ptr [rax+rax+00h]
0x180075ca0  cmp     byte ptr [rsp+4F0h+var_4C0], r14b
0x180075ca5  jz      short loc_180075CBB
0x180075ca7  test    r15b, r15b
0x180075caa  jz      short loc_180075CBB
0x180075cac  test    dil, dil
0x180075caf  jz      short loc_180075CBB
0x180075cb1  test    r12b, r12b
0x180075cb4  jz      short loc_180075CBB
0x180075cb6  test    r13b, r13b
0x180075cb9  jnz     short loc_180075CCB
0x180075cbb  mov     eax, [rsp+4F0h+rgIndices]
0x180075cbf  add     eax, ebx
0x180075cc1  mov     rbx, qword ptr [rsp+4F0h+pv]
0x180075cc6  jmp     loc_180075BB3
0x180075ccb  mov     r14d, ebx
0x180075cce  lea     rcx, [rbp+3F0h+var_468]; pvarg
0x180075cd2  call    cs:__imp_VariantClear
0x180075cd9  nop     dword ptr [rax+rax+00h]
0x180075cde  lea     rcx, [rsp+4F0h+pvarg+8]; pvarg
0x180075ce3  call    cs:__imp_VariantClear
0x180075cea  nop     dword ptr [rax+rax+00h]
0x180075cef  test    rsi, rsi
0x180075cf2  jz      short loc_180075D03
0x180075cf4  mov     rcx, rsi; bstrString
0x180075cf7  call    cs:__imp_SysFreeString
0x180075cfe  nop     dword ptr [rax+rax+00h]
0x180075d03  mov     rcx, [rsp+4F0h+var_4B0]
0x180075d08  test    rcx, rcx
0x180075d0b  jz      short loc_180075D19
0x180075d0d  mov     rax, [rcx]
0x180075d10  mov     rax, [rax+10h]
0x180075d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d19  mov     rcx, qword ptr [rsp+4F0h+pvarg]
0x180075d1e  test    rcx, rcx
0x180075d21  jz      short loc_180075D2F
0x180075d23  mov     rdx, [rcx]
0x180075d26  mov     rax, [rdx+10h]
0x180075d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075d2f  mov     eax, r14d
0x180075d32  mov     rcx, [rbp+3F0h+var_30]
0x180075d39  xor     rcx, rsp; StackCookie
0x180075d3c  call    __security_check_cookie
0x180075d41  lea     r11, [rsp+4F0h+var_20]
0x180075d49  mov     rbx, [r11+38h]
0x180075d4d  mov     rsi, [r11+40h]
0x180075d51  mov     rdi, [r11+48h]
0x180075d55  mov     rsp, r11
0x180075d58  pop     r15
0x180075d5a  pop     r14
0x180075d5c  pop     r13
0x180075d5e  pop     r12
0x180075d60  pop     rbp
0x180075d61  retn
```
