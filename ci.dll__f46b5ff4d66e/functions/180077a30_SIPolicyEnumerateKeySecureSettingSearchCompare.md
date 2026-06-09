# SIPolicyEnumerateKeySecureSettingSearchCompare

- ea: `0x180077a30`
- end: `0x180077a7d`
- name: `SIPolicyEnumerateKeySecureSettingSearchCompare`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180077a30`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x180077a4a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180077a65`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180077a4a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180077a65`

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
0x180077a30  mov     [rsp+arg_0], rbx
0x180077a35  push    rdi
0x180077a36  sub     rsp, 20h
0x180077a3a  mov     rbx, rdx
0x180077a3d  mov     rdi, rcx
0x180077a40  mov     rcx, [rcx]; String1
0x180077a43  add     rdx, 8; String2
0x180077a47  mov     r8b, 1; CaseInSensitive
0x180077a4a  call    cs:__imp_RtlCompareUnicodeString
0x180077a51  nop     dword ptr [rax+rax+00h]
0x180077a56  test    eax, eax
0x180077a58  jnz     short loc_180077A71
0x180077a5a  mov     rcx, [rdi+8]; String1
0x180077a5e  lea     rdx, [rbx+18h]; String2
0x180077a62  mov     r8b, 1; CaseInSensitive
0x180077a65  call    cs:__imp_RtlCompareUnicodeString
0x180077a6c  nop     dword ptr [rax+rax+00h]
0x180077a71  mov     rbx, [rsp+28h+arg_0]
0x180077a76  add     rsp, 20h
0x180077a7a  pop     rdi
0x180077a7b  retn
```
