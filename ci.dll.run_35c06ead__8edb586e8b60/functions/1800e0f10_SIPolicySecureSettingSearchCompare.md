# SIPolicySecureSettingSearchCompare

- ea: `0x1800e0f10`
- end: `0x1800e0f7a`
- name: `SIPolicySecureSettingSearchCompare`
- size: `106`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800e0f10`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f2a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f51`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f6c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f2a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f51`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800e0f6c`

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
0x1800e0f10  mov     [rsp+arg_0], rbx
0x1800e0f15  push    rdi
0x1800e0f16  sub     rsp, 20h
0x1800e0f1a  mov     rbx, rdx
0x1800e0f1d  mov     rdi, rcx
0x1800e0f20  mov     rcx, [rcx]; String1
0x1800e0f23  add     rdx, 8; String2
0x1800e0f27  mov     r8b, 1; CaseInSensitive
0x1800e0f2a  call    cs:__imp_RtlCompareUnicodeString
0x1800e0f31  nop     dword ptr [rax+rax+00h]
0x1800e0f36  test    eax, eax
0x1800e0f38  jz      short loc_1800E0F46
0x1800e0f3a  mov     rbx, [rsp+28h+arg_0]
0x1800e0f3f  add     rsp, 20h
0x1800e0f43  pop     rdi
0x1800e0f44  retn
0x1800e0f46  mov     rcx, [rdi+8]; String1
0x1800e0f4a  lea     rdx, [rbx+18h]; String2
0x1800e0f4e  mov     r8b, 1; CaseInSensitive
0x1800e0f51  call    cs:__imp_RtlCompareUnicodeString
0x1800e0f58  nop     dword ptr [rax+rax+00h]
0x1800e0f5d  test    eax, eax
0x1800e0f5f  jnz     short loc_1800E0F3A
0x1800e0f61  mov     rcx, [rdi+10h]; String1
0x1800e0f65  lea     rdx, [rbx+28h]; String2
0x1800e0f69  mov     r8b, 1; CaseInSensitive
0x1800e0f6c  call    cs:__imp_RtlCompareUnicodeString
0x1800e0f73  nop     dword ptr [rax+rax+00h]
0x1800e0f78  jmp     short loc_1800E0F3A
```
