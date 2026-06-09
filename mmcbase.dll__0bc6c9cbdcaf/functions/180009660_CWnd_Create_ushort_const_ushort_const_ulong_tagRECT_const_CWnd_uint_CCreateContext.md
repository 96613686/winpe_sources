# CWnd::Create(ushort const *,ushort const *,ulong,tagRECT const &,CWnd *,uint,CCreateContext *)

- ea: `0x180009660`
- end: `0x180009666`
- name: `?Create@CWnd@@UEAAHPEBG0KAEBUtagRECT@@PEAV1@IPEAUCCreateContext@@@Z_0`
- size: `6`
- prototype: `int(CWnd *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const struct tagRECT *, struct CWnd *, unsigned int, struct CCreateContext *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `MFC42u!__imp_?Create@CWnd@@UEAAHPEBG0KAEBUtagRECT@@PEAV1@IPEAUCCreateContext@@@Z` at `0x180009660`

## pseudocode

```c
// attributes: thunk
int __fastcall CWnd::Create(
        CWnd *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned int a4,
        const struct tagRECT *a5,
        struct CWnd *a6,
        unsigned int a7,
        struct CCreateContext *a8)
{
  return __imp_?Create@CWnd@@UEAAHPEBG0KAEBUtagRECT@@PEAV1@IPEAUCCreateContext@@@Z(this, a2, a3, a4, a5, a6, a7, a8);
}

```

## disassembly

```asm
0x180009660  jmp     cs:__imp_?Create@CWnd@@UEAAHPEBG0KAEBUtagRECT@@PEAV1@IPEAUCCreateContext@@@Z
```
