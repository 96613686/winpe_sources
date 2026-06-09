# LoadTuneXmlLookupMap(std::map<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>> *,ushort const *)

- ea: `0x180055e80`
- end: `0x18005603c`
- name: `?LoadTuneXmlLookupMap@@YAJPEAV?$map@VCComBSTR@ATL@@V12@Uless_bstr_insensitive@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@PEBG@Z`
- size: `444`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180055374`
- `0x180055448`
- `0x1800555c8`
- `0x180055ae4`

## callees

- `0x180004640`
- `0x1800054bc`
- `0x180054d90`
- `0x18005501c`
- `0x1800550d0`
- `0x180055e80`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180055f7c`
- `OLEAUT32!__imp_SysAllocString` at `0x180055f91`
- `OLEAUT32!__imp_SysAllocString` at `0x180055f7c`
- `OLEAUT32!__imp_SysAllocString` at `0x180055f91`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fde`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fd4`
- `OLEAUT32!__imp_SysFreeString` at `0x180055fde`
- `ADVAPI32!RegEnumValueW` at `0x180055f6e`
- `ADVAPI32!RegEnumValueW` at `0x180055f6e`
- `ADVAPI32!RegOpenKeyExW` at `0x180055ee1`
- `ADVAPI32!RegOpenKeyExW` at `0x180055ee1`
- `ADVAPI32!RegCloseKey` at `0x180055ffe`
- `ADVAPI32!RegCloseKey` at `0x180055ffe`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
LSTATUS __fastcall LoadTuneXmlLookupMap(__int64 a1, const WCHAR *a2)
{
  LSTATUS result; // eax
  bool v4; // cc
  int v5; // esi
  DWORD v6; // r15d
  DWORD v7; // edx
  LSTATUS v8; // eax
  OLECHAR *v9; // rdi
  OLECHAR *v10; // rbx
  __int64 v11; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchValueName; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  OLECHAR *v16; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR *v17; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v18[16]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v19[24]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR ValueName[264]; // [rsp+90h] [rbp-70h] BYREF
  OLECHAR Data[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  if ( !a1 )
    return -2147467261;
  hKey = 0;
  result = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, 0x20019u, &hKey);
  v4 = result <= 0;
  if ( !result )
  {
    v5 = -2147418113;
    v6 = 0;
    Type = 0;
    do
    {
      while ( 1 )
      {
        memset_0(ValueName, 0, 0x208u);
        memset_0(Data, 0, 0x208u);
        cchValueName = 260;
        cbData = 520;
        v7 = v6++;
        v8 = RegEnumValueW(hKey, v7, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
        if ( v8 )
          break;
        v9 = SysAllocString(ValueName);
        v17 = v9;
        v10 = SysAllocString(Data);
        v16 = v10;
        v11 = std::pair<ATL::CComBSTR,ATL::CComBSTR>::pair<ATL::CComBSTR,ATL::CComBSTR>(v18, &v17, &v16);
        std::map<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>>::insert<std::pair<ATL::CComBSTR,ATL::CComBSTR>,0>(
          a1,
          v19,
          v11);
        std::pair<ATL::CComBSTR const,ATL::CComBSTR>::~pair<ATL::CComBSTR const,ATL::CComBSTR>(v18);
        v5 = 0;
        SysFreeString(v10);
        SysFreeString(v9);
      }
    }
    while ( v8 != 259 );
    if ( !hKey )
      return v5;
    result = RegCloseKey(hKey);
    v4 = result <= 0;
    if ( !result )
      return v5;
  }
  if ( !v4 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180055e80  mov     [rsp-8+arg_10], rbx
0x180055e85  push    rbp
0x180055e86  push    rsi
0x180055e87  push    rdi
0x180055e88  push    r14
0x180055e8a  push    r15
0x180055e8c  lea     rbp, [rsp-3C0h]
0x180055e94  sub     rsp, 4C0h
0x180055e9b  mov     rax, cs:__security_cookie
0x180055ea2  xor     rax, rsp
0x180055ea5  mov     [rbp+3E0h+var_30], rax
0x180055eac  mov     r14, rcx
0x180055eaf  test    rcx, rcx
0x180055eb2  jnz     short loc_180055EBE
0x180055eb4  mov     eax, 80004003h
0x180055eb9  jmp     loc_180056016
0x180055ebe  mov     [rsp+4E0h+hKey], 0
0x180055ec7  lea     rax, [rsp+4E0h+hKey]
0x180055ecc  mov     [rsp+4E0h+phkResult], rax; phkResult
0x180055ed1  mov     r9d, 20019h; samDesired
0x180055ed7  xor     r8d, r8d; ulOptions
0x180055eda  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180055ee1  call    cs:__imp_RegOpenKeyExW
0x180055ee7  test    eax, eax
0x180055ee9  jnz     loc_180056008
0x180055eef  mov     esi, 8000FFFFh
0x180055ef4  xor     r15d, r15d
0x180055ef7  mov     [rsp+4E0h+Type], r15d
0x180055efc  xor     edx, edx; Val
0x180055efe  mov     r8d, 208h; Size
0x180055f04  lea     rcx, [rbp+3E0h+ValueName]; void *
0x180055f08  call    memset_0
0x180055f0d  xor     edx, edx; Val
0x180055f0f  mov     r8d, 208h; Size
0x180055f15  lea     rcx, [rbp+3E0h+Data]; void *
0x180055f1c  call    memset_0
0x180055f21  mov     [rsp+4E0h+cchValueName], 104h
0x180055f29  mov     [rsp+4E0h+cbData], 208h
0x180055f31  mov     edx, r15d; dwIndex
0x180055f34  inc     r15d
0x180055f37  lea     rax, [rsp+4E0h+cbData]
0x180055f3c  mov     [rsp+4E0h+lpcbData], rax; lpcbData
0x180055f41  lea     rax, [rbp+3E0h+Data]
0x180055f48  mov     [rsp+4E0h+lpData], rax; lpData
0x180055f4d  lea     rax, [rsp+4E0h+Type]
0x180055f52  mov     [rsp+4E0h+lpType], rax; lpType
0x180055f57  mov     [rsp+4E0h+phkResult], 0; lpReserved
0x180055f60  lea     r9, [rsp+4E0h+cchValueName]; lpcchValueName
0x180055f65  lea     r8, [rbp+3E0h+ValueName]; lpValueName
0x180055f69  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180055f6e  call    cs:__imp_RegEnumValueW
0x180055f74  test    eax, eax
0x180055f76  jnz     short loc_180055FE9
0x180055f78  lea     rcx, [rbp+3E0h+ValueName]; psz
0x180055f7c  call    cs:__imp_SysAllocString
0x180055f82  mov     rdi, rax
0x180055f85  mov     [rsp+4E0h+var_480], rax
0x180055f8a  lea     rcx, [rbp+3E0h+Data]; psz
0x180055f91  call    cs:__imp_SysAllocString
0x180055f97  mov     rbx, rax
0x180055f9a  mov     [rsp+4E0h+var_488], rax
0x180055f9f  lea     r8, [rsp+4E0h+var_488]
0x180055fa4  lea     rdx, [rsp+4E0h+var_480]
0x180055fa9  lea     rcx, [rsp+4E0h+var_478]
0x180055fae  call    ??$?0AEAVCComBSTR@ATL@@AEAV01@$0A@@?$pair@VCComBSTR@ATL@@V12@@std@@QEAA@AEAVCComBSTR@ATL@@0@Z; std::pair<ATL::CComBSTR,ATL::CComBSTR>::pair<ATL::CComBSTR,ATL::CComBSTR>(ATL::CComBSTR &,ATL::CComBSTR &)
0x180055fb3  nop
0x180055fb4  mov     r8, rax
0x180055fb7  lea     rdx, [rsp+4E0h+var_468]
0x180055fbc  mov     rcx, r14
0x180055fbf  call    ??$insert@U?$pair@VCComBSTR@ATL@@V12@@std@@$0A@@?$map@VCComBSTR@ATL@@V12@Uless_bstr_insensitive@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@V12@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@VCComBSTR@ATL@@V12@@1@@Z; std::map<ATL::CComBSTR,ATL::CComBSTR,less_bstr_insensitive,std::allocator<std::pair<ATL::CComBSTR const,ATL::CComBSTR>>>::insert<std::pair<ATL::CComBSTR,ATL::CComBSTR>,0>(std::pair<ATL::CComBSTR,ATL::CComBSTR> &&)
0x180055fc4  nop
0x180055fc5  lea     rcx, [rsp+4E0h+var_478]
0x180055fca  call    ??1?$pair@$$CBVCComBSTR@ATL@@V12@@std@@QEAA@XZ; std::pair<ATL::CComBSTR const,ATL::CComBSTR>::~pair<ATL::CComBSTR const,ATL::CComBSTR>(void)
0x180055fcf  xor     esi, esi
0x180055fd1  mov     rcx, rbx; bstrString
0x180055fd4  call    cs:__imp_SysFreeString
0x180055fda  nop
0x180055fdb  mov     rcx, rdi; bstrString
0x180055fde  call    cs:__imp_SysFreeString
0x180055fe4  jmp     loc_180055EFC
0x180055fe9  cmp     eax, 103h
0x180055fee  jnz     loc_180055EFC
0x180055ff4  mov     rcx, [rsp+4E0h+hKey]; hKey
0x180055ff9  test    rcx, rcx
0x180055ffc  jz      short loc_180056014
0x180055ffe  call    cs:__imp_RegCloseKey
0x180056004  test    eax, eax
0x180056006  jz      short loc_180056014
0x180056008  jle     short loc_180056016
0x18005600a  movzx   eax, ax
0x18005600d  or      eax, 80070000h
0x180056012  jmp     short loc_180056016
0x180056014  mov     eax, esi
0x180056016  mov     rcx, [rbp+3E0h+var_30]
0x18005601d  xor     rcx, rsp; StackCookie
0x180056020  call    __security_check_cookie
0x180056025  mov     rbx, [rsp+4E0h+arg_10]
0x18005602d  add     rsp, 4C0h
0x180056034  pop     r15
0x180056036  pop     r14
0x180056038  pop     rdi
0x180056039  pop     rsi
0x18005603a  pop     rbp
0x18005603b  retn
```
