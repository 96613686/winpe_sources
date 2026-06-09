# InventoryRegistryProvider::ReadFlagDependencies(HKEY__ *,ConfigurationManagement::Flags::DataModel::InventoryFlag &)

- ea: `0x1800a75e4`
- end: `0x1800a7755`
- name: `?ReadFlagDependencies@InventoryRegistryProvider@@AEAAXPEAUHKEY__@@AEAUInventoryFlag@DataModel@Flags@ConfigurationManagement@@@Z`
- size: `369`
- prototype: `void(InventoryRegistryProvider *__hidden this, HKEY, struct ConfigurationManagement::Flags::DataModel::InventoryFlag *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config`

## callers

- `0x1800a7d6c`

## callees

- `0x180003220`
- `0x180015af4`
- `0x180016698`
- `0x180019890`
- `0x18001e820`
- `0x18002abd0`
- `0x18004dcd0`
- `0x1800a75e4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800a771c`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x1800a771c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a763b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a763b`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall InventoryRegistryProvider::ReadFlagDependencies(
        InventoryRegistryProvider *this,
        HKEY a2,
        struct ConfigurationManagement::Flags::DataModel::InventoryFlag *a3)
{
  DWORD v5; // edi
  DWORD i; // edx
  __int64 v7; // rdx
  int v8; // eax
  _DWORD *v9; // rdx
  LSTATUS v10; // eax
  DWORD Type; // [rsp+40h] [rbp-19h] BYREF
  DWORD cbData; // [rsp+44h] [rbp-15h] BYREF
  BYTE Data[4]; // [rsp+48h] [rbp-11h] BYREF
  DWORD cchValueName; // [rsp+4Ch] [rbp-Dh] BYREF
  HKEY hKey; // [rsp+50h] [rbp-9h] BYREF
  int v16; // [rsp+58h] [rbp-1h] BYREF
  _BYTE v17[32]; // [rsp+60h] [rbp+7h] BYREF
  WCHAR ValueName[12]; // [rsp+80h] [rbp+27h] BYREF

  hKey = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hKey,
    0,
    a3);
  if ( !RegOpenKeyExW(a2, L"Dependencies", 0, 0x20019u, &hKey) )
  {
    v5 = 0;
    *(_DWORD *)Data = 0;
    Type = 0;
    for ( i = 0; ; i = v5 )
    {
      cchValueName = 11;
      cbData = 4;
      v10 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
      if ( v10 == 259 )
        break;
      if ( !v10 && Type == 4 )
      {
        std::wstring::wstring(v17);
        v8 = std::stoul(v17, v7, 10);
        v16 = v8;
        v9 = (_DWORD *)*((_QWORD *)a3 + 12);
        if ( v9 == *((_DWORD **)a3 + 13) )
        {
          std::vector<unsigned int>::_Emplace_reallocate<unsigned int>((char *)a3 + 88, v9, &v16);
        }
        else
        {
          *v9 = v8;
          *((_QWORD *)a3 + 12) += 4LL;
        }
        std::wstring::_Tidy_deallocate(v17, v9);
      }
      ++v5;
      *(_DWORD *)Data = 0;
      Type = 0;
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800a75e4  mov     [rsp-8+arg_0], rbx
0x1800a75e9  push    rbp
0x1800a75ea  push    rsi
0x1800a75eb  push    rdi
0x1800a75ec  lea     rbp, [rsp-47h]
0x1800a75f1  sub     rsp, 0A0h
0x1800a75f8  mov     rax, cs:__security_cookie
0x1800a75ff  xor     rax, rsp
0x1800a7602  mov     [rbp+57h+var_18], rax
0x1800a7606  mov     rsi, r8
0x1800a7609  mov     rbx, rdx
0x1800a760c  mov     [rbp+57h+hKey], 0
0x1800a7614  xor     edx, edx
0x1800a7616  lea     rcx, [rbp+57h+hKey]
0x1800a761a  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800a761f  lea     rax, [rbp+57h+hKey]
0x1800a7623  mov     [rsp+0B0h+phkResult], rax; phkResult
0x1800a7628  mov     r9d, 20019h; samDesired
0x1800a762e  xor     r8d, r8d; ulOptions
0x1800a7631  lea     rdx, String2; "Dependencies"
0x1800a7638  mov     rcx, rbx; hKey
0x1800a763b  call    cs:__imp_RegOpenKeyExW
0x1800a7641  test    eax, eax
0x1800a7643  jnz     loc_1800A772D
0x1800a7649  xor     edi, edi
0x1800a764b  mov     dword ptr [rbp+57h+Data], edi
0x1800a764e  mov     [rbp+57h+Type], edi
0x1800a7651  lea     rax, [rbp+57h+cbData]
0x1800a7655  mov     [rsp+0B0h+lpcbData], rax
0x1800a765a  lea     rax, [rbp+57h+Data]
0x1800a765e  mov     [rsp+0B0h+lpData], rax
0x1800a7663  lea     rax, [rbp+57h+Type]
0x1800a7667  mov     [rsp+0B0h+lpType], rax
0x1800a766c  mov     [rsp+0B0h+phkResult], rdi
0x1800a7671  xor     edx, edx
0x1800a7673  jmp     loc_1800A7702
0x1800a7678  test    eax, eax
0x1800a767a  jnz     short loc_1800A76CC
0x1800a767c  cmp     [rbp+57h+Type], 4
0x1800a7680  jnz     short loc_1800A76CC
0x1800a7682  lea     rdx, [rbp+57h+ValueName]
0x1800a7686  lea     rcx, [rbp+57h+var_50]
0x1800a768a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a768f  nop
0x1800a7690  mov     r8d, 0Ah
0x1800a7696  lea     rcx, [rbp+57h+var_50]
0x1800a769a  call    ?stoul@std@@YAKAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@PEA_KH@Z; std::stoul(std::wstring const &,unsigned __int64 *,int)
0x1800a769f  mov     [rbp+57h+var_58], eax
0x1800a76a2  mov     rdx, [rsi+60h]
0x1800a76a6  cmp     rdx, [rsi+68h]
0x1800a76aa  jz      short loc_1800A76B5
0x1800a76ac  mov     [rdx], eax
0x1800a76ae  add     qword ptr [rsi+60h], 4
0x1800a76b3  jmp     short loc_1800A76C3
0x1800a76b5  lea     r8, [rbp+57h+var_58]
0x1800a76b9  lea     rcx, [rsi+58h]
0x1800a76bd  call    ??$_Emplace_reallocate@I@?$vector@IV?$allocator@I@std@@@std@@AEAAPEAIQEAI$$QEAI@Z; std::vector<uint>::_Emplace_reallocate<uint>(uint * const,uint &&)
0x1800a76c2  nop
0x1800a76c3  lea     rcx, [rbp+57h+var_50]
0x1800a76c7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a76cc  inc     edi
0x1800a76ce  mov     dword ptr [rbp+57h+Data], 0
0x1800a76d5  mov     [rbp+57h+Type], 0
0x1800a76dc  lea     rax, [rbp+57h+cbData]
0x1800a76e0  mov     [rsp+0B0h+lpcbData], rax; lpcbData
0x1800a76e5  lea     rax, [rbp+57h+Data]
0x1800a76e9  mov     [rsp+0B0h+lpData], rax; lpData
0x1800a76ee  lea     rax, [rbp+57h+Type]
0x1800a76f2  mov     [rsp+0B0h+lpType], rax; lpType
0x1800a76f7  mov     [rsp+0B0h+phkResult], 0; lpReserved
0x1800a7700  mov     edx, edi; dwIndex
0x1800a7702  mov     [rbp+57h+cchValueName], 0Bh
0x1800a7709  mov     [rbp+57h+cbData], 4
0x1800a7710  lea     r9, [rbp+57h+cchValueName]; lpcchValueName
0x1800a7714  lea     r8, [rbp+57h+ValueName]; lpValueName
0x1800a7718  mov     rcx, [rbp+57h+hKey]; hKey
0x1800a771c  call    cs:__imp_RegEnumValueW
0x1800a7722  cmp     eax, 103h
0x1800a7727  jnz     loc_1800A7678
0x1800a772d  lea     rcx, [rbp+57h+hKey]
0x1800a7731  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a7736  mov     rcx, [rbp+57h+var_18]
0x1800a773a  xor     rcx, rsp; StackCookie
0x1800a773d  call    __security_check_cookie
0x1800a7742  mov     rbx, [rsp+0B0h+arg_0]
0x1800a774a  add     rsp, 0A0h
0x1800a7751  pop     rdi
0x1800a7752  pop     rsi
0x1800a7753  pop     rbp
0x1800a7754  retn
```
