# FltpAttachPolicyIsAltitudeInAvBand

- ea: `0x1800210d0`
- end: `0x180021145`
- name: `FltpAttachPolicyIsAltitudeInAvBand`
- size: `117`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Altitude2)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020300`

## callees

- `0x1800210d0`

## import_xrefs

- `ntoskrnl!RtlCompareAltitudes` at `0x180021100`
- `ntoskrnl!RtlCompareAltitudes` at `0x180021117`
- `ntoskrnl!RtlCompareAltitudes` at `0x180021100`
- `ntoskrnl!RtlCompareAltitudes` at `0x180021117`

## pseudocode

```c
__int64 __fastcall FltpAttachPolicyIsAltitudeInAvBand(PCUNICODE_STRING Altitude2)
{
  unsigned __int8 i; // bl

  for ( i = 0; i < 4u; ++i )
  {
    if ( RtlCompareAltitudes((PCUNICODE_STRING)&qword_1800284D0[4 * i], Altitude2) <= 0
      && RtlCompareAltitudes((PCUNICODE_STRING)&qword_1800284D0[4 * i + 2], Altitude2) >= 0 )
    {
      return 1;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800210d0  mov     [rsp+arg_0], rbx
0x1800210d5  mov     [rsp+arg_8], rsi
0x1800210da  push    rdi
0x1800210db  sub     rsp, 20h
0x1800210df  mov     rdi, rcx
0x1800210e2  xor     bl, bl
0x1800210e4  cmp     bl, 4
0x1800210e7  jnb     short loc_180021132
0x1800210e9  lea     rcx, qword_1800284D0
0x1800210f0  movzx   esi, bl
0x1800210f3  shl     rsi, 5
0x1800210f7  mov     rdx, rdi; Altitude2
0x1800210fa  add     rsi, rcx
0x1800210fd  mov     rcx, rsi; Altitude1
0x180021100  call    cs:__imp_RtlCompareAltitudes
0x180021107  nop     dword ptr [rax+rax+00h]
0x18002110c  test    eax, eax
0x18002110e  jg      short loc_180021127
0x180021110  lea     rcx, [rsi+10h]; Altitude1
0x180021114  mov     rdx, rdi; Altitude2
0x180021117  call    cs:__imp_RtlCompareAltitudes
0x18002111e  nop     dword ptr [rax+rax+00h]
0x180021123  test    eax, eax
0x180021125  jns     short loc_18002112B
0x180021127  inc     bl
0x180021129  jmp     short loc_1800210E4
0x18002112b  mov     eax, 1
0x180021130  jmp     short loc_180021134
0x180021132  xor     eax, eax
0x180021134  mov     rbx, [rsp+28h+arg_0]
0x180021139  mov     rsi, [rsp+28h+arg_8]
0x18002113e  add     rsp, 20h
0x180021142  pop     rdi
0x180021143  retn
```
