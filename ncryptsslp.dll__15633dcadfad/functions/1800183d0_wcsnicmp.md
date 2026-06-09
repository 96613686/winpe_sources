# _wcsnicmp

- ea: `0x1800183d0`
- end: `0x1800183f4`
- name: `_wcsnicmp`
- size: `36`
- prototype: `int __cdecl(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)`
- caller_count: `18`
- callee_count: `4`
- tags: ``

## callers

- `0x180002510`
- `0x1800029e0`
- `0x1800037a0`
- `0x180003f10`
- `0x180004570`
- `0x180005860`
- `0x1800097f0`
- `0x180009ca0`
- `0x18000a120`
- `0x18000ae00`
- `0x18000b6a0`
- `0x18000cfb0`
- `0x18000eb00`
- `0x18000fff0`
- `0x18001d8e8`
- `0x180024450`
- `0x180024964`
- `0x180024d04`

## callees

- `0x1800180b0`
- `0x180018350`
- `0x1800183d0`
- `0x180018400`

## pseudocode

```c
int __cdecl wcsnicmp(const wchar_t *String1, const wchar_t *String2, size_t MaxCount)
{
  if ( _acrt_locale_changed_data )
    return wcsnicmp_l(String1, String2, MaxCount, 0);
  if ( String1 && String2 )
    return _ascii_wcsnicmp(String1, String2, MaxCount);
  return wcsnicmp_validate_param(String1, String2, MaxCount);
}

```

## disassembly

```asm
0x1800183d0  cmp     cs:__acrt_locale_changed_data, 0
0x1800183d7  jnz     short loc_1800183EC
0x1800183d9  test    rcx, rcx
0x1800183dc  jz      short loc_1800183E7
0x1800183de  test    rdx, rdx
0x1800183e1  jnz     __ascii_wcsnicmp
0x1800183e7  jmp     _wcsnicmp_validate_param
0x1800183ec  xor     r9d, r9d
0x1800183ef  jmp     _wcsnicmp_l
```
