# EapLm::BaseEapLibraryManager::InitializeLegacyMethods(void)

- ea: `0x18001c0a8`
- end: `0x18001c1dd`
- name: `?InitializeLegacyMethods@BaseEapLibraryManager@EapLm@@AEAAXXZ`
- size: `309`
- prototype: `void __fastcall(EapLm::BaseEapLibraryManager *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, service_task`

## callers

- `0x18001b67c`
- `0x18001c080`

## callees

- `0x18000a21c`
- `0x18001204c`
- `0x180017e48`
- `0x18001a1c0`
- `0x18001a6d4`
- `0x18001acdc`
- `0x18001c0a8`
- `0x180030288`
- `0x180031294`
- `0x180031314`
- `0x180031348`
- `0x180031930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001c15f`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x18001c15f`

## string_xrefs

- `0x18001c0f1`: `System\CurrentControlSet\Services\RasMan\PPP\EAP`
- `0x18001c18a`: `RegOpenKeyExW`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall EapLm::BaseEapLibraryManager::InitializeLegacyMethods(EapLm::BaseEapLibraryManager *this, HKEY a2)
{
  __int64 i; // rbx
  const WCHAR *v4; // rax
  __int64 v5; // rax
  unsigned __int8 v6; // al
  bool v7; // [rsp+20h] [rbp-50h]
  DWORD v8; // [rsp+20h] [rbp-50h]
  __int64 v9; // [rsp+30h] [rbp-40h] BYREF
  int v10; // [rsp+38h] [rbp-38h]
  HKEY v11[2]; // [rsp+40h] [rbp-30h] BYREF
  __int64 v12; // [rsp+50h] [rbp-20h] BYREF
  __int64 v13; // [rsp+58h] [rbp-18h]
  __int64 v14; // [rsp+60h] [rbp-10h]

  if ( WPP_GLOBAL_Control != (EapHost::Peer::Host *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids);
  }
  RegistryKey::RegistryKey((RegistryKey *)v11, a2, L"System\\CurrentControlSet\\Services\\RasMan\\PPP\\EAP", 9u, v7);
  std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(&v12);
  RegistryKey::SubKeys(v11, &v12);
  for ( i = v12; i != v13; i += 32 )
  {
    v4 = (const WCHAR *)std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
    v9 = 0;
    v10 = 1;
    if ( (unsigned int)RegistryKey::Create((RegistryKey *)&v9, v11[0], v4, 1, v8) )
      SystemError::Throw(L"RegOpenKeyExW");
    v5 = std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(i);
    v6 = _o__wtol(v5);
    EapLm::BaseEapLibraryManager::AddLegacyEapMethod(this, (const struct RegistryKey *)&v9, v6);
    RegistryKey::Clear((RegistryKey *)&v9);
  }
  if ( v12 )
  {
    std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(
      v12,
      v13);
    std::_Deallocate<16>(v12, (v14 - v12) & 0xFFFFFFFFFFFFFFE0uLL);
  }
  RegistryKey::Clear((RegistryKey *)v11);
}

```

## disassembly

