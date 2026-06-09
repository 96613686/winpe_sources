# std::_Tree<std::_Tmap_traits<ProblemNode *,tagRepairInfoEx,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,tagRepairInfoEx>>,1>>::_Insert_at<std::pair<ProblemNode * const,tagRepairInfoEx> &,std::_Tree_node<std::pair<ProblemNode * const,tagRepairInfoEx>,void *> *>(bool,std::_Tree_node<std::pair<ProblemNode * const,tagRepairInfoEx>,void *> *,std::pair<ProblemNode * const,tagRepairInfoEx> &,std::_Tree_node<std::pair<ProblemNode * const,tagRepairInfoEx>,void *> *)

- ea: `0x1800213ec`
- end: `0x18002154a`
- name: `??$_Insert_at@AEAU?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@PEAU?$_Tree_node@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@PEAX@2@@?$_Tree@V?$_Tmap_traits@PEAVProblemNode@@UtagRepairInfoEx@@U?$less@PEAVProblemNode@@@std@@V?$allocator@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@4@$00@std@@@std@@IEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@@std@@@std@@@1@_NPEAU?$_Tree_node@U?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@std@@PEAX@1@AEAU?$pair@QEAVProblemNode@@UtagRepairInfoEx@@@1@1@Z`
- size: `350`
- prototype: `_QWORD *__fastcall(__int64 *, _QWORD *, __int64, _QWORD *, int, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x180021550`

## callees

- `0x180001900`
- `0x18000fea8`
- `0x180010018`
- `0x1800213ec`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180021410`
- `msvcrt!??3@YAXPEAX@Z` at `0x180021410`

## pseudocode

```c
_QWORD *__fastcall std::_Tree<std::_Tmap_traits<ProblemNode *,tagRepairInfoEx,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,tagRepairInfoEx>>,1>>::_Insert_at<std::pair<ProblemNode * const,tagRepairInfoEx> &,std::_Tree_node<std::pair<ProblemNode * const,tagRepairInfoEx>,void *> *>(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        _QWORD *a4,
        int a5,
        _QWORD *a6)
{
  unsigned __int64 v6; // rax
  __int64 *v7; // r11
  _QWORD *v9; // r10
  __int64 v10; // rax
  __int64 v11; // rax
  _QWORD *v12; // r9
  __int64 v13; // rdx
  __int64 *v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rcx
  _QWORD *result; // rax

  v6 = a1[1];
  v7 = a1;
  if ( v6 >= 0x199999999999998LL )
  {
    operator delete(a6);
    std::_Xlength_error("map/set<T> too long");
  }
  v9 = a6;
  a1[1] = v6 + 1;
  a6[1] = a4;
  if ( a4 == (_QWORD *)*a1 )
  {
    *(_QWORD *)(*a1 + 8) = a6;
    *(_QWORD *)*a1 = a6;
    v10 = *a1;
LABEL_9:
    *(_QWORD *)(v10 + 16) = a6;
    goto LABEL_10;
  }
  if ( (_BYTE)a3 )
  {
    *a4 = a6;
    if ( a4 == *(_QWORD **)*a1 )
      *(_QWORD *)*a1 = a6;
    goto LABEL_10;
  }
  a4[2] = a6;
  v10 = *a1;
  if ( a4 == *(_QWORD **)(*a1 + 16) )
    goto LABEL_9;
LABEL_10:
  v11 = a6[1];
  v12 = a6;
  while ( !*(_BYTE *)(v11 + 24) )
  {
    v13 = v12[1];
    v14 = *(__int64 **)(v13 + 8);
    v15 = *v14;
    if ( v13 == *v14 )
    {
      v15 = v14[2];
      if ( !*(_BYTE *)(v15 + 24) )
        goto LABEL_17;
      if ( v12 == *(_QWORD **)(v13 + 16) )
        std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CHelperAttribute *>>,0>>::_Lrotate(
          v7,
          v13);
      *(_BYTE *)(v12[1] + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 24LL) = 0;
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(
        v7,
        *(_QWORD *)(v12[1] + 8LL),
        a3,
        v12);
    }
    else
    {
      if ( !*(_BYTE *)(v15 + 24) )
      {
LABEL_17:
        *(_BYTE *)(v13 + 24) = 1;
        *(_BYTE *)(v15 + 24) = 1;
        *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 24LL) = 0;
        v12 = *(_QWORD **)(v12[1] + 8LL);
        goto LABEL_21;
      }
      if ( v12 == *(_QWORD **)v13 )
        std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(
          v7,
          v13,
          a3,
          v12[1]);
      *(_BYTE *)(v12[1] + 24LL) = 1;
      *(_BYTE *)(*(_QWORD *)(v12[1] + 8LL) + 24LL) = 0;
      std::_Tree<std::_Tmap_traits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,CHelperAttribute *,std::less<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,std::allocator<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CHelperAttribute *>>,0>>::_Lrotate(
        v7,
        *(_QWORD *)(v12[1] + 8LL));
    }
LABEL_21:
    v11 = v12[1];
  }
  v16 = *v7;
  *a2 = v9;
  v17 = *(_QWORD *)(v16 + 8);
  result = a2;
  *(_BYTE *)(v17 + 24) = 1;
  return result;
}

