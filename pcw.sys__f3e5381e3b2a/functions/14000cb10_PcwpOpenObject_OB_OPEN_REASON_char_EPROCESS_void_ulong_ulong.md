# PcwpOpenObject(_OB_OPEN_REASON,char,_EPROCESS *,void *,ulong *,ulong)

- ea: `0x14000cb10`
- end: `0x14000cb1a`
- name: `?PcwpOpenObject@@YAJW4_OB_OPEN_REASON@@DPEAU_EPROCESS@@PEAXPEAKK@Z`
- size: `10`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
__int64 __fastcall PcwpOpenObject(int a1)
{
  return a1 != 0 ? 0xC00000BB : 0;
}

```

## disassembly

```asm
0x14000cb10  neg     ecx
0x14000cb12  sbb     eax, eax
0x14000cb14  and     eax, 0C00000BBh
0x14000cb19  retn
```
