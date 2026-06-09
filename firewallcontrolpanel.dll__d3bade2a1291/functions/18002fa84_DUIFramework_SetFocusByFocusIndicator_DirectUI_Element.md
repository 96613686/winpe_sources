# DUIFramework_SetFocusByFocusIndicator(DirectUI::Element *)

- ea: `0x18002fa84`
- end: `0x18002fb64`
- name: `?DUIFramework_SetFocusByFocusIndicator@@YAJPEAVElement@DirectUI@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18002e8c0`

## callees

- `0x18002fa84`
- `0x180032010`

## import_xrefs

- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x18002fb14`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x18002fb14`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18002fad4`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18002fad4`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002fac8`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18002fac8`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002fae0`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18002fae0`
- `DUI70!StrToID` at `0x18002fa9c`
- `DUI70!StrToID` at `0x18002fa9c`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002faa8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002faec`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002faa8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x18002faec`

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
    Value = DirectUI::Element::GetValue(Descendent, (const struct DirectUI::PropertyInfo *)&off_180045258, 2, 0);
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
0x18002fa84  push    rbx
0x18002fa86  push    rbp
0x18002fa87  push    rsi
0x18002fa88  push    rdi
0x18002fa89  sub     rsp, 58h
0x18002fa8d  mov     rsi, rcx
0x18002fa90  mov     ebp, 80004005h
0x18002fa95  lea     rcx, aFocusindicator; "FocusIndicator"
0x18002fa9c  call    cs:__imp_StrToID
0x18002faa2  movzx   edx, ax
0x18002faa5  mov     rcx, rsi
0x18002faa8  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002faae  test    rax, rax
0x18002fab1  jz      loc_18002FB59
0x18002fab7  xor     r9d, r9d
0x18002faba  lea     rdx, off_180045258; "firsttabtarget"
0x18002fac1  mov     rcx, rax
0x18002fac4  lea     r8d, [r9+2]
0x18002fac8  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18002face  mov     rcx, rax
0x18002fad1  mov     rdi, rax
0x18002fad4  call    cs:__imp_?GetAtom@Value@DirectUI@@QEAAGXZ; DirectUI::Value::GetAtom(void)
0x18002fada  mov     rcx, rdi
0x18002fadd  movzx   ebx, ax
0x18002fae0  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18002fae6  movzx   edx, bx
0x18002fae9  mov     rcx, rsi
0x18002faec  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18002faf2  mov     rbx, rax
0x18002faf5  test    rax, rax
0x18002faf8  jz      short loc_18002FB59
0x18002fafa  xorps   xmm0, xmm0
0x18002fafd  lea     rcx, [rsp+78h+var_48]
0x18002fb02  xor     eax, eax
0x18002fb04  xor     r8d, r8d
0x18002fb07  mov     rdx, rbx
0x18002fb0a  mov     [rsp+78h+var_38], rax
0x18002fb0f  movups  [rsp+78h+var_48], xmm0
0x18002fb14  call    cs:__imp_?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z; DirectUI::NavReference::Init(DirectUI::Element *,tagRECT *)
0x18002fb1a  mov     rax, [rbx]
0x18002fb1d  lea     r9, [rsp+78h+var_48]
0x18002fb22  mov     r8d, 3
0x18002fb28  xor     edx, edx
0x18002fb2a  mov     rcx, rbx
0x18002fb2d  mov     [rsp+78h+var_58], r8d
0x18002fb32  mov     rax, [rax+98h]
0x18002fb39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb3e  test    rax, rax
0x18002fb41  cmovnz  rbx, rax
0x18002fb45  mov     rcx, rbx
0x18002fb48  mov     rax, [rbx]
0x18002fb4b  mov     rax, [rax+0A8h]
0x18002fb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002fb57  xor     ebp, ebp
0x18002fb59  mov     eax, ebp
0x18002fb5b  add     rsp, 58h
0x18002fb5f  pop     rdi
0x18002fb60  pop     rsi
0x18002fb61  pop     rbp
0x18002fb62  pop     rbx
0x18002fb63  retn
```
