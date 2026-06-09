# SIPolicyFileRuleCompare

- ea: `0x1800ada40`
- end: `0x1800adad0`
- name: `SIPolicyFileRuleCompare`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18007a8e0`
- `0x1800a63cc`
- `0x1800ad9b0`

## callees

- `0x1800ada40`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ada71`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ada8c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800adaa7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800adac2`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ada71`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ada8c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800adaa7`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800adac2`

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
0x1800ada40  mov     [rsp+arg_0], rbx
0x1800ada45  push    rdi
0x1800ada46  sub     rsp, 20h
0x1800ada4a  mov     rdi, rcx
0x1800ada4d  mov     rbx, rdx
0x1800ada50  mov     ecx, [rdx]
0x1800ada52  mov     eax, [rdi]
0x1800ada54  cmp     eax, ecx
0x1800ada56  jz      short loc_1800ADA66
0x1800ada58  sub     eax, ecx
0x1800ada5a  mov     rbx, [rsp+28h+arg_0]
0x1800ada5f  add     rsp, 20h
0x1800ada63  pop     rdi
0x1800ada64  retn
0x1800ada66  add     rdx, 8; String2
0x1800ada6a  lea     rcx, [rdi+8]; String1
0x1800ada6e  mov     r8b, 1; CaseInSensitive
0x1800ada71  call    cs:__imp_RtlCompareUnicodeString
0x1800ada78  nop     dword ptr [rax+rax+00h]
0x1800ada7d  test    eax, eax
0x1800ada7f  jnz     short loc_1800ADA5A
0x1800ada81  lea     rdx, [rbx+18h]; String2
0x1800ada85  mov     r8b, 1; CaseInSensitive
0x1800ada88  lea     rcx, [rdi+18h]; String1
0x1800ada8c  call    cs:__imp_RtlCompareUnicodeString
0x1800ada93  nop     dword ptr [rax+rax+00h]
0x1800ada98  test    eax, eax
0x1800ada9a  jnz     short loc_1800ADA5A
0x1800ada9c  lea     rdx, [rbx+28h]; String2
0x1800adaa0  mov     r8b, 1; CaseInSensitive
0x1800adaa3  lea     rcx, [rdi+28h]; String1
0x1800adaa7  call    cs:__imp_RtlCompareUnicodeString
0x1800adaae  nop     dword ptr [rax+rax+00h]
0x1800adab3  test    eax, eax
0x1800adab5  jnz     short loc_1800ADA5A
0x1800adab7  lea     rdx, [rbx+38h]; String2
0x1800adabb  mov     r8b, 1; CaseInSensitive
0x1800adabe  lea     rcx, [rdi+38h]; String1
0x1800adac2  call    cs:__imp_RtlCompareUnicodeString
0x1800adac9  nop     dword ptr [rax+rax+00h]
0x1800adace  jmp     short loc_1800ADA5A
```
