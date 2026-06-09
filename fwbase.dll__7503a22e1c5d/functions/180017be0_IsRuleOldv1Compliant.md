# IsRuleOldv1Compliant

- ea: `0x180017be0`
- end: `0x180017c19`
- name: `IsRuleOldv1Compliant`
- size: `57`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d490`

## callees

- `0x1800119f0`
- `0x180017be0`

## pseudocode

```c
_BOOL8 __fastcall IsRuleOldv1Compliant(_DWORD *a1)
{
  return IsRuleOpenPortOrAuthApp((__int64)a1) && !a1[54] && !a1[50] && a1[58] == 0;
}

```

## disassembly

```asm
0x180017be0  push    rbx
0x180017be2  sub     rsp, 20h
0x180017be6  mov     rbx, rcx
0x180017be9  call    IsRuleOpenPortOrAuthApp
0x180017bee  xor     ecx, ecx
0x180017bf0  test    eax, eax
0x180017bf2  jz      short loc_180017C11
0x180017bf4  cmp     [rbx+0D8h], ecx
0x180017bfa  jnz     short loc_180017C11
0x180017bfc  cmp     [rbx+0C8h], ecx
0x180017c02  jnz     short loc_180017C11
0x180017c04  cmp     [rbx+0E8h], ecx
0x180017c0a  mov     eax, ecx
0x180017c0c  setz    al
0x180017c0f  jmp     short loc_180017C13
0x180017c11  xor     eax, eax
0x180017c13  add     rsp, 20h
0x180017c17  pop     rbx
0x180017c18  retn
```
