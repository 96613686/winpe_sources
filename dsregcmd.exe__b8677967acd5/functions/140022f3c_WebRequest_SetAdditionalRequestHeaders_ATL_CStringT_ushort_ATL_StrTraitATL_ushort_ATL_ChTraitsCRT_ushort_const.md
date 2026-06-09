# WebRequest::SetAdditionalRequestHeaders(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)

- ea: `0x140022f3c`
- end: `0x140023109`
- name: `?SetAdditionalRequestHeaders@WebRequest@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `461`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140014ea4`
- `0x1400176b4`

## callees

- `0x1400017d4`
- `0x140001814`
- `0x1400028ac`
- `0x14000caac`
- `0x14000f978`
- `0x14001e938`
- `0x140022714`
- `0x140022f3c`
- `0x14002c3e8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140022f6d`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x140022f6d`

## string_xrefs

- `0x140022f92`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`
- `0x14002301a`: `onecore\ds\security\dsreg\win32\adal.native\webrequest.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall WebRequest::SetAdditionalRequestHeaders(__int64 a1, const wchar_t **a2)
{
  int v4; // eax
  wchar_t *v5; // rax
  void **v6; // rax
  void **v7; // rbx
  _QWORD *v8; // rax
  _QWORD *v9; // rax
  _QWORD *v10; // rdi
  _QWORD *v11; // rax
  void **v12; // rsi
  _BYTE pExceptionObject[56]; // [rsp+20h] [rbp-38h] BYREF
  void **v14; // [rsp+68h] [rbp+10h] BYREF
  _QWORD *v15; // [rsp+70h] [rbp+18h]

  v4 = *((_DWORD *)*a2 - 4);
  if ( v4 )
  {
    if ( v4 < 0 || (v5 = wcsstr(*a2, L"\r\n")) == 0 || (unsigned int)(v5 - *a2) == -1 )
    {
      Exception::Exception((Exception *)pExceptionObject, -895418329);
      throw (Exception *)pExceptionObject;
    }
    v6 = (void **)operator new(0x10u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\webrequest.cpp");
    v7 = v6;
    v14 = v6;
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
    v14 = v7;
    WebRequest::ParseRawHttpHeaders(&v14, a2);
    if ( v7[1] )
    {
      if ( !*(_QWORD *)(a1 + 16) )
      {
        v9 = operator new(0x10u, 1, "onecore\\ds\\security\\dsreg\\win32\\adal.native\\webrequest.cpp");
        v10 = v9;
        v15 = v9;
        if ( v9 )
        {
          *v9 = 0;
          v9[1] = 0;
          v11 = operator new(0x30u);
          *v11 = v11;
          v11[1] = v11;
          v11[2] = v11;
          *((_WORD *)v11 + 12) = 257;
          *v10 = v11;
        }
        else
        {
          v10 = 0;
        }
        v12 = *(void ***)(a1 + 16);
        *(_QWORD *)(a1 + 16) = v10;
        if ( v12 )
        {
          std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
            (__int64)v12,
            (__int64)v12,
            *((__int64 **)*v12 + 1));
          operator delete(*v12);
          operator delete(v12);
        }
      }
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>,0>>::insert<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>>>(
        *(_QWORD *)(a1 + 16),
        *(_QWORD *)*v7,
        *v7);
    }
    std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
      (__int64)v7,
      (__int64)v7,
      *((__int64 **)*v7 + 1));
    operator delete(*v7);
    operator delete(v7);
  }
}

```

## disassembly

