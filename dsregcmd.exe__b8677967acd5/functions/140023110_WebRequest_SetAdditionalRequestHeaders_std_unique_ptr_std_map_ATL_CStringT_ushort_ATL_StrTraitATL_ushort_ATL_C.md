# WebRequest::SetAdditionalRequestHeaders(std::unique_ptr<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>,std::default_delete<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>> const &)

- ea: `0x140023110`
- end: `0x1400231da`
- name: `?SetAdditionalRequestHeaders@WebRequest@@QEAAXAEBV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@@Z`
- size: `202`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400249f0`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x1400028ac`
- `0x14000f978`
- `0x14001e938`
- `0x140023110`

## string_xrefs

- `0x140023131`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WebRequest::SetAdditionalRequestHeaders(__int64 a1, _QWORD ***a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  _QWORD *v6; // rax
  void **v7; // rsi

  if ( !*(_QWORD *)(a1 + 16) )
  {
    v4 = operator new(0x10u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\webrequest.cpp");
    v5 = v4;
    if ( v4 )
    {
      *v4 = 0;
      v4[1] = 0;
      v6 = operator new(0x30u);
      *v6 = v6;
      v6[1] = v6;
      v6[2] = v6;
      *((_WORD *)v6 + 12) = 257;
      *v5 = v6;
    }
    else
    {
      v5 = 0;
    }
    v7 = *(void ***)(a1 + 16);
    *(_QWORD *)(a1 + 16) = v5;
    if ( v7 )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
        (__int64)v7,
        (__int64)v7,
        *((__int64 **)*v7 + 1));
      operator delete(*v7);
      operator delete(v7);
    }
  }
  return std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,0>>::insert<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>>>(
           *(_QWORD *)(a1 + 16),
           ***a2,
           **a2);
}

```

## disassembly

```asm
0x140023110  push    rbx
0x140023112  push    rsi
0x140023113  push    rdi
0x140023114  push    r14
0x140023116  sub     rsp, 28h
0x14002311a  mov     r14, rdx
0x14002311d  mov     rdi, rcx
0x140023120  cmp     qword ptr [rcx+10h], 0
0x140023125  jnz     loc_1400231BC
0x14002312b  mov     r9d, 0E2h; int
0x140023131  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140023138  mov     edx, 1; int
0x14002313d  lea     ecx, [rdx+0Fh]; unsigned __int64
0x140023140  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140023145  mov     rbx, rax
0x140023148  mov     [rsp+48h+arg_0], rax
0x14002314d  test    rax, rax
0x140023150  jz      short loc_140023181
0x140023152  mov     qword ptr [rax], 0
0x140023159  mov     qword ptr [rax+8], 0
0x140023161  mov     ecx, 30h ; '0'; Size
0x140023166  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002316b  mov     [rax], rax
0x14002316e  mov     [rax+8], rax
0x140023172  mov     [rax+10h], rax
0x140023176  mov     word ptr [rax+18h], 101h
0x14002317c  mov     [rbx], rax
0x14002317f  jmp     short loc_140023183
0x140023181  xor     ebx, ebx
0x140023183  mov     rsi, [rdi+10h]
0x140023187  mov     [rdi+10h], rbx
0x14002318b  test    rsi, rsi
0x14002318e  jz      short loc_1400231BC
0x140023190  mov     r8, [rsi]
0x140023193  mov     r8, [r8+8]
0x140023197  mov     rdx, rsi
0x14002319a  mov     rcx, rsi
0x14002319d  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x1400231a2  mov     edx, 30h ; '0'
0x1400231a7  mov     rcx, [rsi]; Block
0x1400231aa  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x1400231af  mov     edx, 10h
0x1400231b4  mov     rcx, rsi; Block
0x1400231b7  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x1400231bc  mov     rdx, [r14]
0x1400231bf  mov     rdx, [rdx]
0x1400231c2  mov     r8, rdx
0x1400231c5  mov     rdx, [rdx]
0x1400231c8  mov     rcx, [rdi+10h]
0x1400231cc  add     rsp, 28h
0x1400231d0  pop     r14
0x1400231d2  pop     rdi
0x1400231d3  pop     rsi
0x1400231d4  pop     rbx
0x1400231d5  jmp     ??$insert@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$0A@@std@@@std@@QEAAXV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@1@0@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,0>>::insert<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>)
```
