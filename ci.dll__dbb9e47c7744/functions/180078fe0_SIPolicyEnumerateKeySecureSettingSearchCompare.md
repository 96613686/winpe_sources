# SIPolicyEnumerateKeySecureSettingSearchCompare

- ea: `0x180078fe0`
- end: `0x18007902d`
- name: `SIPolicyEnumerateKeySecureSettingSearchCompare`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180078fe0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x180078ffa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180079015`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180078ffa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180079015`

## pseudocode

```c
LONG __fastcall SIPolicyEnumerateKeySecureSettingSearchCompare(PCUNICODE_STRING *a1, __int64 a2)
{
  LONG result; // eax

  result = RtlCompareUnicodeString(*a1, (PCUNICODE_STRING)(a2 + 8), 1u);
  if ( !result )
    return RtlCompareUnicodeString(a1[1], (PCUNICODE_STRING)(a2 + 24), 1u);
  return result;
}

```

## disassembly

```asm
0x180078fe0  mov     [rsp+arg_0], rbx
0x180078fe5  push    rdi
0x180078fe6  sub     rsp, 20h
0x180078fea  mov     rbx, rdx
0x180078fed  mov     rdi, rcx
0x180078ff0  mov     rcx, [rcx]; String1
0x180078ff3  add     rdx, 8; String2
0x180078ff7  mov     r8b, 1; CaseInSensitive
0x180078ffa  call    cs:__imp_RtlCompareUnicodeString
0x180079001  nop     dword ptr [rax+rax+00h]
0x180079006  test    eax, eax
0x180079008  jnz     short loc_180079021
0x18007900a  mov     rcx, [rdi+8]; String1
0x18007900e  lea     rdx, [rbx+18h]; String2
0x180079012  mov     r8b, 1; CaseInSensitive
0x180079015  call    cs:__imp_RtlCompareUnicodeString
0x18007901c  nop     dword ptr [rax+rax+00h]
0x180079021  mov     rbx, [rsp+28h+arg_0]
0x180079026  add     rsp, 20h
0x18007902a  pop     rdi
0x18007902b  retn
```
