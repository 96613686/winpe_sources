# CSNOCplCore::DoDeleteProfile(_GUID const &)

- ea: `0x18000a1f0`
- end: `0x18000a2d7`
- name: `?DoDeleteProfile@CSNOCplCore@@AEAAJAEBU_GUID@@@Z`
- size: `231`
- prototype: `__int64 __fastcall(CSNOCplCore *__hidden this, const struct _GUID *)`
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x18000ee30`
- `0x18000eec0`

## callees

- `0x18000874c`
- `0x18000a1f0`
- `0x18000a2e0`
- `0x18000b384`
- `0x18001030c`
- `0x180013634`
- `0x180013df4`
- `0x180014274`

## import_xrefs

- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000a244`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x18000a244`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CSNOCplCore::DoDeleteProfile(CSNOCplCore *this, const struct _GUID *a2)
{
  __int64 v3; // rbx
  unsigned int v4; // ebx
  struct CProfileData *v5; // rsi
  __int64 v6; // r8
  unsigned int v7; // edx
  DirectUI::Element *v9; // [rsp+20h] [rbp-18h] BYREF
  unsigned int v10[4]; // [rsp+28h] [rbp-10h] BYREF
  __int64 v11; // [rsp+40h] [rbp+8h] BYREF

  std::_Tree<std::_Tmap_traits<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>,0>>::find(
    *((_QWORD *)this + 19),
    &v11,
    a2);
  v3 = v11;
  if ( v11 == **((_QWORD **)this + 19) )
  {
    v4 = 0;
  }
  else
  {
    v9 = (DirectUI::Element *)*((_QWORD *)this + 40);
    v10[0] = 0;
    DirectUI::Element::StartDefer(v9, v10);
    v5 = *(struct CProfileData **)(v3 + 48);
    *(_QWORD *)(v3 + 48) = 0;
    std::_Tree<std::_Tmap_traits<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>,0>>::_Erase_unchecked(
      *((_QWORD *)this + 19),
      v3);
    v4 = CSNOCplCore::RemoveProfileItemDUI(this, v5, v6);
    CSNOCplCore::HandleConnectivityChange(this);
    if ( v5 )
      CProfileData::`scalar deleting destructor'(v5, v7);
    DirectUI::AutoDefer::EndDefer((DirectUI::AutoDefer *)&v9);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 129, &WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids, v4);
  return v4;
}

```

## disassembly

```asm
0x18000a1f0  mov     [rsp+arg_8], rbx
0x18000a1f5  mov     [rsp+arg_10], rsi
0x18000a1fa  push    rdi
0x18000a1fb  sub     rsp, 30h
0x18000a1ff  mov     rdi, rcx
0x18000a202  mov     r8, rdx
0x18000a205  lea     rdx, [rsp+38h+arg_0]
0x18000a20a  mov     rcx, [rcx+98h]
0x18000a211  call    ?find@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCProfileData@@VCKey_Less@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@@2@AEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>,0>>::find(_GUID const &)
0x18000a216  mov     rax, [rdi+98h]
0x18000a21d  mov     rbx, [rsp+38h+arg_0]
0x18000a222  cmp     rbx, [rax]
0x18000a225  jnz     short loc_18000A22B
0x18000a227  xor     ebx, ebx
0x18000a229  jmp     short loc_18000A294
0x18000a22b  mov     rcx, [rdi+140h]
0x18000a232  mov     [rsp+38h+var_18], rcx
0x18000a237  mov     [rsp+38h+var_10], 0
0x18000a23f  lea     rdx, [rsp+38h+var_10]
0x18000a244  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x18000a24a  nop
0x18000a24b  mov     rsi, [rbx+30h]
0x18000a24f  mov     qword ptr [rbx+30h], 0
0x18000a257  mov     rdx, rbx
0x18000a25a  mov     rcx, [rdi+98h]
0x18000a261  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@U_GUID@@PEAVCProfileData@@VCKey_Less@@V?$allocator@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBU_GUID@@PEAVCProfileData@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<_GUID,CProfileData *,CKey_Less,std::allocator<std::pair<_GUID const,CProfileData *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_GUID const,CProfileData *>>>,std::_Iterator_base0>)
0x18000a266  mov     rdx, rsi; struct CProfileData *
0x18000a269  mov     rcx, rdi; this
0x18000a26c  call    ?RemoveProfileItemDUI@CSNOCplCore@@AEAAJPEAVCProfileData@@@Z; CSNOCplCore::RemoveProfileItemDUI(CProfileData *)
0x18000a271  mov     ebx, eax
0x18000a273  mov     rcx, rdi; this
0x18000a276  call    ?HandleConnectivityChange@CSNOCplCore@@AEAAXXZ; CSNOCplCore::HandleConnectivityChange(void)
0x18000a27b  test    rsi, rsi
0x18000a27e  jz      short loc_18000A289
0x18000a280  mov     rcx, rsi; this
0x18000a283  call    ??_GCProfileData@@QEAAPEAXI@Z; CProfileData::`scalar deleting destructor'(uint)
0x18000a288  nop
0x18000a289  lea     rcx, [rsp+38h+var_18]; this
0x18000a28e  call    ?EndDefer@AutoDefer@DirectUI@@QEAAXXZ; DirectUI::AutoDefer::EndDefer(void)
0x18000a293  nop
0x18000a294  lea     rax, WPP_GLOBAL_Control
0x18000a29b  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a2a2  cmp     rcx, rax
0x18000a2a5  jz      short loc_18000A2C5
0x18000a2a7  test    byte ptr [rcx+1Ch], 8
0x18000a2ab  jz      short loc_18000A2C5
0x18000a2ad  mov     edx, 81h
0x18000a2b2  mov     r9d, ebx
0x18000a2b5  lea     r8, WPP_d8bb7fbfbf9a3b96e75101ac321e388b_Traceguids
0x18000a2bc  mov     rcx, [rcx+10h]
0x18000a2c0  call    WPP_SF_d
0x18000a2c5  mov     eax, ebx
0x18000a2c7  mov     rbx, [rsp+38h+arg_8]
0x18000a2cc  mov     rsi, [rsp+38h+arg_10]
0x18000a2d1  add     rsp, 30h
0x18000a2d5  pop     rdi
0x18000a2d6  retn
```
