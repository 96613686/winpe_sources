# _guard_dispatch_icall

- ea: `0x140024bf0`
- end: `0x140024bf6`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `88`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x140001010`
- `0x140001c04`
- `0x140001c34`
- `0x140002fc0`
- `0x140003094`
- `0x1400033f0`
- `0x140003698`
- `0x140003994`
- `0x1400039e8`
- `0x140003a48`
- `0x140003b20`
- `0x140003d84`
- `0x140004cb4`
- `0x1400065d0`
- `0x1400069c8`
- `0x140006d50`
- `0x14000713c`
- `0x1400075d8`
- `0x140007790`
- `0x140007840`
- `0x140008d40`
- `0x140008ef0`
- `0x1400096b0`
- `0x14000b490`
- `0x14000b570`
- `0x14000b5d8`
- `0x14000b62c`
- `0x14000b698`
- `0x14000b6e4`
- `0x14000b730`
- `0x14000b7bc`
- `0x14000b820`
- `0x14000b88c`
- `0x14000b8e8`
- `0x14000b94c`
- `0x14000b9b4`
- `0x14000ba08`
- `0x14000baa0`
- `0x14000c580`
- `0x14000db70`
- `0x14001105c`
- `0x1400110d0`
- `0x140011158`
- `0x140011204`
- `0x140011f30`
- `0x140012754`
- `0x14001569c`
- `0x140017694`
- `0x140017884`
- `0x140017d9c`

## callees

- `0x140024c20`

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
0x140024bf0  jmp     cs:__guard_dispatch_icall_fptr
```
