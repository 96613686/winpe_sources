# Registry::Key::DeleteValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18003c2d0`
- end: `0x18003c2fc`
- name: `?DeleteValue@Key@Registry@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `44`
- prototype: `HRESULT __fastcall(Registry::Key *this, const std::wstring *ValueName)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000dd14`
- `0x1800270d8`
- `0x180039288`

## callees

- `0x180011844`
- `0x18003c2d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c2e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c2e5`

## pseudocode

```c
HRESULT __fastcall Registry::Key::DeleteValue(Registry::Key *this, const std::wstring *ValueName)
{
  const WCHAR *v2; // rax
  HKEY *v3; // r8
  HRESULT result; // eax

  v2 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ValueName->_Mypair._Myval2);
  result = RegDeleteValueW(*v3, v2);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003c2d0  sub     rsp, 28h
0x18003c2d4  mov     r8, this
0x18003c2d7  mov     this, ValueName; this
0x18003c2da  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003c2df  mov     this, [r8]; hKey
0x18003c2e2  mov     ValueName, rax; lpValueName
0x18003c2e5  call    cs:__imp_RegDeleteValueW
0x18003c2eb  test    eax, eax
0x18003c2ed  jle     short loc_18003C2F7
0x18003c2ef  movzx   eax, ax
0x18003c2f2  or      eax, 80070000h
0x18003c2f7  add     rsp, 28h
0x18003c2fb  retn
```
