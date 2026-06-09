# _guard_dispatch_icall

- ea: `0x1400372d0`
- end: `0x1400372d6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `186`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001008`
- `0x140001230`
- `0x140001cb4`
- `0x140001dcc`
- `0x140001f04`
- `0x140002130`
- `0x140002504`
- `0x140003840`
- `0x140004600`
- `0x140004630`
- `0x140004904`
- `0x140005cc0`
- `0x140006a70`
- `0x140007b00`
- `0x140009030`
- `0x14000919c`
- `0x14000a254`
- `0x14000c010`
- `0x14000c0b0`
- `0x14000c730`
- `0x14000ca00`
- `0x14000cb44`
- `0x14000d63c`
- `0x14000dfd0`
- `0x14000e210`
- `0x14000e35c`
- `0x14000e420`
- `0x14000e580`
- `0x14000e880`
- `0x14000f370`
- `0x14000fdb0`
- `0x140010670`
- `0x140010850`
- `0x140010c2c`
- `0x1400111a0`
- `0x140011510`
- `0x1400129cc`
- `0x140012dc4`
- `0x140012f10`
- `0x1400132d0`
- `0x140013db0`
- `0x140013f60`
- `0x1400140c0`
- `0x140014338`
- `0x1400148e0`
- `0x140014ab0`
- `0x140014cb0`
- `0x140014e40`
- `0x140015130`
- `0x140015570`

## callees

- `0x140037270`

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
0x1400372d0  jmp     cs:__guard_dispatch_icall_fptr
```
