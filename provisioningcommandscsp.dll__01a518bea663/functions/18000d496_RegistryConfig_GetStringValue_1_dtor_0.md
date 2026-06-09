# _RegistryConfig::GetStringValue_::_1_::dtor$0

- ea: `0x18000d496`
- end: `0x18000d4bf`
- name: `_RegistryConfig::GetStringValue_::_1_::dtor$0`
- size: `41`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x1800069c0`
- `0x18000d496`

## pseudocode

```c
__int64 __fastcall RegistryConfig::GetStringValue_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 64) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 64) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 136));
  }
  return result;
}

```

## disassembly

```asm
0x18000d496  push    rbp
0x18000d498  sub     rsp, 20h
0x18000d49c  mov     rbp, rdx
0x18000d49f  mov     eax, [rbp+40h]
0x18000d4a2  and     eax, 1
0x18000d4a5  test    eax, eax
0x18000d4a7  jz      short loc_18000D4B9
0x18000d4a9  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x18000d4ad  mov     rcx, [rbp+88h]
0x18000d4b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000d4b9  add     rsp, 20h
0x18000d4bd  pop     rbp
0x18000d4be  retn
```