```asm
0x18001c0a8  mov     [rsp-8+arg_0], rbx
0x18001c0ad  mov     [rsp-8+arg_8], rsi
0x18001c0b2  push    rbp
0x18001c0b3  mov     rbp, rsp
0x18001c0b6  sub     rsp, 70h
0x18001c0ba  mov     rsi, rcx
0x18001c0bd  lea     rax, WPP_GLOBAL_Control
0x18001c0c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c0cb  cmp     rcx, rax
0x18001c0ce  jz      short loc_18001C0EB
0x18001c0d0  test    byte ptr [rcx+1Ch], 4
0x18001c0d4  jz      short loc_18001C0EB
0x18001c0d6  mov     edx, 2Ah ; '*'
0x18001c0db  lea     r8, WPP_2ef3415c67dc300703cdd93ef8c57003_Traceguids
0x18001c0e2  mov     rcx, [rcx+10h]
0x18001c0e6  call    WPP_SF_
0x18001c0eb  mov     r9d, 9; unsigned int
0x18001c0f1  lea     r8, aSystemCurrentc_0; "System\\CurrentControlSet\\Services\\Ra"...
0x18001c0f8  lea     rcx, [rbp+var_30]; this
0x18001c0fc  call    ??0RegistryKey@@QEAA@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::RegistryKey(HKEY__ *,wchar_t const *,ulong,bool)
0x18001c101  nop
0x18001c102  lea     rcx, [rbp+var_20]
0x18001c106  call    ??0?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@QEAA@XZ; std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>(void)
0x18001c10b  nop
0x18001c10c  lea     rdx, [rbp+var_20]
0x18001c110  lea     rcx, [rbp+var_30]
0x18001c114  call    ?SubKeys@RegistryKey@@QEBAXAEAV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@2@@std@@@Z; RegistryKey::SubKeys(std::vector<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001c119  mov     rbx, [rbp+var_20]
0x18001c11d  cmp     rbx, [rbp+var_18]
0x18001c121  jz      short loc_18001C197
0x18001c123  mov     rcx, rbx
0x18001c126  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c12b  mov     [rbp+var_40], 0
0x18001c133  mov     [rbp+var_38], 1
0x18001c13a  mov     r9d, 1
0x18001c140  mov     r8, rax
0x18001c143  mov     rdx, [rbp+var_30]
0x18001c147  lea     rcx, [rbp+var_40]
0x18001c14b  call    ?Create@RegistryKey@@QEAA?AW4ResultType@ResultValue@1@PEAUHKEY__@@PEB_WK_N@Z; RegistryKey::Create(HKEY__ *,wchar_t const *,ulong,bool)
0x18001c150  test    eax, eax
0x18001c152  jnz     short loc_18001C18A
0x18001c154  mov     rcx, rbx
0x18001c157  call    ?_Myptr@?$_String_val@U?$_Simple_types@_W@std@@@std@@QEBAPEB_WXZ; std::_String_val<std::_Simple_types<wchar_t>>::_Myptr(void)
0x18001c15c  mov     rcx, rax
0x18001c15f  call    cs:__imp__o__wtol
0x18001c166  nop     dword ptr [rax+rax+00h]
0x18001c16b  mov     r8d, eax; unsigned __int8
0x18001c16e  lea     rdx, [rbp+var_40]; struct RegistryKey *
0x18001c172  mov     rcx, rsi; this
0x18001c175  call    ?AddLegacyEapMethod@BaseEapLibraryManager@EapLm@@IEAAXAEBVRegistryKey@@E@Z; EapLm::BaseEapLibraryManager::AddLegacyEapMethod(RegistryKey const &,uchar)
0x18001c17a  nop
0x18001c17b  lea     rcx, [rbp+var_40]; this
0x18001c17f  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001c184  add     rbx, 20h ; ' '
0x18001c188  jmp     short loc_18001C11D
0x18001c18a  lea     rcx, aRegopenkeyexw; "RegOpenKeyExW"
0x18001c191  call    ?Throw@SystemError@@SAXPEB_W@Z; SystemError::Throw(wchar_t const *)
0x18001c197  cmp     [rbp+var_20], 0
0x18001c19c  jz      short loc_18001C1C1
0x18001c19e  mov     rdx, [rbp+var_18]
0x18001c1a2  mov     rcx, [rbp+var_20]
0x18001c1a6  call    ??$_Destroy_range@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@std@@@std@@YAXPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@0@QEAV10@AEAV?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$StdAllocator@_W@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>>>(std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> *,std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>> * const,std::allocator<std::basic_string<wchar_t,std::char_traits<wchar_t>,StdAllocator<wchar_t>>> &)
0x18001c1ab  mov     rdx, [rbp+var_10]
0x18001c1af  sub     rdx, [rbp+var_20]
0x18001c1b3  and     rdx, 0FFFFFFFFFFFFFFE0h
0x18001c1b7  mov     rcx, [rbp+var_20]
0x18001c1bb  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001c1c0  nop
0x18001c1c1  lea     rcx, [rbp+var_30]; this
0x18001c1c5  call    ?Clear@RegistryKey@@QEAAXXZ; RegistryKey::Clear(void)
0x18001c1ca  lea     r11, [rsp+70h+var_s0]
0x18001c1cf  mov     rbx, [r11+10h]
0x18001c1d3  mov     rsi, [r11+18h]
0x18001c1d7  mov     rsp, r11
0x18001c1da  pop     rbp
0x18001c1db  retn
```
