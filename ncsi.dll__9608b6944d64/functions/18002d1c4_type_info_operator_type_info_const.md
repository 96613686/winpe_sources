# type_info::operator==(type_info const &)

- ea: `0x18002d1c4`
- end: `0x18002d1e0`
- name: `??8type_info@@QEBA_NAEBV0@@Z`
- size: `28`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180022460`
- `0x1800272f0`
- `0x18002e008`
- `0x180041be0`
- `0x180041d14`
- `0x18006d908`
- `0x18006d960`
- `0x18006d9b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002d1d0`
- `api-ms-win-crt-private-l1-1-0!__std_type_info_compare` at `0x18002d1d0`

## pseudocode

```c
bool __fastcall type_info::operator==(__int64 a1, __int64 a2)
{
  return (unsigned int)__std_type_info_compare(a1 + 8, a2 + 8) == 0;
}

```

## disassembly

```asm
0x18002d1c4  sub     rsp, 28h
0x18002d1c8  add     rdx, 8
0x18002d1cc  add     rcx, 8
0x18002d1d0  call    cs:__imp___std_type_info_compare
0x18002d1d6  test    eax, eax
0x18002d1d8  setz    al
0x18002d1db  add     rsp, 28h
0x18002d1df  retn
```
