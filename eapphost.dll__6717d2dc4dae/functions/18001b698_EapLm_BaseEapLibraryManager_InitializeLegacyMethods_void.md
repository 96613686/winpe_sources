# EapLm::BaseEapLibraryManager::InitializeLegacyMethods(void)

- ea: `0x18001b698`
- end: `0x18001b7c6`
- name: `?InitializeLegacyMethods@BaseEapLibraryManager@EapLm@@AEAAXXZ`
- size: `302`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18001ac7c`
- `0x18001b670`

## callees

- `0x180009dc4`
- `0x1800118e8`
- `0x18001755c`
- `0x1800197d8`
- `0x180019cf0`
- `0x18001a2f0`
- `0x18001b698`
- `0x18002f158`
- `0x180030080`
- `0x1800300fc`
- `0x180030128`
- `0x180030784`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001b74f`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001b74f`

## string_xrefs

- `0x18001b6e1`: `System\CurrentControlSet\Services\RasMan\PPP\EAP`
- `0x18001b774`: `RegOpenKeyExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::BaseEapLibraryManager::InitializeLegacyMethods(EapLm::BaseEapLibraryManager *this, HKEY a2)
{
  __int64 v3; // r8
  __int64 v4; // r9
  _QWORD *i; // rbx
  const WCHAR *v6; // rax
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // r9
  DWORD v10; // [rsp+20h] [rbp-50h]
  HKEY v11; // [rsp+30h] [rbp-40h] BYREF
  int v12; // [rsp+38h] [rbp-38h]
  HKEY v13[2]; // [rsp+40h] [rbp-30h] BYREF
  _QWORD *v14; // [rsp+50h] [rbp-20h] BYREF
  _QWORD *v15; // [rsp+58h] [rbp-18h]
  __int64 v16; // [rsp+60h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
  }
  RegistryKey::RegistryKey((RegistryKey *)v13, a2, L"System\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP", 9);
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v14);
  RegistryKey::SubKeys(v13, &v14);
  for ( i = v14; i != v15; i += 4 )
  {
    v6 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v11 = 0;
    v12 = 1;
    if ( (unsigned int)RegistryKey::Create((__int64)&v11, v13[0], v6, 1, v10) )
      SystemError::Throw(L"RegOpenKeyExW");
    v7 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr();
    v8 = _o__wtol(v7);
    EapLm::BaseEapLibraryManager::AddLegacyEapMethod(this, (const struct RegistryKey *)&v11, v8, v9);
    RegistryKey::Clear(&v11);
  }
  if ( v14 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v14,
      v15,
      v3,
      v4);
    std::_Deallocate<16>(v14, (v16 - (_QWORD)v14) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  RegistryKey::Clear(v13);
}

```

## disassembly

```asm
0x18001b698  mov     [rsp-8+arg_0], rbx
0x18001b69d  mov     [rsp-8+arg_8], rsi
0x18001b6a2  push    rbp
0x18001b6a3  mov     rbp, rsp
0x18001b6a6  sub     rsp, 70h
0x18001b6aa  mov     rsi, rcx
0x18001b6ad  lea     rax, WPP_GLOBAL_Control
0x18001b6b4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b6bb  cmp     rcx, rax
0x18001b6be  jz      short loc_18001B6DB
0x18001b6c0  test    byte ptr [rcx+1Ch], 4
0x18001b6c4  jz      short loc_18001B6DB
0x18001b6c6  mov     edx, 2Ah ; '*'
0x18001b6cb  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001b6d2  mov     rcx, [rcx+10h]
0x18001b6d6  call    WPP_SF_
0x18001b6db  mov     r9d, 9; unsigned int
0x18001b6e1  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ra"...
0x18001b6e8  lea     rcx, [rbp+var_30]; this
0x18001b6ec  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::RegistryKey(HKEY__ *,wchar_t const *,ulong,bool)
0x18001b6f1  nop
0x18001b6f2  lea     rcx, [rbp+var_20]
0x18001b6f6  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001b6fb  nop
0x18001b6fc  lea     rdx, [rbp+var_20]
0x18001b700  lea     rcx, [rbp+var_30]
0x18001b704  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001b709  mov     rbx, [rbp+var_20]
0x18001b70d  cmp     rbx, [rbp+var_18]
0x18001b711  jz      short loc_18001B781
0x18001b713  mov     rcx, rbx
0x18001b716  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b71b  mov     [rbp+var_40], 0
0x18001b723  mov     [rbp+var_38], 1
0x18001b72a  mov     r9d, 1
0x18001b730  mov     r8, rax
0x18001b733  mov     rdx, [rbp+var_30]
0x18001b737  lea     rcx, [rbp+var_40]
0x18001b73b  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x18001b740  test    eax, eax
0x18001b742  jnz     short loc_18001B774
0x18001b744  mov     rcx, rbx
0x18001b747  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001b74c  mov     rcx, rax
0x18001b74f  call    cs:__imp__o__wtol
0x18001b755  mov     r8d, eax; unsigned __int8
0x18001b758  lea     rdx, [rbp+var_40]; struct RegistryKey *
0x18001b75c  mov     rcx, rsi; this
0x18001b75f  call    ?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z; EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)
0x18001b764  nop
0x18001b765  lea     rcx, [rbp+var_40]; this
0x18001b769  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001b76e  add     rbx, 20h ; ' '
0x18001b772  jmp     short loc_18001B70D
0x18001b774  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x18001b77b  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18001b781  cmp     [rbp+var_20], 0
0x18001b786  jz      short loc_18001B7AB
0x18001b788  mov     rdx, [rbp+var_18]
0x18001b78c  mov     rcx, [rbp+var_20]
0x18001b790  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001b795  mov     rdx, [rbp+var_10]
0x18001b799  sub     rdx, [rbp+var_20]
0x18001b79d  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001b7a1  mov     rcx, [rbp+var_20]
0x18001b7a5  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001b7aa  nop
0x18001b7ab  lea     rcx, [rbp+var_30]; this
0x18001b7af  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001b7b4  lea     r11, [rsp+70h+var_s0]
0x18001b7b9  mov     rbx, [r11+10h]
0x18001b7bd  mov     rsi, [r11+18h]
0x18001b7c1  mov     rsp, r11
0x18001b7c4  pop     rbp
0x18001b7c5  retn
```
