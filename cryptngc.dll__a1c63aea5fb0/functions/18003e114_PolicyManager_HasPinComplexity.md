# PolicyManager::HasPinComplexity

- ea: `0x18003e114`
- end: `0x18003e2cc`
- name: `PolicyManager::HasPinComplexity`
- size: `440`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e878`

## callees

- `0x1800046e0`
- `0x18000edb0`
- `0x1800158e0`
- `0x180016538`
- `0x18001a36c`
- `0x180038e9c`
- `0x18003e114`
- `0x180046ce0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003e26b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18003e26b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e1cd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003e1cd`

## string_xrefs

- `0x18003e17e`: `PINComplexity`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall PolicyManager::HasPinComplexity(__int64 a1, bool *a2)
{
  const WCHAR *v4; // rdx
  LSTATUS v5; // eax
  signed int v6; // ebx
  unsigned int v7; // ebx
  LSTATUS v8; // eax
  DWORD cValues; // [rsp+60h] [rbp+7h] BYREF
  LSTATUS v10; // [rsp+64h] [rbp+Bh] BYREF
  void **v11; // [rsp+68h] [rbp+Fh] BYREF
  HKEY hKey; // [rsp+70h] [rbp+17h] BYREF
  LPCWSTR lpSubKey[4]; // [rsp+78h] [rbp+1Fh] BYREF

  if ( !a2 )
    return 87;
  *a2 = 0;
  std::wstring::wstring(lpSubKey, L"SOFTWARE\\Policies\\Microsoft\\PassportForWork");
  std::wstring::_Append<unsigned short>(lpSubKey);
  std::wstring::_Append<unsigned short>(lpSubKey);
  v11 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  hKey = 0;
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v11);
  v4 = (const WCHAR *)lpSubKey;
  if ( lpSubKey[3] > (LPCWSTR)7 )
    v4 = lpSubKey[0];
  v5 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v4, 0, 0x20019u, &hKey);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 != 2 )
    {
      if ( (unsigned int)dword_18006E000 > 2 )
      {
        v10 = v5;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_18006E000,
          (unsigned int)&word_1800621D6,
          0,
          0,
          (__int64)&v10);
      }
      if ( v6 > 0 )
        v6 = (unsigned __int16)v6 | 0x80070000;
      v7 = HResultToSecurityStatus(v6);
      goto LABEL_18;
    }
    *a2 = 0;
  }
  else
  {
    cValues = 0;
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, 0, 0, 0, &cValues, 0, 0, 0, 0);
    v7 = v8;
    if ( v8 )
    {
      if ( v8 > 0 )
        v7 = (unsigned __int16)v8 | 0x80070000;
      goto LABEL_18;
    }
    *a2 = cValues != 0;
  }
  v7 = 0;
LABEL_18:
  v11 = &Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(&v11);
  std::wstring::~wstring(lpSubKey);
  return v7;
}

```

## disassembly

