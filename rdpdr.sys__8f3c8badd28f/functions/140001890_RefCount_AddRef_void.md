# RefCount::AddRef(void)

- ea: `0x140001890`
- end: `0x140001895`
- name: `?AddRef@RefCount@@QEAAXXZ`
- size: `5`
- prototype: `void __fastcall(RefCount *__hidden this)`
- caller_count: `52`
- callee_count: `0`
- tags: ``

## callers

- `0x140011010`
- `0x1400113d0`
- `0x140012330`
- `0x1400125e0`
- `0x1400127a0`
- `0x1400131e0`
- `0x1400137c0`
- `0x140013e70`
- `0x140014360`
- `0x140014d50`
- `0x1400152a0`
- `0x1400154a0`
- `0x140015830`
- `0x140015c50`
- `0x140016130`
- `0x14001652c`
- `0x1400166b4`
- `0x14001b144`
- `0x14001d938`
- `0x14001e900`
- `0x14001ec90`
- `0x14001eeb0`
- `0x14001f710`
- `0x14001f900`
- `0x140020100`
- `0x140020788`
- `0x140020ab0`
- `0x1400227a0`
- `0x140022ab0`
- `0x140023cf0`
- `0x140024830`
- `0x140024a50`
- `0x140024cf0`
- `0x140025000`
- `0x1400254c0`
- `0x140025c40`
- `0x140026380`
- `0x1400268e0`
- `0x140026c18`
- `0x140027190`
- `0x140027c10`
- `0x140027f30`
- `0x140027fe0`
- `0x140028ec0`
- `0x140028f80`
- `0x140029c90`
- `0x14002a9c0`
- `0x14002ab90`
- `0x14002b120`
- `0x14002b530`

## pseudocode

```c
void __fastcall RefCount::AddRef(RefCount *this)
{
  _InterlockedIncrement((volatile signed __int32 *)this + 4);
}

```

## disassembly

```asm
0x140001890  lock inc dword ptr [rcx+10h]
0x140001894  retn
```
