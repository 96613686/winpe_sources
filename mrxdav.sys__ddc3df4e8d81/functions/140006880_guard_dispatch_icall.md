# _guard_dispatch_icall

- ea: `0x140006880`
- end: `0x140006886`
- name: `_guard_dispatch_icall`
- size: `6`
- prototype: ``
- caller_count: `62`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1400015f0`
- `0x14000163c`
- `0x140001680`
- `0x1400016d4`
- `0x140001770`
- `0x1400017e4`
- `0x140001838`
- `0x140001948`
- `0x140001978`
- `0x1400019bc`
- `0x140001a4c`
- `0x140001afc`
- `0x140001b64`
- `0x140001bc4`
- `0x1400025cc`
- `0x1400026a4`
- `0x1400027ac`
- `0x140002824`
- `0x1400028e4`
- `0x140002980`
- `0x140002a14`
- `0x140002ac4`
- `0x140002b60`
- `0x140002ea8`
- `0x140002f34`
- `0x140002fec`
- `0x140003064`
- `0x1400031b4`
- `0x140003310`
- `0x140003378`
- `0x1400033dc`
- `0x140003464`
- `0x1400034f4`
- `0x14000360c`
- `0x1400039b0`
- `0x140003a84`
- `0x140003f48`
- `0x140003ffc`
- `0x140004144`
- `0x140004dac`
- `0x1400059e4`
- `0x140005e30`
- `0x140005ee8`
- `0x140005f88`
- `0x14000603c`
- `0x140006460`
- `0x14000650c`
- `0x140006574`
- `0x140006640`
- `0x140008050`

## callees

- `0x140006820`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall guard_dispatch_icall()
{
  __int64 (*v0)(void); // rax

  return v0();
}

```

## disassembly

```asm
0x140006880  jmp     cs:__guard_dispatch_icall_fptr
```
