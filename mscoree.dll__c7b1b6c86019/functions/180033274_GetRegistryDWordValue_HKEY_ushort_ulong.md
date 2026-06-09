# GetRegistryDWordValue(HKEY__ *,ushort *,ulong *)

- ea: `0x180033274`
- end: `0x1800332fd`
- name: `?GetRegistryDWordValue@@YAJPEAUHKEY__@@PEAGPEAK@Z`
- size: `137`
- prototype: `__int64 __fastcall(HKEY, unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180032c00`

## callees

- `0x18000b1f0`
- `0x180033274`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x1800332a9`
- `ADVAPI32!RegQueryValueExW` at `0x1800332a9`

## string_xrefs

- `0x1800332dd`: `Registry value type for %s was not a DWORD!`

## pseudocode

```c
LSTATUS __fastcall GetRegistryDWordValue(HKEY a1, unsigned __int16 *a2, BYTE *a3)
{
  LSTATUS result; // eax
  DWORD v6[6]; // [rsp+30h] [rbp-18h] BYREF
  DWORD v7; // [rsp+68h] [rbp+20h] BYREF

  v7 = 0;
  v6[0] = 4;
  result = RegQueryValueExW(a1, a2, 0, &v7, a3, v6);
  if ( result )
  {
    if ( result == 2 )
    {
      *(_DWORD *)a3 = 999;
      return 1;
    }
    else if ( result > 0 )
    {
      return (unsigned __int16)result | 0x80070000;
    }
  }
  else if ( v7 == 4 )
  {
    return 0;
  }
  else
  {
    ReportAppCompatError((wchar_t *)L"Registry value type for %s was not a DWORD!", a2);
    return -2147467259;
  }
  return result;
}

```

## disassembly

```asm
0x180033274  mov     r11, rsp
0x180033277  mov     [r11+8], rbx
0x18003327b  push    rdi
0x18003327c  sub     rsp, 40h
0x180033280  mov     rbx, r8
0x180033283  mov     [rsp+48h+arg_18], 0
0x18003328b  lea     rax, [r11-18h]
0x18003328f  mov     [rsp+48h+var_18], 4
0x180033297  mov     [r11-20h], rax
0x18003329b  lea     r9, [r11+20h]; lpType
0x18003329f  xor     r8d, r8d; lpReserved
0x1800332a2  mov     [r11-28h], rbx
0x1800332a6  mov     rdi, rdx
0x1800332a9  call    cs:__imp_RegQueryValueExW
0x1800332af  test    eax, eax
0x1800332b1  jz      short loc_1800332D3
0x1800332b3  cmp     eax, 2
0x1800332b6  jz      short loc_1800332C6
0x1800332b8  test    eax, eax
0x1800332ba  jle     short loc_1800332F2
0x1800332bc  movzx   eax, ax
0x1800332bf  or      eax, 80070000h
0x1800332c4  jmp     short loc_1800332F2
0x1800332c6  mov     dword ptr [rbx], 3E7h
0x1800332cc  mov     eax, 1
0x1800332d1  jmp     short loc_1800332F2
0x1800332d3  cmp     [rsp+48h+arg_18], 4
0x1800332d8  jz      short loc_1800332F0
0x1800332da  mov     rdx, rdi
0x1800332dd  lea     rcx, aRegistryValueT_0; "Registry value type for %s was not a DW"...
0x1800332e4  call    ?ReportAppCompatError@@YAXPEAGZZ; ReportAppCompatError(ushort *,...)
0x1800332e9  mov     eax, 80004005h
0x1800332ee  jmp     short loc_1800332F2
0x1800332f0  xor     eax, eax
0x1800332f2  mov     rbx, [rsp+48h+arg_0]
0x1800332f7  add     rsp, 40h
0x1800332fb  pop     rdi
0x1800332fc  retn
```
