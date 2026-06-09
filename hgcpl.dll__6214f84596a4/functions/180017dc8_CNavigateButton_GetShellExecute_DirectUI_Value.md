# CNavigateButton::GetShellExecute(DirectUI::Value * *)

- ea: `0x180017dc8`
- end: `0x180017df7`
- name: `?GetShellExecute@CNavigateButton@@QEAAPEBGPEAPEAVValue@DirectUI@@@Z`
- size: `47`
- prototype: `const unsigned __int16 *__fastcall(CNavigateButton *__hidden this, struct DirectUI::Value **)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting, installer_update`

## callers

- `0x180018020`
- `0x1800183e4`

## import_xrefs

- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180017ddf`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180017ddf`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x180017df0`

## pseudocode

```c
const unsigned __int16 *__fastcall CNavigateButton::GetShellExecute(CNavigateButton *this, struct DirectUI::Value **a2)
{
  struct DirectUI::Value *Value; // rax

  Value = DirectUI::Element::GetValue(this, (const struct DirectUI::PropertyInfo *)&off_18001C1F0, 2, 0);
  *a2 = Value;
  return DirectUI::Value::GetString(Value);
}

```

## disassembly

```asm
0x180017dc8  push    rbx
0x180017dca  sub     rsp, 20h
0x180017dce  xor     r9d, r9d
0x180017dd1  mov     rbx, rdx
0x180017dd4  lea     rdx, off_18001C1F0; "ShellExecute"
0x180017ddb  lea     r8d, [r9+2]
0x180017ddf  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180017de5  mov     rcx, rax
0x180017de8  mov     [rbx], rax
0x180017deb  add     rsp, 20h
0x180017def  pop     rbx
0x180017df0  jmp     cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
```