```

## disassembly

```asm
0x1800213ec  push    rbx
0x1800213ee  sub     rsp, 20h
0x1800213f2  mov     rax, [rcx+8]
0x1800213f6  mov     r11, rcx
0x1800213f9  mov     rcx, 199999999999998h
0x180021403  mov     rbx, rdx
0x180021406  cmp     rax, rcx
0x180021409  jb      short loc_180021423
0x18002140b  mov     rcx, [rsp+28h+arg_28]
0x180021410  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180021416  lea     rcx, aMapSetTTooLong; "map/set<T> too long"
0x18002141d  call    ?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180021423  mov     r10, [rsp+28h+arg_28]
0x180021428  inc     rax
0x18002142b  mov     [r11+8], rax
0x18002142f  mov     [r10+8], r9
0x180021433  mov     rax, [r11]
0x180021436  cmp     r9, rax
0x180021439  jnz     short loc_18002144A
0x18002143b  mov     [rax+8], r10
0x18002143f  mov     rax, [r11]
0x180021442  mov     [rax], r10
0x180021445  mov     rax, [r11]
0x180021448  jmp     short loc_18002146C
0x18002144a  test    r8b, r8b
0x18002144d  jz      short loc_18002145F
0x18002144f  mov     [r9], r10
0x180021452  mov     rax, [r11]
0x180021455  cmp     r9, [rax]
0x180021458  jnz     short loc_180021470
0x18002145a  mov     [rax], r10
0x18002145d  jmp     short loc_180021470
0x18002145f  mov     [r9+10h], r10
0x180021463  mov     rax, [r11]
0x180021466  cmp     r9, [rax+10h]
0x18002146a  jnz     short loc_180021470
0x18002146c  mov     [rax+10h], r10
0x180021470  mov     rax, [r10+8]
0x180021474  mov     r9, r10
0x180021477  jmp     loc_180021529
0x18002147c  mov     rdx, [r9+8]
0x180021480  mov     rcx, [rdx+8]
0x180021484  mov     rax, [rcx]
0x180021487  cmp     rdx, rax
0x18002148a  jnz     short loc_1800214CD
0x18002148c  mov     rax, [rcx+10h]
0x180021490  cmp     byte ptr [rax+18h], 0
0x180021494  jz      short loc_1800214D3
0x180021496  cmp     r9, [rdx+10h]
0x18002149a  jnz     short loc_1800214A7
0x18002149c  mov     rcx, r11
0x18002149f  mov     r9, rdx
0x1800214a2  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>,void *> *)
0x1800214a7  mov     rax, [r9+8]
0x1800214ab  mov     byte ptr [rax+18h], 1
0x1800214af  mov     rax, [r9+8]
0x1800214b3  mov     rcx, [rax+8]
0x1800214b7  mov     byte ptr [rcx+18h], 0
0x1800214bb  mov     rcx, r11
0x1800214be  mov     rdx, [r9+8]
0x1800214c2  mov     rdx, [rdx+8]
0x1800214c6  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>,void *> *)
0x1800214cb  jmp     short loc_180021525
0x1800214cd  cmp     byte ptr [rax+18h], 0
0x1800214d1  jnz     short loc_1800214F1
0x1800214d3  mov     byte ptr [rdx+18h], 1
0x1800214d7  mov     byte ptr [rax+18h], 1
0x1800214db  mov     rax, [r9+8]
0x1800214df  mov     rcx, [rax+8]
0x1800214e3  mov     byte ptr [rcx+18h], 0
0x1800214e7  mov     rax, [r9+8]
0x1800214eb  mov     r9, [rax+8]
0x1800214ef  jmp     short loc_180021525
0x1800214f1  cmp     r9, [rdx]
0x1800214f4  jnz     short loc_180021501
0x1800214f6  mov     rcx, r11
0x1800214f9  mov     r9, rdx
0x1800214fc  call    ?_Rrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfo@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CExtensionHelperInfo *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>>,0>>::_Rrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfo *>,void *> *)
0x180021501  mov     rax, [r9+8]
0x180021505  mov     byte ptr [rax+18h], 1
0x180021509  mov     rax, [r9+8]
0x18002150d  mov     rcx, [rax+8]
0x180021511  mov     byte ptr [rcx+18h], 0
0x180021515  mov     rcx, r11
0x180021518  mov     rdx, [r9+8]
0x18002151c  mov     rdx, [rdx+8]
0x180021520  call    ?_Lrotate@?$_Tree@V?$_Tmap_traits@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@U?$less@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@@5@$0A@@std@@@std@@IEAAXPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCHelperAttribute@@@std@@PEAX@2@@Z; std::_Tree<std::_Tmap_traits<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>,CHelperAttribute *,std::less<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,std::allocator<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>>,0>>::_Lrotate(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CHelperAttribute *>,void *> *)
0x180021525  mov     rax, [r9+8]
0x180021529  cmp     byte ptr [rax+18h], 0
0x18002152d  jz      loc_18002147C
0x180021533  mov     rax, [r11]
0x180021536  mov     [rbx], r10
0x180021539  mov     rcx, [rax+8]
0x18002153d  mov     rax, rbx
0x180021540  mov     byte ptr [rcx+18h], 1
0x180021544  add     rsp, 20h
0x180021548  pop     rbx
0x180021549  retn
```
