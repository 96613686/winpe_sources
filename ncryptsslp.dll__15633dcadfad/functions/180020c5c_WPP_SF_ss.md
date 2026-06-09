# WPP_SF_ss

- ea: `0x180020c5c`
- end: `0x180020cad`
- name: `WPP_SF_ss`
- size: `81`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000c1c0`

## import_xrefs

- `ntdll!EtwTraceMessage` at `0x180020ca2`
- `ntdll!EtwTraceMessage` at `0x180020ca2`

## string_xrefs

- `0x180020c8b`: `onecore\ds\security\cryptoapi\ncrypt\schannel\tls1key.c`

## pseudocode

```c
__int64 __fastcall WPP_SF_ss(__int64 a1)
{
  return EtwTraceMessage(a1, 43, WPP_0aae2d7063e33980f065131f19c85098_Traceguids);
}

```

## disassembly

```asm
0x180020c5c  mov     r11, rsp
0x180020c5f  sub     rsp, 58h
0x180020c63  mov     qword ptr [r11-18h], 0
0x180020c6b  lea     rax, aTlsencryptpack; "TlsEncryptPacket"
0x180020c72  mov     qword ptr [r11-20h], 11h
0x180020c7a  lea     r8, WPP_0aae2d7063e33980f065131f19c85098_Traceguids
0x180020c81  mov     [r11-28h], rax
0x180020c85  mov     r9d, 1Ch
0x180020c8b  lea     rax, aOnecoreDsSecur_4; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180020c92  mov     qword ptr [r11-30h], 38h ; '8'
0x180020c9a  mov     [r11-38h], rax
0x180020c9e  lea     edx, [r9+0Fh]
0x180020ca2  call    cs:__imp_EtwTraceMessage
0x180020ca8  add     rsp, 58h
0x180020cac  retn
```
