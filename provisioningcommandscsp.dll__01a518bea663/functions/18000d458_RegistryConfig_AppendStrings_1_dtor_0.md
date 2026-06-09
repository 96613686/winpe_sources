# _RegistryConfig::AppendStrings_::_1_::dtor$0

- ea: `0x18000d458`
- end: `0x18000d47e`
- name: `_RegistryConfig::AppendStrings_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800069c0`
- `0x18000d458`

## pseudocode

```c
__int64 __fastcall RegistryConfig::AppendStrings_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 88));
  }
  return result;
}

```

## disassembly

```asm
0x18000d458  push    rbp
0x18000d45a  sub     rsp, 20h
0x18000d45e  mov     rbp, rdx
0x18000d461  mov     eax, [rbp+20h]
0x18000d464  and     eax, 1
0x18000d467  test    eax, eax
0x18000d469  jz      short loc_18000D478
0x18000d46b  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000d46f  mov     rcx, [rbp+58h]
0x18000d473  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18000d478  add     rsp, 20h
0x18000d47c  pop     rbp
0x18000d47d  retn
```
