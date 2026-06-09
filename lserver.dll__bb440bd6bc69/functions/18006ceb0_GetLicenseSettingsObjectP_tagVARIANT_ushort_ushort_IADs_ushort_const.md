# GetLicenseSettingsObjectP(tagVARIANT *,ushort * *,ushort * *,IADs * *,ushort const *)

- ea: `0x18006ceb0`
- end: `0x18006d0c1`
- name: `?GetLicenseSettingsObjectP@@YAJPEAUtagVARIANT@@PEAPEAG1PEAPEAUIADs@@PEBG@Z`
- size: `529`
- prototype: `int(struct tagVARIANT *, unsigned __int16 **, unsigned __int16 **, struct IADs **, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18006d6c4`

## callees

- `0x18000cff0`
- `0x18000d060`
- `0x18006ceb0`
- `0x1800a0fb0`
- `0x1800a5010`

## import_xrefs

- `ACTIVEDS!__imp_ADsOpenObject` at `0x18006cf5b`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x18006d078`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x18006cf5b`
- `ACTIVEDS!__imp_ADsOpenObject` at `0x18006d078`
- `OLEAUT32!__imp_SysAllocString` at `0x18006cf78`
- `OLEAUT32!__imp_SysAllocString` at `0x18006cf78`
- `OLEAUT32!__imp_SysFreeString` at `0x18006cfb2`
- `OLEAUT32!__imp_SysFreeString` at `0x18006cfb2`
- `OLEAUT32!__imp_VariantInit` at `0x18006cee8`
- `OLEAUT32!__imp_VariantInit` at `0x18006cee8`
- `NETAPI32!DsGetSiteNameW` at `0x18006cef9`
- `NETAPI32!DsGetSiteNameW` at `0x18006cef9`
- `KERNEL32!LocalAlloc` at `0x18006d00c`
- `KERNEL32!LocalAlloc` at `0x18006d00c`

## string_xrefs

- `0x18006cf71`: `ConfigurationNamingContext`

## pseudocode

