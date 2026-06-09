# DUIFramework_SetFocusByFocusIndicator(DirectUI::Element *)

- ea: `0x18001602c`
- end: `0x18001610c`
- name: `?DUIFramework_SetFocusByFocusIndicator@@YAJPEAVElement@DirectUI@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(struct DirectUI::Element *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x180016f30`

## callees

- `0x18001602c`
- `0x18001a010`

## import_xrefs

- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016050`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016094`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016050`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x180016094`
- `DUI70!StrToID` at `0x180016044`
- `DUI70!StrToID` at `0x180016044`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180016088`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180016088`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x1800160bc`
- `DUI70!?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z` at `0x1800160bc`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180016070`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x180016070`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18001607c`
- `DUI70!?GetAtom@Value@DirectUI@@QEAAGXZ` at `0x18001607c`

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
    Value = DirectUI::Element::GetValue(Descendent, (const struct DirectUI::PropertyInfo *)&off_180029238, 2, 0);
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
0x18001602c  push    rbx
0x18001602e  push    rbp
0x18001602f  push    rsi
0x180016030  push    rdi
0x180016031  sub     rsp, 58h
0x180016035  mov     rsi, rcx
0x180016038  mov     ebp, 80004005h
0x18001603d  lea     rcx, aFocusindicator; "FocusIndicator"
0x180016044  call    cs:__imp_StrToID
0x18001604a  movzx   edx, ax
0x18001604d  mov     rcx, rsi
0x180016050  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x180016056  test    rax, rax
0x180016059  jz      loc_180016101
0x18001605f  xor     r9d, r9d
0x180016062  lea     rdx, off_180029238; "firsttabtarget"
0x180016069  mov     rcx, rax
0x18001606c  lea     r8d, [r9+2]
0x180016070  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x180016076  mov     rcx, rax
0x180016079  mov     rdi, rax
0x18001607c  call    cs:__imp_?GetAtom@Value@DirectUI@@QEAAGXZ; DirectUI::Value::GetAtom(void)
0x180016082  mov     rcx, rdi
0x180016085  movzx   ebx, ax
0x180016088  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18001608e  movzx   edx, bx
0x180016091  mov     rcx, rsi
0x180016094  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x18001609a  mov     rbx, rax
0x18001609d  test    rax, rax
0x1800160a0  jz      short loc_180016101
0x1800160a2  xorps   xmm0, xmm0
0x1800160a5  lea     rcx, [rsp+78h+var_48]
0x1800160aa  xor     eax, eax
0x1800160ac  xor     r8d, r8d
0x1800160af  mov     rdx, rbx
0x1800160b2  mov     [rsp+78h+var_38], rax
0x1800160b7  movups  [rsp+78h+var_48], xmm0
0x1800160bc  call    cs:__imp_?Init@NavReference@DirectUI@@QEAAXPEAVElement@2@PEAUtagRECT@@@Z; DirectUI::NavReference::Init(DirectUI::Element *,tagRECT *)
0x1800160c2  mov     rax, [rbx]
0x1800160c5  lea     r9, [rsp+78h+var_48]
0x1800160ca  mov     r8d, 3
0x1800160d0  xor     edx, edx
0x1800160d2  mov     rcx, rbx
0x1800160d5  mov     [rsp+78h+var_58], r8d
0x1800160da  mov     rax, [rax+98h]
0x1800160e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160e6  test    rax, rax
0x1800160e9  cmovnz  rbx, rax
0x1800160ed  mov     rcx, rbx
0x1800160f0  mov     rax, [rbx]
0x1800160f3  mov     rax, [rax+0A8h]
0x1800160fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160ff  xor     ebp, ebp
0x180016101  mov     eax, ebp
0x180016103  add     rsp, 58h
0x180016107  pop     rdi
0x180016108  pop     rsi
0x180016109  pop     rbp
0x18001610a  pop     rbx
0x18001610b  retn
```
