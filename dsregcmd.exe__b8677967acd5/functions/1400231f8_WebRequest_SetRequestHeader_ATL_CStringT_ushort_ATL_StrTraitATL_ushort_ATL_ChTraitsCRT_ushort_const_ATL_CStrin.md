# WebRequest::SetRequestHeader(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x1400231f8`
- end: `0x1400232d8`
- name: `?SetRequestHeader@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z`
- size: `224`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000d9a8`
- `0x140014ea4`
- `0x14001604c`
- `0x1400176b4`
- `0x14001bd58`
- `0x140029294`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x1400028ac`
- `0x140007bf8`
- `0x14000f978`
- `0x140014730`
- `0x1400231f8`

## string_xrefs

- `0x140023224`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall WebRequest::SetRequestHeader(__int64 a1, __int64 a2, _QWORD *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  _QWORD *v8; // rax
  void **v9; // rsi
  _QWORD *v10; // rax

  if ( !*(_QWORD *)(a1 + 16) )
  {
    v6 = operator new(0x10u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\webrequest.cpp");
    v7 = v6;
    if ( v6 )
    {
      *v6 = 0;
      v6[1] = 0;
      v8 = operator new(0x30u);
      *v8 = v8;
      v8[1] = v8;
      v8[2] = v8;
      *((_WORD *)v8 + 12) = 257;
      *v7 = v8;
    }
    else
    {
      v7 = 0;
    }
    v9 = *(void ***)(a1 + 16);
    *(_QWORD *)(a1 + 16) = v7;
    if ( v9 )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
        (__int64)v9,
        (__int64)v9,
        *((__int64 **)*v9 + 1));
      operator delete(*v9);
      operator delete(v9);
    }
  }
  v10 = (_QWORD *)std::map<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::operator[](
                    *(_QWORD *)(a1 + 16),
                    a2);
  return ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
           v10,
           a3);
}

```

## disassembly

```asm
0x1400231f8  mov     [rsp+arg_8], rbx
0x1400231fd  mov     [rsp+arg_10], rbp
0x140023202  push    rsi
0x140023203  push    rdi
0x140023204  push    r14
0x140023206  sub     rsp, 20h
0x14002320a  mov     rbp, r8
0x14002320d  mov     r14, rdx
0x140023210  mov     rdi, rcx
0x140023213  cmp     qword ptr [rcx+10h], 0
0x140023218  jnz     loc_1400232AF
0x14002321e  mov     r9d, 0DAh; int
0x140023224  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x14002322b  mov     edx, 1; int
0x140023230  lea     ecx, [rdx+0Fh]; unsigned __int64
0x140023233  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140023238  mov     rbx, rax
0x14002323b  mov     [rsp+38h+arg_0], rax
0x140023240  test    rax, rax
0x140023243  jz      short loc_140023274
0x140023245  mov     qword ptr [rax], 0
0x14002324c  mov     qword ptr [rax+8], 0
0x140023254  mov     ecx, 30h ; '0'; Size
0x140023259  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002325e  mov     [rax], rax
0x140023261  mov     [rax+8], rax
0x140023265  mov     [rax+10h], rax
0x140023269  mov     word ptr [rax+18h], 101h
0x14002326f  mov     [rbx], rax
0x140023272  jmp     short loc_140023276
0x140023274  xor     ebx, ebx
0x140023276  mov     rsi, [rdi+10h]
0x14002327a  mov     [rdi+10h], rbx
0x14002327e  test    rsi, rsi
0x140023281  jz      short loc_1400232AF
0x140023283  mov     r8, [rsi]
0x140023286  mov     r8, [r8+8]
0x14002328a  mov     rdx, rsi
0x14002328d  mov     rcx, rsi
0x140023290  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x140023295  mov     edx, 30h ; '0'
0x14002329a  mov     rcx, [rsi]; Block
0x14002329d  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x1400232a2  mov     edx, 10h
0x1400232a7  mov     rcx, rsi; Block
0x1400232aa  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x1400232af  mov     rdx, r14
0x1400232b2  mov     rcx, [rdi+10h]
0x1400232b6  call    ??A?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@QEAAAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$QEAV23@@Z; std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::operator[](ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &&)
0x1400232bb  mov     rcx, rax
0x1400232be  mov     rdx, rbp
0x1400232c1  mov     rbx, [rsp+38h+arg_8]
0x1400232c6  mov     rbp, [rsp+38h+arg_10]
0x1400232cb  add     rsp, 20h
0x1400232cf  pop     r14
0x1400232d1  pop     rdi
0x1400232d2  pop     rsi
0x1400232d3  jmp     ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
```
