# EapLm::BaseEapLibraryManager::InitializeLegacyMethods(void)

- ea: `0x18002cee8`
- end: `0x18002d039`
- name: `?InitializeLegacyMethods@BaseEapLibraryManager@EapLm@@AEAAXXZ`
- size: `337`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this)`
- caller_count: `2`
- callee_count: `11`
- tags: `registry_config, service_task`

## callers

- `0x18002c728`
- `0x18002cec0`

## callees

- `0x180004ec0`
- `0x18000eb74`
- `0x180011ff0`
- `0x180012258`
- `0x18002a514`
- `0x18002a738`
- `0x18002a7dc`
- `0x18002a808`
- `0x18002ae64`
- `0x18002bc04`
- `0x18002cee8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002cfc2`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18002cfc2`

## string_xrefs

- `0x18002cf58`: `RegOpenKeyExW`
- `0x18002cfe7`: `RegOpenKeyExW`
- `0x18002cf3d`: `System\CurrentControlSet\Services\RasMan\PPP\EAP`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::BaseEapLibraryManager::InitializeLegacyMethods(EapLm::BaseEapLibraryManager *this)
{
  _QWORD *i; // rbx
  const WCHAR *v3; // rax
  __int64 v4; // rax
  char v5; // al
  DWORD v6; // [rsp+20h] [rbp-50h]
  DWORD v7; // [rsp+20h] [rbp-50h]
  HKEY v8; // [rsp+30h] [rbp-40h] BYREF
  int v9; // [rsp+38h] [rbp-38h]
  HKEY v10; // [rsp+40h] [rbp-30h] BYREF
  int v11; // [rsp+48h] [rbp-28h]
  _QWORD *v12; // [rsp+50h] [rbp-20h] BYREF
  _QWORD *v13; // [rsp+58h] [rbp-18h]
  __int64 v14; // [rsp+60h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
  v8 = 0;
  v9 = 9;
  if ( (unsigned int)RegistryKey::Create(
                       (__int64)&v8,
                       HKEY_LOCAL_MACHINE,
                       L"System\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP",
                       9,
                       v6) )
    SystemError::Throw(L"RegOpenKeyExW");
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v12);
  RegistryKey::SubKeys(&v8, &v12);
  for ( i = v12; i != v13; i += 4 )
  {
    v3 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v10 = 0;
    v11 = 1;
    if ( (unsigned int)RegistryKey::Create((__int64)&v10, v8, v3, 1, v7) )
      SystemError::Throw(L"RegOpenKeyExW");
    v4 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v5 = _o__wtol(v4);
    EapLm::BaseEapLibraryManager::AddLegacyEapMethod(this, (const struct RegistryKey *)&v10, v5);
    RegistryKey::Clear(&v10);
  }
  if ( v12 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v12,
      v13);
    std::_Deallocate<16>(v12, (v14 - (_QWORD)v12) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  RegistryKey::Clear(&v8);
}

```

## disassembly

```asm
0x18002cee8  mov     [rsp-8+arg_0], rbx
0x18002ceed  mov     [rsp-8+arg_8], rsi
0x18002cef2  push    rbp
0x18002cef3  mov     rbp, rsp
0x18002cef6  sub     rsp, 70h
0x18002cefa  mov     rsi, rcx
0x18002cefd  lea     rax, WPP_GLOBAL_Control
0x18002cf04  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf0b  cmp     rcx, rax
0x18002cf0e  jz      short loc_18002CF2B
0x18002cf10  test    byte ptr [rcx+1Ch], 4
0x18002cf14  jz      short loc_18002CF2B
0x18002cf16  mov     edx, 2Ah ; '*'
0x18002cf1b  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18002cf22  mov     rcx, [rcx+10h]
0x18002cf26  call    WPP_SF_
0x18002cf2b  mov     [rbp+var_40], 0
0x18002cf33  mov     r9d, 9
0x18002cf39  mov     [rbp+var_38], r9d
0x18002cf3d  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ra"...
0x18002cf44  mov     rdx, 0FFFFFFFF80000002h
0x18002cf4b  lea     rcx, [rbp+var_40]
0x18002cf4f  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x18002cf54  test    eax, eax
0x18002cf56  jz      short loc_18002CF65
0x18002cf58  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x18002cf5f  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18002cf65  lea     rcx, [rbp+var_20]
0x18002cf69  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18002cf6e  nop
0x18002cf6f  lea     rdx, [rbp+var_20]
0x18002cf73  lea     rcx, [rbp+var_40]
0x18002cf77  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002cf7c  mov     rbx, [rbp+var_20]
0x18002cf80  cmp     rbx, [rbp+var_18]
0x18002cf84  jz      short loc_18002CFF4
0x18002cf86  mov     rcx, rbx
0x18002cf89  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002cf8e  mov     [rbp+var_30], 0
0x18002cf96  mov     [rbp+var_28], 1
0x18002cf9d  mov     r9d, 1
0x18002cfa3  mov     r8, rax
0x18002cfa6  mov     rdx, [rbp+var_40]
0x18002cfaa  lea     rcx, [rbp+var_30]
0x18002cfae  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x18002cfb3  test    eax, eax
0x18002cfb5  jnz     short loc_18002CFE7
0x18002cfb7  mov     rcx, rbx
0x18002cfba  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18002cfbf  mov     rcx, rax
0x18002cfc2  call    cs:__imp__o__wtol
0x18002cfc8  mov     r8d, eax; unsigned __int8
0x18002cfcb  lea     rdx, [rbp+var_30]; struct RegistryKey *
0x18002cfcf  mov     rcx, rsi; this
0x18002cfd2  call    ?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z; EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)
0x18002cfd7  nop
0x18002cfd8  lea     rcx, [rbp+var_30]; this
0x18002cfdc  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002cfe1  add     rbx, 20h ; ' '
0x18002cfe5  jmp     short loc_18002CF80
0x18002cfe7  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x18002cfee  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18002cff4  cmp     [rbp+var_20], 0
0x18002cff9  jz      short loc_18002D01E
0x18002cffb  mov     rdx, [rbp+var_18]
0x18002cfff  mov     rcx, [rbp+var_20]
0x18002d003  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18002d008  mov     rdx, [rbp+var_10]
0x18002d00c  sub     rdx, [rbp+var_20]
0x18002d010  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18002d014  mov     rcx, [rbp+var_20]
0x18002d018  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002d01d  nop
0x18002d01e  lea     rcx, [rbp+var_40]; this
0x18002d022  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18002d027  lea     r11, [rsp+70h+var_s0]
0x18002d02c  mov     rbx, [r11+10h]
0x18002d030  mov     rsi, [r11+18h]
0x18002d034  mov     rsp, r11
0x18002d037  pop     rbp
0x18002d038  retn
```
