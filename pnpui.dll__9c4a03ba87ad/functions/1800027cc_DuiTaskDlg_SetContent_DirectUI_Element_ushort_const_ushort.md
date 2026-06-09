# DuiTaskDlg::_SetContent(DirectUI::Element *,ushort const *,ushort *)

- ea: `0x1800027cc`
- end: `0x18000282f`
- name: `?_SetContent@DuiTaskDlg@@IEAAJPEAVElement@DirectUI@@PEBGPEAG@Z`
- size: `99`
- prototype: `int(DuiTaskDlg *__hidden this, struct DirectUI::Element *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x1800036a0`

## callees

- `0x1800027cc`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18000281c`
- `OLEAUT32!__imp_SysFreeString` at `0x18000281c`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000280a`
- `DUI70!?SetVisible@Element@DirectUI@@QEAAJ_N@Z` at `0x18000280a`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800027ff`
- `DUI70!?SetContentString@Element@DirectUI@@QEAAJPEBG@Z` at `0x1800027ff`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800027eb`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800027eb`
- `DUI70!StrToID` at `0x1800027df`
- `DUI70!StrToID` at `0x1800027df`

## pseudocode

```c
__int64 __fastcall DuiTaskDlg::_SetContent(
        DuiTaskDlg *this,
        struct DirectUI::Element *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 v6; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v8; // rbx
  unsigned int v9; // ebx

  v6 = StrToID(a3, a2, a3);
  Descendent = DirectUI::Element::FindDescendent(a2, v6);
  v8 = Descendent;
  if ( Descendent )
  {
    DirectUI::Element::SetContentString(Descendent, a4);
    DirectUI::Element::SetVisible(v8, 1);
    v9 = 0;
  }
  else
  {
    v9 = -2147467259;
  }
  SysFreeString(a4);
  return v9;
}

```

## disassembly

```asm
0x1800027cc  mov     [rsp+arg_0], rbx
0x1800027d1  push    rdi
0x1800027d2  sub     rsp, 20h
0x1800027d6  mov     rcx, r8
0x1800027d9  mov     rdi, r9
0x1800027dc  mov     rbx, rdx
0x1800027df  call    cs:__imp_StrToID
0x1800027e5  movzx   edx, ax
0x1800027e8  mov     rcx, rbx
0x1800027eb  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800027f1  mov     rbx, rax
0x1800027f4  test    rax, rax
0x1800027f7  jz      short loc_180002814
0x1800027f9  mov     rdx, rdi
0x1800027fc  mov     rcx, rax
0x1800027ff  call    cs:__imp_?SetContentString@Element@DirectUI@@QEAAJPEBG@Z; DirectUI::Element::SetContentString(ushort const *)
0x180002805  mov     dl, 1
0x180002807  mov     rcx, rbx
0x18000280a  call    cs:__imp_?SetVisible@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::SetVisible(bool)
0x180002810  xor     ebx, ebx
0x180002812  jmp     short loc_180002819
0x180002814  mov     ebx, 80004005h
0x180002819  mov     rcx, rdi; bstrString
0x18000281c  call    cs:__imp_SysFreeString
0x180002822  mov     eax, ebx
0x180002824  mov     rbx, [rsp+28h+arg_0]
0x180002829  add     rsp, 20h
0x18000282d  pop     rdi
0x18000282e  retn
```
