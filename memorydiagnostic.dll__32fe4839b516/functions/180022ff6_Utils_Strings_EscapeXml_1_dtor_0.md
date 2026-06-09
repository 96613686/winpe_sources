# _Utils::Strings::EscapeXml_::_1_::dtor$0

- ea: `0x180022ff6`
- end: `0x18002301d`
- name: `_Utils::Strings::EscapeXml_::_1_::dtor$0`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x180007858`
- `0x180022ff6`

## pseudocode

```c
__int64 __fastcall Utils::Strings::EscapeXml_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::wstring::~wstring(*(_QWORD *)(a2 + 64));
  }
  return result;
}

```

## disassembly

```asm
0x180022ff6  push    rbp
0x180022ff8  sub     rsp, 20h
0x180022ffc  mov     rbp, rdx
0x180022fff  mov     eax, [rbp+20h]
0x180023002  and     eax, 1
0x180023005  test    eax, eax
0x180023007  jz      short loc_180023016
0x180023009  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x18002300d  mov     rcx, [rbp+40h]
0x180023011  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ
0x180023016  add     rsp, 20h
0x18002301a  pop     rbp
0x18002301b  retn
```
