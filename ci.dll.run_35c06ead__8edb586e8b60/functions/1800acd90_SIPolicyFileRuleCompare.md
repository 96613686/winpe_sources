# SIPolicyFileRuleCompare

- ea: `0x1800acd90`
- end: `0x1800ace20`
- name: `SIPolicyFileRuleCompare`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007b060`
- `0x1800a6020`
- `0x1800acd00`

## callees

- `0x1800acd90`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1800acdc1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800acddc`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800acdf7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ace12`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800acdc1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800acddc`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800acdf7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ace12`

## pseudocode

```c
int __fastcall SIPolicyFileRuleCompare(__int64 a1, __int64 a2)
{
  int result; // eax

  if ( *(_DWORD *)a1 != *(_DWORD *)a2 )
    return *(_DWORD *)a1 - *(_DWORD *)a2;
  result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 8), (PCUNICODE_STRING)(a2 + 8), 1u);
  if ( !result )
  {
    result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 24), (PCUNICODE_STRING)(a2 + 24), 1u);
    if ( !result )
    {
      result = RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 40), (PCUNICODE_STRING)(a2 + 40), 1u);
      if ( !result )
        return RtlCompareUnicodeString((PCUNICODE_STRING)(a1 + 56), (PCUNICODE_STRING)(a2 + 56), 1u);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800acd90  mov     [rsp+arg_0], rbx
0x1800acd95  push    rdi
0x1800acd96  sub     rsp, 20h
0x1800acd9a  mov     rdi, rcx
0x1800acd9d  mov     rbx, rdx
0x1800acda0  mov     ecx, [rdx]
0x1800acda2  mov     eax, [rdi]
0x1800acda4  cmp     eax, ecx
0x1800acda6  jz      short loc_1800ACDB6
0x1800acda8  sub     eax, ecx
0x1800acdaa  mov     rbx, [rsp+28h+arg_0]
0x1800acdaf  add     rsp, 20h
0x1800acdb3  pop     rdi
0x1800acdb4  retn
0x1800acdb6  add     rdx, 8; String2
0x1800acdba  lea     rcx, [rdi+8]; String1
0x1800acdbe  mov     r8b, 1; CaseInSensitive
0x1800acdc1  call    cs:__imp_RtlCompareUnicodeString
0x1800acdc8  nop     dword ptr [rax+rax+00h]
0x1800acdcd  test    eax, eax
0x1800acdcf  jnz     short loc_1800ACDAA
0x1800acdd1  lea     rdx, [rbx+18h]; String2
0x1800acdd5  mov     r8b, 1; CaseInSensitive
0x1800acdd8  lea     rcx, [rdi+18h]; String1
0x1800acddc  call    cs:__imp_RtlCompareUnicodeString
0x1800acde3  nop     dword ptr [rax+rax+00h]
0x1800acde8  test    eax, eax
0x1800acdea  jnz     short loc_1800ACDAA
0x1800acdec  lea     rdx, [rbx+28h]; String2
0x1800acdf0  mov     r8b, 1; CaseInSensitive
0x1800acdf3  lea     rcx, [rdi+28h]; String1
0x1800acdf7  call    cs:__imp_RtlCompareUnicodeString
0x1800acdfe  nop     dword ptr [rax+rax+00h]
0x1800ace03  test    eax, eax
0x1800ace05  jnz     short loc_1800ACDAA
0x1800ace07  lea     rdx, [rbx+38h]; String2
0x1800ace0b  mov     r8b, 1; CaseInSensitive
0x1800ace0e  lea     rcx, [rdi+38h]; String1
0x1800ace12  call    cs:__imp_RtlCompareUnicodeString
0x1800ace19  nop     dword ptr [rax+rax+00h]
0x1800ace1e  jmp     short loc_1800ACDAA
```
