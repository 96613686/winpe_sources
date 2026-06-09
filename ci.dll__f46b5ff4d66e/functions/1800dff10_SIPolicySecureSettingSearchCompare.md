# SIPolicySecureSettingSearchCompare

- ea: `0x1800dff10`
- end: `0x1800dff7a`
- name: `SIPolicySecureSettingSearchCompare`
- size: `106`
- prototype: `int __cdecl(const void *, const void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800dff10`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1800dff2a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800dff51`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800dff6c`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800dff2a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800dff51`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1800dff6c`

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
0x1800dff10  mov     [rsp+arg_0], rbx
0x1800dff15  push    rdi
0x1800dff16  sub     rsp, 20h
0x1800dff1a  mov     rbx, rdx
0x1800dff1d  mov     rdi, rcx
0x1800dff20  mov     rcx, [rcx]; String1
0x1800dff23  add     rdx, 8; String2
0x1800dff27  mov     r8b, 1; CaseInSensitive
0x1800dff2a  call    cs:__imp_RtlCompareUnicodeString
0x1800dff31  nop     dword ptr [rax+rax+00h]
0x1800dff36  test    eax, eax
0x1800dff38  jz      short loc_1800DFF46
0x1800dff3a  mov     rbx, [rsp+28h+arg_0]
0x1800dff3f  add     rsp, 20h
0x1800dff43  pop     rdi
0x1800dff44  retn
0x1800dff46  mov     rcx, [rdi+8]; String1
0x1800dff4a  lea     rdx, [rbx+18h]; String2
0x1800dff4e  mov     r8b, 1; CaseInSensitive
0x1800dff51  call    cs:__imp_RtlCompareUnicodeString
0x1800dff58  nop     dword ptr [rax+rax+00h]
0x1800dff5d  test    eax, eax
0x1800dff5f  jnz     short loc_1800DFF3A
0x1800dff61  mov     rcx, [rdi+10h]; String1
0x1800dff65  lea     rdx, [rbx+28h]; String2
0x1800dff69  mov     r8b, 1; CaseInSensitive
0x1800dff6c  call    cs:__imp_RtlCompareUnicodeString
0x1800dff73  nop     dword ptr [rax+rax+00h]
0x1800dff78  jmp     short loc_1800DFF3A
```
