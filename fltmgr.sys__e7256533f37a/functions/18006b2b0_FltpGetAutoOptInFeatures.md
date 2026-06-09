# FltpGetAutoOptInFeatures

- ea: `0x18006b2b0`
- end: `0x18006b32e`
- name: `FltpGetAutoOptInFeatures`
- size: `126`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Altitude2)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18006aef0`

## callees

- `0x18006b2b0`

## import_xrefs

- `ntoskrnl!RtlCompareAltitudes` at `0x18006b2e4`
- `ntoskrnl!RtlCompareAltitudes` at `0x18006b2fb`
- `ntoskrnl!RtlCompareAltitudes` at `0x18006b2e4`
- `ntoskrnl!RtlCompareAltitudes` at `0x18006b2fb`

## pseudocode

```c
__int64 __fastcall FltpGetAutoOptInFeatures(PCUNICODE_STRING Altitude2)
{
  unsigned int i; // ebx

  for ( i = 0; ; ++i )
  {
    if ( i >= 0xD )
      return 4;
    if ( RtlCompareAltitudes((PCUNICODE_STRING)&qword_180028000[4 * i], Altitude2) <= 0
      && RtlCompareAltitudes((PCUNICODE_STRING)&qword_180028000[4 * i + 2], Altitude2) >= 0 )
    {
      break;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18006b2b0  mov     [rsp+arg_8], rbx
0x18006b2b5  mov     [rsp+arg_10], rbp
0x18006b2ba  push    rsi
0x18006b2bb  sub     rsp, 20h
0x18006b2bf  mov     rsi, rcx
0x18006b2c2  mov     [rsp+28h+arg_0], rdi
0x18006b2c7  xor     ebx, ebx
0x18006b2c9  lea     rbp, qword_180028000
0x18006b2d0  cmp     ebx, 0Dh
0x18006b2d3  jnb     short loc_18006B30F
0x18006b2d5  mov     edi, ebx
0x18006b2d7  mov     rdx, rsi; Altitude2
0x18006b2da  shl     rdi, 5
0x18006b2de  add     rdi, rbp
0x18006b2e1  mov     rcx, rdi; Altitude1
0x18006b2e4  call    cs:__imp_RtlCompareAltitudes
0x18006b2eb  nop     dword ptr [rax+rax+00h]
0x18006b2f0  test    eax, eax
0x18006b2f2  jg      short loc_18006B30B
0x18006b2f4  lea     rcx, [rdi+10h]; Altitude1
0x18006b2f8  mov     rdx, rsi; Altitude2
0x18006b2fb  call    cs:__imp_RtlCompareAltitudes
0x18006b302  nop     dword ptr [rax+rax+00h]
0x18006b307  test    eax, eax
0x18006b309  jns     short loc_18006B32A
0x18006b30b  inc     ebx
0x18006b30d  jmp     short loc_18006B2D0
0x18006b30f  mov     eax, 4
0x18006b314  mov     rdi, [rsp+28h+arg_0]
0x18006b319  mov     rbx, [rsp+28h+arg_8]
0x18006b31e  mov     rbp, [rsp+28h+arg_10]
0x18006b323  add     rsp, 20h
0x18006b327  pop     rsi
0x18006b328  retn
0x18006b32a  xor     eax, eax
0x18006b32c  jmp     short loc_18006B314
```
