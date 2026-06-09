# _RegistryConfig::GetStringValue_::_1_::dtor$0

- ea: `0x18000db63`
- end: `0x18000db8d`
- name: `_RegistryConfig::GetStringValue_::_1_::dtor$0`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180006ce0`
- `0x18000db63`

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
0x18000db63  push    rbp
0x18000db65  sub     rsp, 20h
0x18000db69  mov     rbp, rdx
0x18000db6c  mov     eax, [rbp+40h]
0x18000db6f  and     eax, 1
0x18000db72  test    eax, eax
0x18000db74  jz      short loc_18000DB86
0x18000db76  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x18000db7a  mov     rcx, [rbp+88h]
0x18000db81  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000db86  add     rsp, 20h
0x18000db8a  pop     rbp
0x18000db8b  retn
```
