# SIPolicyEnumerateKeySecureSettingSearchCompare

- ea: `0x1800792f0`
- end: `0x18007933d`
- name: `SIPolicyEnumerateKeySecureSettingSearchCompare`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800792f0`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x18007930a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180079325`
- `ntoskrnl!RtlCompareUnicodeString` at `0x18007930a`
- `ntoskrnl!RtlCompareUnicodeString` at `0x180079325`

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
0x1800792f0  mov     [rsp+arg_0], rbx
0x1800792f5  push    rdi
0x1800792f6  sub     rsp, 20h
0x1800792fa  mov     rbx, rdx
0x1800792fd  mov     rdi, rcx
0x180079300  mov     rcx, [rcx]; String1
0x180079303  add     rdx, 8; String2
0x180079307  mov     r8b, 1; CaseInSensitive
0x18007930a  call    cs:__imp_RtlCompareUnicodeString
0x180079311  nop     dword ptr [rax+rax+00h]
0x180079316  test    eax, eax
0x180079318  jnz     short loc_180079331
0x18007931a  mov     rcx, [rdi+8]; String1
0x18007931e  lea     rdx, [rbx+18h]; String2
0x180079322  mov     r8b, 1; CaseInSensitive
0x180079325  call    cs:__imp_RtlCompareUnicodeString
0x18007932c  nop     dword ptr [rax+rax+00h]
0x180079331  mov     rbx, [rsp+28h+arg_0]
0x180079336  add     rsp, 20h
0x18007933a  pop     rdi
0x18007933b  retn
```
