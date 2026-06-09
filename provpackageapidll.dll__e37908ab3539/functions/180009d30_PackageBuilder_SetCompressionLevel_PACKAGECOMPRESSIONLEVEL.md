# PackageBuilder::SetCompressionLevel(_PACKAGECOMPRESSIONLEVEL)

- ea: `0x180009d30`
- end: `0x180009d36`
- name: `?SetCompressionLevel@PackageBuilder@@EEAAJW4_PACKAGECOMPRESSIONLEVEL@@@Z`
- size: `6`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
__int64 __fastcall PackageBuilder::SetCompressionLevel(__int64 a1, int a2)
{
  *(_DWORD *)(a1 + 80) = a2;
  return 0;
}

```

## disassembly

```asm
0x180009d30  mov     [rcx+50h], edx
0x180009d33  xor     eax, eax
0x180009d35  retn
```
