# IsCacheRebuildRequired(void)

- ea: `0x14000809c`
- end: `0x1400081a1`
- name: `?IsCacheRebuildRequired@@YAHXZ`
- size: `261`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000d8b8`

## callees

- `0x140002190`
- `0x140007930`
- `0x14000809c`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x1400080f5`
- `ADVAPI32!RegGetValueW` at `0x140008142`
- `ADVAPI32!RegGetValueW` at `0x1400080f5`
- `ADVAPI32!RegGetValueW` at `0x140008142`

## string_xrefs

- `0x14000812b`: `System\CurrentControlSet\Control\CMF\Config`

## pseudocode

```c
unsigned int IsCacheRebuildRequired(void)
{
  const unsigned __int16 *v0; // rcx
  LSTATUS ValueW; // eax
  unsigned __int16 *v2; // rax
  int v3; // r8d
  unsigned int result; // eax
  DWORD pcbData; // [rsp+40h] [rbp-448h] BYREF
  DWORD v6[3]; // [rsp+44h] [rbp-444h] BYREF
  _BYTE pvData[528]; // [rsp+50h] [rbp-438h] BYREF
  _BYTE v8[528]; // [rsp+260h] [rbp-228h] BYREF

  pcbData = 520;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\LanguageOverlay\\PriMergeChecksum",
          L"Latest",
          2u,
          0,
          pvData,
          &pcbData) )
  {
    v6[0] = 520;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"System\\CurrentControlSet\\Control\\CMF\\Config",
               L"LanguageOverlaySignatureUsedForMerge",
               2u,
               0,
               v8,
               v6);
    if ( ValueW == 2 )
      return 1;
    if ( !ValueW )
    {
      v2 = (unsigned __int16 *)pvData;
      do
      {
        v3 = *(unsigned __int16 *)((char *)v2 + v8 - pvData);
        v0 = (const unsigned __int16 *)((unsigned int)*v2 - v3);
        if ( (_DWORD)v0 )
          break;
        ++v2;
      }
      while ( v3 );
      if ( (_DWORD)v0 )
        return 1;
    }
  }
  result = GetResControlConfigValue(v0);
  if ( result )
    return 1;
  return result;
}

```

## disassembly

```asm
0x14000809c  sub     rsp, 488h
0x1400080a3  mov     rax, cs:__security_cookie
0x1400080aa  xor     rax, rsp
0x1400080ad  mov     [rsp+488h+var_18], rax
0x1400080b5  lea     rax, [rsp+488h+var_448]
0x1400080ba  mov     [rsp+488h+var_448], 208h
0x1400080c2  mov     [rsp+488h+pcbData], rax; pcbData
0x1400080c7  lea     r8, Value; "Latest"
0x1400080ce  lea     rax, [rsp+488h+var_438]
0x1400080d3  mov     r9d, 2; dwFlags
0x1400080d9  mov     [rsp+488h+pvData], rax; pvData
0x1400080de  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\LanguageOverlay\\P"...
0x1400080e5  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400080ec  mov     [rsp+488h+pdwType], 0; pdwType
0x1400080f5  call    cs:__imp_RegGetValueW
0x1400080fb  test    eax, eax
0x1400080fd  jnz     short loc_14000817B
0x1400080ff  lea     rax, [rsp+488h+var_444]
0x140008104  mov     [rsp+488h+var_444], 208h
0x14000810c  mov     [rsp+488h+pcbData], rax; pcbData
0x140008111  lea     r8, aLanguageoverla; "LanguageOverlaySignatureUsedForMerge"
0x140008118  lea     rax, [rsp+488h+var_228]
0x140008120  mov     r9d, 2; dwFlags
0x140008126  mov     [rsp+488h+pvData], rax; pvData
0x14000812b  lea     rdx, aSystemCurrentc_2; "System\\CurrentControlSet\\Control\\CMF"...
0x140008132  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140008139  mov     [rsp+488h+pdwType], 0; pdwType
0x140008142  call    cs:__imp_RegGetValueW
0x140008148  cmp     eax, 2
0x14000814b  jz      short loc_140008184
0x14000814d  test    eax, eax
0x14000814f  jnz     short loc_14000817B
0x140008151  lea     rax, [rsp+488h+var_438]
0x140008156  lea     rdx, [rsp+488h+var_228]
0x14000815e  sub     rdx, rax
0x140008161  movzx   ecx, word ptr [rax]
0x140008164  movzx   r8d, word ptr [rax+rdx]
0x140008169  sub     ecx, r8d; unsigned __int16 *
0x14000816c  jnz     short loc_140008177
0x14000816e  add     rax, 2
0x140008172  test    r8d, r8d
0x140008175  jnz     short loc_140008161
0x140008177  test    ecx, ecx
0x140008179  jnz     short loc_140008184
0x14000817b  call    ?GetResControlConfigValue@@YAKPEBG@Z; GetResControlConfigValue(ushort const *)
0x140008180  test    eax, eax
0x140008182  jz      short loc_140008189
0x140008184  mov     eax, 1
0x140008189  mov     rcx, [rsp+488h+var_18]
0x140008191  xor     rcx, rsp; StackCookie
0x140008194  call    __security_check_cookie
0x140008199  add     rsp, 488h
0x1400081a0  retn
```
