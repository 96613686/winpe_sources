# DUIFramework_SetFocusByFocusIndicator(DirectUI::Element *)

- ea: `0x18002ea14`
- end: `0x18002eaf4`
- name: `?DUIFramework_SetFocusByFocusIndicator@@YAJPEAVElement@DirectUI@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002e5f0`

## callees

- `0x18002ea14`
- `0x180032010`

## import_xrefs

- `DUI70!StrToID` at `0x18002ea2c`
- `DUI70!StrToID` at `0x18002ea2c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002ea38`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002ea7c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002ea38`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002ea7c`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x18002eaa4`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x18002eaa4`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002ea70`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002ea70`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002ea58`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002ea58`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18002ea64`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18002ea64`

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
    Value = DirectUI::Element::GetValue(Descendent, (const struct DirectUI::PropertyInfo *)&off_180046440, 2, 0);
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
0x18002ea14  push    rbx
0x18002ea16  push    rbp
0x18002ea17  push    rsi
0x18002ea18  push    rdi
0x18002ea19  sub     rsp, 58h
0x18002ea1d  mov     rsi, rcx
0x18002ea20  mov     ebp, 80004005h
0x18002ea25  lea     rcx, aFocusindicator; "FocusIndicator"
0x18002ea2c  call    cs:__imp_StrToID
0x18002ea32  movzx   edx, ax
0x18002ea35  mov     rcx, rsi
0x18002ea38  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002ea3e  test    rax, rax
0x18002ea41  jz      loc_18002EAE9
0x18002ea47  xor     r9d, r9d
0x18002ea4a  lea     rdx, off_180046440; "firsttabtarget"
0x18002ea51  mov     rcx, rax
0x18002ea54  lea     r8d, [r9+2]
0x18002ea58  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002ea5e  mov     rcx, rax
0x18002ea61  mov     rdi, rax
0x18002ea64  call    cs:__imp_?GetAtom@Value@DirectUI@@QEAAGXZ; DirectUI::Value::GetAtom(void)
0x18002ea6a  mov     rcx, rdi
0x18002ea6d  movzx   ebx, ax
0x18002ea70  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002ea76  movzx   edx, bx
0x18002ea79  mov     rcx, rsi
0x18002ea7c  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002ea82  mov     rbx, rax
0x18002ea85  test    rax, rax
0x18002ea88  jz      short loc_18002EAE9
0x18002ea8a  xorps   xmm0, xmm0
0x18002ea8d  lea     rcx, [rsp+78h+var_48]
0x18002ea92  xor     eax, eax
0x18002ea94  xor     r8d, r8d
0x18002ea97  mov     rdx, rbx
0x18002ea9a  mov     [rsp+78h+var_38], rax
0x18002ea9f  movups  [rsp+78h+var_48], xmm0
0x18002eaa4  call    cs:__imp_?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z; DirectUI::NavReference::Init(DirectUI::Element *,tagRECT *)
0x18002eaaa  mov     rax, [rbx]
0x18002eaad  lea     r9, [rsp+78h+var_48]
0x18002eab2  mov     r8d, 3
0x18002eab8  xor     edx, edx
0x18002eaba  mov     rcx, rbx
0x18002eabd  mov     [rsp+78h+var_58], r8d
0x18002eac2  mov     rax, [rax+98h]
0x18002eac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eace  test    rax, rax
0x18002ead1  cmovnz  rbx, rax
0x18002ead5  mov     rcx, rbx
0x18002ead8  mov     rax, [rbx]
0x18002eadb  mov     rax, [rax+0A8h]
0x18002eae2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eae7  xor     ebp, ebp
0x18002eae9  mov     eax, ebp
0x18002eaeb  add     rsp, 58h
0x18002eaef  pop     rdi
0x18002eaf0  pop     rsi
0x18002eaf1  pop     rbp
0x18002eaf2  pop     rbx
0x18002eaf3  retn
```