```asm
0x18003e114  mov     [rsp-8+arg_0], rbx
0x18003e119  mov     [rsp-8+arg_10], rsi
0x18003e11e  push    rbp
0x18003e11f  push    rdi
0x18003e120  push    r14
0x18003e122  lea     rbp, [rsp-47h]
0x18003e127  sub     rsp, 0A0h
0x18003e12e  mov     rax, cs:__security_cookie
0x18003e135  xor     rax, rsp
0x18003e138  mov     [rbp+57h+var_18], rax
0x18003e13c  mov     rdi, rdx
0x18003e13f  xor     esi, esi
0x18003e141  test    rdx, rdx
0x18003e144  jnz     short loc_18003E14E
0x18003e146  lea     eax, [rdx+57h]
0x18003e149  jmp     loc_18003E2A8
0x18003e14e  mov     [rdx], sil
0x18003e151  lea     rdx, aSoftwarePolici_0; "SOFTWARE\\Policies\\Microsoft\\Passport"...
0x18003e158  lea     rcx, [rbp+57h+lpSubKey]
0x18003e15c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18003e161  nop
0x18003e162  mov     r8d, 1
0x18003e168  lea     rdx, asc_180050E74; "\\"
0x18003e16f  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18003e173  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e178  mov     r8d, 0Dh
0x18003e17e  lea     rdx, aPincomplexity; "PINComplexity"
0x18003e185  lea     rcx, [rbp+57h+lpSubKey]; Src
0x18003e189  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003e18e  lea     r14, ??_7?$HandleT@URegKeyHandleTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<RegKeyHandleTraits>::`vftable'
0x18003e195  mov     [rbp+57h+var_48], r14
0x18003e199  mov     [rbp+57h+hKey], rsi
0x18003e19d  lea     rcx, [rbp+57h+var_48]
0x18003e1a1  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x18003e1a6  lea     rdx, [rbp+57h+lpSubKey]
0x18003e1aa  cmp     [rbp+57h+var_20], 7
0x18003e1af  cmova   rdx, [rbp+57h+lpSubKey]; lpSubKey
0x18003e1b4  lea     rax, [rbp+57h+hKey]
0x18003e1b8  mov     [rsp+0B0h+phkResult], rax; phkResult
0x18003e1bd  mov     r9d, 20019h; samDesired
0x18003e1c3  xor     r8d, r8d; ulOptions
0x18003e1c6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003e1cd  call    cs:__imp_RegOpenKeyExW
0x18003e1d3  mov     ebx, eax
0x18003e1d5  test    eax, eax
0x18003e1d7  jz      short loc_18003E230
0x18003e1d9  cmp     eax, 2
0x18003e1dc  jnz     short loc_18003E1E8
0x18003e1de  mov     [rdi], sil
0x18003e1e1  mov     ebx, esi
0x18003e1e3  jmp     loc_18003E28F
0x18003e1e8  mov     eax, cs:dword_18006E000
0x18003e1ee  cmp     eax, 2
0x18003e1f1  jbe     short loc_18003E218
0x18003e1f3  mov     [rbp+57h+var_4C], ebx
0x18003e1f6  lea     rax, [rbp+57h+var_4C]
0x18003e1fa  mov     [rsp+0B0h+phkResult], rax
0x18003e1ff  xor     r9d, r9d
0x18003e202  xor     r8d, r8d
0x18003e205  lea     rdx, word_1800621D6
0x18003e20c  lea     rcx, dword_18006E000
0x18003e213  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18003e218  test    ebx, ebx
0x18003e21a  jle     short loc_18003E225
0x18003e21c  movzx   ebx, bx
0x18003e21f  or      ebx, 80070000h
0x18003e225  mov     ecx, ebx; int
0x18003e227  call    ?HResultToSecurityStatus@@YAJJ@Z; HResultToSecurityStatus(long)
0x18003e22c  mov     ebx, eax
0x18003e22e  jmp     short loc_18003E28F
0x18003e230  mov     [rbp+57h+cValues], esi
0x18003e233  mov     [rsp+0B0h+lpftLastWriteTime], rsi; lpftLastWriteTime
0x18003e238  mov     [rsp+0B0h+lpcbSecurityDescriptor], rsi; lpcbSecurityDescriptor
0x18003e23d  mov     [rsp+0B0h+lpcbMaxValueLen], rsi; lpcbMaxValueLen
0x18003e242  mov     [rsp+0B0h+lpcbMaxValueNameLen], rsi; lpcbMaxValueNameLen
0x18003e247  lea     rax, [rbp+57h+cValues]
0x18003e24b  mov     [rsp+0B0h+lpcValues], rax; lpcValues
0x18003e250  mov     [rsp+0B0h+lpcbMaxClassLen], rsi; lpcbMaxClassLen
0x18003e255  mov     [rsp+0B0h+lpcbMaxSubKeyLen], rsi; lpcbMaxSubKeyLen
0x18003e25a  mov     [rsp+0B0h+phkResult], rsi; lpcSubKeys
0x18003e25f  xor     r9d, r9d; lpReserved
0x18003e262  xor     r8d, r8d; lpcchClass
0x18003e265  xor     edx, edx; lpClass
0x18003e267  mov     rcx, [rbp+57h+hKey]; hKey
0x18003e26b  call    cs:__imp_RegQueryInfoKeyW
0x18003e271  mov     ebx, eax
0x18003e273  test    eax, eax
0x18003e275  jnz     short loc_18003E284
0x18003e277  cmp     [rbp+57h+cValues], esi
0x18003e27a  setnz   al
0x18003e27d  mov     [rdi], al
0x18003e27f  jmp     loc_18003E1E1
0x18003e284  jle     short loc_18003E28F
0x18003e286  movzx   ebx, ax
0x18003e289  or      ebx, 80070000h
0x18003e28f  mov     [rbp+57h+var_48], r14
0x18003e293  lea     rcx, [rbp+57h+var_48]
0x18003e297  call    ?Close@?$HandleT@URpcBindingHandleTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<RpcBindingHandleTraits>::Close(void)
0x18003e29c  nop
0x18003e29d  lea     rcx, [rbp+57h+lpSubKey]
0x18003e2a1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18003e2a6  mov     eax, ebx
0x18003e2a8  mov     rcx, [rbp+57h+var_18]
0x18003e2ac  xor     rcx, rsp; StackCookie
0x18003e2af  call    __security_check_cookie
0x18003e2b4  lea     r11, [rsp+0B0h+var_10]
0x18003e2bc  mov     rbx, [r11+20h]
0x18003e2c0  mov     rsi, [r11+30h]
0x18003e2c4  mov     rsp, r11
0x18003e2c7  pop     r14
0x18003e2c9  pop     rdi
0x18003e2ca  pop     rbp
0x18003e2cb  retn
```
