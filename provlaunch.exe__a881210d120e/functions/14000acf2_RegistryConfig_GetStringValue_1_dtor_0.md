# _RegistryConfig::GetStringValue_::_1_::dtor$0

- ea: `0x14000acf2`
- end: `0x14000ad1b`
- name: `_RegistryConfig::GetStringValue_::_1_::dtor$0`
- size: `41`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007c34`
- `0x14000acf2`

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
0x14000acf2  push    rbp
0x14000acf4  sub     rsp, 20h
0x14000acf8  mov     rbp, rdx
0x14000acfb  mov     eax, [rbp+40h]
0x14000acfe  and     eax, 1
0x14000ad01  test    eax, eax
0x14000ad03  jz      short loc_14000AD15
0x14000ad05  and     dword ptr [rbp+40h], 0FFFFFFFEh
0x14000ad09  mov     rcx, [rbp+88h]
0x14000ad10  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000ad15  add     rsp, 20h
0x14000ad19  pop     rbp
0x14000ad1a  retn
```
