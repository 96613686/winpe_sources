# _RegistryConfig::AppendStrings_::_1_::dtor$0

- ea: `0x18000db24`
- end: `0x18000db4b`
- name: `_RegistryConfig::AppendStrings_::_1_::dtor$0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180006ce0`
- `0x18000db24`

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
0x18000db24  push    rbp
0x18000db26  sub     rsp, 20h
0x18000db2a  mov     rbp, rdx
0x18000db2d  mov     eax, [rbp+20h]
0x18000db30  and     eax, 1
0x18000db33  test    eax, eax
0x18000db35  jz      short loc_18000DB44
0x18000db37  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18000db3b  mov     rcx, [rbp+58h]
0x18000db3f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x18000db44  add     rsp, 20h
0x18000db48  pop     rbp
0x18000db49  retn
```
