# HrRegSetValueEx(HKEY__ *,ushort const *,ulong,uchar const *,ulong)

- ea: `0x180030474`
- end: `0x1800304aa`
- name: `?HrRegSetValueEx@@YAJPEAUHKEY__@@PEBGKPEBEK@Z`
- size: `54`
- prototype: `int(HKEY, const unsigned __int16 *, unsigned int, const unsigned __int8 *, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180031b1c`

## callees

- `0x180030474`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180030493`
- `ADVAPI32!RegSetValueExW` at `0x180030493`

## pseudocode

```c
LSTATUS __fastcall HrRegSetValueEx(HKEY a1, const unsigned __int16 *a2, __int64 a3, const unsigned __int8 *lpData)
{
  LSTATUS result; // eax

  result = RegSetValueExW(a1, L"MediaSubType", 0, 4u, lpData, 4u);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180030474  sub     rsp, 38h
0x180030478  mov     eax, 4
0x18003047d  lea     rdx, ?c_szRegValueMediaSubType@@3QBGB; "MediaSubType"
0x180030484  mov     [rsp+38h+cbData], eax; cbData
0x180030488  xor     r8d, r8d; Reserved
0x18003048b  mov     [rsp+38h+lpData], r9; lpData
0x180030490  mov     r9d, eax; dwType
0x180030493  call    cs:__imp_RegSetValueExW
0x180030499  test    eax, eax
0x18003049b  jle     short loc_1800304A5
0x18003049d  movzx   eax, ax
0x1800304a0  or      eax, 80070000h
0x1800304a5  add     rsp, 38h
0x1800304a9  retn
```
