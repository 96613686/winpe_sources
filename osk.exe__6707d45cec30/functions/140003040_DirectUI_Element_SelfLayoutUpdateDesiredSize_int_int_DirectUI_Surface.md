# DirectUI::Element::_SelfLayoutUpdateDesiredSize(int,int,DirectUI::Surface *)

- ea: `0x140003040`
- end: `0x140003046`
- name: `?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z_0`
- size: `6`
- prototype: `struct tagSIZE(DirectUI::Element *__hidden this, int, int, struct DirectUI::Surface *)`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## import_xrefs

- `DUI70!?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x140003040`

## pseudocode

```c
// attributes: thunk
struct tagSIZE __fastcall DirectUI::Element::_SelfLayoutUpdateDesiredSize(
        DirectUI::Element *this,
        int a2,
        int a3,
        struct DirectUI::Surface *a4)
{
  return __imp_?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z(this, a2, a3, a4);
}

```

## disassembly

```asm
0x140003040  jmp     cs:__imp_?_SelfLayoutUpdateDesiredSize@Element@DirectUI@@MEAA?AUtagSIZE@@HHPEAVSurface@2@@Z
```
