# _CMapsToastTaskHandler::ParseArguments_::_1_::dtor$5

- ea: `0x1800097e6`
- end: `0x180009814`
- name: `_CMapsToastTaskHandler::ParseArguments_::_1_::dtor$5`
- size: `46`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x1800097e6`

## import_xrefs

- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180009808`
- `msvcp_win!??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ` at `0x180009808`

## pseudocode

```c
__int64 __fastcall CMapsToastTaskHandler::ParseArguments_::_1_::dtor_5(__int64 a1, __int64 a2)
{
  __int64 result; // rax

  result = *(_DWORD *)(a2 + 32) & 1;
  if ( (_DWORD)result )
  {
    *(_DWORD *)(a2 + 32) &= ~1u;
    return std::basic_ios<unsigned short>::~basic_ios<unsigned short,std::char_traits<unsigned short>>(a2 + 240);
  }
  return result;
}

```

## disassembly

```asm
0x1800097e6  push    rbp
0x1800097e8  sub     rsp, 20h
0x1800097ec  mov     rbp, rdx
0x1800097ef  mov     eax, [rbp+20h]
0x1800097f2  and     eax, 1
0x1800097f5  test    eax, eax
0x1800097f7  jz      short loc_18000980E
0x1800097f9  and     dword ptr [rbp+20h], 0FFFFFFFEh
0x1800097fd  lea     rcx, [rbp+60h]
0x180009801  add     rcx, 90h
0x180009808  call    cs:__imp_??1?$basic_ios@GU?$char_traits@G@std@@@std@@UEAA@XZ; std::basic_ios<ushort>::~basic_ios<ushort,std::char_traits<ushort>>(void)
0x18000980e  add     rsp, 20h
0x180009812  pop     rbp
0x180009813  retn
```
