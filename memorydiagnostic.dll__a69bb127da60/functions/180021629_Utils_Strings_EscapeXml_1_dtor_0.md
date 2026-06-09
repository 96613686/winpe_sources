# _Utils::Strings::EscapeXml_::_1_::dtor$0

- ea: `0x180021629`
- end: `0x18002164f`
- name: `_Utils::Strings::EscapeXml_::_1_::dtor$0`
- size: `38`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180007818`
- `0x180021629`

## pseudocode

```c
__int64 __fastcall Utils::Strings::EscapeXml_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(*(char ***)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x180021629  push    rbp
0x18002162b  sub     rsp, 20h
0x18002162f  mov     rbp, rdx
0x180021632  mov     eax, [rbp+20h]
0x180021635  and     eax, 1
0x180021638  test    eax, eax
0x18002163a  jz      short loc_180021649
0x18002163c  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x180021640  mov     rcx, [rbp+40h]
0x180021644  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180021649  add     rsp, 20h
0x18002164d  pop     rbp
0x18002164e  retn
```
