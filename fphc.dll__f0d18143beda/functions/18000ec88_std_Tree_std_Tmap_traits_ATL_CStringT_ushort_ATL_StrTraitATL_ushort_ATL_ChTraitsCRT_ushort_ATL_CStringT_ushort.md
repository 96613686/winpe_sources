# std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Erase(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)

- ea: `0x18000ec88`
- end: `0x18000ed1f`
- name: `?_Erase@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@Z`
- size: `151`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x18000d770`
- `0x18000d840`
- `0x18000ec88`

## callees

- `0x18000ec88`
- `0x180012010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000ed00`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000ed00`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
        __int64 a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  _QWORD *i; // rdi
  volatile signed __int32 *v5; // rdx
  volatile signed __int32 *v6; // rdx

  v2 = a2;
  for ( i = a2; !*((_BYTE *)i + 25); v2 = i )
  {
    std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,1>>::_Erase(
      a1,
      i[2]);
    i = (_QWORD *)*i;
    v5 = (volatile signed __int32 *)(v2[5] - 24LL);
    if ( _InterlockedExchangeAdd(v5 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v5 + 8LL))(*(_QWORD *)v5);
    v6 = (volatile signed __int32 *)(v2[4] - 24LL);
    if ( _InterlockedExchangeAdd(v6 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v6 + 8LL))(*(_QWORD *)v6);
    operator delete(v2);
  }
}

```

## disassembly

```asm
0x18000ec88  mov     [rsp+arg_0], rbx
0x18000ec8d  mov     [rsp+arg_8], rsi
0x18000ec92  push    rdi
0x18000ec93  sub     rsp, 20h
0x18000ec97  cmp     byte ptr [rdx+19h], 0
0x18000ec9b  mov     rbx, rdx
0x18000ec9e  mov     rsi, rcx
0x18000eca1  mov     rdi, rdx
0x18000eca4  jnz     short loc_18000ED0F
0x18000eca6  mov     rdx, [rdi+10h]
0x18000ecaa  mov     rcx, rsi
0x18000ecad  call    ?_Erase@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$00@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,1>>::_Erase(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x18000ecb2  mov     rdx, [rbx+28h]
0x18000ecb6  mov     rdi, [rdi]
0x18000ecb9  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000ecbd  or      eax, 0FFFFFFFFh
0x18000ecc0  lock xadd [rdx+10h], eax
0x18000ecc5  sub     eax, 1
0x18000ecc8  jg      short loc_18000ECD9
0x18000ecca  mov     rcx, [rdx]
0x18000eccd  mov     rax, [rcx]
0x18000ecd0  mov     rax, [rax+8]
0x18000ecd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecd9  mov     rdx, [rbx+20h]
0x18000ecdd  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18000ece1  or      eax, 0FFFFFFFFh
0x18000ece4  lock xadd [rdx+10h], eax
0x18000ece9  sub     eax, 1
0x18000ecec  jg      short loc_18000ECFD
0x18000ecee  mov     rcx, [rdx]
0x18000ecf1  mov     rax, [rcx]
0x18000ecf4  mov     rax, [rax+8]
0x18000ecf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecfd  mov     rcx, rbx
0x18000ed00  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000ed06  cmp     byte ptr [rdi+19h], 0
0x18000ed0a  mov     rbx, rdi
0x18000ed0d  jz      short loc_18000ECA6
0x18000ed0f  mov     rbx, [rsp+28h+arg_0]
0x18000ed14  mov     rsi, [rsp+28h+arg_8]
0x18000ed19  add     rsp, 20h
0x18000ed1d  pop     rdi
0x18000ed1e  retn
```
