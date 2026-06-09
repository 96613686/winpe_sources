# NativeMsh::WinSystemCallFacade::_wfopen(ushort const *,ushort const *)

- ea: `0x180009550`
- end: `0x18000955d`
- name: `?_wfopen@WinSystemCallFacade@NativeMsh@@UEAAPEAU_iobuf@@PEBG0@Z`
- size: `13`
- prototype: `struct _iobuf *__fastcall(NativeMsh::WinSystemCallFacade *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcrt!_wfopen` at `0x180009556`

## pseudocode

```c
struct _iobuf *__fastcall NativeMsh::WinSystemCallFacade::_wfopen(
        NativeMsh::WinSystemCallFacade *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  return _wfopen(a2, a3);
}

```

## disassembly

```asm
0x180009550  mov     rcx, rdx
0x180009553  mov     rdx, r8
0x180009556  jmp     cs:__imp__wfopen
```
