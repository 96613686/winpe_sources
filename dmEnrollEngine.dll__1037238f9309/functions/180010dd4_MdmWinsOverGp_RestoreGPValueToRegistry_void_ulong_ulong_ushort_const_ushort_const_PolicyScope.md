# MdmWinsOverGp_RestoreGPValueToRegistry(void *,ulong,ulong,ushort const *,ushort const *,PolicyScope)

- ea: `0x180010dd4`
- end: `0x180010f7a`
- name: `?MdmWinsOverGp_RestoreGPValueToRegistry@@YAJPEAXKKPEBG1W4PolicyScope@@@Z`
- size: `422`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x18000fdc0`

## callees

- `0x1800071c0`
- `0x180010dd4`
- `0x180010f8c`
- `0x1800118f8`
- `0x180011f94`
- `0x180021818`
- `0x18002e1a0`
- `0x180075bf4`
- `0x180075d3c`
- `0x1800761b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010ee6`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010ee6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010f0d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010f0d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f4b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f3a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180010f4b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MdmWinsOverGp_RestoreGPValueToRegistry(
        const BYTE *a1,
        DWORD a2,
        DWORD a3,
        __int64 a4,
        const WCHAR *lpValueName,
        int a6)
{
  LPCWSTR *v9; // rax
  LPCWSTR *v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rax
  const WCHAR *v14; // rdx
  unsigned int v15; // eax
  __int64 v16; // rdx
  unsigned int v17; // ebx
  unsigned int dwOptions; // [rsp+20h] [rbp-99h]
  HKEY hKey; // [rsp+50h] [rbp-69h] BYREF
  _BYTE v21[8]; // [rsp+58h] [rbp-61h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+60h] [rbp-59h] BYREF
  unsigned __int64 v23; // [rsp+78h] [rbp-41h]
  _BYTE v24[32]; // [rsp+80h] [rbp-39h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  std::wstring::wstring(lpSubKey, a4);
  v9 = *(LPCWSTR **)std::wstring::end(lpSubKey, v21);
  v10 = lpSubKey;
  if ( v23 > 7 )
    v10 = (LPCWSTR *)lpSubKey[0];
  while ( v10 != v9 )
  {
    if ( *(_WORD *)v10 == 47 )
      *(_WORD *)v10 = 92;
    v10 = (LPCWSTR *)((char *)v10 + 2);
  }
  v11 = -2147483646;
  if ( a6 == 1 )
  {
    v11 = -2147483645;
    v12 = std::operator+<unsigned short>(v25);
    v13 = std::operator+<unsigned short>(v24, v12, lpSubKey);
    std::wstring::operator=(lpSubKey, v13);
    std::wstring::_Tidy_deallocate(v24);
    std::wstring::_Tidy_deallocate(v25);
  }
  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0);
  v14 = (const WCHAR *)lpSubKey;
  if ( v23 > 7 )
    v14 = lpSubKey[0];
  v15 = RegCreateKeyExW((HKEY)v11, v14, 0, 0, 0, 0x20006u, 0, &hKey, 0);
  if ( v15 )
  {
    v16 = 201;
    goto LABEL_16;
  }
  v15 = RegSetValueExW(hKey, lpValueName, 0, a3, a1, a2);
  if ( v15 )
  {
    v16 = 209;
LABEL_16:
    v17 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)v16,
            (unsigned int)"onecoreuap\\admin\\dm\\dmcfgutils\\mdmwinsovergpengine\\mdmwinsovergp.cpp",
            (const char *)v15,
            dwOptions);
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_21;
  }
  if ( hKey )
    RegCloseKey(hKey);
  v17 = 0;
LABEL_21:
  std::wstring::_Tidy_deallocate(lpSubKey);
  return v17;
}

```

## disassembly

