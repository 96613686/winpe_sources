# CAppIdExtImpl::ResetSkipPackages(void)

- ea: `0x14003a748`
- end: `0x14003a9f8`
- name: `?ResetSkipPackages@CAppIdExtImpl@@IEAAXXZ`
- size: `688`
- prototype: `void __fastcall(CAppIdExtImpl *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ccfc`

## callees

- `0x140001020`
- `0x140004a0c`
- `0x140004a98`
- `0x140033ab0`
- `0x14003a748`

## import_xrefs

- `ADVAPI32!RegDeleteValueW` at `0x14003a961`
- `ADVAPI32!RegDeleteValueW` at `0x14003a961`
- `ADVAPI32!RegCloseKey` at `0x14003a96f`
- `ADVAPI32!RegCloseKey` at `0x14003a993`
- `ADVAPI32!RegCloseKey` at `0x14003a96f`
- `ADVAPI32!RegCloseKey` at `0x14003a993`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14003a846`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14003a8b4`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14003a846`
- `ADVAPI32!RegQueryInfoKeyW` at `0x14003a8b4`
- `ADVAPI32!RegEnumKeyExW` at `0x14003a909`
- `ADVAPI32!RegEnumKeyExW` at `0x14003a909`
- `OLEAUT32!__imp_SysAllocString` at `0x14003a916`
- `OLEAUT32!__imp_SysAllocString` at `0x14003a916`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14003a8c3`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x14003a8c3`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a8d7`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a921`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a92a`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a978`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a99e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a9cd`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a9d5`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a8d7`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a921`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a92a`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a978`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a99e`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a9cd`
- `OLEAUT32!__imp_SysFreeString` at `0x14003a9d5`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14003a790`
- `OLEAUT32!__imp_SysStringByteLen` at `0x14003a790`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14003a79f`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x14003a79f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CAppIdExtImpl::ResetSkipPackages(CAppIdExtImpl *this)
{
  CDevEnvAppId *v1; // rbx
  OLECHAR *v2; // rcx
  OLECHAR *v3; // rax
  UINT v4; // eax
  int v5; // eax
  int v6; // eax
  HKEY v7; // rbx
  LSTATUS v8; // eax
  signed int v9; // ecx
  DWORD i; // r14d
  unsigned __int16 *v11; // rsi
  OLECHAR *v12; // rdi
  int v13; // eax
  HKEY v14; // rdi
  BSTR bstrString; // [rsp+68h] [rbp+17h] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+70h] [rbp+1Fh] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp+23h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+27h] BYREF
  HKEY v19; // [rsp+80h] [rbp+2Fh] BYREF

  v1 = CDevEnvAppId::ms_pTheAppId;
  v2 = (OLECHAR *)*((_QWORD *)CDevEnvAppId::ms_pTheAppId + 25);
  if ( v2 )
  {
    v4 = SysStringByteLen(v2);
    v3 = SysAllocStringByteLen(*((LPCSTR *)v1 + 25), v4);
  }
  else
  {
    v3 = 0;
  }
  bstrString = v3;
  if ( *((_QWORD *)v1 + 25) && !v3 )
    ATL::AtlThrowImpl(-2147024882);
  hKey = 0;
  cSubKeys = 0;
  v5 = ATL::CComBSTR::Append((ATL::CComBSTR *)&bstrString, L"\\Packages", 9);
  if ( v5 < 0 )
  {
    _mm_lfence();
    ATL::AtlThrowImpl(v5);
  }
  v6 = CVsRegKeyW::Open(&hKey, HKEY_CURRENT_USER, bstrString, 9u);
  v7 = hKey;
  if ( v6 >= 0 && hKey )
  {
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v9 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 <= 0 )
      v9 = v8;
    if ( v9 >= 0 )
    {
      for ( i = 0; i < cSubKeys; ++i )
      {
        v11 = 0;
        v19 = 0;
        v12 = 0;
        if ( !RegQueryInfoKeyW(v7, 0, 0, 0, 0, &cbMaxSubKeyLen, (LPDWORD)&hKey, 0, 0, 0, 0, 0) )
        {
          v12 = SysAllocStringLen(0, cbMaxSubKeyLen);
          if ( !v12 )
          {
            SysFreeString(0);
            SysFreeString(0);
            goto LABEL_23;
          }
          SysFreeString(0);
          ++cbMaxSubKeyLen;
          LODWORD(hKey) = 0;
          if ( !RegEnumKeyExW(v7, i, v12, &cbMaxSubKeyLen, 0, 0, (LPDWORD)&hKey, 0) )
            v11 = SysAllocString(v12);
        }
        SysFreeString(0);
        SysFreeString(v12);
        if ( v11 )
        {
          v13 = CVsRegKeyW::Open(&v19, v7, v11, 2u);
          v14 = v19;
          if ( v13 < 0 )
            goto LABEL_21;
          if ( v19 )
          {
            RegDeleteValueW(v19, L"SkipLoading");
LABEL_21:
            if ( v14 )
              RegCloseKey(v14);
          }
        }
LABEL_23:
        SysFreeString(v11);
      }
    }
  }
  if ( v7 )
    RegCloseKey(v7);
  SysFreeString(bstrString);
}

```

