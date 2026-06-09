# PrjfRBComparePathNodes

- ea: `0x1400455d8`
- end: `0x140045653`
- name: `PrjfRBComparePathNodes`
- size: `123`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140044cec`
- `0x1400453bc`

## callees

- `0x1400455d8`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400455fa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140045619`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400455fa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x140045619`

## pseudocode

```c
__int64 __fastcall PrjfRBComparePathNodes(__int64 a1, __int64 a2)
{
  const UNICODE_STRING *v2; // rdi
  const UNICODE_STRING *v3; // rsi
  char v4; // bl
  LONG v5; // eax
  LONG v6; // ecx

  v2 = *(const UNICODE_STRING **)a1;
  v3 = (const UNICODE_STRING *)(a2 + 24);
  v4 = *(_BYTE *)(a1 + 8);
  v5 = RtlCompareUnicodeString(*(PCUNICODE_STRING *)a1, (PCUNICODE_STRING)(a2 + 24), 1u);
  if ( v5 >= 0 )
  {
    if ( v5 > 0 )
      return 1;
    if ( v4 )
      return 0;
    v6 = RtlCompareUnicodeString(v2, v3, 0);
    if ( v6 >= 0 )
      return v6 > 0;
  }
  return 0xFFFFFFFFLL;
}

```

## disassembly

```asm
0x1400455d8  mov     [rsp+arg_0], rbx
0x1400455dd  mov     [rsp+arg_8], rsi
0x1400455e2  push    rdi
0x1400455e3  sub     rsp, 20h
0x1400455e7  mov     rdi, [rcx]
0x1400455ea  lea     rsi, [rdx+18h]
0x1400455ee  mov     bl, [rcx+8]
0x1400455f1  mov     rdx, rsi; String2
0x1400455f4  mov     rcx, rdi; String1
0x1400455f7  mov     r8b, 1; CaseInSensitive
0x1400455fa  call    cs:__imp_RtlCompareUnicodeString
0x140045601  nop     dword ptr [rax+rax+00h]
0x140045606  test    eax, eax
0x140045608  js      short loc_14004563F
0x14004560a  jg      short loc_140045638
0x14004560c  test    bl, bl
0x14004560e  jnz     short loc_140045634
0x140045610  xor     r8d, r8d; CaseInSensitive
0x140045613  mov     rdx, rsi; String2
0x140045616  mov     rcx, rdi; String1
0x140045619  call    cs:__imp_RtlCompareUnicodeString
0x140045620  nop     dword ptr [rax+rax+00h]
0x140045625  mov     ecx, eax
0x140045627  test    eax, eax
0x140045629  js      short loc_14004563F
0x14004562b  xor     eax, eax
0x14004562d  test    ecx, ecx
0x14004562f  setnle  al
0x140045632  jmp     short loc_140045642
0x140045634  xor     eax, eax
0x140045636  jmp     short loc_140045642
0x140045638  mov     eax, 1
0x14004563d  jmp     short loc_140045642
0x14004563f  or      eax, 0FFFFFFFFh
0x140045642  mov     rbx, [rsp+28h+arg_0]
0x140045647  mov     rsi, [rsp+28h+arg_8]
0x14004564c  add     rsp, 20h
0x140045650  pop     rdi
0x140045651  retn
```
