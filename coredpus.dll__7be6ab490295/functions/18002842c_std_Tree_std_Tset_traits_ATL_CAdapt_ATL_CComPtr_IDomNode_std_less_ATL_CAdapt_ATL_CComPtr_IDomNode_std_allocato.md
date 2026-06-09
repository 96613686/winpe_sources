# std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::_Emplace<ATL::CAdapt<ATL::CComPtr<IDomNode>>>(ATL::CAdapt<ATL::CComPtr<IDomNode>> &&)

- ea: `0x18002842c`
- end: `0x180028516`
- name: `??$_Emplace@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@?$_Tree@V?$_Tset_traits@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@U?$less@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@V?$allocator@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@4@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@_N@1@$$QEAV?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@Z`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180028620`

## callees

- `0x180014c60`
- `0x180024028`
- `0x18002842c`
- `0x180028574`
- `0x1800287f0`
- `0x18002b068`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180028489`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180028489`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::_Emplace<ATL::CAdapt<ATL::CComPtr<IDomNode>>>(
        __int64 *a1,
        __int64 a2,
        __int64 *a3)
{
  __int64 v6; // rax
  _QWORD *v7; // r8
  __int128 v8; // xmm6
  __int64 v9; // rdx
  __int64 v10; // rbx
  _QWORD *v11; // rdi
  _OWORD v13[2]; // [rsp+20h] [rbp-58h] BYREF

  v6 = std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::_Find_lower_bound<ATL::CAdapt<ATL::CComPtr<IDomNode>>>(
         a1,
         v13);
  v8 = *(_OWORD *)v6;
  v9 = *(_QWORD *)(v6 + 16);
  if ( *(_BYTE *)(v9 + 25) || *v7 < *(_QWORD *)(v9 + 32) )
  {
    if ( a1[1] == 0x666666666666666LL )
      std::_Xlength_error("map/set too long");
    v10 = *a1;
    v13[0] = (unsigned __int64)a1;
    v11 = operator new(0x28u);
    ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(v11 + 4, *a3);
    *v11 = v10;
    v11[1] = v10;
    v11[2] = v10;
    *((_WORD *)v11 + 12) = 0;
    *((_QWORD *)&v13[0] + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>(v13);
    v13[0] = v8;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDdfInfo *>>>::_Insert_node(
                      a1,
                      v13,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  else
  {
    *(_QWORD *)a2 = v9;
    *(_BYTE *)(a2 + 8) = 0;
  }
  return a2;
}

```

## disassembly

```asm
0x18002842c  push    rbx
0x18002842e  push    rsi
0x18002842f  push    rdi
0x180028430  push    r14
0x180028432  push    r15
0x180028434  sub     rsp, 50h
0x180028438  movaps  [rsp+78h+var_38], xmm6
0x18002843d  mov     r15, r8
0x180028440  mov     rsi, rdx
0x180028443  mov     r14, rcx
0x180028446  lea     rdx, [rsp+78h+var_58]
0x18002844b  call    ??$_Find_lower_bound@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@?$_Tree@V?$_Tset_traits@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@U?$less@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@std@@V?$allocator@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@4@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@@1@AEBV?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@@Z; std::_Tree<std::_Tset_traits<ATL::CAdapt<ATL::CComPtr<IDomNode>>,std::less<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,std::allocator<ATL::CAdapt<ATL::CComPtr<IDomNode>>>,0>>::_Find_lower_bound<ATL::CAdapt<ATL::CComPtr<IDomNode>>>(ATL::CAdapt<ATL::CComPtr<IDomNode>> const &)
0x180028450  movups  xmm6, xmmword ptr [rax]
0x180028453  mov     rdx, [rax+10h]
0x180028457  cmp     byte ptr [rdx+19h], 0
0x18002845b  jnz     short loc_180028472
0x18002845d  mov     rax, [rdx+20h]
0x180028461  cmp     [r8], rax
0x180028464  jb      short loc_180028472
0x180028466  mov     [rsi], rdx
0x180028469  mov     byte ptr [rsi+8], 0
0x18002846d  jmp     loc_180028501
0x180028472  mov     rax, 666666666666666h
0x18002847c  cmp     [r14+8], rax
0x180028480  jnz     short loc_180028496
0x180028482  lea     rcx, aMapSetTooLong; "map/set too long"
0x180028489  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180028496  mov     rbx, [r14]
0x180028499  mov     qword ptr [rsp+78h+var_58], r14
0x18002849e  mov     qword ptr [rsp+78h+var_58+8], 0
0x1800284a7  mov     ecx, 28h ; '('; Size
0x1800284ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800284b1  mov     rdi, rax
0x1800284b4  lea     rcx, [rax+20h]
0x1800284b8  mov     rdx, [r15]
0x1800284bb  call    ??0?$CComPtrBase@UIDomNode@@@ATL@@IEAA@PEAUIDomNode@@@Z; ATL::CComPtrBase<IDomNode>::CComPtrBase<IDomNode>(IDomNode *)
0x1800284c0  mov     [rdi], rbx
0x1800284c3  mov     [rdi+8], rbx
0x1800284c7  mov     [rdi+10h], rbx
0x1800284cb  mov     word ptr [rdi+18h], 0
0x1800284d1  mov     qword ptr [rsp+78h+var_58+8], 0
0x1800284da  lea     rcx, [rsp+78h+var_58]
0x1800284df  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@V?$CAdapt@V?$CComPtr@UIDomNode@@@ATL@@@ATL@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<ATL::CAdapt<ATL::CComPtr<IDomNode>>,void *>>>(void)
0x1800284e4  movdqu  [rsp+78h+var_58], xmm6
0x1800284ea  mov     r8, rdi
0x1800284ed  lea     rdx, [rsp+78h+var_58]
0x1800284f2  mov     rcx, r14
0x1800284f5  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAVCDdfInfo@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,CDdfInfo *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<std::wstring const,CDdfInfo *>,void *> *>,std::_Tree_node<std::pair<std::wstring const,CDdfInfo *>,void *> * const)
0x1800284fa  mov     [rsi], rax
0x1800284fd  mov     byte ptr [rsi+8], 1
0x180028501  mov     rax, rsi
0x180028504  movaps  xmm6, [rsp+78h+var_38]
0x180028509  add     rsp, 50h
0x18002850d  pop     r15
0x18002850f  pop     r14
0x180028511  pop     rdi
0x180028512  pop     rsi
0x180028513  pop     rbx
0x180028514  retn
```