```asm
0x180010dd4  push    rbp
0x180010dd6  push    rbx
0x180010dd7  push    rsi
0x180010dd8  push    rdi
0x180010dd9  push    r14
0x180010ddb  push    r15
0x180010ddd  lea     rbp, [rsp-1Fh]
0x180010de2  sub     rsp, 0D8h
0x180010de9  mov     rax, cs:__security_cookie
0x180010df0  xor     rax, rsp
0x180010df3  mov     [rbp+47h+var_40], rax
0x180010df7  mov     r14d, r8d
0x180010dfa  mov     esi, edx
0x180010dfc  mov     rdi, rcx
0x180010dff  mov     r15, [rbp+47h+lpValueName]
0x180010e03  mov     rdx, r9
0x180010e06  lea     rcx, [rbp+47h+lpSubKey]
0x180010e0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180010e0f  nop
0x180010e10  lea     rdx, [rbp+47h+var_A8]
0x180010e14  lea     rcx, [rbp+47h+lpSubKey]
0x180010e18  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x180010e1d  mov     rax, [rax]
0x180010e20  lea     rcx, [rbp+47h+lpSubKey]
0x180010e24  cmp     [rbp+47h+var_88], 7
0x180010e29  cmova   rcx, [rbp+47h+lpSubKey]
0x180010e2e  jmp     short loc_180010E3F
0x180010e30  cmp     word ptr [rcx], 2Fh ; '/'
0x180010e34  jnz     short loc_180010E3B
0x180010e36  mov     word ptr [rcx], 5Ch ; '\'
0x180010e3b  add     rcx, 2
0x180010e3f  cmp     rcx, rax
0x180010e42  jnz     short loc_180010E30
0x180010e44  mov     rbx, 0FFFFFFFF80000002h
0x180010e4b  cmp     [rbp+47h+arg_28], 1
0x180010e4f  jnz     short loc_180010E91
0x180010e51  mov     rbx, 0FFFFFFFF80000003h
0x180010e58  lea     rcx, [rbp+47h+var_60]
0x180010e5c  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180010e61  nop
0x180010e62  lea     r8, [rbp+47h+lpSubKey]
0x180010e66  mov     rdx, rax
0x180010e69  lea     rcx, [rbp+47h+var_80]
0x180010e6d  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180010e72  mov     rdx, rax
0x180010e75  lea     rcx, [rbp+47h+lpSubKey]
0x180010e79  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180010e7e  lea     rcx, [rbp+47h+var_80]
0x180010e82  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010e87  nop
0x180010e88  lea     rcx, [rbp+47h+var_60]
0x180010e8c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010e91  mov     [rbp+47h+hKey], 0
0x180010e99  xor     edx, edx
0x180010e9b  lea     rcx, [rbp+47h+hKey]
0x180010e9f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180010ea4  lea     rdx, [rbp+47h+lpSubKey]
0x180010ea8  cmp     [rbp+47h+var_88], 7
0x180010ead  cmova   rdx, [rbp+47h+lpSubKey]; lpSubKey
0x180010eb2  mov     [rsp+100h+lpdwDisposition], 0; lpdwDisposition
0x180010ebb  lea     rax, [rbp+47h+hKey]
0x180010ebf  mov     [rsp+100h+phkResult], rax; phkResult
0x180010ec4  mov     [rsp+100h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010ecd  mov     [rsp+100h+samDesired], 20006h; samDesired
0x180010ed5  mov     [rsp+100h+dwOptions], 0; dwOptions
0x180010edd  xor     r9d, r9d; lpClass
0x180010ee0  xor     r8d, r8d; Reserved
0x180010ee3  mov     rcx, rbx; hKey
0x180010ee6  call    cs:__imp_RegCreateKeyExW
0x180010eec  test    eax, eax
0x180010eee  jz      short loc_180010EF7
0x180010ef0  mov     edx, 0C9h
0x180010ef5  jmp     short loc_180010F1C
0x180010ef7  mov     [rsp+100h+samDesired], esi; cbData
0x180010efb  mov     qword ptr [rsp+100h+dwOptions], rdi; unsigned int
0x180010f00  mov     r9d, r14d; dwType
0x180010f03  xor     r8d, r8d; Reserved
0x180010f06  mov     rdx, r15; lpValueName
0x180010f09  mov     rcx, [rbp+47h+hKey]; hKey
0x180010f0d  call    cs:__imp_RegSetValueExW
0x180010f13  test    eax, eax
0x180010f15  jz      short loc_180010F42
0x180010f17  mov     edx, 0D1h; void *
0x180010f1c  lea     r8, aOnecoreuapAdmi_20; "onecoreuap\\admin\\dm\\dmcfgutils\\mdmw"...
0x180010f23  mov     r9d, eax; char *
0x180010f26  mov     rcx, [rbp+4Fh]; this
0x180010f2a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180010f2f  mov     ebx, eax
0x180010f31  mov     rcx, [rbp+47h+hKey]; hKey
0x180010f35  test    rcx, rcx
0x180010f38  jz      short loc_180010F53
0x180010f3a  call    cs:__imp_RegCloseKey
0x180010f40  jmp     short loc_180010F53
0x180010f42  mov     rcx, [rbp+47h+hKey]; hKey
0x180010f46  test    rcx, rcx
0x180010f49  jz      short loc_180010F51
0x180010f4b  call    cs:__imp_RegCloseKey
0x180010f51  xor     ebx, ebx
0x180010f53  lea     rcx, [rbp+47h+lpSubKey]
0x180010f57  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180010f5c  mov     eax, ebx
0x180010f5e  mov     rcx, [rbp+47h+var_40]
0x180010f62  xor     rcx, rsp; StackCookie
0x180010f65  call    __security_check_cookie
0x180010f6a  add     rsp, 0D8h
0x180010f71  pop     r15
0x180010f73  pop     r14
0x180010f75  pop     rdi
0x180010f76  pop     rsi
0x180010f77  pop     rbx
0x180010f78  pop     rbp
0x180010f79  retn
```
