# _guard_dispatch_icall

- ea: `0x140003a00`
- end: `0x140003a06`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `26`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001130`
- `0x140001570`
- `0x1400018d0`
- `0x140001ab0`
- `0x140001c60`
- `0x140001dd0`
- `0x140001f60`
- `0x1400020b0`
- `0x140002708`
- `0x140002a80`
- `0x140005050`
- `0x14000ecc0`
- `0x140010350`
- `0x140010f10`
- `0x1400119f4`
- `0x140012850`
- `0x140012a90`
- `0x140013fb0`
- `0x1400149e0`
- `0x140014bf0`
- `0x140014e00`
- `0x140014f30`
- `0x140015a48`
- `0x14001606c`
- `0x14001645c`
- `0x140017e44`

## callees

- `0x1400039a0`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (__fastcall *v0)(); // rax

  return v0();
}

```

## disassembly

```asm
0x140003a00  jmp     cs:__guard_dispatch_icall_fptr
```
