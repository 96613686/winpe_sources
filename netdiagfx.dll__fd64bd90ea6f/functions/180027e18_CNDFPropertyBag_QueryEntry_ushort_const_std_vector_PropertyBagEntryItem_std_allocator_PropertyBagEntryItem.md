# CNDFPropertyBag::QueryEntry(ushort const *,std::vector<PropertyBagEntryItem,std::allocator<PropertyBagEntryItem>> &)

- ea: `0x180027e18`
- end: `0x1800281d9`
- name: `?QueryEntry@CNDFPropertyBag@@AEAAJPEBGAEAV?$vector@UPropertyBagEntryItem@@V?$allocator@UPropertyBagEntryItem@@@std@@@std@@@Z`
- size: `961`
- prototype: ``
- caller_count: `2`
- callee_count: `15`
- tags: `loader_planting, service_task`

## callers

- `0x180027ce0`
- `0x180028254`

## callees

- `0x1800035a8`
- `0x180005048`
- `0x1800083a0`
- `0x1800083e0`
- `0x180008d38`
- `0x18001006c`
- `0x180010254`
- `0x180011af0`
- `0x180016664`
- `0x1800216d0`
- `0x180027c3c`
- `0x180027e18`
- `0x18002c802`
- `0x18002c840`
- `0x18002f010`

## import_xrefs