```c
__int64 __fastcall GetLicenseSettingsObjectP(
        struct tagVARIANT *a1,
        LPCWSTR *a2,
        unsigned __int16 **a3,
        struct IADs **a4)
{
  signed int SiteNameW; // eax
  int v9; // ebx
  BSTR v10; // rax
  OLECHAR *v11; // rsi
  LONGLONG llVal; // rdi
  __int64 v13; // rcx
  __int64 v14; // rax
  SIZE_T v15; // rbx
  unsigned __int16 *v16; // rax
  void *ppObject; // [rsp+40h] [rbp-268h] BYREF
  WCHAR szPathName[264]; // [rsp+50h] [rbp-258h] BYREF

  ppObject = 0;
  VariantInit(a1);
  SiteNameW = DsGetSiteNameW(0, a3);
  v9 = SiteNameW;
  if ( SiteNameW )
  {
    if ( SiteNameW > 0 )
      v9 = (unsigned __int16)SiteNameW | 0x80070000;
  }
  else
  {
    StringCchCopyW(szPathName, 0x105u, L"LDAP://RootDSE");
    v9 = ADsOpenObject(szPathName, 0, 0, 0xC1u, &IID_IADs, &ppObject);
    if ( v9 < 0 )
      goto LABEL_15;
    v10 = SysAllocString(L"ConfigurationNamingContext");
    v11 = v10;
    if ( !v10 )
      goto LABEL_6;
    v9 = (*(__int64 (__fastcall **)(void *, BSTR, struct tagVARIANT *))(*(_QWORD *)ppObject + 120LL))(ppObject, v10, a1);
    SysFreeString(v11);
    if ( v9 < 0 )
      goto LABEL_15;
    if ( a1->vt != 8 )
    {
      v9 = -2147024883;
      goto LABEL_15;
    }
    llVal = a1->llVal;
    v13 = -1;
    v14 = -1;
    do
      ++v14;
    while ( (*a3)[v14] );
    do
      ++v13;
    while ( *(_WORD *)(llVal + 2 * v13) );
    v15 = (unsigned int)(2 * (v13 + v14) + 128);
    v16 = (unsigned __int16 *)LocalAlloc(0x40u, v15);
    *a2 = v16;
    if ( !v16 )
    {
LABEL_6:
      v9 = -2147024882;
      goto LABEL_15;
    }
    StringCchPrintfW(
      v16,
      v15 >> 1,
      L"LDAP://CN=%ws,CN=%ws,CN=%ws,%ws",
      L"TS-Enterprise-License-Server",
      *a3,
      L"sites",
      llVal);
    v9 = ADsOpenObject(*a2, 0, 0, 0xC1u, &IID_IADs, (void **)a4);
  }
LABEL_15:
  if ( ppObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppObject + 16LL))(ppObject);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18006ceb0  push    rbx
0x18006ceb2  push    rbp
0x18006ceb3  push    rsi
0x18006ceb4  push    rdi
0x18006ceb5  push    r12
0x18006ceb7  push    r14
0x18006ceb9  push    r15
0x18006cebb  sub     rsp, 270h
0x18006cec2  mov     rax, cs:__security_cookie
0x18006cec9  xor     rax, rsp
0x18006cecc  mov     [rsp+2A8h+var_48], rax
0x18006ced4  xor     r12d, r12d
0x18006ced7  mov     rbp, r9
0x18006ceda  mov     [rsp+2A8h+var_268], r12
0x18006cedf  mov     r14, r8
0x18006cee2  mov     r15, rdx
0x18006cee5  mov     rdi, rcx
0x18006cee8  call    cs:__imp_VariantInit
0x18006ceef  nop     dword ptr [rax+rax+00h]
0x18006cef4  mov     rdx, r14; SiteName
0x18006cef7  xor     ecx, ecx; ComputerName
0x18006cef9  call    cs:__imp_DsGetSiteNameW
0x18006cf00  nop     dword ptr [rax+rax+00h]
0x18006cf05  mov     ebx, eax
0x18006cf07  test    eax, eax
0x18006cf09  jz      short loc_18006CF1F
0x18006cf0b  jle     loc_18006D086
0x18006cf11  movzx   ebx, ax
0x18006cf14  or      ebx, 80070000h
0x18006cf1a  jmp     loc_18006D086
0x18006cf1f  lea     r8, aLdapRootdse; "LDAP://RootDSE"
0x18006cf26  mov     edx, 105h; unsigned __int64
0x18006cf2b  lea     rcx, [rsp+2A8h+szPathName]; unsigned __int16 *
0x18006cf30  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006cf35  lea     r11, [rsp+2A8h+var_268]
0x18006cf3a  mov     r9d, 0C1h; dwReserved
0x18006cf40  lea     rax, IID_IADs
0x18006cf47  mov     [rsp+2A8h+ppObject], r11; ppObject
0x18006cf4c  xor     r8d, r8d; lpszPassword
0x18006cf4f  mov     [rsp+2A8h+riid], rax; riid
0x18006cf54  xor     edx, edx; lpszUserName
0x18006cf56  lea     rcx, [rsp+2A8h+szPathName]; lpszPathName
0x18006cf5b  call    cs:__imp_ADsOpenObject
0x18006cf62  nop     dword ptr [rax+rax+00h]
0x18006cf67  mov     ebx, eax
0x18006cf69  test    eax, eax
0x18006cf6b  js      loc_18006D086
0x18006cf71  lea     rcx, psz; "ConfigurationNamingContext"
0x18006cf78  call    cs:__imp_SysAllocString
0x18006cf7f  nop     dword ptr [rax+rax+00h]
0x18006cf84  mov     rsi, rax
0x18006cf87  test    rax, rax
0x18006cf8a  jnz     short loc_18006CF96
0x18006cf8c  mov     ebx, 8007000Eh
0x18006cf91  jmp     loc_18006D086
0x18006cf96  mov     rcx, [rsp+2A8h+var_268]
0x18006cf9b  mov     r8, rdi
0x18006cf9e  mov     rdx, rsi
0x18006cfa1  mov     rax, [rcx]
0x18006cfa4  mov     rax, [rax+78h]
0x18006cfa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006cfad  mov     rcx, rsi; bstrString
0x18006cfb0  mov     ebx, eax
0x18006cfb2  call    cs:__imp_SysFreeString
0x18006cfb9  nop     dword ptr [rax+rax+00h]
0x18006cfbe  test    ebx, ebx
0x18006cfc0  js      loc_18006D086
0x18006cfc6  cmp     word ptr [rdi], 8
0x18006cfca  jz      short loc_18006CFD6
0x18006cfcc  mov     ebx, 8007000Dh
0x18006cfd1  jmp     loc_18006D086
0x18006cfd6  mov     rdi, [rdi+8]
0x18006cfda  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18006cfde  mov     rdx, [r14]
0x18006cfe1  mov     rax, rcx
0x18006cfe4  inc     rax
0x18006cfe7  cmp     [rdx+rax*2], r12w
0x18006cfec  jnz     short loc_18006CFE4
0x18006cfee  inc     rcx
0x18006cff1  cmp     [rdi+rcx*2], r12w
0x18006cff6  jnz     short loc_18006CFEE
0x18006cff8  add     rax, rcx
0x18006cffb  mov     ecx, 40h ; '@'; uFlags
0x18006d000  lea     rax, ds:80h[rax*2]
0x18006d008  mov     edx, eax; uBytes
0x18006d00a  mov     ebx, eax
0x18006d00c  call    cs:__imp_LocalAlloc
0x18006d013  nop     dword ptr [rax+rax+00h]
0x18006d018  mov     [r15], rax
0x18006d01b  mov     rcx, rax; unsigned __int16 *
0x18006d01e  test    rax, rax
0x18006d021  jz      loc_18006CF8C
0x18006d027  lea     rax, aSites; "sites"
0x18006d02e  mov     [rsp+2A8h+var_278], rdi
0x18006d033  mov     [rsp+2A8h+ppObject], rax
0x18006d038  lea     r9, aTsEnterpriseLi; "TS-Enterprise-License-Server"
0x18006d03f  mov     rax, [r14]
0x18006d042  lea     r8, aLdapCnWsCnWsCn; "LDAP://CN=%ws,CN=%ws,CN=%ws,%ws"
0x18006d049  shr     rbx, 1
0x18006d04c  mov     rdx, rbx; unsigned __int64
0x18006d04f  mov     [rsp+2A8h+riid], rax
0x18006d054  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18006d059  mov     rcx, [r15]; lpszPathName
0x18006d05c  lea     rax, IID_IADs
0x18006d063  mov     [rsp+2A8h+ppObject], rbp; ppObject
0x18006d068  mov     r9d, 0C1h; dwReserved
0x18006d06e  xor     r8d, r8d; lpszPassword
0x18006d071  mov     [rsp+2A8h+riid], rax; riid
0x18006d076  xor     edx, edx; lpszUserName
0x18006d078  call    cs:__imp_ADsOpenObject
0x18006d07f  nop     dword ptr [rax+rax+00h]
0x18006d084  mov     ebx, eax
0x18006d086  mov     rcx, [rsp+2A8h+var_268]
0x18006d08b  test    rcx, rcx
0x18006d08e  jz      short loc_18006D09C
0x18006d090  mov     rax, [rcx]
0x18006d093  mov     rax, [rax+10h]
0x18006d097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d09c  mov     eax, ebx
0x18006d09e  mov     rcx, [rsp+2A8h+var_48]
0x18006d0a6  xor     rcx, rsp; StackCookie
0x18006d0a9  call    __security_check_cookie
0x18006d0ae  add     rsp, 270h
0x18006d0b5  pop     r15
0x18006d0b7  pop     r14
0x18006d0b9  pop     r12
0x18006d0bb  pop     rdi
0x18006d0bc  pop     rsi
0x18006d0bd  pop     rbp
0x18006d0be  pop     rbx
0x18006d0bf  retn
```
