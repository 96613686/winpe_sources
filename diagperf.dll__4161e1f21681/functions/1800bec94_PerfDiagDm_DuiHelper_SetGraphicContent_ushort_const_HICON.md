# PerfDiagDm::DuiHelper::SetGraphicContent(ushort const *,HICON__ *)

- ea: `0x1800bec94`
- end: `0x1800bed59`
- name: `?SetGraphicContent@DuiHelper@PerfDiagDm@@QEAAJPEBGPEAUHICON__@@@Z`
- size: `197`
- prototype: `__int64 __fastcall(PerfDiagDm::DuiHelper *__hidden this, const unsigned __int16 *, HICON)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800bdb90`
- `0x1800bdf10`

## callees

- `0x1800bec94`

## import_xrefs

- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x1800bed01`
- `DUI70!?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z` at `0x1800bed01`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800bed2b`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800bed2b`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800beccc`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800beccc`
- `DUI70!StrToID` at `0x1800becc0`
- `DUI70!StrToID` at `0x1800becc0`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1800bed40`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1800bed40`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800becef`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x1800becef`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800bed18`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800bed22`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x1800bed22`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PerfDiagDm::DuiHelper::SetGraphicContent(
        DirectUI::Element **this,
        const unsigned __int16 *a2,
        HICON a3)
{
  DirectUI::Element *v4; // rdi
  unsigned int v6; // ebx
  unsigned __int16 v7; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Element *v9; // rdi
  struct DirectUI::Value *Graphic; // rax
  DirectUI::Value *v11; // rsi
  DirectUI::Element *v12; // [rsp+20h] [rbp-18h]
  unsigned int v13[4]; // [rsp+28h] [rbp-10h] BYREF

  v4 = *this;
  if ( !*this )
    return 2147500037LL;
  v6 = -2147467259;
  v7 = StrToID(a2);
  Descendent = DirectUI::Element::FindDescendent(v4, v7);
  v9 = Descendent;
  if ( Descendent )
  {
    v12 = Descendent;
    v13[0] = 0;
    DirectUI::Element::StartDefer(Descendent, v13);
    Graphic = DirectUI::Value::CreateGraphic(a3, 0, 0, 0);
    v11 = Graphic;
    if ( Graphic )
    {
      DirectUI::Element::SetValue(
        v9,
        (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
        1,
        Graphic);
      DirectUI::Value::Release(v11);
      v6 = 0;
    }
    if ( v13[0] )
      DirectUI::Element::EndDefer(v12, v13[0]);
  }
  return v6;
}

```

## disassembly

```asm
0x1800bec94  mov     [rsp+arg_0], rbx
0x1800bec99  mov     [rsp+arg_8], rsi
0x1800bec9e  push    rdi
0x1800bec9f  sub     rsp, 30h
0x1800beca3  mov     rsi, r8
0x1800beca6  mov     rdi, [rcx]
0x1800beca9  test    rdi, rdi
0x1800becac  jnz     short loc_1800BECB8
0x1800becae  mov     eax, 80004005h
0x1800becb3  jmp     loc_1800BED49
0x1800becb8  mov     ebx, 80004005h
0x1800becbd  mov     rcx, rdx
0x1800becc0  call    cs:__imp_StrToID
0x1800becc6  movzx   edx, ax
0x1800becc9  mov     rcx, rdi
0x1800beccc  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800becd2  mov     rdi, rax
0x1800becd5  test    rax, rax
0x1800becd8  jz      short loc_1800BED47
0x1800becda  mov     [rsp+38h+var_18], rax
0x1800becdf  mov     [rsp+38h+var_10], 0
0x1800bece7  lea     rdx, [rsp+38h+var_10]
0x1800becec  mov     rcx, rax
0x1800becef  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x1800becf5  nop
0x1800becf6  xor     r9d, r9d
0x1800becf9  xor     r8d, r8d
0x1800becfc  xor     edx, edx
0x1800becfe  mov     rcx, rsi
0x1800bed01  call    cs:__imp_?CreateGraphic@Value@DirectUI@@SAPEAV12@PEAUHICON__@@_N11@Z; DirectUI::Value::CreateGraphic(HICON__ *,bool,bool,bool)
0x1800bed07  mov     rsi, rax
0x1800bed0a  test    rax, rax
0x1800bed0d  jz      short loc_1800BED33
0x1800bed0f  mov     r9, rax
0x1800bed12  mov     r8d, 1
0x1800bed18  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x1800bed1f  mov     rcx, rdi
0x1800bed22  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x1800bed28  mov     rcx, rsi
0x1800bed2b  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800bed31  xor     ebx, ebx
0x1800bed33  mov     edx, [rsp+38h+var_10]
0x1800bed37  test    edx, edx
0x1800bed39  jz      short loc_1800BED47
0x1800bed3b  mov     rcx, [rsp+38h+var_18]
0x1800bed40  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x1800bed46  nop
0x1800bed47  mov     eax, ebx
0x1800bed49  mov     rbx, [rsp+38h+arg_0]
0x1800bed4e  mov     rsi, [rsp+38h+arg_8]
0x1800bed53  add     rsp, 30h
0x1800bed57  pop     rdi
0x1800bed58  retn
```
