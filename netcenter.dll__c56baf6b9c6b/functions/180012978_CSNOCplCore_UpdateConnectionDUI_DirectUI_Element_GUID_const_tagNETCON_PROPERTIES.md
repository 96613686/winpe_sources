# CSNOCplCore::UpdateConnectionDUI(DirectUI::Element *,_GUID const &,tagNETCON_PROPERTIES *)

- ea: `0x180012978`
- end: `0x180012a7b`
- name: `?UpdateConnectionDUI@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z`
- size: `259`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, struct DirectUI::Element *, const struct _GUID *, struct tagNETCON_PROPERTIES *)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x180012b6c`

## callees

- `0x180006b70`
- `0x180008fc4`
- `0x18001113c`
- `0x180011464`
- `0x180012978`
- `0x180012a84`
- `0x180014274`

## import_xrefs

- `DUI70!StrToID` at `0x1800129e8`
- `DUI70!StrToID` at `0x1800129e8`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800129f4`
- `DUI70!?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z` at `0x1800129f4`

## pseudocode

```c
__int64 __fastcall CSNOCplCore::UpdateConnectionDUI(
        CSNOCplCore *this,
        struct DirectUI::Element *a2,
        const struct _GUID *a3,
        struct tagNETCON_PROPERTIES *a4)
{
  CSNOCplCore *v8; // rcx
  int v9; // ebx
  unsigned __int16 v10; // ax
  struct DirectUI::Element *Descendent; // rax
  CSNOCplCore *v12; // rcx
  const unsigned __int16 *v13; // rdx
  CSNOCplCore *v14; // rcx
  const struct _GUID *v15; // r8

  v8 = (CSNOCplCore *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 143, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids);
  if ( !a2 || !a4 )
    return 2147500035LL;
  v9 = -2147418113;
  CSNOCplCore::SetGUIDAsAtomtID(v8, a2, &a4->guidId);
  v10 = StrToID(L"connname");
  Descendent = DirectUI::Element::FindDescendent(a2, v10);
  if ( Descendent )
  {
    v9 = CSNOCplCore::SetContentAndAccName(v12, Descendent, a4->pszwName, 0xC1u);
    if ( v9 >= 0 )
    {
      v9 = CSNOCplCore::ChangeHiddenChildIdGUIDGUID(v14, v13, &a4->guidId, a3, a2);
      if ( v9 >= 0 )
        CSNOCplCore::UpdateConnectionIcon(this, a2, v15, a4);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      144,
      &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids,
      (unsigned int)v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012978  push    rbx
0x18001297a  push    rbp
0x18001297b  push    rsi
0x18001297c  push    rdi
0x18001297d  push    r14
0x18001297f  push    r15
0x180012981  sub     rsp, 38h
0x180012985  mov     rdi, r9
0x180012988  mov     r14, r8
0x18001298b  mov     rsi, rdx
0x18001298e  mov     rbp, rcx
0x180012991  mov     rcx, cs:WPP_GLOBAL_Control
0x180012998  lea     r15, WPP_GLOBAL_Control
0x18001299f  cmp     rcx, r15
0x1800129a2  jz      short loc_1800129BF
0x1800129a4  test    byte ptr [rcx+1Ch], 8
0x1800129a8  jz      short loc_1800129BF
0x1800129aa  mov     rcx, [rcx+10h]
0x1800129ae  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x1800129b5  mov     edx, 8Fh
0x1800129ba  call    WPP_SF_
0x1800129bf  test    rsi, rsi
0x1800129c2  jz      loc_180012A69
0x1800129c8  test    rdi, rdi
0x1800129cb  jz      loc_180012A69
0x1800129d1  mov     r8, rdi; struct _GUID *
0x1800129d4  mov     rdx, rsi; struct DirectUI::Element *
0x1800129d7  mov     ebx, 8000FFFFh
0x1800129dc  call    ?SetGUIDAsAtomtID@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@@Z; CSNOCplCore::SetGUIDAsAtomtID(DirectUI::Element *,_GUID const &)
0x1800129e1  lea     rcx, aConnname; "connname"
0x1800129e8  call    cs:__imp_StrToID
0x1800129ee  movzx   edx, ax
0x1800129f1  mov     rcx, rsi
0x1800129f4  call    cs:__imp_?FindDescendent@Element@DirectUI@@QEAAPEAV12@G@Z; DirectUI::Element::FindDescendent(ushort)
0x1800129fa  test    rax, rax
0x1800129fd  jz      short loc_180012A3B
0x1800129ff  mov     r8, [rdi+10h]; unsigned __int16 *
0x180012a03  mov     r9d, 0C1h; unsigned int
0x180012a09  mov     rdx, rax; struct DirectUI::Element *
0x180012a0c  call    ?SetContentAndAccName@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@PEBGI@Z; CSNOCplCore::SetContentAndAccName(DirectUI::Element *,ushort const *,uint)
0x180012a11  mov     ebx, eax
0x180012a13  test    eax, eax
0x180012a15  js      short loc_180012A3B
0x180012a17  mov     r9, r14; struct _GUID *
0x180012a1a  mov     [rsp+68h+var_48], rsi; struct DirectUI::Element *
0x180012a1f  mov     r8, rdi; struct _GUID *
0x180012a22  call    ?ChangeHiddenChildIdGUIDGUID@CSNOCplCore@@AEAAJPEBGAEBU_GUID@@1PEAVElement@DirectUI@@@Z; CSNOCplCore::ChangeHiddenChildIdGUIDGUID(ushort const *,_GUID const &,_GUID const &,DirectUI::Element *)
0x180012a27  mov     ebx, eax
0x180012a29  test    eax, eax
0x180012a2b  js      short loc_180012A3B
0x180012a2d  mov     r9, rdi; struct tagNETCON_PROPERTIES *
0x180012a30  mov     rdx, rsi; struct DirectUI::Element *
0x180012a33  mov     rcx, rbp; this
0x180012a36  call    ?UpdateConnectionIcon@CSNOCplCore@@AEAAJPEAVElement@DirectUI@@AEBU_GUID@@PEAUtagNETCON_PROPERTIES@@@Z; CSNOCplCore::UpdateConnectionIcon(DirectUI::Element *,_GUID const &,tagNETCON_PROPERTIES *)
0x180012a3b  mov     rcx, cs:WPP_GLOBAL_Control
0x180012a42  cmp     rcx, r15
0x180012a45  jz      short loc_180012A65
0x180012a47  test    byte ptr [rcx+1Ch], 8
0x180012a4b  jz      short loc_180012A65
0x180012a4d  mov     rcx, [rcx+10h]
0x180012a51  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x180012a58  mov     edx, 90h
0x180012a5d  mov     r9d, ebx
0x180012a60  call    WPP_SF_d
0x180012a65  mov     eax, ebx
0x180012a67  jmp     short loc_180012A6E
0x180012a69  mov     eax, 80004003h
0x180012a6e  add     rsp, 38h
0x180012a72  pop     r15
0x180012a74  pop     r14
0x180012a76  pop     rdi
0x180012a77  pop     rsi
0x180012a78  pop     rbp
0x180012a79  pop     rbx
0x180012a7a  retn
```
