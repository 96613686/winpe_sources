# ConfigurationManagement::Flags::Storage::InventoryWriter::DeleteInventoryRegistryEntry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,uint,ConfigurationManagement::Flags::IInventoryRegistryProvider::InventoryRegistryKind)

- ea: `0x1800a4424`
- end: `0x1800a4501`
- name: `?DeleteInventoryRegistryEntry@InventoryWriter@Storage@Flags@ConfigurationManagement@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@IW4InventoryRegistryKind@IInventoryRegistryProvider@34@@Z`
- size: `221`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, installer_update`

## callers

- `0x18008a59c`

## callees

- `0x180003220`
- `0x18000949c`
- `0x180019704`
- `0x180019890`
- `0x1800a3ccc`
- `0x1800a4424`
- `0x1800a4980`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a44be`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800a44be`

## string_xrefs

- `0x1800a4465`: `onecore\base\flighting\featuremanagement\libs\configurationmanagement\inventorywriter.cpp`

## pseudocode

```c
__int64 __fastcall ConfigurationManagement::Flags::Storage::InventoryWriter::DeleteInventoryRegistryEntry(
        __int64 a1,
        int a2)
{
  __int64 v4; // r8
  unsigned int v6; // ebx
  const WCHAR *v7; // rax
  LSTATUS v8; // eax
  __int64 v9; // rdx
  int v10[8]; // [rsp+20h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter>::GetImpl'::`2'::impl) )
    return 2147500037LL;
  if ( a2 )
  {
    LOBYTE(v4) = -56;
    anonymous_namespace_::BuildInventoryRegistryPath(
      v10,
      a1,
      v4,
      __ROR4__(_byteswap_ulong(a2 ^ 0x74161A4E) ^ 0x8FB23D4F, 255) ^ 0x833EA8FF);
    v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
    v8 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, v7);
    v6 = v8;
    if ( v8 == 2 )
    {
      v6 = 1;
    }
    else if ( v8 > 0 )
    {
      v6 = (unsigned __int16)v8 | 0x80070000;
    }
    std::wstring::_Tidy_deallocate(v10, v9);
  }
  else
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\base\\flighting\\featuremanagement\\libs\\configurationmanagement\\inventorywriter.cpp",
      (const char *)0x80070057LL,
      v10[0]);
  }
  return v6;
}

```

## disassembly

```asm
0x1800a4424  mov     [rsp+arg_10], rbx
0x1800a4429  push    rdi
0x1800a442a  sub     rsp, 50h
0x1800a442e  mov     rax, cs:__security_cookie
0x1800a4435  xor     rax, rsp
0x1800a4438  mov     [rsp+58h+var_18], rax
0x1800a443d  mov     ebx, edx
0x1800a443f  mov     rdi, rcx
0x1800a4442  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter> `wil::Feature<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter>::GetImpl(void)'::`2'::impl
0x1800a4449  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_FCON_WinCs_StorageWriter>::__private_IsEnabled(void)
0x1800a444e  test    al, al
0x1800a4450  jnz     short loc_1800A445C
0x1800a4452  mov     eax, 80004005h
0x1800a4457  jmp     loc_1800A44E9
0x1800a445c  test    ebx, ebx
0x1800a445e  jnz     short loc_1800A4480
0x1800a4460  mov     rcx, [rsp+58h]; this
0x1800a4465  lea     r8, aOnecoreBaseFli_57; "onecore\\base\\flighting\\featuremanage"...
0x1800a446c  mov     ebx, 80070057h
0x1800a4471  mov     edx, 0DFh; void *
0x1800a4476  mov     r9d, ebx; char *
0x1800a4479  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a447e  jmp     short loc_1800A44E7
0x1800a4480  xor     ebx, 74161A4Eh
0x1800a4486  lea     rcx, [rsp+58h+var_38]
0x1800a448b  bswap   ebx
0x1800a448d  xor     ebx, 8FB23D4Fh
0x1800a4493  mov     r8b, 0C8h
0x1800a4496  ror     ebx, 0FFh
0x1800a4499  mov     rdx, rdi
0x1800a449c  xor     ebx, 833EA8FFh
0x1800a44a2  mov     r9d, ebx
0x1800a44a5  call    _anonymous_namespace___BuildInventoryRegistryPath
0x1800a44aa  lea     rcx, [rsp+58h+var_38]
0x1800a44af  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a44b4  mov     rdx, rax; lpSubKey
0x1800a44b7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a44be  call    cs:__imp_RegDeleteTreeW
0x1800a44c4  mov     ebx, eax
0x1800a44c6  cmp     eax, 2
0x1800a44c9  jnz     short loc_1800A44D0
0x1800a44cb  lea     ebx, [rax-1]
0x1800a44ce  jmp     short loc_1800A44DD
0x1800a44d0  test    eax, eax
0x1800a44d2  jle     short loc_1800A44DD
0x1800a44d4  movzx   ebx, ax
0x1800a44d7  or      ebx, 80070000h
0x1800a44dd  lea     rcx, [rsp+58h+var_38]
0x1800a44e2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a44e7  mov     eax, ebx
0x1800a44e9  mov     rcx, [rsp+58h+var_18]
0x1800a44ee  xor     rcx, rsp; StackCookie
0x1800a44f1  call    __security_check_cookie
0x1800a44f6  mov     rbx, [rsp+58h+arg_10]
0x1800a44fb  add     rsp, 50h
0x1800a44ff  pop     rdi
0x1800a4500  retn
```
