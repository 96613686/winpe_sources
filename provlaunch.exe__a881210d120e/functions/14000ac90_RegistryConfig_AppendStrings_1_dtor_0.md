# _RegistryConfig::AppendStrings_::_1_::dtor$0

- ea: `0x14000ac90`
- end: `0x14000acb6`
- name: `_RegistryConfig::AppendStrings_::_1_::dtor$0`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140007c34`
- `0x14000ac90`

## pseudocode

```c
__int64 __fastcall RegistryConfig::AppendStrings_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 120));
  }
  return result;
}

```

## disassembly

```asm
0x14000ac90  push    rbp
0x14000ac92  sub     rsp, 20h
0x14000ac96  mov     rbp, rdx
0x14000ac99  mov     eax, [rbp+20h]
0x14000ac9c  and     eax, 1
0x14000ac9f  test    eax, eax
0x14000aca1  jz      short loc_14000ACB0
0x14000aca3  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x14000aca7  mov     rcx, [rbp+78h]
0x14000acab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14000acb0  add     rsp, 20h
0x14000acb4  pop     rbp
0x14000acb5  retn
```
