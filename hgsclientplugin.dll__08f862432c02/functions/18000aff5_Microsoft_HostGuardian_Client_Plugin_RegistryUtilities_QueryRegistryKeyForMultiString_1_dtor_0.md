# _Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString_::_1_::dtor$0

- ea: `0x18000aff5`
- end: `0x18000b01b`
- name: `_Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString_::_1_::dtor$0`
- size: `38`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800062ec`
- `0x18000aff5`

## pseudocode

```c
void __fastcall Microsoft::HostGuardian::Client::Plugin::RegistryUtilities::QueryRegistryKeyForMultiString_::_1_::dtor_0(
        __int64 a1,
        __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 80) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 80) &= ~1u;
    std::vector<std::wstring>::~vector<std::wstring>(*(_QWORD *)(a2 + 88));
  }
}

```

## disassembly

```asm
0x18000aff5  push    rbp
0x18000aff7  sub     rsp, 20h
0x18000affb  mov     rbp, rdx
0x18000affe  mov     eax, [rbp+50h]
0x18000b001  and     eax, 1
0x18000b004  test    eax, eax
0x18000b006  jz      short loc_18000B015
0x18000b008  and     dword ptr [rbp+50h], 0FFFFFFFEh
0x18000b00c  mov     rcx, [rbp+58h]
0x18000b010  call    ??1?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAA@XZ; std::vector<std::wstring>::~vector<std::wstring>(void)
0x18000b015  add     rsp, 20h
0x18000b019  pop     rbp
0x18000b01a  retn
```
