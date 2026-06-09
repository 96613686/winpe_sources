# NotifyDnsCache

- ea: `0x180005b88`
- end: `0x180005bc5`
- name: `NotifyDnsCache`
- size: `61`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x1800058ec`
- `0x180011b98`
- `0x18001225c`
- `0x18001c0e4`

## callees

- `0x180005b88`
- `0x180033900`

## import_xrefs

- `DNSAPI!DnsNotifyResolver` at `0x180005b99`
- `DNSAPI!DnsNotifyResolver` at `0x180005b99`

## pseudocode

```c
__int64 NotifyDnsCache()
{
  if ( (xmmword_1800423E0 & 0x10) != 0 )
    WPP_SF_(1028, 10, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids);
  DnsNotifyResolver(0, 0);
  return 0;
}

```

## disassembly

```asm
0x180005b88  sub     rsp, 28h
0x180005b8c  test    byte ptr cs:xmmword_1800423E0, 10h
0x180005b93  jnz     short loc_180005BAD
0x180005b95  xor     edx, edx
0x180005b97  xor     ecx, ecx
0x180005b99  call    cs:__imp_DnsNotifyResolver
0x180005ba0  nop     dword ptr [rax+rax+00h]
0x180005ba5  xor     eax, eax
0x180005ba7  add     rsp, 28h
0x180005bab  retn
0x180005bad  mov     edx, 0Ah
0x180005bb2  lea     r8, WPP_4e6e54b810c33d13f196fe59d5e6619d_Traceguids
0x180005bb9  mov     ecx, 404h
0x180005bbe  call    WPP_SF_
0x180005bc3  jmp     short loc_180005B95
```