```asm
0x140022f3c  mov     [rsp+arg_0], rbx
0x140022f41  push    rbp
0x140022f42  push    rsi
0x140022f43  push    rdi
0x140022f44  push    r12
0x140022f46  push    r15
0x140022f48  sub     rsp, 30h
0x140022f4c  mov     rdi, rdx
0x140022f4f  mov     rbp, rcx
0x140022f52  mov     rcx, [rdx]; Str
0x140022f55  mov     eax, [rcx-10h]
0x140022f58  test    eax, eax
0x140022f5a  jz      loc_1400230D7
0x140022f60  js      loc_1400230E8
0x140022f66  lea     rdx, asc_140034428; "\r\n"
0x140022f6d  call    cs:__imp_wcsstr
0x140022f73  nop
0x140022f74  test    rax, rax
0x140022f77  jz      loc_1400230E8
0x140022f7d  sub     rax, [rdi]
0x140022f80  sar     rax, 1
0x140022f83  cmp     eax, 0FFFFFFFFh
0x140022f86  jz      loc_1400230E8
0x140022f8c  mov     r9d, 0F0h; int
0x140022f92  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140022f99  mov     esi, 1
0x140022f9e  mov     edx, esi; int
0x140022fa0  lea     r12d, [rsi+0Fh]
0x140022fa4  mov     ecx, r12d; unsigned __int64
0x140022fa7  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x140022fac  mov     rbx, rax
0x140022faf  mov     [rsp+58h+arg_8], rax
0x140022fb4  lea     r15d, [rsi+2Fh]
0x140022fb8  test    rax, rax
0x140022fbb  jz      short loc_140022FEA
0x140022fbd  mov     qword ptr [rax], 0
0x140022fc4  mov     qword ptr [rax+8], 0
0x140022fcc  mov     ecx, r15d; Size
0x140022fcf  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140022fd4  mov     [rax], rax
0x140022fd7  mov     [rax+8], rax
0x140022fdb  mov     [rax+10h], rax
0x140022fdf  mov     word ptr [rax+18h], 101h
0x140022fe5  mov     [rbx], rax
0x140022fe8  jmp     short loc_140022FEC
0x140022fea  xor     ebx, ebx
0x140022fec  mov     [rsp+58h+arg_8], rbx
0x140022ff1  mov     rdx, rdi
0x140022ff4  lea     rcx, [rsp+58h+arg_8]
0x140022ff9  call    ?ParseRawHttpHeaders@WebRequest@@SAXAEBV?$unique_ptr@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@U?$default_delete@V?$map@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@@std@@@2@@std@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WebRequest::ParseRawHttpHeaders(std::unique_ptr<std::map<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x140022ffe  cmp     qword ptr [rbx+8], 0
0x140023003  jbe     loc_1400230AF
0x140023009  cmp     qword ptr [rbp+10h], 0
0x14002300e  jnz     loc_14002309C
0x140023014  mov     r9d, 0F5h; int
0x14002301a  lea     r8, aOnecoreDsSecur_7; "onecore\\ds\\security\\dsreg\\win32\\ad"...
0x140023021  mov     edx, esi; int
0x140023023  mov     rcx, r12; unsigned __int64
0x140023026  call    ??2@YAPEAX_KHPEBDH@Z; operator new(unsigned __int64,int,char const *,int)
0x14002302b  mov     rdi, rax
0x14002302e  mov     [rsp+58h+arg_10], rax
0x140023033  test    rax, rax
0x140023036  jz      short loc_140023065
0x140023038  mov     qword ptr [rax], 0
0x14002303f  mov     qword ptr [rax+8], 0
0x140023047  mov     rcx, r15; Size
0x14002304a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14002304f  mov     [rax], rax
0x140023052  mov     [rax+8], rax
0x140023056  mov     [rax+10h], rax
0x14002305a  mov     word ptr [rax+18h], 101h
0x140023060  mov     [rdi], rax
0x140023063  jmp     short loc_140023067
0x140023065  xor     edi, edi
0x140023067  mov     rsi, [rbp+10h]
0x14002306b  mov     [rbp+10h], rdi
0x14002306f  test    rsi, rsi
0x140023072  jz      short loc_14002309C
0x140023074  mov     r8, [rsi]
0x140023077  mov     r8, [r8+8]
0x14002307b  mov     rdx, rsi
0x14002307e  mov     rcx, rsi
0x140023081  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x140023086  mov     rdx, r15
0x140023089  mov     rcx, [rsi]; Block
0x14002308c  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x140023091  mov     rdx, r12
0x140023094  mov     rcx, rsi; Block
0x140023097  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x14002309c  mov     rdx, [rbx]
0x14002309f  mov     r8, rdx
0x1400230a2  mov     rdx, [rdx]
0x1400230a5  mov     rcx, [rbp+10h]
0x1400230a9  call    ??$insert@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@std@@@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@4@$0A@@std@@@std@@QEAAXV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@@1@0@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>,0>>::insert<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>,std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>>)
0x1400230ae  nop
0x1400230af  mov     r8, [rbx]
0x1400230b2  mov     r8, [r8+8]
0x1400230b6  mov     rdx, rbx
0x1400230b9  mov     rcx, rbx
0x1400230bc  call    ??$_Erase_tree_and_orphan@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>>>::_Erase_tree_and_orphan<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>> &,std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *> *)
0x1400230c1  mov     rdx, r15
0x1400230c4  mov     rcx, [rbx]; Block
0x1400230c7  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x1400230cc  mov     rdx, r12
0x1400230cf  mov     rcx, rbx; Block
0x1400230d2  call    ??3@YAXPEAXHPEBDH@Z; operator delete(void *,int,char const *,int)
0x1400230d7  mov     rbx, [rsp+58h+arg_0]
0x1400230dc  add     rsp, 30h
0x1400230e0  pop     r15
0x1400230e2  pop     r12
0x1400230e4  pop     rdi
0x1400230e5  pop     rsi
0x1400230e6  pop     rbp
0x1400230e7  retn
0x1400230e8  mov     edx, 0CAA10027h; unsigned int
0x1400230ed  lea     rcx, [rsp+58h+pExceptionObject]; this
0x1400230f2  call    ??0Exception@@QEAA@K@Z; Exception::Exception(ulong)
0x1400230f7  lea     rdx, _TI1?AVException@@; pThrowInfo
0x1400230fe  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x140023103  call    _CxxThrowException_0
```
