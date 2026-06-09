# Registry::Key::SetValue(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,ulong,uchar const *,ulong)

- ea: `0x18003cc18`
- end: `0x18003cc57`
- name: `?SetValue@Key@Registry@@AEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@KPEBEK@Z`
- size: `63`
- prototype: `HRESULT __fastcall(Registry::Key *this, const std::wstring *ValueName, unsigned int Type, const unsigned __int8 *Data, unsigned int DataLength)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800216c4`
- `0x18003cbd0`

## callees

- `0x180011844`
- `0x18003cc18`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003cc40`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18003cc40`

## pseudocode

```c
HRESULT __fastcall Registry::Key::SetValue(
        Registry::Key *this,
        const std::wstring *ValueName,
        unsigned int Type,
        const unsigned __int8 *Data,
        DWORD DataLength)
{
  const WCHAR *v5; // rax
  HKEY *v6; // r10
  DWORD v7; // r8d
  const BYTE *lpData; // r9
  HRESULT result; // eax

  v5 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&ValueName->_Mypair._Myval2);
  result = RegSetValueExW(*v6, v5, 0, v7, lpData, DataLength);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x18003cc18  sub     rsp, 38h
0x18003cc1c  mov     r10, this
0x18003cc1f  mov     this, ValueName; this
0x18003cc22  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003cc27  mov     edx, [rsp+38h+arg_20]
0x18003cc2b  mov     this, [r10]; hKey
0x18003cc2e  mov     [rsp+38h+cbData], edx; cbData
0x18003cc32  mov     ValueName, rax; lpValueName
0x18003cc35  mov     [rsp+38h+lpData], Data; lpData
0x18003cc3a  mov     r9d, Type; dwType
0x18003cc3d  xor     Type, Type; Reserved
0x18003cc40  call    cs:__imp_RegSetValueExW
0x18003cc46  test    eax, eax
0x18003cc48  jle     short loc_18003CC52
0x18003cc4a  movzx   eax, ax
0x18003cc4d  or      eax, 80070000h
0x18003cc52  add     rsp, 38h
0x18003cc56  retn
```