## disassembly

```asm
0x14003a748  mov     rax, rsp
0x14003a74b  mov     [rax+8], rbx
0x14003a74f  mov     [rax+10h], rsi
0x14003a753  mov     [rax+18h], rdi
0x14003a757  push    rbp
0x14003a758  push    r14
0x14003a75a  push    r15
0x14003a75c  lea     rbp, [rax-5Fh]
0x14003a760  sub     rsp, 90h
0x14003a767  mov     rax, cs:__security_cookie
0x14003a76e  xor     rax, rsp
0x14003a771  mov     [rbp+57h+var_20], rax
0x14003a775  mov     rbx, cs:?ms_pTheAppId@CDevEnvAppId@@1PEAV?$CComFreeThreadedObject@VCDevEnvAppId@@@@EA; CComFreeThreadedObject<CDevEnvAppId> * CDevEnvAppId::ms_pTheAppId
0x14003a77c  mov     rcx, [rbx+0C8h]; bstr
0x14003a783  xor     r15d, r15d
0x14003a786  test    rcx, rcx
0x14003a789  jnz     short loc_14003A790
0x14003a78b  mov     eax, r15d
0x14003a78e  jmp     short loc_14003A7A5
0x14003a790  call    cs:__imp_SysStringByteLen
0x14003a796  mov     edx, eax; len
0x14003a798  mov     rcx, [rbx+0C8h]; psz
0x14003a79f  call    cs:__imp_SysAllocStringByteLen
0x14003a7a5  mov     [rbp+57h+bstrString], rax
0x14003a7a9  cmp     [rbx+0C8h], r15
0x14003a7b0  jz      short loc_14003A7BB
0x14003a7b2  test    rax, rax
0x14003a7b5  jz      loc_14003A9ED
0x14003a7bb  mov     [rbp+57h+hKey], r15
0x14003a7bf  mov     [rbp+57h+cSubKeys], r15d
0x14003a7c3  mov     ebx, 9
0x14003a7c8  mov     r8d, ebx; int
0x14003a7cb  lea     rdx, aPackages_0; "\\Packages"
0x14003a7d2  lea     rcx, [rbp+57h+bstrString]; this
0x14003a7d6  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x14003a7db  test    eax, eax
0x14003a7dd  js      loc_14003A9DD
0x14003a7e3  mov     r9d, ebx; unsigned int
0x14003a7e6  mov     r8, [rbp+57h+bstrString]; unsigned __int16 *
0x14003a7ea  mov     rdx, 0FFFFFFFF80000001h; HKEY
0x14003a7f1  lea     rcx, [rbp+57h+hKey]; this
0x14003a7f5  call    ?Open@CVsRegKeyW@@QEAAJPEAUHKEY__@@PEBGK@Z; CVsRegKeyW::Open(HKEY__ *,ushort const *,ulong)
0x14003a7fa  mov     rbx, [rbp+57h+hKey]
0x14003a7fe  test    eax, eax
0x14003a800  js      loc_14003A98B
0x14003a806  test    rbx, rbx
0x14003a809  jz      loc_14003A98B
0x14003a80f  mov     [rsp+0A0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14003a814  mov     [rsp+0A0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14003a819  mov     [rsp+0A0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14003a81e  mov     [rsp+0A0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x14003a823  mov     [rsp+0A0h+lpcValues], r15; lpcValues
0x14003a828  mov     [rsp+0A0h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x14003a82d  mov     [rsp+0A0h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x14003a832  lea     rax, [rbp+57h+cSubKeys]
0x14003a836  mov     [rsp+0A0h+lpcSubKeys], rax; lpcSubKeys
0x14003a83b  xor     r9d, r9d; lpReserved
0x14003a83e  xor     r8d, r8d; lpcchClass
0x14003a841  xor     edx, edx; lpClass
0x14003a843  mov     rcx, rbx; hKey
0x14003a846  call    cs:__imp_RegQueryInfoKeyW
0x14003a84c  movzx   ecx, ax
0x14003a84f  or      ecx, 80070000h
0x14003a855  test    eax, eax
0x14003a857  cmovle  ecx, eax
0x14003a85a  test    ecx, ecx
0x14003a85c  js      loc_14003A98B
0x14003a862  mov     r14d, r15d
0x14003a865  cmp     [rbp+57h+cSubKeys], r15d
0x14003a869  jbe     loc_14003A98B
0x14003a86f  mov     rsi, r15
0x14003a872  mov     [rbp+57h+var_28], r15
0x14003a876  mov     rdi, r15
0x14003a879  mov     [rsp+0A0h+lpftLastWriteTime], r15; lpftLastWriteTime
0x14003a87e  mov     [rsp+0A0h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x14003a883  mov     [rsp+0A0h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x14003a888  mov     [rsp+0A0h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x14003a88d  mov     [rsp+0A0h+lpcValues], r15; lpcValues
0x14003a892  lea     rax, [rbp+57h+hKey]
0x14003a896  mov     [rsp+0A0h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x14003a89b  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x14003a89f  mov     [rsp+0A0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x14003a8a4  mov     [rsp+0A0h+lpcSubKeys], r15; lpcSubKeys
0x14003a8a9  xor     r9d, r9d; lpReserved
0x14003a8ac  xor     r8d, r8d; lpcchClass
0x14003a8af  xor     edx, edx; lpClass
0x14003a8b1  mov     rcx, rbx; hKey
0x14003a8b4  call    cs:__imp_RegQueryInfoKeyW
0x14003a8ba  test    eax, eax
0x14003a8bc  jnz     short loc_14003A91F
0x14003a8be  mov     edx, [rbp+57h+cbMaxSubKeyLen]; ui
0x14003a8c1  xor     ecx, ecx; strIn
0x14003a8c3  call    cs:__imp_SysAllocStringLen
0x14003a8c9  mov     rdi, rax
0x14003a8cc  xor     ecx, ecx; bstrString
0x14003a8ce  test    rax, rax
0x14003a8d1  jz      loc_14003A9CD
0x14003a8d7  call    cs:__imp_SysFreeString
0x14003a8dd  inc     [rbp+57h+cbMaxSubKeyLen]
0x14003a8e0  mov     dword ptr [rbp+57h+hKey], r15d
0x14003a8e4  mov     [rsp+0A0h+lpcValues], r15; lpftLastWriteTime
0x14003a8e9  lea     rax, [rbp+57h+hKey]
0x14003a8ed  mov     [rsp+0A0h+lpcbMaxClassLen], rax; lpcchClass
0x14003a8f2  mov     [rsp+0A0h+lpcbMaxSubKeyLen], r15; lpClass
0x14003a8f7  mov     [rsp+0A0h+lpcSubKeys], r15; lpReserved
0x14003a8fc  lea     r9, [rbp+57h+cbMaxSubKeyLen]; lpcchName
0x14003a900  mov     r8, rdi; lpName
0x14003a903  mov     edx, r14d; dwIndex
0x14003a906  mov     rcx, rbx; hKey
0x14003a909  call    cs:__imp_RegEnumKeyExW
0x14003a90f  test    eax, eax
0x14003a911  jnz     short loc_14003A91F
0x14003a913  mov     rcx, rdi; psz
0x14003a916  call    cs:__imp_SysAllocString
0x14003a91c  mov     rsi, rax
0x14003a91f  xor     ecx, ecx; bstrString
0x14003a921  call    cs:__imp_SysFreeString
0x14003a927  mov     rcx, rdi; bstrString
0x14003a92a  call    cs:__imp_SysFreeString
0x14003a930  test    rsi, rsi
0x14003a933  jz      short loc_14003A975
0x14003a935  mov     r9d, 2; unsigned int
0x14003a93b  mov     r8, rsi; unsigned __int16 *
0x14003a93e  mov     rdx, rbx; HKEY
0x14003a941  lea     rcx, [rbp+57h+var_28]; this
0x14003a945  call    ?Open@CVsRegKeyW@@QEAAJPEAUHKEY__@@PEBGK@Z; CVsRegKeyW::Open(HKEY__ *,ushort const *,ulong)
0x14003a94a  mov     rdi, [rbp+57h+var_28]
0x14003a94e  test    eax, eax
0x14003a950  js      short loc_14003A967
0x14003a952  test    rdi, rdi
0x14003a955  jz      short loc_14003A975
0x14003a957  lea     rdx, aSkiploading; "SkipLoading"
0x14003a95e  mov     rcx, rdi; hKey
0x14003a961  call    cs:__imp_RegDeleteValueW
0x14003a967  test    rdi, rdi
0x14003a96a  jz      short loc_14003A975
0x14003a96c  mov     rcx, rdi; hKey
0x14003a96f  call    cs:__imp_RegCloseKey
0x14003a975  mov     rcx, rsi; bstrString
0x14003a978  call    cs:__imp_SysFreeString
0x14003a97e  inc     r14d
0x14003a981  cmp     r14d, [rbp+57h+cSubKeys]
0x14003a985  jb      loc_14003A86F
0x14003a98b  test    rbx, rbx
0x14003a98e  jz      short loc_14003A99A
0x14003a990  mov     rcx, rbx; hKey
0x14003a993  call    cs:__imp_RegCloseKey
0x14003a999  nop
0x14003a99a  mov     rcx, [rbp+57h+bstrString]; bstrString
0x14003a99e  call    cs:__imp_SysFreeString
0x14003a9a4  mov     rcx, [rbp+57h+var_20]
0x14003a9a8  xor     rcx, rsp; StackCookie
0x14003a9ab  call    __security_check_cookie
0x14003a9b0  lea     r11, [rsp+0A0h+var_10]
0x14003a9b8  mov     rbx, [r11+20h]
0x14003a9bc  mov     rsi, [r11+28h]
0x14003a9c0  mov     rdi, [r11+30h]
0x14003a9c4  mov     rsp, r11
0x14003a9c7  pop     r15
0x14003a9c9  pop     r14
0x14003a9cb  pop     rbp
0x14003a9cc  retn
0x14003a9cd  call    cs:__imp_SysFreeString
0x14003a9d3  xor     ecx, ecx; bstrString
0x14003a9d5  call    cs:__imp_SysFreeString
0x14003a9db  jmp     short loc_14003A975
0x14003a9dd  lfence
0x14003a9e0  mov     ecx, eax; int
0x14003a9e2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x14003a9e8  jmp     short loc_14003A9EC
0x14003a9ec  nop
0x14003a9ed  mov     ecx, 8007000Eh; int
0x14003a9f2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
