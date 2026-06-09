# CNavigateButton::GetShellExecute(DirectUI::Value * *)

- ea: `0x1800304a8`
- end: `0x1800304d7`
- name: `?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z`
- size: `47`
- prototype: `const unsigned __int16 *__fastcall(CNavigateButton *__hidden this, struct DirectUI::Value **)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x180030700`
- `0x180030acc`

## import_xrefs

- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x1800304d0`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800304bf`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x1800304bf`

## pseudocode

```c
const unsigned __int16 *__fastcall CNavigateButton::GetShellExecute(CNavigateButton *this, struct DirectUI::Value **a2)
{
  struct DirectUI::Value *Value; // rax

  Value = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_180035130, 2, 0);
  *a2 = Value;
  return DirectUI::Value::GetString(Value);
}

```

## disassembly

```asm
0x1800304a8  push    rbx
0x1800304aa  sub     rsp, 20h
0x1800304ae  xor     r9d, r9d
0x1800304b1  mov     rbx, rdx
0x1800304b4  lea     rdx, off_180035130; "ShellExecute"
0x1800304bb  lea     r8d, [r9+2]
0x1800304bf  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x1800304c5  mov     rcx, rax
0x1800304c8  mov     [rbx], rax
0x1800304cb  add     rsp, 20h
0x1800304cf  pop     rbx
0x1800304d0  jmp     cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
```
