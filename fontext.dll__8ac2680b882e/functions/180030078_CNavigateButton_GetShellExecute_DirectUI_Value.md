# CNavigateButton::GetShellExecute(DirectUI::Value * *)

- ea: `0x180030078`
- end: `0x1800300a7`
- name: `?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z`
- size: `47`
- prototype: `const unsigned __int16 *__fastcall(CNavigateButton *__hidden this, struct DirectUI::Value **)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x1800302c0`
- `0x180030684`

## import_xrefs

- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18003008f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18003008f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800300a0`

## pseudocode

```c
const unsigned __int16 *__fastcall CNavigateButton::GetShellExecute(CNavigateButton *this, struct DirectUI::Value **a2)
{
  struct DirectUI::Value *Value; // rax

  Value = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_1800351D0, 2, 0);
  *a2 = Value;
  return DirectUI::Value::GetString(Value);
}

```

## disassembly

```asm
0x180030078  push    rbx
0x18003007a  sub     rsp, 20h
0x18003007e  xor     r9d, r9d
0x180030081  mov     rbx, rdx
0x180030084  lea     rdx, off_1800351D0; "ShellExecute"
0x18003008b  lea     r8d, [r9+2]
0x18003008f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180030095  mov     rcx, rax
0x180030098  mov     [rbx], rax
0x18003009b  add     rsp, 20h
0x18003009f  pop     rbx
0x1800300a0  jmp     cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
```
