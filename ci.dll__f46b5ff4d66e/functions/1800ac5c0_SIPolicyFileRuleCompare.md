# SIPolicyFileRuleCompare

- ea: `0x1800ac5c0`
- end: `0x1800ac650`
- name: `SIPolicyFileRuleCompare`
- size: `144`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180079330`
- `0x1800a4d9c`
- `0x1800ac530`

## callees

- `0x1800ac5c0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ac5f1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ac60c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ac627`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ac642`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ac5f1`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ac60c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ac627`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800ac642`

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
0x1800ac5c0  mov     [rsp+arg_0], rbx
0x1800ac5c5  push    rdi
0x1800ac5c6  sub     rsp, 20h
0x1800ac5ca  mov     rdi, rcx
0x1800ac5cd  mov     rbx, rdx
0x1800ac5d0  mov     ecx, [rdx]
0x1800ac5d2  mov     eax, [rdi]
0x1800ac5d4  cmp     eax, ecx
0x1800ac5d6  jz      short loc_1800AC5E6
0x1800ac5d8  sub     eax, ecx
0x1800ac5da  mov     rbx, [rsp+28h+arg_0]
0x1800ac5df  add     rsp, 20h
0x1800ac5e3  pop     rdi
0x1800ac5e4  retn
0x1800ac5e6  add     rdx, 8; String2
0x1800ac5ea  lea     rcx, [rdi+8]; String1
0x1800ac5ee  mov     r8b, 1; CaseInSensitive
0x1800ac5f1  call    cs:__imp_RtlCompareUnicodeString
0x1800ac5f8  nop     dword ptr [rax+rax+00h]
0x1800ac5fd  test    eax, eax
0x1800ac5ff  jnz     short loc_1800AC5DA
0x1800ac601  lea     rdx, [rbx+18h]; String2
0x1800ac605  mov     r8b, 1; CaseInSensitive
0x1800ac608  lea     rcx, [rdi+18h]; String1
0x1800ac60c  call    cs:__imp_RtlCompareUnicodeString
0x1800ac613  nop     dword ptr [rax+rax+00h]
0x1800ac618  test    eax, eax
0x1800ac61a  jnz     short loc_1800AC5DA
0x1800ac61c  lea     rdx, [rbx+28h]; String2
0x1800ac620  mov     r8b, 1; CaseInSensitive
0x1800ac623  lea     rcx, [rdi+28h]; String1
0x1800ac627  call    cs:__imp_RtlCompareUnicodeString
0x1800ac62e  nop     dword ptr [rax+rax+00h]
0x1800ac633  test    eax, eax
0x1800ac635  jnz     short loc_1800AC5DA
0x1800ac637  lea     rdx, [rbx+38h]; String2
0x1800ac63b  mov     r8b, 1; CaseInSensitive
0x1800ac63e  lea     rcx, [rdi+38h]; String1
0x1800ac642  call    cs:__imp_RtlCompareUnicodeString
0x1800ac649  nop     dword ptr [rax+rax+00h]
0x1800ac64e  jmp     short loc_1800AC5DA
```
