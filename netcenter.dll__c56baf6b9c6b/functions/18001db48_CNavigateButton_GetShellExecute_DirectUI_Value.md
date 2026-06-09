# CNavigateButton::GetShellExecute(DirectUI::Value * *)

- ea: `0x18001db48`
- end: `0x18001db77`
- name: `?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z`
- size: `47`
- prototype: `const unsigned __int16 *__fastcall(CNavigateButton *__hidden this, struct DirectUI::Value **)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x18001dda0`
- `0x18001e16c`

## import_xrefs

- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18001db70`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001db5f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001db5f`

## pseudocode

```c
const unsigned __int16 *__fastcall CNavigateButton::GetShellExecute(CNavigateButton *this, struct DirectUI::Value **a2)
{
  struct DirectUI::Value *Value; // rax

  Value = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_180025980, 2, 0);
  *a2 = Value;
  return DirectUI::Value::GetString(Value);
}

```

## disassembly

```asm
0x18001db48  push    rbx
0x18001db4a  sub     rsp, 20h
0x18001db4e  xor     r9d, r9d
0x18001db51  mov     rbx, rdx
0x18001db54  lea     rdx, off_180025980; "ShellExecute"
0x18001db5b  lea     r8d, [r9+2]
0x18001db5f  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001db65  mov     rcx, rax
0x18001db68  mov     [rbx], rax
0x18001db6b  add     rsp, 20h
0x18001db6f  pop     rbx
0x18001db70  jmp     cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
```
