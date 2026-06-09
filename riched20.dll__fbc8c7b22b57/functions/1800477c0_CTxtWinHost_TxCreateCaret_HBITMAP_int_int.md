# CTxtWinHost::TxCreateCaret(HBITMAP__ *,int,int)

- ea: `0x1800477c0`
- end: `0x1800477cb`
- name: `?TxCreateCaret@CTxtWinHost@@UEAAHPEAUHBITMAP__@@HH@Z`
- size: `11`
- prototype: `__int64 __fastcall(CTxtWinHost *__hidden this, HBITMAP, int, int)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `USER32!CreateCaret` at `0x1800477c4`

## pseudocode

```c
BOOL __fastcall CTxtWinHost::TxCreateCaret(HWND *this, HBITMAP a2, int a3, int a4)
{
  return CreateCaret(this[2], a2, a3, a4);
}

```

## disassembly

```asm
0x1800477c0  mov     rcx, [rcx+10h]
0x1800477c4  jmp     cs:__imp_CreateCaret
```