- `KERNEL32!lstrcmpW` at `0x180027f2c`
- `KERNEL32!lstrcmpW` at `0x180027f2c`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CNDFPropertyBag::QueryEntry(__int64 a1, const WCHAR *a2, __int128 *a3)
{
  __int64 ***v5; // r14
  __int64 **v6; // r12
  _QWORD *v7; // r8
  __int64 **v8; // rdi
  LPCWSTR **i; // rbx
  _QWORD *v10; // rdx
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // r9
  int v15; // eax
  __int64 v16; // r9
  int v17; // eax
  __int64 *v18; // rbx
  __int64 v19; // r14
  __int64 v20; // rcx
  __int64 *j; // rax
  __int64 v22; // rcx
  __int128 *v23; // rsi
  __int64 v24; // rax
  __int64 v25; // rax
  __int64 v26; // rcx
  unsigned int v27; // ebx
  __int128 v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h]
  __int64 v31; // [rsp+48h] [rbp-B8h] BYREF
  _QWORD v32[2]; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v33[3]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 *v36; // [rsp+88h] [rbp-78h]
  _QWORD v37[2]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  _QWORD *v39; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int64 v40; // [rsp+C0h] [rbp-40h]
  unsigned __int16 v41[264]; // [rsp+D0h] [rbp-30h] BYREF

  v36 = a3;
  v29 = 0;
  v30 = 0;
  v32[1] = 0;
  v32[0] = std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,tagHELPER_ATTRIBUTE *>>>::_Buyheadnode();
  std::queue<int>::queue<int,std::deque<int>>(v33);
  v5 = (__int64 ***)(a1 + 64);
  std::deque<ProblemNode *>::push_back(v33, a1 + 64);
  v6 = 0;
  while ( v35 )
  {
    std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(
      (std::_Iterator_base12 *)&v39,
      v34,
      (const struct std::_Container_base12 *)v33);
    v7 = v39;
    if ( v39 )
      v7 = (_QWORD *)*v39;
    v8 = *(__int64 ***)(*(_QWORD *)(v7[1] + 8 * ((v7[2] - 1LL) & (v40 >> 1))) + 8 * (v40 & 1));
    if ( v35 )
    {
      if ( --v35 )
        ++v34;
      else
        v34 = 0;
    }
    for ( i = (LPCWSTR **)v8[13]; i != (LPCWSTR **)v8[14]; i += 2 )
    {
      if ( !lstrcmpW(**i, a2) )
      {
        if ( *((_QWORD *)&v29 + 1) == (_QWORD)v29 )
        {
          v37[0] = i;
          v37[1] = v8;
          v6 = v8;
          v10 = v37;
        }
        else
        {
          if ( *(_QWORD *)(a1 + 72) )
          {
            memset_0(v41, 0, 0x208u);
            v11 = **v5;
            v12 = v11[2];
            if ( !*(_DWORD *)(v12 - 16) )
              v12 = *v11;
            v13 = StringCchPrintfW(
                    v41,
                    0x104u,
                    L"Property Bag: Found a conflict when searching for property bag entry '%s' from HC '%s'",
                    a2,
                    v12);
            if ( ((v13 + 0x80000000) & 0x80000000) != 0 || v13 == -2147024774 )
            {
              (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *))(**(_QWORD **)(a1 + 72) + 96LL))(
                *(_QWORD *)(a1 + 72),
                0,
                v41);
              (*(void (__fastcall **)(_QWORD, _QWORD, const wchar_t *))(**(_QWORD **)(a1 + 72) + 96LL))(
                *(_QWORD *)(a1 + 72),
                0,
                L"Property Bag: The following helper classes hold conflicting values:");
              v14 = (*v6)[2];
              if ( !*(_DWORD *)(v14 - 16) )
                v14 = **v6;
              v15 = StringCchPrintfW(v41, 0x104u, L"Property Bag: %s", v14);
              if ( ((v15 + 0x80000000) & 0x80000000) != 0 || v15 == -2147024774 )
                (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**(_QWORD **)(a1 + 72) + 112LL))(
                  *(_QWORD *)(a1 + 72),
                  0,
                  v41,
                  (*v6)[5]);
              v16 = (*v8)[2];
              if ( !*(_DWORD *)(v16 - 16) )
                v16 = **v8;
              v17 = StringCchPrintfW(v41, 0x104u, L"Property Bag: %s", v16);
              if ( ((v17 + 0x80000000) & 0x80000000) != 0 || v17 == -2147024774 )
                (*(void (__fastcall **)(_QWORD, _QWORD, unsigned __int16 *, __int64))(**(_QWORD **)(a1 + 72) + 112LL))(
                  *(_QWORD *)(a1 + 72),
                  0,
                  v41,
                  (*v8)[5]);
            }
          }
          v38[0] = i;
          v38[1] = v8;
          v10 = v38;
        }
        std::vector<PropertyBagEntry>::push_back(&v29, v10);
      }
    }
    if ( v6 != v8 )
    {
      v18 = (__int64 *)*v8[1];
      while ( v18 != v8[1] )
      {
        v19 = v18[4];
        v31 = v19;
        if ( !*(_QWORD *)std::map<ProblemNode *,ProblemNode *>::operator[](v32, &v31) )
        {
          std::deque<ProblemNode *>::push_back(v33, &v31);
          *(_QWORD *)std::map<ProblemNode *,ProblemNode *>::operator[](v32, &v31) = v19;
        }
        if ( !*((_BYTE *)v18 + 25) )
        {
          v20 = v18[2];
          if ( *(_BYTE *)(v20 + 25) )
          {
            for ( j = (__int64 *)v18[1]; !*((_BYTE *)j + 25) && v18 == (__int64 *)j[2]; j = (__int64 *)j[1] )
              v18 = j;
          }
          else
          {
            j = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,CExtensionHelperInfoContainer *>>>::_Min((_QWORD *)v20);
          }
          v18 = j;
        }
      }
      v5 = (__int64 ***)(a1 + 64);
    }
  }
  v22 = *((_QWORD *)&v29 + 1);
  v23 = v36;
  if ( *((_QWORD *)&v29 + 1) == (_QWORD)v29 )
  {
    v27 = -2147024894;
  }
  else
  {
    if ( v36 != &v29 )
    {
      v24 = *(_QWORD *)v36;
      *(_QWORD *)v36 = v29;
      *(_QWORD *)&v29 = v24;
      v25 = *((_QWORD *)v23 + 1);
      *((_QWORD *)v23 + 1) = v22;
      *((_QWORD *)&v29 + 1) = v25;
      v26 = *((_QWORD *)v23 + 2);
      *((_QWORD *)v23 + 2) = v30;
      v30 = v26;
    }
    v27 = 0;
  }
  std::deque<ProblemNode *>::~deque<ProblemNode *>((__int64)v33);
  std::_Tree<std::_Tmap_traits<ProblemNode *,ProblemNode *,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,ProblemNode *>>,0>>::~_Tree<std::_Tmap_traits<ProblemNode *,ProblemNode *,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,ProblemNode *>>,0>>(v32);
  std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,std::allocator<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *>>((__int64)&v29);
  return v27;
}

