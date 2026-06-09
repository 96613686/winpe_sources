# SIPolicySecureSettingSearchCompare

- ea: `0x1800e0f00`
- end: `0x1800e0f6a`
- name: `SIPolicySecureSettingSearchCompare`
- size: `106`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800e0f00`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f1a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f41`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f5c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f1a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f41`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f5c`

## pseudocode

```c
int __fastcall SIPolicySecureSettingSearchCompare(PCUNICODE_STRING *a1, char *a2)
{
  int result; // eax

  result = RtlCompareUnicodeString(*a1, (PCUNICODE_STRING)(a2 + 8), 1u);
  if ( !result )
  {
    result = RtlCompareUnicodeString(a1[1], (PCUNICODE_STRING)(a2 + 24), 1u);
    if ( !result )
      return RtlCompareUnicodeString(a1[2], (PCUNICODE_STRING)(a2 + 40), 1u);
  }
  return result;
}

```

## disassembly

```asm
0x1800e0f00  mov     [rsp+arg_0], rbx
0x1800e0f05  push    rdi
0x1800e0f06  sub     rsp, 20h
0x1800e0f0a  mov     rbx, rdx
0x1800e0f0d  mov     rdi, rcx
0x1800e0f10  mov     rcx, [rcx]; String1
0x1800e0f13  add     rdx, 8; String2
0x1800e0f17  mov     r8b, 1; CaseInSensitive
0x1800e0f1a  call    cs:__imp_RtlCompareUnicodeString
0x1800e0f21  nop     dword ptr [rax+rax+00h]
0x1800e0f26  test    eax, eax
0x1800e0f28  jz      short loc_1800E0F36
0x1800e0f2a  mov     rbx, [rsp+28h+arg_0]
0x1800e0f2f  add     rsp, 20h
0x1800e0f33  pop     rdi
0x1800e0f34  retn
0x1800e0f36  mov     rcx, [rdi+8]; String1
0x1800e0f3a  lea     rdx, [rbx+18h]; String2
0x1800e0f3e  mov     r8b, 1; CaseInSensitive
0x1800e0f41  call    cs:__imp_RtlCompareUnicodeString
0x1800e0f48  nop     dword ptr [rax+rax+00h]
0x1800e0f4d  test    eax, eax
0x1800e0f4f  jnz     short loc_1800E0F2A
0x1800e0f51  mov     rcx, [rdi+10h]; String1
0x1800e0f55  lea     rdx, [rbx+28h]; String2
0x1800e0f59  mov     r8b, 1; CaseInSensitive
0x1800e0f5c  call    cs:__imp_RtlCompareUnicodeString
0x1800e0f63  nop     dword ptr [rax+rax+00h]
0x1800e0f68  jmp     short loc_1800E0F2A
```
