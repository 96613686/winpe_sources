# DUIFramework_SetFocusByFocusIndicator(DirectUI::Element *)

- ea: `0x18001cacc`
- end: `0x18001cbac`
- name: `?DUIFramework_SetFocusByFocusIndicator@@YAJPEAVElement@DirectUI@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18001c280`

## callees

- `0x18001cacc`
- `0x180023010`

## import_xrefs

- `DUI70!StrToID` at `0x18001cae4`
- `DUI70!StrToID` at `0x18001cae4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001caf0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001cb34`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001caf0`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18001cb34`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cb28`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18001cb28`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x18001cb5c`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x18001cb5c`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18001cb1c`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18001cb1c`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cb10`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18001cb10`

## pseudocode

```c
__int64 __fastcall DUIFramework_SetFocusByFocusIndicator(struct DirectUI::Element *a1)
{
  unsigned int v2; // ebp
  unsigned __int16 v3; // ax
  DirectUI::Element *Descendent; // rax
  DirectUI::Value *Value; // rdi
  unsigned __int16 Atom; // bx
  struct DirectUI::Element *v7; // rbx
  __int64 v8; // rax
  __int128 v10; // [rsp+30h] [rbp-48h] BYREF
  __int64 v11; // [rsp+40h] [rbp-38h]

  v2 = -2147467259;
  v3 = StrToID(L"FocusIndicator");
  Descendent = DirectUI::Element::FindDescendent(a1, v3);
  if ( Descendent )
  {
    Value = DirectUI::Element::GetValue(Descendent, (const struct DirectUI::PropertyInfo *)&off_1800321A8, 2, 0);
    Atom = DirectUI::Value::GetAtom(Value);
    DirectUI::Value::Release(Value);
    v7 = DirectUI::Element::FindDescendent(a1, Atom);
    if ( v7 )
    {
      v11 = 0;
      v10 = 0;
      DirectUI::NavReference::Init((DirectUI::NavReference *)&v10, v7, 0);
      v8 = (*(__int64 (__fastcall **)(struct DirectUI::Element *, _QWORD, __int64, __int128 *, int))(*(_QWORD *)v7 + 152LL))(
             v7,
             0,
             3,
             &v10,
             3);
      if ( v8 )
        v7 = (struct DirectUI::Element *)v8;
      (*(void (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)v7 + 168LL))(v7);
      return 0;
    }
  }
  return v2;
}

```

## disassembly

```asm
0x18001cacc  push    rbx
0x18001cace  push    rbp
0x18001cacf  push    rsi
0x18001cad0  push    rdi
0x18001cad1  sub     rsp, 58h
0x18001cad5  mov     rsi, rcx
0x18001cad8  mov     ebp, 80004005h
0x18001cadd  lea     rcx, aFocusindicator; "FocusIndicator"
0x18001cae4  call    cs:__imp_StrToID
0x18001caea  movzx   edx, ax
0x18001caed  mov     rcx, rsi
0x18001caf0  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001caf6  test    rax, rax
0x18001caf9  jz      loc_18001CBA1
0x18001caff  xor     r9d, r9d
0x18001cb02  lea     rdx, off_1800321A8; "firsttabtarget"
0x18001cb09  mov     rcx, rax
0x18001cb0c  lea     r8d, [r9+2]
0x18001cb10  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18001cb16  mov     rcx, rax
0x18001cb19  mov     rdi, rax
0x18001cb1c  call    cs:__imp_?GetAtom@Value@DirectUI@@QEAAGXZ; DirectUI::Value::GetAtom(void)
0x18001cb22  mov     rcx, rdi
0x18001cb25  movzx   ebx, ax
0x18001cb28  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001cb2e  movzx   edx, bx
0x18001cb31  mov     rcx, rsi
0x18001cb34  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001cb3a  mov     rbx, rax
0x18001cb3d  test    rax, rax
0x18001cb40  jz      short loc_18001CBA1
0x18001cb42  xorps   xmm0, xmm0
0x18001cb45  lea     rcx, [rsp+78h+var_48]
0x18001cb4a  xor     eax, eax
0x18001cb4c  xor     r8d, r8d
0x18001cb4f  mov     rdx, rbx
0x18001cb52  mov     [rsp+78h+var_38], rax
0x18001cb57  movups  [rsp+78h+var_48], xmm0
0x18001cb5c  call    cs:__imp_?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z; DirectUI::NavReference::Init(DirectUI::Element *,tagRECT *)
0x18001cb62  mov     rax, [rbx]
0x18001cb65  lea     r9, [rsp+78h+var_48]
0x18001cb6a  mov     r8d, 3
0x18001cb70  xor     edx, edx
0x18001cb72  mov     rcx, rbx
0x18001cb75  mov     [rsp+78h+var_58], r8d
0x18001cb7a  mov     rax, [rax+98h]
0x18001cb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb86  test    rax, rax
0x18001cb89  cmovnz  rbx, rax
0x18001cb8d  mov     rcx, rbx
0x18001cb90  mov     rax, [rbx]
0x18001cb93  mov     rax, [rax+0A8h]
0x18001cb9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb9f  xor     ebp, ebp
0x18001cba1  mov     eax, ebp
0x18001cba3  add     rsp, 58h
0x18001cba7  pop     rdi
0x18001cba8  pop     rsi
0x18001cba9  pop     rbp
0x18001cbaa  pop     rbx
0x18001cbab  retn
```