```

## disassembly

```asm
0x180027e18  mov     [rsp-8+arg_18], rbx
0x180027e1d  push    rbp
0x180027e1e  push    rsi
0x180027e1f  push    rdi
0x180027e20  push    r12
0x180027e22  push    r13
0x180027e24  push    r14
0x180027e26  push    r15
0x180027e28  lea     rbp, [rsp-1F0h]
0x180027e30  sub     rsp, 2F0h
0x180027e37  mov     rax, cs:__security_cookie
0x180027e3e  xor     rax, rsp
0x180027e41  mov     [rbp+220h+var_40], rax
0x180027e48  mov     [rbp+220h+var_298], r8
0x180027e4c  mov     r13, rdx
0x180027e4f  mov     r15, rcx
0x180027e52  xorps   xmm0, xmm0
0x180027e55  movdqu  [rsp+320h+var_2F0], xmm0
0x180027e5b  mov     [rsp+320h+var_2E0], 0
0x180027e64  mov     [rsp+320h+var_2D0], 0
0x180027e6d  mov     [rsp+320h+var_2C8], 0
0x180027e76  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@V?$allocator@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAUtagHELPER_ATTRIBUTE@@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,tagHELPER_ATTRIBUTE *>>>::_Buyheadnode(void)
0x180027e7b  mov     [rsp+320h+var_2D0], rax
0x180027e80  lea     rcx, [rsp+320h+var_2C0]
0x180027e85  call    ??0?$queue@HV?$deque@HV?$allocator@H@std@@@std@@@std@@QEAA@XZ; std::queue<int>::queue<int,std::deque<int>>(void)
0x180027e8a  nop
0x180027e8b  lea     r14, [r15+40h]
0x180027e8f  mov     rdx, r14
0x180027e92  lea     rcx, [rsp+320h+var_2C0]
0x180027e97  call    ?push_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXAEBQEAVProblemNode@@@Z; std::deque<ProblemNode *>::push_back(ProblemNode * const &)
0x180027e9c  xor     r12d, r12d
0x180027e9f  mov     esi, 80000000h
0x180027ea4  cmp     [rbp+220h+var_2A0], 0
0x180027ea9  jz      loc_18002813D
0x180027eaf  lea     r8, [rsp+320h+var_2C0]
0x180027eb4  mov     rdx, [rsp+320h+var_2A8]
0x180027eb9  lea     rcx, [rbp+220h+var_270]
0x180027ebd  call    ??0?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@PEAVProblemNode@@@std@@@std@@@std@@QEAA@_KPEBU_Container_base12@1@@Z; std::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>::_Deque_iterator<std::_Deque_val<std::_Deque_simple_types<ProblemNode *>>>(unsigned __int64,std::_Container_base12 const *)
0x180027ec2  nop
0x180027ec3  mov     r8, [rbp+220h+var_270]
0x180027ec7  test    r8, r8
0x180027eca  jz      short loc_180027ECF
0x180027ecc  mov     r8, [r8]
0x180027ecf  mov     rdx, [rbp+220h+var_260]
0x180027ed3  mov     rcx, rdx
0x180027ed6  shr     rcx, 1
0x180027ed9  mov     rax, [r8+10h]
0x180027edd  dec     rax
0x180027ee0  and     rcx, rax
0x180027ee3  mov     rax, [r8+8]
0x180027ee7  and     edx, 1
0x180027eea  mov     rax, [rax+rcx*8]
0x180027eee  mov     rdi, [rax+rdx*8]
0x180027ef2  mov     rax, [rbp+220h+var_2A0]
0x180027ef6  test    rax, rax
0x180027ef9  jz      short loc_180027F15
0x180027efb  sub     rax, 1
0x180027eff  mov     [rbp+220h+var_2A0], rax
0x180027f03  jnz     short loc_180027F10
0x180027f05  mov     [rsp+320h+var_2A8], 0
0x180027f0e  jmp     short loc_180027F15
0x180027f10  inc     [rsp+320h+var_2A8]
0x180027f15  mov     rbx, [rdi+68h]
0x180027f19  cmp     rbx, [rdi+70h]
0x180027f1d  jz      loc_1800280AA
0x180027f23  mov     rcx, [rbx]
0x180027f26  mov     rdx, r13; lpString2
0x180027f29  mov     rcx, [rcx]; lpString1
0x180027f2c  call    cs:__imp_lstrcmpW
0x180027f32  test    eax, eax
0x180027f34  jnz     loc_1800280A1
0x180027f3a  mov     rax, qword ptr [rsp+320h+var_2F0+8]
0x180027f3f  cmp     rax, qword ptr [rsp+320h+var_2F0]
0x180027f44  jnz     short loc_180027F5A
0x180027f46  mov     [rbp+220h+var_290], rbx
0x180027f4a  mov     [rbp+220h+var_288], rdi
0x180027f4e  mov     r12, rdi
0x180027f51  lea     rdx, [rbp+220h+var_290]
0x180027f55  jmp     loc_180028097
0x180027f5a  cmp     qword ptr [r15+48h], 0
0x180027f5f  jz      loc_18002808B
0x180027f65  xor     edx, edx; Val
0x180027f67  mov     r8d, 208h; Size
0x180027f6d  lea     rcx, [rbp+220h+var_250]; void *
0x180027f71  call    memset_0
0x180027f76  mov     rax, [r14]
0x180027f79  mov     rcx, [rax]
0x180027f7c  mov     rax, [rcx+10h]
0x180027f80  cmp     dword ptr [rax-10h], 0
0x180027f84  jnz     short loc_180027F89
0x180027f86  mov     rax, [rcx]
0x180027f89  mov     [rsp+320h+var_300], rax
0x180027f8e  mov     r9, r13
0x180027f91  lea     r8, aPropertyBagFou; "Property Bag: Found a conflict when sea"...
0x180027f98  mov     edx, 104h; unsigned __int64
0x180027f9d  lea     rcx, [rbp+220h+var_250]; unsigned __int16 *
0x180027fa1  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180027fa6  lea     ecx, [rax+rsi]
0x180027fa9  test    esi, ecx
0x180027fab  jnz     short loc_180027FB8
0x180027fad  cmp     eax, 8007007Ah
0x180027fb2  jnz     loc_18002808B
0x180027fb8  mov     rcx, [r15+48h]
0x180027fbc  mov     rax, [rcx]
0x180027fbf  lea     r8, [rbp+220h+var_250]
0x180027fc3  xor     edx, edx
0x180027fc5  mov     rax, [rax+60h]
0x180027fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fce  mov     rcx, [r15+48h]
0x180027fd2  mov     rax, [rcx]
0x180027fd5  lea     r8, aPropertyBagThe; "Property Bag: The following helper clas"...
0x180027fdc  xor     edx, edx
0x180027fde  mov     rax, [rax+60h]
0x180027fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027fe7  mov     rax, [r12]
0x180027feb  mov     r9, [rax+10h]
0x180027fef  cmp     dword ptr [r9-10h], 0
0x180027ff4  jnz     short loc_180027FF9
0x180027ff6  mov     r9, [rax]
0x180027ff9  lea     r8, aPropertyBagS; "Property Bag: %s"
0x180028000  mov     edx, 104h; unsigned __int64
0x180028005  lea     rcx, [rbp+220h+var_250]; unsigned __int16 *
0x180028009  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002800e  lea     ecx, [rax+rsi]
0x180028011  test    esi, ecx
0x180028013  jnz     short loc_18002801C
0x180028015  cmp     eax, 8007007Ah
0x18002801a  jnz     short loc_18002803A
0x18002801c  mov     rcx, [r15+48h]
0x180028020  mov     rax, [rcx]
0x180028023  mov     r9, [r12]
0x180028027  mov     r9, [r9+28h]
0x18002802b  lea     r8, [rbp+220h+var_250]
0x18002802f  xor     edx, edx
0x180028031  mov     rax, [rax+70h]
0x180028035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002803a  mov     rax, [rdi]
0x18002803d  mov     r9, [rax+10h]
0x180028041  cmp     dword ptr [r9-10h], 0
0x180028046  jnz     short loc_18002804B
0x180028048  mov     r9, [rax]
0x18002804b  lea     r8, aPropertyBagS; "Property Bag: %s"
0x180028052  mov     edx, 104h; unsigned __int64
0x180028057  lea     rcx, [rbp+220h+var_250]; unsigned __int16 *
0x18002805b  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028060  lea     ecx, [rax+rsi]
0x180028063  test    esi, ecx
0x180028065  jnz     short loc_18002806E
0x180028067  cmp     eax, 8007007Ah
0x18002806c  jnz     short loc_18002808B
0x18002806e  mov     rcx, [r15+48h]
0x180028072  mov     rax, [rcx]
0x180028075  mov     r9, [rdi]
0x180028078  mov     r9, [r9+28h]
0x18002807c  lea     r8, [rbp+220h+var_250]
0x180028080  xor     edx, edx
0x180028082  mov     rax, [rax+70h]
0x180028086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002808b  mov     [rbp+220h+var_280], rbx
0x18002808f  mov     [rbp+220h+var_278], rdi
0x180028093  lea     rdx, [rbp+220h+var_280]
0x180028097  lea     rcx, [rsp+320h+var_2F0]
0x18002809c  call    ?push_back@?$vector@UPropertyBagEntry@@V?$allocator@UPropertyBagEntry@@@std@@@std@@QEAAXAEBUPropertyBagEntry@@@Z; std::vector<PropertyBagEntry>::push_back(PropertyBagEntry const &)
0x1800280a1  add     rbx, 10h
0x1800280a5  jmp     loc_180027F19
0x1800280aa  cmp     r12, rdi
0x1800280ad  jz      loc_180027EA4
0x1800280b3  mov     rbx, [rdi+8]
0x1800280b7  mov     rbx, [rbx]
0x1800280ba  cmp     rbx, [rdi+8]
0x1800280be  jz      short loc_180028134
0x1800280c0  mov     r14, [rbx+20h]
0x1800280c4  mov     [rsp+320h+var_2D8], r14
0x1800280c9  lea     rdx, [rsp+320h+var_2D8]
0x1800280ce  lea     rcx, [rsp+320h+var_2D0]
0x1800280d3  call    ??A?$map@PEAVProblemNode@@PEAV1@U?$less@PEAVProblemNode@@@std@@V?$allocator@U?$pair@QEAVProblemNode@@PEAV1@@std@@@3@@std@@QEAAAEAPEAVProblemNode@@AEBQEAV2@@Z; std::map<ProblemNode *,ProblemNode *>::operator[](ProblemNode * const &)
0x1800280d8  xor     edx, edx
0x1800280da  cmp     [rax], rdx
0x1800280dd  jnz     short loc_180028102
0x1800280df  lea     rdx, [rsp+320h+var_2D8]
0x1800280e4  lea     rcx, [rsp+320h+var_2C0]
0x1800280e9  call    ?push_back@?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAAXAEBQEAVProblemNode@@@Z; std::deque<ProblemNode *>::push_back(ProblemNode * const &)
0x1800280ee  lea     rdx, [rsp+320h+var_2D8]
0x1800280f3  lea     rcx, [rsp+320h+var_2D0]
0x1800280f8  call    ??A?$map@PEAVProblemNode@@PEAV1@U?$less@PEAVProblemNode@@@std@@V?$allocator@U?$pair@QEAVProblemNode@@PEAV1@@std@@@3@@std@@QEAAAEAPEAVProblemNode@@AEBQEAV2@@Z; std::map<ProblemNode *,ProblemNode *>::operator[](ProblemNode * const &)
0x1800280fd  mov     [rax], r14
0x180028100  xor     edx, edx
0x180028102  cmp     [rbx+19h], dl
0x180028105  jnz     short loc_1800280BA
0x180028107  mov     rcx, [rbx+10h]
0x18002810b  cmp     [rcx+19h], dl
0x18002810e  jnz     short loc_180028117
0x180028110  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVCExtensionHelperInfoContainer@@@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>>>::_Min(std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,CExtensionHelperInfoContainer *>,void *> *)
0x180028115  jmp     short loc_18002812F
0x180028117  mov     rax, [rbx+8]
0x18002811b  jmp     short loc_18002812A
0x18002811d  cmp     rbx, [rax+10h]
0x180028121  jnz     short loc_18002812F
0x180028123  mov     rbx, rax
0x180028126  mov     rax, [rax+8]
0x18002812a  cmp     [rax+19h], dl
0x18002812d  jz      short loc_18002811D
0x18002812f  mov     rbx, rax
0x180028132  jmp     short loc_1800280BA
0x180028134  lea     r14, [r15+40h]
0x180028138  jmp     loc_180027EA4
0x18002813d  mov     rcx, qword ptr [rsp+320h+var_2F0+8]
0x180028142  mov     rdx, qword ptr [rsp+320h+var_2F0]
0x180028147  cmp     rcx, rdx
0x18002814a  mov     rsi, [rbp+220h+var_298]
0x18002814e  jz      short loc_180028188
0x180028150  lea     rax, [rsp+320h+var_2F0]
0x180028155  cmp     rsi, rax
0x180028158  jz      short loc_180028184
0x18002815a  mov     rax, [rsi]
0x18002815d  mov     [rsi], rdx
0x180028160  mov     qword ptr [rsp+320h+var_2F0], rax
0x180028165  mov     rax, [rsi+8]
0x180028169  mov     [rsi+8], rcx
0x18002816d  mov     qword ptr [rsp+320h+var_2F0+8], rax
0x180028172  mov     rcx, [rsi+10h]
0x180028176  mov     rax, [rsp+320h+var_2E0]
0x18002817b  mov     [rsi+10h], rax
0x18002817f  mov     [rsp+320h+var_2E0], rcx
0x180028184  xor     ebx, ebx
0x180028186  jmp     short loc_18002818D
0x180028188  mov     ebx, 80070002h
0x18002818d  lea     rcx, [rsp+320h+var_2C0]
0x180028192  call    ??1?$deque@PEAVProblemNode@@V?$allocator@PEAVProblemNode@@@std@@@std@@QEAA@XZ; std::deque<ProblemNode *>::~deque<ProblemNode *>(void)
0x180028197  nop
0x180028198  lea     rcx, [rsp+320h+var_2D0]
0x18002819d  call    ??1?$_Tree@V?$_Tmap_traits@PEAVProblemNode@@PEAV1@U?$less@PEAVProblemNode@@@std@@V?$allocator@U?$pair@QEAVProblemNode@@PEAV1@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<ProblemNode *,ProblemNode *,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,ProblemNode *>>,0>>::~_Tree<std::_Tmap_traits<ProblemNode *,ProblemNode *,std::less<ProblemNode *>,std::allocator<std::pair<ProblemNode * const,ProblemNode *>>,0>>(void)
0x1800281a2  nop
0x1800281a3  lea     rcx, [rsp+320h+var_2F0]
0x1800281a8  call    ??1?$vector@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@PEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>::~vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,std::allocator<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *>>(void)
0x1800281ad  mov     eax, ebx
0x1800281af  mov     rcx, [rbp+220h+var_40]
0x1800281b6  xor     rcx, rsp; StackCookie
0x1800281b9  call    __security_check_cookie
0x1800281be  mov     rbx, [rsp+320h+arg_18]
0x1800281c6  add     rsp, 2F0h
0x1800281cd  pop     r15
0x1800281cf  pop     r14
0x1800281d1  pop     r13
0x1800281d3  pop     r12
0x1800281d5  pop     rdi
0x1800281d6  pop     rsi
0x1800281d7  pop     rbp
0x1800281d8  retn
```
